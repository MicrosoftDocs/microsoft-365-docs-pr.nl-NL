---
title: DeviceEvents-tabel in het geavanceerde jachtschema
description: Meer informatie over antivirus-, firewall- en andere gebeurtenistypen in de tabel van verschillende apparaatgebeurtenissen (DeviceEvents) van het geavanceerde jachtschema
keywords: geavanceerde jacht, bedreiging jacht, cyber bedreiging jacht, Microsoft threat protection, Microsoft 365, mtp, m365, zoeken, query, telemetrie, schema referentie, kusto, tabel, kolom, gegevenstype, security events, antivirus, firewall, exploit guard, DevicesEvent
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
ms.openlocfilehash: 0f565e7584a961fcbc48e6a421419cd48a20a963
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899325"
---
# <a name="deviceevents"></a>DeviceEvents

**Van toepassing op:**
- Microsoft Threat Protection



De verschillende apparaatgebeurtenissen of `DeviceEvents` tabel in het geavanceerde [jachtschema](advanced-hunting-overview.md) bevat informatie over verschillende gebeurtenistypen, waaronder gebeurtenissen die worden geactiveerd door beveiligingscontroles, zoals Windows Defender Antivirus en exploitbescherming. Gebruik deze verwijzing om query's te construeren die informatie uit deze tabel retourneren.

Zie [de geavanceerde jachtreferentie](advanced-hunting-schema-tables.md)voor informatie over andere tabellen in het geavanceerde jachtschema.


| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | Datetime | Datum en tijdstip waarop de gebeurtenis is geregistreerd |
| `DeviceId` | Tekenreeks | Unieke id voor de machine in de service |
| `DeviceName` | Tekenreeks | Volledig gekwalificeerde domeinnaam (FQDN) van de machine |
| `ActionType` | Tekenreeks | Type activiteit dat de gebeurtenis heeft geactiveerd |
| `FileName` | Tekenreeks | Naam van het bestand waarop de geregistreerde actie is toegepast |
| `FolderPath` | Tekenreeks | Map met het bestand waarop de opgenomen actie is toegepast |
| `SHA1` | Tekenreeks | SHA-1 van het bestand waarop de geregistreerde actie is toegepast |
| `SHA256` | Tekenreeks | SHA-256 van het bestand waarop de geregistreerde actie is toegepast. Dit veld wordt meestal niet ingevuld - gebruik de SHA1-kolom indien beschikbaar. |
| `MD5` | Tekenreeks | MD5-hash van het bestand waarop de geregistreerde actie is toegepast |
| `AccountDomain` | Tekenreeks | Domein van het account |
| `AccountName` | Tekenreeks | Gebruikersnaam van het account |
| `AccountSid` | Tekenreeks | Beveiligings-id (SID) van het account |
| `RemoteUrl` | Tekenreeks | URL of volledig gekwalificeerde domeinnaam (FQDN) die werd verbonden met |
| `RemoteDeviceName` | Tekenreeks | Naam van de machine die een externe bewerking op de getroffen machine heeft uitgevoerd. Afhankelijk van de gebeurtenis die wordt gerapporteerd, kan deze naam een volledig gekwalificeerde domeinnaam (FQDN), een NetBIOS-naam of een hostnaam zonder domeininformatie zijn |
| `ProcessId` | Int | Proces-ID (PID) van het nieuw gecreëerde proces |
| `ProcessCommandLine` | Tekenreeks | Opdrachtregel die wordt gebruikt om het nieuwe proces te maken |
| `ProcessCreationTime` | Datetime | Datum en tijd waarop het proces is gemaakt |
| `ProcessTokenElevation` | Tekenreeks | Tokentype dat de aanwezigheid of afwezigheid van UAC-bevoegdheid (User Access Control) aangeeft die wordt toegepast op het nieuw gemaakte proces |
| `LogonId` | Tekenreeks | Id voor een aanmeldingssessie. Deze id is uniek op dezelfde machine alleen tussen herstart |
| `RegistryKey` | Tekenreeks | Registersleutel waarop de geregistreerde actie is toegepast |
| `RegistryValueName` | Tekenreeks | Naam van de registerwaarde waarop de geregistreerde actie is toegepast |
| `RegistryValueData` | Tekenreeks | Gegevens over de registerwaarde waarop de geregistreerde actie is toegepast |
| `RemoteIP` | Tekenreeks | IP-adres waarmee werd verbonden |
| `RemotePort` | Int | TCP-poort op het externe apparaat waarmee |
| `LocalIP` | Tekenreeks | IP-adres toegewezen aan de lokale machine die wordt gebruikt tijdens de communicatie |
| `LocalPort` | Int | TCP-poort op de lokale machine die wordt gebruikt tijdens de communicatie |
| `FileOriginUrl` | Tekenreeks | URL waar het bestand is gedownload |
| `FileOriginIP` | Tekenreeks | IP-adres waar het bestand is gedownload |
| `AdditionalFields` | Tekenreeks | Aanvullende informatie over de gebeurtenis in de JSON-arrayindeling |
| `InitiatingProcessSHA1` | Tekenreeks | SHA-1 van het proces (afbeeldingsbestand) dat de gebeurtenis heeft geïnitieerd |
| `InitiatingProcessSHA256` | Tekenreeks | SHA-256 van het proces (afbeeldingsbestand) dat de gebeurtenis heeft geïnitieerd. Dit veld wordt meestal niet ingevuld - gebruik de SHA1-kolom indien beschikbaar. |
| `InitiatingProcessFileName` | Tekenreeks | Naam van het proces dat de gebeurtenis heeft gestart |
| `InitiatingProcessFolderPath` | Tekenreeks | Map met het proces (afbeeldingsbestand) dat de gebeurtenis heeft geïnitieerd |
| `InitiatingProcessId` | Int | Proces-ID (PID) van het proces dat de gebeurtenis heeft geïnitieerd |
| `InitiatingProcessCommandLine` | Tekenreeks | Opdrachtregel die wordt gebruikt om het proces uit te voeren dat de gebeurtenis heeft gestart |
| `InitiatingProcessCreationTime` | Datetime | Datum en tijd waarop het proces waarmee de gebeurtenis is gestart, is gestart |
| `InitiatingProcessParentId` | Int | Proces-ID (PID) van het bovenliggende proces dat het proces heeft voortgebracht dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessParentFileName` | Tekenreeks | Naam van het bovenliggende proces dat het proces heeft voortgebracht dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessParentCreationTime` | Datetime | Datum en tijd waarop de ouder van het proces dat verantwoordelijk is voor het evenement is gestart |
| `InitiatingProcessMD5` | Tekenreeks | MD5-hash van het proces (afbeeldingsbestand) dat de gebeurtenis heeft geïnitieerd |
| `InitiatingProcessAccountDomain` | Tekenreeks | Domein van het account dat het proces heeft uitgevoerd dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessAccountName` | Tekenreeks | Gebruikersnaam van het account waarop het proces is uitgevoerd dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessAccountSid` | Tekenreeks | Security Identifier (SID) van het account dat het proces heeft uitgevoerd dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessLogonId` | Tekenreeks | Id voor een aanmeldingssessie van het proces dat de gebeurtenis heeft gestart. Deze id is uniek op dezelfde machine alleen tussen herstart |
| `ReportId` | Lange | Gebeurtenis-id op basis van een herhalende teller. Om unieke gebeurtenissen te identificeren, moet deze kolom worden gebruikt in combinatie met de kolommen DeviceName en Timestamp |
| `AppGuardContainerId` | Tekenreeks | Id voor de gevirtualiseerde container die door Application Guard wordt gebruikt om browseractiviteit te isoleren |

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Zoek naar bedreigingen op verschillende apparaten en e-mails](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
