---
title: De tabel DeviceRegistryEvents in het geavanceerde schema voor zoeken
description: Meer informatie over registergebeurtenissen die u kunt uitvoeren in de tabel DeviceRegistryEvents van het geavanceerde schema voor zoeken
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, registryevents, registry, DeviceRegistryEvents, key, subkey, value
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
ms.openlocfilehash: 376e54fb4bf5f07a1c821ff436ddc8ec7dd25812
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931108"
---
# <a name="deviceregistryevents"></a>DeviceRegistryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

De tabel in het geavanceerde schema voor zoeken bevat informatie over het maken en `DeviceRegistryEvents` wijzigen van [](advanced-hunting-overview.md) registergegevens. Gebruik deze verwijzing om query's te maken die gegevens uit deze tabel retourneren.

>[!TIP]
> Voor gedetailleerde informatie over de gebeurtenistypen (waarden) die door een tabel worden ondersteund, gebruikt u de `ActionType` [ingebouwde schemaverwijzing in](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) het beveiligingscentrum.

Zie het geavanceerde zoekschema voor meer informatie over andere tabellen in het geavanceerde schema [voor zoeken.](advanced-hunting-schema-tables.md)

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum en tijd waarop de gebeurtenis is vastgelegd |
| `DeviceId` | tekenreeks | Unieke id voor de computer in de service |
| `DeviceName` | tekenreeks | FQDN (Fully Qualified Domain Name) van de computer |
| `ActionType` | tekenreeks | Het type activiteit dat de gebeurtenis heeft geactiveerd. Zie de [schemaverwijzing in de portal voor](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) meer informatie |
| `RegistryKey` | tekenreeks | Registersleutel waar de opgenomen actie op is toegepast |
| `RegistryValueType` | tekenreeks | Het gegevenstype, zoals een binair getal of een tekenreeks, van de registerwaarde op welke actie is toegepast. |
| `RegistryValueName` | tekenreeks | Naam van de registerwaarde waar de opgenomen actie op is toegepast |
| `RegistryValueData` | tekenreeks | Gegevens van de registerwaarde waar de vastgelegde actie op is toegepast |
| `PreviousRegistryValueName` | tekenreeks | Oorspronkelijke naam van de registerwaarde voordat deze werd gewijzigd |
| `PreviousRegistryValueData` | tekenreeks | Oorspronkelijke gegevens van de registerwaarde voordat deze werd gewijzigd |
| `InitiatingProcessAccountDomain` | tekenreeks | Het domein van het account dat het proces heeft verantwoordelijk voor de gebeurtenis |
| `InitiatingProcessAccountName` | tekenreeks | Gebruikersnaam van het account dat het proces heeft verantwoordelijk voor de gebeurtenis |
| `InitiatingProcessAccountSid` | tekenreeks | Security Identifier (SID) van het account dat het proces heeft verantwoordelijk voor de gebeurtenis |
| `InitiatingProcessSHA1` | tekenreeks | SHA-1 van het proces (afbeeldingsbestand) dat de gebeurtenis heeft gestart |
| `InitiatingProcessSHA256` | tekenreeks | SHA-256 van het proces (afbeeldingsbestand) dat de gebeurtenis heeft gestart. Dit veld wordt meestal niet ingevuld. Gebruik indien beschikbaar de kolom SHA1. |
| `InitiatingProcessMD5` | tekenreeks | MD5-hash van het proces (afbeeldingsbestand) dat de gebeurtenis heeft gestart |
| `InitiatingProcessFileName` | tekenreeks | Naam van het proces dat de gebeurtenis heeft gestart |
| `InitiatingProcessId` | int | Proces-id (PID) van het proces dat de gebeurtenis heeft gestart |
| `InitiatingProcessCommandLine` | tekenreeks | Opdrachtregel die wordt gebruikt voor het uitvoeren van het proces waarmee de gebeurtenis is gestart |
| `InitiatingProcessCreationTime` | datetime | Datum en tijd waarop het proces voor het starten van de gebeurtenis is gestart |
| `InitiatingProcessFolderPath` | tekenreeks | Map met het proces (afbeeldingsbestand) dat de gebeurtenis heeft gestart |
| `InitiatingProcessParentId` | int | Proces-id (PID) van het bovenliggende proces dat het proces heeft geleid dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessParentFileName` | tekenreeks | Naam van het bovenliggende proces dat het proces heeft geleid dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessParentCreationTime` | datetime | Datum en tijd waarop de bovenliggende groep die verantwoordelijk is voor de gebeurtenis is gestart |
| `InitiatingProcessIntegrityLevel` | tekenreeks | Het integriteitsniveau van het proces dat de gebeurtenis heeft gestart. Windows wijst integriteitsniveaus toe aan processen op basis van bepaalde kenmerken, bijvoorbeeld als ze zijn gestart via een internet-download. Deze integriteitsniveaus hebben invloed op machtigingen voor resources |
| `InitiatingProcessTokenElevation` | tekenreeks | Tokentype dat de aanwezigheid of afwezigheid aangeeft van UAC-bevoegdheden (User Access Control) die zijn toegepast op het proces waarmee de gebeurtenis is gestart |
| `ReportId` | lang | Gebeurtenis-id op basis van een herhalende teller. Als u unieke gebeurtenissen wilt identificeren, moet deze kolom worden gebruikt in combinatie met de kolommen Apparaatnaam en Tijdstempel |
| `AppGuardContainerId` | tekenreeks | Id voor de gevirtualiseerde container die door Application Guard wordt gebruikt om browseractiviteit te isoleren |

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Opsporen op apparaten en in e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
