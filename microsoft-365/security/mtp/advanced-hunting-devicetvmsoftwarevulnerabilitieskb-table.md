---
title: DeviceTvmSoftwareVulnerabilitiesKB-tabel in het geavanceerde jacht schema
description: Meer informatie over de beveiligingsproblemen die worden bijgehouden door risico & het beveiligingsbeheer in de tabel DeviceTvmSoftwareVulnerabilitiesKB van het schema Advanced jacht.
keywords: geavanceerde jacht, bedreigings jacht, Cyber Threat-jacht, Microsoft Threat Protection, Microsoft 365, MTP, m365, Search, query, Telemetry, schema, Reference, kusto, Table, Column, Reference,, Table, Column, datatype, Description, Threat &, software
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
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: f5cbc037dce72979874be6246a24ea3491a90df1
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847486"
---
# <a name="devicetvmsoftwarevulnerabilitieskb"></a>DeviceTvmSoftwareVulnerabilitiesKB

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender



De `DeviceTvmSoftwareVulnerabilitiesKB` tabel in het geavanceerde jacht-schema bevat de lijst met problemen die zich voordoen [& risicobeheer](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) apparatuur beoordeelt. Gebruik deze verwijzing om query's te maken die gegevens uit de tabel retourneren.

Zie voor meer informatie over andere tabellen in het geavanceerde jacht-schema [de Naslaggids voor Geavanceerd](advanced-hunting-schema-tables.md)zoeken.

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `CveId` | tekenreeks | Unieke id die is toegewezen aan het beveiligingsprobleem onder het systeem veelvoorkomende problemen en blootstellingen (CVE) |
| `CvssScore` | tekenreeks | Prioriteitsscore die is toegewezen aan het beveiligingsprobleem onder de informatie over het algemene beveiligingslek (CVSS) |
| `IsExploitAvailable` | Boolean | Geeft aan of de beschikbare code voor het beveiligingslek openbaar verkrijgbaar is |
| `VulnerabilitySeverityLevel` | tekenreeks | Prioriteitsniveau dat is toegewezen aan het beveiligingsprobleem op basis van de CVSS-Score en dynamische factoren die worden beïnvloed door de bedreigings niveau liggend |
| `LastModifiedTime` | tijd | De datum en tijd waarop het item of de bijbehorende metagegevens voor het laatst zijn gewijzigd |
| `PublishedDate` | tijd | De datum waarop het beveiligingslek openbaar is gemaakt |
| `VulnerabilityDescription` | tekenreeks | Beschrijving van het risico en de gekoppelde Risico's |
| `AffectedSoftware` | tekenreeks | Lijst van alle softwareproducten die worden beïnvloed door het beveiligingslek |

## <a name="related-topics"></a>Verwante onderwerpen

- [Proactief zoeken naar bedreigingen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Opsporen op apparaten en in e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
- [Overzicht van Threat & beveiligingslek](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
