---
title: Afbeeldingen in pagina's van de modern SharePoint Online-site optimaliseren
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
description: Meer informatie over het gebruik van de hulpmiddelen in SharePoint Online voor het optimaliseren van afbeeldingen in pagina's van de modern SharePoint Online-site.
ms.openlocfilehash: 09122dfd0bc832cf9a09cfb05bf0540e323797d9
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689440"
---
# <a name="optimize-images-in-sharepoint-online-modern-site-pages"></a>Afbeeldingen in pagina's van de modern SharePoint Online-site optimaliseren

In dit artikel vindt u informatie over het optimaliseren van afbeeldingen op pagina's van de modern SharePoint Online-site.

Zie afbeeldingen [optimaliseren voor SharePoint Online](image-optimization-for-sharepoint-online.md)voor meer informatie over het optimaliseren van afbeeldingen op klassieke publicerende sites.

>[!NOTE]
>Zie [prestaties in de moderne SharePoint-ervaring](https://docs.microsoft.com/sharepoint/modern-experience-performance)voor meer informatie over prestaties in moderne portals voor SharePoint Online.

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-image-optimization"></a>Het hulpprogramma pagina diagnose voor SharePoint gebruiken voor het analyseren van afbeeldingen optimaliseren

Het hulpprogramma pagina diagnose voor SharePoint is een browser extensie voor de nieuwe Microsoft Edge- https://www.microsoft.com/edge) en Chrome-browsers die zowel SharePoint Online modern portal als de klassieke publicatiesite pagina's analyseren. Het hulpmiddel biedt een rapport voor elke geanalyseerde pagina op basis van een gedefinieerde set prestatiecriteria. Ga voor meer informatie over het hulpprogramma pagina diagnose voor SharePoint naar [het hulpprogramma pagina diagnose voor SharePoint Online](page-diagnostics-for-spo.md).

>[!NOTE]
>Het hulpmiddel voor het automatisch toevoegen van pagina's werkt alleen voor SharePoint Online en kan niet worden gebruikt op een SharePoint-systeempagina.

Wanneer u een moderne SharePoint-site met behulp van het hulpprogramma pagina diagnose voor SharePoint Analyseer, kunt u informatie over grote afbeeldingen bekijken in het deelvenster _diagnostische tests_ .

Mogelijke resultaten zijn onder meer:

- **Aandacht vereist** (rood): de pagina bevat **een of meer** afbeeldingen met een grootte van 300KB
- **Geen actie vereist** (groen): de pagina bevat geen afbeeldingen met een grootte van 300KB

Als het resultaat van de **grote afbeeldingen** wordt weergegeven in de sectie **aandacht vereist** van de resultaten, klikt u op het resultaat om aanvullende details weer te geven.

![Resultaten van het hulpmiddel pagina diagnose](../media/modern-portal-optimization/pagediag-large-images.png)

## <a name="remediate-large-image-issues"></a>Problemen met grote afbeeldingen oplossen

Als een pagina afbeeldingen met afbeeldingen van 300KB bevat, selecteert u het resultaat voor de **grote afbeeldingen** om te zien welke afbeeldingen te groot zijn. Op de moderne SharePoint Online-pagina's worden weergaven van afbeeldingen binnen de grootte van het browservenster en de resolutie van de client monitor automatisch aangegeven en gewijzigd. U moet altijd afbeeldingen voor webgebruik optimaliseren voordat u ze uploadt naar SharePoint Online. Zeer grote afbeeldingen worden automatisch kleiner in grootte en resolutie, wat kan leiden tot onverwachte weergavekenmerken.

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
