---
title: IFrames optimaliseren in SharePoint Online-pagina's van de publicerende site
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
ms.custom: Adm_O365
ms.reviewer: sstewart
search.appverid:
- MET150
description: Meer informatie over het optimaliseren van de prestaties van iFrames in SharePoint Online-pagina's van de modern en de klassieke publicatiesite.
ms.openlocfilehash: 8985eb1038bbdfc53dc3c6a8ea9350fa6df33556
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689557"
---
# <a name="optimize-iframes-in-sharepoint-online-modern-and-classic-publishing-site-pages"></a>IFrames optimaliseren in SharePoint Online-pagina's van de publicerende site

iFrames kunnen handig zijn voor het weergeven van inhouds rijke inhoud, zoals Video's of andere media. Aangezien iFrames wel een aparte pagina op de pagina van de SharePoint-site laadt, kan de inhoud die in het iFrame wordt geladen grote afbeeldingen, Video's of andere elementen bevatten die kunnen bijdragen aan de totale laadtijden van pagina's en die u niet kunt beheren op de pagina. In dit artikel vindt u informatie over hoe u kunt bepalen hoe iFrames in uw pagina's van invloed zijn op de beschikbare latentie en hoe u veelvoorkomende problemen kunt oplossen.

>[!NOTE]
>Ga voor meer informatie over de prestaties van moderne SharePoint Online-sites naar [prestaties in de moderne SharePoint-ervaring](https://docs.microsoft.com/sharepoint/modern-experience-performance).

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-web-parts-using-iframes"></a>Het hulpprogramma voor het analyseren van webonderdelen met behulp van het hulpprogramma pagina diagnose voor SharePoint gebruiken

Het hulpprogramma pagina diagnose voor SharePoint is een browser extensie voor de nieuwe Microsoft Edge- https://www.microsoft.com/edge) en Chrome-browsers die zowel SharePoint Online modern portal als de klassieke publicatiesite pagina's analyseren. Het hulpmiddel biedt een rapport voor elke geanalyseerde pagina op basis van een gedefinieerde set prestatiecriteria. Ga voor meer informatie over het hulpprogramma pagina diagnose voor SharePoint naar [het hulpprogramma pagina diagnose voor SharePoint Online](page-diagnostics-for-spo.md).

>[!NOTE]
>Het hulpmiddel voor het automatisch toevoegen van pagina's werkt alleen voor SharePoint Online en kan niet worden gebruikt op een SharePoint-systeempagina.

Wanneer u een SharePoint-sitepagina wilt analyseren met het hulpprogramma pagina diagnose voor SharePoint, kunt u informatie weergeven over webonderdelen met iFrames in het deelvenster _diagnostische tests_ . De metric van basislijn is hetzelfde voor moderne en klassieke pagina's.

Mogelijke resultaten zijn onder meer:

- **Aandacht vereist** (rood): de pagina bevat **drie of meer** webonderdelen met IFRAME-instellingen
- **Verbeterings mogelijkheden** (geel): de pagina bevat **een of twee** webonderdelen met behulp van iframes
- **Geen actie vereist** (groen): de pagina bevat geen webonderdelen die gebruikmaken van iframe-instellingen

Als het resultaat van de **webonderdelen die gebruikmaken van iframe-detectie** worden weergegeven in de sectie **verbeterings mogelijkheden** of **aandacht vereist)** , kunt u op het resultaat klikken om de webonderdelen te zien die iframes bevatten.

![Resultaten van het hulpmiddel pagina diagnose](../media/modern-portal-optimization/pagediag-iframe-yellow.png)

## <a name="remediate-iframe-performance-issues"></a>Prestatieproblemen met iFrame oplossen

Het resultaat van de **webonderdelen met iframes gedetecteerd** in het hulpprogramma voor het controleren van pagina's gebruiken om te bepalen welke webonderdelen iframes bevatten en mogelijk worden gelaadd voor trage pagina's.

iFrames zijn inherent aan een traag feit omdat ze een afzonderlijke externe pagina laden, waaronder alle bijbehorende inhoud, zoals JavaScript, CSS-en Framework-elementen, waardoor de overhead van de sitepagina door een factor van twee of meer kan toenemen.

Volg de onderstaande richtlijnen om te zorgen voor optimaal gebruik van iFrames.

- Gebruik afbeeldingen in plaats van iFrames, indien mogelijk, en als het voorbeeld klein is om te beginnen met of niet-interactief.
- Als iFrames moeten worden gebruikt, minimaliseert u het nummer en/of verplaatst u ze uit de viewport.
- Ingesloten Office-bestanden zoals Word, Excel en PowerPoint zijn interactief, maar zijn langzaam te laden. Afbeeldingen met miniaturen met een koppeling naar het volledige document worden vaak beter.
- Ingesloten YouTube-Video's en Twitter-feeds worden meestal beter in iFrames opgenomen, maar u kunt wel gebruikmaken van deze soorten ingesloten bestanden.
- Geïsoleerde webonderdelen vormen een redelijke uitzondering, maar beperken hun nummer en plaats in de viewport View.
- Als een iFrame zich in de viewport bevindt, kunt u een _IntersectionObserver_ gebruiken om de weergave van de iframe te vertragen totdat deze in beeld komt.

Voordat u de revisies van pagina's aanbrengt om prestatieproblemen te verhelpen, kunt u de laadtijd van de pagina in de analyseresultaten noteren. Voer het hulpprogramma opnieuw uit na de wijziging om te zien of het nieuwe resultaat binnen de basislijn standaard valt en de nieuwe laadtijd voor pagina's te controleren om te zien of er een verbetering was.

![Resultaten van laadtijden voor pagina's](../media/modern-portal-optimization/pagediag-page-load-time.png)

>[!NOTE]
>De laadtijd van de pagina kan variëren, afhankelijk van diverse factoren, zoals netwerkbelasting, tijdstip van de dag en andere tijdelijke voorwaarden. U moet de laadtijd voor pagina's enkele keren vóór en na het aanbrengen van wijzigingen aanbrengen om de resultaten te berekenen.

## <a name="related-topics"></a>Verwante onderwerpen

[Prestaties van SharePoint Online afstemmen](tune-sharepoint-online-performance.md)

[Prestaties van Office 365 afstemmen](tune-microsoft-365-performance.md)

[Prestaties in de moderne SharePoint-ervaring](https://docs.microsoft.com/sharepoint/modern-experience-performance)
