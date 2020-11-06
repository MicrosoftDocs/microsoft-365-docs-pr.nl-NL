---
title: Mogelijkheden voor meervoudige geo in OneDrive en SharePoint Online
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
description: Breid uw Microsoft 365-aanwezigheid uit naar meerdere geografische regio's met mogelijkheden voor meervoudige geo-mogelijkheden in OneDrive online.
ms.openlocfilehash: 84abfc01d5073889e998347f58d4a3e8bb29ea33
ms.sourcegitcommit: 5a355bde865369f64ea1788a378da23c65b1d249
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/06/2020
ms.locfileid: "48930175"
---
# <a name="multi-geo-capabilities-in-onedrive-and-sharepoint-online"></a>Mogelijkheden voor meervoudige geo in OneDrive en SharePoint Online

Met mogelijkheden voor meervoudige geo in OneDrive en SharePoint Online kunt u de besturing van het land of de regio met gedeelde bronnen zoals SharePoint-Team sites en Microsoft 365-groeps postvakken bewaren.

Voor elke gebruiker, groeps postvak en SharePoint-site is een voorkeurs gegevenslocatie (PDL) beschikbaar waarmee de geografische locatie wordt aangegeven waar gerelateerde gegevens moeten worden opgeslagen. De persoonsgegevens (Exchange-postvak en OneDrive) van gebruikers en de Microsoft 365-groepen of SharePoint-sites die ze maken, kunnen op de opgegeven geo-locatie worden opgeslagen om te voldoen aan de vereisten voor data-woonplaats. U kunt [verschillende beheerders opgeven voor elke geografische locatie](add-a-sharepoint-geo-admin.md).

Gebruikers krijgen een naadloze ervaring wanneer ze Microsoft 365-Services gebruiken, waaronder Office-toepassingen, OneDrive en Search. Zie [de gebruikerservaring in een omgeving met meerdere geografische gebruikers](multi-geo-user-experience.md) voor meer informatie.

## <a name="onedrive"></a>OneDrive

U kunt de OneDrive van elke gebruiker op de site van een beheerder richten of [verplaatsen](move-onedrive-between-geo-locations.md) naar een locatie op de locatie van de gebruiker op basis van de PDL van de gebruiker. Persoonlijke bestanden worden vervolgens bewaard op die geografische locatie, maar ze kunnen worden gedeeld met gebruikers in andere geografische locaties.

## <a name="sharepoint-sites-and-groups"></a>SharePoint-sites en-groepen

Het beheer van de functie voor meervoudige geo is beschikbaar via het SharePoint-Beheercentrum. Meer informatie vindt u in het [bijbehorende blogbericht](https://techcommunity.microsoft.com/t5/Office-365-Blog/Now-available-Multi-Geo-in-SharePoint-and-Office-365-Groups/ba-p/263302).

Wanneer een gebruiker een SharePoint-groepssite maakt die is verbonden met een SharePoint-site in een omgeving met meerdere geo-geografische omgevingen, wordt de persoonlijke locatie gebruikt om de locatie te bepalen waar de site en het bijbehorende groeps postvak worden gemaakt. (Als de waarde voor PDL PDL van de gebruiker niet is ingesteld of is ingesteld op geo-locatie die niet is geconfigureerd als een satelliet locatie, worden de site en het postvak in de centrale locatie gemaakt.)

Microsoft 365-Services, behalve Exchange, OneDrive en SharePoint, zijn niet meerdere geo. Microsoft 365-groepen die zijn gemaakt door deze services, worden echter vastgelegd met de PDL van de auteur en via hun Exchange-groeps postvak en de site van de Office 365-groep die is ingericht in de bijbehorende geo. 

## <a name="managing-the-multi-geo-environment"></a>De omgeving voor meerdere geografische gebieden beheren

Het instellen en beheren van uw omgeving met meerdere geografische omgevingen doet u door het SharePoint-Beheercentrum. 

![Schermafbeelding van de pagina geografische locaties in het SharePoint-Beheercentrum](../media/sharepoint-multi-geo-admin-center.png)

(Voor sommige acties, zoals het verplaatsen van een SharePoint-site of een OneDrive-site is Microsoft PowerShell vereist.)

## <a name="see-also"></a>Zie ook

[Meerdere geografische groepen in SharePoint-en Microsoft 365-groepen](https://techcommunity.microsoft.com/t5/Office-365-Blog/Now-available-Multi-Geo-in-SharePoint-and-Office-365-Groups/ba-p/263302)

[Een multi-geo-omgeving beheren](administering-a-multi-geo-environment.md)

[SharePoint-opslag quota's in meerdere geografische omgevingen](sharepoint-multi-geo-storage-quota.md)

[Postvakken van Exchange Online in een omgeving met meerdere geografische gebieden beheren](administering-exchange-online-multi-geo.md)
