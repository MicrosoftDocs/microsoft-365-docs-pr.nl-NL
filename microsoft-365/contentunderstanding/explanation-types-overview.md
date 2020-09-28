---
title: Uitleg typen
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 10/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Meer informatie over uitleg typen in Microsoft SharePoint Syntex
ms.openlocfilehash: f4f5dbc24bef57b1801f7df1b7e2fc7ef9b08116
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295850"
---
# <a name="introduction-to-explanation-types"></a><span data-ttu-id="3a921-103">Inleiding tot uitleg typen</span><span class="sxs-lookup"><span data-stu-id="3a921-103">Introduction to explanation types</span></span>

<span data-ttu-id="3a921-104">Gebruik uitleg voor hulp bij het definiëren van de informatie die u wilt labelen en extraheren in uw document met de informatie over modellen voor Microsoft SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="3a921-104">Use explanations to help to define the information that you want to label, and extract in your document the understanding models for Microsoft SharePoint Syntex.</span></span> <span data-ttu-id="3a921-105">Wanneer u een uitleg maakt, moet u ervoor zorgen dat u een uitleg type selecteert.</span><span class="sxs-lookup"><span data-stu-id="3a921-105">When you create an explanation, be sure to select an explanation type.</span></span> 

<span data-ttu-id="3a921-106">Dit artikel helpt u inzicht te krijgen in de verschillende typen uitleg en hoe deze worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="3a921-106">This article helps you understand the different explanation types and how they are used.</span></span>

   ![Uitleg typen](../media/content-understanding/explanation-types.png) 
   
<span data-ttu-id="3a921-108">Deze uitleg typen zijn beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="3a921-108">These explanation types are available:</span></span>

- <span data-ttu-id="3a921-109">**Woordgroepenlijst**: een lijst met woorden, woordgroepen, getallen of andere tekens die u kunt gebruiken in het document of de gegevens die u wilt ophalen.</span><span class="sxs-lookup"><span data-stu-id="3a921-109">**Phrase list**: List of words, phrases, numbers, or other characters you can use in the document or information that you are extracting.</span></span> <span data-ttu-id="3a921-110">De tekstreeks die **verwijst** naar de tekstreeks, is bijvoorbeeld in alle medische verwijzingen die u identificeert.</span><span class="sxs-lookup"><span data-stu-id="3a921-110">For example, the text string **Referring Doctor** is in all Medical Referral documents you are identifying.</span></span></br>

- <span data-ttu-id="3a921-111">**Patroon lijst**: een lijst met getallen, letters of andere tekens die u kunt gebruiken om de informatie die u extraheert te identificeren.</span><span class="sxs-lookup"><span data-stu-id="3a921-111">**Pattern list**: List patterns of numbers, letters, or other characters that you can use to identify the information that you are extracting.</span></span> <span data-ttu-id="3a921-112">U kunt bijvoorbeeld het **telefoonnummer** van de betreffende dokter extraheren uit elk document dat u identificeert voor de medische verwijzing.</span><span class="sxs-lookup"><span data-stu-id="3a921-112">For example, you can extract the **Phone number** of the referring doctor from all Medical Referral document that you are identifying.</span></span></br>

- <span data-ttu-id="3a921-113">**Proximity**: hierin wordt beschreven hoe u de uitleg dicht bij elkaar hebt.</span><span class="sxs-lookup"><span data-stu-id="3a921-113">**Proximity**: Describes how close explanations are to each other.</span></span> <span data-ttu-id="3a921-114">Zo wordt een patroon lijst voor een *straatnummer* direct weergegeven vóór de naam van de *straatnaam* , zonder tokens ertussen (u kunt verderop in dit artikel meer informatie over tokens vinden).</span><span class="sxs-lookup"><span data-stu-id="3a921-114">For example, a *street number* pattern list goes right before the *street name* phrase list, with no tokens in between (you'll learn about tokens later in this article).</span></span> 
 
## <a name="phrase-list"></a><span data-ttu-id="3a921-115">Lijst met zinnen</span><span class="sxs-lookup"><span data-stu-id="3a921-115">Phrase list</span></span>

<span data-ttu-id="3a921-116">Een beschrijving van de lijst met zinnen wordt meestal gebruikt voor het identificeren en classificeren van een document via uw model.</span><span class="sxs-lookup"><span data-stu-id="3a921-116">A phrase list explanation type is typically used to identify and classify a document through your model.</span></span> <span data-ttu-id="3a921-117">Zoals beschreven in het voorbeeld van het *verwijzen van dokter* , is dit een reeks woorden, zinnen, getallen of tekens die consistent zijn in de documenten die u identificeert.</span><span class="sxs-lookup"><span data-stu-id="3a921-117">As described in the *Referring Doctor* label example, it is a string of words, phrases, numbers, or characters that is consistently in the documents that you are identifying.</span></span>

<span data-ttu-id="3a921-118">Hoewel u geen behoefte hebt, kunt u een betere succesvolle beschrijving krijgen als de woordgroep die u vastlegt, op een consistente locatie in het document staat.</span><span class="sxs-lookup"><span data-stu-id="3a921-118">While not a requirement, you can acheive better success with your explanation if the phrase you are capturing is located in a consistent location in your document.</span></span> <span data-ttu-id="3a921-119">Het label van de *verwijzings dokter* kan bijvoorbeeld consistent zijn in de eerste alinea van het document.</span><span class="sxs-lookup"><span data-stu-id="3a921-119">For example, the *Referring Doctor* label may be consistently located in the first paragraph of the document.</span></span>

<span data-ttu-id="3a921-120">Als hoofdlettergevoeligheid een vereiste is voor het identificeren van uw etiket, kunt u dit in uw uitleg opgeven door het selectievakje **alleen exact hoofdlettergebruik** in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="3a921-120">If case sensitivity is a requirement in identifying your label, using the phrase list type allows you to specify it in your explanation by selecting the **Only exact capitalization** checkbox.</span></span>

   ![Hoofdlettergevoeligheid](../media/content-understanding/case-sensitivity.png) 

## <a name="pattern-lists"></a><span data-ttu-id="3a921-122">Patroon lijsten</span><span class="sxs-lookup"><span data-stu-id="3a921-122">Pattern lists</span></span>

<span data-ttu-id="3a921-123">Een patroon lijsttype is vooral handig als u een uitleg maakt waarmee informatie wordt geïdentificeerd en opgehaald uit een document.</span><span class="sxs-lookup"><span data-stu-id="3a921-123">A pattern list type is especially useful when you create an explanation that identifies and extracts information from a document.</span></span> <span data-ttu-id="3a921-124">Dit wordt meestal weergegeven in verschillende notaties, zoals datums, telefoonnummers of creditcardnummers.</span><span class="sxs-lookup"><span data-stu-id="3a921-124">It is typically presented in different formats, such as dates, phone numbers, or credit card numbers.</span></span> <span data-ttu-id="3a921-125">Zo kan een datum worden weergegeven in verschillende notaties (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, 1 januari 2020, enzovoort).</span><span class="sxs-lookup"><span data-stu-id="3a921-125">For example, a date can be displayed in a number of different formats (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, Jan 1,2020, etc.).</span></span> <span data-ttu-id="3a921-126">Door een patroon lijst te definiëren, wordt uw uitleg efficiënter gemaakt door eventuele variaties te vastleggen in de gegevens die u wilt identificeren en uitpakken.</span><span class="sxs-lookup"><span data-stu-id="3a921-126">Defining a pattern list makes your explanation more efficient by capturing any possible variations in the data that you are trying to identify and extract.</span></span> 

<span data-ttu-id="3a921-127">Voor het voorbeeld van het **telefoonnummer** pakt u het telefoonnummer voor elke verzorgde dokter uit met alle medische Referral documenten die door het model worden geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="3a921-127">For the **Phone number** sample, extract the phone number for each referring doctor from all Medical Referral documents that the model identifies.</span></span> <span data-ttu-id="3a921-128">Wanneer u de uitleg maakt, selecteert u het lijsttype patroon om de verschillende opmaken toe te staan die u mogelijk verwacht te retourneren.</span><span class="sxs-lookup"><span data-stu-id="3a921-128">When you create the explanation, select the Pattern list type to allow the different formats that you may expect to be returned.</span></span>

   ![Lijst met opvultekens voor telefoonnummers](../media/content-understanding/pattern-list.png)

<span data-ttu-id="3a921-130">Voor dit voorbeeld selecteert u het selectievakje **willekeurig cijfer uit 0-9** .</span><span class="sxs-lookup"><span data-stu-id="3a921-130">For this sample, select the **Any digit from 0-9** checkbox.</span></span> <span data-ttu-id="3a921-131">Als u deze optie selecteert, wordt de waarde ' 0 ' in de lijst patroon herkend als een cijfer van 0 tot en met 9.</span><span class="sxs-lookup"><span data-stu-id="3a921-131">Selecting this recognizes each "0" value used in your pattern list to be any digit from 0 through 9.</span></span>

   ![Willekeurig cijfer uit 0-9](../media/content-understanding/digit-identity.png)

<span data-ttu-id="3a921-133">Als u een patroon lijst maakt met teksttekens, selecteert u ook de **letter van a-z** .</span><span class="sxs-lookup"><span data-stu-id="3a921-133">Similarly, if you create a pattern list that includes text characters, select the **Any letter from a-z** checkbox.</span></span> <span data-ttu-id="3a921-134">Als u deze optie selecteert, wordt elk willekeurig teken dat in de lijst patroon wordt gebruikt, herkend als een willekeurig teken van ' a ' tot ' z '.</span><span class="sxs-lookup"><span data-stu-id="3a921-134">Selecting this recognizes each "a" character used in the pattern list to be any character from "a" to "z".</span></span>

<span data-ttu-id="3a921-135">Als u bijvoorbeeld een lijst met **datum** patronen maakt en u er zeker van wilt zijn dat de datumnotatie *1 januari 2020* wordt herkend, moet u het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="3a921-135">For example, if you create a **Date** pattern list and you want to make sure that a date format such as *Jan 1, 2020* is recognized, you need to:</span></span>
- <span data-ttu-id="3a921-136">Voeg *AAA 0, 0000* en *AAA 00, 0000* toe aan de lijst patroon.</span><span class="sxs-lookup"><span data-stu-id="3a921-136">Add *aaa 0, 0000* and *aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="3a921-137">Zorg ervoor dat **de letter van a-z** ook is geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="3a921-137">Make sure that **Any letter from a-z** is also selected.</span></span>

   ![Een willekeurige letter van a-z](../media/content-understanding/any-letter.png)

<span data-ttu-id="3a921-139">Daarnaast hebt u de mogelijkheid om het selectievakje **alleen exact hoofdlettergebruik** in te schakelen in de lijst patroon.</span><span class="sxs-lookup"><span data-stu-id="3a921-139">Additionally, if you have capitalization requirements in your pattern list, you have the option to select the **Only exact capitalization** checkbox.</span></span> <span data-ttu-id="3a921-140">Voor het voorbeeld van de datum als u de eerste letter van de maand moet worden gekapitaliseerd, moet u het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="3a921-140">For the Date example, if you require the first letter of the month to be capitalized, you need to:</span></span>

- <span data-ttu-id="3a921-141">Voeg *AAA 0, 0000* en *AAA 00, 0000* toe aan de lijst patroon.</span><span class="sxs-lookup"><span data-stu-id="3a921-141">Add *Aaa 0, 0000* and *Aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="3a921-142">Zorg ervoor dat u ook **exact de juiste hoofdletters** selecteert.</span><span class="sxs-lookup"><span data-stu-id="3a921-142">Make sure that **Only exact capitalization** is also selected.</span></span>

   ![Alleen exact hoofdlettergebruik](../media/content-understanding/exact-caps.png)

> [!NOTE]
> <span data-ttu-id="3a921-144">In plaats van een uitleg van de patroon lijst handmatig te maken, gebruikt u de [uitleg bibliotheek]() om vooraf gemaakte patroon lijstsjablonen te gebruiken voor veelgebruikte patroon lijst, zoals *datum*, *telefoonnummer*, *creditcardnummer*, enzovoort.</span><span class="sxs-lookup"><span data-stu-id="3a921-144">Instead of manually creating pattern list explanation, use the [explanation library]() to use pre-made pattern list templates for common pattern list, such as *date*, *phone number*, *credit card number*, etc..</span></span> 

## <a name="proximity"></a><span data-ttu-id="3a921-145">Buurt</span><span class="sxs-lookup"><span data-stu-id="3a921-145">Proximity</span></span> 

<span data-ttu-id="3a921-146">Het type uitleg bij de buurt helpt uw modelgegevens te identificeren door te definiëren hoe u een ander stuk van de gegevens wilt opslaan.</span><span class="sxs-lookup"><span data-stu-id="3a921-146">The proximity explanation type helps your model identify data through defining how close another piece of data is to it.</span></span> <span data-ttu-id="3a921-147">In uw model hebt u bijvoorbeeld twee uitleg gedefinieerd met een naam voor het *adres* en het *telefoonnummer*van de klant.</span><span class="sxs-lookup"><span data-stu-id="3a921-147">For example, in your model, you have defined two explanations that label both the customer *Street address number* and *Phone number*.</span></span> 

<span data-ttu-id="3a921-148">U ziet ook dat telefoonnummers van klanten altijd voor het adres van de klant worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="3a921-148">You also notice that customer phone numbers always appear before the street address number.</span></span> 

<span data-ttu-id="3a921-149">Alex Wilburn</span><span class="sxs-lookup"><span data-stu-id="3a921-149">Alex Wilburn</span></span><br>
<span data-ttu-id="3a921-150">555-555-5555</span><span class="sxs-lookup"><span data-stu-id="3a921-150">555-555-5555</span></span><br>
<span data-ttu-id="3a921-151">Eén Microsoft-manier</span><span class="sxs-lookup"><span data-stu-id="3a921-151">One Microsoft Way</span></span><br>
<span data-ttu-id="3a921-152">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="3a921-152">Redmond, WA 98034</span></span><br>

<span data-ttu-id="3a921-153">Gebruik de uitleg van de nabijheid van het nummer om aan te geven hoe ver u wilt dat het nummer van de telefoon wordt aangegeven in uw documenten.</span><span class="sxs-lookup"><span data-stu-id="3a921-153">Use the proximity explanation to define how far away the phone number explanation is to better identify the street address number in your documents.</span></span>

   ![Uitleg over proximity](../media/content-understanding/proximity.png)</br>

#### <a name="what-are-tokens"></a><span data-ttu-id="3a921-155">Wat zijn tokens?</span><span class="sxs-lookup"><span data-stu-id="3a921-155">What are tokens?</span></span>

<span data-ttu-id="3a921-156">Als u het type proximity uitleg wilt gebruiken, begrijpt u wat een token is, aangezien het aantal tokens de afstand tussen de Proximity-uitleg en de een andere uitleg.</span><span class="sxs-lookup"><span data-stu-id="3a921-156">In order to use the proximity explanation type, understand what a token is, as the number of tokens is how the proximity explanation measures distance from one explanation to another.</span></span>  

<span data-ttu-id="3a921-157">Een token is een doorlopend bereik (geen spaties of leestekens) van letters en cijfers.</span><span class="sxs-lookup"><span data-stu-id="3a921-157">A token is a continuous span (no spaces or punctuation) of letters and numbers.</span></span> <span data-ttu-id="3a921-158">Een spatie is geen token.</span><span class="sxs-lookup"><span data-stu-id="3a921-158">A space is NOT a token.</span></span> <span data-ttu-id="3a921-159">Elk leesteken is een token.</span><span class="sxs-lookup"><span data-stu-id="3a921-159">Each punctuation character is a token.</span></span> <span data-ttu-id="3a921-160">In de volgende tabel ziet u enkele voorbeelden van het bepalen van het aantal tokens in een woordgroep.</span><span class="sxs-lookup"><span data-stu-id="3a921-160">The following table shows some examples of how to determine the number of tokens in a phrase.</span></span>

|<span data-ttu-id="3a921-161">Zinnen</span><span class="sxs-lookup"><span data-stu-id="3a921-161">Phrase</span></span>|<span data-ttu-id="3a921-162">Aantal tokens</span><span class="sxs-lookup"><span data-stu-id="3a921-162">Number of tokens</span></span>|<span data-ttu-id="3a921-163">Uitleg</span><span class="sxs-lookup"><span data-stu-id="3a921-163">Explanation</span></span>|
|--|--|--|
|`Dog`|<span data-ttu-id="3a921-164">1</span><span class="sxs-lookup"><span data-stu-id="3a921-164">1</span></span>|<span data-ttu-id="3a921-165">Eén woord zonder leestekens of spaties.</span><span class="sxs-lookup"><span data-stu-id="3a921-165">A single word with no punctuation or spaces.</span></span>|
|`RMT33W`|<span data-ttu-id="3a921-166">1</span><span class="sxs-lookup"><span data-stu-id="3a921-166">1</span></span>|<span data-ttu-id="3a921-167">Een record-locator-nummer.</span><span class="sxs-lookup"><span data-stu-id="3a921-167">A record locator number.</span></span> <span data-ttu-id="3a921-168">Het is mogelijk dat er cijfers en letters zijn, maar geen leestekens.</span><span class="sxs-lookup"><span data-stu-id="3a921-168">It may have numbers and letters, but does not have any punctuation.</span></span>|
|`425-555-5555`|<span data-ttu-id="3a921-169">vijf</span><span class="sxs-lookup"><span data-stu-id="3a921-169">5</span></span>|<span data-ttu-id="3a921-170">Een telefoonnummer.</span><span class="sxs-lookup"><span data-stu-id="3a921-170">A phone number.</span></span> <span data-ttu-id="3a921-171">Elk interpunctie is één token, dus  `425-555-5555` moet u 5 tokens hebben:</span><span class="sxs-lookup"><span data-stu-id="3a921-171">Each punctuation mark is a single token so  `425-555-5555` would be 5 tokens:</span></span><br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|<span data-ttu-id="3a921-172">7,5</span><span class="sxs-lookup"><span data-stu-id="3a921-172">7</span></span>|`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a><span data-ttu-id="3a921-173">Het uitleg type proximity configureren</span><span class="sxs-lookup"><span data-stu-id="3a921-173">Configure the proximity explanation type</span></span>

<span data-ttu-id="3a921-174">Voor het voorbeeld moet u de nabijheids instelling configureren, zodat we het bereik van het aantal tokens opgeven dat door het *telefoon* *nummer wordt* uitgelegd.</span><span class="sxs-lookup"><span data-stu-id="3a921-174">For the sample, configure the proximity setting so that we can define the range of the number of tokens the *Phone number* explanation is from the *Street address number* explanation.</span></span>

<span data-ttu-id="3a921-175">U ziet dat het minimale bereik 0 is omdat er geen tokens zijn tussen het telefoonnummer en het adres.</span><span class="sxs-lookup"><span data-stu-id="3a921-175">You should see that the minimum range is "0" since there are no tokens between the phone number and street address number.</span></span>

<span data-ttu-id="3a921-176">Sommige telefoonnummers in de voorbeelddocumenten worden echter met *(mobiel)* toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="3a921-176">However, some phone numbers in the sample documents are appended with *(mobile)*.</span></span>

<span data-ttu-id="3a921-177">Nestor Wilke</span><span class="sxs-lookup"><span data-stu-id="3a921-177">Nestor Wilke</span></span><br>
<span data-ttu-id="3a921-178">111-111-1111 (mobiel)</span><span class="sxs-lookup"><span data-stu-id="3a921-178">111-111-1111 (mobile)</span></span><br>
<span data-ttu-id="3a921-179">Eén Microsoft-manier</span><span class="sxs-lookup"><span data-stu-id="3a921-179">One Microsoft Way</span></span><br>
<span data-ttu-id="3a921-180">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="3a921-180">Redmond, WA 98034</span></span><br>

<span data-ttu-id="3a921-181">Er zijn drie tokens in *(mobiele nummers)*:</span><span class="sxs-lookup"><span data-stu-id="3a921-181">There are three tokens in *(mobile)*:</span></span>

|<span data-ttu-id="3a921-182">Zinnen</span><span class="sxs-lookup"><span data-stu-id="3a921-182">Phrase</span></span>|<span data-ttu-id="3a921-183">Aantal tokens</span><span class="sxs-lookup"><span data-stu-id="3a921-183">Token count</span></span>|
|--|--|
|<span data-ttu-id="3a921-184">(</span><span class="sxs-lookup"><span data-stu-id="3a921-184">(</span></span>|<span data-ttu-id="3a921-185">1</span><span class="sxs-lookup"><span data-stu-id="3a921-185">1</span></span>|
|<span data-ttu-id="3a921-186">mobiele</span><span class="sxs-lookup"><span data-stu-id="3a921-186">mobile</span></span>|<span data-ttu-id="3a921-187">3</span><span class="sxs-lookup"><span data-stu-id="3a921-187">2</span></span>|
|<span data-ttu-id="3a921-188">)</span><span class="sxs-lookup"><span data-stu-id="3a921-188">)</span></span>|<span data-ttu-id="3a921-189">driefasig</span><span class="sxs-lookup"><span data-stu-id="3a921-189">3</span></span>|

<span data-ttu-id="3a921-190">Configureer de nabijheids instelling voor een bereik van 0 tot en met 3.</span><span class="sxs-lookup"><span data-stu-id="3a921-190">Configure the proximity setting to have a range of 0 through 3.</span></span>

   ![Voorbeeld van proximity](../media/content-understanding/proximity-example.png)</br>

## <a name="use-the-explanation-library"></a><span data-ttu-id="3a921-192">De uitleg bibliotheek gebruiken</span><span class="sxs-lookup"><span data-stu-id="3a921-192">Use the explanation library</span></span>

<span data-ttu-id="3a921-193">Hoewel u handmatig verschillende waarden voor de patroon lijst voor uw uitleg kunt toevoegen, kunt u het beste gebruikmaken van de vooraf gemaakte sjablonen die u aan u hebt verstrekt in de uitleg bibliotheek.</span><span class="sxs-lookup"><span data-stu-id="3a921-193">While you can manually add various pattern list values for your explanation, it's much easier to use the pre-created templates provided to you in the explanation library.</span></span>

<span data-ttu-id="3a921-194">In plaats van alle variaties voor *datum*handmatig toe te voegen, gebruikt u de sjabloon patroon lijst voor *datum*die al een aantal waarden voor patroon lijsten omvat:</span><span class="sxs-lookup"><span data-stu-id="3a921-194">For example, instead of manually adding all the variations for *Date*, use the pattern list template for *Date*, that already includes a number of pattern lists values:</span></span></br>

   ![Uitleg bibliotheek](../media/content-understanding/explanation-template.png)</br>
 
<span data-ttu-id="3a921-196">De uitleg bibliotheek bevat een aantal veelgestelde beschrijvingen van patroon lijsten, waaronder:</span><span class="sxs-lookup"><span data-stu-id="3a921-196">The explanation library includes a number of commonly used pattern list explanations, including:</span></span></br>

- <span data-ttu-id="3a921-197">Einddatum</span><span class="sxs-lookup"><span data-stu-id="3a921-197">Date</span></span></br>
- <span data-ttu-id="3a921-198">Datum (getal)</span><span class="sxs-lookup"><span data-stu-id="3a921-198">Date (numeric)</span></span></br>
- <span data-ttu-id="3a921-199">Fase</span><span class="sxs-lookup"><span data-stu-id="3a921-199">Time</span></span></br>
- <span data-ttu-id="3a921-200">Nummer</span><span class="sxs-lookup"><span data-stu-id="3a921-200">Number</span></span></br>
- <span data-ttu-id="3a921-201">Telefoonnummer</span><span class="sxs-lookup"><span data-stu-id="3a921-201">Phone number</span></span></br>
- <span data-ttu-id="3a921-202">Postcode</span><span class="sxs-lookup"><span data-stu-id="3a921-202">Zip code</span></span></br>
- <span data-ttu-id="3a921-203">Eerste woord van de zin</span><span class="sxs-lookup"><span data-stu-id="3a921-203">First word of sentence</span></span></br>
- <span data-ttu-id="3a921-204">Credit Card</span><span class="sxs-lookup"><span data-stu-id="3a921-204">Credit card</span></span></br>
- <span data-ttu-id="3a921-205">Sofi-nummer</span><span class="sxs-lookup"><span data-stu-id="3a921-205">Social security number</span></span></br>

<span data-ttu-id="3a921-206">Houd er rekening mee dat de uitleg bibliotheek ook sjablonen bevat voor uitleg over de lijst met zinnen, waaronder:</span><span class="sxs-lookup"><span data-stu-id="3a921-206">Note that the explanation library also includes templates for phrase list explanations as well, including:</span></span>
- <span data-ttu-id="3a921-207">Einde van de zin</span><span class="sxs-lookup"><span data-stu-id="3a921-207">End of sentence</span></span>
- <span data-ttu-id="3a921-208">Meerdere</span><span class="sxs-lookup"><span data-stu-id="3a921-208">Currency</span></span>

#### <a name="to-use-a-template-from-the-explanation-library"></a><span data-ttu-id="3a921-209">Een sjabloon uit de uitleg bibliotheek gebruiken</span><span class="sxs-lookup"><span data-stu-id="3a921-209">To use a template from the explanation library</span></span>

1. <span data-ttu-id="3a921-210">Selecteer in het gedeelte **uitleg** van de **Train** -pagina van uw model de optie **Nieuw**en selecteer vervolgens **een sjabloon op basis van een sjabloon**.</span><span class="sxs-lookup"><span data-stu-id="3a921-210">From the **Explanations** section of your model's **Train** page, select **New**, then select **From a template**.</span></span></br>

   ![Maken op basis van sjabloon](../media/content-understanding/from-template.png)</br>

2.  <span data-ttu-id="3a921-212">Selecteer op de pagina met **uitleg sjablonen** de uitleg die u wilt gebruiken en selecteer vervolgens **toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="3a921-212">On the **Explanation templates** page, select the explanation you want to use, and then select **Add**.</span></span></br>

       ![Een sjabloon selecteren](../media/content-understanding/phone-template.png)</br>

3. <span data-ttu-id="3a921-214">De gegevens voor de sjabloon die u hebt geselecteerd, worden weergegeven op de pagina **een uitleg maken** .</span><span class="sxs-lookup"><span data-stu-id="3a921-214">The information for the template you selected will display on the **Create an explanation** page.</span></span> <span data-ttu-id="3a921-215">Bewerk, indien nodig, de naam van de uitleg en voeg items toe aan of verwijder ze uit de lijst patroon.</span><span class="sxs-lookup"><span data-stu-id="3a921-215">If needed, edit the explanation name, and add or remove items from the pattern list.</span></span> </br> 

   ![Sjabloon bewerken](../media/content-understanding/phone-template-live.png)</br>

4. <span data-ttu-id="3a921-217">Selecteer **Opslaan**wanneer u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="3a921-217">When finished, select **Save**.</span></span>
