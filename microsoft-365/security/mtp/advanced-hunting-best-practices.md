---
title: Geavanceerde jachtbest practices in Microsoft Threat Protection
description: Leer hoe u snel, efficiënt en foutloos zoeken naar bedreigingen maken bij het gebruik van geavanceerde jacht
keywords: geavanceerde jacht, dreigingjacht, cyberdreigingsjacht, bescherming tegen microsoft-bedreigingen, microsoft 365, mtp, m365, zoeken, query, telemetrie, aangepaste detecties, schema, kusto, vermijd time-out, opdrachtregels, proces-id
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
ms.openlocfilehash: a859aa201b43813d6c66a797cbfee160051d5103
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/24/2020
ms.locfileid: "42805302"
---
# <a name="advanced-hunting-query-best-practices"></a><span data-ttu-id="e5165-104">Aanbevolen procedures voor geavanceerde jachtquery's</span><span class="sxs-lookup"><span data-stu-id="e5165-104">Advanced hunting query best practices</span></span>

<span data-ttu-id="e5165-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="e5165-105">**Applies to:**</span></span>
- <span data-ttu-id="e5165-106">Microsoft-bedreigingsbeveiliging</span><span class="sxs-lookup"><span data-stu-id="e5165-106">Microsoft Threat Protection</span></span>



## <a name="optimize-query-performance"></a><span data-ttu-id="e5165-107">Queryprestaties optimaliseren</span><span class="sxs-lookup"><span data-stu-id="e5165-107">Optimize query performance</span></span>
<span data-ttu-id="e5165-108">Pas deze aanbevelingen toe om sneller resultaten te krijgen en time-outs te voorkomen tijdens het uitvoeren van complexe query's:</span><span class="sxs-lookup"><span data-stu-id="e5165-108">Apply these recommendations to get results faster and avoid timeouts while running complex queries:</span></span>
- <span data-ttu-id="e5165-109">Wanneer u nieuwe query's probeert, gebruikt u `limit` altijd om extreem grote resultaatsets te voorkomen.</span><span class="sxs-lookup"><span data-stu-id="e5165-109">When trying new queries, always use `limit` to avoid extremely large result sets.</span></span> <span data-ttu-id="e5165-110">U ook in eerste instantie de `count`grootte van de resultaatset beoordelen met behulp van.</span><span class="sxs-lookup"><span data-stu-id="e5165-110">You can also initially assess the size of the result set using `count`.</span></span>
- <span data-ttu-id="e5165-111">Gebruik eerst tijdfilters.</span><span class="sxs-lookup"><span data-stu-id="e5165-111">Use time filters first.</span></span> <span data-ttu-id="e5165-112">In het ideale plaats u uw query's beperken tot zelfs dagen.</span><span class="sxs-lookup"><span data-stu-id="e5165-112">Ideally, limit your queries to even days.</span></span>
- <span data-ttu-id="e5165-113">Zet filters die naar verwachting de meeste gegevens in het begin van de query verwijderen, direct na het tijdsfilter.</span><span class="sxs-lookup"><span data-stu-id="e5165-113">Put filters that are expected to remove most of the data in the beginning of the query, right after the time filter.</span></span>
- <span data-ttu-id="e5165-114">Gebruik `has` de `contains` operator over bij het zoeken naar volledige tokens.</span><span class="sxs-lookup"><span data-stu-id="e5165-114">Use the `has` operator over `contains` when looking for full tokens.</span></span>
- <span data-ttu-id="e5165-115">Zoek in een specifieke kolom in plaats van zoekopdrachten in volledige tekst uit te voeren in alle kolommen.</span><span class="sxs-lookup"><span data-stu-id="e5165-115">Look in a specific column rather than running full text searches across all columns.</span></span>
- <span data-ttu-id="e5165-116">Wanneer u tabellen aansluit, geeft u eerst de tabel op met minder rijen.</span><span class="sxs-lookup"><span data-stu-id="e5165-116">When joining tables, specify the table with fewer rows first.</span></span>
- <span data-ttu-id="e5165-117">`project`alleen de benodigde kolommen van tabellen waar toe u bent verbonden.</span><span class="sxs-lookup"><span data-stu-id="e5165-117">`project` only the necessary columns from tables you've joined.</span></span>

>[!Tip]
><span data-ttu-id="e5165-118">Lees [kusto query best practices](https://docs.microsoft.com/azure/kusto/query/best-practices)voor meer richtlijnen voor het verbeteren van de queryprestaties.</span><span class="sxs-lookup"><span data-stu-id="e5165-118">For more guidance on improving query performance, read [Kusto query best practices](https://docs.microsoft.com/azure/kusto/query/best-practices).</span></span>

## <a name="query-tips-and-pitfalls"></a><span data-ttu-id="e5165-119">Querytips en valkuilen</span><span class="sxs-lookup"><span data-stu-id="e5165-119">Query tips and pitfalls</span></span>

### <a name="queries-with-process-ids"></a><span data-ttu-id="e5165-120">Query's met proces-i-d's</span><span class="sxs-lookup"><span data-stu-id="e5165-120">Queries with process IDs</span></span>
<span data-ttu-id="e5165-121">Proces-id's (PID's) worden gerecycled in Windows en hergebruikt voor nieuwe processen.</span><span class="sxs-lookup"><span data-stu-id="e5165-121">Process IDs (PIDs) are recycled in Windows and reused for new processes.</span></span> <span data-ttu-id="e5165-122">Op zichzelf kunnen ze niet dienen als unieke id's voor specifieke processen.</span><span class="sxs-lookup"><span data-stu-id="e5165-122">On their own, they can't serve as unique identifiers for specific processes.</span></span>

<span data-ttu-id="e5165-123">Als u een unieke id voor een proces op een specifieke machine wilt krijgen, gebruikt u de proces-ID samen met de procescreatietijd.</span><span class="sxs-lookup"><span data-stu-id="e5165-123">To get a unique identifier for a process on a specific machine, use the process ID together with the process creation time.</span></span> <span data-ttu-id="e5165-124">Wanneer u gegevens rond processen aansluit of samenvat, `DeviceId` `DeviceName`neemt u kolommen`ProcessId` `InitiatingProcessId`op voor de machine-id (of), de proces-ID (of ) en de procescreatietijd (of`ProcessCreationTime` `InitiatingProcessCreationTime`)</span><span class="sxs-lookup"><span data-stu-id="e5165-124">When you join or summarize data around processes, include columns for the machine identifier (either `DeviceId` or `DeviceName`), the process ID (`ProcessId` or `InitiatingProcessId`), and the process creation time (`ProcessCreationTime` or `InitiatingProcessCreationTime`)</span></span>

<span data-ttu-id="e5165-125">In de volgende voorbeeldquery worden processen gevonden die toegang hebben tot meer dan 10 IP-adressen via poort 445 (SMB), mogelijk scannen op bestandsshares.</span><span class="sxs-lookup"><span data-stu-id="e5165-125">The following example query finds processes that access more than 10 IP addresses over port 445 (SMB), possibly scanning for file shares.</span></span>

<span data-ttu-id="e5165-126">Voorbeeldquery:</span><span class="sxs-lookup"><span data-stu-id="e5165-126">Example query:</span></span>
```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId, InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

<span data-ttu-id="e5165-127">De query wordt `InitiatingProcessId` samengevat `InitiatingProcessCreationTime` door beide en zodat het kijkt naar een enkel proces, zonder het mengen van meerdere processen met dezelfde proces-ID.</span><span class="sxs-lookup"><span data-stu-id="e5165-127">The query summarizes by both `InitiatingProcessId` and `InitiatingProcessCreationTime` so that it looks at a single process, without mixing multiple processes with the same process ID.</span></span>

### <a name="queries-with-command-lines"></a><span data-ttu-id="e5165-128">Query's met opdrachtregels</span><span class="sxs-lookup"><span data-stu-id="e5165-128">Queries with command lines</span></span>

<span data-ttu-id="e5165-129">Opdrachtregels kunnen variëren.</span><span class="sxs-lookup"><span data-stu-id="e5165-129">Command lines can vary.</span></span> <span data-ttu-id="e5165-130">Filter indien van toepassing bestandsnamen en doe fuzzy matching.</span><span class="sxs-lookup"><span data-stu-id="e5165-130">When applicable, filter on file names and do fuzzy matching.</span></span>

<span data-ttu-id="e5165-131">Er zijn tal van manieren om een opdrachtregel te bouwen om een taak te volbrengen.</span><span class="sxs-lookup"><span data-stu-id="e5165-131">There are numerous ways to construct a command line to accomplish a task.</span></span> <span data-ttu-id="e5165-132">Een aanvaller kan bijvoorbeeld verwijzen naar een afbeeldingsbestand met of zonder pad, zonder bestandsextensie, met omgevingsvariabelen of met aanhalingstekens.</span><span class="sxs-lookup"><span data-stu-id="e5165-132">For example, an attacker could reference an image file with or without a path, without a file extension, using environment variables, or with quotes.</span></span> <span data-ttu-id="e5165-133">Daarnaast kan de aanvaller ook de volgorde van parameters wijzigen of meerdere aanhalingstekens en spaties toevoegen.</span><span class="sxs-lookup"><span data-stu-id="e5165-133">In addition, the attacker could also change the order of parameters or add multiple quotes and spaces.</span></span>

<span data-ttu-id="e5165-134">Als u duurzamere query's wilt maken met opdrachtregels, past u de volgende procedures toe:</span><span class="sxs-lookup"><span data-stu-id="e5165-134">To create more durable queries using command lines, apply the following practices:</span></span>

- <span data-ttu-id="e5165-135">Identificeer de bekende processen (zoals *net.exe* of *psexec.exe)* door te matchen op de bestandsnaamvelden, in plaats van te filteren op het veld opdrachtregel.</span><span class="sxs-lookup"><span data-stu-id="e5165-135">Identify the known processes (such as *net.exe* or *psexec.exe*) by matching on the filename fields, instead of filtering on the command-line field.</span></span>
- <span data-ttu-id="e5165-136">Wanneer u naar opdrachtregelargumenten zoekt, zoekt u niet naar een exacte overeenkomst voor meerdere niet-gerelateerde argumenten in een bepaalde volgorde.</span><span class="sxs-lookup"><span data-stu-id="e5165-136">When querying for command-line arguments, don't look for an exact match on multiple unrelated arguments in a certain order.</span></span> <span data-ttu-id="e5165-137">Gebruik in plaats daarvan reguliere expressies of gebruik meerdere afzonderlijke operatoren.</span><span class="sxs-lookup"><span data-stu-id="e5165-137">Instead, use regular expressions or use multiple separate contains operators.</span></span>
- <span data-ttu-id="e5165-138">Gebruik geval ongevoelige overeenkomsten.</span><span class="sxs-lookup"><span data-stu-id="e5165-138">Use case insensitive matches.</span></span> <span data-ttu-id="e5165-139">Gebruik bijvoorbeeld `=~`, `in~`en `contains` in `==` `in`plaats van , en`contains_cs`</span><span class="sxs-lookup"><span data-stu-id="e5165-139">For example, use `=~`, `in~`, and `contains` instead of `==`, `in`, and `contains_cs`</span></span>
- <span data-ttu-id="e5165-140">Als u de obfuscation-technieken van DOS-opdrachtregel wilt beperken, u overwegen offertes te verwijderen, komma's te vervangen door spaties en meerdere opeenvolgende spaties te vervangen door één spatie.</span><span class="sxs-lookup"><span data-stu-id="e5165-140">To mitigate DOS command-line obfuscation techniques, consider removing quotes, replacing commas with spaces, and replacing multiple consecutive spaces with a single space.</span></span> <span data-ttu-id="e5165-141">Merk op dat er meer complexe DOS-verduisteringstechnieken zijn die andere benaderingen vereisen, maar deze kunnen helpen bij het aanpakken van de meest voorkomende.</span><span class="sxs-lookup"><span data-stu-id="e5165-141">Note that there are more complex DOS obfuscation techniques that require other approaches, but these can help address the most common ones.</span></span>

<span data-ttu-id="e5165-142">In de volgende voorbeelden worden verschillende manieren weergegeven om een query te maken die zoekt naar het bestand *net.exe* om de Windows Defender Firewall-service te stoppen:</span><span class="sxs-lookup"><span data-stu-id="e5165-142">The following examples show various ways to construct a query that looks for the file *net.exe* to stop the Windows Defender Firewall service:</span></span>

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
## <a name="related-topics"></a><span data-ttu-id="e5165-143">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="e5165-143">Related topics</span></span>
- [<span data-ttu-id="e5165-144">Proactief op zoek naar bedreigingen</span><span class="sxs-lookup"><span data-stu-id="e5165-144">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="e5165-145">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="e5165-145">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="e5165-146">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="e5165-146">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="e5165-147">Zoek naar bedreigingen op verschillende apparaten en e-mails</span><span class="sxs-lookup"><span data-stu-id="e5165-147">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="e5165-148">Het schema begrijpen</span><span class="sxs-lookup"><span data-stu-id="e5165-148">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
