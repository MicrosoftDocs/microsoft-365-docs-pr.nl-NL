---
title: Stap 1. Gebruik SharePoint Syntex om contractbestanden te identificeren en gegevens op te halen
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: ''
description: Informatie over het gebruik van SharePoint Syntex om contractbestanden te identificeren en gegevens op te halen met een Microsoft 365 oplossing.
ms.openlocfilehash: b73f7b96a1f1a9159770fb1bfb20bf2718f08c07
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287351"
---
# <a name="step-1-use-sharepoint-syntex-to-identify-contract-files-and-extract-data"></a><span data-ttu-id="0b7c1-104">Stap 1.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-104">Step 1.</span></span> <span data-ttu-id="0b7c1-105">Gebruik SharePoint Syntex om contractbestanden te identificeren en gegevens op te halen</span><span class="sxs-lookup"><span data-stu-id="0b7c1-105">Use SharePoint Syntex to identify contract files and extract data</span></span>

<span data-ttu-id="0b7c1-106">Uw organisatie heeft een manier nodig om alle contractdocumenten te identificeren en te classificeren van de vele bestanden die u ontvangt.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-106">Your organization needs a way to identify and classify all contract documents from the many files you receive.</span></span> <span data-ttu-id="0b7c1-107">U wilt ook snel verschillende belangrijke elementen kunnen bekijken in elk van de geïdentificeerde contractbestanden (bijvoorbeeld *Client,* *Contractant* en *Kostenbedrag).*</span><span class="sxs-lookup"><span data-stu-id="0b7c1-107">You also want to be able to quickly view several key elements in each of the contract files identified (for example, *Client*, *Contractor*, and *Fee amount*).</span></span> <span data-ttu-id="0b7c1-108">U kunt dit doen door een document [SharePoint Syntex](index.md) te maken en toe te passen op een documentbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-108">You can do this by using [SharePoint Syntex](index.md) to create a document understanding model and applying it to a document library.</span></span>

## <a name="overview-of-the-process"></a><span data-ttu-id="0b7c1-109">Overzicht van het proces</span><span class="sxs-lookup"><span data-stu-id="0b7c1-109">Overview of the process</span></span>

<span data-ttu-id="0b7c1-110">[Documentkennis](document-understanding-overview.md) maakt gebruik van AI-modellen (Artificial Intelligence) om de classificatie van bestanden en de extractie van informatie te automatiseren.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-110">[Document understanding](document-understanding-overview.md) uses artificial intelligence (AI) models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="0b7c1-111">Documentkennismodellen zijn ook optimaal voor het extraheren van informatie uit ongestructureerde en semi-gestructureerde documenten waarin de informatie die u nodig hebt, niet is opgenomen in tabellen of formulieren, zoals contracten.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-111">Document understanding models are also optimal in extracting information from unstructured and semi-structured documents where the information you need isn't contained in tables or forms, such as contracts.</span></span> 

<span data-ttu-id="0b7c1-112">Documentbegripmodellen gebruiken Optical Character Recognition- (OCR) technologie om pdf-bestanden, afbeeldingen en tiff-bestanden te scannen wanneer je een model traint met voorbeeldbestanden en wanneer je het model uitvoert op bestanden in een documentbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-112">Document understanding models use Optical Character Recognition (OCR) technology to scan PDFs, images, and TIFF files, both when you train a model with example files and when you run the model against files in a document library.</span></span>

1. <span data-ttu-id="0b7c1-113">Eerst moet u ten minste vijf voorbeeldbestanden zoeken die u kunt gebruiken om het model te 'trainen' om te zoeken naar kenmerken die specifiek zijn voor het inhoudstype dat u wilt identificeren (een contract).</span><span class="sxs-lookup"><span data-stu-id="0b7c1-113">First, you need to find at least five example files that you can use to "train" the model to search for characteristics that are specific to the content type you're trying to identify (a contract).</span></span> 

2. <span data-ttu-id="0b7c1-114">Met SharePoint Syntex maakt u een nieuw documentkennismodel.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-114">Using SharePoint Syntex, create a new document understanding model.</span></span> <span data-ttu-id="0b7c1-115">Als u uw voorbeeldbestanden gebruikt, moet u [een classificatie maken.](create-a-classifier.md)</span><span class="sxs-lookup"><span data-stu-id="0b7c1-115">Using your example files, you need to [create a classifier](create-a-classifier.md).</span></span> <span data-ttu-id="0b7c1-116">Door de classificatie te trainen met uw voorbeeldbestanden, leert u deze om te zoeken naar kenmerken die specifiek zijn voor wat u zou zien in de contracten van uw bedrijf.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-116">By training the classifier with your example files, you teach it to search for characteristics that are specific to what you would see in your company's contracts.</span></span> <span data-ttu-id="0b7c1-117">Maak bijvoorbeeld [een 'uitleg'](create-a-classifier.md#create-an-explanation) waarin wordt gezocht naar specifieke tekenreeksen die in uw contracten staan, zoals *Serviceovereenkomst,* Overeenkomstsvoorwaarden en  *Compensatie.*</span><span class="sxs-lookup"><span data-stu-id="0b7c1-117">For example, [create an "explanation"](create-a-classifier.md#create-an-explanation) that searches for specific strings that are in your contracts, such as *Service Agreement*, *Terms of Agreement*, and *Compensation*.</span></span> <span data-ttu-id="0b7c1-118">U kunt zelfs uw uitleg trainen om te zoeken naar deze tekenreeksen in specifieke secties van het document of naast andere tekenreeksen.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-118">You can even train your explanation to look for these strings in specific sections of the document, or located next to other strings.</span></span> <span data-ttu-id="0b7c1-119">Wanneer u denkt dat u uw classificatie hebt opgeleid met de informatie die het nodig heeft, kunt u uw model testen op een voorbeeldset met voorbeeldbestanden om te zien hoe efficiënt het is.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-119">When you think you have trained your classifier with the information it needs, you can test your model on a sample set of example files to see how efficient it is.</span></span> <span data-ttu-id="0b7c1-120">Na het testen kunt u indien nodig wijzigingen aanbrengen in uw uitleg om ze efficiënter te maken.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-120">After testing, if needed you can choose to make changes to your explanations to make them more efficient.</span></span> 

3. <span data-ttu-id="0b7c1-121">In uw model kunt u [een extractor](create-an-extractor.md) maken om specifieke gegevens uit elk contract te halen.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-121">In your model, you can [create an extractor](create-an-extractor.md) to pull out specific pieces of data from each contract.</span></span> <span data-ttu-id="0b7c1-122">Voor elk contract is de informatie waar u zich het meest zorgen over maakt bijvoorbeeld wie de klant is, de naam van de contractant en de totale kosten.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-122">For example, for each contract, the information you're most concerned about is who the client is, the name of the contractor, and the total cost.</span></span>

4. <span data-ttu-id="0b7c1-123">Nadat u het model hebt gemaakt, kunt u het toepassen [op een SharePoint documentbibliotheek.](apply-a-model.md)</span><span class="sxs-lookup"><span data-stu-id="0b7c1-123">After you successfully create your model, [apply it to a SharePoint document library](apply-a-model.md).</span></span> <span data-ttu-id="0b7c1-124">Wanneer u documenten uploadt naar de documentbibliotheek, wordt uw documentkennismodel uitgevoerd en worden alle bestanden die overeenkomen met het inhoudstype contracten dat u in uw model hebt gedefinieerd, identificeren en classificeren.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-124">As you upload documents to the document library, your document understanding model will run and will identify and classify all files that match the contracts content type you defined in your model.</span></span> <span data-ttu-id="0b7c1-125">Alle bestanden die als contracten zijn geclassificeerd, worden weergegeven in een aangepaste bibliotheekweergave.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-125">All files that are classified as contracts will display in a custom library view.</span></span> <span data-ttu-id="0b7c1-126">In de bestanden worden ook de waarden weergegeven van elk contract dat u hebt gedefinieerd in de extractor.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-126">The files will also display the values from each contract that you defined in your extractor.</span></span>

   ![Contracten in documentbibliotheek](../media/content-understanding/doc-lib-solution.png)

5. <span data-ttu-id="0b7c1-128">Als u bewaar- of beveiligingsvereisten voor uw contracten hebt, [](apply-a-retention-label-to-a-model.md) kunt u [](apply-a-sensitivity-label-to-a-model.md) uw model ook gebruiken om een bewaarlabel of een gevoeligheidslabel toe te passen waardoor uw contracten niet voor een bepaalde periode worden verwijderd of om te beperken wie toegang heeft tot de contracten.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-128">If you have retention or security requirements for your contracts, you can also use your model to apply a [retention label](apply-a-retention-label-to-a-model.md) or a [sensitivity label](apply-a-sensitivity-label-to-a-model.md) that will prevent your contracts from being deleted for a specified period of time or to restrict who can access the contracts.</span></span>

## <a name="steps-to-create-and-train-your-model"></a><span data-ttu-id="0b7c1-129">Stappen voor het maken en trainen van uw model</span><span class="sxs-lookup"><span data-stu-id="0b7c1-129">Steps to create and train your model</span></span>

> [!NOTE]
> <span data-ttu-id="0b7c1-130">Voor deze stappen kunt u de voorbeeldbestanden gebruiken in de [opslagplaats Voor oplossingsactiva voor contractenbeheer.](https://github.com/pnp/syntex-samples/tree/main/scenario%20assets/Contracts%20Management)</span><span class="sxs-lookup"><span data-stu-id="0b7c1-130">For these steps, you can use the example files in the [Contracts Management Solution Assets repository](https://github.com/pnp/syntex-samples/tree/main/scenario%20assets/Contracts%20Management).</span></span> <span data-ttu-id="0b7c1-131">De voorbeelden in deze opslagplaats bevatten zowel de documentkennis van modelbestanden als de bestanden die worden gebruikt om het model te trainen.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-131">The examples in this repository contain both the document understanding model files and the files used to train the model.</span></span>

### <a name="create-a-contract-model"></a><span data-ttu-id="0b7c1-132">Een contractmodel maken</span><span class="sxs-lookup"><span data-stu-id="0b7c1-132">Create a Contract model</span></span>

<span data-ttu-id="0b7c1-133">De eerste stap is het maken van uw contractmodel.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-133">The first step is to create your Contract model.</span></span>

1. <span data-ttu-id="0b7c1-134">Selecteer in het Inhoudscentrum **Nieuw** en klik vervolgens **Maak een model**.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-134">From the content center, select **New**, and then **Create a model**.</span></span>

2. <span data-ttu-id="0b7c1-135">Typ in **het deelvenster Nieuw documenttypemodel** in het veld **Naam** de naam van het model.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-135">On the **New document understanding model** pane, in the **Name** field, type the name of the model.</span></span> <span data-ttu-id="0b7c1-136">Voor deze oplossing voor contractbeheer kunt u het modelContract een naam *geven.*</span><span class="sxs-lookup"><span data-stu-id="0b7c1-136">For this contract management solution, you can name the model *Contract*.</span></span>

4. <span data-ttu-id="0b7c1-137">Kies **Create**.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-137">Choose **Create**.</span></span> <span data-ttu-id="0b7c1-138">Hiermee maa je een startpagina voor het model.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-138">This creates a home page for the model.</span></span></br>

    ![Schermafbeelding van de startpagina contract.](../media/content-understanding/models-contract-home-page.png)


### <a name="train-your-model-to-classify-a-type-of-file"></a><span data-ttu-id="0b7c1-140">Uw model trainen om een type bestand te classificeren</span><span class="sxs-lookup"><span data-stu-id="0b7c1-140">Train your model to classify a type of file</span></span>

#### <a name="add-example-files-for-your-model"></a><span data-ttu-id="0b7c1-141">Voorbeeldbestanden voor uw model toevoegen</span><span class="sxs-lookup"><span data-stu-id="0b7c1-141">Add example files for your model</span></span>

<span data-ttu-id="0b7c1-142">U moet ten minste vijf voorbeeldbestanden toevoegen die contractdocumenten zijn en één voorbeeldbestand dat geen contractdocument is (bijvoorbeeld een werkoverzicht).</span><span class="sxs-lookup"><span data-stu-id="0b7c1-142">You need to add at least five example files that are contract documents, and one example file that's not a contract document (for example, a statement of work).</span></span> 

1. <span data-ttu-id="0b7c1-143">Selecteer op **de pagina > Contract** onder Belangrijke **acties**  >  **Voorbeeldbestanden** toevoegen de optie **Bestanden toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="0b7c1-143">On the **Models > Contract** page, under **Key actions** > **Add example files**, select **Add files**.</span></span>

   ![Schermafbeelding met de pagina Contracten met de optie Voorbeeldbestanden toevoegen gemarkeerd.](../media/content-understanding/key-actions-add-example-files.png)

2. <span data-ttu-id="0b7c1-145">Open op **de pagina Voorbeeldbestanden selecteren** voor uw model de map Contract, selecteer bestanden die u wilt gebruiken en selecteer vervolgens **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="0b7c1-145">On the **Select example files for your model** page, open the Contract folder, select files you want to use, and then select **Add**.</span></span> <span data-ttu-id="0b7c1-146">Als u daar geen voorbeeldbestanden hebt, selecteert **u Upload** om ze toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-146">If you don't have example files there, select **Upload** to add them.</span></span>

#### <a name="label-the-files-as-positive-or-negative-examples"></a><span data-ttu-id="0b7c1-147">De bestanden labelen als positieve of negatieve voorbeelden</span><span class="sxs-lookup"><span data-stu-id="0b7c1-147">Label the files as positive or negative examples</span></span>

1. <span data-ttu-id="0b7c1-148">Selecteer op **de pagina > Contract** onder Belangrijke **acties** Bestanden classificeren en  >  **training** uitvoeren de optie **Train classifier**.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-148">On the **Models > Contract** page, under **Key actions** > **Classify files and run training**, select **Train classifier**.</span></span>

   ![Schermafbeelding met de pagina Contracten met Bestanden classificeren en trainingsoptie uitvoeren gemarkeerd.](../media/content-understanding/key-actions-classify-files.png)

2. <span data-ttu-id="0b7c1-150">Op de pagina > **Contract > Contract classifier** ziet u in de viewer boven aan het eerste voorbeeldbestand tekst met de vraag of het bestand een voorbeeld is van het contractmodel dat u hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-150">On the **Models > Contract > Contract classifier** page, in the viewer on the top of the first example file, you'll see text asking if the file is an example of the Contract model you created.</span></span> <span data-ttu-id="0b7c1-151">Als het om een positief voorbeeld gaat, selecteer je **Ja**.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-151">If it is a positive example, select **Yes**.</span></span> <span data-ttu-id="0b7c1-152">Als het om een negatief voorbeeld gaat, selecteer je **Nee**.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-152">If it is a negative example, select **No**.</span></span>

3. <span data-ttu-id="0b7c1-153">Selecteer in **de lijst Gelabelde** voorbeelden aan de linkerkant andere bestanden die u als voorbeelden wilt gebruiken en label ze.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-153">From the **Labeled examples** list on the left, select other files that you want to use as examples, and label them.</span></span> 

    ![Startpagina voor classificatie](../media/content-understanding/models-contract-classifier.png) 

#### <a name="add-at-least-one-explanation-to-train-the-classifier"></a><span data-ttu-id="0b7c1-155">Voeg ten minste één uitleg toe om de classificatie te trainen</span><span class="sxs-lookup"><span data-stu-id="0b7c1-155">Add at least one explanation to train the classifier</span></span> 

1. <span data-ttu-id="0b7c1-156">Selecteer op **de pagina > contract > de pagina Contractclassifier** het **tabblad** Trein.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-156">On the **Models > Contract > Contract classifier** page, select the **Train** tab.</span></span>

2. <span data-ttu-id="0b7c1-157">In de **sectie Getrainde** bestanden ziet u een lijst met de voorbeeldbestanden die u eerder hebt gelabeld.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-157">In the **Trained files** section, you'll see a list of the example files that you previously labeled.</span></span> <span data-ttu-id="0b7c1-158">Selecteer een van de positieve bestanden in de lijst om deze weer te geven in de viewer.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-158">Select one of the positive files from the list to display it in the viewer.</span></span>

3. <span data-ttu-id="0b7c1-159">Selecteer in **de sectie Uitleg** de optie **Nieuw** en vervolgens **Leeg.**</span><span class="sxs-lookup"><span data-stu-id="0b7c1-159">In the **Explanations** section, select **New** and then **Blank**.</span></span>

4. <span data-ttu-id="0b7c1-160">Op de pagina **Maak een uitleg**:</span><span class="sxs-lookup"><span data-stu-id="0b7c1-160">On the **Create an explanation** page:</span></span>

    <span data-ttu-id="0b7c1-161">a.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-161">a.</span></span> <span data-ttu-id="0b7c1-162">Typ in **het** veld Naam de naam van de uitleg (zoals 'Overeenkomst').</span><span class="sxs-lookup"><span data-stu-id="0b7c1-162">In the **Name** field, type the name of the explanation (such as "Agreement").</span></span>

    <span data-ttu-id="0b7c1-163">b.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-163">b.</span></span> <span data-ttu-id="0b7c1-164">Selecteer in **het veld Uitlegtype** de optie **Lijst Woordgroep** omdat u een tekenreeks toevoegt.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-164">In the **Explanation type** field, select **Phrase list**, because you add a text string.</span></span>

    <span data-ttu-id="0b7c1-165">c.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-165">c.</span></span> <span data-ttu-id="0b7c1-166">Typ in **de lijst Woordgroep** de tekenreeks (zoals 'OVEREENKOMST').</span><span class="sxs-lookup"><span data-stu-id="0b7c1-166">In the **Phrase list** box, type the string (such as "AGREEMENT").</span></span> <span data-ttu-id="0b7c1-167">U kunt Case **sensitive selecteren** als de tekenreeks case-sensitive moet zijn.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-167">You can select **Case sensitive** if the string needs to be case-sensitive.</span></span>

    <span data-ttu-id="0b7c1-168">d.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-168">d.</span></span> <span data-ttu-id="0b7c1-169">Selecteer **Opslaan en trainen.**</span><span class="sxs-lookup"><span data-stu-id="0b7c1-169">Select **Save and train**.</span></span>

    ![Schermafbeelding van het deelvenster Uitleg maken.](../media/content-understanding/contract-classifier-create-explanation.png) 

#### <a name="test-your-model"></a><span data-ttu-id="0b7c1-171">Test je model.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-171">Test your model</span></span>

<span data-ttu-id="0b7c1-172">U kunt uw contractmodel testen op voorbeeldbestanden die u nog niet eerder hebt gezien.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-172">You can test your Contract model on example files it hasn’t seen before.</span></span> <span data-ttu-id="0b7c1-173">Dit is optioneel, maar kan handig zijn.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-173">This is optional, but it can be a useful best practice.</span></span>

1. <span data-ttu-id="0b7c1-174">Selecteer op **de pagina > Contract > contractclassifier** het **tabblad** Testen. Hiermee wordt het model uitgevoerd op uw voorbeeldbestanden zonder label.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-174">On the **Models > Contract > Contract classifier** page, select the **Test** tab. This runs the model on your unlabeled example files.</span></span>

2. <span data-ttu-id="0b7c1-175">In de **lijst Testbestanden** worden uw voorbeeldbestanden weergegeven en wordt weergegeven of het model voorspelde dat ze positief of negatief waren.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-175">In the **Test Files** list, your example files display and shows if the model predicted them to be positive or negative.</span></span> <span data-ttu-id="0b7c1-176">Gebruik deze informatie om de effectiviteit van je classificatie bij het identificeren van je documenten vast te stellen.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-176">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![Schermafbeelding van de niet-gemarkeerde bestanden in de lijst Tekstbestanden](../media/content-understanding/test-on-files.png) 

3. <span data-ttu-id="0b7c1-178">Wanneer u klaar bent, **selecteert u Training afsluiten.**</span><span class="sxs-lookup"><span data-stu-id="0b7c1-178">When done, select **Exit Training**.</span></span>

### <a name="create-and-train-an-extractor"></a><span data-ttu-id="0b7c1-179">Een extractor maken en trainen</span><span class="sxs-lookup"><span data-stu-id="0b7c1-179">Create and train an extractor</span></span>

1. <span data-ttu-id="0b7c1-180">Selecteer op **de pagina >** contract onder Belangrijke acties Extractoren maken en trainen de optie  >   **Extractor maken.**</span><span class="sxs-lookup"><span data-stu-id="0b7c1-180">On the **Models > Contract** page, under **Key actions** > **Create and train extractors**, select **Create extractor**.</span></span>

   ![Schermafbeelding met de pagina Contracten met de optie Extractoren maken en trainen gemarkeerd.](../media/content-understanding/key-actions-create-extractors.png)

2. <span data-ttu-id="0b7c1-182">Typ in **het deelvenster Nieuwe entiteitsextractor** in het veld **Nieuwe** naam de naam van de extractor.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-182">On the **New entity extractor** panel, in the **New name** field, type the name of your extractor.</span></span> <span data-ttu-id="0b7c1-183">Noem de client bijvoorbeeld *Client als* u de naam van de client uit elk contract wilt oppakken.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-183">For example, name it *Client* if you want to extract the name of the client from each contract.</span></span>

3. <span data-ttu-id="0b7c1-184">Wanneer u klaar bent, selecteert u **Maken.**</span><span class="sxs-lookup"><span data-stu-id="0b7c1-184">When you're done, select **Create**.</span></span>

#### <a name="label-the-entity-you-want-to-extract"></a><span data-ttu-id="0b7c1-185">Label de entiteit die u wilt oppakken</span><span class="sxs-lookup"><span data-stu-id="0b7c1-185">Label the entity you want to extract</span></span>

<span data-ttu-id="0b7c1-186">Wanneer u de extractor maakt, wordt de extractorpagina geopend.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-186">When you create the extractor, the extractor page opens.</span></span> <span data-ttu-id="0b7c1-187">Hier zie je een lijst met je voorbeeldbestanden, met het eerste bestand in de lijst die wordt weergegeven in de viewer.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-187">Here you see a list of your sample files, with the first file on the list displayed in the viewer.</span></span>

![Schermafbeelding van de pagina Voorbeelden van clientextractor Labeled.](../media/content-understanding/client-extractor-labeled-examples.png) 

<span data-ttu-id="0b7c1-189">De entiteit een label geven:</span><span class="sxs-lookup"><span data-stu-id="0b7c1-189">To label the entity:</span></span>

1. <span data-ttu-id="0b7c1-190">Selecteer in de viewer de gegevens die je wilt ophalen uit de bestanden.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-190">From the viewer, select the data that you want to extract from the files.</span></span> <span data-ttu-id="0b7c1-191">Als u bijvoorbeeld de client wilt extraheren, markeert u de clientwaarde in het eerste bestand (in dit voorbeeld *Best For You Organics)* en selecteert u **Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="0b7c1-191">For example, if you want to extract the *Client*, you highlight the client value in the first file (in this example, *Best For You Organics*), and then select **Save**.</span></span> <span data-ttu-id="0b7c1-192">U ziet de waardeweergave van het bestand in de lijst **Gelabelde** voorbeelden, onder de **kolom** Label.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-192">You'll see the value display from the file in the **Labeled examples** list, under the **Label** column.</span></span>

2. <span data-ttu-id="0b7c1-193">Selecteer **Volgende bestand** om het volgende bestand in de lijst in de viewer automatisch op te geven en te openen.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-193">Select **Next file** to autosave and open the next file in the list in the viewer.</span></span> <span data-ttu-id="0b7c1-194">Of selecteer **Opslaan** en selecteer vervolgens een ander bestand in de **lijst Gelabelde** voorbeelden.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-194">Or select **Save**, and then select another file from the **Labeled examples** list.</span></span>

3. <span data-ttu-id="0b7c1-195">Herhaal in de viewer stap 1 en 2 en herhaal dit totdat u het label in alle bestanden hebt opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-195">In the viewer, repeat steps 1 and 2, then repeat until you saved the label in all the files.</span></span>

<span data-ttu-id="0b7c1-196">Nadat u de bestanden hebt gelabeld, wordt er een meldingsbanner weergegeven met de mededeling dat u naar de training moet gaan.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-196">After you've labeled the files, a notification banner displays informing you to move to training.</span></span> <span data-ttu-id="0b7c1-197">U kunt ervoor kiezen om meer documenten te labelen of door te gaan naar de training.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-197">You can choose to label more documents or advance to training.</span></span>

#### <a name="add-an-explanation"></a><span data-ttu-id="0b7c1-198">Voeg een uitleg toe</span><span class="sxs-lookup"><span data-stu-id="0b7c1-198">Add an explanation</span></span>

<span data-ttu-id="0b7c1-199">U kunt een uitleg maken waarin een hint wordt gegeven over de entiteitsindeling zelf en variaties in de voorbeeldbestanden.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-199">You can create an explanation that provides a hint about the entity format itself and variations it might have in the example files.</span></span> <span data-ttu-id="0b7c1-200">Een datumwaarde kan bijvoorbeeld in veel verschillende indelingen zijn, zoals:</span><span class="sxs-lookup"><span data-stu-id="0b7c1-200">For example, a date value can be in many different formats, such as:</span></span>

- <span data-ttu-id="0b7c1-201">10/14/2019</span><span class="sxs-lookup"><span data-stu-id="0b7c1-201">10/14/2019</span></span>
- <span data-ttu-id="0b7c1-202">14 oktober 2019</span><span class="sxs-lookup"><span data-stu-id="0b7c1-202">October 14, 2019</span></span>
- <span data-ttu-id="0b7c1-203">Maandag 14 oktober 2019</span><span class="sxs-lookup"><span data-stu-id="0b7c1-203">Monday, October 14, 2019</span></span>

<span data-ttu-id="0b7c1-204">Als u de begindatum *van het contract wilt identificeren,* kunt u een patroonverklaring maken.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-204">To help identify the *Contract Start Date*, you can create a pattern explanation.</span></span>

1. <span data-ttu-id="0b7c1-205">Selecteer in **de sectie Uitleg** de optie **Nieuw** en vervolgens **Leeg.**</span><span class="sxs-lookup"><span data-stu-id="0b7c1-205">In the **Explanations** section, select **New** and then **Blank**.</span></span>

2. <span data-ttu-id="0b7c1-206">Op de pagina **Maak een uitleg**:</span><span class="sxs-lookup"><span data-stu-id="0b7c1-206">On the **Create an explanation** page:</span></span>

    <span data-ttu-id="0b7c1-207">a.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-207">a.</span></span> <span data-ttu-id="0b7c1-208">Typ in **het** veld Naam de naam van de uitleg (zoals *Datum).*</span><span class="sxs-lookup"><span data-stu-id="0b7c1-208">In the **Name** field, type the name of the explanation (such as *Date*).</span></span>

    <span data-ttu-id="0b7c1-209">b.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-209">b.</span></span> <span data-ttu-id="0b7c1-210">Selecteer in **het veld Uitlegtype** **de optie Patroonlijst**.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-210">In the **Explanation type** field, select **Pattern list**.</span></span>

    <span data-ttu-id="0b7c1-211">c.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-211">c.</span></span> <span data-ttu-id="0b7c1-212">Geef in **het** veld Waarde de datumvariatie op zoals deze worden weergegeven in de voorbeeldbestanden.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-212">In the **Value** field, provide the date variation as they appear in the sample files.</span></span> <span data-ttu-id="0b7c1-213">Als je bijvoorbeeld datumnotaties hebt die worden weergegeven als 0/00/0000, geef je de variaties op die worden weergegeven in je documenten, zoals:</span><span class="sxs-lookup"><span data-stu-id="0b7c1-213">For example, if you have date formats that appear as 0/00/0000, you enter any variations that appear in your documents, such as:</span></span>

    - <span data-ttu-id="0b7c1-214">0/0/0000</span><span class="sxs-lookup"><span data-stu-id="0b7c1-214">0/0/0000</span></span>
    - <span data-ttu-id="0b7c1-215">0/00/0000</span><span class="sxs-lookup"><span data-stu-id="0b7c1-215">0/00/0000</span></span>
    - <span data-ttu-id="0b7c1-216">00/0/0000</span><span class="sxs-lookup"><span data-stu-id="0b7c1-216">00/0/0000</span></span>
    - <span data-ttu-id="0b7c1-217">00/00/0000</span><span class="sxs-lookup"><span data-stu-id="0b7c1-217">00/00/0000</span></span>

4. <span data-ttu-id="0b7c1-218">Selecteer **Opslaan en trainen.**</span><span class="sxs-lookup"><span data-stu-id="0b7c1-218">Select **Save and train**.</span></span>

#### <a name="test-your-model-again"></a><span data-ttu-id="0b7c1-219">Test uw model opnieuw</span><span class="sxs-lookup"><span data-stu-id="0b7c1-219">Test your model again</span></span>

<span data-ttu-id="0b7c1-220">U kunt uw contractmodel testen op voorbeeldbestanden die u nog niet eerder hebt gezien.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-220">You can test your Contract model on example files it hasn’t seen before.</span></span> <span data-ttu-id="0b7c1-221">Dit is optioneel, maar kan handig zijn.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-221">This is optional, but it can be a useful best practice.</span></span>

1. <span data-ttu-id="0b7c1-222">Selecteer op **de pagina > Contract > contractclassifier** het **tabblad** Testen. Hiermee wordt het model uitgevoerd op uw voorbeeldbestanden zonder label.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-222">On the **Models > Contract > Contract classifier** page, select the **Test** tab. This runs the model on your unlabeled example files.</span></span>

2. <span data-ttu-id="0b7c1-223">In de **lijst Testbestanden** worden uw voorbeeldbestanden weergegeven en wordt weergegeven of het model de gegevens kan oppakken die u nodig hebt.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-223">In the **Test files** list, your example files display and shows if the model is able to extract the information you need.</span></span> <span data-ttu-id="0b7c1-224">Gebruik deze informatie om de effectiviteit van je classificatie bij het identificeren van je documenten vast te stellen.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-224">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

3. <span data-ttu-id="0b7c1-225">Wanneer u klaar bent, **selecteert u Training afsluiten.**</span><span class="sxs-lookup"><span data-stu-id="0b7c1-225">When done, select **Exit Training**.</span></span>

### <a name="apply-your-model-to-a-document-library"></a><span data-ttu-id="0b7c1-226">Uw model toepassen op een documentbibliotheek</span><span class="sxs-lookup"><span data-stu-id="0b7c1-226">Apply your model to a document library</span></span>

<span data-ttu-id="0b7c1-227">Als u uw model wilt toepassen op een SharePoint documentbibliotheek:</span><span class="sxs-lookup"><span data-stu-id="0b7c1-227">To apply your model to a SharePoint document library:</span></span>

1. <span data-ttu-id="0b7c1-228">Selecteer op **de pagina > Contract** onder Sleutelacties Model toepassen op   >  **bibliotheken** de optie Model **toepassen.**</span><span class="sxs-lookup"><span data-stu-id="0b7c1-228">On the **Models > Contract** page, under **Key actions** > **Apply model to libraries**, select **Apply model**.</span></span>

   ![Schermafbeelding met de pagina Contracten met de optie Model toepassen op bibliotheken gemarkeerd.](../media/content-understanding/key-actions-apply-model.png)

2. <span data-ttu-id="0b7c1-230">Selecteer in **het deelvenster Contract** toevoegen de SharePoint site met de documentbibliotheek waarin u het model wilt toepassen.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-230">On the **Add Contract** panel, select the SharePoint site that contains the document library that you want to apply the model to.</span></span> <span data-ttu-id="0b7c1-231">Als de site niet in de lijst wordt weergegeven, gebruikt u het zoekvak om de site te vinden.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-231">If the site does not show in the list, use the search box to find it.</span></span> <span data-ttu-id="0b7c1-232">Kies **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-232">Select **Add**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0b7c1-233">U moet beschikken over de machtiging *Lijst beheren* of *Machtiging voor bewerken* voor de documentbibliotheek waarop u het model toepast.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-233">You must have *Manage List* permissions or *Edit* rights to the document library you are applying the model to.</span></span>

3. <span data-ttu-id="0b7c1-234">Nadat u de site hebt geselecteerd, selecteert u de documentbibliotheek waarop u het model wilt toepassen.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-234">After you select the site, select the document library to which you want to apply the model.</span></span>

4. <span data-ttu-id="0b7c1-235">Omdat het model is gekoppeld aan een inhoudstype, wordt het inhoudstype en de weergave ervan toegevoegd wanneer u dit op de bibliotheek toevoegt, met de labels die u hebt geëxtraheerd en die als kolommen worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-235">Because the model is associated to a content type, when you apply it to the library it will add the content type and its view with the labels you extracted showing as columns.</span></span> <span data-ttu-id="0b7c1-236">Deze weergave is standaard de standaardweergave van de bibliotheek, maar u kunt er  desgewenst voor kiezen deze weergave niet de standaardweergave te laten zijn door Geavanceerde instellingen te selecteren en het selectievakje Deze nieuwe weergave als standaard instellen uit **te** sluiten.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-236">This view is the library's default view by default, but you can optionally choose to have it not be the default view by selecting **Advanced settings** and clearing the **Set this new view as default** check box.</span></span>

5. <span data-ttu-id="0b7c1-237">Selecteer **Toevoegen** om het model toe te passen op de bibliotheek.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-237">Select **Add** to apply the model to the library.</span></span>

6. <span data-ttu-id="0b7c1-238">Op de **pagina > contract** ziet u in de sectie Bibliotheken met dit **model** de URL naar de SharePoint site.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-238">On the **Models > Contract** page, in the **Libraries with this model** section, you'll see the URL to the SharePoint site listed.</span></span>

    ![Schermafbeelding van de startpagina Contract met de sectie Bibliotheken met dit model.](../media/content-understanding/contract-libraries-with-this-model.png)

7. <span data-ttu-id="0b7c1-240">Onder **Instellingen**  >  **Bibliotheekinstellingen:**</span><span class="sxs-lookup"><span data-stu-id="0b7c1-240">Under **Settings** > **Library settings**:</span></span>

   - <span data-ttu-id="0b7c1-241">Voeg een kolom met de naam **Status** toe en **selecteer Keuze** als kolomtype.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-241">Add a column named **Status** and select **Choice** as the column type.</span></span>
   - <span data-ttu-id="0b7c1-242">Pas de **waarden In revisie,** **Goedgekeurd** en **Geweigerd** toe.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-242">Apply the **In review**, **Approved**, and **Rejected** values.</span></span>

<span data-ttu-id="0b7c1-243">Nadat u het model hebt toegepast op de documentbibliotheek, kunt u beginnen met het uploaden van documenten naar de site en de resultaten bekijken.</span><span class="sxs-lookup"><span data-stu-id="0b7c1-243">After you apply the model to the document library, you can begin uploading documents to the site and see the results.</span></span>

## <a name="next-step"></a><span data-ttu-id="0b7c1-244">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="0b7c1-244">Next step</span></span>

[<span data-ttu-id="0b7c1-245">Stap 2. Gebruik Microsoft Teams om uw contractbeheerkanaal te maken</span><span class="sxs-lookup"><span data-stu-id="0b7c1-245">Step 2. Use Microsoft Teams to create your contract management channel</span></span>](solution-manage-contracts-step2.md)