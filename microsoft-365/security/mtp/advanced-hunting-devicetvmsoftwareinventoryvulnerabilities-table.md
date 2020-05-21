---
title: Tabel DeviceTvmSoftwareInventoryVulnerabilities in het geavanceerde jachtschema
description: Meer informatie over de inventaris van software in uw apparaten en hun kwetsbaarheden in de tabel DeviceTvmSoftwareInventoryVulnerabilities van het geavanceerde jachtschema.
keywords: geavanceerde jacht, dreigingjacht, cyberdreigingsjacht, bescherming tegen microsoft-dreigingen, microsoft 365, mtp, m365, zoekopdracht, query, telemetrie, schemareferentie, kusto, tabel, kolom, gegevenstype, beschrijving, bedreiging & kwetsbaarheidsbeheer, TVM, apparaatbeheer, software, inventaris, kwetsbaarheden, CVE ID, OS DeviceTvmSoftwareInventoryVulnerabilities
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
ms.openlocfilehash: 0a7ac5a68bcdb12b3cdcd94cac8012c7807a6e2b
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327946"
---
# <a name="devicetvmsoftwareinventoryvulnerabilities"></a>DeviceTvmSoftwareInventoryVulnerabilities

**Geldt voor:**
- Microsoft Threat Protection



De `DeviceTvmSoftwareInventoryVulnerabilities` tabel in het geavanceerde jachtschema bevat de threat & Vulnerability [Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) inventaris van software op uw apparaten en eventuele bekende kwetsbaarheden in deze softwareproducten. Deze tabel bevat ook informatie over het besturingssysteem, CVE-id's en informatie over de ernst van kwetsbaarheden. Gebruik deze verwijzing om query's te construeren die informatie uit de tabel retourneren.

Voor informatie over andere tabellen in de geavanceerde jacht schema, zie [de geavanceerde jacht referentie](advanced-hunting-schema-tables.md).

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `DeviceId` | Tekenreeks | Unieke id voor de machine in de service |
| `DeviceName` | Tekenreeks | Volledig gekwalificeerde domeinnaam (FQDN) van de machine |
| `OSPlatform` | Tekenreeks | Platform van het besturingssysteem dat op de machine draait. Dit geeft specifieke besturingssystemen aan, waaronder variaties binnen dezelfde familie, zoals Windows 10 en Windows 7. |
| `OSVersion` | Tekenreeks | Versie van het besturingssysteem die op de machine draait |
| `OSArchitecture` | Tekenreeks | Architectuur van het besturingssysteem dat op de machine draait |
| `SoftwareVendor` | Tekenreeks | Naam van de softwareleverancier |
| `SoftwareName` | Tekenreeks | Naam van het softwareproduct |
| `SoftwareVersion` | Tekenreeks | Versienummer van het softwareproduct |
| `CveId` | Tekenreeks | Unieke id die is toegewezen aan het beveiligingslek onder het CVE-systeem (Common Vulnerabilities and Exposures) |
| `VulnerabilitySeverityLevel` | Tekenreeks | Ernstniveau toegewezen aan het beveiligingslek op basis van de CVSS-score en dynamische factoren die worden beïnvloed door het dreigingslandschap |



## <a name="related-topics"></a>Verwante onderwerpen

- [Proactief op zoek naar bedreigingen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Zoek naar bedreigingen op verschillende apparaten en e-mails](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
- [Overzicht van Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
