---
title: Webonderdeel Inhoud zoeken gebruiken in plaats van webonderdeel Inhoudsquery om de prestaties in SharePoint Online
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
description: Lees hoe u de prestaties kunt verbeteren door het webonderdeel Inhoudsquery te vervangen door het webonderdeel Inhoud zoeken in SharePoint Server 2013 en SharePoint Online.
ms.openlocfilehash: e5f57e59a421d79302f447e229091fdfc96f1237
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689549"
---
# <a name="using-content-search-web-part-instead-of-content-query-web-part-to-improve-performance-in-sharepoint-online"></a>Webonderdeel Inhoud zoeken gebruiken in plaats van webonderdeel Inhoudsquery om de prestaties in SharePoint Online

In dit artikel wordt beschreven hoe u de prestaties kunt verbeteren door het webonderdeel Inhoudsquery te vervangen door het webonderdeel Inhoud zoeken in SharePoint Server 2013 en SharePoint Online.
  
Een van de krachtigste nieuwe functies van SharePoint Server 2013 en SharePoint Online is het webonderdeel Inhoud zoeken (WEBWP). In dit webonderdeel wordt de zoekindex gebruikt om snel resultaten op te halen die aan de gebruiker worden weergegeven. Gebruik het webonderdeel Inhoud zoeken in plaats van het webonderdeel Inhoudsquery (CQWP) op uw pagina's om de prestaties voor uw gebruikers te verbeteren.
  
Als u een webonderdeel Inhoud zoeken gebruikt via een webonderdeel Inhoudsquery, resulteert dit bijna altijd in aanzienlijk betere laadprestaties voor pagina's op SharePoint Online. Er is een beetje extra configuratie om de juiste query te krijgen, maar de voordelen zijn verbeterde prestaties en gelukkiger gebruikers.
  
## <a name="comparing-the-performance-gain-you-get-from-using-content-search-web-part-instead-of-content-query-web-part"></a>De prestaties van het webonderdeel Inhoud zoeken vergelijken in plaats van webonderdeel Inhoudsquery

In de volgende voorbeelden ziet u de relatieve prestatieverbeteringen die u kunt ontvangen wanneer u een webonderdeel Inhoud zoeken gebruikt in plaats van een webonderdeel Inhoudsquery. De effecten zijn duidelijker met een complexe sitestructuur en zeer brede inhoudsquery's.
  
Deze voorbeeldsite heeft de volgende kenmerken:
  
- 8 niveaus met subsites.
    
- Lijsten met een aangepast inhoudstype 'fruit'.
    
- In het webonderdeel is de inhoudsquery breed en worden alle items met het inhoudstype 'fruit' als resultaat gebruikt.
    
- In het voorbeeld worden slechts 50 items op de 8 sites gebruikt. De effecten zijn nog duidelijker voor sites met meer inhoud.
    
Hier ziet u een schermafbeelding van de resultaten van het webonderdeel Inhoudsquery.
  
![Afbeelding met inhoudsquery voor webonderdeel](../media/b3d41f20-dfe5-46ed-9c0a-31057e82de33.png)
  
Gebruik in Internet Explorer het **tabblad Netwerk** van de hulpprogramma's voor F12-ontwikkelaars om de details van de antwoordkop te bekijken. In de volgende schermafbeelding is de waarde voor **de SPRequestDuration** voor deze paginabelasting 924 milliseconden. 
  
![Schermafbeelding met de duur van de aanvraag van 924](../media/343571f2-a249-4de2-bc11-2cee93498aea.png)
  
 **SPRequestDuration** geeft de hoeveelheid werk aan die op de server wordt uitgevoerd om de pagina voor te bereiden. Als u van inhoud op query wisselt Webonderdelen inhoud op zoekfunctie, Webonderdelen de tijd die nodig is om de pagina weer te geven aanzienlijk. Een pagina met een vergelijkbaar webonderdeel Inhoud zoeken, die hetzelfde aantal resultaten retourneert, heeft daarentegen een **SPRequestDuration-waarde** van 106 milliseconden, zoals wordt weergegeven in deze schermafbeelding: 
  
![Schermafbeelding met aanvraagduur van 106](../media/b46387ac-660d-4e5e-a11c-cc430e912962.png)
  
## <a name="adding-a-content-search-web-part-in-sharepoint-online"></a>Een webonderdeel Inhoud zoeken toevoegen in SharePoint Online

Het toevoegen van een webonderdeel Inhoud zoeken lijkt sterk op een gewoon webonderdeel Inhoudsquery. Zie de sectie *'Een webonderdeel* Inhoud zoeken toevoegen' in Een webonderdeel Inhoud zoeken [configureren in SharePoint.](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a)
  
## <a name="creating-the-right-search-query-for-your-content-search-web-part"></a>De juiste zoekquery maken voor het webonderdeel Inhoud zoeken

Nadat u een webonderdeel Inhoud zoeken hebt toegevoegd, kunt u de zoekopdracht verfijnen en de gezochte items retourneren. Zie de sectie 'Inhoud weergeven door een geavanceerde *query in* een webonderdeel Inhoud zoeken te configureren' in Een webonderdeel Inhoud zoeken configureren [in](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a)SharePoint.
  
## <a name="query-building-and-testing-tool"></a>Hulpprogramma voor het maken en testen van query's

Zie het hulpprogramma Zoekquery op Codeplex voor een hulpprogramma voor het maken en testen van complexe query's. [](https://sp2013searchtool.codeplex.com/) 
  

