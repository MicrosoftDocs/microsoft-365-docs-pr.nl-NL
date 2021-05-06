---
title: Een rapport maken over inonthoudt in eDiscovery-zaken
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/11/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: cca08d26-6fbf-4b2c-b102-b226e4cd7381
ms.custom:
- seo-marvel-apr2020
description: Meer informatie over het genereren van een rapport met informatie over alle in- en uitstopstops die zijn gekoppeld aan eDiscovery-zaken.
ms.openlocfilehash: 04282f6f2481d892fa16d685936efeec55feae77
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52161885"
---
# <a name="create-a-report-on-holds-in-ediscovery-cases"></a>Een rapport maken over inonthoudt in eDiscovery-zaken

Met het script in dit artikel kunnen eDiscovery-beheerders en eDiscovery-beheerders een rapport genereren dat informatie bevat over alle in- en uitbatingen die zijn gekoppeld aan eDiscovery-gevallen in het compliancecentrum in Office 365 of Microsoft 365. Het rapport bevat informatie, zoals de naam van de zaak aan een wachtplaats, de inhoudslocaties die in de wacht worden gezet en of de wacht op query's is gebaseerd. Als er gevallen zijn die geen gebruiksreportages hebben, wordt in het script een extra rapport gemaakt met een lijst met zaken zonder wacht.

Zie de [sectie Meer informatie](#more-information) voor een gedetailleerde beschrijving van de informatie in het rapport.

## <a name="admin-requirements-and-script-information"></a>Beheerdersvereisten en scriptgegevens

- Als u een rapport wilt genereren over alle eDiscovery-zaken in uw organisatie, moet u een eDiscovery-beheerder in uw organisatie zijn. Als u een eDiscovery Manager bent, bevat het rapport alleen informatie over de zaken die u kunt openen. Zie eDiscovery-machtigingen toewijzen voor meer informatie over [eDiscovery-machtigingen.](assign-ediscovery-permissions.md)

- Het script in dit artikel heeft minimale foutafhandeling. Het primaire doel is om snel rapport te maken over de inhoudt die zijn gekoppeld aan de eDiscovery-zaken in uw organisatie.

- De voorbeeldscripts in dit onderwerp worden niet ondersteund onder een standaardondersteuningsprogramma of -service van Microsoft. De voorbeeldscripts worden geleverd als IS zonder enige garantie. Microsoft wijst alle impliciete garanties verder af, inclusief, zonder beperking, impliciete garanties van verkoopbaarheid of geschiktheid voor een bepaald doel. Het volledige risico dat voortvloeit uit het gebruik of de prestaties van de voorbeeldscripts en documentatie blijft bij u. In geen geval zijn Microsoft, de auteurs of anderen die betrokken zijn bij het maken, produceren of leveren van de scripts aansprakelijk voor enige schade (met inbegrip van, zonder beperking, schade voor verlies van bedrijfswinsten, bedrijfsonderbreking, verlies van bedrijfsgegevens of ander geldverlies) als gevolg van het gebruik van of het onvermogen om de voorbeeldscripts of documentatie te gebruiken, zelfs als Microsoft op de hoogte is gesteld van de mogelijkheid van dergelijke schade.

## <a name="step-1-connect-to-the-security--compliance-center-powershell"></a>Stap 1: Verbinding maken naar het beveiligingscentrum & Compliance center PowerShell

De eerste stap is om verbinding te maken met Security & Compliance Center PowerShell voor uw organisatie. Zie voor stapsgewijs instructies Verbinding maken [Beveiligingscentrum & PowerShell](/powershell/exchange/connect-to-scc-powershell).

## <a name="step-2-run-the-script-to-report-on-holds-associated-with-ediscovery-cases"></a>Stap 2: Voer het script uit om te rapporteren over in- en uit te voeren die zijn gekoppeld aan eDiscovery-zaken

Nadat u verbinding hebt gemaakt met Security & Compliance Center PowerShell, is de volgende stap het maken en uitvoeren van het script dat informatie verzamelt over de eDiscovery-gevallen in uw organisatie.

1. Sla de volgende tekst op in een Windows PowerShell scriptbestand met behulp van een achtervoegsel voor bestandsnaam van .ps1; bijvoorbeeld CaseHoldsReport.ps1.

   ```powershell
   #script begin
   " "
   write-host "***********************************************"
   write-host "   Security & Compliance Center   " -foregroundColor yellow -backgroundcolor darkgreen
   write-host "        eDiscovery cases - Holds report         " -foregroundColor yellow -backgroundcolor darkgreen
   write-host "***********************************************"
   " "
   #prompt users to specify a path to store the output files
   $time=get-date
   $Path = Read-Host 'Enter a file path to save the report to a .csv file'
   $outputpath=$Path+'\'+'CaseHoldsReport'+' '+$time.day+'-'+$time.month+'-'+$time.year+' '+$time.hour+'.'+$time.minute+'.csv'
   $noholdsfilepath=$Path+'\'+'CaseswithNoHolds'+' '+$time.day+'-'+$time.month+'-'+$time.year+' '+$time.hour+'.'+$time.minute+'.csv'
   #add case details to the csv file
   function add-tocasereport{
   Param([string]$casename,
   [String]$casestatus,
   [datetime]$casecreatedtime,
   [string]$casemembers,
   [datetime]$caseClosedDateTime,
   [string]$caseclosedby,
   [string]$holdname,
   [String]$Holdenabled,
   [string]$holdcreatedby,
   [string]$holdlastmodifiedby,
   [string]$ExchangeLocation,
   [string]$sharePointlocation,
   [string]$ContentMatchQuery,
   [datetime]$holdcreatedtime,
   [datetime]$holdchangedtime
   )
   $addRow = New-Object PSObject
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case name" -Value $casename
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case status" -Value $casestatus
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case members" -Value $casemembers
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case created time" -Value $casecreatedtime
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case closed time" -Value $caseClosedDateTime
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case closed by" -Value $caseclosedby
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold name" -Value $holdname
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold enabled" -Value $Holdenabled
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold created by" -Value $holdcreatedby
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold last changed by" -Value $holdlastmodifiedby
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Exchange locations" -Value  $ExchangeLocation
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "SharePoint locations" -Value $sharePointlocation
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold query" -Value $ContentMatchQuery
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold created time (UTC)" -Value $holdcreatedtime
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold changed time (UTC)" -Value $holdchangedtime
   $allholdreport = $addRow | Select-Object "Case name","Case status","Hold name","Hold enabled","Case members", "Case created time","Case closed time","Case closed by","Exchange locations","SharePoint locations","Hold query","Hold created by","Hold created time (UTC)","Hold last changed by","Hold changed time (UTC)"
   $allholdreport | export-csv -path $outputPath -notypeinfo -append -Encoding ascii
   }
   #get information on the cases and pass values to the case report function
   " "
   write-host "Gathering a list of cases and holds..."
   " "
   $edc =Get-ComplianceCase -ErrorAction SilentlyContinue
   foreach($cc in $edc)
   {
   write-host "Working on case :" $cc.name
   if($cc.status -eq 'Closed')
   {
   $cmembers = ((Get-ComplianceCaseMember -Case $cc.name).windowsLiveID)-join ';'
   add-tocasereport -casename $cc.name -casestatus $cc.Status -caseclosedby $cc.closedby -caseClosedDateTime $cc.ClosedDateTime -casemembers $cmembers
   }
   else{
   $cmembers = ((Get-ComplianceCaseMember -Case $cc.name).windowsLiveID)-join ';'
   $policies = Get-CaseHoldPolicy -Case $cc.Name | %{ Get-CaseHoldPolicy $_.Name -Case $_.CaseId -DistributionDetail}
   if ($policies -ne $NULL)
   {
   foreach ($policy in $policies)
   {
   $rule=Get-CaseHoldRule -Policy $policy.name
   add-tocasereport -casename $cc.name -casemembers $cmembers -casestatus $cc.Status -casecreatedtime $cc.CreatedDateTime -holdname $policy.name -holdenabled $policy.enabled -holdcreatedby $policy.CreatedBy -holdlastmodifiedby $policy.LastModifiedBy -ExchangeLocation (($policy.exchangelocation.name)-join ';') -SharePointLocation (($policy.sharePointlocation.name)-join ';') -ContentMatchQuery $rule.ContentMatchQuery -holdcreatedtime $policy.WhenCreatedUTC -holdchangedtime $policy.WhenChangedUTC
   }
   }
   else{
   write-host "No hold policies found in case:" $cc.name -foregroundColor 'Yellow'
   " "
   [string]$cc.name | out-file -filepath $noholdsfilepath -append
   }
   }
   }

   " "
   Write-host "Script complete! Report files saved to this folder: '$Path'"
   " "
   #script end
   ```

2. Ga in Windows PowerShell sessie die is geopend in stap 1 naar de map waar u het script hebt opgeslagen.

3. Voer het script uit; bijvoorbeeld:

   ```powershell
   .\CaseHoldsReport.ps1
   ```

   Het script vraagt om een doelmap om het rapport op te slaan.

4. Typ de volledige padnaam van de map waarin u het rapport wilt opslaan en druk vervolgens op **Enter.**

   > [!TIP]
   > Als u het rapport wilt opslaan in dezelfde map waarin het script zich bevindt, typt u een punt (".") wanneer u wordt gevraagd om een doelmap. Als u het rapport wilt opslaan in een submap in de map waar het script zich bevindt, typt u de naam van de submap.

   Het script begint met het verzamelen van informatie over alle eDiscovery-gevallen in uw organisatie. Krijg geen toegang tot het rapportbestand terwijl het script wordt uitgevoerd. Nadat het script is voltooid, wordt er een bevestigingsbericht weergegeven in de Windows PowerShell sessie. Nadat dit bericht is weergegeven, hebt u toegang tot het rapport in de map die u hebt opgegeven in stap 4. De bestandsnaam voor het rapport is `CaseHoldsReport<DateTimeStamp>.csv` .

   Bovendien wordt met het script ook een rapport gemaakt met een lijst met zaken die niet in gebruik zijn. De bestandsnaam voor dit rapport is `CaseswithNoHolds<DateTimeStamp>.csv` .

   Hier is een voorbeeld van het uitvoeren van het CaseHoldsReport.ps1 script.

   ![De uitvoer na het uitvoeren van CaseHoldsReport.ps1 script](../media/7d312ed5-505e-4ec5-8f06-3571e3524a1a.png)

## <a name="more-information"></a>Meer informatie

De zaak bevat rapport dat is gemaakt wanneer u het script in dit artikel uit te voeren, bevat de volgende informatie over elke wacht. Zoals eerder is uitgelegd, moet u een eDiscovery-beheerder zijn om informatie te retourneren voor alle in uw organisatie op te vragen. Zie [eDiscovery-zaken](./get-started-core-ediscovery.md)voor meer informatie over case holds.

- De naam van de wacht en de naam van de eDiscovery-zaak waar de wacht aan is gekoppeld.

- Ongeacht of de eDiscovery-zaak actief of gesloten is.

- Ongeacht of de wacht in- of uitgeschakeld is.

- De leden van de eDiscovery-zaak waar de wacht aan is gekoppeld. Caseleden kunnen een zaak bekijken of beheren, afhankelijk van de eDiscovery-machtigingen die aan hen zijn toegewezen.

- De tijd en datum waarop de zaak is gemaakt.

- Als een zaak is gesloten, de persoon die het heeft gesloten en de tijd en datum waarop het is gesloten.

- De Exchange postvakken en SharePoint sites die in de wacht staan.

- Als de wacht op query's is gebaseerd, wordt de syntaxis van de query gebruikt.

- De tijd en datum waarop de wacht wordt gehouden en de persoon die deze heeft gemaakt.

- De tijd en datum waarop de wacht voor het laatst is gewijzigd en de persoon die deze heeft gewijzigd.