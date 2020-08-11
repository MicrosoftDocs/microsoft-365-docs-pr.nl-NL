---
title: Een extractor maken (preview)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Meer informatie over het maken van een extractor
ms.openlocfilehash: 64dede9f6613da82c65ca12c6c335a25301f5b9e
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612760"
---
# <a name="create-an-extractor-preview"></a><span data-ttu-id="a9940-103">Een extractor maken (preview)</span><span class="sxs-lookup"><span data-stu-id="a9940-103">Create an extractor (Preview)</span></span>
> [!Note] 
> <span data-ttu-id="a9940-104">De inhoud in dit artikel is bedoeld voor project cortex private preview.</span><span class="sxs-lookup"><span data-stu-id="a9940-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="a9940-105">[Lees meer over project cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="a9940-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL2G]

</br> 

<span data-ttu-id="a9940-106">Voordat of nadat u een classificatiemodel hebt gemaakt om het identificeren en classificeren van specifieke documenttypen te automatiseren, kunt u ervoor kiezen om extra informatie toe te voegen aan uw model om bepaalde informatie uit deze documenten uit te pakken.</span><span class="sxs-lookup"><span data-stu-id="a9940-106">Either before or after you create a classifier model to automate identification and classification of specific document types, you can optionally choose to add extractors to your model to pull out specific information from these documents.</span></span> <span data-ttu-id="a9940-107">U wilt bijvoorbeeld dat uw model niet alleen alle documenten voor het verlengen van een *contract* identificeert die aan de documentbibliotheek worden toegevoegd, maar ook de *begindatum* van de service voor elk document weergeven als kolom in de documentbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="a9940-107">For example, you may want your model not only to identify all *Contract Renewal* documents that are added to your document library, but to also display the *Service Start date* for each document as a column in the document library.</span></span>

<span data-ttu-id="a9940-108">U moet een extractor maken voor elke entiteit in het document die u wilt extraheren.</span><span class="sxs-lookup"><span data-stu-id="a9940-108">You need to create an extractor for each entity in the document that you want to extract.</span></span> <span data-ttu-id="a9940-109">In ons voorbeeld willen we de *begindatum* van de service uitpakken voor elk document voor het *verlengen* van documenten dat door het model wordt geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="a9940-109">In our example, we want to extract the *Service Start Date* for each *Contract Renewal* document that is identified by the model.</span></span> <span data-ttu-id="a9940-110">We willen een weergave in de documentbibliotheek van alle documenten voor het *verlengen* van documenten kunnen zien, met een kolom die de begindatum waarde van een service van elk document weergeeft.</span><span class="sxs-lookup"><span data-stu-id="a9940-110">We want to be able to see a view in the document library of all *Contract Renewal* documents, with a column that shows the Service Start date value of each document.</span></span>

> [!Note]
> <span data-ttu-id="a9940-111">Voordat u een Extractor maakt, moet u eerst de [voorbeeldbestanden toevoegen](https://docs.microsoft.com/microsoft-365/contentunderstanding/create-a-classifier?view=o365-worldwide#add-your-example-files) die u nodig hebt om het model te identificeren, zodat u de informatie die u wilt extraheren, kunt identificeren.</span><span class="sxs-lookup"><span data-stu-id="a9940-111">Before creating an extractor, you need to [add your example files](https://docs.microsoft.com/microsoft-365/contentunderstanding/create-a-classifier?view=o365-worldwide#add-your-example-files) you will need to help train the model to identify the information you want to extract.</span></span> <span data-ttu-id="a9940-112">Gebruik de voorbeeldbestanden die u hebt gebruikt om uw classificatie te maken.</span><span class="sxs-lookup"><span data-stu-id="a9940-112">Use the same example files you used to create your classifier.</span></span>


## <a name="name-your-extractor"></a><span data-ttu-id="a9940-113">Naam van de extractor</span><span class="sxs-lookup"><span data-stu-id="a9940-113">Name your extractor</span></span>

1. <span data-ttu-id="a9940-114">Klik op de startpagina van het model in de tegel **extracten maken en trainen** op **Train Extractor**.</span><span class="sxs-lookup"><span data-stu-id="a9940-114">On the model home page, in the **Create and train extractors** tile, click **Train extractor**.</span></span>
2. <span data-ttu-id="a9940-115">Typ in het scherm **nieuwe entiteits Extractor** de naam van het extractor in het veld **nieuwe naam** van de extractie.</span><span class="sxs-lookup"><span data-stu-id="a9940-115">On the **New entity extractor** screen, type the name of your extractor in the **New extractor name** field.</span></span> <span data-ttu-id="a9940-116">We kunnen bijvoorbeeld de naam van de service **starten** wanneer we de begindatum van een service willen uitpakken uit elk document voor het verlengen van het contract.</span><span class="sxs-lookup"><span data-stu-id="a9940-116">For example, we can name it **Service Start Date** if we want to extract the service start date from each Contract Renewal document.</span></span>
3. <span data-ttu-id="a9940-117">Klik op **Maken**.</span><span class="sxs-lookup"><span data-stu-id="a9940-117">Click **Create**.</span></span>

## <a name="add-a-label"></a><span data-ttu-id="a9940-118">Een label toevoegen</span><span class="sxs-lookup"><span data-stu-id="a9940-118">Add a label</span></span>

<span data-ttu-id="a9940-119">De volgende stap is het markeren van de gegevens die u wilt extraheren in de voorbeeldbestanden van uw voorkeuren.</span><span class="sxs-lookup"><span data-stu-id="a9940-119">The next step is to label the information you want to extract in your example training files.</span></span>

<span data-ttu-id="a9940-120">Als u de Extractor maakt, wordt de extractor-pagina geopend waarin u een lijst met voorbeeldbestanden ziet, waarbij het eerste bestand in de lijst wordt weergegeven in de viewer.</span><span class="sxs-lookup"><span data-stu-id="a9940-120">Creating the extractor will open the extractor page in which you will see a list of your example files, with the first file on the list displayed in the viewer.</span></span>

1. <span data-ttu-id="a9940-121">Selecteer de gegevens die u wilt extraheren uit de bestanden in de viewer.</span><span class="sxs-lookup"><span data-stu-id="a9940-121">In the viewer, select the data that you want to extract from the files.</span></span> <span data-ttu-id="a9940-122">Als u bijvoorbeeld de *begindatum*van de service wilt extraheren, markeert u de datumwaarde voor de service in het eerste bestand (*maandag, 14 oktober 2019*).</span><span class="sxs-lookup"><span data-stu-id="a9940-122">For example, if you want to extract the *Start Service Date*, you will highlight the date value for it in the first file (*Monday, October 14, 2019*).</span></span> <span data-ttu-id="a9940-123">Klik vervolgens op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="a9940-123">Then click **Save**.</span></span>  <span data-ttu-id="a9940-124">U ziet in de lijst met gelabelde voorbeelden onder de kolom **Label** de waarde weergave voor het bestand.</span><span class="sxs-lookup"><span data-stu-id="a9940-124">You will see the value display for the file in the Labeled examples list under the **Label** column.</span></span>
2. <span data-ttu-id="a9940-125">Selecteer **volgende bestand** om automatisch opslaan te selecteren en het volgende bestand te openen in de lijst in de Viewer of selecteer **Opslaan** en selecteer een ander bestand in de lijst met **gelabelde voorbeelden** .</span><span class="sxs-lookup"><span data-stu-id="a9940-125">Select **Next file** to autosave and open the next file in the list in the viewer, or you can select **Save** and select another file from the **Labeled examples** list.</span></span>
3. <span data-ttu-id="a9940-126">Herhaal de stappen 1 en 2 in de viewer totdat u het label in vijf bestanden hebt opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="a9940-126">In the viewer, repeat steps 1 and 2, and do this until you have saved the label in five files.</span></span>

    ![Geavanceerde instellingen](../media/content-understanding/select-service-start-date.png) 


### <a name="add-a-negative-example"></a><span data-ttu-id="a9940-128">Een negatief voorbeeld toevoegen</span><span class="sxs-lookup"><span data-stu-id="a9940-128">Add a negative example</span></span>

<span data-ttu-id="a9940-129">Net als bij het toevoegen van een negatief voorbeeldbestand bij het maken van een classificatie, moet u een negatief voorbeeld toevoegen voor de extractor.</span><span class="sxs-lookup"><span data-stu-id="a9940-129">Similar to how you would add a negative example file when creating a classifier, you need to add a negative example for the extractor.</span></span> <span data-ttu-id="a9940-130">Voor ons voorbeeld dient dit een bestand te zijn dat geen begindatum waarde voor een service bevat.</span><span class="sxs-lookup"><span data-stu-id="a9940-130">For our example, it should be a file that does not contain a Service Start Date value.</span></span>

1. <span data-ttu-id="a9940-131">Selecteer in de lijst met **gelabelde voorbeelden** een negatief voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="a9940-131">From the **Labeled examples** list, select a negative example.</span></span>
2. <span data-ttu-id="a9940-132">Selecteer in de viewer, bovenaan het artikel, de optie **geen label aanwezig**.</span><span class="sxs-lookup"><span data-stu-id="a9940-132">In the viewer, on the top of the article, select **No label present**.</span></span>
3. <span data-ttu-id="a9940-133">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="a9940-133">Click **Save**.</span></span>
 
<span data-ttu-id="a9940-134">Als u een label hebt met een label van vijf bestanden, wordt u in een banner weergegeven dat u kunt overstappen op de training.</span><span class="sxs-lookup"><span data-stu-id="a9940-134">Once you have labeled five files, a notification banner will display informing you to move to training.</span></span> <span data-ttu-id="a9940-135">U kunt kiezen voor meer documenten of verder naar training.</span><span class="sxs-lookup"><span data-stu-id="a9940-135">You can choose to more documents or advance to training.</span></span> 

## <a name="add-an-explanation"></a><span data-ttu-id="a9940-136">Een uitleg toevoegen</span><span class="sxs-lookup"><span data-stu-id="a9940-136">Add an explanation</span></span>

<span data-ttu-id="a9940-137">Voor ons voorbeeld maken we een uitleg met een beschrijving van de entiteits indeling zelf en variaties in de voorbeelddocumenten.</span><span class="sxs-lookup"><span data-stu-id="a9940-137">For our example, we are going to create an explanation that provides a hint about the entity format itself and variations it may have in the example documents.</span></span> <span data-ttu-id="a9940-138">U kunt bijvoorbeeld een datumwaarde in verschillende notaties, bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="a9940-138">For example,a date value can be in a number of different formats, such as:</span></span>
- <span data-ttu-id="a9940-139">10/14/2019</span><span class="sxs-lookup"><span data-stu-id="a9940-139">10/14/2019</span></span>
- <span data-ttu-id="a9940-140">14 oktober 2019</span><span class="sxs-lookup"><span data-stu-id="a9940-140">October 14, 2019</span></span>
- <span data-ttu-id="a9940-141">Maandag 14 oktober 2019</span><span class="sxs-lookup"><span data-stu-id="a9940-141">Monday, October 14, 2019</span></span>
 

<span data-ttu-id="a9940-142">Om de *begindatum* van de service te identificeren, kunt u een patroon toelichting maken.</span><span class="sxs-lookup"><span data-stu-id="a9940-142">To help identify the *Service Start Date* you can create a pattern explanation.</span></span>

1. <span data-ttu-id="a9940-143">Selecteer in de sectie uitleg de optie **Nieuw**en typ een naam (bijvoorbeeld *datum*).</span><span class="sxs-lookup"><span data-stu-id="a9940-143">In the Explanation section, select **New**, and then type a name (for example, *Date*).</span></span>
2. <span data-ttu-id="a9940-144">Selecteer voor type de optie **patroon lijst**.</span><span class="sxs-lookup"><span data-stu-id="a9940-144">For the Type, select **Pattern list**.</span></span>
3. <span data-ttu-id="a9940-145">Voor de waarde moet u de datumvariant invullen zoals deze in de voorbeeldbestanden worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="a9940-145">For the value, you need to provide the date variation as they appear in the sample files.</span></span> <span data-ttu-id="a9940-146">Als u bijvoorbeeld datumnotaties hebt die worden weergegeven als 0/00/0000, typt u eventuele variaties die in uw documenten kunnen worden weergegeven, zoals:</span><span class="sxs-lookup"><span data-stu-id="a9940-146">For example, if you have date formats that appear as 0/00/0000, you would enter any variations that might appear in your documents, such as:</span></span>
    - <span data-ttu-id="a9940-147">0/0/0000</span><span class="sxs-lookup"><span data-stu-id="a9940-147">0/0/0000</span></span>
    - <span data-ttu-id="a9940-148">0/00/0000</span><span class="sxs-lookup"><span data-stu-id="a9940-148">0/00/0000</span></span>
    - <span data-ttu-id="a9940-149">00/0/0000</span><span class="sxs-lookup"><span data-stu-id="a9940-149">00/0/0000</span></span>
    - <span data-ttu-id="a9940-150">00/00/0000</span><span class="sxs-lookup"><span data-stu-id="a9940-150">00/00/0000</span></span>
4. <span data-ttu-id="a9940-151">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="a9940-151">Select **Save**.</span></span>


### <a name="use-the-explanation-library"></a><span data-ttu-id="a9940-152">De uitleg bibliotheek gebruiken</span><span class="sxs-lookup"><span data-stu-id="a9940-152">Use the Explanation library</span></span>

<span data-ttu-id="a9940-153">Voor het maken van uitleg voor zaken als datums, is het veel eenvoudiger om de uitleg bibliotheek te gebruiken dan voorhand matige invoer van alle variaties.</span><span class="sxs-lookup"><span data-stu-id="a9940-153">For creating explanations for things such as dates, it is much easier to use the explanation library than to manually enter all variations.</span></span> <span data-ttu-id="a9940-154">De uitleg bibliotheek is een set vooraf gedefinieerde tekst en patroon toelichting.</span><span class="sxs-lookup"><span data-stu-id="a9940-154">The explanation library is a set of pre-built phrase and pattern explanations.</span></span> <span data-ttu-id="a9940-155">De bibliotheek probeert alle indelingen te geven voor veelgebruikte woordgroepen of patroon lijsten, zoals datums, telefoonnummers, postcode en vele andere.</span><span class="sxs-lookup"><span data-stu-id="a9940-155">The library tries to provide all formats for common phrase or pattern lists, such as dates, phone numbers, zip code, and many others.</span></span> 

<span data-ttu-id="a9940-156">Voor het voorbeeld van de *begindatum* van een service is het efficiënter om de vooraf samengestelde uitleg voor *datum* in de uitleg bibliotheek te gebruiken:</span><span class="sxs-lookup"><span data-stu-id="a9940-156">For our *Service Start Date* example, it is more efficient to use the pre-built explanation for *Date* in the explanation library:</span></span>

1. <span data-ttu-id="a9940-157">Selecteer in de **sectie uitleg**de optie **Nieuw**en selecteer vervolgens **uit uitleg bibliotheek**.</span><span class="sxs-lookup"><span data-stu-id="a9940-157">In the **Explanation section**,\*\* select **New**, and then select **From explanation library**.</span></span>
2. <span data-ttu-id="a9940-158">Selecteer **datum**in de uitleg bibliotheek.</span><span class="sxs-lookup"><span data-stu-id="a9940-158">From the explanation library, select **Date**.</span></span> <span data-ttu-id="a9940-159">U kunt alle variaties van de datum weergeven die worden herkend.</span><span class="sxs-lookup"><span data-stu-id="a9940-159">You can view all variations of date that will be recognized.</span></span>
3. <span data-ttu-id="a9940-160">Kies **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="a9940-160">Select **Add**.</span></span></br>

    ![Uitleg bibliotheek](../media/content-understanding/explanation-library.png) 

4. <span data-ttu-id="a9940-162">Op de pagina **een uitleg maken** worden in de datuminformatie uit de uitleg bibliotheek de velden automatisch *bijgewerkt* .</span><span class="sxs-lookup"><span data-stu-id="a9940-162">On the **Create an explanation** page, the *Date* information from the explanation library will autofill the fields.</span></span> <span data-ttu-id="a9940-163">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="a9940-163">Select **Save**.</span></span></br>

    ![Uitleg bibliotheek](../media/content-understanding/date-explanation-library.png) 

 
## <a name="train-the-model"></a><span data-ttu-id="a9940-165">Het model trainen</span><span class="sxs-lookup"><span data-stu-id="a9940-165">Train the model</span></span> 

<span data-ttu-id="a9940-166">Als u uw uitleg opslaat, begint de training.</span><span class="sxs-lookup"><span data-stu-id="a9940-166">Saving your explanation will start the training.</span></span> <span data-ttu-id="a9940-167">Als uw model voldoende informatie bevat voor het extraheren van de gegevens uit de voorbeeldbestanden met labels, wordt elk bestand weergegeven met de **naam van het**bestand.</span><span class="sxs-lookup"><span data-stu-id="a9940-167">If your model has enough information to extract the data from your labeled example files, you will see each file labeled with **Match**.</span></span>  

![Uitleg bibliotheek](../media/content-understanding/match2.png) 

<span data-ttu-id="a9940-169">Als de uitleg niet voldoende informatie bevat om de gegevens te vinden die u wilt extraheren, wordt elk bestand aangeduid met een **overeenkomende**naam.</span><span class="sxs-lookup"><span data-stu-id="a9940-169">If the explanation does not have enough information to find the data you want to extract, each file will be labeled with **Mismatch**.</span></span> <span data-ttu-id="a9940-170">U kunt op de niet-gerelateerde bestanden klikken om meer informatie weer te geven over de reden waarom het niet klopt.</span><span class="sxs-lookup"><span data-stu-id="a9940-170">You can click on the Mismatched files to see more information about why there was a mismatch.</span></span>


## <a name="add-another-explanation"></a><span data-ttu-id="a9940-171">Nog een uitleg toevoegen</span><span class="sxs-lookup"><span data-stu-id="a9940-171">Add another explanation</span></span>

<span data-ttu-id="a9940-172">Vaak is de door u verstrekte uitleg niet voldoende informatie verstrekt om de begindatum waarde van de service uit te pakken, zodat deze overeenkomt met de gelabelde bestanden.</span><span class="sxs-lookup"><span data-stu-id="a9940-172">Often the mismatch is an indication that the explanation we provided did not provide enough information to extract the service start date value to match our labeled files.</span></span> <span data-ttu-id="a9940-173">Mogelijk moet u deze bewerken of een andere uitleg toevoegen.</span><span class="sxs-lookup"><span data-stu-id="a9940-173">You may need to edit it, or add another explanation.</span></span>

<span data-ttu-id="a9940-174">Voor ons voorbeeld ziet u dat de tekst *van de begindatum van* de tekenreeks altijd voorafgaat aan de werkelijke waarde.</span><span class="sxs-lookup"><span data-stu-id="a9940-174">For our example, we notice that the text string *Start Service date of* always precedes the actual value.</span></span> <span data-ttu-id="a9940-175">Om de begindatum van de service te identificeren, kunnen we een uitleg van de zinnen maken.</span><span class="sxs-lookup"><span data-stu-id="a9940-175">To help identify the Service Start Date we can create a phrase explanation.</span></span>

1. <span data-ttu-id="a9940-176">Selecteer in de sectie uitleg de optie **Nieuw**en typ een naam (bijvoorbeeld de prefix- *tekenreeks*).</span><span class="sxs-lookup"><span data-stu-id="a9940-176">In the Explanation section, select **New**, and then type a name (for example, *Prefix String*).</span></span>
2. <span data-ttu-id="a9940-177">Selecteer in het vak Type de optie **phrase**.</span><span class="sxs-lookup"><span data-stu-id="a9940-177">For the Type, select **Phrase list**.</span></span>
3. <span data-ttu-id="a9940-178">Gebruik de *begindatum van de service* als de waarde.</span><span class="sxs-lookup"><span data-stu-id="a9940-178">Use *Service Start Date of* as the value.</span></span>
4. <span data-ttu-id="a9940-179">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="a9940-179">Select **Save**.</span></span>

    ![Uitleg bibliotheek](../media/content-understanding/prefix-string.png) 


## <a name="train-the-model"></a><span data-ttu-id="a9940-181">Het model trainen</span><span class="sxs-lookup"><span data-stu-id="a9940-181">Train the model</span></span>

<span data-ttu-id="a9940-182">Als u uw uitleg opslaat, wordt deze keer opnieuw gestart met beide uitleg in ons voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="a9940-182">Saving your explanation will start the training again, this time using both explanations in our example.</span></span> <span data-ttu-id="a9940-183">Als uw model voldoende informatie bevat voor het extraheren van de gegevens uit de voorbeeldbestanden met labels, wordt elk bestand weergegeven met de **naam van het**bestand.</span><span class="sxs-lookup"><span data-stu-id="a9940-183">If your model has enough information to extract the data from your labeled example files, you will see each file labeled with **Match**.</span></span> 

<span data-ttu-id="a9940-184">Als u weer een **niet-overeenkomend** bestand met gelabelde bestanden ontvangt, moet u mogelijk een andere uitleg maken om het documenttype te identificeren of om wijzigingen aan te brengen in de bestaande mappen.</span><span class="sxs-lookup"><span data-stu-id="a9940-184">If you again receive a **Mismatch** on your labeled files, you may need to create another explanation to provide the model more information to identify the document type, or look at making changes to your existing ones.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="a9940-185">Uw model testen</span><span class="sxs-lookup"><span data-stu-id="a9940-185">Test your model</span></span>

<span data-ttu-id="a9940-186">Als u een overeenkomst met de gelabelde voorbeeldbestanden hebt ontvangen, kunt u de naam van uw model testen in de resterende voorbeeldbestanden met bijschriften.</span><span class="sxs-lookup"><span data-stu-id="a9940-186">If you received a match on your labeled example files, you can now test your model on your remaining unlabeled example files.</span></span>

1. <span data-ttu-id="a9940-187">Klik op de startpagina van het model op het tabblad **testen** .  Het model wordt uitgevoerd in uw niet-gelabelde voorbeeldbestanden.</span><span class="sxs-lookup"><span data-stu-id="a9940-187">On the model home page, click the **Test** tab.  This will run the model on your unlabeled example files.</span></span>
2. <span data-ttu-id="a9940-188">In de lijst **test bestanden** worden de voorbeeldbestanden weergegeven en wordt weergegeven of de gegevens die u nodig hebt, in het model kunnen worden opgehaald.</span><span class="sxs-lookup"><span data-stu-id="a9940-188">In the **Test files** list, your example files will display and will show if the model is able to extract the information you need from them.</span></span> <span data-ttu-id="a9940-189">U kunt deze gegevens gebruiken om de effectiviteit van uw classificatie voor het identificeren van uw documenten te bepalen.</span><span class="sxs-lookup"><span data-stu-id="a9940-189">You can use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![Uw bestanden testen](../media/content-understanding/test-filies-extractor.png) 

## <a name="see-also"></a><span data-ttu-id="a9940-191">Zie ook</span><span class="sxs-lookup"><span data-stu-id="a9940-191">See Also</span></span>
  




