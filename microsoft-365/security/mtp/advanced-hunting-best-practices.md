---
title: Geavanceerde ervaring met best practices in Microsoft Threat Protection
description: Ontdek hoe u Fast, efficient en error-free Threat jacht kunt maken bij gebruik van geavanceerde jacht
keywords: geavanceerde jacht, bedreigings jacht, Cyber Threat jacht, Microsoft Threat Protection, Microsoft 365, MTP, m365, Search, query, telemetrie, aangepaste detectie, schema, kusto, code voor timeout, opdracht lijnen
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
ms.openlocfilehash: f66b17fbdaaa58cf12bd0373d0fece59349c3a48
ms.sourcegitcommit: 51097b18d94da20aa727ebfbeb6ec84c263b25c3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/12/2020
ms.locfileid: "46649497"
---
# <a name="advanced-hunting-query-best-practices"></a><span data-ttu-id="ab670-104">Best practices voor geavanceerde zoekactie</span><span class="sxs-lookup"><span data-stu-id="ab670-104">Advanced hunting query best practices</span></span>

<span data-ttu-id="ab670-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="ab670-105">**Applies to:**</span></span>
- <span data-ttu-id="ab670-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="ab670-106">Microsoft Threat Protection</span></span>



## <a name="optimize-query-performance"></a><span data-ttu-id="ab670-107">Queryprestaties optimaliseren</span><span class="sxs-lookup"><span data-stu-id="ab670-107">Optimize query performance</span></span>
<span data-ttu-id="ab670-108">Pas deze aanbevelingen toe om resultaten sneller te vinden en time-outs te voorkomen tijdens het uitvoeren van complexe query's:</span><span class="sxs-lookup"><span data-stu-id="ab670-108">Apply these recommendations to get results faster and avoid timeouts while running complex queries:</span></span>
- <span data-ttu-id="ab670-109">Altijd gebruiken `limit` om extreem grote resultaatsets te vermijden.</span><span class="sxs-lookup"><span data-stu-id="ab670-109">When trying new queries, always use `limit` to avoid extremely large result sets.</span></span> <span data-ttu-id="ab670-110">U kunt ook de grootte van de resultatenset in eerste instantie beoordelen `count` .</span><span class="sxs-lookup"><span data-stu-id="ab670-110">You can also initially assess the size of the result set using `count`.</span></span>
- <span data-ttu-id="ab670-111">Gebruik eerst time filters.</span><span class="sxs-lookup"><span data-stu-id="ab670-111">Use time filters first.</span></span> <span data-ttu-id="ab670-112">In het ideale geval beperkt u de query's tot dagen.</span><span class="sxs-lookup"><span data-stu-id="ab670-112">Ideally, limit your queries to even days.</span></span>
- <span data-ttu-id="ab670-113">Plaats filters waarvan de meeste gegevens aan het begin van de query moeten worden verwijderd, rechts na het filter tijd.</span><span class="sxs-lookup"><span data-stu-id="ab670-113">Put filters that are expected to remove most of the data in the beginning of the query, right after the time filter.</span></span>
- <span data-ttu-id="ab670-114">Gebruik de `has` operator over `contains` Wanneer u op zoek bent naar volledige tokens.</span><span class="sxs-lookup"><span data-stu-id="ab670-114">Use the `has` operator over `contains` when looking for full tokens.</span></span>
- <span data-ttu-id="ab670-115">In een specifieke kolom zoeken in plaats van volledige tekst zoekopdrachten in alle kolommen uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="ab670-115">Look in a specific column rather than running full text searches across all columns.</span></span>
- <span data-ttu-id="ab670-116">Geef bij het samenvoegen van tabellen de tabel op met minder rijen.</span><span class="sxs-lookup"><span data-stu-id="ab670-116">When joining tables, specify the table with fewer rows first.</span></span>
- <span data-ttu-id="ab670-117">`project`alleen de benodigde kolommen van tabellen waarvan u lid bent geworden.</span><span class="sxs-lookup"><span data-stu-id="ab670-117">`project` only the necessary columns from tables you've joined.</span></span>

>[!Tip]
><span data-ttu-id="ab670-118">Lees voor meer informatie over het verbeteren van de prestaties van query's het artikel [Best practices voor Kusto query](https://docs.microsoft.com/azure/kusto/query/best-practices).</span><span class="sxs-lookup"><span data-stu-id="ab670-118">For more guidance on improving query performance, read [Kusto query best practices](https://docs.microsoft.com/azure/kusto/query/best-practices).</span></span>

## <a name="query-tips-and-pitfalls"></a><span data-ttu-id="ab670-119">Query tips en valkuilen</span><span class="sxs-lookup"><span data-stu-id="ab670-119">Query tips and pitfalls</span></span>

### <a name="queries-with-process-ids"></a><span data-ttu-id="ab670-120">Query's met proces-Id's</span><span class="sxs-lookup"><span data-stu-id="ab670-120">Queries with process IDs</span></span>
<span data-ttu-id="ab670-121">Proces-Id's in Windows worden gerecycled en opnieuw gebruikt voor nieuwe processen.</span><span class="sxs-lookup"><span data-stu-id="ab670-121">Process IDs (PIDs) are recycled in Windows and reused for new processes.</span></span> <span data-ttu-id="ab670-122">Ze kunnen op hun eigen manier geen unieke id's voor specifieke processen gebruiken.</span><span class="sxs-lookup"><span data-stu-id="ab670-122">On their own, they can't serve as unique identifiers for specific processes.</span></span>

<span data-ttu-id="ab670-123">Als u een unieke aanduiding wilt krijgen voor een proces op een specifieke computer, gebruikt u de proces-ID samen met de Aanmaaktijd van het proces.</span><span class="sxs-lookup"><span data-stu-id="ab670-123">To get a unique identifier for a process on a specific machine, use the process ID together with the process creation time.</span></span> <span data-ttu-id="ab670-124">Wanneer u gegevens rond processen samenvoegt of samenvoegt, neemt u kolommen op voor de machine-id (of `DeviceId` `DeviceName` ), de proces-id ( `ProcessId` of `InitiatingProcessId` ) en de tijd waarop het proces is gemaakt ( `ProcessCreationTime` of `InitiatingProcessCreationTime` ).</span><span class="sxs-lookup"><span data-stu-id="ab670-124">When you join or summarize data around processes, include columns for the machine identifier (either `DeviceId` or `DeviceName`), the process ID (`ProcessId` or `InitiatingProcessId`), and the process creation time (`ProcessCreationTime` or `InitiatingProcessCreationTime`)</span></span>

<span data-ttu-id="ab670-125">Met de volgende voorbeeldquery vindt u processen die toegang hebben tot meer dan 10 IP-adressen via poort 445 (SMB), mogelijk met de scanfunctie voor bestandsshares.</span><span class="sxs-lookup"><span data-stu-id="ab670-125">The following example query finds processes that access more than 10 IP addresses over port 445 (SMB), possibly scanning for file shares.</span></span>

<span data-ttu-id="ab670-126">Voorbeeldquery:</span><span class="sxs-lookup"><span data-stu-id="ab670-126">Example query:</span></span>
```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId, InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

<span data-ttu-id="ab670-127">De query geeft een samenvatting van beide `InitiatingProcessId` `InitiatingProcessCreationTime` processen weer, zodat de query één proces uitziet, zonder meerdere processen met hetzelfde proces-id te kunnen combineren.</span><span class="sxs-lookup"><span data-stu-id="ab670-127">The query summarizes by both `InitiatingProcessId` and `InitiatingProcessCreationTime` so that it looks at a single process, without mixing multiple processes with the same process ID.</span></span>

### <a name="queries-with-command-lines"></a><span data-ttu-id="ab670-128">Query's met opdrachtregels</span><span class="sxs-lookup"><span data-stu-id="ab670-128">Queries with command lines</span></span>

<span data-ttu-id="ab670-129">De opdrachtregels kunnen variëren.</span><span class="sxs-lookup"><span data-stu-id="ab670-129">Command lines can vary.</span></span> <span data-ttu-id="ab670-130">Gebruik indien van toepassing een filter voor de bestandsnamen en voer fuzz treffers uit.</span><span class="sxs-lookup"><span data-stu-id="ab670-130">When applicable, filter on file names and do fuzzy matching.</span></span>

<span data-ttu-id="ab670-131">U kunt op verschillende manieren een opdrachtregel maken om een taak uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="ab670-131">There are numerous ways to construct a command line to accomplish a task.</span></span> <span data-ttu-id="ab670-132">Een aanvaller kan bijvoorbeeld verwijzen naar een afbeeldingsbestand met of zonder een bestandsextensie, met behulp van omgevingsvariabelen of met aanhalingstekens.</span><span class="sxs-lookup"><span data-stu-id="ab670-132">For example, an attacker could reference an image file with or without a path, without a file extension, using environment variables, or with quotes.</span></span> <span data-ttu-id="ab670-133">Daarnaast kan de aanvaller ook de volgorde van parameters wijzigen of meerdere aanhalingstekens en spaties toevoegen.</span><span class="sxs-lookup"><span data-stu-id="ab670-133">In addition, the attacker could also change the order of parameters or add multiple quotes and spaces.</span></span>

<span data-ttu-id="ab670-134">Als u meer duurzame query's wilt maken met behulp van opdrachtregels, moet u de volgende procedures toepassen:</span><span class="sxs-lookup"><span data-stu-id="ab670-134">To create more durable queries using command lines, apply the following practices:</span></span>

- <span data-ttu-id="ab670-135">Identificeer de bekende processen (zoals *net.exe* of *psexec.exe*) door te zoeken in de bestandsnaam velden, in plaats van te filteren op het opdrachtregel veld.</span><span class="sxs-lookup"><span data-stu-id="ab670-135">Identify the known processes (such as *net.exe* or *psexec.exe*) by matching on the filename fields, instead of filtering on the command-line field.</span></span>
- <span data-ttu-id="ab670-136">Wanneer u een query uitvoert voor opdrachtregelargumenten, zoekt u niet naar een exacte overeenkomst voor meerdere niet-gerelateerde argumenten in een bepaalde volgorde.</span><span class="sxs-lookup"><span data-stu-id="ab670-136">When querying for command-line arguments, don't look for an exact match on multiple unrelated arguments in a certain order.</span></span> <span data-ttu-id="ab670-137">Gebruik in plaats daarvan reguliere expressies of gebruik van meerdere aparte operatoren.</span><span class="sxs-lookup"><span data-stu-id="ab670-137">Instead, use regular expressions or use multiple separate contains operators.</span></span>
- <span data-ttu-id="ab670-138">Gebruik hoofdlettergevoelige overeenkomsten.</span><span class="sxs-lookup"><span data-stu-id="ab670-138">Use case insensitive matches.</span></span> <span data-ttu-id="ab670-139">Gebruik bijvoorbeeld, `=~` `in~` en `contains` in plaats van `==` , `in` en`contains_cs`</span><span class="sxs-lookup"><span data-stu-id="ab670-139">For example, use `=~`, `in~`, and `contains` instead of `==`, `in`, and `contains_cs`</span></span>
- <span data-ttu-id="ab670-140">Als u de opdrachtregel wilt beperken, kunt u aanhalingstekens verwijderen, komma's vervangen door spaties en meerdere opeenvolgende spaties vervangen door één spatie.</span><span class="sxs-lookup"><span data-stu-id="ab670-140">To mitigate DOS command-line obfuscation techniques, consider removing quotes, replacing commas with spaces, and replacing multiple consecutive spaces with a single space.</span></span> <span data-ttu-id="ab670-141">Houd er rekening mee dat er andere gecompliceerde functies zijn voor het maken van donkere informatie, maar deze kunnen de meest voorkomende methoden helpen.</span><span class="sxs-lookup"><span data-stu-id="ab670-141">Note that there are more complex DOS obfuscation techniques that require other approaches, but these can help address the most common ones.</span></span>

<span data-ttu-id="ab670-142">In de volgende voorbeelden ziet u verschillende manieren om een query te maken waarmee wordt gezocht naar het bestand *net.exe* de Windows Defender Firewall-service te stoppen:</span><span class="sxs-lookup"><span data-stu-id="ab670-142">The following examples show various ways to construct a query that looks for the file *net.exe* to stop the Windows Defender Firewall service:</span></span>

```kusto
// Non-durable query - do not use
DeviceProcessEvents
| where ProcessCommandLine == "net stop MpsSvc"
| limit 10

// Better query - filters on filename, does case-insensitive matches
DeviceProcessEvents
| where Timestamp > ago(7d) and FileName in~ ("net.exe", "net1.exe") and ProcessCommandLine contains "stop" and ProcessCommandLine contains "MpsSvc" 

// Best query also ignores quotes
DeviceProcessEvents
| where Timestamp > ago(7d) and FileName in~ ("net.exe", "net1.exe")
| extend CanonicalCommandLine=replace("\"", "", ProcessCommandLine)
| where CanonicalCommandLine contains "stop" and CanonicalCommandLine contains "MpsSvc" 
```
## <a name="related-topics"></a><span data-ttu-id="ab670-143">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="ab670-143">Related topics</span></span>
- [<span data-ttu-id="ab670-144">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="ab670-144">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="ab670-145">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="ab670-145">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="ab670-146">Werken met queryresultaten</span><span class="sxs-lookup"><span data-stu-id="ab670-146">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="ab670-147">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="ab670-147">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="ab670-148">Jacht op apparaten, e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="ab670-148">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="ab670-149">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="ab670-149">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
