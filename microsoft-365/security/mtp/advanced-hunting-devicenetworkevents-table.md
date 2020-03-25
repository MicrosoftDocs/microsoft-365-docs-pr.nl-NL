---
title: Tabel DeviceNetworkEvents in het geavanceerde jachtschema
description: Meer informatie over netwerkverbindingsgebeurtenissen die u opvragen in de tabel DeviceNetworkEvents van het geavanceerde jachtschema
keywords: geavanceerde jacht, dreigingsjacht, cyberdreigingsjacht, bescherming tegen microsoft-dreigingen, microsoft 365, mtp, m365, zoekopdracht, query, telemetrie, schemareferentie, kusto, tabel, kolom, gegevenstype, devicenetworkevents, NetworkCommunicationEvents, netwerk verbinding, remote ip, lokale ip
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
ms.openlocfilehash: d5e3327f4b4e066b3e4c14f646ad8db78ff3804a
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929038"
---
# <a name="devicenetworkevents"></a>DeviceNetworkEvents DeviceNetworkEvents

**Van toepassing op:**
- Microsoft-bedreigingsbeveiliging



De `DeviceNetworkEvents` tabel in het [geavanceerde jachtschema](advanced-hunting-overview.md) bevat informatie over netwerkverbindingen en gerelateerde gebeurtenissen. Gebruik deze verwijzing om query's te construeren die informatie uit deze tabel retourneren.

Voor informatie over andere tabellen in de geavanceerde jacht schema, [zie de geavanceerde jacht referentie](advanced-hunting-schema-tables.md).

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | Datetime | Datum en tijdstip waarop de gebeurtenis is geregistreerd |
| `DeviceId` | Tekenreeks | Unieke id voor de machine in de service |
| `DeviceName` | Tekenreeks | Volledig gekwalificeerde domeinnaam (FQDN) van de machine |
| `ActionType` | Tekenreeks | Type activiteit dat de gebeurtenis heeft geactiveerd |
| `RemoteIP` | Tekenreeks | IP-adres dat werd verbonden met |
| `RemotePort` | Int | TCP-poort op het externe apparaat waarmee werd verbonden |
| `RemoteUrl` | Tekenreeks | URL of volledig gekwalificeerde domeinnaam (FQDN) die werd verbonden met |
| `LocalIP` | Tekenreeks | IP-adres toegewezen aan de lokale machine die tijdens de communicatie wordt gebruikt |
| `LocalPort` | Int | TCP-poort op de lokale machine die tijdens de communicatie wordt gebruikt |
| `Protocol` | Tekenreeks | Protocol dat tijdens de communicatie wordt gebruikt |
| `LocalIPType` | Tekenreeks | Type IP-adres, bijvoorbeeld Openbaar, Privé, Gereserveerd, Loopback, Teredo, FourToSixMapping en Broadcast |
| `RemoteIPType` | Tekenreeks | Type IP-adres, bijvoorbeeld Openbaar, Privé, Gereserveerd, Loopback, Teredo, FourToSixMapping en Broadcast |
| `InitiatingProcessSHA1` | Tekenreeks | SHA-1 van het proces (afbeeldingsbestand) dat de gebeurtenis heeft geïnitieerd |
| `InitiatingProcessMD5` | Tekenreeks | MD5-hash van het proces (afbeeldingsbestand) waarmee de gebeurtenis is gestart |
| `InitiatingProcessFileName` | Tekenreeks | Naam van het proces dat de gebeurtenis heeft geïnitieerd |
| `InitiatingProcessId` | Int | Proces-ID (PID) van het proces dat de gebeurtenis heeft geïnitieerd |
| `InitiatingProcessCommandLine` | Tekenreeks | Opdrachtregel die wordt gebruikt om het proces uit te voeren waarmee de gebeurtenis is gestart |
| `InitiatingProcessCreationTime` | Datetime | Datum en tijd waarop het proces dat de gebeurtenis heeft gestart, is gestart |
| `InitiatingProcessFolderPath` | Tekenreeks | Map met het proces (afbeeldingsbestand) waarmee de gebeurtenis is gestart |
| `InitiatingProcessParentFileName` | Tekenreeks | Naam van het bovenliggende proces dat het proces heeft voortgebracht dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessParentId` | Int | Process ID (PID) van het bovenliggende proces dat het proces heeft voortgebracht dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessParentCreationTime` | Datetime | Datum en tijd waarop de ouder van het proces dat verantwoordelijk is voor de gebeurtenis is gestart |
| `InitiatingProcessAccountDomain` | Tekenreeks | Domein van het account dat het proces heeft uitgevoerd dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessAccountName` | Tekenreeks | Gebruikersnaam van het account dat het proces heeft uitgevoerd dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessAccountSid` | Tekenreeks | Beveiligings-id (SID) van het account dat het proces heeft uitgevoerd dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessIntegrityLevel` | Tekenreeks | Integriteitsniveau van het proces dat de gebeurtenis heeft geïnitieerd. Windows kent integriteitsniveaus toe aan processen op basis van bepaalde kenmerken, bijvoorbeeld als ze zijn gestart vanaf een internetdownload. Deze integriteitsniveaus beïnvloeden machtigingen voor resources |
| `InitiatingProcessTokenElevation` | Tekenreeks | Tokentype dat de aanwezigheid of afwezigheid van UAC-bevoegdheden (User Access Control) aangeeft die zijn toegepast op het proces waarmee de gebeurtenis is gestart |
| `ReportId` | Lange | Gebeurtenis-id op basis van een herhalingsteller. Om unieke gebeurtenissen te identificeren, moet deze kolom worden gebruikt in combinatie met de kolommen DeviceName en Timestamp |
| `AppGuardContainerId` | Tekenreeks | Id voor de gevirtualiseerde container die door Application Guard wordt gebruikt om browseractiviteit te isoleren |

## <a name="related-topics"></a>Verwante onderwerpen
- [Proactief op zoek naar bedreigingen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Zoek naar bedreigingen op verschillende apparaten en e-mails](advanced-hunting-query-emails-devices.md)
- [Het schema begrijpen](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
