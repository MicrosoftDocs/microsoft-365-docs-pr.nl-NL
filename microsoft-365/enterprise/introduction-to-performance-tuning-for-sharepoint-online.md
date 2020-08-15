---
title: Inleiding tot het optimaliseren van de prestaties voor SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/22/2018
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid: SPO160
ms.assetid: 81c4be5f-327e-435d-a568-526d68cffef0
description: In dit artikel wordt uitgelegd welke specifieke aspecten u moet nemen bij het ontwerpen van pagina's voor de beste prestaties in SharePoint Online.
ms.openlocfilehash: d3a9dedbd5812774b81494af0f8defa5568f7dac
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689449"
---
# <a name="introduction-to-performance-tuning-for-sharepoint-online"></a>Inleiding tot het optimaliseren van de prestaties voor SharePoint Online

In dit artikel wordt uitgelegd welke specifieke aspecten u moet nemen bij het ontwerpen van pagina's voor de beste prestaties in SharePoint Online.
     
## <a name="sharepoint-online-metrics"></a>SharePoint Online-metrieken

De volgende algemene metrische gegevens voor SharePoint Online zorgen voor actuele wereld informatie over de prestaties:
  
- Hoe snel pagina's worden geladen
    
- Hoeveel reis uitnodigingen per pagina zijn vereist
    
- Problemen met de service
    
- Andere dingen die leiden tot verminderde prestaties
    
### <a name="conclusions-reached-because-of-the-data"></a>Conclusies op basis van de gegevens

De gegevens melden ons:
  
- Het merendeel van de pagina's is geschikt voor SharePoint Online.
    
- Niet-aangepaste pagina's worden zeer snel geladen.
    
- OneDrive voor bedrijven, team sites en systeem pagina's, zoals _layouts, enzovoort, worden allemaal snel geladen.
    
- De meest traagste 1% van de SharePoint Online-pagina's kost meer dan 5.000 milliseconden.
    
Eén eenvoudige Bench type-test die u kunt gebruiken om de prestaties van uw eigen portal te vergelijken met de laadtijd van de startpagina van OneDrive voor bedrijven, aangezien deze gebruikmaakt van enkele aangepaste functies. Dit is vaak de eerste stap die u moet uitvoeren wanneer u problemen met de netwerkprestaties oplost.
  
## <a name="use-a-standard-user-account-when-checking-performance"></a>Een standaardgebruikersaccount gebruiken bij het controleren van de prestaties

Een beheerder van een siteverzameling, site-eigenaar, editor of Inzender behoort tot extra beveiligingsgroepen, heeft extra machtigingen en bevat daarom extra elementen die in SharePoint op een pagina worden geladen.
  
Dit geldt voor on-premises SharePoint en SharePoint Online, maar in een on-premises scenario worden de verschillen niet zo gemakkelijk weergegeven als in SharePoint Online.
  
Om te bepalen hoe een pagina voor gebruikers moet worden uitgevoerd, moet u een standaardgebruikersaccount gebruiken om te voorkomen dat u de creatie besturingselementen en extra verkeer met betrekking tot beveiligingsgroepen kunt laden.
  
## <a name="connection-categories-for-performance-tuning"></a>Verbindings categorieën voor prestatieafstemming

U kunt de verbindingen tussen de server en de gebruiker categoriseren met drie belangrijkste onderdelen. U kunt deze bij het ontwerpen van SharePoint Online-pagina's voor inzicht in laadtijden.
  
- De **Server** De servers die Microsoft hosten in datacenters.
    
- **Netwerk** Het Microsoft-netwerk, Internet en uw on-premises netwerk tussen het datacenter en uw gebruikers.
    
- **Browser** Waar de pagina wordt geladen.
    
Binnen deze drie verbindingen zijn meestal vijf redenen die 95% van de traagste pagina's veroorzaken. Dit artikel bevat de volgende redenen:
  
- Problemen met navigeren
    
- Inhoud samengevouwen
    
- Grote bestanden
    
- Veel aanvragen voor de server
    
- Verwerking van webonderdelen
    
### <a name="server-connection"></a>Server verbinding

Veel van de problemen die de prestaties beïnvloeden van on-premises SharePoint zijn ook van toepassing op SharePoint Online.
  
Zoals u zou verwachten, hebt u veel meer controle over de implementatie van servers met on-premises SharePoint. Met SharePoint Online-dingen zijn iets anders. Hoe meer werken u maakt met een server, hoe langer het duurt voor een pagina wordt weergegeven. Met SharePoint is de grootste probleem voor dit opzicht ingewikkelde pagina's met meerdere webonderdelen.
  
SharePoint Server on-premises
  
![Schermafbeelding van de server on-premises](../media/a8e9b646-cdff-4131-976a-b5f891da44ac.png)
  
SharePoint Online
  
![Schermafbeelding van server online](../media/46b27ded-d8a4-4287-b3e0-2603a764b8f8.png)
  
Met SharePoint Online kunnen bepaalde pagina aanvragen uiteindelijk meerdere servers beëindigen. U kunt uiteindelijk een matrix met aanvragen tussen servers voor een afzonderlijke aanvraag beëindigen. Deze interacties zijn kostbaar van een perspectief voor het laden van pagina's en werken hierdoor te traag.
  
Voorbeelden van de interacties van servers naar servers zijn:
  
- Web-naar SQL-servers
    
- Web-naar toepassingsservers
    
Een andere manier om de server interacties te vertragen, is Cachemissers. In tegenstelling tot on-premises SharePoint is er een zeer compacte uitzooming en gaat u naar de server die u eerder hebt bezocht. Hierdoor wordt de objectcache verouderd.
  
### <a name="network-connection"></a>Netwerkverbinding

Met een on-premises SharePoint dat geen gebruik maakt van een WAN, mag u een snelle verbinding gebruiken tussen datacenter en eindgebruikers. In het algemeen kunt u eenvoudig zaken beheren vanuit een netwerk perspectief.
  
Met SharePoint Online zijn er een paar factoren waarmee u rekening moet houden; voorbeeld:
  
- Het Microsoft-netwerk
    
- Internet
    
- De INTERNETPROVIDER
    
Ongeacht welke versie van SharePoint (en welk netwerk) u gebruikt, is het mogelijk dat het netwerk meestal bezet is:
  
- Grote nettolading
    
- Veel bestanden
    
- Grote fysieke afstand tot de server
    
Eén functie die u in SharePoint Online kunt benutten, is het Microsoft CDN (Content Delivery Network). Een CDN is een gedistribueerde verzameling servers die wordt geïmplementeerd via meerdere datacenters. Met een CDN kunnen inhoud op pagina's op een server worden gehost op de client, zelfs als de client ver weg is van de oorspronkelijke SharePoint-Server. Microsoft zal dit meer in de toekomst gebruiken voor het opslaan van lokale exemplaren van pagina's die niet kunnen worden aangepast, zoals de startpagina van de SharePoint Online-beheerder. Zie [netwerken die inhoud leveren](content-delivery-networks.md)voor meer informatie over cdn's.
  
Als u op de hoogte bent van de verbindingssnelheid van uw internetprovider, moet u op de hoogte blijven van de verbindingssnelheid van uw internetprovider. Met een eenvoudige snelheids test kunt u de verbindingssnelheid aangeven.
  
### <a name="browser-connection"></a>Browser verbinding

U kunt ook met webbrowsers van een prestatie perspectief rekening houden.
  
Het bezoeken van ingewikkelde pagina's heeft invloed op de prestaties. De meeste browsers hebben alleen een kleine cache (rondom 90MB), terwijl de gemiddelde webpagina doorgaans ongeveer 1,6 MB is. Dit duurt niet lang.
  
Bandbreedte kan ook een probleem zijn. Als een gebruiker bijvoorbeeld Video's bekijkt in een andere sessie, is dit van invloed op de prestaties van de SharePoint-pagina. Wanneer u niet kunt voorkomen dat gebruikers van streaming media streaming kunnen voorkomen, kunt u bepalen hoe een pagina wordt geladen voor gebruikers.
  
Raadpleeg de volgende artikelen voor verschillende technieken voor het aanpassen van SharePoint Online-pagina's en andere aanbevolen procedures voor het optimaliseren van de prestaties.
  
- [Navigatieopties voor SharePoint Online](navigation-options-for-sharepoint-online.md)
    
- [Het hulpprogramma pagina diagnose voor SharePoint Online gebruiken](page-diagnostics-for-spo.md)
    
- [Afbeeldingen optimaliseren voor SharePoint Online](image-optimization-for-sharepoint-online.md)
    
- [Laden van afbeeldingen en JavaScript vertragen in SharePoint Online](delay-loading-images-and-javascript-in-sharepoint-online.md)
    
- [Minification en bundeling in SharePoint Online](minification-and-bundling-in-sharepoint-online.md)
    
- [Het Office 365 Content Delivery Network (CDN) gebruiken met SharePoint Online](use-microsoft-365-cdn-with-spo.md)
    
- [Het webonderdeel inhoud zoeken in plaats van het webonderdeel inhouds query gebruiken om de prestaties te verbeteren in SharePoint Online](using-content-search-web-part-instead-of-content-query-web-part-to-improve-perfo.md)
    
- [Capaciteitsplanning en belastingtest van SharePoint Online](capacity-planning-and-load-testing-sharepoint-online.md)
    
- [Prestatieproblemen met SharePoint Online vaststellen](diagnosing-performance-issues-with-sharepoint-online.md)
    
- [De objectcache gebruiken met SharePoint Online](using-the-object-cache-with-sharepoint-online.md)
    
- [Procedure: vertraging of blokkering voorkomen in SharePoint Online](https://msdn.microsoft.com/library/office/dn889829.aspx)
    

