---
title: DeviceLogonEvents tabel in de geavanceerde jacht schema
description: Meer informatie over verificatie- of aanmeldingsgebeurtenissen in de tabel DeviceLogonEvents van het geavanceerde jachtschema
keywords: geavanceerde jacht, bedreigingsjacht, cyberdreigingsjacht, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetrie, schemareferentie, kusto, tabel, kolom, gegevenstype, beschrijving, aanmeldingsgebeurtenissen, DeviceLogonEvents, authenticatie, logon, log in
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
ms.openlocfilehash: 7c7f1bba23379b25ccecc427b2aa866a1105396d
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/24/2020
ms.locfileid: "42812072"
---
# <a name="devicelogonevents"></a>DeviceLogonEvents

**Van toepassing op:**
- Microsoft-bedreigingsbeveiliging



De `DeviceLogonEvents` tabel in het [geavanceerde jachtschema](advanced-hunting-overview.md) bevat informatie over gebruikersaanmeldingen en andere verificatiegebeurtenissen. Gebruik deze verwijzing om query's te maken die informatie uit deze tabel retourneren.

Zie [de geavanceerde jachtreferentie](advanced-hunting-schema-tables.md)voor informatie over andere tabellen in het geavanceerde jachtschema.

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | Datetime | Datum en tijd waarop de gebeurtenis is geregistreerd |
| `DeviceId` | Tekenreeks | Unieke id voor de machine in de service |
| `DeviceName` | Tekenreeks | Volledig gekwalificeerde domeinnaam (FQDN) van de machine |
| `ActionType` | Tekenreeks |Type activiteit dat de gebeurtenis heeft geactiveerd |
| `AccountDomain` | Tekenreeks | Domein van het account |
| `AccountName` | Tekenreeks | Gebruikersnaam van het account |
| `AccountSid` | Tekenreeks | Beveiligingsidentificatie (SID) van het account |
| `LogonType` | Tekenreeks | Type aanmeldingssessie, in het bijzonder:<br><br> - **Interactief** - Gebruiker communiceert fysiek met de machine met behulp van het lokale toetsenbord en scherm<br><br> - **Remote interactive (RDP) logons** - Gebruiker werkt op afstand met de machine met extern bureaublad, Terminal Services, Remote Assistance of andere RDP-clients<br><br> - **Netwerk** - Sessie gestart wanneer de machine wordt geopend via PsExec of wanneer gedeelde bronnen op de machine, zoals printers en gedeelde mappen, worden geopend<br><br> - **Batch** - Sessie geïnitieerd door geplande taken<br><br> - **Service** - Sessie geïnitieerd door services bij het starten<br> |
| `LogonId` | Tekenreeks | Id voor een aanmeldingssessie. Deze id is uniek op dezelfde machine alleen tussen herstart |
| `RemoteDeviceName` | Tekenreeks | Naam van de machine die een externe bewerking op de getroffen machine heeft uitgevoerd. Afhankelijk van de gebeurtenis die wordt gerapporteerd, kan deze naam een volledig gekwalificeerde domeinnaam (FQDN), een NetBIOS-naam of een hostnaam zonder domeininformatie zijn |
| `RemoteIP` | Tekenreeks | IP-adres dat werd verbonden met |
| `RemoteIPType` | Tekenreeks | Type IP-adres, bijvoorbeeld Openbaar, Privé, Gereserveerd, Loopback, Teredo, FourToSixMapping en Broadcast |
| `RemotePort` | Int | TCP-poort op het externe apparaat waarmee |
| `AdditionalFields` | Tekenreeks | Aanvullende informatie over het evenement in JSON-arrayindeling |
| `InitiatingProcessAccountDomain` | Tekenreeks | Domein van het account dat het proces heeft uitgevoerd dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessAccountName` | Tekenreeks | Gebruikersnaam van het account dat het proces heeft uitgevoerd dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessAccountSid` | Tekenreeks | Beveiligings-id (SID) van het account dat het proces dat verantwoordelijk was voor de gebeurtenis leidde |
| `InitiatingProcessIntegrityLevel` | Tekenreeks | Integriteitsniveau van het proces dat de gebeurtenis heeft geïnitieerd. Windows kent integriteitsniveaus toe aan processen op basis van bepaalde kenmerken, zoals of ze zijn gestart via een internetdownload. Deze integriteitsniveaus beïnvloeden machtigingen voor resources |
| `InitiatingProcessTokenElevation` | Tekenreeks | Tokentype dat de aanwezigheid of afwezigheid aangeeft van uac-bevoegdheden (User Access Control) die zijn toegepast op het proces dat de gebeurtenis heeft gestart |
| `InitiatingProcessSHA1` | Tekenreeks | SHA-1 van het proces (afbeeldingsbestand) waarmee de gebeurtenis is gestart |
| `InitiatingProcessSHA256` | Tekenreeks | SHA-256 van het proces (afbeeldingsbestand) waarmee de gebeurtenis is gestart. Dit veld wordt meestal niet ingevuld: gebruik de SHA1-kolom indien beschikbaar |
| `InitiatingProcessMD5` | Tekenreeks | MD5-hash van het proces (afbeeldingsbestand) waarmee de gebeurtenis is gestart |
| `InitiatingProcessFileName` | Tekenreeks | Naam van het proces waarmee de gebeurtenis is gestart |
| `InitiatingProcessId` | Int | Process ID (PID) van het proces dat de gebeurtenis heeft geïnitieerd |
| `InitiatingProcessCommandLine` | Tekenreeks | Opdrachtregel die wordt gebruikt om het proces uit te voeren waarmee de gebeurtenis is gestart |
| `InitiatingProcessCreationTime` | Datetime | Datum en tijd waarop het proces waarmee de gebeurtenis is gestart, is gestart |
| `InitiatingProcessFolderPath` | Tekenreeks | Map met het proces (afbeeldingsbestand) waarmee de gebeurtenis is gestart |
| `InitiatingProcessParentId` | Int | Process ID (PID) van het bovenliggende proces dat het proces dat verantwoordelijk is voor de gebeurtenis heeft voortgebracht |
| `InitiatingProcessParentFileName` | Tekenreeks | Naam van het bovenliggende proces dat het proces dat verantwoordelijk is voor de gebeurtenis heeft voortgebracht |
| `InitiatingProcessParentCreationTime` | Datetime | Datum en tijd waarop de ouder van het proces dat verantwoordelijk is voor de gebeurtenis is gestart |
| `ReportId` | Lange | Gebeurtenis-id op basis van een herhalende teller. Om unieke gebeurtenissen te identificeren, moet deze kolom worden gebruikt in combinatie met de kolommen DeviceName en Timestamp |
| `AppGuardContainerId` | Tekenreeks | Id voor de gevirtualiseerde container die door Application Guard wordt gebruikt om browseractiviteit te isoleren |
| `IsLocalAdmin` | Booleaanse | Booleaanse indicator van de vraag of de gebruiker een lokale beheerder op de machine is |

## <a name="related-topics"></a>Verwante onderwerpen
- [Proactief jagen op bedreigingen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Op zoek naar bedreigingen op verschillende apparaten en e-mails](advanced-hunting-query-emails-devices.md)
- [Het schema begrijpen](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
