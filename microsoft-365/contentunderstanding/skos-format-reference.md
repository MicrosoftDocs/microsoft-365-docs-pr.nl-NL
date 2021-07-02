---
title: SKOS-verwijzing voor SharePoint-taxonomie
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: SKOS-verwijzing voor SharePoint-taxonomie
ms.openlocfilehash: 4c08073f453ef0b6a224829b7d4cb4034b74ed14
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228733"
---
# <a name="skos-format-reference-for-sharepoint-taxonomy"></a><span data-ttu-id="24b4f-103">SKOS-verwijzing voor SharePoint-taxonomie</span><span class="sxs-lookup"><span data-stu-id="24b4f-103">SKOS format reference for SharePoint taxonomy</span></span>

<span data-ttu-id="24b4f-104">Dit artikel bevat de RDF-vocabulaire die wordt gebruikt om [SharePoint-taxonomie](/dotnet/api/microsoft.sharepoint.taxonomy) te vertegenwoordigen en is gebaseerd op [SKOS](https://www.w3.org/TR/skos-primer/).</span><span class="sxs-lookup"><span data-stu-id="24b4f-104">This article includes RDF vocabulary used to represent [SharePoint taxonomy](/dotnet/api/microsoft.sharepoint.taxonomy) and is based on [SKOS](https://www.w3.org/TR/skos-primer/).</span></span> <span data-ttu-id="24b4f-105">Gebruik RDF [SCHILDPAD](https://www.w3.org/TR/turtle/)voor de serialisatie van deze RDF-syntaxis.</span><span class="sxs-lookup"><span data-stu-id="24b4f-105">For serialization of this RDF syntax, use RDF [TURTLE](https://www.w3.org/TR/turtle/).</span></span>

<span data-ttu-id="24b4f-106">In de volgende tabel zie je de [SKOS](https://www.w3.org/TR/skos-primer/)- equivalenten voor de [SharePoint-taxonomie](/dotnet/api/microsoft.sharepoint.taxonomy) woordenlijst.</span><span class="sxs-lookup"><span data-stu-id="24b4f-106">The following table shows the [SKOS](https://www.w3.org/TR/skos-primer/) equivalents for the [SharePoint taxonomy](/dotnet/api/microsoft.sharepoint.taxonomy) vocabulary.</span></span> <span data-ttu-id="24b4f-107">SharePoint biedt geen ondersteuning voor [SKOS](https://www.w3.org/TR/skos-primer/) waarden zonder SharePoint-taxonomie equivalent.</span><span class="sxs-lookup"><span data-stu-id="24b4f-107">SharePoint does not support [SKOS](https://www.w3.org/TR/skos-primer/) values that have no SharePoint taxonomy equivalent.</span></span>

|<span data-ttu-id="24b4f-108">SharePoint-taxonomie</span><span class="sxs-lookup"><span data-stu-id="24b4f-108">SharePoint taxonomy</span></span>|<span data-ttu-id="24b4f-109">SKOS-equivalent</span><span class="sxs-lookup"><span data-stu-id="24b4f-109">SKOS equivalent</span></span>|
|:-----------------|:--------------|
|<span data-ttu-id="24b4f-110">sharepoint-taxonomy:Term</span><span class="sxs-lookup"><span data-stu-id="24b4f-110">sharepoint-taxonomy:Term</span></span>|<span data-ttu-id="24b4f-111">skos: concept</span><span class="sxs-lookup"><span data-stu-id="24b4f-111">skos:Concept</span></span>|
|<span data-ttu-id="24b4f-112">sharepoint-taxonomy:TermSet</span><span class="sxs-lookup"><span data-stu-id="24b4f-112">sharepoint-taxonomy:TermSet</span></span>|<span data-ttu-id="24b4f-113">skos:ConceptScheme</span><span class="sxs-lookup"><span data-stu-id="24b4f-113">skos:ConceptScheme</span></span>|
|<span data-ttu-id="24b4f-114">sharepoint-taxonomy:inTermSet</span><span class="sxs-lookup"><span data-stu-id="24b4f-114">sharepoint-taxonomy:inTermSet</span></span>|<span data-ttu-id="24b4f-115">skos:inScheme</span><span class="sxs-lookup"><span data-stu-id="24b4f-115">skos:inScheme</span></span>|
|<span data-ttu-id="24b4f-116">sharepoint-taxonomy:hasTopLevelTerm</span><span class="sxs-lookup"><span data-stu-id="24b4f-116">sharepoint-taxonomy:hasTopLevelTerm</span></span>|<span data-ttu-id="24b4f-117">skos:hasTopConcept</span><span class="sxs-lookup"><span data-stu-id="24b4f-117">skos:hasTopConcept</span></span>|
|<span data-ttu-id="24b4f-118">sharepoint-taxonomy:topLevelTermOf</span><span class="sxs-lookup"><span data-stu-id="24b4f-118">sharepoint-taxonomy:topLevelTermOf</span></span>|<span data-ttu-id="24b4f-119">skos:topConceptOf</span><span class="sxs-lookup"><span data-stu-id="24b4f-119">skos:topConceptOf</span></span>|
|<span data-ttu-id="24b4f-120">sharepoint-taxonomy:defaultLabel</span><span class="sxs-lookup"><span data-stu-id="24b4f-120">sharepoint-taxonomy:defaultLabel</span></span>|<span data-ttu-id="24b4f-121">skos:prefLabel</span><span class="sxs-lookup"><span data-stu-id="24b4f-121">skos:prefLabel</span></span>|
|<span data-ttu-id="24b4f-122">sharepoint-taxonomy:termSetName</span><span class="sxs-lookup"><span data-stu-id="24b4f-122">sharepoint-taxonomy:termSetName</span></span>|<span data-ttu-id="24b4f-123">skos:prefLabel</span><span class="sxs-lookup"><span data-stu-id="24b4f-123">skos:prefLabel</span></span>|
|<span data-ttu-id="24b4f-124">sharepoint-taxonomy:propertyName</span><span class="sxs-lookup"><span data-stu-id="24b4f-124">sharepoint-taxonomy:propertyName</span></span>|<span data-ttu-id="24b4f-125">skos:prefLabel</span><span class="sxs-lookup"><span data-stu-id="24b4f-125">skos:prefLabel</span></span>|
|<span data-ttu-id="24b4f-126">sharepoint-taxonomy:otherLabel</span><span class="sxs-lookup"><span data-stu-id="24b4f-126">sharepoint-taxonomy:otherLabel</span></span>|<span data-ttu-id="24b4f-127">skos:altLabel</span><span class="sxs-lookup"><span data-stu-id="24b4f-127">skos:altLabel</span></span>|
|<span data-ttu-id="24b4f-128">sharepoint-taxonomy:description</span><span class="sxs-lookup"><span data-stu-id="24b4f-128">sharepoint-taxonomy:description</span></span>|<span data-ttu-id="24b4f-129">skos:definition</span><span class="sxs-lookup"><span data-stu-id="24b4f-129">skos:definition</span></span>|
|<span data-ttu-id="24b4f-130">sharepoint-taxonomy:parent</span><span class="sxs-lookup"><span data-stu-id="24b4f-130">sharepoint-taxonomy:parent</span></span>|<span data-ttu-id="24b4f-131">skos:broader</span><span class="sxs-lookup"><span data-stu-id="24b4f-131">skos:broader</span></span>|
|<span data-ttu-id="24b4f-132">sharepoint-taxonomy:child</span><span class="sxs-lookup"><span data-stu-id="24b4f-132">sharepoint-taxonomy:child</span></span>|<span data-ttu-id="24b4f-133">skos:narrower</span><span class="sxs-lookup"><span data-stu-id="24b4f-133">skos:narrower</span></span>|

<span data-ttu-id="24b4f-134">In de volgende tabel zie je de entiteiten van de SharePoint-taxonomie die is afgeleid van [OWL](https://www.w3.org/TR/owl2-primer/).</span><span class="sxs-lookup"><span data-stu-id="24b4f-134">The following table displays the entities of the SharePoint taxonomy vocabulary derived from [OWL](https://www.w3.org/TR/owl2-primer/).</span></span>

|<span data-ttu-id="24b4f-135">SharePoint-taxonomie woordenlijst</span><span class="sxs-lookup"><span data-stu-id="24b4f-135">SharePoint taxonomy vocabulary</span></span>|<span data-ttu-id="24b4f-136">Afgeleid van OWL</span><span class="sxs-lookup"><span data-stu-id="24b4f-136">Derived from OWL</span></span>|
|:-----------------------------|:----------------------|
|<span data-ttu-id="24b4f-137">sharepoint-taxonomy:isAvailableForTagging</span><span class="sxs-lookup"><span data-stu-id="24b4f-137">sharepoint-taxonomy:isAvailableForTagging</span></span>|<span data-ttu-id="24b4f-138">owl:datatypeproperty</span><span class="sxs-lookup"><span data-stu-id="24b4f-138">owl:datatypeproperty</span></span>|
|<span data-ttu-id="24b4f-139">sharepoint-taxonomy:SharedCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="24b4f-139">sharepoint-taxonomy:SharedCustomPropertyForTerm</span></span>|<span data-ttu-id="24b4f-140">owl:ObjectProperty</span><span class="sxs-lookup"><span data-stu-id="24b4f-140">owl:ObjectProperty</span></span>|
|<span data-ttu-id="24b4f-141">sharepoint-taxonomy:LocalCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="24b4f-141">sharepoint-taxonomy:LocalCustomPropertyForTerm</span></span>|<span data-ttu-id="24b4f-142">owl:ObjectProperty</span><span class="sxs-lookup"><span data-stu-id="24b4f-142">owl:ObjectProperty</span></span>|
|<span data-ttu-id="24b4f-143">sharepoint-taxonomy:CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="24b4f-143">sharepoint-taxonomy:CustomPropertyForTermSet</span></span>|<span data-ttu-id="24b4f-144">owl:ObjectProperty</span><span class="sxs-lookup"><span data-stu-id="24b4f-144">owl:ObjectProperty</span></span>|

## <a name="sharepoint-taxonomy-vocabulary"></a><span data-ttu-id="24b4f-145">SharePoint-taxonomie woordenlijst</span><span class="sxs-lookup"><span data-stu-id="24b4f-145">SharePoint taxonomy vocabulary</span></span>

<span data-ttu-id="24b4f-p103">Een taxonomie is een formeel classificatiesysteem. In een taxonomie worden de woorden, labels en termen gegroepeerd die iets beschrijven. Vervolgens worden die groepen gerangschikt in een hiërarchie.</span><span class="sxs-lookup"><span data-stu-id="24b4f-p103">A taxonomy is a formal classification system. A taxonomy groups the words, labels, and terms that describe something, and then arranges the groups into a hierarchy.</span></span>

<span data-ttu-id="24b4f-148">**sharepoint-taxonomy:Term**</span><span class="sxs-lookup"><span data-stu-id="24b4f-148">**sharepoint-taxonomy:Term**</span></span>

<span data-ttu-id="24b4f-149">Vertegenwoordigt een term of een trefwoord in een hiërarchie met beheerde metagegevens.</span><span class="sxs-lookup"><span data-stu-id="24b4f-149">Represents a Term or a Keyword in a managed metadata hierarchy.</span></span>

<span data-ttu-id="24b4f-150">Een [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) is de atomische eenheid van een SharePoint-[TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore).</span><span class="sxs-lookup"><span data-stu-id="24b4f-150">A [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) is the atomic unit of a SharePoint [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore).</span></span> <span data-ttu-id="24b4f-151">Elke [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) behoort tot een [Termenset](/dotnet/api/microsoft.sharepoint.taxonomy.termset) die behoort tot een [TermGroep](/dotnet/api/microsoft.sharepoint.taxonomy.group).</span><span class="sxs-lookup"><span data-stu-id="24b4f-151">Each [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) belongs to a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) that belongs to a [TermGroup](/dotnet/api/microsoft.sharepoint.taxonomy.group).</span></span>

<span data-ttu-id="24b4f-152">De syntaxis voor het definiëren van een [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) is als volgt:</span><span class="sxs-lookup"><span data-stu-id="24b4f-152">The syntax to define a [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) is as follows:</span></span>

```SKOS
ex:TermA    a    sharepoint-taxonomy:Term;
    sharepoint-taxonomy:inTermSet    ex:TermSetA;
    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA;
    sharepoint-taxonomy:child    ex:TermA1;
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharePoint-taxonomy:defaultLabel    “Term A”@en-us.
```

<span data-ttu-id="24b4f-153">Er bestaat een [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) verplicht binnen een [Termenset](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="24b4f-153">A [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) compulsorily exists within a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="24b4f-154">DefaultLabel is de naam van de [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) zoals deze wordt weergegeven in de visuele weergave.</span><span class="sxs-lookup"><span data-stu-id="24b4f-154">DefaultLabel is the name of the [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) as it appears in the visual representation.</span></span> <span data-ttu-id="24b4f-155">De vereiste velden voor het definiëren van een [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) zijn:</span><span class="sxs-lookup"><span data-stu-id="24b4f-155">The required fields for defining a [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) include:</span></span>

- <span data-ttu-id="24b4f-156">sharepoint-taxonomy:defaultLabel</span><span class="sxs-lookup"><span data-stu-id="24b4f-156">sharepoint-taxonomy:defaultLabel</span></span>
- <span data-ttu-id="24b4f-157">sharepoint-taxonomy:inTermSet</span><span class="sxs-lookup"><span data-stu-id="24b4f-157">sharepoint-taxonomy:inTermSet</span></span>

<span data-ttu-id="24b4f-158">Een [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) kan:</span><span class="sxs-lookup"><span data-stu-id="24b4f-158">A [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) can:</span></span>

- <span data-ttu-id="24b4f-159">Hiërarchisch gerelateerd zijn aan een andere [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) die worden vermeld in zowel de [Termen](/dotnet/api/microsoft.sharepoint.taxonomy.term) behoort tot dezelfde [Termenset](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="24b4f-159">Be hierarchically related to another [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) that is provided both the [Terms](/dotnet/api/microsoft.sharepoint.taxonomy.term) belong to the same [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>
- <span data-ttu-id="24b4f-160">Meerdere onderliggende [Termen](/dotnet/api/microsoft.sharepoint.taxonomy.term), maar slechts één bovenliggende [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="24b4f-160">Have multiple child [Terms](/dotnet/api/microsoft.sharepoint.taxonomy.term), but only a single parent [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>
- <span data-ttu-id="24b4f-161">Er is geen bovenliggende [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)gedefinieerd, als het een topLevelTermOf een [Termenset](/dotnet/api/microsoft.sharepoint.taxonomy.termset)is.</span><span class="sxs-lookup"><span data-stu-id="24b4f-161">Not have a parent [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) defined, if it is a topLevelTermOf a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>
- <span data-ttu-id="24b4f-162">Een defaultLabel hebben, per [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore)-werktaal.</span><span class="sxs-lookup"><span data-stu-id="24b4f-162">Have one defaultLabel, per [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span>
- <span data-ttu-id="24b4f-163">Niet bestaan als deze geen bovenliggende [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)bevat, en niet de topLevelTermOf een [Termenset](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="24b4f-163">Not exist if it neither contains a parent [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term), nor is the topLevelTermOf a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>
- <span data-ttu-id="24b4f-164">Slechts een unieke defaultLabel op hetzelfde hiërarchische niveau hebben.</span><span class="sxs-lookup"><span data-stu-id="24b4f-164">Have only a unique defaultLabel in the same hierarchical level.</span></span>

<span data-ttu-id="24b4f-165">**sharepoint-taxonomy:TermSet**</span><span class="sxs-lookup"><span data-stu-id="24b4f-165">**sharepoint-taxonomy:TermSet**</span></span>

<span data-ttu-id="24b4f-166">Hiermee wordt een hiërarchische of vlakke set termobjecten aangeduid die worden aangeduid als een "Termset".</span><span class="sxs-lookup"><span data-stu-id="24b4f-166">Represents a hierarchical or flat set of Term objects known as a "TermSet".</span></span>

<span data-ttu-id="24b4f-167">Zoals de naam suggereertt, is Termset een set [Termen](/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="24b4f-167">As the name suggests, TermSet is a set of [Terms](/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="24b4f-168">Een [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) in een [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) moet deel uitmaken van een [Termenset](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="24b4f-168">A [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) in a [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) must belong to a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="24b4f-169">Er kan geen [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) afzonderlijk bestaan.</span><span class="sxs-lookup"><span data-stu-id="24b4f-169">No [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) can exist independently.</span></span>

<span data-ttu-id="24b4f-170">De syntaxis voor het definiëren van een [Term](/dotnet/api/microsoft.sharepoint.taxonomy.termset) is:</span><span class="sxs-lookup"><span data-stu-id="24b4f-170">The syntax to define a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) is:</span></span>

```SKOS
ex:TermSetA    a    sharepoint-taxonomy:TermSet;
    sharepoint-taxonomy:termSetName    “TermSet A";
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharepoint-taxonomy:hasTopLevelTerm    Ex:Term A.
```

<span data-ttu-id="24b4f-171">[TermSets](/dotnet/api/microsoft.sharepoint.taxonomy.termset) zijn logisch gegroepeerd in [TermGroups](/dotnet/api/microsoft.sharepoint.taxonomy.group).</span><span class="sxs-lookup"><span data-stu-id="24b4f-171">[TermSets](/dotnet/api/microsoft.sharepoint.taxonomy.termset) are logically grouped together in [TermGroups](/dotnet/api/microsoft.sharepoint.taxonomy.group).</span></span> <span data-ttu-id="24b4f-172">De vereiste velden voor het definiëren van een [Termenset](/dotnet/api/microsoft.sharepoint.taxonomy.termset) zijn:</span><span class="sxs-lookup"><span data-stu-id="24b4f-172">The required field for defining a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) is:</span></span>

- <span data-ttu-id="24b4f-173">sharepoint-taxonomy:termSetName</span><span class="sxs-lookup"><span data-stu-id="24b4f-173">sharepoint-taxonomy:termSetName</span></span>

<span data-ttu-id="24b4f-174">In het geval van het gegeven termSetName niet uniek is binnen de [TermGroup](/dotnet/api/microsoft.sharepoint.taxonomy.group), wordt aan het begin van de naam een nummer toegevoegd door SharePoint om de uniekheid van termSetName(s) te behouden.</span><span class="sxs-lookup"><span data-stu-id="24b4f-174">In the case of the termSetName provided is not unique within the [TermGroup](/dotnet/api/microsoft.sharepoint.taxonomy.group), SharePoint appends a number at the end of the name to maintain the uniqueness of termSetName(s).</span></span>

<span data-ttu-id="24b4f-175">**sharepoint-taxonomy:hasTopLevelTerm**</span><span class="sxs-lookup"><span data-stu-id="24b4f-175">**sharepoint-taxonomy:hasTopLevelTerm**</span></span>

<span data-ttu-id="24b4f-176">SharePoint gebruikt deze eigenschap om de hoogste [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) toe te wijzen aan de [Termenset](/dotnet/api/microsoft.sharepoint.taxonomy.termset), het ingangspunt van de hiërarchie met [Termen](/dotnet/api/microsoft.sharepoint.taxonomy.term) in een [Termenset](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="24b4f-176">SharePoint uses this property to map the top most [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) in the [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset), which is the entry point to the hierarchy of [Terms](/dotnet/api/microsoft.sharepoint.taxonomy.term) in a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="24b4f-177">Dit is een inverse relatie met de SharePoint-taxonomie: topLevelTermOf.</span><span class="sxs-lookup"><span data-stu-id="24b4f-177">This is an inverse relation to sharepoint-taxonomy:topLevelTermOf.</span></span>

<span data-ttu-id="24b4f-178">De syntaxis voor het definiëren hiervan is:</span><span class="sxs-lookup"><span data-stu-id="24b4f-178">The syntax to define this is:</span></span>

```SKOS
ex:TermSetA    sharepoint-taxonomy:hasTopLevelTerm    ex:TermA.
```

> [!NOTE]
> <span data-ttu-id="24b4f-179">Het is niet mogelijk om de [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) op het hoogste niveau van een bovenliggend [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)te definiëren.</span><span class="sxs-lookup"><span data-stu-id="24b4f-179">You cannot define the top level [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) of a parent [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="24b4f-180">**sharepoint-taxonomy:topLevelTermOf**</span><span class="sxs-lookup"><span data-stu-id="24b4f-180">**sharepoint-taxonomy:topLevelTermOf**</span></span>

<span data-ttu-id="24b4f-181">SharePoint-taxonomie: topLevelTermOf is de inverse van SharePoint-taxonomie: hasTopLevelTerm</span><span class="sxs-lookup"><span data-stu-id="24b4f-181">Sharepoint-taxonomy:topLevelTermOf is the inverse of sharepoint-taxonomy:hasTopLevelTerm</span></span>

<span data-ttu-id="24b4f-182">De syntaxis voor het definiëren hiervan is:</span><span class="sxs-lookup"><span data-stu-id="24b4f-182">The syntax to define this is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA.
```

<span data-ttu-id="24b4f-183">**sharepoint-taxonomy:inTermSet**</span><span class="sxs-lookup"><span data-stu-id="24b4f-183">**sharepoint-taxonomy:inTermSet**</span></span>

<span data-ttu-id="24b4f-184">Gebruik dit om een [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) toe te wijzen aan een [Termenset](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="24b4f-184">Use this to map a [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) to a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="24b4f-185">Een [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) kan slechts bestaan in één [Termenset](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="24b4f-185">A [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) can only exist in a single [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="24b4f-186">SharePoint vereist deze eigenschap bij het[definiëren van een term](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term).</span><span class="sxs-lookup"><span data-stu-id="24b4f-186">SharePoint requires this property when [defining a term](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term).</span></span>

## <a name="required-labels"></a><span data-ttu-id="24b4f-187">Vereiste labels</span><span class="sxs-lookup"><span data-stu-id="24b4f-187">Required labels</span></span>

<span data-ttu-id="24b4f-188">Het is mogelijk dat je organisatie een zorgvuldige planning moet uitvoeren voordat je beheerde metagegevens gaat gebruiken.</span><span class="sxs-lookup"><span data-stu-id="24b4f-188">Your organization may want to do careful planning before you start to use managed metadata.</span></span> <span data-ttu-id="24b4f-189">De hoeveelheid planning die je moet uitvoeren, hangt af van hoe formeel de taxonomie is.</span><span class="sxs-lookup"><span data-stu-id="24b4f-189">The amount of planning that you must do depends on how formal your taxonomy is.</span></span> <span data-ttu-id="24b4f-190">De functie is ook afhankelijk van de hoeveelheid besturingselementen die je wilt toepassen op metagegevens.</span><span class="sxs-lookup"><span data-stu-id="24b4f-190">It also depends on how much control that you want to impose on metadata.</span></span> <span data-ttu-id="24b4f-191">Op elk niveau van de hiërarchie moet je de vereiste labels voor een Term of Termenset configureren.</span><span class="sxs-lookup"><span data-stu-id="24b4f-191">At each level of the hierarchy, you need to configure required labels for a Term or TermSet.</span></span>

<span data-ttu-id="24b4f-192">Een term kan een of meer labels in de standaardtaal bevatten en nul of meer etiketten in de niet-standaardtaal.</span><span class="sxs-lookup"><span data-stu-id="24b4f-192">A Term can have one or more labels in the default language, and zero or more labels in the non-default language.</span></span> <span data-ttu-id="24b4f-193">Als de term labels in een taal heeft, moet een van de labels het standaardlabel zijn.</span><span class="sxs-lookup"><span data-stu-id="24b4f-193">If the term has labels in a language, one of the labels must be the default label.</span></span>

<span data-ttu-id="24b4f-194">**sharepoint-taxonomy:defaultLabel**</span><span class="sxs-lookup"><span data-stu-id="24b4f-194">**sharepoint-taxonomy:defaultLabel**</span></span>

<span data-ttu-id="24b4f-195">Gebruik dit standaard-lexicale label voor een [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) die een verplichte parameter is voor een [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="24b4f-195">Use this default lexical label for a [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) that is a required parameter for a [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="24b4f-196">Gebruik om de [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)visueel te representeren.</span><span class="sxs-lookup"><span data-stu-id="24b4f-196">Use to visually representing the [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="24b4f-197">De syntaxis voor het definiëren van standaard label is:</span><span class="sxs-lookup"><span data-stu-id="24b4f-197">The syntax to define a defaultLabel is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:defaultLabel    “Term A”@en-us.
```

<span data-ttu-id="24b4f-198">De defaultLabel bevat twee onderdelen: de tekenreeks en de taal.</span><span class="sxs-lookup"><span data-stu-id="24b4f-198">The defaultLabel contains two parts to it – the string and the language tag.</span></span> <span data-ttu-id="24b4f-199">De taal moet een van de [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore)- werktalen zijn.</span><span class="sxs-lookup"><span data-stu-id="24b4f-199">The language must be one of the [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working languages.</span></span> <span data-ttu-id="24b4f-200">De defaultLabel moet uniek zijn voor alle [Termen](/dotnet/api/microsoft.sharepoint.taxonomy.term) in dezelfde [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) op hetzelfde hiërarchische niveau.</span><span class="sxs-lookup"><span data-stu-id="24b4f-200">The defaultLabel must be unique for all [Terms](/dotnet/api/microsoft.sharepoint.taxonomy.term) in the same [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset), at the same hierarchical level.</span></span>

<span data-ttu-id="24b4f-201">**sharepoint-taxonomy:termSetName**</span><span class="sxs-lookup"><span data-stu-id="24b4f-201">**sharepoint-taxonomy:termSetName**</span></span>

<span data-ttu-id="24b4f-202">Hiermee wordt de naam opgehaald en ingesteld voor het huidige Termenset-object.</span><span class="sxs-lookup"><span data-stu-id="24b4f-202">Gets and sets the name for the current TermSet object.</span></span>

<span data-ttu-id="24b4f-203">Dit is het lexicale label voor een [Termenset](/dotnet/api/microsoft.sharepoint.taxonomy.termset), in een [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore)-werktaal.</span><span class="sxs-lookup"><span data-stu-id="24b4f-203">This the lexical label for a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset), in a [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span> <span data-ttu-id="24b4f-204">Dit is een verplichte parameter voor een [Termenset](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="24b4f-204">This is a required parameter for a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="24b4f-205">Gebruik om de [Termenset](/dotnet/api/microsoft.sharepoint.taxonomy.termset)visueel te representeren.</span><span class="sxs-lookup"><span data-stu-id="24b4f-205">Use to visually representing a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>

<span data-ttu-id="24b4f-206">De syntaxis voor het definiëren van een termSetName is:</span><span class="sxs-lookup"><span data-stu-id="24b4f-206">The syntax to define a termSetName is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:TermSetName    “Term Set A”@en-us.
```

<span data-ttu-id="24b4f-207">**sharepoint-taxonomy:propertyName**</span><span class="sxs-lookup"><span data-stu-id="24b4f-207">**sharepoint-taxonomy:propertyName**</span></span>

<span data-ttu-id="24b4f-208">Hiermee wordt de eigenschapsnaam opgehaald en ingesteld voor het huidige Termenset-object.</span><span class="sxs-lookup"><span data-stu-id="24b4f-208">Gets and sets the property name for the current TermSet object.</span></span>

<span data-ttu-id="24b4f-209">Dit is het lexical-label voor een SharePoint-taxonomie: SharedCustomPropertyForTerm, SharePoint-taxonomie: LocalCustomPropertyForTerm en SharePoint-taxonomie: CustomPropertyForTermSet in een [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore)-werktaal.</span><span class="sxs-lookup"><span data-stu-id="24b4f-209">This is the lexical label for a sharepoint-taxonomy:SharedCustomPropertyForTerm, sharepoint-taxonomy:LocalCustomPropertyForTerm and sharepoint-taxonomy:CustomPropertyForTermSet in a [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span>

<span data-ttu-id="24b4f-210">SharePoint-taxonomie: eigenschapnamen wordt behandeld als de sleutel van de CustomProperty.</span><span class="sxs-lookup"><span data-stu-id="24b4f-210">The sharepoint-taxonomy:propertyName is treated as the key of the CustomProperty.</span></span>

<span data-ttu-id="24b4f-211">De syntaxis voor het definiëren van een propetyName is:</span><span class="sxs-lookup"><span data-stu-id="24b4f-211">The syntax to define a propetyName is:</span></span>

```SKOS
ex:SharedCustomProperty1    sharepoint-taxonomy:propertyName    “Shared Custom Property Key 1”@en-us.
```

## <a name="optional-labels"></a><span data-ttu-id="24b4f-212">Optionele labels</span><span class="sxs-lookup"><span data-stu-id="24b4f-212">Optional labels</span></span>

<span data-ttu-id="24b4f-213">Je kunt ook optionele labels toevoegen aan je taxonomie.</span><span class="sxs-lookup"><span data-stu-id="24b4f-213">You can also add optional labels to your taxonomy.</span></span>

<span data-ttu-id="24b4f-214">**sharepoint-taxonomy:otherLabel**</span><span class="sxs-lookup"><span data-stu-id="24b4f-214">**sharepoint-taxonomy:otherLabel**</span></span>

<span data-ttu-id="24b4f-215">Dit is het alternatieve lexicale label voor een [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="24b4f-215">This is the alternate lexical label for a [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="24b4f-216">De syntaxis voor het definiëren van otherLabel is:</span><span class="sxs-lookup"><span data-stu-id="24b4f-216">The syntax to define an otherLabel is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:otherLabel    “Term A”@en-us.
```

## <a name="semantic-relationships"></a><span data-ttu-id="24b4f-217">Semantische relaties</span><span class="sxs-lookup"><span data-stu-id="24b4f-217">Semantic relationships</span></span>

<span data-ttu-id="24b4f-218">Taxonomie heeft hiërarchische en soms een simpele "gerelateerde term" associatieve relatie, maar enkele voorbeelden van "semantische relaties" of relaties met aangepaste voorwaarden.</span><span class="sxs-lookup"><span data-stu-id="24b4f-218">Taxonomies have hierarchical and sometimes a simple “related term” associative relationship, but some have "semantic relationships" or custom-created relationships.</span></span>

<span data-ttu-id="24b4f-219">**sharepoint-taxonomy:parent**</span><span class="sxs-lookup"><span data-stu-id="24b4f-219">**sharepoint-taxonomy:parent**</span></span>

<span data-ttu-id="24b4f-220">Hiermee wordt een [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) op een andere [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="24b4f-220">This hierarchically relates a [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) to another [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="24b4f-221">Een [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) kan een hoog niveau [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) van een [Termenset](/dotnet/api/microsoft.sharepoint.taxonomy.termset) zijn, maar als het niet zo is moet er een bovenliggende [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) zijn.</span><span class="sxs-lookup"><span data-stu-id="24b4f-221">A [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) could be a top level [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) of a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset), but in case it doesn’t it must have a parent [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="24b4f-222">De syntaxis voor het definiëren van een bovenliggende term is:</span><span class="sxs-lookup"><span data-stu-id="24b4f-222">The syntax to define a parent is:</span></span>

```SKOS
ex:TermA1    sharepoint-taxonomy:parent    ex:TermA.
```

<span data-ttu-id="24b4f-223">Dit betekent dat TermA het bovenliggende en TermA het onderliggende.</span><span class="sxs-lookup"><span data-stu-id="24b4f-223">This means that TermA is the parent and  TermA is the child.</span></span>

<span data-ttu-id="24b4f-224">**sharepoint-taxonomy:child**</span><span class="sxs-lookup"><span data-stu-id="24b4f-224">**sharepoint-taxonomy:child**</span></span>

<span data-ttu-id="24b4f-225">Het object bevat een of meer onderliggende Termenset-instanties en kan worden geopend via de eigenschap TermSets.</span><span class="sxs-lookup"><span data-stu-id="24b4f-225">The object contains one or more child TermSet instances, and these can be accessed through the TermSets property.</span></span> <span data-ttu-id="24b4f-226">Deze klas biedt ook methoden voor het maken van nieuwe onderliggende Termenset-objecten.</span><span class="sxs-lookup"><span data-stu-id="24b4f-226">This class also provides methods for creating new child TermSet objects.</span></span> <span data-ttu-id="24b4f-227">De machtigingen voor het bewerken van onderliggende termen en Termenset-exemplaren zijn opgegeven voor de groep.</span><span class="sxs-lookup"><span data-stu-id="24b4f-227">Permissions for editing child Term and TermSet instances is specified on the group.</span></span>

<span data-ttu-id="24b4f-228">Hiermee wordt een [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) op een andere [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="24b4f-228">This hierarchically relates a [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) to another [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="24b4f-229">De syntaxis voor het definiëren van een onderliggende term is:</span><span class="sxs-lookup"><span data-stu-id="24b4f-229">The syntax to define a child is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:child    ex:TermA1.
```

<span data-ttu-id="24b4f-230">Dit betekent dat TermA het bovenliggende en TermA het onderliggende.</span><span class="sxs-lookup"><span data-stu-id="24b4f-230">This means that TermA is the parent and  TermA is the child.</span></span>

## <a name="documentation-notes"></a><span data-ttu-id="24b4f-231">Documentatienotities</span><span class="sxs-lookup"><span data-stu-id="24b4f-231">Documentation notes</span></span>

<span data-ttu-id="24b4f-232">In deze sectie wordt de taxonomie besproken die wordt beschreven in de Naamruimte Microsoft.SharePoint-taxonomie.</span><span class="sxs-lookup"><span data-stu-id="24b4f-232">This section discusses the taxonomy detailed in the Microsoft.SharePoint.Taxonomy Namespace.</span></span>

<span data-ttu-id="24b4f-233">**sharepoint-taxonomy:description**</span><span class="sxs-lookup"><span data-stu-id="24b4f-233">**sharepoint-taxonomy:description**</span></span>

<span data-ttu-id="24b4f-234">Dit is een gedetailleerde uitleg van een [SharePoint-taxonomie](/dotnet/api/microsoft.sharepoint.taxonomy) vocabulaire-entiteit.</span><span class="sxs-lookup"><span data-stu-id="24b4f-234">This is a detailed explanation of any [SharePoint taxonomy](/dotnet/api/microsoft.sharepoint.taxonomy) vocabulary entity.</span></span>

<span data-ttu-id="24b4f-235">De syntaxis om een beschrijving toe te voegen is:</span><span class="sxs-lookup"><span data-stu-id="24b4f-235">The syntax to add a description is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:description    “Term A is the top level term of TermSetA”@en-us.
```

## <a name="custom-properties"></a><span data-ttu-id="24b4f-236">Aangepaste eigenschappen</span><span class="sxs-lookup"><span data-stu-id="24b4f-236">Custom properties</span></span>

<span data-ttu-id="24b4f-237">Hiermee haal je een verzameling aangepaste eigenschapsobjecten op voor de huidige objectterm uit de alleen-lezen woordenlijst.</span><span class="sxs-lookup"><span data-stu-id="24b4f-237">Gets the collection of custom property objects for the current Term object from the read-only dictionary.</span></span>

<span data-ttu-id="24b4f-238">Aangepaste eigenschappen zijn sleutelwaarden paren die kunnen worden gedefinieerd voor een [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) of een [Termenset](/dotnet/api/microsoft.sharepoint.taxonomy.termset), om de beschrijving van de [Termen](/dotnet/api/microsoft.sharepoint.taxonomy.term) of een [Termenset](/dotnet/api/microsoft.sharepoint.taxonomy.termset) te bevorderen.</span><span class="sxs-lookup"><span data-stu-id="24b4f-238">Custom Properties are key-values pairs that can be defined for a [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset), to further the description of the [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="24b4f-239">SharePoint geeft de sleutel van de aangepaste eigenschap aan met behulp van propertyName.</span><span class="sxs-lookup"><span data-stu-id="24b4f-239">SharePoint specifies the key of the custom property with the help of propertyName.</span></span>

<span data-ttu-id="24b4f-240">**sharepoint-taxonomy:CustomPropertyForTermSet**</span><span class="sxs-lookup"><span data-stu-id="24b4f-240">**sharepoint-taxonomy:CustomPropertyForTermSet**</span></span>

<span data-ttu-id="24b4f-241">De syntaxis voor het definiëren hiervan is:</span><span class="sxs-lookup"><span data-stu-id="24b4f-241">The syntax to define this is:</span></span>

```SKOS
ex:CustomProp1    rdf:type    sharepoint-taxonomy:CustomPropertyForTermSet;
    sharepoint-taxonomy:propertyName “Colour”.

ex:TermSetA    ex:CustomProp1    “Red”@en-us.
```

<span data-ttu-id="24b4f-242">**sharepoint-taxonomy:SharedCustomPropertyForTerm**</span><span class="sxs-lookup"><span data-stu-id="24b4f-242">**sharepoint-taxonomy:SharedCustomPropertyForTerm**</span></span>

<span data-ttu-id="24b4f-243">Als de aangepaste eigenschap voor een [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) moet worden meegenomen aan de [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term), moet je de [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) vervolgens op de gewenste locatie definiëren onder SharedCustomPropertyForTerm.</span><span class="sxs-lookup"><span data-stu-id="24b4f-243">If the custom property for a [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) needs to be carried along with the [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term), when you reuse the [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) somewhere else, then you need to be define it under SharedCustomPropertyForTerm.</span></span>

<span data-ttu-id="24b4f-244">De syntaxis voor het definiëren hiervan is:</span><span class="sxs-lookup"><span data-stu-id="24b4f-244">The syntax to define this is:</span></span>

``` SKOS
ex:CustomProp2    rdf:type sharepoint-taxonomy:SharedCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “Length”.

ex:TermA    ex:CustomProp2    “5 cm”@en-us.
```
<span data-ttu-id="24b4f-245">**sharepoint-taxonomy:LocalCustomPropertyForTerm**</span><span class="sxs-lookup"><span data-stu-id="24b4f-245">**sharepoint-taxonomy:LocalCustomPropertyForTerm**</span></span>

<span data-ttu-id="24b4f-246">Als de aangepaste eigenschap voor een [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) niet moet worden meegenomen met de [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term), moet je de [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) vervolgens op de gewenste locatie definiëren onder LocalCustomPropertyForTerm.</span><span class="sxs-lookup"><span data-stu-id="24b4f-246">If the custom property for a [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) does not need to be carried along with the [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term), when you reuse the [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) somewhere else, then you need to define it under LocalCustomPropertyForTerm.</span></span>

<span data-ttu-id="24b4f-247">De syntaxis voor het definiëren hiervan is:</span><span class="sxs-lookup"><span data-stu-id="24b4f-247">The syntax to define this is:</span></span>

```SKOS
ex:CustomProp3    rdf:type sharepoint-taxonomy:LocalCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “width”.

ex:TermA    ex:CustomProp3    “5 cm”@en-us.
```

## <a name="data-properties"></a><span data-ttu-id="24b4f-248">Gegevenseigenschappen</span><span class="sxs-lookup"><span data-stu-id="24b4f-248">Data properties</span></span>

<span data-ttu-id="24b4f-249">Op elk niveau van de hiërarchie moet je de specifieke gegevenseigenschappen voor een Term of Termenset configureren.</span><span class="sxs-lookup"><span data-stu-id="24b4f-249">At each level of the hierarchy, you can configure specific data properties for a Term or TermSet.</span></span>

<span data-ttu-id="24b4f-250">**sharepoint-taxonomy:isAvailableForTagging**</span><span class="sxs-lookup"><span data-stu-id="24b4f-250">**sharepoint-taxonomy:isAvailableForTagging**</span></span>

<span data-ttu-id="24b4f-251">Gebruik deze instelling om op te geven of een [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) of een [Termenset](/dotnet/api/microsoft.sharepoint.taxonomy.termset) die beschikbaar is in SharePoint-lijsten en - bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="24b4f-251">Use this to specify if a [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) available in SharePoint Lists and Libraries.</span></span>

<span data-ttu-id="24b4f-252">De syntaxis voor dit is als volgt:</span><span class="sxs-lookup"><span data-stu-id="24b4f-252">The syntax for this is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:isAvailableForTagging     "true"^^xsd:Boolean;
```

## <a name="domain-and-range"></a><span data-ttu-id="24b4f-253">Domein en bereik</span><span class="sxs-lookup"><span data-stu-id="24b4f-253">Domain and range</span></span>

<span data-ttu-id="24b4f-254">In de volgende tabel vind je een beschrijving van het domein en het bereik van de SharePoint-taxonomie woordenlijst.</span><span class="sxs-lookup"><span data-stu-id="24b4f-254">The table below describes the domain and range of SharePoint taxonomy vocabulary.</span></span>

|<span data-ttu-id="24b4f-255">Predikaten/werkwoord</span><span class="sxs-lookup"><span data-stu-id="24b4f-255">Predicates/verb</span></span>|<span data-ttu-id="24b4f-256">Betekenis</span><span class="sxs-lookup"><span data-stu-id="24b4f-256">Meaning</span></span>|<span data-ttu-id="24b4f-257">Domein</span><span class="sxs-lookup"><span data-stu-id="24b4f-257">Domain</span></span>|<span data-ttu-id="24b4f-258">Bereik</span><span class="sxs-lookup"><span data-stu-id="24b4f-258">Range</span></span>|
|:--------------|:------|:-----|:----|
<span data-ttu-id="24b4f-259">inTermSet</span><span class="sxs-lookup"><span data-stu-id="24b4f-259">inTermSet</span></span>|<span data-ttu-id="24b4f-260">In Termenset</span><span class="sxs-lookup"><span data-stu-id="24b4f-260">In term set</span></span>|<span data-ttu-id="24b4f-261">Term</span><span class="sxs-lookup"><span data-stu-id="24b4f-261">Term</span></span>|<span data-ttu-id="24b4f-262">Termenset</span><span class="sxs-lookup"><span data-stu-id="24b4f-262">Term Set</span></span>|
<span data-ttu-id="24b4f-263">inTermGroup</span><span class="sxs-lookup"><span data-stu-id="24b4f-263">inTermGroup</span></span>|<span data-ttu-id="24b4f-264">In termgroep</span><span class="sxs-lookup"><span data-stu-id="24b4f-264">In term group</span></span>|<span data-ttu-id="24b4f-265">TermSet</span><span class="sxs-lookup"><span data-stu-id="24b4f-265">TermSet</span></span>|<span data-ttu-id="24b4f-266">TermGroup</span><span class="sxs-lookup"><span data-stu-id="24b4f-266">TermGroup</span></span>|
<span data-ttu-id="24b4f-267">topLevelTermOf</span><span class="sxs-lookup"><span data-stu-id="24b4f-267">topLevelTermOf</span></span>|<span data-ttu-id="24b4f-268">Is het hoogste niveau van</span><span class="sxs-lookup"><span data-stu-id="24b4f-268">Is Top Level Term Of</span></span>|<span data-ttu-id="24b4f-269">Term</span><span class="sxs-lookup"><span data-stu-id="24b4f-269">Term</span></span>|<span data-ttu-id="24b4f-270">TermSet</span><span class="sxs-lookup"><span data-stu-id="24b4f-270">TermSet</span></span>|
<span data-ttu-id="24b4f-271">hasTopLevelTerm</span><span class="sxs-lookup"><span data-stu-id="24b4f-271">hasTopLevelTerm</span></span>|<span data-ttu-id="24b4f-272">Heeft het hoogste niveau term</span><span class="sxs-lookup"><span data-stu-id="24b4f-272">Has top level term</span></span>|<span data-ttu-id="24b4f-273">Termenset</span><span class="sxs-lookup"><span data-stu-id="24b4f-273">Term Set</span></span>|<span data-ttu-id="24b4f-274">Term</span><span class="sxs-lookup"><span data-stu-id="24b4f-274">Term</span></span>|
<span data-ttu-id="24b4f-275">termSetName</span><span class="sxs-lookup"><span data-stu-id="24b4f-275">termSetName</span></span>|<span data-ttu-id="24b4f-276">Termenset heeft naam</span><span class="sxs-lookup"><span data-stu-id="24b4f-276">Term set has Name</span></span>|<span data-ttu-id="24b4f-277">Term</span><span class="sxs-lookup"><span data-stu-id="24b4f-277">Term</span></span>|<span data-ttu-id="24b4f-278">Letterlijke tekst zonder opmaak</span><span class="sxs-lookup"><span data-stu-id="24b4f-278">Plain literal</span></span>|
<span data-ttu-id="24b4f-279">defaultLabel</span><span class="sxs-lookup"><span data-stu-id="24b4f-279">defaultLabel</span></span>|<span data-ttu-id="24b4f-280">Term heeft een standaardlabel</span><span class="sxs-lookup"><span data-stu-id="24b4f-280">Term has default label</span></span>|<span data-ttu-id="24b4f-281">Term</span><span class="sxs-lookup"><span data-stu-id="24b4f-281">Term</span></span>|<span data-ttu-id="24b4f-282">Letterlijke tekst zonder opmaak</span><span class="sxs-lookup"><span data-stu-id="24b4f-282">Plain literal</span></span>|
<span data-ttu-id="24b4f-283">otherLabel</span><span class="sxs-lookup"><span data-stu-id="24b4f-283">otherLabel</span></span>|<span data-ttu-id="24b4f-284">Term heeft een ander label</span><span class="sxs-lookup"><span data-stu-id="24b4f-284">Term has other label</span></span>|<span data-ttu-id="24b4f-285">Term</span><span class="sxs-lookup"><span data-stu-id="24b4f-285">Term</span></span>|<span data-ttu-id="24b4f-286">Letterlijke tekst zonder opmaak</span><span class="sxs-lookup"><span data-stu-id="24b4f-286">Plain literal</span></span>|
<span data-ttu-id="24b4f-287">propertyName</span><span class="sxs-lookup"><span data-stu-id="24b4f-287">propertyName</span></span>|<span data-ttu-id="24b4f-288">Heeft eigenschapslabel</span><span class="sxs-lookup"><span data-stu-id="24b4f-288">Has Property Label</span></span>|<span data-ttu-id="24b4f-289">SharedCustomPropertyForTerm, LocalCustomPropertyForTerm, CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="24b4f-289">SharedCustomPropertyForTerm, LocalCustomPropertyForTerm, CustomPropertyForTermSet</span></span> |<span data-ttu-id="24b4f-290">Boolean, String, Integer, Decimal, Double</span><span class="sxs-lookup"><span data-stu-id="24b4f-290">Boolean, String, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="24b4f-291">beschrijving</span><span class="sxs-lookup"><span data-stu-id="24b4f-291">description</span></span>|<span data-ttu-id="24b4f-292">Heeft beschrijving</span><span class="sxs-lookup"><span data-stu-id="24b4f-292">Has Description</span></span>|<span data-ttu-id="24b4f-293">Alle</span><span class="sxs-lookup"><span data-stu-id="24b4f-293">All</span></span>|<span data-ttu-id="24b4f-294">Letterlijke tekst zonder opmaak</span><span class="sxs-lookup"><span data-stu-id="24b4f-294">Plain literal</span></span>|
|<span data-ttu-id="24b4f-295">Bovenliggend</span><span class="sxs-lookup"><span data-stu-id="24b4f-295">parent</span></span>|<span data-ttu-id="24b4f-296">Heeft bovenliggend element</span><span class="sxs-lookup"><span data-stu-id="24b4f-296">Has parent</span></span>|<span data-ttu-id="24b4f-297">Term</span><span class="sxs-lookup"><span data-stu-id="24b4f-297">Term</span></span>|<span data-ttu-id="24b4f-298">Term</span><span class="sxs-lookup"><span data-stu-id="24b4f-298">Term</span></span>|
|<span data-ttu-id="24b4f-299">onderliggend element</span><span class="sxs-lookup"><span data-stu-id="24b4f-299">child</span></span>|<span data-ttu-id="24b4f-300">Heeft onderliggend element</span><span class="sxs-lookup"><span data-stu-id="24b4f-300">Has Child</span></span>|<span data-ttu-id="24b4f-301">Term</span><span class="sxs-lookup"><span data-stu-id="24b4f-301">Term</span></span>|<span data-ttu-id="24b4f-302">Term</span><span class="sxs-lookup"><span data-stu-id="24b4f-302">Term</span></span>|
|<span data-ttu-id="24b4f-303">isAvailableForTagging</span><span class="sxs-lookup"><span data-stu-id="24b4f-303">isAvailableForTagging</span></span>|<span data-ttu-id="24b4f-304">Is beschikbaar voor labelen</span><span class="sxs-lookup"><span data-stu-id="24b4f-304">Is available for tagging</span></span>|<span data-ttu-id="24b4f-305">Term, Termenset</span><span class="sxs-lookup"><span data-stu-id="24b4f-305">Term, Term Set</span></span>|<span data-ttu-id="24b4f-306">Booleaanse waarde</span><span class="sxs-lookup"><span data-stu-id="24b4f-306">Boolean</span></span>|
|<span data-ttu-id="24b4f-307">SharedCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="24b4f-307">SharedCustomPropertyForTerm</span></span>|<span data-ttu-id="24b4f-308">Heeft aangepaste eigenschap gedeeld</span><span class="sxs-lookup"><span data-stu-id="24b4f-308">Has shared custom property</span></span>|<span data-ttu-id="24b4f-309">Term</span><span class="sxs-lookup"><span data-stu-id="24b4f-309">Term</span></span>|<span data-ttu-id="24b4f-310">Boolean, String, Integer, Decimal, Double</span><span class="sxs-lookup"><span data-stu-id="24b4f-310">Boolean, string, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="24b4f-311">LocalCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="24b4f-311">LocalCustomPropertyForTerm</span></span>|<span data-ttu-id="24b4f-312">Heeft lokale aangepaste eigenschap</span><span class="sxs-lookup"><span data-stu-id="24b4f-312">Has local custom property</span></span>|<span data-ttu-id="24b4f-313">Term</span><span class="sxs-lookup"><span data-stu-id="24b4f-313">Term</span></span>|<span data-ttu-id="24b4f-314">Boolean, String, Integer, Decimal, Double</span><span class="sxs-lookup"><span data-stu-id="24b4f-314">Boolean, String, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="24b4f-315">CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="24b4f-315">CustomPropertyForTermSet</span></span>|<span data-ttu-id="24b4f-316">Heeft aangepaste eigenschap</span><span class="sxs-lookup"><span data-stu-id="24b4f-316">Has Custom Property</span></span>|<span data-ttu-id="24b4f-317">TermSet</span><span class="sxs-lookup"><span data-stu-id="24b4f-317">TermSet</span></span>|<span data-ttu-id="24b4f-318">Boolean, String, Integer, Decimal, Double</span><span class="sxs-lookup"><span data-stu-id="24b4f-318">Boolean, String, Integer, Decimal, Double</span></span>|

<span data-ttu-id="24b4f-319">[SKOS](https://www.w3.org/TR/skos-primer/) geldige scenario's die [ SharePoint-taxonomie](/dotnet/api/microsoft.sharepoint.taxonomy) niet is toegestaan:</span><span class="sxs-lookup"><span data-stu-id="24b4f-319">[SKOS](https://www.w3.org/TR/skos-primer/) valid scenarios that [SharePoint taxonomy](/dotnet/api/microsoft.sharepoint.taxonomy) does not allow:</span></span>

- <span data-ttu-id="24b4f-320">Hiërarchische redundantie - een [SKOS](https://www.w3.org/TR/skos-primer/) concept kan tegelijk met meerdere bredere concepten worden bijgevoegd, maar een SharePoint-taxonomie: kan slechts één SharePoint-taxonomie bevatten: bovenliggend, dus cyclische afhankelijkheid van termen is ook niet toegestaan.</span><span class="sxs-lookup"><span data-stu-id="24b4f-320">Hierarchical redundancy - A [SKOS](https://www.w3.org/TR/skos-primer/) concept can be attached to several broader concepts at the same time, but a sharepoint-taxonomy:Term can have only one sharepoint-taxonomy:parent, hence cyclic dependency, of Terms is also not allowed.</span></span>
- <span data-ttu-id="24b4f-p118">Zwevende termen zijn niet toegestaan in SharePoint-taxonomie. Elke sharepoint-taxonomie:Term moet een sharepoint-taxonomie:parent hebben of moet de sharepoint-taxonomie:topLevelTermOf a TermSet zijn.</span><span class="sxs-lookup"><span data-stu-id="24b4f-p118">Orphaned terms are not allowed in SharePoint taxonomy. Every sharepoint-taxonomy:Term should either have a sharepoint-taxonomy:parent or it should be the sharepoint-taxonomy:topLevelTermOf a TermSet.</span></span>
- <span data-ttu-id="24b4f-323">SharePoint-taxonomie biedt geen ondersteuning voor associatierelaties.</span><span class="sxs-lookup"><span data-stu-id="24b4f-323">SharePoint taxonomy does not support associative relations.</span></span>
- <span data-ttu-id="24b4f-324">SharePoint-taxonomie is alleen geschikt voor 2 typen hiërarchische relaties: SharePoint-taxonomie: bovenliggende en SharePoint-taxonomie: onderliggend.</span><span class="sxs-lookup"><span data-stu-id="24b4f-324">SharePoint taxonomy only allows 2 types of Hierarchical relations – sharepoint-taxonomy:parent and sharepoint-Taxonomy:child.</span></span>
- <span data-ttu-id="24b4f-325">In tegenstelling tot [SKOS](https://www.w3.org/TR/skos-primer/) de hiërarchische relatie in de SharePoint-taxonomie-vocabulaire, kan de hiërarchische relatie alleen tot stand worden gebracht met termen binnen de Termenset.</span><span class="sxs-lookup"><span data-stu-id="24b4f-325">Unlike [SKOS](https://www.w3.org/TR/skos-primer/) the hierarchical relationship in SharePoint taxonomy vocabulary, can only be established with Terms within the same TermSet.</span></span>

## <a name="see-also"></a><span data-ttu-id="24b4f-326">Zie ook</span><span class="sxs-lookup"><span data-stu-id="24b4f-326">See also</span></span>

[<span data-ttu-id="24b4f-327">Een termenset met een SKOS-indeling importeren</span><span class="sxs-lookup"><span data-stu-id="24b4f-327">Import a term set using a SKOS-based format</span></span>](import-term-set-skos.md)