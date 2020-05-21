---
title: DeviceTvmSecureConfigurationAssessment tabel in het geavanceerde jachtschema
description: Meer informatie over beveiligingsbeoordelingsgebeurtenissen voor het & van vulnerability management vindt u in de tabel DeviceTvmSecureConfigurationAssessment van het geavanceerde jachtschema. Deze gebeurtenissen bieden machine-informatie, beveiligingsconfiguratiegegevens, impact en nalevingsinformatie.
keywords: geavanceerde jacht, dreigingsjacht, cyberdreigingsjacht, bescherming tegen microsoft-bedreigingen, microsoft 365, mtp, m365, zoekopdracht, query, telemetrie, schemareferentie, kusto, tabel, kolom, gegevenstype, beschrijving, bedreiging & kwetsbaarheidsbeheer, TVM, apparaatbeheer, beveiligingsconfiguratie, DeviceTvmSecureConfigurationAssessment
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
ms.openlocfilehash: ade218a440f8e7db223460e95363eae2cb659622
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327951"
---
# <a name="devicetvmsecureconfigurationassessment"></a>DeviceTvmSecureConfigurationAssessment

**Geldt voor:**
- Microsoft Threat Protection



Elke rij in de `DeviceTvmSecureConfigurationAssessment` tabel bevat een beoordelingsgebeurtenis voor een specifieke beveiligingsconfiguratie van [Threat & Vulnerability Management.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) Gebruik deze verwijzing om de meest recente beoordelingsresultaten te controleren en te bepalen of apparaten compatibel zijn.

Voor informatie over andere tabellen in de geavanceerde jacht schema, zie [de geavanceerde jacht referentie](advanced-hunting-schema-tables.md).

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `DeviceId` | Tekenreeks | Unieke id voor de machine in de service |
| `DeviceName` | Tekenreeks | Volledig gekwalificeerde domeinnaam (FQDN) van de machine |
| `OSPlatform` | Tekenreeks | Platform van het besturingssysteem dat op de machine draait. Dit geeft specifieke besturingssystemen aan, waaronder variaties binnen dezelfde familie, zoals Windows 10 en Windows 7.|
| `Timestamp` | Datetime | Datum en tijd waarop de record is gegenereerd |
| `ConfigurationId` | Tekenreeks | Unieke id voor een specifieke configuratie |
| `ConfigurationCategory` | Tekenreeks | Categorie of groepering waartoe de configuratie behoort: Toepassing, BE, Netwerk, Accounts, Beveiligingsbesturingselementen |
| `ConfigurationSubcategory` | Tekenreeks | Subcategorie of subgroep waartoe de configuratie behoort. In veel gevallen worden specifieke mogelijkheden of functies beschreven. |
| `ConfigurationImpact` | Tekenreeks | Nominale impact van de configuratie op de totale configuratiescore (1-10) |
| `IsCompliant` | Booleaanse | Geeft aan of de configuratie of het beleid correct is geconfigureerd |

## <a name="related-topics"></a>Verwante onderwerpen

- [Proactief op zoek naar bedreigingen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Zoek naar bedreigingen op verschillende apparaten en e-mails](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
- [Overzicht van Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
