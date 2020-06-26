---
title: DeviceLogonEvents-tabel in het geavanceerde jachtschema
description: Meer informatie over verificatie- of aanmeldingsgebeurtenissen in de tabel DeviceLogonEvents van het geavanceerde jachtschema
keywords: geavanceerde jacht, bedreiging jacht, cyber bedreiging jacht, Microsoft threat protection, Microsoft 365, mtp, m365, zoeken, query, telemetrie, schema referentie, kusto, tabel, kolom, gegevenstype, beschrijving, logonevents, DeviceLogonEvents, authenticatie, aanmelding, aanmelden
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
ms.openlocfilehash: 07b2c2301784f378075e3c9803cebc5bcabf9cb0
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899265"
---
# <a name="devicelogonevents"></a>DeviceLogonEvents

**Van toepassing op:**
- Microsoft Threat Protection



De `DeviceLogonEvents` tabel in het geavanceerde [jachtschema](advanced-hunting-overview.md) bevat informatie over gebruikersaanmeldingen en andere verificatiegebeurtenissen. Gebruik deze verwijzing om query's te construeren die informatie uit deze tabel retourneren.

Zie [de geavanceerde jachtreferentie](advanced-hunting-schema-tables.md)voor informatie over andere tabellen in het geavanceerde jachtschema.

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | Datetime | Datum en tijdstip waarop de gebeurtenis is geregistreerd |
| `DeviceId` | Tekenreeks | Unieke id voor de machine in de service |
| `DeviceName` | Tekenreeks | Volledig gekwalificeerde domeinnaam (FQDN) van de machine |
| `ActionType` | Tekenreeks |Type activiteit dat de gebeurtenis heeft geactiveerd |
| `AccountDomain` | Tekenreeks | Domein van het account |
| `AccountName` | Tekenreeks | Gebruikersnaam van het account |
| `AccountSid` | Tekenreeks | Beveiligings-id (SID) van het account |
| `LogonType` | Tekenreeks | Type aanmeldingssessie, met name:<br><br> - **Interactief** - Gebruiker communiceert fysiek met de machine via het lokale toetsenbord en scherm<br><br> - **Remote interactive (RDP) logons** - Gebruiker communiceert op afstand met de machine met Remote Desktop, Terminal Services, Remote Assistance of andere RDP-clients<br><br> - **Netwerk** - Sessie die wordt gestart wanneer de machine wordt geopend met PsExec of wanneer gedeelde bronnen op de machine, zoals printers en gedeelde mappen, worden geopend<br><br> - **Batch** - Sessie geïnitieerd door geplande taken<br><br> - **Service** - Sessie geïnitieerd door services bij het starten<br> |
| `LogonId` | Tekenreeks | Id voor een aanmeldingssessie. Deze id is uniek op dezelfde machine alleen tussen herstart |
| `RemoteDeviceName` | Tekenreeks | Naam van de machine die een externe bewerking op de getroffen machine heeft uitgevoerd. Afhankelijk van de gebeurtenis die wordt gemeld, kan deze naam een volledig gekwalificeerde domeinnaam (FQDN), een NetBIOS-naam of een hostnaam zijn zonder domeininformatie |
| `RemoteIP` | Tekenreeks | IP-adres waarmee werd verbonden |
| `RemoteIPType` | Tekenreeks | Type IP-adres, bijvoorbeeld Openbaar, Privé, Gereserveerd, Loopback, Teredo, FourToSixMapping en Broadcast |
| `RemotePort` | Int | TCP-poort op het externe apparaat waarmee |
| `AdditionalFields` | Tekenreeks | Aanvullende informatie over de gebeurtenis in de JSON-arrayindeling |
| `InitiatingProcessAccountDomain` | Tekenreeks | Domein van het account dat het proces heeft uitgevoerd dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessAccountName` | Tekenreeks | Gebruikersnaam van het account waarop het proces is uitgevoerd dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessAccountSid` | Tekenreeks | Security Identifier (SID) van het account dat het proces heeft uitgevoerd dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessIntegrityLevel` | Tekenreeks | Integriteitsniveau van het proces dat de gebeurtenis heeft geïnitieerd. Windows wijst integriteitsniveaus toe aan processen op basis van bepaalde kenmerken, zoals wanneer ze zijn gestart vanaf een internetdownload. Deze integriteitsniveaus beïnvloeden machtigingen voor resources |
| `InitiatingProcessTokenElevation` | Tekenreeks | Tokentype dat de aanwezigheid of afwezigheid van UAC-bevoegdheid (User Access Control) aangeeft die wordt toegepast op het proces dat de gebeurtenis heeft gestart |
| `InitiatingProcessSHA1` | Tekenreeks | SHA-1 van het proces (afbeeldingsbestand) dat de gebeurtenis heeft geïnitieerd |
| `InitiatingProcessSHA256` | Tekenreeks | SHA-256 van het proces (afbeeldingsbestand) dat de gebeurtenis heeft geïnitieerd. Dit veld wordt meestal niet ingevuld: gebruik de SHA1-kolom indien beschikbaar |
| `InitiatingProcessMD5` | Tekenreeks | MD5-hash van het proces (afbeeldingsbestand) dat de gebeurtenis heeft geïnitieerd |
| `InitiatingProcessFileName` | Tekenreeks | Naam van het proces dat de gebeurtenis heeft gestart |
| `InitiatingProcessId` | Int | Proces-ID (PID) van het proces dat de gebeurtenis heeft geïnitieerd |
| `InitiatingProcessCommandLine` | Tekenreeks | Opdrachtregel die wordt gebruikt om het proces uit te voeren dat de gebeurtenis heeft gestart |
| `InitiatingProcessCreationTime` | Datetime | Datum en tijd waarop het proces waarmee de gebeurtenis is gestart, is gestart |
| `InitiatingProcessFolderPath` | Tekenreeks | Map met het proces (afbeeldingsbestand) dat de gebeurtenis heeft geïnitieerd |
| `InitiatingProcessParentId` | Int | Proces-ID (PID) van het bovenliggende proces dat het proces heeft voortgebracht dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessParentFileName` | Tekenreeks | Naam van het bovenliggende proces dat het proces heeft voortgebracht dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessParentCreationTime` | Datetime | Datum en tijd waarop de ouder van het proces dat verantwoordelijk is voor het evenement is gestart |
| `ReportId` | Lange | Gebeurtenis-id op basis van een herhalende teller. Om unieke gebeurtenissen te identificeren, moet deze kolom worden gebruikt in combinatie met de kolommen DeviceName en Timestamp |
| `AppGuardContainerId` | Tekenreeks | Id voor de gevirtualiseerde container die door Application Guard wordt gebruikt om browseractiviteit te isoleren |
| `IsLocalAdmin` | Booleaanse | Booleaanse indicator van de vraag of de gebruiker een lokale beheerder op de machine is |

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Zoek naar bedreigingen op verschillende apparaten en e-mails](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
