---
title: DeviceLogonEvents-tabel in het geavanceerde jacht schema
description: Meer informatie over verificatie-of aanmeld gebeurtenissen in de tabel DeviceLogonEvents van het schema geavanceerde jacht
keywords: geavanceerde jacht, bedreigings jacht, Cyber Threat jacht, Microsoft Threat Protection, Microsoft 365, MTP, m365, Search, query, Telemetry, schema naslag, kusto, tabel, kolom, gegevenstype, beschrijving, logonevents, DeviceLogonEvents, verificatie, aanmelden, aanmelden
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
ms.openlocfilehash: acdc9f1e17e163f075616e74fdc4f94865c2f38d
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842700"
---
# <a name="devicelogonevents"></a>DeviceLogonEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender



De `DeviceLogonEvents` tabel in het [Geavanceerde bejachts](advanced-hunting-overview.md) schema bevat informatie over gebruikersaanmeldingen en andere verificatiegebeurtenissen op apparaten. Gebruik deze verwijzing voor het maken van query's waarmee informatie uit deze tabel wordt geretourneerd.

>[!TIP]
> Voor gedetailleerde informatie over de typen gebeurtenissen ( `ActionType` waarden) die door een tabel worden ondersteund, gebruikt u de [ingebouwde schema verwijzing](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) die beschikbaar is in het Beveiligingscentrum.

Zie voor meer informatie over andere tabellen in het geavanceerde jacht-schema [de Naslaggids voor Geavanceerd](advanced-hunting-schema-tables.md)zoeken.

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | tijd | De datum en tijd waarop de gebeurtenis is vastgelegd |
| `DeviceId` | tekenreeks | Unieke id voor de computer in de service |
| `DeviceName` | tekenreeks | FQDN-naam (Fully Qualified Domain Name) van de computer |
| `ActionType` | tekenreeks |Type activiteit waarmee de gebeurtenis wordt geactiveerd |
| `AccountDomain` | tekenreeks | Domein van het account |
| `AccountName` | tekenreeks | Gebruikersnaam van het account |
| `AccountSid` | tekenreeks | SID (Security Identifier) van het account |
| `LogonType` | tekenreeks | Type aanmeldingssessie, met name:<br><br> - **Interactieve** gebruiker werkt fysiek samen met de computer met het lokale toetsenbord en scherm<br><br> - **Externe interactieve (RDP) aanmeldinging** -gebruikers onderlinge interactie met de computer met behulp van extern bureaublad, Terminal Services, hulp op afstand of andere RDP-clients<br><br> - **Netwerk** -sessie gestart wanneer de computer wordt geopend met behulp van PsExec of wanneer gedeelde bronnen op de computer, zoals printers en gedeelde mappen, worden geopend<br><br> - **Batch** -sessie geïnitieerd door geplande taken<br><br> - **Service** -sessie gestart door een service als deze wordt gestart<br> |
| `LogonId` | tekenreeks | Id van een aanmeldingssessie. Deze id is alleen uniek op dezelfde computer als de computer opnieuw is opgestart |
| `RemoteDeviceName` | tekenreeks | De naam van de computer die een externe bewerking heeft uitgevoerd op de betreffende computer. Afhankelijk van het item dat u meldt, kan deze naam bestaan uit een FQDN (Fully Qualified Domain Name), een NetBIOS-naam of een host name zonder domeininformatie. |
| `RemoteIP` | tekenreeks | IP-adres waarop verbinding is gemaakt |
| `RemoteIPType` | tekenreeks | Type IP-adres, bijvoorbeeld openbaar, privé, gereserveerd, loopback, Teredo, FourToSixMapping en broadcast |
| `RemotePort` | int | TCP-poort op het externe apparaat waarmee verbinding is gemaakt |
| `AdditionalFields` | tekenreeks | Aanvullende informatie over de gebeurtenis in de JSON-matrix indeling |
| `InitiatingProcessAccountDomain` | tekenreeks | Domein van het account dat de verantwoordelijke procedure voor de gebeurtenis heeft uitgevoerd |
| `InitiatingProcessAccountName` | tekenreeks | Gebruikersnaam van het account dat de door u verantwoordelijke procedure voor de gebeurtenis heeft uitgevoerd |
| `InitiatingProcessAccountSid` | tekenreeks | SID (Security Identifier) van het account dat het proces dat verantwoordelijk is voor de gebeurtenis heeft uitgevoerd |
| `InitiatingProcessIntegrityLevel` | tekenreeks | Integriteitsniveau van het proces dat de gebeurtenis heeft gestart. Windows wijst Integriteitsniveaus toe aan processen op basis van bepaalde kenmerken, zoals wanneer ze zijn gestart vanaf een Internet Download. Voor de Integriteitsniveaus zijn machtigingen voor resources van invloed. |
| `InitiatingProcessTokenElevation` | tekenreeks | Token type waarmee de aanwezigheids-of afwezigheids verhoging van de bevoegdheden voor gebruikers toegang wordt aangegeven die is uitgevoerd voor het proces waarmee de gebeurtenis wordt gestart |
| `InitiatingProcessSHA1` | tekenreeks | SHA-1 van het proces (afbeeldingsbestand) waarmee de gebeurtenis wordt gestart |
| `InitiatingProcessSHA256` | tekenreeks | SHA-256 van het proces (afbeeldingsbestand) waarmee de gebeurtenis wordt gestart. Dit veld wordt meestal niet ingevuld, met de kolom SHA1, indien beschikbaar |
| `InitiatingProcessMD5` | tekenreeks | MD5-hash van het proces (afbeeldingsbestand) waarmee de gebeurtenis wordt gestart |
| `InitiatingProcessFileName` | tekenreeks | Naam van het proces dat de gebeurtenis heeft gestart |
| `InitiatingProcessId` | int | De proces-ID (PID) van het proces dat de gebeurtenis heeft gestart |
| `InitiatingProcessCommandLine` | tekenreeks | Opdrachtregel die wordt gebruikt om het proces te starten waarmee de gebeurtenis wordt gestart |
| `InitiatingProcessCreationTime` | tijd | De datum en tijd waarop het proces dat de gebeurtenis heeft gestart, is gestart |
| `InitiatingProcessFolderPath` | tekenreeks | Map met het proces (afbeeldingsbestand) waarmee de gebeurtenis is gestart |
| `InitiatingProcessParentId` | int | De proces-ID (PID) van het bovenliggende proces dat de proces verantwoordelijke voor de gebeurtenis heeft veroorzaakt. |
| `InitiatingProcessParentFileName` | tekenreeks | Naam van het bovenliggende proces dat de proces verantwoordelijke voor de gebeurtenis heeft uitgevoerd |
| `InitiatingProcessParentCreationTime` | tijd | De datum en tijd waarop de bovenliggende site van het proces dat verantwoordelijk is voor de gebeurtenis, is gestart. |
| `ReportId` | lang | Gebeurtenis-id op basis van een herhalende teller. Als u unieke gebeurtenissen wilt identificeren, moet deze kolom worden gebruikt in combinatie met de naam van het apparaat en de timestamp-kolommen. |
| `AppGuardContainerId` | tekenreeks | Id van de gevirtualiseerde container die wordt gebruikt door Application Guard om browser activiteiten te isoleren |
| `IsLocalAdmin` | Boolean | Booleaanse indicator van het feit of de gebruiker een lokale beheerder is op de computer |

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Opsporen op apparaten en in e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
