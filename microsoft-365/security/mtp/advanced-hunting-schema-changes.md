---
title: Naamgevingswijzigingen in het geavanceerde schema van Microsoft 365 Defender voor zoeken
description: Wijzigingen in tabellen en kolommen in het geavanceerde schema voor zoeken bijhouden en bekijken
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, data, naming changes, rename, Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 3f03543b03dca5fe426700ffff4f5c6edb8fa3c7
ms.sourcegitcommit: c550c1b5b9e67398fd95bfb0256c4f5c7930b2be
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/01/2021
ms.locfileid: "50066867"
---
# <a name="advanced-hunting-schema---naming-changes"></a>Geavanceerd schema voor zoeken - naamwijzigingen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Het [geavanceerde schema voor zoeken](advanced-hunting-schema-tables.md) wordt regelmatig bijgewerkt om nieuwe tabellen en kolommen toe te voegen. In sommige gevallen worden bestaande kolomnamen gewijzigd of vervangen om de gebruikerservaring te verbeteren. Raadpleeg dit artikel voor meer informatie over naamgevingswijzigingen die van invloed kunnen zijn op uw query's.

Naamwijzigingen worden automatisch toegepast op query's die worden opgeslagen in het beveiligingscentrum, inclusief query's die door aangepaste detectieregels worden gebruikt. U hoeft deze query's niet handmatig bij te werken. U moet echter de volgende query's bijwerken:
- Query's die worden uitgevoerd met de API
- Query's die ergens anders buiten het beveiligingscentrum worden opgeslagen

## <a name="december-2020"></a>December 2020

| Tabelnaam | Oorspronkelijke kolomnaam | Nieuwe kolomnaam | Reden voor wijziging
|--|--|--|--|
| [EmailEvents](advanced-hunting-emailevents-table.md) | `FinalEmailAction` | `EmailAction` | Feedback van klanten |
| [EmailEvents](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicy` | `EmailActionPolicy` | Feedback van klanten |
| [EmailEvents](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicyGuid` | `EmailActionPolicyGuid` | Feedback van klanten |

## <a name="january-2021"></a>Januari 2021

| Kolomnaam | Oorspronkelijke waardenaam | Nieuwe waardenaam | Reden voor wijziging
|--|--|--|--|
| `DetectionSource` | MCAS |    Microsoft Cloud App Security | Naamswijziging |
| `DetectionSource` | WindowsDefenderAtp|   EDR| Naamswijziging |
| `DetectionSource` | WindowsDefenderAv | Antivirussoftware | Naamswijziging |
| `DetectionSource` | WindowsDefenderSmartScreen |  SmartScreen | Naamswijziging |
| `DetectionSource` | CustomerTI |  Aangepaste TI | Naamswijziging |
| `DetectionSource` | OfficeATP | Microsoft Defender voor Office 365 | Naamswijziging |
| `DetectionSource` | MTP   | Microsoft 365 Defender | Naamswijziging |
| `DetectionSource` | AzureATP |    Microsoft Defender for Identity | Naamswijziging |
| `DetectionSource` | CustomDetection   | Aangepaste detectie | Naamswijziging |
| `DetectionSource` | AutomatedInvestigation |Geautomatiseerd onderzoek | Naamswijziging |
| `DetectionSource` | ThreatExperts | Microsoft Threat Experts | Naamswijziging |
| `DetectionSource` | TI van derden | Sensoren van derden | Naamswijziging |
| `ServiceSource` | Microsoft Defender ATP| Microsoft Defender for Endpoint | Naamswijziging |
|`ServiceSource` |Microsoft Threat Protection   | Microsoft 365 Defender | Naamswijziging |
| `ServiceSource` | Office 365 ATP  |Microsoft Defender voor Office 365 | Naamswijziging |
| `ServiceSource` |Azure ATP    |Microsoft Defender for Identity | Naamswijziging |

`DetectionSource`is beschikbaar in de [tabel AlertInfo.](advanced-hunting-alertinfo-table.md) `ServiceSource`is beschikbaar in de [tabellen AlertEvidence en](advanced-hunting-alertevidence-table.md) [AlertInfo.](advanced-hunting-alertinfo-table.md) 
## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)