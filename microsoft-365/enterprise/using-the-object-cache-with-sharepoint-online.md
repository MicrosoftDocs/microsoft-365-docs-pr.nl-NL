---
title: De objectcache gebruiken met SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 4/20/2015
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
ms.assetid: 38bc9c14-3826-449c-beb6-b1003bcbeaaf
description: In dit artikel wordt het verschil beschreven tussen het gebruik van de objectcache in SharePoint Server 2013 on-premises en SharePoint Online.
ms.openlocfilehash: 279d156a941aad6fbe7adbcf052c57f5b58c652f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695751"
---
# <a name="using-the-object-cache-with-sharepoint-online"></a>De objectcache gebruiken met SharePoint Online

In dit artikel wordt het verschil beschreven tussen het gebruik van de objectcache in SharePoint Server 2013 on-premises en SharePoint Online.
  
Er is een aanzienlijk negatief effect van het vertrouwen op de objectcache in SharePoint Online-implementatie. Elke afhankelijkheid van de objectcache in SharePoint Online vermindert de betrouwbaarheid van uw pagina. 
  
## <a name="how-the-sharepoint-online-and-sharepoint-server-2013-object-cache-works"></a>Hoe de SharePoint Online en SharePoint Server 2013-objectcache werkt

Wanneer SharePoint Server 2013 on-premises wordt gehost, beschikt de klant over persoonlijke front-endwebservers die de objectcache hosten. Dit betekent dat de cache is toegewezen aan één klant en alleen wordt beperkt door hoeveel geheugen beschikbaar is en wordt toegewezen aan de objectcache. Omdat in het on-premises scenario slechts één klant wordt gediend, hebben de front-endwebservers meestal gebruikers die steeds opnieuw aanvragen indienen bij dezelfde sites. Dit betekent dat de cache snel vol raakt en vol blijft met de lijstqueryresultaten en SharePoint objecten die uw gebruikers regelmatig aanvragen.
  
![Toont verkeer en laden naar on-premises front-endwebservers](../media/a0d38b36-4909-4abb-8d4e-4930814bb3de.png)
  
De tweede keer dat een gebruiker een pagina bezoekt, wordt de laadtijd van de pagina verbeterd. Na minimaal vier belastingen van dezelfde pagina wordt de pagina in de cache opgeslagen op alle front-endwebservers.
  
In SharePoint Online zijn er echter veel meer servers, maar ook veel meer sites. Elke gebruiker kan verbinding maken met een andere front-endwebserver die de cache niet heeft ingevuld. Of misschien wordt de cache wel ingevuld voor een server, maar de volgende gebruiker van die front-endwebserver vraagt om een pagina van een andere site. Of, zelfs als de volgende gebruiker dezelfde pagina aanvraagt als tijdens het vorige bezoek, worden ze gebalanceerd geladen naar een andere front-endwebserver die deze pagina niet in de cache heeft. In dit laatste geval helpt caching de gebruikers helemaal niet.
  
In de volgende afbeelding staat elke punt voor een pagina die een gebruiker aanvraagt en waar deze in de cache is opgeslagen. Verschillende kleuren vertegenwoordigen verschillende klanten die gezamenlijk gebruikmaken van de SaaS-infrastructuur.
  
![Toont de resultaten van objectcaching in SharePoint Online](../media/25d04011-ef83-4cb7-9e04-a6ed490f63c3.png)
  
Zoals u kunt zien in het diagram, is de kans klein dat een bepaalde gebruiker een server raakt met de in de cache opgeslagen versie van de pagina. Vanwege de grote doorvoer en het feit dat de servers worden gedeeld tussen veel sites, duurt de cache niet lang, omdat er slechts zo veel ruimte beschikbaar is voor caching.
  
Om al deze redenen is het vertrouwen op gebruikers die objecten in de cache krijgen, geen effectieve manier om te zorgen voor een hoogwaardige gebruikerservaring en laadtijden voor pagina's in SharePoint Online.
  
## <a name="if-we-cant-rely-on-the-object-cache-to-improve-performance-in-sharepoint-online-what-do-we-use-instead"></a>Als we niet kunnen vertrouwen op de objectcache om de prestaties in SharePoint Online te verbeteren, wat gebruiken we dan?

Aangezien u niet afhankelijk moet zijn van caching in SharePoint Online, moet u alternatieve ontwerpbenaderingen evalueren voor SharePoint aanpassingen die de objectcache gebruiken. Dit betekent dat u benaderingen gebruikt voor prestatieproblemen die niet afhankelijk zijn van de objectcaching om goede resultaten te leveren voor gebruikers. Dit wordt beschreven in enkele andere artikelen in deze reeks en bevat:
  
- [Navigatieopties voor SharePoint Online](navigation-options-for-sharepoint-online.md)
    
- [Minificatie en bundeling in SharePoint Online](minification-and-bundling-in-sharepoint-online.md)
    
- [De Office 365 Content Delivery Network (CDN) gebruiken met SharePoint Online](use-microsoft-365-cdn-with-spo.md)
    
- [Vertraging bij het laden van afbeeldingen en JavaScript in SharePoint Online](delay-loading-images-and-javascript-in-sharepoint-online.md)
    

