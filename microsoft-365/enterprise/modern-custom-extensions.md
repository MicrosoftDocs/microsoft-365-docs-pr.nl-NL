---
title: Aangepaste extensies optimaliseren in SharePoint moderne onlinesitepagina's
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
description: Meer informatie over het optimaliseren van de prestaties van aangepaste extensies in SharePoint moderne onlinesitepagina's.
ms.openlocfilehash: 05d9b9cd9ad70630169595dc42080c718b39dbc8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923053"
---
# <a name="optimize-custom-extension-performance-in-sharepoint-online-modern-site-pages"></a>Aangepaste uitbreidingsprestaties optimaliseren in SharePoint moderne onlinesitepagina's

In dit artikel wordt beschreven hoe u kunt bepalen hoe aangepaste extensies van invloed zijn op de waargenomen latentie van de gebruiker en hoe u veelvoorkomende problemen kunt oplossen.

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-custom-extensions"></a>Het hulpprogramma Paginadiagnose voor SharePoint gebruiken om aangepaste extensies te analyseren

Het hulpprogramma Paginadiagnose voor SharePoint is een browserextensie voor de nieuwe Microsoft Edge ( en Chrome-browsers die zowel SharePoint Moderne portal online als klassieke https://www.microsoft.com/edge) publicerende sitepagina's analyseren. Het hulpprogramma bevat een rapport voor elke geanalyseerde pagina die laat zien hoe de pagina presteert op basis van een gedefinieerde set prestatiecriteria. Als u het hulpprogramma Paginadiagnose voor SharePoint wilt installeren en meer wilt weten, gaat u naar Het hulpprogramma [Paginadiagnose gebruiken](page-diagnostics-for-spo.md)voor SharePoint Online.

>[!NOTE]
>Het hulpprogramma Paginadiagnose werkt alleen SharePoint Online en kan niet worden gebruikt op een SharePoint systeempagina.

Wanneer u een SharePoint-sitepagina analyseert met het hulpprogramma Paginadiagnose voor SharePoint, kunt u  informatie zien over aangepaste extensies  die de basislijnmetriek in de extensies overschrijden, van invloed zijn op de laadtijd en/of het resultaat van te veel gebruikte extensies in het deelvenster Diagnostische tests  

Mogelijke resultaten zijn:

- **Aandacht vereist** (rood): Een _aangepaste_ extensie die langer dan **één** seconde duurt om te laden. De totale laadtijd, zoals weergegeven in testresultaten, wordt uitgesplitsd naar modulebelasting en init. Als er te veel extensies op een pagina staan, kan dit van  invloed zijn op de laadtijd van de pagina en wordt dit gemarkeerd als er zeven of meer extensies op de pagina worden gebruikt.
- **Verkoopkansen voor** verbetering  (geel) Als er vijf of meer extensies worden gebruikt, worden ze in deze sectie gemarkeerd als een waarschuwing totdat er zeven of meer worden gebruikt, waarna deze worden gemarkeerd als Aandacht vereist.
- **Geen actie vereist** (groen): Het laden van de extensie duurt langer dan één seconde.

Als een extensie van invloed is op de laadtijd van de pagina of als er te veel extensies op de pagina staan, wordt het resultaat weergegeven in de sectie Aandacht **vereist** van de resultaten. Klik op het resultaat om te zien welke extensie langzaam wordt geladen of te veel extensies is gemarkeerd. Toekomstige updates voor het hulpprogramma Paginadiagnose voor SharePoint kunnen updates van analyseregels bevatten, dus zorg ervoor dat u altijd de nieuwste versie van het hulpprogramma hebt.

![De laadtijd van pagina's](../media/page-diagnostics-for-spo/pagediag-extensions-load-time.png)

De beschikbare informatie in de resultaten omvat:

- **Naam en id** toont identificerende gegevens die u kunnen helpen de extensie op de pagina te vinden
- **Totaal** geeft de totale tijd weer voor de uitbreiding voor het laden en initialiseren van de module. Het is de totale relatieve tijd die door de extensie wordt gebruikt om op de pagina uit te voeren, van begin tot einde.
- **Module laden** toont de tijd die nodig is voor het downloaden, evalueren en laden van de extensies JavaScript- en CSS-bestanden. Vervolgens wordt het Init-proces begonnen.
- **Init toont** de tijd die nodig is voor de extensie om de gegevens te initialiseren.
    Het is een asynchrone oproep en init time is de berekening van de tijd voor de functie onInit wanneer de geretourneerde belofte is opgelost.

Deze informatie wordt verstrekt om ontwerpers en ontwikkelaars te helpen bij het oplossen van problemen. Deze informatie moet worden verstrekt aan uw ontwerp- en ontwikkelingsteam.

## <a name="overview-of-extensions"></a>Overzicht van extensies

SharePoint Framework (SPFx) Extensies kunnen worden gebruikt om de gebruikerservaring SharePoint uitbreiden. Met SharePoint Framework Extensies kunt u meer facetten van de SharePoint aanpassen, waaronder meldingsgebieden, werkbalken en lijstgegevensweergaven.

Extensies kunnen een slechte invloed hebben op de prestaties van een pagina SharePoint omdat er ook CPU- en netwerkbronnen nodig zijn om het vereiste werk te doen.

Er zijn vier typen extensies:

- **Application Customizers** voegt scripts toe aan de pagina en gebruikt bekende tijdelijke aanduidingen voor HTML-elementen en breidt deze uit met aangepaste weergaven.
- **Veld aanpassen biedt** gewijzigde weergaven voor gegevens voor velden in een lijst.
- **Opdrachtsets** breiden de SharePoint om nieuwe acties toe te voegen en bieden code aan de clientzijde die u kunt gebruiken om gedragingen te implementeren.
- **Zoekquery-modifier (alleen voorbeeld)** wordt aangeroepen vlak voordat de zoekquery wordt uitgevoerd.

## <a name="remediate-extension-performance-issues"></a>Problemen met de uitbreidingsprestaties oplossen

Volg de richtlijnen in deze sectie om prestatieproblemen met extensies in de extensies te identificeren en te **verhelpen,** die van invloed zijn op de laadtijd van pagina's.

>[!NOTE]
>Toepassingsaanpasters kunnen in de beginfase van de levenscyclus van een pagina worden uitgevoerd en kunnen van invloed zijn op de prestaties van andere extensies op de pagina.

De controleresultaten in het hulpprogramma Voor paginadiagnose worden twee stadia van het uitvoeren van een extensie weergegeven om de mogelijke gevolgen voor de prestaties te identificeren.

- **Modulebelasting** is hoe lang het duurt om de extensie te laden, wat wordt beïnvloed door de grootte van een extensie, zodat het een goed idee is om alleen de benodigde bibliotheken in de extensie te bundelen en lichtere bibliotheken te kiezen.
- **Init** is de initialisatietijd van de extensie en extensieontwikkelaars moeten overwegen of de extensie overbodig werk doet of te veel opdrachten tijdens de initialisatiefase uitwerkt.

Paginaauteurs kunnen het controleresultaat ook gebruiken om te zien of een pagina te veel extensies bevat, omdat te veel extensies een negatieve invloed hebben op de prestaties van een pagina.

- **Uitbreidingsgrootte en afhankelijkheden**
  - Gebruik van de Office 365 CDN is vereist voor een optimale statische resource downloaden. Openbare CDN origins hebben de voorkeur voor _js/css-bestanden._ Zie De Office 365 CDN Office 365 Content Delivery Network [(CDN)](use-microsoft-365-cdn-with-spo.md)gebruiken met SharePoint Online voor meer informatie over het gebruik van de SharePoint.
  - Gebruik frameworks zoals _React_ _en import van_ stof die deel uitmaken van de SharePoint Framework (SPFx). Zie Overzicht van de [SharePoint Framework.](/sharepoint/dev/spfx/sharepoint-framework-overview)
  - Zorg ervoor dat u de nieuwste versie van de SharePoint Framework en upgrade naar nieuwe versies zodra deze beschikbaar zijn.
- **Gegevens ophalen/caching**
  - Als de extensie afhankelijk is van extra serveroproepen om gegevens op te halen voor weergave, controleert u of deze server-API's snel zijn en/of client caching implementeren (zoals _localStorage_ of _IndexDB_ voor grotere sets).
  - Als meerdere oproepen nodig zijn om kritieke gegevens weer te geven, kunt u overwegen batching op de server of andere methoden voor het samenvoegen van aanvragen tot één gesprek.
  - Als sommige gegevenselementen een tragere API vereisen, maar niet essentieel zijn voor de eerste weergave, kunt u deze ook loskoppelen van een afzonderlijk gesprek dat wordt uitgevoerd nadat kritieke gegevens zijn weergegeven.
  - Als meerdere onderdelen dezelfde gegevens gebruiken, gebruikt u een veelgebruikte gegevenslaag om dubbele oproepen te voorkomen.
- **Weergavetijd**
  - Mediabronnen zoals afbeeldingen en video's moeten worden uitgebreid tot de limieten van de container, het apparaat en/of het netwerk om te voorkomen dat onnodige grote assets worden gedownload. Zie De Office 365 Content Delivery Network (CDN) gebruiken met [SharePoint Online voor meer informatie over inhoudsafhankelijkheden.](use-microsoft-365-cdn-with-spo.md)
  - Vermijd API-oproepen die leiden tot herstroom, complexe CSS-regels of ingewikkelde animaties. Zie Browserreflow minimaliseren voor [meer informatie.](https://developers.google.com/speed/docs/insights/browser-reflow)
  - Vermijd het gebruik van geketende, langlopende taken. In plaats daarvan kunt u langlopende taken uit elkaar halen in afzonderlijke wachtrijen. Zie [JavaScript-uitvoering optimaliseren voor meer informatie.](https://developers.google.com/web/fundamentals/performance/rendering/optimize-javascript-execution)
  - Reserveer de bijbehorende ruimte voor asynchrone weergave van media of visuele elementen om overgeslagen frames en stotteren (ook wel jank genoemd) _te voorkomen._
  - Als een bepaalde browser geen ondersteuning biedt voor een functie die wordt gebruikt bij het weergeven, laadt u een polyfill of sluit u het uitvoeren van afhankelijke code uit. Als de functie niet kritiek is, moet u resources, zoals gebeurtenis-handlers, verwijderen om geheugenlekken te voorkomen.

Voordat u paginaherzieningen maakt om prestatieproblemen op te lossen, noteert u de laadtijd van de pagina in de analyseresultaten. Voer het hulpprogramma na de revisie opnieuw uit om te zien of het nieuwe resultaat binnen de basislijnstandaard valt en controleer de laadtijd van de nieuwe pagina om te zien of er een verbetering is.

![De laadtijd van pagina's](../media/modern-portal-optimization/pagediag-page-load-time.png)

>[!NOTE]
>De laadtijd van pagina's kan variëren op basis van verschillende factoren, zoals de netwerkbelasting, de tijd van de dag en andere tijdelijke omstandigheden. U moet de laadtijd van pagina's een paar keer voor en na het aanbrengen van wijzigingen testen, zodat u de resultaten kunt gemiddelden.

## <a name="related-topics"></a>Verwante onderwerpen

[Prestaties SharePoint online afstemmen](tune-sharepoint-online-performance.md)

[Prestaties Office 365 afstemmen](tune-microsoft-365-performance.md)

[Prestaties in de moderne SharePoint ervaring](/sharepoint/modern-experience-performance)

[Netwerken voor contentlevering](content-delivery-networks.md)

[De Office 365 Content Delivery Network (CDN) gebruiken met SharePoint Online](use-microsoft-365-cdn-with-spo.md)