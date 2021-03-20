---
title: Paginagewicht optimaliseren in moderne sitepagina's van SharePoint Online
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
description: Lees hoe u het hulpprogramma Paginadiagnose gebruikt om het paginagewicht te optimaliseren in moderne sitepagina's van SharePoint Online.
ms.openlocfilehash: 780d8ca0debbc5efb834f8f3543b9a5a8d168108
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907442"
---
# <a name="optimize-page-weight-in-sharepoint-online-modern-site-pages"></a><span data-ttu-id="4bd51-103">Paginagewicht optimaliseren in moderne sitepagina's van SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="4bd51-103">Optimize page weight in SharePoint Online modern site pages</span></span>

<span data-ttu-id="4bd51-104">Moderne SharePoint Online-sitepagina's bevatten seriële code die is vereist om pagina-inhoud van de pagina weer te geven, inclusief afbeeldingen, tekst, objecten in het inhoudsgebied onder navigatie-/opdrachtbalken en andere HTML-code die het kader van de pagina vormt.</span><span class="sxs-lookup"><span data-stu-id="4bd51-104">SharePoint Online modern site pages contain serialized code that is required to render page content of the page, including images, text, objects in the content area underneath navigation/command bars and other HTML code that forms the framework of the page.</span></span> <span data-ttu-id="4bd51-105">Paginagewicht is een meting van deze HTML-code en moet worden beperkt om optimale laadtijden voor pagina's te garanderen.</span><span class="sxs-lookup"><span data-stu-id="4bd51-105">Page weight is a measurement of this HTML code, and should be limited to ensure optimal page load times.</span></span>

<span data-ttu-id="4bd51-106">In dit artikel wordt beschreven hoe u het paginagewicht op uw moderne sitepagina's kunt verminderen.</span><span class="sxs-lookup"><span data-stu-id="4bd51-106">This article will help you understand how to reduce page weight in your modern site pages.</span></span>

>[!NOTE]
><span data-ttu-id="4bd51-107">Zie Prestaties in de [moderne SharePoint-ervaring](/sharepoint/modern-experience-performance)voor meer informatie over de prestaties in moderne SharePoint Online-portals.</span><span class="sxs-lookup"><span data-stu-id="4bd51-107">For more information about performance in SharePoint Online modern portals, see [Performance in the modern SharePoint experience](/sharepoint/modern-experience-performance).</span></span>

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-page-weight"></a><span data-ttu-id="4bd51-108">Het hulpprogramma Paginadiagnose voor SharePoint gebruiken om het paginagewicht te analyseren</span><span class="sxs-lookup"><span data-stu-id="4bd51-108">Use the Page Diagnostics for SharePoint tool to analyze page weight</span></span>

<span data-ttu-id="4bd51-109">Het hulpprogramma Paginadiagnose voor SharePoint is een browserextensie voor de nieuwe Microsoft Edge - en Chrome-browsers waarmee zowel moderne portals van SharePoint Online als klassieke https://www.microsoft.com/edge) publicerende sitepagina's worden geanalyseerd.</span><span class="sxs-lookup"><span data-stu-id="4bd51-109">The Page Diagnostics for SharePoint tool is a browser extension for the new Microsoft Edge (https://www.microsoft.com/edge) and Chrome browsers that analyzes both SharePoint Online modern portal and classic publishing site pages.</span></span> <span data-ttu-id="4bd51-110">Het hulpprogramma bevat een rapport voor elke geanalyseerde pagina die laat zien hoe de pagina presteert op basis van een gedefinieerde set prestatiecriteria.</span><span class="sxs-lookup"><span data-stu-id="4bd51-110">The tool provides a report for each analyzed page showing how the page performs against a defined set of performance criteria.</span></span> <span data-ttu-id="4bd51-111">Als u het hulpprogramma Paginadiagnose voor SharePoint wilt installeren en meer wilt weten, gaat u naar Het hulpprogramma [Paginadiagnose gebruiken voor SharePoint Online.](page-diagnostics-for-spo.md)</span><span class="sxs-lookup"><span data-stu-id="4bd51-111">To install and learn about the Page Diagnostics for SharePoint tool, visit [Use the Page Diagnostics tool for SharePoint Online](page-diagnostics-for-spo.md).</span></span>

>[!NOTE]
><span data-ttu-id="4bd51-112">Het hulpprogramma Paginadiagnose werkt alleen voor SharePoint Online en kan niet worden gebruikt op een SharePoint-systeempagina.</span><span class="sxs-lookup"><span data-stu-id="4bd51-112">The Page Diagnostics tool only works for SharePoint Online, and cannot be used on a SharePoint system page.</span></span>

<span data-ttu-id="4bd51-113">Wanneer u een SharePoint-sitepagina analyseert met het hulpprogramma Paginadiagnose voor SharePoint, ziet u informatie over de pagina in het pagina-gewicht onder **500 KB-resultaat** van het deelvenster _Diagnostische tests._</span><span class="sxs-lookup"><span data-stu-id="4bd51-113">When you analyze a SharePoint site page with the Page Diagnostics for SharePoint tool, you can see information about page in the **Page weight under 500KB** result of the _Diagnostic tests_ pane.</span></span> <span data-ttu-id="4bd51-114">Het resultaat wordt groen weergegeven als het paginagewicht onder de basislijnwaarde valt en rood als het paginagewicht de basislijnwaarde overschrijdt.</span><span class="sxs-lookup"><span data-stu-id="4bd51-114">The result will appear in green if the page weight is under the baseline value, and red if the page weight exceeds the baseline value.</span></span>

<span data-ttu-id="4bd51-115">Mogelijke resultaten zijn:</span><span class="sxs-lookup"><span data-stu-id="4bd51-115">Possible results include:</span></span>

- <span data-ttu-id="4bd51-116">**Aandacht vereist** (rood): Paginagewicht groter dan 500 KB</span><span class="sxs-lookup"><span data-stu-id="4bd51-116">**Attention required** (red): Page weight exceeds 500KB</span></span>
- <span data-ttu-id="4bd51-117">**Geen actie vereist** (groen): Paginagewicht is minder dan 500 KB</span><span class="sxs-lookup"><span data-stu-id="4bd51-117">**No action required** (green): Page weight is under 500KB</span></span>

<span data-ttu-id="4bd51-118">Als het  **paginagewicht onder 500 KB** wordt weergegeven in de sectie Aandacht vereist, kunt u op het resultaat klikken voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="4bd51-118">If the **Page weight under 500KB** result appears in the **Attention required** section, you can click the result for details.</span></span>

![Aanvragen voor SharePoint-resultaten](../media/modern-portal-optimization/pagediag-page-weight.png)

## <a name="remediate-page-weight-issues"></a><span data-ttu-id="4bd51-120">Problemen met het gewicht van pagina's oplossen</span><span class="sxs-lookup"><span data-stu-id="4bd51-120">Remediate page weight issues</span></span>

<span data-ttu-id="4bd51-121">Als het paginagewicht meer dan 500 KB bedraagt, kunt u de totale laadtijd van pagina's verbeteren door het aantal webonderdelen te verminderen en de pagina-inhoud in de juiste mate te beperken.</span><span class="sxs-lookup"><span data-stu-id="4bd51-121">If page weight exceeds 500KB, you can improve overall page load time by reducing the number of web parts and limiting page content to an appropriate degree.</span></span>

<span data-ttu-id="4bd51-122">Algemene richtlijnen voor het verminderen van het paginagewicht zijn:</span><span class="sxs-lookup"><span data-stu-id="4bd51-122">General guidance for reducing page weight includes:</span></span>

- <span data-ttu-id="4bd51-123">Beperk de pagina-inhoud tot een redelijk bedrag en gebruik meerdere pagina's voor gerelateerde inhoud.</span><span class="sxs-lookup"><span data-stu-id="4bd51-123">Limit the page content to a reasonable amount and use multiple pages for related content.</span></span>
- <span data-ttu-id="4bd51-124">Minimaliseer het gebruik van webonderdelen met grote eigenschappentassen.</span><span class="sxs-lookup"><span data-stu-id="4bd51-124">Minimize the use of web parts that have large property bags.</span></span>
- <span data-ttu-id="4bd51-125">Gebruik indien mogelijk niet-interactieve rollupweergaven.</span><span class="sxs-lookup"><span data-stu-id="4bd51-125">Use non-interactive rollup views when possible.</span></span>
- <span data-ttu-id="4bd51-126">Optimaliseer de grootte van afbeeldingen door afbeeldingen op de juiste manier te formaatken, gecomprimeerde afbeeldingsindelingen te gebruiken en ervoor te zorgen dat ze worden gedownload van een CDN.</span><span class="sxs-lookup"><span data-stu-id="4bd51-126">Optimize image sizes by sizing images appropriately, using compressed image formats and ensuring that they are downloaded from a CDN.</span></span>

<span data-ttu-id="4bd51-127">In het volgende artikel vindt u aanvullende richtlijnen voor het beperken van het paginagewicht:</span><span class="sxs-lookup"><span data-stu-id="4bd51-127">You can find additional guidance for limiting page weight in the following article:</span></span>

- [<span data-ttu-id="4bd51-128">Paginaprestaties optimaliseren in SharePoint</span><span class="sxs-lookup"><span data-stu-id="4bd51-128">Optimize page performance in SharePoint</span></span>](/sharepoint/dev/general-development/optimize-page-performance-in-sharepoint)

<span data-ttu-id="4bd51-129">Voordat u paginaherzieningen maakt om prestatieproblemen op te lossen, noteert u de laadtijd van de pagina in de analyseresultaten.</span><span class="sxs-lookup"><span data-stu-id="4bd51-129">Before you make page revisions to remediate performance issues, make a note of the page load time in the analysis results.</span></span> <span data-ttu-id="4bd51-130">Voer het hulpprogramma na de revisie opnieuw uit om te zien of het nieuwe resultaat binnen de basislijnstandaard valt en controleer de laadtijd van de nieuwe pagina om te zien of er een verbetering is.</span><span class="sxs-lookup"><span data-stu-id="4bd51-130">Run the tool again after your revision to see if the new result is within the baseline standard, and check the new page load time to see if there was an improvement.</span></span>

![De laadtijd van pagina's](../media/modern-portal-optimization/pagediag-page-load-time.png)

>[!NOTE]
><span data-ttu-id="4bd51-132">De laadtijd van pagina's kan variëren op basis van verschillende factoren, zoals de netwerkbelasting, de tijd van de dag en andere tijdelijke omstandigheden.</span><span class="sxs-lookup"><span data-stu-id="4bd51-132">Page load time can vary based on a variety of factors such as network load, time of day, and other transient conditions.</span></span> <span data-ttu-id="4bd51-133">U moet de laadtijd van pagina's een paar keer voor en na het aanbrengen van wijzigingen testen, zodat u de resultaten kunt gemiddelden.</span><span class="sxs-lookup"><span data-stu-id="4bd51-133">You should test page load time a few times before and after making changes to help you average the results.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4bd51-134">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="4bd51-134">Related topics</span></span>

[<span data-ttu-id="4bd51-135">Prestaties van SharePoint Online afstemmen</span><span class="sxs-lookup"><span data-stu-id="4bd51-135">Tune SharePoint Online performance</span></span>](tune-sharepoint-online-performance.md)

[<span data-ttu-id="4bd51-136">Prestaties van Office 365 afstemmen</span><span class="sxs-lookup"><span data-stu-id="4bd51-136">Tune Office 365 performance</span></span>](tune-microsoft-365-performance.md)

[<span data-ttu-id="4bd51-137">Prestaties in de moderne SharePoint-ervaring</span><span class="sxs-lookup"><span data-stu-id="4bd51-137">Performance in the modern SharePoint experience</span></span>](/sharepoint/modern-experience-performance)

[<span data-ttu-id="4bd51-138">Netwerken voor contentlevering</span><span class="sxs-lookup"><span data-stu-id="4bd51-138">Content delivery networks</span></span>](content-delivery-networks.md)

[<span data-ttu-id="4bd51-139">Het Office 365 Content Delivery Network (CDN) gebruiken met SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="4bd51-139">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)