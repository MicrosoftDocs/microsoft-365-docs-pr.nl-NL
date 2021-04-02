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
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: m365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: b65adbc968e095a6845f27ae1ae859830e4065c4
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499261"
---
# <a name="advanced-hunting-query-best-practices"></a>Geavanceerde best practices voor query's

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)


>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-bestpractices-abovefoldlink)

## <a name="optimize-query-performance"></a>Prestaties van query's optimaliseren

Pas deze aanbevelingen toe om sneller resultaten te krijgen en time-outs te vermijden tijdens het uitvoeren van complexe query's.

- Gebruik bij het proberen van nieuwe query's `limit` altijd om zeer grote resultatensets te voorkomen. U kunt ook in eerste instantie de grootte van de resultatenset beoordelen met `count` behulp van .
- Gebruik eerst tijdfilters. Beperk uw query's in het ideale ideaal tot zeven dagen.
- Filters instellen die naar verwachting de meeste gegevens aan het begin van de query verwijderen, direct na het tijdfilter.
- Gebruik de `has` operator over wanneer u op zoek bent naar volledige `contains` tokens.
- Zoek in een specifieke kolom in plaats van volledige tekst te zoeken in alle kolommen.
- Geef bij het deelnemen aan tabellen eerst de tabel op met minder rijen.
- `project` alleen de benodigde kolommen uit tabellen die u hebt samengevoegd.

>[!TIP]
>Lees [Kusto query best practices](https://docs.microsoft.com/azure/kusto/query/best-practices)voor meer informatie over het verbeteren van queryprestaties.

## <a name="query-tips-and-pitfalls"></a>Querytips en valkuilen

### <a name="queries-with-process-ids"></a>Query's met proces-IDs

Proces-ID's (PID's) worden in Windows hergebruikt en opnieuw gebruikt voor nieuwe processen. Op zichzelf kunnen ze niet fungeren als unieke id's voor specifieke processen. Als u een unieke id wilt krijgen voor een proces op een bepaald apparaat, gebruikt u de proces-id samen met de tijd voor het maken van het proces. Wanneer u gegevens rond processen bij elkaar opeet of samenvatten, kunt u kolommen voor de apparaataanduiding (of), de proces-id (of) en de tijd voor het maken `DeviceId` `DeviceName` van het proces `ProcessId` `InitiatingProcessId` `ProcessCreationTime` `InitiatingProcessCreationTime` (of) opnemen.

In de volgende voorbeeldquery worden processen gevonden die toegang hebben tot meer dan 10 IP-adressen via poort 445 (SMB), mogelijk scannen op bestandsaandelen.

```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId, InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

De query wordt op beide manieren samengevat, zodat er naar één proces wordt ge kijkt, zonder dat meerdere processen met dezelfde `InitiatingProcessId` `InitiatingProcessCreationTime` proces-id worden vermengd.

### <a name="queries-with-command-lines"></a>Query's met opdrachtregels

Opdrachtlijnen kunnen variëren. Filter indien van toepassing op bestandsnamen en doe fuzzy matching.

Er zijn verschillende manieren om een opdrachtregel te maken om een taak uit te voeren. Een aanvaller kan bijvoorbeeld verwijzen naar een afbeeldingsbestand met of zonder pad, zonder bestandsextensie, met omgevingsvariabelen of met aanhalingstekens. Daarnaast kan de aanvaller ook de volgorde van parameters wijzigen of meerdere aanhalingstekens en spaties toevoegen.

Als u duurzamere query's wilt maken met opdrachtlijnen, moet u de volgende procedures toepassen:

- Identificeer de bekende processen  (zoalsnet.exeof *psexec.exe)* door op de bestandsnaamvelden te matchen in plaats van te filteren op het opdrachtregelveld.
- Wanneer u query's uitvoert voor opdrachtregelargumenten, moet u niet zoeken naar een exacte overeenkomst voor meerdere niet-gerelateerde argumenten in een bepaalde volgorde. Gebruik in plaats daarvan gewone expressies of gebruik meerdere afzonderlijke operatoren.
- Gebruik case insensitive matches. Gebruik bijvoorbeeld `=~` , `in~` en in plaats van `contains` , `==` `in` en `contains_cs`
- Als u dos-technieken voor obfuscation wilt beperken, kunt u aanhalingstekens verwijderen, komma's vervangen door spaties en meerdere opeenvolgende spaties vervangen door één spatie. Houd er rekening mee dat er complexere DOS-obfuscation-technieken zijn die andere methoden vereisen, maar deze kunnen helpen bij het aanpakken van de meest voorkomende technieken.

In de volgende voorbeelden ziet u verschillende manieren  om een query te maken die zoekt naar het bestandnet.exeom de Windows Defender Firewall-service te stoppen:

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

> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-bestpractices-belowfoldlink)

## <a name="related-topics"></a>Verwante onderwerpen

- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Meer informatie over het schema](advanced-hunting-schema-reference.md)
- [Werken met queryresultaten](advanced-hunting-query-results.md)
- [Overzicht van aangepaste detectie](overview-custom-detections.md)
