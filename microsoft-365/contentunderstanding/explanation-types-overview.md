---
title: Uitlegtypen
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: Meer informatie over uitlegtypen in Microsoft SharePoint Syntex
ms.openlocfilehash: 43272504912451e4690cb8b7fe351462371bb252
ms.sourcegitcommit: 3a0accd616ca94d6ba7f50e502552b45e9661a95
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/03/2020
ms.locfileid: "48350301"
---
# <a name="introduction-to-explanation-types"></a><span data-ttu-id="6a1a7-103">Inleiding tot uitlegtypen</span><span class="sxs-lookup"><span data-stu-id="6a1a7-103">Introduction to explanation types</span></span>

<span data-ttu-id="6a1a7-104">Uitleg wordt gebruikt om de gegevens te definiëren die je wilt labelen en ophalen in je documentinformatie over modellen in Microsoft SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="6a1a7-104">Explanations are used to help to define the information you want to label and extract in your document understanding models in Microsoft SharePoint Syntex.</span></span> <span data-ttu-id="6a1a7-105">Bij het maken van een uitleg moet je een uitlegtype selecteren.</span><span class="sxs-lookup"><span data-stu-id="6a1a7-105">When creating an explanation, you need to select an explanation type.</span></span> <span data-ttu-id="6a1a7-106">In dit artikel vind je meer informatie over de verschillende uitlegtypen en hoe je deze kunt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="6a1a7-106">This article will help you learn more to better understand the different explanation types and how they are used.</span></span> 

   ![Uitlegtypen](../media/content-understanding/explanation-types.png) 
   
<span data-ttu-id="6a1a7-108">Deze uitlegtypen zijn beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="6a1a7-108">These explanation types are available:</span></span>

- <span data-ttu-id="6a1a7-109">**Frasenlijst**: Lijst met woorden, woordgroepen, getallen of andere tekens die je kunt gebruiken in het document of de gegevens die je wilt ophalen.</span><span class="sxs-lookup"><span data-stu-id="6a1a7-109">**Phrase list**: List of words, phrases, numbers, or other characters you can use in the document or information that you are extracting.</span></span> <span data-ttu-id="6a1a7-110">De tekenreeks **Verwijzen naar Doctor** wordt bijvoorbeeld gebruikt in medische verwijsdocumenten die je identificeert.</span><span class="sxs-lookup"><span data-stu-id="6a1a7-110">For example, the text string **Referring Doctor** is in all Medical Referral documents you are identifying.</span></span></br>

- <span data-ttu-id="6a1a7-111">**Patroonlijst**: lijst patronen met getallen, letters of andere tekens die je kunt gebruiken om de gegevens te identificeren die je wilt ophalen.</span><span class="sxs-lookup"><span data-stu-id="6a1a7-111">**Pattern list**: List patterns of numbers, letters, or other characters that you can use to identify the information that you are extracting.</span></span> <span data-ttu-id="6a1a7-112">Je kunt bijvoorbeeld het **Telefoonnummer** van de verwijsarts extraheren uit medische verwijsdocumenten die je identificeert.</span><span class="sxs-lookup"><span data-stu-id="6a1a7-112">For example, you can extract the **Phone number** of the referring doctor from all Medical Referral document that you are identifying.</span></span></br>

- <span data-ttu-id="6a1a7-113">**Proximity**: in dit artikel wordt beschreven hoe dicht toelichtingen bij elkaar liggen.</span><span class="sxs-lookup"><span data-stu-id="6a1a7-113">**Proximity**: Describes how close explanations are to each other.</span></span> <span data-ttu-id="6a1a7-114">Een patroonlijst van *straatnummer* wordt bijvoorbeeld direct weergeven voor de woordenlijst met *straatnamen* zonder tokens ertussen (je vind meer informatie over tokens verderop in dit artikel).</span><span class="sxs-lookup"><span data-stu-id="6a1a7-114">For example, a *street number* pattern list goes right before the *street name* phrase list, with no tokens in between (you'll learn about tokens later in this article).</span></span> <span data-ttu-id="6a1a7-115">Voor het type proximity moet je ten minste twee uitleggen in je model hebben, of de optie wordt uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="6a1a7-115">Using the proximity type requires you to have at least two explanations in your model, or the option will be disabled.</span></span> 
 
## <a name="phrase-list"></a><span data-ttu-id="6a1a7-116">Woordenlijst</span><span class="sxs-lookup"><span data-stu-id="6a1a7-116">Phrase list</span></span>

<span data-ttu-id="6a1a7-117">Het uitlegtype van een woordenlijst wordt meestal gebruikt om een document te identificeren en te classificeren via je model.</span><span class="sxs-lookup"><span data-stu-id="6a1a7-117">A phrase list explanation type is typically used to identify and classify a document through your model.</span></span> <span data-ttu-id="6a1a7-118">Zoals wordt beschreven in het labelvoorbeeld *Verwijzende arts*, is het een tekenreeks met woorden, woordgroepen, getallen of tekens die consequent voorkomen in de documenten die je wilt herkennen.</span><span class="sxs-lookup"><span data-stu-id="6a1a7-118">As described in the *Referring Doctor* label example, it is a string of words, phrases, numbers, or characters that is consistently in the documents that you are identifying.</span></span>

<span data-ttu-id="6a1a7-119">Hoewel het geen eis is, kunt je je uitleg beter laten opvallen als de woordgroep die je wilt vastleggen zich op een consistente locatie in het document bevindt.</span><span class="sxs-lookup"><span data-stu-id="6a1a7-119">While not a requirement, you can achieve better success with your explanation if the phrase you are capturing is located in a consistent location in your document.</span></span> <span data-ttu-id="6a1a7-120">Zo kan het label *Verwijzende arts* label zich in de eerste alinea van het document bevinden.</span><span class="sxs-lookup"><span data-stu-id="6a1a7-120">For example, the *Referring Doctor* label may be consistently located in the first paragraph of the document.</span></span>

<span data-ttu-id="6a1a7-121">Als hoofdlettergevoeligheid een vereiste is bij het identificeren van je label, kun je met het woordenlijsttype in uw uitleg opgeven door het selectievakje **Alleen exacte kapitalisatie** in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="6a1a7-121">If case sensitivity is a requirement in identifying your label, using the phrase list type allows you to specify it in your explanation by selecting the **Only exact capitalization** checkbox.</span></span>

   ![Onderscheid tussen hoofdletters en kleine letters](../media/content-understanding/case-sensitivity.png) 

## <a name="pattern-lists"></a><span data-ttu-id="6a1a7-123">Patroonlijsten</span><span class="sxs-lookup"><span data-stu-id="6a1a7-123">Pattern lists</span></span>

<span data-ttu-id="6a1a7-124">Een patroonlijst is met name handig wanneer je een uitleg maakt waarmee gegevens uit een document worden geïdentificeerd en opgehaald.</span><span class="sxs-lookup"><span data-stu-id="6a1a7-124">A pattern list type is especially useful when you create an explanation that identifies and extracts information from a document.</span></span> <span data-ttu-id="6a1a7-125">Deze worden meestal weergegeven in verschillende indelingen, zoals datums, telefoonnummers of creditcardnummers.</span><span class="sxs-lookup"><span data-stu-id="6a1a7-125">It is typically presented in different formats, such as dates, phone numbers, or credit card numbers.</span></span> <span data-ttu-id="6a1a7-126">Een datum kan bijvoorbeeld worden weergegeven in een aantal verschillende notaties (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, 1 januari 2020, enzovoort).</span><span class="sxs-lookup"><span data-stu-id="6a1a7-126">For example, a date can be displayed in a number of different formats (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, Jan 1,2020, etc.).</span></span> <span data-ttu-id="6a1a7-127">Door een patroonlijst te definiëren, kun je je efficiënter identificeren door eventuele variaties in de gegevens vast te leggen die je probeert vast te stellen en op te halen.</span><span class="sxs-lookup"><span data-stu-id="6a1a7-127">Defining a pattern list makes your explanation more efficient by capturing any possible variations in the data that you are trying to identify and extract.</span></span> 

<span data-ttu-id="6a1a7-128">Voor het voorbeeld **Telefoonnummer** moet je het telefoonnummer voor elke verwijzende arts ophalen uit alle medische verwijzingsdocumenten die door het model worden geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="6a1a7-128">For the **Phone number** sample, extract the phone number for each referring doctor from all Medical Referral documents that the model identifies.</span></span> <span data-ttu-id="6a1a7-129">Wanneer je de uitleg maakt, selecteer je het patroonlijsttype om de verschillende indelingen toe te staan die mogelijk naar verwachting worden geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="6a1a7-129">When you create the explanation, select the Pattern list type to allow the different formats that you may expect to be returned.</span></span>

   ![Patroonlijst telefoonnummers](../media/content-understanding/pattern-list.png)

<span data-ttu-id="6a1a7-131">Voor dit voorbeeld selecteer je het selectievakje **een cijfer uit 0-9**.</span><span class="sxs-lookup"><span data-stu-id="6a1a7-131">For this sample, select the **Any digit from 0-9** checkbox.</span></span> <span data-ttu-id="6a1a7-132">Als je deze optie selecteert, wordt de waarde 0 tot en met 9 in de patroonlijst herkend als een willekeurige waarde van 0 tot en met 9.</span><span class="sxs-lookup"><span data-stu-id="6a1a7-132">Selecting this recognizes each "0" value used in your pattern list to be any digit from 0 through 9.</span></span>

   ![Een willekeurig cijfer van 0-9](../media/content-understanding/digit-identity.png)

<span data-ttu-id="6a1a7-134">Als je een patroonlijst maakt die teksttekens bevat, schakel je het selectievakje **Een letter van een-z** in.</span><span class="sxs-lookup"><span data-stu-id="6a1a7-134">Similarly, if you create a pattern list that includes text characters, select the **Any letter from a-z** checkbox.</span></span> <span data-ttu-id="6a1a7-135">Als je deze optie inschakelt, wordt elk teken dat in de patroonlijst wordt gebruikt, elk teken van "a" tot en met "z" herkent.</span><span class="sxs-lookup"><span data-stu-id="6a1a7-135">Selecting this recognizes each "a" character used in the pattern list to be any character from "a" to "z".</span></span>

<span data-ttu-id="6a1a7-136">Als je bijvoorbeeld een patroonlijst**Datum** maakt en je ervoor wilt zorgen dat een datumnotatie wordt ondersteund zoals *2020 1 januari*, moet je het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="6a1a7-136">For example, if you create a **Date** pattern list and you want to make sure that a date format such as *Jan 1, 2020* is recognized, you need to:</span></span>
- <span data-ttu-id="6a1a7-137">Voeg *AAA 0, 0000* en *AAA 00, 0000* aan de patroonlijst toe.</span><span class="sxs-lookup"><span data-stu-id="6a1a7-137">Add *aaa 0, 0000* and *aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="6a1a7-138">Zorg ervoor dat **Een willekeurige letter van a-z** is geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="6a1a7-138">Make sure that **Any letter from a-z** is also selected.</span></span>

   ![Een letter van a-z](../media/content-understanding/any-letter.png)

<span data-ttu-id="6a1a7-140">Als je hoofdlettereisen in je patroonlijst hebt, kun je ook het selectievakje **Alleen exact hoofdlettergebruik** selecteren.</span><span class="sxs-lookup"><span data-stu-id="6a1a7-140">Additionally, if you have capitalization requirements in your pattern list, you have the option to select the **Only exact capitalization** checkbox.</span></span> <span data-ttu-id="6a1a7-141">Als de eerste letter van de maand moet worden gekapitaliseerd, moet je het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="6a1a7-141">For the Date example, if you require the first letter of the month to be capitalized, you need to:</span></span>

- <span data-ttu-id="6a1a7-142">Voeg *Aaa 0, 0000* en *AAA 00, 0000* aan de patroonlijst toe.</span><span class="sxs-lookup"><span data-stu-id="6a1a7-142">Add *Aaa 0, 0000* and *Aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="6a1a7-143">Zorg ervoor dat **Alleen exact hoofdlettergebruik**ook is geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="6a1a7-143">Make sure that **Only exact capitalization** is also selected.</span></span>

   ![Alleen exact hoofdlettergebruik](../media/content-understanding/exact-caps.png)

> [!NOTE]
> <span data-ttu-id="6a1a7-145">Gebruik in plaats van het handmatig maken van een uitleg voor patroonlijsten de [Uitlegbibliotheek](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-explanation-templates) voor het gebruik van vooraf gemaakte patroonlijstsjablonen voor een algemene patroonlijsten, zoals *datum*, *telefoonnummer*, *creditcardnummer*, enzovoort.</span><span class="sxs-lookup"><span data-stu-id="6a1a7-145">Instead of manually creating pattern list explanation, use the [explanation library](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-explanation-templates) to use pre-made pattern list templates for common pattern list, such as *date*, *phone number*, *credit card number*, etc..</span></span> 

## <a name="proximity"></a><span data-ttu-id="6a1a7-146">Proximity</span><span class="sxs-lookup"><span data-stu-id="6a1a7-146">Proximity</span></span> 

<span data-ttu-id="6a1a7-147">Met het Proximity-uitlegtype kun je gegevens identificeren met behulp van de manier waarop je een ander stukje gegevens kunt identificeren.</span><span class="sxs-lookup"><span data-stu-id="6a1a7-147">The proximity explanation type helps your model identify data through defining how close another piece of data is to it.</span></span> <span data-ttu-id="6a1a7-148">Bijvoorbeeld, zo heb je in je model twee verklaringen gedefinieerd waaraan zowel het *huisnummer* als *telefoonnummer*is toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="6a1a7-148">For example, in your model, you have defined two explanations that label both the customer *Street address number* and *Phone number*.</span></span> 

<span data-ttu-id="6a1a7-149">Je ziet ook dat de telefoonnummers van klanten altijd voor het huisnummer worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="6a1a7-149">You also notice that customer phone numbers always appear before the street address number.</span></span> 

<span data-ttu-id="6a1a7-150">Alex Wilburn</span><span class="sxs-lookup"><span data-stu-id="6a1a7-150">Alex Wilburn</span></span><br>
<span data-ttu-id="6a1a7-151">555-555-5555</span><span class="sxs-lookup"><span data-stu-id="6a1a7-151">555-555-5555</span></span><br>
<span data-ttu-id="6a1a7-152">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="6a1a7-152">One Microsoft Way</span></span><br>
<span data-ttu-id="6a1a7-153">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="6a1a7-153">Redmond, WA 98034</span></span><br>

<span data-ttu-id="6a1a7-154">Gebruik de proximity-uitleg om te bepalen hoe ver de uitleg van een telefoonnummer is zodat u het huisnummer in je documenten beter kunt identificeren.</span><span class="sxs-lookup"><span data-stu-id="6a1a7-154">Use the proximity explanation to define how far away the phone number explanation is to better identify the street address number in your documents.</span></span>

   ![Proximity-uitleg](../media/content-understanding/proximity.png)</br>

#### <a name="what-are-tokens"></a><span data-ttu-id="6a1a7-156">Wat zijn tokens?</span><span class="sxs-lookup"><span data-stu-id="6a1a7-156">What are tokens?</span></span>

<span data-ttu-id="6a1a7-157">Voor het gebruik van het Proximity-uitlegtype moet je weten wat een token is, omdat het aantal tokens is hoe de proximity-uitleg de afstand tussen een verklaring en een andere meet.</span><span class="sxs-lookup"><span data-stu-id="6a1a7-157">In order to use the proximity explanation type, you need to understand what a token is, as the number of tokens is how the proximity explanation measures distance from one explanation to another.</span></span>  

<span data-ttu-id="6a1a7-158">Een token is een doorlopende reeks (geen spaties of interpunctie) van letters en cijfers.</span><span class="sxs-lookup"><span data-stu-id="6a1a7-158">A token is a continuous span (no spaces or punctuation) of letters and numbers.</span></span> <span data-ttu-id="6a1a7-159">Een spatie is GEEN token.</span><span class="sxs-lookup"><span data-stu-id="6a1a7-159">A space is NOT a token.</span></span> <span data-ttu-id="6a1a7-160">Elk leesteken is een token.</span><span class="sxs-lookup"><span data-stu-id="6a1a7-160">Each punctuation character is a token.</span></span> <span data-ttu-id="6a1a7-161">In de volgende tabel zie je enkele voorbeelden van hoe je het aantal tokens in een woordgroep kunt vaststellen.</span><span class="sxs-lookup"><span data-stu-id="6a1a7-161">The following table shows some examples of how to determine the number of tokens in a phrase.</span></span>

|<span data-ttu-id="6a1a7-162">Woordengroep</span><span class="sxs-lookup"><span data-stu-id="6a1a7-162">Phrase</span></span>|<span data-ttu-id="6a1a7-163">Aantal tokens</span><span class="sxs-lookup"><span data-stu-id="6a1a7-163">Number of tokens</span></span>|<span data-ttu-id="6a1a7-164">Uitleg</span><span class="sxs-lookup"><span data-stu-id="6a1a7-164">Explanation</span></span>|
|--|--|--|
|`Dog`|<span data-ttu-id="6a1a7-165">1</span><span class="sxs-lookup"><span data-stu-id="6a1a7-165">1</span></span>|<span data-ttu-id="6a1a7-166">Eén woord zonder leesteken of spatie.</span><span class="sxs-lookup"><span data-stu-id="6a1a7-166">A single word with no punctuation or spaces.</span></span>|
|`RMT33W`|<span data-ttu-id="6a1a7-167">1</span><span class="sxs-lookup"><span data-stu-id="6a1a7-167">1</span></span>|<span data-ttu-id="6a1a7-168">Een record locatornummer.</span><span class="sxs-lookup"><span data-stu-id="6a1a7-168">A record locator number.</span></span> <span data-ttu-id="6a1a7-169">Het mag cijfers en letters bevatten, maar geen leesteken.</span><span class="sxs-lookup"><span data-stu-id="6a1a7-169">It may have numbers and letters, but does not have any punctuation.</span></span>|
|`425-555-5555`|<span data-ttu-id="6a1a7-170">5</span><span class="sxs-lookup"><span data-stu-id="6a1a7-170">5</span></span>|<span data-ttu-id="6a1a7-171">Een telefoonnummer.</span><span class="sxs-lookup"><span data-stu-id="6a1a7-171">A phone number.</span></span> <span data-ttu-id="6a1a7-172">Elk leesteken bestaat uit één token, zodat  `425-555-5555` 5 tokens zou zijn:</span><span class="sxs-lookup"><span data-stu-id="6a1a7-172">Each punctuation mark is a single token so  `425-555-5555` would be 5 tokens:</span></span><br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|<span data-ttu-id="6a1a7-173">7</span><span class="sxs-lookup"><span data-stu-id="6a1a7-173">7</span></span>|`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a><span data-ttu-id="6a1a7-174">Het proximity-uitlegtype configureren</span><span class="sxs-lookup"><span data-stu-id="6a1a7-174">Configure the proximity explanation type</span></span>

<span data-ttu-id="6a1a7-175">Voor het voorbeeld configureer je de proximity-instelling zodanig dat we het aantal tokens kunnen definiëren dat de*telefoonnummer*-uitleg afkomstig is van de*straatnummer*-uitleg.</span><span class="sxs-lookup"><span data-stu-id="6a1a7-175">For the sample, configure the proximity setting so that we can define the range of the number of tokens the *Phone number* explanation is from the *Street address number* explanation.</span></span>

<span data-ttu-id="6a1a7-176">Je ziet dat het minimumbereik „0“ is omdat er geen tokens zijn tussen het telefoonnummer en het huisnummer.</span><span class="sxs-lookup"><span data-stu-id="6a1a7-176">You should see that the minimum range is "0" since there are no tokens between the phone number and street address number.</span></span>

<span data-ttu-id="6a1a7-177">Sommige telefoonnummers in de voorbeelddocumenten worden echter toegevoegd met *(mobiel)*.</span><span class="sxs-lookup"><span data-stu-id="6a1a7-177">However, some phone numbers in the sample documents are appended with *(mobile)*.</span></span>

<span data-ttu-id="6a1a7-178">Wander Kuijken</span><span class="sxs-lookup"><span data-stu-id="6a1a7-178">Nestor Wilke</span></span><br>
<span data-ttu-id="6a1a7-179">111-111-1111 (mobiel)</span><span class="sxs-lookup"><span data-stu-id="6a1a7-179">111-111-1111 (mobile)</span></span><br>
<span data-ttu-id="6a1a7-180">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="6a1a7-180">One Microsoft Way</span></span><br>
<span data-ttu-id="6a1a7-181">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="6a1a7-181">Redmond, WA 98034</span></span><br>

<span data-ttu-id="6a1a7-182">Er zijn drie tokens in *(mobiel)*:</span><span class="sxs-lookup"><span data-stu-id="6a1a7-182">There are three tokens in *(mobile)*:</span></span>

|<span data-ttu-id="6a1a7-183">Woordengroep</span><span class="sxs-lookup"><span data-stu-id="6a1a7-183">Phrase</span></span>|<span data-ttu-id="6a1a7-184">Aantal tokens</span><span class="sxs-lookup"><span data-stu-id="6a1a7-184">Token count</span></span>|
|--|--|
|<span data-ttu-id="6a1a7-185">(</span><span class="sxs-lookup"><span data-stu-id="6a1a7-185">(</span></span>|<span data-ttu-id="6a1a7-186">1</span><span class="sxs-lookup"><span data-stu-id="6a1a7-186">1</span></span>|
|<span data-ttu-id="6a1a7-187">Mobiel</span><span class="sxs-lookup"><span data-stu-id="6a1a7-187">mobile</span></span>|<span data-ttu-id="6a1a7-188">2</span><span class="sxs-lookup"><span data-stu-id="6a1a7-188">2</span></span>|
|<span data-ttu-id="6a1a7-189">)</span><span class="sxs-lookup"><span data-stu-id="6a1a7-189">)</span></span>|<span data-ttu-id="6a1a7-190">3</span><span class="sxs-lookup"><span data-stu-id="6a1a7-190">3</span></span>|

<span data-ttu-id="6a1a7-191">Configureer de proximity-instelling voor een bereik van 0 tot en met 3.</span><span class="sxs-lookup"><span data-stu-id="6a1a7-191">Configure the proximity setting to have a range of 0 through 3.</span></span>

   ![Voorbeeld van proximity](../media/content-understanding/proximity-example.png)</br>

## <a name="use-explanation-templates"></a><span data-ttu-id="6a1a7-193">Uitlegsjablonen gebruiken</span><span class="sxs-lookup"><span data-stu-id="6a1a7-193">Use explanation templates</span></span>

<span data-ttu-id="6a1a7-194">Hoewel je handmatig verschillende waarden voor een patroonlijst kunt toevoegen voor je uitleg, is het veel eenvoudiger om de vooraf gemaakte sjablonen te gebruiken die in de uitlegbibliotheek worden aangeboden.</span><span class="sxs-lookup"><span data-stu-id="6a1a7-194">While you can manually add various pattern list values for your explanation, it can be much easier to use the pre-created templates provided to you in the explanation library.</span></span>

<span data-ttu-id="6a1a7-195">Je kunt bijvoorbeeld in plaats van alle variaties voor *Datum*handmatig toe te voegen, de sjabloonlijst met patronen gebruiken voor *Datum*, die al een aantal waarden voor een patroonlijst bevat:</span><span class="sxs-lookup"><span data-stu-id="6a1a7-195">For example, instead of manually adding all the variations for *Date*, you can use the pattern list template for *Date*, that already includes a number of pattern lists values:</span></span></br>

   ![Uitlegbibliotheek](../media/content-understanding/explanation-template.png)</br>
 
<span data-ttu-id="6a1a7-197">De uitlegbibliotheek bevat een aantal veelgebruikte beschrijvingen van de patroonlijst, waaronder:</span><span class="sxs-lookup"><span data-stu-id="6a1a7-197">The explanation library includes a number of commonly used pattern list explanations, including:</span></span></br>

- <span data-ttu-id="6a1a7-198">Datum</span><span class="sxs-lookup"><span data-stu-id="6a1a7-198">Date</span></span></br>
- <span data-ttu-id="6a1a7-199">Datum (getal)</span><span class="sxs-lookup"><span data-stu-id="6a1a7-199">Date (numeric)</span></span></br>
- <span data-ttu-id="6a1a7-200">Tijd</span><span class="sxs-lookup"><span data-stu-id="6a1a7-200">Time</span></span></br>
- <span data-ttu-id="6a1a7-201">Nummer</span><span class="sxs-lookup"><span data-stu-id="6a1a7-201">Number</span></span></br>
- <span data-ttu-id="6a1a7-202">Telefoonnummer</span><span class="sxs-lookup"><span data-stu-id="6a1a7-202">Phone number</span></span></br>
- <span data-ttu-id="6a1a7-203">Postcode</span><span class="sxs-lookup"><span data-stu-id="6a1a7-203">Zip code</span></span></br>
- <span data-ttu-id="6a1a7-204">Eerste woord of zin</span><span class="sxs-lookup"><span data-stu-id="6a1a7-204">First word of sentence</span></span></br>
- <span data-ttu-id="6a1a7-205">Creditcard</span><span class="sxs-lookup"><span data-stu-id="6a1a7-205">Credit card</span></span></br>
- <span data-ttu-id="6a1a7-206">Sofi-nummer</span><span class="sxs-lookup"><span data-stu-id="6a1a7-206">Social security number</span></span></br>

<span data-ttu-id="6a1a7-207">Let op: de uitlegbibliotheek bevat ook sjablonen voor verklaringen van een fraselijst, waaronder:</span><span class="sxs-lookup"><span data-stu-id="6a1a7-207">Note that the explanation library also includes templates for phrase list explanations as well, including:</span></span>
- <span data-ttu-id="6a1a7-208">Afgelopen zin</span><span class="sxs-lookup"><span data-stu-id="6a1a7-208">End of sentence</span></span>
- <span data-ttu-id="6a1a7-209">Valuta</span><span class="sxs-lookup"><span data-stu-id="6a1a7-209">Currency</span></span>

#### <a name="to-use-a-template-from-the-explanation-library"></a><span data-ttu-id="6a1a7-210">Een sjabloon gebruiken uit de uitlegbibliotheek</span><span class="sxs-lookup"><span data-stu-id="6a1a7-210">To use a template from the explanation library</span></span>

1. <span data-ttu-id="6a1a7-211">Ga naar het gedeelte **Uitleg** van de **Train**-pagina van je model en selecteer **Nieuwe**en selecteer vervolgens **Van een sjabloon**.</span><span class="sxs-lookup"><span data-stu-id="6a1a7-211">From the **Explanations** section of your model's **Train** page, select **New**, then select **From a template**.</span></span></br>

   ![Van sjabloon maken](../media/content-understanding/from-template.png)</br>

2.  <span data-ttu-id="6a1a7-213">Selecteer op de pagina **Uitlegsjablonen** de uitleg die je wilt gebruiken en selecteer vervolgens **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="6a1a7-213">On the **Explanation templates** page, select the explanation you want to use, and then select **Add**.</span></span></br>

       ![Selecteer een sjabloon](../media/content-understanding/phone-template.png)</br>

3. <span data-ttu-id="6a1a7-215">De informatie voor de sjabloon die je hebt geselecteerd, wordt weergegeven op de **Een uitleg maken**.</span><span class="sxs-lookup"><span data-stu-id="6a1a7-215">The information for the template you selected will display on the **Create an explanation** page.</span></span> <span data-ttu-id="6a1a7-216">Bewerk zo nodig de naam van de uitleg en voeg items toe aan of te verwijderen uit de patroonlijst.</span><span class="sxs-lookup"><span data-stu-id="6a1a7-216">If needed, edit the explanation name, and add or remove items from the pattern list.</span></span> </br> 

   ![Sjabloon bewerken](../media/content-understanding/phone-template-live.png)</br>

4. <span data-ttu-id="6a1a7-218">Selecteer **Opslaan** wanneer je klaar bent.</span><span class="sxs-lookup"><span data-stu-id="6a1a7-218">When finished, select **Save**.</span></span>
