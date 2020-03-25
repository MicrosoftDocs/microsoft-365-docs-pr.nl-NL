---
title: Tabel AlertInfo in het geavanceerde jachtschema
description: Meer informatie over gebeurtenissen voor het genereren van waarschuwingen in de tabel AlertInfo van het geavanceerde jachtschema
keywords: geavanceerde jacht, bedreigingsjacht, cyberdreigingsjacht, bescherming tegen microsoft-dreigingen, microsoft 365, mtp, m365, zoekopdracht, query, telemetrie, schemareferentie, kusto, tabel, kolom, gegevenstype, beschrijving, AlertInfo, waarschuwing, ernst, categorie, MITRE, ATT&CK, Microsoft Defender ATP, MDATP, Office 365 ATP, Microsoft Cloud App Security, MCAS en Azure ATP
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
ms.openlocfilehash: e4d7ec213a4b4d1108c06784fb5e6675c79429c1
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929514"
---
# <a name="alertinfo"></a>AlertInfo

**Van toepassing op:**
- Microsoft-bedreigingsbeveiliging



De `AlertInfo` tabel in het [geavanceerde jachtschema](advanced-hunting-overview.md) bevat informatie over waarschuwingen van Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security en Azure ATP. Gebruik deze verwijzing om query's te construeren die informatie uit deze tabel retourneren.

Voor informatie over andere tabellen in de geavanceerde jacht schema, [zie de geavanceerde jacht referentie](advanced-hunting-schema-tables.md).

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | Datetime | Datum en tijdstip waarop de gebeurtenis is geregistreerd |
| `AlertId` | Tekenreeks | Unieke id voor de waarschuwing |
| `Title` | Tekenreeks | Titel van de waarschuwing |
| `Category` | Tekenreeks | Type bedreigingsindicator of inbreukactiviteit die door de waarschuwing wordt geïdentificeerd |
| `Severity` | Tekenreeks | Geeft de potentiële impact (hoog, gemiddeld of laag) van de bedreigingsindicator of inbreukactiviteit aan die door de waarschuwing wordt geïdentificeerd |
| `ServiceSource` | Tekenreeks | Product of dienst die de waarschuwingsinformatie heeft verstrekt |
| `DetectionSource` | Tekenreeks | Detectietechnologie of sensor die de opmerkelijke component of activiteit identificeerde |
| `AttackTechniques` | Tekenreeks | MITRE ATT&CK-technieken die verband houden met de activiteit die de waarschuwing heeft geactiveerd |

## <a name="related-topics"></a>Verwante onderwerpen
- [Proactief op zoek naar bedreigingen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Zoek naar bedreigingen op verschillende apparaten en e-mails](advanced-hunting-query-emails-devices.md)
- [Het schema begrijpen](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
