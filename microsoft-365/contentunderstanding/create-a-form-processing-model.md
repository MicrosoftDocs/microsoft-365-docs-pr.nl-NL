---
title: Een formulier verwerkings model maken (preview)
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
description: Maak een formulier verwerkings model in Project cortex.
ms.openlocfilehash: cec3b9a8b1b58237c4beb745377709d4938a2dba
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950142"
---
# <a name="create-a-form-processing-model-preview"></a><span data-ttu-id="463f1-103">Een formulier verwerkings model maken (preview)</span><span class="sxs-lookup"><span data-stu-id="463f1-103">Create a form processing model (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="463f1-104">De inhoud in dit artikel is bedoeld voor project cortex private preview.</span><span class="sxs-lookup"><span data-stu-id="463f1-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="463f1-105">[Lees meer over project cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="463f1-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="463f1-106">Met [AI Builder](https://docs.microsoft.com/ai-builder/overview) : een functie in Microsoft PowerApps-project cortex gebruikers kunnen rechtstreeks een [formulier verwerkings model](form-processing-overview.md) maken vanuit een SharePoint-documentbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="463f1-106">Using [AI Builder](https://docs.microsoft.com/ai-builder/overview) - a feature in Microsoft PowerApps - Project Cortex users can create a [form processing model](form-processing-overview.md) directly from a SharePoint document library.</span></span> 

<span data-ttu-id="463f1-107">Het maken van een formulier voor formulier verwerkings modellen omvat het volgende:</span><span class="sxs-lookup"><span data-stu-id="463f1-107">Creating a form processing model involves the following:</span></span>
 - <span data-ttu-id="463f1-108">Stap 1: het verwerkings model maken om het inhoudstype te maken</span><span class="sxs-lookup"><span data-stu-id="463f1-108">Step 1: Create the from processing model to create the content type</span></span>
 - <span data-ttu-id="463f1-109">Stap 2: voorbeeldbestanden toevoegen en analyseren</span><span class="sxs-lookup"><span data-stu-id="463f1-109">Step 2: Add and analyze example files</span></span>
 - <span data-ttu-id="463f1-110">Stap 3: de formuliervelden selecteren</span><span class="sxs-lookup"><span data-stu-id="463f1-110">Step 3: Select your form fields</span></span>
 - <span data-ttu-id="463f1-111">Stap 4: uw model trainen en testen</span><span class="sxs-lookup"><span data-stu-id="463f1-111">Step 4: Train and test your model</span></span>
 - <span data-ttu-id="463f1-112">Stap 5: uw model publiceren</span><span class="sxs-lookup"><span data-stu-id="463f1-112">Step 5: Publish your model</span></span>
 - <span data-ttu-id="463f1-113">Stap 6: uw model gebruiken</span><span class="sxs-lookup"><span data-stu-id="463f1-113">Step 6: Use your model</span></span>


## <a name="requirements"></a><span data-ttu-id="463f1-114">Vereisten</span><span class="sxs-lookup"><span data-stu-id="463f1-114">Requirements</span></span>

<span data-ttu-id="463f1-115">U kunt alleen een formulier verwerkings model maken in SharePoint-documentbibliotheken waarin dit is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="463f1-115">You can only create a form processing model in SharePoint document libraries in which it is enabled.</span></span> <span data-ttu-id="463f1-116">Als het verwerken van formulieren is ingeschakeld, kunt u de **AI Builder** **' een formulier verwerkings model maken '** weergeven in het menu **automatisch** in de documentbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="463f1-116">If form processing is enabled, you will be able to see the **AI Builder** **"Create a form processing model'** under the **Automate** menu in your document library.</span></span>  <span data-ttu-id="463f1-117">Neem contact op met uw beheerder als u de verwerking voor de documentbibliotheek wilt inschakelen.</span><span class="sxs-lookup"><span data-stu-id="463f1-117">If you need from processing enabled on your document library, contact your admin.</span></span>

 ![Een AI Builder-model maken](../media/content-understanding/create-ai-builder-model.png)</br>


## <a name="step-1-create-a-form-processing-model"></a><span data-ttu-id="463f1-119">Stap 1: een formulier verwerkings model maken</span><span class="sxs-lookup"><span data-stu-id="463f1-119">Step 1: Create a Form Processing model</span></span>

<span data-ttu-id="463f1-120">De eerste stap bij het maken van een formulier verwerkings model is het noemen van het maken van het nieuwe inhoudstype en het maken van een nieuwe weergave van de documentbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="463f1-120">The first step in creating a form processing model is to name it to create the define the new content type and create a new document library view for it.</span></span>

1. <span data-ttu-id="463f1-121">Selecteer in de documentbibliotheek het menu **automatiseren** , selecteer **AI Builder**en selecteer vervolgens **een formulier verwerkings model maken**.</span><span class="sxs-lookup"><span data-stu-id="463f1-121">In your document library, select the **Automate** menu, select **AI Builder**, and then select **Create a Form Processing model**.</span></span>

    ![Een AI Builder-model maken](../media/content-understanding/create-ai-builder-model.png)</br>
2. <span data-ttu-id="463f1-123">Typ in het deelvenster **Nieuw model voor formulier verwerkings model** in het veld  **naam** een naam voor uw model (bijvoorbeeld *aankoop orders*).</span><span class="sxs-lookup"><span data-stu-id="463f1-123">In the **New form processing model** pane, in the  **Name** field, type a name for your model (for example, *Purchase Orders*).</span></span>

    ![Nieuw model voor formulierverwerking](../media/content-understanding/new-form-model.png)</br> 

3. <span data-ttu-id="463f1-125">Wanneer u een formulier verwerkings model maakt, maakt u een nieuw SharePoint-inhoudstype.</span><span class="sxs-lookup"><span data-stu-id="463f1-125">When you create a form processing model, you are creating a new SharePoint content type.</span></span> <span data-ttu-id="463f1-126">Een SharePoint-inhoudstype vertegenwoordigt een categorie documenten met gemeenschappelijke kenmerken en deel een verzameling kolommen of metagegevenseigenschappen voor die specifieke inhoud.</span><span class="sxs-lookup"><span data-stu-id="463f1-126">A SharePoint content type represents a category of documents that have common characteristics and share a collection of columns or metadata properties for that particular content.</span></span> <span data-ttu-id="463f1-127">SharePoint-inhoudstypen worden beheerd via de [Galerie met inhoudstypen]().</span><span class="sxs-lookup"><span data-stu-id="463f1-127">SharePoint Content Types are managed through the [Content types gallery]().</span></span>

    <span data-ttu-id="463f1-128">Selecteer **Geavanceerde instellingen** als u dit model wilt toewijzen aan een bestaand inhoudstype in de galerie SharePoint-inhoudstypen om het schema te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="463f1-128">Select **Advanced settings** if you want to map this model to an existing content type in the SharePoint Content types gallery to use its schema.</span></span> 

4. <span data-ttu-id="463f1-129">Uw model maakt een nieuwe weergave in uw documentbibliotheek voor de opgehaalde gegevens.</span><span class="sxs-lookup"><span data-stu-id="463f1-129">Your model will create a new view in your document library for your extracted data.</span></span> <span data-ttu-id="463f1-130">Als u de standaardweergave niet wilt, schakelt u **de optie de weergave als standaard instellen**uit.</span><span class="sxs-lookup"><span data-stu-id="463f1-130">If you do not want it to the default view, deselect **Set the view as default**.</span></span>
5. <span data-ttu-id="463f1-131">Selecteer **maken**.</span><span class="sxs-lookup"><span data-stu-id="463f1-131">Select **Create**.</span></span>


## <a name="step-2-add-and-analyze-documents"></a><span data-ttu-id="463f1-132">Stap 2: documenten toevoegen en analyseren</span><span class="sxs-lookup"><span data-stu-id="463f1-132">Step 2: Add and analyze documents</span></span>

<span data-ttu-id="463f1-133">Nadat u uw nieuwe formulier verwerkings model hebt gemaakt, wordt in de browser een nieuwe PowerApps AI Builder-formulier verwerkings model geopend.</span><span class="sxs-lookup"><span data-stu-id="463f1-133">After you create your new form processing model, your browser will open a new PowerApps AI Builder forms processing model page.</span></span> <span data-ttu-id="463f1-134">Op deze pagina kunt u voorbeelddocumenten toevoegen en analyseren.</span><span class="sxs-lookup"><span data-stu-id="463f1-134">On this page you can add and analyze your example documents.</span></span> </br>

> [!Note]
> <span data-ttu-id="463f1-135">Zie de [vereisten voor invoerdocumenten voor formulieren bewerken en optimaliseren](https://docs.microsoft.com/ai-builder/form-processing-model-requirements)voor meer informatie over het gebruik van voorbeeldbestanden.</span><span class="sxs-lookup"><span data-stu-id="463f1-135">When looking for example files to use, see the [form processing model input document requirements and optimization tips](https://docs.microsoft.com/ai-builder/form-processing-model-requirements).</span></span> 

   ![Power apps AI Builder](../media/content-understanding/powerapps.png)</br> 
 

1. <span data-ttu-id="463f1-137">Klik op **documenten toevoegen** om voorbeelddocumenten toe te voegen die worden geanalyseerd om te bepalen welke benoemde waardeparen kunnen worden opgehaald.</span><span class="sxs-lookup"><span data-stu-id="463f1-137">Click **Add documents** to begin adding example documents that are analyzed to determine what named value pairs can be extracted.</span></span> <span data-ttu-id="463f1-138">U kunt **uploaden vanaf de lokale opslag**, **SharePoint**of **Azure-blobopslag**kiezen.</span><span class="sxs-lookup"><span data-stu-id="463f1-138">You can choose either **Upload from local storage**, **SharePoint**, or **Azure Blob storage**.</span></span> <span data-ttu-id="463f1-139">U dient ten minste vijf bestanden te gebruiken om te kunnen oefenen.</span><span class="sxs-lookup"><span data-stu-id="463f1-139">You will need to use at least five files for training.</span></span>
2. <span data-ttu-id="463f1-140">Na het toevoegen van uw bestanden, selecteert u **analyseren** om te controleren of alle bestanden algemeen zijn.</span><span class="sxs-lookup"><span data-stu-id="463f1-140">After adding your files, select **Analyze** to check for any information that is common is all files.</span></span> <span data-ttu-id="463f1-141">Dit kan enkele minuten duren voordat u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="463f1-141">Note that this may take several minutes to complete.</span></span></br> 
 
    ![Bestanden analyseren](../media/content-understanding/analyze.png)</br> 

3. <span data-ttu-id="463f1-143">Nadat de gegevens zijn geanalyseerd, klikt u in de pagina **Selecteer de formuliervelden die u wilt opslaan** op het bestand om de gevonden velden weer te geven.</span><span class="sxs-lookup"><span data-stu-id="463f1-143">After they have been analyzed, in the **Select the form fields you want to save** page, click the file to see the fields that were detected.</span></span></br>

    ![Formuliervelden selecteren](../media/content-understanding/select-form-fields.png)</br> 

## <a name="step-3-select-your-form-fields"></a><span data-ttu-id="463f1-145">Stap 3: de formuliervelden selecteren</span><span class="sxs-lookup"><span data-stu-id="463f1-145">Step 3: Select your form fields</span></span>

<span data-ttu-id="463f1-146">Nadat u uw documenten hebt geanalyseerd voor velden, kunt u nu zien welke velden zijn gevonden en welke velden u wilt opslaan.</span><span class="sxs-lookup"><span data-stu-id="463f1-146">After analyzing your documents for fields, you can now see which fields were found, and which ones you want to save.</span></span> <span data-ttu-id="463f1-147">Opgeslagen velden worden als kolommen weergegeven in de documentbibliotheekweergave van uw model en worden de waarden weergegeven die uit elk document worden opgehaald.</span><span class="sxs-lookup"><span data-stu-id="463f1-147">Saved fields will display as columns in your model's document library view and will show the values extracted from each document.</span></span>

1. <span data-ttu-id="463f1-148">Op de volgende pagina wordt een van de voorbeeldbestanden weergegeven en worden alle gemeenschappelijke velden gemarkeerd die automatisch door het systeem zijn gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="463f1-148">The next page will display one of your sample files and will highlight all common fields that were automatically detected by the system.</span></span> </br>

    ![Formuliervelden selecteren](../media/content-understanding/select-fields-page.png)</br> 

2. <span data-ttu-id="463f1-150">Selecteer de velden die u wilt opslaan en schakel het selectievakje in om uw selectie te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="463f1-150">Select the fields you want to save, and select the checkbox to confirm your selection.</span></span> <span data-ttu-id="463f1-151">In het inkooporder model kunt u bijvoorbeeld kiezen voor de velden *date*, *po*en *Total* .</span><span class="sxs-lookup"><span data-stu-id="463f1-151">For example, in the Purchase Order model, you can choose to select the *Date*, *PO*, and *Total* fields.</span></span>  <span data-ttu-id="463f1-152">U kunt er ook voor kiezen om de naam van een veld te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="463f1-152">Note that you can also choose to rename a field if you choose.</span></span> </br>

    ![Selecteer PO #](../media/content-understanding/po.png)</br> 

3. <span data-ttu-id="463f1-154">Als een veld niet door de analyse is gedetecteerd, kunt u er nog steeds voor kiezen om het toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="463f1-154">If a field was not detected by analysis, you can still choose to add it.</span></span> <span data-ttu-id="463f1-155">Selecteer de gegevens die u wilt extraheren en typ in het vak Naam de naam die u wilt opgeven.</span><span class="sxs-lookup"><span data-stu-id="463f1-155">Highlight the information you want to extract, and in the name box type in the name you want to give it.</span></span> <span data-ttu-id="463f1-156">Selecteer vervolgens de cheque.</span><span class="sxs-lookup"><span data-stu-id="463f1-156">Then select the check.</span></span> <span data-ttu-id="463f1-157">Houd er rekening mee dat u de niet-gevonden velden in de resterende voorbeeldbestanden moet bevestigen.</span><span class="sxs-lookup"><span data-stu-id="463f1-157">Note that you will need to confirm undetected fields in your remaining example files.</span></span>
4. <span data-ttu-id="463f1-158">Klik op **velden bevestigen** nadat u de velden hebt geselecteerd die u wilt opslaan.</span><span class="sxs-lookup"><span data-stu-id="463f1-158">Click **Confirm fields** after you have selected the fields you want to save.</span></span> </br>
 
    ![Velden bevestigen](../media/content-understanding/confirm-fields.png)</br> 
 
5. <span data-ttu-id="463f1-160">Op de pagina **Selecteer de formuliervelden die u wilt opslaan** , wordt het aantal velden weergegeven dat u hebt geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="463f1-160">On the **Select the form fields you want to save** page, it will show the number of fields you have selected.</span></span> <span data-ttu-id="463f1-161">Selecteer **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="463f1-161">Select **Done**.</span></span>

## <a name="step-4-train-and-test-your-model"></a><span data-ttu-id="463f1-162">Stap 4: uw model trainen en testen</span><span class="sxs-lookup"><span data-stu-id="463f1-162">Step 4: Train and test your model</span></span>

<span data-ttu-id="463f1-163">Nadat u de velden hebt geselecteerd die u wilt opslaan, kunt u het model met de **overzichtspagina model** leren trainen en testen.</span><span class="sxs-lookup"><span data-stu-id="463f1-163">After selecting the fields you want to save, the **Model Summary** page will let you train and test your model.</span></span>

1. <span data-ttu-id="463f1-164">Op de pagina **model samenvatting** wordt de opgeslagen velden weergegeven in de sectie **geselecteerde velden** .</span><span class="sxs-lookup"><span data-stu-id="463f1-164">On the **Model Summary** page, the saved fields will show in the **Selected fields** section.</span></span> <span data-ttu-id="463f1-165">Selecteer **training** om de training te beginnen op uw voorbeeldbestanden.</span><span class="sxs-lookup"><span data-stu-id="463f1-165">Select **Train** to begin training on your example files.</span></span> <span data-ttu-id="463f1-166">Dit kan een paar minuten duren.</span><span class="sxs-lookup"><span data-stu-id="463f1-166">Note that this may take a few minutes to complete.</span></span></br>
    <span data-ttu-id="463f1-167">![Velden bevestigen](../media/content-understanding/select-fields-train.png)</span><span class="sxs-lookup"><span data-stu-id="463f1-167">![Confirm fields](../media/content-understanding/select-fields-train.png)</span></span></br> 
2. <span data-ttu-id="463f1-168">Wanneer de melding wordt weergegeven dat de training is voltooid, selecteert u **Ga naar details pagina**.</span><span class="sxs-lookup"><span data-stu-id="463f1-168">When you see the notification that training has completed, select **Go to details page**.</span></span> 
3. <span data-ttu-id="463f1-169">Op de pagina **model Details** kunt u kiezen hoe u het model gaat gebruiken door **snel testen**te selecteren.</span><span class="sxs-lookup"><span data-stu-id="463f1-169">On the **Model details** page, you can choose to test how your model works by selecting **Quick test**.</span></span> <span data-ttu-id="463f1-170">Hiermee kunt u bestanden slepen en neerzetten naar de pagina om te zien of de velden zijn gevonden.</span><span class="sxs-lookup"><span data-stu-id="463f1-170">This lets you drag and drop files to the page and see if the fields are detected.</span></span>

## <a name="step-5-publish-your-model"></a><span data-ttu-id="463f1-171">Stap 5: uw model publiceren</span><span class="sxs-lookup"><span data-stu-id="463f1-171">Step 5: Publish your model</span></span>



1. <span data-ttu-id="463f1-172">Als u tevreden bent over de resultaten van uw model, selecteert u **publiceren** om het beschikbaar te maken voor gebruik.</span><span class="sxs-lookup"><span data-stu-id="463f1-172">If you are satisfied with the results of your model, select **Publish** to make it available for use.</span></span>
2. <span data-ttu-id="463f1-173">Wanneer het model is gepubliceerd, selecteert **u model gebruiken**.</span><span class="sxs-lookup"><span data-stu-id="463f1-173">After the model published, select **Use model**.</span></span> <span data-ttu-id="463f1-174">Hiermee wordt een PowerAutomate-stroom gemaakt die wordt uitgevoerd in uw SharePoint-documentbibliotheek, en worden de velden die in het model zijn gevonden, uitgepakt.</span><span class="sxs-lookup"><span data-stu-id="463f1-174">This creates a PowerAutomate flow that will run in your SharePoint document library and will extract the fields that have been identified in the model.</span></span> <span data-ttu-id="463f1-175">Selecteer **Create flow**.</span><span class="sxs-lookup"><span data-stu-id="463f1-175">Select **Create Flow**.</span></span>  
3. <span data-ttu-id="463f1-176">Wanneer u klaar bent, wordt het bericht weergegeven dat **uw stroom is gemaakt**.</span><span class="sxs-lookup"><span data-stu-id="463f1-176">When completed, you will see the message **Your flow has been successfully created**.</span></span>
 
 
## <a name="step-6-use-your-model"></a><span data-ttu-id="463f1-177">Stap 6: uw model gebruiken</span><span class="sxs-lookup"><span data-stu-id="463f1-177">Step 6: Use your model</span></span>

<span data-ttu-id="463f1-178">Nadat u uw model hebt gepubliceerd en de PowerAutomate-stroom hebt gemaakt, kunt u uw model gebruiken in de SharePoint-documentbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="463f1-178">After publishing your model and creating it's PowerAutomate flow, you can use your model in your SharePoint document library.</span></span>

1. <span data-ttu-id="463f1-179">Wanneer u uw model hebt gepubliceerd, selecteert u **Ga naar SharePoint** om naar de documentbibliotheek te gaan.</span><span class="sxs-lookup"><span data-stu-id="463f1-179">After publishing your model , select **Go to SharePoint** to go to your document library.</span></span>
2. <span data-ttu-id="463f1-180">In de modelweergave van uw documentbibliotheek ziet u dat de velden die u nu als kolommen hebt geselecteerd, worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="463f1-180">On your document library model view, notice that the fields you selected now display as columns.</span></span></br>

    ![Document bibliotheek met toegepast model](../media/content-understanding/doc-lib-view.png)</br> 

    <span data-ttu-id="463f1-182">Daarnaast wordt in de koppeling informatie naast **documenten** aangegeven dat een model voor formulierverwerking op deze documentbibliotheek is toegepast.</span><span class="sxs-lookup"><span data-stu-id="463f1-182">Also notice that the information link next to **Documents** will note that a forms processing model is applied to this document library.</span></span>

    ![Opgehaalde](../media/content-understanding/info-button.png)</br>  

3. <span data-ttu-id="463f1-184">Upload bestanden naar de documentbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="463f1-184">Upload files to your document library.</span></span> <span data-ttu-id="463f1-185">Alle bestanden die het model identificeert terwijl het inhoudstype het inhoudstype bevat, worden weergegeven in de weergave en worden de opgehaalde gegevens in de kolommen weergegeven.</span><span class="sxs-lookup"><span data-stu-id="463f1-185">Any files that the model identifies as it's content type will list the files in your view, and will display the extracted data in the columns.</span></span></br>

    ![Opgehaalde](../media/content-understanding/doc-lib-done.png)</br>  



## <a name="see-also"></a><span data-ttu-id="463f1-187">Zie ook</span><span class="sxs-lookup"><span data-stu-id="463f1-187">See Also</span></span>
  
[<span data-ttu-id="463f1-188">De documentatie voor Power Automatiseer</span><span class="sxs-lookup"><span data-stu-id="463f1-188">Power Automate documentation</span></span>](https://docs.microsoft.com/power-automate/)</br>
[<span data-ttu-id="463f1-189">Training: bedrijfsprestaties verbeteren met AI Builder</span><span class="sxs-lookup"><span data-stu-id="463f1-189">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>




