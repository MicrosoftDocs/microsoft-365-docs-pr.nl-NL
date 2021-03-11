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
ms.openlocfilehash: 9eb2f195959409ad25b9a401a44425cc4af7f97e
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/10/2021
ms.locfileid: "50712496"
---
# <a name="appfileevents"></a>AppFileEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

De tabel in het geavanceerde zoekschema bevat informatie over activiteiten in verband met bestanden in cloud-apps en services die worden gecontroleerd door `AppFileEvents` Microsoft Cloud App Security. [](advanced-hunting-overview.md) Gebruik deze verwijzing om query's te maken die gegevens uit deze tabel retourneren.

>[!WARNING]
>Deze tabel is binnenkort niet meer beschikbaar. Vanaf 7 maart 2021 worden er geen `AppFileEvents` records meer bij de tabel logboekregistratie. Gebruikers die op en na deze datum op zoek zijn naar activiteiten in verband met bestanden in cloudservices, moeten in plaats daarvan de tabel [CloudAppEvents](advanced-hunting-cloudappevents-table.md) gebruiken. <br><br>Zoek naar query's en aangepaste detectieregels die nog steeds de tabel gebruiken en bewerk deze `AppFileEvents` om de tabel te `CloudAppEvents` gebruiken. Meer richtlijnen over het converteren van betrokken query's vindt u in Het zoeken naar [cloud-app-activiteiten met Microsoft 365 Defender geavanceerd zoeken.](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857)


Zie het geavanceerde zoekschema voor informatie over andere tabellen in het geavanceerde schema voor [het zoeken.](advanced-hunting-schema-tables.md)

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum en tijd waarop de gebeurtenis is vastgelegd |
| `ActionType` | tekenreeks | Het type activiteit dat de gebeurtenis heeft geactiveerd. Zie de [schemaverwijzing in de portal](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) voor meer informatie |
| `Application` | tekenreeks | Toepassing die de opgenomen actie heeft uitgevoerd |
| `FileName` | tekenreeks | De naam van het bestand waar de opgenomen actie op is toegepast |
| `FolderPath` | tekenreeks | Map met het bestand waar de opgenomen actie op is toegepast |
| `PreviousFileName` | tekenreeks | Oorspronkelijke naam van het bestand dat is hernoemd als gevolg van de actie |
| `PreviousFolderPath` | tekenreeks | Oorspronkelijke map met het bestand voordat de opgenomen actie werd toegepast |
| `Protocol` | tekenreeks | Netwerkprotocol gebruikt |
| `AccountName` | tekenreeks | Gebruikersnaam van het account |
| `AccountDomain` | tekenreeks | Domein van het account |
| `AccountSid` | tekenreeks | Security Identifier (SID) van het account |
| `AccountUpn` | tekenreeks | UPN (User Principal Name) van het account |
| `AccountObjectId` | tekenreeks | Unieke id voor het account in Azure AD |
| `AccountDisplayName` | tekenreeks | De naam van de accountgebruiker die wordt weergegeven in het adresboek. Meestal een combinatie van een bepaalde of voornaam, een middelste start en een achternaam of achternaam. |
| `DeviceName` | tekenreeks | FQDN (Fully Qualified Domain Name) van het apparaat |
| `DeviceType` | tekenreeks | Type apparaat | 
| `OSPlatform` | tekenreeks | Platform van het besturingssysteem dat wordt uitgevoerd op het apparaat. Dit geeft specifieke besturingssystemen aan, inclusief variaties binnen dezelfde familie, zoals Windows 10 en Windows 7. |
| `IPAddress` | tekenreeks | IP-adres dat aan het eindpunt is toegewezen en dat is gebruikt tijdens gerelateerde netwerkcommunicatie |
| `Port` | tekenreeks | TCP-poort gebruikt tijdens communicatie  |
| `DestinationDeviceName` | tekenreeks | Naam van het apparaat met de servertoepassing die de opgenomen actie heeft verwerkt |
| `DestinationIPAddress` | tekenreeks | Het IP-adres van het apparaat met de servertoepassing dat de opgenomen actie heeft verwerkt |
| `DestinationPort` | tekenreeks | Bestemmingspoort van gerelateerde netwerkcommunicatie |
| `Location` | tekenreeks | Plaats, land of andere geografische locatie die is gekoppeld aan de gebeurtenis |
| `Isp` | tekenreeks | Internetprovider (ISP) die is gekoppeld aan het IP-adres van het eindpunt |
| `ReportId` | lang | Unieke id voor de gebeurtenis |
| `AdditionalFields` | tekenreeks | Aanvullende informatie over de entiteit of gebeurtenis |

>[!TIP]
> Voor gedetailleerde informatie over de gebeurtenistypen (waarden) die door een tabel worden ondersteund, gebruikt u de `ActionType` ingebouwde schemaverwijzing in het beveiligingscentrum.


## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Opsporen op apparaten en in e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
