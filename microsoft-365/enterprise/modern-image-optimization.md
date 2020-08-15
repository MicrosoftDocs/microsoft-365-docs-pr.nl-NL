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
# <a name="optimize-images-in-sharepoint-online-modern-site-pages"></a><span data-ttu-id="474f5-103">Afbeeldingen in pagina's van de modern SharePoint Online-site optimaliseren</span><span class="sxs-lookup"><span data-stu-id="474f5-103">Optimize images in SharePoint Online modern site pages</span></span>

<span data-ttu-id="474f5-104">In dit artikel vindt u informatie over het optimaliseren van afbeeldingen op pagina's van de modern SharePoint Online-site.</span><span class="sxs-lookup"><span data-stu-id="474f5-104">This article will help you understand how to optimize images in SharePoint Online modern site pages.</span></span>

<span data-ttu-id="474f5-105">Zie afbeeldingen [optimaliseren voor SharePoint Online](image-optimization-for-sharepoint-online.md)voor meer informatie over het optimaliseren van afbeeldingen op klassieke publicerende sites.</span><span class="sxs-lookup"><span data-stu-id="474f5-105">For information about optimizing images in classic publishing sites, see [Image optimization for SharePoint Online](image-optimization-for-sharepoint-online.md)..</span></span>

>[!NOTE]
><span data-ttu-id="474f5-106">Zie [prestaties in de moderne SharePoint-ervaring](https://docs.microsoft.com/sharepoint/modern-experience-performance)voor meer informatie over prestaties in moderne portals voor SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="474f5-106">For more information about performance in SharePoint Online modern portals, see [Performance in the modern SharePoint experience](https://docs.microsoft.com/sharepoint/modern-experience-performance).</span></span>

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-image-optimization"></a><span data-ttu-id="474f5-107">Het hulpprogramma pagina diagnose voor SharePoint gebruiken voor het analyseren van afbeeldingen optimaliseren</span><span class="sxs-lookup"><span data-stu-id="474f5-107">Use the Page Diagnostics for SharePoint tool to analyze image optimization</span></span>

<span data-ttu-id="474f5-108">Het hulpprogramma pagina diagnose voor SharePoint is een browser extensie voor de nieuwe Microsoft Edge- https://www.microsoft.com/edge) en Chrome-browsers die zowel SharePoint Online modern portal als de klassieke publicatiesite pagina's analyseren.</span><span class="sxs-lookup"><span data-stu-id="474f5-108">The Page Diagnostics for SharePoint tool is a browser extension for the new Microsoft Edge (https://www.microsoft.com/edge) and Chrome browsers that analyzes both SharePoint Online modern portal and classic publishing site pages.</span></span> <span data-ttu-id="474f5-109">Het hulpmiddel biedt een rapport voor elke geanalyseerde pagina op basis van een gedefinieerde set prestatiecriteria.</span><span class="sxs-lookup"><span data-stu-id="474f5-109">The tool provides a report for each analyzed page showing how the page performs against a defined set of performance criteria.</span></span> <span data-ttu-id="474f5-110">Ga voor meer informatie over het hulpprogramma pagina diagnose voor SharePoint naar [het hulpprogramma pagina diagnose voor SharePoint Online](page-diagnostics-for-spo.md).</span><span class="sxs-lookup"><span data-stu-id="474f5-110">To install and learn about the Page Diagnostics for SharePoint tool, visit [Use the Page Diagnostics tool for SharePoint Online](page-diagnostics-for-spo.md).</span></span>

>[!NOTE]
><span data-ttu-id="474f5-111">Het hulpmiddel voor het automatisch toevoegen van pagina's werkt alleen voor SharePoint Online en kan niet worden gebruikt op een SharePoint-systeempagina.</span><span class="sxs-lookup"><span data-stu-id="474f5-111">The Page Diagnostics tool only works for SharePoint Online, and cannot be used on a SharePoint system page.</span></span>

<span data-ttu-id="474f5-112">Wanneer u een moderne SharePoint-site met behulp van het hulpprogramma pagina diagnose voor SharePoint Analyseer, kunt u informatie over grote afbeeldingen bekijken in het deelvenster _diagnostische tests_ .</span><span class="sxs-lookup"><span data-stu-id="474f5-112">When you analyze a SharePoint modern site with the Page Diagnostics for SharePoint tool, you can see information about large images in the _Diagnostic tests_ pane.</span></span>

<span data-ttu-id="474f5-113">Mogelijke resultaten zijn onder meer:</span><span class="sxs-lookup"><span data-stu-id="474f5-113">Possible results include:</span></span>

- <span data-ttu-id="474f5-114">**Aandacht vereist** (rood): de pagina bevat **een of meer** afbeeldingen met een grootte van 300KB</span><span class="sxs-lookup"><span data-stu-id="474f5-114">**Attention required** (red): The page contains **one or more** images over 300KB in size</span></span>
- <span data-ttu-id="474f5-115">**Geen actie vereist** (groen): de pagina bevat geen afbeeldingen met een grootte van 300KB</span><span class="sxs-lookup"><span data-stu-id="474f5-115">**No action required** (green): The page contains no images over 300KB in size</span></span>

<span data-ttu-id="474f5-116">Als het resultaat van de **grote afbeeldingen** wordt weergegeven in de sectie **aandacht vereist** van de resultaten, klikt u op het resultaat om aanvullende details weer te geven.</span><span class="sxs-lookup"><span data-stu-id="474f5-116">If the **Large images detected** result appears in the **Attention required** section of the results, you can click the result to see additional details.</span></span>

![Resultaten van het hulpmiddel pagina diagnose](../media/modern-portal-optimization/pagediag-large-images.png)

## <a name="remediate-large-image-issues"></a><span data-ttu-id="474f5-118">Problemen met grote afbeeldingen oplossen</span><span class="sxs-lookup"><span data-stu-id="474f5-118">Remediate large image issues</span></span>

<span data-ttu-id="474f5-119">Als een pagina afbeeldingen met afbeeldingen van 300KB bevat, selecteert u het resultaat voor de **grote afbeeldingen** om te zien welke afbeeldingen te groot zijn.</span><span class="sxs-lookup"><span data-stu-id="474f5-119">If a page contains images over 300KB in size, select the **Large images detected** result to see which images are too large.</span></span> <span data-ttu-id="474f5-120">Op de moderne SharePoint Online-pagina's worden weergaven van afbeeldingen binnen de grootte van het browservenster en de resolutie van de client monitor automatisch aangegeven en gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="474f5-120">In modern SharePoint Online pages, renditions of images are automatically provided and sized depending on the size of the browser window and the resolution of the client monitor.</span></span> <span data-ttu-id="474f5-121">U moet altijd afbeeldingen voor webgebruik optimaliseren voordat u ze uploadt naar SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="474f5-121">You should always optimize images for web use prior to upload to SharePoint Online.</span></span> <span data-ttu-id="474f5-122">Zeer grote afbeeldingen worden automatisch kleiner in grootte en resolutie, wat kan leiden tot onverwachte weergavekenmerken.</span><span class="sxs-lookup"><span data-stu-id="474f5-122">Very large images will be automatically reduced in size and resolution which can result in unexpected rendering characteristics.</span></span>

<span data-ttu-id="474f5-123">Voordat u de revisies van pagina's aanbrengt om prestatieproblemen te verhelpen, kunt u de laadtijd van de pagina in de analyseresultaten noteren.</span><span class="sxs-lookup"><span data-stu-id="474f5-123">Before you make page revisions to remediate performance issues, make a note of the page load time in the analysis results.</span></span> <span data-ttu-id="474f5-124">Voer het hulpprogramma opnieuw uit na de wijziging om te zien of het nieuwe resultaat binnen de basislijn standaard valt en de nieuwe laadtijd voor pagina's te controleren om te zien of er een verbetering was.</span><span class="sxs-lookup"><span data-stu-id="474f5-124">Run the tool again after your revision to see if the new result is within the baseline standard, and check the new page load time to see if there was an improvement.</span></span>

![Resultaten van laadtijden voor pagina's](../media/modern-portal-optimization/pagediag-page-load-time.png)

>[!NOTE]
><span data-ttu-id="474f5-126">De laadtijd van de pagina kan variëren, afhankelijk van diverse factoren, zoals netwerkbelasting, tijdstip van de dag en andere tijdelijke voorwaarden.</span><span class="sxs-lookup"><span data-stu-id="474f5-126">Page load time can vary based on a variety of factors such as network load, time of day, and other transient conditions.</span></span> <span data-ttu-id="474f5-127">U moet de laadtijd voor pagina's enkele keren vóór en na het aanbrengen van wijzigingen aanbrengen om de resultaten te berekenen.</span><span class="sxs-lookup"><span data-stu-id="474f5-127">You should test page load time a few times before and after making changes to help you average the results.</span></span>

## <a name="related-topics"></a><span data-ttu-id="474f5-128">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="474f5-128">Related topics</span></span>

[<span data-ttu-id="474f5-129">Prestaties van SharePoint Online afstemmen</span><span class="sxs-lookup"><span data-stu-id="474f5-129">Tune SharePoint Online performance</span></span>](tune-sharepoint-online-performance.md)

[<span data-ttu-id="474f5-130">Prestaties van Office 365 afstemmen</span><span class="sxs-lookup"><span data-stu-id="474f5-130">Tune Office 365 performance</span></span>](tune-microsoft-365-performance.md)

[<span data-ttu-id="474f5-131">Prestaties in de moderne SharePoint-ervaring</span><span class="sxs-lookup"><span data-stu-id="474f5-131">Performance in the modern SharePoint experience</span></span>](https://docs.microsoft.com/sharepoint/modern-experience-performance)

[<span data-ttu-id="474f5-132">Netwerken voor content levering</span><span class="sxs-lookup"><span data-stu-id="474f5-132">Content delivery networks</span></span>](content-delivery-networks.md)

[<span data-ttu-id="474f5-133">Het Office 365 Content Delivery Network (CDN) gebruiken met SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="474f5-133">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)
