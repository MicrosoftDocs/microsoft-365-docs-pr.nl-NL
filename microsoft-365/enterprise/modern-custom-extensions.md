---
title: Aangepaste extensies in SharePoint Online-pagina's met de moderne site optimaliseren
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 03/11/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.reviewer: sstewart
search.appverid:
- MET150
description: Meer informatie over het optimaliseren van de prestaties van aangepaste extensies op pagina's van de moderne SharePoint Online-site.
ms.openlocfilehash: 3f9474bcfa3266742d2e01af2f1df6eb5c0d017c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689342"
---
# <a name="optimize-custom-extension-performance-in-sharepoint-online-modern-site-pages"></a>De prestaties van aangepaste uitbreidingen op sites met moderne SharePoint Online optimaliseren

In dit artikel wordt uitgelegd hoe u kunt bepalen hoe aangepaste extensies van invloed zijn op de beschikbare latentie van de gebruiker en hoe u veelvoorkomende problemen kunt oplossen.

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-custom-extensions"></a>Het hulpprogramma pagina diagnose voor SharePoint gebruiken om aangepaste extensies te analyseren

Het hulpprogramma pagina diagnose voor SharePoint is een browser extensie voor de nieuwe Microsoft Edge- https://www.microsoft.com/edge) en Chrome-browsers die zowel SharePoint Online modern portal als de klassieke publicatiesite pagina's analyseren. Het hulpmiddel biedt een rapport voor elke geanalyseerde pagina op basis van een gedefinieerde set prestatiecriteria. Ga voor meer informatie over het hulpprogramma pagina diagnose voor SharePoint naar [het hulpprogramma pagina diagnose voor SharePoint Online](page-diagnostics-for-spo.md).

>[!NOTE]
>Het hulpmiddel voor het automatisch toevoegen van pagina's werkt alleen voor SharePoint Online en kan niet worden gebruikt op een SharePoint-systeempagina.

Wanneer u een pagina van een SharePoint-site wilt analyseren met het hulpprogramma pagina diagnose voor SharePoint, kunt u informatie weergeven over aangepaste extensies die de metric-Metric van de **uitbreidingen beïnvloeden** en/of het resultaat van **te veel uitbreidingen** in het deelvenster _diagnostische tests_ . 

Mogelijke resultaten zijn onder meer:

- **Aandacht vereist** (rood): elke _aangepaste_ extensie die langer dan **één** seconde duurt om te worden geladen. Totale laadtijd, zoals weergegeven in testresultaten, wordt opgesplitst via module laden en init. Ook als er te veel extensies zijn op een pagina, kunnen ze de laadtijd van de pagina beïnvloeden en worden deze gemarkeerd als er **zeven** of meer extensies worden gebruikt op de pagina.
- **Verbeterings mogelijkheden** (geel) als er **vijf** of meer uitbreidingen worden gebruikt, worden deze gemarkeerd in deze sectie als een waarschuwing totdat zeven of meer worden gebruikt die vervolgens worden gemarkeerd als aandacht vereist.
- **Geen actie vereist** (groen): geen enkele uitbreiding duurt langer dan één seconde voor de belasting.

Als een extensie van invloed is op de laadtijd van pagina's of er te veel extsnions op de pagina staan, wordt het resultaat weergegeven in de sectie **aandacht vereist** van de resultaten. Klik op het resultaat om de details te bekijken van de module die langzaam wordt geladen of te veel extensies is gemarkeerd. Toekomstige updates voor het hulpprogramma pagina diagnose voor SharePoint bevatten mogelijk updates voor analyseregels, dus zorg ervoor dat u altijd de nieuwste versie van het hulpmiddel hebt.

![Resultaten van laadtijden voor pagina's](../media/page-diagnostics-for-spo/pagediag-extensions-load-time.png)

Gegevens die in de resultaten worden weergegeven zijn onder meer:

- **Naam en id** toont identificatiegegevens waarmee u de uitbreiding op de pagina kunt vinden
- **Totale hoeveelheid** de totale tijd voor het initialiseren en laden van de uitbreiding
- **Module belasting** toont de tijd die is besteed aan het ophalen en laden van de uitbreiding
- **Init** toont de tijd die wordt besteed aan de extensie voor initialisatie

Deze informatie wordt verschaft om ontwerpers en ontwikkelaars te helpen problemen op te lossen. U dient deze informatie te verstrekken aan uw ontwerp-en ontwikkelingsteam.

## <a name="overview-of-extensions"></a>Overzicht van extensies

U kunt SharePoint Framework (SPFx)-extensies gebruiken om de SharePoint-gebruikerservaring uit te breiden. Met SharePoint Framework-uitbreidingen kunt u meer facetten van de SharePoint-ervaring aanpassen, met inbegrip van de gebieden, werkbalken en lijstgegevens weergaven.

Uitbreidingen kunnen een onjuiste invloed hebben op de prestaties van een SharePoint-pagina, aangezien dit de processor-en netwerkbronnen voor het uitvoeren van vereiste werk mogelijk maakt.

Er zijn vier typen extensies:

- Met **toepassingen** kunnen scripts worden toegevoegd aan de pagina, en worden tijdelijke aanduidingen voor HTML-elementen met een aangepaste weergave uitgebreid.
- **Veld** weergaven biedt gewijzigde weergaven voor gegevens voor velden in een lijst.
- Met de **opdracht sets** breidt u de opdracht vlakken van SharePoint uit om nieuwe acties toe te voegen, en de code aan de clientzijde die u kunt gebruiken om gedrag te implementeren.
- **Wijziging van de zoekopdracht (alleen voorbeeld)** wordt aangeroepen net voordat de zoek query wordt uitgevoerd.

## <a name="remediate-extension-performance-issues"></a>Problemen met de snelheid van de toestel herstel

Volg de richtlijnen in deze sectie voor het identificeren en herstellen van prestatieproblemen met extensies die worden weergegeven in de **uitbreidingen voor het laden van pagina's van invloed zijn** op het laden van pagina's.

>[!NOTE]
>Toepassingen in het stadium voor het in de loop van de levenscyclus van een pagina kunnen worden aangepast, wat van invloed kan zijn op de prestaties van andere extensies op de pagina.

Met de controleresultaten in het hulpmiddel voor het beheer van pagina's worden twee fasen voor het uitvoeren van een uitbreiding weergegeven om de mogelijke prestatie gevolgen te identificeren.

- **Laden van modules** is hoe lang het duurt voordat de extensie wordt geladen, wat van invloed is op de grootte van een uitbreiding, zodat het een goed idee is om alleen de gewenste bibliotheken in de extensie te bundelen en ook om lichtere bibliotheken te kiezen.
- **Init** is de initialisatie tijd van de ontwikkelaars voor extensies en extensies om na te gaan of de extensie niet langer werk moet werken of te veel opdrachten uitvoert tijdens de Initialisatiefase.

Auteurs van pagina's kunnen ook het controleresultaat gebruiken om te zien of een pagina te veel extensies bevat voor te veel extensies, wat de prestaties van een pagina negatief beïnvloeden.

- **Grootte en afhankelijkheden van de extensie**
  - Het gebruik van het Office 365 CDN is vereist voor optimale statische Download bronnen. Openbare CDN-oorsprong zijn de voorkeur voor _js-en CSS-_ bestanden. Zie [het office 365 Content Delivery Network (CDN) gebruiken met SharePoint Online](use-microsoft-365-cdn-with-spo.md)voor meer informatie over het gebruik van Office 365 CDN.
  - U kunt onder andere kaders gebruiken, zoals _reageren_ en de invoer van de _infrastructuur_ , die deel uitmaken van de SharePoint Framework (SPFx). Voor meer informatie raadpleegt u [overzicht van SharePoint Framework](https://docs.microsoft.com/sharepoint/dev/spfx/sharepoint-framework-overview).
  - Zorg ervoor dat u de meest recente versie van het SharePoint-Framework gebruikt en een upgrade uitvoert naar nieuwe versies zodra deze beschikbaar komen.
- **Gegevens ophalen/in cache opslaan**
  - Als de uitbreiding gebruikmaakt van extra server oproepen voor het ophalen van gegevens voor weergave, moet u ervoor zorgen dat deze server-Api's snel en/of de cache van de client gebruiken (zoals het gebruik van _localStorage_ of _IndexDB_ voor grotere sets).
  - Als er meerdere oproepen vereist zijn om cruciale gegevens weer te geven, kunt u overwegen om batches op de server of andere methoden voor het samenvoegen van aanvragen in één gesprek.
  - Als voor sommige elementen met gegevens een langzamere API is vereist, maar niet essentieel is voor het maken van de rendering, ontkoppelt u deze naar een afzonderlijke oproep die wordt uitgevoerd nadat de kritieke gegevens zijn weergegeven.
  - Als in meerdere delen dezelfde gegevens worden gebruikt, gebruikt u een gemeenschappelijke Gegevenstoegangslaag om dubbele oproepen te voorkomen.
- **Tijdstip van rendering**
  - De grootte van de container, het apparaat en/of netwerk dient te worden aangepast om te voorkomen dat u onnodige grote activa kunt downloaden. Zie [het Office 365 Content Delivery Network (CDN) gebruiken met SharePoint Online](use-microsoft-365-cdn-with-spo.md)voor meer informatie over inhouds afhankelijkheden.
  - Vermijd API-oproepen die een nieuwe, complexe CSS-regels of complexe animaties veroorzaken. Zie voor meer informatie [browser heruitvoering minimaliseren](https://developers.google.com/speed/docs/insights/browser-reflow).
  - Vermijd het gebruik van gekoppelde langdurige taken. In plaats daarvan kunt u langere taken met een onderbrekingspunt verdelen. Zie [JavaScript Execution optimaliseren](https://developers.google.com/web/fundamentals/performance/rendering/optimize-javascript-execution)voor meer informatie.
  - Plaats een juiste ruimte voor asynchrone rendering van media of visuele elementen om overgeslagen frames en hapert (ook wel _JanK_) te voorkomen.
  - Als een bepaalde browser geen ondersteuning biedt voor een functie die wordt gebruikt in de rendering, laadt u een polyfill of niet-uitgevoerde afhankelijke code. Als de functie niet essentieel is, kunt u resources verwijderen, zoals gebeurtenis-handlers om geheugenlekkages te vermijden.

Voordat u de revisies van pagina's aanbrengt om prestatieproblemen te verhelpen, kunt u de laadtijd van de pagina in de analyseresultaten noteren. Voer het hulpprogramma opnieuw uit na de wijziging om te zien of het nieuwe resultaat binnen de basislijn standaard valt en de nieuwe laadtijd voor pagina's te controleren om te zien of er een verbetering was.

![Resultaten van laadtijden voor pagina's](../media/modern-portal-optimization/pagediag-page-load-time.png)

>[!NOTE]
>De laadtijd van de pagina kan variëren, afhankelijk van diverse factoren, zoals netwerkbelasting, tijdstip van de dag en andere tijdelijke voorwaarden. U moet de laadtijd voor pagina's enkele keren vóór en na het aanbrengen van wijzigingen aanbrengen om de resultaten te berekenen.

## <a name="related-topics"></a>Verwante onderwerpen

[Prestaties van SharePoint Online afstemmen](tune-sharepoint-online-performance.md)

[Prestaties van Office 365 afstemmen](tune-microsoft-365-performance.md)

[Prestaties in de moderne SharePoint-ervaring](https://docs.microsoft.com/sharepoint/modern-experience-performance)

[Netwerken voor content levering](content-delivery-networks.md)

[Het Office 365 Content Delivery Network (CDN) gebruiken met SharePoint Online](use-microsoft-365-cdn-with-spo.md)
