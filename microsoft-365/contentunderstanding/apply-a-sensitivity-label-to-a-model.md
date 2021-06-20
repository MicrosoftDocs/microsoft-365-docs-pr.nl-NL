---
title: Een gevoeligheidslabel toepassen op een model in Microsoft SharePoint Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Lees hoe u een gevoeligheidslabel kunt toepassen op een model in SharePoint Syntex.
ms.openlocfilehash: 2ddfd6ffe11e8e01e32b6e1b5ddf65763e4ae381
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022412"
---
# <a name="apply-a-sensitivity-label-to-a-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="9af8d-103">Een gevoeligheidslabel toepassen op een model in Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="9af8d-103">Apply a sensitivity label to a model in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="9af8d-104">U kunt eenvoudig een [gevoeligheidslabel](../compliance/sensitivity-labels.md) toepassen op een documentbegripmodel in Microsoft SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="9af8d-104">You can easily apply a [sensitivity label](../compliance/sensitivity-labels.md) to document understanding models in Microsoft SharePoint Syntex.</span></span> <span data-ttu-id="9af8d-105">Deze functie is nog niet beschikbaar voor formulierverwerkingsmodellen.</span><span class="sxs-lookup"><span data-stu-id="9af8d-105">This feature isn't available yet for form processing models.</span></span>

<span data-ttu-id="9af8d-106">Met gevoeligheidslabels kunt u beleid voor versleuteling, delen en voorwaardelijke toegang toepassen op de documenten die uw modellen identificeren.</span><span class="sxs-lookup"><span data-stu-id="9af8d-106">Sensitivity labels let you apply encryption, sharing, and conditional access policies to the documents that your models identify.</span></span> <span data-ttu-id="9af8d-107">U wilt bijvoorbeeld dat uw model niet alleen financiële documenten identificeert die bankrekeningnummers of creditcardnummers bevatten die naar uw documentbibliotheek zijn geüpload, maar ook een gevoeligheidslabel *Versleuteling* erop toepast om te beperken wie toegang heeft tot die inhoud en hoe het kan worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="9af8d-107">For example, you want your model to not only identify any financial documents that contain bank account numbers or credit card numbers that are uploaded to your document library, but also to apply an *Encryption* sensitivity label to them to restrict who can access that content and how it can be used.</span></span> <span data-ttu-id="9af8d-108">Syntex-modellen houden zich aan regels voor [labelvolgorde](../compliance/apply-sensitivity-label-automatically.md?view=o365-worldwide#how-multiple-conditions-are-evaluated-when-they-apply-to-more-than-one-label) en overschrijven ook geen bestaand label dat handmatig door een gebruiker op het bestand is toegepast.</span><span class="sxs-lookup"><span data-stu-id="9af8d-108">Syntex models honor [label order](../compliance/apply-sensitivity-label-automatically.md?view=o365-worldwide#how-multiple-conditions-are-evaluated-when-they-apply-to-more-than-one-label) rules and also do not overwrite an existing label that was manually applied by a user to the file.</span></span> 

<span data-ttu-id="9af8d-109">U kunt een reeds bestaand gevoeligheidslabel op uw model toepassen via uw modelinstellingen op de startpagina van uw model.</span><span class="sxs-lookup"><span data-stu-id="9af8d-109">You can apply a pre-existing sensitivity label to your model through your model settings on your model's home page.</span></span> <span data-ttu-id="9af8d-110">Het label moet al zijn gepubliceerd om te kunnen worden geselecteerd in de modelinstellingen.</span><span class="sxs-lookup"><span data-stu-id="9af8d-110">The label must already be published to be available for selection from model settings.</span></span>

> [!Important]
> <span data-ttu-id="9af8d-111">Als je wilt dat gevoeligheidslabels beschikbaar zijn voor je documentbegripmodel, moeten deze [aangemaakt en gepubliceerd worden in het Microsoft 365-compliancecentrum](../business-video/create-sensitivity-labels.md).</span><span class="sxs-lookup"><span data-stu-id="9af8d-111">For sensitivity labels to be available to apply to your document understanding models, they need to be [created and published in the Microsoft 365 Compliance Center](../business-video/create-sensitivity-labels.md).</span></span>

## <a name="add-a-sensitivity-label-to-a-document-understanding-model"></a><span data-ttu-id="9af8d-112">Een gevoeligheidslabel toepassen op een documentbegripmodel</span><span class="sxs-lookup"><span data-stu-id="9af8d-112">Add a sensitivity label to a document understanding model</span></span>

1. <span data-ttu-id="9af8d-113">Selecteer op de startpagina van het model **Modelinstellingen**.</span><span class="sxs-lookup"><span data-stu-id="9af8d-113">From the model home page, select **Model settings**.</span></span>

   ![Schermafbeelding van de pagina Modellen met de optie Modelinstellingen gemarkeerd.](../media/content-understanding/sensitivity-model-settings.png)

2. <span data-ttu-id="9af8d-115">Selecteer in het deelvenster **Modelinstellingen** in de sectie **Naleving** het menu **Gevoeligheidslabel** om een lijst met gevoeligheidslabels weer te geven die u kunt toepassen op het model.</span><span class="sxs-lookup"><span data-stu-id="9af8d-115">On **Model settings** pane, in the **Compliance** section, select the **Sensitivity label** menu to see a list of sensitivity labels that are available for you to apply to the model.</span></span>

   ![Schermafbeelding van het deelvenster Modelinstellingen met het menu Gevoeligheidslabel.](../media/content-understanding/sensitivity-model-settings-pane.png) 

3. <span data-ttu-id="9af8d-117">Selecteer het gevoeligheidslabel dat u wilt toepassen op het model en selecteer vervolgens **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="9af8d-117">Select the sensitivity label you want to apply to the model, and then select **Save**.</span></span>

<span data-ttu-id="9af8d-118">Nadat u het gevoeligheidslabel op het model hebt toegepast, kunt u dit toepassen op een:</span><span class="sxs-lookup"><span data-stu-id="9af8d-118">After you apply the sensitivity label to your model, you can apply it to a:</span></span>

- <span data-ttu-id="9af8d-119">Nieuwe documentbibliotheek</span><span class="sxs-lookup"><span data-stu-id="9af8d-119">New document library</span></span>
- <span data-ttu-id="9af8d-120">Documentbibliotheek waarop het model al is toegepast</span><span class="sxs-lookup"><span data-stu-id="9af8d-120">Document library to which the model is already applied</span></span>
 
### <a name="apply-the-sensitivity-label-to-a-document-library-to-which-the-model-is-already-applied"></a><span data-ttu-id="9af8d-121">Het gevoeligheidslabel toepassen op een documentbibliotheek waarop het model al is toegepast</span><span class="sxs-lookup"><span data-stu-id="9af8d-121">Apply the sensitivity label to a document library to which the model is already applied</span></span>

<span data-ttu-id="9af8d-122">Als uw documentbegripmodel al is toegepast op een documentbibliotheek, kunt u het volgende doen om de gevoeligheidslabelupdate te synchroniseren en toe te passen op de documentbibliotheek:</span><span class="sxs-lookup"><span data-stu-id="9af8d-122">If your document understanding model has already been applied to a document library, you can do the following to sync your sensitivity label update to apply it to the document library:</span></span>

1. <span data-ttu-id="9af8d-123">Selecteer op de startpagina van het model in het gedeelte **Bibliotheken met dit model** de documentbibliotheek waarop u de gevoeligheidslabelupdate wilt toepassen.</span><span class="sxs-lookup"><span data-stu-id="9af8d-123">On the model home page, in the **Libraries with this model** section, select the document library to which you want to apply the sensitivity label update.</span></span>

2. <span data-ttu-id="9af8d-124">Selecteer **Synchroniseren**.</span><span class="sxs-lookup"><span data-stu-id="9af8d-124">Select **Sync**.</span></span>

   ![Schermafbeelding van bibliotheken met dit modelgedeelte waarin Synchronisatie is gemarkeerd.](../media/content-understanding/sensitivity-libraries-sync.png)

<span data-ttu-id="9af8d-126">Nadat u de update hebt toegepast en deze naar uw model hebt gesynchroniseerd, kunt u bevestigen dat deze is toegepast door de volgende stappen uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="9af8d-126">After you apply the update and sync it to your model, you can confirm that it has been applied by doing the following steps:</span></span>

1. <span data-ttu-id="9af8d-127">Klik in het inhoudscentrum in het gedeelte **Bibliotheken met dit model** op de bibliotheek waarop het bijgewerkte model is toegepast.</span><span class="sxs-lookup"><span data-stu-id="9af8d-127">In the content center, in the **Libraries with this model** section, select the library to which your updated model was applied.</span></span> 

2. <span data-ttu-id="9af8d-128">Selecteer in de documentbibliotheekweergave het informatiepictogram om de modeleigenschappen te bekijken.</span><span class="sxs-lookup"><span data-stu-id="9af8d-128">In your document library view, select the information icon to check the model properties.</span></span>

3. <span data-ttu-id="9af8d-129">Selecteer in de lijst **Actieve modellen** het bijgewerkte model.</span><span class="sxs-lookup"><span data-stu-id="9af8d-129">In the **Active models** list, select your updated model.</span></span>

4. <span data-ttu-id="9af8d-130">In het gedeelte **Gevoeligheidslabel** ziet u de naam van het toegepaste gevoeligheidslabel.</span><span class="sxs-lookup"><span data-stu-id="9af8d-130">In the **Sensitivity label** section, you'll see the name of the applied sensitivity label.</span></span>

<span data-ttu-id="9af8d-131">Op de pagina met de weergave van uw model in uw documentbibliotheek wordt er een nieuwe kolom **Gevoeligheidslabel** weergegeven.</span><span class="sxs-lookup"><span data-stu-id="9af8d-131">On your model's view page in your document library, a new **Sensitivity label** column will display.</span></span> <span data-ttu-id="9af8d-132">Terwijl uw model bestanden classificeert die het identificeert als behorend tot het inhoudstype en ze weergeeft in de bibliotheekweergave, zal de kolom **Gevoeligheidslabel** ook de naam weergeven van het gevoeligheidslabel dat er via het model op is toegepast.</span><span class="sxs-lookup"><span data-stu-id="9af8d-132">As your model classifies files it identifies as belonging to its content type and lists them in the library view, the **Sensitivity label** column will also display the name of the sensitivity label that has been applied to it through the model.</span></span>

<span data-ttu-id="9af8d-133">Op alle financiële documenten die uw model identificeert, wordt bijvoorbeeld ook het gevoeligheidslabel *Versleuteling* toegepast, zodat onbevoegden er geen toegang toe hebben.</span><span class="sxs-lookup"><span data-stu-id="9af8d-133">For example, all financial documents that your model identifies also will have the *Encryption* sensitivity label applied to them, preventing them from being accessed by unauthorized people.</span></span> <span data-ttu-id="9af8d-134">Als een onbevoegde persoon probeert toegang te krijgen tot het bestand vanuit de documentbibliotheek, wordt er een foutmelding weergegeven waarin staat dat dit niet is toegestaan vanwege het toegepaste gevoeligheidslabel.</span><span class="sxs-lookup"><span data-stu-id="9af8d-134">If an attempt is made to access the file from the document library by an unauthorized person, an error will display saying it isn't allowed because of the applied sensitivity label.</span></span>

<!---
## Add a sensitivity label to a form processing model

> [!Important]
> For sensitivity labels to be available to apply to your form processing model, they need to be [created and published in the Microsoft 365 Compliance Center](../business-video/create-sensitivity-labels.md).

You can either apply a sensitivity label to a form processing model when you are creating a model, or apply it to an existing model.

### Add a sensitivity label when you create a form processing model

1. When you [create a new form processing model](create-a-form-processing-model.md), select **Advanced settings**.

2. In **Advanced settings**, in the **Sensitivity label** section, select the menu and then select the sensitivity label you want to apply to the model.

3.  After you've completed your remaining model settings, select **Create** to build your model.

### Add a sensitivity label to an existing form processing model

You can add a sensitivity label to an existing form processing model in different ways:

- Through the **Automate** menu in the document library
- Through the **Active model** settings in the document library 

#### Add a sensitivity label to an existing form processing model through the Automate menu

You can add a sensitivity label to an existing form processing model that you own through the **Automate** menu in the document library in which the model is applied.

1. In your document library to which the form processing model is applied, select the **Automate** menu, select **AI Builder**, and then select **View form processing model details**.

2. On the **Model details** pane, in the **Sensitivity label** section, select the sensitivity label you want to apply. Then select **Save**.

#### Add a sensitivity label to an existing form processing model in the active model settings

You can add a sensitivity label to an existing form processing model that you own through the **Active model** settings in the document library in which the model is applied.

1. In the SharePoint document library in which the model is applied, select the **View active models** icon, and then select **View active models**.

2. In **Active models**, select the form processing model to which you want to apply the sensitivity label.

3. On the **Model details** pane, in the **Sensitivity label** section, select the sensitivity label you want to apply. Then select **Save**.

   > [!NOTE]
   > You must be the model owner for the **Model settings** pane to be editable. 
--->

## <a name="see-also"></a><span data-ttu-id="9af8d-135">Zie ook</span><span class="sxs-lookup"><span data-stu-id="9af8d-135">See also</span></span>

[<span data-ttu-id="9af8d-136">Een retentielabel toepassen</span><span class="sxs-lookup"><span data-stu-id="9af8d-136">Apply a retention label</span></span>](apply-a-retention-label-to-a-model.md)

[<span data-ttu-id="9af8d-137">Een classificatie maken</span><span class="sxs-lookup"><span data-stu-id="9af8d-137">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="9af8d-138">Een extractor maken</span><span class="sxs-lookup"><span data-stu-id="9af8d-138">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="9af8d-139">Overzicht van documentbegrip</span><span class="sxs-lookup"><span data-stu-id="9af8d-139">Document Understanding overview</span></span>](document-understanding-overview.md)
