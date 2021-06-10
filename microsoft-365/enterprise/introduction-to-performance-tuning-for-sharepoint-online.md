---
title: Inleiding tot prestatieafstemming voor SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/22/2018
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid: SPO160
ms.assetid: 81c4be5f-327e-435d-a568-526d68cffef0
description: In dit artikel wordt uitgelegd welke specifieke aspecten u moet overwegen bij het ontwerpen van pagina's voor de beste prestaties in SharePoint Online.
ms.openlocfilehash: 6f40243c9d6a1657b6716a071288f5b4fb018164
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909736"
---
# <a name="introduction-to-performance-tuning-for-sharepoint-online"></a><span data-ttu-id="08c0e-103">Inleiding tot prestatieafstemming voor SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="08c0e-103">Introduction to performance tuning for SharePoint Online</span></span>

<span data-ttu-id="08c0e-104">In dit artikel wordt uitgelegd welke specifieke aspecten u moet overwegen bij het ontwerpen van pagina's voor de beste prestaties in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="08c0e-104">This article explains what specific aspects you need to consider when designing pages for best performance in SharePoint Online.</span></span>
     
## <a name="sharepoint-online-metrics"></a><span data-ttu-id="08c0e-105">SharePoint Onlinegegevens</span><span class="sxs-lookup"><span data-stu-id="08c0e-105">SharePoint Online metrics</span></span>

<span data-ttu-id="08c0e-106">De volgende algemene statistieken voor SharePoint Online bieden gegevens over prestaties in de echte wereld:</span><span class="sxs-lookup"><span data-stu-id="08c0e-106">The following broad metrics for SharePoint Online provide real world data about performance:</span></span>
  
- <span data-ttu-id="08c0e-107">Hoe snel pagina's worden geladen</span><span class="sxs-lookup"><span data-stu-id="08c0e-107">How fast pages load</span></span>
    
- <span data-ttu-id="08c0e-108">Hoeveel retourreizen per pagina zijn vereist</span><span class="sxs-lookup"><span data-stu-id="08c0e-108">How many round trips required per page</span></span>
    
- <span data-ttu-id="08c0e-109">Problemen met de service</span><span class="sxs-lookup"><span data-stu-id="08c0e-109">Issues with the service</span></span>
    
- <span data-ttu-id="08c0e-110">Andere dingen die prestatiedegradatie veroorzaken</span><span class="sxs-lookup"><span data-stu-id="08c0e-110">Other things that cause performance degradation</span></span>
    
### <a name="conclusions-reached-because-of-the-data"></a><span data-ttu-id="08c0e-111">Conclusies die zijn bereikt vanwege de gegevens</span><span class="sxs-lookup"><span data-stu-id="08c0e-111">Conclusions reached because of the data</span></span>

<span data-ttu-id="08c0e-112">De gegevens vertellen ons:</span><span class="sxs-lookup"><span data-stu-id="08c0e-112">The data tells us:</span></span>
  
- <span data-ttu-id="08c0e-113">De meeste pagina's presteren goed op SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="08c0e-113">Most of the pages perform well on SharePoint Online.</span></span>
    
- <span data-ttu-id="08c0e-114">Niet-aangepaste pagina's worden zeer snel geladen.</span><span class="sxs-lookup"><span data-stu-id="08c0e-114">Non-customized pages load very quickly.</span></span>
    
- <span data-ttu-id="08c0e-115">OneDrive voor Bedrijven, teamsites en systeempagina's, zoals _layouts, zijn allemaal snel te laden.</span><span class="sxs-lookup"><span data-stu-id="08c0e-115">OneDrive for Business, team sites and system pages, such as _layouts, etc., are all quick to load.</span></span>
    
- <span data-ttu-id="08c0e-116">De traagste 1% van SharePoint onlinepagina's duurt meer dan 5.000 milliseconden om te laden.</span><span class="sxs-lookup"><span data-stu-id="08c0e-116">The slowest 1% of SharePoint Online pages take more than 5,000 milliseconds to load.</span></span>
    
<span data-ttu-id="08c0e-117">Een eenvoudige benchmarktest die u kunt gebruiken, is het meten van de prestaties door de laadtijd van uw eigen portal te vergelijken met de laadtijd van de startpagina van OneDrive voor Bedrijven omdat er weinig aangepaste functies worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="08c0e-117">One simple benchmark test you can use would be to measure performance by comparing the load time of your own portal against the load time of the OneDrive for Business home page as it uses few customized features.</span></span> <span data-ttu-id="08c0e-118">Dit is vaak de eerste stap Die ondersteuning vraagt u om in te vullen bij het oplossen van problemen met netwerkprestaties.</span><span class="sxs-lookup"><span data-stu-id="08c0e-118">This will often be the first step Support will ask you to complete when troubleshooting network performance issues.</span></span>
  
## <a name="use-a-standard-user-account-when-checking-performance"></a><span data-ttu-id="08c0e-119">Een standaardgebruikersaccount gebruiken bij het controleren van de prestaties</span><span class="sxs-lookup"><span data-stu-id="08c0e-119">Use a standard user account when checking performance</span></span>

<span data-ttu-id="08c0e-120">Een beheerder van de siteverzameling, site-eigenaar, editor of inzender behoren tot extra beveiligingsgroepen, hebben extra machtigingen en hebben daarom extra elementen die SharePoint op een pagina worden geladen.</span><span class="sxs-lookup"><span data-stu-id="08c0e-120">A Site Collection Administrator, Site Owner, Editor, or Contributor belong to additional security groups, have additional permissions, and therefore have additional elements that SharePoint loads on a page.</span></span>
  
<span data-ttu-id="08c0e-121">Dit is van toepassing op SharePoint on-premises en SharePoint Online, maar in een on-premises scenario worden de verschillen niet zo gemakkelijk opgemerkt als in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="08c0e-121">This is applicable to SharePoint on-premises and SharePoint Online but in an on-premises scenario the differences will not be as easily noticed as in SharePoint Online.</span></span>
  
<span data-ttu-id="08c0e-122">Als u de prestaties van een pagina voor gebruikers correct wilt evalueren, moet u een standaardgebruikersaccount gebruiken om te voorkomen dat de ontwerpbesturingselementen en extra verkeer met betrekking tot beveiligingsgroepen worden geladen.</span><span class="sxs-lookup"><span data-stu-id="08c0e-122">In order to correctly evaluate how a page will perform for users, you should use a standard user account to avoid loading the authoring controls and additional traffic related to security groups.</span></span>
  
## <a name="connection-categories-for-performance-tuning"></a><span data-ttu-id="08c0e-123">Verbindingscategorieën voor prestatieafstemming</span><span class="sxs-lookup"><span data-stu-id="08c0e-123">Connection categories for performance tuning</span></span>

<span data-ttu-id="08c0e-124">U kunt de verbindingen tussen de server en de gebruiker categoriseren in drie hoofdonderdelen.</span><span class="sxs-lookup"><span data-stu-id="08c0e-124">You can categorize the connections between the server and the user into three main components.</span></span> <span data-ttu-id="08c0e-125">Houd hier rekening mee bij het ontwerpen SharePoint onlinepagina's voor inzicht in laadtijden.</span><span class="sxs-lookup"><span data-stu-id="08c0e-125">Consider these when designing SharePoint Online pages for insight into load times.</span></span>
  
- <span data-ttu-id="08c0e-126">**Server** De servers die microsoft host in datacenters.</span><span class="sxs-lookup"><span data-stu-id="08c0e-126">**Server** The servers that Microsoft hosts in datacenters.</span></span>
    
- <span data-ttu-id="08c0e-127">**Netwerk** Het Microsoft-netwerk, internet en uw on-premises netwerk tussen het datacenter en uw gebruikers.</span><span class="sxs-lookup"><span data-stu-id="08c0e-127">**Network** The Microsoft network, the Internet, and your on-premises network between the datacenter and your users.</span></span>
    
- <span data-ttu-id="08c0e-128">**Browser** Waar de pagina is geladen.</span><span class="sxs-lookup"><span data-stu-id="08c0e-128">**Browser** Where the page is loaded.</span></span>
    
<span data-ttu-id="08c0e-129">Binnen deze drie verbindingen zijn er meestal vijf redenen die 95% van de trage pagina's veroorzaken.</span><span class="sxs-lookup"><span data-stu-id="08c0e-129">Within these three connections there are typically five reasons that cause 95% of slow pages.</span></span> <span data-ttu-id="08c0e-130">Elk van deze redenen wordt besproken in dit artikel:</span><span class="sxs-lookup"><span data-stu-id="08c0e-130">Each of these reasons is discussed in this article:</span></span>
  
- <span data-ttu-id="08c0e-131">Navigatieproblemen</span><span class="sxs-lookup"><span data-stu-id="08c0e-131">Navigation issues</span></span>
    
- <span data-ttu-id="08c0e-132">Inhouds roll-up</span><span class="sxs-lookup"><span data-stu-id="08c0e-132">Content roll up</span></span>
    
- <span data-ttu-id="08c0e-133">Grote bestanden</span><span class="sxs-lookup"><span data-stu-id="08c0e-133">Large files</span></span>
    
- <span data-ttu-id="08c0e-134">Veel aanvragen voor de server</span><span class="sxs-lookup"><span data-stu-id="08c0e-134">Many requests to the server</span></span>
    
- <span data-ttu-id="08c0e-135">Webonderdeelverwerking</span><span class="sxs-lookup"><span data-stu-id="08c0e-135">Web Part processing</span></span>
    
### <a name="server-connection"></a><span data-ttu-id="08c0e-136">Serververbinding</span><span class="sxs-lookup"><span data-stu-id="08c0e-136">Server connection</span></span>

<span data-ttu-id="08c0e-137">Veel van de problemen die van invloed zijn op de prestaties SharePoint on-premises, zijn ook van toepassing op SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="08c0e-137">Many of the issues that affect performance with SharePoint on-premises also apply to SharePoint Online.</span></span>
  
<span data-ttu-id="08c0e-138">Zoals u zou verwachten, hebt u veel meer controle over hoe servers presteren met on-premises SharePoint.</span><span class="sxs-lookup"><span data-stu-id="08c0e-138">As you would expect, you have far more control over how servers perform with on-premises SharePoint.</span></span> <span data-ttu-id="08c0e-139">Met SharePoint Online zijn dingen iets anders.</span><span class="sxs-lookup"><span data-stu-id="08c0e-139">With SharePoint Online things are a little different.</span></span> <span data-ttu-id="08c0e-140">Hoe meer werk een server moet doen, hoe langer het duurt om een pagina weer te geven.</span><span class="sxs-lookup"><span data-stu-id="08c0e-140">The more work you make a server do, the longer it takes to render a page.</span></span> <span data-ttu-id="08c0e-141">Met SharePoint zijn complexe pagina's met meerdere webonderdelen de grootste boosdoener in dit opzicht.</span><span class="sxs-lookup"><span data-stu-id="08c0e-141">With SharePoint, the biggest culprit in this respect are complex pages with multiple web parts.</span></span>
  
<span data-ttu-id="08c0e-142">SharePoint Server on-premises</span><span class="sxs-lookup"><span data-stu-id="08c0e-142">SharePoint Server on-premises</span></span>
  
![Schermafbeelding van server on premises](../media/a8e9b646-cdff-4131-976a-b5f891da44ac.png)
  
<span data-ttu-id="08c0e-144">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="08c0e-144">SharePoint Online</span></span>
  
![Schermafbeelding van server online](../media/46b27ded-d8a4-4287-b3e0-2603a764b8f8.png)
  
<span data-ttu-id="08c0e-146">Met SharePoint Online kunnen bepaalde paginaaanvragen uiteindelijk meerdere servers bellen.</span><span class="sxs-lookup"><span data-stu-id="08c0e-146">With SharePoint Online, certain page requests may actually end up calling multiple servers.</span></span> <span data-ttu-id="08c0e-147">U kunt eindigen met een matrix met aanvragen tussen servers voor een afzonderlijke aanvraag.</span><span class="sxs-lookup"><span data-stu-id="08c0e-147">You could end up with a matrix of requests between servers for an individual request.</span></span> <span data-ttu-id="08c0e-148">Deze interacties zijn duur vanuit het laadperspectief van een pagina en zorgen ervoor dat de dingen traag worden.</span><span class="sxs-lookup"><span data-stu-id="08c0e-148">These interactions are expensive from a page load perspective and will make things slow.</span></span>
  
<span data-ttu-id="08c0e-149">Voorbeelden van deze server- en serverinteracties zijn:</span><span class="sxs-lookup"><span data-stu-id="08c0e-149">Examples of these server to server interactions are:</span></span>
  
- <span data-ttu-id="08c0e-150">Web to SQL Servers</span><span class="sxs-lookup"><span data-stu-id="08c0e-150">Web to SQL Servers</span></span>
    
- <span data-ttu-id="08c0e-151">Web-to-application servers</span><span class="sxs-lookup"><span data-stu-id="08c0e-151">Web to application servers</span></span>
    
<span data-ttu-id="08c0e-152">Het andere wat serverinteracties kan vertragen, is cache-missers.</span><span class="sxs-lookup"><span data-stu-id="08c0e-152">The other thing that can slow down server interactions is cache misses.</span></span> <span data-ttu-id="08c0e-153">In tegenstelling tot on-premises SharePoint, is de kans zeer klein dat u dezelfde server gebruikt voor een pagina die u eerder hebt bezocht. Dit maakt object caching verouderd.</span><span class="sxs-lookup"><span data-stu-id="08c0e-153">Unlike on-premises SharePoint, there is a very slim chance that you will hit the same server for a page that you have visited previously; this makes object caching obsolete.</span></span>
  
### <a name="network-connection"></a><span data-ttu-id="08c0e-154">Netwerkverbinding</span><span class="sxs-lookup"><span data-stu-id="08c0e-154">Network connection</span></span>

<span data-ttu-id="08c0e-155">Met on-premises SharePoint die geen gebruik maken van een WAN, kunt u een snelle verbinding tussen datacenter en eindgebruikers gebruiken.</span><span class="sxs-lookup"><span data-stu-id="08c0e-155">With on-premises SharePoint that doesn't make use of a WAN, you may use a high-speed connection between datacenter and end-users.</span></span> <span data-ttu-id="08c0e-156">Over het algemeen zijn de zaken eenvoudig te beheren vanuit een netwerkperspectief.</span><span class="sxs-lookup"><span data-stu-id="08c0e-156">Generally, things are easy to manage from a network perspective.</span></span>
  
<span data-ttu-id="08c0e-157">Met SharePoint Online zijn er nog een paar factoren waar u rekening mee moet houden. bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="08c0e-157">With SharePoint Online, there are a few more factors to consider; for example:</span></span>
  
- <span data-ttu-id="08c0e-158">Het Microsoft-netwerk</span><span class="sxs-lookup"><span data-stu-id="08c0e-158">The Microsoft network</span></span>
    
- <span data-ttu-id="08c0e-159">The Internet</span><span class="sxs-lookup"><span data-stu-id="08c0e-159">The Internet</span></span>
    
- <span data-ttu-id="08c0e-160">De isp</span><span class="sxs-lookup"><span data-stu-id="08c0e-160">The ISP</span></span>
    
<span data-ttu-id="08c0e-161">Ongeacht welke versie van SharePoint (en welk netwerk) u gebruikt, zijn de volgende zaken waardoor het netwerk meestal bezet is:</span><span class="sxs-lookup"><span data-stu-id="08c0e-161">Regardless of which version of SharePoint (and which network) you are using, things that will typically cause the network to be busy include:</span></span>
  
- <span data-ttu-id="08c0e-162">Grote laadvermogen</span><span class="sxs-lookup"><span data-stu-id="08c0e-162">Large payload</span></span>
    
- <span data-ttu-id="08c0e-163">Veel bestanden</span><span class="sxs-lookup"><span data-stu-id="08c0e-163">Many files</span></span>
    
- <span data-ttu-id="08c0e-164">Grote fysieke afstand tot de server</span><span class="sxs-lookup"><span data-stu-id="08c0e-164">Large physical distance to the server</span></span>
    
<span data-ttu-id="08c0e-165">Een functie die u kunt gebruiken in SharePoint Online is de Microsoft-CDN (Content Delivery Network).</span><span class="sxs-lookup"><span data-stu-id="08c0e-165">One feature that you can leverage in SharePoint Online is the Microsoft CDN (Content Delivery Network).</span></span> <span data-ttu-id="08c0e-166">Een CDN is in feite een gedistribueerde verzameling servers die is geïmplementeerd in meerdere datacenters.</span><span class="sxs-lookup"><span data-stu-id="08c0e-166">A CDN is basically a distributed collection of servers deployed across multiple datacenters.</span></span> <span data-ttu-id="08c0e-167">Met een CDN kunnen inhoud op pagina's worden gehost op een server dicht bij de client, zelfs als de client ver weg is van de oorspronkelijke SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="08c0e-167">With a CDN, content on pages can be hosted on a server close to the client even if the client is far away from the originating SharePoint Server.</span></span> <span data-ttu-id="08c0e-168">Microsoft gebruikt dit in de toekomst meer om lokale exemplaren op te slaan van pagina's die niet kunnen worden aangepast, bijvoorbeeld de startpagina SharePoint onlinebeheerder.</span><span class="sxs-lookup"><span data-stu-id="08c0e-168">Microsoft will be using this more in the future to store local instances of pages which cannot be customized, for example the SharePoint Online admin home page.</span></span> <span data-ttu-id="08c0e-169">Zie Inhoudsleveringsnetwerken voor meer informatie over [CDN's.](content-delivery-networks.md)</span><span class="sxs-lookup"><span data-stu-id="08c0e-169">For more information about CDNs, see [Content delivery networks](content-delivery-networks.md).</span></span>
  
<span data-ttu-id="08c0e-170">Iets waar u rekening mee moet houden, maar waar u mogelijk niet veel aan kunt doen, is de verbindingssnelheid van uw internetprovider.</span><span class="sxs-lookup"><span data-stu-id="08c0e-170">Something that you need to be aware of but may not be able to do much about is the connection speed of your ISP.</span></span> <span data-ttu-id="08c0e-171">Met een eenvoudig snelheidstestprogramma ziet u de verbindingssnelheid.</span><span class="sxs-lookup"><span data-stu-id="08c0e-171">A simple speed test tool will tell you the connection speed.</span></span>
  
### <a name="browser-connection"></a><span data-ttu-id="08c0e-172">Browserverbinding</span><span class="sxs-lookup"><span data-stu-id="08c0e-172">Browser connection</span></span>

<span data-ttu-id="08c0e-173">Er zijn een paar factoren waar u rekening mee moet houden met webbrowsers vanuit prestatieperspectief.</span><span class="sxs-lookup"><span data-stu-id="08c0e-173">There are a few factors to consider with web browsers from a performance perspective.</span></span>
  
<span data-ttu-id="08c0e-174">Het bezoeken van complexe pagina's is van invloed op de prestaties.</span><span class="sxs-lookup"><span data-stu-id="08c0e-174">Visiting complex pages will affect performance.</span></span> <span data-ttu-id="08c0e-175">De meeste browsers hebben slechts een kleine cache (ongeveer 90 MB), terwijl de gemiddelde webpagina meestal rond de 1,6 MB ligt.</span><span class="sxs-lookup"><span data-stu-id="08c0e-175">Most browsers only have a small cache (around 90MB), while the average web page is typically around 1.6MB.</span></span> <span data-ttu-id="08c0e-176">Dit duurt niet lang om te wennen.</span><span class="sxs-lookup"><span data-stu-id="08c0e-176">This doesn't take long to get used up.</span></span>
  
<span data-ttu-id="08c0e-177">Bandbreedte kan ook een probleem zijn.</span><span class="sxs-lookup"><span data-stu-id="08c0e-177">Bandwidth may also be an issue.</span></span> <span data-ttu-id="08c0e-178">Als een gebruiker bijvoorbeeld video's bekijkt in een andere sessie, is dit van invloed op de prestaties van uw SharePoint pagina.</span><span class="sxs-lookup"><span data-stu-id="08c0e-178">For example, if a user is watching videos in another session, this will affect the performance of your SharePoint page.</span></span> <span data-ttu-id="08c0e-179">Hoewel u niet kunt voorkomen dat gebruikers media streamen, kunt u bepalen hoe een pagina wordt geladen voor gebruikers.</span><span class="sxs-lookup"><span data-stu-id="08c0e-179">While you can't prevent users from streaming media, you can control the way a page will load for users.</span></span>
  
<span data-ttu-id="08c0e-180">Bekijk de volgende artikelen voor verschillende SharePoint online paginaaanpassingstechnieken en andere best practices om u te helpen optimale prestaties te bereiken.</span><span class="sxs-lookup"><span data-stu-id="08c0e-180">Check out the following articles for different SharePoint Online page customization techniques and other best practices to help you achieve optimal performance.</span></span>
  
- [<span data-ttu-id="08c0e-181">Navigatieopties voor SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="08c0e-181">Navigation options for SharePoint Online</span></span>](navigation-options-for-sharepoint-online.md)
    
- [<span data-ttu-id="08c0e-182">Het hulpprogramma Paginadiagnose gebruiken voor SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="08c0e-182">Use the Page Diagnostics tool for SharePoint Online</span></span>](page-diagnostics-for-spo.md)
    
- [<span data-ttu-id="08c0e-183">Afbeeldingsoptimalisatie voor SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="08c0e-183">Image optimization for SharePoint Online</span></span>](image-optimization-for-sharepoint-online.md)
    
- [<span data-ttu-id="08c0e-184">Vertraging bij het laden van afbeeldingen en JavaScript in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="08c0e-184">Delay loading images and JavaScript in SharePoint Online</span></span>](delay-loading-images-and-javascript-in-sharepoint-online.md)
    
- [<span data-ttu-id="08c0e-185">Minificatie en bundeling in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="08c0e-185">Minification and bundling in SharePoint Online</span></span>](minification-and-bundling-in-sharepoint-online.md)
    
- [<span data-ttu-id="08c0e-186">De Office 365 Content Delivery Network (CDN) gebruiken met SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="08c0e-186">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)
    
- [<span data-ttu-id="08c0e-187">Webonderdeel Inhoud zoeken gebruiken in plaats van webonderdeel Inhoudsquery om de prestaties in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="08c0e-187">Using Content Search Web Part instead of Content Query Web Part to improve performance in SharePoint Online</span></span>](using-content-search-web-part-instead-of-content-query-web-part-to-improve-perfo.md)
    
- [<span data-ttu-id="08c0e-188">Capaciteitsplanning en belastingtest van SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="08c0e-188">Capacity planning and load testing SharePoint Online</span></span>](capacity-planning-and-load-testing-sharepoint-online.md)
    
- [<span data-ttu-id="08c0e-189">Prestatieproblemen diagnosticeren met SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="08c0e-189">Diagnosing performance issues with SharePoint Online</span></span>](diagnosing-performance-issues-with-sharepoint-online.md)
    
- [<span data-ttu-id="08c0e-190">De objectcache gebruiken met SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="08c0e-190">Using the object cache with SharePoint Online</span></span>](using-the-object-cache-with-sharepoint-online.md)
    
- [<span data-ttu-id="08c0e-191">How to: Voorkomen dat u wordt beperkt of geblokkeerd in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="08c0e-191">How to: Avoid getting throttled or blocked in SharePoint Online</span></span>](/sharepoint/dev/general-development/how-to-avoid-getting-throttled-or-blocked-in-sharepoint-online)
