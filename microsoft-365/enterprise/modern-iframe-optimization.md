---
title: iFrames optimaliseren in SharePoint moderne en klassieke publicatiesitepagina's online
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
description: Meer informatie over het optimaliseren van de prestaties van iFrames in SharePoint moderne en klassieke publicerende sitepagina's online.
ms.openlocfilehash: d6e9aefa23972589c752540959b17f5d20ed0889
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923054"
---
# <a name="optimize-iframes-in-sharepoint-online-modern-and-classic-publishing-site-pages"></a><span data-ttu-id="dfe27-103">iFrames optimaliseren in SharePoint moderne en klassieke publicatiesitepagina's online</span><span class="sxs-lookup"><span data-stu-id="dfe27-103">Optimize iFrames in SharePoint Online modern and classic publishing site pages</span></span>

<span data-ttu-id="dfe27-104">iFrames kunnen handig zijn voor het bekijken van uitgebreide inhoud, zoals video's of andere media.</span><span class="sxs-lookup"><span data-stu-id="dfe27-104">iFrames can be useful for previewing rich content such as videos or other media.</span></span> <span data-ttu-id="dfe27-105">Omdat iFrames echter een afzonderlijke pagina laden op de sitepagina van SharePoint, kan inhoud die in het iFrame wordt geladen, grote afbeeldingen, video's of andere elementen bevatten die kunnen bijdragen aan de totale laadtijden van pagina's en die u niet kunt bepalen op de pagina.</span><span class="sxs-lookup"><span data-stu-id="dfe27-105">However, because iFrames load a separate page within the SharePoint site page, content loaded in the iFrame could contain large images, videos or other elements that can contribute to overall page load times and that you cannot control on the page.</span></span> <span data-ttu-id="dfe27-106">In dit artikel wordt beschreven hoe u kunt bepalen hoe iFrames op uw pagina's van invloed zijn op de waargenomen latentie van de gebruiker en hoe u veelvoorkomende problemen kunt oplossen.</span><span class="sxs-lookup"><span data-stu-id="dfe27-106">This article will help you understand how to determine how iFrames in your pages affect user perceived latency, and how to remediate common issues.</span></span>

>[!NOTE]
><span data-ttu-id="dfe27-107">Zie Prestaties in de moderne SharePoint voor meer informatie over prestaties in SharePoint moderne [onlinesites.](/sharepoint/modern-experience-performance)</span><span class="sxs-lookup"><span data-stu-id="dfe27-107">For more information about performance in SharePoint Online modern sites, see [Performance in the modern SharePoint experience](/sharepoint/modern-experience-performance).</span></span>

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-web-parts-using-iframes"></a><span data-ttu-id="dfe27-108">Het hulpprogramma Paginadiagnose voor SharePoint gebruiken om webonderdelen te analyseren met iFrames</span><span class="sxs-lookup"><span data-stu-id="dfe27-108">Use the Page Diagnostics for SharePoint tool to analyze web parts using iFrames</span></span>

<span data-ttu-id="dfe27-109">Het hulpprogramma Paginadiagnose voor SharePoint is een browserextensie voor de nieuwe Microsoft Edge ( en Chrome-browsers die zowel SharePoint Moderne portal online als klassieke https://www.microsoft.com/edge) publicerende sitepagina's analyseren.</span><span class="sxs-lookup"><span data-stu-id="dfe27-109">The Page Diagnostics for SharePoint tool is a browser extension for the new Microsoft Edge (https://www.microsoft.com/edge) and Chrome browsers that analyzes both SharePoint Online modern portal and classic publishing site pages.</span></span> <span data-ttu-id="dfe27-110">Het hulpprogramma bevat een rapport voor elke geanalyseerde pagina die laat zien hoe de pagina presteert op basis van een gedefinieerde set prestatiecriteria.</span><span class="sxs-lookup"><span data-stu-id="dfe27-110">The tool provides a report for each analyzed page showing how the page performs against a defined set of performance criteria.</span></span> <span data-ttu-id="dfe27-111">Als u het hulpprogramma Paginadiagnose voor SharePoint wilt installeren en meer wilt weten, gaat u naar Het hulpprogramma [Paginadiagnose gebruiken](page-diagnostics-for-spo.md)voor SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="dfe27-111">To install and learn about the Page Diagnostics for SharePoint tool, visit [Use the Page Diagnostics tool for SharePoint Online](page-diagnostics-for-spo.md).</span></span>

>[!NOTE]
><span data-ttu-id="dfe27-112">Het hulpprogramma Paginadiagnose werkt alleen SharePoint Online en kan niet worden gebruikt op een SharePoint systeempagina.</span><span class="sxs-lookup"><span data-stu-id="dfe27-112">The Page Diagnostics tool only works for SharePoint Online, and cannot be used on a SharePoint system page.</span></span>

<span data-ttu-id="dfe27-113">Wanneer u een SharePoint sitepagina analyseert met het hulpprogramma Paginadiagnose voor SharePoint, ziet u informatie over webonderdelen met iFrames in het deelvenster _Diagnostische_ tests.</span><span class="sxs-lookup"><span data-stu-id="dfe27-113">When you analyze a SharePoint site page with the Page Diagnostics for SharePoint tool, you can see information about web parts containing iFrames in the _Diagnostic tests_ pane.</span></span> <span data-ttu-id="dfe27-114">De basislijnmetriek is hetzelfde voor moderne en klassieke pagina's.</span><span class="sxs-lookup"><span data-stu-id="dfe27-114">The baseline metric is the same for modern and classic pages.</span></span>

<span data-ttu-id="dfe27-115">Mogelijke resultaten zijn:</span><span class="sxs-lookup"><span data-stu-id="dfe27-115">Possible results include:</span></span>

- <span data-ttu-id="dfe27-116">**Aandacht vereist** (rood): de pagina bevat **drie of meer** webonderdelen met iFrames</span><span class="sxs-lookup"><span data-stu-id="dfe27-116">**Attention required** (red): The page contains **three or more** web parts using iFrames</span></span>
- <span data-ttu-id="dfe27-117">**Verbeterkansen** (geel): De pagina bevat **een of twee** webonderdelen met iFrames</span><span class="sxs-lookup"><span data-stu-id="dfe27-117">**Improvement opportunities** (yellow): The page contains **one or two** web parts using iFrames</span></span>
- <span data-ttu-id="dfe27-118">**Geen actie vereist** (groen): de pagina bevat geen webonderdelen met iFrames</span><span class="sxs-lookup"><span data-stu-id="dfe27-118">**No action required** (green): The page contains no web parts using iFrames</span></span>

<span data-ttu-id="dfe27-119">Als de webonderdelen met **iFrames** gedetecteerd resultaat  worden  weergegeven in de sectie Verbeterkansen of Aandacht vereist) van de resultaten, kunt u op het resultaat klikken om de webonderdelen te zien die iFrames bevatten.</span><span class="sxs-lookup"><span data-stu-id="dfe27-119">If the **Web parts using iFrames detected** result appears in either the **Improvement opportunities** or **Attention required)** section of the results, you can click the result to see the web parts that contain iFrames.</span></span>

![Resultaten van het hulpprogramma Paginadiagnose](../media/modern-portal-optimization/pagediag-iframe-yellow.png)

## <a name="remediate-iframe-performance-issues"></a><span data-ttu-id="dfe27-121">Problemen met de prestaties van iFrame oplossen</span><span class="sxs-lookup"><span data-stu-id="dfe27-121">Remediate iFrame performance issues</span></span>

<span data-ttu-id="dfe27-122">Gebruik de webonderdelen met **iFrames** gedetecteerd resultaat in het hulpprogramma Paginadiagnose om te bepalen welke webonderdelen iFrames bevatten en kunnen bijdragen aan trage laadtijden voor pagina's.</span><span class="sxs-lookup"><span data-stu-id="dfe27-122">Use the **Web parts using iFrames detected** result in the Page Diagnostic tool to determine which web parts contain iFrames and may be contributing to slow page load times.</span></span>

<span data-ttu-id="dfe27-123">iFrames zijn inherent traag omdat ze een afzonderlijke externe pagina laden, inclusief alle bijbehorende inhoud, zoals javascript, CSS en framework-elementen, waardoor de overhead van de sitepagina mogelijk met twee of meer wordt verhogen.</span><span class="sxs-lookup"><span data-stu-id="dfe27-123">iFrames are inherently slow because they load a separate external page including all associated content such as javascript, CSS and framework elements, potentially increasing the overhead of the site page by a factor of two or more.</span></span>

<span data-ttu-id="dfe27-124">Volg de onderstaande richtlijnen om ervoor te zorgen dat iFrames optimaal worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="dfe27-124">Follow the guidance below to ensure optimal use of iFrames.</span></span>

- <span data-ttu-id="dfe27-125">Gebruik indien mogelijk afbeeldingen in plaats van iFrames als de preview klein is om te beginnen of niet interactief is.</span><span class="sxs-lookup"><span data-stu-id="dfe27-125">When possible, use images instead of iFrames if the preview is small to begin with or non-interactive.</span></span>
- <span data-ttu-id="dfe27-126">Als iFrames moeten worden gebruikt, minimaliseert u het aantal en/of verplaatst u deze uit de viewport.</span><span class="sxs-lookup"><span data-stu-id="dfe27-126">If iFrames must be used, minimize the number and/or move them out of the viewport.</span></span>
- <span data-ttu-id="dfe27-127">Ingesloten Office, zoals Word, Excel en PowerPoint zijn interactief, maar worden traag geladen.</span><span class="sxs-lookup"><span data-stu-id="dfe27-127">Embedded Office files like Word, Excel and PowerPoint are interactive, but are slow to load.</span></span> <span data-ttu-id="dfe27-128">Miniatuurafbeeldingen met een koppeling naar het volledige document presteren vaak beter.</span><span class="sxs-lookup"><span data-stu-id="dfe27-128">Image thumbnails with a link to the full document will often perform better.</span></span>
- <span data-ttu-id="dfe27-129">Ingesloten YouTube-video's en Twitter-feeds presteren meestal beter in iFrames, maar gebruiken dit soort insluitingen op een verstandige manier.</span><span class="sxs-lookup"><span data-stu-id="dfe27-129">Embedded YouTube videos and Twitter feeds tend to perform better in iFrames, but use these kinds of embeds judiciously.</span></span>
- <span data-ttu-id="dfe27-130">Geïsoleerde webonderdelen vormen een redelijke uitzondering, maar minimaliseren het aantal en de plaatsing ervan in de viewport.</span><span class="sxs-lookup"><span data-stu-id="dfe27-130">Isolated web parts are a reasonable exception, but minimize their number and placement in the viewport.</span></span>
- <span data-ttu-id="dfe27-131">Als een iFrame zich buiten de viewport bevindt, kunt u overwegen een _IntersectionObserver_ te gebruiken om de weergave van het iFrame uit te stellen totdat deze in beeld komt.</span><span class="sxs-lookup"><span data-stu-id="dfe27-131">If an iFrame is located out of the viewport, consider using an _IntersectionObserver_ to delay rendering the iFrame until it comes into view.</span></span>

<span data-ttu-id="dfe27-132">Voordat u paginaherzieningen maakt om prestatieproblemen op te lossen, noteert u de laadtijd van de pagina in de analyseresultaten.</span><span class="sxs-lookup"><span data-stu-id="dfe27-132">Before you make page revisions to remediate performance issues, make a note of the page load time in the analysis results.</span></span> <span data-ttu-id="dfe27-133">Voer het hulpprogramma na de revisie opnieuw uit om te zien of het nieuwe resultaat binnen de basislijnstandaard valt en controleer de laadtijd van de nieuwe pagina om te zien of er een verbetering is.</span><span class="sxs-lookup"><span data-stu-id="dfe27-133">Run the tool again after your revision to see if the new result is within the baseline standard, and check the new page load time to see if there was an improvement.</span></span>

![De laadtijd van pagina's](../media/modern-portal-optimization/pagediag-page-load-time.png)

>[!NOTE]
><span data-ttu-id="dfe27-135">De laadtijd van pagina's kan variëren op basis van verschillende factoren, zoals de netwerkbelasting, de tijd van de dag en andere tijdelijke omstandigheden.</span><span class="sxs-lookup"><span data-stu-id="dfe27-135">Page load time can vary based on a variety of factors such as network load, time of day, and other transient conditions.</span></span> <span data-ttu-id="dfe27-136">U moet de laadtijd van pagina's een paar keer voor en na het aanbrengen van wijzigingen testen, zodat u de resultaten kunt gemiddelden.</span><span class="sxs-lookup"><span data-stu-id="dfe27-136">You should test page load time a few times before and after making changes to help you average the results.</span></span>

## <a name="related-topics"></a><span data-ttu-id="dfe27-137">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="dfe27-137">Related topics</span></span>

[<span data-ttu-id="dfe27-138">Prestaties SharePoint online afstemmen</span><span class="sxs-lookup"><span data-stu-id="dfe27-138">Tune SharePoint Online performance</span></span>](tune-sharepoint-online-performance.md)

[<span data-ttu-id="dfe27-139">Prestaties Office 365 afstemmen</span><span class="sxs-lookup"><span data-stu-id="dfe27-139">Tune Office 365 performance</span></span>](tune-microsoft-365-performance.md)

[<span data-ttu-id="dfe27-140">Prestaties in de moderne SharePoint ervaring</span><span class="sxs-lookup"><span data-stu-id="dfe27-140">Performance in the modern SharePoint experience</span></span>](/sharepoint/modern-experience-performance)