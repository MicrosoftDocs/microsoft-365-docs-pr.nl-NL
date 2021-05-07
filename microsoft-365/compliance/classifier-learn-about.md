---
title: Meer informatie over trainbare classificaties
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Een Microsoft 365 trainable classifier is een hulpmiddel dat u kunt trainen om verschillende soorten inhoud te herkennen door deze positieve en negatieve voorbeelden te geven om naar te kijken. Nadat de classificatie is opgeleid, bevestigt u dat de resultaten juist zijn. Vervolgens gebruikt u deze om de inhoud van uw organisatie te doorzoeken en te classificeren om bewaar- of gevoeligheidslabels toe te passen of op te nemen in het preventiebeleid voor gegevensverlies (DLP) of bewaarbeleid.
ms.openlocfilehash: 1881e4de87fd41f21bb1f2236d46391b3a1ed785
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/30/2021
ms.locfileid: "52162888"
---
# <a name="learn-about-trainable-classifiers"></a><span data-ttu-id="decf8-105">Meer informatie over trainbare classificaties</span><span class="sxs-lookup"><span data-stu-id="decf8-105">Learn about trainable classifiers</span></span>

<span data-ttu-id="decf8-106">Het classificeren en labelen van inhoud, zodat deze op de juiste manier kan worden beveiligd en verwerkt, is de beginplaats voor de informatiebeveiligingsdiscipline.</span><span class="sxs-lookup"><span data-stu-id="decf8-106">Classifying and labeling content so it can be protected and handled properly is the starting place for the information protection discipline.</span></span> <span data-ttu-id="decf8-107">Microsoft 365 heeft drie manieren om inhoud te classificeren.</span><span class="sxs-lookup"><span data-stu-id="decf8-107">Microsoft 365 has three ways to classify content.</span></span>

## <a name="manually"></a><span data-ttu-id="decf8-108">Handmatig</span><span class="sxs-lookup"><span data-stu-id="decf8-108">Manually</span></span>

<span data-ttu-id="decf8-109">Voor deze methode zijn menselijke beoordeling en actie vereist.</span><span class="sxs-lookup"><span data-stu-id="decf8-109">This method requires human judgment and action.</span></span> <span data-ttu-id="decf8-110">Een beheerder kan de bestaande etiketten en gevoelige informatietypen gebruiken of een eigen label maken en vervolgens publiceren.</span><span class="sxs-lookup"><span data-stu-id="decf8-110">An admin may either use the pre-existing labels and sensitive information types or create their own and then publish them.</span></span> <span data-ttu-id="decf8-111">Gebruikers en beheerders passen deze toe op inhoud wanneer ze deze tegenkomen.</span><span class="sxs-lookup"><span data-stu-id="decf8-111">Users and admins apply them to content as they encounter it.</span></span> <span data-ttu-id="decf8-112">Vervolgens kunt u de inhoud beveiligen en de positie ervan beheren.</span><span class="sxs-lookup"><span data-stu-id="decf8-112">You can then protect the content and manage its disposition.</span></span>

## <a name="automated-pattern-matching"></a><span data-ttu-id="decf8-113">Automatische patroonmatching</span><span class="sxs-lookup"><span data-stu-id="decf8-113">Automated pattern matching</span></span>

<span data-ttu-id="decf8-114">Deze categorie classificatiemechanismen omvat het vinden van inhoud door:</span><span class="sxs-lookup"><span data-stu-id="decf8-114">This category of classification mechanisms include finding content by:</span></span>

- <span data-ttu-id="decf8-115">Trefwoorden of metagegevenswaarden (trefwoordquerytaal).</span><span class="sxs-lookup"><span data-stu-id="decf8-115">Keywords or metadata values (keyword query language).</span></span>
- <span data-ttu-id="decf8-116">Gebruik eerder geïdentificeerde patronen van gevoelige informatie, zoals sociale zekerheid, creditcard- of bankrekeningnummers [(definities van entiteitsdefinities van het type Gevoelige informatie).](sensitive-information-type-entity-definitions.md)</span><span class="sxs-lookup"><span data-stu-id="decf8-116">Using previously identified patterns of sensitive information like social security, credit card or bank account numbers [(Sensitive information type entity definitions)](sensitive-information-type-entity-definitions.md).</span></span>
- <span data-ttu-id="decf8-117">Een item herkennen omdat het een variatie is op een sjabloon [(afdrukken met documentvinger)](document-fingerprinting.md).</span><span class="sxs-lookup"><span data-stu-id="decf8-117">Recognizing an item because it's a variation on a template [(document finger printing)](document-fingerprinting.md).</span></span>
- <span data-ttu-id="decf8-118">Gebruik de aanwezigheid van exacte tekenreeksen [(exacte gegevens overeenkomen)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span><span class="sxs-lookup"><span data-stu-id="decf8-118">Using the presence of exact strings [(exact data match)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

<span data-ttu-id="decf8-119">Gevoeligheids- en bewaarlabels kunnen vervolgens automatisch worden toegepast om de inhoud beschikbaar te maken [voor](dlp-learn-about-dlp.md)gebruik in Meer informatie over preventie van gegevensverlies) en om automatisch de politie voor bewaarlabels toe [te passen.](apply-retention-labels-automatically.md)</span><span class="sxs-lookup"><span data-stu-id="decf8-119">Sensitivity and retention labels can then be automatically applied to make the content available for use in [Learn about data loss prevention](dlp-learn-about-dlp.md)) and [auto-apply polices for retention labels](apply-retention-labels-automatically.md).</span></span>

## <a name="classifiers"></a><span data-ttu-id="decf8-120">Classificaties</span><span class="sxs-lookup"><span data-stu-id="decf8-120">Classifiers</span></span>

<span data-ttu-id="decf8-121">Deze classificatiemethode is met name geschikt voor inhoud die niet gemakkelijk kan worden geïdentificeerd met de handmatige of geautomatiseerde methoden voor het koppelen van patronen.</span><span class="sxs-lookup"><span data-stu-id="decf8-121">This classification method is particularly well suited to content that isn't easily identified by either the manual or automated pattern matching methods.</span></span> <span data-ttu-id="decf8-122">Deze classificatiemethode heeft meer te maken met het trainen van een classificatie om een item te identificeren op basis van wat het item is, niet door elementen in het item (patroonmatching).</span><span class="sxs-lookup"><span data-stu-id="decf8-122">This method of classification is more about training a classifier to identify an item based on what the item is, not by elements that are in the item (pattern matching).</span></span> <span data-ttu-id="decf8-123">Een classificatie leert hoe u een type inhoud kunt identificeren door honderden voorbeelden te bekijken van de inhoud die u wilt classificeren.</span><span class="sxs-lookup"><span data-stu-id="decf8-123">A classifier learns how to identify a type of content by looking at hundreds of examples of the content you're interested in classifying.</span></span> <span data-ttu-id="decf8-124">U begint met het geven van voorbeelden die zeker in de categorie staan.</span><span class="sxs-lookup"><span data-stu-id="decf8-124">You start by feeding it examples that are definitely in the category.</span></span> <span data-ttu-id="decf8-125">Wanneer deze zijn verwerkt, test u deze door een combinatie te maken van zowel overeenkomende als niet-overeenkomende voorbeelden.</span><span class="sxs-lookup"><span data-stu-id="decf8-125">Once it processes those, you test it by giving it a mix of both matching and non-matching examples.</span></span> <span data-ttu-id="decf8-126">In de classificatie wordt vervolgens voorspeld of een bepaald item in de categorie valt die u maakt.</span><span class="sxs-lookup"><span data-stu-id="decf8-126">The classifier then makes predictions as to whether any given item falls into the category you're building.</span></span> <span data-ttu-id="decf8-127">Vervolgens bevestigt u de resultaten en sorteert u de waar positieven, waar negatieven, onwaar-positieven en onwaar negatieven om de nauwkeurigheid van de voorspellingen te vergroten.</span><span class="sxs-lookup"><span data-stu-id="decf8-127">You then confirm its results, sorting out the true positives, true negatives, false positives, and false negatives to help increase the accuracy of its predictions.</span></span> 

<span data-ttu-id="decf8-128">Wanneer u de classificatie publiceert, worden items gesorteerd op locaties zoals SharePoint Online, Exchange en OneDrive en classificeert u de inhoud.</span><span class="sxs-lookup"><span data-stu-id="decf8-128">When you publish the classifier, it sorts through items in locations like SharePoint Online, Exchange, and OneDrive, and classifies the content.</span></span> <span data-ttu-id="decf8-129">Nadat u de classificatie hebt gepubliceerd, kunt u deze blijven trainen met behulp van een feedbackproces dat lijkt op het eerste trainingsproces.</span><span class="sxs-lookup"><span data-stu-id="decf8-129">After you publish the classifier, you can continue to train it using a feedback process that is similar to the initial training process.</span></span>

### <a name="where-you-can-use-trainable-classifiers"></a><span data-ttu-id="decf8-130">Waar u trainbare classificaties kunt gebruiken</span><span class="sxs-lookup"><span data-stu-id="decf8-130">Where you can use trainable classifiers</span></span>
<span data-ttu-id="decf8-131">Zowel ingebouwde classificaties als trainbare classificaties zijn beschikbaar als voorwaarde voor [Office autolabeling](apply-sensitivity-label-automatically.md)met gevoeligheidslabels, [](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) automatisch bewaarlabelbeleid toepassen op basis van een voorwaarde en [in](communication-compliance.md)communicatieconditie.</span><span class="sxs-lookup"><span data-stu-id="decf8-131">Both built-in classifiers and trainable classifiers are available as a condition for [Office autolabeling with sensitivity labels](apply-sensitivity-label-automatically.md), [auto-apply retention label policy based on a condition](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) and in [communication compliance](communication-compliance.md).</span></span> 

<span data-ttu-id="decf8-132">Gevoeligheidslabels kunnen classificaties gebruiken als voorwaarden, zie [Een gevoeligheidslabel](apply-sensitivity-label-automatically.md)automatisch toepassen op inhoud.</span><span class="sxs-lookup"><span data-stu-id="decf8-132">Sensitivity labels can use classifiers as conditions, see [Apply a sensitivity label to content automatically](apply-sensitivity-label-automatically.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="decf8-133">Classificaties werken alleen met items die niet zijn versleuteld en in het Engels zijn.</span><span class="sxs-lookup"><span data-stu-id="decf8-133">Classifiers only work with items that are not encrypted and are in English.</span></span>

## <a name="types-of-classifiers"></a><span data-ttu-id="decf8-134">Typen classificaties</span><span class="sxs-lookup"><span data-stu-id="decf8-134">Types of classifiers</span></span>

- <span data-ttu-id="decf8-135">**vooraf getrainde classificaties:** Microsoft heeft een aantal classificaties gemaakt en vooraf opgeleid die u kunt gebruiken zonder ze te trainen.</span><span class="sxs-lookup"><span data-stu-id="decf8-135">**pre-trained classifiers** - Microsoft has created and pre-trained a number of classifiers that you can start using without training them.</span></span> <span data-ttu-id="decf8-136">Deze classificaties worden weergegeven met de status `Ready to use` van .</span><span class="sxs-lookup"><span data-stu-id="decf8-136">These classifiers will appear with the status of `Ready to use`.</span></span>
- <span data-ttu-id="decf8-137">**aangepaste classificaties:** als u classificatiebehoeften hebt die verder gaan dan wat de vooraf getrainde classificaties dekken, kunt u uw eigen classificaties maken en trainen.</span><span class="sxs-lookup"><span data-stu-id="decf8-137">**custom classifiers** - If you have classification needs that extend beyond what the pre-trained classifiers cover, you can create and train your own classifiers.</span></span>

### <a name="pre-trained-classifiers"></a><span data-ttu-id="decf8-138">Vooraf getrainde classificaties</span><span class="sxs-lookup"><span data-stu-id="decf8-138">Pre-trained classifiers</span></span>

<span data-ttu-id="decf8-139">Microsoft 365 wordt geleverd met vijf vooraf getrainde classificaties:</span><span class="sxs-lookup"><span data-stu-id="decf8-139">Microsoft 365 comes with five pre-trained classifiers:</span></span>

> [!CAUTION]
> <span data-ttu-id="decf8-140">De vooraf getrainde  classificatie voor aanstootgevende taal wordt afgeschaft omdat er een groot aantal fout-positieven is geproduceerd.</span><span class="sxs-lookup"><span data-stu-id="decf8-140">We are deprecating the **Offensive Language** pre-trained classifier because it has been producing a high number of false positives.</span></span> <span data-ttu-id="decf8-141">Gebruik deze niet en als u het momenteel gebruikt, moet u uw bedrijfsprocessen ervan af zetten.</span><span class="sxs-lookup"><span data-stu-id="decf8-141">Don't use it and if you are currently using it, you should move your business processes off of it.</span></span> <span data-ttu-id="decf8-142">We raden u **aan** in plaats daarvan de vooraf **getrainde** classificaties Bedreiging, **Godslastering** en Pesterijen te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="decf8-142">We recommend using the **Threat**, **Profanity**, and **Harassment** pre-trained classifiers instead.</span></span>

- <span data-ttu-id="decf8-143">Cv's: detecteert items die tekstuele accounts zijn van persoonlijke, educatieve, professionele **kwalificaties,** werkervaring en andere persoonlijk identificeerbare gegevens van een sollicitant</span><span class="sxs-lookup"><span data-stu-id="decf8-143">**Resumes**: detects items that are textual accounts of an applicant's personal, educational, professional qualifications, work experience, and other personally identifying information</span></span>
- <span data-ttu-id="decf8-144">**Broncode:** detecteert items die een reeks instructies en instructies bevatten die zijn geschreven in de 25 meest gebruikte programmeertalen op GitHub</span><span class="sxs-lookup"><span data-stu-id="decf8-144">**Source Code**: detects items that contain a set of instructions and statements written in the top 25 used computer programming languages on GitHub</span></span>
    - <span data-ttu-id="decf8-145">ActionScript</span><span class="sxs-lookup"><span data-stu-id="decf8-145">ActionScript</span></span>
    - <span data-ttu-id="decf8-146">C</span><span class="sxs-lookup"><span data-stu-id="decf8-146">C</span></span>
    - <span data-ttu-id="decf8-147">C #</span><span class="sxs-lookup"><span data-stu-id="decf8-147">C#</span></span>
    - <span data-ttu-id="decf8-148">C++</span><span class="sxs-lookup"><span data-stu-id="decf8-148">C++</span></span>
    - <span data-ttu-id="decf8-149">Klaveren</span><span class="sxs-lookup"><span data-stu-id="decf8-149">Clojure</span></span>
    - <span data-ttu-id="decf8-150">CoffeeScript</span><span class="sxs-lookup"><span data-stu-id="decf8-150">CoffeeScript</span></span>
    - <span data-ttu-id="decf8-151">Ga</span><span class="sxs-lookup"><span data-stu-id="decf8-151">Go</span></span>
    - <span data-ttu-id="decf8-152">Haskell</span><span class="sxs-lookup"><span data-stu-id="decf8-152">Haskell</span></span>
    - <span data-ttu-id="decf8-153">Java</span><span class="sxs-lookup"><span data-stu-id="decf8-153">Java</span></span>
    - <span data-ttu-id="decf8-154">JavaScript</span><span class="sxs-lookup"><span data-stu-id="decf8-154">JavaScript</span></span>
    - <span data-ttu-id="decf8-155">Lua</span><span class="sxs-lookup"><span data-stu-id="decf8-155">Lua</span></span>
    - <span data-ttu-id="decf8-156">MATLAB</span><span class="sxs-lookup"><span data-stu-id="decf8-156">MATLAB</span></span>
    - <span data-ttu-id="decf8-157">Objective-C</span><span class="sxs-lookup"><span data-stu-id="decf8-157">Objective-C</span></span>
    - <span data-ttu-id="decf8-158">Perl</span><span class="sxs-lookup"><span data-stu-id="decf8-158">Perl</span></span>
    - <span data-ttu-id="decf8-159">PHP</span><span class="sxs-lookup"><span data-stu-id="decf8-159">PHP</span></span>
    - <span data-ttu-id="decf8-160">Python</span><span class="sxs-lookup"><span data-stu-id="decf8-160">Python</span></span>
    - <span data-ttu-id="decf8-161">R</span><span class="sxs-lookup"><span data-stu-id="decf8-161">R</span></span>
    - <span data-ttu-id="decf8-162">Ruby</span><span class="sxs-lookup"><span data-stu-id="decf8-162">Ruby</span></span>
    - <span data-ttu-id="decf8-163">Scala</span><span class="sxs-lookup"><span data-stu-id="decf8-163">Scala</span></span>
    - <span data-ttu-id="decf8-164">Shell</span><span class="sxs-lookup"><span data-stu-id="decf8-164">Shell</span></span>
    - <span data-ttu-id="decf8-165">Swift</span><span class="sxs-lookup"><span data-stu-id="decf8-165">Swift</span></span>
    - <span data-ttu-id="decf8-166">Tex</span><span class="sxs-lookup"><span data-stu-id="decf8-166">Tex</span></span>
    - <span data-ttu-id="decf8-167">Vim-script</span><span class="sxs-lookup"><span data-stu-id="decf8-167">Vim Script</span></span>

> [!NOTE]
> <span data-ttu-id="decf8-168">Broncode is opgeleid om te detecteren wanneer het grootste deel van de tekst broncode is.</span><span class="sxs-lookup"><span data-stu-id="decf8-168">Source Code is trained to detect when the bulk of the text is source code.</span></span> <span data-ttu-id="decf8-169">Er wordt geen broncodetekst gedetecteerd die wordt afgewisseld met tekst zonder tekst.</span><span class="sxs-lookup"><span data-stu-id="decf8-169">It does not detect source code text that is interspersed with plain text.</span></span>

- <span data-ttu-id="decf8-170">**Pesterijen:** detecteert een specifieke categorie aanstootgevende taaltekstitems met betrekking tot aanstootgevend gedrag dat is gericht op een of meer personen op basis van de volgende kenmerken: ras, etniciteit, religie, nationale origin, geslacht, seksuele oriëntatie, leeftijd, handicap</span><span class="sxs-lookup"><span data-stu-id="decf8-170">**Harassment**: detects a specific category of offensive language text items related to offensive conduct targeting one or multiple individuals based on the following traits: race, ethnicity, religion, national origin, gender, sexual orientation, age, disability</span></span>
- <span data-ttu-id="decf8-171">**Grof taalgebruik:** detecteert een specifieke categorie aanstootgevende taaltekstitems die expressies bevatten die de meeste mensen voor schut zetten</span><span class="sxs-lookup"><span data-stu-id="decf8-171">**Profanity**: detects a specific category of offensive language text items that contain expressions that embarrass most people</span></span>
- <span data-ttu-id="decf8-172">**Bedreiging:** detecteert een specifieke categorie aanstootgevende taaltekstitems met betrekking tot bedreigingen voor het plegen van geweld of fysieke schade aan een persoon of eigenschap</span><span class="sxs-lookup"><span data-stu-id="decf8-172">**Threat**: detects a specific category of offensive language text items related to threats to commit violence or do physical harm or damage to a person or property</span></span>

<span data-ttu-id="decf8-173">Deze worden weergegeven in **het Microsoft 365 weergave**  >  **Gegevensclassificatie**  >  **Trainable classifiers** met de status van `Ready to use` .</span><span class="sxs-lookup"><span data-stu-id="decf8-173">These appear in the **Microsoft 365 compliance center** > **Data classification** > **Trainable classifiers** view with the status of `Ready to use`.</span></span>

![classifiers-pre-trained-classifiers](../media/classifiers-ready-to-use-classifiers.png)

> [!IMPORTANT]
> <span data-ttu-id="decf8-175">Houd er rekening mee dat de aanstootgevende taal, pesterijen, grof taalgebruik en bedreigingsclassifiers alleen werken met doorzoekbare tekst, niet volledig of volledig zijn.</span><span class="sxs-lookup"><span data-stu-id="decf8-175">Please note that the offensive language, harassment, profanity, and threat classifiers only work with searchable text are not exhaustive or complete.</span></span>  <span data-ttu-id="decf8-176">Bovendien veranderen taal- en culturele standaarden voortdurend en in het licht van deze realiteit behoudt Microsoft zich het recht voor om deze classificaties naar eigen goed inzicht bij te werken.</span><span class="sxs-lookup"><span data-stu-id="decf8-176">Further, language and cultural standards continually change, and in light of these realities, Microsoft reserves the right to update these classifiers in its discretion.</span></span> <span data-ttu-id="decf8-177">Hoewel de classificaties uw organisatie kunnen helpen bij het controleren van aanstootgevende taal en andere taal die wordt gebruikt, hebben de classificaties geen aandacht voor de gevolgen van een dergelijke taal en zijn ze niet bedoeld om uw organisatie de enige manier te bieden om het gebruik van deze taal te controleren of te beantwoorden.</span><span class="sxs-lookup"><span data-stu-id="decf8-177">While the classifiers may assist your organization in monitoring offensive and other language used, the classifiers do not address consequences of such language and are not intended to provide your organization's sole means of monitoring or responding to the use of such language.</span></span> <span data-ttu-id="decf8-178">Uw organisatie, en niet Microsoft of haar dochterondernemingen, blijft verantwoordelijk voor alle beslissingen met betrekking tot het bewaken, afdwingen, blokkeren, verwijderen en bewaren van inhoud die is geïdentificeerd door een vooraf getrainde classificatie.</span><span class="sxs-lookup"><span data-stu-id="decf8-178">Your organization, and not Microsoft or its subsidiaries, remains responsible for all decisions related to monitoring, enforcement, blocking, removal and retention of any content identified by a pre-trained classifier.</span></span>

### <a name="custom-classifiers"></a><span data-ttu-id="decf8-179">Aangepaste classificaties</span><span class="sxs-lookup"><span data-stu-id="decf8-179">Custom classifiers</span></span>

<span data-ttu-id="decf8-180">Wanneer de vooraf getrainde classificaties niet aan uw behoeften voldoen, kunt u uw eigen classificaties maken en trainen.</span><span class="sxs-lookup"><span data-stu-id="decf8-180">When the pre-trained classifiers don't meet your needs, you can create and train your own classifiers.</span></span> <span data-ttu-id="decf8-181">Er is aanzienlijk meer werk betrokken bij het maken van uw eigen werk, maar ze zijn veel beter afgestemd op de behoeften van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="decf8-181">There's significantly more work involved with creating your own, but they'll be much better tailored to your organizations needs.</span></span> 

<span data-ttu-id="decf8-182">U kunt bijvoorbeeld trainbare classificaties maken voor:</span><span class="sxs-lookup"><span data-stu-id="decf8-182">For example you could create trainable classifiers for:</span></span>
 
- <span data-ttu-id="decf8-183">Juridische documenten , zoals het privilege van een advocatenclient, het sluiten van sets, de werkverklaring</span><span class="sxs-lookup"><span data-stu-id="decf8-183">Legal documents - such as attorney client privilege, closing sets, statement of work</span></span>
- <span data-ttu-id="decf8-184">Strategische zakelijke documenten: zoals persberichten, fusies en overnames, aanbiedingen, zakelijke of marketingplannen, intellectueel eigendom, octrooien, ontwerpdocumenten</span><span class="sxs-lookup"><span data-stu-id="decf8-184">Strategic business documents - like press releases, merger and acquisition, deals, business or marketing plans, intellectual property, patents, design docs</span></span>
- <span data-ttu-id="decf8-185">Prijsinformatie: zoals facturen, prijsophalingstekens, werkorders, biedingsdocumenten</span><span class="sxs-lookup"><span data-stu-id="decf8-185">Pricing information - like invoices, price quotes, work orders, bidding documents</span></span> 
- <span data-ttu-id="decf8-186">Financiële informatie, zoals bedrijfsinvesteringen, kwartaal- of jaarresultaten</span><span class="sxs-lookup"><span data-stu-id="decf8-186">Financial information - such as organizational investments, quarterly or annual results</span></span>    

#### <a name="process-flow-for-creating-custom-classifiers"></a><span data-ttu-id="decf8-187">Processtroom voor het maken van aangepaste classificaties</span><span class="sxs-lookup"><span data-stu-id="decf8-187">Process flow for creating custom classifiers</span></span>

<span data-ttu-id="decf8-188">Het maken en publiceren van een classificatie voor gebruik in complianceoplossingen, zoals bewaarbeleid en communicatietoezicht, volgt deze stroom.</span><span class="sxs-lookup"><span data-stu-id="decf8-188">Creating and publishing a classifier for use in compliance solutions, such as retention policies and communication supervision, follows this flow.</span></span> <span data-ttu-id="decf8-189">Zie Een aangepaste classificatie maken voor meer informatie over het maken van een aangepaste, trainbare [classificatie.](classifier-get-started-with.md)</span><span class="sxs-lookup"><span data-stu-id="decf8-189">For more detail on creating a custom trainable classifier see, [Creating a custom classifier](classifier-get-started-with.md).</span></span>

![aangepaste classificatie voor processtroom](../media/classifier-trainable-classifier-flow.png)

### <a name="retraining-classifiers"></a><span data-ttu-id="decf8-191">Omscholingsclassifiers</span><span class="sxs-lookup"><span data-stu-id="decf8-191">Retraining classifiers</span></span>

<span data-ttu-id="decf8-192">U kunt de nauwkeurigheid van alle aangepaste classificaties en sommige vooraf getrainde classificaties verbeteren door hen feedback te geven over de nauwkeurigheid van de classificatie die ze uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="decf8-192">You can help improve the accuracy of all custom classifiers and some pre-trained classifiers by providing them with feedback on the accuracy of the classification that they perform.</span></span> <span data-ttu-id="decf8-193">Dit wordt omscholing genoemd en volgt deze werkstroom.</span><span class="sxs-lookup"><span data-stu-id="decf8-193">This is called retraining and follow this workflow.</span></span>

![omscholingswerkstroom voor classifier](../media/classifier-retraining-workflow.png)

## <a name="see-also"></a><span data-ttu-id="decf8-195">Zie ook</span><span class="sxs-lookup"><span data-stu-id="decf8-195">See also</span></span>

- [<span data-ttu-id="decf8-196">Bewaarlabels</span><span class="sxs-lookup"><span data-stu-id="decf8-196">Retention labels</span></span>](retention.md)
- [<span data-ttu-id="decf8-197">Meer informatie over preventie van gegevensverlies</span><span class="sxs-lookup"><span data-stu-id="decf8-197">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="decf8-198">Vertrouwelijkheidslabels</span><span class="sxs-lookup"><span data-stu-id="decf8-198">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="decf8-199">Definities van entiteiten van het type Gevoelige informatie</span><span class="sxs-lookup"><span data-stu-id="decf8-199">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="decf8-200">Afdrukken met documentvinger</span><span class="sxs-lookup"><span data-stu-id="decf8-200">Document finger printing</span></span>](document-fingerprinting.md)
- [<span data-ttu-id="decf8-201">Exacte gegevensmatch</span><span class="sxs-lookup"><span data-stu-id="decf8-201">Exact data match</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
