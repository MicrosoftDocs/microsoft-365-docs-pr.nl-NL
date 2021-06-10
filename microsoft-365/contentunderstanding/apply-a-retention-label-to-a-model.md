---
title: Een retentietag toepassen op een model
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
localization_priority: Normal
description: In dit artikel wordt uitgelegd hoe je een retentietag kunt toepassen op een model in SharePoint Syntex
ms.openlocfilehash: 00a8d255b3274af3cd96527e0dcd2ae2644226ac
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861609"
---
# <a name="apply-a-retention-label-to-a-model-in-sharepoint-syntex"></a><span data-ttu-id="4ad9b-103">Je kunt een retentietag toepassen op een model in Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="4ad9b-103">Apply a retention label to a model in SharePoint Syntex</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GydO]  

</br>


<span data-ttu-id="4ad9b-104">Je kunt eenvoudig een [retentietag](../compliance/retention.md) toepassen op een model in Microsoft SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="4ad9b-104">You can easily apply a [retention label](../compliance/retention.md) to a model in Microsoft SharePoint Syntex.</span></span> <span data-ttu-id="4ad9b-105">Je kan dit voor documentbegripmodellen en formulierverwerkingsmodellen doen.</span><span class="sxs-lookup"><span data-stu-id="4ad9b-105">You can do this for both document understanding and form processing models.</span></span>

<span data-ttu-id="4ad9b-106">Met retentietags kan je retentie-instellingen toepassen op de documenten die door je modellen worden geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="4ad9b-106">Retention labels let you apply retention settings to the documents that your models identify.</span></span>  <span data-ttu-id="4ad9b-107">Bijvoorbeeld: u wilt dat uw model niet alleen alle documenten met *verzekeringskennisgevingen* die naar uw documentbibliotheek worden geüpload identificeert, maar ook een retentietag *zakelijk* aanbrengt, zodat deze documenten niet uit de documentbibliotheek kunnen worden verwijderd gedurende de opgegeven periode (bijvoorbeeld de komende vijf maanden).</span><span class="sxs-lookup"><span data-stu-id="4ad9b-107">For example, you want your model to not only identify any *Insurance notice* documents that are uploaded to your document library, but to also apply a *Business* retention tag to them so that these documents cannot be deleted from the document library for the specified time period (the next five months, for example).</span></span>

<span data-ttu-id="4ad9b-108">Je kunt een bestaande retentietag toepassen op je model via de modelinstellingen op de startpagina van het model.</span><span class="sxs-lookup"><span data-stu-id="4ad9b-108">You can apply a pre-existing retention label to your model through your model settings on your model's home page.</span></span> 

> [!Important]
> <span data-ttu-id="4ad9b-109">Als je wilt dat retentietags beschikbaar zijn voor je documentbegripmodel, moeten deze [aangemaakt en gepubliceerd worden in het Microsoft 365-compliancecentrum](../compliance/create-apply-retention-labels.md#how-to-create-and-publish-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="4ad9b-109">For retention labels to be available to apply to your document understanding models, they need to be [created and published in the Microsoft 365 Compliance Center](../compliance/create-apply-retention-labels.md#how-to-create-and-publish-retention-labels).</span></span>

## <a name="to-add-a-retention-label-to-a-document-understanding-model"></a><span data-ttu-id="4ad9b-110">Een retentietag toepassen op een documentbegripmodel</span><span class="sxs-lookup"><span data-stu-id="4ad9b-110">To add a retention label to a document understanding model</span></span>

1. <span data-ttu-id="4ad9b-111">Selecteren **Modelinstellingen** op de startpagina van het model.</span><span class="sxs-lookup"><span data-stu-id="4ad9b-111">From the model home page, select **Model settings**.</span></span></br>
2. <span data-ttu-id="4ad9b-112">Selecteer in **Modelinstellingen**, in het gedeelte **Beveiliging en compliance**, het menu **Retentietag** om een lijst met retentietags weer te geven die beschikbaar zijn om toe te passen op het model.</span><span class="sxs-lookup"><span data-stu-id="4ad9b-112">In **Model settings**, in the **Security and compliance** section, select the **Retention label** menu to see a list of retention labels that are available for your to apply to the model.</span></span></br>
 <span data-ttu-id="4ad9b-113">![Menu Retentietag](../media/content-understanding/retention-labels-menu.png)</span><span class="sxs-lookup"><span data-stu-id="4ad9b-113">![Retention label menu](../media/content-understanding/retention-labels-menu.png)</span></span></br> 
3. <span data-ttu-id="4ad9b-114">Selecteer de retentietag die u wilt toepassen op het model en selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="4ad9b-114">Select the retention label you want to apply to the model, and then select **Save**.</span></span></br>

<span data-ttu-id="4ad9b-115">Nadat u de retentietag hebt toegepast op uw model, kunt u het toepassen op een:</span><span class="sxs-lookup"><span data-stu-id="4ad9b-115">After applying the retention label to your model, you are able to apply it to a:</span></span>
- <span data-ttu-id="4ad9b-116">Nieuwe documentbibliotheek</span><span class="sxs-lookup"><span data-stu-id="4ad9b-116">New document library</span></span>
- <span data-ttu-id="4ad9b-117">Documentbibliotheek waarop het model al is toegepast</span><span class="sxs-lookup"><span data-stu-id="4ad9b-117">Document library to which the model is already applied</span></span>
 
## <a name="apply-the-retention-label-to-a-document-library-to-which-the-model-is-already-applied"></a><span data-ttu-id="4ad9b-118">De retentietag toepassen op een documentbibliotheek waarop het model al is toegepast</span><span class="sxs-lookup"><span data-stu-id="4ad9b-118">Apply the retention label to a document library to which the model is already applied</span></span>

<span data-ttu-id="4ad9b-119">Als uw documentbegripmodel al is toegepast op een documentbibliotheek, kunt u het volgende doen om de retentietagupdate te synchroniseren en toe te passen op de documentbibliotheek:</span><span class="sxs-lookup"><span data-stu-id="4ad9b-119">If your document understanding model has already been applied to a document library, you can do the following to sync your retention label update to apply it to the document library:</span></span></br>

1. <span data-ttu-id="4ad9b-120">Selecteer op de startpagina van het model in het gedeelte **Bibliotheken met dit model** de documentbibliotheek waarop u de retentietagupdate wilt toepassen.</span><span class="sxs-lookup"><span data-stu-id="4ad9b-120">On your model home page, in the **Libraries with this model** section, select the document library to which you want to apply the retention label update.</span></span> </br> 
2. <span data-ttu-id="4ad9b-121">Selecteer **Synchroniseren**.</span><span class="sxs-lookup"><span data-stu-id="4ad9b-121">Select **Sync**.</span></span> </br>
 <span data-ttu-id="4ad9b-122">![Model synchroniseren](../media/content-understanding/sync-model.png)</span><span class="sxs-lookup"><span data-stu-id="4ad9b-122">![Sync model](../media/content-understanding/sync-model.png)</span></span></br> 


<span data-ttu-id="4ad9b-123">Nadat u de update hebt toegepast en gesynchroniseerd met uw model, kunt u het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="4ad9b-123">After applying the update and syncing it to your model, you can confirm that it has been applied by doing the following:</span></span>

1. <span data-ttu-id="4ad9b-124">Klik in het inhoudscentrum in het gedeelte **Bibliotheken met deze model** op de bibliotheek waarop het bijgewerkte model is toegepast.</span><span class="sxs-lookup"><span data-stu-id="4ad9b-124">In the content center, in the **Libraries with this model** section, click on the library to which your updated model was applied.</span></span> </br>
2. <span data-ttu-id="4ad9b-125">Selecteer in de documentbibliotheekweergave het informatiepictogram om de modeleigenschappen te bekijken.</span><span class="sxs-lookup"><span data-stu-id="4ad9b-125">In your document library view, select the information icon to check the model properties.</span></span></br>  
3. <span data-ttu-id="4ad9b-126">Selecteer in de lijst **Actieve modellen** het bijgewerkte model.</span><span class="sxs-lookup"><span data-stu-id="4ad9b-126">In the **Active models** list, select your updated model.</span></span></br>
4. <span data-ttu-id="4ad9b-127">In het gedeelte **Retentietag** wordt de naam van de toegepaste retentietag weergegeven.</span><span class="sxs-lookup"><span data-stu-id="4ad9b-127">In the **Retention label** section you will see the name of the applied retention label.</span></span></br>


<span data-ttu-id="4ad9b-128">Op de pagina met de weergave van uw model in uw documentbibliotheek wordt er een nieuwe kolom **Retentietag** weergegeven.</span><span class="sxs-lookup"><span data-stu-id="4ad9b-128">On your model's view page in your document library, a new **Retention label** column will display.</span></span>  <span data-ttu-id="4ad9b-129">Omdat uw model bestanden classificeert die het identificeert als het relevante inhoudstype en ze vermeldt in de bibliotheekweergave, bevat de kolom Retentietag ook de naam van de retentietag die via het model is toegepast.</span><span class="sxs-lookup"><span data-stu-id="4ad9b-129">As your model classifies files it identifies as belonging to it's content type and lists them in the library view, the Retention label column will also display the name of the retention label that has been applied to it through the model.</span></span>


<span data-ttu-id="4ad9b-130">Bijvoorbeeld: op alle *verzekeringskennisgevingen* die uw model identificeert, wordt ook de retentietag *zakelijk* toegepast, zodat ze gedurende vijf maanden lang niet uit de documentenbibliotheek kunnen worden verwijderd.</span><span class="sxs-lookup"><span data-stu-id="4ad9b-130">For example, all *Insurance notice* documents that your model identifies will also have the *Business* retention label applied to them, preventing them from being deleted from the document library for five months.</span></span> <span data-ttu-id="4ad9b-131">Als geprobeerd wordt het bestand uit de documentbibliotheek te verwijderen, wordt een foutbericht weergegeven met de mededeling dat het niet is toegestaan vanwege de toegepaste retentietag.</span><span class="sxs-lookup"><span data-stu-id="4ad9b-131">If an attempt is made to delete the file from the document library, an error will display saying it is not allowed because of the applied retention label.</span></span>

## <a name="to-add-a-retention-label-to-a-form-processing-model"></a><span data-ttu-id="4ad9b-132">Een retentietag toepassen op een formulierverwerkingsmodel</span><span class="sxs-lookup"><span data-stu-id="4ad9b-132">To add a retention label to a form processing model</span></span>

> [!Important]
> <span data-ttu-id="4ad9b-133">Als je wilt dat retentietags beschikbaar zijn voor je formulierverwerkingsmodel, moeten deze [aangemaakt en gepubliceerd worden in het Microsoft 365-compliancecentrum](../compliance/create-apply-retention-labels.md#how-to-create-and-publish-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="4ad9b-133">For retention labels to be available to apply to your form processing model, they need to be [created and published in the Microsoft 365 Compliance Center](../compliance/create-apply-retention-labels.md#how-to-create-and-publish-retention-labels).</span></span>

<span data-ttu-id="4ad9b-134">Je kan een retentietag toepassen op een formulierverwerkingsmodel wanneer je een model maakt of je kan het toepassen op een bestaand model.</span><span class="sxs-lookup"><span data-stu-id="4ad9b-134">You can either apply a retention label to a form processing model when you are creating a model, or apply it to an existing model.</span></span>

### <a name="to-add-a-retention-label-when-you-create-a-form-processing-model"></a><span data-ttu-id="4ad9b-135">Een retentietag toepassen wanneer je een formulierverwerkingsmodel maakt</span><span class="sxs-lookup"><span data-stu-id="4ad9b-135">To add a retention label when you create a form processing model</span></span>

1. <span data-ttu-id="4ad9b-136">Wanneer je een [nieuw formulierverwerkingsmodel maakt](./create-a-form-processing-model.md), kies <b>Geavanceerde instellingen.</b></span><span class="sxs-lookup"><span data-stu-id="4ad9b-136">When you are [creating a new form processing model](./create-a-form-processing-model.md), select <b>Advanced settings.</b></span></span>
2. <span data-ttu-id="4ad9b-137">In <b>Geavanceerde instellingen</b>, in de sectie <b>Retentietag</b>, selecteer het menu en selecteer vervolgens de retentietag die je wilt toepassen op het model.</b></span><span class="sxs-lookup"><span data-stu-id="4ad9b-137">In <b>Advanced settings</b>, in the <b>Retention label</b> section, select the menu and then select the retention label you want to apply to the model.</b></span></span>

 
     ![Toevoegen aan een nieuw formulierverwerkingsmodel](../media/content-understanding/retention-label-forms.png)</br>

3.  <span data-ttu-id="4ad9b-139">Nadat je de overige modelinstellingen afgewerkt hebt, selecteer <b>Aanmaken</b> om jouw model te maken.</span><span class="sxs-lookup"><span data-stu-id="4ad9b-139">After you've completed your remaining model settings, select <b>Create</b> to build your model.</span></span>

### <a name="to-add-a-retention-label-to-an-existing-form-processing-model"></a><span data-ttu-id="4ad9b-140">Een retentietag toepassen op een bestaand formulierverwerkingsmodel</span><span class="sxs-lookup"><span data-stu-id="4ad9b-140">To add a retention label to an existing form processing model</span></span>

<span data-ttu-id="4ad9b-141">Een retentietag toevoegen aan een bestaand formulierverwerkingsmodel kan op verschillende manieren:</span><span class="sxs-lookup"><span data-stu-id="4ad9b-141">You can add a retention label to an existing form processing model in different ways:</span></span>
- <span data-ttu-id="4ad9b-142">Via het Automatiseren-menu in de documentbibliotheek</span><span class="sxs-lookup"><span data-stu-id="4ad9b-142">Through the Automate menu in the document library</span></span>
- <span data-ttu-id="4ad9b-143">Via de actieve modellen-instellingen in de documentbibliotheek</span><span class="sxs-lookup"><span data-stu-id="4ad9b-143">Through the Active model settings in the document library</span></span> 


#### <a name="to-add-a-retention-label-to-an-existing-form-processing-model-through-the-automate-menu"></a><span data-ttu-id="4ad9b-144">Een retentietag toepassen op een bestaand formulierverwerkingsmodel via het Automatiseren-menu</span><span class="sxs-lookup"><span data-stu-id="4ad9b-144">To add a retention label to an existing form processing model through the Automate menu</span></span>

<span data-ttu-id="4ad9b-145">Je kan een retentietag aan een bestaand formulierverwerkingsmodel dat je bezit, toevoegen via het Automatiseren-menu in de documentbibliotheek, waarop het model wordt toegepast.</span><span class="sxs-lookup"><span data-stu-id="4ad9b-145">You can add a retention label to an existing form processing model that you own through the Automate menu in the document library in which the model is applied.</span></span>


1. <span data-ttu-id="4ad9b-146">In je documentbibliotheek, waarop het formulierverwerkingsmodel wordt toegepast, kies je het menu <b>Automatiseren</b>, kies <b>AI-opbouwfunctie</b> en kies vervolgens <b>Informatie over formulierverwerkingsmodel weergeven</b>.</span><span class="sxs-lookup"><span data-stu-id="4ad9b-146">In your document library to which the form processing model is applied, select the <b>Automate</b> menu, select <b>AI Builder</b>, then select <b>View form processing model details</b>.</span></span>

   ![Automatiseren-menu](../media/content-understanding/automate-menu.png)</br>

2. <span data-ttu-id="4ad9b-148">In de informatie over het model, in de sectie <b>Retentietag</b>, selecteer de retentietag die je wilt toepassen.</span><span class="sxs-lookup"><span data-stu-id="4ad9b-148">In the model details, in the <b>Retention Label</b> section, select the retention label you want to apply.</span></span>  <span data-ttu-id="4ad9b-149">Selecteer vervolgens <b>Opslaan</b>.</span><span class="sxs-lookup"><span data-stu-id="4ad9b-149">Then select <b>Save</b>.</span></span>

     ![Toevoegen aan een bestaand formulierverwerkingsmodel](../media/content-understanding/retention-label-model-details.png)</br> 

#### <a name="to-add-a-retention-label-to-an-existing-form-processing-model-in-the-active-model-settings"></a><span data-ttu-id="4ad9b-151">Een retentietag toevoegen aan een bestaand formulierverwerkingsmodel in de actieve modelinstellingen</span><span class="sxs-lookup"><span data-stu-id="4ad9b-151">To add a retention label to an existing form processing model in the active model settings</span></span>

<span data-ttu-id="4ad9b-152">Je kan een retentietag aan een bestaand formulierverwerkingsmodel dat je bezit, toevoegen via de actieve modelinstellingen in de documentbibliotheek, waarop het model wordt toegepast.</span><span class="sxs-lookup"><span data-stu-id="4ad9b-152">You can add a retention label to an existing form processing model that you own through the Active model settings in the document library in which the model is applied.</span></span>

1. <span data-ttu-id="4ad9b-153">In de SharePoint documentbibliotheek waarop het model wordt toegepast, selecteer het pictogram<b>Actieve modellen weergeven</b> en selecteer vervolgens <b>Actieve modellen weergeven</b>.</b></span><span class="sxs-lookup"><span data-stu-id="4ad9b-153">In the SharePoint document library in which the model is applied, select the <b>View active models</b> icon, and then select <b>View active models</b>.</b></span></span>

   ![Actieve modellen weergeven](../media/content-understanding/info-du.png)</br> 

2. <span data-ttu-id="4ad9b-155">In <b>Actieve modellen</b>, selecteer het formulierverwerkingsmodel waarop je de retentietag wilt toepassen.</span><span class="sxs-lookup"><span data-stu-id="4ad9b-155">In <b>Active models</b>, select the form processing model to which you want to apply the retention label.</span></span>

     ![Informatie over model](../media/content-understanding/retention-label-model-details.png)</br> 


3. <span data-ttu-id="4ad9b-157">In de informatie over het model, in de sectie <b>Retentietag</b>, selecteer de retentietag die je wilt toepassen.</span><span class="sxs-lookup"><span data-stu-id="4ad9b-157">In the model details, in the <b>Retention Label</b> section, select the retention label you want to apply.</span></span>  <span data-ttu-id="4ad9b-158">Selecteer vervolgens <b>Opslaan</b>.</span><span class="sxs-lookup"><span data-stu-id="4ad9b-158">Then select <b>Save</b>.</span></span>

> [!NOTE]
> <span data-ttu-id="4ad9b-159">Enkel de eigenaar van het model kan bewerkingen maken in het deelvenster modelinstellingen.</span><span class="sxs-lookup"><span data-stu-id="4ad9b-159">You must be the model owner for the model settings pane to be editable.</span></span> 


## <a name="see-also"></a><span data-ttu-id="4ad9b-160">Zie ook</span><span class="sxs-lookup"><span data-stu-id="4ad9b-160">See Also</span></span>
[<span data-ttu-id="4ad9b-161">Een classificatie maken</span><span class="sxs-lookup"><span data-stu-id="4ad9b-161">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="4ad9b-162">Een extractor maken</span><span class="sxs-lookup"><span data-stu-id="4ad9b-162">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="4ad9b-163">Overzicht van documentbegrip</span><span class="sxs-lookup"><span data-stu-id="4ad9b-163">Document Understanding overview</span></span>](document-understanding-overview.md)
