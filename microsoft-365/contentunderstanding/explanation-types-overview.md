---
title: Uitlegtypen
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: Meer informatie over uitlegtypen in Microsoft SharePoint Syntex
ms.openlocfilehash: f01529199bf4dea0a14c7dc30b39fcaa5078931b
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087641"
---
# <a name="introduction-to-explanation-types"></a><span data-ttu-id="a878c-103">Inleiding tot uitlegtypen</span><span class="sxs-lookup"><span data-stu-id="a878c-103">Introduction to explanation types</span></span>

<span data-ttu-id="a878c-104">Uitleg wordt gebruikt om de gegevens te definiëren die je wilt labelen en ophalen in je documentinformatie over modellen in Microsoft SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="a878c-104">Explanations are used to help to define the information you want to label and extract in your document understanding models in Microsoft SharePoint Syntex.</span></span> <span data-ttu-id="a878c-105">Bij het maken van een uitleg moet je een uitlegtype selecteren.</span><span class="sxs-lookup"><span data-stu-id="a878c-105">When creating an explanation, you need to select an explanation type.</span></span> <span data-ttu-id="a878c-106">In dit artikel vind je meer informatie over de verschillende uitlegtypen en hoe je deze kunt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="a878c-106">This article helps you understand the different explanation types and how they are used.</span></span> 

   ![Uitlegtypen](../media/content-understanding/explanation-types.png) 
   
<span data-ttu-id="a878c-108">Deze uitlegtypen zijn beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="a878c-108">These explanation types are available:</span></span>

- <span data-ttu-id="a878c-109">**Frasenlijst**: Lijst met woorden, woordgroepen, getallen of andere tekens die je kunt gebruiken in het document of de gegevens die je wilt ophalen.</span><span class="sxs-lookup"><span data-stu-id="a878c-109">**Phrase list**: List of words, phrases, numbers, or other characters you can use in the document or information that you are extracting.</span></span> <span data-ttu-id="a878c-110">De tekenreeks **Verwijzen naar Doctor** wordt bijvoorbeeld gebruikt in medische verwijsdocumenten die je identificeert.</span><span class="sxs-lookup"><span data-stu-id="a878c-110">For example, the text string **Referring Doctor** is in all Medical Referral documents you are identifying.</span></span></br>

- <span data-ttu-id="a878c-111">**Patroonlijst**: lijst patronen met getallen, letters of andere tekens die je kunt gebruiken om de gegevens te identificeren die je wilt ophalen.</span><span class="sxs-lookup"><span data-stu-id="a878c-111">**Pattern list**: List patterns of numbers, letters, or other characters that you can use to identify the information that you are extracting.</span></span> <span data-ttu-id="a878c-112">Je kunt bijvoorbeeld het **Telefoonnummer** van de verwijsarts extraheren uit medische verwijsdocumenten die je identificeert.</span><span class="sxs-lookup"><span data-stu-id="a878c-112">For example, you can extract the **Phone number** of the referring doctor from all Medical Referral document that you are identifying.</span></span></br>

- <span data-ttu-id="a878c-113">**Proximity**: in dit artikel wordt beschreven hoe dicht toelichtingen bij elkaar liggen.</span><span class="sxs-lookup"><span data-stu-id="a878c-113">**Proximity**: Describes how close explanations are to each other.</span></span> <span data-ttu-id="a878c-114">Een patroonlijst van *straatnummer* wordt bijvoorbeeld direct weergeven voor de woordenlijst met *straatnamen* zonder tokens ertussen (je vind meer informatie over tokens verderop in dit artikel).</span><span class="sxs-lookup"><span data-stu-id="a878c-114">For example, a *street number* pattern list goes right before the *street name* phrase list, with no tokens in between (you'll learn about tokens later in this article).</span></span> <span data-ttu-id="a878c-115">Voor het type proximity moet je ten minste twee uitleggen in je model hebben, of de optie wordt uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="a878c-115">Using the proximity type requires you to have at least two explanations in your model or the option will be disabled.</span></span> 
 
## <a name="phrase-list"></a><span data-ttu-id="a878c-116">Woordenlijst</span><span class="sxs-lookup"><span data-stu-id="a878c-116">Phrase list</span></span>

<span data-ttu-id="a878c-117">Het uitlegtype van een woordenlijst wordt meestal gebruikt om een document te identificeren en te classificeren via je model.</span><span class="sxs-lookup"><span data-stu-id="a878c-117">A phrase list explanation type is typically used to identify and classify a document through your model.</span></span> <span data-ttu-id="a878c-118">Zoals wordt beschreven in het labelvoorbeeld *Verwijzende arts*, is het een tekenreeks met woorden, woordgroepen, getallen of tekens die consequent voorkomen in de documenten die je wilt herkennen.</span><span class="sxs-lookup"><span data-stu-id="a878c-118">As described in the *Referring Doctor* label example, it is a string of words, phrases, numbers, or characters that is consistently in the documents that you are identifying.</span></span>

<span data-ttu-id="a878c-119">Hoewel het geen eis is, kunt je je uitleg beter laten opvallen als de woordgroep die je wilt vastleggen zich op een consistente locatie in het document bevindt.</span><span class="sxs-lookup"><span data-stu-id="a878c-119">While not a requirement, you can achieve better success with your explanation if the phrase you are capturing is located in a consistent location in your document.</span></span> <span data-ttu-id="a878c-120">Zo kan het label *Verwijzende arts* label zich in de eerste alinea van het document bevinden.</span><span class="sxs-lookup"><span data-stu-id="a878c-120">For example, the *Referring Doctor* label may be consistently located in the first paragraph of the document.</span></span>

<span data-ttu-id="a878c-121">Als hoofdlettergevoeligheid een vereiste is bij het identificeren van je label, kun je met het woordenlijsttype in uw uitleg opgeven door het selectievakje **Alleen exacte kapitalisatie** in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="a878c-121">If case sensitivity is a requirement in identifying your label, using the phrase list type allows you to specify it in your explanation by selecting the **Only exact capitalization** checkbox.</span></span>

   ![Onderscheid tussen hoofdletters en kleine letters](../media/content-understanding/case-sensitivity.png) 

## <a name="pattern-lists"></a><span data-ttu-id="a878c-123">Patroonlijsten</span><span class="sxs-lookup"><span data-stu-id="a878c-123">Pattern lists</span></span>

<span data-ttu-id="a878c-124">Een patroonlijst is met name handig wanneer je een uitleg maakt waarmee gegevens uit een document worden geïdentificeerd en opgehaald.</span><span class="sxs-lookup"><span data-stu-id="a878c-124">A pattern list type is especially useful when you create an explanation that identifies and extracts information from a document.</span></span> <span data-ttu-id="a878c-125">Deze worden meestal weergegeven in verschillende indelingen, zoals datums, telefoonnummers of creditcardnummers.</span><span class="sxs-lookup"><span data-stu-id="a878c-125">It is typically presented in different formats, such as dates, phone numbers, and credit card numbers.</span></span> <span data-ttu-id="a878c-126">Een datum kan bijvoorbeeld worden weergegeven in een aantal verschillende notaties (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, 1 januari 2020, enzovoort).</span><span class="sxs-lookup"><span data-stu-id="a878c-126">For example, a date can be displayed in a number of different formats (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, Jan 1,2020, etc.).</span></span> <span data-ttu-id="a878c-127">Door een patroonlijst te definiëren, kun je je efficiënter identificeren door eventuele variaties in de gegevens vast te leggen die je probeert vast te stellen en op te halen.</span><span class="sxs-lookup"><span data-stu-id="a878c-127">Defining a pattern list makes your explanation more efficient by capturing any possible variations in the data that you are trying to identify and extract.</span></span> 

<span data-ttu-id="a878c-128">Voor het voorbeeld **Telefoonnummer** moet je het telefoonnummer voor elke verwijzende arts ophalen uit alle Medische Verwijzingsdocumenten die door het model worden geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="a878c-128">For the **Phone number** example, you extract the phone number for each referring doctor from all Medical Referral documents that the model identifies.</span></span> <span data-ttu-id="a878c-129">Wanneer je de uitleg maakt, selecteer je het patroonlijsttype om de verschillende indelingen toe te staan die mogelijk naar verwachting worden geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="a878c-129">When you create the explanation, select the Pattern list type to allow the different formats that you may expect to be returned.</span></span>

   ![Patroonlijst telefoonnummers](../media/content-understanding/pattern-list.png)

<span data-ttu-id="a878c-131">Voor dit voorbeeld selecteert u het selectievakje **een cijfer van 0-9** als u elke ' 0 ' waarde die in de patroonlijst wordt gebruikt, wilt herkennen aan een cijfer van 0 tot en met 9.</span><span class="sxs-lookup"><span data-stu-id="a878c-131">For this example, select the **Any digit from 0-9** checkbox to recognize each "0" value used in your pattern list to be any digit from 0 through 9.</span></span>

   ![Een willekeurig cijfer van 0-9](../media/content-understanding/digit-identity.png)

<span data-ttu-id="a878c-133">Als u een patroonlijst maakt die teksttekens bevat, selecteert u het selectievakje **een letter van a-z** om elk teken dat wordt gebruikt in de patroonlijst te herkennen aan een teken van a tot en met z.</span><span class="sxs-lookup"><span data-stu-id="a878c-133">Similarly, if you create a pattern list that includes text characters, select the **Any letter from a-z** checkbox to recognize each "a" character used in the pattern list to be any character from "a" to "z".</span></span>

<span data-ttu-id="a878c-134">Als je bijvoorbeeld een patroonlijst **Datum** maakt en je ervoor wilt zorgen dat een datumnotatie wordt ondersteund zoals *2020 1 januari*, moet je het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="a878c-134">For example, if you create a **Date** pattern list and you want to make sure that a date format such as *Jan 1, 2020* is recognized, you need to:</span></span>
- <span data-ttu-id="a878c-135">Voeg *AAA 0, 0000* en *AAA 00, 0000* aan de patroonlijst toe.</span><span class="sxs-lookup"><span data-stu-id="a878c-135">Add *aaa 0, 0000* and *aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="a878c-136">Zorg ervoor dat **Een willekeurige letter van a-z** is geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="a878c-136">Make sure that **Any letter from a-z** is also selected.</span></span>

   ![Een letter van a-z](../media/content-understanding/any-letter.png)

<span data-ttu-id="a878c-138">Als je hoofdlettereisen in je patroonlijst hebt, kun je ook het selectievakje **Alleen exact hoofdlettergebruik** selecteren.</span><span class="sxs-lookup"><span data-stu-id="a878c-138">Additionally, if you have capitalization requirements in your pattern list, you have the option to select the **Only exact capitalization** checkbox.</span></span> <span data-ttu-id="a878c-139">Als de eerste letter van de maand moet worden gekapitaliseerd, moet je het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="a878c-139">For the Date example, if you require the first letter of the month to be capitalized, you need to:</span></span>

- <span data-ttu-id="a878c-140">Voeg *Aaa 0, 0000* en *AAA 00, 0000* aan de patroonlijst toe.</span><span class="sxs-lookup"><span data-stu-id="a878c-140">Add *Aaa 0, 0000* and *Aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="a878c-141">Zorg ervoor dat **Alleen exact hoofdlettergebruik** ook is geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="a878c-141">Make sure that **Only exact capitalization** is also selected.</span></span>

   ![Alleen exact hoofdlettergebruik](../media/content-understanding/exact-caps.png)

> [!NOTE]
> <span data-ttu-id="a878c-143">Gebruik in plaats van het handmatig maken van een uitleg voor patroonlijsten de [uitlegbibliotheek](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-explanation-templates) voor het gebruik van vooraf gemaakte patroonlijstsjablonen voor een algemene patroonlijst, zoals *datum*, *telefoonnummer*, *creditcardnummer*, enzovoort.</span><span class="sxs-lookup"><span data-stu-id="a878c-143">Instead of manually creating a pattern list explanation, use the [explanation library](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-explanation-templates) to use pattern list templates for a common pattern list, such as *date*, *phone number*, *credit card number*, etc.</span></span>

## <a name="proximity"></a><span data-ttu-id="a878c-144">Proximity</span><span class="sxs-lookup"><span data-stu-id="a878c-144">Proximity</span></span> 

<span data-ttu-id="a878c-145">Met het Proximity-uitlegtype kan je model identificeren met behulp van hoe dichtbij een ander stukje gegevens is.</span><span class="sxs-lookup"><span data-stu-id="a878c-145">The proximity explanation type helps your model identify data by defining how close another piece of data is to it.</span></span> <span data-ttu-id="a878c-146">Bijvoorbeeld, in je model heb je twee verklaringen gedefinieerd waaraan zowel het *huisnummer* als *telefoonnummer* zijn gelabeld.</span><span class="sxs-lookup"><span data-stu-id="a878c-146">For example, in your model say you have defined two explanations that label both the customer *Street address number* and *Phone number*.</span></span> 

<span data-ttu-id="a878c-147">Je ziet ook dat de telefoonnummers van klanten altijd voor het huisnummer worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="a878c-147">Notice that customer phone numbers always appear before the street address number.</span></span> 

<span data-ttu-id="a878c-148">Alex Wilburn</span><span class="sxs-lookup"><span data-stu-id="a878c-148">Alex Wilburn</span></span><br>
<span data-ttu-id="a878c-149">555-555-5555</span><span class="sxs-lookup"><span data-stu-id="a878c-149">555-555-5555</span></span><br>
<span data-ttu-id="a878c-150">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="a878c-150">One Microsoft Way</span></span><br>
<span data-ttu-id="a878c-151">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="a878c-151">Redmond, WA 98034</span></span><br>

<span data-ttu-id="a878c-152">Gebruik de proximity-uitleg om te bepalen hoe ver de uitleg van een telefoonnummer is zodat u het huisnummer in je documenten beter kunt identificeren.</span><span class="sxs-lookup"><span data-stu-id="a878c-152">Use the proximity explanation to define how far away the phone number explanation is to better identify the street address number in your documents.</span></span>

   ![Proximity-uitleg](../media/content-understanding/proximity.png)</br>

#### <a name="what-are-tokens"></a><span data-ttu-id="a878c-154">Wat zijn tokens?</span><span class="sxs-lookup"><span data-stu-id="a878c-154">What are tokens?</span></span>

<span data-ttu-id="a878c-155">Voor het gebruik van het Proximity-uitlegtype moet je weten wat een token is, omdat het aantal tokens is hoe de proximity-uitleg de afstand tussen een verklaring en een andere meet.</span><span class="sxs-lookup"><span data-stu-id="a878c-155">In order to use the proximity explanation type, you need to understand what a token is, as the number of tokens is how the proximity explanation measures distance from one explanation to another.</span></span> <span data-ttu-id="a878c-156">Een token is een doorlopende reeks (geen spaties of interpunctie) van letters en cijfers.</span><span class="sxs-lookup"><span data-stu-id="a878c-156">A token is a continuous span (not including spaces or punctuation) of letters and numbers.</span></span> 

<span data-ttu-id="a878c-157">In de volgende tabel zie je enkele voorbeelden van hoe je het aantal tokens in een woordgroep kunt vaststellen.</span><span class="sxs-lookup"><span data-stu-id="a878c-157">The following table shows examples for how to determine the number of tokens in a phrase.</span></span>

|<span data-ttu-id="a878c-158">Woordengroep</span><span class="sxs-lookup"><span data-stu-id="a878c-158">Phrase</span></span>|<span data-ttu-id="a878c-159">Aantal tokens</span><span class="sxs-lookup"><span data-stu-id="a878c-159">Number of tokens</span></span>|<span data-ttu-id="a878c-160">Uitleg</span><span class="sxs-lookup"><span data-stu-id="a878c-160">Explanation</span></span>|
|--|--|--|
|`Dog`|<span data-ttu-id="a878c-161">1</span><span class="sxs-lookup"><span data-stu-id="a878c-161">1</span></span>|<span data-ttu-id="a878c-162">Eén woord zonder leesteken of spatie.</span><span class="sxs-lookup"><span data-stu-id="a878c-162">A single word with no punctuation or spaces.</span></span>|
|`RMT33W`|<span data-ttu-id="a878c-163">1</span><span class="sxs-lookup"><span data-stu-id="a878c-163">1</span></span>|<span data-ttu-id="a878c-164">Een record locatornummer.</span><span class="sxs-lookup"><span data-stu-id="a878c-164">A record locator number.</span></span> <span data-ttu-id="a878c-165">Het mag cijfers en letters bevatten, maar geen leestekens.</span><span class="sxs-lookup"><span data-stu-id="a878c-165">It may include numbers and letters, but does not have punctuation.</span></span>|
|`425-555-5555`|<span data-ttu-id="a878c-166">5</span><span class="sxs-lookup"><span data-stu-id="a878c-166">5</span></span>|<span data-ttu-id="a878c-167">Een telefoonnummer.</span><span class="sxs-lookup"><span data-stu-id="a878c-167">A phone number.</span></span> <span data-ttu-id="a878c-168">Elk leesteken bestaat uit één token, zodat `425-555-5555` 5 tokens zou zijn:</span><span class="sxs-lookup"><span data-stu-id="a878c-168">Each punctuation mark is a single token, so `425-555-5555` is 5 tokens:</span></span><br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|<span data-ttu-id="a878c-169">7</span><span class="sxs-lookup"><span data-stu-id="a878c-169">7</span></span>|`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a><span data-ttu-id="a878c-170">Het proximity-uitlegtype configureren</span><span class="sxs-lookup"><span data-stu-id="a878c-170">Configure the proximity explanation type</span></span>

<span data-ttu-id="a878c-171">Voor het voorbeeld configureer je de proximity-instelling zodanig dat je het aantal tokens kunt definiëren in *Telefoonnummer*-uitleg afkomstig van de *Huisnummer*-uitleg.</span><span class="sxs-lookup"><span data-stu-id="a878c-171">For the example, configure the proximity setting to define the range of the number of tokens in the *Phone number* explanation from the *Street address number* explanation.</span></span> <span data-ttu-id="a878c-172">Je ziet dat het minimumbereik “0“ is omdat er geen tokens zijn tussen het telefoonnummer en het huisnummer.</span><span class="sxs-lookup"><span data-stu-id="a878c-172">Notice that the minimum range is "0", because there are no tokens between the phone number and street address number.</span></span>

<span data-ttu-id="a878c-173">Sommige telefoonnummers in de voorbeelddocumenten worden echter toegevoegd met *(mobiel)*.</span><span class="sxs-lookup"><span data-stu-id="a878c-173">But some phone numbers in the sample documents are appended with *(mobile)*.</span></span>

<span data-ttu-id="a878c-174">Wander Kuijken</span><span class="sxs-lookup"><span data-stu-id="a878c-174">Nestor Wilke</span></span><br>
<span data-ttu-id="a878c-175">111-111-1111 (mobiel)</span><span class="sxs-lookup"><span data-stu-id="a878c-175">111-111-1111 (mobile)</span></span><br>
<span data-ttu-id="a878c-176">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="a878c-176">One Microsoft Way</span></span><br>
<span data-ttu-id="a878c-177">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="a878c-177">Redmond, WA 98034</span></span><br>

<span data-ttu-id="a878c-178">Er zijn drie tokens in *(mobiel)*:</span><span class="sxs-lookup"><span data-stu-id="a878c-178">There are three tokens in *(mobile)*:</span></span>

|<span data-ttu-id="a878c-179">Woordengroep</span><span class="sxs-lookup"><span data-stu-id="a878c-179">Phrase</span></span>|<span data-ttu-id="a878c-180">Aantal tokens</span><span class="sxs-lookup"><span data-stu-id="a878c-180">Token count</span></span>|
|--|--|
|<span data-ttu-id="a878c-181">(</span><span class="sxs-lookup"><span data-stu-id="a878c-181">(</span></span>|<span data-ttu-id="a878c-182">1</span><span class="sxs-lookup"><span data-stu-id="a878c-182">1</span></span>|
|<span data-ttu-id="a878c-183">Mobiel</span><span class="sxs-lookup"><span data-stu-id="a878c-183">mobile</span></span>|<span data-ttu-id="a878c-184">2</span><span class="sxs-lookup"><span data-stu-id="a878c-184">2</span></span>|
|<span data-ttu-id="a878c-185">)</span><span class="sxs-lookup"><span data-stu-id="a878c-185">)</span></span>|<span data-ttu-id="a878c-186">3</span><span class="sxs-lookup"><span data-stu-id="a878c-186">3</span></span>|

<span data-ttu-id="a878c-187">Configureer de proximity-instelling voor een bereik van 0 tot en met 3.</span><span class="sxs-lookup"><span data-stu-id="a878c-187">Configure the proximity setting to have a range of 0 through 3.</span></span>

   ![Voorbeeld van proximity](../media/content-understanding/proximity-example.png)</br>

## <a name="use-explanation-templates"></a><span data-ttu-id="a878c-189">Uitlegsjablonen gebruiken</span><span class="sxs-lookup"><span data-stu-id="a878c-189">Use explanation templates</span></span>

<span data-ttu-id="a878c-190">Hoewel je handmatig verschillende waarden voor een patroonlijst kunt toevoegen voor je uitleg, is het veel eenvoudiger om de vooraf gemaakte sjablonen te gebruiken die in de uitlegbibliotheek worden aangeboden.</span><span class="sxs-lookup"><span data-stu-id="a878c-190">While you can manually add various pattern list values for your explanation, it can be easier to use the templates provided to you in the explanation library.</span></span>

<span data-ttu-id="a878c-191">Je kunt bijvoorbeeld in plaats van alle variaties voor *Datum* handmatig toe te voegen, de sjabloonlijst met patronen gebruiken voor *Datum*, die al een aantal waarden voor een patroonlijst bevat:</span><span class="sxs-lookup"><span data-stu-id="a878c-191">For example, instead of manually adding all the variations for *Date*, you can use the pattern list template for *Date* as it already includes a number of pattern lists values:</span></span></br>

   ![Uitlegbibliotheek](../media/content-understanding/explanation-template.png)</br>
 
<span data-ttu-id="a878c-193">De uitlegbibliotheek bevat een aantal veelgebruikte beschrijvingen van de patroonlijst, waaronder:</span><span class="sxs-lookup"><span data-stu-id="a878c-193">The explanation library includes commonly used pattern list explanations, including:</span></span></br>

- <span data-ttu-id="a878c-194">Datum</span><span class="sxs-lookup"><span data-stu-id="a878c-194">Date</span></span></br>
- <span data-ttu-id="a878c-195">Datum (getal)</span><span class="sxs-lookup"><span data-stu-id="a878c-195">Date (numeric)</span></span></br>
- <span data-ttu-id="a878c-196">Tijd</span><span class="sxs-lookup"><span data-stu-id="a878c-196">Time</span></span></br>
- <span data-ttu-id="a878c-197">Nummer</span><span class="sxs-lookup"><span data-stu-id="a878c-197">Number</span></span></br>
- <span data-ttu-id="a878c-198">Telefoonnummer</span><span class="sxs-lookup"><span data-stu-id="a878c-198">Phone number</span></span></br>
- <span data-ttu-id="a878c-199">Postcode</span><span class="sxs-lookup"><span data-stu-id="a878c-199">Zip code</span></span></br>
- <span data-ttu-id="a878c-200">Eerste woord of zin</span><span class="sxs-lookup"><span data-stu-id="a878c-200">First word of sentence</span></span></br>
- <span data-ttu-id="a878c-201">Creditcard</span><span class="sxs-lookup"><span data-stu-id="a878c-201">Credit card</span></span></br>
- <span data-ttu-id="a878c-202">Sofi-nummer</span><span class="sxs-lookup"><span data-stu-id="a878c-202">Social security number</span></span></br>

<span data-ttu-id="a878c-203">Let op: de uitlegbibliotheek bevat ook sjablonen voor verklaringen van een woordenlijst, waaronder:</span><span class="sxs-lookup"><span data-stu-id="a878c-203">Note that the explanation library also includes templates for phrase list explanations:</span></span>
- <span data-ttu-id="a878c-204">Afgelopen zin</span><span class="sxs-lookup"><span data-stu-id="a878c-204">End of sentence</span></span>
- <span data-ttu-id="a878c-205">Valuta</span><span class="sxs-lookup"><span data-stu-id="a878c-205">Currency</span></span>

#### <a name="to-use-a-template-from-the-explanation-library"></a><span data-ttu-id="a878c-206">Een sjabloon gebruiken uit de uitlegbibliotheek</span><span class="sxs-lookup"><span data-stu-id="a878c-206">To use a template from the explanation library</span></span>

1. <span data-ttu-id="a878c-207">Ga naar het gedeelte **Uitleg** van de **Train**-pagina van je model en selecteer **Nieuwe** en selecteer vervolgens **Van een sjabloon**.</span><span class="sxs-lookup"><span data-stu-id="a878c-207">From the **Explanations** section of your model's **Train** page, select **New**, then select **From a template**.</span></span></br>

   ![Van sjabloon maken](../media/content-understanding/from-template.png)</br>

2.  <span data-ttu-id="a878c-209">Selecteer op de pagina **Uitlegsjablonen** de uitleg die je wilt gebruiken en selecteer vervolgens **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="a878c-209">On the **Explanation templates** page, select the explanation you want to use, then select **Add**.</span></span></br>

       ![Selecteer een sjabloon](../media/content-understanding/phone-template.png)</br>

3. <span data-ttu-id="a878c-211">De informatie voor de sjabloon die je hebt geselecteerd, wordt weergegeven op de pagina **Een uitleg maken**.</span><span class="sxs-lookup"><span data-stu-id="a878c-211">The information for the template you selected displays on the **Create an explanation** page.</span></span> <span data-ttu-id="a878c-212">Bewerk zo nodig de naam van de uitleg en voeg items toe aan of verwijder items uit de patroonlijst.</span><span class="sxs-lookup"><span data-stu-id="a878c-212">If needed, edit the explanation name and add or remove items from the pattern list.</span></span> </br> 

   ![Sjabloon bewerken](../media/content-understanding/phone-template-live.png)</br>

4. <span data-ttu-id="a878c-214">Selecteer **Opslaan** wanneer je klaar bent.</span><span class="sxs-lookup"><span data-stu-id="a878c-214">When finished, select **Save**.</span></span>
