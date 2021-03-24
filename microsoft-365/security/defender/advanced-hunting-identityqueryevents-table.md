---
title: Tabel IdentityQueryEvents in het geavanceerde schema voor de jacht
description: Meer informatie over Active Directory-querygebeurtenissen in de tabel IdentityQueryEvents van het geavanceerde schema voor de jacht
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, IdentityQueryEvents, Azure AD, Active Directory, Azure ATP, identits, LDAP queries
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
ms.openlocfilehash: f663a9dcc5bebd3a7fd124bbd0c0fece5dbb62e4
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060421"
---
# <a name="identityqueryevents"></a>IdentityQueryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

De tabel in het geavanceerde schema bevat informatie over query's die worden uitgevoerd met `IdentityQueryEvents` Active Directory-objecten, zoals gebruikers, groepen, apparaten en domeinen. [](advanced-hunting-overview.md) Gebruik deze verwijzing om query's te maken die gegevens uit deze tabel retourneren.

>[!TIP]
> Voor gedetailleerde informatie over de gebeurtenissentypen (waarden) die door een tabel worden ondersteund, gebruikt u de `ActionType` ingebouwde schemaverwijzing die beschikbaar is in het beveiligingscentrum.

Zie de geavanceerde zoekverwijzing voor meer informatie over andere tabellen in het geavanceerde schema voor [de jacht.](advanced-hunting-schema-tables.md)

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum en tijd waarop de gebeurtenis is opgenomen |
| `ActionType` | tekenreeks | Type activiteit dat de gebeurtenis heeft geactiveerd. Zie de [in-portal schemaverwijzing voor](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) meer informatie |
| `Application` | tekenreeks | Toepassing die de opgenomen actie heeft uitgevoerd |
| `QueryType` | tekenreeks | Type query, zoals Querygroep, QueryUser of EnumerateUsers |
| `QueryTarget` | tekenreeks | Naam van gebruiker, groep, apparaat, domein of een ander entiteitstype dat wordt opgevraagd |
| `Query` | tekenreeks | Tekenreeks die wordt gebruikt om de query uit te voeren |
| `Protocol` | tekenreeks | Protocol dat tijdens de communicatie wordt gebruikt |
| `AccountName` | tekenreeks | Gebruikersnaam van het account |
| `AccountDomain` | tekenreeks | Domein van het account |
| `AccountUpn` | tekenreeks | Gebruikersnaam (UPN) van het account |
| `AccountSid` | tekenreeks | Beveiligings-id (SID) van het account |
| `AccountObjectId` | tekenreeks | Unieke id voor het account in Azure AD |
| `AccountDisplayName` | tekenreeks | Naam van de accountgebruiker die wordt weergegeven in het adresboek. Meestal een combinatie van een bepaalde of voornaam, een middelste initiatie en een achternaam of achternaam. |
| `DeviceName` | tekenreeks | Volledig gekwalificeerde domeinnaam (FQDN) van het eindpunt |
| `IPAddress` | tekenreeks | IP-adres toegewezen aan het eindpunt en gebruikt tijdens gerelateerde netwerkcommunicatie |
| `Port` | tekenreeks | TCP-poort die tijdens communicatie wordt gebruikt |
| `DestinationDeviceName` | tekenreeks | Naam van het apparaat met de servertoepassing die de opgenomen actie heeft verwerkt |
| `DestinationIPAddress` | tekenreeks | IP-adres van het apparaat met de servertoepassing die de opgenomen actie heeft verwerkt |
| `DestinationPort` | tekenreeks | Doelpoort van gerelateerde netwerkcommunicatie |
| `TargetDeviceName` | tekenreeks | Volledig gekwalificeerde domeinnaam (FQDN) van het apparaat waar de opgenomen actie op is toegepast |
| `TargetAccountUpn` | tekenreeks | User principal name (UPN) of the account that the recorded action was applied to |
| `TargetAccountDisplayName` | tekenreeks | Weergavenaam van het account waar de opgenomen actie op is toegepast |
| `Location` | tekenreeks | Plaats, land of andere geografische locatie die is gekoppeld aan de gebeurtenis |
| `ReportId` | lang | Unieke id voor de gebeurtenis |
| `AdditionalFields` | tekenreeks | Aanvullende informatie over de entiteit of gebeurtenis |

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Opsporen op apparaten en in e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
