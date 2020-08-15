---
title: Meerdere geografische SharePoint-geografische locaties inschakelen
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.collection:
- Strat_SP_gtc
- SPO_Content
localization_priority: Normal
description: Dit artikel bevat informatie over globale beheerders en SharePoint-beheerders over het inschakelen van meervoudige SharePoint-geografische locaties voor satellieten.
ms.openlocfilehash: 78f0e925a333dd48a6016bc749459b13e1ac21c0
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689520"
---
# <a name="enabling-sharepoint-multi-geo-in-your-satellite-geo-location"></a>Meerdere geografische SharePoint-geografische locaties inschakelen

Dit artikel is bedoeld voor globale beheerders en SharePoint-beheerders die een locatie voor meervoudige geo-satelliet hebben gemaakt, zodat de mogelijkheden van SharePoint in meerdere geografische groepen algemeen beschikbaar zijn op 27 maart 2019 en die niet meerdere gebruikers van **SharePoint hebben** ingeschakeld op hun satelliet locatie (s). 

>[!Note]
>Als u **na maart 27**een nieuwe geo-locatie hebt toegevoegd, hoeft u deze instructies niet uit te voeren, aangezien de nieuwe geografische locatie al voor OneDrive en SharePoint is ingeschakeld.

Met deze instructies kunt u SharePoint op uw locatie inschakelen, zodat de gebruikers van de multi-geo-satelliet gebruikmaken van de mogelijkheden van OneDrive en SharePoint voor meerdere gebruikers in O365. 

>[!IMPORTANT]
>Dit vormt één manier van activering. Wanneer u de SPO-modus hebt ingesteld, kunt u uw Tenant niet terugzetten naar de modus voor meerdere geo-modus zonder dat u een escalatie hoeft te voeren. 

## <a name="to-set-a-geo-location-into-spo-mode"></a>Een geografische locatie instellen in de SPO-modus

Als u een geografische locatie wilt instellen in de SPO-modus, maakt u verbinding met de geografische locatie die u wilt instellen in de SPO-modus:

1.    Uw SharePoint Online Management Shell openen 
2.    Connect-SPOService-URL "https://$tenantGeo-admin.sharepoint.com"-Credential $credential
3.    Set-SPOMultiGeoExperience</br></br>
![Set-SPOMultiGeoExperience](../media/Set-SPO-MultiGeo.jpg)
4.    Deze bewerking duurt doorgaans ongeveer een uur, wat betekent dat u diverse publicaties in de service maakt en de Tenant opnieuw stempelt. Voer na minstens 1 uur een Get-SPOMultiGeoExperience uit.  Hiermee wordt aangegeven of deze geo-locatie in de SPO-modus is.</br></br>
![Set-SPOMultiGeoExperience](../media/Get-SPO-MultiGeo.jpg)

 
 
 
>[!Note]
>Bepaalde caches in de service-update elke 24 uur, dus het is mogelijk dat de satelliet voor een periode van maximaal 24 uur niet af en toe verloopt alsof deze nog steeds in de ODB-modus was. Dit veroorzaakt geen technische problemen. 
 
Ga naar [aka.MS/sharepointmultigeo](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md) voor meer informatie over multi-geo SharePoint.


