---
title: Een afzuigkap maken (Voorbeeld)
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
description: Meer informatie over het maken van een afzuigkap
ms.openlocfilehash: 76cb17df069c6905080baabb0b57d765fe5cc94c
ms.sourcegitcommit: 3a47efcbdf3d2b39caa2798ea5be806839b05ed1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/01/2020
ms.locfileid: "46540104"
---
# <a name="create-an-extractor-preview"></a><span data-ttu-id="aab34-103">Een afzuigkap maken (Voorbeeld)</span><span class="sxs-lookup"><span data-stu-id="aab34-103">Create an extractor (Preview)</span></span>
> [!Note] 
> <span data-ttu-id="aab34-104">De inhoud in dit artikel is voor Project Cortex Private Preview.</span><span class="sxs-lookup"><span data-stu-id="aab34-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="aab34-105">[Lees meer over Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="aab34-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL2G]

</br> 

<span data-ttu-id="aab34-106">Voor of nadat u een classificatiemodel hebt gemaakt om de identificatie en classificatie van specifieke documenttypen te automatiseren, u er optioneel voor kiezen om afzuigers toe te voegen aan uw model om specifieke informatie uit deze documenten te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="aab34-106">Either before or after you create a classifier model to automate identification and classification of specific document types, you can optionally choose to add extractors to your model to pull out specific information from these documents.</span></span> <span data-ttu-id="aab34-107">U wilt bijvoorbeeld dat uw model niet alleen alle *contractverlengingsdocumenten* identificeert die aan uw documentbibliotheek zijn toegevoegd, maar ook de *begindatum van* de service voor elk document weergeven als kolom in de documentbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="aab34-107">For example, you may want your model not only to identify all *Contract Renewal* documents that are added to your document library, but to also display the *Service Start date* for each document as a column in the document library.</span></span>

<span data-ttu-id="aab34-108">U moet een afzuigkap maken voor elke entiteit in het document dat u wilt extraheren.</span><span class="sxs-lookup"><span data-stu-id="aab34-108">You need to create an extractor for each entity in the document that you want to extract.</span></span> <span data-ttu-id="aab34-109">In ons voorbeeld willen we de *begindatum* van de service extraheren voor elk document *voor contractverlenging* dat wordt geïdentificeerd door het model.</span><span class="sxs-lookup"><span data-stu-id="aab34-109">In our example, we want to extract the *Service Start Date* for each *Contract Renewal* document that is identified by the model.</span></span> <span data-ttu-id="aab34-110">We willen een weergave kunnen zien in de documentbibliotheek van alle documenten *voor contractverlenging,* met een kolom met de datum waarde van de begindatum van de service van elk document.</span><span class="sxs-lookup"><span data-stu-id="aab34-110">We want to be able to see a view in the document library of all *Contract Renewal* documents, with a column that shows the Service Start date value of each document.</span></span>

> [!Note]
> <span data-ttu-id="aab34-111">Voordat u een afzuigkap maakt, moet u [uw voorbeeldbestanden toevoegen](https://docs.microsoft.com/microsoft-365/contentunderstanding/create-a-classifier?view=o365-worldwide#add-your-example-files) die u nodig hebt om het model te trainen om de informatie te identificeren die u wilt extraheren.</span><span class="sxs-lookup"><span data-stu-id="aab34-111">Before creating an extractor, you need to [add your example files](https://docs.microsoft.com/microsoft-365/contentunderstanding/create-a-classifier?view=o365-worldwide#add-your-example-files) you will need to help train the model to identify the information you want to extract.</span></span> <span data-ttu-id="aab34-112">Gebruik dezelfde voorbeeldbestanden die u hebt gebruikt om uw classificatie te maken.</span><span class="sxs-lookup"><span data-stu-id="aab34-112">Use the same example files you used to create your classifier.</span></span>


## <a name="name-your-extractor"></a><span data-ttu-id="aab34-113">Geef uw afzuiger een naam</span><span class="sxs-lookup"><span data-stu-id="aab34-113">Name your extractor</span></span>

1. <span data-ttu-id="aab34-114">Klik op de startpagina van het model in de tegel **Extrahers maken en trainen** op **Treinextracor**.</span><span class="sxs-lookup"><span data-stu-id="aab34-114">On the model home page, in the **Create and train extractors** tile, click **Train extractor**.</span></span>
2. <span data-ttu-id="aab34-115">Typ in het scherm **Nieuwe entiteitsafzuig** de naam van uw afzuigkap in het veld **Nieuwe afzuignaam.**</span><span class="sxs-lookup"><span data-stu-id="aab34-115">On the **New entity extractor** screen, type the name of your extractor in the **New extractor name** field.</span></span> <span data-ttu-id="aab34-116">We kunnen het bijvoorbeeld **de begindatum van de service** benoemen als we de begindatum van de service uit elk document voor contractverlenging willen halen.</span><span class="sxs-lookup"><span data-stu-id="aab34-116">For example, we can name it **Service Start Date** if we want to extract the service start date from each Contract Renewal document.</span></span>
3. <span data-ttu-id="aab34-117">Klik op **Maken**.</span><span class="sxs-lookup"><span data-stu-id="aab34-117">Click **Create**.</span></span>

## <a name="add-a-label"></a><span data-ttu-id="aab34-118">Een label toevoegen</span><span class="sxs-lookup"><span data-stu-id="aab34-118">Add a label</span></span>

<span data-ttu-id="aab34-119">De volgende stap is het labelen van de informatie die u wilt extraheren in uw voorbeeldtrainingsbestanden.</span><span class="sxs-lookup"><span data-stu-id="aab34-119">The next step is to label the information you want to extract in your example training files.</span></span>

<span data-ttu-id="aab34-120">Als u de uitzuigkap maakt, opent u de uitzuigpagina waarin u een lijst met uw voorbeeldbestanden ziet, waarbij het eerste bestand in de lijst in de viewer wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="aab34-120">Creating the extractor will open the extractor page in which you will see a list of your example files, with the first file on the list displayed in the viewer.</span></span>

1. <span data-ttu-id="aab34-121">Selecteer in de viewer de gegevens die u uit de bestanden wilt halen.</span><span class="sxs-lookup"><span data-stu-id="aab34-121">In the viewer, select the data that you want to extract from the files.</span></span> <span data-ttu-id="aab34-122">Als u bijvoorbeeld de *servicedatum start*wilt extraheren, markeert u de datumwaarde hiervoor in het eerste bestand *(maandag 14 oktober 2019).*</span><span class="sxs-lookup"><span data-stu-id="aab34-122">For example, if you want to extract the *Start Service Date*, you will highlight the date value for it in the first file (*Monday, October 14, 2019*).</span></span> <span data-ttu-id="aab34-123">Klik vervolgens op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="aab34-123">Then click **Save**.</span></span>  <span data-ttu-id="aab34-124">U ziet de waardeweergave voor het bestand in de lijst Met gelabelde voorbeelden onder de kolom **Label.**</span><span class="sxs-lookup"><span data-stu-id="aab34-124">You will see the value display for the file in the Labeled examples list under the **Label** column.</span></span>
2. <span data-ttu-id="aab34-125">Selecteer **Volgende bestand** om automatisch te worden weergegeven en open het volgende bestand in de lijst in de viewer of u **Opslaan** selecteren en een ander bestand selecteren in de lijst **Met gelabelde voorbeelden.**</span><span class="sxs-lookup"><span data-stu-id="aab34-125">Select **Next file** to autosave and open the next file in the list in the viewer, or you can select **Save** and select another file from the **Labeled examples** list.</span></span>
3. <span data-ttu-id="aab34-126">Herhaal in de viewer stap 1 en 2 en doe dit totdat u het label in vijf bestanden hebt opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="aab34-126">In the viewer, repeat steps 1 and 2, and do this until you have saved the label in five files.</span></span>

    ![Geavanceerde instellingen](../media/content-understanding/select-service-start-date.png) 


### <a name="add-a-negative-example"></a><span data-ttu-id="aab34-128">Een negatief voorbeeld toevoegen</span><span class="sxs-lookup"><span data-stu-id="aab34-128">Add a negative example</span></span>

<span data-ttu-id="aab34-129">Net als bij het toevoegen van een negatief voorbeeldbestand bij het maken van een classificatie, moet u een negatief voorbeeld voor de afzuigkap toevoegen.</span><span class="sxs-lookup"><span data-stu-id="aab34-129">Similar to how you would add a negative example file when creating a classifier, you need to add a negative example for the extractor.</span></span> <span data-ttu-id="aab34-130">Voor ons voorbeeld moet het een bestand zijn dat geen begindatumwaarde van de service bevat.</span><span class="sxs-lookup"><span data-stu-id="aab34-130">For our example, it should be a file that does not contain a Service Start Date value.</span></span>

1. <span data-ttu-id="aab34-131">Selecteer in de lijst **Met gelabelde voorbeelden** een negatief voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="aab34-131">From the **Labeled examples** list, select a negative example.</span></span>
2. <span data-ttu-id="aab34-132">Selecteer in de viewer boven aan het artikel **Geen label aanwezig**.</span><span class="sxs-lookup"><span data-stu-id="aab34-132">In the viewer, on the top of the article, select **No label present**.</span></span>
3. <span data-ttu-id="aab34-133">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="aab34-133">Click **Save**.</span></span>
 
<span data-ttu-id="aab34-134">Zodra u vijf bestanden hebt gelabeld, wordt er een meldingsbanner weergegeven waarin u wordt geïnformeerd om over te gaan tot training.</span><span class="sxs-lookup"><span data-stu-id="aab34-134">Once you have labeled five files, a notification banner will display informing you to move to training.</span></span> <span data-ttu-id="aab34-135">U ervoor kiezen om meer documenten of vooraf aan de opleiding.</span><span class="sxs-lookup"><span data-stu-id="aab34-135">You can choose to more documents or advance to training.</span></span> 

## <a name="add-an-explanation"></a><span data-ttu-id="aab34-136">Een uitleg toevoegen</span><span class="sxs-lookup"><span data-stu-id="aab34-136">Add an explanation</span></span>

<span data-ttu-id="aab34-137">We gaan bijvoorbeeld een uitleg maken die een hint geeft over de entiteitsindeling zelf en variaties die deze in de voorbeelddocumenten kan hebben.</span><span class="sxs-lookup"><span data-stu-id="aab34-137">For our example, we are going to create an explanation that provides a hint about the entity format itself and variations it may have in the example documents.</span></span> <span data-ttu-id="aab34-138">Een datumwaarde kan bijvoorbeeld in een aantal verschillende indelingen zijn, zoals:</span><span class="sxs-lookup"><span data-stu-id="aab34-138">For example,a date value can be in a number of different formats, such as:</span></span>
- <span data-ttu-id="aab34-139">10/14/2019</span><span class="sxs-lookup"><span data-stu-id="aab34-139">10/14/2019</span></span>
- <span data-ttu-id="aab34-140">14 oktober 2019</span><span class="sxs-lookup"><span data-stu-id="aab34-140">October 14, 2019</span></span>
- <span data-ttu-id="aab34-141">Maandag 14 oktober 2019</span><span class="sxs-lookup"><span data-stu-id="aab34-141">Monday, October 14, 2019</span></span>
 

<span data-ttu-id="aab34-142">Om de *startdatum van* de service te identificeren, u een patroonuitleg maken.</span><span class="sxs-lookup"><span data-stu-id="aab34-142">To help identify the *Service Start Date* you can create a pattern explanation.</span></span>

1. <span data-ttu-id="aab34-143">Selecteer in de sectie Uitleg de optie **Nieuw**en typ een naam (bijvoorbeeld *Datum).*</span><span class="sxs-lookup"><span data-stu-id="aab34-143">In the Explanation section, select **New**, and then type a name (for example, *Date*).</span></span>
2. <span data-ttu-id="aab34-144">Selecteer voor tekst **de lijst Patroon**.</span><span class="sxs-lookup"><span data-stu-id="aab34-144">For the Type, select **Pattern list**.</span></span>
3. <span data-ttu-id="aab34-145">Voor de waarde moet u de datumvariatie ops geven zoals deze in de voorbeeldbestanden worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="aab34-145">For the value, you need to provide the date variation as they appear in the sample files.</span></span> <span data-ttu-id="aab34-146">Als u bijvoorbeeld datumnotaties hebt die worden weergegeven als 0/00/0000, voert u eventuele wijzigingen in die in uw documenten kunnen worden weergegeven, zoals:</span><span class="sxs-lookup"><span data-stu-id="aab34-146">For example, if you have date formats that appear as 0/00/0000, you would enter any variations that might appear in your documents, such as:</span></span>
    - <span data-ttu-id="aab34-147">0/0/0000</span><span class="sxs-lookup"><span data-stu-id="aab34-147">0/0/0000</span></span>
    - <span data-ttu-id="aab34-148">0/00/0000</span><span class="sxs-lookup"><span data-stu-id="aab34-148">0/00/0000</span></span>
    - <span data-ttu-id="aab34-149">00/0/0000</span><span class="sxs-lookup"><span data-stu-id="aab34-149">00/0/0000</span></span>
    - <span data-ttu-id="aab34-150">00/00/0000</span><span class="sxs-lookup"><span data-stu-id="aab34-150">00/00/0000</span></span>
4. <span data-ttu-id="aab34-151">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="aab34-151">Select **Save**.</span></span>


### <a name="use-the-explanation-library"></a><span data-ttu-id="aab34-152">De bibliotheek Uitleg gebruiken</span><span class="sxs-lookup"><span data-stu-id="aab34-152">Use the Explanation library</span></span>

<span data-ttu-id="aab34-153">Voor het maken van uitleg voor zaken als datums is het veel gemakkelijker om de uitlegbibliotheek te gebruiken dan om alle varianten handmatig in te voeren.</span><span class="sxs-lookup"><span data-stu-id="aab34-153">For creating explanations for things such as dates, it is much easier to use the explanation library than to manually enter all variations.</span></span> <span data-ttu-id="aab34-154">De uitlegbibliotheek is een set vooraf gebouwde woord- en patroonuitleg.</span><span class="sxs-lookup"><span data-stu-id="aab34-154">The explanation library is a set of pre-built phrase and pattern explanations.</span></span> <span data-ttu-id="aab34-155">De bibliotheek probeert alle indelingen voor algemene woordgroepen of patroonlijsten te bieden, zoals datums, telefoonnummers, postcode en vele andere.</span><span class="sxs-lookup"><span data-stu-id="aab34-155">The library tries to provide all formats for common phrase or pattern lists, such as dates, phone numbers, zip code, and many others.</span></span> 

<span data-ttu-id="aab34-156">Voor ons voorbeeld *van de startdatum van* de service is het efficiënter om de vooraf gebouwde uitleg voor *Datum* in de uitlegbibliotheek te gebruiken:</span><span class="sxs-lookup"><span data-stu-id="aab34-156">For our *Service Start Date* example, it is more efficient to use the pre-built explanation for *Date* in the explanation library:</span></span>

1. <span data-ttu-id="aab34-157">Selecteer **In**de sectie Uitleg ,\*\* selecteer **Nieuw**en selecteer **Vervolgens Uit uitlegbibliotheek**.</span><span class="sxs-lookup"><span data-stu-id="aab34-157">In the **Explanation section**,\*\* select **New**, and then select **From explanation library**.</span></span>
2. <span data-ttu-id="aab34-158">Selecteer **Datum**in de uitlegbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="aab34-158">From the explanation library, select **Date**.</span></span> <span data-ttu-id="aab34-159">U alle datumvariaties bekijken die worden herkend.</span><span class="sxs-lookup"><span data-stu-id="aab34-159">You can view all variations of date that will be recognized.</span></span>
3. <span data-ttu-id="aab34-160">Kies **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="aab34-160">Select **Add**.</span></span></br>

    ![Uitlegbibliotheek](../media/content-understanding/explanation-library.png) 

4. <span data-ttu-id="aab34-162">Op de pagina **Een uitleg maken** worden de velden automatisch ingevuld met de *datumgegevens* uit de uitlegbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="aab34-162">On the **Create an explanation** page, the *Date* information from the explanation library will autofill the fields.</span></span> <span data-ttu-id="aab34-163">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="aab34-163">Select **Save**.</span></span></br>

    ![Uitlegbibliotheek](../media/content-understanding/date-explanation-library.png) 

 
## <a name="train-the-model"></a><span data-ttu-id="aab34-165">Train het model</span><span class="sxs-lookup"><span data-stu-id="aab34-165">Train the model</span></span> 

<span data-ttu-id="aab34-166">Het opslaan van uw uitleg zal beginnen met de training.</span><span class="sxs-lookup"><span data-stu-id="aab34-166">Saving your explanation will start the training.</span></span> <span data-ttu-id="aab34-167">Als uw model voldoende informatie heeft om de gegevens uit uw gelabelde voorbeeldbestanden te extraheren, ziet u elk bestand met het label **Match**.</span><span class="sxs-lookup"><span data-stu-id="aab34-167">If your model has enough information to extract the data from your labeled example files, you will see each file labeled with **Match**.</span></span>  

![Uitlegbibliotheek](../media/content-understanding/match2.png) 

<span data-ttu-id="aab34-169">Als de uitleg niet genoeg informatie heeft om de gegevens te vinden die u wilt extraheren, wordt elk bestand gelabeld met **Mismatch**.</span><span class="sxs-lookup"><span data-stu-id="aab34-169">If the explanation does not have enough information to find the data you want to extract, each file will be labeled with **Mismatch**.</span></span> <span data-ttu-id="aab34-170">U op de verkeerde bestanden klikken om meer informatie te zien over waarom er een mismatch was.</span><span class="sxs-lookup"><span data-stu-id="aab34-170">You can click on the Mismatched files to see more information about why there was a mismatch.</span></span>


## <a name="add-another-explanation"></a><span data-ttu-id="aab34-171">Een andere uitleg toevoegen</span><span class="sxs-lookup"><span data-stu-id="aab34-171">Add another explanation</span></span>

<span data-ttu-id="aab34-172">Vaak is de mismatch een indicatie dat de uitleg die we hebben gegeven niet genoeg informatie heeft verstrekt om de begindatum van de service te extraheren die overeenkomt met onze gelabelde bestanden.</span><span class="sxs-lookup"><span data-stu-id="aab34-172">Often the mismatch is an indication that the explanation we provided did not provide enough information to extract the service start date value to match our labeled files.</span></span> <span data-ttu-id="aab34-173">Mogelijk moet u het bewerken of een andere uitleg toevoegen.</span><span class="sxs-lookup"><span data-stu-id="aab34-173">You may need to edit it, or add another explanation.</span></span>

<span data-ttu-id="aab34-174">We merken bijvoorbeeld dat de *begindatum van* de tekenreeks Service altijd voorafgaat aan de werkelijke waarde.</span><span class="sxs-lookup"><span data-stu-id="aab34-174">For our example, we notice that the text string *Start Service date of* always precedes the actual value.</span></span> <span data-ttu-id="aab34-175">Om de startdatum van de service te identificeren, kunnen we een woordgroepsverklaring maken.</span><span class="sxs-lookup"><span data-stu-id="aab34-175">To help identify the Service Start Date we can create a phrase explanation.</span></span>

1. <span data-ttu-id="aab34-176">Selecteer in de sectie Uitleg de optie **Nieuw**en typ een naam (bijvoorbeeld *voorvoegselreeks).*</span><span class="sxs-lookup"><span data-stu-id="aab34-176">In the Explanation section, select **New**, and then type a name (for example, *Prefix String*).</span></span>
2. <span data-ttu-id="aab34-177">Selecteer Voor tekst **de lijst Zinsgroepen**.</span><span class="sxs-lookup"><span data-stu-id="aab34-177">For the Type, select **Phrase list**.</span></span>
3. <span data-ttu-id="aab34-178">Gebruik *de begindatum van* de service als waarde.</span><span class="sxs-lookup"><span data-stu-id="aab34-178">Use *Service Start Date of* as the value.</span></span>
4. <span data-ttu-id="aab34-179">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="aab34-179">Select **Save**.</span></span>

    ![Uitlegbibliotheek](../media/content-understanding/prefix-string.png) 


## <a name="train-the-model"></a><span data-ttu-id="aab34-181">Train het model</span><span class="sxs-lookup"><span data-stu-id="aab34-181">Train the model</span></span>

<span data-ttu-id="aab34-182">Het opslaan van uw uitleg zal de training opnieuw beginnen, dit keer met behulp van beide uitleg in ons voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="aab34-182">Saving your explanation will start the training again, this time using both explanations in our example.</span></span> <span data-ttu-id="aab34-183">Als uw model voldoende informatie heeft om de gegevens uit uw gelabelde voorbeeldbestanden te extraheren, ziet u elk bestand met het label **Match**.</span><span class="sxs-lookup"><span data-stu-id="aab34-183">If your model has enough information to extract the data from your labeled example files, you will see each file labeled with **Match**.</span></span> 

<span data-ttu-id="aab34-184">Als u opnieuw een **Mismatch** ontvangt op uw gelabelde bestanden, moet u mogelijk een andere uitleg maken om het model meer informatie te geven om het documenttype te identificeren of om wijzigingen aan te brengen in uw bestaande bestanden.</span><span class="sxs-lookup"><span data-stu-id="aab34-184">If you again receive a **Mismatch** on your labeled files, you may need to create another explanation to provide the model more information to identify the document type, or look at making changes to your existing ones.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="aab34-185">Test uw model</span><span class="sxs-lookup"><span data-stu-id="aab34-185">Test your model</span></span>

<span data-ttu-id="aab34-186">Als u een overeenkomst hebt ontvangen in uw gelabelde voorbeeldbestanden, u uw model nu testen op uw resterende niet-gelabelde voorbeeldbestanden.</span><span class="sxs-lookup"><span data-stu-id="aab34-186">If you received a match on your labeled example files, you can now test your model on your remaining unlabeled example files.</span></span>

1. <span data-ttu-id="aab34-187">Klik op de startpagina van het model op het tabblad **Testen.**  Hiermee wordt het model uitgevoerd op uw niet-gelabelde voorbeeldbestanden.</span><span class="sxs-lookup"><span data-stu-id="aab34-187">On the model home page, click the **Test** tab.  This will run the model on your unlabeled example files.</span></span>
2. <span data-ttu-id="aab34-188">In de lijst **Bestanden testen** worden uw voorbeeldbestanden weergegeven en wordt weergegeven of het model de informatie kan extraheren die u nodig hebt.</span><span class="sxs-lookup"><span data-stu-id="aab34-188">In the **Test files** list, your example files will display and will show if the model is able to extract the information you need from them.</span></span> <span data-ttu-id="aab34-189">U deze informatie gebruiken om de effectiviteit van uw classificatie te bepalen bij het identificeren van uw documenten.</span><span class="sxs-lookup"><span data-stu-id="aab34-189">You can use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![Testen op uw bestanden](../media/content-understanding/test-filies-extractor.png) 

## <a name="see-also"></a><span data-ttu-id="aab34-191">Zie ook</span><span class="sxs-lookup"><span data-stu-id="aab34-191">See Also</span></span>
  




