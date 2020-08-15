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
# <a name="optimize-page-weight-in-sharepoint-online-modern-site-pages"></a><span data-ttu-id="9dd51-103">Pagina gewicht optimaliseren in pagina's van de moderne SharePoint Online-site</span><span class="sxs-lookup"><span data-stu-id="9dd51-103">Optimize page weight in SharePoint Online modern site pages</span></span>

<span data-ttu-id="9dd51-104">Sitepagina's van SharePoint Online met een serienummer die is vereist voor het weergeven van pagina-inhoud op de pagina, waaronder afbeeldingen, tekst, objecten in het inhoudsgebied van de navigatie/opdrachtbalken en andere HTML-code die het Framework van de pagina vormt.</span><span class="sxs-lookup"><span data-stu-id="9dd51-104">SharePoint Online modern site pages contain serialized code that is required to render page content of the page, including images, text, objects in the content area underneath navigation/command bars and other HTML code that forms the framework of the page.</span></span> <span data-ttu-id="9dd51-105">Pagina gewicht is een afmeting van deze HTML-code en moet beperkt zijn voor optimale laadtijden voor pagina's.</span><span class="sxs-lookup"><span data-stu-id="9dd51-105">Page weight is a measurement of this HTML code, and should be limited to ensure optimal page load times.</span></span>

<span data-ttu-id="9dd51-106">In dit artikel wordt uitgelegd hoe u het pagina gewicht kunt verkleinen op de pagina's van uw moderne site.</span><span class="sxs-lookup"><span data-stu-id="9dd51-106">This article will help you understand how to reduce page weight in your modern site pages.</span></span>

>[!NOTE]
><span data-ttu-id="9dd51-107">Zie [prestaties in de moderne SharePoint-ervaring](https://docs.microsoft.com/sharepoint/modern-experience-performance)voor meer informatie over prestaties in moderne portals voor SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="9dd51-107">For more information about performance in SharePoint Online modern portals, see [Performance in the modern SharePoint experience](https://docs.microsoft.com/sharepoint/modern-experience-performance).</span></span>

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-page-weight"></a><span data-ttu-id="9dd51-108">Het hulpprogramma pagina diagnose voor SharePoint gebruiken om het pagina gewicht te analyseren</span><span class="sxs-lookup"><span data-stu-id="9dd51-108">Use the Page Diagnostics for SharePoint tool to analyze page weight</span></span>

<span data-ttu-id="9dd51-109">Het hulpprogramma pagina diagnose voor SharePoint is een browser extensie voor de nieuwe Microsoft Edge- https://www.microsoft.com/edge) en Chrome-browsers die zowel SharePoint Online modern portal als de klassieke publicatiesite pagina's analyseren.</span><span class="sxs-lookup"><span data-stu-id="9dd51-109">The Page Diagnostics for SharePoint tool is a browser extension for the new Microsoft Edge (https://www.microsoft.com/edge) and Chrome browsers that analyzes both SharePoint Online modern portal and classic publishing site pages.</span></span> <span data-ttu-id="9dd51-110">Het hulpmiddel biedt een rapport voor elke geanalyseerde pagina op basis van een gedefinieerde set prestatiecriteria.</span><span class="sxs-lookup"><span data-stu-id="9dd51-110">The tool provides a report for each analyzed page showing how the page performs against a defined set of performance criteria.</span></span> <span data-ttu-id="9dd51-111">Ga voor meer informatie over het hulpprogramma pagina diagnose voor SharePoint naar [het hulpprogramma pagina diagnose voor SharePoint Online](page-diagnostics-for-spo.md).</span><span class="sxs-lookup"><span data-stu-id="9dd51-111">To install and learn about the Page Diagnostics for SharePoint tool, visit [Use the Page Diagnostics tool for SharePoint Online](page-diagnostics-for-spo.md).</span></span>

>[!NOTE]
><span data-ttu-id="9dd51-112">Het hulpmiddel voor het automatisch toevoegen van pagina's werkt alleen voor SharePoint Online en kan niet worden gebruikt op een SharePoint-systeempagina.</span><span class="sxs-lookup"><span data-stu-id="9dd51-112">The Page Diagnostics tool only works for SharePoint Online, and cannot be used on a SharePoint system page.</span></span>

<span data-ttu-id="9dd51-113">Wanneer u een SharePoint-sitepagina wilt analyseren met het hulpprogramma pagina diagnose voor SharePoint, kunt u informatie raadplegen over de pagina in het **pagina gewicht onder 500KB** resultaat van het deelvenster _diagnostische tests_ .</span><span class="sxs-lookup"><span data-stu-id="9dd51-113">When you analyze a SharePoint site page with the Page Diagnostics for SharePoint tool, you can see information about page in the **Page weight under 500KB** result of the _Diagnostic tests_ pane.</span></span> <span data-ttu-id="9dd51-114">Het resultaat wordt in groen weergegeven als het pagina gewicht onder de waarde van de basislijn valt en rood als het pagina gewicht de waarde van de basislijn overschrijdt.</span><span class="sxs-lookup"><span data-stu-id="9dd51-114">The result will appear in green if the page weight is under the baseline value, and red if the page weight exceeds the baseline value.</span></span>

<span data-ttu-id="9dd51-115">Mogelijke resultaten zijn onder meer:</span><span class="sxs-lookup"><span data-stu-id="9dd51-115">Possible results include:</span></span>

- <span data-ttu-id="9dd51-116">**Aandacht vereist** (rood): pagina gewicht OVERSCHRIJDt 500KB</span><span class="sxs-lookup"><span data-stu-id="9dd51-116">**Attention required** (red): Page weight exceeds 500KB</span></span>
- <span data-ttu-id="9dd51-117">**Geen actie vereist** (groen): pagina gewicht staat onder 500KB</span><span class="sxs-lookup"><span data-stu-id="9dd51-117">**No action required** (green): Page weight is under 500KB</span></span>

<span data-ttu-id="9dd51-118">Als het **pagina gewicht onder 500KB** resultaat wordt weergegeven in de sectie **aandacht vereist** , kunt u op het resultaat klikken voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="9dd51-118">If the **Page weight under 500KB** result appears in the **Attention required** section, you can click the result for details.</span></span>

![Aanvragen voor resultaten van SharePoint](../media/modern-portal-optimization/pagediag-page-weight.png)

## <a name="remediate-page-weight-issues"></a><span data-ttu-id="9dd51-120">Problemen met het pagina gewicht herstellen</span><span class="sxs-lookup"><span data-stu-id="9dd51-120">Remediate page weight issues</span></span>

<span data-ttu-id="9dd51-121">Als het pagina gewicht groter is dan 500KB, kunt u de laadtijd van een pagina verbeteren door het aantal webonderdelen te verminderen en de inhoud van de pagina te beperken.</span><span class="sxs-lookup"><span data-stu-id="9dd51-121">If page weight exceeds 500KB, you can improve overall page load time by reducing the number of web parts and limiting page content to an appropriate degree.</span></span>

<span data-ttu-id="9dd51-122">Algemene richtlijnen voor het verkleinen van pagina gewicht omvat:</span><span class="sxs-lookup"><span data-stu-id="9dd51-122">General guidance for reducing page weight includes:</span></span>

- <span data-ttu-id="9dd51-123">Beperk de inhoud van de pagina tot een redelijk bedrag en gebruik meerdere pagina's voor gerelateerde inhoud.</span><span class="sxs-lookup"><span data-stu-id="9dd51-123">Limit the page content to a reasonable amount and use multiple pages for related content.</span></span>
- <span data-ttu-id="9dd51-124">Minimaliseer het gebruik van webonderdelen met grote eigenschappen zakken.</span><span class="sxs-lookup"><span data-stu-id="9dd51-124">Minimize the use of web parts that have large property bags.</span></span>
- <span data-ttu-id="9dd51-125">Gebruik niet-interactieve samenvouw weergaven indien mogelijk.</span><span class="sxs-lookup"><span data-stu-id="9dd51-125">Use non-interactive rollup views when possible.</span></span>
- <span data-ttu-id="9dd51-126">U kunt de grootte van afbeeldingen optimaliseren door afbeeldingen passend te maken met de indelingen voor gecomprimeerde afbeeldingen en ervoor te zorgen dat ze worden gedownload van een CDN.</span><span class="sxs-lookup"><span data-stu-id="9dd51-126">Optimize image sizes by sizing images appropriately, using compressed image formats and ensuring that they are downloaded from a CDN.</span></span>

<span data-ttu-id="9dd51-127">In het volgende artikel vindt u meer informatie over het beperken van pagina gewicht:</span><span class="sxs-lookup"><span data-stu-id="9dd51-127">You can find additional guidance for limiting page weight in the following article:</span></span>

- [<span data-ttu-id="9dd51-128">De prestaties van pagina's in SharePoint optimaliseren</span><span class="sxs-lookup"><span data-stu-id="9dd51-128">Optimize page performance in SharePoint</span></span>](https://docs.microsoft.com/sharepoint/dev/general-development/optimize-page-performance-in-sharepoint)

<span data-ttu-id="9dd51-129">Voordat u de revisies van pagina's aanbrengt om prestatieproblemen te verhelpen, kunt u de laadtijd van de pagina in de analyseresultaten noteren.</span><span class="sxs-lookup"><span data-stu-id="9dd51-129">Before you make page revisions to remediate performance issues, make a note of the page load time in the analysis results.</span></span> <span data-ttu-id="9dd51-130">Voer het hulpprogramma opnieuw uit na de wijziging om te zien of het nieuwe resultaat binnen de basislijn standaard valt en de nieuwe laadtijd voor pagina's te controleren om te zien of er een verbetering was.</span><span class="sxs-lookup"><span data-stu-id="9dd51-130">Run the tool again after your revision to see if the new result is within the baseline standard, and check the new page load time to see if there was an improvement.</span></span>

![Resultaten van laadtijden voor pagina's](../media/modern-portal-optimization/pagediag-page-load-time.png)

>[!NOTE]
><span data-ttu-id="9dd51-132">De laadtijd van de pagina kan variëren, afhankelijk van diverse factoren, zoals netwerkbelasting, tijdstip van de dag en andere tijdelijke voorwaarden.</span><span class="sxs-lookup"><span data-stu-id="9dd51-132">Page load time can vary based on a variety of factors such as network load, time of day, and other transient conditions.</span></span> <span data-ttu-id="9dd51-133">U moet de laadtijd voor pagina's enkele keren vóór en na het aanbrengen van wijzigingen aanbrengen om de resultaten te berekenen.</span><span class="sxs-lookup"><span data-stu-id="9dd51-133">You should test page load time a few times before and after making changes to help you average the results.</span></span>

## <a name="related-topics"></a><span data-ttu-id="9dd51-134">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="9dd51-134">Related topics</span></span>

[<span data-ttu-id="9dd51-135">Prestaties van SharePoint Online afstemmen</span><span class="sxs-lookup"><span data-stu-id="9dd51-135">Tune SharePoint Online performance</span></span>](tune-sharepoint-online-performance.md)

[<span data-ttu-id="9dd51-136">Prestaties van Office 365 afstemmen</span><span class="sxs-lookup"><span data-stu-id="9dd51-136">Tune Office 365 performance</span></span>](tune-microsoft-365-performance.md)

[<span data-ttu-id="9dd51-137">Prestaties in de moderne SharePoint-ervaring</span><span class="sxs-lookup"><span data-stu-id="9dd51-137">Performance in the modern SharePoint experience</span></span>](https://docs.microsoft.com/sharepoint/modern-experience-performance)

[<span data-ttu-id="9dd51-138">Netwerken voor content levering</span><span class="sxs-lookup"><span data-stu-id="9dd51-138">Content delivery networks</span></span>](content-delivery-networks.md)

[<span data-ttu-id="9dd51-139">Het Office 365 Content Delivery Network (CDN) gebruiken met SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="9dd51-139">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)
