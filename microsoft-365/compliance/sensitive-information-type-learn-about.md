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
description: ''
ms.openlocfilehash: 7d23230ebe4321f355128d1f3268e967a35a0a89
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245646"
---
# <a name="learn-about-sensitive-information-types"></a><span data-ttu-id="caee6-102">Meer informatie over typen gevoelige informatie</span><span class="sxs-lookup"><span data-stu-id="caee6-102">Learn about sensitive information types</span></span>

<span data-ttu-id="caee6-103">Het identificeren en classificeren van gevoelige items die onder uw organisatiebeheer vallen, is de eerste stap in de [discipline Informatiebeveiliging.](./information-protection.md)</span><span class="sxs-lookup"><span data-stu-id="caee6-103">Identifying and classifying sensitive items that are under your organizations control is the first step in the [Information Protection discipline](./information-protection.md).</span></span>  <span data-ttu-id="caee6-104">Microsoft 365 biedt drie manieren om items te identificeren, zodat ze kunnen worden geclassificeerd:</span><span class="sxs-lookup"><span data-stu-id="caee6-104">Microsoft 365 provides three ways of identifying items so that they can be classified:</span></span>

- <span data-ttu-id="caee6-105">handmatig door gebruikers</span><span class="sxs-lookup"><span data-stu-id="caee6-105">manually by users</span></span>
- <span data-ttu-id="caee6-106">geautomatiseerde patroonherkenning, zoals gevoelige informatietypen</span><span class="sxs-lookup"><span data-stu-id="caee6-106">automated pattern recognition, like sensitive information types</span></span>
- [<span data-ttu-id="caee6-107">machine learning</span><span class="sxs-lookup"><span data-stu-id="caee6-107">machine learning</span></span>](classifier-learn-about.md)

<span data-ttu-id="caee6-108">Gevoelige informatietypen zijn classificaties op basis van patronen.</span><span class="sxs-lookup"><span data-stu-id="caee6-108">Sensitive information types are pattern-based classifiers.</span></span> <span data-ttu-id="caee6-109">Ze detecteren gevoelige informatie, zoals sociale zekerheid, creditcard- of bankrekeningnummers om gevoelige items te identificeren, zie Definities van [entiteitstypen gevoelige informatie](sensitive-information-type-entity-definitions.md)</span><span class="sxs-lookup"><span data-stu-id="caee6-109">They detect sensitive information like social security, credit card, or bank account numbers to identify sensitive items, see [Sensitive information types entity definitions](sensitive-information-type-entity-definitions.md)</span></span>

## <a name="sensitive-information-types-are-used-in"></a><span data-ttu-id="caee6-110">Gevoelige informatietypen worden gebruikt in</span><span class="sxs-lookup"><span data-stu-id="caee6-110">Sensitive information types are used in</span></span>

- [<span data-ttu-id="caee6-111">Preventiebeleid voor gegevensverlies</span><span class="sxs-lookup"><span data-stu-id="caee6-111">Data loss prevention policies</span></span>](dlp-learn-about-dlp.md) 
- [<span data-ttu-id="caee6-112">Gevoeligheidslabels</span><span class="sxs-lookup"><span data-stu-id="caee6-112">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="caee6-113">Bewaarlabels</span><span class="sxs-lookup"><span data-stu-id="caee6-113">Retention labels</span></span>](retention.md)
- [<span data-ttu-id="caee6-114">Insider-risicobeheer</span><span class="sxs-lookup"><span data-stu-id="caee6-114">Insider risk management</span></span>](insider-risk-management.md)
- [<span data-ttu-id="caee6-115">Communicatiecompliance</span><span class="sxs-lookup"><span data-stu-id="caee6-115">Communication compliance</span></span>](communication-compliance.md)
- [<span data-ttu-id="caee6-116">Beleid voor automatisch labelen</span><span class="sxs-lookup"><span data-stu-id="caee6-116">Auto-labelling policies</span></span>](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps)

## <a name="fundamental-parts-of-a-sensitive-information-type"></a><span data-ttu-id="caee6-117">Basisonderdelen van een type gevoelige informatie</span><span class="sxs-lookup"><span data-stu-id="caee6-117">Fundamental parts of a sensitive information type</span></span>

<span data-ttu-id="caee6-118">Elke entiteit van het type gevoelige informatie wordt gedefinieerd door deze velden:</span><span class="sxs-lookup"><span data-stu-id="caee6-118">Every sensitive information type entity is defined by these fields:</span></span>

- <span data-ttu-id="caee6-119">naam: de manier waarop naar het type gevoelige informatie wordt verwezen</span><span class="sxs-lookup"><span data-stu-id="caee6-119">name: how the sensitive information type is referred to</span></span>
- <span data-ttu-id="caee6-120">beschrijving: beschrijft wat het type gevoelige informatie zoekt</span><span class="sxs-lookup"><span data-stu-id="caee6-120">description: describes what the sensitive information type is looking for</span></span>
- <span data-ttu-id="caee6-121">patroon: Een patroon definieert wat een gevoelige informatietype detecteert.</span><span class="sxs-lookup"><span data-stu-id="caee6-121">pattern: A pattern defines what a sensitive information type detects.</span></span> <span data-ttu-id="caee6-122">Deze bestaat uit de volgende onderdelen</span><span class="sxs-lookup"><span data-stu-id="caee6-122">It consists of the following components</span></span>
    - <span data-ttu-id="caee6-123">Primair element: het hoofdelement dat het gevoelige informatietype zoekt.</span><span class="sxs-lookup"><span data-stu-id="caee6-123">Primary element – the main element that the sensitive information type is looking for.</span></span> <span data-ttu-id="caee6-124">Het kan een normale **expressie zijn** met of zonder een checksumvalidatie, een **trefwoordlijst,** een woordenlijst **met** trefwoorden of een **functie.**</span><span class="sxs-lookup"><span data-stu-id="caee6-124">It can be a **regular expression** with or without a checksum validation, a **keyword list**, a **keyword dictionary**, or a **function**.</span></span>
    - <span data-ttu-id="caee6-125">Ondersteunend element: elementen die fungeren als ondersteunend bewijs om het vertrouwen van de overeenkomst te vergroten.</span><span class="sxs-lookup"><span data-stu-id="caee6-125">Supporting element – elements that act as supporting evidence that help in increasing the confidence of the match.</span></span> <span data-ttu-id="caee6-126">Trefwoord 'SSN' bijvoorbeeld in de nabijheid van een SSN-getal.</span><span class="sxs-lookup"><span data-stu-id="caee6-126">For example, keyword “SSN” in proximity of an SSN number.</span></span> <span data-ttu-id="caee6-127">Het kan een normale expressie zijn met of zonder een checksumvalidatie, trefwoordlijst, trefwoordwoordenlijst.</span><span class="sxs-lookup"><span data-stu-id="caee6-127">It can be a regular expression with or without a checksum validation, keyword list, keyword dictionary.</span></span>
    - <span data-ttu-id="caee6-128">Betrouwbaarheidsniveau: betrouwbaarheidsniveaus (hoog, gemiddeld, laag) geven aan hoeveel ondersteunend bewijs samen met het primaire element is gevonden.</span><span class="sxs-lookup"><span data-stu-id="caee6-128">Confidence Level - Confidence levels (high, medium, low) reflect how much supporting evidence was detected along with the primary element.</span></span> <span data-ttu-id="caee6-129">Hoe meer ondersteunend bewijs een item bevat, hoe groter het vertrouwen dat een overeenkomend item de gevoelige informatie bevat die u zoekt.</span><span class="sxs-lookup"><span data-stu-id="caee6-129">The more supporting evidence an item contains, the higher the confidence that a matched item contains the sensitive info you're looking for.</span></span>
    - <span data-ttu-id="caee6-130">Nabijheid: aantal tekens tussen primair en ondersteunend element</span><span class="sxs-lookup"><span data-stu-id="caee6-130">Proximity – Number of characters between primary and supporting element</span></span>

![Diagram van bevestigend bewijs en nabijheidsvenster](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

<span data-ttu-id="caee6-132">Meer informatie over betrouwbaarheidsniveaus in deze video</span><span class="sxs-lookup"><span data-stu-id="caee6-132">Learn more about confidence levels in this video</span></span>


 > [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Hx60]  

### <a name="example-sensitive-information-type"></a><span data-ttu-id="caee6-133">Voorbeeld van het type gevoelige informatie</span><span class="sxs-lookup"><span data-stu-id="caee6-133">Example sensitive information type</span></span>


## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="caee6-134">Argentinië national identity (DNI) number</span><span class="sxs-lookup"><span data-stu-id="caee6-134">Argentina national identity (DNI) number</span></span>

### <a name="format"></a><span data-ttu-id="caee6-135">Opmaak</span><span class="sxs-lookup"><span data-stu-id="caee6-135">Format</span></span>

<span data-ttu-id="caee6-136">Acht cijfers gescheiden door perioden</span><span class="sxs-lookup"><span data-stu-id="caee6-136">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="caee6-137">Patroon</span><span class="sxs-lookup"><span data-stu-id="caee6-137">Pattern</span></span>

<span data-ttu-id="caee6-138">Acht cijfers:</span><span class="sxs-lookup"><span data-stu-id="caee6-138">Eight digits:</span></span>
- <span data-ttu-id="caee6-139">twee cijfers</span><span class="sxs-lookup"><span data-stu-id="caee6-139">two digits</span></span>
- <span data-ttu-id="caee6-140">een punt</span><span class="sxs-lookup"><span data-stu-id="caee6-140">a period</span></span>
- <span data-ttu-id="caee6-141">drie cijfers</span><span class="sxs-lookup"><span data-stu-id="caee6-141">three digits</span></span>
- <span data-ttu-id="caee6-142">een punt</span><span class="sxs-lookup"><span data-stu-id="caee6-142">a period</span></span>
- <span data-ttu-id="caee6-143">drie cijfers</span><span class="sxs-lookup"><span data-stu-id="caee6-143">three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="caee6-144">Checksum</span><span class="sxs-lookup"><span data-stu-id="caee6-144">Checksum</span></span>

<span data-ttu-id="caee6-145">Nee</span><span class="sxs-lookup"><span data-stu-id="caee6-145">No</span></span>

### <a name="definition"></a><span data-ttu-id="caee6-146">Definitie</span><span class="sxs-lookup"><span data-stu-id="caee6-146">Definition</span></span>

<span data-ttu-id="caee6-147">Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:</span><span class="sxs-lookup"><span data-stu-id="caee6-147">A DLP policy has medium confidence that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="caee6-148">De normale expressie Regex_argentina_national_id inhoud die overeenkomt met het patroon.</span><span class="sxs-lookup"><span data-stu-id="caee6-148">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="caee6-149">Er wordt een trefwoord Keyword_argentina_national_id gevonden.</span><span class="sxs-lookup"><span data-stu-id="caee6-149">A keyword from Keyword_argentina_national_id is found.</span></span>

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="caee6-150">Trefwoorden</span><span class="sxs-lookup"><span data-stu-id="caee6-150">Keywords</span></span>

#### <a name="keyword_argentina_national_id"></a><span data-ttu-id="caee6-151">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="caee6-151">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="caee6-152">Nationale identiteitsnummer argentinië</span><span class="sxs-lookup"><span data-stu-id="caee6-152">Argentina National Identity number</span></span> 
- <span data-ttu-id="caee6-153">Identiteit</span><span class="sxs-lookup"><span data-stu-id="caee6-153">Identity</span></span> 
- <span data-ttu-id="caee6-154">Identificatie nationale identiteitskaart</span><span class="sxs-lookup"><span data-stu-id="caee6-154">Identification National Identity Card</span></span> 
- <span data-ttu-id="caee6-155">DNI</span><span class="sxs-lookup"><span data-stu-id="caee6-155">DNI</span></span> 
- <span data-ttu-id="caee6-156">NIC National Registry of Persons</span><span class="sxs-lookup"><span data-stu-id="caee6-156">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="caee6-157">Documento Nacional de Identidad</span><span class="sxs-lookup"><span data-stu-id="caee6-157">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="caee6-158">Registro Nacional de las Personas</span><span class="sxs-lookup"><span data-stu-id="caee6-158">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="caee6-159">Identidad</span><span class="sxs-lookup"><span data-stu-id="caee6-159">Identidad</span></span> 
- <span data-ttu-id="caee6-160">Identificación</span><span class="sxs-lookup"><span data-stu-id="caee6-160">Identificación</span></span> 

### <a name="more-on-confidence-levels"></a><span data-ttu-id="caee6-161">Meer informatie over betrouwbaarheidsniveaus</span><span class="sxs-lookup"><span data-stu-id="caee6-161">More on confidence levels</span></span>

<span data-ttu-id="caee6-162">In een entiteitsdefinitie van het type gevoelige informatie **geeft** betrouwbaarheidsniveau aan hoeveel ondersteunend bewijs wordt gedetecteerd naast het primaire element.</span><span class="sxs-lookup"><span data-stu-id="caee6-162">In a sensitive information type entity definition, **confidence level** reflects how much supporting evidence is detected in addition to the primary element.</span></span> <span data-ttu-id="caee6-163">Hoe meer ondersteunend bewijs een item bevat, hoe groter het vertrouwen dat een overeenkomend item de gevoelige informatie bevat die u zoekt.</span><span class="sxs-lookup"><span data-stu-id="caee6-163">The more supporting evidence an item contains, the higher the confidence that a matched item contains the sensitive info you're looking for.</span></span> <span data-ttu-id="caee6-164">Overeenkomsten met een hoog betrouwbaarheidsniveau bevatten bijvoorbeeld meer ondersteunend bewijs in de nabijheid van het primaire element, terwijl overeenkomsten met een laag betrouwbaarheidsniveau in de nabijheid weinig tot geen ondersteunend bewijs bevatten.</span><span class="sxs-lookup"><span data-stu-id="caee6-164">For example, matches with a high confidence level will contain more supporting evidence in close proximity of the primary element, whereas matches with a low confidence level would contain little to no supporting evidence in close proximity.</span></span> 

<span data-ttu-id="caee6-165">Een hoog betrouwbaarheidsniveau retourneert de minste onwaar-positieven, maar kan leiden tot meer onwaar negatieven.</span><span class="sxs-lookup"><span data-stu-id="caee6-165">A high confidence level returns the fewest false positives but might result in more false negatives.</span></span> <span data-ttu-id="caee6-166">Lage of gemiddelde betrouwbaarheidsniveaus retourneert meer onwaar-positieve waarden, maar weinig tot nul onwaar negatieven.</span><span class="sxs-lookup"><span data-stu-id="caee6-166">Low or medium confidence levels returns more false positives but few to zero false negatives.</span></span>

- <span data-ttu-id="caee6-167">**weinig vertrouwen:** waarde van 65, overeenkomende items bevat de minste onwaar negatieven, maar de meeste onwaar positieven.</span><span class="sxs-lookup"><span data-stu-id="caee6-167">**low confidence**: Value of 65, matched items will contain the fewest false negatives but the most false positives.</span></span> <span data-ttu-id="caee6-168">Lage betrouwbaarheid retourneert alle overeenkomsten met lage, gemiddelde en hoge betrouwbaarheid.</span><span class="sxs-lookup"><span data-stu-id="caee6-168">Low confidence returns all low, medium, and high confidence matches.</span></span>
- <span data-ttu-id="caee6-169">**gemiddeld vertrouwen:** waarde van 75, overeenkomende items bevat een gemiddelde hoeveelheid onwaar-positieven en onwaar negatieven.</span><span class="sxs-lookup"><span data-stu-id="caee6-169">**medium confidence**: Value of 75, matched items will contain an average amount of false positives and false negatives.</span></span> <span data-ttu-id="caee6-170">Gemiddeld vertrouwen retourneert alle gemiddelde en hoge betrouwbaarheids matches.</span><span class="sxs-lookup"><span data-stu-id="caee6-170">Medium confidence returns all medium, and high confidence matches.</span></span>  
- <span data-ttu-id="caee6-171">**hoog vertrouwen:** waarde van 85, overeenkomende items bevat de minste onwaar-positieven, maar de meeste onwaar negatieven.</span><span class="sxs-lookup"><span data-stu-id="caee6-171">**high confidence**: Value of 85, matched items will contain the fewest false positives but the most false negatives.</span></span> <span data-ttu-id="caee6-172">Hoog vertrouwen geeft alleen overeenkomsten met hoog vertrouwen als rendement.</span><span class="sxs-lookup"><span data-stu-id="caee6-172">High confidence only returns high confidence matches.</span></span>  

<span data-ttu-id="caee6-173">Gebruik patronen met een hoog betrouwbaarheidsniveau met lage tellingen, bijvoorbeeld vijf tot tien, en lage betrouwbaarheidspatronen met hogere tellingen, bijvoorbeeld 20 of meer.</span><span class="sxs-lookup"><span data-stu-id="caee6-173">You should use high confidence level patterns with low counts, say five to ten, and low confidence patterns with higher counts, say 20 or more.</span></span>

> [!NOTE]
> <span data-ttu-id="caee6-174">Als u bestaande beleidsregels of aangepaste gevoelige informatietypen (SIT's) hebt gedefinieerd met behulp van betrouwbaarheidsniveaus op basis van een getal (ook bekend als nauwkeurigheid), worden deze automatisch aan de drie afzonderlijke betrouwbaarheidsniveaus toegesneden. weinig vertrouwen, gemiddeld vertrouwen en veel vertrouwen in de gebruikersinterface van het Beveiligings- en compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="caee6-174">If you have existing policies or custom sensitive information types (SITs) defined using number-based confidence levels (also know as accuracy), they will automatically be mapped to the three discrete confidence levels; low confidence, medium confidence, and high confidence, across the Security @ Compliance Center UI.</span></span>
> - <span data-ttu-id="caee6-175">Alle beleidsregels met minimale nauwkeurigheid of aangepaste SIT-patronen met betrouwbaarheidsniveaus tussen 76 en 100 worden in kaart gebracht op hoog vertrouwen.</span><span class="sxs-lookup"><span data-stu-id="caee6-175">All policies with minimum accuracy or custom SIT patterns with confidence levels of between 76 and 100 will be mapped to high confidence.</span></span> 
> - <span data-ttu-id="caee6-176">Alle beleidsregels met minimale nauwkeurigheid of aangepaste SIT-patronen met betrouwbaarheidsniveaus tussen 66 en 75 worden in kaart gebracht op gemiddeld vertrouwen.</span><span class="sxs-lookup"><span data-stu-id="caee6-176">All policies with minimum accuracy or custom SIT patterns with confidence levels of between 66 and 75 will be mapped to medium confidence.</span></span>
> - <span data-ttu-id="caee6-177">Alle beleidsregels met minimale nauwkeurigheid of aangepaste SIT-patronen met betrouwbaarheidsniveaus kleiner dan of gelijk aan 65, worden in kaart gebracht aan lage betrouwbaarheid.</span><span class="sxs-lookup"><span data-stu-id="caee6-177">All policies with minimum accuracy or custom SIT patterns with confidence levels less than or equal to 65 will be mapped to low confidence.</span></span> 

## <a name="creating-custom-sensitive-information-types"></a><span data-ttu-id="caee6-178">Aangepaste gevoelige informatietypen maken</span><span class="sxs-lookup"><span data-stu-id="caee6-178">Creating custom sensitive information types</span></span>

<span data-ttu-id="caee6-179">Als u aangepaste gevoelige informatietypen wilt maken in het beveiligings- & compliancecentrum, kunt u kiezen uit verschillende opties:</span><span class="sxs-lookup"><span data-stu-id="caee6-179">To create custom sensitive information types in the Security & Compliance Center, you can choose from several options:</span></span>

- <span data-ttu-id="caee6-180">**De gebruikersinterface gebruiken** U kunt een aangepast type gevoelige informatie instellen met behulp van de gebruikersinterface & compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="caee6-180">**Use the UI** You can set up a custom sensitive information type using the Security & Compliance Center UI.</span></span> <span data-ttu-id="caee6-181">Met deze methode kunt u gewone expressies, trefwoorden en woordenlijsten voor trefwoorden gebruiken.</span><span class="sxs-lookup"><span data-stu-id="caee6-181">With this method, you can use regular expressions, keywords, and keyword dictionaries.</span></span> <span data-ttu-id="caee6-182">Zie Een aangepast type gevoelige informatie maken voor [meer informatie.](create-a-custom-sensitive-information-type.md)</span><span class="sxs-lookup"><span data-stu-id="caee6-182">To learn more, see [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md).</span></span>

- <span data-ttu-id="caee6-183">**EDM gebruiken** U kunt aangepaste gevoelige informatietypen instellen met de classificatie Exact Data Match (EDM).</span><span class="sxs-lookup"><span data-stu-id="caee6-183">**Use EDM** You can set up custom sensitive information types using Exact Data Match (EDM)-based classification.</span></span> <span data-ttu-id="caee6-184">Met deze methode kunt u een dynamisch type gevoelige informatie maken met behulp van een beveiligde database die u regelmatig kunt vernieuwen.</span><span class="sxs-lookup"><span data-stu-id="caee6-184">This method enables you to create a dynamic sensitive information type using a secure database that you can refresh periodically.</span></span> <span data-ttu-id="caee6-185">Zie [Een aangepast type gevoelige informatie maken met de classificatie Exacte gegevensmatch.](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)</span><span class="sxs-lookup"><span data-stu-id="caee6-185">See [Create a custom sensitive information type with Exact Data Match based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

- <span data-ttu-id="caee6-186">**PowerShell gebruiken** U kunt aangepaste gevoelige informatietypen instellen met PowerShell.</span><span class="sxs-lookup"><span data-stu-id="caee6-186">**Use PowerShell** You can set up custom sensitive information types using PowerShell.</span></span> <span data-ttu-id="caee6-187">Hoewel deze methode complexer is dan het gebruikersinterface, hebt u meer configuratieopties.</span><span class="sxs-lookup"><span data-stu-id="caee6-187">Although this method is more complex than using the UI, you have more configuration options.</span></span> <span data-ttu-id="caee6-188">Zie [Een aangepast type gevoelige informatie maken in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="caee6-188">See [Create a custom sensitive information type in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span>



> [!NOTE]
> <span data-ttu-id="caee6-189">Verbeterde betrouwbaarheidsniveaus zijn beschikbaar voor direct gebruik in preventie van gegevensverlies voor Microsoft 365-services, Microsoft Information Protection voor Microsoft 365-services, Communicatie compliance, informatiebeheer en recordsbeheer.</span><span class="sxs-lookup"><span data-stu-id="caee6-189">Improved confidence levels are available for immediate use within Data Loss Prevention for Microsoft 365 services, Microsoft Information Protection for Microsoft 365 services, Communication Compliance, Information Governance, and Records Management.</span></span>

> <span data-ttu-id="caee6-190">Microsoft 365 Information Protection ondersteunt nu in voorbeeldtalen voor dubbele bytetekensets voor:</span><span class="sxs-lookup"><span data-stu-id="caee6-190">Microsoft 365 Information Protection now  supports in preview double byte character set languages for:</span></span>
> - <span data-ttu-id="caee6-191">Chinees (vereenvoudigd)</span><span class="sxs-lookup"><span data-stu-id="caee6-191">Chinese (simplified)</span></span>
> - <span data-ttu-id="caee6-192">Chinees (traditioneel)</span><span class="sxs-lookup"><span data-stu-id="caee6-192">Chinese (traditional)</span></span>
> - <span data-ttu-id="caee6-193">Koreaans</span><span class="sxs-lookup"><span data-stu-id="caee6-193">Korean</span></span>
> - <span data-ttu-id="caee6-194">Japans</span><span class="sxs-lookup"><span data-stu-id="caee6-194">Japanese</span></span>

><span data-ttu-id="caee6-195">Deze ondersteuning is beschikbaar voor gevoelige informatietypen.</span><span class="sxs-lookup"><span data-stu-id="caee6-195">This support is available for sensitive information types.</span></span> <span data-ttu-id="caee6-196">Zie [Informatiebeveiligingsondersteuning voor dubbele bytetekensets releasenotities (preview)](mip-dbcs-relnotes.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="caee6-196">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>

## <a name="for-further-information"></a><span data-ttu-id="caee6-197">Voor meer informatie</span><span class="sxs-lookup"><span data-stu-id="caee6-197">For further information</span></span>
- [<span data-ttu-id="caee6-198">Definities van entiteiten van het type Gevoelige informatie</span><span class="sxs-lookup"><span data-stu-id="caee6-198">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="caee6-199">Een aangepast type gevoelige informatie maken</span><span class="sxs-lookup"><span data-stu-id="caee6-199">Create a custom sensitive information type</span></span>](create-a-custom-sensitive-information-type.md)
- [<span data-ttu-id="caee6-200">Een aangepast type gevoelige informatie maken in PowerShell</span><span class="sxs-lookup"><span data-stu-id="caee6-200">Create a custom sensitive information type in PowerShell</span></span>](create-a-custom-sensitive-information-type-in-scc-powershell.md)

<span data-ttu-id="caee6-201">Zie Informatiebeveiliging implementeren voor privacyregels voor gegevens met [](../solutions/information-protection-deploy.md) Microsoft 365 (aka.ms/m365dataprivacy).</span><span class="sxs-lookup"><span data-stu-id="caee6-201">To learn how to use sensitive information types to comply with data privacy regulations, see [Deploy information protection for data privacy regulations with Microsoft 365](../solutions/information-protection-deploy.md)  (aka.ms/m365dataprivacy).</span></span>

<!-- fwlink for this topic https://go.microsoft.com/fwlink/?linkid=2135644-->