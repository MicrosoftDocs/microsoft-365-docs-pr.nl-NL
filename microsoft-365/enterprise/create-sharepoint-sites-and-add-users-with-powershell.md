---
title: SharePoint Online-sites maken en gebruikers toevoegen met PowerShell
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
description: 'Overzicht: PowerShell gebruiken om nieuwe SharePoint Online-sites te maken en vervolgens gebruikers en groepen aan deze sites toe te voegen.'
ms.openlocfilehash: 4c4edbd68343f0eaf3a25a8c60a2af1e83b058b6
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689103"
---
# <a name="create-sharepoint-online-sites-and-add-users-with-powershell"></a>SharePoint Online-sites maken en gebruikers toevoegen met PowerShell

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Wanneer u PowerShell voor Microsoft 365 gebruikt om SharePoint Online-sites te maken en gebruikers toe te voegen, kunt u snel en herhaaldelijk taken sneller uitvoeren dan in het Microsoft 365-Beheercentrum. Het is ook mogelijk om taken uit te voeren die niet beschikbaar zijn in het Microsoft 365-Beheercentrum. 

## <a name="connect-to-sharepoint-online"></a>Verbinding maken met SharePoint Online

Voor de procedures in dit onderwerp moet u verbinding maken met SharePoint Online. Zie [verbinding maken met SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) voor instructies

## <a name="step-1-create-new-site-collections-using-powershell"></a>Stap 1: Maak nieuwe siteverzamelingen met behulp van PowerShell

Maak meerdere sites met behulp van PowerShell en een CSV-bestand dat u maakt met behulp van de voorbeeldcode en het Kladblok. Voor deze procedure vervangt u de informatie over de tijdelijke aanduiding tussen vierkante haken met uw eigen site-en Tenant informatie. Met deze procedure kunt u één bestand maken en één PowerShell-opdracht uitvoeren waarbij dat bestand wordt gebruikt. Dit zorgt ervoor dat de acties zowel herhalen als verplaatsbaar zijn en veel, indien niet allen, van invloed zijn op het typen van lange opdrachten in de SharePoint Online Management Shell. Deze procedure bestaat uit twee gedeelten. Eerst maakt u een CSV-bestand en gaat u naar het CSV-bestand met behulp van PowerShell, waarin de inhoud wordt gebruikt om de sites te maken.

De PowerShell-cmdlet importeert het CSV-bestand en sluist in een lus binnen de accolades die de eerste regel van het bestand als kolomkoppen leest. De PowerShell-cmdlet belegt vervolgens de resterende records, maakt een nieuwe siteverzameling voor elke record en wijst eigenschappen van de siteverzameling toe op basis van de kolomkoppen.

### <a name="create-a-csv-file"></a>Een CSV-bestand maken

1. Open Kladblok en plak de volgende tekst blokkering erin:<br/>

```powershell
Owner,StorageQuota,Url,ResourceQuota,Template,TimeZoneID,Name
owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/TeamSite01,25,EHS#1,10,Contoso Team Site
owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/Blog01,25,BLOG#0,10,Contoso Blog
owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Project01,25,PROJECTSITE#0,10,Project Alpha
owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Community01,25,COMMUNITY#0,10,Community Site
```
<br/>Waarbij *Tenant* de naam van de Tenant is en *eigenaar* de gebruikersnaam is van de gebruiker in de Tenant waaraan u de rol van primaire beheerder van de siteverzameling wilt verlenen.<br/>(Druk op CTRL + H wanneer u Kladblok gebruikt om de bulk sneller te vervangen.)<br/>

2. Sla het bestand op uw bureaublad op als **SiteCollections.csv**.<br/>

> [!TIP]
> Voordat u dit of een ander. CSV-of Windows PowerShell-scriptbestand gebruikt, is het een goede gewoonte om ervoor te zorgen dat er geen overbodige of niet-afdrukbare tekens zijn. Open het bestand in Word en klik op het lint op het pictogram alinea om niet-afdrukbare tekens weer te geven. Er moeten geen overbodige niet-afdrukbare tekens zijn. Dit kan bijvoorbeeld geen alineamarkeringen buiten de laatste aan het einde van het bestand bevatten.

### <a name="run-the-windows-powershell-command"></a>De Windows PowerShell-opdracht uitvoeren

1. Typ of kopieer en plak de volgende opdracht bij de Windows PowerShell-prompt en druk op ENTER:<br/>
```powershell
Import-Csv C:\users\MyAlias\desktop\SiteCollections.csv | ForEach-Object {New-SPOSite -Owner $_.Owner -StorageQuota $_.StorageQuota -Url $_.Url -NoWait -ResourceQuota $_.ResourceQuota -Template $_.Template -TimeZoneID $_.TimeZoneID -Title $_.Name}
```
<br/>Waarbij *Mijn alias* gelijk is aan uw alias voor uw gebruikers.<br/>

2. Wacht totdat de Windows PowerShell-prompt opnieuw wordt weergegeven. Het kan een paar minuten duren.<br/>

3. Typ of kopieer en plak de volgende cmdlet achter de Windows PowerShell-prompt en druk op ENTER:<br/>

```powershell
Get-SPOSite -Detailed | Format-Table -AutoSize
```
<br/>

4. Let op de nieuwe siteverzamelingen in de lijst. Als u het CSV-voorbeeldbestand gebruikt, ziet u de volgende siteverzamelingen: **TeamSite01**, **Blog01**, **Project01**en **Community01**

Dat is alles. U hebt meerdere siteverzamelingen gemaakt met het. CSV-bestand dat u hebt gemaakt en één Windows PowerShell-opdracht. U bent nu klaar om gebruikers te maken en toe te wijzen aan deze sites.

## <a name="step-2-add-users-and-groups"></a>Stap 2: gebruikers en groepen toevoegen

U gaat nu gebruikers maken en deze toevoegen aan een siteverzamelingsgroep. Vervolgens gebruikt u een CSV-bestand om nieuwe groepen en gebruikers bulksgewijs te uploaden.

De volgende procedures gaan verder met de voorbeeld sites TeamSite01, Blog01, Project01 en Community01.

### <a name="create-csv-and-ps1-files"></a>CSV-en ps1-bestanden maken

1. Open Kladblok en plak de volgende tekst blokkering erin:<br/>

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
<br/>Dit *is de* naam van de Tenant en de naam van de Tenant.<br/>

2. Sla het bestand op uw bureaublad op als **GroupsAndPermissions.csv**.<br/>

3. Open een nieuw exemplaar van Kladblok en plak het volgende tekstblok in het Kladblok:<br/>

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
<br/>Dit *is de* naam van de Tenant en de *gebruikersnaam is gelijk aan* de gebruikersnaam van een bestaande gebruiker.<br/>

4. Sla het bestand op uw bureaublad op als **Users.csv**.<br/>

5. Open een nieuw exemplaar van Kladblok en plak het volgende tekstblok in het Kladblok:<br/>

```powershell
Import-Csv C:\users\MyAlias\desktop\GroupsAndPermissions.csv | ForEach-Object {New-SPOSiteGroup -Group $_.Group -PermissionLevels $_.PermissionLevels -Site $_.Site}
Import-Csv C:\users\MyAlias\desktop\Users.csv | where {Add-SPOUser -Group $_.Group –LoginName $_.LoginName -Site $_.Site}
```
<br/>Waarbij mijn alias gelijk is aan de gebruikersnaam van de gebruiker die op dat moment is aangemeld.<br/>

6. Sla het bestand op uw bureaublad op als **UsersAndGroups.ps1**. Dit is een eenvoudig Windows PowerShell-script.

U bent nu klaar om het UsersAndGroup.ps1 script uit te voeren om gebruikers en groepen toe te voegen aan meerdere siteverzamelingen.

### <a name="run-usersandgroupsps1-script"></a>UsersAndGroups.ps1 script uitvoeren

1. Ga terug naar de SharePoint Online Management Shell.<br/>
2. Typ of kopieer en plak de volgende regel in de Windows PowerShell-prompt en druk op ENTER:<br/>
```powershell
Set-ExecutionPolicy Bypass
```
<br/>

3. Druk op **Y**wanneer u om een bevestiging wordt gevraagd.<br/>

4. Typ of kopieer en plak de volgende tekst bij de Windows PowerShell-prompt en druk op ENTER:<br/>

```powershell
c:\users\MyAlias\desktop\UsersAndGroups.ps1
```
<br/>Waarbij *Mijn alias* gelijk is aan uw gebruikersnaam.<br/>

5. Wacht totdat de prompt wordt weergegeven voordat u verdergaat. U ziet eerst welke groepen worden weergegeven wanneer ze worden gemaakt. Vervolgens wordt de groepslijst herhaald wanneer gebruikers worden toegevoegd.

## <a name="see-also"></a>Zie ook

[Verbinding maken met SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

[SharePoint Online-sitegroepen beheren met PowerShell](manage-sharepoint-site-groups-with-powershell.md)

[Microsoft 365 beheren met PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Aan de slag met PowerShell voor Microsoft 365](getting-started-with-microsoft-365-powershell.md)

