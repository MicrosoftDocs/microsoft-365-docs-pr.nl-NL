---
title: AlertEvidence-tabel in het geavanceerde jacht schema
description: Meer informatie over bestands-, netwerkadres-, gebruikers-of apparaatgegevens die zijn gekoppeld aan gegenereerde waarschuwingen in de tabel AlertEvidence van het schema geavanceerde jacht
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 8fc713db33b0e40adcd0975d26c10daece636ab1
ms.sourcegitcommit: 51097b18d94da20aa727ebfbeb6ec84c263b25c3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/12/2020
ms.locfileid: "46649509"
---
# <a name="alertevidence"></a>AlertEvidence

**Van toepassing op:**
- Microsoft Threat Protection

De `AlertEvidence` tabel in het [Geavanceerde opjacht](advanced-hunting-overview.md) -schema bevat informatie over diverse entiteiten, zoals bestanden, IP-adressen, url's, gebruikers of apparaten, gekoppeld aan waarschuwingen uit Microsoft Defender atp, Office 365 ATP, Microsoft Cloud app Security en Azure ATP. Gebruik deze verwijzing voor het maken van query's waarmee informatie uit deze tabel wordt geretourneerd.

Zie voor meer informatie over andere tabellen in het geavanceerde jacht-schema [de Naslaggids voor Geavanceerd](advanced-hunting-schema-tables.md)zoeken.

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | tijd | De datum en tijd waarop de gebeurtenis is vastgelegd |
| `AlertId` | tekenreeks | Unieke id voor de waarschuwing |
| `EntityType` | tekenreeks | Type object, zoals een bestand, een proces, een apparaat of een gebruiker |
| `EvidenceRole` | tekenreeks | Hoe de entiteit deel uitmaakt van een melding, geeft aan of het niet wordt beïnvloed |
| `SHA1` | tekenreeks | SHA-1 van het bestand waarop de opgenomen actie is toegepast |
| `SHA256` | tekenreeks | SHA-256 van het bestand waarop de opgenomen actie is toegepast. Dit veld wordt meestal niet ingevuld, met behulp van de SHA1-kolom. |
| `RemoteIP` | tekenreeks | IP-adres waarop verbinding is gemaakt |
| `RemoteUrl` | tekenreeks | URL of FQDN (Fully Qualified Domain Name) waarmee verbinding is gemaakt |
| `AccountName` | tekenreeks | Gebruikersnaam van het account |
| `AccountDomain` | tekenreeks | Domein van het account |
| `AccountSid` | tekenreeks | SID (Security Identifier) van het account |
| `AccountObjectId` | tekenreeks | Unieke id voor het account in azure AD |
| `DeviceId` | tekenreeks | Unieke id voor de computer in de service |
| `ThreatFamily` | tekenreeks | De familie van de malware waarmee het verdachte of schadelijke bestand of proces is geclassificeerd. |
| `EvidenceDirection` | tekenreeks | Geeft aan of de entiteit de bron is of de bestemming van een netwerkverbinding |
| `AdditionalFields` | tekenreeks | Aanvullende informatie over de gebeurtenis in de JSON-matrix indeling |

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Jacht op apparaten, e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
