---
title: Gebruikers en groepen van SharePoint Online beheren met PowerShell
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
description: In dit artikel vindt u informatie over het gebruik van PowerShell voor Microsoft 365 voor het beheren van SharePoint Online-gebruikers,-groepen en-sites.
ms.openlocfilehash: 5252ecc950e5f26d6ad60cd871910a67bf50f187
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689405"
---
# <a name="manage-sharepoint-online-users-and-groups-with-powershell"></a>Gebruikers en groepen van SharePoint Online beheren met PowerShell

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Als u een SharePoint Online-beheerder bent die met grote lijsten met gebruikersaccounts of groepen werkt en ze een eenvoudige manier wil beheren, kunt u PowerShell voor Microsoft 365 gebruiken. 

Voordat u begint, moet u voor de procedures in dit onderwerp verbinding maken met SharePoint Online. Zie [verbinding maken met SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) voor instructies

## <a name="get-a-list-of-sites-groups-and-users"></a>Een lijst met sites, groepen en gebruikers weergeven

Voordat we gebruikers en groepen gaan beheren, moet u lijsten met uw sites, groepen en gebruikers krijgen. U kunt deze gegevens gebruiken om het voorbeeld in dit artikel te bewerken.

U ontvangt een lijst met de sites in de Tenant met behulp van deze opdracht:

```powershell
Get-SPOSite
```

U ontvangt een lijst met de groepen in uw Tenant met deze opdracht:

```powershell
Get-SPOSite | ForEach {Get-SPOSiteGroup -Site $_.Url} | Format-Table
```

U ontvangt een lijst met gebruikers in uw Tenant met deze opdracht:

```powershell
Get-SPOSite | ForEach {Get-SPOUser -Site $_.Url}
```

## <a name="add-a-user-to-the-site-collection-administrators-group"></a>Een gebruiker toevoegen aan de groep beheerders van de site verzameling

U gebruikt de `Set-SPOUser` cmdlet om een gebruiker toe te voegen aan de lijst met beheerders van siteverzamelingen voor een siteverzameling.

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
Set-SPOUser -Site https://$tenant.sharepoint.com/sites/$site -LoginName $user@$tenant.com -IsSiteCollectionAdmin $true
 ```

Als u deze opdrachten wilt gebruiken, vervangt u alles binnen de aanhalingstekens, waaronder de < en > tekens, met de juiste namen.

Deze reeks opdrachten voegt bijvoorbeeld Opal Castillo (gebruikersnaam opalc) toe aan de lijst met beheerders van de siteverzameling in de siteverzameling contoso, pacht:

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "opalc"
Set-SPOUser -Site https://$tenant.sharepoint.com/sites/$site -LoginName $user@$tenant.com -IsSiteCollectionAdmin $true
```

U kunt deze opdrachten in Kladblok kopiëren en plakken, de variabele waarden voor $tenant, $site en $user van werkelijke waarden uit de omgeving wijzigen en deze vervolgens in het SharePoint Online management shell-venster plakken om ze uit te voeren.

## <a name="add-a-user-to-other-site-collection-groups"></a>Een gebruiker toevoegen aan andere site verzamelings groepen

In deze taak gebruiken we de `Add-SPOUser` cmdlet om een gebruiker toe te voegen aan een SharePoint-groep in een siteverzameling.

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
$group = "<group name name, such as Auditors>"
Add-SPOUser -Group $group -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site

```

Laten we bijvoorbeeld Glen Rife (gebruikersnaam glenr) toevoegen aan de groep auditers in de siteverzameling voor ContosoTest in contoso, pacht:

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "glenr"
$group = "Auditors"
Add-SPOUser -Group $group -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site
```

## <a name="create-a-site-collection-group"></a>Een siteverzamelingsgroep maken

Met de `New-SPOSiteGroup` cmdlet maakt u een nieuwe SharePoint-groep en voegt u deze toe aan een siteverzameling.

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$group = "<group name name, such as Auditors>"
$level = "<permission level, such as View Only>"
New-SPOSiteGroup -Group $group -PermissionLevels $level -Site https://$tenant.sharepoint.com/sites/$site
```
De eigenschappen van de groep, zoals de machtigingsniveaus, kunt u later bijwerken met behulp van de `Set-SPOSiteGroup` cmdlet.

Laten we bijvoorbeeld de groep auditors toevoegen met de machtiging alleen weergeven voor de contosotest-siteverzameling in contoso, pacht:

```powershell
$tenant = "contoso"
$site = "contosotest"
$group = "Auditors"
$level = "View Only"
New-SPOSiteGroup -Group $group -PermissionLevels $level -Site https://$tenant.sharepoint.com/sites/$site
```

## <a name="remove-users-from-a-group"></a>Gebruikers uit een groep verwijderen

Soms moet u een gebruiker van een site of zelfs alle sites verwijderen. Het kan zijn dat de werknemer van de ene naar de andere afdeling gaat of het bedrijf verlaat. U kunt deze functie in de GEBRUIKERSINTERFACE eenvoudig doen voor een werknemer, maar dit is niet eenvoudig wanneer u een volledige afdeling van een site naar een andere site wilt verplaatsen.

Met de SharePoint Online Management Shell-en CSV-bestanden is dit echter snel en gemakkelijk. In deze taak gaat u Windows PowerShell gebruiken om een gebruiker te verwijderen uit een beveiligingsgroep van een siteverzameling. Vervolgens maakt u een CSV-bestand en verwijdert u veel gebruikers van verschillende sites. 

We gebruiken de cmdlet Remove-echtgenoot om één Microsoft 365-gebruiker uit de groep siteverzameling te verwijderen, zodat we de opdrachtsyntaxis kunnen zien. U ziet de syntaxis als volgt:

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
$group = "<group name name, such as Auditors>"
Remove-SPOUser -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site -Group $group
```
Laten we de Overby van de siteverzameling in de contosotest-siteverzameling verwijderen uit de siteverzameling van de siteverzameling in de contoso pacht:

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "bobbyo"
$group = "Auditors"
Remove-SPOUser -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site -Group $group
```

Stel dat we Berend willen verwijderen van alle groepen die hij momenteel aanmeldt. Dit doet u als volgt:

```powershell
$tenant = "contoso"
$user = "bobbyo"
Get-SPOSite | ForEach {Get-SPOSiteGroup –Site $_.Url} | ForEach {Remove-SPOUser -LoginName $user@$tenant.com -Site &_.Url}
```

> [!WARNING]
> Dit is slechts een voorbeeld. U dient deze opdracht niet uit te voeren, tenzij u echt een gebruiker uit elke groep moet verwijderen, bijvoorbeeld als de gebruiker het bedrijf verlaat.

## <a name="automate-management-of-large-lists-of-users-and-groups"></a>Beheer van grote lijsten van gebruikers en groepen automatiseren

Als u een groot aantal accounts wilt toevoegen aan SharePoint-sites en ze machtigingen wilt geven, kunt u het Microsoft 365-Beheercentrum, afzonderlijke PowerShell-opdrachten of PowerShell gebruiken als een CSV-bestand. Met deze opties is het CSV-bestand de snelste manier om deze taak te automatiseren.

Het basisproces is het maken van een CSV-bestand met kopteksten (kolommen) die overeenkomen met de parameters die door het Windows PowerShell-script worden vereist. U kunt eenvoudig een lijst maken in Excel en deze vervolgens als een CSV-bestand exporteren. Vervolgens gebruikt u een Windows PowerShell-script om records (rijen) uit het CSV-bestand te doorzoeken en de gebruikers toe te voegen aan groepen en de groepen aan sites. 

Als u bijvoorbeeld een CSV-bestand wilt maken, kunt u een groep siteverzamelingen, groepen en machtigingen definiëren. Vervolgens maakt u een CSV-bestand om de groepen met gebruikers te vullen. Tot slot maakt u een simpel Windows PowerShell-script waarmee de groepen worden gemaakt en gevuld.

Het eerste CSV-bestand voegt een of meer groepen toe aan een of meer siteverzamelingen, en heeft de volgende structuur:

Factuurkop

```powershell
Site,Group,PermissionLevels
```

Item

```powershell
https://tenant.sharepoint.com/sites/site,group,level
```

Hier ziet u een voorbeeld van een bestand:

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

Het tweede CSV-bestand voegt een of meer gebruikers toe aan een of meer groepen, en heeft de volgende structuur:

Factuurkop

```powershell
Group,LoginName,Site
```

Item

```powershell
group,login,https://tenant.sharepoint.com/sites/site
```

Hier ziet u een voorbeeld van een bestand:

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

Voor de volgende stap moet u de twee CSV-bestanden opslaan op uw station. Hier ziet u voorbeelden van opdrachten die gebruikmaken van CSV-bestanden en het toevoegen van machtigingen en groepslidmaatschap:

```powershell
Import-Csv C:\O365Admin\GroupsAndPermissions.csv | ForEach {New-SPOSiteGroup -Group $_.Group -PermissionLevels $_.PermissionLevels -Site $_.Site}
Import-Csv C:\O365Admin\Users.csv | ForEach {Add-SPOUser -Group $_.Group –LoginName $_.LoginName -Site $_.Site}
```

Met het script wordt de inhoud van het CSV-bestand geïmporteerd en worden de waarden in de kolommen gebruikt voor het vullen van de parameters van de opdrachten **New-SPOSiteGroup** en **add-echtgenote** . In ons voorbeeld wordt deze map opgeslagen in de map theO365Admin op station C, maar u kunt de locatie waar u maar wilt.

Laten we nu een aantal personen verwijderen voor verschillende groepen in verschillende sites met hetzelfde CSV-bestand. Hier ziet u een voorbeeld van een opdracht:

```powershell
Import-Csv C:\O365Admin\Users.csv | ForEach {Remove-SPOUser -LoginName $_.LoginName -Site $_.Site -Group $_.Group}
```

## <a name="generate-user-reports"></a>Gebruikers rapporten genereren

Mogelijk wilt u een eenvoudig rapport voor enkele sites weergeven en de gebruikers voor deze sites, hun machtigingsniveau en andere eigenschappen weergeven. Hoe ziet de syntaxis er als volgt uit:

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | select * | Format-table -Wrap -AutoSize | Out-File c\UsersReport.txt -Force -Width 360 -Append
```

Hierdoor worden de gegevens van deze drie sites opgezocht en naar een tekstbestand op uw lokale station geschreven. Houd er rekening mee dat via de parameter toevoegen nieuwe inhoud aan een bestaand bestand wordt toegevoegd.

Laten we bijvoorbeeld een rapport uitvoeren op de sites ContosoTest, TeamSite01 en Project01 voor de Contoso1-Tenant:

```powershell
$tenant = "contoso"
$site = "contosotest"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
$site = "TeamSite01"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site |Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
$site = "Project01"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
```

Let erop dat we alleen de **$site** variabele wijzigen. Met de **$Tenant** variabele wordt de waarde van de hele opdracht beperkt.

Maar wat als u dit wilt doen voor elke site? U kunt dit doen zonder alle websites te hoeven typen met behulp van deze opdracht:

```powershell
Get-SPOSite | ForEach {Get-SPOUser –Site $_.Url} | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
```

Dit rapport is tamelijk simpel, en u kunt meer informatie toevoegen om specifiekere rapporten of rapporten te maken die meer gedetailleerde informatie bevatten. Dit geeft wel een idee van hoe u de SharePoint Online Management Shell kunt gebruiken voor het beheren van gebruikers in de SharePoint Online-omgeving.
   
## <a name="see-also"></a>Zie ook

[Verbinding maken met SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

[SharePoint Online beheren met PowerShell](create-sharepoint-sites-and-add-users-with-powershell.md)

[Microsoft 365 beheren met PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Aan de slag met PowerShell voor Microsoft 365](getting-started-with-microsoft-365-powershell.md)
