---
title: Werken met geavanceerde queryresultaten in Microsoft 365 Defender
description: Maak zo veel mogelijk gebruik van de queryresultaten die het resultaat zijn van geavanceerd zoeken in Microsoft 365 Defender
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, custom detections, schema, kusto, microsoft 365, Microsoft Threat Protection, visualization, chart, filters, drill-down
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 462ba35f584b45bbfeb0d8a3de3b118ba1c9e17c
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932320"
---
# <a name="work-with-advanced-hunting-query-results"></a><span data-ttu-id="9a88b-104">Werken met geavanceerde queryresultaten</span><span class="sxs-lookup"><span data-stu-id="9a88b-104">Work with advanced hunting query results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="9a88b-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="9a88b-105">**Applies to:**</span></span>
- <span data-ttu-id="9a88b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9a88b-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="9a88b-107">Hoewel u geavanceerde [](advanced-hunting-overview.md) zoekquery's kunt maken om zeer nauwkeurige gegevens te retourneren, kunt u ook met de queryresultaten werken om meer inzicht te krijgen en specifieke activiteiten en indicatoren te onderzoeken.</span><span class="sxs-lookup"><span data-stu-id="9a88b-107">While you can construct your [advanced hunting](advanced-hunting-overview.md) queries to return very precise information, you can also work with the query results to gain further insight and investigate specific activities and indicators.</span></span> <span data-ttu-id="9a88b-108">U kunt de volgende acties uitvoeren op uw queryresultaten:</span><span class="sxs-lookup"><span data-stu-id="9a88b-108">You can take the following actions on your query results:</span></span>

- <span data-ttu-id="9a88b-109">Resultaten weergeven als een tabel of grafiek</span><span class="sxs-lookup"><span data-stu-id="9a88b-109">View results as a table or chart</span></span>
- <span data-ttu-id="9a88b-110">Tabellen en grafieken exporteren</span><span class="sxs-lookup"><span data-stu-id="9a88b-110">Export tables and charts</span></span>
- <span data-ttu-id="9a88b-111">Inzoomen op gedetailleerde informatie over de entiteit</span><span class="sxs-lookup"><span data-stu-id="9a88b-111">Drill down to detailed entity information</span></span>
- <span data-ttu-id="9a88b-112">Uw query's rechtstreeks aanpassen aan de hand van de resultaten of filters toepassen</span><span class="sxs-lookup"><span data-stu-id="9a88b-112">Tweak your queries directly from the results or apply filters</span></span>

## <a name="view-query-results-as-a-table-or-chart"></a><span data-ttu-id="9a88b-113">Queryresultaten weergeven als een tabel of grafiek</span><span class="sxs-lookup"><span data-stu-id="9a88b-113">View query results as a table or chart</span></span>
<span data-ttu-id="9a88b-114">Bij geavanceerd zoeken worden queryresultaten standaard weergegeven als tabelgegevens.</span><span class="sxs-lookup"><span data-stu-id="9a88b-114">By default, advanced hunting displays query results as tabular data.</span></span> <span data-ttu-id="9a88b-115">U kunt dezelfde gegevens ook als een grafiek weergeven.</span><span class="sxs-lookup"><span data-stu-id="9a88b-115">You can also display the same data as a chart.</span></span> <span data-ttu-id="9a88b-116">Geavanceerd zoeken ondersteunt de volgende weergaven:</span><span class="sxs-lookup"><span data-stu-id="9a88b-116">Advanced hunting supports the following views:</span></span>

| <span data-ttu-id="9a88b-117">Weergavetype</span><span class="sxs-lookup"><span data-stu-id="9a88b-117">View type</span></span> | <span data-ttu-id="9a88b-118">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="9a88b-118">Description</span></span> |
| -- | -- |
| <span data-ttu-id="9a88b-119">**Tabel**</span><span class="sxs-lookup"><span data-stu-id="9a88b-119">**Table**</span></span> | <span data-ttu-id="9a88b-120">Geeft de queryresultaten weer in tabelindeling</span><span class="sxs-lookup"><span data-stu-id="9a88b-120">Displays the query results in tabular format</span></span> |
| <span data-ttu-id="9a88b-121">**Kolomdiagram**</span><span class="sxs-lookup"><span data-stu-id="9a88b-121">**Column chart**</span></span> | <span data-ttu-id="9a88b-122">Geeft een reeks unieke items op de x-as weer als verticale balken waarvan de hoogte numerieke waarden uit een ander veld vertegenwoordigt</span><span class="sxs-lookup"><span data-stu-id="9a88b-122">Renders a series of unique items on the x-axis as vertical bars whose heights represent numeric values from another field</span></span> |
| <span data-ttu-id="9a88b-123">**Gestapeld kolomdiagram**</span><span class="sxs-lookup"><span data-stu-id="9a88b-123">**Stacked column chart**</span></span> | <span data-ttu-id="9a88b-124">Geeft een reeks unieke items op de x-as weer als gestapelde verticale balken waarvan de hoogte numerieke waarden uit een of meer andere velden vertegenwoordigt</span><span class="sxs-lookup"><span data-stu-id="9a88b-124">Renders a series of unique items on the x-axis as stacked vertical bars whose heights represent numeric values from one or more other fields</span></span> |
| <span data-ttu-id="9a88b-125">**Cirkeldiagram**</span><span class="sxs-lookup"><span data-stu-id="9a88b-125">**Pie chart**</span></span> | <span data-ttu-id="9a88b-126">Hiermee worden sectie cirkels weergegeven die unieke items vertegenwoordigen.</span><span class="sxs-lookup"><span data-stu-id="9a88b-126">Renders sectional pies representing unique items.</span></span> <span data-ttu-id="9a88b-127">De grootte van elke cirkel vertegenwoordigt numerieke waarden uit een ander veld.</span><span class="sxs-lookup"><span data-stu-id="9a88b-127">The size of each pie represents numeric values from another field.</span></span> |
| <span data-ttu-id="9a88b-128">**Donut chart**</span><span class="sxs-lookup"><span data-stu-id="9a88b-128">**Donut chart**</span></span> | <span data-ttu-id="9a88b-129">Hiermee worden sectiebogen weergegeven die unieke items vertegenwoordigen.</span><span class="sxs-lookup"><span data-stu-id="9a88b-129">Renders sectional arcs representing unique items.</span></span> <span data-ttu-id="9a88b-130">De lengte van elke boog vertegenwoordigt numerieke waarden uit een ander veld.</span><span class="sxs-lookup"><span data-stu-id="9a88b-130">The length of each arc represents numeric values from another field.</span></span> |
| <span data-ttu-id="9a88b-131">**Lijndiagram**</span><span class="sxs-lookup"><span data-stu-id="9a88b-131">**Line chart**</span></span> | <span data-ttu-id="9a88b-132">Zet numerieke waarden uit voor een reeks unieke items en verbindt de uitgezet waarden</span><span class="sxs-lookup"><span data-stu-id="9a88b-132">Plots numeric values for a series of unique items and connects the plotted values</span></span> |
| <span data-ttu-id="9a88b-133">**Spreidingsdiagram**</span><span class="sxs-lookup"><span data-stu-id="9a88b-133">**Scatter chart**</span></span> | <span data-ttu-id="9a88b-134">Numerieke waarden uitlijnen voor een reeks unieke items</span><span class="sxs-lookup"><span data-stu-id="9a88b-134">Plots numeric values for a series of unique items</span></span> |
| <span data-ttu-id="9a88b-135">**Vlakdiagram**</span><span class="sxs-lookup"><span data-stu-id="9a88b-135">**Area chart**</span></span> | <span data-ttu-id="9a88b-136">Zet numerieke waarden uit voor een reeks unieke items en vult de secties onder de uitgezete waarden</span><span class="sxs-lookup"><span data-stu-id="9a88b-136">Plots numeric values for a series of unique items and fills the sections below the plotted values</span></span> |

### <a name="construct-queries-for-effective-charts"></a><span data-ttu-id="9a88b-137">Query's maken voor effectieve grafieken</span><span class="sxs-lookup"><span data-stu-id="9a88b-137">Construct queries for effective charts</span></span>
<span data-ttu-id="9a88b-138">Bij het weergeven van grafieken herkent geavanceerd zoeken automatisch de aandachtskolommen en de numerieke waarden die moeten worden samengevoegd.</span><span class="sxs-lookup"><span data-stu-id="9a88b-138">When rendering charts, advanced hunting automatically identifies columns of interest and the numeric values to aggregate.</span></span> <span data-ttu-id="9a88b-139">Voor een zinvolle grafiek kunt u query's maken om de specifieke waarden te retourneren die u wilt visualiseren.</span><span class="sxs-lookup"><span data-stu-id="9a88b-139">To get meaningful charts, construct your queries to return the specific values you want to see visualized.</span></span> <span data-ttu-id="9a88b-140">Hier zijn enkele voorbeeldquery's en de resulterende grafieken.</span><span class="sxs-lookup"><span data-stu-id="9a88b-140">Here are some sample queries and the resulting charts.</span></span>

#### <a name="alerts-by-severity"></a><span data-ttu-id="9a88b-141">Waarschuwingen op ernst</span><span class="sxs-lookup"><span data-stu-id="9a88b-141">Alerts by severity</span></span>
<span data-ttu-id="9a88b-142">Gebruik de `summarize` operator om een numerieke telling te verkrijgen van de waarden die u in een grafiek wilt onder brengen.</span><span class="sxs-lookup"><span data-stu-id="9a88b-142">Use the `summarize` operator to obtain a numeric count of the values you want to chart.</span></span> <span data-ttu-id="9a88b-143">In de onderstaande query wordt `summarize` de operator gebruikt om het aantal waarschuwingen op ernst op te vragen.</span><span class="sxs-lookup"><span data-stu-id="9a88b-143">The query below uses the `summarize` operator to get the number of alerts by severity.</span></span>

```kusto
AlertInfo
| summarize Total = count() by Severity
```
<span data-ttu-id="9a88b-144">Bij het weergeven van de resultaten wordt in een kolomdiagram elke ernstwaarde als een aparte kolom weergegeven:</span><span class="sxs-lookup"><span data-stu-id="9a88b-144">When rendering the results, a column chart displays each severity value as a separate column:</span></span>

<span data-ttu-id="9a88b-145">![Afbeelding van geavanceerde queryresultaten in de query als kolomdiagram Queryresultaten voor waarschuwingen op ernst ](../../media/advanced-hunting-column-chart.jpg)
 *die als kolomdiagram worden weergegeven*</span><span class="sxs-lookup"><span data-stu-id="9a88b-145">![Image of advanced hunting query results displayed as a column chart](../../media/advanced-hunting-column-chart.jpg)
*Query results for alerts by severity displayed as a column chart*</span></span>

#### <a name="alert-severity-by-operating-system"></a><span data-ttu-id="9a88b-146">Ernst van waarschuwingen per besturingssysteem</span><span class="sxs-lookup"><span data-stu-id="9a88b-146">Alert severity by operating system</span></span>
<span data-ttu-id="9a88b-147">U kunt de operator ook gebruiken om de resultaten voor te bereiden voor het in kaart brengen `summarize` van waarden uit meerdere velden.</span><span class="sxs-lookup"><span data-stu-id="9a88b-147">You could also use the `summarize` operator to prepare results for charting values from multiple fields.</span></span> <span data-ttu-id="9a88b-148">U wilt bijvoorbeeld weten hoe ernst van waarschuwingen is verdeeld over het besturingssysteem.</span><span class="sxs-lookup"><span data-stu-id="9a88b-148">For example, you might want to understand how alert severities are distributed across operating systems (OS).</span></span> 

<span data-ttu-id="9a88b-149">De onderstaande query gebruikt een operator om OS-gegevens op te halen uit de tabel en wordt vervolgens gebruikt om waarden in zowel de tabel als de kolommen `join` `DeviceInfo` te `summarize` `OSPlatform` `Severity` tellen:</span><span class="sxs-lookup"><span data-stu-id="9a88b-149">The query below uses a `join` operator to pull in OS information from the `DeviceInfo` table, and then uses `summarize` to count values in both the `OSPlatform` and `Severity` columns:</span></span>

```kusto
AlertInfo
| join AlertEvidence on AlertId
| join DeviceInfo on DeviceId
| summarize Count = count() by OSPlatform, Severity 
```
<span data-ttu-id="9a88b-150">Deze resultaten worden het best gevisualiseerd met behulp van een gestapeld kolomdiagram:</span><span class="sxs-lookup"><span data-stu-id="9a88b-150">These results are best visualized using a stacked column chart:</span></span>

<span data-ttu-id="9a88b-151">![Afbeelding van geavanceerde queryresultaten in een gestapelde grafiek voor waarschuwingen per besturingssysteem en ernst die worden weergegeven ](../../media/advanced-hunting-stacked-chart.jpg)
 *als een gestapelde grafiek*</span><span class="sxs-lookup"><span data-stu-id="9a88b-151">![Image of advanced hunting query results displayed as a stacked chart](../../media/advanced-hunting-stacked-chart.jpg)
*Query results for alerts by OS and severity displayed as a stacked chart*</span></span>

#### <a name="phishing-emails-across-top-ten-sender-domains"></a><span data-ttu-id="9a88b-152">Phishing-e-mailberichten in de tien belangrijkste afzenderdomeinen</span><span class="sxs-lookup"><span data-stu-id="9a88b-152">Phishing emails across top ten sender domains</span></span>
<span data-ttu-id="9a88b-153">Als u te maken hebt met een lijst met waarden die niet is eindig, kunt u de operator gebruiken om alleen de waarden in een grafiek met `Top` de meeste gevallen weer te geven.</span><span class="sxs-lookup"><span data-stu-id="9a88b-153">If you're dealing with a list of values that isn’t finite, you can use the `Top` operator to chart only the values with the most instances.</span></span> <span data-ttu-id="9a88b-154">Gebruik de onderstaande query om de tien topdomeinen met de meeste phishing-e-mailberichten op te halen:</span><span class="sxs-lookup"><span data-stu-id="9a88b-154">For example, to get the top ten sender domains with the most phishing emails, use the query below:</span></span>

```kusto
EmailEvents
| where PhishFilterVerdict == "Phish"
| summarize Count = count() by SenderFromDomain
| top 10 by Count
```
<span data-ttu-id="9a88b-155">Gebruik de weergave cirkeldiagram om effectief de verdeling over de belangrijkste domeinen weer te geven:</span><span class="sxs-lookup"><span data-stu-id="9a88b-155">Use the pie chart view to effectively show distribution across the top domains:</span></span>

<span data-ttu-id="9a88b-156">![Afbeelding van geavanceerde queryresultaten in een cirkeldiagram waarin de distributie van phishing-e-mailberichten over de domeinen van de ](../../media/advanced-hunting-pie-chart.jpg)
 *belangrijkste afzender wordt weergegeven*</span><span class="sxs-lookup"><span data-stu-id="9a88b-156">![Image of advanced hunting query results displayed as a pie chart](../../media/advanced-hunting-pie-chart.jpg)
*Pie chart showing distribution of phishing emails across top sender domains*</span></span>

#### <a name="file-activities-over-time"></a><span data-ttu-id="9a88b-157">Bestandsactiviteiten in de tijd</span><span class="sxs-lookup"><span data-stu-id="9a88b-157">File activities over time</span></span>
<span data-ttu-id="9a88b-158">Met de operator voor de functie kunt u controleren op gebeurtenissen met `summarize` een bepaalde indicator in de `bin()` tijd.</span><span class="sxs-lookup"><span data-stu-id="9a88b-158">Using the `summarize` operator with the `bin()` function, you can check for events involving a particular indicator over time.</span></span> <span data-ttu-id="9a88b-159">Met de onderstaande query worden gebeurtenissen met betrekking tot het bestand geteld met intervallen van 30 minuten om pieken weer te geven in activiteit die `invoice.doc` betrekking heeft op dat bestand:</span><span class="sxs-lookup"><span data-stu-id="9a88b-159">The query below counts events involving the file `invoice.doc` at 30 minute intervals to show spikes in activity related to that file:</span></span>

```kusto
AppFileEvents
| union DeviceFileEvents
| where FileName == "invoice.doc"
| summarize FileCount = count() by bin(Timestamp, 30m)
```
<span data-ttu-id="9a88b-160">In het onderstaande lijndiagram worden perioden duidelijk aangegeven met meer activiteiten met betrekking `invoice.doc` tot:</span><span class="sxs-lookup"><span data-stu-id="9a88b-160">The line chart below clearly highlights time periods with more activity involving `invoice.doc`:</span></span> 

<span data-ttu-id="9a88b-161">![Afbeelding van geavanceerde queryresultaten in een lijndiagram met het aantal gebeurtenissen voor een bestand ](../../media/advanced-hunting-line-chart.jpg)
 *in de tijd*</span><span class="sxs-lookup"><span data-stu-id="9a88b-161">![Image of advanced hunting query results displayed as a line chart](../../media/advanced-hunting-line-chart.jpg)
*Line chart showing the number of events involving a file over time*</span></span>


## <a name="export-tables-and-charts"></a><span data-ttu-id="9a88b-162">Tabellen en grafieken exporteren</span><span class="sxs-lookup"><span data-stu-id="9a88b-162">Export tables and charts</span></span>
<span data-ttu-id="9a88b-163">Nadat u een query hebt uitgevoerd, **selecteert u Exporteren om** de resultaten op te slaan in een lokaal bestand.</span><span class="sxs-lookup"><span data-stu-id="9a88b-163">After running a query, select **Export** to save the results to local file.</span></span> <span data-ttu-id="9a88b-164">De gekozen weergave bepaalt hoe de resultaten worden geëxporteerd:</span><span class="sxs-lookup"><span data-stu-id="9a88b-164">Your chosen view determines how the results are exported:</span></span>

- <span data-ttu-id="9a88b-165">**Tabelweergave:** de queryresultaten worden in tabelvorm geëxporteerd als een Microsoft Excel-werkmap</span><span class="sxs-lookup"><span data-stu-id="9a88b-165">**Table view** — the query results are exported in tabular form as a Microsoft Excel workbook</span></span>
- <span data-ttu-id="9a88b-166">**Een grafiek:** de queryresultaten worden geëxporteerd als JPEG-afbeelding van de weergegeven grafiek</span><span class="sxs-lookup"><span data-stu-id="9a88b-166">**Any chart** — the query results are exported as a JPEG image of the rendered chart</span></span>

## <a name="drill-down-from-query-results"></a><span data-ttu-id="9a88b-167">Inzoomen op queryresultaten</span><span class="sxs-lookup"><span data-stu-id="9a88b-167">Drill down from query results</span></span>
<span data-ttu-id="9a88b-168">Als u snel een record in de queryresultaten wilt controleren, selecteert u de bijbehorende rij om het **deelvenster Record controleren te** openen.</span><span class="sxs-lookup"><span data-stu-id="9a88b-168">To quickly inspect a record in your query results, select the corresponding row to open the **Inspect record** panel.</span></span> <span data-ttu-id="9a88b-169">In het deelvenster wordt de volgende informatie weergegeven op basis van de geselecteerde record:</span><span class="sxs-lookup"><span data-stu-id="9a88b-169">The panel provides the following information based on the selected record:</span></span>

- <span data-ttu-id="9a88b-170">**Activa:** samengevatte weergave van de belangrijkste activa (postvakken, apparaten en gebruikers) die in de record zijn gevonden, die worden uitgebreid met beschikbare informatie, zoals risico- en blootstellingsniveaus</span><span class="sxs-lookup"><span data-stu-id="9a88b-170">**Assets** — summarized view of the main assets (mailboxes, devices, and users) found in the record, enriched with available information, such as risk and exposure levels</span></span>
- <span data-ttu-id="9a88b-171">**Processtructuur:** gegenereerd voor records met procesinformatie en wordt gebruikt met behulp van beschikbare contextuele informatie; In het algemeen kunnen query's die meer kolommen retourneren resulteren in uitgebreidere procesbomen.</span><span class="sxs-lookup"><span data-stu-id="9a88b-171">**Process tree** — generated for records with process information and enriched using available contextual information; in general, queries that return more columns can result in richer process trees.</span></span>
- <span data-ttu-id="9a88b-172">**Alle details:** alle waarden uit de kolommen in de record</span><span class="sxs-lookup"><span data-stu-id="9a88b-172">**All details** — all the values from the columns in the record</span></span>  

![Afbeelding van de geselecteerde record met deelvenster voor het controleren van de record](../../media/mtp-ah/inspect-record.png)

<span data-ttu-id="9a88b-174">Als u meer informatie wilt weergeven over een specifieke entiteit in uw queryresultaten, zoals een computer, bestand, gebruiker, IP-adres of URL, selecteert u de entiteits-id om een gedetailleerde profielpagina voor die entiteit te openen.</span><span class="sxs-lookup"><span data-stu-id="9a88b-174">To view more information about a specific entity in your query results, such as a machine, file, user, IP address, or URL, select the entity identifier to open a detailed profile page for that entity.</span></span>

## <a name="tweak-your-queries-from-the-results"></a><span data-ttu-id="9a88b-175">Uw query's aanpassen aan de hand van de resultaten</span><span class="sxs-lookup"><span data-stu-id="9a88b-175">Tweak your queries from the results</span></span>
<span data-ttu-id="9a88b-176">Klik met de rechtermuisknop op een waarde in de resultatenset om uw query snel te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="9a88b-176">Right-click a value in the result set to quickly enhance your query.</span></span> <span data-ttu-id="9a88b-177">U kunt de volgende opties gebruiken:</span><span class="sxs-lookup"><span data-stu-id="9a88b-177">You can use the options to:</span></span>

- <span data-ttu-id="9a88b-178">De geselecteerde waarde expliciet zoeken `==` ()</span><span class="sxs-lookup"><span data-stu-id="9a88b-178">Explicitly look for the selected value (`==`)</span></span>
- <span data-ttu-id="9a88b-179">De geselecteerde waarde uitsluiten van de query ( `!=` )</span><span class="sxs-lookup"><span data-stu-id="9a88b-179">Exclude the selected value from the query (`!=`)</span></span>
- <span data-ttu-id="9a88b-180">Geavanceerdere operatoren voor het toevoegen van de waarde aan uw query, `contains` zoals `starts with``ends with`</span><span class="sxs-lookup"><span data-stu-id="9a88b-180">Get more advanced operators for adding the value to your query, such as `contains`, `starts with` and `ends with`</span></span> 

![Afbeelding van geavanceerde resultatenset voor zoeken](../../media/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a><span data-ttu-id="9a88b-182">De queryresultaten filteren</span><span class="sxs-lookup"><span data-stu-id="9a88b-182">Filter the query results</span></span>
<span data-ttu-id="9a88b-183">De rechts weergegeven filters geven een overzicht van de resultatenset.</span><span class="sxs-lookup"><span data-stu-id="9a88b-183">The filters displayed to the right provide a summary of the result set.</span></span> <span data-ttu-id="9a88b-184">Elke kolom heeft een eigen sectie met de unieke waarden die voor die kolom zijn gevonden en het aantal exemplaren.</span><span class="sxs-lookup"><span data-stu-id="9a88b-184">Each column has its own section that lists the distinct values found for that column and the number of instances.</span></span>

<span data-ttu-id="9a88b-185">Verfijn uw query door de (knoppen) te selecteren op de waarden die u wilt opnemen of uitsluiten en selecteer `+` `-` vervolgens Query **uitvoeren.**</span><span class="sxs-lookup"><span data-stu-id="9a88b-185">Refine your query by selecting the `+` or `-` buttons on the values that you want to include or exclude and then selecting **Run query**.</span></span>

![Afbeelding van geavanceerd zoekfilter](../../media/advanced-hunting-filter.png)

<span data-ttu-id="9a88b-187">Nadat u het filter hebt toegepast om de query te wijzigen en de query vervolgens uit te voeren, worden de resultaten dienovereenkomstig bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="9a88b-187">Once you apply the filter to modify the query and then run the query, the results are updated accordingly.</span></span>

## <a name="related-topics"></a><span data-ttu-id="9a88b-188">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="9a88b-188">Related topics</span></span>
- [<span data-ttu-id="9a88b-189">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="9a88b-189">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="9a88b-190">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="9a88b-190">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="9a88b-191">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="9a88b-191">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="9a88b-192">Opsporen op apparaten en in e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="9a88b-192">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="9a88b-193">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="9a88b-193">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="9a88b-194">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="9a88b-194">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="9a88b-195">Overzicht van aangepaste detectie</span><span class="sxs-lookup"><span data-stu-id="9a88b-195">Custom detections overview</span></span>](custom-detections-overview.md)
