---
title: DeviceTvmSoftwareInventory-tabel in het geavanceerde schema voor de jacht
description: Meer informatie over de inventaris van software op uw apparaten in de tabel DeviceTvmSoftwareInventory van het geavanceerde schema voor de jacht.
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, software, inventory, vulnerabilities, CVE ID, OS DeviceTvmSoftwareInventoryVulnerabilities
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
ms.openlocfilehash: 6e24b6aa7412c05324571bd22b380215219bdf44
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934835"
---
# <a name="devicetvmsoftwareinventory"></a>DeviceTvmSoftwareInventory

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

>[!IMPORTANT]
> Sommige informatie is gerelateerd aan voorlopige productversies die mogelijk aanzienlijk gewijzigd worden voordat ze commercieel gepubliceerd worden. Microsoft geeft geen garantie, uitdrukkelijk of impliciet, met betrekking tot de informatie die hier wordt beschreven.


De tabel in het geavanceerde schema bevat de inventaris & Threat & Vulnerability Management van software die momenteel is geïnstalleerd op apparaten in uw netwerk, inclusief informatie over het einde `DeviceTvmSoftwareInventory` van de ondersteuning. [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) U kunt bijvoorbeeld zoeken naar gebeurtenissen met apparaten die zijn geïnstalleerd met een momenteel kwetsbare softwareversie. Gebruik deze verwijzing om query's te maken die gegevens uit de tabel retourneren.

>[!NOTE]
> De `DeviceTvmSoftwareInventory` tabel en de tabellen zijn `DeviceTvmSoftwareVulnerabilities` `DeviceTvmSoftwareInventoryVulnerabilities` vervangen. De eerste twee tabellen bevatten meer kolommen die u kunt gebruiken om uw vulnerablity-beheeractiviteiten te informeren of om te zoeken naar kwetsbare apparaten.

Zie de geavanceerde zoekverwijzing voor meer informatie over andere tabellen in het geavanceerde schema voor [de jacht.](advanced-hunting-schema-tables.md)

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `DeviceId` | tekenreeks | Unieke id voor de machine in de service |
| `DeviceName` | tekenreeks | Volledig gekwalificeerde domeinnaam (FQDN) van de computer |
| `OSPlatform` | tekenreeks | Platform van het besturingssysteem dat op de computer wordt uitgevoerd. Dit geeft specifieke besturingssystemen aan, waaronder variaties binnen dezelfde familie, zoals Windows 10 en Windows 7. |
| `OSVersion` | tekenreeks | Versie van het besturingssysteem dat op de computer wordt uitgevoerd |
| `OSArchitecture` | tekenreeks | Architectuur van het besturingssysteem dat op de computer wordt uitgevoerd |
| `SoftwareVendor` | tekenreeks | Naam van de softwareleverancier |
| `SoftwareName` | tekenreeks | Naam van het softwareproduct |
| `SoftwareVersion` | tekenreeks | Versienummer van het softwareproduct |
| `EndOfSupportStatus` | tekenreeks | Geeft de levenscyclusfase van het softwareproduct aan ten opzichte van de opgegeven einddatum (EOS) of de einddatum van het softwareproduct (EOL) |
| `EndOfSupportDate` | tekenreeks | End-of-support (EOS) of end-of-life (EOL) datum van het softwareproduct |



## <a name="related-topics"></a>Verwante onderwerpen

- [Proactief op bedreigingen zoeken](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Opsporen op apparaten en in e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
- [Overzicht van threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
