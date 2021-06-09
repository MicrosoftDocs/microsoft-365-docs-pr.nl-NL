---
title: Webonderdeel Inhoud zoeken gebruiken in plaats van webonderdeel Inhoudsquery om de prestaties in SharePoint Online
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
description: Lees hoe u de prestaties kunt verbeteren door het webonderdeel Inhoudsquery te vervangen door het webonderdeel Inhoud zoeken in SharePoint Server 2013 en SharePoint Online.
ms.openlocfilehash: e5f57e59a421d79302f447e229091fdfc96f1237
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689549"
---
# <a name="using-content-search-web-part-instead-of-content-query-web-part-to-improve-performance-in-sharepoint-online"></a><span data-ttu-id="0bb9a-103">Webonderdeel Inhoud zoeken gebruiken in plaats van webonderdeel Inhoudsquery om de prestaties in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="0bb9a-103">Using Content Search Web Part instead of Content Query Web Part to improve performance in SharePoint Online</span></span>

<span data-ttu-id="0bb9a-104">In dit artikel wordt beschreven hoe u de prestaties kunt verbeteren door het webonderdeel Inhoudsquery te vervangen door het webonderdeel Inhoud zoeken in SharePoint Server 2013 en SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="0bb9a-104">This article describes how to increase performance by replacing the Content Query Web Part with the Content Search Web Part in SharePoint Server 2013 and SharePoint Online.</span></span>
  
<span data-ttu-id="0bb9a-105">Een van de krachtigste nieuwe functies van SharePoint Server 2013 en SharePoint Online is het webonderdeel Inhoud zoeken (WEBWP).</span><span class="sxs-lookup"><span data-stu-id="0bb9a-105">One of the most powerful new features of SharePoint Server 2013 and SharePoint Online is the Content Search Web Part (CSWP).</span></span> <span data-ttu-id="0bb9a-106">In dit webonderdeel wordt de zoekindex gebruikt om snel resultaten op te halen die aan de gebruiker worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="0bb9a-106">This Web Part uses the search index to quickly retrieve results which are shown to the user.</span></span> <span data-ttu-id="0bb9a-107">Gebruik het webonderdeel Inhoud zoeken in plaats van het webonderdeel Inhoudsquery (CQWP) op uw pagina's om de prestaties voor uw gebruikers te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="0bb9a-107">Use the Content Search Web Part instead of the Content Query Web Part (CQWP) in your pages to improve performance for your users.</span></span>
  
<span data-ttu-id="0bb9a-108">Als u een webonderdeel Inhoud zoeken gebruikt via een webonderdeel Inhoudsquery, resulteert dit bijna altijd in aanzienlijk betere laadprestaties voor pagina's op SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="0bb9a-108">Using a Content Search Web Part over a Content Query Web Part will almost always result in significantly better page load performance on SharePoint Online.</span></span> <span data-ttu-id="0bb9a-109">Er is een beetje extra configuratie om de juiste query te krijgen, maar de voordelen zijn verbeterde prestaties en gelukkiger gebruikers.</span><span class="sxs-lookup"><span data-stu-id="0bb9a-109">There is a little additional configuration to get the right query, but the rewards are improved performance and happier users.</span></span>
  
## <a name="comparing-the-performance-gain-you-get-from-using-content-search-web-part-instead-of-content-query-web-part"></a><span data-ttu-id="0bb9a-110">De prestaties van het webonderdeel Inhoud zoeken vergelijken in plaats van webonderdeel Inhoudsquery</span><span class="sxs-lookup"><span data-stu-id="0bb9a-110">Comparing the performance gain you get from using Content Search Web Part instead of Content Query Web Part</span></span>

<span data-ttu-id="0bb9a-111">In de volgende voorbeelden ziet u de relatieve prestatieverbeteringen die u kunt ontvangen wanneer u een webonderdeel Inhoud zoeken gebruikt in plaats van een webonderdeel Inhoudsquery.</span><span class="sxs-lookup"><span data-stu-id="0bb9a-111">The following examples show the relative performance gains you may receive when you use a Content Search Web Part instead of a Content Query Web Part.</span></span> <span data-ttu-id="0bb9a-112">De effecten zijn duidelijker met een complexe sitestructuur en zeer brede inhoudsquery's.</span><span class="sxs-lookup"><span data-stu-id="0bb9a-112">The effects are more obvious with a complex site structure and very broad content queries.</span></span>
  
<span data-ttu-id="0bb9a-113">Deze voorbeeldsite heeft de volgende kenmerken:</span><span class="sxs-lookup"><span data-stu-id="0bb9a-113">This example site has the following characteristics:</span></span>
  
- <span data-ttu-id="0bb9a-114">8 niveaus met subsites.</span><span class="sxs-lookup"><span data-stu-id="0bb9a-114">8 levels of subsites.</span></span>
    
- <span data-ttu-id="0bb9a-115">Lijsten met een aangepast inhoudstype 'fruit'.</span><span class="sxs-lookup"><span data-stu-id="0bb9a-115">Lists using a custom "fruit" content type.</span></span>
    
- <span data-ttu-id="0bb9a-116">In het webonderdeel is de inhoudsquery breed en worden alle items met het inhoudstype 'fruit' als resultaat gebruikt.</span><span class="sxs-lookup"><span data-stu-id="0bb9a-116">In the Web Part, the content query is broad, returning all items with the content type of "fruit".</span></span>
    
- <span data-ttu-id="0bb9a-117">In het voorbeeld worden slechts 50 items op de 8 sites gebruikt.</span><span class="sxs-lookup"><span data-stu-id="0bb9a-117">The example only uses 50 items across the 8 sites.</span></span> <span data-ttu-id="0bb9a-118">De effecten zijn nog duidelijker voor sites met meer inhoud.</span><span class="sxs-lookup"><span data-stu-id="0bb9a-118">The effects will be even more pronounced for sites with more content.</span></span>
    
<span data-ttu-id="0bb9a-119">Hier ziet u een schermafbeelding van de resultaten van het webonderdeel Inhoudsquery.</span><span class="sxs-lookup"><span data-stu-id="0bb9a-119">Here is a screen shot of the results of the Content Query Web Part.</span></span>
  
![Afbeelding met inhoudsquery voor webonderdeel](../media/b3d41f20-dfe5-46ed-9c0a-31057e82de33.png)
  
<span data-ttu-id="0bb9a-121">Gebruik in Internet Explorer het **tabblad Netwerk** van de hulpprogramma's voor F12-ontwikkelaars om de details van de antwoordkop te bekijken.</span><span class="sxs-lookup"><span data-stu-id="0bb9a-121">In Internet Explorer, use the **Network** tab of the F12 developer tools to look at the details for the response header.</span></span> <span data-ttu-id="0bb9a-122">In de volgende schermafbeelding is de waarde voor **de SPRequestDuration** voor deze paginabelasting 924 milliseconden.</span><span class="sxs-lookup"><span data-stu-id="0bb9a-122">In the following screen shot, the value for the **SPRequestDuration** for this page load is 924 milliseconds.</span></span> 
  
![Schermafbeelding met de duur van de aanvraag van 924](../media/343571f2-a249-4de2-bc11-2cee93498aea.png)
  
 <span data-ttu-id="0bb9a-124">**SPRequestDuration** geeft de hoeveelheid werk aan die op de server wordt uitgevoerd om de pagina voor te bereiden.</span><span class="sxs-lookup"><span data-stu-id="0bb9a-124">**SPRequestDuration** indicates the amount of work that is done on the server to prepare the page.</span></span> <span data-ttu-id="0bb9a-125">Als u van inhoud op query wisselt Webonderdelen inhoud op zoekfunctie, Webonderdelen de tijd die nodig is om de pagina weer te geven aanzienlijk.</span><span class="sxs-lookup"><span data-stu-id="0bb9a-125">Switching Content by Query Web Parts with Content by Search Web Parts dramatically reduces the time it takes to render the page.</span></span> <span data-ttu-id="0bb9a-126">Een pagina met een vergelijkbaar webonderdeel Inhoud zoeken, die hetzelfde aantal resultaten retourneert, heeft daarentegen een **SPRequestDuration-waarde** van 106 milliseconden, zoals wordt weergegeven in deze schermafbeelding:</span><span class="sxs-lookup"><span data-stu-id="0bb9a-126">By contrast, a page with an equivalent Content Search Web Part, returning the same number of results has an **SPRequestDuration** value of 106 milliseconds as shown in this screen shot:</span></span> 
  
![Schermafbeelding met aanvraagduur van 106](../media/b46387ac-660d-4e5e-a11c-cc430e912962.png)
  
## <a name="adding-a-content-search-web-part-in-sharepoint-online"></a><span data-ttu-id="0bb9a-128">Een webonderdeel Inhoud zoeken toevoegen in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="0bb9a-128">Adding a Content Search Web Part in SharePoint Online</span></span>

<span data-ttu-id="0bb9a-129">Het toevoegen van een webonderdeel Inhoud zoeken lijkt sterk op een gewoon webonderdeel Inhoudsquery.</span><span class="sxs-lookup"><span data-stu-id="0bb9a-129">Adding a Content Search Web Part is very similar to a regular Content Query Web Part.</span></span> <span data-ttu-id="0bb9a-130">Zie de sectie *'Een webonderdeel* Inhoud zoeken toevoegen' in Een webonderdeel Inhoud zoeken [configureren in SharePoint.](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a)</span><span class="sxs-lookup"><span data-stu-id="0bb9a-130">See the section  *"Add a Content Search Web Part"*  in [Configure a Content Search Web Part in SharePoint](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a).</span></span>
  
## <a name="creating-the-right-search-query-for-your-content-search-web-part"></a><span data-ttu-id="0bb9a-131">De juiste zoekquery maken voor het webonderdeel Inhoud zoeken</span><span class="sxs-lookup"><span data-stu-id="0bb9a-131">Creating the right search query for your Content Search Web Part</span></span>

<span data-ttu-id="0bb9a-132">Nadat u een webonderdeel Inhoud zoeken hebt toegevoegd, kunt u de zoekopdracht verfijnen en de gezochte items retourneren.</span><span class="sxs-lookup"><span data-stu-id="0bb9a-132">Once you have added a Content Search Web Part, you can refine the search and return the items you want.</span></span> <span data-ttu-id="0bb9a-133">Zie de sectie 'Inhoud weergeven door een geavanceerde *query in* een webonderdeel Inhoud zoeken te configureren' in Een webonderdeel Inhoud zoeken configureren [in](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a)SharePoint.</span><span class="sxs-lookup"><span data-stu-id="0bb9a-133">For detailed instructions on how to do this, see the section,  *"Display content by configuring an advanced query in a Content Search Web Part"*  in [Configure a Content Search Web Part in SharePoint](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a).</span></span>
  
## <a name="query-building-and-testing-tool"></a><span data-ttu-id="0bb9a-134">Hulpprogramma voor het maken en testen van query's</span><span class="sxs-lookup"><span data-stu-id="0bb9a-134">Query building and testing tool</span></span>

<span data-ttu-id="0bb9a-135">Zie het hulpprogramma Zoekquery op Codeplex voor een hulpprogramma voor het maken en testen van complexe query's. [](https://sp2013searchtool.codeplex.com/)</span><span class="sxs-lookup"><span data-stu-id="0bb9a-135">For a tool to build and test complex queries, see the [Search Query Tool](https://sp2013searchtool.codeplex.com/) on Codeplex.</span></span> 
  

