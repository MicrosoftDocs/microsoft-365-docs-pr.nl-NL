---
title: DeviceTvmSoftwareInventoryVulnerabilities table in the advanced hunting schema
description: Meer informatie over de inventaris van software op uw apparaten en de beveiligingslekken in de tabel DeviceTvmSoftwareInventoryVulnerabilities van het geavanceerde schema voor de jacht.
keywords: advanced hunting, threat hunting, cyber threat hunting, mdatp, microsoft defender atp, wdatp search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, software, inventory, vulnerabilities, CVE ID, OS DeviceTvmSoftwareInventoryVulnerabilities
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
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
ms.openlocfilehash: bbb535aa3f106c8569edb3c64ba95bba9bf36186
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163457"
---
# <a name="devicetvmsoftwareinventoryvulnerabilities"></a>DeviceTvmSoftwareInventoryVulnerabilities

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**

- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)

>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)


[!include[Prerelease information](../../includes/prerelease.md)]

De tabel in het geavanceerde schema bevat de inventaris & Beveiligingsprobleembeheer van software op uw apparaten en eventuele bekende beveiligingslekken `DeviceTvmSoftwareInventoryVulnerabilities` in deze [](next-gen-threat-and-vuln-mgt.md) softwareproducten. Deze tabel bevat ook informatie over het besturingssysteem, CVE-ID's en ernst van de kwetsbaarheid. Gebruik deze verwijzing om query's te maken die gegevens uit de tabel retourneren.

Zie de geavanceerde zoekverwijzing voor meer informatie over andere tabellen in het geavanceerde schema voor [de jacht.](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `DeviceId` | tekenreeks | Unieke id voor het apparaat in de service |
| `DeviceName` | tekenreeks | Volledig gekwalificeerde domeinnaam (FQDN) van het apparaat |
| `OSPlatform` | tekenreeks | Platform van het besturingssysteem dat op het apparaat wordt uitgevoerd. Dit geeft specifieke besturingssystemen aan, waaronder variaties binnen dezelfde familie, zoals Windows 10 en Windows 7. |
| `OSVersion` | tekenreeks | Versie van het besturingssysteem dat op het apparaat wordt uitgevoerd |
| `OSArchitecture` | tekenreeks | Architectuur van het besturingssysteem dat op het apparaat wordt uitgevoerd |
| `SoftwareVendor` | tekenreeks | Naam van de softwareleverancier |
| `SoftwareName` | tekenreeks | Naam van het softwareproduct |
| `SoftwareVersion` | tekenreeks | Versienummer van het softwareproduct |
| `CveId` | tekenreeks | Unieke id die is toegewezen aan het beveiligingsprobleem onder het CVE-systeem (Common Vulnerabilities and Exposures) |
| `VulnerabilitySeverityLevel` | tekenreeks | Ernstniveau dat is toegewezen aan het beveiligingsprobleem op basis van de CVSS-score en dynamische factoren die worden beïnvloed door het bedreigingslandschap |



## <a name="related-topics"></a>Verwante onderwerpen

- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Meer informatie over het schema](advanced-hunting-schema-reference.md)
- [Overzicht van threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md)
