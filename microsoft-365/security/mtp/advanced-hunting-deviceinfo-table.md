---
title: DeviceInfo-tabel in het geavanceerde jachtschema
description: Meer informatie over besturingssysteem, computernaam en andere machine-informatie in de DeviceInfo-tabel van het geavanceerde jachtschema
keywords: geavanceerde jacht, bedreiging jacht, cyber bedreiging jacht, Microsoft threat protection, Microsoft 365, mtp, m365, zoeken, query, telemetrie, schema referentie, kusto, tabel, kolom, gegevenstype, beschrijving, machineinfo, DeviceInfo, apparaat, machine, OS, platform, gebruikers
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
ms.openlocfilehash: 526e210a472862593f2652e9b2b21957702c48f0
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899277"
---
# <a name="deviceinfo"></a>DeviceInfo

**Van toepassing op:**
- Microsoft Threat Protection



De `DeviceInfo` tabel in het geavanceerde [jachtschema](advanced-hunting-overview.md) bevat informatie over machines in de organisatie, waaronder de OS-versie, actieve gebruikers en de computernaam. Gebruik deze verwijzing om query's te construeren die informatie uit deze tabel retourneren.

Zie [de geavanceerde jachtreferentie](advanced-hunting-schema-tables.md)voor informatie over andere tabellen in het geavanceerde jachtschema.

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | Datetime | Datum en tijdstip waarop de gebeurtenis is geregistreerd |
| `DeviceId` | Tekenreeks | Unieke id voor de machine in de service |
| `DeviceName` | Tekenreeks | Volledig gekwalificeerde domeinnaam (FQDN) van de machine |
| `ClientVersion` | Tekenreeks | Versie van de eindpuntagent of -sensor die op de machine wordt uitgevoerd |
| `PublicIP` | Tekenreeks | Openbaar IP-adres dat door de ingebouwde machine wordt gebruikt om verbinding te maken met de Microsoft Defender ATP-service. Dit kan het IP-adres zijn van de machine zelf, een NAT-apparaat of een proxy |
| `OSArchitecture` | Tekenreeks | Architectuur van het besturingssysteem dat op de machine draait |
| `OSPlatform` | Tekenreeks | Platform van het besturingssysteem dat op de machine draait. Dit duidt op specifieke besturingssystemen, waaronder variaties binnen dezelfde familie, zoals Windows 10 en Windows 7 |
| `OSBuild` | Tekenreeks | Bouwversie van het besturingssysteem dat op de machine draait |
| `IsAzureADJoined` | Booleaanse | Booleaanse indicator van de vraag of de machine is verbonden met de Azure Active Directory |
| `LoggedOnUsers` | Tekenreeks | Lijst van alle gebruikers die op het moment van de gebeurtenis op de machine zijn aangemeld in de JSON-arrayindeling |
| `RegistryDeviceTag` | Tekenreeks | Machinetag toegevoegd via het register |
| `ReportId` | Lange | Gebeurtenis-id op basis van een herhalende teller. Om unieke gebeurtenissen te identificeren, moet deze kolom worden gebruikt in combinatie met de kolommen DeviceName en Timestamp |
| `OSVersion` | Tekenreeks | Versie van het besturingssysteem dat op de machine draait |
| `MachineGroup` | Tekenreeks | Machinegroep van de machine. Deze groep wordt gebruikt door op rollen gebaseerde toegangscontrole om de toegang tot de machine te bepalen |

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Zoek naar bedreigingen op verschillende apparaten en e-mails](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
