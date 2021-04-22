---
title: Werken met geavanceerde resultaten van query's in Microsoft 365 Defender
description: Maak gebruik van de queryresultaten die worden geretourneerd door geavanceerd zoeken in Microsoft 365 Defender
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, custom detections, schema, kusto, visualisatie, chart, filters, drill-down
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 34880c870cdf398ab1565f7f532ac95a6fde475d
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932927"
---
# <a name="work-with-advanced-hunting-query-results"></a><span data-ttu-id="6ad2c-104">Werken met geavanceerde resultaten van query's</span><span class="sxs-lookup"><span data-stu-id="6ad2c-104">Work with advanced hunting query results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="6ad2c-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="6ad2c-105">**Applies to:**</span></span>
- <span data-ttu-id="6ad2c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6ad2c-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="6ad2c-107">Hoewel u geavanceerde [](advanced-hunting-overview.md) zoekquery's kunt maken om zeer nauwkeurige informatie te retourneren, kunt u ook met de queryresultaten werken om meer inzicht te krijgen en specifieke activiteiten en indicatoren te onderzoeken.</span><span class="sxs-lookup"><span data-stu-id="6ad2c-107">While you can construct your [advanced hunting](advanced-hunting-overview.md) queries to return very precise information, you can also work with the query results to gain further insight and investigate specific activities and indicators.</span></span> <span data-ttu-id="6ad2c-108">U kunt de volgende acties uitvoeren voor de queryresultaten:</span><span class="sxs-lookup"><span data-stu-id="6ad2c-108">You can take the following actions on your query results:</span></span>

- <span data-ttu-id="6ad2c-109">Resultaten weergeven als een tabel of grafiek</span><span class="sxs-lookup"><span data-stu-id="6ad2c-109">View results as a table or chart</span></span>
- <span data-ttu-id="6ad2c-110">Tabellen en grafieken exporteren</span><span class="sxs-lookup"><span data-stu-id="6ad2c-110">Export tables and charts</span></span>
- <span data-ttu-id="6ad2c-111">Inzoomen op gedetailleerde entiteitsgegevens</span><span class="sxs-lookup"><span data-stu-id="6ad2c-111">Drill down to detailed entity information</span></span>
- <span data-ttu-id="6ad2c-112">Uw query's rechtstreeks aanpassen aan de resultaten of filters toepassen</span><span class="sxs-lookup"><span data-stu-id="6ad2c-112">Tweak your queries directly from the results or apply filters</span></span>

## <a name="view-query-results-as-a-table-or-chart"></a><span data-ttu-id="6ad2c-113">Queryresultaten weergeven als een tabel of grafiek</span><span class="sxs-lookup"><span data-stu-id="6ad2c-113">View query results as a table or chart</span></span>
<span data-ttu-id="6ad2c-114">Standaard worden queryresultaten in geavanceerde query's weergegeven als tabelgegevens.</span><span class="sxs-lookup"><span data-stu-id="6ad2c-114">By default, advanced hunting displays query results as tabular data.</span></span> <span data-ttu-id="6ad2c-115">U kunt ook dezelfde gegevens als een grafiek weergeven.</span><span class="sxs-lookup"><span data-stu-id="6ad2c-115">You can also display the same data as a chart.</span></span> <span data-ttu-id="6ad2c-116">Geavanceerde jacht ondersteunt de volgende weergaven:</span><span class="sxs-lookup"><span data-stu-id="6ad2c-116">Advanced hunting supports the following views:</span></span>

| <span data-ttu-id="6ad2c-117">Weergavetype</span><span class="sxs-lookup"><span data-stu-id="6ad2c-117">View type</span></span> | <span data-ttu-id="6ad2c-118">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="6ad2c-118">Description</span></span> |
| -- | -- |
| <span data-ttu-id="6ad2c-119">**Tabel**</span><span class="sxs-lookup"><span data-stu-id="6ad2c-119">**Table**</span></span> | <span data-ttu-id="6ad2c-120">Geeft de queryresultaten weer in tabelvorm</span><span class="sxs-lookup"><span data-stu-id="6ad2c-120">Displays the query results in tabular format</span></span> |
| <span data-ttu-id="6ad2c-121">**Kolomdiagram**</span><span class="sxs-lookup"><span data-stu-id="6ad2c-121">**Column chart**</span></span> | <span data-ttu-id="6ad2c-122">Geeft een reeks unieke items op de x-as weer als verticale balken waarvan de hoogten numerieke waarden uit een ander veld vertegenwoordigen</span><span class="sxs-lookup"><span data-stu-id="6ad2c-122">Renders a series of unique items on the x-axis as vertical bars whose heights represent numeric values from another field</span></span> |
| <span data-ttu-id="6ad2c-123">**Gestapeld kolomdiagram**</span><span class="sxs-lookup"><span data-stu-id="6ad2c-123">**Stacked column chart**</span></span> | <span data-ttu-id="6ad2c-124">Geeft een reeks unieke items op de x-as weer als gestapelde verticale balken waarvan de hoogten numerieke waarden uit een of meer andere velden vertegenwoordigen</span><span class="sxs-lookup"><span data-stu-id="6ad2c-124">Renders a series of unique items on the x-axis as stacked vertical bars whose heights represent numeric values from one or more other fields</span></span> |
| <span data-ttu-id="6ad2c-125">**Cirkeldiagram**</span><span class="sxs-lookup"><span data-stu-id="6ad2c-125">**Pie chart**</span></span> | <span data-ttu-id="6ad2c-126">Hiermee worden sectie-cirkels weergegeven die unieke items vertegenwoordigen.</span><span class="sxs-lookup"><span data-stu-id="6ad2c-126">Renders sectional pies representing unique items.</span></span> <span data-ttu-id="6ad2c-127">De grootte van elke cirkel vertegenwoordigt numerieke waarden uit een ander veld.</span><span class="sxs-lookup"><span data-stu-id="6ad2c-127">The size of each pie represents numeric values from another field.</span></span> |
| <span data-ttu-id="6ad2c-128">**Donut-diagram**</span><span class="sxs-lookup"><span data-stu-id="6ad2c-128">**Donut chart**</span></span> | <span data-ttu-id="6ad2c-129">Hiermee worden sectiebogen weergegeven die unieke items vertegenwoordigen.</span><span class="sxs-lookup"><span data-stu-id="6ad2c-129">Renders sectional arcs representing unique items.</span></span> <span data-ttu-id="6ad2c-130">De lengte van elke boog vertegenwoordigt numerieke waarden uit een ander veld.</span><span class="sxs-lookup"><span data-stu-id="6ad2c-130">The length of each arc represents numeric values from another field.</span></span> |
| <span data-ttu-id="6ad2c-131">**Lijndiagram**</span><span class="sxs-lookup"><span data-stu-id="6ad2c-131">**Line chart**</span></span> | <span data-ttu-id="6ad2c-132">Plots numerieke waarden voor een reeks unieke items en verbindt de uitgezete waarden</span><span class="sxs-lookup"><span data-stu-id="6ad2c-132">Plots numeric values for a series of unique items and connects the plotted values</span></span> |
| <span data-ttu-id="6ad2c-133">**Spreidingsdiagram**</span><span class="sxs-lookup"><span data-stu-id="6ad2c-133">**Scatter chart**</span></span> | <span data-ttu-id="6ad2c-134">Numerieke waarden voor een reeks unieke items plots</span><span class="sxs-lookup"><span data-stu-id="6ad2c-134">Plots numeric values for a series of unique items</span></span> |
| <span data-ttu-id="6ad2c-135">**Vlakdiagram**</span><span class="sxs-lookup"><span data-stu-id="6ad2c-135">**Area chart**</span></span> | <span data-ttu-id="6ad2c-136">Plots numerieke waarden voor een reeks unieke items en vult de secties onder de uitgezete waarden</span><span class="sxs-lookup"><span data-stu-id="6ad2c-136">Plots numeric values for a series of unique items and fills the sections below the plotted values</span></span> |

### <a name="construct-queries-for-effective-charts"></a><span data-ttu-id="6ad2c-137">Query's maken voor effectieve grafieken</span><span class="sxs-lookup"><span data-stu-id="6ad2c-137">Construct queries for effective charts</span></span>
<span data-ttu-id="6ad2c-138">Bij het weergeven van grafieken worden met geavanceerde jacht automatisch de kolommen met interesse en de numerieke waarden geïdentificeerd die moeten worden samengevoegd.</span><span class="sxs-lookup"><span data-stu-id="6ad2c-138">When rendering charts, advanced hunting automatically identifies columns of interest and the numeric values to aggregate.</span></span> <span data-ttu-id="6ad2c-139">Als u zinvolle grafieken wilt krijgen, maakt u uw query's om de specifieke waarden te retourneren die u wilt visualiseren.</span><span class="sxs-lookup"><span data-stu-id="6ad2c-139">To get meaningful charts, construct your queries to return the specific values you want to see visualized.</span></span> <span data-ttu-id="6ad2c-140">Hier zijn enkele voorbeeldquery's en de resulterende grafieken.</span><span class="sxs-lookup"><span data-stu-id="6ad2c-140">Here are some sample queries and the resulting charts.</span></span>

#### <a name="alerts-by-severity"></a><span data-ttu-id="6ad2c-141">Waarschuwingen op ernst</span><span class="sxs-lookup"><span data-stu-id="6ad2c-141">Alerts by severity</span></span>
<span data-ttu-id="6ad2c-142">Gebruik de operator om een numeriek aantal waarden te verkrijgen dat `summarize` u wilt grafieken.</span><span class="sxs-lookup"><span data-stu-id="6ad2c-142">Use the `summarize` operator to obtain a numeric count of the values you want to chart.</span></span> <span data-ttu-id="6ad2c-143">In de onderstaande query wordt `summarize` de operator gebruikt om het aantal waarschuwingen op ernst te krijgen.</span><span class="sxs-lookup"><span data-stu-id="6ad2c-143">The query below uses the `summarize` operator to get the number of alerts by severity.</span></span>

```kusto
AlertInfo
| summarize Total = count() by Severity
```
<span data-ttu-id="6ad2c-144">Bij het weergeven van de resultaten wordt in een kolomdiagram elke ernstwaarde weergegeven als een afzonderlijke kolom:</span><span class="sxs-lookup"><span data-stu-id="6ad2c-144">When rendering the results, a column chart displays each severity value as a separate column:</span></span>

<span data-ttu-id="6ad2c-145">![Afbeelding van geavanceerde resultaten van query's die worden weergegeven als kolomdiagram Queryresultaten voor waarschuwingen op ernst die als ](../../media/advanced-hunting-column-chart.jpg)
 *kolomdiagram worden weergegeven*</span><span class="sxs-lookup"><span data-stu-id="6ad2c-145">![Image of advanced hunting query results displayed as a column chart](../../media/advanced-hunting-column-chart.jpg)
*Query results for alerts by severity displayed as a column chart*</span></span>

#### <a name="alert-severity-by-operating-system"></a><span data-ttu-id="6ad2c-146">Ernst van waarschuwing per besturingssysteem</span><span class="sxs-lookup"><span data-stu-id="6ad2c-146">Alert severity by operating system</span></span>
<span data-ttu-id="6ad2c-147">U kunt de operator ook `summarize` gebruiken om resultaten voor te bereiden voor het in kaart brengen van waarden uit meerdere velden.</span><span class="sxs-lookup"><span data-stu-id="6ad2c-147">You could also use the `summarize` operator to prepare results for charting values from multiple fields.</span></span> <span data-ttu-id="6ad2c-148">U wilt bijvoorbeeld weten hoe de ernst van waarschuwingen wordt verdeeld over besturingssystemen (OS).</span><span class="sxs-lookup"><span data-stu-id="6ad2c-148">For example, you might want to understand how alert severities are distributed across operating systems (OS).</span></span> 

<span data-ttu-id="6ad2c-149">In de onderstaande query wordt een operator gebruikt om besturingssysteemgegevens uit de tabel te halen en vervolgens waarden in zowel de tabel als `join` `DeviceInfo` de kolommen te `summarize` `OSPlatform` `Severity` tellen:</span><span class="sxs-lookup"><span data-stu-id="6ad2c-149">The query below uses a `join` operator to pull in OS information from the `DeviceInfo` table, and then uses `summarize` to count values in both the `OSPlatform` and `Severity` columns:</span></span>

```kusto
AlertInfo
| join AlertEvidence on AlertId
| join DeviceInfo on DeviceId
| summarize Count = count() by OSPlatform, Severity 
```
<span data-ttu-id="6ad2c-150">Deze resultaten worden het best gevisualiseerd met behulp van een gestapeld kolomdiagram:</span><span class="sxs-lookup"><span data-stu-id="6ad2c-150">These results are best visualized using a stacked column chart:</span></span>

<span data-ttu-id="6ad2c-151">![Afbeelding van geavanceerde resultaten van query's die worden weergegeven als een gestapelde grafiek Queryresultaten voor waarschuwingen per besturingssysteem en ernst die worden weergegeven ](../../media/advanced-hunting-stacked-chart.jpg)
 *als een gestapelde grafiek*</span><span class="sxs-lookup"><span data-stu-id="6ad2c-151">![Image of advanced hunting query results displayed as a stacked chart](../../media/advanced-hunting-stacked-chart.jpg)
*Query results for alerts by OS and severity displayed as a stacked chart*</span></span>

#### <a name="phishing-emails-across-top-ten-sender-domains"></a><span data-ttu-id="6ad2c-152">Phishing-e-mailberichten in top tien afzenderdomeinen</span><span class="sxs-lookup"><span data-stu-id="6ad2c-152">Phishing emails across top ten sender domains</span></span>
<span data-ttu-id="6ad2c-153">Als u te maken hebt met een lijst met waarden die niet eindig is, kunt u de operator gebruiken om alleen de waarden met de meeste `Top` exemplaren in kaart te brengen.</span><span class="sxs-lookup"><span data-stu-id="6ad2c-153">If you're dealing with a list of values that isn’t finite, you can use the `Top` operator to chart only the values with the most instances.</span></span> <span data-ttu-id="6ad2c-154">Als u bijvoorbeeld de tien top tien afzenderdomeinen met de meeste phishing-e-mailberichten wilt krijgen, gebruikt u de onderstaande query:</span><span class="sxs-lookup"><span data-stu-id="6ad2c-154">For example, to get the top ten sender domains with the most phishing emails, use the query below:</span></span>

```kusto
EmailEvents
| where ThreatTypes has "Phish" 
| summarize Count = count() by SenderFromDomain 
| top 10 by Count
```
<span data-ttu-id="6ad2c-155">Gebruik de cirkeldiagramweergave om de verdeling over de bovenste domeinen effectief weer te geven:</span><span class="sxs-lookup"><span data-stu-id="6ad2c-155">Use the pie chart view to effectively show distribution across the top domains:</span></span>

<span data-ttu-id="6ad2c-156">![Afbeelding van geavanceerde resultaten van query's die worden weergegeven als cirkeldiagram Cirkeldiagram met de verdeling van ](../../media/advanced-hunting-pie-chart.jpg)
 *phishing-e-mailberichten over domeinen met de belangrijkste afzender*</span><span class="sxs-lookup"><span data-stu-id="6ad2c-156">![Image of advanced hunting query results displayed as a pie chart](../../media/advanced-hunting-pie-chart.jpg)
*Pie chart showing distribution of phishing emails across top sender domains*</span></span>

#### <a name="file-activities-over-time"></a><span data-ttu-id="6ad2c-157">Bestandsactiviteiten in de tijd</span><span class="sxs-lookup"><span data-stu-id="6ad2c-157">File activities over time</span></span>
<span data-ttu-id="6ad2c-158">Met behulp `summarize` van de operator met de functie kunt u controleren op gebeurtenissen met een bepaalde indicator in de `bin()` tijd.</span><span class="sxs-lookup"><span data-stu-id="6ad2c-158">Using the `summarize` operator with the `bin()` function, you can check for events involving a particular indicator over time.</span></span> <span data-ttu-id="6ad2c-159">In de onderstaande query worden gebeurtenissen met het bestand geteld met intervallen van 30 minuten om pieken in activiteit met betrekking `invoice.doc` tot dat bestand weer te geven:</span><span class="sxs-lookup"><span data-stu-id="6ad2c-159">The query below counts events involving the file `invoice.doc` at 30 minute intervals to show spikes in activity related to that file:</span></span>

```kusto
AppFileEvents
| union DeviceFileEvents
| where FileName == "invoice.doc"
| summarize FileCount = count() by bin(Timestamp, 30m)
```
<span data-ttu-id="6ad2c-160">In het onderstaande lijndiagram worden duidelijk perioden met meer activiteiten met betrekking tot `invoice.doc` :</span><span class="sxs-lookup"><span data-stu-id="6ad2c-160">The line chart below clearly highlights time periods with more activity involving `invoice.doc`:</span></span> 

<span data-ttu-id="6ad2c-161">![Afbeelding van geavanceerde resultaten van query's die worden weergegeven als een lijndiagram Lijndiagram met het aantal gebeurtenissen met ](../../media/advanced-hunting-line-chart.jpg)
 *een bestand in de tijd*</span><span class="sxs-lookup"><span data-stu-id="6ad2c-161">![Image of advanced hunting query results displayed as a line chart](../../media/advanced-hunting-line-chart.jpg)
*Line chart showing the number of events involving a file over time*</span></span>


## <a name="export-tables-and-charts"></a><span data-ttu-id="6ad2c-162">Tabellen en grafieken exporteren</span><span class="sxs-lookup"><span data-stu-id="6ad2c-162">Export tables and charts</span></span>
<span data-ttu-id="6ad2c-163">Nadat u een query hebt uitgevoerd, **selecteert u Exporteren om** de resultaten op te slaan in een lokaal bestand.</span><span class="sxs-lookup"><span data-stu-id="6ad2c-163">After running a query, select **Export** to save the results to local file.</span></span> <span data-ttu-id="6ad2c-164">De gekozen weergave bepaalt hoe de resultaten worden geëxporteerd:</span><span class="sxs-lookup"><span data-stu-id="6ad2c-164">Your chosen view determines how the results are exported:</span></span>

- <span data-ttu-id="6ad2c-165">**Tabelweergave:** de queryresultaten worden in tabelvorm geëxporteerd als een Microsoft Excel-werkmap</span><span class="sxs-lookup"><span data-stu-id="6ad2c-165">**Table view** — the query results are exported in tabular form as a Microsoft Excel workbook</span></span>
- <span data-ttu-id="6ad2c-166">**Een grafiek:** de queryresultaten worden geëxporteerd als EEN JPEG-afbeelding van de weergegeven grafiek</span><span class="sxs-lookup"><span data-stu-id="6ad2c-166">**Any chart** — the query results are exported as a JPEG image of the rendered chart</span></span>

## <a name="drill-down-from-query-results"></a><span data-ttu-id="6ad2c-167">Inzoomen op queryresultaten</span><span class="sxs-lookup"><span data-stu-id="6ad2c-167">Drill down from query results</span></span>
<span data-ttu-id="6ad2c-168">Als u snel een record in de queryresultaten wilt controleren, selecteert u de bijbehorende rij om het **deelvenster Record** controleren te openen.</span><span class="sxs-lookup"><span data-stu-id="6ad2c-168">To quickly inspect a record in your query results, select the corresponding row to open the **Inspect record** panel.</span></span> <span data-ttu-id="6ad2c-169">Het deelvenster bevat de volgende informatie op basis van de geselecteerde record:</span><span class="sxs-lookup"><span data-stu-id="6ad2c-169">The panel provides the following information based on the selected record:</span></span>

- <span data-ttu-id="6ad2c-170">**Activa:** een overzicht van de belangrijkste activa (postvakken, apparaten en gebruikers) die in de record zijn gevonden, aangevuld met beschikbare informatie, zoals risico- en blootstellingsniveaus</span><span class="sxs-lookup"><span data-stu-id="6ad2c-170">**Assets** — summarized view of the main assets (mailboxes, devices, and users) found in the record, enriched with available information, such as risk and exposure levels</span></span>
- <span data-ttu-id="6ad2c-171">**Processtructuur:** gegenereerd voor records met procesgegevens en uitgebreid met behulp van beschikbare contextuele informatie; Query's die meer kolommen retourneren, kunnen over het algemeen leiden tot rijkere procesbomen.</span><span class="sxs-lookup"><span data-stu-id="6ad2c-171">**Process tree** — generated for records with process information and enriched using available contextual information; in general, queries that return more columns can result in richer process trees.</span></span>
- <span data-ttu-id="6ad2c-172">**Alle details:** alle waarden uit de kolommen in de record</span><span class="sxs-lookup"><span data-stu-id="6ad2c-172">**All details** — all the values from the columns in the record</span></span>  

![Afbeelding van geselecteerde record met deelvenster voor het controleren van de record](../../media/mtp-ah/inspect-record.png)

<span data-ttu-id="6ad2c-174">Als u meer informatie wilt weergeven over een specifieke entiteit in de queryresultaten, zoals een computer, bestand, gebruiker, IP-adres of URL, selecteert u de entiteit-id om een gedetailleerde profielpagina voor die entiteit te openen.</span><span class="sxs-lookup"><span data-stu-id="6ad2c-174">To view more information about a specific entity in your query results, such as a machine, file, user, IP address, or URL, select the entity identifier to open a detailed profile page for that entity.</span></span>

## <a name="tweak-your-queries-from-the-results"></a><span data-ttu-id="6ad2c-175">Uw query's aanpassen aan de hand van de resultaten</span><span class="sxs-lookup"><span data-stu-id="6ad2c-175">Tweak your queries from the results</span></span>
<span data-ttu-id="6ad2c-176">Klik met de rechtermuisknop op een waarde in de resultatenset om de query snel te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="6ad2c-176">Right-click a value in the result set to quickly enhance your query.</span></span> <span data-ttu-id="6ad2c-177">U kunt de opties gebruiken om:</span><span class="sxs-lookup"><span data-stu-id="6ad2c-177">You can use the options to:</span></span>

- <span data-ttu-id="6ad2c-178">Zoek expliciet naar de geselecteerde waarde ( `==` )</span><span class="sxs-lookup"><span data-stu-id="6ad2c-178">Explicitly look for the selected value (`==`)</span></span>
- <span data-ttu-id="6ad2c-179">De geselecteerde waarde uitsluiten van de query ( `!=` )</span><span class="sxs-lookup"><span data-stu-id="6ad2c-179">Exclude the selected value from the query (`!=`)</span></span>
- <span data-ttu-id="6ad2c-180">Meer geavanceerde operatoren voor het toevoegen van de waarde aan uw query, zoals `contains` , `starts with` en `ends with`</span><span class="sxs-lookup"><span data-stu-id="6ad2c-180">Get more advanced operators for adding the value to your query, such as `contains`, `starts with` and `ends with`</span></span> 

![Afbeelding van geavanceerde resultatenset voor de jacht](../../media/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a><span data-ttu-id="6ad2c-182">De queryresultaten filteren</span><span class="sxs-lookup"><span data-stu-id="6ad2c-182">Filter the query results</span></span>
<span data-ttu-id="6ad2c-183">De filters die aan de rechterkant worden weergegeven, geven een overzicht van de resultatenset.</span><span class="sxs-lookup"><span data-stu-id="6ad2c-183">The filters displayed to the right provide a summary of the result set.</span></span> <span data-ttu-id="6ad2c-184">Elke kolom heeft een eigen sectie met de verschillende waarden die voor die kolom zijn gevonden en het aantal exemplaren.</span><span class="sxs-lookup"><span data-stu-id="6ad2c-184">Each column has its own section that lists the distinct values found for that column and the number of instances.</span></span>

<span data-ttu-id="6ad2c-185">Verfijn de query door de of knoppen te selecteren op de waarden die u wilt opnemen of uitsluiten en selecteer `+` `-` vervolgens Query **uitvoeren.**</span><span class="sxs-lookup"><span data-stu-id="6ad2c-185">Refine your query by selecting the `+` or `-` buttons on the values that you want to include or exclude and then selecting **Run query**.</span></span>

![Afbeelding van geavanceerd zoekfilter](../../media/advanced-hunting-filter.png)

<span data-ttu-id="6ad2c-187">Nadat u het filter hebt toegepast om de query te wijzigen en de query vervolgens uit te voeren, worden de resultaten dienovereenkomstig bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="6ad2c-187">Once you apply the filter to modify the query and then run the query, the results are updated accordingly.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6ad2c-188">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="6ad2c-188">Related topics</span></span>
- [<span data-ttu-id="6ad2c-189">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="6ad2c-189">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="6ad2c-190">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="6ad2c-190">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="6ad2c-191">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="6ad2c-191">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="6ad2c-192">Opsporen op apparaten en in e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="6ad2c-192">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="6ad2c-193">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="6ad2c-193">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="6ad2c-194">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="6ad2c-194">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="6ad2c-195">Overzicht van aangepaste detectie</span><span class="sxs-lookup"><span data-stu-id="6ad2c-195">Custom detections overview</span></span>](custom-detections-overview.md)
