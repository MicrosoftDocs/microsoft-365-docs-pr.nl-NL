---
title: DeviceTvmSoftwareVulnerabilitiesKB table in the advanced hunting schema
description: Meer informatie over de door Threat & Vulnerability Management bij te houden beveiligingsproblemen in de tabel DeviceTvmSoftwareVulnerabilitiesKB van het geavanceerde schema voor zoeken.
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema, reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, software, inventory, vulnerabilities, CVE ID, CVSS, DeviceTvmSoftwareVulnerabilitiesKBB
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
ms.openlocfilehash: 00474ac13f88cd9a00ea2ba4a53a6e30ddd664c4
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931048"
---
# <a name="devicetvmsoftwarevulnerabilitieskb"></a>DeviceTvmSoftwareVulnerabilitiesKB

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender



De tabel in het geavanceerde schema voor zoeken bevat de lijst met `DeviceTvmSoftwareVulnerabilitiesKB` [beveiligingsproblemen Bedreiging & Beveiligingsprobleembeheer](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) evalueert apparaten voor. Gebruik deze verwijzing om query's te maken die gegevens uit de tabel retourneren.

Zie het geavanceerde zoekschema voor meer informatie over andere tabellen in het geavanceerde schema [voor zoeken.](advanced-hunting-schema-tables.md)

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `CveId` | tekenreeks | Unieke id die is toegewezen aan het beveiligingsprobleem onder het cve-systeem (Common Vulnerabilities and Exposures) |
| `CvssScore` | tekenreeks | De ernstscore die is toegewezen aan het beveiligingsprobleem onder het Common Vulnerability Scoring System (CVSS) |
| `IsExploitAvailable` | boolean | Hiermee wordt aangegeven of misbruik van code voor het beveiligingsprobleem openbaar beschikbaar is |
| `VulnerabilitySeverityLevel` | tekenreeks | Niveau van ernst dat is toegewezen aan het beveiligingsprobleem op basis van de CVSS-score en dynamische factoren die worden beïnvloed door het bedreigingsland |
| `LastModifiedTime` | datetime | Datum en tijd waarop het item of de gerelateerde metagegevens het laatst zijn gewijzigd |
| `PublishedDate` | datetime | Datumprobleem is openbaar gemaakt |
| `VulnerabilityDescription` | tekenreeks | Beschrijving van beveiligingsrisico's en bijbehorende risico's |
| `AffectedSoftware` | tekenreeks | Lijst met alle softwareproducten die door dit beveiligingsprobleem worden beïnvloed |

## <a name="related-topics"></a>Verwante onderwerpen

- [Proactief zoeken naar bedreigingen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Opsporen op apparaten en in e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
- [Overzicht van risicobeheer & beveiligingsprobleem](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
