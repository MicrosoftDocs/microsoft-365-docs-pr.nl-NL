---
title: DeviceFileEvents-tabel in het geavanceerde jacht schema
description: Meer informatie over bestanden met gebeurtenissen in de tabel DeviceFileEvents van het schema geavanceerde jacht
keywords: geavanceerde jacht, bedreigings jacht, Cyber Threat jacht, Microsoft Threat Protection, Microsoft 365, MTP, m365, Search, query, Telemetry, schema Reference, kusto, Table, Column, datatype, Path, hash, SHA1, sha256, MD5
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
ms.openlocfilehash: b4656c4fd7666ba99ca6125331bdc458d3835edb
ms.sourcegitcommit: 445b249a6f0420b32e49742fd7744006c7090b2b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/18/2020
ms.locfileid: "46798002"
---
# <a name="devicefileevents"></a>DeviceFileEvents

**Van toepassing op:**
- Microsoft Threat Protection

De `DeviceFileEvents` tabel in het [Geavanceerde bejachts](advanced-hunting-overview.md) schema bevat informatie over het maken van bestanden, het wijzigen van en andere bestandssysteem gebeurtenissen. Gebruik deze verwijzing voor het maken van query's waarmee informatie uit deze tabel wordt geretourneerd.

>[!TIP]
> Voor gedetailleerde informatie over de typen gebeurtenissen ( `ActionType` waarden) die door een tabel worden ondersteund, gebruikt u de [ingebouwde schema verwijzing](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) die beschikbaar is in het Beveiligingscentrum.

Zie voor meer informatie over andere tabellen in het geavanceerde jacht-schema [de Naslaggids voor Geavanceerd](advanced-hunting-schema-tables.md)zoeken.

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | tijd | De datum en tijd waarop de gebeurtenis is vastgelegd |
| `DeviceId` | tekenreeks | Unieke id voor de computer in de service |
| `DeviceName` | tekenreeks | FQDN-naam (Fully Qualified Domain Name) van de computer |
| `ActionType` | tekenreeks | Type activiteit waarmee de gebeurtenis wordt geactiveerd. Zie de [verwijzingen naar het portal schema](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) voor Details |
| `FileName` | tekenreeks | De naam van het bestand waarop de opgenomen actie is toegepast |
| `FolderPath` | tekenreeks | Map met het bestand waarop de opgenomen actie is toegepast |
| `SHA1` | tekenreeks | SHA-1 van het bestand waarop de opgenomen actie is toegepast |
| `SHA256` | tekenreeks | SHA-256 van het bestand waarop de opgenomen actie is toegepast. Dit veld wordt meestal niet ingevuld, met behulp van de SHA1-kolom. |
| `MD5` | tekenreeks | MD5-hash van het bestand waarop de opgenomen actie is toegepast |
| `FileOriginUrl` | tekenreeks | URL waarnaar het bestand is gedownload |
| `FileOriginReferrerUrl` | tekenreeks | De URL van de webpagina die is gekoppeld aan het gedownloade bestand |
| `FileOriginIP` | tekenreeks | Het IP-adres waarvandaan het bestand is gedownload |
| `InitiatingProcessAccountDomain` | tekenreeks | Domein van het account dat de verantwoordelijke procedure voor de gebeurtenis heeft uitgevoerd |
| `InitiatingProcessAccountName` | tekenreeks | Gebruikersnaam van het account dat de door u verantwoordelijke procedure voor de gebeurtenis heeft uitgevoerd |
| `InitiatingProcessAccountSid` | tekenreeks | SID (Security Identifier) van het account dat het proces dat verantwoordelijk is voor de gebeurtenis heeft uitgevoerd |
| `InitiatingProcessMD5` | tekenreeks | MD5-hash van het proces (afbeeldingsbestand) waarmee de gebeurtenis wordt gestart |
| `InitiatingProcessSHA1` | tekenreeks | SHA-1 van het proces (afbeeldingsbestand) waarmee de gebeurtenis wordt gestart |
| `InitiatingProcessSHA256` | tekenreeks | SHA-256 van het proces (afbeeldingsbestand) waarmee de gebeurtenis wordt gestart. Dit veld wordt meestal niet ingevuld, met behulp van de SHA1-kolom. |
| `InitiatingProcessFolderPath` | tekenreeks | Map met het proces (afbeeldingsbestand) waarmee de gebeurtenis is gestart |
| `InitiatingProcessFileName` | tekenreeks | Naam van het proces dat de gebeurtenis heeft gestart |
| `InitiatingProcessId` | int | De proces-ID (PID) van het proces dat de gebeurtenis heeft gestart |
| `InitiatingProcessCommandLine` | tekenreeks | Opdrachtregel die wordt gebruikt om het proces te starten waarmee de gebeurtenis wordt gestart |
| `InitiatingProcessCreationTime` | tijd | De datum en tijd waarop het proces dat de gebeurtenis heeft gestart, is gestart |
| `InitiatingProcessIntegrityLevel` | tekenreeks | Integriteitsniveau van het proces dat de gebeurtenis heeft gestart. Windows wijst Integriteitsniveaus toe aan processen op basis van bepaalde kenmerken, zoals wanneer ze zijn gestart vanaf een Internet Download. Voor de Integriteitsniveaus zijn machtigingen voor resources van invloed. |
| `InitiatingProcessTokenElevation` | tekenreeks | Token type waarmee de aanwezigheids-of afwezigheids verhoging van de bevoegdheden voor gebruikers toegang wordt aangegeven die is uitgevoerd voor het proces waarmee de gebeurtenis wordt gestart |
| `InitiatingProcessParentId` | int | De proces-ID (PID) van het bovenliggende proces dat de proces verantwoordelijke voor de gebeurtenis heeft veroorzaakt. |
| `InitiatingProcessParentFileName` | tekenreeks | Naam van het bovenliggende proces dat de proces verantwoordelijke voor de gebeurtenis heeft uitgevoerd |
| `InitiatingProcessParentCreationTime` | tijd | De datum en tijd waarop de bovenliggende site van het proces dat verantwoordelijk is voor de gebeurtenis, is gestart. |
| `RequestProtocol` | tekenreeks | Netwerkprotocol, indien van toepassing, wordt gebruikt om de activiteit te starten: onbekend, lokaal, SMB of NFS |
| `ShareName` | tekenreeks | Naam van de gedeelde map die het bestand bevat |
| `RequestSourceIP` | tekenreeks | IPv4-of IPv6-adres van het externe apparaat waarmee de activiteit is gestart |
| `RequestSourcePort` | tekenreeks | Bronpoort op het externe apparaat waarmee de activiteit is gestart |
| `RequestAccountName` | tekenreeks | Gebruikersnaam van account die wordt gebruikt om de activiteit extern te starten |
| `RequestAccountDomain` | tekenreeks | Domein van het account dat wordt gebruikt voor het extern starten van de activiteit |
| `RequestAccountSid` | tekenreeks | SID (Security Identifier) van het account dat wordt gebruikt voor het extern starten van de activiteit |
| `ReportId` | lang | Gebeurtenis-id op basis van een herhalende teller. Als u unieke gebeurtenissen wilt identificeren, moet deze kolom worden gebruikt in combinatie met de naam van het apparaat en de timestamp-kolommen. |
| `AppGuardContainerId` | tekenreeks | Id van de gevirtualiseerde container die wordt gebruikt door Application Guard om browser activiteiten te isoleren |
| `SensitivityLabel` | tekenreeks | Label toegepast op een e-mailbericht, bestand of andere inhoud om deze te classificeren ter informatiebescherming |
| `SensitivitySubLabel` | tekenreeks | Sublabel voor een e-mailbericht, bestand of andere inhoud om dit te classificeren ter informatiebescherming; sublabels voor de gevoeligheid zijn gegroepeerd onder tekstlabels, maar worden afzonderlijk verwerkt |
| `IsAzureInfoProtectionApplied` | Boolean | Geeft aan of het bestand is versleuteld door Azure Information Protection |

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Opsporen op apparaten en in e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)