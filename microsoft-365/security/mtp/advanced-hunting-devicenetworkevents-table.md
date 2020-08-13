---
title: DeviceNetworkEvents-tabel in het geavanceerde jacht schema
description: Meer informatie over netwerk verbindings gebeurtenissen waarmee u kunt zoeken in de tabel DeviceNetworkEvents van het schema geavanceerde jacht
keywords: geavanceerde jacht, bedreigings jacht, Cyber Threat jacht, Microsoft Threat Protection, Microsoft 365, MTP, m365, Search, query, Telemetry, schema naslag, kusto, tabel, kolom, gegevenstype, devicenetworkevents, NetworkCommunicationEvents, netwerkverbinding, externe IP, lokaal IP
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
ms.openlocfilehash: 892ffe59f0902938b5d248e11a967b46de9c30b3
ms.sourcegitcommit: 51097b18d94da20aa727ebfbeb6ec84c263b25c3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/12/2020
ms.locfileid: "46649047"
---
# <a name="devicenetworkevents"></a>DeviceNetworkEvents

**Van toepassing op:**
- Microsoft Threat Protection



De `DeviceNetworkEvents` tabel in het [geavanceerde jacht](advanced-hunting-overview.md) -schema bevat informatie over netwerkverbindingen en gerelateerde gebeurtenissen. Gebruik deze verwijzing voor het maken van query's waarmee informatie uit deze tabel wordt geretourneerd.

Zie voor meer informatie over andere tabellen in het geavanceerde jacht-schema [de Naslaggids voor Geavanceerd](advanced-hunting-schema-tables.md)zoeken.

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | tijd | De datum en tijd waarop de gebeurtenis is vastgelegd |
| `DeviceId` | tekenreeks | Unieke id voor de computer in de service |
| `DeviceName` | tekenreeks | FQDN-naam (Fully Qualified Domain Name) van de computer |
| `ActionType` | tekenreeks | Type activiteit waarmee de gebeurtenis wordt geactiveerd |
| `RemoteIP` | tekenreeks | IP-adres waarop verbinding is gemaakt |
| `RemotePort` | int | TCP-poort op het externe apparaat waarmee verbinding is gemaakt |
| `RemoteUrl` | tekenreeks | URL of FQDN (Fully Qualified Domain Name) waarmee verbinding is gemaakt |
| `LocalIP` | tekenreeks | IP-adres dat is toegewezen aan de lokale computer die wordt gebruikt tijdens de communicatie |
| `LocalPort` | int | TCP-poort op de lokale computer die wordt gebruikt tijdens de communicatie |
| `Protocol` | tekenreeks | Gebruikte protocol tijdens de communicatie |
| `LocalIPType` | tekenreeks | Type IP-adres, bijvoorbeeld openbaar, privé, gereserveerd, loopback, Teredo, FourToSixMapping en broadcast |
| `RemoteIPType` | tekenreeks | Type IP-adres, bijvoorbeeld openbaar, privé, gereserveerd, loopback, Teredo, FourToSixMapping en broadcast |
| `InitiatingProcessSHA1` | tekenreeks | SHA-1 van het proces (afbeeldingsbestand) waarmee de gebeurtenis wordt gestart |
| `InitiatingProcessSHA256` | tekenreeks | SHA-256 van het proces (afbeeldingsbestand) waarmee de gebeurtenis wordt gestart. Dit veld wordt meestal niet ingevuld, met behulp van de SHA1-kolom. |
| `InitiatingProcessMD5` | tekenreeks | MD5-hash van het proces (afbeeldingsbestand) waarmee de gebeurtenis wordt gestart |
| `InitiatingProcessFileName` | tekenreeks | Naam van het proces dat de gebeurtenis heeft gestart |
| `InitiatingProcessId` | int | De proces-ID (PID) van het proces dat de gebeurtenis heeft gestart |
| `InitiatingProcessCommandLine` | tekenreeks | Opdrachtregel die wordt gebruikt om het proces te starten waarmee de gebeurtenis wordt gestart |
| `InitiatingProcessCreationTime` | tijd | De datum en tijd waarop het proces dat de gebeurtenis heeft gestart, is gestart |
| `InitiatingProcessFolderPath` | tekenreeks | Map met het proces (afbeeldingsbestand) waarmee de gebeurtenis is gestart |
| `InitiatingProcessParentFileName` | tekenreeks | Naam van het bovenliggende proces dat de proces verantwoordelijke voor de gebeurtenis heeft uitgevoerd |
| `InitiatingProcessParentId` | int | De proces-ID (PID) van het bovenliggende proces dat de proces verantwoordelijke voor de gebeurtenis heeft veroorzaakt. |
| `InitiatingProcessParentCreationTime` | tijd | De datum en tijd waarop de bovenliggende site van het proces dat verantwoordelijk is voor de gebeurtenis, is gestart. |
| `InitiatingProcessAccountDomain` | tekenreeks | Domein van het account dat de verantwoordelijke procedure voor de gebeurtenis heeft uitgevoerd |
| `InitiatingProcessAccountName` | tekenreeks | Gebruikersnaam van het account dat de door u verantwoordelijke procedure voor de gebeurtenis heeft uitgevoerd |
| `InitiatingProcessAccountSid` | tekenreeks | SID (Security Identifier) van het account dat het proces dat verantwoordelijk is voor de gebeurtenis heeft uitgevoerd |
| `InitiatingProcessIntegrityLevel` | tekenreeks | Integriteitsniveau van het proces dat de gebeurtenis heeft gestart. Windows wijst Integriteitsniveaus toe aan processen op basis van bepaalde kenmerken, zoals wanneer ze zijn gestart vanaf een Internet Download. Voor de Integriteitsniveaus zijn machtigingen voor resources van invloed. |
| `InitiatingProcessTokenElevation` | tekenreeks | Token type waarmee de aanwezigheids-of afwezigheids verhoging van de bevoegdheden voor gebruikers toegang wordt aangegeven die is uitgevoerd voor het proces waarmee de gebeurtenis wordt gestart |
| `ReportId` | lang | Gebeurtenis-id op basis van een herhalende teller. Als u unieke gebeurtenissen wilt identificeren, moet deze kolom worden gebruikt in combinatie met de naam van het apparaat en de timestamp-kolommen. |
| `AppGuardContainerId` | tekenreeks | Id van de gevirtualiseerde container die wordt gebruikt door Application Guard om browser activiteiten te isoleren |

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Jacht op apparaten, e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
