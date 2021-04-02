---
title: Tabel AlertEvidence in het geavanceerde schema voor de jacht
description: Meer informatie over informatie die is gekoppeld aan waarschuwingen in de tabel AlertEvidence van het geavanceerde schema voor de jacht
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, AlertInfo, alert, entities, evidence, file, IP address, device, machine, user, account
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 7b1f581e1cfc8345df6e7b8053621cf46110c355
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499884"
---
# <a name="alertevidence"></a>AlertEvidence

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

De tabel in het geavanceerde schema bevat informatie over verschillende entiteiten, zoals `AlertEvidence` bestanden, IP-adressen, URL's, gebruikers of apparaten, die zijn gekoppeld aan waarschuwingen van Microsoft Defender voor Eindpunt, Microsoft Defender voor Office 365, Microsoft Cloud App Security en Microsoft [](advanced-hunting-overview.md) Defender voor identiteit. Gebruik deze verwijzing om query's te maken die gegevens uit deze tabel retourneren.

Zie de geavanceerde zoekverwijzing voor meer informatie over andere tabellen in het geavanceerde schema voor [de jacht.](advanced-hunting-schema-tables.md)

| Kolomnaam | Gegevenstype | Omschrijving |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum en tijd waarop de gebeurtenis is opgenomen |
| `AlertId` | tekenreeks | Unieke id voor de waarschuwing |
| `ServiceSource` | tekenreeks | Product of service met de waarschuwingsgegevens |
| `EntityType` | tekenreeks | Type object, zoals een bestand, een proces, een apparaat of een gebruiker |
| `EvidenceRole` | tekenreeks | Hoe de entiteit betrokken is bij een waarschuwing, waarmee wordt aangegeven of deze gevolgen heeft of alleen gerelateerd is |
| `EvidenceDirection` | tekenreeks | Geeft aan of de entiteit de bron of de bestemming van een netwerkverbinding is |
| `FileName` | tekenreeks | Naam van het bestand waar de opgenomen actie op is toegepast |
| `FolderPath` | tekenreeks | Map met het bestand waarin de opgenomen actie is toegepast |
| `SHA1` | tekenreeks | SHA-1 van het bestand waar de opgenomen actie op is toegepast |
| `SHA256` | tekenreeks | SHA-256 van het bestand waar de opgenomen actie op is toegepast. Dit veld wordt meestal niet ingevuld. Gebruik de kolom SHA1 wanneer deze beschikbaar is. |
| `FileSize` | int | Grootte van het bestand in bytes |
| `ThreatFamily` | tekenreeks | Malwarefamilie die het verdachte of schadelijke bestand of proces heeft geclassificeerd onder |
| `RemoteIP` | tekenreeks | IP-adres dat werd verbonden met |
| `RemoteUrl` | tekenreeks | URL of volledig gekwalificeerde domeinnaam (FQDN) die werd verbonden met |
| `AccountName` | tekenreeks | Gebruikersnaam van het account |
| `AccountDomain` | tekenreeks | Domein van het account |
| `AccountSid` | tekenreeks | Beveiligings-id (SID) van het account |
| `AccountObjectId` | tekenreeks | Unieke id voor het account in Azure Active Directory |
| `AccountUpn` | tekenreeks | Gebruikersnaam (UPN) van het account |
| `DeviceId` | tekenreeks | Unieke id voor het apparaat in de service |
| `DeviceName` | tekenreeks | Volledig gekwalificeerde domeinnaam (FQDN) van de computer |
| `LocalIP` | tekenreeks | IP-adres dat is toegewezen aan het lokale apparaat dat tijdens communicatie wordt gebruikt |
| `NetworkMessageId` | tekenreeks | Unieke id voor het e-mailbericht, gegenereerd door Office 365 |
| `EmailSubject` | tekenreeks | Onderwerp van het e-mailbericht |
| `ApplicationId` | tekenreeks | Unieke id voor de toepassing |
| `Application` | tekenreeks | Toepassing die de opgenomen actie heeft uitgevoerd |
| `ProcessCommandLine` | tekenreeks | Opdrachtregel die wordt gebruikt om het nieuwe proces te maken |
| `AdditionalFields` | tekenreeks | Aanvullende informatie over de gebeurtenis in de JSON-matrixindeling |
| `RegistryKey` |tekenreeks | Registersleutel waar de opgenomen actie op is toegepast |
| `RegistryValueName` |tekenreeks | Naam van de registerwaarde waar de opgenomen actie op is toegepast |
| `RegistryValueData` |tekenreeks | Gegevens van de registerwaarde waar de opgenomen actie op is toegepast |

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Opsporen op apparaten en in e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
