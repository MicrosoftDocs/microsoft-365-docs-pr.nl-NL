---
title: Statistieken weergeven voor eDiscovery-zoekresultaten
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.search: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
description: Lees hoe u de functie zoekstatistieken kunt gebruiken om statistieken weer te geven voor zoekopdrachten en zoekopdrachten voor inhoud die zijn gekoppeld aan een hoofd-eDiscovery-zaak in het Microsoft 365 compliancecentrum.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a0e543c89b91560520a4e4bf31feb8471c91da4a
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311094"
---
# <a name="view-statistics-for-ediscovery-search-results"></a><span data-ttu-id="dd0f0-103">Statistieken weergeven voor eDiscovery-zoekresultaten</span><span class="sxs-lookup"><span data-stu-id="dd0f0-103">View statistics for eDiscovery search results</span></span>

<span data-ttu-id="dd0f0-104">Nadat u een inhoudszoekactie of een zoekopdracht hebt uitgevoerd die is gekoppeld aan een Hoofd-eDiscovery-zaak, kunt u statistieken bekijken over de geschatte zoekresultaten.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-104">After you create and run a Content search or a search associated with a Core eDiscovery case, you can view statistics about the estimated search results.</span></span> <span data-ttu-id="dd0f0-105">Dit omvat een overzicht van de zoekresultaten (vergelijkbaar met de samenvatting van de geschatte zoekresultaten die worden weergegeven op de flyoutpagina voor zoeken), de querystatistieken, zoals het aantal inhoudslocaties met items die overeenkomen met de zoekquery en de identiteit van inhoudslocaties met de meest overeenkomende items.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-105">This includes a summary of the search results (similar to the summary of the estimated search results displayed on the search flyout page), the query statistics such as the number of content locations with items that match the search query, and the identity of content locations that have the most matching items.</span></span>
  
<span data-ttu-id="dd0f0-106">Daarnaast kunt u de lijst met trefwoorden gebruiken om een zoekopdracht te configureren om statistieken te retourneren voor elk trefwoord in een zoekquery.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-106">Additionally, you can use the keywords list to configure a search to return statistics for each keyword in a search query.</span></span> <span data-ttu-id="dd0f0-107">Hiermee kunt u het aantal resultaten vergelijken dat door elk trefwoord in een query wordt geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-107">This lets you compare the number of results returned by each keyword in a query.</span></span>
  
<span data-ttu-id="dd0f0-108">U kunt ook zoekstatistieken downloaden naar een CSV-bestand.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-108">You can also download search statistics to a CSV file.</span></span> <span data-ttu-id="dd0f0-109">Op deze manier kunt u de filter- en sorteerfuncties in Excel gebruiken om resultaten te vergelijken en rapporten voor te bereiden op uw zoekresultaten.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-109">This lets you use the filtering and sorting features in Excel to compare results, and prepare reports for your search results.</span></span>
  
## <a name="get-statistics-for-searches"></a><span data-ttu-id="dd0f0-110">Statistieken voor zoekopdrachten krijgen</span><span class="sxs-lookup"><span data-stu-id="dd0f0-110">Get statistics for searches</span></span>

<span data-ttu-id="dd0f0-111">Als u statistieken wilt weergeven voor een inhoudszoekactie of een zoekopdracht die is gekoppeld aan een hoofd-eDiscovery-zaak.:</span><span class="sxs-lookup"><span data-stu-id="dd0f0-111">To display statistics for a Content search or a search associated with a Core eDiscovery case.:</span></span>
  
1. <span data-ttu-id="dd0f0-112">Klik in Microsoft 365 compliancecentrum op **Alles tonen** en ga op een van de volgende dingen te werk:</span><span class="sxs-lookup"><span data-stu-id="dd0f0-112">In the Microsoft 365 compliance center, click **Show all**, and then do one of the following:</span></span>

   - <span data-ttu-id="dd0f0-113">Klik **op Inhoud zoeken** en selecteer vervolgens een zoekopdracht om de flyoutpagina weer te geven.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-113">Click **Content search** and then select a search to display the flyout page.</span></span>

     <span data-ttu-id="dd0f0-114">OF</span><span class="sxs-lookup"><span data-stu-id="dd0f0-114">OR</span></span>

   - <span data-ttu-id="dd0f0-115">Klik **op eDiscovery** Core, selecteer een hoofddeksel en selecteer vervolgens een zoekopdracht op het tabblad Zoekopdrachten om de  >  flyoutpagina weer te geven. </span><span class="sxs-lookup"><span data-stu-id="dd0f0-115">Click **eDiscovery** > **Core**, select a case, and then select a search on the **Searches** tab to display the flyout page.</span></span>

2. <span data-ttu-id="dd0f0-116">Klik op de flyoutpagina van de geselecteerde zoekopdracht op **het tabblad Statistieken** zoeken.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-116">On the flyout page of the selected search, click the **Search statistics** tab.</span></span>
  
   ![Het tabblad Zoekstatistieken](../media/SearchStatistics1.png)

<span data-ttu-id="dd0f0-118">Het **tabblad Zoekstatistieken** bevat voor volgende secties die verschillende soorten statistieken over de zoekopdracht bevatten.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-118">The **Search statistics** tab contains for following sections that contain different types of statistics about the search.</span></span>

### <a name="search-content"></a><span data-ttu-id="dd0f0-119">Inhoud zoeken</span><span class="sxs-lookup"><span data-stu-id="dd0f0-119">Search content</span></span>

<span data-ttu-id="dd0f0-120">In deze sectie wordt een grafische samenvatting weergegeven van de geschatte items die door de zoekopdracht worden geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-120">This section displays a graphical summary of the estimated items returned by the search.</span></span> <span data-ttu-id="dd0f0-121">Dit geeft het aantal items aan dat voldoet aan de zoekcriteria.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-121">This indicates the number of items that match the search criteria.</span></span> <span data-ttu-id="dd0f0-122">Deze informatie geeft een idee van het geschatte aantal items dat door de zoekopdracht wordt geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-122">This information gives you an idea about the estimated number of items returned by the search.</span></span>

![Zoekschattingen voor een zoekopdracht](../media/SearchContentReport.png)

- <span data-ttu-id="dd0f0-124">**Geschatte items per locatie:** het totale aantal geschatte items dat door de zoekopdracht wordt geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-124">**Estimated items by locations**: The total number of estimated items returned by the search.</span></span> <span data-ttu-id="dd0f0-125">Het specifieke aantal items in postvakken en op sites wordt ook weergegeven.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-125">The specific number of items located in mailboxes and located in sites is also displayed.</span></span>

- <span data-ttu-id="dd0f0-126">**Geschatte locaties met hits:** het totale aantal inhoudslocaties dat items bevat die door de zoekopdracht zijn geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-126">**Estimated locations with hits**: The total number of content locations that contain items returned by the search.</span></span> <span data-ttu-id="dd0f0-127">Het specifieke aantal postvakken en sitelocaties wordt ook weergegeven.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-127">The specific number of mailbox and site locations is also displayed.</span></span>

- <span data-ttu-id="dd0f0-128">**Gegevensvolume per locatie (in MB)**: de totale grootte van alle geschatte items die door de zoekopdracht worden geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-128">**Data volume by location (in MB)**: The total size of all estimated items returned by the search.</span></span> <span data-ttu-id="dd0f0-129">De specifieke grootte van postvakitems en site-items wordt ook weergegeven.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-129">The specific size of mailbox items and site items is also displayed.</span></span>

### <a name="condition-report"></a><span data-ttu-id="dd0f0-130">Rapport Voorwaarde</span><span class="sxs-lookup"><span data-stu-id="dd0f0-130">Condition report</span></span>

<span data-ttu-id="dd0f0-131">In deze sectie worden statistieken weergegeven over de zoekquery en het aantal geschatte items dat overeenkomen met verschillende onderdelen van de zoekquery.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-131">This section displays statistics about the search query and the number of estimated items that matched different parts of the search query.</span></span> <span data-ttu-id="dd0f0-132">U kunt deze statistieken gebruiken om het aantal items te analyseren dat overeenkomen met elk onderdeel van de zoekquery.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-132">You can use these statistics to analyze the number of items that match each component of search query.</span></span> <span data-ttu-id="dd0f0-133">Dit kan u helpen de zoekcriteria te verfijnen en zo nodig het bereik van het bereik te beperken.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-133">This can help you refine the search criteria and if necessary narrow the scope of the scope.</span></span> <span data-ttu-id="dd0f0-134">U kunt ook een kopie van dit rapport downloaden in CSV-indeling.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-134">You can also download a copy of this report in CSV format.</span></span>

![Rapport Voorwaarde](../media/SearchContentReportNoKeywordList.png)

- <span data-ttu-id="dd0f0-136">**Locatietype:** Het type inhoudslocatie waar de querystatistieken op van toepassing zijn.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-136">**Location type**: The type of content location that the query statistics are applicable to.</span></span> <span data-ttu-id="dd0f0-137">De waarde van **Exchange** geeft een postvaklocatie aan. een waarde van **SharePoint** geeft een sitelocatie aan.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-137">The value of **Exchange** indicates a mailbox location; a value of **SharePoint** indicates a site location.</span></span>

- <span data-ttu-id="dd0f0-138">**Deel**: Het deel van de zoekquery waar de statistieken op van toepassing zijn.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-138">**Part**: The part of the search query the statistics are applicable to.</span></span> <span data-ttu-id="dd0f0-139">**Primair** geeft de hele zoekquery aan.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-139">**Primary** indicates the entire search query.</span></span> <span data-ttu-id="dd0f0-140">**Trefwoord** geeft aan dat de statistieken in de rij voor een specifiek trefwoord zijn.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-140">**Keyword** indicates the statistics in the row are for a specific keyword.</span></span> <span data-ttu-id="dd0f0-141">Als u een trefwoordlijst voor zoekquery gebruikt, worden statistieken voor elk onderdeel van de query opgenomen in deze tabel.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-141">If you use a keyword list for search query, statistics for each component of the query are included in this table.</span></span> <span data-ttu-id="dd0f0-142">Zie Trefwoordstatistieken [voor zoekopdrachten voor meer informatie.](#get-keyword-statistics-for-searches)</span><span class="sxs-lookup"><span data-stu-id="dd0f0-142">For more information, see [Get keyword statistics for searches](#get-keyword-statistics-for-searches).</span></span>

- <span data-ttu-id="dd0f0-143">**Voorwaarde:** Het werkelijke onderdeel (trefwoord of voorwaarde) van de zoekquery die de statistieken heeft geretourneerd die in de bijbehorende rij worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-143">**Condition**: The actual component (keyword or condition) of the search query that returned the statistics displayed in the corresponding row.</span></span>

- <span data-ttu-id="dd0f0-144">**Locaties met treffers:** het aantal inhoudslocaties (opgegeven door de kolom Locatietype) die items bevatten die overeenkomen met de primaire query of trefwoordquery in de kolom **Voorwaarde.** </span><span class="sxs-lookup"><span data-stu-id="dd0f0-144">**Locations with hits**: The number of the content locations (specified by the **Location type** column) that contain items that match the primary or keyword query listed in the **Condition** column.</span></span>

- <span data-ttu-id="dd0f0-145">**Items:** Het aantal items (van de opgegeven inhoudslocatie) dat overeenkomen met de query die wordt weergegeven in **de** kolom Voorwaarde.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-145">**Items**: The number of items (from the specified content location) that match the query listed in the **Condition** column.</span></span> <span data-ttu-id="dd0f0-146">Zoals eerder uitgelegd, als een item meerdere exemplaren bevat van een trefwoord dat wordt gezocht, wordt dit slechts eenmaal geteld in deze kolom.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-146">As previously explained, if an item contains multiple instances of a keyword that is being searched for, it's only counted once in this column.</span></span>

- <span data-ttu-id="dd0f0-147">**Grootte (MB)**: De totale grootte van alle items die zijn gevonden (op de opgegeven inhoudslocatie) die overeenkomen met de zoekquery in **de** kolom Voorwaarde.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-147">**Size (MB)**: The total size of all items that were found (in the specified content location) that match the search query in the **Condition** column.</span></span>

### <a name="top-locations"></a><span data-ttu-id="dd0f0-148">Toplocaties</span><span class="sxs-lookup"><span data-stu-id="dd0f0-148">Top locations</span></span>

<span data-ttu-id="dd0f0-149">In deze sectie worden statistieken weergegeven over de specifieke inhoudslocaties met de meeste items die door de zoekopdracht worden geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-149">This section displays statistics about the specific content locations with the most items returned by the search.</span></span> <span data-ttu-id="dd0f0-150">De bovenste 1000 locaties worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-150">The top 1,000 locations are displayed.</span></span> <span data-ttu-id="dd0f0-151">U kunt ook een kopie van dit rapport downloaden in CSV-indeling.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-151">You can also download a copy of this report in CSV format.</span></span>

- <span data-ttu-id="dd0f0-152">De naam van de locatienaam (het e-mailadres van postvakken en de URL voor sites).</span><span class="sxs-lookup"><span data-stu-id="dd0f0-152">The name of the location name (the email address of mailboxes and the URL for sites).</span></span>

- <span data-ttu-id="dd0f0-153">Locatietype (een postvak of site).</span><span class="sxs-lookup"><span data-stu-id="dd0f0-153">Location type (a mailbox or site).</span></span>

- <span data-ttu-id="dd0f0-154">Geschatte hoeveelheid items op de inhoudslocatie die door de zoekopdracht wordt geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-154">Estimated number of items in the content location returned by the search.</span></span>

- <span data-ttu-id="dd0f0-155">De totale grootte van geschatte items op elke inhoudslocatie.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-155">The total size of estimated items in each content location.</span></span>

## <a name="get-keyword-statistics-for-searches"></a><span data-ttu-id="dd0f0-156">Trefwoordstatistieken voor zoekopdrachten krijgen</span><span class="sxs-lookup"><span data-stu-id="dd0f0-156">Get keyword statistics for searches</span></span>

<span data-ttu-id="dd0f0-157">Zoals eerder uitgelegd, worden in **de sectie Rapport** Voorwaarde de zoekquery en het aantal items (en de grootte) van de items die overeenkomen met de query, in de sectie Voorwaarde.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-157">As previous explained, the **Condition report** section shows the search query and the number (and size) of items that match the query.</span></span> <span data-ttu-id="dd0f0-158">Als u een lijst met trefwoorden gebruikt wanneer u een zoekquery maakt of bewerkt, kunt u uitgebreide statistieken krijgen die laten zien hoeveel items overeenkomen met elk trefwoord of trefwoord.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-158">If you use a keyword list when you create or edit a search query, you can get enhanced statistics that show how many items match each keyword or keyword phrase.</span></span> <span data-ttu-id="dd0f0-159">Op deze manier kunt u snel bepalen welke onderdelen van de query het meest (en het minst) effectief zijn.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-159">This can help you quickly identify which parts of the query are the most (and least) effective.</span></span> <span data-ttu-id="dd0f0-160">Als een trefwoord bijvoorbeeld een groot aantal items retourneert, kunt u ervoor kiezen om de trefwoordquery te verfijnen om de zoekresultaten te verfijnen.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-160">For example, if a keyword returns a large number of items, you might choose to refine the keyword query to narrow the search results.</span></span>

<span data-ttu-id="dd0f0-161">Een trefwoordlijst maken en trefwoordstatistieken weergeven voor een zoekopdracht:</span><span class="sxs-lookup"><span data-stu-id="dd0f0-161">To create a keyword list and view keyword statistics for a search:</span></span>
  
1. <span data-ttu-id="dd0f0-162">Maak in Microsoft 365 compliancecentrum een nieuwe inhoudszoekactie of een zoekopdracht die is gekoppeld aan een core eDiscovery-zaak.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-162">In the Microsoft 365 compliance center, create a new Content search or a search associated with a Core eDiscovery case.</span></span>

2. <span data-ttu-id="dd0f0-163">Op de **pagina Voorwaarden** van de wizard Zoeken.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-163">On the **Conditions** page of the search wizard.</span></span> <span data-ttu-id="dd0f0-164">schakel het **selectievakje Trefwoordlijst tonen** in.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-164">select the **Show keyword list** checkbox.</span></span>

   ![Selectievakje Trefwoordenlijst weergeven](../media/SearchKeywordsList1.png)

3. <span data-ttu-id="dd0f0-166">Typ een trefwoord of trefwoordfase in een rij in de trefwoordentabel.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-166">Type a keyword or keyword phase in a row in the keywords table.</span></span> <span data-ttu-id="dd0f0-167">Typ bijvoorbeeld **budget** in de eerste rij, typ **beveiliging** in de tweede rij en typ **FY2021** in de derde rij.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-167">For example, type **budget** in the first row, type **security** in the second row, and type **FY2021** in the third row.</span></span>

   ![Typ maximaal 20 trefwoorden of trefwoordzinnen in de lijst](../media/SearchKeywordsList2.png)

   > [!NOTE]
   > <span data-ttu-id="dd0f0-169">Als u problemen wilt beperken die worden veroorzaakt door grote lijsten met trefwoorden, kunt u maximaal 20 rijen in de lijst met trefwoorden van een zoekquery gebruiken.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-169">To help reduce issues caused by large keyword lists, you're limited to a maximum of 20 rows in the keyword list of a search query.</span></span>

4. <span data-ttu-id="dd0f0-170">Nadat u de trefwoorden hebt toegevoegd aan de lijst die u wilt zoeken en statistieken wilt krijgen, kunt u de zoekopdracht uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-170">After adding the keywords to the list that you want to search and get statistics for, run the search.</span></span>

5. <span data-ttu-id="dd0f0-171">Wanneer de zoekopdracht is voltooid, selecteert u deze om de flyoutpagina weer te geven.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-171">When the search is completed, select it to display the flyout page.</span></span>

6. <span data-ttu-id="dd0f0-172">Klik op **het tabblad Zoekstatistieken** op het **rapport Voorwaarde om** de trefwoordstatistieken voor de zoekopdracht weer te geven.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-172">On the **Search statistics** tab, click the **Condition report** to display the keyword statistics for the search.</span></span>

    ![De statistieken voor elk trefwoord worden weergegeven](../media/SearchKeywordsList3.png)
  
    <span data-ttu-id="dd0f0-174">Zoals in de vorige schermafbeelding wordt weergegeven, worden de statistieken voor elk trefwoord weergegeven. dit omvat:</span><span class="sxs-lookup"><span data-stu-id="dd0f0-174">As shown in the previous screenshot, the statistics for each keyword are displayed; this includes:</span></span>

    - <span data-ttu-id="dd0f0-175">De trefwoordstatistieken voor elk type inhoudslocatie dat is opgenomen in de zoekopdracht.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-175">The keyword statistics for each type of content location included in the search.</span></span>

    - <span data-ttu-id="dd0f0-176">Het aantal niet-geïndexeerde postvakitems.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-176">The number of unindexed mailbox items.</span></span>

    - <span data-ttu-id="dd0f0-177">De werkelijke zoekquery en de resultaten voor  elk trefwoord (geïdentificeerd als Trefwoord **in** de kolom Onderdeel), met alle voorwaarden uit de zoekquery.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-177">The actual search query and results for each keyword (identified as **Keyword** in the **Part** column), which includes any conditions from the search query.</span></span>

    - <span data-ttu-id="dd0f0-178">De volledige zoekquery (die  is geïdentificeerd als **primair** in de kolom Onderdeel) en de statistieken voor de volledige query voor elk locatietype.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-178">The complete search query (identified as **Primary** in the **Part** column) and the statistics for the complete query for each location type.</span></span> <span data-ttu-id="dd0f0-179">Let op: dit zijn dezelfde statistieken die worden weergegeven op het **tabblad** Overzicht.</span><span class="sxs-lookup"><span data-stu-id="dd0f0-179">Note these are the same statistics displayed on the **Summary** tab.</span></span>
