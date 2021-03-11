---
title: Tabel DeviceFileEvents in het geavanceerde schema voor zoeken
description: Meer informatie over bestandsgerelateerde gebeurtenissen in de tabel DeviceFileEvents van het geavanceerde schema voor zoeken
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: e54a6dce9765a8b87fcf2f63bbd1342beabdcf39
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/10/2021
ms.locfileid: "50712460"
---
# <a name="devicefileevents"></a>DeviceFileEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

De `DeviceFileEvents` tabel in het geavanceerde [zoekschema](advanced-hunting-overview.md) bevat informatie over het maken, wijzigen en andere gebeurtenissen in het bestandssysteem. Gebruik deze verwijzing om query's te maken die gegevens uit deze tabel retourneren.

>[!TIP]
> Voor gedetailleerde informatie over de gebeurtenistypen (waarden) die door een tabel worden ondersteund, gebruikt u de `ActionType` ingebouwde schemaverwijzing in het beveiligingscentrum.

Zie het geavanceerde zoekschema voor informatie over andere tabellen in het geavanceerde schema voor [het zoeken.](advanced-hunting-schema-tables.md)

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum en tijd waarop de gebeurtenis is vastgelegd |
| `DeviceId` | tekenreeks | Unieke id voor de computer in de service |
| `DeviceName` | tekenreeks | FQDN (Fully Qualified Domain Name) van de computer |
| `ActionType` | tekenreeks | Het type activiteit dat de gebeurtenis heeft geactiveerd. Zie de [schemaverwijzing in de portal](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) voor meer informatie |
| `FileName` | tekenreeks | De naam van het bestand waar de opgenomen actie op is toegepast |
| `FolderPath` | tekenreeks | Map met het bestand waar de opgenomen actie op is toegepast |
| `SHA1` | tekenreeks | SHA-1 van het bestand waar de opgenomen actie op is toegepast |
| `SHA256` | tekenreeks | SHA-256 van het bestand waar de opgenomen actie op is toegepast. Dit veld wordt meestal niet ingevuld. Gebruik indien beschikbaar de kolom SHA1. |
| `MD5` | tekenreeks | MD5-hash van het bestand waar de opgenomen actie op is toegepast |
| `FileOriginUrl` | tekenreeks | URL waar het bestand is gedownload |
| `FileOriginReferrerUrl` | tekenreeks | URL van de webpagina met een koppeling naar het gedownloade bestand |
| `FileOriginIP` | tekenreeks | IP-adres waar het bestand is gedownload |
| `PreviousFolderPath` | tekenreeks | Oorspronkelijke map met het bestand voordat de opgenomen actie werd toegepast |
| `PreviousFileName` | tekenreeks | Oorspronkelijke naam van het bestand dat is hernoemd als gevolg van de actie |
| `FileSize` | lang | Grootte van het bestand in bytes |
| `InitiatingProcessAccountDomain` | tekenreeks | Het domein van het account dat het proces heeft verantwoordelijk voor de gebeurtenis |
| `InitiatingProcessAccountName` | tekenreeks | Gebruikersnaam van het account dat het proces heeft verantwoordelijk voor de gebeurtenis |
| `InitiatingProcessAccountSid` | tekenreeks | Security Identifier (SID) van het account dat het proces heeft verantwoordelijk voor de gebeurtenis |
| `InitiatingProcessAccountUpn` | tekenreeks | UPN (User Principal Name) van het account dat het proces heeft verantwoordelijk voor de gebeurtenis |
| `InitiatingProcessMD5` | tekenreeks | MD5-hash van het proces (afbeeldingsbestand) dat de gebeurtenis heeft gestart |
| `InitiatingProcessSHA1` | tekenreeks | SHA-1 van het proces (afbeeldingsbestand) dat de gebeurtenis heeft gestart |
| `InitiatingProcessSHA256` | tekenreeks | SHA-256 van het proces (afbeeldingsbestand) dat de gebeurtenis heeft gestart. Dit veld wordt meestal niet ingevuld. Gebruik indien beschikbaar de kolom SHA1. |
| `InitiatingProcessFolderPath` | tekenreeks | Map met het proces (afbeeldingsbestand) dat de gebeurtenis heeft gestart |
| `InitiatingProcessFileName` | tekenreeks | Naam van het proces dat de gebeurtenis heeft gestart |
| `InitiatingProcessId` | int | Proces-id (PID) van het proces dat de gebeurtenis heeft gestart |
| `InitiatingProcessCommandLine` | tekenreeks | Opdrachtregel die wordt gebruikt voor het uitvoeren van het proces waarmee de gebeurtenis is gestart |
| `InitiatingProcessCreationTime` | datetime | Datum en tijd waarop het proces voor het starten van de gebeurtenis is gestart |
| `InitiatingProcessIntegrityLevel` | tekenreeks | Het integriteitsniveau van het proces dat de gebeurtenis heeft gestart. Windows wijst integriteitsniveaus toe aan processen op basis van bepaalde kenmerken, bijvoorbeeld als ze zijn gestart via een internet-download. Deze integriteitsniveaus zijn van invloed op machtigingen voor resources |
| `InitiatingProcessTokenElevation` | tekenreeks | Tokentype dat de aanwezigheid of afwezigheid aangeeft van UAC-bevoegdheden (User Access Control) die zijn toegepast op het proces waarmee de gebeurtenis is gestart |
| `InitiatingProcessParentId` | int | Proces-id (PID) van het bovenliggende proces dat het proces heeft geleid dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessParentFileName` | tekenreeks | Naam van het bovenliggende proces dat het proces heeft geleid dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessParentCreationTime` | datetime | Datum en tijd waarop de bovenliggende groep die verantwoordelijk is voor de gebeurtenis is gestart |
| `RequestProtocol` | tekenreeks | Netwerkprotocol, indien van toepassing, dat wordt gebruikt om de activiteit te starten: Onbekend, Lokaal, SMB of NFS |
| `ShareName` | tekenreeks | Naam van gedeelde map met het bestand |
| `RequestSourceIP` | tekenreeks | IPv4- of IPv6-adres van het externe apparaat dat de activiteit heeft geïnitieerd |
| `RequestSourcePort` | tekenreeks | Bronpoort op het externe apparaat dat de activiteit heeft geïnitieerd |
| `RequestAccountName` | tekenreeks | Gebruikersnaam van het account waarmee de activiteit op afstand wordt gestart |
| `RequestAccountDomain` | tekenreeks | Domein van het account waarmee de activiteit op afstand wordt gestart |
| `RequestAccountSid` | tekenreeks | Security Identifier (SID) van het account waarmee de activiteit op afstand wordt gestart |
| `ReportId` | lang | Gebeurtenis-id op basis van een herhalende teller. Als u unieke gebeurtenissen wilt identificeren, moet deze kolom worden gebruikt in combinatie met de kolommen DeviceName en Timestamp. |
| `AppGuardContainerId` | tekenreeks | Id voor de gevirtualiseerde container die door Application Guard wordt gebruikt om browseractiviteit te isoleren |
| `AdditionalFields` | tekenreeks | Aanvullende informatie over de entiteit of gebeurtenis |
| `InitiatingProcessFileSize` | lang | Grootte van het bestand met het proces dat verantwoordelijk is voor de gebeurtenis |
| `SensitivityLabel` | tekenreeks | Label dat wordt toegepast op een e-mailbericht, bestand of andere inhoud om deze te classificeren ter bescherming van gegevens |
| `SensitivitySubLabel` | tekenreeks | Sublabel dat wordt toegepast op een e-mailbericht, bestand of andere inhoud om deze te classificeren ter bescherming van gegevens; gevoeligheidssublabels worden gegroepeerd onder gevoeligheidslabels, maar worden onafhankelijk behandeld |
| `IsAzureInfoProtectionApplied` | booleaanse | Geeft aan of het bestand is versleuteld door Azure Information Protection |

>[!NOTE]
> Hash-gegevens van bestanden worden altijd weergegeven wanneer deze beschikbaar zijn. Er zijn echter verschillende mogelijke redenen waarom een SHA1, SHA256 of MD5 niet kan worden berekend. Het bestand kan zich bijvoorbeeld bevinden in externe opslag, vergrendeld door een ander proces, gecomprimeerd of gemarkeerd als virtueel. In deze scenario's wordt de hash-informatie van het bestand leeg weergegeven.

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Opsporen op apparaten en in e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
