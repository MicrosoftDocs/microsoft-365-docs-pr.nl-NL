---
title: Microsoft 365 Network Insights (preview)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/17/2020
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
ms.openlocfilehash: e3730704b6672c931b7538659a38f218e769dd0a
ms.sourcegitcommit: 7c0873d2a804f17697844fb13f1a100fabce86c4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962369"
---
# <a name="microsoft-365-network-insights-preview"></a><span data-ttu-id="18ea6-103">Microsoft 365 Network Insights (preview)</span><span class="sxs-lookup"><span data-stu-id="18ea6-103">Microsoft 365 Network Insights (preview)</span></span>

<span data-ttu-id="18ea6-104">**Netwerk inzichten** zijn prestatiegegevens die worden verzameld uit uw microsoft 365-Tenant en zijn alleen beschikbaar voor weergave door beheerders gebruikers in uw Tenant.</span><span class="sxs-lookup"><span data-stu-id="18ea6-104">**Network insights** are performance metrics collected from your Microsoft 365 tenant, and available to view only by administrative users in your tenant.</span></span> <span data-ttu-id="18ea6-105">Inzichten worden weergegeven in het Microsoft 365-Beheercentrum op <https://portal.microsoft.com/adminportal/home#/networkperformance> .</span><span class="sxs-lookup"><span data-stu-id="18ea6-105">Insights are displayed in the Microsoft 365 Admin Center at <https://portal.microsoft.com/adminportal/home#/networkperformance>.</span></span>

<span data-ttu-id="18ea6-106">Inzichten zijn bedoeld voor hulp bij het ontwerpen van netwerkverbindingen voor uw Office-locaties.</span><span class="sxs-lookup"><span data-stu-id="18ea6-106">Insights are intended to help in designing network perimeters for your office locations.</span></span> <span data-ttu-id="18ea6-107">Elk inzicht biedt u actuele informatie over de prestatie-eigenschappen voor een specifiek gemeenschappelijke probleem waarbij gebruikers toegang krijgen tot uw Tenant.</span><span class="sxs-lookup"><span data-stu-id="18ea6-107">Each insight provides live details about the performance characteristics for a specific common issue for each geographic location where users are accessing your tenant.</span></span>

<span data-ttu-id="18ea6-108">Er bestaan zes specifieke netwerk inzichten die voor elke kantoorlocatie kunnen worden weergegeven:</span><span class="sxs-lookup"><span data-stu-id="18ea6-108">There are six specific network insights that may be shown for each office location:</span></span>

- [<span data-ttu-id="18ea6-109">Backhauled netwerk uitgang</span><span class="sxs-lookup"><span data-stu-id="18ea6-109">Backhauled network egress</span></span>](#backhauled-network-egress)
- [<span data-ttu-id="18ea6-110">Betere prestaties vastgesteld voor klanten in de buurt</span><span class="sxs-lookup"><span data-stu-id="18ea6-110">Better performance detected for customers near you</span></span>](#better-performance-detected-for-customers-near-you)
- [<span data-ttu-id="18ea6-111">Het gebruik van een niet-optimale Exchange Online-service-voor deur</span><span class="sxs-lookup"><span data-stu-id="18ea6-111">Use of a non-optimal Exchange Online service front door</span></span>](#use-of-a-non-optimal-exchange-online-service-front-door)
- [<span data-ttu-id="18ea6-112">Het gebruik van een niet-optimale SharePoint Online-service front deur</span><span class="sxs-lookup"><span data-stu-id="18ea6-112">Use of a non-optimal SharePoint Online service front door</span></span>](#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [<span data-ttu-id="18ea6-113">Lage downloadsnelheid van SharePoint-voor deur</span><span class="sxs-lookup"><span data-stu-id="18ea6-113">Low download speed from SharePoint front door</span></span>](#low-download-speed-from-sharepoint-front-door)
- [<span data-ttu-id="18ea6-114">Gebruikers van China optimale netwerk uitgang</span><span class="sxs-lookup"><span data-stu-id="18ea6-114">China user optimal network egress</span></span>](#china-user-optimal-network-egress)

<span data-ttu-id="18ea6-115">Er zijn twee netwerk inzichten op tenantniveau die kunnen worden weergegeven voor de Tenant.</span><span class="sxs-lookup"><span data-stu-id="18ea6-115">There are two tenant level network insights that may be shown for the tenant.</span></span> <span data-ttu-id="18ea6-116">Deze worden ook weergegeven op de Score pagina's van producvitivy:</span><span class="sxs-lookup"><span data-stu-id="18ea6-116">These also appear in the producvitivy score pages:</span></span>

- [<span data-ttu-id="18ea6-117">Gesamplinge verbindingen van Exchange beïnvloed door verbindingsproblemen</span><span class="sxs-lookup"><span data-stu-id="18ea6-117">Exchange sampled connections impacted by connectivity issues</span></span>](#exchange-sampled-connections-impacted-by-connectivity-issues)
- [<span data-ttu-id="18ea6-118">Gepipetteerde SharePoint-verbindingen beïnvloed door verbindingsproblemen</span><span class="sxs-lookup"><span data-stu-id="18ea6-118">SharePoint sampled connections impacted by connectivity issues</span></span>](#sharepoint-sampled-connections-impacted-by-connectivity-issues)

>[!IMPORTANT]
><span data-ttu-id="18ea6-119">Netwerk inzichten, prestatie aanbevelingen en beoordelingen in het Microsoft 365-Beheercentrum is momenteel in de preview-versie en is alleen beschikbaar voor Microsoft 365-tenants die zijn geregistreerd in het functie voorbeeldprogramma.</span><span class="sxs-lookup"><span data-stu-id="18ea6-119">Network insights, performance recommendations and assessments in the Microsoft 365 Admin Center is currently in preview status, and is only available for Microsoft 365 tenants that have been enrolled in the feature preview program.</span></span>

## <a name="backhauled-network-egress"></a><span data-ttu-id="18ea6-120">Backhauled netwerk uitgang</span><span class="sxs-lookup"><span data-stu-id="18ea6-120">Backhauled network egress</span></span>

<span data-ttu-id="18ea6-121">Dit inzicht wordt weergegeven als de Network Insights-service opspoort dat de afstand van een bepaalde gebruikerslocatie van de netwerk uitgang groter is dan 500 kilometers (800 kilometer), om aan te geven dat Microsoft 365-verkeer wordt backhauled naar een veelvoorkomende apparaat of proxy voor Internet Edge.</span><span class="sxs-lookup"><span data-stu-id="18ea6-121">This insight will be displayed if the network insights service detects that the distance from a given user location to the network egress is greater than 500 miles (800 kilometers), indicating that Microsoft 365 traffic is being backhauled to a common Internet edge device or proxy.</span></span>

<span data-ttu-id="18ea6-122">Dit inzicht wordt kort weergegeven als ' uitgaand ' in sommige samenvattings weergaven.</span><span class="sxs-lookup"><span data-stu-id="18ea6-122">This insight is abbreviated as "Egress" in some summary views.</span></span>

![Backhauled netwerk uitgang](../media/m365-mac-perf/m365-mac-perf-insights-detail-backhauled.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="18ea6-124">Wat betekent dit?</span><span class="sxs-lookup"><span data-stu-id="18ea6-124">What does this mean?</span></span>

<span data-ttu-id="18ea6-125">Hiermee wordt aangegeven dat de afstand tussen de kantoorlocatie en de uitgang van het netwerk langer is dan 500 km (800 kilometer).</span><span class="sxs-lookup"><span data-stu-id="18ea6-125">This identifies that the distance between the office location and the network egress is more than 500 miles (800 kilometers).</span></span> <span data-ttu-id="18ea6-126">De locatie van Office wordt aangeduid door een bemerkte locatie van de clientcomputer en de locatie van het netwerk.</span><span class="sxs-lookup"><span data-stu-id="18ea6-126">The office location is identified by an obfuscated client machine location and the network egress location is identified by using reverse IP Address to location databases.</span></span> <span data-ttu-id="18ea6-127">De kantoorlocatie is mogelijk onnauwkeurig als de Windows-locatie Services is uitgeschakeld op machines.</span><span class="sxs-lookup"><span data-stu-id="18ea6-127">The office location may be inaccurate if Windows Location Services is disabled on machines.</span></span> <span data-ttu-id="18ea6-128">De locatie van de netwerk uitgang is mogelijk onnauwkeurig als de informatie over de omgekeerde IP-adresdatabase onnauwkeurig is.</span><span class="sxs-lookup"><span data-stu-id="18ea6-128">The network egress location may be inaccurate if the reverse IP Address database information is inaccurate.</span></span>

<span data-ttu-id="18ea6-129">Details voor dit inzicht zijn de kantoorlocatie, het geschatte percentage van de totale Tenant gebruiker op de locatie, de huidige locatie van het netwerk, de relevantie van de uitzonderingslocatie, de afstand tussen de locatie en het huidige uitgangspunt, de datum waarop de voorwaarde voor het eerst is vastgesteld en de datum waarop de voorwaarde is opgelost.</span><span class="sxs-lookup"><span data-stu-id="18ea6-129">Details for this insight include the office location, estimated percentage of total tenant user at the location, the current network egress location, relevance of the egress location, the distance between the location and the current egress point, the date the condition was first detected, and the date the condition was resolved.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="18ea6-130">Wat moet ik doen?</span><span class="sxs-lookup"><span data-stu-id="18ea6-130">What should I do?</span></span>

<span data-ttu-id="18ea6-131">Om dit inzicht in te stellen, kunnen we de netwerk uitgang dichter bij de kantoorlocatie aanbevelen, zodat de verbinding optimaal kan worden gerouteerd naar het globale netwerk van Microsoft en de dichtstbijzijnde Microsoft 365-service.</span><span class="sxs-lookup"><span data-stu-id="18ea6-131">For this insight, we would recommend network egress closer to the office location so that connectivity can route optimally to Microsoft's global network and to the nearest Microsoft 365 service front door.</span></span> <span data-ttu-id="18ea6-132">Als u de netwerkverbinding met de gebruikers uitsluitte, kunnen de prestaties in de toekomst ook toenemen omdat Microsoft beide netwerk punten van aanwezigheid en de Microsoft 365-service voor de toekomst uitbreidt.</span><span class="sxs-lookup"><span data-stu-id="18ea6-132">Having close network egress to users office locations also allows for improved performance in the future as Microsoft expands both network points of presence and Microsoft 365 service front doors in the future.</span></span>

<span data-ttu-id="18ea6-133">Voor meer informatie over het oplossen van dit probleem, raadpleegt u [Netwerkverbindingen lokaal](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) uitzetten in de [netwerk verbindings beginselen van Office 365](microsoft-365-network-connectivity-principles.md).</span><span class="sxs-lookup"><span data-stu-id="18ea6-133">For more information about how to resolve this issue, see [Egress network connections locally](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) in [Office 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="better-performance-detected-for-customers-near-you"></a><span data-ttu-id="18ea6-134">Betere prestaties vastgesteld voor klanten in de buurt</span><span class="sxs-lookup"><span data-stu-id="18ea6-134">Better performance detected for customers near you</span></span>

<span data-ttu-id="18ea6-135">Dit inzicht wordt weergegeven als de Network Insights-service vaststelt dat een groot aantal klanten in uw metro gebied betere prestaties heeft dan de gebruikers in uw organisatie op deze locatie van Office.</span><span class="sxs-lookup"><span data-stu-id="18ea6-135">This insight will be displayed if the network insights service detects that a significant number of customers in your metro area have better performance than users in your organization at this office location.</span></span>

<span data-ttu-id="18ea6-136">Dit inzicht wordt afgekort als ' collega's ' in sommige samenvattings weergaven.</span><span class="sxs-lookup"><span data-stu-id="18ea6-136">This insight is abbreviated as "Peers" in some summary views.</span></span>

![Relatieve netwerkprestaties](../media/m365-mac-perf/m365-mac-perf-insights-detail-cust-near-you.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="18ea6-138">Wat betekent dit?</span><span class="sxs-lookup"><span data-stu-id="18ea6-138">What does this mean?</span></span>

<span data-ttu-id="18ea6-139">Dit inzicht bestudeert de totale prestaties van Microsoft 365-klanten in dezelfde stad als deze locatie van Office.</span><span class="sxs-lookup"><span data-stu-id="18ea6-139">This insight examines the aggregate performance of Microsoft 365 customers in the same city as this office location.</span></span> <span data-ttu-id="18ea6-140">Dit inzicht wordt weergegeven als de gemiddelde latentie van uw gebruikers 10% groter is dan de gemiddelde latentie van naburige tenants.</span><span class="sxs-lookup"><span data-stu-id="18ea6-140">This insight is displayed if the average latency of your users is 10% greater than the average latency of neighboring tenants.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="18ea6-141">Wat moet ik doen?</span><span class="sxs-lookup"><span data-stu-id="18ea6-141">What should I do?</span></span>

<span data-ttu-id="18ea6-142">Er kunnen verschillende redenen zijn voor deze voorwaarde, zoals latentie in uw bedrijfsnetwerk of INTERNETPROVIDER, knelpunten of architectuurontwerp problemen.</span><span class="sxs-lookup"><span data-stu-id="18ea6-142">There could be many reasons for this condition, including latency in your corporate network or ISP, bottlenecks, or architecture design issues.</span></span> <span data-ttu-id="18ea6-143">Bekijk de latentie tussen elke hop in de route tussen uw Office-netwerk en de huidige Microsoft 365-voor deur.</span><span class="sxs-lookup"><span data-stu-id="18ea6-143">Examine the latency between each hop in the route between your office network and the current Microsoft 365 front door.</span></span> <span data-ttu-id="18ea6-144">Zie voor meer informatie de [beginselen voor de netwerkverbindingen van Office 365](microsoft-365-network-connectivity-principles.md).</span><span class="sxs-lookup"><span data-stu-id="18ea6-144">For more information, see [Office 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="use-of-a-non-optimal-exchange-online-service-front-door"></a><span data-ttu-id="18ea6-145">Het gebruik van een niet-optimale Exchange Online-service-voor deur</span><span class="sxs-lookup"><span data-stu-id="18ea6-145">Use of a non-optimal Exchange Online service front door</span></span>

<span data-ttu-id="18ea6-146">Dit inzicht wordt weergegeven als de Network Insights-service detecteert dat gebruikers op een specifieke locatie geen verbinding maken met een optimale Exchange Online-service voor de voor deur.</span><span class="sxs-lookup"><span data-stu-id="18ea6-146">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to an optimal Exchange Online service front door.</span></span>

<span data-ttu-id="18ea6-147">Dit inzicht wordt verkort weergegeven als ' omleiding ' in sommige samenvattings weergaven.</span><span class="sxs-lookup"><span data-stu-id="18ea6-147">This insight is abbreviated as "Routing" in some summary views.</span></span>

![Niet-optimale EXO-voor deur](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-exo.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="18ea6-149">Wat betekent dit?</span><span class="sxs-lookup"><span data-stu-id="18ea6-149">What does this mean?</span></span>

<span data-ttu-id="18ea6-150">De omruilservice voor Exchange Online-Services die geschikt zijn voor gebruik vanaf de locatie van Office-locaties, biedt goede prestaties.</span><span class="sxs-lookup"><span data-stu-id="18ea6-150">We list Exchange Online service front doors which are suitable for use from the office location city with good performance.</span></span> <span data-ttu-id="18ea6-151">Als op de huidige test de front cover van de Exchange Online-service wordt gebruikt die niet in deze lijst voorkomt, dan noemen we deze aanbeveling.</span><span class="sxs-lookup"><span data-stu-id="18ea6-151">If the current test shows use of an Exchange Online service front door not on this list, then we call out this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="18ea6-152">Wat moet ik doen?</span><span class="sxs-lookup"><span data-stu-id="18ea6-152">What should I do?</span></span>

<span data-ttu-id="18ea6-153">Het gebruik van een niet-optimale omruil bare Exchange Online-service kan worden veroorzaakt door netwerk backhaul voordat het bedrijfsnetwerk wordt uitgevoerd, zodat het een lokale en rechtstreekse netwerk uitgang voor u aanbeveelt.</span><span class="sxs-lookup"><span data-stu-id="18ea6-153">Use of a non-optimal Exchange Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="18ea6-154">Dit kan ook worden veroorzaakt door het gebruik van een externe DNS recursieve resolver-server, maar het is raadzaam de DNS recursieve resolver server uit te lijnen met het netwerk uitgang.</span><span class="sxs-lookup"><span data-stu-id="18ea6-154">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="use-of-a-non-optimal-sharepoint-online-service-front-door"></a><span data-ttu-id="18ea6-155">Het gebruik van een niet-optimale SharePoint Online-service front deur</span><span class="sxs-lookup"><span data-stu-id="18ea6-155">Use of a non-optimal SharePoint Online service front door</span></span>

<span data-ttu-id="18ea6-156">Dit inzicht wordt weergegeven als de Network Insights-service detecteert dat gebruikers op een specifieke locatie geen verbinding maken met de dichtstbijzijnde SharePoint Online-service-deur.</span><span class="sxs-lookup"><span data-stu-id="18ea6-156">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to the closest SharePoint Online service front door.</span></span>

<span data-ttu-id="18ea6-157">Dit inzicht wordt afgekort als ' afd ' in sommige samenvattings weergaven.</span><span class="sxs-lookup"><span data-stu-id="18ea6-157">This insight is abbreviated as "Afd" in some summary views.</span></span>

![Niet-optimale SPO-voor deur](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-spo.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="18ea6-159">Wat betekent dit?</span><span class="sxs-lookup"><span data-stu-id="18ea6-159">What does this mean?</span></span>

<span data-ttu-id="18ea6-160">We identificeren de front cover van de SharePoint Online-service waarmee de test client verbinding maakt.</span><span class="sxs-lookup"><span data-stu-id="18ea6-160">We identify the SharePoint Online service front door that the test client is connecting to.</span></span> <span data-ttu-id="18ea6-161">Vervolgens gaan we naar de locatie van Office-locaties om te zien dat de front cover van de SharePoint Online-service voor die stad werd verwacht.</span><span class="sxs-lookup"><span data-stu-id="18ea6-161">Then for the office location city we compare that to the expected SharePoint Online service front door for that city.</span></span> <span data-ttu-id="18ea6-162">Als ze niet overeenkomen, maakt u hiervan een aanbeveling.</span><span class="sxs-lookup"><span data-stu-id="18ea6-162">If it doesn't match, then we make this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="18ea6-163">Wat moet ik doen?</span><span class="sxs-lookup"><span data-stu-id="18ea6-163">What should I do?</span></span>

<span data-ttu-id="18ea6-164">Het gebruik van een niet-optimale SharePoint Online-service voor de voor deur kan worden veroorzaakt door de netwerk backhaul voordat het bedrijfsnetwerk wordt uitgevoerd, zodat het lokale en rechtstreekse netwerk uitgang voor u adviseert.</span><span class="sxs-lookup"><span data-stu-id="18ea6-164">Use of a non-optimal SharePoint Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="18ea6-165">Dit kan ook worden veroorzaakt door het gebruik van een externe DNS recursieve resolver-server, maar het is raadzaam de DNS recursieve resolver server uit te lijnen met het netwerk uitgang.</span><span class="sxs-lookup"><span data-stu-id="18ea6-165">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="low-download-speed-from-sharepoint-front-door"></a><span data-ttu-id="18ea6-166">Lage downloadsnelheid van SharePoint-voor deur</span><span class="sxs-lookup"><span data-stu-id="18ea6-166">Low download speed from SharePoint front door</span></span>

<span data-ttu-id="18ea6-167">Dit inzicht wordt weergegeven als de Network Insights-service de bandbreedte tussen de specifieke kantoorlocatie en SharePoint Online lager is dan 1 MBps.</span><span class="sxs-lookup"><span data-stu-id="18ea6-167">This insight will be displayed if the network insights service detects that bandwidth between the specific office location and SharePoint Online is less than 1 MBps.</span></span>

<span data-ttu-id="18ea6-168">Dit inzicht wordt afgekort als ' doorvoer ' in sommige samenvattings weergaven.</span><span class="sxs-lookup"><span data-stu-id="18ea6-168">This insight is abbreviated as "Throughput" in some summary views.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="18ea6-169">Wat betekent dit?</span><span class="sxs-lookup"><span data-stu-id="18ea6-169">What does this mean?</span></span>

<span data-ttu-id="18ea6-170">De downloadsnelheid die een gebruiker uit de front-deur van SharePoint Online en de OneDrive voor bedrijven-service bevindt, wordt gemeten in megabytes per seconde (MBps).</span><span class="sxs-lookup"><span data-stu-id="18ea6-170">The download speed that a user can get from SharePoint Online and OneDrive for Business service front doors is measured in megabytes per second (MBps).</span></span> <span data-ttu-id="18ea6-171">Als deze waarde lager is dan 1 MBps, bieden we deze inzichten.</span><span class="sxs-lookup"><span data-stu-id="18ea6-171">If this value is less than 1 MBps then we provide this insight.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="18ea6-172">Wat moet ik doen?</span><span class="sxs-lookup"><span data-stu-id="18ea6-172">What should I do?</span></span>

<span data-ttu-id="18ea6-173">Om de downloadsnelheid te verbeteren, moet de bandbreedte wellicht toenemen.</span><span class="sxs-lookup"><span data-stu-id="18ea6-173">To improve download speeds, bandwidth may need to be increased.</span></span> <span data-ttu-id="18ea6-174">Het kan ook zijn dat de netwerkcongestie tussen gebruikers computers op de kantoorlocatie en de SharePoint Online-service-klep.</span><span class="sxs-lookup"><span data-stu-id="18ea6-174">Alternatively, there may be network congestion between user machines at the office location and the SharePoint Online service front door.</span></span> <span data-ttu-id="18ea6-175">Dit wordt ook wel congestie verlies genoemd en de beschikbare downloadsnelheid voor gebruikers wordt beperkt, zelfs als de voldoende bandbreedte beschikbaar is.</span><span class="sxs-lookup"><span data-stu-id="18ea6-175">This is sometimes called congestive loss and it restricts the download speed available to users even if sufficient bandwidth is available.</span></span>

## <a name="china-user-optimal-network-egress"></a><span data-ttu-id="18ea6-176">Gebruikers van China optimale netwerk uitgang</span><span class="sxs-lookup"><span data-stu-id="18ea6-176">China user optimal network egress</span></span>

<span data-ttu-id="18ea6-177">Dit inzicht wordt weergegeven als uw organisatie gebruikers heeft in China die verbinding maken met uw Microsoft 365-Tenant in andere geografische locaties.</span><span class="sxs-lookup"><span data-stu-id="18ea6-177">This insight will be displayed if your organization has users in China connecting to your Microsoft 365 tenant in other geographic locations.</span></span> 

### <a name="what-does-this-mean"></a><span data-ttu-id="18ea6-178">Wat betekent dit?</span><span class="sxs-lookup"><span data-stu-id="18ea6-178">What does this mean?</span></span>

<span data-ttu-id="18ea6-179">Als uw organisatie beschikt over een persoonlijke WAN-verbinding, wordt u aangeraden een netwerkwan-circuit te configureren op uw kantoorlocaties in China met een netwerk uitgang op Internet op een van de volgende locaties:</span><span class="sxs-lookup"><span data-stu-id="18ea6-179">If your organization has private WAN connectivity, we recommend configuring a network WAN circuit from your office locations in China that has network egress to the Internet in any of the following locations:</span></span>

- <span data-ttu-id="18ea6-180">Hongkong</span><span class="sxs-lookup"><span data-stu-id="18ea6-180">Hong Kong</span></span>
- <span data-ttu-id="18ea6-181">Japan </span><span class="sxs-lookup"><span data-stu-id="18ea6-181">Japan</span></span>
- <span data-ttu-id="18ea6-182">Taiwan</span><span class="sxs-lookup"><span data-stu-id="18ea6-182">Taiwan</span></span>
- <span data-ttu-id="18ea6-183">Zuid-Korea</span><span class="sxs-lookup"><span data-stu-id="18ea6-183">South Korea</span></span>
- <span data-ttu-id="18ea6-184">Singapore</span><span class="sxs-lookup"><span data-stu-id="18ea6-184">Singapore</span></span>
- <span data-ttu-id="18ea6-185">Maleisië </span><span class="sxs-lookup"><span data-stu-id="18ea6-185">Malaysia</span></span>

<span data-ttu-id="18ea6-186">Verder wegteren van gebruikers van gebruikers van deze locaties reduceren de prestaties en het uitgangs niveau in China kan leiden tot hoge latentie en connectiviteitsproblemen vanwege een oplopende verbinding.</span><span class="sxs-lookup"><span data-stu-id="18ea6-186">Internet egress further away from users than these locations will reduce performance, and egress in China may cause high latency and connectivity issues due to cross-border congestion.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="18ea6-187">Wat moet ik doen?</span><span class="sxs-lookup"><span data-stu-id="18ea6-187">What should I do?</span></span>

<span data-ttu-id="18ea6-188">Zie voor meer informatie over het beperken van de prestaties van dit inzicht de prestatie [optimalisering van Office 365 voor gebruikers van China](microsoft-365-networking-china.md).</span><span class="sxs-lookup"><span data-stu-id="18ea6-188">For more information about how to mitigate performance issues related to this insight, see [Office 365 global tenant performance optimization for China users](microsoft-365-networking-china.md).</span></span>

## <a name="exchange-sampled-connections-impacted-by-connectivity-issues"></a><span data-ttu-id="18ea6-189">Gesamplinge verbindingen van Exchange beïnvloed door verbindingsproblemen</span><span class="sxs-lookup"><span data-stu-id="18ea6-189">Exchange sampled connections impacted by connectivity issues</span></span>

<span data-ttu-id="18ea6-190">Dit inzicht zal aangeven wanneer 50% of meer van de bemonsterde verbindingen worden beïnvloed.</span><span class="sxs-lookup"><span data-stu-id="18ea6-190">This insight will show when 50% or more of the sampled connections are impacted.</span></span> <span data-ttu-id="18ea6-191">Het effect wordt bepaald door de proef van Exchange onder 60% voor elk voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="18ea6-191">The impact is defined by the Exchange assessment being below 60% for each sample.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="18ea6-192">Wat betekent dit?</span><span class="sxs-lookup"><span data-stu-id="18ea6-192">What does this mean?</span></span>

<span data-ttu-id="18ea6-193">Het is een aanwijzing dat het merendeel van de gebruikers problemen met de gebruikerservaring opneemt met Outlook waarmee verbinding wordt gemaakt met Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="18ea6-193">It is an indication that the majority of your users are likely to be experiencing user experience issues with Outlook connecting to Exchange Online.</span></span> <span data-ttu-id="18ea6-194">Het percentage van de gepaarde steekproeven staat voor het percentage van gebruikers dat onder 60 punten wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="18ea6-194">The percentage of samples likely represents the percentage of users who show below 60 points.</span></span>  

### <a name="what-should-i-do"></a><span data-ttu-id="18ea6-195">Wat moet ik doen?</span><span class="sxs-lookup"><span data-stu-id="18ea6-195">What should I do?</span></span>

<span data-ttu-id="18ea6-196">De netwerklocatie van de Office-locatie voor netwerktoegang inschakelen als u dit nog niet hebt gedaan.</span><span class="sxs-lookup"><span data-stu-id="18ea6-196">Enable office location network connectivity visibility if you have not already done so.</span></span> <span data-ttu-id="18ea6-197">U wilt weten welke kantoren zijn impactred door slechte netwerkconnectiviteit, wat van invloed is op Exchange en manieren om de netwerkverbinding te verbeteren, zodat de netwerkverbindingen van de gebruikers met de gebruikers van het Microsoft-netwerk zijn verbonden.</span><span class="sxs-lookup"><span data-stu-id="18ea6-197">You want to identify which offices are impactred by poor network connectivity that is impacting Exchange and find ways to improve the network perimeter at each that connects the users to Microsoft's network.</span></span>

## <a name="sharepoint-sampled-connections-impacted-by-connectivity-issues"></a><span data-ttu-id="18ea6-198">Gepipetteerde SharePoint-verbindingen beïnvloed door verbindingsproblemen</span><span class="sxs-lookup"><span data-stu-id="18ea6-198">SharePoint sampled connections impacted by connectivity issues</span></span>

<span data-ttu-id="18ea6-199">Dit inzicht zal aangeven wanneer 50% of meer van de bemonsterde verbindingen worden beïnvloed.</span><span class="sxs-lookup"><span data-stu-id="18ea6-199">This insight will show when 50% or more of the sampled connections are impacted.</span></span> <span data-ttu-id="18ea6-200">Het effect wordt bepaald door de SharePoint-beoordeling onder 40% voor elk voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="18ea6-200">The impact is defined by the SharePoint assessment being below 40% for each sample.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="18ea6-201">Wat betekent dit?</span><span class="sxs-lookup"><span data-stu-id="18ea6-201">What does this mean?</span></span>

<span data-ttu-id="18ea6-202">Het is een aanwijzing dat het merendeel van de gebruikers problemen met de gebruikerservaring met SharePoint en OneDrive ondervindt.</span><span class="sxs-lookup"><span data-stu-id="18ea6-202">It is an indication that the majority of your users are likely to be experiencing user experience issues with SharePoint and OneDrive.</span></span> <span data-ttu-id="18ea6-203">Het percentage van de gepaarde steekproeven staat voor het percentage van gebruikers dat onder 40 punten wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="18ea6-203">The percentage of samples likely represents the percentage of users who show below 40 points.</span></span>  

### <a name="what-should-i-do"></a><span data-ttu-id="18ea6-204">Wat moet ik doen?</span><span class="sxs-lookup"><span data-stu-id="18ea6-204">What should I do?</span></span>

<span data-ttu-id="18ea6-205">De netwerklocatie van de Office-locatie voor netwerktoegang inschakelen als u dit nog niet hebt gedaan.</span><span class="sxs-lookup"><span data-stu-id="18ea6-205">Enable office location network connectivity visibility if you have not already done so.</span></span> <span data-ttu-id="18ea6-206">U wilt weten welke kantoren zijn impactred door slechte netwerkconnectiviteit, wat van invloed is op SharePoint en manieren om de netwerkverbinding te verbeteren waarmee de gebruikers worden verbonden met de gebruikers van het Microsoft-netwerk.</span><span class="sxs-lookup"><span data-stu-id="18ea6-206">You want to identify which offices are impactred by poor network connectivity that is impacting SharePoint and find ways to improve the network perimeter at each that connects the users to Microsoft's network.</span></span>

## <a name="related-topics"></a><span data-ttu-id="18ea6-207">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="18ea6-207">Related topics</span></span>

[<span data-ttu-id="18ea6-208">Netwerkverbinding in het Microsoft 365-Beheercentrum (preview)</span><span class="sxs-lookup"><span data-stu-id="18ea6-208">Network connectivity in the Microsoft 365 Admin Center (preview)</span></span>](office-365-network-mac-perf-overview.md)

[<span data-ttu-id="18ea6-209">Microsoft 365-netwerk beoordeling (preview)</span><span class="sxs-lookup"><span data-stu-id="18ea6-209">Microsoft 365 network assessment (preview)</span></span>](office-365-network-mac-perf-score.md)

[<span data-ttu-id="18ea6-210">Microsoft 365 connectiviteitstest in het M365-Beheercentrum (preview)</span><span class="sxs-lookup"><span data-stu-id="18ea6-210">Microsoft 365 connectivity test in the M365 Admin Center (preview)</span></span>](office-365-network-mac-perf-onboarding-tool.md)

[<span data-ttu-id="18ea6-211">Locatie Services voor Microsoft 365-netwerkconnectiviteit</span><span class="sxs-lookup"><span data-stu-id="18ea6-211">Microsoft 365 Network Connectivity Location Services (preview)</span></span>](office-365-network-mac-location-services.md)
