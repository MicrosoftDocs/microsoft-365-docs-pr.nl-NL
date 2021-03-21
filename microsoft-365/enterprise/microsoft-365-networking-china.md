---
title: Microsoft 365 global tenant performance optimization for China users
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/23/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- remotework
search.appverid: MET150
f1.keywords:
- NOCSH
description: Dit artikel bevat richtlijnen voor het optimaliseren van netwerkprestaties voor China-gebruikers van globale Microsoft 365-tenants.
ms.openlocfilehash: 2ba0509425b60aec35d29b23b84e3b6346d2f5cb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923192"
---
# <a name="microsoft-365-global-tenant-performance-optimization-for-china-users"></a>Microsoft 365 global tenant performance optimization for China users

>[!IMPORTANT]
>Deze richtlijnen zijn specifiek voor gebruiksscenario's waarin zakelijke **Microsoft 365-gebruikers in China** verbinding maken met een globale Microsoft **365-tenant.** Deze richtlijn is **niet van** toepassing op tenants in Office 365 beheerd door 21Vianet.

Voor ondernemingen met globale Microsoft 365-tenants en een aanwezigheid van bedrijven in China kunnen de prestaties van microsoft 365-client voor gebruikers in China worden bemoeilijkt door factoren die uniek zijn voor de internetarchitectuur van China Telco.

China ISP's hebben offshoreverbindingen met het wereldwijde openbare internet geregeld die door perimeterapparaten gaan die gevoelig zijn voor hoge niveaus van congestie van het grensoverschrijdende netwerk. Deze congestie zorgt voor pakketverlies en latentie voor al het internetverkeer dat china binnen en buiten gaat.

![Microsoft 365-verkeer - niet-geoptimiseerd](../media/O365-networking/China-O365-unoptimized.png)

Pakketverlies en latentie zijn nadelig voor de prestaties van netwerkservices, met name services waarvoor grote gegevensuitwisselingen nodig zijn (zoals grote bestandsoverdrachten) of die bijna realtime prestaties vereisen (audio- en videotoepassingen).

Het doel van dit onderwerp is om best practices te bieden voor het beperken van de gevolgen van grensoverschrijdende netwerkcongestie in China voor Microsoft 365-services. Dit onderwerp heeft geen betrekking op andere veelvoorkomende prestatieproblemen op de laatste kilometer, zoals problemen met hoge pakketlatentie als gevolg van complexe routering binnen Chinese providers.

## <a name="corporate-network-best-practices"></a>Best practices voor bedrijfsnetwerk

Veel ondernemingen met globale Microsoft 365-tenants en gebruikers in China hebben privénetwerken geïmplementeerd die bedrijfsnetwerkverkeer tussen China-kantoorlocaties en offshorelocaties over de hele wereld uitvoeren. Deze ondernemingen kunnen gebruikmaken van deze netwerkinfrastructuur om grensoverschrijdende netwerkcongestie te voorkomen en de prestaties van de Microsoft 365-service in China te optimaliseren.

>[!IMPORTANT]
>Net als bij alle private WAN-implementaties, moet u altijd de wettelijke vereisten voor uw land en/of regio raadplegen om ervoor te zorgen dat de netwerkconfiguratie voldoet.

Als eerste stap is het van essentieel belang dat u onze benchmarknetwerk richtlijnen volgt voor netwerkplanning en [prestatieafstemming voor Microsoft 365.](./network-planning-and-performance.md) Het primaire doel moet zijn om zo mogelijk geen toegang te krijgen tot globale Microsoft 365-services vanaf internet in China.

- Maak gebruik van uw bestaande privénetwerk om Microsoft 365-netwerkverkeer te voeren tussen Office-netwerken in China en offshorelocaties die buiten China op het openbare internet komen. Vrijwel elke locatie buiten China biedt een duidelijk voordeel. Netwerkbeheerders kunnen verder optimaliseren door uit te gaan in gebieden met een lage latentie interconnect met het [globale Microsoft-netwerk.](/azure/networking/microsoft-global-network) Hongkong, Japan en Zuid-Korea zijn voorbeelden.
- Configureer gebruikersapparaten om via een VPN-verbinding toegang te krijgen tot het bedrijfsnetwerk, zodat Microsoft 365-verkeer de private offshore-koppeling van het bedrijfsnetwerk kan doorvoeren. Zorg ervoor dat VPN-clients niet zijn geconfigureerd voor het gebruik van gesplitste tunneling of dat gebruikersapparaten zijn geconfigureerd om gesplitste tunneling voor Microsoft 365-verkeer te negeren.
- Configureer uw netwerk om al het Microsoft 365-verkeer via uw privé-offshorekoppeling te laten lopen. Als u het volume van het verkeer op uw privékoppeling moet minimaliseren, kunt u ervoor  kiezen  om alleen eindpunten te routen in de categorie Optimaliseren en toestaan dat aanvragen voor Toegestane en Standaard-eindpunten via internet worden doorgeleid.  Dit verbetert de prestaties en minimaliseert het bandbreedteverbruik door geoptimaliseerd verkeer te beperken tot kritieke services die het meest gevoelig zijn voor hoge latentie en pakketverlies.
- Gebruik indien mogelijk UDP in plaats van TCP voor live mediastreamingverkeer, zoals voor Teams. UDP biedt betere live mediastreamingprestaties dan TCP.

Zie Office 365-eindpunten beheren voor informatie over het selectief doorsturen van Microsoft [365-verkeer.](managing-office-365-endpoints.md) Zie URL's en IP-adresbereiken van [Office 365](urls-and-ip-address-ranges.md)voor een lijst met alle url's en IP-adressen over de hele wereld.

![Microsoft 365-verkeer - geoptimaliseerd](../media/O365-networking/China-O365-optimized.png)

## <a name="user-best-practices"></a>Best practices voor gebruikers

Gebruikers in China die verbinding maken met globale Microsoft 365-tenants vanaf externe locaties, zoals huizen, coffeeshops, hotels en filialen zonder verbinding met bedrijfsnetwerken, kunnen slechte netwerkprestaties ervaren, omdat het verkeer tussen hun apparaten en Microsoft 365 de overbelaste grensoverschrijdende netwerkcircuits van China moet doorvoeren.

Als grensoverschrijdende privénetwerken en/of VPN-toegang tot het bedrijfsnetwerk geen optie zijn, kunnen prestatieproblemen per gebruiker nog steeds worden beperkt door uw in China gevestigde gebruikers op te trainen om deze best practices te volgen.

- Gebruik uitgebreide Office-clients die caching ondersteunen (bijvoorbeeld Outlook, Teams, OneDrive, enzovoort) en vermijd webcl clients. Office-client caching- en offlinetoegangsfuncties kunnen de impact van netwerkcongestie en latentie aanzienlijk verminderen.
- Als uw Microsoft 365-tenant is geconfigureerd met de functie _Audiovergadering,_ kunnen Teams-gebruikers deelnemen aan vergaderingen via het openbare telefoonnetwerk (PSTN). Zie [Audiovergaderingen in Office 365](/microsoftteams/audio-conferencing-in-office-365)voor meer informatie.
- Als gebruikers problemen met de netwerkprestaties ervaren, moeten ze zich melden bij hun IT-afdeling voor probleemoplossing en escaleren naar Microsoft-ondersteuning als er problemen met Microsoft 365-services worden vermoed. Niet alle problemen worden veroorzaakt door grensoverschrijdende netwerkprestaties.

Microsoft werkt voortdurend aan het verbeteren van de gebruikerservaring van Microsoft 365 en de prestaties van clients over een zo breed mogelijk bereik van netwerkarchitectuur en -kenmerken. Ga naar [de Office 365 Tech Community om](https://techcommunity.microsoft.com/t5/office-365/bd-p/Office365General) een gesprek te starten of deel te nemen, bronnen te zoeken en functieaanvragen en suggesties in te dienen.

## <a name="related-topics"></a>Verwante onderwerpen

[Netwerkplanning en prestaties optimaliseren voor Microsoft 365](./network-planning-and-performance.md)

[Beginselen voor Microsoft 365-netwerkverbindingen](microsoft-365-network-connectivity-principles.md)

[Office 365-eindpunten beheren](managing-office-365-endpoints.md)

[URL's en IP-adresbereiken voor Office 365](urls-and-ip-address-ranges.md)

[Microsoft Global Network](/azure/networking/microsoft-global-network)