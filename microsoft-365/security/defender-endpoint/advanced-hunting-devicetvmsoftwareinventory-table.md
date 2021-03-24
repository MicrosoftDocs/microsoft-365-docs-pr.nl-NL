---
title: DeviceTvmSoftwareInventory-tabel in het geavanceerde schema voor de jacht
description: Meer informatie over de inventaris van software op uw apparaten in de tabel DeviceTvmSoftwareInventory van het geavanceerde schema voor de jacht.
keywords: advanced hunting, threat hunting, cyber threat hunting, mdatp, microsoft defender atp, wdatp search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, software, inventory, vulnerabilities, CVE ID, OS DeviceTvmSoftwareInventoryVulnerabilities
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: fc9e5fb29518207c5360d5fbe29b8b4848d350e2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060014"
---
# <a name="devicetvmsoftwareinventory"></a>DeviceTvmSoftwareInventory

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)

>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

De tabel in het geavanceerde schema bevat de inventaris & Threat & Vulnerability Management van software die momenteel is geïnstalleerd op apparaten in uw netwerk, inclusief informatie over het einde `DeviceTvmSoftwareInventory` van de ondersteuning. [](next-gen-threat-and-vuln-mgt.md) U kunt bijvoorbeeld zoeken naar gebeurtenissen met apparaten die zijn geïnstalleerd met een momenteel kwetsbare softwareversie. Gebruik deze verwijzing om query's te maken die gegevens uit de tabel retourneren.

>[!NOTE]
>De `DeviceTvmSoftwareInventory` tabel en de tabellen zijn `DeviceTvmSoftwareVulnerabilities` `DeviceTvmSoftwareInventoryVulnerabilities` vervangen. De eerste twee tabellen bevatten samen meer kolommen die u kunt gebruiken om uw activiteiten op het gebied van kwetsbaarheidsbeheer te informeren.

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
| `EndOfSupportStatus` | tekenreeks | Geeft de levenscyclusfase van het softwareproduct aan ten opzichte van de opgegeven einddatum (EOS) of de einddatum van het softwareproduct (EOL) |
| `EndOfSupportDate` | tekenreeks | End-of-support (EOS) of end-of-life (EOL) datum van het softwareproduct |



## <a name="related-topics"></a>Verwante onderwerpen

- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Meer informatie over het schema](advanced-hunting-schema-reference.md)
- [Overzicht van threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md)

