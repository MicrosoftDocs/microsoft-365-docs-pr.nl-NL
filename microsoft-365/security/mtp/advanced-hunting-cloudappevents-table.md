---
title: Tabel CloudAppEvents in het geavanceerde schema voor zoeken
description: Meer informatie over gebeurtenissen in cloud-apps en -services in de tabel CloudAppEvents van het geavanceerde schema voor zoeken
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, CloudAppEvents, Cloud App Security, MCAS
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
ms.openlocfilehash: 021a8210bbe5886021e980b33ade0b9e2ded7b5b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928451"
---
# <a name="cloudappevents"></a>CloudAppEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

De tabel in het geavanceerde schema voor zoeken is momenteel beschikbaar in de preview-versie en bevat informatie over activiteiten in verschillende cloud-apps en -services, met name `CloudAppEvents` Microsoft Teams en Exchange Online. [](advanced-hunting-overview.md) Gebruik deze verwijzing om query's te maken die gegevens uit deze tabel retourneren.

Deze tabel wordt uitgebreid met meer activiteiten die worden gecontroleerd door Microsoft Cloud App Security. Uiteindelijk bevat deze tabel bestandsactiviteit die momenteel is opgeslagen in de [tabel AppFileEvents.](advanced-hunting-appfileevents-table.md) Microsoft begeleidt u wanneer er meer gegevens naar deze tabel worden verplaatst.

Zie het geavanceerde zoekschema voor meer informatie over andere tabellen in het geavanceerde schema [voor zoeken.](advanced-hunting-schema-tables.md)

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum en tijd waarop de gebeurtenis is vastgelegd |
| `ActionType` | tekenreeks | Het type activiteit dat de gebeurtenis heeft geactiveerd |
| `Application` | tekenreeks | Toepassing die de opgenomen actie heeft uitgevoerd |
| `ApplicationId` | tekenreeks | Unieke id voor de toepassing |
| `AccountObjectId` | tekenreeks | Unieke id voor het account in Azure Active Directory |
| `AccountDisplayName` | tekenreeks | De naam van de accountgebruiker die wordt weergegeven in het adresboek. Meestal een combinatie van een bepaalde of voornaam, een middelste start en een achternaam of achternaam. |
| `IsAdminOperation` | tekenreeks | Geeft aan of de activiteit is uitgevoerd door een beheerder |
| `DeviceType` | tekenreeks | Type apparaat op basis van doel en functionaliteit, zoals 'Netwerkapparaat', 'Werkstation', 'Server', 'Mobiel', 'Gamingconsole' of 'Printer' | 
| `OSPlatform` | tekenreeks | Platform van het besturingssysteem dat wordt uitgevoerd op het apparaat. Deze kolom geeft specifieke besturingssystemen aan, inclusief variaties binnen dezelfde familie, zoals Windows 10 en Windows 7. |
| `IPAddress` | tekenreeks | IP-adres dat aan het eindpunt is toegewezen en dat is gebruikt tijdens gerelateerde netwerkcommunicatie |
| `IsAnonymousProxy` | tekenreeks | Geeft aan of het IP-adres behoort tot een bekende anonieme proxy |
| `CountryCode` | tekenreeks | Tweeletterige code die het land aangeeft waar het IP-adres van de client geo-toegewezen is |
| `City` | tekenreeks | Plaats waar het IP-adres van de client geolocatie is |
| `Isp` | tekenreeks | Internetprovider (ISP) die is gekoppeld aan het IP-adres |
| `UserAgent` | tekenreeks | Gegevens van de gebruikersagent vanuit de webbrowser of een andere clienttoepassing |
| `ActivityType` | tekenreeks | Het type activiteit dat de gebeurtenis heeft geactiveerd |
| `ActivityObjects` | tekenreeks | Lijst met objecten, zoals bestanden of mappen, die zijn betrokken bij de vastgelegde activiteit |
| `ObjectName` | tekenreeks | De naam van het object waar de opgenomen actie op is toegepast |
| `ObjectType` | tekenreeks | Het type object, zoals een bestand of map, waar de opgenomen actie op is toegepast |
| `ObjectId` | tekenreeks | Unieke id van het object waar de opgenomen actie op is toegepast |
| `ReportId` | tekenreeks | Unieke id voor de gebeurtenis |
| `RawEventData` | tekenreeks | Onbewerkte gebeurtenisgegevens uit de brontoepassing of service in JSON-indeling |
| `AdditionalFields` | tekenreeks | Aanvullende informatie over de entiteit of gebeurtenis |

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Opsporen op apparaten en in e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
