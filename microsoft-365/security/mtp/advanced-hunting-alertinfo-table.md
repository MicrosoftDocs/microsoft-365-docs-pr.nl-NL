---
title: AlertInfo-tabel in het geavanceerde jacht schema
description: Meer informatie over gebeurtenissen voor het genereren van waarschuwingen in de tabel AlertInfo van het schema geavanceerde jacht
keywords: geavanceerde jacht, bedreigings jacht, Cyber Threat jacht, Microsoft Threat Protection, Microsoft 365, MTP, m365, Search, query, Telemetry, schema Reference, kusto, Table, Column, datatype, Description, AlertInfo, alert,, categorie, Mitre,&ATT, de versie van Microsoft-apps, MDATP, Office 365, MCAS
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 7672d974666a381a48da15e0917a46c97df88895
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847666"
---
# <a name="alertinfo"></a>AlertInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender



De `AlertInfo` tabel in het [Geavanceerde bejachts](advanced-hunting-overview.md) schema bevat informatie over waarschuwingen van Microsoft Defender for endpoints, Microsoft defender for Office 365, Microsoft Cloud app Security en Microsoft Defender for Identity. Gebruik deze verwijzing voor het maken van query's waarmee informatie uit deze tabel wordt geretourneerd.

Zie voor meer informatie over andere tabellen in het geavanceerde jacht-schema [de Naslaggids voor Geavanceerd](advanced-hunting-schema-tables.md)zoeken.

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | tijd | De datum en tijd waarop de gebeurtenis is vastgelegd |
| `AlertId` | tekenreeks | Unieke id voor de waarschuwing |
| `Title` | tekenreeks | Titel van de waarschuwing |
| `Category` | tekenreeks | Type bedreigings indicator of schendings activiteit aangegeven door de waarschuwing |
| `Severity` | tekenreeks | Hiermee wordt de potentiële impact (hoog, normaal of laag) aangegeven van de bedreigings indicator of de melding over de overtreding, aangegeven door de waarschuwing |
| `ServiceSource` | tekenreeks | Het product of de service die de waarschuwingsinformatie heeft verstrekt |
| `DetectionSource` | tekenreeks | Detectie-technologie of-sensor waarmee de opmerkelijke component of activiteit wordt aangegeven |
| `AttackTechniques` | tekenreeks | MITRE ATT&verzonken technieken die zijn gekoppeld aan de activiteit waarmee de waarschuwing is geactiveerd |

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Opsporen op apparaten en in e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
