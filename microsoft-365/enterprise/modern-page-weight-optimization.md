---
title: Pagina gewicht optimaliseren in pagina's van de moderne SharePoint Online-site
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 03/11/2020
audience: ITPro
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
description: Meer informatie over het gebruik van het hulpprogramma pagina diagnose voor het optimaliseren van het pagina gewicht in de pagina's van de moderne SharePoint Online-site.
ms.openlocfilehash: 64fb3c90db78a23c7f1c3fcfe604c8ef58703be0
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688999"
---
# <a name="optimize-page-weight-in-sharepoint-online-modern-site-pages"></a>Pagina gewicht optimaliseren in pagina's van de moderne SharePoint Online-site

Sitepagina's van SharePoint Online met een serienummer die is vereist voor het weergeven van pagina-inhoud op de pagina, waaronder afbeeldingen, tekst, objecten in het inhoudsgebied van de navigatie/opdrachtbalken en andere HTML-code die het Framework van de pagina vormt. Pagina gewicht is een afmeting van deze HTML-code en moet beperkt zijn voor optimale laadtijden voor pagina's.

In dit artikel wordt uitgelegd hoe u het pagina gewicht kunt verkleinen op de pagina's van uw moderne site.

>[!NOTE]
>Zie [prestaties in de moderne SharePoint-ervaring](https://docs.microsoft.com/sharepoint/modern-experience-performance)voor meer informatie over prestaties in moderne portals voor SharePoint Online.

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-page-weight"></a>Het hulpprogramma pagina diagnose voor SharePoint gebruiken om het pagina gewicht te analyseren

Het hulpprogramma pagina diagnose voor SharePoint is een browser extensie voor de nieuwe Microsoft Edge- https://www.microsoft.com/edge) en Chrome-browsers die zowel SharePoint Online modern portal als de klassieke publicatiesite pagina's analyseren. Het hulpmiddel biedt een rapport voor elke geanalyseerde pagina op basis van een gedefinieerde set prestatiecriteria. Ga voor meer informatie over het hulpprogramma pagina diagnose voor SharePoint naar [het hulpprogramma pagina diagnose voor SharePoint Online](page-diagnostics-for-spo.md).

>[!NOTE]
>Het hulpmiddel voor het automatisch toevoegen van pagina's werkt alleen voor SharePoint Online en kan niet worden gebruikt op een SharePoint-systeempagina.

Wanneer u een SharePoint-sitepagina wilt analyseren met het hulpprogramma pagina diagnose voor SharePoint, kunt u informatie raadplegen over de pagina in het **pagina gewicht onder 500KB** resultaat van het deelvenster _diagnostische tests_ . Het resultaat wordt in groen weergegeven als het pagina gewicht onder de waarde van de basislijn valt en rood als het pagina gewicht de waarde van de basislijn overschrijdt.

Mogelijke resultaten zijn onder meer:

- **Aandacht vereist** (rood): pagina gewicht OVERSCHRIJDt 500KB
- **Geen actie vereist** (groen): pagina gewicht staat onder 500KB

Als het **pagina gewicht onder 500KB** resultaat wordt weergegeven in de sectie **aandacht vereist** , kunt u op het resultaat klikken voor meer informatie.

![Aanvragen voor resultaten van SharePoint](../media/modern-portal-optimization/pagediag-page-weight.png)

## <a name="remediate-page-weight-issues"></a>Problemen met het pagina gewicht herstellen

Als het pagina gewicht groter is dan 500KB, kunt u de laadtijd van een pagina verbeteren door het aantal webonderdelen te verminderen en de inhoud van de pagina te beperken.

Algemene richtlijnen voor het verkleinen van pagina gewicht omvat:

- Beperk de inhoud van de pagina tot een redelijk bedrag en gebruik meerdere pagina's voor gerelateerde inhoud.
- Minimaliseer het gebruik van webonderdelen met grote eigenschappen zakken.
- Gebruik niet-interactieve samenvouw weergaven indien mogelijk.
- U kunt de grootte van afbeeldingen optimaliseren door afbeeldingen passend te maken met de indelingen voor gecomprimeerde afbeeldingen en ervoor te zorgen dat ze worden gedownload van een CDN.

In het volgende artikel vindt u meer informatie over het beperken van pagina gewicht:

- [De prestaties van pagina's in SharePoint optimaliseren](https://docs.microsoft.com/sharepoint/dev/general-development/optimize-page-performance-in-sharepoint)

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
