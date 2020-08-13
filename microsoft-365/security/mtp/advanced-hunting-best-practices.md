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
# <a name="advanced-hunting-query-best-practices"></a>Best practices voor geavanceerde zoekactie

**Van toepassing op:**
- Microsoft Threat Protection



## <a name="optimize-query-performance"></a>Queryprestaties optimaliseren
Pas deze aanbevelingen toe om resultaten sneller te vinden en time-outs te voorkomen tijdens het uitvoeren van complexe query's:
- Altijd gebruiken `limit` om extreem grote resultaatsets te vermijden. U kunt ook de grootte van de resultatenset in eerste instantie beoordelen `count` .
- Gebruik eerst time filters. In het ideale geval beperkt u de query's tot dagen.
- Plaats filters waarvan de meeste gegevens aan het begin van de query moeten worden verwijderd, rechts na het filter tijd.
- Gebruik de `has` operator over `contains` Wanneer u op zoek bent naar volledige tokens.
- In een specifieke kolom zoeken in plaats van volledige tekst zoekopdrachten in alle kolommen uit te voeren.
- Geef bij het samenvoegen van tabellen de tabel op met minder rijen.
- `project`alleen de benodigde kolommen van tabellen waarvan u lid bent geworden.

>[!Tip]
>Lees voor meer informatie over het verbeteren van de prestaties van query's het artikel [Best practices voor Kusto query](https://docs.microsoft.com/azure/kusto/query/best-practices).

## <a name="query-tips-and-pitfalls"></a>Query tips en valkuilen

### <a name="queries-with-process-ids"></a>Query's met proces-Id's
Proces-Id's in Windows worden gerecycled en opnieuw gebruikt voor nieuwe processen. Ze kunnen op hun eigen manier geen unieke id's voor specifieke processen gebruiken.

Als u een unieke aanduiding wilt krijgen voor een proces op een specifieke computer, gebruikt u de proces-ID samen met de Aanmaaktijd van het proces. Wanneer u gegevens rond processen samenvoegt of samenvoegt, neemt u kolommen op voor de machine-id (of `DeviceId` `DeviceName` ), de proces-id ( `ProcessId` of `InitiatingProcessId` ) en de tijd waarop het proces is gemaakt ( `ProcessCreationTime` of `InitiatingProcessCreationTime` ).

Met de volgende voorbeeldquery vindt u processen die toegang hebben tot meer dan 10 IP-adressen via poort 445 (SMB), mogelijk met de scanfunctie voor bestandsshares.

Voorbeeldquery:
```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId, InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

De query geeft een samenvatting van beide `InitiatingProcessId` `InitiatingProcessCreationTime` processen weer, zodat de query één proces uitziet, zonder meerdere processen met hetzelfde proces-id te kunnen combineren.

### <a name="queries-with-command-lines"></a>Query's met opdrachtregels

De opdrachtregels kunnen variëren. Gebruik indien van toepassing een filter voor de bestandsnamen en voer fuzz treffers uit.

U kunt op verschillende manieren een opdrachtregel maken om een taak uit te voeren. Een aanvaller kan bijvoorbeeld verwijzen naar een afbeeldingsbestand met of zonder een bestandsextensie, met behulp van omgevingsvariabelen of met aanhalingstekens. Daarnaast kan de aanvaller ook de volgorde van parameters wijzigen of meerdere aanhalingstekens en spaties toevoegen.

Als u meer duurzame query's wilt maken met behulp van opdrachtregels, moet u de volgende procedures toepassen:

- Identificeer de bekende processen (zoals *net.exe* of *psexec.exe*) door te zoeken in de bestandsnaam velden, in plaats van te filteren op het opdrachtregel veld.
- Wanneer u een query uitvoert voor opdrachtregelargumenten, zoekt u niet naar een exacte overeenkomst voor meerdere niet-gerelateerde argumenten in een bepaalde volgorde. Gebruik in plaats daarvan reguliere expressies of gebruik van meerdere aparte operatoren.
- Gebruik hoofdlettergevoelige overeenkomsten. Gebruik bijvoorbeeld, `=~` `in~` en `contains` in plaats van `==` , `in` en`contains_cs`
- Als u de opdrachtregel wilt beperken, kunt u aanhalingstekens verwijderen, komma's vervangen door spaties en meerdere opeenvolgende spaties vervangen door één spatie. Houd er rekening mee dat er andere gecompliceerde functies zijn voor het maken van donkere informatie, maar deze kunnen de meest voorkomende methoden helpen.

In de volgende voorbeelden ziet u verschillende manieren om een query te maken waarmee wordt gezocht naar het bestand *net.exe* de Windows Defender Firewall-service te stoppen:

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
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Werken met queryresultaten](advanced-hunting-query-results.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Jacht op apparaten, e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
