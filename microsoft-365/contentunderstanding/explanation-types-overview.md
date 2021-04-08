---
title: Uitlegtypen
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
description: Meer informatie over uitlegtypen in Microsoft SharePoint Syntex
ms.openlocfilehash: a5404230a59d1740a2b855527229a7aca92195a8
ms.sourcegitcommit: dc1ac43a57fac6f57438859dd668f927d94fdf34
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/07/2021
ms.locfileid: "51604403"
---
# <a name="introduction-to-explanation-types"></a><span data-ttu-id="90c07-103">Inleiding tot uitlegtypen</span><span class="sxs-lookup"><span data-stu-id="90c07-103">Introduction to explanation types</span></span>

<span data-ttu-id="90c07-104">Uitleg wordt gebruikt om de gegevens te definiëren die je wilt labelen en ophalen in je documentinformatie over modellen in Microsoft SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="90c07-104">Explanations are used to help to define the information you want to label and extract in your document understanding models in Microsoft SharePoint Syntex.</span></span> <span data-ttu-id="90c07-105">Bij het maken van een uitleg moet je een uitlegtype selecteren.</span><span class="sxs-lookup"><span data-stu-id="90c07-105">When creating an explanation, you need to select an explanation type.</span></span> <span data-ttu-id="90c07-106">In dit artikel vind je meer informatie over de verschillende uitlegtypen en hoe je deze kunt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="90c07-106">This article helps you understand the different explanation types and how they are used.</span></span> 

![Uitlegtypen](../media/content-understanding/explanation-types.png) 
   
<span data-ttu-id="90c07-108">Deze uitlegtypen zijn beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="90c07-108">These explanation types are available:</span></span>

- <span data-ttu-id="90c07-109">**Frasenlijst**: Lijst met woorden, woordgroepen, getallen of andere tekens die je kunt gebruiken in het document of de gegevens die je wilt ophalen.</span><span class="sxs-lookup"><span data-stu-id="90c07-109">**Phrase list**: List of words, phrases, numbers, or other characters you can use in the document or information that you are extracting.</span></span> <span data-ttu-id="90c07-110">De tekenreeks **Verwijzen naar Doctor** wordt bijvoorbeeld gebruikt in medische verwijsdocumenten die je identificeert.</span><span class="sxs-lookup"><span data-stu-id="90c07-110">For example, the text string **Referring Doctor** is in all Medical Referral documents you are identifying.</span></span> <span data-ttu-id="90c07-111">Of het **telefoonnummer** van de verwijzende arts uit medische verwijzingsdocumenten die u identificeert.</span><span class="sxs-lookup"><span data-stu-id="90c07-111">Or the **Phone number** of the referring doctor from all Medical Referral document that you are identifying.</span></span>

- <span data-ttu-id="90c07-112">**Nabijheid**: in dit artikel wordt beschreven hoe dicht toelichtingen bij elkaar liggen.</span><span class="sxs-lookup"><span data-stu-id="90c07-112">**Proximity**: Describes how close explanations are to each other.</span></span> <span data-ttu-id="90c07-113">Een lijst met *straatnummers* staat bijvoorbeeld vlak voor de lijst met *straatnamen*, zonder tokens ertussen (verderop in dit artikel vindt u meer informatie over tokens).</span><span class="sxs-lookup"><span data-stu-id="90c07-113">For example, a *street number* phrase list goes right before the *street name* phrase list, with no tokens in between (you'll learn about tokens later in this article).</span></span> <span data-ttu-id="90c07-114">Voor het type proximity moet je ten minste twee uitleggen in je model hebben, of de optie wordt uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="90c07-114">Using the proximity type requires you to have at least two explanations in your model or the option will be disabled.</span></span> 
 
## <a name="phrase-list"></a><span data-ttu-id="90c07-115">Woordenlijst</span><span class="sxs-lookup"><span data-stu-id="90c07-115">Phrase list</span></span>

<span data-ttu-id="90c07-116">Het uitlegtype van een woordenlijst wordt meestal gebruikt om een document te identificeren en te classificeren via je model.</span><span class="sxs-lookup"><span data-stu-id="90c07-116">A phrase list explanation type is typically used to identify and classify a document through your model.</span></span> <span data-ttu-id="90c07-117">Zoals wordt beschreven in het labelvoorbeeld *Verwijzende arts*, is het een tekenreeks met woorden, woordgroepen, getallen of tekens die consequent voorkomen in de documenten die je wilt herkennen.</span><span class="sxs-lookup"><span data-stu-id="90c07-117">As described in the *Referring Doctor* label example, it is a string of words, phrases, numbers, or characters that is consistently in the documents that you are identifying.</span></span>

<span data-ttu-id="90c07-118">Hoewel het geen eis is, kunt je je uitleg beter laten opvallen als de woordgroep die je wilt vastleggen zich op een consistente locatie in het document bevindt.</span><span class="sxs-lookup"><span data-stu-id="90c07-118">While not a requirement, you can achieve better success with your explanation if the phrase you are capturing is located in a consistent location in your document.</span></span> <span data-ttu-id="90c07-119">Zo kan het label *Verwijzende arts* label zich in de eerste alinea van het document bevinden.</span><span class="sxs-lookup"><span data-stu-id="90c07-119">For example, the *Referring Doctor* label may be consistently located in the first paragraph of the document.</span></span> <span data-ttu-id="90c07-120">U kunt ook de optie **[Configureren waar zinnen voorkomen in het document](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#configure-where-phrases-occur-in-the-document)** in de geavanceerde instellingen gebruiken om specifieke gebieden te selecteren waar de zin zich bevindt, vooral als de kans bestaat dat de zin op meerdere locaties in uw document voorkomt.</span><span class="sxs-lookup"><span data-stu-id="90c07-120">You can also use the **[Configure where phrases occur in the document](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#configure-where-phrases-occur-in-the-document)** advanced setting to select specific areas where the phrase is located, especially if there is a chance that the phrase might occur in multiple locations in your document.</span></span>

<span data-ttu-id="90c07-121">Als hoofdlettergevoeligheid een vereiste is bij het identificeren van je label, kun je met het woordenlijsttype in uw uitleg opgeven door het selectievakje **Alleen exacte kapitalisatie** in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="90c07-121">If case sensitivity is a requirement in identifying your label, using the phrase list type allows you to specify it in your explanation by selecting the **Only exact capitalization** checkbox.</span></span>

![Onderscheid tussen hoofdletters en kleine letters](../media/content-understanding/case-sensitivity.png) 

<span data-ttu-id="90c07-123">Een patroonlijst is vooral handig wanneer u een uitleg maakt die informatie in verschillende indelingen identificeert en extraheert, zoals datums, telefoonnummers en creditcardnummers.</span><span class="sxs-lookup"><span data-stu-id="90c07-123">A phrase type is especially useful when you create an explanation that identifies and extracts information in different formats, such as dates, phone numbers, and credit card numbers.</span></span> <span data-ttu-id="90c07-124">Een datum kan bijvoorbeeld worden weergegeven in een aantal verschillende notaties (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, 1 januari 2020, enzovoort).</span><span class="sxs-lookup"><span data-stu-id="90c07-124">For example, a date can be displayed in a number of different formats (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, Jan 1,2020, etc.).</span></span> <span data-ttu-id="90c07-125">Door een patroonlijst te definiëren, kunt u efficiënter identificeren door eventuele variaties in de gegevens vast te leggen die u probeert vast te stellen en op te halen.</span><span class="sxs-lookup"><span data-stu-id="90c07-125">Defining a phrase list makes your explanation more efficient by capturing any possible variations in the data that you are trying to identify and extract.</span></span> 

<span data-ttu-id="90c07-126">Voor het voorbeeld **Telefoonnummer** moet je het telefoonnummer voor elke verwijzende arts ophalen uit alle Medische Verwijzingsdocumenten die door het model worden geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="90c07-126">For the **Phone number** example, you extract the phone number for each referring doctor from all Medical Referral documents that the model identifies.</span></span> <span data-ttu-id="90c07-127">Wanneer u de uitleg maakt, typt u de verschillende notaties die een telefoonnummer in uw document kan weergeven, zodat u mogelijke variaties kunt vastleggen.</span><span class="sxs-lookup"><span data-stu-id="90c07-127">When you create the explanation, type the different formats a phone number might display in your document so that you are able to capture possible variations.</span></span> 

![Patroonlijst met telefoonnummers](../media/content-understanding/pattern-list.png)

<span data-ttu-id="90c07-129">Schakel voor dit voorbeeld in **Geavanceerde instellingen** het selectievakje **Elk cijfer van 0-9** in om elke '0'-waarde die in uw lijst met zinnen wordt gebruikt, te herkennen als een cijfer van 0 tot en met 9.</span><span class="sxs-lookup"><span data-stu-id="90c07-129">For this example, in **Advanced Settings** select the **Any digit from 0-9** checkbox to recognize each "0" value used in your phrase list to be any digit from 0 through 9.</span></span>

![Een willekeurig cijfer van 0-9](../media/content-understanding/digit-identity.png)

<span data-ttu-id="90c07-131">Als u een patroonlijst maakt die teksttekens bevat, selecteert u het selectievakje **Willekeurige letter van a-z** om aan te geven dat elk 'a'-teken dat in de patroonlijst wordt gebruikt, elk teken van 'a' tot 'z' kan zijn.</span><span class="sxs-lookup"><span data-stu-id="90c07-131">Similarly, if you create a phrase list that includes text characters, select the **Any letter from a-z** checkbox to recognize each "a" character used in the phrase list to be any character from "a" to "z".</span></span>

<span data-ttu-id="90c07-132">Als u bijvoorbeeld een patroonlijst **Datum** maakt en u ervoor wilt zorgen dat een datumnotatie wordt ondersteund zoals *1 januari 2020*, moet u het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="90c07-132">For example, if you create a **Date** phrase list and you want to make sure that a date format such as *Jan 1, 2020* is recognized, you need to:</span></span>
- <span data-ttu-id="90c07-133">Voeg *0 AAA 0000* en *00 AAA 0000* aan de patroonlijst toe.</span><span class="sxs-lookup"><span data-stu-id="90c07-133">Add *aaa 0, 0000* and *aaa 00, 0000* to your phrase list.</span></span>
- <span data-ttu-id="90c07-134">Zorg ervoor dat **Een willekeurige letter van a-z** is geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="90c07-134">Make sure that **Any letter from a-z** is also selected.</span></span>

![Een letter van a-z](../media/content-understanding/any-letter.png)

<span data-ttu-id="90c07-136">Als je hoofdlettereisen in je patroonlijst hebt, kun je ook het selectievakje **Alleen exact hoofdlettergebruik** selecteren.</span><span class="sxs-lookup"><span data-stu-id="90c07-136">Additionally, if you have capitalization requirements in your phrase list, you have the option to select the **Only exact capitalization** checkbox.</span></span> <span data-ttu-id="90c07-137">Als de eerste letter van de maand moet worden gekapitaliseerd, moet u het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="90c07-137">For the Date example, if you require the first letter of the month to be capitalized, you need to:</span></span>

- <span data-ttu-id="90c07-138">Voeg *0 Aaa 0000* en *00 AAA 0000* aan de patroonlijst toe.</span><span class="sxs-lookup"><span data-stu-id="90c07-138">Add *Aaa 0, 0000* and *Aaa 00, 0000* to your phrase list.</span></span>
- <span data-ttu-id="90c07-139">Zorg ervoor dat **Alleen exact hoofdlettergebruik** ook is geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="90c07-139">Make sure that **Only exact capitalization** is also selected.</span></span>

![Alleen exact hoofdlettergebruik](../media/content-understanding/exact-caps.png)

> [!NOTE]
> <span data-ttu-id="90c07-141">Gebruik in plaats van het handmatig maken van een uitleg voor patroonlijsten de [uitlegbibliotheek](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-explanation-templates) voor het gebruik van vooraf gemaakte patroonlijstsjablonen voor een algemene patroonlijst, zoals *datum*, *telefoonnummer*, *creditcardnummer*, enzovoort.</span><span class="sxs-lookup"><span data-stu-id="90c07-141">Instead of manually creating a phrase list explanation, use the [explanation library](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-explanation-templates) to use phrase list templates for a common phrase list, such as *date*, *phone number*, *credit card number*, etc.</span></span>

## <a name="proximity"></a><span data-ttu-id="90c07-142">Proximity</span><span class="sxs-lookup"><span data-stu-id="90c07-142">Proximity</span></span> 

<span data-ttu-id="90c07-143">Met het Proximity-uitlegtype kan je model identificeren met behulp van hoe dichtbij een ander stukje gegevens is.</span><span class="sxs-lookup"><span data-stu-id="90c07-143">The proximity explanation type helps your model identify data by defining how close another piece of data is to it.</span></span> <span data-ttu-id="90c07-144">Bijvoorbeeld, in je model heb je twee verklaringen gedefinieerd waaraan zowel het *huisnummer* als *telefoonnummer* zijn gelabeld.</span><span class="sxs-lookup"><span data-stu-id="90c07-144">For example, in your model say you have defined two explanations that label both the customer *Street address number* and *Phone number*.</span></span> 

<span data-ttu-id="90c07-145">Je ziet ook dat de telefoonnummers van klanten altijd voor het huisnummer worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="90c07-145">Notice that customer phone numbers always appear before the street address number.</span></span> 

<span data-ttu-id="90c07-146">Alex Wilburn</span><span class="sxs-lookup"><span data-stu-id="90c07-146">Alex Wilburn</span></span><br>
<span data-ttu-id="90c07-147">555-555-5555</span><span class="sxs-lookup"><span data-stu-id="90c07-147">555-555-5555</span></span><br>
<span data-ttu-id="90c07-148">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="90c07-148">One Microsoft Way</span></span><br>
<span data-ttu-id="90c07-149">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="90c07-149">Redmond, WA 98034</span></span><br>

<span data-ttu-id="90c07-150">Gebruik de proximity-uitleg om te bepalen hoe ver de uitleg van een telefoonnummer is zodat u het huisnummer in je documenten beter kunt identificeren.</span><span class="sxs-lookup"><span data-stu-id="90c07-150">Use the proximity explanation to define how far away the phone number explanation is to better identify the street address number in your documents.</span></span>

![Proximity-uitleg](../media/content-understanding/proximity.png)

#### <a name="what-are-tokens"></a><span data-ttu-id="90c07-152">Wat zijn tokens?</span><span class="sxs-lookup"><span data-stu-id="90c07-152">What are tokens?</span></span>

<span data-ttu-id="90c07-153">Voor het gebruik van het Proximity-uitlegtype moet je weten wat een token is, omdat het aantal tokens is hoe de proximity-uitleg de afstand tussen een verklaring en een andere meet.</span><span class="sxs-lookup"><span data-stu-id="90c07-153">In order to use the proximity explanation type, you need to understand what a token is, as the number of tokens is how the proximity explanation measures distance from one explanation to another.</span></span> <span data-ttu-id="90c07-154">Een token is een doorlopende reeks (geen spaties of interpunctie) van letters en cijfers.</span><span class="sxs-lookup"><span data-stu-id="90c07-154">A token is a continuous span (not including spaces or punctuation) of letters and numbers.</span></span> 

<span data-ttu-id="90c07-155">In de volgende tabel zie je enkele voorbeelden van hoe je het aantal tokens in een woordgroep kunt vaststellen.</span><span class="sxs-lookup"><span data-stu-id="90c07-155">The following table shows examples for how to determine the number of tokens in a phrase.</span></span>

|<span data-ttu-id="90c07-156">Woordengroep</span><span class="sxs-lookup"><span data-stu-id="90c07-156">Phrase</span></span>|<span data-ttu-id="90c07-157">Aantal tokens</span><span class="sxs-lookup"><span data-stu-id="90c07-157">Number of tokens</span></span>|<span data-ttu-id="90c07-158">Uitleg</span><span class="sxs-lookup"><span data-stu-id="90c07-158">Explanation</span></span>|
|--|--|--|
|`Dog`|<span data-ttu-id="90c07-159">1</span><span class="sxs-lookup"><span data-stu-id="90c07-159">1</span></span>|<span data-ttu-id="90c07-160">Eén woord zonder leesteken of spatie.</span><span class="sxs-lookup"><span data-stu-id="90c07-160">A single word with no punctuation or spaces.</span></span>|
|`RMT33W`|<span data-ttu-id="90c07-161">1</span><span class="sxs-lookup"><span data-stu-id="90c07-161">1</span></span>|<span data-ttu-id="90c07-162">Een record locatornummer.</span><span class="sxs-lookup"><span data-stu-id="90c07-162">A record locator number.</span></span> <span data-ttu-id="90c07-163">Het mag cijfers en letters bevatten, maar geen leestekens.</span><span class="sxs-lookup"><span data-stu-id="90c07-163">It may include numbers and letters, but does not have punctuation.</span></span>|
|`425-555-5555`|<span data-ttu-id="90c07-164">5</span><span class="sxs-lookup"><span data-stu-id="90c07-164">5</span></span>|<span data-ttu-id="90c07-165">Een telefoonnummer.</span><span class="sxs-lookup"><span data-stu-id="90c07-165">A phone number.</span></span> <span data-ttu-id="90c07-166">Elk leesteken bestaat uit één token, zodat `425-555-5555` 5 tokens zou zijn:</span><span class="sxs-lookup"><span data-stu-id="90c07-166">Each punctuation mark is a single token, so `425-555-5555` is 5 tokens:</span></span><br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|<span data-ttu-id="90c07-167">7</span><span class="sxs-lookup"><span data-stu-id="90c07-167">7</span></span>|`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a><span data-ttu-id="90c07-168">Het proximity-uitlegtype configureren</span><span class="sxs-lookup"><span data-stu-id="90c07-168">Configure the proximity explanation type</span></span>

<span data-ttu-id="90c07-169">Voor het voorbeeld configureer je de proximity-instelling zodanig dat je het aantal tokens kunt definiëren in *Telefoonnummer*-uitleg afkomstig van de *Huisnummer*-uitleg.</span><span class="sxs-lookup"><span data-stu-id="90c07-169">For the example, configure the proximity setting to define the range of the number of tokens in the *Phone number* explanation from the *Street address number* explanation.</span></span> <span data-ttu-id="90c07-170">Je ziet dat het minimumbereik “0“ is omdat er geen tokens zijn tussen het telefoonnummer en het huisnummer.</span><span class="sxs-lookup"><span data-stu-id="90c07-170">Notice that the minimum range is "0", because there are no tokens between the phone number and street address number.</span></span>

<span data-ttu-id="90c07-171">Sommige telefoonnummers in de voorbeelddocumenten worden echter toegevoegd met *(mobiel)*.</span><span class="sxs-lookup"><span data-stu-id="90c07-171">But some phone numbers in the sample documents are appended with *(mobile)*.</span></span>

<span data-ttu-id="90c07-172">Wander Kuijken</span><span class="sxs-lookup"><span data-stu-id="90c07-172">Nestor Wilke</span></span><br>
<span data-ttu-id="90c07-173">111-111-1111 (mobiel)</span><span class="sxs-lookup"><span data-stu-id="90c07-173">111-111-1111 (mobile)</span></span><br>
<span data-ttu-id="90c07-174">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="90c07-174">One Microsoft Way</span></span><br>
<span data-ttu-id="90c07-175">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="90c07-175">Redmond, WA 98034</span></span><br>

<span data-ttu-id="90c07-176">Er zijn drie tokens in *(mobiel)*:</span><span class="sxs-lookup"><span data-stu-id="90c07-176">There are three tokens in *(mobile)*:</span></span>

|<span data-ttu-id="90c07-177">Woordengroep</span><span class="sxs-lookup"><span data-stu-id="90c07-177">Phrase</span></span>|<span data-ttu-id="90c07-178">Aantal tokens</span><span class="sxs-lookup"><span data-stu-id="90c07-178">Token count</span></span>|
|--|--|
|<span data-ttu-id="90c07-179">(</span><span class="sxs-lookup"><span data-stu-id="90c07-179">(</span></span>|<span data-ttu-id="90c07-180">1</span><span class="sxs-lookup"><span data-stu-id="90c07-180">1</span></span>|
|<span data-ttu-id="90c07-181">Mobiel</span><span class="sxs-lookup"><span data-stu-id="90c07-181">mobile</span></span>|<span data-ttu-id="90c07-182">2</span><span class="sxs-lookup"><span data-stu-id="90c07-182">2</span></span>|
|<span data-ttu-id="90c07-183">)</span><span class="sxs-lookup"><span data-stu-id="90c07-183">)</span></span>|<span data-ttu-id="90c07-184">3</span><span class="sxs-lookup"><span data-stu-id="90c07-184">3</span></span>|

<span data-ttu-id="90c07-185">Configureer de proximity-instelling voor een bereik van 0 tot en met 3.</span><span class="sxs-lookup"><span data-stu-id="90c07-185">Configure the proximity setting to have a range of 0 through 3.</span></span>

![Voorbeeld van proximity](../media/content-understanding/proximity-example.png)


## <a name="configure-where-phrases-occur-in-the-document"></a><span data-ttu-id="90c07-187">Configureren waar woordgroepen voorkomen in het document</span><span class="sxs-lookup"><span data-stu-id="90c07-187">Configure where phrases occur in the document</span></span>

<span data-ttu-id="90c07-188">Wanneer u een uitleg maakt, wordt standaard in het hele document gezocht naar de woordgroep die u wilt extraheren.</span><span class="sxs-lookup"><span data-stu-id="90c07-188">When you create an explanation, by default the entire document is searched for the phrase you are trying to extract.</span></span> <span data-ttu-id="90c07-189">U kunt echter de geavanceerde instelling **Waar deze woordgroepen voorkomen** gebruiken om een specifieke locatie in het document te isoleren waar een woordgroep voorkomt.</span><span class="sxs-lookup"><span data-stu-id="90c07-189">However, you can use the **Where these phrases occur** advanced setting to help in isolating a specific location in the document that a phrase occurs.</span></span> <span data-ttu-id="90c07-190">Dit is handig in situaties waarin soortgelijke gevallen van een woordgroep ergens anders in het document kunnen worden weergegeven en u wilt ervoor zorgen dat de juiste is geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="90c07-190">This is useful in situations where similar instances of a phrase might appear somewhere else in the document, and you want to make sure that the correct one is selected.</span></span> <span data-ttu-id="90c07-191">Wanneer we kijken naar ons voorbeelddocument voor medische verwijzing, wordt de **Verwijzende arts** altijd in de eerste alinea van het document vermeld.</span><span class="sxs-lookup"><span data-stu-id="90c07-191">Referring to our Medical Referral document example, the **Referring Doctor** is always mentioned in the first paragraph of the document.</span></span> <span data-ttu-id="90c07-192">Met de instelling \*\*Waar deze woordgroepen voorkomen kunt u in dit voorbeeld de uitleg zo configureren dat alleen in het begin van het document naar dit label wordt gezocht, of op een andere locatie waar dit kan voorkomen.</span><span class="sxs-lookup"><span data-stu-id="90c07-192">With the \*\*Where these phrases occur setting, in this example you can configure your explanation to search for this label only in the beginning section of the document, or any other location in which it might occur.</span></span>

![Instelling Waar deze woordgroepen voorkomen](../media/content-understanding/phrase-location.png)

<span data-ttu-id="90c07-194">U kunt kiezen uit de volgende opties voor deze instelling:</span><span class="sxs-lookup"><span data-stu-id="90c07-194">You can choose the following options for this setting:</span></span>

- <span data-ttu-id="90c07-195">Overal in het bestand: in het hele document wordt naar de woordgroep gezocht.</span><span class="sxs-lookup"><span data-stu-id="90c07-195">Anywhere in the file: The entire document is searched for the phrase.</span></span>

- <span data-ttu-id="90c07-196">Begin van het bestand: het document wordt vanaf het begin tot aan de locatie van de woordgroep doorzocht.</span><span class="sxs-lookup"><span data-stu-id="90c07-196">Beginning of the file:  The document is searched from the beginning to the phrase location.</span></span>

   ![Begin van bestand](../media/content-understanding/beginning-of-file.png)

    <span data-ttu-id="90c07-198">In de viewer kunt u het selectievakje handmatig aanpassen zodat de locatie van de woordgroep wordt opgenomen.</span><span class="sxs-lookup"><span data-stu-id="90c07-198">In the viewer, you can manually adjust the select box to include the location where the phase occurs.</span></span> <span data-ttu-id="90c07-199">De waarde van **Eindpositie** wordt bijgewerkt om het aantal tokens weer te geven dat het geselecteerde gebied bevat.</span><span class="sxs-lookup"><span data-stu-id="90c07-199">The **End position** value will update to show the number of tokens your selected area includes.</span></span> <span data-ttu-id="90c07-200">U kunt de waarde van de Eindpositie ook bijwerken om het geselecteerde gebied aan te passen.</span><span class="sxs-lookup"><span data-stu-id="90c07-200">Note that you can update the End position value as well to adjust the selected area.</span></span>

   ![Vak Begin van bestandspositie](../media/content-understanding/beginning-box.png)

- <span data-ttu-id="90c07-202">Einde van het bestand: het document wordt vanaf het eind tot aan de locatie van de woordgroep doorzocht.</span><span class="sxs-lookup"><span data-stu-id="90c07-202">End of the file:  The document is searched from the end to the phrase location.</span></span>

   ![Einde van bestand](../media/content-understanding/end-of-file.png)

    <span data-ttu-id="90c07-204">In de viewer kunt u het selectievakje handmatig aanpassen zodat de locatie van de woordgroep wordt opgenomen.</span><span class="sxs-lookup"><span data-stu-id="90c07-204">In the viewer, you can manually adjust the select box to include the location where the phase occurs.</span></span> <span data-ttu-id="90c07-205">De waarde van **Beginpositie** wordt bijgewerkt om het aantal tokens weer te geven dat het geselecteerde gebied bevat.</span><span class="sxs-lookup"><span data-stu-id="90c07-205">The **Starting position** value will update to show the number of tokens your selected area includes.</span></span> <span data-ttu-id="90c07-206">U kunt de waarde van de Beginpositie ook bijwerken om het geselecteerde gebied aan te passen.</span><span class="sxs-lookup"><span data-stu-id="90c07-206">Note that you can update the Starting position value as well to adjust the selected area.</span></span>

   ![Vak Einde van bestand](../media/content-understanding/end-box.png)

- <span data-ttu-id="90c07-208">Aangepast bereik: in een bepaald bereik binnen het document wordt gezocht naar de locatie van de woordgroep.</span><span class="sxs-lookup"><span data-stu-id="90c07-208">Custom range:  The document is searched in a specified range within the it for the phrase location.</span></span>

   ![Aangepast bereik](../media/content-understanding/custom-file.png)

    <span data-ttu-id="90c07-210">In de viewer kunt u het selectievakje handmatig aanpassen zodat de locatie van de woordgroep wordt opgenomen.</span><span class="sxs-lookup"><span data-stu-id="90c07-210">In the viewer, you can manually adjust the select box to include the location where the phase occurs.</span></span> <span data-ttu-id="90c07-211">Voor deze instelling moet u een **Beginpositie** en een **Eindpositie** selecteren.</span><span class="sxs-lookup"><span data-stu-id="90c07-211">For this setting, you need to select a **Start** and an **End** position.</span></span> <span data-ttu-id="90c07-212">Deze waarden geven het aantal tokens aan vanaf het begin van het document.</span><span class="sxs-lookup"><span data-stu-id="90c07-212">These values represent the number of tokens from the begging of the document.</span></span> <span data-ttu-id="90c07-213">Hoewel u deze waarden handmatig kunt invoeren, is het eenvoudiger om het selectievakje handmatig aan te passen in de viewer.</span><span class="sxs-lookup"><span data-stu-id="90c07-213">While you can manually enter in these values, it is easier to manually adjust the select box in the viewer.</span></span> 
   
## <a name="use-explanation-templates"></a><span data-ttu-id="90c07-214">Uitlegsjablonen gebruiken</span><span class="sxs-lookup"><span data-stu-id="90c07-214">Use explanation templates</span></span>

<span data-ttu-id="90c07-215">Je kan handmatig verschillende frasenlijstwaarden toevoegen voor je uitleg, maar het kan eenvoudiger door sjablonen te gebruiken die aangeboden worden in de uitlegbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="90c07-215">While you can manually add various phrase list values for your explanation, it can be easier to use the templates provided to you in the explanation library.</span></span>

<span data-ttu-id="90c07-216">Je kunt bijvoorbeeld in plaats van alle variaties voor *Datum* handmatig toe te voegen, de frasenlijstsjabloon gebruiken voor *Datum*, die al een aantal frasenlijstwaarden bevat:</span><span class="sxs-lookup"><span data-stu-id="90c07-216">For example, instead of manually adding all the variations for *Date*, you can use the phrase list template for *Date* as it already includes a number of phrase lists values:</span></span>

![Uitlegbibliotheek](../media/content-understanding/explanation-template.png)
 
<span data-ttu-id="90c07-218&quot;>De uitlegbibliotheek bevat een aantal veelgebruikte beschrijvingen van de frasenlijst, waaronder:</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;90c07-218&quot;>The explanation library includes commonly used phrase list explanations, including:</span></span>

- <span data-ttu-id=&quot;90c07-219&quot;>Datum: Kalenderdatums, alle notaties.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;90c07-219&quot;>Date: Calendar dates, all formats.</span></span> <span data-ttu-id=&quot;90c07-220&quot;>Bevat tekst en getallen (bijvoorbeeld &quot;9 dec, 2020").</span><span class="sxs-lookup"><span data-stu-id="90c07-220">Includes text and numbers (for example, "Dec 9, 2020").</span></span>
- <span data-ttu-id="90c07-221">Datum (numeriek): Kalenderdatums, alle notaties.</span><span class="sxs-lookup"><span data-stu-id="90c07-221">Date (numeric): Calendar dates, all formats.</span></span> <span data-ttu-id="90c07-222">Bevat getallen (bijvoorbeeld 1-11-2020).</span><span class="sxs-lookup"><span data-stu-id="90c07-222">Includes numbers (for example 1-11-2020).</span></span>
- <span data-ttu-id="90c07-223">Tijd: 12- en 24-uurs tijdnotatie.</span><span class="sxs-lookup"><span data-stu-id="90c07-223">Time: 12 and 24 hour formats.</span></span>
- <span data-ttu-id="90c07-224">Getal: Positieve en negatieve getallen tot maximaal 2 decimalen.</span><span class="sxs-lookup"><span data-stu-id="90c07-224">Number: Positive and negative numbers up to 2 decimals.</span></span> 
- <span data-ttu-id="90c07-225">Percentage: een lijst met patronen die een percentage vertegenwoordigen.</span><span class="sxs-lookup"><span data-stu-id="90c07-225">Percentage: A list of patterns representing a percentage.</span></span> <span data-ttu-id="90c07-226">Bijvoorbeeld, 1%, 11%, 100%, 11.11%, enz.</span><span class="sxs-lookup"><span data-stu-id="90c07-226">For example, 1%, 11%, 100%, 11.11%, etc.</span></span>
- <span data-ttu-id="90c07-227">Telefoonnummer: veelgebruikte Amerikaanse en internationale notaties.</span><span class="sxs-lookup"><span data-stu-id="90c07-227">Phone number: Common US and International formats.</span></span> <span data-ttu-id="90c07-228">Bijvoorbeeld, 000 000 0000, 000-000-0000, (000)000-0000, (000) 000-0000, enz.</span><span class="sxs-lookup"><span data-stu-id="90c07-228">For example, 000 000 0000, 000-000-0000, (000)000-0000, (000) 000-0000, etc.</span></span>
- <span data-ttu-id="90c07-229">Postcode: Amerikaanse postcode-indelingen.</span><span class="sxs-lookup"><span data-stu-id="90c07-229">Zip code: US Zip code formats.</span></span> <span data-ttu-id="90c07-230">Bijvoorbeeld, 11111, 11111-1111.</span><span class="sxs-lookup"><span data-stu-id="90c07-230">For example, 11111, 11111-1111.</span></span>
- <span data-ttu-id="90c07-231">Eerste woord van zin: algemene patronen voor woorden met maximaal negen tekens.</span><span class="sxs-lookup"><span data-stu-id="90c07-231">First word of sentence: Common patterns for words up to 9 characters.</span></span> 
- <span data-ttu-id="90c07-232">Einde van zin: veelvoorkomende interpunctie voor het einde van een zin</span><span class="sxs-lookup"><span data-stu-id="90c07-232">End of sentence: Common punctuation for end of a sentence</span></span>
- <span data-ttu-id="90c07-233">Creditcard: veelgebruikte notaties voor creditcards.</span><span class="sxs-lookup"><span data-stu-id="90c07-233">Credit card: Common credit card number formats.</span></span> <span data-ttu-id="90c07-234">Bijvoorbeeld, 1111-1111-1111-1111.</span><span class="sxs-lookup"><span data-stu-id="90c07-234">For example, 1111-1111-1111-1111.</span></span> 
- <span data-ttu-id="90c07-235">Sofinummer: Amerikaanse notatie voor het sofinummer.</span><span class="sxs-lookup"><span data-stu-id="90c07-235">Social security number: US Social Security Number format.</span></span> <span data-ttu-id="90c07-236">Bijvoorbeeld, 111-11-1111.</span><span class="sxs-lookup"><span data-stu-id="90c07-236">For example, 111-11-1111.</span></span> 
- <span data-ttu-id="90c07-237">Selectievakje: een frasenlijst die variaties op een opgevuld selectievakje vertegenwoordigt.</span><span class="sxs-lookup"><span data-stu-id="90c07-237">Checkbox: A phrase list representing variations on a filled in checkbox.</span></span> <span data-ttu-id="90c07-238">Bijvoorbeeld, _X_, _ _X_, enz.</span><span class="sxs-lookup"><span data-stu-id="90c07-238">For example, _X_, _ _X_, etc.</span></span>
- <span data-ttu-id="90c07-239">Valuta: Belangrijke internationale symbolen.</span><span class="sxs-lookup"><span data-stu-id="90c07-239">Currency: Major international symbols.</span></span> <span data-ttu-id="90c07-240">Bijvoorbeeld, $.</span><span class="sxs-lookup"><span data-stu-id="90c07-240">For example, $.</span></span> 
- <span data-ttu-id="90c07-241">E-mail CC: Een frasenlijst met de term 'CC:', vaak gevonden in de buurt van de namen of e-mailadressen van extra personen of groepen waar het bericht naar is verzonden.</span><span class="sxs-lookup"><span data-stu-id="90c07-241">Email CC: A phrase list with the term 'CC:', often found near the names or email addresses of additional people or groups the message was sent to.</span></span>
- <span data-ttu-id="90c07-242">E-maildatum: Een frasenlijst met de term 'Verzonden op:', vaak gevonden bij de datum waarop het e-mailbericht is verzonden.</span><span class="sxs-lookup"><span data-stu-id="90c07-242">Email date: A phrase list with the term 'Sent on:', often found near the date the email was sent.</span></span>
- <span data-ttu-id="90c07-243">E-mail begroeting: Algemene beginregels voor e-mailberichten.</span><span class="sxs-lookup"><span data-stu-id="90c07-243">Email greeting: Common opening lines for emails.</span></span>
- <span data-ttu-id="90c07-244">E-mail ontvanger: Een frasenlijst met de term 'Aan:', vaak gevonden in de buurt van de namen of e-mailadressen van personen of groepen waar het bericht naar is verzonden.</span><span class="sxs-lookup"><span data-stu-id="90c07-244">Email recipient: A phrase list with the term 'To:', often found near the names or email addresses of people or groups the message was sent to.</span></span> 
- <span data-ttu-id="90c07-245">E-mail afzender: Een frasenlijst met de term 'Van:', vaak gevonden in de buurt van de naam of het e-mailadres van de afzender.</span><span class="sxs-lookup"><span data-stu-id="90c07-245">Email sender: A phrase list with the term 'From:', often found near the sender's name or email address.</span></span> 
- <span data-ttu-id="90c07-246">E-mail onderwerp: Een frasenlijst met de term 'Onderwerp:', vaak gevonden in de buurt van het e-mail onderwerp.</span><span class="sxs-lookup"><span data-stu-id="90c07-246">Email subject: A phrase list with the term 'Subject:', often found near the email's subject.</span></span> 

<span data-ttu-id="90c07-247">De uitlegbibliotheek bevat ook drie automatische sjabloontypen die binnen de gegevens werken die je gelabeld hebt in je voorbeeldbestanden:</span><span class="sxs-lookup"><span data-stu-id="90c07-247">The explanation library also includes three automatic template types that work with the data you've labeled in your example files:</span></span>

- <span data-ttu-id="90c07-248">After-label: De woorden of karakters die voorkomen na de labels in de voorbeeldbestanden.</span><span class="sxs-lookup"><span data-stu-id="90c07-248">After label: The words or characters that occur after the labels in the example files.</span></span>
- <span data-ttu-id="90c07-249">Before-label: De woorden of karakters die voorkomen voor de labels in de voorbeeldbestanden.</span><span class="sxs-lookup"><span data-stu-id="90c07-249">Before label: The words or characters that occur before the labels in the example files.</span></span>
- <span data-ttu-id="90c07-250">Labels: Tot maximaal de eerste 10 karakters van de voorbeeldbestanden.</span><span class="sxs-lookup"><span data-stu-id="90c07-250">Labels: Up to the first 10 labels from the example files.</span></span>

<span data-ttu-id="90c07-251">Automatische sjablonen werken bijvoorbeeld zoals in het volgende voorbeeldbestand waar we de before-label-uitlegsjabloon gebruiken om het model meer informatie te geven zodat we tot een nauwkeurigere overeenkomst komen.</span><span class="sxs-lookup"><span data-stu-id="90c07-251">To give you an example of how automatic templates work, in the following example file, we will use the Before Label explanation template to help give the model more information to get a more accurate match.</span></span>

![Voorbeeldbestand](../media/content-understanding/before-label.png)

<span data-ttu-id="90c07-253">Als je het before-label-uitlegsjabloon selecteert, zoekt het de eerste groep woorden die voorkomen vóór het label in je voorbeeldbestanden.</span><span class="sxs-lookup"><span data-stu-id="90c07-253">When you select the Before Label explanation template, it will look for the first set of words that appear before the label in your example files.</span></span> <span data-ttu-id="90c07-254">In het voorbeeld is het woord dat geïdentificeerd werd ‘Vanaf’.</span><span class="sxs-lookup"><span data-stu-id="90c07-254">In the example, the words that are identified in the first example file is "As of".</span></span>

![Before-labelsjabloon](../media/content-understanding/before-label-explanation.png)

<span data-ttu-id="90c07-256">Je kan een uitleg voor een sjabloon maken door **Toevoegen** te selecteren.</span><span class="sxs-lookup"><span data-stu-id="90c07-256">You can select **Add** to create an explanation from the template.</span></span>  <span data-ttu-id="90c07-257">Aanvullende woorden worden geïdentificeerd en toegevoegd aan de frasenlijst naargelang je meer voorbeeldbestanden toevoegt.</span><span class="sxs-lookup"><span data-stu-id="90c07-257">As you add more example files, additional words will be identified and added to the phrase list.</span></span>

![Het label toevoegen](../media/content-understanding/before-label-add.png)
 
#### <a name="to-use-a-template-from-the-explanation-library"></a><span data-ttu-id="90c07-259">Een sjabloon gebruiken uit de uitlegbibliotheek</span><span class="sxs-lookup"><span data-stu-id="90c07-259">To use a template from the explanation library</span></span>

1. <span data-ttu-id="90c07-260">Ga naar het gedeelte **Uitleg** van de **Train**-pagina van je model en selecteer **Nieuwe** en selecteer vervolgens **Van een sjabloon**.</span><span class="sxs-lookup"><span data-stu-id="90c07-260">From the **Explanations** section of your model's **Train** page, select **New**, then select **From a template**.</span></span>

   ![Before-label toevoegen](../media/content-understanding/from-template.png)

2.  <span data-ttu-id="90c07-262">Selecteer op de pagina **Uitlegsjablonen** de uitleg die je wilt gebruiken en selecteer vervolgens **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="90c07-262">On the **Explanation templates** page, select the explanation you want to use, then select **Add**.</span></span>

    ![Selecteer een sjabloon](../media/content-understanding/phone-template.png)

3. <span data-ttu-id="90c07-264">De informatie voor de sjabloon die je hebt geselecteerd, wordt weergegeven op de pagina **Een uitleg maken**.</span><span class="sxs-lookup"><span data-stu-id="90c07-264">The information for the template you selected displays on the **Create an explanation** page.</span></span> <span data-ttu-id="90c07-265">Bewerk zo nodig de naam van de uitleg en voeg items toe of verwijder items uit de frasenlijst.</span><span class="sxs-lookup"><span data-stu-id="90c07-265">If needed, edit the explanation name and add or remove items from the phrase list.</span></span>  

    ![Sjabloon bewerken](../media/content-understanding/phone-template-live.png)

4. <span data-ttu-id="90c07-267">Selecteer **Opslaan** wanneer je klaar bent.</span><span class="sxs-lookup"><span data-stu-id="90c07-267">When finished, select **Save**.</span></span>