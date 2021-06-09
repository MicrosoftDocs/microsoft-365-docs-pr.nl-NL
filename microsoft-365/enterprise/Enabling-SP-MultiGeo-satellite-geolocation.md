---
title: SharePoint multi-geo in de geografische locatie van de satelliet inschakelen
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
description: Dit artikel bevat informatie voor globale of SharePoint beheerders over het inschakelen van SharePoint Multi-Geo in satellietlocatielocaties.
ms.openlocfilehash: 78f0e925a333dd48a6016bc749459b13e1ac21c0
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689520"
---
# <a name="enabling-sharepoint-multi-geo-in-your-satellite-geo-location"></a>SharePoint multi-geo in de geografische locatie van de satelliet inschakelen

Dit artikel is bedoeld voor globale of SharePoint-beheerders die een  multi-geo-satellietlocatie hebben gemaakt voordat SharePoint Multi-Geo-mogelijkheden algemeen beschikbaar werden op 27 maart 2019 en die SharePoint Multi-Geo niet hebben ingeschakeld in hun satellietlocatie(en). 

>[!Note]
>Als u na **27** maart een nieuwe geografische locatie hebt toegevoegd, hoeft u deze instructies niet uit te voeren, omdat uw nieuwe geografische locatie al is ingeschakeld voor OneDrive en SharePoint Multi-Geo.

Met deze instructies kunt u SharePoint inschakelen op uw satellietlocatie, zodat uw multi-geo satellietgebruikers kunnen profiteren van zowel OneDrive als SharePoint Multi-Geo mogelijkheden in O365. 

>[!IMPORTANT]
>Houd er rekening mee dat dit een enkele manier van inschakelen is. Nadat u de SPO-modus hebt ingesteld, kunt u uw tenant niet meer terugdraaien OneDrive alleen multi-geomodus zonder escalatie met ondersteuning. 

## <a name="to-set-a-geo-location-into-spo-mode"></a>Een geografische locatie instellen in de SPO-modus

Als u een geografische locatie wilt instellen in de SPO-modus, maakt u verbinding met de geografische locatie die u wilt instellen in de SPO-modus:

1.    Open uw SharePoint Online Management Shell 
2.    Connect-SPOService -URL "https://$tenantGeo-admin.sharepoint.com" -Credential $credential
3.    Set-SPOMultiGeoExperience</br></br>
![Set-SPOMultiGeoExperience](../media/Set-SPO-MultiGeo.jpg)
4.    Deze bewerking duurt meestal ongeveer een uur terwijl we verschillende publiceren backs in de service uitvoeren en uw tenant opnieuw stempelen. Voer na ten minste 1 uur een Get-SPOMultiGeoExperience uit.  Op deze manier kunt u zien of deze geografische locatie zich in de SPO-modus bevindt.</br></br>
![Set-SPOMultiGeoExperience](../media/Get-SPO-MultiGeo.jpg)

 
 
 
>[!Note]
>Bepaalde caches in de service-update worden elke 24 uur bijgewerkt, zodat het mogelijk is dat uw satelliet-geo zich voor een periode van maximaal 24 uur af en toe gedraagt alsof het zich nog in de ODB-modus heeft gedragen. Dit veroorzaakt geen technische problemen. 
 
Voor meer informatie over SharePoint Multi-Geo, raadpleegt u [aka.ms/sharepointmultigeo](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)


