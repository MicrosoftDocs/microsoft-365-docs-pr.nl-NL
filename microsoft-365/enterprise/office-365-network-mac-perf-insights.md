---
title: Microsoft 365 Network Insights (preview)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365 Network Insights (preview)
ms.openlocfilehash: d6786ce6cd58ce6f350804fbbacd272b8c077dc0
ms.sourcegitcommit: 1ac884d8470b2f2a58b6f79e324fd91e4d11dceb
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2021
ms.locfileid: "50055471"
---
# <a name="microsoft-365-network-insights-preview"></a>Microsoft 365 Network Insights (preview)

**Netwerkinzichten** zijn prestatiestatistieken die worden verzameld via uw Microsoft 365-tenant en die alleen kunnen worden bekeken door beheerders in uw tenant. Inzichten worden weergegeven in het Microsoft 365-beheercentrum op <https://portal.microsoft.com/adminportal/home#/networkperformance> .

Inzichten zijn bedoeld om u te helpen bij het ontwerpen van netwerkperimeters voor uw kantoorlocaties. Elk inzicht biedt livedetails over de prestatiekenmerken voor een specifiek algemeen probleem voor elke geografische locatie waar gebruikers toegang hebben tot uw tenant.

Er zijn zes specifieke netwerkinzichten die kunnen worden weergegeven voor elke kantoorlocatie:

- [Backgressie van netwerk](#backhauled-network-egress)
- [Tussenapparaat netwerk](#network-intermediary-device)
- [Betere prestaties gedetecteerd voor klanten bij u in de buurt](#better-performance-detected-for-customers-near-you)
- [Gebruik van een niet-optimale front door de Exchange Online-service](#use-of-a-non-optimal-exchange-online-service-front-door)
- [Gebruik van een niet-optimale front door de SharePoint Online-service](#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [Lage downloadsnelheid van SharePoint-front door](#low-download-speed-from-sharepoint-front-door)
- [Optimaal netwerkingressie china-gebruiker](#china-user-optimal-network-egress)

Er zijn twee netwerkinzichten op tenantniveau die kunnen worden weergegeven voor de tenant. Deze worden ook weergegeven op de scorepagina's van Producvitivy:

- [Voorbeeldverbindingen in Exchange die zijn beïnvloed door verbindingsproblemen](#exchange-sampled-connections-impacted-by-connectivity-issues)
- [Voorbeeldverbindingen in SharePoint die zijn beïnvloed door verbindingsproblemen](#sharepoint-sampled-connections-impacted-by-connectivity-issues)

>[!IMPORTANT]
>Netwerkinzichten, prestatieaanbevelingen en beoordelingen in het Microsoft 365-beheercentrum hebben momenteel de preview-status en zijn alleen beschikbaar voor Microsoft 365-tenants die zijn ingeschreven voor het feature preview-programma.

## <a name="backhauled-network-egress"></a>Backgressie van netwerk

Dit inzicht wordt weergegeven als de Network Insights-service detecteert dat de afstand tussen een bepaalde gebruikerslocatie en het netwerkuitzicht groter is dan 500 kilometer (800 kilometer), waarmee wordt aangegeven dat Microsoft 365-verkeer wordt geback-mailt naar een gemeenschappelijk internetrandapparaat of -proxy.

Dit inzicht wordt in sommige overzichtsweergaven afgekort als 'Uitgangsweergaven'.

![Teruggeopend netwerkingressie](../media/m365-mac-perf/m365-mac-perf-insights-detail-backhauled.png)

### <a name="what-does-this-mean"></a>Wat betekent dit?

Hiermee wordt aangegeven dat de afstand tussen de kantoorlocatie en het netwerkingressie groter is dan 500 kilometer (800 kilometer). De kantoorlocatie wordt geïdentificeerd door een locatie van een onbekende clientmachine en de netwerklocatie wordt vastgesteld met behulp van reverse IP Address to location-databases. De kantoorlocatie is mogelijk onjuist als Windows Location Services is uitgeschakeld op computers. De netwerkingangslocatie is mogelijk onjuist als de gegevens van de omgekeerde IP-adresdatabase onjuist zijn.

Details voor dit inzicht zijn de kantoorlocatie, het geschatte percentage van het totale aantal tenantgebruikers op de locatie, de huidige netwerkingressielocatie, de relevantie van de uitgangslocatie, de afstand tussen de locatie en het huidige uitgangspunt, de datum waarop de voorwaarde voor het eerst is gedetecteerd en de datum waarop de voorwaarde is opgelost.

### <a name="what-should-i-do"></a>Wat moet ik doen?

Voor dit inzicht raden we aan dat het netwerk dichter bij de kantoorlocatie komt, zodat de connectiviteit optimaal kan worden gerouted naar het wereldwijde netwerk van Microsoft en naar de dichtstbijzijnde microsoft 365-serviceaanzicht. Als het netwerk niet ver van kantoorlocaties voor gebruikers af komt te liggen, kunnen de prestaties in de toekomst worden verbeterd omdat zowel netwerkaand dus aanwezigheidspunten als microsoft 365-service in de toekomst worden uitgebreid.

Zie voor meer informatie over hoe u dit probleem kunt oplossen, lokaal uitgangspuntnetwerkverbindingen in [Office 365-netwerkconnectiviteitsprincipes.](microsoft-365-network-connectivity-principles.md) [](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally)

## <a name="network-intermediary-device"></a>Tussenapparaat netwerk

Dit inzicht wordt weergegeven als er apparaten tussen uw gebruikers en het Microsoft-netwerk zijn gedetecteerd die van invloed kunnen zijn op de office 365-gebruikerservaring. Het is raadzaam deze te omzeilen voor specifiek Microsoft 365-netwerkverkeer dat bestemd is voor Microsoft-datacenters. Deze aanbeveling wordt bovendien beschreven in De Beginselen voor [Microsoft 365-netwerkconnectiviteit](microsoft-365-network-connectivity-principles.md)

### <a name="what-does-this-mean"></a>Wat betekent dit?

Tussenliggende apparaten van het netwerk, zoals proxyservers, VPN's en apparaten voor preventie van gegevensverlies, kunnen van invloed zijn op de prestaties en stabiliteit van Microsoft 365-clients waarbij verkeer tussenliggende clients wordt gebruikt.

### <a name="what-should-i-do"></a>Wat moet ik doen?

Configureer het tussenstation van het netwerkapparaat dat is gedetecteerd om de verwerking voor Microsoft 365-netwerkverkeer te omzeilen.

## <a name="better-performance-detected-for-customers-near-you"></a>Betere prestaties gedetecteerd voor klanten bij u in de buurt

Dit inzicht wordt weergegeven als de network insights-service detecteert dat een aanzienlijk aantal klanten in uw metrogebied betere prestaties leveren dan gebruikers in uw organisatie op deze kantoorlocatie.

Dit inzicht wordt in sommige overzichtsweergaven afgekort als 'Peers'.

![Relatieve netwerkprestaties](../media/m365-mac-perf/m365-mac-perf-insights-detail-cust-near-you.png)

### <a name="what-does-this-mean"></a>Wat betekent dit?

Dit inzicht bekijkt de statistische prestaties van Microsoft 365-klanten in dezelfde plaats als deze kantoorlocatie. Dit inzicht wordt weergegeven als de gemiddelde latentie van uw gebruikers 10% groter is dan de gemiddelde latentie van aangrenzende tenants.

### <a name="what-should-i-do"></a>Wat moet ik doen?

Er kunnen veel redenen zijn voor deze voorwaarde, waaronder latentie in uw bedrijfsnetwerk of isprovider, knelpunten of ontwerpproblemen met de architectuur. Bekijk de latentie tussen elke hop in de route tussen uw kantoornetwerk en de huidige Microsoft 365-front door. Zie de Beginselen voor [Microsoft 365-netwerkconnectiviteit voor meer informatie.](microsoft-365-network-connectivity-principles.md)

## <a name="use-of-a-non-optimal-exchange-online-service-front-door"></a>Gebruik van een niet-optimale voorzijde van Exchange Online-service

Dit inzicht wordt weergegeven als de network insights-service detecteert dat gebruikers op een specifieke locatie geen verbinding maken met een optimale front door de Exchange Online-service.

Dit inzicht wordt in sommige overzichtsweergaven afgekort als Routering.

![Niet-optimale EXO-voorzijde](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-exo.png)

### <a name="what-does-this-mean"></a>Wat betekent dit?

De frontdeuren van Exchange Online-service worden vermeld, die geschikt zijn voor gebruik vanuit de plaats op kantoorlocatie met goede prestaties. Als in de huidige test het gebruik van een Exchange Online-service front door niet in deze lijst wordt weergegeven, wordt deze aanbeveling genoemd.

### <a name="what-should-i-do"></a>Wat moet ik doen?

Het gebruik van een niet-optimale front door de Exchange Online-service kan worden veroorzaakt door netwerkbackhaul vóór het bedrijfsnetwerkuitregressie. In dit geval raden we lokaal en direct netwerkuiteringen aan. Dit kan ook worden veroorzaakt door gebruik van een externe DNS Recursive Resolver-server. In dat geval wordt u aangeraden de server DNS Recursive Resolver uit te lijnen op het netwerkuitlijningsnetwerk.

## <a name="use-of-a-non-optimal-sharepoint-online-service-front-door"></a>Gebruik van een niet-optimale front door de SharePoint Online-service

Dit inzicht wordt weergegeven als door de Network Insights-service wordt gedetecteerd dat gebruikers op een specifieke locatie geen verbinding maken met de dichtstbijzijnde front door de SharePoint Online-service.

Dit inzicht wordt in sommige overzichtsweergaven afgekort als Afd.

![Niet-optimale SPO-front door](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-spo.png)

### <a name="what-does-this-mean"></a>Wat betekent dit?

We identificeren de frontlinie van de SharePoint Online-service waar de testclient verbinding mee maakt. Voor de plaats waar kantoorlocatie wordt gevonden, vergelijken we die met de verwachte frontlinie van de SharePoint Online-service voor die plaats. Als het niet overeen komt, doen we dit.

### <a name="what-should-i-do"></a>Wat moet ik doen?

Het gebruik van een niet-optimale front door de SharePoint Online-service kan worden veroorzaakt door netwerkbackhaul vóór het bedrijfsnetwerkuitregressie. In dit geval raden we lokaal en rechtstreeks netwerkuitreeding aan. Dit kan ook worden veroorzaakt door gebruik van een externe DNS Recursive Resolver-server. In dat geval wordt u aangeraden de server DNS Recursive Resolver uit te lijnen op het netwerkuitlijningsnetwerk.

## <a name="low-download-speed-from-sharepoint-front-door"></a>Lage downloadsnelheid van SharePoint-front door

Dit inzicht wordt weergegeven als de network insights-service detecteert dat de bandbreedte tussen de specifieke kantoorlocatie en SharePoint Online minder dan 1 MBPS is.

Dit inzicht wordt in sommige overzichtsweergaven afgekort als 'Doorvoer'.

### <a name="what-does-this-mean"></a>Wat betekent dit?

De downloadsnelheid die een gebruiker via de front-doors van SharePoint Online en OneDrive voor Bedrijven kan downloaden, wordt gemeten in megabytes per seconde (MBPS). Als deze waarde kleiner is dan 1 MBPS, geven we dit inzicht.

### <a name="what-should-i-do"></a>Wat moet ik doen?

Om de downloadsnelheid te verbeteren, moet de bandbreedte mogelijk worden verhoogd. Er kunnen zich ook netwerkopstoppingen bevinden tussen de gebruikersapparaten op kantoorlocatie en de front door de SharePoint Online-service. Dit wordt ook wel congestive loss genoemd en beperkt de downloadsnelheid voor gebruikers, zelfs als er voldoende bandbreedte beschikbaar is.

## <a name="china-user-optimal-network-egress"></a>Optimaal netwerkingressie china-gebruiker

Dit inzicht wordt weergegeven als uw organisatie heeft dat gebruikers in China verbinding maken met uw Microsoft 365-tenant op andere geografische locaties. 

### <a name="what-does-this-mean"></a>Wat betekent dit?

Als uw organisatie een persoonlijke WAN-verbinding heeft, raden we u aan een NETWERK-WAN-circuit te configureren vanaf uw kantoorlocaties in China die een netwerkingressie naar internet hebben op een van de volgende locaties:

- Hongkong
- Japan 
- Taiwan
- Zuid-Korea
- Singapore
- Maleisië 

Internetuitgangspunten verder weg van gebruikers dan deze locaties verminderen de prestaties, en een uitgang in China kan leiden tot grote latentie en verbindingsproblemen door opstoppingen aan de rand van de grens.

### <a name="what-should-i-do"></a>Wat moet ik doen?

Zie de wereldwijde tenantprestatieoptimalisatie voor China-gebruikers in [Microsoft 365](microsoft-365-networking-china.md)voor meer informatie over het beperken van prestatieproblemen met betrekking tot dit inzicht.

## <a name="exchange-sampled-connections-impacted-by-connectivity-issues"></a>Voorbeeldverbindingen van Exchange die zijn beïnvloed door verbindingsproblemen

Dit inzicht geeft aan wanneer 50% of meer van de steekproefverbindingen worden beïnvloed. De impact wordt gedefinieerd door de Exchange-evaluatie lager dan 60% voor elke steekproef.

### <a name="what-does-this-mean"></a>Wat betekent dit?

Het is een indicatie dat de meerderheid van uw gebruikers waarschijnlijk problemen ondervindt met gebruikerservaring bij het maken van verbinding tussen Outlook en Exchange Online. Het percentage steekproeven vertegenwoordigt waarschijnlijk het percentage gebruikers dat minder dan 60 punten laat zien.  

### <a name="what-should-i-do"></a>Wat moet ik doen?

Schakel de zichtbaarheid van de netwerkverbinding tussen office-locaties in als u dat nog niet hebt gedaan. U wilt vaststellen welke kantoren worden beïnvloed door slechte netwerkconnectiviteit die van invloed is op Exchange en manieren vinden om de netwerkperimeter te verbeteren voor elk kantoor dat de gebruikers met het Microsoft-netwerk verbindt.

## <a name="sharepoint-sampled-connections-impacted-by-connectivity-issues"></a>Voorbeeldverbindingen in SharePoint die zijn beïnvloed door verbindingsproblemen

Dit inzicht geeft aan wanneer 50% of meer van de steekproefverbindingen worden beïnvloed. De impact wordt gedefinieerd door de SharePoint-evaluatie lager dan 40% voor elke steekproef.

### <a name="what-does-this-mean"></a>Wat betekent dit?

Het is een indicatie dat de meeste gebruikers waarschijnlijk gebruikerservaringsproblemen ondervinden met SharePoint en OneDrive. Het percentage steekproeven vertegenwoordigt waarschijnlijk het percentage gebruikers dat minder dan 40 punten laat zien.  

### <a name="what-should-i-do"></a>Wat moet ik doen?

Schakel de zichtbaarheid van de netwerkverbinding tussen office-locaties in als u dat nog niet hebt gedaan. U wilt vaststellen welke kantoren worden beïnvloed door slechte netwerkconnectiviteit die van invloed is op SharePoint en manieren vinden om de netwerkperimeter te verbeteren voor beide kantoren die de gebruikers met het Microsoft-netwerk verbinden.

## <a name="related-topics"></a>Verwante onderwerpen

[Netwerkconnectiviteit in het Microsoft 365-beheercentrum (preview)](office-365-network-mac-perf-overview.md)

[Evaluatie van het Microsoft 365-netwerk (preview)](office-365-network-mac-perf-score.md)

[Testhulpmiddel voor Microsoft 365-netwerkconnectiviteit (preview)](office-365-network-mac-perf-onboarding-tool.md)

[Microsoft 365 Network Connectivity Location Services (preview)](office-365-network-mac-location-services.md)
