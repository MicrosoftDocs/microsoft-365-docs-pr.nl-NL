---
title: DeviceTvmSecureConfigurationAssessment table in the advanced hunting schema
description: Meer informatie over & beveiligingsbeoordelingsgebeurtenissen voor beveiligingsrisico's in de tabel DeviceTvmSecureConfigurationAssessment van het schema Geavanceerd. Deze gebeurtenissen bevatten apparaatgegevens en beveiligingsconfiguratiegegevens, impact- en compliancegegevens.
keywords: advanced hunting, threat hunting, cyber threat hunting, mdatp, microsoft defender atp, wdatp search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, security configuration, DeviceTvmSecureConfigurationAssessment
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 1be5d911d1a2d21abdadce5745151a2778361672
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059766"
---
# <a name="devicetvmsecureconfigurationassessment"></a>DeviceTvmSecureConfigurationAssessment 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)



>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

Elke rij in de `DeviceTvmSecureConfigurationAssessment` tabel bevat een beoordelingsgebeurtenis voor een specifieke beveiligingsconfiguratie van [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md). Gebruik deze verwijzing om de meest recente evaluatieresultaten te controleren en te bepalen of apparaten compatibel zijn.

Zie de geavanceerde zoekverwijzing voor meer informatie over andere tabellen in het geavanceerde schema voor [de jacht.](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `DeviceId` | tekenreeks | Unieke id voor het apparaat in de service |
| `DeviceName` | tekenreeks | Volledig gekwalificeerde domeinnaam (FQDN) van het apparaat |
| `OSPlatform` | tekenreeks | Platform van het besturingssysteem dat op het apparaat wordt uitgevoerd. Dit geeft specifieke besturingssystemen aan, waaronder variaties binnen dezelfde familie, zoals Windows 10 en Windows 7.|
| `Timestamp` | datetime |Datum en tijd waarop de record is gegenereerd |
| `ConfigurationId` | tekenreeks | Unieke id voor een specifieke configuratie |
| `ConfigurationCategory` | tekenreeks | Categorie of groepering waarvan de configuratie deel uitmaken: Toepassing, BE, Netwerk, Accounts, Beveiligingsbesturingselementen |
| `ConfigurationSubcategory` | tekenreeks |Subcategorie of subgroepering waarvan de configuratie deel uitmaken. In veel gevallen worden hier specifieke mogelijkheden of functies beschreven. |
| `ConfigurationImpact` | tekenreeks | Beoordeelde invloed van de configuratie op de algemene configuratiescore (1-10) |
| `IsCompliant` | booleaanse | Geeft aan of de configuratie of het beleid juist is geconfigureerd |
| `IsApplicable` | booleaanse | Geeft aan of de configuratie of het beleid van toepassing is op het apparaat |
| `Context` | tekenreeks | Aanvullende contextuele informatie over de configuratie of het beleid |
| `IsExpectedUserImpactCompliant` | booleaanse | Geeft aan of er gevolgen voor de gebruiker zijn als de configuratie of het beleid wordt toegepast |

## <a name="related-topics"></a>Verwante onderwerpen

- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Meer informatie over het schema](advanced-hunting-schema-reference.md)
- [Overzicht van threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md)