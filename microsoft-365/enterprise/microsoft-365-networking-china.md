---
title: Microsoft 365 global tenant performance optimization for China users
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 11/17/2020
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
ms.openlocfilehash: e330e892b584c805bded2228381e74e6a4fa615a
ms.sourcegitcommit: 0ff6edbf52562138a69c6675cb0274ec984986c3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/07/2021
ms.locfileid: "51615193"
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

- Maak gebruik van uw bestaande privénetwerk om Microsoft 365-netwerkverkeer te voeren tussen Office-netwerken in China en offshorelocaties die buiten China op het openbare internet komen. Vrijwel elke locatie buiten China biedt een duidelijk voordeel. Netwerkbeheerders kunnen verder optimaliseren door uit te gaan in gebieden met een lage latentie interconnect met het [globale Microsoft-netwerk.](https://docs.microsoft.com/azure/networking/microsoft-global-network) Hongkong, Japan en Zuid-Korea zijn voorbeelden.
- Configureer gebruikersapparaten om via een VPN-verbinding toegang te krijgen tot het bedrijfsnetwerk, zodat Microsoft 365-verkeer de private offshore-koppeling van het bedrijfsnetwerk kan doorvoeren. Zorg ervoor dat VPN-clients niet zijn geconfigureerd voor het gebruik van gesplitste tunneling of dat gebruikersapparaten zijn geconfigureerd om gesplitste tunneling voor Microsoft 365-verkeer te negeren. Zie deze sectie voor meer informatie over het optimaliseren van VPN-connectiviteit voor Teams en realtime [mediaverkeer.](#optimizing-microsoft-teams-meetings-network-performance-for-users-in-china)
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

## <a name="optimizing-microsoft-teams-meetings-network-performance-for-users-in-china"></a>Netwerkprestaties van Microsoft Teams-vergaderingen optimaliseren voor gebruikers in China  

Voor organisaties met globale Microsoft 365-tenants en een aanwezigheid in China kunnen microsoft 365-clientprestaties voor gebruikers in China worden bemoeilijkt door factoren die uniek zijn voor de Chinese internetarchitectuur. Veel bedrijven en scholen hebben goede resultaten gerapporteerd door deze richtlijnen te volgen. Het bereik is echter beperkt tot gebruikersnetwerklocaties die onder controle staan van de configuratie van IT-netwerken, bijvoorbeeld kantoorlocaties of thuis/mobiele eindpunten met VPN-connectiviteit. Microsoft Teams-oproepen en -vergaderingen worden vaak gebruikt vanaf externe locaties, zoals thuiskantoren, mobiele locaties, onderweg en coffeeshops. Omdat oproepen en vergaderingen afhankelijk zijn van realtime mediaverkeer, zijn deze Teams-ervaringen bijzonder gevoelig voor netwerkcongestie.

Als gevolg hiervan werkt Microsoft samen met telecommunicatieproviders om Teams en Skype voor Bedrijven Online real-time mediaverkeer te bieden met behulp van een netwerkpad van hogere kwaliteit tussen binnenlandse en openbare internetverbindingen in China en de Teams- en Skype-services in de globale microsoft 365-cloud. Deze mogelijkheid heeft geleid tot een meer dan tienvoudige verbetering van pakketverlies en andere belangrijke metrische gegevens die van invloed zijn op de ervaring van uw gebruiker.

>[!IMPORTANT]
>Op dit moment zijn deze verbeteringen niet gericht op het bijwonen van Microsoft Live Events-vergaderingen, zoals grote vergaderingen in de stijl van een uitzending of een 'gemeentehuis' met Teams of Microsoft Stream. Als u een Live Events-vergadering wilt bekijken, moeten gebruikers in China een privénetwerk of SDWAN/VPN-oplossing gebruiken. De netwerkverbeteringen komen echter ten goede aan gebruikers die een Live Events-vergadering presenteren of produceren, omdat deze ervaring fungeert als een gewone Teams-vergadering voor de producent of presentator.

### <a name="organization-network-best-practices-for-teams-meetings"></a>Best practices voor organisatienetwerk voor Teams-vergaderingen

U moet overwegen hoe u gebruik kunt maken van deze netwerkverbeteringen, aangezien de vorige richtlijnen een privénetwerkextensie overwegen om congestie van het grensoverschrijdende netwerk te voorkomen. Er zijn twee algemene opties voor organisatie-officenetwerken:

1.  Doe niets nieuws. Volg de eerdere richtlijnen voor het omzeilen van privénetwerk om grensoverschrijdende congestie te voorkomen. Teams real-time mediaverkeer maakt gebruik van deze configuratie, net als voorheen.
2.  Implementeert een gesplitst/hybride patroon. 

  - Gebruik de vorige richtlijnen voor alle verkeer dat is gemarkeerd voor optimalisatie, behalve Teams-vergaderingen en het bellen van realtime mediaverkeer.

  - Route teams vergaderen en bellen van realtime mediaverkeer via het openbare internet. Zie de volgende informatie voor specifieke informatie over het identificeren van het realtime medianetwerkverkeer.

Als u Teams realtime mediaaudio- en videoverkeer verzendt via het openbare internet, dat gebruikmaakt van de connectiviteit van hogere kwaliteit, kan dit leiden tot aanzienlijke kostenbesparingen, omdat het gratis is versus betalen om dat verkeer via een privénetwerk te verzenden. Er kunnen soortgelijke extra voordelen zijn als gebruikers ook SDWAN- of VPN-clients gebruiken. Sommige organisaties geven er ook de voorkeur aan dat meer van hun gegevens openbare internetverbindingen gebruiken als algemene praktijk.

Dezelfde opties kunnen van toepassing zijn op SDWAN- of VPN-configuraties. Een gebruiker gebruikt bijvoorbeeld een SDWAN of VPN om Microsoft 365-verkeer naar het bedrijfsnetwerk te leiden en vervolgens gebruik te maken van de persoonlijke extensie van dat netwerk om grensoverschrijdende congestie te voorkomen. De SDWAN of VPN van de gebruiker kan nu worden geconfigureerd om Teams-vergadering uit te sluiten en realtimeverkeer te bellen vanuit de VPN-routering. Deze VPN-configuratie wordt splits tunneling genoemd. Zie [VPN splits tunneling voor Office 365](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-vpn-implement-split-tunnel) voor meer informatie.

U kunt ook uw SDWAN of VPN blijven gebruiken voor al het Microsoft 365-verkeer, ook voor realtimeverkeer van Microsoft Teams. Microsoft heeft geen aanbevelingen voor het gebruik van SDWAN- of VPN-oplossingen.

### <a name="home-mobile-and-user-network-best-practices-for-teams-meetings"></a>Best practices voor Thuisgebruik, Mobiel en Gebruikersnetwerk voor Teams-vergaderingen

Gebruikers in China kunnen van deze verbeteringen profiteren door gewoon verbinding te maken met de openbare internetservice in China met een vaste of mobiele verbinding. Teams real-time media audio- en videoverkeer op het openbare internet profiteert rechtstreeks van verbeterde connectiviteit en kwaliteit.

Gegevens van andere Microsoft 365-services en ander verkeer in Teams, zoals chat of bestanden, profiteren echter niet rechtstreeks van deze verbeteringen. Gebruikers buiten het organisatienetwerk kunnen nog steeds te maken hebben met slechte netwerkprestaties voor dit verkeer. Zoals in dit artikel wordt besproken, kunt u deze effecten beperken met behulp van een VPN of SDWAN. U kunt uw gebruikers ook rich desktopcl clients laten gebruiken via webcl clients, die in-app caching ondersteunen om netwerkproblemen te beperken.

### <a name="identifying-teams-real-time-media-network-traffic"></a>Teams real-time medianetwerkverkeer identificeren

Als u een netwerkapparaat of een VPN/SDWAN-installatie wilt configureren, hoeft u alleen het realtime media-audio- en videoverkeer van Teams uit te sluiten. De verkeersgegevens vindt u voor ID 11 in de officiële lijst met URL's en [IP-adresbereiken van Office 365.](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) Alle andere netwerkconfiguraties moeten in de huidige staat blijven.

Microsoft werkt voortdurend aan het verbeteren van de gebruikerservaring van Microsoft 365 en de prestaties van clients over een zo breed mogelijk bereik van netwerkarchitectuur en -kenmerken. Ga naar [de Office 365 Networking Tech Community om]( https://techcommunity.microsoft.com/t5/office-365-networking/bd-p/Office365Networking) een gesprek te starten of deel te nemen, bronnen te zoeken en functieaanvragen en suggesties in te dienen

## <a name="related-topics"></a>Verwante onderwerpen

[Netwerkplanning en prestaties optimaliseren voor Microsoft 365](./network-planning-and-performance.md)

[Beginselen voor Microsoft 365-netwerkverbindingen](microsoft-365-network-connectivity-principles.md)

[Office 365-eindpunten beheren](managing-office-365-endpoints.md)

[URL's en IP-adresbereiken voor Office 365](urls-and-ip-address-ranges.md)

[Microsoft Global Network](/azure/networking/microsoft-global-network)