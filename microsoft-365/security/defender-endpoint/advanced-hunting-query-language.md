---
title: De geavanceerde zoekquerytaal leren
description: Maak uw eerste zoekquery voor bedreigingen en leer meer over veelgebruikte operatoren en andere aspecten van de geavanceerde zoekquerytaal
keywords: advanced hunting, threat hunting, cyber threat hunting, mdatp, microsoft defender atp, wdatp search, query, language, learn, first query, telemetry, events, telemetry, custom detections, schema, kusto, operators, data types
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 21cea1f661de294aea41ea2c4db21b1aca8a0eec
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058825"
---
# <a name="learn-the-advanced-hunting-query-language"></a><span data-ttu-id="11a36-104">De geavanceerde zoekquerytaal leren</span><span class="sxs-lookup"><span data-stu-id="11a36-104">Learn the advanced hunting query language</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="11a36-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="11a36-105">**Applies to:**</span></span>
- [<span data-ttu-id="11a36-106">Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="11a36-106">Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

> <span data-ttu-id="11a36-107">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="11a36-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="11a36-108">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="11a36-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

<span data-ttu-id="11a36-109">Geavanceerd zoeken is gebaseerd op de [querytaal Kusto.](https://docs.microsoft.com/azure/kusto/query/)</span><span class="sxs-lookup"><span data-stu-id="11a36-109">Advanced hunting is based on the [Kusto query language](https://docs.microsoft.com/azure/kusto/query/).</span></span> <span data-ttu-id="11a36-110">U kunt Kusto-operatoren en instructies gebruiken om query's te maken die informatie zoeken in een gespecialiseerd [schema.](advanced-hunting-schema-reference.md)</span><span class="sxs-lookup"><span data-stu-id="11a36-110">You can use Kusto operators and statements to construct queries that locate information in a specialized [schema](advanced-hunting-schema-reference.md).</span></span> <span data-ttu-id="11a36-111">Als u deze concepten beter wilt begrijpen, kunt u de eerste query uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="11a36-111">To understand these concepts better, run your first query.</span></span>

## <a name="try-your-first-query"></a><span data-ttu-id="11a36-112">Probeer uw eerste query</span><span class="sxs-lookup"><span data-stu-id="11a36-112">Try your first query</span></span>

<span data-ttu-id="11a36-113">Ga in het Microsoft Defender-beveiligingscentrum naar **Geavanceerd zoeken om** uw eerste query uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="11a36-113">In Microsoft Defender Security Center, go to **Advanced hunting** to run your first query.</span></span> <span data-ttu-id="11a36-114">Gebruik het volgende voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="11a36-114">Use the following example:</span></span>

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
<span data-ttu-id="11a36-115">**[Voer deze query uit in geavanceerd zoeken](https://securitycenter.windows.com/hunting?query=H4sIAAAAAAAEAI2TT0vDQBDF5yz4HUJPFcTqyZsXqyCIBFvxKNGWtpo_NVlbC8XP7m8mado0K5Zls8nkzdu3b2Z70pNAbmUmqYyk4D2UTJYyllwGMmWNGQHrN_NNvsSBzUBrbMFMiWieAx3xDEBl4GL4AuNd8B0bNgARENcdUmIZ3yM5liPwac3bN-YZPGPU5ET1rWDc7Ox4uod8YDp4MzI-GkjlX4Ne2nly0zEkKzFWh4ZE5sSuTN8Ehq5couvEMnvmUAhez-HsRBMipVa_W_OG6vEfGtT12JRHpqV064e1Kx04NsxFzXxW1aFjp_djXmDRPbfY3XMMcLogTz2bWZ2KqmIJI6q6wKe2WYnrRsa9KVeU9kCBBo2v7BzPxF_Bx2DKiqh63SGoRoc6Njti48z_yL71XHQAcgAur6rXRpcqH3l-4knZF23Utsbq2MircEqmw-G__xR1TdZ1r7zb7XLezmx3etkvGr-ze6NdGdW92azUfpcdluWvr-aqbh_nofnqcWI3aYyOsBV7giduRUO7187LMKTT5rxvHHX80_t8IeeMgLquvL7-Ak3q-kz8BAAA&runQuery=true&timeRangeId=week)**</span><span class="sxs-lookup"><span data-stu-id="11a36-115">**[Run this query in advanced hunting](https://securitycenter.windows.com/hunting?query=H4sIAAAAAAAEAI2TT0vDQBDF5yz4HUJPFcTqyZsXqyCIBFvxKNGWtpo_NVlbC8XP7m8mado0K5Zls8nkzdu3b2Z70pNAbmUmqYyk4D2UTJYyllwGMmWNGQHrN_NNvsSBzUBrbMFMiWieAx3xDEBl4GL4AuNd8B0bNgARENcdUmIZ3yM5liPwac3bN-YZPGPU5ET1rWDc7Ox4uod8YDp4MzI-GkjlX4Ne2nly0zEkKzFWh4ZE5sSuTN8Ehq5couvEMnvmUAhez-HsRBMipVa_W_OG6vEfGtT12JRHpqV064e1Kx04NsxFzXxW1aFjp_djXmDRPbfY3XMMcLogTz2bWZ2KqmIJI6q6wKe2WYnrRsa9KVeU9kCBBo2v7BzPxF_Bx2DKiqh63SGoRoc6Njti48z_yL71XHQAcgAur6rXRpcqH3l-4knZF23Utsbq2MircEqmw-G__xR1TdZ1r7zb7XLezmx3etkvGr-ze6NdGdW92azUfpcdluWvr-aqbh_nofnqcWI3aYyOsBV7giduRUO7187LMKTT5rxvHHX80_t8IeeMgLquvL7-Ak3q-kz8BAAA&runQuery=true&timeRangeId=week)**</span></span>

### <a name="describe-the-query-and-specify-the-tables-to-search"></a><span data-ttu-id="11a36-116">Beschrijf de query en geef de tabellen op die u wilt zoeken</span><span class="sxs-lookup"><span data-stu-id="11a36-116">Describe the query and specify the tables to search</span></span>
<span data-ttu-id="11a36-117">Er is een korte opmerking toegevoegd aan het begin van de query om te beschrijven waar deze voor is.</span><span class="sxs-lookup"><span data-stu-id="11a36-117">A short comment has been added to the beginning of the query to describe what it is for.</span></span> <span data-ttu-id="11a36-118">Deze opmerking helpt als u later besluit de query op te slaan en deze te delen met anderen in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="11a36-118">This comment helps if you later decide to save the query and share it with others in your organization.</span></span>

```kusto
// Finds PowerShell execution events that could involve a download
```
<span data-ttu-id="11a36-119">De query zelf begint meestal met een tabelnaam, gevolgd door verschillende elementen die beginnen met een pijp ( `|` ).</span><span class="sxs-lookup"><span data-stu-id="11a36-119">The query itself will typically start with a table name followed by several elements that start with a pipe (`|`).</span></span> <span data-ttu-id="11a36-120">In dit voorbeeld beginnen we met het maken van een samenvoeging van twee tabellen en , en voegen we zo nodig  `DeviceProcessEvents` `DeviceNetworkEvents` gepijpte elementen toe.</span><span class="sxs-lookup"><span data-stu-id="11a36-120">In this example, we start by creating a union of two tables,  `DeviceProcessEvents` and `DeviceNetworkEvents`, and add piped elements as needed.</span></span>

```kusto
union DeviceProcessEvents, DeviceNetworkEvents
```
### <a name="set-the-time-range"></a><span data-ttu-id="11a36-121">Het tijdsbereik instellen</span><span class="sxs-lookup"><span data-stu-id="11a36-121">Set the time range</span></span>
<span data-ttu-id="11a36-122">Het eerste piped-element is een tijdfilter dat is beperkt tot de afgelopen zeven dagen.</span><span class="sxs-lookup"><span data-stu-id="11a36-122">The first piped element is a time filter scoped to the previous seven days.</span></span> <span data-ttu-id="11a36-123">Als u het tijdbereik beperkt, zorgt u ervoor dat query's goed presteren, beheersbare resultaten retourneren en geen time-out maken.</span><span class="sxs-lookup"><span data-stu-id="11a36-123">Limiting the time range helps ensure that queries perform well, return manageable results, and don't time out.</span></span>

```kusto
| where Timestamp > ago(7d)
```

### <a name="check-specific-processes"></a><span data-ttu-id="11a36-124">Specifieke processen controleren</span><span class="sxs-lookup"><span data-stu-id="11a36-124">Check specific processes</span></span>
<span data-ttu-id="11a36-125">Het tijdbereik wordt onmiddellijk gevolgd door een zoekopdracht naar de namen van procesbestanden die de PowerShell-toepassing vertegenwoordigen.</span><span class="sxs-lookup"><span data-stu-id="11a36-125">The time range is immediately followed by a search for process file names representing the PowerShell application.</span></span>

```kusto
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
```

### <a name="search-for-specific-command-strings"></a><span data-ttu-id="11a36-126">Specifieke opdrachtreeksen zoeken</span><span class="sxs-lookup"><span data-stu-id="11a36-126">Search for specific command strings</span></span>
<span data-ttu-id="11a36-127">Daarna zoekt de query naar tekenreeksen in opdrachtregels die gewoonlijk worden gebruikt om bestanden te downloaden met PowerShell.</span><span class="sxs-lookup"><span data-stu-id="11a36-127">Afterwards, the query looks for strings in command lines that are typically used to download files using PowerShell.</span></span>

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

### <a name="customize-result-columns-and-length"></a><span data-ttu-id="11a36-128">Resultaatkolommen en lengte aanpassen</span><span class="sxs-lookup"><span data-stu-id="11a36-128">Customize result columns and length</span></span> 
<span data-ttu-id="11a36-129">Nu de query duidelijk aangeeft welke gegevens u wilt zoeken, kunt u definiëren hoe de resultaten eruit zien.</span><span class="sxs-lookup"><span data-stu-id="11a36-129">Now that your query clearly identifies the data you want to locate, you can define what the results look like.</span></span> <span data-ttu-id="11a36-130">`project` geeft als resultaat specifieke kolommen en `top` beperkt het aantal resultaten.</span><span class="sxs-lookup"><span data-stu-id="11a36-130">`project` returns specific columns, and `top` limits the number of results.</span></span> <span data-ttu-id="11a36-131">Deze operatoren helpen ervoor te zorgen dat de resultaten goed zijn opgemaakt en redelijk groot en eenvoudig te verwerken zijn.</span><span class="sxs-lookup"><span data-stu-id="11a36-131">These operators help ensure the results are well-formatted and reasonably large and easy to process.</span></span>

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

<span data-ttu-id="11a36-132">Selecteer **Query uitvoeren om** de resultaten te zien.</span><span class="sxs-lookup"><span data-stu-id="11a36-132">Select **Run query** to see the results.</span></span> <span data-ttu-id="11a36-133">Gebruik het pictogram Uitvvuiten rechtsboven in de queryeditor om de focus te leggen op uw query en de resultaten.</span><span class="sxs-lookup"><span data-stu-id="11a36-133">Use the expand icon at the top right of the query editor to focus on your hunting query and the results.</span></span> 

![Afbeelding van het besturingselement Uitvvv in de geavanceerde queryeditor](images/advanced-hunting-expand.png)

>[!TIP]
><span data-ttu-id="11a36-135">U kunt queryresultaten weergeven als grafieken en snel filters aanpassen.</span><span class="sxs-lookup"><span data-stu-id="11a36-135">You can view query results as charts and quickly adjust filters.</span></span> <span data-ttu-id="11a36-136">Lees voor meer [informatie over het werken met queryresultaten](advanced-hunting-query-results.md)</span><span class="sxs-lookup"><span data-stu-id="11a36-136">For guidance, [read about working with query results](advanced-hunting-query-results.md)</span></span>

## <a name="learn-common-query-operators-for-advanced-hunting"></a><span data-ttu-id="11a36-137">Veelgebruikte queryoperatoren voor geavanceerd zoeken</span><span class="sxs-lookup"><span data-stu-id="11a36-137">Learn common query operators for advanced hunting</span></span>

<span data-ttu-id="11a36-138">U hebt zojuist uw eerste query uitgevoerd en hebt een algemeen idee van de onderdelen.</span><span class="sxs-lookup"><span data-stu-id="11a36-138">You've just run your first query and have a general idea of its components.</span></span> <span data-ttu-id="11a36-139">Het is tijd om iets terug te keren en enkele basisbeginselen te leren.</span><span class="sxs-lookup"><span data-stu-id="11a36-139">It's time to backtrack slightly and learn some basics.</span></span> <span data-ttu-id="11a36-140">De kusto-querytaal die wordt gebruikt door geavanceerde jagen ondersteunt een reeks operatoren, waaronder de volgende veelgebruikte.</span><span class="sxs-lookup"><span data-stu-id="11a36-140">The Kusto query language used by advanced hunting supports a range of operators, including the following common ones.</span></span>

| <span data-ttu-id="11a36-141">Operator</span><span class="sxs-lookup"><span data-stu-id="11a36-141">Operator</span></span> | <span data-ttu-id="11a36-142">Beschrijving en gebruik</span><span class="sxs-lookup"><span data-stu-id="11a36-142">Description and usage</span></span> |
|--|--|
| `where` | <span data-ttu-id="11a36-143">Een tabel filteren op de subset van rijen die voldoen aan een predicaat.</span><span class="sxs-lookup"><span data-stu-id="11a36-143">Filter a table to the subset of rows that satisfy a predicate.</span></span> |
| `summarize` | <span data-ttu-id="11a36-144">Een tabel maken die de inhoud van de invoertabel aggregeert.</span><span class="sxs-lookup"><span data-stu-id="11a36-144">Produce a table that aggregates the content of the input table.</span></span> |
| `join` | <span data-ttu-id="11a36-145">Voeg de rijen van twee tabellen samen om een nieuwe tabel te vormen door de waarden van de opgegeven kolom(en) uit elke tabel te koppelen.</span><span class="sxs-lookup"><span data-stu-id="11a36-145">Merge the rows of two tables to form a new table by matching values of the specified column(s) from each table.</span></span> |
| `count` | <span data-ttu-id="11a36-146">Het aantal records in de invoerrecordset retourneren.</span><span class="sxs-lookup"><span data-stu-id="11a36-146">Return the number of records in the input record set.</span></span> |
| `top` | <span data-ttu-id="11a36-147">Retourneert de eerste N-records gesorteerd op de opgegeven kolommen.</span><span class="sxs-lookup"><span data-stu-id="11a36-147">Return the first N records sorted by the specified columns.</span></span> |
| `limit` | <span data-ttu-id="11a36-148">Ga terug naar het opgegeven aantal rijen.</span><span class="sxs-lookup"><span data-stu-id="11a36-148">Return up to the specified number of rows.</span></span> |
| `project` | <span data-ttu-id="11a36-149">Selecteer de kolommen die u wilt opnemen, de naam wilt wijzigen of neerzetten en voeg nieuwe berekende kolommen in.</span><span class="sxs-lookup"><span data-stu-id="11a36-149">Select the columns to include, rename or drop, and insert new computed columns.</span></span> |
| `extend` | <span data-ttu-id="11a36-150">Maak berekende kolommen en wijs deze toe aan de resultatenset.</span><span class="sxs-lookup"><span data-stu-id="11a36-150">Create calculated columns and append them to the result set.</span></span> |
| `makeset` |  <span data-ttu-id="11a36-151">Retourneert een dynamische matrix (JSON) van de set afzonderlijke waarden die Expr in de groep op zich neemt.</span><span class="sxs-lookup"><span data-stu-id="11a36-151">Return a dynamic (JSON) array of the set of distinct values that Expr takes in the group.</span></span> |
| `find` | <span data-ttu-id="11a36-152">Rijen zoeken die overeenkomen met een predicaat in een set tabellen.</span><span class="sxs-lookup"><span data-stu-id="11a36-152">Find rows that match a predicate across a set of tables.</span></span> |

<span data-ttu-id="11a36-153">Als u een livevoorbeeld van deze operatoren wilt zien, kunt u deze uitvoeren vanuit de sectie Aan **de** slag van de geavanceerde pagina.</span><span class="sxs-lookup"><span data-stu-id="11a36-153">To see a live example of these operators, run them from the **Get started** section of the advanced hunting page.</span></span>

## <a name="understand-data-types"></a><span data-ttu-id="11a36-154">Gegevenstypen begrijpen</span><span class="sxs-lookup"><span data-stu-id="11a36-154">Understand data types</span></span>

<span data-ttu-id="11a36-155">Geavanceerde jacht ondersteunt Kusto-gegevenstypen, waaronder de volgende veelvoorkomende typen:</span><span class="sxs-lookup"><span data-stu-id="11a36-155">Advanced hunting supports Kusto data types, including the following common types:</span></span>

| <span data-ttu-id="11a36-156">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="11a36-156">Data type</span></span> | <span data-ttu-id="11a36-157">Beschrijving en query-implicaties</span><span class="sxs-lookup"><span data-stu-id="11a36-157">Description and query implications</span></span> |
|--|--|
| `datetime` | <span data-ttu-id="11a36-158">Gegevens- en tijdgegevens die meestal gebeurtenistijdstempels vertegenwoordigen.</span><span class="sxs-lookup"><span data-stu-id="11a36-158">Data and time information typically representing event timestamps.</span></span> [<span data-ttu-id="11a36-159">Ondersteunde datumtime-indelingen bekijken</span><span class="sxs-lookup"><span data-stu-id="11a36-159">See supported datetime formats</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/datetime) |
| `string` | <span data-ttu-id="11a36-160">Tekenreeks in UTF-8 tussen enkele aanhalingstekens ( `'` ) of dubbele aanhalingstekens ( `"` ).</span><span class="sxs-lookup"><span data-stu-id="11a36-160">Character string in UTF-8 enclosed in single quotes (`'`) or double quotes (`"`).</span></span> [<span data-ttu-id="11a36-161">Meer informatie over tekenreeksen</span><span class="sxs-lookup"><span data-stu-id="11a36-161">Read more about strings</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/string) |
| `bool` | <span data-ttu-id="11a36-162">Dit gegevenstype ondersteunt `true` of `false` geeft deze op.</span><span class="sxs-lookup"><span data-stu-id="11a36-162">This data type supports `true` or `false` states.</span></span> [<span data-ttu-id="11a36-163">Ondersteunde letterlijke en operatoren bekijken</span><span class="sxs-lookup"><span data-stu-id="11a36-163">See supported literals and operators</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/bool) |
| `int` | <span data-ttu-id="11a36-164">32-bits geheel getal</span><span class="sxs-lookup"><span data-stu-id="11a36-164">32-bit integer</span></span>  |
| `long` | <span data-ttu-id="11a36-165">64-bits geheel getal</span><span class="sxs-lookup"><span data-stu-id="11a36-165">64-bit integer</span></span> |

<span data-ttu-id="11a36-166">Als u meer wilt weten over deze gegevenstypen, [leest u meer over kusto scalaire gegevenstypen.](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/)</span><span class="sxs-lookup"><span data-stu-id="11a36-166">To learn more about these data types, [read about Kusto scalar data types](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/).</span></span>

## <a name="get-help-as-you-write-queries"></a><span data-ttu-id="11a36-167">Hulp krijgen tijdens het schrijven van query's</span><span class="sxs-lookup"><span data-stu-id="11a36-167">Get help as you write queries</span></span>
<span data-ttu-id="11a36-168">Profiteer van de volgende functionaliteit om query's sneller te schrijven:</span><span class="sxs-lookup"><span data-stu-id="11a36-168">Take advantage of the following functionality to write queries faster:</span></span>

- <span data-ttu-id="11a36-169">**Autosuggest**: terwijl u query's schrijft, biedt geavanceerd zoeken suggesties van IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="11a36-169">**Autosuggest**—as you write queries, advanced hunting provides suggestions from IntelliSense.</span></span>
- <span data-ttu-id="11a36-170">**Schemastructuur:** een schemaweergave die de lijst met tabellen en de kolommen bevat, wordt naast uw werkgebied weergegeven.</span><span class="sxs-lookup"><span data-stu-id="11a36-170">**Schema tree**—a schema representation that includes the list of tables and their columns is provided next to your working area.</span></span> <span data-ttu-id="11a36-171">Plaats de muisaanwijzer op een item voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="11a36-171">For more information, hover over an item.</span></span> <span data-ttu-id="11a36-172">Dubbelklik op een item om het in te voegen in de queryeditor.</span><span class="sxs-lookup"><span data-stu-id="11a36-172">Double-click an item to insert it to the query editor.</span></span>
- <span data-ttu-id="11a36-173">**[Schemaverwijzing:](advanced-hunting-schema-reference.md#get-schema-information-in-the-security-center)** in-portalverwijzing met tabel- en kolombeschrijvingen, ondersteunde gebeurtenistypen `ActionType` (waarden) en voorbeeldquery's</span><span class="sxs-lookup"><span data-stu-id="11a36-173">**[Schema reference](advanced-hunting-schema-reference.md#get-schema-information-in-the-security-center)**—in-portal reference with table and column descriptions as well as supported event types (`ActionType` values) and sample queries</span></span>

## <a name="work-with-multiple-queries-in-the-editor"></a><span data-ttu-id="11a36-174">Werken met meerdere query's in de editor</span><span class="sxs-lookup"><span data-stu-id="11a36-174">Work with multiple queries in the editor</span></span>
<span data-ttu-id="11a36-175">U kunt de queryeditor gebruiken om te experimenteren met meerdere query's.</span><span class="sxs-lookup"><span data-stu-id="11a36-175">You can use the query editor to experiment with multiple queries.</span></span> <span data-ttu-id="11a36-176">Meerdere query's gebruiken:</span><span class="sxs-lookup"><span data-stu-id="11a36-176">To use multiple queries:</span></span>

- <span data-ttu-id="11a36-177">Scheid elke query met een lege regel.</span><span class="sxs-lookup"><span data-stu-id="11a36-177">Separate each query with an empty line.</span></span>
- <span data-ttu-id="11a36-178">Plaats de cursor op een deel van een query om die query te selecteren voordat u deze uitvoert.</span><span class="sxs-lookup"><span data-stu-id="11a36-178">Place the cursor on any part of a query to select that query before running it.</span></span> <span data-ttu-id="11a36-179">Hiermee wordt alleen de geselecteerde query uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="11a36-179">This will run only the selected query.</span></span> <span data-ttu-id="11a36-180">Als u een andere query wilt uitvoeren, verplaatst u de cursor dienovereenkomstig en selecteert u **Query uitvoeren.**</span><span class="sxs-lookup"><span data-stu-id="11a36-180">To run another query, move the cursor accordingly and select **Run query**.</span></span>

<span data-ttu-id="11a36-181">![Afbeelding van de geavanceerde queryeditor met meerdere query's ](images/ah-multi-query.png)
 _Queryeditor met meerdere query's_</span><span class="sxs-lookup"><span data-stu-id="11a36-181">![Image of the advanced hunting query editor with multiple queries](images/ah-multi-query.png)
_Query editor with multiple queries_</span></span>

## <a name="use-sample-queries"></a><span data-ttu-id="11a36-182">Voorbeeldquery's gebruiken</span><span class="sxs-lookup"><span data-stu-id="11a36-182">Use sample queries</span></span>

<span data-ttu-id="11a36-183">De **sectie Aan de** slag bevat een paar eenvoudige query's met veelgebruikte operatoren.</span><span class="sxs-lookup"><span data-stu-id="11a36-183">The **Get started** section provides a few simple queries using commonly used operators.</span></span> <span data-ttu-id="11a36-184">Probeer deze query's uit te proberen en kleine wijzigingen aan te brengen.</span><span class="sxs-lookup"><span data-stu-id="11a36-184">Try running these queries and making small modifications to them.</span></span>

![Afbeelding van het tabblad Geavanceerd zoeken aan de slag](images/atp-advanced-hunting.png)

> [!NOTE]
> <span data-ttu-id="11a36-186">Naast de basisqueryvoorbeelden hebt u ook toegang tot gedeelde [query's](advanced-hunting-shared-queries.md) voor specifieke scenario's voor het zoeken naar bedreigingen.</span><span class="sxs-lookup"><span data-stu-id="11a36-186">Apart from the basic query samples, you can also access [shared queries](advanced-hunting-shared-queries.md) for specific threat hunting scenarios.</span></span> <span data-ttu-id="11a36-187">Verken de gedeelde query's aan de linkerkant van de pagina of de [GitHub-queryopslagplaats.](https://aka.ms/hunting-queries)</span><span class="sxs-lookup"><span data-stu-id="11a36-187">Explore the shared queries on the left side of the page or the [GitHub query repository](https://aka.ms/hunting-queries).</span></span>

## <a name="access-comprehensive-query-language-reference"></a><span data-ttu-id="11a36-188">Uitgebreide querytaalverwijzing van Access</span><span class="sxs-lookup"><span data-stu-id="11a36-188">Access comprehensive query language reference</span></span>

<span data-ttu-id="11a36-189">Zie [Kusto-querytaaldocumentatie](https://docs.microsoft.com/azure/kusto/query/)voor meer informatie over de querytaal.</span><span class="sxs-lookup"><span data-stu-id="11a36-189">For detailed information about the query language, see [Kusto query language documentation](https://docs.microsoft.com/azure/kusto/query/).</span></span>

## <a name="related-topics"></a><span data-ttu-id="11a36-190">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="11a36-190">Related topics</span></span>
- [<span data-ttu-id="11a36-191">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="11a36-191">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="11a36-192">Werken met queryresultaten</span><span class="sxs-lookup"><span data-stu-id="11a36-192">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="11a36-193">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="11a36-193">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="11a36-194">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="11a36-194">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="11a36-195">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="11a36-195">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
