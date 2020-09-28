---
title: Een classificatie maken
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
description: Leer hoe u een classificatie maakt
ms.openlocfilehash: 29b2a4775bec12649c66b4cb4a07fe5f0fc93ae2
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294900"
---
# <a name="create-a-classifier-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="21fee-103">Een classificatie maken in Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="21fee-103">Create a classifier in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="21fee-104">De inhoud in dit artikel is bedoeld voor de cortex van de private preview van project.</span><span class="sxs-lookup"><span data-stu-id="21fee-104">The content in this article is for the Project Cortex Private Preview.</span></span> <span data-ttu-id="21fee-105">[Lees meer over project cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="21fee-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL0R]  

</br>

<span data-ttu-id="21fee-106">Een classificatie is een type model dat u kunt gebruiken om de identificatie en classificatie van een documenttype te automatiseren.</span><span class="sxs-lookup"><span data-stu-id="21fee-106">A classifier is a type of model that you can use to automate identification and classification of a document type.</span></span> <span data-ttu-id="21fee-107">U kunt bijvoorbeeld alle documenten voor het verlengen van een *contract* voor de documentbibliotheek identificeren, zoals wordt weergegeven in de volgende afbeelding.</span><span class="sxs-lookup"><span data-stu-id="21fee-107">For example, you may want to identify all *Contract Renewal* documents that are added to your document library, such as is shown in the following illustration.</span></span>

![Document voor vernieuwing van contract](../media/content-understanding/contract-renewal.png)

<span data-ttu-id="21fee-109">Als u een classificatie maakt, kunt u een nieuw [SharePoint-inhouds type](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) maken dat is gekoppeld aan het model.</span><span class="sxs-lookup"><span data-stu-id="21fee-109">Creating a classifier enables you to create a new [SharePoint Content Type](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) that will be associated to the model.</span></span>

<span data-ttu-id="21fee-110">Wanneer u de classificatie maakt, moet u *uitleg* maken om het model te definiëren.</span><span class="sxs-lookup"><span data-stu-id="21fee-110">When creating the classifier, you need to create *explanations* to define the model.</span></span> <span data-ttu-id="21fee-111">Op deze manier kunt u algemene gegevens noteren waarvan u denkt dat deze het documenttype voortdurend moet vinden.</span><span class="sxs-lookup"><span data-stu-id="21fee-111">This enables you to note common data that you would expect to consistently find this document type.</span></span> 

<span data-ttu-id="21fee-112">Gebruik voorbeelden van het documenttype (' voorbeelden van bestanden ') om uw model te identificeren om bestanden met hetzelfde inhoudstype te identificeren.</span><span class="sxs-lookup"><span data-stu-id="21fee-112">Use examples of the document type ("example files") to "train" your model to identify files that have the same content type.</span></span>

<span data-ttu-id="21fee-113">Als u een classificatie wilt maken, moet u het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="21fee-113">To create a classifier, you need to:</span></span>
1. <span data-ttu-id="21fee-114">Geef een naam op voor uw model.</span><span class="sxs-lookup"><span data-stu-id="21fee-114">Name your model.</span></span>
2. <span data-ttu-id="21fee-115">Voeg uw voorbeeldbestanden toe.</span><span class="sxs-lookup"><span data-stu-id="21fee-115">Add your example files.</span></span>
3. <span data-ttu-id="21fee-116">Voorzie uw voorbeeldbestanden van een label.</span><span class="sxs-lookup"><span data-stu-id="21fee-116">Label your example files.</span></span>
4. <span data-ttu-id="21fee-117">Maak een uitleg.</span><span class="sxs-lookup"><span data-stu-id="21fee-117">Create an explanation.</span></span>
5. <span data-ttu-id="21fee-118">Test uw model.</span><span class="sxs-lookup"><span data-stu-id="21fee-118">Test your model.</span></span>

> [!NOTE]
> <span data-ttu-id="21fee-119">Hoewel uw model gebruikmaakt van een classificatie voor het identificeren en classificeren van documenttypen, kunt u ook kiezen voor het verzamelen van specifieke gegevens uit een bestand dat door het model wordt geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="21fee-119">While your model uses a classifier to identify and classify document types, you can also choose to pull specific pieces of information from each file identified by the model.</span></span> <span data-ttu-id="21fee-120">Dit doet u door een **Extractor** te maken om aan uw model toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="21fee-120">Do this by creating an **extractor** to add to your model.</span></span> <span data-ttu-id="21fee-121">Zie [een extractor maken](create-an-extractor.md).</span><span class="sxs-lookup"><span data-stu-id="21fee-121">See [Create an extractor](create-an-extractor.md).</span></span>

## <a name="name-your-model"></a><span data-ttu-id="21fee-122">De naam van uw model wijzigen</span><span class="sxs-lookup"><span data-stu-id="21fee-122">Name your model</span></span>

<span data-ttu-id="21fee-123">Voor het maken van uw model moet u de eerste stap een naam geven:</span><span class="sxs-lookup"><span data-stu-id="21fee-123">The first step to create your model is to give it a name:</span></span>

1. <span data-ttu-id="21fee-124">Selecteer in het inhouds centrum de optie **Nieuw**en **Maak vervolgens een model**.</span><span class="sxs-lookup"><span data-stu-id="21fee-124">From the Content Center, select **New**, and then **Create a model**.</span></span>
2. <span data-ttu-id="21fee-125">Typ in het vak Naam van **Nieuw document** de naam van het model in het veld **naam** .</span><span class="sxs-lookup"><span data-stu-id="21fee-125">In the **New document understanding model** pane, in the **Name** field type the name of the model.</span></span> <span data-ttu-id="21fee-126">Als u bijvoorbeeld documenten voor het verlengen van de contracten wilt identificeren, kunt u de naam van het model voor het *vernieuwen*van het model opgeven.</span><span class="sxs-lookup"><span data-stu-id="21fee-126">For example, if you want to identify contract renewal documents, you could name the model *Contract Renewal*.</span></span>
3. <span data-ttu-id="21fee-127">Kies **Create**.</span><span class="sxs-lookup"><span data-stu-id="21fee-127">Choose **Create**.</span></span> <span data-ttu-id="21fee-128">Hiermee maakt u een startpagina voor het model.</span><span class="sxs-lookup"><span data-stu-id="21fee-128">This creates a home page for the model.</span></span></br>

    ![Startpagina van het classificatiemodel](../media/content-understanding/model-home.png)

<span data-ttu-id="21fee-130">Wanneer u een model maakt, maakt u ook een nieuw SharePoint-inhoudstype.</span><span class="sxs-lookup"><span data-stu-id="21fee-130">When you create a model, you are also creating a new SharePoint content type.</span></span> <span data-ttu-id="21fee-131">Een SharePoint-inhoudstype vertegenwoordigt een categorie documenten met gemeenschappelijke kenmerken en deel een verzameling kolommen of metagegevenseigenschappen voor die specifieke inhoud.</span><span class="sxs-lookup"><span data-stu-id="21fee-131">A SharePoint content type represents a category of documents that have common characteristics and share a collection of columns or metadata properties for that particular content.</span></span> <span data-ttu-id="21fee-132">SharePoint-inhoudstypen worden beheerd via de [Galerie met inhoudstypen](https://support.microsoft.com/office/create-or-customize-a-site-content-type-27eb6551-9867-4201-a819-620c5658a60f).</span><span class="sxs-lookup"><span data-stu-id="21fee-132">SharePoint Content Types are managed through the [Content types gallery](https://support.microsoft.com/office/create-or-customize-a-site-content-type-27eb6551-9867-4201-a819-620c5658a60f).</span></span> <span data-ttu-id="21fee-133">Als u het model maakt voor dit voorbeeld, maakt u een nieuw inhoudstype voor het verlengen van een *contract* .</span><span class="sxs-lookup"><span data-stu-id="21fee-133">For this example, when you create the model, you are creating a new *Contract Renewal* content type.</span></span>

<span data-ttu-id="21fee-134">Selecteer **Geavanceerde instellingen** als u dit model wilt toewijzen aan een bestaand inhoudstype in de galerie SharePoint-inhoudstypen om het schema te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="21fee-134">Select **Advanced settings** if you want to map this model to an existing content type in the SharePoint Content types gallery to use its schema.</span></span> <span data-ttu-id="21fee-135">Houd er rekening mee dat u met een bestaand inhoudstype het schema kunt gebruiken voor het identificeren en classificeren van een bestaand inhoudstype zodat u de gegevens kunt ophalen uit de bestanden die worden geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="21fee-135">Note that while you can use an existing content type to leverage its schema to help with identification and classification, you still need to train your model to extract information from files it identifies.</span></span></br>

![Geavanceerde instellingen](../media/content-understanding/advanced-settings.png)

## <a name="add-your-example-files"></a><span data-ttu-id="21fee-137">Voorbeeldbestanden toevoegen</span><span class="sxs-lookup"><span data-stu-id="21fee-137">Add your example files</span></span>

<span data-ttu-id="21fee-138">Voeg op de startpagina van het model uw voorbeelden van bestanden toe die u nodig hebt om het model te leren bieden ter identificatie van uw documenttype.</span><span class="sxs-lookup"><span data-stu-id="21fee-138">On the model home page, add your examples files you will need to help train the model to identify your document type.</span></span> </br>
</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4D0iX] 

</br>

> [!NOTE]
> <span data-ttu-id="21fee-139">U dient dezelfde bestanden te gebruiken voor de training Classifier en [Extractor](create-an-extractor.md).</span><span class="sxs-lookup"><span data-stu-id="21fee-139">You should use the same files for both classifier and [extractor training](create-an-extractor.md).</span></span> <span data-ttu-id="21fee-140">U hebt altijd de mogelijkheid om later meer toe te voegen, maar u voegt meestal een volledige set voorbeeldbestanden toe.</span><span class="sxs-lookup"><span data-stu-id="21fee-140">You always have the option to add more later, but typically you add a full set of sample files.</span></span> <span data-ttu-id="21fee-141">Voorzie wat van een deel van uw model en test de resterende ongelabelde producten om de geschiktheid van het model te beoordelen.</span><span class="sxs-lookup"><span data-stu-id="21fee-141">Label some to train your model, and test the remaining unlabeled ones to evaluate model fitness.</span></span> 

<span data-ttu-id="21fee-142">Voor de set training wilt u zowel positieve als negatieve voorbeelden gebruiken:</span><span class="sxs-lookup"><span data-stu-id="21fee-142">For your training set, you want to use both positive and negative examples:</span></span>
- <span data-ttu-id="21fee-143">Positief voorbeeld: documenten die het documenttype aangeven.</span><span class="sxs-lookup"><span data-stu-id="21fee-143">Positive example: Documents that represent the document type.</span></span> <span data-ttu-id="21fee-144">Dit bevat tekenreeksen en informatie over dit type document.</span><span class="sxs-lookup"><span data-stu-id="21fee-144">These contain strings and information that would always be in this type of document.</span></span>
- <span data-ttu-id="21fee-145">Negatief voorbeeld: documenten die niet het documenttype vertegenwoordigen.</span><span class="sxs-lookup"><span data-stu-id="21fee-145">Negative example: Documents that do not represent the document type.</span></span> <span data-ttu-id="21fee-146">Dit ontbreken tekenreeksen en gegevens die in dit type document moeten worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="21fee-146">These are missing strings and information that needs to be present in this type of document.</span></span>

<span data-ttu-id="21fee-147">Zorg ervoor dat u ten minste vijf positieve voorbeelden en minstens één negatief voorbeeld gebruikt om het model te leren bieden.</span><span class="sxs-lookup"><span data-stu-id="21fee-147">Be sure to use at least five positive examples and at least one negative example to train your model.</span></span>  <span data-ttu-id="21fee-148">U wilt nog meer items maken om uw model na het trainingsproces te testen.</span><span class="sxs-lookup"><span data-stu-id="21fee-148">You want to create additional ones to test your model after the training process.</span></span>

<span data-ttu-id="21fee-149">Voorbeeldbestanden toevoegen:</span><span class="sxs-lookup"><span data-stu-id="21fee-149">To add sample files:</span></span>

1. <span data-ttu-id="21fee-150">Klik op de startpagina van het model in de tegel **voorbeeld bibliotheek opbouwen** op **bestanden toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="21fee-150">From the model home page, in the **Build sample library** tile, click **Add files**.</span></span>
2. <span data-ttu-id="21fee-151">Selecteer op de pagina **voorbeeldbestanden voor uw model selecteren** de voorbeeldbestanden uit de voorbeeldbestanden bibliotheek in het inhouds centrum.</span><span class="sxs-lookup"><span data-stu-id="21fee-151">On the **Select sample files for your model** page, select your example files from the Sample files library in the Content Center.</span></span> <span data-ttu-id="21fee-152">Als u deze niet al had geüpload, kunt u deze nu uploaden door te klikken op **uploaden** om de bestanden te verplaatsen.</span><span class="sxs-lookup"><span data-stu-id="21fee-152">If you had not already uploaded them there, choose to upload them now by clicking **Upload** to move them the Sample file library.</span></span>
3. <span data-ttu-id="21fee-153">Selecteer **toevoegen**nadat u de voorbeeldbestanden hebt geselecteerd die u wilt gebruiken voor het trainen van het model.</span><span class="sxs-lookup"><span data-stu-id="21fee-153">After selecting your example files to use to train the model, click **Add**.</span></span>

    ![Voorbeeldbestanden selecteren](../media/content-understanding/select-sample.png) 

## <a name="label-your-example-files"></a><span data-ttu-id="21fee-155">Een label opgeven voor voorbeeldbestanden</span><span class="sxs-lookup"><span data-stu-id="21fee-155">Label your example files</span></span>

<span data-ttu-id="21fee-156">Wanneer u voorbeeldbestanden hebt toegevoegd, moet u deze als een positief of negatief voorbeeld markeren.</span><span class="sxs-lookup"><span data-stu-id="21fee-156">After adding your example files, you need to label them as either positive or negative examples.</span></span>

1. <span data-ttu-id="21fee-157">Klik op de startpagina van het model op de tegel **bestanden classificeren en training uitvoeren** op **classificatie voor trainer**.</span><span class="sxs-lookup"><span data-stu-id="21fee-157">From the model home page, on the **Classify files and run training** tile, click **Train Classifier**.</span></span>
   <span data-ttu-id="21fee-158">Hiermee wordt de etiket pagina weergegeven met een overzicht van de voorbeeldbestanden, waarbij het eerste bestand zichtbaar is in de viewer.</span><span class="sxs-lookup"><span data-stu-id="21fee-158">This displays the label page that shows a listing of your example files, with the first file visible in the viewer.</span></span>
2. <span data-ttu-id="21fee-159">In de viewer boven aan het eerste voorbeeldbestand ziet u tekst met de vraag of het bestand een voorbeeld is van het model dat u zojuist hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="21fee-159">In the viewer on the top of the first example file, you should see text asking if the file is an example of the model you just created.</span></span> <span data-ttu-id="21fee-160">Als het om een positief voorbeeld gaat, selecteert u **Ja**.</span><span class="sxs-lookup"><span data-stu-id="21fee-160">If it is a positive example, select **Yes**.</span></span> <span data-ttu-id="21fee-161">Als het om een negatief voorbeeld gaat, selecteert u **Nee**.</span><span class="sxs-lookup"><span data-stu-id="21fee-161">If it is a negative example, select **No**.</span></span>
3. <span data-ttu-id="21fee-162">Selecteer in de lijst met **gelabelde voorbeelden** aan de linkerkant extra bestanden die u als voorbeeld wilt gebruiken, en voorzie ze van een label.</span><span class="sxs-lookup"><span data-stu-id="21fee-162">From the **Labeled examples** list on the left, select additional files that you want to use as examples, and label them.</span></span> 

    ![Startpagina classificatie](../media/content-understanding/classifier-home-page.png) 


> [!NOTE]
> <span data-ttu-id="21fee-164">Etiketten van minimaal vijf positieve voorbeelden en een negatief voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="21fee-164">Label at least five positive examples, and one negative example.</span></span> 

## <a name="create-an-explanation"></a><span data-ttu-id="21fee-165">Een uitleg maken</span><span class="sxs-lookup"><span data-stu-id="21fee-165">Create an explanation</span></span>

<span data-ttu-id="21fee-166">De volgende stap is een uitleg over het maken van een uitleg op de pagina van de trein.</span><span class="sxs-lookup"><span data-stu-id="21fee-166">The next step is for you to create an explanation on the Train page.</span></span> <span data-ttu-id="21fee-167">Met een uitleg wordt het model vertrouwd met het herkennen van het document.</span><span class="sxs-lookup"><span data-stu-id="21fee-167">An explanation helps the model understand how to recognize the document.</span></span> <span data-ttu-id="21fee-168">De documenten voor het verlengen van het contract bevatten bijvoorbeeld altijd een *aanvraag voor aanvullende informatie over de verschaffings* tekst.</span><span class="sxs-lookup"><span data-stu-id="21fee-168">For example, the Contract Renewal documents always contain a *Request for additional disclosure* text string.</span></span>

> [!Note]
> <span data-ttu-id="21fee-169">Wanneer u deze gebruikt met uitpaknen, wordt met een uitleg de tekenreeks aangegeven die u uit het document wilt extraheren.</span><span class="sxs-lookup"><span data-stu-id="21fee-169">When used with extractors, an explanation identifies the string that you want to extract from the document.</span></span> 

<span data-ttu-id="21fee-170">Een uitleg maken:</span><span class="sxs-lookup"><span data-stu-id="21fee-170">To create an explanation:</span></span>

1. <span data-ttu-id="21fee-171">Op de startpagina van het model, selecteert u het tabblad **trein** om naar de pagina training te gaan.</span><span class="sxs-lookup"><span data-stu-id="21fee-171">From the model home page, select the **Train** tab to go to the Train page.</span></span>
2. <span data-ttu-id="21fee-172">Op de pagina Train, in de sectie met uitbesteieve **bestanden** , ziet u een lijst met de voorbeeldbestanden die u eerder hebt gelabeld.</span><span class="sxs-lookup"><span data-stu-id="21fee-172">On the Train page, in the **Trained files** section you should see a list of the sample files that you previously labeled.</span></span> <span data-ttu-id="21fee-173">Selecteer een van de positieve bestanden in de lijst en wordt weergegeven in de viewer.</span><span class="sxs-lookup"><span data-stu-id="21fee-173">Select one of the positive files from the list, and it displays in the viewer.</span></span>
3. <span data-ttu-id="21fee-174">Selecteer in de sectie uitleg de optie **Nieuw** en selecteer **leeg**.</span><span class="sxs-lookup"><span data-stu-id="21fee-174">In the Explanation section, select **New** and then **Blank**.</span></span>
4. <span data-ttu-id="21fee-175">Op de pagina **een uitleg maken** :</span><span class="sxs-lookup"><span data-stu-id="21fee-175">On the **Create an explanation** page:</span></span></br>
    <span data-ttu-id="21fee-176">a.</span><span class="sxs-lookup"><span data-stu-id="21fee-176">a.</span></span> <span data-ttu-id="21fee-177">Typ de **naam** (bijvoorbeeld ' uitschaffings blok ').</span><span class="sxs-lookup"><span data-stu-id="21fee-177">Type the **Name** (for example, "Disclosure Block").</span></span></br>
    <span data-ttu-id="21fee-178">b.</span><span class="sxs-lookup"><span data-stu-id="21fee-178">b.</span></span> <span data-ttu-id="21fee-179">Selecteer het **type**.</span><span class="sxs-lookup"><span data-stu-id="21fee-179">Select the **Type**.</span></span> <span data-ttu-id="21fee-180">Voorbeeld: Selecteer **phrase List**, aangezien u een tekenreeks toevoegt.</span><span class="sxs-lookup"><span data-stu-id="21fee-180">For the sample, select **Phrase list**, since you add a text string.</span></span></br>
    <span data-ttu-id="21fee-181">c.</span><span class="sxs-lookup"><span data-stu-id="21fee-181">c.</span></span> <span data-ttu-id="21fee-182">Typ in het vak **Typ hier** de tekenreeks.</span><span class="sxs-lookup"><span data-stu-id="21fee-182">In the **Type here** box, type the string.</span></span> <span data-ttu-id="21fee-183">Voorbeeld van het toevoegen van een aanvraag voor aanvullende informatie.</span><span class="sxs-lookup"><span data-stu-id="21fee-183">For the sample, add "Request for additional disclosure".</span></span> <span data-ttu-id="21fee-184">U kunt onderscheid maken tussen **hoofd** letters en kleine letters in de tekenreeks.</span><span class="sxs-lookup"><span data-stu-id="21fee-184">You can select **Case sensitive** if the string needs to be case sensitive.</span></span></br>
    <span data-ttu-id="21fee-185">d.</span><span class="sxs-lookup"><span data-stu-id="21fee-185">d.</span></span> <span data-ttu-id="21fee-186">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="21fee-186">Click **Save**.</span></span>

    ![Uitleg maken](../media/content-understanding/explanation.png) 
    
 
5. <span data-ttu-id="21fee-188">Het model controleert nu of de uitleg die u hebt gemaakt goed genoeg was om de resterende gelabelde voorbeeldbestanden correct te identificeren, met een positief en negatief voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="21fee-188">The model now checks to see if the explanation you created was good enough to identify the remaining labeled example files correctly, as positive and negative examples.</span></span> <span data-ttu-id="21fee-189">Selecteer in de sectie opgeleid files de kolom **evaluatie** nadat de training is voltooid om de resultaten te bekijken.</span><span class="sxs-lookup"><span data-stu-id="21fee-189">In the Trained Files section, check the **Evaluation** column after the training has completed to see the results.</span></span> <span data-ttu-id="21fee-190">De bestanden bevatten de **gezochte**waarde, als de door u gemaakte uitleg voldoende is voor de naam van het bestand dat u als positief of negatief hebt aangemerkt.</span><span class="sxs-lookup"><span data-stu-id="21fee-190">The files show a value of **Match**, if the explanations you created was enough to match what you labeled as positive or negative.</span></span>

    ![Waarde vergelijken](../media/content-understanding/match.png) 

<span data-ttu-id="21fee-192">Als u een **niet-overeenkomend** bestand met gelabelde bestanden ontvangt, moet u mogelijk een extra uitleg maken om het model meer informatie te verschaffen ter identificatie van het documenttype.</span><span class="sxs-lookup"><span data-stu-id="21fee-192">If you receive a **Mismatch** on the labeled files, you may need to create an additional explanation to provide the model more information to identify the document type.</span></span> <span data-ttu-id="21fee-193">Als dit het geval is, klikt u op het bestand om meer informatie weer te geven over de reden waarom de fout is opgetreden.</span><span class="sxs-lookup"><span data-stu-id="21fee-193">If this happens, click on the file to get more information about why the mismatch occurred.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="21fee-194">Uw model testen</span><span class="sxs-lookup"><span data-stu-id="21fee-194">Test your model</span></span>

<span data-ttu-id="21fee-195">Als u een overeenkomst met de gelabelde voorbeeldbestanden hebt ontvangen, kunt u de naam van uw model testen in de resterende voorbeeldbestanden met bijschriften.</span><span class="sxs-lookup"><span data-stu-id="21fee-195">If you received a match on your labeled sample files, you can now test your model on your remaining unlabeled example files.</span></span>

1. <span data-ttu-id="21fee-196">Selecteer op de startpagina van het model het tabblad **testen** .  Hiermee voert u het model uit op uw niet-gelabelde voorbeeldbestanden.</span><span class="sxs-lookup"><span data-stu-id="21fee-196">From the model home page, select the **Test** tab.  This runs the model on your unlabeled sample files.</span></span>
2. <span data-ttu-id="21fee-197">In de lijst **bestanden testen** worden de voorbeeldbestanden weergegeven en wordt weergegeven of het model met de voor spelling positief of negatief is.</span><span class="sxs-lookup"><span data-stu-id="21fee-197">In the **Test files** list, your example files display and shows if the model predicted them to be positive or negative.</span></span> <span data-ttu-id="21fee-198">Met deze informatie kunt u de effectiviteit van uw classificatie voor het identificeren van documenten bepalen.</span><span class="sxs-lookup"><span data-stu-id="21fee-198">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![Test van bestanden zonder label](../media/content-understanding/test-on-files.png) 

## <a name="see-also"></a><span data-ttu-id="21fee-200">Zie ook</span><span class="sxs-lookup"><span data-stu-id="21fee-200">See Also</span></span>
[<span data-ttu-id="21fee-201">Een extractor maken</span><span class="sxs-lookup"><span data-stu-id="21fee-201">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="21fee-202">Overzicht van document</span><span class="sxs-lookup"><span data-stu-id="21fee-202">Document Understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="21fee-203">Een formulier verwerkings model maken</span><span class="sxs-lookup"><span data-stu-id="21fee-203">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>
[<span data-ttu-id="21fee-204">Een model toepassen</span><span class="sxs-lookup"><span data-stu-id="21fee-204">Apply a model</span></span>](apply-a-model.md) 
