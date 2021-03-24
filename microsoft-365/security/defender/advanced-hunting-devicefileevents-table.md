---
title: Tabel DeviceFileEvents in het geavanceerde schema voor de jacht
description: Meer informatie over bestandsgerelateerde gebeurtenissen in de tabel DeviceFileEvents van het geavanceerde schema voor de jacht
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, filecreationevents, DeviceFileEvents, files, path, hash, sha1, sha256, md5
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 10009edab33d04ca01da9459c394634d0622cf3d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058033"
---
# <a name="devicefileevents"></a>DeviceFileEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

De `DeviceFileEvents` tabel in het geavanceerde schema [bevat](advanced-hunting-overview.md) informatie over het maken, wijzigen en andere bestandssysteemgebeurtenissen. Gebruik deze verwijzing om query's te maken die gegevens uit deze tabel retourneren.

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
| `FileOriginUrl` | tekenreeks | URL waar het bestand is gedownload |
| `FileOriginReferrerUrl` | tekenreeks | URL van de webpagina die een koppeling naar het gedownloade bestand bevat |
| `FileOriginIP` | tekenreeks | IP-adres waar het bestand is gedownload |
| `PreviousFolderPath` | tekenreeks | Oorspronkelijke map met het bestand voordat de opgenomen actie werd toegepast |
| `PreviousFileName` | tekenreeks | Oorspronkelijke naam van het bestand dat de naam heeft gewijzigd als gevolg van de actie |
| `FileSize` | lang | Grootte van het bestand in bytes |
| `InitiatingProcessAccountDomain` | tekenreeks | Domein van het account dat het proces heeft doorlopen dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessAccountName` | tekenreeks | Gebruikersnaam van het account dat het proces heeft doorlopen dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessAccountSid` | tekenreeks | Beveiligingsaanduiding (SID) van het account dat het proces heeft doorlopen dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessAccountUpn` | tekenreeks | User principal name (UPN) of the account that ran the process responsible for the event |
| `InitiatingProcessMD5` | tekenreeks | MD5-hash van het proces (afbeeldingsbestand) dat de gebeurtenis heeft gestart |
| `InitiatingProcessSHA1` | tekenreeks | SHA-1 van het proces (afbeeldingsbestand) dat de gebeurtenis heeft gestart |
| `InitiatingProcessSHA256` | tekenreeks | SHA-256 van het proces (afbeeldingsbestand) dat de gebeurtenis heeft gestart. Dit veld wordt meestal niet ingevuld: gebruik de kolom SHA1 wanneer deze beschikbaar is. |
| `InitiatingProcessFolderPath` | tekenreeks | Map met het proces (afbeeldingsbestand) dat de gebeurtenis heeft gestart |
| `InitiatingProcessFileName` | tekenreeks | Naam van het proces dat de gebeurtenis heeft gestart |
| `InitiatingProcessId` | int | Proces-id (PID) van het proces dat de gebeurtenis heeft gestart |
| `InitiatingProcessCommandLine` | tekenreeks | Opdrachtregel die wordt gebruikt om het proces uit te voeren waarmee de gebeurtenis is gestart |
| `InitiatingProcessCreationTime` | datetime | Datum en tijd waarop het proces dat de gebeurtenis heeft gestart is gestart |
| `InitiatingProcessIntegrityLevel` | tekenreeks | Integriteitsniveau van het proces dat de gebeurtenis heeft gestart. Windows wijst integriteitsniveaus toe aan processen op basis van bepaalde kenmerken, bijvoorbeeld als ze zijn gestart via een internet-download. Deze integriteitsniveaus zijn van invloed op machtigingen voor resources |
| `InitiatingProcessTokenElevation` | tekenreeks | Tokentype dat aangeeft dat de aanwezigheid of afwezigheid van UAC-bevoegdheden (User Access Control) is toegepast op het proces waarmee de gebeurtenis is gestart |
| `InitiatingProcessParentId` | int | Proces-id (PID) van het bovenliggende proces dat het proces heeft voortgebracht dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessParentFileName` | tekenreeks | Naam van het bovenliggende proces dat het proces heeft voortgebracht dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessParentCreationTime` | datetime | Datum en tijd waarop het bovenliggende deel van het proces dat verantwoordelijk is voor de gebeurtenis is gestart |
| `RequestProtocol` | tekenreeks | Netwerkprotocol, indien van toepassing, dat wordt gebruikt om de activiteit te starten: Onbekend, Lokaal, SMB of NFS |
| `ShareName` | tekenreeks | Naam van de gedeelde map met het bestand |
| `RequestSourceIP` | tekenreeks | IPv4- of IPv6-adres van het externe apparaat dat de activiteit heeft gestart |
| `RequestSourcePort` | tekenreeks | Bronpoort op het externe apparaat dat de activiteit heeft gestart |
| `RequestAccountName` | tekenreeks | Gebruikersnaam van het account dat wordt gebruikt om de activiteit op afstand te starten |
| `RequestAccountDomain` | tekenreeks | Domein van het account dat wordt gebruikt om de activiteit op afstand te starten |
| `RequestAccountSid` | tekenreeks | Beveiligingsaanduiding (SID) van het account dat wordt gebruikt om de activiteit op afstand te starten |
| `ReportId` | lang | Gebeurtenis-id op basis van een herhalende teller. Als u unieke gebeurtenissen wilt identificeren, moet deze kolom worden gebruikt in combinatie met de kolommen DeviceName en Timestamp. |
| `AppGuardContainerId` | tekenreeks | Id voor de gevirtualiseerde container die door Application Guard wordt gebruikt om browseractiviteit te isoleren |
| `AdditionalFields` | tekenreeks | Aanvullende informatie over de entiteit of gebeurtenis |
| `InitiatingProcessFileSize` | lang | Grootte van het bestand dat het proces heeft doorlopen dat verantwoordelijk is voor de gebeurtenis |
| `SensitivityLabel` | tekenreeks | Label toegepast op een e-mailbericht, bestand of andere inhoud om deze te classificeren voor informatiebeveiliging |
| `SensitivitySubLabel` | tekenreeks | Sublabel dat is toegepast op een e-mailbericht, bestand of andere inhoud om deze te classificeren voor informatiebeveiliging; gevoeligheidssublabels worden gegroepeerd onder gevoeligheidslabels, maar worden onafhankelijk van elkaar behandeld |
| `IsAzureInfoProtectionApplied` | booleaanse | Geeft aan of het bestand is versleuteld door Azure Information Protection |

>[!NOTE]
> Bestandshashgegevens worden altijd weergegeven wanneer deze beschikbaar zijn. Er zijn echter verschillende mogelijke redenen waarom een SHA1, SHA256 of MD5 niet kan worden berekend. Het bestand bevindt zich bijvoorbeeld in externe opslag, vergrendeld door een ander proces, gecomprimeerd of gemarkeerd als virtueel. In deze scenario's worden de bestandshashgegevens leeg weergegeven.

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Opsporen op apparaten en in e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
