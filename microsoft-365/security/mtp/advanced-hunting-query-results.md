---
title: Werken met geavanceerde zoekopdrachten voor de jacht in Microsoft Threat Protection
description: Maak optimaal resultaten van de queryresultaten die worden geretourneerd door de geavanceerde jacht in Microsoft Threat Protection
keywords: geavanceerde jacht, bedreigings jacht, Cyber Threat jacht, Microsoft Threat Protection, Microsoft 365, MTP, m365, Search, query, telemetrie, aangepaste detectie, schema, kusto, Microsoft 365, Microsoft Threat Protection, visualisatie, grafiek, filters en inzoomen
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 222d7f12c1a648800e4a359eb341354a5609c548
ms.sourcegitcommit: 51097b18d94da20aa727ebfbeb6ec84c263b25c3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/12/2020
ms.locfileid: "46649377"
---
# <a name="work-with-advanced-hunting-query-results"></a><span data-ttu-id="0d935-104">Werken met geavanceerde zoekresultaten van de jacht</span><span class="sxs-lookup"><span data-stu-id="0d935-104">Work with advanced hunting query results</span></span>

<span data-ttu-id="0d935-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="0d935-105">**Applies to:**</span></span>
- <span data-ttu-id="0d935-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="0d935-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="0d935-107">Hoewel u uw [Geavanceerde](advanced-hunting-overview.md) zoekopdrachten kunt maken om zeer nauwkeurige informatie te retourneren, kunt u ook werken met de queryresultaten om meer inzicht te krijgen en specifieke activiteiten en indicatoren te onderzoeken.</span><span class="sxs-lookup"><span data-stu-id="0d935-107">While you can construct your [advanced hunting](advanced-hunting-overview.md) queries to return very precise information, you can also work with the query results to gain further insight and investigate specific activities and indicators.</span></span> <span data-ttu-id="0d935-108">U kunt de volgende acties uitvoeren op uw queryresultaten:</span><span class="sxs-lookup"><span data-stu-id="0d935-108">You can take the following actions on your query results:</span></span>

- <span data-ttu-id="0d935-109">Resultaten als een tabel of grafiek weergeven</span><span class="sxs-lookup"><span data-stu-id="0d935-109">View results as a table or chart</span></span>
- <span data-ttu-id="0d935-110">Tabellen en grafieken exporteren</span><span class="sxs-lookup"><span data-stu-id="0d935-110">Export tables and charts</span></span>
- <span data-ttu-id="0d935-111">Inzoomen op gedetailleerde entiteits informatie</span><span class="sxs-lookup"><span data-stu-id="0d935-111">Drill down to detailed entity information</span></span>
- <span data-ttu-id="0d935-112">Uw zoekopdrachten direct toepassen op de resultaten of filters toepassen</span><span class="sxs-lookup"><span data-stu-id="0d935-112">Tweak your queries directly from the results or apply filters</span></span>

## <a name="view-query-results-as-a-table-or-chart"></a><span data-ttu-id="0d935-113">Queryresultaten als tabel of in een grafiek weergeven</span><span class="sxs-lookup"><span data-stu-id="0d935-113">View query results as a table or chart</span></span>
<span data-ttu-id="0d935-114">Standaard worden in geavanceerde jacht queryresultaten weergegeven als tabelgegevens.</span><span class="sxs-lookup"><span data-stu-id="0d935-114">By default, advanced hunting displays query results as tabular data.</span></span> <span data-ttu-id="0d935-115">U kunt ook dezelfde gegevens weergeven als een grafiek.</span><span class="sxs-lookup"><span data-stu-id="0d935-115">You can also display the same data as a chart.</span></span> <span data-ttu-id="0d935-116">Geavanceerde jacht ondersteuning voor de volgende weergaven:</span><span class="sxs-lookup"><span data-stu-id="0d935-116">Advanced hunting supports the following views:</span></span>

| <span data-ttu-id="0d935-117">Weergavetype</span><span class="sxs-lookup"><span data-stu-id="0d935-117">View type</span></span> | <span data-ttu-id="0d935-118">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="0d935-118">Description</span></span> |
| -- | -- |
| <span data-ttu-id="0d935-119">**Tabel**</span><span class="sxs-lookup"><span data-stu-id="0d935-119">**Table**</span></span> | <span data-ttu-id="0d935-120">De queryresultaten worden in tabelvorm weergegeven</span><span class="sxs-lookup"><span data-stu-id="0d935-120">Displays the query results in tabular format</span></span> |
| <span data-ttu-id="0d935-121">**Kolomdiagram**</span><span class="sxs-lookup"><span data-stu-id="0d935-121">**Column chart**</span></span> | <span data-ttu-id="0d935-122">Geeft een reeks unieke items weer op de x-as met verticale balken waarvan de numerieke waarden uit een ander veld aangeven</span><span class="sxs-lookup"><span data-stu-id="0d935-122">Renders a series of unique items on the x-axis as vertical bars whose heights represent numeric values from another field</span></span> |
| <span data-ttu-id="0d935-123">**Gestapeld kolomdiagram**</span><span class="sxs-lookup"><span data-stu-id="0d935-123">**Stacked column chart**</span></span> | <span data-ttu-id="0d935-124">Geeft een reeks unieke items op de x-as weer als gestapelde verticale balken waarvan de numerieke waarden in een of meer andere velden aangeven</span><span class="sxs-lookup"><span data-stu-id="0d935-124">Renders a series of unique items on the x-axis as stacked vertical bars whose heights represent numeric values from one or more other fields</span></span> |
| <span data-ttu-id="0d935-125">**Cirkeldiagram**</span><span class="sxs-lookup"><span data-stu-id="0d935-125">**Pie chart**</span></span> | <span data-ttu-id="0d935-126">Geeft een Pies weer en vertegenwoordigen unieke items.</span><span class="sxs-lookup"><span data-stu-id="0d935-126">Renders sectional pies representing unique items.</span></span> <span data-ttu-id="0d935-127">De grootte van elk cirkeldiagram bevat numerieke waarden uit een ander veld.</span><span class="sxs-lookup"><span data-stu-id="0d935-127">The size of each pie represents numeric values from another field.</span></span> |
| <span data-ttu-id="0d935-128">**Ringdiagram**</span><span class="sxs-lookup"><span data-stu-id="0d935-128">**Donut chart**</span></span> | <span data-ttu-id="0d935-129">Rendert sectietab van de secties die unieke items vertegenwoordigen.</span><span class="sxs-lookup"><span data-stu-id="0d935-129">Renders sectional arcs representing unique items.</span></span> <span data-ttu-id="0d935-130">Elke boog bevat numerieke waarden uit een ander veld.</span><span class="sxs-lookup"><span data-stu-id="0d935-130">The length of each arc represents numeric values from another field.</span></span> |
| <span data-ttu-id="0d935-131">**Lijndiagram**</span><span class="sxs-lookup"><span data-stu-id="0d935-131">**Line chart**</span></span> | <span data-ttu-id="0d935-132">De numerieke waarden voor een reeks unieke items tekenen en de geplotte waarden verbinden</span><span class="sxs-lookup"><span data-stu-id="0d935-132">Plots numeric values for a series of unique items and connects the plotted values</span></span> |
| <span data-ttu-id="0d935-133">**Spreidingsdiagram**</span><span class="sxs-lookup"><span data-stu-id="0d935-133">**Scatter chart**</span></span> | <span data-ttu-id="0d935-134">Numerieke waarden voor een reeks unieke items tekenen</span><span class="sxs-lookup"><span data-stu-id="0d935-134">Plots numeric values for a series of unique items</span></span> |
| <span data-ttu-id="0d935-135">**Vlakdiagram**</span><span class="sxs-lookup"><span data-stu-id="0d935-135">**Area chart**</span></span> | <span data-ttu-id="0d935-136">Hiermee tekent u numerieke waarden voor een reeks unieke items en vult u de secties onder de gevolgde waarden door</span><span class="sxs-lookup"><span data-stu-id="0d935-136">Plots numeric values for a series of unique items and fills the sections below the plotted values</span></span> |

### <a name="construct-queries-for-effective-charts"></a><span data-ttu-id="0d935-137">Query's opstellen voor effectieve grafieken</span><span class="sxs-lookup"><span data-stu-id="0d935-137">Construct queries for effective charts</span></span>
<span data-ttu-id="0d935-138">Bij het weergeven van grafieken worden in geavanceerde jacht automatisch de kolommen rente en de numerieke waarden aangegeven voor statistische functies.</span><span class="sxs-lookup"><span data-stu-id="0d935-138">When rendering charts, advanced hunting automatically identifies columns of interest and the numeric values to aggregate.</span></span> <span data-ttu-id="0d935-139">Als u zinvolle grafieken wilt weergeven, maakt u de query's om de specifieke waarden te retourneren die u wilt weergeven.</span><span class="sxs-lookup"><span data-stu-id="0d935-139">To get meaningful charts, construct your queries to return the specific values you want to see visualized.</span></span> <span data-ttu-id="0d935-140">Hier volgen enkele voorbeelden van query's en de gemaakte grafieken.</span><span class="sxs-lookup"><span data-stu-id="0d935-140">Here are some sample queries and the resulting charts.</span></span>

#### <a name="alerts-by-severity"></a><span data-ttu-id="0d935-141">Waarschuwingen per Ernst</span><span class="sxs-lookup"><span data-stu-id="0d935-141">Alerts by severity</span></span>
<span data-ttu-id="0d935-142">Gebruik de `summarize` operator om een numeriek aantal te verkrijgen voor de waarden die u in een grafiek wilt opnemen.</span><span class="sxs-lookup"><span data-stu-id="0d935-142">Use the `summarize` operator to obtain a numeric count of the values you want to chart.</span></span> <span data-ttu-id="0d935-143">Voor de onderstaande query wordt de `summarize` operator gebruikt om het aantal waarschuwingen per ernst te ontvangen.</span><span class="sxs-lookup"><span data-stu-id="0d935-143">The query below uses the `summarize` operator to get the number of alerts by severity.</span></span>

```kusto
AlertInfo
| summarize Total = count() by Severity
```
<span data-ttu-id="0d935-144">Bij het weergeven van de resultaten ziet u in een kolomdiagram elke waarde voor de ernst als een afzonderlijke kolom:</span><span class="sxs-lookup"><span data-stu-id="0d935-144">When rendering the results, a column chart displays each severity value as a separate column:</span></span>

<span data-ttu-id="0d935-145">![Afbeelding van geavanceerde zoekresultaten die worden weergegeven als kolomdiagram ](../../media/advanced-hunting-column-chart.jpg)
 *queryresultaten voor waarschuwingen per Ernst weergegeven als kolomdiagram*</span><span class="sxs-lookup"><span data-stu-id="0d935-145">![Image of advanced hunting query results displayed as a column chart](../../media/advanced-hunting-column-chart.jpg)
*Query results for alerts by severity displayed as a column chart*</span></span>

#### <a name="alert-severity-by-operating-system"></a><span data-ttu-id="0d935-146">Ernst van waarschuwingen via besturingssysteem</span><span class="sxs-lookup"><span data-stu-id="0d935-146">Alert severity by operating system</span></span>
<span data-ttu-id="0d935-147">U kunt ook de `summarize` operator gebruiken om resultaten voor de grafiekwaarden uit meerdere velden voor te bereiden.</span><span class="sxs-lookup"><span data-stu-id="0d935-147">You could also use the `summarize` operator to prepare results for charting values from multiple fields.</span></span> <span data-ttu-id="0d935-148">U kunt bijvoorbeeld inzicht krijgen in de beschikbaarheid van waarschuwings punten voor het besturingssysteem (OS).</span><span class="sxs-lookup"><span data-stu-id="0d935-148">For example, you might want to understand how alert severities are distributed across operating systems (OS).</span></span> 

<span data-ttu-id="0d935-149">In de onderstaande query wordt een `join` operator gebruikt om besturingssysteemgegevens uit de tabel op te halen `DeviceInfo` en wordt gebruikt `summarize` om waarden te tellen in zowel de `OSPlatform` kolommen als `Severity` :</span><span class="sxs-lookup"><span data-stu-id="0d935-149">The query below uses a `join` operator to pull in OS information from the `DeviceInfo` table, and then uses `summarize` to count values in both the `OSPlatform` and `Severity` columns:</span></span>

```kusto
AlertInfo
| join AlertEvidence on AlertId
| join DeviceInfo on DeviceId
| summarize Count = count() by OSPlatform, Severity 
```
<span data-ttu-id="0d935-150">Dit zijn de beste visuele resultaten met behulp van een gestapeld kolomdiagram:</span><span class="sxs-lookup"><span data-stu-id="0d935-150">These results are best visualized using a stacked column chart:</span></span>

<span data-ttu-id="0d935-151">![Afbeelding van geavanceerde zoekresultaten die worden weergegeven als een gestapeld diagram ](../../media/advanced-hunting-stacked-chart.jpg)
 *queryresultaten voor waarschuwingen per OS en ernst weergegeven als gestapelde grafiek*</span><span class="sxs-lookup"><span data-stu-id="0d935-151">![Image of advanced hunting query results displayed as a stacked chart](../../media/advanced-hunting-stacked-chart.jpg)
*Query results for alerts by OS and severity displayed as a stacked chart*</span></span>

#### <a name="phishing-emails-across-top-ten-sender-domains"></a><span data-ttu-id="0d935-152">Phishing-e-mails in de bovenste tien verzender domeinen</span><span class="sxs-lookup"><span data-stu-id="0d935-152">Phishing emails across top ten sender domains</span></span>
<span data-ttu-id="0d935-153">Als u wilt werken met een lijst met waarden die niet beperkt zijn, kunt u de `Top` operator gebruiken om alleen de waarden in een grafiek te plaatsen.</span><span class="sxs-lookup"><span data-stu-id="0d935-153">If you're dealing with a list of values that isn’t finite, you can use the `Top` operator to chart only the values with the most instances.</span></span> <span data-ttu-id="0d935-154">Als u bijvoorbeeld de meeste tien verzender domeinen met de meest verduidelijkende e-mail wilt ophalen, gebruikt u de onderstaande query:</span><span class="sxs-lookup"><span data-stu-id="0d935-154">For example, to get the top ten sender domains with the most phishing emails, use the query below:</span></span>

```kusto
EmailEvents
| where PhishFilterVerdict == "Phish"
| summarize Count = count() by SenderFromDomain
| top 10 by Count
```
<span data-ttu-id="0d935-155">In de weergave cirkeldiagram kunt u de verdeling effectief weergeven op de meest voorkomende domeinen:</span><span class="sxs-lookup"><span data-stu-id="0d935-155">Use the pie chart view to effectively show distribution across the top domains:</span></span>

<span data-ttu-id="0d935-156">![Afbeelding van geavanceerde zoekresultaten die worden weergegeven als een cirkeldiagram met een cirkeldiagram ](../../media/advanced-hunting-pie-chart.jpg)
 *waarin de distributie van malafide e-mailberichten in domeinen van de belangrijkste afzender wordt getoond*</span><span class="sxs-lookup"><span data-stu-id="0d935-156">![Image of advanced hunting query results displayed as a pie chart](../../media/advanced-hunting-pie-chart.jpg)
*Pie chart showing distribution of phishing emails across top sender domains*</span></span>

#### <a name="file-activities-over-time"></a><span data-ttu-id="0d935-157">Bestandsactiviteiten gedurende een bepaalde periode</span><span class="sxs-lookup"><span data-stu-id="0d935-157">File activities over time</span></span>
<span data-ttu-id="0d935-158">Met de `summarize` operator met de `bin()` functie, kunt u controleren op gebeurtenissen met een bepaalde indicator gedurende een bepaalde periode.</span><span class="sxs-lookup"><span data-stu-id="0d935-158">Using the `summarize` operator with the `bin()` function, you can check for events involving a particular indicator over time.</span></span> <span data-ttu-id="0d935-159">Met de query eronder worden de gebeurtenissen met het bestand `invoice.doc` bij 30 minuten geteld om uitschieters weer te geven in activiteiten met betrekking tot dat bestand:</span><span class="sxs-lookup"><span data-stu-id="0d935-159">The query below counts events involving the file `invoice.doc` at 30 minute intervals to show spikes in activity related to that file:</span></span>

```kusto
AppFileEvents
| union DeviceFileEvents
| where FileName == "invoice.doc"
| summarize FileCount = count() by bin(Timestamp, 30m)
```
<span data-ttu-id="0d935-160">In het lijndiagram onder duidelijk worden tijdsperioden gemarkeerd met meer activiteiten `invoice.doc` :</span><span class="sxs-lookup"><span data-stu-id="0d935-160">The line chart below clearly highlights time periods with more activity involving `invoice.doc`:</span></span> 

<span data-ttu-id="0d935-161">![Afbeelding van geavanceerde zoekresultaten van de zoekactie die worden weergegeven als lijndiagram ](../../media/advanced-hunting-line-chart.jpg)
 *met meerdere gebeurtenissen*</span><span class="sxs-lookup"><span data-stu-id="0d935-161">![Image of advanced hunting query results displayed as a line chart](../../media/advanced-hunting-line-chart.jpg)
*Line chart showing the number of events involving a file over time*</span></span>


## <a name="export-tables-and-charts"></a><span data-ttu-id="0d935-162">Tabellen en grafieken exporteren</span><span class="sxs-lookup"><span data-stu-id="0d935-162">Export tables and charts</span></span>
<span data-ttu-id="0d935-163">Na het uitvoeren van een query, selecteert u **exporteren** om de resultaten in het lokale bestand op te slaan.</span><span class="sxs-lookup"><span data-stu-id="0d935-163">After running a query, select **Export** to save the results to local file.</span></span> <span data-ttu-id="0d935-164">Met de gekozen weergave wordt bepaald hoe de resultaten worden geëxporteerd:</span><span class="sxs-lookup"><span data-stu-id="0d935-164">Your chosen view determines how the results are exported:</span></span>

- <span data-ttu-id="0d935-165">**Tabel weergave** : de queryresultaten worden in tabelvorm geëxporteerd als een Microsoft Excel-werkmap</span><span class="sxs-lookup"><span data-stu-id="0d935-165">**Table view** — the query results are exported in tabular form as a Microsoft Excel workbook</span></span>
- <span data-ttu-id="0d935-166">**Een grafiek** : de queryresultaten worden geëxporteerd als een JPEG-afbeelding van de weergegeven grafiek</span><span class="sxs-lookup"><span data-stu-id="0d935-166">**Any chart** — the query results are exported as a JPEG image of the rendered chart</span></span>

## <a name="drill-down-from-query-results"></a><span data-ttu-id="0d935-167">Inzoomen op queryresultaten</span><span class="sxs-lookup"><span data-stu-id="0d935-167">Drill down from query results</span></span>
<span data-ttu-id="0d935-168">Als u in uw queryresultaten snel een record wilt controleren, selecteert u de bijbehorende rij om het deelvenster **record controleren** te openen.</span><span class="sxs-lookup"><span data-stu-id="0d935-168">To quickly inspect a record in your query results, select the corresponding row to open the **Inspect record** panel.</span></span> <span data-ttu-id="0d935-169">Het deelvenster bevat de volgende informatie op basis van de geselecteerde record:</span><span class="sxs-lookup"><span data-stu-id="0d935-169">The panel provides the following information based on the selected record:</span></span>

- <span data-ttu-id="0d935-170">**Activa** : een overzichtsweergave van de belangrijkste activa (postvakken, apparaten en gebruikers) die zijn gevonden in de record, verrijkd met de beschikbare informatie, zoals risico en belichtings niveau</span><span class="sxs-lookup"><span data-stu-id="0d935-170">**Assets** — summarized view of the main assets (mailboxes, devices, and users) found in the record, enriched with available information, such as risk and exposure levels</span></span>
- <span data-ttu-id="0d935-171">**Processtructuur** : gegenereerd voor records met procesinformatie en verrijking met behulp van beschikbare contextuele informatie. in het algemeen kunnen query's die meer kolommen retourneren, resulteren in uitgebreide processen.</span><span class="sxs-lookup"><span data-stu-id="0d935-171">**Process tree** — generated for records with process information and enriched using available contextual information; in general, queries that return more columns can result in richer process trees.</span></span>
- <span data-ttu-id="0d935-172">**Alle details** : alle waarden uit de kolommen in de record</span><span class="sxs-lookup"><span data-stu-id="0d935-172">**All details** — all the values from the columns in the record</span></span>  

![Afbeelding van geselecteerde record met deelvenster voor inspectie van de record](../../media/mtp-ah/inspect-record.png)

<span data-ttu-id="0d935-174">Als u meer informatie wilt bekijken over een bepaalde entiteit in uw queryresultaten, zoals een computer, bestand, gebruiker, IP-adres of URL, selecteert u de entiteits-id om een gedetailleerde profielpagina voor die entiteit te openen.</span><span class="sxs-lookup"><span data-stu-id="0d935-174">To view more information about a specific entity in your query results, such as a machine, file, user, IP address, or URL, select the entity identifier to open a detailed profile page for that entity.</span></span>

## <a name="tweak-your-queries-from-the-results"></a><span data-ttu-id="0d935-175">De query's van de zoekresultaten verfijnen</span><span class="sxs-lookup"><span data-stu-id="0d935-175">Tweak your queries from the results</span></span>
<span data-ttu-id="0d935-176">Klik met de rechtermuisknop op een waarde in de resultatenset om uw query snel te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="0d935-176">Right-click a value in the result set to quickly enhance your query.</span></span> <span data-ttu-id="0d935-177">Met de opties kunt u:</span><span class="sxs-lookup"><span data-stu-id="0d935-177">You can use the options to:</span></span>

- <span data-ttu-id="0d935-178">Zoek expliciet naar de geselecteerde waarde ( `==` ).</span><span class="sxs-lookup"><span data-stu-id="0d935-178">Explicitly look for the selected value (`==`)</span></span>
- <span data-ttu-id="0d935-179">De geselecteerde waarde van de query uitsluiten `!=`</span><span class="sxs-lookup"><span data-stu-id="0d935-179">Exclude the selected value from the query (`!=`)</span></span>
- <span data-ttu-id="0d935-180">Meer geavanceerde operatoren voor het toevoegen van een waarde aan uw query, zoals `contains` , `starts with` en `ends with`</span><span class="sxs-lookup"><span data-stu-id="0d935-180">Get more advanced operators for adding the value to your query, such as `contains`, `starts with` and `ends with`</span></span> 

![Afbeelding van geavanceerde resultatenset van jacht](../../media/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a><span data-ttu-id="0d935-182">De queryresultaten filteren</span><span class="sxs-lookup"><span data-stu-id="0d935-182">Filter the query results</span></span>
<span data-ttu-id="0d935-183">De filters rechts geven een overzicht van de resultatenset.</span><span class="sxs-lookup"><span data-stu-id="0d935-183">The filters displayed to the right provide a summary of the result set.</span></span> <span data-ttu-id="0d935-184">Elke kolom heeft een eigen sectie met daarin de unieke waarden die zijn gevonden voor de kolom en het aantal exemplaren.</span><span class="sxs-lookup"><span data-stu-id="0d935-184">Each column has its own section that lists the distinct values found for that column and the number of instances.</span></span>

<span data-ttu-id="0d935-185">Verfijn uw zoekopdracht door de `+` knoppen of de knoppen te selecteren `-` voor de waarden die u wilt opnemen of uitsluiten en vervolgens **query uitvoeren**te selecteren.</span><span class="sxs-lookup"><span data-stu-id="0d935-185">Refine your query by selecting the `+` or `-` buttons on the values that you want to include or exclude and then selecting **Run query**.</span></span>

![Afbeelding van een geavanceerd jacht filter](../../media/advanced-hunting-filter.png)

<span data-ttu-id="0d935-187">Wanneer u het filter hebt toegepast om de query te wijzigen en vervolgens de query uit te voeren, worden de resultaten dienovereenkomstig bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="0d935-187">Once you apply the filter to modify the query and then run the query, the results are updated accordingly.</span></span>

## <a name="related-topics"></a><span data-ttu-id="0d935-188">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="0d935-188">Related topics</span></span>
- [<span data-ttu-id="0d935-189">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="0d935-189">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="0d935-190">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="0d935-190">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="0d935-191">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="0d935-191">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="0d935-192">Jacht op apparaten, e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="0d935-192">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="0d935-193">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="0d935-193">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="0d935-194">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="0d935-194">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="0d935-195">Overzicht van aangepaste detectie</span><span class="sxs-lookup"><span data-stu-id="0d935-195">Custom detections overview</span></span>](custom-detections-overview.md)
