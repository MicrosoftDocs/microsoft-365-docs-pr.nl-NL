---
title: Het webonderdeel inhoud zoeken in plaats van het webonderdeel inhouds query gebruiken om de prestaties te verbeteren in SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 4/20/2015
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- SPO160
ms.assetid: e8ce6b72-745b-464a-85c7-cbf6eb53391b
description: Meer informatie over hoe u de prestaties kunt verbeteren door het webonderdeel inhouds query te vervangen door het webonderdeel inhoud zoeken in SharePoint Server 2013 en SharePoint Online.
ms.openlocfilehash: e5f57e59a421d79302f447e229091fdfc96f1237
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689549"
---
# <a name="using-content-search-web-part-instead-of-content-query-web-part-to-improve-performance-in-sharepoint-online"></a><span data-ttu-id="ab1ca-103">Het webonderdeel inhoud zoeken in plaats van het webonderdeel inhouds query gebruiken om de prestaties te verbeteren in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="ab1ca-103">Using Content Search Web Part instead of Content Query Web Part to improve performance in SharePoint Online</span></span>

<span data-ttu-id="ab1ca-104">In dit artikel wordt uitgelegd hoe u de prestaties kunt verbeteren door het webonderdeel inhouds query te vervangen door het webonderdeel inhoud zoeken in SharePoint Server 2013 en SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="ab1ca-104">This article describes how to increase performance by replacing the Content Query Web Part with the Content Search Web Part in SharePoint Server 2013 and SharePoint Online.</span></span>
  
<span data-ttu-id="ab1ca-105">Een van de krachtigste nieuwe functies van SharePoint Server 2013 en SharePoint Online is het webonderdeel inhoud zoeken (WEBONDERDEEL inhoud zoeken).</span><span class="sxs-lookup"><span data-stu-id="ab1ca-105">One of the most powerful new features of SharePoint Server 2013 and SharePoint Online is the Content Search Web Part (CSWP).</span></span> <span data-ttu-id="ab1ca-106">Dit webonderdeel maakt gebruik van de zoekindex om snel resultaten op te halen die aan de gebruiker worden getoond.</span><span class="sxs-lookup"><span data-stu-id="ab1ca-106">This Web Part uses the search index to quickly retrieve results which are shown to the user.</span></span> <span data-ttu-id="ab1ca-107">Gebruik het webonderdeel inhoud zoeken in plaats van het webonderdeel inhouds query (CQWP) op uw pagina's om de prestaties van uw gebruikers te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="ab1ca-107">Use the Content Search Web Part instead of the Content Query Web Part (CQWP) in your pages to improve performance for your users.</span></span>
  
<span data-ttu-id="ab1ca-108">Het gebruik van een webonderdeel inhoud zoeken via een webonderdeel inhouds query levert bijna altijd betere resultaten op voor het laden van pagina's in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="ab1ca-108">Using a Content Search Web Part over a Content Query Web Part will almost always result in significantly better page load performance on SharePoint Online.</span></span> <span data-ttu-id="ab1ca-109">Er is een beetje extra configuratie ter verbetering van de juiste query, maar de voordelen zijn voor betere prestaties en tevredenere gebruikers.</span><span class="sxs-lookup"><span data-stu-id="ab1ca-109">There is a little additional configuration to get the right query, but the rewards are improved performance and happier users.</span></span>
  
## <a name="comparing-the-performance-gain-you-get-from-using-content-search-web-part-instead-of-content-query-web-part"></a><span data-ttu-id="ab1ca-110">Wanneer u de prestaties vergelijkt met het gebruik van het webonderdeel inhoud zoeken in plaats van het webonderdeel inhouds query</span><span class="sxs-lookup"><span data-stu-id="ab1ca-110">Comparing the performance gain you get from using Content Search Web Part instead of Content Query Web Part</span></span>

<span data-ttu-id="ab1ca-111">In het volgende voorbeeld worden de relatieve prestatiewinst weergegeven wanneer u een webonderdeel inhoud zoeken gebruikt in plaats van een webonderdeel inhouds query.</span><span class="sxs-lookup"><span data-stu-id="ab1ca-111">The following examples show the relative performance gains you may receive when you use a Content Search Web Part instead of a Content Query Web Part.</span></span> <span data-ttu-id="ab1ca-112">De effecten zijn duidelijker met een complexe sitestructuur en zeer brede inhoudsquery's.</span><span class="sxs-lookup"><span data-stu-id="ab1ca-112">The effects are more obvious with a complex site structure and very broad content queries.</span></span>
  
<span data-ttu-id="ab1ca-113">De voorbeeldsite heeft de volgende kenmerken:</span><span class="sxs-lookup"><span data-stu-id="ab1ca-113">This example site has the following characteristics:</span></span>
  
- <span data-ttu-id="ab1ca-114">acht niveaus van subsites.</span><span class="sxs-lookup"><span data-stu-id="ab1ca-114">8 levels of subsites.</span></span>
    
- <span data-ttu-id="ab1ca-115">Lijsten waarin een aangepast inhoudstype wordt gebruikt voor fruit.</span><span class="sxs-lookup"><span data-stu-id="ab1ca-115">Lists using a custom "fruit" content type.</span></span>
    
- <span data-ttu-id="ab1ca-116">In het webonderdeel is de Inhoudsquery uitgebreid, met als resultaat alle items met het inhoudstype ' fruit '.</span><span class="sxs-lookup"><span data-stu-id="ab1ca-116">In the Web Part, the content query is broad, returning all items with the content type of "fruit".</span></span>
    
- <span data-ttu-id="ab1ca-117">Het voorbeeld werkt alleen met 50-items op de acht sites.</span><span class="sxs-lookup"><span data-stu-id="ab1ca-117">The example only uses 50 items across the 8 sites.</span></span> <span data-ttu-id="ab1ca-118">De effecten zullen nog meer uitspreken voor sites met meer inhoud.</span><span class="sxs-lookup"><span data-stu-id="ab1ca-118">The effects will be even more pronounced for sites with more content.</span></span>
    
<span data-ttu-id="ab1ca-119">Dit is een schermafbeelding van de resultaten van het webonderdeel inhouds query.</span><span class="sxs-lookup"><span data-stu-id="ab1ca-119">Here is a screen shot of the results of the Content Query Web Part.</span></span>
  
![Afbeelding met Inhoudsquery voor webonderdeel](../media/b3d41f20-dfe5-46ed-9c0a-31057e82de33.png)
  
<span data-ttu-id="ab1ca-121">In Internet Explorer gebruikt u het tabblad **netwerk** van de F12-hulpprogramma's voor ontwikkelaars om de details te bekijken voor de antwoordheader.</span><span class="sxs-lookup"><span data-stu-id="ab1ca-121">In Internet Explorer, use the **Network** tab of the F12 developer tools to look at the details for the response header.</span></span> <span data-ttu-id="ab1ca-122">In de volgende schermafbeelding is de waarde voor het **SPRequestDuration** voor deze pagina-laad 924 milliseconden.</span><span class="sxs-lookup"><span data-stu-id="ab1ca-122">In the following screen shot, the value for the **SPRequestDuration** for this page load is 924 milliseconds.</span></span> 
  
![Schermafbeelding van het aanvragen van de duur van 924](../media/343571f2-a249-4de2-bc11-2cee93498aea.png)
  
 <span data-ttu-id="ab1ca-124">In **SPRequestDuration** wordt de hoeveelheid werk die op de server is uitgevoerd, aangegeven om de pagina voor te bereiden.</span><span class="sxs-lookup"><span data-stu-id="ab1ca-124">**SPRequestDuration** indicates the amount of work that is done on the server to prepare the page.</span></span> <span data-ttu-id="ab1ca-125">Door de inhoud van een query te vervangen door de webonderdelen inhoud door zoekresultaten wordt de tijd voor het weergeven van de pagina aanzienlijk verkleind.</span><span class="sxs-lookup"><span data-stu-id="ab1ca-125">Switching Content by Query Web Parts with Content by Search Web Parts dramatically reduces the time it takes to render the page.</span></span> <span data-ttu-id="ab1ca-126">Als u daarentegen een pagina met een vergelijkbaar webonderdeel inhoud zoeken oplevert, wordt het resultaat van de **SPRequestDuration** -waarde van 106 milliseconden weergegeven, zoals in deze schermafbeelding:</span><span class="sxs-lookup"><span data-stu-id="ab1ca-126">By contrast, a page with an equivalent Content Search Web Part, returning the same number of results has an **SPRequestDuration** value of 106 milliseconds as shown in this screen shot:</span></span> 
  
![Schermafbeelding van het aanvragen van de duur van 106](../media/b46387ac-660d-4e5e-a11c-cc430e912962.png)
  
## <a name="adding-a-content-search-web-part-in-sharepoint-online"></a><span data-ttu-id="ab1ca-128">Een webonderdeel inhoud zoeken toevoegen in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="ab1ca-128">Adding a Content Search Web Part in SharePoint Online</span></span>

<span data-ttu-id="ab1ca-129">Het toevoegen van een webonderdeel inhoud is vergelijkbaar met een standaard webonderdeel inhouds query.</span><span class="sxs-lookup"><span data-stu-id="ab1ca-129">Adding a Content Search Web Part is very similar to a regular Content Query Web Part.</span></span> <span data-ttu-id="ab1ca-130">Zie de sectie  *' een webonderdeel inhoud zoeken toevoegen '*  in een webonderdeel inhoud [Zoeken configureren in SharePoint](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a).</span><span class="sxs-lookup"><span data-stu-id="ab1ca-130">See the section  *"Add a Content Search Web Part"*  in [Configure a Content Search Web Part in SharePoint](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a).</span></span>
  
## <a name="creating-the-right-search-query-for-your-content-search-web-part"></a><span data-ttu-id="ab1ca-131">De juiste zoekquery maken voor het webonderdeel inhoud zoeken</span><span class="sxs-lookup"><span data-stu-id="ab1ca-131">Creating the right search query for your Content Search Web Part</span></span>

<span data-ttu-id="ab1ca-132">Wanneer u een webonderdeel inhoud zoeken hebt toegevoegd, kunt u de zoekopdracht verfijnen en de gewenste items herstellen.</span><span class="sxs-lookup"><span data-stu-id="ab1ca-132">Once you have added a Content Search Web Part, you can refine the search and return the items you want.</span></span> <span data-ttu-id="ab1ca-133">Zie de sectie  *' inhoud weergeven door een geavanceerde query te configureren in een webonderdeel inhoud zoeken '*  in een webonderdeel inhoud [Zoeken configureren in SharePoint](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a)voor gedetailleerde instructies.</span><span class="sxs-lookup"><span data-stu-id="ab1ca-133">For detailed instructions on how to do this, see the section,  *"Display content by configuring an advanced query in a Content Search Web Part"*  in [Configure a Content Search Web Part in SharePoint](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a).</span></span>
  
## <a name="query-building-and-testing-tool"></a><span data-ttu-id="ab1ca-134">Het hulpmiddel voor het maken en testen van query's</span><span class="sxs-lookup"><span data-stu-id="ab1ca-134">Query building and testing tool</span></span>

<span data-ttu-id="ab1ca-135">Voor een hulpmiddel voor het maken en testen van complexe query's, raadpleegt u het [hulpmiddel Zoek query](https://sp2013searchtool.codeplex.com/) op codeplex.</span><span class="sxs-lookup"><span data-stu-id="ab1ca-135">For a tool to build and test complex queries, see the [Search Query Tool](https://sp2013searchtool.codeplex.com/) on Codeplex.</span></span> 
  

