---
title: Een formulierverwerkingsmodel maken (Voorbeeld)
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
description: Maak een formulierverwerkingsmodel in Project Cortex.
ms.openlocfilehash: d3ca64ff5923e95704b72fd748884549a18624a3
ms.sourcegitcommit: 3a47efcbdf3d2b39caa2798ea5be806839b05ed1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/01/2020
ms.locfileid: "46540140"
---
# <a name="create-a-form-processing-model-preview"></a><span data-ttu-id="aa14e-103">Een formulierverwerkingsmodel maken (Voorbeeld)</span><span class="sxs-lookup"><span data-stu-id="aa14e-103">Create a form processing model (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="aa14e-104">De inhoud in dit artikel is voor Project Cortex Private Preview.</span><span class="sxs-lookup"><span data-stu-id="aa14e-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="aa14e-105">[Lees meer over Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="aa14e-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="aa14e-106">Met behulp van [AI Builder](https://docs.microsoft.com/ai-builder/overview) - een functie in Microsoft PowerApps - kunnen Project Cortex-gebruikers rechtstreeks vanuit een SharePoint-documentbibliotheek een [formulierverwerkingsmodel](form-processing-overview.md) maken.</span><span class="sxs-lookup"><span data-stu-id="aa14e-106">Using [AI Builder](https://docs.microsoft.com/ai-builder/overview) - a feature in Microsoft PowerApps - Project Cortex users can create a [form processing model](form-processing-overview.md) directly from a SharePoint document library.</span></span> 

<span data-ttu-id="aa14e-107">Het maken van een formulierverwerkingsmodel omvat het volgende:</span><span class="sxs-lookup"><span data-stu-id="aa14e-107">Creating a form processing model involves the following:</span></span>
 - <span data-ttu-id="aa14e-108">Stap 1: Het van-verwerkingsmodel maken om het inhoudstype te maken</span><span class="sxs-lookup"><span data-stu-id="aa14e-108">Step 1: Create the from processing model to create the content type</span></span>
 - <span data-ttu-id="aa14e-109">Stap 2: Voorbeeldbestanden toevoegen en analyseren</span><span class="sxs-lookup"><span data-stu-id="aa14e-109">Step 2: Add and analyze example files</span></span>
 - <span data-ttu-id="aa14e-110">Stap 3: Uw formuliervelden selecteren</span><span class="sxs-lookup"><span data-stu-id="aa14e-110">Step 3: Select your form fields</span></span>
 - <span data-ttu-id="aa14e-111">Stap 4: Train en test je model</span><span class="sxs-lookup"><span data-stu-id="aa14e-111">Step 4: Train and test your model</span></span>
 - <span data-ttu-id="aa14e-112">Stap 5: Uw model publiceren</span><span class="sxs-lookup"><span data-stu-id="aa14e-112">Step 5: Publish your model</span></span>
 - <span data-ttu-id="aa14e-113">Stap 6: Gebruik uw model</span><span class="sxs-lookup"><span data-stu-id="aa14e-113">Step 6: Use your model</span></span>


## <a name="requirements"></a><span data-ttu-id="aa14e-114">Vereisten</span><span class="sxs-lookup"><span data-stu-id="aa14e-114">Requirements</span></span>

<span data-ttu-id="aa14e-115">U alleen een formulierverwerkingsmodel maken in SharePoint-documentbibliotheken waarin het is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="aa14e-115">You can only create a form processing model in SharePoint document libraries in which it is enabled.</span></span> <span data-ttu-id="aa14e-116">Als formulierverwerking is ingeschakeld, u de **AI Builder** **'Een formulierverwerkingsmodel maken'** zien onder het menu **Automatiseren** in uw documentbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="aa14e-116">If form processing is enabled, you will be able to see the **AI Builder** **"Create a form processing model'** under the **Automate** menu in your document library.</span></span>  <span data-ttu-id="aa14e-117">Als de verwerking in de documentbibliotheek is ingeschakeld, neemt u contact op met de beheerder.</span><span class="sxs-lookup"><span data-stu-id="aa14e-117">If you need from processing enabled on your document library, contact your admin.</span></span>

 ![Een AI Builder-model maken](../media/content-understanding/create-ai-builder-model.png)</br>


## <a name="step-1-create-a-form-processing-model"></a><span data-ttu-id="aa14e-119">Stap 1: Een formulierverwerkingsmodel maken</span><span class="sxs-lookup"><span data-stu-id="aa14e-119">Step 1: Create a Form Processing model</span></span>

<span data-ttu-id="aa14e-120">De eerste stap bij het maken van een formulierverwerkingsmodel is de naam te geven om het nieuwe inhoudstype te definiëren en er een nieuwe documentbibliotheekweergave voor te maken.</span><span class="sxs-lookup"><span data-stu-id="aa14e-120">The first step in creating a form processing model is to name it to create the define the new content type and create a new document library view for it.</span></span>

1. <span data-ttu-id="aa14e-121">Selecteer in de documentbibliotheek het menu **Automatiseren,** selecteer **AI Builder**en selecteer **vervolgens Een formulierverwerkingsmodel maken.**</span><span class="sxs-lookup"><span data-stu-id="aa14e-121">In your document library, select the **Automate** menu, select **AI Builder**, and then select **Create a Form Processing model**.</span></span>

    ![Een AI Builder-model maken](../media/content-understanding/create-ai-builder-model.png)</br>
2. <span data-ttu-id="aa14e-123">Typ in het deelvenster Modellen van **het nieuwe formulierverwerkingsmodel** in het veld **Naam** een naam voor uw model (bijvoorbeeld *Inkooporders).*</span><span class="sxs-lookup"><span data-stu-id="aa14e-123">In the **New form processing model** pane, in the  **Name** field, type a name for your model (for example, *Purchase Orders*).</span></span>

    ![Nieuw formulierverwerkingsmodel](../media/content-understanding/new-form-model.png)</br> 

3. <span data-ttu-id="aa14e-125">Wanneer u een formulierverwerkingsmodel maakt, maakt u een nieuw SharePoint-inhoudstype.</span><span class="sxs-lookup"><span data-stu-id="aa14e-125">When you create a form processing model, you are creating a new SharePoint content type.</span></span> <span data-ttu-id="aa14e-126">Een SharePoint-inhoudstype vertegenwoordigt een categorie documenten met algemene kenmerken en deelt een verzameling kolommen of metagegevens eigenschappen voor die bepaalde inhoud.</span><span class="sxs-lookup"><span data-stu-id="aa14e-126">A SharePoint content type represents a category of documents that have common characteristics and share a collection of columns or metadata properties for that particular content.</span></span> <span data-ttu-id="aa14e-127">SharePoint-inhoudstypen worden beheerd via de [galerie Inhoudstypen]().</span><span class="sxs-lookup"><span data-stu-id="aa14e-127">SharePoint Content Types are managed through the [Content types gallery]().</span></span>

    <span data-ttu-id="aa14e-128">Selecteer **Geavanceerde instellingen** als u dit model wilt toewijzen aan een bestaand inhoudstype in de galerie Met SharePoint-inhoudstypen om het schema te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="aa14e-128">Select **Advanced settings** if you want to map this model to an existing content type in the SharePoint Content types gallery to use its schema.</span></span> 

4. <span data-ttu-id="aa14e-129">Uw model maakt een nieuwe weergave in uw documentbibliotheek voor uw uitgepakte gegevens.</span><span class="sxs-lookup"><span data-stu-id="aa14e-129">Your model will create a new view in your document library for your extracted data.</span></span> <span data-ttu-id="aa14e-130">Als u niet wilt dat deze in de standaardweergave wordt weergegeven, schakelt u **de optie De weergave als standaard instellen uit.**</span><span class="sxs-lookup"><span data-stu-id="aa14e-130">If you do not want it to the default view, deselect **Set the view as default**.</span></span>
5. <span data-ttu-id="aa14e-131">Selecteer **Maken**.</span><span class="sxs-lookup"><span data-stu-id="aa14e-131">Select **Create**.</span></span>


## <a name="step-2-add-and-analyze-documents"></a><span data-ttu-id="aa14e-132">Stap 2: Documenten toevoegen en analyseren</span><span class="sxs-lookup"><span data-stu-id="aa14e-132">Step 2: Add and analyze documents</span></span>

<span data-ttu-id="aa14e-133">Nadat u uw nieuwe formulierverwerkingsmodel hebt gemaakt, opent uw browser een nieuwe PowerApps AI Builder-formulierverwerkingsmodelpagina.</span><span class="sxs-lookup"><span data-stu-id="aa14e-133">After you create your new form processing model, your browser will open a new PowerApps AI Builder forms processing model page.</span></span> <span data-ttu-id="aa14e-134">Op deze pagina u uw voorbeelddocumenten toevoegen en analyseren.</span><span class="sxs-lookup"><span data-stu-id="aa14e-134">On this page you can add and analyze your example documents.</span></span> </br>

> [!Note]
> <span data-ttu-id="aa14e-135">Zie de vereisten voor het [invoerdocument en de optimalisatietips voor formulierverwerkingsmodel](https://docs.microsoft.com/ai-builder/form-processing-model-requirements)bij het zoeken naar bijvoorbeeld bestanden.</span><span class="sxs-lookup"><span data-stu-id="aa14e-135">When looking for example files to use, see the [form processing model input document requirements and optimization tips](https://docs.microsoft.com/ai-builder/form-processing-model-requirements).</span></span> 

   ![Power Apps AI Builder](../media/content-understanding/powerapps.png)</br> 
 

1. <span data-ttu-id="aa14e-137">Klik **op Documenten toevoegen** om voorbeelddocumenten toe te voegen die worden geanalyseerd om te bepalen welke benoemde waardeparen kunnen worden geëxtraheerd.</span><span class="sxs-lookup"><span data-stu-id="aa14e-137">Click **Add documents** to begin adding example documents that are analyzed to determine what named value pairs can be extracted.</span></span> <span data-ttu-id="aa14e-138">U **kiezen uit Uploaden vanuit lokale opslag,** **SharePoint**of **Azure Blob-opslag.**</span><span class="sxs-lookup"><span data-stu-id="aa14e-138">You can choose either **Upload from local storage**, **SharePoint**, or **Azure Blob storage**.</span></span> <span data-ttu-id="aa14e-139">U moet ten minste vijf bestanden gebruiken voor training.</span><span class="sxs-lookup"><span data-stu-id="aa14e-139">You will need to use at least five files for training.</span></span>
2. <span data-ttu-id="aa14e-140">Nadat u uw bestanden hebt toegevoegd, selecteert u **Analyseren** om te controleren op alle algemene informatie die alle bestanden zijn.</span><span class="sxs-lookup"><span data-stu-id="aa14e-140">After adding your files, select **Analyze** to check for any information that is common is all files.</span></span> <span data-ttu-id="aa14e-141">Houd er rekening mee dat dit enkele minuten kan duren.</span><span class="sxs-lookup"><span data-stu-id="aa14e-141">Note that this may take several minutes to complete.</span></span></br> 
 
    ![Bestanden analyseren](../media/content-understanding/analyze.png)</br> 

3. <span data-ttu-id="aa14e-143">Nadat ze zijn geanalyseerd, klikt u in de **pagina Formuliervelden selecteren die u wilt opslaan** op het bestand om de gedetecteerde velden weer te geven.</span><span class="sxs-lookup"><span data-stu-id="aa14e-143">After they have been analyzed, in the **Select the form fields you want to save** page, click the file to see the fields that were detected.</span></span></br>

    ![Formuliervelden selecteren](../media/content-understanding/select-form-fields.png)</br> 

## <a name="step-3-select-your-form-fields"></a><span data-ttu-id="aa14e-145">Stap 3: Uw formuliervelden selecteren</span><span class="sxs-lookup"><span data-stu-id="aa14e-145">Step 3: Select your form fields</span></span>

<span data-ttu-id="aa14e-146">Nadat u uw documenten voor velden hebt geanalyseerd, u nu zien welke velden zijn gevonden en welke velden u wilt opslaan.</span><span class="sxs-lookup"><span data-stu-id="aa14e-146">After analyzing your documents for fields, you can now see which fields were found, and which ones you want to save.</span></span> <span data-ttu-id="aa14e-147">Opgeslagen velden worden weergegeven als kolommen in de documentbibliotheekweergave van uw model en geven de waarden weer die uit elk document zijn geëxtraheerd.</span><span class="sxs-lookup"><span data-stu-id="aa14e-147">Saved fields will display as columns in your model's document library view and will show the values extracted from each document.</span></span>

1. <span data-ttu-id="aa14e-148">Op de volgende pagina wordt een van uw voorbeeldbestanden weergegeven en worden alle veelvoorkomende velden weergegeven die automatisch door het systeem zijn gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="aa14e-148">The next page will display one of your sample files and will highlight all common fields that were automatically detected by the system.</span></span> </br>

    ![Formuliervelden selecteren](../media/content-understanding/select-fields-page.png)</br> 

2. <span data-ttu-id="aa14e-150">Selecteer de velden die u wilt opslaan en schakel het selectievakje in om uw selectie te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="aa14e-150">Select the fields you want to save, and select the checkbox to confirm your selection.</span></span> <span data-ttu-id="aa14e-151">In het model Inkooporder u er bijvoorbeeld voor kiezen om de velden *Datum,* *PO*en *Totaal* te selecteren.</span><span class="sxs-lookup"><span data-stu-id="aa14e-151">For example, in the Purchase Order model, you can choose to select the *Date*, *PO*, and *Total* fields.</span></span>  <span data-ttu-id="aa14e-152">Houd er rekening mee dat u er ook voor kiezen om de naam van een veld te wijzigen als u dat wilt.</span><span class="sxs-lookup"><span data-stu-id="aa14e-152">Note that you can also choose to rename a field if you choose.</span></span> </br>

    ![Po selecteren #](../media/content-understanding/po.png)</br> 

3. <span data-ttu-id="aa14e-154">Als een veld niet is gedetecteerd door analyse, u er nog steeds voor kiezen om het toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="aa14e-154">If a field was not detected by analysis, you can still choose to add it.</span></span> <span data-ttu-id="aa14e-155">Markeer de informatie die u wilt extraheren en typ in het vak Naam in de naam die u wilt opgeven.</span><span class="sxs-lookup"><span data-stu-id="aa14e-155">Highlight the information you want to extract, and in the name box type in the name you want to give it.</span></span> <span data-ttu-id="aa14e-156">Selecteer vervolgens de cheque.</span><span class="sxs-lookup"><span data-stu-id="aa14e-156">Then select the check.</span></span> <span data-ttu-id="aa14e-157">Houd er rekening mee dat u onontdekte velden in uw resterende voorbeeldbestanden moet bevestigen.</span><span class="sxs-lookup"><span data-stu-id="aa14e-157">Note that you will need to confirm undetected fields in your remaining example files.</span></span>
4. <span data-ttu-id="aa14e-158">Klik **op Velden bevestigen** nadat u de velden hebt geselecteerd die u wilt opslaan.</span><span class="sxs-lookup"><span data-stu-id="aa14e-158">Click **Confirm fields** after you have selected the fields you want to save.</span></span> </br>
 
    ![Velden bevestigen](../media/content-understanding/confirm-fields.png)</br> 
 
5. <span data-ttu-id="aa14e-160">Op de **pagina Formuliervelden selecteren die u wilt opslaan,** wordt het aantal velden weergegeven dat u hebt geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="aa14e-160">On the **Select the form fields you want to save** page, it will show the number of fields you have selected.</span></span> <span data-ttu-id="aa14e-161">Selecteer **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="aa14e-161">Select **Done**.</span></span>

## <a name="step-4-train-and-test-your-model"></a><span data-ttu-id="aa14e-162">Stap 4: Train en test je model</span><span class="sxs-lookup"><span data-stu-id="aa14e-162">Step 4: Train and test your model</span></span>

<span data-ttu-id="aa14e-163">Nadat u de velden hebt geselecteerd die u wilt opslaan, u op de pagina **Modeloverzicht** uw model trainen en testen.</span><span class="sxs-lookup"><span data-stu-id="aa14e-163">After selecting the fields you want to save, the **Model Summary** page will let you train and test your model.</span></span>

1. <span data-ttu-id="aa14e-164">Op de pagina **Modeloverzicht** worden de opgeslagen velden weergegeven in de sectie **Geselecteerde velden.**</span><span class="sxs-lookup"><span data-stu-id="aa14e-164">On the **Model Summary** page, the saved fields will show in the **Selected fields** section.</span></span> <span data-ttu-id="aa14e-165">Selecteer **Trainen** om te beginnen met trainen in uw voorbeeldbestanden.</span><span class="sxs-lookup"><span data-stu-id="aa14e-165">Select **Train** to begin training on your example files.</span></span> <span data-ttu-id="aa14e-166">Houd er rekening mee dat dit enkele minuten kan duren.</span><span class="sxs-lookup"><span data-stu-id="aa14e-166">Note that this may take a few minutes to complete.</span></span></br>
    <span data-ttu-id="aa14e-167">![Velden bevestigen](../media/content-understanding/select-fields-train.png)</span><span class="sxs-lookup"><span data-stu-id="aa14e-167">![Confirm fields](../media/content-understanding/select-fields-train.png)</span></span></br> 
2. <span data-ttu-id="aa14e-168">Wanneer u de melding ziet die de training heeft voltooid, selecteert u **Pagina Ga naar details**.</span><span class="sxs-lookup"><span data-stu-id="aa14e-168">When you see the notification that training has completed, select **Go to details page**.</span></span> 
3. <span data-ttu-id="aa14e-169">Op de pagina **Modeldetails** u ervoor kiezen om te testen hoe uw model werkt door **snelle test**te selecteren.</span><span class="sxs-lookup"><span data-stu-id="aa14e-169">On the **Model details** page, you can choose to test how your model works by selecting **Quick test**.</span></span> <span data-ttu-id="aa14e-170">Hiermee u bestanden naar de pagina slepen en neerzetten en kijken of de velden worden gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="aa14e-170">This lets you drag and drop files to the page and see if the fields are detected.</span></span>

## <a name="step-5-publish-your-model"></a><span data-ttu-id="aa14e-171">Stap 5: Uw model publiceren</span><span class="sxs-lookup"><span data-stu-id="aa14e-171">Step 5: Publish your model</span></span>



1. <span data-ttu-id="aa14e-172">Als u tevreden bent met de resultaten van uw model, selecteert u **Publiceren** om het beschikbaar te maken voor gebruik.</span><span class="sxs-lookup"><span data-stu-id="aa14e-172">If you are satisfied with the results of your model, select **Publish** to make it available for use.</span></span>
2. <span data-ttu-id="aa14e-173">Selecteer Na de publicatie van het model **het model gebruiken**.</span><span class="sxs-lookup"><span data-stu-id="aa14e-173">After the model published, select **Use model**.</span></span> <span data-ttu-id="aa14e-174">Hiermee wordt een PowerAutomate-stroom gemaakt die wordt uitgevoerd in uw SharePoint-documentbibliotheek en de velden die in het model zijn geïdentificeerd, wordt geëxtraheerd.</span><span class="sxs-lookup"><span data-stu-id="aa14e-174">This creates a PowerAutomate flow that will run in your SharePoint document library and will extract the fields that have been identified in the model.</span></span> <span data-ttu-id="aa14e-175">Selecteer **Stroom maken**.</span><span class="sxs-lookup"><span data-stu-id="aa14e-175">Select **Create Flow**.</span></span>  
3. <span data-ttu-id="aa14e-176">Wanneer voltooid, ziet u het bericht **Uw stroom is gemaakt**.</span><span class="sxs-lookup"><span data-stu-id="aa14e-176">When completed, you will see the message **Your flow has been successfully created**.</span></span>
 
 
## <a name="step-6-use-your-model"></a><span data-ttu-id="aa14e-177">Stap 6: Gebruik uw model</span><span class="sxs-lookup"><span data-stu-id="aa14e-177">Step 6: Use your model</span></span>

<span data-ttu-id="aa14e-178">Nadat u uw model hebt gepubliceerd en de PowerAutomate-stroom hebt gemaakt, u uw model gebruiken in uw SharePoint-documentbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="aa14e-178">After publishing your model and creating it's PowerAutomate flow, you can use your model in your SharePoint document library.</span></span>

1. <span data-ttu-id="aa14e-179">Nadat u uw model hebt gepubliceerd, selecteert u **Ga naar SharePoint** om naar uw documentbibliotheek te gaan.</span><span class="sxs-lookup"><span data-stu-id="aa14e-179">After publishing your model , select **Go to SharePoint** to go to your document library.</span></span>
2. <span data-ttu-id="aa14e-180">Let er in de modelweergave van de documentbibliotheek op dat de velden die u hebt geselecteerd nu als kolommen worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="aa14e-180">On your document library model view, notice that the fields you selected now display as columns.</span></span></br>

    ![Documentbibliotheek met toegepast model](../media/content-understanding/doc-lib-view.png)</br> 

    <span data-ttu-id="aa14e-182">Houd er ook rekening mee dat de informatiekoppeling naast **Documenten** er rekening mee houdt dat een formulierverwerkingsmodel wordt toegepast op deze documentbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="aa14e-182">Also notice that the information link next to **Documents** will note that a forms processing model is applied to this document library.</span></span>

    ![Uitgepakt](../media/content-understanding/info-button.png)</br>  

3. <span data-ttu-id="aa14e-184">Bestanden uploaden naar uw documentbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="aa14e-184">Upload files to your document library.</span></span> <span data-ttu-id="aa14e-185">Alle bestanden die het model identificeert als het inhoudstype, geven een lijst van de bestanden in uw weergave en geven de uitgepakte gegevens in de kolommen weer.</span><span class="sxs-lookup"><span data-stu-id="aa14e-185">Any files that the model identifies as it's content type will list the files in your view, and will display the extracted data in the columns.</span></span></br>

    ![Uitgepakt](../media/content-understanding/doc-lib-done.png)</br>  



## <a name="see-also"></a><span data-ttu-id="aa14e-187">Zie ook</span><span class="sxs-lookup"><span data-stu-id="aa14e-187">See Also</span></span>
  
[<span data-ttu-id="aa14e-188">Documentatie voor energie automatiseren</span><span class="sxs-lookup"><span data-stu-id="aa14e-188">Power Automate documentation</span></span>](https://docs.microsoft.com/power-automate/)</br>
[<span data-ttu-id="aa14e-189">Training: Verbeter de bedrijfsprestaties met AI Builder</span><span class="sxs-lookup"><span data-stu-id="aa14e-189">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>




