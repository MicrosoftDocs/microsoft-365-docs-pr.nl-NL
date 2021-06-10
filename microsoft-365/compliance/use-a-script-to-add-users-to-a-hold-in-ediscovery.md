---
title: Een script gebruiken om gebruikers toe te voegen aan een wacht in een Hoofd-eDiscovery-zaak
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.collection:
- SPO_Content
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: bad352ff-d5d2-45d8-ac2a-6cb832f10e73
ms.custom: seo-marvel-apr2020
description: Lees hoe u een script kunt uitvoeren om postvakken & OneDrive voor Bedrijven sites toe te voegen aan een nieuwe wachtplaats die is gekoppeld aan een eDiscovery-zaak in het Microsoft 365 compliancecentrum.
ms.openlocfilehash: d6e6ff1ca053fd8c729054490e78ef42dc64e829
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52161890"
---
# <a name="use-a-script-to-add-users-to-a-hold-in-a-core-ediscovery-case"></a>Een script gebruiken om gebruikers toe te voegen aan een wacht in een Hoofd-eDiscovery-zaak

Beveiligings & Compliance center PowerShell biedt cmdlets om tijdrovende taken met betrekking tot het maken en beheren van eDiscovery-zaken te automatiseren. Het gebruik van de core eDiscovery-zaak in het beveiligings- & compliancecentrum om een groot aantal bewaarlocaties voor inhoud in de wacht te zetten, kost tijd en voorbereiding. Voordat u bijvoorbeeld een hold maakt, moet u de URL verzamelen voor elke OneDrive voor Bedrijven site die u in de wacht wilt zetten. Vervolgens moet u voor elke gebruiker die u in de wacht wilt zetten, zijn of haar postvak en OneDrive voor Bedrijven aan de wachtplaats toevoegen. U kunt het script in dit artikel gebruiken om dit proces te automatiseren.
  
In het script wordt u gevraagd om de naam van het domein Mijn site van uw organisatie (bijvoorbeeld in de URL, de naam van een bestaand `contoso` eDiscovery-geval, de naam van de nieuwe wachtplaats die is gekoppeld aan de zaak, een lijst met e-mailadressen van de gebruikers die u wilt in de wacht zetten en een zoekquery die u wilt gebruiken als u een query-hold wilt https://contoso-my.sharepoint.com) maken. Het script krijgt vervolgens de URL voor de OneDrive voor Bedrijven-site voor elke gebruiker in de lijst, maakt de nieuwe wacht en voegt vervolgens het postvak en de OneDrive voor Bedrijven-site voor elke gebruiker in de lijst toe aan de wacht. Het script genereert ook logboekbestanden die informatie over de nieuwe wacht houden bevatten.
  
Hier volgen de stappen om dit te doen:
  
[Stap 1: De SharePoint Online Management Shell installeren](#step-1-install-the-sharepoint-online-management-shell)
  
[Stap 2: Een lijst met gebruikers genereren](#step-2-generate-a-list-of-users)
  
[Stap 3: Het script uitvoeren om een wacht te maken en gebruikers toe te voegen](#step-3-run-the-script-to-create-a-hold-and-add-users)
  
## <a name="before-you-add-users-to-a-hold"></a>Voordat u gebruikers toevoegt aan een wacht

- U moet lid zijn van de rollengroep eDiscovery Manager in het beveiligings- & compliancecentrum en een SharePoint Online-beheerder om het script uit te voeren in stap 3. Zie [eDiscovery-machtigingen toewijzen in het Office 365 Beveiligingscentrum & compliancecentrum voor meer informatie.](assign-ediscovery-permissions.md)

- Er kunnen maximaal 1.000 postvakken en 100 sites worden toegevoegd aan een wachtplaats die is gekoppeld aan een eDiscovery-zaak in het beveiligings- & compliancecentrum. Ervan uitgaande dat elke gebruiker die u in de wacht wilt zetten een OneDrive voor Bedrijven site heeft, kunt u maximaal 100 gebruikers aan een wacht houden met behulp van het script in dit artikel.

- Zorg ervoor dat u de lijst met gebruikers die u maakt in stap 2 en het script in stap 3 in dezelfde map opgeslagen. Dit maakt het eenvoudiger om het script uit te voeren.

- Met het script wordt de lijst met gebruikers toegevoegd aan een nieuwe wacht die is gekoppeld aan een bestaand geval. Zorg ervoor dat de zaak aan wie u de wacht wilt koppelen, is gemaakt voordat u het script uitwerkt.

- Het script in dit artikel ondersteunt moderne verificatie wanneer u verbinding maakt met & Compliance Center PowerShell en SharePoint Online Management Shell. U kunt het script gewoon gebruiken als u een Microsoft 365 of een Microsoft 365 GCC organisatie. Als u een organisatie Office 365 Duitsland, een Microsoft 365 GCC Hoge organisatie of een Microsoft 365 DoD-organisatie bent, moet u het script bewerken om het uit te voeren. U moet de regel bewerken en de `Connect-IPPSSession` parameters *ConnectionUri* en *AzureADAuthorizationEndpointUri* (en de juiste waarden voor uw organisatietype) gebruiken om verbinding te maken met Security & Compliance Center PowerShell. Zie de voorbeelden in Verbinding maken security [& Compliance Center PowerShell voor meer informatie.](/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa)

- Het script wordt automatisch losgekoppeld van Security & Compliance Center PowerShell en SharePoint Online Management Shell.

- Het script bevat minimale foutafhandeling. Het primaire doel is om het postvak en de OneDrive voor Bedrijven van elke gebruiker snel en eenvoudig in de wacht te zetten.

- De voorbeeldscripts in dit onderwerp worden niet ondersteund onder een standaardondersteuningsprogramma of -service van Microsoft. De voorbeeldscripts worden zonder enige garantie ONGEWIJZIGD verstrekt. Microsoft wijst alle impliciete garanties met inbegrip van, maar niet beperkt tot, impliciete garanties van verkoopbaarheid en geschiktheid voor een bepaald doel af. Het risico dat ontstaat als gevolg van het gebruik of prestaties van de voorbeeldscripts ligt geheel bij u. In geen geval kan Microsoft, haar auteurs of anderen die bij het maken, produceren of leveren van de scripts zijn betrokken, aansprakelijk worden gehouden voor enige schade om welke reden dan ook (met inbegrip van maar niet beperkt tot schade door verlies van bedrijfswinsten, belemmering van de bedrijfsuitvoering, verlies van bedrijfsinformatie of andere geldelijke verliezen) voortvloeiend uit het gebruik of de onmogelijkheid van het gebruik van de voorbeeldscripts, zelfs als Microsoft op de hoogte is gesteld van de mogelijkheid van dergelijke schade.

## <a name="step-1-install-the-sharepoint-online-management-shell"></a>Stap 1: De SharePoint Online Management Shell installeren

De eerste stap is om de SharePoint Online Management Shell te installeren als deze nog niet op uw lokale computer is geïnstalleerd. U hoeft de shell niet te gebruiken in deze procedure, maar u moet deze installeren omdat deze vereisten bevat die vereist zijn voor het script dat u in stap 3 uit te voeren. Met deze vereisten kan het script communiceren met SharePoint Online om de URL's voor de OneDrive voor Bedrijven krijgen.
  
Ga naar De SharePoint [Online Management Shell Windows PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) en voer stap 1 en stap 2 uit om de SharePoint Online Management Shell op uw lokale computer te installeren.

## <a name="step-2-generate-a-list-of-users"></a>Stap 2: Een lijst met gebruikers genereren

Met het script in stap 3 wordt een wachtlijst gemaakt die is gekoppeld aan een eDiscovery-zaak en worden de postvakken en OneDrive voor Bedrijven sites van een lijst met gebruikers aan de wacht gezet. U kunt alleen de e-mailadressen in een tekstbestand typen of u kunt een opdracht uitvoeren in Windows PowerShell om een lijst met e-mailadressen op te halen en deze op te slaan in een bestand (in dezelfde map waarin u het script in stap 3 op wilt slaan).
  
Hier ziet u een PowerShell-opdracht (die u kunt uitvoeren met externe PowerShell die is verbonden met uw Exchange Online-organisatie) om een lijst met e-mailadressen op te halen voor alle gebruikers in uw organisatie en deze op te slaan in een tekstbestand met de naam HoldUsers.txt.
  
```powershell
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > HoldUsers.txt
```

Nadat u deze opdracht hebt uitgevoerd, opent u het tekstbestand en verwijdert u de koptekst met de naam van de  `PrimarySmtpAddress` eigenschap. Verwijder vervolgens alle e-mailadressen, behalve de e-mailadressen voor de gebruikers die u wilt toevoegen aan de wacht die u in stap 3 maakt. Zorg ervoor dat er geen lege rijen zijn voor of na de lijst met e-mailadressen.
  
## <a name="step-3-run-the-script-to-create-a-hold-and-add-users"></a>Stap 3: Het script uitvoeren om een wacht te maken en gebruikers toe te voegen

Wanneer u het script in deze stap uit te voeren, wordt u gevraagd om de volgende informatie. Zorg ervoor dat u deze informatie klaar hebt voordat u het script gaat uitvoeren.
  
- **Uw gebruikersreferenties:** Het script gebruikt uw referenties om verbinding te maken met & Compliancecentrum met PowerShell. Deze referenties worden ook gebruikt om toegang te krijgen tot SharePoint Online om de OneDrive voor Bedrijven url's voor de lijst met gebruikers te krijgen.

- **Naam van uw SharePoint domein:** In het script wordt u gevraagd deze naam in te voeren, zodat deze verbinding kan maken met het SharePoint beheercentrum. De domeinnaam wordt ook gebruikt voor de OneDrive URL's in uw organisatie. Als bijvoorbeeld de URL voor uw beheercentrum is en de URL voor OneDrive is, voert u deze in wanneer het script u om uw domeinnaam `https://contoso-admin.sharepoint.com` `https://contoso-my.sharepoint.com` `contoso` vraagt.

- **Naam van de zaak:** De naam van een bestaand geval. Het script maakt een nieuwe wacht die aan deze zaak is gekoppeld.

- **Naam van de wacht:** De naam van de wacht houden van het script wordt gemaakt en aan het opgegeven geval koppelen.

- **Zoekquery voor een op query's gebaseerde wachtfunctie:** U kunt een op query's gebaseerde wachtplaats maken, zodat alleen de inhoud die voldoet aan de opgegeven zoekcriteria, in de wacht wordt geplaatst. Als u alle inhoud in de wacht wilt zetten, drukt u **op Enter** wanneer u wordt gevraagd om een zoekquery.

- **De wacht in- of uitschakelen:** U kunt het script inschakelen nadat het is gemaakt of u kunt het script de wacht laten zetten zonder dit in te stellen. Als u het script niet in de wacht hebt gezet, kunt u het later in het Beveiligings- & Compliancecentrum in- of door de volgende PowerShell-opdrachten uit te voeren:

  ```powershell
  Set-CaseHoldPolicy -Identity <name of the hold> -Enabled $true
  ```

  ```powershell
  Set-CaseHoldRule -Identity <name of the hold> -Disabled $false
  ```

- **Naam van het tekstbestand met** de lijst met gebruikers: de naam van het tekstbestand uit stap 2 met de lijst met gebruikers die u wilt toevoegen aan de wacht. Als dit bestand zich in dezelfde map bevindt als het script, typt u de naam van het bestand (bijvoorbeeld HoldUsers.txt). Als het tekstbestand zich in een andere map, typt u de volledige padnaam van het bestand.

Nadat u de informatie hebt verzameld waar u om wordt gevraagd door het script, is de laatste stap het uitvoeren van het script om de nieuwe wachtstand te maken en er gebruikers aan toe te voegen.
  
1. Sla de volgende tekst op in een Windows PowerShell scriptbestand met behulp van een achtervoegsel van de bestandsnaam `.ps1` . Bijvoorbeeld `AddUsersToHold.ps1`.

```powershell
#script begin
" "
write-host "***********************************************"
write-host "   Security & Compliance Center PowerShell  " -foregroundColor yellow -backgroundcolor darkgreen
write-host "   Core eDiscovery cases - Add users to a hold   " -foregroundColor yellow -backgroundcolor darkgreen 
write-host "***********************************************"
" "
# Connect to SCC PowerShell using modern authentication
if (!$SccSession)
{
  Import-Module ExchangeOnlineManagement
  Connect-IPPSSession
}

# Get the organization's domain name. We use this to create the SharePoint admin URL and root URL for OneDrive for Business.
""
$mySiteDomain = Read-Host "Enter the domain name for your SharePoint organization. We use this name to connect to SharePoint admin center and for the OneDrive URLs in your organization. For example, 'contoso' in 'https://contoso-admin.sharepoint.com' and 'https://contoso-my.sharepoint.com'"
""

# Connect to PnP Online using modern authentication
Import-Module PnP.PowerShell
Connect-PnPOnline -Url https://$mySiteDomain-admin.sharepoint.com -UseWebLogin

# Load the SharePoint assemblies from the SharePoint Online Management Shell
# To install, go to https://go.microsoft.com/fwlink/p/?LinkId=255251
if (!$SharePointClient -or !$SPRuntime -or !$SPUserProfile)
{
    $SharePointClient = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client")
    $SPRuntime = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.Runtime")
    $SPUserProfile = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.UserProfiles")
    if (!$SharePointClient)
    {
        Write-Error "The SharePoint Online Management Shell isn't installed. Please install it from: https://go.microsoft.com/fwlink/p/?LinkId=255251 and then re-run this script."
        return;
    }
}

# Get other required information
do{
$casename = Read-Host "Enter the name of the case"
$caseexists = (get-compliancecase -identity "$casename" -erroraction SilentlyContinue).isvalid
if($caseexists -ne 'True')
{""
write-host "A case named '$casename' doesn't exist. Please specify the name of an existing case, or create a new case and then re-run the script." -foregroundColor Yellow
""}
}While($caseexists -ne 'True')
""
do{
$holdName = Read-Host "Enter the name of the new hold"
$holdexists=(get-caseholdpolicy -identity "$holdname" -case "$casename" -erroraction SilentlyContinue).isvalid
if($holdexists -eq 'True')
{""
write-host "A hold named '$holdname' already exists. Please specify a new hold name." -foregroundColor Yellow
""}
}While($holdexists -eq 'True')
""
$holdQuery = Read-Host "Enter a search query to create a query-based hold, or press Enter to hold all content"
""
$holdstatus = read-host "Do you want the hold enabled after it's created? (Yes/No)"
do{
""
$inputfile = read-host "Enter the name of the text file that contains the email addresses of the users to add to the hold"
""
$fileexists = test-path -path $inputfile
if($fileexists -ne 'True'){write-host "$inputfile doesn't exist. Please enter a valid file name." -foregroundcolor Yellow}
}while($fileexists -ne 'True')
#Import the list of addresses from the txt file.  Trim any excess spaces and make sure all addresses 
    #in the list are unique.
  [array]$emailAddresses = Get-Content $inputfile -ErrorAction SilentlyContinue | where {$_.trim() -ne ""}  | foreach{ $_.Trim() }
  [int]$dupl = $emailAddresses.count
  [array]$emailAddresses = $emailAddresses | select-object -unique
  $dupl -= $emailAddresses.count
#Validate email addresses so the hold creation does not run in to an error.
if($emailaddresses.count -gt 0){
write-host ($emailAddresses).count "addresses were found in the text file. There were $dupl duplicate entries in the file." -foregroundColor Yellow
""
Write-host "Validating the email addresses. Please wait..." -foregroundColor Yellow
""
$finallist =@()
foreach($emailAddress in $emailAddresses)
{
if((get-recipient $emailaddress -erroraction SilentlyContinue).isvalid -eq 'True')
{$finallist += $emailaddress}
else {"Unable to find the user $emailaddress"
[array]$excludedlist += $emailaddress}
}
""
#Find user's OneDrive account URL using email address
Write-Host "Getting the URL for each user's OneDrive for Business site." -foregroundColor Yellow 
""
$AdminUrl = "https://$mySiteDomain-admin.sharepoint.com"
$mySiteUrlRoot = "https://$mySiteDomain-my.sharepoint.com"
$urls = @()
foreach($emailAddress in $emailAddresses)
{
try
{
$url=Get-PnPUserProfileProperty -Account $emailAddress | Select PersonalUrl
$urls += $url.PersonalUrl
       Write-Host "- $emailAddress => $url"
       [array]$ODadded += $url.PersonalUrl
       }catch { 
 Write-Warning "Could not locate OneDrive for $emailAddress"
 [array]$ODExluded += $emailAddress
 Continue }
}
$urls | FL
if(($finallist.count -gt 0) -or ($urls.count -gt 0)){
""
Write-Host "Creating the hold named $holdname. Please wait..." -foregroundColor Yellow
if(($holdstatus -eq "Y") -or ($holdstatus -eq  "y") -or ($holdstatus -eq "yes") -or ($holdstatus -eq "YES")){
New-CaseHoldPolicy -Name "$holdName" -Case "$casename" -ExchangeLocation $finallist -SharePointLocation $urls -Enabled $True | out-null
New-CaseHoldRule -Name "$holdName" -Policy "$holdname" -ContentMatchQuery $holdQuery | out-null
}
else{
New-CaseHoldPolicy -Name "$holdName" -Case "$casename" -ExchangeLocation $finallist -SharePointLocation $urls -Enabled $false | out-null
New-CaseHoldRule -Name "$holdName" -Policy "$holdname" -ContentMatchQuery $holdQuery -disabled $true | out-null
}
""
}
else {"No valid locations were identified. Therefore, the hold wasn't created."}
#write log files (if needed)
$newhold=Get-CaseHoldPolicy -Identity "$holdname" -Case "$casename" -erroraction SilentlyContinue
$newholdrule=Get-CaseHoldRule -Identity "$holdName" -erroraction SilentlyContinue
if(($ODAdded.count -gt 0) -or ($ODExluded.count -gt 0) -or ($finallist.count -gt 0) -or ($excludedlist.count -gt 0) -or ($newhold.isvalid -eq 'True') -or ($newholdrule.isvalid -eq 'True'))
{
Write-Host "Generating output files..." -foregroundColor Yellow
if($ODAdded.count -gt 0){
"OneDrive Locations" | add-content .\LocationsOnHold.txt
"==================" | add-content .\LocationsOnHold.txt 
$newhold.SharePointLocation.name | add-content .\LocationsOnHold.txt}
if($ODExluded.count -gt 0){ 
"Users without OneDrive locations" | add-content .\LocationsNotOnHold.txt
"================================" | add-content .\LocationsNotOnHold.txt
$ODExluded | add-content .\LocationsNotOnHold.txt}
if($finallist.count -gt 0){
" " | add-content .\LocationsOnHold.txt
"Exchange Locations" | add-content .\LocationsOnHold.txt
"==================" | add-content .\LocationsOnHold.txt 
$newhold.ExchangeLocation.name | add-content .\LocationsOnHold.txt}
if($excludedlist.count -gt 0){
" "| add-content .\LocationsNotOnHold.txt
"Mailboxes not added to the hold" | add-content .\LocationsNotOnHold.txt
"===============================" | add-content .\LocationsNotOnHold.txt
$excludedlist | add-content .\LocationsNotOnHold.txt}
$FormatEnumerationLimit=-1
if($newhold.isvalid -eq 'True'){$newhold|fl >.\GetCaseHoldPolicy.txt}
if($newholdrule.isvalid -eq 'True'){$newholdrule|Fl >.\GetCaseHoldRule.txt}
}
}
else {"The hold wasn't created because no valid entries were found in the text file."}
""
#Disconnect from SCC PowerShell and PnPOnline

Write-host "Disconnecting from SCC PowerShell and PnP Online" -foregroundColor Yellow
Get-PSSession | Remove-PSSession
Disconnect-PnPOnline

Write-host "Script complete!" -foregroundColor Yellow
""
#script end
```

2. Open op uw lokale computer Windows PowerShell en ga naar de map waar u het script hebt opgeslagen.

3. Voer het script uit; bijvoorbeeld:

   ```powershell
   .\AddUsersToHold.ps1
   ```

4. Voer de informatie in waar u om wordt gevraagd in het script.

   Het script maakt verbinding met Security & Compliance Center PowerShell en maakt vervolgens de nieuwe wacht in de eDiscovery-zaak en voegt de postvakken en OneDrive voor Bedrijven toe voor de gebruikers in de lijst. U kunt naar de zaak op de **eDiscovery-pagina** in het beveiligings- & compliancecentrum gaan om de nieuwe wacht te bekijken.

Nadat het script is uitgevoerd, worden de volgende logboekbestanden gemaakt en worden deze opgeslagen in de map waar het script zich bevindt.
  
- **LocationsOnHold.txt:** Bevat een lijst met postvakken en OneDrive voor Bedrijven sites die het script in de wacht heeft gezet.

- **LocationsNotOnHold.txt:** Bevat een lijst met postvakken en OneDrive voor Bedrijven sites die het script niet in de wacht heeft geplaatst. Als een gebruiker een postvak heeft, maar geen OneDrive voor Bedrijven site, wordt de gebruiker opgenomen in de lijst met OneDrive voor Bedrijven sites die niet in de wacht zijn geplaatst.

- **GetCaseHoldPolicy.txt:** Bevat de uitvoer van de **Get-CaseHoldPolicy-cmdlet** voor de nieuwe wacht, die het script heeft uitgevoerd na het maken van de nieuwe hold. De gegevens die door deze cmdlet worden geretourneerd, bevatten een lijst met gebruikers van wie de postvakken en OneDrive voor Bedrijven in de wacht zijn geplaatst en of de wacht in- of uitgeschakeld is. 

- **GetCaseHoldRule.txt:** Bevat de uitvoer van de **Get-CaseHoldRule-cmdlet** voor de nieuwe wacht, die het script heeft uitgevoerd na het maken van de nieuwe wacht. De informatie die door deze cmdlet wordt geretourneerd, bevat de zoekquery als u het script hebt gebruikt om een op query gebaseerde greep te maken.