---
title: Multi-Geo-mogelijkheden in OneDrive en SharePoint Online
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: ''
ms.collection:
- Strat_SP_gtc
- SPO_Content
- m365solution-scenario
- m365solution-spintranet
localization_priority: Normal
ms.assetid: 094e86f2-9ff0-40ac-af31-28fcaba00c1d
description: Vouw uw Microsoft 365 uit naar meerdere geografische regio's met multi-geomogelijkheden in OneDrive Online.
ms.openlocfilehash: 405f876317a6cec6defdf3f1a49b0dc32ac0add2
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362280"
---
# <a name="multi-geo-capabilities-in-onedrive-and-sharepoint-online"></a>Multi-Geo Capabilities in OneDrive en SharePoint Online

Met multi-geo-mogelijkheden in OneDrive en SharePoint Online kunt u gedeelde resources beheren, zoals SharePoint teamsites en Microsoft 365 Groepspostvakken die in rust zijn opgeslagen op een opgegeven geografische locatie.

Elke gebruiker, groeppostvak en SharePoint site heeft een VOORKEURsgegevenslocatie (PDL) die de geografische locatie aan wijst waar gerelateerde gegevens moeten worden opgeslagen. De persoonlijke gegevens van gebruikers (Exchange postvak en OneDrive) samen met alle Microsoft 365 Groepen of SharePoint-sites die ze maken, kunnen worden opgeslagen op de opgegeven geografische locatie om te voldoen aan de vereisten voor gegevensopslag. U kunt [verschillende beheerders opgeven voor elke geografische locatie.](add-a-sharepoint-geo-admin.md)

Gebruikers krijgen een naadloze ervaring bij het gebruik Microsoft 365 services, Office toepassingen, OneDrive en Zoeken. Zie [Gebruikerservaring in een multi-geo-omgeving voor](multi-geo-user-experience.md) meer informatie.

## <a name="onedrive"></a>OneDrive

De OneDrive gebruikers kunnen worden ingericht in of verplaatst door een [beheerder](move-onedrive-between-geo-locations.md) naar een satellietlocatie in overeenstemming met de PDL van de gebruiker. Persoonlijke bestanden worden vervolgens op die geografische locatie bewaard, maar ze kunnen worden gedeeld met gebruikers op andere geografische locaties.

## <a name="sharepoint-sites-and-groups"></a>SharePoint Sites en groepen

Het beheer van de functie Multi-Geo is beschikbaar via het SharePoint beheercentrum. Gedetailleerde informatie vindt u in het [bijbehorende blogbericht.](https://techcommunity.microsoft.com/t5/Office-365-Blog/Now-available-Multi-Geo-in-SharePoint-and-Office-365-Groups/ba-p/263302)

Wanneer een gebruiker een SharePoint met een groep verbonden site maakt in een multi-geo-omgeving, wordt de PDL ervan gebruikt om de geografische locatie te bepalen waar de site en het bijbehorende groepspostvak worden gemaakt. (Als de PDL-waarde van de gebruiker niet is ingesteld of is ingesteld op een geografische locatie die niet is geconfigureerd als satellietlocatie, worden de site en het postvak op de centrale locatie gemaakt.)

Microsoft 365 andere services dan Exchange, OneDrive, SharePoint en Teams zijn niet Multi-Geo. De Microsoft 365 groepen die door deze services worden gemaakt, worden echter geconfigureerd met de PDL van de maker en het Exchange Groepspostvak, SharePoint-site zijn ingericht in de bijbehorende geo. 

## <a name="managing-the-multi-geo-environment"></a>De multi-geo-omgeving beheren

Het instellen en beheren van uw multi-geo-omgeving gebeurt via het SharePoint beheercentrum. 

![Schermafbeelding van de pagina geografische locaties in het SharePoint beheercentrum](../media/sharepoint-multi-geo-admin-center.png)

(Voor sommige acties, zoals het verplaatsen van een SharePoint site of een OneDrive microsoft PowerShell.)

## <a name="see-also"></a>Zie ook

[Multi-Geo in SharePoint en Microsoft 365 Groepen](https://techcommunity.microsoft.com/t5/Office-365-Blog/Now-available-Multi-Geo-in-SharePoint-and-Office-365-Groups/ba-p/263302)

[Een multi-geo-omgeving beheren](administering-a-multi-geo-environment.md)

[SharePoint opslagquota in multi-geo-omgevingen](sharepoint-multi-geo-storage-quota.md)

[Postvakken Exchange Online in een multi-geo-omgeving beheren](administering-exchange-online-multi-geo.md)
