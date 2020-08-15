---
title: Office 365 Content Delivery Network (CDN) gebruiken met SharePoint Online
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
description: Meer informatie over het gebruik van het Office 365 Content Delivery Network (CDN) om de levering van uw SharePoint Online-assets te versnellen.
ms.openlocfilehash: 0ef7922f4e8881065f97a5fdeb4f21242c2b6467
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688971"
---
# <a name="use-the-office-365-content-delivery-network-cdn-with-sharepoint-online"></a><span data-ttu-id="148ad-103">Het Office 365 Content Delivery Network (CDN) gebruiken met SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="148ad-103">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>

<span data-ttu-id="148ad-104">U kunt het ingebouwde Office 365 Content Delivery Network (CDN) gebruiken voor het hosten van statische activa voor betere prestaties voor de SharePoint Online-pagina's.</span><span class="sxs-lookup"><span data-stu-id="148ad-104">You can use the built-in Office 365 Content Delivery Network (CDN) to host static assets to provide better performance for your SharePoint Online pages.</span></span> <span data-ttu-id="148ad-105">Het CDN van Office 365 verbetert de prestaties omdat statische activa dichter bij de door u gevraagde browsers worden opgevolgd, zodat downloads sneller kunnen worden en de latentie minder kost.</span><span class="sxs-lookup"><span data-stu-id="148ad-105">The Office 365 CDN improves performance by caching static assets closer to the browsers requesting them, which helps to speed up downloads and reduce latency.</span></span> <span data-ttu-id="148ad-106">Daarnaast wordt in Office 365 CDN het [protocol http/2](https://en.wikipedia.org/wiki/HTTP/2) gebruikt voor verbeterde compressie en http-pipeline.</span><span class="sxs-lookup"><span data-stu-id="148ad-106">Also, the Office 365 CDN uses the [HTTP/2 protocol](https://en.wikipedia.org/wiki/HTTP/2) for improved compression and HTTP pipelining.</span></span> <span data-ttu-id="148ad-107">De Office 365 CDN-service maakt deel uit van uw SharePoint Online-abonnement.</span><span class="sxs-lookup"><span data-stu-id="148ad-107">The Office 365 CDN service is included as part of your SharePoint Online subscription.</span></span>

> [!NOTE]
> <span data-ttu-id="148ad-108">Het Office 365 CDN is alleen beschikbaar voor tenants in de **productie** -Cloud (wereldwijd).</span><span class="sxs-lookup"><span data-stu-id="148ad-108">The Office 365 CDN is only available to tenants in the **Production** (worldwide) cloud.</span></span> <span data-ttu-id="148ad-109">Tenants in de Verenigde Staten voor de overheid, China en Duitsland ondersteunen momenteel het Office 365 CDN.</span><span class="sxs-lookup"><span data-stu-id="148ad-109">Tenants in the US Government, China and Germany clouds do not currently support the Office 365 CDN.</span></span>

<span data-ttu-id="148ad-110">Het CDN van Office 365 is samengesteld uit meerdere Cdn's die u in staat stellen statische activa te hosten op meerdere locaties of _herkomst_en ze van wereldwijde hogesnelheids netwerken te bezorgen.</span><span class="sxs-lookup"><span data-stu-id="148ad-110">The Office 365 CDN is composed of multiple CDNs that allow you to host static assets in multiple locations, or _origins_, and serve them from global high-speed networks.</span></span> <span data-ttu-id="148ad-111">Afhankelijk van het type inhoud dat u in het Office 365 CDN wilt hosten, kunt u **openbare** oorsprong, **persoonlijke** Origins of beide toevoegen.</span><span class="sxs-lookup"><span data-stu-id="148ad-111">Depending on the kind of content you want to host in the Office 365 CDN, you can add **public** origins, **private** origins or both.</span></span> <span data-ttu-id="148ad-112">Zie [kiezen of u elke oorsprong openbaar of privé moet zijn](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate) voor meer informatie over het verschil tussen openbare en persoonlijke oorsprong.</span><span class="sxs-lookup"><span data-stu-id="148ad-112">See [Choose whether each origin should be public or private](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate) for more information on the difference between public and private origins.</span></span>

<span data-ttu-id="148ad-113">![Office 365 CDN-conceptueel diagram](../media/O365-CDN/o365-cdn-flow-transparent.svg "Office 365 CDN-conceptueel diagram")</span><span class="sxs-lookup"><span data-stu-id="148ad-113">![Office 365 CDN conceptual diagram](../media/O365-CDN/o365-cdn-flow-transparent.svg "Office 365 CDN conceptual diagram")</span></span>

<span data-ttu-id="148ad-114">Als u al bekend bent met de manier waarop Cdn's werken, hoeft u slechts enkele stappen uit te voeren om het Office 365 CDN voor uw Tenant in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="148ad-114">If you are already familiar with the way that CDNs work, you only need to complete a few steps to enable the Office 365 CDN for your tenant.</span></span> <span data-ttu-id="148ad-115">In dit onderwerp wordt uitgelegd hoe u dit kunt doen.</span><span class="sxs-lookup"><span data-stu-id="148ad-115">This topic describes how.</span></span> <span data-ttu-id="148ad-116">Lees verder voor informatie over hoe u aan de slag kunt gaan met het hosten van uw statische activa.</span><span class="sxs-lookup"><span data-stu-id="148ad-116">Read on for information about how to get started hosting your static assets.</span></span>

> [!TIP]
> <span data-ttu-id="148ad-117">Er zijn andere Microsoft-gehoste Cdn's die kunnen worden gebruikt met Office 365 voor gespecialiseerde gebruiksscenario's, maar worden niet in dit onderwerp besproken omdat ze buiten het bereik van het Office 365-CDN vallen.</span><span class="sxs-lookup"><span data-stu-id="148ad-117">There are other Microsoft-hosted CDNs that can be used with Office 365 for specialized usage scenarios, but are not discussed in this topic because they fall outside the scope of the Office 365 CDN.</span></span> <span data-ttu-id="148ad-118">Zie voor meer informatie [andere Microsoft-cdn's](content-delivery-networks.md#other-microsoft-cdns).</span><span class="sxs-lookup"><span data-stu-id="148ad-118">For more information, see [Other Microsoft CDNs](content-delivery-networks.md#other-microsoft-cdns).</span></span>

 <span data-ttu-id="148ad-119">**Ga terug naar [netwerk planning en prestaties optimaliseren voor Office 365](https://aka.ms/tune).**</span><span class="sxs-lookup"><span data-stu-id="148ad-119">**Head back to [Network planning and performance tuning for Office 365](https://aka.ms/tune).**</span></span>

## <a name="overview-of-working-with-the-office-365-cdn-in-sharepoint-online"></a><span data-ttu-id="148ad-120">Overzicht van het werken met het Office 365-CDN in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="148ad-120">Overview of working with the Office 365 CDN in SharePoint Online</span></span>

<span data-ttu-id="148ad-121">Als u het Office 365 CDN voor uw organisatie wilt instellen, volgt u deze basisstappen:</span><span class="sxs-lookup"><span data-stu-id="148ad-121">To set up the Office 365 CDN for your organization, you follow these basic steps:</span></span>

+ [<span data-ttu-id="148ad-122">Implementatie van Office 365 CDN voorbereiden</span><span class="sxs-lookup"><span data-stu-id="148ad-122">Plan for deployment of the Office 365 CDN</span></span>](use-microsoft-365-cdn-with-spo.md#plan-for-deployment-of-the-office-365-cdn)

  + <span data-ttu-id="148ad-123">[Bepaal welke statische activa u wilt hosten op de CDN](use-microsoft-365-cdn-with-spo.md#CDNAssets).</span><span class="sxs-lookup"><span data-stu-id="148ad-123">[Determine which static assets you want to host on the CDN](use-microsoft-365-cdn-with-spo.md#CDNAssets).</span></span>
  + <span data-ttu-id="148ad-124">[Bepalen waar u de assets wilt opslaan](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets).</span><span class="sxs-lookup"><span data-stu-id="148ad-124">[Determine where you want to store your assets](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets).</span></span> <span data-ttu-id="148ad-125">Deze locatie kan een SharePoint-site,-bibliotheek of-map worden en wordt een _oorsprong_genoemd.</span><span class="sxs-lookup"><span data-stu-id="148ad-125">This location can be a SharePoint site, library or folder and is called an _origin_.</span></span>
  + <span data-ttu-id="148ad-126">[Kies of u de oorsprong openbaar of privé wilt maken](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate).</span><span class="sxs-lookup"><span data-stu-id="148ad-126">[Choose whether each origin should be public or private](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate).</span></span> <span data-ttu-id="148ad-127">U kunt meerdere herkomst van zowel openbare als persoonlijke typen toevoegen.</span><span class="sxs-lookup"><span data-stu-id="148ad-127">You can add multiple origins of both public and private types.</span></span>

+ <span data-ttu-id="148ad-128">Het CDN instellen en configureren met behulp van PowerShell of de SharePoint Online CLI</span><span class="sxs-lookup"><span data-stu-id="148ad-128">Set up and configure the CDN, using either PowerShell or the SharePoint Online CLI</span></span>

  + [<span data-ttu-id="148ad-129">Het CDN instellen en configureren met behulp van de SharePoint Online Management Shell</span><span class="sxs-lookup"><span data-stu-id="148ad-129">Set up and configure the CDN by using the SharePoint Online Management Shell</span></span>](use-microsoft-365-cdn-with-spo.md#CDNSetupinPShell)
  + [<span data-ttu-id="148ad-130">Het CDN instellen en configureren met behulp van PnP PowerShell</span><span class="sxs-lookup"><span data-stu-id="148ad-130">Set up and configure the CDN by using PnP PowerShell</span></span>](use-microsoft-365-cdn-with-spo.md#CDNSetupinPnPPosh)
  + [<span data-ttu-id="148ad-131">Het CDN instellen en configureren met behulp van Office 365 CLI</span><span class="sxs-lookup"><span data-stu-id="148ad-131">Set up and configure the CDN by using the Office 365 CLI</span></span>](use-microsoft-365-cdn-with-spo.md#CDNSetupinCLI)

  <span data-ttu-id="148ad-132">Wanneer u deze stap uitvoert, hebt u de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="148ad-132">When you complete this step, you will have:</span></span>

  + <span data-ttu-id="148ad-133">De CDN voor uw organisatie is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="148ad-133">Enabled the CDN for your organization.</span></span>
  + <span data-ttu-id="148ad-134">U hebt uw oorsprong toegevoegd en identificeren elke Origin als openbaar of privé.</span><span class="sxs-lookup"><span data-stu-id="148ad-134">Added your origins, identifying each origin as public or private.</span></span>

<span data-ttu-id="148ad-135">Wanneer u klaar bent met de configuratie, kunt u [het Office 365-CDN in de](use-microsoft-365-cdn-with-spo.md#CDNManage) loop van de tijd beheren door het volgende te doen:</span><span class="sxs-lookup"><span data-stu-id="148ad-135">Once you're done with setup, you can [Manage the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNManage) over time by:</span></span>
  
+ <span data-ttu-id="148ad-136">Assets toevoegen, bijwerken en verwijderen</span><span class="sxs-lookup"><span data-stu-id="148ad-136">Adding, updating, and removing assets</span></span>
+ <span data-ttu-id="148ad-137">Oorsprong toevoegen en verwijderen</span><span class="sxs-lookup"><span data-stu-id="148ad-137">Adding and removing origins</span></span>
+ <span data-ttu-id="148ad-138">CDN-beleidsregels configureren</span><span class="sxs-lookup"><span data-stu-id="148ad-138">Configuring CDN policies</span></span>
+ <span data-ttu-id="148ad-139">Het CDN zo nodig uitschakelen</span><span class="sxs-lookup"><span data-stu-id="148ad-139">If necessary, disabling the CDN</span></span>

<span data-ttu-id="148ad-140">Zie tot slot [uw CDN-assets gebruiken](use-microsoft-365-cdn-with-spo.md#using-your-cdn-assets) voor meer informatie over het openen van uw CDN-assets via openbare en persoonlijke oorsprong.</span><span class="sxs-lookup"><span data-stu-id="148ad-140">Finally, see [Using your CDN assets](use-microsoft-365-cdn-with-spo.md#using-your-cdn-assets) to learn about accessing your CDN assets from both public and private origins.</span></span>

<span data-ttu-id="148ad-141">Zie [problemen oplossen met het Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting) voor informatie over het oplossen van veelvoorkomende problemen.</span><span class="sxs-lookup"><span data-stu-id="148ad-141">See [Troubleshooting the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting) for guidance on resolving common issues.</span></span>

## <a name="plan-for-deployment-of-the-office-365-cdn"></a><span data-ttu-id="148ad-142">Implementatie van Office 365 CDN voorbereiden</span><span class="sxs-lookup"><span data-stu-id="148ad-142">Plan for deployment of the Office 365 CDN</span></span>

<span data-ttu-id="148ad-143">Voordat u het Office 365 CDN voor uw Office 365-Tenant implementeert, moet u de volgende factoren overwegen als onderdeel van de plannings procedure.</span><span class="sxs-lookup"><span data-stu-id="148ad-143">Before you deploy the Office 365 CDN for your Office 365 tenant, you should consider the following factors as part of your planning process.</span></span>

  + [<span data-ttu-id="148ad-144">Bepalen welke statische activa u wilt hosten op het CDN</span><span class="sxs-lookup"><span data-stu-id="148ad-144">Determine which static assets you want to host on the CDN</span></span>](use-microsoft-365-cdn-with-spo.md#CDNAssets)
  + [<span data-ttu-id="148ad-145">Bepalen waar u de assets wilt opslaan</span><span class="sxs-lookup"><span data-stu-id="148ad-145">Determine where you want to store your assets</span></span>](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets)
  + [<span data-ttu-id="148ad-146">Kies of u de oorsprong openbaar of privé wilt maken.</span><span class="sxs-lookup"><span data-stu-id="148ad-146">Choose whether each origin should be public or private</span></span>](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)

<span data-ttu-id="148ad-147"><a name="CDNAssets"> </a></span><span class="sxs-lookup"><span data-stu-id="148ad-147"><a name="CDNAssets"> </a></span></span>
### <a name="determine-which-static-assets-you-want-to-host-on-the-cdn"></a><span data-ttu-id="148ad-148">Bepalen welke statische activa u wilt hosten op het CDN</span><span class="sxs-lookup"><span data-stu-id="148ad-148">Determine which static assets you want to host on the CDN</span></span>

<span data-ttu-id="148ad-149">In het algemeen is Cdn's het meest geschikt voor het hosten van _statische activa_, of activa die niet vaak veranderen.</span><span class="sxs-lookup"><span data-stu-id="148ad-149">In general, CDNs are most effective for hosting _static assets_, or assets that don't change very often.</span></span> <span data-ttu-id="148ad-150">Een goede vuistregel is om bestanden te identificeren die voldoen aan een of meer van de volgende voorwaarden:</span><span class="sxs-lookup"><span data-stu-id="148ad-150">A good rule of thumb is to identify files that meet some or all of these conditions:</span></span>

+ <span data-ttu-id="148ad-151">Statische bestanden die zijn ingesloten in een pagina (zoals scripts en afbeeldingen) die mogelijk een belangrijke invloed hebben op de laadtijden van pagina's</span><span class="sxs-lookup"><span data-stu-id="148ad-151">Static files embedded in a page (like scripts and images) that may have a significant incremental impact on page load times</span></span>
+ <span data-ttu-id="148ad-152">Grote bestanden, zoals uitvoerbare bestanden en installatiebestanden</span><span class="sxs-lookup"><span data-stu-id="148ad-152">Large files like executables and installation files</span></span>
+ <span data-ttu-id="148ad-153">Bronnen bibliotheken die de programmacode voor de client ondersteunen</span><span class="sxs-lookup"><span data-stu-id="148ad-153">Resource libraries that support client-side code</span></span>

<span data-ttu-id="148ad-154">Wanneer u een site toevoegt aan een CDN-oorsprong, kunnen de prestaties van sites in SharePoint Online op een andere manier worden weergegeven, bijvoorbeeld wanneer u deze hebt toegevoegd aan een CDN-oorsprong.</span><span class="sxs-lookup"><span data-stu-id="148ad-154">For example, small files that are repeatedly requested like site images and scripts can significantly improve site rendering performance and incrementally reduce the load on your SharePoint Online sites when you add them to a CDN origin.</span></span> <span data-ttu-id="148ad-155">Grotere bestanden, zoals uitvoerbare bestanden, kunnen worden gedownload van de CDN, met een positieve invloed op de prestaties en het verminderen van de belasting van de SharePoint Online-site, zelfs als ze niet zo vaak worden geopend.</span><span class="sxs-lookup"><span data-stu-id="148ad-155">Larger files such as installation executables can be downloaded from the CDN, delivering a positive performance impact and subsequent reduction of the load on your SharePoint Online site, even if they are not accessed as often.</span></span>

<span data-ttu-id="148ad-156">De prestaties zijn afhankelijk van een groot aantal factoren, waaronder de buurt van de client en het dichtstbijzijnde CDN-eindpunt, tijdelijke voorwaarden voor het lokale netwerk, enzovoort.</span><span class="sxs-lookup"><span data-stu-id="148ad-156">Performance improvement on a per-file basis is dependent on many factors, including the client's proximity to the nearest CDN endpoint, transient conditions on the local network, and so forth.</span></span> <span data-ttu-id="148ad-157">Veel statische bestanden zijn zeer klein en kunnen worden gedownload van Office 365 in minder dan een seconde.</span><span class="sxs-lookup"><span data-stu-id="148ad-157">Many static files are quite small, and can be downloaded from Office 365 in less than a second.</span></span> <span data-ttu-id="148ad-158">Een webpagina kan echter veel ingesloten bestanden bevatten met een cumulatieve downloadtijd van enkele seconden.</span><span class="sxs-lookup"><span data-stu-id="148ad-158">However, a web page may contain many embedded files with a cumulative download time of several seconds.</span></span> <span data-ttu-id="148ad-159">Bij deze bestanden van de CDN kan de totale laadtijd van de pagina aanzienlijk worden verkleind.</span><span class="sxs-lookup"><span data-stu-id="148ad-159">Serving these files from the CDN can significantly reduce the overall page load time.</span></span> <span data-ttu-id="148ad-160">Bekijk [welke prestatiewinst een CDN](content-delivery-networks.md#what-performance-gains-does-a-cdn-provide) biedt voor een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="148ad-160">See [What performance gains does a CDN provide?](content-delivery-networks.md#what-performance-gains-does-a-cdn-provide) for an example.</span></span>

<span data-ttu-id="148ad-161"><a name="CDNStoreAssets"> </a></span><span class="sxs-lookup"><span data-stu-id="148ad-161"><a name="CDNStoreAssets"> </a></span></span>
### <a name="determine-where-you-want-to-store-your-assets"></a><span data-ttu-id="148ad-162">Bepalen waar u de assets wilt opslaan</span><span class="sxs-lookup"><span data-stu-id="148ad-162">Determine where you want to store your assets</span></span>

<span data-ttu-id="148ad-163">De CDN haalt de assets op van de locatie die een _oorsprong_wordt genoemd.</span><span class="sxs-lookup"><span data-stu-id="148ad-163">The CDN fetches your assets from a location called an _origin_.</span></span> <span data-ttu-id="148ad-164">Een oorsprong kan een SharePoint-site, documentbibliotheek of map zijn die toegankelijk is voor een URL.</span><span class="sxs-lookup"><span data-stu-id="148ad-164">An origin can be a SharePoint site, document library or folder that is accessible by a URL.</span></span> <span data-ttu-id="148ad-165">U hebt een fantastische flexibiliteit wanneer u oorsprong opgeeft voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="148ad-165">You have great flexibility when you specify origins for your organization.</span></span> <span data-ttu-id="148ad-166">U kunt bijvoorbeeld meerdere Origins of één herkomst opgeven waar u al uw CDN-activa wilt plaatsen.</span><span class="sxs-lookup"><span data-stu-id="148ad-166">For example, you can specify multiple origins or a single origin where you want to put all your CDN assets.</span></span> <span data-ttu-id="148ad-167">U kunt ervoor kiezen om zowel openbare als persoonlijke oorsprong te hebben voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="148ad-167">You can choose to have both public or private origins for your organization.</span></span> <span data-ttu-id="148ad-168">De meeste organisaties kiezen om een combinatie van beide te implementeren.</span><span class="sxs-lookup"><span data-stu-id="148ad-168">Most organizations will choose to implement a combination of the two.</span></span>

<span data-ttu-id="148ad-169">U kunt een nieuwe container maken voor uw herkomst, zoals mappen of documentbibliotheken, en bestanden toevoegen die u beschikbaar wilt maken in het CDN.</span><span class="sxs-lookup"><span data-stu-id="148ad-169">You can create new container for your origins such as folders or document libraries, and add files you want to make available from the CDN.</span></span> <span data-ttu-id="148ad-170">Dit is een goede manier om te bepalen of u beschikt over een specifieke groep activa die u in het CDN wilt weergegeven, en dat u de set CDN-assets wilt beperken tot alleen de bestanden in de container.</span><span class="sxs-lookup"><span data-stu-id="148ad-170">This is a good approach if you have a specific set of assets you want to be available from the CDN, and want to restrict the set of CDN assets to only those files in the container.</span></span>

<span data-ttu-id="148ad-171">U kunt ook een bestaande siteverzameling, site, bibliotheek of map configureren als een oorsprong, zodat alle in aanmerking komende assets worden gemaakt in de container die beschikbaar is in het CDN.</span><span class="sxs-lookup"><span data-stu-id="148ad-171">You can also configure an existing site collection, site, library or folder as an origin, which will make all eligible assets in the container available from the CDN.</span></span> <span data-ttu-id="148ad-172">Voordat u een bestaande container als een oorsprong toevoegt, moet u ervoor zorgen dat u zich bewust bent van de inhoud en machtigingen van de container, zodat u niet per ongeluk middelen uitgeeft aan anonieme toegang of niet-geautoriseerde gebruikers.</span><span class="sxs-lookup"><span data-stu-id="148ad-172">Before you add an existing container as an origin, it's important to make sure you are aware of its contents and permissions so you do not inadvertently expose assets to anonymous access or unauthorized users.</span></span>

<span data-ttu-id="148ad-173">U kunt _CDN-beleidsregels_ definiëren als u de inhoud van uw oorsprong wilt uitsluiten van het CDN.</span><span class="sxs-lookup"><span data-stu-id="148ad-173">You can define _CDN policies_ to exclude content in your origins from the CDN.</span></span> <span data-ttu-id="148ad-174">CDN-beleidsregels uitsluiten activa in openbare of persoonlijke oorsprong op basis van kenmerken zoals _bestandstype_ en _siteclassificatie_, en worden toegepast op alle oorsprong van de CdnType (privé of openbaar) die u in het beleid opgeeft.</span><span class="sxs-lookup"><span data-stu-id="148ad-174">CDN policies exclude assets in public or private origins by attributes such as _file type_ and _site classification_, and are applied to all origins of the CdnType (private or public) you specify in the policy.</span></span> <span data-ttu-id="148ad-175">Als u bijvoorbeeld een persoonlijke oorsprong opneemt van een site die meerdere subsites bevat, kunt u een beleid definiëren om websites uit te sluiten die als **vertrouwelijk** zijn gemarkeerd, zodat de inhoud van sites met deze classificatie niet wordt verzonden vanuit de CDN.</span><span class="sxs-lookup"><span data-stu-id="148ad-175">For example, if you add a private origin consisting of a site that contains multiple subsites, you can define a policy to exclude sites marked as **Confidential** so content from sites with that classification applied will not be served from the CDN.</span></span> <span data-ttu-id="148ad-176">Het beleid is van toepassing op inhoud van _alle_ persoonlijke oorsprong die u hebt toegevoegd aan het CDN.</span><span class="sxs-lookup"><span data-stu-id="148ad-176">The policy will apply to content from _all_ private origins you have added to the CDN.</span></span>
  
<span data-ttu-id="148ad-177">Houd er rekening mee dat u het volgende moet doen, hoe hoger de invloed van de CDN-service op het verwerken van aanvragen.</span><span class="sxs-lookup"><span data-stu-id="148ad-177">Keep in mind that the greater the number of origins, the greater the impact on the time it takes the CDN service to process requests.</span></span> <span data-ttu-id="148ad-178">We raden u aan het aantal oorsprong zo veel mogelijk te beperken.</span><span class="sxs-lookup"><span data-stu-id="148ad-178">We recommend that you limit the number of origins as much as possible.</span></span>
  
<span data-ttu-id="148ad-179"><a name="CDNOriginChoosePublicPrivate"> </a></span><span class="sxs-lookup"><span data-stu-id="148ad-179"><a name="CDNOriginChoosePublicPrivate"> </a></span></span>
### <a name="choose-whether-each-origin-should-be-public-or-private"></a><span data-ttu-id="148ad-180">Kies of u de oorsprong openbaar of privé wilt maken.</span><span class="sxs-lookup"><span data-stu-id="148ad-180">Choose whether each origin should be public or private</span></span>

<span data-ttu-id="148ad-181">Wanneer u een oorsprong identificeert, geeft u op of deze _openbaar_ of _privé_moet worden gemaakt.</span><span class="sxs-lookup"><span data-stu-id="148ad-181">When you identify an origin, you specify whether it should be made _public_ or _private_.</span></span> <span data-ttu-id="148ad-182">Toegang tot CDN-assets in openbare Origins is anoniem, en CDN-inhoud in persoonlijke Origins wordt beveiligd door dynamische gegenereerde tokens voor een betere beveiliging.</span><span class="sxs-lookup"><span data-stu-id="148ad-182">Access to CDN assets in public origins is anonymous, and CDN content in private origins is secured by dynamically generated tokens for greater security.</span></span> <span data-ttu-id="148ad-183">Ongeacht de optie die u kiest, heeft Microsoft het zware recht voor u bij het beheer van de CDN zelf.</span><span class="sxs-lookup"><span data-stu-id="148ad-183">Regardless of which option you choose, Microsoft does all the heavy lifting for you when it comes to administration of the CDN itself.</span></span> <span data-ttu-id="148ad-184">Daarnaast kunt u later ook wijzigen na het instellen van de CDN en het identificeren van uw oorsprong.</span><span class="sxs-lookup"><span data-stu-id="148ad-184">Also, you can change your mind later, after you've set up the CDN and identified your origins.</span></span>

<span data-ttu-id="148ad-185">Zowel de openbare als de persoonlijke opties bieden soortgelijke prestatieverbeteringen, maar elk heeft unieke kenmerken en voordelen.</span><span class="sxs-lookup"><span data-stu-id="148ad-185">Both public and private options provide similar performance gains, but each has unique attributes and advantages.</span></span>

<span data-ttu-id="148ad-186">**Openbare** Origins in Office 365 CDN zijn anoniem toegankelijk en gehoste assets zijn toegankelijk voor iedereen die de URL van het activum bevat.</span><span class="sxs-lookup"><span data-stu-id="148ad-186">**Public** origins within the Office 365 CDN are accessible anonymously, and hosted assets can be accessed by anyone who has the URL to the asset.</span></span> <span data-ttu-id="148ad-187">Aangezien toegang tot inhoud in openbare Origin anoniem is, moet u deze alleen gebruiken voor het opslaan van niet-gevoelige algemene inhoud, zoals JavaScript-bestanden, scripts, pictogrammen en afbeeldingen.</span><span class="sxs-lookup"><span data-stu-id="148ad-187">Because access to content in public origins is anonymous, you should only use them to cache non-sensitive generic content such as javascript files, scripts, icons and images.</span></span>

<span data-ttu-id="148ad-188">**Persoonlijke** Origins in Office 365 CDN bieden persoonlijke toegang tot gebruikers inhoud, zoals documentbibliotheken van SharePoint Online, sites en eigen afbeeldingen.</span><span class="sxs-lookup"><span data-stu-id="148ad-188">**Private** origins within the Office 365 CDN provide private access to user content such as SharePoint Online document libraries, sites and proprietary images.</span></span> <span data-ttu-id="148ad-189">De toegang tot inhoud in persoonlijke Origins wordt door dynamische gegenereerde tokens beveiligd, zodat deze alleen kan worden geopend door gebruikers met machtigingen voor de oorspronkelijke documentbibliotheek of opslaglocatie.</span><span class="sxs-lookup"><span data-stu-id="148ad-189">Access to content in private origins is secured by dynamically generated tokens so it can only be accessed by users with permissions to the original document library or storage location.</span></span> <span data-ttu-id="148ad-190">Persoonlijke Origins in het Office 365-CDN kunnen alleen worden gebruikt voor SharePoint Online-inhoud en u kunt geen toegang krijgen tot assets van persoonlijke oorsprong via omleiding van de SharePoint Online-Tenant.</span><span class="sxs-lookup"><span data-stu-id="148ad-190">Private origins in the Office 365 CDN can only be used for SharePoint Online content, and you can only access assets in private origins through redirection from your SharePoint Online tenant.</span></span>

<span data-ttu-id="148ad-191">U vindt meer informatie over de manier waarop u met behulp van de toegang tot activa in een privé-oorsprong kunt werken [met assets in persoonlijke oorsprong](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins).</span><span class="sxs-lookup"><span data-stu-id="148ad-191">You can read more about how CDN access to assets in a private origin works in [Using assets in private origins](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins).</span></span>

#### <a name="attributes-and-advantages-of-hosting-assets-in-public-origins"></a><span data-ttu-id="148ad-192">Kenmerken en voordelen van het hosten van assets in openbare oorsprong</span><span class="sxs-lookup"><span data-stu-id="148ad-192">Attributes and advantages of hosting assets in public origins</span></span>
  
+ <span data-ttu-id="148ad-193">Activa die zijn opgenomen in een openbare Origin zijn door iedereen anoniem toegankelijk.</span><span class="sxs-lookup"><span data-stu-id="148ad-193">Assets exposed in a public origin are accessible by everyone anonymously.</span></span>
    > [!IMPORTANT]
    > <span data-ttu-id="148ad-194">U dient nooit bronnen te plaatsen die gebruikersgegevens bevatten of die in een openbare Origin als vertrouwelijk worden beschouwd.</span><span class="sxs-lookup"><span data-stu-id="148ad-194">You should never place resources that contain user information or are considered sensitive to your organization in a public origin.</span></span>
+ <span data-ttu-id="148ad-195">Als u een activum verwijdert uit een openbare Origin, is het mogelijk dat het activum tot 30 dagen langer beschikbaar is in de cache. We zullen de koppelingen naar het activum binnen 15 minuten ongeldig maken.</span><span class="sxs-lookup"><span data-stu-id="148ad-195">If you remove an asset from a public origin, the asset may continue to be available for up to 30 days from the cache; however, we will invalidate links to the asset in the CDN within 15 minutes.</span></span>
+ <span data-ttu-id="148ad-196">Wanneer u stijlbladen (CSS-bestanden) in een openbare Origin host, kunt u relatieve paden en Uri's binnen de code gebruiken.</span><span class="sxs-lookup"><span data-stu-id="148ad-196">When you host style sheets (CSS files) in a public origin, you can use relative paths and URIs within the code.</span></span> <span data-ttu-id="148ad-197">Dit betekent dat u kunt verwijzen naar de locatie van achtergrondafbeeldingen en andere objecten ten opzichte van de locatie van het activum dat wordt gebeld.</span><span class="sxs-lookup"><span data-stu-id="148ad-197">This means that you can reference the location of background images and other objects relative to the location of the asset that's calling it.</span></span>
+ <span data-ttu-id="148ad-198">U kunt de URL van een openbare oorsprong ook op een andere manier vastleggen.</span><span class="sxs-lookup"><span data-stu-id="148ad-198">While you can hard code a public origin's URL, doing so is not recommended.</span></span> <span data-ttu-id="148ad-199">De reden hiervoor is dat de toegang tot de CDN niet langer beschikbaar is, dat de URL automatisch wordt omgezet in uw organisatie in SharePoint Online en kan leiden tot verbroken koppelingen en andere fouten.</span><span class="sxs-lookup"><span data-stu-id="148ad-199">The reason for this is that if access to the CDN becomes unavailable, the URL will not automatically resolve to your organization in SharePoint Online and might result in broken links and other errors.</span></span>
+ <span data-ttu-id="148ad-200">De standaardbestandstypen die zijn opgenomen voor openbare oorsprong zijn. CSS,. EOT,. GIF,. ICO,. JPEG,. jpg,. js,. map,. png,. svg,.</span><span class="sxs-lookup"><span data-stu-id="148ad-200">The default file types that are included for public origins are .css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff and .woff2.</span></span> <span data-ttu-id="148ad-201">U kunt extra bestandstypen opgeven.</span><span class="sxs-lookup"><span data-stu-id="148ad-201">You can specify additional file types.</span></span>
+ <span data-ttu-id="148ad-202">U kunt een beleid configureren voor de uitsluiting van activa die zijn aangeduid door de site classificaties die u opgeeft.</span><span class="sxs-lookup"><span data-stu-id="148ad-202">You can configure a policy to exclude assets that have been identified by site classifications that you specify.</span></span> <span data-ttu-id="148ad-203">U kunt bijvoorbeeld alle assets uitsluiten die zijn gemarkeerd als ' vertrouwelijk ' of ' beperkt ', zelfs als ze een toegestaan bestandstype zijn en zich bevinden in een openbare Origin.</span><span class="sxs-lookup"><span data-stu-id="148ad-203">For example, you can choose to exclude all assets that are marked as "confidential" or "restricted" even if they are an allowed file type and are located in a public origin.</span></span>

#### <a name="attributes-and-advantages-of-hosting-assets-in-private-origins"></a><span data-ttu-id="148ad-204">Kenmerken en voordelen van het hosten van assets in persoonlijke oorsprong</span><span class="sxs-lookup"><span data-stu-id="148ad-204">Attributes and advantages of hosting assets in private origins</span></span>

+ <span data-ttu-id="148ad-205">Persoonlijke Origins kunnen alleen worden gebruikt voor SharePoint Online-assets.</span><span class="sxs-lookup"><span data-stu-id="148ad-205">Private origins can only be used for SharePoint Online assets.</span></span>
+ <span data-ttu-id="148ad-206">Gebruikers hebben alleen toegang tot de assets van een privé-oorsprong als ze toegang hebben tot de container.</span><span class="sxs-lookup"><span data-stu-id="148ad-206">Users can only access the assets from a private origin if they have permissions to access the container.</span></span> <span data-ttu-id="148ad-207">Anonieme toegang tot deze assets wordt voorkomen.</span><span class="sxs-lookup"><span data-stu-id="148ad-207">Anonymous access to these assets is prevented.</span></span>
+ <span data-ttu-id="148ad-208">De activa in de privé-oorsprong moeten worden genoemd in de SharePoint Online-Tenant.</span><span class="sxs-lookup"><span data-stu-id="148ad-208">Assets in private origins must be referred from the SharePoint Online tenant.</span></span> <span data-ttu-id="148ad-209">Directe toegang tot private CDN-assets werkt niet.</span><span class="sxs-lookup"><span data-stu-id="148ad-209">Direct access to private CDN assets does not work.</span></span>
+ <span data-ttu-id="148ad-210">Als u een activum verwijdert uit de persoonlijke oorsprong, kan het activum langer beschikbaar zijn voor een uur van de cache. We zullen echter de koppelingen naar het activum binnen 15 minuten na verwijdering van het activum ongeldig maken in het CDN.</span><span class="sxs-lookup"><span data-stu-id="148ad-210">If you remove an asset from the private origin, the asset may continue to be available for up to an hour from the cache; however, we will invalidate links to the asset in the CDN within 15 minutes of the asset's removal.</span></span>
+ <span data-ttu-id="148ad-211">De standaardbestandstypen die zijn opgenomen voor persoonlijke oorsprong zijn. GIF,. ICO,. JPEG,. jpg,. js en. png.</span><span class="sxs-lookup"><span data-stu-id="148ad-211">The default file types that are included for private origins are .gif, .ico, .jpeg, .jpg, .js, and .png.</span></span> <span data-ttu-id="148ad-212">U kunt extra bestandstypen opgeven.</span><span class="sxs-lookup"><span data-stu-id="148ad-212">You can specify additional file types.</span></span>
+ <span data-ttu-id="148ad-213">Net als bij openbare Origin, kunt u een beleid configureren om activa uit te sluiten die zijn geïdentificeerd door site classificaties die u opgeeft, ook als u jokertekens gebruikt om alle elementen in een map of een documentbibliotheek op te nemen.</span><span class="sxs-lookup"><span data-stu-id="148ad-213">Just like with public origins, you can configure a policy to exclude assets that have been identified by site classifications that you specify even if you use wildcards to include all assets within a folder or document library.</span></span>

<span data-ttu-id="148ad-214">Zie [netwerken die inhoud leveren](content-delivery-networks.md)voor meer informatie over het gebruik van Office 365 CDN, algemene CDN-concepten en andere Microsoft-cdn's die u kunt gebruiken met uw Office 365-Tenant.</span><span class="sxs-lookup"><span data-stu-id="148ad-214">For more information about why to use the Office 365 CDN, general CDN concepts, and other Microsoft CDNs you can use with your Office 365 tenant, see [Content Delivery Networks](content-delivery-networks.md).</span></span>

### <a name="default-cdn-origins"></a><span data-ttu-id="148ad-215">Standaard CDN-oorsprong</span><span class="sxs-lookup"><span data-stu-id="148ad-215">Default CDN origins</span></span>

<span data-ttu-id="148ad-216">Tenzij u anders opgeeft, worden in Office 365 sommige standaardoorsprong voor u ingesteld wanneer u Office 365 CDN inschakelt.</span><span class="sxs-lookup"><span data-stu-id="148ad-216">Unless you specify otherwise, Office 365 sets up some default origins for you when you enable the Office 365 CDN.</span></span> <span data-ttu-id="148ad-217">Als u ervoor kiest deze oorsprong niet in te richten, kunt u deze oorsprong toevoegen nadat u de installatie hebt voltooid.</span><span class="sxs-lookup"><span data-stu-id="148ad-217">If you initially opt not to provision them, you can add these origins after you complete setup.</span></span> <span data-ttu-id="148ad-218">Tenzij u weet wat de gevolgen zijn voor het overlopen van de instelling van standaardoorsprong en een specifieke reden om dit te doen, moet u ze laten maken wanneer u het CDN inschakelt.</span><span class="sxs-lookup"><span data-stu-id="148ad-218">Unless you understand the consequences of skipping the setup of default origins and have a specific reason for doing so, you should allow them to be created when you enable the CDN.</span></span>
  
<span data-ttu-id="148ad-219">Standaard persoonlijke CDN-oorsprong:</span><span class="sxs-lookup"><span data-stu-id="148ad-219">Default private CDN origins:</span></span>
  
+ <span data-ttu-id="148ad-220">\*/userphoto.aspx</span><span class="sxs-lookup"><span data-stu-id="148ad-220">\*/userphoto.aspx</span></span>
+ <span data-ttu-id="148ad-221">\*/siteassets</span><span class="sxs-lookup"><span data-stu-id="148ad-221">\*/siteassets</span></span>

<span data-ttu-id="148ad-222">Standaard openbare CDN-oorsprong:</span><span class="sxs-lookup"><span data-stu-id="148ad-222">Default public CDN origins:</span></span>
  
+ <span data-ttu-id="148ad-223">\*/masterpage</span><span class="sxs-lookup"><span data-stu-id="148ad-223">\*/masterpage</span></span>
+ <span data-ttu-id="148ad-224">\*/Style-bibliotheek</span><span class="sxs-lookup"><span data-stu-id="148ad-224">\*/style library</span></span>
+ <span data-ttu-id="148ad-225">\*/clientsideassets</span><span class="sxs-lookup"><span data-stu-id="148ad-225">\*/clientsideassets</span></span>

> [!NOTE]
> <span data-ttu-id="148ad-226">_clientsideassets_ is een standaard-openbare oorsprong die is toegevoegd aan de Office 365 CDN-service in december 2017.</span><span class="sxs-lookup"><span data-stu-id="148ad-226">_clientsideassets_ is a default public origin that was added to the Office 365 CDN service in December 2017.</span></span> <span data-ttu-id="148ad-227">Deze Origin moet bestaan in de volgorde waarin oplossingen van SharePoint Framework in de CDN werken.</span><span class="sxs-lookup"><span data-stu-id="148ad-227">This origin must be present in order for SharePoint Framework solutions in the CDN to work.</span></span> <span data-ttu-id="148ad-228">Als u het Office 365-CDN vóór december 2017 hebt ingeschakeld, of als u de installatie van standaardoorsprong hebt overgeslagen wanneer u het CDN inschakelt, kunt u deze oorsprong handmatig toevoegen.</span><span class="sxs-lookup"><span data-stu-id="148ad-228">If you enabled the Office 365 CDN prior to December 2017, or if you skipped setup of default origins when you enabled the CDN, you can manually add this origin.</span></span> <span data-ttu-id="148ad-229">Zie [het webonderdeel van de client of de SharePoint Framework-oplossing werkt niet](use-microsoft-365-cdn-with-spo.md#my-client-side-web-part-or-sharepoint-framework-solution-isnt-working)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="148ad-229">For more information, see [My client-side web part or SharePoint Framework solution isn't working](use-microsoft-365-cdn-with-spo.md#my-client-side-web-part-or-sharepoint-framework-solution-isnt-working).</span></span>

<span data-ttu-id="148ad-230"><a name="CDNSetupinPShell"> </a></span><span class="sxs-lookup"><span data-stu-id="148ad-230"><a name="CDNSetupinPShell"> </a></span></span>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell"></a><span data-ttu-id="148ad-231">Het Office 365-CDN instellen en configureren met behulp van de SharePoint Online Management Shell</span><span class="sxs-lookup"><span data-stu-id="148ad-231">Set up and configure the Office 365 CDN by using the SharePoint Online Management Shell</span></span>

<span data-ttu-id="148ad-232">Voor de procedures in deze sectie moet u de SharePoint Online Management Shell gebruiken om verbinding te maken met SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="148ad-232">The procedures in this section require you to use the SharePoint Online Management Shell to connect to SharePoint Online.</span></span> <span data-ttu-id="148ad-233">Zie [verbinding maken met SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="148ad-233">For instructions, see [Connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

<span data-ttu-id="148ad-234">Voer de volgende stappen uit om de CDN in te stellen en te configureren voor het hosten van uw assets in SharePoint Online met behulp van SharePoint Online Management Shell.</span><span class="sxs-lookup"><span data-stu-id="148ad-234">Complete these steps to set up and configure the CDN to host your assets in SharePoint Online using the SharePoint Online Management Shell.</span></span>

<details>
  <summary><span data-ttu-id="148ad-235">Klik om uit te vouwen</span><span class="sxs-lookup"><span data-stu-id="148ad-235">Click to expand</span></span></summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a><span data-ttu-id="148ad-236">Toestaan dat uw organisatie Office 365 CDN gebruikt</span><span class="sxs-lookup"><span data-stu-id="148ad-236">Enable your organization to use the Office 365 CDN</span></span>

<span data-ttu-id="148ad-237">Voordat u wijzigingen aanbrengt in de CDN-instellingen van de Tenant, moet u de huidige status van de persoonlijke CDN-configuratie in de Office 365-Tenant ophalen.</span><span class="sxs-lookup"><span data-stu-id="148ad-237">Before you make changes to the tenant CDN settings, you should retrieve the current status of the private CDN configuration in your Office 365 tenant.</span></span> <span data-ttu-id="148ad-238">Maak verbinding met de Tenant met behulp van SharePoint Online Management Shell:</span><span class="sxs-lookup"><span data-stu-id="148ad-238">Connect to your tenant using the SharePoint Online Management Shell:</span></span>

``` powershell
Connect-SPOService -Url https://contoso-admin.sharepoint.com
```

<span data-ttu-id="148ad-239">Gebruik nu de cmdlet **Get-SPOTenantCdnEnabled** om de CDN-statusinstellingen van de Tenant op te halen:</span><span class="sxs-lookup"><span data-stu-id="148ad-239">Now use the **Get-SPOTenantCdnEnabled** cmdlet to retrieve the CDN status settings from the tenant:</span></span>

``` powershell
Get-SPOTenantCdnEnabled -CdnType <Public | Private>
```

<span data-ttu-id="148ad-240">De status van de CDN voor het opgegeven CdnType wordt uitgevoerd naar het scherm.</span><span class="sxs-lookup"><span data-stu-id="148ad-240">The status of the CDN for the specified CdnType will output to the screen.</span></span>

<span data-ttu-id="148ad-241">Gebruik de cmdlet **set-SPOTenantCdnEnabled** om uw organisatie de mogelijkheid Office 365 CDN te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="148ad-241">Use the **Set-SPOTenantCdnEnabled** cmdlet to enable your organization to use the Office 365 CDN.</span></span> <span data-ttu-id="148ad-242">U kunt ervoor zorgen dat uw organisatie openbare Origins, persoonlijke oorsprong of beide tegelijk kan gebruiken.</span><span class="sxs-lookup"><span data-stu-id="148ad-242">You can enable your organization to use public origins, private origins, or both at once.</span></span> <span data-ttu-id="148ad-243">U kunt de CDN ook configureren om de instelling van standaardoorsprong te negeren wanneer u deze inschakelt.</span><span class="sxs-lookup"><span data-stu-id="148ad-243">You can also configure the CDN to skip the setup of default origins when you enable it.</span></span> <span data-ttu-id="148ad-244">U kunt deze oorsprong altijd later toevoegen, zoals beschreven in dit onderwerp.</span><span class="sxs-lookup"><span data-stu-id="148ad-244">You can always add these origins later as described in this topic.</span></span>
  
<span data-ttu-id="148ad-245">In Windows PowerShell voor SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="148ad-245">In Windows Powershell for SharePoint Online:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

<span data-ttu-id="148ad-246">Als u bijvoorbeeld wilt dat uw organisatie zowel openbare als persoonlijke oorsprong kan gebruiken, typt u de volgende opdracht:</span><span class="sxs-lookup"><span data-stu-id="148ad-246">For example, to enable your organization to use both public and private origins, type the following command:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

<span data-ttu-id="148ad-247">Als u wilt dat uw organisatie zowel openbare als persoonlijke Origins kan gebruiken, maar de instelling van de standaardoorsprong gaat negeren, typt u de volgende opdracht:</span><span class="sxs-lookup"><span data-stu-id="148ad-247">To enable your organization to use both public and private origins but skip setting up the default origins, type the following command:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

<span data-ttu-id="148ad-248">Zie [standaard CDN-oorsprong](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) voor informatie over de oorsprong die standaard wordt ingericht wanneer u Office 365 CDN inschakelt en de mogelijkheid om de instelling van standaardoorsprong over te slaan.</span><span class="sxs-lookup"><span data-stu-id="148ad-248">See [Default CDN origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) for information about the origins that are provisioned by default when you enable the Office 365 CDN, and the potential impact of skipping the setup of default origins.</span></span>

<span data-ttu-id="148ad-249">Als u wilt dat uw organisatie gebruik kan maken van openbare oorsprong, typt u de volgende opdracht:</span><span class="sxs-lookup"><span data-stu-id="148ad-249">To enable your organization to use public origins, type the following command:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $true
```

<span data-ttu-id="148ad-250">Als u wilt dat uw organisatie gebruik kan maken van persoonlijke oorsprong, typt u de volgende opdracht:</span><span class="sxs-lookup"><span data-stu-id="148ad-250">To enable your organization to use private origins, type the following command:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $true
```

<span data-ttu-id="148ad-251">Zie [set-SPOTenantCdnEnabled](https://technet.microsoft.com/library/mt790765.aspx)voor meer informatie over deze cmdlet.</span><span class="sxs-lookup"><span data-stu-id="148ad-251">For more information about this cmdlet, see [Set-SPOTenantCdnEnabled](https://technet.microsoft.com/library/mt790765.aspx).</span></span>

<span data-ttu-id="148ad-252"><a name="Office365CDNforSPOFileType"> </a></span><span class="sxs-lookup"><span data-stu-id="148ad-252"><a name="Office365CDNforSPOFileType"> </a></span></span>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a><span data-ttu-id="148ad-253">De lijst met bestandstypen wijzigen die moeten worden opgenomen in het Office 365 CDN (optioneel)</span><span class="sxs-lookup"><span data-stu-id="148ad-253">Change the list of file types to include in the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="148ad-254">Wanneer u bestandstypen definieert met behulp van de cmdlet **set-SPOTenantCdnPolicy** , wordt de momenteel gedefinieerde lijst overschreven.</span><span class="sxs-lookup"><span data-stu-id="148ad-254">When you define file types by using the **Set-SPOTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="148ad-255">Als u extra bestandstypen aan de lijst wilt toevoegen, gebruikt u de cmdlet eerst om erachter te komen welke bestandstypen al zijn toegestaan en voegt u ze toe aan de lijst samen met uw nieuwe.</span><span class="sxs-lookup"><span data-stu-id="148ad-255">If you want to add additional file types to the list, use the cmdlet first to find out what file types are already allowed and include them in the list along with your new ones.</span></span>
  
<span data-ttu-id="148ad-256">Met de cmdlet **set-SPOTenantCdnPolicy** kunt u statische bestandstypen definiëren die worden gehost door openbare en persoonlijke Origins in het CDN.</span><span class="sxs-lookup"><span data-stu-id="148ad-256">Use the **Set-SPOTenantCdnPolicy** cmdlet to define static file types that can be hosted by public and private origins in the CDN.</span></span> <span data-ttu-id="148ad-257">Veelgebruikte activatypen zijn standaard toegestaan, bijvoorbeeld. CSS,. GIF,. jpg en. js.</span><span class="sxs-lookup"><span data-stu-id="148ad-257">By default, common asset types are allowed, for example .css, .gif, .jpg, and .js.</span></span>

<span data-ttu-id="148ad-258">In Windows PowerShell voor SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="148ad-258">In Windows PowerShell for SharePoint Online:</span></span>

``` powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

<span data-ttu-id="148ad-259">Als u bijvoorbeeld de CDN wilt inschakelen voor host. CSS-en PNG-bestanden, typt u de volgende opdracht:</span><span class="sxs-lookup"><span data-stu-id="148ad-259">For example, to enable the CDN to host .css and .png files, you would enter the command:</span></span>

``` powershell
Set-SPOTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

<span data-ttu-id="148ad-260">Gebruik de cmdlet **Get-Get spotenantcdnpolicies** om te zien welke bestandstypen momenteel zijn toegestaan in het CDN.</span><span class="sxs-lookup"><span data-stu-id="148ad-260">To see what file types are currently allowed by the CDN, use the **Get-SPOTenantCdnPolicies** cmdlet:</span></span>

``` powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="148ad-261">Zie [set-SPOTenantCdnPolicy](https://technet.microsoft.com/library/mt800839.aspx) en [Get-Get spotenantcdnpolicies](https://technet.microsoft.com/library/mt800838.aspx)voor meer informatie over deze cmdlets.</span><span class="sxs-lookup"><span data-stu-id="148ad-261">For more information about these cmdlets, see [Set-SPOTenantCdnPolicy](https://technet.microsoft.com/library/mt800839.aspx) and [Get-SPOTenantCdnPolicies](https://technet.microsoft.com/library/mt800838.aspx).</span></span>

<span data-ttu-id="148ad-262"><a name="Office365CDNforSPOSiteClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="148ad-262"><a name="Office365CDNforSPOSiteClassification"> </a></span></span>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a><span data-ttu-id="148ad-263">De lijst met site classificaties wijzigen die u wilt uitsluiten van Office 365 CDN (optioneel)</span><span class="sxs-lookup"><span data-stu-id="148ad-263">Change the list of site classifications you want to exclude from the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="148ad-264">Wanneer u site classificaties uitsluit met behulp van de cmdlet **set-SPOTenantCdnPolicy** , wordt de momenteel gedefinieerde lijst overschreven.</span><span class="sxs-lookup"><span data-stu-id="148ad-264">When you exclude site classifications by using the **Set-SPOTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="148ad-265">Als u extra site classificaties wilt uitsluiten, gebruikt u de cmdlet eerst om erachter te komen welke classificaties al zijn uitgesloten en voegt u ze vervolgens samen met uw nieuwe.</span><span class="sxs-lookup"><span data-stu-id="148ad-265">If you want to exclude additional site classifications, use the cmdlet first to find out what classifications are already excluded and then add them along with your new ones.</span></span>

<span data-ttu-id="148ad-266">Met de cmdlet **set-SPOTenantCdnPolicy** kunt u de site classificaties uitsluiten die u niet beschikbaar wilt maken via het CDN.</span><span class="sxs-lookup"><span data-stu-id="148ad-266">Use the **Set-SPOTenantCdnPolicy** cmdlet to exclude site classifications that you do not want to make available over the CDN.</span></span> <span data-ttu-id="148ad-267">Standaard zijn geen site classificaties uitgesloten.</span><span class="sxs-lookup"><span data-stu-id="148ad-267">By default, no site classifications are excluded.</span></span>

<span data-ttu-id="148ad-268">In Windows PowerShell voor SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="148ad-268">In Windows PowerShell for SharePoint Online:</span></span>

``` powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications >"
```

<span data-ttu-id="148ad-269">Gebruik de cmdlet **Get-Get spotenantcdnpolicies** om te zien welke site classificaties momenteel zijn toegestaan.</span><span class="sxs-lookup"><span data-stu-id="148ad-269">To see what site classifications are currently restricted, use the **Get-SPOTenantCdnPolicies** cmdlet:</span></span>

``` powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="148ad-270">De eigenschappen die worden geretourneerd, zijn _IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ en _ExcludeIfNoScriptDisabled_.</span><span class="sxs-lookup"><span data-stu-id="148ad-270">The properties that will be returned are _IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ and _ExcludeIfNoScriptDisabled_.</span></span>

<span data-ttu-id="148ad-271">De eigenschap _IncludeFileExtensions_ bevat de lijst met bestandsextensies die vanuit het CDN worden bediend.</span><span class="sxs-lookup"><span data-stu-id="148ad-271">The _IncludeFileExtensions_ property contains the list of file extensions that will be served from the CDN.</span></span>

> [!NOTE]
> <span data-ttu-id="148ad-272">De standaardbestandsextensies verschillen tussen openbare en persoonlijke bestanden.</span><span class="sxs-lookup"><span data-stu-id="148ad-272">The default file extensions are different between public and private.</span></span>

<span data-ttu-id="148ad-273">De eigenschap _ExcludeRestrictedSiteClassifications_ bevat de site classificaties die u wilt uitsluiten van het CDN.</span><span class="sxs-lookup"><span data-stu-id="148ad-273">The _ExcludeRestrictedSiteClassifications_ property contains the site classifications that you want to exclude from the CDN.</span></span> <span data-ttu-id="148ad-274">U kunt bijvoorbeeld sites die als **vertrouwelijk** zijn gemarkeerd, uitsluiten, zodat de inhoud van sites met die classificatie niet via het CDN wordt verzonden.</span><span class="sxs-lookup"><span data-stu-id="148ad-274">For example, you can exclude sites marked as **Confidential** so content from sites with that classification applied will not be served from the CDN.</span></span>

<span data-ttu-id="148ad-275">De eigenschap _ExcludeIfNoScriptDisabled_ uitsluiten de inhoud van de CDN op basis van de instellingen van het _NoScript_ op siteniveau.</span><span class="sxs-lookup"><span data-stu-id="148ad-275">The _ExcludeIfNoScriptDisabled_ property excludes content from the CDN based on the site-level _NoScript_ attribute settings.</span></span> <span data-ttu-id="148ad-276">Het kenmerk _NoScript_ is standaard ingesteld op **beschikbaar** voor _moderne_ sites en **uitgeschakeld** voor _klassieke_ sites.</span><span class="sxs-lookup"><span data-stu-id="148ad-276">By default, the _NoScript_ attribute is set to **Enabled** for _Modern_ sites and **Disabled** for _Classic_ sites.</span></span> <span data-ttu-id="148ad-277">Dit hangt af van uw tenantinstellingen.</span><span class="sxs-lookup"><span data-stu-id="148ad-277">This depends on your tenant settings.</span></span>

<span data-ttu-id="148ad-278">Zie [set-SPOTenantCdnPolicy](https://technet.microsoft.com/library/mt800839.aspx) en [Get-Get spotenantcdnpolicies](https://technet.microsoft.com/library/mt800838.aspx)voor meer informatie over deze cmdlets.</span><span class="sxs-lookup"><span data-stu-id="148ad-278">For more information about these cmdlets, see [Set-SPOTenantCdnPolicy](https://technet.microsoft.com/library/mt800839.aspx) and [Get-SPOTenantCdnPolicies](https://technet.microsoft.com/library/mt800838.aspx).</span></span>

<span data-ttu-id="148ad-279"><a name="Office365CDNforSPOOriginPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="148ad-279"><a name="Office365CDNforSPOOriginPosh"> </a></span></span>
### <a name="add-an-origin-for-your-assets"></a><span data-ttu-id="148ad-280">Een oorsprong voor uw activa toevoegen</span><span class="sxs-lookup"><span data-stu-id="148ad-280">Add an origin for your assets</span></span>

<span data-ttu-id="148ad-281">Met de cmdlet **add-add spotenantcdnorigin** kunt u een oorsprong definiëren.</span><span class="sxs-lookup"><span data-stu-id="148ad-281">Use the **Add-SPOTenantCdnOrigin** cmdlet to define an origin.</span></span> <span data-ttu-id="148ad-282">U kunt meerdere oorsprong definiëren.</span><span class="sxs-lookup"><span data-stu-id="148ad-282">You can define multiple origins.</span></span> <span data-ttu-id="148ad-283">De origin is een URL die verwijst naar een SharePoint-bibliotheek of-map die de assets bevat die u wilt hosten door de CDN.</span><span class="sxs-lookup"><span data-stu-id="148ad-283">The origin is a URL that points to a SharePoint library or folder that contains the assets that you want to be hosted by the CDN.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="148ad-284">U dient nooit bronnen te plaatsen die gebruikersgegevens bevatten of die in een openbare Origin als vertrouwelijk worden beschouwd.</span><span class="sxs-lookup"><span data-stu-id="148ad-284">You should never place resources that contain user information or are considered sensitive to your organization in a public origin.</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

<span data-ttu-id="148ad-285">De waarde van _pad_ is het relatieve pad naar de bibliotheek of map met de assets.</span><span class="sxs-lookup"><span data-stu-id="148ad-285">The value of _path_ is the relative path to the library or folder that contains the assets.</span></span> <span data-ttu-id="148ad-286">U kunt jokertekens gebruiken in aanvulling op relatieve paden.</span><span class="sxs-lookup"><span data-stu-id="148ad-286">You can use wildcards in addition to relative paths.</span></span> <span data-ttu-id="148ad-287">Voor de URL worden jokertekens ondersteund.</span><span class="sxs-lookup"><span data-stu-id="148ad-287">Origins support wildcards prepended to the URL.</span></span> <span data-ttu-id="148ad-288">Hiermee kunt u oorsprong maken die meerdere sites beslaat.</span><span class="sxs-lookup"><span data-stu-id="148ad-288">This allows you to create origins that span multiple sites.</span></span> <span data-ttu-id="148ad-289">Als u bijvoorbeeld alle activa in de map # # # # # # # # # # # # # # # # wilt opnemen in het CDN, typt u de volgende opdracht:</span><span class="sxs-lookup"><span data-stu-id="148ad-289">For example, to include all of the assets in the masterpages folder for all of your sites as a public origin within the CDN, type the following command:</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ <span data-ttu-id="148ad-290">De wijziging van het jokerteken \* **/** kan alleen aan het begin van het pad worden gebruikt en komt overeen met alle URL-segmenten onder de opgegeven URL.</span><span class="sxs-lookup"><span data-stu-id="148ad-290">The wildcard modifier \***/** can only be used at the beginning of the path, and will match all URL segments under the specified URL.</span></span>
+ <span data-ttu-id="148ad-291">Het pad kan verwijzen naar een documentbibliotheek, map of site.</span><span class="sxs-lookup"><span data-stu-id="148ad-291">The path can point to a document library, folder or site.</span></span> <span data-ttu-id="148ad-292">Het pad _\*/site1_ komt bijvoorbeeld overeen met alle documentbibliotheken onder de site.</span><span class="sxs-lookup"><span data-stu-id="148ad-292">For example, the path _\*/site1_ will match all the document libraries under the site.</span></span>

<span data-ttu-id="148ad-293">U kunt een oorsprong met een specifiek relatief pad toevoegen.</span><span class="sxs-lookup"><span data-stu-id="148ad-293">You can add an origin with a specific relative path.</span></span> <span data-ttu-id="148ad-294">U kunt geen origin toevoegen met het volledige pad.</span><span class="sxs-lookup"><span data-stu-id="148ad-294">You cannot add an origin using the full path.</span></span>

<span data-ttu-id="148ad-295">In dit voorbeeld wordt een persoonlijke oorsprong van de siteassets-bibliotheek op een specifieke site toegevoegd:</span><span class="sxs-lookup"><span data-stu-id="148ad-295">This example adds a private origin of the siteassets library on a specific site:</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="148ad-296">In dit voorbeeld wordt een persoonlijke oorsprong van de map _Map1_ toegevoegd aan de bibliotheek siteactiva van de siteverzameling:</span><span class="sxs-lookup"><span data-stu-id="148ad-296">This example adds a private origin of the _folder1_ folder in the site collection's site assets library:</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

<span data-ttu-id="148ad-297">Als het pad een spatie bevat, kunt u het pad tussen dubbele aanhalingstekens plaatsen of de ruimte vervangen door de URL-codering %20.</span><span class="sxs-lookup"><span data-stu-id="148ad-297">If there is a space in the path, you can either surround the path in double quotes or replace the space with the URL encoding %20.</span></span> <span data-ttu-id="148ad-298">In het volgende voorbeeld wordt een persoonlijke oorsprong van de map _map 1_ toegevoegd aan de bibliotheek siteactiva van de siteverzameling:</span><span class="sxs-lookup"><span data-stu-id="148ad-298">The following examples add a private origin of the _folder 1_ folder in the site collection's site assets library:</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

<span data-ttu-id="148ad-299">Zie [add-add spotenantcdnorigin](https://technet.microsoft.com/library/mt790772.aspx)voor meer informatie over deze opdracht en de syntaxis.</span><span class="sxs-lookup"><span data-stu-id="148ad-299">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790772.aspx).</span></span>

> [!NOTE]
> <span data-ttu-id="148ad-300">Bij particuliere Origin moet de activa die vanaf een oorsprong worden gedeeld, een primaire versie hebben gepubliceerd voordat ze toegankelijk zijn vanuit het CDN.</span><span class="sxs-lookup"><span data-stu-id="148ad-300">In private origins, assets being shared from an origin must have a major version published before they can be accessed from the CDN.</span></span>
  
<span data-ttu-id="148ad-301">Wanneer u de opdracht hebt uitgevoerd, wordt de configuratie door het systeem gesynchroniseerd via het datacenter.</span><span class="sxs-lookup"><span data-stu-id="148ad-301">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="148ad-302">Dit kan 15 minuten duren.</span><span class="sxs-lookup"><span data-stu-id="148ad-302">This can take up to 15 minutes.</span></span>

<span data-ttu-id="148ad-303"><a name="ExamplePublicOrigin"> </a></span><span class="sxs-lookup"><span data-stu-id="148ad-303"><a name="ExamplePublicOrigin"> </a></span></span>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a><span data-ttu-id="148ad-304">Voorbeeld: een openbare Origin configureren voor uw basispagina's en voor de stijlbibliotheek voor SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="148ad-304">Example: Configure a public origin for your master pages and for your style library for SharePoint Online</span></span>

<span data-ttu-id="148ad-305">Normaalgesproken zijn deze oorsprong voor u standaard ingesteld wanneer u Office 365 CDN inschakelt.</span><span class="sxs-lookup"><span data-stu-id="148ad-305">Normally, these origins are set up for you by default when you enable the Office 365 CDN.</span></span> <span data-ttu-id="148ad-306">Voer de volgende stappen uit als u deze handmatig wilt inschakelen.</span><span class="sxs-lookup"><span data-stu-id="148ad-306">However, if you want to enable them manually, follow these steps.</span></span>
  
+ <span data-ttu-id="148ad-307">Met de cmdlet **add-add spotenantcdnorigin** kunt u de stijlbibliotheek definiëren als een openbare Origin.</span><span class="sxs-lookup"><span data-stu-id="148ad-307">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the style library as a public origin.</span></span>

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ <span data-ttu-id="148ad-308">Met de cmdlet **add-add spotenantcdnorigin** kunt u de basispagina's definiëren als een openbare Origin.</span><span class="sxs-lookup"><span data-stu-id="148ad-308">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the master pages as a public origin.</span></span>

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

<span data-ttu-id="148ad-309">Zie [add-add spotenantcdnorigin](https://technet.microsoft.com/library/mt790772.aspx)voor meer informatie over deze opdracht en de syntaxis.</span><span class="sxs-lookup"><span data-stu-id="148ad-309">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790772.aspx).</span></span>

<span data-ttu-id="148ad-310">Wanneer u de opdracht hebt uitgevoerd, wordt de configuratie door het systeem gesynchroniseerd via het datacenter.</span><span class="sxs-lookup"><span data-stu-id="148ad-310">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="148ad-311">Dit kan 15 minuten duren.</span><span class="sxs-lookup"><span data-stu-id="148ad-311">This can take up to 15 minutes.</span></span>

<span data-ttu-id="148ad-312"><a name="ExamplePrivateOrigin"> </a></span><span class="sxs-lookup"><span data-stu-id="148ad-312"><a name="ExamplePrivateOrigin"> </a></span></span>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a><span data-ttu-id="148ad-313">Voorbeeld: een persoonlijke Origin configureren voor uw site-assets, sitepagina's en publicatie afbeeldingen voor SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="148ad-313">Example: Configure a private origin for your site assets, site pages, and publishing images for SharePoint Online</span></span>

+ <span data-ttu-id="148ad-314">Met de cmdlet **add-add spotenantcdnorigin** kunt u de map siteactiva definiëren als persoonlijke Origin.</span><span class="sxs-lookup"><span data-stu-id="148ad-314">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the site assets folder as a private origin.</span></span>

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ <span data-ttu-id="148ad-315">Met de cmdlet **add-add spotenantcdnorigin** kunt u de map sitepagina's definiëren als persoonlijke Origin.</span><span class="sxs-lookup"><span data-stu-id="148ad-315">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the site pages folder as a private origin.</span></span>

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ <span data-ttu-id="148ad-316">Met de cmdlet **add-add spotenantcdnorigin** kunt u de map met publicatie-afbeeldingen definiëren als persoonlijke Origin.</span><span class="sxs-lookup"><span data-stu-id="148ad-316">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the publishing images folder as a private origin.</span></span>

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

<span data-ttu-id="148ad-317">Zie [add-add spotenantcdnorigin](https://technet.microsoft.com/library/mt790772.aspx)voor meer informatie over deze opdracht en de syntaxis.</span><span class="sxs-lookup"><span data-stu-id="148ad-317">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790772.aspx).</span></span>

<span data-ttu-id="148ad-318">Wanneer u de opdracht hebt uitgevoerd, wordt de configuratie door het systeem gesynchroniseerd via het datacenter.</span><span class="sxs-lookup"><span data-stu-id="148ad-318">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="148ad-319">Dit kan 15 minuten duren.</span><span class="sxs-lookup"><span data-stu-id="148ad-319">This can take up to 15 minutes.</span></span>

<span data-ttu-id="148ad-320"><a name="ExamplePrivateOriginSiteCollection"> </a></span><span class="sxs-lookup"><span data-stu-id="148ad-320"><a name="ExamplePrivateOriginSiteCollection"> </a></span></span>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a><span data-ttu-id="148ad-321">Voorbeeld: een persoonlijke Origin configureren voor een siteverzameling voor SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="148ad-321">Example: Configure a private origin for a site collection for SharePoint Online</span></span>

<span data-ttu-id="148ad-322">Met de cmdlet **add-add spotenantcdnorigin** kunt u een siteverzameling als persoonlijke Origin definiëren.</span><span class="sxs-lookup"><span data-stu-id="148ad-322">Use the **Add-SPOTenantCdnOrigin** cmdlet to define a site collection as a private origin.</span></span> <span data-ttu-id="148ad-323">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="148ad-323">For example:</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="148ad-324">Zie [add-add spotenantcdnorigin](https://technet.microsoft.com/library/mt790772.aspx)voor meer informatie over deze opdracht en de syntaxis.</span><span class="sxs-lookup"><span data-stu-id="148ad-324">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790772.aspx).</span></span>
  
<span data-ttu-id="148ad-325">Wanneer u de opdracht hebt uitgevoerd, wordt de configuratie door het systeem gesynchroniseerd via het datacenter.</span><span class="sxs-lookup"><span data-stu-id="148ad-325">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="148ad-326">U ziet mogelijk een bericht _in behandeling_ waarvan de status van de SharePoint Online-Tenant wordt verwacht, zodat deze verbinding maakt met de CDN-service.</span><span class="sxs-lookup"><span data-stu-id="148ad-326">You may see a _Configuration pending_ message which is expected as the SharePoint Online tenant connects to the CDN service.</span></span> <span data-ttu-id="148ad-327">Dit kan 15 minuten duren.</span><span class="sxs-lookup"><span data-stu-id="148ad-327">This can take up to 15 minutes.</span></span>

<span data-ttu-id="148ad-328"><a name="CDNManage"> </a></span><span class="sxs-lookup"><span data-stu-id="148ad-328"><a name="CDNManage"> </a></span></span>
### <a name="manage-the-office-365-cdn"></a><span data-ttu-id="148ad-329">Het Office 365-CDN beheren</span><span class="sxs-lookup"><span data-stu-id="148ad-329">Manage the Office 365 CDN</span></span>

<span data-ttu-id="148ad-330">Wanneer u de CDN hebt ingesteld, kunt u wijzigingen aanbrengen in de configuratie wanneer u inhoud bijwerkt of de gewenste wijziging aanbrengt, zoals in deze sectie wordt beschreven.</span><span class="sxs-lookup"><span data-stu-id="148ad-330">Once you've set up the CDN, you can make changes to your configuration as you update content or as your needs change, as described in this section.</span></span>
  
<span data-ttu-id="148ad-331"><a name="Office365CDNforSPOaddremoveasset"> </a></span><span class="sxs-lookup"><span data-stu-id="148ad-331"><a name="Office365CDNforSPOaddremoveasset"> </a></span></span>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a><span data-ttu-id="148ad-332">Bronnen toevoegen, bijwerken of verwijderen uit het Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="148ad-332">Add, update, or remove assets from the Office 365 CDN</span></span>

<span data-ttu-id="148ad-333">Wanneer u de instellingsstappen hebt voltooid, kunt u nieuwe activa toevoegen en bestaande activa bijwerken of verwijderen wanneer u maar wilt.</span><span class="sxs-lookup"><span data-stu-id="148ad-333">Once you've completed the setup steps, you can add new assets, and update or remove existing assets whenever you want.</span></span> <span data-ttu-id="148ad-334">Breng de gewenste wijzigingen aan in de activa in de map of in de SharePoint-bibliotheek die u als een oorsprong hebt aangewezen.</span><span class="sxs-lookup"><span data-stu-id="148ad-334">Just make your changes to the assets in the folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="148ad-335">Als u een nieuw activum toevoegt, is het direct beschikbaar via het CDN.</span><span class="sxs-lookup"><span data-stu-id="148ad-335">If you add a new asset, it is available through the CDN immediately.</span></span> <span data-ttu-id="148ad-336">Als u echter het activum bijwerkt, duurt het maximaal vijftien minuten voordat de nieuwe versie beschikbaar is in het CDN.</span><span class="sxs-lookup"><span data-stu-id="148ad-336">However, if you update the asset, it will take up to 15 minutes for the new copy to propagate and become available in the CDN.</span></span>
  
<span data-ttu-id="148ad-337">Als u de locatie van de origin moet ophalen, kunt u de cmdlet **Get-SPOTenantCdnOrigins** gebruiken.</span><span class="sxs-lookup"><span data-stu-id="148ad-337">If you need to retrieve the location of the origin, you can use the **Get-SPOTenantCdnOrigins** cmdlet.</span></span> <span data-ttu-id="148ad-338">Zie [Get-SPOTenantCdnOrigins](https://technet.microsoft.com/library/mt790770.aspx)voor informatie over het gebruik van deze cmdlet.</span><span class="sxs-lookup"><span data-stu-id="148ad-338">For information on how to use this cmdlet, see [Get-SPOTenantCdnOrigins](https://technet.microsoft.com/library/mt790770.aspx).</span></span>

<span data-ttu-id="148ad-339"><a name="Office365CDNforSPORemoveOriginPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="148ad-339"><a name="Office365CDNforSPORemoveOriginPosh"> </a></span></span>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a><span data-ttu-id="148ad-340">Een oorsprong uit Office 365 CDN verwijderen</span><span class="sxs-lookup"><span data-stu-id="148ad-340">Remove an origin from the Office 365 CDN</span></span>

<span data-ttu-id="148ad-341">U kunt de toegang tot een map of een SharePoint-bibliotheek die u als een oorsprong hebt opgegeven, verwijderen.</span><span class="sxs-lookup"><span data-stu-id="148ad-341">You can remove access to a folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="148ad-342">U kunt dit doen met behulp van de **Remove-add spotenantcdnorigin-** cmdlet.</span><span class="sxs-lookup"><span data-stu-id="148ad-342">To do this, use the **Remove-SPOTenantCdnOrigin** cmdlet.</span></span>

``` powershell
Remove-SPOTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

<span data-ttu-id="148ad-343">Zie [Remove-add spotenantcdnorigin](https://technet.microsoft.com/library/mt790761.aspx)voor informatie over het gebruik van deze cmdlet.</span><span class="sxs-lookup"><span data-stu-id="148ad-343">For information on how to use this cmdlet, see [Remove-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790761.aspx).</span></span>

<span data-ttu-id="148ad-344"><a name="Office365CDNforSPOModifyOrigin"> </a></span><span class="sxs-lookup"><span data-stu-id="148ad-344"><a name="Office365CDNforSPOModifyOrigin"> </a></span></span>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a><span data-ttu-id="148ad-345">Een origin in het Office 365-CDN wijzigen</span><span class="sxs-lookup"><span data-stu-id="148ad-345">Modify an origin in the Office 365 CDN</span></span>

<span data-ttu-id="148ad-346">U kunt geen Origin wijzigen die u hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="148ad-346">You cannot modify an origin you've created.</span></span> <span data-ttu-id="148ad-347">In plaats daarvan verwijdert u de oorsprong en voegt u een nieuwe toe.</span><span class="sxs-lookup"><span data-stu-id="148ad-347">Instead, remove the origin and then add a new one.</span></span> <span data-ttu-id="148ad-348">Zie voor meer informatie [een origin verwijderen uit het Office 365 CDN](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPosh) en [een origin voor uw assets toevoegen](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPosh).</span><span class="sxs-lookup"><span data-stu-id="148ad-348">For more information, see [To remove an origin from the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPosh) and [To add an origin for your assets](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPosh).</span></span>

<span data-ttu-id="148ad-349"><a name="Office365CDNforSPODisable"> </a></span><span class="sxs-lookup"><span data-stu-id="148ad-349"><a name="Office365CDNforSPODisable"> </a></span></span>
#### <a name="disable-the-office-365-cdn"></a><span data-ttu-id="148ad-350">Het Office 365-CDN uitschakelen</span><span class="sxs-lookup"><span data-stu-id="148ad-350">Disable the Office 365 CDN</span></span>

<span data-ttu-id="148ad-351">Gebruik de cmdlet **set-SPOTenantCdnEnabled** om de CDN uit te schakelen voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="148ad-351">Use the **Set-SPOTenantCdnEnabled** cmdlet to disable the CDN for your organization.</span></span> <span data-ttu-id="148ad-352">Als u zowel openbare als persoonlijke Origins voor het CDN hebt ingeschakeld, moet u de cmdlet twee keer uitvoeren, zoals in de volgende voorbeelden wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="148ad-352">If you have both the public and private origins enabled for the CDN, you need to run the cmdlet twice as shown in the following examples.</span></span>
  
<span data-ttu-id="148ad-353">Als u het gebruik van openbare Origins in het CDN wilt uitschakelen, voert u de volgende opdracht in:</span><span class="sxs-lookup"><span data-stu-id="148ad-353">To disable use of public origins in the CDN, enter the following command:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $false
```

<span data-ttu-id="148ad-354">Als u het gebruik van de persoonlijke Origins in het CDN wilt uitschakelen, voert u de volgende opdracht in:</span><span class="sxs-lookup"><span data-stu-id="148ad-354">To disable use of the private origins in the CDN, enter the following command:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $false
```

<span data-ttu-id="148ad-355">Zie [set-SPOTenantCdnEnabled](https://technet.microsoft.com/library/mt790765.aspx)voor meer informatie over deze cmdlet.</span><span class="sxs-lookup"><span data-stu-id="148ad-355">For more information about this cmdlet, see [Set-SPOTenantCdnEnabled](https://technet.microsoft.com/library/mt790765.aspx).</span></span>

</details>

<span data-ttu-id="148ad-356"><a name="CDNSetupinPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="148ad-356"><a name="CDNSetupinPnPPosh"> </a></span></span>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-pnp-powershell"></a><span data-ttu-id="148ad-357">Het Office 365-CDN instellen en configureren met behulp van PnP PowerShell</span><span class="sxs-lookup"><span data-stu-id="148ad-357">Set up and configure the Office 365 CDN by using PnP PowerShell</span></span>

<span data-ttu-id="148ad-358">Voor de procedures in dit gedeelte moet u gebruikmaken van PnP PowerShell om verbinding te maken met SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="148ad-358">The procedures in this section require you to use PnP PowerShell to connect to SharePoint Online.</span></span> <span data-ttu-id="148ad-359">Zie [aan de slag met PnP PowerShell](https://github.com/SharePoint/PnP-PowerShell#getting-started)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="148ad-359">For instructions, see [Getting started with PnP PowerShell](https://github.com/SharePoint/PnP-PowerShell#getting-started).</span></span>

<span data-ttu-id="148ad-360">Voer de volgende stappen uit om de CDN in te stellen en te configureren voor het hosten van uw assets in SharePoint Online met behulp van PnP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="148ad-360">Complete these steps to set up and configure the CDN to host your assets in SharePoint Online using PnP PowerShell.</span></span>

<details>
  <summary><span data-ttu-id="148ad-361">Klik om uit te vouwen</span><span class="sxs-lookup"><span data-stu-id="148ad-361">Click to expand</span></span></summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a><span data-ttu-id="148ad-362">Toestaan dat uw organisatie Office 365 CDN gebruikt</span><span class="sxs-lookup"><span data-stu-id="148ad-362">Enable your organization to use the Office 365 CDN</span></span>

<span data-ttu-id="148ad-363">Voordat u wijzigingen aanbrengt in de CDN-instellingen van de Tenant, moet u de huidige status van de persoonlijke CDN-configuratie in de Office 365-Tenant ophalen.</span><span class="sxs-lookup"><span data-stu-id="148ad-363">Before you make changes to the tenant CDN settings, you should retrieve the current status of the private CDN configuration in your Office 365 tenant.</span></span> <span data-ttu-id="148ad-364">Maak verbinding met de Tenant met behulp van PnP PowerShell:</span><span class="sxs-lookup"><span data-stu-id="148ad-364">Connect to your tenant using PnP PowerShell:</span></span>

``` powershell
Connect-PnPOnline -Url https://contoso-admin.sharepoint.com -UseWebLogin
```

<span data-ttu-id="148ad-365">Gebruik nu de cmdlet **Get-PnPTenantCdnEnabled** om de CDN-statusinstellingen van de Tenant op te halen:</span><span class="sxs-lookup"><span data-stu-id="148ad-365">Now use the **Get-PnPTenantCdnEnabled** cmdlet to retrieve the CDN status settings from the tenant:</span></span>

``` powershell
Get-PnPTenantCdnEnabled -CdnType <Public | Private>
```

<span data-ttu-id="148ad-366">De status van de CDN voor het opgegeven CdnType wordt uitgevoerd naar het scherm.</span><span class="sxs-lookup"><span data-stu-id="148ad-366">The status of the CDN for the specified CdnType will output to the screen.</span></span>

<span data-ttu-id="148ad-367">Gebruik de cmdlet **set-PnPTenantCdnEnabled** om uw organisatie de mogelijkheid Office 365 CDN te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="148ad-367">Use the **Set-PnPTenantCdnEnabled** cmdlet to enable your organization to use the Office 365 CDN.</span></span> <span data-ttu-id="148ad-368">U kunt instellen dat uw organisatie openbare Origins, persoonlijke oorsprong of beide tegelijkertijd kan gebruiken.</span><span class="sxs-lookup"><span data-stu-id="148ad-368">You can enable your organization to use public origins, private origins, or both at at the same time.</span></span> <span data-ttu-id="148ad-369">U kunt de CDN ook configureren om de instelling van standaardoorsprong te negeren wanneer u deze inschakelt.</span><span class="sxs-lookup"><span data-stu-id="148ad-369">You can also configure the CDN to skip the setup of default origins when you enable it.</span></span> <span data-ttu-id="148ad-370">U kunt deze oorsprong altijd later toevoegen, zoals beschreven in dit onderwerp.</span><span class="sxs-lookup"><span data-stu-id="148ad-370">You can always add these origins later as described in this topic.</span></span>
  
<span data-ttu-id="148ad-371">In PnP PowerShell:</span><span class="sxs-lookup"><span data-stu-id="148ad-371">In PnP PowerShell:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

<span data-ttu-id="148ad-372">Als u bijvoorbeeld wilt dat uw organisatie zowel openbare als persoonlijke oorsprong kan gebruiken, typt u de volgende opdracht:</span><span class="sxs-lookup"><span data-stu-id="148ad-372">For example, to enable your organization to use both public and private origins, type the following command:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true
```

<span data-ttu-id="148ad-373">Als u wilt dat uw organisatie zowel openbare als persoonlijke Origins kan gebruiken, maar de instelling van de standaardoorsprong gaat negeren, typt u de volgende opdracht:</span><span class="sxs-lookup"><span data-stu-id="148ad-373">To enable your organization to use both public and private origins but skip setting up the default origins, type the following command:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

<span data-ttu-id="148ad-374">Zie [standaard CDN-oorsprong](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) voor informatie over de oorsprong die standaard wordt ingericht wanneer u Office 365 CDN inschakelt en de mogelijkheid om de instelling van standaardoorsprong over te slaan.</span><span class="sxs-lookup"><span data-stu-id="148ad-374">See [Default CDN origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) for information about the origins that are provisioned by default when you enable the Office 365 CDN, and the potential impact of skipping the setup of default origins.</span></span>

<span data-ttu-id="148ad-375">Als u wilt dat uw organisatie gebruik kan maken van openbare oorsprong, typt u de volgende opdracht:</span><span class="sxs-lookup"><span data-stu-id="148ad-375">To enable your organization to use public origins, type the following command:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $true
```

<span data-ttu-id="148ad-376">Als u wilt dat uw organisatie gebruik kan maken van persoonlijke oorsprong, typt u de volgende opdracht:</span><span class="sxs-lookup"><span data-stu-id="148ad-376">To enable your organization to use private origins, type the following command:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $true
```

<span data-ttu-id="148ad-377">Zie [set-PnPTenantCdnEnabled](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled)voor meer informatie over deze cmdlet.</span><span class="sxs-lookup"><span data-stu-id="148ad-377">For more information about this cmdlet, see [Set-PnPTenantCdnEnabled](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled).</span></span>

<span data-ttu-id="148ad-378"><a name="Office365CDNforPnPPoshFileType"> </a></span><span class="sxs-lookup"><span data-stu-id="148ad-378"><a name="Office365CDNforPnPPoshFileType"> </a></span></span>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a><span data-ttu-id="148ad-379">De lijst met bestandstypen wijzigen die moeten worden opgenomen in het Office 365 CDN (optioneel)</span><span class="sxs-lookup"><span data-stu-id="148ad-379">Change the list of file types to include in the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="148ad-380">Wanneer u bestandstypen definieert met behulp van de cmdlet **set-PnPTenantCdnPolicy** , wordt de momenteel gedefinieerde lijst overschreven.</span><span class="sxs-lookup"><span data-stu-id="148ad-380">When you define file types by using the **Set-PnPTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="148ad-381">Als u extra bestandstypen aan de lijst wilt toevoegen, gebruikt u de cmdlet eerst om erachter te komen welke bestandstypen al zijn toegestaan en voegt u ze toe aan de lijst samen met uw nieuwe.</span><span class="sxs-lookup"><span data-stu-id="148ad-381">If you want to add additional file types to the list, use the cmdlet first to find out what file types are already allowed and include them in the list along with your new ones.</span></span>
  
<span data-ttu-id="148ad-382">Met de cmdlet **set-PnPTenantCdnPolicy** kunt u statische bestandstypen definiëren die worden gehost door openbare en persoonlijke Origins in het CDN.</span><span class="sxs-lookup"><span data-stu-id="148ad-382">Use the **Set-PnPTenantCdnPolicy** cmdlet to define static file types that can be hosted by public and private origins in the CDN.</span></span> <span data-ttu-id="148ad-383">Veelgebruikte activatypen zijn standaard toegestaan, bijvoorbeeld. CSS,. GIF,. jpg en. js.</span><span class="sxs-lookup"><span data-stu-id="148ad-383">By default, common asset types are allowed, for example .css, .gif, .jpg, and .js.</span></span>

<span data-ttu-id="148ad-384">In PnP PowerShell:</span><span class="sxs-lookup"><span data-stu-id="148ad-384">In PnP PowerShell:</span></span>

``` powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

<span data-ttu-id="148ad-385">Als u bijvoorbeeld de CDN wilt inschakelen voor host. CSS-en PNG-bestanden, typt u de volgende opdracht:</span><span class="sxs-lookup"><span data-stu-id="148ad-385">For example, to enable the CDN to host .css and .png files, you would enter the command:</span></span>

``` powershell
Set-PnPTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

<span data-ttu-id="148ad-386">Gebruik de cmdlet **Get-PnPTenantCdnPolicies** om te zien welke bestandstypen momenteel zijn toegestaan in het CDN.</span><span class="sxs-lookup"><span data-stu-id="148ad-386">To see what file types are currently allowed by the CDN, use the **Get-PnPTenantCdnPolicies** cmdlet:</span></span>

``` powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="148ad-387">Zie [set-PnPTenantCdnPolicy](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) en [Get-PnPTenantCdnPolicies](https://docs.microsoft.com/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies)voor meer informatie over deze cmdlets.</span><span class="sxs-lookup"><span data-stu-id="148ad-387">For more information about these cmdlets, see [Set-PnPTenantCdnPolicy](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) and [Get-PnPTenantCdnPolicies](https://docs.microsoft.com/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).</span></span>

<span data-ttu-id="148ad-388"><a name="Office365CDNforPnPPoshSiteClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="148ad-388"><a name="Office365CDNforPnPPoshSiteClassification"> </a></span></span>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a><span data-ttu-id="148ad-389">De lijst met site classificaties wijzigen die u wilt uitsluiten van Office 365 CDN (optioneel)</span><span class="sxs-lookup"><span data-stu-id="148ad-389">Change the list of site classifications you want to exclude from the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="148ad-390">Wanneer u site classificaties uitsluit met behulp van de cmdlet **set-PnPTenantCdnPolicy** , wordt de momenteel gedefinieerde lijst overschreven.</span><span class="sxs-lookup"><span data-stu-id="148ad-390">When you exclude site classifications by using the **Set-PnPTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="148ad-391">Als u extra site classificaties wilt uitsluiten, gebruikt u de cmdlet eerst om erachter te komen welke classificaties al zijn uitgesloten en voegt u ze vervolgens samen met uw nieuwe.</span><span class="sxs-lookup"><span data-stu-id="148ad-391">If you want to exclude additional site classifications, use the cmdlet first to find out what classifications are already excluded and then add them along with your new ones.</span></span>

<span data-ttu-id="148ad-392">Met de cmdlet **set-PnPTenantCdnPolicy** kunt u de site classificaties uitsluiten die u niet beschikbaar wilt maken via het CDN.</span><span class="sxs-lookup"><span data-stu-id="148ad-392">Use the **Set-PnPTenantCdnPolicy** cmdlet to exclude site classifications that you do not want to make available over the CDN.</span></span> <span data-ttu-id="148ad-393">Standaard zijn geen site classificaties uitgesloten.</span><span class="sxs-lookup"><span data-stu-id="148ad-393">By default, no site classifications are excluded.</span></span>

<span data-ttu-id="148ad-394">In PnP PowerShell:</span><span class="sxs-lookup"><span data-stu-id="148ad-394">In PnP PowerShell:</span></span>

``` powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications>"
```

<span data-ttu-id="148ad-395">Gebruik de cmdlet **Get-PnPTenantCdnPolicies** om te zien welke site classificaties momenteel zijn toegestaan.</span><span class="sxs-lookup"><span data-stu-id="148ad-395">To see what site classifications are currently restricted, use the **Get-PnPTenantCdnPolicies** cmdlet:</span></span>

``` powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="148ad-396">De eigenschappen die worden geretourneerd, zijn _IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ en _ExcludeIfNoScriptDisabled_.</span><span class="sxs-lookup"><span data-stu-id="148ad-396">The properties that will be returned are _IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ and _ExcludeIfNoScriptDisabled_.</span></span>

<span data-ttu-id="148ad-397">De eigenschap _IncludeFileExtensions_ bevat de lijst met bestandsextensies die vanuit het CDN worden bediend.</span><span class="sxs-lookup"><span data-stu-id="148ad-397">The _IncludeFileExtensions_ property contains the list of file extensions that will be served from the CDN.</span></span>

> [!NOTE]
> <span data-ttu-id="148ad-398">De standaardbestandsextensies verschillen tussen openbare en persoonlijke bestanden.</span><span class="sxs-lookup"><span data-stu-id="148ad-398">The default file extensions are different between public and private.</span></span>

<span data-ttu-id="148ad-399">De eigenschap _ExcludeRestrictedSiteClassifications_ bevat de site classificaties die u wilt uitsluiten van het CDN.</span><span class="sxs-lookup"><span data-stu-id="148ad-399">The _ExcludeRestrictedSiteClassifications_ property contains the site classifications that you want to exclude from the CDN.</span></span> <span data-ttu-id="148ad-400">U kunt bijvoorbeeld sites die als **vertrouwelijk** zijn gemarkeerd, uitsluiten, zodat de inhoud van sites met die classificatie niet via het CDN wordt verzonden.</span><span class="sxs-lookup"><span data-stu-id="148ad-400">For example, you can exclude sites marked as **Confidential** so content from sites with that classification applied will not be served from the CDN.</span></span>

<span data-ttu-id="148ad-401">De eigenschap _ExcludeIfNoScriptDisabled_ uitsluiten de inhoud van de CDN op basis van de instellingen van het _NoScript_ op siteniveau.</span><span class="sxs-lookup"><span data-stu-id="148ad-401">The _ExcludeIfNoScriptDisabled_ property excludes content from the CDN based on the site-level _NoScript_ attribute settings.</span></span> <span data-ttu-id="148ad-402">Het kenmerk _NoScript_ is standaard ingesteld op **beschikbaar** voor _moderne_ sites en **uitgeschakeld** voor _klassieke_ sites.</span><span class="sxs-lookup"><span data-stu-id="148ad-402">By default, the _NoScript_ attribute is set to **Enabled** for _Modern_ sites and **Disabled** for _Classic_ sites.</span></span> <span data-ttu-id="148ad-403">Dit hangt af van uw tenantinstellingen.</span><span class="sxs-lookup"><span data-stu-id="148ad-403">This depends on your tenant settings.</span></span>

<span data-ttu-id="148ad-404">Zie [set-PnPTenantCdnPolicy](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) en [Get-PnPTenantCdnPolicies](https://docs.microsoft.com/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies)voor meer informatie over deze cmdlets.</span><span class="sxs-lookup"><span data-stu-id="148ad-404">For more information about these cmdlets, see [Set-PnPTenantCdnPolicy](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) and [Get-PnPTenantCdnPolicies](https://docs.microsoft.com/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).</span></span>

<span data-ttu-id="148ad-405"><a name="Office365CDNforSPOOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="148ad-405"><a name="Office365CDNforSPOOriginPnPPosh"> </a></span></span>
### <a name="add-an-origin-for-your-assets"></a><span data-ttu-id="148ad-406">Een oorsprong voor uw activa toevoegen</span><span class="sxs-lookup"><span data-stu-id="148ad-406">Add an origin for your assets</span></span>

<span data-ttu-id="148ad-407">Met de cmdlet **add-PnPTenantCdnOrigin** kunt u een oorsprong definiëren.</span><span class="sxs-lookup"><span data-stu-id="148ad-407">Use the **Add-PnPTenantCdnOrigin** cmdlet to define an origin.</span></span> <span data-ttu-id="148ad-408">U kunt meerdere oorsprong definiëren.</span><span class="sxs-lookup"><span data-stu-id="148ad-408">You can define multiple origins.</span></span> <span data-ttu-id="148ad-409">De origin is een URL die verwijst naar een SharePoint-bibliotheek of-map die de assets bevat die u wilt hosten door de CDN.</span><span class="sxs-lookup"><span data-stu-id="148ad-409">The origin is a URL that points to a SharePoint library or folder that contains the assets that you want to be hosted by the CDN.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="148ad-410">U dient nooit bronnen te plaatsen die gebruikersgegevens bevatten of die in een openbare Origin als vertrouwelijk worden beschouwd.</span><span class="sxs-lookup"><span data-stu-id="148ad-410">You should never place resources that contain user information or are considered sensitive to your organization in a public origin.</span></span>

``` powershell
Add-PnPTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

<span data-ttu-id="148ad-411">De waarde van _pad_ is het relatieve pad naar de bibliotheek of map met de assets.</span><span class="sxs-lookup"><span data-stu-id="148ad-411">The value of _path_ is the relative path to the library or folder that contains the assets.</span></span> <span data-ttu-id="148ad-412">U kunt jokertekens gebruiken in aanvulling op relatieve paden.</span><span class="sxs-lookup"><span data-stu-id="148ad-412">You can use wildcards in addition to relative paths.</span></span> <span data-ttu-id="148ad-413">Voor de URL worden jokertekens ondersteund.</span><span class="sxs-lookup"><span data-stu-id="148ad-413">Origins support wildcards prepended to the URL.</span></span> <span data-ttu-id="148ad-414">Hiermee kunt u oorsprong maken die meerdere sites beslaat.</span><span class="sxs-lookup"><span data-stu-id="148ad-414">This allows you to create origins that span multiple sites.</span></span> <span data-ttu-id="148ad-415">Als u bijvoorbeeld alle activa in de map # # # # # # # # # # # # # # # # wilt opnemen in het CDN, typt u de volgende opdracht:</span><span class="sxs-lookup"><span data-stu-id="148ad-415">For example, to include all of the assets in the masterpages folder for all of your sites as a public origin within the CDN, type the following command:</span></span>

``` powershell
Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ <span data-ttu-id="148ad-416">De wijziging van het jokerteken \* **/** kan alleen aan het begin van het pad worden gebruikt en komt overeen met alle URL-segmenten onder de opgegeven URL.</span><span class="sxs-lookup"><span data-stu-id="148ad-416">The wildcard modifier \***/** can only be used at the beginning of the path, and will match all URL segments under the specified URL.</span></span>
+ <span data-ttu-id="148ad-417">Het pad kan verwijzen naar een documentbibliotheek, map of site.</span><span class="sxs-lookup"><span data-stu-id="148ad-417">The path can point to a document library, folder or site.</span></span> <span data-ttu-id="148ad-418">Het pad _\*/site1_ komt bijvoorbeeld overeen met alle documentbibliotheken onder de site.</span><span class="sxs-lookup"><span data-stu-id="148ad-418">For example, the path _\*/site1_ will match all the document libraries under the site.</span></span>

<span data-ttu-id="148ad-419">U kunt een oorsprong met een specifiek relatief pad toevoegen.</span><span class="sxs-lookup"><span data-stu-id="148ad-419">You can add an origin with a specific relative path.</span></span> <span data-ttu-id="148ad-420">U kunt geen origin toevoegen met het volledige pad.</span><span class="sxs-lookup"><span data-stu-id="148ad-420">You cannot add an origin using the full path.</span></span>

<span data-ttu-id="148ad-421">In dit voorbeeld wordt de persoonlijke oorsprong van de bibliotheek siteactiva op een specifieke site toegevoegd:</span><span class="sxs-lookup"><span data-stu-id="148ad-421">This example adds a private origin of the site assets library on a specific site:</span></span>

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="148ad-422">In dit voorbeeld wordt een persoonlijke oorsprong van de map _Map1_ toegevoegd aan de bibliotheek siteactiva van de siteverzameling:</span><span class="sxs-lookup"><span data-stu-id="148ad-422">This example adds a private origin of the _folder1_ folder in the site collection's site assets library:</span></span>

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

<span data-ttu-id="148ad-423">Als het pad een spatie bevat, kunt u het pad tussen dubbele aanhalingstekens plaatsen of de ruimte vervangen door de URL-codering %20.</span><span class="sxs-lookup"><span data-stu-id="148ad-423">If there is a space in the path, you can either surround the path in double quotes or replace the space with the URL encoding %20.</span></span> <span data-ttu-id="148ad-424">In het volgende voorbeeld wordt een persoonlijke oorsprong van de map _map 1_ toegevoegd aan de bibliotheek siteactiva van de siteverzameling:</span><span class="sxs-lookup"><span data-stu-id="148ad-424">The following examples add a private origin of the _folder 1_ folder in the site collection's site assets library:</span></span>

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

<span data-ttu-id="148ad-425">Zie [add-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)voor meer informatie over deze opdracht en de syntaxis.</span><span class="sxs-lookup"><span data-stu-id="148ad-425">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>

> [!NOTE]
> <span data-ttu-id="148ad-426">Bij particuliere Origin moet de activa die vanaf een oorsprong worden gedeeld, een primaire versie hebben gepubliceerd voordat ze toegankelijk zijn vanuit het CDN.</span><span class="sxs-lookup"><span data-stu-id="148ad-426">In private origins, assets being shared from an origin must have a major version published before they can be accessed from the CDN.</span></span>
  
<span data-ttu-id="148ad-427">Wanneer u de opdracht hebt uitgevoerd, wordt de configuratie door het systeem gesynchroniseerd via het datacenter.</span><span class="sxs-lookup"><span data-stu-id="148ad-427">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="148ad-428">Dit kan 15 minuten duren.</span><span class="sxs-lookup"><span data-stu-id="148ad-428">This can take up to 15 minutes.</span></span>

<span data-ttu-id="148ad-429"><a name="ExamplePublicOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="148ad-429"><a name="ExamplePublicOriginPnPPosh"> </a></span></span>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a><span data-ttu-id="148ad-430">Voorbeeld: een openbare Origin configureren voor uw basispagina's en voor de stijlbibliotheek voor SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="148ad-430">Example: Configure a public origin for your master pages and for your style library for SharePoint Online</span></span>

<span data-ttu-id="148ad-431">Normaalgesproken zijn deze oorsprong voor u standaard ingesteld wanneer u Office 365 CDN inschakelt.</span><span class="sxs-lookup"><span data-stu-id="148ad-431">Normally, these origins are set up for you by default when you enable the Office 365 CDN.</span></span> <span data-ttu-id="148ad-432">Voer de volgende stappen uit als u deze handmatig wilt inschakelen.</span><span class="sxs-lookup"><span data-stu-id="148ad-432">However, if you want to enable them manually, follow these steps.</span></span>
  
+ <span data-ttu-id="148ad-433">Met de cmdlet **add-PnPTenantCdnOrigin** kunt u de stijlbibliotheek definiëren als een openbare Origin.</span><span class="sxs-lookup"><span data-stu-id="148ad-433">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the style library as a public origin.</span></span>

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ <span data-ttu-id="148ad-434">Met de cmdlet **add-PnPTenantCdnOrigin** kunt u de basispagina's definiëren als een openbare Origin.</span><span class="sxs-lookup"><span data-stu-id="148ad-434">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the master pages as a public origin.</span></span>

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

<span data-ttu-id="148ad-435">Zie [add-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)voor meer informatie over deze opdracht en de syntaxis.</span><span class="sxs-lookup"><span data-stu-id="148ad-435">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>

<span data-ttu-id="148ad-436">Wanneer u de opdracht hebt uitgevoerd, wordt de configuratie door het systeem gesynchroniseerd via het datacenter.</span><span class="sxs-lookup"><span data-stu-id="148ad-436">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="148ad-437">Dit kan 15 minuten duren.</span><span class="sxs-lookup"><span data-stu-id="148ad-437">This can take up to 15 minutes.</span></span>

<span data-ttu-id="148ad-438"><a name="ExamplePrivateOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="148ad-438"><a name="ExamplePrivateOriginPnPPosh"> </a></span></span>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a><span data-ttu-id="148ad-439">Voorbeeld: een persoonlijke Origin configureren voor uw site-assets, sitepagina's en publicatie afbeeldingen voor SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="148ad-439">Example: Configure a private origin for your site assets, site pages, and publishing images for SharePoint Online</span></span>

+ <span data-ttu-id="148ad-440">Met de cmdlet **add-PnPTenantCdnOrigin** kunt u de map siteactiva definiëren als persoonlijke Origin.</span><span class="sxs-lookup"><span data-stu-id="148ad-440">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the site assets folder as a private origin.</span></span>

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ <span data-ttu-id="148ad-441">Met de cmdlet **add-PnPTenantCdnOrigin** kunt u de map sitepagina's definiëren als persoonlijke Origin.</span><span class="sxs-lookup"><span data-stu-id="148ad-441">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the site pages folder as a private origin.</span></span>

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ <span data-ttu-id="148ad-442">Met de cmdlet **add-PnPTenantCdnOrigin** kunt u de map met publicatie-afbeeldingen definiëren als persoonlijke Origin.</span><span class="sxs-lookup"><span data-stu-id="148ad-442">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the publishing images folder as a private origin.</span></span>

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

<span data-ttu-id="148ad-443">Zie [add-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)voor meer informatie over deze opdracht en de syntaxis.</span><span class="sxs-lookup"><span data-stu-id="148ad-443">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>

<span data-ttu-id="148ad-444">Wanneer u de opdracht hebt uitgevoerd, wordt de configuratie door het systeem gesynchroniseerd via het datacenter.</span><span class="sxs-lookup"><span data-stu-id="148ad-444">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="148ad-445">Dit kan 15 minuten duren.</span><span class="sxs-lookup"><span data-stu-id="148ad-445">This can take up to 15 minutes.</span></span>

<span data-ttu-id="148ad-446"><a name="ExamplePrivateOriginSiteCollectionPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="148ad-446"><a name="ExamplePrivateOriginSiteCollectionPnPPosh"> </a></span></span>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a><span data-ttu-id="148ad-447">Voorbeeld: een persoonlijke Origin configureren voor een siteverzameling voor SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="148ad-447">Example: Configure a private origin for a site collection for SharePoint Online</span></span>

<span data-ttu-id="148ad-448">Met de cmdlet **add-PnPTenantCdnOrigin** kunt u een siteverzameling als persoonlijke Origin definiëren.</span><span class="sxs-lookup"><span data-stu-id="148ad-448">Use the **Add-PnPTenantCdnOrigin** cmdlet to define a site collection as a private origin.</span></span> <span data-ttu-id="148ad-449">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="148ad-449">For example:</span></span>

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="148ad-450">Zie [add-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)voor meer informatie over deze opdracht en de syntaxis.</span><span class="sxs-lookup"><span data-stu-id="148ad-450">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>
  
<span data-ttu-id="148ad-451">Wanneer u de opdracht hebt uitgevoerd, wordt de configuratie door het systeem gesynchroniseerd via het datacenter.</span><span class="sxs-lookup"><span data-stu-id="148ad-451">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="148ad-452">U ziet mogelijk een bericht _in behandeling_ waarvan de status van de SharePoint Online-Tenant wordt verwacht, zodat deze verbinding maakt met de CDN-service.</span><span class="sxs-lookup"><span data-stu-id="148ad-452">You may see a _Configuration pending_ message which is expected as the SharePoint Online tenant connects to the CDN service.</span></span> <span data-ttu-id="148ad-453">Dit kan 15 minuten duren.</span><span class="sxs-lookup"><span data-stu-id="148ad-453">This can take up to 15 minutes.</span></span>

<span data-ttu-id="148ad-454"><a name="CDNManagePnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="148ad-454"><a name="CDNManagePnPPosh"> </a></span></span>
### <a name="manage-the-office-365-cdn"></a><span data-ttu-id="148ad-455">Het Office 365-CDN beheren</span><span class="sxs-lookup"><span data-stu-id="148ad-455">Manage the Office 365 CDN</span></span>

<span data-ttu-id="148ad-456">Wanneer u de CDN hebt ingesteld, kunt u wijzigingen aanbrengen in de configuratie wanneer u inhoud bijwerkt of de gewenste wijziging aanbrengt, zoals in deze sectie wordt beschreven.</span><span class="sxs-lookup"><span data-stu-id="148ad-456">Once you've set up the CDN, you can make changes to your configuration as you update content or as your needs change, as described in this section.</span></span>
  
<span data-ttu-id="148ad-457"><a name="Office365CDNforSPOaddremoveassetPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="148ad-457"><a name="Office365CDNforSPOaddremoveassetPnPPosh"> </a></span></span>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a><span data-ttu-id="148ad-458">Bronnen toevoegen, bijwerken of verwijderen uit het Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="148ad-458">Add, update, or remove assets from the Office 365 CDN</span></span>

<span data-ttu-id="148ad-459">Wanneer u de instellingsstappen hebt voltooid, kunt u nieuwe activa toevoegen en bestaande activa bijwerken of verwijderen wanneer u maar wilt.</span><span class="sxs-lookup"><span data-stu-id="148ad-459">Once you've completed the setup steps, you can add new assets, and update or remove existing assets whenever you want.</span></span> <span data-ttu-id="148ad-460">Breng de gewenste wijzigingen aan in de activa in de map of in de SharePoint-bibliotheek die u als een oorsprong hebt aangewezen.</span><span class="sxs-lookup"><span data-stu-id="148ad-460">Just make your changes to the assets in the folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="148ad-461">Als u een nieuw activum toevoegt, is het direct beschikbaar via het CDN.</span><span class="sxs-lookup"><span data-stu-id="148ad-461">If you add a new asset, it is available through the CDN immediately.</span></span> <span data-ttu-id="148ad-462">Als u echter het activum bijwerkt, duurt het maximaal vijftien minuten voordat de nieuwe versie beschikbaar is in het CDN.</span><span class="sxs-lookup"><span data-stu-id="148ad-462">However, if you update the asset, it will take up to 15 minutes for the new copy to propagate and become available in the CDN.</span></span>
  
<span data-ttu-id="148ad-463">Als u de locatie van de origin moet ophalen, kunt u de cmdlet **Get-PnPTenantCdnOrigin** gebruiken.</span><span class="sxs-lookup"><span data-stu-id="148ad-463">If you need to retrieve the location of the origin, you can use the **Get-PnPTenantCdnOrigin** cmdlet.</span></span> <span data-ttu-id="148ad-464">Zie [Get-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/get-pnptenantcdnorigin)voor informatie over het gebruik van deze cmdlet.</span><span class="sxs-lookup"><span data-stu-id="148ad-464">For information on how to use this cmdlet, see [Get-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/get-pnptenantcdnorigin).</span></span>

<span data-ttu-id="148ad-465"><a name="Office365CDNforSPORemoveOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="148ad-465"><a name="Office365CDNforSPORemoveOriginPnPPosh"> </a></span></span>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a><span data-ttu-id="148ad-466">Een oorsprong uit Office 365 CDN verwijderen</span><span class="sxs-lookup"><span data-stu-id="148ad-466">Remove an origin from the Office 365 CDN</span></span>

<span data-ttu-id="148ad-467">U kunt de toegang tot een map of een SharePoint-bibliotheek die u als een oorsprong hebt opgegeven, verwijderen.</span><span class="sxs-lookup"><span data-stu-id="148ad-467">You can remove access to a folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="148ad-468">U kunt dit doen met behulp van de **Remove-PnPTenantCdnOrigin-** cmdlet.</span><span class="sxs-lookup"><span data-stu-id="148ad-468">To do this, use the **Remove-PnPTenantCdnOrigin** cmdlet.</span></span>

``` powershell
Remove-PnPTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

<span data-ttu-id="148ad-469">Zie [Remove-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/remove-pnptenantcdnorigin)voor informatie over het gebruik van deze cmdlet.</span><span class="sxs-lookup"><span data-stu-id="148ad-469">For information on how to use this cmdlet, see [Remove-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/remove-pnptenantcdnorigin).</span></span>

<span data-ttu-id="148ad-470"><a name="Office365CDNforSPOModifyOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="148ad-470"><a name="Office365CDNforSPOModifyOriginPnPPosh"> </a></span></span>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a><span data-ttu-id="148ad-471">Een origin in het Office 365-CDN wijzigen</span><span class="sxs-lookup"><span data-stu-id="148ad-471">Modify an origin in the Office 365 CDN</span></span>

<span data-ttu-id="148ad-472">U kunt geen Origin wijzigen die u hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="148ad-472">You cannot modify an origin you've created.</span></span> <span data-ttu-id="148ad-473">In plaats daarvan verwijdert u de oorsprong en voegt u een nieuwe toe.</span><span class="sxs-lookup"><span data-stu-id="148ad-473">Instead, remove the origin and then add a new one.</span></span> <span data-ttu-id="148ad-474">Zie voor meer informatie [een origin verwijderen uit het Office 365 CDN](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPnPPosh) en [een origin voor uw assets toevoegen](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPnPPosh).</span><span class="sxs-lookup"><span data-stu-id="148ad-474">For more information, see [To remove an origin from the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPnPPosh) and [To add an origin for your assets](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPnPPosh).</span></span>

<span data-ttu-id="148ad-475"><a name="Office365CDNforSPODisable"> </a></span><span class="sxs-lookup"><span data-stu-id="148ad-475"><a name="Office365CDNforSPODisable"> </a></span></span>
#### <a name="disable-the-office-365-cdn"></a><span data-ttu-id="148ad-476">Het Office 365-CDN uitschakelen</span><span class="sxs-lookup"><span data-stu-id="148ad-476">Disable the Office 365 CDN</span></span>

<span data-ttu-id="148ad-477">Gebruik de cmdlet **set-PnPTenantCdnEnabled** om de CDN uit te schakelen voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="148ad-477">Use the **Set-PnPTenantCdnEnabled** cmdlet to disable the CDN for your organization.</span></span> <span data-ttu-id="148ad-478">Als u zowel openbare als persoonlijke Origins voor het CDN hebt ingeschakeld, moet u de cmdlet twee keer uitvoeren, zoals in de volgende voorbeelden wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="148ad-478">If you have both the public and private origins enabled for the CDN, you need to run the cmdlet twice as shown in the following examples.</span></span>
  
<span data-ttu-id="148ad-479">Als u het gebruik van openbare Origins in het CDN wilt uitschakelen, voert u de volgende opdracht in:</span><span class="sxs-lookup"><span data-stu-id="148ad-479">To disable use of public origins in the CDN, enter the following command:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $false
```

<span data-ttu-id="148ad-480">Als u het gebruik van de persoonlijke Origins in het CDN wilt uitschakelen, voert u de volgende opdracht in:</span><span class="sxs-lookup"><span data-stu-id="148ad-480">To disable use of the private origins in the CDN, enter the following command:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $false
```

<span data-ttu-id="148ad-481">Zie [set-PnPTenantCdnEnabled](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled)voor meer informatie over deze cmdlet.</span><span class="sxs-lookup"><span data-stu-id="148ad-481">For more information about this cmdlet, see [Set-PnPTenantCdnEnabled](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled).</span></span>

</details>

<span data-ttu-id="148ad-482"><a name="CDNSetupinCLI"> </a></span><span class="sxs-lookup"><span data-stu-id="148ad-482"><a name="CDNSetupinCLI"> </a></span></span>
## <a name="set-up-and-configure-the-office-365-cdn-using-the-office-365-cli"></a><span data-ttu-id="148ad-483">Het Office 365 CDN instellen en configureren met behulp van Office 365 CLI</span><span class="sxs-lookup"><span data-stu-id="148ad-483">Set up and configure the Office 365 CDN using the Office 365 CLI</span></span>

<span data-ttu-id="148ad-484">Voor de procedures in deze sectie moet u [Office 365 cli](https://aka.ms/o365cli)hebben geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="148ad-484">The procedures in this section require that you have installed the [Office 365 CLI](https://aka.ms/o365cli).</span></span> <span data-ttu-id="148ad-485">Maak vervolgens verbinding met de Office 365-Tenant met behulp van de opdracht [login](https://pnp.github.io/office365-cli/cmd/login/) .</span><span class="sxs-lookup"><span data-stu-id="148ad-485">Next, connect to your Office 365 tenant using the [login](https://pnp.github.io/office365-cli/cmd/login/) command.</span></span>

<span data-ttu-id="148ad-486">Voer de volgende stappen uit om de CDN in te stellen en te configureren voor het hosten van uw assets in SharePoint Online met behulp van Office 365 CLI.</span><span class="sxs-lookup"><span data-stu-id="148ad-486">Complete these steps to set up and configure the CDN to host your assets in SharePoint Online using the Office 365 CLI.</span></span>

<details>
  <summary><span data-ttu-id="148ad-487">Klik om uit te vouwen</span><span class="sxs-lookup"><span data-stu-id="148ad-487">Click to expand</span></span></summary>

### <a name="enable-the-office-365-cdn"></a><span data-ttu-id="148ad-488">Het Office 365 CDN inschakelen</span><span class="sxs-lookup"><span data-stu-id="148ad-488">Enable the Office 365 CDN</span></span>

<span data-ttu-id="148ad-489">U kunt de status van het Office 365 CDN in uw Tenant beheren met behulp van de CDN-opdracht [SPO](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-set/) .</span><span class="sxs-lookup"><span data-stu-id="148ad-489">You can manage the state of the Office 365 CDN in your tenant using the [spo cdn set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-set/) command.</span></span>

<span data-ttu-id="148ad-490">Als u het openbare CDN van Office 365 in uw Tenant wilt inschakelen, voert u het volgende uit:</span><span class="sxs-lookup"><span data-stu-id="148ad-490">To enable the Office 365 Public CDN in your tenant execute:</span></span>

```sh
spo cdn set --type Public --enabled true
```

<span data-ttu-id="148ad-491">Voer het volgende uit om het Office 365-CDN in te schakelen:</span><span class="sxs-lookup"><span data-stu-id="148ad-491">To enable the Office 365 SharePoint CDN, execute:</span></span>

```sh
spo cdn set --type Private --enabled true
```

#### <a name="view-the-current-status-of-the-office-365-cdn"></a><span data-ttu-id="148ad-492">De huidige status van het Office 365 CDN weergeven</span><span class="sxs-lookup"><span data-stu-id="148ad-492">View the current status of the Office 365 CDN</span></span>

<span data-ttu-id="148ad-493">Als u wilt controleren of het specifieke type van Office 365 CDN is ingeschakeld of uitgeschakeld, gebruikt u de opdracht [SPO CDN Get](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-get/) .</span><span class="sxs-lookup"><span data-stu-id="148ad-493">To check if the particular type of Office 365 CDN is enabled or disabled, use the [spo cdn get](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-get/) command.</span></span>

<span data-ttu-id="148ad-494">Voer het volgende uit om te controleren of het Office 365 openbare CDN is ingeschakeld:</span><span class="sxs-lookup"><span data-stu-id="148ad-494">To check if the Office 365 Public CDN is enabled, execute:</span></span>

```sh
spo cdn get --type Public
```

### <a name="view-the-office-365-cdn-origins"></a><span data-ttu-id="148ad-495">De Office 365 CDN-oorsprong weergeven</span><span class="sxs-lookup"><span data-stu-id="148ad-495">View the Office 365 CDN origins</span></span>

<span data-ttu-id="148ad-496">U kunt als volgt het momenteel geconfigureerde Office 365 openbare CDN-oorsprong uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="148ad-496">To view the currently configured Office 365 Public CDN origins execute:</span></span>

```sh
spo cdn origin list --type Public
```

<span data-ttu-id="148ad-497">Zie [standaard CDN-oorsprong](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) voor informatie over de oorsprong die standaard wordt ingericht wanneer u Office 365 CDN inschakelt.</span><span class="sxs-lookup"><span data-stu-id="148ad-497">See [Default CDN origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) for information about the origins that are provisioned by default when you enable the Office 365 CDN.</span></span>

### <a name="add-an-office-365-cdn-origin"></a><span data-ttu-id="148ad-498">Een Office 365 CDN-oorsprong toevoegen</span><span class="sxs-lookup"><span data-stu-id="148ad-498">Add an Office 365 CDN origin</span></span>

> [!IMPORTANT]
> <span data-ttu-id="148ad-499">U dient nooit bronnen te plaatsen die in een SharePoint-documentbibliotheek zijn geconfigureerd als een openbare Origin.</span><span class="sxs-lookup"><span data-stu-id="148ad-499">You should never place resources that are considered sensitive to your organization in a SharePoint document library configured as a public origin.</span></span>

<span data-ttu-id="148ad-500">Gebruik de opdracht [toevoegen van SPO CDN Origin](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-add/) voor het definiëren van een CDN-oorsprong.</span><span class="sxs-lookup"><span data-stu-id="148ad-500">Use the [spo cdn origin add](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-add/) command to define a CDN origin.</span></span> <span data-ttu-id="148ad-501">U kunt meerdere oorsprong definiëren.</span><span class="sxs-lookup"><span data-stu-id="148ad-501">You can define multiple origins.</span></span> <span data-ttu-id="148ad-502">De origin is een URL die verwijst naar een SharePoint-bibliotheek of-map die de assets bevat die u wilt hosten door de CDN.</span><span class="sxs-lookup"><span data-stu-id="148ad-502">The origin is a URL that points to a SharePoint library or folder that contains the assets that you want to be hosted by the CDN.</span></span>

```sh
spo cdn origin add --type [Public | Private] --origin <path>
```

<span data-ttu-id="148ad-503">Waar `path` is het relatieve pad naar de map die de elementen bevat.</span><span class="sxs-lookup"><span data-stu-id="148ad-503">Where `path` is the relative path to the folder that contains the assets.</span></span> <span data-ttu-id="148ad-504">U kunt jokertekens gebruiken in aanvulling op relatieve paden.</span><span class="sxs-lookup"><span data-stu-id="148ad-504">You can use wildcards in addition to relative paths.</span></span>

<span data-ttu-id="148ad-505">Als u alle activa in de **Galerie met basispagina's** van alle sites als een openbare Origin wilt opnemen, voert u het volgende uit:</span><span class="sxs-lookup"><span data-stu-id="148ad-505">To include all assets in the **Master Page Gallery** of all sites as a public origin, execute:</span></span>

```sh
spo cdn origin add --type Public --origin */masterpage
```

<span data-ttu-id="148ad-506">Voer het volgende uit om een persoonlijke Origin te configureren voor een bepaalde siteverzameling:</span><span class="sxs-lookup"><span data-stu-id="148ad-506">To configure a private origin for a specific site collection, execute:</span></span>

```sh
spo cdn origin add --type Private --origin sites/site1/siteassets
```

> [!NOTE]
> <span data-ttu-id="148ad-507">Na het toevoegen van een CDN-oorsprong kan het tot 15 minuten duren voordat u bestanden kunt ophalen via de CDN-service.</span><span class="sxs-lookup"><span data-stu-id="148ad-507">After adding a CDN origin, it might take up to 15 minutes for you to be able to retrieve files via the CDN service.</span></span> <span data-ttu-id="148ad-508">U kunt controleren of de bepaalde oorsprong al is ingeschakeld met de opdracht [SPO CDN Origin List](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) .</span><span class="sxs-lookup"><span data-stu-id="148ad-508">You can verify if the particular origin has already been enabled using the [spo cdn origin list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) command.</span></span>

### <a name="remove-an-office-365-cdn-origin"></a><span data-ttu-id="148ad-509">Een Office 365 CDN-oorsprong verwijderen</span><span class="sxs-lookup"><span data-stu-id="148ad-509">Remove an Office 365 CDN origin</span></span>

<span data-ttu-id="148ad-510">Met de opdracht [verwijderen van SPO CDN Origin Origin](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-remove/) verwijdert u een CDN-oorsprong voor het opgegeven CDN-type.</span><span class="sxs-lookup"><span data-stu-id="148ad-510">Use the [spo cdn origin remove](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-remove/) command to remove a CDN origin for the specified CDN type.</span></span>

<span data-ttu-id="148ad-511">Voer het volgende uit om een openbare Origin te verwijderen uit de CDN-configuratie:</span><span class="sxs-lookup"><span data-stu-id="148ad-511">To remove a public origin from the CDN configuration, execute:</span></span>

```sh
spo cdn origin remove --type Public --origin */masterpage
```

> [!NOTE]
> <span data-ttu-id="148ad-512">Het verwijderen van een CDN-oorsprong heeft geen invloed op de bestanden die zijn opgeslagen in een documentbibliotheek die overeenkomen met die waarvan de oorsprong</span><span class="sxs-lookup"><span data-stu-id="148ad-512">Removing a CDN origin doesn't affect the files stored in any document library matching that origin.</span></span> <span data-ttu-id="148ad-513">Als ernaar werd verwezen met de SharePoint-URL, wordt in SharePoint automatisch de oorspronkelijke URL weergegeven die verwijst naar de documentbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="148ad-513">If these assets have been referenced using their SharePoint URL, SharePoint will automatically switch back to the original URL pointing to the document library.</span></span> <span data-ttu-id="148ad-514">Als ernaar verwijste verwijzingen via een openbare CDN-URL, wordt de koppeling verbroken en moet u deze handmatig wijzigen.</span><span class="sxs-lookup"><span data-stu-id="148ad-514">If, however, assets have been referenced using a public CDN URL, then removing the origin will break the link and you will need to manually change them.</span></span>

### <a name="modify-an-office-365-cdn-origin"></a><span data-ttu-id="148ad-515">Een Office 365 CDN Origin wijzigen</span><span class="sxs-lookup"><span data-stu-id="148ad-515">Modify an Office 365 CDN origin</span></span>

<span data-ttu-id="148ad-516">Het is niet mogelijk om een bestaande CDN-oorsprong te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="148ad-516">It's not possible to modify an existing CDN origin.</span></span> <span data-ttu-id="148ad-517">In plaats daarvan dient u de eerder opgegeven CDN-oorsprong te verwijderen met de `spo cdn origin remove` opdracht en een nieuwe naam toe te voegen met de `spo cdn origin add` opdracht.</span><span class="sxs-lookup"><span data-stu-id="148ad-517">Instead, you should remove the previously defined CDN origin using the `spo cdn origin remove` command and add a new one using the `spo cdn origin add` command.</span></span>

### <a name="change-the-types-of-files-to-include-in-the-office-365-cdn"></a><span data-ttu-id="148ad-518">De bestandstypen wijzigen die u wilt opnemen in het Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="148ad-518">Change the types of files to include in the Office 365 CDN</span></span>

<span data-ttu-id="148ad-519">Standaard zijn de volgende bestandstypen opgenomen in de CDN: _. CSS,. EOT,. GIF,. ICO,. JPEG,. jpg,. js,. folder,. png,. js_,.</span><span class="sxs-lookup"><span data-stu-id="148ad-519">By default, the following file types are included in the CDN: _.css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff and .woff2_.</span></span> <span data-ttu-id="148ad-520">Als u extra bestandstypen in het CDN wilt opnemen, kunt u de CDN-configuratie wijzigen met de opdracht [SPO CDN-beleidsset](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) .</span><span class="sxs-lookup"><span data-stu-id="148ad-520">If you need to include additional file types in the CDN, you can change the CDN configuration using the [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) command.</span></span>

> [!NOTE]
> <span data-ttu-id="148ad-521">Wanneer u de lijst met bestandstypen wijzigt, overschrijft u de momenteel gedefinieerde lijst.</span><span class="sxs-lookup"><span data-stu-id="148ad-521">When changing the list of file types, you overwrite the currently defined list.</span></span> <span data-ttu-id="148ad-522">Als u extra bestandstypen wilt opnemen, gebruikt u eerst de opdracht [SPO CDN-beleidslijst](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) om erachter te komen welke bestandstypen momenteel zijn geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="148ad-522">If you want to include additional file types, first use the [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) command to find out which file types are currently configured.</span></span>

<span data-ttu-id="148ad-523">Voer de volgende stappen uit om het type _JSON_ -bestand toe te voegen aan de standaardlijst met bestandstypen die in het openbare CDN zijn opgenomen:</span><span class="sxs-lookup"><span data-stu-id="148ad-523">To add the _JSON_ file type to the default list of file types included in the public CDN, execute:</span></span>

```sh
spo cdn policy set --type Public --policy IncludeFileExtensions --value "CSS,EOT,GIF,ICO,JPEG,JPG,JS,MAP,PNG,SVG,TTF,WOFF,JSON"
```

### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn"></a><span data-ttu-id="148ad-524">De lijst met site classificaties wijzigen die u wilt uitsluiten van Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="148ad-524">Change the list of site classifications you want to exclude from the Office 365 CDN</span></span>

<span data-ttu-id="148ad-525">Met de opdracht [SPO CDN-beleidsinstelling](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) kunt u de site classificaties uitsluiten die u niet beschikbaar wilt maken in het CDN.</span><span class="sxs-lookup"><span data-stu-id="148ad-525">Use the [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) command to exclude site classifications that you do not want to make available over the CDN.</span></span> <span data-ttu-id="148ad-526">Standaard zijn geen site classificaties uitgesloten.</span><span class="sxs-lookup"><span data-stu-id="148ad-526">By default, no site classifications are excluded.</span></span>

> [!NOTE]
> <span data-ttu-id="148ad-527">Wanneer u de lijst met uitgesloten site classificaties wijzigt, overschrijft u de momenteel gedefinieerde lijst.</span><span class="sxs-lookup"><span data-stu-id="148ad-527">When changing the list of excluded site classifications, you overwrite the currently defined list.</span></span> <span data-ttu-id="148ad-528">Als u extra classificaties wilt uitsluiten, gebruikt u eerst de opdracht [SPO CDN-beleidslijst](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-list/) om erachter te komen welke indelingen zijn geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="148ad-528">If you want to exclude additional classifications, first use the [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-list/) command to find out which classifications are currently configured.</span></span>

<span data-ttu-id="148ad-529">Als u sites wilt uitsluiten die zijn geclassificeerd als _HBI_ uit het openbare CDN, voert u</span><span class="sxs-lookup"><span data-stu-id="148ad-529">To exclude sites classified as _HBI_ from the public CDN, execute</span></span>

```sh
spo cdn policy set --type Public --policy ExcludeRestrictedSiteClassifications --value "HBI"
```

### <a name="disable-the-office-365-cdn"></a><span data-ttu-id="148ad-530">Het Office 365-CDN uitschakelen</span><span class="sxs-lookup"><span data-stu-id="148ad-530">Disable the Office 365 CDN</span></span>

<span data-ttu-id="148ad-531">Als u het Office 365-CDN wilt uitschakelen, gebruikt u de volgende `spo cdn set` opdracht:</span><span class="sxs-lookup"><span data-stu-id="148ad-531">To disable the Office 365 CDN use the `spo cdn set` command, for example:</span></span>

```sh
spo cdn set --type Public --enabled false
```

</details>

## <a name="using-your-cdn-assets"></a><span data-ttu-id="148ad-532">Uw CDN-bronnen gebruiken</span><span class="sxs-lookup"><span data-stu-id="148ad-532">Using your CDN assets</span></span>

<span data-ttu-id="148ad-533">Nu u de CDN en de geconfigureerde oorsprong en beleidsregels hebt ingeschakeld, kunt u uw CDN-activa gaan gebruiken.</span><span class="sxs-lookup"><span data-stu-id="148ad-533">Now that you have enabled the CDN and configured origins and policies, you can begin using your CDN assets.</span></span>

<span data-ttu-id="148ad-534">In deze sectie vindt u meer informatie over het gebruik van CDN-Url's op uw SharePoint-pagina's en inhoud, zodat aanvragen voor assets in openbare en persoonlijke Origins worden doorgestuurd naar het CDN.</span><span class="sxs-lookup"><span data-stu-id="148ad-534">This section will help you understand how to use CDN URLs in your SharePoint pages and content so that SharePoint redirects requests for assets in both public and private origins to the CDN.</span></span>

+ [<span data-ttu-id="148ad-535">Koppelingen naar CDN-assets bijwerken</span><span class="sxs-lookup"><span data-stu-id="148ad-535">Updating links to CDN assets</span></span>](use-microsoft-365-cdn-with-spo.md#updating-links-to-cdn-assets)
+ [<span data-ttu-id="148ad-536">Activa gebruiken in openbare oorsprong</span><span class="sxs-lookup"><span data-stu-id="148ad-536">Using assets in public origins</span></span>](use-microsoft-365-cdn-with-spo.md#using-assets-in-public-origins)
+ [<span data-ttu-id="148ad-537">Werken met assets in persoonlijke oorsprong</span><span class="sxs-lookup"><span data-stu-id="148ad-537">Using assets in private origins</span></span>](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)

<span data-ttu-id="148ad-538">Voor informatie over het gebruik van het CDN voor het hosten van webonderdelen aan de clientzijde, raadpleegt u het onderwerp [uw webonderdeel op de client Toep kelen vanuit Office 365 CDN (Hallo wereld Part 4)](https://docs.microsoft.com/sharepoint/dev/spfx/web-parts/get-started/hosting-webpart-from-office-365-cdn).</span><span class="sxs-lookup"><span data-stu-id="148ad-538">For information on how to use the CDN for hosting client-side web parts, see the topic [Host your client-side web part from Office 365 CDN (Hello World part 4)](https://docs.microsoft.com/sharepoint/dev/spfx/web-parts/get-started/hosting-webpart-from-office-365-cdn).</span></span>

> [!NOTE]
> <span data-ttu-id="148ad-539">Als u de map _ClientSideAssets_ toevoegt aan de lijst met **persoonlijke** CDN-oorsprong, kunnen aangepaste webonderdelen met CDN-host niet worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="148ad-539">If you add the _ClientSideAssets_ folder to the **private** CDN origins list, CDN-hosted custom web parts will fail to render.</span></span> <span data-ttu-id="148ad-540">Bestanden die worden gebruikt door webonderdelen van SPFX kunnen alleen gebruikmaken van het openbare CDN en de map ClientSideAssets is een standaardoorsprong voor openbare CDN.</span><span class="sxs-lookup"><span data-stu-id="148ad-540">Files used by SPFX web parts can only utilize the public CDN and the ClientSideAssets folder is a default origin for public CDN.</span></span> 

### <a name="updating-links-to-cdn-assets"></a><span data-ttu-id="148ad-541">Koppelingen naar CDN-assets bijwerken</span><span class="sxs-lookup"><span data-stu-id="148ad-541">Updating links to CDN assets</span></span>

<span data-ttu-id="148ad-542">Als u assets wilt gebruiken die u hebt toegevoegd aan een oorsprong, moet u een koppeling naar het oorspronkelijke bestand bijwerken met het pad naar het bestand in de oorsprong.</span><span class="sxs-lookup"><span data-stu-id="148ad-542">To use assets that you have added to an origin, you simply update links to the original file with the path to the file in the origin.</span></span>

+ <span data-ttu-id="148ad-543">Bewerk de pagina of inhoud die koppelingen bevat naar activa die u hebt toegevoegd aan een oorsprong.</span><span class="sxs-lookup"><span data-stu-id="148ad-543">Edit the page or content that contains links to assets you have added to an origin.</span></span> <span data-ttu-id="148ad-544">U kunt ook een van de volgende methoden gebruiken om koppelingen te zoeken en te vervangen op een Enter-site of siteverzameling als u de koppeling naar een bepaald activum overal wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="148ad-544">You can also use one of several methods to globally search and replace links across an enter site or site collection if you want to update the link to a given asset everywhere it appears.</span></span>
+ <span data-ttu-id="148ad-545">Voor elke koppeling naar een activum in een oorsprong, vervangt u het pad door het pad naar het bestand in de CDN-oorsprong.</span><span class="sxs-lookup"><span data-stu-id="148ad-545">For each link to an asset in an origin, replace the path with the path to the file in the CDN origin.</span></span> <span data-ttu-id="148ad-546">U kunt relatieve paden gebruiken.</span><span class="sxs-lookup"><span data-stu-id="148ad-546">You can use relative paths.</span></span>
+ <span data-ttu-id="148ad-547">Sla de pagina of de inhoud op.</span><span class="sxs-lookup"><span data-stu-id="148ad-547">Save the page or content.</span></span>

<span data-ttu-id="148ad-548">Kijk bijvoorbeeld naar de afbeelding _/site/SiteAssets/images/image.png_die u hebt gekopieerd naar de map documentbibliotheek _/site/CDN_origins/Public/_.</span><span class="sxs-lookup"><span data-stu-id="148ad-548">For example, consider the image _/site/SiteAssets/images/image.png_, which you have copied to the document library folder _/site/CDN_origins/public/_.</span></span> <span data-ttu-id="148ad-549">Als u het CDN-activum wilt gebruiken, vervangt u het oorspronkelijke pad naar de locatie van het afbeeldingsbestand met het pad naar de oorsprong zodat u de nieuwe URL _/site/CDN_origins/public/image.png_.</span><span class="sxs-lookup"><span data-stu-id="148ad-549">To use the CDN asset, replace the original path to the image file location with the path to the origin to make the new URL _/site/CDN_origins/public/image.png_.</span></span>

<span data-ttu-id="148ad-550">Als u de volledige URL naar het activum wilt gebruiken in plaats van een relatief pad, maakt u de koppeling als volgt:</span><span class="sxs-lookup"><span data-stu-id="148ad-550">If you want to use the full URL to the asset instead of a relative path, construct the link like so:</span></span>

`https://<TenantHostName>.sharepoint.com/sites/site/CDN_origins/public/image.png`

> [!NOTE]
> <span data-ttu-id="148ad-551">In het algemeen is het niet mogelijk om de Url's rechtstreeks in het CDN te hardcode.</span><span class="sxs-lookup"><span data-stu-id="148ad-551">In general, you should not hardcode URLs directly to assets in the CDN.</span></span> <span data-ttu-id="148ad-552">U kunt echter handmatig Url's maken voor assets in openbare oorsprong.</span><span class="sxs-lookup"><span data-stu-id="148ad-552">However, you can manually construct URLs for assets in public origins if needed.</span></span> <span data-ttu-id="148ad-553">Zie voor meer informatie [HARDCODING CDN url's voor openbare assets](use-microsoft-365-cdn-with-spo.md#hardcoding-cdn-urls-for-public-assets).</span><span class="sxs-lookup"><span data-stu-id="148ad-553">For more information, see [Hardcoding CDN URLs for public assets](use-microsoft-365-cdn-with-spo.md#hardcoding-cdn-urls-for-public-assets).</span></span>

<span data-ttu-id="148ad-554">Als u wilt weten hoe u kunt controleren of de activa worden bediend via de CDN, raadpleegt u [Hoe kan ik controleren of de activa worden geleverd door de CDN?](use-microsoft-365-cdn-with-spo.md#CDNConfirm) in de sectie [problemen met Office 365 CDN oplossen](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting) .</span><span class="sxs-lookup"><span data-stu-id="148ad-554">To learn about how to verify that assets are being served from the CDN, see [How do I confirm that assets are being served by the CDN?](use-microsoft-365-cdn-with-spo.md#CDNConfirm) in the [Troubleshooting the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting) section.</span></span>

### <a name="using-assets-in-public-origins"></a><span data-ttu-id="148ad-555">Activa gebruiken in openbare oorsprong</span><span class="sxs-lookup"><span data-stu-id="148ad-555">Using assets in public origins</span></span>

<span data-ttu-id="148ad-556">Met de **functie publiceren** in SharePoint Online worden de url's van activa die in openbare Origin-Origins zijn opgeslagen, automatisch herschreven naar hun CDN-equivalenten, zodat assets van de CDN-service in plaats van SharePoint worden bediend.</span><span class="sxs-lookup"><span data-stu-id="148ad-556">The **Publishing feature** in SharePoint Online automatically rewrites URLs of assets stored in public origins to their CDN equivalents so that assets are served from the CDN service instead of SharePoint.</span></span>

<span data-ttu-id="148ad-557">Als uw oorsprong zich op een site bevindt waarop de publicatiefunctie is ingeschakeld en de activa die u wilt overzetten naar de CDN, in een van de volgende categorieën staan, worden Url's automatisch herschreven voor activa in de oorsprong, mits het activum niet is uitgesloten door een CDN-beleid.</span><span class="sxs-lookup"><span data-stu-id="148ad-557">If your origin is in a site with the Publishing feature enabled, and the assets you want to offload to the CDN are in one of the following categories, SharePoint will automatically rewrite URLs for assets in the origin, provided that the asset has not been excluded by a CDN policy.</span></span>

<span data-ttu-id="148ad-558">Hieronder ziet u een overzicht van de koppelingen die automatisch worden herschreven met de SharePoint-publicatiefunctie:</span><span class="sxs-lookup"><span data-stu-id="148ad-558">The following is an overview of which links are automatically rewritten by the SharePoint Publishing feature:</span></span>

+ <span data-ttu-id="148ad-559">Url's van Hyper LINK/LINK/CSS in de klassieke publicatiepagina-antwoorden</span><span class="sxs-lookup"><span data-stu-id="148ad-559">IMG/LINK/CSS URLs in classic publishing page HTML responses</span></span>
  + <span data-ttu-id="148ad-560">Dit omvat afbeeldingen die zijn toegevoegd door auteurs binnen de HTML-inhoud van een pagina.</span><span class="sxs-lookup"><span data-stu-id="148ad-560">This includes images added by authors within the HTML content of a page</span></span>
+ <span data-ttu-id="148ad-561">Afbeeldingen van afbeeldingen in de webonderdelen afbeeldingsbibliotheek</span><span class="sxs-lookup"><span data-stu-id="148ad-561">Picture Library SlideShow webpart image URLs</span></span>
+ <span data-ttu-id="148ad-562">Afbeeldingsvelden in de REST-API van de SPList (RenderListDataAsStream)</span><span class="sxs-lookup"><span data-stu-id="148ad-562">Image fields in SPList REST API (RenderListDataAsStream) results</span></span>
  + <span data-ttu-id="148ad-563">Het nieuwe eigenschappen _ImageFieldsToTryRewriteToCdnUrls_ gebruiken om een door komma's gescheiden lijst met velden te maken</span><span class="sxs-lookup"><span data-stu-id="148ad-563">Use the new property _ImageFieldsToTryRewriteToCdnUrls_ to provide a comma separated list of fields</span></span>
  + <span data-ttu-id="148ad-564">Ondersteuning voor hyperlink velden en PublishingImage velden</span><span class="sxs-lookup"><span data-stu-id="148ad-564">Supports hyperlink fields and PublishingImage fields</span></span>
+ <span data-ttu-id="148ad-565">SharePoint-afbeeldingsweergaven</span><span class="sxs-lookup"><span data-stu-id="148ad-565">SharePoint image renditions</span></span>

<span data-ttu-id="148ad-566">In het volgende diagram ziet u de werkstroom wanneer SharePoint een aanvraag ontvangt voor een pagina die activa van een openbare oorsprong bevat.</span><span class="sxs-lookup"><span data-stu-id="148ad-566">The following diagram illustrates the workflow when SharePoint receives a request for a page containing assets from a public origin.</span></span>

<span data-ttu-id="148ad-567">![Werkstroom diagram: Office 365 CDN-activa ophalen uit een openbare Origin](../media/O365-CDN/o365-cdn-public-steps-transparent.svg "Werkstroom: Office 365 CDN-activa ophalen uit een openbare Origin")</span><span class="sxs-lookup"><span data-stu-id="148ad-567">![Workflow diagram: Retrieving Office 365 CDN assets from a public origin](../media/O365-CDN/o365-cdn-public-steps-transparent.svg "Workflow: Retrieving Office 365 CDN assets from a public origin")</span></span>

> [!TIP]
> <span data-ttu-id="148ad-568">Als u automatisch herschrijven voor specifieke Url's wilt uitschakelen op een pagina, kunt u de pagina uitchecken en de queryreeksparameter toevoegen **? NoAutoReWrites = True** naar het einde van elke koppeling die u wilt uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="148ad-568">If you want to disable auto-rewriting for specific URLs on a page, you can check out the page and add the query string parameter **?NoAutoReWrites=true** to the end of each link you want to disable.</span></span>

#### <a name="hardcoding-cdn-urls-for-public-assets"></a><span data-ttu-id="148ad-569">CDN-Url's voor hardcoding voor openbare assets</span><span class="sxs-lookup"><span data-stu-id="148ad-569">Hardcoding CDN URLs for public assets</span></span>

<span data-ttu-id="148ad-570">Als de _publicatie_ functie niet is ingeschakeld voor een openbare Origin of als het activum niet een van de koppelingstypen is die worden ondersteund door de functie automatisch herschrijven van de CDN-service, kunt u handmatig url's maken op de CDN-locatie van de assets en deze url's gebruiken in uw inhoud.</span><span class="sxs-lookup"><span data-stu-id="148ad-570">If the _Publishing_ feature is not enabled for a public origin, or the asset is not one of the link types supported by the auto-rewrite feature of the CDN service, you can manually construct URLs to the CDN location of the assets and use these URLs in your content.</span></span>

> [!NOTE]
> <span data-ttu-id="148ad-571">U kunt geen CDN-Url's hardcode naar assets in een persoonlijke Origin omdat het vereiste toegangstoken dat de laatste sectie van de URL vormt, wordt gegenereerd op het moment dat de resource wordt opgevraagd.</span><span class="sxs-lookup"><span data-stu-id="148ad-571">You cannot hardcode CDN URLs to assets in a private origin because the required access token that forms the last section of the URL is generated at the time the resource is requested.</span></span>

<span data-ttu-id="148ad-572">Voor openbare CDN-assets ziet de URL-indeling er als volgt uit:</span><span class="sxs-lookup"><span data-stu-id="148ad-572">For public CDN assets, the URL format will look like the following:</span></span>

``` html
https://publiccdn.sharepointonline.com/<TenantHostName>/sites/site/library/asset.png
```

<span data-ttu-id="148ad-573">Vervang **TenantHostName** door de naam van de Tenant.</span><span class="sxs-lookup"><span data-stu-id="148ad-573">Replace **TenantHostName** with your tenant name.</span></span> <span data-ttu-id="148ad-574">Voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="148ad-574">Example:</span></span>

``` html
https://publiccdn.sharepointonline.com/contoso.sharepoint.com/sites/site/library/asset.png
```

### <a name="using-assets-in-private-origins"></a><span data-ttu-id="148ad-575">Werken met assets in persoonlijke oorsprong</span><span class="sxs-lookup"><span data-stu-id="148ad-575">Using assets in private origins</span></span>

<span data-ttu-id="148ad-576">Er is geen extra configuratie vereist voor het gebruik van assets in persoonlijke oorsprong.</span><span class="sxs-lookup"><span data-stu-id="148ad-576">No additional configuration is required to use assets in private origins.</span></span> <span data-ttu-id="148ad-577">Url's worden in SharePoint Online automatisch herschreven voor activa in persoonlijke oorsprong, zodat aanvragen voor deze activa altijd vanuit het CDN worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="148ad-577">SharePoint Online automatically rewrites URLs for assets in private origins so requests for those assets will always be served from the CDN.</span></span> <span data-ttu-id="148ad-578">U kunt geen Url's handmatig maken voor CDN-assets in persoonlijke Origins omdat deze Url's tokens bevatten die automatisch moeten worden gegenereerd door SharePoint Online op het moment dat het activum wordt opgevraagd.</span><span class="sxs-lookup"><span data-stu-id="148ad-578">You cannot manually build URLs to CDN assets in private origins because these URLs contain tokens that must be auto-generated by SharePoint Online at the time the asset is requested.</span></span>

<span data-ttu-id="148ad-579">De toegang tot assets in persoonlijke Origins wordt beschermd door dynamische tokens die op basis van gebruikersmachtigingen voor de oorsprong worden vastgelegd, met de voorbehoud van de namen in de volgende secties.</span><span class="sxs-lookup"><span data-stu-id="148ad-579">Access to assets in private origins is protected by dynamically generated tokens based on user permissions to the origin, with the caveats described in the following sections.</span></span> <span data-ttu-id="148ad-580">Gebruikers moeten minimaal **Lees** toegang hebben tot de oorsprong van de CDN om inhoud weer te geven.</span><span class="sxs-lookup"><span data-stu-id="148ad-580">Users must have at least **read** access to the origins for the CDN to render content.</span></span>

<span data-ttu-id="148ad-581">In het volgende diagram ziet u de werkstroom wanneer SharePoint een aanvraag ontvangt voor een pagina die activa van een persoonlijke oorsprong bevat.</span><span class="sxs-lookup"><span data-stu-id="148ad-581">The following diagram illustrates the workflow when SharePoint receives a request for a page containing assets from a private origin.</span></span>

<span data-ttu-id="148ad-582">![Werkstroom diagram: bij het ophalen van Office 365 CDN-assets van een persoonlijke Origin](../media/O365-CDN/o365-cdn-private-steps-transparent.svg "Werkstroom: Office 365 CDN-activa ophalen van een persoonlijke oorsprong")</span><span class="sxs-lookup"><span data-stu-id="148ad-582">![Workflow diagram: Retrieving Office 365 CDN assets from a private origin](../media/O365-CDN/o365-cdn-private-steps-transparent.svg "Workflow: Retrieving Office 365 CDN assets from a private origin")</span></span>

#### <a name="token-based-authorization-in-private-origins"></a><span data-ttu-id="148ad-583">Autorisatie op basis van tokens in persoonlijke oorsprong</span><span class="sxs-lookup"><span data-stu-id="148ad-583">Token-based authorization in private origins</span></span>

<span data-ttu-id="148ad-584">Toegang tot assets in persoonlijke Origins in het Office 365 CDN wordt verleend door tokens die worden gegenereerd door SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="148ad-584">Access to assets in private origins in the Office 365 CDN is granted by tokens generated by SharePoint Online.</span></span> <span data-ttu-id="148ad-585">Gebruikers die al machtigingen hebben voor toegang tot de map of bibliotheek die door de origin zijn aangewezen, krijgen automatisch tokens te ontvangen waarmee de gebruiker toegang kan krijgen tot het bestand op basis van hun machtigingsniveau.</span><span class="sxs-lookup"><span data-stu-id="148ad-585">Users who already have permission to access to the folder or library designated by the origin are automatically granted tokens that permit the user to access the file based on their permission level.</span></span> <span data-ttu-id="148ad-586">De toegangstokens zijn geldig gedurende 30 tot 90 minuten na het genereren ervan om token herhalings aanvallen te helpen voorkomen.</span><span class="sxs-lookup"><span data-stu-id="148ad-586">These access tokens are valid for 30 to 90 minutes after they are generated to help prevent token replay attacks.</span></span>

<span data-ttu-id="148ad-587">Nadat het toegangstoken is gegenereerd, retourneert SharePoint Online een aangepaste URI naar de client met twee autorisatie parameters _eten_ (Edge Authorization token) en _Oat_ (origin Authorization token).</span><span class="sxs-lookup"><span data-stu-id="148ad-587">Once the access token is generated, SharePoint Online returns a custom URI to the client containing two authorization parameters _eat_ (edge authorization token) and _oat_ (origin authorization token).</span></span> <span data-ttu-id="148ad-588">De structuur van elk token wordt _< ' verlooptijd in de epoche-tijdnotatie ' >__< ' veilige handtekening ' >_.</span><span class="sxs-lookup"><span data-stu-id="148ad-588">The structure of each token is _<'expiration time in Epoch time format'>__<'secure signature'>_.</span></span> <span data-ttu-id="148ad-589">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="148ad-589">For example:</span></span>

``` html
https://privatecdn.sharepointonline.com/contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg?eat=1486154359_cc59042c5c55c90b26a2775323c7c8112718431228fe84d568a3795a63912840&oat=1486154359_7d73c2e3ba4b7b1f97242332900616db0d4ffb04312
```

> [!NOTE]
> <span data-ttu-id="148ad-590">Iedereen in het bezit van het token kan toegang krijgen tot de resource in het CDN.</span><span class="sxs-lookup"><span data-stu-id="148ad-590">Anyone in possession of the token can access the resource in the CDN.</span></span> <span data-ttu-id="148ad-591">Url's met deze toegangstokens worden echter alleen via HTTPS gedeeld, dus tenzij de URL expliciet wordt gedeeld door een eindgebruiker voordat het token verloopt, is het activum niet toegankelijk voor niet-geautoriseerde gebruikers.</span><span class="sxs-lookup"><span data-stu-id="148ad-591">However, URLs containing these access tokens are only shared over HTTPS, so unless the URL is explicitly shared by an end user before the token expires, the asset won't be accessible to unauthorized users.</span></span>

#### <a name="item-level-permissions-are-not-supported-for-assets-in-private-origins"></a><span data-ttu-id="148ad-592">Machtigingen op item niveau worden niet ondersteund voor assets in persoonlijke Origin.</span><span class="sxs-lookup"><span data-stu-id="148ad-592">Item-level permissions are not supported for assets in private origins</span></span>

<span data-ttu-id="148ad-593">Houd er rekening mee dat SharePoint Online geen machtigingen op itemniveau biedt voor assets in persoonlijke oorsprong.</span><span class="sxs-lookup"><span data-stu-id="148ad-593">It is important to note that SharePoint Online does not support item-level permissions for assets in private origins.</span></span> <span data-ttu-id="148ad-594">Wanneer een bestand zich bevindt `https://contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg` , hebben gebruikers voor het openen van het bestand de volgende voorwaarden:</span><span class="sxs-lookup"><span data-stu-id="148ad-594">For example, for a file located at `https://contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg`, users have effective access to the file given the following conditions:</span></span>

|<span data-ttu-id="148ad-595">Gebruiker</span><span class="sxs-lookup"><span data-stu-id="148ad-595">User</span></span>  |<span data-ttu-id="148ad-596">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="148ad-596">Permissions</span></span>  |<span data-ttu-id="148ad-597">Effectieve toegang</span><span class="sxs-lookup"><span data-stu-id="148ad-597">Effective access</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="148ad-598">Gebruiker 1</span><span class="sxs-lookup"><span data-stu-id="148ad-598">User 1</span></span>     |<span data-ttu-id="148ad-599">Toegang heeft tot Map1</span><span class="sxs-lookup"><span data-stu-id="148ad-599">Has access to folder1</span></span>         |<span data-ttu-id="148ad-600">Toegang tot image1.jpg vanuit het CDN</span><span class="sxs-lookup"><span data-stu-id="148ad-600">Can access image1.jpg from the CDN</span></span>         |
|<span data-ttu-id="148ad-601">Gebruiker 2</span><span class="sxs-lookup"><span data-stu-id="148ad-601">User 2</span></span>     |<span data-ttu-id="148ad-602">Heeft geen toegang tot Map1</span><span class="sxs-lookup"><span data-stu-id="148ad-602">Does not have access to folder1</span></span>         |<span data-ttu-id="148ad-603">Geen toegang tot image1.jpg vanuit het CDN</span><span class="sxs-lookup"><span data-stu-id="148ad-603">Cannot access image1.jpg from the CDN</span></span>         |
|<span data-ttu-id="148ad-604">Gebruiker 3</span><span class="sxs-lookup"><span data-stu-id="148ad-604">User 3</span></span>     |<span data-ttu-id="148ad-605">Heeft geen toegang tot Map1, maar krijgt expliciet toestemming voor toegang tot image1.jpg in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="148ad-605">Does not have access to folder1, but is granted explicit permission to access image1.jpg in SharePoint Online</span></span>         |<span data-ttu-id="148ad-606">Toegang tot het activum image1.jpg rechtstreeks vanuit SharePoint Online, maar niet in het CDN</span><span class="sxs-lookup"><span data-stu-id="148ad-606">Can access the asset image1.jpg directly from SharePoint Online, but not from the CDN</span></span>         |
|<span data-ttu-id="148ad-607">Gebruiker 4</span><span class="sxs-lookup"><span data-stu-id="148ad-607">User 4</span></span>     |<span data-ttu-id="148ad-608">Toegang tot Map1, maar de toegang tot image1.jpg in SharePoint Online is expliciet geweigerd</span><span class="sxs-lookup"><span data-stu-id="148ad-608">Has access to folder1, but has been explicitly denied access to image1.jpg in SharePoint Online</span></span>         |<span data-ttu-id="148ad-609">Kan geen toegang krijgen tot het activum via SharePoint Online, maar het is niet mogelijk om toegang te krijgen tot het bestand in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="148ad-609">Cannot access the asset from SharePoint Online, but can access the asset from the CDN despite being denied access to the file in SharePoint Online</span></span>         |

<span data-ttu-id="148ad-610"><a name="CDNTroubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="148ad-610"><a name="CDNTroubleshooting"> </a></span></span>
## <a name="troubleshooting-the-office-365-cdn"></a><span data-ttu-id="148ad-611">Problemen oplossen met het Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="148ad-611">Troubleshooting the Office 365 CDN</span></span>

<span data-ttu-id="148ad-612"><a name="CDNConfirm"> </a></span><span class="sxs-lookup"><span data-stu-id="148ad-612"><a name="CDNConfirm"> </a></span></span>
### <a name="how-do-i-confirm-that-assets-are-being-served-by-the-cdn"></a><span data-ttu-id="148ad-613">Hoe controleer ik of de assets worden bediend door de CDN?</span><span class="sxs-lookup"><span data-stu-id="148ad-613">How do I confirm that assets are being served by the CDN?</span></span>

<span data-ttu-id="148ad-614">Wanneer u koppelingen naar CDN-assets aan een pagina hebt toegevoegd, kunt u bevestigen dat het activum wordt bediend door te browsen door op de pagina te klikken, met de rechtermuisknop op de afbeelding te klikken en de afbeeldings-URL te reviseren.</span><span class="sxs-lookup"><span data-stu-id="148ad-614">Once you have added links to CDN assets to a page, you can confirm that the asset is being served from the CDN by browsing to the page, right clicking on the image once it has rendered and reviewing the image URL.</span></span>

<span data-ttu-id="148ad-615">U kunt ook de ontwikkelhulpprogramma's van de browser gebruiken om de URL voor elk activum op een pagina weer te geven of een hulpprogramma voor netwerktracering van derden te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="148ad-615">You can also use your browser's developer tools to view the URL for each asset on a page, or use a third party network trace tool.</span></span>

> [!NOTE]
> <span data-ttu-id="148ad-616">Als u een netwerkprogramma gebruikt, zoals Fiddler, om uw activa te testen buiten het activum van een SharePoint-pagina, moet u handmatig de koptekst voor de linker-header toevoegen `https://yourdomain.sharepoint.com` aan de aanvraag voor het opvragen van de URL van uw SharePoint Online-Tenant.</span><span class="sxs-lookup"><span data-stu-id="148ad-616">If you use a network tool such as Fiddler to test your assets outside of rendering the asset from a SharePoint page, you must manually add the referer header "Referer: `https://yourdomain.sharepoint.com`" to the GET request where the URL is the root URL of your SharePoint Online tenant.</span></span>

<span data-ttu-id="148ad-617">U kunt CDN-Url's niet rechtstreeks in een webbrowser testen, omdat u een verwijzing moet hebben van SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="148ad-617">You cannot test CDN URLs directly in a web browser because you must have a referer coming from SharePoint Online.</span></span> <span data-ttu-id="148ad-618">Als u echter de URL van de CDN-activum toevoegt aan een SharePoint-pagina en vervolgens de pagina in een browser opent, ziet u het CDN-activum dat op de pagina wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="148ad-618">However, if you add the CDN asset URL to a SharePoint page and then open the page in a browser, you will see the CDN asset rendered on the page.</span></span>

<span data-ttu-id="148ad-619">Zie [Microsoft Edge-ontwikkelaars Programma's](https://docs.microsoft.com/microsoft-edge/devtools-guide)voor meer informatie over het gebruik van de hulpmiddelen voor ontwikkelaars in de Microsoft Edge-browser.</span><span class="sxs-lookup"><span data-stu-id="148ad-619">For more information on using the developer tools in the Microsoft Edge browser, see [Microsoft Edge Developer Tools](https://docs.microsoft.com/microsoft-edge/devtools-guide).</span></span>

<span data-ttu-id="148ad-620">Als u een korte video in het [YouTube-kanaal van de SharePoint-ontwikkel patronen en-procedures](https://aka.ms/sppnp-videos) wilt bekijken waarin wordt uitgelegd hoe u kunt controleren of uw CDN werkt, raadpleegt u [uw CDN-gebruik verifiëren en zorgen voor optimale netwerkconnectiviteit](https://www.youtube.com/watch?v=ClCtBAtGjE8&list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA&index=5).</span><span class="sxs-lookup"><span data-stu-id="148ad-620">To watch a short video hosted in the [SharePoint Developer Patterns and Practices YouTube channel](https://aka.ms/sppnp-videos) demonstrating how to verify that your CDN is working, please see [Verifying your CDN usage and ensuring optimal network connectivity](https://www.youtube.com/watch?v=ClCtBAtGjE8&list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA&index=5).</span></span>

### <a name="why-are-assets-from-a-new-origin-unavailable"></a><span data-ttu-id="148ad-621">Waarom zijn activa van een nieuwe Origin niet beschikbaar?</span><span class="sxs-lookup"><span data-stu-id="148ad-621">Why are assets from a new origin unavailable?</span></span>
<span data-ttu-id="148ad-622">Activa in nieuwe oorsprong zijn niet onmiddellijk beschikbaar voor gebruik, omdat het tijd is voor het doorgeven van de registratie via de CDN en voor de activa die van de origin worden geüpload naar de CDN-opslag.</span><span class="sxs-lookup"><span data-stu-id="148ad-622">Assets in new origins will not immediately be available for use, as it takes time for the registration to propagate through the CDN and for the assets to be uploaded from the origin to CDN storage.</span></span> <span data-ttu-id="148ad-623">De tijd die nodig is voor het maken van activa in de CDN, is afhankelijk van het aantal activa en de grootte van de bestanden.</span><span class="sxs-lookup"><span data-stu-id="148ad-623">The time required for assets to be available in the CDN depends on how many assets and the files sizes.</span></span>

### <a name="my-client-side-web-part-or-sharepoint-framework-solution-isnt-working"></a><span data-ttu-id="148ad-624">Het webonderdeel van de client of de SharePoint Framework-oplossing werkt niet</span><span class="sxs-lookup"><span data-stu-id="148ad-624">My client-side web part or SharePoint Framework solution isn't working</span></span>

<span data-ttu-id="148ad-625">Wanneer u Office 365 CDN voor openbare oorsprong inschakelt, worden deze standaard Origins automatisch gemaakt met de CDN-service:</span><span class="sxs-lookup"><span data-stu-id="148ad-625">When you enable the Office 365 CDN for public origins, the CDN service automatically creates these default origins:</span></span>

+ <span data-ttu-id="148ad-626">\*/MASTERPAGE</span><span class="sxs-lookup"><span data-stu-id="148ad-626">\*/MASTERPAGE</span></span>
+ <span data-ttu-id="148ad-627">\*/STYLE BIBLIOTHEEK</span><span class="sxs-lookup"><span data-stu-id="148ad-627">\*/STYLE LIBRARY</span></span>
+ <span data-ttu-id="148ad-628">\*/CLIENTSIDEASSETS</span><span class="sxs-lookup"><span data-stu-id="148ad-628">\*/CLIENTSIDEASSETS</span></span>

<span data-ttu-id="148ad-629">Als de/clientsideassets-oorsprong ontbreekt, mislukt SharePoint Framework-oplossingen en worden er geen waarschuwings-of foutberichten gegenereerd.</span><span class="sxs-lookup"><span data-stu-id="148ad-629">If the \*/clientsideassets origin is missing, SharePoint Framework solutions will fail, and no warning or error messages are generated.</span></span> <span data-ttu-id="148ad-630">Deze oorsprong kan ontbreken omdat de CDN is ingeschakeld en de parameter _NoDefaultOrigins_ is ingesteld op **$True**, of omdat de oorsprong handmatig is verwijderd.</span><span class="sxs-lookup"><span data-stu-id="148ad-630">This origin may be missing either because the CDN was enabled with the _-NoDefaultOrigins_ parameter set to **$true**, or because the origin was manually deleted.</span></span>

<span data-ttu-id="148ad-631">U kunt nagaan welke oorsprong aanwezig zijn met de volgende PowerShell-opdracht:</span><span class="sxs-lookup"><span data-stu-id="148ad-631">You can check to see which origins are present with the following PowerShell command:</span></span>

``` powershell
Get-SPOTenantCdnOrigins -CdnType Public
```

<span data-ttu-id="148ad-632">U kunt ook het volgende controleren met Office 365 CLI:</span><span class="sxs-lookup"><span data-stu-id="148ad-632">Or you can check with the Office 365 CLI:</span></span>

``` powershell
spo cdn origin list
```

<span data-ttu-id="148ad-633">De origin toevoegen in PowerShell:</span><span class="sxs-lookup"><span data-stu-id="148ad-633">To add the origin in PowerShell:</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */CLIENTSIDEASSETS
```

<span data-ttu-id="148ad-634">De origin toevoegen in Office 365 CLI:</span><span class="sxs-lookup"><span data-stu-id="148ad-634">To add the origin in the Office 365 CLI:</span></span>

``` powershell
spo cdn origin add --origin */CLIENTSIDEASSETS
```

### <a name="what-powershell-modules-and-cli-shells-do-i-need-to-work-with-the-office-365-cdn"></a><span data-ttu-id="148ad-635">Welke PowerShell-modules en CLI-shells moet ik gebruiken met Office 365 CDN?</span><span class="sxs-lookup"><span data-stu-id="148ad-635">What PowerShell modules and CLI shells do I need to work with the Office 365 CDN?</span></span>

<span data-ttu-id="148ad-636">U kunt ervoor kiezen om te werken met Office 365 CDN met behulp van de PowerShell-module van **SharePoint Online Management Shell** of **Office 365 cli**.</span><span class="sxs-lookup"><span data-stu-id="148ad-636">You can choose to work with the Office 365 CDN using either the **SharePoint Online Management Shell** PowerShell module or the **Office 365 CLI**.</span></span>

+ [<span data-ttu-id="148ad-637">Aan de slag met SharePoint Online Management Shell</span><span class="sxs-lookup"><span data-stu-id="148ad-637">Getting started with SharePoint Online Management Shell</span></span>](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)
+ [<span data-ttu-id="148ad-638">Office 365 CLI installeren</span><span class="sxs-lookup"><span data-stu-id="148ad-638">Installing the Office 365 CLI</span></span>](https://pnp.github.io/office365-cli/user-guide/installing-cli/)

## <a name="see-also"></a><span data-ttu-id="148ad-639">Zie ook</span><span class="sxs-lookup"><span data-stu-id="148ad-639">See also</span></span>

[<span data-ttu-id="148ad-640">Netwerken voor content levering</span><span class="sxs-lookup"><span data-stu-id="148ad-640">Content Delivery Networks</span></span>](https://aka.ms/o365cdns)

[<span data-ttu-id="148ad-641">Network planning and performance tuning for Office 365</span><span class="sxs-lookup"><span data-stu-id="148ad-641">Network planning and performance tuning for Office 365</span></span>](https://aka.ms/tune)

[<span data-ttu-id="148ad-642">SharePoint-prestatie serie-Office 365 CDN-VideoReeks</span><span class="sxs-lookup"><span data-stu-id="148ad-642">SharePoint Performance Series - Office 365 CDN video series</span></span>](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)
