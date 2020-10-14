---
title: Snelstartgids voor Office 365 Content Delivery Network (CDN)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 06/04/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
- m365initiative-coredeploy
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- SPO160
description: Snelstartgids voor Office 365 Content Delivery Network (CDN)
ms.openlocfilehash: e541b2ea63a69644de22329c45bd6963749964f7
ms.sourcegitcommit: d76a4c07f0be2938372bdfae50e0e4d523bd8e9f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/14/2020
ms.locfileid: "48456409"
---
# <a name="office-365-content-delivery-network-cdn-quickstart"></a><span data-ttu-id="42904-103">Snelstartgids voor Office 365 Content Delivery Network (CDN)</span><span class="sxs-lookup"><span data-stu-id="42904-103">Office 365 Content Delivery Network (CDN) Quickstart</span></span>

<span data-ttu-id="42904-104">U kunt het ingebouwde **Office 365 Content Delivery Network (CDN)** gebruiken voor het hosten van statische activa (afbeeldingen, JavaScript, opmaakmodellen en WOFF-bestanden) voor betere prestaties voor de SharePoint Online-pagina's.</span><span class="sxs-lookup"><span data-stu-id="42904-104">You can use the built-in **Office 365 Content Delivery Network (CDN)** to host static assets (images, JavaScript, Stylesheets, WOFF files) to provide better performance for your SharePoint Online pages.</span></span> <span data-ttu-id="42904-105">Het CDN van Office 365 verbetert de prestaties omdat statische activa dichter bij de door u gevraagde browsers worden opgevolgd, zodat downloads sneller kunnen worden en de latentie minder kost.</span><span class="sxs-lookup"><span data-stu-id="42904-105">The Office 365 CDN improves performance by caching static assets closer to the browsers requesting them, which helps to speed up downloads and reduce latency.</span></span> <span data-ttu-id="42904-106">Daarnaast wordt in Office 365 CDN het Protocol HTTP/2 gebruikt voor verbeterde compressie en HTTP-pipeline.</span><span class="sxs-lookup"><span data-stu-id="42904-106">Also, the Office 365 CDN uses the HTTP/2 protocol for improved compression and HTTP pipelining.</span></span> <span data-ttu-id="42904-107">De Office 365 CDN-service maakt deel uit van uw SharePoint Online-abonnement.</span><span class="sxs-lookup"><span data-stu-id="42904-107">The Office 365 CDN service is included as part of your SharePoint Online subscription.</span></span>

<span data-ttu-id="42904-108">Zie [het Office 365 Content Delivery Network (CDN) gebruiken met SharePoint Online](use-microsoft-365-cdn-with-spo.md)voor uitgebreidere informatie.</span><span class="sxs-lookup"><span data-stu-id="42904-108">For more detailed information guidance see [Use the Office 365 Content Delivery Network (CDN) with SharePoint Online](use-microsoft-365-cdn-with-spo.md).</span></span>

>[!NOTE]
><span data-ttu-id="42904-109">Het Office 365 CDN is alleen beschikbaar voor tenants in de productie-Cloud (wereldwijd).</span><span class="sxs-lookup"><span data-stu-id="42904-109">The Office 365 CDN is only available to tenants in the production (worldwide) cloud.</span></span> <span data-ttu-id="42904-110">Tenants in de Verenigde Staten voor de overheid, China en Duitsland ondersteunen momenteel het Office 365 CDN.</span><span class="sxs-lookup"><span data-stu-id="42904-110">Tenants in the US Government, China and Germany clouds do not currently support the Office 365 CDN.</span></span>

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-identify-items-not-in-cdn"></a><span data-ttu-id="42904-111">Het hulpprogramma pagina diagnose voor SharePoint gebruiken om te zoeken naar items die niet in het CDN staan</span><span class="sxs-lookup"><span data-stu-id="42904-111">Use the Page Diagnostics for SharePoint tool to identify items not in CDN</span></span>

<span data-ttu-id="42904-112">U kunt de browser extensie voor de browser **van SharePoint voor SharePoint** gebruiken om eenvoudig de assets van de SharePoint Online-pagina's weer te geven die kunnen worden toegevoegd aan een CDN-oorsprong.</span><span class="sxs-lookup"><span data-stu-id="42904-112">You can use the **Page Diagnostics for SharePoint tool** browser extension to easily list assets in your SharePoint Online pages that can be added to a CDN origin.</span></span>

<span data-ttu-id="42904-113">Het **hulpprogramma pagina diagnose voor SharePoint** is een browser extensie voor de nieuwe Microsoft Edge- https://www.microsoft.com/edge) en Chrome-browsers die zowel SharePoint Online modern portal als de klassieke publicatiesite pagina's analyseren.</span><span class="sxs-lookup"><span data-stu-id="42904-113">The **Page Diagnostics for SharePoint tool** is a browser extension for the new Microsoft Edge (https://www.microsoft.com/edge) and Chrome browsers that analyzes both SharePoint Online modern portal and classic publishing site pages.</span></span> <span data-ttu-id="42904-114">Het hulpmiddel biedt een rapport voor elke geanalyseerde pagina op basis van een gedefinieerde set prestatiecriteria.</span><span class="sxs-lookup"><span data-stu-id="42904-114">The tool provides a report for each analyzed page showing how the page performs against a defined set of performance criteria.</span></span> <span data-ttu-id="42904-115">Ga voor meer informatie over het hulpprogramma pagina diagnose voor SharePoint naar [het hulpprogramma pagina diagnose voor SharePoint Online](https://aka.ms/perftool).</span><span class="sxs-lookup"><span data-stu-id="42904-115">To install and learn about the Page Diagnostics for SharePoint tool, visit [Use the Page Diagnostics tool for SharePoint Online](https://aka.ms/perftool).</span></span>

<span data-ttu-id="42904-116">Wanneer u het hulpprogramma pagina diagnose voor SharePoint op een SharePoint Online-pagina uitvoert, kunt u op het tabblad **diagnostische tests** klikken om een lijst weer te geven met assets die niet worden gehost op de CDN.</span><span class="sxs-lookup"><span data-stu-id="42904-116">When you run the Page Diagnostics for SharePoint tool on a SharePoint Online page, you can click the **Diagnostic Tests** tab to see a list of assets not being hosted by the CDN.</span></span> <span data-ttu-id="42904-117">Deze assets worden weergegeven onder het **selectievakje header Content Delivery Network (CDN)** , zoals wordt weergegeven in de onderstaande schermafbeelding.</span><span class="sxs-lookup"><span data-stu-id="42904-117">These assets will be listed under the heading **Content Delivery Network (CDN) check** as shown in the screenshot below.</span></span>

![Diagnostische gegevens voor pagina's](../media/page-diagnostics-for-spo/pagediag-results-general.PNG)

>[!NOTE]
><span data-ttu-id="42904-119">Het hulpmiddel voor het automatisch toevoegen van pagina's werkt alleen voor SharePoint Online en kan niet worden gebruikt op een SharePoint-systeempagina.</span><span class="sxs-lookup"><span data-stu-id="42904-119">The Page Diagnostics tool only works for SharePoint Online, and cannot be used on a SharePoint system page.</span></span>

## <a name="cdn-overview"></a><span data-ttu-id="42904-120">CDN-overzicht</span><span class="sxs-lookup"><span data-stu-id="42904-120">CDN Overview</span></span>

<span data-ttu-id="42904-121">Het Office 365 CDN is ontworpen om de prestaties van gebruikers te optimaliseren door regelmatig toegankelijke objecten zoals afbeeldingen en JavaScript-bestanden te distribueren via een hogesnelheidsnet globaal netwerk, de laadtijd van pagina's te beperken en toegang tot gehoste objecten zo dicht mogelijk te bieden.</span><span class="sxs-lookup"><span data-stu-id="42904-121">The Office 365 CDN is designed to optimize performance for users by distributing frequently accessed objects like images and javascript files over a high-speed global network, reducing page load time and providing access to hosted objects as close as possible to the user.</span></span> <span data-ttu-id="42904-122">De CDN haalt de assets op van de locatie die een _oorsprong_wordt genoemd.</span><span class="sxs-lookup"><span data-stu-id="42904-122">The CDN fetches your assets from a location called an _origin_.</span></span> <span data-ttu-id="42904-123">Een oorsprong kan een SharePoint-site, documentbibliotheek of map zijn die toegankelijk is voor een URL.</span><span class="sxs-lookup"><span data-stu-id="42904-123">An origin can be a SharePoint site, document library or folder that is accessible by a URL.</span></span>

<span data-ttu-id="42904-124">Het CDN van Office 365 is onderverdeeld in twee basistypen:</span><span class="sxs-lookup"><span data-stu-id="42904-124">The Office 365 CDN is separated into two basic types:</span></span>

- <span data-ttu-id="42904-125">Het **openbare CDN** is bedoeld voor JS (JavaScript), CSS (Style Sheets), Web lettertypebestand (WOFF, WOFF2) en niet-eigen afbeeldingen zoals bedrijfslogo's.</span><span class="sxs-lookup"><span data-stu-id="42904-125">**Public CDN** is designed to be used for JS (JavaScript), CSS (StyleSheets), Web Font File (WOFF, WOFF2) and non-proprietary images like company logos.</span></span>
- <span data-ttu-id="42904-126">**Persoonlijk CDN** is bedoeld voor afbeeldingen (PNG, JPG, JPEG, enzovoort).</span><span class="sxs-lookup"><span data-stu-id="42904-126">**Private CDN** is designed to be used for images (PNG, JPG, JPEG, etc.).</span></span>

<span data-ttu-id="42904-127">U kunt ervoor kiezen om zowel openbare als persoonlijke oorsprong te hebben voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="42904-127">You can choose to have both public or private origins for your organization.</span></span> <span data-ttu-id="42904-128">De meeste organisaties kiezen om een combinatie van beide te implementeren.</span><span class="sxs-lookup"><span data-stu-id="42904-128">Most organizations will choose to implement a combination of the two.</span></span> <span data-ttu-id="42904-129">Zowel de openbare als de persoonlijke opties bieden soortgelijke prestatieverbeteringen, maar elk heeft unieke kenmerken en voordelen.</span><span class="sxs-lookup"><span data-stu-id="42904-129">Both public and private options provide similar performance gains, but each has unique attributes and advantages.</span></span> <span data-ttu-id="42904-130">Zie voor meer informatie over openbare en persoonlijke CDN-oorsprong [de optie voor het maken van een openbare of persoonlijke oorsprong](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate).</span><span class="sxs-lookup"><span data-stu-id="42904-130">For more information about public and private CDN origins, see [Choose whether each origin should be public or private](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate).</span></span>

## <a name="how-to-enable-public-and-private-cdn-with-the-default-configuration"></a><span data-ttu-id="42904-131">Public en private CDN inschakelen met de standaardconfiguratie</span><span class="sxs-lookup"><span data-stu-id="42904-131">How to enable Public and Private CDN with the default configuration</span></span>
<span data-ttu-id="42904-132">Voordat u wijzigingen aanbrengt in de CDN-instellingen van de Tenant, dient u te controleren of deze voldoet aan naleving, beveiliging en privacybeleid van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="42904-132">Before you make changes to the tenant CDN settings, you should verify that it meets compliance, security and privacy policies of your organization.</span></span>

<span data-ttu-id="42904-133">Zie het gedeelte [Office 365 CDN instellen en configureren met behulp van de SharePoint Online Management Shell](use-microsoft-365-cdn-with-spo.md#set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell) voor meer informatie over de configuratie-instellingen of voor het toevoegen van een ander CDN en het toevoegen van extra locaties (oorsprong).</span><span class="sxs-lookup"><span data-stu-id="42904-133">For more detailed configuration settings, or if you have already enabled CDN and want to add additional locations (origins), please see the section [Set up and configure the Office 365 CDN by using the SharePoint Online Management Shell](use-microsoft-365-cdn-with-spo.md#set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell)</span></span>

<span data-ttu-id="42904-134">Maak verbinding met de Tenant met behulp van SharePoint Online Management Shell:</span><span class="sxs-lookup"><span data-stu-id="42904-134">Connect to your tenant using the SharePoint Online Management Shell:</span></span>

```PowerShell
Connect-SPOService -Url https://<YourTenantName>-admin.sharepoint.com
```

<span data-ttu-id="42904-135">Als u wilt dat uw organisatie zowel openbare als persoonlijke Origins gebruikt met de standaardconfiguratie, typt u de volgende opdracht:</span><span class="sxs-lookup"><span data-stu-id="42904-135">To enable your organization to use both public and private origins with the default configuration, type the following command:</span></span>

```PowerShell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

<span data-ttu-id="42904-136">De uitvoer van de volgende cmdlets ziet er als volgt uit:</span><span class="sxs-lookup"><span data-stu-id="42904-136">Output of these cmdlets should look like the following:</span></span>

![Uitvoer van Set-SPOTenantCdnEnabled](../media/O365-CDN/o365-cdn-enable-output.png)

## <a name="see-also"></a><span data-ttu-id="42904-138">Zie ook</span><span class="sxs-lookup"><span data-stu-id="42904-138">See also</span></span>

[<span data-ttu-id="42904-139">Het hulpprogramma pagina diagnose voor SharePoint Online gebruiken</span><span class="sxs-lookup"><span data-stu-id="42904-139">Use the Page Diagnostics tool for SharePoint Online</span></span>](https://aka.ms/perftool)

[<span data-ttu-id="42904-140">Het Office 365 Content Delivery Network (CDN) gebruiken met SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="42904-140">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)

[<span data-ttu-id="42904-141">Netwerken voor contentlevering</span><span class="sxs-lookup"><span data-stu-id="42904-141">Content Delivery Networks</span></span>](https://aka.ms/o365cdns)

[<span data-ttu-id="42904-142">Network planning and performance tuning for Office 365</span><span class="sxs-lookup"><span data-stu-id="42904-142">Network planning and performance tuning for Office 365</span></span>](https://aka.ms/tune)

[<span data-ttu-id="42904-143">SharePoint-prestatie serie-Office 365 CDN-VideoReeks</span><span class="sxs-lookup"><span data-stu-id="42904-143">SharePoint Performance Series - Office 365 CDN video series</span></span>](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)
