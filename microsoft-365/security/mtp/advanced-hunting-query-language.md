---
title: Meer informatie over de geavanceerde zoekquerytaal in Microsoft Threat Protection
description: Maak uw eerste jachtquery voor bedreigingen en leer meer over veelvoorkomende operators en andere aspecten van de geavanceerde jachtquerytaal
keywords: geavanceerde jacht, bedreigingjacht, cyberdreigingsjacht, microsoft threat protection, microsoft 365, mtp, m365, search, query, taal, leren, eerste query, telemetrie, evenementen, telemetrie, aangepaste detecties, schema, kusto, operators, gegevenstypen, powershell downloaden, query voorbeeld
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
ms.openlocfilehash: 7f2cf7f62060774343354467d27b76456f6581fc
ms.sourcegitcommit: cc3b64a91e16ccdaa9c338b9a9056dbe3963ba9e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/09/2020
ms.locfileid: "42809189"
---
# <a name="learn-the-advanced-hunting-query-language"></a><span data-ttu-id="a4286-104">Meer informatie over de geavanceerde jachtquerytaal</span><span class="sxs-lookup"><span data-stu-id="a4286-104">Learn the advanced hunting query language</span></span>

<span data-ttu-id="a4286-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="a4286-105">**Applies to:**</span></span>
- <span data-ttu-id="a4286-106">Microsoft-bedreigingsbeveiliging</span><span class="sxs-lookup"><span data-stu-id="a4286-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="a4286-107">Geavanceerde jacht is gebaseerd op de [Kusto query taal](https://docs.microsoft.com/azure/kusto/query/).</span><span class="sxs-lookup"><span data-stu-id="a4286-107">Advanced hunting is based on the [Kusto query language](https://docs.microsoft.com/azure/kusto/query/).</span></span> <span data-ttu-id="a4286-108">U kusto-syntaxis en operators gebruiken om query's te maken die informatie vinden in het [schema](advanced-hunting-schema-tables.md) dat specifiek is gestructureerd voor geavanceerde jacht.</span><span class="sxs-lookup"><span data-stu-id="a4286-108">You can use Kusto syntax and operators to construct queries that locate information in the [schema](advanced-hunting-schema-tables.md) specifically structured for advanced hunting.</span></span> <span data-ttu-id="a4286-109">Voer uw eerste query uit om deze concepten beter te begrijpen.</span><span class="sxs-lookup"><span data-stu-id="a4286-109">To understand these concepts better, run your first query.</span></span>

## <a name="try-your-first-query"></a><span data-ttu-id="a4286-110">Probeer uw eerste query</span><span class="sxs-lookup"><span data-stu-id="a4286-110">Try your first query</span></span>

<span data-ttu-id="a4286-111">Ga in microsoft 365-beveiligingscentrum naar **Jagen** om uw eerste query uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="a4286-111">In Microsoft 365 security center, go to **Hunting** to run your first query.</span></span> <span data-ttu-id="a4286-112">Gebruik het volgende voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="a4286-112">Use the following example:</span></span>

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

<span data-ttu-id="a4286-113">Zo zal het eruit zien in de geavanceerde jacht.</span><span class="sxs-lookup"><span data-stu-id="a4286-113">This is how it will look like in advanced hunting.</span></span>

![Afbeelding van geavanceerde jachtquery Microsoft Threat Protection](../../media/advanced-hunting-query-example.png)

<span data-ttu-id="a4286-115">Een korte opmerking is toegevoegd aan het begin van de query om te beschrijven waar het voor is.</span><span class="sxs-lookup"><span data-stu-id="a4286-115">A short comment has been added to the beginning of the query to describe what it is for.</span></span> <span data-ttu-id="a4286-116">Dit helpt als u later besluit de query op te slaan en te delen met anderen in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="a4286-116">This helps if you later decide to save the query and share it with others in your organization.</span></span> 

```kusto
// Finds PowerShell execution events that could involve a download
```

<span data-ttu-id="a4286-117">De query zelf begint meestal met een tabelnaam, gevolgd door`|`een reeks elementen die zijn gestart door een pipe ( ).</span><span class="sxs-lookup"><span data-stu-id="a4286-117">The query itself will typically start with a table name followed by a series of elements started by a pipe (`|`).</span></span> <span data-ttu-id="a4286-118">In dit voorbeeld beginnen we met het `DeviceProcessEvents` maken `DeviceNetworkEvents`van een unie van twee tabellen en voegen we indien nodig piped-elementen toe.</span><span class="sxs-lookup"><span data-stu-id="a4286-118">In this example, we start by creating a union of two tables,  `DeviceProcessEvents` and `DeviceNetworkEvents`, and add piped elements as needed.</span></span>

```kusto
union DeviceProcessEvents, DeviceNetworkEvents
```
<span data-ttu-id="a4286-119">Het eerste piped-element is een tijdfilter dat is gescoped tot de voorgaande zeven dagen.</span><span class="sxs-lookup"><span data-stu-id="a4286-119">The first piped element is a time filter scoped to the previous seven days.</span></span> <span data-ttu-id="a4286-120">Het tijdsbereik zo beperkt mogelijk houden, zorgt ervoor dat query's goed presteren, beheersbare resultaten retourneren en geen time-out hebben.</span><span class="sxs-lookup"><span data-stu-id="a4286-120">Keeping the time range as narrow as possible ensures that queries perform well, return manageable results, and don't time out.</span></span>

```kusto
| where Timestamp > ago(7d)
```

<span data-ttu-id="a4286-121">Het tijdsbereik wordt onmiddellijk gevolgd door een zoekopdracht naar procesbestandsnamen die de PowerShell-toepassing vertegenwoordigen.</span><span class="sxs-lookup"><span data-stu-id="a4286-121">The time range is immediately followed by a search for process file names representing the PowerShell application.</span></span>

```
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
```

<span data-ttu-id="a4286-122">Daarna wordt in de query gezocht naar tekenreeksen in opdrachtregels die doorgaans worden gebruikt om bestanden te downloaden met PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a4286-122">Afterwards, the query looks for strings in command lines that are typically used to download files using PowerShell.</span></span>

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
<span data-ttu-id="a4286-123">Nu uw query duidelijk de gegevens identificeert die u wilt zoeken, u elementen toevoegen die bepalen hoe de resultaten eruit zien.</span><span class="sxs-lookup"><span data-stu-id="a4286-123">Now that your query clearly identifies the data you want to locate, you can add elements that define what the results look like.</span></span> <span data-ttu-id="a4286-124">`project`retourneert `top` specifieke kolommen en beperkt het aantal resultaten, waardoor de resultaten goed geformatteerd en redelijk groot en gemakkelijk te verwerken zijn.</span><span class="sxs-lookup"><span data-stu-id="a4286-124">`project` returns specific columns and `top` limits the number of results, helping ensure the results well-formatted and reasonably large and easy to process.</span></span>

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

<span data-ttu-id="a4286-125">Klik op **Query uitvoeren** om de resultaten weer te geven.</span><span class="sxs-lookup"><span data-stu-id="a4286-125">Click **Run query** to see the results.</span></span> <span data-ttu-id="a4286-126">Selecteer het pictogram Uitvouwen rechtsboven in de queryeditor om u te concentreren op uw jachtquery en de resultaten.</span><span class="sxs-lookup"><span data-stu-id="a4286-126">Select the expand icon at the top right of the query editor to focus on your hunting query and the results.</span></span>

![Afbeelding van de besturingselement Uitbreiden in de geavanceerde jachtqueryeditor](../../media/advanced-hunting-expand.png)

## <a name="learn-common-query-operators-for-advanced-hunting"></a><span data-ttu-id="a4286-128">Meer informatie over veelvoorkomende queryoperators voor geavanceerde jacht</span><span class="sxs-lookup"><span data-stu-id="a4286-128">Learn common query operators for advanced hunting</span></span>

<span data-ttu-id="a4286-129">Nu u uw eerste query hebt uitgevoerd en een algemeen idee hebt van de componenten ervan, is het tijd om een beetje terug te krabbelen en een aantal basisprincipes te leren.</span><span class="sxs-lookup"><span data-stu-id="a4286-129">Now that you've run your first query and have a general idea of its components, it's time to backtrack a little bit and learn some basics.</span></span> <span data-ttu-id="a4286-130">De Kusto-querytaal die wordt gebruikt door geavanceerde jacht ondersteunt een reeks operatoren, waaronder de volgende veelvoorkomende.</span><span class="sxs-lookup"><span data-stu-id="a4286-130">The Kusto query language used by advanced hunting supports a range of operators, including the following common ones.</span></span>

| <span data-ttu-id="a4286-131">Operator</span><span class="sxs-lookup"><span data-stu-id="a4286-131">Operator</span></span> | <span data-ttu-id="a4286-132">Beschrijving en gebruik</span><span class="sxs-lookup"><span data-stu-id="a4286-132">Description and usage</span></span> |
|--|--|
| `where` | <span data-ttu-id="a4286-133">Filter een tabel naar de subset van rijen die voldoen aan een predicaat.</span><span class="sxs-lookup"><span data-stu-id="a4286-133">Filter a table to the subset of rows that satisfy a predicate.</span></span> |
| `summarize` | <span data-ttu-id="a4286-134">Een tabel maken die de inhoud van de invoertabel samenvoegt.</span><span class="sxs-lookup"><span data-stu-id="a4286-134">Produce a table that aggregates the content of the input table.</span></span> |
| `join` | <span data-ttu-id="a4286-135">Voeg de rijen van twee tabellen samen om een nieuwe tabel te vormen door waarden van de opgegeven kolom(en) van elke tabel te matchen.</span><span class="sxs-lookup"><span data-stu-id="a4286-135">Merge the rows of two tables to form a new table by matching values of the specified column(s) from each table.</span></span> |
| `count` | <span data-ttu-id="a4286-136">Retourneer het aantal records in de invoerrecordset.</span><span class="sxs-lookup"><span data-stu-id="a4286-136">Return the number of records in the input record set.</span></span> |
| `top` | <span data-ttu-id="a4286-137">De eerste N-records retourneren die zijn gesorteerd op de opgegeven kolommen.</span><span class="sxs-lookup"><span data-stu-id="a4286-137">Return the first N records sorted by the specified columns.</span></span> |
| `limit` | <span data-ttu-id="a4286-138">Terug naar het opgegeven aantal rijen.</span><span class="sxs-lookup"><span data-stu-id="a4286-138">Return up to the specified number of rows.</span></span> |
| `project` | <span data-ttu-id="a4286-139">Selecteer de kolommen die u wilt opnemen, wijzig de naam of neerzet en voeg nieuwe berekende kolommen in.</span><span class="sxs-lookup"><span data-stu-id="a4286-139">Select the columns to include, rename or drop, and insert new computed columns.</span></span> |
| `extend` | <span data-ttu-id="a4286-140">Maak berekende kolommen en appze toe aan de resultaatset.</span><span class="sxs-lookup"><span data-stu-id="a4286-140">Create calculated columns and append them to the result set.</span></span> |
| `makeset` |  <span data-ttu-id="a4286-141">Retourneer een dynamische (JSON) array van de set van verschillende waarden die Expr in de groep neemt.</span><span class="sxs-lookup"><span data-stu-id="a4286-141">Return a dynamic (JSON) array of the set of distinct values that Expr takes in the group.</span></span> |
| `find` | <span data-ttu-id="a4286-142">Zoek rijen die overeenkomen met een predicaat in een set tabellen.</span><span class="sxs-lookup"><span data-stu-id="a4286-142">Find rows that match a predicate across a set of tables.</span></span> |

<span data-ttu-id="a4286-143">Om een live voorbeeld van deze operators te zien, voer ze uit vanaf de sectie **Aan de slag** in geavanceerde jacht.</span><span class="sxs-lookup"><span data-stu-id="a4286-143">To see a live example of these operators, run them from the **Get started** section in advanced hunting.</span></span>

## <a name="understand-data-types-and-their-query-syntax-implications"></a><span data-ttu-id="a4286-144">Gegevenstypen en de implicaties van de querysyntaxis begrijpen</span><span class="sxs-lookup"><span data-stu-id="a4286-144">Understand data types and their query syntax implications</span></span>

<span data-ttu-id="a4286-145">Gegevens in geavanceerde jachttabellen worden over het algemeen ingedeeld in de volgende gegevenstypen.</span><span class="sxs-lookup"><span data-stu-id="a4286-145">Data in advanced hunting tables are generally classified into the following data types.</span></span>

| <span data-ttu-id="a4286-146">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="a4286-146">Data type</span></span> | <span data-ttu-id="a4286-147">Implicaties beschrijving en query</span><span class="sxs-lookup"><span data-stu-id="a4286-147">Description and query implications</span></span> |
|--|--|
| `datetime` | <span data-ttu-id="a4286-148">Gegevens en tijdsinformatie die doorgaans tijdstempels van gebeurtenissen vertegenwoordigen</span><span class="sxs-lookup"><span data-stu-id="a4286-148">Data and time information typically representing event timestamps</span></span> |
| `string` | <span data-ttu-id="a4286-149">Tekentekenreeks</span><span class="sxs-lookup"><span data-stu-id="a4286-149">Character string</span></span> |
| `bool` | <span data-ttu-id="a4286-150">Waar of onwaar</span><span class="sxs-lookup"><span data-stu-id="a4286-150">True or false</span></span> |
| `int` | <span data-ttu-id="a4286-151">32-bits numerieke waarde</span><span class="sxs-lookup"><span data-stu-id="a4286-151">32-bit numeric value</span></span>  |
| `long` | <span data-ttu-id="a4286-152">64-bits numerieke waarde</span><span class="sxs-lookup"><span data-stu-id="a4286-152">64-bit numeric value</span></span> |

## <a name="use-sample-queries"></a><span data-ttu-id="a4286-153">Voorbeeldquery's gebruiken</span><span class="sxs-lookup"><span data-stu-id="a4286-153">Use sample queries</span></span>

<span data-ttu-id="a4286-154">De sectie **Aan de slag** biedt een paar eenvoudige query's met veelgebruikte operators.</span><span class="sxs-lookup"><span data-stu-id="a4286-154">The **Get started** section provides a few simple queries using commonly used operators.</span></span> <span data-ttu-id="a4286-155">Probeer deze query's uit te voeren en kleine wijzigingen aan te brengen.</span><span class="sxs-lookup"><span data-stu-id="a4286-155">Try running these queries and making small modifications to them.</span></span>

![Beeld van geavanceerd jachtvenster](../../media/advanced-hunting-get-started.png)

>[!NOTE]
><span data-ttu-id="a4286-157">Naast de basisqueryvoorbeelden hebt u ook toegang tot [gedeelde query's](advanced-hunting-shared-queries.md) voor specifieke scenario's voor het jagen op bedreigingen.</span><span class="sxs-lookup"><span data-stu-id="a4286-157">Apart from the basic query samples, you can also access [shared queries](advanced-hunting-shared-queries.md) for specific threat hunting scenarios.</span></span> <span data-ttu-id="a4286-158">Bekijk de gedeelde query's aan de linkerkant van de pagina of de GitHub-queryrepository.</span><span class="sxs-lookup"><span data-stu-id="a4286-158">Explore the shared queries on the left side of the page or the GitHub query repository.</span></span>

## <a name="access-query-language-documentation"></a><span data-ttu-id="a4286-159">Documentatie voor querytaal openen</span><span class="sxs-lookup"><span data-stu-id="a4286-159">Access query language documentation</span></span>

<span data-ttu-id="a4286-160">Zie [Kusto-querytaaldocumentatie](https://docs.microsoft.com/azure/kusto/query/)voor meer informatie over Kusto-querytaal en ondersteunde operatoren.</span><span class="sxs-lookup"><span data-stu-id="a4286-160">For more information on Kusto query language and supported operators, see [Kusto query language documentation](https://docs.microsoft.com/azure/kusto/query/).</span></span>

## <a name="related-topics"></a><span data-ttu-id="a4286-161">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="a4286-161">Related topics</span></span>
- [<span data-ttu-id="a4286-162">Proactief jagen op bedreigingen</span><span class="sxs-lookup"><span data-stu-id="a4286-162">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="a4286-163">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="a4286-163">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="a4286-164">Op zoek naar bedreigingen op verschillende apparaten en e-mails</span><span class="sxs-lookup"><span data-stu-id="a4286-164">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="a4286-165">Het schema begrijpen</span><span class="sxs-lookup"><span data-stu-id="a4286-165">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="a4286-166">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="a4286-166">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
