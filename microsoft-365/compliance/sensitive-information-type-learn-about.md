---
title: Meer informatie over typen gevoelige informatie
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
search.appverid: MET150
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: In dit artikel wordt een overzicht gegeven van gevoelige informatietypen en hoe ze gevoelige informatie detecteren, zoals sociale zekerheid, creditcard- of bankrekeningnummers om gevoelige items te identificeren
ms.openlocfilehash: dee4ec59ce5fe6140c4aef33d147e89e11facd59
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/15/2021
ms.locfileid: "53453619"
---
# <a name="learn-about-sensitive-information-types"></a><span data-ttu-id="6683f-103">Meer informatie over typen gevoelige informatie</span><span class="sxs-lookup"><span data-stu-id="6683f-103">Learn about sensitive information types</span></span>

<span data-ttu-id="6683f-104">Het identificeren en classificeren van gevoelige items die onder uw organisatiebeheer vallen, is de eerste stap in de [discipline Informatiebeveiliging.](./information-protection.md)</span><span class="sxs-lookup"><span data-stu-id="6683f-104">Identifying and classifying sensitive items that are under your organizations control is the first step in the [Information Protection discipline](./information-protection.md).</span></span>  <span data-ttu-id="6683f-105">Microsoft 365 biedt drie manieren om items te identificeren, zodat ze kunnen worden geclassificeerd:</span><span class="sxs-lookup"><span data-stu-id="6683f-105">Microsoft 365 provides three ways of identifying items so that they can be classified:</span></span>

- <span data-ttu-id="6683f-106">handmatig door gebruikers</span><span class="sxs-lookup"><span data-stu-id="6683f-106">manually by users</span></span>
- <span data-ttu-id="6683f-107">geautomatiseerde patroonherkenning, zoals gevoelige informatietypen</span><span class="sxs-lookup"><span data-stu-id="6683f-107">automated pattern recognition, like sensitive information types</span></span>
- [<span data-ttu-id="6683f-108">machine learning</span><span class="sxs-lookup"><span data-stu-id="6683f-108">machine learning</span></span>](classifier-learn-about.md)

<span data-ttu-id="6683f-109">Gevoelige informatietypen zijn classificaties op basis van patronen.</span><span class="sxs-lookup"><span data-stu-id="6683f-109">Sensitive information types are pattern-based classifiers.</span></span> <span data-ttu-id="6683f-110">Ze detecteren gevoelige informatie, zoals sociale zekerheid, creditcard- of bankrekeningnummers om gevoelige items te identificeren, zie Definities van [entiteitstypen gevoelige informatie](sensitive-information-type-entity-definitions.md)</span><span class="sxs-lookup"><span data-stu-id="6683f-110">They detect sensitive information like social security, credit card, or bank account numbers to identify sensitive items, see [Sensitive information types entity definitions](sensitive-information-type-entity-definitions.md)</span></span>

## <a name="sensitive-information-types-are-used-in"></a><span data-ttu-id="6683f-111">Gevoelige informatietypen worden gebruikt in</span><span class="sxs-lookup"><span data-stu-id="6683f-111">Sensitive information types are used in</span></span>

- [<span data-ttu-id="6683f-112">Preventiebeleid voor gegevensverlies</span><span class="sxs-lookup"><span data-stu-id="6683f-112">Data loss prevention policies</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="6683f-113">Gevoeligheidslabels</span><span class="sxs-lookup"><span data-stu-id="6683f-113">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="6683f-114">Retentielabels</span><span class="sxs-lookup"><span data-stu-id="6683f-114">Retention labels</span></span>](retention.md)
- [<span data-ttu-id="6683f-115">Intern risicobeheer</span><span class="sxs-lookup"><span data-stu-id="6683f-115">Insider risk management</span></span>](insider-risk-management.md)
- [<span data-ttu-id="6683f-116">Communicatiecompliance</span><span class="sxs-lookup"><span data-stu-id="6683f-116">Communication compliance</span></span>](communication-compliance.md)
- [<span data-ttu-id="6683f-117">Beleid voor automatisch labelen</span><span class="sxs-lookup"><span data-stu-id="6683f-117">Auto-labelling policies</span></span>](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps)
- [<span data-ttu-id="6683f-118">Privacybeheer (preview)</span><span class="sxs-lookup"><span data-stu-id="6683f-118">Privacy management (preview)</span></span>](privacy-management.md)

## <a name="fundamental-parts-of-a-sensitive-information-type"></a><span data-ttu-id="6683f-119">Basisonderdelen van een type gevoelige informatie</span><span class="sxs-lookup"><span data-stu-id="6683f-119">Fundamental parts of a sensitive information type</span></span>

<span data-ttu-id="6683f-120">Elke entiteit van het type gevoelige informatie wordt gedefinieerd door deze velden:</span><span class="sxs-lookup"><span data-stu-id="6683f-120">Every sensitive information type entity is defined by these fields:</span></span>

- <span data-ttu-id="6683f-121">naam: de manier waarop naar het type gevoelige informatie wordt verwezen</span><span class="sxs-lookup"><span data-stu-id="6683f-121">name: how the sensitive information type is referred to</span></span>
- <span data-ttu-id="6683f-122">beschrijving: beschrijft wat het type gevoelige informatie zoekt</span><span class="sxs-lookup"><span data-stu-id="6683f-122">description: describes what the sensitive information type is looking for</span></span>
- <span data-ttu-id="6683f-123">patroon: Een patroon definieert wat een gevoelige informatietype detecteert.</span><span class="sxs-lookup"><span data-stu-id="6683f-123">pattern: A pattern defines what a sensitive information type detects.</span></span> <span data-ttu-id="6683f-124">Deze bestaat uit de volgende onderdelen</span><span class="sxs-lookup"><span data-stu-id="6683f-124">It consists of the following components</span></span>
    - <span data-ttu-id="6683f-125">Primair element: het hoofdelement dat het gevoelige informatietype zoekt.</span><span class="sxs-lookup"><span data-stu-id="6683f-125">Primary element – the main element that the sensitive information type is looking for.</span></span> <span data-ttu-id="6683f-126">Het kan een normale **expressie zijn** met of zonder een checksumvalidatie, een **trefwoordlijst,** een woordenlijst **met** trefwoorden of een **functie.**</span><span class="sxs-lookup"><span data-stu-id="6683f-126">It can be a **regular expression** with or without a checksum validation, a **keyword list**, a **keyword dictionary**, or a **function**.</span></span>
    - <span data-ttu-id="6683f-127">Ondersteunend element: elementen die fungeren als ondersteunend bewijs om het vertrouwen van de overeenkomst te vergroten.</span><span class="sxs-lookup"><span data-stu-id="6683f-127">Supporting element – elements that act as supporting evidence that help in increasing the confidence of the match.</span></span> <span data-ttu-id="6683f-128">Trefwoord 'SSN' bijvoorbeeld in de nabijheid van een SSN-getal.</span><span class="sxs-lookup"><span data-stu-id="6683f-128">For example, keyword “SSN” in proximity of an SSN number.</span></span> <span data-ttu-id="6683f-129">Het kan een normale expressie zijn met of zonder een checksumvalidatie, trefwoordlijst, trefwoordwoordenlijst.</span><span class="sxs-lookup"><span data-stu-id="6683f-129">It can be a regular expression with or without a checksum validation, keyword list, keyword dictionary.</span></span>
    - <span data-ttu-id="6683f-130">Betrouwbaarheidsniveau: betrouwbaarheidsniveaus (hoog, gemiddeld, laag) geven aan hoeveel ondersteunend bewijs samen met het primaire element is gevonden.</span><span class="sxs-lookup"><span data-stu-id="6683f-130">Confidence Level - Confidence levels (high, medium, low) reflect how much supporting evidence was detected along with the primary element.</span></span> <span data-ttu-id="6683f-131">Hoe meer ondersteunend bewijs een item bevat, hoe groter het vertrouwen dat een overeenkomend item de gevoelige informatie bevat die u zoekt.</span><span class="sxs-lookup"><span data-stu-id="6683f-131">The more supporting evidence an item contains, the higher the confidence that a matched item contains the sensitive info you're looking for.</span></span>
    - <span data-ttu-id="6683f-132">Nabijheid: aantal tekens tussen primair en ondersteunend element</span><span class="sxs-lookup"><span data-stu-id="6683f-132">Proximity – Number of characters between primary and supporting element</span></span>

![Diagram van ondersteunende gegevens en nabijheidsmarge](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

<span data-ttu-id="6683f-134">Meer informatie over betrouwbaarheidsniveaus in deze video</span><span class="sxs-lookup"><span data-stu-id="6683f-134">Learn more about confidence levels in this video</span></span>


 > [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Hx60]  

### <a name="example-sensitive-information-type"></a><span data-ttu-id="6683f-135">Voorbeeld van het type gevoelige informatie</span><span class="sxs-lookup"><span data-stu-id="6683f-135">Example sensitive information type</span></span>


## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="6683f-136">Argentinië national identity (DNI) number</span><span class="sxs-lookup"><span data-stu-id="6683f-136">Argentina national identity (DNI) number</span></span>

### <a name="format"></a><span data-ttu-id="6683f-137">Opmaak</span><span class="sxs-lookup"><span data-stu-id="6683f-137">Format</span></span>

<span data-ttu-id="6683f-138">Acht cijfers gescheiden door perioden</span><span class="sxs-lookup"><span data-stu-id="6683f-138">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="6683f-139">Patroon</span><span class="sxs-lookup"><span data-stu-id="6683f-139">Pattern</span></span>

<span data-ttu-id="6683f-140">Acht cijfers:</span><span class="sxs-lookup"><span data-stu-id="6683f-140">Eight digits:</span></span>
- <span data-ttu-id="6683f-141">twee cijfers</span><span class="sxs-lookup"><span data-stu-id="6683f-141">two digits</span></span>
- <span data-ttu-id="6683f-142">een punt</span><span class="sxs-lookup"><span data-stu-id="6683f-142">a period</span></span>
- <span data-ttu-id="6683f-143">drie cijfers</span><span class="sxs-lookup"><span data-stu-id="6683f-143">three digits</span></span>
- <span data-ttu-id="6683f-144">een punt</span><span class="sxs-lookup"><span data-stu-id="6683f-144">a period</span></span>
- <span data-ttu-id="6683f-145">drie cijfers</span><span class="sxs-lookup"><span data-stu-id="6683f-145">three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6683f-146">Checksum</span><span class="sxs-lookup"><span data-stu-id="6683f-146">Checksum</span></span>

<span data-ttu-id="6683f-147">Nee</span><span class="sxs-lookup"><span data-stu-id="6683f-147">No</span></span>

### <a name="definition"></a><span data-ttu-id="6683f-148">Definitie</span><span class="sxs-lookup"><span data-stu-id="6683f-148">Definition</span></span>

<span data-ttu-id="6683f-149">Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:</span><span class="sxs-lookup"><span data-stu-id="6683f-149">A DLP policy has medium confidence that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6683f-150">De normale expressie Regex_argentina_national_id inhoud die overeenkomt met het patroon.</span><span class="sxs-lookup"><span data-stu-id="6683f-150">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="6683f-151">Er wordt een trefwoord Keyword_argentina_national_id gevonden.</span><span class="sxs-lookup"><span data-stu-id="6683f-151">A keyword from Keyword_argentina_national_id is found.</span></span>

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6683f-152">Trefwoorden</span><span class="sxs-lookup"><span data-stu-id="6683f-152">Keywords</span></span>

#### <a name="keyword_argentina_national_id"></a><span data-ttu-id="6683f-153">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="6683f-153">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="6683f-154">Nationale identiteitsnummer argentinië</span><span class="sxs-lookup"><span data-stu-id="6683f-154">Argentina National Identity number</span></span> 
- <span data-ttu-id="6683f-155">Identiteit</span><span class="sxs-lookup"><span data-stu-id="6683f-155">Identity</span></span> 
- <span data-ttu-id="6683f-156">Identificatie nationale identiteitskaart</span><span class="sxs-lookup"><span data-stu-id="6683f-156">Identification National Identity Card</span></span> 
- <span data-ttu-id="6683f-157">DNI</span><span class="sxs-lookup"><span data-stu-id="6683f-157">DNI</span></span> 
- <span data-ttu-id="6683f-158">NIC National Registry of Persons</span><span class="sxs-lookup"><span data-stu-id="6683f-158">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="6683f-159">Documento Nacional de Identidad</span><span class="sxs-lookup"><span data-stu-id="6683f-159">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="6683f-160">Registro Nacional de las Personas</span><span class="sxs-lookup"><span data-stu-id="6683f-160">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="6683f-161">Identidad</span><span class="sxs-lookup"><span data-stu-id="6683f-161">Identidad</span></span> 
- <span data-ttu-id="6683f-162">Identificación</span><span class="sxs-lookup"><span data-stu-id="6683f-162">Identificación</span></span> 

### <a name="more-on-confidence-levels"></a><span data-ttu-id="6683f-163">Meer informatie over betrouwbaarheidsniveaus</span><span class="sxs-lookup"><span data-stu-id="6683f-163">More on confidence levels</span></span>

<span data-ttu-id="6683f-164">In een entiteitsdefinitie van het type gevoelige informatie **geeft** betrouwbaarheidsniveau aan hoeveel ondersteunend bewijs wordt gedetecteerd naast het primaire element.</span><span class="sxs-lookup"><span data-stu-id="6683f-164">In a sensitive information type entity definition, **confidence level** reflects how much supporting evidence is detected in addition to the primary element.</span></span> <span data-ttu-id="6683f-165">Hoe meer ondersteunend bewijs een item bevat, hoe groter het vertrouwen dat een overeenkomend item de gevoelige informatie bevat die u zoekt.</span><span class="sxs-lookup"><span data-stu-id="6683f-165">The more supporting evidence an item contains, the higher the confidence that a matched item contains the sensitive info you're looking for.</span></span> <span data-ttu-id="6683f-166">Overeenkomsten met een hoog betrouwbaarheidsniveau bevatten bijvoorbeeld meer ondersteunend bewijs in de nabijheid van het primaire element, terwijl overeenkomsten met een laag betrouwbaarheidsniveau in de nabijheid weinig tot geen ondersteunend bewijs bevatten.</span><span class="sxs-lookup"><span data-stu-id="6683f-166">For example, matches with a high confidence level will contain more supporting evidence in close proximity of the primary element, whereas matches with a low confidence level would contain little to no supporting evidence in close proximity.</span></span> 

<span data-ttu-id="6683f-167">Een hoog betrouwbaarheidsniveau retourneert de minste onwaar-positieven, maar kan leiden tot meer onwaar negatieven.</span><span class="sxs-lookup"><span data-stu-id="6683f-167">A high confidence level returns the fewest false positives but might result in more false negatives.</span></span> <span data-ttu-id="6683f-168">Lage of gemiddelde betrouwbaarheidsniveaus retourneert meer onwaar-positieve waarden, maar weinig tot nul onwaar negatieven.</span><span class="sxs-lookup"><span data-stu-id="6683f-168">Low or medium confidence levels returns more false positives but few to zero false negatives.</span></span>

- <span data-ttu-id="6683f-169">**weinig vertrouwen:** waarde van 65, overeenkomende items bevat de minste onwaar negatieven, maar de meeste onwaar positieven.</span><span class="sxs-lookup"><span data-stu-id="6683f-169">**low confidence**: Value of 65, matched items will contain the fewest false negatives but the most false positives.</span></span> <span data-ttu-id="6683f-170">Lage betrouwbaarheid retourneert alle overeenkomsten met lage, gemiddelde en hoge betrouwbaarheid.</span><span class="sxs-lookup"><span data-stu-id="6683f-170">Low confidence returns all low, medium, and high confidence matches.</span></span>
- <span data-ttu-id="6683f-171">**gemiddeld vertrouwen:** waarde van 75, overeenkomende items bevat een gemiddelde hoeveelheid onwaar-positieven en onwaar negatieven.</span><span class="sxs-lookup"><span data-stu-id="6683f-171">**medium confidence**: Value of 75, matched items will contain an average amount of false positives and false negatives.</span></span> <span data-ttu-id="6683f-172">Gemiddeld vertrouwen retourneert alle gemiddelde en hoge betrouwbaarheids matches.</span><span class="sxs-lookup"><span data-stu-id="6683f-172">Medium confidence returns all medium, and high confidence matches.</span></span>  
- <span data-ttu-id="6683f-173">**hoog vertrouwen:** waarde van 85, overeenkomende items bevat de minste onwaar-positieven, maar de meeste onwaar negatieven.</span><span class="sxs-lookup"><span data-stu-id="6683f-173">**high confidence**: Value of 85, matched items will contain the fewest false positives but the most false negatives.</span></span> <span data-ttu-id="6683f-174">Hoog vertrouwen geeft alleen overeenkomsten met hoog vertrouwen als rendement.</span><span class="sxs-lookup"><span data-stu-id="6683f-174">High confidence only returns high confidence matches.</span></span>  

<span data-ttu-id="6683f-175">Gebruik patronen met een hoog betrouwbaarheidsniveau met lage tellingen, bijvoorbeeld vijf tot tien, en lage betrouwbaarheidspatronen met hogere tellingen, bijvoorbeeld 20 of meer.</span><span class="sxs-lookup"><span data-stu-id="6683f-175">You should use high confidence level patterns with low counts, say five to ten, and low confidence patterns with higher counts, say 20 or more.</span></span>

> [!NOTE]
> <span data-ttu-id="6683f-176">Als u bestaande beleidsregels of aangepaste gevoelige informatietypen (SIT's) hebt gedefinieerd met behulp van betrouwbaarheidsniveaus op basis van een getal (ook bekend als nauwkeurigheid), worden deze automatisch aan de drie afzonderlijke betrouwbaarheidsniveaus toegesneden. weinig vertrouwen, gemiddeld vertrouwen en veel vertrouwen in de gebruikersinterface van het Beveiligings- en compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="6683f-176">If you have existing policies or custom sensitive information types (SITs) defined using number-based confidence levels (also know as accuracy), they will automatically be mapped to the three discrete confidence levels; low confidence, medium confidence, and high confidence, across the Security @ Compliance Center UI.</span></span>
> - <span data-ttu-id="6683f-177">Alle beleidsregels met minimale nauwkeurigheid of aangepaste SIT-patronen met betrouwbaarheidsniveaus tussen 76 en 100 worden in kaart gebracht op hoog vertrouwen.</span><span class="sxs-lookup"><span data-stu-id="6683f-177">All policies with minimum accuracy or custom SIT patterns with confidence levels of between 76 and 100 will be mapped to high confidence.</span></span> 
> - <span data-ttu-id="6683f-178">Alle beleidsregels met minimale nauwkeurigheid of aangepaste SIT-patronen met betrouwbaarheidsniveaus tussen 66 en 75 worden in kaart gebracht op gemiddeld vertrouwen.</span><span class="sxs-lookup"><span data-stu-id="6683f-178">All policies with minimum accuracy or custom SIT patterns with confidence levels of between 66 and 75 will be mapped to medium confidence.</span></span>
> - <span data-ttu-id="6683f-179">Alle beleidsregels met minimale nauwkeurigheid of aangepaste SIT-patronen met betrouwbaarheidsniveaus kleiner dan of gelijk aan 65, worden in kaart gebracht aan lage betrouwbaarheid.</span><span class="sxs-lookup"><span data-stu-id="6683f-179">All policies with minimum accuracy or custom SIT patterns with confidence levels less than or equal to 65 will be mapped to low confidence.</span></span> 

## <a name="creating-custom-sensitive-information-types"></a><span data-ttu-id="6683f-180">Aangepaste gevoelige informatietypen maken</span><span class="sxs-lookup"><span data-stu-id="6683f-180">Creating custom sensitive information types</span></span>

<span data-ttu-id="6683f-181">Als u aangepaste gevoelige informatietypen wilt maken in het beveiligings- & compliancecentrum, kunt u kiezen uit verschillende opties:</span><span class="sxs-lookup"><span data-stu-id="6683f-181">To create custom sensitive information types in the Security & Compliance Center, you can choose from several options:</span></span>

- <span data-ttu-id="6683f-182">**De gebruikersinterface gebruiken** U kunt een aangepast type gevoelige informatie instellen met behulp van de gebruikersinterface & compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="6683f-182">**Use the UI** You can set up a custom sensitive information type using the Security & Compliance Center UI.</span></span> <span data-ttu-id="6683f-183">Met deze methode kunt u gewone expressies, trefwoorden en woordenlijsten voor trefwoorden gebruiken.</span><span class="sxs-lookup"><span data-stu-id="6683f-183">With this method, you can use regular expressions, keywords, and keyword dictionaries.</span></span> <span data-ttu-id="6683f-184">Zie Een aangepast type gevoelige informatie maken voor [meer informatie.](create-a-custom-sensitive-information-type.md)</span><span class="sxs-lookup"><span data-stu-id="6683f-184">To learn more, see [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md).</span></span>

- <span data-ttu-id="6683f-185">**EDM gebruiken** U kunt aangepaste gevoelige informatietypen instellen met de classificatie Exact Data Match (EDM).</span><span class="sxs-lookup"><span data-stu-id="6683f-185">**Use EDM** You can set up custom sensitive information types using Exact Data Match (EDM)-based classification.</span></span> <span data-ttu-id="6683f-186">Met deze methode kunt u een dynamisch type gevoelige informatie maken met behulp van een beveiligde database die u regelmatig kunt vernieuwen.</span><span class="sxs-lookup"><span data-stu-id="6683f-186">This method enables you to create a dynamic sensitive information type using a secure database that you can refresh periodically.</span></span> <span data-ttu-id="6683f-187">Zie [Een aangepast type gevoelige informatie maken met de classificatie Exacte gegevensmatch.](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)</span><span class="sxs-lookup"><span data-stu-id="6683f-187">See [Create a custom sensitive information type with Exact Data Match based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

- <span data-ttu-id="6683f-188">**PowerShell gebruiken** U kunt aangepaste gevoelige informatietypen instellen met PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6683f-188">**Use PowerShell** You can set up custom sensitive information types using PowerShell.</span></span> <span data-ttu-id="6683f-189">Hoewel deze methode complexer is dan het gebruikersinterface, hebt u meer configuratieopties.</span><span class="sxs-lookup"><span data-stu-id="6683f-189">Although this method is more complex than using the UI, you have more configuration options.</span></span> <span data-ttu-id="6683f-190">Zie [Een aangepast type gevoelige informatie maken in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="6683f-190">See [Create a custom sensitive information type in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span>



> [!NOTE]
> <span data-ttu-id="6683f-191">Verbeterde betrouwbaarheidsniveaus zijn beschikbaar voor direct gebruik in preventie van gegevensverlies voor Microsoft 365-services, Microsoft Information Protection voor Microsoft 365-services, Communicatie compliance, informatiebeheer en recordsbeheer.</span><span class="sxs-lookup"><span data-stu-id="6683f-191">Improved confidence levels are available for immediate use within Data Loss Prevention for Microsoft 365 services, Microsoft Information Protection for Microsoft 365 services, Communication Compliance, Information Governance, and Records Management.</span></span>
> <span data-ttu-id="6683f-192">Microsoft 365 Information Protection ondersteunt nu dubbele bytetekensettalen voor:</span><span class="sxs-lookup"><span data-stu-id="6683f-192">Microsoft 365 Information Protection now  supports double byte character set languages for:</span></span>
> - <span data-ttu-id="6683f-193">Vereenvoudigd Chinees</span><span class="sxs-lookup"><span data-stu-id="6683f-193">Chinese (simplified)</span></span>
> - <span data-ttu-id="6683f-194">Traditioneel Chinees</span><span class="sxs-lookup"><span data-stu-id="6683f-194">Chinese (traditional)</span></span>
> - <span data-ttu-id="6683f-195">Korean</span><span class="sxs-lookup"><span data-stu-id="6683f-195">Korean</span></span>
> - <span data-ttu-id="6683f-196">Japanese</span><span class="sxs-lookup"><span data-stu-id="6683f-196">Japanese</span></span>
> 
> <span data-ttu-id="6683f-197">Deze ondersteuning is beschikbaar voor typen gevoelige informatie.</span><span class="sxs-lookup"><span data-stu-id="6683f-197">This support is available for sensitive information types.</span></span> <span data-ttu-id="6683f-198">Zie [Ondersteuning voor Information Protection voor releaseopmerkingen bij dubbel-bytetekensets (preview)](mip-dbcs-relnotes.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="6683f-198">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>

> [!TIP]
> <span data-ttu-id="6683f-199">Om patronen te detecteren die Chinese/Japanse karakters en enkelbyte karakters bevatten of om patronen te detecteren die Chinees/Japans en Engels bevatten, definieert u twee varianten van het trefwoord of de regex.</span><span class="sxs-lookup"><span data-stu-id="6683f-199">To detect patterns containing Chinese/Japanese characters and single byte characters or to detect patterns containing Chinese/Japanese and English, define two variants of the keyword or regex.</span></span>
> 
> <span data-ttu-id="6683f-200">Om bijvoorbeeld een trefwoord als "机密的document" te detecteren, gebruikt u twee varianten van het trefwoord; een met een spatie tussen de Japanse en Engelse tekst en een andere zonder een spatie tussen de Japanse en Engelse tekst.</span><span class="sxs-lookup"><span data-stu-id="6683f-200">For example, to detect a keyword like "机密的document", use two variants of the keyword; one with a space between the Japanese and English text and another without a space between the Japanese and English text.</span></span> <span data-ttu-id="6683f-201">De trefwoorden die in de SIT moeten worden toegevoegd, moeten dus "机密的 document" en "机密的document" zijn.</span><span class="sxs-lookup"><span data-stu-id="6683f-201">So, the keywords to be added in the SIT should be "机密的 document" and "机密的document".</span></span> <span data-ttu-id="6683f-202">Evenzo moeten twee varianten worden gebruikt om een zin "東京オリンピック2020" te detecteren; "東京オリンピック 2020" en "東京オリンピック2020".</span><span class="sxs-lookup"><span data-stu-id="6683f-202">Similarly, to detect a phrase "東京オリンピック2020", two variants should be used; "東京オリンピック 2020" and "東京オリンピック2020".</span></span>
> 
> <span data-ttu-id="6683f-p118">Tijdens het maken van een regex met behulp van een dubbel byteafbreekstreepje of een dubbele byteperiode, moet u ervoor zorgen dat beide tekens, zoals één, een afbreekstreepje of een punt in een regex. Hier volgt een voorbeeld van een regex ter referentie:</span><span class="sxs-lookup"><span data-stu-id="6683f-p118">While creating a regex using a double byte hyphen or a double byte period, make sure to escape both the characters like one would escape a hyphen or period in a regex. Here is a sample regex for reference:</span></span>
>    - <span data-ttu-id="6683f-205">(?<!\d)([４][０-９]{3}[\-?\－\t]\*[０-９]{4}</span><span class="sxs-lookup"><span data-stu-id="6683f-205">(?<!\d)([４][０-９]{3}[\-?\－\t]\*[０-９]{4}</span></span>
>
> <span data-ttu-id="6683f-206">Het is raadzaam tekenreeksmatch te gebruiken in plaats van woordmatch in een trefwoordlijst.</span><span class="sxs-lookup"><span data-stu-id="6683f-206">We recommend using string match instead of word match in a keyword list.</span></span>

## <a name="for-further-information"></a><span data-ttu-id="6683f-207">Voor meer informatie</span><span class="sxs-lookup"><span data-stu-id="6683f-207">For further information</span></span>
- [<span data-ttu-id="6683f-208">Entiteitsdefinities voor het type gevoelige informatie</span><span class="sxs-lookup"><span data-stu-id="6683f-208">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="6683f-209">Een aangepast type gevoelige informatie maken</span><span class="sxs-lookup"><span data-stu-id="6683f-209">Create a custom sensitive information type</span></span>](create-a-custom-sensitive-information-type.md)
- [<span data-ttu-id="6683f-210">Een aangepast type gevoelige informatie maken in PowerShell</span><span class="sxs-lookup"><span data-stu-id="6683f-210">Create a custom sensitive information type in PowerShell</span></span>](create-a-custom-sensitive-information-type-in-scc-powershell.md)

<span data-ttu-id="6683f-211">Zie Informatiebeveiliging implementeren voor privacyregels voor gegevens met [](../solutions/information-protection-deploy.md) Microsoft 365 (aka.ms/m365dataprivacy).</span><span class="sxs-lookup"><span data-stu-id="6683f-211">To learn how to use sensitive information types to comply with data privacy regulations, see [Deploy information protection for data privacy regulations with Microsoft 365](../solutions/information-protection-deploy.md)  (aka.ms/m365dataprivacy).</span></span>

<!-- fwlink for this topic https://go.microsoft.com/fwlink/?linkid=2135644-->
