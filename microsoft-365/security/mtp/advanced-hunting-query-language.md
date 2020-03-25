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
ms.openlocfilehash: e093bd9c5a76b44cf66591b4212f37014189186e
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2020
ms.locfileid: "42928994"
---
# <a name="learn-the-advanced-hunting-query-language"></a><span data-ttu-id="8679b-104">Leer de geavanceerde jachtquerytaal</span><span class="sxs-lookup"><span data-stu-id="8679b-104">Learn the advanced hunting query language</span></span>

<span data-ttu-id="8679b-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="8679b-105">**Applies to:**</span></span>
- <span data-ttu-id="8679b-106">Microsoft-bedreigingsbeveiliging</span><span class="sxs-lookup"><span data-stu-id="8679b-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="8679b-107">Geavanceerde jacht is gebaseerd op de [Kusto query taal](https://docs.microsoft.com/azure/kusto/query/).</span><span class="sxs-lookup"><span data-stu-id="8679b-107">Advanced hunting is based on the [Kusto query language](https://docs.microsoft.com/azure/kusto/query/).</span></span> <span data-ttu-id="8679b-108">U kusto-syntaxis en operatoren gebruiken om query's te maken die informatie vinden in het [schema](advanced-hunting-schema-tables.md) dat specifiek is gestructureerd voor geavanceerde jacht.</span><span class="sxs-lookup"><span data-stu-id="8679b-108">You can use Kusto syntax and operators to construct queries that locate information in the [schema](advanced-hunting-schema-tables.md) specifically structured for advanced hunting.</span></span> <span data-ttu-id="8679b-109">Voer uw eerste query uit om deze concepten beter te begrijpen.</span><span class="sxs-lookup"><span data-stu-id="8679b-109">To understand these concepts better, run your first query.</span></span>

## <a name="try-your-first-query"></a><span data-ttu-id="8679b-110">Probeer uw eerste query</span><span class="sxs-lookup"><span data-stu-id="8679b-110">Try your first query</span></span>

<span data-ttu-id="8679b-111">Ga in het beveiligingscentrum van Microsoft 365 naar **Op jacht** om uw eerste query uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="8679b-111">In Microsoft 365 security center, go to **Hunting** to run your first query.</span></span> <span data-ttu-id="8679b-112">Gebruik het volgende voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8679b-112">Use the following example:</span></span>

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

<span data-ttu-id="8679b-113">Dit is hoe het eruit zal zien in geavanceerde jacht.</span><span class="sxs-lookup"><span data-stu-id="8679b-113">This is how it will look like in advanced hunting.</span></span>

![Afbeelding van geavanceerde jachtquery van Microsoft Threat Protection](../../media/advanced-hunting-query-example.png)

<span data-ttu-id="8679b-115">Er is een korte opmerking toegevoegd aan het begin van de query om te beschrijven waar deze voor is.</span><span class="sxs-lookup"><span data-stu-id="8679b-115">A short comment has been added to the beginning of the query to describe what it is for.</span></span> <span data-ttu-id="8679b-116">Dit helpt als u later besluit om de query op te slaan en te delen met anderen in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="8679b-116">This helps if you later decide to save the query and share it with others in your organization.</span></span> 

```kusto
// Finds PowerShell execution events that could involve a download
```

<span data-ttu-id="8679b-117">De query zelf begint meestal met een tabelnaam, gevolgd door`|`een reeks elementen die door een pipe zijn gestart ( ).</span><span class="sxs-lookup"><span data-stu-id="8679b-117">The query itself will typically start with a table name followed by a series of elements started by a pipe (`|`).</span></span> <span data-ttu-id="8679b-118">In dit voorbeeld beginnen we met het `DeviceProcessEvents` creëren `DeviceNetworkEvents`van een unie van twee tabellen en, en voeg piped elementen toe als dat nodig is.</span><span class="sxs-lookup"><span data-stu-id="8679b-118">In this example, we start by creating a union of two tables,  `DeviceProcessEvents` and `DeviceNetworkEvents`, and add piped elements as needed.</span></span>

```kusto
union DeviceProcessEvents, DeviceNetworkEvents
```
<span data-ttu-id="8679b-119">Het eerste piped element is een tijdfilter dat is uitgevoerd naar de voorgaande zeven dagen.</span><span class="sxs-lookup"><span data-stu-id="8679b-119">The first piped element is a time filter scoped to the previous seven days.</span></span> <span data-ttu-id="8679b-120">Als u het tijdsbereik zo beperkt mogelijk houdt, zorgt u ervoor dat query's goed presteren, beheerbare resultaten opleveren en geen time-out krijgen.</span><span class="sxs-lookup"><span data-stu-id="8679b-120">Keeping the time range as narrow as possible ensures that queries perform well, return manageable results, and don't time out.</span></span>

```kusto
| where Timestamp > ago(7d)
```

<span data-ttu-id="8679b-121">Het tijdsbereik wordt onmiddellijk gevolgd door een zoekopdracht naar procesbestandsnamen die de PowerShell-toepassing vertegenwoordigen.</span><span class="sxs-lookup"><span data-stu-id="8679b-121">The time range is immediately followed by a search for process file names representing the PowerShell application.</span></span>

```
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
```

<span data-ttu-id="8679b-122">Daarna zoekt de query naar tekenreeksen in opdrachtregels die doorgaans worden gebruikt om bestanden te downloaden met PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8679b-122">Afterwards, the query looks for strings in command lines that are typically used to download files using PowerShell.</span></span>

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
<span data-ttu-id="8679b-123">Nu uw query duidelijk de gegevens identificeert die u wilt vinden, u elementen toevoegen die bepalen hoe de resultaten eruit zien.</span><span class="sxs-lookup"><span data-stu-id="8679b-123">Now that your query clearly identifies the data you want to locate, you can add elements that define what the results look like.</span></span> <span data-ttu-id="8679b-124">`project`retourneert `top` specifieke kolommen en beperkt het aantal resultaten, waardoor de resultaten goed zijn opgemaakt en redelijk groot en eenvoudig te verwerken zijn.</span><span class="sxs-lookup"><span data-stu-id="8679b-124">`project` returns specific columns and `top` limits the number of results, helping ensure the results well-formatted and reasonably large and easy to process.</span></span>

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

<span data-ttu-id="8679b-125">Klik **op Query uitvoeren** om de resultaten te bekijken.</span><span class="sxs-lookup"><span data-stu-id="8679b-125">Click **Run query** to see the results.</span></span> <span data-ttu-id="8679b-126">Selecteer het uitvouwpictogram rechtsboven in de queryeditor om u te concentreren op uw jachtquery en de resultaten.</span><span class="sxs-lookup"><span data-stu-id="8679b-126">Select the expand icon at the top right of the query editor to focus on your hunting query and the results.</span></span>

![Afbeelding van het besturingselement Uitvouwen in de geavanceerde besturingselement voor jachtquery's](../../media/advanced-hunting-expand.png)

## <a name="learn-common-query-operators-for-advanced-hunting"></a><span data-ttu-id="8679b-128">Meer informatie over algemene query-operators voor geavanceerde jacht</span><span class="sxs-lookup"><span data-stu-id="8679b-128">Learn common query operators for advanced hunting</span></span>

<span data-ttu-id="8679b-129">Nu u uw eerste query hebt uitgevoerd en een algemeen idee hebt van de onderdelen, is het tijd om een beetje terug te krabbelen en enkele basisprincipes te leren.</span><span class="sxs-lookup"><span data-stu-id="8679b-129">Now that you've run your first query and have a general idea of its components, it's time to backtrack a little bit and learn some basics.</span></span> <span data-ttu-id="8679b-130">De Kusto-querytaal die door geavanceerde jacht wordt gebruikt, ondersteunt een reeks operatoren, waaronder de volgende gemeenschappelijke.</span><span class="sxs-lookup"><span data-stu-id="8679b-130">The Kusto query language used by advanced hunting supports a range of operators, including the following common ones.</span></span>

| <span data-ttu-id="8679b-131">Operator</span><span class="sxs-lookup"><span data-stu-id="8679b-131">Operator</span></span> | <span data-ttu-id="8679b-132">Beschrijving en gebruik</span><span class="sxs-lookup"><span data-stu-id="8679b-132">Description and usage</span></span> |
|--|--|
| `where` | <span data-ttu-id="8679b-133">Filter een tabel naar de subset van rijen die voldoen aan een predicaat.</span><span class="sxs-lookup"><span data-stu-id="8679b-133">Filter a table to the subset of rows that satisfy a predicate.</span></span> |
| `summarize` | <span data-ttu-id="8679b-134">Maak een tabel die de inhoud van de invoertabel samenvoegt.</span><span class="sxs-lookup"><span data-stu-id="8679b-134">Produce a table that aggregates the content of the input table.</span></span> |
| `join` | <span data-ttu-id="8679b-135">Voeg de rijen van twee tabellen samen om een nieuwe tabel te vormen door de waarden van de opgegeven kolom(en) van elke tabel af te voegen.</span><span class="sxs-lookup"><span data-stu-id="8679b-135">Merge the rows of two tables to form a new table by matching values of the specified column(s) from each table.</span></span> |
| `count` | <span data-ttu-id="8679b-136">Retourneer het aantal records in de set invoerrecord.</span><span class="sxs-lookup"><span data-stu-id="8679b-136">Return the number of records in the input record set.</span></span> |
| `top` | <span data-ttu-id="8679b-137">Retourneer de eerste N-records gesorteerd op de opgegeven kolommen.</span><span class="sxs-lookup"><span data-stu-id="8679b-137">Return the first N records sorted by the specified columns.</span></span> |
| `limit` | <span data-ttu-id="8679b-138">Ga terug naar het opgegeven aantal rijen.</span><span class="sxs-lookup"><span data-stu-id="8679b-138">Return up to the specified number of rows.</span></span> |
| `project` | <span data-ttu-id="8679b-139">Selecteer de kolommen die u wilt opnemen, de naam wijzigen of neerzetten en nieuwe berekende kolommen invoegen.</span><span class="sxs-lookup"><span data-stu-id="8679b-139">Select the columns to include, rename or drop, and insert new computed columns.</span></span> |
| `extend` | <span data-ttu-id="8679b-140">Maak berekende kolommen en sluit ze toe aan de resultatenset.</span><span class="sxs-lookup"><span data-stu-id="8679b-140">Create calculated columns and append them to the result set.</span></span> |
| `makeset` |  <span data-ttu-id="8679b-141">Retourneer een dynamische (JSON)-array van de set afzonderlijke waarden die Expr in de groep neemt.</span><span class="sxs-lookup"><span data-stu-id="8679b-141">Return a dynamic (JSON) array of the set of distinct values that Expr takes in the group.</span></span> |
| `find` | <span data-ttu-id="8679b-142">Zoek rijen die overeenkomen met een predicaat in een reeks tabellen.</span><span class="sxs-lookup"><span data-stu-id="8679b-142">Find rows that match a predicate across a set of tables.</span></span> |

<span data-ttu-id="8679b-143">Om een live voorbeeld van deze operators te zien, voert u ze uit vanaf de sectie **Aan de slag** in geavanceerde jacht.</span><span class="sxs-lookup"><span data-stu-id="8679b-143">To see a live example of these operators, run them from the **Get started** section in advanced hunting.</span></span>

## <a name="understand-data-types-and-their-query-syntax-implications"></a><span data-ttu-id="8679b-144">Gegevenstypen en de implicaties van de syntaxis van query's begrijpen</span><span class="sxs-lookup"><span data-stu-id="8679b-144">Understand data types and their query syntax implications</span></span>

<span data-ttu-id="8679b-145">Gegevens in geavanceerde jachttabellen worden over het algemeen ingedeeld in de volgende gegevenstypen.</span><span class="sxs-lookup"><span data-stu-id="8679b-145">Data in advanced hunting tables are generally classified into the following data types.</span></span>

| <span data-ttu-id="8679b-146">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="8679b-146">Data type</span></span> | <span data-ttu-id="8679b-147">Implicaties voor beschrijving en query</span><span class="sxs-lookup"><span data-stu-id="8679b-147">Description and query implications</span></span> |
|--|--|
| `datetime` | <span data-ttu-id="8679b-148">Gegevens- en tijdsinformatie die doorgaans gebeurtenistijdstempels vertegenwoordigen</span><span class="sxs-lookup"><span data-stu-id="8679b-148">Data and time information typically representing event timestamps</span></span> |
| `string` | <span data-ttu-id="8679b-149">Tekentekenreeks</span><span class="sxs-lookup"><span data-stu-id="8679b-149">Character string</span></span> |
| `bool` | <span data-ttu-id="8679b-150">Waar of onwaar</span><span class="sxs-lookup"><span data-stu-id="8679b-150">True or false</span></span> |
| `int` | <span data-ttu-id="8679b-151">32-bits numerieke waarde</span><span class="sxs-lookup"><span data-stu-id="8679b-151">32-bit numeric value</span></span>  |
| `long` | <span data-ttu-id="8679b-152">64-bits numerieke waarde</span><span class="sxs-lookup"><span data-stu-id="8679b-152">64-bit numeric value</span></span> |

## <a name="use-sample-queries"></a><span data-ttu-id="8679b-153">Voorbeeldquery's gebruiken</span><span class="sxs-lookup"><span data-stu-id="8679b-153">Use sample queries</span></span>

<span data-ttu-id="8679b-154">De sectie **Aan de slag** biedt een paar eenvoudige query's met veelgebruikte operatoren.</span><span class="sxs-lookup"><span data-stu-id="8679b-154">The **Get started** section provides a few simple queries using commonly used operators.</span></span> <span data-ttu-id="8679b-155">Probeer het uitvoeren van deze query's en het maken van kleine wijzigingen aan hen.</span><span class="sxs-lookup"><span data-stu-id="8679b-155">Try running these queries and making small modifications to them.</span></span>

![Beeld van geavanceerd jachtvenster](../../media/advanced-hunting-get-started.png)

>[!NOTE]
><span data-ttu-id="8679b-157">Naast de basisqueryvoorbeelden hebt u ook toegang tot [gedeelde query's](advanced-hunting-shared-queries.md) voor specifieke scenario's voor de jacht op bedreigingen.</span><span class="sxs-lookup"><span data-stu-id="8679b-157">Apart from the basic query samples, you can also access [shared queries](advanced-hunting-shared-queries.md) for specific threat hunting scenarios.</span></span> <span data-ttu-id="8679b-158">Bekijk de gedeelde query's aan de linkerkant van de pagina of de GitHub-queryopslagplaats.</span><span class="sxs-lookup"><span data-stu-id="8679b-158">Explore the shared queries on the left side of the page or the GitHub query repository.</span></span>

## <a name="access-query-language-documentation"></a><span data-ttu-id="8679b-159">Taaldocumentatie voor query's openen</span><span class="sxs-lookup"><span data-stu-id="8679b-159">Access query language documentation</span></span>

<span data-ttu-id="8679b-160">Zie [Kusto-querytaaldocumentatie](https://docs.microsoft.com/azure/kusto/query/)voor meer informatie over kusto-querytaal en ondersteunde operatoren.</span><span class="sxs-lookup"><span data-stu-id="8679b-160">For more information on Kusto query language and supported operators, see [Kusto query language documentation](https://docs.microsoft.com/azure/kusto/query/).</span></span>

## <a name="related-topics"></a><span data-ttu-id="8679b-161">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="8679b-161">Related topics</span></span>
- [<span data-ttu-id="8679b-162">Geavanceerd jachtoverzicht</span><span class="sxs-lookup"><span data-stu-id="8679b-162">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="8679b-163">Werken met queryresultaten</span><span class="sxs-lookup"><span data-stu-id="8679b-163">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="8679b-164">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="8679b-164">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="8679b-165">Zoek naar bedreigingen op verschillende apparaten en e-mails</span><span class="sxs-lookup"><span data-stu-id="8679b-165">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="8679b-166">Het schema begrijpen</span><span class="sxs-lookup"><span data-stu-id="8679b-166">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="8679b-167">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="8679b-167">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
