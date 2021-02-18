---
title: Aangepaste extensies optimaliseren op moderne SharePoint Online-sitepagina's
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
description: Informatie over het optimaliseren van de prestaties van aangepaste extensies op moderne SharePoint Online-sitepagina's.
ms.openlocfilehash: 92d328c64c89a1a01bbcd50fb7ad04affdf69af8
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287195"
---
# <a name="optimize-custom-extension-performance-in-sharepoint-online-modern-site-pages"></a>Prestaties van aangepaste extensies optimaliseren op moderne SharePoint Online-sitepagina's

In dit artikel wordt beschreven hoe u kunt bepalen hoe aangepaste extensies van invloed zijn op de gebruikerslatentie en hoe u veelvoorkomende problemen kunt oplossen.

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-custom-extensions"></a>Het hulpprogramma Paginadiagnose voor SharePoint gebruiken om aangepaste extensies te analyseren

Het hulpprogramma Paginadiagnose voor SharePoint is een browseruitbreiding voor de nieuwe versie van Microsoft Edge (en Chrome-browsers die zowel moderne Portal- als klassieke publicerende sitepagina's van https://www.microsoft.com/edge) SharePoint Online analyseren. Het hulpmiddel bevat een rapport voor elke geanalyseerde pagina, waarin u kunt zien hoe de pagina zich vertreedt ten opzichte van een gedefinieerde set prestatiecriteria. Ga naar Het hulpprogramma Paginadiagnose voor SharePoint Online gebruiken voor meer informatie over het hulpprogramma [Paginadiagnose voor SharePoint Online.](page-diagnostics-for-spo.md)

>[!NOTE]
>Het hulpprogramma Paginadiagnose werkt alleen voor SharePoint Online en kan niet worden gebruikt op een SharePoint-systeempagina.

Wanneer u een SharePoint-sitepagina analyseert met het hulpprogramma Paginadiagnose voor SharePoint, kunt u in het deelvenster  Diagnostische tests informatie  zien over aangepaste extensies die de basislijnmetingen overschrijden. Dit heeft gevolgen voor de laadtijd en/of het te veel gebruikte extensies in het deelvenster Diagnostische tests  

Mogelijke resultaten zijn:

- **Aandacht vereist** (rood): Elke _aangepaste extensie_ die langer dan **één seconde** duurt om te laden. De totale laadtijd die wordt weergegeven in de testresultaten, wordt onderverdeeld op het laden en init van een module. Als een pagina te veel extensies heeft, kan dit van invloed zijn  op de laadtijd van de pagina. Dit wordt gemarkeerd als er zeven of meer extensies op de pagina worden gebruikt.
- **Verkoopkansen voor** verbetering  (geel) Als er vijf of meer extensies worden gebruikt, worden deze in deze sectie gemarkeerd als een waarschuwing totdat er zeven of meer worden gebruikt. Deze worden vervolgens gemarkeerd als Aandacht vereist.
- **Geen actie vereist** (groen): Het laden duurt langer dan één seconde.

Als een uitbreiding van invloed is op de laadtijd van een pagina  of als de pagina te veel extensies heeft, wordt het resultaat weergegeven in de sectie Aandacht vereist van de resultaten. Klik op het resultaat om meer informatie te zien over welke extensie langzaam wordt geladen of er te veel extensies zijn gemarkeerd. Toekomstige updates van het hulpprogramma Paginadiagnose voor SharePoint kunnen updates van analyseregels bevatten, dus zorg ervoor dat u altijd de meest recente versie van het hulpprogramma hebt.

![Resultaten van laadtijd van pagina](../media/page-diagnostics-for-spo/pagediag-extensions-load-time.png)

De beschikbare informatie in de resultaten omvat:

- **Met naam en** id worden identificerende gegevens weergegeven die u kunnen helpen de extensie op de pagina te vinden
- **Totaal** toont de totale tijd voor het laden en initialiseren van de uitbreiding voor de module. Het is de totale relatieve tijd die door de extensie wordt genomen om op de pagina uit te voeren, van begin tot einde.
- **Bij het laden** van een module ziet u de tijd die nodig is om de javaScript- en CSS-bestanden te downloaden, te evalueren en te laden. Vervolgens wordt het Init-proces begonnen.
- **Init** shows the time taken for the extension to initialize the data.
    Het is een asynchrone oproep en tijdin voeren de berekening van de tijd voor de on-Init-functie uit wanneer de geretourneerde belofte wordt opgelost.

Deze informatie wordt verstrekt om ontwerpers en ontwikkelaars te helpen bij het oplossen van problemen. Deze informatie moet u verstrekken aan uw ontwerp- en ontwikkelteam.

## <a name="overview-of-extensions"></a>Overzicht van extensies

SharePoint Framework-extensies (SPFX) Kunnen worden gebruikt om de SharePoint-gebruikerservaring uit te breiden. Met SharePoint Framework Extensions kunt u meer facets van de SharePoint-ervaring aanpassen, zoals meldingsgebieden, werkbalken en lijstgegevensweergaven.

Extensies kunnen een negatieve invloed hebben op de prestaties van een SharePoint-pagina, omdat ook CPU- en netwerkbronnen vereiste werkzaamheden moeten doen.

Er zijn vier typen extensies:

- **Application Customizers** voegt scripts toe aan de pagina, heeft toegang tot bekende tijdelijke aanduidingen voor HTML-elementen en breidt deze uit met aangepaste weergaven.
- **Met veld customizers** kunt u aangepaste weergaven maken van gegevens voor velden in een lijst.
- **Met opdrachtsets** worden de SharePoint-opdrachtoppervlakken uitgebreid om nieuwe acties toe te voegen en wordt code aan de clientzijde verstrekt die u kunt gebruiken om gedrag te implementeren.
- **Zoekquery modifier (alleen voor voorbeeld)** wordt aangeroepen vlak voordat de zoekquery wordt uitgevoerd.

## <a name="remediate-extension-performance-issues"></a>Problemen met de prestaties van uitbreidingen verhelpen

Volg de richtlijnen in deze sectie om prestatieproblemen te identificeren en op te lossen met extensies die worden vermeld in de Extensies, die van invloed zijn op de laadtijd **van pagina's.**

>[!NOTE]
>Het is mogelijk dat de toepassingsuitbreidingen in het begin van de levensduur van een pagina worden uitgevoerd en dit kan van invloed zijn op de prestaties van andere extensies op de pagina.

De controleresultaten in het diagnostisch hulpprogramma pagina worden weergegeven in twee fasen van het uitvoeren van een uitbreiding om de mogelijke prestatie-impact te identificeren.

- **Het** laden van een module is de tijd die nodig is om de uitbreiding te laden. Dit wordt beïnvloed door de grootte van een uitbreiding, dus het is een goed idee om alleen de benodigde bibliotheken in de extensie te bundelen en lichtere bibliotheken te kiezen.
- **Init** is the initialization time of the extension and extension developers should consider whether the extension is doing unnecessary work or executing too many commands during the initializing stage.

Paginaauteurs kunnen ook het controleresultaat gebruiken om te controleren of een pagina te veel extensies heeft, omdat het aantal extensies een negatieve invloed heeft op de prestaties van een pagina.

- **Extensiegrootte en afhankelijkheden**
  - Het Office 365-CDN is vereist voor het optimaal statisch downloaden van statische bronnen. Openbare CDN-origins hebben de voorkeur voor _js-/css-bestanden._ Zie Het Office 365 Content Delivery Network (CDN) gebruiken met SharePoint Online voor meer informatie over het gebruik van het [Office 365-CDN.](use-microsoft-365-cdn-with-spo.md)
  - Gebruik frameworks zoals _React-_ en _Fabric-importen_ die deel uitmaken van het SharePoint Framework (SPFX). Zie Overzicht van SharePoint Framework voor [meer informatie.](https://docs.microsoft.com/sharepoint/dev/spfx/sharepoint-framework-overview)
  - Zorg ervoor dat u de nieuwste versie van SharePoint Framework gebruikt en upgrade naar nieuwe versies zodra deze beschikbaar zijn.
- **Gegevens ophalen/caching**
  - Als de extensie afhankelijk is van extra servergesprekken om gegevens op te halen voor weergave, zorgt u ervoor dat deze server-API's snel zijn en/of client caching (zoals het gebruik van _localStorage_ of _IndexDB_ voor grotere sets) implementeren.
  - Als er meerdere oproepen nodig zijn om essentiële gegevens weer te geven, kunt u overwegen om een batch te maken op de server of op andere manieren om aanvragen samen tevoegen tot één oproep.
  - Als voor sommige gegevenselementen een tragere API is vereist, maar die niet essentieel zijn voor de eerste weergave, ontkoppelt u deze tot een afzonderlijke oproep die wordt uitgevoerd nadat essentiële gegevens zijn weergegeven.
  - Als meerdere onderdelen dezelfde gegevens gebruiken, gebruik dan een algemene gegevenslaag om dubbele aanroepen te voorkomen.
- **Weergavetijd**
  - Mediabronnen zoals afbeeldingen en video's moeten worden beperkt tot de limieten van de container, het apparaat en/of het netwerk om te voorkomen dat onnodige grote assets worden gedownload. Zie het [Office 365 Content Delivery Network (CDN)](use-microsoft-365-cdn-with-spo.md)gebruiken met SharePoint Online voor meer informatie over inhoudsafhankelijkheden.
  - Voorkom API-aanroepen die leiden tot nieuwe stroom, complexe CSS-regels of ingewikkelde animaties. Zie Het minimaliseren van de [browserreflow voor meer informatie.](https://developers.google.com/speed/docs/insights/browser-reflow)
  - Vermijd het gebruik van geketende, langlopende taken. Verbreed taken daarom in afzonderlijke wachtrijen. Zie [JavaScript-uitvoering optimaliseren voor meer informatie.](https://developers.google.com/web/fundamentals/performance/rendering/optimize-javascript-execution)
  - Reserveer overeenkomstige ruimte voor asynchrone weergave van media of visuele elementen om te voorkomen dat frames worden overgeslagen en rug ruggoot (ook wel _jank genoemd)._
  - Als een bepaalde browser geen ondersteuning biedt voor een functie die wordt gebruikt in weergave, laadt u een polyfillfunctie of sluit u het uitvoeren van afhankelijke code uit. Als de functie niet kritiek is, moet u resources verwijderen, zoals gebeurtenis-handlers, om geheugenlekken te voorkomen.

Voordat u paginarevisies maakt om prestatieproblemen te verhelpen, noteert u de laadtijd van de pagina in de analyseresultaten. Voer het hulpprogramma na de revisie opnieuw uit om te zien of het nieuwe resultaat binnen de basislijnstandaard valt en controleer de nieuwe laadtijd van de pagina om te zien of er een verbetering is.

![Resultaten van laadtijd van pagina](../media/modern-portal-optimization/pagediag-page-load-time.png)

>[!NOTE]
>De laadtijd van pagina's kan variëren afhankelijk van een aantal factoren, zoals de belasting van het netwerk, het tijdstip van de dag en andere tijdelijke voorwaarden. Test het laden van pagina's een paar keer voor en na het aanbrengen van wijzigingen om het gemiddelde van de resultaten te kunnen bekijken.

## <a name="related-topics"></a>Verwante onderwerpen

[Prestaties van SharePoint Online afstemmen](tune-sharepoint-online-performance.md)

[De prestaties van Office 365 afstemmen](tune-microsoft-365-performance.md)

[Prestaties in de moderne SharePoint-ervaring](https://docs.microsoft.com/sharepoint/modern-experience-performance)

[Netwerken voor contentlevering](content-delivery-networks.md)

[Het Office 365 Content Delivery Network (CDN) gebruiken met SharePoint Online](use-microsoft-365-cdn-with-spo.md)
