---
title: Microsoft 365 algemene tenantprestatieoptimalisatie voor Gebruikers van China
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
description: Dit artikel bevat richtlijnen voor het optimaliseren van netwerkprestaties voor China-gebruikers van globale Microsoft 365 tenants.
ms.openlocfilehash: f48b552dec72d78e2429aedf6a3834dba6c7590a
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844500"
---
# <a name="microsoft-365-global-tenant-performance-optimization-for-china-users"></a>Microsoft 365 algemene tenantprestatieoptimalisatie voor Gebruikers van China

> [!IMPORTANT]
> Deze richtlijnen zijn specifiek voor gebruiksscenario's waarin **Microsoft 365 gebruikers in China** verbinding maken met een globale Microsoft 365 **tenant**. Deze richtlijn is **niet van** toepassing op tenants in Office 365 beheerd door 21Vianet.

Voor ondernemingen met globale Microsoft 365-tenants en een zakelijke aanwezigheid in China kunnen Microsoft 365-clientprestaties voor in China gevestigde gebruikers worden bemoeilijkt door factoren die uniek zijn voor de internetarchitectuur van China Telco.

China ISP's hebben offshoreverbindingen met het wereldwijde openbare internet geregeld die door perimeterapparaten gaan die gevoelig zijn voor hoge niveaus van congestie van het grensoverschrijdende netwerk. Deze congestie zorgt voor pakketverlies en latentie voor al het internetverkeer dat china binnen en buiten gaat.

![Microsoft 365 - niet-geoptimiseerd](../media/O365-networking/China-O365-unoptimized.png)

Pakketverlies en latentie zijn nadelig voor de prestaties van netwerkservices, met name services waarvoor grote gegevensuitwisselingen nodig zijn (zoals grote bestandsoverdrachten) of die bijna realtime prestaties vereisen (audio- en videotoepassingen).

Het doel van dit onderwerp is om best practices te bieden voor het beperken van de gevolgen van grensoverschrijdende netwerkcongestie in China voor Microsoft 365 services. Dit onderwerp heeft geen betrekking op andere veelvoorkomende prestatieproblemen op de laatste kilometer, zoals problemen met hoge pakketlatentie als gevolg van complexe routering binnen Chinese providers.

## <a name="corporate-network-best-practices"></a>Best practices voor bedrijfsnetwerk

Veel ondernemingen met globale Microsoft 365 en gebruikers in China hebben privénetwerken geïmplementeerd die bedrijfsnetwerkverkeer tussen China-kantoorlocaties en offshorelocaties over de hele wereld uitvoeren. Deze ondernemingen kunnen gebruikmaken van deze netwerkinfrastructuur om grensoverschrijdende netwerkcongestie te voorkomen en hun Microsoft 365 in China te optimaliseren.

> [!IMPORTANT]
> Net als bij alle private WAN-implementaties, moet u altijd de wettelijke vereisten voor uw land en/of regio raadplegen om ervoor te zorgen dat de netwerkconfiguratie voldoet.

Als eerste stap is het van essentieel belang dat u onze benchmarknetwerkbegeleiding volgt bij Netwerkplanning en prestatieafstemming voor [Microsoft 365.](./network-planning-and-performance.md) Het primaire doel moet zijn om te voorkomen dat er toegang wordt Microsoft 365 globale services vanaf internet in China, indien mogelijk.

- Maak gebruik van uw bestaande privénetwerk om Microsoft 365 te voeren tussen China Office-netwerken en offshorelocaties die buiten China op het openbare internet komen. Vrijwel elke locatie buiten China biedt een duidelijk voordeel. Netwerkbeheerders kunnen verder optimaliseren door uit te gaan in gebieden met een lage latentie interconnect met het [globale Microsoft-netwerk.](/azure/networking/microsoft-global-network) Hongkong, Japan en Zuid-Korea zijn voorbeelden.
- Configureer gebruikersapparaten om via een VPN-verbinding toegang te krijgen tot het bedrijfsnetwerk, zodat Microsoft 365 de private offshore-koppeling van het bedrijfsnetwerk kan doorvoeren. Zorg ervoor dat VPN-clients niet zijn geconfigureerd voor het gebruik van gesplitste tunneling of dat gebruikersapparaten zijn geconfigureerd om gesplitste tunneling te negeren voor Microsoft 365 verkeer. Zie deze sectie voor meer informatie over het optimaliseren van VPN-connectiviteit Teams en realtime [mediaverkeer.](#optimizing-microsoft-teams-meetings-network-performance-for-users-in-china)
- Configureer uw netwerk om al het Microsoft 365 via uw privé-offshoreverbinding te laten lopen. Als u het volume van het verkeer op uw privékoppeling moet minimaliseren, kunt u ervoor  kiezen  om alleen eindpunten te routen in de categorie Optimaliseren en toestaan dat aanvragen voor Toegestane en Standaard-eindpunten via internet worden doorgeleid.  Dit verbetert de prestaties en minimaliseert het bandbreedteverbruik door geoptimaliseerd verkeer te beperken tot kritieke services die het meest gevoelig zijn voor hoge latentie en pakketverlies.
- Gebruik indien mogelijk UDP in plaats van TCP voor live mediastreamingverkeer, zoals voor Teams. UDP biedt betere live mediastreamingprestaties dan TCP.

Zie Office 365 eindpunten beheren voor informatie over het selectief Microsoft 365 [routebeheer.](managing-office-365-endpoints.md) Voor een lijst met alle Office 365 URL's en IP-adressen, [zie Office 365 URL's en IP-adresbereiken.](urls-and-ip-address-ranges.md)

![Microsoft 365 - geoptimaliseerd](../media/O365-networking/China-O365-optimized.png)

## <a name="user-best-practices"></a>Best practices voor gebruikers

Gebruikers in China die verbinding maken met globale Microsoft 365-tenants vanaf externe locaties, zoals huizen, coffeeshops, hotels en filialen zonder verbinding met bedrijfsnetwerken, kunnen slechte netwerkprestaties ervaren omdat het verkeer tussen hun apparaten en Microsoft 365 de overbelaste grensoverschrijdende netwerkcircuits van China moet doorvoeren.

Als grensoverschrijdende privénetwerken en/of VPN-toegang tot het bedrijfsnetwerk geen optie zijn, kunnen prestatieproblemen per gebruiker nog steeds worden beperkt door uw in China gevestigde gebruikers op te trainen om deze best practices te volgen.

- Gebruik rich Office clients die caching ondersteunen (bijvoorbeeld Outlook, Teams, OneDrive, enzovoort) en vermijd web-clients. Office client caching- en offlinetoegangsfuncties kunnen de impact van netwerkcongestie en latentie aanzienlijk verminderen.
- Als uw Microsoft 365 tenant is geconfigureerd met  de functie Audiovergaderingen, kunnen Teams gebruikers deelnemen aan vergaderingen via het openbare telefoonnetwerk (PSTN). Zie Audiovergaderingen in Office 365 voor [meer Office 365.](/microsoftteams/audio-conferencing-in-office-365)
- Als gebruikers problemen met netwerkprestaties ervaren, moeten ze zich melden bij hun IT-afdeling voor probleemoplossing en escaleren naar Microsoft-ondersteuning als er problemen met Microsoft 365 services worden vermoed. Niet alle problemen worden veroorzaakt door grensoverschrijdende netwerkprestaties.

## <a name="optimizing-microsoft-teams-meetings-network-performance-for-users-in-china"></a>Netwerkprestaties Microsoft Teams vergaderingen optimaliseren voor gebruikers in China

Voor organisaties met globale Microsoft 365 en een aanwezigheid in China kunnen Microsoft 365 prestaties van klanten voor in China gebaseerde gebruikers worden bemoeilijkt door factoren die uniek zijn voor de Chinese internetarchitectuur. Veel bedrijven en scholen hebben goede resultaten gerapporteerd door deze richtlijnen te volgen. Het bereik is echter beperkt tot gebruikersnetwerklocaties die onder controle staan van de configuratie van IT-netwerken, bijvoorbeeld kantoorlocaties of thuis/mobiele eindpunten met VPN-connectiviteit. Microsoft Teams gesprekken en vergaderingen worden vaak gebruikt vanaf externe locaties, zoals thuiskantoren, mobiele locaties, onderweg en coffeeshops. Omdat oproepen en vergaderingen afhankelijk zijn van realtime mediaverkeer, zijn deze Teams bijzonder gevoelig voor netwerkcongestie.

Als gevolg hiervan werkt Microsoft samen met telecommunicatieproviders om Teams en Skype voor Bedrijven Online realtime mediaverkeer te voeren met behulp van een netwerkpad van hogere kwaliteit tussen binnenlandse en openbare internetverbindingen in China en de Teams- en Skype-services in de globale cloud van Microsoft 365. Deze mogelijkheid heeft geleid tot een meer dan tienvoudige verbetering van pakketverlies en andere belangrijke metrische gegevens die van invloed zijn op de ervaring van uw gebruiker.

>[!IMPORTANT]
>Op dit moment zijn deze verbeteringen niet gericht op het bijwonen van Microsoft Live Events-vergaderingen, zoals grote broadcast- of 'town hall'-stijlvergaderingen met Teams of Microsoft Stream. Als u een Live Events-vergadering wilt bekijken, moeten gebruikers in China een privénetwerk of SDWAN/VPN-oplossing gebruiken. De netwerkverbeteringen komen echter ten goede aan gebruikers die een livegebeurtenissenvergadering presenteren of produceren, omdat deze ervaring fungeert als een normale Teams voor de producent of presentator.

### <a name="organization-network-best-practices-for-teams-meetings"></a>Best practices voor organisatienetwerk voor Teams vergaderingen

U moet overwegen hoe u gebruik kunt maken van deze netwerkverbeteringen, aangezien de vorige richtlijnen een privénetwerkextensie overwegen om congestie van het grensoverschrijdende netwerk te voorkomen. Er zijn twee algemene opties voor organisatie-officenetwerken:

1. Doe niets nieuws. Volg de eerdere richtlijnen voor het omzeilen van privénetwerk om grensoverschrijdende congestie te voorkomen. Teams realtime mediaverkeer maakt gebruik van deze configuratie, net als voorheen.
2. Implementeert een gesplitst/hybride patroon.
   - Gebruik de vorige richtlijnen voor alle verkeer met een vlag voor optimalisatie, behalve Teams vergaderingen en het bellen van realtime mediaverkeer.
   - Routeer Teams en bel realtime mediaverkeer via het openbare internet. Zie de volgende informatie voor specifieke informatie over het identificeren van het realtime medianetwerkverkeer.

Het verzenden Teams realtime mediaaudio- en videoverkeer via het openbare internet, dat gebruikmaakt van de connectiviteit van hogere kwaliteit, kan aanzienlijke kostenbesparingen tot gevolg hebben, omdat het gratis is versus betalen om dat verkeer via een privénetwerk te verzenden. Er kunnen soortgelijke extra voordelen zijn als gebruikers ook SDWAN- of VPN-clients gebruiken. Sommige organisaties geven er ook de voorkeur aan dat meer van hun gegevens openbare internetverbindingen gebruiken als algemene praktijk.

Dezelfde opties kunnen van toepassing zijn op SDWAN- of VPN-configuraties. Een gebruiker gebruikt bijvoorbeeld een SDWAN of VPN om Microsoft 365-verkeer naar het bedrijfsnetwerk te leiden en vervolgens gebruik te maken van de persoonlijke extensie van dat netwerk om grensoverschrijdende congestie te voorkomen. De SDWAN of VPN van de gebruiker kan nu worden geconfigureerd om de Teams en realtimeverkeer uit te sluiten van de VPN-routering. Deze VPN-configuratie wordt splits tunneling genoemd. Zie [VPN splits tunneling voor Office 365](/microsoft-365/enterprise/microsoft-365-vpn-implement-split-tunnel) voor meer informatie.

U kunt ook uw SDWAN of VPN blijven gebruiken voor alle Microsoft 365 verkeer, ook voor Microsoft Teams realtimeverkeer. Microsoft heeft geen aanbevelingen voor het gebruik van SDWAN- of VPN-oplossingen.

### <a name="home-mobile-and-user-network-best-practices-for-teams-meetings"></a>Best practices voor thuisgebruik, mobiel en gebruikersnetwerk voor Teams vergaderingen

Gebruikers in China kunnen van deze verbeteringen profiteren door gewoon verbinding te maken met de openbare internetservice in China met een vaste of mobiele verbinding. Teams real-time media-audio- en videoverkeer op het openbare internet profiteert rechtstreeks van verbeterde connectiviteit en kwaliteit.

Gegevens van andere Microsoft 365 services en ander verkeer in Teams, zoals chat of bestanden, profiteren echter niet rechtstreeks van deze verbeteringen. Gebruikers buiten het organisatienetwerk kunnen nog steeds te maken hebben met slechte netwerkprestaties voor dit verkeer. Zoals in dit artikel wordt besproken, kunt u deze effecten beperken met behulp van een VPN of SDWAN. U kunt uw gebruikers ook rich desktopcl clients laten gebruiken via webcl clients, die in-app caching ondersteunen om netwerkproblemen te beperken.

### <a name="identifying-teams-real-time-media-network-traffic"></a>Realtime Teams medianetwerkverkeer identificeren

Als u een netwerkapparaat of een VPN/SDWAN-installatie wilt configureren, hoeft u alleen het realtime audio- en videoverkeer Teams media uit te sluiten. De verkeersgegevens vindt u voor id 11 in de officiële lijst met Office 365 [URL's en IP-adresbereiken.](urls-and-ip-address-ranges.md#skype-for-business-online-and-microsoft-teams) Alle andere netwerkconfiguraties moeten in de huidige staat blijven.

Microsoft werkt voortdurend aan het verbeteren van Microsoft 365 gebruikerservaring en de prestaties van clients over een zo breed mogelijk bereik van netwerkarchitectuur en -kenmerken. Ga naar [de Office 365 Networking Tech Community om](https://techcommunity.microsoft.com/t5/office-365-networking/bd-p/Office365Networking) een gesprek te starten of deel te nemen, bronnen te zoeken en functieaanvragen en suggesties in te dienen

## <a name="related-topics"></a>Verwante onderwerpen

[Netwerkplanning en prestaties optimaliseren voor Microsoft 365](./network-planning-and-performance.md)

[Beginselen voor Microsoft 365-netwerkverbindingen](microsoft-365-network-connectivity-principles.md)

[Office 365-eindpunten beheren](managing-office-365-endpoints.md)

[URL's en IP-adresbereiken voor Office 365](urls-and-ip-address-ranges.md)

[Microsoft Global Network](/azure/networking/microsoft-global-network)
