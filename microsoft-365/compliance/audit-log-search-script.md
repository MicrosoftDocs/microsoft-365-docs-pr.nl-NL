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
# <a name="use-a-powershell-script-to-search-the-audit-log"></a><span data-ttu-id="edf7f-105">Een PowerShell-script gebruiken om in het auditlogboek te zoeken</span><span class="sxs-lookup"><span data-stu-id="edf7f-105">Use a PowerShell script to search the audit log</span></span>

<span data-ttu-id="edf7f-106">Beveiliging, compliance en controle zijn de hoogste prioriteit geworden voor IT-beheerders tegenwoordig.</span><span class="sxs-lookup"><span data-stu-id="edf7f-106">Security, compliance, and auditing have become a top priority for IT administrators in today’s world.</span></span> <span data-ttu-id="edf7f-107">Microsoft 365 heeft verschillende ingebouwde mogelijkheden om organisaties te helpen bij het beheren van beveiliging, compliance en controle.</span><span class="sxs-lookup"><span data-stu-id="edf7f-107">Microsoft 365 has several built-in capabilities to help organizations manage security, compliance, and auditing.</span></span> <span data-ttu-id="edf7f-108">Met geïntegreerde logboekregistratie kunt u met name beveiligingsincidenten en nalevingsproblemen onderzoeken.</span><span class="sxs-lookup"><span data-stu-id="edf7f-108">In particular, unified audit logging can help you investigate security incidents and compliance issues.</span></span> <span data-ttu-id="edf7f-109">U kunt auditlogboeken ophalen met behulp van de volgende methoden:</span><span class="sxs-lookup"><span data-stu-id="edf7f-109">You can retrieve audit logs by using the following methods:</span></span>

- [<span data-ttu-id="edf7f-110">De Office 365 Management Activity-API</span><span class="sxs-lookup"><span data-stu-id="edf7f-110">The Office 365 Management Activity API</span></span>](/office/office-365-management-api/office-365-management-activity-api-reference)

- <span data-ttu-id="edf7f-111">Het [hulpprogramma Zoeken in auditlogboek](search-the-audit-log-in-security-and-compliance.md) in het Microsoft 365-compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="edf7f-111">The [audit log search tool](search-the-audit-log-in-security-and-compliance.md) in the Microsoft 365 compliance center</span></span>

- <span data-ttu-id="edf7f-112">De cmdlet [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog) in Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="edf7f-112">The [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog) cmdlet in Exchange Online PowerShell</span></span>

<span data-ttu-id="edf7f-113">Als u regelmatig auditlogboeken moet ophalen, dient u een oplossing te overwegen die gebruikmaakt van de Office 365 Management Activity-API, omdat deze grote organisaties de schaalbaarheid en prestaties kan bieden om ononderbroken miljoenen auditrecords op te halen.</span><span class="sxs-lookup"><span data-stu-id="edf7f-113">If you need to retrieve audit logs on a regular basis, you should consider a solution that uses the Office 365 Management Activity API because it that can provide large organizations with the scalability and performance to retrieve millions of audit records on an ongoing basis.</span></span> <span data-ttu-id="edf7f-114">Het zoekprogramma voor het auditlogboek in het Microsoft 365-compliancecentrum is een goede manier om snel auditrecords te vinden voor specifieke bewerkingen die in een kortere periode plaatsvinden.</span><span class="sxs-lookup"><span data-stu-id="edf7f-114">Using the audit log search tool in Microsoft 365 compliance center is a good way to quickly find audit records for specific operations that occur in shorter time range.</span></span> <span data-ttu-id="edf7f-115">Door gebruik te maken van langere tijdsbereiken in het zoekprogramma voor het auditlogboek, met name voor grote organisaties, kunnen algauw te veel records worden als retourneert om ze gemakkelijk te beheren of te exporteren.</span><span class="sxs-lookup"><span data-stu-id="edf7f-115">Using longer time ranges in the audit log search tool, especially for large organizations, might return too many records to easily manage or export.</span></span>

<span data-ttu-id="edf7f-116">In situaties waarin u handmatig auditgegevens moet ophalen voor een specifiek onderzoek of incident, met name voor langere datumbereiken in grotere organisaties, is het gebruik van de cmdlet **Search-UnifiedAuditLog** mogelijk de beste optie.</span><span class="sxs-lookup"><span data-stu-id="edf7f-116">When there are situations where you need to manually retrieve auditing data for a specific investigation or incident, particularly for longer date ranges in larger organizations, using the **Search-UnifiedAuditLog** cmdlet may be the best option.</span></span> <span data-ttu-id="edf7f-117">Dit artikel bevat een PowerShell-script waarin de cmdlet wordt gebruikt om tot 50.000 auditrecords op te halen en deze vervolgens te exporteren naar een CSV-bestand dat u kunt opmaken met behulp van Power Query in Excel.</span><span class="sxs-lookup"><span data-stu-id="edf7f-117">This article includes a PowerShell script that uses the cmdlet to retrieve up to 50,000 audit records and then export them to a CSV file that you can format using Power Query in Excel to help with your review.</span></span> <span data-ttu-id="edf7f-118">Door het script in dit artikel te gebruiken, verkleint u ook de kans dat er bij grote zoekopdrachten in auditlogboek een time-out optreedt.</span><span class="sxs-lookup"><span data-stu-id="edf7f-118">Using the script in this article also minimizes the chance that large audit log searches will time out in the service.</span></span>

## <a name="before-you-run-the-script"></a><span data-ttu-id="edf7f-119">Voor u het script ExportO365UserInfo uitvoert</span><span class="sxs-lookup"><span data-stu-id="edf7f-119">Before you run the script</span></span>

- <span data-ttu-id="edf7f-120">Controlelogboekregistratie moet zijn ingeschakeld zodat uw organisatie met succes het script kan gebruiken om auditrecords te retourneren.</span><span class="sxs-lookup"><span data-stu-id="edf7f-120">Audit logging has to be enabled for your organization to successfully use the script to return audit records.</span></span> <span data-ttu-id="edf7f-121">Auditlogboekregistratie is standaard ingeschakeld voor organisaties met Microsoft 365 en Office 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="edf7f-121">Audit logging is turned on by default for Microsoft 365 and Office 365 enterprise organizations.</span></span> <span data-ttu-id="edf7f-122">Als u wilt controleren of zoeken in auditlogboek is ingeschakeld voor uw organisatie, kunt u de volgende opdracht uitvoeren in Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="edf7f-122">To verify that audit log search is turned on for your organization, you can run the following command in Exchange Online PowerShell:</span></span>

  ```powershell
  Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
  ```

  <span data-ttu-id="edf7f-123">De waarde van `True` voor de eigenschap **UnifiedAuditLogIngestionEnabled** geeft aan dat zoeken in auditlogboek is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="edf7f-123">The value of `True` for the **UnifiedAuditLogIngestionEnabled** property indicates that audit log search is turned on.</span></span>

- <span data-ttu-id="edf7f-124">Als u het script wilt uitvoeren moet aan u de rol Auditlogboeken alleen-weergeven of Auditlogboeken in Exchange Online zijn toegewezen.</span><span class="sxs-lookup"><span data-stu-id="edf7f-124">You have to be assigned the View-Only Audit Logs or Audit Logs role in Exchange Online to run successfully the script.</span></span> <span data-ttu-id="edf7f-125">Deze rollen worden standaard toegewezen aan de rollengroepen Compliancebeheer en Organisatiebeheer op de pagina Machtigingen in het Exchange-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="edf7f-125">By default, these roles are assigned to the Compliance Management and Organization Management role groups on the Permissions page in the Exchange admin center.</span></span> <span data-ttu-id="edf7f-126">Zie voor meer informatie de sectie 'Vereisten voor het doorzoeken van het auditlogboek' in [Zoek in het auditlogboek in het compliancecentrum](search-the-audit-log-in-security-and-compliance.md#before-you-search-the-audit-log).</span><span class="sxs-lookup"><span data-stu-id="edf7f-126">For more information, see the "Requirements to search the audit log" section in [Search the audit log in the compliance center](search-the-audit-log-in-security-and-compliance.md#before-you-search-the-audit-log).</span></span>

- <span data-ttu-id="edf7f-127">Het kan lang duren voordat het script is voltooid.</span><span class="sxs-lookup"><span data-stu-id="edf7f-127">It may take a long time for the script to complete.</span></span> <span data-ttu-id="edf7f-128">Hoe lang het duurt om deze uit te voeren, is afhankelijk van het datumbereik en de grootte van het interval waar u het script voor configureert om auditrecords voor op te halen.</span><span class="sxs-lookup"><span data-stu-id="edf7f-128">How long it takes to run depends on the date range and the size of the interval that you configure the script to retrieve audit records for.</span></span> <span data-ttu-id="edf7f-129">Grotere datumbereiken en kleinere intervallen leiden tot een lange oplopende tijd.</span><span class="sxs-lookup"><span data-stu-id="edf7f-129">Larger date ranges and smaller intervals will result in a long running time.</span></span> <span data-ttu-id="edf7f-130">Zie de tabel in stap 2 voor meer informatie over het datumbereik en de intervallen.</span><span class="sxs-lookup"><span data-stu-id="edf7f-130">See the table in Step 2 for more information about the date range and intervals.</span></span>

- <span data-ttu-id="edf7f-131">Het voorbeeldscript in dit artikel wordt niet ondersteund door een standaardondersteuningsprogramma of -service van Microsoft.</span><span class="sxs-lookup"><span data-stu-id="edf7f-131">The sample script provided in this article isn't supported under any Microsoft standard support program or service.</span></span> <span data-ttu-id="edf7f-132">Het voorbeeldscripts wordt zonder enige garantie ONGEWIJZIGD verstrekt.</span><span class="sxs-lookup"><span data-stu-id="edf7f-132">The sample script is provided AS IS without warranty of any kind.</span></span> <span data-ttu-id="edf7f-133">Microsoft wijst alle impliciete garanties met inbegrip van, maar niet beperkt tot, impliciete garanties van verkoopbaarheid en geschiktheid voor een bepaald doel af.</span><span class="sxs-lookup"><span data-stu-id="edf7f-133">Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span></span> <span data-ttu-id="edf7f-134">Het risico dat ontstaat als gevolg van het gebruik of prestaties van het voorbeeldscript ligt geheel bij u.</span><span class="sxs-lookup"><span data-stu-id="edf7f-134">The entire risk arising out of the use or performance of the sample script and documentation remains with you.</span></span> <span data-ttu-id="edf7f-135">In geen geval kan Microsoft, haar auteurs of anderen die bij het maken, produceren of leveren van de scripts zijn betrokken, aansprakelijk worden gehouden voor enige schade om welke reden dan ook (met inbegrip van maar niet beperkt tot schade door verlies van bedrijfswinsten, belemmering van de bedrijfsuitvoering, verlies van bedrijfsinformatie of andere geldelijke verliezen) voortvloeiend uit het gebruik of de onmogelijkheid van het gebruik van de voorbeeldscripts, zelfs als Microsoft op de hoogte is gesteld van de mogelijkheid van dergelijke schade.</span><span class="sxs-lookup"><span data-stu-id="edf7f-135">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the script be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample script or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>

## <a name="step-1-connect-to-exchange-online-powershell"></a><span data-ttu-id="edf7f-136">Stap 1: Verbinding maken met Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="edf7f-136">Step 1: Connect to Exchange Online PowerShell</span></span>

<span data-ttu-id="edf7f-137">De eerste stap is verbinding maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="edf7f-137">The first step is to connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="edf7f-138">U kunt verbinding maken via moderne verificatie of met MFA (Multi-Factor Authentication).</span><span class="sxs-lookup"><span data-stu-id="edf7f-138">You can connect using modern authentication or with multi-factor authentication (MFA).</span></span> <span data-ttu-id="edf7f-139">Zie [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) (Verbinding maken met Exchange Online PowerShell) voor stapsgewijze instructies.</span><span class="sxs-lookup"><span data-stu-id="edf7f-139">For step-by-step instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

## <a name="step-2-modify-and-run-the-script-to-retrieve-audit-records"></a><span data-ttu-id="edf7f-140">Stap 2: Het script wijzigen en uitvoeren om auditrecords op te halen</span><span class="sxs-lookup"><span data-stu-id="edf7f-140">Step 2: Modify and run the script to retrieve audit records</span></span>

<span data-ttu-id="edf7f-141">Nadat u verbinding hebt gemaakt met Exchange Online PowerShell, bestaat de volgende stap uit het maken, wijzigen en uitvoeren van het script om de controlegegevens op te halen.</span><span class="sxs-lookup"><span data-stu-id="edf7f-141">After you've connected to Exchange Online PowerShell, the next step is to create, modify, and run the script to retrieve the auditing data.</span></span> <span data-ttu-id="edf7f-142">De eerste zeven regels in het zoekscript voor het auditlogboek bevatten de volgende variabelen die u kunt wijzigen om uw zoekopdracht te configureren.</span><span class="sxs-lookup"><span data-stu-id="edf7f-142">The first seven lines in the audit log search script contain the following variables that you can modify to configure your search.</span></span> <span data-ttu-id="edf7f-143">Zie de tabel in stap 2 voor een beschrijving van deze variabelen.</span><span class="sxs-lookup"><span data-stu-id="edf7f-143">See the table in step 2 for a description of these variables.</span></span>

1. <span data-ttu-id="edf7f-p111">Sla de volgende tekst op in een Windows PowerShell-script door het bestandsnaamachtervoegsel .ps1 te gebruiken. Bijvoorbeeld, SearchAuditLog.ps1.</span><span class="sxs-lookup"><span data-stu-id="edf7f-p111">Save the following text to a Windows PowerShell script by using a filename suffix of .ps1. For example, SearchAuditLog.ps1.</span></span>

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

2. <span data-ttu-id="edf7f-146">Wijzig de variabelen in de volgende tabel om de zoekcriteria te configureren.</span><span class="sxs-lookup"><span data-stu-id="edf7f-146">Modify the variables listed in the following table to configure the search criteria.</span></span> <span data-ttu-id="edf7f-147">Het script bevat voorbeeldwaarden voor deze variabelen, maar u moet deze wijzigen (tenzij anders wordt vermeld) om te voldoen aan uw specifieke vereisten.</span><span class="sxs-lookup"><span data-stu-id="edf7f-147">The script includes sample values for these variables, but you should change them (unless stated otherwise) to meet your specific requirements.</span></span>

   <br>

   ****

   |<span data-ttu-id="edf7f-148">Variabele</span><span class="sxs-lookup"><span data-stu-id="edf7f-148">Variable</span></span>|<span data-ttu-id="edf7f-149">Voorbeeldwaarde</span><span class="sxs-lookup"><span data-stu-id="edf7f-149">Sample value</span></span>|<span data-ttu-id="edf7f-150">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="edf7f-150">Description</span></span>|
   |---|---|---|
   |`$logFile`|<span data-ttu-id="edf7f-151">"d:\temp\AuditSearchLog.txt"</span><span class="sxs-lookup"><span data-stu-id="edf7f-151">"d:\temp\AuditSearchLog.txt"</span></span>|<span data-ttu-id="edf7f-p113">De naam en locatie van het logboekbestand met informatie over de voortgang van de zoekopdracht in het auditlogboek die door het script wordt uitgevoerd. Het script schrijft UTC-tijdstempels naar het logbestand.</span><span class="sxs-lookup"><span data-stu-id="edf7f-p113">Specifies the name and location for the log file that contains information about the progress of the audit log search performed by the script. The script writes UTC timestamps to the log file.</span></span>|
   |`$outputFile`|<span data-ttu-id="edf7f-154">"d:\temp\AuditRecords.csv"</span><span class="sxs-lookup"><span data-stu-id="edf7f-154">"d:\temp\AuditRecords.csv"</span></span>|<span data-ttu-id="edf7f-155">Hiermee geeft u de naam en locatie op van het CSV-bestand dat de auditrecords bevat die door het script worden geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="edf7f-155">Specifies the name and location of the CSV file that contains the audit records returned by the script.</span></span>|
   |<span data-ttu-id="edf7f-156">`[DateTime]$start` en `[DateTime]$end`</span><span class="sxs-lookup"><span data-stu-id="edf7f-156">`[DateTime]$start` and `[DateTime]$end`</span></span>|[DateTime]::UtcNow.AddDays(-1) <br/>[DateTime]::UtcNow|<span data-ttu-id="edf7f-159">Hiermee geeft u het datumbereik voor het zoeken in het auditlogboek op.</span><span class="sxs-lookup"><span data-stu-id="edf7f-159">Specifies the date range for the audit log search.</span></span> <span data-ttu-id="edf7f-160">Het script retourneert records voor controleactiviteiten die hebben plaatsgevonden binnen het opgegeven datumbereik.</span><span class="sxs-lookup"><span data-stu-id="edf7f-160">The script will return records for audit activities that occurred within the specified date range.</span></span> <span data-ttu-id="edf7f-161">Als u bijvoorbeeld activiteiten wilt retourneren die zijn uitgevoerd in januari 2021, kunt u een begindatum van `"2021-01-01"` en een einddatum van `"2021-01-31"` gebruiken (plaats de waarden tussen dubbele aanhalingstekens) Met de voorbeeldwaarde in het script worden records als resultaat geven voor activiteiten die in de afgelopen 24 uur zijn uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="edf7f-161">For example, to return activities performed in January 2021, you can use a start date of `"2021-01-01"` and an end date of `"2021-01-31"` (be sure to surround the values in double-quotation marks) The sample value in the script returns records for activities performed in the previous 24 hours.</span></span> <span data-ttu-id="edf7f-162">Als de waarde geen tijdstempel bevat, is de standaardtijdstempel 12:00 uur (middernacht) op de opgegeven datum.</span><span class="sxs-lookup"><span data-stu-id="edf7f-162">If you don't include a timestamp in the value, the default timestamp is 12:00 AM (midnight) on the specified date.</span></span>|
   |`$record`|<span data-ttu-id="edf7f-163">"AzureActiveDirectory"</span><span class="sxs-lookup"><span data-stu-id="edf7f-163">"AzureActiveDirectory"</span></span>|<span data-ttu-id="edf7f-164">Het recordtype van de controleactiviteiten (ook wel controle *bewerkingen* genoemd) die u wilt zoeken.</span><span class="sxs-lookup"><span data-stu-id="edf7f-164">Specifies the record type of the audit activities (also called *operations*) to search for.</span></span> <span data-ttu-id="edf7f-165">Deze eigenschap geeft de service of functie aan waarin een activiteit is geactiveerd.</span><span class="sxs-lookup"><span data-stu-id="edf7f-165">This property indicates the service or feature that an activity was triggered in.</span></span> <span data-ttu-id="edf7f-166">Zie [Het recordtype Auditlogboek](/office/office-365-management-api/office-365-management-activity-api-schema#auditlogrecordtype)voor een lijst met recordtypen die u voor deze variabele kunt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="edf7f-166">For a list of record types that you can use for this variable, see [Audit log record type](/office/office-365-management-api/office-365-management-activity-api-schema#auditlogrecordtype).</span></span> <span data-ttu-id="edf7f-167">U kunt de naam van het recordtype of de ENUM-waarde gebruiken.</span><span class="sxs-lookup"><span data-stu-id="edf7f-167">You can use the record type name or ENUM value.</span></span> <br/><br/><span data-ttu-id="edf7f-168">**Tip:** als u auditrecords voor alle recordtypen wilt retourneren, gebruikt u de waarde `$null` (zonder dubbele aanhalingstekens).</span><span class="sxs-lookup"><span data-stu-id="edf7f-168">**Tip:** To return audit records for all record types, use the value `$null` (without double-quotations marks).</span></span>|
   |`$resultSize`|<span data-ttu-id="edf7f-169">5000</span><span class="sxs-lookup"><span data-stu-id="edf7f-169">5000</span></span>|<span data-ttu-id="edf7f-170">Het aantal resultaten dat telkens wordt geretourneerd als de cmdlet **Search-UnifiedAuditLog** door het script wordt aangeroepen (een *resultatenset*).</span><span class="sxs-lookup"><span data-stu-id="edf7f-170">Specifies the number of results returned each time the **Search-UnifiedAuditLog** cmdlet is called by the script (called a *result set*).</span></span> <span data-ttu-id="edf7f-171">De waarde van 5000 is de maximumwaarde die wordt ondersteund door de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="edf7f-171">The value of 5,000 is the maximum value supported by the cmdlet.</span></span> <span data-ttu-id="edf7f-172">Laat deze waarde ingesteld zonder wijziging.</span><span class="sxs-lookup"><span data-stu-id="edf7f-172">Leave this value as-is.</span></span>|
   |`$intervalMinutes`|<span data-ttu-id="edf7f-173">60</span><span class="sxs-lookup"><span data-stu-id="edf7f-173">60</span></span>|<span data-ttu-id="edf7f-174">Om de limiet van 5000 geretourneerde records te helpen om te komen, neemt deze variabele het gegevensbereik op dat u hebt opgegeven en worden deze in kleinere tijdsintervallen gehouden.</span><span class="sxs-lookup"><span data-stu-id="edf7f-174">To help overcome the limit of 5000 records returned, this variable takes the data range you specified and slices it up into smaller time intervals.</span></span> <span data-ttu-id="edf7f-175">Nu is elk interval, niet het hele datumbereik, onderhevig aan de uitvoerlimiet van 5000 records van de opdracht.</span><span class="sxs-lookup"><span data-stu-id="edf7f-175">Now each interval, not the entire date range, is subject to the 5000 record output limit of the command.</span></span> <span data-ttu-id="edf7f-176">Voor de meeste organisaties moet de standaardwaarde van 5000 records per tijdsinterval van 60 minuten binnen het datumbereik voldoende zijn.</span><span class="sxs-lookup"><span data-stu-id="edf7f-176">The default value of 5000 records per 60-minute interval within the date range should be sufficient for most organizations.</span></span> <span data-ttu-id="edf7f-177">Maar als het script een fout retourneert zoals: `maximum results limitation reached`, verlaag dan het tijdsinterval (bijvoorbeeld tot 30 minuten of zelfs 15 minuten) en voer het script opnieuw uit.</span><span class="sxs-lookup"><span data-stu-id="edf7f-177">But, if the script returns an error that says, `maximum results limitation reached`, decrease the time interval (for example, to 30 minutes or even 15 minutes) and rerun the script.</span></span>|
   ||||

   <span data-ttu-id="edf7f-178">De meeste variabelen in de vorige tabel komen overeen met parameters voor de cmdlet **Search-UnifiedAuditLog**.</span><span class="sxs-lookup"><span data-stu-id="edf7f-178">Most of the variables listed in the previous table correspond to parameters for the **Search-UnifiedAuditLog** cmdlet.</span></span> <span data-ttu-id="edf7f-179">Zie [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog) voor meer informatie over deze parameters.</span><span class="sxs-lookup"><span data-stu-id="edf7f-179">For more information about these parameters, see [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog).</span></span>

3. <span data-ttu-id="edf7f-180">Open Windows PowerShell op uw lokale computer en ga naar de map waarin u het gewijzigde script hebt opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="edf7f-180">On your local computer, open Windows PowerShell and go to the folder where you saved the modified script.</span></span>

4. <span data-ttu-id="edf7f-181">Voer het volgende script uit in Exchange Online PowerShell; bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="edf7f-181">Run the script in Exchange Online PowerShell; for example:</span></span>

   ```powershell
   .\SearchAuditLog.ps1
   ```

<span data-ttu-id="edf7f-182">Tijdens het uitvoeren van het script worden voortgangsberichten weergegeven.</span><span class="sxs-lookup"><span data-stu-id="edf7f-182">The script displays progress messages while it's running.</span></span> <span data-ttu-id="edf7f-183">Nadat het script is uitgevoerd, wordt het logboekbestand en het CSV-bestand met de auditrecords gemaakt en worden deze opgeslagen in de mappen die zijn gedefinieerd door de variabelen `$logFile` en `$outputFile`.</span><span class="sxs-lookup"><span data-stu-id="edf7f-183">After the script is finished running, it creates the log file and the CSV file that contains the audit records and saves them to the folders defined by the `$logFile` and `$outputFile` variables.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="edf7f-184">Er geldt een limiet van 50.000 voor het maximum aantal controlerecords dat telkens wordt geretourneerd wanneer u dit script gebruikt.</span><span class="sxs-lookup"><span data-stu-id="edf7f-184">There is a 50,000 limit for the maximum number of audit records returned each time you run this script.</span></span> <span data-ttu-id="edf7f-185">Als u dit script uitvoeren en 50.000 resultaten retourneert, is de kans groot dat de auditrecords voor activiteiten die binnen het datumbereik hebben plaatsgevonden, niet zijn opgenomen.</span><span class="sxs-lookup"><span data-stu-id="edf7f-185">If you run this script and it returns 50,000 results, then it's likely that audit records for activities that occurred within the date range weren't included.</span></span> <span data-ttu-id="edf7f-186">Als dit gebeurt, is het raadzaam om het datumbereik op te splitsen in kleinere duur en het script vervolgens opnieuw uit te voeren voor elk datumbereik.</span><span class="sxs-lookup"><span data-stu-id="edf7f-186">If this happens, we recommend that you divide the date range into smaller durations and then rerun the script for each date range.</span></span> <span data-ttu-id="edf7f-187">Als een datumbereik van 90 dagen bijvoorbeeld 50.000 resultaten oplevert, kunt u het script tweemaal opnieuw uitvoeren, één keer voor de eerste 45 dagen in het datumbereik en vervolgens weer voor de volgende 45 dagen.</span><span class="sxs-lookup"><span data-stu-id="edf7f-187">For example, if a date range of 90 days returns 50,000 results then you can rerun the script twice, once for the first 45 days in the date range and then again for the next 45 days.</span></span>

## <a name="step-3-format-and-view-the-audit-records"></a><span data-ttu-id="edf7f-188">Stap 3: De auditrecords opmaken en weergeven</span><span class="sxs-lookup"><span data-stu-id="edf7f-188">Step 3: Format and view the audit records</span></span>

<span data-ttu-id="edf7f-189">Nadat u het script hebt uitgevoerd en de auditrecords hebt geëxporteerd naar een CSV-bestand, wilt u het CSV-bestand mogelijk opmaken om de controlerecords eenvoudiger te kunnen controleren en analyseren.</span><span class="sxs-lookup"><span data-stu-id="edf7f-189">After you've run the script and exported the audit records to a CSV file, you may want to format the CSV to make easier to review and analyze the audit records.</span></span> <span data-ttu-id="edf7f-190">Eén manier om dit te doen is met de transformatiefunctie JSON van Power Query in Excel om elke eigenschap in het JSON-object in de kolom **AuditData** te splitsen in een eigen kolom.</span><span class="sxs-lookup"><span data-stu-id="edf7f-190">One way to do this is to the Power Query JSON transform feature in Excel to split each property in the JSON object in the **AuditData** column into its own column.</span></span> <span data-ttu-id="edf7f-191">Zie "Stap 2: de geëxporteerde autditlogboeken opmaken met de Power Query Editor'  voor stapsgewijze instructies in [Auditlogboekrecords exporteren, configureren en bekijken](export-view-audit-log-records.md#step-2-format-the-exported-audit-log-using-the-power-query-editor).</span><span class="sxs-lookup"><span data-stu-id="edf7f-191">For step-by-step instructions, see "Step 2: Format the exported audit log using the Power Query Editor" in [Export, configure, and view audit log records](export-view-audit-log-records.md#step-2-format-the-exported-audit-log-using-the-power-query-editor).</span></span>
