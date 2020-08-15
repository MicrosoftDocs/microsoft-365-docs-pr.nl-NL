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
# <a name="optimize-iframes-in-sharepoint-online-modern-and-classic-publishing-site-pages"></a><span data-ttu-id="0a776-103">IFrames optimaliseren in SharePoint Online-pagina's van de publicerende site</span><span class="sxs-lookup"><span data-stu-id="0a776-103">Optimize iFrames in SharePoint Online modern and classic publishing site pages</span></span>

<span data-ttu-id="0a776-104">iFrames kunnen handig zijn voor het weergeven van inhouds rijke inhoud, zoals Video's of andere media.</span><span class="sxs-lookup"><span data-stu-id="0a776-104">iFrames can be useful for previewing rich content such as videos or other media.</span></span> <span data-ttu-id="0a776-105">Aangezien iFrames wel een aparte pagina op de pagina van de SharePoint-site laadt, kan de inhoud die in het iFrame wordt geladen grote afbeeldingen, Video's of andere elementen bevatten die kunnen bijdragen aan de totale laadtijden van pagina's en die u niet kunt beheren op de pagina.</span><span class="sxs-lookup"><span data-stu-id="0a776-105">However, because iFrames load a separate page within the SharePoint site page, content loaded in the iFrame could contain large images, videos or other elements that can contribute to overall page load times and that you cannot control on the page.</span></span> <span data-ttu-id="0a776-106">In dit artikel vindt u informatie over hoe u kunt bepalen hoe iFrames in uw pagina's van invloed zijn op de beschikbare latentie en hoe u veelvoorkomende problemen kunt oplossen.</span><span class="sxs-lookup"><span data-stu-id="0a776-106">This article will help you understand how to determine how iFrames in your pages affect user perceived latency, and how to remediate common issues.</span></span>

>[!NOTE]
><span data-ttu-id="0a776-107">Ga voor meer informatie over de prestaties van moderne SharePoint Online-sites naar [prestaties in de moderne SharePoint-ervaring](https://docs.microsoft.com/sharepoint/modern-experience-performance).</span><span class="sxs-lookup"><span data-stu-id="0a776-107">For more information about performance in SharePoint Online modern sites, see [Performance in the modern SharePoint experience](https://docs.microsoft.com/sharepoint/modern-experience-performance).</span></span>

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-web-parts-using-iframes"></a><span data-ttu-id="0a776-108">Het hulpprogramma voor het analyseren van webonderdelen met behulp van het hulpprogramma pagina diagnose voor SharePoint gebruiken</span><span class="sxs-lookup"><span data-stu-id="0a776-108">Use the Page Diagnostics for SharePoint tool to analyze web parts using iFrames</span></span>

<span data-ttu-id="0a776-109">Het hulpprogramma pagina diagnose voor SharePoint is een browser extensie voor de nieuwe Microsoft Edge- https://www.microsoft.com/edge) en Chrome-browsers die zowel SharePoint Online modern portal als de klassieke publicatiesite pagina's analyseren.</span><span class="sxs-lookup"><span data-stu-id="0a776-109">The Page Diagnostics for SharePoint tool is a browser extension for the new Microsoft Edge (https://www.microsoft.com/edge) and Chrome browsers that analyzes both SharePoint Online modern portal and classic publishing site pages.</span></span> <span data-ttu-id="0a776-110">Het hulpmiddel biedt een rapport voor elke geanalyseerde pagina op basis van een gedefinieerde set prestatiecriteria.</span><span class="sxs-lookup"><span data-stu-id="0a776-110">The tool provides a report for each analyzed page showing how the page performs against a defined set of performance criteria.</span></span> <span data-ttu-id="0a776-111">Ga voor meer informatie over het hulpprogramma pagina diagnose voor SharePoint naar [het hulpprogramma pagina diagnose voor SharePoint Online](page-diagnostics-for-spo.md).</span><span class="sxs-lookup"><span data-stu-id="0a776-111">To install and learn about the Page Diagnostics for SharePoint tool, visit [Use the Page Diagnostics tool for SharePoint Online](page-diagnostics-for-spo.md).</span></span>

>[!NOTE]
><span data-ttu-id="0a776-112">Het hulpmiddel voor het automatisch toevoegen van pagina's werkt alleen voor SharePoint Online en kan niet worden gebruikt op een SharePoint-systeempagina.</span><span class="sxs-lookup"><span data-stu-id="0a776-112">The Page Diagnostics tool only works for SharePoint Online, and cannot be used on a SharePoint system page.</span></span>

<span data-ttu-id="0a776-113">Wanneer u een SharePoint-sitepagina wilt analyseren met het hulpprogramma pagina diagnose voor SharePoint, kunt u informatie weergeven over webonderdelen met iFrames in het deelvenster _diagnostische tests_ .</span><span class="sxs-lookup"><span data-stu-id="0a776-113">When you analyze a SharePoint site page with the Page Diagnostics for SharePoint tool, you can see information about web parts containing iFrames in the _Diagnostic tests_ pane.</span></span> <span data-ttu-id="0a776-114">De metric van basislijn is hetzelfde voor moderne en klassieke pagina's.</span><span class="sxs-lookup"><span data-stu-id="0a776-114">The baseline metric is the same for modern and classic pages.</span></span>

<span data-ttu-id="0a776-115">Mogelijke resultaten zijn onder meer:</span><span class="sxs-lookup"><span data-stu-id="0a776-115">Possible results include:</span></span>

- <span data-ttu-id="0a776-116">**Aandacht vereist** (rood): de pagina bevat **drie of meer** webonderdelen met IFRAME-instellingen</span><span class="sxs-lookup"><span data-stu-id="0a776-116">**Attention required** (red): The page contains **three or more** web parts using iFrames</span></span>
- <span data-ttu-id="0a776-117">**Verbeterings mogelijkheden** (geel): de pagina bevat **een of twee** webonderdelen met behulp van iframes</span><span class="sxs-lookup"><span data-stu-id="0a776-117">**Improvement opportunities** (yellow): The page contains **one or two** web parts using iFrames</span></span>
- <span data-ttu-id="0a776-118">**Geen actie vereist** (groen): de pagina bevat geen webonderdelen die gebruikmaken van iframe-instellingen</span><span class="sxs-lookup"><span data-stu-id="0a776-118">**No action required** (green): The page contains no web parts using iFrames</span></span>

<span data-ttu-id="0a776-119">Als het resultaat van de **webonderdelen die gebruikmaken van iframe-detectie** worden weergegeven in de sectie **verbeterings mogelijkheden** of **aandacht vereist)** , kunt u op het resultaat klikken om de webonderdelen te zien die iframes bevatten.</span><span class="sxs-lookup"><span data-stu-id="0a776-119">If the **Web parts using iFrames detected** result appears in either the **Improvement opportunities** or **Attention required)** section of the results, you can click the result to see the web parts that contain iFrames.</span></span>

![Resultaten van het hulpmiddel pagina diagnose](../media/modern-portal-optimization/pagediag-iframe-yellow.png)

## <a name="remediate-iframe-performance-issues"></a><span data-ttu-id="0a776-121">Prestatieproblemen met iFrame oplossen</span><span class="sxs-lookup"><span data-stu-id="0a776-121">Remediate iFrame performance issues</span></span>

<span data-ttu-id="0a776-122">Het resultaat van de **webonderdelen met iframes gedetecteerd** in het hulpprogramma voor het controleren van pagina's gebruiken om te bepalen welke webonderdelen iframes bevatten en mogelijk worden gelaadd voor trage pagina's.</span><span class="sxs-lookup"><span data-stu-id="0a776-122">Use the **Web parts using iFrames detected** result in the Page Diagnostic tool to determine which web parts contain iFrames and may be contributing to slow page load times.</span></span>

<span data-ttu-id="0a776-123">iFrames zijn inherent aan een traag feit omdat ze een afzonderlijke externe pagina laden, waaronder alle bijbehorende inhoud, zoals JavaScript, CSS-en Framework-elementen, waardoor de overhead van de sitepagina door een factor van twee of meer kan toenemen.</span><span class="sxs-lookup"><span data-stu-id="0a776-123">iFrames are inherently slow because they load a separate external page including all associated content such as javascript, CSS and framework elements, potentially increasing the overhead of the site page by a factor of two or more.</span></span>

<span data-ttu-id="0a776-124">Volg de onderstaande richtlijnen om te zorgen voor optimaal gebruik van iFrames.</span><span class="sxs-lookup"><span data-stu-id="0a776-124">Follow the guidance below to ensure optimal use of iFrames.</span></span>

- <span data-ttu-id="0a776-125">Gebruik afbeeldingen in plaats van iFrames, indien mogelijk, en als het voorbeeld klein is om te beginnen met of niet-interactief.</span><span class="sxs-lookup"><span data-stu-id="0a776-125">When possible, use images instead of iFrames if the preview is small to begin with or non-interactive.</span></span>
- <span data-ttu-id="0a776-126">Als iFrames moeten worden gebruikt, minimaliseert u het nummer en/of verplaatst u ze uit de viewport.</span><span class="sxs-lookup"><span data-stu-id="0a776-126">If iFrames must be used, minimize the number and/or move them out of the viewport.</span></span>
- <span data-ttu-id="0a776-127">Ingesloten Office-bestanden zoals Word, Excel en PowerPoint zijn interactief, maar zijn langzaam te laden.</span><span class="sxs-lookup"><span data-stu-id="0a776-127">Embedded Office files like Word, Excel and PowerPoint are interactive, but are slow to load.</span></span> <span data-ttu-id="0a776-128">Afbeeldingen met miniaturen met een koppeling naar het volledige document worden vaak beter.</span><span class="sxs-lookup"><span data-stu-id="0a776-128">Image thumbnails with a link to the full document will often perform better.</span></span>
- <span data-ttu-id="0a776-129">Ingesloten YouTube-Video's en Twitter-feeds worden meestal beter in iFrames opgenomen, maar u kunt wel gebruikmaken van deze soorten ingesloten bestanden.</span><span class="sxs-lookup"><span data-stu-id="0a776-129">Embedded YouTube videos and Twitter feeds tend to perform better in iFrames, but use these kinds of embeds judiciously.</span></span>
- <span data-ttu-id="0a776-130">Geïsoleerde webonderdelen vormen een redelijke uitzondering, maar beperken hun nummer en plaats in de viewport View.</span><span class="sxs-lookup"><span data-stu-id="0a776-130">Isolated web parts are a reasonable exception, but minimize their number and placement in the viewport.</span></span>
- <span data-ttu-id="0a776-131">Als een iFrame zich in de viewport bevindt, kunt u een _IntersectionObserver_ gebruiken om de weergave van de iframe te vertragen totdat deze in beeld komt.</span><span class="sxs-lookup"><span data-stu-id="0a776-131">If an iFrame is located out of the viewport, consider using an _IntersectionObserver_ to delay rendering the iFrame until it comes into view.</span></span>

<span data-ttu-id="0a776-132">Voordat u de revisies van pagina's aanbrengt om prestatieproblemen te verhelpen, kunt u de laadtijd van de pagina in de analyseresultaten noteren.</span><span class="sxs-lookup"><span data-stu-id="0a776-132">Before you make page revisions to remediate performance issues, make a note of the page load time in the analysis results.</span></span> <span data-ttu-id="0a776-133">Voer het hulpprogramma opnieuw uit na de wijziging om te zien of het nieuwe resultaat binnen de basislijn standaard valt en de nieuwe laadtijd voor pagina's te controleren om te zien of er een verbetering was.</span><span class="sxs-lookup"><span data-stu-id="0a776-133">Run the tool again after your revision to see if the new result is within the baseline standard, and check the new page load time to see if there was an improvement.</span></span>

![Resultaten van laadtijden voor pagina's](../media/modern-portal-optimization/pagediag-page-load-time.png)

>[!NOTE]
><span data-ttu-id="0a776-135">De laadtijd van de pagina kan variëren, afhankelijk van diverse factoren, zoals netwerkbelasting, tijdstip van de dag en andere tijdelijke voorwaarden.</span><span class="sxs-lookup"><span data-stu-id="0a776-135">Page load time can vary based on a variety of factors such as network load, time of day, and other transient conditions.</span></span> <span data-ttu-id="0a776-136">U moet de laadtijd voor pagina's enkele keren vóór en na het aanbrengen van wijzigingen aanbrengen om de resultaten te berekenen.</span><span class="sxs-lookup"><span data-stu-id="0a776-136">You should test page load time a few times before and after making changes to help you average the results.</span></span>

## <a name="related-topics"></a><span data-ttu-id="0a776-137">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="0a776-137">Related topics</span></span>

[<span data-ttu-id="0a776-138">Prestaties van SharePoint Online afstemmen</span><span class="sxs-lookup"><span data-stu-id="0a776-138">Tune SharePoint Online performance</span></span>](tune-sharepoint-online-performance.md)

[<span data-ttu-id="0a776-139">Prestaties van Office 365 afstemmen</span><span class="sxs-lookup"><span data-stu-id="0a776-139">Tune Office 365 performance</span></span>](tune-microsoft-365-performance.md)

[<span data-ttu-id="0a776-140">Prestaties in de moderne SharePoint-ervaring</span><span class="sxs-lookup"><span data-stu-id="0a776-140">Performance in the modern SharePoint experience</span></span>](https://docs.microsoft.com/sharepoint/modern-experience-performance)
