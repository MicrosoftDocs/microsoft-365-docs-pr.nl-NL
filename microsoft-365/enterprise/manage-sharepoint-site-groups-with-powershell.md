---
title: SharePoint Online-sitegroepen beheren met PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/17/2019
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
description: In dit artikel vindt u procedures voor het gebruik van PowerShell voor Microsoft 365 voor het beheren van SharePoint Online-sitegroepen.
ms.openlocfilehash: fa9aff769ff84f8567c45b20c7b6c8a078b4a70c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689408"
---
# <a name="manage-sharepoint-online-site-groups-with-powershell"></a>SharePoint Online-sitegroepen beheren met PowerShell

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Hoewel u het Microsoft 365-Beheercentrum kunt gebruiken, kunt u ook PowerShell voor Microsoft 365 gebruiken voor het beheren van uw SharePoint Online-sitegroepen.

## <a name="before-you-begin"></a>Voordat u begint

Voor de procedures in dit artikel moet u verbinding maken met SharePoint Online. Zie [verbinding maken met SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)voor instructies.

## <a name="view-sharepoint-online-with-powershell-for-microsoft-365"></a>SharePoint Online weergeven met PowerShell voor Microsoft 365

Het SharePoint Online-Beheercentrum heeft een aantal handige methoden voor het beheren van sitegroepen. Stel dat u de groepen en de groepsleden voor de site wilt bekijken `https://litwareinc.sharepoint.com/sites/finance` . U moet het volgende doen om het volgende te doen:

1. Klik in het SharePoint-Beheercentrum op **actieve sites**en klik vervolgens op de URL van de site.
2. Klik op de sitepagina op het pictogram **instellingen** (in de rechterbovenhoek van de pagina) en klik vervolgens op **site machtigingen**.

Herhaal het proces voor de volgende site die u wilt bekijken.

Als u een lijst wilt weergeven met de groepen met PowerShell voor Microsoft 365, kunt u de volgende opdrachten gebruiken:

```powershell
$siteURL = "https://litwareinc.sharepoint.com/sites/finance"
$x = Get-SPOSiteGroup -Site $siteURL
foreach ($y in $x)
    {
        Write-Host $y.Title -ForegroundColor "Yellow"
        Get-SPOSiteGroup -Site $siteURL -Group $y.Title | Select-Object -ExpandProperty Users
        Write-Host
    }
```

Er zijn twee manieren om deze opdracht uit te voeren in de opdrachtprompt van SharePoint Online Management Shell:

- Kopieer de opdrachten naar Kladblok (of een andere teksteditor), wijzig de waarde van de **$siteURL** variabele, selecteer de opdrachten en plak deze vervolgens in de SharePoint Online Management Shell-opdrachtprompt. Wanneer u dat doet, wordt PowerShell beëindigd wanneer u **>>** hierom wordt gevraagd. Druk op ENTER om de opdracht uit te voeren `foreach` .<br/>
- Kopieer de opdrachten naar Kladblok (of een andere teksteditor), wijzig de waarde van de **$siteURL** variabele en sla het tekstbestand op met een naam en de extensie. ps1 in een geschikte map. Voer vervolgens het script uit van de SharePoint Online Management Shell-opdrachtprompt door het pad en de bestandsnaam op te geven. Hier ziet u een voorbeeld van een opdracht:

```powershell
C:\Scripts\SiteGroupsAndUsers.ps1
```

In beide gevallen ziet u iets dat lijkt op het volgende:

![SharePoint Online-sitegroepen](../media/SPO-site-groups.png)

Dit zijn alle groepen die zijn gemaakt voor de site `https://litwareinc.sharepoint.com/sites/finance` en alle gebruikers die zijn toegewezen aan deze groepen. De namen van de groepen zijn geel, zodat u de namen van de groepsleden kunt onderscheiden.

Hier ziet u bijvoorbeeld een opdrachtset met de groepen en alle groepslidmaatschappen voor al uw SharePoint Online-sites.

```powershell
$x = Get-SPOSite
foreach ($y in $x)
    {
        Write-Host $y.Url -ForegroundColor "Yellow"
        $z = Get-SPOSiteGroup -Site $y.Url
        foreach ($a in $z)
            {
                 $b = Get-SPOSiteGroup -Site $y.Url -Group $a.Title 
                 Write-Host $b.Title -ForegroundColor "Cyan"
                 $b | Select-Object -ExpandProperty Users
                 Write-Host
            }
    }
```
    
## <a name="see-also"></a>Zie ook

[Verbinding maken met SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

[SharePoint Online-sites maken en gebruikers toevoegen met PowerShell](create-sharepoint-sites-and-add-users-with-powershell.md)

[Gebruikers en groepen van SharePoint Online beheren met PowerShell](manage-sharepoint-users-and-groups-with-powershell.md)

[Microsoft 365 beheren met PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Aan de slag met PowerShell voor Microsoft 365](getting-started-with-microsoft-365-powershell.md)

