---
title: DeviceInfo-tabel in het geavanceerde jacht schema
description: Meer informatie over het besturingssysteem, de computernaam en andere informatie over de computer in de tabel DeviceInfo van het schema geavanceerde jacht
keywords: geavanceerde jacht, bedreigings jacht, Cyber Threat jacht, Microsoft Threat Protection, Microsoft 365, MTP, m365, Search, query, Telemetry, schema naslag, kusto, tabel, kolom, gegevenstype, beschrijving, machineinfo, DeviceInfo, apparaat, computer, systeem, platform, gebruikers
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
ms.openlocfilehash: 1bb48b4332bc9d60de15bb513f04a503d6a6913b
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842712"
---
# <a name="deviceinfo"></a>DeviceInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender



De `DeviceInfo` tabel in het [Geavanceerde bejachts](advanced-hunting-overview.md) schema bevat informatie over de computers in de organisatie, waaronder versie van het besturingssysteem, actieve gebruikers en computernaam. Gebruik deze verwijzing voor het maken van query's waarmee informatie uit deze tabel wordt geretourneerd.

Zie voor meer informatie over andere tabellen in het geavanceerde jacht-schema [de Naslaggids voor Geavanceerd](advanced-hunting-schema-tables.md)zoeken.

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | tijd | De datum en tijd waarop de gebeurtenis is vastgelegd |
| `DeviceId` | tekenreeks | Unieke id voor de computer in de service |
| `DeviceName` | tekenreeks | FQDN-naam (Fully Qualified Domain Name) van de computer |
| `ClientVersion` | tekenreeks | Versie van de eindpunt-agent of-sensor die op de computer wordt uitgevoerd |
| `PublicIP` | tekenreeks | Openbaar IP-adres dat wordt gebruikt door de gehoste computer om verbinding te maken met de Microsoft Defender voor eindpunt-service. Dit kan het IP-adres van de computer, een NAT-apparaat of een proxy zijn |
| `OSArchitecture` | tekenreeks | Architectuur van het besturingssysteem dat op de computer wordt uitgevoerd |
| `OSPlatform` | tekenreeks | Platform van het besturingssysteem dat op de computer wordt uitgevoerd. Dit geeft specifieke besturingssystemen aan, waaronder variaties in dezelfde familie, zoals Windows 10 en Windows 7 |
| `OSBuild` | tekenreeks | Build-versie van het besturingssysteem dat op de computer wordt uitgevoerd |
| `IsAzureADJoined` | Boolean | Booleaanse aanduiding of de computer is verbonden met Azure Active Directory |
| `LoggedOnUsers` | tekenreeks | Lijst met alle gebruikers die op de computer zijn aangemeld wanneer de gebeurtenis in de JSON-matrix indeling wordt gebruikt |
| `RegistryDeviceTag` | tekenreeks | De code van de computer die is toegevoegd via het register |
| `ReportId` | lang | Gebeurtenis-id op basis van een herhalende teller. Als u unieke gebeurtenissen wilt identificeren, moet deze kolom worden gebruikt in combinatie met de naam van het apparaat en de timestamp-kolommen. |
| `OSVersion` | tekenreeks | Versie van het besturingssysteem dat op de computer wordt uitgevoerd |
| `MachineGroup` | tekenreeks | Computergroep van de computer. Deze groep wordt gebruikt door toegangsbeheer op basis van rollen om de toegang tot de computer te bepalen. |

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Opsporen op apparaten en in e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
