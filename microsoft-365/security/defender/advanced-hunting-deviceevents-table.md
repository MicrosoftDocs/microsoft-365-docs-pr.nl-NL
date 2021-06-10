---
title: Tabel DeviceEvents in het geavanceerde schema voor de jacht
description: Meer informatie over antivirus, firewall en andere gebeurtenistypen in de tabel diverse apparaatgebeurtenissen (DeviceEvents) van het geavanceerde schema voor de jacht
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, security events, antivirus, firewall, exploit guard, DeviceEvents
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
ms.openlocfilehash: 63a2d41714329918192caccd384587a4e4f04112
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023197"
---
# <a name="deviceevents"></a>DeviceEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Van toepassing op:**
- Microsoft 365 Defender
- Microsoft Defender voor Eindpunt

De diverse apparaatgebeurtenissen of -tabel in het geavanceerde schema voor de jacht bevat informatie over verschillende gebeurtenistypen, waaronder gebeurtenissen die worden veroorzaakt door beveiligingsbesturingselementen, zoals Windows Defender Antivirus `DeviceEvents` en bescherming tegen misbruik. [](advanced-hunting-overview.md) Gebruik deze verwijzing om query's te maken die gegevens uit deze tabel retourneren.

>[!TIP]
> Voor gedetailleerde informatie over de gebeurtenissentypen (waarden) die door een tabel worden ondersteund, gebruikt u de `ActionType` ingebouwde schemaverwijzing die beschikbaar is in het beveiligingscentrum.

Zie de geavanceerde zoekverwijzing voor meer informatie over andere tabellen in het geavanceerde schema voor [de jacht.](advanced-hunting-schema-tables.md)


| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum en tijd waarop de gebeurtenis is opgenomen |
| `DeviceId` | tekenreeks | Unieke id voor de machine in de service |
| `DeviceName` | tekenreeks | Volledig gekwalificeerde domeinnaam (FQDN) van de computer |
| `ActionType` | tekenreeks | Type activiteit dat de gebeurtenis heeft geactiveerd. Zie de [in-portal schemaverwijzing voor](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) meer informatie |
| `FileName` | tekenreeks | Naam van het bestand waar de opgenomen actie op is toegepast |
| `FolderPath` | tekenreeks | Map met het bestand waarin de opgenomen actie is toegepast |
| `SHA1` | tekenreeks | SHA-1 van het bestand waar de opgenomen actie op is toegepast |
| `SHA256` | tekenreeks | SHA-256 van het bestand waar de opgenomen actie op is toegepast. Dit veld wordt meestal niet ingevuld: gebruik de kolom SHA1 wanneer deze beschikbaar is. |
| `MD5` | tekenreeks | MD5-hash van het bestand waar de opgenomen actie op is toegepast |
| `FileSize` | lang | Grootte van het bestand in bytes |
| `AccountDomain` | tekenreeks | Domein van het account |
| `AccountName` | tekenreeks | Gebruikersnaam van het account |
| `AccountSid` | tekenreeks | Beveiligings-id (SID) van het account |
| `RemoteUrl` | tekenreeks | URL of volledig gekwalificeerde domeinnaam (FQDN) die werd verbonden met |
| `RemoteDeviceName` | tekenreeks | Naam van de machine die een externe bewerking heeft uitgevoerd op de betreffende computer. Afhankelijk van de gebeurtenis die wordt gerapporteerd, kan deze naam een volledig gekwalificeerde domeinnaam (FQDN), een NetBIOS-naam of een hostnaam zonder domeingegevens zijn |
| `ProcessId` | int | Proces-id (PID) van het nieuw gemaakte proces |
| `ProcessCommandLine` | tekenreeks | Opdrachtregel die wordt gebruikt om het nieuwe proces te maken |
| `ProcessCreationTime` | datetime | Datum en tijd waarop het proces is gemaakt |
| `ProcessTokenElevation` | tekenreeks | Tokentype dat de aanwezigheid of afwezigheid aangeeft van UAC-bevoegdheden (User Access Control) die zijn toegepast op het nieuw gemaakte proces |
| `LogonId` | tekenreeks | Id voor een aanmeldingssessie. Deze id is alleen uniek op dezelfde computer tussen herstarten |
| `RegistryKey` | tekenreeks | Registersleutel waar de opgenomen actie op is toegepast |
| `RegistryValueName` | tekenreeks | Naam van de registerwaarde waar de opgenomen actie op is toegepast |
| `RegistryValueData` | tekenreeks | Gegevens van de registerwaarde waar de opgenomen actie op is toegepast |
| `RemoteIP` | tekenreeks | IP-adres dat werd verbonden met |
| `RemotePort` | int | TCP-poort op het externe apparaat waar verbinding mee werd |
| `LocalIP` | tekenreeks | IP-adres dat is toegewezen aan de lokale computer die tijdens communicatie wordt gebruikt |
| `LocalPort` | int | TCP-poort op de lokale computer die tijdens communicatie wordt gebruikt |
| `FileOriginUrl` | tekenreeks | URL waar het bestand is gedownload |
| `FileOriginIP` | tekenreeks | IP-adres waar het bestand is gedownload |
| `InitiatingProcessSHA1` | tekenreeks | SHA-1 van het proces (afbeeldingsbestand) dat de gebeurtenis heeft gestart |
| `InitiatingProcessSHA256` | tekenreeks | SHA-256 van het proces (afbeeldingsbestand) dat de gebeurtenis heeft gestart. Dit veld wordt meestal niet ingevuld: gebruik de kolom SHA1 wanneer deze beschikbaar is. |
| `InitiatingProcessMD5` | tekenreeks | MD5-hash van het proces (afbeeldingsbestand) dat de gebeurtenis heeft gestart |
| `InitiatingProcessFileName` | tekenreeks | Naam van het proces dat de gebeurtenis heeft gestart |
| `InitiatingProcessFileSize` | lang | Grootte van het bestand dat het proces heeft doorlopen dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessFolderPath` | tekenreeks | Map met het proces (afbeeldingsbestand) dat de gebeurtenis heeft gestart |
| `InitiatingProcessId` | int | Proces-id (PID) van het proces dat de gebeurtenis heeft gestart |
| `InitiatingProcessCommandLine` | tekenreeks | Opdrachtregel die wordt gebruikt om het proces uit te voeren waarmee de gebeurtenis is gestart |
| `InitiatingProcessCreationTime` | datetime | Datum en tijd waarop het proces dat de gebeurtenis heeft gestart is gestart |
| `InitiatingProcessAccountDomain` | tekenreeks | Domein van het account dat het proces heeft doorlopen dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessAccountName` | tekenreeks | Gebruikersnaam van het account dat het proces heeft doorlopen dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessAccountSid` | tekenreeks | Beveiligingsaanduiding (SID) van het account dat het proces heeft doorlopen dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessAccountUpn` | tekenreeks | User principal name (UPN) of the account that ran the process responsible for the event |
| `InitiatingProcessAccountObjectId` | tekenreeks | Azure AD-object-id van het gebruikersaccount dat het proces heeft uitgevoerd dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessVersionInfoCompanyName` | tekenreeks | Bedrijfsnaam van de versiegegevens van het proces (afbeeldingsbestand) dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessVersionInfoProductName` | tekenreeks | Productnaam van de versiegegevens van het proces (afbeeldingsbestand) dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessVersionInfoProductVersion` | tekenreeks | Productversie van de versiegegevens van het proces (afbeeldingsbestand) dat verantwoordelijk is voor de gebeurtenis |
|` InitiatingProcessVersionInfoInternalFileName` | tekenreeks | Interne bestandsnaam van de versiegegevens van het proces (afbeeldingsbestand) dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessVersionInfoOriginalFileName` | tekenreeks | Oorspronkelijke bestandsnaam van de versiegegevens van het proces (afbeeldingsbestand) dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessVersionInfoFileDescription` | tekenreeks | Beschrijving van de versiegegevens van het proces (afbeeldingsbestand) dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessParentId` | int | Proces-id (PID) van het bovenliggende proces dat het proces heeft voortgebracht dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessParentFileName` | tekenreeks | Naam van het bovenliggende proces dat het proces heeft voortgebracht dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessParentCreationTime` | datetime | Datum en tijd waarop het bovenliggende deel van het proces dat verantwoordelijk is voor de gebeurtenis is gestart |
| `InitiatingProcessLogonId` | tekenreeks | Id voor een aanmeldingssessie van het proces dat de gebeurtenis heeft gestart. Deze id is alleen uniek op dezelfde computer tussen herstarten |
| `ReportId` | lang | Gebeurtenis-id op basis van een herhalende teller. Als u unieke gebeurtenissen wilt identificeren, moet deze kolom worden gebruikt in combinatie met de kolommen DeviceName en Timestamp |
| `AppGuardContainerId` | tekenreeks | Id voor de gevirtualiseerde container die door Application Guard wordt gebruikt om browseractiviteit te isoleren |
| `AdditionalFields` | tekenreeks | Aanvullende informatie over de gebeurtenis in de JSON-matrixindeling |

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Opsporen op apparaten en in e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
