---
title: De geavanceerde zoekquerytaal in Microsoft 365 Defender leren
description: Maak uw eerste zoekquery voor bedreigingen en leer meer over veelgebruikte operatoren en andere aspecten van de geavanceerde zoekquerytaal
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, language, learn, first query, telemetry, events, telemetry, custom detections, schema, kusto, operators, data types, powershell download, query example
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
ms.openlocfilehash: 14287fb6dea9dda8accb580246b383f0427c3b3f
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952618"
---
# <a name="learn-the-advanced-hunting-query-language"></a><span data-ttu-id="3a783-104">De geavanceerde zoekquerytaal leren</span><span class="sxs-lookup"><span data-stu-id="3a783-104">Learn the advanced hunting query language</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="3a783-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="3a783-105">**Applies to:**</span></span>
- <span data-ttu-id="3a783-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3a783-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="3a783-107">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="3a783-107">Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="3a783-108">Geavanceerd zoeken is gebaseerd op de [querytaal Kusto.](/azure/kusto/query/)</span><span class="sxs-lookup"><span data-stu-id="3a783-108">Advanced hunting is based on the [Kusto query language](/azure/kusto/query/).</span></span> <span data-ttu-id="3a783-109">U kunt Kusto-operatoren en instructies gebruiken om query's te maken die informatie zoeken in een gespecialiseerd [schema.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="3a783-109">You can use Kusto operators and statements to construct queries that locate information in a specialized [schema](advanced-hunting-schema-tables.md).</span></span> <span data-ttu-id="3a783-110">Als u deze concepten beter wilt begrijpen, kunt u de eerste query uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="3a783-110">To understand these concepts better, run your first query.</span></span>

## <a name="try-your-first-query"></a><span data-ttu-id="3a783-111">Probeer uw eerste query</span><span class="sxs-lookup"><span data-stu-id="3a783-111">Try your first query</span></span>

<span data-ttu-id="3a783-112">Ga in het Microsoft 365-beveiligingscentrum naar **Hunting** om uw eerste query uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="3a783-112">In Microsoft 365 security center, go to **Hunting** to run your first query.</span></span> <span data-ttu-id="3a783-113">Gebruik het volgende voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="3a783-113">Use the following example:</span></span>

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

<span data-ttu-id="3a783-114">**[Voer deze query uit in geavanceerd zoeken](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2TW0sCURSF93PQfxh8Moisp956yYIgQtLoMaYczJpbzkkTpN_et_dcdPQkcpjbmrXXWftyetKTQG5lKqmMpeB9IJksJJKZDOWdZ8wKeP5wvcm3OLgZbMXmXCmIxjnYIfcAVgYvRi8w3TnfsXEDGAG47pCCZXyP5ViO4KeNbt-Up-hEuJmB6lvButnY8XSL-cDl0M2I-GwxVX8Fe2H5zMzHiKjEVB0eEsnBrszfBIWuXOLrxCJ7VqEBfM3DWUYTkNKrv1p5y3X0jwetemzOQ_NSVuuXZ1c6aNTKRaN8VvWhY9n7OS-o6J5r7mYeQypdEKc1m1qfiqpjCSuspsDntt2J61bEvTlXls5AgQfFl5bHM_gr_BhO2RF1rztoBv2tWahrso_TtzkL93KGMGZVr2pe7eWR-xeZl91f_113UOsx3nDR4Y9j5R6kaCq8ajr_YWfFeedsd27L7it-Z6dAZyxsJq1d9-2ZOSzK3y2NVd8-zUPjtZaJnYsIH4Md7AmdeAcd2Cl1XoURc5PzXlfU8U9P54WcswL6t_TW9Q__qX-xygQAAA&runQuery=true&timeRangeId=week)**</span><span class="sxs-lookup"><span data-stu-id="3a783-114">**[Run this query in advanced hunting](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2TW0sCURSF93PQfxh8Moisp956yYIgQtLoMaYczJpbzkkTpN_et_dcdPQkcpjbmrXXWftyetKTQG5lKqmMpeB9IJksJJKZDOWdZ8wKeP5wvcm3OLgZbMXmXCmIxjnYIfcAVgYvRi8w3TnfsXEDGAG47pCCZXyP5ViO4KeNbt-Up-hEuJmB6lvButnY8XSL-cDl0M2I-GwxVX8Fe2H5zMzHiKjEVB0eEsnBrszfBIWuXOLrxCJ7VqEBfM3DWUYTkNKrv1p5y3X0jwetemzOQ_NSVuuXZ1c6aNTKRaN8VvWhY9n7OS-o6J5r7mYeQypdEKc1m1qfiqpjCSuspsDntt2J61bEvTlXls5AgQfFl5bHM_gr_BhO2RF1rztoBv2tWahrso_TtzkL93KGMGZVr2pe7eWR-xeZl91f_113UOsx3nDR4Y9j5R6kaCq8ajr_YWfFeedsd27L7it-Z6dAZyxsJq1d9-2ZOSzK3y2NVd8-zUPjtZaJnYsIH4Md7AmdeAcd2Cl1XoURc5PzXlfU8U9P54WcswL6t_TW9Q__qX-xygQAAA&runQuery=true&timeRangeId=week)**</span></span>

### <a name="describe-the-query-and-specify-the-tables-to-search"></a><span data-ttu-id="3a783-115">Beschrijf de query en geef de tabellen op die u wilt zoeken</span><span class="sxs-lookup"><span data-stu-id="3a783-115">Describe the query and specify the tables to search</span></span>
<span data-ttu-id="3a783-116">Er is een korte opmerking toegevoegd aan het begin van de query om te beschrijven waar deze voor is.</span><span class="sxs-lookup"><span data-stu-id="3a783-116">A short comment has been added to the beginning of the query to describe what it is for.</span></span> <span data-ttu-id="3a783-117">Deze opmerking helpt als u later besluit de query op te slaan en deze te delen met anderen in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="3a783-117">This comment helps if you later decide to save the query and share it with others in your organization.</span></span> 

```kusto
// Finds PowerShell execution events that could involve a download
```

<span data-ttu-id="3a783-118">De query zelf begint meestal met een tabelnaam, gevolgd door verschillende elementen die beginnen met een pijp ( `|` ).</span><span class="sxs-lookup"><span data-stu-id="3a783-118">The query itself will typically start with a table name followed by several elements that start with a pipe (`|`).</span></span> <span data-ttu-id="3a783-119">In dit voorbeeld beginnen we met het maken van een samenvoeging van twee tabellen en , en voegen we zo nodig  `DeviceProcessEvents` `DeviceNetworkEvents` gepijpte elementen toe.</span><span class="sxs-lookup"><span data-stu-id="3a783-119">In this example, we start by creating a union of two tables,  `DeviceProcessEvents` and `DeviceNetworkEvents`, and add piped elements as needed.</span></span>

```kusto
union DeviceProcessEvents, DeviceNetworkEvents
```
### <a name="set-the-time-range"></a><span data-ttu-id="3a783-120">Het tijdsbereik instellen</span><span class="sxs-lookup"><span data-stu-id="3a783-120">Set the time range</span></span>
<span data-ttu-id="3a783-121">Het eerste piped-element is een tijdfilter dat is beperkt tot de afgelopen zeven dagen.</span><span class="sxs-lookup"><span data-stu-id="3a783-121">The first piped element is a time filter scoped to the previous seven days.</span></span> <span data-ttu-id="3a783-122">Als u het tijdbereik beperkt, zorgt u ervoor dat query's goed presteren, beheersbare resultaten retourneren en geen time-out maken.</span><span class="sxs-lookup"><span data-stu-id="3a783-122">Limiting the time range helps ensure that queries perform well, return manageable results, and don't time out.</span></span>

```kusto
| where Timestamp > ago(7d)
```

### <a name="check-specific-processes"></a><span data-ttu-id="3a783-123">Specifieke processen controleren</span><span class="sxs-lookup"><span data-stu-id="3a783-123">Check specific processes</span></span>
<span data-ttu-id="3a783-124">Het tijdbereik wordt onmiddellijk gevolgd door een zoekopdracht naar de namen van procesbestanden die de PowerShell-toepassing vertegenwoordigen.</span><span class="sxs-lookup"><span data-stu-id="3a783-124">The time range is immediately followed by a search for process file names representing the PowerShell application.</span></span>

```kusto
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
```

### <a name="search-for-specific-command-strings"></a><span data-ttu-id="3a783-125">Specifieke opdrachtreeksen zoeken</span><span class="sxs-lookup"><span data-stu-id="3a783-125">Search for specific command strings</span></span>
<span data-ttu-id="3a783-126">Daarna zoekt de query naar tekenreeksen in opdrachtregels die gewoonlijk worden gebruikt om bestanden te downloaden met PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3a783-126">Afterwards, the query looks for strings in command lines that are typically used to download files using PowerShell.</span></span>

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

### <a name="customize-result-columns-and-length"></a><span data-ttu-id="3a783-127">Resultaatkolommen en lengte aanpassen</span><span class="sxs-lookup"><span data-stu-id="3a783-127">Customize result columns and length</span></span> 
<span data-ttu-id="3a783-128">Nu de query duidelijk aangeeft welke gegevens u wilt zoeken, kunt u definiëren hoe de resultaten eruit zien.</span><span class="sxs-lookup"><span data-stu-id="3a783-128">Now that your query clearly identifies the data you want to locate, you can define what the results look like.</span></span> <span data-ttu-id="3a783-129">`project` geeft als resultaat specifieke kolommen en `top` beperkt het aantal resultaten.</span><span class="sxs-lookup"><span data-stu-id="3a783-129">`project` returns specific columns, and `top` limits the number of results.</span></span> <span data-ttu-id="3a783-130">Deze operatoren helpen ervoor te zorgen dat de resultaten goed zijn opgemaakt en redelijk groot en eenvoudig te verwerken zijn.</span><span class="sxs-lookup"><span data-stu-id="3a783-130">These operators help ensure the results are well-formatted and reasonably large and easy to process.</span></span>

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

<span data-ttu-id="3a783-131">Selecteer **Query uitvoeren om** de resultaten te zien.</span><span class="sxs-lookup"><span data-stu-id="3a783-131">Select **Run query** to see the results.</span></span> <span data-ttu-id="3a783-132">Gebruik het pictogram Uitvvuiten rechtsboven in de queryeditor om de focus te leggen op uw query en de resultaten.</span><span class="sxs-lookup"><span data-stu-id="3a783-132">Use the expand icon at the top right of the query editor to focus on your hunting query and the results.</span></span> 

![Afbeelding van het besturingselement Uitvvv in de geavanceerde queryeditor](../../media/advanced-hunting-expand.png)

>[!TIP]
><span data-ttu-id="3a783-134">U kunt queryresultaten weergeven als grafieken en snel filters aanpassen.</span><span class="sxs-lookup"><span data-stu-id="3a783-134">You can view query results as charts and quickly adjust filters.</span></span> <span data-ttu-id="3a783-135">Lees voor meer [informatie over het werken met queryresultaten](advanced-hunting-query-results.md)</span><span class="sxs-lookup"><span data-stu-id="3a783-135">For guidance, [read about working with query results](advanced-hunting-query-results.md)</span></span>

## <a name="learn-common-query-operators"></a><span data-ttu-id="3a783-136">Veelgebruikte queryoperatoren leren</span><span class="sxs-lookup"><span data-stu-id="3a783-136">Learn common query operators</span></span>

<span data-ttu-id="3a783-137">U hebt zojuist uw eerste query uitgevoerd en hebt een algemeen idee van de onderdelen.</span><span class="sxs-lookup"><span data-stu-id="3a783-137">You've just run your first query and have a general idea of its components.</span></span> <span data-ttu-id="3a783-138">Het is tijd om iets terug te keren en enkele basisbeginselen te leren.</span><span class="sxs-lookup"><span data-stu-id="3a783-138">It's time to backtrack slightly and learn some basics.</span></span> <span data-ttu-id="3a783-139">De kusto-querytaal die wordt gebruikt door geavanceerde jagen ondersteunt een reeks operatoren, waaronder de volgende veelgebruikte.</span><span class="sxs-lookup"><span data-stu-id="3a783-139">The Kusto query language used by advanced hunting supports a range of operators, including the following common ones.</span></span>

| <span data-ttu-id="3a783-140">Operator</span><span class="sxs-lookup"><span data-stu-id="3a783-140">Operator</span></span> | <span data-ttu-id="3a783-141">Beschrijving en gebruik</span><span class="sxs-lookup"><span data-stu-id="3a783-141">Description and usage</span></span> |
|--|--|
| `where` | <span data-ttu-id="3a783-142">Een tabel filteren op de subset van rijen die voldoen aan een predicaat.</span><span class="sxs-lookup"><span data-stu-id="3a783-142">Filter a table to the subset of rows that satisfy a predicate.</span></span> |
| `summarize` | <span data-ttu-id="3a783-143">Een tabel maken die de inhoud van de invoertabel aggregeert.</span><span class="sxs-lookup"><span data-stu-id="3a783-143">Produce a table that aggregates the content of the input table.</span></span> |
| `join` | <span data-ttu-id="3a783-144">Voeg de rijen van twee tabellen samen om een nieuwe tabel te vormen door de waarden van de opgegeven kolom(en) uit elke tabel te koppelen.</span><span class="sxs-lookup"><span data-stu-id="3a783-144">Merge the rows of two tables to form a new table by matching values of the specified column(s) from each table.</span></span> |
| `count` | <span data-ttu-id="3a783-145">Het aantal records in de invoerrecordset retourneren.</span><span class="sxs-lookup"><span data-stu-id="3a783-145">Return the number of records in the input record set.</span></span> |
| `top` | <span data-ttu-id="3a783-146">Retourneert de eerste N-records gesorteerd op de opgegeven kolommen.</span><span class="sxs-lookup"><span data-stu-id="3a783-146">Return the first N records sorted by the specified columns.</span></span> |
| `limit` | <span data-ttu-id="3a783-147">Ga terug naar het opgegeven aantal rijen.</span><span class="sxs-lookup"><span data-stu-id="3a783-147">Return up to the specified number of rows.</span></span> |
| `project` | <span data-ttu-id="3a783-148">Selecteer de kolommen die u wilt opnemen, de naam wilt wijzigen of neerzetten en voeg nieuwe berekende kolommen in.</span><span class="sxs-lookup"><span data-stu-id="3a783-148">Select the columns to include, rename or drop, and insert new computed columns.</span></span> |
| `extend` | <span data-ttu-id="3a783-149">Maak berekende kolommen en wijs deze toe aan de resultatenset.</span><span class="sxs-lookup"><span data-stu-id="3a783-149">Create calculated columns and append them to the result set.</span></span> |
| `makeset` |  <span data-ttu-id="3a783-150">Retourneert een dynamische matrix (JSON) van de set afzonderlijke waarden die Expr in de groep op zich neemt.</span><span class="sxs-lookup"><span data-stu-id="3a783-150">Return a dynamic (JSON) array of the set of distinct values that Expr takes in the group.</span></span> |
| `find` | <span data-ttu-id="3a783-151">Rijen zoeken die overeenkomen met een predicaat in een set tabellen.</span><span class="sxs-lookup"><span data-stu-id="3a783-151">Find rows that match a predicate across a set of tables.</span></span> |

<span data-ttu-id="3a783-152">Als u een livevoorbeeld van deze operatoren wilt zien, kunt u deze uitvoeren vanuit de sectie **Aan de** slag in geavanceerde jacht.</span><span class="sxs-lookup"><span data-stu-id="3a783-152">To see a live example of these operators, run them from the **Get started** section in advanced hunting.</span></span>

## <a name="understand-data-types"></a><span data-ttu-id="3a783-153">Gegevenstypen begrijpen</span><span class="sxs-lookup"><span data-stu-id="3a783-153">Understand data types</span></span>

<span data-ttu-id="3a783-154">Geavanceerde jacht ondersteunt Kusto-gegevenstypen, waaronder de volgende veelvoorkomende typen:</span><span class="sxs-lookup"><span data-stu-id="3a783-154">Advanced hunting supports Kusto data types, including the following common types:</span></span>

| <span data-ttu-id="3a783-155">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="3a783-155">Data type</span></span> | <span data-ttu-id="3a783-156">Beschrijving en query-implicaties</span><span class="sxs-lookup"><span data-stu-id="3a783-156">Description and query implications</span></span> |
|--|--|
| `datetime` | <span data-ttu-id="3a783-157">Gegevens- en tijdgegevens die meestal gebeurtenistijdstempels vertegenwoordigen.</span><span class="sxs-lookup"><span data-stu-id="3a783-157">Data and time information typically representing event timestamps.</span></span> [<span data-ttu-id="3a783-158">Ondersteunde datumtime-indelingen bekijken</span><span class="sxs-lookup"><span data-stu-id="3a783-158">See supported datetime formats</span></span>](/azure/data-explorer/kusto/query/scalar-data-types/datetime) |
| `string` | <span data-ttu-id="3a783-159">Tekenreeks in UTF-8 tussen enkele aanhalingstekens ( `'` ) of dubbele aanhalingstekens ( `"` ).</span><span class="sxs-lookup"><span data-stu-id="3a783-159">Character string in UTF-8 enclosed in single quotes (`'`) or double quotes (`"`).</span></span> [<span data-ttu-id="3a783-160">Meer informatie over tekenreeksen</span><span class="sxs-lookup"><span data-stu-id="3a783-160">Read more about strings</span></span>](/azure/data-explorer/kusto/query/scalar-data-types/string) |
| `bool` | <span data-ttu-id="3a783-161">Dit gegevenstype ondersteunt `true` of `false` geeft deze op.</span><span class="sxs-lookup"><span data-stu-id="3a783-161">This data type supports `true` or `false` states.</span></span> [<span data-ttu-id="3a783-162">Ondersteunde letterlijke en operatoren bekijken</span><span class="sxs-lookup"><span data-stu-id="3a783-162">See supported literals and operators</span></span>](/azure/data-explorer/kusto/query/scalar-data-types/bool) |
| `int` | <span data-ttu-id="3a783-163">32-bits geheel getal</span><span class="sxs-lookup"><span data-stu-id="3a783-163">32-bit integer</span></span>  |
| `long` | <span data-ttu-id="3a783-164">64-bits geheel getal</span><span class="sxs-lookup"><span data-stu-id="3a783-164">64-bit integer</span></span> |

<span data-ttu-id="3a783-165">Als u meer wilt weten over deze gegevenstypen, [leest u meer over kusto scalaire gegevenstypen.](/azure/data-explorer/kusto/query/scalar-data-types/)</span><span class="sxs-lookup"><span data-stu-id="3a783-165">To learn more about these data types, [read about Kusto scalar data types](/azure/data-explorer/kusto/query/scalar-data-types/).</span></span>

## <a name="get-help-as-you-write-queries"></a><span data-ttu-id="3a783-166">Hulp krijgen tijdens het schrijven van query's</span><span class="sxs-lookup"><span data-stu-id="3a783-166">Get help as you write queries</span></span>
<span data-ttu-id="3a783-167">Profiteer van de volgende functionaliteit om query's sneller te schrijven:</span><span class="sxs-lookup"><span data-stu-id="3a783-167">Take advantage of the following functionality to write queries faster:</span></span>
- <span data-ttu-id="3a783-168">**Autosuggest**: terwijl u query's schrijft, biedt geavanceerd zoeken suggesties van IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="3a783-168">**Autosuggest**—as you write queries, advanced hunting provides suggestions from IntelliSense.</span></span> 
- <span data-ttu-id="3a783-169">**Schemastructuur:** een schemaweergave die de lijst met tabellen en de kolommen bevat, wordt naast uw werkgebied weergegeven.</span><span class="sxs-lookup"><span data-stu-id="3a783-169">**Schema tree**—a schema representation that includes the list of tables and their columns is provided next to your working area.</span></span> <span data-ttu-id="3a783-170">Plaats de muisaanwijzer op een item voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="3a783-170">For more information, hover over an item.</span></span> <span data-ttu-id="3a783-171">Dubbelklik op een item om het in te voegen in de queryeditor.</span><span class="sxs-lookup"><span data-stu-id="3a783-171">Double-click an item to insert it to the query editor.</span></span>
- <span data-ttu-id="3a783-172">**[Schemaverwijzing:](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** in-portalverwijzing met tabel- en kolombeschrijvingen, ondersteunde gebeurtenistypen `ActionType` (waarden) en voorbeeldquery's</span><span class="sxs-lookup"><span data-stu-id="3a783-172">**[Schema reference](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)**—in-portal reference with table and column descriptions as well as supported event types (`ActionType` values) and sample queries</span></span>

## <a name="work-with-multiple-queries-in-the-editor"></a><span data-ttu-id="3a783-173">Werken met meerdere query's in de editor</span><span class="sxs-lookup"><span data-stu-id="3a783-173">Work with multiple queries in the editor</span></span>
<span data-ttu-id="3a783-174">U kunt de queryeditor gebruiken om te experimenteren met meerdere query's.</span><span class="sxs-lookup"><span data-stu-id="3a783-174">You can use the query editor to experiment with multiple queries.</span></span> <span data-ttu-id="3a783-175">Meerdere query's gebruiken:</span><span class="sxs-lookup"><span data-stu-id="3a783-175">To use multiple queries:</span></span>

- <span data-ttu-id="3a783-176">Scheid elke query met een lege regel.</span><span class="sxs-lookup"><span data-stu-id="3a783-176">Separate each query with an empty line.</span></span>
- <span data-ttu-id="3a783-177">Plaats de cursor op een deel van een query om die query te selecteren voordat u deze uitvoert.</span><span class="sxs-lookup"><span data-stu-id="3a783-177">Place the cursor on any part of a query to select that query before running it.</span></span> <span data-ttu-id="3a783-178">Hiermee wordt alleen de geselecteerde query uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="3a783-178">This will run only the selected query.</span></span> <span data-ttu-id="3a783-179">Als u een andere query wilt uitvoeren, verplaatst u de cursor dienovereenkomstig en selecteert u **Query uitvoeren.**</span><span class="sxs-lookup"><span data-stu-id="3a783-179">To run another query, move the cursor accordingly and select **Run query**.</span></span>

![Afbeelding van de queryeditor met meerdere query's](../../media/mtp-ah/ah-multi-query.png)

## <a name="use-sample-queries"></a><span data-ttu-id="3a783-181">Voorbeeldquery's gebruiken</span><span class="sxs-lookup"><span data-stu-id="3a783-181">Use sample queries</span></span>

<span data-ttu-id="3a783-182">De **sectie Aan de** slag bevat een paar eenvoudige query's met veelgebruikte operatoren.</span><span class="sxs-lookup"><span data-stu-id="3a783-182">The **Get started** section provides a few simple queries using commonly used operators.</span></span> <span data-ttu-id="3a783-183">Probeer deze query's uit te proberen en kleine wijzigingen aan te brengen.</span><span class="sxs-lookup"><span data-stu-id="3a783-183">Try running these queries and making small modifications to them.</span></span>

![Afbeelding van geavanceerd zoekvenster](../../media/advanced-hunting-get-started.png)

>[!NOTE]
><span data-ttu-id="3a783-185">Naast de basisqueryvoorbeelden hebt u ook toegang tot gedeelde [query's](advanced-hunting-shared-queries.md) voor specifieke scenario's voor het zoeken naar bedreigingen.</span><span class="sxs-lookup"><span data-stu-id="3a783-185">Apart from the basic query samples, you can also access [shared queries](advanced-hunting-shared-queries.md) for specific threat hunting scenarios.</span></span> <span data-ttu-id="3a783-186">Verken de gedeelde query's aan de linkerkant van de pagina of de [GitHub-queryopslagplaats.](https://aka.ms/hunting-queries)</span><span class="sxs-lookup"><span data-stu-id="3a783-186">Explore the shared queries on the left side of the page or the [GitHub query repository](https://aka.ms/hunting-queries).</span></span>

## <a name="access-query-language-documentation"></a><span data-ttu-id="3a783-187">Documentatie van access-querytaal</span><span class="sxs-lookup"><span data-stu-id="3a783-187">Access query language documentation</span></span>

<span data-ttu-id="3a783-188">Zie [Kusto querytaaldocumentatie](/azure/kusto/query/)voor meer informatie over kusto-querytaal en ondersteunde operatoren.</span><span class="sxs-lookup"><span data-stu-id="3a783-188">For more information on Kusto query language and supported operators, see [Kusto query language documentation](/azure/kusto/query/).</span></span>

>[!NOTE]
><span data-ttu-id="3a783-189">Sommige tabellen in dit artikel zijn mogelijk niet beschikbaar in Microsoft Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="3a783-189">Some tables in this article might not be available in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="3a783-190">[Schakel Microsoft 365 Defender in om](m365d-enable.md) te zoeken naar bedreigingen met meer gegevensbronnen.</span><span class="sxs-lookup"><span data-stu-id="3a783-190">[Turn on Microsoft 365 Defender](m365d-enable.md) to hunt for threats using more data sources.</span></span> <span data-ttu-id="3a783-191">U kunt uw geavanceerde zoekwerkstromen verplaatsen van Microsoft Defender voor Eindpunt naar Microsoft 365 Defender door de stappen te volgen in Geavanceerde zoekquery's migreren van [Microsoft Defender voor Eindpunt.](advanced-hunting-migrate-from-mde.md)</span><span class="sxs-lookup"><span data-stu-id="3a783-191">You can move your advanced hunting workflows from Microsoft Defender for Endpoint to Microsoft 365 Defender by following the steps in [Migrate advanced hunting queries from Microsoft Defender for Endpoint](advanced-hunting-migrate-from-mde.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="3a783-192">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="3a783-192">Related topics</span></span>
- [<span data-ttu-id="3a783-193">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="3a783-193">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="3a783-194">Werken met queryresultaten</span><span class="sxs-lookup"><span data-stu-id="3a783-194">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="3a783-195">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="3a783-195">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="3a783-196">Opsporen op apparaten en in e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="3a783-196">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="3a783-197">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="3a783-197">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="3a783-198">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="3a783-198">Apply query best practices</span></span>](advanced-hunting-best-practices.md)