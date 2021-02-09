---
title: De tabel DeviceInfo in het geavanceerde schema voor zoeken
description: Meer informatie over het besturingssysteem, de computernaam en andere computergegevens vindt u in de tabel DeviceInfo van het geavanceerde schema voor zoeken
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, machineinfo, DeviceInfo, device, machine, OS, platform, users
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
ms.openlocfilehash: 6462096a6c1b44ee11299f652a54f261d0355523
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145365"
---
# <a name="deviceinfo"></a>DeviceInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender



De `DeviceInfo` tabel in het geavanceerde [zoekschema](advanced-hunting-overview.md) bevat informatie over machines in de organisatie, zoals de versie van het besturingssysteem, actieve gebruikers en de naam van de computer. Gebruik deze verwijzing om query's te maken die gegevens uit deze tabel retourneren.

Zie het geavanceerde zoekschema voor meer informatie over andere tabellen in het geavanceerde schema [voor zoeken.](advanced-hunting-schema-tables.md)

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum en tijd waarop de gebeurtenis is vastgelegd |
| `DeviceId` | tekenreeks | Unieke id voor de computer in de service |
| `DeviceName` | tekenreeks | FQDN (Fully Qualified Domain Name) van de computer |
| `ClientVersion` | tekenreeks | Versie van de eindpuntagent of sensor die op de computer wordt uitgevoerd |
| `PublicIP` | tekenreeks | Het openbare IP-adres dat door de onboarded-computer wordt gebruikt om verbinding te maken met de Microsoft Defender for Endpoint-service. Dit kan het IP-adres zijn van de computer zelf, een NAT-apparaat of een proxy |
| `OSArchitecture` | tekenreeks | Architectuur van het besturingssysteem dat op de computer wordt uitgevoerd |
| `OSPlatform` | tekenreeks | Platform van het besturingssysteem dat op de computer wordt uitgevoerd. Dit geeft specifieke besturingssystemen aan, inclusief variaties binnen dezelfde familie, zoals Windows 10 en Windows 7 |
| `OSBuild` | tekenreeks | Buildversie van het besturingssysteem dat op de computer wordt uitgevoerd |
| `IsAzureADJoined` | boolean | Booleaanse indicator of de computer is verbonden met Azure Active Directory |
| `DeviceObjectId` | tekenreeks | Unieke id voor het apparaat in Azure AD |
| `LoggedOnUsers` | tekenreeks | Lijst met alle gebruikers die op de computer zijn aangemeld op het moment van de gebeurtenis in de JSON-matrixindeling |
| `RegistryDeviceTag` | tekenreeks | Machinetag toegevoegd via het register |
| `ReportId` | lang | Gebeurtenis-id op basis van een herhalende teller. Als u unieke gebeurtenissen wilt identificeren, moet deze kolom worden gebruikt in combinatie met de kolommen Apparaatnaam en Tijdstempel |
|`AdditionalFields` | tekenreeks | Aanvullende informatie over de gebeurtenis in de JSON-matrixindeling |
| `OSVersion` | tekenreeks | Versie van het besturingssysteem dat op de computer wordt uitgevoerd |
| `MachineGroup` | tekenreeks | De machinegroep van de computer. Deze groep wordt gebruikt door toegangsbeheer op basis van rollen om de toegang tot de computer te bepalen |

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Opsporen op apparaten en in e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
