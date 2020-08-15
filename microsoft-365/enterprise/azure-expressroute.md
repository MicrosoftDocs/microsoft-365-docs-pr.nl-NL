---
title: Azure ExpressRoute voor Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/5/2019
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 6d2534a2-c19c-4a99-be5e-33a0cee5d3bd
description: Meer informatie over het gebruik van Azure ExpressRoute met Office 365 en het plannen van het netwerkimplementatie project als u dit implementeert.
ms.openlocfilehash: 3691161767aba784039cbf317a51429c9ee6444c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688938"
---
# <a name="azure-expressroute-for-office-365"></a>Azure ExpressRoute voor Office 365

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Lees hoe Azure ExpressRoute wordt gebruikt met Office 365 en hoe u het netwerkimplementatie project moet plannen dat moet worden uitgevoerd als u Azure ExpressRoute implementeert voor gebruik met Office 365. Infrastructuur en platform services die worden uitgevoerd in azure, hebben vaak voordeel door de netwerkarchitectuur en de Prestatieoverwegingen te adresseren. We raden ExpressRoute voor Azure in deze gevallen aan. Software als service aanbiedingen zoals Office 365 en Dynamics 365 zijn gebouwd om veilig en betrouwbaar via internet toegankelijk te zijn. U kunt meer lezen over Internet prestaties en beveiliging en wanneer u in het artikel Azure ExpressRoute voor Office 365 in het artikel de [netwerkverbinding van office 365 Opoordeelt](assessing-network-connectivity.md).

> [!NOTE]
> Microsoft Authorization is vereist voor het gebruik van ExpressRoute voor Office 365. Microsoft beoordeelt elke klantaanvraag en verstuurt ExpressRoute voor Office 365 gebruik wanneer de wettelijke vereisten van de klant directe verbinding vereisen. Als u dergelijke vereisten hebt, dient u het tekstfragment en de webkoppeling naar de verordening te geven die u vertolkt om te betekenen dat directe verbinding is vereist in het [ExpressRoute voor Office 365 aanvraagformulier](https://aka.ms/O365ERReview) om een beoordeling van Microsoft te starten. Niet-geautoriseerde abonnementen bij het maken van routefilters voor Office 365 wordt een [foutbericht](https://support.microsoft.com/kb/3181709)weergegeven.

U kunt nu een directe netwerkverbinding met Office 365 toevoegen voor het geselecteerde netwerkverkeer van Office 365. Azure ExpressRoute biedt een directe verbinding, voorspelbare prestaties en levert een uptime-SLA van 99,95% voor de Microsoft-netwerkonderdelen. U hebt nog steeds een internetverbinding nodig voor services die niet worden ondersteund via Azure ExpressRoute.

## <a name="planning-azure-expressroute-for-office-365"></a>Planning van Azure ExpressRoute voor Office 365

Naast internetverbinding kunt u ook kiezen voor het routeren van een subset van het netwerkverkeer van Office 365 via een directe verbinding die voorspelbaar en een 99,95% uptime-overeenkomst biedt voor de Microsoft-netwerkonderdelen. Azure ExpressRoute biedt u de speciale netwerkverbinding met Office 365 en andere Microsoft-cloudservices.

Ongeacht of u een bestaand MPLS WAN hebt, kan ExpressRoute op drie manieren worden toegevoegd aan de netwerkarchitectuur. via een ondersteunde provider van de Cloud Exchange-Exchange, een Ethernet Point-to-Point-verbindingsprovider of via een MPLS-verbindingsprovider. Kijk welke [providers beschikbaar zijn in uw regio](https://azure.microsoft.com/documentation/articles/expressroute-locations/). De direct ExpressRoute-verbinding zorgt voor connectiviteit met de toepassingen die worden beschreven in [welke Office 365-Services zijn opgenomen?](azure-expressroute.md#BKMK_WhatDoIGet) hieronder. Netwerkverkeer voor alle overige toepassingen en services gaat verder met het internet.

In dit voorbeeld ziet u het volgende netwerkdiagram op hoog niveau met een typische Office 365-klant die verbinding maakt met de datacenters van Microsoft via internet voor toegang tot alle Microsoft-toepassingen, zoals Office 365, Windows Update en TechNet. Klanten gebruiken een vergelijkbaar netwerkpad, ongeacht of ze verbinding maken vanaf een on-premises netwerk of via een onafhankelijke internetverbinding.

![Netwerkconnectiviteit van Office 365](../media/9d8bc622-4a38-4a3b-a0f3-68657712d460.png)

Bekijk nu de bijgewerkte grafiek met een klant van Office 365 die de Internet-en ExpressRoute gebruiken om verbinding te maken met Office 365. In sommige verbindingen, zoals openbare DNS en netwerkknooppunten voor de levering, is de openbare internetverbinding nog steeds vereist. U zult ook merken dat de gebruikers van de klant die zich niet bevinden in hun verbonden gebouw van ExpressRoute, verbinding maken via internet.

![Office 365-connectiviteit met ExpressRoute](../media/251788c4-0937-4584-9b2c-df08e11611fc.png)

Wilt u nog meer weten? Meer informatie over het [beheren van uw netwerkverkeer met Azure ExpressRoute voor office 365](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408) en informatie over het [configureren van Azure ExpressRoute voor Office 365](https://azure.microsoft.com/documentation/articles/expressroute-faqs/). We hebben ook een 10 onderdeel [van Azure ExpressRoute voor Office 365-training](https://channel9.msdn.com/series/aer) reeks in kanaal 9 opgenomen, zodat u de concepten uitgebreider kunt uitleggen.

## <a name="what-office-365-services-are-included"></a>Welke Office 365-Services zijn opgenomen?
<a name="BKMK_WhatDoIGet"> </a>

In de volgende tabel vindt u de Office 365-services die worden ondersteund via ExpressRoute. Zie het [artikel Office 365-eindpunten](https://aka.ms/o365endpoints) voor informatie over de netwerkaanvragen voor deze toepassingen, internetconnectiviteit vereist.

|**Inbegrepen toepassingen**|
|:-----|
|Exchange Online<sup>1</sup> <br/> Exchange Online Protection<sup>1</sup> <br/> Delve<sup>1</sup> <br/> |
|Skype voor bedrijven online<sup>1</sup> <br/> Microsoft teams <sup>1</sup> <br/> |
|SharePoint Online<sup>1</sup> <br/> OneDrive voor bedrijven<sup>1</sup> <br/> Project online<sup>1</sup> <br/> |
|Portal en gedeelde<sup>1</sup> <br/> Azure Active Directory (Azure AD) <sup>1</sup> <br/> Azure AD Connect<sup>1</sup> <br/> Office<sup>1</sup> <br/> |

<sup>1</sup> voor elk van deze toepassingen gelden verbindings vereisten voor internetverbindingen die niet worden ondersteund via ExpressRoute, zie het [artikel Office 365-eindpunten](https://aka.ms/o365endpoints) voor meer informatie.

De services die niet zijn opgenomen in ExpressRoute voor Office 365 zijn Microsoft 365-apps for Enterprise Client downloads, on-premises Identity provider Sign-in en de Office 365-service (beheerd door 21 ViaNet) in China.

## <a name="implementing-expressroute-for-office-365"></a>ExpressRoute voor Office 365 implementeren

Voor de implementatie van ExpressRoute is de betrokkenheid van netwerk-en toepassings eigenaren vereist en moet de planning van de nieuwe [netwerk routerings architectuur](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408), de bandbreedtevereisten, waar de beveiliging wordt geïmplementeerd, hoge beschikbaarheid, enzovoort. Als u ExpressRoute wilt implementeren, moet u het volgende doen:

1. Volledig inzicht in de benodigde ExpressRoute voldoet aan de planning van Office 365-verbindingen. Meer informatie over de toepassingen die gebruikmaken van Internet-of ExpressRoute en de behoeften van uw netwerk, beveiliging en hoge beschikbaarheid plannen in de context van het gebruik van Internet-en ExpressRoute voor Office 365-verkeer.

2. De ontwaarde en peering locaties voor Internet-en ExpressRoute-verkeer<sup>1</sup>bepalen.

3. De vereiste capaciteit bepalen op de Internet-en ExpressRoute-verbindingen.

4. Zorg voor een plan voor de implementatie van de beveiliging en van andere standaard perimeter besturingselementen<sup>1</sup>.

5. U hebt een geldig Microsoft Azure-account om u aan te melden bij ExpressRoute.

6. Selecteer een verbindings model en een [erkend provider](https://azure.microsoft.com/documentation/articles/expressroute-locations/). Houd er rekening mee dat klanten meerdere verbindings modellen of partners kunnen selecteren en de partner niet hoeft te zijn als uw bestaande netwerkprovider.

7. Implementatie valideren voordat verkeer naar ExpressRoute wordt geleid.

8. [Implementeer QoS](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d) optioneel en evalueer de regionale expansie.

<sup>1</sup> belangrijke Prestatieoverwegingen. Dit kan drastische gevolgen hebben voor de latentie, wat essentieel is voor toepassingen zoals Skype voor bedrijven.

Gebruik voor Aanvullende naslaginformatie onze [routerings gids](https://support.office.com/article/Routing-with-ExpressRoute-for-Office-365-e1da26c6-2d39-4379-af6f-4da213218408) naast de [documentatie van ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-introduction/).

Voor de aankoop van ExpressRoute voor Office 365 moet u met een of meer [goedgekeurde providers](https://azure.microsoft.com/documentation/articles/expressroute-locations/) samenwerken met een ExpressRoute Premium-abonnement. U kunt geen extra licenties kopen in Office 365.

Met deze korte koppeling kunt u teruggaan: [https://aka.ms/expressrouteoffice365](https://aka.ms/expressrouteoffice365)

Klaar om u aan te melden voor [ExpressRoute voor Office 365](https://aka.ms/ert)?

## <a name="related-topics"></a>Verwante onderwerpen

[Een beoordeling van de netwerkverbinding van Office 365](assessing-network-connectivity.md)

[ExpressRoute voor Office 365-connectiviteit beheren](managing-expressroute-for-connectivity.md)

[Routeren met ExpressRoute voor Office 365](routing-with-expressroute.md)

[Netwerk planning met ExpressRoute voor Office 365](network-planning-with-expressroute.md)

[ExpressRoute voor Office 365 implementeren](implementing-expressroute.md)

[Het gebruik van BGP-community's in ExpressRoute voor Office 365-scenario's](bgp-communities-in-expressroute.md)

[Media kwaliteit en prestaties van de netwerkverbinding in Skype voor bedrijven online](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)

[Prestaties afstemmen van Office 365 met basislijnen en prestatie geschiedenis](performance-tuning-using-baselines-and-history.md)

[Prestatieproblemen met het plannen van Office 365](performance-troubleshooting-plan.md)

[URL's en IP-adresbereiken voor Office 365](urls-and-ip-address-ranges.md)

[Office 365 netwerk en prestaties optimaliseren](network-planning-and-performance.md)

## <a name="see-also"></a>Zie ook

[Overzicht van Microsoft 365 Enterprise](microsoft-365-overview.md)
