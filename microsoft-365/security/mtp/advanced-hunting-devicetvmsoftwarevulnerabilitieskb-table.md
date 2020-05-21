---
title: DeviceTvmSoftwareVulnerabilitiesKB tabel in de geavanceerde jacht schema
description: Meer informatie over de software kwetsbaarheden bijgehouden door Threat & Vulnerability Management in de DeviceTvmSoftwareVulnerabilitiesKB tabel van de geavanceerde jacht schema.
keywords: geavanceerde jacht, dreigingsjacht, cyberdreigingsjacht, bescherming tegen microsoft-dreigingen, microsoft 365, mtp, m365, zoeken, query, telemetrie, schema, referentie, kusto, tabel, kolom, gegevenstype, beschrijving, bedreiging & kwetsbaarheidsbeheer, TVM, apparaatbeheer, software, inventaris, kwetsbaarheden, CVE ID, CVSS, DeviceTvmSoftwareVulnerabilitiesKB
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
ms.openlocfilehash: 378ffee34a24af225b1b6deebd7cc514c62e1926
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327950"
---
# <a name="devicetvmsoftwarevulnerabilitieskb"></a>DeviceTvmSoftwareVulnerabilitiesKB

**Geldt voor:**
- Microsoft Threat Protection



De `DeviceTvmSoftwareVulnerabilitiesKB` tabel in het geavanceerde jachtschema bevat de lijst met kwetsbaarheden Threat & Vulnerability [Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) beoordeelt apparaten voor. Gebruik deze verwijzing om query's te construeren die informatie uit de tabel retourneren.

Voor informatie over andere tabellen in de geavanceerde jacht schema, zie [de geavanceerde jacht referentie](advanced-hunting-schema-tables.md).

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `CveId` | Tekenreeks | Unieke id die is toegewezen aan het beveiligingslek onder het CVE-systeem (Common Vulnerabilities and Exposures) |
| `CvssScore` | Tekenreeks | Ernstscore toegewezen aan het beveiligingslek onder het Common Vulnerability Scoring System (CVSS) |
| `IsExploitAvailable` | Booleaanse | Geeft aan of exploitcode voor het beveiligingslek openbaar beschikbaar is |
| `VulnerabilitySeverityLevel` | Tekenreeks | Ernstniveau toegewezen aan het beveiligingslek op basis van de CVSS-score en dynamische factoren die worden beïnvloed door het dreigingslandschap |
| `LastModifiedTime` | Datetime | Datum en tijd dat het item of gerelateerde metagegevens voor het laatst zijn gewijzigd |
| `PublishedDate` | Datetime | Datum kwetsbaarheid werd openbaar gemaakt |
| `VulnerabilityDescription` | Tekenreeks | Beschrijving van kwetsbaarheid en bijbehorende risico's |
| `AffectedSoftware` | Tekenreeks | Lijst van alle softwareproducten die door het beveiligingslek zijn getroffen |

## <a name="related-topics"></a>Verwante onderwerpen

- [Proactief op zoek naar bedreigingen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Zoek naar bedreigingen op verschillende apparaten en e-mails](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
- [Overzicht van Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
