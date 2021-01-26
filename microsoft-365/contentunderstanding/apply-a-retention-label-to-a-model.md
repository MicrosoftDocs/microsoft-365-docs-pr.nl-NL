---
title: Een retentietag toepassen op een documentbegripmodel
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
description: In dit artikel wordt uitgelegd hoe u een retentietag kunt toepassen op een documentbegripmodel
ms.openlocfilehash: 6dcd81b580b7bf0801641bbd019e1b99ecfe7338
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/25/2021
ms.locfileid: "49976553"
---
# <a name="apply-a-retention-label-to-a-document-understanding-model"></a><span data-ttu-id="c14f2-103">Een retentietag toepassen op een documentbegripmodel</span><span class="sxs-lookup"><span data-stu-id="c14f2-103">Apply a retention label to a document understanding model</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GydO]  

</br>


<span data-ttu-id="c14f2-104">U kunt eenvoudig een [retentietag](https://docs.microsoft.com/microsoft-365/compliance/retention) toepassen op een documentbegripmodel in Microsoft SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="c14f2-104">You can easily apply a [retention label](https://docs.microsoft.com/microsoft-365/compliance/retention) to a document understanding model in Microsoft SharePoint Syntex.</span></span>

<span data-ttu-id="c14f2-105">Met retentietags kunt u retentie-instellingen toepassen op de documenten die door uw documentbegripmodellen worden geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="c14f2-105">Retention labels let you apply retention settings to the documents that your document understanding models identify.</span></span>  <span data-ttu-id="c14f2-106">Bijvoorbeeld: u wilt dat uw model niet alleen alle documenten met *verzekeringskennisgevingen* die naar uw documentbibliotheek worden geüpload identificeert, maar ook een retentietag *zakelijk* aanbrengt, zodat deze documenten niet uit de documentbibliotheek kunnen worden verwijderd gedurende de opgegeven periode (bijvoorbeeld de komende vijf maanden).</span><span class="sxs-lookup"><span data-stu-id="c14f2-106">For example, you want your model to not only identify any *Insurance notice* documents that are uploaded to your document library, but to also apply a *Business* retention tag to them so that these documents cannot be deleted from the document library for the specified time period (the next five months, for example).</span></span>

<span data-ttu-id="c14f2-107">U kunt een bestaande retentietag toepassen op uw documentbegripmodel via de modelinstellingen op de startpagina van uw model.</span><span class="sxs-lookup"><span data-stu-id="c14f2-107">You can apply a pre-existing retention label to your document understanding model through your model settings on your model's home page.</span></span> 

> [!Important]
> <span data-ttu-id="c14f2-108">Als u wilt dat retentietags beschikbaar zijn voor uw inhoudsbegripmodel, moeten deze worden [gemaakt en gepubliceerd in het Microsoft 365-compliancecentrum](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="c14f2-108">For retention labels to be available to apply to your content understanding model, they need to be [created and published in the Microsoft 365 Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels).</span></span>

## <a name="to-add-a-retention-label-to-a-document-understanding-model"></a><span data-ttu-id="c14f2-109">Een retentietag toepassen op een documentbegripmodel</span><span class="sxs-lookup"><span data-stu-id="c14f2-109">To add a retention label to a document understanding model</span></span>

1. <span data-ttu-id="c14f2-110">Selecteren **Modelinstellingen** op de startpagina van het model.</span><span class="sxs-lookup"><span data-stu-id="c14f2-110">From the model home page, select **Model settings**.</span></span></br>
2. <span data-ttu-id="c14f2-111">Selecteer in **Modelinstellingen**, in het gedeelte **Beveiliging en compliance**, het menu **Retentietag** om een lijst met retentietags weer te geven die beschikbaar zijn om toe te passen op het model.</span><span class="sxs-lookup"><span data-stu-id="c14f2-111">In **Model settings**, in the **Security and compliance** section, select the **Retention label** menu to see a list of retention labels that are available for your to apply to the model.</span></span></br>
 <span data-ttu-id="c14f2-112">![Menu Retentietag](../media/content-understanding/retention-labels-menu.png)</span><span class="sxs-lookup"><span data-stu-id="c14f2-112">![Retention label menu](../media/content-understanding/retention-labels-menu.png)</span></span></br> 
3. <span data-ttu-id="c14f2-113">Selecteer de retentietag die u wilt toepassen op het model en selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="c14f2-113">Select the retention label you want to apply to the model, and then select **Save**.</span></span></br>

<span data-ttu-id="c14f2-114">Nadat u de retentietag hebt toegepast op uw model, kunt u het toepassen op een:</span><span class="sxs-lookup"><span data-stu-id="c14f2-114">After applying the retention label to your model, you are able to apply it to a:</span></span>
- <span data-ttu-id="c14f2-115">Nieuwe documentbibliotheek</span><span class="sxs-lookup"><span data-stu-id="c14f2-115">New document library</span></span>
- <span data-ttu-id="c14f2-116">Documentbibliotheek waarop het model al is toegepast</span><span class="sxs-lookup"><span data-stu-id="c14f2-116">Document library to which the model is already applied</span></span>
 
## <a name="apply-the-retention-label-to-a-document-library-to-which-the-model-is-already-applied"></a><span data-ttu-id="c14f2-117">De retentietag toepassen op een documentbibliotheek waarop het model al is toegepast</span><span class="sxs-lookup"><span data-stu-id="c14f2-117">Apply the retention label to a document library to which the model is already applied</span></span>

<span data-ttu-id="c14f2-118">Als uw documentbegripmodel al is toegepast op een documentbibliotheek, kunt u het volgende doen om de retentietagupdate te synchroniseren en toe te passen op de documentbibliotheek:</span><span class="sxs-lookup"><span data-stu-id="c14f2-118">If your document understanding model has already been applied to a document library, you can do the following to sync your retention label update to apply it to the document library:</span></span></br>

1. <span data-ttu-id="c14f2-119">Selecteer op de startpagina van het model in het gedeelte **Bibliotheken met dit model** de documentbibliotheek waarop u de retentietagupdate wilt toepassen.</span><span class="sxs-lookup"><span data-stu-id="c14f2-119">On your model home page, in the **Libraries with this model** section, select the document library to which you want to apply the retention label update.</span></span> </br> 
2. <span data-ttu-id="c14f2-120">Selecteer **Synchroniseren**.</span><span class="sxs-lookup"><span data-stu-id="c14f2-120">Select **Sync**.</span></span> </br>
 <span data-ttu-id="c14f2-121">![Model synchroniseren](../media/content-understanding/sync-model.png)</span><span class="sxs-lookup"><span data-stu-id="c14f2-121">![Sync model](../media/content-understanding/sync-model.png)</span></span></br> 


<span data-ttu-id="c14f2-122">Nadat u de update hebt toegepast en gesynchroniseerd met uw model, kunt u het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="c14f2-122">After applying the update and syncing it to your model, you can confirm that it has been applied by doing the following:</span></span>

1. <span data-ttu-id="c14f2-123">Klik in het inhoudscentrum in het gedeelte **Bibliotheken met deze model** op de bibliotheek waarop het bijgewerkte model is toegepast.</span><span class="sxs-lookup"><span data-stu-id="c14f2-123">In the content center, in the **Libraries with this model** section, click on the library to which your updated model was applied.</span></span> </br>
2. <span data-ttu-id="c14f2-124">Selecteer in de documentbibliotheekweergave het informatiepictogram om de modeleigenschappen te bekijken.</span><span class="sxs-lookup"><span data-stu-id="c14f2-124">In your document library view, select the information icon to check the model properties.</span></span></br>  
3. <span data-ttu-id="c14f2-125">Selecteer in de lijst **Actieve modellen** het bijgewerkte model.</span><span class="sxs-lookup"><span data-stu-id="c14f2-125">In the **Active models** list, select your updated model.</span></span></br>
4. <span data-ttu-id="c14f2-126">In het gedeelte **Retentietag** wordt de naam van de toegepaste retentietag weergegeven.</span><span class="sxs-lookup"><span data-stu-id="c14f2-126">In the **Retention label** section you will see the name of the applied retention label.</span></span></br>


<span data-ttu-id="c14f2-127">Op de pagina met de weergave van uw model in uw documentbibliotheek wordt er een nieuwe kolom **Retentietag** weergegeven.</span><span class="sxs-lookup"><span data-stu-id="c14f2-127">On your model's view page in your document library, a new **Retention label** column will display.</span></span>  <span data-ttu-id="c14f2-128">Omdat uw model bestanden classificeert die het identificeert als het relevante inhoudstype en ze vermeldt in de bibliotheekweergave, bevat de kolom Retentietag ook de naam van de retentietag die via het model is toegepast.</span><span class="sxs-lookup"><span data-stu-id="c14f2-128">As your model classifies files it identifies as belonging to it's content type and lists them in the library view, the Retention label column will also display the name of the retention label that has been applied to it through the model.</span></span>


<span data-ttu-id="c14f2-129">Bijvoorbeeld: op alle *verzekeringskennisgevingen* die uw model identificeert, wordt ook de retentietag *zakelijk* toegepast, zodat ze gedurende vijf maanden lang niet uit de documentenbibliotheek kunnen worden verwijderd.</span><span class="sxs-lookup"><span data-stu-id="c14f2-129">For example, all *Insurance notice* documents that your model identifies will also have the *Business* retention label applied to them, preventing them from being deleted from the document library for five months.</span></span> <span data-ttu-id="c14f2-130">Als geprobeerd wordt het bestand uit de documentbibliotheek te verwijderen, wordt een foutbericht weergegeven met de mededeling dat het niet is toegestaan vanwege de toegepaste retentietag.</span><span class="sxs-lookup"><span data-stu-id="c14f2-130">If an attempt is made to delete the file from the document library, an error will display saying it is not allowed because of the applied retention label.</span></span>

## <a name="see-also"></a><span data-ttu-id="c14f2-131">Zie ook</span><span class="sxs-lookup"><span data-stu-id="c14f2-131">See Also</span></span>
[<span data-ttu-id="c14f2-132">Een classificatie maken</span><span class="sxs-lookup"><span data-stu-id="c14f2-132">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="c14f2-133">Een extractor maken</span><span class="sxs-lookup"><span data-stu-id="c14f2-133">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="c14f2-134">Overzicht van documentbegrip</span><span class="sxs-lookup"><span data-stu-id="c14f2-134">Document Understanding overview</span></span>](document-understanding-overview.md)


