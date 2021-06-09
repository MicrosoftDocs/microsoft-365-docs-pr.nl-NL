---
title: Uw netwerk instellen voor Microsoft 365
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
description: Vind koppelingen naar artikelen met informatie om u te helpen uw netwerk in te stellen voor Microsoft 365, waaronder een overzicht van netwerkconnectiviteit en een lijst met eindpunten.
ms.openlocfilehash: f0e0499c70745d31399240372c190758285408aa
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689006"
---
# <a name="set-up-your-network-for-microsoft-365"></a>Uw netwerk instellen voor Microsoft 365

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Een belangrijk onderdeel van uw Microsoft 365 onboarding is ervoor te zorgen dat uw netwerk en internetverbinding zijn ingesteld voor geoptimaliseerde toegang. Het configureren van uw on-premises netwerk om toegang te krijgen tot een saas-cloud (Software-as-a-Service) die wereldwijd wordt gedistribueerd, verschilt van een traditioneel netwerk dat is geoptimaliseerd voor verkeer naar on-premises datacenters en een centrale internetverbinding. 

Gebruik deze artikelen om de belangrijkste verschillen te begrijpen en om uw edge-apparaten, clientcomputers en on-premises netwerk te wijzigen om de beste prestaties te krijgen voor uw on-premises gebruikers.

## <a name="how-microsoft-365-networking-works"></a>Hoe Microsoft 365 netwerken werkt

Zie deze artikelen voor een overzicht van connectiviteit voor Microsoft 365:

- [Overzicht van netwerkverbindingen voor Microsoft 365](microsoft-365-networking-overview.md)
- [Beginselen voor Microsoft 365-netwerkverbindingen](microsoft-365-network-connectivity-principles.md)
- [Microsoft 365-netwerkverbindingen evalueren](assessing-network-connectivity.md)

Zie Netwerkplanning en prestatieafstemming voor meer [Microsoft 365.](network-planning-and-performance.md)

## <a name="support-microsoft-365-networking-as-a-network-equipment-vendor"></a>Ondersteuning Microsoft 365 netwerken als leverancier van netwerkapparatuur

Als u een leverancier van netwerkapparatuur bent, kunt u deelnemen aan [de Office 365 Networking Partner Program.](microsoft-365-networking-partner-program.md) Schrijf u in voor het programma om Office 365 netwerkconnectiviteitsprincipes in te bouwen in uw producten en oplossingen. 

## <a name="office-365-endpoints"></a>Office 365-eindpunten

Eindpunten zijn de set doel-IP-adressen, DNS-domeinnamen en URL's voor Office 365 internetverkeer. 

Als u de prestaties wilt optimaliseren Office 365 cloudservices, hebben sommige eindpunten speciale verwerking nodig door uw clientbrowsers en de apparaten in uw edge-netwerk. Deze apparaten omvatten firewalls, SSL-apparaten voor het breken en controleren en controleren van pakketten en preventiesystemen voor gegevensverlies.

Zie [Beheer Office 365 eindpunten](managing-office-365-endpoints.md) voor de details.

Er zijn momenteel vijf verschillende Office 365 wolken. Met deze tabel gaat u naar de lijst met eindpunten voor elk eindpunt.

| Eindpunten | Beschrijving |
|:-------|:-----|
| [Wereldwijde eindpunten](urls-and-ip-address-ranges.md) | De eindpunten voor wereldwijde Office 365 abonnementen, waaronder de Verenigde Staten Government Community Cloud (GCC). |
| [Eindpunten voor U.S. Government DoD](microsoft-365-u-s-government-dod-endpoints.md) | De eindpunten voor abonnementen van het Amerikaanse ministerie van Defensie (DoD). |
| [Eindpunten voor U.S. Government GCC High](microsoft-365-u-s-government-gcc-high-endpoints.md) | De eindpunten voor amerikaanse Government Community Cloud High (GCC High) abonnementen. |
| [Office 365 beheerd door 21Vianet-eindpunten](urls-and-ip-address-ranges-21vianet.md) | De eindpunten voor Office 365 beheerd door 21Vianet, dat is ontworpen om te voldoen aan de behoeften voor Office 365 in China. |
| [Office 365 eindpunten Germany-eindpunten](microsoft-365-germany-endpoints.md) | De eindpunten voor een afzonderlijke cloud in Europa voor de meest gereguleerde klanten in Duitsland, de Europese Unie (EU) en de European Free Trade Association (EFTA). |
|||

Als u het verkrijgen van de meest recente lijst met eindpunten voor uw Office 365 cloud wilt automatiseren, bekijkt u de Office 365 [IP-adres en URL-webservice.](microsoft-365-ip-web-service.md)

Zie deze artikelen voor meer eindpunten:

- [Aanvullende eindpunten die niet zijn opgenomen in de webservice](additional-office365-ip-addresses-and-urls.md)
- [Netwerkaanvragen in Office 2016 voor Mac](network-requests-in-office-2016-for-mac.md)


## <a name="additional-topics-for-microsoft-365-networking"></a>Aanvullende onderwerpen voor Microsoft 365 netwerken

Zie deze artikelen voor gespecialiseerde onderwerpen in Microsoft 365 netwerken:

- [Netwerken voor contentlevering](content-delivery-networks.md)
- [IPv6-ondersteuning in Office 365-services](ipv6-support.md)
- [Ondersteuning voor NAT met Office 365](nat-support-with-microsoft-365.md)

## <a name="expressroute-for-microsoft-365"></a>ExpressRoute voor Microsoft 365

Zie deze artikelen voor informatie over het gebruik van ExpressRoute voor Office 365 verkeer:

- [Azure ExpressRoute voor Office 365](azure-expressroute.md)
- [ExpressRoute implementeren voor Office 365](implementing-expressroute.md)
- [Netwerkplanning met ExpressRoute voor Office 365](network-planning-with-expressroute.md)
- [Routeren met ExpressRoute voor Office 365](routing-with-expressroute.md)
