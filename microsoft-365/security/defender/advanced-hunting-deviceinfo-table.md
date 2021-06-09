---
title: Tabel DeviceInfo in het geavanceerde schema voor de jacht
description: Meer informatie over besturingssysteem, computernaam en andere computergegevens in de tabel DeviceInfo van het geavanceerde schema voor de jacht
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, machineinfo, DeviceInfo, device, machine, OS, platform, users
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
ms.openlocfilehash: 99a07b1517058b0e5ab241aaae9c6899e2994432
ms.sourcegitcommit: 82a4d74020cd93ba444006317cfecc178c6d41dc
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689107"
---
# <a name="deviceinfo"></a>DeviceInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender
- Microsoft Defender voor Eindpunt



De tabel in het geavanceerde schema voor de jacht bevat informatie over apparaten in de organisatie, waaronder `DeviceInfo` besturingssysteemversie, actieve gebruikers en computernaam. [](advanced-hunting-overview.md) Gebruik deze verwijzing om query's te maken die gegevens uit deze tabel retourneren.

Zie de geavanceerde zoekverwijzing voor meer informatie over andere tabellen in het geavanceerde schema voor [de jacht.](advanced-hunting-schema-tables.md)

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum en tijd waarop de gebeurtenis is opgenomen |
| `DeviceId` | tekenreeks | Unieke id voor de machine in de service |
| `DeviceName` | tekenreeks | Volledig gekwalificeerde domeinnaam (FQDN) van de computer |
| `ClientVersion` | tekenreeks | Versie van de eindpuntagent of -sensor die op de computer wordt uitgevoerd |
| `PublicIP` | tekenreeks | Openbaar IP-adres dat door de onboarded-computer wordt gebruikt om verbinding te maken met de Microsoft Defender voor Eindpunt-service. Dit kan het IP-adres van de computer zelf, een NAT-apparaat of een proxy zijn |
| `OSArchitecture` | tekenreeks | Architectuur van het besturingssysteem dat op de computer wordt uitgevoerd |
| `OSPlatform` | tekenreeks | Platform van het besturingssysteem dat op de computer wordt uitgevoerd. Dit geeft specifieke besturingssystemen aan, waaronder variaties binnen dezelfde familie, zoals Windows 10 en Windows 7 |
| `OSBuild` | tekenreeks | Build-versie van het besturingssysteem dat op de computer wordt uitgevoerd |
| `IsAzureADJoined` | booleaanse | Booleaanse indicator van de vraag of de machine is verbonden met de Azure Active Directory |
| `AadObjectId` | tekenreeks | Unieke id voor het apparaat in Azure AD |
| `LoggedOnUsers` | tekenreeks | Lijst met alle gebruikers die zijn aangemeld op de computer op het moment van de gebeurtenis in de JSON-matrixindeling |
| `RegistryDeviceTag` | tekenreeks | Machinetag toegevoegd via het register |
| `OSVersion` | tekenreeks | Versie van het besturingssysteem dat op de computer wordt uitgevoerd |
| `MachineGroup` | tekenreeks | Machinegroep van de machine. Deze groep wordt gebruikt door op rollen gebaseerd toegangsbeheer om de toegang tot de computer te bepalen |
| `ReportId` | lang | Gebeurtenis-id op basis van een herhalende teller. Als u unieke gebeurtenissen wilt identificeren, moet deze kolom worden gebruikt in combinatie met de kolommen DeviceName en Timestamp |
| `OnboardingStatus` | tekenreeks | Geeft aan of het apparaat al dan niet is onboarded bij Microsoft Defender For Endpoint of dat het apparaat niet wordt ondersteund |
|`AdditionalFields` | tekenreeks | Aanvullende informatie over de gebeurtenis in de JSON-matrixindeling |
|`DeviceCategory` | tekenreeks | Bredere classificatie die bepaalde apparaattypen groept onder de volgende categorieën: Eindpunt, Netwerkapparaat, IoT, Onbekend |
|`DeviceType` | tekenreeks | Type apparaat op basis van doel en functionaliteit, zoals netwerkapparaat, werkstation, server, mobiel, gameconsole of printer |
|`DeviceSubType` | tekenreeks | Extra modifier voor bepaalde typen apparaten, bijvoorbeeld een mobiel apparaat kan een tablet of smartphone zijn |
|`Model` | tekenreeks | Modelnaam of nummer van het product van de leverancier of fabrikant |
|`Vendor` | tekenreeks | Naam van de leverancier of fabrikant van het product |
|`OSDistribution` | tekenreeks | Distributie van het besturingssysteemplatform, zoals Ubuntu of RedHat voor Linux-platforms |
|`OSVersionInfo` | tekenreeks | Aanvullende informatie over de besturingssysteemversie, zoals de populaire naam, codenaam of versienummer |
|`MergedDeviceIds` | tekenreeks | Vorige apparaat-ID's die aan hetzelfde apparaat zijn toegewezen |
|`MergedToDeviceId` | tekenreeks | De meest recente apparaat-id die is toegewezen aan een apparaat |

De `DeviceInfo` tabel bevat apparaatgegevens op basis van hartslagen, die periodieke rapporten of signalen van een apparaat zijn. Om de vijftien minuten verzendt het apparaat een gedeeltelijke hartslag die vaak wisselende kenmerken bevat, zoals `LoggedOnUsers` . Eenmaal per dag wordt een volledige hartslag verzonden met de kenmerken van het apparaat.

U kunt de volgende voorbeeldquery gebruiken om de meest recente status van een apparaat te krijgen:

```kusto
// Get latest information on user/device
DeviceInfo
| where DeviceName == "example" and isnotempty(OSPlatform)
| summarize arg_max(Timestamp, *) by DeviceId 
```

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Opsporen op apparaten en in e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
