---
title: SKOS-indelings overzicht voor SharePoint-taxonomie
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
description: SKOS-indelings overzicht voor SharePoint-taxonomie
ms.openlocfilehash: eb228394b06b6e6027937ab105df7c0079875226
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295894"
---
# <a name="skos-format-reference-for-sharepoint-taxonomy"></a><span data-ttu-id="a33be-103">SKOS-indelings overzicht voor SharePoint-taxonomie</span><span class="sxs-lookup"><span data-stu-id="a33be-103">SKOS format reference for SharePoint taxonomy</span></span>

<span data-ttu-id="a33be-104">Dit artikel bevat de RDF-vocabulaire die wordt gebruikt voor de weergave van de [SharePoint-taxonomie](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) en is gebaseerd op [skos](https://www.w3.org/TR/skos-primer/).</span><span class="sxs-lookup"><span data-stu-id="a33be-104">This article includes RDF vocabulary used to represent [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) and is based on [SKOS](https://www.w3.org/TR/skos-primer/).</span></span> <span data-ttu-id="a33be-105">Voor serialisatie van deze RDF-syntaxis gebruikt u RDF [TURTLE](https://www.w3.org/TR/turtle/).</span><span class="sxs-lookup"><span data-stu-id="a33be-105">For serialization of this RDF syntax, use RDF [TURTLE](https://www.w3.org/TR/turtle/).</span></span>

<span data-ttu-id="a33be-106">In de volgende tabel worden de [skos](https://www.w3.org/TR/skos-primer/) -equivalenten voor de [SharePoint-taxonomie](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) terminologie weergegeven.</span><span class="sxs-lookup"><span data-stu-id="a33be-106">The following table shows the [SKOS](https://www.w3.org/TR/skos-primer/) equivalents for the [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) vocabulary.</span></span> <span data-ttu-id="a33be-107">SharePoint biedt geen ondersteuning voor [skos](https://www.w3.org/TR/skos-primer/) -waarden zonder SharePoint-taxonomie equivalent.</span><span class="sxs-lookup"><span data-stu-id="a33be-107">SharePoint does not support [SKOS](https://www.w3.org/TR/skos-primer/) values that have no SharePoint taxonomy equivalent.</span></span>

|<span data-ttu-id="a33be-108">SharePoint-taxonomie</span><span class="sxs-lookup"><span data-stu-id="a33be-108">SharePoint taxonomy</span></span>|<span data-ttu-id="a33be-109">SKOS-equivalent</span><span class="sxs-lookup"><span data-stu-id="a33be-109">SKOS equivalent</span></span>|
|:-----------------|:--------------|
|<span data-ttu-id="a33be-110">SharePoint-taxonomie: term</span><span class="sxs-lookup"><span data-stu-id="a33be-110">sharepoint-taxonomy:Term</span></span>|<span data-ttu-id="a33be-111">skos: concept</span><span class="sxs-lookup"><span data-stu-id="a33be-111">skos:Concept</span></span>|
|<span data-ttu-id="a33be-112">SharePoint-taxonomie: Termenset</span><span class="sxs-lookup"><span data-stu-id="a33be-112">sharepoint-taxonomy:TermSet</span></span>|<span data-ttu-id="a33be-113">skos:ConceptScheme</span><span class="sxs-lookup"><span data-stu-id="a33be-113">skos:ConceptScheme</span></span>|
|<span data-ttu-id="a33be-114">SharePoint-taxonomie: intermenset</span><span class="sxs-lookup"><span data-stu-id="a33be-114">sharepoint-taxonomy:inTermSet</span></span>|<span data-ttu-id="a33be-115">skos: schema</span><span class="sxs-lookup"><span data-stu-id="a33be-115">skos:inScheme</span></span>|
|<span data-ttu-id="a33be-116">SharePoint-taxonomie: hasTopLevelTerm</span><span class="sxs-lookup"><span data-stu-id="a33be-116">sharepoint-taxonomy:hasTopLevelTerm</span></span>|<span data-ttu-id="a33be-117">skos:hasTopConcept</span><span class="sxs-lookup"><span data-stu-id="a33be-117">skos:hasTopConcept</span></span>|
|<span data-ttu-id="a33be-118">SharePoint-taxonomie: topLevelTermOf</span><span class="sxs-lookup"><span data-stu-id="a33be-118">sharepoint-taxonomy:topLevelTermOf</span></span>|<span data-ttu-id="a33be-119">skos:topConceptOf</span><span class="sxs-lookup"><span data-stu-id="a33be-119">skos:topConceptOf</span></span>|
|<span data-ttu-id="a33be-120">SharePoint-taxonomie: defaultLabel</span><span class="sxs-lookup"><span data-stu-id="a33be-120">sharepoint-taxonomy:defaultLabel</span></span>|<span data-ttu-id="a33be-121">skos:prefLabel</span><span class="sxs-lookup"><span data-stu-id="a33be-121">skos:prefLabel</span></span>|
|<span data-ttu-id="a33be-122">SharePoint-taxonomie: termSetName</span><span class="sxs-lookup"><span data-stu-id="a33be-122">sharepoint-taxonomy:termSetName</span></span>|<span data-ttu-id="a33be-123">skos:prefLabel</span><span class="sxs-lookup"><span data-stu-id="a33be-123">skos:prefLabel</span></span>|
|<span data-ttu-id="a33be-124">SharePoint-taxonomie: eigenschaps</span><span class="sxs-lookup"><span data-stu-id="a33be-124">sharepoint-taxonomy:propertyName</span></span>|<span data-ttu-id="a33be-125">skos:prefLabel</span><span class="sxs-lookup"><span data-stu-id="a33be-125">skos:prefLabel</span></span>|
|<span data-ttu-id="a33be-126">SharePoint-taxonomie: otherLabel</span><span class="sxs-lookup"><span data-stu-id="a33be-126">sharepoint-taxonomy:otherLabel</span></span>|<span data-ttu-id="a33be-127">skos:altLabel</span><span class="sxs-lookup"><span data-stu-id="a33be-127">skos:altLabel</span></span>|
|<span data-ttu-id="a33be-128">SharePoint-taxonomie: beschrijving</span><span class="sxs-lookup"><span data-stu-id="a33be-128">sharepoint-taxonomy:description</span></span>|<span data-ttu-id="a33be-129">skos: definitie</span><span class="sxs-lookup"><span data-stu-id="a33be-129">skos:definition</span></span>|
|<span data-ttu-id="a33be-130">SharePoint-taxonomie: bovenliggend element</span><span class="sxs-lookup"><span data-stu-id="a33be-130">sharepoint-taxonomy:parent</span></span>|<span data-ttu-id="a33be-131">skos: bredere</span><span class="sxs-lookup"><span data-stu-id="a33be-131">skos:broader</span></span>|
|<span data-ttu-id="a33be-132">SharePoint-taxonomie: onderliggend</span><span class="sxs-lookup"><span data-stu-id="a33be-132">sharepoint-taxonomy:child</span></span>|<span data-ttu-id="a33be-133">skos: smaller</span><span class="sxs-lookup"><span data-stu-id="a33be-133">skos:narrower</span></span>|

<span data-ttu-id="a33be-134">In de volgende tabel ziet u de entiteiten van de SharePoint-taxonomie van de SharePoint-taxonomie afgeleid van [Owl](https://www.w3.org/TR/owl2-primer/).</span><span class="sxs-lookup"><span data-stu-id="a33be-134">The following table displays the entities of the SharePoint taxonomy vocabulary derived from [OWL](https://www.w3.org/TR/owl2-primer/).</span></span>

|<span data-ttu-id="a33be-135">Vocabulaire van SharePoint-taxonomie</span><span class="sxs-lookup"><span data-stu-id="a33be-135">SharePoint taxonomy vocabulary</span></span>|<span data-ttu-id="a33be-136">Afgeleid van OWL</span><span class="sxs-lookup"><span data-stu-id="a33be-136">Derived from OWL</span></span>|
|:-----------------------------|:----------------------|
|<span data-ttu-id="a33be-137">SharePoint-taxonomie: isAvailableForTagging</span><span class="sxs-lookup"><span data-stu-id="a33be-137">sharepoint-taxonomy:isAvailableForTagging</span></span>|<span data-ttu-id="a33be-138">owl:datatypeproperty</span><span class="sxs-lookup"><span data-stu-id="a33be-138">owl:datatypeproperty</span></span>|
|<span data-ttu-id="a33be-139">SharePoint-taxonomie: SharedCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="a33be-139">sharepoint-taxonomy:SharedCustomPropertyForTerm</span></span>|<span data-ttu-id="a33be-140">owl:ObjectProperty</span><span class="sxs-lookup"><span data-stu-id="a33be-140">owl:ObjectProperty</span></span>|
|<span data-ttu-id="a33be-141">SharePoint-taxonomie: LocalCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="a33be-141">sharepoint-taxonomy:LocalCustomPropertyForTerm</span></span>|<span data-ttu-id="a33be-142">owl:ObjectProperty</span><span class="sxs-lookup"><span data-stu-id="a33be-142">owl:ObjectProperty</span></span>|
|<span data-ttu-id="a33be-143">SharePoint-taxonomie: CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="a33be-143">sharepoint-taxonomy:CustomPropertyForTermSet</span></span>|<span data-ttu-id="a33be-144">owl:ObjectProperty</span><span class="sxs-lookup"><span data-stu-id="a33be-144">owl:ObjectProperty</span></span>|

## <a name="sharepoint-taxonomy-vocabulary"></a><span data-ttu-id="a33be-145">Vocabulaire van SharePoint-taxonomie</span><span class="sxs-lookup"><span data-stu-id="a33be-145">SharePoint taxonomy vocabulary</span></span>

<span data-ttu-id="a33be-146">Een taxonomie is een formele classificatiesysteem.</span><span class="sxs-lookup"><span data-stu-id="a33be-146">A taxonomy is a formal classification system.</span></span> <span data-ttu-id="a33be-147">Een taxonomiegroepen de woorden, labels en voorwaarden die een beschrijving beschrijven en de groepen worden vervolgens ingedeeld in een hiërarchie.</span><span class="sxs-lookup"><span data-stu-id="a33be-147">A taxonomy groups the words, labels, and terms that describe something, and then arranges the groups into a hierarchy.</span></span>

<span data-ttu-id="a33be-148">**SharePoint-taxonomie: term**</span><span class="sxs-lookup"><span data-stu-id="a33be-148">**sharepoint-taxonomy:Term**</span></span>

<span data-ttu-id="a33be-149">Vertegenwoordigt een term of een trefwoord in een hiërarchie met beheerde metagegevens.</span><span class="sxs-lookup"><span data-stu-id="a33be-149">Represents a Term or a Keyword in a managed metadata hierarchy.</span></span>

<span data-ttu-id="a33be-150">Een [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) is de atoom eenheid van een SharePoint- [Archief](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore).</span><span class="sxs-lookup"><span data-stu-id="a33be-150">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) is the atomic unit of a SharePoint [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore).</span></span> <span data-ttu-id="a33be-151">Elke [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) behoort tot een [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) die deel uitmaakt van een [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group).</span><span class="sxs-lookup"><span data-stu-id="a33be-151">Each [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) belongs to a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) that belongs to a [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group).</span></span> 

<span data-ttu-id="a33be-152">De syntaxis voor het definiëren van een [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) is als volgt:</span><span class="sxs-lookup"><span data-stu-id="a33be-152">The syntax to define a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) is as follows:</span></span>

```SKOS
ex:TermA    a    sharepoint-taxonomy:Term;
    sharepoint-taxonomy:inTermSet    ex:TermSetA;
    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA;
    sharepoint-taxonomy:child    ex:TermA1;
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharePoint-taxonomy:defaultLabel    “Term A”@en-us.
```

<span data-ttu-id="a33be-153">Een [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) voorkomt binnen een [termenset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="a33be-153">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) compulsorily exists within a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="a33be-154">DefaultLabel is de naam van de [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) zoals weergegeven in de visuele weergave.</span><span class="sxs-lookup"><span data-stu-id="a33be-154">DefaultLabel is the name of the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) as it appears in the visual representation.</span></span> <span data-ttu-id="a33be-155">De verplichte velden voor het definiëren van een [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) zijn onder meer:</span><span class="sxs-lookup"><span data-stu-id="a33be-155">The required fields for defining a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) include:</span></span>

- <span data-ttu-id="a33be-156">SharePoint-taxonomie: defaultLabel</span><span class="sxs-lookup"><span data-stu-id="a33be-156">sharepoint-taxonomy:defaultLabel</span></span>
- <span data-ttu-id="a33be-157">SharePoint-taxonomie: intermenset</span><span class="sxs-lookup"><span data-stu-id="a33be-157">sharepoint-taxonomy:inTermSet</span></span>

<span data-ttu-id="a33be-158">Een [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) kan:</span><span class="sxs-lookup"><span data-stu-id="a33be-158">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) can:</span></span>

- <span data-ttu-id="a33be-159">Zorg dat u aan een andere [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) die niet wordt vermeld, [in een andere](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) term moet worden weer [gegeven.](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)</span><span class="sxs-lookup"><span data-stu-id="a33be-159">Be hierarchically related to another [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) that is provided both the [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) belong to the same [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>
- <span data-ttu-id="a33be-160">Meerdere onderliggende [termen](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)hebben, maar slechts één bovenliggende [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="a33be-160">Have multiple child [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), but only a single parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>
- <span data-ttu-id="a33be-161">Er is geen bovenliggende [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) gedefinieerd, als dit een topLevelTermOf is van een [termenset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="a33be-161">Not have a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) defined, if it is a topLevelTermOf a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>
- <span data-ttu-id="a33be-162">Eén defaultLabel [, per werk](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) woorden.</span><span class="sxs-lookup"><span data-stu-id="a33be-162">Have one defaultLabel, per [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span>
- <span data-ttu-id="a33be-163">Niet aanwezig als het geen bovenliggende [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)bevat, noch de TopLevelTermOf een [termenset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="a33be-163">Not exist if it neither contains a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), nor is the topLevelTermOf a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> 
- <span data-ttu-id="a33be-164">Alleen een unieke defaultLabel op hetzelfde hiërarchische niveau hebben.</span><span class="sxs-lookup"><span data-stu-id="a33be-164">Have only a unique defaultLabel in the same hierarchical level.</span></span>

<span data-ttu-id="a33be-165">**SharePoint-taxonomie: Termenset**</span><span class="sxs-lookup"><span data-stu-id="a33be-165">**sharepoint-taxonomy:TermSet**</span></span>

<span data-ttu-id="a33be-166">Voorbeeld van een hiërarchische of vlakke set termen objecten die een term ' Termset ' genoemd.</span><span class="sxs-lookup"><span data-stu-id="a33be-166">Represents a hierarchical or flat set of Term objects known as a "TermSet".</span></span>

<span data-ttu-id="a33be-167">Aangezien de naamsuggesties geeft, is de Termset een set [termen](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="a33be-167">As the name suggests, TermSet is a set of [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="a33be-168">Een [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in een [termenset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) moet deel uitmaken van een [termenset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="a33be-168">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in a [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) must belong to a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="a33be-169">Er kan geen [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) apart worden opgenomen.</span><span class="sxs-lookup"><span data-stu-id="a33be-169">No [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) can exist independently.</span></span> 

<span data-ttu-id="a33be-170">De syntaxis voor het definiëren van een [termenset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) luidt als volgt:</span><span class="sxs-lookup"><span data-stu-id="a33be-170">The syntax to define a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) is:</span></span>

```SKOS
ex:TermSetA    a    sharepoint-taxonomy:TermSet;
    sharepoint-taxonomy:termSetName    “TermSet A";
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharepoint-taxonomy:hasTopLevelTerm    Ex:Term A.
```

<span data-ttu-id="a33be-171">[TermSets](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) worden logischerwijze samen gegroepeerd in [TermGroups](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group).</span><span class="sxs-lookup"><span data-stu-id="a33be-171">[TermSets](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) are logically grouped together in [TermGroups](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group).</span></span> <span data-ttu-id="a33be-172">Het vereiste veld voor het definiëren van een [termenset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) luidt als volgt:</span><span class="sxs-lookup"><span data-stu-id="a33be-172">The required field for defining a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) is:</span></span>

- <span data-ttu-id="a33be-173">SharePoint-taxonomie: termSetName</span><span class="sxs-lookup"><span data-stu-id="a33be-173">sharepoint-taxonomy:termSetName</span></span>

<span data-ttu-id="a33be-174">In het geval van het opgegeven termSetName is er geen unieke waarde in de [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group), voegt SharePoint een nummer toe aan het einde van de naam, zodat de uniekheid van termSetName (en) wordt gehandhaafd.</span><span class="sxs-lookup"><span data-stu-id="a33be-174">In the case of the termSetName provided is not unique within the [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group), SharPoint appends a number at the end of the name to maintain the uniqueness of termSetName(s).</span></span>

<span data-ttu-id="a33be-175">**SharePoint-taxonomie: hasTopLevelTerm**</span><span class="sxs-lookup"><span data-stu-id="a33be-175">**sharepoint-taxonomy:hasTopLevelTerm**</span></span>

<span data-ttu-id="a33be-176">In SharePoint wordt deze eigenschap gebruikt om de meest voorkomende [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in de [termenset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)toe te wijzen, wat het invoerpunt is voor de structuur van [termen](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in een [termenset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="a33be-176">SharePoint uses this property to map the top most [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in the [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), which is the entry point to the hierarchy of [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="a33be-177">Dit is een inverse relatie naar SharePoint-Taxonomy: topLevelTermOf.</span><span class="sxs-lookup"><span data-stu-id="a33be-177">This is an inverse relation to sharepoint-taxonomy:topLevelTermOf.</span></span> 

<span data-ttu-id="a33be-178">De syntaxis voor de definiëren hiervan luidt als volgt:</span><span class="sxs-lookup"><span data-stu-id="a33be-178">The syntax to define this is:</span></span>

```SKOS
ex:TermSetA    sharepoint-taxonomy:hasTopLevelTerm    ex:TermA.
```

>[!NOTE]
> <span data-ttu-id="a33be-179">U kunt de bovenste [termijn](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) van een bovenliggende [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)niet definiëren.</span><span class="sxs-lookup"><span data-stu-id="a33be-179">You cannot define the top level [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) of a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="a33be-180">**SharePoint-taxonomie: topLevelTermOf**</span><span class="sxs-lookup"><span data-stu-id="a33be-180">**sharepoint-taxonomy:topLevelTermOf**</span></span>

<span data-ttu-id="a33be-181">SharePoint-taxonomie: topLevelTermOf is de inverse van SharePoint-taxonomie: hasTopLevelTerm</span><span class="sxs-lookup"><span data-stu-id="a33be-181">Sharepoint-taxonomy:topLevelTermOf is the inverse of sharepoint-taxonomy:hasTopLevelTerm</span></span>

<span data-ttu-id="a33be-182">De syntaxis voor de definiëren hiervan luidt als volgt:</span><span class="sxs-lookup"><span data-stu-id="a33be-182">The syntax to define this is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA.
```

<span data-ttu-id="a33be-183">**SharePoint-taxonomie: intermenset**</span><span class="sxs-lookup"><span data-stu-id="a33be-183">**sharepoint-taxonomy:inTermSet**</span></span>

<span data-ttu-id="a33be-184">Hiermee kunt u een [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) toewijzen aan een [termenset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="a33be-184">Use this to map a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) to a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="a33be-185">Een [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) kan maar in één [termenset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)bestaan.</span><span class="sxs-lookup"><span data-stu-id="a33be-185">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) can only exist in a single [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="a33be-186">SharePoint vereist deze eigenschap voor [het definiëren van een term](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term).</span><span class="sxs-lookup"><span data-stu-id="a33be-186">SharePoint requires this property when [defining a term](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term).</span></span>

## <a name="required-labels"></a><span data-ttu-id="a33be-187">Vereiste labels</span><span class="sxs-lookup"><span data-stu-id="a33be-187">Required labels</span></span>

<span data-ttu-id="a33be-188">Het kan handig zijn voor de planning van uw organisatie voordat u beheerde metagegevens gaat gebruiken.</span><span class="sxs-lookup"><span data-stu-id="a33be-188">Your organization may want to do careful planning before you start to use managed metadata.</span></span> <span data-ttu-id="a33be-189">Welke planning u moet doen, is afhankelijk van de manier waarop u de taxonomie moet afmaken.</span><span class="sxs-lookup"><span data-stu-id="a33be-189">The amount of planning that you must do depends on how formal your taxonomy is.</span></span> <span data-ttu-id="a33be-190">Dit hangt ook af van de hoeveel besturingselementen u de metagegevens wilt leggen.</span><span class="sxs-lookup"><span data-stu-id="a33be-190">It also depends on how much control that you want to impose on metadata.</span></span> <span data-ttu-id="a33be-191">Op elk niveau van de hiërarchie moet u de vereiste LABLES configureren voor een term of Termenset.</span><span class="sxs-lookup"><span data-stu-id="a33be-191">At each level of the hierarchy, you need to configure required lables for a Term or TermSet.</span></span>

<span data-ttu-id="a33be-192">Een term kan een of meer labels in de standaardtaal bevatten, en de waarden 0 of meer zijn niet in de standaardtaal.</span><span class="sxs-lookup"><span data-stu-id="a33be-192">A Term can have one or more labels in the default language, and zero or more labels in the non-default language.</span></span> <span data-ttu-id="a33be-193">Als de term labels bevat in een taal, moet een van de labels het standaardlabel zijn.</span><span class="sxs-lookup"><span data-stu-id="a33be-193">If the term has labels in a language, one of the labels must be the default label.</span></span>

<span data-ttu-id="a33be-194">**SharePoint-taxonomie: defaultLabel**</span><span class="sxs-lookup"><span data-stu-id="a33be-194">**sharepoint-taxonomy:defaultLabel**</span></span>

<span data-ttu-id="a33be-195">Gebruik dit standaard-lexicale label voor een [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) die een vereiste parameter is voor een [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="a33be-195">Use this default lexical label for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) that is a required parameter for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="a33be-196">Wordt gebruikt om de [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)visueel aan te duiden.</span><span class="sxs-lookup"><span data-stu-id="a33be-196">Use to visually representing the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="a33be-197">De syntaxis voor het definiëren van een defaultLabel is:</span><span class="sxs-lookup"><span data-stu-id="a33be-197">The syntax to define a defaultLabel is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:defaultLabel    “Term A”@en-us.
```

<span data-ttu-id="a33be-198">De defaultLabel bevat twee onderdelen, namelijk de tekenreeks en de taalcode.</span><span class="sxs-lookup"><span data-stu-id="a33be-198">The defaultLabel contains two parts to it – the string and the language tag.</span></span> <span data-ttu-id="a33be-199">De taal moet een van [de werktalen voor het werk](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) woorden zijn.</span><span class="sxs-lookup"><span data-stu-id="a33be-199">The language must be one of the [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working languages.</span></span> <span data-ttu-id="a33be-200">De defaultLabel moet uniek zijn voor alle [termen](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in dezelfde [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), op hetzelfde hiërarchische niveau.</span><span class="sxs-lookup"><span data-stu-id="a33be-200">The defaultLabel must be unique for all [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in the same [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), at the same hierarchical level.</span></span>

<span data-ttu-id="a33be-201">**SharePoint-taxonomie: termSetName**</span><span class="sxs-lookup"><span data-stu-id="a33be-201">**sharepoint-taxonomy:termSetName**</span></span>

<span data-ttu-id="a33be-202">Haalt de naam van het huidige Termset-object op en stelt dit in.</span><span class="sxs-lookup"><span data-stu-id="a33be-202">Gets and sets the name for the current TermSet object.</span></span>

<span data-ttu-id="a33be-203">Dit is het lexicale etiket voor een [termenset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), [in de werk](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) taal van een werkwoord.</span><span class="sxs-lookup"><span data-stu-id="a33be-203">This the lexical label for a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), in a [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span> <span data-ttu-id="a33be-204">Dit is een vereiste parameter voor een [termenset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="a33be-204">This is a required parameter for a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="a33be-205">Voor het visueel vertegenwoordigen van een [termenset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="a33be-205">Use to visually representing a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>

<span data-ttu-id="a33be-206">De syntaxis voor het definiëren van een termSetName is:</span><span class="sxs-lookup"><span data-stu-id="a33be-206">The syntax to define a termSetName is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:TermSetName    “Term Set A”@en-us.
```

<span data-ttu-id="a33be-207">**SharePoint-taxonomie: eigenschaps**</span><span class="sxs-lookup"><span data-stu-id="a33be-207">**sharepoint-taxonomy:propertyName**</span></span>

<span data-ttu-id="a33be-208">Hiermee wordt de naam van de eigenschap voor het huidige Termset-object opgehaald en ingesteld.</span><span class="sxs-lookup"><span data-stu-id="a33be-208">Gets and sets the property name for the current TermSet object.</span></span>

<span data-ttu-id="a33be-209">Dit is het lexicale etiket voor een SharePoint-taxonomie: SharedCustomPropertyForTerm, SharePoint-taxonomie: LocalCustomPropertyForTerm en SharePoint-taxonomie: CustomPropertyForTermSet in een werkgebied van een werk [Archief](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) .</span><span class="sxs-lookup"><span data-stu-id="a33be-209">This is the lexical label for a sharepoint-taxonomy:SharedCustomPropertyForTerm, sharepoint-taxonomy:LocalCustomPropertyForTerm and sharepoint-taxonomy:CustomPropertyForTermSet in a [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span>

<span data-ttu-id="a33be-210">De SharePoint-taxonomie: eigenschapnaam wordt behandeld als de sleutel van de CustomProperty.</span><span class="sxs-lookup"><span data-stu-id="a33be-210">The sharepoint-taxonomy:propertyName is treated as the key of the CustomProperty.</span></span>

<span data-ttu-id="a33be-211">De syntaxis voor het definiëren van een propetyName is:</span><span class="sxs-lookup"><span data-stu-id="a33be-211">The syntax to define a propetyName is:</span></span>

```SKOS
ex:SharedCustomProperty1    sharepoint-taxonomy:propertyName    “Shared Custom Property Key 1”@en-us.
```

## <a name="optional-labels"></a><span data-ttu-id="a33be-212">Optionele labels</span><span class="sxs-lookup"><span data-stu-id="a33be-212">Optional labels</span></span>

<span data-ttu-id="a33be-213">U kunt ook optionele etiketten toevoegen aan de taxonomie.</span><span class="sxs-lookup"><span data-stu-id="a33be-213">You can also add optional labels to your taxonomy.</span></span>

<span data-ttu-id="a33be-214">**SharePoint-taxonomie: otherLabel**</span><span class="sxs-lookup"><span data-stu-id="a33be-214">**sharepoint-taxonomy:otherLabel**</span></span>

<span data-ttu-id="a33be-215">Dit is het alternatieve lexicale etiket voor een [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="a33be-215">This is the alternate lexical label for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> 

<span data-ttu-id="a33be-216">De syntaxis voor het definiëren van een otherLabel is:</span><span class="sxs-lookup"><span data-stu-id="a33be-216">The syntax to define an otherLabel is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:otherLabel    “Term A”@en-us.
```

## <a name="semantic-relationships"></a><span data-ttu-id="a33be-217">Semantische relaties</span><span class="sxs-lookup"><span data-stu-id="a33be-217">Semantic relationships</span></span>

<span data-ttu-id="a33be-218">Taxonomieën hebben hiërarchische en soms een eenvoudige, gerelateerde term ' gekoppelde term ', maar er zijn een aantal ' semantische relaties ' of aangepaste relaties.</span><span class="sxs-lookup"><span data-stu-id="a33be-218">Taxonomies have hierarchical and sometimes a simple “related term” associative relationship, but some have "semantic relationships" or custom-created relationships.</span></span> 

<span data-ttu-id="a33be-219">**SharePoint-taxonomie: bovenliggend element**</span><span class="sxs-lookup"><span data-stu-id="a33be-219">**sharepoint-taxonomy:parent**</span></span>

<span data-ttu-id="a33be-220">Hiermee verlegt u deze hiërarchische [termijn](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) met een andere [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="a33be-220">This hierarchically relates a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) to another [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="a33be-221">Een [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) kan een topniveau van [een](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) [termenset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)zijn, maar in de praktijk moet de term geen bovenliggende [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)hebben.</span><span class="sxs-lookup"><span data-stu-id="a33be-221">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) could be a top level [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) of a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), but in case it doesn’t it must have a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> 

<span data-ttu-id="a33be-222">De syntaxis voor het definiëren van een bovenliggend element luidt als volgt:</span><span class="sxs-lookup"><span data-stu-id="a33be-222">The syntax to define a parent is:</span></span>

```SKOS
ex:TermA1    sharepoint-taxonomy:parent    ex:TermA.
```

<span data-ttu-id="a33be-223">Dat betekent dat TermA1 bovenliggende Terma heeft.</span><span class="sxs-lookup"><span data-stu-id="a33be-223">This means that TermA1 has parent TermA.</span></span> <span data-ttu-id="a33be-224">Ook betekent dit dat TermA1 het kind is van Terma.</span><span class="sxs-lookup"><span data-stu-id="a33be-224">Inversely it also means that TermA1 is the child of TermA.</span></span> <span data-ttu-id="a33be-225">Relatie tussen bovenliggende en onderliggende items is een inversible-relatie.</span><span class="sxs-lookup"><span data-stu-id="a33be-225">Parent-child relationship is an inversible relationship.</span></span>

<span data-ttu-id="a33be-226">**SharePoint-taxonomie: onderliggend**</span><span class="sxs-lookup"><span data-stu-id="a33be-226">**sharepoint-taxonomy:child**</span></span>

<span data-ttu-id="a33be-227">Het object bevat een of meer onderliggende exemplaren van de Termenset, en deze kunnen worden geopend via de eigenschap TermSets.</span><span class="sxs-lookup"><span data-stu-id="a33be-227">The object contains one or more child TermSet instances, and these can be accessed through the TermSets property.</span></span> <span data-ttu-id="a33be-228">Deze klasse biedt ook methoden voor het maken van nieuwe onderliggende Termenset-objecten.</span><span class="sxs-lookup"><span data-stu-id="a33be-228">This class also provides methods for creating new child TermSet objects.</span></span> <span data-ttu-id="a33be-229">Machtigingen voor het bewerken van onderliggende termen en Termenset-exemplaren zijn opgegeven voor de groep.</span><span class="sxs-lookup"><span data-stu-id="a33be-229">Permissions for editing child Term and TermSet instances is specified on the group.</span></span> 

<span data-ttu-id="a33be-230">Hiermee verlegt u deze hiërarchische [termijn](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) met een andere [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="a33be-230">This hierarchically relates a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) to another [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="a33be-231">De syntaxis voor het definiëren van een kind luidt als volgt:</span><span class="sxs-lookup"><span data-stu-id="a33be-231">The syntax to define a child is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:child    ex:TermA1.
```

<span data-ttu-id="a33be-232">Dat betekent dat Terma onderliggend TermA1.</span><span class="sxs-lookup"><span data-stu-id="a33be-232">This means that TermA has child TermA1.</span></span> <span data-ttu-id="a33be-233">Ook betekent dit dat Terma de bovenliggende relatie van TermA1 bovenliggend-kind is een inversible-relatie.</span><span class="sxs-lookup"><span data-stu-id="a33be-233">Inversely it also means that TermA is the parent of TermA1 parent-child relationship is an inversible relationship.</span></span>

## <a name="documentation-notes"></a><span data-ttu-id="a33be-234">Documentatie over documentatie</span><span class="sxs-lookup"><span data-stu-id="a33be-234">Documentation notes</span></span>

<span data-ttu-id="a33be-235">In deze sectie wordt de taxonomie uitvoerig besproken in de naamruimte Microsoft. SharePoint. Taxonomy.</span><span class="sxs-lookup"><span data-stu-id="a33be-235">This section discusses the taxonomy detailed in the Microsoft.SharePoint.Taxonomy Namespace.</span></span>

<span data-ttu-id="a33be-236">**SharePoint-taxonomie: beschrijving**</span><span class="sxs-lookup"><span data-stu-id="a33be-236">**sharepoint-taxonomy:description**</span></span>

<span data-ttu-id="a33be-237">Dit is een gedetailleerde uitleg van de entiteiten van een [SharePoint-taxonomie](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) .</span><span class="sxs-lookup"><span data-stu-id="a33be-237">This is a detailed explanation of any [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) vocabulary entity.</span></span> 

<span data-ttu-id="a33be-238">De syntaxis voor het toevoegen van een beschrijving luidt als volgt:</span><span class="sxs-lookup"><span data-stu-id="a33be-238">The syntax to add a description is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:description    “Term A is the top level term of TermSetA”@en-us.
```

## <a name="custom-properties"></a><span data-ttu-id="a33be-239">Aangepaste eigenschappen</span><span class="sxs-lookup"><span data-stu-id="a33be-239">Custom properties</span></span>

<span data-ttu-id="a33be-240">Hiermee wordt het verzamelen van aangepaste eigenschappen objecten voor het huidige term object in de alleen-lezen woordenlijst opgehaald.</span><span class="sxs-lookup"><span data-stu-id="a33be-240">Gets the collection of custom property objects for the current Term object from the read-only dictionary.</span></span>

<span data-ttu-id="a33be-241">Aangepaste eigenschappen zijn combinaties van sleutelwaarden die kunnen worden gedefinieerd voor een [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) of [termenset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), zodat de beschrijving van de [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) of [termenset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)verder wordt.</span><span class="sxs-lookup"><span data-stu-id="a33be-241">Custom Properties are key-values pairs that can be defined for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), to further the description of the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="a33be-242">SharePoint geeft de sleutel van de aangepaste eigenschap aan met de Help van eigenschapnaam.</span><span class="sxs-lookup"><span data-stu-id="a33be-242">SharePoint specifies the key of the custom property with the help of propertyName.</span></span>

<span data-ttu-id="a33be-243">**SharePoint-taxonomie: CustomPropertyForTermSet**</span><span class="sxs-lookup"><span data-stu-id="a33be-243">**sharepoint-taxonomy:CustomPropertyForTermSet**</span></span>

<span data-ttu-id="a33be-244">De syntaxis voor de definiëren hiervan luidt als volgt:</span><span class="sxs-lookup"><span data-stu-id="a33be-244">The syntax to define this is:</span></span>

```SKOS
ex:CustomProp1    rdf:type    sharepoint-taxonomy:CustomPropertyForTermSet;
    sharepoint-taxonomy:propertyName “Colour”.

ex:TermSetA    ex:CustomProp1    “Red”@en-us.
```

<span data-ttu-id="a33be-245">**SharePoint-taxonomie: SharedCustomPropertyForTerm**</span><span class="sxs-lookup"><span data-stu-id="a33be-245">**sharepoint-taxonomy:SharedCustomPropertyForTerm**</span></span>

<span data-ttu-id="a33be-246">Als de aangepaste eigenschap voor een [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) moet worden getransporteerd met de [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), moet u deze eerst definiëren onder SharedCustomPropertyForTerm wanneer u [de term vervolgens ergens anders](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) opnieuw gebruikt.</span><span class="sxs-lookup"><span data-stu-id="a33be-246">If the custom property for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) needs to be carried along with the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), when you reuse the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) somewhere else, then you need to be define it under SharedCustomPropertyForTerm.</span></span>

<span data-ttu-id="a33be-247">De syntaxis voor de definiëren hiervan luidt als volgt:</span><span class="sxs-lookup"><span data-stu-id="a33be-247">The syntax to define this is:</span></span>

``` SKOS
ex:CustomProp2    rdf:type sharepoint-taxonomy:SharedCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “Length”.

ex:TermA    ex:CustomProp2    “5 cm”@en-us.
```
<span data-ttu-id="a33be-248">**SharePoint-taxonomie: LocalCustomPropertyForTerm**</span><span class="sxs-lookup"><span data-stu-id="a33be-248">**sharepoint-taxonomy:LocalCustomPropertyForTerm**</span></span>

<span data-ttu-id="a33be-249">Als u de aangepaste eigenschap voor een [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) niet samen met de [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)hoeft te gebruiken, moet u deze eerst definiëren onder LocalCustomPropertyForTerm wanneer u [de term vervolgens ergens anders](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) opnieuw gebruikt.</span><span class="sxs-lookup"><span data-stu-id="a33be-249">If the custom property for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) does not need to be carried along with the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), when you reuse the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) somewhere else, then you need to define it under LocalCustomPropertyForTerm.</span></span>

<span data-ttu-id="a33be-250">De syntaxis voor de definiëren hiervan luidt als volgt:</span><span class="sxs-lookup"><span data-stu-id="a33be-250">The syntax to define this is:</span></span>

```SKOS
ex:CustomProp3    rdf:type sharepoint-taxonomy:LocalCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “width”.

ex:TermA    ex:CustomProp3    “5 cm”@en-us.
```

## <a name="data-properties"></a><span data-ttu-id="a33be-251">Gegevenseigenschappen</span><span class="sxs-lookup"><span data-stu-id="a33be-251">Data properties</span></span>

<span data-ttu-id="a33be-252">U kunt op elk niveau van de hiërarchie bepaalde gegevenseigenschappen configureren voor een term of Termenset.</span><span class="sxs-lookup"><span data-stu-id="a33be-252">At each level of the hierarchy, you can configure specific data properties for a Term or TermSet.</span></span>

<span data-ttu-id="a33be-253">**SharePoint-taxonomie: isAvailableForTagging**</span><span class="sxs-lookup"><span data-stu-id="a33be-253">**sharepoint-taxonomy:isAvailableForTagging**</span></span>

<span data-ttu-id="a33be-254">Hiermee kunt u opgeven of een [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) of [termenset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) beschikbaar is in de SharePoint-lijsten en-bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="a33be-254">Use this to specify if a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) available in SharePoint Lists and Libraries.</span></span>  

<span data-ttu-id="a33be-255">Dit is de syntaxis voor dit:</span><span class="sxs-lookup"><span data-stu-id="a33be-255">The syntax for this is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:isAvailableForTagging     "true"^^xsd:Boolean;
```

## <a name="domain-and-range"></a><span data-ttu-id="a33be-256">Domein en bereik</span><span class="sxs-lookup"><span data-stu-id="a33be-256">Domain and range</span></span>

<span data-ttu-id="a33be-257">In de volgende tabel wordt de naam van het domein en het bereik van de SharePoint-taxonomie voor de taxonomie beschreven</span><span class="sxs-lookup"><span data-stu-id="a33be-257">The table below describes the domain and range of SharePoint taxonomy vocabulary.</span></span>

|<span data-ttu-id="a33be-258">Predikaten/werkwoord</span><span class="sxs-lookup"><span data-stu-id="a33be-258">Predicates/verb</span></span>|<span data-ttu-id="a33be-259">Zinloos</span><span class="sxs-lookup"><span data-stu-id="a33be-259">Meaning</span></span>|<span data-ttu-id="a33be-260">Domein</span><span class="sxs-lookup"><span data-stu-id="a33be-260">Domain</span></span>|<span data-ttu-id="a33be-261">Kleurovergangsbereik</span><span class="sxs-lookup"><span data-stu-id="a33be-261">Range</span></span>|
|:--------------|:------|:-----|:----|
<span data-ttu-id="a33be-262">inbegripset</span><span class="sxs-lookup"><span data-stu-id="a33be-262">inTermSet</span></span>|<span data-ttu-id="a33be-263">In de termenset</span><span class="sxs-lookup"><span data-stu-id="a33be-263">In term set</span></span>|<span data-ttu-id="a33be-264">Onder</span><span class="sxs-lookup"><span data-stu-id="a33be-264">Term</span></span>|<span data-ttu-id="a33be-265">Termenset</span><span class="sxs-lookup"><span data-stu-id="a33be-265">Term Set</span></span>|
<span data-ttu-id="a33be-266">inTermGroup</span><span class="sxs-lookup"><span data-stu-id="a33be-266">inTermGroup</span></span>|<span data-ttu-id="a33be-267">In de groep termen</span><span class="sxs-lookup"><span data-stu-id="a33be-267">In term group</span></span>|<span data-ttu-id="a33be-268">Termenset</span><span class="sxs-lookup"><span data-stu-id="a33be-268">TermSet</span></span>|<span data-ttu-id="a33be-269">TermGroup</span><span class="sxs-lookup"><span data-stu-id="a33be-269">TermGroup</span></span>|
<span data-ttu-id="a33be-270">topLevelTermOf</span><span class="sxs-lookup"><span data-stu-id="a33be-270">topLevelTermOf</span></span>|<span data-ttu-id="a33be-271">Is bovenste niveau term</span><span class="sxs-lookup"><span data-stu-id="a33be-271">Is Top Level Term Of</span></span>|<span data-ttu-id="a33be-272">Onder</span><span class="sxs-lookup"><span data-stu-id="a33be-272">Term</span></span>|<span data-ttu-id="a33be-273">Termenset</span><span class="sxs-lookup"><span data-stu-id="a33be-273">TermSet</span></span>|
<span data-ttu-id="a33be-274">hasTopLevelTerm</span><span class="sxs-lookup"><span data-stu-id="a33be-274">hasTopLevelTerm</span></span>|<span data-ttu-id="a33be-275">Heeft een bovenste termijn</span><span class="sxs-lookup"><span data-stu-id="a33be-275">Has top level term</span></span>|<span data-ttu-id="a33be-276">Termenset</span><span class="sxs-lookup"><span data-stu-id="a33be-276">Term Set</span></span>|<span data-ttu-id="a33be-277">Onder</span><span class="sxs-lookup"><span data-stu-id="a33be-277">Term</span></span>|
<span data-ttu-id="a33be-278">termSetName</span><span class="sxs-lookup"><span data-stu-id="a33be-278">termSetName</span></span>|<span data-ttu-id="a33be-279">Termenset heeft naam</span><span class="sxs-lookup"><span data-stu-id="a33be-279">Term set has Name</span></span>|<span data-ttu-id="a33be-280">Onder</span><span class="sxs-lookup"><span data-stu-id="a33be-280">Term</span></span>|<span data-ttu-id="a33be-281">Letterlijke tekst</span><span class="sxs-lookup"><span data-stu-id="a33be-281">Plain literal</span></span>|
<span data-ttu-id="a33be-282">defaultLabel</span><span class="sxs-lookup"><span data-stu-id="a33be-282">defaultLabel</span></span>|<span data-ttu-id="a33be-283">De term heeft een standaardlabel</span><span class="sxs-lookup"><span data-stu-id="a33be-283">Term has default label</span></span>|<span data-ttu-id="a33be-284">Onder</span><span class="sxs-lookup"><span data-stu-id="a33be-284">Term</span></span>|<span data-ttu-id="a33be-285">Letterlijke tekst</span><span class="sxs-lookup"><span data-stu-id="a33be-285">Plain literal</span></span>|
<span data-ttu-id="a33be-286">otherLabel</span><span class="sxs-lookup"><span data-stu-id="a33be-286">otherLabel</span></span>|<span data-ttu-id="a33be-287">De term heeft een ander label</span><span class="sxs-lookup"><span data-stu-id="a33be-287">Term has other label</span></span>|<span data-ttu-id="a33be-288">Onder</span><span class="sxs-lookup"><span data-stu-id="a33be-288">Term</span></span>|<span data-ttu-id="a33be-289">Letterlijke tekst</span><span class="sxs-lookup"><span data-stu-id="a33be-289">Plain literal</span></span>|
<span data-ttu-id="a33be-290">eigenschaps</span><span class="sxs-lookup"><span data-stu-id="a33be-290">propertyName</span></span>|<span data-ttu-id="a33be-291">Heeft eigenschaps label</span><span class="sxs-lookup"><span data-stu-id="a33be-291">Has Property Label</span></span>|<span data-ttu-id="a33be-292">SharedCustomPropertyForTerm, LocalCustomPropertyForTerm, CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="a33be-292">SharedCustomPropertyForTerm, LocalCustomPropertyForTerm, CustomPropertyForTermSet</span></span> |<span data-ttu-id="a33be-293">Booleaanse waarde, tekenreeks, integer, decimaal, dubbel</span><span class="sxs-lookup"><span data-stu-id="a33be-293">Boolean, String, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="a33be-294">beschrijving</span><span class="sxs-lookup"><span data-stu-id="a33be-294">description</span></span>|<span data-ttu-id="a33be-295">Heeft een beschrijving</span><span class="sxs-lookup"><span data-stu-id="a33be-295">Has Description</span></span>|<span data-ttu-id="a33be-296">Alles</span><span class="sxs-lookup"><span data-stu-id="a33be-296">All</span></span>|<span data-ttu-id="a33be-297">Letterlijke tekst</span><span class="sxs-lookup"><span data-stu-id="a33be-297">Plain literal</span></span>|
|<span data-ttu-id="a33be-298">site</span><span class="sxs-lookup"><span data-stu-id="a33be-298">parent</span></span>|<span data-ttu-id="a33be-299">Heeft bovenliggend element</span><span class="sxs-lookup"><span data-stu-id="a33be-299">Has parent</span></span>|<span data-ttu-id="a33be-300">Onder</span><span class="sxs-lookup"><span data-stu-id="a33be-300">Term</span></span>|<span data-ttu-id="a33be-301">Onder</span><span class="sxs-lookup"><span data-stu-id="a33be-301">Term</span></span>|
|<span data-ttu-id="a33be-302">kinderen</span><span class="sxs-lookup"><span data-stu-id="a33be-302">child</span></span>|<span data-ttu-id="a33be-303">Heeft een kind</span><span class="sxs-lookup"><span data-stu-id="a33be-303">Has Child</span></span>|<span data-ttu-id="a33be-304">Onder</span><span class="sxs-lookup"><span data-stu-id="a33be-304">Term</span></span>|<span data-ttu-id="a33be-305">Onder</span><span class="sxs-lookup"><span data-stu-id="a33be-305">Term</span></span>|
|<span data-ttu-id="a33be-306">isAvailableForTagging</span><span class="sxs-lookup"><span data-stu-id="a33be-306">isAvailableForTagging</span></span>|<span data-ttu-id="a33be-307">Is beschikbaar voor labelen</span><span class="sxs-lookup"><span data-stu-id="a33be-307">Is available for tagging</span></span>|<span data-ttu-id="a33be-308">Term, Termenset</span><span class="sxs-lookup"><span data-stu-id="a33be-308">Term, Term Set</span></span>|<span data-ttu-id="a33be-309">Booleaanse waarde</span><span class="sxs-lookup"><span data-stu-id="a33be-309">Boolean</span></span>|
|<span data-ttu-id="a33be-310">SharedCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="a33be-310">SharedCustomPropertyForTerm</span></span>|<span data-ttu-id="a33be-311">Heeft een gedeelde aangepaste eigenschap</span><span class="sxs-lookup"><span data-stu-id="a33be-311">Has shared custom property</span></span>|<span data-ttu-id="a33be-312">Onder</span><span class="sxs-lookup"><span data-stu-id="a33be-312">Term</span></span>|<span data-ttu-id="a33be-313">Booleaanse waarde, tekenreeks, integer, decimaal, dubbel</span><span class="sxs-lookup"><span data-stu-id="a33be-313">Boolean, string, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="a33be-314">LocalCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="a33be-314">LocalCustomPropertyForTerm</span></span>|<span data-ttu-id="a33be-315">Heeft lokale aangepaste eigenschap</span><span class="sxs-lookup"><span data-stu-id="a33be-315">Has local custom property</span></span>|<span data-ttu-id="a33be-316">Onder</span><span class="sxs-lookup"><span data-stu-id="a33be-316">Term</span></span>|<span data-ttu-id="a33be-317">Booleaanse waarde, tekenreeks, integer, decimaal, dubbel</span><span class="sxs-lookup"><span data-stu-id="a33be-317">Boolean, String, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="a33be-318">CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="a33be-318">CustomPropertyForTermSet</span></span>|<span data-ttu-id="a33be-319">Heeft een aangepaste eigenschap</span><span class="sxs-lookup"><span data-stu-id="a33be-319">Has Custom Property</span></span>|<span data-ttu-id="a33be-320">Termenset</span><span class="sxs-lookup"><span data-stu-id="a33be-320">TermSet</span></span>|<span data-ttu-id="a33be-321">Booleaanse waarde, tekenreeks, integer, decimaal, dubbel</span><span class="sxs-lookup"><span data-stu-id="a33be-321">Boolean, String, Integer, Decimal, Double</span></span>|

<span data-ttu-id="a33be-322">[Skos](https://www.w3.org/TR/skos-primer/) geldige Scenario's die [SharePoint-taxonomie](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) niet toestaan:</span><span class="sxs-lookup"><span data-stu-id="a33be-322">[SKOS](https://www.w3.org/TR/skos-primer/) valid scenarios that [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) does not allow:</span></span>

- <span data-ttu-id="a33be-323">Hiërarchische redundantie: een [skos](https://www.w3.org/TR/skos-primer/) -concept kan tegelijk worden bijgevoegd aan diverse bredere concepten, maar een SharePoint-taxonomie: de term mag maar één SharePoint-taxonomie hebben: ouder, dus cyclische afhankelijkheid, van voorwaarden is ook niet toegestaan.</span><span class="sxs-lookup"><span data-stu-id="a33be-323">Hierarchical redundancy - A [SKOS](https://www.w3.org/TR/skos-primer/) concept can be attached to several broader concepts at the same time, but a sharepoint-taxonomy:Term can have only one sharepoint-taxonomy:parent, hence cyclic dependency, of Terms is also not allowed.</span></span>
- <span data-ttu-id="a33be-324">Zwevende termen zijn niet toegestaan in de SharePoint-taxonomie.</span><span class="sxs-lookup"><span data-stu-id="a33be-324">Orphaned terms are not allowed in SharePoint taxonomy.</span></span> <span data-ttu-id="a33be-325">Elke SharePoint-taxonomie: een term moet bestaan uit een SharePoint-taxonomie: de naam van de SharePoint-taxonomie: topLevelTermOf een Termenset.</span><span class="sxs-lookup"><span data-stu-id="a33be-325">Every sharepoint-taxonomy:Term should either have a sharepoint-taxonomy:parent or it should be the sharepoint-taxonomy:topLevelTermOf a TermSet.</span></span>
- <span data-ttu-id="a33be-326">SharePoint-taxonomie biedt geen ondersteuning voor koppelieve betrekkingen.</span><span class="sxs-lookup"><span data-stu-id="a33be-326">SharePoint taxonomy does not support associative relations.</span></span>
- <span data-ttu-id="a33be-327">SharePoint-taxonomie biedt alleen ondersteuning voor twee typen hiërarchierelaties – SharePoint-Taxonomy: Parent en SharePoint-Taxonomy: kind.</span><span class="sxs-lookup"><span data-stu-id="a33be-327">SharePoint taxonomy only allows 2 types of Hierarchical relations – sharepoint-taxonomy:parent and sharepoint-Taxonomy:child.</span></span> 
- <span data-ttu-id="a33be-328">In tegenstelling tot [skos](https://www.w3.org/TR/skos-primer/) wordt de hiërarchische relatie in de woordenlijst van de SharePoint-taxonomie slechts met termen binnen dezelfde termset vastgelegd.</span><span class="sxs-lookup"><span data-stu-id="a33be-328">Unlike [SKOS](https://www.w3.org/TR/skos-primer/) the hierarchical relationship in SharePoint taxonomy vocabulary, can only be established with Terms within the same TermSet.</span></span>

## <a name="see-also"></a><span data-ttu-id="a33be-329">Zie ook</span><span class="sxs-lookup"><span data-stu-id="a33be-329">See also</span></span>

[<span data-ttu-id="a33be-330">Een termenset importeren met een op SKOS gebaseerde indeling</span><span class="sxs-lookup"><span data-stu-id="a33be-330">Import a term set using a SKOS-based format</span></span>](import-term-set-skos.md)

