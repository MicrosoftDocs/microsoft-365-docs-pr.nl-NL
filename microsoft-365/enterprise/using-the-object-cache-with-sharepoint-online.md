---
title: De objectcache gebruiken met SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 4/20/2015
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
ms.assetid: 38bc9c14-3826-449c-beb6-b1003bcbeaaf
description: In dit artikel wordt het verschil beschreven tussen het gebruik van de objectcache in SharePoint Server 2013 on-premises en SharePoint Online.
ms.openlocfilehash: 279d156a941aad6fbe7adbcf052c57f5b58c652f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695751"
---
# <a name="using-the-object-cache-with-sharepoint-online"></a><span data-ttu-id="dc6b1-103">De objectcache gebruiken met SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="dc6b1-103">Using the object cache with SharePoint Online</span></span>

<span data-ttu-id="dc6b1-104">In dit artikel wordt het verschil beschreven tussen het gebruik van de objectcache in SharePoint Server 2013 on-premises en SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="dc6b1-104">This article explains the difference between using the object cache in SharePoint Server 2013 on-premises and SharePoint Online.</span></span>
  
<span data-ttu-id="dc6b1-105">Er is een aanzienlijk negatief effect van het vertrouwen op de objectcache in SharePoint Online-implementatie.</span><span class="sxs-lookup"><span data-stu-id="dc6b1-105">There is significant negative impact of relying on the object cache in SharePoint Online deployment.</span></span> <span data-ttu-id="dc6b1-106">Elke afhankelijkheid van de objectcache in SharePoint Online vermindert de betrouwbaarheid van uw pagina.</span><span class="sxs-lookup"><span data-stu-id="dc6b1-106">Any dependency on object cache in SharePoint Online will reduce the reliability of your page.</span></span> 
  
## <a name="how-the-sharepoint-online-and-sharepoint-server-2013-object-cache-works"></a><span data-ttu-id="dc6b1-107">Hoe de SharePoint Online en SharePoint Server 2013-objectcache werkt</span><span class="sxs-lookup"><span data-stu-id="dc6b1-107">How the SharePoint Online and SharePoint Server 2013 object cache works</span></span>

<span data-ttu-id="dc6b1-108">Wanneer SharePoint Server 2013 on-premises wordt gehost, beschikt de klant over persoonlijke front-endwebservers die de objectcache hosten.</span><span class="sxs-lookup"><span data-stu-id="dc6b1-108">When SharePoint Server 2013 is hosted on-premises, the customer has private front-end web servers that host the object cache.</span></span> <span data-ttu-id="dc6b1-109">Dit betekent dat de cache is toegewezen aan één klant en alleen wordt beperkt door hoeveel geheugen beschikbaar is en wordt toegewezen aan de objectcache.</span><span class="sxs-lookup"><span data-stu-id="dc6b1-109">This means the cache is dedicated to one customer and is only limited by how much memory is available and allocated to the object cache.</span></span> <span data-ttu-id="dc6b1-110">Omdat in het on-premises scenario slechts één klant wordt gediend, hebben de front-endwebservers meestal gebruikers die steeds opnieuw aanvragen indienen bij dezelfde sites.</span><span class="sxs-lookup"><span data-stu-id="dc6b1-110">Because only one customer is served in the on-premises scenario the front-end web servers typically have users making requests to the same sites over and over.</span></span> <span data-ttu-id="dc6b1-111">Dit betekent dat de cache snel vol raakt en vol blijft met de lijstqueryresultaten en SharePoint objecten die uw gebruikers regelmatig aanvragen.</span><span class="sxs-lookup"><span data-stu-id="dc6b1-111">This means that the cache gets full quickly and remains full of the list query results and SharePoint objects that your users are requesting on a regular basis.</span></span>
  
![Toont verkeer en laden naar on-premises front-endwebservers](../media/a0d38b36-4909-4abb-8d4e-4930814bb3de.png)
  
<span data-ttu-id="dc6b1-113">De tweede keer dat een gebruiker een pagina bezoekt, wordt de laadtijd van de pagina verbeterd.</span><span class="sxs-lookup"><span data-stu-id="dc6b1-113">As a result, the second time a user visits a page, the page load time improves.</span></span> <span data-ttu-id="dc6b1-114">Na minimaal vier belastingen van dezelfde pagina wordt de pagina in de cache opgeslagen op alle front-endwebservers.</span><span class="sxs-lookup"><span data-stu-id="dc6b1-114">After a minimum of four loads of the same page, the page is cached on all of the front-end web servers.</span></span>
  
<span data-ttu-id="dc6b1-115">In SharePoint Online zijn er echter veel meer servers, maar ook veel meer sites.</span><span class="sxs-lookup"><span data-stu-id="dc6b1-115">In contrast, in SharePoint Online there are many more servers but also many more sites.</span></span> <span data-ttu-id="dc6b1-116">Elke gebruiker kan verbinding maken met een andere front-endwebserver die de cache niet heeft ingevuld.</span><span class="sxs-lookup"><span data-stu-id="dc6b1-116">Each user may connect to a different front-end web server that doesn't have the cache populated.</span></span> <span data-ttu-id="dc6b1-117">Of misschien wordt de cache wel ingevuld voor een server, maar de volgende gebruiker van die front-endwebserver vraagt om een pagina van een andere site.</span><span class="sxs-lookup"><span data-stu-id="dc6b1-117">Or, perhaps the cache does get populated for a server, but the next user to that front-end web server requests a page from a different site.</span></span> <span data-ttu-id="dc6b1-118">Of, zelfs als de volgende gebruiker dezelfde pagina aanvraagt als tijdens het vorige bezoek, worden ze gebalanceerd geladen naar een andere front-endwebserver die deze pagina niet in de cache heeft.</span><span class="sxs-lookup"><span data-stu-id="dc6b1-118">Or, even if the next user requests the same page as on their previous visit, they are load-balanced to a different front-end web server that doesn't have that page in its cache.</span></span> <span data-ttu-id="dc6b1-119">In dit laatste geval helpt caching de gebruikers helemaal niet.</span><span class="sxs-lookup"><span data-stu-id="dc6b1-119">In this last case, caching doesn't help the users at all.</span></span>
  
<span data-ttu-id="dc6b1-120">In de volgende afbeelding staat elke punt voor een pagina die een gebruiker aanvraagt en waar deze in de cache is opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="dc6b1-120">In the following figure, each dot represents a page that a user is requesting and where it cached.</span></span> <span data-ttu-id="dc6b1-121">Verschillende kleuren vertegenwoordigen verschillende klanten die gezamenlijk gebruikmaken van de SaaS-infrastructuur.</span><span class="sxs-lookup"><span data-stu-id="dc6b1-121">Different colors represent different customers making shared use of the SaaS infrastructure.</span></span>
  
![Toont de resultaten van objectcaching in SharePoint Online](../media/25d04011-ef83-4cb7-9e04-a6ed490f63c3.png)
  
<span data-ttu-id="dc6b1-123">Zoals u kunt zien in het diagram, is de kans klein dat een bepaalde gebruiker een server raakt met de in de cache opgeslagen versie van de pagina.</span><span class="sxs-lookup"><span data-stu-id="dc6b1-123">As you can see from the diagram, the chances of any given user hitting a server with the cached version of their page are slim.</span></span> <span data-ttu-id="dc6b1-124">Vanwege de grote doorvoer en het feit dat de servers worden gedeeld tussen veel sites, duurt de cache niet lang, omdat er slechts zo veel ruimte beschikbaar is voor caching.</span><span class="sxs-lookup"><span data-stu-id="dc6b1-124">Also, due to the large throughput and fact that the servers are shared between many sites, the cache doesn't last long since there is only so much space for caching available.</span></span>
  
<span data-ttu-id="dc6b1-125">Om al deze redenen is het vertrouwen op gebruikers die objecten in de cache krijgen, geen effectieve manier om te zorgen voor een hoogwaardige gebruikerservaring en laadtijden voor pagina's in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="dc6b1-125">For all of these reasons, relying on users getting cached objects is not an effective way to ensure a quality user experience and page load times in SharePoint Online.</span></span>
  
## <a name="if-we-cant-rely-on-the-object-cache-to-improve-performance-in-sharepoint-online-what-do-we-use-instead"></a><span data-ttu-id="dc6b1-126">Als we niet kunnen vertrouwen op de objectcache om de prestaties in SharePoint Online te verbeteren, wat gebruiken we dan?</span><span class="sxs-lookup"><span data-stu-id="dc6b1-126">If we can't rely on the object cache to improve performance in SharePoint Online, what do we use instead?</span></span>

<span data-ttu-id="dc6b1-127">Aangezien u niet afhankelijk moet zijn van caching in SharePoint Online, moet u alternatieve ontwerpbenaderingen evalueren voor SharePoint aanpassingen die de objectcache gebruiken.</span><span class="sxs-lookup"><span data-stu-id="dc6b1-127">Since you shouldn't rely on caching in SharePoint Online, you should evaluate alternative design approaches for SharePoint customizations that use the object cache.</span></span> <span data-ttu-id="dc6b1-128">Dit betekent dat u benaderingen gebruikt voor prestatieproblemen die niet afhankelijk zijn van de objectcaching om goede resultaten te leveren voor gebruikers.</span><span class="sxs-lookup"><span data-stu-id="dc6b1-128">This means using approaches for performance issues which do not rely on the object caching in order to produce good results for users.</span></span> <span data-ttu-id="dc6b1-129">Dit wordt beschreven in enkele andere artikelen in deze reeks en bevat:</span><span class="sxs-lookup"><span data-stu-id="dc6b1-129">This is described in some of the other articles in this series and include:</span></span>
  
- [<span data-ttu-id="dc6b1-130">Navigatieopties voor SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="dc6b1-130">Navigation options for SharePoint Online</span></span>](navigation-options-for-sharepoint-online.md)
    
- [<span data-ttu-id="dc6b1-131">Minificatie en bundeling in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="dc6b1-131">Minification and bundling in SharePoint Online</span></span>](minification-and-bundling-in-sharepoint-online.md)
    
- [<span data-ttu-id="dc6b1-132">De Office 365 Content Delivery Network (CDN) gebruiken met SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="dc6b1-132">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)
    
- [<span data-ttu-id="dc6b1-133">Vertraging bij het laden van afbeeldingen en JavaScript in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="dc6b1-133">Delay loading images and JavaScript in SharePoint Online</span></span>](delay-loading-images-and-javascript-in-sharepoint-online.md)
    

