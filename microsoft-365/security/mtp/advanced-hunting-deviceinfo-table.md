---
title: DeviceInfo-tabel in het geavanceerde jachtschema
description: Meer informatie over besturingssysteem, computernaam en andere machine-informatie in de tabel DeviceInfo van het geavanceerde jachtschema
keywords: geavanceerde jacht, dreiging jacht, cyber dreiging jacht, Microsoft bedreiging bescherming, Microsoft 365, mtp, m365, zoeken, query, telemetrie, schema referentie, kusto, tabel, kolom, gegevenstype, beschrijving, machineinfo, DeviceInfo, apparaat, machine, OS, platform Gebruikers
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
ms.openlocfilehash: 71bd9e9ff1dfb17e4a9266d9ee351799e18888c9
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/24/2020
ms.locfileid: "42809538"
---
# <a name="deviceinfo"></a>DeviceInfo

**Van toepassing op:**
- Microsoft-bedreigingsbeveiliging



De `DeviceInfo` tabel in het [geavanceerde jachtschema](advanced-hunting-overview.md) bevat informatie over machines in de organisatie, waaronder de OS-versie, actieve gebruikers en de naam van de computer. Gebruik deze verwijzing om query's te construeren die informatie uit deze tabel retourneren.

Voor informatie over andere tabellen in de geavanceerde jacht schema, [zie de geavanceerde jacht referentie](advanced-hunting-schema-tables.md).

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | Datetime | Datum en tijdstip waarop de gebeurtenis is geregistreerd |
| `DeviceId` | Tekenreeks | Unieke id voor de machine in de service |
| `DeviceName` | Tekenreeks | Volledig gekwalificeerde domeinnaam (FQDN) van de machine |
| `ClientVersion` | Tekenreeks | Versie van de endpoint-agent of sensor die op de machine wordt uitgevoerd |
| `PublicIP` | Tekenreeks | Openbaar IP-adres dat door de aanboordmachine wordt gebruikt om verbinding te maken met de Microsoft Defender ATP-service. Dit kan het IP-adres van de machine zelf, een NAT-apparaat of een proxy zijn |
| `OSArchitecture` | Tekenreeks | Architectuur van het besturingssysteem dat op de machine draait |
| `OSPlatform` | Tekenreeks | Platform van het besturingssysteem dat op de machine draait. Dit geeft specifieke besturingssystemen aan, waaronder variaties binnen dezelfde familie, zoals Windows 10 en Windows 7 |
| `OSBuild` | Tekenreeks | Build versie van het besturingssysteem draait op de machine |
| `IsAzureADJoined` | Booleaanse | Booleaanse indicator of de machine is verbonden met de Azure Active Directory |
| `LoggedOnUsers` | Tekenreeks | Lijst met alle gebruikers die op het moment van de gebeurtenis op de machine zijn aangemeld in JSON-arrayindeling |
| `RegistryDeviceTag` | Tekenreeks | Machinetag toegevoegd via het register |
| `ReportId` | Lange | Gebeurtenis-id op basis van een herhalingsteller. Om unieke gebeurtenissen te identificeren, moet deze kolom worden gebruikt in combinatie met de kolommen DeviceName en Timestamp |
| `OSVersion` | Tekenreeks | Versie van het besturingssysteem die op de machine draait |
| `MachineGroup` | Tekenreeks | Machinegroep van de machine. Deze groep wordt gebruikt door op rollen gebaseerd toegangscontrole om de toegang tot de machine te bepalen |

## <a name="related-topics"></a>Verwante onderwerpen
- [Proactief op zoek naar bedreigingen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Zoek naar bedreigingen op verschillende apparaten en e-mails](advanced-hunting-query-emails-devices.md)
- [Het schema begrijpen](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
