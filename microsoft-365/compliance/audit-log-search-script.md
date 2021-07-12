---
title: Een PowerShell-script gebruiken om in het auditlogboek te zoeken
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom: seo-marvel-apr2020
description: Een PowerShell-script gebruiken dat de cmdlet Search-UnifiedAuditLog in Exchange Online gebruikt om het auditlogboek te doorzoeken. Dit script is geoptimaliseerd voor het retourneren van een grote set (maximaal 50.000) van auditrecords. Het script exporteert deze records naar een CSV-bestand dat u kunt bekijken of transformeren met behulp van Power Query in Excel.
ms.openlocfilehash: 8abea51bb1e7e1fa7bd513bea78708b06da62def
ms.sourcegitcommit: 5db5047c24b56f3af90c2bc5c830a7a13eeeccad
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/09/2021
ms.locfileid: "53341006"
---
# <a name="use-a-powershell-script-to-search-the-audit-log"></a>Een PowerShell-script gebruiken om in het auditlogboek te zoeken

Beveiliging, compliance en controle zijn de hoogste prioriteit geworden voor IT-beheerders tegenwoordig. Microsoft 365 heeft verschillende ingebouwde mogelijkheden om organisaties te helpen bij het beheren van beveiliging, compliance en controle. Met geïntegreerde logboekregistratie kunt u met name beveiligingsincidenten en nalevingsproblemen onderzoeken. U kunt auditlogboeken ophalen met behulp van de volgende methoden:

- [De Office 365 Management Activity-API](/office/office-365-management-api/office-365-management-activity-api-reference)

- Het [hulpprogramma Zoeken in auditlogboek](search-the-audit-log-in-security-and-compliance.md) in het Microsoft 365-compliancecentrum.

- De cmdlet [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog) in Exchange Online PowerShell

Als u regelmatig auditlogboeken moet ophalen, dient u een oplossing te overwegen die gebruikmaakt van de Office 365 Management Activity-API, omdat deze grote organisaties de schaalbaarheid en prestaties kan bieden om ononderbroken miljoenen auditrecords op te halen. Het zoekprogramma voor het auditlogboek in het Microsoft 365-compliancecentrum is een goede manier om snel auditrecords te vinden voor specifieke bewerkingen die in een kortere periode plaatsvinden. Door gebruik te maken van langere tijdsbereiken in het zoekprogramma voor het auditlogboek, met name voor grote organisaties, kunnen algauw te veel records worden als retourneert om ze gemakkelijk te beheren of te exporteren.

In situaties waarin u handmatig auditgegevens moet ophalen voor een specifiek onderzoek of incident, met name voor langere datumbereiken in grotere organisaties, is het gebruik van de cmdlet **Search-UnifiedAuditLog** mogelijk de beste optie. Dit artikel bevat een PowerShell-script waarin de cmdlet wordt gebruikt om tot 50.000 auditrecords op te halen en deze vervolgens te exporteren naar een CSV-bestand dat u kunt opmaken met behulp van Power Query in Excel. Door het script in dit artikel te gebruiken, verkleint u ook de kans dat er bij grote zoekopdrachten in auditlogboek een time-out optreedt.

## <a name="before-you-run-the-script"></a>Voor u het script ExportO365UserInfo uitvoert

- Controlelogboekregistratie moet zijn ingeschakeld zodat uw organisatie met succes het script kan gebruiken om auditrecords te retourneren. Auditlogboekregistratie is standaard ingeschakeld voor organisaties met Microsoft 365 en Office 365 Enterprise. Als u wilt controleren of zoeken in auditlogboek is ingeschakeld voor uw organisatie, kunt u de volgende opdracht uitvoeren in Exchange Online PowerShell:

  ```powershell
  Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
  ```

  De waarde van `True` voor de eigenschap **UnifiedAuditLogIngestionEnabled** geeft aan dat zoeken in auditlogboek is ingeschakeld.

- Als u het script wilt uitvoeren moet aan u de rol Auditlogboeken alleen-weergeven of Auditlogboeken in Exchange Online zijn toegewezen. Deze rollen worden standaard toegewezen aan de rollengroepen Compliancebeheer en Organisatiebeheer op de pagina Machtigingen in het Exchange-beheercentrum. Zie voor meer informatie de sectie 'Vereisten voor het doorzoeken van het auditlogboek' in [Zoek in het auditlogboek in het compliancecentrum](search-the-audit-log-in-security-and-compliance.md#before-you-search-the-audit-log).

- Het kan lang duren voordat het script is voltooid. Hoe lang het duurt om deze uit te voeren, is afhankelijk van het datumbereik en de grootte van het interval waar u het script voor configureert om auditrecords voor op te halen. Grotere datumbereiken en kleinere intervallen leiden tot een lange oplopende tijd. Zie de tabel in stap 2 voor meer informatie over het datumbereik en de intervallen.

- Het voorbeeldscript in dit artikel wordt niet ondersteund door een standaardondersteuningsprogramma of -service van Microsoft. Het voorbeeldscripts wordt zonder enige garantie ONGEWIJZIGD verstrekt. Microsoft wijst alle impliciete garanties met inbegrip van, maar niet beperkt tot, impliciete garanties van verkoopbaarheid en geschiktheid voor een bepaald doel af. Het risico dat ontstaat als gevolg van het gebruik of prestaties van het voorbeeldscript ligt geheel bij u. In geen geval kan Microsoft, haar auteurs of anderen die bij het maken, produceren of leveren van de scripts zijn betrokken, aansprakelijk worden gehouden voor enige schade om welke reden dan ook (met inbegrip van maar niet beperkt tot schade door verlies van bedrijfswinsten, belemmering van de bedrijfsuitvoering, verlies van bedrijfsinformatie of andere geldelijke verliezen) voortvloeiend uit het gebruik of de onmogelijkheid van het gebruik van de voorbeeldscripts, zelfs als Microsoft op de hoogte is gesteld van de mogelijkheid van dergelijke schade.

## <a name="step-1-connect-to-exchange-online-powershell"></a>Stap 1: Verbinding maken met Exchange Online PowerShell

De eerste stap is verbinding maken met Exchange Online PowerShell. U kunt verbinding maken via moderne verificatie of met MFA (Multi-Factor Authentication). Zie [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) (Verbinding maken met Exchange Online PowerShell) voor stapsgewijze instructies.

## <a name="step-2-modify-and-run-the-script-to-retrieve-audit-records"></a>Stap 2: Het script wijzigen en uitvoeren om auditrecords op te halen

Nadat u verbinding hebt gemaakt met Exchange Online PowerShell, bestaat de volgende stap uit het maken, wijzigen en uitvoeren van het script om de controlegegevens op te halen. De eerste zeven regels in het zoekscript voor het auditlogboek bevatten de volgende variabelen die u kunt wijzigen om uw zoekopdracht te configureren. Zie de tabel in stap 2 voor een beschrijving van deze variabelen.

1. Sla de volgende tekst op in een Windows PowerShell-script door het bestandsnaamachtervoegsel .ps1 te gebruiken. Bijvoorbeeld, SearchAuditLog.ps1.

   ```powershell
   #Modify the values for the following variables to configure the audit log search.
   $logFile = "d:\AuditLogSearch\AuditLogSearchLog.txt"
   $outputFile = "d:\AuditLogSearch\AuditLogRecords.csv"
   [DateTime]$start = [DateTime]::UtcNow.AddDays(-1)
   [DateTime]$end = [DateTime]::UtcNow
   $record = "AzureActiveDirectory"
   $resultSize = 5000
   $intervalMinutes = 60
   
   #Start script
   [DateTime]$currentStart = $start
   [DateTime]$currentEnd = $start
   
   Function Write-LogFile ([String]$Message)
   {
       $final = [DateTime]::Now.ToUniversalTime().ToString("s") + ":" + $Message
       $final | Out-File $logFile -Append
   }
   
   Write-LogFile "BEGIN: Retrieving audit records between $($start) and $($end), RecordType=$record, PageSize=$resultSize."
   Write-Host "Retrieving audit records for the date range between $($start) and $($end), RecordType=$record, ResultsSize=$resultSize"
   
   $totalCount = 0
   while ($true)
   {
       $currentEnd = $currentStart.AddMinutes($intervalMinutes)
       if ($currentEnd -gt $end)
       {
           $currentEnd = $end
       }
   
       if ($currentStart -eq $currentEnd)
       {
           break
       }
   
       $sessionID = [Guid]::NewGuid().ToString() + "_" +  "ExtractLogs" + (Get-Date).ToString("yyyyMMddHHmmssfff")
       Write-LogFile "INFO: Retrieving audit records for activities performed between $($currentStart) and $($currentEnd)"
       Write-Host "Retrieving audit records for activities performed between $($currentStart) and $($currentEnd)"
       $currentCount = 0
   
       $sw = [Diagnostics.StopWatch]::StartNew()
       do
       {
           $results = Search-UnifiedAuditLog -StartDate $currentStart -EndDate $currentEnd -RecordType $record -SessionId $sessionID -SessionCommand ReturnLargeSet -ResultSize $resultSize
   
           if (($results | Measure-Object).Count -ne 0)
           {
               $results | export-csv -Path $outputFile -Append -NoTypeInformation
   
               $currentTotal = $results[0].ResultCount
               $totalCount += $results.Count
               $currentCount += $results.Count
               Write-LogFile "INFO: Retrieved $($currentCount) audit records out of the total $($currentTotal)"
   
               if ($currentTotal -eq $results[$results.Count - 1].ResultIndex)
               {
                   $message = "INFO: Successfully retrieved $($currentTotal) audit records for the current time range. Moving on!"
                   Write-LogFile $message
                   Write-Host "Successfully retrieved $($currentTotal) audit records for the current time range. Moving on to the next interval." -foregroundColor Yellow
                   ""
                   break
               }
           }
       }
       while (($results | Measure-Object).Count -ne 0)
   
       $currentStart = $currentEnd
   }
   
   Write-LogFile "END: Retrieving audit records between $($start) and $($end), RecordType=$record, PageSize=$resultSize, total count: $totalCount."
   Write-Host "Script complete! Finished retrieving audit records for the date range between $($start) and $($end). Total count: $totalCount" -foregroundColor Green
   ```

2. Wijzig de variabelen in de volgende tabel om de zoekcriteria te configureren. Het script bevat voorbeeldwaarden voor deze variabelen, maar u moet deze wijzigen (tenzij anders wordt vermeld) om te voldoen aan uw specifieke vereisten.

   <br>

   ****

   |Variabele|Voorbeeldwaarde|Omschrijving|
   |---|---|---|
   |`$logFile`|"d:\temp\AuditSearchLog.txt"|De naam en locatie van het logboekbestand met informatie over de voortgang van de zoekopdracht in het auditlogboek die door het script wordt uitgevoerd. Het script schrijft UTC-tijdstempels naar het logbestand.|
   |`$outputFile`|"d:\temp\AuditRecords.csv"|Hiermee geeft u de naam en locatie op van het CSV-bestand dat de auditrecords bevat die door het script worden geretourneerd.|
   |`[DateTime]$start` en `[DateTime]$end`|[DateTime]::UtcNow.AddDays(-1) <br/>[DateTime]::UtcNow|Hiermee geeft u het datumbereik voor het zoeken in het auditlogboek op. Het script retourneert records voor controleactiviteiten die hebben plaatsgevonden binnen het opgegeven datumbereik. Als u bijvoorbeeld activiteiten wilt retourneren die zijn uitgevoerd in januari 2021, kunt u een begindatum van `"2021-01-01"` en een einddatum van `"2021-01-31"` gebruiken (plaats de waarden tussen dubbele aanhalingstekens) Met de voorbeeldwaarde in het script worden records als resultaat geven voor activiteiten die in de afgelopen 24 uur zijn uitgevoerd. Als de waarde geen tijdstempel bevat, is de standaardtijdstempel 12:00 uur (middernacht) op de opgegeven datum.|
   |`$record`|"AzureActiveDirectory"|Het recordtype van de controleactiviteiten (ook wel controle *bewerkingen* genoemd) die u wilt zoeken. Deze eigenschap geeft de service of functie aan waarin een activiteit is geactiveerd. Zie [Het recordtype Auditlogboek](/office/office-365-management-api/office-365-management-activity-api-schema#auditlogrecordtype)voor een lijst met recordtypen die u voor deze variabele kunt gebruiken. U kunt de naam van het recordtype of de ENUM-waarde gebruiken. <br/><br/>**Tip:** als u auditrecords voor alle recordtypen wilt retourneren, gebruikt u de waarde `$null` (zonder dubbele aanhalingstekens).|
   |`$resultSize`|5000|Het aantal resultaten dat telkens wordt geretourneerd als de cmdlet **Search-UnifiedAuditLog** door het script wordt aangeroepen (een *resultatenset*). De waarde van 5000 is de maximumwaarde die wordt ondersteund door de cmdlet. Laat deze waarde ingesteld zonder wijziging.|
   |`$intervalMinutes`|60|Om de limiet van 5000 geretourneerde records te helpen om te komen, neemt deze variabele het gegevensbereik op dat u hebt opgegeven en worden deze in kleinere tijdsintervallen gehouden. Nu is elk interval, niet het hele datumbereik, onderhevig aan de uitvoerlimiet van 5000 records van de opdracht. Voor de meeste organisaties moet de standaardwaarde van 5000 records per tijdsinterval van 60 minuten binnen het datumbereik voldoende zijn. Maar als het script een fout retourneert zoals: `maximum results limitation reached`, verlaag dan het tijdsinterval (bijvoorbeeld tot 30 minuten of zelfs 15 minuten) en voer het script opnieuw uit.|
   ||||

   De meeste variabelen in de vorige tabel komen overeen met parameters voor de cmdlet **Search-UnifiedAuditLog**. Zie [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog) voor meer informatie over deze parameters.

3. Open Windows PowerShell op uw lokale computer en ga naar de map waarin u het gewijzigde script hebt opgeslagen.

4. Voer het volgende script uit in Exchange Online PowerShell; bijvoorbeeld:

   ```powershell
   .\SearchAuditLog.ps1
   ```

Tijdens het uitvoeren van het script worden voortgangsberichten weergegeven. Nadat het script is uitgevoerd, wordt het logboekbestand en het CSV-bestand met de auditrecords gemaakt en worden deze opgeslagen in de mappen die zijn gedefinieerd door de variabelen `$logFile` en `$outputFile`.

> [!IMPORTANT]
> Er geldt een limiet van 50.000 voor het maximum aantal controlerecords dat telkens wordt geretourneerd wanneer u dit script gebruikt. Als u dit script uitvoeren en 50.000 resultaten retourneert, is de kans groot dat de auditrecords voor activiteiten die binnen het datumbereik hebben plaatsgevonden, niet zijn opgenomen. Als dit gebeurt, is het raadzaam om het datumbereik op te splitsen in kleinere duur en het script vervolgens opnieuw uit te voeren voor elk datumbereik. Als een datumbereik van 90 dagen bijvoorbeeld 50.000 resultaten oplevert, kunt u het script tweemaal opnieuw uitvoeren, één keer voor de eerste 45 dagen in het datumbereik en vervolgens weer voor de volgende 45 dagen.

## <a name="step-3-format-and-view-the-audit-records"></a>Stap 3: De auditrecords opmaken en weergeven

Nadat u het script hebt uitgevoerd en de auditrecords hebt geëxporteerd naar een CSV-bestand, wilt u het CSV-bestand mogelijk opmaken om de controlerecords eenvoudiger te kunnen controleren en analyseren. Eén manier om dit te doen is met de transformatiefunctie JSON van Power Query in Excel om elke eigenschap in het JSON-object in de kolom **AuditData** te splitsen in een eigen kolom. Zie "Stap 2: de geëxporteerde autditlogboeken opmaken met de Power Query Editor'  voor stapsgewijze instructies in [Auditlogboekrecords exporteren, configureren en bekijken](export-view-audit-log-records.md#step-2-format-the-exported-audit-log-using-the-power-query-editor).
