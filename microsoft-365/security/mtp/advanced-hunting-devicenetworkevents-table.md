---
title: DeviceNetworkEvents-tabel in het geavanceerde jachtschema
description: Meer informatie over netwerkverbindingsgebeurtenissen die u opvragen in de tabel DeviceNetworkEvents van het geavanceerde jachtschema
keywords: geavanceerde jacht, bedreiging jacht, cyber bedreiging jacht, Microsoft threat protection, Microsoft 365, mtp, m365, zoeken, query, telemetrie, schema referentie, kusto, tabel, kolom, datatype, devicenetworkevents, NetworkCommunicationEvents, netwerkverbinding, remote ip, lokale ip
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
ms.openlocfilehash: 3be6523372edcda520e05545c87385c0e1a42044
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/09/2020
ms.locfileid: "44617116"
---
# <a name="devicenetworkevents"></a>DeviceNetworkEvents

**Van toepassing op:**
- Microsoft Threat Protection



De `DeviceNetworkEvents` tabel in het geavanceerde [jachtschema](advanced-hunting-overview.md) bevat informatie over netwerkverbindingen en gerelateerde gebeurtenissen. Gebruik deze verwijzing om query's te construeren die informatie uit deze tabel retourneren.

Zie [de geavanceerde jachtreferentie](advanced-hunting-schema-tables.md)voor informatie over andere tabellen in het geavanceerde jachtschema.

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | Datetime | Datum en tijdstip waarop de gebeurtenis is geregistreerd |
| `DeviceId` | Tekenreeks | Unieke id voor de machine in de service |
| `DeviceName` | Tekenreeks | Volledig gekwalificeerde domeinnaam (FQDN) van de machine |
| `ActionType` | Tekenreeks | Type activiteit dat de gebeurtenis heeft geactiveerd |
| `RemoteIP` | Tekenreeks | IP-adres waarmee werd verbonden |
| `RemotePort` | Int | TCP-poort op het externe apparaat waarmee |
| `RemoteUrl` | Tekenreeks | URL of volledig gekwalificeerde domeinnaam (FQDN) die werd verbonden met |
| `LocalIP` | Tekenreeks | IP-adres toegewezen aan de lokale machine die wordt gebruikt tijdens de communicatie |
| `LocalPort` | Int | TCP-poort op de lokale machine die wordt gebruikt tijdens de communicatie |
| `Protocol` | Tekenreeks | Protocol dat tijdens de communicatie wordt gebruikt |
| `LocalIPType` | Tekenreeks | Type IP-adres, bijvoorbeeld Openbaar, Privé, Gereserveerd, Loopback, Teredo, FourToSixMapping en Broadcast |
| `RemoteIPType` | Tekenreeks | Type IP-adres, bijvoorbeeld Openbaar, Privé, Gereserveerd, Loopback, Teredo, FourToSixMapping en Broadcast |
| `InitiatingProcessSHA1` | Tekenreeks | SHA-1 van het proces (afbeeldingsbestand) dat de gebeurtenis heeft geïnitieerd |
| `InitiatingProcessSHA256` | Tekenreeks | SHA-256 van het proces (afbeeldingsbestand) dat de gebeurtenis heeft geïnitieerd. Dit veld wordt meestal niet ingevuld - gebruik de SHA1-kolom indien beschikbaar. |
| `InitiatingProcessMD5` | Tekenreeks | MD5-hash van het proces (afbeeldingsbestand) dat de gebeurtenis heeft geïnitieerd |
| `InitiatingProcessFileName` | Tekenreeks | Naam van het proces dat de gebeurtenis heeft gestart |
| `InitiatingProcessId` | Int | Proces-ID (PID) van het proces dat de gebeurtenis heeft geïnitieerd |
| `InitiatingProcessCommandLine` | Tekenreeks | Opdrachtregel die wordt gebruikt om het proces uit te voeren dat de gebeurtenis heeft gestart |
| `InitiatingProcessCreationTime` | Datetime | Datum en tijd waarop het proces waarmee de gebeurtenis is gestart, is gestart |
| `InitiatingProcessFolderPath` | Tekenreeks | Map met het proces (afbeeldingsbestand) dat de gebeurtenis heeft geïnitieerd |
| `InitiatingProcessParentFileName` | Tekenreeks | Naam van het bovenliggende proces dat het proces heeft voortgebracht dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessParentId` | Int | Proces-ID (PID) van het bovenliggende proces dat het proces heeft voortgebracht dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessParentCreationTime` | Datetime | Datum en tijd waarop de ouder van het proces dat verantwoordelijk is voor het evenement is gestart |
| `InitiatingProcessAccountDomain` | Tekenreeks | Domein van het account dat het proces heeft uitgevoerd dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessAccountName` | Tekenreeks | Gebruikersnaam van het account waarop het proces is uitgevoerd dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessAccountSid` | Tekenreeks | Security Identifier (SID) van het account dat het proces heeft uitgevoerd dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessIntegrityLevel` | Tekenreeks | Integriteitsniveau van het proces dat de gebeurtenis heeft geïnitieerd. Windows wijst integriteitsniveaus toe aan processen op basis van bepaalde kenmerken, zoals wanneer ze zijn gestart vanaf een internetdownload. Deze integriteitsniveaus beïnvloeden machtigingen voor resources |
| `InitiatingProcessTokenElevation` | Tekenreeks | Tokentype dat de aanwezigheid of afwezigheid van UAC-bevoegdheid (User Access Control) aangeeft die wordt toegepast op het proces dat de gebeurtenis heeft gestart |
| `ReportId` | Lange | Gebeurtenis-id op basis van een herhalende teller. Om unieke gebeurtenissen te identificeren, moet deze kolom worden gebruikt in combinatie met de kolommen DeviceName en Timestamp |
| `AppGuardContainerId` | Tekenreeks | Id voor de gevirtualiseerde container die door Application Guard wordt gebruikt om browseractiviteit te isoleren |

## <a name="related-topics"></a>Verwante onderwerpen
- [Proactief op zoek naar bedreigingen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Zoek naar bedreigingen op verschillende apparaten en e-mails](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
