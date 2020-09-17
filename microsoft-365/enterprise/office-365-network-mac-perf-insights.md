---
title: Microsoft 365 Network Insights (preview)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 04/21/2020
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
ms.openlocfilehash: a9d4dbde112c9b6c74e340824c63ce2b9749e80e
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948514"
---
# <a name="microsoft-365-network-insights-preview"></a>Microsoft 365 Network Insights (preview)

**Netwerk inzichten** zijn prestatiegegevens die worden verzameld uit uw microsoft 365-Tenant en zijn alleen beschikbaar voor weergave door beheerders gebruikers in uw Tenant. Inzichten worden weergegeven in het Microsoft 365-Beheercentrum op <https://portal.microsoft.com/adminportal/home#/networkperformance> .

Inzichten zijn bedoeld voor hulp bij het ontwerpen van netwerkverbindingen voor uw Office-locaties. Elk inzicht biedt u actuele informatie over de prestatie-eigenschappen voor een specifiek gemeenschappelijke probleem waarbij gebruikers toegang krijgen tot uw Tenant.

Er bestaan zes specifieke netwerk inzichten die voor elke kantoorlocatie kunnen worden weergegeven:

- [Backhauled netwerk uitgang](#backhauled-network-egress)
- [Betere prestaties vastgesteld voor klanten in de buurt](#better-performance-detected-for-customers-near-you)
- [Het gebruik van een niet-optimale Exchange Online-service-voor deur](#use-of-a-non-optimal-exchange-online-service-front-door)
- [Het gebruik van een niet-optimale SharePoint Online-service front deur](#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [Lage downloadsnelheid van SharePoint-voor deur](#low-download-speed-from-sharepoint-front-door)
- [Gebruikers van China optimale netwerk uitgang](#china-user-optimal-network-egress)

Er zijn twee netwerk inzichten op tenantniveau die kunnen worden weergegeven voor de Tenant. Deze worden ook weergegeven op de Score pagina's van producvitivy:

- [Gesamplinge verbindingen van Exchange beïnvloed door verbindingsproblemen](#exchange-sampled-connections-impacted-by-connectivity-issues)
- [Gepipetteerde SharePoint-verbindingen beïnvloed door verbindingsproblemen](#sharepoint-sampled-connections-impacted-by-connectivity-issues)

>[!IMPORTANT]
>Netwerk inzichten, prestatie aanbevelingen en beoordelingen in het Microsoft 365-Beheercentrum is momenteel in de preview-versie en is alleen beschikbaar voor Microsoft 365-tenants die zijn geregistreerd in het functie voorbeeldprogramma.

## <a name="backhauled-network-egress"></a>Backhauled netwerk uitgang

Dit inzicht wordt weergegeven als de Network Insights-service opspoort dat de afstand van een bepaalde gebruikerslocatie van de netwerk uitgang groter is dan 500 kilometers (800 kilometer), om aan te geven dat Microsoft 365-verkeer wordt backhauled naar een veelvoorkomende apparaat of proxy voor Internet Edge.

Dit inzicht wordt kort weergegeven als ' uitgaand ' in sommige samenvattings weergaven.

![Backhauled netwerk uitgang](../media/m365-mac-perf/m365-mac-perf-insights-detail-backhauled.png)

### <a name="what-does-this-mean"></a>Wat betekent dit?

Hiermee wordt aangegeven dat de afstand tussen de kantoorlocatie en de uitgang van het netwerk langer is dan 500 km (800 kilometer). De locatie van Office wordt aangeduid door een bemerkte locatie van de clientcomputer en de locatie van het netwerk. De kantoorlocatie is mogelijk onnauwkeurig als de Windows-locatie Services is uitgeschakeld op machines. De locatie van de netwerk uitgang is mogelijk onnauwkeurig als de informatie over de omgekeerde IP-adresdatabase onnauwkeurig is.

Details voor dit inzicht zijn de kantoorlocatie, het geschatte percentage van de totale Tenant gebruiker op de locatie, de huidige locatie van het netwerk, de relevantie van de uitzonderingslocatie, de afstand tussen de locatie en het huidige uitgangspunt, de datum waarop de voorwaarde voor het eerst is vastgesteld en de datum waarop de voorwaarde is opgelost.

### <a name="what-should-i-do"></a>Wat moet ik doen?

Om dit inzicht in te stellen, kunnen we de netwerk uitgang dichter bij de kantoorlocatie aanbevelen, zodat de verbinding optimaal kan worden gerouteerd naar het globale netwerk van Microsoft en de dichtstbijzijnde Microsoft 365-service. Als u de netwerkverbinding met de gebruikers uitsluitte, kunnen de prestaties in de toekomst ook toenemen omdat Microsoft beide netwerk punten van aanwezigheid en de Microsoft 365-service voor de toekomst uitbreidt.

Voor meer informatie over het oplossen van dit probleem, raadpleegt u [Netwerkverbindingen lokaal](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) uitzetten in de [netwerk verbindings beginselen van Office 365](microsoft-365-network-connectivity-principles.md).

## <a name="better-performance-detected-for-customers-near-you"></a>Betere prestaties vastgesteld voor klanten in de buurt

Dit inzicht wordt weergegeven als de Network Insights-service vaststelt dat een groot aantal klanten in uw metro gebied betere prestaties heeft dan de gebruikers in uw organisatie op deze locatie van Office.

Dit inzicht wordt afgekort als ' collega's ' in sommige samenvattings weergaven.

![Relatieve netwerkprestaties](../media/m365-mac-perf/m365-mac-perf-insights-detail-cust-near-you.png)

### <a name="what-does-this-mean"></a>Wat betekent dit?

Dit inzicht bestudeert de totale prestaties van Microsoft 365-klanten in dezelfde stad als deze locatie van Office. Dit inzicht wordt weergegeven als de gemiddelde latentie van uw gebruikers 10% groter is dan de gemiddelde latentie van naburige tenants.

### <a name="what-should-i-do"></a>Wat moet ik doen?

Er kunnen verschillende redenen zijn voor deze voorwaarde, zoals latentie in uw bedrijfsnetwerk of INTERNETPROVIDER, knelpunten of architectuurontwerp problemen. Bekijk de latentie tussen elke hop in de route tussen uw Office-netwerk en de huidige Microsoft 365-voor deur. Zie voor meer informatie de [beginselen voor de netwerkverbindingen van Office 365](microsoft-365-network-connectivity-principles.md).

## <a name="use-of-a-non-optimal-exchange-online-service-front-door"></a>Het gebruik van een niet-optimale Exchange Online-service-voor deur

Dit inzicht wordt weergegeven als de Network Insights-service detecteert dat gebruikers op een specifieke locatie geen verbinding maken met een optimale Exchange Online-service voor de voor deur.

Dit inzicht wordt verkort weergegeven als ' omleiding ' in sommige samenvattings weergaven.

![Niet-optimale voor deur](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-exo.png)

### <a name="what-does-this-mean"></a>Wat betekent dit?

De omruilservice voor Exchange Online-Services die geschikt zijn voor gebruik vanaf de locatie van Office-locaties, biedt goede prestaties. Als op de huidige test de front cover van de Exchange Online-service wordt gebruikt die niet in deze lijst voorkomt, dan noemen we deze aanbeveling.

### <a name="what-should-i-do"></a>Wat moet ik doen?

Het gebruik van een niet-optimale omruil bare Exchange Online-service kan worden veroorzaakt door netwerk backhaul voordat het bedrijfsnetwerk wordt uitgevoerd, zodat het een lokale en rechtstreekse netwerk uitgang voor u aanbeveelt. Dit kan ook worden veroorzaakt door het gebruik van een externe DNS recursieve resolver-server, maar het is raadzaam de DNS recursieve resolver server uit te lijnen met het netwerk uitgang.

## <a name="use-of-a-non-optimal-sharepoint-online-service-front-door"></a>Het gebruik van een niet-optimale SharePoint Online-service front deur

Dit inzicht wordt weergegeven als de Network Insights-service detecteert dat gebruikers op een specifieke locatie geen verbinding maken met de dichtstbijzijnde SharePoint Online-service-deur.

Dit inzicht wordt afgekort als ' afd ' in sommige samenvattings weergaven.

![Niet-optimale voor deur](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-spo.png)

### <a name="what-does-this-mean"></a>Wat betekent dit?

We identificeren de front cover van de SharePoint Online-service waarmee de test client verbinding maakt. Vervolgens gaan we naar de locatie van Office-locaties om te zien dat de front cover van de SharePoint Online-service voor die stad werd verwacht. Als ze niet overeenkomen, maakt u hiervan een aanbeveling.

### <a name="what-should-i-do"></a>Wat moet ik doen?

Het gebruik van een niet-optimale SharePoint Online-service voor de voor deur kan worden veroorzaakt door de netwerk backhaul voordat het bedrijfsnetwerk wordt uitgevoerd, zodat het lokale en rechtstreekse netwerk uitgang voor u adviseert. Dit kan ook worden veroorzaakt door het gebruik van een externe DNS recursieve resolver-server, maar het is raadzaam de DNS recursieve resolver server uit te lijnen met het netwerk uitgang.

## <a name="low-download-speed-from-sharepoint-front-door"></a>Lage downloadsnelheid van SharePoint-voor deur

Dit inzicht wordt weergegeven als de Network Insights-service de bandbreedte tussen de specifieke kantoorlocatie en SharePoint Online lager is dan 1 MBps.

Dit inzicht wordt afgekort als ' doorvoer ' in sommige samenvattings weergaven.

### <a name="what-does-this-mean"></a>Wat betekent dit?

De downloadsnelheid die een gebruiker uit de front-deur van SharePoint Online en de OneDrive voor bedrijven-service bevindt, wordt gemeten in megabytes per seconde (MBps). Als deze waarde lager is dan 1 MBps, bieden we deze inzichten.

### <a name="what-should-i-do"></a>Wat moet ik doen?

Om de downloadsnelheid te verbeteren, moet de bandbreedte wellicht toenemen. Het kan ook zijn dat de netwerkcongestie tussen gebruikers computers op de kantoorlocatie en de SharePoint Online-service-klep. Dit wordt ook wel congestie verlies genoemd en de beschikbare downloadsnelheid voor gebruikers wordt beperkt, zelfs als de voldoende bandbreedte beschikbaar is.

## <a name="china-user-optimal-network-egress"></a>Gebruikers van China optimale netwerk uitgang

Dit inzicht wordt weergegeven als uw organisatie gebruikers heeft in China die verbinding maken met uw Microsoft 365-Tenant in andere geografische locaties. 

### <a name="what-does-this-mean"></a>Wat betekent dit?

Als uw organisatie beschikt over een persoonlijke WAN-verbinding, wordt u aangeraden een netwerkwan-circuit te configureren op uw kantoorlocaties in China met een netwerk uitgang op Internet op een van de volgende locaties:

- Hongkong
- Japan 
- Taiwan
- Zuid-Korea
- Singapore
- Maleisië 

Verder wegteren van gebruikers van gebruikers van deze locaties reduceren de prestaties en het uitgangs niveau in China kan leiden tot hoge latentie en connectiviteitsproblemen vanwege een oplopende verbinding.

### <a name="what-should-i-do"></a>Wat moet ik doen?

Zie voor meer informatie over het beperken van de prestaties van dit inzicht de prestatie [optimalisering van Office 365 voor gebruikers van China](microsoft-365-networking-china.md).

## <a name="exchange-sampled-connections-impacted-by-connectivity-issues"></a>Gesamplinge verbindingen van Exchange beïnvloed door verbindingsproblemen

Dit inzicht zal aangeven wanneer 50% of meer van de bemonsterde verbindingen worden beïnvloed. Het effect wordt bepaald door de proef van Exchange onder 60% voor elk voorbeeld.

### <a name="what-does-this-mean"></a>Wat betekent dit?

Het is een aanwijzing dat het merendeel van de gebruikers problemen met de gebruikerservaring opneemt met Outlook waarmee verbinding wordt gemaakt met Exchange Online. Het percentage van de gepaarde steekproeven staat voor het percentage van gebruikers dat onder 60 punten wordt weergegeven.  

### <a name="what-should-i-do"></a>Wat moet ik doen?

De netwerklocatie van de Office-locatie voor netwerktoegang inschakelen als u dit nog niet hebt gedaan. U wilt weten welke kantoren zijn impactred door slechte netwerkconnectiviteit, wat van invloed is op Exchange en manieren om de netwerkverbinding te verbeteren, zodat de netwerkverbindingen van de gebruikers met de gebruikers van het Microsoft-netwerk zijn verbonden.

## <a name="sharepoint-sampled-connections-impacted-by-connectivity-issues"></a>Gepipetteerde SharePoint-verbindingen beïnvloed door verbindingsproblemen

Dit inzicht zal aangeven wanneer 50% of meer van de bemonsterde verbindingen worden beïnvloed. Het effect wordt bepaald door de SharePoint-beoordeling onder 40% voor elk voorbeeld.

### <a name="what-does-this-mean"></a>Wat betekent dit?

Het is een aanwijzing dat het merendeel van de gebruikers problemen met de gebruikerservaring met SharePoint en OneDrive ondervindt. Het percentage van de gepaarde steekproeven staat voor het percentage van gebruikers dat onder 40 punten wordt weergegeven.  

### <a name="what-should-i-do"></a>Wat moet ik doen?

De netwerklocatie van de Office-locatie voor netwerktoegang inschakelen als u dit nog niet hebt gedaan. U wilt weten welke kantoren zijn impactred door slechte netwerkconnectiviteit, wat van invloed is op SharePoint en manieren om de netwerkverbinding te verbeteren waarmee de gebruikers worden verbonden met de gebruikers van het Microsoft-netwerk.

## <a name="related-topics"></a>Verwante onderwerpen

[Aanbevelingen voor netwerkprestaties in het Microsoft 365-Beheercentrum (preview)](office-365-network-mac-perf-overview.md)

[Microsoft 365-netwerk beoordeling (preview)](office-365-network-mac-perf-score.md)

[Microsoft 365 connectiviteitstest in het M365-Beheercentrum (preview)](office-365-network-mac-perf-onboarding-tool.md)

[Locatie Services voor Microsoft 365-netwerkconnectiviteit](office-365-network-mac-location-services.md)
