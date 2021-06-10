---
title: Paginagesprekken optimaliseren in SharePoint moderne en klassieke publicatiesitepagina's online
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
description: Meer informatie over het optimaliseren van moderne en klassieke publicatiesitepagina's in SharePoint Online door het aantal oproepen te beperken tot SharePoint Online service-eindpunten.
ms.openlocfilehash: cab0f6a020bd1148a0e852b5a393a6ad907f9771
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921616"
---
# <a name="optimize-page-calls-in-sharepoint-online-modern-and-classic-publishing-site-pages"></a><span data-ttu-id="d23f5-103">Paginagesprekken optimaliseren in SharePoint moderne en klassieke publicatiesitepagina's online</span><span class="sxs-lookup"><span data-stu-id="d23f5-103">Optimize page calls in SharePoint Online modern and classic publishing site pages</span></span>

<span data-ttu-id="d23f5-104">Zowel SharePoint moderne als klassieke publicatiesites van Online bevatten koppelingen die gegevens laden van (of bellen naar) SharePoint en CDN's.</span><span class="sxs-lookup"><span data-stu-id="d23f5-104">Both SharePoint Online modern and classic publishing sites contain links that load data from (or make calls to) SharePoint features and CDNs.</span></span> <span data-ttu-id="d23f5-105">Hoe meer oproepen door een pagina worden gedaan, hoe langer de pagina duurt om te laden.</span><span class="sxs-lookup"><span data-stu-id="d23f5-105">The more calls made by a page, the longer the page takes to load.</span></span> <span data-ttu-id="d23f5-106">Dit staat bekend als **de waargenomen latentie van eindgebruikers of** **EUPL.**</span><span class="sxs-lookup"><span data-stu-id="d23f5-106">This is known as **end user perceived latency** or **EUPL**.</span></span>

<span data-ttu-id="d23f5-107">In dit artikel wordt beschreven hoe u het aantal en de impact van oproepen naar externe eindpunten kunt bepalen vanaf uw moderne en klassieke publicerende sitepagina's en hoe u het effect ervan op de waargenomen latentie van de eindgebruiker kunt beperken.</span><span class="sxs-lookup"><span data-stu-id="d23f5-107">This article will help you understand how to determine the number and impact of calls to external endpoints from your modern and classic publishing site pages and how to limit their effect on end user perceived latency.</span></span>

>[!NOTE]
><span data-ttu-id="d23f5-108">Zie Prestaties in de moderne SharePoint voor meer informatie over prestaties in SharePoint moderne [onlineportalen.](/sharepoint/modern-experience-performance)</span><span class="sxs-lookup"><span data-stu-id="d23f5-108">For more information about performance in SharePoint Online modern portals, see [Performance in the modern SharePoint experience](/sharepoint/modern-experience-performance).</span></span>

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-page-calls"></a><span data-ttu-id="d23f5-109">Het hulpprogramma Paginadiagnose SharePoint gebruiken om paginagesprekken te analyseren</span><span class="sxs-lookup"><span data-stu-id="d23f5-109">Use the Page Diagnostics for SharePoint tool to analyze page calls</span></span>

<span data-ttu-id="d23f5-110">Het hulpprogramma Paginadiagnose voor SharePoint is een browserextensie voor de nieuwe Microsoft Edge ( en Chrome-browsers die zowel SharePoint Moderne portal online als klassieke https://www.microsoft.com/edge) publicerende sitepagina's analyseren.</span><span class="sxs-lookup"><span data-stu-id="d23f5-110">The Page Diagnostics for SharePoint tool is a browser extension for the new Microsoft Edge (https://www.microsoft.com/edge) and Chrome browsers that analyzes both SharePoint Online modern portal and classic publishing site pages.</span></span> <span data-ttu-id="d23f5-111">Het hulpprogramma bevat een rapport voor elke geanalyseerde pagina die laat zien hoe de pagina presteert op basis van een gedefinieerde set prestatiecriteria.</span><span class="sxs-lookup"><span data-stu-id="d23f5-111">The tool provides a report for each analyzed page showing how the page performs against a defined set of performance criteria.</span></span> <span data-ttu-id="d23f5-112">Als u het hulpprogramma Paginadiagnose voor SharePoint wilt installeren en meer wilt weten, gaat u naar Het hulpprogramma [Paginadiagnose gebruiken](page-diagnostics-for-spo.md)voor SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="d23f5-112">To install and learn about the Page Diagnostics for SharePoint tool, visit [Use the Page Diagnostics tool for SharePoint Online](page-diagnostics-for-spo.md).</span></span>

>[!NOTE]
><span data-ttu-id="d23f5-113">Het hulpprogramma Paginadiagnose werkt alleen SharePoint Online en kan niet worden gebruikt op een SharePoint systeempagina.</span><span class="sxs-lookup"><span data-stu-id="d23f5-113">The Page Diagnostics tool only works for SharePoint Online, and cannot be used on a SharePoint system page.</span></span>

<span data-ttu-id="d23f5-114">Wanneer u een SharePoint sitepagina analyseert met het hulpprogramma Paginadiagnose voor SharePoint, ziet u informatie over externe oproepen in het deelvenster Aanvragen SharePoint resultaten in het deelvenster **Diagnostische** _tests._</span><span class="sxs-lookup"><span data-stu-id="d23f5-114">When you analyze a SharePoint site page with the Page Diagnostics for SharePoint tool, you can see information about external calls in the **Requests to SharePoint** result in the _Diagnostic tests_ pane.</span></span> <span data-ttu-id="d23f5-115">De regel wordt groen weergegeven als de sitepagina minder dan het basislijnaantal oproepen bevat en rood als de pagina het basislijnnummer overschrijdt.</span><span class="sxs-lookup"><span data-stu-id="d23f5-115">The line will appear in green if the site page contains fewer than the baseline number of calls, and red if the page exceeds the baseline number.</span></span> <span data-ttu-id="d23f5-116">Het basislijnnummer is anders voor moderne en klassieke pagina's omdat klassieke sitepagina's HTTP1.1 gebruiken en moderne pagina's HTTP2.0 gebruiken:</span><span class="sxs-lookup"><span data-stu-id="d23f5-116">The baseline number is different for modern and classic pages because classic site pages use HTTP1.1 and modern pages use HTTP2.0:</span></span>

- <span data-ttu-id="d23f5-117">Moderne sitepagina's mogen niet meer dan **25 oproepen** bevatten</span><span class="sxs-lookup"><span data-stu-id="d23f5-117">Modern site pages should contain no more than **25** calls</span></span>
- <span data-ttu-id="d23f5-118">Klassieke publicatiepagina's mogen niet meer dan **6 oproepen** bevatten</span><span class="sxs-lookup"><span data-stu-id="d23f5-118">Classic publishing pages should contain no more than **6** calls</span></span>

<span data-ttu-id="d23f5-119">Mogelijke resultaten zijn:</span><span class="sxs-lookup"><span data-stu-id="d23f5-119">Possible results include:</span></span>

- <span data-ttu-id="d23f5-120">**Aandacht vereist** (rood): De pagina overschrijdt het aantal oproepen volgens de basislijn</span><span class="sxs-lookup"><span data-stu-id="d23f5-120">**Attention required** (red): The page exceeds the baseline number of calls</span></span>
- <span data-ttu-id="d23f5-121">**Geen actie vereist** (groen): De pagina bevat minder dan het basislijnaantal oproepen</span><span class="sxs-lookup"><span data-stu-id="d23f5-121">**No action required** (green): The page contains fewer than the baseline number of calls</span></span>

<span data-ttu-id="d23f5-122">Als het resultaat **Aanvragen SharePoint** wordt weergegeven  in de sectie Aandacht vereist, kunt u op het resultaat klikken voor meer informatie, inclusief het totale aantal oproepen op de pagina en een lijst met URL's.</span><span class="sxs-lookup"><span data-stu-id="d23f5-122">If the **Requests to SharePoint** result appears in the **Attention required** section, you can click the result for details, including the total number of calls on the page and a list of the URLs.</span></span>

![Aanvragen om SharePoint resultaten](../media/modern-portal-optimization/pagediag-requests.png)

## <a name="remediate-performance-issues-related-to-too-many-calls-on-a-page"></a><span data-ttu-id="d23f5-124">Prestatieproblemen met te veel oproepen op een pagina oplossen</span><span class="sxs-lookup"><span data-stu-id="d23f5-124">Remediate performance issues related to too many calls on a page</span></span>

<span data-ttu-id="d23f5-125">Als een pagina te veel oproepen bevat, kunt u de lijst met URL's in de resultaten van Aanvragen voor **Sharepoint** gebruiken om te bepalen of er herhaalde oproepen zijn, oproepen die moeten worden gebatcheerd of oproepen die gegevens retourneren die in de cache moeten worden opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="d23f5-125">If a page contains too many calls, you can use the list of URLs in the **Requests to Sharepoint** results to determine whether there are any repeated calls, calls that should be batched, or calls that return data that should be cached.</span></span>

<span data-ttu-id="d23f5-126">**Batching REST calls can** help to reduce performance overhead.</span><span class="sxs-lookup"><span data-stu-id="d23f5-126">**Batching REST calls** can help to reduce performance overhead.</span></span> <span data-ttu-id="d23f5-127">Zie Batchaanvragen maken met de [REST-API's](/sharepoint/dev/sp-add-ins/make-batch-requests-with-the-rest-apis)voor meer informatie over api-oproepbatching.</span><span class="sxs-lookup"><span data-stu-id="d23f5-127">For more information about API call batching, see [Make batch requests with the REST APIs](/sharepoint/dev/sp-add-ins/make-batch-requests-with-the-rest-apis).</span></span>

<span data-ttu-id="d23f5-128">**Als** u een cache gebruikt om de resultaten van een API-oproep op te slaan, kunt u de prestaties van een warm verzoek verbeteren door de client de gegevens in de cache te laten gebruiken in plaats van extra te bellen voor elke volgende paginabelasting.</span><span class="sxs-lookup"><span data-stu-id="d23f5-128">**Using a cache** to store the results of an API call can improve the performance of a warm request by allowing the client to use the cached data instead of making an additional call for each subsequent page load.</span></span> <span data-ttu-id="d23f5-129">Er zijn verschillende manieren om deze oplossing te benaderen, afhankelijk van de bedrijfsvereisten.</span><span class="sxs-lookup"><span data-stu-id="d23f5-129">There are multiple ways to approach this solution depending on the business requirement.</span></span> <span data-ttu-id="d23f5-130">Als de gegevens voor alle gebruikers hetzelfde zijn, is het gebruik van een cachingservice met een middenlaag, zoals [ _Azure Redis-cache,_](https://azure.microsoft.com/services/cache/) een goede optie om het API-verkeer ten opzichte van een site aanzienlijk te verminderen, omdat de gebruikers de gegevens bij de caching-service zouden aanvragen in plaats van rechtstreeks bij SPO.</span><span class="sxs-lookup"><span data-stu-id="d23f5-130">Typically if the data will be the same for all users, using a middle-tier caching service like [_Azure Redis_ cache](https://azure.microsoft.com/services/cache/) is a great option to significantly reduce API traffic against a site, as the users would request the data from the caching service instead of directly from SPO.</span></span> <span data-ttu-id="d23f5-131">De enige SPO-oproepen die nodig zijn, zijn het vernieuwen van de cache van de middelste laag.</span><span class="sxs-lookup"><span data-stu-id="d23f5-131">The only SPO calls needed would be to refresh the middle-tier's cache.</span></span> <span data-ttu-id="d23f5-132">Als de gegevens per gebruiker fluctueren, kunt u het beste een cache aan de clientzijde implementeren, zoals LocalStorage of zelfs een Cookie.</span><span class="sxs-lookup"><span data-stu-id="d23f5-132">If the data will fluctuate on an individual user basis, it may be best to implement a client side cache, like LocalStorage or even a Cookie.</span></span> <span data-ttu-id="d23f5-133">Hierdoor worden de gespreksvolumes nog steeds beperkt doordat de volgende aanvragen van dezelfde gebruiker voor de duur van de cache worden verwijderd, maar minder efficiënt zijn dan een speciale caching-service.</span><span class="sxs-lookup"><span data-stu-id="d23f5-133">This will still reduce call volumes by eliminating subsequent requests made by the same user for the cache duration, but will be less efficient than a dedicated caching service.</span></span> <span data-ttu-id="d23f5-134">Met PnP kunt u LocalStorage gebruiken met weinig extra ontwikkeling vereist.</span><span class="sxs-lookup"><span data-stu-id="d23f5-134">PnP allows you to use LocalStorage with little additional development required.</span></span>

<span data-ttu-id="d23f5-135">Voordat u paginaherzieningen maakt om prestatieproblemen op te lossen, noteert u de laadtijd van de pagina in de analyseresultaten.</span><span class="sxs-lookup"><span data-stu-id="d23f5-135">Before you make page revisions to remediate performance issues, make a note of the page load time in the analysis results.</span></span> <span data-ttu-id="d23f5-136">Voer het hulpprogramma na de revisie opnieuw uit om te zien of het nieuwe resultaat binnen de basislijnstandaard valt en controleer de laadtijd van de nieuwe pagina om te zien of er een verbetering is.</span><span class="sxs-lookup"><span data-stu-id="d23f5-136">Run the tool again after your revision to see if the new result is within the baseline standard, and check the new page load time to see if there was an improvement.</span></span>

![De laadtijd van pagina's](../media/modern-portal-optimization/pagediag-page-load-time.png)

>[!NOTE]
><span data-ttu-id="d23f5-138">De laadtijd van pagina's kan variëren op basis van verschillende factoren, zoals de netwerkbelasting, de tijd van de dag en andere tijdelijke omstandigheden.</span><span class="sxs-lookup"><span data-stu-id="d23f5-138">Page load time can vary based on a variety of factors such as network load, time of day, and other transient conditions.</span></span> <span data-ttu-id="d23f5-139">U moet de laadtijd van pagina's een paar keer voor en na het aanbrengen van wijzigingen testen, zodat u de resultaten kunt gemiddelden.</span><span class="sxs-lookup"><span data-stu-id="d23f5-139">You should test page load time a few times before and after making changes to help you average the results.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d23f5-140">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="d23f5-140">Related topics</span></span>

[<span data-ttu-id="d23f5-141">Prestaties SharePoint online afstemmen</span><span class="sxs-lookup"><span data-stu-id="d23f5-141">Tune SharePoint Online performance</span></span>](tune-sharepoint-online-performance.md)

[<span data-ttu-id="d23f5-142">Prestaties Office 365 afstemmen</span><span class="sxs-lookup"><span data-stu-id="d23f5-142">Tune Office 365 performance</span></span>](tune-microsoft-365-performance.md)

[<span data-ttu-id="d23f5-143">Prestaties in de moderne SharePoint ervaring</span><span class="sxs-lookup"><span data-stu-id="d23f5-143">Performance in the modern SharePoint experience</span></span>](/sharepoint/modern-experience-performance)

[<span data-ttu-id="d23f5-144">Netwerken voor contentlevering</span><span class="sxs-lookup"><span data-stu-id="d23f5-144">Content delivery networks</span></span>](content-delivery-networks.md)

[<span data-ttu-id="d23f5-145">De Office 365 Content Delivery Network (CDN) gebruiken met SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="d23f5-145">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)