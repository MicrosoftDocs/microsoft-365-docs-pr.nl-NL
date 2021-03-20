---
title: Inleiding tot prestatieafstemming voor SharePoint Online
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
description: In dit artikel wordt uitgelegd welke specifieke aspecten u moet overwegen bij het ontwerpen van pagina's voor de beste prestaties in SharePoint Online.
ms.openlocfilehash: 6f40243c9d6a1657b6716a071288f5b4fb018164
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909736"
---
# <a name="introduction-to-performance-tuning-for-sharepoint-online"></a>Inleiding tot prestatieafstemming voor SharePoint Online

In dit artikel wordt uitgelegd welke specifieke aspecten u moet overwegen bij het ontwerpen van pagina's voor de beste prestaties in SharePoint Online.
     
## <a name="sharepoint-online-metrics"></a>SharePoint Online-statistieken

De volgende algemene metrische gegevens voor SharePoint Online bieden gegevens over prestaties in de echte wereld:
  
- Hoe snel pagina's worden geladen
    
- Hoeveel retourreizen per pagina zijn vereist
    
- Problemen met de service
    
- Andere dingen die prestatiedegradatie veroorzaken
    
### <a name="conclusions-reached-because-of-the-data"></a>Conclusies die zijn bereikt vanwege de gegevens

De gegevens vertellen ons:
  
- De meeste pagina's presteren goed in SharePoint Online.
    
- Niet-aangepaste pagina's worden zeer snel geladen.
    
- OneDrive voor Bedrijven, teamsites en systeempagina's, zoals _layouts, enzovoort, zijn allemaal snel te laden.
    
- De traagste 1% van de SharePoint Online-pagina's duurt meer dan 5.000 milliseconden om te laden.
    
Een eenvoudige benchmarktest die u kunt gebruiken, is het meten van de prestaties door de laadtijd van uw eigen portal te vergelijken met de laadtijd van de startpagina van OneDrive voor Bedrijven, omdat er weinig aangepaste functies worden gebruikt. Dit is vaak de eerste stap Die ondersteuning vraagt u om in te vullen bij het oplossen van problemen met netwerkprestaties.
  
## <a name="use-a-standard-user-account-when-checking-performance"></a>Een standaardgebruikersaccount gebruiken bij het controleren van de prestaties

Een beheerder van de siteverzameling, site-eigenaar, editor of inzender behoren tot extra beveiligingsgroepen, hebben extra machtigingen en hebben daarom extra elementen die door SharePoint op een pagina worden geladen.
  
Dit is van toepassing op on-premises SharePoint en SharePoint Online, maar in een on-premises scenario zijn de verschillen niet zo gemakkelijk op te merken als in SharePoint Online.
  
Als u de prestaties van een pagina voor gebruikers correct wilt evalueren, moet u een standaardgebruikersaccount gebruiken om te voorkomen dat de ontwerpbesturingselementen en extra verkeer met betrekking tot beveiligingsgroepen worden geladen.
  
## <a name="connection-categories-for-performance-tuning"></a>Verbindingscategorieën voor prestatieafstemming

U kunt de verbindingen tussen de server en de gebruiker categoriseren in drie hoofdonderdelen. Houd hier rekening mee bij het ontwerpen van SharePoint Online-pagina's voor inzicht in laadtijden.
  
- **Server** De servers die microsoft host in datacenters.
    
- **Netwerk** Het Microsoft-netwerk, internet en uw on-premises netwerk tussen het datacenter en uw gebruikers.
    
- **Browser** Waar de pagina is geladen.
    
Binnen deze drie verbindingen zijn er meestal vijf redenen die 95% van de trage pagina's veroorzaken. Elk van deze redenen wordt besproken in dit artikel:
  
- Navigatieproblemen
    
- Inhouds roll-up
    
- Grote bestanden
    
- Veel aanvragen voor de server
    
- Webonderdeelverwerking
    
### <a name="server-connection"></a>Serververbinding

Veel van de problemen die van invloed zijn op de prestaties met on-premises SharePoint zijn ook van toepassing op SharePoint Online.
  
Zoals u zou verwachten, hebt u veel meer controle over de manier waarop servers presteren met on-premises SharePoint. Met SharePoint Online zijn dingen iets anders. Hoe meer werk een server moet doen, hoe langer het duurt om een pagina weer te geven. In SharePoint zijn complexe pagina's met meerdere webonderdelen de grootste boosdoener in dit opzicht.
  
On-premises SharePoint Server
  
![Schermafbeelding van server on premises](../media/a8e9b646-cdff-4131-976a-b5f891da44ac.png)
  
SharePoint Online
  
![Schermafbeelding van server online](../media/46b27ded-d8a4-4287-b3e0-2603a764b8f8.png)
  
Met SharePoint Online kunnen bepaalde paginaaanvragen uiteindelijk meerdere servers bellen. U kunt eindigen met een matrix met aanvragen tussen servers voor een afzonderlijke aanvraag. Deze interacties zijn duur vanuit het laadperspectief van een pagina en zorgen ervoor dat de dingen traag worden.
  
Voorbeelden van deze server- en serverinteracties zijn:
  
- Web naar SQL-servers
    
- Web-to-application servers
    
Het andere wat serverinteracties kan vertragen, is cache-missers. In tegenstelling tot on-premises SharePoint is de kans zeer klein dat u dezelfde server gebruikt voor een pagina die u eerder hebt bezocht. Dit maakt object caching verouderd.
  
### <a name="network-connection"></a>Netwerkverbinding

Met on-premises SharePoint die geen gebruik maakt van een WAN, kunt u een snelle verbinding tussen datacenter en eindgebruikers gebruiken. Over het algemeen zijn de zaken eenvoudig te beheren vanuit een netwerkperspectief.
  
Met SharePoint Online zijn er nog een paar factoren waar u rekening mee moet houden. bijvoorbeeld:
  
- Het Microsoft-netwerk
    
- The Internet
    
- De isp
    
Ongeacht welke versie van SharePoint (en welk netwerk) u gebruikt, zijn de volgende zaken waardoor het netwerk bezet is:
  
- Grote laadvermogen
    
- Veel bestanden
    
- Grote fysieke afstand tot de server
    
Een functie die u kunt gebruiken in SharePoint Online is het Microsoft CDN (Content Delivery Network). Een CDN is in feite een gedistribueerde verzameling servers die is geïmplementeerd in meerdere datacenters. Met een CDN kan inhoud op pagina's worden gehost op een server dicht bij de client, zelfs als de client ver van de oorspronkelijke SharePoint Server ligt. Microsoft gebruikt dit in de toekomst meer om lokale exemplaren op te slaan van pagina's die niet kunnen worden aangepast, bijvoorbeeld de startpagina van de SharePoint Online-beheerder. Zie Inhoudsleveringsnetwerken voor meer informatie over [CDN's.](content-delivery-networks.md)
  
Iets waar u rekening mee moet houden, maar waar u mogelijk niet veel aan kunt doen, is de verbindingssnelheid van uw internetprovider. Met een eenvoudig snelheidstestprogramma ziet u de verbindingssnelheid.
  
### <a name="browser-connection"></a>Browserverbinding

Er zijn een paar factoren waar u rekening mee moet houden met webbrowsers vanuit prestatieperspectief.
  
Het bezoeken van complexe pagina's is van invloed op de prestaties. De meeste browsers hebben slechts een kleine cache (ongeveer 90 MB), terwijl de gemiddelde webpagina meestal rond de 1,6 MB ligt. Dit duurt niet lang om te wennen.
  
Bandbreedte kan ook een probleem zijn. Als een gebruiker bijvoorbeeld video's bekijkt in een andere sessie, is dit van invloed op de prestaties van uw SharePoint-pagina. Hoewel u niet kunt voorkomen dat gebruikers media streamen, kunt u bepalen hoe een pagina wordt geladen voor gebruikers.
  
Bekijk de volgende artikelen voor verschillende aanpassingstechnieken voor sharePoint Online-pagina's en andere best practices om optimale prestaties te bereiken.
  
- [Navigatieopties voor SharePoint Online](navigation-options-for-sharepoint-online.md)
    
- [Het hulpprogramma Paginadiagnose gebruiken voor SharePoint Online](page-diagnostics-for-spo.md)
    
- [Afbeeldingsoptimalisatie voor SharePoint Online](image-optimization-for-sharepoint-online.md)
    
- [Vertraging bij het laden van afbeeldingen en JavaScript in SharePoint Online](delay-loading-images-and-javascript-in-sharepoint-online.md)
    
- [Minificatie en bundeling in SharePoint Online](minification-and-bundling-in-sharepoint-online.md)
    
- [Het Office 365 Content Delivery Network (CDN) gebruiken met SharePoint Online](use-microsoft-365-cdn-with-spo.md)
    
- [Webonderdeel Inhoud zoeken gebruiken in plaats van webonderdeel Inhoudsquery om de prestaties in SharePoint Online te verbeteren](using-content-search-web-part-instead-of-content-query-web-part-to-improve-perfo.md)
    
- [Capaciteitsplanning en belastingtest van SharePoint Online](capacity-planning-and-load-testing-sharepoint-online.md)
    
- [Prestatieproblemen met SharePoint Online diagnosticeren](diagnosing-performance-issues-with-sharepoint-online.md)
    
- [De objectcache gebruiken met SharePoint Online](using-the-object-cache-with-sharepoint-online.md)
    
- [How to: Voorkomen dat u wordt beperkt of geblokkeerd in SharePoint Online](/sharepoint/dev/general-development/how-to-avoid-getting-throttled-or-blocked-in-sharepoint-online)
