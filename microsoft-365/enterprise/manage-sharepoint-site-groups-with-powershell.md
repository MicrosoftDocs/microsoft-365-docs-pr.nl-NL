---
title: Online SharePoint onlinesitegroepen beheren met PowerShell
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
description: In dit artikel vindt u procedures voor het gebruik van PowerShell Microsoft 365 voor het beheren SharePoint Online-sitegroepen.
ms.openlocfilehash: bcc7a00a6114a6fa2ba8aa02520267bd03a0abf5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909536"
---
# <a name="manage-sharepoint-online-site-groups-with-powershell"></a>Online SharePoint onlinesitegroepen beheren met PowerShell

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Hoewel u het Microsoft 365 beheercentrum kunt gebruiken, kunt u PowerShell ook gebruiken voor Microsoft 365 om uw SharePoint Online-sitegroepen te beheren.

## <a name="before-you-begin"></a>Voordat u begint

Voor de procedures in dit artikel moet u verbinding maken met SharePoint Online. Zie voor instructies [Verbinding maken SharePoint Online PowerShell.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

## <a name="view-sharepoint-online-with-powershell-for-microsoft-365"></a>Online SharePoint weergeven met PowerShell voor Microsoft 365

Het SharePoint Online-beheercentrum heeft een aantal eenvoudig te gebruiken methoden voor het beheren van sitegroepen. Stel dat u de groepen en de groepsleden wilt bekijken voor de `https://litwareinc.sharepoint.com/sites/finance` site. U moet het volgende doen:

1. Klik in SharePoint beheercentrum op **Actieve sites** en klik vervolgens op de URL van de site.
2. Klik op de sitepagina op **Instellingen** pictogram (in de rechterbovenhoek van de pagina) en klik vervolgens op **Sitemachtigingen.**

Herhaal vervolgens het proces voor de volgende site die u wilt bekijken.

Als u een lijst met de groepen met PowerShell wilt Microsoft 365, kunt u de volgende opdrachten gebruiken:

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

U kunt deze opdrachtset op twee manieren uitvoeren in SharePoint opdrachtprompt Online Management Shell:

- Kopieer de opdrachten naar Kladblok (of een andere teksteditor), wijzig de waarde van de **variabele $siteURL,** selecteer de opdrachten en plak ze vervolgens in de opdrachtprompt onlinebeheershell SharePoint onlinebeheershell. Wanneer u dit doet, stopt PowerShell bij een **>>** prompt. Druk op Enter om de opdracht uit te `foreach` voeren.<br/>
- Kopieer de opdrachten naar Kladblok (of een andere teksteditor), wijzig de waarde van de **variabele $siteURL** en sla dit tekstbestand op met een naam en de .ps1-extensie in een geschikte map. Voer vervolgens het script uit vanaf SharePoint opdrachtprompt onlinebeheershell door het pad en de bestandsnaam op te geven. Hier is een voorbeeldopdracht:

```powershell
C:\Scripts\SiteGroupsAndUsers.ps1
```

In beide gevallen ziet u zoiets als dit:

![SharePoint Onlinesitegroepen](../media/SPO-site-groups.png)

Dit zijn alle groepen die zijn gemaakt voor de site `https://litwareinc.sharepoint.com/sites/finance` en alle gebruikers die aan deze groepen zijn toegewezen. De groepsnamen zijn geel om u te helpen groepsnamen van hun leden te scheiden.

Als een ander voorbeeld is hier een opdrachtset met de groepen en alle groepslidmaatschap voor al uw SharePoint Online-sites.

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

[Verbinding maken om SharePoint Online PowerShell te gebruiken](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

[Onlinesites SharePoint en gebruikers toevoegen met PowerShell](create-sharepoint-sites-and-add-users-with-powershell.md)

[Online SharePoint en groepen beheren met PowerShell](manage-sharepoint-users-and-groups-with-powershell.md)

[Microsoft 365 beheren met PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Aan de slag met PowerShell voor Microsoft 365](getting-started-with-microsoft-365-powershell.md)