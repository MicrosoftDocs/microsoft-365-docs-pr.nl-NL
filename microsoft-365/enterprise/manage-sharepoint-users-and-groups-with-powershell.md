---
title: SharePoint Online-gebruikers en -groepen beheren met PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
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
description: In dit artikel leert u hoe u PowerShell voor Microsoft 365 gebruikt om SharePoint Online-gebruikers, groepen en sites te beheren.
ms.openlocfilehash: cc977355f1182b18d2f2e90b573683ed69299c1c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916724"
---
# <a name="manage-sharepoint-online-users-and-groups-with-powershell"></a>SharePoint Online-gebruikers en -groepen beheren met PowerShell

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Als u een SharePoint Online-beheerder bent die werkt met grote lijsten met gebruikersaccounts of groepen en een eenvoudigere manier wilt om deze te beheren, kunt u PowerShell voor Microsoft 365 gebruiken. 

Voordat u begint, moet u voor de procedures in dit onderwerp verbinding maken met SharePoint Online. Zie Verbinding maken [met SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) voor instructies

## <a name="get-a-list-of-sites-groups-and-users"></a>Een lijst met sites, groepen en gebruikers krijgen

Voordat we gebruikers en groepen gaan beheren, moet u lijsten van uw sites, groepen en gebruikers krijgen. U kunt deze informatie vervolgens gebruiken om het voorbeeld in dit artikel door te nemen.

Een lijst met de sites in uw tenant krijgen met deze opdracht:

```powershell
Get-SPOSite
```

Met deze opdracht krijgt u een lijst met de groepen in uw tenant:

```powershell
Get-SPOSite | ForEach {Get-SPOSiteGroup -Site $_.Url} | Format-Table
```

Een lijst met de gebruikers in uw tenant met deze opdracht:

```powershell
Get-SPOSite | ForEach {Get-SPOUser -Site $_.Url}
```

## <a name="add-a-user-to-the-site-collection-administrators-group"></a>Een gebruiker toevoegen aan de groep Beheerders van siteverzamelingen

U gebruikt de cmdlet om een gebruiker toe te voegen aan de lijst met beheerders van `Set-SPOUser` siteverzamelingen in een siteverzameling.

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
Set-SPOUser -Site https://$tenant.sharepoint.com/sites/$site -LoginName $user@$tenant.com -IsSiteCollectionAdmin $true
 ```

Als u deze opdrachten wilt gebruiken, vervangt u alles in de aanhalingstekens, inclusief de < en > tekens, door de juiste namen.

Met deze reeks opdrachten wordt bijvoorbeeld Opal Castillo (gebruikersnaam opalc) toegevoegd aan de lijst met beheerders van siteverzamelingen in de ContosoTest-siteverzameling in de contoso-tenancy:

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "opalc"
Set-SPOUser -Site https://$tenant.sharepoint.com/sites/$site -LoginName $user@$tenant.com -IsSiteCollectionAdmin $true
```

U kunt deze opdrachten kopiëren en plakken in Kladblok, de variabele waarden voor $tenant, $site en $user wijzigen in werkelijke waarden uit uw omgeving en deze vervolgens in uw SharePoint Online Management Shell-venster plakken om deze uit te voeren.

## <a name="add-a-user-to-other-site-collection-groups"></a>Een gebruiker toevoegen aan andere siteverzamelingsgroepen

In deze taak gebruiken we de cmdlet om een gebruiker toe te voegen aan een `Add-SPOUser` SharePoint-groep op een siteverzameling.

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
$group = "<group name name, such as Auditors>"
Add-SPOUser -Group $group -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site

```

Laten we bijvoorbeeld Glen Rife (gebruikersnaam glenr) toevoegen aan de groep Auditors in de contosoTest-siteverzameling in de contoso tenancy:

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "glenr"
$group = "Auditors"
Add-SPOUser -Group $group -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site
```

## <a name="create-a-site-collection-group"></a>Een siteverzamelingsgroep maken

U gebruikt de `New-SPOSiteGroup` cmdlet om een nieuwe SharePoint-groep te maken en deze toe te voegen aan een siteverzameling.

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$group = "<group name name, such as Auditors>"
$level = "<permission level, such as View Only>"
New-SPOSiteGroup -Group $group -PermissionLevels $level -Site https://$tenant.sharepoint.com/sites/$site
```
Groepseigenschappen, zoals machtigingsniveaus, kunnen later worden bijgewerkt met de `Set-SPOSiteGroup` cmdlet.

Laten we bijvoorbeeld de groep Auditors met alleen-weergavemachtigingen toevoegen aan de contosotestsiteverzameling in de contoso-tenancy:

```powershell
$tenant = "contoso"
$site = "contosotest"
$group = "Auditors"
$level = "View Only"
New-SPOSiteGroup -Group $group -PermissionLevels $level -Site https://$tenant.sharepoint.com/sites/$site
```

## <a name="remove-users-from-a-group"></a>Gebruikers uit een groep verwijderen

Soms moet u een gebruiker van een site of zelfs van alle sites verwijderen. Misschien gaat de werknemer van de ene afdeling naar de andere of verlaat hij het bedrijf. U kunt dit eenvoudig doen voor één werknemer in de gebruikersinterface, maar dit is niet eenvoudig wanneer u een volledige afdeling van de ene site naar de andere moet verplaatsen.

Maar door de SharePoint Online Management Shell- en CSV-bestanden te gebruiken, is dit snel en eenvoudig. In deze taak gebruikt u Windows PowerShell om een gebruiker te verwijderen uit een beveiligingsgroep voor siteverzamelingen. Vervolgens gebruikt u een CSV-bestand en verwijdert u veel gebruikers van verschillende sites. 

We gebruiken de cmdlet 'Remove-SPOUser' om één Microsoft 365-gebruiker uit een siteverzamelingsgroep te verwijderen, zodat we de syntaxis van de opdracht kunnen zien. De syntaxis ziet er als volgende uit:

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
$group = "<group name name, such as Auditors>"
Remove-SPOUser -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site -Group $group
```
Laten we bijvoorbeeld Bobby Overby verwijderen uit de groep Auditors van de siteverzameling Auditors in de contosotestsiteverzameling in de contoso-tenancy:

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "bobbyo"
$group = "Auditors"
Remove-SPOUser -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site -Group $group
```

Stel dat we Bobby willen verwijderen uit alle groepen waarin hij zich momenteel in. Dit doen we als volgende:

```powershell
$tenant = "contoso"
$user = "bobbyo"
Get-SPOSite | ForEach {Get-SPOSiteGroup –Site $_.Url} | ForEach {Remove-SPOUser -LoginName $user@$tenant.com -Site &_.Url}
```

> [!WARNING]
> Dit is slechts een voorbeeld. U moet deze opdracht alleen uitvoeren als u een gebruiker echt uit elke groep moet verwijderen, bijvoorbeeld als de gebruiker het bedrijf verlaat.

## <a name="automate-management-of-large-lists-of-users-and-groups"></a>Beheer van grote lijsten met gebruikers en groepen automatiseren

Als u een groot aantal accounts wilt toevoegen aan SharePoint-sites en deze machtigingen wilt geven, kunt u het Microsoft 365-beheercentrum, afzonderlijke PowerShell-opdrachten of PowerShell een CSV-bestand gebruiken. Van deze opties is het CSV-bestand de snelste manier om deze taak te automatiseren.

Het basisproces bestaat uit het maken van een CSV-bestand met kopteksten (kolommen) die overeenkomen met de parameters die het Windows PowerShell-script nodig heeft. U kunt eenvoudig een dergelijke lijst maken in Excel en deze vervolgens exporteren als een CSV-bestand. Vervolgens gebruikt u een Windows PowerShell-script om records (rijen) in het CSV-bestand te itereren en de gebruikers toe te voegen aan groepen en groepen aan sites. 

Laten we bijvoorbeeld een CSV-bestand maken om een groep siteverzamelingen, groepen en machtigingen te definiëren. Vervolgens maken we een CSV-bestand om de groepen te vullen met gebruikers. Ten slotte maken en uitvoeren we een eenvoudig Windows PowerShell-script dat de groepen maakt en vult.

Het eerste CSV-bestand voegt een of meer groepen toe aan een of meer siteverzamelingen en heeft deze structuur:

Koptekst:

```powershell
Site,Group,PermissionLevels
```

Item:

```powershell
https://tenant.sharepoint.com/sites/site,group,level
```

Hier is een voorbeeldbestand:

```powershell
Site,Group,PermissionLevels
https://contoso.sharepoint.com/sites/contosotest,Contoso Project Leads,Full Control
https://contoso.sharepoint.com/sites/contosotest,Contoso Auditors,View Only
https://contoso.sharepoint.com/sites/contosotest,Contoso Designers,Design
https://contoso.sharepoint.com/sites/TeamSite01,XT1000 Team Leads,Full Control
https://contoso.sharepoint.com/sites/TeamSite01,XT1000 Advisors,Edit
https://contoso.sharepoint.com/sites/Blog01,Contoso Blog Designers,Design
https://contoso.sharepoint.com/sites/Blog01,Contoso Blog Editors,Edit
https://contoso.sharepoint.com/sites/Project01,Project Alpha Approvers,Full Control
```

Het tweede CSV-bestand voegt een of meer gebruikers toe aan een of meer groepen en heeft deze structuur:

Koptekst:

```powershell
Group,LoginName,Site
```

Item:

```powershell
group,login,https://tenant.sharepoint.com/sites/site
```

Hier is een voorbeeldbestand:

```powershell
Group,LoginName,Site
Contoso Project Leads,bobbyo@contoso.com,https://contoso.sharepoint.com/sites/contosotest
Contoso Auditors,allieb@contoso.com,https://contoso.sharepoint.com/sites/contosotest
Contoso Designers,bonniek@contoso.com,https://contoso.sharepoint.com/sites/contosotest
XT1000 Team Leads,dorenap@contoso.com,https://contoso.sharepoint.com/sites/TeamSite01
XT1000 Advisors,garthf@contoso.com,https://contoso.sharepoint.com/sites/TeamSite01
Contoso Blog Designers,janets@contoso.com,https://contoso.sharepoint.com/sites/Blog01
Contoso Blog Editors,opalc@contoso.com,https://contoso.sharepoint.com/sites/Blog01
Project Alpha Approvers,robinc@contoso.com,https://contoso.sharepoint.com/sites/Project01
```

Voor de volgende stap moet u de twee CSV-bestanden hebben opgeslagen op uw station. Hier volgen voorbeeldopdrachten die zowel CSV-bestanden gebruiken als machtigingen en groepslidmaatschap toevoegen:

```powershell
Import-Csv C:\O365Admin\GroupsAndPermissions.csv | ForEach {New-SPOSiteGroup -Group $_.Group -PermissionLevels $_.PermissionLevels -Site $_.Site}
Import-Csv C:\O365Admin\Users.csv | ForEach {Add-SPOUser -Group $_.Group –LoginName $_.LoginName -Site $_.Site}
```

Het script importeert de inhoud van het CSV-bestand en gebruikt de waarden in de kolommen om de parameters van de opdrachten **New-SPOSiteGroup** en **Add-SPOUser** in te vullen. In ons voorbeeld slaan we deze op in de map O365Admin op station C, maar u kunt deze opslaan waar u maar wilt.

Laten we nu een aantal personen voor verschillende groepen op verschillende sites verwijderen met hetzelfde CSV-bestand. Hier is een voorbeeldopdracht:

```powershell
Import-Csv C:\O365Admin\Users.csv | ForEach {Remove-SPOUser -LoginName $_.LoginName -Site $_.Site -Group $_.Group}
```

## <a name="generate-user-reports"></a>Gebruikersrapporten genereren

Mogelijk wilt u een eenvoudig rapport voor een paar sites krijgen en de gebruikers weergeven voor deze sites, hun machtigingsniveau en andere eigenschappen. De syntaxis ziet er als volgende uit:

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | select * | Format-table -Wrap -AutoSize | Out-File c\UsersReport.txt -Force -Width 360 -Append
```

Hiermee worden de gegevens voor deze drie sites verzameld en naar een tekstbestand op uw lokale station geschreven. De parameter –Toevoegen voegt nieuwe inhoud toe aan een bestaand bestand.

Laten we bijvoorbeeld een rapport uitvoeren op de sites ContosoTest, TeamSite01 en Project01 voor de Contoso1-tenant:

```powershell
$tenant = "contoso"
$site = "contosotest"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
$site = "TeamSite01"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site |Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
$site = "Project01"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
```

Houd er rekening mee dat we alleen de variabele **$site** wijzigen. De **$tenant** variabele behoudt de waarde door alle drie de runs van de opdracht.

Maar wat als u dit voor elke site wilt doen? U kunt dit doen zonder dat u al deze websites hoeft te typen met behulp van deze opdracht:

```powershell
Get-SPOSite | ForEach {Get-SPOUser –Site $_.Url} | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
```

Dit rapport is vrij eenvoudig en u kunt meer code toevoegen om specifiekere rapporten of rapporten te maken met meer gedetailleerde informatie. Maar dit moet u een idee geven van hoe u sharePoint Online Management Shell kunt gebruiken om gebruikers in de SharePoint Online-omgeving te beheren.
   
## <a name="see-also"></a>Zie ook

[Verbinding maken met SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

[SharePoint Online beheren met PowerShell](create-sharepoint-sites-and-add-users-with-powershell.md)

[Microsoft 365 beheren met PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Aan de slag met PowerShell voor Microsoft 365](getting-started-with-microsoft-365-powershell.md)