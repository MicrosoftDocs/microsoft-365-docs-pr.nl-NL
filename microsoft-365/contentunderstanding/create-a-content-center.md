---
title: Een inhouds centrum maken (preview)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Leer hoe u een inhouds centrum maakt.
ms.openlocfilehash: ae10cdae2fe84abf72cf09141798b628d88a504a
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950094"
---
# <a name="create-a-content-center-preview"></a><span data-ttu-id="02d5b-103">Een inhouds centrum maken (preview)</span><span class="sxs-lookup"><span data-stu-id="02d5b-103">Create a content center (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="02d5b-104">De inhoud in dit artikel is bedoeld voor project cortex private preview.</span><span class="sxs-lookup"><span data-stu-id="02d5b-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="02d5b-105">[Lees meer over project cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="02d5b-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span></br>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CPSF]

</br>

<span data-ttu-id="02d5b-106">Voor het maken en beheren van documenten met modellen hebt u eerst een inhouds centrum nodig.</span><span class="sxs-lookup"><span data-stu-id="02d5b-106">To create and manage document understanding models, you first need a content center.</span></span> <span data-ttu-id="02d5b-107">Het inhouds centrum is de interface voor het maken van modellen en bevat ook informatie over de publicatie van documentbibliotheken gepubliceerde modellen.</span><span class="sxs-lookup"><span data-stu-id="02d5b-107">The content center is the model creation interface and also contains information about which document libraries published models have been applied.</span></span></br>

   ![Een documentbibliotheek selecteren](../media/content-understanding/content-center-page.png)</br>

<span data-ttu-id="02d5b-109">Er wordt een initieel inhouds centrum gemaakt tijdens de [installatie](set-up-content-understanding.md), maar een SharePoint-beheerder kan desgewenst extra bestanden maken.</span><span class="sxs-lookup"><span data-stu-id="02d5b-109">An initial content center is created during [setup](set-up-content-understanding.md), but a SharePoint admin can choose to create additional ones as needed.</span></span> <span data-ttu-id="02d5b-110">Hoewel een bepaald inhouds centrum geschikt is voor omgevingen waarvan u een uitvouwing van alle model activiteiten wilt zien, kunt u deze mogelijk extra weergeven als uw organisatie meerdere afdelingen binnen uw organisatie heeft die verschillende behoeften en vereisten voor hun modellen hebben.</span><span class="sxs-lookup"><span data-stu-id="02d5b-110">While a single content center may be fine for environments in which you want to see a roll-up of all model activity, you may want to have additional ones if your have multiple departments within your organization that may have different needs and requirements for their models.</span></span>

<span data-ttu-id="02d5b-111">Een SharePoint-beheerder kan een inhouds centrum site maken alsof deze een [andere SharePoint-site maakt](https://docs.microsoft.com/sharepoint/create-site-collection) , via een sitesjabloon.</span><span class="sxs-lookup"><span data-stu-id="02d5b-111">A SharePoint admin can create a content center site like they would [create any other SharePoint site](https://docs.microsoft.com/sharepoint/create-site-collection) - through a site template.</span></span>

<span data-ttu-id="02d5b-112">Een nieuw inhouds centrum maken:</span><span class="sxs-lookup"><span data-stu-id="02d5b-112">To create a new content center:</span></span>

1. <span data-ttu-id="02d5b-113">Ga in het Microsoft 365-Beheercentrum naar het SharePoint-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="02d5b-113">On the Microsoft 365 admin center, go to the SharePoint admin center.</span></span>
2. <span data-ttu-id="02d5b-114">Selecteer in het SharePoint-Beheercentrum, onder **sites**, de optie **actieve sites**.</span><span class="sxs-lookup"><span data-stu-id="02d5b-114">On the SharePoint admin center, under **Sites**, select **Active Sites**.</span></span>
3. <span data-ttu-id="02d5b-115">Klik op de pagina **actieve sites** op **maken**en selecteer vervolgens **andere opties**.</span><span class="sxs-lookup"><span data-stu-id="02d5b-115">On the **Active Sites** page, click **Create**, and then select **Other options**.</span></span>
4. <span data-ttu-id="02d5b-116">Selecteer in het menu **een sjabloon kiezen** de optie **inhouds centrum**.</span><span class="sxs-lookup"><span data-stu-id="02d5b-116">On the **Choose a template** menu, select **Content Center**.</span></span>
5. <span data-ttu-id="02d5b-117">Geef voor de nieuwe site een **sitenaam**, **primaire beheerder**en een **taal**op.</span><span class="sxs-lookup"><span data-stu-id="02d5b-117">For the new site, provide a **Site Name**, **Primary administrator**, and a **Language**.</span></span></br>

> [!Note] 
> <span data-ttu-id="02d5b-118">U kunt een inhouds centrum site selecteren om weer te geven in een van de beschikbare talen, maar houd er rekening mee dat momenteel alleen voor Engelse bestanden kunnen worden gemaakt.</span><span class="sxs-lookup"><span data-stu-id="02d5b-118">You can select a content center site to render in any of the available languages, but note that currently models can only be created for English files.</span></span></br>

6. <span data-ttu-id="02d5b-119">Klik op **gereed**.</span><span class="sxs-lookup"><span data-stu-id="02d5b-119">Click **Finished**.</span></span>

### <a name="give-access-to-additional-users"></a><span data-ttu-id="02d5b-120">Toegang verlenen aan extra gebruikers</span><span class="sxs-lookup"><span data-stu-id="02d5b-120">Give access to additional users</span></span>
 
<span data-ttu-id="02d5b-121">Nadat de site is gemaakt, kunt u extra gebruikers toegang geven tot de site via het standaard [model van SharePoint-site machtigingen](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions).</span><span class="sxs-lookup"><span data-stu-id="02d5b-121">After the site is created, you can give additional users access to the site through the standard [SharePoint site permissions model](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions).</span></span>





## <a name="see-also"></a><span data-ttu-id="02d5b-122">Zie ook</span><span class="sxs-lookup"><span data-stu-id="02d5b-122">See Also</span></span>
[<span data-ttu-id="02d5b-123">Een classificatie maken</span><span class="sxs-lookup"><span data-stu-id="02d5b-123">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="02d5b-124">Een extractor maken</span><span class="sxs-lookup"><span data-stu-id="02d5b-124">Create an extractor</span></span>](create-an-extractor.md)</br>
<span data-ttu-id="02d5b-125">[Een inhouds centrum maken](create-a-content-center.md) 
 [Overzicht van document](document-understanding-overview.md)</span><span class="sxs-lookup"><span data-stu-id="02d5b-125">[Create a content center](create-a-content-center.md)
[Document understanding overview](document-understanding-overview.md)</span></span></br>
[<span data-ttu-id="02d5b-126">Een formulier verwerkings model maken</span><span class="sxs-lookup"><span data-stu-id="02d5b-126">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>
[<span data-ttu-id="02d5b-127">Een model toepassen</span><span class="sxs-lookup"><span data-stu-id="02d5b-127">Apply a model</span></span>](apply-a-model.md)    




