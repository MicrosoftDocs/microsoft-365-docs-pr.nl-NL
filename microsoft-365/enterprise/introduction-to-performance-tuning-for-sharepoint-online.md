---
title: Inleiding tot het optimaliseren van de prestaties voor SharePoint Online
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
description: In dit artikel wordt uitgelegd welke specifieke aspecten u moet nemen bij het ontwerpen van pagina's voor de beste prestaties in SharePoint Online.
ms.openlocfilehash: d3a9dedbd5812774b81494af0f8defa5568f7dac
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689449"
---
# <a name="introduction-to-performance-tuning-for-sharepoint-online"></a><span data-ttu-id="d3f81-103">Inleiding tot het optimaliseren van de prestaties voor SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="d3f81-103">Introduction to performance tuning for SharePoint Online</span></span>

<span data-ttu-id="d3f81-104">In dit artikel wordt uitgelegd welke specifieke aspecten u moet nemen bij het ontwerpen van pagina's voor de beste prestaties in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="d3f81-104">This article explains what specific aspects you need to consider when designing pages for best performance in SharePoint Online.</span></span>
     
## <a name="sharepoint-online-metrics"></a><span data-ttu-id="d3f81-105">SharePoint Online-metrieken</span><span class="sxs-lookup"><span data-stu-id="d3f81-105">SharePoint Online metrics</span></span>

<span data-ttu-id="d3f81-106">De volgende algemene metrische gegevens voor SharePoint Online zorgen voor actuele wereld informatie over de prestaties:</span><span class="sxs-lookup"><span data-stu-id="d3f81-106">The following broad metrics for SharePoint Online provide real world data about performance:</span></span>
  
- <span data-ttu-id="d3f81-107">Hoe snel pagina's worden geladen</span><span class="sxs-lookup"><span data-stu-id="d3f81-107">How fast pages load</span></span>
    
- <span data-ttu-id="d3f81-108">Hoeveel reis uitnodigingen per pagina zijn vereist</span><span class="sxs-lookup"><span data-stu-id="d3f81-108">How many round trips required per page</span></span>
    
- <span data-ttu-id="d3f81-109">Problemen met de service</span><span class="sxs-lookup"><span data-stu-id="d3f81-109">Issues with the service</span></span>
    
- <span data-ttu-id="d3f81-110">Andere dingen die leiden tot verminderde prestaties</span><span class="sxs-lookup"><span data-stu-id="d3f81-110">Other things that cause performance degradation</span></span>
    
### <a name="conclusions-reached-because-of-the-data"></a><span data-ttu-id="d3f81-111">Conclusies op basis van de gegevens</span><span class="sxs-lookup"><span data-stu-id="d3f81-111">Conclusions reached because of the data</span></span>

<span data-ttu-id="d3f81-112">De gegevens melden ons:</span><span class="sxs-lookup"><span data-stu-id="d3f81-112">The data tells us:</span></span>
  
- <span data-ttu-id="d3f81-113">Het merendeel van de pagina's is geschikt voor SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="d3f81-113">Most of the pages perform well on SharePoint Online.</span></span>
    
- <span data-ttu-id="d3f81-114">Niet-aangepaste pagina's worden zeer snel geladen.</span><span class="sxs-lookup"><span data-stu-id="d3f81-114">Non-customized pages load very quickly.</span></span>
    
- <span data-ttu-id="d3f81-115">OneDrive voor bedrijven, team sites en systeem pagina's, zoals _layouts, enzovoort, worden allemaal snel geladen.</span><span class="sxs-lookup"><span data-stu-id="d3f81-115">OneDrive for Business, team sites and system pages, such as _layouts, etc., are all quick to load.</span></span>
    
- <span data-ttu-id="d3f81-116">De meest traagste 1% van de SharePoint Online-pagina's kost meer dan 5.000 milliseconden.</span><span class="sxs-lookup"><span data-stu-id="d3f81-116">The slowest 1% of SharePoint Online pages take more than 5,000 milliseconds to load.</span></span>
    
<span data-ttu-id="d3f81-117">Eén eenvoudige Bench type-test die u kunt gebruiken om de prestaties van uw eigen portal te vergelijken met de laadtijd van de startpagina van OneDrive voor bedrijven, aangezien deze gebruikmaakt van enkele aangepaste functies.</span><span class="sxs-lookup"><span data-stu-id="d3f81-117">One simple benchmark test you can use would be to measure performance by comparing the load time of your own portal against the load time of the OneDrive for Business home page as it uses few customized features.</span></span> <span data-ttu-id="d3f81-118">Dit is vaak de eerste stap die u moet uitvoeren wanneer u problemen met de netwerkprestaties oplost.</span><span class="sxs-lookup"><span data-stu-id="d3f81-118">This will often be the first step Support will ask you to complete when troubleshooting network performance issues.</span></span>
  
## <a name="use-a-standard-user-account-when-checking-performance"></a><span data-ttu-id="d3f81-119">Een standaardgebruikersaccount gebruiken bij het controleren van de prestaties</span><span class="sxs-lookup"><span data-stu-id="d3f81-119">Use a standard user account when checking performance</span></span>

<span data-ttu-id="d3f81-120">Een beheerder van een siteverzameling, site-eigenaar, editor of Inzender behoort tot extra beveiligingsgroepen, heeft extra machtigingen en bevat daarom extra elementen die in SharePoint op een pagina worden geladen.</span><span class="sxs-lookup"><span data-stu-id="d3f81-120">A Site Collection Administrator, Site Owner, Editor, or Contributor belong to additional security groups, have additional permissions, and therefore have additional elements that SharePoint loads on a page.</span></span>
  
<span data-ttu-id="d3f81-121">Dit geldt voor on-premises SharePoint en SharePoint Online, maar in een on-premises scenario worden de verschillen niet zo gemakkelijk weergegeven als in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="d3f81-121">This is applicable to SharePoint on-premises and SharePoint Online but in an on-premises scenario the differences will not be as easily noticed as in SharePoint Online.</span></span>
  
<span data-ttu-id="d3f81-122">Om te bepalen hoe een pagina voor gebruikers moet worden uitgevoerd, moet u een standaardgebruikersaccount gebruiken om te voorkomen dat u de creatie besturingselementen en extra verkeer met betrekking tot beveiligingsgroepen kunt laden.</span><span class="sxs-lookup"><span data-stu-id="d3f81-122">In order to correctly evaluate how a page will perform for users, you should use a standard user account to avoid loading the authoring controls and additional traffic related to security groups.</span></span>
  
## <a name="connection-categories-for-performance-tuning"></a><span data-ttu-id="d3f81-123">Verbindings categorieën voor prestatieafstemming</span><span class="sxs-lookup"><span data-stu-id="d3f81-123">Connection categories for performance tuning</span></span>

<span data-ttu-id="d3f81-124">U kunt de verbindingen tussen de server en de gebruiker categoriseren met drie belangrijkste onderdelen.</span><span class="sxs-lookup"><span data-stu-id="d3f81-124">You can categorize the connections between the server and the user into three main components.</span></span> <span data-ttu-id="d3f81-125">U kunt deze bij het ontwerpen van SharePoint Online-pagina's voor inzicht in laadtijden.</span><span class="sxs-lookup"><span data-stu-id="d3f81-125">Consider these when designing SharePoint Online pages for insight into load times.</span></span>
  
- <span data-ttu-id="d3f81-126">De **Server** De servers die Microsoft hosten in datacenters.</span><span class="sxs-lookup"><span data-stu-id="d3f81-126">**Server** The servers that Microsoft hosts in datacenters.</span></span>
    
- <span data-ttu-id="d3f81-127">**Netwerk** Het Microsoft-netwerk, Internet en uw on-premises netwerk tussen het datacenter en uw gebruikers.</span><span class="sxs-lookup"><span data-stu-id="d3f81-127">**Network** The Microsoft network, the Internet, and your on-premises network between the datacenter and your users.</span></span>
    
- <span data-ttu-id="d3f81-128">**Browser** Waar de pagina wordt geladen.</span><span class="sxs-lookup"><span data-stu-id="d3f81-128">**Browser** Where the page is loaded.</span></span>
    
<span data-ttu-id="d3f81-129">Binnen deze drie verbindingen zijn meestal vijf redenen die 95% van de traagste pagina's veroorzaken.</span><span class="sxs-lookup"><span data-stu-id="d3f81-129">Within these three connections there are typically five reasons that cause 95% of slow pages.</span></span> <span data-ttu-id="d3f81-130">Dit artikel bevat de volgende redenen:</span><span class="sxs-lookup"><span data-stu-id="d3f81-130">Each of these reasons is discussed in this article:</span></span>
  
- <span data-ttu-id="d3f81-131">Problemen met navigeren</span><span class="sxs-lookup"><span data-stu-id="d3f81-131">Navigation issues</span></span>
    
- <span data-ttu-id="d3f81-132">Inhoud samengevouwen</span><span class="sxs-lookup"><span data-stu-id="d3f81-132">Content roll up</span></span>
    
- <span data-ttu-id="d3f81-133">Grote bestanden</span><span class="sxs-lookup"><span data-stu-id="d3f81-133">Large files</span></span>
    
- <span data-ttu-id="d3f81-134">Veel aanvragen voor de server</span><span class="sxs-lookup"><span data-stu-id="d3f81-134">Many requests to the server</span></span>
    
- <span data-ttu-id="d3f81-135">Verwerking van webonderdelen</span><span class="sxs-lookup"><span data-stu-id="d3f81-135">Web Part processing</span></span>
    
### <a name="server-connection"></a><span data-ttu-id="d3f81-136">Server verbinding</span><span class="sxs-lookup"><span data-stu-id="d3f81-136">Server connection</span></span>

<span data-ttu-id="d3f81-137">Veel van de problemen die de prestaties beïnvloeden van on-premises SharePoint zijn ook van toepassing op SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="d3f81-137">Many of the issues that affect performance with SharePoint on-premises also apply to SharePoint Online.</span></span>
  
<span data-ttu-id="d3f81-138">Zoals u zou verwachten, hebt u veel meer controle over de implementatie van servers met on-premises SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d3f81-138">As you would expect, you have far more control over how servers perform with on-premises SharePoint.</span></span> <span data-ttu-id="d3f81-139">Met SharePoint Online-dingen zijn iets anders.</span><span class="sxs-lookup"><span data-stu-id="d3f81-139">With SharePoint Online things are a little different.</span></span> <span data-ttu-id="d3f81-140">Hoe meer werken u maakt met een server, hoe langer het duurt voor een pagina wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="d3f81-140">The more work you make a server do, the longer it takes to render a page.</span></span> <span data-ttu-id="d3f81-141">Met SharePoint is de grootste probleem voor dit opzicht ingewikkelde pagina's met meerdere webonderdelen.</span><span class="sxs-lookup"><span data-stu-id="d3f81-141">With SharePoint, the biggest culprit in this respect are complex pages with multiple web parts.</span></span>
  
<span data-ttu-id="d3f81-142">SharePoint Server on-premises</span><span class="sxs-lookup"><span data-stu-id="d3f81-142">SharePoint Server on-premises</span></span>
  
![Schermafbeelding van de server on-premises](../media/a8e9b646-cdff-4131-976a-b5f891da44ac.png)
  
<span data-ttu-id="d3f81-144">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="d3f81-144">SharePoint Online</span></span>
  
![Schermafbeelding van server online](../media/46b27ded-d8a4-4287-b3e0-2603a764b8f8.png)
  
<span data-ttu-id="d3f81-146">Met SharePoint Online kunnen bepaalde pagina aanvragen uiteindelijk meerdere servers beëindigen.</span><span class="sxs-lookup"><span data-stu-id="d3f81-146">With SharePoint Online, certain page requests may actually end up calling multiple servers.</span></span> <span data-ttu-id="d3f81-147">U kunt uiteindelijk een matrix met aanvragen tussen servers voor een afzonderlijke aanvraag beëindigen.</span><span class="sxs-lookup"><span data-stu-id="d3f81-147">You could end up with a matrix of requests between servers for an individual request.</span></span> <span data-ttu-id="d3f81-148">Deze interacties zijn kostbaar van een perspectief voor het laden van pagina's en werken hierdoor te traag.</span><span class="sxs-lookup"><span data-stu-id="d3f81-148">These interactions are expensive from a page load perspective and will make things slow.</span></span>
  
<span data-ttu-id="d3f81-149">Voorbeelden van de interacties van servers naar servers zijn:</span><span class="sxs-lookup"><span data-stu-id="d3f81-149">Examples of these server to server interactions are:</span></span>
  
- <span data-ttu-id="d3f81-150">Web-naar SQL-servers</span><span class="sxs-lookup"><span data-stu-id="d3f81-150">Web to SQL Servers</span></span>
    
- <span data-ttu-id="d3f81-151">Web-naar toepassingsservers</span><span class="sxs-lookup"><span data-stu-id="d3f81-151">Web to application servers</span></span>
    
<span data-ttu-id="d3f81-152">Een andere manier om de server interacties te vertragen, is Cachemissers.</span><span class="sxs-lookup"><span data-stu-id="d3f81-152">The other thing that can slow down server interactions is cache misses.</span></span> <span data-ttu-id="d3f81-153">In tegenstelling tot on-premises SharePoint is er een zeer compacte uitzooming en gaat u naar de server die u eerder hebt bezocht. Hierdoor wordt de objectcache verouderd.</span><span class="sxs-lookup"><span data-stu-id="d3f81-153">Unlike on-premises SharePoint, there is a very slim chance that you will hit the same server for a page that you have visited previously; this makes object caching obsolete.</span></span>
  
### <a name="network-connection"></a><span data-ttu-id="d3f81-154">Netwerkverbinding</span><span class="sxs-lookup"><span data-stu-id="d3f81-154">Network connection</span></span>

<span data-ttu-id="d3f81-155">Met een on-premises SharePoint dat geen gebruik maakt van een WAN, mag u een snelle verbinding gebruiken tussen datacenter en eindgebruikers.</span><span class="sxs-lookup"><span data-stu-id="d3f81-155">With on-premises SharePoint that doesn't make use of a WAN, you may use a high-speed connection between datacenter and end-users.</span></span> <span data-ttu-id="d3f81-156">In het algemeen kunt u eenvoudig zaken beheren vanuit een netwerk perspectief.</span><span class="sxs-lookup"><span data-stu-id="d3f81-156">Generally, things are easy to manage from a network perspective.</span></span>
  
<span data-ttu-id="d3f81-157">Met SharePoint Online zijn er een paar factoren waarmee u rekening moet houden; voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="d3f81-157">With SharePoint Online, there are a few more factors to consider; for example:</span></span>
  
- <span data-ttu-id="d3f81-158">Het Microsoft-netwerk</span><span class="sxs-lookup"><span data-stu-id="d3f81-158">The Microsoft network</span></span>
    
- <span data-ttu-id="d3f81-159">Internet</span><span class="sxs-lookup"><span data-stu-id="d3f81-159">The Internet</span></span>
    
- <span data-ttu-id="d3f81-160">De INTERNETPROVIDER</span><span class="sxs-lookup"><span data-stu-id="d3f81-160">The ISP</span></span>
    
<span data-ttu-id="d3f81-161">Ongeacht welke versie van SharePoint (en welk netwerk) u gebruikt, is het mogelijk dat het netwerk meestal bezet is:</span><span class="sxs-lookup"><span data-stu-id="d3f81-161">Regardless of which version of SharePoint (and which network) you are using, things that will typically cause the network to be busy include:</span></span>
  
- <span data-ttu-id="d3f81-162">Grote nettolading</span><span class="sxs-lookup"><span data-stu-id="d3f81-162">Large payload</span></span>
    
- <span data-ttu-id="d3f81-163">Veel bestanden</span><span class="sxs-lookup"><span data-stu-id="d3f81-163">Many files</span></span>
    
- <span data-ttu-id="d3f81-164">Grote fysieke afstand tot de server</span><span class="sxs-lookup"><span data-stu-id="d3f81-164">Large physical distance to the server</span></span>
    
<span data-ttu-id="d3f81-165">Eén functie die u in SharePoint Online kunt benutten, is het Microsoft CDN (Content Delivery Network).</span><span class="sxs-lookup"><span data-stu-id="d3f81-165">One feature that you can leverage in SharePoint Online is the Microsoft CDN (Content Delivery Network).</span></span> <span data-ttu-id="d3f81-166">Een CDN is een gedistribueerde verzameling servers die wordt geïmplementeerd via meerdere datacenters.</span><span class="sxs-lookup"><span data-stu-id="d3f81-166">A CDN is basically a distributed collection of servers deployed across multiple datacenters.</span></span> <span data-ttu-id="d3f81-167">Met een CDN kunnen inhoud op pagina's op een server worden gehost op de client, zelfs als de client ver weg is van de oorspronkelijke SharePoint-Server.</span><span class="sxs-lookup"><span data-stu-id="d3f81-167">With a CDN, content on pages can be hosted on a server close to the client even if the client is far away from the originating SharePoint Server.</span></span> <span data-ttu-id="d3f81-168">Microsoft zal dit meer in de toekomst gebruiken voor het opslaan van lokale exemplaren van pagina's die niet kunnen worden aangepast, zoals de startpagina van de SharePoint Online-beheerder.</span><span class="sxs-lookup"><span data-stu-id="d3f81-168">Microsoft will be using this more in the future to store local instances of pages which cannot be customized, for example the SharePoint Online admin home page.</span></span> <span data-ttu-id="d3f81-169">Zie [netwerken die inhoud leveren](content-delivery-networks.md)voor meer informatie over cdn's.</span><span class="sxs-lookup"><span data-stu-id="d3f81-169">For more information about CDNs, see [Content delivery networks](content-delivery-networks.md).</span></span>
  
<span data-ttu-id="d3f81-170">Als u op de hoogte bent van de verbindingssnelheid van uw internetprovider, moet u op de hoogte blijven van de verbindingssnelheid van uw internetprovider.</span><span class="sxs-lookup"><span data-stu-id="d3f81-170">Something that you need to be aware of but may not be able to do much about is the connection speed of your ISP.</span></span> <span data-ttu-id="d3f81-171">Met een eenvoudige snelheids test kunt u de verbindingssnelheid aangeven.</span><span class="sxs-lookup"><span data-stu-id="d3f81-171">A simple speed test tool will tell you the connection speed.</span></span>
  
### <a name="browser-connection"></a><span data-ttu-id="d3f81-172">Browser verbinding</span><span class="sxs-lookup"><span data-stu-id="d3f81-172">Browser connection</span></span>

<span data-ttu-id="d3f81-173">U kunt ook met webbrowsers van een prestatie perspectief rekening houden.</span><span class="sxs-lookup"><span data-stu-id="d3f81-173">There are a few factors to consider with web browsers from a performance perspective.</span></span>
  
<span data-ttu-id="d3f81-174">Het bezoeken van ingewikkelde pagina's heeft invloed op de prestaties.</span><span class="sxs-lookup"><span data-stu-id="d3f81-174">Visiting complex pages will affect performance.</span></span> <span data-ttu-id="d3f81-175">De meeste browsers hebben alleen een kleine cache (rondom 90MB), terwijl de gemiddelde webpagina doorgaans ongeveer 1,6 MB is.</span><span class="sxs-lookup"><span data-stu-id="d3f81-175">Most browsers only have a small cache (around 90MB), while the average web page is typically around 1.6MB.</span></span> <span data-ttu-id="d3f81-176">Dit duurt niet lang.</span><span class="sxs-lookup"><span data-stu-id="d3f81-176">This doesn't take long to get used up.</span></span>
  
<span data-ttu-id="d3f81-177">Bandbreedte kan ook een probleem zijn.</span><span class="sxs-lookup"><span data-stu-id="d3f81-177">Bandwidth may also be an issue.</span></span> <span data-ttu-id="d3f81-178">Als een gebruiker bijvoorbeeld Video's bekijkt in een andere sessie, is dit van invloed op de prestaties van de SharePoint-pagina.</span><span class="sxs-lookup"><span data-stu-id="d3f81-178">For example, if a user is watching videos in another session, this will affect the performance of your SharePoint page.</span></span> <span data-ttu-id="d3f81-179">Wanneer u niet kunt voorkomen dat gebruikers van streaming media streaming kunnen voorkomen, kunt u bepalen hoe een pagina wordt geladen voor gebruikers.</span><span class="sxs-lookup"><span data-stu-id="d3f81-179">While you can't prevent users from streaming media, you can control the way a page will load for users.</span></span>
  
<span data-ttu-id="d3f81-180">Raadpleeg de volgende artikelen voor verschillende technieken voor het aanpassen van SharePoint Online-pagina's en andere aanbevolen procedures voor het optimaliseren van de prestaties.</span><span class="sxs-lookup"><span data-stu-id="d3f81-180">Check out the following articles for different SharePoint Online page customization techniques and other best practices to help you achieve optimal performance.</span></span>
  
- [<span data-ttu-id="d3f81-181">Navigatieopties voor SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="d3f81-181">Navigation options for SharePoint Online</span></span>](navigation-options-for-sharepoint-online.md)
    
- [<span data-ttu-id="d3f81-182">Het hulpprogramma pagina diagnose voor SharePoint Online gebruiken</span><span class="sxs-lookup"><span data-stu-id="d3f81-182">Use the Page Diagnostics tool for SharePoint Online</span></span>](page-diagnostics-for-spo.md)
    
- [<span data-ttu-id="d3f81-183">Afbeeldingen optimaliseren voor SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="d3f81-183">Image optimization for SharePoint Online</span></span>](image-optimization-for-sharepoint-online.md)
    
- [<span data-ttu-id="d3f81-184">Laden van afbeeldingen en JavaScript vertragen in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="d3f81-184">Delay loading images and JavaScript in SharePoint Online</span></span>](delay-loading-images-and-javascript-in-sharepoint-online.md)
    
- [<span data-ttu-id="d3f81-185">Minification en bundeling in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="d3f81-185">Minification and bundling in SharePoint Online</span></span>](minification-and-bundling-in-sharepoint-online.md)
    
- [<span data-ttu-id="d3f81-186">Het Office 365 Content Delivery Network (CDN) gebruiken met SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="d3f81-186">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)
    
- [<span data-ttu-id="d3f81-187">Het webonderdeel inhoud zoeken in plaats van het webonderdeel inhouds query gebruiken om de prestaties te verbeteren in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="d3f81-187">Using Content Search Web Part instead of Content Query Web Part to improve performance in SharePoint Online</span></span>](using-content-search-web-part-instead-of-content-query-web-part-to-improve-perfo.md)
    
- [<span data-ttu-id="d3f81-188">Capaciteitsplanning en belastingtest van SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="d3f81-188">Capacity planning and load testing SharePoint Online</span></span>](capacity-planning-and-load-testing-sharepoint-online.md)
    
- [<span data-ttu-id="d3f81-189">Prestatieproblemen met SharePoint Online vaststellen</span><span class="sxs-lookup"><span data-stu-id="d3f81-189">Diagnosing performance issues with SharePoint Online</span></span>](diagnosing-performance-issues-with-sharepoint-online.md)
    
- [<span data-ttu-id="d3f81-190">De objectcache gebruiken met SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="d3f81-190">Using the object cache with SharePoint Online</span></span>](using-the-object-cache-with-sharepoint-online.md)
    
- [<span data-ttu-id="d3f81-191">Procedure: vertraging of blokkering voorkomen in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="d3f81-191">How to: Avoid getting throttled or blocked in SharePoint Online</span></span>](https://msdn.microsoft.com/library/office/dn889829.aspx)
    

