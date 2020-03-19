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
# <a name="advanced-hunting-query-best-practices"></a>Aanbevolen procedures voor geavanceerde jachtquery's

**Van toepassing op:**
- Microsoft-bedreigingsbeveiliging



## <a name="optimize-query-performance"></a>Queryprestaties optimaliseren
Pas deze aanbevelingen toe om sneller resultaten te krijgen en time-outs te voorkomen tijdens het uitvoeren van complexe query's:
- Wanneer u nieuwe query's probeert, gebruikt u `limit` altijd om extreem grote resultaatsets te voorkomen. U ook in eerste instantie de `count`grootte van de resultaatset beoordelen met behulp van.
- Gebruik eerst tijdfilters. In het ideale plaats u uw query's beperken tot zelfs dagen.
- Zet filters die naar verwachting de meeste gegevens in het begin van de query verwijderen, direct na het tijdsfilter.
- Gebruik `has` de `contains` operator over bij het zoeken naar volledige tokens.
- Zoek in een specifieke kolom in plaats van zoekopdrachten in volledige tekst uit te voeren in alle kolommen.
- Wanneer u tabellen aansluit, geeft u eerst de tabel op met minder rijen.
- `project`alleen de benodigde kolommen van tabellen waar toe u bent verbonden.

>[!Tip]
>Lees [kusto query best practices](https://docs.microsoft.com/azure/kusto/query/best-practices)voor meer richtlijnen voor het verbeteren van de queryprestaties.

## <a name="query-tips-and-pitfalls"></a>Querytips en valkuilen

### <a name="queries-with-process-ids"></a>Query's met proces-i-d's
Proces-id's (PID's) worden gerecycled in Windows en hergebruikt voor nieuwe processen. Op zichzelf kunnen ze niet dienen als unieke id's voor specifieke processen.

Als u een unieke id voor een proces op een specifieke machine wilt krijgen, gebruikt u de proces-ID samen met de procescreatietijd. Wanneer u gegevens rond processen aansluit of samenvat, `DeviceId` `DeviceName`neemt u kolommen`ProcessId` `InitiatingProcessId`op voor de machine-id (of), de proces-ID (of ) en de procescreatietijd (of`ProcessCreationTime` `InitiatingProcessCreationTime`)

In de volgende voorbeeldquery worden processen gevonden die toegang hebben tot meer dan 10 IP-adressen via poort 445 (SMB), mogelijk scannen op bestandsshares.

Voorbeeldquery:
```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId, InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

De query wordt `InitiatingProcessId` samengevat `InitiatingProcessCreationTime` door beide en zodat het kijkt naar een enkel proces, zonder het mengen van meerdere processen met dezelfde proces-ID.

### <a name="queries-with-command-lines"></a>Query's met opdrachtregels

Opdrachtregels kunnen variëren. Filter indien van toepassing bestandsnamen en doe fuzzy matching.

Er zijn tal van manieren om een opdrachtregel te bouwen om een taak te volbrengen. Een aanvaller kan bijvoorbeeld verwijzen naar een afbeeldingsbestand met of zonder pad, zonder bestandsextensie, met omgevingsvariabelen of met aanhalingstekens. Daarnaast kan de aanvaller ook de volgorde van parameters wijzigen of meerdere aanhalingstekens en spaties toevoegen.

Als u duurzamere query's wilt maken met opdrachtregels, past u de volgende procedures toe:

- Identificeer de bekende processen (zoals *net.exe* of *psexec.exe)* door te matchen op de bestandsnaamvelden, in plaats van te filteren op het veld opdrachtregel.
- Wanneer u naar opdrachtregelargumenten zoekt, zoekt u niet naar een exacte overeenkomst voor meerdere niet-gerelateerde argumenten in een bepaalde volgorde. Gebruik in plaats daarvan reguliere expressies of gebruik meerdere afzonderlijke operatoren.
- Gebruik geval ongevoelige overeenkomsten. Gebruik bijvoorbeeld `=~`, `in~`en `contains` in `==` `in`plaats van , en`contains_cs`
- Als u de obfuscation-technieken van DOS-opdrachtregel wilt beperken, u overwegen offertes te verwijderen, komma's te vervangen door spaties en meerdere opeenvolgende spaties te vervangen door één spatie. Merk op dat er meer complexe DOS-verduisteringstechnieken zijn die andere benaderingen vereisen, maar deze kunnen helpen bij het aanpakken van de meest voorkomende.

In de volgende voorbeelden worden verschillende manieren weergegeven om een query te maken die zoekt naar het bestand *net.exe* om de Windows Defender Firewall-service te stoppen:

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
## <a name="related-topics"></a>Verwante onderwerpen
- [Proactief op zoek naar bedreigingen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Zoek naar bedreigingen op verschillende apparaten en e-mails](advanced-hunting-query-emails-devices.md)
- [Het schema begrijpen](advanced-hunting-schema-tables.md)
