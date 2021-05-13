---
title: Een query uitvoeren op de gegevens in een controleset
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
description: Meer informatie over het maken en uitvoeren van een query in een revisieset om gegevens te ordenen voor een efficiëntere controle in een Advanced eDiscovery geval.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 5a03b0c863f9cc2050b18ce83ed11b8a71d1db4d
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/12/2021
ms.locfileid: "52345798"
---
# <a name="query-the-data-in-a-review-set"></a><span data-ttu-id="eee7c-103">Een query uitvoeren op de gegevens in een controleset</span><span class="sxs-lookup"><span data-stu-id="eee7c-103">Query the data in a review set</span></span>

<span data-ttu-id="eee7c-104">In de meeste gevallen is het handig om dieper in de gegevens in een revisieset te kunnen graven en deze gegevens te organiseren om een efficiëntere controle te vergemakkelijken.</span><span class="sxs-lookup"><span data-stu-id="eee7c-104">In most cases, it will be useful to be able to dig deeper into the data in a review set and organize that data to facilitate a more efficient review.</span></span> <span data-ttu-id="eee7c-105">Als u query's in een revisieset gebruikt, kunt u zich concentreren op een subset met documenten die voldoen aan de criteria van uw beoordeling.</span><span class="sxs-lookup"><span data-stu-id="eee7c-105">Using Queries in a review set helps you focus on a subset of documents that meet the criteria of your review.</span></span>

## <a name="creating-and-running-a-query-in-a-review-set"></a><span data-ttu-id="eee7c-106">Een query maken en uitvoeren in een revisieset</span><span class="sxs-lookup"><span data-stu-id="eee7c-106">Creating and running a query in a review set</span></span>

<span data-ttu-id="eee7c-107">Als u een query wilt maken en uitvoeren op de documenten in een revisieset, **selecteert** u Nieuwe query in de revisieset.</span><span class="sxs-lookup"><span data-stu-id="eee7c-107">To create and run a query on the documents in a review set, select **New query** in the review set.</span></span> <span data-ttu-id="eee7c-108">Nadat u de naam van de query hebt gegeven en de voorwaarden hebt bepaald, **selecteert** u Opslaan om de query op te slaan en uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="eee7c-108">After you name your query and define the conditions, select **Save** to save and run the query.</span></span> <span data-ttu-id="eee7c-109">Als u een query wilt uitvoeren die eerder is opgeslagen, selecteert u een opgeslagen query.</span><span class="sxs-lookup"><span data-stu-id="eee7c-109">To run a query that has been previously saved, select a saved query.</span></span>

![Query's instellen controleren](../media/AeDReviewSetQueries.png)

## <a name="building-a-review-set-query"></a><span data-ttu-id="eee7c-111">Een revisiesetquery maken</span><span class="sxs-lookup"><span data-stu-id="eee7c-111">Building a review set query</span></span>

<span data-ttu-id="eee7c-112">U kunt een query maken met behulp van een combinatie van trefwoorden, eigenschappen en voorwaarden in de voorwaarde Trefwoorden.</span><span class="sxs-lookup"><span data-stu-id="eee7c-112">You can build a query by using a combination of keywords, properties, and conditions in the Keywords condition.</span></span> <span data-ttu-id="eee7c-113">U kunt voorwaarden ook groepen als een blok (een zogenaamde *voorwaardegroep)* om een complexere query te maken.</span><span class="sxs-lookup"><span data-stu-id="eee7c-113">You can also group conditions as a block (called a *condition group*) to build a more complex query.</span></span> <span data-ttu-id="eee7c-114">Zie Metagegevensvelden in documenten in Advanced eDiscovery voor een lijst en beschrijving van metagegevenseigenschappen die [u kunt zoeken.](document-metadata-fields-in-Advanced-eDiscovery.md)</span><span class="sxs-lookup"><span data-stu-id="eee7c-114">For a list and description of metadata properties that you can search, see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span></span>

### <a name="conditions"></a><span data-ttu-id="eee7c-115">Voorwaarden</span><span class="sxs-lookup"><span data-stu-id="eee7c-115">Conditions</span></span>

<span data-ttu-id="eee7c-116">Elk doorzoekbaar veld in een revisieset heeft een bijbehorende voorwaarde die u kunt gebruiken om de query te maken.</span><span class="sxs-lookup"><span data-stu-id="eee7c-116">Every searchable field in a review set has a corresponding condition that you can use to build your query.</span></span>

<span data-ttu-id="eee7c-117">Er zijn meerdere typen voorwaarden:</span><span class="sxs-lookup"><span data-stu-id="eee7c-117">There are multiple types of conditions:</span></span>

- <span data-ttu-id="eee7c-118">Vrije tekst: Een voorwaarde voor vrije tekst wordt gebruikt voor tekstvelden zoals onderwerp.</span><span class="sxs-lookup"><span data-stu-id="eee7c-118">Freetext: A freetext condition is used for text fields such as subject.</span></span> <span data-ttu-id="eee7c-119">U kunt meerdere zoektermen op een lijst zetten door ze te scheiden met een komma.</span><span class="sxs-lookup"><span data-stu-id="eee7c-119">You can list multiple search terms by separating them out with a comma.</span></span>

- <span data-ttu-id="eee7c-120">Datum: Er wordt een datumvoorwaarde gebruikt voor datumvelden, zoals laatst gewijzigde datum.</span><span class="sxs-lookup"><span data-stu-id="eee7c-120">Date: A date condition is used for date fields such as last modified date.</span></span>

- <span data-ttu-id="eee7c-121">Zoekopties: Een voorwaarde voor zoekopties biedt een lijst met mogelijke waarden voor het specifieke veld in de revisieset.</span><span class="sxs-lookup"><span data-stu-id="eee7c-121">Search options: A search options condition will provide a list of possible values for the particular field in your review set.</span></span> <span data-ttu-id="eee7c-122">Dit wordt gebruikt voor velden, zoals afzender, waarbij er een eindig aantal mogelijke waarden in de revisieset staat.</span><span class="sxs-lookup"><span data-stu-id="eee7c-122">This is used for fields, such as sender, where there is a finite number of possible values in your review set.</span></span>

- <span data-ttu-id="eee7c-123">Trefwoord: Een trefwoordvoorwaarde is een specifiek exemplaar van een voorwaarde voor vrije tekst die u kunt gebruiken om te zoeken naar termen of om KQL-achtige querytaal te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="eee7c-123">Keyword: A keyword condition is a specific instance of freetext condition that you can use to search for terms, or use KQL-like query language in.</span></span> <span data-ttu-id="eee7c-124">Zie hieronder voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="eee7c-124">See below for more detail.</span></span>

### <a name="query-language"></a><span data-ttu-id="eee7c-125">Querytaal</span><span class="sxs-lookup"><span data-stu-id="eee7c-125">Query language</span></span>

<span data-ttu-id="eee7c-126">Naast de voorwaarden kunt u een KQL-achtige querytaal in de voorwaarde Trefwoorden gebruiken om uw query te maken.</span><span class="sxs-lookup"><span data-stu-id="eee7c-126">In addition to conditions, you can use a KQL-like query language in the Keywords condition to build your query.</span></span> <span data-ttu-id="eee7c-127">De querytaal voor revisiesetquery's ondersteunt standaard Booleaanse operatoren, zoals **EN**, **OF**, **NIET**, en **NEAR**.</span><span class="sxs-lookup"><span data-stu-id="eee7c-127">The query language for review set queries supports standard Boolean operators, such as **AND**, **OR**, **NOT**, and **NEAR**.</span></span> <span data-ttu-id="eee7c-128">Het ondersteunt ook een jokerteken met één teken (?) en een jokerteken met meerdere tekens (\*).</span><span class="sxs-lookup"><span data-stu-id="eee7c-128">It also supports a single-character wildcard (?) and a multi-character wildcard (\*).</span></span>

## <a name="filters"></a><span data-ttu-id="eee7c-129">Filters</span><span class="sxs-lookup"><span data-stu-id="eee7c-129">Filters</span></span>

<span data-ttu-id="eee7c-130">Naast query's die u kunt opslaan, kunt u filters voor revisiesets gebruiken om snel aanvullende voorwaarden toe te passen op een revisiesetquery.</span><span class="sxs-lookup"><span data-stu-id="eee7c-130">In addition to queries that you can save, you can use review set filters to quickly apply additional conditions to a review set query.</span></span> <span data-ttu-id="eee7c-131">Met behulp van filters kunt u de resultaten van een query voor revisiesets verder verfijnen.</span><span class="sxs-lookup"><span data-stu-id="eee7c-131">Using filters help you further refine the results displayed by a review set query.</span></span>

![Filters voor revisiesets](../media/AeDReviewSetFilters.png)

<span data-ttu-id="eee7c-133">Filters verschillen op twee belangrijke manieren van query's:</span><span class="sxs-lookup"><span data-stu-id="eee7c-133">Filters differ from queries in two significant ways:</span></span>

- <span data-ttu-id="eee7c-134">Filters zijn van tijdelijke aard.</span><span class="sxs-lookup"><span data-stu-id="eee7c-134">Filters are transient.</span></span> <span data-ttu-id="eee7c-135">Ze blijven niet langer bestaan dan de bestaande sessie.</span><span class="sxs-lookup"><span data-stu-id="eee7c-135">They don't persist beyond the existing session.</span></span> <span data-ttu-id="eee7c-136">Met andere woorden, u kunt een filter niet opslaan.</span><span class="sxs-lookup"><span data-stu-id="eee7c-136">In other words, you can't save a filter.</span></span> <span data-ttu-id="eee7c-137">Query's worden opgeslagen in de revisieset en worden geopend wanneer u de revisieset opent.</span><span class="sxs-lookup"><span data-stu-id="eee7c-137">Queries are saved to the review set, and access them whenever you open the review set.</span></span>

- <span data-ttu-id="eee7c-138">Filters zijn altijd additief.</span><span class="sxs-lookup"><span data-stu-id="eee7c-138">Filters are always additive.</span></span> <span data-ttu-id="eee7c-139">Filters worden toegepast naast de huidige query voor revisiesets.</span><span class="sxs-lookup"><span data-stu-id="eee7c-139">Filters are applied in addition to the current review set query.</span></span> <span data-ttu-id="eee7c-140">Als u een andere query toepassen, worden de resultaten vervangen die door de huidige query worden geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="eee7c-140">Applying a different query will replace the results returned by the current query.</span></span>
