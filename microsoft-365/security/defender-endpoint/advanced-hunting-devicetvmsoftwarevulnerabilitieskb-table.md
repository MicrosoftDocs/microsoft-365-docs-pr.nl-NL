---
title: DeviceTvmSoftwareVulnerabilitiesKB-tabel in het geavanceerde schema voor de jacht
description: Meer informatie over de softwareproblemen die door Threat & Vulnerability Management zijn bijgespoord in de tabel DeviceTvmSoftwareVulnerabilitiesKB van het geavanceerde schema voor de jacht.
keywords: advanced hunting, threat hunting, cyber threat hunting, mdatp, microsoft defender atp, wdatp search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, software, inventory, vulnerabilities, CVE ID, CVSS, DeviceTvmSoftwareVulnerabilitiesKB
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 772a287097f0b204eb329d066cdd81c4eef7a755
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51057705"
---
# <a name="devicetvmsoftwarevulnerabilitieskb"></a>DeviceTvmSoftwareVulnerabilitiesKB 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)

>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

De tabel in het geavanceerde schema voor de jacht bevat de lijst met beveiligingsproblemen `DeviceTvmSoftwareVulnerabilitiesKB` [& kwetsbaarheidsbeheer](next-gen-threat-and-vuln-mgt.md) apparaten beoordeelt voor. Gebruik deze verwijzing om query's te maken die gegevens uit de tabel retourneren.

Zie de geavanceerde zoekverwijzing voor meer informatie over andere tabellen in het geavanceerde schema voor [de jacht.](advanced-hunting-schema-reference.md)

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

- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Meer informatie over het schema](advanced-hunting-schema-reference.md)
- [Overzicht van threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md)
