---
title: Ondersteuning voor CJK/Double Byte voor Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Lees hoe Advanced eDiscovery in Microsoft 365 Chinese, Japanse en Koreaanse talen (CJK) ondersteunt, waarbij een dubbele bytetekenset wordt gebruikt.
ms.openlocfilehash: ee47c5cd7f1a378ccfff05b8f7712e91092907cb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162160"
---
# <a name="cjk-language-support-for-advanced-ediscovery"></a><span data-ttu-id="f7798-103">CJK-taalondersteuning voor Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="f7798-103">CJK language support for Advanced eDiscovery</span></span>

<span data-ttu-id="f7798-104">Advanced eDiscovery ondersteunt dubbel bytetekensettalen (zoals Vereenvoudigd Chinees, Traditioneel Chinees, Japans en Koreaans, die gezamenlijk *CJK-talen* worden genoemd) voor de volgende geavanceerde scenario's in een revisieset:</span><span class="sxs-lookup"><span data-stu-id="f7798-104">Advanced eDiscovery supports double-byte character set languages (these include Simplified Chinese, Traditional Chinese, Japanese, and Korean, which are collectively known as *CJK* languages) for the following advanced scenarios in a review set:</span></span>

- <span data-ttu-id="f7798-105">Wanneer u [een query uitvoert op de gegevens in een revisieset.](review-set-search.md)</span><span class="sxs-lookup"><span data-stu-id="f7798-105">When you [query the data in a review set](review-set-search.md).</span></span>

- <span data-ttu-id="f7798-106">Wanneer u [documenten tagt in een revisieset.](tagging-documents.md)</span><span class="sxs-lookup"><span data-stu-id="f7798-106">When you [tag documents in a review set](tagging-documents.md).</span></span>

- <span data-ttu-id="f7798-107">Wanneer u [casegegevens in een revisieset analyseert](analyzing-data-in-review-set.md) met behulp van bijna dubbele detectie, e-mailthreading en themaanalyse.</span><span class="sxs-lookup"><span data-stu-id="f7798-107">When you [analyze case data in a review set](analyzing-data-in-review-set.md) by using near duplicate detection, email threading, and themes analytics.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="f7798-108">Veelgestelde vragen</span><span class="sxs-lookup"><span data-stu-id="f7798-108">Frequently asked questions</span></span>

<span data-ttu-id="f7798-109">**Hoe maak ik een zoekopdracht om items te verzamelen die CJK-tekens bevatten?**</span><span class="sxs-lookup"><span data-stu-id="f7798-109">**How do I create a search to collect items that contains CJK characters?**</span></span>

<span data-ttu-id="f7798-110">U kunt CJK-tekens gebruiken [](keyword-queries-and-search-conditions.md) voor [zoektermen,](building-search-queries.md#keyword-searches)trefwoordquery's en zoekvoorwaarden bij het zoeken naar inhoud in Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="f7798-110">You can use CJK characters for [keyword searches](building-search-queries.md#keyword-searches), [keyword queries and search conditions](keyword-queries-and-search-conditions.md) when searching for content in Advanced eDiscovery.</span></span> <span data-ttu-id="f7798-111">Het zoeken naar CJK-tekens wordt ook ondersteund bij het zoeken naar inhoud in Core eDiscovery en Inhoud zoeken.</span><span class="sxs-lookup"><span data-stu-id="f7798-111">Searching for CJK characters is also supported when searching for content in Core eDiscovery and Content Search.</span></span>

<span data-ttu-id="f7798-112">We bieden CJK-ondersteuning voor [](keyword-queries-and-search-conditions.md#search-conditions)alle [zoekoperatoren](keyword-queries-and-search-conditions.md#search-operators) en **zoekvoorwaarden,** inclusief de booleaanse operatoren **AND,** **OR,** **NOT** en NEAR.</span><span class="sxs-lookup"><span data-stu-id="f7798-112">We provide CJK support for all [search operators](keyword-queries-and-search-conditions.md#search-operators) and [search conditions](keyword-queries-and-search-conditions.md#search-conditions), including the boolean operators **AND**, **OR**, **NOT**, and **NEAR**.</span></span>

<span data-ttu-id="f7798-113">Als u er zeker van bent dat inhoudslocaties of -items CJK-tekens bevatten, maar zoekopdrachten geen resultaten opleveren, klikt u op het pictogram querytaal/regio</span><span class="sxs-lookup"><span data-stu-id="f7798-113">If you're certain that content locations or items contain CJK characters, but searches aren't returning any results, click the query language-country/region icon</span></span> ![Pictogram Querytaal/regio in zoeken naar inhoud](../media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png) <span data-ttu-id="f7798-115">en selecteer de bijbehorende cultuurcodewaarde voor taalland voor de zoekopdracht.</span><span class="sxs-lookup"><span data-stu-id="f7798-115">and select the corresponding language-country culture code value for the search.</span></span> <span data-ttu-id="f7798-116">De standaardtaal/regio is neutraal.</span><span class="sxs-lookup"><span data-stu-id="f7798-116">The default language/region is neutral.</span></span>

<span data-ttu-id="f7798-117">**Kan ik meerdere talen tegelijk zoeken?**</span><span class="sxs-lookup"><span data-stu-id="f7798-117">**Can I search for multiple languages at once?**</span></span>

<span data-ttu-id="f7798-118">Dit is afhankelijk van uw zoekscenario.</span><span class="sxs-lookup"><span data-stu-id="f7798-118">It depends on your search scenario.</span></span>

- <span data-ttu-id="f7798-119">Wanneer u [gegevens opvraagt in een revisieset](review-set-search.md) in Advanced eDiscovery, kunt u naar meerdere talen zoeken.</span><span class="sxs-lookup"><span data-stu-id="f7798-119">When you [query data in a review set](review-set-search.md) in Advanced eDiscovery, you can search for multiple languages.</span></span>

- <span data-ttu-id="f7798-120">Wanneer u [een zoekopdracht maakt om gegevens te verzamelen,](create-search-to-collect-data.md)maakt u een afzonderlijke zoekopdracht voor elke taal die u wilt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="f7798-120">When you [create a search to collect data](create-search-to-collect-data.md), create a separate search for each language you're targeting.</span></span> <span data-ttu-id="f7798-121">Als u bijvoorbeeld zoekt naar een document dat zowel Chinees als Koreaans bevat, selecteert u Chinees voor uw eerste query en selecteert u Koreaans voor uw tweede query.</span><span class="sxs-lookup"><span data-stu-id="f7798-121">For example, if you are searching for a document that contains both Chinese and Korean, select Chinese for your first query and select Korean for your second query.</span></span>

<span data-ttu-id="f7798-122">**Ik zie het pictogram querytaal/regio niet om een taal voor query's in een revisieset te selecteren. Hoe kan ik een querytaal opgeven in een zoekopdracht voor revisiesets?**</span><span class="sxs-lookup"><span data-stu-id="f7798-122">**I don't see the query language-country/region icon to select a language for queries in a review set. How can I specify a query language in a review set search?**</span></span>

<span data-ttu-id="f7798-123">Voor revisiesetquery's hoeft u geen documenttaal op te geven.</span><span class="sxs-lookup"><span data-stu-id="f7798-123">For review set queries, you don't need to specify a document language.</span></span> <span data-ttu-id="f7798-124">Advanced eDiscovery detecteert automatisch documenttalen wanneer u inhoud toevoegt aan een revisieset.</span><span class="sxs-lookup"><span data-stu-id="f7798-124">Advanced eDiscovery automatically detects document languages when you add content to a review set.</span></span> <span data-ttu-id="f7798-125">Dit helpt u bij het optimaliseren van de queryresultaten in een revisieset.</span><span class="sxs-lookup"><span data-stu-id="f7798-125">This helps you optimize your query results in a review set.</span></span>

<span data-ttu-id="f7798-126">**Kan ik gedetecteerde talen in bestandsmetagegevens [zien?](view-documents-in-review-set.md#file-metadata)**</span><span class="sxs-lookup"><span data-stu-id="f7798-126">**Can I see detected languages in [file metadata](view-documents-in-review-set.md#file-metadata)?**</span></span>

<span data-ttu-id="f7798-127">Nee, u kunt gedetecteerde talen niet zien in bestandsmetagegevens.</span><span class="sxs-lookup"><span data-stu-id="f7798-127">No, you can't see detected languages in file metadata.</span></span>

<span data-ttu-id="f7798-128">**Kan ik filteren op documenttalen in een revisieset?**</span><span class="sxs-lookup"><span data-stu-id="f7798-128">**Can I filter by document languages in a review set**?</span></span>

<span data-ttu-id="f7798-129">Nee, u kunt niet filteren, sorteren of zoeken op documenttalen in een revisieset.</span><span class="sxs-lookup"><span data-stu-id="f7798-129">No, you can't filter, sort, or search by document languages in a review set.</span></span>

<span data-ttu-id="f7798-130">**Is deze CJK-release voor revisiesetscenario's van invloed op een van mijn bestaande zoekopdrachten en revisiesets?**</span><span class="sxs-lookup"><span data-stu-id="f7798-130">**Will this CJK release for review set scenarios affect any of my existing searches and review sets?**</span></span>

<span data-ttu-id="f7798-131">Nee, geen van uw bestaande zoekopdrachten en revisiesets wordt gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="f7798-131">No, none of your existing searches and review sets will change.</span></span> <span data-ttu-id="f7798-132">U hoeft bestaande gegevens niet opnieuw te indexeren en de zoekresultaten voor Engelse tekst zijn hetzelfde.</span><span class="sxs-lookup"><span data-stu-id="f7798-132">You don't need to reindex existing data, and search results for English text will be the same.</span></span>

<span data-ttu-id="f7798-133">**Hoe wijzig ik mijn weergavetaal in Chinees, Japans of Koreaans?**</span><span class="sxs-lookup"><span data-stu-id="f7798-133">**How do I change my display language to Chinese, Japanese, or Korean?**</span></span>

<span data-ttu-id="f7798-134">Zie Taal- en regio-instellingen instellen voor meer informatie over het wijzigen van weergavetaal en -tijdzone voor [Office 365.](/office365/troubleshoot/access-management/set-language-and-region)</span><span class="sxs-lookup"><span data-stu-id="f7798-134">For information about how to change display language and time zone, see [How to set language and region settings for Office 365](/office365/troubleshoot/access-management/set-language-and-region).</span></span>

## <a name="known-issues"></a><span data-ttu-id="f7798-135">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="f7798-135">Known issues</span></span>

- <span data-ttu-id="f7798-136">OCR biedt geen ondersteuning voor CJK-tekens uit afbeeldingsbestanden</span><span class="sxs-lookup"><span data-stu-id="f7798-136">OCR doesn't support CJK characters from image files</span></span>

- <span data-ttu-id="f7798-137">E-mailbestanden (zoals \*.eml en \*.msg) [in](view-documents-in-review-set.md#annotate-view) de aantekeningenweergave worden niet ondersteund voor CJK-talen.</span><span class="sxs-lookup"><span data-stu-id="f7798-137">Email files (such as \*.eml and \*.msg) in [Annotate view](view-documents-in-review-set.md#annotate-view) aren't supported for CJK languages.</span></span>

- <span data-ttu-id="f7798-138">Zoeken in de [tekstweergave wordt](view-documents-in-review-set.md#text-view) niet ondersteund voor CJK-talen.</span><span class="sxs-lookup"><span data-stu-id="f7798-138">Search hit highlighting in [Text view](view-documents-in-review-set.md#text-view) isn't supported for CJK languages.</span></span>

- <span data-ttu-id="f7798-139">De [relevantiemodule die](using-relevance.md) wordt gebruikt om gegevens te analyseren, ondersteunt geen CJK-talen.</span><span class="sxs-lookup"><span data-stu-id="f7798-139">The [Relevance module](using-relevance.md) used to analyze data doesn't support CJK languages.</span></span>

- <span data-ttu-id="f7798-140">[Query's worden](managing-holds.md#manage-non-custodial-holds) niet ondersteund voor CJK-talen.</span><span class="sxs-lookup"><span data-stu-id="f7798-140">[Query-based holds](managing-holds.md#manage-non-custodial-holds) aren't supported for CJK languages.</span></span>