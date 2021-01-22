---
title: DeviceTvmSoftwareInventoryVulnerabilities table in the advanced hunting schema
description: Meer informatie over de inventaris van software op uw apparaten en de beveiligingslekken in de tabel DeviceTvmSoftwareInventoryVulnerabilities van het geavanceerde schema voor zoeken.
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, software, inventory, vulnerabilities, CVE ID, OS DeviceTvmSoftwareInventoryVulnerabilities
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
ms.openlocfilehash: 517f974657032a1a4b7fee5888b0c681ec8063d7
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931072"
---
# <a name="devicetvmsoftwareinventoryvulnerabilities"></a>DeviceTvmSoftwareInventoryVulnerabilities

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender



De tabel in het geavanceerde schema voor zoeken bevat de inventaris van `DeviceTvmSoftwareInventoryVulnerabilities` bedreigings- &-beveiligingslekken van software op uw apparaten, evenals bekende beveiligingsproblemen in deze softwareproducten. [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) Deze tabel bevat ook informatie over het besturingssysteem, CVE-identiteiten en gegevens over ernst van beveiligingslees. Gebruik deze verwijzing om query's te maken die gegevens uit de tabel retourneren.

Zie het geavanceerde zoekschema voor meer informatie over andere tabellen in het geavanceerde schema [voor zoeken.](advanced-hunting-schema-tables.md)

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `DeviceId` | tekenreeks | Unieke id voor de computer in de service |
| `DeviceName` | tekenreeks | FQDN (Fully Qualified Domain Name) van de computer |
| `OSPlatform` | tekenreeks | Platform van het besturingssysteem dat op de computer wordt uitgevoerd. Dit geeft specifieke besturingssystemen aan, inclusief variaties binnen dezelfde familie, zoals Windows 10 en Windows 7. |
| `OSVersion` | tekenreeks | Versie van het besturingssysteem dat op de computer wordt uitgevoerd |
| `OSArchitecture` | tekenreeks | Architectuur van het besturingssysteem dat op de computer wordt uitgevoerd |
| `SoftwareVendor` | tekenreeks | Naam van de softwareleverancier |
| `SoftwareName` | tekenreeks | Naam van het softwareproduct |
| `SoftwareVersion` | tekenreeks | Versienummer van het softwareproduct |
| `CveId` | tekenreeks | Unieke id die is toegewezen aan het beveiligingsprobleem onder het cve-systeem (Common Vulnerabilities and Exposures) |
| `VulnerabilitySeverityLevel` | tekenreeks | Niveau van ernst dat is toegewezen aan het beveiligingsprobleem op basis van de CVSS-score en dynamische factoren die worden beïnvloed door het bedreigingsland |



## <a name="related-topics"></a>Verwante onderwerpen

- [Proactief zoeken naar bedreigingen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Opsporen op apparaten en in e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
- [Overzicht van risicobeheer & beveiligingsprobleem](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
