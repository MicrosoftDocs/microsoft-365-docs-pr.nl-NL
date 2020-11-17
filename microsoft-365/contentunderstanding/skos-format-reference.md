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
ms.openlocfilehash: 90c20ddb440e216941a5ea06f1aa815cb80102a9
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087275"
---
# <a name="skos-format-reference-for-sharepoint-taxonomy"></a><span data-ttu-id="f3218-103">SKOS-verwijzing voor SharePoint-taxonomie</span><span class="sxs-lookup"><span data-stu-id="f3218-103">SKOS format reference for SharePoint taxonomy</span></span>

<span data-ttu-id="f3218-104">Dit artikel bevat de RDF-vocabulaire die wordt gebruikt om [SharePoint-taxonomie](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) te vertegenwoordigen en is gebaseerd op [SKOS](https://www.w3.org/TR/skos-primer/).</span><span class="sxs-lookup"><span data-stu-id="f3218-104">This article includes RDF vocabulary used to represent [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) and is based on [SKOS](https://www.w3.org/TR/skos-primer/).</span></span> <span data-ttu-id="f3218-105">Gebruik RDF [SCHILDPAD](https://www.w3.org/TR/turtle/)voor de serialisatie van deze RDF-syntaxis.</span><span class="sxs-lookup"><span data-stu-id="f3218-105">For serialization of this RDF syntax, use RDF [TURTLE](https://www.w3.org/TR/turtle/).</span></span>

<span data-ttu-id="f3218-106">In de volgende tabel zie je de [SKOS](https://www.w3.org/TR/skos-primer/)- equivalenten voor de [SharePoint-taxonomie](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) woordenlijst.</span><span class="sxs-lookup"><span data-stu-id="f3218-106">The following table shows the [SKOS](https://www.w3.org/TR/skos-primer/) equivalents for the [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) vocabulary.</span></span> <span data-ttu-id="f3218-107">SharePoint biedt geen ondersteuning voor [SKOS](https://www.w3.org/TR/skos-primer/) waarden zonder SharePoint-taxonomie equivalent.</span><span class="sxs-lookup"><span data-stu-id="f3218-107">SharePoint does not support [SKOS](https://www.w3.org/TR/skos-primer/) values that have no SharePoint taxonomy equivalent.</span></span>

|<span data-ttu-id="f3218-108">SharePoint-taxonomie</span><span class="sxs-lookup"><span data-stu-id="f3218-108">SharePoint taxonomy</span></span>|<span data-ttu-id="f3218-109">SKOS-equivalent</span><span class="sxs-lookup"><span data-stu-id="f3218-109">SKOS equivalent</span></span>|
|:-----------------|:--------------|
|<span data-ttu-id="f3218-110">sharepoint-taxonomy:Term</span><span class="sxs-lookup"><span data-stu-id="f3218-110">sharepoint-taxonomy:Term</span></span>|<span data-ttu-id="f3218-111">skos: concept</span><span class="sxs-lookup"><span data-stu-id="f3218-111">skos:Concept</span></span>|
|<span data-ttu-id="f3218-112">sharepoint-taxonomy:TermSet</span><span class="sxs-lookup"><span data-stu-id="f3218-112">sharepoint-taxonomy:TermSet</span></span>|<span data-ttu-id="f3218-113">skos:ConceptScheme</span><span class="sxs-lookup"><span data-stu-id="f3218-113">skos:ConceptScheme</span></span>|
|<span data-ttu-id="f3218-114">sharepoint-taxonomy:inTermSet</span><span class="sxs-lookup"><span data-stu-id="f3218-114">sharepoint-taxonomy:inTermSet</span></span>|<span data-ttu-id="f3218-115">skos:inScheme</span><span class="sxs-lookup"><span data-stu-id="f3218-115">skos:inScheme</span></span>|
|<span data-ttu-id="f3218-116">sharepoint-taxonomy:hasTopLevelTerm</span><span class="sxs-lookup"><span data-stu-id="f3218-116">sharepoint-taxonomy:hasTopLevelTerm</span></span>|<span data-ttu-id="f3218-117">skos:hasTopConcept</span><span class="sxs-lookup"><span data-stu-id="f3218-117">skos:hasTopConcept</span></span>|
|<span data-ttu-id="f3218-118">sharepoint-taxonomy:topLevelTermOf</span><span class="sxs-lookup"><span data-stu-id="f3218-118">sharepoint-taxonomy:topLevelTermOf</span></span>|<span data-ttu-id="f3218-119">skos:topConceptOf</span><span class="sxs-lookup"><span data-stu-id="f3218-119">skos:topConceptOf</span></span>|
|<span data-ttu-id="f3218-120">sharepoint-taxonomy:defaultLabel</span><span class="sxs-lookup"><span data-stu-id="f3218-120">sharepoint-taxonomy:defaultLabel</span></span>|<span data-ttu-id="f3218-121">skos:prefLabel</span><span class="sxs-lookup"><span data-stu-id="f3218-121">skos:prefLabel</span></span>|
|<span data-ttu-id="f3218-122">sharepoint-taxonomy:termSetName</span><span class="sxs-lookup"><span data-stu-id="f3218-122">sharepoint-taxonomy:termSetName</span></span>|<span data-ttu-id="f3218-123">skos:prefLabel</span><span class="sxs-lookup"><span data-stu-id="f3218-123">skos:prefLabel</span></span>|
|<span data-ttu-id="f3218-124">sharepoint-taxonomy:propertyName</span><span class="sxs-lookup"><span data-stu-id="f3218-124">sharepoint-taxonomy:propertyName</span></span>|<span data-ttu-id="f3218-125">skos:prefLabel</span><span class="sxs-lookup"><span data-stu-id="f3218-125">skos:prefLabel</span></span>|
|<span data-ttu-id="f3218-126">sharepoint-taxonomy:otherLabel</span><span class="sxs-lookup"><span data-stu-id="f3218-126">sharepoint-taxonomy:otherLabel</span></span>|<span data-ttu-id="f3218-127">skos:altLabel</span><span class="sxs-lookup"><span data-stu-id="f3218-127">skos:altLabel</span></span>|
|<span data-ttu-id="f3218-128">sharepoint-taxonomy:description</span><span class="sxs-lookup"><span data-stu-id="f3218-128">sharepoint-taxonomy:description</span></span>|<span data-ttu-id="f3218-129">skos:definition</span><span class="sxs-lookup"><span data-stu-id="f3218-129">skos:definition</span></span>|
|<span data-ttu-id="f3218-130">sharepoint-taxonomy:parent</span><span class="sxs-lookup"><span data-stu-id="f3218-130">sharepoint-taxonomy:parent</span></span>|<span data-ttu-id="f3218-131">skos:broader</span><span class="sxs-lookup"><span data-stu-id="f3218-131">skos:broader</span></span>|
|<span data-ttu-id="f3218-132">sharepoint-taxonomy:child</span><span class="sxs-lookup"><span data-stu-id="f3218-132">sharepoint-taxonomy:child</span></span>|<span data-ttu-id="f3218-133">skos:narrower</span><span class="sxs-lookup"><span data-stu-id="f3218-133">skos:narrower</span></span>|

<span data-ttu-id="f3218-134">In de volgende tabel zie je de entiteiten van de SharePoint-taxonomie die is afgeleid van [OWL](https://www.w3.org/TR/owl2-primer/).</span><span class="sxs-lookup"><span data-stu-id="f3218-134">The following table displays the entities of the SharePoint taxonomy vocabulary derived from [OWL](https://www.w3.org/TR/owl2-primer/).</span></span>

|<span data-ttu-id="f3218-135">SharePoint-taxonomie woordenlijst</span><span class="sxs-lookup"><span data-stu-id="f3218-135">SharePoint taxonomy vocabulary</span></span>|<span data-ttu-id="f3218-136">Afgeleid van OWL</span><span class="sxs-lookup"><span data-stu-id="f3218-136">Derived from OWL</span></span>|
|:-----------------------------|:----------------------|
|<span data-ttu-id="f3218-137">sharepoint-taxonomy:isAvailableForTagging</span><span class="sxs-lookup"><span data-stu-id="f3218-137">sharepoint-taxonomy:isAvailableForTagging</span></span>|<span data-ttu-id="f3218-138">owl:datatypeproperty</span><span class="sxs-lookup"><span data-stu-id="f3218-138">owl:datatypeproperty</span></span>|
|<span data-ttu-id="f3218-139">sharepoint-taxonomy:SharedCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="f3218-139">sharepoint-taxonomy:SharedCustomPropertyForTerm</span></span>|<span data-ttu-id="f3218-140">owl:ObjectProperty</span><span class="sxs-lookup"><span data-stu-id="f3218-140">owl:ObjectProperty</span></span>|
|<span data-ttu-id="f3218-141">sharepoint-taxonomy:LocalCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="f3218-141">sharepoint-taxonomy:LocalCustomPropertyForTerm</span></span>|<span data-ttu-id="f3218-142">owl:ObjectProperty</span><span class="sxs-lookup"><span data-stu-id="f3218-142">owl:ObjectProperty</span></span>|
|<span data-ttu-id="f3218-143">sharepoint-taxonomy:CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="f3218-143">sharepoint-taxonomy:CustomPropertyForTermSet</span></span>|<span data-ttu-id="f3218-144">owl:ObjectProperty</span><span class="sxs-lookup"><span data-stu-id="f3218-144">owl:ObjectProperty</span></span>|

## <a name="sharepoint-taxonomy-vocabulary"></a><span data-ttu-id="f3218-145">SharePoint-taxonomie woordenlijst</span><span class="sxs-lookup"><span data-stu-id="f3218-145">SharePoint taxonomy vocabulary</span></span>

<span data-ttu-id="f3218-146">Een taxonomie is een formeel classificatiesysteem.</span><span class="sxs-lookup"><span data-stu-id="f3218-146">A taxonomy is a formal classification system.</span></span> <span data-ttu-id="f3218-147">In een taxonomie worden de woorden, labels en termen gegroepeerd die iets beschrijven. Vervolgens worden die groepen gerangschikt in een hiërarchie.</span><span class="sxs-lookup"><span data-stu-id="f3218-147">A taxonomy groups the words, labels, and terms that describe something, and then arranges the groups into a hierarchy.</span></span>

<span data-ttu-id="f3218-148">**sharepoint-taxonomy:Term**</span><span class="sxs-lookup"><span data-stu-id="f3218-148">**sharepoint-taxonomy:Term**</span></span>

<span data-ttu-id="f3218-149">Vertegenwoordigt een term of een trefwoord in een hiërarchie met beheerde metagegevens.</span><span class="sxs-lookup"><span data-stu-id="f3218-149">Represents a Term or a Keyword in a managed metadata hierarchy.</span></span>

<span data-ttu-id="f3218-150">Een [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) is de atomische eenheid van een SharePoint-[TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore).</span><span class="sxs-lookup"><span data-stu-id="f3218-150">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) is the atomic unit of a SharePoint [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore).</span></span> <span data-ttu-id="f3218-151">Elke [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) behoort tot een [Termenset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) die behoort tot een [TermGroep](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group).</span><span class="sxs-lookup"><span data-stu-id="f3218-151">Each [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) belongs to a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) that belongs to a [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group).</span></span> 

<span data-ttu-id="f3218-152">De syntaxis voor het definiëren van een [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) is als volgt:</span><span class="sxs-lookup"><span data-stu-id="f3218-152">The syntax to define a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) is as follows:</span></span>

```SKOS
ex:TermA    a    sharepoint-taxonomy:Term;
    sharepoint-taxonomy:inTermSet    ex:TermSetA;
    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA;
    sharepoint-taxonomy:child    ex:TermA1;
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharePoint-taxonomy:defaultLabel    “Term A”@en-us.
```

<span data-ttu-id="f3218-153">Er bestaat een [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) verplicht binnen een [Termenset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="f3218-153">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) compulsorily exists within a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="f3218-154">DefaultLabel is de naam van de [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) zoals deze wordt weergegeven in de visuele weergave.</span><span class="sxs-lookup"><span data-stu-id="f3218-154">DefaultLabel is the name of the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) as it appears in the visual representation.</span></span> <span data-ttu-id="f3218-155">De vereiste velden voor het definiëren van een [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) zijn:</span><span class="sxs-lookup"><span data-stu-id="f3218-155">The required fields for defining a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) include:</span></span>

- <span data-ttu-id="f3218-156">sharepoint-taxonomy:defaultLabel</span><span class="sxs-lookup"><span data-stu-id="f3218-156">sharepoint-taxonomy:defaultLabel</span></span>
- <span data-ttu-id="f3218-157">sharepoint-taxonomy:inTermSet</span><span class="sxs-lookup"><span data-stu-id="f3218-157">sharepoint-taxonomy:inTermSet</span></span>

<span data-ttu-id="f3218-158">Een [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) kan:</span><span class="sxs-lookup"><span data-stu-id="f3218-158">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) can:</span></span>

- <span data-ttu-id="f3218-159">Hiërarchisch gerelateerd zijn aan een andere [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) die worden vermeld in zowel de [Termen](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) behoort tot dezelfde [Termenset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="f3218-159">Be hierarchically related to another [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) that is provided both the [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) belong to the same [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>
- <span data-ttu-id="f3218-160">Meerdere onderliggende [Termen](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), maar slechts één bovenliggende [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="f3218-160">Have multiple child [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), but only a single parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>
- <span data-ttu-id="f3218-161">Er is geen bovenliggende [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)gedefinieerd, als het een topLevelTermOf een [Termenset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)is.</span><span class="sxs-lookup"><span data-stu-id="f3218-161">Not have a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) defined, if it is a topLevelTermOf a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>
- <span data-ttu-id="f3218-162">Een defaultLabel hebben, per [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore)-werktaal.</span><span class="sxs-lookup"><span data-stu-id="f3218-162">Have one defaultLabel, per [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span>
- <span data-ttu-id="f3218-163">Niet bestaan als deze geen bovenliggende [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)bevat, en niet de topLevelTermOf een [Termenset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="f3218-163">Not exist if it neither contains a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), nor is the topLevelTermOf a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> 
- <span data-ttu-id="f3218-164">Slechts een unieke defaultLabel op hetzelfde hiërarchische niveau hebben.</span><span class="sxs-lookup"><span data-stu-id="f3218-164">Have only a unique defaultLabel in the same hierarchical level.</span></span>

<span data-ttu-id="f3218-165">**sharepoint-taxonomy:TermSet**</span><span class="sxs-lookup"><span data-stu-id="f3218-165">**sharepoint-taxonomy:TermSet**</span></span>

<span data-ttu-id="f3218-166">Hiermee wordt een hiërarchische of vlakke set termobjecten aangeduid die worden aangeduid als een "Termset".</span><span class="sxs-lookup"><span data-stu-id="f3218-166">Represents a hierarchical or flat set of Term objects known as a "TermSet".</span></span>

<span data-ttu-id="f3218-167">Zoals de naam suggereertt, is Termset een set [Termen](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="f3218-167">As the name suggests, TermSet is a set of [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="f3218-168">Een [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in een [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) moet deel uitmaken van een [Termenset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="f3218-168">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in a [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) must belong to a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="f3218-169">Er kan geen [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) afzonderlijk bestaan.</span><span class="sxs-lookup"><span data-stu-id="f3218-169">No [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) can exist independently.</span></span> 

<span data-ttu-id="f3218-170">De syntaxis voor het definiëren van een [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) is:</span><span class="sxs-lookup"><span data-stu-id="f3218-170">The syntax to define a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) is:</span></span>

```SKOS
ex:TermSetA    a    sharepoint-taxonomy:TermSet;
    sharepoint-taxonomy:termSetName    “TermSet A";
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharepoint-taxonomy:hasTopLevelTerm    Ex:Term A.
```

<span data-ttu-id="f3218-171">[TermSets](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) zijn logisch gegroepeerd in [TermGroups](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group).</span><span class="sxs-lookup"><span data-stu-id="f3218-171">[TermSets](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) are logically grouped together in [TermGroups](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group).</span></span> <span data-ttu-id="f3218-172">De vereiste velden voor het definiëren van een [Termenset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) zijn:</span><span class="sxs-lookup"><span data-stu-id="f3218-172">The required field for defining a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) is:</span></span>

- <span data-ttu-id="f3218-173">sharepoint-taxonomy:termSetName</span><span class="sxs-lookup"><span data-stu-id="f3218-173">sharepoint-taxonomy:termSetName</span></span>

<span data-ttu-id="f3218-174">In het geval van het gegeven termSetName niet uniek is binnen de [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group), wordt aan het begin van de naam een nummer toegevoegd door SharePoint om de uniekheid van termSetName(s) te behouden.</span><span class="sxs-lookup"><span data-stu-id="f3218-174">In the case of the termSetName provided is not unique within the [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group), SharePoint appends a number at the end of the name to maintain the uniqueness of termSetName(s).</span></span>

<span data-ttu-id="f3218-175">**sharepoint-taxonomy:hasTopLevelTerm**</span><span class="sxs-lookup"><span data-stu-id="f3218-175">**sharepoint-taxonomy:hasTopLevelTerm**</span></span>

<span data-ttu-id="f3218-176">SharePoint gebruikt deze eigenschap om de hoogste [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) toe te wijzen aan de [Termenset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), het ingangspunt van de hiërarchie met [Termen](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in een [Termenset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="f3218-176">SharePoint uses this property to map the top most [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in the [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), which is the entry point to the hierarchy of [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="f3218-177">Dit is een inverse relatie met de SharePoint-taxonomie: topLevelTermOf.</span><span class="sxs-lookup"><span data-stu-id="f3218-177">This is an inverse relation to sharepoint-taxonomy:topLevelTermOf.</span></span> 

<span data-ttu-id="f3218-178">De syntaxis voor het definiëren hiervan is:</span><span class="sxs-lookup"><span data-stu-id="f3218-178">The syntax to define this is:</span></span>

```SKOS
ex:TermSetA    sharepoint-taxonomy:hasTopLevelTerm    ex:TermA.
```

>[!NOTE]
> <span data-ttu-id="f3218-179">Het is niet mogelijk om de [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) op het hoogste niveau van een bovenliggend [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)te definiëren.</span><span class="sxs-lookup"><span data-stu-id="f3218-179">You cannot define the top level [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) of a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="f3218-180">**sharepoint-taxonomy:topLevelTermOf**</span><span class="sxs-lookup"><span data-stu-id="f3218-180">**sharepoint-taxonomy:topLevelTermOf**</span></span>

<span data-ttu-id="f3218-181">SharePoint-taxonomie: topLevelTermOf is de inverse van SharePoint-taxonomie: hasTopLevelTerm</span><span class="sxs-lookup"><span data-stu-id="f3218-181">Sharepoint-taxonomy:topLevelTermOf is the inverse of sharepoint-taxonomy:hasTopLevelTerm</span></span>

<span data-ttu-id="f3218-182">De syntaxis voor het definiëren hiervan is:</span><span class="sxs-lookup"><span data-stu-id="f3218-182">The syntax to define this is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA.
```

<span data-ttu-id="f3218-183">**sharepoint-taxonomy:inTermSet**</span><span class="sxs-lookup"><span data-stu-id="f3218-183">**sharepoint-taxonomy:inTermSet**</span></span>

<span data-ttu-id="f3218-184">Gebruik dit om een [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) toe te wijzen aan een [Termenset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="f3218-184">Use this to map a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) to a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="f3218-185">Een [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) kan slechts bestaan in één [Termenset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="f3218-185">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) can only exist in a single [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="f3218-186">SharePoint vereist deze eigenschap bij het[definiëren van een term](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term).</span><span class="sxs-lookup"><span data-stu-id="f3218-186">SharePoint requires this property when [defining a term](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term).</span></span>

## <a name="required-labels"></a><span data-ttu-id="f3218-187">Vereiste labels</span><span class="sxs-lookup"><span data-stu-id="f3218-187">Required labels</span></span>

<span data-ttu-id="f3218-188">Het is mogelijk dat je organisatie een zorgvuldige planning moet uitvoeren voordat je beheerde metagegevens gaat gebruiken.</span><span class="sxs-lookup"><span data-stu-id="f3218-188">Your organization may want to do careful planning before you start to use managed metadata.</span></span> <span data-ttu-id="f3218-189">De hoeveelheid planning die je moet uitvoeren, hangt af van hoe formeel de taxonomie is.</span><span class="sxs-lookup"><span data-stu-id="f3218-189">The amount of planning that you must do depends on how formal your taxonomy is.</span></span> <span data-ttu-id="f3218-190">De functie is ook afhankelijk van de hoeveelheid besturingselementen die je wilt toepassen op metagegevens.</span><span class="sxs-lookup"><span data-stu-id="f3218-190">It also depends on how much control that you want to impose on metadata.</span></span> <span data-ttu-id="f3218-191">Op elk niveau van de hiërarchie moet je de vereiste labels voor een Term of Termenset configureren.</span><span class="sxs-lookup"><span data-stu-id="f3218-191">At each level of the hierarchy, you need to configure required labels for a Term or TermSet.</span></span>

<span data-ttu-id="f3218-192">Een term kan een of meer labels in de standaardtaal bevatten en nul of meer etiketten in de niet-standaardtaal.</span><span class="sxs-lookup"><span data-stu-id="f3218-192">A Term can have one or more labels in the default language, and zero or more labels in the non-default language.</span></span> <span data-ttu-id="f3218-193">Als de term labels in een taal heeft, moet een van de labels het standaardlabel zijn.</span><span class="sxs-lookup"><span data-stu-id="f3218-193">If the term has labels in a language, one of the labels must be the default label.</span></span>

<span data-ttu-id="f3218-194">**sharepoint-taxonomy:defaultLabel**</span><span class="sxs-lookup"><span data-stu-id="f3218-194">**sharepoint-taxonomy:defaultLabel**</span></span>

<span data-ttu-id="f3218-195">Gebruik dit standaard-lexicale label voor een [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) die een verplichte parameter is voor een [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="f3218-195">Use this default lexical label for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) that is a required parameter for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="f3218-196">Gebruik om de [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)visueel te representeren.</span><span class="sxs-lookup"><span data-stu-id="f3218-196">Use to visually representing the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="f3218-197">De syntaxis voor het definiëren van standaard label is:</span><span class="sxs-lookup"><span data-stu-id="f3218-197">The syntax to define a defaultLabel is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:defaultLabel    “Term A”@en-us.
```

<span data-ttu-id="f3218-198">De defaultLabel bevat twee onderdelen: de tekenreeks en de taal.</span><span class="sxs-lookup"><span data-stu-id="f3218-198">The defaultLabel contains two parts to it – the string and the language tag.</span></span> <span data-ttu-id="f3218-199">De taal moet een van de [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore)- werktalen zijn.</span><span class="sxs-lookup"><span data-stu-id="f3218-199">The language must be one of the [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working languages.</span></span> <span data-ttu-id="f3218-200">De defaultLabel moet uniek zijn voor alle [Termen](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in dezelfde [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) op hetzelfde hiërarchische niveau.</span><span class="sxs-lookup"><span data-stu-id="f3218-200">The defaultLabel must be unique for all [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in the same [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), at the same hierarchical level.</span></span>

<span data-ttu-id="f3218-201">**sharepoint-taxonomy:termSetName**</span><span class="sxs-lookup"><span data-stu-id="f3218-201">**sharepoint-taxonomy:termSetName**</span></span>

<span data-ttu-id="f3218-202">Hiermee wordt de naam opgehaald en ingesteld voor het huidige Termenset-object.</span><span class="sxs-lookup"><span data-stu-id="f3218-202">Gets and sets the name for the current TermSet object.</span></span>

<span data-ttu-id="f3218-203">Dit is het lexicale label voor een [Termenset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), in een [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore)-werktaal.</span><span class="sxs-lookup"><span data-stu-id="f3218-203">This the lexical label for a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), in a [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span> <span data-ttu-id="f3218-204">Dit is een verplichte parameter voor een [Termenset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="f3218-204">This is a required parameter for a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="f3218-205">Gebruik om de [Termenset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)visueel te representeren.</span><span class="sxs-lookup"><span data-stu-id="f3218-205">Use to visually representing a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>

<span data-ttu-id="f3218-206">De syntaxis voor het definiëren van een termSetName is:</span><span class="sxs-lookup"><span data-stu-id="f3218-206">The syntax to define a termSetName is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:TermSetName    “Term Set A”@en-us.
```

<span data-ttu-id="f3218-207">**sharepoint-taxonomy:propertyName**</span><span class="sxs-lookup"><span data-stu-id="f3218-207">**sharepoint-taxonomy:propertyName**</span></span>

<span data-ttu-id="f3218-208">Hiermee wordt de eigenschapsnaam opgehaald en ingesteld voor het huidige Termenset-object.</span><span class="sxs-lookup"><span data-stu-id="f3218-208">Gets and sets the property name for the current TermSet object.</span></span>

<span data-ttu-id="f3218-209">Dit is het lexical-label voor een SharePoint-taxonomie: SharedCustomPropertyForTerm, SharePoint-taxonomie: LocalCustomPropertyForTerm en SharePoint-taxonomie: CustomPropertyForTermSet in een [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore)-werktaal.</span><span class="sxs-lookup"><span data-stu-id="f3218-209">This is the lexical label for a sharepoint-taxonomy:SharedCustomPropertyForTerm, sharepoint-taxonomy:LocalCustomPropertyForTerm and sharepoint-taxonomy:CustomPropertyForTermSet in a [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span>

<span data-ttu-id="f3218-210">SharePoint-taxonomie: eigenschapnamen wordt behandeld als de sleutel van de CustomProperty.</span><span class="sxs-lookup"><span data-stu-id="f3218-210">The sharepoint-taxonomy:propertyName is treated as the key of the CustomProperty.</span></span>

<span data-ttu-id="f3218-211">De syntaxis voor het definiëren van een propetyName is:</span><span class="sxs-lookup"><span data-stu-id="f3218-211">The syntax to define a propetyName is:</span></span>

```SKOS
ex:SharedCustomProperty1    sharepoint-taxonomy:propertyName    “Shared Custom Property Key 1”@en-us.
```

## <a name="optional-labels"></a><span data-ttu-id="f3218-212">Optionele labels</span><span class="sxs-lookup"><span data-stu-id="f3218-212">Optional labels</span></span>

<span data-ttu-id="f3218-213">Je kunt ook optionele labels toevoegen aan je taxonomie.</span><span class="sxs-lookup"><span data-stu-id="f3218-213">You can also add optional labels to your taxonomy.</span></span>

<span data-ttu-id="f3218-214">**sharepoint-taxonomy:otherLabel**</span><span class="sxs-lookup"><span data-stu-id="f3218-214">**sharepoint-taxonomy:otherLabel**</span></span>

<span data-ttu-id="f3218-215">Dit is het alternatieve lexicale label voor een [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="f3218-215">This is the alternate lexical label for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> 

<span data-ttu-id="f3218-216">De syntaxis voor het definiëren van otherLabel is:</span><span class="sxs-lookup"><span data-stu-id="f3218-216">The syntax to define an otherLabel is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:otherLabel    “Term A”@en-us.
```

## <a name="semantic-relationships"></a><span data-ttu-id="f3218-217">Semantische relaties</span><span class="sxs-lookup"><span data-stu-id="f3218-217">Semantic relationships</span></span>

<span data-ttu-id="f3218-218">Taxonomie heeft hiërarchische en soms een simpele "gerelateerde term" associatieve relatie, maar enkele voorbeelden van "semantische relaties" of relaties met aangepaste voorwaarden.</span><span class="sxs-lookup"><span data-stu-id="f3218-218">Taxonomies have hierarchical and sometimes a simple “related term” associative relationship, but some have "semantic relationships" or custom-created relationships.</span></span> 

<span data-ttu-id="f3218-219">**sharepoint-taxonomy:parent**</span><span class="sxs-lookup"><span data-stu-id="f3218-219">**sharepoint-taxonomy:parent**</span></span>

<span data-ttu-id="f3218-220">Hiermee wordt een [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) op een andere [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="f3218-220">This hierarchically relates a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) to another [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="f3218-221">Een [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) kan een hoog niveau [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) van een [Termenset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) zijn, maar als het niet zo is moet er een bovenliggende [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) zijn.</span><span class="sxs-lookup"><span data-stu-id="f3218-221">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) could be a top level [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) of a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), but in case it doesn’t it must have a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> 

<span data-ttu-id="f3218-222">De syntaxis voor het definiëren van een bovenliggende term is:</span><span class="sxs-lookup"><span data-stu-id="f3218-222">The syntax to define a parent is:</span></span>

```SKOS
ex:TermA1    sharepoint-taxonomy:parent    ex:TermA.
```

<span data-ttu-id="f3218-223">Dit betekent dat TermA het bovenliggende en TermA het onderliggende.</span><span class="sxs-lookup"><span data-stu-id="f3218-223">This means that TermA is the parent and  TermA is the child.</span></span>

<span data-ttu-id="f3218-224">**sharepoint-taxonomy:child**</span><span class="sxs-lookup"><span data-stu-id="f3218-224">**sharepoint-taxonomy:child**</span></span>

<span data-ttu-id="f3218-225">Het object bevat een of meer onderliggende Termenset-instanties en kan worden geopend via de eigenschap TermSets.</span><span class="sxs-lookup"><span data-stu-id="f3218-225">The object contains one or more child TermSet instances, and these can be accessed through the TermSets property.</span></span> <span data-ttu-id="f3218-226">Deze klas biedt ook methoden voor het maken van nieuwe onderliggende Termenset-objecten.</span><span class="sxs-lookup"><span data-stu-id="f3218-226">This class also provides methods for creating new child TermSet objects.</span></span> <span data-ttu-id="f3218-227">De machtigingen voor het bewerken van onderliggende termen en Termenset-exemplaren zijn opgegeven voor de groep.</span><span class="sxs-lookup"><span data-stu-id="f3218-227">Permissions for editing child Term and TermSet instances is specified on the group.</span></span> 

<span data-ttu-id="f3218-228">Hiermee wordt een [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) op een andere [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="f3218-228">This hierarchically relates a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) to another [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="f3218-229">De syntaxis voor het definiëren van een onderliggende term is:</span><span class="sxs-lookup"><span data-stu-id="f3218-229">The syntax to define a child is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:child    ex:TermA1.
```

<span data-ttu-id="f3218-230">Dit betekent dat TermA het bovenliggende en TermA het onderliggende.</span><span class="sxs-lookup"><span data-stu-id="f3218-230">This means that TermA is the parent and  TermA is the child.</span></span>

## <a name="documentation-notes"></a><span data-ttu-id="f3218-231">Documentatienotities</span><span class="sxs-lookup"><span data-stu-id="f3218-231">Documentation notes</span></span>

<span data-ttu-id="f3218-232">In deze sectie wordt de taxonomie besproken die wordt beschreven in de Naamruimte Microsoft.SharePoint-taxonomie.</span><span class="sxs-lookup"><span data-stu-id="f3218-232">This section discusses the taxonomy detailed in the Microsoft.SharePoint.Taxonomy Namespace.</span></span>

<span data-ttu-id="f3218-233">**sharepoint-taxonomy:description**</span><span class="sxs-lookup"><span data-stu-id="f3218-233">**sharepoint-taxonomy:description**</span></span>

<span data-ttu-id="f3218-234">Dit is een gedetailleerde uitleg van een [SharePoint-taxonomie](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) vocabulaire-entiteit.</span><span class="sxs-lookup"><span data-stu-id="f3218-234">This is a detailed explanation of any [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) vocabulary entity.</span></span> 

<span data-ttu-id="f3218-235">De syntaxis om een beschrijving toe te voegen is:</span><span class="sxs-lookup"><span data-stu-id="f3218-235">The syntax to add a description is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:description    “Term A is the top level term of TermSetA”@en-us.
```

## <a name="custom-properties"></a><span data-ttu-id="f3218-236">Aangepaste eigenschappen</span><span class="sxs-lookup"><span data-stu-id="f3218-236">Custom properties</span></span>

<span data-ttu-id="f3218-237">Hiermee haal je een verzameling aangepaste eigenschapsobjecten op voor de huidige objectterm uit de alleen-lezen woordenlijst.</span><span class="sxs-lookup"><span data-stu-id="f3218-237">Gets the collection of custom property objects for the current Term object from the read-only dictionary.</span></span>

<span data-ttu-id="f3218-238">Aangepaste eigenschappen zijn sleutelwaarden paren die kunnen worden gedefinieerd voor een [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) of een [Termenset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), om de beschrijving van de [Termen](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) of een [Termenset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) te bevorderen.</span><span class="sxs-lookup"><span data-stu-id="f3218-238">Custom Properties are key-values pairs that can be defined for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), to further the description of the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="f3218-239">SharePoint geeft de sleutel van de aangepaste eigenschap aan met behulp van propertyName.</span><span class="sxs-lookup"><span data-stu-id="f3218-239">SharePoint specifies the key of the custom property with the help of propertyName.</span></span>

<span data-ttu-id="f3218-240">**sharepoint-taxonomy:CustomPropertyForTermSet**</span><span class="sxs-lookup"><span data-stu-id="f3218-240">**sharepoint-taxonomy:CustomPropertyForTermSet**</span></span>

<span data-ttu-id="f3218-241">De syntaxis voor het definiëren hiervan is:</span><span class="sxs-lookup"><span data-stu-id="f3218-241">The syntax to define this is:</span></span>

```SKOS
ex:CustomProp1    rdf:type    sharepoint-taxonomy:CustomPropertyForTermSet;
    sharepoint-taxonomy:propertyName “Colour”.

ex:TermSetA    ex:CustomProp1    “Red”@en-us.
```

<span data-ttu-id="f3218-242">**sharepoint-taxonomy:SharedCustomPropertyForTerm**</span><span class="sxs-lookup"><span data-stu-id="f3218-242">**sharepoint-taxonomy:SharedCustomPropertyForTerm**</span></span>

<span data-ttu-id="f3218-243">Als de aangepaste eigenschap voor een [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) moet worden meegenomen aan de [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), moet je de [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) vervolgens op de gewenste locatie definiëren onder SharedCustomPropertyForTerm.</span><span class="sxs-lookup"><span data-stu-id="f3218-243">If the custom property for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) needs to be carried along with the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), when you reuse the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) somewhere else, then you need to be define it under SharedCustomPropertyForTerm.</span></span>

<span data-ttu-id="f3218-244">De syntaxis voor het definiëren hiervan is:</span><span class="sxs-lookup"><span data-stu-id="f3218-244">The syntax to define this is:</span></span>

``` SKOS
ex:CustomProp2    rdf:type sharepoint-taxonomy:SharedCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “Length”.

ex:TermA    ex:CustomProp2    “5 cm”@en-us.
```
<span data-ttu-id="f3218-245">**sharepoint-taxonomy:LocalCustomPropertyForTerm**</span><span class="sxs-lookup"><span data-stu-id="f3218-245">**sharepoint-taxonomy:LocalCustomPropertyForTerm**</span></span>

<span data-ttu-id="f3218-246">Als de aangepaste eigenschap voor een [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) niet moet worden meegenomen met de [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), moet je de [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) vervolgens op de gewenste locatie definiëren onder LocalCustomPropertyForTerm.</span><span class="sxs-lookup"><span data-stu-id="f3218-246">If the custom property for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) does not need to be carried along with the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), when you reuse the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) somewhere else, then you need to define it under LocalCustomPropertyForTerm.</span></span>

<span data-ttu-id="f3218-247">De syntaxis voor het definiëren hiervan is:</span><span class="sxs-lookup"><span data-stu-id="f3218-247">The syntax to define this is:</span></span>

```SKOS
ex:CustomProp3    rdf:type sharepoint-taxonomy:LocalCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “width”.

ex:TermA    ex:CustomProp3    “5 cm”@en-us.
```

## <a name="data-properties"></a><span data-ttu-id="f3218-248">Gegevenseigenschappen</span><span class="sxs-lookup"><span data-stu-id="f3218-248">Data properties</span></span>

<span data-ttu-id="f3218-249">Op elk niveau van de hiërarchie moet je de specifieke gegevenseigenschappen voor een Term of Termenset configureren.</span><span class="sxs-lookup"><span data-stu-id="f3218-249">At each level of the hierarchy, you can configure specific data properties for a Term or TermSet.</span></span>

<span data-ttu-id="f3218-250">**sharepoint-taxonomy:isAvailableForTagging**</span><span class="sxs-lookup"><span data-stu-id="f3218-250">**sharepoint-taxonomy:isAvailableForTagging**</span></span>

<span data-ttu-id="f3218-251">Gebruik deze instelling om op te geven of een [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) of een [Termenset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) die beschikbaar is in SharePoint-lijsten en - bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="f3218-251">Use this to specify if a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) available in SharePoint Lists and Libraries.</span></span>  

<span data-ttu-id="f3218-252">De syntaxis voor dit is als volgt:</span><span class="sxs-lookup"><span data-stu-id="f3218-252">The syntax for this is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:isAvailableForTagging     "true"^^xsd:Boolean;
```

## <a name="domain-and-range"></a><span data-ttu-id="f3218-253">Domein en bereik</span><span class="sxs-lookup"><span data-stu-id="f3218-253">Domain and range</span></span>

<span data-ttu-id="f3218-254">In de volgende tabel vind je een beschrijving van het domein en het bereik van de SharePoint-taxonomie woordenlijst.</span><span class="sxs-lookup"><span data-stu-id="f3218-254">The table below describes the domain and range of SharePoint taxonomy vocabulary.</span></span>

|<span data-ttu-id="f3218-255">Predikaten/werkwoord</span><span class="sxs-lookup"><span data-stu-id="f3218-255">Predicates/verb</span></span>|<span data-ttu-id="f3218-256">Betekenis</span><span class="sxs-lookup"><span data-stu-id="f3218-256">Meaning</span></span>|<span data-ttu-id="f3218-257">Domein</span><span class="sxs-lookup"><span data-stu-id="f3218-257">Domain</span></span>|<span data-ttu-id="f3218-258">Bereik</span><span class="sxs-lookup"><span data-stu-id="f3218-258">Range</span></span>|
|:--------------|:------|:-----|:----|
<span data-ttu-id="f3218-259">inTermSet</span><span class="sxs-lookup"><span data-stu-id="f3218-259">inTermSet</span></span>|<span data-ttu-id="f3218-260">In Termenset</span><span class="sxs-lookup"><span data-stu-id="f3218-260">In term set</span></span>|<span data-ttu-id="f3218-261">Term</span><span class="sxs-lookup"><span data-stu-id="f3218-261">Term</span></span>|<span data-ttu-id="f3218-262">Termenset</span><span class="sxs-lookup"><span data-stu-id="f3218-262">Term Set</span></span>|
<span data-ttu-id="f3218-263">inTermGroup</span><span class="sxs-lookup"><span data-stu-id="f3218-263">inTermGroup</span></span>|<span data-ttu-id="f3218-264">In termgroep</span><span class="sxs-lookup"><span data-stu-id="f3218-264">In term group</span></span>|<span data-ttu-id="f3218-265">TermSet</span><span class="sxs-lookup"><span data-stu-id="f3218-265">TermSet</span></span>|<span data-ttu-id="f3218-266">TermGroup</span><span class="sxs-lookup"><span data-stu-id="f3218-266">TermGroup</span></span>|
<span data-ttu-id="f3218-267">topLevelTermOf</span><span class="sxs-lookup"><span data-stu-id="f3218-267">topLevelTermOf</span></span>|<span data-ttu-id="f3218-268">Is het hoogste niveau van</span><span class="sxs-lookup"><span data-stu-id="f3218-268">Is Top Level Term Of</span></span>|<span data-ttu-id="f3218-269">Term</span><span class="sxs-lookup"><span data-stu-id="f3218-269">Term</span></span>|<span data-ttu-id="f3218-270">TermSet</span><span class="sxs-lookup"><span data-stu-id="f3218-270">TermSet</span></span>|
<span data-ttu-id="f3218-271">hasTopLevelTerm</span><span class="sxs-lookup"><span data-stu-id="f3218-271">hasTopLevelTerm</span></span>|<span data-ttu-id="f3218-272">Heeft het hoogste niveau term</span><span class="sxs-lookup"><span data-stu-id="f3218-272">Has top level term</span></span>|<span data-ttu-id="f3218-273">Termenset</span><span class="sxs-lookup"><span data-stu-id="f3218-273">Term Set</span></span>|<span data-ttu-id="f3218-274">Term</span><span class="sxs-lookup"><span data-stu-id="f3218-274">Term</span></span>|
<span data-ttu-id="f3218-275">termSetName</span><span class="sxs-lookup"><span data-stu-id="f3218-275">termSetName</span></span>|<span data-ttu-id="f3218-276">Termenset heeft naam</span><span class="sxs-lookup"><span data-stu-id="f3218-276">Term set has Name</span></span>|<span data-ttu-id="f3218-277">Term</span><span class="sxs-lookup"><span data-stu-id="f3218-277">Term</span></span>|<span data-ttu-id="f3218-278">Letterlijke tekst zonder opmaak</span><span class="sxs-lookup"><span data-stu-id="f3218-278">Plain literal</span></span>|
<span data-ttu-id="f3218-279">defaultLabel</span><span class="sxs-lookup"><span data-stu-id="f3218-279">defaultLabel</span></span>|<span data-ttu-id="f3218-280">Term heeft een standaardlabel</span><span class="sxs-lookup"><span data-stu-id="f3218-280">Term has default label</span></span>|<span data-ttu-id="f3218-281">Term</span><span class="sxs-lookup"><span data-stu-id="f3218-281">Term</span></span>|<span data-ttu-id="f3218-282">Letterlijke tekst zonder opmaak</span><span class="sxs-lookup"><span data-stu-id="f3218-282">Plain literal</span></span>|
<span data-ttu-id="f3218-283">otherLabel</span><span class="sxs-lookup"><span data-stu-id="f3218-283">otherLabel</span></span>|<span data-ttu-id="f3218-284">Term heeft een ander label</span><span class="sxs-lookup"><span data-stu-id="f3218-284">Term has other label</span></span>|<span data-ttu-id="f3218-285">Term</span><span class="sxs-lookup"><span data-stu-id="f3218-285">Term</span></span>|<span data-ttu-id="f3218-286">Letterlijke tekst zonder opmaak</span><span class="sxs-lookup"><span data-stu-id="f3218-286">Plain literal</span></span>|
<span data-ttu-id="f3218-287">propertyName</span><span class="sxs-lookup"><span data-stu-id="f3218-287">propertyName</span></span>|<span data-ttu-id="f3218-288">Heeft eigenschapslabel</span><span class="sxs-lookup"><span data-stu-id="f3218-288">Has Property Label</span></span>|<span data-ttu-id="f3218-289">SharedCustomPropertyForTerm, LocalCustomPropertyForTerm, CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="f3218-289">SharedCustomPropertyForTerm, LocalCustomPropertyForTerm, CustomPropertyForTermSet</span></span> |<span data-ttu-id="f3218-290">Boolean, String, Integer, Decimal, Double</span><span class="sxs-lookup"><span data-stu-id="f3218-290">Boolean, String, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="f3218-291">beschrijving</span><span class="sxs-lookup"><span data-stu-id="f3218-291">description</span></span>|<span data-ttu-id="f3218-292">Heeft beschrijving</span><span class="sxs-lookup"><span data-stu-id="f3218-292">Has Description</span></span>|<span data-ttu-id="f3218-293">Alle</span><span class="sxs-lookup"><span data-stu-id="f3218-293">All</span></span>|<span data-ttu-id="f3218-294">Letterlijke tekst zonder opmaak</span><span class="sxs-lookup"><span data-stu-id="f3218-294">Plain literal</span></span>|
|<span data-ttu-id="f3218-295">Bovenliggend</span><span class="sxs-lookup"><span data-stu-id="f3218-295">parent</span></span>|<span data-ttu-id="f3218-296">Heeft bovenliggend element</span><span class="sxs-lookup"><span data-stu-id="f3218-296">Has parent</span></span>|<span data-ttu-id="f3218-297">Term</span><span class="sxs-lookup"><span data-stu-id="f3218-297">Term</span></span>|<span data-ttu-id="f3218-298">Term</span><span class="sxs-lookup"><span data-stu-id="f3218-298">Term</span></span>|
|<span data-ttu-id="f3218-299">onderliggend element</span><span class="sxs-lookup"><span data-stu-id="f3218-299">child</span></span>|<span data-ttu-id="f3218-300">Heeft onderliggend element</span><span class="sxs-lookup"><span data-stu-id="f3218-300">Has Child</span></span>|<span data-ttu-id="f3218-301">Term</span><span class="sxs-lookup"><span data-stu-id="f3218-301">Term</span></span>|<span data-ttu-id="f3218-302">Term</span><span class="sxs-lookup"><span data-stu-id="f3218-302">Term</span></span>|
|<span data-ttu-id="f3218-303">isAvailableForTagging</span><span class="sxs-lookup"><span data-stu-id="f3218-303">isAvailableForTagging</span></span>|<span data-ttu-id="f3218-304">Is beschikbaar voor labelen</span><span class="sxs-lookup"><span data-stu-id="f3218-304">Is available for tagging</span></span>|<span data-ttu-id="f3218-305">Term, Termenset</span><span class="sxs-lookup"><span data-stu-id="f3218-305">Term, Term Set</span></span>|<span data-ttu-id="f3218-306">Booleaanse waarde</span><span class="sxs-lookup"><span data-stu-id="f3218-306">Boolean</span></span>|
|<span data-ttu-id="f3218-307">SharedCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="f3218-307">SharedCustomPropertyForTerm</span></span>|<span data-ttu-id="f3218-308">Heeft aangepaste eigenschap gedeeld</span><span class="sxs-lookup"><span data-stu-id="f3218-308">Has shared custom property</span></span>|<span data-ttu-id="f3218-309">Term</span><span class="sxs-lookup"><span data-stu-id="f3218-309">Term</span></span>|<span data-ttu-id="f3218-310">Boolean, String, Integer, Decimal, Double</span><span class="sxs-lookup"><span data-stu-id="f3218-310">Boolean, string, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="f3218-311">LocalCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="f3218-311">LocalCustomPropertyForTerm</span></span>|<span data-ttu-id="f3218-312">Heeft lokale aangepaste eigenschap</span><span class="sxs-lookup"><span data-stu-id="f3218-312">Has local custom property</span></span>|<span data-ttu-id="f3218-313">Term</span><span class="sxs-lookup"><span data-stu-id="f3218-313">Term</span></span>|<span data-ttu-id="f3218-314">Boolean, String, Integer, Decimal, Double</span><span class="sxs-lookup"><span data-stu-id="f3218-314">Boolean, String, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="f3218-315">CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="f3218-315">CustomPropertyForTermSet</span></span>|<span data-ttu-id="f3218-316">Heeft aangepaste eigenschap</span><span class="sxs-lookup"><span data-stu-id="f3218-316">Has Custom Property</span></span>|<span data-ttu-id="f3218-317">TermSet</span><span class="sxs-lookup"><span data-stu-id="f3218-317">TermSet</span></span>|<span data-ttu-id="f3218-318">Boolean, String, Integer, Decimal, Double</span><span class="sxs-lookup"><span data-stu-id="f3218-318">Boolean, String, Integer, Decimal, Double</span></span>|

<span data-ttu-id="f3218-319">[SKOS](https://www.w3.org/TR/skos-primer/) geldige scenario's die [ SharePoint-taxonomie](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) niet is toegestaan:</span><span class="sxs-lookup"><span data-stu-id="f3218-319">[SKOS](https://www.w3.org/TR/skos-primer/) valid scenarios that [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) does not allow:</span></span>

- <span data-ttu-id="f3218-320">Hiërarchische redundantie - een [SKOS](https://www.w3.org/TR/skos-primer/) concept kan tegelijk met meerdere bredere concepten worden bijgevoegd, maar een SharePoint-taxonomie: kan slechts één SharePoint-taxonomie bevatten: bovenliggend, dus cyclische afhankelijkheid van termen is ook niet toegestaan.</span><span class="sxs-lookup"><span data-stu-id="f3218-320">Hierarchical redundancy - A [SKOS](https://www.w3.org/TR/skos-primer/) concept can be attached to several broader concepts at the same time, but a sharepoint-taxonomy:Term can have only one sharepoint-taxonomy:parent, hence cyclic dependency, of Terms is also not allowed.</span></span>
- <span data-ttu-id="f3218-321">Zwevende termen zijn niet toegestaan in een SharePoint-taxonomie.</span><span class="sxs-lookup"><span data-stu-id="f3218-321">Orphaned terms are not allowed in SharePoint taxonomy.</span></span> <span data-ttu-id="f3218-322">Elke SharePoint-taxonomie: begrip moet een SharePoint-taxonomie: bovenliggende of de SharePoint-taxonomie zijn: topLevelTermOf een Termenset.</span><span class="sxs-lookup"><span data-stu-id="f3218-322">Every sharepoint-taxonomy:Term should either have a sharepoint-taxonomy:parent or it should be the sharepoint-taxonomy:topLevelTermOf a TermSet.</span></span>
- <span data-ttu-id="f3218-323">SharePoint-taxonomie biedt geen ondersteuning voor associatierelaties.</span><span class="sxs-lookup"><span data-stu-id="f3218-323">SharePoint taxonomy does not support associative relations.</span></span>
- <span data-ttu-id="f3218-324">SharePoint-taxonomie is alleen geschikt voor 2 typen hiërarchische relaties: SharePoint-taxonomie: bovenliggende en SharePoint-taxonomie: onderliggend.</span><span class="sxs-lookup"><span data-stu-id="f3218-324">SharePoint taxonomy only allows 2 types of Hierarchical relations – sharepoint-taxonomy:parent and sharepoint-Taxonomy:child.</span></span> 
- <span data-ttu-id="f3218-325">In tegenstelling tot [SKOS](https://www.w3.org/TR/skos-primer/) de hiërarchische relatie in de SharePoint-taxonomie-vocabulaire, kan de hiërarchische relatie alleen tot stand worden gebracht met termen binnen de Termenset.</span><span class="sxs-lookup"><span data-stu-id="f3218-325">Unlike [SKOS](https://www.w3.org/TR/skos-primer/) the hierarchical relationship in SharePoint taxonomy vocabulary, can only be established with Terms within the same TermSet.</span></span>

## <a name="see-also"></a><span data-ttu-id="f3218-326">Zie ook</span><span class="sxs-lookup"><span data-stu-id="f3218-326">See also</span></span>

[<span data-ttu-id="f3218-327">Een termenset met een SKOS-indeling importeren</span><span class="sxs-lookup"><span data-stu-id="f3218-327">Import a term set using a SKOS-based format</span></span>](import-term-set-skos.md)

