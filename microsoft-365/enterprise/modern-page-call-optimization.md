---
title: Pagina-oproepen optimaliseren in de pagina's modern en Classic Publishing site in SharePoint Online
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
description: Meer informatie over het optimaliseren van de modern en de klassieke publicatiesite van pagina's in SharePoint Online door het aantal oproepen naar SharePoint Online-service-eindpunten te beperken.
ms.openlocfilehash: b3c41dfe308f1546887f28cf0e8fbe9ab4dc2761
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689537"
---
# <a name="optimize-page-calls-in-sharepoint-online-modern-and-classic-publishing-site-pages"></a><span data-ttu-id="30a94-103">Pagina-oproepen optimaliseren in de pagina's modern en Classic Publishing site in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="30a94-103">Optimize page calls in SharePoint Online modern and classic publishing site pages</span></span>

<span data-ttu-id="30a94-104">De sites van SharePoint Online modern en Classic bevatten koppelingen waarmee u SharePoint-functies en-Cdn's kunt laden.</span><span class="sxs-lookup"><span data-stu-id="30a94-104">Both SharePoint Online modern and classic publishing sites contain links that load data from (or make calls to) SharePoint features and CDNs.</span></span> <span data-ttu-id="30a94-105">Hoe meer oproepen worden gedaan door een pagina, hoe langer de pagina wordt geladen.</span><span class="sxs-lookup"><span data-stu-id="30a94-105">The more calls made by a page, the longer the page takes to load.</span></span> <span data-ttu-id="30a94-106">Dit is een bekend merk wanneer een **eindgebruiker latentie heeft waargenomen** of **EUPL**.</span><span class="sxs-lookup"><span data-stu-id="30a94-106">This is known as **end user perceived latency** or **EUPL**.</span></span>

<span data-ttu-id="30a94-107">In dit artikel vindt u informatie over hoe u het aantal en de gevolgen van oproepen voor externe eindpunten op de moderne en klassieke pagina's voor publicerende sites bepaalt</span><span class="sxs-lookup"><span data-stu-id="30a94-107">This article will help you understand how to determine the number and impact of calls to external endpoints from your modern and classic publishing site pages and how to limit their effect on end user perceived latency.</span></span>

>[!NOTE]
><span data-ttu-id="30a94-108">Zie [prestaties in de moderne SharePoint-ervaring](https://docs.microsoft.com/sharepoint/modern-experience-performance)voor meer informatie over prestaties in moderne portals voor SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="30a94-108">For more information about performance in SharePoint Online modern portals, see [Performance in the modern SharePoint experience](https://docs.microsoft.com/sharepoint/modern-experience-performance).</span></span>

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-page-calls"></a><span data-ttu-id="30a94-109">Het hulpprogramma pagina diagnose voor SharePoint gebruiken om pagina oproepen te analyseren</span><span class="sxs-lookup"><span data-stu-id="30a94-109">Use the Page Diagnostics for SharePoint tool to analyze page calls</span></span>

<span data-ttu-id="30a94-110">Het hulpprogramma pagina diagnose voor SharePoint is een browser extensie voor de nieuwe Microsoft Edge- https://www.microsoft.com/edge) en Chrome-browsers die zowel SharePoint Online modern portal als de klassieke publicatiesite pagina's analyseren.</span><span class="sxs-lookup"><span data-stu-id="30a94-110">The Page Diagnostics for SharePoint tool is a browser extension for the new Microsoft Edge (https://www.microsoft.com/edge) and Chrome browsers that analyzes both SharePoint Online modern portal and classic publishing site pages.</span></span> <span data-ttu-id="30a94-111">Het hulpmiddel biedt een rapport voor elke geanalyseerde pagina op basis van een gedefinieerde set prestatiecriteria.</span><span class="sxs-lookup"><span data-stu-id="30a94-111">The tool provides a report for each analyzed page showing how the page performs against a defined set of performance criteria.</span></span> <span data-ttu-id="30a94-112">Ga voor meer informatie over het hulpprogramma pagina diagnose voor SharePoint naar [het hulpprogramma pagina diagnose voor SharePoint Online](page-diagnostics-for-spo.md).</span><span class="sxs-lookup"><span data-stu-id="30a94-112">To install and learn about the Page Diagnostics for SharePoint tool, visit [Use the Page Diagnostics tool for SharePoint Online](page-diagnostics-for-spo.md).</span></span>

>[!NOTE]
><span data-ttu-id="30a94-113">Het hulpmiddel voor het automatisch toevoegen van pagina's werkt alleen voor SharePoint Online en kan niet worden gebruikt op een SharePoint-systeempagina.</span><span class="sxs-lookup"><span data-stu-id="30a94-113">The Page Diagnostics tool only works for SharePoint Online, and cannot be used on a SharePoint system page.</span></span>

<span data-ttu-id="30a94-114">Wanneer u een SharePoint-sitepagina wilt analyseren met het hulpprogramma pagina diagnose voor SharePoint, kunt u in het deelvenster _diagnostische tests_ informatie vinden over externe oproepen in het resultaat van de **verzoeken tot SharePoint** .</span><span class="sxs-lookup"><span data-stu-id="30a94-114">When you analyze a SharePoint site page with the Page Diagnostics for SharePoint tool, you can see information about external calls in the **Requests to SharePoint** result in the _Diagnostic tests_ pane.</span></span> <span data-ttu-id="30a94-115">De lijn wordt in groen weergegeven als de sitepagina minder is dan het basislijn aantal gesprekken, en rood als de pagina het basislijn nummer overschrijdt.</span><span class="sxs-lookup"><span data-stu-id="30a94-115">The line will appear in green if the site page contains fewer than the baseline number of calls, and red if the page exceeds the baseline number.</span></span> <span data-ttu-id="30a94-116">Het nummer van de basislijn is verschillend voor moderne pagina's en de klassieke pagina's, aangezien de klassieke sitepagina's gebruikmaken van http 1.1 en moderne pagina's gebruikmaken van HTTP 2.0:</span><span class="sxs-lookup"><span data-stu-id="30a94-116">The baseline number is different for modern and classic pages because classic site pages use HTTP1.1 and modern pages use HTTP2.0:</span></span>

- <span data-ttu-id="30a94-117">Pagina's op een moderne site mogen niet meer dan **25** oproepen bevatten</span><span class="sxs-lookup"><span data-stu-id="30a94-117">Modern site pages should contain no more than **25** calls</span></span>
- <span data-ttu-id="30a94-118">Klassieke publicatiepagina's mogen niet meer dan **zes** oproepen bevatten</span><span class="sxs-lookup"><span data-stu-id="30a94-118">Classic publishing pages should contain no more than **6** calls</span></span>

<span data-ttu-id="30a94-119">Mogelijke resultaten zijn onder meer:</span><span class="sxs-lookup"><span data-stu-id="30a94-119">Possible results include:</span></span>

- <span data-ttu-id="30a94-120">**Aandacht vereist** (rood): de pagina overschrijdt het basislijn aantal oproepen</span><span class="sxs-lookup"><span data-stu-id="30a94-120">**Attention required** (red): The page exceeds the baseline number of calls</span></span>
- <span data-ttu-id="30a94-121">**Geen actie vereist** (groen): de pagina bevat minder dan het basislijn aantal oproepen</span><span class="sxs-lookup"><span data-stu-id="30a94-121">**No action required** (green): The page contains fewer than the baseline number of calls</span></span>

<span data-ttu-id="30a94-122">Als het resultaat van de **verzoeken tot SharePoint** wordt weergegeven in de sectie **aandacht vereist** , kunt u op het resultaat klikken voor details, waaronder het totale aantal oproepen op de pagina en een lijst met de url's.</span><span class="sxs-lookup"><span data-stu-id="30a94-122">If the **Requests to SharePoint** result appears in the **Attention required** section, you can click the result for details, including the total number of calls on the page and a list of the URLs.</span></span>

![Aanvragen voor resultaten van SharePoint](../media/modern-portal-optimization/pagediag-requests.png)

## <a name="remediate-performance-issues-related-to-too-many-calls-on-a-page"></a><span data-ttu-id="30a94-124">Prestatieproblemen met betrekking tot een groot aantal oproepen herstellen op een pagina</span><span class="sxs-lookup"><span data-stu-id="30a94-124">Remediate performance issues related to too many calls on a page</span></span>

<span data-ttu-id="30a94-125">Als een pagina te veel oproepen bevat, kunt u deze gebruiken in de lijst met Url's in de resultaten van de **SharePoint-** resultaten om te bepalen of er herhaaldelijke oproepen plaatsvinden, oproepen die moeten worden opgenomen of gesprekken die gegevens bevatten die moeten worden opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="30a94-125">If a page contains too many calls, you can use the list of URLs in the **Requests to Sharepoint** results to determine whether there are any repeated calls, calls that should be batched, or calls that return data that should be cached.</span></span>

<span data-ttu-id="30a94-126">Met **reste gesprekken** kunt u de prestaties van de kosten verminderen.</span><span class="sxs-lookup"><span data-stu-id="30a94-126">**Batching REST calls** can help to reduce performance overhead.</span></span> <span data-ttu-id="30a94-127">Zie voor meer informatie over het uitvoeren van API-oproepen batch [aanvragen indienen met de rest-api's](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/make-batch-requests-with-the-rest-apis).</span><span class="sxs-lookup"><span data-stu-id="30a94-127">For more information about API call batching, see [Make batch requests with the REST APIs](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/make-batch-requests-with-the-rest-apis).</span></span>

<span data-ttu-id="30a94-128">**Met behulp van een cache** voor het opslaan van de resultaten van een API-oproep kunt u de prestaties van een verzoek verbeteren door de client gebruik te maken van de in de cache geplaatste gegevens in plaats van een extra oproep te voeren voor elke volgende pagina belasting.</span><span class="sxs-lookup"><span data-stu-id="30a94-128">**Using a cache** to store the results of an API call can improve the performance of a warm request by allowing the client to use the cached data instead of making an additional call for each subsequent page load.</span></span> <span data-ttu-id="30a94-129">U kunt op verschillende manieren deze oplossing volgen, afhankelijk van de zakelijke eis.</span><span class="sxs-lookup"><span data-stu-id="30a94-129">There are multiple ways to approach this solution depending on the business requirement.</span></span> <span data-ttu-id="30a94-130">Meestal als de gegevens hetzelfde zijn voor alle gebruikers, is het gebruik van een cacheservice voor middelste lagen, zoals [ _Azure redis_ cache](https://azure.microsoft.com/services/cache/) , een uitstekende optie om het API-verkeer van een site aanzienlijk te reduceren, aangezien de gebruikers de gegevens van de cacheservice aanvragen via de cacheservice, in plaats van rechtstreeks vanuit SPO.</span><span class="sxs-lookup"><span data-stu-id="30a94-130">Typically if the data will be the same for all users, using a middle-tier caching service like [_Azure Redis_ cache](https://azure.microsoft.com/services/cache/) is a great option to significantly reduce API traffic against a site, as the users would request the data from the caching service instead of directly from SPO.</span></span> <span data-ttu-id="30a94-131">De enige SPOs die nodig zijn, zijn de cache van de middelste laag vernieuwd.</span><span class="sxs-lookup"><span data-stu-id="30a94-131">The only SPO calls needed would be to refresh the middle-tier's cache.</span></span> <span data-ttu-id="30a94-132">Als de gegevens voor afzonderlijke gebruikers schommelen, kunt u het beste een cache voor de clientcache, zoals LocalStorage of zelfs een cookie, implementeren.</span><span class="sxs-lookup"><span data-stu-id="30a94-132">If the data will fluctuate on an individual user basis, it may be best to implement a client side cache, like LocalStorage or even a Cookie.</span></span> <span data-ttu-id="30a94-133">Dit beperkt de oproepen van de oproep en verlaagt de volgende aanvragen van dezelfde gebruiker voor de cacheduur, maar is minder efficiënt dan een specifieke cacheservice.</span><span class="sxs-lookup"><span data-stu-id="30a94-133">This will still reduce call volumes by eliminating subsequent requests made by the same user for the cache duration, but will be less efficient than a dedicated caching service.</span></span> <span data-ttu-id="30a94-134">Met PnP kunt u LocalStorage gebruiken met een beetje extra ontwikkeling vereist.</span><span class="sxs-lookup"><span data-stu-id="30a94-134">PnP allows you to use LocalStorage with little additional development required.</span></span>

<span data-ttu-id="30a94-135">Voordat u de revisies van pagina's aanbrengt om prestatieproblemen te verhelpen, kunt u de laadtijd van de pagina in de analyseresultaten noteren.</span><span class="sxs-lookup"><span data-stu-id="30a94-135">Before you make page revisions to remediate performance issues, make a note of the page load time in the analysis results.</span></span> <span data-ttu-id="30a94-136">Voer het hulpprogramma opnieuw uit na de wijziging om te zien of het nieuwe resultaat binnen de basislijn standaard valt en de nieuwe laadtijd voor pagina's te controleren om te zien of er een verbetering was.</span><span class="sxs-lookup"><span data-stu-id="30a94-136">Run the tool again after your revision to see if the new result is within the baseline standard, and check the new page load time to see if there was an improvement.</span></span>

![Resultaten van laadtijden voor pagina's](../media/modern-portal-optimization/pagediag-page-load-time.png)

>[!NOTE]
><span data-ttu-id="30a94-138">De laadtijd van de pagina kan variëren, afhankelijk van diverse factoren, zoals netwerkbelasting, tijdstip van de dag en andere tijdelijke voorwaarden.</span><span class="sxs-lookup"><span data-stu-id="30a94-138">Page load time can vary based on a variety of factors such as network load, time of day, and other transient conditions.</span></span> <span data-ttu-id="30a94-139">U moet de laadtijd voor pagina's enkele keren vóór en na het aanbrengen van wijzigingen aanbrengen om de resultaten te berekenen.</span><span class="sxs-lookup"><span data-stu-id="30a94-139">You should test page load time a few times before and after making changes to help you average the results.</span></span>

## <a name="related-topics"></a><span data-ttu-id="30a94-140">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="30a94-140">Related topics</span></span>

[<span data-ttu-id="30a94-141">Prestaties van SharePoint Online afstemmen</span><span class="sxs-lookup"><span data-stu-id="30a94-141">Tune SharePoint Online performance</span></span>](tune-sharepoint-online-performance.md)

[<span data-ttu-id="30a94-142">Prestaties van Office 365 afstemmen</span><span class="sxs-lookup"><span data-stu-id="30a94-142">Tune Office 365 performance</span></span>](tune-microsoft-365-performance.md)

[<span data-ttu-id="30a94-143">Prestaties in de moderne SharePoint-ervaring</span><span class="sxs-lookup"><span data-stu-id="30a94-143">Performance in the modern SharePoint experience</span></span>](https://docs.microsoft.com/sharepoint/modern-experience-performance)

[<span data-ttu-id="30a94-144">Netwerken voor content levering</span><span class="sxs-lookup"><span data-stu-id="30a94-144">Content delivery networks</span></span>](content-delivery-networks.md)

[<span data-ttu-id="30a94-145">Het Office 365 Content Delivery Network (CDN) gebruiken met SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="30a94-145">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)
