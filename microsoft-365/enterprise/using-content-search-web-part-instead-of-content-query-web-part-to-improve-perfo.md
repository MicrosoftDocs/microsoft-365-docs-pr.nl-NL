---
title: Het webonderdeel inhoud zoeken in plaats van het webonderdeel inhouds query gebruiken om de prestaties te verbeteren in SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 4/20/2015
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- SPO160
ms.assetid: e8ce6b72-745b-464a-85c7-cbf6eb53391b
description: Meer informatie over hoe u de prestaties kunt verbeteren door het webonderdeel inhouds query te vervangen door het webonderdeel inhoud zoeken in SharePoint Server 2013 en SharePoint Online.
ms.openlocfilehash: e5f57e59a421d79302f447e229091fdfc96f1237
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689549"
---
# <a name="using-content-search-web-part-instead-of-content-query-web-part-to-improve-performance-in-sharepoint-online"></a>Het webonderdeel inhoud zoeken in plaats van het webonderdeel inhouds query gebruiken om de prestaties te verbeteren in SharePoint Online

In dit artikel wordt uitgelegd hoe u de prestaties kunt verbeteren door het webonderdeel inhouds query te vervangen door het webonderdeel inhoud zoeken in SharePoint Server 2013 en SharePoint Online.
  
Een van de krachtigste nieuwe functies van SharePoint Server 2013 en SharePoint Online is het webonderdeel inhoud zoeken (WEBONDERDEEL inhoud zoeken). Dit webonderdeel maakt gebruik van de zoekindex om snel resultaten op te halen die aan de gebruiker worden getoond. Gebruik het webonderdeel inhoud zoeken in plaats van het webonderdeel inhouds query (CQWP) op uw pagina's om de prestaties van uw gebruikers te verbeteren.
  
Het gebruik van een webonderdeel inhoud zoeken via een webonderdeel inhouds query levert bijna altijd betere resultaten op voor het laden van pagina's in SharePoint Online. Er is een beetje extra configuratie ter verbetering van de juiste query, maar de voordelen zijn voor betere prestaties en tevredenere gebruikers.
  
## <a name="comparing-the-performance-gain-you-get-from-using-content-search-web-part-instead-of-content-query-web-part"></a>Wanneer u de prestaties vergelijkt met het gebruik van het webonderdeel inhoud zoeken in plaats van het webonderdeel inhouds query

In het volgende voorbeeld worden de relatieve prestatiewinst weergegeven wanneer u een webonderdeel inhoud zoeken gebruikt in plaats van een webonderdeel inhouds query. De effecten zijn duidelijker met een complexe sitestructuur en zeer brede inhoudsquery's.
  
De voorbeeldsite heeft de volgende kenmerken:
  
- acht niveaus van subsites.
    
- Lijsten waarin een aangepast inhoudstype wordt gebruikt voor fruit.
    
- In het webonderdeel is de Inhoudsquery uitgebreid, met als resultaat alle items met het inhoudstype ' fruit '.
    
- Het voorbeeld werkt alleen met 50-items op de acht sites. De effecten zullen nog meer uitspreken voor sites met meer inhoud.
    
Dit is een schermafbeelding van de resultaten van het webonderdeel inhouds query.
  
![Afbeelding met Inhoudsquery voor webonderdeel](../media/b3d41f20-dfe5-46ed-9c0a-31057e82de33.png)
  
In Internet Explorer gebruikt u het tabblad **netwerk** van de F12-hulpprogramma's voor ontwikkelaars om de details te bekijken voor de antwoordheader. In de volgende schermafbeelding is de waarde voor het **SPRequestDuration** voor deze pagina-laad 924 milliseconden. 
  
![Schermafbeelding van het aanvragen van de duur van 924](../media/343571f2-a249-4de2-bc11-2cee93498aea.png)
  
 In **SPRequestDuration** wordt de hoeveelheid werk die op de server is uitgevoerd, aangegeven om de pagina voor te bereiden. Door de inhoud van een query te vervangen door de webonderdelen inhoud door zoekresultaten wordt de tijd voor het weergeven van de pagina aanzienlijk verkleind. Als u daarentegen een pagina met een vergelijkbaar webonderdeel inhoud zoeken oplevert, wordt het resultaat van de **SPRequestDuration** -waarde van 106 milliseconden weergegeven, zoals in deze schermafbeelding: 
  
![Schermafbeelding van het aanvragen van de duur van 106](../media/b46387ac-660d-4e5e-a11c-cc430e912962.png)
  
## <a name="adding-a-content-search-web-part-in-sharepoint-online"></a>Een webonderdeel inhoud zoeken toevoegen in SharePoint Online

Het toevoegen van een webonderdeel inhoud is vergelijkbaar met een standaard webonderdeel inhouds query. Zie de sectie  *' een webonderdeel inhoud zoeken toevoegen '*  in een webonderdeel inhoud [Zoeken configureren in SharePoint](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a).
  
## <a name="creating-the-right-search-query-for-your-content-search-web-part"></a>De juiste zoekquery maken voor het webonderdeel inhoud zoeken

Wanneer u een webonderdeel inhoud zoeken hebt toegevoegd, kunt u de zoekopdracht verfijnen en de gewenste items herstellen. Zie de sectie  *' inhoud weergeven door een geavanceerde query te configureren in een webonderdeel inhoud zoeken '*  in een webonderdeel inhoud [Zoeken configureren in SharePoint](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a)voor gedetailleerde instructies.
  
## <a name="query-building-and-testing-tool"></a>Het hulpmiddel voor het maken en testen van query's

Voor een hulpmiddel voor het maken en testen van complexe query's, raadpleegt u het [hulpmiddel Zoek query](https://sp2013searchtool.codeplex.com/) op codeplex. 
  

