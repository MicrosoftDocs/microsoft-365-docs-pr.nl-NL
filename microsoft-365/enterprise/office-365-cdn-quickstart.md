---
title: Office 365 Content Delivery Network (CDN) Quickstart
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
description: Office 365 Content Delivery Network (CDN) Quickstart
ms.openlocfilehash: 3539ad1f11b27c60b5641976ae66a1480ef4be98
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921592"
---
# <a name="office-365-content-delivery-network-cdn-quickstart"></a><span data-ttu-id="c229d-103">Office 365 Content Delivery Network (CDN) Quickstart</span><span class="sxs-lookup"><span data-stu-id="c229d-103">Office 365 Content Delivery Network (CDN) Quickstart</span></span>

<span data-ttu-id="c229d-104">U kunt de ingebouwde **Office 365 Content Delivery Network (CDN)** gebruiken om statische assets (afbeeldingen, JavaScript, Stylesheets, WOFF-bestanden) te hosten om betere prestaties te bieden voor uw SharePoint Online-pagina's.</span><span class="sxs-lookup"><span data-stu-id="c229d-104">You can use the built-in **Office 365 Content Delivery Network (CDN)** to host static assets (images, JavaScript, Stylesheets, WOFF files) to provide better performance for your SharePoint Online pages.</span></span> <span data-ttu-id="c229d-105">De Office 365 CDN verbetert de prestaties door statische assets dichter bij de browsers te houden waarin ze worden gevraagd, wat helpt om downloads te versnellen en de latentie te verminderen.</span><span class="sxs-lookup"><span data-stu-id="c229d-105">The Office 365 CDN improves performance by caching static assets closer to the browsers requesting them, which helps to speed up downloads and reduce latency.</span></span> <span data-ttu-id="c229d-106">De Office 365 CDN gebruikt ook het HTTP/2-protocol voor verbeterde compressie en HTTP-pipelineing.</span><span class="sxs-lookup"><span data-stu-id="c229d-106">Also, the Office 365 CDN uses the HTTP/2 protocol for improved compression and HTTP pipelining.</span></span> <span data-ttu-id="c229d-107">De Office 365 CDN service is opgenomen als onderdeel van uw SharePoint Online-abonnement.</span><span class="sxs-lookup"><span data-stu-id="c229d-107">The Office 365 CDN service is included as part of your SharePoint Online subscription.</span></span>

<span data-ttu-id="c229d-108">Zie De Office 365 Content Delivery Network [(CDN)](use-microsoft-365-cdn-with-spo.md)met SharePoint Online voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="c229d-108">For more detailed information guidance see [Use the Office 365 Content Delivery Network (CDN) with SharePoint Online](use-microsoft-365-cdn-with-spo.md).</span></span>

>[!NOTE]
><span data-ttu-id="c229d-109">De Office 365 CDN is alleen beschikbaar voor tenants in de productiecloud (wereldwijd).</span><span class="sxs-lookup"><span data-stu-id="c229d-109">The Office 365 CDN is only available to tenants in the production (worldwide) cloud.</span></span> <span data-ttu-id="c229d-110">Tenants in de amerikaanse overheid, China en Duitsland clouds ondersteunen momenteel de Office 365 CDN.</span><span class="sxs-lookup"><span data-stu-id="c229d-110">Tenants in the US Government, China and Germany clouds do not currently support the Office 365 CDN.</span></span>

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-identify-items-not-in-cdn"></a><span data-ttu-id="c229d-111">Gebruik het hulpprogramma Paginadiagnose voor SharePoint om items te identificeren die niet in de CDN</span><span class="sxs-lookup"><span data-stu-id="c229d-111">Use the Page Diagnostics for SharePoint tool to identify items not in CDN</span></span>

<span data-ttu-id="c229d-112">U kunt de browserextensie **Paginadiagnose** voor SharePoint gebruiken om eenvoudig activa in uw SharePoint Online-pagina's weer te geven die kunnen worden toegevoegd aan een CDN origin.</span><span class="sxs-lookup"><span data-stu-id="c229d-112">You can use the **Page Diagnostics for SharePoint tool** browser extension to easily list assets in your SharePoint Online pages that can be added to a CDN origin.</span></span>

<span data-ttu-id="c229d-113">Het **hulpprogramma Paginadiagnose voor SharePoint** is een browserextensie voor de nieuwe Microsoft Edge ( en Chrome-browsers die zowel SharePoint Moderne portal online als klassieke https://www.microsoft.com/edge) publicerende sitepagina's analyseert.</span><span class="sxs-lookup"><span data-stu-id="c229d-113">The **Page Diagnostics for SharePoint tool** is a browser extension for the new Microsoft Edge (https://www.microsoft.com/edge) and Chrome browsers that analyzes both SharePoint Online modern portal and classic publishing site pages.</span></span> <span data-ttu-id="c229d-114">Het hulpprogramma bevat een rapport voor elke geanalyseerde pagina die laat zien hoe de pagina presteert op basis van een gedefinieerde set prestatiecriteria.</span><span class="sxs-lookup"><span data-stu-id="c229d-114">The tool provides a report for each analyzed page showing how the page performs against a defined set of performance criteria.</span></span> <span data-ttu-id="c229d-115">Als u het hulpprogramma Paginadiagnose voor SharePoint wilt installeren en meer wilt weten, gaat u naar Het hulpprogramma [Paginadiagnose gebruiken](./page-diagnostics-for-spo.md)voor SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="c229d-115">To install and learn about the Page Diagnostics for SharePoint tool, visit [Use the Page Diagnostics tool for SharePoint Online](./page-diagnostics-for-spo.md).</span></span>

<span data-ttu-id="c229d-116">Wanneer u het hulpprogramma Paginadiagnose voor SharePoint op een pagina SharePoint  Online uit te voeren, kunt u op het tabblad Diagnostische tests klikken om een lijst weer te geven met assets die niet worden gehost door de CDN.</span><span class="sxs-lookup"><span data-stu-id="c229d-116">When you run the Page Diagnostics for SharePoint tool on a SharePoint Online page, you can click the **Diagnostic Tests** tab to see a list of assets not being hosted by the CDN.</span></span> <span data-ttu-id="c229d-117">Deze activa worden weergegeven onder de kopcontrole **Content Delivery Network (CDN)** zoals wordt weergegeven in de onderstaande schermafbeelding.</span><span class="sxs-lookup"><span data-stu-id="c229d-117">These assets will be listed under the heading **Content Delivery Network (CDN) check** as shown in the screenshot below.</span></span>

![Paginadiagnose](../media/page-diagnostics-for-spo/pagediag-results-general.PNG)

>[!NOTE]
><span data-ttu-id="c229d-119">Het hulpprogramma Paginadiagnose werkt alleen SharePoint Online en kan niet worden gebruikt op een SharePoint systeempagina.</span><span class="sxs-lookup"><span data-stu-id="c229d-119">The Page Diagnostics tool only works for SharePoint Online, and cannot be used on a SharePoint system page.</span></span>

## <a name="cdn-overview"></a><span data-ttu-id="c229d-120">CDN Overzicht</span><span class="sxs-lookup"><span data-stu-id="c229d-120">CDN Overview</span></span>

<span data-ttu-id="c229d-121">De Office 365 CDN is ontworpen om de prestaties voor gebruikers te optimaliseren door veelgebruikte objecten, zoals afbeeldingen en javascript-bestanden, te distribueren via een snel globaal netwerk, de laadtijd van pagina's te verkorten en door de gebruiker zo dicht mogelijk toegang te bieden tot gehoste objecten.</span><span class="sxs-lookup"><span data-stu-id="c229d-121">The Office 365 CDN is designed to optimize performance for users by distributing frequently accessed objects like images and javascript files over a high-speed global network, reducing page load time and providing access to hosted objects as close as possible to the user.</span></span> <span data-ttu-id="c229d-122">De CDN haalt uw activa op van een locatie die een origin _wordt genoemd._</span><span class="sxs-lookup"><span data-stu-id="c229d-122">The CDN fetches your assets from a location called an _origin_.</span></span> <span data-ttu-id="c229d-123">Een origin kan een SharePoint site, documentbibliotheek of map zijn die toegankelijk is via een URL.</span><span class="sxs-lookup"><span data-stu-id="c229d-123">An origin can be a SharePoint site, document library or folder that is accessible by a URL.</span></span>

<span data-ttu-id="c229d-124">De Office 365 CDN is gescheiden in twee basistypen:</span><span class="sxs-lookup"><span data-stu-id="c229d-124">The Office 365 CDN is separated into two basic types:</span></span>

- <span data-ttu-id="c229d-125">**Openbare CDN** is ontworpen voor JS (JavaScript), CSS (StyleSheets), Web Font File (WOFF, WOFF2) en niet-eigendomsafbeeldingen, zoals bedrijfslogo's.</span><span class="sxs-lookup"><span data-stu-id="c229d-125">**Public CDN** is designed to be used for JS (JavaScript), CSS (StyleSheets), Web Font File (WOFF, WOFF2) and non-proprietary images like company logos.</span></span>
- <span data-ttu-id="c229d-126">**Persoonlijke CDN** is ontworpen voor afbeeldingen (PNG, JPG, JPEG, enzovoort).</span><span class="sxs-lookup"><span data-stu-id="c229d-126">**Private CDN** is designed to be used for images (PNG, JPG, JPEG, etc.).</span></span>

<span data-ttu-id="c229d-127">U kunt ervoor kiezen om zowel openbare als persoonlijke origins voor uw organisatie te hebben.</span><span class="sxs-lookup"><span data-stu-id="c229d-127">You can choose to have both public or private origins for your organization.</span></span> <span data-ttu-id="c229d-128">De meeste organisaties kiezen ervoor om een combinatie van de twee te implementeren.</span><span class="sxs-lookup"><span data-stu-id="c229d-128">Most organizations will choose to implement a combination of the two.</span></span> <span data-ttu-id="c229d-129">Openbare en private opties bieden vergelijkbare prestatieverbeteringen, maar elk heeft unieke kenmerken en voordelen.</span><span class="sxs-lookup"><span data-stu-id="c229d-129">Both public and private options provide similar performance gains, but each has unique attributes and advantages.</span></span> <span data-ttu-id="c229d-130">Zie Kiezen of elke origin openbaar of privé [](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)moet zijn voor meer informatie over openbare en CDN origins.</span><span class="sxs-lookup"><span data-stu-id="c229d-130">For more information about public and private CDN origins, see [Choose whether each origin should be public or private](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate).</span></span>

## <a name="how-to-enable-public-and-private-cdn-with-the-default-configuration"></a><span data-ttu-id="c229d-131">Openbare en privé-CDN met de standaardconfiguratie inschakelen</span><span class="sxs-lookup"><span data-stu-id="c229d-131">How to enable Public and Private CDN with the default configuration</span></span>
<span data-ttu-id="c229d-132">Voordat u wijzigingen aan de tenantinstellingen CDN, moet u controleren of deze voldoet aan het compliance-, beveiligings- en privacybeleid van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="c229d-132">Before you make changes to the tenant CDN settings, you should verify that it meets compliance, security and privacy policies of your organization.</span></span>

<span data-ttu-id="c229d-133">Voor meer gedetailleerde configuratie-instellingen of als u CDN al hebt ingeschakeld en extra locaties (origins) wilt toevoegen, raadpleegt u de sectie De Office 365 CDN instellen en configureren met behulp van [de SharePoint Online Management Shell](use-microsoft-365-cdn-with-spo.md#set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell)</span><span class="sxs-lookup"><span data-stu-id="c229d-133">For more detailed configuration settings, or if you have already enabled CDN and want to add additional locations (origins), please see the section [Set up and configure the Office 365 CDN by using the SharePoint Online Management Shell](use-microsoft-365-cdn-with-spo.md#set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell)</span></span>

<span data-ttu-id="c229d-134">Verbinding maken naar uw tenant met behulp van SharePoint Online Management Shell:</span><span class="sxs-lookup"><span data-stu-id="c229d-134">Connect to your tenant using the SharePoint Online Management Shell:</span></span>

```PowerShell
Connect-SPOService -Url https://<YourTenantName>-admin.sharepoint.com
```

<span data-ttu-id="c229d-135">Als u wilt dat uw organisatie zowel openbare als persoonlijke origins met de standaardconfiguratie kan gebruiken, typt u de volgende opdracht:</span><span class="sxs-lookup"><span data-stu-id="c229d-135">To enable your organization to use both public and private origins with the default configuration, type the following command:</span></span>

```PowerShell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

<span data-ttu-id="c229d-136">De uitvoer van deze cmdlets ziet er als volgt uit:</span><span class="sxs-lookup"><span data-stu-id="c229d-136">Output of these cmdlets should look like the following:</span></span>

![Uitvoer van Set-SPOTenantCdnEnabled](../media/O365-CDN/o365-cdn-enable-output.png)

## <a name="see-also"></a><span data-ttu-id="c229d-138">Zie ook</span><span class="sxs-lookup"><span data-stu-id="c229d-138">See also</span></span>

[<span data-ttu-id="c229d-139">Het hulpprogramma Paginadiagnose gebruiken voor SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="c229d-139">Use the Page Diagnostics tool for SharePoint Online</span></span>](./page-diagnostics-for-spo.md)

[<span data-ttu-id="c229d-140">De Office 365 Content Delivery Network (CDN) gebruiken met SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="c229d-140">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)

[<span data-ttu-id="c229d-141">Netwerken voor contentlevering</span><span class="sxs-lookup"><span data-stu-id="c229d-141">Content Delivery Networks</span></span>](./content-delivery-networks.md)

[<span data-ttu-id="c229d-142">Network planning and performance tuning for Office 365</span><span class="sxs-lookup"><span data-stu-id="c229d-142">Network planning and performance tuning for Office 365</span></span>](./network-planning-and-performance.md)

[<span data-ttu-id="c229d-143">SharePoint Performance Series - Office 365 CDN videoreeks</span><span class="sxs-lookup"><span data-stu-id="c229d-143">SharePoint Performance Series - Office 365 CDN video series</span></span>](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)