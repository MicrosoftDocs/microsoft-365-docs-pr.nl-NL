---
title: Leer de geavanceerde taal van de jachtquery in Microsoft Threat Protection
description: Maak uw eerste bedreigingsjachtquery en leer meer over veelvoorkomende operators en andere aspecten van de geavanceerde jachtquerytaal
keywords: geavanceerde jacht, dreigingjacht, cyberdreigingsjacht, bescherming tegen microsoft-dreigingen, microsoft 365, mtp, m365, zoeken, query, taal, leren, eerste query, telemetrie, gebeurtenissen, telemetrie, aangepaste detecties, schema, kusto, operators, gegevenstypen, powershell downloaden, queryvoorbeeld
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
ms.openlocfilehash: 5715baaccd95d975f7d15196906a6326177bbc2e
ms.sourcegitcommit: 242f051c4cf3683f8c1a5da20ceca81bde212cfc
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/26/2020
ms.locfileid: "42982006"
---
# <a name="learn-the-advanced-hunting-query-language"></a><span data-ttu-id="e0824-104">Leer de geavanceerde jachtquerytaal</span><span class="sxs-lookup"><span data-stu-id="e0824-104">Learn the advanced hunting query language</span></span>

<span data-ttu-id="e0824-105">**Geldt voor:**</span><span class="sxs-lookup"><span data-stu-id="e0824-105">**Applies to:**</span></span>
- <span data-ttu-id="e0824-106">Microsoft-bedreigingsbeveiliging</span><span class="sxs-lookup"><span data-stu-id="e0824-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="e0824-107">Geavanceerde jacht is gebaseerd op de [Kusto query taal](https://docs.microsoft.com/azure/kusto/query/).</span><span class="sxs-lookup"><span data-stu-id="e0824-107">Advanced hunting is based on the [Kusto query language](https://docs.microsoft.com/azure/kusto/query/).</span></span> <span data-ttu-id="e0824-108">U kusto-syntaxis en operatoren gebruiken om query's te maken die informatie vinden in het [schema](advanced-hunting-schema-tables.md) dat specifiek is gestructureerd voor geavanceerde jacht.</span><span class="sxs-lookup"><span data-stu-id="e0824-108">You can use Kusto syntax and operators to construct queries that locate information in the [schema](advanced-hunting-schema-tables.md) specifically structured for advanced hunting.</span></span> <span data-ttu-id="e0824-109">Voer uw eerste query uit om deze concepten beter te begrijpen.</span><span class="sxs-lookup"><span data-stu-id="e0824-109">To understand these concepts better, run your first query.</span></span>

## <a name="try-your-first-query"></a><span data-ttu-id="e0824-110">Probeer uw eerste query</span><span class="sxs-lookup"><span data-stu-id="e0824-110">Try your first query</span></span>

<span data-ttu-id="e0824-111">Ga in het beveiligingscentrum van Microsoft 365 naar **Op jacht** om uw eerste query uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="e0824-111">In Microsoft 365 security center, go to **Hunting** to run your first query.</span></span> <span data-ttu-id="e0824-112">Gebruik het volgende voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="e0824-112">Use the following example:</span></span>

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

<span data-ttu-id="e0824-113">Dit is hoe het eruit zal zien in geavanceerde jacht.</span><span class="sxs-lookup"><span data-stu-id="e0824-113">This is how it will look like in advanced hunting.</span></span>

![Afbeelding van geavanceerde jachtquery van Microsoft Threat Protection](../../media/advanced-hunting-query-example-2.png)

### <a name="describe-the-query-and-specify-the-tables-to-search"></a><span data-ttu-id="e0824-115">Beschrijf de query en geef de tabellen op die moeten zoeken</span><span class="sxs-lookup"><span data-stu-id="e0824-115">Describe the query and specify the tables to search</span></span>
<span data-ttu-id="e0824-116">Er is een korte opmerking toegevoegd aan het begin van de query om te beschrijven waar deze voor is.</span><span class="sxs-lookup"><span data-stu-id="e0824-116">A short comment has been added to the beginning of the query to describe what it is for.</span></span> <span data-ttu-id="e0824-117">Dit helpt als u later besluit om de query op te slaan en te delen met anderen in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="e0824-117">This helps if you later decide to save the query and share it with others in your organization.</span></span> 

```kusto
// Finds PowerShell execution events that could involve a download
```

<span data-ttu-id="e0824-118">De query zelf begint meestal met een tabelnaam, gevolgd door`|`een reeks elementen die door een pipe zijn gestart ( ).</span><span class="sxs-lookup"><span data-stu-id="e0824-118">The query itself will typically start with a table name followed by a series of elements started by a pipe (`|`).</span></span> <span data-ttu-id="e0824-119">In dit voorbeeld beginnen we met het `DeviceProcessEvents` creëren `DeviceNetworkEvents`van een unie van twee tabellen en, en voeg piped elementen toe als dat nodig is.</span><span class="sxs-lookup"><span data-stu-id="e0824-119">In this example, we start by creating a union of two tables,  `DeviceProcessEvents` and `DeviceNetworkEvents`, and add piped elements as needed.</span></span>

```kusto
union DeviceProcessEvents, DeviceNetworkEvents
```
### <a name="set-the-time-range"></a><span data-ttu-id="e0824-120">Het tijdsbereik instellen</span><span class="sxs-lookup"><span data-stu-id="e0824-120">Set the time range</span></span>
<span data-ttu-id="e0824-121">Het eerste piped element is een tijdfilter dat is uitgevoerd naar de voorgaande zeven dagen.</span><span class="sxs-lookup"><span data-stu-id="e0824-121">The first piped element is a time filter scoped to the previous seven days.</span></span> <span data-ttu-id="e0824-122">Als u het tijdsbereik zo beperkt mogelijk houdt, zorgt u ervoor dat query's goed presteren, beheerbare resultaten opleveren en geen time-out krijgen.</span><span class="sxs-lookup"><span data-stu-id="e0824-122">Keeping the time range as narrow as possible ensures that queries perform well, return manageable results, and don't time out.</span></span>

```kusto
| where Timestamp > ago(7d)
```

### <a name="check-specific-processes"></a><span data-ttu-id="e0824-123">Specifieke processen controleren</span><span class="sxs-lookup"><span data-stu-id="e0824-123">Check specific processes</span></span>
<span data-ttu-id="e0824-124">Het tijdsbereik wordt onmiddellijk gevolgd door een zoekopdracht naar procesbestandsnamen die de PowerShell-toepassing vertegenwoordigen.</span><span class="sxs-lookup"><span data-stu-id="e0824-124">The time range is immediately followed by a search for process file names representing the PowerShell application.</span></span>

```
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
```

### <a name="search-for-specific-command-strings"></a><span data-ttu-id="e0824-125">Zoeken naar specifieke opdrachttekenreeksen</span><span class="sxs-lookup"><span data-stu-id="e0824-125">Search for specific command strings</span></span>
<span data-ttu-id="e0824-126">Daarna zoekt de query naar tekenreeksen in opdrachtregels die doorgaans worden gebruikt om bestanden te downloaden met PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e0824-126">Afterwards, the query looks for strings in command lines that are typically used to download files using PowerShell.</span></span>

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

### <a name="customize-result-columns-and-length"></a><span data-ttu-id="e0824-127">Resultaatkolommen en lengte aanpassen</span><span class="sxs-lookup"><span data-stu-id="e0824-127">Customize result columns and length</span></span> 
<span data-ttu-id="e0824-128">Nu uw query duidelijk de gegevens identificeert die u wilt vinden, u elementen toevoegen die bepalen hoe de resultaten eruit zien.</span><span class="sxs-lookup"><span data-stu-id="e0824-128">Now that your query clearly identifies the data you want to locate, you can add elements that define what the results look like.</span></span> <span data-ttu-id="e0824-129">`project`retourneert specifieke `top` kolommen en beperkt het aantal resultaten.</span><span class="sxs-lookup"><span data-stu-id="e0824-129">`project` returns specific columns, and `top` limits the number of results.</span></span> <span data-ttu-id="e0824-130">Deze operators zorgen ervoor dat de resultaten goed geformatteerd en redelijk groot en eenvoudig te verwerken zijn.</span><span class="sxs-lookup"><span data-stu-id="e0824-130">These operators help ensure the results are well-formatted and reasonably large and easy to process.</span></span>

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

<span data-ttu-id="e0824-131">Klik **op Query uitvoeren** om de resultaten te bekijken.</span><span class="sxs-lookup"><span data-stu-id="e0824-131">Click **Run query** to see the results.</span></span> <span data-ttu-id="e0824-132">Selecteer het uitvouwpictogram rechtsboven in de queryeditor om u te concentreren op uw jachtquery en de resultaten.</span><span class="sxs-lookup"><span data-stu-id="e0824-132">Select the expand icon at the top right of the query editor to focus on your hunting query and the results.</span></span> 

![Afbeelding van het besturingselement Uitvouwen in de geavanceerde besturingselement voor jachtquery's](../../media/advanced-hunting-expand.png)

>[!TIP]
><span data-ttu-id="e0824-134">U queryresultaten als grafieken weergeven en filters snel aanpassen.</span><span class="sxs-lookup"><span data-stu-id="e0824-134">You can view query results as charts and quickly adjust filters.</span></span> <span data-ttu-id="e0824-135">Lees voor richtlijnen [meer over werken met queryresultaten](advanced-hunting-query-results.md)</span><span class="sxs-lookup"><span data-stu-id="e0824-135">For guidance, [read about working with query results](advanced-hunting-query-results.md)</span></span>

## <a name="learn-common-query-operators-for-advanced-hunting"></a><span data-ttu-id="e0824-136">Meer informatie over algemene query-operators voor geavanceerde jacht</span><span class="sxs-lookup"><span data-stu-id="e0824-136">Learn common query operators for advanced hunting</span></span>

<span data-ttu-id="e0824-137">Nu u uw eerste query hebt uitgevoerd en een algemeen idee hebt van de onderdelen, is het tijd om een beetje terug te krabbelen en enkele basisprincipes te leren.</span><span class="sxs-lookup"><span data-stu-id="e0824-137">Now that you've run your first query and have a general idea of its components, it's time to backtrack a little bit and learn some basics.</span></span> <span data-ttu-id="e0824-138">De Kusto-querytaal die door geavanceerde jacht wordt gebruikt, ondersteunt een reeks operatoren, waaronder de volgende gemeenschappelijke.</span><span class="sxs-lookup"><span data-stu-id="e0824-138">The Kusto query language used by advanced hunting supports a range of operators, including the following common ones.</span></span>

| <span data-ttu-id="e0824-139">Operator</span><span class="sxs-lookup"><span data-stu-id="e0824-139">Operator</span></span> | <span data-ttu-id="e0824-140">Beschrijving en gebruik</span><span class="sxs-lookup"><span data-stu-id="e0824-140">Description and usage</span></span> |
|--|--|
| `where` | <span data-ttu-id="e0824-141">Filter een tabel naar de subset van rijen die voldoen aan een predicaat.</span><span class="sxs-lookup"><span data-stu-id="e0824-141">Filter a table to the subset of rows that satisfy a predicate.</span></span> |
| `summarize` | <span data-ttu-id="e0824-142">Maak een tabel die de inhoud van de invoertabel samenvoegt.</span><span class="sxs-lookup"><span data-stu-id="e0824-142">Produce a table that aggregates the content of the input table.</span></span> |
| `join` | <span data-ttu-id="e0824-143">Voeg de rijen van twee tabellen samen om een nieuwe tabel te vormen door de waarden van de opgegeven kolom(en) van elke tabel af te voegen.</span><span class="sxs-lookup"><span data-stu-id="e0824-143">Merge the rows of two tables to form a new table by matching values of the specified column(s) from each table.</span></span> |
| `count` | <span data-ttu-id="e0824-144">Retourneer het aantal records in de set invoerrecord.</span><span class="sxs-lookup"><span data-stu-id="e0824-144">Return the number of records in the input record set.</span></span> |
| `top` | <span data-ttu-id="e0824-145">Retourneer de eerste N-records gesorteerd op de opgegeven kolommen.</span><span class="sxs-lookup"><span data-stu-id="e0824-145">Return the first N records sorted by the specified columns.</span></span> |
| `limit` | <span data-ttu-id="e0824-146">Ga terug naar het opgegeven aantal rijen.</span><span class="sxs-lookup"><span data-stu-id="e0824-146">Return up to the specified number of rows.</span></span> |
| `project` | <span data-ttu-id="e0824-147">Selecteer de kolommen die u wilt opnemen, de naam wijzigen of neerzetten en nieuwe berekende kolommen invoegen.</span><span class="sxs-lookup"><span data-stu-id="e0824-147">Select the columns to include, rename or drop, and insert new computed columns.</span></span> |
| `extend` | <span data-ttu-id="e0824-148">Maak berekende kolommen en sluit ze toe aan de resultatenset.</span><span class="sxs-lookup"><span data-stu-id="e0824-148">Create calculated columns and append them to the result set.</span></span> |
| `makeset` |  <span data-ttu-id="e0824-149">Retourneer een dynamische (JSON)-array van de set afzonderlijke waarden die Expr in de groep neemt.</span><span class="sxs-lookup"><span data-stu-id="e0824-149">Return a dynamic (JSON) array of the set of distinct values that Expr takes in the group.</span></span> |
| `find` | <span data-ttu-id="e0824-150">Zoek rijen die overeenkomen met een predicaat in een reeks tabellen.</span><span class="sxs-lookup"><span data-stu-id="e0824-150">Find rows that match a predicate across a set of tables.</span></span> |

<span data-ttu-id="e0824-151">Om een live voorbeeld van deze operators te zien, voert u ze uit vanaf de sectie **Aan de slag** in geavanceerde jacht.</span><span class="sxs-lookup"><span data-stu-id="e0824-151">To see a live example of these operators, run them from the **Get started** section in advanced hunting.</span></span>

## <a name="understand-data-types-and-their-query-syntax-implications"></a><span data-ttu-id="e0824-152">Gegevenstypen en de implicaties van de syntaxis van query's begrijpen</span><span class="sxs-lookup"><span data-stu-id="e0824-152">Understand data types and their query syntax implications</span></span>

<span data-ttu-id="e0824-153">Gegevens in geavanceerde jachttabellen worden over het algemeen ingedeeld in de volgende gegevenstypen.</span><span class="sxs-lookup"><span data-stu-id="e0824-153">Data in advanced hunting tables are generally classified into the following data types.</span></span>

| <span data-ttu-id="e0824-154">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="e0824-154">Data type</span></span> | <span data-ttu-id="e0824-155">Implicaties voor beschrijving en query</span><span class="sxs-lookup"><span data-stu-id="e0824-155">Description and query implications</span></span> |
|--|--|
| `datetime` | <span data-ttu-id="e0824-156">Gegevens- en tijdsinformatie die doorgaans gebeurtenistijdstempels vertegenwoordigen</span><span class="sxs-lookup"><span data-stu-id="e0824-156">Data and time information typically representing event timestamps</span></span> |
| `string` | <span data-ttu-id="e0824-157">Tekentekenreeks</span><span class="sxs-lookup"><span data-stu-id="e0824-157">Character string</span></span> |
| `bool` | <span data-ttu-id="e0824-158">Waar of onwaar</span><span class="sxs-lookup"><span data-stu-id="e0824-158">True or false</span></span> |
| `int` | <span data-ttu-id="e0824-159">32-bits numerieke waarde</span><span class="sxs-lookup"><span data-stu-id="e0824-159">32-bit numeric value</span></span>  |
| `long` | <span data-ttu-id="e0824-160">64-bits numerieke waarde</span><span class="sxs-lookup"><span data-stu-id="e0824-160">64-bit numeric value</span></span> |

## <a name="use-sample-queries"></a><span data-ttu-id="e0824-161">Voorbeeldquery's gebruiken</span><span class="sxs-lookup"><span data-stu-id="e0824-161">Use sample queries</span></span>

<span data-ttu-id="e0824-162">De sectie **Aan de slag** biedt een paar eenvoudige query's met veelgebruikte operatoren.</span><span class="sxs-lookup"><span data-stu-id="e0824-162">The **Get started** section provides a few simple queries using commonly used operators.</span></span> <span data-ttu-id="e0824-163">Probeer het uitvoeren van deze query's en het maken van kleine wijzigingen aan hen.</span><span class="sxs-lookup"><span data-stu-id="e0824-163">Try running these queries and making small modifications to them.</span></span>

![Beeld van geavanceerd jachtvenster](../../media/advanced-hunting-get-started.png)

>[!NOTE]
><span data-ttu-id="e0824-165">Naast de basisqueryvoorbeelden hebt u ook toegang tot [gedeelde query's](advanced-hunting-shared-queries.md) voor specifieke scenario's voor de jacht op bedreigingen.</span><span class="sxs-lookup"><span data-stu-id="e0824-165">Apart from the basic query samples, you can also access [shared queries](advanced-hunting-shared-queries.md) for specific threat hunting scenarios.</span></span> <span data-ttu-id="e0824-166">Bekijk de gedeelde query's aan de linkerkant van de pagina of de GitHub-queryopslagplaats.</span><span class="sxs-lookup"><span data-stu-id="e0824-166">Explore the shared queries on the left side of the page or the GitHub query repository.</span></span>

## <a name="access-query-language-documentation"></a><span data-ttu-id="e0824-167">Taaldocumentatie voor query's openen</span><span class="sxs-lookup"><span data-stu-id="e0824-167">Access query language documentation</span></span>

<span data-ttu-id="e0824-168">Zie [Kusto-querytaaldocumentatie](https://docs.microsoft.com/azure/kusto/query/)voor meer informatie over kusto-querytaal en ondersteunde operatoren.</span><span class="sxs-lookup"><span data-stu-id="e0824-168">For more information on Kusto query language and supported operators, see [Kusto query language documentation](https://docs.microsoft.com/azure/kusto/query/).</span></span>

## <a name="related-topics"></a><span data-ttu-id="e0824-169">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="e0824-169">Related topics</span></span>
- [<span data-ttu-id="e0824-170">Geavanceerd jachtoverzicht</span><span class="sxs-lookup"><span data-stu-id="e0824-170">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="e0824-171">Werken met queryresultaten</span><span class="sxs-lookup"><span data-stu-id="e0824-171">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="e0824-172">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="e0824-172">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="e0824-173">Zoek naar bedreigingen op verschillende apparaten en e-mails</span><span class="sxs-lookup"><span data-stu-id="e0824-173">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="e0824-174">Het schema begrijpen</span><span class="sxs-lookup"><span data-stu-id="e0824-174">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="e0824-175">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="e0824-175">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
