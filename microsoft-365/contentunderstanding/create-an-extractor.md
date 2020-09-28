---
title: Een extractor maken
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
description: Meer informatie over het maken van een extractor in Microsoft SharePoint Syntex.
ms.openlocfilehash: 740df6769b3a1675e4e1691f84d164312b15567c
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295454"
---
# <a name="create-an-extractor-preview"></a><span data-ttu-id="e2c4a-103">Een extractor maken (preview)</span><span class="sxs-lookup"><span data-stu-id="e2c4a-103">Create an extractor (Preview)</span></span>

<span data-ttu-id="e2c4a-104">De inhoud in dit artikel is bedoeld voor de cortex van de private preview van project.</span><span class="sxs-lookup"><span data-stu-id="e2c4a-104">The content in this article is for the Project Cortex Private Preview.</span></span> <span data-ttu-id="e2c4a-105">[Lees meer over project cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="e2c4a-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL2G]

</br> 

<span data-ttu-id="e2c4a-106">Voordat of nadat u een classificatiemodel hebt gemaakt om het identificeren en classificeren van specifieke documenttypen te automatiseren, kunt u ervoor kiezen om extra informatie toe te voegen aan uw model om bepaalde informatie uit deze documenten uit te pakken.</span><span class="sxs-lookup"><span data-stu-id="e2c4a-106">Before or after you create a classifier model to automate identification and classification of specific document types, you can optionally choose to add extractors to your model to pull out specific information from these documents.</span></span> <span data-ttu-id="e2c4a-107">U wilt bijvoorbeeld dat uw model niet alleen alle documenten voor het vernieuwen van een *contract* toevoegt aan uw documentbibliotheek, maar u kunt ook de *begindatum* van de service voor elk document weergeven als een kolom in de documentbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="e2c4a-107">For example, you may want your model not only to identify all *Contract Renewal* documents added to your document library, but also to display the *Service Start date* for each document as a column in the document library.</span></span>

<span data-ttu-id="e2c4a-108">U moet een extractor maken voor elke entiteit in het document die u wilt extraheren.</span><span class="sxs-lookup"><span data-stu-id="e2c4a-108">You need to create an extractor for each entity in the document that you want to extract.</span></span> <span data-ttu-id="e2c4a-109">In het voorbeeld wilt u de *begindatum* van de service uitpakken voor elk document voor het *verlengen* van documenten dat door het model wordt geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="e2c4a-109">In the sample, you want to extract the *Service Start Date* for each *Contract Renewal* document that is identified by the model.</span></span> <span data-ttu-id="e2c4a-110">Dit moet gebeuren wanneer u een weergave wilt weergeven in de documentbibliotheek van alle documenten voor het verlengen van het *contract* met een kolom met de begindatum waarde van een service voor elk document.</span><span class="sxs-lookup"><span data-stu-id="e2c4a-110">This must happen when you want to see a view in the document library of all the *Contract Renewal* documents with a column showing the Service Start date value for each document.</span></span>

> [!NOTE]
> <span data-ttu-id="e2c4a-111">Voordat u een Extractor maakt, moet u de [voorbeeldbestanden toevoegen](https://docs.microsoft.com/microsoft-365/contentunderstanding/create-a-classifier#add-your-example-files) om het model te leren bieden om de informatie die u wilt extraheren te identificeren.</span><span class="sxs-lookup"><span data-stu-id="e2c4a-111">Before creating an extractor, you need to [add your example files](https://docs.microsoft.com/microsoft-365/contentunderstanding/create-a-classifier#add-your-example-files) to help train the model to identify the information you want to extract.</span></span> <span data-ttu-id="e2c4a-112">Gebruik de voorbeeldbestanden die u hebt gebruikt om uw classificatie te maken.</span><span class="sxs-lookup"><span data-stu-id="e2c4a-112">Use the same sample files you used to create your classifier.</span></span>

## <a name="name-your-extractor"></a><span data-ttu-id="e2c4a-113">Naam van de extractor</span><span class="sxs-lookup"><span data-stu-id="e2c4a-113">Name your extractor</span></span>

1. <span data-ttu-id="e2c4a-114">Klik op de startpagina van het model in de tegel **extracten maken en trainen** op **Train Extractor**.</span><span class="sxs-lookup"><span data-stu-id="e2c4a-114">From the model home page, in the **Create and train extractors** tile, click **Train extractor**.</span></span>
2. <span data-ttu-id="e2c4a-115">Typ in het scherm **nieuwe entiteits Extractor** de naam van het extractor in het veld **nieuwe naam** van de extractie.</span><span class="sxs-lookup"><span data-stu-id="e2c4a-115">On the **New entity extractor** screen, type the name of your extractor in the **New extractor name** field.</span></span> <span data-ttu-id="e2c4a-116">Als u bijvoorbeeld de naam van de service starten als u de begindatum van de service wilt extraheren uit het document **voor het verlengen** van het contract.</span><span class="sxs-lookup"><span data-stu-id="e2c4a-116">For example, name it **Service Start Date** if you want to extract the service start date from each Contract Renewal document.</span></span>
3. <span data-ttu-id="e2c4a-117">Klik op **Maken**.</span><span class="sxs-lookup"><span data-stu-id="e2c4a-117">Click **Create**.</span></span>

## <a name="add-a-label"></a><span data-ttu-id="e2c4a-118">Een label toevoegen</span><span class="sxs-lookup"><span data-stu-id="e2c4a-118">Add a label</span></span>

<span data-ttu-id="e2c4a-119">De volgende stap is het markeren van de gegevens die u wilt extraheren in de voorbeeldbestanden van uw voorkeuren.</span><span class="sxs-lookup"><span data-stu-id="e2c4a-119">The next step is to label the information you want to extract in your sample training files.</span></span>

<span data-ttu-id="e2c4a-120">Door de Extractor te maken opent u de extractor-pagina.</span><span class="sxs-lookup"><span data-stu-id="e2c4a-120">Creating the extractor opens the extractor page.</span></span> <span data-ttu-id="e2c4a-121">Hier ziet u een overzicht van de voorbeeldbestanden, waarbij het eerste bestand in de lijst wordt weergegeven in de viewer.</span><span class="sxs-lookup"><span data-stu-id="e2c4a-121">Here you see a list of your sample files, with the first file on the list displayed in the viewer.</span></span>

1. <span data-ttu-id="e2c4a-122">Selecteer de gegevens die u wilt extraheren uit de bestanden in de viewer.</span><span class="sxs-lookup"><span data-stu-id="e2c4a-122">From the viewer, select the data that you want to extract from the files.</span></span> <span data-ttu-id="e2c4a-123">Als u bijvoorbeeld de *begindatum*van de service wilt extraheren, markeert u de datumwaarde in het eerste bestand (*maandag, 14 oktober 2019*).</span><span class="sxs-lookup"><span data-stu-id="e2c4a-123">For example, if you want to extract the *Start Service Date*, you highlight the date value in the first file (*Monday, October 14, 2019*).</span></span> <span data-ttu-id="e2c4a-124">en klikt u vervolgens op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="e2c4a-124">and then click **Save**.</span></span>  <span data-ttu-id="e2c4a-125">De weergave van de waarde in het bestand wordt weergegeven in de lijst met gelabelde voorbeelden, onder de kolom **etiket** .</span><span class="sxs-lookup"><span data-stu-id="e2c4a-125">You should see the value display from the file in the Labeled examples list, under the **Label** column.</span></span>
2. <span data-ttu-id="e2c4a-126">Selecteer **volgende bestand** om automatisch op te slaan en het volgende bestand in de lijst in de viewer te openen.</span><span class="sxs-lookup"><span data-stu-id="e2c4a-126">Select **Next file** to auto save and open the next file in the list in the viewer.</span></span> <span data-ttu-id="e2c4a-127">Of selecteer **Opslaan** en selecteer vervolgens een ander bestand in de lijst met **gelabelde voorbeelden** .</span><span class="sxs-lookup"><span data-stu-id="e2c4a-127">Or select **Save** and then select another file from the **Labeled examples** list.</span></span>
3. <span data-ttu-id="e2c4a-128">Herhaal de stappen 1 en 2 in de viewer en herhaal dit tot u het etiket in de vijf bestanden hebt opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="e2c4a-128">In the viewer, repeat steps 1 and 2, then repeat until you saved the label in all five files.</span></span>

    ![Geavanceerde instellingen](../media/content-understanding/select-service-start-date.png) 

### <a name="add-a-negative-example"></a><span data-ttu-id="e2c4a-130">Een negatief voorbeeld toevoegen</span><span class="sxs-lookup"><span data-stu-id="e2c4a-130">Add a negative example</span></span>

<span data-ttu-id="e2c4a-131">Net zoals bij het toevoegen van een negatief voorbeeldbestand bij het maken van een classificatie, moet u een negatieve steekproef toevoegen voor de extractor.</span><span class="sxs-lookup"><span data-stu-id="e2c4a-131">Similar to how you add a negative sample file when creating a classifier, you need to add a negative sample for the extractor.</span></span> <span data-ttu-id="e2c4a-132">Dit moet een bestand zijn dat geen datumwaarde ' service start ' bevat.</span><span class="sxs-lookup"><span data-stu-id="e2c4a-132">It should be a file that does not contain a "Service Start" date value.</span></span>

1. <span data-ttu-id="e2c4a-133">Selecteer in de lijst met **gelabelde voorbeelden** een negatief voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="e2c4a-133">From the **Labeled examples** list, select a negative example.</span></span>
2. <span data-ttu-id="e2c4a-134">Selecteer in de viewer boven aan het artikel de optie **geen label aanwezig**.</span><span class="sxs-lookup"><span data-stu-id="e2c4a-134">In the viewer on the top of the article, select **No label present**.</span></span>
3. <span data-ttu-id="e2c4a-135">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="e2c4a-135">Click **Save**.</span></span>
 
<span data-ttu-id="e2c4a-136">Wanneer u vijf bestanden hebt gelabeld, wordt een melding weergegeven met de mededeling dat u wilt overstappen op de training.</span><span class="sxs-lookup"><span data-stu-id="e2c4a-136">Once you labeled five files, a notification banner displays informing you to move to training.</span></span> <span data-ttu-id="e2c4a-137">U kunt kiezen voor meer documenten of verder naar training.</span><span class="sxs-lookup"><span data-stu-id="e2c4a-137">You can choose to more documents or advance to training.</span></span> 

## <a name="add-an-explanation"></a><span data-ttu-id="e2c4a-138">Een uitleg toevoegen</span><span class="sxs-lookup"><span data-stu-id="e2c4a-138">Add an explanation</span></span>

<span data-ttu-id="e2c4a-139">Voorbeeld: u maakt een uitleg met een beschrijving van de entiteits indeling zelf en variaties in de voorbeelddocumenten.</span><span class="sxs-lookup"><span data-stu-id="e2c4a-139">For the example, you create an explanation that provides a hint about the entity format itself and variations it may have in the sample documents.</span></span> <span data-ttu-id="e2c4a-140">U kunt bijvoorbeeld een datumwaarde in verschillende notaties, bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="e2c4a-140">For example, a date value can be in a number of different formats, such as:</span></span>
- <span data-ttu-id="e2c4a-141">10/14/2019</span><span class="sxs-lookup"><span data-stu-id="e2c4a-141">10/14/2019</span></span>
- <span data-ttu-id="e2c4a-142">14 oktober 2019</span><span class="sxs-lookup"><span data-stu-id="e2c4a-142">October 14, 2019</span></span>
- <span data-ttu-id="e2c4a-143">Maandag 14 oktober 2019</span><span class="sxs-lookup"><span data-stu-id="e2c4a-143">Monday, October 14, 2019</span></span>
 

<span data-ttu-id="e2c4a-144">Om de *begindatum* van de service te identificeren, maakt u een patroon toelichting.</span><span class="sxs-lookup"><span data-stu-id="e2c4a-144">To help identify the *Service Start Date* you create a pattern explanation.</span></span>

1. <span data-ttu-id="e2c4a-145">Selecteer in de sectie uitleg de optie **Nieuw** en typ een naam (bijvoorbeeld *datum*).</span><span class="sxs-lookup"><span data-stu-id="e2c4a-145">In the Explanation section, select **New** and type a name (for example, *Date*).</span></span>
2. <span data-ttu-id="e2c4a-146">Selecteer bij type de optie **patroon lijst**.</span><span class="sxs-lookup"><span data-stu-id="e2c4a-146">For Type, select **Pattern list**.</span></span>
3. <span data-ttu-id="e2c4a-147">Voer bij waarde de datum variatie in zoals ze worden weergegeven in de voorbeeldbestanden.</span><span class="sxs-lookup"><span data-stu-id="e2c4a-147">For Value, provide the date variation as they appear in the sample files.</span></span> <span data-ttu-id="e2c4a-148">Als u bijvoorbeeld datumnotaties hebt die worden weergegeven als 0/00/0000, typt u variaties die in uw documenten worden weergegeven, zoals:</span><span class="sxs-lookup"><span data-stu-id="e2c4a-148">For example, if you have date formats that appear as 0/00/0000, you enter any variations that appear in your documents, such as:</span></span>
    - <span data-ttu-id="e2c4a-149">0/0/0000</span><span class="sxs-lookup"><span data-stu-id="e2c4a-149">0/0/0000</span></span>
    - <span data-ttu-id="e2c4a-150">0/00/0000</span><span class="sxs-lookup"><span data-stu-id="e2c4a-150">0/00/0000</span></span>
    - <span data-ttu-id="e2c4a-151">00/0/0000</span><span class="sxs-lookup"><span data-stu-id="e2c4a-151">00/0/0000</span></span>
    - <span data-ttu-id="e2c4a-152">00/00/0000</span><span class="sxs-lookup"><span data-stu-id="e2c4a-152">00/00/0000</span></span>
4. <span data-ttu-id="e2c4a-153">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="e2c4a-153">Select **Save**.</span></span>

### <a name="use-the-explanation-library"></a><span data-ttu-id="e2c4a-154">De uitleg bibliotheek gebruiken</span><span class="sxs-lookup"><span data-stu-id="e2c4a-154">Use the Explanation library</span></span>

<span data-ttu-id="e2c4a-155">Voor het maken van uitleg voor items, zoals datums, is het eenvoudiger om de uitleg bibliotheek te gebruiken dan voorhand matige invoer van alle variaties.</span><span class="sxs-lookup"><span data-stu-id="e2c4a-155">For creating explanations for items such as dates, it is easier to use the explanation library than to manually enter all variations.</span></span> <span data-ttu-id="e2c4a-156">De uitleg bibliotheek is een set vooraf gedefinieerde tekst en patroon toelichting.</span><span class="sxs-lookup"><span data-stu-id="e2c4a-156">The explanation library is a set of pre-built phrase and pattern explanations.</span></span> <span data-ttu-id="e2c4a-157">De bibliotheek biedt alle indelingen voor veelgebruikte woordgroepen of patroon lijsten, zoals datums, telefoonnummers, postcode, enzovoort.</span><span class="sxs-lookup"><span data-stu-id="e2c4a-157">The library provides all formats for common phrase or pattern lists, such as dates, phone numbers, zip code, etc.</span></span> 

<span data-ttu-id="e2c4a-158">Voor het voorbeeld van de *service begint* , is het efficiënter om de vooraf samengestelde uitleg voor *datum* in de uitleg bibliotheek te gebruiken:</span><span class="sxs-lookup"><span data-stu-id="e2c4a-158">For the *Service Start Date* sample, it is more efficient to use the pre-built explanation for *Date* in the explanation library:</span></span>

1. <span data-ttu-id="e2c4a-159">Selecteer in de **sectie uitleg**de optie **Nieuw**en selecteer vervolgens **uit uitleg bibliotheek**.</span><span class="sxs-lookup"><span data-stu-id="e2c4a-159">In the **Explanation section**, select **New**, and then select **From explanation library**.</span></span>
2. <span data-ttu-id="e2c4a-160">Selecteer **datum**in de uitleg bibliotheek.</span><span class="sxs-lookup"><span data-stu-id="e2c4a-160">From the explanation library, select **Date**.</span></span> <span data-ttu-id="e2c4a-161">U kunt alle variaties van een ondersteunde datum weergeven.</span><span class="sxs-lookup"><span data-stu-id="e2c4a-161">You can view all variations of date that are recognized.</span></span>
3. <span data-ttu-id="e2c4a-162">Kies **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="e2c4a-162">Select **Add**.</span></span></br>

    ![Uitleg bibliotheek](../media/content-understanding/explanation-library.png) 

4. <span data-ttu-id="e2c4a-164">Op de pagina **een uitleg maken** worden in de *datum* informatie uit de uitleg bibliotheek automatisch de velden ingevuld.</span><span class="sxs-lookup"><span data-stu-id="e2c4a-164">On the **Create an explanation** page, the *Date* information from the explanation library auto fills the fields.</span></span> <span data-ttu-id="e2c4a-165">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="e2c4a-165">Select **Save**.</span></span></br>

    ![Einddatum](../media/content-understanding/date-explanation-library.png) 

## <a name="train-the-model"></a><span data-ttu-id="e2c4a-167">Het model trainen</span><span class="sxs-lookup"><span data-stu-id="e2c4a-167">Train the model</span></span> 

<span data-ttu-id="e2c4a-168">Uw uitleg opslaan start de training.</span><span class="sxs-lookup"><span data-stu-id="e2c4a-168">Saving your explanation start the training.</span></span> <span data-ttu-id="e2c4a-169">Als uw model voldoende informatie bevat voor het extraheren van de gegevens uit de voorbeeldbestanden met labels, wordt elk bestand weergegeven met de **naam van het**bestand.</span><span class="sxs-lookup"><span data-stu-id="e2c4a-169">If your model has enough information to extract the data from your labeled example files, you will see each file labeled with **Match**.</span></span>  

![Doet](../media/content-understanding/match2.png) 

<span data-ttu-id="e2c4a-171">Als de uitleg niet voldoende informatie bevat om de gegevens te vinden die u wilt extraheren, wordt elk bestand aangeduid met een **overeenkomende**naam.</span><span class="sxs-lookup"><span data-stu-id="e2c4a-171">If the explanation does not have enough information to find the data you want to extract, each file will be labeled with **Mismatch**.</span></span> <span data-ttu-id="e2c4a-172">U kunt op de niet- **gerelateerde** bestanden klikken om meer informatie weer te geven over de reden waarom het niet klopt.</span><span class="sxs-lookup"><span data-stu-id="e2c4a-172">You can click on the **Mismatched** files to see more information about why there was a mismatch.</span></span>


## <a name="add-another-explanation"></a><span data-ttu-id="e2c4a-173">Nog een uitleg toevoegen</span><span class="sxs-lookup"><span data-stu-id="e2c4a-173">Add another explanation</span></span>

<span data-ttu-id="e2c4a-174">Vaak is de door u verstrekte uitleg niet voldoende informatie verstrekt om de begindatum waarde van de service uit te pakken, zodat deze overeenkomt met de gelabelde bestanden.</span><span class="sxs-lookup"><span data-stu-id="e2c4a-174">Often the mismatch is an indication that the explanation we provided did not provide enough information to extract the service start date value to match our labeled files.</span></span> <span data-ttu-id="e2c4a-175">Mogelijk moet u deze bewerken of een andere uitleg toevoegen.</span><span class="sxs-lookup"><span data-stu-id="e2c4a-175">You may need to edit it, or add another explanation.</span></span>

<span data-ttu-id="e2c4a-176">In het voorbeeld ziet u dat de *begindatum van* de tekenreeks vóór de daadwerkelijke waarde voorafgaat.</span><span class="sxs-lookup"><span data-stu-id="e2c4a-176">For the sample, notice that the text string *Start Service date of* always precedes the actual value.</span></span> <span data-ttu-id="e2c4a-177">Om de begindatum van de service te identificeren, moet u een uitdrukking maken die wordt uitgelegd.</span><span class="sxs-lookup"><span data-stu-id="e2c4a-177">To help identify the Service Start Date, you need ot create a phrase explanation.</span></span>

1. <span data-ttu-id="e2c4a-178">Selecteer in de sectie uitleg de optie **Nieuw**en typ een naam (bijvoorbeeld de prefix- *tekenreeks*).</span><span class="sxs-lookup"><span data-stu-id="e2c4a-178">In the Explanation section, select **New**, and then type a name (for example, *Prefix String*).</span></span>
2. <span data-ttu-id="e2c4a-179">Selecteer in het vak Type de optie **phrase**.</span><span class="sxs-lookup"><span data-stu-id="e2c4a-179">For the Type, select **Phrase list**.</span></span>
3. <span data-ttu-id="e2c4a-180">Gebruik de *begindatum van de service* als de waarde.</span><span class="sxs-lookup"><span data-stu-id="e2c4a-180">Use *Service Start Date of* as the value.</span></span>
4. <span data-ttu-id="e2c4a-181">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="e2c4a-181">Select **Save**.</span></span>

    ![Prefix-reeks](../media/content-understanding/prefix-string.png) 

## <a name="train-the-model-again"></a><span data-ttu-id="e2c4a-183">Het model opnieuw trainen</span><span class="sxs-lookup"><span data-stu-id="e2c4a-183">Train the model again</span></span>

<span data-ttu-id="e2c4a-184">Wanneer u de uitleg opslaat, wordt de training opnieuw gestart, op deze manier de uitleg van beide uitleg in het voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="e2c4a-184">Saving the explanation starts the training again, this time using both explanations in the sample.</span></span> <span data-ttu-id="e2c4a-185">Als uw model voldoende informatie bevat voor het extraheren van de gegevens uit de voorbeeldbestanden met labels, wordt elk bestand weergegeven met de naam van de **treffer**.</span><span class="sxs-lookup"><span data-stu-id="e2c4a-185">If your model has enough information to extract the data from the labeled sample files, you see each file labeled with **Match**.</span></span> 

<span data-ttu-id="e2c4a-186">Als u weer een **niet-overeenkomend** bestand met gelabelde bestanden ontvangt, moet u waarschijnlijk een andere uitleg maken om het documenttype te identificeren of om wijzigingen aan te brengen in het voorbeeldmodel.</span><span class="sxs-lookup"><span data-stu-id="e2c4a-186">If you again receive a **Mismatch** on your labeled files, you likely need to create another explanation to provide the model more information to identify the document type, or consider making changes to your sample model.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="e2c4a-187">Uw model testen</span><span class="sxs-lookup"><span data-stu-id="e2c4a-187">Test your model</span></span>

<span data-ttu-id="e2c4a-188">Als u een overeenkomst ontvangt met de gelabelde voorbeeldbestanden, kunt u uw model nu testen in de resterende voorbeeldbestanden met de naam.</span><span class="sxs-lookup"><span data-stu-id="e2c4a-188">If you receive a match on your labeled sample files, you can now test your model on the remaining unlabeled sample files.</span></span>

1. <span data-ttu-id="e2c4a-189">Klik op de startpagina van het model op het tabblad **testen** .  Hiermee voert u het model uit op uw niet-gelabelde voorbeeldbestanden.</span><span class="sxs-lookup"><span data-stu-id="e2c4a-189">From the model home page, click the **Test** tab.  This runs the model on your unlabeled sample files.</span></span>
2. <span data-ttu-id="e2c4a-190">In de lijst **bestanden testen** worden de voorbeeldbestanden weergegeven om aan te geven of de gegevens die u nodig hebt, kunnen worden uitgepakt in het model.</span><span class="sxs-lookup"><span data-stu-id="e2c4a-190">In the **Test files** list, your example files display to show if the model is able to extract the information you need.</span></span> <span data-ttu-id="e2c4a-191">Met deze informatie kunt u de effectiviteit van uw classificatie voor het identificeren van documenten bepalen.</span><span class="sxs-lookup"><span data-stu-id="e2c4a-191">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![Uw bestanden testen](../media/content-understanding/test-filies-extractor.png) 
