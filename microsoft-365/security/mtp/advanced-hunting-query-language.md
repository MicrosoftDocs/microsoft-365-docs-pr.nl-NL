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
ms.openlocfilehash: 8c66ee39d9c7f90142a564c61b13f68e6b4b481e
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197771"
---
# <a name="learn-the-advanced-hunting-query-language"></a><span data-ttu-id="27e68-104">Meer informatie over de querytaal Advanced jacht</span><span class="sxs-lookup"><span data-stu-id="27e68-104">Learn the advanced hunting query language</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="27e68-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="27e68-105">**Applies to:**</span></span>
- <span data-ttu-id="27e68-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="27e68-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="27e68-107">Voor de geavanceerde jacht op basis van de [querytaal Kusto](https://docs.microsoft.com/azure/kusto/query/).</span><span class="sxs-lookup"><span data-stu-id="27e68-107">Advanced hunting is based on the [Kusto query language](https://docs.microsoft.com/azure/kusto/query/).</span></span> <span data-ttu-id="27e68-108">U kunt de syntaxis van Kusto en operatoren gebruiken om query's te maken waarmee informatie in het [schema](advanced-hunting-schema-tables.md) specifiek wordt gestructureerd voor de geavanceerde jacht.</span><span class="sxs-lookup"><span data-stu-id="27e68-108">You can use Kusto syntax and operators to construct queries that locate information in the [schema](advanced-hunting-schema-tables.md) specifically structured for advanced hunting.</span></span> <span data-ttu-id="27e68-109">Voor een betere uitleg van deze concepten voert u uw eerste query uit.</span><span class="sxs-lookup"><span data-stu-id="27e68-109">To understand these concepts better, run your first query.</span></span>

## <a name="try-your-first-query"></a><span data-ttu-id="27e68-110">Probeer uw eerste query</span><span class="sxs-lookup"><span data-stu-id="27e68-110">Try your first query</span></span>

<span data-ttu-id="27e68-111">In Microsoft 365 Beveiligingscentrum gaat u naar **jacht** om uw eerste query uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="27e68-111">In Microsoft 365 security center, go to **Hunting** to run your first query.</span></span> <span data-ttu-id="27e68-112">Gebruik het volgende voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="27e68-112">Use the following example:</span></span>

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

<span data-ttu-id="27e68-113">Dit ziet er zo uit in de geavanceerde jacht.</span><span class="sxs-lookup"><span data-stu-id="27e68-113">This is how it will look like in advanced hunting.</span></span>

![Afbeelding van Microsoft Threat Protection Advanced jacht query](../../media/advanced-hunting-query-example-2.png)

### <a name="describe-the-query-and-specify-the-tables-to-search"></a><span data-ttu-id="27e68-115">De query beschrijven en de tabellen opgeven waarnaar moet worden gezocht</span><span class="sxs-lookup"><span data-stu-id="27e68-115">Describe the query and specify the tables to search</span></span>
<span data-ttu-id="27e68-116">Er is een korte opmerking toegevoegd aan het begin van de query om te beschrijven wat het is.</span><span class="sxs-lookup"><span data-stu-id="27e68-116">A short comment has been added to the beginning of the query to describe what it is for.</span></span> <span data-ttu-id="27e68-117">Dit helpt u als u later besluit om de query op te slaan en te delen met anderen in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="27e68-117">This helps if you later decide to save the query and share it with others in your organization.</span></span> 

```kusto
// Finds PowerShell execution events that could involve a download
```

<span data-ttu-id="27e68-118">De query zelf begint meestal met een tabelnaam gevolgd door een reeks elementen die met een sluisteken () zijn gestart `|` .</span><span class="sxs-lookup"><span data-stu-id="27e68-118">The query itself will typically start with a table name followed by a series of elements started by a pipe (`|`).</span></span> <span data-ttu-id="27e68-119">In dit voorbeeld beginnen we met het maken van een samenvoeging van twee tabellen, en het  `DeviceProcessEvents` `DeviceNetworkEvents` toevoegen van elementen met een sluisteken.</span><span class="sxs-lookup"><span data-stu-id="27e68-119">In this example, we start by creating a union of two tables,  `DeviceProcessEvents` and `DeviceNetworkEvents`, and add piped elements as needed.</span></span>

```kusto
union DeviceProcessEvents, DeviceNetworkEvents
```
### <a name="set-the-time-range"></a><span data-ttu-id="27e68-120">Het tijdsbereik instellen</span><span class="sxs-lookup"><span data-stu-id="27e68-120">Set the time range</span></span>
<span data-ttu-id="27e68-121">Het eerste element met een pipet is een tijdfilter bereik dat de afgelopen zeven dagen is beperkt.</span><span class="sxs-lookup"><span data-stu-id="27e68-121">The first piped element is a time filter scoped to the previous seven days.</span></span> <span data-ttu-id="27e68-122">Zorg dat het tijdsbereik zo smal mogelijk is dat query's goed worden uitgevoerd, retourneer kunnen komen en geen tijd in beslag kunnen gaan.</span><span class="sxs-lookup"><span data-stu-id="27e68-122">Keeping the time range as narrow as possible ensures that queries perform well, return manageable results, and don't time out.</span></span>

```kusto
| where Timestamp > ago(7d)
```

### <a name="check-specific-processes"></a><span data-ttu-id="27e68-123">Specifieke processen controleren</span><span class="sxs-lookup"><span data-stu-id="27e68-123">Check specific processes</span></span>
<span data-ttu-id="27e68-124">Het tijdsbereik wordt direct gevolgd door een zoekopdracht naar proces bestandsnamen die de PowerShell-toepassing vertegenwoordigen.</span><span class="sxs-lookup"><span data-stu-id="27e68-124">The time range is immediately followed by a search for process file names representing the PowerShell application.</span></span>

```kusto
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
```

### <a name="search-for-specific-command-strings"></a><span data-ttu-id="27e68-125">Zoeken naar specifieke opdrachtreeksen</span><span class="sxs-lookup"><span data-stu-id="27e68-125">Search for specific command strings</span></span>
<span data-ttu-id="27e68-126">Vervolgens zoekt de query naar tekenreeksen in opdrachtregels die meestal worden gebruikt om bestanden te downloaden met PowerShell.</span><span class="sxs-lookup"><span data-stu-id="27e68-126">Afterwards, the query looks for strings in command lines that are typically used to download files using PowerShell.</span></span>

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

### <a name="customize-result-columns-and-length"></a><span data-ttu-id="27e68-127">Resultatenkolommen en lengte aanpassen</span><span class="sxs-lookup"><span data-stu-id="27e68-127">Customize result columns and length</span></span> 
<span data-ttu-id="27e68-128">Wanneer de gegevens die u wilt zoeken duidelijk worden geïdentificeerd met de query, kunt u elementen toevoegen waarmee wordt gedefinieerd hoe de resultaten eruit komen te zien.</span><span class="sxs-lookup"><span data-stu-id="27e68-128">Now that your query clearly identifies the data you want to locate, you can add elements that define what the results look like.</span></span> <span data-ttu-id="27e68-129">`project` geeft als resultaat bepaalde kolommen en `top` beperkt het aantal resultaten.</span><span class="sxs-lookup"><span data-stu-id="27e68-129">`project` returns specific columns, and `top` limits the number of results.</span></span> <span data-ttu-id="27e68-130">Met deze operatoren zorgt u ervoor dat de resultaten goed opgemaakt en redelijk zijn.</span><span class="sxs-lookup"><span data-stu-id="27e68-130">These operators help ensure the results are well-formatted and reasonably large and easy to process.</span></span>

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

<span data-ttu-id="27e68-131">Klik op **query uitvoeren** om de resultaten te bekijken.</span><span class="sxs-lookup"><span data-stu-id="27e68-131">Click **Run query** to see the results.</span></span> <span data-ttu-id="27e68-132">Selecteer het pictogram voor uitvouwen in de rechterbovenhoek van de query-editor om de focus te richten op de jacht-query en de resultaten.</span><span class="sxs-lookup"><span data-stu-id="27e68-132">Select the expand icon at the top right of the query editor to focus on your hunting query and the results.</span></span> 

![Afbeelding van het besturingselement uitvouwen in de geavanceerde jacht query editor](../../media/advanced-hunting-expand.png)

>[!TIP]
><span data-ttu-id="27e68-134">U kunt queryresultaten weergeven als grafieken en de filters snel aanpassen.</span><span class="sxs-lookup"><span data-stu-id="27e68-134">You can view query results as charts and quickly adjust filters.</span></span> <span data-ttu-id="27e68-135">[Zie voor meer informatie over het werken met queryresultaten](advanced-hunting-query-results.md)</span><span class="sxs-lookup"><span data-stu-id="27e68-135">For guidance, [read about working with query results](advanced-hunting-query-results.md)</span></span>

## <a name="learn-common-query-operators"></a><span data-ttu-id="27e68-136">Veelgebruikte queryoperators</span><span class="sxs-lookup"><span data-stu-id="27e68-136">Learn common query operators</span></span>

<span data-ttu-id="27e68-137">Nu u uw eerste query hebt uitgevoerd en een algemeen idee van de onderdelen hebt, is het tijd om terugkeren iets een beetje te leren en de basisbeginselen te leren kennen.</span><span class="sxs-lookup"><span data-stu-id="27e68-137">Now that you've run your first query and have a general idea of its components, it's time to backtrack a little bit and learn some basics.</span></span> <span data-ttu-id="27e68-138">De Kusto querytaal die wordt gebruikt in de geavanceerde jacht, biedt ondersteuning voor een bereik van operatoren, waaronder de volgende algemene versies.</span><span class="sxs-lookup"><span data-stu-id="27e68-138">The Kusto query language used by advanced hunting supports a range of operators, including the following common ones.</span></span>

| <span data-ttu-id="27e68-139">Werk</span><span class="sxs-lookup"><span data-stu-id="27e68-139">Operator</span></span> | <span data-ttu-id="27e68-140">Beschrijving en gebruik</span><span class="sxs-lookup"><span data-stu-id="27e68-140">Description and usage</span></span> |
|--|--|
| `where` | <span data-ttu-id="27e68-141">Een tabel filteren op de subset van rijen die op een predicaat voldoen.</span><span class="sxs-lookup"><span data-stu-id="27e68-141">Filter a table to the subset of rows that satisfy a predicate.</span></span> |
| `summarize` | <span data-ttu-id="27e68-142">Een tabel maken waarmee de inhoud van de invoertabel wordt geaggregeerd.</span><span class="sxs-lookup"><span data-stu-id="27e68-142">Produce a table that aggregates the content of the input table.</span></span> |
| `join` | <span data-ttu-id="27e68-143">De rijen van twee tabellen samenvoegen om een nieuwe tabel te maken door te zoeken naar waarden van de opgegeven kolommen in elke tabel.</span><span class="sxs-lookup"><span data-stu-id="27e68-143">Merge the rows of two tables to form a new table by matching values of the specified column(s) from each table.</span></span> |
| `count` | <span data-ttu-id="27e68-144">Het aantal records in de invoerrecord retourneren.</span><span class="sxs-lookup"><span data-stu-id="27e68-144">Return the number of records in the input record set.</span></span> |
| `top` | <span data-ttu-id="27e68-145">De eerste N records die op de opgegeven kolommen zijn gesorteerd, retourneren.</span><span class="sxs-lookup"><span data-stu-id="27e68-145">Return the first N records sorted by the specified columns.</span></span> |
| `limit` | <span data-ttu-id="27e68-146">Naar het opgegeven aantal rijen gaan.</span><span class="sxs-lookup"><span data-stu-id="27e68-146">Return up to the specified number of rows.</span></span> |
| `project` | <span data-ttu-id="27e68-147">Selecteer de kolommen die u wilt opnemen, waarvan u de naam wilt wijzigen of die u wilt verwijderen en voeg nieuwe berekende kolommen in.</span><span class="sxs-lookup"><span data-stu-id="27e68-147">Select the columns to include, rename or drop, and insert new computed columns.</span></span> |
| `extend` | <span data-ttu-id="27e68-148">Berekende kolommen maken en deze toevoegen aan de resultatenset.</span><span class="sxs-lookup"><span data-stu-id="27e68-148">Create calculated columns and append them to the result set.</span></span> |
| `makeset` |  <span data-ttu-id="27e68-149">Retourneert een dynamische (JSON) matrix van de reeks unieke waarden die in de groep worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="27e68-149">Return a dynamic (JSON) array of the set of distinct values that Expr takes in the group.</span></span> |
| `find` | <span data-ttu-id="27e68-150">Rijen zoeken die overeenkomen met een predicaat in een set tabellen.</span><span class="sxs-lookup"><span data-stu-id="27e68-150">Find rows that match a predicate across a set of tables.</span></span> |

<span data-ttu-id="27e68-151">Als u een voorbeeld van deze operatoren wilt zien, voert u deze uit in de sectie **aan de slag** in geavanceerde jacht.</span><span class="sxs-lookup"><span data-stu-id="27e68-151">To see a live example of these operators, run them from the **Get started** section in advanced hunting.</span></span>

## <a name="understand-data-types"></a><span data-ttu-id="27e68-152">Meer informatie over gegevenstypen</span><span class="sxs-lookup"><span data-stu-id="27e68-152">Understand data types</span></span>

<span data-ttu-id="27e68-153">Gegevens in geavanceerde jagers tabellen worden algemeen ingedeeld in de volgende gegevenstypen.</span><span class="sxs-lookup"><span data-stu-id="27e68-153">Data in advanced hunting tables are generally classified into the following data types.</span></span>

| <span data-ttu-id="27e68-154">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="27e68-154">Data type</span></span> | <span data-ttu-id="27e68-155">Beschrijving van de gevolgen van de query</span><span class="sxs-lookup"><span data-stu-id="27e68-155">Description and query implications</span></span> |
|--|--|
| `datetime` | <span data-ttu-id="27e68-156">Gegevens en tijds informatie die meestal tijdstempels voor gebeurtenissen vertegenwoordigen</span><span class="sxs-lookup"><span data-stu-id="27e68-156">Data and time information typically representing event timestamps</span></span> |
| `string` | <span data-ttu-id="27e68-157">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="27e68-157">Character string</span></span> |
| `bool` | <span data-ttu-id="27e68-158">Waar of onwaar</span><span class="sxs-lookup"><span data-stu-id="27e68-158">True or false</span></span> |
| `int` | <span data-ttu-id="27e68-159">32-bits numerieke waarde</span><span class="sxs-lookup"><span data-stu-id="27e68-159">32-bit numeric value</span></span>  |
| `long` | <span data-ttu-id="27e68-160">64-bits numerieke waarde</span><span class="sxs-lookup"><span data-stu-id="27e68-160">64-bit numeric value</span></span> |

<span data-ttu-id="27e68-161">Meer informatie over deze gegevenstypen en de implicaties hiervan [vindt u in Kusto scalaire gegevenstypen](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/).</span><span class="sxs-lookup"><span data-stu-id="27e68-161">To learn more about these data types and their implications, [read about Kusto scalar data types](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/).</span></span>

## <a name="get-help-as-you-write-queries"></a><span data-ttu-id="27e68-162">Hulp vragen bij het schrijven van query's</span><span class="sxs-lookup"><span data-stu-id="27e68-162">Get help as you write queries</span></span>
<span data-ttu-id="27e68-163">Profiteer van de volgende functies om query's sneller te schrijven:</span><span class="sxs-lookup"><span data-stu-id="27e68-163">Take advantage of the following functionality to write queries faster:</span></span>
- <span data-ttu-id="27e68-164">**Suggesties, wanneer** u query's schrijft, biedt geavanceerde jacht suggesties voor IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="27e68-164">**Autosuggest** — as you write queries, advanced hunting provides suggestions from IntelliSense.</span></span> 
- <span data-ttu-id="27e68-165">**Schemastructuur** : een schema weergave met daarin de lijst met tabellen en de bijbehorende kolommen wordt weergegeven naast uw werkruimte.</span><span class="sxs-lookup"><span data-stu-id="27e68-165">**Schema tree** — a schema representation that includes the list of tables and their columns is provided next to your working area.</span></span> <span data-ttu-id="27e68-166">Plaats de muisaanwijzer op een item voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="27e68-166">For more information, hover over an item.</span></span> <span data-ttu-id="27e68-167">Dubbelklik op een item om het in te voegen in de query editor.</span><span class="sxs-lookup"><span data-stu-id="27e68-167">Double-click an item to insert it to the query editor.</span></span>
- <span data-ttu-id="27e68-168">Naslag voor **[schema verwijzingen](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** in de portal met beschrijvingen van tabellen en kolommen, en ondersteunde gebeurtenistypen ( `ActionType` waarden) en voorbeeldquery's</span><span class="sxs-lookup"><span data-stu-id="27e68-168">**[Schema reference](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** — in-portal reference with table and column descriptions as well as supported event types (`ActionType` values) and sample queries</span></span>

## <a name="work-with-multiple-queries-in-the-editor"></a><span data-ttu-id="27e68-169">Werken met meerdere query's in de editor</span><span class="sxs-lookup"><span data-stu-id="27e68-169">Work with multiple queries in the editor</span></span>
<span data-ttu-id="27e68-170">Met de query editor kunt u ook uw Kladblok gebruiken om te experimenteren met meerdere query's.</span><span class="sxs-lookup"><span data-stu-id="27e68-170">The query editor can serve as your scratch pad for experimenting with multiple queries.</span></span> <span data-ttu-id="27e68-171">Meerdere query's gebruiken:</span><span class="sxs-lookup"><span data-stu-id="27e68-171">To use multiple queries:</span></span>

- <span data-ttu-id="27e68-172">Afzonderlijke query's met een lege regel scheiden.</span><span class="sxs-lookup"><span data-stu-id="27e68-172">Separate each query with an empty line.</span></span>
- <span data-ttu-id="27e68-173">Plaats de cursor op een deel van een query om die query te selecteren voordat u deze uitvoert.</span><span class="sxs-lookup"><span data-stu-id="27e68-173">Place the cursor on any part of a query to select that query before running it.</span></span> <span data-ttu-id="27e68-174">Hiermee wordt alleen de geselecteerde query uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="27e68-174">This will run only the selected query.</span></span> <span data-ttu-id="27e68-175">Als u een andere query wilt uitvoeren, verplaatst u de cursor dienovereenkomstig en selecteert u **query uitvoeren**.</span><span class="sxs-lookup"><span data-stu-id="27e68-175">To run another query, move the cursor accordingly and select **Run query**.</span></span>

![Afbeelding van de query editor met meerdere query's](../../media/mtp-ah/ah-multi-query.png)

## <a name="use-sample-queries"></a><span data-ttu-id="27e68-177">Voorbeeldquery's gebruiken</span><span class="sxs-lookup"><span data-stu-id="27e68-177">Use sample queries</span></span>

<span data-ttu-id="27e68-178">De sectie **aan** de slag biedt een paar eenvoudige query's waarbij veelgebruikte operatoren worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="27e68-178">The **Get started** section provides a few simple queries using commonly used operators.</span></span> <span data-ttu-id="27e68-179">Voer deze query's uit en wijzig deze met een kleine wijziging.</span><span class="sxs-lookup"><span data-stu-id="27e68-179">Try running these queries and making small modifications to them.</span></span>

![Afbeelding van het venster Geavanceerde jacht](../../media/advanced-hunting-get-started.png)

>[!NOTE]
><span data-ttu-id="27e68-181">Afgezien van de basisvoorbeelden van de query, hebt u ook toegang tot [gedeelde query's](advanced-hunting-shared-queries.md) voor specifieke scenario's voor bedreigings jacht.</span><span class="sxs-lookup"><span data-stu-id="27e68-181">Apart from the basic query samples, you can also access [shared queries](advanced-hunting-shared-queries.md) for specific threat hunting scenarios.</span></span> <span data-ttu-id="27e68-182">Verstudeer de gedeelde query's aan de linkerkant van de pagina of in de GitHub query-bibliotheek.</span><span class="sxs-lookup"><span data-stu-id="27e68-182">Explore the shared queries on the left side of the page or the GitHub query repository.</span></span>

## <a name="access-query-language-documentation"></a><span data-ttu-id="27e68-183">Documentatie voor Access-querytalen</span><span class="sxs-lookup"><span data-stu-id="27e68-183">Access query language documentation</span></span>

<span data-ttu-id="27e68-184">Zie de [documentatie bij de querytaal van Kusto](https://docs.microsoft.com/azure/kusto/query/)voor meer informatie over Kusto querytaal en ondersteunde operatoren.</span><span class="sxs-lookup"><span data-stu-id="27e68-184">For more information on Kusto query language and supported operators, see [Kusto query language documentation](https://docs.microsoft.com/azure/kusto/query/).</span></span>

## <a name="related-topics"></a><span data-ttu-id="27e68-185">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="27e68-185">Related topics</span></span>
- [<span data-ttu-id="27e68-186">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="27e68-186">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="27e68-187">Werken met queryresultaten</span><span class="sxs-lookup"><span data-stu-id="27e68-187">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="27e68-188">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="27e68-188">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="27e68-189">Opsporen op apparaten en in e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="27e68-189">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="27e68-190">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="27e68-190">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="27e68-191">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="27e68-191">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
