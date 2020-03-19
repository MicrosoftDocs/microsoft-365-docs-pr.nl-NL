---
title: Tabel DeviceEvents in het geavanceerde jachtschema
description: Meer informatie over antivirus-, firewall- en andere gebeurtenistypen in de tabel diverse apparaatgebeurtenissen (DeviceEvents) van het geavanceerde jachtschema
keywords: geavanceerde jacht, dreigingjacht, cyberdreigingsjacht, bescherming tegen microsoft-dreigingen, microsoft 365, mtp, m365, zoekopdracht, query, telemetrie, schemareferentie, kusto, tabel, kolom, gegevenstype, beveiligingsgebeurtenissen, antivirus, firewall, exploit guard, DeviceEvents
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
ms.openlocfilehash: f99420b978f77f8b4a4660394d4a6f335c5aad66
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/24/2020
ms.locfileid: "42809886"
---
# <a name="deviceevents"></a>DeviceEvents DeviceEvents

**Van toepassing op:**
- Microsoft-bedreigingsbeveiliging



De diverse apparaatgebeurtenissen of `DeviceEvents` -tabel in het geavanceerde [jachtschema](advanced-hunting-overview.md) bevat informatie over verschillende gebeurtenistypen, waaronder gebeurtenissen die worden geactiveerd door beveiligingscontroles, zoals Windows Defender Antivirus en exploitprotection. Gebruik deze verwijzing om query's te construeren die informatie uit deze tabel retourneren.

Voor informatie over andere tabellen in de geavanceerde jacht schema, [zie de geavanceerde jacht referentie](advanced-hunting-schema-tables.md).


| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | Datetime | Datum en tijdstip waarop de gebeurtenis is geregistreerd |
| `DeviceId` | Tekenreeks | Unieke id voor de machine in de service |
| `DeviceName` | Tekenreeks | Volledig gekwalificeerde domeinnaam (FQDN) van de machine |
| `ActionType` | Tekenreeks | Type activiteit dat de gebeurtenis heeft geactiveerd |
| `FileName` | Tekenreeks | Naam van het bestand waarop de opgenomen actie is toegepast |
| `FolderPath` | Tekenreeks | Map met het bestand waarop de opgenomen actie is toegepast |
| `SHA1` | Tekenreeks | SHA-1 van het bestand waarop de opgenomen actie is toegepast |
| `SHA256` | Tekenreeks | SHA-256 van het bestand waarop de opgenomen actie is toegepast. Dit veld is meestal niet gevuld: gebruik de SHA1-kolom indien beschikbaar |
| `MD5` | Tekenreeks | MD5-hash van het bestand waarop de opgenomen actie is toegepast |
| `AccountDomain` | Tekenreeks | Domein van het account |
| `AccountName` | Tekenreeks | Gebruikersnaam van het account |
| `AccountSid` | Tekenreeks | Beveiligings-id (SID) van het account |
| `RemoteUrl` | Tekenreeks | URL of volledig gekwalificeerde domeinnaam (FQDN) die werd verbonden met |
| `RemoteDeviceName` | Tekenreeks | Naam van de machine die een externe bewerking op de getroffen machine heeft uitgevoerd. Afhankelijk van de gebeurtenis die wordt gerapporteerd, kan deze naam een volledig gekwalificeerde domeinnaam (FQDN), een NetBIOS-naam of een hostnaam zonder domeingegevens zijn |
| `ProcessId` | Int | Proces-ID (PID) van het nieuw gemaakte proces |
| `ProcessCommandLine` | Tekenreeks | Opdrachtregel die wordt gebruikt om het nieuwe proces te maken |
| `ProcessCreationTime` | Datetime | Datum en tijd van het proces is gemaakt |
| `ProcessTokenElevation` | Tekenreeks | Tokentype dat de aanwezigheid of afwezigheid van UAC-bevoegdheden (User Access Control) aangeeft die zijn toegepast op het nieuw gemaakte proces |
| `LogonId` | Tekenreeks | Id voor een aanmeldingssessie. Deze id is alleen uniek op dezelfde machine tussen het opnieuw opstarten |
| `RegistryKey` | Tekenreeks | Registersleutel waarop de geregistreerde actie is toegepast |
| `RegistryValueName` | Tekenreeks | Naam van de registerwaarde waarop de geregistreerde actie is toegepast |
| `RegistryValueData` | Tekenreeks | Gegevens van de registerwaarde waarop de geregistreerde actie is toegepast |
| `RemoteIP` | Tekenreeks | IP-adres dat werd verbonden met |
| `RemotePort` | Int | TCP-poort op het externe apparaat waarmee werd verbonden |
| `LocalIP` | Tekenreeks | IP-adres toegewezen aan de lokale machine die tijdens de communicatie wordt gebruikt |
| `LocalPort` | Int | TCP-poort op de lokale machine die tijdens de communicatie wordt gebruikt |
| `FileOriginUrl` | Tekenreeks | URL waar het bestand van is gedownload |
| `FileOriginIP` | Tekenreeks | IP-adres waar het bestand van is gedownload |
| `AdditionalFields` | Tekenreeks | Aanvullende informatie over de gebeurtenis in JSON-arrayindeling |
| `InitiatingProcessSHA1` | Tekenreeks | SHA-1 van het proces (afbeeldingsbestand) dat de gebeurtenis heeft geïnitieerd |
| `InitiatingProcessSHA256` | Tekenreeks | SHA-256 van het proces (afbeeldingsbestand) dat de gebeurtenis heeft geïnitieerd. Dit veld is meestal niet gevuld: gebruik de SHA1-kolom indien beschikbaar |
| `InitiatingProcessFileName` | Tekenreeks | Naam van het proces dat de gebeurtenis heeft geïnitieerd |
| `InitiatingProcessFolderPath` | Tekenreeks | Map met het proces (afbeeldingsbestand) waarmee de gebeurtenis is gestart |
| `InitiatingProcessId` | Int | Proces-ID (PID) van het proces dat de gebeurtenis heeft geïnitieerd |
| `InitiatingProcessCommandLine` | Tekenreeks | Opdrachtregel die wordt gebruikt om het proces uit te voeren waarmee de gebeurtenis is gestart |
| `InitiatingProcessCreationTime` | Datetime | Datum en tijd waarop het proces dat de gebeurtenis heeft gestart, is gestart |
| `InitiatingProcessParentId` | Int | Process ID (PID) van het bovenliggende proces dat het proces heeft voortgebracht dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessParentFileName` | Tekenreeks | Naam van het bovenliggende proces dat het proces heeft voortgebracht dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessParentCreationTime` | Datetime | Datum en tijd waarop de ouder van het proces dat verantwoordelijk is voor de gebeurtenis is gestart |
| `InitiatingProcessMD5` | Tekenreeks | MD5-hash van het proces (afbeeldingsbestand) waarmee de gebeurtenis is gestart |
| `InitiatingProcessAccountDomain` | Tekenreeks | Domein van het account dat het proces heeft uitgevoerd dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessAccountName` | Tekenreeks | Gebruikersnaam van het account dat het proces heeft uitgevoerd dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessAccountSid` | Tekenreeks | Beveiligings-id (SID) van het account dat het proces heeft uitgevoerd dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessLogonId` | Tekenreeks | Id voor een aanmeldingssessie van het proces dat de gebeurtenis heeft gestart. Deze id is alleen uniek op dezelfde machine tussen het opnieuw opstarten |
| `ReportId` | Lange | Gebeurtenis-id op basis van een herhalingsteller. Om unieke gebeurtenissen te identificeren, moet deze kolom worden gebruikt in combinatie met de kolommen DeviceName en Timestamp |
| `AppGuardContainerId` | Tekenreeks | Id voor de gevirtualiseerde container die door Application Guard wordt gebruikt om browseractiviteit te isoleren |

## <a name="related-topics"></a>Verwante onderwerpen
- [Proactief op zoek naar bedreigingen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Zoek naar bedreigingen op verschillende apparaten en e-mails](advanced-hunting-query-emails-devices.md)
- [Het schema begrijpen](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
