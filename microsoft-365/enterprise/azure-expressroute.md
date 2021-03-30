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
description: Meer informatie over het gebruik van Azure ExpressRoute met Office 365 en het plannen van het netwerkuitvoeringsproject als u er mee implementeert.
ms.openlocfilehash: 9af9a2981c9220784725284aa602cf2de66721e5
ms.sourcegitcommit: c75aac39ee8d93218a79585113ef6b36f47c9ddf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/29/2021
ms.locfileid: "51408369"
---
# <a name="azure-expressroute-for-office-365"></a>Azure ExpressRoute voor Office 365

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Lees hoe Azure ExpressRoute wordt gebruikt met Office 365 en hoe u het netwerkuitvoeringsproject kunt plannen dat vereist is als u Azure ExpressRoute implementeert voor gebruik met Office 365. Infrastructuur- en platformservices die in Azure worden uitgevoerd, profiteren vaak door aandacht te vragen voor netwerkarchitectuur en prestatieoverwegingen. In deze gevallen raden we ExpressRoute voor Azure aan. Software as a Service-aanbiedingen zoals Office 365 en Dynamics 365 zijn gebouwd om veilig en betrouwbaar te kunnen worden gebruikt via internet. U kunt lezen over de prestaties en beveiliging van internet en wanneer u Azure ExpressRoute voor Office 365 kunt overwegen in het artikel De netwerkconnectiviteit van [Office 365 beoordelen.](assessing-network-connectivity.md)

> [!NOTE]
> Microsoft Defender voor Eindpunt wordt niet ondersteund in Azure Express Route.

> [!NOTE]
> Microsoft-autorisatie is vereist voor het gebruik van ExpressRoute voor Office 365. Microsoft controleert elke klantaanvraag en autoreert ExpressRoute voor Office 365-gebruik wanneer de wettelijke vereisten van een klant directe connectiviteit verplicht stellen. Als u dergelijke vereisten hebt, geeft u het tekstfragment en de webkoppeling op naar de verordening die u interpreteert om te betekenen dat directe connectiviteit vereist is in het ExpressRoute voor [Office 365-aanvraagformulier](https://aka.ms/O365ERReview) om een Microsoft-beoordeling te starten. Ongeautoriseerde abonnementen die routefilters voor Office 365 proberen te maken, ontvangen een [foutbericht.](https://support.microsoft.com/kb/3181709)

U kunt nu een directe netwerkverbinding toevoegen aan Office 365 voor geselecteerd Office 365-netwerkverkeer. Azure ExpressRoute biedt een directe verbinding, voorspelbare prestaties en wordt geleverd met een UPTIME SLA van 99,95% voor de Microsoft-netwerkonderdelen. U hebt nog steeds een internetverbinding nodig voor services die niet worden ondersteund via Azure ExpressRoute.

## <a name="planning-azure-expressroute-for-office-365"></a>Azure ExpressRoute plannen voor Office 365

Naast internetconnectiviteit kunt u ervoor kiezen om een subset van hun Office 365-netwerkverkeer te routen via een directe verbinding die voorspelbaarheid en een SLA van 99,95% uptime biedt voor de Microsoft-netwerkonderdelen. Azure ExpressRoute biedt u deze speciale netwerkverbinding met Office 365 en andere Microsoft-cloudservices.

ExpressRoute kan op drie manieren worden toegevoegd aan uw netwerkarchitectuur, ongeacht of u een bestaand MPLS WAN hebt. via een ondersteunde cloud exchange-colocatieprovider, een Ethernet-point-to-point-verbindingsprovider of via een MPLS-verbindingsprovider. Bekijk welke [providers beschikbaar zijn in uw regio.](/azure/expressroute/expressroute-locations) Met de directe ExpressRoute-verbinding kunt u verbinding maken met de toepassingen die worden beschreven in [Welke Office 365-services zijn opgenomen? hieronder.](azure-expressroute.md#BKMK_WhatDoIGet) Netwerkverkeer voor alle andere toepassingen en services blijft via internet lopen.

Houd rekening met het volgende netwerkdiagram op hoog niveau, waarin een normale Office 365-klant via internet verbinding maakt met de datacenters van Microsoft voor toegang tot alle Microsoft-toepassingen, zoals Office 365, Windows Update en TechNet. Klanten gebruiken een vergelijkbaar netwerkpad, ongeacht of ze verbinding maken via een on-premises netwerk of via een onafhankelijke internetverbinding.

![Office 365-netwerkconnectiviteit](../media/9d8bc622-4a38-4a3b-a0f3-68657712d460.png)

Bekijk nu het bijgewerkte diagram met een Office 365-klant die zowel internet als ExpressRoute gebruikt om verbinding te maken met Office 365. Voor sommige verbindingen, zoals openbare DNS- en Content Delivery Network-knooppunten, is nog steeds de openbare internetverbinding vereist. U ziet ook dat de gebruikers van de klant die zich niet in het met ExpressRoute verbonden gebouw bevinden, verbinding maken via internet.

![Office 365-connectiviteit met ExpressRoute](../media/251788c4-0937-4584-9b2c-df08e11611fc.png)

Wilt u nog steeds meer informatie? Meer informatie over het beheren van uw netwerkverkeer [met Azure ExpressRoute voor Office 365](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408) en informatie over het configureren van [Azure ExpressRoute voor Office 365.](/azure/expressroute/expressroute-faqs) We hebben ook een 10-delige Azure ExpressRoute voor [Office 365-trainingsreeks](https://channel9.msdn.com/series/aer) opgenomen op Kanaal 9 om de concepten beter uit te leggen.

## <a name="what-office-365-services-are-included"></a>Welke Office 365-services zijn inbegrepen?
<a name="BKMK_WhatDoIGet"> </a>

De volgende tabel bevat de Office 365-services die worden ondersteund via ExpressRoute. Bekijk het [Artikel met Office 365-eindpunten](./urls-and-ip-address-ranges.md) om te begrijpen welke netwerkaanvragen voor deze toepassingen een internetverbinding vereisen.

|**Toepassingen inbegrepen**|
|:-----|
|Exchange Online<sup>1</sup> <br/> Exchange Online Protection<sup>1</sup> <br/> Delve<sup>1</sup> <br/> |
|Skype voor Bedrijven Online<sup>1</sup> <br/> Microsoft Teams <sup>1</sup> <br/> |
|SharePoint Online<sup>1</sup> <br/> OneDrive voor Bedrijven<sup>1</sup> <br/> Project Online<sup>1</sup> <br/> |
|Portal en gedeelde<sup>1</sup> <br/> Azure Active Directory (Azure AD) <sup>1</sup> <br/> Azure AD Connect<sup>1</sup> <br/> Office<sup>1</sup> <br/> |

<sup>1</sup> Voor elk van deze toepassingen worden internetconnectiviteitsvereisten niet ondersteund via ExpressRoute, zie het [Office 365-eindpunten-artikel](./urls-and-ip-address-ranges.md) voor meer informatie.

De services die niet zijn opgenomen in ExpressRoute voor Office 365, zijn Microsoft 365 Apps voor het downloaden van zakelijke client, Aanmelding van on-premises identiteitsprovider en Office 365-service (beheerd door 21 Vianet) in China.

## <a name="implementing-expressroute-for-office-365"></a>ExpressRoute implementeren voor Office 365

De implementatie van ExpressRoute vereist de betrokkenheid van netwerk- [](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408)en toepassingseigenaren en vereist zorgvuldige planning om de nieuwe netwerkrouteringsarchitectuur, bandbreedtevereisten, waar beveiliging wordt geïmplementeerd, hoge beschikbaarheid, en ga zo maar door. Als u ExpressRoute wilt implementeren, moet u het volgende doen:

1. Volledig inzicht in de behoefte die ExpressRoute aan uw Office 365-connectiviteitsplanning voldoet. Begrijp welke toepassingen internet of ExpressRoute gebruiken en plan uw netwerkcapaciteit, beveiliging en hoge beschikbaarheidsbehoeften volledig in de context van het gebruik van zowel internet- als ExpressRoute-verkeer voor Office 365-verkeer.

2. Bepaal de uitgangs- en peeringlocaties voor zowel internet- als ExpressRoute-verkeer<sup>1.</sup>

3. Bepaal de vereiste capaciteit op internet- en ExpressRoute-verbindingen.

4. Hebt u een plan voor het implementeren van beveiliging en andere standaardperimeterbesturingselementen<sup>1</sup>.

5. Een geldig Microsoft Azure-account hebben om u te abonneren op ExpressRoute.

6. Selecteer een connectiviteitsmodel en een [goedgekeurde provider.](/azure/expressroute/expressroute-locations) Houd er rekening mee dat klanten meerdere connectiviteitsmodellen of partners kunnen selecteren en dat de partner niet hetzelfde hoeft te zijn als uw bestaande netwerkprovider.

7. Valideer de implementatie voordat het verkeer wordt doorgestuurd naar ExpressRoute.

8. U kunt [QoS desgewenst implementeren en](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d) regionale uitbreiding evalueren.

<sup>1</sup> Belangrijke prestatieoverwegingen. Beslissingen hier kunnen een grote invloed hebben op latentie, wat essentieel is voor toepassingen zoals Skype voor Bedrijven.

Gebruik onze routeringshandleiding naast de [ExpressRoute-documentatie](/azure/expressroute/expressroute-introduction)voor aanvullende verwijzingen. [](https://support.office.com/article/Routing-with-ExpressRoute-for-Office-365-e1da26c6-2d39-4379-af6f-4da213218408)

Als u ExpressRoute voor Office 365 wilt kopen, moet u samenwerken met een of meer goedgekeurde [providers](/azure/expressroute/expressroute-locations) om het gewenste nummer- en groottecircuit in te stellen met een ExpressRoute Premium-abonnement. Er zijn geen extra licenties om te kopen bij Office 365.

Met deze korte koppeling kunt u teruggaan: [https://aka.ms/expressrouteoffice365]()

Wilt u zich aanmelden voor [ExpressRoute voor Office 365?](https://aka.ms/ert)

## <a name="related-topics"></a>Verwante onderwerpen

[Office 365-netwerkverbinding beoordelen](assessing-network-connectivity.md)

[ExpressRoute voor Office 365-connectiviteit beheren](managing-expressroute-for-connectivity.md)

[Routeren met ExpressRoute voor Office 365](routing-with-expressroute.md)

[Netwerkplanning met ExpressRoute voor Office 365](network-planning-with-expressroute.md)

[ExpressRoute implementeren voor Office 365](implementing-expressroute.md)

[BGP-community's gebruiken in ExpressRoute voor Office 365-scenario's](bgp-communities-in-expressroute.md)

[Mediakwaliteit en prestaties van de netwerkverbinding in Skype voor Bedrijven Online](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)

[Office 365-prestatieafstemming met behulp van basislijnen en prestatiegeschiedenis](performance-tuning-using-baselines-and-history.md)

[Prestatieproblemen met Office 365 oplossen: planning](performance-troubleshooting-plan.md)

[URL's en IP-adresbereiken voor Office 365](urls-and-ip-address-ranges.md)

[Aanpassing van Office 365-netwerk en -prestaties](network-planning-and-performance.md)

## <a name="see-also"></a>Zie ook

[Overzicht van Microsoft 365 Enterprise](microsoft-365-overview.md)
