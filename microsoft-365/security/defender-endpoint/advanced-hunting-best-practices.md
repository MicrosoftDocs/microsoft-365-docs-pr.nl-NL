---
title: Best practices voor query's voor geavanceerde jacht
description: Meer informatie over het maken van snelle, efficiënte en foutloze zoekquery's voor bedreigingen bij het gebruik van geavanceerde jacht
keywords: advanced hunting, threat hunting, cyber threat hunting, mdatp, microsoft defender atp, wdatp search, query, telemetry, custom detections, schema, kusto, avoid timeout, command lines, process id
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
ms.collection: m365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6259ac1c5804b244c825a1bb54401640fdefaf34
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058458"
---
# <a name="advanced-hunting-query-best-practices"></a><span data-ttu-id="d89bf-104">Geavanceerde best practices voor query's</span><span class="sxs-lookup"><span data-stu-id="d89bf-104">Advanced hunting query best practices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d89bf-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="d89bf-105">**Applies to:**</span></span>
- [<span data-ttu-id="d89bf-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="d89bf-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="d89bf-107">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="d89bf-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d89bf-108">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="d89bf-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-bestpractices-abovefoldlink)

## <a name="optimize-query-performance"></a><span data-ttu-id="d89bf-109">Prestaties van query's optimaliseren</span><span class="sxs-lookup"><span data-stu-id="d89bf-109">Optimize query performance</span></span>

<span data-ttu-id="d89bf-110">Pas deze aanbevelingen toe om sneller resultaten te krijgen en time-outs te vermijden tijdens het uitvoeren van complexe query's.</span><span class="sxs-lookup"><span data-stu-id="d89bf-110">Apply these recommendations to get results faster and avoid timeouts while running complex queries.</span></span>

- <span data-ttu-id="d89bf-111">Gebruik bij het proberen van nieuwe query's `limit` altijd om zeer grote resultatensets te voorkomen.</span><span class="sxs-lookup"><span data-stu-id="d89bf-111">When trying new queries, always use `limit` to avoid extremely large result sets.</span></span> <span data-ttu-id="d89bf-112">U kunt ook in eerste instantie de grootte van de resultatenset beoordelen met `count` behulp van .</span><span class="sxs-lookup"><span data-stu-id="d89bf-112">You can also initially assess the size of the result set using `count`.</span></span>
- <span data-ttu-id="d89bf-113">Gebruik eerst tijdfilters.</span><span class="sxs-lookup"><span data-stu-id="d89bf-113">Use time filters first.</span></span> <span data-ttu-id="d89bf-114">Beperk uw query's in het ideale ideaal tot zeven dagen.</span><span class="sxs-lookup"><span data-stu-id="d89bf-114">Ideally, limit your queries to seven days.</span></span>
- <span data-ttu-id="d89bf-115">Filters instellen die naar verwachting de meeste gegevens aan het begin van de query verwijderen, direct na het tijdfilter.</span><span class="sxs-lookup"><span data-stu-id="d89bf-115">Put filters that are expected to remove most of the data in the beginning of the query, right after the time filter.</span></span>
- <span data-ttu-id="d89bf-116">Gebruik de `has` operator over wanneer u op zoek bent naar volledige `contains` tokens.</span><span class="sxs-lookup"><span data-stu-id="d89bf-116">Use the `has` operator over `contains` when looking for full tokens.</span></span>
- <span data-ttu-id="d89bf-117">Zoek in een specifieke kolom in plaats van volledige tekst te zoeken in alle kolommen.</span><span class="sxs-lookup"><span data-stu-id="d89bf-117">Look in a specific column rather than running full text searches across all columns.</span></span>
- <span data-ttu-id="d89bf-118">Geef bij het deelnemen aan tabellen eerst de tabel op met minder rijen.</span><span class="sxs-lookup"><span data-stu-id="d89bf-118">When joining tables, specify the table with fewer rows first.</span></span>
- <span data-ttu-id="d89bf-119">`project` alleen de benodigde kolommen uit tabellen die u hebt samengevoegd.</span><span class="sxs-lookup"><span data-stu-id="d89bf-119">`project` only the necessary columns from tables you've joined.</span></span>

>[!TIP]
><span data-ttu-id="d89bf-120">Lees [Kusto query best practices](https://docs.microsoft.com/azure/kusto/query/best-practices)voor meer informatie over het verbeteren van queryprestaties.</span><span class="sxs-lookup"><span data-stu-id="d89bf-120">For more guidance on improving query performance, read [Kusto query best practices](https://docs.microsoft.com/azure/kusto/query/best-practices).</span></span>

## <a name="query-tips-and-pitfalls"></a><span data-ttu-id="d89bf-121">Querytips en valkuilen</span><span class="sxs-lookup"><span data-stu-id="d89bf-121">Query tips and pitfalls</span></span>

### <a name="queries-with-process-ids"></a><span data-ttu-id="d89bf-122">Query's met proces-IDs</span><span class="sxs-lookup"><span data-stu-id="d89bf-122">Queries with process IDs</span></span>

<span data-ttu-id="d89bf-123">Proces-ID's (PID's) worden in Windows hergebruikt en opnieuw gebruikt voor nieuwe processen.</span><span class="sxs-lookup"><span data-stu-id="d89bf-123">Process IDs (PIDs) are recycled in Windows and reused for new processes.</span></span> <span data-ttu-id="d89bf-124">Op zichzelf kunnen ze niet fungeren als unieke id's voor specifieke processen.</span><span class="sxs-lookup"><span data-stu-id="d89bf-124">On their own, they can't serve as unique identifiers for specific processes.</span></span> <span data-ttu-id="d89bf-125">Als u een unieke id wilt krijgen voor een proces op een bepaald apparaat, gebruikt u de proces-id samen met de tijd voor het maken van het proces.</span><span class="sxs-lookup"><span data-stu-id="d89bf-125">To get a unique identifier for a process on a specific device, use the process ID together with the process creation time.</span></span> <span data-ttu-id="d89bf-126">Wanneer u gegevens rond processen bij elkaar opeet of samenvatten, kunt u kolommen voor de apparaataanduiding (of), de proces-id (of) en de tijd voor het maken `DeviceId` `DeviceName` van het proces `ProcessId` `InitiatingProcessId` `ProcessCreationTime` `InitiatingProcessCreationTime` (of) opnemen.</span><span class="sxs-lookup"><span data-stu-id="d89bf-126">When you join or summarize data around processes, include columns for the device identifier (either `DeviceId` or `DeviceName`), the process ID (`ProcessId` or `InitiatingProcessId`), and the process creation time (`ProcessCreationTime` or `InitiatingProcessCreationTime`).</span></span>

<span data-ttu-id="d89bf-127">In de volgende voorbeeldquery worden processen gevonden die toegang hebben tot meer dan 10 IP-adressen via poort 445 (SMB), mogelijk scannen op bestandsaandelen.</span><span class="sxs-lookup"><span data-stu-id="d89bf-127">The following example query finds processes that access more than 10 IP addresses over port 445 (SMB), possibly scanning for file shares.</span></span>

```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId, InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

<span data-ttu-id="d89bf-128">De query wordt op beide manieren samengevat, zodat er naar één proces wordt ge kijkt, zonder dat meerdere processen met dezelfde `InitiatingProcessId` `InitiatingProcessCreationTime` proces-id worden vermengd.</span><span class="sxs-lookup"><span data-stu-id="d89bf-128">The query summarizes by both `InitiatingProcessId` and `InitiatingProcessCreationTime` so that it looks at a single process, without mixing multiple processes with the same process ID.</span></span>

### <a name="queries-with-command-lines"></a><span data-ttu-id="d89bf-129">Query's met opdrachtregels</span><span class="sxs-lookup"><span data-stu-id="d89bf-129">Queries with command lines</span></span>

<span data-ttu-id="d89bf-130">Opdrachtlijnen kunnen variëren.</span><span class="sxs-lookup"><span data-stu-id="d89bf-130">Command lines can vary.</span></span> <span data-ttu-id="d89bf-131">Filter indien van toepassing op bestandsnamen en doe fuzzy matching.</span><span class="sxs-lookup"><span data-stu-id="d89bf-131">When applicable, filter on file names and do fuzzy matching.</span></span>

<span data-ttu-id="d89bf-132">Er zijn verschillende manieren om een opdrachtregel te maken om een taak uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="d89bf-132">There are numerous ways to construct a command line to accomplish a task.</span></span> <span data-ttu-id="d89bf-133">Een aanvaller kan bijvoorbeeld verwijzen naar een afbeeldingsbestand met of zonder pad, zonder bestandsextensie, met omgevingsvariabelen of met aanhalingstekens.</span><span class="sxs-lookup"><span data-stu-id="d89bf-133">For example, an attacker could reference an image file with or without a path, without a file extension, using environment variables, or with quotes.</span></span> <span data-ttu-id="d89bf-134">Daarnaast kan de aanvaller ook de volgorde van parameters wijzigen of meerdere aanhalingstekens en spaties toevoegen.</span><span class="sxs-lookup"><span data-stu-id="d89bf-134">In addition, the attacker could also change the order of parameters or add multiple quotes and spaces.</span></span>

<span data-ttu-id="d89bf-135">Als u duurzamere query's wilt maken met opdrachtlijnen, moet u de volgende procedures toepassen:</span><span class="sxs-lookup"><span data-stu-id="d89bf-135">To create more durable queries using command lines, apply the following practices:</span></span>

- <span data-ttu-id="d89bf-136">Identificeer de bekende processen  (zoalsnet.exeof *psexec.exe)* door op de bestandsnaamvelden te matchen in plaats van te filteren op het opdrachtregelveld.</span><span class="sxs-lookup"><span data-stu-id="d89bf-136">Identify the known processes (such as *net.exe* or *psexec.exe*) by matching on the filename fields, instead of filtering on the command-line field.</span></span>
- <span data-ttu-id="d89bf-137">Wanneer u query's uitvoert voor opdrachtregelargumenten, moet u niet zoeken naar een exacte overeenkomst voor meerdere niet-gerelateerde argumenten in een bepaalde volgorde.</span><span class="sxs-lookup"><span data-stu-id="d89bf-137">When querying for command-line arguments, don't look for an exact match on multiple unrelated arguments in a certain order.</span></span> <span data-ttu-id="d89bf-138">Gebruik in plaats daarvan gewone expressies of gebruik meerdere afzonderlijke operatoren.</span><span class="sxs-lookup"><span data-stu-id="d89bf-138">Instead, use regular expressions or use multiple separate contains operators.</span></span>
- <span data-ttu-id="d89bf-139">Gebruik case insensitive matches.</span><span class="sxs-lookup"><span data-stu-id="d89bf-139">Use case insensitive matches.</span></span> <span data-ttu-id="d89bf-140">Gebruik bijvoorbeeld `=~` , `in~` en in plaats van `contains` , `==` `in` en `contains_cs`</span><span class="sxs-lookup"><span data-stu-id="d89bf-140">For example, use `=~`, `in~`, and `contains` instead of `==`, `in` and `contains_cs`</span></span>
- <span data-ttu-id="d89bf-141">Als u dos-technieken voor obfuscation wilt beperken, kunt u aanhalingstekens verwijderen, komma's vervangen door spaties en meerdere opeenvolgende spaties vervangen door één spatie.</span><span class="sxs-lookup"><span data-stu-id="d89bf-141">To mitigate DOS command-line obfuscation techniques, consider removing quotes, replacing commas with spaces, and replacing multiple consecutive spaces with a single space.</span></span> <span data-ttu-id="d89bf-142">Houd er rekening mee dat er complexere DOS-obfuscation-technieken zijn die andere methoden vereisen, maar deze kunnen helpen bij het aanpakken van de meest voorkomende technieken.</span><span class="sxs-lookup"><span data-stu-id="d89bf-142">Note that there are more complex DOS obfuscation techniques that require other approaches, but these can help address the most common ones.</span></span>

<span data-ttu-id="d89bf-143">In de volgende voorbeelden ziet u verschillende manieren  om een query te maken die zoekt naar het bestandnet.exeom de Windows Defender Firewall-service te stoppen:</span><span class="sxs-lookup"><span data-stu-id="d89bf-143">The following examples show various ways to construct a query that looks for the file *net.exe* to stop the Windows Defender Firewall service:</span></span>

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

> <span data-ttu-id="d89bf-144">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="d89bf-144">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d89bf-145">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="d89bf-145">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-bestpractices-belowfoldlink)

## <a name="related-topics"></a><span data-ttu-id="d89bf-146">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="d89bf-146">Related topics</span></span>

- [<span data-ttu-id="d89bf-147">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="d89bf-147">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="d89bf-148">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="d89bf-148">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="d89bf-149">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="d89bf-149">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="d89bf-150">Werken met queryresultaten</span><span class="sxs-lookup"><span data-stu-id="d89bf-150">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="d89bf-151">Overzicht van aangepaste detectie</span><span class="sxs-lookup"><span data-stu-id="d89bf-151">Custom detections overview</span></span>](overview-custom-detections.md)
