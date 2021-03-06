---
title: DeviceTvmSecureConfigurationAssessmentKB-tabel in het geavanceerde schema voor de jacht
description: Meer informatie over de verschillende beveiligde configuraties die zijn beoordeeld door Threat & Vulnerability Management in de tabel DeviceTvmSecureConfigurationAssessmentKB van het geavanceerde schema voor de jacht.
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, security configuration, MITRE ATT&CK framework, knowledge base, KB, DeviceTvmSecureConfigurationAssessmentKB
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
ms.openlocfilehash: 1dfa710b86afdcfd8a5643555564a0f34c7b4702
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/26/2021
ms.locfileid: "52024239"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a>DeviceTvmSecureConfigurationAssessmentKB

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender
- Microsoft Defender voor Eindpunt



De tabel in het geavanceerde schema bevat informatie over de verschillende beveiligde configuraties, zoals of een apparaat automatische updates heeft ingeschakeld, gecontroleerd door `DeviceTvmSecureConfigurationAssessmentKB` Threat & Vulnerability [Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt). Het omvat ook risicogegevens, gerelateerde industriebenchmarks en toepasselijke MITRE ATT-&CK-technieken en -tactieken. Gebruik deze verwijzing om query's te maken die gegevens uit de tabel retourneren.

Zie de geavanceerde zoekverwijzing voor meer informatie over andere tabellen in het geavanceerde schema voor [de jacht.](advanced-hunting-schema-tables.md)

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `ConfigurationId` | tekenreeks | Unieke id voor een specifieke configuratie |
| `ConfigurationImpact` | tekenreeks | Beoordeelde invloed van de configuratie op de algemene configuratiescore (1-10) |
| `ConfigurationName` | tekenreeks | Weergavenaam van de configuratie |
| `ConfigurationDescription` | tekenreeks | Beschrijving van de configuratie |
| `RiskDescription` | tekenreeks | Beschrijving van het bijbehorende risico |
| `ConfigurationCategory` | tekenreeks | Categorie of groepering waarvan de configuratie deel uitmaken: Toepassing, BE, Netwerk, Accounts, Beveiligingsbesturingselementen|
| `ConfigurationSubcategory` | tekenreeks |Subcategorie of subgroepering waarvan de configuratie deel uitmaken. In veel gevallen worden hier specifieke mogelijkheden of functies beschreven. |
| `ConfigurationBenchmarks` | tekenreeks | Lijst met industriebenchmarks die dezelfde of vergelijkbare configuratie aanbevelen |
| `Tags` | tekenreeks | Labels met verschillende kenmerken die worden gebruikt om een beveiligingsconfiguratie te identificeren of te categoriseren |
| `RemediationOptions` | tekenreeks | Aanbevolen acties om eventuele bijbehorende risico's te beperken of aan te pakken |

## <a name="related-topics"></a>Verwante onderwerpen

- [Proactief op bedreigingen zoeken](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Opsporen op apparaten en in e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
- [Overzicht van threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)