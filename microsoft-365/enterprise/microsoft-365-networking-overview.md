---
title: Overzicht van netwerkverbindingen voor Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/23/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- m365initiative-coredeploy
f1.keywords:
- NOCSH
description: Bespreekt waarom netwerkoptimalisatie belangrijk is voor SaaS-services, het doel van Microsoft 365 netwerken en hoe SaaS andere netwerken vereist dan andere werkbelastingen.
ms.openlocfilehash: d1a2b79f6e4042b97ec5a31d0ff92175baa1218e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923180"
---
# <a name="microsoft-365-network-connectivity-overview"></a>Microsoft 365 overzicht van netwerkconnectiviteit

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Microsoft 365 is een gedistribueerde SaaS-cloud (Software-as-a-Service) die productiviteits- en samenwerkingsscenario's biedt via diverse microservices en toepassingen. Clientonderdelen van Microsoft 365 zoals Outlook, Word en PowerPoint worden uitgevoerd op gebruikerscomputers en maken verbinding met andere onderdelen van Microsoft 365 die worden uitgevoerd in Microsoft-datacenters. De belangrijkste factor die de kwaliteit van de Microsoft 365 eindgebruikerservaring bepaalt, is netwerkbetrouwbaarheid en lage latentie tussen Microsoft 365 clients en Microsoft 365 servicedeuren.

In dit artikel leert u over de doelstellingen van Microsoft 365 netwerken en waarom voor Microsoft 365 netwerken een andere benadering voor optimalisatie is vereist dan algemeen internetverkeer.

## <a name="microsoft-365-networking-goals"></a>Microsoft 365 netwerkdoelen

Het uiteindelijke doel van Microsoft 365 netwerken is het optimaliseren van de eindgebruikerservaring door de minst beperkende toegang in te stellen tussen clients en de dichtstbijzijnde Microsoft 365 eindpunten. De kwaliteit van de eindgebruikerservaring is rechtstreeks gerelateerd aan de prestaties en reactiesnelheid van de toepassing die de gebruiker gebruikt. Microsoft Teams is bijvoorbeeld afhankelijk van een lage latentie, zodat telefoongesprekken, vergaderingen en gedeelde schermsamenwerkingen van gebruikers probleemloos zijn en Outlook afhankelijk is van goede netwerkconnectiviteit voor directe zoekfuncties die gebruikmaken van indexering aan de server en AI-mogelijkheden.

Het primaire doel in het netwerkontwerp moet zijn om de latentie te minimaliseren door de retourtijd (RTT) te verkorten van clientapparaten naar het Microsoft Global Network, de openbare netwerk backbone van Microsoft die alle datacenters van Microsoft verbindt met lage latentie, toegangspunten voor cloudtoepassing met hoge beschikbaarheid, verspreid over de hele wereld. U kunt meer lezen over het Microsoft Global Network op [Hoe Microsoft zijn snelle en betrouwbare wereldwijde netwerk opbouwt](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/).

Het optimaliseren Microsoft 365 netwerkprestaties hoeft niet ingewikkeld te zijn. U kunt de best mogelijke prestaties krijgen door een paar belangrijke principes te volgen:

- Netwerkverkeer Microsoft 365 identificeren
- Lokale vertakking van netwerkverkeer Microsoft 365 internet toestaan vanaf elke locatie waar gebruikers verbinding maken met Microsoft 365
- Toestaan Microsoft 365 om proxies en pakketcontroleapparaten te omzeilen

Zie voor meer informatie over Microsoft 365 netwerkconnectiviteitsprincipes [Microsoft 365 Netwerkconnectiviteitsbeginselen.](microsoft-365-network-connectivity-principles.md)

## <a name="traditional-network-architectures-and-saas"></a>Traditionele netwerkarchitectuur en SaaS

Traditionele netwerkarchitectuurprincipes voor client-/serverbelastingen zijn ontworpen rond de aanname dat het verkeer tussen clients en eindpunten niet buiten de bedrijfsnetwerkperimeter wordt uitgebreid. In veel bedrijfsnetwerken lopen alle uitgaande internetverbindingen door het bedrijfsnetwerk en lopen ze van een centrale locatie af.

In traditionele netwerkarchitectuur is een hogere latentie voor algemeen internetverkeer een noodzakelijke afweging om de beveiliging van de netwerkperimeter te behouden, en bij het optimaliseren van de prestaties voor internetverkeer moet de apparatuur meestal worden ge-upgraden of opgeschaald op netwerkovertredingspunten. Deze benadering voldoet echter niet aan de vereisten voor optimale netwerkprestaties van SaaS-services, zoals Microsoft 365.

## <a name="identifying-microsoft-365-network-traffic"></a>Netwerkverkeer Microsoft 365 identificeren

We maken het gemakkelijker om het netwerkverkeer Microsoft 365 te identificeren en het eenvoudiger te maken om de netwerkidentificatie te beheren.

- Nieuwe categorieën netwerk-eindpunten om zeer kritieke netwerkverkeer te onderscheiden van netwerkverkeer dat niet wordt beïnvloed door internetlatentie. Er zijn slechts een paar URL's en ondersteunende IP-adressen in de meest kritieke categorie 'Optimaliseren'.
- Webservices voor scriptgebruik of directe apparaatconfiguratie en wijzigingsbeheer van Microsoft 365 netwerkidentificatie. Wijzigingen zijn beschikbaar via de webservice of in de RSS-indeling of via e-mail met een Microsoft Flow sjabloon.
- [Office 365 netwerkpartnerprogramma](./microsoft-365-networking-partner-program.md) met Microsoft-partners die apparaten of services leveren die Microsoft 365 netwerkconnectiviteitsprincipes volgen en eenvoudige configuratie hebben.

## <a name="securing-microsoft-365-connections"></a>Verbinding Microsoft 365 beveiligen

Het doel van traditionele netwerkbeveiliging is om de perimeter van het bedrijfsnetwerk te beschermen tegen indringing en kwaadwillende exploits. De meeste bedrijfsnetwerken dwingen netwerkbeveiliging af voor internetverkeer met behulp van technologieën zoals proxyservers, firewalls, SSL-onderbreking en -inspectie, deep packet-inspectie en preventiesystemen voor gegevensverlies. Deze technologieën bieden belangrijke risicobeperkingen voor algemene internetverzoeken, maar kunnen de prestaties, schaalbaarheid en kwaliteit van de eindgebruikerservaring drastisch verminderen wanneer ze worden toegepast op Microsoft 365-eindpunten.

Microsoft 365 helpt tegemoet te komen aan de behoeften van uw organisatie voor inhoudsbeveiliging en naleving van gegevensgebruik met ingebouwde beveiligings- en beheerfuncties die speciaal zijn ontworpen voor Microsoft 365 functies en werkbelastingen. Zie de routekaart voor Microsoft 365 beveiliging en naleving [Office 365 voor meer informatie.](/office365/securitycompliance/security-roadmap) Zie Netwerkapparaten of oplossingen van derden gebruiken voor Office 365-verkeer voor meer informatie over de aanbevelingen en ondersteuningspositie van Microsoft voor geavanceerde netwerkoplossingen die geavanceerde verwerking op Microsoft 365-verkeer [uitvoeren.](https://support.microsoft.com/help/2690045)

## <a name="why-is-microsoft-365-networking-different"></a>Waarom is Microsoft 365 netwerk anders?

Microsoft 365 is ontworpen voor optimale prestaties met behulp van eindpuntbeveiliging en versleutelde netwerkverbindingen, waardoor de perimeterbeveiliging minder nodig is. Microsoft 365 datacenters bevinden zich over de hele wereld en de service is ontworpen om verschillende methoden te gebruiken voor het verbinden van clients met de best beschikbare service-eindpunten. Aangezien gebruikersgegevens en -verwerking worden verdeeld over veel Microsoft-datacenters, is er geen enkel netwerk-eindpunt waarmee clientapparaten verbinding kunnen maken. In feite worden gegevens en services in uw Microsoft 365-tenant dynamisch geoptimaliseerd door het Microsoft Global Network om zich aan te passen aan de geografische locaties waaruit ze worden gebruikt door eindgebruikers.

Bepaalde veelvoorkomende prestatieproblemen worden gemaakt Microsoft 365 het verkeer onderworpen is aan pakketcontrole en gecentraliseerde uittreding:

- Hoge latentie kan leiden tot zeer slechte prestaties van video- en audiostreams, en trage reactie van het ophalen van gegevens, zoekopdrachten, realtime samenwerking, agenda-vrije/drukke informatie, inhoud in het product en andere services
- Het weglaten van verbindingen vanaf een centrale locatie verslaat de dynamische routeringsmogelijkheden van het Microsoft 365 globale netwerk, wat latentie en retourtijd toevoegt
- Het ontsleutelen van SSL Microsoft 365 netwerkverkeer en het opnieuw versleutelen kan protocolfouten veroorzaken en heeft beveiligingsrisico's

Door het netwerkpad naar Microsoft 365 toegangspunten te verkorten door clientverkeer zo dicht mogelijk bij de geografische locatie te laten lopen, kunnen de connectiviteitsprestaties en de ervaring van de eindgebruiker in Microsoft 365. Het kan ook helpen om de impact van toekomstige wijzigingen in de netwerkarchitectuur op Microsoft 365 prestaties en betrouwbaarheid te verminderen. Het optimale connectiviteitsmodel is om altijd netwerkafloop op de locatie van de gebruiker aan te bieden, ongeacht of dit zich op het bedrijfsnetwerk of op externe locaties bevindt, zoals thuis, hotels, coffeeshops en luchthavens. Algemeen internetverkeer en wan-gebaseerd bedrijfsnetwerkverkeer worden afzonderlijk gerouteerd en gebruiken niet het lokale directe uitgangsmodel. Dit lokale directe uitgangsmodel wordt weergegeven in het onderstaande diagram.

![Netwerkarchitectuur voor lokaal uitgaand verkeer](../media/6bc636b0-1234-4ceb-a45a-aadd1044b39c.png)

De lokale uitgangsarchitectuur heeft de volgende voordelen voor Microsoft 365 netwerkverkeer ten opzichte van het traditionele model:
  
- Biedt optimale Microsoft 365-prestaties door de lengte van de route te optimaliseren. Eindgebruikersverbindingen worden dynamisch doorgeleid naar het dichtstbijzijnde Microsoft 365-toegangspunt door de _Infrastructuur_ voor gedistribueerde service voor de deur van het Microsoft Global Network en het verkeer wordt vervolgens intern gerouteerd naar gegevens- en service-eindpunten via de uiterst lage latentie van Microsoft.
- Vermindert de belasting van de bedrijfsnetwerkinfrastructuur door lokale uittreding toe te staan Microsoft 365 verkeer, door proxies en controleapparaten voor verkeer te omzeilen.
- Beveiligt verbindingen aan beide uiteinden door gebruik te maken van client-eindpuntbeveiligings- en cloudbeveiligingsfuncties, waardoor de toepassing van redundante netwerkbeveiligingstechnologieën wordt vermeden.

> [!NOTE]
> De _infrastructuur voor gedistribueerde service voor_ de deur is de zeer beschikbare en schaalbare netwerkrand van het Microsoft Global Network met geografisch verspreide locaties. De verbinding met eindgebruikers wordt beëindigd en efficiënt gerouteerd binnen het Microsoft Global Network. U kunt meer lezen over het Microsoft Global Network op [Hoe Microsoft zijn snelle en betrouwbare wereldwijde netwerk opbouwt](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/).

Zie voor meer informatie over het begrijpen en toepassen van Microsoft 365 netwerkconnectiviteitsprincipes [Microsoft 365 Netwerkconnectiviteitsbeginselen.](microsoft-365-network-connectivity-principles.md)

## <a name="conclusion"></a>Conclusie

Het optimaliseren Microsoft 365 netwerkprestaties komt echt neer op het verwijderen van onnodige belemmeringen. Door Microsoft 365 verbindingen te behandelen als vertrouwd verkeer, kunt u voorkomen dat latentie wordt geïntroduceerd door pakketcontrole en concurrentie voor proxybandbreedte. Door lokale verbindingen tussen clientapparaten en Office 365 eindpunten toe te staan, kan verkeer dynamisch worden gerouteerd via het Microsoft Global Network.

## <a name="related-topics"></a>Verwante onderwerpen

[Microsoft 365 Beginselen van netwerkconnectiviteit](microsoft-365-network-connectivity-principles.md)

[Office 365-eindpunten beheren](managing-office-365-endpoints.md)

[URL's en IP-adresbereiken voor Office 365](urls-and-ip-address-ranges.md)

[IP-adres en URL-webservice van Office 365](microsoft-365-ip-web-service.md)

[Microsoft 365-netwerkverbindingen evalueren](assessing-network-connectivity.md)

[Netwerkplanning en prestaties optimaliseren voor Microsoft 365](network-planning-and-performance.md)

[Office 365-prestatieafstemming met behulp van basislijnen en prestatiegeschiedenis](performance-tuning-using-baselines-and-history.md)

[Prestatieproblemen met Office 365 oplossen: planning](performance-troubleshooting-plan.md)

[Netwerken voor contentlevering](content-delivery-networks.md)

[Microsoft 365-connectiviteitstest](https://aka.ms/netonboard)

[Hoe Microsoft zijn snelle en betrouwbare wereldwijde netwerk opbouwt](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/)

[Office 365-netwerkblog](https://techcommunity.microsoft.com/t5/Office-365-Networking/bd-p/Office365Networking)