---
title: Query's uitvoeren op de inhoud in een revisieset
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Meer informatie over het maken en uitvoeren van een query in een revisieset om inhoud te ordenen voor een efficiëntere controle in een Advanced eDiscovery geval.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 64dbeb8ad68f4188e5768a0a7e0e80ca6c22760b
ms.sourcegitcommit: cc9e3cac6af23f20d7cc5ac6fc6f6e01bc3cc5c5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/03/2021
ms.locfileid: "52736420"
---
# <a name="query-and-filter-content-in-a-review-set"></a><span data-ttu-id="c00ef-103">Query- en filterinhoud in een controleset</span><span class="sxs-lookup"><span data-stu-id="c00ef-103">Query and filter content in a review set</span></span>

<span data-ttu-id="c00ef-104">In de meeste gevallen is het handig om dieper in te gaan op de inhoud in een revisieset en deze te organiseren om een efficiëntere controle te vergemakkelijken.</span><span class="sxs-lookup"><span data-stu-id="c00ef-104">In most cases, it will be useful to dig deeper into the content in a review set and organize it to facilitate a more efficient review.</span></span> <span data-ttu-id="c00ef-105">Als u filters en query's in een revisieset gebruikt, kunt u zich concentreren op een subset met documenten die voldoen aan de criteria van uw revisie.</span><span class="sxs-lookup"><span data-stu-id="c00ef-105">Using filters and queries in a review set helps you focus on a subset of documents that meet the criteria of your review.</span></span>

## <a name="default-filters"></a><span data-ttu-id="c00ef-106">Standaardfilters</span><span class="sxs-lookup"><span data-stu-id="c00ef-106">Default filters</span></span>

<span data-ttu-id="c00ef-107">In een revisieset zijn er vijf standaardfilters die vooraf zijn geladen in de revisieset:</span><span class="sxs-lookup"><span data-stu-id="c00ef-107">In a review set, there are five default filters that are pre-loaded in the review set:</span></span>

- <span data-ttu-id="c00ef-108">Trefwoorden</span><span class="sxs-lookup"><span data-stu-id="c00ef-108">Keywords</span></span>
- <span data-ttu-id="c00ef-109">Datum</span><span class="sxs-lookup"><span data-stu-id="c00ef-109">Date</span></span>
- <span data-ttu-id="c00ef-110">Afzender/auteur</span><span class="sxs-lookup"><span data-stu-id="c00ef-110">Sender/Author</span></span>
- <span data-ttu-id="c00ef-111">Onderwerp/titel</span><span class="sxs-lookup"><span data-stu-id="c00ef-111">Subject/Title</span></span>
- <span data-ttu-id="c00ef-112">Tags</span><span class="sxs-lookup"><span data-stu-id="c00ef-112">Tags</span></span>

![Standaardfiltertypen](../media/DefaultFilterTypes.png)

<span data-ttu-id="c00ef-114">Klik op elk filter om het uit te vouwen en een waarde toe te wijzen.</span><span class="sxs-lookup"><span data-stu-id="c00ef-114">Click each filter to expand it and assign a value.</span></span> <span data-ttu-id="c00ef-115">Klik buiten het filter om het filter automatisch toe te passen op de revisieset.</span><span class="sxs-lookup"><span data-stu-id="c00ef-115">Click outside the filter to automatically apply the filter to the review set.</span></span> <span data-ttu-id="c00ef-116">In de volgende schermafbeelding ziet u het datumfilter dat is geconfigureerd om documenten weer te geven binnen een datumbereik.</span><span class="sxs-lookup"><span data-stu-id="c00ef-116">The following screenshot shows the Date filter configured to show documents within a date range.</span></span>

![Standaardfilter uitv](../media/ExpandedFilter.png)

## <a name="add-or-remove-filters"></a><span data-ttu-id="c00ef-118">Filters toevoegen of verwijderen</span><span class="sxs-lookup"><span data-stu-id="c00ef-118">Add or remove filters</span></span>

<span data-ttu-id="c00ef-119">Als u filters wilt toevoegen of verwijderen die worden weergegeven voor de revisieset, selecteert u **Filters** om het filtervenster te openen, dat wordt weergegeven op een flyoutpagina.</span><span class="sxs-lookup"><span data-stu-id="c00ef-119">To add or remove filters that are displayed for the review set, select **Filters** to open the filter panel, which is displayed on a flyout page.</span></span> 

![Deelvenster Filter](../media/FilterPanel.png)

<span data-ttu-id="c00ef-121">De beschikbare filters zijn ingedeeld in vier secties:</span><span class="sxs-lookup"><span data-stu-id="c00ef-121">The available filters are organized in four sections:</span></span>

- <span data-ttu-id="c00ef-122">**Zoeken:** filters die verschillende zoekmogelijkheden bieden.</span><span class="sxs-lookup"><span data-stu-id="c00ef-122">**Search**: Filters that provide different search capabilities.</span></span>

- <span data-ttu-id="c00ef-123">**Analyse & voorspellende** codering: filters voor eigenschappen die worden gegenereerd  en toegevoegd aan documenten wanneer u de documentanalyse & of voorspellende coderingsmodellen gebruikt.</span><span class="sxs-lookup"><span data-stu-id="c00ef-123">**Analytics & predictive coding**: Filters for properties generated and added to documents when you run the **Document & email analytic** job or use predictive coding models.</span></span>

- <span data-ttu-id="c00ef-124">**Id's:** filtert voor alle id-eigenschappen van documenten.</span><span class="sxs-lookup"><span data-stu-id="c00ef-124">**IDs**: Filters for all ID properties of documents.</span></span>

- <span data-ttu-id="c00ef-125">**Itemeigenschappen:** Filters voor documenteigenschappen.</span><span class="sxs-lookup"><span data-stu-id="c00ef-125">**Item properties**: Filters for document properties.</span></span> 

<span data-ttu-id="c00ef-126">Vouw elke sectie uit en selecteer of deselecteer filters om ze toe te voegen of te verwijderen in de filterset.</span><span class="sxs-lookup"><span data-stu-id="c00ef-126">Expand each section and select or deselect filters to add or remove them in the filter set.</span></span> <span data-ttu-id="c00ef-127">Wanneer u een filter toevoegt, wordt dit weergegeven in de filterset.</span><span class="sxs-lookup"><span data-stu-id="c00ef-127">When you add a filter, it's displayed in the filter set.</span></span> 

![Lijst met filtersecties en eigenschappen in het filtervenster](../media/FilterPanel2.png)

> [!NOTE]
> <span data-ttu-id="c00ef-129">Wanneer u een sectie uitv vouwt in het filtervenster, ziet u dat de standaardfiltertypen zijn geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="c00ef-129">When you expand a section in the filter panel, you'll notice that the default filter types are selected.</span></span> <span data-ttu-id="c00ef-130">U kunt deze geselecteerd houden of deselecteren en verwijderen uit de filterset.</span><span class="sxs-lookup"><span data-stu-id="c00ef-130">You can keep these selected or deselect them and removed them from the filter set.</span></span> 

## <a name="filter-types"></a><span data-ttu-id="c00ef-131">Filtertypen</span><span class="sxs-lookup"><span data-stu-id="c00ef-131">Filter types</span></span>

<span data-ttu-id="c00ef-132">Elk doorzoekbaar veld in een revisieset heeft een bijbehorend filter dat u kunt gebruiken voor filteritems op basis van een specifiek veld.</span><span class="sxs-lookup"><span data-stu-id="c00ef-132">Every searchable field in a review set has a corresponding filter that you can use for filter items based on a specific field.</span></span>

<span data-ttu-id="c00ef-133">Er zijn meerdere typen filters:</span><span class="sxs-lookup"><span data-stu-id="c00ef-133">There are multiple types of filters:</span></span>

- <span data-ttu-id="c00ef-134">**Vrije tekst:** Er wordt een freetekstfilter toegepast op tekstvelden zoals 'Onderwerp'.</span><span class="sxs-lookup"><span data-stu-id="c00ef-134">**Freetext**: A freetext filter is applied to text fields such as "Subject".</span></span> <span data-ttu-id="c00ef-135">U kunt meerdere zoektermen op een lijst zetten door ze te scheiden met een komma.</span><span class="sxs-lookup"><span data-stu-id="c00ef-135">You can list multiple search terms by separating them with a comma.</span></span>

- <span data-ttu-id="c00ef-136">**Datum:** er wordt een datumfilter gebruikt voor datumvelden zoals 'Laatst gewijzigde datum'.</span><span class="sxs-lookup"><span data-stu-id="c00ef-136">**Date**: A date filter is used for date fields such as "Last modified date".</span></span>

- <span data-ttu-id="c00ef-137">**Zoekopties:** Een zoekoptiesfilter bevat een lijst met mogelijke waarden (elke waarde wordt weergegeven met een selectievakje dat u kunt selecteren) voor bepaalde velden in de revisie.</span><span class="sxs-lookup"><span data-stu-id="c00ef-137">**Search options**: A search options filter provides a list of possible values (each value is displayed with a checkbox that you can select) for particular fields in the review.</span></span> <span data-ttu-id="c00ef-138">Dit filter wordt gebruikt voor velden, zoals 'Afzender', waarbij er een beperkt aantal mogelijke waarden in de revisieset staat.</span><span class="sxs-lookup"><span data-stu-id="c00ef-138">This filter is used for fields, such as "Sender", where there is a finite number of possible values in the review set.</span></span>

- <span data-ttu-id="c00ef-139">**Trefwoord:** een trefwoordvoorwaarde is een specifiek exemplaar van een voorwaarde voor vrije tekst die u kunt gebruiken om te zoeken naar termen.</span><span class="sxs-lookup"><span data-stu-id="c00ef-139">**Keyword**: A keyword condition is a specific instance of freetext condition that you can use to search for terms.</span></span> <span data-ttu-id="c00ef-140">U kunt ook KQL-achtige querytaal gebruiken in dit type filter.</span><span class="sxs-lookup"><span data-stu-id="c00ef-140">You can also use KQL-like query language in this type of filter.</span></span> <span data-ttu-id="c00ef-141">Zie de secties Querytaal en Geavanceerde opbouwfunctie voor query's in dit onderwerp voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="c00ef-141">For more information, see the Query language and Advanced query builder sections in this topic.</span></span>

## <a name="include-and-exclude-filter-relationships"></a><span data-ttu-id="c00ef-142">Filterrelaties opnemen en uitsluiten</span><span class="sxs-lookup"><span data-stu-id="c00ef-142">Include and exclude filter relationships</span></span>

<span data-ttu-id="c00ef-143">U hebt de optie om de op te nemen en uit te sluiten relatie voor een bepaald filter.</span><span class="sxs-lookup"><span data-stu-id="c00ef-143">You have the option to change the include and exclude relationship for a particular filter.</span></span> <span data-ttu-id="c00ef-144">In het filter Label kunt u bijvoorbeeld items uitsluiten die met een bepaalde tag zijn gemarkeerd door Gelijk aan **geen** van in het vervolgkeuzefilter te selecteren.</span><span class="sxs-lookup"><span data-stu-id="c00ef-144">For example, in the Tag filter, you can exclude items that are tagged with a particular tag by selecting **Equals none of** in the dropdown filter.</span></span> 

![Labelfilter uitsluiten](../media/TagFilterExclude.png)

## <a name="save-filters-as-queries"></a><span data-ttu-id="c00ef-146">Filters opslaan als query's</span><span class="sxs-lookup"><span data-stu-id="c00ef-146">Save filters as queries</span></span>

<span data-ttu-id="c00ef-147">Nadat u tevreden bent over uw filters, kunt u de filtercombinatie opslaan als een filterquery.</span><span class="sxs-lookup"><span data-stu-id="c00ef-147">After you are satisfied with your filters, you can save the filter combination as a filter query.</span></span> <span data-ttu-id="c00ef-148">Hiermee kunt u het filter toepassen in de toekomstige revisiesessies.</span><span class="sxs-lookup"><span data-stu-id="c00ef-148">This lets you apply the filter in the future review sessions.</span></span>

<span data-ttu-id="c00ef-149">Als u een filter wilt opslaan, **selecteert u De query opslaan** en een naam geven.</span><span class="sxs-lookup"><span data-stu-id="c00ef-149">To save a filter, select **Save the query** and name it.</span></span> <span data-ttu-id="c00ef-150">U of andere revisoren kunnen eerder opgeslagen filterquery's uitvoeren door de vervolgkeuzekeuze van opgeslagen filterquery's te selecteren en een filterquery te selecteren die u wilt toepassen om de setdocumenten te controleren. </span><span class="sxs-lookup"><span data-stu-id="c00ef-150">You or other reviewers can run previously saved filter queries by selecting the **Saved filter queries** dropdown and selecting a filter query to apply to review set documents.</span></span> 

![Een filterquery opslaan](../media/SaveFilterQuery.png)

<span data-ttu-id="c00ef-152">Als u een filterquery wilt verwijderen, opent u het filtervenster en selecteert u het prullenbakpictogram naast de query.</span><span class="sxs-lookup"><span data-stu-id="c00ef-152">To delete a filter query, open the filter panel and select the trashcan icon next to the query.</span></span>

![Een filterquery verwijderen](../media/DeleteFilterQuery.png)

## <a name="query-language"></a><span data-ttu-id="c00ef-154">Querytaal</span><span class="sxs-lookup"><span data-stu-id="c00ef-154">Query language</span></span>

<span data-ttu-id="c00ef-155">Naast het gebruik van filters kunt u ook een KQL-achtige querytaal gebruiken in het filter Trefwoorden om de zoekquery voor revisiesets te maken.</span><span class="sxs-lookup"><span data-stu-id="c00ef-155">In addition to using filters, you can also use a KQL-like query language in the Keywords filter to build your review set search query.</span></span> <span data-ttu-id="c00ef-156">De querytaal voor revisiesetquery's ondersteunt standaard Booleaanse operatoren, zoals **EN**, **OF**, **NIET**, en **NEAR**.</span><span class="sxs-lookup"><span data-stu-id="c00ef-156">The query language for review set queries supports standard Boolean operators, such as **AND**, **OR**, **NOT**, and **NEAR**.</span></span> <span data-ttu-id="c00ef-157">Het ondersteunt ook een jokerteken met één teken (?) en een jokerteken met meerdere tekens (\*).</span><span class="sxs-lookup"><span data-stu-id="c00ef-157">It also supports a single-character wildcard (?) and a multi-character wildcard (\*).</span></span>

## <a name="advanced-query-builder"></a><span data-ttu-id="c00ef-158">Geavanceerde opbouwfunctie voor query's</span><span class="sxs-lookup"><span data-stu-id="c00ef-158">Advanced query builder</span></span>

<span data-ttu-id="c00ef-159">U kunt ook geavanceerdere query's maken om documenten te zoeken in een revisieset.</span><span class="sxs-lookup"><span data-stu-id="c00ef-159">You can also build more advanced queries to search for documents in a review set.</span></span>

1. <span data-ttu-id="c00ef-160">Open het filtervenster, selecteer **Filters** en vouw de **sectie** Zoeken uit.</span><span class="sxs-lookup"><span data-stu-id="c00ef-160">Open the filter panel, select **Filters**, and expand the **Search** section.</span></span>

  ![Een KQL-filter toevoegen](../media/AddKQLFilter.png)

2. <span data-ttu-id="c00ef-162">Selecteer het **KQL-filter** en klik **op Opbouwfunctie voor query's openen.**</span><span class="sxs-lookup"><span data-stu-id="c00ef-162">Select the **KQL** filter and click **Open query builder**.</span></span>

   <span data-ttu-id="c00ef-163">In dit deelvenster kunt u complexe KQL-query's maken met behulp van de opbouwfunctie voor query's.</span><span class="sxs-lookup"><span data-stu-id="c00ef-163">In this panel, you can create complex KQL queries by using the query builder.</span></span> <span data-ttu-id="c00ef-164">U kunt voorwaarden toevoegen of voorwaardengroepen toevoegen die zijn opgebouwd uit meerdere voorwaarden die logisch zijn verbonden door **EN-** of **OF-relaties.**</span><span class="sxs-lookup"><span data-stu-id="c00ef-164">You can add conditions or add condition groups that are made up of multiple conditions that are logically connected by **AND** or **OR** relationships.</span></span>

   ![Opbouwfunctie voor query's gebruiken om complexe filterquery's te configureren](../media/ComplexQuery.png)
