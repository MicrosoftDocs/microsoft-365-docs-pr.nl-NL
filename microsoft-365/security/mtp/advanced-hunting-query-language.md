---
title: De geavanceerde zoekquerytaal in Microsoft 365 Defender leren
description: Uw eerste zoekquery voor bedreigingen maken en meer te weten komen over veelgebruikte operatoren en andere aspecten van de geavanceerde zoekquerytaal
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, language, learn, first query, telemetry, events, telemetry, custom detections, schema, kusto, operators, data types, powershell download, query example
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
ms.openlocfilehash: 41341a2b5238485fc58021fe4af71cd5c635352c
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929800"
---
# <a name="learn-the-advanced-hunting-query-language"></a><span data-ttu-id="aa1b5-104">De geavanceerde zoekquerytaal leren</span><span class="sxs-lookup"><span data-stu-id="aa1b5-104">Learn the advanced hunting query language</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="aa1b5-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="aa1b5-105">**Applies to:**</span></span>
- <span data-ttu-id="aa1b5-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="aa1b5-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="aa1b5-107">Geavanceerd zoeken is gebaseerd op de [Kusto-querytaal.](https://docs.microsoft.com/azure/kusto/query/)</span><span class="sxs-lookup"><span data-stu-id="aa1b5-107">Advanced hunting is based on the [Kusto query language](https://docs.microsoft.com/azure/kusto/query/).</span></span> <span data-ttu-id="aa1b5-108">U kunt de operatoren en instructies van Kusto gebruiken om query's te maken op zoek naar informatie in een speciaal [schema.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="aa1b5-108">You can use Kusto operators and statements to construct queries that locate information in a specialized [schema](advanced-hunting-schema-tables.md).</span></span> <span data-ttu-id="aa1b5-109">Voer uw eerste query uit om deze concepten beter te begrijpen.</span><span class="sxs-lookup"><span data-stu-id="aa1b5-109">To understand these concepts better, run your first query.</span></span>

## <a name="try-your-first-query"></a><span data-ttu-id="aa1b5-110">Uw eerste query uitproberen</span><span class="sxs-lookup"><span data-stu-id="aa1b5-110">Try your first query</span></span>

<span data-ttu-id="aa1b5-111">Ga in het Microsoft 365-beveiligingscentrum naar **Op zoek naar** uw eerste query.</span><span class="sxs-lookup"><span data-stu-id="aa1b5-111">In Microsoft 365 security center, go to **Hunting** to run your first query.</span></span> <span data-ttu-id="aa1b5-112">Gebruik het volgende voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="aa1b5-112">Use the following example:</span></span>

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

<span data-ttu-id="aa1b5-113">**[Voer deze query uit op geavanceerde zoekopdrachten](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2TW0sCURSF93PQfxh8Moisp956yYIgQtLoMaYczJpbzkkTpN_et_dcdPQkcpjbmrXXWftyetKTQG5lKqmMpeB9IJksJJKZDOWdZ8wKeP5wvcm3OLgZbMXmXCmIxjnYIfcAVgYvRi8w3TnfsXEDGAG47pCCZXyP5ViO4KeNbt-Up-hEuJmB6lvButnY8XSL-cDl0M2I-GwxVX8Fe2H5zMzHiKjEVB0eEsnBrszfBIWuXOLrxCJ7VqEBfM3DWUYTkNKrv1p5y3X0jwetemzOQ_NSVuuXZ1c6aNTKRaN8VvWhY9n7OS-o6J5r7mYeQypdEKc1m1qfiqpjCSuspsDntt2J61bEvTlXls5AgQfFl5bHM_gr_BhO2RF1rztoBv2tWahrso_TtzkL93KGMGZVr2pe7eWR-xeZl91f_113UOsx3nDR4Y9j5R6kaCq8ajr_YWfFeedsd27L7it-Z6dAZyxsJq1d9-2ZOSzK3y2NVd8-zUPjtZaJnYsIH4Md7AmdeAcd2Cl1XoURc5PzXlfU8U9P54WcswL6t_TW9Q__qX-xygQAAA&runQuery=true&timeRangeId=week)**</span><span class="sxs-lookup"><span data-stu-id="aa1b5-113">**[Run this query in advanced hunting](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2TW0sCURSF93PQfxh8Moisp956yYIgQtLoMaYczJpbzkkTpN_et_dcdPQkcpjbmrXXWftyetKTQG5lKqmMpeB9IJksJJKZDOWdZ8wKeP5wvcm3OLgZbMXmXCmIxjnYIfcAVgYvRi8w3TnfsXEDGAG47pCCZXyP5ViO4KeNbt-Up-hEuJmB6lvButnY8XSL-cDl0M2I-GwxVX8Fe2H5zMzHiKjEVB0eEsnBrszfBIWuXOLrxCJ7VqEBfM3DWUYTkNKrv1p5y3X0jwetemzOQ_NSVuuXZ1c6aNTKRaN8VvWhY9n7OS-o6J5r7mYeQypdEKc1m1qfiqpjCSuspsDntt2J61bEvTlXls5AgQfFl5bHM_gr_BhO2RF1rztoBv2tWahrso_TtzkL93KGMGZVr2pe7eWR-xeZl91f_113UOsx3nDR4Y9j5R6kaCq8ajr_YWfFeedsd27L7it-Z6dAZyxsJq1d9-2ZOSzK3y2NVd8-zUPjtZaJnYsIH4Md7AmdeAcd2Cl1XoURc5PzXlfU8U9P54WcswL6t_TW9Q__qX-xygQAAA&runQuery=true&timeRangeId=week)**</span></span>

### <a name="describe-the-query-and-specify-the-tables-to-search"></a><span data-ttu-id="aa1b5-114">Beschrijf de query en geef de tabellen op waarin u wilt zoeken</span><span class="sxs-lookup"><span data-stu-id="aa1b5-114">Describe the query and specify the tables to search</span></span>
<span data-ttu-id="aa1b5-115">Aan het begin van de query is een korte opmerking toegevoegd om te beschrijven waarvoor deze is gebruikt.</span><span class="sxs-lookup"><span data-stu-id="aa1b5-115">A short comment has been added to the beginning of the query to describe what it is for.</span></span> <span data-ttu-id="aa1b5-116">Deze opmerking helpt als u later besluit de query op te slaan en te delen met anderen in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="aa1b5-116">This comment helps if you later decide to save the query and share it with others in your organization.</span></span> 

```kusto
// Finds PowerShell execution events that could involve a download
```

<span data-ttu-id="aa1b5-117">De query zelf begint meestal met een tabelnaam, gevolgd door een aantal elementen die beginnen met een s pipe ( `|` ).</span><span class="sxs-lookup"><span data-stu-id="aa1b5-117">The query itself will typically start with a table name followed by several elements that start with a pipe (`|`).</span></span> <span data-ttu-id="aa1b5-118">In dit voorbeeld maken we eerst een samenvoeging van twee tabellen en voegen we naar behoefte door de  `DeviceProcessEvents` `DeviceNetworkEvents` pipetelementen toe.</span><span class="sxs-lookup"><span data-stu-id="aa1b5-118">In this example, we start by creating a union of two tables,  `DeviceProcessEvents` and `DeviceNetworkEvents`, and add piped elements as needed.</span></span>

```kusto
union DeviceProcessEvents, DeviceNetworkEvents
```
### <a name="set-the-time-range"></a><span data-ttu-id="aa1b5-119">Het tijdsbereik instellen</span><span class="sxs-lookup"><span data-stu-id="aa1b5-119">Set the time range</span></span>
<span data-ttu-id="aa1b5-120">Het eerste element met de pipet is een tijdfilter dat is beperkt tot de vorige zeven dagen.</span><span class="sxs-lookup"><span data-stu-id="aa1b5-120">The first piped element is a time filter scoped to the previous seven days.</span></span> <span data-ttu-id="aa1b5-121">Door het tijdsbereik te beperken, zorgt u ervoor dat query's goed presteren, beheerbare resultaten retourneren en geen time-out optreden.</span><span class="sxs-lookup"><span data-stu-id="aa1b5-121">Limiting the time range helps ensure that queries perform well, return manageable results, and don't time out.</span></span>

```kusto
| where Timestamp > ago(7d)
```

### <a name="check-specific-processes"></a><span data-ttu-id="aa1b5-122">Specifieke processen controleren</span><span class="sxs-lookup"><span data-stu-id="aa1b5-122">Check specific processes</span></span>
<span data-ttu-id="aa1b5-123">Het tijdsbereik wordt direct gevolgd door een zoekopdracht naar namen van procesbestanden die de PowerShell-toepassing vertegenwoordigen.</span><span class="sxs-lookup"><span data-stu-id="aa1b5-123">The time range is immediately followed by a search for process file names representing the PowerShell application.</span></span>

```kusto
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
```

### <a name="search-for-specific-command-strings"></a><span data-ttu-id="aa1b5-124">Zoeken naar specifieke opdrachtreeksen</span><span class="sxs-lookup"><span data-stu-id="aa1b5-124">Search for specific command strings</span></span>
<span data-ttu-id="aa1b5-125">Later zoekt de query naar tekenreeksen in opdrachtregels die meestal worden gebruikt voor het downloaden van bestanden met PowerShell.</span><span class="sxs-lookup"><span data-stu-id="aa1b5-125">Afterwards, the query looks for strings in command lines that are typically used to download files using PowerShell.</span></span>

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

### <a name="customize-result-columns-and-length"></a><span data-ttu-id="aa1b5-126">Resultaatkolommen en lengte aanpassen</span><span class="sxs-lookup"><span data-stu-id="aa1b5-126">Customize result columns and length</span></span> 
<span data-ttu-id="aa1b5-127">Nu uw query duidelijk de gegevens identificeert die u wilt zoeken, kunt u definiëren hoe de resultaten eruit zien.</span><span class="sxs-lookup"><span data-stu-id="aa1b5-127">Now that your query clearly identifies the data you want to locate, you can define what the results look like.</span></span> <span data-ttu-id="aa1b5-128">`project` retourneert specifieke kolommen en `top` beperkt het aantal resultaten.</span><span class="sxs-lookup"><span data-stu-id="aa1b5-128">`project` returns specific columns, and `top` limits the number of results.</span></span> <span data-ttu-id="aa1b5-129">Deze operatoren zorgen ervoor dat de resultaten goed zijn opgemaakt en redelijk groot zijn en gemakkelijk kunnen worden verwerkt.</span><span class="sxs-lookup"><span data-stu-id="aa1b5-129">These operators help ensure the results are well-formatted and reasonably large and easy to process.</span></span>

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

<span data-ttu-id="aa1b5-130">Selecteer **Query uitvoeren om** de resultaten te bekijken.</span><span class="sxs-lookup"><span data-stu-id="aa1b5-130">Select **Run query** to see the results.</span></span> <span data-ttu-id="aa1b5-131">Gebruik het pictogram Uitvbreed rechtsboven in de queryeditor om u te richten op uw zoekquery en de resultaten.</span><span class="sxs-lookup"><span data-stu-id="aa1b5-131">Use the expand icon at the top right of the query editor to focus on your hunting query and the results.</span></span> 

![Afbeelding van het besturingselement Uitbreiden in de geavanceerde queryeditor](../../media/advanced-hunting-expand.png)

>[!TIP]
><span data-ttu-id="aa1b5-133">U kunt queryresultaten weergeven als grafieken en filters snel aanpassen.</span><span class="sxs-lookup"><span data-stu-id="aa1b5-133">You can view query results as charts and quickly adjust filters.</span></span> <span data-ttu-id="aa1b5-134">Meer informatie over [het werken met queryresultaten](advanced-hunting-query-results.md)</span><span class="sxs-lookup"><span data-stu-id="aa1b5-134">For guidance, [read about working with query results](advanced-hunting-query-results.md)</span></span>

## <a name="learn-common-query-operators"></a><span data-ttu-id="aa1b5-135">Algemene queryoperatoren</span><span class="sxs-lookup"><span data-stu-id="aa1b5-135">Learn common query operators</span></span>

<span data-ttu-id="aa1b5-136">U hebt zojuist uw eerste query uitgevoerd en hebt een algemeen idee van de onderdelen ervan.</span><span class="sxs-lookup"><span data-stu-id="aa1b5-136">You've just run your first query and have a general idea of its components.</span></span> <span data-ttu-id="aa1b5-137">Het is tijd om een backtrack te maken en enkele basisprincipes te leren.</span><span class="sxs-lookup"><span data-stu-id="aa1b5-137">It's time to backtrack slightly and learn some basics.</span></span> <span data-ttu-id="aa1b5-138">De kusto-querytaal die wordt gebruikt door geavanceerd zoeken ondersteunt een reeks operatoren, waaronder de volgende algemene operatoren.</span><span class="sxs-lookup"><span data-stu-id="aa1b5-138">The Kusto query language used by advanced hunting supports a range of operators, including the following common ones.</span></span>

| <span data-ttu-id="aa1b5-139">Operator</span><span class="sxs-lookup"><span data-stu-id="aa1b5-139">Operator</span></span> | <span data-ttu-id="aa1b5-140">Beschrijving en gebruik</span><span class="sxs-lookup"><span data-stu-id="aa1b5-140">Description and usage</span></span> |
|--|--|
| `where` | <span data-ttu-id="aa1b5-141">Filter een tabel op de subset rijen die voldoen aan een predicaat.</span><span class="sxs-lookup"><span data-stu-id="aa1b5-141">Filter a table to the subset of rows that satisfy a predicate.</span></span> |
| `summarize` | <span data-ttu-id="aa1b5-142">Maak een tabel die de inhoud van de invoertabel samentelt.</span><span class="sxs-lookup"><span data-stu-id="aa1b5-142">Produce a table that aggregates the content of the input table.</span></span> |
| `join` | <span data-ttu-id="aa1b5-143">Voeg de rijen van twee tabellen samen om een nieuwe tabel te maken door overeenkomende waarden uit de opgegeven kolommen uit elke tabel te combineren.</span><span class="sxs-lookup"><span data-stu-id="aa1b5-143">Merge the rows of two tables to form a new table by matching values of the specified column(s) from each table.</span></span> |
| `count` | <span data-ttu-id="aa1b5-144">Het aantal records in de invoerrecordset retourneren.</span><span class="sxs-lookup"><span data-stu-id="aa1b5-144">Return the number of records in the input record set.</span></span> |
| `top` | <span data-ttu-id="aa1b5-145">Retourneert de eerste N-records die zijn gesorteerd op de opgegeven kolommen.</span><span class="sxs-lookup"><span data-stu-id="aa1b5-145">Return the first N records sorted by the specified columns.</span></span> |
| `limit` | <span data-ttu-id="aa1b5-146">Maximaal het opgegeven aantal rijen retourneren.</span><span class="sxs-lookup"><span data-stu-id="aa1b5-146">Return up to the specified number of rows.</span></span> |
| `project` | <span data-ttu-id="aa1b5-147">Selecteer de kolommen die u wilt opnemen, wijzigen of neerzetten en voeg nieuwe berekende kolommen in.</span><span class="sxs-lookup"><span data-stu-id="aa1b5-147">Select the columns to include, rename or drop, and insert new computed columns.</span></span> |
| `extend` | <span data-ttu-id="aa1b5-148">Berekende kolommen maken en deze toevoegen aan de resultatenset.</span><span class="sxs-lookup"><span data-stu-id="aa1b5-148">Create calculated columns and append them to the result set.</span></span> |
| `makeset` |  <span data-ttu-id="aa1b5-149">Retourneert een dynamische (JSON)-matrix van de set unieke waarden die Expr in de groep neemt.</span><span class="sxs-lookup"><span data-stu-id="aa1b5-149">Return a dynamic (JSON) array of the set of distinct values that Expr takes in the group.</span></span> |
| `find` | <span data-ttu-id="aa1b5-150">Rijen zoeken die overeenkomen met een predicaat in een set tabellen.</span><span class="sxs-lookup"><span data-stu-id="aa1b5-150">Find rows that match a predicate across a set of tables.</span></span> |

<span data-ttu-id="aa1b5-151">Als u een live voorbeeld van deze operators wilt zien, kunt u ze uitvoeren vanuit de sectie **Aan** de slag in geavanceerd zoeken.</span><span class="sxs-lookup"><span data-stu-id="aa1b5-151">To see a live example of these operators, run them from the **Get started** section in advanced hunting.</span></span>

## <a name="understand-data-types"></a><span data-ttu-id="aa1b5-152">Gegevenstypen</span><span class="sxs-lookup"><span data-stu-id="aa1b5-152">Understand data types</span></span>

<span data-ttu-id="aa1b5-153">Geavanceerd zoeken ondersteunt Kusto-gegevenstypen, waaronder de volgende veelgebruikte typen:</span><span class="sxs-lookup"><span data-stu-id="aa1b5-153">Advanced hunting supports Kusto data types, including the following common types:</span></span>

| <span data-ttu-id="aa1b5-154">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="aa1b5-154">Data type</span></span> | <span data-ttu-id="aa1b5-155">Gevolgen voor beschrijving en query's</span><span class="sxs-lookup"><span data-stu-id="aa1b5-155">Description and query implications</span></span> |
|--|--|
| `datetime` | <span data-ttu-id="aa1b5-156">Gegevens- en tijdgegevens die meestal tijdstempels van gebeurtenissen vertegenwoordigen.</span><span class="sxs-lookup"><span data-stu-id="aa1b5-156">Data and time information typically representing event timestamps.</span></span> [<span data-ttu-id="aa1b5-157">Ondersteunde datum-/tijdnota's bekijken</span><span class="sxs-lookup"><span data-stu-id="aa1b5-157">See supported datetime formats</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/datetime) |
| `string` | <span data-ttu-id="aa1b5-158">Tekenreeks in UTF-8 tussen enkele aanhalingstekens ( `'` ) of dubbele aanhalingstekens ( `"` ).</span><span class="sxs-lookup"><span data-stu-id="aa1b5-158">Character string in UTF-8 enclosed in single quotes (`'`) or double quotes (`"`).</span></span> [<span data-ttu-id="aa1b5-159">Meer informatie over tekenreeksen</span><span class="sxs-lookup"><span data-stu-id="aa1b5-159">Read more about strings</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/string) |
| `bool` | <span data-ttu-id="aa1b5-160">Dit gegevenstype ondersteunt `true` of `false` wordt ondersteund.</span><span class="sxs-lookup"><span data-stu-id="aa1b5-160">This data type supports `true` or `false` states.</span></span> [<span data-ttu-id="aa1b5-161">Ondersteunde letterlijke letterlijke en operatoren bekijken</span><span class="sxs-lookup"><span data-stu-id="aa1b5-161">See supported literals and operators</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/bool) |
| `int` | <span data-ttu-id="aa1b5-162">32-bits geheel getal</span><span class="sxs-lookup"><span data-stu-id="aa1b5-162">32-bit integer</span></span>  |
| `long` | <span data-ttu-id="aa1b5-163">64-bits geheel getal</span><span class="sxs-lookup"><span data-stu-id="aa1b5-163">64-bit integer</span></span> |

<span data-ttu-id="aa1b5-164">Meer informatie over deze gegevenstypen kunt u lezen in meer informatie [over scalaire kusto-gegevenstypen.](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/)</span><span class="sxs-lookup"><span data-stu-id="aa1b5-164">To learn more about these data types, [read about Kusto scalar data types](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/).</span></span>

## <a name="get-help-as-you-write-queries"></a><span data-ttu-id="aa1b5-165">Hulp krijgen tijdens het schrijven van query's</span><span class="sxs-lookup"><span data-stu-id="aa1b5-165">Get help as you write queries</span></span>
<span data-ttu-id="aa1b5-166">Maak gebruik van de volgende functionaliteit om sneller query's te schrijven:</span><span class="sxs-lookup"><span data-stu-id="aa1b5-166">Take advantage of the following functionality to write queries faster:</span></span>
- <span data-ttu-id="aa1b5-167">**AutoSuggest:** tijdens het schrijven van query's geeft geavanceerd zoeken suggesties van IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="aa1b5-167">**Autosuggest**—as you write queries, advanced hunting provides suggestions from IntelliSense.</span></span> 
- <span data-ttu-id="aa1b5-168">**Schemastructuur:** een schemaweergave met de lijst met tabellen en de kolommen naast uw werkgebied.</span><span class="sxs-lookup"><span data-stu-id="aa1b5-168">**Schema tree**—a schema representation that includes the list of tables and their columns is provided next to your working area.</span></span> <span data-ttu-id="aa1b5-169">Plaats de muisaanwijzer op een item voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="aa1b5-169">For more information, hover over an item.</span></span> <span data-ttu-id="aa1b5-170">Dubbelklik op een item om dit in te voegen in de queryeditor.</span><span class="sxs-lookup"><span data-stu-id="aa1b5-170">Double-click an item to insert it to the query editor.</span></span>
- <span data-ttu-id="aa1b5-171">**[Schemaverwijzing:](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** in-portalverwijzing met tabel- en kolombeschrijvingen en ondersteunde gebeurtenistypen `ActionType` (waarden) en voorbeeldquery's</span><span class="sxs-lookup"><span data-stu-id="aa1b5-171">**[Schema reference](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)**—in-portal reference with table and column descriptions as well as supported event types (`ActionType` values) and sample queries</span></span>

## <a name="work-with-multiple-queries-in-the-editor"></a><span data-ttu-id="aa1b5-172">Werken met meerdere query's in de editor</span><span class="sxs-lookup"><span data-stu-id="aa1b5-172">Work with multiple queries in the editor</span></span>
<span data-ttu-id="aa1b5-173">U kunt de queryeditor gebruiken om te experimenteren met meerdere query's.</span><span class="sxs-lookup"><span data-stu-id="aa1b5-173">You can use the query editor to experiment with multiple queries.</span></span> <span data-ttu-id="aa1b5-174">Meerdere query's gebruiken:</span><span class="sxs-lookup"><span data-stu-id="aa1b5-174">To use multiple queries:</span></span>

- <span data-ttu-id="aa1b5-175">Scheidt elke query met een lege regel.</span><span class="sxs-lookup"><span data-stu-id="aa1b5-175">Separate each query with an empty line.</span></span>
- <span data-ttu-id="aa1b5-176">Plaats de cursor op een deel van een query om de query te selecteren voordat u deze uitvoert.</span><span class="sxs-lookup"><span data-stu-id="aa1b5-176">Place the cursor on any part of a query to select that query before running it.</span></span> <span data-ttu-id="aa1b5-177">Hiermee wordt alleen de geselecteerde query uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="aa1b5-177">This will run only the selected query.</span></span> <span data-ttu-id="aa1b5-178">Als u een andere query wilt uitvoeren, verplaatst u de cursor dienovereenkomstig en **selecteert u Query uitvoeren.**</span><span class="sxs-lookup"><span data-stu-id="aa1b5-178">To run another query, move the cursor accordingly and select **Run query**.</span></span>

![Afbeelding van de queryeditor met meerdere query's](../../media/mtp-ah/ah-multi-query.png)

## <a name="use-sample-queries"></a><span data-ttu-id="aa1b5-180">Voorbeeldquery's gebruiken</span><span class="sxs-lookup"><span data-stu-id="aa1b5-180">Use sample queries</span></span>

<span data-ttu-id="aa1b5-181">De **sectie Aan de** slag bevat een paar eenvoudige query's met veelgebruikte operatoren.</span><span class="sxs-lookup"><span data-stu-id="aa1b5-181">The **Get started** section provides a few simple queries using commonly used operators.</span></span> <span data-ttu-id="aa1b5-182">Probeer deze query's uit te kunnen uitvoeren en er kleine wijzigingen in aan te brengen.</span><span class="sxs-lookup"><span data-stu-id="aa1b5-182">Try running these queries and making small modifications to them.</span></span>

![Afbeelding van geavanceerd zoekvenster](../../media/advanced-hunting-get-started.png)

>[!NOTE]
><span data-ttu-id="aa1b5-184">Afgezien van de basisqueryvoorbeelden, hebt u ook toegang tot [gedeelde query's](advanced-hunting-shared-queries.md) voor specifieke scenario's voor het zoeken naar bedreigingen.</span><span class="sxs-lookup"><span data-stu-id="aa1b5-184">Apart from the basic query samples, you can also access [shared queries](advanced-hunting-shared-queries.md) for specific threat hunting scenarios.</span></span> <span data-ttu-id="aa1b5-185">Verken de gedeelde query's aan de linkerkant van de pagina of de [GitHub-querybibliotheek.](https://aka.ms/hunting-queries)</span><span class="sxs-lookup"><span data-stu-id="aa1b5-185">Explore the shared queries on the left side of the page or the [GitHub query repository](https://aka.ms/hunting-queries).</span></span>

## <a name="access-query-language-documentation"></a><span data-ttu-id="aa1b5-186">Taaldocumentatie voor Access-query's</span><span class="sxs-lookup"><span data-stu-id="aa1b5-186">Access query language documentation</span></span>

<span data-ttu-id="aa1b5-187">Zie de kusto-querytaaldocumentatie voor meer informatie over de [Kusto-querytaal en ondersteunde operatoren.](https://docs.microsoft.com/azure/kusto/query/)</span><span class="sxs-lookup"><span data-stu-id="aa1b5-187">For more information on Kusto query language and supported operators, see [Kusto query language documentation](https://docs.microsoft.com/azure/kusto/query/).</span></span>

## <a name="related-topics"></a><span data-ttu-id="aa1b5-188">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="aa1b5-188">Related topics</span></span>
- [<span data-ttu-id="aa1b5-189">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="aa1b5-189">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="aa1b5-190">Werken met queryresultaten</span><span class="sxs-lookup"><span data-stu-id="aa1b5-190">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="aa1b5-191">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="aa1b5-191">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="aa1b5-192">Opsporen op apparaten en in e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="aa1b5-192">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="aa1b5-193">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="aa1b5-193">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="aa1b5-194">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="aa1b5-194">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
