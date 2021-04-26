---
title: DeviceTvmSecureConfigurationAssessment table in the advanced hunting schema
description: Meer informatie over beveiligingsbeoordelingsgebeurtenissen in de tabel DeviceTvmSecureConfigurationAssessment van het geavanceerde schema voor de jacht. Deze bedreigingen & beveiligingsrisico's bevatten apparaatgegevens, evenals beveiligingsconfiguratiegegevens, impact- en compliancegegevens.
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, security configuration, DeviceTvmSecureConfigurationAssessment
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
ms.openlocfilehash: 2e3e649911cb2ce63c2a49be0ebc93e35e8055d6
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/26/2021
ms.locfileid: "52024215"
---
# <a name="devicetvmsecureconfigurationassessment"></a>DeviceTvmSecureConfigurationAssessment

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender
- Microsoft Defender voor Eindpunt



Elke rij in de `DeviceTvmSecureConfigurationAssessment` tabel bevat een beoordelingsgebeurtenis voor een specifieke beveiligingsconfiguratie van [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt). Gebruik deze verwijzing om de meest recente evaluatieresultaten te controleren en te bepalen of apparaten compatibel zijn.

Zie de geavanceerde zoekverwijzing voor meer informatie over andere tabellen in het geavanceerde schema voor [de jacht.](advanced-hunting-schema-tables.md)

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `DeviceId` | tekenreeks | Unieke id voor het apparaat in de service |
| `DeviceName` | tekenreeks | Volledig gekwalificeerde domeinnaam (FQDN) van het apparaat |
| `OSPlatform` | tekenreeks | Platform van het besturingssysteem dat op het apparaat wordt uitgevoerd. Dit geeft specifieke besturingssystemen aan, waaronder variaties binnen dezelfde familie, zoals Windows 10 en Windows 7.|
| `Timestamp` | datetime | Datum en tijd waarop de record is gegenereerd |
| `ConfigurationId` | tekenreeks | Unieke id voor een specifieke configuratie |
| `ConfigurationCategory` | tekenreeks | Categorie of groepering waarvan de configuratie deel uitmaken: Toepassing, BE, Netwerk, Accounts, Beveiligingsbesturingselementen |
| `ConfigurationSubcategory` | tekenreeks | Subcategorie of subgroepering waarvan de configuratie deel uitmaken. In veel gevallen worden hier specifieke mogelijkheden of functies beschreven. |
| `ConfigurationImpact` | tekenreeks | Beoordeelde invloed van de configuratie op de algemene configuratiescore (1-10) |
| `IsCompliant` | booleaanse | Geeft aan of de configuratie of het beleid juist is geconfigureerd |
| `IsApplicable` | booleaanse | Geeft aan of de configuratie of het beleid van toepassing is op het apparaat |
| `Context` | tekenreeks | Aanvullende contextuele informatie over de configuratie of het beleid |
| `IsExpectedUserImpact` | booleaanse | Geeft aan of er gevolgen voor de gebruiker zijn als de configuratie of het beleid wordt toegepast |

## <a name="related-topics"></a>Verwante onderwerpen

- [Proactief op bedreigingen zoeken](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Opsporen op apparaten en in e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
- [Overzicht van threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)