---
title: Een formulier verwerkings model maken
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
description: Maak een formulier verwerkings model in Microsoft SharePoint Syntex.
ms.openlocfilehash: f61dbad837173c412daefb7285c4abff10a01817
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295476"
---
# <a name="create-a-form-processing-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="0467f-103">Een formulier verwerkings model maken in Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="0467f-103">Create a form processing model in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="0467f-104">De inhoud in dit artikel is bedoeld voor de cortex van de private preview van project.</span><span class="sxs-lookup"><span data-stu-id="0467f-104">The content in this article is for the Project Cortex Private Preview.</span></span> <span data-ttu-id="0467f-105">[Lees meer over project cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="0467f-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="0467f-106">Met [AI Builder](https://docs.microsoft.com/ai-builder/overview) : een functie in Microsoft PowerApps-project cortex gebruikers kunnen rechtstreeks een [formulier verwerkings model](form-processing-overview.md) maken vanuit een SharePoint-documentbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="0467f-106">Using [AI Builder](https://docs.microsoft.com/ai-builder/overview) - a feature in Microsoft PowerApps - Project Cortex users can create a [form processing model](form-processing-overview.md) directly from a SharePoint document library.</span></span> 

<span data-ttu-id="0467f-107">Het maken van een formulier voor formulier verwerkings modellen omvat het volgende:</span><span class="sxs-lookup"><span data-stu-id="0467f-107">Creating a form processing model involves the following:</span></span>
 - <span data-ttu-id="0467f-108">Stap 1: het verwerkings model maken om het inhoudstype te maken</span><span class="sxs-lookup"><span data-stu-id="0467f-108">Step 1: Create the from processing model to create the content type</span></span>
 - <span data-ttu-id="0467f-109">Stap 2: voorbeeldbestanden toevoegen en analyseren</span><span class="sxs-lookup"><span data-stu-id="0467f-109">Step 2: Add and analyze example files</span></span>
 - <span data-ttu-id="0467f-110">Stap 3: de formuliervelden selecteren</span><span class="sxs-lookup"><span data-stu-id="0467f-110">Step 3: Select your form fields</span></span>
 - <span data-ttu-id="0467f-111">Stap 4: uw model trainen en testen</span><span class="sxs-lookup"><span data-stu-id="0467f-111">Step 4: Train and test your model</span></span>
 - <span data-ttu-id="0467f-112">Stap 5: uw model publiceren</span><span class="sxs-lookup"><span data-stu-id="0467f-112">Step 5: Publish your model</span></span>
 - <span data-ttu-id="0467f-113">Stap 6: uw model gebruiken</span><span class="sxs-lookup"><span data-stu-id="0467f-113">Step 6: Use your model</span></span>

## <a name="requirements"></a><span data-ttu-id="0467f-114">Vereisten</span><span class="sxs-lookup"><span data-stu-id="0467f-114">Requirements</span></span>

<span data-ttu-id="0467f-115">U kunt alleen een formulier verwerkings model maken in SharePoint-documentbibliotheken waarvoor dit is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="0467f-115">You can only create a form processing model in SharePoint document libraries for which it is enabled.</span></span> <span data-ttu-id="0467f-116">Als het verwerken van formulieren is ingeschakeld, kunt u de **AI Builder** **' een formulier verwerkings model maken '** weergeven in het menu **automatisch** in de documentbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="0467f-116">If form processing is enabled, you are able to see the **AI Builder** **"Create a form processing model'** under the **Automate** menu in your document library.</span></span>  <span data-ttu-id="0467f-117">Als u de verwerking voor de documentbibliotheek wilt inschakelen, moet u contact opnemen met de SharePoint-beheerder.</span><span class="sxs-lookup"><span data-stu-id="0467f-117">If you need processing enabled on your document library, you must contact your SharePoint administrator.</span></span>

 ![Een AI Builder-model maken](../media/content-understanding/create-ai-builder-model.png)</br>

## <a name="step-1-create-a-form-processing-model"></a><span data-ttu-id="0467f-119">Stap 1: een formulier verwerkings model maken</span><span class="sxs-lookup"><span data-stu-id="0467f-119">Step 1: Create a form Processing model</span></span>

<span data-ttu-id="0467f-120">De eerste stap bij het maken van een formulier voor formulier verwerkings modellen is het maken van een naam en het maken van het nieuwe inhoudstype en het maken van een nieuwe weergave van een documentbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="0467f-120">The first step in creating a form processing model is to name it and create the define the new content type and create a new document library view for it.</span></span>

1. <span data-ttu-id="0467f-121">Selecteer in de documentbibliotheek het menu **automatisch** , selecteer **AI Builder**en selecteer vervolgens **een formulier verwerkings model maken**.</span><span class="sxs-lookup"><span data-stu-id="0467f-121">From the document library, select the **Automate** menu, select **AI Builder**, and then select **Create a Form Processing model**.</span></span>

    ![Een model maken](../media/content-understanding/create-ai-builder-model.png)</br>

2. <span data-ttu-id="0467f-123">Typ in het deelvenster **Nieuw model voor formulier verwerkings model** in het veld  **naam** een naam voor uw model (bijvoorbeeld *aankoop orders*).</span><span class="sxs-lookup"><span data-stu-id="0467f-123">In the **New form processing model** pane, in the  **Name** field, type a name for your model (for example, *Purchase Orders*).</span></span>

    ![Nieuw model voor formulierverwerking](../media/content-understanding/new-form-model.png)</br> 

3. <span data-ttu-id="0467f-125">Wanneer u een formulier verwerkings model maakt, maakt u een nieuw SharePoint-inhoudstype.</span><span class="sxs-lookup"><span data-stu-id="0467f-125">When you create a form processing model, you create a new SharePoint content type.</span></span> <span data-ttu-id="0467f-126">Een SharePoint-inhoudstype vertegenwoordigt een categorie documenten met gemeenschappelijke kenmerken en deel een verzameling kolommen of metagegevenseigenschappen voor die specifieke inhoud.</span><span class="sxs-lookup"><span data-stu-id="0467f-126">A SharePoint content type represents a category of documents that have common characteristics and share a collection of columns or metadata properties for that particular content.</span></span> <span data-ttu-id="0467f-127">SharePoint-inhoudstypen worden beheerd via de [Galerie met inhoudstypen]().</span><span class="sxs-lookup"><span data-stu-id="0467f-127">SharePoint Content Types are managed through the [Content types gallery]().</span></span>

    <span data-ttu-id="0467f-128">Selecteer **Geavanceerde instellingen** als u dit model wilt toewijzen aan een bestaand inhoudstype in de galerie SharePoint-inhoudstypen om het schema te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="0467f-128">Select **Advanced settings** if you want to map this model to an existing content type in the SharePoint Content types gallery to use its schema.</span></span> 

4. <span data-ttu-id="0467f-129">Uw model maakt een nieuwe weergave in uw documentbibliotheek voor de opgehaalde gegevens.</span><span class="sxs-lookup"><span data-stu-id="0467f-129">Your model creates a new view in your document library for your extracted data.</span></span> <span data-ttu-id="0467f-130">Als u de standaardweergave niet wilt, schakelt u **de optie de weergave als standaard instellen**uit.</span><span class="sxs-lookup"><span data-stu-id="0467f-130">If you do not want it to the default view, deselect **Set the view as default**.</span></span>

5. <span data-ttu-id="0467f-131">Selecteer **maken**.</span><span class="sxs-lookup"><span data-stu-id="0467f-131">Select **Create**.</span></span>

## <a name="step-2-add-and-analyze-documents"></a><span data-ttu-id="0467f-132">Stap 2: documenten toevoegen en analyseren</span><span class="sxs-lookup"><span data-stu-id="0467f-132">Step 2: Add and analyze documents</span></span>

<span data-ttu-id="0467f-133">Nadat u uw nieuwe formulier verwerkings model hebt gemaakt, wordt in de browser een nieuwe PowerApps AI Builder-formulier verwerkings model geopend.</span><span class="sxs-lookup"><span data-stu-id="0467f-133">After you create your new form processing model, your browser opens a new PowerApps AI Builder forms processing model page.</span></span> <span data-ttu-id="0467f-134">Op deze pagina kunt u voorbeelddocumenten toevoegen en analyseren.</span><span class="sxs-lookup"><span data-stu-id="0467f-134">On this page you can add and analyze your example documents.</span></span> </br>

> [!NOTE]
> <span data-ttu-id="0467f-135">Zie de [vereisten voor invoerdocumenten voor formulieren bewerken en optimaliseren](https://docs.microsoft.com/ai-builder/form-processing-model-requirements)voor meer informatie over het gebruik van voorbeeldbestanden.</span><span class="sxs-lookup"><span data-stu-id="0467f-135">When looking for example files to use, see the [form processing model input document requirements and optimization tips](https://docs.microsoft.com/ai-builder/form-processing-model-requirements).</span></span> 

   ![Power apps AI Builder](../media/content-understanding/powerapps.png)</br> 
 
1. <span data-ttu-id="0467f-137">Selecteer **documenten toevoegen** om voorbeelddocumenten toe te voegen om te beginnen met het toevoegen van de benoemde waardeparen die kunnen worden opgehaald.</span><span class="sxs-lookup"><span data-stu-id="0467f-137">Select **Add documents** to begin adding example documents analyzed to determine the named value pairs that can be extracted.</span></span> <span data-ttu-id="0467f-138">U kunt vervolgens uploaden kiezen **van lokale opslag**, **SharePoint**-of **Azure-blobopslag**.</span><span class="sxs-lookup"><span data-stu-id="0467f-138">You can then choose either **Upload from local storage**, **SharePoint**, or **Azure Blob storage**.</span></span> <span data-ttu-id="0467f-139">U dient ten minste vijf bestanden te gebruiken om te kunnen oefenen.</span><span class="sxs-lookup"><span data-stu-id="0467f-139">You need to use at least five files for training.</span></span>

2. <span data-ttu-id="0467f-140">Wanneer u bestanden hebt toegevoegd, selecteert u **analyseren** om te controleren of de gegevens in het algemeen worden weergeven.</span><span class="sxs-lookup"><span data-stu-id="0467f-140">After adding files, select **Analyze** to check for any information common is all files.</span></span> <span data-ttu-id="0467f-141">Het kan een paar minuten duren voordat u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="0467f-141">This may take several minutes to complete.</span></span></br> 
 
    ![Bestanden analyseren](../media/content-understanding/analyze.png)</br> 

3. <span data-ttu-id="0467f-143">Nadat de bestanden zijn geanalyseerd, selecteert u het bestand in de pagina **Selecteer de formuliervelden die u wilt opslaan** in het bestand om de gevonden velden weer te geven.</span><span class="sxs-lookup"><span data-stu-id="0467f-143">After the files have been analyzed, in the **Select the form fields you want to save** page select the file to view the detected fields.</span></span></br>

    ![Formuliervelden selecteren](../media/content-understanding/select-form-fields.png)</br> 

## <a name="step-3-select-your-form-fields"></a><span data-ttu-id="0467f-145">Stap 3: de formuliervelden selecteren</span><span class="sxs-lookup"><span data-stu-id="0467f-145">Step 3: Select your form fields</span></span>

<span data-ttu-id="0467f-146">Nadat u de documenten voor velden hebt geanalyseerd, kunt u nu de gevonden velden zien en de bestanden identificeren die u wilt opslaan.</span><span class="sxs-lookup"><span data-stu-id="0467f-146">After analyzing the documents for fields, you can now see the fields that were found, and identify the ones that you want to save.</span></span> <span data-ttu-id="0467f-147">Opgeslagen velden worden als kolommen weergegeven in de documentbibliotheekweergave van uw model en tonen de waarden die uit elk document worden opgehaald.</span><span class="sxs-lookup"><span data-stu-id="0467f-147">Saved fields display as columns in your model's document library view and show the values extracted from each document.</span></span>

1. <span data-ttu-id="0467f-148">Op de volgende pagina ziet u een van de voorbeeldbestanden en worden alle gemeenschappelijke velden gemarkeerd die automatisch door het systeem zijn gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="0467f-148">The next page displays one of your sample files and will highlight all common fields that were automatically detected by the system.</span></span> </br>

    ![Pagina met velden selecteren](../media/content-understanding/select-fields-page.png)</br> 

2. <span data-ttu-id="0467f-150">Selecteer de velden die u wilt opslaan en schakel het selectievakje in om uw selectie te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="0467f-150">Select the fields that you want to save and select the checkbox to confirm your selection.</span></span> <span data-ttu-id="0467f-151">Kies in het inkooporder model bijvoorbeeld de velden *datum*, *po*en *totaal* .</span><span class="sxs-lookup"><span data-stu-id="0467f-151">For example, in the Purchase Order model, choose to select the *Date*, *PO*, and *Total* fields.</span></span>  <span data-ttu-id="0467f-152">U kunt er ook voor kiezen om de naam van een veld te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="0467f-152">Note that you can also choose to rename a field if you choose.</span></span> </br>

    ![Selecteer PO #](../media/content-understanding/po.png)</br> 

3. <span data-ttu-id="0467f-154">Als een veld niet door de analyse is gedetecteerd, kunt u er nog steeds voor kiezen om het toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="0467f-154">If a field was not detected by analysis, you can still choose to add it.</span></span> <span data-ttu-id="0467f-155">Selecteer de gegevens die u wilt extraheren en typ in het vak Naam de naam van de gewenste gegevens.</span><span class="sxs-lookup"><span data-stu-id="0467f-155">Highlight the information you want to extract, and in the name box type in the name you want.</span></span> <span data-ttu-id="0467f-156">Schakel vervolgens het selectievakje in.</span><span class="sxs-lookup"><span data-stu-id="0467f-156">Then select the check box.</span></span> <span data-ttu-id="0467f-157">Houd er rekening mee dat u niet-gevonden velden in de resterende voorbeeldbestanden moet bevestigen.</span><span class="sxs-lookup"><span data-stu-id="0467f-157">Note that you need to confirm undetected fields in your remaining sample files.</span></span>

4. <span data-ttu-id="0467f-158">Klik op **velden bevestigen** nadat u de velden hebt geselecteerd die u wilt opslaan.</span><span class="sxs-lookup"><span data-stu-id="0467f-158">Click **Confirm fields** after you have selected the fields that you want to save.</span></span> </br>
 
    ![Velden bevestigen na selecteren van velden](../media/content-understanding/confirm-fields.png)</br> 
 
5. <span data-ttu-id="0467f-160">Op de pagina **Selecteer de formuliervelden die u wilt opslaan** , wordt het aantal velden weergegeven dat u hebt geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="0467f-160">On the **Select the form fields you want to save** page, it shows the number of fields you have selected.</span></span> <span data-ttu-id="0467f-161">Selecteer **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="0467f-161">Select **Done**.</span></span>

## <a name="step-4-train-and-test-your-model"></a><span data-ttu-id="0467f-162">Stap 4: uw model trainen en testen</span><span class="sxs-lookup"><span data-stu-id="0467f-162">Step 4: Train and test your model</span></span>

<span data-ttu-id="0467f-163">Nadat u de velden hebt geselecteerd die u wilt opslaan, kunt u uw model trainen en testen met de **overzichtspagina model** .</span><span class="sxs-lookup"><span data-stu-id="0467f-163">After selecting the fields you want to save, the **Model Summary** page lets you train and test your model.</span></span>

1. <span data-ttu-id="0467f-164">Op de pagina **model samenvatting** wordt de opgeslagen velden weergegeven in de sectie **geselecteerde velden** .</span><span class="sxs-lookup"><span data-stu-id="0467f-164">On the **Model Summary** page, the saved fields will show in the **Selected fields** section.</span></span> <span data-ttu-id="0467f-165">Selecteer **training** om de training te beginnen op uw voorbeeldbestanden.</span><span class="sxs-lookup"><span data-stu-id="0467f-165">Select **Train** to begin training on your example files.</span></span> <span data-ttu-id="0467f-166">Dit kan een paar minuten duren.</span><span class="sxs-lookup"><span data-stu-id="0467f-166">Note that this may take a few minutes to complete.</span></span></br>

     ![De velden training selecteren](../media/content-understanding/select-fields-train.png)</br> 

2. <span data-ttu-id="0467f-168">Wanneer de melding wordt weergegeven dat de training is voltooid, selecteert u **Ga naar details pagina**.</span><span class="sxs-lookup"><span data-stu-id="0467f-168">When you see the notification that training has completed, select **Go to details page**.</span></span> 

3. <span data-ttu-id="0467f-169">Op de pagina **model Details** kunt u kiezen hoe u het model gaat gebruiken door **snel testen**te selecteren.</span><span class="sxs-lookup"><span data-stu-id="0467f-169">On the **Model details** page, you can choose to test how your model works by selecting **Quick test**.</span></span> <span data-ttu-id="0467f-170">Hiermee kunt u bestanden slepen en neerzetten naar de pagina om te zien of de velden zijn gevonden.</span><span class="sxs-lookup"><span data-stu-id="0467f-170">This lets you drag and drop files to the page and see if the fields are detected.</span></span>

    ![Velden bevestigen](../media/content-understanding/select-fields-train.png)</br> 

2. <span data-ttu-id="0467f-172">Wanneer de melding wordt weergegeven dat de training is voltooid, selecteert u **Ga naar details pagina**.</span><span class="sxs-lookup"><span data-stu-id="0467f-172">When you see the notification that training has completed, select **Go to details page**.</span></span> 

3. <span data-ttu-id="0467f-173">Op de pagina **model Details** kiest u of u de werking van uw model wilt testen door **snel testen**te selecteren.</span><span class="sxs-lookup"><span data-stu-id="0467f-173">On the **Model details** page, choose to test how your model works by selecting **Quick test**.</span></span> <span data-ttu-id="0467f-174">Hiermee kunt u bestanden slepen en neerzetten naar de pagina om te zien of de velden zijn gevonden.</span><span class="sxs-lookup"><span data-stu-id="0467f-174">This lets you drag and drop files to the page and see if the fields are detected.</span></span>

## <a name="step-5-publish-your-model"></a><span data-ttu-id="0467f-175">Stap 5: uw model publiceren</span><span class="sxs-lookup"><span data-stu-id="0467f-175">Step 5: Publish your model</span></span>

1. <span data-ttu-id="0467f-176">Als u tevreden bent over de resultaten van uw model, selecteert u **publiceren** om het beschikbaar te maken voor gebruik.</span><span class="sxs-lookup"><span data-stu-id="0467f-176">If you are satisfied with the results of your model, select **Publish** to make it available for use.</span></span>

2. <span data-ttu-id="0467f-177">Wanneer het model is gepubliceerd, selecteert **u model gebruiken**.</span><span class="sxs-lookup"><span data-stu-id="0467f-177">After the model is published, select **Use model**.</span></span> <span data-ttu-id="0467f-178">Hiermee maakt u een PowerAutomate-stroom die kan worden uitgevoerd in uw SharePoint-documentbibliotheek en worden de velden die in het model zijn gevonden, uitgepakt en selecteert u **stroom maken**.</span><span class="sxs-lookup"><span data-stu-id="0467f-178">This creates a PowerAutomate flow that can run in your SharePoint document library and extracts the fields that have been identified in the model, then select **Create Flow**.</span></span>
  
3. <span data-ttu-id="0467f-179">Wanneer u klaar bent, wordt het bericht weergegeven dat **uw stroom is gemaakt**.</span><span class="sxs-lookup"><span data-stu-id="0467f-179">When completed, you will see the message **Your flow has been successfully created**.</span></span>
 
## <a name="step-6-use-your-model"></a><span data-ttu-id="0467f-180">Stap 6: uw model gebruiken</span><span class="sxs-lookup"><span data-stu-id="0467f-180">Step 6: Use your model</span></span>

<span data-ttu-id="0467f-181">Nadat u uw model hebt gepubliceerd en de PowerAutomate-stroom hebt gemaakt, kunt u uw model gebruiken in de SharePoint-documentbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="0467f-181">After publishing your model and creating it's PowerAutomate flow, you can use your model in your SharePoint document library.</span></span>

1. <span data-ttu-id="0467f-182">Wanneer u uw model hebt gepubliceerd, selecteert u **Ga naar SharePoint** om naar de documentbibliotheek te gaan.</span><span class="sxs-lookup"><span data-stu-id="0467f-182">After publishing your model, select **Go to SharePoint** to go to your document library.</span></span>

2. <span data-ttu-id="0467f-183">In de modelweergave documentbibliotheek ziet u dat de velden die u nu als kolommen hebt geselecteerd, worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="0467f-183">In the document library model view, notice that the fields you selected now display as columns.</span></span></br>

    ![Gesolliciteerd document bibliotheek model](../media/content-understanding/doc-lib-view.png)</br> 

3. <span data-ttu-id="0467f-185">De koppeling informatie naast **documenten** die een model voor formulierverwerking op deze documentbibliotheek toepast.</span><span class="sxs-lookup"><span data-stu-id="0467f-185">Notice that the information link next to **Documents** notes that a forms processing model is applied to this document library.</span></span>

    ![Knop Info](../media/content-understanding/info-button.png)</br>  

4. <span data-ttu-id="0467f-187">Upload bestanden naar de documentbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="0467f-187">Upload files to your document library.</span></span> <span data-ttu-id="0467f-188">Alle bestanden die het model als het inhoudstype identificeert, worden weergegeven in de bestanden in de weergave en de opgehaalde gegevens in de kolommen.</span><span class="sxs-lookup"><span data-stu-id="0467f-188">Any files that the model identifies as it's content type lists the files in your view and displays the extracted data in the columns.</span></span></br>

    ![Gereed](../media/content-understanding/doc-lib-done.png)</br>  

## <a name="see-also"></a><span data-ttu-id="0467f-190">Zie ook</span><span class="sxs-lookup"><span data-stu-id="0467f-190">See Also</span></span>
  
[<span data-ttu-id="0467f-191">De documentatie voor Power Automatiseer</span><span class="sxs-lookup"><span data-stu-id="0467f-191">Power Automate documentation</span></span>](https://docs.microsoft.com/power-automate/)</br>
[<span data-ttu-id="0467f-192">Training: bedrijfsprestaties verbeteren met AI Builder</span><span class="sxs-lookup"><span data-stu-id="0467f-192">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>
