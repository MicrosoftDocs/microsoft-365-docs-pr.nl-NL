---
title: De prestaties van het webonderdeel in SharePoint Online moderne sitepagina's optimaliseren
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
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.reviewer: sstewart
search.appverid:
- MET150
description: Meer informatie over het gebruik van diagnostische gegevens voor pagina's voor het optimaliseren van de prestaties van webonderdelen in SharePoint Online-sitepagina's.
ms.openlocfilehash: f7b72aa8ed212147c06660585c4e58e548762c35
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519749"
---
# <a name="optimize-web-part-performance-in-sharepoint-online-modern-site-pages"></a>De prestaties van het webonderdeel in SharePoint Online moderne sitepagina's optimaliseren

Pagina's van de moderne SharePoint Online-site bevatten webonderdelen die kunnen bijdragen aan de totale laadtijden van pagina's. In dit artikel leest u hoe u kunt bepalen hoe webonderdelen op uw pagina's van invloed zijn op de beschikbare latentie van de gebruiker en hoe u veelvoorkomende problemen kunt oplossen.

>[!NOTE]
>Zie [prestaties in de moderne SharePoint-ervaring](https://docs.microsoft.com/sharepoint/modern-experience-performance)voor meer informatie over prestaties in moderne portals voor SharePoint Online.

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-web-parts"></a>Het hulpprogramma voor het analyseren van webonderdelen met behulp van het hulpprogramma pagina diagnose voor SharePoint

Het hulpprogramma pagina diagnose voor SharePoint is een browser extensie voor de nieuwe Microsoft Edge- https://www.microsoft.com/edge) en Chrome-browsers die zowel SharePoint Online modern portal als de klassieke publicatiesite pagina's analyseren. Het hulpmiddel biedt een rapport voor elke geanalyseerde pagina op basis van een gedefinieerde set prestatiecriteria. Ga voor meer informatie over het hulpprogramma pagina diagnose voor SharePoint naar [het hulpprogramma pagina diagnose voor SharePoint Online](page-diagnostics-for-spo.md).

>[!NOTE]
>Het hulpmiddel voor het automatisch toevoegen van pagina's werkt alleen voor SharePoint Online en kan niet worden gebruikt op een SharePoint-systeempagina.

Wanneer u een SharePoint-sitepagina wilt analyseren met het hulpprogramma pagina diagnose voor SharePoint, kunt u informatie weergeven over webonderdelen die de metric-Metric _van de_ **webonderdelen beïnvloeden** .

Mogelijke resultaten zijn onder meer:

- **Aandacht vereist** (rood): alle _aangepaste_ webonderdelen die zichtbaar zijn in de viewport (scherm dat deel uitmaakt van de pagina die eerst wordt geladen) en waarvan de belasting langer dan **twee** seconden duurt. _Aangepaste_ webonderdelen van buiten de viewport die langer dan **vier** seconden duren. Totale laadtijd wordt weergegeven in testresultaten en wordt verbroken via module laden, Lazy load, init en rendering.
- **Verbeterings verkoopkansen** (geel): items die van invloed kunnen zijn op de pagina laadtijd worden weergegeven in deze sectie en moeten worden gecontroleerd en gecontroleerd. Dit kan de volgende Microsoft-webonderdelen (OOTB) hebben. Resultaten van Microsoft-webonderdelen die in deze sectie worden weergegeven, worden automatisch aan Microsoft gerapporteerd, zodat u **geen actie hoeft te ondernemen**. U dient alleen een ondersteuningsticket aan te melden voor onderzoek als er zeer traag de prestaties op de pagina worden weergegeven en **alle Microsoft-webonderdelen** op de pagina worden weergegeven in de resultaten van de sectie **verbeterings verkoopkansen** . Houd er rekening mee dat bij een update van de SharePoint-hulpmiddel toekomstige diagnostische gegevens de resultaten verder opleveren op basis van de specifieke configuratie van het Microsoft-webonderdeel.
- **Geen actie vereist** (groen): geen enkel webonderdeel duurt langer dan **twee** seconden voor het retourneren van gegevens.

Als het resultaat van **invloed is op de pagina laadtijd** van een pagina, klikt u in **het gedeelte** **Let** op de resultaten van de zoekresultaten op het resultaat om de details te bekijken van de webonderdelen die langzaam worden geladen. Toekomstige updates voor het hulpprogramma pagina diagnose voor SharePoint bevatten mogelijk updates voor analyseregels, dus zorg ervoor dat u altijd de nieuwste versie van het hulpmiddel hebt.

![Resultaten van het hulpmiddel pagina diagnose](../media/modern-portal-optimization/pagediag-web-part.png)

Gegevens die in de resultaten worden weergegeven zijn onder meer:

- **Gemaakt door geeft aan** of het webonderdeel aangepast of MICROsoft OOTB
- **Naam en id** toont identificatiegegevens die u kunnen helpen bij het vinden van het webonderdeel op de pagina.
- **Totale hoeveelheid** de totale tijd voor het webonderdeel dat wordt geladen
- **Module belasting** toont de tijd die is besteed aan het ophalen en laden van de onderdelen van het webonderdeel
- Met **Lazy laadt** u de tijd voor het uitgesteld laden van webonderdelen die niet zichtbaar zijn in het hoofdgedeelte van de pagina
- **Init** toont de tijd die wordt gebruikt voor de initialisatie van webonderdelen
- **Render** toont de tijd die het webonderdeel heeft gemaakt om resultaten op te halen en weer te geven

Deze informatie wordt verschaft om ontwerpers en ontwikkelaars te helpen problemen op te lossen. U dient deze informatie te verstrekken aan uw ontwerp-en ontwikkelingsteam.

## <a name="remediate-web-part-performance-issues"></a>Prestatieproblemen met het webonderdeel oplossen

Volg de richtlijnen in deze sectie om prestatieproblemen met webonderdelen die worden vermeld in de webonderdelen te identificeren en te herstellen **, zijn van invloed op de laadtijd voor pagina's** .

Er zijn drie categorieën mogelijke oorzaken voor slechtere prestaties van het webonderdeel. Gebruik de onderstaande informatie om te bepalen welke problemen van toepassing zijn op uw scenario en om ze te herstellen.

- Script formaat en afhankelijkheden van webonderdelen
  - Optimaliseer het eerste script waarmee het Mainline-scenario wordt weergegeven voor de _weergavemodus_.
  - Beweeg de minder frequente scenario's en de bewerkingsmodus (zoals het deelvenster Eigenschappen) om segmenten van elkaar te scheiden met behulp van de instructie _importeren ()_ .
  - Controleer de afhankelijkheden van de _package.jsin_ het bestand om de dodecode helemaal te verwijderen. Verplaats de afhankelijkheden testen/samenstellen naar devDependencies.
  - Het gebruik van het Office 365 CDN is vereist voor optimale statische Download bronnen. Openbare CDN-oorsprong zijn de voorkeur voor _js-en CSS-_ bestanden. Zie [het office 365 Content Delivery Network (CDN) gebruiken met SharePoint Online](use-microsoft-365-cdn-with-spo.md)voor meer informatie over het gebruik van Office 365 CDN.
  - U kunt onder andere kaders gebruiken, zoals _reageren_ en de invoer van de _infrastructuur_ , die deel uitmaken van de SharePoint Framework (SPFx). Voor meer informatie raadpleegt u [overzicht van SharePoint Framework](https://docs.microsoft.com/sharepoint/dev/spfx/sharepoint-framework-overview).
  - Zorg ervoor dat u de meest recente versie van het SharePoint-Framework gebruikt en een upgrade uitvoert naar nieuwe versies zodra deze beschikbaar komen.
- Gegevens ophalen/in cache opslaan
  - Als het webonderdeel gebruikmaakt van extra server oproepen om gegevens op te halen voor weergave, moet u ervoor zorgen dat deze server-Api's snel en/of de cache voor clienttoegang gebruiken (zoals het gebruik van _localStorage_ of _IndexedDB_ voor grotere sets).
  - Als er meerdere oproepen vereist zijn om cruciale gegevens weer te geven, kunt u overwegen om batches op de server of andere methoden voor het samenvoegen van aanvragen in één gesprek.
  - Als voor sommige elementen met gegevens een langzamere API is vereist, maar niet essentieel is voor het maken van de rendering, ontkoppelt u deze naar een afzonderlijke oproep die wordt uitgevoerd nadat de kritieke gegevens zijn weergegeven.
  - Als in meerdere delen dezelfde gegevens worden gebruikt, gebruikt u een gemeenschappelijke Gegevenstoegangslaag om dubbele oproepen te voorkomen.
- Tijdstip van rendering
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

[Netwerken voor contentlevering](content-delivery-networks.md)

[Het Office 365 Content Delivery Network (CDN) gebruiken met SharePoint Online](use-microsoft-365-cdn-with-spo.md)
