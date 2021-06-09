---
title: Onlinesites SharePoint en gebruikers toevoegen met PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
- SPO_Content
- seo-marvel-apr2020
ms.assetid: d0d3877a-831f-4744-96b0-d8167f06cca2
description: 'Overzicht: Gebruik PowerShell om nieuwe SharePoint onlinesites te maken en vervolgens gebruikers en groepen aan deze sites toe te voegen.'
ms.openlocfilehash: eb6c2817c8760ca222da8a7c2b14cbfcda4eb4b8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907616"
---
# <a name="create-sharepoint-online-sites-and-add-users-with-powershell"></a>Onlinesites SharePoint en gebruikers toevoegen met PowerShell

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Wanneer u PowerShell voor Microsoft 365 gebruikt om SharePoint Online-sites te maken en gebruikers toe te voegen, kunt u snel en herhaaldelijk taken veel sneller uitvoeren dan in het Microsoft 365 beheercentrum. U kunt ook taken uitvoeren die niet kunnen worden uitgevoerd in het Microsoft 365 beheercentrum. 

## <a name="connect-to-sharepoint-online"></a>Verbinding maken online SharePoint online

Voor de procedures in dit onderwerp moet u verbinding maken met SharePoint Online. Zie Verbinding maken [SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) voor instructies

## <a name="step-1-create-new-site-collections-using-powershell"></a>Stap 1: Nieuwe siteverzamelingen maken met PowerShell

Maak meerdere sites met PowerShell en een .csv bestand dat u maakt met behulp van de opgegeven voorbeeldcode en Kladblok. Voor deze procedure vervangt u de tijdelijke aanduidingen tussen haakjes door uw eigen site- en tenantspecifieke informatie. Met dit proces kunt u één bestand maken en één PowerShell-opdracht uitvoeren waarin dat bestand wordt gebruikt. Hierdoor kunnen de acties die worden ondernomen, zowel herhaalbaar als overdraagbaar zijn en worden veel, zo niet alle, fouten weggewerkt die kunnen ontstaan door lange opdrachten te typen in de SharePoint Online Management Shell. Deze procedure bestaat uit twee onderdelen. Eerst maakt u een .csv bestand en vervolgens verwijst u naar dat .csv-bestand met PowerShell, waarmee de inhoud ervan wordt gebruikt om de sites te maken.

De PowerShell-cmdlet importeert het .csv-bestand en voert deze naar een lus in de gekrulde haken die de eerste regel van het bestand als kolomkoppen leest. De PowerShell-cmdlet itereert vervolgens door de resterende records, maakt een nieuwe siteverzameling voor elke record en wijst eigenschappen van de siteverzameling toe op basis van de kolomkoppen.

### <a name="create-a-csv-file"></a>Een .csv maken

> [!NOTE]
> De resourcequotaparameter werkt alleen op klassieke sites. Als u deze parameter op een moderne site gebruikt, ontvangt u mogelijk een waarschuwing dat deze is afgeschaft. 

1. Open Kladblok en plak het volgende tekstblok er in:<br/>

```powershell
Owner,StorageQuota,Url,ResourceQuota,Template,TimeZoneID,Name
owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/TeamSite01,25,EHS#1,10,Contoso Team Site
owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/Blog01,25,BLOG#0,10,Contoso Blog
owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Project01,25,PROJECTSITE#0,10,Project Alpha
owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Community01,25,COMMUNITY#0,10,Community Site
```
<br/>Waarbij *tenant* de naam van uw tenant *is* en de eigenaar de gebruikersnaam is van de gebruiker op uw tenant aan wie u de rol van primaire beheerder van de siteverzameling wilt verlenen.<br/>(U kunt op Ctrl+H drukken wanneer u de Kladblok gebruikt om sneller bulksgewijs te vervangen.)<br/>

2. Sla het bestand op uw bureaublad op **alsSiteCollections.csv.**<br/>

> [!TIP]
> Voordat u dit of een ander .csv of Windows PowerShell scriptbestand gebruikt, is het een goede gewoonte om ervoor te zorgen dat er geen overbodige of niet-afdrukbare tekens zijn. Open het bestand in Word en klik op het lint op het alineapictogram om niet-afdrukbare tekens weer te geven. Er mogen geen overbodige niet-afdrukbare tekens zijn. Er mogen bijvoorbeeld geen alineamarkeringen achter de laatste alineamarkeringen aan het einde van het bestand staan.

### <a name="run-the-windows-powershell-command"></a>De opdracht Windows PowerShell uitvoeren

1. Typ Windows PowerShell en plak de volgende opdracht en druk op Enter:<br/>
```powershell
Import-Csv C:\users\MyAlias\desktop\SiteCollections.csv | ForEach-Object {New-SPOSite -Owner $_.Owner -StorageQuota $_.StorageQuota -Url $_.Url -NoWait -ResourceQuota $_.ResourceQuota -Template $_.Template -TimeZoneID $_.TimeZoneID -Title $_.Name}
```
<br/>Waarbij *MyAlias* gelijk is aan uw gebruikersalias.<br/>

2. Wacht totdat de Windows PowerShell wordt opnieuw verschijnt. Het kan een paar minuten duren.<br/>

3. Typ Windows PowerShell of kopieer en plak de volgende cmdlet en druk op Enter:<br/>

```powershell
Get-SPOSite -Detailed | Format-Table -AutoSize
```
<br/>

4. Let op de nieuwe siteverzamelingen in de lijst. Als u ons voorbeeld CSV-bestand gebruikt, ziet u de volgende siteverzamelingen: **TeamSite01,** **Blog01,** **Project01** en **Community01**

Dat is alles. U hebt meerdere siteverzamelingen gemaakt met het .csv bestand dat u hebt gemaakt en één opdracht Windows PowerShell maken. U bent nu klaar om gebruikers aan deze sites te maken en toe te wijzen.

## <a name="step-2-add-users-and-groups"></a>Stap 2: Gebruikers en groepen toevoegen

U gaat nu gebruikers maken en toevoegen aan een groep siteverzamelingen. Vervolgens gebruikt u een .csv om nieuwe groepen en gebruikers bulksgewijs te uploaden.

In de volgende procedures worden de voorbeeldsites TeamSite01, Blog01, Project01 en Community01 gebruikt.

### <a name="create-csv-and-ps1-files"></a>Bestanden .csv en .ps1 maken

1. Open Kladblok en plak het volgende tekstblok er in:<br/>

```powershell
Site,Group,PermissionLevels
https://tenant.sharepoint.com/sites/Community01,Contoso Project Leads,Full Control
https://tenant.sharepoint.com/sites/Community01,Contoso Auditors,View Only
https://tenant.sharepoint.com/sites/Community01,Contoso Designers,Design
https://tenant.sharepoint.com/sites/TeamSite01,XT1000 Team Leads,Full Control
https://tenant.sharepoint.com/sites/TeamSite01,XT1000 Advisors,Edit
https://tenant.sharepoint.com/sites/Blog01,Contoso Blog Designers,Design
https://tenant.sharepoint.com/sites/Blog01,Contoso Blog Editors,Edit
https://tenant.sharepoint.com/sites/Project01,Project Alpha Approvers,Full Control
```
<br/>Waarbij *tenant* gelijk is aan uw tenantnaam.<br/>

2. Sla het bestand op uw bureaublad op **alsGroupsAndPermissions.csv.**<br/>

3. Open een nieuw exemplaar van Kladblok en plak het volgende tekstblok er in:<br/>

```powershell
Group,LoginName,Site
Contoso Project Leads,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Community01
Contoso Auditors,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Community01
Contoso Designers,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Community01
XT1000 Team Leads,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/TeamSite01
XT1000 Advisors,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/TeamSite01
Contoso Blog Designers,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Blog01
Contoso Blog Editors,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Blog01
Project Alpha Approvers,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Project01
```
<br/>Waarbij *tenant* gelijk is aan uw tenantnaam en *gebruikersnaam* gelijk is aan de gebruikersnaam van een bestaande gebruiker.<br/>

4. Sla het bestand op uw bureaublad op **alsUsers.csv.**<br/>

5. Open een nieuw exemplaar van Kladblok en plak het volgende tekstblok er in:<br/>

```powershell
Import-Csv C:\users\MyAlias\desktop\GroupsAndPermissions.csv | ForEach-Object {New-SPOSiteGroup -Group $_.Group -PermissionLevels $_.PermissionLevels -Site $_.Site}
Import-Csv C:\users\MyAlias\desktop\Users.csv | where {Add-SPOUser -Group $_.Group –LoginName $_.LoginName -Site $_.Site}
```
<br/>Waarbij MyAlias gelijk is aan de gebruikersnaam van de gebruiker die momenteel is aangemeld.<br/>

6. Sla het bestand op uw bureaublad op **alsUsersAndGroups.ps1.** Dit is een eenvoudig Windows PowerShell script.

U kunt nu het script UsersAndGroup.ps1 om gebruikers en groepen toe te voegen aan meerdere siteverzamelingen.

### <a name="run-usersandgroupsps1-script"></a>Voer UsersAndGroups.ps1 script uit

1. Ga terug naar de SharePoint Online Management Shell.<br/>
2. Typ of kopieer Windows PowerShell de volgende regel en druk op Enter:<br/>
```powershell
Set-ExecutionPolicy Bypass
```
<br/>

3. Druk bij de bevestigingsprompt op **Y**.<br/>

4. Typ of kopieer en plak Windows PowerShell de volgende prompt en druk op Enter:<br/>

```powershell
c:\users\MyAlias\desktop\UsersAndGroups.ps1
```
<br/>Waarbij *MyAlias* gelijk is aan uw gebruikersnaam.<br/>

5. Wacht totdat de prompt wordt terugkomt voordat u verder gaat. De groepen worden eerst weergegeven terwijl ze worden gemaakt. Vervolgens wordt de groepslijst herhaald wanneer gebruikers worden toegevoegd.

## <a name="see-also"></a>Zie ook

[Verbinding maken om SharePoint Online PowerShell te gebruiken](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

[Online SharePoint onlinesitegroepen beheren met PowerShell](manage-sharepoint-site-groups-with-powershell.md)

[Microsoft 365 beheren met PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Aan de slag met PowerShell voor Microsoft 365](getting-started-with-microsoft-365-powershell.md)