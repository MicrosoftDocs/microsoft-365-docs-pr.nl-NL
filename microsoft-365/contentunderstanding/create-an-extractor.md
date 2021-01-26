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
ms.openlocfilehash: 7417805f51bb3a1c7b993ce2cd72137478abbc02
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/25/2021
ms.locfileid: "49976541"
---
# <a name="create-an-extractor-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="4b243-103">Maak een Extractor in Microsoft SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="4b243-103">Create an extractor in Microsoft SharePoint Syntex</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL2G]

</br> 

<span data-ttu-id="4b243-104">Vóór of na het maken van een classificatiemodel voor het automatiseren van de identificatie en classificatie van specifieke documenttypen, kun je desgewenst extra uittreksels toevoegen aan je model om specifieke informatie uit deze documenten te halen.</span><span class="sxs-lookup"><span data-stu-id="4b243-104">Before or after you create a classifier model to automate identification and classification of specific document types, you can optionally choose to add extractors to your model to pull out specific information from these documents.</span></span> <span data-ttu-id="4b243-105">Het is bijvoorbeeld mogelijk dat je wilt dat je model niet alleen wordt herkend aan *alle* documenten die worden toegevoegd aan de documentbibliotheek, maar je kunt ook de *service-begindatum* voor elk document weergeven als een kolomwaarde in de documentbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="4b243-105">For example, you may want your model not only to identify all *Contract Renewal* documents added to your document library, but also to display the *Service Start date* for each document as a column value in the document library.</span></span>

<span data-ttu-id="4b243-106">Je moet een extractor maken voor elke entiteit in het document die je wilt ophalen.</span><span class="sxs-lookup"><span data-stu-id="4b243-106">You need to create an extractor for each entity in the document that you want to extract.</span></span> <span data-ttu-id="4b243-107">In ons voorbeeld willen we de  **begindatum van de service** extraheren voor elke  **contractvernieuwing** -document dat door het model wordt geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="4b243-107">In our example, we want to extract the **Service Start Date** for each **Contract Renewal** document that is identified by the model.</span></span> <span data-ttu-id="4b243-108">We willen een weergave kunnen zien in de documentbibliotheek van alle  **contract** documenten, met een kolom waarin de **begindatum van de service** van elk document wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="4b243-108">We want to be able to see a view in the document library of all  **Contract Renewal** documents, with a column that shows the **Service Start** date value of each document.</span></span> 

> [!NOTE]
> <span data-ttu-id="4b243-109">Als je een extractor wilt maken, gebruik je dezelfde bestanden die je eerder hebt geüpload om de classificatie te trainen.</span><span class="sxs-lookup"><span data-stu-id="4b243-109">In order to create an extractor, you use the same files you previously uploaded to train the classifier.</span></span> 

## <a name="name-your-extractor"></a><span data-ttu-id="4b243-110">Een naam voor de Extractor geven</span><span class="sxs-lookup"><span data-stu-id="4b243-110">Name your extractor</span></span>

1. <span data-ttu-id="4b243-111">Klik op de startpagina van het model op **Train Extractor** in de tegel **Extractor maken en trainen**.</span><span class="sxs-lookup"><span data-stu-id="4b243-111">From the model home page, in the **Create and train extractors** tile, click **Train extractor**.</span></span>
2. <span data-ttu-id="4b243-112">Typ in het scherm **New entiteit Extractor** de naam van je extractor in het veld **Nieuwe extractorname**.</span><span class="sxs-lookup"><span data-stu-id="4b243-112">On the **New entity extractor** screen, type the name of your extractor in the **New extractor name** field.</span></span> <span data-ttu-id="4b243-113">Als je bijvoorbeeld de **begindatum van de service** wilt wijzigen als je de begindatum van de service wilt ophalen uit elk document voor het verlengen van een contract.</span><span class="sxs-lookup"><span data-stu-id="4b243-113">For example, name it **Service Start Date** if you want to extract the service start date from each Contract Renewal document.</span></span> <span data-ttu-id="4b243-114">Je kunt er ook voor kiezen om een eerder gemaakte kolom opnieuw te gebruiken (bijvoorbeeld een kolom met beheerde metagegevens).</span><span class="sxs-lookup"><span data-stu-id="4b243-114">You can also choose to reuse a previously created column (for example, a managed metadata column).</span></span>
> [!NOTE]
> <span data-ttu-id="4b243-115">Als je een nieuwe extractor maakt, selecteer dan **Nieuwe kolomtype** en kies **Enkele tekstregel**. Het maximumaantal tekens is 255.</span><span class="sxs-lookup"><span data-stu-id="4b243-115">If you create a new extractor, then select **New column type** and choose **Single line of text**, the maximum character limit is 255.</span></span> <span data-ttu-id="4b243-116">Alle tekens die de limiet overschrijden worden afgebroken.</span><span class="sxs-lookup"><span data-stu-id="4b243-116">Any characters that you type exceeding the limit get truncated.</span></span> 
3. <span data-ttu-id="4b243-117">Klik op **Maken** wanneer je klaar bent.</span><span class="sxs-lookup"><span data-stu-id="4b243-117">When you're done, click **Create**.</span></span>

## <a name="add-a-label"></a><span data-ttu-id="4b243-118">Een label toevoegen</span><span class="sxs-lookup"><span data-stu-id="4b243-118">Add a label</span></span>

<span data-ttu-id="4b243-119">De volgende stap bestaat uit het label van de entiteit die je wilt ophalen in de voorbeeldbestanden van de training.</span><span class="sxs-lookup"><span data-stu-id="4b243-119">The next step is to label the entity you want to extract in your example training files.</span></span>

<span data-ttu-id="4b243-120">Als je de Extractor maakt, wordt de extractor-pagina geopend.</span><span class="sxs-lookup"><span data-stu-id="4b243-120">Creating the extractor opens the extractor page.</span></span> <span data-ttu-id="4b243-121">Hier zie je een lijst met je voorbeeldbestanden, met het eerste bestand in de lijst die wordt weergegeven in de viewer.</span><span class="sxs-lookup"><span data-stu-id="4b243-121">Here you see a list of your sample files, with the first file on the list displayed in the viewer.</span></span>

1. <span data-ttu-id="4b243-122">Selecteer in de viewer de gegevens die je wilt ophalen uit de bestanden.</span><span class="sxs-lookup"><span data-stu-id="4b243-122">From the viewer, select the data that you want to extract from the files.</span></span> <span data-ttu-id="4b243-123">Als je bijvoorbeeld de *begindatum van service* wilt ophalen, markeer je de datumwaarde in het eerste bestand (*maandag, 14 oktober 2019*).</span><span class="sxs-lookup"><span data-stu-id="4b243-123">For example, if you want to extract the *Start Service Date*, you highlight the date value in the first file (*Monday, October 14, 2019*).</span></span> <span data-ttu-id="4b243-124">en klik dan op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="4b243-124">and then click **Save**.</span></span>  <span data-ttu-id="4b243-125">De weergave van de waarde wordt weergegeven in het bestand in de lijst voorbeelden met een bijschrift onder de **labelkolom**.</span><span class="sxs-lookup"><span data-stu-id="4b243-125">You should see the value display from the file in the Labeled examples list, under the **Label** column.</span></span>
2. <span data-ttu-id="4b243-126">Selecteer **Volgende bestand** om automatisch op te slaan en het volgende bestand te openen in de lijst in de viewer.</span><span class="sxs-lookup"><span data-stu-id="4b243-126">Select **Next file** to auto save and open the next file in the list in the viewer.</span></span> <span data-ttu-id="4b243-127">Of selecteer **Opslaan** en selecteer een ander bestand van de lijst **Gelabelde voorbeelden**.</span><span class="sxs-lookup"><span data-stu-id="4b243-127">Or select **Save** and then select another file from the **Labeled examples** list.</span></span>
3. <span data-ttu-id="4b243-128">Herhaal stap 1 en 2 in de viewer en herhaal dit totdat je het label in alle vijf bestanden hebt opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="4b243-128">In the viewer, repeat steps 1 and 2, then repeat until you saved the label in all five files.</span></span>

    ![Geavanceerde instellingen](../media/content-understanding/select-service-start-date.png) 

 
<span data-ttu-id="4b243-130">Wanneer je vijf bestanden hebt voorzien van een label, wordt een melding weergegeven met de mededeling dat je wilt overstappen op de training.</span><span class="sxs-lookup"><span data-stu-id="4b243-130">Once you labeled five files, a notification banner displays informing you to move to training.</span></span> <span data-ttu-id="4b243-131">Je kunt ervoor kiezen om meer documenten beter te labelen of verder te gaan met de training.</span><span class="sxs-lookup"><span data-stu-id="4b243-131">You can choose to more label more documents or advance to training.</span></span> 

## <a name="add-an-explanation"></a><span data-ttu-id="4b243-132">Voeg een uitleg toe</span><span class="sxs-lookup"><span data-stu-id="4b243-132">Add an explanation</span></span>

<span data-ttu-id="4b243-133">In ons voorbeeld gaan we een uitleg maken met een aanwijzing voor de indeling van de label zelf en de variaties in de voorbeelddocumenten.</span><span class="sxs-lookup"><span data-stu-id="4b243-133">For our example, we are going to create an explanation that provides a hint about the entity format itself and variations it may have in the sample documents.</span></span> <span data-ttu-id="4b243-134">Een datum kan bijvoorbeeld worden weergegeven in een aantal verschillende notaties:</span><span class="sxs-lookup"><span data-stu-id="4b243-134">For example, a date value can be in a number of different formats, such as:</span></span>
- <span data-ttu-id="4b243-135">10/14/2019</span><span class="sxs-lookup"><span data-stu-id="4b243-135">10/14/2019</span></span>
- <span data-ttu-id="4b243-136">14 oktober 2019</span><span class="sxs-lookup"><span data-stu-id="4b243-136">October 14, 2019</span></span>
- <span data-ttu-id="4b243-137">Maandag 14 oktober 2019</span><span class="sxs-lookup"><span data-stu-id="4b243-137">Monday, October 14, 2019</span></span>
 

<span data-ttu-id="4b243-138">Als je de *begindatum van de service* wilt identificeren kun je een uitleg bij het patroon maken.</span><span class="sxs-lookup"><span data-stu-id="4b243-138">To help identify the *Service Start Date* you can create a pattern explanation.</span></span>

1. <span data-ttu-id="4b243-139">In de sectie uitleg selecteer je **Nieuw** en type een naam (bijvoorbeeld, *Leeg*).</span><span class="sxs-lookup"><span data-stu-id="4b243-139">In the Explanation section, select **New** and type a name (for example, *Date*).</span></span>
2. <span data-ttu-id="4b243-140">Selecteer bij type **Patroonlijst**.</span><span class="sxs-lookup"><span data-stu-id="4b243-140">For Type, select **Pattern list**.</span></span>
3. <span data-ttu-id="4b243-141">Geef bij waarde de datumvariant op zoals deze wordt weergegeven in de voorbeeldbestanden.</span><span class="sxs-lookup"><span data-stu-id="4b243-141">For Value, provide the date variation as they appear in the sample files.</span></span> <span data-ttu-id="4b243-142">Als je bijvoorbeeld datumnotaties hebt die worden weergegeven als 0/00/0000, geef je de variaties op die worden weergegeven in je documenten, zoals:</span><span class="sxs-lookup"><span data-stu-id="4b243-142">For example, if you have date formats that appear as 0/00/0000, you enter any variations that appear in your documents, such as:</span></span>
    - <span data-ttu-id="4b243-143">0/0/0000</span><span class="sxs-lookup"><span data-stu-id="4b243-143">0/0/0000</span></span>
    - <span data-ttu-id="4b243-144">0/00/0000</span><span class="sxs-lookup"><span data-stu-id="4b243-144">0/00/0000</span></span>
    - <span data-ttu-id="4b243-145">00/0/0000</span><span class="sxs-lookup"><span data-stu-id="4b243-145">00/0/0000</span></span>
    - <span data-ttu-id="4b243-146">00/00/0000</span><span class="sxs-lookup"><span data-stu-id="4b243-146">00/00/0000</span></span>
4. <span data-ttu-id="4b243-147">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="4b243-147">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="4b243-148">Zie [Uitlegtypen](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview)voor meer informatie over uitlegtypen.</span><span class="sxs-lookup"><span data-stu-id="4b243-148">For more learn more about explanation types, see [Explanation types](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview).</span></span>  


### <a name="use-the-explanation-library"></a><span data-ttu-id="4b243-149">De Uitlegbibliotheek gebruiken</span><span class="sxs-lookup"><span data-stu-id="4b243-149">Use the Explanation library</span></span>

<span data-ttu-id="4b243-150">Voor het maken van toelichtingen voor items als datums, is het eenvoudiger om [de uitlegbibliotheek te gebruiken](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-the-explanation-library) dan om alle variaties handmatig in te voeren.</span><span class="sxs-lookup"><span data-stu-id="4b243-150">For creating explanations for items such as dates, it is easier to [use the explanation library](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-the-explanation-library) than to manually enter all variations.</span></span> <span data-ttu-id="4b243-151">De uitlegbibliotheek is een set vooraf gedefinieerde frasen en patroonverklaringen.</span><span class="sxs-lookup"><span data-stu-id="4b243-151">The explanation library is a set of pre-built phrase and pattern explanations.</span></span> <span data-ttu-id="4b243-152">De bibliotheek biedt alle indelingen voor veelgebruikte woordenlijsten of patroonlijsten, zoals datums, telefoonnummers en postcodes.</span><span class="sxs-lookup"><span data-stu-id="4b243-152">The library tries to provides all formats for common phrase or pattern lists, such as dates, phone numbers, zip codes, and many others.</span></span> 

<span data-ttu-id="4b243-153">Voor het voorbeeld *Begindatum van de service* is het efficiënter om de vooraf gedefinieerde uitleg voor *Datum* te gebruiken in de uitlegbibliotheek:</span><span class="sxs-lookup"><span data-stu-id="4b243-153">For the *Service Start Date* sample, it is more efficient to use the pre-built explanation for *Date* in the explanation library:</span></span>

1. <span data-ttu-id="4b243-154">In de **Sectie uitleg** selecteer je **Nieuw** en vervolgens **Uit Uitlegbibliotheek**.</span><span class="sxs-lookup"><span data-stu-id="4b243-154">In the **Explanation section**, select **New**, and then select **From explanation library**.</span></span>
2. <span data-ttu-id="4b243-155">Uit de uitlegbibliotheek, selecteer **Datum**.</span><span class="sxs-lookup"><span data-stu-id="4b243-155">From the explanation library, select **Date**.</span></span> <span data-ttu-id="4b243-156">Je kunt alle datumvariaties weergeven die worden herkend.</span><span class="sxs-lookup"><span data-stu-id="4b243-156">You can view all variations of date that are recognized.</span></span>
3. <span data-ttu-id="4b243-157">Kies **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="4b243-157">Select **Add**.</span></span></br>

    ![Uitlegbibliotheek](../media/content-understanding/explanation-library.png) 

4. <span data-ttu-id="4b243-159">Op de pagina **een uitleg maken** wordt de *Datum* informatie uit de uitlegbibliotheek automatisch ingevuld op de velden.</span><span class="sxs-lookup"><span data-stu-id="4b243-159">On the **Create an explanation** page, the *Date* information from the explanation library auto fills the fields.</span></span> <span data-ttu-id="4b243-160">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="4b243-160">Select **Save**.</span></span></br>

    ![Datum](../media/content-understanding/date-explanation-library.png) 

## <a name="train-the-model"></a><span data-ttu-id="4b243-162">Het model trainen</span><span class="sxs-lookup"><span data-stu-id="4b243-162">Train the model</span></span> 

<span data-ttu-id="4b243-163">Je uitleg start de training opslaan.</span><span class="sxs-lookup"><span data-stu-id="4b243-163">Saving your explanation start the training.</span></span> <span data-ttu-id="4b243-164">Als je model voldoende gegevens heeft om de gegevens uit de voorbeeldbestanden met een label te halen, zie je elk bestand dat is gemarkeerd met **Overeenkomst**.</span><span class="sxs-lookup"><span data-stu-id="4b243-164">If your model has enough information to extract the data from your labeled example files, you will see each file labeled with **Match**.</span></span>  

![Match](../media/content-understanding/match2.png) 

<span data-ttu-id="4b243-166">Als er niet voldoende informatie is om de gegevens te vinden die je wilt ophalen, krijgt elk bestand de aanduiding **Komt niet overeen**.</span><span class="sxs-lookup"><span data-stu-id="4b243-166">If the explanation does not have enough information to find the data you want to extract, each file will be labeled with **Mismatch**.</span></span> <span data-ttu-id="4b243-167">Je kunt klikken op de **Bestanden die niet overeenkomen**, om meer informatie weer te geven over de reden waarom er geen overeenkomt was.</span><span class="sxs-lookup"><span data-stu-id="4b243-167">You can click on the **Mismatched** files to see more information about why there was a mismatch.</span></span>


## <a name="add-another-explanation"></a><span data-ttu-id="4b243-168">Nog een uitleg toevoegen</span><span class="sxs-lookup"><span data-stu-id="4b243-168">Add another explanation</span></span>

<span data-ttu-id="4b243-169">Het niet-overeenkomen is vaak een aanwijzing dat de uitleg die we hebben verstrekt niet voldoende gegevens heeft verstrekt om de waarde van de begindatum van de service te halen om te voldoen aan de gelabelde bestanden.</span><span class="sxs-lookup"><span data-stu-id="4b243-169">Often the mismatch is an indication that the explanation we provided did not provide enough information to extract the service start date value to match our labeled files.</span></span> <span data-ttu-id="4b243-170">Mogelijk moet je het bewerken of nog een uitleg toevoegen.</span><span class="sxs-lookup"><span data-stu-id="4b243-170">You may need to edit it, or add another explanation.</span></span>

<span data-ttu-id="4b243-171">In ons voorbeeld ziet u dat de tekenreeks *Begindatum van de service van* altijd vóór de werkelijke waarde begint.</span><span class="sxs-lookup"><span data-stu-id="4b243-171">For our example, notice that the text string *Start Service date of* always precedes the actual value.</span></span> <span data-ttu-id="4b243-172">Als je de begindatum van de service wilt identificeren moet je een uitleg bij de frase maken.</span><span class="sxs-lookup"><span data-stu-id="4b243-172">To help identify the Service Start Date, you need to create a phrase explanation.</span></span>

1. <span data-ttu-id="4b243-173">In de sectie uitleg selecteer je **Nieuw** en type een naam (bijvoorbeeld, *Voorvoegseltekenreeks*).</span><span class="sxs-lookup"><span data-stu-id="4b243-173">In the Explanation section, select **New**, and then type a name (for example, *Prefix String*).</span></span>
2. <span data-ttu-id="4b243-174">Voor het type selecteer je **Woordenlijst**.</span><span class="sxs-lookup"><span data-stu-id="4b243-174">For the Type, select **Phrase list**.</span></span>
3. <span data-ttu-id="4b243-175">De *Begindatum van de service van* als waarde gebruiken.</span><span class="sxs-lookup"><span data-stu-id="4b243-175">Use *Service Start Date of* as the value.</span></span>
4. <span data-ttu-id="4b243-176">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="4b243-176">Select **Save**.</span></span>

    ![Voorvoegseltekenreeks](../media/content-understanding/prefix-string.png) 

## <a name="train-the-model-again"></a><span data-ttu-id="4b243-178">Het model nogmaals trainen</span><span class="sxs-lookup"><span data-stu-id="4b243-178">Train the model again</span></span>

<span data-ttu-id="4b243-179">Door de uitleg op te slaan, wordt de training opnieuw gestart en deze keer worden met beide uitleggen in het voorbeeld gebruikt.</span><span class="sxs-lookup"><span data-stu-id="4b243-179">Saving the explanation starts the training again, this time using both explanations in the example.</span></span> <span data-ttu-id="4b243-180">Als je model voldoende gegevens heeft om de gegevens uit de voorbeeldbestanden met een label te halen, zie je elk bestand dat is gemarkeerd met **Overeenkomst**.</span><span class="sxs-lookup"><span data-stu-id="4b243-180">If your model has enough information to extract the data from the labeled example files, you see each file labeled with **Match**.</span></span> 

<span data-ttu-id="4b243-181">Als je opnieuw een **Komt niet overeen** op je gelabelde bestanden ontvangt, moet je waarschijnlijk nog een uitleg maken om het model meer informatie te geven om het documenttype te identificeren, of je kunt wijzigingen aanbrengen in je bestaande bestanden.</span><span class="sxs-lookup"><span data-stu-id="4b243-181">If you again receive a **Mismatch** on your labeled files, you likely need to create another explanation to provide the model more information to identify the document type, or consider making changes to your existing ones.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="4b243-182">Test je model.</span><span class="sxs-lookup"><span data-stu-id="4b243-182">Test your model</span></span>

<span data-ttu-id="4b243-183">Als je een overeenkomst hebt gekregen met de gelabelde voorbeeldbestanden, kun je nu je model testen op de andere niet-gelabelde voorbeeldbestanden.</span><span class="sxs-lookup"><span data-stu-id="4b243-183">If you receive a match on your labeled sample files, you can now test your model on the remaining unlabeled example files.</span></span> <span data-ttu-id="4b243-184">Dit is een optionele, maar handige stap voor het evalueren van de "geschiktheid" of het voorbereiding van het model voordat dit wordt gebruikt, door het te testen op bestanden die het model nog niet heeft gezien.</span><span class="sxs-lookup"><span data-stu-id="4b243-184">This is optional, but a useful step to evaluate the “fitness” or readiness of the model before using it, by testing it on files the model hasn’t seen before.</span></span>

1. <span data-ttu-id="4b243-185">Op de startpagina van het model klik je op het tabblad **Testen**.  Hiermee wordt het model uitgevoerd op de niet-gelabelde voorbeeldbestanden.</span><span class="sxs-lookup"><span data-stu-id="4b243-185">From the model home page, click the **Test** tab.  This runs the model on your unlabeled sample files.</span></span>
2. <span data-ttu-id="4b243-186">In de lijst **Testbestanden** worden de voorbeeldbestanden weergegeven om aan te geven of de gegevens die je nodig hebt, door het model kunnen worden opgehaald.</span><span class="sxs-lookup"><span data-stu-id="4b243-186">In the **Test files** list, your example files display to show if the model is able to extract the information you need.</span></span> <span data-ttu-id="4b243-187">Gebruik deze informatie om de effectiviteit van je classificatie bij het identificeren van je documenten vast te stellen.</span><span class="sxs-lookup"><span data-stu-id="4b243-187">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![Op je bestanden testen](../media/content-understanding/test-filies-extractor.png) 

## <a name="see-also"></a><span data-ttu-id="4b243-189">Zie ook</span><span class="sxs-lookup"><span data-stu-id="4b243-189">See Also</span></span>
[<span data-ttu-id="4b243-190">Een classificatie maken</span><span class="sxs-lookup"><span data-stu-id="4b243-190">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="4b243-191">Uitlegtypen</span><span class="sxs-lookup"><span data-stu-id="4b243-191">Explanation types</span></span>](explanation-types-overview.md)

[<span data-ttu-id="4b243-192">De taxonomie van een termenarchief benutten bij het maken van een extractor</span><span class="sxs-lookup"><span data-stu-id="4b243-192">Leverage term store taxonomy when creating an extractor</span></span>](leverage-term-store-taxonomy.md)

[<span data-ttu-id="4b243-193">Overzicht van documentbegrip</span><span class="sxs-lookup"><span data-stu-id="4b243-193">Document Understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="4b243-194">Een model toepassen</span><span class="sxs-lookup"><span data-stu-id="4b243-194">Apply a model</span></span>](apply-a-model.md) 
