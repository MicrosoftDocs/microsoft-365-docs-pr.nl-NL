---
title: Naamgevingswijzigingen in het geavanceerde schema voor de microsoft 365 Defender-jacht
description: Naamgevingswijzigingen bijhouden en controleren tabellen en kolommen in het geavanceerde schema voor de jacht
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: acb259088717b2772ec9798027545f2ff6dbc5e0
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060597"
---
# <a name="advanced-hunting-schema---naming-changes"></a>Geavanceerd schema voor de jacht - Naamgevingswijzigingen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Het [geavanceerde schema wordt](advanced-hunting-schema-tables.md) regelmatig bijgewerkt om nieuwe tabellen en kolommen toe te voegen. In sommige gevallen worden bestaande kolommennamen hernoemd of vervangen om de gebruikerservaring te verbeteren. Raadpleeg dit artikel om naamgevingswijzigingen te bekijken die van invloed kunnen zijn op uw query's.

Naamgevingswijzigingen worden automatisch toegepast op query's die zijn opgeslagen in het beveiligingscentrum, inclusief query's die worden gebruikt door aangepaste detectieregels. U hoeft deze query's niet handmatig bij te werken. U moet echter de volgende query's bijwerken:
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
| `DetectionSource` | MCAS |    Microsoft Cloud App Security | Rebranding |
| `DetectionSource` | WindowsDefenderAtp|   EDR| Rebranding |
| `DetectionSource` | WindowsDefenderAv | Antivirus | Rebranding |
| `DetectionSource` | WindowsDefenderSmartScreen |  SmartScreen | Rebranding |
| `DetectionSource` | CustomerTI |  Aangepaste TI | Rebranding |
| `DetectionSource` | OfficeATP | Microsoft Defender voor Office 365 | Rebranding |
| `DetectionSource` | MTP   | Microsoft 365 Defender | Rebranding |
| `DetectionSource` | AzureATP |    Microsoft Defender for Identity | Rebranding |
| `DetectionSource` | CustomDetection   | Aangepaste detectie | Rebranding |
| `DetectionSource` | AutomatedInvestigation |Geautomatiseerd onderzoek | Rebranding |
| `DetectionSource` | ThreatExperts | Microsoft Threat Experts | Rebranding |
| `DetectionSource` | TI van derden | Sensoren van derden | Rebranding |
| `ServiceSource` | Microsoft Defender ATP| Microsoft Defender for Endpoint | Rebranding |
|`ServiceSource` |Microsoft Threat Protection   | Microsoft 365 Defender | Rebranding |
| `ServiceSource` | Office 365 ATP  |Microsoft Defender voor Office 365 | Rebranding |
| `ServiceSource` |Azure ATP    |Microsoft Defender for Identity | Rebranding |

`DetectionSource`is beschikbaar in de [tabel AlertInfo.](advanced-hunting-alertinfo-table.md) `ServiceSource`is beschikbaar in de [tabellen AlertEvidence](advanced-hunting-alertevidence-table.md) en [AlertInfo.](advanced-hunting-alertinfo-table.md) 

## <a name="february-2021"></a>Februari 2021

1. In de [tabellen EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) en [EmailEvents](advanced-hunting-emailevents-table.md) zijn de kolommen vervangen `MalwareFilterVerdict` door de `PhishFilterVerdict` `ThreatTypes` kolom. De `MalwareDetectionMethod` kolommen en kolommen zijn ook vervangen door de `PhishDetectionMethod` `DetectionMethods` kolom. Met deze stroomlijning kunnen we meer informatie geven onder de nieuwe kolommen. De toewijzing vindt u hieronder.

| Tabelnaam | Oorspronkelijke kolomnaam | Nieuwe kolomnaam | Reden voor wijziging
|--|--|--|--|
| `EmailAttachmentInfo` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | Meer detectiemethoden opnemen |
| `EmailAttachmentInfo`  | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | Meer bedreigingstypen opnemen |
| `EmailEvents` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | Meer detectiemethoden opnemen |
| `EmailEvents` | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | Meer bedreigingstypen opnemen |


2. In de tabellen en tabellen is de kolom toegevoegd om meer informatie over de e-maildreiging `EmailAttachmentInfo` `EmailEvents` te `ThreatNames` geven. Deze kolom bevat waarden zoals Spam of Phish.

3. In de [tabel DeviceInfo](advanced-hunting-deviceinfo-table.md) is de `DeviceObjectId` kolom vervangen door de kolom op basis van feedback van `AadDeviceId` klanten.

4. In de [tabel DeviceEvents](advanced-hunting-deviceevents-table.md) zijn verschillende ActionType-namen gewijzigd om de beschrijving van de actie beter weer te geven. Details van de wijzigingen vindt u hieronder.

| Tabelnaam | Oorspronkelijke naam ActionType | Nieuwe naam ActionType | Reden voor wijziging
|--|--|--|--|
| `DeviceEvents` | `DlpPocPrintJob` | `FilePrinted` | Feedback van klanten |
| `DeviceEvents` | `UsbDriveMount` | `UsbDriveMounted` | Feedback van klanten |
| `DeviceEvents` | `UsbDriveUnmount` | `UsbDriveUnmounted` | Feedback van klanten |
| `DeviceEvents` | `WriteProcessMemoryApiCall` | `WriteToLsassProcessMemory` | Feedback van klanten |






## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)