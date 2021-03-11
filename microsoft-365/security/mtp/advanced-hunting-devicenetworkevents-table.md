---
title: DeviceNetworkEvents-tabel in het geavanceerde schema voor zoeken
description: Meer informatie over netwerkverbindingsgebeurtenissen die u kunt opvragen in de tabel DeviceNetworkEvents van het geavanceerde schema voor zoeken
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, devicenetworkevents, NetworkCommunicationEvents, network connection, remote ip, local ip
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
ms.openlocfilehash: 65b9b7608b39f802cc82c62b87d7104ee4ff4304
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/10/2021
ms.locfileid: "50712424"
---
# <a name="devicenetworkevents"></a>DeviceNetworkEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender



De `DeviceNetworkEvents` tabel in het geavanceerde [zoekschema](advanced-hunting-overview.md) bevat informatie over netwerkverbindingen en gerelateerde gebeurtenissen. Gebruik deze verwijzing om query's te maken die gegevens uit deze tabel retourneren.

>[!TIP]
> Voor gedetailleerde informatie over de gebeurtenistypen (waarden) die door een tabel worden ondersteund, gebruikt u de `ActionType` ingebouwde schemaverwijzing in het beveiligingscentrum.

Zie het geavanceerde zoekschema voor informatie over andere tabellen in het geavanceerde schema voor [het zoeken.](advanced-hunting-schema-tables.md)

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum en tijd waarop de gebeurtenis is vastgelegd |
| `DeviceId` | tekenreeks | Unieke id voor de computer in de service |
| `DeviceName` | tekenreeks | FQDN (Fully Qualified Domain Name) van de computer |
| `ActionType` | tekenreeks | Het type activiteit dat de gebeurtenis heeft geactiveerd. Zie de [schemaverwijzing in de portal](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) voor meer informatie |
| `RemoteIP` | tekenreeks | IP-adres dat werd gekoppeld aan |
| `RemotePort` | int | TCP-poort op het externe apparaat dat werd verbonden met |
| `RemoteUrl` | tekenreeks | URL of FQDN (Fully Qualified Domain Name) die werd verbonden met |
| `LocalIP` | tekenreeks | IP-adres dat is toegewezen aan de lokale computer die tijdens communicatie wordt gebruikt |
| `LocalPort` | int | TCP-poort op de lokale computer die tijdens communicatie wordt gebruikt |
| `Protocol` | tekenreeks | Protocol dat is gebruikt tijdens de communicatie |
| `LocalIPType` | tekenreeks | Type IP-adres, bijvoorbeeld Openbaar, Privé, Gereserveerd, Loopback, Teredo, FourToSixMapping en Broadcast |
| `RemoteIPType` | tekenreeks | Type IP-adres, bijvoorbeeld Openbaar, Privé, Gereserveerd, Loopback, Teredo, FourToSixMapping en Broadcast |
| `InitiatingProcessSHA1` | tekenreeks | SHA-1 van het proces (afbeeldingsbestand) dat de gebeurtenis heeft gestart |
| `InitiatingProcessSHA256` | tekenreeks | SHA-256 van het proces (afbeeldingsbestand) dat de gebeurtenis heeft gestart. Dit veld wordt meestal niet ingevuld. Gebruik indien beschikbaar de kolom SHA1. |
| `InitiatingProcessMD5` | tekenreeks | MD5-hash van het proces (afbeeldingsbestand) dat de gebeurtenis heeft gestart |
| `InitiatingProcessFileName` | tekenreeks | Naam van het proces dat de gebeurtenis heeft gestart |
| `InitiatingProcessFileSize` | lang | Grootte van het bestand met het proces dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessId` | int | Proces-id (PID) van het proces dat de gebeurtenis heeft gestart |
| `InitiatingProcessCommandLine` | tekenreeks | Opdrachtregel die wordt gebruikt voor het uitvoeren van het proces waarmee de gebeurtenis is gestart |
| `InitiatingProcessCreationTime` | datetime | Datum en tijd waarop het proces voor het starten van de gebeurtenis is gestart |
| `InitiatingProcessFolderPath` | tekenreeks | Map met het proces (afbeeldingsbestand) dat de gebeurtenis heeft gestart |
| `InitiatingProcessParentFileName` | tekenreeks | Naam van het bovenliggende proces dat het proces heeft geleid dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessParentId` | int | Proces-id (PID) van het bovenliggende proces dat het proces heeft geleid dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessParentCreationTime` | datetime | Datum en tijd waarop de bovenliggende groep die verantwoordelijk is voor de gebeurtenis is gestart |
| `InitiatingProcessAccountDomain` | tekenreeks | Het domein van het account dat het proces heeft verantwoordelijk voor de gebeurtenis |
| `InitiatingProcessAccountName` | tekenreeks | Gebruikersnaam van het account dat het proces heeft verantwoordelijk voor de gebeurtenis |
| `InitiatingProcessAccountSid` | tekenreeks | Security Identifier (SID) van het account dat het proces heeft verantwoordelijk voor de gebeurtenis |
| `InitiatingProcessAccountUpn` | tekenreeks | UPN (User Principal Name) van het account dat het proces heeft verantwoordelijk voor de gebeurtenis |
| `InitiatingProcessIntegrityLevel` | tekenreeks | Het integriteitsniveau van het proces dat de gebeurtenis heeft gestart. Windows wijst integriteitsniveaus toe aan processen op basis van bepaalde kenmerken, bijvoorbeeld als ze zijn gestart via een internet-download. Deze integriteitsniveaus zijn van invloed op machtigingen voor resources |
| `InitiatingProcessTokenElevation` | tekenreeks | Tokentype dat de aanwezigheid of afwezigheid aangeeft van UAC-bevoegdheden (User Access Control) die zijn toegepast op het proces waarmee de gebeurtenis is gestart |
| `ReportId` | lang | Gebeurtenis-id op basis van een herhalende teller. Als u unieke gebeurtenissen wilt identificeren, moet deze kolom worden gebruikt in combinatie met de kolommen Apparaatnaam en Tijdstempel |
| `AppGuardContainerId` | tekenreeks | Id voor de gevirtualiseerde container die door Application Guard wordt gebruikt om browseractiviteit te isoleren |
| `AdditionalFields` | tekenreeks | Aanvullende informatie over de gebeurtenis in de JSON-matrixindeling |

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Opsporen op apparaten en in e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
