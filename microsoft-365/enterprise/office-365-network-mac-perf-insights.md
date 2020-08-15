---
title: Microsoft 365 Network Insights (preview)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 04/21/2020
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
ms.openlocfilehash: b30af89d480383fdc9011d24409e3b418339c70b
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689233"
---
# <a name="microsoft-365-network-insights-preview"></a><span data-ttu-id="556a6-103">Microsoft 365 Network Insights (preview)</span><span class="sxs-lookup"><span data-stu-id="556a6-103">Microsoft 365 Network Insights (preview)</span></span>

<span data-ttu-id="556a6-104">**Netwerk inzichten** zijn gegevens van een dynamische prestaties die zijn verzameld via uw microsoft 365-Tenant en die alleen kunnen worden weergegeven door gebruikers van beheerders in uw Tenant.</span><span class="sxs-lookup"><span data-stu-id="556a6-104">**Network insights** are live performance metrics collected from your Microsoft 365 tenant, and available to view only by administrative users in your tenant.</span></span> <span data-ttu-id="556a6-105">Inzichten worden weergegeven in het Microsoft 365-Beheercentrum op <https://portal.microsoft.com/adminportal/home#/networkperformance> .</span><span class="sxs-lookup"><span data-stu-id="556a6-105">Insights are displayed in the Microsoft 365 Admin Center at <https://portal.microsoft.com/adminportal/home#/networkperformance>.</span></span>

<span data-ttu-id="556a6-106">Inzichten zijn bedoeld voor hulp bij het ontwerpen van netwerkverbindingen voor uw Office-locaties.</span><span class="sxs-lookup"><span data-stu-id="556a6-106">Insights are intended to help in designing network perimeters for your office locations.</span></span> <span data-ttu-id="556a6-107">Elk inzicht biedt u actuele informatie over de prestatie-eigenschappen voor een specifiek gemeenschappelijke probleem waarbij gebruikers toegang krijgen tot uw Tenant.</span><span class="sxs-lookup"><span data-stu-id="556a6-107">Each insight provides live details about the performance characteristics for a specific common issue for each geographic location where users are accessing your tenant.</span></span>

<span data-ttu-id="556a6-108">Er zijn vijf specifieke netwerk inzichten die voor elke kantoorlocatie kunnen worden weergegeven:</span><span class="sxs-lookup"><span data-stu-id="556a6-108">There are five specific network insights that may be shown for each office location:</span></span>

- [<span data-ttu-id="556a6-109">Backhauled netwerk uitgang</span><span class="sxs-lookup"><span data-stu-id="556a6-109">Backhauled network egress</span></span>](#backhauled-network-egress)
- [<span data-ttu-id="556a6-110">Betere prestaties vastgesteld voor klanten in de buurt</span><span class="sxs-lookup"><span data-stu-id="556a6-110">Better performance detected for customers near you</span></span>](#better-performance-detected-for-customers-near-you)
- [<span data-ttu-id="556a6-111">Het gebruik van een niet-optimale Exchange Online-service-voor deur</span><span class="sxs-lookup"><span data-stu-id="556a6-111">Use of a non-optimal Exchange Online service front door</span></span>](#use-of-a-non-optimal-exchange-online-service-front-door)
- [<span data-ttu-id="556a6-112">Het gebruik van een niet-optimale SharePoint Online-service front deur</span><span class="sxs-lookup"><span data-stu-id="556a6-112">Use of a non-optimal SharePoint Online service front door</span></span>](#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [<span data-ttu-id="556a6-113">Lage downloadsnelheid van SharePoint-voor deur</span><span class="sxs-lookup"><span data-stu-id="556a6-113">Low download speed from SharePoint front door</span></span>](#low-download-speed-from-sharepoint-front-door)

>[!IMPORTANT]
><span data-ttu-id="556a6-114">Netwerk inzichten, prestatie aanbevelingen en beoordelingen in het Microsoft 365-Beheercentrum is momenteel in de preview-versie en is alleen beschikbaar voor Microsoft 365-tenants die zijn geregistreerd in het functie voorbeeldprogramma.</span><span class="sxs-lookup"><span data-stu-id="556a6-114">Network insights, performance recommendations and assessments in the Microsoft 365 Admin Center is currently in preview status, and is only available for Microsoft 365 tenants that have been enrolled in the feature preview program.</span></span>

## <a name="backhauled-network-egress"></a><span data-ttu-id="556a6-115">Backhauled netwerk uitgang</span><span class="sxs-lookup"><span data-stu-id="556a6-115">Backhauled network egress</span></span>

<span data-ttu-id="556a6-116">Dit inzicht wordt weergegeven als de Network Insights-service opspoort dat de afstand van een bepaalde gebruikerslocatie van de netwerk uitgang groter is dan 500 kilometers (800 kilometer), om aan te geven dat Microsoft 365-verkeer wordt backhauled naar een veelvoorkomende apparaat of proxy voor Internet Edge.</span><span class="sxs-lookup"><span data-stu-id="556a6-116">This insight will be displayed if the network insights service detects that the distance from a given user location to the network egress is greater than 500 miles (800 kilometers), indicating that Microsoft 365 traffic is being backhauled to a common Internet edge device or proxy.</span></span>

<span data-ttu-id="556a6-117">Dit inzicht wordt kort weergegeven als ' uitgaand ' in sommige samenvattings weergaven.</span><span class="sxs-lookup"><span data-stu-id="556a6-117">This insight is abbreviated as "Egress" in some summary views.</span></span>

![Backhauled netwerk uitgang](../media/m365-mac-perf/m365-mac-perf-insights-detail-backhauled.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="556a6-119">Wat betekent dit?</span><span class="sxs-lookup"><span data-stu-id="556a6-119">What does this mean?</span></span>

<span data-ttu-id="556a6-120">Hiermee wordt aangegeven dat de afstand tussen de kantoorlocatie en de uitgang van het netwerk langer is dan 500 km (800 kilometer).</span><span class="sxs-lookup"><span data-stu-id="556a6-120">This identifies that the distance between the office location and the network egress is more than 500 miles (800 kilometers).</span></span> <span data-ttu-id="556a6-121">De locatie van Office wordt aangeduid door een bemerkte locatie van de clientcomputer en de locatie van het netwerk.</span><span class="sxs-lookup"><span data-stu-id="556a6-121">The office location is identified by an obfuscated client machine location and the network egress location is identified by using reverse IP Address to location databases.</span></span> <span data-ttu-id="556a6-122">De kantoorlocatie is mogelijk onnauwkeurig als de Windows-locatie Services is uitgeschakeld op machines.</span><span class="sxs-lookup"><span data-stu-id="556a6-122">The office location may be inaccurate if Windows Location Services is disabled on machines.</span></span> <span data-ttu-id="556a6-123">De locatie van de netwerk uitgang is mogelijk onnauwkeurig als de informatie over de omgekeerde IP-adresdatabase onnauwkeurig is.</span><span class="sxs-lookup"><span data-stu-id="556a6-123">The network egress location may be inaccurate if the reverse IP Address database information is inaccurate.</span></span>

<span data-ttu-id="556a6-124">Details voor dit inzicht zijn de kantoorlocatie, het geschatte percentage van de totale Tenant gebruiker op de locatie, de huidige locatie van het netwerk, de relevantie van de uitzonderingslocatie, de afstand tussen de locatie en het huidige uitgangspunt, de datum waarop de voorwaarde voor het eerst is vastgesteld en de datum waarop de voorwaarde is opgelost.</span><span class="sxs-lookup"><span data-stu-id="556a6-124">Details for this insight include the office location, estimated percentage of total tenant user at the location, the current network egress location, relevance of the egress location, the distance between the location and the current egress point, the date the condition was first detected, and the date the condition was resolved.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="556a6-125">Wat moet ik doen?</span><span class="sxs-lookup"><span data-stu-id="556a6-125">What should I do?</span></span>

<span data-ttu-id="556a6-126">Om dit inzicht in te stellen, kunnen we de netwerk uitgang dichter bij de kantoorlocatie aanbevelen, zodat de verbinding optimaal kan worden gerouteerd naar het globale netwerk van Microsoft en de dichtstbijzijnde Microsoft 365-service.</span><span class="sxs-lookup"><span data-stu-id="556a6-126">For this insight, we would recommend network egress closer to the office location so that connectivity can route optimally to Microsoft's global network and to the nearest Microsoft 365 service front door.</span></span> <span data-ttu-id="556a6-127">Als u de netwerkverbinding met de gebruikers uitsluitte, kunnen de prestaties in de toekomst ook toenemen omdat Microsoft beide netwerk punten van aanwezigheid en de Microsoft 365-service voor de toekomst uitbreidt.</span><span class="sxs-lookup"><span data-stu-id="556a6-127">Having close network egress to users office locations also allows for improved performance in the future as Microsoft expands both network points of presence and Microsoft 365 service front doors in the future.</span></span>

<span data-ttu-id="556a6-128">Voor meer informatie over het oplossen van dit probleem, raadpleegt u [Netwerkverbindingen lokaal](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) uitzetten in de [netwerk verbindings beginselen van Office 365](microsoft-365-network-connectivity-principles.md).</span><span class="sxs-lookup"><span data-stu-id="556a6-128">For more information about how to resolve this issue, see [Egress network connections locally](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) in [Office 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="better-performance-detected-for-customers-near-you"></a><span data-ttu-id="556a6-129">Betere prestaties vastgesteld voor klanten in de buurt</span><span class="sxs-lookup"><span data-stu-id="556a6-129">Better performance detected for customers near you</span></span>

<span data-ttu-id="556a6-130">Dit inzicht wordt weergegeven als de Network Insights-service vaststelt dat een groot aantal klanten in uw metro gebied betere prestaties heeft dan de gebruikers in uw organisatie op deze locatie van Office.</span><span class="sxs-lookup"><span data-stu-id="556a6-130">This insight will be displayed if the network insights service detects that a significant number of customers in your metro area have better performance than users in your organization at this office location.</span></span>

<span data-ttu-id="556a6-131">Dit inzicht wordt afgekort als ' collega's ' in sommige samenvattings weergaven.</span><span class="sxs-lookup"><span data-stu-id="556a6-131">This insight is abbreviated as "Peers" in some summary views.</span></span>

![Relatieve netwerkprestaties](../media/m365-mac-perf/m365-mac-perf-insights-detail-cust-near-you.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="556a6-133">Wat betekent dit?</span><span class="sxs-lookup"><span data-stu-id="556a6-133">What does this mean?</span></span>

<span data-ttu-id="556a6-134">Dit inzicht bestudeert de totale prestaties van Microsoft 365-klanten in dezelfde stad als deze locatie van Office.</span><span class="sxs-lookup"><span data-stu-id="556a6-134">This insight examines the aggregate performance of Microsoft 365 customers in the same city as this office location.</span></span> <span data-ttu-id="556a6-135">Dit inzicht wordt weergegeven als de gemiddelde latentie van uw gebruikers 10% groter is dan de gemiddelde latentie van naburige tenants.</span><span class="sxs-lookup"><span data-stu-id="556a6-135">This insight is displayed if the average latency of your users is 10% greater than the average latency of neighboring tenants.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="556a6-136">Wat moet ik doen?</span><span class="sxs-lookup"><span data-stu-id="556a6-136">What should I do?</span></span>

<span data-ttu-id="556a6-137">Er kunnen verschillende redenen zijn voor deze voorwaarde, zoals latentie in uw bedrijfsnetwerk of INTERNETPROVIDER, knelpunten of architectuurontwerp problemen.</span><span class="sxs-lookup"><span data-stu-id="556a6-137">There could be many reasons for this condition, including latency in your corporate network or ISP, bottlenecks, or architecture design issues.</span></span> <span data-ttu-id="556a6-138">Bekijk de latentie tussen elke hop in de route tussen uw Office-netwerk en de huidige Microsoft 365-voor deur.</span><span class="sxs-lookup"><span data-stu-id="556a6-138">Examine the latency between each hop in the route between your office network and the current Microsoft 365 front door.</span></span> <span data-ttu-id="556a6-139">Zie voor meer informatie de [beginselen voor de netwerkverbindingen van Office 365](microsoft-365-network-connectivity-principles.md).</span><span class="sxs-lookup"><span data-stu-id="556a6-139">For more information, see [Office 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="use-of-a-non-optimal-exchange-online-service-front-door"></a><span data-ttu-id="556a6-140">Het gebruik van een niet-optimale Exchange Online-service-voor deur</span><span class="sxs-lookup"><span data-stu-id="556a6-140">Use of a non-optimal Exchange Online service front door</span></span>

<span data-ttu-id="556a6-141">Dit inzicht wordt weergegeven als de Network Insights-service detecteert dat gebruikers op een specifieke locatie geen verbinding maken met een optimale Exchange Online-service voor de voor deur.</span><span class="sxs-lookup"><span data-stu-id="556a6-141">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to an optimal Exchange Online service front door.</span></span>

<span data-ttu-id="556a6-142">Dit inzicht wordt verkort weergegeven als ' omleiding ' in sommige samenvattings weergaven.</span><span class="sxs-lookup"><span data-stu-id="556a6-142">This insight is abbreviated as "Routing" in some summary views.</span></span>

![Niet-optimale voor deur](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-exo.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="556a6-144">Wat betekent dit?</span><span class="sxs-lookup"><span data-stu-id="556a6-144">What does this mean?</span></span>

<span data-ttu-id="556a6-145">De omruilservice voor Exchange Online-Services die geschikt zijn voor gebruik vanaf de locatie van Office-locaties, biedt goede prestaties.</span><span class="sxs-lookup"><span data-stu-id="556a6-145">We list Exchange Online service front doors which are suitable for use from the office location city with good performance.</span></span> <span data-ttu-id="556a6-146">Als op de huidige test de front cover van de Exchange Online-service wordt gebruikt die niet in deze lijst voorkomt, dan noemen we deze aanbeveling.</span><span class="sxs-lookup"><span data-stu-id="556a6-146">If the current test shows use of an Exchange Online service front door not on this list, then we call out this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="556a6-147">Wat moet ik doen?</span><span class="sxs-lookup"><span data-stu-id="556a6-147">What should I do?</span></span>

<span data-ttu-id="556a6-148">Het gebruik van een niet-optimale omruil bare Exchange Online-service kan worden veroorzaakt door netwerk backhaul voordat het bedrijfsnetwerk wordt uitgevoerd, zodat het een lokale en rechtstreekse netwerk uitgang voor u aanbeveelt.</span><span class="sxs-lookup"><span data-stu-id="556a6-148">Use of a non-optimal Exchange Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="556a6-149">Dit kan ook worden veroorzaakt door het gebruik van een externe DNS recursieve resolver-server, maar het is raadzaam de DNS recursieve resolver server uit te lijnen met het netwerk uitgang.</span><span class="sxs-lookup"><span data-stu-id="556a6-149">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="use-of-a-non-optimal-sharepoint-online-service-front-door"></a><span data-ttu-id="556a6-150">Het gebruik van een niet-optimale SharePoint Online-service front deur</span><span class="sxs-lookup"><span data-stu-id="556a6-150">Use of a non-optimal SharePoint Online service front door</span></span>

<span data-ttu-id="556a6-151">Dit inzicht wordt weergegeven als de Network Insights-service detecteert dat gebruikers op een specifieke locatie geen verbinding maken met de dichtstbijzijnde SharePoint Online-service-deur.</span><span class="sxs-lookup"><span data-stu-id="556a6-151">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to the closest SharePoint Online service front door.</span></span>

<span data-ttu-id="556a6-152">Dit inzicht wordt afgekort als ' afd ' in sommige samenvattings weergaven.</span><span class="sxs-lookup"><span data-stu-id="556a6-152">This insight is abbreviated as "Afd" in some summary views.</span></span>

![Niet-optimale voor deur](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-spo.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="556a6-154">Wat betekent dit?</span><span class="sxs-lookup"><span data-stu-id="556a6-154">What does this mean?</span></span>

<span data-ttu-id="556a6-155">We identificeren de front cover van de SharePoint Online-service waarmee de test client verbinding maakt.</span><span class="sxs-lookup"><span data-stu-id="556a6-155">We identify the SharePoint Online service front door that the test client is connecting to.</span></span> <span data-ttu-id="556a6-156">Vervolgens gaan we naar de locatie van Office-locaties om te zien dat de front cover van de SharePoint Online-service voor die stad werd verwacht.</span><span class="sxs-lookup"><span data-stu-id="556a6-156">Then for the office location city we compare that to the expected SharePoint Online service front door for that city.</span></span> <span data-ttu-id="556a6-157">Als ze niet overeenkomen, maakt u hiervan een aanbeveling.</span><span class="sxs-lookup"><span data-stu-id="556a6-157">If it doesn't match, then we make this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="556a6-158">Wat moet ik doen?</span><span class="sxs-lookup"><span data-stu-id="556a6-158">What should I do?</span></span>

<span data-ttu-id="556a6-159">Het gebruik van een niet-optimale SharePoint Online-service voor de voor deur kan worden veroorzaakt door de netwerk backhaul voordat het bedrijfsnetwerk wordt uitgevoerd, zodat het lokale en rechtstreekse netwerk uitgang voor u adviseert.</span><span class="sxs-lookup"><span data-stu-id="556a6-159">Use of a non-optimal SharePoint Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="556a6-160">Dit kan ook worden veroorzaakt door het gebruik van een externe DNS recursieve resolver-server, maar het is raadzaam de DNS recursieve resolver server uit te lijnen met het netwerk uitgang.</span><span class="sxs-lookup"><span data-stu-id="556a6-160">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="low-download-speed-from-sharepoint-front-door"></a><span data-ttu-id="556a6-161">Lage downloadsnelheid van SharePoint-voor deur</span><span class="sxs-lookup"><span data-stu-id="556a6-161">Low download speed from SharePoint front door</span></span>

<span data-ttu-id="556a6-162">Dit inzicht wordt weergegeven als de Network Insights-service de bandbreedte tussen de specifieke kantoorlocatie en SharePoint Online lager is dan 1 MBps.</span><span class="sxs-lookup"><span data-stu-id="556a6-162">This insight will be displayed if the network insights service detects that bandwidth between the specific office location and SharePoint Online is less than 1 MBps.</span></span>

<span data-ttu-id="556a6-163">Dit inzicht wordt afgekort als ' doorvoer ' in sommige samenvattings weergaven.</span><span class="sxs-lookup"><span data-stu-id="556a6-163">This insight is abbreviated as "Throughput" in some summary views.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="556a6-164">Wat betekent dit?</span><span class="sxs-lookup"><span data-stu-id="556a6-164">What does this mean?</span></span>

<span data-ttu-id="556a6-165">De downloadsnelheid die een gebruiker uit de front-deur van SharePoint Online en de OneDrive voor bedrijven-service bevindt, wordt gemeten in megabytes per seconde (MBps).</span><span class="sxs-lookup"><span data-stu-id="556a6-165">The download speed that a user can get from SharePoint Online and OneDrive for Business service front doors is measured in megabytes per second (MBps).</span></span> <span data-ttu-id="556a6-166">Als deze waarde lager is dan 1 MBps, bieden we deze inzichten.</span><span class="sxs-lookup"><span data-stu-id="556a6-166">If this value is less than 1 MBps then we provide this insight.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="556a6-167">Wat moet ik doen?</span><span class="sxs-lookup"><span data-stu-id="556a6-167">What should I do?</span></span>

<span data-ttu-id="556a6-168">Om de downloadsnelheid te verbeteren, moet de bandbreedte wellicht toenemen.</span><span class="sxs-lookup"><span data-stu-id="556a6-168">To improve download speeds, bandwidth may need to be increased.</span></span> <span data-ttu-id="556a6-169">Het kan ook zijn dat de netwerkcongestie tussen gebruikers computers op de kantoorlocatie en de SharePoint Online-service-klep.</span><span class="sxs-lookup"><span data-stu-id="556a6-169">Alternatively, there may be network congestion between user machines at the office location and the SharePoint Online service front door.</span></span> <span data-ttu-id="556a6-170">Dit wordt ook wel congestie verlies genoemd en de beschikbare downloadsnelheid voor gebruikers wordt beperkt, zelfs als de voldoende bandbreedte beschikbaar is.</span><span class="sxs-lookup"><span data-stu-id="556a6-170">This is sometimes called congestive loss and it restricts the download speed available to users even if sufficient bandwidth is available.</span></span>

## <a name="china-user-optimal-network-egress"></a><span data-ttu-id="556a6-171">Gebruikers van China optimale netwerk uitgang</span><span class="sxs-lookup"><span data-stu-id="556a6-171">China user optimal network egress</span></span>

<span data-ttu-id="556a6-172">Dit inzicht wordt weergegeven als uw organisatie gebruikers heeft in China die verbinding maken met uw Microsoft 365-Tenant in andere geografische locaties.</span><span class="sxs-lookup"><span data-stu-id="556a6-172">This insight will be displayed if your organization has users in China connecting to your Microsoft 365 tenant in other geographic locations.</span></span> 

### <a name="what-does-this-mean"></a><span data-ttu-id="556a6-173">Wat betekent dit?</span><span class="sxs-lookup"><span data-stu-id="556a6-173">What does this mean?</span></span>

<span data-ttu-id="556a6-174">Als uw organisatie beschikt over een persoonlijke WAN-verbinding, wordt u aangeraden een netwerkwan-circuit te configureren op uw kantoorlocaties in China met een netwerk uitgang op Internet op een van de volgende locaties:</span><span class="sxs-lookup"><span data-stu-id="556a6-174">If your organization has private WAN connectivity, we recommend configuring a network WAN circuit from your office locations in China that has network egress to the Internet in any of the following locations:</span></span>

- <span data-ttu-id="556a6-175">Hongkong</span><span class="sxs-lookup"><span data-stu-id="556a6-175">Hong Kong</span></span>
- <span data-ttu-id="556a6-176">Japan</span><span class="sxs-lookup"><span data-stu-id="556a6-176">Japan</span></span>
- <span data-ttu-id="556a6-177">Taiwan</span><span class="sxs-lookup"><span data-stu-id="556a6-177">Taiwan</span></span>
- <span data-ttu-id="556a6-178">Zuid-Korea</span><span class="sxs-lookup"><span data-stu-id="556a6-178">South Korea</span></span>
- <span data-ttu-id="556a6-179">Singapore</span><span class="sxs-lookup"><span data-stu-id="556a6-179">Singapore</span></span>
- <span data-ttu-id="556a6-180">Maleisië</span><span class="sxs-lookup"><span data-stu-id="556a6-180">Malaysia</span></span>

<span data-ttu-id="556a6-181">Verder wegteren van gebruikers van gebruikers van deze locaties reduceren de prestaties en het uitgangs niveau in China kan leiden tot hoge latentie en connectiviteitsproblemen vanwege een oplopende verbinding.</span><span class="sxs-lookup"><span data-stu-id="556a6-181">Internet egress further away from users than these locations will reduce performance, and egress in China may cause high latency and connectivity issues due to cross-border congestion.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="556a6-182">Wat moet ik doen?</span><span class="sxs-lookup"><span data-stu-id="556a6-182">What should I do?</span></span>

<span data-ttu-id="556a6-183">Zie voor meer informatie over het beperken van de prestaties van dit inzicht de prestatie [optimalisering van Office 365 voor gebruikers van China](microsoft-365-networking-china.md).</span><span class="sxs-lookup"><span data-stu-id="556a6-183">For more information about how to mitigate performance issues related to this insight, see [Office 365 global tenant performance optimization for China users](microsoft-365-networking-china.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="556a6-184">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="556a6-184">Related topics</span></span>

[<span data-ttu-id="556a6-185">Aanbevelingen voor netwerkprestaties in het Microsoft 365-Beheercentrum (preview)</span><span class="sxs-lookup"><span data-stu-id="556a6-185">Network performance recommendations in the Microsoft 365 Admin Center (preview)</span></span>](office-365-network-mac-perf-overview.md)

[<span data-ttu-id="556a6-186">Microsoft 365-netwerk beoordeling (preview)</span><span class="sxs-lookup"><span data-stu-id="556a6-186">Microsoft 365 network assessment (preview)</span></span>](office-365-network-mac-perf-score.md)

[<span data-ttu-id="556a6-187">Microsoft 365 connectiviteitstest in het M365-Beheercentrum (preview)</span><span class="sxs-lookup"><span data-stu-id="556a6-187">Microsoft 365 connectivity test in the M365 Admin Center (preview)</span></span>](office-365-network-mac-perf-onboarding-tool.md)

[<span data-ttu-id="556a6-188">Locatie Services voor Microsoft 365-netwerkconnectiviteit</span><span class="sxs-lookup"><span data-stu-id="556a6-188">Microsoft 365 Network Connectivity Location Services (preview)</span></span>](office-365-network-mac-location-services.md)
