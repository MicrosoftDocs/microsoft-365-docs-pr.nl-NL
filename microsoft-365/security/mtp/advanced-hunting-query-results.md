---
title: Werken met geavanceerde resultaten van jachtquery's in Microsoft Threat Protection
description: Haal het meeste uit de queryresultaten die zijn geretourneerd door geavanceerde jacht in Microsoft Threat Protection
keywords: geavanceerde jacht, dreigingjacht, cyberdreigingsjacht, bescherming tegen microsoft-bedreigingen, microsoft 365, mtp, m365, zoeken, query, telemetrie, aangepaste detecties, schema, kusto, microsoft 365, Microsoft Threat Protection, visualisatie, grafiek, filters, inzoomen
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
ms.openlocfilehash: f9838908ca0dbfb498601c3509b920b064a2eb22
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929149"
---
# <a name="work-with-advanced-hunting-query-results"></a><span data-ttu-id="993fa-104">Werken met geavanceerde resultaten van jachtquery's</span><span class="sxs-lookup"><span data-stu-id="993fa-104">Work with advanced hunting query results</span></span>

<span data-ttu-id="993fa-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="993fa-105">**Applies to:**</span></span>
- <span data-ttu-id="993fa-106">Microsoft-bedreigingsbeveiliging</span><span class="sxs-lookup"><span data-stu-id="993fa-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="993fa-107">Hoewel u uw [geavanceerde jachtquery's](advanced-hunting-overview.md) samenstellen om zeer nauwkeurige informatie terug te geven, u ook met de queryresultaten werken om meer inzicht te krijgen en specifieke activiteiten en indicatoren te onderzoeken.</span><span class="sxs-lookup"><span data-stu-id="993fa-107">While you can construct your [advanced hunting](advanced-hunting-overview.md) queries to return very precise information, you can also work with the query results to gain further insight and investigate specific activities and indicators.</span></span> <span data-ttu-id="993fa-108">U de volgende acties uitvoeren op uw queryresultaten:</span><span class="sxs-lookup"><span data-stu-id="993fa-108">You can take the following actions on your query results:</span></span>

- <span data-ttu-id="993fa-109">Resultaten weergeven als een tabel of grafiek</span><span class="sxs-lookup"><span data-stu-id="993fa-109">View results as a table or chart</span></span>
- <span data-ttu-id="993fa-110">Tabellen en grafieken exporteren</span><span class="sxs-lookup"><span data-stu-id="993fa-110">Export tables and charts</span></span>
- <span data-ttu-id="993fa-111">Inzoomen op gedetailleerde entiteitsinformatie</span><span class="sxs-lookup"><span data-stu-id="993fa-111">Drill down to detailed entity information</span></span>
- <span data-ttu-id="993fa-112">Uw query's rechtstreeks vanuit de resultaten aanpassen of filters toepassen</span><span class="sxs-lookup"><span data-stu-id="993fa-112">Tweak your queries directly from the results or apply filters</span></span>

## <a name="view-query-results-as-a-table-or-chart"></a><span data-ttu-id="993fa-113">Queryresultaten weergeven als een tabel of grafiek</span><span class="sxs-lookup"><span data-stu-id="993fa-113">View query results as a table or chart</span></span>
<span data-ttu-id="993fa-114">Geavanceerde jacht geeft standaard queryresultaten weer als tabelgegevens.</span><span class="sxs-lookup"><span data-stu-id="993fa-114">By default, advanced hunting displays query results as tabular data.</span></span> <span data-ttu-id="993fa-115">U ook dezelfde gegevens weergeven als een grafiek.</span><span class="sxs-lookup"><span data-stu-id="993fa-115">You can also display the same data as a chart.</span></span> <span data-ttu-id="993fa-116">Geavanceerde jacht ondersteunt de volgende standpunten:</span><span class="sxs-lookup"><span data-stu-id="993fa-116">Advanced hunting supports the following views:</span></span>

| <span data-ttu-id="993fa-117">Weergavetype</span><span class="sxs-lookup"><span data-stu-id="993fa-117">View type</span></span> | <span data-ttu-id="993fa-118">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="993fa-118">Description</span></span> |
| -- | -- |
| <span data-ttu-id="993fa-119">**Tabel**</span><span class="sxs-lookup"><span data-stu-id="993fa-119">**Table**</span></span> | <span data-ttu-id="993fa-120">Geeft de queryresultaten in tabelindeling weer</span><span class="sxs-lookup"><span data-stu-id="993fa-120">Displays the query results in tabular format</span></span> |
| <span data-ttu-id="993fa-121">**Kolomdiagram**</span><span class="sxs-lookup"><span data-stu-id="993fa-121">**Column chart**</span></span> | <span data-ttu-id="993fa-122">Hiermee wordt een reeks unieke items op de x-as weergegeven als verticale balken waarvan de hoogte smeudatumewaarden uit een ander veld vertegenwoordigen</span><span class="sxs-lookup"><span data-stu-id="993fa-122">Renders a series of unique items on the x-axis as vertical bars whose heights represent numeric values from another field</span></span> |
| <span data-ttu-id="993fa-123">**Gestapeld kolomdiagram**</span><span class="sxs-lookup"><span data-stu-id="993fa-123">**Stacked column chart**</span></span> | <span data-ttu-id="993fa-124">Hiermee worden een reeks unieke items op de x-as weergegeven als gestapelde verticale balken waarvan de hoogtes numerieke waarden van een of meer andere velden vertegenwoordigen</span><span class="sxs-lookup"><span data-stu-id="993fa-124">Renders a series of unique items on the x-axis as stacked vertical bars whose heights represent numeric values from one or more other fields</span></span> |
| <span data-ttu-id="993fa-125">**Cirkeldiagram**</span><span class="sxs-lookup"><span data-stu-id="993fa-125">**Pie chart**</span></span> | <span data-ttu-id="993fa-126">Renders sectionele taarten die unieke items vertegenwoordigen.</span><span class="sxs-lookup"><span data-stu-id="993fa-126">Renders sectional pies representing unique items.</span></span> <span data-ttu-id="993fa-127">De grootte van elke cirkel vertegenwoordigt numerieke waarden uit een ander veld.</span><span class="sxs-lookup"><span data-stu-id="993fa-127">The size of each pie represents numeric values from another field.</span></span> |
| <span data-ttu-id="993fa-128">**Donutdiagram**</span><span class="sxs-lookup"><span data-stu-id="993fa-128">**Donut chart**</span></span> | <span data-ttu-id="993fa-129">Hiermee worden sectionele bogen weergegeven die unieke items vertegenwoordigen.</span><span class="sxs-lookup"><span data-stu-id="993fa-129">Renders sectional arcs representing unique items.</span></span> <span data-ttu-id="993fa-130">De lengte van elke boog vertegenwoordigt numerieke waarden uit een ander veld.</span><span class="sxs-lookup"><span data-stu-id="993fa-130">The length of each arc represents numeric values from another field.</span></span> |
| <span data-ttu-id="993fa-131">**Lijndiagram**</span><span class="sxs-lookup"><span data-stu-id="993fa-131">**Line chart**</span></span> | <span data-ttu-id="993fa-132">Hiermee worden numerieke waarden voor een reeks unieke items inkaart en de uitgezette waarden met elkaar verbonden</span><span class="sxs-lookup"><span data-stu-id="993fa-132">Plots numeric values for a series of unique items and connects the plotted values</span></span> |
| <span data-ttu-id="993fa-133">**Spreidingsdiagram**</span><span class="sxs-lookup"><span data-stu-id="993fa-133">**Scatter chart**</span></span> | <span data-ttu-id="993fa-134">Numerieke waarden voor een reeks unieke items in- en uitplannen</span><span class="sxs-lookup"><span data-stu-id="993fa-134">Plots numeric values for a series of unique items</span></span> |
| <span data-ttu-id="993fa-135">**Gebiedsdiagram**</span><span class="sxs-lookup"><span data-stu-id="993fa-135">**Area chart**</span></span> | <span data-ttu-id="993fa-136">Hiermee worden numerieke waarden voor een reeks unieke items inkaart en worden de secties onder de uitgezette waarden gevuld</span><span class="sxs-lookup"><span data-stu-id="993fa-136">Plots numeric values for a series of unique items and fills the sections below the plotted values</span></span> |

### <a name="construct-queries-for-effective-charts"></a><span data-ttu-id="993fa-137">Query's maken voor effectieve grafieken</span><span class="sxs-lookup"><span data-stu-id="993fa-137">Construct queries for effective charts</span></span>
<span data-ttu-id="993fa-138">Bij het renderen van grafieken identificeert geavanceerde jacht automatisch kolommen van belang en de numerieke waarden die u wilt samenvoegen.</span><span class="sxs-lookup"><span data-stu-id="993fa-138">When rendering charts, advanced hunting automatically identifies columns of interest and the numeric values to aggregate.</span></span> <span data-ttu-id="993fa-139">Als u zinvolle grafieken wilt maken, maakt u uw query's om de specifieke waarden die u wilt zien, gevisualiseerd weer te geven.</span><span class="sxs-lookup"><span data-stu-id="993fa-139">To get meaningful charts, construct your queries to return the specific values you want to see visualized.</span></span> <span data-ttu-id="993fa-140">Hier volgen enkele voorbeeldquery's en de resulterende grafieken.</span><span class="sxs-lookup"><span data-stu-id="993fa-140">Here are some sample queries and the resulting charts.</span></span>

#### <a name="alerts-by-severity"></a><span data-ttu-id="993fa-141">Waarschuwingen op ernst</span><span class="sxs-lookup"><span data-stu-id="993fa-141">Alerts by severity</span></span>
<span data-ttu-id="993fa-142">Gebruik `summarize` de operator om een numeriek aantal te verkrijgen van de waarden die u wilt in kaart brengen.</span><span class="sxs-lookup"><span data-stu-id="993fa-142">Use the `summarize` operator to obtain a numeric count of the values you want to chart.</span></span> <span data-ttu-id="993fa-143">De onderstaande `summarize` query gebruikt de operator om het aantal waarschuwingen per ernst te krijgen.</span><span class="sxs-lookup"><span data-stu-id="993fa-143">The query below uses the `summarize` operator to get the number of alerts by severity.</span></span>

```kusto
AlertInfo
| summarize Total = count() by Severity
```
<span data-ttu-id="993fa-144">Bij het renderen van de resultaten geeft een kolomdiagram elke ernstwaarde weer als een afzonderlijke kolom:</span><span class="sxs-lookup"><span data-stu-id="993fa-144">When rendering the results, a column chart displays each severity value as a separate column:</span></span>

<span data-ttu-id="993fa-145">![Afbeelding van geavanceerde resultaten van de](../../media/advanced-hunting-column-chart.jpg)
jachtquery die worden weergegeven als een kolomdiagram*Queryresultaten voor waarschuwingen op ernst die worden weergegeven als een kolomdiagram*</span><span class="sxs-lookup"><span data-stu-id="993fa-145">![Image of advanced hunting query results displayed as a column chart](../../media/advanced-hunting-column-chart.jpg)
*Query results for alerts by severity displayed as a column chart*</span></span>

#### <a name="alert-severity-by-operating-system"></a><span data-ttu-id="993fa-146">Ernst van de waarschuwing per besturingssysteem</span><span class="sxs-lookup"><span data-stu-id="993fa-146">Alert severity by operating system</span></span>
<span data-ttu-id="993fa-147">U de `summarize` operator ook gebruiken om resultaten voor te bereiden op het in kaart brengen van waarden uit meerdere velden.</span><span class="sxs-lookup"><span data-stu-id="993fa-147">You could also use the `summarize` operator to prepare results for charting values from multiple fields.</span></span> <span data-ttu-id="993fa-148">U wilt bijvoorbeeld begrijpen hoe waarschuwingsernst over besturingssystemen (os) wordt verdeeld.</span><span class="sxs-lookup"><span data-stu-id="993fa-148">For example, you might want to understand how alert severities are distributed across operating systems (OS).</span></span> 

<span data-ttu-id="993fa-149">De onderstaande `join` query gebruikt een operator `DeviceInfo` om OS-informatie `summarize` uit de tabel `OSPlatform` `Severity` op te halen en vervolgens te gebruiken om waarden in zowel de kolommen als de kolommen te tellen:</span><span class="sxs-lookup"><span data-stu-id="993fa-149">The query below uses a `join` operator to pull in OS information from the `DeviceInfo` table, and then uses `summarize` to count values in both the `OSPlatform` and `Severity` columns:</span></span>

```kusto
AlertInfo
| join AlertEvidence on AlertId
| join DeviceInfo on DeviceId
| summarize Count = count() by OSPlatform, Severity 
```
<span data-ttu-id="993fa-150">Deze resultaten kunnen het beste worden gevisualiseerd met behulp van een gestapeld kolomdiagram:</span><span class="sxs-lookup"><span data-stu-id="993fa-150">These results are best visualized using a stacked column chart:</span></span>

<span data-ttu-id="993fa-151">![Afbeelding van geavanceerde resultaten van de jachtquery die worden weergegeven als een gestapeld grafiek](../../media/advanced-hunting-stacked-chart.jpg)
*Queryresultaten voor waarschuwingen per besturingssysteem en ernst die worden weergegeven als een gestapeld diagram*</span><span class="sxs-lookup"><span data-stu-id="993fa-151">![Image of advanced hunting query results displayed as a stacked chart](../../media/advanced-hunting-stacked-chart.jpg)
*Query results for alerts by OS and severity displayed as a stacked chart*</span></span>

#### <a name="phishing-emails-across-top-ten-sender-domains"></a><span data-ttu-id="993fa-152">Phishing-e-mails in top tien afzenderdomeinen</span><span class="sxs-lookup"><span data-stu-id="993fa-152">Phishing emails across top ten sender domains</span></span>
<span data-ttu-id="993fa-153">Als u te maken hebt met een lijst met waarden `Top` die niet eindig zijn, u de operator gebruiken om alleen de waarden met de meeste instanties in kaart te brengen.</span><span class="sxs-lookup"><span data-stu-id="993fa-153">If you're dealing with a list of values that isn’t finite, you can use the `Top` operator to chart only the values with the most instances.</span></span> <span data-ttu-id="993fa-154">Bijvoorbeeld, om de top tien afzender domeinen met de meeste phishing e-mails te krijgen, gebruik maken van de onderstaande query:</span><span class="sxs-lookup"><span data-stu-id="993fa-154">For example, to get the top ten sender domains with the most phishing emails, use the query below:</span></span>

```kusto
EmailEvents
| where PhishFilterVerdict == "Phish"
| summarize Count = count() by SenderFromDomain
| top 10 by Count
```
<span data-ttu-id="993fa-155">Gebruik de grafiekweergave om de distributie over de topdomeinen effectief weer te geven:</span><span class="sxs-lookup"><span data-stu-id="993fa-155">Use the pie chart view to effectively show distribution across the top domains:</span></span>

<span data-ttu-id="993fa-156">![Afbeelding van geavanceerde resultaten van jachtquery's die worden weergegeven als een cirkeldiagram](../../media/advanced-hunting-pie-chart.jpg)
*Cirkeldiagram met de distributie van phishing-e-mails over topdomeinen van afzenders*</span><span class="sxs-lookup"><span data-stu-id="993fa-156">![Image of advanced hunting query results displayed as a pie chart](../../media/advanced-hunting-pie-chart.jpg)
*Pie chart showing distribution of phishing emails across top sender domains*</span></span>

#### <a name="file-activities-over-time"></a><span data-ttu-id="993fa-157">Bestandsactiviteiten in de loop van de tijd</span><span class="sxs-lookup"><span data-stu-id="993fa-157">File activities over time</span></span>
<span data-ttu-id="993fa-158">Met `summarize` behulp van `bin()` de operator met de functie, u controleren op gebeurtenissen waarbij een bepaalde indicator in de tijd.</span><span class="sxs-lookup"><span data-stu-id="993fa-158">Using the `summarize` operator with the `bin()` function, you can check for events involving a particular indicator over time.</span></span> <span data-ttu-id="993fa-159">De onderstaande query telt `invoice.doc` gebeurtenissen met het bestand met intervallen van 30 minuten om pieken in activiteit met betrekking tot dat bestand weer te geven:</span><span class="sxs-lookup"><span data-stu-id="993fa-159">The query below counts events involving the file `invoice.doc` at 30 minute intervals to show spikes in activity related to that file:</span></span>

```kusto
AppFileEvents
| union DeviceFileEvents
| where FileName == "invoice.doc"
| summarize FileCount = count() by bin(Timestamp, 30m)
```
<span data-ttu-id="993fa-160">In het onderstaande lijndiagram worden duidelijk `invoice.doc`perioden aangegeven met meer activiteit:</span><span class="sxs-lookup"><span data-stu-id="993fa-160">The line chart below clearly highlights time periods with more activity involving `invoice.doc`:</span></span> 

<span data-ttu-id="993fa-161">![Afbeelding van geavanceerde resultaten van de](../../media/advanced-hunting-line-chart.jpg)
jachtquery die worden weergegeven als een lijndiagram*Lijndiagram met het aantal gebeurtenissen met betrekking tot een bestand in de loop van de tijd*</span><span class="sxs-lookup"><span data-stu-id="993fa-161">![Image of advanced hunting query results displayed as a line chart](../../media/advanced-hunting-line-chart.jpg)
*Line chart showing the number of events involving a file over time*</span></span>


## <a name="export-tables-and-charts"></a><span data-ttu-id="993fa-162">Tabellen en grafieken exporteren</span><span class="sxs-lookup"><span data-stu-id="993fa-162">Export tables and charts</span></span>
<span data-ttu-id="993fa-163">Nadat u een query hebt uitgevoerd, selecteert u **Exporteren** om de resultaten op te slaan in lokaal bestand.</span><span class="sxs-lookup"><span data-stu-id="993fa-163">After running a query, select **Export** to save the results to local file.</span></span> <span data-ttu-id="993fa-164">De door u gekozen weergave bepaalt hoe de resultaten worden geëxporteerd:</span><span class="sxs-lookup"><span data-stu-id="993fa-164">Your chosen view determines how the results are exported:</span></span>

- <span data-ttu-id="993fa-165">**Tabelweergave** : de queryresultaten worden in tabelvorm geëxporteerd als een Microsoft Excel-werkmap</span><span class="sxs-lookup"><span data-stu-id="993fa-165">**Table view** — the query results are exported in tabular form as a Microsoft Excel workbook</span></span>
- <span data-ttu-id="993fa-166">**Elke grafiek** : de queryresultaten worden geëxporteerd als een JPEG-afbeelding van het gerenderde grafiek</span><span class="sxs-lookup"><span data-stu-id="993fa-166">**Any chart** — the query results are exported as a JPEG image of the rendered chart</span></span>

## <a name="drill-down-from-query-results"></a><span data-ttu-id="993fa-167">Inzoomen op queryresultaten</span><span class="sxs-lookup"><span data-stu-id="993fa-167">Drill down from query results</span></span>
<span data-ttu-id="993fa-168">Als u meer informatie wilt weergeven over entiteiten, zoals machines, bestanden, gebruikers, IP-adressen en URL's, klikt u in uw queryresultaten op de entiteits-id.</span><span class="sxs-lookup"><span data-stu-id="993fa-168">To view more information about entities, such as machines, files, users, IP addresses, and URLs, in your query results, simply click the entity identifier.</span></span> <span data-ttu-id="993fa-169">Hiermee wordt een gedetailleerde profielpagina geopend voor de geselecteerde entiteit in Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="993fa-169">This opens a detailed profile page for the selected entity in Microsoft Defender Security Center.</span></span>

## <a name="tweak-your-queries-from-the-results"></a><span data-ttu-id="993fa-170">Uw query's aanpassen aan de resultaten</span><span class="sxs-lookup"><span data-stu-id="993fa-170">Tweak your queries from the results</span></span>
<span data-ttu-id="993fa-171">Klik met de rechtermuisknop op een waarde in de resultatenset om uw query snel te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="993fa-171">Right-click a value in the result set to quickly enhance your query.</span></span> <span data-ttu-id="993fa-172">U de opties gebruiken om:</span><span class="sxs-lookup"><span data-stu-id="993fa-172">You can use the options to:</span></span>

- <span data-ttu-id="993fa-173">Expliciet zoeken naar de`==`geselecteerde waarde ( )</span><span class="sxs-lookup"><span data-stu-id="993fa-173">Explicitly look for the selected value (`==`)</span></span>
- <span data-ttu-id="993fa-174">De geselecteerde waarde uitsluiten`!=`van de query ( )</span><span class="sxs-lookup"><span data-stu-id="993fa-174">Exclude the selected value from the query (`!=`)</span></span>
- <span data-ttu-id="993fa-175">Meer geavanceerde operators voor het toevoegen van `contains`de `starts with` waarde aan uw query, zoals , en`ends with`</span><span class="sxs-lookup"><span data-stu-id="993fa-175">Get more advanced operators for adding the value to your query, such as `contains`, `starts with` and `ends with`</span></span> 

![Beeld van geavanceerde reeks van het jachtresultaat](../../media/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a><span data-ttu-id="993fa-177">De queryresultaten filteren</span><span class="sxs-lookup"><span data-stu-id="993fa-177">Filter the query results</span></span>
<span data-ttu-id="993fa-178">De filters die rechts worden weergegeven, geven een overzicht van de resultatenset.</span><span class="sxs-lookup"><span data-stu-id="993fa-178">The filters displayed to the right provide a summary of the result set.</span></span> <span data-ttu-id="993fa-179">Elke kolom heeft een eigen sectie met de verschillende waarden die voor die kolom zijn gevonden en het aantal exemplaren.</span><span class="sxs-lookup"><span data-stu-id="993fa-179">Each column has its own section that lists the distinct values found for that column and the number of instances.</span></span>

<span data-ttu-id="993fa-180">Verfijn uw query `+` `-` door de or-knoppen te selecteren op de waarden die u wilt opnemen of uit te sluiten en selecteer query **uitvoeren**.</span><span class="sxs-lookup"><span data-stu-id="993fa-180">Refine your query by selecting the `+` or `-` buttons on the values that you want to include or exclude and then selecting **Run query**.</span></span>

![Beeld van geavanceerd jachtfilter](../../media/advanced-hunting-filter.png)

<span data-ttu-id="993fa-182">Zodra u het filter toepast om de query te wijzigen en de query vervolgens uit te voeren, worden de resultaten dienovereenkomstig bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="993fa-182">Once you apply the filter to modify the query and then run the query, the results are updated accordingly.</span></span>

## <a name="related-topics"></a><span data-ttu-id="993fa-183">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="993fa-183">Related topics</span></span>
- [<span data-ttu-id="993fa-184">Geavanceerd jachtoverzicht</span><span class="sxs-lookup"><span data-stu-id="993fa-184">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="993fa-185">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="993fa-185">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="993fa-186">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="993fa-186">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="993fa-187">Zoek naar bedreigingen op verschillende apparaten en e-mails</span><span class="sxs-lookup"><span data-stu-id="993fa-187">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="993fa-188">Het schema begrijpen</span><span class="sxs-lookup"><span data-stu-id="993fa-188">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="993fa-189">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="993fa-189">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="993fa-190">Overzicht van aangepaste detecties</span><span class="sxs-lookup"><span data-stu-id="993fa-190">Custom detections overview</span></span>](custom-detections-overview.md)
