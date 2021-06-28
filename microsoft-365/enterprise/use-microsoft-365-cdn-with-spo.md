---
title: Gebruik Office 365 Content Delivery Network (CDN) met SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 2/19/2020
audience: ITPro
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
ms.assetid: bebb285f-1d54-4f79-90a5-94985afc6af8
description: Lees hoe u de Office 365 Content Delivery Network (CDN) kunt gebruiken om de levering van uw SharePoint Online-assets te versnellen.
ms.openlocfilehash: e6cce93be0e8d893d68ae8bcdb15fde325a2cb59
ms.sourcegitcommit: 5866e45a6a4e90c661e8f90c91550a9872b68e03
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/28/2021
ms.locfileid: "53169554"
---
# <a name="use-the-office-365-content-delivery-network-cdn-with-sharepoint-online"></a><span data-ttu-id="e7358-103">De Office 365 Content Delivery Network (CDN) gebruiken met SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="e7358-103">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>

<span data-ttu-id="e7358-104">U kunt de ingebouwde Office 365 Content Delivery Network (CDN) gebruiken om statische assets te hosten om betere prestaties te bieden voor uw SharePoint Online-pagina's.</span><span class="sxs-lookup"><span data-stu-id="e7358-104">You can use the built-in Office 365 Content Delivery Network (CDN) to host static assets to provide better performance for your SharePoint Online pages.</span></span> <span data-ttu-id="e7358-105">De Office 365 CDN verbetert de prestaties door statische assets dichter bij de browsers te houden waarin ze worden gevraagd, wat helpt om downloads te versnellen en de latentie te verminderen.</span><span class="sxs-lookup"><span data-stu-id="e7358-105">The Office 365 CDN improves performance by caching static assets closer to the browsers requesting them, which helps to speed up downloads and reduce latency.</span></span> <span data-ttu-id="e7358-106">De Office 365 CDN gebruikt ook het [HTTP/2-protocol](https://en.wikipedia.org/wiki/HTTP/2) voor verbeterde compressie en HTTP-pipelineing.</span><span class="sxs-lookup"><span data-stu-id="e7358-106">Also, the Office 365 CDN uses the [HTTP/2 protocol](https://en.wikipedia.org/wiki/HTTP/2) for improved compression and HTTP pipelining.</span></span> <span data-ttu-id="e7358-107">De Office 365 CDN service is opgenomen als onderdeel van uw SharePoint Online-abonnement.</span><span class="sxs-lookup"><span data-stu-id="e7358-107">The Office 365 CDN service is included as part of your SharePoint Online subscription.</span></span>

> [!NOTE]
> <span data-ttu-id="e7358-108">De Office 365 CDN is alleen beschikbaar voor tenants in de **productiecloud** (wereldwijd).</span><span class="sxs-lookup"><span data-stu-id="e7358-108">The Office 365 CDN is only available to tenants in the **Production** (worldwide) cloud.</span></span> <span data-ttu-id="e7358-109">Tenants in de amerikaanse overheid, China en Duitsland clouds ondersteunen momenteel de Office 365 CDN.</span><span class="sxs-lookup"><span data-stu-id="e7358-109">Tenants in the US Government, China and Germany clouds do not currently support the Office 365 CDN.</span></span>

<span data-ttu-id="e7358-110">De Office 365 CDN bestaat uit meerdere CDN's waarmee u statische assets op meerdere locaties of _origins_ kunt hosten en deze kunt gebruiken vanuit globale snelle netwerken.</span><span class="sxs-lookup"><span data-stu-id="e7358-110">The Office 365 CDN is composed of multiple CDNs that allow you to host static assets in multiple locations, or _origins_, and serve them from global high-speed networks.</span></span> <span data-ttu-id="e7358-111">Afhankelijk van het type inhoud dat u wilt hosten in  de Office 365 CDN, kunt u openbare origins, **privé-origins** of beide toevoegen.</span><span class="sxs-lookup"><span data-stu-id="e7358-111">Depending on the kind of content you want to host in the Office 365 CDN, you can add **public** origins, **private** origins or both.</span></span> <span data-ttu-id="e7358-112">Zie [Kiezen of elke origin openbaar](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate) of privé moet zijn voor meer informatie over het verschil tussen openbare en private origins.</span><span class="sxs-lookup"><span data-stu-id="e7358-112">See [Choose whether each origin should be public or private](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate) for more information on the difference between public and private origins.</span></span>

<span data-ttu-id="e7358-113">![Office 365 CDN conceptueel diagram](../media/O365-CDN/o365-cdn-flow-transparent.svg "Office 365 CDN conceptueel diagram")</span><span class="sxs-lookup"><span data-stu-id="e7358-113">![Office 365 CDN conceptual diagram](../media/O365-CDN/o365-cdn-flow-transparent.svg "Office 365 CDN conceptual diagram")</span></span>

<span data-ttu-id="e7358-114">Als u al bekend bent met de manier waarop CDN's werken, hoeft u slechts een paar stappen uit te voeren om de Office 365 CDN voor uw tenant in te stellen.</span><span class="sxs-lookup"><span data-stu-id="e7358-114">If you are already familiar with the way that CDNs work, you only need to complete a few steps to enable the Office 365 CDN for your tenant.</span></span> <span data-ttu-id="e7358-115">In dit onderwerp wordt beschreven hoe.</span><span class="sxs-lookup"><span data-stu-id="e7358-115">This topic describes how.</span></span> <span data-ttu-id="e7358-116">Lees verder voor informatie over hoe u aan de slag kunt met het hosten van uw statische assets.</span><span class="sxs-lookup"><span data-stu-id="e7358-116">Read on for information about how to get started hosting your static assets.</span></span>

> [!TIP]
> <span data-ttu-id="e7358-117">Er zijn andere door Microsoft gehoste CDN's die kunnen worden gebruikt met Office 365 voor gespecialiseerde gebruiksscenario's, maar worden niet besproken in dit onderwerp omdat ze buiten het bereik van de Office 365 CDN.</span><span class="sxs-lookup"><span data-stu-id="e7358-117">There are other Microsoft-hosted CDNs that can be used with Office 365 for specialized usage scenarios, but are not discussed in this topic because they fall outside the scope of the Office 365 CDN.</span></span> <span data-ttu-id="e7358-118">Zie Andere [Microsoft CDN's](content-delivery-networks.md#other-microsoft-cdns)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="e7358-118">For more information, see [Other Microsoft CDNs](content-delivery-networks.md#other-microsoft-cdns).</span></span>

 <span data-ttu-id="e7358-119">**Ga terug naar [Netwerkplanning en prestatieafstemming voor Office 365.](./network-planning-and-performance.md)**</span><span class="sxs-lookup"><span data-stu-id="e7358-119">**Head back to [Network planning and performance tuning for Office 365](./network-planning-and-performance.md).**</span></span>

## <a name="overview-of-working-with-the-office-365-cdn-in-sharepoint-online"></a><span data-ttu-id="e7358-120">Overzicht van het werken met de Office 365 CDN in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="e7358-120">Overview of working with the Office 365 CDN in SharePoint Online</span></span>

<span data-ttu-id="e7358-121">Als u de Office 365 CDN voor uw organisatie wilt instellen, volgt u de volgende basisstappen:</span><span class="sxs-lookup"><span data-stu-id="e7358-121">To set up the Office 365 CDN for your organization, you follow these basic steps:</span></span>

+ [<span data-ttu-id="e7358-122">Plannen voor implementatie van de Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="e7358-122">Plan for deployment of the Office 365 CDN</span></span>](use-microsoft-365-cdn-with-spo.md#plan-for-deployment-of-the-office-365-cdn)

  + <span data-ttu-id="e7358-123">[Bepaal welke statische assets u wilt hosten op de CDN.](use-microsoft-365-cdn-with-spo.md#CDNAssets)</span><span class="sxs-lookup"><span data-stu-id="e7358-123">[Determine which static assets you want to host on the CDN](use-microsoft-365-cdn-with-spo.md#CDNAssets).</span></span>
  + <span data-ttu-id="e7358-124">[Bepaal waar u uw activa wilt opslaan.](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets)</span><span class="sxs-lookup"><span data-stu-id="e7358-124">[Determine where you want to store your assets](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets).</span></span> <span data-ttu-id="e7358-125">Deze locatie kan een SharePoint site, bibliotheek of map zijn en wordt een _origin genoemd._</span><span class="sxs-lookup"><span data-stu-id="e7358-125">This location can be a SharePoint site, library or folder and is called an _origin_.</span></span>
  + <span data-ttu-id="e7358-126">[Kies of elke origin openbaar of privé moet zijn.](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)</span><span class="sxs-lookup"><span data-stu-id="e7358-126">[Choose whether each origin should be public or private](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate).</span></span> <span data-ttu-id="e7358-127">U kunt meerdere origins van zowel openbare als privétypen toevoegen.</span><span class="sxs-lookup"><span data-stu-id="e7358-127">You can add multiple origins of both public and private types.</span></span>

+ <span data-ttu-id="e7358-128">De CDN instellen en configureren met PowerShell of SharePoint Online CLI</span><span class="sxs-lookup"><span data-stu-id="e7358-128">Set up and configure the CDN, using either PowerShell or the SharePoint Online CLI</span></span>

  + [<span data-ttu-id="e7358-129">De CDN instellen en configureren met de SharePoint Online Management Shell</span><span class="sxs-lookup"><span data-stu-id="e7358-129">Set up and configure the CDN by using the SharePoint Online Management Shell</span></span>](use-microsoft-365-cdn-with-spo.md#CDNSetupinPShell)
  + [<span data-ttu-id="e7358-130">De CDN instellen en configureren met PnP PowerShell</span><span class="sxs-lookup"><span data-stu-id="e7358-130">Set up and configure the CDN by using PnP PowerShell</span></span>](use-microsoft-365-cdn-with-spo.md#CDNSetupinPnPPosh)
  + [<span data-ttu-id="e7358-131">De CDN instellen en configureren met de Office 365 CLI</span><span class="sxs-lookup"><span data-stu-id="e7358-131">Set up and configure the CDN by using the Office 365 CLI</span></span>](use-microsoft-365-cdn-with-spo.md#CDNSetupinCLI)

  <span data-ttu-id="e7358-132">Wanneer u deze stap voltooit, hebt u het volgende:</span><span class="sxs-lookup"><span data-stu-id="e7358-132">When you complete this step, you will have:</span></span>

  + <span data-ttu-id="e7358-133">De CDN voor uw organisatie ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="e7358-133">Enabled the CDN for your organization.</span></span>
  + <span data-ttu-id="e7358-134">U hebt uw origins toegevoegd, die elke origin als openbaar of privé identificeren.</span><span class="sxs-lookup"><span data-stu-id="e7358-134">Added your origins, identifying each origin as public or private.</span></span>

<span data-ttu-id="e7358-135">Nadat u klaar bent met instellen, kunt u [de](use-microsoft-365-cdn-with-spo.md#CDNManage) Office 365 CDN in de tijd beheren door:</span><span class="sxs-lookup"><span data-stu-id="e7358-135">Once you're done with setup, you can [Manage the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNManage) over time by:</span></span>
  
+ <span data-ttu-id="e7358-136">Activa toevoegen, bijwerken en verwijderen</span><span class="sxs-lookup"><span data-stu-id="e7358-136">Adding, updating, and removing assets</span></span>
+ <span data-ttu-id="e7358-137">Origins toevoegen en verwijderen</span><span class="sxs-lookup"><span data-stu-id="e7358-137">Adding and removing origins</span></span>
+ <span data-ttu-id="e7358-138">Beleidsregels CDN configureren</span><span class="sxs-lookup"><span data-stu-id="e7358-138">Configuring CDN policies</span></span>
+ <span data-ttu-id="e7358-139">Als dat nodig is, kunt u de CDN</span><span class="sxs-lookup"><span data-stu-id="e7358-139">If necessary, disabling the CDN</span></span>

<span data-ttu-id="e7358-140">Zie Ten slotte [Uw CDN gebruiken voor](use-microsoft-365-cdn-with-spo.md#using-your-cdn-assets) meer informatie over toegang tot uw CDN activa van zowel openbare als privé-origins.</span><span class="sxs-lookup"><span data-stu-id="e7358-140">Finally, see [Using your CDN assets](use-microsoft-365-cdn-with-spo.md#using-your-cdn-assets) to learn about accessing your CDN assets from both public and private origins.</span></span>

<span data-ttu-id="e7358-141">Zie [Problemen oplossen Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting) voor richtlijnen voor het oplossen van veelvoorkomende problemen.</span><span class="sxs-lookup"><span data-stu-id="e7358-141">See [Troubleshooting the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting) for guidance on resolving common issues.</span></span>

## <a name="plan-for-deployment-of-the-office-365-cdn"></a><span data-ttu-id="e7358-142">Plannen voor implementatie van de Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="e7358-142">Plan for deployment of the Office 365 CDN</span></span>

<span data-ttu-id="e7358-143">Voordat u de Office 365 CDN voor uw Office 365 tenant implementeert, moet u rekening houden met de volgende factoren als onderdeel van uw planningsproces.</span><span class="sxs-lookup"><span data-stu-id="e7358-143">Before you deploy the Office 365 CDN for your Office 365 tenant, you should consider the following factors as part of your planning process.</span></span>

  + [<span data-ttu-id="e7358-144">Bepalen welke statische assets u wilt hosten op de CDN</span><span class="sxs-lookup"><span data-stu-id="e7358-144">Determine which static assets you want to host on the CDN</span></span>](use-microsoft-365-cdn-with-spo.md#CDNAssets)
  + [<span data-ttu-id="e7358-145">Bepalen waar u uw assets wilt opslaan</span><span class="sxs-lookup"><span data-stu-id="e7358-145">Determine where you want to store your assets</span></span>](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets)
  + [<span data-ttu-id="e7358-146">Kies of elke origin openbaar of privé moet zijn</span><span class="sxs-lookup"><span data-stu-id="e7358-146">Choose whether each origin should be public or private</span></span>](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)

<span data-ttu-id="e7358-147"><a name="CDNAssets"> </a></span><span class="sxs-lookup"><span data-stu-id="e7358-147"><a name="CDNAssets"> </a></span></span>
### <a name="determine-which-static-assets-you-want-to-host-on-the-cdn"></a><span data-ttu-id="e7358-148">Bepalen welke statische assets u wilt hosten op de CDN</span><span class="sxs-lookup"><span data-stu-id="e7358-148">Determine which static assets you want to host on the CDN</span></span>

<span data-ttu-id="e7358-149">CdN's zijn over het algemeen het meest effectief voor het hosten van _statische_ activa of activa die niet vaak veranderen.</span><span class="sxs-lookup"><span data-stu-id="e7358-149">In general, CDNs are most effective for hosting _static assets_, or assets that don't change very often.</span></span> <span data-ttu-id="e7358-150">Een goede vuistregel is om bestanden te identificeren die voldoen aan bepaalde of al deze voorwaarden:</span><span class="sxs-lookup"><span data-stu-id="e7358-150">A good rule of thumb is to identify files that meet some or all of these conditions:</span></span>

+ <span data-ttu-id="e7358-151">Statische bestanden die zijn ingesloten in een pagina (zoals scripts en afbeeldingen) die een aanzienlijk incrementeel effect kunnen hebben op laadtijden van pagina's</span><span class="sxs-lookup"><span data-stu-id="e7358-151">Static files embedded in a page (like scripts and images) that may have a significant incremental impact on page load times</span></span>
+ <span data-ttu-id="e7358-152">Grote bestanden, zoals uitvoerbare bestanden en installatiebestanden</span><span class="sxs-lookup"><span data-stu-id="e7358-152">Large files like executables and installation files</span></span>
+ <span data-ttu-id="e7358-153">Resourcebibliotheken die clientcode ondersteunen</span><span class="sxs-lookup"><span data-stu-id="e7358-153">Resource libraries that support client-side code</span></span>

<span data-ttu-id="e7358-154">Kleine bestanden die herhaaldelijk worden aangevraagd, zoals siteafbeeldingen en scripts, kunnen bijvoorbeeld de prestaties van siterendering aanzienlijk verbeteren en de belasting op uw SharePoint Online-sites stapsgewijs verminderen wanneer u ze toevoegt aan een CDN origin.</span><span class="sxs-lookup"><span data-stu-id="e7358-154">For example, small files that are repeatedly requested like site images and scripts can significantly improve site rendering performance and incrementally reduce the load on your SharePoint Online sites when you add them to a CDN origin.</span></span> <span data-ttu-id="e7358-155">Grotere bestanden, zoals installatieuitvoerbare bestanden, kunnen worden gedownload van de CDN, wat een positief effect heeft op de prestaties en de belasting op uw SharePoint Online-site, zelfs als ze niet zo vaak worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="e7358-155">Larger files such as installation executables can be downloaded from the CDN, delivering a positive performance impact and subsequent reduction of the load on your SharePoint Online site, even if they are not accessed as often.</span></span>

<span data-ttu-id="e7358-156">Prestatieverbetering per bestand is afhankelijk van een groot aantal factoren, waaronder de nabijheid van de client tot het dichtstbijzijnde CDN eindpunt, tijdelijke voorwaarden op het lokale netwerk, enzovoort.</span><span class="sxs-lookup"><span data-stu-id="e7358-156">Performance improvement on a per-file basis is dependent on many factors, including the client's proximity to the nearest CDN endpoint, transient conditions on the local network, and so forth.</span></span> <span data-ttu-id="e7358-157">Veel statische bestanden zijn vrij klein en kunnen in minder dan Office 365 worden gedownload.</span><span class="sxs-lookup"><span data-stu-id="e7358-157">Many static files are quite small, and can be downloaded from Office 365 in less than a second.</span></span> <span data-ttu-id="e7358-158">Een webpagina kan echter veel ingesloten bestanden bevatten met een cumulatieve downloadtijd van enkele seconden.</span><span class="sxs-lookup"><span data-stu-id="e7358-158">However, a web page may contain many embedded files with a cumulative download time of several seconds.</span></span> <span data-ttu-id="e7358-159">Als u deze bestanden vanuit de CDN kunt u de totale laadtijd van de pagina aanzienlijk verminderen.</span><span class="sxs-lookup"><span data-stu-id="e7358-159">Serving these files from the CDN can significantly reduce the overall page load time.</span></span> <span data-ttu-id="e7358-160">Zie [Welke prestatiewinst levert een CDN?](content-delivery-networks.md#what-performance-gains-does-a-cdn-provide) voor een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="e7358-160">See [What performance gains does a CDN provide?](content-delivery-networks.md#what-performance-gains-does-a-cdn-provide) for an example.</span></span>

<span data-ttu-id="e7358-161"><a name="CDNStoreAssets"> </a></span><span class="sxs-lookup"><span data-stu-id="e7358-161"><a name="CDNStoreAssets"> </a></span></span>
### <a name="determine-where-you-want-to-store-your-assets"></a><span data-ttu-id="e7358-162">Bepalen waar u uw assets wilt opslaan</span><span class="sxs-lookup"><span data-stu-id="e7358-162">Determine where you want to store your assets</span></span>

<span data-ttu-id="e7358-163">De CDN haalt uw activa op van een locatie die een origin _wordt genoemd._</span><span class="sxs-lookup"><span data-stu-id="e7358-163">The CDN fetches your assets from a location called an _origin_.</span></span> <span data-ttu-id="e7358-164">Een origin kan een SharePoint site, documentbibliotheek of map zijn die toegankelijk is via een URL.</span><span class="sxs-lookup"><span data-stu-id="e7358-164">An origin can be a SharePoint site, document library or folder that is accessible by a URL.</span></span> <span data-ttu-id="e7358-165">U hebt grote flexibiliteit wanneer u origins voor uw organisatie opgeeft.</span><span class="sxs-lookup"><span data-stu-id="e7358-165">You have great flexibility when you specify origins for your organization.</span></span> <span data-ttu-id="e7358-166">U kunt bijvoorbeeld meerdere origins of één origin opgeven waar u al uw CDN wilt plaatsen.</span><span class="sxs-lookup"><span data-stu-id="e7358-166">For example, you can specify multiple origins or a single origin where you want to put all your CDN assets.</span></span> <span data-ttu-id="e7358-167">U kunt ervoor kiezen om zowel openbare als persoonlijke origins voor uw organisatie te hebben.</span><span class="sxs-lookup"><span data-stu-id="e7358-167">You can choose to have both public or private origins for your organization.</span></span> <span data-ttu-id="e7358-168">De meeste organisaties kiezen ervoor om een combinatie van de twee te implementeren.</span><span class="sxs-lookup"><span data-stu-id="e7358-168">Most organizations will choose to implement a combination of the two.</span></span>

<span data-ttu-id="e7358-169">U kunt nieuwe containers maken voor uw origins, zoals mappen of documentbibliotheken, en bestanden toevoegen die u beschikbaar wilt maken vanaf de CDN.</span><span class="sxs-lookup"><span data-stu-id="e7358-169">You can create new container for your origins such as folders or document libraries, and add files you want to make available from the CDN.</span></span> <span data-ttu-id="e7358-170">Dit is een goede methode als u een specifieke set activa hebt die u beschikbaar wilt hebben in de CDN en u de set CDN-assets wilt beperken tot alleen die bestanden in de container.</span><span class="sxs-lookup"><span data-stu-id="e7358-170">This is a good approach if you have a specific set of assets you want to be available from the CDN, and want to restrict the set of CDN assets to only those files in the container.</span></span>

<span data-ttu-id="e7358-171">U kunt ook een bestaande siteverzameling, site, bibliotheek of map configureren als origin, zodat alle in aanmerking komende activa in de container beschikbaar zijn vanaf de CDN.</span><span class="sxs-lookup"><span data-stu-id="e7358-171">You can also configure an existing site collection, site, library or folder as an origin, which will make all eligible assets in the container available from the CDN.</span></span> <span data-ttu-id="e7358-172">Voordat u een bestaande container als origin toevoegt, is het belangrijk dat u op de hoogte bent van de inhoud en machtigingen, zodat u activa niet per ongeluk blootstelt aan anonieme toegang of niet-geautoriseerde gebruikers.</span><span class="sxs-lookup"><span data-stu-id="e7358-172">Before you add an existing container as an origin, it's important to make sure you are aware of its contents and permissions so you do not inadvertently expose assets to anonymous access or unauthorized users.</span></span>

<span data-ttu-id="e7358-173">U kunt een _CDN definiëren om_ inhoud in uw origins uit te sluiten van de CDN.</span><span class="sxs-lookup"><span data-stu-id="e7358-173">You can define _CDN policies_ to exclude content in your origins from the CDN.</span></span> <span data-ttu-id="e7358-174">CDN beleidsregels sluiten activa in openbare of privé-origins uit op basis van kenmerken zoals bestandstype en _siteclassificatie_ en worden toegepast op alle origins van het CdnType (privé of openbaar) dat u opgeeft in het beleid. </span><span class="sxs-lookup"><span data-stu-id="e7358-174">CDN policies exclude assets in public or private origins by attributes such as _file type_ and _site classification_, and are applied to all origins of the CdnType (private or public) you specify in the policy.</span></span> <span data-ttu-id="e7358-175">Als u bijvoorbeeld een privé-origin toevoegt die bestaat uit een site die meerdere subsites bevat, kunt u een beleid definiëren om sites uit te sluiten die zijn gemarkeerd als Vertrouwelijk, zodat inhoud van sites met die classificatie wordt toegepast, niet wordt gebruikt vanaf de CDN. </span><span class="sxs-lookup"><span data-stu-id="e7358-175">For example, if you add a private origin consisting of a site that contains multiple subsites, you can define a policy to exclude sites marked as **Confidential** so content from sites with that classification applied will not be served from the CDN.</span></span> <span data-ttu-id="e7358-176">Het beleid is van toepassing op inhoud van _alle_ persoonlijke origins die u hebt toegevoegd aan de CDN.</span><span class="sxs-lookup"><span data-stu-id="e7358-176">The policy will apply to content from _all_ private origins you have added to the CDN.</span></span>
  
<span data-ttu-id="e7358-177">Houd er rekening mee dat hoe groter het aantal origins, hoe groter de impact op de tijd die de service CDN om aanvragen te verwerken.</span><span class="sxs-lookup"><span data-stu-id="e7358-177">Keep in mind that the greater the number of origins, the greater the impact on the time it takes the CDN service to process requests.</span></span> <span data-ttu-id="e7358-178">U wordt aangeraden het aantal origins zo veel mogelijk te beperken.</span><span class="sxs-lookup"><span data-stu-id="e7358-178">We recommend that you limit the number of origins as much as possible.</span></span>
  
<span data-ttu-id="e7358-179"><a name="CDNOriginChoosePublicPrivate"> </a></span><span class="sxs-lookup"><span data-stu-id="e7358-179"><a name="CDNOriginChoosePublicPrivate"> </a></span></span>
### <a name="choose-whether-each-origin-should-be-public-or-private"></a><span data-ttu-id="e7358-180">Kies of elke origin openbaar of privé moet zijn</span><span class="sxs-lookup"><span data-stu-id="e7358-180">Choose whether each origin should be public or private</span></span>

<span data-ttu-id="e7358-181">Wanneer u een origin identificeert, geeft u aan of deze openbaar of _privé_ moet _worden gemaakt._</span><span class="sxs-lookup"><span data-stu-id="e7358-181">When you identify an origin, you specify whether it should be made _public_ or _private_.</span></span> <span data-ttu-id="e7358-182">Toegang tot CDN activa in openbare origins is anoniem en CDN inhoud in privé-origins wordt beveiligd door dynamisch gegenereerde tokens voor meer beveiliging.</span><span class="sxs-lookup"><span data-stu-id="e7358-182">Access to CDN assets in public origins is anonymous, and CDN content in private origins is secured by dynamically generated tokens for greater security.</span></span> <span data-ttu-id="e7358-183">Ongeacht welke optie u kiest, Microsoft doet al het zware werk voor u als het gaat om het beheer van de CDN zelf.</span><span class="sxs-lookup"><span data-stu-id="e7358-183">Regardless of which option you choose, Microsoft does all the heavy lifting for you when it comes to administration of the CDN itself.</span></span> <span data-ttu-id="e7358-184">U kunt ook later van gedachten veranderen nadat u de CDN hebt ingesteld en uw origins hebt geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="e7358-184">Also, you can change your mind later, after you've set up the CDN and identified your origins.</span></span>

<span data-ttu-id="e7358-185">Openbare en private opties bieden vergelijkbare prestatieverbeteringen, maar elk heeft unieke kenmerken en voordelen.</span><span class="sxs-lookup"><span data-stu-id="e7358-185">Both public and private options provide similar performance gains, but each has unique attributes and advantages.</span></span>

<span data-ttu-id="e7358-186">**Openbare** origins binnen de Office 365 CDN zijn anoniem toegankelijk en gehoste assets kunnen worden gebruikt door iedereen die de URL van het activum heeft.</span><span class="sxs-lookup"><span data-stu-id="e7358-186">**Public** origins within the Office 365 CDN are accessible anonymously, and hosted assets can be accessed by anyone who has the URL to the asset.</span></span> <span data-ttu-id="e7358-187">Omdat toegang tot inhoud in openbare origins anoniem is, moet u deze alleen gebruiken om niet-gevoelige algemene inhoud in de cache op te slaan, zoals JavaScript-bestanden, scripts, pictogrammen en afbeeldingen.</span><span class="sxs-lookup"><span data-stu-id="e7358-187">Because access to content in public origins is anonymous, you should only use them to cache non-sensitive generic content such as JavaScript files, scripts, icons and images.</span></span>

<span data-ttu-id="e7358-188">**Privé-origins** binnen de Office 365 CDN bieden persoonlijke toegang tot gebruikersinhoud, zoals SharePoint Online-documentbibliotheken, sites en eigen afbeeldingen.</span><span class="sxs-lookup"><span data-stu-id="e7358-188">**Private** origins within the Office 365 CDN provide private access to user content such as SharePoint Online document libraries, sites and proprietary images.</span></span> <span data-ttu-id="e7358-189">Toegang tot inhoud in privé-origins wordt beveiligd door dynamisch gegenereerde tokens, zodat deze alleen toegankelijk is voor gebruikers met machtigingen voor de oorspronkelijke documentbibliotheek of opslaglocatie.</span><span class="sxs-lookup"><span data-stu-id="e7358-189">Access to content in private origins is secured by dynamically generated tokens so it can only be accessed by users with permissions to the original document library or storage location.</span></span> <span data-ttu-id="e7358-190">Privé-origins in de Office 365 CDN kunnen alleen worden gebruikt voor SharePoint Online-inhoud en u hebt alleen toegang tot activa in privé-origins via omleiding vanuit uw SharePoint Online-tenant.</span><span class="sxs-lookup"><span data-stu-id="e7358-190">Private origins in the Office 365 CDN can only be used for SharePoint Online content, and you can only access assets in private origins through redirection from your SharePoint Online tenant.</span></span>

<span data-ttu-id="e7358-191">U kunt meer informatie lezen over hoe CDN toegang tot activa in een persoonlijke origin werkt in [Assets gebruiken in private origins.](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)</span><span class="sxs-lookup"><span data-stu-id="e7358-191">You can read more about how CDN access to assets in a private origin works in [Using assets in private origins](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins).</span></span>

#### <a name="attributes-and-advantages-of-hosting-assets-in-public-origins"></a><span data-ttu-id="e7358-192">Kenmerken en voordelen van het hosten van activa in openbare origins</span><span class="sxs-lookup"><span data-stu-id="e7358-192">Attributes and advantages of hosting assets in public origins</span></span>
  
+ <span data-ttu-id="e7358-193">Activa die in een openbare origin worden getoond, zijn anoniem toegankelijk voor iedereen.</span><span class="sxs-lookup"><span data-stu-id="e7358-193">Assets exposed in a public origin are accessible by everyone anonymously.</span></span>
    > [!IMPORTANT]
    > <span data-ttu-id="e7358-194">U mag nooit resources plaatsen die gebruikersgegevens bevatten of die als gevoelig voor uw organisatie worden beschouwd in een openbare origin.</span><span class="sxs-lookup"><span data-stu-id="e7358-194">You should never place resources that contain user information or are considered sensitive to your organization in a public origin.</span></span>

+ <span data-ttu-id="e7358-195">Als u een activum uit een openbare origin verwijdert, is het activum mogelijk nog maximaal 30 dagen beschikbaar in de cache. De koppelingen naar het activum worden binnen 15 minuten CDN ongeldig.</span><span class="sxs-lookup"><span data-stu-id="e7358-195">If you remove an asset from a public origin, the asset may continue to be available for up to 30 days from the cache; however, we will invalidate links to the asset in the CDN within 15 minutes.</span></span>

+ <span data-ttu-id="e7358-196">Wanneer u stijlbladen (CSS-bestanden) host in een openbare origin, kunt u relatieve paden en URL's binnen de code gebruiken.</span><span class="sxs-lookup"><span data-stu-id="e7358-196">When you host style sheets (CSS files) in a public origin, you can use relative paths and URIs within the code.</span></span> <span data-ttu-id="e7358-197">Dit betekent dat u kunt verwijzen naar de locatie van achtergrondafbeeldingen en andere objecten ten opzichte van de locatie van het activum dat de activum aanroept.</span><span class="sxs-lookup"><span data-stu-id="e7358-197">This means that you can reference the location of background images and other objects relative to the location of the asset that's calling it.</span></span>

+ <span data-ttu-id="e7358-198">Hoewel u de URL van een openbare origin kunt maken, moet u voorzichtig te werk gaan en ervoor zorgen dat u de context-eigenschap pagina gebruikt en de richtlijnen volgt om dit te doen.</span><span class="sxs-lookup"><span data-stu-id="e7358-198">While you can construct a public origin's URL, you should proceed with caution and ensure you utilize the page context property and follow the guidance for doing so.</span></span> <span data-ttu-id="e7358-199">De reden hiervoor is dat als de toegang tot de CDN niet beschikbaar wordt, de URL niet automatisch wordt opgelost voor uw organisatie in SharePoint Online en kan leiden tot verbroken koppelingen en andere fouten.</span><span class="sxs-lookup"><span data-stu-id="e7358-199">The reason for this is that if access to the CDN becomes unavailable, the URL will not automatically resolve to your organization in SharePoint Online and might result in broken links and other errors.</span></span> <span data-ttu-id="e7358-200">De URL kan ook worden gewijzigd. Daarom moet de URL niet alleen hard worden gecodeerd naar de huidige waarde.</span><span class="sxs-lookup"><span data-stu-id="e7358-200">The URL is also subject to change which is why it should not just be hard coded to its current value.</span></span>

+ <span data-ttu-id="e7358-201">De standaardbestandstypen die zijn opgenomen voor openbare origins zijn .css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff en .woff2.</span><span class="sxs-lookup"><span data-stu-id="e7358-201">The default file types that are included for public origins are .css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff and .woff2.</span></span> <span data-ttu-id="e7358-202">U kunt extra bestandstypen opgeven.</span><span class="sxs-lookup"><span data-stu-id="e7358-202">You can specify additional file types.</span></span>

+ <span data-ttu-id="e7358-203">U kunt een beleid configureren om activa uit te sluiten die zijn geïdentificeerd met siteclassificaties die u opgeeft.</span><span class="sxs-lookup"><span data-stu-id="e7358-203">You can configure a policy to exclude assets that have been identified by site classifications that you specify.</span></span> <span data-ttu-id="e7358-204">U kunt er bijvoorbeeld voor kiezen om alle activa uit te sluiten die zijn gemarkeerd als 'vertrouwelijk' of 'beperkt', zelfs als ze een toegestaan bestandstype zijn en zich in een openbare origin bevinden.</span><span class="sxs-lookup"><span data-stu-id="e7358-204">For example, you can choose to exclude all assets that are marked as "confidential" or "restricted" even if they are an allowed file type and are located in a public origin.</span></span>

#### <a name="attributes-and-advantages-of-hosting-assets-in-private-origins"></a><span data-ttu-id="e7358-205">Kenmerken en voordelen van hostingactiva in privé-origins</span><span class="sxs-lookup"><span data-stu-id="e7358-205">Attributes and advantages of hosting assets in private origins</span></span>

+ <span data-ttu-id="e7358-206">Privé-origins kunnen alleen worden gebruikt voor SharePoint onlineactiva.</span><span class="sxs-lookup"><span data-stu-id="e7358-206">Private origins can only be used for SharePoint Online assets.</span></span>

+ <span data-ttu-id="e7358-207">Gebruikers hebben alleen toegang tot de assets van een persoonlijke origin als ze machtigingen hebben voor toegang tot de container.</span><span class="sxs-lookup"><span data-stu-id="e7358-207">Users can only access the assets from a private origin if they have permissions to access the container.</span></span> <span data-ttu-id="e7358-208">Anonieme toegang tot deze activa wordt voorkomen.</span><span class="sxs-lookup"><span data-stu-id="e7358-208">Anonymous access to these assets is prevented.</span></span>

+ <span data-ttu-id="e7358-209">Activa in privé-origins moeten worden verwezen vanuit de SharePoint Online-tenant.</span><span class="sxs-lookup"><span data-stu-id="e7358-209">Assets in private origins must be referred from the SharePoint Online tenant.</span></span> <span data-ttu-id="e7358-210">Directe toegang tot privé-CDN werkt niet.</span><span class="sxs-lookup"><span data-stu-id="e7358-210">Direct access to private CDN assets does not work.</span></span>

+ <span data-ttu-id="e7358-211">Als u een activum uit de privé-origin verwijdert, is het activum mogelijk nog maximaal een uur beschikbaar in de cache. We zullen echter binnen 15 minuten na de verwijdering van het activum koppelingen naar het activum in CDN ongeldig maken.</span><span class="sxs-lookup"><span data-stu-id="e7358-211">If you remove an asset from the private origin, the asset may continue to be available for up to an hour from the cache; however, we will invalidate links to the asset in the CDN within 15 minutes of the asset's removal.</span></span>

+ <span data-ttu-id="e7358-212">De standaardbestandstypen die zijn opgenomen voor privé-origins zijn .gif, .ico, .jpeg, .jpg, .js en .png.</span><span class="sxs-lookup"><span data-stu-id="e7358-212">The default file types that are included for private origins are .gif, .ico, .jpeg, .jpg, .js, and .png.</span></span> <span data-ttu-id="e7358-213">U kunt extra bestandstypen opgeven.</span><span class="sxs-lookup"><span data-stu-id="e7358-213">You can specify additional file types.</span></span>

+ <span data-ttu-id="e7358-214">Net als bij openbare origins kunt u een beleid configureren om activa uit te sluiten die zijn geïdentificeerd met siteclassificaties die u opgeeft, zelfs als u jokertekens gebruikt om alle activa in een map of documentbibliotheek op te nemen.</span><span class="sxs-lookup"><span data-stu-id="e7358-214">Just like with public origins, you can configure a policy to exclude assets that have been identified by site classifications that you specify even if you use wildcards to include all assets within a folder or document library.</span></span>

<span data-ttu-id="e7358-215">Zie Content [Delivery Networks](content-delivery-networks.md)voor meer informatie over Office 365 CDN, algemene CDN concepten en andere Microsoft CDN's die u kunt gebruiken met uw Office 365 tenant.</span><span class="sxs-lookup"><span data-stu-id="e7358-215">For more information about why to use the Office 365 CDN, general CDN concepts, and other Microsoft CDNs you can use with your Office 365 tenant, see [Content Delivery Networks](content-delivery-networks.md).</span></span>

### <a name="default-cdn-origins"></a><span data-ttu-id="e7358-216">Standaard CDN origins</span><span class="sxs-lookup"><span data-stu-id="e7358-216">Default CDN origins</span></span>

<span data-ttu-id="e7358-217">Tenzij u anders opgeeft, Office 365 u een aantal standaard origins voor u in wanneer u de Office 365 CDN.</span><span class="sxs-lookup"><span data-stu-id="e7358-217">Unless you specify otherwise, Office 365 sets up some default origins for you when you enable the Office 365 CDN.</span></span> <span data-ttu-id="e7358-218">Als u er in eerste instantie voor kiest om deze niet in te stellen, kunt u deze origins toevoegen nadat u de installatie hebt voltooid.</span><span class="sxs-lookup"><span data-stu-id="e7358-218">If you initially opt not to provision them, you can add these origins after you complete setup.</span></span> <span data-ttu-id="e7358-219">Tenzij u de gevolgen begrijpt van het overslaan van de instelling van standaard origins en hiervoor een specifieke reden hebt, moet u toestaan dat deze worden gemaakt wanneer u de CDN.</span><span class="sxs-lookup"><span data-stu-id="e7358-219">Unless you understand the consequences of skipping the setup of default origins and have a specific reason for doing so, you should allow them to be created when you enable the CDN.</span></span>
  
<span data-ttu-id="e7358-220">Standaardinstellingen CDN privé-origins:</span><span class="sxs-lookup"><span data-stu-id="e7358-220">Default private CDN origins:</span></span>
  
+ <span data-ttu-id="e7358-221">\*/userphoto.aspx</span><span class="sxs-lookup"><span data-stu-id="e7358-221">\*/userphoto.aspx</span></span>
+ <span data-ttu-id="e7358-222">\*/siteassets</span><span class="sxs-lookup"><span data-stu-id="e7358-222">\*/siteassets</span></span>

<span data-ttu-id="e7358-223">Standaard openbare CDN origins:</span><span class="sxs-lookup"><span data-stu-id="e7358-223">Default public CDN origins:</span></span>
  
+ <span data-ttu-id="e7358-224">\*/masterpage</span><span class="sxs-lookup"><span data-stu-id="e7358-224">\*/masterpage</span></span>
+ <span data-ttu-id="e7358-225">\*/stijlbibliotheek</span><span class="sxs-lookup"><span data-stu-id="e7358-225">\*/style library</span></span>
+ <span data-ttu-id="e7358-226">\*/clientsideassets</span><span class="sxs-lookup"><span data-stu-id="e7358-226">\*/clientsideassets</span></span>

> [!NOTE]
> <span data-ttu-id="e7358-227">_clientsideassets_ is een standaard openbare origin die in december 2017 is toegevoegd aan de Office 365 CDN service.</span><span class="sxs-lookup"><span data-stu-id="e7358-227">_clientsideassets_ is a default public origin that was added to the Office 365 CDN service in December 2017.</span></span> <span data-ttu-id="e7358-228">Deze origin moet aanwezig zijn om te kunnen SharePoint Framework oplossingen in de CDN werken.</span><span class="sxs-lookup"><span data-stu-id="e7358-228">This origin must be present in order for SharePoint Framework solutions in the CDN to work.</span></span> <span data-ttu-id="e7358-229">Als u de Office 365 CDN hebt ingeschakeld vóór december 2017 of als u de installatie van standaard origins hebt overgeslagen toen u de CDN inschakelen, kunt u deze origin handmatig toevoegen.</span><span class="sxs-lookup"><span data-stu-id="e7358-229">If you enabled the Office 365 CDN prior to December 2017, or if you skipped setup of default origins when you enabled the CDN, you can manually add this origin.</span></span> <span data-ttu-id="e7358-230">Zie Mijn [webonderdeel aan de clientzijde of](use-microsoft-365-cdn-with-spo.md#my-client-side-web-part-or-sharepoint-framework-solution-isnt-working)SharePoint Framework oplossing werkt niet voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="e7358-230">For more information, see [My client-side web part or SharePoint Framework solution isn't working](use-microsoft-365-cdn-with-spo.md#my-client-side-web-part-or-sharepoint-framework-solution-isnt-working).</span></span>

<span data-ttu-id="e7358-231"><a name="CDNSetupinPShell"> </a></span><span class="sxs-lookup"><span data-stu-id="e7358-231"><a name="CDNSetupinPShell"> </a></span></span>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell"></a><span data-ttu-id="e7358-232">De Office 365 CDN instellen en configureren met de SharePoint Online Management Shell</span><span class="sxs-lookup"><span data-stu-id="e7358-232">Set up and configure the Office 365 CDN by using the SharePoint Online Management Shell</span></span>

<span data-ttu-id="e7358-233">Voor de procedures in deze sectie moet u de SharePoint Online Management Shell gebruiken om verbinding te maken met SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="e7358-233">The procedures in this section require you to use the SharePoint Online Management Shell to connect to SharePoint Online.</span></span> <span data-ttu-id="e7358-234">Zie voor instructies [Verbinding maken SharePoint Online PowerShell.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)</span><span class="sxs-lookup"><span data-stu-id="e7358-234">For instructions, see [Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

<span data-ttu-id="e7358-235">Voltooi deze stappen voor het instellen en configureren van de CDN om uw assets te hosten in SharePoint Online met behulp van SharePoint Online Management Shell.</span><span class="sxs-lookup"><span data-stu-id="e7358-235">Complete these steps to set up and configure the CDN to host your assets in SharePoint Online using the SharePoint Online Management Shell.</span></span>

<details>
  <summary><span data-ttu-id="e7358-236">Klik om uit te vouwen</span><span class="sxs-lookup"><span data-stu-id="e7358-236">Click to expand</span></span></summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a><span data-ttu-id="e7358-237">Uw organisatie in staat stellen de Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="e7358-237">Enable your organization to use the Office 365 CDN</span></span>

<span data-ttu-id="e7358-238">Voordat u wijzigingen aan de tenantinstellingen CDN, moet u de huidige status van de privé-CDN in uw Office 365 tenant.</span><span class="sxs-lookup"><span data-stu-id="e7358-238">Before you make changes to the tenant CDN settings, you should retrieve the current status of the private CDN configuration in your Office 365 tenant.</span></span> <span data-ttu-id="e7358-239">Verbinding maken naar uw tenant met behulp van SharePoint Online Management Shell:</span><span class="sxs-lookup"><span data-stu-id="e7358-239">Connect to your tenant using the SharePoint Online Management Shell:</span></span>

```powershell
Connect-SPOService -Url https://contoso-admin.sharepoint.com
```

<span data-ttu-id="e7358-240">Gebruik nu **de cmdlet Get-SPOTenantCdnEnabled** om de CDN statusinstellingen van de tenant op te halen:</span><span class="sxs-lookup"><span data-stu-id="e7358-240">Now use the **Get-SPOTenantCdnEnabled** cmdlet to retrieve the CDN status settings from the tenant:</span></span>

```powershell
Get-SPOTenantCdnEnabled -CdnType <Public | Private>
```

<span data-ttu-id="e7358-241">De status van de CDN voor het opgegeven CdnType wordt naar het scherm uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="e7358-241">The status of the CDN for the specified CdnType will output to the screen.</span></span>

<span data-ttu-id="e7358-242">Gebruik de **cmdlet Set-SPOTenantCdnEnabled** om uw organisatie in staat te stellen de Office 365 CDN.</span><span class="sxs-lookup"><span data-stu-id="e7358-242">Use the **Set-SPOTenantCdnEnabled** cmdlet to enable your organization to use the Office 365 CDN.</span></span> <span data-ttu-id="e7358-243">U kunt uw organisatie in staat stellen om openbare origins, privé-origins of beide tegelijk te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="e7358-243">You can enable your organization to use public origins, private origins, or both at once.</span></span> <span data-ttu-id="e7358-244">U kunt de CDN ook zo configureren dat de instelling van standaard origins wordt overgeslagen wanneer u deze inschakelen.</span><span class="sxs-lookup"><span data-stu-id="e7358-244">You can also configure the CDN to skip the setup of default origins when you enable it.</span></span> <span data-ttu-id="e7358-245">U kunt deze origins altijd later toevoegen, zoals in dit onderwerp wordt beschreven.</span><span class="sxs-lookup"><span data-stu-id="e7358-245">You can always add these origins later as described in this topic.</span></span>
  
<span data-ttu-id="e7358-246">In Windows PowerShell voor SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="e7358-246">In Windows PowerShell for SharePoint Online:</span></span>

```powershell
Set-SPOTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

<span data-ttu-id="e7358-247">Als u bijvoorbeeld wilt dat uw organisatie zowel openbare als privé-origins kan gebruiken, typt u de volgende opdracht:</span><span class="sxs-lookup"><span data-stu-id="e7358-247">For example, to enable your organization to use both public and private origins, type the following command:</span></span>

```powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

<span data-ttu-id="e7358-248">Als u wilt dat uw organisatie zowel openbare als persoonlijke origins kan gebruiken, maar het instellen van de standaard origins wilt overslaan, typt u de volgende opdracht:</span><span class="sxs-lookup"><span data-stu-id="e7358-248">To enable your organization to use both public and private origins but skip setting up the default origins, type the following command:</span></span>

```powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

<span data-ttu-id="e7358-249">Zie [Standaard CDN origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) voor informatie over de origins die standaard zijn ingericht wanneer u de Office 365 CDN inschakelen, en de mogelijke impact van het overslaan van de instelling van standaard origins.</span><span class="sxs-lookup"><span data-stu-id="e7358-249">See [Default CDN origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) for information about the origins that are provisioned by default when you enable the Office 365 CDN, and the potential impact of skipping the setup of default origins.</span></span>

<span data-ttu-id="e7358-250">Als u wilt dat uw organisatie openbare origins kan gebruiken, typt u de volgende opdracht:</span><span class="sxs-lookup"><span data-stu-id="e7358-250">To enable your organization to use public origins, type the following command:</span></span>

```powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $true
```

<span data-ttu-id="e7358-251">Als u wilt dat uw organisatie persoonlijke origins kan gebruiken, typt u de volgende opdracht:</span><span class="sxs-lookup"><span data-stu-id="e7358-251">To enable your organization to use private origins, type the following command:</span></span>

```powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $true
```

<span data-ttu-id="e7358-252">Zie [Set-SPOTenantCdnEnabled voor](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled)meer informatie over deze cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e7358-252">For more information about this cmdlet, see [Set-SPOTenantCdnEnabled](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled).</span></span>

<span data-ttu-id="e7358-253"><a name="Office365CDNforSPOFileType"> </a></span><span class="sxs-lookup"><span data-stu-id="e7358-253"><a name="Office365CDNforSPOFileType"> </a></span></span>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a><span data-ttu-id="e7358-254">De lijst met bestandstypen wijzigen die u wilt opnemen in de Office 365 CDN (Optioneel)</span><span class="sxs-lookup"><span data-stu-id="e7358-254">Change the list of file types to include in the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="e7358-255">Wanneer u bestandstypen definieert met de **cmdlet Set-SPOTenantCdnPolicy,** overschrijft u de lijst die momenteel is gedefinieerd.</span><span class="sxs-lookup"><span data-stu-id="e7358-255">When you define file types by using the **Set-SPOTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="e7358-256">Als u extra bestandstypen aan de lijst wilt toevoegen, gebruikt u de cmdlet eerst om te kijken welke bestandstypen al zijn toegestaan en deze samen met de nieuwe bestandstypen in de lijst op te nemen.</span><span class="sxs-lookup"><span data-stu-id="e7358-256">If you want to add additional file types to the list, use the cmdlet first to find out what file types are already allowed and include them in the list along with your new ones.</span></span>
  
<span data-ttu-id="e7358-257">Gebruik de **cmdlet Set-SPOTenantCdnPolicy** om statische bestandstypen te definiëren die kunnen worden gehost door openbare en private origins in de CDN.</span><span class="sxs-lookup"><span data-stu-id="e7358-257">Use the **Set-SPOTenantCdnPolicy** cmdlet to define static file types that can be hosted by public and private origins in the CDN.</span></span> <span data-ttu-id="e7358-258">Standaard zijn veelgebruikte activatypen toegestaan, zoals .css, .gif, .jpg en .js.</span><span class="sxs-lookup"><span data-stu-id="e7358-258">By default, common asset types are allowed, for example .css, .gif, .jpg, and .js.</span></span>

<span data-ttu-id="e7358-259">In Windows PowerShell voor SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="e7358-259">In Windows PowerShell for SharePoint Online:</span></span>

```powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

<span data-ttu-id="e7358-260">Als u bijvoorbeeld de CDN css en .png wilt hosten, voert u de opdracht in:</span><span class="sxs-lookup"><span data-stu-id="e7358-260">For example, to enable the CDN to host .css and .png files, you would enter the command:</span></span>

```powershell
Set-SPOTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

<span data-ttu-id="e7358-261">Gebruik de **cmdlet Get-SPOTenantCdnPolicies** om te zien welke bestandstypen momenteel door de CDN zijn toegestaan:</span><span class="sxs-lookup"><span data-stu-id="e7358-261">To see what file types are currently allowed by the CDN, use the **Get-SPOTenantCdnPolicies** cmdlet:</span></span>

```powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="e7358-262">Zie Set-SPOTenantCdnPolicy and Get-SPOTenantCdnPolicies [(Set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/) en [Get-SPOTenantCdnPolicies)](/powershell/module/sharepoint-online/)voor meer informatie over deze cmdlets.</span><span class="sxs-lookup"><span data-stu-id="e7358-262">For more information about these cmdlets, see [Set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/) and [Get-SPOTenantCdnPolicies](/powershell/module/sharepoint-online/).</span></span>

<span data-ttu-id="e7358-263"><a name="Office365CDNforSPOSiteClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="e7358-263"><a name="Office365CDNforSPOSiteClassification"> </a></span></span>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a><span data-ttu-id="e7358-264">De lijst met siteclassificaties wijzigen die u wilt uitsluiten van de Office 365 CDN (Optioneel)</span><span class="sxs-lookup"><span data-stu-id="e7358-264">Change the list of site classifications you want to exclude from the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="e7358-265">Wanneer u siteclassificaties uitsluit met de **cmdlet Set-SPOTenantCdnPolicy,** overschrijft u de lijst die momenteel is gedefinieerd.</span><span class="sxs-lookup"><span data-stu-id="e7358-265">When you exclude site classifications by using the **Set-SPOTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="e7358-266">Als u extra siteclassificaties wilt uitsluiten, gebruikt u de cmdlet eerst om te kijken welke classificaties al zijn uitgesloten en voegt u deze vervolgens samen met de nieuwe toe.</span><span class="sxs-lookup"><span data-stu-id="e7358-266">If you want to exclude additional site classifications, use the cmdlet first to find out what classifications are already excluded and then add them along with your new ones.</span></span>

<span data-ttu-id="e7358-267">Gebruik de **cmdlet Set-SPOTenantCdnPolicy** om siteclassificaties uit te sluiten die u niet beschikbaar wilt maken in de CDN.</span><span class="sxs-lookup"><span data-stu-id="e7358-267">Use the **Set-SPOTenantCdnPolicy** cmdlet to exclude site classifications that you do not want to make available over the CDN.</span></span> <span data-ttu-id="e7358-268">Standaard worden geen siteclassificaties uitgesloten.</span><span class="sxs-lookup"><span data-stu-id="e7358-268">By default, no site classifications are excluded.</span></span>

<span data-ttu-id="e7358-269">In Windows PowerShell voor SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="e7358-269">In Windows PowerShell for SharePoint Online:</span></span>

```powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications >"
```

<span data-ttu-id="e7358-270">Als u wilt zien welke siteclassificaties momenteel zijn beperkt, gebruikt u de **cmdlet Get-SPOTenantCdnPolicies:**</span><span class="sxs-lookup"><span data-stu-id="e7358-270">To see what site classifications are currently restricted, use the **Get-SPOTenantCdnPolicies** cmdlet:</span></span>

```powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="e7358-271">De eigenschappen die worden geretourneerd, zijn _IncludeFileExtensions,_ _ExcludeRestrictedSiteClassifications_ en _ExcludeIfNoScriptDisabled_.</span><span class="sxs-lookup"><span data-stu-id="e7358-271">The properties that will be returned are _IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ and _ExcludeIfNoScriptDisabled_.</span></span>

<span data-ttu-id="e7358-272">De _eigenschap IncludeFileExtensions_ bevat de lijst met bestandsextensies die vanaf de CDN.</span><span class="sxs-lookup"><span data-stu-id="e7358-272">The _IncludeFileExtensions_ property contains the list of file extensions that will be served from the CDN.</span></span>

> [!NOTE]
> <span data-ttu-id="e7358-273">De standaardbestandsextensies verschillen tussen openbaar en privé.</span><span class="sxs-lookup"><span data-stu-id="e7358-273">The default file extensions are different between public and private.</span></span>

<span data-ttu-id="e7358-274">De _eigenschap ExcludeRestrictedSiteClassifications_ bevat de siteclassificaties die u wilt uitsluiten van de CDN.</span><span class="sxs-lookup"><span data-stu-id="e7358-274">The _ExcludeRestrictedSiteClassifications_ property contains the site classifications that you want to exclude from the CDN.</span></span> <span data-ttu-id="e7358-275">U kunt bijvoorbeeld sites uitsluiten die zijn gemarkeerd als **Vertrouwelijk,** zodat inhoud van sites met die classificatie die is toegepast, niet wordt gebruikt vanaf de CDN.</span><span class="sxs-lookup"><span data-stu-id="e7358-275">For example, you can exclude sites marked as **Confidential** so content from sites with that classification applied will not be served from the CDN.</span></span>

<span data-ttu-id="e7358-276">De _eigenschap ExcludeIfNoScriptDisabled_ sluit inhoud uit van de CDN op basis van de _noScript-kenmerkinstellingen_ op siteniveau.</span><span class="sxs-lookup"><span data-stu-id="e7358-276">The _ExcludeIfNoScriptDisabled_ property excludes content from the CDN based on the site-level _NoScript_ attribute settings.</span></span> <span data-ttu-id="e7358-277">Het kenmerk _NoScript_ is standaard ingesteld op **Ingeschakeld voor** _moderne_ sites en **Uitgeschakeld** voor _klassieke_ sites.</span><span class="sxs-lookup"><span data-stu-id="e7358-277">By default, the _NoScript_ attribute is set to **Enabled** for _Modern_ sites and **Disabled** for _Classic_ sites.</span></span> <span data-ttu-id="e7358-278">Dit is afhankelijk van uw tenantinstellingen.</span><span class="sxs-lookup"><span data-stu-id="e7358-278">This depends on your tenant settings.</span></span>

<span data-ttu-id="e7358-279">Zie Set-SPOTenantCdnPolicy and Get-SPOTenantCdnPolicies [(Set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/) en [Get-SPOTenantCdnPolicies)](/powershell/module/sharepoint-online/)voor meer informatie over deze cmdlets.</span><span class="sxs-lookup"><span data-stu-id="e7358-279">For more information about these cmdlets, see [Set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/) and [Get-SPOTenantCdnPolicies](/powershell/module/sharepoint-online/).</span></span>

<span data-ttu-id="e7358-280"><a name="Office365CDNforSPOOriginPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="e7358-280"><a name="Office365CDNforSPOOriginPosh"> </a></span></span>
### <a name="add-an-origin-for-your-assets"></a><span data-ttu-id="e7358-281">Een origin toevoegen voor uw activa</span><span class="sxs-lookup"><span data-stu-id="e7358-281">Add an origin for your assets</span></span>

<span data-ttu-id="e7358-282">Gebruik de **cmdlet Add-SPOTenantCdnOrigin** om een origin te definiëren.</span><span class="sxs-lookup"><span data-stu-id="e7358-282">Use the **Add-SPOTenantCdnOrigin** cmdlet to define an origin.</span></span> <span data-ttu-id="e7358-283">U kunt meerdere origins definiëren.</span><span class="sxs-lookup"><span data-stu-id="e7358-283">You can define multiple origins.</span></span> <span data-ttu-id="e7358-284">De origin is een URL die wijst naar een SharePoint of map die de assets bevat die u wilt hosten door de CDN.</span><span class="sxs-lookup"><span data-stu-id="e7358-284">The origin is a URL that points to a SharePoint library or folder that contains the assets that you want to be hosted by the CDN.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e7358-285">U mag nooit resources plaatsen die gebruikersgegevens bevatten of die als gevoelig voor uw organisatie worden beschouwd in een openbare origin.</span><span class="sxs-lookup"><span data-stu-id="e7358-285">You should never place resources that contain user information or are considered sensitive to your organization in a public origin.</span></span>

```powershell
Add-SPOTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

<span data-ttu-id="e7358-286">De waarde van _pad_ is het relatieve pad naar de bibliotheek of map die de assets bevat.</span><span class="sxs-lookup"><span data-stu-id="e7358-286">The value of _path_ is the relative path to the library or folder that contains the assets.</span></span> <span data-ttu-id="e7358-287">U kunt jokertekens gebruiken naast relatieve paden.</span><span class="sxs-lookup"><span data-stu-id="e7358-287">You can use wildcards in addition to relative paths.</span></span> <span data-ttu-id="e7358-288">Origins ondersteunt jokertekens die zijn voorbereid op de URL.</span><span class="sxs-lookup"><span data-stu-id="e7358-288">Origins support wildcards prepended to the URL.</span></span> <span data-ttu-id="e7358-289">Op deze manier kunt u origins maken die meerdere sites bespannen.</span><span class="sxs-lookup"><span data-stu-id="e7358-289">This allows you to create origins that span multiple sites.</span></span> <span data-ttu-id="e7358-290">Als u bijvoorbeeld alle assets wilt opnemen in de map met basispagina's voor al uw sites als openbare origin in de CDN, typt u de volgende opdracht:</span><span class="sxs-lookup"><span data-stu-id="e7358-290">For example, to include all of the assets in the masterpages folder for all of your sites as a public origin within the CDN, type the following command:</span></span>

```powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ <span data-ttu-id="e7358-291">De jokertekenmodule \* kan alleen worden gebruikt aan het begin van het pad en komt overeen met alle URL-segmenten **/** onder de opgegeven URL.</span><span class="sxs-lookup"><span data-stu-id="e7358-291">The wildcard modifier \***/** can only be used at the beginning of the path, and will match all URL segments under the specified URL.</span></span>
+ <span data-ttu-id="e7358-292">Het pad kan naar een documentbibliotheek, map of site wijzen.</span><span class="sxs-lookup"><span data-stu-id="e7358-292">The path can point to a document library, folder or site.</span></span> <span data-ttu-id="e7358-293">Het pad _\*/site1_ komt bijvoorbeeld overeen met alle documentbibliotheken onder de site.</span><span class="sxs-lookup"><span data-stu-id="e7358-293">For example, the path _\*/site1_ will match all the document libraries under the site.</span></span>

<span data-ttu-id="e7358-294">U kunt een origin toevoegen met een specifiek relatieve pad.</span><span class="sxs-lookup"><span data-stu-id="e7358-294">You can add an origin with a specific relative path.</span></span> <span data-ttu-id="e7358-295">U kunt geen origin toevoegen met het volledige pad.</span><span class="sxs-lookup"><span data-stu-id="e7358-295">You cannot add an origin using the full path.</span></span>

<span data-ttu-id="e7358-296">In dit voorbeeld wordt een persoonlijke origin van de siteassetsbibliotheek op een specifieke site toegevoegd:</span><span class="sxs-lookup"><span data-stu-id="e7358-296">This example adds a private origin of the siteassets library on a specific site:</span></span>

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="e7358-297">In dit voorbeeld wordt een persoonlijke origin van de _map1_ toegevoegd aan de siteactivabibliotheek van de siteverzameling:</span><span class="sxs-lookup"><span data-stu-id="e7358-297">This example adds a private origin of the _folder1_ folder in the site collection's site assets library:</span></span>

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

<span data-ttu-id="e7358-298">Als er een spatie in het pad is, kunt u het pad omringen met dubbele aanhalingstekens of de spatie vervangen door de URL-codering %20.</span><span class="sxs-lookup"><span data-stu-id="e7358-298">If there is a space in the path, you can either surround the path in double quotes or replace the space with the URL encoding %20.</span></span> <span data-ttu-id="e7358-299">In de volgende voorbeelden wordt een persoonlijke origin van de _map 1_ in de siteactivabibliotheek van de siteverzameling toegevoegd:</span><span class="sxs-lookup"><span data-stu-id="e7358-299">The following examples add a private origin of the _folder 1_ folder in the site collection's site assets library:</span></span>

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

<span data-ttu-id="e7358-300">Zie [Add-SPOTenantCdnOrigin (Add-SPOTenantCdnOrigin)](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin)voor meer informatie over deze opdracht en de syntaxis ervan.</span><span class="sxs-lookup"><span data-stu-id="e7358-300">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span></span>

> [!NOTE]
> <span data-ttu-id="e7358-301">In privé-origins moeten activa die vanaf een origin worden gedeeld, een hoofdversie hebben gepubliceerd voordat ze vanaf de CDN.</span><span class="sxs-lookup"><span data-stu-id="e7358-301">In private origins, assets being shared from an origin must have a major version published before they can be accessed from the CDN.</span></span>
  
<span data-ttu-id="e7358-302">Wanneer u de opdracht hebt uitgevoerd, synchroniseert het systeem de configuratie in het datacenter.</span><span class="sxs-lookup"><span data-stu-id="e7358-302">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="e7358-303">Dit kan maximaal 15 minuten duren.</span><span class="sxs-lookup"><span data-stu-id="e7358-303">This can take up to 15 minutes.</span></span>

<span data-ttu-id="e7358-304"><a name="ExamplePublicOrigin"> </a></span><span class="sxs-lookup"><span data-stu-id="e7358-304"><a name="ExamplePublicOrigin"> </a></span></span>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a><span data-ttu-id="e7358-305">Voorbeeld: Een openbare origin configureren voor uw basispagina's en voor uw stijlbibliotheek voor SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="e7358-305">Example: Configure a public origin for your master pages and for your style library for SharePoint Online</span></span>

<span data-ttu-id="e7358-306">Normaal gesproken worden deze origins standaard voor u ingesteld wanneer u de Office 365 CDN.</span><span class="sxs-lookup"><span data-stu-id="e7358-306">Normally, these origins are set up for you by default when you enable the Office 365 CDN.</span></span> <span data-ttu-id="e7358-307">Als u ze echter handmatig wilt inschakelen, volgt u deze stappen.</span><span class="sxs-lookup"><span data-stu-id="e7358-307">However, if you want to enable them manually, follow these steps.</span></span>
  
+ <span data-ttu-id="e7358-308">Gebruik de **cmdlet Add-SPOTenantCdnOrigin** om de stijlbibliotheek te definiëren als een openbare origin.</span><span class="sxs-lookup"><span data-stu-id="e7358-308">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the style library as a public origin.</span></span>

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ <span data-ttu-id="e7358-309">Gebruik de **cmdlet Add-SPOTenantCdnOrigin** om de basispagina's te definiëren als een openbare origin.</span><span class="sxs-lookup"><span data-stu-id="e7358-309">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the master pages as a public origin.</span></span>

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

<span data-ttu-id="e7358-310">Zie [Add-SPOTenantCdnOrigin (Add-SPOTenantCdnOrigin)](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin)voor meer informatie over deze opdracht en de syntaxis ervan.</span><span class="sxs-lookup"><span data-stu-id="e7358-310">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span></span>

<span data-ttu-id="e7358-311">Wanneer u de opdracht hebt uitgevoerd, synchroniseert het systeem de configuratie in het datacenter.</span><span class="sxs-lookup"><span data-stu-id="e7358-311">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="e7358-312">Dit kan maximaal 15 minuten duren.</span><span class="sxs-lookup"><span data-stu-id="e7358-312">This can take up to 15 minutes.</span></span>

<span data-ttu-id="e7358-313"><a name="ExamplePrivateOrigin"> </a></span><span class="sxs-lookup"><span data-stu-id="e7358-313"><a name="ExamplePrivateOrigin"> </a></span></span>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a><span data-ttu-id="e7358-314">Voorbeeld: Een persoonlijke origin configureren voor uw siteactiva, sitepagina's en publicerende afbeeldingen voor SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="e7358-314">Example: Configure a private origin for your site assets, site pages, and publishing images for SharePoint Online</span></span>

+ <span data-ttu-id="e7358-315">Gebruik de **cmdlet Add-SPOTenantCdnOrigin** om de map met siteactiva te definiëren als een persoonlijke origin.</span><span class="sxs-lookup"><span data-stu-id="e7358-315">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the site assets folder as a private origin.</span></span>

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ <span data-ttu-id="e7358-316">Gebruik de **cmdlet Add-SPOTenantCdnOrigin** om de map sitepagina's te definiëren als een persoonlijke origin.</span><span class="sxs-lookup"><span data-stu-id="e7358-316">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the site pages folder as a private origin.</span></span>

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ <span data-ttu-id="e7358-317">Gebruik de **cmdlet Add-SPOTenantCdnOrigin** om de map met publicatieafbeeldingen te definiëren als een persoonlijke origin.</span><span class="sxs-lookup"><span data-stu-id="e7358-317">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the publishing images folder as a private origin.</span></span>

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

<span data-ttu-id="e7358-318">Zie [Add-SPOTenantCdnOrigin (Add-SPOTenantCdnOrigin)](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin)voor meer informatie over deze opdracht en de syntaxis ervan.</span><span class="sxs-lookup"><span data-stu-id="e7358-318">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span></span>

<span data-ttu-id="e7358-319">Wanneer u de opdracht hebt uitgevoerd, synchroniseert het systeem de configuratie in het datacenter.</span><span class="sxs-lookup"><span data-stu-id="e7358-319">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="e7358-320">Dit kan maximaal 15 minuten duren.</span><span class="sxs-lookup"><span data-stu-id="e7358-320">This can take up to 15 minutes.</span></span>

<span data-ttu-id="e7358-321"><a name="ExamplePrivateOriginSiteCollection"> </a></span><span class="sxs-lookup"><span data-stu-id="e7358-321"><a name="ExamplePrivateOriginSiteCollection"> </a></span></span>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a><span data-ttu-id="e7358-322">Voorbeeld: Een persoonlijke origin configureren voor een siteverzameling voor SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="e7358-322">Example: Configure a private origin for a site collection for SharePoint Online</span></span>

<span data-ttu-id="e7358-323">Gebruik de **cmdlet Add-SPOTenantCdnOrigin** om een siteverzameling te definiëren als een persoonlijke origin.</span><span class="sxs-lookup"><span data-stu-id="e7358-323">Use the **Add-SPOTenantCdnOrigin** cmdlet to define a site collection as a private origin.</span></span> <span data-ttu-id="e7358-324">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="e7358-324">For example:</span></span>

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="e7358-325">Zie [Add-SPOTenantCdnOrigin (Add-SPOTenantCdnOrigin)](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin)voor meer informatie over deze opdracht en de syntaxis ervan.</span><span class="sxs-lookup"><span data-stu-id="e7358-325">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span></span>
  
<span data-ttu-id="e7358-326">Wanneer u de opdracht hebt uitgevoerd, synchroniseert het systeem de configuratie in het datacenter.</span><span class="sxs-lookup"><span data-stu-id="e7358-326">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="e7358-327">Mogelijk ziet u een _bericht in_ behandeling met configuratie dat wordt verwacht wanneer de SharePoint Online-tenant verbinding maakt met de CDN service.</span><span class="sxs-lookup"><span data-stu-id="e7358-327">You may see a _Configuration pending_ message which is expected as the SharePoint Online tenant connects to the CDN service.</span></span> <span data-ttu-id="e7358-328">Dit kan maximaal 15 minuten duren.</span><span class="sxs-lookup"><span data-stu-id="e7358-328">This can take up to 15 minutes.</span></span>

<span data-ttu-id="e7358-329"><a name="CDNManage"> </a></span><span class="sxs-lookup"><span data-stu-id="e7358-329"><a name="CDNManage"> </a></span></span>
### <a name="manage-the-office-365-cdn"></a><span data-ttu-id="e7358-330">De Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="e7358-330">Manage the Office 365 CDN</span></span>

<span data-ttu-id="e7358-331">Nadat u de CDN hebt ingesteld, kunt u wijzigingen aanbrengen in uw configuratie terwijl u inhoud bij werk of als uw behoeften veranderen, zoals in deze sectie wordt beschreven.</span><span class="sxs-lookup"><span data-stu-id="e7358-331">Once you've set up the CDN, you can make changes to your configuration as you update content or as your needs change, as described in this section.</span></span>
  
<span data-ttu-id="e7358-332"><a name="Office365CDNforSPOaddremoveasset"> </a></span><span class="sxs-lookup"><span data-stu-id="e7358-332"><a name="Office365CDNforSPOaddremoveasset"> </a></span></span>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a><span data-ttu-id="e7358-333">Activa toevoegen, bijwerken of verwijderen uit de Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="e7358-333">Add, update, or remove assets from the Office 365 CDN</span></span>

<span data-ttu-id="e7358-334">Nadat u de installatiestappen hebt voltooid, kunt u nieuwe activa toevoegen en bestaande assets bijwerken of verwijderen wanneer u maar wilt.</span><span class="sxs-lookup"><span data-stu-id="e7358-334">Once you've completed the setup steps, you can add new assets, and update or remove existing assets whenever you want.</span></span> <span data-ttu-id="e7358-335">Pas uw wijzigingen aan in de assets in de map of SharePoint bibliotheek die u hebt geïdentificeerd als een origin.</span><span class="sxs-lookup"><span data-stu-id="e7358-335">Just make your changes to the assets in the folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="e7358-336">Als u een nieuw activum toevoegt, is deze direct beschikbaar via CDN.</span><span class="sxs-lookup"><span data-stu-id="e7358-336">If you add a new asset, it is available through the CDN immediately.</span></span> <span data-ttu-id="e7358-337">Als u het activum echter bij werkt, duurt het maximaal 15 minuten voordat de nieuwe kopie wordt doorgegeven en beschikbaar komt in de CDN.</span><span class="sxs-lookup"><span data-stu-id="e7358-337">However, if you update the asset, it will take up to 15 minutes for the new copy to propagate and become available in the CDN.</span></span>
  
<span data-ttu-id="e7358-338">Als u de locatie van de origin wilt ophalen, kunt u de **cmdlet Get-SPOTenantCdnOrigins** gebruiken.</span><span class="sxs-lookup"><span data-stu-id="e7358-338">If you need to retrieve the location of the origin, you can use the **Get-SPOTenantCdnOrigins** cmdlet.</span></span> <span data-ttu-id="e7358-339">Zie [Get-SPOTenantCdnOrigins](/powershell/module/sharepoint-online/Get-SPOTenantCdnOrigins)voor meer informatie over het gebruik van deze cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e7358-339">For information on how to use this cmdlet, see [Get-SPOTenantCdnOrigins](/powershell/module/sharepoint-online/Get-SPOTenantCdnOrigins).</span></span>

<span data-ttu-id="e7358-340"><a name="Office365CDNforSPORemoveOriginPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="e7358-340"><a name="Office365CDNforSPORemoveOriginPosh"> </a></span></span>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a><span data-ttu-id="e7358-341">Een origin verwijderen uit de Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="e7358-341">Remove an origin from the Office 365 CDN</span></span>

<span data-ttu-id="e7358-342">U kunt de toegang tot een map of bibliotheek SharePoint verwijderen die u hebt geïdentificeerd als een origin.</span><span class="sxs-lookup"><span data-stu-id="e7358-342">You can remove access to a folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="e7358-343">Gebruik hiervoor de **cmdlet Remove-SPOTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="e7358-343">To do this, use the **Remove-SPOTenantCdnOrigin** cmdlet.</span></span>

```powershell
Remove-SPOTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

<span data-ttu-id="e7358-344">Zie [Remove-SPOTenantCdnOrigin (Verwijderen-SPOTenantCdnOrigin)](/powershell/module/sharepoint-online/Remove-SPOTenantCdnOrigin)voor meer informatie over het gebruik van deze cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e7358-344">For information on how to use this cmdlet, see [Remove-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Remove-SPOTenantCdnOrigin).</span></span>

<span data-ttu-id="e7358-345"><a name="Office365CDNforSPOModifyOrigin"> </a></span><span class="sxs-lookup"><span data-stu-id="e7358-345"><a name="Office365CDNforSPOModifyOrigin"> </a></span></span>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a><span data-ttu-id="e7358-346">Een origin in de Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="e7358-346">Modify an origin in the Office 365 CDN</span></span>

<span data-ttu-id="e7358-347">U kunt een origin die u hebt gemaakt niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="e7358-347">You cannot modify an origin you've created.</span></span> <span data-ttu-id="e7358-348">In plaats daarvan verwijdert u de origin en voegt u een nieuwe toe.</span><span class="sxs-lookup"><span data-stu-id="e7358-348">Instead, remove the origin and then add a new one.</span></span> <span data-ttu-id="e7358-349">Zie Een origin verwijderen [uit de](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPosh) Office 365 CDN en Een origin toevoegen voor uw assets voor [meer informatie.](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPosh)</span><span class="sxs-lookup"><span data-stu-id="e7358-349">For more information, see [To remove an origin from the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPosh) and [To add an origin for your assets](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPosh).</span></span>

<span data-ttu-id="e7358-350"><a name="Office365CDNforSPODisable"> </a></span><span class="sxs-lookup"><span data-stu-id="e7358-350"><a name="Office365CDNforSPODisable"> </a></span></span>
#### <a name="disable-the-office-365-cdn"></a><span data-ttu-id="e7358-351">De Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="e7358-351">Disable the Office 365 CDN</span></span>

<span data-ttu-id="e7358-352">Gebruik de **cmdlet Set-SPOTenantCdnEnabled** om de CDN voor uw organisatie uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="e7358-352">Use the **Set-SPOTenantCdnEnabled** cmdlet to disable the CDN for your organization.</span></span> <span data-ttu-id="e7358-353">Als u zowel de openbare als de privé-origins hebt ingeschakeld voor de CDN, moet u de cmdlet tweemaal uitvoeren, zoals wordt weergegeven in de volgende voorbeelden.</span><span class="sxs-lookup"><span data-stu-id="e7358-353">If you have both the public and private origins enabled for the CDN, you need to run the cmdlet twice as shown in the following examples.</span></span>
  
<span data-ttu-id="e7358-354">Als u het gebruik van openbare origins in de CDN wilt uitschakelen, voert u de volgende opdracht in:</span><span class="sxs-lookup"><span data-stu-id="e7358-354">To disable use of public origins in the CDN, enter the following command:</span></span>

```powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $false
```

<span data-ttu-id="e7358-355">Als u het gebruik van de privé-origins in de CDN wilt uitschakelen, voert u de volgende opdracht in:</span><span class="sxs-lookup"><span data-stu-id="e7358-355">To disable use of the private origins in the CDN, enter the following command:</span></span>

```powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $false
```

<span data-ttu-id="e7358-356">Zie [Set-SPOTenantCdnEnabled voor](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled)meer informatie over deze cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e7358-356">For more information about this cmdlet, see [Set-SPOTenantCdnEnabled](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled).</span></span>

</details>

<span data-ttu-id="e7358-357"><a name="CDNSetupinPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="e7358-357"><a name="CDNSetupinPnPPosh"> </a></span></span>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-pnp-powershell"></a><span data-ttu-id="e7358-358">De Office 365 CDN instellen en configureren met PnP PowerShell</span><span class="sxs-lookup"><span data-stu-id="e7358-358">Set up and configure the Office 365 CDN by using PnP PowerShell</span></span>

<span data-ttu-id="e7358-359">Voor de procedures in deze sectie moet u PnP PowerShell gebruiken om verbinding te maken met SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="e7358-359">The procedures in this section require you to use PnP PowerShell to connect to SharePoint Online.</span></span> <span data-ttu-id="e7358-360">Zie Aan de slag [met PnP PowerShell](https://github.com/SharePoint/PnP-PowerShell#getting-started)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="e7358-360">For instructions, see [Getting started with PnP PowerShell](https://github.com/SharePoint/PnP-PowerShell#getting-started).</span></span>

<span data-ttu-id="e7358-361">Voltooi deze stappen voor het instellen en configureren van de CDN om uw assets te hosten in SharePoint Online met PnP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e7358-361">Complete these steps to set up and configure the CDN to host your assets in SharePoint Online using PnP PowerShell.</span></span>

<details>
  <summary><span data-ttu-id="e7358-362">Klik om uit te vouwen</span><span class="sxs-lookup"><span data-stu-id="e7358-362">Click to expand</span></span></summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a><span data-ttu-id="e7358-363">Uw organisatie in staat stellen de Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="e7358-363">Enable your organization to use the Office 365 CDN</span></span>

<span data-ttu-id="e7358-364">Voordat u wijzigingen aan de tenantinstellingen CDN, moet u de huidige status van de privé-CDN in uw Office 365 tenant.</span><span class="sxs-lookup"><span data-stu-id="e7358-364">Before you make changes to the tenant CDN settings, you should retrieve the current status of the private CDN configuration in your Office 365 tenant.</span></span> <span data-ttu-id="e7358-365">Verbinding maken met PnP PowerShell naar uw tenant:</span><span class="sxs-lookup"><span data-stu-id="e7358-365">Connect to your tenant using PnP PowerShell:</span></span>

```powershell
Connect-PnPOnline -Url https://contoso-admin.sharepoint.com -UseWebLogin
```

<span data-ttu-id="e7358-366">Gebruik nu **de cmdlet Get-PnPTenantCdnEnabled om** de statusinstellingen CDN de tenant op te halen:</span><span class="sxs-lookup"><span data-stu-id="e7358-366">Now use the **Get-PnPTenantCdnEnabled** cmdlet to retrieve the CDN status settings from the tenant:</span></span>

```powershell
Get-PnPTenantCdnEnabled -CdnType <Public | Private>
```

<span data-ttu-id="e7358-367">De status van de CDN voor het opgegeven CdnType wordt naar het scherm uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="e7358-367">The status of the CDN for the specified CdnType will output to the screen.</span></span>

<span data-ttu-id="e7358-368">Gebruik de **cmdlet Set-PnPTenantCdnEnabled om** uw organisatie in staat te stellen de Office 365 CDN.</span><span class="sxs-lookup"><span data-stu-id="e7358-368">Use the **Set-PnPTenantCdnEnabled** cmdlet to enable your organization to use the Office 365 CDN.</span></span> <span data-ttu-id="e7358-369">U kunt uw organisatie inschakelen om tegelijk gebruik te maken van openbare origins, privé-origins of beide.</span><span class="sxs-lookup"><span data-stu-id="e7358-369">You can enable your organization to use public origins, private origins, or both at at the same time.</span></span> <span data-ttu-id="e7358-370">U kunt de CDN ook zo configureren dat de instelling van standaard origins wordt overgeslagen wanneer u deze inschakelen.</span><span class="sxs-lookup"><span data-stu-id="e7358-370">You can also configure the CDN to skip the setup of default origins when you enable it.</span></span> <span data-ttu-id="e7358-371">U kunt deze origins altijd later toevoegen, zoals in dit onderwerp wordt beschreven.</span><span class="sxs-lookup"><span data-stu-id="e7358-371">You can always add these origins later as described in this topic.</span></span>
  
<span data-ttu-id="e7358-372">In PnP PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e7358-372">In PnP PowerShell:</span></span>

```powershell
Set-PnPTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

<span data-ttu-id="e7358-373">Als u bijvoorbeeld wilt dat uw organisatie zowel openbare als privé-origins kan gebruiken, typt u de volgende opdracht:</span><span class="sxs-lookup"><span data-stu-id="e7358-373">For example, to enable your organization to use both public and private origins, type the following command:</span></span>

```powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true
```

<span data-ttu-id="e7358-374">Als u wilt dat uw organisatie zowel openbare als persoonlijke origins kan gebruiken, maar het instellen van de standaard origins wilt overslaan, typt u de volgende opdracht:</span><span class="sxs-lookup"><span data-stu-id="e7358-374">To enable your organization to use both public and private origins but skip setting up the default origins, type the following command:</span></span>

```powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

<span data-ttu-id="e7358-375">Zie [Standaard CDN origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) voor informatie over de origins die standaard zijn ingericht wanneer u de Office 365 CDN inschakelen, en de mogelijke impact van het overslaan van de instelling van standaard origins.</span><span class="sxs-lookup"><span data-stu-id="e7358-375">See [Default CDN origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) for information about the origins that are provisioned by default when you enable the Office 365 CDN, and the potential impact of skipping the setup of default origins.</span></span>

<span data-ttu-id="e7358-376">Als u wilt dat uw organisatie openbare origins kan gebruiken, typt u de volgende opdracht:</span><span class="sxs-lookup"><span data-stu-id="e7358-376">To enable your organization to use public origins, type the following command:</span></span>

```powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $true
```

<span data-ttu-id="e7358-377">Als u wilt dat uw organisatie persoonlijke origins kan gebruiken, typt u de volgende opdracht:</span><span class="sxs-lookup"><span data-stu-id="e7358-377">To enable your organization to use private origins, type the following command:</span></span>

```powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $true
```

<span data-ttu-id="e7358-378">Zie [Set-PnPTenantCdnEnabled voor meer informatie over deze cmdlet.](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled)</span><span class="sxs-lookup"><span data-stu-id="e7358-378">For more information about this cmdlet, see [Set-PnPTenantCdnEnabled](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled).</span></span>

<span data-ttu-id="e7358-379"><a name="Office365CDNforPnPPoshFileType"> </a></span><span class="sxs-lookup"><span data-stu-id="e7358-379"><a name="Office365CDNforPnPPoshFileType"> </a></span></span>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a><span data-ttu-id="e7358-380">De lijst met bestandstypen wijzigen die u wilt opnemen in de Office 365 CDN (Optioneel)</span><span class="sxs-lookup"><span data-stu-id="e7358-380">Change the list of file types to include in the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="e7358-381">Wanneer u bestandstypen definieert met de **cmdlet Set-PnPTenantCdnPolicy,** overschrijft u de momenteel gedefinieerde lijst.</span><span class="sxs-lookup"><span data-stu-id="e7358-381">When you define file types by using the **Set-PnPTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="e7358-382">Als u extra bestandstypen aan de lijst wilt toevoegen, gebruikt u de cmdlet eerst om te kijken welke bestandstypen al zijn toegestaan en deze samen met de nieuwe bestandstypen in de lijst op te nemen.</span><span class="sxs-lookup"><span data-stu-id="e7358-382">If you want to add additional file types to the list, use the cmdlet first to find out what file types are already allowed and include them in the list along with your new ones.</span></span>
  
<span data-ttu-id="e7358-383">Gebruik de **cmdlet Set-PnPTenantCdnPolicy** om statische bestandstypen te definiëren die kunnen worden gehost door openbare en private origins in de CDN.</span><span class="sxs-lookup"><span data-stu-id="e7358-383">Use the **Set-PnPTenantCdnPolicy** cmdlet to define static file types that can be hosted by public and private origins in the CDN.</span></span> <span data-ttu-id="e7358-384">Standaard zijn veelgebruikte activatypen toegestaan, zoals .css, .gif, .jpg en .js.</span><span class="sxs-lookup"><span data-stu-id="e7358-384">By default, common asset types are allowed, for example .css, .gif, .jpg, and .js.</span></span>

<span data-ttu-id="e7358-385">In PnP PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e7358-385">In PnP PowerShell:</span></span>

```powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

<span data-ttu-id="e7358-386">Als u bijvoorbeeld de CDN css en .png wilt hosten, voert u de opdracht in:</span><span class="sxs-lookup"><span data-stu-id="e7358-386">For example, to enable the CDN to host .css and .png files, you would enter the command:</span></span>

```powershell
Set-PnPTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

<span data-ttu-id="e7358-387">Gebruik de **cmdlet Get-PnPTenantCdnPolicies** om te zien welke bestandstypen momenteel door de CDN zijn toegestaan:</span><span class="sxs-lookup"><span data-stu-id="e7358-387">To see what file types are currently allowed by the CDN, use the **Get-PnPTenantCdnPolicies** cmdlet:</span></span>

```powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="e7358-388">Zie [Set-PnPTenantCdnPolicy](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) and [Get-PnPTenantCdnPolicies (Set-PnPTenantCdnPolicy en Get-PnPTenantCdnPolicies)](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies)voor meer informatie over deze cmdlets.</span><span class="sxs-lookup"><span data-stu-id="e7358-388">For more information about these cmdlets, see [Set-PnPTenantCdnPolicy](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) and [Get-PnPTenantCdnPolicies](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).</span></span>

<span data-ttu-id="e7358-389"><a name="Office365CDNforPnPPoshSiteClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="e7358-389"><a name="Office365CDNforPnPPoshSiteClassification"> </a></span></span>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a><span data-ttu-id="e7358-390">De lijst met siteclassificaties wijzigen die u wilt uitsluiten van de Office 365 CDN (Optioneel)</span><span class="sxs-lookup"><span data-stu-id="e7358-390">Change the list of site classifications you want to exclude from the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="e7358-391">Wanneer u siteclassificaties uitsluit met de **cmdlet Set-PnPTenantCdnPolicy,** overschrijft u de momenteel gedefinieerde lijst.</span><span class="sxs-lookup"><span data-stu-id="e7358-391">When you exclude site classifications by using the **Set-PnPTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="e7358-392">Als u extra siteclassificaties wilt uitsluiten, gebruikt u de cmdlet eerst om te kijken welke classificaties al zijn uitgesloten en voegt u deze vervolgens samen met de nieuwe toe.</span><span class="sxs-lookup"><span data-stu-id="e7358-392">If you want to exclude additional site classifications, use the cmdlet first to find out what classifications are already excluded and then add them along with your new ones.</span></span>

<span data-ttu-id="e7358-393">Gebruik de **cmdlet Set-PnPTenantCdnPolicy** om siteclassificaties uit te sluiten die u niet beschikbaar wilt maken in de CDN.</span><span class="sxs-lookup"><span data-stu-id="e7358-393">Use the **Set-PnPTenantCdnPolicy** cmdlet to exclude site classifications that you do not want to make available over the CDN.</span></span> <span data-ttu-id="e7358-394">Standaard worden geen siteclassificaties uitgesloten.</span><span class="sxs-lookup"><span data-stu-id="e7358-394">By default, no site classifications are excluded.</span></span>

<span data-ttu-id="e7358-395">In PnP PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e7358-395">In PnP PowerShell:</span></span>

```powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications>"
```

<span data-ttu-id="e7358-396">Als u wilt zien welke siteclassificaties momenteel zijn beperkt, gebruikt u de **cmdlet Get-PnPTenantCdnPolicies:**</span><span class="sxs-lookup"><span data-stu-id="e7358-396">To see what site classifications are currently restricted, use the **Get-PnPTenantCdnPolicies** cmdlet:</span></span>

```powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="e7358-397">De eigenschappen die worden geretourneerd, zijn _IncludeFileExtensions,_ _ExcludeRestrictedSiteClassifications_ en _ExcludeIfNoScriptDisabled_.</span><span class="sxs-lookup"><span data-stu-id="e7358-397">The properties that will be returned are _IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ and _ExcludeIfNoScriptDisabled_.</span></span>

<span data-ttu-id="e7358-398">De _eigenschap IncludeFileExtensions_ bevat de lijst met bestandsextensies die vanaf de CDN.</span><span class="sxs-lookup"><span data-stu-id="e7358-398">The _IncludeFileExtensions_ property contains the list of file extensions that will be served from the CDN.</span></span>

> [!NOTE]
> <span data-ttu-id="e7358-399">De standaardbestandsextensies verschillen tussen openbaar en privé.</span><span class="sxs-lookup"><span data-stu-id="e7358-399">The default file extensions are different between public and private.</span></span>

<span data-ttu-id="e7358-400">De _eigenschap ExcludeRestrictedSiteClassifications_ bevat de siteclassificaties die u wilt uitsluiten van de CDN.</span><span class="sxs-lookup"><span data-stu-id="e7358-400">The _ExcludeRestrictedSiteClassifications_ property contains the site classifications that you want to exclude from the CDN.</span></span> <span data-ttu-id="e7358-401">U kunt bijvoorbeeld sites uitsluiten die zijn gemarkeerd als **Vertrouwelijk,** zodat inhoud van sites met die classificatie die is toegepast, niet wordt gebruikt vanaf de CDN.</span><span class="sxs-lookup"><span data-stu-id="e7358-401">For example, you can exclude sites marked as **Confidential** so content from sites with that classification applied will not be served from the CDN.</span></span>

<span data-ttu-id="e7358-402">De _eigenschap ExcludeIfNoScriptDisabled_ sluit inhoud uit van de CDN op basis van de _noScript-kenmerkinstellingen_ op siteniveau.</span><span class="sxs-lookup"><span data-stu-id="e7358-402">The _ExcludeIfNoScriptDisabled_ property excludes content from the CDN based on the site-level _NoScript_ attribute settings.</span></span> <span data-ttu-id="e7358-403">Het kenmerk _NoScript_ is standaard ingesteld op **Ingeschakeld voor** _moderne_ sites en **Uitgeschakeld** voor _klassieke_ sites.</span><span class="sxs-lookup"><span data-stu-id="e7358-403">By default, the _NoScript_ attribute is set to **Enabled** for _Modern_ sites and **Disabled** for _Classic_ sites.</span></span> <span data-ttu-id="e7358-404">Dit is afhankelijk van uw tenantinstellingen.</span><span class="sxs-lookup"><span data-stu-id="e7358-404">This depends on your tenant settings.</span></span>

<span data-ttu-id="e7358-405">Zie [Set-PnPTenantCdnPolicy](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) and [Get-PnPTenantCdnPolicies (Set-PnPTenantCdnPolicy en Get-PnPTenantCdnPolicies)](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies)voor meer informatie over deze cmdlets.</span><span class="sxs-lookup"><span data-stu-id="e7358-405">For more information about these cmdlets, see [Set-PnPTenantCdnPolicy](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) and [Get-PnPTenantCdnPolicies](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).</span></span>

<span data-ttu-id="e7358-406"><a name="Office365CDNforSPOOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="e7358-406"><a name="Office365CDNforSPOOriginPnPPosh"> </a></span></span>
### <a name="add-an-origin-for-your-assets"></a><span data-ttu-id="e7358-407">Een origin toevoegen voor uw activa</span><span class="sxs-lookup"><span data-stu-id="e7358-407">Add an origin for your assets</span></span>

<span data-ttu-id="e7358-408">Gebruik de **cmdlet Add-PnPTenantCdnOrigin** om een origin te definiëren.</span><span class="sxs-lookup"><span data-stu-id="e7358-408">Use the **Add-PnPTenantCdnOrigin** cmdlet to define an origin.</span></span> <span data-ttu-id="e7358-409">U kunt meerdere origins definiëren.</span><span class="sxs-lookup"><span data-stu-id="e7358-409">You can define multiple origins.</span></span> <span data-ttu-id="e7358-410">De origin is een URL die wijst naar een SharePoint of map die de assets bevat die u wilt hosten door de CDN.</span><span class="sxs-lookup"><span data-stu-id="e7358-410">The origin is a URL that points to a SharePoint library or folder that contains the assets that you want to be hosted by the CDN.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e7358-411">U mag nooit resources plaatsen die gebruikersgegevens bevatten of die als gevoelig voor uw organisatie worden beschouwd in een openbare origin.</span><span class="sxs-lookup"><span data-stu-id="e7358-411">You should never place resources that contain user information or are considered sensitive to your organization in a public origin.</span></span>

```powershell
Add-PnPTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

<span data-ttu-id="e7358-412">De waarde van _pad_ is het relatieve pad naar de bibliotheek of map die de assets bevat.</span><span class="sxs-lookup"><span data-stu-id="e7358-412">The value of _path_ is the relative path to the library or folder that contains the assets.</span></span> <span data-ttu-id="e7358-413">U kunt jokertekens gebruiken naast relatieve paden.</span><span class="sxs-lookup"><span data-stu-id="e7358-413">You can use wildcards in addition to relative paths.</span></span> <span data-ttu-id="e7358-414">Origins ondersteunt jokertekens die zijn voorbereid op de URL.</span><span class="sxs-lookup"><span data-stu-id="e7358-414">Origins support wildcards prepended to the URL.</span></span> <span data-ttu-id="e7358-415">Op deze manier kunt u origins maken die meerdere sites bespannen.</span><span class="sxs-lookup"><span data-stu-id="e7358-415">This allows you to create origins that span multiple sites.</span></span> <span data-ttu-id="e7358-416">Als u bijvoorbeeld alle assets wilt opnemen in de map met basispagina's voor al uw sites als openbare origin in de CDN, typt u de volgende opdracht:</span><span class="sxs-lookup"><span data-stu-id="e7358-416">For example, to include all of the assets in the masterpages folder for all of your sites as a public origin within the CDN, type the following command:</span></span>

```powershell
Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ <span data-ttu-id="e7358-417">De jokertekenmodule \* kan alleen worden gebruikt aan het begin van het pad en komt overeen met alle URL-segmenten **/** onder de opgegeven URL.</span><span class="sxs-lookup"><span data-stu-id="e7358-417">The wildcard modifier \***/** can only be used at the beginning of the path, and will match all URL segments under the specified URL.</span></span>
+ <span data-ttu-id="e7358-418">Het pad kan naar een documentbibliotheek, map of site wijzen.</span><span class="sxs-lookup"><span data-stu-id="e7358-418">The path can point to a document library, folder or site.</span></span> <span data-ttu-id="e7358-419">Het pad _\*/site1_ komt bijvoorbeeld overeen met alle documentbibliotheken onder de site.</span><span class="sxs-lookup"><span data-stu-id="e7358-419">For example, the path _\*/site1_ will match all the document libraries under the site.</span></span>

<span data-ttu-id="e7358-420">U kunt een origin toevoegen met een specifiek relatieve pad.</span><span class="sxs-lookup"><span data-stu-id="e7358-420">You can add an origin with a specific relative path.</span></span> <span data-ttu-id="e7358-421">U kunt geen origin toevoegen met het volledige pad.</span><span class="sxs-lookup"><span data-stu-id="e7358-421">You cannot add an origin using the full path.</span></span>

<span data-ttu-id="e7358-422">In dit voorbeeld wordt een persoonlijke origin van de siteactivabibliotheek op een specifieke site toegevoegd:</span><span class="sxs-lookup"><span data-stu-id="e7358-422">This example adds a private origin of the site assets library on a specific site:</span></span>

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="e7358-423">In dit voorbeeld wordt een persoonlijke origin van de _map1_ toegevoegd aan de siteactivabibliotheek van de siteverzameling:</span><span class="sxs-lookup"><span data-stu-id="e7358-423">This example adds a private origin of the _folder1_ folder in the site collection's site assets library:</span></span>

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

<span data-ttu-id="e7358-424">Als er een spatie in het pad is, kunt u het pad omringen met dubbele aanhalingstekens of de spatie vervangen door de URL-codering %20.</span><span class="sxs-lookup"><span data-stu-id="e7358-424">If there is a space in the path, you can either surround the path in double quotes or replace the space with the URL encoding %20.</span></span> <span data-ttu-id="e7358-425">In de volgende voorbeelden wordt een persoonlijke origin van de _map 1_ in de siteactivabibliotheek van de siteverzameling toegevoegd:</span><span class="sxs-lookup"><span data-stu-id="e7358-425">The following examples add a private origin of the _folder 1_ folder in the site collection's site assets library:</span></span>

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

<span data-ttu-id="e7358-426">Zie [Add-PnPTenantCdnOrigin (Add-PnPTenantCdnOrigin)](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)voor meer informatie over deze opdracht en de syntaxis ervan.</span><span class="sxs-lookup"><span data-stu-id="e7358-426">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>

> [!NOTE]
> <span data-ttu-id="e7358-427">In privé-origins moeten activa die vanaf een origin worden gedeeld, een hoofdversie hebben gepubliceerd voordat ze vanaf de CDN.</span><span class="sxs-lookup"><span data-stu-id="e7358-427">In private origins, assets being shared from an origin must have a major version published before they can be accessed from the CDN.</span></span>
  
<span data-ttu-id="e7358-428">Wanneer u de opdracht hebt uitgevoerd, synchroniseert het systeem de configuratie in het datacenter.</span><span class="sxs-lookup"><span data-stu-id="e7358-428">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="e7358-429">Dit kan maximaal 15 minuten duren.</span><span class="sxs-lookup"><span data-stu-id="e7358-429">This can take up to 15 minutes.</span></span>

<span data-ttu-id="e7358-430"><a name="ExamplePublicOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="e7358-430"><a name="ExamplePublicOriginPnPPosh"> </a></span></span>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a><span data-ttu-id="e7358-431">Voorbeeld: Een openbare origin configureren voor uw basispagina's en voor uw stijlbibliotheek voor SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="e7358-431">Example: Configure a public origin for your master pages and for your style library for SharePoint Online</span></span>

<span data-ttu-id="e7358-432">Normaal gesproken worden deze origins standaard voor u ingesteld wanneer u de Office 365 CDN.</span><span class="sxs-lookup"><span data-stu-id="e7358-432">Normally, these origins are set up for you by default when you enable the Office 365 CDN.</span></span> <span data-ttu-id="e7358-433">Als u ze echter handmatig wilt inschakelen, volgt u deze stappen.</span><span class="sxs-lookup"><span data-stu-id="e7358-433">However, if you want to enable them manually, follow these steps.</span></span>
  
+ <span data-ttu-id="e7358-434">Gebruik de **cmdlet Add-PnPTenantCdnOrigin** om de stijlbibliotheek te definiëren als een openbare origin.</span><span class="sxs-lookup"><span data-stu-id="e7358-434">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the style library as a public origin.</span></span>

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ <span data-ttu-id="e7358-435">Gebruik de **cmdlet Add-PnPTenantCdnOrigin** om de basispagina's te definiëren als een openbare origin.</span><span class="sxs-lookup"><span data-stu-id="e7358-435">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the master pages as a public origin.</span></span>

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

<span data-ttu-id="e7358-436">Zie [Add-PnPTenantCdnOrigin (Add-PnPTenantCdnOrigin)](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)voor meer informatie over deze opdracht en de syntaxis ervan.</span><span class="sxs-lookup"><span data-stu-id="e7358-436">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>

<span data-ttu-id="e7358-437">Wanneer u de opdracht hebt uitgevoerd, synchroniseert het systeem de configuratie in het datacenter.</span><span class="sxs-lookup"><span data-stu-id="e7358-437">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="e7358-438">Dit kan maximaal 15 minuten duren.</span><span class="sxs-lookup"><span data-stu-id="e7358-438">This can take up to 15 minutes.</span></span>

<span data-ttu-id="e7358-439"><a name="ExamplePrivateOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="e7358-439"><a name="ExamplePrivateOriginPnPPosh"> </a></span></span>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a><span data-ttu-id="e7358-440">Voorbeeld: Een persoonlijke origin configureren voor uw siteactiva, sitepagina's en publicerende afbeeldingen voor SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="e7358-440">Example: Configure a private origin for your site assets, site pages, and publishing images for SharePoint Online</span></span>

+ <span data-ttu-id="e7358-441">Gebruik de **cmdlet Add-PnPTenantCdnOrigin** om de map met siteactiva te definiëren als een persoonlijke origin.</span><span class="sxs-lookup"><span data-stu-id="e7358-441">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the site assets folder as a private origin.</span></span>

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ <span data-ttu-id="e7358-442">Gebruik de **cmdlet Add-PnPTenantCdnOrigin** om de map sitepagina's te definiëren als een persoonlijke origin.</span><span class="sxs-lookup"><span data-stu-id="e7358-442">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the site pages folder as a private origin.</span></span>

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ <span data-ttu-id="e7358-443">Gebruik de **cmdlet Add-PnPTenantCdnOrigin** om de map publicerende afbeeldingen te definiëren als een persoonlijke origin.</span><span class="sxs-lookup"><span data-stu-id="e7358-443">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the publishing images folder as a private origin.</span></span>

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

<span data-ttu-id="e7358-444">Zie [Add-PnPTenantCdnOrigin (Add-PnPTenantCdnOrigin)](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)voor meer informatie over deze opdracht en de syntaxis ervan.</span><span class="sxs-lookup"><span data-stu-id="e7358-444">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>

<span data-ttu-id="e7358-445">Wanneer u de opdracht hebt uitgevoerd, synchroniseert het systeem de configuratie in het datacenter.</span><span class="sxs-lookup"><span data-stu-id="e7358-445">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="e7358-446">Dit kan maximaal 15 minuten duren.</span><span class="sxs-lookup"><span data-stu-id="e7358-446">This can take up to 15 minutes.</span></span>

<span data-ttu-id="e7358-447"><a name="ExamplePrivateOriginSiteCollectionPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="e7358-447"><a name="ExamplePrivateOriginSiteCollectionPnPPosh"> </a></span></span>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a><span data-ttu-id="e7358-448">Voorbeeld: Een persoonlijke origin configureren voor een siteverzameling voor SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="e7358-448">Example: Configure a private origin for a site collection for SharePoint Online</span></span>

<span data-ttu-id="e7358-449">Gebruik de **cmdlet Add-PnPTenantCdnOrigin** om een siteverzameling te definiëren als een persoonlijke origin.</span><span class="sxs-lookup"><span data-stu-id="e7358-449">Use the **Add-PnPTenantCdnOrigin** cmdlet to define a site collection as a private origin.</span></span> <span data-ttu-id="e7358-450">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="e7358-450">For example:</span></span>

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="e7358-451">Zie [Add-PnPTenantCdnOrigin (Add-PnPTenantCdnOrigin)](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)voor meer informatie over deze opdracht en de syntaxis ervan.</span><span class="sxs-lookup"><span data-stu-id="e7358-451">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>
  
<span data-ttu-id="e7358-452">Wanneer u de opdracht hebt uitgevoerd, synchroniseert het systeem de configuratie in het datacenter.</span><span class="sxs-lookup"><span data-stu-id="e7358-452">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="e7358-453">Mogelijk ziet u een _bericht in_ behandeling met configuratie dat wordt verwacht wanneer de SharePoint Online-tenant verbinding maakt met de CDN service.</span><span class="sxs-lookup"><span data-stu-id="e7358-453">You may see a _Configuration pending_ message which is expected as the SharePoint Online tenant connects to the CDN service.</span></span> <span data-ttu-id="e7358-454">Dit kan maximaal 15 minuten duren.</span><span class="sxs-lookup"><span data-stu-id="e7358-454">This can take up to 15 minutes.</span></span>

<span data-ttu-id="e7358-455"><a name="CDNManagePnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="e7358-455"><a name="CDNManagePnPPosh"> </a></span></span>
### <a name="manage-the-office-365-cdn"></a><span data-ttu-id="e7358-456">De Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="e7358-456">Manage the Office 365 CDN</span></span>

<span data-ttu-id="e7358-457">Nadat u de CDN hebt ingesteld, kunt u wijzigingen aanbrengen in uw configuratie terwijl u inhoud bij werk of als uw behoeften veranderen, zoals in deze sectie wordt beschreven.</span><span class="sxs-lookup"><span data-stu-id="e7358-457">Once you've set up the CDN, you can make changes to your configuration as you update content or as your needs change, as described in this section.</span></span>
  
<span data-ttu-id="e7358-458"><a name="Office365CDNforSPOaddremoveassetPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="e7358-458"><a name="Office365CDNforSPOaddremoveassetPnPPosh"> </a></span></span>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a><span data-ttu-id="e7358-459">Activa toevoegen, bijwerken of verwijderen uit de Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="e7358-459">Add, update, or remove assets from the Office 365 CDN</span></span>

<span data-ttu-id="e7358-460">Nadat u de installatiestappen hebt voltooid, kunt u nieuwe activa toevoegen en bestaande assets bijwerken of verwijderen wanneer u maar wilt.</span><span class="sxs-lookup"><span data-stu-id="e7358-460">Once you've completed the setup steps, you can add new assets, and update or remove existing assets whenever you want.</span></span> <span data-ttu-id="e7358-461">Pas uw wijzigingen aan in de assets in de map of SharePoint bibliotheek die u hebt geïdentificeerd als een origin.</span><span class="sxs-lookup"><span data-stu-id="e7358-461">Just make your changes to the assets in the folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="e7358-462">Als u een nieuw activum toevoegt, is deze direct beschikbaar via CDN.</span><span class="sxs-lookup"><span data-stu-id="e7358-462">If you add a new asset, it is available through the CDN immediately.</span></span> <span data-ttu-id="e7358-463">Als u het activum echter bij werkt, duurt het maximaal 15 minuten voordat de nieuwe kopie wordt doorgegeven en beschikbaar komt in de CDN.</span><span class="sxs-lookup"><span data-stu-id="e7358-463">However, if you update the asset, it will take up to 15 minutes for the new copy to propagate and become available in the CDN.</span></span>
  
<span data-ttu-id="e7358-464">Als u de locatie van de origin wilt ophalen, kunt u de **cmdlet Get-PnPTenantCdnOrigin** gebruiken.</span><span class="sxs-lookup"><span data-stu-id="e7358-464">If you need to retrieve the location of the origin, you can use the **Get-PnPTenantCdnOrigin** cmdlet.</span></span> <span data-ttu-id="e7358-465">Zie [Get-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/get-pnptenantcdnorigin)voor meer informatie over het gebruik van deze cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e7358-465">For information on how to use this cmdlet, see [Get-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/get-pnptenantcdnorigin).</span></span>

<span data-ttu-id="e7358-466"><a name="Office365CDNforSPORemoveOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="e7358-466"><a name="Office365CDNforSPORemoveOriginPnPPosh"> </a></span></span>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a><span data-ttu-id="e7358-467">Een origin verwijderen uit de Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="e7358-467">Remove an origin from the Office 365 CDN</span></span>

<span data-ttu-id="e7358-468">U kunt de toegang tot een map of bibliotheek SharePoint verwijderen die u hebt geïdentificeerd als een origin.</span><span class="sxs-lookup"><span data-stu-id="e7358-468">You can remove access to a folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="e7358-469">Gebruik hiervoor de **cmdlet Remove-PnPTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="e7358-469">To do this, use the **Remove-PnPTenantCdnOrigin** cmdlet.</span></span>

```powershell
Remove-PnPTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

<span data-ttu-id="e7358-470">Zie [Remove-PnPTenantCdnOrigin (Verwijderen-PnPTenantCdnOrigin)](/powershell/module/sharepoint-pnp/remove-pnptenantcdnorigin)voor meer informatie over het gebruik van deze cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e7358-470">For information on how to use this cmdlet, see [Remove-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/remove-pnptenantcdnorigin).</span></span>

<span data-ttu-id="e7358-471"><a name="Office365CDNforSPOModifyOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="e7358-471"><a name="Office365CDNforSPOModifyOriginPnPPosh"> </a></span></span>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a><span data-ttu-id="e7358-472">Een origin in de Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="e7358-472">Modify an origin in the Office 365 CDN</span></span>

<span data-ttu-id="e7358-473">U kunt een origin die u hebt gemaakt niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="e7358-473">You cannot modify an origin you've created.</span></span> <span data-ttu-id="e7358-474">In plaats daarvan verwijdert u de origin en voegt u een nieuwe toe.</span><span class="sxs-lookup"><span data-stu-id="e7358-474">Instead, remove the origin and then add a new one.</span></span> <span data-ttu-id="e7358-475">Zie Een origin verwijderen [uit de](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPnPPosh) Office 365 CDN en Een origin toevoegen voor uw assets voor [meer informatie.](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPnPPosh)</span><span class="sxs-lookup"><span data-stu-id="e7358-475">For more information, see [To remove an origin from the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPnPPosh) and [To add an origin for your assets](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPnPPosh).</span></span>

<span data-ttu-id="e7358-476"><a name="Office365CDNforSPODisable"> </a></span><span class="sxs-lookup"><span data-stu-id="e7358-476"><a name="Office365CDNforSPODisable"> </a></span></span>
#### <a name="disable-the-office-365-cdn"></a><span data-ttu-id="e7358-477">De Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="e7358-477">Disable the Office 365 CDN</span></span>

<span data-ttu-id="e7358-478">Gebruik de **cmdlet Set-PnPTenantCdnEnabled om** de CDN voor uw organisatie uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="e7358-478">Use the **Set-PnPTenantCdnEnabled** cmdlet to disable the CDN for your organization.</span></span> <span data-ttu-id="e7358-479">Als u zowel de openbare als de privé-origins hebt ingeschakeld voor de CDN, moet u de cmdlet tweemaal uitvoeren, zoals wordt weergegeven in de volgende voorbeelden.</span><span class="sxs-lookup"><span data-stu-id="e7358-479">If you have both the public and private origins enabled for the CDN, you need to run the cmdlet twice as shown in the following examples.</span></span>
  
<span data-ttu-id="e7358-480">Als u het gebruik van openbare origins in de CDN wilt uitschakelen, voert u de volgende opdracht in:</span><span class="sxs-lookup"><span data-stu-id="e7358-480">To disable use of public origins in the CDN, enter the following command:</span></span>

```powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $false
```

<span data-ttu-id="e7358-481">Als u het gebruik van de privé-origins in de CDN wilt uitschakelen, voert u de volgende opdracht in:</span><span class="sxs-lookup"><span data-stu-id="e7358-481">To disable use of the private origins in the CDN, enter the following command:</span></span>

```powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $false
```

<span data-ttu-id="e7358-482">Zie [Set-PnPTenantCdnEnabled voor meer informatie over deze cmdlet.](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled)</span><span class="sxs-lookup"><span data-stu-id="e7358-482">For more information about this cmdlet, see [Set-PnPTenantCdnEnabled](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled).</span></span>

</details>

<span data-ttu-id="e7358-483"><a name="CDNSetupinCLI"> </a></span><span class="sxs-lookup"><span data-stu-id="e7358-483"><a name="CDNSetupinCLI"> </a></span></span>
## <a name="set-up-and-configure-the-office-365-cdn-using-the-office-365-cli"></a><span data-ttu-id="e7358-484">De Office 365 CDN instellen en configureren met Office 365 CLI</span><span class="sxs-lookup"><span data-stu-id="e7358-484">Set up and configure the Office 365 CDN using the Office 365 CLI</span></span>

<span data-ttu-id="e7358-485">Voor de procedures in deze sectie moet u de Office 365 [CLI.](https://aka.ms/o365cli)</span><span class="sxs-lookup"><span data-stu-id="e7358-485">The procedures in this section require that you have installed the [Office 365 CLI](https://aka.ms/o365cli).</span></span> <span data-ttu-id="e7358-486">Maak vervolgens verbinding met uw Office 365 tenant met de [opdracht Aanmelden.](https://pnp.github.io/office365-cli/cmd/login/)</span><span class="sxs-lookup"><span data-stu-id="e7358-486">Next, connect to your Office 365 tenant using the [login](https://pnp.github.io/office365-cli/cmd/login/) command.</span></span>

<span data-ttu-id="e7358-487">Voltooi deze stappen voor het instellen en configureren van de CDN om uw assets te hosten in SharePoint Online met behulp van Office 365 CLI.</span><span class="sxs-lookup"><span data-stu-id="e7358-487">Complete these steps to set up and configure the CDN to host your assets in SharePoint Online using the Office 365 CLI.</span></span>

<details>
  <summary><span data-ttu-id="e7358-488">Klik om uit te vouwen</span><span class="sxs-lookup"><span data-stu-id="e7358-488">Click to expand</span></span></summary>

### <a name="enable-the-office-365-cdn"></a><span data-ttu-id="e7358-489">De Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="e7358-489">Enable the Office 365 CDN</span></span>

<span data-ttu-id="e7358-490">U kunt de status van de Office 365 CDN in uw tenant beheren met de [opdracht SPO-cdn-set.](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-set/)</span><span class="sxs-lookup"><span data-stu-id="e7358-490">You can manage the state of the Office 365 CDN in your tenant using the [spo cdn set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-set/) command.</span></span>

<span data-ttu-id="e7358-491">Als u de Office 365 openbare CDN in uw tenant wilt inschakelen, voert u het volgende uit:</span><span class="sxs-lookup"><span data-stu-id="e7358-491">To enable the Office 365 Public CDN in your tenant execute:</span></span>

```cli
spo cdn set --type Public --enabled true
```

<span data-ttu-id="e7358-492">Voer de volgende Office 365 SharePoint CDN uit om de Office 365 SharePoint CDN in te stellen:</span><span class="sxs-lookup"><span data-stu-id="e7358-492">To enable the Office 365 SharePoint CDN, execute:</span></span>

```cli
spo cdn set --type Private --enabled true
```

#### <a name="view-the-current-status-of-the-office-365-cdn"></a><span data-ttu-id="e7358-493">De huidige status van de Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="e7358-493">View the current status of the Office 365 CDN</span></span>

<span data-ttu-id="e7358-494">Als u wilt controleren of het specifieke type Office 365 CDN is ingeschakeld of uitgeschakeld, gebruikt u de [opdracht spo cdn get.](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-get/)</span><span class="sxs-lookup"><span data-stu-id="e7358-494">To check if the particular type of Office 365 CDN is enabled or disabled, use the [spo cdn get](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-get/) command.</span></span>

<span data-ttu-id="e7358-495">Als u wilt controleren of Office 365 openbare CDN is ingeschakeld, voert u het volgende uit:</span><span class="sxs-lookup"><span data-stu-id="e7358-495">To check if the Office 365 Public CDN is enabled, execute:</span></span>

```cli
spo cdn get --type Public
```

### <a name="view-the-office-365-cdn-origins"></a><span data-ttu-id="e7358-496">De oorspronkelijke Office 365 CDN weergeven</span><span class="sxs-lookup"><span data-stu-id="e7358-496">View the Office 365 CDN origins</span></span>

<span data-ttu-id="e7358-497">Als u de momenteel geconfigureerde Office 365 openbare CDN origins wilt weergeven:</span><span class="sxs-lookup"><span data-stu-id="e7358-497">To view the currently configured Office 365 Public CDN origins execute:</span></span>

```cli
spo cdn origin list --type Public
```

<span data-ttu-id="e7358-498">Zie [Standaardinstellingen CDN origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) voor informatie over de origins die standaard zijn ingericht wanneer u de Office 365 CDN.</span><span class="sxs-lookup"><span data-stu-id="e7358-498">See [Default CDN origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) for information about the origins that are provisioned by default when you enable the Office 365 CDN.</span></span>

### <a name="add-an-office-365-cdn-origin"></a><span data-ttu-id="e7358-499">Een oorspronkelijke Office 365 CDN toevoegen</span><span class="sxs-lookup"><span data-stu-id="e7358-499">Add an Office 365 CDN origin</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e7358-500">U mag resources die als gevoelig voor uw organisatie worden beschouwd, nooit in een SharePoint documentbibliotheek plaatsen die is geconfigureerd als een openbare origin.</span><span class="sxs-lookup"><span data-stu-id="e7358-500">You should never place resources that are considered sensitive to your organization in a SharePoint document library configured as a public origin.</span></span>

<span data-ttu-id="e7358-501">Gebruik de [opdracht SPO CDN Origin Add om](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-add/) een CDN definiëren.</span><span class="sxs-lookup"><span data-stu-id="e7358-501">Use the [spo cdn origin add](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-add/) command to define a CDN origin.</span></span> <span data-ttu-id="e7358-502">U kunt meerdere origins definiëren.</span><span class="sxs-lookup"><span data-stu-id="e7358-502">You can define multiple origins.</span></span> <span data-ttu-id="e7358-503">De origin is een URL die wijst naar een SharePoint of map die de assets bevat die u wilt hosten door de CDN.</span><span class="sxs-lookup"><span data-stu-id="e7358-503">The origin is a URL that points to a SharePoint library or folder that contains the assets that you want to be hosted by the CDN.</span></span>

```cli
spo cdn origin add --type [Public | Private] --origin <path>
```

<span data-ttu-id="e7358-504">Waar `path` is het relatieve pad naar de map met de assets.</span><span class="sxs-lookup"><span data-stu-id="e7358-504">Where `path` is the relative path to the folder that contains the assets.</span></span> <span data-ttu-id="e7358-505">U kunt jokertekens gebruiken naast relatieve paden.</span><span class="sxs-lookup"><span data-stu-id="e7358-505">You can use wildcards in addition to relative paths.</span></span>

<span data-ttu-id="e7358-506">Als u alle activa in de galerie met **basispagina's** van alle sites wilt opnemen als openbare origin, voert u het volgende uit:</span><span class="sxs-lookup"><span data-stu-id="e7358-506">To include all assets in the **Master Page Gallery** of all sites as a public origin, execute:</span></span>

```cli
spo cdn origin add --type Public --origin */masterpage
```

<span data-ttu-id="e7358-507">Als u een persoonlijke origin wilt configureren voor een specifieke siteverzameling, voert u het volgende uit:</span><span class="sxs-lookup"><span data-stu-id="e7358-507">To configure a private origin for a specific site collection, execute:</span></span>

```cli
spo cdn origin add --type Private --origin sites/site1/siteassets
```

> [!NOTE]
> <span data-ttu-id="e7358-508">Nadat u een CDN hebt toegevoegd, kan het tot 15 minuten duren voordat u bestanden kunt ophalen via de CDN service.</span><span class="sxs-lookup"><span data-stu-id="e7358-508">After adding a CDN origin, it might take up to 15 minutes for you to be able to retrieve files via the CDN service.</span></span> <span data-ttu-id="e7358-509">U kunt controleren of de specifieke origin al is ingeschakeld met de [opdracht SPO CDN Origin List.](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/)</span><span class="sxs-lookup"><span data-stu-id="e7358-509">You can verify if the particular origin has already been enabled using the [spo cdn origin list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) command.</span></span>

### <a name="remove-an-office-365-cdn-origin"></a><span data-ttu-id="e7358-510">Een oorspronkelijke Office 365 CDN verwijderen</span><span class="sxs-lookup"><span data-stu-id="e7358-510">Remove an Office 365 CDN origin</span></span>

<span data-ttu-id="e7358-511">Gebruik de [opdracht SPO CDN Origin Remove om](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-remove/) een CDN voor het opgegeven CDN verwijderen.</span><span class="sxs-lookup"><span data-stu-id="e7358-511">Use the [spo cdn origin remove](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-remove/) command to remove a CDN origin for the specified CDN type.</span></span>

<span data-ttu-id="e7358-512">Als u een openbare origin wilt verwijderen uit de CDN configuratie, voert u het volgende uit:</span><span class="sxs-lookup"><span data-stu-id="e7358-512">To remove a public origin from the CDN configuration, execute:</span></span>

```cli
spo cdn origin remove --type Public --origin */masterpage
```

> [!NOTE]
> <span data-ttu-id="e7358-513">Het verwijderen CDN origin heeft geen invloed op de bestanden die zijn opgeslagen in een documentbibliotheek die overeenkomt met die origin.</span><span class="sxs-lookup"><span data-stu-id="e7358-513">Removing a CDN origin doesn't affect the files stored in any document library matching that origin.</span></span> <span data-ttu-id="e7358-514">Als naar deze assets wordt verwezen met behulp van SharePoint URL, SharePoint automatisch terug naar de oorspronkelijke URL die naar de documentbibliotheek wijst.</span><span class="sxs-lookup"><span data-stu-id="e7358-514">If these assets have been referenced using their SharePoint URL, SharePoint will automatically switch back to the original URL pointing to the document library.</span></span> <span data-ttu-id="e7358-515">Als er echter naar activa is verwezen met een openbare CDN URL, wordt de koppeling door het verwijderen van de origin verwijderd en moet u deze handmatig wijzigen.</span><span class="sxs-lookup"><span data-stu-id="e7358-515">If, however, assets have been referenced using a public CDN URL, then removing the origin will break the link and you will need to manually change them.</span></span>

### <a name="modify-an-office-365-cdn-origin"></a><span data-ttu-id="e7358-516">Een oorspronkelijke Office 365 CDN wijzigen</span><span class="sxs-lookup"><span data-stu-id="e7358-516">Modify an Office 365 CDN origin</span></span>

<span data-ttu-id="e7358-517">Het is niet mogelijk om een bestaande CDN wijzigen.</span><span class="sxs-lookup"><span data-stu-id="e7358-517">It's not possible to modify an existing CDN origin.</span></span> <span data-ttu-id="e7358-518">In plaats daarvan moet u de eerder gedefinieerde origin CDN de opdracht verwijderen en een nieuwe met `spo cdn origin remove` de opdracht `spo cdn origin add` toevoegen.</span><span class="sxs-lookup"><span data-stu-id="e7358-518">Instead, you should remove the previously defined CDN origin using the `spo cdn origin remove` command and add a new one using the `spo cdn origin add` command.</span></span>

### <a name="change-the-types-of-files-to-include-in-the-office-365-cdn"></a><span data-ttu-id="e7358-519">De typen bestanden wijzigen die u wilt opnemen in de Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="e7358-519">Change the types of files to include in the Office 365 CDN</span></span>

<span data-ttu-id="e7358-520">Standaard worden de volgende bestandstypen opgenomen in de CDN: _.css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff en .woff2_.</span><span class="sxs-lookup"><span data-stu-id="e7358-520">By default, the following file types are included in the CDN: _.css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff and .woff2_.</span></span> <span data-ttu-id="e7358-521">Als u extra bestandstypen wilt opnemen in de CDN, kunt u de configuratie van de CDN wijzigen met de [opdracht SPO CDN-beleidset.](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/)</span><span class="sxs-lookup"><span data-stu-id="e7358-521">If you need to include additional file types in the CDN, you can change the CDN configuration using the [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) command.</span></span>

> [!NOTE]
> <span data-ttu-id="e7358-522">Wanneer u de lijst met bestandstypen verandert, overschrijft u de lijst die momenteel is gedefinieerd.</span><span class="sxs-lookup"><span data-stu-id="e7358-522">When changing the list of file types, you overwrite the currently defined list.</span></span> <span data-ttu-id="e7358-523">Als u extra bestandstypen wilt opnemen, gebruikt u eerst de opdracht lijst met [spo-cdn-beleid](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) om erachter te komen welke bestandstypen momenteel zijn geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="e7358-523">If you want to include additional file types, first use the [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) command to find out which file types are currently configured.</span></span>

<span data-ttu-id="e7358-524">Als u het _JSON-bestandstype_ wilt toevoegen aan de standaardlijst met bestandstypen die zijn opgenomen in de openbare CDN voert u het volgende uit:</span><span class="sxs-lookup"><span data-stu-id="e7358-524">To add the _JSON_ file type to the default list of file types included in the public CDN, execute:</span></span>

```cli
spo cdn policy set --type Public --policy IncludeFileExtensions --value "CSS,EOT,GIF,ICO,JPEG,JPG,JS,MAP,PNG,SVG,TTF,WOFF,JSON"
```

### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn"></a><span data-ttu-id="e7358-525">De lijst met siteclassificaties wijzigen die u wilt uitsluiten van de Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="e7358-525">Change the list of site classifications you want to exclude from the Office 365 CDN</span></span>

<span data-ttu-id="e7358-526">Gebruik de [opdracht SPO CDN-beleidset](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) om siteclassificaties uit te sluiten die u niet beschikbaar wilt maken in de CDN.</span><span class="sxs-lookup"><span data-stu-id="e7358-526">Use the [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) command to exclude site classifications that you do not want to make available over the CDN.</span></span> <span data-ttu-id="e7358-527">Standaard worden geen siteclassificaties uitgesloten.</span><span class="sxs-lookup"><span data-stu-id="e7358-527">By default, no site classifications are excluded.</span></span>

> [!NOTE]
> <span data-ttu-id="e7358-528">Wanneer u de lijst met uitgesloten siteclassificaties verandert, overschrijft u de lijst die momenteel is gedefinieerd.</span><span class="sxs-lookup"><span data-stu-id="e7358-528">When changing the list of excluded site classifications, you overwrite the currently defined list.</span></span> <span data-ttu-id="e7358-529">Als u extra classificaties wilt uitsluiten, gebruikt u eerst de [opdracht SPO CDN-beleidlijst](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-list/) om te kijken welke classificaties momenteel zijn geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="e7358-529">If you want to exclude additional classifications, first use the [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-list/) command to find out which classifications are currently configured.</span></span>

<span data-ttu-id="e7358-530">Als u sites die als _HBI zijn geclassificeerd,_ wilt uitsluiten van de openbare CDN, voert u</span><span class="sxs-lookup"><span data-stu-id="e7358-530">To exclude sites classified as _HBI_ from the public CDN, execute</span></span>

```cli
spo cdn policy set --type Public --policy ExcludeRestrictedSiteClassifications --value "HBI"
```

### <a name="disable-the-office-365-cdn"></a><span data-ttu-id="e7358-531">De Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="e7358-531">Disable the Office 365 CDN</span></span>

<span data-ttu-id="e7358-532">Als u de Office 365 CDN de opdracht `spo cdn set` wilt uitschakelen, bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="e7358-532">To disable the Office 365 CDN use the `spo cdn set` command, for example:</span></span>

```cli
spo cdn set --type Public --enabled false
```

</details>

## <a name="using-your-cdn-assets"></a><span data-ttu-id="e7358-533">Uw CDN gebruiken</span><span class="sxs-lookup"><span data-stu-id="e7358-533">Using your CDN assets</span></span>

<span data-ttu-id="e7358-534">Nu u de oorspronkelijke CDN en geconfigureerde origins en beleidsregels hebt ingeschakeld, kunt u uw CDN gebruiken.</span><span class="sxs-lookup"><span data-stu-id="e7358-534">Now that you have enabled the CDN and configured origins and policies, you can begin using your CDN assets.</span></span>

<span data-ttu-id="e7358-535">In deze sectie krijgt u inzicht in het gebruik van CDN-URL's in uw SharePoint-pagina's en inhoud, zodat SharePoint aanvragen voor activa in zowel openbare als privé-origins omleiden naar de CDN.</span><span class="sxs-lookup"><span data-stu-id="e7358-535">This section will help you understand how to use CDN URLs in your SharePoint pages and content so that SharePoint redirects requests for assets in both public and private origins to the CDN.</span></span>

+ [<span data-ttu-id="e7358-536">Koppelingen naar CDN bijwerken</span><span class="sxs-lookup"><span data-stu-id="e7358-536">Updating links to CDN assets</span></span>](use-microsoft-365-cdn-with-spo.md#updating-links-to-cdn-assets)
+ [<span data-ttu-id="e7358-537">Activa gebruiken in openbare origins</span><span class="sxs-lookup"><span data-stu-id="e7358-537">Using assets in public origins</span></span>](use-microsoft-365-cdn-with-spo.md#using-assets-in-public-origins)
+ [<span data-ttu-id="e7358-538">Activa in privé-origins gebruiken</span><span class="sxs-lookup"><span data-stu-id="e7358-538">Using assets in private origins</span></span>](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)

<span data-ttu-id="e7358-539">Zie het onderwerp Host [your client-side web part from Office 365 CDN (Hello World part 4)](/sharepoint/dev/spfx/web-parts/get-started/hosting-webpart-from-office-365-cdn)voor informatie over het gebruik van de CDN voor het hosten van webonderdelen aan de clientzijde.</span><span class="sxs-lookup"><span data-stu-id="e7358-539">For information on how to use the CDN for hosting client-side web parts, see the topic [Host your client-side web part from Office 365 CDN (Hello World part 4)](/sharepoint/dev/spfx/web-parts/get-started/hosting-webpart-from-office-365-cdn).</span></span>

> [!NOTE]
> <span data-ttu-id="e7358-540">Als u de map _ClientSideAssets_ toevoegt aan de lijst met CDN-origins, kunnen CDN aangepaste webonderdelen niet worden weergegeven. </span><span class="sxs-lookup"><span data-stu-id="e7358-540">If you add the _ClientSideAssets_ folder to the **private** CDN origins list, CDN-hosted custom web parts will fail to render.</span></span> <span data-ttu-id="e7358-541">Bestanden die door SPFX-webonderdelen worden gebruikt, kunnen alleen gebruikmaken van de openbare CDN en de map ClientSideAssets is een standaardinstelling voor openbare CDN.</span><span class="sxs-lookup"><span data-stu-id="e7358-541">Files used by SPFX web parts can only utilize the public CDN and the ClientSideAssets folder is a default origin for public CDN.</span></span> 

### <a name="updating-links-to-cdn-assets"></a><span data-ttu-id="e7358-542">Koppelingen naar CDN bijwerken</span><span class="sxs-lookup"><span data-stu-id="e7358-542">Updating links to CDN assets</span></span>

<span data-ttu-id="e7358-543">Als u activa wilt gebruiken die u aan een origin hebt toegevoegd, kunt u koppelingen naar het oorspronkelijke bestand bijwerken met het pad naar het bestand in de origin.</span><span class="sxs-lookup"><span data-stu-id="e7358-543">To use assets that you have added to an origin, you simply update links to the original file with the path to the file in the origin.</span></span>

+ <span data-ttu-id="e7358-544">Bewerk de pagina of inhoud die koppelingen bevat naar activa die u aan een origin hebt toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="e7358-544">Edit the page or content that contains links to assets you have added to an origin.</span></span> <span data-ttu-id="e7358-545">U kunt ook een van de verschillende methoden gebruiken om wereldwijd koppelingen in een enter-site of siteverzameling te zoeken en te vervangen als u de koppeling naar een bepaald activum overal wilt bijwerken waar deze wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="e7358-545">You can also use one of several methods to globally search and replace links across an enter site or site collection if you want to update the link to a given asset everywhere it appears.</span></span>
+ <span data-ttu-id="e7358-546">Vervang voor elke koppeling naar een activum in een origin het pad door het pad naar het bestand in de CDN origin.</span><span class="sxs-lookup"><span data-stu-id="e7358-546">For each link to an asset in an origin, replace the path with the path to the file in the CDN origin.</span></span> <span data-ttu-id="e7358-547">U kunt relatieve paden gebruiken.</span><span class="sxs-lookup"><span data-stu-id="e7358-547">You can use relative paths.</span></span>
+ <span data-ttu-id="e7358-548">Sla de pagina of inhoud op.</span><span class="sxs-lookup"><span data-stu-id="e7358-548">Save the page or content.</span></span>

<span data-ttu-id="e7358-549">Denk bijvoorbeeld aan de afbeelding _/site/SiteAssets/images/image.png_, die u hebt gekopieerd naar de map _documentbibliotheek /site/CDN_origins/public/_.</span><span class="sxs-lookup"><span data-stu-id="e7358-549">For example, consider the image _/site/SiteAssets/images/image.png_, which you have copied to the document library folder _/site/CDN_origins/public/_.</span></span> <span data-ttu-id="e7358-550">Als u de CDN wilt gebruiken, vervangt u het oorspronkelijke pad naar de locatie van het afbeeldingsbestand door het pad naar de origin om de nieuwe URL _/site/CDN_origins/public/image.png._</span><span class="sxs-lookup"><span data-stu-id="e7358-550">To use the CDN asset, replace the original path to the image file location with the path to the origin to make the new URL _/site/CDN_origins/public/image.png_.</span></span>

<span data-ttu-id="e7358-551">Als u de volledige URL naar het activum wilt gebruiken in plaats van een relatief pad, maakt u de koppeling als het volgende:</span><span class="sxs-lookup"><span data-stu-id="e7358-551">If you want to use the full URL to the asset instead of a relative path, construct the link like so:</span></span>

`https://<TenantHostName>.sharepoint.com/sites/site/CDN_origins/public/image.png`

> [!NOTE]
> <span data-ttu-id="e7358-552">In het algemeen moet u URL's niet rechtstreeks hardcoderen naar activa in de CDN.</span><span class="sxs-lookup"><span data-stu-id="e7358-552">In general, you should not hardcode URLs directly to assets in the CDN.</span></span> <span data-ttu-id="e7358-553">U kunt echter indien nodig handmatig URL's maken voor activa in openbare origins.</span><span class="sxs-lookup"><span data-stu-id="e7358-553">However, you can manually construct URLs for assets in public origins if needed.</span></span> <span data-ttu-id="e7358-554">Zie [Hardcoding CDN URL's voor openbare activa voor meer informatie.](use-microsoft-365-cdn-with-spo.md#constructing-cdn-urls-for-public-assets)</span><span class="sxs-lookup"><span data-stu-id="e7358-554">For more information, see [Hardcoding CDN URLs for public assets](use-microsoft-365-cdn-with-spo.md#constructing-cdn-urls-for-public-assets).</span></span>

<span data-ttu-id="e7358-555">Zie Hoe kan ik bevestigen dat activa worden beheerd door de CDN [Office 365 CDN?](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting)in Problemen met de CDN voor meer informatie over het controleren of activa worden gebruikt vanuit de [CDN.](use-microsoft-365-cdn-with-spo.md#CDNConfirm)</span><span class="sxs-lookup"><span data-stu-id="e7358-555">To learn about how to verify that assets are being served from the CDN, see [How do I confirm that assets are being served by the CDN?](use-microsoft-365-cdn-with-spo.md#CDNConfirm) in [Troubleshooting the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting).</span></span>

### <a name="using-assets-in-public-origins"></a><span data-ttu-id="e7358-556">Activa gebruiken in openbare origins</span><span class="sxs-lookup"><span data-stu-id="e7358-556">Using assets in public origins</span></span>

<span data-ttu-id="e7358-557">Met **de** functie Publiceren in SharePoint Online worden URL's van activa die zijn opgeslagen in openbare origins automatisch herschreven in hun CDN-equivalenten, zodat activa worden gebruikt vanuit de CDN-service in plaats van SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e7358-557">The **Publishing feature** in SharePoint Online automatically rewrites URLs of assets stored in public origins to their CDN equivalents so that assets are served from the CDN service instead of SharePoint.</span></span>

<span data-ttu-id="e7358-558">Als uw origin zich op een site met de functie Publiceren heeft ingeschakeld en de activa die u wilt overschrijven naar de CDN zich in een van de volgende categorieën plaatsen, worden INL's in SharePoint automatisch herschreven voor activa in de origin, mits het activum niet is uitgesloten door een CDN-beleid.</span><span class="sxs-lookup"><span data-stu-id="e7358-558">If your origin is in a site with the Publishing feature enabled, and the assets you want to offload to the CDN are in one of the following categories, SharePoint will automatically rewrite URLs for assets in the origin, provided that the asset has not been excluded by a CDN policy.</span></span>

<span data-ttu-id="e7358-559">Hieronder volgt een overzicht van de koppelingen die automatisch worden herschreven door de SharePoint Publicatiefunctie:</span><span class="sxs-lookup"><span data-stu-id="e7358-559">The following is an overview of which links are automatically rewritten by the SharePoint Publishing feature:</span></span>

+ <span data-ttu-id="e7358-560">IMG/LINK/CSS-URL's in html-antwoorden voor klassieke publicatiepagina</span><span class="sxs-lookup"><span data-stu-id="e7358-560">IMG/LINK/CSS URLs in classic publishing page HTML responses</span></span>
  + <span data-ttu-id="e7358-561">Dit omvat afbeeldingen die door auteurs zijn toegevoegd aan de HTML-inhoud van een pagina</span><span class="sxs-lookup"><span data-stu-id="e7358-561">This includes images added by authors within the HTML content of a page</span></span>
+ <span data-ttu-id="e7358-562">AfbeeldingsbibliotheekDiavoorstelling webonderdeel AFBEELDING-URL's</span><span class="sxs-lookup"><span data-stu-id="e7358-562">Picture Library SlideShow webpart image URLs</span></span>
+ <span data-ttu-id="e7358-563">Afbeeldingsvelden in SPList REST API (RenderListDataAsStream) resultaten</span><span class="sxs-lookup"><span data-stu-id="e7358-563">Image fields in SPList REST API (RenderListDataAsStream) results</span></span>
  + <span data-ttu-id="e7358-564">De nieuwe eigenschap _ImageFieldsToTryRewriteToCdnUrls_ gebruiken om een door komma's gescheiden lijst met velden op te geven</span><span class="sxs-lookup"><span data-stu-id="e7358-564">Use the new property _ImageFieldsToTryRewriteToCdnUrls_ to provide a comma separated list of fields</span></span>
  + <span data-ttu-id="e7358-565">Ondersteunt hyperlinkvelden en PublishingImage-velden</span><span class="sxs-lookup"><span data-stu-id="e7358-565">Supports hyperlink fields and PublishingImage fields</span></span>
+ <span data-ttu-id="e7358-566">SharePoint afbeeldingsweergaven</span><span class="sxs-lookup"><span data-stu-id="e7358-566">SharePoint image renditions</span></span>

<span data-ttu-id="e7358-567">In het volgende diagram wordt de werkstroom weergegeven wanneer SharePoint een aanvraag ontvangt voor een pagina met activa van een openbare origin.</span><span class="sxs-lookup"><span data-stu-id="e7358-567">The following diagram illustrates the workflow when SharePoint receives a request for a page containing assets from a public origin.</span></span>

<span data-ttu-id="e7358-568">![Werkstroomdiagram: ophalen Office 365 CDN activa van een openbare origin](../media/O365-CDN/o365-cdn-public-steps-transparent.svg "Werkstroom: het ophalen Office 365 CDN activa van een openbare origin")</span><span class="sxs-lookup"><span data-stu-id="e7358-568">![Workflow diagram: Retrieving Office 365 CDN assets from a public origin](../media/O365-CDN/o365-cdn-public-steps-transparent.svg "Workflow: Retrieving Office 365 CDN assets from a public origin")</span></span>

> [!TIP]
> <span data-ttu-id="e7358-569">Als u automatisch herschrijven voor specifieke URL's op een pagina wilt uitschakelen, kunt u de pagina bekijken en de parameter queryreeks **toevoegen? NoAutoReWrites=true** aan het einde van elke koppeling die u wilt uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="e7358-569">If you want to disable auto-rewriting for specific URLs on a page, you can check out the page and add the query string parameter **?NoAutoReWrites=true** to the end of each link you want to disable.</span></span>

#### <a name="constructing-cdn-urls-for-public-assets"></a><span data-ttu-id="e7358-570">Url'CDN maken voor openbare activa</span><span class="sxs-lookup"><span data-stu-id="e7358-570">Constructing CDN URLs for public assets</span></span>

<span data-ttu-id="e7358-571">Als  de publicatiefunctie niet is ingeschakeld voor een openbare origin of als het activum niet een van de koppelingstypen is die worden ondersteund door de functie voor automatisch herschrijven van de CDN-service, kunt u HANDMATIG URL's maken naar de CDN-locatie van de activa en deze URL's in uw inhoud gebruiken.</span><span class="sxs-lookup"><span data-stu-id="e7358-571">If the _Publishing_ feature is not enabled for a public origin, or the asset is not one of the link types supported by the auto-rewrite feature of the CDN service, you can manually construct URLs to the CDN location of the assets and use these URLs in your content.</span></span>

> [!NOTE]
> <span data-ttu-id="e7358-572">U kunt url's niet hardcoderen of CDN maken voor activa in een persoonlijke origin, omdat het vereiste toegangs token dat de laatste sectie van de URL vormt, wordt gegenereerd op het moment dat de resource wordt aangevraagd.</span><span class="sxs-lookup"><span data-stu-id="e7358-572">You cannot hardcode or construct CDN URLs to assets in a private origin because the required access token that forms the last section of the URL is generated at the time the resource is requested.</span></span> <span data-ttu-id="e7358-573">U kunt de URL voor openbare CDN maken en de URL mag niet moeilijk worden gecodeerd omdat deze onderhevig is aan wijziging.</span><span class="sxs-lookup"><span data-stu-id="e7358-573">You can construct the URL for Public CDN and the URL should not be hard coded as it is subject to change.</span></span>

<span data-ttu-id="e7358-574">Voor openbare CDN ziet de URL-indeling er als volgt uit:</span><span class="sxs-lookup"><span data-stu-id="e7358-574">For public CDN assets, the URL format will look like the following:</span></span>

```http
https://publiccdn.sharepointonline.com/<TenantHostName>/sites/site/library/asset.png
```

<span data-ttu-id="e7358-575">Vervang **TenantHostName** door uw tenantnaam.</span><span class="sxs-lookup"><span data-stu-id="e7358-575">Replace **TenantHostName** with your tenant name.</span></span> <span data-ttu-id="e7358-576">Voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="e7358-576">Example:</span></span>

```http
https://publiccdn.sharepointonline.com/contoso.sharepoint.com/sites/site/library/asset.png
```

> [!NOTE]
> <span data-ttu-id="e7358-577">De paginacontext-eigenschap moet worden gebruikt om het voorvoegsel te maken in plaats van hardcoderen " https://publiccdn.sharepointonline.com ".</span><span class="sxs-lookup"><span data-stu-id="e7358-577">The page context property should be used to construct the prefix instead of hard coding "https://publiccdn.sharepointonline.com".</span></span> <span data-ttu-id="e7358-578">De URL kan worden gewijzigd en mag niet hard worden gecodeerd.</span><span class="sxs-lookup"><span data-stu-id="e7358-578">The URL is subject to change and should not be hard coded.</span></span> <span data-ttu-id="e7358-579">Als u weergavesjablonen gebruikt met Classic SharePoint Online, kunt u de eigenschap 'window._spPageContextInfo.publicCdnBaseUrl' gebruiken in de weergavesjabloon voor het voorvoegsel van de URL.</span><span class="sxs-lookup"><span data-stu-id="e7358-579">If you are using display templates with Classic SharePoint Online then you can use the property "window._spPageContextInfo.publicCdnBaseUrl" in your display template for the prefix of the URL.</span></span> <span data-ttu-id="e7358-580">Als u SPFx voor moderne en klassieke SharePoint kunt u de eigenschap 'this.context.pageContext.legacyPageContext.publicCdnBaseUrl' gebruiken.</span><span class="sxs-lookup"><span data-stu-id="e7358-580">If you are SPFx web parts for modern and classic SharePoint the you can utilize the property "this.context.pageContext.legacyPageContext.publicCdnBaseUrl".</span></span> <span data-ttu-id="e7358-581">Dit geeft het voorvoegsel op, zodat als het wordt gewijzigd, de implementatie wordt bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="e7358-581">This will provide the prefix so that if it is changed then your implementation will update with it.</span></span> <span data-ttu-id="e7358-582">Als voorbeeld voor SPFx kan de URL worden gemaakt met de eigenschap 'this.context.pageContext.legacyPageContext.publicCdnBaseUrl' + "/" + "host" + "/" + "relativeURL for the item".</span><span class="sxs-lookup"><span data-stu-id="e7358-582">As an example for SPFx, the URL can be constructed using the property "this.context.pageContext.legacyPageContext.publicCdnBaseUrl" + "/" + "host" + "/" + "relativeURL for the item".</span></span> <span data-ttu-id="e7358-583">Zie [Gebruik CDN in clientcode](https://youtu.be/IH1RbQlbhIA) die deel uitmaakt van de [prestatiereeks seizoen 1](https://aka.ms/sppnp-perfvideos)</span><span class="sxs-lookup"><span data-stu-id="e7358-583">Please see [Using CDN in Client-side code](https://youtu.be/IH1RbQlbhIA) which is part of the [season 1 performance series](https://aka.ms/sppnp-perfvideos)</span></span>


### <a name="using-assets-in-private-origins"></a><span data-ttu-id="e7358-584">Activa in privé-origins gebruiken</span><span class="sxs-lookup"><span data-stu-id="e7358-584">Using assets in private origins</span></span>

<span data-ttu-id="e7358-585">Er is geen extra configuratie vereist voor het gebruik van activa in privé-origins.</span><span class="sxs-lookup"><span data-stu-id="e7358-585">No additional configuration is required to use assets in private origins.</span></span> <span data-ttu-id="e7358-586">SharePoint Online herschrijft automatisch URL's voor activa in privé-origins, zodat aanvragen voor deze activa altijd vanaf de CDN.</span><span class="sxs-lookup"><span data-stu-id="e7358-586">SharePoint Online automatically rewrites URLs for assets in private origins so requests for those assets will always be served from the CDN.</span></span> <span data-ttu-id="e7358-587">U kunt URL's niet handmatig maken voor CDN-assets in privé-origins, omdat deze URL's tokens bevatten die automatisch moeten worden gegenereerd door SharePoint Online op het moment dat het activum wordt aangevraagd.</span><span class="sxs-lookup"><span data-stu-id="e7358-587">You cannot manually build URLs to CDN assets in private origins because these URLs contain tokens that must be auto-generated by SharePoint Online at the time the asset is requested.</span></span>

<span data-ttu-id="e7358-588">Toegang tot activa in privé-origins wordt beveiligd door dynamisch gegenereerde tokens op basis van gebruikersmachtigingen voor de origin, met de waarschuwingen die in de volgende secties worden beschreven.</span><span class="sxs-lookup"><span data-stu-id="e7358-588">Access to assets in private origins is protected by dynamically generated tokens based on user permissions to the origin, with the caveats described in the following sections.</span></span> <span data-ttu-id="e7358-589">Gebruikers moeten ten minste **leestoegang** hebben tot de origins voor de CDN om inhoud weer te geven.</span><span class="sxs-lookup"><span data-stu-id="e7358-589">Users must have at least **read** access to the origins for the CDN to render content.</span></span>

<span data-ttu-id="e7358-590">In het volgende diagram wordt de werkstroom weergegeven wanneer SharePoint een aanvraag ontvangt voor een pagina met activa van een persoonlijke origin.</span><span class="sxs-lookup"><span data-stu-id="e7358-590">The following diagram illustrates the workflow when SharePoint receives a request for a page containing assets from a private origin.</span></span>

<span data-ttu-id="e7358-591">![Werkstroomdiagram: ophalen Office 365 CDN activa van een privé-origin](../media/O365-CDN/o365-cdn-private-steps-transparent.svg "Werkstroom: ophalen van Office 365 CDN activa van een privé-origin")</span><span class="sxs-lookup"><span data-stu-id="e7358-591">![Workflow diagram: Retrieving Office 365 CDN assets from a private origin](../media/O365-CDN/o365-cdn-private-steps-transparent.svg "Workflow: Retrieving Office 365 CDN assets from a private origin")</span></span>

#### <a name="token-based-authorization-in-private-origins"></a><span data-ttu-id="e7358-592">Autorisatie op basis van token in privé-origins</span><span class="sxs-lookup"><span data-stu-id="e7358-592">Token-based authorization in private origins</span></span>

<span data-ttu-id="e7358-593">Toegang tot activa in privé-origins in de Office 365 CDN wordt verleend door tokens die worden gegenereerd door SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="e7358-593">Access to assets in private origins in the Office 365 CDN is granted by tokens generated by SharePoint Online.</span></span> <span data-ttu-id="e7358-594">Gebruikers die al toegang hebben tot de map of bibliotheek die door de origin is aangewezen, krijgen automatisch tokens die de gebruiker toegang geven tot het bestand op basis van hun machtigingsniveau.</span><span class="sxs-lookup"><span data-stu-id="e7358-594">Users who already have permission to access to the folder or library designated by the origin are automatically granted tokens that permit the user to access the file based on their permission level.</span></span> <span data-ttu-id="e7358-595">Deze toegangstokens zijn geldig voor 30 tot 90 minuten nadat ze zijn gegenereerd om te voorkomen dat token opnieuw wordt afgespeeld.</span><span class="sxs-lookup"><span data-stu-id="e7358-595">These access tokens are valid for 30 to 90 minutes after they are generated to help prevent token replay attacks.</span></span>

<span data-ttu-id="e7358-596">Wanneer het toegangs token is gegenereerd, retourneert SharePoint Online een aangepaste URI naar de client met twee autorisatieparameters _eten_ (edge authorization token) en _haver_ (origin authorization token).</span><span class="sxs-lookup"><span data-stu-id="e7358-596">Once the access token is generated, SharePoint Online returns a custom URI to the client containing two authorization parameters _eat_ (edge authorization token) and _oat_ (origin authorization token).</span></span> <span data-ttu-id="e7358-597">De structuur van elk token is<'verlooptijd in tijdnotatie _epoch'>__<'secure signature'>._</span><span class="sxs-lookup"><span data-stu-id="e7358-597">The structure of each token is _<'expiration time in Epoch time format'>__<'secure signature'>_.</span></span> <span data-ttu-id="e7358-598">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="e7358-598">For example:</span></span>

```http
https://privatecdn.sharepointonline.com/contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg?eat=1486154359_cc59042c5c55c90b26a2775323c7c8112718431228fe84d568a3795a63912840&oat=1486154359_7d73c2e3ba4b7b1f97242332900616db0d4ffb04312
```

> [!NOTE]
> <span data-ttu-id="e7358-599">Iedereen die in het bezit is van het token, heeft toegang tot de resource in de CDN.</span><span class="sxs-lookup"><span data-stu-id="e7358-599">Anyone in possession of the token can access the resource in the CDN.</span></span> <span data-ttu-id="e7358-600">URL's met deze toegangstokens worden echter alleen gedeeld via HTTPS, dus tenzij de URL expliciet wordt gedeeld door een eindgebruiker voordat het token verloopt, is het activum niet toegankelijk voor niet-geautoriseerde gebruikers.</span><span class="sxs-lookup"><span data-stu-id="e7358-600">However, URLs containing these access tokens are only shared over HTTPS, so unless the URL is explicitly shared by an end user before the token expires, the asset won't be accessible to unauthorized users.</span></span>

#### <a name="item-level-permissions-are-not-supported-for-assets-in-private-origins"></a><span data-ttu-id="e7358-601">Machtigingen op itemniveau worden niet ondersteund voor activa in privé-origins</span><span class="sxs-lookup"><span data-stu-id="e7358-601">Item-level permissions are not supported for assets in private origins</span></span>

<span data-ttu-id="e7358-602">Het is belangrijk om te weten dat SharePoint Online geen machtigingen op itemniveau ondersteunt voor activa in privé-origins.</span><span class="sxs-lookup"><span data-stu-id="e7358-602">It is important to note that SharePoint Online does not support item-level permissions for assets in private origins.</span></span> <span data-ttu-id="e7358-603">Voor een bestand dat zich bijvoorbeeld op bevindt, hebben gebruikers effectieve toegang tot het `https://contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg` bestand onder de volgende voorwaarden:</span><span class="sxs-lookup"><span data-stu-id="e7358-603">For example, for a file located at `https://contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg`, users have effective access to the file given the following conditions:</span></span>

|<span data-ttu-id="e7358-604">Gebruiker</span><span class="sxs-lookup"><span data-stu-id="e7358-604">User</span></span>  |<span data-ttu-id="e7358-605">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="e7358-605">Permissions</span></span>  |<span data-ttu-id="e7358-606">Effectieve toegang</span><span class="sxs-lookup"><span data-stu-id="e7358-606">Effective access</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="e7358-607">Gebruiker 1</span><span class="sxs-lookup"><span data-stu-id="e7358-607">User 1</span></span>     |<span data-ttu-id="e7358-608">Heeft toegang tot map1</span><span class="sxs-lookup"><span data-stu-id="e7358-608">Has access to folder1</span></span>         |<span data-ttu-id="e7358-609">Toegang tot image1.jpg de CDN</span><span class="sxs-lookup"><span data-stu-id="e7358-609">Can access image1.jpg from the CDN</span></span>         |
|<span data-ttu-id="e7358-610">Gebruiker 2</span><span class="sxs-lookup"><span data-stu-id="e7358-610">User 2</span></span>     |<span data-ttu-id="e7358-611">Heeft geen toegang tot map1</span><span class="sxs-lookup"><span data-stu-id="e7358-611">Does not have access to folder1</span></span>         |<span data-ttu-id="e7358-612">Geen toegang image1.jpg de CDN</span><span class="sxs-lookup"><span data-stu-id="e7358-612">Cannot access image1.jpg from the CDN</span></span>         |
|<span data-ttu-id="e7358-613">Gebruiker 3</span><span class="sxs-lookup"><span data-stu-id="e7358-613">User 3</span></span>     |<span data-ttu-id="e7358-614">Heeft geen toegang tot map1, maar wordt expliciete machtigingen verleend voor toegang tot image1.jpg in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="e7358-614">Does not have access to folder1, but is granted explicit permission to access image1.jpg in SharePoint Online</span></span>         |<span data-ttu-id="e7358-615">U kunt de activa image1.jpg rechtstreeks vanuit SharePoint Online openen, maar niet vanuit de CDN</span><span class="sxs-lookup"><span data-stu-id="e7358-615">Can access the asset image1.jpg directly from SharePoint Online, but not from the CDN</span></span>         |
|<span data-ttu-id="e7358-616">Gebruiker 4</span><span class="sxs-lookup"><span data-stu-id="e7358-616">User 4</span></span>     |<span data-ttu-id="e7358-617">Heeft toegang tot map1, maar is expliciet toegang geweigerd tot image1.jpg in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="e7358-617">Has access to folder1, but has been explicitly denied access to image1.jpg in SharePoint Online</span></span>         |<span data-ttu-id="e7358-618">Heeft geen toegang tot het activum vanuit SharePoint Online, maar heeft wel toegang tot het activum vanuit de CDN ondanks dat de toegang tot het bestand in SharePoint Online is geweigerd</span><span class="sxs-lookup"><span data-stu-id="e7358-618">Cannot access the asset from SharePoint Online, but can access the asset from the CDN despite being denied access to the file in SharePoint Online</span></span>         |

<span data-ttu-id="e7358-619"><a name="CDNTroubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="e7358-619"><a name="CDNTroubleshooting"> </a></span></span>
## <a name="troubleshooting-the-office-365-cdn"></a><span data-ttu-id="e7358-620">Problemen met de Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="e7358-620">Troubleshooting the Office 365 CDN</span></span>

<span data-ttu-id="e7358-621"><a name="CDNConfirm"> </a></span><span class="sxs-lookup"><span data-stu-id="e7358-621"><a name="CDNConfirm"> </a></span></span>
### <a name="how-do-i-confirm-that-assets-are-being-served-by-the-cdn"></a><span data-ttu-id="e7358-622">Hoe kan ik bevestigen dat activa worden gebruikt door de CDN?</span><span class="sxs-lookup"><span data-stu-id="e7358-622">How do I confirm that assets are being served by the CDN?</span></span>

<span data-ttu-id="e7358-623">Nadat u koppelingen naar CDN-assets aan een pagina hebt toegevoegd, kunt u bevestigen dat het activum wordt weergegeven vanaf de CDN door naar de pagina te bladeren, met de rechtermuisknop op de afbeelding te klikken nadat de afbeelding is weergegeven en de url van de afbeelding te controleren.</span><span class="sxs-lookup"><span data-stu-id="e7358-623">Once you have added links to CDN assets to a page, you can confirm that the asset is being served from the CDN by browsing to the page, right clicking on the image once it has rendered and reviewing the image URL.</span></span>

<span data-ttu-id="e7358-624">U kunt ook de hulpprogramma's voor ontwikkelaars van uw browser gebruiken om de URL voor elk activum op een pagina weer te geven of een hulpprogramma voor netwerk traceren van derden gebruiken.</span><span class="sxs-lookup"><span data-stu-id="e7358-624">You can also use your browser's developer tools to view the URL for each asset on a page, or use a third party network trace tool.</span></span>

> [!NOTE]
> <span data-ttu-id="e7358-625">Als u een netwerkhulpmiddel, zoals Fiddler, gebruikt om uw activa te testen buiten het weergeven van het activum vanaf een SharePoint-pagina, moet u handmatig de refererkop 'Referer:' toevoegen aan de GET-aanvraag waarbij de URL de hoofd-URL is van uw `https://yourdomain.sharepoint.com` SharePoint Online-tenant.</span><span class="sxs-lookup"><span data-stu-id="e7358-625">If you use a network tool such as Fiddler to test your assets outside of rendering the asset from a SharePoint page, you must manually add the referer header "Referer: `https://yourdomain.sharepoint.com`" to the GET request where the URL is the root URL of your SharePoint Online tenant.</span></span>

<span data-ttu-id="e7358-626">Het is niet mogelijk CDN URL's rechtstreeks in een webbrowser te testen, omdat u een referer moet hebben die afkomstig is van SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="e7358-626">You cannot test CDN URLs directly in a web browser because you must have a referer coming from SharePoint Online.</span></span> <span data-ttu-id="e7358-627">Als u echter de CDN-activa-URL toevoegt aan een SharePoint-pagina en vervolgens de pagina opent in een browser, ziet u de CDN-asset weergegeven op de pagina.</span><span class="sxs-lookup"><span data-stu-id="e7358-627">However, if you add the CDN asset URL to a SharePoint page and then open the page in a browser, you will see the CDN asset rendered on the page.</span></span>

<span data-ttu-id="e7358-628">Zie voor meer informatie over het gebruik van de hulpprogramma's voor ontwikkelaars in Microsoft Edge browser [Microsoft Edge Ontwikkelaarshulpmiddelen.](/microsoft-edge/devtools-guide)</span><span class="sxs-lookup"><span data-stu-id="e7358-628">For more information on using the developer tools in the Microsoft Edge browser, see [Microsoft Edge Developer Tools](/microsoft-edge/devtools-guide).</span></span>

<span data-ttu-id="e7358-629">Als u een korte video wilt bekijken die wordt gehost in het [YouTube-kanaal van SharePoint Developer Patterns and Practices,](https://aka.ms/sppnp-videos) waarin wordt gedemonstreert hoe u kunt controleren of uw CDN werkt, raadpleegt u [Uw CDN-gebruik](https://www.youtube.com/watch?v=ClCtBAtGjE8&list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA&index=5)verifiëren en een optimale netwerkverbinding garanderen.</span><span class="sxs-lookup"><span data-stu-id="e7358-629">To watch a short video hosted in the [SharePoint Developer Patterns and Practices YouTube channel](https://aka.ms/sppnp-videos) demonstrating how to verify that your CDN is working, please see [Verifying your CDN usage and ensuring optimal network connectivity](https://www.youtube.com/watch?v=ClCtBAtGjE8&list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA&index=5).</span></span>

### <a name="why-are-assets-from-a-new-origin-unavailable"></a><span data-ttu-id="e7358-630">Waarom zijn activa van een nieuwe origin niet beschikbaar?</span><span class="sxs-lookup"><span data-stu-id="e7358-630">Why are assets from a new origin unavailable?</span></span>
<span data-ttu-id="e7358-631">Activa in nieuwe origins zijn niet onmiddellijk beschikbaar voor gebruik, omdat het tijd kost om de registratie door te sturen via de CDN en om de assets te uploaden van de origin naar CDN storage.</span><span class="sxs-lookup"><span data-stu-id="e7358-631">Assets in new origins will not immediately be available for use, as it takes time for the registration to propagate through the CDN and for the assets to be uploaded from the origin to CDN storage.</span></span> <span data-ttu-id="e7358-632">De tijd die nodig is om activa beschikbaar te maken in de CDN is afhankelijk van het aantal assets en de bestandsgrootten.</span><span class="sxs-lookup"><span data-stu-id="e7358-632">The time required for assets to be available in the CDN depends on how many assets and the files sizes.</span></span>

### <a name="my-client-side-web-part-or-sharepoint-framework-solution-isnt-working"></a><span data-ttu-id="e7358-633">Mijn clientwebonderdeel of -SharePoint Framework werkt niet</span><span class="sxs-lookup"><span data-stu-id="e7358-633">My client-side web part or SharePoint Framework solution isn't working</span></span>

<span data-ttu-id="e7358-634">Wanneer u de Office 365 CDN voor openbare origins inschakelen, worden CDN standaard origins automatisch gemaakt:</span><span class="sxs-lookup"><span data-stu-id="e7358-634">When you enable the Office 365 CDN for public origins, the CDN service automatically creates these default origins:</span></span>

+ <span data-ttu-id="e7358-635">\*/MASTERPAGE</span><span class="sxs-lookup"><span data-stu-id="e7358-635">\*/MASTERPAGE</span></span>
+ <span data-ttu-id="e7358-636">\*/STIJLBIBLIOTHEEK</span><span class="sxs-lookup"><span data-stu-id="e7358-636">\*/STYLE LIBRARY</span></span>
+ <span data-ttu-id="e7358-637">\*/CLIENTSIDEASSETS</span><span class="sxs-lookup"><span data-stu-id="e7358-637">\*/CLIENTSIDEASSETS</span></span>

<span data-ttu-id="e7358-638">Als de origin \*/clientsideassets ontbreekt, mislukt SharePoint Framework en worden er geen waarschuwings- of foutberichten gegenereerd.</span><span class="sxs-lookup"><span data-stu-id="e7358-638">If the \*/clientsideassets origin is missing, SharePoint Framework solutions will fail, and no warning or error messages are generated.</span></span> <span data-ttu-id="e7358-639">Deze origin ontbreekt mogelijk omdat de CDN is ingeschakeld met de parameter _-NoDefaultOrigins_ ingesteld op **$true** of omdat de origin handmatig is verwijderd.</span><span class="sxs-lookup"><span data-stu-id="e7358-639">This origin may be missing either because the CDN was enabled with the _-NoDefaultOrigins_ parameter set to **$true**, or because the origin was manually deleted.</span></span>

<span data-ttu-id="e7358-640">U kunt controleren welke origins aanwezig zijn met de volgende PowerShell-opdracht:</span><span class="sxs-lookup"><span data-stu-id="e7358-640">You can check to see which origins are present with the following PowerShell command:</span></span>

```powershell
Get-SPOTenantCdnOrigins -CdnType Public
```

<span data-ttu-id="e7358-641">U kunt ook contact op met Office 365 CLI:</span><span class="sxs-lookup"><span data-stu-id="e7358-641">Or you can check with the Office 365 CLI:</span></span>

```cli
spo cdn origin list
```

<span data-ttu-id="e7358-642">De origin in PowerShell toevoegen:</span><span class="sxs-lookup"><span data-stu-id="e7358-642">To add the origin in PowerShell:</span></span>

```powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */CLIENTSIDEASSETS
```

<span data-ttu-id="e7358-643">Als u de origin in de Office 365 CLI wilt toevoegen:</span><span class="sxs-lookup"><span data-stu-id="e7358-643">To add the origin in the Office 365 CLI:</span></span>

```cli
spo cdn origin add --origin */CLIENTSIDEASSETS
```

### <a name="what-powershell-modules-and-cli-shells-do-i-need-to-work-with-the-office-365-cdn"></a><span data-ttu-id="e7358-644">Welke PowerShell-modules en CLI-shells heb ik nodig om met de Office 365 CDN?</span><span class="sxs-lookup"><span data-stu-id="e7358-644">What PowerShell modules and CLI shells do I need to work with the Office 365 CDN?</span></span>

<span data-ttu-id="e7358-645">U kunt ervoor kiezen om met de Office 365 CDN te werken met de **SharePoint Online Management Shell** PowerShell-module of de Office 365 **CLI.**</span><span class="sxs-lookup"><span data-stu-id="e7358-645">You can choose to work with the Office 365 CDN using either the **SharePoint Online Management Shell** PowerShell module or the **Office 365 CLI**.</span></span>

+ [<span data-ttu-id="e7358-646">Aan de slag met SharePoint Online Management Shell</span><span class="sxs-lookup"><span data-stu-id="e7358-646">Getting started with SharePoint Online Management Shell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)
+ [<span data-ttu-id="e7358-647">De cli Office 365 installeren</span><span class="sxs-lookup"><span data-stu-id="e7358-647">Installing the Office 365 CLI</span></span>](https://pnp.github.io/office365-cli/user-guide/installing-cli/)

## <a name="see-also"></a><span data-ttu-id="e7358-648">Zie ook</span><span class="sxs-lookup"><span data-stu-id="e7358-648">See also</span></span>

[<span data-ttu-id="e7358-649">Netwerken voor contentlevering</span><span class="sxs-lookup"><span data-stu-id="e7358-649">Content Delivery Networks</span></span>](./content-delivery-networks.md)

[<span data-ttu-id="e7358-650">Network planning and performance tuning for Office 365</span><span class="sxs-lookup"><span data-stu-id="e7358-650">Network planning and performance tuning for Office 365</span></span>](./network-planning-and-performance.md)

[<span data-ttu-id="e7358-651">SharePoint Performance Series - Office 365 CDN videoreeks</span><span class="sxs-lookup"><span data-stu-id="e7358-651">SharePoint Performance Series - Office 365 CDN video series</span></span>](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)
