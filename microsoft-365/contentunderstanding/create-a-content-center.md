---
title: Een inhouds centrum maken in Microsoft SharePoint Syntex
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Leer hoe u een inhouds centrum maakt.
ms.openlocfilehash: 62977bc5a34b041e9e958ff46e0dbc010d6bd822
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295430"
---
# <a name="create-a-content-center-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="f9b5e-103">Een inhouds centrum maken in Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="f9b5e-103">Create a content center in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="f9b5e-104">De inhoud in dit artikel is bedoeld voor de cortex van de private preview van project.</span><span class="sxs-lookup"><span data-stu-id="f9b5e-104">The content in this article is for the Project Cortex Private Preview.</span></span> <span data-ttu-id="f9b5e-105">[Lees meer over project cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="f9b5e-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span></br>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CPSF]

</br>

<span data-ttu-id="f9b5e-106">Voor het maken en beheren van documenten met modellen hebt u eerst een inhouds centrum nodig.</span><span class="sxs-lookup"><span data-stu-id="f9b5e-106">To create and manage document understanding models, you first need a content center.</span></span> <span data-ttu-id="f9b5e-107">Het inhouds centrum is de interface voor het maken van modellen en bevat ook informatie over de documentenbibliotheken waarop publicerende modellen zijn toegepast.</span><span class="sxs-lookup"><span data-stu-id="f9b5e-107">The content center is the model creation interface and also contains information about which document libraries published models have been applied to.</span></span></br>

   ![Een documentbibliotheek selecteren](../media/content-understanding/content-center-page.png)</br>

<span data-ttu-id="f9b5e-109">U maakt een initieel inhouds centrum tijdens de [installatie](set-up-content-understanding.md).</span><span class="sxs-lookup"><span data-stu-id="f9b5e-109">You create an initial content center during [setup](set-up-content-understanding.md).</span></span> <span data-ttu-id="f9b5e-110">Een SharePoint-beheerder kan er ook voor kiezen om zo nodig extra centra te maken.</span><span class="sxs-lookup"><span data-stu-id="f9b5e-110">But a SharePoint admin can also choose to create additional centers as needed.</span></span> <span data-ttu-id="f9b5e-111">Hoewel een enkelvoudig inhouds centrum voor omgevingen waarvan u een totalisatie van alle model activiteiten wilt uitvouwen, kan het handig zijn om een extra centrum te hebben voor meerdere afdelingen binnen uw organisatie, welke verschillende behoeften en vereisten voor hun modellen kunnen hebben.</span><span class="sxs-lookup"><span data-stu-id="f9b5e-111">While a single content center may be fine for environments for which you want a roll-up of all model activity, you may want to have additional centers for multiple departments within your organization, which may have different needs and requirements for their models.</span></span>

> [!NOTE]
> <span data-ttu-id="f9b5e-112">Een SharePoint-beheerder kan een inhouds centrum site maken alsof ze een [andere SharePoint-site maken](https://docs.microsoft.com/sharepoint/create-site-collection) op basis van een sitesjabloon.</span><span class="sxs-lookup"><span data-stu-id="f9b5e-112">A SharePoint admin can create a content center site like they would [create any other SharePoint site](https://docs.microsoft.com/sharepoint/create-site-collection) by using a site template.</span></span>

<span data-ttu-id="f9b5e-113">Een nieuw inhouds centrum maken:</span><span class="sxs-lookup"><span data-stu-id="f9b5e-113">To create a new content center:</span></span>

1. <span data-ttu-id="f9b5e-114">Ga in het Microsoft 365-Beheercentrum naar het SharePoint-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="f9b5e-114">From the Microsoft 365 admin center, go to the SharePoint admin center.</span></span>
2. <span data-ttu-id="f9b5e-115">Selecteer in het SharePoint-Beheercentrum, onder **sites**, de optie **actieve sites**.</span><span class="sxs-lookup"><span data-stu-id="f9b5e-115">In the SharePoint admin center, under **Sites**, select **Active Sites**.</span></span>
3. <span data-ttu-id="f9b5e-116">Klik op de pagina **actieve sites** op **maken**en selecteer vervolgens **andere opties**.</span><span class="sxs-lookup"><span data-stu-id="f9b5e-116">On the **Active Sites** page, click **Create**, and then select **Other options**.</span></span>
4. <span data-ttu-id="f9b5e-117">Selecteer in het menu **een sjabloon kiezen** de optie **inhouds centrum**.</span><span class="sxs-lookup"><span data-stu-id="f9b5e-117">On the **Choose a template** menu, select **Content Center**.</span></span>
5. <span data-ttu-id="f9b5e-118">Geef voor de nieuwe site een **sitenaam**, **primaire beheerder**en een **taal**op.</span><span class="sxs-lookup"><span data-stu-id="f9b5e-118">For the new site, provide a **Site Name**, **Primary administrator**, and a **Language**.</span></span></br>

> [!NOTE] 
> <span data-ttu-id="f9b5e-119">U kunt desgewenst een inhouds centrum site selecteren om weer te geven in een van de beschikbare talen.</span><span class="sxs-lookup"><span data-stu-id="f9b5e-119">You can optionally select a content center site to render in any of the available languages.</span></span> <span data-ttu-id="f9b5e-120">Alleen huidige modellen kunnen worden gemaakt voor Engelse bestanden.</span><span class="sxs-lookup"><span data-stu-id="f9b5e-120">Only current models can be created for English files.</span></span></br>

6. <span data-ttu-id="f9b5e-121">Selecteer **Gereedgemeld**.</span><span class="sxs-lookup"><span data-stu-id="f9b5e-121">Select **Finished**.</span></span>

### <a name="give-access-to-additional-users"></a><span data-ttu-id="f9b5e-122">Toegang verlenen aan extra gebruikers</span><span class="sxs-lookup"><span data-stu-id="f9b5e-122">Give access to additional users</span></span>
 
<span data-ttu-id="f9b5e-123">Wanneer u de site hebt gemaakt, kunt u extra gebruikers toegang geven tot de site via het standaard [model van SharePoint-site machtigingen](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions).</span><span class="sxs-lookup"><span data-stu-id="f9b5e-123">After you create the site, you can give additional users access to the site through the standard [SharePoint site permissions model](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions).</span></span>

## <a name="see-also"></a><span data-ttu-id="f9b5e-124">Zie ook</span><span class="sxs-lookup"><span data-stu-id="f9b5e-124">See Also</span></span>
[<span data-ttu-id="f9b5e-125">Een classificatie maken</span><span class="sxs-lookup"><span data-stu-id="f9b5e-125">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="f9b5e-126">Een extractor maken</span><span class="sxs-lookup"><span data-stu-id="f9b5e-126">Create an extractor</span></span>](create-an-extractor.md)</br>
<span data-ttu-id="f9b5e-127">[Een inhouds centrum maken](create-a-content-center.md) 
 [Overzicht van document](document-understanding-overview.md)</span><span class="sxs-lookup"><span data-stu-id="f9b5e-127">[Create a content center](create-a-content-center.md)
[Document understanding overview](document-understanding-overview.md)</span></span></br>
[<span data-ttu-id="f9b5e-128">Een formulier verwerkings model maken</span><span class="sxs-lookup"><span data-stu-id="f9b5e-128">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>
[<span data-ttu-id="f9b5e-129">Een model toepassen</span><span class="sxs-lookup"><span data-stu-id="f9b5e-129">Apply a model</span></span>](apply-a-model.md)    
