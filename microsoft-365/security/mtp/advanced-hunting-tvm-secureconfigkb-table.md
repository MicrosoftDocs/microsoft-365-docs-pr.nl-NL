---
title: DeviceTvmSecureConfigurationAssessmentKB-tabel in het geavanceerde jachtschema
description: Lees meer over de verschillende beveiligde configuraties die zijn beoordeeld door Threat & Vulnerability Management in de DeviceTvmSecureConfigurationAssessmentKB-tabel van het geavanceerde jachtschema.
keywords: geavanceerde jacht, dreigingsjacht, cyberdreigingsjacht, bescherming tegen microsoft-dreigingen, microsoft 365, mtp, m365, zoekopdracht, query, telemetrie, schemareferentie, kusto, tabel, kolom, gegevenstype, beschrijving, bedreiging & kwetsbaarheidsbeheer, TVM, apparaatbeheer, beveiligingsconfiguratie, MITRE ATT&CK-framework, kennisbank, KB, DeviceTvmSecureConfigurationAssessment
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
ms.openlocfilehash: a265bb84b0ad59ee56cb0f0670951bab1bcd344a
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/24/2020
ms.locfileid: "42806321"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a>DeviceTvmSecureConfigurationAssessmentKB

**Van toepassing op:**
- Microsoft-bedreigingsbeveiliging



De `DeviceTvmSecureConfigurationAssessmentKB` tabel in het geavanceerde jachtschema bevat informatie over de verschillende beveiligde configuraties - zoals of een apparaat automatische updates heeft ingeschakeld - gecontroleerd door [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt). Het omvat ook risico-informatie, gerelateerde industrie benchmarks, en de toepasselijke MITRE ATT&CK technieken en tactieken. Gebruik deze verwijzing om query's te construeren die informatie uit de tabel retourneren.

Voor informatie over andere tabellen in de geavanceerde jacht schema, zie [de geavanceerde jacht referentie](advanced-hunting-schema-tables.md).

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `ConfigurationId` | Tekenreeks | Unieke id voor een specifieke configuratie |
| `ConfigurationImpact` | Tekenreeks | Nominale impact van de configuratie op de totale configuratiescore (1-10) |
| `ConfigurationName` | Tekenreeks | Weergavenaam van de configuratie |
| `ConfigurationDescription` | Tekenreeks | Beschrijving van de configuratie |
| `RiskDescription` | Tekenreeks | Beschrijving van het bijbehorende risico |
| `ConfigurationCategory` | Tekenreeks | Categorie of groepering waartoe de configuratie behoort: Toepassing, BE, Netwerk, Accounts, Beveiligingsbesturingselementen|
| `ConfigurationSubcategory` | Tekenreeks |Subcategorie of subgroep waartoe de configuratie behoort. In veel gevallen worden specifieke mogelijkheden of functies beschreven. |
| `ConfigurationBenchmarks` | Tekenreeks | Lijst van industriebenchmarks die dezelfde of vergelijkbare configuratie aanbevelen |
| `RelatedMitreTechniques` | Tekenreeks | Lijst van Mitre ATT&CK framework technieken met betrekking tot de configuratie |
| `RelatedMitreTactics ` | Tekenreeks | Lijst van Mitre ATT&CK framework tactiek met betrekking tot de configuratie |

## <a name="related-topics"></a>Verwante onderwerpen

- [Proactief op zoek naar bedreigingen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Zoek naar bedreigingen op verschillende apparaten en e-mails](advanced-hunting-query-emails-devices.md)
- [Het schema begrijpen](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
- [Overzicht van Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
