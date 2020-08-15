---
title: Overzicht van Microsoft 365 netwerkverbinding
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
f1.keywords:
- NOCSH
description: Dit artikel bevat informatie over de manier waarop netwerk optimalisering belangrijk is voor SaaS-Services, het doel van Microsoft 365-netwerken en de manier waarop SaaS verschillende netwerken van andere werkbelastingen vereist.
ms.openlocfilehash: 4fea7364dc79717583ebca8ce0dbe333ee818f1f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689128"
---
# <a name="microsoft-365-network-connectivity-overview"></a>Overzicht van Microsoft 365 netwerkverbinding

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Microsoft 365 is een Distributed software-as-a-Service (SaaS)-wolk die productiviteits-en samenwerkingsscenario's biedt via een verscheidenheid aan Microsoft-services en-toepassingen. Client onderdelen van Microsoft 365, zoals Outlook, Word en PowerPoint, worden uitgevoerd op computers van gebruikers en verbinding maken met andere onderdelen van Microsoft 365 die worden uitgevoerd in Microsoft datacenters. De belangrijkste factor waarmee de kwaliteit van de eindgebruikers ervaring van Microsoft 365 wordt bepaald, is netwerk betrouwbaarheid en lage latentie tussen Microsoft 365-clients en de Microsoft 365-service voor de deuren.

In dit artikel vindt u meer informatie over de doelstellingen van Microsoft 365-netwerken en waarom voor Microsoft 365-netwerken een andere methode moet worden geoptimaliseerd dan voor algemeen Internet verkeer.

## <a name="microsoft-365-networking-goals"></a>Microsoft 365-netwerk doelstellingen

Het ultieme doel van Microsoft 365-netwerken is het optimaliseren van de eindgebruikers ervaring door de minst beperkte toegang tot de clients en de dichtstbijzijnde Microsoft 365-eindpunten in te schakelen. De kwaliteit van de eindgebruikers ervaring is direct gerelateerd aan de werking en de reactiesnelheid van de toepassing die de gebruiker gebruikt. In Microsoft teams is bijvoorbeeld gebruikgemaakt van lage latentie, zodat de telefoongesprekken van gebruikers, vergaderingen en gedeelde scherm samenwerking niet goed zijn en Outlook wordt gebruikt voor de functies voor direct zoeken waarmee de functies van de server en de AI-functies worden gebruikt.

Het primaire doel van het netwerkontwerp moet de latentie van de round-trip (RTT) van de clientcomputers in het Microsoft Global-netwerk beperken, de openbare netwerkbackbone van Microsoft die alle datacenters van Microsoft verbindt met lage latentie, de ingangspunten van de Cloud toepassing van hoge beschikbaarheid over de hele wereld. U vindt meer informatie over het wereldwijde Microsoft-netwerk [waar Microsoft het snelle en betrouwbare wereldwijde netwerk bouwt](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/).

Het optimaliseren van de prestaties van Microsoft 365 Network hoeft niet ingewikkeld te zijn. U krijgt de best mogelijke prestaties door een aantal van de belangrijkste beginselen te volgen:

- Microsoft 365-netwerkverkeer identificeren
- Lokale branch-uitgang voor Microsoft 365-netwerkverkeer naar Internet toestaan vanaf elke locatie waar gebruikers verbinding maken met Microsoft 365
- Microsoft 365-verkeer toestaan om proxy's en pakket inspectie apparaten te negeren

Zie beginselen van de [Netwerkverbindingen van Microsoft 365](microsoft-365-network-connectivity-principles.md)voor meer informatie over de principes van microsoft 365-netwerkverbindingen.

## <a name="traditional-network-architectures-and-saas"></a>Traditionele netwerk architecturen en SaaS

Traditionele beleids beginselen voor de netwerkarchitectuur voor client-en server belastingen zijn ontworpen rond de hypothese dat verkeer tussen clients en eindpunten niet wordt uitgebreid buiten het bedrijfsnetwerk. Ook in veel zakelijke netwerken worden alle uitgaande Internet verbindingen via het bedrijfsnetwerk, en de uitvoer van een centrale locatie, verbroken.

In traditionele netwerk architecturen is een hogere latentie voor algemeen Internet verkeer een noodzakelijke afname om de beveiliging van de netwerkverbinding te behouden, en prestatie optimalisering voor Internet verkeer omvat meestal een upgrade of schaling van de apparatuur op netwerk uitgangspunten. Deze aanpak biedt echter geen oplossing voor de vereisten voor optimale netwerkprestaties van SaaS-services zoals Microsoft 365.

## <a name="identifying-microsoft-365-network-traffic"></a>Microsoft 365-netwerkverkeer identificeren

U kunt het netwerkverkeer van Microsoft 365 eenvoudiger identificeren en de Netwerkidentificatie eenvoudiger beheren.

- Nieuwe categorieën netwerkeindpunten om zeer kritieke netwerkverkeer te onderscheiden van netwerkverkeer dat niet wordt beïnvloed door Internet latentie. Er zijn slechts een paar Url's en ondersteunde IP-adressen in de meest kritieke categorie ' optimaliseren '.
- Webservices voor het gebruik van script of directe apparaatconfiguratie en het wijzigen van het beheer van Microsoft 365-Netwerkidentificatie. U kunt wijzigingen aanbrengen in de webservice of in de RSS-indeling, of op e-mail met een Microsoft-flow sjabloon.
- Het [Office 365 Network partner-programma](https://aka.ms/Office365NPP) met Microsoft-partners die apparaten of diensten aanbieden die de principes van microsoft 365-netwerkconnectiviteit volgen en eenvoudige configuratie hebben.

## <a name="securing-microsoft-365-connections"></a>Microsoft 365-verbindingen beveiligen

Het doel van traditionele netwerkbeveiliging is het versterken van de perimeternetwerk omgeving tegen indringers en kwaadaardige aanvallen. De meeste Enterprise-netwerken zorgen voor netwerkbeveiliging van Internet verkeer met behulp van technologieën zoals proxyservers, firewalls en SSL-onderbrekingen, uitgebreide pakket inspecties en systemen voor preventie van gegevensverlies. Deze technologieën zorgen voor belangrijke risico beperkingen voor aanvragen van grote en grote en grote hoeveelheden en de kwaliteit van de eindgebruikers ervaring wanneer ze worden toegepast op Microsoft 365-eindpunten.

Microsoft 365 helpt bij het voldoen aan de behoeften van de organisatie voor inhoud beveiliging en compliance Data Usage met ingebouwde beveiligings-en beheerfuncties, speciaal ontworpen voor de functies en werkbelasting van Microsoft 365. Zie het Beveiligingsoverzicht van [Office 365](https://docs.microsoft.com/office365/securitycompliance/security-roadmap)voor meer informatie over beveiliging en compliance van microsoft 365. Zie voor meer informatie over de aanbevelingen en de ondersteunings locatie van Microsoft voor geavanceerde netwerkoplossingen die op het niveau van Microsoft 365 op Geavanceerd niveau [gebruikmaken van netwerkapparaten van derden of oplossingen voor Office 365-verkeer](https://support.microsoft.com/help/2690045).

## <a name="why-is-microsoft-365-networking-different"></a>Waarom verschilt Microsoft 365-netwerken?

Microsoft 365 is ontworpen voor optimale prestaties met behulp van eindpunt beveiliging en versleutelde netwerkverbindingen, waardoor het afdwingen van beveiligingsmaatregelen minder noodzakelijk is. Microsoft 365-datacenters bevinden zich overal ter wereld en de service is ontworpen voor gebruik van diverse methoden voor het verbinden van clients met de beste beschikbare service-eindpunten. Aangezien gebruikersgegevens en verwerking tussen diverse Microsoft-datacenters worden verdeeld, bestaat er geen enkel netwerkeindpunt waarmee clientcomputers verbinding kunnen maken. Gegevens en services in uw Microsoft 365-Tenant worden in feite dynamisch geoptimaliseerd door het Microsoft Global Network om aan te passen aan de geografische locaties van waaraf ze door eindgebruikers worden gebruikt.

Bepaalde bekende prestatieproblemen worden gemaakt wanneer Microsoft 365-verkeer is onderworpen aan inspectie van pakket en gecentraliseerde uitgang:

- Hoge latentie kan zorgen voor zeer slechtere prestaties van video-en audiostreams, en traag reageren op het ophalen van gegevens, zoekopdrachten, realtime samenwerking, agenda beschikbaarheidsinfo, inhoud van het product en andere services
- Egressing-verbindingen vanaf een centrale locatie Defeats de dynamische routeringsfuncties van het globale Microsoft 365-netwerk, waarbij de latentie en de round-trip tijd worden toegevoegd
- Met het deactiveren van SSL beveiligd Microsoft 365-netwerkverkeer en het opnieuw versleutelen van een protocol kan dit resulteren in protocolfouten en beveiligingsrisico

Verkort het netwerkpad naar Microsoft 365-toegangspunten door het verkeer van clientverkeer zo dicht mogelijk te laten verlopen, zodat de efficiëntie van de verbinding en de eindgebruikers ervaring in Microsoft 365 kan worden verbeterd. U kunt er ook voor zorgen dat u de gevolgen van toekomstige wijzigingen in de netwerkarchitectuur op de prestaties en betrouwbaarheid van Microsoft 365 beperkt. Het optimale verbindings model is altijd beschikbaar op de locatie van de gebruiker, ongeacht of dit zich bevindt in het bedrijfsnetwerk of externe locaties, zoals thuis, hotels, cafés en luchthavens. Algemeen Internet verkeer en netwerkverkeer op basis van een bedrijfsnetwerk worden apart gerouteerd en gebruiken geen lokaal direct uitgangs model. Dit lokale direct uitgangs model wordt weergegeven in het onderstaande diagram.

![Lokale uituitgangs netwerkarchitectuur](../media/6bc636b0-1234-4ceb-a45a-aadd1044b39c.png)

De architectuur voor lokale uitslagen heeft de volgende voordelen voor Microsoft 365-netwerkverkeer via het traditionele model:
  
- Biedt optimale prestaties van Microsoft 365 door de route lengte te optimaliseren. Eindgebruikers verbindingen worden dynamisch naar het dichtstbijzijnde Microsoft 365-toegangspunt gerouteerd via de front-enddatabase _voor de gedistribueerde service voor_ Microsoft Global Network en verkeer wordt vervolgens intern gerouteerd naar gegevens-en service-eindpunten over de zeer lage beschikbaarheids kwaliteit van Microsoft.
- Hiermee wordt de netwerkinfrastructuur beperkt door lokaal aflossing voor Microsoft 365-verkeer te passeren, proxy's en inspectieapparatuur voor verkeer over te slaan.
- Verveilig verbindingen aan beide uiteinden door gebruik te maken van beveiligingsfuncties voor client eindpunten en de Cloud beveiligingstechnologieën te vermijden.

> [!NOTE]
> De infrastructuur van de _gedistribueerde service front deur_ is de uiterst beschikbare en schaalbare netwerk Edge van het Microsoft-netwerk met geografisch verspreide locaties. De client beëindigt verbindingen van eindgebruikers en stuurt efficiënt ze binnen het Microsoft Global Network. U vindt meer informatie over het wereldwijde Microsoft-netwerk [waar Microsoft het snelle en betrouwbare wereldwijde netwerk bouwt](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/).

Zie beginselen van de [Netwerkverbindingen van Microsoft 365](microsoft-365-network-connectivity-principles.md)voor meer informatie over het begrijpen en toepassen van de principes van microsoft 365-netwerkverbindingen.

## <a name="conclusion"></a>Conclusie

Het optimaliseren van de prestaties van Microsoft 365 Network is echt overbodig om overbodige belemmeringen te verwijderen. Door Microsoft 365-verbindingen als vertrouwd verkeer te behandelen, kunt u voorkomen dat de latentie van de genodigden door de pakket inspectie en-concurrentie wordt geïntroduceerd voor de proxy bandbreedte. Als u lokale verbindingen tussen clientcomputers en Office 365-eindpunten toestaat, kunt u verkeer dynamisch via het Microsoft Global Network routeren.

## <a name="related-topics"></a>Verwante onderwerpen

[Principes voor Microsoft 365-netwerkverbindingen](microsoft-365-network-connectivity-principles.md)

[Office 365-eindpunten beheren](managing-office-365-endpoints.md)

[URL's en IP-adresbereiken voor Office 365](urls-and-ip-address-ranges.md)

[Office 365 IP Address en URL web service](microsoft-365-ip-web-service.md)

[Microsoft 365-netwerkconnectiviteit beoordelen](assessing-network-connectivity.md)

[Netwerk planning en prestaties optimaliseren voor Microsoft 365](network-planning-and-performance.md)

[Prestaties afstemmen van Office 365 met basislijnen en prestatie geschiedenis](performance-tuning-using-baselines-and-history.md)

[Prestatieproblemen met het plannen van Office 365](performance-troubleshooting-plan.md)

[Netwerken voor content levering](content-delivery-networks.md)

[Microsoft 365 connectiviteitstest](https://aka.ms/netonboard)

[Hoe Microsoft het snelle en betrouwbare wereldwijde netwerk bouwt](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/)

[Blog van Office 365-netwerken](https://techcommunity.microsoft.com/t5/Office-365-Networking/bd-p/Office365Networking)
