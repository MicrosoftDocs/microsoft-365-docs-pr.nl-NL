---
title: Een classificatie maken (preview)
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
description: Leer hoe u een classificatie maakt
ms.openlocfilehash: 718d904ca397d43644c578ff6f589b5e5b043e5a
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950154"
---
# <a name="create-a-classifier-preview"></a><span data-ttu-id="076d4-103">Een classificatie maken (preview)</span><span class="sxs-lookup"><span data-stu-id="076d4-103">Create a classifier (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="076d4-104">De inhoud in dit artikel is bedoeld voor project cortex private preview.</span><span class="sxs-lookup"><span data-stu-id="076d4-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="076d4-105">[Lees meer over project cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="076d4-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL0R]  

</br>

<span data-ttu-id="076d4-106">Een classificatie is een type model waarmee identificatie en classificatie van een documenttype worden geautomatiseerd.</span><span class="sxs-lookup"><span data-stu-id="076d4-106">A classifier is a type of model that automates identification and classification of a document type.</span></span> <span data-ttu-id="076d4-107">U kunt bijvoorbeeld alle documenten voor het verlengen van een *contract* identificeren die zijn toegevoegd aan de documentbibliotheek, zoals hieronder beschreven.</span><span class="sxs-lookup"><span data-stu-id="076d4-107">For example, you may want to identify all *Contract Renewal* documents that are added to your document library, such as the following.</span></span>

![Document voor vernieuwing van contract](../media/content-understanding/contract-renewal.png)

<span data-ttu-id="076d4-109">Als u een classificatie maakt, wordt een nieuw [SharePoint-inhouds type](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) gemaakt dat aan het model wordt gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="076d4-109">Creating a classifier will create a new [SharePoint Content Type](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) that will be associated to the model.</span></span>

<span data-ttu-id="076d4-110">Wanneer u de classificatie maakt, moet u *uitleg* maken waarmee u het model kunt definiëren door veelvoorkomende gegevens te laten opvallen die u op een consistente manier voor dit documenttype wilt vinden.</span><span class="sxs-lookup"><span data-stu-id="076d4-110">When creating the classifier, you need to create *explanations* that help to define the model by noting common data that you would expect to find consistently for this document type.</span></span> 

<span data-ttu-id="076d4-111">U gebruikt voorbeelden van het documenttype (' voorbeelden van bestanden ') om het model ' Train ' om te helpen met het identificeren van bestanden met hetzelfde inhoudstype.</span><span class="sxs-lookup"><span data-stu-id="076d4-111">You use examples of the document type ("example files") to help "train" your model to identify files that have the same content type.</span></span>

<span data-ttu-id="076d4-112">Als u een classificatie wilt maken, moet u het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="076d4-112">To create a classifier, you need to:</span></span>
1. <span data-ttu-id="076d4-113">De naam van uw model wijzigen</span><span class="sxs-lookup"><span data-stu-id="076d4-113">Name your model</span></span>
2. <span data-ttu-id="076d4-114">Voorbeeldbestanden toevoegen</span><span class="sxs-lookup"><span data-stu-id="076d4-114">Add your example files</span></span>
3. <span data-ttu-id="076d4-115">Een label opgeven voor voorbeeldbestanden</span><span class="sxs-lookup"><span data-stu-id="076d4-115">Label your example files</span></span>
4. <span data-ttu-id="076d4-116">Een uitleg maken</span><span class="sxs-lookup"><span data-stu-id="076d4-116">Create an explanation</span></span>
5. <span data-ttu-id="076d4-117">Uw model testen</span><span class="sxs-lookup"><span data-stu-id="076d4-117">Test your model</span></span> 

> [!Note]
> <span data-ttu-id="076d4-118">Hoewel een classificatie wordt gebruikt door uw model voor het identificeren en classificeren van documenttypen, kunt u er ook voor kiezen bepaalde gegevens uit te trekken van elk bestand dat door het model wordt geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="076d4-118">While a classifier is used by your model to identify and classify document types, you can also choose to pull specific pieces of information from each file identified by the model.</span></span> <span data-ttu-id="076d4-119">U doet dit door een **Extractor** te maken om aan uw model toe te voegen, en wordt beschreven in [een extractor maken](create-an-extractor.md).</span><span class="sxs-lookup"><span data-stu-id="076d4-119">You do this by creating an **extractor** to add to your model, and this is described in [Create an extractor](create-an-extractor.md).</span></span>

## <a name="name-your-model"></a><span data-ttu-id="076d4-120">De naam van uw model wijzigen</span><span class="sxs-lookup"><span data-stu-id="076d4-120">Name your model</span></span>

<span data-ttu-id="076d4-121">De eerste stap bestaat uit het maken van een model in uw inhouds centrum door het een naam te geven:</span><span class="sxs-lookup"><span data-stu-id="076d4-121">The first step is to create your model in your Content Center by giving it a name:</span></span>

1. <span data-ttu-id="076d4-122">Klik in uw inhouds centrum op **Nieuw**en klik vervolgens op **een model maken**.</span><span class="sxs-lookup"><span data-stu-id="076d4-122">In your Content Center, click **New**, and then click **Create a model**.</span></span>
2. <span data-ttu-id="076d4-123">Typ in het vak Naam van **Nieuw document** in het veld **naam** de naam van het model.</span><span class="sxs-lookup"><span data-stu-id="076d4-123">In the **New document understanding model** pane, in the **Name** field, type the name of the model.</span></span> <span data-ttu-id="076d4-124">Voor ons voorbeeld, als we documenten verlengen, kunnen we de verlenging van dit model in de naam van het *contract*aangeven.</span><span class="sxs-lookup"><span data-stu-id="076d4-124">For our example, if we want to identify contract renewal documents, we might name this model *Contract Renewal*.</span></span>
3. <span data-ttu-id="076d4-125">Klik op **Maken**.</span><span class="sxs-lookup"><span data-stu-id="076d4-125">Click **Create**.</span></span> <span data-ttu-id="076d4-126">Vervolgens maakt u een startpagina voor het model.</span><span class="sxs-lookup"><span data-stu-id="076d4-126">This will create a home page for the model.</span></span></br>

    ![Startpagina van het classificatiemodel](../media/content-understanding/model-home.png)

<span data-ttu-id="076d4-128">Wanneer u een model maakt, maakt u een nieuw SharePoint-inhoudstype.</span><span class="sxs-lookup"><span data-stu-id="076d4-128">When you create a model, you are creating a new SharePoint content type.</span></span> <span data-ttu-id="076d4-129">Een SharePoint-inhoudstype vertegenwoordigt een categorie documenten met gemeenschappelijke kenmerken en deel een verzameling kolommen of metagegevenseigenschappen voor die specifieke inhoud.</span><span class="sxs-lookup"><span data-stu-id="076d4-129">A SharePoint content type represents a category of documents that have common characteristics and share a collection of columns or metadata properties for that particular content.</span></span> <span data-ttu-id="076d4-130">SharePoint-inhoudstypen worden beheerd via de [Galerie met inhoudstypen]().</span><span class="sxs-lookup"><span data-stu-id="076d4-130">SharePoint Content Types are managed through the [Content types gallery]().</span></span> <span data-ttu-id="076d4-131">Voor ons voorbeeld, wanneer we het model maken, maken we een nieuw inhoudstype voor het verlengen van een *contract* .</span><span class="sxs-lookup"><span data-stu-id="076d4-131">For our example, when we create the model, we will be creating a new *Contract Renewal* content type.</span></span>

<span data-ttu-id="076d4-132">Selecteer **Geavanceerde instellingen** als u dit model wilt toewijzen aan een bestaand inhoudstype in de galerie SharePoint-inhoudstypen om het schema te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="076d4-132">Select **Advanced settings** if you want to map this model to an existing content type in the SharePoint Content types gallery to use its schema.</span></span> <span data-ttu-id="076d4-133">Houd er rekening mee dat u met een bestaand inhoudstype het schema van het schema kunt gebruiken voor het identificeren en classificeren van een bestaand inhoudstype dat u het model nog moet trainen om informatie op te halen uit de bestanden die wordt geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="076d4-133">Note that while you can use an existing content type to leverage its schema to help with identification and classification, you will still need to train your model to extract information from files it identifies.</span></span></br>

![Geavanceerde instellingen](../media/content-understanding/advanced-settings.png)

## <a name="add-your-example-files"></a><span data-ttu-id="076d4-135">Voorbeeldbestanden toevoegen</span><span class="sxs-lookup"><span data-stu-id="076d4-135">Add your example files</span></span>

<span data-ttu-id="076d4-136">Op de startpagina van het model kunt u voorbeelden van bestanden toevoegen die u nodig hebt om het model te leren bieden ter identificatie van uw documenttype.</span><span class="sxs-lookup"><span data-stu-id="076d4-136">On the model home page, you can add your examples files you will need to help train the model to identify your document type.</span></span> </br>
</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4D0iX] 

</br>

> [!Note]
> <span data-ttu-id="076d4-137">U moet dezelfde bestanden gebruiken voor de training Classifier en [Extractor](create-an-extractor.md).</span><span class="sxs-lookup"><span data-stu-id="076d4-137">The same files should be used for both classifier and [extractor training](create-an-extractor.md).</span></span> <span data-ttu-id="076d4-138">U kunt altijd later meer toevoegen aan een extra optie, maar meestal moet u een volledige set voorbeeldbestanden toevoegen.</span><span class="sxs-lookup"><span data-stu-id="076d4-138">You always have the option to add more later, but typically you should add a full set of example files.</span></span> <span data-ttu-id="076d4-139">U maakt een etiket voor uw model en test de resterende ongelabelde producten om de geschiktheid van het model te beoordelen.</span><span class="sxs-lookup"><span data-stu-id="076d4-139">You will label some to train your model, and test the remaining unlabeled ones to evaluate model fitness.</span></span> 

<span data-ttu-id="076d4-140">Voor de Trainingsset wilt u met beide positieve voorbeelden en de negatieve voorbeelden het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="076d4-140">For your training set, you will want to use both positive examples, and negative examples:</span></span>
- <span data-ttu-id="076d4-141">Positief voorbeeld: documenten die het documenttype aangeven.</span><span class="sxs-lookup"><span data-stu-id="076d4-141">Positive example: Documents that represent the document type.</span></span> <span data-ttu-id="076d4-142">De persoon bevat tekenreeksen en informatie over dit type document.</span><span class="sxs-lookup"><span data-stu-id="076d4-142">They contain strings and information that would always be in this type of document.</span></span>
- <span data-ttu-id="076d4-143">Negatief voorbeeld: documenten die niet het documenttype vertegenwoordigen.</span><span class="sxs-lookup"><span data-stu-id="076d4-143">Negative example: Documents that do not represent the document type.</span></span>  <span data-ttu-id="076d4-144">Er ontbreken tekenreeksen en informatie die in dit type document moeten worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="076d4-144">They are missing strings and information that needs to be present in this type of document.</span></span>

<span data-ttu-id="076d4-145">U wilt minimaal vijf positieve voorbeelden en één negatief voorbeeld gebruiken om het model te leren bieden.</span><span class="sxs-lookup"><span data-stu-id="076d4-145">You will want to use at least five positive examples and one negative examples to train your model.</span></span>  <span data-ttu-id="076d4-146">U wilt nog meer vragen om uw model te testen na de training.</span><span class="sxs-lookup"><span data-stu-id="076d4-146">You will want to have additional ones to test your model after training.</span></span>

<span data-ttu-id="076d4-147">Voorbeeldbestanden toevoegen:</span><span class="sxs-lookup"><span data-stu-id="076d4-147">To add sample files:</span></span>

1. <span data-ttu-id="076d4-148">Klik op de startpagina van het model op de tegel **voorbeeld bibliotheek opbouwen** op **bestanden toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="076d4-148">On the model home page, in the **Build sample library** tile, click **Add files**.</span></span>
2. <span data-ttu-id="076d4-149">Selecteer op de pagina **voorbeeldbestanden voor uw model selecteren** de voorbeeldbestanden uit de voorbeeldbestanden bibliotheek in het inhouds centrum.</span><span class="sxs-lookup"><span data-stu-id="076d4-149">On the **Select sample files for your model** page, select your example files from the Sample files library in the Content Center.</span></span> <span data-ttu-id="076d4-150">Als u deze niet al had geüpload, kunt u ervoor kiezen om ze nu te uploaden door te klikken op **uploaden** om de bestanden te verplaatsen.</span><span class="sxs-lookup"><span data-stu-id="076d4-150">If you had not already uploaded them there, you can choose to upload them now by clicking **Upload** to move them the Sample file library.</span></span>
3. <span data-ttu-id="076d4-151">Selecteer **toevoegen**nadat u de voorbeeldbestanden hebt geselecteerd die u wilt gebruiken voor het trainen van het model.</span><span class="sxs-lookup"><span data-stu-id="076d4-151">After selecting your example files to use to train the model, click **Add**.</span></span>

    ![Voorbeeldbestanden selecteren](../media/content-understanding/select-sample.png) 

## <a name="label-your-example-files"></a><span data-ttu-id="076d4-153">Een label opgeven voor voorbeeldbestanden</span><span class="sxs-lookup"><span data-stu-id="076d4-153">Label your example files</span></span>

<span data-ttu-id="076d4-154">Wanneer u voorbeeldbestanden hebt toegevoegd, moet u deze als een positief voorbeeld of met een negatief voorbeeld markeren.</span><span class="sxs-lookup"><span data-stu-id="076d4-154">After adding your example files, you then need to label them as either positive examples or negative examples.</span></span>

1. <span data-ttu-id="076d4-155">Klik op de startpagina van het model op de tegel **bestanden classificeren en training uitvoeren** op **classificatie voor trainer**.</span><span class="sxs-lookup"><span data-stu-id="076d4-155">On the model home page, on the **Classify files and run training** tile, click **Train Classifier**.</span></span>
   <span data-ttu-id="076d4-156">Hiermee wordt de etiket pagina weergegeven met een overzicht van de voorbeeldbestanden, waarbij het eerste bestand zichtbaar is in de viewer.</span><span class="sxs-lookup"><span data-stu-id="076d4-156">This will display the label page that shows a listing of your example files, with the first file visible in the viewer.</span></span>
2. <span data-ttu-id="076d4-157">In de viewer, boven aan het eerste voorbeeldbestand, ziet u tekst met de vraag of het bestand een voorbeeld is van het model dat u zojuist hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="076d4-157">In the viewer, on the top of the first example file, you will see text asking you if the file is an example of the model you just created.</span></span> <span data-ttu-id="076d4-158">Als het om een positief voorbeeld gaat, selecteert u **Ja**.</span><span class="sxs-lookup"><span data-stu-id="076d4-158">If it is a positive example, select **Yes**.</span></span> <span data-ttu-id="076d4-159">Als het om een negatief voorbeeld gaat, selecteert u **Nee**.</span><span class="sxs-lookup"><span data-stu-id="076d4-159">If it is a negative example, select **No**.</span></span>
3. <span data-ttu-id="076d4-160">Selecteer in de lijst met **gelabelde voorbeelden** aan de linkerkant extra bestanden die u als voorbeeld wilt gebruiken, en voorzie ze ook van een etiket.</span><span class="sxs-lookup"><span data-stu-id="076d4-160">From the **Labeled examples** list on the left, select additional files that you want to use as examples, and label them as well.</span></span> 

    ![Startpagina van het classificatiemodel](../media/content-understanding/classifier-home-page.png) 


> [!Note]
> <span data-ttu-id="076d4-162">Etiketten van minimaal vijf positieve voorbeelden en een negatief voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="076d4-162">Label at least five positive examples, and one negative example.</span></span> 

## <a name="create-an-explanation"></a><span data-ttu-id="076d4-163">Een uitleg maken</span><span class="sxs-lookup"><span data-stu-id="076d4-163">Create an explanation</span></span>

<span data-ttu-id="076d4-164">De volgende stap is het maken van een uitleg op de pagina Train.</span><span class="sxs-lookup"><span data-stu-id="076d4-164">The next step is to create an explanation on the Train page.</span></span>  <span data-ttu-id="076d4-165">Een uitleg is een tip of aanwijzingen om het model te leren kennen hoe u dit document kunt herkennen.</span><span class="sxs-lookup"><span data-stu-id="076d4-165">An explanation is a hint or clue to help the model understand how to recognize this document.</span></span> <span data-ttu-id="076d4-166">Onze documenten voor het verlengen van een contract bevatten bijvoorbeeld altijd een *aanvraag voor aanvullende informatie over de verschaffings* tekst.</span><span class="sxs-lookup"><span data-stu-id="076d4-166">For example, our Contract Renewal documents always contain a *Request for additional disclosure* text string.</span></span>

> [!Note]
> <span data-ttu-id="076d4-167">Wanneer u deze gebruikt met uitpaknen, wordt een uitleg gebruikt om de tekenreeks te identificeren die u uit het document wilt extraheren.</span><span class="sxs-lookup"><span data-stu-id="076d4-167">When used with extractors, an explanation is use to identify the string that you want to extract from the document.</span></span> 

<span data-ttu-id="076d4-168">Een uitleg maken:</span><span class="sxs-lookup"><span data-stu-id="076d4-168">To create an explanation:</span></span>

1. <span data-ttu-id="076d4-169">Ga naar de startpagina van het model en klik op het tabblad **trein** om naar de pagina Train te gaan.</span><span class="sxs-lookup"><span data-stu-id="076d4-169">On the model home page, click the **Train** tab to go to the Train page.</span></span>
2. <span data-ttu-id="076d4-170">Op de pagina Train in de sectie met **begeleide bestanden** ziet u een lijst met de voorbeeldbestanden die u eerder hebt gelabeld.</span><span class="sxs-lookup"><span data-stu-id="076d4-170">On the Train page, in the **Trained files** section, you will see a list of the example files that you had labeled previously.</span></span> <span data-ttu-id="076d4-171">Selecteer een van uw positieve bestanden in de lijst en wordt weergegeven in de viewer.</span><span class="sxs-lookup"><span data-stu-id="076d4-171">Select one of your positive files from the list, and it will display in the viewer.</span></span>
3. <span data-ttu-id="076d4-172">Klik in de sectie uitleg op **Nieuw**en klik vervolgens op **leeg**.</span><span class="sxs-lookup"><span data-stu-id="076d4-172">In the Explanation section, click **New**, then click **Blank**.</span></span>
4. <span data-ttu-id="076d4-173">Op de pagina **een uitleg maken** :</span><span class="sxs-lookup"><span data-stu-id="076d4-173">On the **Create an explanation** page:</span></span></br>
    <span data-ttu-id="076d4-174">a.</span><span class="sxs-lookup"><span data-stu-id="076d4-174">a.</span></span> <span data-ttu-id="076d4-175">Typ de **naam** (bijvoorbeeld ' uitschaffings blok ').</span><span class="sxs-lookup"><span data-stu-id="076d4-175">Type the **Name** (for example, "Disclosure Block").</span></span></br>
    <span data-ttu-id="076d4-176">b.</span><span class="sxs-lookup"><span data-stu-id="076d4-176">b.</span></span> <span data-ttu-id="076d4-177">Selecteer het **type**.</span><span class="sxs-lookup"><span data-stu-id="076d4-177">Select the **Type**.</span></span> <span data-ttu-id="076d4-178">Voor ons voorbeeld selecteren we een **lijst met zinnen**, aangezien we een tekenreeks toevoegen.</span><span class="sxs-lookup"><span data-stu-id="076d4-178">For our example, we'll select **Phrase list**, since we are adding a text string.</span></span></br>
    <span data-ttu-id="076d4-179">c.</span><span class="sxs-lookup"><span data-stu-id="076d4-179">c.</span></span> <span data-ttu-id="076d4-180">Typ in het vak **Typ hier** de tekenreeks.</span><span class="sxs-lookup"><span data-stu-id="076d4-180">In the **Type here** box, type the string.</span></span>  <span data-ttu-id="076d4-181">Voor ons voorbeeld voegen we "aanvraag voor aanvullende informatie" toe.</span><span class="sxs-lookup"><span data-stu-id="076d4-181">For our example, we'll add "Request for additional disclosure".</span></span> <span data-ttu-id="076d4-182">U kunt onderscheid maken tussen **hoofd** letters en kleine letters in de tekenreeks.</span><span class="sxs-lookup"><span data-stu-id="076d4-182">You can select **Case sensitive** if the string needs to be case sensitive.</span></span></br>
    <span data-ttu-id="076d4-183">d.</span><span class="sxs-lookup"><span data-stu-id="076d4-183">d.</span></span> <span data-ttu-id="076d4-184">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="076d4-184">Click **Save**.</span></span>

    ![Uitleg maken](../media/content-understanding/explanation.png) 
    
 
5.  <span data-ttu-id="076d4-186">In het model wordt nu gecontroleerd of de door u gemaakte uitleg goed genoeg is om uw resterende gelabelde voorbeeldbestanden correct te identificeren als positieve en negatieve voorbeelden.</span><span class="sxs-lookup"><span data-stu-id="076d4-186">The model will now check to see if the explanation you created was good enough to identify your remaining labeled example files correctly as positive and negative examples.</span></span> <span data-ttu-id="076d4-187">Selecteer in de sectie met begeleide bestanden de kolom **evaluatie** nadat de training is voltooid om de resultaten te bekijken.</span><span class="sxs-lookup"><span data-stu-id="076d4-187">In Trained Files section, check the **Evaluation** column after the training has completed to see the results.</span></span>  <span data-ttu-id="076d4-188">De bestanden geven de **overeenkomende** waarde weer als de door u gemaakte uitleg voldoende is voor de naam van het bestand dat u als (positief of negatief) hebt opgegeven.</span><span class="sxs-lookup"><span data-stu-id="076d4-188">The files will show a value of **Match** if the explanation you created was enough to match what you had labeled them as (positive or negative).</span></span>

    ![Uitleg maken](../media/content-understanding/match.png) 

<span data-ttu-id="076d4-190">Als u een **niet-overeenkomend** bestand met gelabelde bestanden ontvangt, moet u mogelijk een extra uitleg maken om het model meer informatie te verschaffen ter identificatie van het documenttype.</span><span class="sxs-lookup"><span data-stu-id="076d4-190">If you receive a **Mismatch** on your labeled files, you may need to create an additional explanation to provide the model more information to identify the document type.</span></span> <span data-ttu-id="076d4-191">U kunt op het bestand klikken voor meer informatie over waarom de niet-overeenkomende fout is opgetreden.</span><span class="sxs-lookup"><span data-stu-id="076d4-191">You can click on the file to get more information about why the mismatch occurred.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="076d4-192">Uw model testen</span><span class="sxs-lookup"><span data-stu-id="076d4-192">Test your model</span></span>

<span data-ttu-id="076d4-193">Als u een overeenkomst met de gelabelde voorbeeldbestanden hebt ontvangen, kunt u de naam van uw model testen in de resterende voorbeeldbestanden met bijschriften.</span><span class="sxs-lookup"><span data-stu-id="076d4-193">If you received a match on your labeled example files, you can now test your model on your remaining unlabeled example files.</span></span>

1. <span data-ttu-id="076d4-194">Klik op de startpagina van het model op het tabblad **testen** .  Het model wordt uitgevoerd in uw niet-gelabelde voorbeeldbestanden.</span><span class="sxs-lookup"><span data-stu-id="076d4-194">On the model home page, click the **Test** tab.  This will run the model on your unlabeled example files.</span></span>
2. <span data-ttu-id="076d4-195">In de lijst **bestanden testen** worden de voorbeeldbestanden weergegeven en wordt weergegeven als een voorbeeld van het model wordt voorspeld voor een positief of negatief voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="076d4-195">In the **Test files** list, your example files will display and will show if the model predicted them to be positive or negative examples.</span></span> <span data-ttu-id="076d4-196">U kunt deze gegevens gebruiken om de effectiviteit van uw classificatie voor het identificeren van uw documenten te bepalen.</span><span class="sxs-lookup"><span data-stu-id="076d4-196">You can use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![Test van bestanden zonder label](../media/content-understanding/test-on-files.png) 



## <a name="see-also"></a><span data-ttu-id="076d4-198">Zie ook</span><span class="sxs-lookup"><span data-stu-id="076d4-198">See Also</span></span>
[<span data-ttu-id="076d4-199">Een extractor maken</span><span class="sxs-lookup"><span data-stu-id="076d4-199">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="076d4-200">Overzicht van document</span><span class="sxs-lookup"><span data-stu-id="076d4-200">Document Understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="076d4-201">Een formulier verwerkings model maken</span><span class="sxs-lookup"><span data-stu-id="076d4-201">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>
[<span data-ttu-id="076d4-202">Een model toepassen</span><span class="sxs-lookup"><span data-stu-id="076d4-202">Apply a model</span></span>](apply-a-model.md) 




