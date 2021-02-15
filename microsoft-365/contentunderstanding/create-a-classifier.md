---
title: Een classificatie maken
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
description: Lees hoe je een classificatie maakt
ms.openlocfilehash: bff23807fce18bf4a585dbb1ec47c1502ab686f6
ms.sourcegitcommit: 78f48304f990e969a052fe6536b2e8d6856e1086
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/14/2021
ms.locfileid: "50242686"
---
# <a name="create-a-classifier-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="823cd-103">Een classificatie maken in Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="823cd-103">Create a classifier in Microsoft SharePoint Syntex</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL0R]  

</br>

<span data-ttu-id="823cd-104">Een classificatie is een typemodel dat je kunt gebruiken om de identificatie en classificatie van een documenttype te automatiseren.</span><span class="sxs-lookup"><span data-stu-id="823cd-104">A classifier is a type of model that you can use to automate identification and classification of a document type.</span></span> <span data-ttu-id="823cd-105">Het is bijvoorbeeld mogelijk dat je alle *contract wilt identificeren* documenten die worden toegevoegd aan de documentbibliotheek, zoals wordt weergegeven in de volgende afbeelding.</span><span class="sxs-lookup"><span data-stu-id="823cd-105">For example, you may want to identify all *Contract Renewal* documents that are added to your document library, such as is shown in the following illustration.</span></span>

![Contract voor contractverlenging](../media/content-understanding/contract-renewal.png)

<span data-ttu-id="823cd-107">Als je een classificatie maakt, kun je een nieuw [SharePoint-inhoudstype](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) maken dat aan het model wordt gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="823cd-107">Creating a classifier enables you to create a new [SharePoint content type](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) that will be associated to the model.</span></span>

<span data-ttu-id="823cd-108">Bij het maken van de classificatie moet je *uitleg* maken om het model te definiëren.</span><span class="sxs-lookup"><span data-stu-id="823cd-108">When creating the classifier, you need to create *explanations* to define the model.</span></span> <span data-ttu-id="823cd-109">Op deze manier kun je algemene gegevens noteren waarop je dit documenttype consequent zou verwachten.</span><span class="sxs-lookup"><span data-stu-id="823cd-109">This enables you to note common data that you would expect to consistently find this document type.</span></span> 

<span data-ttu-id="823cd-110">Gebruik voorbeelden van het documenttype (' voorbeeldbestanden') om het model te trainen om bestanden met hetzelfde inhoudstype te identificeren.</span><span class="sxs-lookup"><span data-stu-id="823cd-110">Use examples of the document type ("example files") to "train" your model to identify files that have the same content type.</span></span>

<span data-ttu-id="823cd-111">Om een classificatie te maken, moet je:</span><span class="sxs-lookup"><span data-stu-id="823cd-111">To create a classifier, you need to:</span></span>
1. <span data-ttu-id="823cd-112">Geef het model een naam.</span><span class="sxs-lookup"><span data-stu-id="823cd-112">Name your model.</span></span>
2. <span data-ttu-id="823cd-113">Voeg je voorbeeldbestanden toe.</span><span class="sxs-lookup"><span data-stu-id="823cd-113">Add your example files.</span></span>
3. <span data-ttu-id="823cd-114">Label je voorbeeldbestanden.</span><span class="sxs-lookup"><span data-stu-id="823cd-114">Label your example files.</span></span>
4. <span data-ttu-id="823cd-115">Maak een uitleg.</span><span class="sxs-lookup"><span data-stu-id="823cd-115">Create an explanation.</span></span>
5. <span data-ttu-id="823cd-116">Test je model.</span><span class="sxs-lookup"><span data-stu-id="823cd-116">Test your model.</span></span>

> [!NOTE]
> <span data-ttu-id="823cd-117">Hoewel je model een classificatie gebruikt om documenttypen te identificeren en te classificeren, kun je er ook voor kiezen om specifieke gegevens te verzamelen uit elk bestand dat door het model wordt aangeduid.</span><span class="sxs-lookup"><span data-stu-id="823cd-117">While your model uses a classifier to identify and classify document types, you can also choose to pull specific pieces of information from each file identified by the model.</span></span> <span data-ttu-id="823cd-118">Dit doe je door een **Extractor** te maken om toe te voegen aan je model.</span><span class="sxs-lookup"><span data-stu-id="823cd-118">Do this by creating an **extractor** to add to your model.</span></span> <span data-ttu-id="823cd-119">Zie[Een extractor maken](create-an-extractor.md).</span><span class="sxs-lookup"><span data-stu-id="823cd-119">See [Create an extractor](create-an-extractor.md).</span></span>

## <a name="name-your-model"></a><span data-ttu-id="823cd-120">Geef het model een naam</span><span class="sxs-lookup"><span data-stu-id="823cd-120">Name your model</span></span>

<span data-ttu-id="823cd-121">De eerste stap voor het maken van een model is het geven van een naam:</span><span class="sxs-lookup"><span data-stu-id="823cd-121">The first step to create your model is to give it a name:</span></span>

1. <span data-ttu-id="823cd-122">Selecteer in het Inhoudscentrum **Nieuw** en klik vervolgens **Maak een model**.</span><span class="sxs-lookup"><span data-stu-id="823cd-122">From the content center, select **New**, and then **Create a model**.</span></span>
2. <span data-ttu-id="823cd-123">Typ in het deelvenster **Nieuw document met inzicht in model** in het veldtype **Naam** de naam van het model.</span><span class="sxs-lookup"><span data-stu-id="823cd-123">In the **New document understanding model** pane, in the **Name** field type the name of the model.</span></span> <span data-ttu-id="823cd-124">Als je bijvoorbeeld documenten voor het verlengen van het contract wilt identificeren, kun je het model *Contractverlenging* noemen.</span><span class="sxs-lookup"><span data-stu-id="823cd-124">For example, if you want to identify contract renewal documents, you could name the model *Contract Renewal*.</span></span>
3. <span data-ttu-id="823cd-125">Kies **Create**.</span><span class="sxs-lookup"><span data-stu-id="823cd-125">Choose **Create**.</span></span> <span data-ttu-id="823cd-126">Hiermee maa je een startpagina voor het model.</span><span class="sxs-lookup"><span data-stu-id="823cd-126">This creates a home page for the model.</span></span></br>

    ![Startpagina voor classificatiemodel](../media/content-understanding/model-home.png)

<span data-ttu-id="823cd-128">Wanneer je een model maakt, maak je ook een nieuw site-inhoudstype.</span><span class="sxs-lookup"><span data-stu-id="823cd-128">When you create a model, you are also creating a new site content type.</span></span> <span data-ttu-id="823cd-129">Een inhoudstype is een categorie documenten met gemeenschappelijke kenmerken en een verzameling kolommen of metagegevenseigenschappen voor die inhoud delen.</span><span class="sxs-lookup"><span data-stu-id="823cd-129">A content type represents a category of documents that have common characteristics and share a collection of columns or metadata properties for that particular content.</span></span> <span data-ttu-id="823cd-130">SharePoint-inhoudstypen worden beheerd via de [Galerie met inhoudstypen](https://support.microsoft.com/office/create-or-customize-a-site-content-type-27eb6551-9867-4201-a819-620c5658a60f).</span><span class="sxs-lookup"><span data-stu-id="823cd-130">SharePoint content types are managed through the [Content types gallery](https://support.microsoft.com/office/create-or-customize-a-site-content-type-27eb6551-9867-4201-a819-620c5658a60f).</span></span> <span data-ttu-id="823cd-131">Als je in dit voorbeeld het model maakt, maak je een nieuwe *contract vernieuwing*-inhoudstype.</span><span class="sxs-lookup"><span data-stu-id="823cd-131">For this example, when you create the model, you are creating a new *Contract Renewal* content type.</span></span>

<span data-ttu-id="823cd-132">Selecteer **Geavanceerde instellingen** als je dit model wilt toewijzen aan een bestaand ondernemingsinhoudstype in de SharePoint-galerie met inhoudstypen om het bijbehorende schema te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="823cd-132">Select **Advanced settings** if you want to map this model to an existing enterprise content type in the SharePoint Content types gallery to use its schema.</span></span> <span data-ttu-id="823cd-133">Ondernemingsinhoudtypen worden opgeslagen in de hub inhoudstype in het SharePoint-Beheercentrum en worden gepubliceerd naar alle sites in de Tenant.</span><span class="sxs-lookup"><span data-stu-id="823cd-133">Enterprise content types are stored in the Content Type Hub in the SharePoint admin center and are syndicated to all sites in the tenant.</span></span> <span data-ttu-id="823cd-134">Hoewel je een bestaand inhoudstype kunt gebruiken om het bijbehorende schema te gebruiken om te helpen bij het identificeren en classificeren, moet je het model nog steeds trainen om gegevens uit bestanden die worden geïdentificeerd op te halen.</span><span class="sxs-lookup"><span data-stu-id="823cd-134">Note that while you can use an existing content type to leverage its schema to help with identification and classification, you still need to train your model to extract information from files it identifies.</span></span></br>

![Geavanceerde instellingen](../media/content-understanding/advanced-settings.png)

## <a name="add-your-example-files"></a><span data-ttu-id="823cd-136">Voeg je voorbeeldbestanden toe</span><span class="sxs-lookup"><span data-stu-id="823cd-136">Add your example files</span></span>

<span data-ttu-id="823cd-137">Voeg op de startpagina van het model je voorbeelden-bestanden toe die je nodig hebt om het model te helpen je documenttype te identificeren.</span><span class="sxs-lookup"><span data-stu-id="823cd-137">On the model home page, add your examples files you will need to help train the model to identify your document type.</span></span> </br>
</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4D0iX] 

</br>

> [!NOTE]
> <span data-ttu-id="823cd-138">Je moet dezelfde bestanden gebruiken voor zowel classificatie als [Extractor-training](create-an-extractor.md).</span><span class="sxs-lookup"><span data-stu-id="823cd-138">You should use the same files for both classifier and [extractor training](create-an-extractor.md).</span></span> <span data-ttu-id="823cd-139">Je kunt altijd later meer toevoegen, maar meestal voeg je een volledige set voorbeeldbestanden toe.</span><span class="sxs-lookup"><span data-stu-id="823cd-139">You always have the option to add more later, but typically you add a full set of example files.</span></span> <span data-ttu-id="823cd-140">Geef een naam op voor je model en test de resterende niet-gelabelde om model geschiktheid te evalueren.</span><span class="sxs-lookup"><span data-stu-id="823cd-140">Label some to train your model, and test the remaining unlabeled ones to evaluate model fitness.</span></span> 

<span data-ttu-id="823cd-141">Voor het instellen van je training wil je zowel positieve als negatieve voorbeelden gebruiken:</span><span class="sxs-lookup"><span data-stu-id="823cd-141">For your training set, you want to use both positive and negative examples:</span></span>
- <span data-ttu-id="823cd-142">Positief voorbeeld: documenten die het documenttype voorstellen.</span><span class="sxs-lookup"><span data-stu-id="823cd-142">Positive example: Documents that represent the document type.</span></span> <span data-ttu-id="823cd-143">Dit zijn tekenreeksen en informatie die altijd in dit type document voorkomen.</span><span class="sxs-lookup"><span data-stu-id="823cd-143">These contain strings and information that would always be in this type of document.</span></span>
- <span data-ttu-id="823cd-144">Negatief voorbeeld: een ander document dat niet overeenkomt met het document dat je wilt classificeren.</span><span class="sxs-lookup"><span data-stu-id="823cd-144">Negative example: Any other document that does not represent the document you want to classify.</span></span> 

<span data-ttu-id="823cd-145">Zorg ervoor dat je minimaal vijf positieve voorbeelden gebruikt en ten minste één negatief voorbeeld om het model te trainen.</span><span class="sxs-lookup"><span data-stu-id="823cd-145">Be sure to use at least five positive examples and at least one negative example to train your model.</span></span>  <span data-ttu-id="823cd-146">Je wilt extra codes maken om het model na het trainingsproces te testen.</span><span class="sxs-lookup"><span data-stu-id="823cd-146">You want to create additional ones to test your model after the training process.</span></span>

<span data-ttu-id="823cd-147">Om voorbeeldbestanden toe te voegen:</span><span class="sxs-lookup"><span data-stu-id="823cd-147">To add example files:</span></span>

1. <span data-ttu-id="823cd-148">Klik op de startpagina van het model in de **Voorbeeldbestanden toevoegen**-tegel op **Bestanden toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="823cd-148">On the model home page, in the **Add example files** tile, click **Add files**.</span></span>
2. <span data-ttu-id="823cd-149">Selecteer op de pagina **Voorbeeldbestanden voor je model** de optie bestanden uit de bibliotheek van trainingsbestanden in het inhoudscentrum.</span><span class="sxs-lookup"><span data-stu-id="823cd-149">On the **Select example files for your model** page, select your example files from the Training files library in the content center.</span></span> <span data-ttu-id="823cd-150">Als je ze nog niet hebt geüpload, kun je deze nu uploaden door op **Uploaden** te klikken om ze naar de bibliotheek met trainingsbestanden te kopiëren.</span><span class="sxs-lookup"><span data-stu-id="823cd-150">If you had not already uploaded them there, choose to upload them now by clicking **Upload** to copy them to the Training files library.</span></span>
3. <span data-ttu-id="823cd-151">Nadat je de voorbeeldbestanden hebt geselecteerd die je wilt gebruiken om het model te trainen, klik je op **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="823cd-151">After selecting your example files to use to train the model, click **Add**.</span></span>

    ![Selecteer voorbeeldbestanden](../media/content-understanding/select-sample.png) 

## <a name="label-your-example-files"></a><span data-ttu-id="823cd-153">Label je voorbeeldbestanden</span><span class="sxs-lookup"><span data-stu-id="823cd-153">Label your example files</span></span>

<span data-ttu-id="823cd-154">Nadat je de voorbeeldbestanden hebt toegevoegd, moet je ze een label geven als positieve of negatieve voorbeelden.</span><span class="sxs-lookup"><span data-stu-id="823cd-154">After adding your example files, you need to label them as either positive or negative examples.</span></span>

1. <span data-ttu-id="823cd-155">Klik op de startpagina van het model, op de tegel **Bestanden classificeren en training uitvoeren**, en klik op **Train Classifier**.</span><span class="sxs-lookup"><span data-stu-id="823cd-155">From the model home page, on the **Classify files and run training** tile, click **Train classifier**.</span></span>
   <span data-ttu-id="823cd-156">Hier wordt de labelpagina weergegeven met een lijst met voorbeeldbestanden met het eerste bestand dat in de viewer wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="823cd-156">This displays the label page that shows a listing of your example files, with the first file visible in the viewer.</span></span>
2. <span data-ttu-id="823cd-157">In de viewer boven aan het eerste voorbeeldbestand zie je tekst waarin je wordt gevraagd of het bestand een voorbeeld is van het model dat je zojuist hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="823cd-157">In the viewer on the top of the first example file, you should see text asking if the file is an example of the model you just created.</span></span> <span data-ttu-id="823cd-158">Als het om een positief voorbeeld gaat, selecteer je **Ja**.</span><span class="sxs-lookup"><span data-stu-id="823cd-158">If it is a positive example, select **Yes**.</span></span> <span data-ttu-id="823cd-159">Als het om een negatief voorbeeld gaat, selecteer je **Nee**.</span><span class="sxs-lookup"><span data-stu-id="823cd-159">If it is a negative example, select **No**.</span></span>
3. <span data-ttu-id="823cd-160">Klik in de **lijst met gelabelde voorbeelden** aan de linkerkant op extra bestanden die je als voorbeeld wilt gebruiken en voorzie ze van een label.</span><span class="sxs-lookup"><span data-stu-id="823cd-160">From the **Labeled examples** list on the left, select additional files that you want to use as examples, and label them.</span></span> 

    ![Startpagina voor classificatie](../media/content-understanding/classifier-home-page.png) 


> [!NOTE]
> <span data-ttu-id="823cd-162">Voorzie ten minste vijf positieve voorbeelden van labels.</span><span class="sxs-lookup"><span data-stu-id="823cd-162">Label at least five positive examples.</span></span> <span data-ttu-id="823cd-163">Je moet ook een label aan ten minste één negatief voorbeeld geven.</span><span class="sxs-lookup"><span data-stu-id="823cd-163">You must also label at least one negative example.</span></span> 

## <a name="create-an-explanation"></a><span data-ttu-id="823cd-164">Maak een uitleg</span><span class="sxs-lookup"><span data-stu-id="823cd-164">Create an explanation</span></span>

<span data-ttu-id="823cd-165">In de volgende stap wordt uitgelegd hoe je op de pagina Train een uitleg maakt.</span><span class="sxs-lookup"><span data-stu-id="823cd-165">The next step is for you to create an explanation on the Train page.</span></span> <span data-ttu-id="823cd-166">Met een uitleg wordt het model uitgelegd hoe je het document kunt herkennen.</span><span class="sxs-lookup"><span data-stu-id="823cd-166">An explanation helps the model understand how to recognize the document.</span></span> <span data-ttu-id="823cd-167">De documenten voor het verlengen van een contract bevatten bijvoorbeeld altijd een *Verzoek om aanvullende informatie* tekenreeks.</span><span class="sxs-lookup"><span data-stu-id="823cd-167">For example, the Contract Renewal documents always contain a *Request for additional disclosure* text string.</span></span>

> [!Note]
> <span data-ttu-id="823cd-168">Als je een verklaring gebruikt met uittreksels, wordt de tekenreeks die je wilt ophalen uit het document geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="823cd-168">When used with extractors, an explanation identifies the string that you want to extract from the document.</span></span> 

<span data-ttu-id="823cd-169">Maak een uitleg:</span><span class="sxs-lookup"><span data-stu-id="823cd-169">To create an explanation:</span></span>

1. <span data-ttu-id="823cd-170">Op de startpagina van het model selecteer je het tabblad **Train** om naar de pagina Train te gaan.</span><span class="sxs-lookup"><span data-stu-id="823cd-170">From the model home page, select the **Train** tab to go to the Train page.</span></span>
2. <span data-ttu-id="823cd-171">Op de pagina Train kun je in de sectie **Getrainde bestanden** een lijst zien met de voorbeeldbestanden waaraan je eerder een label hebt gegeven.</span><span class="sxs-lookup"><span data-stu-id="823cd-171">On the Train page, in the **Trained files** section you should see a list of the sample files that you previously labeled.</span></span> <span data-ttu-id="823cd-172">Selecteer een van de positieve bestanden uit de lijst en deze wordt weergegeven in de viewer.</span><span class="sxs-lookup"><span data-stu-id="823cd-172">Select one of the positive files from the list, and it displays in the viewer.</span></span>
3. <span data-ttu-id="823cd-173">In de sectie uitleg selecteert je **Nieuw** en vervolgens **Leeg**.</span><span class="sxs-lookup"><span data-stu-id="823cd-173">In the Explanation section, select **New** and then **Blank**.</span></span>
4. <span data-ttu-id="823cd-174">Op de pagina **Maak een uitleg**:</span><span class="sxs-lookup"><span data-stu-id="823cd-174">On the **Create an explanation** page:</span></span></br>
    <span data-ttu-id="823cd-175">a.</span><span class="sxs-lookup"><span data-stu-id="823cd-175">a.</span></span> <span data-ttu-id="823cd-176">Typ de **Naam**(bijvoorbeeld "uitnamelijst").</span><span class="sxs-lookup"><span data-stu-id="823cd-176">Type the **Name** (for example, "Disclosure Block").</span></span></br>
    <span data-ttu-id="823cd-177">b.</span><span class="sxs-lookup"><span data-stu-id="823cd-177">b.</span></span> <span data-ttu-id="823cd-178">Selecteer het **Type**.</span><span class="sxs-lookup"><span data-stu-id="823cd-178">Select the **Type**.</span></span> <span data-ttu-id="823cd-179">Voor het voorbeeld selecteer je **lijst met frasen** omdat je een tekenreeks toevoegt.</span><span class="sxs-lookup"><span data-stu-id="823cd-179">For the sample, select **Phrase list**, since you add a text string.</span></span></br>
    <span data-ttu-id="823cd-180">c.</span><span class="sxs-lookup"><span data-stu-id="823cd-180">c.</span></span> <span data-ttu-id="823cd-181">Typ de tekenreeks in het vak **Type hier**.</span><span class="sxs-lookup"><span data-stu-id="823cd-181">In the **Type here** box, type the string.</span></span> <span data-ttu-id="823cd-182">Voor het voorbeeld moet je „verzoek om aanvullende informatie“ toe voegen.</span><span class="sxs-lookup"><span data-stu-id="823cd-182">For the sample, add "Request for additional disclosure".</span></span> <span data-ttu-id="823cd-183">Je kunt **hoofdlettergevoeligheid selecteren** als de tekenreeks hoofdlettergevoelig moet zijn.</span><span class="sxs-lookup"><span data-stu-id="823cd-183">You can select **Case sensitive** if the string needs to be case sensitive.</span></span></br>
    <span data-ttu-id="823cd-184">d.</span><span class="sxs-lookup"><span data-stu-id="823cd-184">d.</span></span> <span data-ttu-id="823cd-185">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="823cd-185">Click **Save**.</span></span>

    ![Maak een uitleg](../media/content-understanding/explanation.png) 
    
5. <span data-ttu-id="823cd-187">Er wordt nu door het Inhoudscentrum gecontroleerd of de uitleg die je hebt gemaakt compleet is om de achterliggende voorbeeldbestanden op de juiste manier te identificeren, als positieve en negatieve voorbeelden.</span><span class="sxs-lookup"><span data-stu-id="823cd-187">The Content Center now checks to see if the explanation you created is complete enough to identify the remaining labeled example files correctly, as positive and negative examples.</span></span> <span data-ttu-id="823cd-188">Schakel in de sectie met opgeleid bestanden de **Evaluatie** kolom nadat de training is voltooid om de resultaten te zien.</span><span class="sxs-lookup"><span data-stu-id="823cd-188">In the Trained Files section, check the **Evaluation** column after the training has completed to see the results.</span></span> <span data-ttu-id="823cd-189">De bestanden bevatten de waarde **Overeenkomst** als de verklaringen die je hebt gemaakt voldoende zijn om aan te geven wat je als positief of negatief hebt gemarkeerd.</span><span class="sxs-lookup"><span data-stu-id="823cd-189">The files show a value of **Match**, if the explanations you created was enough to match what you labeled as positive or negative.</span></span>

    ![Overeenkomende waarde](../media/content-understanding/match.png) 

<span data-ttu-id="823cd-191">Als je een **niet-overeenkomende** ontvangt voor de gelabelde bestanden, moet je mogelijk een extra uitleg maken om het model meer informatie te geven om het documenttype te identificeren.</span><span class="sxs-lookup"><span data-stu-id="823cd-191">If you receive a **Mismatch** on the labeled files, you may need to create an additional explanation to provide the model more information to identify the document type.</span></span> <span data-ttu-id="823cd-192">Als dit gebeurt, klik je op het bestand om meer informatie weer te geven over de reden waarom de fout is opgetreden.</span><span class="sxs-lookup"><span data-stu-id="823cd-192">If this happens, click on the file to get more information about why the mismatch occurred.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="823cd-193">Test je model.</span><span class="sxs-lookup"><span data-stu-id="823cd-193">Test your model</span></span>

<span data-ttu-id="823cd-194">Als je een overeenkomst hebt gekregen met de gelabelde voorbeeldbestanden, kun je nu je model testen op de andere niet-gelabelde voorbeeldbestanden die het model nog niet heeft gezien.</span><span class="sxs-lookup"><span data-stu-id="823cd-194">If you received a match on your labeled sample files, you can now  test your model on your remaining unlabeled example files that the model has not seen before.</span></span>  <span data-ttu-id="823cd-195">Dit is een optionele, maar handige stap voor het evalueren van de "geschiktheid" of het voorbereiding van het model voordat dit wordt gebruikt, door het te testen op bestanden die het model nog niet heeft gezien.</span><span class="sxs-lookup"><span data-stu-id="823cd-195">This is optional, but a useful step to evaluate the “fitness” or readiness of the model before using it, by testing it on files the model hasn’t seen before.</span></span>

1. <span data-ttu-id="823cd-196">Op de startpagina van het model selecteer je het tabblad **Testen**.  Hiermee wordt het model uitgevoerd op de niet-gelabelde voorbeeldbestanden.</span><span class="sxs-lookup"><span data-stu-id="823cd-196">From the model home page, select the **Test** tab.  This runs the model on your unlabeled sample files.</span></span>
2. <span data-ttu-id="823cd-197">In de lijst **Testbestanden** worden de voorbeeldbestanden weergegeven en weergegeven als het model deze positief of negatief is.</span><span class="sxs-lookup"><span data-stu-id="823cd-197">In the **Test files** list, your example files display and shows if the model predicted them to be positive or negative.</span></span> <span data-ttu-id="823cd-198">Gebruik deze informatie om de effectiviteit van je classificatie bij het identificeren van je documenten vast te stellen.</span><span class="sxs-lookup"><span data-stu-id="823cd-198">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![Testen van bestanden zonder label](../media/content-understanding/test-on-files.png) 

## <a name="see-also"></a><span data-ttu-id="823cd-200">Zie ook</span><span class="sxs-lookup"><span data-stu-id="823cd-200">See Also</span></span>
[<span data-ttu-id="823cd-201">Een extractor maken</span><span class="sxs-lookup"><span data-stu-id="823cd-201">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="823cd-202">Overzicht van documentbegrip</span><span class="sxs-lookup"><span data-stu-id="823cd-202">Document Understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="823cd-203">Uitlegtypen</span><span class="sxs-lookup"><span data-stu-id="823cd-203">Explanation types</span></span>](explanation-types-overview.md)

[<span data-ttu-id="823cd-204">Een model toepassen</span><span class="sxs-lookup"><span data-stu-id="823cd-204">Apply a model</span></span>](apply-a-model.md) 

[<span data-ttu-id="823cd-205">SharePoint Syntex toegankelijkheidsmodus</span><span class="sxs-lookup"><span data-stu-id="823cd-205">SharePoint Syntex Accessibility Mode</span></span>](accessibility-mode.md)
