---
title: Microsoft 365 Network Insights (preview)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365 Network Insights (preview)
ms.openlocfilehash: ca665f4e492b071e5a387ffde0efae8336bd96bc
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245778"
---
# <a name="microsoft-365-network-insights-preview"></a><span data-ttu-id="e0094-103">Microsoft 365 Network Insights (preview)</span><span class="sxs-lookup"><span data-stu-id="e0094-103">Microsoft 365 Network Insights (preview)</span></span>

<span data-ttu-id="e0094-104">**Netwerkinzichten** zijn prestatiemetrische gegevens die zijn verzameld van uw Microsoft 365 tenant en die alleen kunnen worden bekeken door beheerders in uw tenant.</span><span class="sxs-lookup"><span data-stu-id="e0094-104">**Network insights** are performance metrics collected from your Microsoft 365 tenant, and available to view only by administrative users in your tenant.</span></span> <span data-ttu-id="e0094-105">Inzichten worden weergegeven in het Microsoft 365 beheercentrum op <https://portal.microsoft.com/adminportal/home#/networkperformance> .</span><span class="sxs-lookup"><span data-stu-id="e0094-105">Insights are displayed in the Microsoft 365 Admin Center at <https://portal.microsoft.com/adminportal/home#/networkperformance>.</span></span>

<span data-ttu-id="e0094-106">Inzichten zijn bedoeld om te helpen bij het ontwerpen van netwerkperimeters voor uw kantoorlocaties.</span><span class="sxs-lookup"><span data-stu-id="e0094-106">Insights are intended to help in designing network perimeters for your office locations.</span></span> <span data-ttu-id="e0094-107">Elk inzicht bevat live details over de prestatiekenmerken voor een specifiek veelvoorkomende probleem voor elke geografische locatie waar gebruikers toegang hebben tot uw tenant.</span><span class="sxs-lookup"><span data-stu-id="e0094-107">Each insight provides live details about the performance characteristics for a specific common issue for each geographic location where users are accessing your tenant.</span></span>

<span data-ttu-id="e0094-108">Er zijn zes specifieke netwerkinzichten die kunnen worden weergegeven voor elke kantoorlocatie:</span><span class="sxs-lookup"><span data-stu-id="e0094-108">There are six specific network insights that may be shown for each office location:</span></span>

- [<span data-ttu-id="e0094-109">Backhauled network egress</span><span class="sxs-lookup"><span data-stu-id="e0094-109">Backhauled network egress</span></span>](#backhauled-network-egress)
- [<span data-ttu-id="e0094-110">Netwerkbemiddelingsapparaat</span><span class="sxs-lookup"><span data-stu-id="e0094-110">Network intermediary device</span></span>](#network-intermediary-device)
- [<span data-ttu-id="e0094-111">Betere prestaties gedetecteerd voor klanten in uw buurt</span><span class="sxs-lookup"><span data-stu-id="e0094-111">Better performance detected for customers near you</span></span>](#better-performance-detected-for-customers-near-you)
- [<span data-ttu-id="e0094-112">Gebruik van een niet-optimale Exchange Online servicedeuren</span><span class="sxs-lookup"><span data-stu-id="e0094-112">Use of a non-optimal Exchange Online service front door</span></span>](#use-of-a-non-optimal-exchange-online-service-front-door)
- [<span data-ttu-id="e0094-113">Gebruik van een niet-optimale SharePoint onlineservice voor de deur</span><span class="sxs-lookup"><span data-stu-id="e0094-113">Use of a non-optimal SharePoint Online service front door</span></span>](#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [<span data-ttu-id="e0094-114">Lage downloadsnelheid van SharePoint voor deur</span><span class="sxs-lookup"><span data-stu-id="e0094-114">Low download speed from SharePoint front door</span></span>](#low-download-speed-from-sharepoint-front-door)
- [<span data-ttu-id="e0094-115">China user optimal network egress</span><span class="sxs-lookup"><span data-stu-id="e0094-115">China user optimal network egress</span></span>](#china-user-optimal-network-egress)

<span data-ttu-id="e0094-116">Er zijn twee netwerkinzichten op tenantniveau die mogelijk worden weergegeven voor de tenant.</span><span class="sxs-lookup"><span data-stu-id="e0094-116">There are two tenant level network insights that may be shown for the tenant.</span></span> <span data-ttu-id="e0094-117">Deze worden ook weergegeven op de pagina's met productiviteitsscores:</span><span class="sxs-lookup"><span data-stu-id="e0094-117">These also appear in the productivity score pages:</span></span>

- [<span data-ttu-id="e0094-118">Exchange verbindingen die zijn beïnvloed door verbindingsproblemen</span><span class="sxs-lookup"><span data-stu-id="e0094-118">Exchange sampled connections impacted by connectivity issues</span></span>](#exchange-sampled-connections-impacted-by-connectivity-issues)
- [<span data-ttu-id="e0094-119">SharePoint verbindingen die zijn beïnvloed door verbindingsproblemen</span><span class="sxs-lookup"><span data-stu-id="e0094-119">SharePoint sampled connections impacted by connectivity issues</span></span>](#sharepoint-sampled-connections-impacted-by-connectivity-issues)

>[!IMPORTANT]
><span data-ttu-id="e0094-120">Netwerkinzichten, prestatieaanbevelingen en evaluaties in het Microsoft 365-beheercentrum hebben momenteel de preview-status en zijn alleen beschikbaar voor Microsoft 365-tenants die zijn geregistreerd voor het functievoorbeeldprogramma.</span><span class="sxs-lookup"><span data-stu-id="e0094-120">Network insights, performance recommendations and assessments in the Microsoft 365 Admin Center is currently in preview status, and is only available for Microsoft 365 tenants that have been enrolled in the feature preview program.</span></span>

## <a name="backhauled-network-egress"></a><span data-ttu-id="e0094-121">Backhauled network egress</span><span class="sxs-lookup"><span data-stu-id="e0094-121">Backhauled network egress</span></span>

<span data-ttu-id="e0094-122">Dit inzicht wordt weergegeven als de netwerkinzichtservice detecteert dat de afstand van een bepaalde gebruikerslocatie tot het netwerkuitje groter is dan 800 kilometer, wat aangeeft dat Microsoft 365-verkeer wordt teruggeplaatst naar een gemeenschappelijk internetrandapparaat of proxy.</span><span class="sxs-lookup"><span data-stu-id="e0094-122">This insight will be displayed if the network insights service detects that the distance from a given user location to the network egress is greater than 500 miles (800 kilometers), indicating that Microsoft 365 traffic is being backhauled to a common Internet edge device or proxy.</span></span>

<span data-ttu-id="e0094-123">Dit inzicht wordt in sommige overzichtsweergaven afgekort als 'Uittreding'.</span><span class="sxs-lookup"><span data-stu-id="e0094-123">This insight is abbreviated as "Egress" in some summary views.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e0094-124">![Backhauled network egress](../media/m365-mac-perf/m365-mac-perf-insights-detail-backhauled.png)</span><span class="sxs-lookup"><span data-stu-id="e0094-124">![Backhauled network egress](../media/m365-mac-perf/m365-mac-perf-insights-detail-backhauled.png)</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="e0094-125">Wat betekent dit?</span><span class="sxs-lookup"><span data-stu-id="e0094-125">What does this mean?</span></span>

<span data-ttu-id="e0094-126">Hiermee wordt aangegeven dat de afstand tussen de kantoorlocatie en het netwerk een afstand van meer dan 800 kilometer heeft.</span><span class="sxs-lookup"><span data-stu-id="e0094-126">This identifies that the distance between the office location and the network egress is more than 500 miles (800 kilometers).</span></span> <span data-ttu-id="e0094-127">De kantoorlocatie wordt geïdentificeerd door een obfuscated clientapparaatlocatie en de netwerklocatie wordt geïdentificeerd met behulp van omgekeerde IP-adres-naar-locatiedatabases.</span><span class="sxs-lookup"><span data-stu-id="e0094-127">The office location is identified by an obfuscated client machine location and the network egress location is identified by using reverse IP Address to location databases.</span></span> <span data-ttu-id="e0094-128">De kantoorlocatie kan onnauwkeurig zijn als Windows Locatieservices is uitgeschakeld op machines.</span><span class="sxs-lookup"><span data-stu-id="e0094-128">The office location may be inaccurate if Windows Location Services is disabled on machines.</span></span> <span data-ttu-id="e0094-129">De locatie van het netwerk kan onnauwkeurig zijn als de gegevens van de reverse IP-adresdatabase onjuist zijn.</span><span class="sxs-lookup"><span data-stu-id="e0094-129">The network egress location may be inaccurate if the reverse IP Address database information is inaccurate.</span></span>

<span data-ttu-id="e0094-130">Details voor dit inzicht zijn de kantoorlocatie, het geschatte percentage van de totale tenantgebruiker op de locatie, de huidige netwerklocatie, de relevantie van de uitgangslocatie, de afstand tussen de locatie en het huidige uitgangspunt, de datum waarop de voorwaarde voor het eerst is gedetecteerd en de datum waarop de voorwaarde is opgelost.</span><span class="sxs-lookup"><span data-stu-id="e0094-130">Details for this insight include the office location, estimated percentage of total tenant user at the location, the current network egress location, relevance of the egress location, the distance between the location and the current egress point, the date the condition was first detected, and the date the condition was resolved.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="e0094-131">Wat moet ik doen?</span><span class="sxs-lookup"><span data-stu-id="e0094-131">What should I do?</span></span>

<span data-ttu-id="e0094-132">Voor dit inzicht wordt aangeraden om het netwerk dichter bij de kantoorlocatie te laten lopen, zodat de connectiviteit optimaal kan worden doorgeleid naar het globale netwerk van Microsoft en naar de dichtstbijzijnde Microsoft 365 voorde deur van de service.</span><span class="sxs-lookup"><span data-stu-id="e0094-132">For this insight, we would recommend network egress closer to the office location so that connectivity can route optimally to Microsoft's global network and to the nearest Microsoft 365 service front door.</span></span> <span data-ttu-id="e0094-133">Het sluiten van netwerkverbreding voor officelocaties van gebruikers zorgt ook voor betere prestaties in de toekomst, aangezien Microsoft in de toekomst zowel netwerkpunten van aanwezigheid als Microsoft 365-servicedeuren uitbreidt.</span><span class="sxs-lookup"><span data-stu-id="e0094-133">Having close network egress to users office locations also allows for improved performance in the future as Microsoft expands both network points of presence and Microsoft 365 service front doors in the future.</span></span>

<span data-ttu-id="e0094-134">Zie Netwerkverbindingen lokaal in Office 365 [Netwerkconnectiviteitsprincipes](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) voor meer informatie over het oplossen van dit [probleem.](microsoft-365-network-connectivity-principles.md)</span><span class="sxs-lookup"><span data-stu-id="e0094-134">For more information about how to resolve this issue, see [Egress network connections locally](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) in [Office 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="network-intermediary-device"></a><span data-ttu-id="e0094-135">Netwerkbemiddelingsapparaat</span><span class="sxs-lookup"><span data-stu-id="e0094-135">Network intermediary device</span></span>

<span data-ttu-id="e0094-136">Dit inzicht wordt weergegeven als we apparaten tussen uw gebruikers en het microsoft-netwerk hebben gedetecteerd die van invloed kunnen zijn op de Office 365 gebruikerservaring.</span><span class="sxs-lookup"><span data-stu-id="e0094-136">This insight will be displayed if we detected devices between your users and Microsoft's network which may impact the Office 365 user experience.</span></span> <span data-ttu-id="e0094-137">Het is raadzaam deze te omzeilen voor specifieke Microsoft 365 netwerkverkeer dat is bestemd voor Microsoft-datacenters.</span><span class="sxs-lookup"><span data-stu-id="e0094-137">It is recommended that these be bypassed for specific Microsoft 365 network traffic that is destined for Microsoft datacenters.</span></span> <span data-ttu-id="e0094-138">Deze aanbeveling wordt bovendien beschreven in [Microsoft 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span><span class="sxs-lookup"><span data-stu-id="e0094-138">This recommendation is additionally described in [Microsoft 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span> 

<span data-ttu-id="e0094-139">Een tussenpersoonsinzicht dat we laten zien is SSL-onderbreking en -inspectie wanneer kritieke Office 365 netwerk-eindpunten voor Exchange, SharePoint en Teams worden onderschept en ontsleuteld door netwerktussenliggende apparaten.</span><span class="sxs-lookup"><span data-stu-id="e0094-139">One network intermediary insight we show is SSL break and inspection when critical Office 365 network endpoints for Exchange, SharePoint and Teams are intercepted and decrypted by network intermediary devices.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="e0094-140">Wat betekent dit?</span><span class="sxs-lookup"><span data-stu-id="e0094-140">What does this mean?</span></span>

<span data-ttu-id="e0094-141">Netwerktussenliggende apparaten, zoals proxyservers, VPN's en preventieapparaten voor gegevensverlies, kunnen van invloed zijn op de prestaties en stabiliteit van Microsoft 365 clients waar verkeer wordt tussenbemiddeld.</span><span class="sxs-lookup"><span data-stu-id="e0094-141">Network intermediary devices such as proxy servers, VPNs, and data loss prevention devices can affect performance and stability of Microsoft 365 clients where traffic is intermediated.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="e0094-142">Wat moet ik doen?</span><span class="sxs-lookup"><span data-stu-id="e0094-142">What should I do?</span></span>

<span data-ttu-id="e0094-143">Configureer het netwerktussenapparaat dat is gedetecteerd om de verwerking voor Microsoft 365 netwerkverkeer te omzeilen.</span><span class="sxs-lookup"><span data-stu-id="e0094-143">Configure the network intermediary device that was detected to bypass processing for Microsoft 365 network traffic.</span></span>

## <a name="better-performance-detected-for-customers-near-you"></a><span data-ttu-id="e0094-144">Betere prestaties gedetecteerd voor klanten in uw buurt</span><span class="sxs-lookup"><span data-stu-id="e0094-144">Better performance detected for customers near you</span></span>

<span data-ttu-id="e0094-145">Dit inzicht wordt weergegeven als de netwerkinzichtservice detecteert dat een aanzienlijk aantal klanten in uw metrogebied betere prestaties heeft dan gebruikers in uw organisatie op deze kantoorlocatie.</span><span class="sxs-lookup"><span data-stu-id="e0094-145">This insight will be displayed if the network insights service detects that a significant number of customers in your metro area have better performance than users in your organization at this office location.</span></span>

<span data-ttu-id="e0094-146">Dit inzicht wordt in sommige overzichtsweergaven afgekort als 'Peers'.</span><span class="sxs-lookup"><span data-stu-id="e0094-146">This insight is abbreviated as "Peers" in some summary views.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e0094-147">![Relatieve netwerkprestaties](../media/m365-mac-perf/m365-mac-perf-insights-detail-cust-near-you.png)</span><span class="sxs-lookup"><span data-stu-id="e0094-147">![Relative network performance](../media/m365-mac-perf/m365-mac-perf-insights-detail-cust-near-you.png)</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="e0094-148">Wat betekent dit?</span><span class="sxs-lookup"><span data-stu-id="e0094-148">What does this mean?</span></span>

<span data-ttu-id="e0094-149">In dit inzicht worden de statistische prestaties van Microsoft 365 klanten in dezelfde plaats als deze kantoorlocatie onderzocht.</span><span class="sxs-lookup"><span data-stu-id="e0094-149">This insight examines the aggregate performance of Microsoft 365 customers in the same city as this office location.</span></span> <span data-ttu-id="e0094-150">Dit inzicht wordt weergegeven als de gemiddelde latentie van uw gebruikers 10% groter is dan de gemiddelde latentie van aangrenzende tenants.</span><span class="sxs-lookup"><span data-stu-id="e0094-150">This insight is displayed if the average latency of your users is 10% greater than the average latency of neighboring tenants.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="e0094-151">Wat moet ik doen?</span><span class="sxs-lookup"><span data-stu-id="e0094-151">What should I do?</span></span>

<span data-ttu-id="e0094-152">Er kunnen veel redenen zijn voor deze voorwaarde, waaronder latentie in uw bedrijfsnetwerk of isp, knelpunten of ontwerpproblemen met architectuur.</span><span class="sxs-lookup"><span data-stu-id="e0094-152">There could be many reasons for this condition, including latency in your corporate network or ISP, bottlenecks, or architecture design issues.</span></span> <span data-ttu-id="e0094-153">Bekijk de latentie tussen elke hop in de route tussen uw kantoornetwerk en de huidige Microsoft 365 voor deur.</span><span class="sxs-lookup"><span data-stu-id="e0094-153">Examine the latency between each hop in the route between your office network and the current Microsoft 365 front door.</span></span> <span data-ttu-id="e0094-154">Zie voor meer informatie [Microsoft 365 Netwerkconnectiviteitsbeginselen.](microsoft-365-network-connectivity-principles.md)</span><span class="sxs-lookup"><span data-stu-id="e0094-154">For more information, see [Microsoft 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="use-of-a-non-optimal-exchange-online-service-front-door"></a><span data-ttu-id="e0094-155">Gebruik van een niet-optimale Exchange Online servicedeuren</span><span class="sxs-lookup"><span data-stu-id="e0094-155">Use of a non-optimal Exchange Online service front door</span></span>

<span data-ttu-id="e0094-156">Dit inzicht wordt weergegeven als de netwerkinzichtservice detecteert dat gebruikers op een specifieke locatie geen verbinding maken met een optimale Exchange Online servicedeuren.</span><span class="sxs-lookup"><span data-stu-id="e0094-156">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to an optimal Exchange Online service front door.</span></span>

<span data-ttu-id="e0094-157">Dit inzicht wordt in sommige overzichtsweergaven afgekort als Routering.</span><span class="sxs-lookup"><span data-stu-id="e0094-157">This insight is abbreviated as "Routing" in some summary views.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e0094-158">![Niet-optimale EXO-voordeur](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-exo.png)</span><span class="sxs-lookup"><span data-stu-id="e0094-158">![Non-optimal EXO front door](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-exo.png)</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="e0094-159">Wat betekent dit?</span><span class="sxs-lookup"><span data-stu-id="e0094-159">What does this mean?</span></span>

<span data-ttu-id="e0094-160">We geven Exchange Online servicedeuren weer die geschikt zijn voor gebruik vanuit de kantoorlocatie met goede prestaties.</span><span class="sxs-lookup"><span data-stu-id="e0094-160">We list Exchange Online service front doors which are suitable for use from the office location city with good performance.</span></span> <span data-ttu-id="e0094-161">Als in de huidige test het gebruik van een Exchange Online in deze lijst wordt weergegeven, wordt deze aanbeveling aanbevolen.</span><span class="sxs-lookup"><span data-stu-id="e0094-161">If the current test shows use of an Exchange Online service front door not on this list, then we call out this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="e0094-162">Wat moet ik doen?</span><span class="sxs-lookup"><span data-stu-id="e0094-162">What should I do?</span></span>

<span data-ttu-id="e0094-163">Het gebruik van een niet-Exchange Online-servicedeuren kan worden veroorzaakt door netwerkbackhaul voordat het bedrijfsnetwerk uitkomt. In dat geval raden we lokale en directe netwerkuittreding aan.</span><span class="sxs-lookup"><span data-stu-id="e0094-163">Use of a non-optimal Exchange Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="e0094-164">Dit kan ook worden veroorzaakt door het gebruik van een externe DNS Recursive Resolver-server, in welk geval het raadzaam is om de DNS Recursive Resolver-server uit te lijnen met het netwerkuitstroom.</span><span class="sxs-lookup"><span data-stu-id="e0094-164">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="use-of-a-non-optimal-sharepoint-online-service-front-door"></a><span data-ttu-id="e0094-165">Gebruik van een niet-optimale SharePoint onlineservice voor de deur</span><span class="sxs-lookup"><span data-stu-id="e0094-165">Use of a non-optimal SharePoint Online service front door</span></span>

<span data-ttu-id="e0094-166">Dit inzicht wordt weergegeven als de netwerkinzichtservice detecteert dat gebruikers op een specifieke locatie geen verbinding maken met de dichtstbijzijnde SharePoint Online-servicedeuren.</span><span class="sxs-lookup"><span data-stu-id="e0094-166">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to the closest SharePoint Online service front door.</span></span>

<span data-ttu-id="e0094-167">Dit inzicht wordt in sommige overzichtsweergaven afgekort als 'Afd'.</span><span class="sxs-lookup"><span data-stu-id="e0094-167">This insight is abbreviated as "Afd" in some summary views.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e0094-168">![Niet-optimale SPO-voordeur](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-spo.png)</span><span class="sxs-lookup"><span data-stu-id="e0094-168">![Non-optimal SPO front door](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-spo.png)</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="e0094-169">Wat betekent dit?</span><span class="sxs-lookup"><span data-stu-id="e0094-169">What does this mean?</span></span>

<span data-ttu-id="e0094-170">We identificeren de SharePoint onlineservice waar de testclient verbinding mee maakt.</span><span class="sxs-lookup"><span data-stu-id="e0094-170">We identify the SharePoint Online service front door that the test client is connecting to.</span></span> <span data-ttu-id="e0094-171">Voor de locatie van het kantoor vergelijken we dat met de verwachte SharePoint onlineservice voor die stad.</span><span class="sxs-lookup"><span data-stu-id="e0094-171">Then for the office location city we compare that to the expected SharePoint Online service front door for that city.</span></span> <span data-ttu-id="e0094-172">Als deze niet overeenkomen, doen we deze aanbeveling.</span><span class="sxs-lookup"><span data-stu-id="e0094-172">If it doesn't match, then we make this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="e0094-173">Wat moet ik doen?</span><span class="sxs-lookup"><span data-stu-id="e0094-173">What should I do?</span></span>

<span data-ttu-id="e0094-174">Het gebruik van een niet-optimale SharePoint Online-servicedeuren kan worden veroorzaakt door backhaul van het netwerk voordat het bedrijfsnetwerk uitkomt. In dat geval raden we lokale en directe netwerkuittreding aan.</span><span class="sxs-lookup"><span data-stu-id="e0094-174">Use of a non-optimal SharePoint Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="e0094-175">Dit kan ook worden veroorzaakt door het gebruik van een externe DNS Recursive Resolver-server, in welk geval het raadzaam is om de DNS Recursive Resolver-server uit te lijnen met het netwerkuitstroom.</span><span class="sxs-lookup"><span data-stu-id="e0094-175">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="low-download-speed-from-sharepoint-front-door"></a><span data-ttu-id="e0094-176">Lage downloadsnelheid van SharePoint voor deur</span><span class="sxs-lookup"><span data-stu-id="e0094-176">Low download speed from SharePoint front door</span></span>

<span data-ttu-id="e0094-177">Dit inzicht wordt weergegeven als de netwerkinzichtservice detecteert dat de bandbreedte tussen de specifieke kantoorlocatie en SharePoint Online kleiner is dan 1 MBps.</span><span class="sxs-lookup"><span data-stu-id="e0094-177">This insight will be displayed if the network insights service detects that bandwidth between the specific office location and SharePoint Online is less than 1 MBps.</span></span>

<span data-ttu-id="e0094-178">Dit inzicht wordt in sommige overzichtsweergaven afgekort als 'Doorvoer'.</span><span class="sxs-lookup"><span data-stu-id="e0094-178">This insight is abbreviated as "Throughput" in some summary views.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="e0094-179">Wat betekent dit?</span><span class="sxs-lookup"><span data-stu-id="e0094-179">What does this mean?</span></span>

<span data-ttu-id="e0094-180">De downloadsnelheid die een gebruiker kan krijgen van SharePoint Online en OneDrive voor Bedrijven servicedeuren wordt gemeten in megabytes per seconde (MBps).</span><span class="sxs-lookup"><span data-stu-id="e0094-180">The download speed that a user can get from SharePoint Online and OneDrive for Business service front doors is measured in megabytes per second (MBps).</span></span> <span data-ttu-id="e0094-181">Als deze waarde kleiner is dan 1 MBps, bieden we dit inzicht.</span><span class="sxs-lookup"><span data-stu-id="e0094-181">If this value is less than 1 MBps then we provide this insight.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="e0094-182">Wat moet ik doen?</span><span class="sxs-lookup"><span data-stu-id="e0094-182">What should I do?</span></span>

<span data-ttu-id="e0094-183">Als u de downloadsnelheid wilt verbeteren, moet de bandbreedte mogelijk worden verhoogd.</span><span class="sxs-lookup"><span data-stu-id="e0094-183">To improve download speeds, bandwidth may need to be increased.</span></span> <span data-ttu-id="e0094-184">U kunt ook netwerkopstoppingen veroorzaken tussen gebruikersapparaten op de kantoorlocatie en de SharePoint onlineservicedeuren.</span><span class="sxs-lookup"><span data-stu-id="e0094-184">Alternatively, there may be network congestion between user machines at the office location and the SharePoint Online service front door.</span></span> <span data-ttu-id="e0094-185">Dit wordt soms congestief verlies genoemd en beperkt de downloadsnelheid die beschikbaar is voor gebruikers, zelfs als er voldoende bandbreedte beschikbaar is.</span><span class="sxs-lookup"><span data-stu-id="e0094-185">This is sometimes called congestive loss and it restricts the download speed available to users even if sufficient bandwidth is available.</span></span>

## <a name="china-user-optimal-network-egress"></a><span data-ttu-id="e0094-186">China user optimal network egress</span><span class="sxs-lookup"><span data-stu-id="e0094-186">China user optimal network egress</span></span>

<span data-ttu-id="e0094-187">Dit inzicht wordt weergegeven als uw organisatie gebruikers in China heeft die verbinding maken met uw Microsoft 365 tenant op andere geografische locaties.</span><span class="sxs-lookup"><span data-stu-id="e0094-187">This insight will be displayed if your organization has users in China connecting to your Microsoft 365 tenant in other geographic locations.</span></span> 

### <a name="what-does-this-mean"></a><span data-ttu-id="e0094-188">Wat betekent dit?</span><span class="sxs-lookup"><span data-stu-id="e0094-188">What does this mean?</span></span>

<span data-ttu-id="e0094-189">Als uw organisatie een privé WAN-verbinding heeft, raden we u aan om een NETWERK WAN-circuit te configureren vanaf uw kantoorlocaties in China met netwerktoegang tot internet op een van de volgende locaties:</span><span class="sxs-lookup"><span data-stu-id="e0094-189">If your organization has private WAN connectivity, we recommend configuring a network WAN circuit from your office locations in China that has network egress to the Internet in any of the following locations:</span></span>

- <span data-ttu-id="e0094-190">Hongkong</span><span class="sxs-lookup"><span data-stu-id="e0094-190">Hong Kong</span></span>
- <span data-ttu-id="e0094-191">Japan </span><span class="sxs-lookup"><span data-stu-id="e0094-191">Japan</span></span>
- <span data-ttu-id="e0094-192">Taiwan</span><span class="sxs-lookup"><span data-stu-id="e0094-192">Taiwan</span></span>
- <span data-ttu-id="e0094-193">Zuid-Korea</span><span class="sxs-lookup"><span data-stu-id="e0094-193">South Korea</span></span>
- <span data-ttu-id="e0094-194">Singapore</span><span class="sxs-lookup"><span data-stu-id="e0094-194">Singapore</span></span>
- <span data-ttu-id="e0094-195">Maleisië </span><span class="sxs-lookup"><span data-stu-id="e0094-195">Malaysia</span></span>

<span data-ttu-id="e0094-196">Internetuitgang verder weg van gebruikers dan deze locaties vermindert de prestaties en een uittreding in China kan leiden tot hoge latentie- en verbindingsproblemen als gevolg van congestie over de grens.</span><span class="sxs-lookup"><span data-stu-id="e0094-196">Internet egress further away from users than these locations will reduce performance, and egress in China may cause high latency and connectivity issues due to cross-border congestion.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="e0094-197">Wat moet ik doen?</span><span class="sxs-lookup"><span data-stu-id="e0094-197">What should I do?</span></span>

<span data-ttu-id="e0094-198">Zie voor meer informatie over het beperken van prestatieproblemen met betrekking tot dit inzicht Microsoft 365 algemene [tenantprestatieoptimalisatie voor Gebruikers van China.](microsoft-365-networking-china.md)</span><span class="sxs-lookup"><span data-stu-id="e0094-198">For more information about how to mitigate performance issues related to this insight, see [Microsoft 365 global tenant performance optimization for China users](microsoft-365-networking-china.md).</span></span>

## <a name="exchange-sampled-connections-impacted-by-connectivity-issues"></a><span data-ttu-id="e0094-199">Exchange verbindingen die zijn beïnvloed door verbindingsproblemen</span><span class="sxs-lookup"><span data-stu-id="e0094-199">Exchange sampled connections impacted by connectivity issues</span></span>

<span data-ttu-id="e0094-200">Dit inzicht laat zien wanneer 50% of meer van de bemonsterde verbindingen worden beïnvloed.</span><span class="sxs-lookup"><span data-stu-id="e0094-200">This insight will show when 50% or more of the sampled connections are impacted.</span></span> <span data-ttu-id="e0094-201">De impact wordt gedefinieerd door de Exchange die lager is dan 60% voor elk voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="e0094-201">The impact is defined by the Exchange assessment being below 60% for each sample.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="e0094-202">Wat betekent dit?</span><span class="sxs-lookup"><span data-stu-id="e0094-202">What does this mean?</span></span>

<span data-ttu-id="e0094-203">Het is een indicatie dat de meeste gebruikers waarschijnlijk last hebben van gebruikerservaringsproblemen met Outlook verbinding maken met Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e0094-203">It is an indication that the majority of your users are likely to be experiencing user experience issues with Outlook connecting to Exchange Online.</span></span> <span data-ttu-id="e0094-204">Het percentage steekproeven vertegenwoordigt waarschijnlijk het percentage gebruikers dat onder de 60 punten wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="e0094-204">The percentage of samples likely represents the percentage of users who show below 60 points.</span></span>  

### <a name="what-should-i-do"></a><span data-ttu-id="e0094-205">Wat moet ik doen?</span><span class="sxs-lookup"><span data-stu-id="e0094-205">What should I do?</span></span>

<span data-ttu-id="e0094-206">Schakel zichtbaarheid van officelocatienetwerkconnectiviteit in als u dit nog niet hebt gedaan.</span><span class="sxs-lookup"><span data-stu-id="e0094-206">Enable office location network connectivity visibility if you have not already done so.</span></span> <span data-ttu-id="e0094-207">U wilt bepalen welke kantoren worden beïnvloed door slechte netwerkconnectiviteit die van invloed is op Exchange en manieren zoeken om de netwerkperimeter te verbeteren bij elk kantoor dat de gebruikers verbindt met het netwerk van Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e0094-207">You want to identify which offices are impacted by poor network connectivity that is impacting Exchange and find ways to improve the network perimeter at each that connects the users to Microsoft's network.</span></span>

## <a name="sharepoint-sampled-connections-impacted-by-connectivity-issues"></a><span data-ttu-id="e0094-208">SharePoint verbindingen die zijn beïnvloed door verbindingsproblemen</span><span class="sxs-lookup"><span data-stu-id="e0094-208">SharePoint sampled connections impacted by connectivity issues</span></span>

<span data-ttu-id="e0094-209">Dit inzicht laat zien wanneer 50% of meer van de bemonsterde verbindingen worden beïnvloed.</span><span class="sxs-lookup"><span data-stu-id="e0094-209">This insight will show when 50% or more of the sampled connections are impacted.</span></span> <span data-ttu-id="e0094-210">De impact wordt gedefinieerd door de SharePoint die lager is dan 40% voor elk voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="e0094-210">The impact is defined by the SharePoint assessment being below 40% for each sample.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="e0094-211">Wat betekent dit?</span><span class="sxs-lookup"><span data-stu-id="e0094-211">What does this mean?</span></span>

<span data-ttu-id="e0094-212">Het is een indicatie dat de meeste gebruikers waarschijnlijk te maken hebben met gebruikerservaringsproblemen met SharePoint en OneDrive.</span><span class="sxs-lookup"><span data-stu-id="e0094-212">It is an indication that the majority of your users are likely to be experiencing user experience issues with SharePoint and OneDrive.</span></span> <span data-ttu-id="e0094-213">Het percentage steekproeven vertegenwoordigt waarschijnlijk het percentage gebruikers dat onder de 40 punten wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="e0094-213">The percentage of samples likely represents the percentage of users who show below 40 points.</span></span>  

### <a name="what-should-i-do"></a><span data-ttu-id="e0094-214">Wat moet ik doen?</span><span class="sxs-lookup"><span data-stu-id="e0094-214">What should I do?</span></span>

<span data-ttu-id="e0094-215">Schakel zichtbaarheid van officelocatienetwerkconnectiviteit in als u dit nog niet hebt gedaan.</span><span class="sxs-lookup"><span data-stu-id="e0094-215">Enable office location network connectivity visibility if you have not already done so.</span></span> <span data-ttu-id="e0094-216">U wilt bepalen welke kantoren worden beïnvloed door slechte netwerkconnectiviteit die van invloed is op SharePoint en manieren vinden om de netwerkperimeter te verbeteren bij elk kantoor dat de gebruikers verbindt met het microsoft-netwerk.</span><span class="sxs-lookup"><span data-stu-id="e0094-216">You want to identify which offices are impacted by poor network connectivity that is impacting SharePoint and find ways to improve the network perimeter at each that connects the users to Microsoft's network.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e0094-217">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="e0094-217">Related topics</span></span>

[<span data-ttu-id="e0094-218">Netwerkconnectiviteit in het Microsoft 365 beheercentrum (voorbeeld)</span><span class="sxs-lookup"><span data-stu-id="e0094-218">Network connectivity in the Microsoft 365 Admin Center (preview)</span></span>](office-365-network-mac-perf-overview.md)

[<span data-ttu-id="e0094-219">Microsoft 365 netwerkbeoordeling (voorbeeld)</span><span class="sxs-lookup"><span data-stu-id="e0094-219">Microsoft 365 network assessment (preview)</span></span>](office-365-network-mac-perf-score.md)

[<span data-ttu-id="e0094-220">Microsoft 365 testprogramma voor netwerkconnectiviteit (voorbeeld)</span><span class="sxs-lookup"><span data-stu-id="e0094-220">Microsoft 365 network connectivity test tool (preview)</span></span>](office-365-network-mac-perf-onboarding-tool.md)

[<span data-ttu-id="e0094-221">Microsoft 365 Network Connectivity Location Services (preview)</span><span class="sxs-lookup"><span data-stu-id="e0094-221">Microsoft 365 Network Connectivity Location Services (preview)</span></span>](office-365-network-mac-location-services.md)
