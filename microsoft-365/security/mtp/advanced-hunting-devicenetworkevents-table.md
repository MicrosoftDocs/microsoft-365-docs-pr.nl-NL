---
title: DeviceNetworkEvents tabel in de geavanceerde jacht schema
description: Meer informatie over netwerkverbindingsgebeurtenissen die u opvragen vanuit de tabel DeviceNetworkEvents van het geavanceerde jachtschema
keywords: geavanceerde jacht, bedreigingjacht, cyberdreigingsjacht, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetrie, schemareferentie, kusto, tabel, kolom, gegevenstype, devicenetworkevents, NetworkCommunicationEvents, netwerk verbinding, ip op afstand, lokaal ip
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
ms.openlocfilehash: 2e7999fef43adb372947d9edf92b84ac67f347fe
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/24/2020
ms.locfileid: "42805722"
---
# <a name="devicenetworkevents"></a>DeviceNetworkEvents

**Van toepassing op:**
- Microsoft-bedreigingsbeveiliging



De `DeviceNetworkEvents` tabel in het [geavanceerde jachtschema](advanced-hunting-overview.md) bevat informatie over netwerkverbindingen en gerelateerde gebeurtenissen. Gebruik deze verwijzing om query's te maken die informatie uit deze tabel retourneren.

Zie [de geavanceerde jachtreferentie](advanced-hunting-schema-tables.md)voor informatie over andere tabellen in het geavanceerde jachtschema.

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | Datetime | Datum en tijd waarop de gebeurtenis is geregistreerd |
| `DeviceId` | Tekenreeks | Unieke id voor de machine in de service |
| `DeviceName` | Tekenreeks | Volledig gekwalificeerde domeinnaam (FQDN) van de machine |
| `ActionType` | Tekenreeks | Type activiteit dat de gebeurtenis heeft geactiveerd |
| `RemoteIP` | Tekenreeks | IP-adres dat werd verbonden met |
| `RemotePort` | Int | TCP-poort op het externe apparaat waarmee |
| `RemoteUrl` | Tekenreeks | URL of volledig gekwalificeerde domeinnaam (FQDN) die werd verbonden met |
| `LocalIP` | Tekenreeks | IP-adres toegewezen aan de lokale machine die tijdens de communicatie wordt gebruikt |
| `LocalPort` | Int | TCP-poort op de lokale machine die wordt gebruikt tijdens de communicatie |
| `Protocol` | Tekenreeks | IP-protocol gebruikt, of TCP of UDP |
| `LocalIPType` | Tekenreeks | Type IP-adres, bijvoorbeeld Openbaar, Privé, Gereserveerd, Loopback, Teredo, FourToSixMapping en Broadcast |
| `RemoteIPType` | Tekenreeks | Type IP-adres, bijvoorbeeld Openbaar, Privé, Gereserveerd, Loopback, Teredo, FourToSixMapping en Broadcast |
| `InitiatingProcessSHA1` | Tekenreeks | SHA-1 van het proces (afbeeldingsbestand) waarmee de gebeurtenis is gestart |
| `InitiatingProcessMD5` | Tekenreeks | MD5-hash van het proces (afbeeldingsbestand) waarmee de gebeurtenis is gestart |
| `InitiatingProcessFileName` | Tekenreeks | Naam van het proces waarmee de gebeurtenis is gestart |
| `InitiatingProcessId` | Int | Process ID (PID) van het proces dat de gebeurtenis heeft geïnitieerd |
| `InitiatingProcessCommandLine` | Tekenreeks | Opdrachtregel die wordt gebruikt om het proces uit te voeren waarmee de gebeurtenis is gestart |
| `InitiatingProcessCreationTime` | Datetime | Datum en tijd waarop het proces waarmee de gebeurtenis is gestart, is gestart |
| `InitiatingProcessFolderPath` | Tekenreeks | Map met het proces (afbeeldingsbestand) waarmee de gebeurtenis is gestart |
| `InitiatingProcessParentFileName` | Tekenreeks | Naam van het bovenliggende proces dat het proces dat verantwoordelijk is voor de gebeurtenis heeft voortgebracht |
| `InitiatingProcessParentId` | Int | Process ID (PID) van het bovenliggende proces dat het proces dat verantwoordelijk is voor de gebeurtenis heeft voortgebracht |
| `InitiatingProcessParentCreationTime` | Datetime | Datum en tijd waarop de ouder van het proces dat verantwoordelijk is voor de gebeurtenis is gestart |
| `InitiatingProcessAccountDomain` | Tekenreeks | Domein van het account dat het proces heeft uitgevoerd dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessAccountName` | Tekenreeks | Gebruikersnaam van het account dat het proces heeft uitgevoerd dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessAccountSid` | Tekenreeks | Beveiligings-id (SID) van het account dat het proces dat verantwoordelijk was voor de gebeurtenis leidde |
| `InitiatingProcessIntegrityLevel` | Tekenreeks | Integriteitsniveau van het proces dat de gebeurtenis heeft geïnitieerd. Windows kent integriteitsniveaus toe aan processen op basis van bepaalde kenmerken, zoals of ze zijn gestart via een internetdownload. Deze integriteitsniveaus beïnvloeden machtigingen voor resources |
| `InitiatingProcessTokenElevation` | Tekenreeks | Tokentype dat de aanwezigheid of afwezigheid aangeeft van uac-bevoegdheden (User Access Control) die zijn toegepast op het proces dat de gebeurtenis heeft gestart |
| `ReportId` | Lange | Gebeurtenis-id op basis van een herhalende teller. Om unieke gebeurtenissen te identificeren, moet deze kolom worden gebruikt in combinatie met de kolommen DeviceName en Timestamp |
| `AppGuardContainerId` | Tekenreeks | Id voor de gevirtualiseerde container die door Application Guard wordt gebruikt om browseractiviteit te isoleren |

## <a name="related-topics"></a>Verwante onderwerpen
- [Proactief jagen op bedreigingen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Op zoek naar bedreigingen op verschillende apparaten en e-mails](advanced-hunting-query-emails-devices.md)
- [Het schema begrijpen](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
