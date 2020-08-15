---
title: Het netwerk instellen voor Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/19/2019
audience: ITPro
ms.topic: hub-page
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: ''
description: Hier vindt u koppelingen naar artikelen met informatie over het instellen van uw netwerk voor Microsoft 365, waaronder een overzicht van netwerkverbindingen en een lijst met eindpunten.
ms.openlocfilehash: f0e0499c70745d31399240372c190758285408aa
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689006"
---
# <a name="set-up-your-network-for-microsoft-365"></a>Het netwerk instellen voor Microsoft 365

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Een belangrijk onderdeel van uw Microsoft 365-onboarding is om ervoor te zorgen dat uw netwerk-en Internet verbindingen zijn ingesteld voor geoptimaliseerde toegang. Uw on-premises netwerk configureren voor toegang tot een globale Distributed software-as-a-Service (SaaS) Cloud wijkt af van een traditioneel netwerk dat is geoptimaliseerd voor verkeer naar on-premises datacenters en een centrale Internet verbinding. 

U kunt deze artikelen gebruiken om inzicht te krijgen in de belangrijkste verschillen en om uw edge-apparaten, clients en on-premises netwerk te wijzigen om de beste prestaties te verkrijgen voor uw on-premises gebruikers.

## <a name="how-microsoft-365-networking-works"></a>De werking van Microsoft 365-netwerken

Zie de volgende artikelen voor een overzicht van connectiviteit voor Microsoft 365:

- [Overzicht van Microsoft 365-netwerkconnectiviteit](microsoft-365-networking-overview.md)
- [Principes voor Microsoft 365-netwerkverbindingen](microsoft-365-network-connectivity-principles.md)
- [Microsoft 365-netwerkconnectiviteit beoordelen](assessing-network-connectivity.md)

Zie [netwerk planning en prestaties optimaliseren voor Microsoft 365](network-planning-and-performance.md)voor advies over het verbeteren van de prestaties.

## <a name="support-microsoft-365-networking-as-a-network-equipment-vendor"></a>Microsoft 365-netwerken ondersteunen als leverancier van netwerkapparatuur

Als u een leverancier van netwerkapparatuur bent, neemt u deel aan het [Office 365-programma](microsoft-365-networking-partner-program.md)voor de netwerk partner. Meld u aan bij het programma voor het maken van de principes van Office 365-netwerkverbindingen in uw producten en oplossingen. 

## <a name="office-365-endpoints"></a>Office 365-eindpunten

Eindpunten zijn de set doel-IP-adressen, DNS-domeinnamen en Url's voor Office 365-verkeer op internet. 

Voor het optimaliseren van de prestaties van de cloudservices van Office 365 moeten sommige eindpunten speciale functies hebben voor de clientbrowsers en de apparaten in het Edge-netwerk. Deze apparaten zijn firewalls, SSL-onderbreking en inspectie-en pakket controleapparaten, en systemen voor preventie van gegevensverlies.

Zie [Office 365-eindpunten beheren](managing-office-365-endpoints.md) voor de details.

Er zijn momenteel vijf verschillende Clouds van Office 365. In deze tabel vindt u een lijst met eindpunten voor elk item.

| Eindpunten | Beschrijving |
|:-------|:-----|
| [Wereldwijde eindpunten](urls-and-ip-address-ranges.md) | De eindpunten voor wereldwijde Office 365-abonnementen, waaronder de Verenigde Staten van de Cloud gemeenschappen van de overheid (GCC). |
| [U.S. Government DoD-eindpunten](microsoft-365-u-s-government-dod-endpoints.md) | De eindpunten voor de Nederlandse afdeling van de defensie (DoD). |
| [High-eindpunten van Amerikaanse overheid GCC](microsoft-365-u-s-government-gcc-high-endpoints.md) | De eindpunten voor de Verenigde Staten Government Community High (GCC High)-abonnementen. |
| [Office 365 beheerd door 21Vianet-eindpunten](urls-and-ip-address-ranges-21vianet.md) | De eindpunten van Office 365, beheerd door 21Vianet, dat is ontworpen om te voldoen aan de behoeften van Office 365 in China. |
| [Office 365 Duitsland-eindpunten](microsoft-365-germany-endpoints.md) | De eindpunten voor een aparte Cloud in Europa voor de meest gereglementeerde klanten in Duitsland, de Europese Unie (EU) en de Europese gratis Trade Association (EVA). |
|||

Als u de meest recente lijst met eindpunten voor uw Office 365-Cloud wilt automatiseren, raadpleegt u de [website IP Address and URL van office 365](microsoft-365-ip-web-service.md).

Voor extra eindpunten raadpleegt u de volgende artikelen:

- [Extra eindpunten die niet zijn opgenomen in de webservice](additional-office365-ip-addresses-and-urls.md)
- [Netwerkverzoeken in Office 2016 voor Mac](network-requests-in-office-2016-for-mac.md)


## <a name="additional-topics-for-microsoft-365-networking"></a>Meer onderwerpen voor Microsoft 365-netwerken

Zie de volgende artikelen voor gespecialiseerde onderwerpen in Microsoft 365-netwerken:

- [Netwerken voor content levering](content-delivery-networks.md)
- [IPv6-ondersteuning in Office 365-Services](ipv6-support.md)
- [NAT-ondersteuning met Office 365](nat-support-with-microsoft-365.md)

## <a name="expressroute-for-microsoft-365"></a>ExpressRoute voor Microsoft 365

Zie de volgende artikelen voor informatie over het gebruik van ExpressRoute voor Office 365-verkeer:

- [Azure ExpressRoute voor Office 365](azure-expressroute.md)
- [ExpressRoute voor Office 365 implementeren](implementing-expressroute.md)
- [Netwerk planning met ExpressRoute voor Office 365](network-planning-with-expressroute.md)
- [Routeren met ExpressRoute voor Office 365](routing-with-expressroute.md)
