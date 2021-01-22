---
title: Tabel AppFileEvents in het geavanceerde schema voor zoeken
description: Meer informatie over bestandsgerelateerde gebeurtenissen die zijn gekoppeld aan cloud-apps en -services in de tabel AppFileEvents van het geavanceerde schema voor zoeken
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, AppFileEvents, Cloud App Security, MCAS
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
ms.openlocfilehash: 59e9affc53398f2a1b06fbab9774e4b53e146425
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932872"
---
# <a name="appfileevents"></a>AppFileEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

De tabel in het geavanceerde zoekschema bevat informatie over activiteiten in verband met bestanden in cloud-apps en services die worden gecontroleerd `AppFileEvents` door Microsoft Cloud App Security. [](advanced-hunting-overview.md) Gebruik deze verwijzing om query's te maken die gegevens uit deze tabel retourneren.

>[!TIP]
> Voor gedetailleerde informatie over de gebeurtenistypen (waarden) die door een tabel worden ondersteund, gebruikt u de `ActionType` [ingebouwde schemaverwijzing in](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) het beveiligingscentrum.

Zie het geavanceerde zoekschema voor meer informatie over andere tabellen in het geavanceerde schema [voor zoeken.](advanced-hunting-schema-tables.md)

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum en tijd waarop de gebeurtenis is vastgelegd |
| `ActionType` | tekenreeks | Het type activiteit dat de gebeurtenis heeft geactiveerd. Zie de [schemaverwijzing in de portal voor](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) meer informatie |
| `Application` | tekenreeks | Toepassing die de opgenomen actie heeft uitgevoerd |
| `FileName` | tekenreeks | Naam van het bestand waar de opgenomen actie op is toegepast |
| `FolderPath` | tekenreeks | Map met het bestand waar de opgenomen actie op is toegepast |
| `PreviousFileName` | tekenreeks | Oorspronkelijke naam van het bestand dat door de actie een andere naam heeft gegeven |
| `PreviousFolderPath` | tekenreeks | Oorspronkelijke map met het bestand voordat de opgenomen actie werd toegepast |
| `Protocol` | tekenreeks | Netwerkprotocol gebruikt |
| `AccountName` | tekenreeks | Gebruikersnaam van het account |
| `AccountDomain` | tekenreeks | Domein van het account |
| `AccountUpn` | tekenreeks | UPN (User Principal Name) van het account |
| `AccountObjectId` | tekenreeks | Unieke id voor het account in Azure AD |
| `AccountDisplayName` | tekenreeks | De naam van de accountgebruiker die wordt weergegeven in het adresboek. Meestal een combinatie van een bepaalde of voornaam, een middelste start en een achternaam of achternaam. |
| `DeviceName` | tekenreeks | FQDN (Fully Qualified Domain Name) van het apparaat |
| `DeviceType` | tekenreeks | Type apparaat | 
| `OSPlatform` | tekenreeks | Platform van het besturingssysteem dat wordt uitgevoerd op het apparaat. Dit geeft specifieke besturingssystemen aan, inclusief variaties binnen dezelfde familie, zoals Windows 10 en Windows 7. |
| `IPAddress` | tekenreeks | IP-adres dat aan het eindpunt is toegewezen en dat is gebruikt tijdens gerelateerde netwerkcommunicatie |
| `DestinationDeviceName` | tekenreeks | Naam van het apparaat met de servertoepassing die de opgenomen actie heeft verwerkt |
| `DestinationIPAddress` | tekenreeks | Het IP-adres van het apparaat met de servertoepassing die de opgenomen actie heeft verwerkt |
| `Location` | tekenreeks | Plaats, land of andere geografische locatie die is gekoppeld aan de gebeurtenis |
| `Isp` | tekenreeks | Internetprovider (ISP) die is gekoppeld aan het IP-adres van het eindpunt |
| `ReportId` | lang | Unieke id voor de gebeurtenis |
| `AdditionalFields` | tekenreeks | Aanvullende informatie over de entiteit of gebeurtenis |

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Opsporen op apparaten en in e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
