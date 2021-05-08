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
ms.openlocfilehash: ca665f4e492b071e5a387ffde0efae8336bd96bc
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245778"
---
# <a name="microsoft-365-network-insights-preview"></a>Microsoft 365 Network Insights (preview)

**Netwerkinzichten** zijn prestatiemetrische gegevens die zijn verzameld van uw Microsoft 365 tenant en die alleen kunnen worden bekeken door beheerders in uw tenant. Inzichten worden weergegeven in het Microsoft 365 beheercentrum op <https://portal.microsoft.com/adminportal/home#/networkperformance> .

Inzichten zijn bedoeld om te helpen bij het ontwerpen van netwerkperimeters voor uw kantoorlocaties. Elk inzicht bevat live details over de prestatiekenmerken voor een specifiek veelvoorkomende probleem voor elke geografische locatie waar gebruikers toegang hebben tot uw tenant.

Er zijn zes specifieke netwerkinzichten die kunnen worden weergegeven voor elke kantoorlocatie:

- [Backhauled network egress](#backhauled-network-egress)
- [Netwerkbemiddelingsapparaat](#network-intermediary-device)
- [Betere prestaties gedetecteerd voor klanten in uw buurt](#better-performance-detected-for-customers-near-you)
- [Gebruik van een niet-optimale Exchange Online servicedeuren](#use-of-a-non-optimal-exchange-online-service-front-door)
- [Gebruik van een niet-optimale SharePoint onlineservice voor de deur](#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [Lage downloadsnelheid van SharePoint voor deur](#low-download-speed-from-sharepoint-front-door)
- [China user optimal network egress](#china-user-optimal-network-egress)

Er zijn twee netwerkinzichten op tenantniveau die mogelijk worden weergegeven voor de tenant. Deze worden ook weergegeven op de pagina's met productiviteitsscores:

- [Exchange verbindingen die zijn beïnvloed door verbindingsproblemen](#exchange-sampled-connections-impacted-by-connectivity-issues)
- [SharePoint verbindingen die zijn beïnvloed door verbindingsproblemen](#sharepoint-sampled-connections-impacted-by-connectivity-issues)

>[!IMPORTANT]
>Netwerkinzichten, prestatieaanbevelingen en evaluaties in het Microsoft 365-beheercentrum hebben momenteel de preview-status en zijn alleen beschikbaar voor Microsoft 365-tenants die zijn geregistreerd voor het functievoorbeeldprogramma.

## <a name="backhauled-network-egress"></a>Backhauled network egress

Dit inzicht wordt weergegeven als de netwerkinzichtservice detecteert dat de afstand van een bepaalde gebruikerslocatie tot het netwerkuitje groter is dan 800 kilometer, wat aangeeft dat Microsoft 365-verkeer wordt teruggeplaatst naar een gemeenschappelijk internetrandapparaat of proxy.

Dit inzicht wordt in sommige overzichtsweergaven afgekort als 'Uittreding'.

> [!div class="mx-imgBorder"]
> ![Backhauled network egress](../media/m365-mac-perf/m365-mac-perf-insights-detail-backhauled.png)

### <a name="what-does-this-mean"></a>Wat betekent dit?

Hiermee wordt aangegeven dat de afstand tussen de kantoorlocatie en het netwerk een afstand van meer dan 800 kilometer heeft. De kantoorlocatie wordt geïdentificeerd door een obfuscated clientapparaatlocatie en de netwerklocatie wordt geïdentificeerd met behulp van omgekeerde IP-adres-naar-locatiedatabases. De kantoorlocatie kan onnauwkeurig zijn als Windows Locatieservices is uitgeschakeld op machines. De locatie van het netwerk kan onnauwkeurig zijn als de gegevens van de reverse IP-adresdatabase onjuist zijn.

Details voor dit inzicht zijn de kantoorlocatie, het geschatte percentage van de totale tenantgebruiker op de locatie, de huidige netwerklocatie, de relevantie van de uitgangslocatie, de afstand tussen de locatie en het huidige uitgangspunt, de datum waarop de voorwaarde voor het eerst is gedetecteerd en de datum waarop de voorwaarde is opgelost.

### <a name="what-should-i-do"></a>Wat moet ik doen?

Voor dit inzicht wordt aangeraden om het netwerk dichter bij de kantoorlocatie te laten lopen, zodat de connectiviteit optimaal kan worden doorgeleid naar het globale netwerk van Microsoft en naar de dichtstbijzijnde Microsoft 365 voorde deur van de service. Het sluiten van netwerkverbreding voor officelocaties van gebruikers zorgt ook voor betere prestaties in de toekomst, aangezien Microsoft in de toekomst zowel netwerkpunten van aanwezigheid als Microsoft 365-servicedeuren uitbreidt.

Zie Netwerkverbindingen lokaal in Office 365 [Netwerkconnectiviteitsprincipes](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) voor meer informatie over het oplossen van dit [probleem.](microsoft-365-network-connectivity-principles.md)

## <a name="network-intermediary-device"></a>Netwerkbemiddelingsapparaat

Dit inzicht wordt weergegeven als we apparaten tussen uw gebruikers en het microsoft-netwerk hebben gedetecteerd die van invloed kunnen zijn op de Office 365 gebruikerservaring. Het is raadzaam deze te omzeilen voor specifieke Microsoft 365 netwerkverkeer dat is bestemd voor Microsoft-datacenters. Deze aanbeveling wordt bovendien beschreven in [Microsoft 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md). 

Een tussenpersoonsinzicht dat we laten zien is SSL-onderbreking en -inspectie wanneer kritieke Office 365 netwerk-eindpunten voor Exchange, SharePoint en Teams worden onderschept en ontsleuteld door netwerktussenliggende apparaten.

### <a name="what-does-this-mean"></a>Wat betekent dit?

Netwerktussenliggende apparaten, zoals proxyservers, VPN's en preventieapparaten voor gegevensverlies, kunnen van invloed zijn op de prestaties en stabiliteit van Microsoft 365 clients waar verkeer wordt tussenbemiddeld.

### <a name="what-should-i-do"></a>Wat moet ik doen?

Configureer het netwerktussenapparaat dat is gedetecteerd om de verwerking voor Microsoft 365 netwerkverkeer te omzeilen.

## <a name="better-performance-detected-for-customers-near-you"></a>Betere prestaties gedetecteerd voor klanten in uw buurt

Dit inzicht wordt weergegeven als de netwerkinzichtservice detecteert dat een aanzienlijk aantal klanten in uw metrogebied betere prestaties heeft dan gebruikers in uw organisatie op deze kantoorlocatie.

Dit inzicht wordt in sommige overzichtsweergaven afgekort als 'Peers'.

> [!div class="mx-imgBorder"]
> ![Relatieve netwerkprestaties](../media/m365-mac-perf/m365-mac-perf-insights-detail-cust-near-you.png)

### <a name="what-does-this-mean"></a>Wat betekent dit?

In dit inzicht worden de statistische prestaties van Microsoft 365 klanten in dezelfde plaats als deze kantoorlocatie onderzocht. Dit inzicht wordt weergegeven als de gemiddelde latentie van uw gebruikers 10% groter is dan de gemiddelde latentie van aangrenzende tenants.

### <a name="what-should-i-do"></a>Wat moet ik doen?

Er kunnen veel redenen zijn voor deze voorwaarde, waaronder latentie in uw bedrijfsnetwerk of isp, knelpunten of ontwerpproblemen met architectuur. Bekijk de latentie tussen elke hop in de route tussen uw kantoornetwerk en de huidige Microsoft 365 voor deur. Zie voor meer informatie [Microsoft 365 Netwerkconnectiviteitsbeginselen.](microsoft-365-network-connectivity-principles.md)

## <a name="use-of-a-non-optimal-exchange-online-service-front-door"></a>Gebruik van een niet-optimale Exchange Online servicedeuren

Dit inzicht wordt weergegeven als de netwerkinzichtservice detecteert dat gebruikers op een specifieke locatie geen verbinding maken met een optimale Exchange Online servicedeuren.

Dit inzicht wordt in sommige overzichtsweergaven afgekort als Routering.

> [!div class="mx-imgBorder"]
> ![Niet-optimale EXO-voordeur](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-exo.png)

### <a name="what-does-this-mean"></a>Wat betekent dit?

We geven Exchange Online servicedeuren weer die geschikt zijn voor gebruik vanuit de kantoorlocatie met goede prestaties. Als in de huidige test het gebruik van een Exchange Online in deze lijst wordt weergegeven, wordt deze aanbeveling aanbevolen.

### <a name="what-should-i-do"></a>Wat moet ik doen?

Het gebruik van een niet-Exchange Online-servicedeuren kan worden veroorzaakt door netwerkbackhaul voordat het bedrijfsnetwerk uitkomt. In dat geval raden we lokale en directe netwerkuittreding aan. Dit kan ook worden veroorzaakt door het gebruik van een externe DNS Recursive Resolver-server, in welk geval het raadzaam is om de DNS Recursive Resolver-server uit te lijnen met het netwerkuitstroom.

## <a name="use-of-a-non-optimal-sharepoint-online-service-front-door"></a>Gebruik van een niet-optimale SharePoint onlineservice voor de deur

Dit inzicht wordt weergegeven als de netwerkinzichtservice detecteert dat gebruikers op een specifieke locatie geen verbinding maken met de dichtstbijzijnde SharePoint Online-servicedeuren.

Dit inzicht wordt in sommige overzichtsweergaven afgekort als 'Afd'.

> [!div class="mx-imgBorder"]
> ![Niet-optimale SPO-voordeur](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-spo.png)

### <a name="what-does-this-mean"></a>Wat betekent dit?

We identificeren de SharePoint onlineservice waar de testclient verbinding mee maakt. Voor de locatie van het kantoor vergelijken we dat met de verwachte SharePoint onlineservice voor die stad. Als deze niet overeenkomen, doen we deze aanbeveling.

### <a name="what-should-i-do"></a>Wat moet ik doen?

Het gebruik van een niet-optimale SharePoint Online-servicedeuren kan worden veroorzaakt door backhaul van het netwerk voordat het bedrijfsnetwerk uitkomt. In dat geval raden we lokale en directe netwerkuittreding aan. Dit kan ook worden veroorzaakt door het gebruik van een externe DNS Recursive Resolver-server, in welk geval het raadzaam is om de DNS Recursive Resolver-server uit te lijnen met het netwerkuitstroom.

## <a name="low-download-speed-from-sharepoint-front-door"></a>Lage downloadsnelheid van SharePoint voor deur

Dit inzicht wordt weergegeven als de netwerkinzichtservice detecteert dat de bandbreedte tussen de specifieke kantoorlocatie en SharePoint Online kleiner is dan 1 MBps.

Dit inzicht wordt in sommige overzichtsweergaven afgekort als 'Doorvoer'.

### <a name="what-does-this-mean"></a>Wat betekent dit?

De downloadsnelheid die een gebruiker kan krijgen van SharePoint Online en OneDrive voor Bedrijven servicedeuren wordt gemeten in megabytes per seconde (MBps). Als deze waarde kleiner is dan 1 MBps, bieden we dit inzicht.

### <a name="what-should-i-do"></a>Wat moet ik doen?

Als u de downloadsnelheid wilt verbeteren, moet de bandbreedte mogelijk worden verhoogd. U kunt ook netwerkopstoppingen veroorzaken tussen gebruikersapparaten op de kantoorlocatie en de SharePoint onlineservicedeuren. Dit wordt soms congestief verlies genoemd en beperkt de downloadsnelheid die beschikbaar is voor gebruikers, zelfs als er voldoende bandbreedte beschikbaar is.

## <a name="china-user-optimal-network-egress"></a>China user optimal network egress

Dit inzicht wordt weergegeven als uw organisatie gebruikers in China heeft die verbinding maken met uw Microsoft 365 tenant op andere geografische locaties. 

### <a name="what-does-this-mean"></a>Wat betekent dit?

Als uw organisatie een privé WAN-verbinding heeft, raden we u aan om een NETWERK WAN-circuit te configureren vanaf uw kantoorlocaties in China met netwerktoegang tot internet op een van de volgende locaties:

- Hongkong
- Japan 
- Taiwan
- Zuid-Korea
- Singapore
- Maleisië 

Internetuitgang verder weg van gebruikers dan deze locaties vermindert de prestaties en een uittreding in China kan leiden tot hoge latentie- en verbindingsproblemen als gevolg van congestie over de grens.

### <a name="what-should-i-do"></a>Wat moet ik doen?

Zie voor meer informatie over het beperken van prestatieproblemen met betrekking tot dit inzicht Microsoft 365 algemene [tenantprestatieoptimalisatie voor Gebruikers van China.](microsoft-365-networking-china.md)

## <a name="exchange-sampled-connections-impacted-by-connectivity-issues"></a>Exchange verbindingen die zijn beïnvloed door verbindingsproblemen

Dit inzicht laat zien wanneer 50% of meer van de bemonsterde verbindingen worden beïnvloed. De impact wordt gedefinieerd door de Exchange die lager is dan 60% voor elk voorbeeld.

### <a name="what-does-this-mean"></a>Wat betekent dit?

Het is een indicatie dat de meeste gebruikers waarschijnlijk last hebben van gebruikerservaringsproblemen met Outlook verbinding maken met Exchange Online. Het percentage steekproeven vertegenwoordigt waarschijnlijk het percentage gebruikers dat onder de 60 punten wordt weergegeven.  

### <a name="what-should-i-do"></a>Wat moet ik doen?

Schakel zichtbaarheid van officelocatienetwerkconnectiviteit in als u dit nog niet hebt gedaan. U wilt bepalen welke kantoren worden beïnvloed door slechte netwerkconnectiviteit die van invloed is op Exchange en manieren zoeken om de netwerkperimeter te verbeteren bij elk kantoor dat de gebruikers verbindt met het netwerk van Microsoft.

## <a name="sharepoint-sampled-connections-impacted-by-connectivity-issues"></a>SharePoint verbindingen die zijn beïnvloed door verbindingsproblemen

Dit inzicht laat zien wanneer 50% of meer van de bemonsterde verbindingen worden beïnvloed. De impact wordt gedefinieerd door de SharePoint die lager is dan 40% voor elk voorbeeld.

### <a name="what-does-this-mean"></a>Wat betekent dit?

Het is een indicatie dat de meeste gebruikers waarschijnlijk te maken hebben met gebruikerservaringsproblemen met SharePoint en OneDrive. Het percentage steekproeven vertegenwoordigt waarschijnlijk het percentage gebruikers dat onder de 40 punten wordt weergegeven.  

### <a name="what-should-i-do"></a>Wat moet ik doen?

Schakel zichtbaarheid van officelocatienetwerkconnectiviteit in als u dit nog niet hebt gedaan. U wilt bepalen welke kantoren worden beïnvloed door slechte netwerkconnectiviteit die van invloed is op SharePoint en manieren vinden om de netwerkperimeter te verbeteren bij elk kantoor dat de gebruikers verbindt met het microsoft-netwerk.

## <a name="related-topics"></a>Verwante onderwerpen

[Netwerkconnectiviteit in het Microsoft 365 beheercentrum (voorbeeld)](office-365-network-mac-perf-overview.md)

[Microsoft 365 netwerkbeoordeling (voorbeeld)](office-365-network-mac-perf-score.md)

[Microsoft 365 testprogramma voor netwerkconnectiviteit (voorbeeld)](office-365-network-mac-perf-onboarding-tool.md)

[Microsoft 365 Network Connectivity Location Services (preview)](office-365-network-mac-location-services.md)
