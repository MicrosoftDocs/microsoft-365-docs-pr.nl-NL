---
title: Een classificatie maken (Voorbeeld)
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
description: Meer informatie over het maken van een classificatie
ms.openlocfilehash: 029ac16310f8e95a69a713896b1109a778eb3b8d
ms.sourcegitcommit: ea5e2f85bd6b609658545b120c7e08789b9686fd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/01/2020
ms.locfileid: "46537222"
---
# <a name="create-a-classifier-preview"></a><span data-ttu-id="59b71-103">Een classificatie maken (Voorbeeld)</span><span class="sxs-lookup"><span data-stu-id="59b71-103">Create a classifier (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="59b71-104">De inhoud in dit artikel is voor Project Cortex Private Preview.</span><span class="sxs-lookup"><span data-stu-id="59b71-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="59b71-105">[Lees meer over Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="59b71-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL0R]  

</br>

<span data-ttu-id="59b71-106">Een classificatie is een type model dat de identificatie en classificatie van een documenttype automatiseert.</span><span class="sxs-lookup"><span data-stu-id="59b71-106">A classifier is a type of model that automates identification and classification of a document type.</span></span> <span data-ttu-id="59b71-107">U bijvoorbeeld alle *contractverlengingsdocumenten* identificeren die aan uw documentbibliotheek zijn toegevoegd, zoals het volgende.</span><span class="sxs-lookup"><span data-stu-id="59b71-107">For example, you may want to identify all *Contract Renewal* documents that are added to your document library, such as the following.</span></span>

![Document contractverlenging](../media/content-understanding/contract-renewal.png)

<span data-ttu-id="59b71-109">Als u een classificatie maakt, wordt een nieuw [SharePoint-inhoudstype](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) gemaakt dat aan het model is gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="59b71-109">Creating a classifier will create a new [SharePoint Content Type](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) that will be associated to the model.</span></span>

<span data-ttu-id="59b71-110">Wanneer u de classificatie maakt, moet u *uitleg* maken die helpt bij het definiëren van het model door algemene gegevens op te merken die u consistent zou verwachten voor dit documenttype.</span><span class="sxs-lookup"><span data-stu-id="59b71-110">When creating the classifier, you need to create *explanations* that help to define the model by noting common data that you would expect to find consistently for this document type.</span></span> 

<span data-ttu-id="59b71-111">U gebruikt voorbeelden van het documenttype ('voorbeeldbestanden') om uw model te helpen 'trainen' om bestanden te identificeren die hetzelfde inhoudstype hebben.</span><span class="sxs-lookup"><span data-stu-id="59b71-111">You use examples of the document type ("example files") to help "train" your model to identify files that have the same content type.</span></span>

<span data-ttu-id="59b71-112">Als u een classificatie wilt maken, moet u het:</span><span class="sxs-lookup"><span data-stu-id="59b71-112">To create a classifier, you need to:</span></span>
1. <span data-ttu-id="59b71-113">Geef uw model een naam</span><span class="sxs-lookup"><span data-stu-id="59b71-113">Name your model</span></span>
2. <span data-ttu-id="59b71-114">Uw voorbeeldbestanden toevoegen</span><span class="sxs-lookup"><span data-stu-id="59b71-114">Add your example files</span></span>
3. <span data-ttu-id="59b71-115">Uw voorbeeldbestanden labelen</span><span class="sxs-lookup"><span data-stu-id="59b71-115">Label your example files</span></span>
4. <span data-ttu-id="59b71-116">Een uitleg maken</span><span class="sxs-lookup"><span data-stu-id="59b71-116">Create an explanation</span></span>
5. <span data-ttu-id="59b71-117">Test uw model</span><span class="sxs-lookup"><span data-stu-id="59b71-117">Test your model</span></span> 

> [!Note]
> <span data-ttu-id="59b71-118">Hoewel een classificatie door uw model wordt gebruikt om documenttypen te identificeren en te classificeren, u er ook voor kiezen om specifieke stukjes informatie uit elk bestand te halen dat door het model wordt geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="59b71-118">While a classifier is used by your model to identify and classify document types, you can also choose to pull specific pieces of information from each file identified by the model.</span></span> <span data-ttu-id="59b71-119">U doet dit door een **afzuigkap** te maken om aan uw model toe te voegen, en dit wordt beschreven in [Een afzuigkap maken.](create-an-extractor.md)</span><span class="sxs-lookup"><span data-stu-id="59b71-119">You do this by creating an **extractor** to add to your model, and this is described in [Create an extractor](create-an-extractor.md).</span></span>

## <a name="name-your-model"></a><span data-ttu-id="59b71-120">Geef uw model een naam</span><span class="sxs-lookup"><span data-stu-id="59b71-120">Name your model</span></span>

<span data-ttu-id="59b71-121">De eerste stap is om uw model te maken in uw Content Center door het een naam te geven:</span><span class="sxs-lookup"><span data-stu-id="59b71-121">The first step is to create your model in your Content Center by giving it a name:</span></span>

1. <span data-ttu-id="59b71-122">Klik in het Inhoudscentrum op **Nieuw**en klik vervolgens op **Een model maken**.</span><span class="sxs-lookup"><span data-stu-id="59b71-122">In your Content Center, click **New**, and then click **Create a model**.</span></span>
2. <span data-ttu-id="59b71-123">Typ in het **modelvenster Nieuw documentbegrip** in het veld **Naam** de naam van het model.</span><span class="sxs-lookup"><span data-stu-id="59b71-123">In the **New document understanding model** pane, in the **Name** field, type the name of the model.</span></span> <span data-ttu-id="59b71-124">Als we bijvoorbeeld contractverlengingsdocumenten willen identificeren, kunnen we dit model *contractverlenging een naam geven.*</span><span class="sxs-lookup"><span data-stu-id="59b71-124">For our example, if we want to identify contract renewal documents, we might name this model *Contract Renewal*.</span></span>
3. <span data-ttu-id="59b71-125">Klik op **Maken**.</span><span class="sxs-lookup"><span data-stu-id="59b71-125">Click **Create**.</span></span> <span data-ttu-id="59b71-126">Hiermee wordt een startpagina voor het model gemaakt.</span><span class="sxs-lookup"><span data-stu-id="59b71-126">This will create a home page for the model.</span></span></br>

    ![Startpagina classificatiemodel](../media/content-understanding/model-home.png)

<span data-ttu-id="59b71-128">Wanneer u een model maakt, maakt u een nieuw SharePoint-inhoudstype.</span><span class="sxs-lookup"><span data-stu-id="59b71-128">When you create a model, you are creating a new SharePoint content type.</span></span> <span data-ttu-id="59b71-129">Een SharePoint-inhoudstype vertegenwoordigt een categorie documenten met algemene kenmerken en deelt een verzameling kolommen of metagegevens eigenschappen voor die bepaalde inhoud.</span><span class="sxs-lookup"><span data-stu-id="59b71-129">A SharePoint content type represents a category of documents that have common characteristics and share a collection of columns or metadata properties for that particular content.</span></span> <span data-ttu-id="59b71-130">SharePoint-inhoudstypen worden beheerd via de [galerie Inhoudstypen]().</span><span class="sxs-lookup"><span data-stu-id="59b71-130">SharePoint Content Types are managed through the [Content types gallery]().</span></span> <span data-ttu-id="59b71-131">Wanneer we bijvoorbeeld het model maken, maken we een nieuw *inhoudstype voor contractverlenging.*</span><span class="sxs-lookup"><span data-stu-id="59b71-131">For our example, when we create the model, we will be creating a new *Contract Renewal* content type.</span></span>

<span data-ttu-id="59b71-132">Selecteer **Geavanceerde instellingen** als u dit model wilt toewijzen aan een bestaand inhoudstype in de galerie Met SharePoint-inhoudstypen om het schema te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="59b71-132">Select **Advanced settings** if you want to map this model to an existing content type in the SharePoint Content types gallery to use its schema.</span></span> <span data-ttu-id="59b71-133">Houd er rekening mee dat u weliswaar een bestaand inhoudstype gebruiken om het schema te gebruiken om te helpen bij de identificatie en classificatie, maar dat u uw model nog steeds moet trainen om informatie uit bestanden te extraheren die het identificeert.</span><span class="sxs-lookup"><span data-stu-id="59b71-133">Note that while you can use an existing content type to leverage its schema to help with identification and classification, you will still need to train your model to extract information from files it identifies.</span></span></br>

![Geavanceerde instellingen](../media/content-understanding/advanced-settings.png)

## <a name="add-your-example-files"></a><span data-ttu-id="59b71-135">Uw voorbeeldbestanden toevoegen</span><span class="sxs-lookup"><span data-stu-id="59b71-135">Add your example files</span></span>

<span data-ttu-id="59b71-136">Op de startpagina van het model u uw voorbeeldbestanden toevoegen die u nodig hebt om het model te trainen om uw documenttype te identificeren.</span><span class="sxs-lookup"><span data-stu-id="59b71-136">On the model home page, you can add your examples files you will need to help train the model to identify your document type.</span></span> </br>
</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4D0iX] 

</br>

> [!Note]
> <span data-ttu-id="59b71-137">Dezelfde bestanden moeten worden gebruikt voor zowel classificatie als [afzuigopleiding](create-an-extractor.md).</span><span class="sxs-lookup"><span data-stu-id="59b71-137">The same files should be used for both classifier and [extractor training](create-an-extractor.md).</span></span> <span data-ttu-id="59b71-138">U hebt altijd de optie om later meer toe te voegen, maar meestal moet u een volledige set voorbeeldbestanden toevoegen.</span><span class="sxs-lookup"><span data-stu-id="59b71-138">You always have the option to add more later, but typically you should add a full set of example files.</span></span> <span data-ttu-id="59b71-139">U labelt wat om uw model te trainen en test de resterende niet-gelabelde modellen om de geschiktheid van het model te evalueren.</span><span class="sxs-lookup"><span data-stu-id="59b71-139">You will label some to train your model, and test the remaining unlabeled ones to evaluate model fitness.</span></span> 

<span data-ttu-id="59b71-140">Voor uw trainingsset wilt u zowel positieve als negatieve voorbeelden gebruiken:</span><span class="sxs-lookup"><span data-stu-id="59b71-140">For your training set, you will want to use both positive examples, and negative examples:</span></span>
- <span data-ttu-id="59b71-141">Positief voorbeeld: documenten die het documenttype vertegenwoordigen.</span><span class="sxs-lookup"><span data-stu-id="59b71-141">Positive example: Documents that represent the document type.</span></span> <span data-ttu-id="59b71-142">Ze bevatten tekenreeksen en informatie die altijd in dit type document zou zitten.</span><span class="sxs-lookup"><span data-stu-id="59b71-142">They contain strings and information that would always be in this type of document.</span></span>
- <span data-ttu-id="59b71-143">Negatief voorbeeld: documenten die het documenttype niet vertegenwoordigen.</span><span class="sxs-lookup"><span data-stu-id="59b71-143">Negative example: Documents that do not represent the document type.</span></span>  <span data-ttu-id="59b71-144">Ze missen tekenreeksen en informatie die aanwezig moet zijn in dit type document.</span><span class="sxs-lookup"><span data-stu-id="59b71-144">They are missing strings and information that needs to be present in this type of document.</span></span>

<span data-ttu-id="59b71-145">U zult minstens vijf positieve voorbeelden en één negatieve voorbeelden willen gebruiken om uw model te trainen.</span><span class="sxs-lookup"><span data-stu-id="59b71-145">You will want to use at least five positive examples and one negative examples to train your model.</span></span>  <span data-ttu-id="59b71-146">U zult extra degenen willen hebben om uw model na opleiding te testen.</span><span class="sxs-lookup"><span data-stu-id="59b71-146">You will want to have additional ones to test your model after training.</span></span>

<span data-ttu-id="59b71-147">Ga als voorbeeldbestanden toevoegen:</span><span class="sxs-lookup"><span data-stu-id="59b71-147">To add sample files:</span></span>

1. <span data-ttu-id="59b71-148">Klik op de startpagina van het model in de tegel **Voorbeeldbibliotheek bouwen** op **Bestanden toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="59b71-148">On the model home page, in the **Build sample library** tile, click **Add files**.</span></span>
2. <span data-ttu-id="59b71-149">Selecteer op de **voorbeeldbestanden selecteren voor uw modelpagina** uw voorbeeldbestanden uit de bibliotheek Voorbeeldbestanden in het Inhoudscentrum.</span><span class="sxs-lookup"><span data-stu-id="59b71-149">On the **Select sample files for your model** page, select your example files from the Sample files library in the Content Center.</span></span> <span data-ttu-id="59b71-150">Als je ze daar nog niet hebt geüpload, kun je ervoor kiezen om ze nu te uploaden door op **Uploaden** te klikken om ze de voorbeeldbestandsbibliotheek te verplaatsen.</span><span class="sxs-lookup"><span data-stu-id="59b71-150">If you had not already uploaded them there, you can choose to upload them now by clicking **Upload** to move them the Sample file library.</span></span>
3. <span data-ttu-id="59b71-151">Nadat u uw voorbeeldbestanden hebt geselecteerd die u wilt gebruiken om het model te trainen, klikt u op **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="59b71-151">After selecting your example files to use to train the model, click **Add**.</span></span>

    ![Voorbeeldbestanden selecteren](../media/content-understanding/select-sample.png) 

## <a name="label-your-example-files"></a><span data-ttu-id="59b71-153">Uw voorbeeldbestanden labelen</span><span class="sxs-lookup"><span data-stu-id="59b71-153">Label your example files</span></span>

<span data-ttu-id="59b71-154">Nadat u uw voorbeeldbestanden hebt toegevoegd, moet u ze vervolgens labelen als positieve voorbeelden of negatieve voorbeelden.</span><span class="sxs-lookup"><span data-stu-id="59b71-154">After adding your example files, you then need to label them as either positive examples or negative examples.</span></span>

1. <span data-ttu-id="59b71-155">Klik op de startpagina van het model op de **tegel Bestanden classificeren en trainingsafbeelding uitvoeren** op **Classifier trainen**.</span><span class="sxs-lookup"><span data-stu-id="59b71-155">On the model home page, on the **Classify files and run training** tile, click **Train Classifier**.</span></span>
   <span data-ttu-id="59b71-156">Hiermee wordt de labelpagina weergegeven met een lijst van uw voorbeeldbestanden, waarbij het eerste bestand zichtbaar is in de viewer.</span><span class="sxs-lookup"><span data-stu-id="59b71-156">This will display the label page that shows a listing of your example files, with the first file visible in the viewer.</span></span>
2. <span data-ttu-id="59b71-157">In de viewer ziet u boven aan het eerste voorbeeldbestand tekst met de vraag of het bestand een voorbeeld is van het model dat u zojuist hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="59b71-157">In the viewer, on the top of the first example file, you will see text asking you if the file is an example of the model you just created.</span></span> <span data-ttu-id="59b71-158">Als het een positief voorbeeld is, selecteert u **Ja**.</span><span class="sxs-lookup"><span data-stu-id="59b71-158">If it is a positive example, select **Yes**.</span></span> <span data-ttu-id="59b71-159">Als het een negatief voorbeeld is, selecteert u **Nee**.</span><span class="sxs-lookup"><span data-stu-id="59b71-159">If it is a negative example, select **No**.</span></span>
3. <span data-ttu-id="59b71-160">Selecteer in de lijst **Met gelabelde voorbeelden** aan de linkerkant extra bestanden die u als voorbeeld wilt gebruiken en label ze ook.</span><span class="sxs-lookup"><span data-stu-id="59b71-160">From the **Labeled examples** list on the left, select additional files that you want to use as examples, and label them as well.</span></span> 

    ![Startpagina classificatiemodel](../media/content-understanding/classifier-home-page.png) 


> [!Note]
> <span data-ttu-id="59b71-162">Label ten minste vijf positieve voorbeelden, en een negatief voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="59b71-162">Label at least five positive examples, and one negative example.</span></span> 

## <a name="create-an-explanation"></a><span data-ttu-id="59b71-163">Een uitleg maken</span><span class="sxs-lookup"><span data-stu-id="59b71-163">Create an explanation</span></span>

<span data-ttu-id="59b71-164">De volgende stap is het maken van een uitleg op de pagina Trein.</span><span class="sxs-lookup"><span data-stu-id="59b71-164">The next step is to create an explanation on the Train page.</span></span>  <span data-ttu-id="59b71-165">Een verklaring is een hint of aanwijzing om het model te helpen begrijpen hoe dit document te herkennen.</span><span class="sxs-lookup"><span data-stu-id="59b71-165">An explanation is a hint or clue to help the model understand how to recognize this document.</span></span> <span data-ttu-id="59b71-166">Onze documenten voor contractverlenging bevatten bijvoorbeeld altijd een *aanvraag voor aanvullende openbaarmakingstekstreeks.*</span><span class="sxs-lookup"><span data-stu-id="59b71-166">For example, our Contract Renewal documents always contain a *Request for additional disclosure* text string.</span></span>

> [!Note]
> <span data-ttu-id="59b71-167">Wanneer u met uittreksers wordt gebruikt, wordt een uitleg gebruikt om de tekenreeks te identificeren die u uit het document wilt extraheren.</span><span class="sxs-lookup"><span data-stu-id="59b71-167">When used with extractors, an explanation is use to identify the string that you want to extract from the document.</span></span> 

<span data-ttu-id="59b71-168">Een verklaring maken:</span><span class="sxs-lookup"><span data-stu-id="59b71-168">To create an explanation:</span></span>

1. <span data-ttu-id="59b71-169">Klik op de startpagina van het model op het tabblad **Trein** om naar de pagina Trein te gaan.</span><span class="sxs-lookup"><span data-stu-id="59b71-169">On the model home page, click the **Train** tab to go to the Train page.</span></span>
2. <span data-ttu-id="59b71-170">Op de pagina Trein ziet u in de sectie **Getrainde bestanden** een lijst met de voorbeeldbestanden die u eerder had gelabeld.</span><span class="sxs-lookup"><span data-stu-id="59b71-170">On the Train page, in the **Trained files** section, you will see a list of the example files that you had labeled previously.</span></span> <span data-ttu-id="59b71-171">Selecteer een van uw positieve bestanden in de lijst en deze wordt weergegeven in de viewer.</span><span class="sxs-lookup"><span data-stu-id="59b71-171">Select one of your positive files from the list, and it will display in the viewer.</span></span>
3. <span data-ttu-id="59b71-172">Klik in de sectie Uitleg op **Nieuw**en klik vervolgens op **Leeg**.</span><span class="sxs-lookup"><span data-stu-id="59b71-172">In the Explanation section, click **New**, then click **Blank**.</span></span>
4. <span data-ttu-id="59b71-173">Op de pagina **Een uitleg** maken:</span><span class="sxs-lookup"><span data-stu-id="59b71-173">On the **Create an explanation** page:</span></span></br>
    <span data-ttu-id="59b71-174">a.</span><span class="sxs-lookup"><span data-stu-id="59b71-174">a.</span></span> <span data-ttu-id="59b71-175">Typ de **naam** (bijvoorbeeld 'Openbaarmakingsblok').</span><span class="sxs-lookup"><span data-stu-id="59b71-175">Type the **Name** (for example, "Disclosure Block").</span></span></br>
    <span data-ttu-id="59b71-176">b.</span><span class="sxs-lookup"><span data-stu-id="59b71-176">b.</span></span> <span data-ttu-id="59b71-177">Selecteer het **type**.</span><span class="sxs-lookup"><span data-stu-id="59b71-177">Select the **Type**.</span></span> <span data-ttu-id="59b71-178">In ons voorbeeld selecteren we **de lijst Met zinnen,** omdat we een tekenreeks toevoegen.</span><span class="sxs-lookup"><span data-stu-id="59b71-178">For our example, we'll select **Phrase list**, since we are adding a text string.</span></span></br>
    <span data-ttu-id="59b71-179">c.</span><span class="sxs-lookup"><span data-stu-id="59b71-179">c.</span></span> <span data-ttu-id="59b71-180">Typ de tekenreeks in het vak **Tekst hier.**</span><span class="sxs-lookup"><span data-stu-id="59b71-180">In the **Type here** box, type the string.</span></span>  <span data-ttu-id="59b71-181">In ons voorbeeld voegen we 'Verzoek om aanvullende openbaarmaking' toe.</span><span class="sxs-lookup"><span data-stu-id="59b71-181">For our example, we'll add "Request for additional disclosure".</span></span> <span data-ttu-id="59b71-182">U **gevalgevoelig** selecteren als de tekenreeks gevalgevoelig moet zijn.</span><span class="sxs-lookup"><span data-stu-id="59b71-182">You can select **Case sensitive** if the string needs to be case sensitive.</span></span></br>
    <span data-ttu-id="59b71-183">d.</span><span class="sxs-lookup"><span data-stu-id="59b71-183">d.</span></span> <span data-ttu-id="59b71-184">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="59b71-184">Click **Save**.</span></span>

    ![Uitleg maken](../media/content-understanding/explanation.png) 
    
 
5.  <span data-ttu-id="59b71-186">Het model controleert nu of de uitleg die u hebt gemaakt goed genoeg was om uw resterende gelabelde voorbeeldbestanden correct te identificeren als positieve en negatieve voorbeelden.</span><span class="sxs-lookup"><span data-stu-id="59b71-186">The model will now check to see if the explanation you created was good enough to identify your remaining labeled example files correctly as positive and negative examples.</span></span> <span data-ttu-id="59b71-187">Controleer in de sectie Getrainde bestanden de kolom **Evaluatie** nadat de training is voltooid om de resultaten te bekijken.</span><span class="sxs-lookup"><span data-stu-id="59b71-187">In Trained Files section, check the **Evaluation** column after the training has completed to see the results.</span></span>  <span data-ttu-id="59b71-188">De bestanden tonen een waarde van **Match** als de uitleg die u hebt gemaakt voldoende was om overeen te komen met wat u ze als (positief of negatief) had bestempeld.</span><span class="sxs-lookup"><span data-stu-id="59b71-188">The files will show a value of **Match** if the explanation you created was enough to match what you had labeled them as (positive or negative).</span></span>

    ![Uitleg maken](../media/content-understanding/match.png) 

<span data-ttu-id="59b71-190">Als u een **mismatch** ontvangt op uw gelabelde bestanden, moet u mogelijk een aanvullende uitleg maken om het model meer informatie te geven om het documenttype te identificeren.</span><span class="sxs-lookup"><span data-stu-id="59b71-190">If you receive a **Mismatch** on your labeled files, you may need to create an additional explanation to provide the model more information to identify the document type.</span></span> <span data-ttu-id="59b71-191">U op het bestand klikken om meer informatie te krijgen over waarom de mismatch heeft plaatsgevonden.</span><span class="sxs-lookup"><span data-stu-id="59b71-191">You can click on the file to get more information about why the mismatch occurred.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="59b71-192">Test uw model</span><span class="sxs-lookup"><span data-stu-id="59b71-192">Test your model</span></span>

<span data-ttu-id="59b71-193">Als u een overeenkomst hebt ontvangen in uw gelabelde voorbeeldbestanden, u uw model nu testen op uw resterende niet-gelabelde voorbeeldbestanden.</span><span class="sxs-lookup"><span data-stu-id="59b71-193">If you received a match on your labeled example files, you can now test your model on your remaining unlabeled example files.</span></span>

1. <span data-ttu-id="59b71-194">Klik op de startpagina van het model op het tabblad **Testen.**  Hiermee wordt het model uitgevoerd op uw niet-gelabelde voorbeeldbestanden.</span><span class="sxs-lookup"><span data-stu-id="59b71-194">On the model home page, click the **Test** tab.  This will run the model on your unlabeled example files.</span></span>
2. <span data-ttu-id="59b71-195">In de lijst **Bestanden testen** worden uw voorbeeldbestanden weergegeven en wordt weergegeven of het model voorspelde dat ze positieve of negatieve voorbeelden zijn.</span><span class="sxs-lookup"><span data-stu-id="59b71-195">In the **Test files** list, your example files will display and will show if the model predicted them to be positive or negative examples.</span></span> <span data-ttu-id="59b71-196">U deze informatie gebruiken om de effectiviteit van uw classificatie te bepalen bij het identificeren van uw documenten.</span><span class="sxs-lookup"><span data-stu-id="59b71-196">You can use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![Testen van niet-gelabelde bestanden](../media/content-understanding/test-on-files.png) 



## <a name="see-also"></a><span data-ttu-id="59b71-198">Zie ook</span><span class="sxs-lookup"><span data-stu-id="59b71-198">See Also</span></span>
[<span data-ttu-id="59b71-199">Een afzuiger maken</span><span class="sxs-lookup"><span data-stu-id="59b71-199">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="59b71-200">Overzicht van documentbegrip</span><span class="sxs-lookup"><span data-stu-id="59b71-200">Document Understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="59b71-201">Een formulierverwerkingsmodel maken</span><span class="sxs-lookup"><span data-stu-id="59b71-201">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>
[<span data-ttu-id="59b71-202">Een model toepassen</span><span class="sxs-lookup"><span data-stu-id="59b71-202">Apply a model</span></span>](apply-a-model.md) 




