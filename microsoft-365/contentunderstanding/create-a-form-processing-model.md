---
title: Een formulierverwerkingsmodel maken
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: Maak een formulierverwerkingmodel in Microsoft SharePoint Syntex.
ms.openlocfilehash: aed918d899fe7c5e3c49b733d2411c178e9b98d0
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087689"
---
# <a name="create-a-form-processing-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="ce6db-103">Maak een formulierverwerkingmodel in Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="ce6db-103">Create a form processing model in Microsoft SharePoint Syntex</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GnhN]  

</br>

<span data-ttu-id="ce6db-104">Met [AI-Builder](https://docs.microsoft.com/ai-builder/overview) - een functie in Microsoft PowerApps - SharePoint-gebruikers kunnen een [formulierverwerkingsmodel](form-processing-overview.md) rechtstreeks vanuit een SharePoint-documentbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="ce6db-104">Using [AI Builder](https://docs.microsoft.com/ai-builder/overview) - a feature in Microsoft PowerApps - SharePoint Syntex users can create a [form processing model](form-processing-overview.md) directly from a SharePoint document library.</span></span> 

<span data-ttu-id="ce6db-105">Het maken van een formulierverwerkingsmodel omvat het volgende:</span><span class="sxs-lookup"><span data-stu-id="ce6db-105">Creating a form processing model involves the following:</span></span>
 - <span data-ttu-id="ce6db-106">Stap 1: maak het formulierverwerkingsmodel om het inhoudstype te maken</span><span class="sxs-lookup"><span data-stu-id="ce6db-106">Step 1: Create the from processing model to create the content type</span></span>
 - <span data-ttu-id="ce6db-107">Stap 2: voorbeeldbestanden toevoegen en analyseren</span><span class="sxs-lookup"><span data-stu-id="ce6db-107">Step 2: Add and analyze example files</span></span>
 - <span data-ttu-id="ce6db-108">Stap 3: de formuliervelden selecteren</span><span class="sxs-lookup"><span data-stu-id="ce6db-108">Step 3: Select your form fields</span></span>
 - <span data-ttu-id="ce6db-109">Stap 4: trainen testen van je model</span><span class="sxs-lookup"><span data-stu-id="ce6db-109">Step 4: Train and test your model</span></span>
 - <span data-ttu-id="ce6db-110">Stap 5: uw model publiceren</span><span class="sxs-lookup"><span data-stu-id="ce6db-110">Step 5: Publish your model</span></span>
 - <span data-ttu-id="ce6db-111">Stap 6: uw model gebruiken</span><span class="sxs-lookup"><span data-stu-id="ce6db-111">Step 6: Use your model</span></span>

## <a name="requirements"></a><span data-ttu-id="ce6db-112">Vereisten</span><span class="sxs-lookup"><span data-stu-id="ce6db-112">Requirements</span></span>

<span data-ttu-id="ce6db-p101">U kunt alleen een model voor het verwerken van een formulier maken in de SharePoint-documentbibliotheken waarvoor het model is ingeschakeld. Als de verwerking van formulieren is ingeschakeld, ziet u de **AI Builder** **Een formulierverwerkingsmodel maken** onder het menu **Automate** in de documentbibliotheek.  Als u verwerking wilt inschakelen voor uw documentbibliotheek, moet u contact opnemen met uw SharePoint-beheerder.</span><span class="sxs-lookup"><span data-stu-id="ce6db-p101">You can only create a form processing model in SharePoint document libraries for which it is enabled. If form processing is enabled, you are able to see the **AI Builder** **"Create a form processing model'** under the **Automate** menu in your document library.  If you need processing enabled on your document library, you must contact your SharePoint administrator.</span></span>

 ![Een AI Builder-model maken](../media/content-understanding/create-ai-builder-model.png)</br>

## <a name="step-1-create-a-form-processing-model"></a><span data-ttu-id="ce6db-117">Stap 1: Een formulierverwerkingsmodel maken</span><span class="sxs-lookup"><span data-stu-id="ce6db-117">Step 1: Create a form processing model</span></span>

<span data-ttu-id="ce6db-118">De eerste stap bij het maken van een formulierverwerkingsmodel is het een naam te geven, het nieuwe inhoudstype te definiëren en de bijbehorende nieuwe documentbibliotheekweergave te maken.</span><span class="sxs-lookup"><span data-stu-id="ce6db-118">The first step in creating a form processing model is to name it and create the define the new content type and create a new document library view for it.</span></span>

1. <span data-ttu-id="ce6db-119">Selecteer in de documentbibliotheek het menu **Automatisch openen**, selecteer **AI-Builder** en selecteer vervolgens **Een formulierverwerkingsmodel maken**.</span><span class="sxs-lookup"><span data-stu-id="ce6db-119">From the document library, select the **Automate** menu, select **AI Builder**, and then select **Create a Form Processing model**.</span></span>

    ![Een model kiezen](../media/content-understanding/create-ai-builder-model.png)</br>

2. <span data-ttu-id="ce6db-121">Typ in het deelvenster **Nieuw formulierverwerkingsmodel** in het veld **naam** een naam voor je model (bijvoorbeeld *aankoop orders*).</span><span class="sxs-lookup"><span data-stu-id="ce6db-121">In the **New form processing model** pane, in the  **Name** field, type a name for your model (for example, *Purchase Orders*).</span></span>

    ![Nieuw Formulierverwerkingsmodel](../media/content-understanding/new-form-model.png)</br> 

3. <span data-ttu-id="ce6db-p102">Wanneer u een formulierverwerkingsmodel maakt, maakt u een nieuw SharePoint-inhoudstype. Een SharePoint-inhoudstype is een categorie documenten met gemeenschappelijke kenmerken en kolommen of metagegevenseigenschappen die inhoud delen. SharePoint-inhoudstypen worden beheerd via de [Galerie met inhoudstypen]().</span><span class="sxs-lookup"><span data-stu-id="ce6db-p102">When you create a form processing model, you create a new SharePoint content type. A SharePoint content type represents a category of documents that have common characteristics and share a collection of columns or metadata properties for that particular content. SharePoint Content Types are managed through the [Content types gallery]().</span></span>

    <span data-ttu-id="ce6db-126">Selecteer **Geavanceerde instellingen** als je dit model wilt toewijzen aan een bestaand inhoudstype in de SharePoint-galerie met inhoudstypen om het bijbehorende schema te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="ce6db-126">Select **Advanced settings** if you want to map this model to an existing content type in the SharePoint Content types gallery to use its schema.</span></span> 

4. <span data-ttu-id="ce6db-p103">Het model maakt in uw documentbibliotheek een nieuwe weergave voor de geëxtraheerde gegevens. Als u de standaardweergave niet wilt weergeven, schakelt u **De weergave instellen als standaard** uit.</span><span class="sxs-lookup"><span data-stu-id="ce6db-p103">Your model creates a new view in your document library for your extracted data. If you do not want it to the default view, deselect **Set the view as default**.</span></span>

5. <span data-ttu-id="ce6db-129">Selecteer **Maken**. </span><span class="sxs-lookup"><span data-stu-id="ce6db-129">Select **Create**.</span></span>

## <a name="step-2-add-and-analyze-documents"></a><span data-ttu-id="ce6db-130">Stap 2: Documenten toevoegen en analyseren</span><span class="sxs-lookup"><span data-stu-id="ce6db-130">Step 2: Add and analyze documents</span></span>

<span data-ttu-id="ce6db-p104">Wanneer u een nieuw model voor formulierverwerking hebt gemaakt, wordt in uw browser een nieuwe pagina voor een model van formulierverwerking van PowerApps Al Builder geopend. Op deze pagina kunt u voorbeelddocumenten toevoegen en analyseren.</span><span class="sxs-lookup"><span data-stu-id="ce6db-p104">After you create your new form processing model, your browser opens a new PowerApps AI Builder forms processing model page. On this page you can add and analyze your example documents.</span></span> </br>

> [!NOTE]
> <span data-ttu-id="ce6db-133">Als je voorbeeldbestanden zoekt die je wilt gebruiken, raadpleeg je de [ vereisten voor formulierverwerkingseisen en optimaliseringstips](https://docs.microsoft.com/ai-builder/form-processing-model-requirements).</span><span class="sxs-lookup"><span data-stu-id="ce6db-133">When looking for example files to use, see the [form processing model input document requirements and optimization tips](https://docs.microsoft.com/ai-builder/form-processing-model-requirements).</span></span> 

   ![Power Apps AI Builder](../media/content-understanding/powerapps.png)</br> 
 
1. <span data-ttu-id="ce6db-p105">Selecteer **Documenten toevoegen** om voorbeelddocumenten toe te voegen die worden geanalyseerd om te bepalen welke benoemde waardeparen kunnen worden geëxtraheerd. U kunt vervolgens **Uploaden van lokale opslag** **SharePoint** of **Azure Blob-opslag**. U moet ten minste vijf bestanden gebruiken voor de training.</span><span class="sxs-lookup"><span data-stu-id="ce6db-p105">Select **Add documents** to begin adding example documents analyzed to determine the named value pairs that can be extracted. You can then choose either **Upload from local storage**, **SharePoint**, or **Azure Blob storage**. You need to use at least five files for training.</span></span>

2. <span data-ttu-id="ce6db-p106">Nadat u bestanden hebt toegevoegd, selecteert u **Analyseren** om gemeenschappelijke gegevens in alle bestanden te controleren. Dit kan enkele minuten duren.</span><span class="sxs-lookup"><span data-stu-id="ce6db-p106">After adding files, select **Analyze** to check for any information common is all files. This may take several minutes to complete.</span></span></br> 
 
    ![Bestanden analyseren](../media/content-understanding/analyze.png)</br> 

3. <span data-ttu-id="ce6db-141">Nadat de bestanden zijn geanalyseerd, selecteer je in **de formuliervelden die je wilt opslaan** pagina selecteer je het bestand om de gevonden velden weer te geven.</span><span class="sxs-lookup"><span data-stu-id="ce6db-141">After the files have been analyzed, in the **Select the form fields you want to save** page select the file to view the detected fields.</span></span></br>

    ![Formuliervelden selecteren](../media/content-understanding/select-form-fields.png)</br> 

## <a name="step-3-select-your-form-fields"></a><span data-ttu-id="ce6db-143">Stap 3: De formuliervelden selecteren</span><span class="sxs-lookup"><span data-stu-id="ce6db-143">Step 3: Select your form fields</span></span>

<span data-ttu-id="ce6db-p107">Nadat u de documenten voor velden hebt geanalyseerd, ziet u nu de velden die werden gevonden en identificeert u de velden die u wilt opslaan. Opgeslagen velden worden als kolommen weergegeven in de documentbibliotheek van uw model en tonen de geëxtraheerde waarden van elk document.</span><span class="sxs-lookup"><span data-stu-id="ce6db-p107">After analyzing the documents for fields, you can now see the fields that were found, and identify the ones that you want to save. Saved fields display as columns in your model's document library view and show the values extracted from each document.</span></span>

1. <span data-ttu-id="ce6db-146">Op de volgende pagina wordt een van de voorbeeldbestanden weergegeven en worden alle gemeenschappelijke velden gemarkeerd die automatisch door het systeem zijn gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="ce6db-146">The next page displays one of your sample files and will highlight all common fields that were automatically detected by the system.</span></span> </br>

    ![Paginavelden selecteren](../media/content-understanding/select-fields-page.png)</br> 

2. <span data-ttu-id="ce6db-p108">Selecteer de velden die u wilt opslaan en schakel het selectievakje in om de selectie te bevestigen. In het Purchase Order-model selecteert u bijvoorbeeld de *Datum-* *PO-* en *Totaal* velden.  U kunt er ook voor kiezen om de naam van een veld te wijzigen. </span><span class="sxs-lookup"><span data-stu-id="ce6db-p108">Select the fields that you want to save and select the checkbox to confirm your selection. For example, in the Purchase Order model, choose to select the *Date*, *PO*, and *Total* fields.  Note that you can also choose to rename a field if you choose. </span></span></br>

    ![Selecteer PO #](../media/content-understanding/po.png)</br> 

3. <span data-ttu-id="ce6db-p109">Als een veld niet door de analyse is gedetecteerd, kunt u het nog steeds toevoegen. Markeer de gegevens die u wilt ophalen en typ in het naamvak de gewenste naam. Schakel het selectievakje in. U moet niet-gedetecteerde velden in de resterende voorbeeldbestanden bevestigen.</span><span class="sxs-lookup"><span data-stu-id="ce6db-p109">If a field was not detected by analysis, you can still choose to add it. Highlight the information you want to extract, and in the name box type in the name you want. Then select the check box. Note that you need to confirm undetected fields in your remaining sample files.</span></span>

4. <span data-ttu-id="ce6db-156">Klik op **Velden bevestigen** nadat je de velden hebt geselecteerd die je wilt opslaan.</span><span class="sxs-lookup"><span data-stu-id="ce6db-156">Click **Confirm fields** after you have selected the fields that you want to save.</span></span> </br>
 
    ![Velden bevestigen na selectie van velden](../media/content-understanding/confirm-fields.png)</br> 
 
5. <span data-ttu-id="ce6db-p110">Selecteer op de **De formuliervelden die u wilt opslaan** pagina, hier wordt het aantal velden weergegeven dat u hebt geselecteerd. Selecteer **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="ce6db-p110">On the **Select the form fields you want to save** page, it shows the number of fields you have selected. Select **Done**.</span></span>

## <a name="step-4-train-and-test-your-model"></a><span data-ttu-id="ce6db-160">Stap 4: Uw model trainen en testen</span><span class="sxs-lookup"><span data-stu-id="ce6db-160">Step 4: Train and test your model</span></span>

<span data-ttu-id="ce6db-161">Nadat je de velden hebt geselecteerd die je wilt opslaan, kun je op de pagina **Model Samenvatting** het model trainen en testen.</span><span class="sxs-lookup"><span data-stu-id="ce6db-161">After selecting the fields you want to save, the **Model Summary** page lets you train and test your model.</span></span>

1. <span data-ttu-id="ce6db-p111">Op de pagina **Model Samenvatting** worden de opgeslagen velden weergegeven in de sectie **Geselecteerde velden**. Selecteer **Trainen** om te beginnen met de training op uw voorbeeldbestanden. Het kan enkele minuten duren voordat dit is voltooid.</span><span class="sxs-lookup"><span data-stu-id="ce6db-p111">On the **Model Summary** page, the saved fields will show in the **Selected fields** section. Select **Train** to begin training on your example files. Note that this may take a few minutes to complete.</span></span></br>

     ![Velden trainen selecteren](../media/content-understanding/select-fields-train.png)</br> 

2. <span data-ttu-id="ce6db-166">Wanneer je het bericht ziet dat de training is voltooid, selecteer je **Naar detailspagina gaan**.</span><span class="sxs-lookup"><span data-stu-id="ce6db-166">When you see the notification that training has completed, select **Go to details page**.</span></span> 

3. <span data-ttu-id="ce6db-p112">Op de pagina **Modeldetails** kunt u testen hoe uw model werkt door **Snelle Test** te selecteren. Hiermee kunt u bestanden slepen naar en neerzetten op de pagina en nagaan of de velden worden gevonden.</span><span class="sxs-lookup"><span data-stu-id="ce6db-p112">On the **Model details** page, you can choose to test how your model works by selecting **Quick test**. This lets you drag and drop files to the page and see if the fields are detected.</span></span>

    ![Velden bevestigen](../media/content-understanding/select-fields-train.png)</br> 

2. <span data-ttu-id="ce6db-170">Wanneer je het bericht ziet dat de training is voltooid, selecteer je **Naar detailspagina gaan**.</span><span class="sxs-lookup"><span data-stu-id="ce6db-170">When you see the notification that training has completed, select **Go to details page**.</span></span> 

3. <span data-ttu-id="ce6db-p113">Op de pagina **Modeldetails** kunt u testen hoe uw model werkt door **Snelle test** te selecteren. Hiermee kunt u bestanden slepen naar en neerzetten op de pagina en nagaan of de velden worden gevonden.</span><span class="sxs-lookup"><span data-stu-id="ce6db-p113">On the **Model details** page, choose to test how your model works by selecting **Quick test**. This lets you drag and drop files to the page and see if the fields are detected.</span></span>

## <a name="step-5-publish-your-model"></a><span data-ttu-id="ce6db-173">Stap 5: Uw model publiceren</span><span class="sxs-lookup"><span data-stu-id="ce6db-173">Step 5: Publish your model</span></span>

1. <span data-ttu-id="ce6db-174">Als u tevreden bent over de resultaten van je model, selecteert u **Publiceren** om het beschikbaar te maken voor gebruik.</span><span class="sxs-lookup"><span data-stu-id="ce6db-174">If you are satisfied with the results of your model, select **Publish** to make it available for use.</span></span>

2. <span data-ttu-id="ce6db-p114">Nadat het model is gepubliceerd, selecteert u **Model gebruiken**. Hiermee maakt u een PowerAutomate-stroom die kan worden uitgevoerd in uw SharePoint-documentbibliotheek, waarna de velden worden geëxtraheerd die in het model zijn geïdentificeerd, selecteer vervolgens **Stroom maken**.</span><span class="sxs-lookup"><span data-stu-id="ce6db-p114">After the model is published, select **Use model**. This creates a PowerAutomate flow that can run in your SharePoint document library and extracts the fields that have been identified in the model, then select **Create Flow**.</span></span>
  
3. <span data-ttu-id="ce6db-177">Wanneer u klaar bent, ziet u het bericht **Uw stroom is succesvol gemaakt**.</span><span class="sxs-lookup"><span data-stu-id="ce6db-177">When completed, you will see the message **Your flow has been successfully created**.</span></span>
 
## <a name="step-6-use-your-model"></a><span data-ttu-id="ce6db-178">Stap 6: uw model gebruiken</span><span class="sxs-lookup"><span data-stu-id="ce6db-178">Step 6: Use your model</span></span>

<span data-ttu-id="ce6db-179">Na het publiceren van je model en het maken van de PowerAutomate-stroom, kun je je model gebruiken in je SharePoint-documentbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="ce6db-179">After publishing your model and creating it's PowerAutomate flow, you can use your model in your SharePoint document library.</span></span>

1. <span data-ttu-id="ce6db-180">Na het publiceren van je model selecteer je **Ga naar SharePoint** om naar de documentbibliotheek te gaan.</span><span class="sxs-lookup"><span data-stu-id="ce6db-180">After publishing your model, select **Go to SharePoint** to go to your document library.</span></span>

2. <span data-ttu-id="ce6db-181">Je ziet dat de velden die je hebt geselecteerd nu als kolommen worden weergegeven in de documentbibliotheek model.</span><span class="sxs-lookup"><span data-stu-id="ce6db-181">In the document library model view, notice that the fields you selected now display as columns.</span></span></br>

    ![Document bibliotheekmodel toegepast](../media/content-understanding/doc-lib-view.png)</br> 

3. <span data-ttu-id="ce6db-183">Zoals je ziet, zie je in de koppelingsinformatie naast **Documenten** notities die op deze documentbibliotheek worden toegepast.</span><span class="sxs-lookup"><span data-stu-id="ce6db-183">Notice that the information link next to **Documents** notes that a forms processing model is applied to this document library.</span></span>

    ![Knop Info](../media/content-understanding/info-button.png)</br>  

4. <span data-ttu-id="ce6db-p115">Upload bestanden in uw documentbibliotheek. Alle bestanden die door het model worden geïdentificeerd, worden weergegeven in de lijst met de bestanden in de weergave en de geëxtraheerde gegevens worden weergegeven in de kolommen.</span><span class="sxs-lookup"><span data-stu-id="ce6db-p115">Upload files to your document library. Any files that the model identifies as it's content type lists the files in your view and displays the extracted data in the columns.</span></span></br>

    ![Gereed](../media/content-understanding/doc-lib-done.png)</br>  

## <a name="see-also"></a><span data-ttu-id="ce6db-188">Zie ook</span><span class="sxs-lookup"><span data-stu-id="ce6db-188">See Also</span></span>
  
[<span data-ttu-id="ce6db-189">Power Automate-documentatie</span><span class="sxs-lookup"><span data-stu-id="ce6db-189">Power Automate documentation</span></span>](https://docs.microsoft.com/power-automate/)

[<span data-ttu-id="ce6db-190">Training: zakelijke prestaties verbeteren met AI-Builder</span><span class="sxs-lookup"><span data-stu-id="ce6db-190">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)
