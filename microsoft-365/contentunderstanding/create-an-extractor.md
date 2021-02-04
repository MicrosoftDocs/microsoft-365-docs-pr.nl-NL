---
title: Een extractor maken
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
description: Lees hoe je een Extractor kunt maken in Microsoft SharePoint Syntex.
ms.openlocfilehash: dd26b049f71688804cd5110a5a0bb7c87950be94
ms.sourcegitcommit: d354727303d9574991b5a0fd298d2c9414e19f6c
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/02/2021
ms.locfileid: "50080483"
---
# <a name="create-an-extractor-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="955e9-103">Maak een Extractor in Microsoft SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="955e9-103">Create an extractor in Microsoft SharePoint Syntex</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL2G]

</br> 

<span data-ttu-id="955e9-104">Vóór of na het maken van een classificatiemodel voor het automatiseren van de identificatie en classificatie van specifieke documenttypen, kun je desgewenst extra uittreksels toevoegen aan je model om specifieke informatie uit deze documenten te halen.</span><span class="sxs-lookup"><span data-stu-id="955e9-104">Before or after you create a classifier model to automate identification and classification of specific document types, you can optionally choose to add extractors to your model to pull out specific information from these documents.</span></span> <span data-ttu-id="955e9-105">Het is bijvoorbeeld mogelijk dat je wilt dat je model niet alleen wordt herkend aan *alle* documenten die worden toegevoegd aan de documentbibliotheek, maar je kunt ook de *service-begindatum* voor elk document weergeven als een kolomwaarde in de documentbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="955e9-105">For example, you may want your model not only to identify all *Contract Renewal* documents added to your document library, but also to display the *Service Start date* for each document as a column value in the document library.</span></span>

<span data-ttu-id="955e9-106">Je moet een extractor maken voor elke entiteit in het document die je wilt ophalen.</span><span class="sxs-lookup"><span data-stu-id="955e9-106">You need to create an extractor for each entity in the document that you want to extract.</span></span> <span data-ttu-id="955e9-107">In ons voorbeeld willen we de  **begindatum van de service** extraheren voor elke  **contractvernieuwing** -document dat door het model wordt geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="955e9-107">In our example, we want to extract the **Service Start Date** for each **Contract Renewal** document that is identified by the model.</span></span> <span data-ttu-id="955e9-108">We willen een weergave kunnen zien in de documentbibliotheek van alle  **contract** documenten, met een kolom waarin de **begindatum van de service** van elk document wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="955e9-108">We want to be able to see a view in the document library of all  **Contract Renewal** documents, with a column that shows the **Service Start** date value of each document.</span></span> 

> [!NOTE]
> <span data-ttu-id="955e9-109">Als je een extractor wilt maken, gebruik je dezelfde bestanden die je eerder hebt geüpload om de classificatie te trainen.</span><span class="sxs-lookup"><span data-stu-id="955e9-109">In order to create an extractor, you use the same files you previously uploaded to train the classifier.</span></span> 

## <a name="name-your-extractor"></a><span data-ttu-id="955e9-110">Een naam voor de Extractor geven</span><span class="sxs-lookup"><span data-stu-id="955e9-110">Name your extractor</span></span>

1. <span data-ttu-id="955e9-111">Klik op de startpagina van het model op **Train Extractor** in de tegel **Extractor maken en trainen**.</span><span class="sxs-lookup"><span data-stu-id="955e9-111">From the model home page, in the **Create and train extractors** tile, click **Train extractor**.</span></span>
2. <span data-ttu-id="955e9-112">Typ in het scherm **New entiteit Extractor** de naam van je extractor in het veld **Nieuwe extractorname**.</span><span class="sxs-lookup"><span data-stu-id="955e9-112">On the **New entity extractor** screen, type the name of your extractor in the **New extractor name** field.</span></span> <span data-ttu-id="955e9-113">Als je bijvoorbeeld de **begindatum van de service** wilt wijzigen als je de begindatum van de service wilt ophalen uit elk document voor het verlengen van een contract.</span><span class="sxs-lookup"><span data-stu-id="955e9-113">For example, name it **Service Start Date** if you want to extract the service start date from each Contract Renewal document.</span></span> <span data-ttu-id="955e9-114">Je kunt er ook voor kiezen om een eerder gemaakte kolom opnieuw te gebruiken (bijvoorbeeld een kolom met beheerde metagegevens).</span><span class="sxs-lookup"><span data-stu-id="955e9-114">You can also choose to reuse a previously created column (for example, a managed metadata column).</span></span>
> [!NOTE]
> <span data-ttu-id="955e9-115">Als je een nieuwe extractor maakt, selecteer dan **Nieuwe kolomtype** en kies **Enkele tekstregel**. Het maximumaantal tekens is 255.</span><span class="sxs-lookup"><span data-stu-id="955e9-115">If you create a new extractor, then select **New column type** and choose **Single line of text**, the maximum character limit is 255.</span></span> <span data-ttu-id="955e9-116">Alle tekens die de limiet overschrijden worden afgebroken.</span><span class="sxs-lookup"><span data-stu-id="955e9-116">Any characters that you type exceeding the limit get truncated.</span></span> 
3. <span data-ttu-id="955e9-117">Klik op **Maken** wanneer je klaar bent.</span><span class="sxs-lookup"><span data-stu-id="955e9-117">When you're done, click **Create**.</span></span>

## <a name="add-a-label"></a><span data-ttu-id="955e9-118">Een label toevoegen</span><span class="sxs-lookup"><span data-stu-id="955e9-118">Add a label</span></span>

<span data-ttu-id="955e9-119">De volgende stap bestaat uit het label van de entiteit die je wilt ophalen in de voorbeeldbestanden van de training.</span><span class="sxs-lookup"><span data-stu-id="955e9-119">The next step is to label the entity you want to extract in your example training files.</span></span>

<span data-ttu-id="955e9-120">Als je de Extractor maakt, wordt de extractor-pagina geopend.</span><span class="sxs-lookup"><span data-stu-id="955e9-120">Creating the extractor opens the extractor page.</span></span> <span data-ttu-id="955e9-121">Hier zie je een lijst met je voorbeeldbestanden, met het eerste bestand in de lijst die wordt weergegeven in de viewer.</span><span class="sxs-lookup"><span data-stu-id="955e9-121">Here you see a list of your sample files, with the first file on the list displayed in the viewer.</span></span>

1. <span data-ttu-id="955e9-122">Selecteer in de viewer de gegevens die je wilt ophalen uit de bestanden.</span><span class="sxs-lookup"><span data-stu-id="955e9-122">From the viewer, select the data that you want to extract from the files.</span></span> <span data-ttu-id="955e9-123">Als je bijvoorbeeld de *begindatum van service* wilt ophalen, markeer je de datumwaarde in het eerste bestand (*maandag, 14 oktober 2019*).</span><span class="sxs-lookup"><span data-stu-id="955e9-123">For example, if you want to extract the *Start Service Date*, you highlight the date value in the first file (*Monday, October 14, 2019*).</span></span> <span data-ttu-id="955e9-124">en klik dan op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="955e9-124">and then click **Save**.</span></span>  <span data-ttu-id="955e9-125">De weergave van de waarde wordt weergegeven in het bestand in de lijst voorbeelden met een bijschrift onder de **labelkolom**.</span><span class="sxs-lookup"><span data-stu-id="955e9-125">You should see the value display from the file in the Labeled examples list, under the **Label** column.</span></span>
2. <span data-ttu-id="955e9-126">Selecteer **Volgende bestand** om automatisch op te slaan en het volgende bestand te openen in de lijst in de viewer.</span><span class="sxs-lookup"><span data-stu-id="955e9-126">Select **Next file** to auto save and open the next file in the list in the viewer.</span></span> <span data-ttu-id="955e9-127">Of selecteer **Opslaan** en selecteer een ander bestand van de lijst **Gelabelde voorbeelden**.</span><span class="sxs-lookup"><span data-stu-id="955e9-127">Or select **Save** and then select another file from the **Labeled examples** list.</span></span>
3. <span data-ttu-id="955e9-128">Herhaal stap 1 en 2 in de viewer en herhaal dit totdat je het label in alle vijf bestanden hebt opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="955e9-128">In the viewer, repeat steps 1 and 2, then repeat until you saved the label in all five files.</span></span>

    ![Geavanceerde instellingen](../media/content-understanding/select-service-start-date.png) 

 
<span data-ttu-id="955e9-130">Wanneer je vijf bestanden hebt voorzien van een label, wordt een melding weergegeven met de mededeling dat je wilt overstappen op de training.</span><span class="sxs-lookup"><span data-stu-id="955e9-130">Once you labeled five files, a notification banner displays informing you to move to training.</span></span> <span data-ttu-id="955e9-131">Je kunt ervoor kiezen om meer documenten beter te labelen of verder te gaan met de training.</span><span class="sxs-lookup"><span data-stu-id="955e9-131">You can choose to more label more documents or advance to training.</span></span> 

### <a name="use-find-to-search-your-file"></a><span data-ttu-id="955e9-132">Zoeken gebruiken om in je bestand te zoeken</span><span class="sxs-lookup"><span data-stu-id="955e9-132">Use Find to search your file</span></span>
<span data-ttu-id="955e9-133">Je kunt de functie <b>Zoeken</b> gebruiken om te zoeken naar een entiteit in je document, dat je van een label wilt voorzien.</span><span class="sxs-lookup"><span data-stu-id="955e9-133">You can use the <b>Find</b> feature to search for an entity in your document that you want to label.</span></span>

   ![Zoeken in bestand](../media/content-understanding/find-feature.png) 

<span data-ttu-id="955e9-135">De functie Zoeken is handig als je in een groot document zoekt of als het document meerdere exemplaren van de entiteit bevat.</span><span class="sxs-lookup"><span data-stu-id="955e9-135">The Find feature is useful if you are searching a large document or if there are multiple instances of the entity in the document.</span></span> <span data-ttu-id="955e9-136">Als je meerdere exemplaren hebt gevonden, kun je in de zoekresultaten het exemplaar selecteren dat je nodig hebt om naar die locatie in de viewer te gaan en dat exemplaar van een label te voorzien.</span><span class="sxs-lookup"><span data-stu-id="955e9-136">If you find multiple instances, you can select the one you need in the search results to go to that location in the viewer to label it.</span></span>


## <a name="add-an-explanation"></a><span data-ttu-id="955e9-137">Voeg een uitleg toe</span><span class="sxs-lookup"><span data-stu-id="955e9-137">Add an explanation</span></span>

<span data-ttu-id="955e9-138">In ons voorbeeld gaan we een uitleg maken met een aanwijzing voor de indeling van de label zelf en de variaties in de voorbeelddocumenten.</span><span class="sxs-lookup"><span data-stu-id="955e9-138">For our example, we are going to create an explanation that provides a hint about the entity format itself and variations it may have in the sample documents.</span></span> <span data-ttu-id="955e9-139">Een datum kan bijvoorbeeld worden weergegeven in een aantal verschillende notaties:</span><span class="sxs-lookup"><span data-stu-id="955e9-139">For example, a date value can be in a number of different formats, such as:</span></span>
- <span data-ttu-id="955e9-140">10/14/2019</span><span class="sxs-lookup"><span data-stu-id="955e9-140">10/14/2019</span></span>
- <span data-ttu-id="955e9-141">14 oktober 2019</span><span class="sxs-lookup"><span data-stu-id="955e9-141">October 14, 2019</span></span>
- <span data-ttu-id="955e9-142">Maandag 14 oktober 2019</span><span class="sxs-lookup"><span data-stu-id="955e9-142">Monday, October 14, 2019</span></span>
 

<span data-ttu-id="955e9-143">Als je de *begindatum van de service* wilt identificeren kun je een uitleg bij het patroon maken.</span><span class="sxs-lookup"><span data-stu-id="955e9-143">To help identify the *Service Start Date* you can create a pattern explanation.</span></span>

1. <span data-ttu-id="955e9-144">In de sectie uitleg selecteer je **Nieuw** en type een naam (bijvoorbeeld, *Leeg*).</span><span class="sxs-lookup"><span data-stu-id="955e9-144">In the Explanation section, select **New** and type a name (for example, *Date*).</span></span>
2. <span data-ttu-id="955e9-145">Selecteer bij type **Patroonlijst**.</span><span class="sxs-lookup"><span data-stu-id="955e9-145">For Type, select **Pattern list**.</span></span>
3. <span data-ttu-id="955e9-146">Geef bij waarde de datumvariant op zoals deze wordt weergegeven in de voorbeeldbestanden.</span><span class="sxs-lookup"><span data-stu-id="955e9-146">For Value, provide the date variation as they appear in the sample files.</span></span> <span data-ttu-id="955e9-147">Als je bijvoorbeeld datumnotaties hebt die worden weergegeven als 0/00/0000, geef je de variaties op die worden weergegeven in je documenten, zoals:</span><span class="sxs-lookup"><span data-stu-id="955e9-147">For example, if you have date formats that appear as 0/00/0000, you enter any variations that appear in your documents, such as:</span></span>
    - <span data-ttu-id="955e9-148">0/0/0000</span><span class="sxs-lookup"><span data-stu-id="955e9-148">0/0/0000</span></span>
    - <span data-ttu-id="955e9-149">0/00/0000</span><span class="sxs-lookup"><span data-stu-id="955e9-149">0/00/0000</span></span>
    - <span data-ttu-id="955e9-150">00/0/0000</span><span class="sxs-lookup"><span data-stu-id="955e9-150">00/0/0000</span></span>
    - <span data-ttu-id="955e9-151">00/00/0000</span><span class="sxs-lookup"><span data-stu-id="955e9-151">00/00/0000</span></span>
4. <span data-ttu-id="955e9-152">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="955e9-152">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="955e9-153">Zie [Uitlegtypen](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview)voor meer informatie over uitlegtypen.</span><span class="sxs-lookup"><span data-stu-id="955e9-153">For more learn more about explanation types, see [Explanation types](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview).</span></span>  


### <a name="use-the-explanation-library"></a><span data-ttu-id="955e9-154">De Uitlegbibliotheek gebruiken</span><span class="sxs-lookup"><span data-stu-id="955e9-154">Use the Explanation library</span></span>

<span data-ttu-id="955e9-155">Voor het maken van toelichtingen voor items als datums, is het eenvoudiger om [de uitlegbibliotheek te gebruiken](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-the-explanation-library) dan om alle variaties handmatig in te voeren.</span><span class="sxs-lookup"><span data-stu-id="955e9-155">For creating explanations for items such as dates, it is easier to [use the explanation library](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-the-explanation-library) than to manually enter all variations.</span></span> <span data-ttu-id="955e9-156">De uitlegbibliotheek is een set vooraf gedefinieerde frasen en patroonverklaringen.</span><span class="sxs-lookup"><span data-stu-id="955e9-156">The explanation library is a set of pre-built phrase and pattern explanations.</span></span> <span data-ttu-id="955e9-157">De bibliotheek biedt alle indelingen voor veelgebruikte woordenlijsten of patroonlijsten, zoals datums, telefoonnummers en postcodes.</span><span class="sxs-lookup"><span data-stu-id="955e9-157">The library tries to provides all formats for common phrase or pattern lists, such as dates, phone numbers, zip codes, and many others.</span></span> 

<span data-ttu-id="955e9-158">Voor het voorbeeld *Begindatum van de service* is het efficiënter om de vooraf gedefinieerde uitleg voor *Datum* te gebruiken in de uitlegbibliotheek:</span><span class="sxs-lookup"><span data-stu-id="955e9-158">For the *Service Start Date* sample, it is more efficient to use the pre-built explanation for *Date* in the explanation library:</span></span>

1. <span data-ttu-id="955e9-159">In de **Sectie uitleg** selecteer je **Nieuw** en vervolgens **Uit Uitlegbibliotheek**.</span><span class="sxs-lookup"><span data-stu-id="955e9-159">In the **Explanation section**, select **New**, and then select **From explanation library**.</span></span>
2. <span data-ttu-id="955e9-160">Uit de uitlegbibliotheek, selecteer **Datum**.</span><span class="sxs-lookup"><span data-stu-id="955e9-160">From the explanation library, select **Date**.</span></span> <span data-ttu-id="955e9-161">Je kunt alle datumvariaties weergeven die worden herkend.</span><span class="sxs-lookup"><span data-stu-id="955e9-161">You can view all variations of date that are recognized.</span></span>
3. <span data-ttu-id="955e9-162">Kies **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="955e9-162">Select **Add**.</span></span></br>

    ![Uitlegbibliotheek](../media/content-understanding/explanation-library.png) 

4. <span data-ttu-id="955e9-164">Op de pagina **een uitleg maken** wordt de *Datum* informatie uit de uitlegbibliotheek automatisch ingevuld op de velden.</span><span class="sxs-lookup"><span data-stu-id="955e9-164">On the **Create an explanation** page, the *Date* information from the explanation library auto fills the fields.</span></span> <span data-ttu-id="955e9-165">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="955e9-165">Select **Save**.</span></span></br>

    ![Datum](../media/content-understanding/date-explanation-library.png) 

## <a name="train-the-model"></a><span data-ttu-id="955e9-167">Het model trainen</span><span class="sxs-lookup"><span data-stu-id="955e9-167">Train the model</span></span> 

<span data-ttu-id="955e9-168">Je uitleg start de training opslaan.</span><span class="sxs-lookup"><span data-stu-id="955e9-168">Saving your explanation start the training.</span></span> <span data-ttu-id="955e9-169">Als je model voldoende gegevens heeft om de gegevens uit de voorbeeldbestanden met een label te halen, zie je elk bestand dat is gemarkeerd met **Overeenkomst**.</span><span class="sxs-lookup"><span data-stu-id="955e9-169">If your model has enough information to extract the data from your labeled example files, you will see each file labeled with **Match**.</span></span>  

![Match](../media/content-understanding/match2.png) 

<span data-ttu-id="955e9-171">Als er niet voldoende informatie is om de gegevens te vinden die je wilt ophalen, krijgt elk bestand de aanduiding **Komt niet overeen**.</span><span class="sxs-lookup"><span data-stu-id="955e9-171">If the explanation does not have enough information to find the data you want to extract, each file will be labeled with **Mismatch**.</span></span> <span data-ttu-id="955e9-172">Je kunt klikken op de **Bestanden die niet overeenkomen**, om meer informatie weer te geven over de reden waarom er geen overeenkomt was.</span><span class="sxs-lookup"><span data-stu-id="955e9-172">You can click on the **Mismatched** files to see more information about why there was a mismatch.</span></span>


## <a name="add-another-explanation"></a><span data-ttu-id="955e9-173">Nog een uitleg toevoegen</span><span class="sxs-lookup"><span data-stu-id="955e9-173">Add another explanation</span></span>

<span data-ttu-id="955e9-174">Het niet-overeenkomen is vaak een aanwijzing dat de uitleg die we hebben verstrekt niet voldoende gegevens heeft verstrekt om de waarde van de begindatum van de service te halen om te voldoen aan de gelabelde bestanden.</span><span class="sxs-lookup"><span data-stu-id="955e9-174">Often the mismatch is an indication that the explanation we provided did not provide enough information to extract the service start date value to match our labeled files.</span></span> <span data-ttu-id="955e9-175">Mogelijk moet je het bewerken of nog een uitleg toevoegen.</span><span class="sxs-lookup"><span data-stu-id="955e9-175">You may need to edit it, or add another explanation.</span></span>

<span data-ttu-id="955e9-176">In ons voorbeeld ziet u dat de tekenreeks *Begindatum van de service van* altijd vóór de werkelijke waarde begint.</span><span class="sxs-lookup"><span data-stu-id="955e9-176">For our example, notice that the text string *Start Service date of* always precedes the actual value.</span></span> <span data-ttu-id="955e9-177">Als je de begindatum van de service wilt identificeren moet je een uitleg bij de frase maken.</span><span class="sxs-lookup"><span data-stu-id="955e9-177">To help identify the Service Start Date, you need to create a phrase explanation.</span></span>

1. <span data-ttu-id="955e9-178">In de sectie uitleg selecteer je **Nieuw** en type een naam (bijvoorbeeld, *Voorvoegseltekenreeks*).</span><span class="sxs-lookup"><span data-stu-id="955e9-178">In the Explanation section, select **New**, and then type a name (for example, *Prefix String*).</span></span>
2. <span data-ttu-id="955e9-179">Voor het type selecteer je **Woordenlijst**.</span><span class="sxs-lookup"><span data-stu-id="955e9-179">For the Type, select **Phrase list**.</span></span>
3. <span data-ttu-id="955e9-180">De *Begindatum van de service van* als waarde gebruiken.</span><span class="sxs-lookup"><span data-stu-id="955e9-180">Use *Service Start Date of* as the value.</span></span>
4. <span data-ttu-id="955e9-181">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="955e9-181">Select **Save**.</span></span>

    ![Voorvoegseltekenreeks](../media/content-understanding/prefix-string.png) 

## <a name="train-the-model-again"></a><span data-ttu-id="955e9-183">Het model nogmaals trainen</span><span class="sxs-lookup"><span data-stu-id="955e9-183">Train the model again</span></span>

<span data-ttu-id="955e9-184">Door de uitleg op te slaan, wordt de training opnieuw gestart en deze keer worden met beide uitleggen in het voorbeeld gebruikt.</span><span class="sxs-lookup"><span data-stu-id="955e9-184">Saving the explanation starts the training again, this time using both explanations in the example.</span></span> <span data-ttu-id="955e9-185">Als je model voldoende gegevens heeft om de gegevens uit de voorbeeldbestanden met een label te halen, zie je elk bestand dat is gemarkeerd met **Overeenkomst**.</span><span class="sxs-lookup"><span data-stu-id="955e9-185">If your model has enough information to extract the data from the labeled example files, you see each file labeled with **Match**.</span></span> 

<span data-ttu-id="955e9-186">Als je opnieuw een **Komt niet overeen** op je gelabelde bestanden ontvangt, moet je waarschijnlijk nog een uitleg maken om het model meer informatie te geven om het documenttype te identificeren, of je kunt wijzigingen aanbrengen in je bestaande bestanden.</span><span class="sxs-lookup"><span data-stu-id="955e9-186">If you again receive a **Mismatch** on your labeled files, you likely need to create another explanation to provide the model more information to identify the document type, or consider making changes to your existing ones.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="955e9-187">Test je model.</span><span class="sxs-lookup"><span data-stu-id="955e9-187">Test your model</span></span>

<span data-ttu-id="955e9-188">Als je een overeenkomst hebt gekregen met de gelabelde voorbeeldbestanden, kun je nu je model testen op de andere niet-gelabelde voorbeeldbestanden.</span><span class="sxs-lookup"><span data-stu-id="955e9-188">If you receive a match on your labeled sample files, you can now test your model on the remaining unlabeled example files.</span></span> <span data-ttu-id="955e9-189">Dit is een optionele, maar handige stap voor het evalueren van de "geschiktheid" of het voorbereiding van het model voordat dit wordt gebruikt, door het te testen op bestanden die het model nog niet heeft gezien.</span><span class="sxs-lookup"><span data-stu-id="955e9-189">This is optional, but a useful step to evaluate the “fitness” or readiness of the model before using it, by testing it on files the model hasn’t seen before.</span></span>

1. <span data-ttu-id="955e9-190">Op de startpagina van het model klik je op het tabblad **Testen**.  Hiermee wordt het model uitgevoerd op de niet-gelabelde voorbeeldbestanden.</span><span class="sxs-lookup"><span data-stu-id="955e9-190">From the model home page, click the **Test** tab.  This runs the model on your unlabeled sample files.</span></span>
2. <span data-ttu-id="955e9-191">In de lijst **Testbestanden** worden de voorbeeldbestanden weergegeven om aan te geven of de gegevens die je nodig hebt, door het model kunnen worden opgehaald.</span><span class="sxs-lookup"><span data-stu-id="955e9-191">In the **Test files** list, your example files display to show if the model is able to extract the information you need.</span></span> <span data-ttu-id="955e9-192">Gebruik deze informatie om de effectiviteit van je classificatie bij het identificeren van je documenten vast te stellen.</span><span class="sxs-lookup"><span data-stu-id="955e9-192">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![Op je bestanden testen](../media/content-understanding/test-filies-extractor.png) 

## <a name="see-also"></a><span data-ttu-id="955e9-194">Zie ook</span><span class="sxs-lookup"><span data-stu-id="955e9-194">See Also</span></span>
[<span data-ttu-id="955e9-195">Een classificatie maken</span><span class="sxs-lookup"><span data-stu-id="955e9-195">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="955e9-196">Uitlegtypen</span><span class="sxs-lookup"><span data-stu-id="955e9-196">Explanation types</span></span>](explanation-types-overview.md)

[<span data-ttu-id="955e9-197">De taxonomie van een termenarchief benutten bij het maken van een extractor</span><span class="sxs-lookup"><span data-stu-id="955e9-197">Leverage term store taxonomy when creating an extractor</span></span>](leverage-term-store-taxonomy.md)

[<span data-ttu-id="955e9-198">Overzicht van documentbegrip</span><span class="sxs-lookup"><span data-stu-id="955e9-198">Document Understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="955e9-199">Een model toepassen</span><span class="sxs-lookup"><span data-stu-id="955e9-199">Apply a model</span></span>](apply-a-model.md) 
