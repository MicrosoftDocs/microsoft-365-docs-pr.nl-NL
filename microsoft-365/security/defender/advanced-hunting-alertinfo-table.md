---
title: Tabel AlertInfo in het geavanceerde schema voor de jacht
description: Meer informatie over gebeurtenissen bij het genereren van waarschuwingen in de tabel AlertInfo van het geavanceerde schema voor de jacht
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, AlertInfo, alert, ernst, category, MITRE, ATT&CK, Microsoft Defender ATP, MDATP, Office 365 ATP, Microsoft Cloud App Security, MCAS en Azure ATP
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 1386830a4b3e05009b19a7d0e3a4ea62ce3321f2
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499829"
---
# <a name="alertinfo"></a>AlertInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender



De tabel in het geavanceerde schema bevat informatie over waarschuwingen van Microsoft Defender voor Eindpunt, Microsoft Defender voor `AlertInfo` Office 365, Microsoft Cloud App Security en Microsoft Defender voor identiteit. [](advanced-hunting-overview.md) Gebruik deze verwijzing om query's te maken die gegevens uit deze tabel retourneren.

Zie de geavanceerde zoekverwijzing voor meer informatie over andere tabellen in het geavanceerde schema voor [de jacht.](advanced-hunting-schema-tables.md)

| Kolomnaam | Gegevenstype | Omschrijving |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum en tijd waarop de gebeurtenis is opgenomen |
| `AlertId` | tekenreeks | Unieke id voor de waarschuwing |
| `Title` | tekenreeks | Titel van de waarschuwing |
| `Category` | tekenreeks | Type bedreigingsindicator of inbreukactiviteit die door de waarschuwing is geïdentificeerd |
| `Severity` | tekenreeks | Geeft het mogelijke effect (hoog, gemiddeld of laag) aan van de bedreigingsindicator of inbreukactiviteit die door de waarschuwing is geïdentificeerd |
| `ServiceSource` | tekenreeks | Product of service met de waarschuwingsgegevens |
| `DetectionSource` | tekenreeks | Detectietechnologie of -sensor die het opmerkelijke onderdeel of de activiteit heeft geïdentificeerd |
| `AttackTechniques` | tekenreeks | MITRE ATT&CK-technieken die zijn gekoppeld aan de activiteit die de waarschuwing heeft geactiveerd |

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Opsporen op apparaten en in e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
