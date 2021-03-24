---
title: AppFileEvents-tabel in het geavanceerde schema voor de jacht
description: Meer informatie over bestandsgerelateerde gebeurtenissen die zijn gekoppeld aan cloud-apps en -services in de tabel AppFileEvents van het geavanceerde schema voor het zoeken
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: f25570916692c4568a6d09d92faaf57b0c155029
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058062"
---
# <a name="appfileevents"></a>AppFileEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

De tabel in het geavanceerde schema bevat informatie over bestandsgerelateerde activiteiten in cloud-apps en -services die worden gecontroleerd `AppFileEvents` door Microsoft Cloud App Security. [](advanced-hunting-overview.md) Gebruik deze verwijzing om query's te maken die gegevens uit deze tabel retourneren.

>[!WARNING]
>Deze tabel wordt binnenkort niet meer gebruikt. Vanaf 7 maart 2021 registreert de tabel geen `AppFileEvents` records meer. Gebruikers die op zoek zijn naar bestandsgerelateerde activiteiten in cloudservices op en na deze datum, moeten in plaats daarvan de [tabel CloudAppEvents](advanced-hunting-cloudappevents-table.md) gebruiken. <br><br>Zoek naar query's en aangepaste detectieregels die de tabel nog steeds gebruiken en bewerk ze om `AppFileEvents` de tabel te `CloudAppEvents` gebruiken. Meer richtlijnen over het converteren van beïnvloede query's vindt u in [Hunt voor cloud-app-activiteiten met microsoft 365 Defender advanced hunting](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857).


Zie de geavanceerde zoekverwijzing voor meer informatie over andere tabellen in het geavanceerde schema voor [de jacht.](advanced-hunting-schema-tables.md)

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum en tijd waarop de gebeurtenis is opgenomen |
| `ActionType` | tekenreeks | Type activiteit dat de gebeurtenis heeft geactiveerd. Zie de [in-portal schemaverwijzing voor](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) meer informatie |
| `Application` | tekenreeks | Toepassing die de opgenomen actie heeft uitgevoerd |
| `FileName` | tekenreeks | Naam van het bestand waar de opgenomen actie op is toegepast |
| `FolderPath` | tekenreeks | Map met het bestand waarin de opgenomen actie is toegepast |
| `PreviousFileName` | tekenreeks | Oorspronkelijke naam van het bestand dat de naam heeft gewijzigd als gevolg van de actie |
| `PreviousFolderPath` | tekenreeks | Oorspronkelijke map met het bestand voordat de opgenomen actie werd toegepast |
| `Protocol` | tekenreeks | Netwerkprotocol gebruikt |
| `AccountName` | tekenreeks | Gebruikersnaam van het account |
| `AccountDomain` | tekenreeks | Domein van het account |
| `AccountSid` | tekenreeks | Beveiligings-id (SID) van het account |
| `AccountUpn` | tekenreeks | Gebruikersnaam (UPN) van het account |
| `AccountObjectId` | tekenreeks | Unieke id voor het account in Azure AD |
| `AccountDisplayName` | tekenreeks | Naam van de accountgebruiker die wordt weergegeven in het adresboek. Meestal een combinatie van een bepaalde of voornaam, een middelste initiatie en een achternaam of achternaam. |
| `DeviceName` | tekenreeks | Volledig gekwalificeerde domeinnaam (FQDN) van het apparaat |
| `DeviceType` | tekenreeks | Type apparaat | 
| `OSPlatform` | tekenreeks | Platform van het besturingssysteem dat op het apparaat wordt uitgevoerd. Dit geeft specifieke besturingssystemen aan, waaronder variaties binnen dezelfde familie, zoals Windows 10 en Windows 7. |
| `IPAddress` | tekenreeks | IP-adres toegewezen aan het eindpunt en gebruikt tijdens gerelateerde netwerkcommunicatie |
| `Port` | tekenreeks | TCP-poort die tijdens communicatie wordt gebruikt  |
| `DestinationDeviceName` | tekenreeks | Naam van het apparaat met de servertoepassing die de opgenomen actie heeft verwerkt |
| `DestinationIPAddress` | tekenreeks | IP-adres van het apparaat met de servertoepassing die de opgenomen actie heeft verwerkt |
| `DestinationPort` | tekenreeks | Doelpoort van gerelateerde netwerkcommunicatie |
| `Location` | tekenreeks | Plaats, land of andere geografische locatie die is gekoppeld aan de gebeurtenis |
| `Isp` | tekenreeks | Internetprovider die is gekoppeld aan het IP-adres van het eindpunt |
| `ReportId` | lang | Unieke id voor de gebeurtenis |
| `AdditionalFields` | tekenreeks | Aanvullende informatie over de entiteit of gebeurtenis |

>[!TIP]
> Voor gedetailleerde informatie over de gebeurtenissentypen (waarden) die door een tabel worden ondersteund, gebruikt u de `ActionType` ingebouwde schemaverwijzing die beschikbaar is in het beveiligingscentrum.


## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Opsporen op apparaten en in e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
