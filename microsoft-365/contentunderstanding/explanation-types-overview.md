---
title: Uitlegtypen in Microsoft SharePoint Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Meer informatie over uitlegtypen in Microsoft SharePoint Syntex.
ms.openlocfilehash: 515fd8af289ec7c64e14eb6d54b236ba3a8aa9f6
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706559"
---
# <a name="explanation-types-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="46aec-103">Uitlegtypen in Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="46aec-103">Explanation types in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="46aec-104">Uitleg wordt gebruikt om de gegevens te definiëren die je wilt labelen en ophalen in je documentinformatie over modellen in Microsoft SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="46aec-104">Explanations are used to help to define the information you want to label and extract in your document understanding models in Microsoft SharePoint Syntex.</span></span> <span data-ttu-id="46aec-105">Bij het maken van een uitleg moet je een uitlegtype selecteren.</span><span class="sxs-lookup"><span data-stu-id="46aec-105">When you create an explanation, you need to select an explanation type.</span></span> <span data-ttu-id="46aec-106">In dit artikel vind je meer informatie over de verschillende uitlegtypen en hoe je deze kunt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="46aec-106">This article helps you understand the different explanation types and how they're used.</span></span>

![Schermafbeelding van het deelvenster Een uitleg maken met de drie typen uitleg.](../media/content-understanding/explanation-types.png) 
   
<span data-ttu-id="46aec-108">Deze uitlegtypen zijn beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="46aec-108">These explanation types are available:</span></span>

- <span data-ttu-id="46aec-109">[**Patroonlijst**](#phrase-list): lijst met woorden, woordgroepen, cijfers of andere tekens die u kunt gebruiken in het document of de informatie die u uit het document haalt.</span><span class="sxs-lookup"><span data-stu-id="46aec-109">[**Phrase list**](#phrase-list): List of words, phrases, numbers, or other characters you can use in the document or information that you're extracting.</span></span> <span data-ttu-id="46aec-110">De tekststring *verwijzende arts* staat bijvoorbeeld in alle medische verwijzingsdocumenten die u identificeert.</span><span class="sxs-lookup"><span data-stu-id="46aec-110">For example, the text string *referring doctor* is in all Medical Referral documents you're identifying.</span></span> <span data-ttu-id="46aec-111">Of het *telefoonnummer* van de verwijzende arts uit alle medische verwijzingsdocumenten die u identificeert.</span><span class="sxs-lookup"><span data-stu-id="46aec-111">Or the *phone number* of the referring doctor from all Medical Referral documents that you're identifying.</span></span>

- <span data-ttu-id="46aec-112">[**Reguliere expressie**](#regular-expression): in een reguliere expressie wordt een notatie gebruikt om patronen te matchen en zo specifieke tekenpatronen te vinden.</span><span class="sxs-lookup"><span data-stu-id="46aec-112">[**Regular expression**](#regular-expression): Uses a pattern-matching notation to find specific character patterns.</span></span> <span data-ttu-id="46aec-113">U kunt bijvoorbeeld een reguliere expressie gebruiken om alle instanties van een *e-mailadres* patroon in een verzameling documenten te zoeken.</span><span class="sxs-lookup"><span data-stu-id="46aec-113">For example, you can use a regular expression to find all instances of an *email address* pattern in a set of documents.</span></span>

- <span data-ttu-id="46aec-114">[**Nabijheid**](#proximity): beschrijft hoe nauw de verklaringen bij elkaar liggen.</span><span class="sxs-lookup"><span data-stu-id="46aec-114">[**Proximity**](#proximity): Describes how close explanations are to each other.</span></span> <span data-ttu-id="46aec-115">Een lijst met *straatnummers* staat bijvoorbeeld vlak voor de lijst met *straatnamen*, zonder tokens ertussen (verderop in dit artikel vindt u meer informatie over tokens).</span><span class="sxs-lookup"><span data-stu-id="46aec-115">For example, a *street number* phrase list goes right before the *street name* phrase list, with no tokens in between (you'll learn about tokens later in this article).</span></span> <span data-ttu-id="46aec-116">Voor het type proximity moet je ten minste twee uitleggen in je model hebben, of de optie wordt uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="46aec-116">Using the proximity type requires you to have at least two explanations in your model or the option will be disabled.</span></span> 

## <a name="phrase-list"></a><span data-ttu-id="46aec-117">Woordenlijst</span><span class="sxs-lookup"><span data-stu-id="46aec-117">Phrase list</span></span>

<span data-ttu-id="46aec-118">Het uitlegtype van een woordenlijst wordt meestal gebruikt om een document te identificeren en te classificeren via je model.</span><span class="sxs-lookup"><span data-stu-id="46aec-118">A phrase list explanation type is typically used to identify and classify a document through your model.</span></span> <span data-ttu-id="46aec-119">Zoals beschreven in het voorbeeld van het label *verwijzende arts*, is het een reeks woorden, woordgroepen, cijfers of tekens die consistent in de documenten staat die u identificeert.</span><span class="sxs-lookup"><span data-stu-id="46aec-119">As described in the *referring doctor* label example, it's a string of words, phrases, numbers, or characters that is consistently in the documents that you're identifying.</span></span>

<span data-ttu-id="46aec-120">Hoewel dit geen vereiste is, kunt u meer succes behalen met uw uitleg als het patroon dat u vastlegt zich op een consistente locatie in uw document bevindt.</span><span class="sxs-lookup"><span data-stu-id="46aec-120">While not a requirement, you can achieve better success with your explanation if the phrase you're capturing is located in a consistent location in your document.</span></span> <span data-ttu-id="46aec-121">Het label *verwijzende arts* kan bijvoorbeeld consequent in de eerste alinea van het document staan.</span><span class="sxs-lookup"><span data-stu-id="46aec-121">For example, the *referring doctor* label might be consistently located in the first paragraph of the document.</span></span> <span data-ttu-id="46aec-122">U kunt ook de optie **[Configureren waar zinnen voorkomen in het document](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#configure-where-phrases-occur-in-the-document)** in de geavanceerde instellingen gebruiken om specifieke gebieden te selecteren waar de zin zich bevindt, vooral als de kans bestaat dat het patroon op meerdere locaties in uw document voorkomt.</span><span class="sxs-lookup"><span data-stu-id="46aec-122">You can also use the **[Configure where phrases occur in the document](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#configure-where-phrases-occur-in-the-document)** advanced setting to select specific areas where the phrase is located, especially if there's a chance that the phrase might occur in multiple locations in your document.</span></span>

<span data-ttu-id="46aec-123">Als hoofdlettergevoeligheid een vereiste is bij het identificeren van je label, kun je met het woordenlijsttype in uw uitleg opgeven door het selectievakje **Alleen exacte kapitalisatie** in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="46aec-123">If case sensitivity is a requirement in identifying your label, using the phrase list type allows you to specify it in your explanation by selecting the **Only exact capitalization** checkbox.</span></span>

![Onderscheid tussen hoofdletters en kleine letters](../media/content-understanding/case-sensitivity.png) 

<span data-ttu-id="46aec-125">Een patroonlijst is vooral handig wanneer u een uitleg maakt die informatie in verschillende indelingen identificeert en extraheert, zoals datums, telefoonnummers en creditcardnummers.</span><span class="sxs-lookup"><span data-stu-id="46aec-125">A phrase type is especially useful when you create an explanation that identifies and extracts information in different formats, such as dates, phone numbers, and credit card numbers.</span></span> <span data-ttu-id="46aec-126">Een datum kan bijvoorbeeld in veel verschillende formaten worden weergegeven (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, 1 januari 2020, enzovoort).</span><span class="sxs-lookup"><span data-stu-id="46aec-126">For example, a date can be displayed in many different formats (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, or Jan 1,2020).</span></span> <span data-ttu-id="46aec-127">Door een patroonlijst te definiëren, kunt u efficiënter identificeren door eventuele variaties in de gegevens vast te leggen die u probeert vast te stellen en op te halen.</span><span class="sxs-lookup"><span data-stu-id="46aec-127">Defining a phrase list makes your explanation more efficient by capturing any possible variations in the data that you're trying to identify and extract.</span></span> 

<span data-ttu-id="46aec-128">Voor het voorbeeld *Telefoonnummer* haalt u het telefoonnummer voor elke verwijzende arts op uit alle Medische Verwijzingsdocumenten die door het model worden geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="46aec-128">For the *phone number* example, you extract the phone number for each referring doctor from all Medical Referral documents that the model identifies.</span></span> <span data-ttu-id="46aec-129">Wanneer u de uitleg maakt, typt u de verschillende notaties die een telefoonnummer in uw document kan weergeven, zodat u mogelijke variaties kunt vastleggen.</span><span class="sxs-lookup"><span data-stu-id="46aec-129">When you create the explanation, type the different formats a phone number might display in your document so that you're able to capture possible variations.</span></span> 

![Patroonlijst met telefoonnummers](../media/content-understanding/pattern-list.png)

<span data-ttu-id="46aec-131">Schakel voor dit voorbeeld in **Geavanceerde instellingen** het selectievakje **Elk cijfer van 0-9** in om elke '0'-waarde die in uw lijst met zinnen wordt gebruikt, te herkennen als een cijfer van 0 tot en met 9.</span><span class="sxs-lookup"><span data-stu-id="46aec-131">For this example, in **Advanced Settings** select the **Any digit from 0-9** checkbox to recognize each "0" value used in your phrase list to be any digit from 0 through 9.</span></span>

![Een willekeurig cijfer van 0-9](../media/content-understanding/digit-identity.png)

<span data-ttu-id="46aec-133">Als u een patroonlijst maakt die teksttekens bevat, selecteert u het selectievakje **Willekeurige letter van a-z** om aan te geven dat elk 'a'-teken dat in de patroonlijst wordt gebruikt, elk teken van 'a' tot 'z' kan zijn.</span><span class="sxs-lookup"><span data-stu-id="46aec-133">Similarly, if you create a phrase list that includes text characters, select the **Any letter from a-z** checkbox to recognize each "a" character used in the phrase list to be any character from "a" to "z".</span></span>

<span data-ttu-id="46aec-134">Als u bijvoorbeeld een patroonlijst **Datum** maakt en u ervoor wilt zorgen dat een datumnotatie wordt ondersteund zoals *1 januari 2020*, moet u het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="46aec-134">For example, if you create a **Date** phrase list and you want to make sure that a date format such as *Jan 1, 2020* is recognized, you need to:</span></span>

- <span data-ttu-id="46aec-135">Voeg *0 AAA 0000* en *00 AAA 0000* aan de patroonlijst toe.</span><span class="sxs-lookup"><span data-stu-id="46aec-135">Add *aaa 0, 0000* and *aaa 00, 0000* to your phrase list.</span></span>
- <span data-ttu-id="46aec-136">Zorg ervoor dat **Een willekeurige letter van a-z** is geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="46aec-136">Make sure that **Any letter from a-z** is also selected.</span></span>

![Een letter van a-z](../media/content-understanding/any-letter.png)

<span data-ttu-id="46aec-138">Als je hoofdlettereisen in je patroonlijst hebt, kun je ook het selectievakje **Alleen exact hoofdlettergebruik** selecteren.</span><span class="sxs-lookup"><span data-stu-id="46aec-138">If you have capitalization requirements in your phrase list, you can select the **Only exact capitalization** checkbox.</span></span> <span data-ttu-id="46aec-139">Als u voor het datumvoorbeeld wilt dat de eerste letter van de maand met een hoofdletter wordt geschreven, moet u:</span><span class="sxs-lookup"><span data-stu-id="46aec-139">For the date example, if you require the first letter of the month to be capitalized, you need to:</span></span>

- <span data-ttu-id="46aec-140">Voeg *0 Aaa 0000* en *00 AAA 0000* aan de patroonlijst toe.</span><span class="sxs-lookup"><span data-stu-id="46aec-140">Add *Aaa 0, 0000* and *Aaa 00, 0000* to your phrase list.</span></span>
- <span data-ttu-id="46aec-141">Zorg ervoor dat **Alleen exact hoofdlettergebruik** ook is geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="46aec-141">Make sure that **Only exact capitalization** is also selected.</span></span>

![Alleen exact hoofdlettergebruik](../media/content-understanding/exact-caps.png)

> [!NOTE]
> <span data-ttu-id="46aec-143">Gebruik in plaats van het handmatig maken van een uitleg voor patroonlijsten de [uitlegbibliotheek](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-explanation-templates) voor het gebruik van vooraf gemaakte patroonlijstsjablonen voor een algemene patroonlijst, zoals *datum*, *telefoonnummer*, *creditcardnummer*, enzovoort.</span><span class="sxs-lookup"><span data-stu-id="46aec-143">Instead of manually creating a phrase list explanation, use the [explanation library](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-explanation-templates) to use phrase list templates for a common phrase list, such as *date*, *phone number*, or *credit card number*.</span></span>

## <a name="regular-expression"></a><span data-ttu-id="46aec-144">Reguliere expressie</span><span class="sxs-lookup"><span data-stu-id="46aec-144">Regular expression</span></span>

<span data-ttu-id="46aec-145">Met behulp van een reguliere uitlegtype voor expressies kunt u patronen maken om bepaalde tekenreeksen in documenten te zoeken en te identificeren.</span><span class="sxs-lookup"><span data-stu-id="46aec-145">A regular expression explanation type allows you to create patterns that help find and identify certain text strings in documents.</span></span> <span data-ttu-id="46aec-146">U kunt reguliere expressies gebruiken om snel grote hoeveelheden tekst te parseren om:</span><span class="sxs-lookup"><span data-stu-id="46aec-146">You can use regular expressions to quickly parse large amounts of text to:</span></span>

- <span data-ttu-id="46aec-147">Specifieke tekenpatronen te zoeken.</span><span class="sxs-lookup"><span data-stu-id="46aec-147">Find specific character patterns.</span></span>
- <span data-ttu-id="46aec-148">Tekst te valideren om ervoor te zorgen dat deze overeenkomt met een vooraf gedefinieerd patroon (zoals een e-mailadres).</span><span class="sxs-lookup"><span data-stu-id="46aec-148">Validate text to ensure that it matches a predefined pattern (such as an email address).</span></span>
- <span data-ttu-id="46aec-149">Tekstsubtekenreeksen te extraheren, bewerken, vervangen of verwijderen.</span><span class="sxs-lookup"><span data-stu-id="46aec-149">Extract, edit, replace, or delete text substrings.</span></span>

<span data-ttu-id="46aec-150">Een type reguliere expressie is vooral handig wanneer u een uitleg maakt die informatie in vergelijkbare indelingen identificeert en extraheert, zoals e-mailadressen, bankrekeningnummers of URL's.</span><span class="sxs-lookup"><span data-stu-id="46aec-150">A regular expression type is especially useful when you create an explanation that identifies and extracts information in similar formats, such as email addresses, bank account numbers, or URLs.</span></span> <span data-ttu-id="46aec-151">Een e-mailadres, zoals megan@contoso.com, wordt bijvoorbeeld met een bepaald patroon weergegeven ('megan' is het eerste deel en 'com' is het laatste deel).</span><span class="sxs-lookup"><span data-stu-id="46aec-151">For example, an email address, such as megan@contoso.com, is displayed in a certain pattern ("megan" is the first part, and "com" is the last part).</span></span> 

<span data-ttu-id="46aec-152">De reguliere expressie voor een e-mailadres is: **[A-Za-z0-9._%-]+@[A-Za-z0-9.-]+. [A-Za-z]{2,6}**.</span><span class="sxs-lookup"><span data-stu-id="46aec-152">The regular expression for an email address is: **[A-Za-z0-9._%-]+@[A-Za-z0-9.-]+.[A-Za-z]{2,6}**.</span></span>

<span data-ttu-id="46aec-153">Deze expressie bestaat uit vijf delen, in deze volgorde:</span><span class="sxs-lookup"><span data-stu-id="46aec-153">This expression consists of five parts, in this order:</span></span>

1. <span data-ttu-id="46aec-154">Een of meer van de volgende tekens:</span><span class="sxs-lookup"><span data-stu-id="46aec-154">Any amount of the following characters:</span></span>

   <span data-ttu-id="46aec-155">a.</span><span class="sxs-lookup"><span data-stu-id="46aec-155">a.</span></span> <span data-ttu-id="46aec-156">Letters van a tot z</span><span class="sxs-lookup"><span data-stu-id="46aec-156">Letters from a to z</span></span>

   <span data-ttu-id="46aec-157">b.</span><span class="sxs-lookup"><span data-stu-id="46aec-157">b.</span></span> <span data-ttu-id="46aec-158">Getal tussen 0 en 9</span><span class="sxs-lookup"><span data-stu-id="46aec-158">Numbers from 0-9</span></span>

   <span data-ttu-id="46aec-159">c.</span><span class="sxs-lookup"><span data-stu-id="46aec-159">c.</span></span> <span data-ttu-id="46aec-160">Punt, onderstrepingsteken, percentage of streepje</span><span class="sxs-lookup"><span data-stu-id="46aec-160">Period, underscore, percent, or dash</span></span>

2. <span data-ttu-id="46aec-161">Het @-symbool</span><span class="sxs-lookup"><span data-stu-id="46aec-161">The @ symbol</span></span>

3. <span data-ttu-id="46aec-162">Elk aantal van hetzelfde soort tekens als het eerste deel van het e-mailadres</span><span class="sxs-lookup"><span data-stu-id="46aec-162">Any amount of the same characters as the first part of the email address</span></span>

4. <span data-ttu-id="46aec-163">Een punt</span><span class="sxs-lookup"><span data-stu-id="46aec-163">A period</span></span>

5. <span data-ttu-id="46aec-164">Twee tot zes letters</span><span class="sxs-lookup"><span data-stu-id="46aec-164">Two to six letters</span></span>

<span data-ttu-id="46aec-165">Een uitlegtype voor een reguliere expressie toevoegen:</span><span class="sxs-lookup"><span data-stu-id="46aec-165">To add a regular expression explanation type:</span></span>

1. <span data-ttu-id="46aec-166">Selecteer **Reguliere expressie** in het deelvenster **Een uitleg maken** onder **Type uitleg**.</span><span class="sxs-lookup"><span data-stu-id="46aec-166">From the **Create an explanation** panel, under **Explanation type**, select **Regular expression**.</span></span>

   ![Schermafbeelding van het deelvenster Een uitleg maken waarin Reguliere expressie is geselecteerd.](../media/content-understanding/create-regular-expression.png)

2. <span data-ttu-id="46aec-168">U kunt een uitdrukking typen in het tekstvak **Reguliere expressie** of **Een reguliere uitdrukking uit een sjabloon toevoegen** selecteren.</span><span class="sxs-lookup"><span data-stu-id="46aec-168">You can either type an expression in the **Regular expression** text box or select **Add a regular expression from a template**.</span></span>

   <span data-ttu-id="46aec-169">Wanneer u een reguliere expressie toevoegt met behulp van een sjabloon, worden de naam en de reguliere expressie automatisch toegevoegd aan het tekstvak.</span><span class="sxs-lookup"><span data-stu-id="46aec-169">When you add a regular expression by using a template, it automatically adds the name and the regular expression to the text box.</span></span> <span data-ttu-id="46aec-170">Als u bijvoorbeeld de sjabloon **E-mailadres** kiest, wordt het paneel **Een uitleg maken** ingevuld.</span><span class="sxs-lookup"><span data-stu-id="46aec-170">For example, if you choose the **Email address** template, the **Create an explanation** panel will be populated.</span></span>

   ![Schermafbeelding van het deelvenster Een uitleg maken waarop de sjabloon E-mailadres is toegepast.](../media/content-understanding/create-regular-expression-email.png)

## <a name="proximity"></a><span data-ttu-id="46aec-172">Proximity</span><span class="sxs-lookup"><span data-stu-id="46aec-172">Proximity</span></span> 

<span data-ttu-id="46aec-173">Met het Proximity-uitlegtype kan je model identificeren met behulp van hoe dichtbij een ander stukje gegevens is.</span><span class="sxs-lookup"><span data-stu-id="46aec-173">The proximity explanation type helps your model identify data by defining how close another piece of data is to it.</span></span> <span data-ttu-id="46aec-174">Stel dat u in uw model twee verklaringen hebt gedefinieerd die zowel het *huisnummer* van de klant als het *telefoonnummer* van een label voorzien.</span><span class="sxs-lookup"><span data-stu-id="46aec-174">For example, in your model say you have defined two explanations that label both the customer *street address number* and *phone number*.</span></span> 

<span data-ttu-id="46aec-175">Je ziet ook dat de telefoonnummers van klanten altijd voor het huisnummer worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="46aec-175">Notice that customer phone numbers always appear before the street address number.</span></span> 

<span data-ttu-id="46aec-176">Alex Wilburn</span><span class="sxs-lookup"><span data-stu-id="46aec-176">Alex Wilburn</span></span><br>
<span data-ttu-id="46aec-177">555-555-5555</span><span class="sxs-lookup"><span data-stu-id="46aec-177">555-555-5555</span></span><br>
<span data-ttu-id="46aec-178">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="46aec-178">One Microsoft Way</span></span><br>
<span data-ttu-id="46aec-179">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="46aec-179">Redmond, WA 98034</span></span><br>

<span data-ttu-id="46aec-180">Gebruik de proximity-uitleg om te bepalen hoe ver de uitleg van een telefoonnummer is zodat u het huisnummer in je documenten beter kunt identificeren.</span><span class="sxs-lookup"><span data-stu-id="46aec-180">Use the proximity explanation to define how far away the phone number explanation is to better identify the street address number in your documents.</span></span>

![Proximity-uitleg](../media/content-understanding/proximity.png)

#### <a name="what-are-tokens"></a><span data-ttu-id="46aec-182">Wat zijn tokens?</span><span class="sxs-lookup"><span data-stu-id="46aec-182">What are tokens?</span></span>

<span data-ttu-id="46aec-183">Om het uitlegtype nabijheid te gebruiken, moet u weten wat een token is.</span><span class="sxs-lookup"><span data-stu-id="46aec-183">To use the proximity explanation type, you need to understand what a token is.</span></span> <span data-ttu-id="46aec-184">Het aantal tokens is de manier waarop de nabijheidsverklaring de afstand van de ene uitleg tot de andere meet.</span><span class="sxs-lookup"><span data-stu-id="46aec-184">The number of tokens is how the proximity explanation measures distance from one explanation to another.</span></span> <span data-ttu-id="46aec-185">Een token is een doorlopende reeks (geen spaties of interpunctie) van letters en cijfers.</span><span class="sxs-lookup"><span data-stu-id="46aec-185">A token is a continuous span (not including spaces or punctuation) of letters and numbers.</span></span> 

<span data-ttu-id="46aec-186">In de volgende tabel zie je enkele voorbeelden van hoe je het aantal tokens in een woordgroep kunt vaststellen.</span><span class="sxs-lookup"><span data-stu-id="46aec-186">The following table shows examples for how to determine the number of tokens in a phrase.</span></span>

|<span data-ttu-id="46aec-187">Woordengroep</span><span class="sxs-lookup"><span data-stu-id="46aec-187">Phrase</span></span>|<span data-ttu-id="46aec-188">Aantal tokens</span><span class="sxs-lookup"><span data-stu-id="46aec-188">Number of tokens</span></span>|<span data-ttu-id="46aec-189">Uitleg</span><span class="sxs-lookup"><span data-stu-id="46aec-189">Explanation</span></span>|
|--|--|--|
|`Dog`|<span data-ttu-id="46aec-190">1</span><span class="sxs-lookup"><span data-stu-id="46aec-190">1</span></span>|<span data-ttu-id="46aec-191">Eén woord zonder leesteken of spatie.</span><span class="sxs-lookup"><span data-stu-id="46aec-191">A single word with no punctuation or spaces.</span></span>|
|`RMT33W`|<span data-ttu-id="46aec-192">1</span><span class="sxs-lookup"><span data-stu-id="46aec-192">1</span></span>|<span data-ttu-id="46aec-193">Een record locatornummer.</span><span class="sxs-lookup"><span data-stu-id="46aec-193">A record locator number.</span></span> <span data-ttu-id="46aec-194">Het mag cijfers en letters bevatten, maar geen leestekens.</span><span class="sxs-lookup"><span data-stu-id="46aec-194">It might include numbers and letters, but doesn't have punctuation.</span></span>|
|`425-555-5555`|<span data-ttu-id="46aec-195">5</span><span class="sxs-lookup"><span data-stu-id="46aec-195">5</span></span>|<span data-ttu-id="46aec-196">Een telefoonnummer.</span><span class="sxs-lookup"><span data-stu-id="46aec-196">A phone number.</span></span> <span data-ttu-id="46aec-197">Elk leesteken bestaat uit één token, zodat `425-555-5555` 5 tokens zou zijn:</span><span class="sxs-lookup"><span data-stu-id="46aec-197">Each punctuation mark is a single token, so `425-555-5555` is 5 tokens:</span></span><br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|<span data-ttu-id="46aec-198">7</span><span class="sxs-lookup"><span data-stu-id="46aec-198">7</span></span>|`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a><span data-ttu-id="46aec-199">Het proximity-uitlegtype configureren</span><span class="sxs-lookup"><span data-stu-id="46aec-199">Configure the proximity explanation type</span></span>

<span data-ttu-id="46aec-200">Voor het voorbeeld configureert u de nabijheidsinstelling zodanig dat u het aantal tokens kunt definiëren in de *telefoonnummer*-uitleg afkomstig van de *huisnummer*-uitleg.</span><span class="sxs-lookup"><span data-stu-id="46aec-200">For the example, configure the proximity setting to define the range of the number of tokens in the *phone number* explanation from the *street address number* explanation.</span></span> <span data-ttu-id="46aec-201">Je ziet dat het minimumbereik “0“ is omdat er geen tokens zijn tussen het telefoonnummer en het huisnummer.</span><span class="sxs-lookup"><span data-stu-id="46aec-201">Notice that the minimum range is "0", because there are no tokens between the phone number and street address number.</span></span>

<span data-ttu-id="46aec-202">Sommige telefoonnummers in de voorbeelddocumenten worden echter toegevoegd met *(mobiel)*.</span><span class="sxs-lookup"><span data-stu-id="46aec-202">But some phone numbers in the sample documents are appended with *(mobile)*.</span></span>

<span data-ttu-id="46aec-203">Wander Kuijken</span><span class="sxs-lookup"><span data-stu-id="46aec-203">Nestor Wilke</span></span><br>
<span data-ttu-id="46aec-204">111-111-1111 (mobiel)</span><span class="sxs-lookup"><span data-stu-id="46aec-204">111-111-1111 (mobile)</span></span><br>
<span data-ttu-id="46aec-205">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="46aec-205">One Microsoft Way</span></span><br>
<span data-ttu-id="46aec-206">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="46aec-206">Redmond, WA 98034</span></span><br>

<span data-ttu-id="46aec-207">Er zijn drie tokens in *(mobiel)*:</span><span class="sxs-lookup"><span data-stu-id="46aec-207">There are three tokens in *(mobile)*:</span></span>

|<span data-ttu-id="46aec-208">Woordengroep</span><span class="sxs-lookup"><span data-stu-id="46aec-208">Phrase</span></span>|<span data-ttu-id="46aec-209">Aantal tokens</span><span class="sxs-lookup"><span data-stu-id="46aec-209">Token count</span></span>|
|--|--|
|<span data-ttu-id="46aec-210">(</span><span class="sxs-lookup"><span data-stu-id="46aec-210">(</span></span>|<span data-ttu-id="46aec-211">1</span><span class="sxs-lookup"><span data-stu-id="46aec-211">1</span></span>|
|<span data-ttu-id="46aec-212">Mobiel</span><span class="sxs-lookup"><span data-stu-id="46aec-212">mobile</span></span>|<span data-ttu-id="46aec-213">2</span><span class="sxs-lookup"><span data-stu-id="46aec-213">2</span></span>|
|<span data-ttu-id="46aec-214">)</span><span class="sxs-lookup"><span data-stu-id="46aec-214">)</span></span>|<span data-ttu-id="46aec-215">3</span><span class="sxs-lookup"><span data-stu-id="46aec-215">3</span></span>|

<span data-ttu-id="46aec-216">Configureer de proximity-instelling voor een bereik van 0 tot en met 3.</span><span class="sxs-lookup"><span data-stu-id="46aec-216">Configure the proximity setting to have a range of 0 through 3.</span></span>

![Voorbeeld van proximity](../media/content-understanding/proximity-example.png)

## <a name="configure-where-phrases-occur-in-the-document"></a><span data-ttu-id="46aec-218">Configureren waar woordgroepen voorkomen in het document</span><span class="sxs-lookup"><span data-stu-id="46aec-218">Configure where phrases occur in the document</span></span>

<span data-ttu-id="46aec-219">Wanneer u een uitleg maakt, wordt standaard in het hele document gezocht naar het patroon dat u wilt extraheren.</span><span class="sxs-lookup"><span data-stu-id="46aec-219">When you create an explanation, by default the entire document is searched for the phrase you're trying to extract.</span></span> <span data-ttu-id="46aec-220">U kunt echter de geavanceerde instelling **Waar deze woordgroepen voorkomen** gebruiken om een specifieke locatie in het document te isoleren waar een woordgroep voorkomt.</span><span class="sxs-lookup"><span data-stu-id="46aec-220">However, you can use the **Where these phrases occur** advanced setting to help in isolating a specific location in the document that a phrase occurs.</span></span> <span data-ttu-id="46aec-221">Deze instelling is handig in situaties waarin vergelijkbare gevallen van een patroon ergens anders in het document kunnen voorkomen en u zeker wilt weten dat de juiste is geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="46aec-221">This setting is useful in situations where similar instances of a phrase might appear somewhere else in the document, and you want to make sure that the correct one is selected.</span></span>

<span data-ttu-id="46aec-222">Wanneer we kijken naar ons voorbeelddocument voor medische verwijzing, wordt de *verwijzende arts* altijd in de eerste alinea van het document vermeld.</span><span class="sxs-lookup"><span data-stu-id="46aec-222">Referring to our Medical Referral document example, the *referring doctor* is always mentioned in the first paragraph of the document.</span></span> <span data-ttu-id="46aec-223">Met de instelling **Waar deze woordgroepen voorkomen** kunt u in dit voorbeeld de uitleg zo configureren dat alleen in het begin van het document naar dit label wordt gezocht, of op een andere locatie waar dit kan voorkomen.</span><span class="sxs-lookup"><span data-stu-id="46aec-223">With the **Where these phrases occur** setting, in this example you can configure your explanation to search for this label only in the beginning section of the document, or any other location in which it might occur.</span></span>

![Instelling Waar deze woordgroepen voorkomen](../media/content-understanding/phrase-location.png)

<span data-ttu-id="46aec-225">U kunt kiezen uit de volgende opties voor deze instelling:</span><span class="sxs-lookup"><span data-stu-id="46aec-225">You can choose the following options for this setting:</span></span>

- <span data-ttu-id="46aec-226">Overal in het bestand: in het hele document wordt naar de woordgroep gezocht.</span><span class="sxs-lookup"><span data-stu-id="46aec-226">Anywhere in the file: The entire document is searched for the phrase.</span></span>

- <span data-ttu-id="46aec-227">Begin van het bestand: het document wordt vanaf het begin tot aan de locatie van de woordgroep doorzocht.</span><span class="sxs-lookup"><span data-stu-id="46aec-227">Beginning of the file:  The document is searched from the beginning to the phrase location.</span></span>

   ![Begin van bestand](../media/content-understanding/beginning-of-file.png)

    <span data-ttu-id="46aec-229">In de viewer kunt u het selectievakje handmatig aanpassen zodat de locatie van de woordgroep wordt opgenomen.</span><span class="sxs-lookup"><span data-stu-id="46aec-229">In the viewer, you can manually adjust the select box to include the location where the phase occurs.</span></span> <span data-ttu-id="46aec-230">De waarde van **Eindpositie** wordt bijgewerkt om het aantal tokens weer te geven dat het geselecteerde gebied bevat.</span><span class="sxs-lookup"><span data-stu-id="46aec-230">The **End position** value will update to show the number of tokens your selected area includes.</span></span> <span data-ttu-id="46aec-231">U kunt de waarde van de **Eindpositie** ook bijwerken om het geselecteerde gebied aan te passen.</span><span class="sxs-lookup"><span data-stu-id="46aec-231">You can update the **End position** value as well to adjust the selected area.</span></span>

   ![Vak Begin van bestandspositie](../media/content-understanding/beginning-box.png)

- <span data-ttu-id="46aec-233">Einde van het bestand: het document wordt vanaf het eind tot aan de locatie van het patroon doorzocht.</span><span class="sxs-lookup"><span data-stu-id="46aec-233">End of the file: The document is searched from the end to the phrase location.</span></span>

   ![Einde van bestand](../media/content-understanding/end-of-file.png)

    <span data-ttu-id="46aec-235">In de viewer kunt u het selectievakje handmatig aanpassen zodat de locatie van de woordgroep wordt opgenomen.</span><span class="sxs-lookup"><span data-stu-id="46aec-235">In the viewer, you can manually adjust the select box to include the location where the phase occurs.</span></span> <span data-ttu-id="46aec-236">De waarde van **Beginpositie** wordt bijgewerkt om het aantal tokens weer te geven dat het geselecteerde gebied bevat.</span><span class="sxs-lookup"><span data-stu-id="46aec-236">The **Starting position** value will update to show the number of tokens your selected area includes.</span></span> <span data-ttu-id="46aec-237">U kunt de waarde van de Beginpositie ook bijwerken om het geselecteerde gebied aan te passen.</span><span class="sxs-lookup"><span data-stu-id="46aec-237">You can update the Starting position value as well to adjust the selected area.</span></span>

   ![Vak Einde van bestand](../media/content-understanding/end-box.png)

- <span data-ttu-id="46aec-239">Aangepast bereik: het document wordt binnen een opgegeven bereik doorzocht op de locatie van het patroon.</span><span class="sxs-lookup"><span data-stu-id="46aec-239">Custom range: The document is searched within a specified range for the phrase location.</span></span>

   ![Aangepast bereik](../media/content-understanding/custom-file.png)

    <span data-ttu-id="46aec-241">In de viewer kunt u het selectievakje handmatig aanpassen zodat de locatie van de woordgroep wordt opgenomen.</span><span class="sxs-lookup"><span data-stu-id="46aec-241">In the viewer, you can manually adjust the select box to include the location where the phase occurs.</span></span> <span data-ttu-id="46aec-242">Voor deze instelling moet u een **Beginpositie** en een **Eindpositie** selecteren.</span><span class="sxs-lookup"><span data-stu-id="46aec-242">For this setting, you need to select a **Start** and an **End** position.</span></span> <span data-ttu-id="46aec-243">Deze waarden geven het aantal tokens aan vanaf het begin van het document.</span><span class="sxs-lookup"><span data-stu-id="46aec-243">These values represent the number of tokens from the beginning of the document.</span></span> <span data-ttu-id="46aec-244">Hoewel u deze waarden handmatig kunt invoeren, is het eenvoudiger om het selectievakje handmatig aan te passen in de viewer.</span><span class="sxs-lookup"><span data-stu-id="46aec-244">While you can manually enter in these values, it's easier to manually adjust the select box in the viewer.</span></span> 
   
## <a name="use-explanation-templates"></a><span data-ttu-id="46aec-245">Uitlegsjablonen gebruiken</span><span class="sxs-lookup"><span data-stu-id="46aec-245">Use explanation templates</span></span>

<span data-ttu-id="46aec-246">Je kan handmatig verschillende frasenlijstwaarden toevoegen voor je uitleg, maar het kan eenvoudiger door sjablonen te gebruiken die aangeboden worden in de uitlegbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="46aec-246">While you can manually add various phrase list values for your explanation, it can be easier to use the templates provided to you in the explanation library.</span></span>

<span data-ttu-id="46aec-247">In plaats van alle variaties voor de *datum* handmatig toe te voegen, kunt u bijvoorbeeld de sjabloonlijst voor het patroon voor *datum* gebruiken, omdat deze al veel waarden voor een patroonlijst bevat:</span><span class="sxs-lookup"><span data-stu-id="46aec-247">For example, instead of manually adding all the variations for *date*, you can use the phrase list template for *date* because it already includes many phrase lists values:</span></span>

![Uitlegbibliotheek](../media/content-understanding/explanation-template.png)
 
<span data-ttu-id="46aec-249&quot;>De uitlegbibliotheek bevat een aantal veelgebruikte beschrijvingen van de *patroonlijst*, waaronder:</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;46aec-249&quot;>The explanation library includes commonly used *phrase list* explanations, including:</span></span>

- <span data-ttu-id=&quot;46aec-250&quot;>Datum: Kalenderdatums, alle notaties.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;46aec-250&quot;>Date: Calendar dates, all formats.</span></span> <span data-ttu-id=&quot;46aec-251&quot;>Bevat tekst en getallen (bijvoorbeeld &quot;9 dec, 2020").</span><span class="sxs-lookup"><span data-stu-id="46aec-251">Includes text and numbers (for example, "Dec 9, 2020").</span></span>
- <span data-ttu-id="46aec-252">Datum (numeriek): Kalenderdatums, alle notaties.</span><span class="sxs-lookup"><span data-stu-id="46aec-252">Date (numeric): Calendar dates, all formats.</span></span> <span data-ttu-id="46aec-253">Bevat getallen (bijvoorbeeld 1-11-2020).</span><span class="sxs-lookup"><span data-stu-id="46aec-253">Includes numbers (for example, 1-11-2020).</span></span>
- <span data-ttu-id="46aec-254">Tijd: 12- en 24-uurs tijdnotatie.</span><span class="sxs-lookup"><span data-stu-id="46aec-254">Time: 12 and 24 hour formats.</span></span>
- <span data-ttu-id="46aec-255">Getal: positieve en negatieve getallen met maximaal twee decimalen.</span><span class="sxs-lookup"><span data-stu-id="46aec-255">Number: Positive and negative numbers up to two decimals.</span></span> 
- <span data-ttu-id="46aec-256">Percentage: een lijst met patronen die een percentage vertegenwoordigen.</span><span class="sxs-lookup"><span data-stu-id="46aec-256">Percentage: A list of patterns representing a percentage.</span></span> <span data-ttu-id="46aec-257">Bijvoorbeeld 1%, 11%, 100% of 11,11%.</span><span class="sxs-lookup"><span data-stu-id="46aec-257">For example, 1%, 11%, 100%, or 11.11%.</span></span>
- <span data-ttu-id="46aec-258">Telefoonnummer: veelgebruikte Amerikaanse en internationale notaties.</span><span class="sxs-lookup"><span data-stu-id="46aec-258">Phone number: Common US and International formats.</span></span> <span data-ttu-id="46aec-259">Bijvoorbeeld 000 000 0000, 000-000-0000, (000)000-0000 of (000) 000-0000.</span><span class="sxs-lookup"><span data-stu-id="46aec-259">For example, 000 000 0000, 000-000-0000, (000)000-0000, or (000) 000-0000.</span></span>
- <span data-ttu-id="46aec-260">Postcode: Amerikaanse postcode-indelingen.</span><span class="sxs-lookup"><span data-stu-id="46aec-260">Zip code: US Zip code formats.</span></span> <span data-ttu-id="46aec-261">Bijvoorbeeld, 11111, 11111-1111.</span><span class="sxs-lookup"><span data-stu-id="46aec-261">For example, 11111, 11111-1111.</span></span>
- <span data-ttu-id="46aec-262">Eerste woord van zin: algemene patronen voor woorden met maximaal negen tekens.</span><span class="sxs-lookup"><span data-stu-id="46aec-262">First word of sentence: Common patterns for words up to nine characters.</span></span> 
- <span data-ttu-id="46aec-263">Einde van zin: veelvoorkomende interpunctie voor het einde van een zin.</span><span class="sxs-lookup"><span data-stu-id="46aec-263">End of sentence: Common punctuation for end of a sentence.</span></span>
- <span data-ttu-id="46aec-264">Creditcard: veelgebruikte notaties voor creditcards.</span><span class="sxs-lookup"><span data-stu-id="46aec-264">Credit card: Common credit card number formats.</span></span> <span data-ttu-id="46aec-265">Bijvoorbeeld, 1111-1111-1111-1111.</span><span class="sxs-lookup"><span data-stu-id="46aec-265">For example, 1111-1111-1111-1111.</span></span> 
- <span data-ttu-id="46aec-p132">Sofinummer: Amerikaanse notatie voor het sofinummer. Bijvoorbeeld: 111-11-1111.</span><span class="sxs-lookup"><span data-stu-id="46aec-p132">Social security number: US Social Security Number format. For example, 111-11-1111.</span></span> 
- <span data-ttu-id="46aec-268">Selectievakje: een patroonlijst die variaties op een ingevuld selectievakje vertegenwoordigt.</span><span class="sxs-lookup"><span data-stu-id="46aec-268">Checkbox: A phrase list representing variations on a filled in checkbox.</span></span> <span data-ttu-id="46aec-269">Bijvoorbeeld: _X_, _ _X_</span><span class="sxs-lookup"><span data-stu-id="46aec-269">For example, _X_, _ _X_.</span></span>
- <span data-ttu-id="46aec-270">Valuta: Belangrijke internationale symbolen.</span><span class="sxs-lookup"><span data-stu-id="46aec-270">Currency: Major international symbols.</span></span> <span data-ttu-id="46aec-271">Bijvoorbeeld, $.</span><span class="sxs-lookup"><span data-stu-id="46aec-271">For example, $.</span></span> 
- <span data-ttu-id="46aec-272">E-mail CC: een patroonlijst met de term 'CC:', die vaak wordt gevonden in de buurt van de namen of e-mailadressen van andere mensen of groepen waarnaar het bericht is verzonden.</span><span class="sxs-lookup"><span data-stu-id="46aec-272">Email CC: A phrase list with the term 'CC:', often found near the names or email addresses of other people or groups the message was sent to.</span></span>
- <span data-ttu-id="46aec-273">E-maildatum: Een frasenlijst met de term 'Verzonden op:', vaak gevonden bij de datum waarop het e-mailbericht is verzonden.</span><span class="sxs-lookup"><span data-stu-id="46aec-273">Email date: A phrase list with the term 'Sent on:', often found near the date the email was sent.</span></span>
- <span data-ttu-id="46aec-274">E-mail begroeting: Algemene beginregels voor e-mailberichten.</span><span class="sxs-lookup"><span data-stu-id="46aec-274">Email greeting: Common opening lines for emails.</span></span>
- <span data-ttu-id="46aec-275">E-mail ontvanger: Een frasenlijst met de term 'Aan:', vaak gevonden in de buurt van de namen of e-mailadressen van personen of groepen waar het bericht naar is verzonden.</span><span class="sxs-lookup"><span data-stu-id="46aec-275">Email recipient: A phrase list with the term 'To:', often found near the names or email addresses of people or groups the message was sent to.</span></span> 
- <span data-ttu-id="46aec-276">E-mail afzender: Een frasenlijst met de term 'Van:', vaak gevonden in de buurt van de naam of het e-mailadres van de afzender.</span><span class="sxs-lookup"><span data-stu-id="46aec-276">Email sender: A phrase list with the term 'From:', often found near the sender's name or email address.</span></span> 
- <span data-ttu-id="46aec-277">E-mail onderwerp: Een frasenlijst met de term 'Onderwerp:', vaak gevonden in de buurt van het e-mail onderwerp.</span><span class="sxs-lookup"><span data-stu-id="46aec-277">Email subject: A phrase list with the term 'Subject:', often found near the email's subject.</span></span>

<span data-ttu-id="46aec-278">De uitlegbibliotheek bevat beschrijvingen van een aantal veelgebruikte *reguliere expressies*, waaronder:</span><span class="sxs-lookup"><span data-stu-id="46aec-278">The explanation library also includes commonly used *regular expression* explanations, including:</span></span>

- <span data-ttu-id="46aec-279">6 tot 17 cijfers: komt overeen met een getal van 6 tot 17 cijfers.</span><span class="sxs-lookup"><span data-stu-id="46aec-279">6 to 17 digit numbers: Matches any number from 6 to 17 digits long.</span></span> <span data-ttu-id="46aec-280">Amerikaanse bankrekeningnummers hebben dit patroon.</span><span class="sxs-lookup"><span data-stu-id="46aec-280">US bank account numbers fit this pattern.</span></span>
- <span data-ttu-id="46aec-281">E-mailadres: komt overeen met een gangbaar type e-mailadres zoals meganb@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="46aec-281">Email address: Matches a common type of email address like meganb@contoso.com.</span></span>
- <span data-ttu-id="46aec-282">Id-nummer van Amerikaanse belastingplichtige: komt overeen met een driecijferig nummer dat begint met een 9, gevolgd door een zescijferig nummer dat begint met een 7 of 8.</span><span class="sxs-lookup"><span data-stu-id="46aec-282">US taxpayer ID number: Matches a three-digit number starting with 9 followed by a 6 digit number starting with 7 or 8.</span></span> 
- <span data-ttu-id="46aec-283">Webadres (URL): komt overeen met de indeling van een webadres, beginnend met http:// of https://.</span><span class="sxs-lookup"><span data-stu-id="46aec-283">Web address (URL): Matches the format of a web address, starting with http:// or https://.</span></span>

<span data-ttu-id="46aec-284">Bovendien bevat de uitlegbibliotheek drie automatische sjabloontypen die werken met de gegevens die u in uw voorbeeldbestanden hebt gelabeld:</span><span class="sxs-lookup"><span data-stu-id="46aec-284">In addition, the explanation library includes three automatic template types that work with the data you've labeled in your example files:</span></span>

- <span data-ttu-id="46aec-285">After-label: De woorden of karakters die voorkomen na de labels in de voorbeeldbestanden.</span><span class="sxs-lookup"><span data-stu-id="46aec-285">After label: The words or characters that occur after the labels in the example files.</span></span>
- <span data-ttu-id="46aec-286">Before-label: De woorden of karakters die voorkomen voor de labels in de voorbeeldbestanden.</span><span class="sxs-lookup"><span data-stu-id="46aec-286">Before label: The words or characters that occur before the labels in the example files.</span></span>
- <span data-ttu-id="46aec-287">Labels: Tot maximaal de eerste 10 karakters van de voorbeeldbestanden.</span><span class="sxs-lookup"><span data-stu-id="46aec-287">Labels: Up to the first 10 labels from the example files.</span></span>

<span data-ttu-id="46aec-288">Automatische sjablonen werken bijvoorbeeld zoals in het volgende voorbeeldbestand waar we de before-label-uitlegsjabloon gebruiken om het model meer informatie te geven zodat we tot een nauwkeurigere overeenkomst komen.</span><span class="sxs-lookup"><span data-stu-id="46aec-288">To give you an example of how automatic templates work, in the following example file, we'll use the Before label explanation template to help give the model more information to get a more accurate match.</span></span>

![Voorbeeldbestand](../media/content-understanding/before-label.png)

<span data-ttu-id="46aec-290">Als je het before-label-uitlegsjabloon selecteert, zoekt het de eerste groep woorden die voorkomen vóór het label in je voorbeeldbestanden.</span><span class="sxs-lookup"><span data-stu-id="46aec-290">When you select the Before label explanation template, it will look for the first set of words that appear before the label in your example files.</span></span> <span data-ttu-id="46aec-291">In het voorbeeld is het woord dat geïdentificeerd werd ‘Vanaf’.</span><span class="sxs-lookup"><span data-stu-id="46aec-291">In the example, the words that are identified in the first example file is "As of".</span></span>

![Before-labelsjabloon](../media/content-understanding/before-label-explanation.png)

<span data-ttu-id="46aec-293">Je kan een uitleg voor een sjabloon maken door **Toevoegen** te selecteren.</span><span class="sxs-lookup"><span data-stu-id="46aec-293">You can select **Add** to create an explanation from the template.</span></span>  <span data-ttu-id="46aec-294">Aanvullende woorden worden geïdentificeerd en toegevoegd aan de frasenlijst naargelang je meer voorbeeldbestanden toevoegt.</span><span class="sxs-lookup"><span data-stu-id="46aec-294">As you add more example files, additional words will be identified and added to the phrase list.</span></span>

![Het label toevoegen](../media/content-understanding/before-label-add.png)
 
#### <a name="to-use-a-template-from-the-explanation-library"></a><span data-ttu-id="46aec-296">Een sjabloon gebruiken uit de uitlegbibliotheek</span><span class="sxs-lookup"><span data-stu-id="46aec-296">To use a template from the explanation library</span></span>

1. <span data-ttu-id="46aec-297">Ga naar het gedeelte **Uitleg** van de **Train**-pagina van je model en selecteer **Nieuwe** en selecteer vervolgens **Van een sjabloon**.</span><span class="sxs-lookup"><span data-stu-id="46aec-297">From the **Explanations** section of your model's **Train** page, select **New**, then select **From a template**.</span></span>

   ![Before-label toevoegen](../media/content-understanding/from-template.png)

2.  <span data-ttu-id="46aec-299">Selecteer op de pagina **Uitlegsjablonen** de uitleg die je wilt gebruiken en selecteer vervolgens **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="46aec-299">On the **Explanation templates** page, select the explanation you want to use, then select **Add**.</span></span>

    ![Selecteer een sjabloon](../media/content-understanding/phone-template.png)

3. <span data-ttu-id="46aec-301">De informatie voor de sjabloon die je hebt geselecteerd, wordt weergegeven op de pagina **Een uitleg maken**.</span><span class="sxs-lookup"><span data-stu-id="46aec-301">The information for the template you selected displays on the **Create an explanation** page.</span></span> <span data-ttu-id="46aec-302">Bewerk zo nodig de naam van de uitleg en voeg items toe of verwijder items uit de frasenlijst.</span><span class="sxs-lookup"><span data-stu-id="46aec-302">If needed, edit the explanation name and add or remove items from the phrase list.</span></span>  

    ![Sjabloon bewerken](../media/content-understanding/phone-template-live.png)

4. <span data-ttu-id="46aec-304">Selecteer **Opslaan** wanneer je klaar bent.</span><span class="sxs-lookup"><span data-stu-id="46aec-304">When finished, select **Save**.</span></span>