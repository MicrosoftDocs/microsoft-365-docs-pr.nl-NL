---
title: DeviceTvmSecureConfigurationAssessmentKB-tabel in het geavanceerde jacht schema
description: Meer informatie over de diverse beveiligde configuraties die zijn goedgekeurd door risico & in de tabel DeviceTvmSecureConfigurationAssessmentKB van het schema geavanceerde jacht.
keywords: geavanceerde jacht, bedreigings jacht, Cyber Threat jacht, Microsoft Threat Protection, Microsoft 365, MTP, m365, Search, query, Telemetry, schema verwijzing, kusto, Table, Column, datatype, Description &, beveiliging, beveiliging, MITRE ATT&verzwakken, Knowledge Base, KB, DeviceTvmSecureConfigurationAssessmentKB
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
ms.collection:
- M365-security-compliance
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: f2642a46f952d3324cec4936aeb813d4ee5507d1
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412992"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a>DeviceTvmSecureConfigurationAssessmentKB

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft Threat Protection



De `DeviceTvmSecureConfigurationAssessmentKB` tabel in het geavanceerde jacht-schema bevat informatie over de verschillende veilige configuraties, zoals het feit of een apparaat automatische updates bevat, gecontroleerd op [bedreiging & beveiligingsbeheer](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt). Dit omvat ook risico informatie, verwante branche benchmarks en toepasselijke MITRE ATT&e technieken en tactieken. Gebruik deze verwijzing om query's te maken die gegevens uit de tabel retourneren.

Zie voor meer informatie over andere tabellen in het geavanceerde jacht-schema [de Naslaggids voor Geavanceerd](advanced-hunting-schema-tables.md)zoeken.

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `ConfigurationId` | tekenreeks | Unieke id voor een specifieke configuratie |
| `ConfigurationImpact` | tekenreeks | Geclassificeerde impact van de configuratie voor de totale configuratie Score (1-10) |
| `ConfigurationName` | tekenreeks | Naam van de configuratie weergeven |
| `ConfigurationDescription` | tekenreeks | Beschrijving van de configuratie |
| `RiskDescription` | tekenreeks | Beschrijving van het bijbehorende risico |
| `ConfigurationCategory` | tekenreeks | Categorie of groepering waartoe de configuratie behoort: toepassing, besturingssysteem, netwerk, accounts, beveiliging besturingselement|
| `ConfigurationSubcategory` | tekenreeks |Subcategorie of subgroep waartoe de configuratie behoort. In veel gevallen bevat dit een beschrijving van specifieke functies of functies. |
| `ConfigurationBenchmarks` | tekenreeks | Lijst met onderliggend verzekeringen met dezelfde of dezelfde configuratie |
| `RelatedMitreTechniques` | tekenreeks | Lijst met Mitre ATT&e Framework-technieken met betrekking tot de configuratie |
| `RelatedMitreTactics ` | tekenreeks | Lijst met Mitre ATT&e Framework tactiek met betrekking tot de configuratie |

## <a name="related-topics"></a>Verwante onderwerpen

- [Proactief zoeken naar bedreigingen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Opsporen op apparaten en in e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
- [Overzicht van Threat & beveiligingslek](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
