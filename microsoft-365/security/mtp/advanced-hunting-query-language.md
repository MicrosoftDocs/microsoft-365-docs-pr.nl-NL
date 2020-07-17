---
title: Leer de geavanceerde jachtquerytaal in Microsoft Threat Protection
description: Maak uw eerste dreiging jacht query en meer informatie over gemeenschappelijke exploitanten en andere aspecten van de geavanceerde jacht query taal
keywords: geavanceerde jacht, bedreiging jacht, cyber bedreiging jacht, Microsoft threat protection, Microsoft 365, mtp, m365, zoeken, query, taal, leren, eerste query, telemetrie, gebeurtenissen, telemetrie, aangepaste detecties, schema, kusto, operators, gegevenstypen, powershell download, query voorbeeld
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
ms.openlocfilehash: 26b376fe3e804a3ebaa478e484807bea4c33d38b
ms.sourcegitcommit: 7c1b34205746ff0690ffc774a74bdfd434256cf5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/07/2020
ms.locfileid: "45049691"
---
# <a name="learn-the-advanced-hunting-query-language"></a><span data-ttu-id="1ac00-104">Leer de geavanceerde jachtquerytaal</span><span class="sxs-lookup"><span data-stu-id="1ac00-104">Learn the advanced hunting query language</span></span>

<span data-ttu-id="1ac00-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="1ac00-105">**Applies to:**</span></span>
- <span data-ttu-id="1ac00-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="1ac00-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="1ac00-107">Geavanceerde jacht is gebaseerd op de [Kusto query taal.](https://docs.microsoft.com/azure/kusto/query/)</span><span class="sxs-lookup"><span data-stu-id="1ac00-107">Advanced hunting is based on the [Kusto query language](https://docs.microsoft.com/azure/kusto/query/).</span></span> <span data-ttu-id="1ac00-108">U Kusto-syntaxis en operatoren gebruiken om query's te construeren die informatie in het [schema](advanced-hunting-schema-tables.md) vinden dat specifiek is gestructureerd voor geavanceerde jacht.</span><span class="sxs-lookup"><span data-stu-id="1ac00-108">You can use Kusto syntax and operators to construct queries that locate information in the [schema](advanced-hunting-schema-tables.md) specifically structured for advanced hunting.</span></span> <span data-ttu-id="1ac00-109">Voer uw eerste query uit om deze concepten beter te begrijpen.</span><span class="sxs-lookup"><span data-stu-id="1ac00-109">To understand these concepts better, run your first query.</span></span>

## <a name="try-your-first-query"></a><span data-ttu-id="1ac00-110">Probeer uw eerste query</span><span class="sxs-lookup"><span data-stu-id="1ac00-110">Try your first query</span></span>

<span data-ttu-id="1ac00-111">Ga in het Microsoft 365-beveiligingscentrum naar **Hunting** om uw eerste query uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="1ac00-111">In Microsoft 365 security center, go to **Hunting** to run your first query.</span></span> <span data-ttu-id="1ac00-112">Gebruik het volgende voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="1ac00-112">Use the following example:</span></span>

```kusto
// Finds PowerShell execution events that could involve a download
union DeviceProcessEvents, DeviceNetworkEvents
| where Timestamp > ago(7d)
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
// Suspicious commands
| where ProcessCommandLine has_any("WebClient",
 "DownloadFile",
 "DownloadData",
 "DownloadString",
"WebRequest",
"Shellcode",
"http",
"https")
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

<span data-ttu-id="1ac00-113">Zo zal het eruit zien in de geavanceerde jacht.</span><span class="sxs-lookup"><span data-stu-id="1ac00-113">This is how it will look like in advanced hunting.</span></span>

![Afbeelding van microsoft Threat Protection geavanceerde jachtquery](../../media/advanced-hunting-query-example-2.png)

### <a name="describe-the-query-and-specify-the-tables-to-search"></a><span data-ttu-id="1ac00-115">De query beschrijven en de tabellen opgeven die u moet zoeken</span><span class="sxs-lookup"><span data-stu-id="1ac00-115">Describe the query and specify the tables to search</span></span>
<span data-ttu-id="1ac00-116">Een korte opmerking is toegevoegd aan het begin van de query om te beschrijven waar het voor is.</span><span class="sxs-lookup"><span data-stu-id="1ac00-116">A short comment has been added to the beginning of the query to describe what it is for.</span></span> <span data-ttu-id="1ac00-117">Dit helpt als u later besluit de query op te slaan en te delen met anderen in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="1ac00-117">This helps if you later decide to save the query and share it with others in your organization.</span></span> 

```kusto
// Finds PowerShell execution events that could involve a download
```

<span data-ttu-id="1ac00-118">De query zelf begint meestal met een tabelnaam, gevolgd door een reeks elementen die door een pijp zijn gestart ( `|` ).</span><span class="sxs-lookup"><span data-stu-id="1ac00-118">The query itself will typically start with a table name followed by a series of elements started by a pipe (`|`).</span></span> <span data-ttu-id="1ac00-119">In dit voorbeeld beginnen we met het maken van een unie van twee tabellen `DeviceProcessEvents` en voegen we zo nodig `DeviceNetworkEvents` leidingelementen toe.</span><span class="sxs-lookup"><span data-stu-id="1ac00-119">In this example, we start by creating a union of two tables,  `DeviceProcessEvents` and `DeviceNetworkEvents`, and add piped elements as needed.</span></span>

```kusto
union DeviceProcessEvents, DeviceNetworkEvents
```
### <a name="set-the-time-range"></a><span data-ttu-id="1ac00-120">Het tijdsbereik instellen</span><span class="sxs-lookup"><span data-stu-id="1ac00-120">Set the time range</span></span>
<span data-ttu-id="1ac00-121">Het eerste gepipeteerde element is een tijdfilter scoped naar de vorige zeven dagen.</span><span class="sxs-lookup"><span data-stu-id="1ac00-121">The first piped element is a time filter scoped to the previous seven days.</span></span> <span data-ttu-id="1ac00-122">Als u het tijdsbereik zo smal mogelijk houdt, zorgt u ervoor dat query's goed presteren, beheersbare resultaten retourneren en geen time-out krijgen.</span><span class="sxs-lookup"><span data-stu-id="1ac00-122">Keeping the time range as narrow as possible ensures that queries perform well, return manageable results, and don't time out.</span></span>

```kusto
| where Timestamp > ago(7d)
```

### <a name="check-specific-processes"></a><span data-ttu-id="1ac00-123">Specifieke processen controleren</span><span class="sxs-lookup"><span data-stu-id="1ac00-123">Check specific processes</span></span>
<span data-ttu-id="1ac00-124">Het tijdsbereik wordt onmiddellijk gevolgd door een zoekopdracht naar procesbestandsnamen die de PowerShell-toepassing vertegenwoordigen.</span><span class="sxs-lookup"><span data-stu-id="1ac00-124">The time range is immediately followed by a search for process file names representing the PowerShell application.</span></span>

```kusto
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
```

### <a name="search-for-specific-command-strings"></a><span data-ttu-id="1ac00-125">Zoeken naar specifieke opdrachttekenreeksen</span><span class="sxs-lookup"><span data-stu-id="1ac00-125">Search for specific command strings</span></span>
<span data-ttu-id="1ac00-126">Daarna zoekt de query naar tekenreeksen in opdrachtlijnen die doorgaans worden gebruikt om bestanden te downloaden met PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1ac00-126">Afterwards, the query looks for strings in command lines that are typically used to download files using PowerShell.</span></span>

```kusto
// Suspicious commands
| where ProcessCommandLine has_any("WebClient",
    "DownloadFile",
    "DownloadData",
    "DownloadString",
    "WebRequest",
    "Shellcode",
    "http",
    "https")
```

### <a name="customize-result-columns-and-length"></a><span data-ttu-id="1ac00-127">Resultaatkolommen en -lengte aanpassen</span><span class="sxs-lookup"><span data-stu-id="1ac00-127">Customize result columns and length</span></span> 
<span data-ttu-id="1ac00-128">Nu uw query duidelijk de gegevens identificeert die u wilt vinden, u elementen toevoegen die bepalen hoe de resultaten eruit zien.</span><span class="sxs-lookup"><span data-stu-id="1ac00-128">Now that your query clearly identifies the data you want to locate, you can add elements that define what the results look like.</span></span> <span data-ttu-id="1ac00-129">`project`retourneert specifieke kolommen en `top` beperkt het aantal resultaten.</span><span class="sxs-lookup"><span data-stu-id="1ac00-129">`project` returns specific columns, and `top` limits the number of results.</span></span> <span data-ttu-id="1ac00-130">Deze operatoren helpen ervoor te zorgen dat de resultaten goed zijn opgemaakt en redelijk groot en eenvoudig te verwerken zijn.</span><span class="sxs-lookup"><span data-stu-id="1ac00-130">These operators help ensure the results are well-formatted and reasonably large and easy to process.</span></span>

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

<span data-ttu-id="1ac00-131">Klik **op Query uitvoeren** om de resultaten te bekijken.</span><span class="sxs-lookup"><span data-stu-id="1ac00-131">Click **Run query** to see the results.</span></span> <span data-ttu-id="1ac00-132">Selecteer het pictogram uitvouwen rechtsboven in de queryeditor om u te concentreren op uw jachtquery en de resultaten.</span><span class="sxs-lookup"><span data-stu-id="1ac00-132">Select the expand icon at the top right of the query editor to focus on your hunting query and the results.</span></span> 

![Afbeelding van de besturingselement Uitbreiden in de geavanceerde query-editor](../../media/advanced-hunting-expand.png)

>[!TIP]
><span data-ttu-id="1ac00-134">U queryresultaten weergeven als grafieken en snel filters aanpassen.</span><span class="sxs-lookup"><span data-stu-id="1ac00-134">You can view query results as charts and quickly adjust filters.</span></span> <span data-ttu-id="1ac00-135">Lees voor advies [over het werken met queryresultaten](advanced-hunting-query-results.md)</span><span class="sxs-lookup"><span data-stu-id="1ac00-135">For guidance, [read about working with query results](advanced-hunting-query-results.md)</span></span>

## <a name="learn-common-query-operators-for-advanced-hunting"></a><span data-ttu-id="1ac00-136">Leer algemene queryoperators voor geavanceerde jacht</span><span class="sxs-lookup"><span data-stu-id="1ac00-136">Learn common query operators for advanced hunting</span></span>

<span data-ttu-id="1ac00-137">Nu u uw eerste query hebt uitgevoerd en een algemeen idee hebt van de componenten, is het tijd om een beetje terug te krabbelen en een aantal basisprincipes te leren.</span><span class="sxs-lookup"><span data-stu-id="1ac00-137">Now that you've run your first query and have a general idea of its components, it's time to backtrack a little bit and learn some basics.</span></span> <span data-ttu-id="1ac00-138">De Kusto-querytaal die wordt gebruikt door geavanceerde jacht, ondersteunt een reeks operatoren, waaronder de volgende veelvoorkomende.</span><span class="sxs-lookup"><span data-stu-id="1ac00-138">The Kusto query language used by advanced hunting supports a range of operators, including the following common ones.</span></span>

| <span data-ttu-id="1ac00-139">Operator</span><span class="sxs-lookup"><span data-stu-id="1ac00-139">Operator</span></span> | <span data-ttu-id="1ac00-140">Beschrijving en gebruik</span><span class="sxs-lookup"><span data-stu-id="1ac00-140">Description and usage</span></span> |
|--|--|
| `where` | <span data-ttu-id="1ac00-141">Filter een tabel naar de subset van rijen die voldoen aan een predicaat.</span><span class="sxs-lookup"><span data-stu-id="1ac00-141">Filter a table to the subset of rows that satisfy a predicate.</span></span> |
| `summarize` | <span data-ttu-id="1ac00-142">Maak een tabel die de inhoud van de invoertabel samenvoegt.</span><span class="sxs-lookup"><span data-stu-id="1ac00-142">Produce a table that aggregates the content of the input table.</span></span> |
| `join` | <span data-ttu-id="1ac00-143">Voeg de rijen van twee tabellen samen om een nieuwe tabel te vormen door waarden van de opgegeven kolom(en) uit elke tabel te matchen.</span><span class="sxs-lookup"><span data-stu-id="1ac00-143">Merge the rows of two tables to form a new table by matching values of the specified column(s) from each table.</span></span> |
| `count` | <span data-ttu-id="1ac00-144">Retourneert het aantal records in de invoerrecordset.</span><span class="sxs-lookup"><span data-stu-id="1ac00-144">Return the number of records in the input record set.</span></span> |
| `top` | <span data-ttu-id="1ac00-145">Retourneert de eerste N-records gesorteerd op de opgegeven kolommen.</span><span class="sxs-lookup"><span data-stu-id="1ac00-145">Return the first N records sorted by the specified columns.</span></span> |
| `limit` | <span data-ttu-id="1ac00-146">Ga terug naar het opgegeven aantal rijen.</span><span class="sxs-lookup"><span data-stu-id="1ac00-146">Return up to the specified number of rows.</span></span> |
| `project` | <span data-ttu-id="1ac00-147">Selecteer de kolommen die u wilt opnemen, de naam of de daling wilt wijzigen en nieuwe berekende kolommen invoegen.</span><span class="sxs-lookup"><span data-stu-id="1ac00-147">Select the columns to include, rename or drop, and insert new computed columns.</span></span> |
| `extend` | <span data-ttu-id="1ac00-148">Maak berekende kolommen en plaats ze aan de resultatenset.</span><span class="sxs-lookup"><span data-stu-id="1ac00-148">Create calculated columns and append them to the result set.</span></span> |
| `makeset` |  <span data-ttu-id="1ac00-149">Retourleer een dynamische array (JSON) van de set afzonderlijke waarden die Expr in de groep opneemt.</span><span class="sxs-lookup"><span data-stu-id="1ac00-149">Return a dynamic (JSON) array of the set of distinct values that Expr takes in the group.</span></span> |
| `find` | <span data-ttu-id="1ac00-150">Zoek rijen die overeenkomen met een predicaat in een set tabellen.</span><span class="sxs-lookup"><span data-stu-id="1ac00-150">Find rows that match a predicate across a set of tables.</span></span> |

<span data-ttu-id="1ac00-151">Als u een live voorbeeld van deze operatoren wilt zien, voert u ze uit vanuit de sectie Aan de **slag** in geavanceerde jacht.</span><span class="sxs-lookup"><span data-stu-id="1ac00-151">To see a live example of these operators, run them from the **Get started** section in advanced hunting.</span></span>

## <a name="understand-data-types-and-their-query-syntax-implications"></a><span data-ttu-id="1ac00-152">Gegevenstypen en de implicaties van querysyntaxis begrijpen</span><span class="sxs-lookup"><span data-stu-id="1ac00-152">Understand data types and their query syntax implications</span></span>

<span data-ttu-id="1ac00-153">Gegevens in geavanceerde jachttabellen worden over het algemeen ingedeeld in de volgende gegevenstypen.</span><span class="sxs-lookup"><span data-stu-id="1ac00-153">Data in advanced hunting tables are generally classified into the following data types.</span></span>

| <span data-ttu-id="1ac00-154">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="1ac00-154">Data type</span></span> | <span data-ttu-id="1ac00-155">Implicaties voor beschrijving en query</span><span class="sxs-lookup"><span data-stu-id="1ac00-155">Description and query implications</span></span> |
|--|--|
| `datetime` | <span data-ttu-id="1ac00-156">Gegevens en tijdsinformatie die doorgaans gebeurtenistimetamps vertegenwoordigen</span><span class="sxs-lookup"><span data-stu-id="1ac00-156">Data and time information typically representing event timestamps</span></span> |
| `string` | <span data-ttu-id="1ac00-157">Tekentekenreeks</span><span class="sxs-lookup"><span data-stu-id="1ac00-157">Character string</span></span> |
| `bool` | <span data-ttu-id="1ac00-158">Waar of onwaar</span><span class="sxs-lookup"><span data-stu-id="1ac00-158">True or false</span></span> |
| `int` | <span data-ttu-id="1ac00-159">32-bits numerieke waarde</span><span class="sxs-lookup"><span data-stu-id="1ac00-159">32-bit numeric value</span></span>  |
| `long` | <span data-ttu-id="1ac00-160">64-bits numerieke waarde</span><span class="sxs-lookup"><span data-stu-id="1ac00-160">64-bit numeric value</span></span> |

## <a name="get-help-as-you-write-queries"></a><span data-ttu-id="1ac00-161">Hulp krijgen bij het schrijven van query's</span><span class="sxs-lookup"><span data-stu-id="1ac00-161">Get help as you write queries</span></span>
<span data-ttu-id="1ac00-162">Profiteer van de volgende functionaliteit om query's sneller te schrijven:</span><span class="sxs-lookup"><span data-stu-id="1ac00-162">Take advantage of the following functionality to write queries faster:</span></span>
- <span data-ttu-id="1ac00-163">**Autosuggest** - als je schrijft query's, geavanceerde jacht biedt suggesties van IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="1ac00-163">**Autosuggest** — as you write queries, advanced hunting provides suggestions from IntelliSense.</span></span> 
- <span data-ttu-id="1ac00-164">**Schemastructuur** : een schemaweergave met de lijst met tabellen en hun kolommen wordt naast uw werkgebied weergegeven.</span><span class="sxs-lookup"><span data-stu-id="1ac00-164">**Schema tree** — a schema representation that includes the list of tables and their columns is provided next to your working area.</span></span> <span data-ttu-id="1ac00-165">Voor meer informatie u de muisaanwijzer op een item laten zweven.</span><span class="sxs-lookup"><span data-stu-id="1ac00-165">For more information, hover over an item.</span></span> <span data-ttu-id="1ac00-166">Dubbelklik op een item om het in te voegen aan de queryeditor.</span><span class="sxs-lookup"><span data-stu-id="1ac00-166">Double-click an item to insert it to the query editor.</span></span>
- <span data-ttu-id="1ac00-167">**[Schemaverwijzing](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** — in-portalverwijzing met tabel- en kolombeschrijvingen, ondersteunde gebeurtenistypen `ActionType` (waarden) en voorbeeldquery's</span><span class="sxs-lookup"><span data-stu-id="1ac00-167">**[Schema reference](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** — in-portal reference with table and column descriptions as well as supported event types (`ActionType` values) and sample queries</span></span>

## <a name="work-with-multiple-queries-in-the-editor"></a><span data-ttu-id="1ac00-168">Werken met meerdere query's in de editor</span><span class="sxs-lookup"><span data-stu-id="1ac00-168">Work with multiple queries in the editor</span></span>
<span data-ttu-id="1ac00-169">De queryeditor kan dienen als uw krasblok voor het experimenteren met meerdere query's.</span><span class="sxs-lookup"><span data-stu-id="1ac00-169">The query editor can serve as your scratch pad for experimenting with multiple queries.</span></span> <span data-ttu-id="1ac00-170">Ga als u meerdere query's gebruikt:</span><span class="sxs-lookup"><span data-stu-id="1ac00-170">To use multiple queries:</span></span>

- <span data-ttu-id="1ac00-171">Scheid elke query met een lege regel.</span><span class="sxs-lookup"><span data-stu-id="1ac00-171">Separate each query with an empty line.</span></span>
- <span data-ttu-id="1ac00-172">Plaats de cursor op een deel van een query om die query te selecteren voordat u deze uitvoert.</span><span class="sxs-lookup"><span data-stu-id="1ac00-172">Place the cursor on any part of a query to select that query before running it.</span></span> <span data-ttu-id="1ac00-173">Hiermee wordt alleen de geselecteerde query uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="1ac00-173">This will run only the selected query.</span></span> <span data-ttu-id="1ac00-174">Als u een andere query wilt uitvoeren, verplaatst u de cursor dienovereenkomstig en selecteert u **Query uitvoeren**.</span><span class="sxs-lookup"><span data-stu-id="1ac00-174">To run another query, move the cursor accordingly and select **Run query**.</span></span>

![Afbeelding van de queryeditor met meerdere query's](../../media/mtp-ah/ah-multi-query.png)

## <a name="use-sample-queries"></a><span data-ttu-id="1ac00-176">Voorbeeldquery's gebruiken</span><span class="sxs-lookup"><span data-stu-id="1ac00-176">Use sample queries</span></span>

<span data-ttu-id="1ac00-177">De sectie **Aan de slag** biedt een paar eenvoudige query's met veelgebruikte operators.</span><span class="sxs-lookup"><span data-stu-id="1ac00-177">The **Get started** section provides a few simple queries using commonly used operators.</span></span> <span data-ttu-id="1ac00-178">Probeer deze query's uit te voeren en kleine wijzigingen aan te brengen.</span><span class="sxs-lookup"><span data-stu-id="1ac00-178">Try running these queries and making small modifications to them.</span></span>

![Beeld van geavanceerd jachtvenster](../../media/advanced-hunting-get-started.png)

>[!NOTE]
><span data-ttu-id="1ac00-180">Naast de basisqueryvoorbeelden u ook toegang krijgen tot [gedeelde query's](advanced-hunting-shared-queries.md) voor specifieke scenario's voor bedreigingsjacht.</span><span class="sxs-lookup"><span data-stu-id="1ac00-180">Apart from the basic query samples, you can also access [shared queries](advanced-hunting-shared-queries.md) for specific threat hunting scenarios.</span></span> <span data-ttu-id="1ac00-181">Verken de gedeelde query's aan de linkerkant van de pagina of de GitHub-queryrepository.</span><span class="sxs-lookup"><span data-stu-id="1ac00-181">Explore the shared queries on the left side of the page or the GitHub query repository.</span></span>

## <a name="access-query-language-documentation"></a><span data-ttu-id="1ac00-182">Documentatie over querytaal openen</span><span class="sxs-lookup"><span data-stu-id="1ac00-182">Access query language documentation</span></span>

<span data-ttu-id="1ac00-183">Zie [Kusto querytaaldocumentatie](https://docs.microsoft.com/azure/kusto/query/)voor meer informatie over kusto-querytaal en ondersteunde operatoren.</span><span class="sxs-lookup"><span data-stu-id="1ac00-183">For more information on Kusto query language and supported operators, see [Kusto query language documentation](https://docs.microsoft.com/azure/kusto/query/).</span></span>

## <a name="related-topics"></a><span data-ttu-id="1ac00-184">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="1ac00-184">Related topics</span></span>
- [<span data-ttu-id="1ac00-185">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="1ac00-185">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="1ac00-186">Werken met queryresultaten</span><span class="sxs-lookup"><span data-stu-id="1ac00-186">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="1ac00-187">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="1ac00-187">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="1ac00-188">Zoek naar bedreigingen op verschillende apparaten en e-mails</span><span class="sxs-lookup"><span data-stu-id="1ac00-188">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="1ac00-189">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="1ac00-189">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="1ac00-190">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="1ac00-190">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
