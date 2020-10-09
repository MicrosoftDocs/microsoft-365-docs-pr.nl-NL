---
title: Meer informatie over de querytaal Advanced jacht in Microsoft Threat Protection
description: Maak uw eerste bedreigings informatie en leer meer over de gangbare operatoren en andere aspecten van de geavanceerde jacht-querytaal
keywords: geavanceerde jacht, bedreigings jacht, Cyber Threat jacht, Microsoft Threat Protection, Microsoft 365, MTP, m365, Search, query, update, learn, First query, Telemetry, gebeurtenissen, telemetrie, aangepaste detectie, schema, telemetrie, en voorbeeld van gegevenstypen
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
ms.openlocfilehash: de8a2c3d55d887a28500bb82a97e4453861aef46
ms.sourcegitcommit: cd17328baa58448214487e3e68c37590ab9fd08d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/09/2020
ms.locfileid: "48399215"
---
# <a name="learn-the-advanced-hunting-query-language"></a><span data-ttu-id="63b02-104">Meer informatie over de querytaal Advanced jacht</span><span class="sxs-lookup"><span data-stu-id="63b02-104">Learn the advanced hunting query language</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="63b02-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="63b02-105">**Applies to:**</span></span>
- <span data-ttu-id="63b02-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="63b02-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="63b02-107">Voor de geavanceerde jacht op basis van de [querytaal Kusto](https://docs.microsoft.com/azure/kusto/query/).</span><span class="sxs-lookup"><span data-stu-id="63b02-107">Advanced hunting is based on the [Kusto query language](https://docs.microsoft.com/azure/kusto/query/).</span></span> <span data-ttu-id="63b02-108">U kunt de syntaxis van Kusto en operatoren gebruiken om query's te maken waarmee informatie in een speciaal [schema](advanced-hunting-schema-tables.md)wordt gezocht.</span><span class="sxs-lookup"><span data-stu-id="63b02-108">You can use Kusto syntax and operators to construct queries that locate information in specialized [schema](advanced-hunting-schema-tables.md).</span></span> <span data-ttu-id="63b02-109">Voor een betere uitleg van deze concepten voert u uw eerste query uit.</span><span class="sxs-lookup"><span data-stu-id="63b02-109">To understand these concepts better, run your first query.</span></span>

## <a name="try-your-first-query"></a><span data-ttu-id="63b02-110">Probeer uw eerste query</span><span class="sxs-lookup"><span data-stu-id="63b02-110">Try your first query</span></span>

<span data-ttu-id="63b02-111">In Microsoft 365 Beveiligingscentrum gaat u naar **jacht** om uw eerste query uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="63b02-111">In Microsoft 365 security center, go to **Hunting** to run your first query.</span></span> <span data-ttu-id="63b02-112">Gebruik het volgende voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="63b02-112">Use the following example:</span></span>

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

<span data-ttu-id="63b02-113">**[Voer deze query uit in geavanceerde jacht](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2TW0sCURSF93PQfxh8Moisp956yYIgQtLoMaYczJpbzkkTpN_et_dcdPQkcpjbmrXXWftyetKTQG5lKqmMpeB9IJksJJKZDOWdZ8wKeP5wvcm3OLgZbMXmXCmIxjnYIfcAVgYvRi8w3TnfsXEDGAG47pCCZXyP5ViO4KeNbt-Up-hEuJmB6lvButnY8XSL-cDl0M2I-GwxVX8Fe2H5zMzHiKjEVB0eEsnBrszfBIWuXOLrxCJ7VqEBfM3DWUYTkNKrv1p5y3X0jwetemzOQ_NSVuuXZ1c6aNTKRaN8VvWhY9n7OS-o6J5r7mYeQypdEKc1m1qfiqpjCSuspsDntt2J61bEvTlXls5AgQfFl5bHM_gr_BhO2RF1rztoBv2tWahrso_TtzkL93KGMGZVr2pe7eWR-xeZl91f_113UOsx3nDR4Y9j5R6kaCq8ajr_YWfFeedsd27L7it-Z6dAZyxsJq1d9-2ZOSzK3y2NVd8-zUPjtZaJnYsIH4Md7AmdeAcd2Cl1XoURc5PzXlfU8U9P54WcswL6t_TW9Q__qX-xygQAAA&runQuery=true&timeRangeId=week)**</span><span class="sxs-lookup"><span data-stu-id="63b02-113">**[Run this query in advanced hunting](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2TW0sCURSF93PQfxh8Moisp956yYIgQtLoMaYczJpbzkkTpN_et_dcdPQkcpjbmrXXWftyetKTQG5lKqmMpeB9IJksJJKZDOWdZ8wKeP5wvcm3OLgZbMXmXCmIxjnYIfcAVgYvRi8w3TnfsXEDGAG47pCCZXyP5ViO4KeNbt-Up-hEuJmB6lvButnY8XSL-cDl0M2I-GwxVX8Fe2H5zMzHiKjEVB0eEsnBrszfBIWuXOLrxCJ7VqEBfM3DWUYTkNKrv1p5y3X0jwetemzOQ_NSVuuXZ1c6aNTKRaN8VvWhY9n7OS-o6J5r7mYeQypdEKc1m1qfiqpjCSuspsDntt2J61bEvTlXls5AgQfFl5bHM_gr_BhO2RF1rztoBv2tWahrso_TtzkL93KGMGZVr2pe7eWR-xeZl91f_113UOsx3nDR4Y9j5R6kaCq8ajr_YWfFeedsd27L7it-Z6dAZyxsJq1d9-2ZOSzK3y2NVd8-zUPjtZaJnYsIH4Md7AmdeAcd2Cl1XoURc5PzXlfU8U9P54WcswL6t_TW9Q__qX-xygQAAA&runQuery=true&timeRangeId=week)**</span></span>

### <a name="describe-the-query-and-specify-the-tables-to-search"></a><span data-ttu-id="63b02-114">De query beschrijven en de tabellen opgeven waarnaar moet worden gezocht</span><span class="sxs-lookup"><span data-stu-id="63b02-114">Describe the query and specify the tables to search</span></span>
<span data-ttu-id="63b02-115">Er is een korte opmerking toegevoegd aan het begin van de query om te beschrijven wat het is.</span><span class="sxs-lookup"><span data-stu-id="63b02-115">A short comment has been added to the beginning of the query to describe what it is for.</span></span> <span data-ttu-id="63b02-116">Deze opmerking helpt u als u later besluit om de query op te slaan en te delen met anderen in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="63b02-116">This comment helps if you later decide to save the query and share it with others in your organization.</span></span> 

```kusto
// Finds PowerShell execution events that could involve a download
```

<span data-ttu-id="63b02-117">De query zelf begint meestal met een tabelnaam gevolgd door meerdere elementen die beginnen met een sluisteken ( `|` ).</span><span class="sxs-lookup"><span data-stu-id="63b02-117">The query itself will typically start with a table name followed by several elements that start with a pipe (`|`).</span></span> <span data-ttu-id="63b02-118">In dit voorbeeld beginnen we met het maken van een samenvoeging van twee tabellen, en het  `DeviceProcessEvents` `DeviceNetworkEvents` toevoegen van elementen met een sluisteken.</span><span class="sxs-lookup"><span data-stu-id="63b02-118">In this example, we start by creating a union of two tables,  `DeviceProcessEvents` and `DeviceNetworkEvents`, and add piped elements as needed.</span></span>

```kusto
union DeviceProcessEvents, DeviceNetworkEvents
```
### <a name="set-the-time-range"></a><span data-ttu-id="63b02-119">Het tijdsbereik instellen</span><span class="sxs-lookup"><span data-stu-id="63b02-119">Set the time range</span></span>
<span data-ttu-id="63b02-120">Het eerste element met een pipet is een tijdfilter bereik dat de afgelopen zeven dagen is beperkt.</span><span class="sxs-lookup"><span data-stu-id="63b02-120">The first piped element is a time filter scoped to the previous seven days.</span></span> <span data-ttu-id="63b02-121">Wanneer u de periode beperkt, kunt u ervoor zorgen dat query's goed worden uitgevoerd, de beheerbare resultaten kunnen resulteren en geen tijd in beslag gaan.</span><span class="sxs-lookup"><span data-stu-id="63b02-121">Limiting the time range helps ensure that queries perform well, return manageable results, and don't time out.</span></span>

```kusto
| where Timestamp > ago(7d)
```

### <a name="check-specific-processes"></a><span data-ttu-id="63b02-122">Specifieke processen controleren</span><span class="sxs-lookup"><span data-stu-id="63b02-122">Check specific processes</span></span>
<span data-ttu-id="63b02-123">Het tijdsbereik wordt direct gevolgd door een zoekopdracht naar proces bestandsnamen die de PowerShell-toepassing vertegenwoordigen.</span><span class="sxs-lookup"><span data-stu-id="63b02-123">The time range is immediately followed by a search for process file names representing the PowerShell application.</span></span>

```kusto
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
```

### <a name="search-for-specific-command-strings"></a><span data-ttu-id="63b02-124">Zoeken naar specifieke opdrachtreeksen</span><span class="sxs-lookup"><span data-stu-id="63b02-124">Search for specific command strings</span></span>
<span data-ttu-id="63b02-125">Vervolgens zoekt de query naar tekenreeksen in opdrachtregels die meestal worden gebruikt om bestanden te downloaden met PowerShell.</span><span class="sxs-lookup"><span data-stu-id="63b02-125">Afterwards, the query looks for strings in command lines that are typically used to download files using PowerShell.</span></span>

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

### <a name="customize-result-columns-and-length"></a><span data-ttu-id="63b02-126">Resultatenkolommen en lengte aanpassen</span><span class="sxs-lookup"><span data-stu-id="63b02-126">Customize result columns and length</span></span> 
<span data-ttu-id="63b02-127">Wanneer de gegevens die u wilt zoeken duidelijk worden geïdentificeerd met de query, kunt u definiëren hoe de resultaten eruit komen te zien.</span><span class="sxs-lookup"><span data-stu-id="63b02-127">Now that your query clearly identifies the data you want to locate, you can define what the results look like.</span></span> <span data-ttu-id="63b02-128">`project` geeft als resultaat bepaalde kolommen en `top` beperkt het aantal resultaten.</span><span class="sxs-lookup"><span data-stu-id="63b02-128">`project` returns specific columns, and `top` limits the number of results.</span></span> <span data-ttu-id="63b02-129">Met deze operatoren zorgt u ervoor dat de resultaten goed opgemaakt en redelijk zijn.</span><span class="sxs-lookup"><span data-stu-id="63b02-129">These operators help ensure the results are well-formatted and reasonably large and easy to process.</span></span>

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

<span data-ttu-id="63b02-130">Selecteer **query uitvoeren** om de resultaten te bekijken.</span><span class="sxs-lookup"><span data-stu-id="63b02-130">Select **Run query** to see the results.</span></span> <span data-ttu-id="63b02-131">Met het pictogram uitvouwen in de rechterbovenhoek van de query editor kunt u zich richten op de jacht-query en de resultaten.</span><span class="sxs-lookup"><span data-stu-id="63b02-131">Use the expand icon at the top right of the query editor to focus on your hunting query and the results.</span></span> 

![Afbeelding van het besturingselement uitvouwen in de geavanceerde jacht query editor](../../media/advanced-hunting-expand.png)

>[!TIP]
><span data-ttu-id="63b02-133">U kunt queryresultaten weergeven als grafieken en de filters snel aanpassen.</span><span class="sxs-lookup"><span data-stu-id="63b02-133">You can view query results as charts and quickly adjust filters.</span></span> <span data-ttu-id="63b02-134">[Zie voor meer informatie over het werken met queryresultaten](advanced-hunting-query-results.md)</span><span class="sxs-lookup"><span data-stu-id="63b02-134">For guidance, [read about working with query results](advanced-hunting-query-results.md)</span></span>

## <a name="learn-common-query-operators"></a><span data-ttu-id="63b02-135">Veelgebruikte queryoperators</span><span class="sxs-lookup"><span data-stu-id="63b02-135">Learn common query operators</span></span>

<span data-ttu-id="63b02-136">U voer zojuist uw eerste query uit en hebt een algemeen idee van de onderdelen.</span><span class="sxs-lookup"><span data-stu-id="63b02-136">You've just run your first query and have a general idea of its components.</span></span> <span data-ttu-id="63b02-137">Het is tijd om iets iets te terugkeren iets en meer informatie over de basisbeginselen te leren kennen.</span><span class="sxs-lookup"><span data-stu-id="63b02-137">It's time to backtrack slightly and learn some basics.</span></span> <span data-ttu-id="63b02-138">De Kusto querytaal die wordt gebruikt in de geavanceerde jacht, biedt ondersteuning voor een bereik van operatoren, waaronder de volgende algemene versies.</span><span class="sxs-lookup"><span data-stu-id="63b02-138">The Kusto query language used by advanced hunting supports a range of operators, including the following common ones.</span></span>

| <span data-ttu-id="63b02-139">Werk</span><span class="sxs-lookup"><span data-stu-id="63b02-139">Operator</span></span> | <span data-ttu-id="63b02-140">Beschrijving en gebruik</span><span class="sxs-lookup"><span data-stu-id="63b02-140">Description and usage</span></span> |
|--|--|
| `where` | <span data-ttu-id="63b02-141">Een tabel filteren op de subset van rijen die op een predicaat voldoen.</span><span class="sxs-lookup"><span data-stu-id="63b02-141">Filter a table to the subset of rows that satisfy a predicate.</span></span> |
| `summarize` | <span data-ttu-id="63b02-142">Een tabel maken waarmee de inhoud van de invoertabel wordt geaggregeerd.</span><span class="sxs-lookup"><span data-stu-id="63b02-142">Produce a table that aggregates the content of the input table.</span></span> |
| `join` | <span data-ttu-id="63b02-143">De rijen van twee tabellen samenvoegen om een nieuwe tabel te maken door te zoeken naar waarden van de opgegeven kolommen in elke tabel.</span><span class="sxs-lookup"><span data-stu-id="63b02-143">Merge the rows of two tables to form a new table by matching values of the specified column(s) from each table.</span></span> |
| `count` | <span data-ttu-id="63b02-144">Het aantal records in de invoerrecord retourneren.</span><span class="sxs-lookup"><span data-stu-id="63b02-144">Return the number of records in the input record set.</span></span> |
| `top` | <span data-ttu-id="63b02-145">De eerste N records die op de opgegeven kolommen zijn gesorteerd, retourneren.</span><span class="sxs-lookup"><span data-stu-id="63b02-145">Return the first N records sorted by the specified columns.</span></span> |
| `limit` | <span data-ttu-id="63b02-146">Naar het opgegeven aantal rijen gaan.</span><span class="sxs-lookup"><span data-stu-id="63b02-146">Return up to the specified number of rows.</span></span> |
| `project` | <span data-ttu-id="63b02-147">Selecteer de kolommen die u wilt opnemen, waarvan u de naam wilt wijzigen of die u wilt verwijderen en voeg nieuwe berekende kolommen in.</span><span class="sxs-lookup"><span data-stu-id="63b02-147">Select the columns to include, rename or drop, and insert new computed columns.</span></span> |
| `extend` | <span data-ttu-id="63b02-148">Berekende kolommen maken en deze toevoegen aan de resultatenset.</span><span class="sxs-lookup"><span data-stu-id="63b02-148">Create calculated columns and append them to the result set.</span></span> |
| `makeset` |  <span data-ttu-id="63b02-149">Retourneert een dynamische (JSON) matrix van de reeks unieke waarden die in de groep worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="63b02-149">Return a dynamic (JSON) array of the set of distinct values that Expr takes in the group.</span></span> |
| `find` | <span data-ttu-id="63b02-150">Rijen zoeken die overeenkomen met een predicaat in een set tabellen.</span><span class="sxs-lookup"><span data-stu-id="63b02-150">Find rows that match a predicate across a set of tables.</span></span> |

<span data-ttu-id="63b02-151">Als u een voorbeeld van deze operatoren wilt zien, voert u deze uit in de sectie **aan de slag** in geavanceerde jacht.</span><span class="sxs-lookup"><span data-stu-id="63b02-151">To see a live example of these operators, run them from the **Get started** section in advanced hunting.</span></span>

## <a name="understand-data-types"></a><span data-ttu-id="63b02-152">Meer informatie over gegevenstypen</span><span class="sxs-lookup"><span data-stu-id="63b02-152">Understand data types</span></span>

<span data-ttu-id="63b02-153">Geavanceerde jacht biedt ondersteuning voor Kusto-gegevenstypen, waaronder de volgende algemene typen:</span><span class="sxs-lookup"><span data-stu-id="63b02-153">Advanced hunting supports Kusto data types, including the following common types:</span></span>

| <span data-ttu-id="63b02-154">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="63b02-154">Data type</span></span> | <span data-ttu-id="63b02-155">Beschrijving van de gevolgen van de query</span><span class="sxs-lookup"><span data-stu-id="63b02-155">Description and query implications</span></span> |
|--|--|
| `datetime` | <span data-ttu-id="63b02-156">Gegevens en tijds informatie die meestal tijdstempels voor gebeurtenissen vertegenwoordigen.</span><span class="sxs-lookup"><span data-stu-id="63b02-156">Data and time information typically representing event timestamps.</span></span> [<span data-ttu-id="63b02-157">Ondersteunde notaties voor datetime weergeven</span><span class="sxs-lookup"><span data-stu-id="63b02-157">See supported datetime formats</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/datetime) |
| `string` | <span data-ttu-id="63b02-158">Tekenreeks in UTF-8 tussen enkele aanhalingstekens ( `'` ) of dubbele aanhalingstekens ( `"` ).</span><span class="sxs-lookup"><span data-stu-id="63b02-158">Character string in UTF-8 enclosed in single quotes (`'`) or double quotes (`"`).</span></span> [<span data-ttu-id="63b02-159">Lees meer over tekenreeksen</span><span class="sxs-lookup"><span data-stu-id="63b02-159">Read more about strings</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/string) |
| `bool` | <span data-ttu-id="63b02-160">Dit gegevenstype ondersteunt `true` of `false` staat.</span><span class="sxs-lookup"><span data-stu-id="63b02-160">This data type supports `true` or `false` states.</span></span> [<span data-ttu-id="63b02-161">Ondersteunde letterlijke waarden en operatoren weergeven</span><span class="sxs-lookup"><span data-stu-id="63b02-161">See supported literals and operators</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/bool) |
| `int` | <span data-ttu-id="63b02-162">32-bits integer</span><span class="sxs-lookup"><span data-stu-id="63b02-162">32-bit integer</span></span>  |
| `long` | <span data-ttu-id="63b02-163">64-bits integer</span><span class="sxs-lookup"><span data-stu-id="63b02-163">64-bit integer</span></span> |

<span data-ttu-id="63b02-164">Meer informatie over deze gegevenstypen vindt u in [Kusto scalaire gegevenstypen](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/).</span><span class="sxs-lookup"><span data-stu-id="63b02-164">To learn more about these data types, [read about Kusto scalar data types](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/).</span></span>

## <a name="get-help-as-you-write-queries"></a><span data-ttu-id="63b02-165">Hulp vragen bij het schrijven van query's</span><span class="sxs-lookup"><span data-stu-id="63b02-165">Get help as you write queries</span></span>
<span data-ttu-id="63b02-166">Profiteer van de volgende functies om query's sneller te schrijven:</span><span class="sxs-lookup"><span data-stu-id="63b02-166">Take advantage of the following functionality to write queries faster:</span></span>
- <span data-ttu-id="63b02-167">**Suggesties, wanneer**u query's schrijft, biedt geavanceerde jacht suggesties voor IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="63b02-167">**Autosuggest**—as you write queries, advanced hunting provides suggestions from IntelliSense.</span></span> 
- <span data-ttu-id="63b02-168">**Schemastructuur**: een schema weergave met daarin de lijst met tabellen en de bijbehorende kolommen wordt weergegeven naast uw werkruimte.</span><span class="sxs-lookup"><span data-stu-id="63b02-168">**Schema tree**—a schema representation that includes the list of tables and their columns is provided next to your working area.</span></span> <span data-ttu-id="63b02-169">Plaats de muisaanwijzer op een item voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="63b02-169">For more information, hover over an item.</span></span> <span data-ttu-id="63b02-170">Dubbelklik op een item om het in te voegen in de query editor.</span><span class="sxs-lookup"><span data-stu-id="63b02-170">Double-click an item to insert it to the query editor.</span></span>
- <span data-ttu-id="63b02-171">Naslag voor **[schema verwijzingen](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** in de portal met beschrijvingen van tabellen en kolommen, en ondersteunde gebeurtenistypen ( `ActionType` waarden) en voorbeeldquery's</span><span class="sxs-lookup"><span data-stu-id="63b02-171">**[Schema reference](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)**—in-portal reference with table and column descriptions as well as supported event types (`ActionType` values) and sample queries</span></span>

## <a name="work-with-multiple-queries-in-the-editor"></a><span data-ttu-id="63b02-172">Werken met meerdere query's in de editor</span><span class="sxs-lookup"><span data-stu-id="63b02-172">Work with multiple queries in the editor</span></span>
<span data-ttu-id="63b02-173">Met de query editor kunt u experimenteren met meerdere query's.</span><span class="sxs-lookup"><span data-stu-id="63b02-173">You can use the query editor to experiment with multiple queries.</span></span> <span data-ttu-id="63b02-174">Meerdere query's gebruiken:</span><span class="sxs-lookup"><span data-stu-id="63b02-174">To use multiple queries:</span></span>

- <span data-ttu-id="63b02-175">Afzonderlijke query's met een lege regel scheiden.</span><span class="sxs-lookup"><span data-stu-id="63b02-175">Separate each query with an empty line.</span></span>
- <span data-ttu-id="63b02-176">Plaats de cursor op een deel van een query om die query te selecteren voordat u deze uitvoert.</span><span class="sxs-lookup"><span data-stu-id="63b02-176">Place the cursor on any part of a query to select that query before running it.</span></span> <span data-ttu-id="63b02-177">Hiermee wordt alleen de geselecteerde query uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="63b02-177">This will run only the selected query.</span></span> <span data-ttu-id="63b02-178">Als u een andere query wilt uitvoeren, verplaatst u de cursor dienovereenkomstig en selecteert u **query uitvoeren**.</span><span class="sxs-lookup"><span data-stu-id="63b02-178">To run another query, move the cursor accordingly and select **Run query**.</span></span>

![Afbeelding van de query editor met meerdere query's](../../media/mtp-ah/ah-multi-query.png)

## <a name="use-sample-queries"></a><span data-ttu-id="63b02-180">Voorbeeldquery's gebruiken</span><span class="sxs-lookup"><span data-stu-id="63b02-180">Use sample queries</span></span>

<span data-ttu-id="63b02-181">De sectie **aan** de slag biedt een paar eenvoudige query's waarbij veelgebruikte operatoren worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="63b02-181">The **Get started** section provides a few simple queries using commonly used operators.</span></span> <span data-ttu-id="63b02-182">Voer deze query's uit en wijzig deze met een kleine wijziging.</span><span class="sxs-lookup"><span data-stu-id="63b02-182">Try running these queries and making small modifications to them.</span></span>

![Afbeelding van het venster Geavanceerde jacht](../../media/advanced-hunting-get-started.png)

>[!NOTE]
><span data-ttu-id="63b02-184">Afgezien van de basisvoorbeelden van de query, hebt u ook toegang tot [gedeelde query's](advanced-hunting-shared-queries.md) voor specifieke scenario's voor bedreigings jacht.</span><span class="sxs-lookup"><span data-stu-id="63b02-184">Apart from the basic query samples, you can also access [shared queries](advanced-hunting-shared-queries.md) for specific threat hunting scenarios.</span></span> <span data-ttu-id="63b02-185">Verstudeer de gedeelde query's aan de linkerkant van de pagina of in de [github query-bibliotheek](https://aka.ms/hunting-queries).</span><span class="sxs-lookup"><span data-stu-id="63b02-185">Explore the shared queries on the left side of the page or the [GitHub query repository](https://aka.ms/hunting-queries).</span></span>

## <a name="access-query-language-documentation"></a><span data-ttu-id="63b02-186">Documentatie voor Access-querytalen</span><span class="sxs-lookup"><span data-stu-id="63b02-186">Access query language documentation</span></span>

<span data-ttu-id="63b02-187">Zie de [documentatie bij de querytaal van Kusto](https://docs.microsoft.com/azure/kusto/query/)voor meer informatie over Kusto querytaal en ondersteunde operatoren.</span><span class="sxs-lookup"><span data-stu-id="63b02-187">For more information on Kusto query language and supported operators, see [Kusto query language documentation](https://docs.microsoft.com/azure/kusto/query/).</span></span>

## <a name="related-topics"></a><span data-ttu-id="63b02-188">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="63b02-188">Related topics</span></span>
- [<span data-ttu-id="63b02-189">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="63b02-189">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="63b02-190">Werken met queryresultaten</span><span class="sxs-lookup"><span data-stu-id="63b02-190">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="63b02-191">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="63b02-191">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="63b02-192">Opsporen op apparaten en in e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="63b02-192">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="63b02-193">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="63b02-193">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="63b02-194">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="63b02-194">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
