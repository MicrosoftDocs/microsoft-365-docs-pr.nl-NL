---
title: De tabel AlertEvidence in het geavanceerde schema voor zoeken
description: Meer informatie over de informatie die is gekoppeld aan waarschuwingen in de tabel AlertEvidence van het geavanceerde schema voor zoeken
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, AlertInfo, alert, entities, evidence, file, IP address, device, machine, user, account
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: c01b0aae1eff3d9b4add632aff0f13cb56941a30
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932302"
---
# <a name="alertevidence"></a>AlertEvidence

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

De tabel in het geavanceerde zoekschema bevat informatie over verschillende entiteiten `AlertEvidence` (bestanden, [](advanced-hunting-overview.md) IP-adressen, URL's, gebruikers of apparaten) die zijn gekoppeld aan waarschuwingen van Microsoft Defender voor eindpunt, Microsoft Defender voor Office 365, Microsoft Cloud App Security en Microsoft Defender for Identity. Gebruik deze verwijzing om query's te maken die gegevens uit deze tabel retourneren.

Zie het geavanceerde zoekschema voor meer informatie over andere tabellen in het geavanceerde schema [voor zoeken.](advanced-hunting-schema-tables.md)

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum en tijd waarop de gebeurtenis is vastgelegd |
| `AlertId` | tekenreeks | Unieke id voor de waarschuwing |
| `ServiceSource` | tekenreeks | Product of service dat de waarschuwingsgegevens heeft verstrekt |
| `EntityType` | tekenreeks | Type object, zoals een bestand, een proces, een apparaat of een gebruiker |
| `EvidenceRole` | tekenreeks | Hoe de entiteit is betrokken bij een waarschuwing, om aan te geven of deze van invloed is of alleen is gerelateerd |
| `EvidenceDirection` | tekenreeks | Geeft aan of de entiteit de bron of het doel van een netwerkverbinding is |
| `FileName` | tekenreeks | Naam van het bestand waar de opgenomen actie op is toegepast |
| `FolderPath` | tekenreeks | Map met het bestand waar de opgenomen actie op is toegepast |
| `SHA1` | tekenreeks | SHA-1 van het bestand waar de opgenomen actie op is toegepast |
| `SHA256` | tekenreeks | SHA-256 van het bestand waar de opgenomen actie op is toegepast. Dit veld wordt meestal niet ingevuld. Gebruik de kolom SHA1 indien beschikbaar. |
| `FileSize` | int | Grootte van het bestand in bytes |
| `ThreatFamily` | tekenreeks | Malwarefamilie waarbij het verdachte of schadelijke bestand of proces is geclassificeerd onder |
| `RemoteIP` | tekenreeks | IP-adres dat werd gekoppeld aan |
| `RemoteUrl` | tekenreeks | URL of FQDN (Fully Qualified Domain Name) die werd verbonden met |
| `AccountName` | tekenreeks | Gebruikersnaam van het account |
| `AccountDomain` | tekenreeks | Domein van het account |
| `AccountSid` | tekenreeks | Security Identifier (SID) van het account |
| `AccountObjectId` | tekenreeks | Unieke id voor het account in Azure Active Directory |
| `DeviceId` | tekenreeks | Unieke id voor het apparaat in de service |
| `DeviceName` | tekenreeks | FQDN (Fully Qualified Domain Name) van de computer |
| `LocalIP` | tekenreeks | IP-adres dat is toegewezen aan het lokale apparaat dat tijdens communicatie wordt gebruikt |
| `NetworkMessageId` | tekenreeks | Unieke id voor het e-mailbericht, gegenereerd door Office 365 |
| `EmailSubject` | tekenreeks | Onderwerp van de e-mail |
| `ApplicationId` | tekenreeks | Unieke id voor de toepassing |
| `Application` | tekenreeks | Toepassing die de opgenomen actie heeft uitgevoerd |
| `ProcessCommandLine` | tekenreeks | Opdrachtregel die wordt gebruikt om het nieuwe proces te maken |
| `AdditionalFields` | tekenreeks | Aanvullende informatie over de gebeurtenis in de JSON-matrixindeling |

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Opsporen op apparaten en in e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
