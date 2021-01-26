---
title: Een inhoudscentrum maken in Microsoft SharePoint Syntex
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Informatie over het maken van een inhoudscentrum.
ms.openlocfilehash: 4377cbfbda8572fe9e08a079a05146961105298b
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/25/2021
ms.locfileid: "49976529"
---
# <a name="create-a-content-center-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="0fdbe-103">Een inhoudscentrum maken in Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="0fdbe-103">Create a content center in Microsoft SharePoint Syntex</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CPSF]

</br>

<span data-ttu-id="0fdbe-104">Om modellen voor documentbegrip te maken en beheren hebt u eerst een inhoudscentrum nodig.</span><span class="sxs-lookup"><span data-stu-id="0fdbe-104">To create and manage document understanding models, you first need a content center.</span></span> <span data-ttu-id="0fdbe-105">Het inhoudscentrum is de interface voor het maken van modellen en bevat ook informatie over op welke documentbibliotheken gepubliceerde modellen zijn toegepast.</span><span class="sxs-lookup"><span data-stu-id="0fdbe-105">The content center is the model creation interface and also contains information about which document libraries published models have been applied to.</span></span></br>

   ![Een documentbibliotheek selecteren](../media/content-understanding/content-center-page.png)</br>

<span data-ttu-id="0fdbe-107">U maakt een standaardinhoudscentrum tijdens de [installatie](set-up-content-understanding.md).</span><span class="sxs-lookup"><span data-stu-id="0fdbe-107">You create a default content center during [setup](set-up-content-understanding.md).</span></span> <span data-ttu-id="0fdbe-108">Een SharePoint-beheerder kan extra inhoudscentra maken wanneer dat nodig is.</span><span class="sxs-lookup"><span data-stu-id="0fdbe-108">But a SharePoint admin can also choose to create additional centers as needed.</span></span> <span data-ttu-id="0fdbe-109">Hoewel één enkel inhoudscentrum prima geschikt kan zijn voor omgevingen waarin u het overzicht wilt houden van alle modelactiviteiten, wilt u misschien extra inhoudscentra maken voor meerdere afdelingen binnen uw organisatie, die mogelijk verschillende behoeften en machtigingsvereisten voor hun modellen hebben.</span><span class="sxs-lookup"><span data-stu-id="0fdbe-109">While a single content center may be fine for environments for which you want a roll-up of all model activity, you may want to have additional centers for multiple departments within your organization, which may have different needs and permission requirements for their models.</span></span>

> [!NOTE]
> <span data-ttu-id="0fdbe-110">Een SharePoint-beheerder kan een inhoudscentrumsite aanmaken zoals hij [elke andere SharePoint-site zou maken](https://docs.microsoft.com/sharepoint/create-site-collection), via het inrichtingspaneel van het beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="0fdbe-110">A SharePoint admin can create a content center site like they would [create any other SharePoint site](https://docs.microsoft.com/sharepoint/create-site-collection) through the admin center site provisioning panel.</span></span>

<span data-ttu-id="0fdbe-111">Een nieuw inhoudscentrum maken:</span><span class="sxs-lookup"><span data-stu-id="0fdbe-111">To create a new content center:</span></span>

1. <span data-ttu-id="0fdbe-112">Ga in het Microsoft 365-beheercentrum naar het SharePoint-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="0fdbe-112">On the Microsoft 365 admin center, go to the SharePoint admin center.</span></span>
2. <span data-ttu-id="0fdbe-113">Selecteer in het SharePoint-beheercentrum onder **Sites** de optie **Actieve sites**.</span><span class="sxs-lookup"><span data-stu-id="0fdbe-113">On the SharePoint admin center, under **Sites**, select **Active Sites**.</span></span>
3. <span data-ttu-id="0fdbe-114">Klik op de pagina **Actieve sites** op **Maken** en selecteer **Overige opties**.</span><span class="sxs-lookup"><span data-stu-id="0fdbe-114">On the **Active Sites** page, click **Create**, and then select **Other options**.</span></span>
4. <span data-ttu-id="0fdbe-115">Kies in het menu **Sjabloon kiezen** **Inhoudscentrum**.</span><span class="sxs-lookup"><span data-stu-id="0fdbe-115">On the **Choose a template** menu, select **Content Center**.</span></span>
5. <span data-ttu-id="0fdbe-116">Geef voor de nieuwe site een **Sitenaam**, **Primaire beheerder** en **Taal** op.</span><span class="sxs-lookup"><span data-stu-id="0fdbe-116">For the new site, provide a **Site Name**, **Primary administrator**, and a **Language**.</span></span></br>

> [!NOTE] 
> <span data-ttu-id="0fdbe-117">U kunt een inhoudscentrumsite weergeven in elk van de beschikbare talen, maar houd er rekening mee dat u momenteel alleen modellen kunt maken voor Engelstalige bestanden.</span><span class="sxs-lookup"><span data-stu-id="0fdbe-117">You can select a content center site to render in any of the available languages, but note that currently models can only be created for English files.</span></span> <span data-ttu-id="0fdbe-118">Houd er ook rekening mee dat de standaardtaal van de site niet kan worden gewijzigd nadat de site is gemaakt, net zoals bij andere sitesjablonen.</span><span class="sxs-lookup"><span data-stu-id="0fdbe-118">Also note that like other site templates, the default site language isn't editable after the site is created.</span></span></br>

6. <span data-ttu-id="0fdbe-119">Selecteer **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="0fdbe-119">Select **Finished**.</span></span>
 
<span data-ttu-id="0fdbe-120">Nadat u een inhoudscentrumsite hebt gemaakt, wordt het weergegeven op de pagina **Actieve sites** in het SharePoint-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="0fdbe-120">After you create a content center site, you will see it listed on the **Active sites** page in the SharePoint admin center.</span></span> 

### <a name="give-access-to-additional-users"></a><span data-ttu-id="0fdbe-121">Toegang verlenen aan extra gebruikers</span><span class="sxs-lookup"><span data-stu-id="0fdbe-121">Give access to additional users</span></span>
 
<span data-ttu-id="0fdbe-122">Nadat u de site hebt gemaakt, kunt u extra gebruikers toegang geven tot de site via het standaard [SharePoint-sitemachtigingenmodel](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions).</span><span class="sxs-lookup"><span data-stu-id="0fdbe-122">After you create the site, you can give additional users access to the site through the standard [SharePoint site permissions model](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions).</span></span>

## <a name="see-also"></a><span data-ttu-id="0fdbe-123">Zie ook</span><span class="sxs-lookup"><span data-stu-id="0fdbe-123">See Also</span></span>
[<span data-ttu-id="0fdbe-124">Een classificatie maken</span><span class="sxs-lookup"><span data-stu-id="0fdbe-124">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="0fdbe-125">Een extractor maken</span><span class="sxs-lookup"><span data-stu-id="0fdbe-125">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="0fdbe-126">Een inhoudscentrum maken</span><span class="sxs-lookup"><span data-stu-id="0fdbe-126">Create a content center</span></span>](create-a-content-center.md)

[<span data-ttu-id="0fdbe-127">Overzicht van documentbegrip</span><span class="sxs-lookup"><span data-stu-id="0fdbe-127">Document understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="0fdbe-128">Een formulierverwerkingsmodel maken</span><span class="sxs-lookup"><span data-stu-id="0fdbe-128">Create a form processing model</span></span>](create-a-form-processing-model.md)

[<span data-ttu-id="0fdbe-129">Een model toepassen</span><span class="sxs-lookup"><span data-stu-id="0fdbe-129">Apply a model</span></span>](apply-a-model.md)    
