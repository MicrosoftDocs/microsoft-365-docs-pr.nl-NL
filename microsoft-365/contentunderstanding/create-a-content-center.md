---
title: Een inhoudscentrum maken (Voorbeeld)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Meer informatie over het maken van een inhoudscentrum.
ms.openlocfilehash: ced47f8029079910479dd9aa5c43b39870a56aea
ms.sourcegitcommit: ea5e2f85bd6b609658545b120c7e08789b9686fd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/01/2020
ms.locfileid: "46537223"
---
# <a name="create-a-content-center-preview"></a><span data-ttu-id="90038-103">Een inhoudscentrum maken (Voorbeeld)</span><span class="sxs-lookup"><span data-stu-id="90038-103">Create a content center (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="90038-104">De inhoud in dit artikel is voor Project Cortex Private Preview.</span><span class="sxs-lookup"><span data-stu-id="90038-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="90038-105">[Lees meer over Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="90038-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span></br>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CPSF]

</br>

<span data-ttu-id="90038-106">Als u modellen voor het begrijpen van documenten wilt maken en beheren, hebt u eerst een inhoudscentrum nodig.</span><span class="sxs-lookup"><span data-stu-id="90038-106">To create and manage document understanding models, you first need a content center.</span></span> <span data-ttu-id="90038-107">Het inhoudscentrum is de interface voor het maken van modellen en bevat ook informatie over welke documentbibliotheken gepubliceerde modellen zijn toegepast.</span><span class="sxs-lookup"><span data-stu-id="90038-107">The content center is the model creation interface and also contains information about which document libraries published models have been applied.</span></span></br>

   ![Een documentbibliotheek selecteren](../media/content-understanding/content-center-page.png)</br>

<span data-ttu-id="90038-109">Tijdens de [installatie](set-up-content-understanding.md)wordt een eerste inhoudscentrum gemaakt, maar een SharePoint-beheerder kan ervoor kiezen om indien nodig extra te maken.</span><span class="sxs-lookup"><span data-stu-id="90038-109">An initial content center is created during [setup](set-up-content-understanding.md), but a SharePoint admin can choose to create additional ones as needed.</span></span> <span data-ttu-id="90038-110">Hoewel een enkel inhoudscentrum mogelijk prima is voor omgevingen waarin u een oprol van alle modelactiviteit wilt zien, u extra services hebben als u meerdere afdelingen binnen uw organisatie hebt die mogelijk verschillende behoeften en vereisten voor hun modellen hebben.</span><span class="sxs-lookup"><span data-stu-id="90038-110">While a single content center may be fine for environments in which you want to see a roll-up of all model activity, you may want to have additional ones if your have multiple departments within your organization that may have different needs and requirements for their models.</span></span>

<span data-ttu-id="90038-111">Een SharePoint-beheerder kan een inhoudscentrumsite maken zoals elke [andere SharePoint-site](https://docs.microsoft.com/sharepoint/create-site-collection) zou maken via een sitesjabloon.</span><span class="sxs-lookup"><span data-stu-id="90038-111">A SharePoint admin can create a content center site like they would [create any other SharePoint site](https://docs.microsoft.com/sharepoint/create-site-collection) - through a site template.</span></span>

<span data-ttu-id="90038-112">Ga als een nieuw inhoudscentrum:</span><span class="sxs-lookup"><span data-stu-id="90038-112">To create a new content center:</span></span>

1. <span data-ttu-id="90038-113">Ga in het Microsoft 365-beheercentrum naar het SharePoint-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="90038-113">On the Microsoft 365 admin center, go to the SharePoint admin center.</span></span>
2. <span data-ttu-id="90038-114">Selecteer in het SharePoint-beheercentrum onder **Sites**de optie **Actieve sites**.</span><span class="sxs-lookup"><span data-stu-id="90038-114">On the SharePoint admin center, under **Sites**, select **Active Sites**.</span></span>
3. <span data-ttu-id="90038-115">Klik op de pagina **Actieve sites** op **Maken**en selecteer **Vervolgens Andere opties**.</span><span class="sxs-lookup"><span data-stu-id="90038-115">On the **Active Sites** page, click **Create**, and then select **Other options**.</span></span>
4. <span data-ttu-id="90038-116">Selecteer **inhoudscentrum**in het menu Kies een **sjabloon** .</span><span class="sxs-lookup"><span data-stu-id="90038-116">On the **Choose a template** menu, select **Content Center**.</span></span>
5. <span data-ttu-id="90038-117">Geef voor de nieuwe site een **sitenaam,** **primaire beheerder**en een **taal**op .</span><span class="sxs-lookup"><span data-stu-id="90038-117">For the new site, provide a **Site Name**, **Primary administrator**, and a **Language**.</span></span></br>

> [!Note] 
> <span data-ttu-id="90038-118">U een inhoudscentrumsite selecteren die u wilt weergeven in een van de beschikbare talen, maar houd er rekening mee dat momenteel alleen modellen kunnen worden gemaakt voor Engelse bestanden.</span><span class="sxs-lookup"><span data-stu-id="90038-118">You can select a content center site to render in any of the available languages, but note that currently models can only be created for English files.</span></span></br>

6. <span data-ttu-id="90038-119">Klik **op Voltooid**.</span><span class="sxs-lookup"><span data-stu-id="90038-119">Click **Finished**.</span></span>

### <a name="give-access-to-additional-users"></a><span data-ttu-id="90038-120">Geef toegang tot extra gebruikers</span><span class="sxs-lookup"><span data-stu-id="90038-120">Give access to additional users</span></span>
 
<span data-ttu-id="90038-121">Nadat de site is gemaakt, u extra gebruikers toegang geven tot de site via het standaard [model voor machtigingen voor SharePoint-site.](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions)</span><span class="sxs-lookup"><span data-stu-id="90038-121">After the site is created, you can give additional users access to the site through the standard [SharePoint site permissions model](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions).</span></span>





## <a name="see-also"></a><span data-ttu-id="90038-122">Zie ook</span><span class="sxs-lookup"><span data-stu-id="90038-122">See Also</span></span>
[<span data-ttu-id="90038-123">Een classificatie maken</span><span class="sxs-lookup"><span data-stu-id="90038-123">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="90038-124">Een afzuiger maken</span><span class="sxs-lookup"><span data-stu-id="90038-124">Create an extractor</span></span>](create-an-extractor.md)</br>
<span data-ttu-id="90038-125">[Een inhoudscentrum maken](create-a-content-center.md) 
 [Overzicht van documentbegrip](document-understanding-overview.md)</span><span class="sxs-lookup"><span data-stu-id="90038-125">[Create a content center](create-a-content-center.md)
[Document understanding overview](document-understanding-overview.md)</span></span></br>
[<span data-ttu-id="90038-126">Een formulierverwerkingsmodel maken</span><span class="sxs-lookup"><span data-stu-id="90038-126">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>
[<span data-ttu-id="90038-127">Een model toepassen</span><span class="sxs-lookup"><span data-stu-id="90038-127">Apply a model</span></span>](apply-a-model.md)    




