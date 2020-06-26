---
title: AlertInfo-tabel in het geavanceerde jachtschema
description: Meer informatie over gebeurtenissen voor het genereren van waarschuwingen in de AlertInfo-tabel van het geavanceerde jachtschema
keywords: geavanceerde jacht, bedreiging jacht, cyber bedreiging jacht, Microsoft threat protection, Microsoft 365, mtp, m365, zoeken, query, telemetrie, schema referentie, kusto, tabel, kolom, gegevenstype, beschrijving, AlertInfo, alert, ernst, categorie, MITRE, ATT&CK, Microsoft Defender ATP, MDATP, Office 365 ATP, Microsoft Cloud App Security, MCAS, en Azure ATP
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
ms.openlocfilehash: a1290ee415073a9cb3948bc4b0cc6bb3ae13285b
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899015"
---
# <a name="alertinfo"></a>AlertInfo

**Van toepassing op:**
- Microsoft Threat Protection



De `AlertInfo` tabel in het geavanceerde [jachtschema](advanced-hunting-overview.md) bevat informatie over waarschuwingen van Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security en Azure ATP. Gebruik deze verwijzing om query's te construeren die informatie uit deze tabel retourneren.

Zie [de geavanceerde jachtreferentie](advanced-hunting-schema-tables.md)voor informatie over andere tabellen in het geavanceerde jachtschema.

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | Datetime | Datum en tijdstip waarop de gebeurtenis is geregistreerd |
| `AlertId` | Tekenreeks | Unieke id voor de waarschuwing |
| `Title` | Tekenreeks | Titel van de waarschuwing |
| `Category` | Tekenreeks | Type bedreigingsindicator of inbreukactiviteit die door de waarschuwing wordt geïdentificeerd |
| `Severity` | Tekenreeks | Geeft de potentiële impact (hoog, gemiddeld of laag) aan van de dreigingsindicator of inbreukactiviteit die door de waarschuwing wordt geïdentificeerd |
| `ServiceSource` | Tekenreeks | Product of dienst die de waarschuwingsinformatie heeft verstrekt |
| `DetectionSource` | Tekenreeks | Detectietechnologie of sensor die de opmerkelijke component of activiteit identificeerde |
| `AttackTechniques` | Tekenreeks | MITRE ATT&CK-technieken die zijn gekoppeld aan de activiteit die de waarschuwing heeft geactiveerd |

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Zoek naar bedreigingen op verschillende apparaten en e-mails](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
