---
title: AlertEvidence-tabel in het geavanceerde jacht schema
description: Meer informatie over informatie die is gekoppeld aan waarschuwingen in de tabel AlertEvidence van het schema geavanceerde jacht
keywords: geavanceerde jacht, bedreigings jacht, Cyber Threat jacht, Microsoft Threat Protection, Microsoft 365, MTP, m365, Search, query, Telemetry, schema naslag, kusto, tabel, kolom, gegevenstype, beschrijving, AlertInfo, waarschuwing, entiteit, bewijs, bestand, IP-adres, apparaat, computer, gebruiker
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
ms.openlocfilehash: 7f6a4f7592e6a8fde0b7ae6269f07ce7f76a5730
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430161"
---
# <a name="alertevidence"></a>AlertEvidence

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft Threat Protection

De `AlertEvidence` tabel in het [Geavanceerde opjacht](advanced-hunting-overview.md) -schema bevat informatie over diverse entiteiten, zoals bestanden, IP-adressen, url's, gebruikers of apparaten, gekoppeld aan waarschuwingen uit Microsoft Defender atp, Office 365 ATP, Microsoft Cloud app Security en Azure ATP. Gebruik deze verwijzing voor het maken van query's waarmee informatie uit deze tabel wordt geretourneerd.

Zie voor meer informatie over andere tabellen in het geavanceerde jacht-schema [de Naslaggids voor Geavanceerd](advanced-hunting-schema-tables.md)zoeken.

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | tijd | De datum en tijd waarop de gebeurtenis is vastgelegd |
| `AlertId` | tekenreeks | Unieke id voor de waarschuwing |
| `ServiceSource` | tekenreeks | Het product of de service die de waarschuwingsinformatie heeft verstrekt |
| `EntityType` | tekenreeks | Type object, zoals een bestand, een proces, een apparaat of een gebruiker |
| `EvidenceRole` | tekenreeks | Hoe de entiteit deel uitmaakt van een melding, geeft aan of het niet wordt beïnvloed |
| `EvidenceDirection` | tekenreeks | Geeft aan of de entiteit de bron is of de bestemming van een netwerkverbinding |
| `FileName` | tekenreeks | De naam van het bestand waarop de opgenomen actie is toegepast |
| `FolderPath` | tekenreeks | Map met het bestand waarop de opgenomen actie is toegepast |
| `SHA1` | tekenreeks | SHA-1 van het bestand waarop de opgenomen actie is toegepast |
| `SHA256` | tekenreeks | SHA-256 van het bestand waarop de opgenomen actie is toegepast. Dit veld wordt meestal niet ingevuld, met behulp van de SHA1-kolom. |
| `FileSize` | int | Bestandsgrootte in bytes |
| `ThreatFamily` | tekenreeks | De familie van de malware waarmee het verdachte of schadelijke bestand of proces is geclassificeerd. |
| `RemoteIP` | tekenreeks | IP-adres waarop verbinding is gemaakt |
| `RemoteUrl` | tekenreeks | URL of FQDN (Fully Qualified Domain Name) waarmee verbinding is gemaakt |
| `AccountName` | tekenreeks | Gebruikersnaam van het account |
| `AccountDomain` | tekenreeks | Domein van het account |
| `AccountSid` | tekenreeks | SID (Security Identifier) van het account |
| `AccountObjectId` | tekenreeks | Unieke id voor het account in azure Active Directory |
| `DeviceId` | tekenreeks | Unieke id van het apparaat in de service |
| `DeviceName` | tekenreeks | FQDN-naam (Fully Qualified Domain Name) van de computer |
| `LocalIP` | tekenreeks | Het IP-adres dat is toegewezen aan het lokale apparaat dat wordt gebruikt tijdens de communicatie |
| `NetworkMessageId` | tekenreeks | Unieke id voor de e-mail, gegenereerd door Office 365 |
| `EmailSubject` | tekenreeks | Onderwerp van de e-mail |
| `ApplicationId` | tekenreeks | Unieke id voor de toepassing |
| `Application` | tekenreeks | De toepassing die de opgenomen actie heeft uitgevoerd |
| `ProcessCommandLine` | tekenreeks | Opdrachtregel voor het maken van het nieuwe proces |
| `AdditionalFields` | tekenreeks | Aanvullende informatie over de gebeurtenis in de JSON-matrix indeling |

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Opsporen op apparaten en in e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
