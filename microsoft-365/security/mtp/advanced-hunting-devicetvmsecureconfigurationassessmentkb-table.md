---
title: DeviceTvmSecureConfigurationAssessmentKB in het geavanceerde schema voor zoeken
description: Meer informatie over de verschillende veilige configuraties die zijn geëvalueerd op basis van Bedreiging & Beveiligingsprobleembeheer in de tabel DeviceTvmSecureConfigurationAssessmentKB van het geavanceerde zoekschema.
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, security configuration, MITRE ATT&CK framework, Knowledge Base, KB, DeviceTvmSecureConfigurationAssessmentKB
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
ms.openlocfilehash: cf4204767843b9a9e0b0bbfecc2d3fc50db531fc
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145449"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a>DeviceTvmSecureConfigurationAssessmentKB

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender



De tabel in het geavanceerde schema voor zoeken bevat informatie over de verschillende veilige configuraties (zoals of op een apparaat automatische updates zijn ingeschakeld) die zijn ingeschakeld door `DeviceTvmSecureConfigurationAssessmentKB` [Threat & Vulnerability Management.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) Het omvat ook risicogegevens, gerelateerde industriebe benchmarks en toepasselijke MITRE ATT&CK-technieken en -technieken. Gebruik deze verwijzing om query's te maken die gegevens uit de tabel retourneren.

Zie het geavanceerde zoekschema voor informatie over andere tabellen in het geavanceerde schema voor [het zoeken.](advanced-hunting-schema-tables.md)

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `ConfigurationId` | tekenreeks | Unieke id voor een specifieke configuratie |
| `ConfigurationImpact` | tekenreeks | Beoordeelde invloed van de configuratie op de totale configuratiescore (1-10) |
| `ConfigurationName` | tekenreeks | Weergavenaam van de configuratie |
| `ConfigurationDescription` | tekenreeks | Beschrijving van de configuratie |
| `RiskDescription` | tekenreeks | Beschrijving van het bijbehorende risico |
| `ConfigurationCategory` | tekenreeks | Tot welke categorie of groepering de configuratie behoort: Toepassing, besturingssysteem, netwerk, accounts, beveiligingsbesturingselementen|
| `ConfigurationSubcategory` | tekenreeks |Subcategorie of subgroepering tot welke de configuratie behoort. In veel gevallen wordt hier specifieke functionaliteit of functies beschreven. |
| `ConfigurationBenchmarks` | tekenreeks | Lijst met industriebe benchmarks die dezelfde of vergelijkbare configuratie aanbevelen |
| `Tags` | tekenreeks | Labels voor de verschillende kenmerken die worden gebruikt om een beveiligingsconfiguratie te identificeren of te categoriseren |
| `RemediationOptions` | tekenreeks | Aanbevolen acties om eventuele bijbehorende risico's te beperken of aan te pakken |

## <a name="related-topics"></a>Verwante onderwerpen

- [Proactief zoeken naar bedreigingen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Opsporen op apparaten en in e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
- [Overzicht van risicobeheer & beveiligingsprobleem](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
