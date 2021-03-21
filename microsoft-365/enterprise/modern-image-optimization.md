---
title: Afbeeldingen optimaliseren op moderne sitepagina's van SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 03/11/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.reviewer: sstewart
search.appverid:
- MET150
description: Lees hoe u de hulpmiddelen in SharePoint Online kunt gebruiken om afbeeldingen te optimaliseren op moderne sitepagina's van SharePoint Online.
ms.openlocfilehash: a4f2def86e1378a9fb76ae9ecbe6a55da75ecffc
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923014"
---
# <a name="optimize-images-in-sharepoint-online-modern-site-pages"></a><span data-ttu-id="54556-103">Afbeeldingen optimaliseren op moderne sitepagina's van SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="54556-103">Optimize images in SharePoint Online modern site pages</span></span>

<span data-ttu-id="54556-104">In dit artikel vindt u meer informatie over het optimaliseren van afbeeldingen op moderne sitepagina's van SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="54556-104">This article will help you understand how to optimize images in SharePoint Online modern site pages.</span></span>

<span data-ttu-id="54556-105">Zie Afbeeldingsoptimalisatie voor [SharePoint Online](image-optimization-for-sharepoint-online.md)voor informatie over het optimaliseren van afbeeldingen in klassieke publicatiesites.</span><span class="sxs-lookup"><span data-stu-id="54556-105">For information about optimizing images in classic publishing sites, see [Image optimization for SharePoint Online](image-optimization-for-sharepoint-online.md)..</span></span>

>[!NOTE]
><span data-ttu-id="54556-106">Zie Prestaties in de [moderne SharePoint-ervaring](/sharepoint/modern-experience-performance)voor meer informatie over de prestaties in moderne SharePoint Online-portals.</span><span class="sxs-lookup"><span data-stu-id="54556-106">For more information about performance in SharePoint Online modern portals, see [Performance in the modern SharePoint experience](/sharepoint/modern-experience-performance).</span></span>

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-image-optimization"></a><span data-ttu-id="54556-107">Het hulpprogramma Paginadiagnose voor SharePoint gebruiken om afbeeldingsoptimalisatie te analyseren</span><span class="sxs-lookup"><span data-stu-id="54556-107">Use the Page Diagnostics for SharePoint tool to analyze image optimization</span></span>

<span data-ttu-id="54556-108">Het hulpprogramma Paginadiagnose voor SharePoint is een browserextensie voor de nieuwe Microsoft Edge - en Chrome-browsers waarmee zowel moderne portals van SharePoint Online als klassieke https://www.microsoft.com/edge) publicerende sitepagina's worden geanalyseerd.</span><span class="sxs-lookup"><span data-stu-id="54556-108">The Page Diagnostics for SharePoint tool is a browser extension for the new Microsoft Edge (https://www.microsoft.com/edge) and Chrome browsers that analyzes both SharePoint Online modern portal and classic publishing site pages.</span></span> <span data-ttu-id="54556-109">Het hulpprogramma bevat een rapport voor elke geanalyseerde pagina die laat zien hoe de pagina presteert op basis van een gedefinieerde set prestatiecriteria.</span><span class="sxs-lookup"><span data-stu-id="54556-109">The tool provides a report for each analyzed page showing how the page performs against a defined set of performance criteria.</span></span> <span data-ttu-id="54556-110">Als u het hulpprogramma Paginadiagnose voor SharePoint wilt installeren en meer wilt weten, gaat u naar Het hulpprogramma [Paginadiagnose gebruiken voor SharePoint Online.](page-diagnostics-for-spo.md)</span><span class="sxs-lookup"><span data-stu-id="54556-110">To install and learn about the Page Diagnostics for SharePoint tool, visit [Use the Page Diagnostics tool for SharePoint Online](page-diagnostics-for-spo.md).</span></span>

>[!NOTE]
><span data-ttu-id="54556-111">Het hulpprogramma Paginadiagnose werkt alleen voor SharePoint Online en kan niet worden gebruikt op een SharePoint-systeempagina.</span><span class="sxs-lookup"><span data-stu-id="54556-111">The Page Diagnostics tool only works for SharePoint Online, and cannot be used on a SharePoint system page.</span></span>

<span data-ttu-id="54556-112">Wanneer u een moderne SharePoint-site analyseert met het hulpprogramma Paginadiagnose voor SharePoint, ziet u informatie over grote afbeeldingen in het deelvenster _Diagnostische tests._</span><span class="sxs-lookup"><span data-stu-id="54556-112">When you analyze a SharePoint modern site with the Page Diagnostics for SharePoint tool, you can see information about large images in the _Diagnostic tests_ pane.</span></span>

<span data-ttu-id="54556-113">Mogelijke resultaten zijn:</span><span class="sxs-lookup"><span data-stu-id="54556-113">Possible results include:</span></span>

- <span data-ttu-id="54556-114">**Aandacht vereist** (rood): De pagina bevat **een of meer** afbeeldingen van meer dan 300 KB in grootte</span><span class="sxs-lookup"><span data-stu-id="54556-114">**Attention required** (red): The page contains **one or more** images over 300KB in size</span></span>
- <span data-ttu-id="54556-115">**Geen actie vereist** (groen): De pagina bevat geen afbeeldingen van meer dan 300 KB in grootte</span><span class="sxs-lookup"><span data-stu-id="54556-115">**No action required** (green): The page contains no images over 300KB in size</span></span>

<span data-ttu-id="54556-116">Als het **gedetecteerde resultaat Grote**  afbeeldingen wordt weergegeven in de sectie Aandacht vereist van de resultaten, kunt u op het resultaat klikken om meer informatie te zien.</span><span class="sxs-lookup"><span data-stu-id="54556-116">If the **Large images detected** result appears in the **Attention required** section of the results, you can click the result to see additional details.</span></span>

![Resultaten van het hulpprogramma Paginadiagnose](../media/modern-portal-optimization/pagediag-large-images.png)

## <a name="remediate-large-image-issues"></a><span data-ttu-id="54556-118">Grote problemen met afbeeldingen oplossen</span><span class="sxs-lookup"><span data-stu-id="54556-118">Remediate large image issues</span></span>

<span data-ttu-id="54556-119">Als een pagina afbeeldingen van meer dan 300 KB groot bevat, selecteert u het resultaat Grote afbeeldingen gedetecteerd om te zien welke afbeeldingen te groot zijn. </span><span class="sxs-lookup"><span data-stu-id="54556-119">If a page contains images over 300KB in size, select the **Large images detected** result to see which images are too large.</span></span> <span data-ttu-id="54556-120">Op moderne SharePoint Online-pagina's worden afbeeldingen automatisch weergegeven en de grootte is afhankelijk van de grootte van het browservenster en de resolutie van de clientmonitor.</span><span class="sxs-lookup"><span data-stu-id="54556-120">In modern SharePoint Online pages, renditions of images are automatically provided and sized depending on the size of the browser window and the resolution of the client monitor.</span></span> <span data-ttu-id="54556-121">U moet afbeeldingen altijd optimaliseren voor webgebruik voordat u ze uploadt naar SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="54556-121">You should always optimize images for web use prior to upload to SharePoint Online.</span></span> <span data-ttu-id="54556-122">Zeer grote afbeeldingen worden automatisch verkleind in grootte en resolutie, wat kan leiden tot onverwachte weergavekenmerken.</span><span class="sxs-lookup"><span data-stu-id="54556-122">Very large images will be automatically reduced in size and resolution which can result in unexpected rendering characteristics.</span></span>

<span data-ttu-id="54556-123">Voordat u paginaherzieningen maakt om prestatieproblemen op te lossen, noteert u de laadtijd van de pagina in de analyseresultaten.</span><span class="sxs-lookup"><span data-stu-id="54556-123">Before you make page revisions to remediate performance issues, make a note of the page load time in the analysis results.</span></span> <span data-ttu-id="54556-124">Voer het hulpprogramma na de revisie opnieuw uit om te zien of het nieuwe resultaat binnen de basislijnstandaard valt en controleer de laadtijd van de nieuwe pagina om te zien of er een verbetering is.</span><span class="sxs-lookup"><span data-stu-id="54556-124">Run the tool again after your revision to see if the new result is within the baseline standard, and check the new page load time to see if there was an improvement.</span></span>

![De laadtijd van pagina's](../media/modern-portal-optimization/pagediag-page-load-time.png)

>[!NOTE]
><span data-ttu-id="54556-126">De laadtijd van pagina's kan variëren op basis van verschillende factoren, zoals de netwerkbelasting, de tijd van de dag en andere tijdelijke omstandigheden.</span><span class="sxs-lookup"><span data-stu-id="54556-126">Page load time can vary based on a variety of factors such as network load, time of day, and other transient conditions.</span></span> <span data-ttu-id="54556-127">U moet de laadtijd van pagina's een paar keer voor en na het aanbrengen van wijzigingen testen, zodat u de resultaten kunt gemiddelden.</span><span class="sxs-lookup"><span data-stu-id="54556-127">You should test page load time a few times before and after making changes to help you average the results.</span></span>

## <a name="related-topics"></a><span data-ttu-id="54556-128">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="54556-128">Related topics</span></span>

[<span data-ttu-id="54556-129">Prestaties van SharePoint Online afstemmen</span><span class="sxs-lookup"><span data-stu-id="54556-129">Tune SharePoint Online performance</span></span>](tune-sharepoint-online-performance.md)

[<span data-ttu-id="54556-130">Prestaties van Office 365 afstemmen</span><span class="sxs-lookup"><span data-stu-id="54556-130">Tune Office 365 performance</span></span>](tune-microsoft-365-performance.md)

[<span data-ttu-id="54556-131">Prestaties in de moderne SharePoint-ervaring</span><span class="sxs-lookup"><span data-stu-id="54556-131">Performance in the modern SharePoint experience</span></span>](/sharepoint/modern-experience-performance)

[<span data-ttu-id="54556-132">Netwerken voor contentlevering</span><span class="sxs-lookup"><span data-stu-id="54556-132">Content delivery networks</span></span>](content-delivery-networks.md)

[<span data-ttu-id="54556-133">Het Office 365 Content Delivery Network (CDN) gebruiken met SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="54556-133">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)