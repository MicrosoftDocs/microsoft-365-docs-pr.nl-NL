---
title: Naamgevingswijzigingen in het Geavanceerde schema voor zoeken van Microsoft 365 Defender
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
ms.openlocfilehash: cd06286083297d0930270868b99a14f8ddb2f4b2
ms.sourcegitcommit: a7d1b29a024b942c7d0d8f5fb9b5bb98a0036b68
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/05/2021
ms.locfileid: "50461665"
---
# <a name="advanced-hunting-schema---naming-changes"></a>Geavanceerd schema voor zoeken : naamgevingswijzigingen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Het [geavanceerde schema voor zoeken](advanced-hunting-schema-tables.md) wordt regelmatig bijgewerkt om nieuwe tabellen en kolommen toe te voegen. In sommige gevallen worden bestaande kolomnamen gewijzigd of vervangen om de gebruikerservaring te verbeteren. Raadpleeg dit artikel voor meer informatie over naamgevingswijzigingen die van invloed kunnen zijn op uw query's.

Naamwijzigingen worden automatisch toegepast op query's die worden opgeslagen in het beveiligingscentrum, inclusief query's die worden gebruikt door aangepaste detectieregels. U hoeft deze query's niet handmatig bij te werken. U moet echter de volgende query's bijwerken:
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

## <a name="february-2021"></a>Februari 2021

1. In de [tabellen EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) en [EmailEvents](advanced-hunting-emailevents-table.md) hebben we de kolommen en kolommen afgeschaft en vervangen `MalwareFilterVerdict` door de `PhishFilterVerdict` `ThreatTypes` kolom. We hebben ook de kolommen afgeschaft `MalwareDetectionMethod` en vervangen door de `PhishDetectionMethod` `DetectionMethods` kolom. Met deze stroomlijning kunnen we meer informatie onder de nieuwe kolommen verstrekken. Hieronder vindt u de toewijzing.

| Tabelnaam | Oorspronkelijke kolomnaam | Nieuwe kolomnaam | Reden voor wijziging
|--|--|--|--|
| `EmailAttachmentInfo` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | Meer detectiemethoden opnemen |
| `EmailAttachmentInfo`  | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | Meer bedreigingstypen opnemen |
| `EmailEvents` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | Meer detectiemethoden opnemen |
| `EmailEvents` | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | Meer bedreigingstypen opnemen |


2. In de tabellen is de kolom toegevoegd om meer informatie te geven over het `EmailAttachmentInfo` `EmailEvents` `ThreatNames` e-mailbericht. Deze kolom bevat waarden zoals Spam of Phish.

3. In de [tabel DeviceInfo](advanced-hunting-deviceinfo-table.md) hebben we de kolom `DeviceObjectId` vervangen door op basis van feedback van `AadDeviceId` klanten.

4. In de [tabel DeviceEvents](advanced-hunting-deviceevents-table.md) hebben we verschillende ActionType-namen bijgewerkt om de beschrijving van de actie beter aan te geven. Meer informatie vindt u hieronder.

| Tabelnaam | Oorspronkelijke ActionType-naam | Nieuwe ActionType-naam | Reden voor wijziging
|--|--|--|--|
| `DeviceEvents` | `DlpPocPrintJob` | `FilePrinted` | Feedback van klanten |
| `DeviceEvents` | `UsbDriveMount` | `UsbDriveMounted` | Feedback van klanten |
| `DeviceEvents` | `UsbDriveUnmount` | `UsbDriveUnmounted` | Feedback van klanten |
| `DeviceEvents` | `WriteProcessMemoryApiCall` | `WriteToLsassProcessMemory` | Feedback van klanten |
| `DeviceEvents` | `AntivirusDetection` | `EdrBlock` | Feedback van klanten |





## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)