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
ms.openlocfilehash: d6786ce6cd58ce6f350804fbbacd272b8c077dc0
ms.sourcegitcommit: 1ac884d8470b2f2a58b6f79e324fd91e4d11dceb
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2021
ms.locfileid: "50055471"
---
# <a name="microsoft-365-network-insights-preview"></a><span data-ttu-id="529b2-103">Microsoft 365 Network Insights (preview)</span><span class="sxs-lookup"><span data-stu-id="529b2-103">Microsoft 365 Network Insights (preview)</span></span>

<span data-ttu-id="529b2-104">**Netwerkinzichten** zijn prestatiestatistieken die worden verzameld via uw Microsoft 365-tenant en die alleen kunnen worden bekeken door beheerders in uw tenant.</span><span class="sxs-lookup"><span data-stu-id="529b2-104">**Network insights** are performance metrics collected from your Microsoft 365 tenant, and available to view only by administrative users in your tenant.</span></span> <span data-ttu-id="529b2-105">Inzichten worden weergegeven in het Microsoft 365-beheercentrum op <https://portal.microsoft.com/adminportal/home#/networkperformance> .</span><span class="sxs-lookup"><span data-stu-id="529b2-105">Insights are displayed in the Microsoft 365 Admin Center at <https://portal.microsoft.com/adminportal/home#/networkperformance>.</span></span>

<span data-ttu-id="529b2-106">Inzichten zijn bedoeld om u te helpen bij het ontwerpen van netwerkperimeters voor uw kantoorlocaties.</span><span class="sxs-lookup"><span data-stu-id="529b2-106">Insights are intended to help in designing network perimeters for your office locations.</span></span> <span data-ttu-id="529b2-107">Elk inzicht biedt livedetails over de prestatiekenmerken voor een specifiek algemeen probleem voor elke geografische locatie waar gebruikers toegang hebben tot uw tenant.</span><span class="sxs-lookup"><span data-stu-id="529b2-107">Each insight provides live details about the performance characteristics for a specific common issue for each geographic location where users are accessing your tenant.</span></span>

<span data-ttu-id="529b2-108">Er zijn zes specifieke netwerkinzichten die kunnen worden weergegeven voor elke kantoorlocatie:</span><span class="sxs-lookup"><span data-stu-id="529b2-108">There are six specific network insights that may be shown for each office location:</span></span>

- [<span data-ttu-id="529b2-109">Backgressie van netwerk</span><span class="sxs-lookup"><span data-stu-id="529b2-109">Backhauled network egress</span></span>](#backhauled-network-egress)
- [<span data-ttu-id="529b2-110">Tussenapparaat netwerk</span><span class="sxs-lookup"><span data-stu-id="529b2-110">Network intermediary device</span></span>](#network-intermediary-device)
- [<span data-ttu-id="529b2-111">Betere prestaties gedetecteerd voor klanten bij u in de buurt</span><span class="sxs-lookup"><span data-stu-id="529b2-111">Better performance detected for customers near you</span></span>](#better-performance-detected-for-customers-near-you)
- [<span data-ttu-id="529b2-112">Gebruik van een niet-optimale front door de Exchange Online-service</span><span class="sxs-lookup"><span data-stu-id="529b2-112">Use of a non-optimal Exchange Online service front door</span></span>](#use-of-a-non-optimal-exchange-online-service-front-door)
- [<span data-ttu-id="529b2-113">Gebruik van een niet-optimale front door de SharePoint Online-service</span><span class="sxs-lookup"><span data-stu-id="529b2-113">Use of a non-optimal SharePoint Online service front door</span></span>](#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [<span data-ttu-id="529b2-114">Lage downloadsnelheid van SharePoint-front door</span><span class="sxs-lookup"><span data-stu-id="529b2-114">Low download speed from SharePoint front door</span></span>](#low-download-speed-from-sharepoint-front-door)
- [<span data-ttu-id="529b2-115">Optimaal netwerkingressie china-gebruiker</span><span class="sxs-lookup"><span data-stu-id="529b2-115">China user optimal network egress</span></span>](#china-user-optimal-network-egress)

<span data-ttu-id="529b2-116">Er zijn twee netwerkinzichten op tenantniveau die kunnen worden weergegeven voor de tenant.</span><span class="sxs-lookup"><span data-stu-id="529b2-116">There are two tenant level network insights that may be shown for the tenant.</span></span> <span data-ttu-id="529b2-117">Deze worden ook weergegeven op de scorepagina's van Producvitivy:</span><span class="sxs-lookup"><span data-stu-id="529b2-117">These also appear in the producvitivy score pages:</span></span>

- [<span data-ttu-id="529b2-118">Voorbeeldverbindingen in Exchange die zijn beïnvloed door verbindingsproblemen</span><span class="sxs-lookup"><span data-stu-id="529b2-118">Exchange sampled connections impacted by connectivity issues</span></span>](#exchange-sampled-connections-impacted-by-connectivity-issues)
- [<span data-ttu-id="529b2-119">Voorbeeldverbindingen in SharePoint die zijn beïnvloed door verbindingsproblemen</span><span class="sxs-lookup"><span data-stu-id="529b2-119">SharePoint sampled connections impacted by connectivity issues</span></span>](#sharepoint-sampled-connections-impacted-by-connectivity-issues)

>[!IMPORTANT]
><span data-ttu-id="529b2-120">Netwerkinzichten, prestatieaanbevelingen en beoordelingen in het Microsoft 365-beheercentrum hebben momenteel de preview-status en zijn alleen beschikbaar voor Microsoft 365-tenants die zijn ingeschreven voor het feature preview-programma.</span><span class="sxs-lookup"><span data-stu-id="529b2-120">Network insights, performance recommendations and assessments in the Microsoft 365 Admin Center is currently in preview status, and is only available for Microsoft 365 tenants that have been enrolled in the feature preview program.</span></span>

## <a name="backhauled-network-egress"></a><span data-ttu-id="529b2-121">Backgressie van netwerk</span><span class="sxs-lookup"><span data-stu-id="529b2-121">Backhauled network egress</span></span>

<span data-ttu-id="529b2-122">Dit inzicht wordt weergegeven als de Network Insights-service detecteert dat de afstand tussen een bepaalde gebruikerslocatie en het netwerkuitzicht groter is dan 500 kilometer (800 kilometer), waarmee wordt aangegeven dat Microsoft 365-verkeer wordt geback-mailt naar een gemeenschappelijk internetrandapparaat of -proxy.</span><span class="sxs-lookup"><span data-stu-id="529b2-122">This insight will be displayed if the network insights service detects that the distance from a given user location to the network egress is greater than 500 miles (800 kilometers), indicating that Microsoft 365 traffic is being backhauled to a common Internet edge device or proxy.</span></span>

<span data-ttu-id="529b2-123">Dit inzicht wordt in sommige overzichtsweergaven afgekort als 'Uitgangsweergaven'.</span><span class="sxs-lookup"><span data-stu-id="529b2-123">This insight is abbreviated as "Egress" in some summary views.</span></span>

![Teruggeopend netwerkingressie](../media/m365-mac-perf/m365-mac-perf-insights-detail-backhauled.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="529b2-125">Wat betekent dit?</span><span class="sxs-lookup"><span data-stu-id="529b2-125">What does this mean?</span></span>

<span data-ttu-id="529b2-126">Hiermee wordt aangegeven dat de afstand tussen de kantoorlocatie en het netwerkingressie groter is dan 500 kilometer (800 kilometer).</span><span class="sxs-lookup"><span data-stu-id="529b2-126">This identifies that the distance between the office location and the network egress is more than 500 miles (800 kilometers).</span></span> <span data-ttu-id="529b2-127">De kantoorlocatie wordt geïdentificeerd door een locatie van een onbekende clientmachine en de netwerklocatie wordt vastgesteld met behulp van reverse IP Address to location-databases.</span><span class="sxs-lookup"><span data-stu-id="529b2-127">The office location is identified by an obfuscated client machine location and the network egress location is identified by using reverse IP Address to location databases.</span></span> <span data-ttu-id="529b2-128">De kantoorlocatie is mogelijk onjuist als Windows Location Services is uitgeschakeld op computers.</span><span class="sxs-lookup"><span data-stu-id="529b2-128">The office location may be inaccurate if Windows Location Services is disabled on machines.</span></span> <span data-ttu-id="529b2-129">De netwerkingangslocatie is mogelijk onjuist als de gegevens van de omgekeerde IP-adresdatabase onjuist zijn.</span><span class="sxs-lookup"><span data-stu-id="529b2-129">The network egress location may be inaccurate if the reverse IP Address database information is inaccurate.</span></span>

<span data-ttu-id="529b2-130">Details voor dit inzicht zijn de kantoorlocatie, het geschatte percentage van het totale aantal tenantgebruikers op de locatie, de huidige netwerkingressielocatie, de relevantie van de uitgangslocatie, de afstand tussen de locatie en het huidige uitgangspunt, de datum waarop de voorwaarde voor het eerst is gedetecteerd en de datum waarop de voorwaarde is opgelost.</span><span class="sxs-lookup"><span data-stu-id="529b2-130">Details for this insight include the office location, estimated percentage of total tenant user at the location, the current network egress location, relevance of the egress location, the distance between the location and the current egress point, the date the condition was first detected, and the date the condition was resolved.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="529b2-131">Wat moet ik doen?</span><span class="sxs-lookup"><span data-stu-id="529b2-131">What should I do?</span></span>

<span data-ttu-id="529b2-132">Voor dit inzicht raden we aan dat het netwerk dichter bij de kantoorlocatie komt, zodat de connectiviteit optimaal kan worden gerouted naar het wereldwijde netwerk van Microsoft en naar de dichtstbijzijnde microsoft 365-serviceaanzicht.</span><span class="sxs-lookup"><span data-stu-id="529b2-132">For this insight, we would recommend network egress closer to the office location so that connectivity can route optimally to Microsoft's global network and to the nearest Microsoft 365 service front door.</span></span> <span data-ttu-id="529b2-133">Als het netwerk niet ver van kantoorlocaties voor gebruikers af komt te liggen, kunnen de prestaties in de toekomst worden verbeterd omdat zowel netwerkaand dus aanwezigheidspunten als microsoft 365-service in de toekomst worden uitgebreid.</span><span class="sxs-lookup"><span data-stu-id="529b2-133">Having close network egress to users office locations also allows for improved performance in the future as Microsoft expands both network points of presence and Microsoft 365 service front doors in the future.</span></span>

<span data-ttu-id="529b2-134">Zie voor meer informatie over hoe u dit probleem kunt oplossen, lokaal uitgangspuntnetwerkverbindingen in [Office 365-netwerkconnectiviteitsprincipes.](microsoft-365-network-connectivity-principles.md) [](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally)</span><span class="sxs-lookup"><span data-stu-id="529b2-134">For more information about how to resolve this issue, see [Egress network connections locally](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) in [Office 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="network-intermediary-device"></a><span data-ttu-id="529b2-135">Tussenapparaat netwerk</span><span class="sxs-lookup"><span data-stu-id="529b2-135">Network intermediary device</span></span>

<span data-ttu-id="529b2-136">Dit inzicht wordt weergegeven als er apparaten tussen uw gebruikers en het Microsoft-netwerk zijn gedetecteerd die van invloed kunnen zijn op de office 365-gebruikerservaring.</span><span class="sxs-lookup"><span data-stu-id="529b2-136">This insight will be displayed if we detected devices between your users and Microsoft's network which may impact the Office 365 user experience.</span></span> <span data-ttu-id="529b2-137">Het is raadzaam deze te omzeilen voor specifiek Microsoft 365-netwerkverkeer dat bestemd is voor Microsoft-datacenters.</span><span class="sxs-lookup"><span data-stu-id="529b2-137">It is recommended that these be bypassed for specific Microsoft 365 network traffic that is destined for Microsoft datacenters.</span></span> <span data-ttu-id="529b2-138">Deze aanbeveling wordt bovendien beschreven in De Beginselen voor [Microsoft 365-netwerkconnectiviteit](microsoft-365-network-connectivity-principles.md)</span><span class="sxs-lookup"><span data-stu-id="529b2-138">This recommendation is additionally described in [Microsoft 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md)</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="529b2-139">Wat betekent dit?</span><span class="sxs-lookup"><span data-stu-id="529b2-139">What does this mean?</span></span>

<span data-ttu-id="529b2-140">Tussenliggende apparaten van het netwerk, zoals proxyservers, VPN's en apparaten voor preventie van gegevensverlies, kunnen van invloed zijn op de prestaties en stabiliteit van Microsoft 365-clients waarbij verkeer tussenliggende clients wordt gebruikt.</span><span class="sxs-lookup"><span data-stu-id="529b2-140">Network intermediary devices such as proxy servers, VPNs, and data loss prevention devices can affect performance and stability of Microsoft 365 clients where traffic is intermediated.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="529b2-141">Wat moet ik doen?</span><span class="sxs-lookup"><span data-stu-id="529b2-141">What should I do?</span></span>

<span data-ttu-id="529b2-142">Configureer het tussenstation van het netwerkapparaat dat is gedetecteerd om de verwerking voor Microsoft 365-netwerkverkeer te omzeilen.</span><span class="sxs-lookup"><span data-stu-id="529b2-142">Configure the network intermediary device that was detected to bypass processing for Microsoft 365 network traffic.</span></span>

## <a name="better-performance-detected-for-customers-near-you"></a><span data-ttu-id="529b2-143">Betere prestaties gedetecteerd voor klanten bij u in de buurt</span><span class="sxs-lookup"><span data-stu-id="529b2-143">Better performance detected for customers near you</span></span>

<span data-ttu-id="529b2-144">Dit inzicht wordt weergegeven als de network insights-service detecteert dat een aanzienlijk aantal klanten in uw metrogebied betere prestaties leveren dan gebruikers in uw organisatie op deze kantoorlocatie.</span><span class="sxs-lookup"><span data-stu-id="529b2-144">This insight will be displayed if the network insights service detects that a significant number of customers in your metro area have better performance than users in your organization at this office location.</span></span>

<span data-ttu-id="529b2-145">Dit inzicht wordt in sommige overzichtsweergaven afgekort als 'Peers'.</span><span class="sxs-lookup"><span data-stu-id="529b2-145">This insight is abbreviated as "Peers" in some summary views.</span></span>

![Relatieve netwerkprestaties](../media/m365-mac-perf/m365-mac-perf-insights-detail-cust-near-you.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="529b2-147">Wat betekent dit?</span><span class="sxs-lookup"><span data-stu-id="529b2-147">What does this mean?</span></span>

<span data-ttu-id="529b2-148">Dit inzicht bekijkt de statistische prestaties van Microsoft 365-klanten in dezelfde plaats als deze kantoorlocatie.</span><span class="sxs-lookup"><span data-stu-id="529b2-148">This insight examines the aggregate performance of Microsoft 365 customers in the same city as this office location.</span></span> <span data-ttu-id="529b2-149">Dit inzicht wordt weergegeven als de gemiddelde latentie van uw gebruikers 10% groter is dan de gemiddelde latentie van aangrenzende tenants.</span><span class="sxs-lookup"><span data-stu-id="529b2-149">This insight is displayed if the average latency of your users is 10% greater than the average latency of neighboring tenants.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="529b2-150">Wat moet ik doen?</span><span class="sxs-lookup"><span data-stu-id="529b2-150">What should I do?</span></span>

<span data-ttu-id="529b2-151">Er kunnen veel redenen zijn voor deze voorwaarde, waaronder latentie in uw bedrijfsnetwerk of isprovider, knelpunten of ontwerpproblemen met de architectuur.</span><span class="sxs-lookup"><span data-stu-id="529b2-151">There could be many reasons for this condition, including latency in your corporate network or ISP, bottlenecks, or architecture design issues.</span></span> <span data-ttu-id="529b2-152">Bekijk de latentie tussen elke hop in de route tussen uw kantoornetwerk en de huidige Microsoft 365-front door.</span><span class="sxs-lookup"><span data-stu-id="529b2-152">Examine the latency between each hop in the route between your office network and the current Microsoft 365 front door.</span></span> <span data-ttu-id="529b2-153">Zie de Beginselen voor [Microsoft 365-netwerkconnectiviteit voor meer informatie.](microsoft-365-network-connectivity-principles.md)</span><span class="sxs-lookup"><span data-stu-id="529b2-153">For more information, see [Microsoft 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="use-of-a-non-optimal-exchange-online-service-front-door"></a><span data-ttu-id="529b2-154">Gebruik van een niet-optimale voorzijde van Exchange Online-service</span><span class="sxs-lookup"><span data-stu-id="529b2-154">Use of a non-optimal Exchange Online service front door</span></span>

<span data-ttu-id="529b2-155">Dit inzicht wordt weergegeven als de network insights-service detecteert dat gebruikers op een specifieke locatie geen verbinding maken met een optimale front door de Exchange Online-service.</span><span class="sxs-lookup"><span data-stu-id="529b2-155">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to an optimal Exchange Online service front door.</span></span>

<span data-ttu-id="529b2-156">Dit inzicht wordt in sommige overzichtsweergaven afgekort als Routering.</span><span class="sxs-lookup"><span data-stu-id="529b2-156">This insight is abbreviated as "Routing" in some summary views.</span></span>

![Niet-optimale EXO-voorzijde](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-exo.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="529b2-158">Wat betekent dit?</span><span class="sxs-lookup"><span data-stu-id="529b2-158">What does this mean?</span></span>

<span data-ttu-id="529b2-159">De frontdeuren van Exchange Online-service worden vermeld, die geschikt zijn voor gebruik vanuit de plaats op kantoorlocatie met goede prestaties.</span><span class="sxs-lookup"><span data-stu-id="529b2-159">We list Exchange Online service front doors which are suitable for use from the office location city with good performance.</span></span> <span data-ttu-id="529b2-160">Als in de huidige test het gebruik van een Exchange Online-service front door niet in deze lijst wordt weergegeven, wordt deze aanbeveling genoemd.</span><span class="sxs-lookup"><span data-stu-id="529b2-160">If the current test shows use of an Exchange Online service front door not on this list, then we call out this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="529b2-161">Wat moet ik doen?</span><span class="sxs-lookup"><span data-stu-id="529b2-161">What should I do?</span></span>

<span data-ttu-id="529b2-162">Het gebruik van een niet-optimale front door de Exchange Online-service kan worden veroorzaakt door netwerkbackhaul vóór het bedrijfsnetwerkuitregressie. In dit geval raden we lokaal en direct netwerkuiteringen aan.</span><span class="sxs-lookup"><span data-stu-id="529b2-162">Use of a non-optimal Exchange Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="529b2-163">Dit kan ook worden veroorzaakt door gebruik van een externe DNS Recursive Resolver-server. In dat geval wordt u aangeraden de server DNS Recursive Resolver uit te lijnen op het netwerkuitlijningsnetwerk.</span><span class="sxs-lookup"><span data-stu-id="529b2-163">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="use-of-a-non-optimal-sharepoint-online-service-front-door"></a><span data-ttu-id="529b2-164">Gebruik van een niet-optimale front door de SharePoint Online-service</span><span class="sxs-lookup"><span data-stu-id="529b2-164">Use of a non-optimal SharePoint Online service front door</span></span>

<span data-ttu-id="529b2-165">Dit inzicht wordt weergegeven als door de Network Insights-service wordt gedetecteerd dat gebruikers op een specifieke locatie geen verbinding maken met de dichtstbijzijnde front door de SharePoint Online-service.</span><span class="sxs-lookup"><span data-stu-id="529b2-165">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to the closest SharePoint Online service front door.</span></span>

<span data-ttu-id="529b2-166">Dit inzicht wordt in sommige overzichtsweergaven afgekort als Afd.</span><span class="sxs-lookup"><span data-stu-id="529b2-166">This insight is abbreviated as "Afd" in some summary views.</span></span>

![Niet-optimale SPO-front door](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-spo.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="529b2-168">Wat betekent dit?</span><span class="sxs-lookup"><span data-stu-id="529b2-168">What does this mean?</span></span>

<span data-ttu-id="529b2-169">We identificeren de frontlinie van de SharePoint Online-service waar de testclient verbinding mee maakt.</span><span class="sxs-lookup"><span data-stu-id="529b2-169">We identify the SharePoint Online service front door that the test client is connecting to.</span></span> <span data-ttu-id="529b2-170">Voor de plaats waar kantoorlocatie wordt gevonden, vergelijken we die met de verwachte frontlinie van de SharePoint Online-service voor die plaats.</span><span class="sxs-lookup"><span data-stu-id="529b2-170">Then for the office location city we compare that to the expected SharePoint Online service front door for that city.</span></span> <span data-ttu-id="529b2-171">Als het niet overeen komt, doen we dit.</span><span class="sxs-lookup"><span data-stu-id="529b2-171">If it doesn't match, then we make this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="529b2-172">Wat moet ik doen?</span><span class="sxs-lookup"><span data-stu-id="529b2-172">What should I do?</span></span>

<span data-ttu-id="529b2-173">Het gebruik van een niet-optimale front door de SharePoint Online-service kan worden veroorzaakt door netwerkbackhaul vóór het bedrijfsnetwerkuitregressie. In dit geval raden we lokaal en rechtstreeks netwerkuitreeding aan.</span><span class="sxs-lookup"><span data-stu-id="529b2-173">Use of a non-optimal SharePoint Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="529b2-174">Dit kan ook worden veroorzaakt door gebruik van een externe DNS Recursive Resolver-server. In dat geval wordt u aangeraden de server DNS Recursive Resolver uit te lijnen op het netwerkuitlijningsnetwerk.</span><span class="sxs-lookup"><span data-stu-id="529b2-174">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="low-download-speed-from-sharepoint-front-door"></a><span data-ttu-id="529b2-175">Lage downloadsnelheid van SharePoint-front door</span><span class="sxs-lookup"><span data-stu-id="529b2-175">Low download speed from SharePoint front door</span></span>

<span data-ttu-id="529b2-176">Dit inzicht wordt weergegeven als de network insights-service detecteert dat de bandbreedte tussen de specifieke kantoorlocatie en SharePoint Online minder dan 1 MBPS is.</span><span class="sxs-lookup"><span data-stu-id="529b2-176">This insight will be displayed if the network insights service detects that bandwidth between the specific office location and SharePoint Online is less than 1 MBps.</span></span>

<span data-ttu-id="529b2-177">Dit inzicht wordt in sommige overzichtsweergaven afgekort als 'Doorvoer'.</span><span class="sxs-lookup"><span data-stu-id="529b2-177">This insight is abbreviated as "Throughput" in some summary views.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="529b2-178">Wat betekent dit?</span><span class="sxs-lookup"><span data-stu-id="529b2-178">What does this mean?</span></span>

<span data-ttu-id="529b2-179">De downloadsnelheid die een gebruiker via de front-doors van SharePoint Online en OneDrive voor Bedrijven kan downloaden, wordt gemeten in megabytes per seconde (MBPS).</span><span class="sxs-lookup"><span data-stu-id="529b2-179">The download speed that a user can get from SharePoint Online and OneDrive for Business service front doors is measured in megabytes per second (MBps).</span></span> <span data-ttu-id="529b2-180">Als deze waarde kleiner is dan 1 MBPS, geven we dit inzicht.</span><span class="sxs-lookup"><span data-stu-id="529b2-180">If this value is less than 1 MBps then we provide this insight.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="529b2-181">Wat moet ik doen?</span><span class="sxs-lookup"><span data-stu-id="529b2-181">What should I do?</span></span>

<span data-ttu-id="529b2-182">Om de downloadsnelheid te verbeteren, moet de bandbreedte mogelijk worden verhoogd.</span><span class="sxs-lookup"><span data-stu-id="529b2-182">To improve download speeds, bandwidth may need to be increased.</span></span> <span data-ttu-id="529b2-183">Er kunnen zich ook netwerkopstoppingen bevinden tussen de gebruikersapparaten op kantoorlocatie en de front door de SharePoint Online-service.</span><span class="sxs-lookup"><span data-stu-id="529b2-183">Alternatively, there may be network congestion between user machines at the office location and the SharePoint Online service front door.</span></span> <span data-ttu-id="529b2-184">Dit wordt ook wel congestive loss genoemd en beperkt de downloadsnelheid voor gebruikers, zelfs als er voldoende bandbreedte beschikbaar is.</span><span class="sxs-lookup"><span data-stu-id="529b2-184">This is sometimes called congestive loss and it restricts the download speed available to users even if sufficient bandwidth is available.</span></span>

## <a name="china-user-optimal-network-egress"></a><span data-ttu-id="529b2-185">Optimaal netwerkingressie china-gebruiker</span><span class="sxs-lookup"><span data-stu-id="529b2-185">China user optimal network egress</span></span>

<span data-ttu-id="529b2-186">Dit inzicht wordt weergegeven als uw organisatie heeft dat gebruikers in China verbinding maken met uw Microsoft 365-tenant op andere geografische locaties.</span><span class="sxs-lookup"><span data-stu-id="529b2-186">This insight will be displayed if your organization has users in China connecting to your Microsoft 365 tenant in other geographic locations.</span></span> 

### <a name="what-does-this-mean"></a><span data-ttu-id="529b2-187">Wat betekent dit?</span><span class="sxs-lookup"><span data-stu-id="529b2-187">What does this mean?</span></span>

<span data-ttu-id="529b2-188">Als uw organisatie een persoonlijke WAN-verbinding heeft, raden we u aan een NETWERK-WAN-circuit te configureren vanaf uw kantoorlocaties in China die een netwerkingressie naar internet hebben op een van de volgende locaties:</span><span class="sxs-lookup"><span data-stu-id="529b2-188">If your organization has private WAN connectivity, we recommend configuring a network WAN circuit from your office locations in China that has network egress to the Internet in any of the following locations:</span></span>

- <span data-ttu-id="529b2-189">Hongkong</span><span class="sxs-lookup"><span data-stu-id="529b2-189">Hong Kong</span></span>
- <span data-ttu-id="529b2-190">Japan </span><span class="sxs-lookup"><span data-stu-id="529b2-190">Japan</span></span>
- <span data-ttu-id="529b2-191">Taiwan</span><span class="sxs-lookup"><span data-stu-id="529b2-191">Taiwan</span></span>
- <span data-ttu-id="529b2-192">Zuid-Korea</span><span class="sxs-lookup"><span data-stu-id="529b2-192">South Korea</span></span>
- <span data-ttu-id="529b2-193">Singapore</span><span class="sxs-lookup"><span data-stu-id="529b2-193">Singapore</span></span>
- <span data-ttu-id="529b2-194">Maleisië </span><span class="sxs-lookup"><span data-stu-id="529b2-194">Malaysia</span></span>

<span data-ttu-id="529b2-195">Internetuitgangspunten verder weg van gebruikers dan deze locaties verminderen de prestaties, en een uitgang in China kan leiden tot grote latentie en verbindingsproblemen door opstoppingen aan de rand van de grens.</span><span class="sxs-lookup"><span data-stu-id="529b2-195">Internet egress further away from users than these locations will reduce performance, and egress in China may cause high latency and connectivity issues due to cross-border congestion.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="529b2-196">Wat moet ik doen?</span><span class="sxs-lookup"><span data-stu-id="529b2-196">What should I do?</span></span>

<span data-ttu-id="529b2-197">Zie de wereldwijde tenantprestatieoptimalisatie voor China-gebruikers in [Microsoft 365](microsoft-365-networking-china.md)voor meer informatie over het beperken van prestatieproblemen met betrekking tot dit inzicht.</span><span class="sxs-lookup"><span data-stu-id="529b2-197">For more information about how to mitigate performance issues related to this insight, see [Microsoft 365 global tenant performance optimization for China users](microsoft-365-networking-china.md).</span></span>

## <a name="exchange-sampled-connections-impacted-by-connectivity-issues"></a><span data-ttu-id="529b2-198">Voorbeeldverbindingen van Exchange die zijn beïnvloed door verbindingsproblemen</span><span class="sxs-lookup"><span data-stu-id="529b2-198">Exchange sampled connections impacted by connectivity issues</span></span>

<span data-ttu-id="529b2-199">Dit inzicht geeft aan wanneer 50% of meer van de steekproefverbindingen worden beïnvloed.</span><span class="sxs-lookup"><span data-stu-id="529b2-199">This insight will show when 50% or more of the sampled connections are impacted.</span></span> <span data-ttu-id="529b2-200">De impact wordt gedefinieerd door de Exchange-evaluatie lager dan 60% voor elke steekproef.</span><span class="sxs-lookup"><span data-stu-id="529b2-200">The impact is defined by the Exchange assessment being below 60% for each sample.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="529b2-201">Wat betekent dit?</span><span class="sxs-lookup"><span data-stu-id="529b2-201">What does this mean?</span></span>

<span data-ttu-id="529b2-202">Het is een indicatie dat de meerderheid van uw gebruikers waarschijnlijk problemen ondervindt met gebruikerservaring bij het maken van verbinding tussen Outlook en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="529b2-202">It is an indication that the majority of your users are likely to be experiencing user experience issues with Outlook connecting to Exchange Online.</span></span> <span data-ttu-id="529b2-203">Het percentage steekproeven vertegenwoordigt waarschijnlijk het percentage gebruikers dat minder dan 60 punten laat zien.</span><span class="sxs-lookup"><span data-stu-id="529b2-203">The percentage of samples likely represents the percentage of users who show below 60 points.</span></span>  

### <a name="what-should-i-do"></a><span data-ttu-id="529b2-204">Wat moet ik doen?</span><span class="sxs-lookup"><span data-stu-id="529b2-204">What should I do?</span></span>

<span data-ttu-id="529b2-205">Schakel de zichtbaarheid van de netwerkverbinding tussen office-locaties in als u dat nog niet hebt gedaan.</span><span class="sxs-lookup"><span data-stu-id="529b2-205">Enable office location network connectivity visibility if you have not already done so.</span></span> <span data-ttu-id="529b2-206">U wilt vaststellen welke kantoren worden beïnvloed door slechte netwerkconnectiviteit die van invloed is op Exchange en manieren vinden om de netwerkperimeter te verbeteren voor elk kantoor dat de gebruikers met het Microsoft-netwerk verbindt.</span><span class="sxs-lookup"><span data-stu-id="529b2-206">You want to identify which offices are impacted by poor network connectivity that is impacting Exchange and find ways to improve the network perimeter at each that connects the users to Microsoft's network.</span></span>

## <a name="sharepoint-sampled-connections-impacted-by-connectivity-issues"></a><span data-ttu-id="529b2-207">Voorbeeldverbindingen in SharePoint die zijn beïnvloed door verbindingsproblemen</span><span class="sxs-lookup"><span data-stu-id="529b2-207">SharePoint sampled connections impacted by connectivity issues</span></span>

<span data-ttu-id="529b2-208">Dit inzicht geeft aan wanneer 50% of meer van de steekproefverbindingen worden beïnvloed.</span><span class="sxs-lookup"><span data-stu-id="529b2-208">This insight will show when 50% or more of the sampled connections are impacted.</span></span> <span data-ttu-id="529b2-209">De impact wordt gedefinieerd door de SharePoint-evaluatie lager dan 40% voor elke steekproef.</span><span class="sxs-lookup"><span data-stu-id="529b2-209">The impact is defined by the SharePoint assessment being below 40% for each sample.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="529b2-210">Wat betekent dit?</span><span class="sxs-lookup"><span data-stu-id="529b2-210">What does this mean?</span></span>

<span data-ttu-id="529b2-211">Het is een indicatie dat de meeste gebruikers waarschijnlijk gebruikerservaringsproblemen ondervinden met SharePoint en OneDrive.</span><span class="sxs-lookup"><span data-stu-id="529b2-211">It is an indication that the majority of your users are likely to be experiencing user experience issues with SharePoint and OneDrive.</span></span> <span data-ttu-id="529b2-212">Het percentage steekproeven vertegenwoordigt waarschijnlijk het percentage gebruikers dat minder dan 40 punten laat zien.</span><span class="sxs-lookup"><span data-stu-id="529b2-212">The percentage of samples likely represents the percentage of users who show below 40 points.</span></span>  

### <a name="what-should-i-do"></a><span data-ttu-id="529b2-213">Wat moet ik doen?</span><span class="sxs-lookup"><span data-stu-id="529b2-213">What should I do?</span></span>

<span data-ttu-id="529b2-214">Schakel de zichtbaarheid van de netwerkverbinding tussen office-locaties in als u dat nog niet hebt gedaan.</span><span class="sxs-lookup"><span data-stu-id="529b2-214">Enable office location network connectivity visibility if you have not already done so.</span></span> <span data-ttu-id="529b2-215">U wilt vaststellen welke kantoren worden beïnvloed door slechte netwerkconnectiviteit die van invloed is op SharePoint en manieren vinden om de netwerkperimeter te verbeteren voor beide kantoren die de gebruikers met het Microsoft-netwerk verbinden.</span><span class="sxs-lookup"><span data-stu-id="529b2-215">You want to identify which offices are impacted by poor network connectivity that is impacting SharePoint and find ways to improve the network perimeter at each that connects the users to Microsoft's network.</span></span>

## <a name="related-topics"></a><span data-ttu-id="529b2-216">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="529b2-216">Related topics</span></span>

[<span data-ttu-id="529b2-217">Netwerkconnectiviteit in het Microsoft 365-beheercentrum (preview)</span><span class="sxs-lookup"><span data-stu-id="529b2-217">Network connectivity in the Microsoft 365 Admin Center (preview)</span></span>](office-365-network-mac-perf-overview.md)

[<span data-ttu-id="529b2-218">Evaluatie van het Microsoft 365-netwerk (preview)</span><span class="sxs-lookup"><span data-stu-id="529b2-218">Microsoft 365 network assessment (preview)</span></span>](office-365-network-mac-perf-score.md)

[<span data-ttu-id="529b2-219">Testhulpmiddel voor Microsoft 365-netwerkconnectiviteit (preview)</span><span class="sxs-lookup"><span data-stu-id="529b2-219">Microsoft 365 network connectivity test tool (preview)</span></span>](office-365-network-mac-perf-onboarding-tool.md)

[<span data-ttu-id="529b2-220">Microsoft 365 Network Connectivity Location Services (preview)</span><span class="sxs-lookup"><span data-stu-id="529b2-220">Microsoft 365 Network Connectivity Location Services (preview)</span></span>](office-365-network-mac-location-services.md)
