---
title: DeviceTvmSoftwareVulnerabilitiesKB-tabel in het geavanceerde schema voor de jacht
description: Meer informatie over de softwareproblemen die door Threat & Vulnerability Management zijn bijgespoord in de tabel DeviceTvmSoftwareVulnerabilitiesKB van het geavanceerde schema voor de jacht.
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema, reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, software, inventory, vulnerabilities, CVE ID, CVSS, DeviceTvmSoftwareVulnerabilitiesKB
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
ms.openlocfilehash: afcd6bcd81e1a8635be9ced766c533ea4195334f
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023795"
---
# <a name="devicetvmsoftwarevulnerabilitieskb"></a>DeviceTvmSoftwareVulnerabilitiesKB

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender
- Microsoft Defender voor Eindpunt



De tabel in het geavanceerde schema voor de jacht bevat de lijst met beveiligingsproblemen `DeviceTvmSoftwareVulnerabilitiesKB` [& kwetsbaarheidsbeheer](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) apparaten beoordeelt voor. Gebruik deze verwijzing om query's te maken die gegevens uit de tabel retourneren.

Zie de geavanceerde zoekverwijzing voor meer informatie over andere tabellen in het geavanceerde schema voor [de jacht.](advanced-hunting-schema-tables.md)

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `CveId` | tekenreeks | Unieke id die is toegewezen aan het beveiligingsprobleem onder het CVE-systeem (Common Vulnerabilities and Exposures) |
| `CvssScore` | tekenreeks | Ernstscore die is toegewezen aan het beveiligingsprobleem onder het Common Vulnerability Scoring System (CVSS) |
| `IsExploitAvailable` | booleaanse | Geeft aan of exploitcode voor het beveiligingsprobleem openbaar beschikbaar is |
| `VulnerabilitySeverityLevel` | tekenreeks | Ernstniveau dat is toegewezen aan het beveiligingsprobleem op basis van de CVSS-score en dynamische factoren die worden beïnvloed door het bedreigingslandschap |
| `LastModifiedTime` | datetime | Datum en tijd waarop het item of de gerelateerde metagegevens voor het laatst zijn gewijzigd |
| `PublishedDate` | datetime | Datumprobleem is openbaar gemaakt |
| `VulnerabilityDescription` | tekenreeks | Beschrijving van kwetsbaarheid en bijbehorende risico's |
| `AffectedSoftware` | tekenreeks | Lijst met alle softwareproducten die door het beveiligingsprobleem zijn beïnvloed |

## <a name="related-topics"></a>Verwante onderwerpen

- [Proactief op bedreigingen zoeken](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Opsporen op apparaten en in e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
- [Overzicht van threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)