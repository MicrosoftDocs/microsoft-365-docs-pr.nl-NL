---
title: DeviceTvmSecureConfigurationAssessment-tabel in het geavanceerde jacht schema
description: Meer informatie over bedreiging & beveiligings evaluatie gebeurtenissen in de tabel DeviceTvmSecureConfigurationAssessment van het schema geavanceerde jacht. Deze gebeurtenissen geven informatie over de computer en ook van Beveiligingsconfiguratie Details, van invloed tot informatie over naleving.
keywords: geavanceerde jacht, bedreigings jacht, Cyber Threat-jacht, Microsoft Threat Protection, Microsoft 365, MTP, m365, Search, query, Telemetry, schema Reference, kusto, Table, Column, datatype, een beschrijving, bedreiging & beveiligingsconfiguratie, DeviceTvmSecureConfigurationAssessment
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
ms.openlocfilehash: f25c0ad47a520ec23a94775b64a4f1ecc2eb9486
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/09/2020
ms.locfileid: "48414248"
---
# <a name="devicetvmsecureconfigurationassessment"></a>DeviceTvmSecureConfigurationAssessment

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft Threat Protection



Elke rij in de `DeviceTvmSecureConfigurationAssessment` tabel bevat een beoordelings gebeurtenis voor een bepaalde beveiligingsconfiguratie, van [bedreiging & beveiligingsbeheer](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt). Gebruik deze naslag voor de laatste beoordelings resultaten en bepaal of apparaten compatibel zijn.

Zie voor meer informatie over andere tabellen in het geavanceerde jacht-schema [de Naslaggids voor Geavanceerd](advanced-hunting-schema-tables.md)zoeken.

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `DeviceId` | tekenreeks | Unieke id voor de computer in de service |
| `DeviceName` | tekenreeks | FQDN-naam (Fully Qualified Domain Name) van de computer |
| `OSPlatform` | tekenreeks | Platform van het besturingssysteem dat op de computer wordt uitgevoerd. Dit geeft specifieke besturingssystemen aan, met inbegrip van variaties in dezelfde familie, zoals Windows 10 en Windows 7.|
| `Timestamp` | tijd | De datum en tijd waarop de record is gegenereerd |
| `ConfigurationId` | tekenreeks | Unieke id voor een specifieke configuratie |
| `ConfigurationCategory` | tekenreeks | Categorie of groepering waartoe de configuratie behoort: toepassing, besturingssysteem, netwerk, accounts, beveiliging besturingselement |
| `ConfigurationSubcategory` | tekenreeks | Subcategorie of subgroep waartoe de configuratie behoort. In veel gevallen bevat dit een beschrijving van specifieke functies of functies. |
| `ConfigurationImpact` | tekenreeks | Geclassificeerde impact van de configuratie voor de totale configuratie Score (1-10) |
| `IsCompliant` | Boolean | Geeft aan of de configuratie of het beleid correct is geconfigureerd |

## <a name="related-topics"></a>Verwante onderwerpen

- [Proactief zoeken naar bedreigingen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Opsporen op apparaten en in e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
- [Overzicht van Threat & beveiligingslek](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
