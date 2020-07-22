---
title: IdentityQueryEvents tabel in de geavanceerde jacht schema
description: Meer informatie over Active Directory-querygebeurtenissen in de tabel IdentityQueryEvents van het geavanceerde jachtschema
keywords: geavanceerde jacht, bedreiging jacht, cyber bedreiging jacht, Microsoft threat protection, Microsoft 365, mtp, m365, zoeken, query, telemetrie, schema referentie, kusto, tabel, kolom, gegevenstype, beschrijving, IdentityQueryEvents, Azure AD, Active Directory, Azure ATP, identiteiten, LDAP query's
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
ms.openlocfilehash: 436c4d7306f9f5febd614489090a0a10929ba3c9
ms.sourcegitcommit: b4119682bd3c036289e851fff56fde869c816479
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/22/2020
ms.locfileid: "45204873"
---
# <a name="identityqueryevents"></a>IdentityQueryEvents

**Van toepassing op:**
- Microsoft Threat Protection

De `IdentityQueryEvents` tabel in het geavanceerde [jachtschema](advanced-hunting-overview.md) bevat informatie over query's die zijn uitgevoerd op Active Directory-objecten, zoals gebruikers, groepen, apparaten en domeinen. Gebruik deze verwijzing om query's te construeren die informatie uit deze tabel retourneren.

Zie [de geavanceerde jachtreferentie](advanced-hunting-schema-tables.md)voor informatie over andere tabellen in het geavanceerde jachtschema.

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | Datetime | Datum en tijdstip waarop de gebeurtenis is geregistreerd |
| `ActionType` | Tekenreeks | Type activiteit dat de gebeurtenis heeft geactiveerd |
| `Application` | Tekenreeks | Toepassing die de opgenomen actie heeft uitgevoerd |
| `QueryType` | Tekenreeks | Type query, zoals QueryGroup, QueryUser of EnumerateUsers |
| `QueryTarget` | Tekenreeks | Naam van gebruiker, groep, apparaat, domein of ander entiteitstype dat wordt opgevraagd |
| `Query` | Tekenreeks | Tekenreeks die wordt gebruikt om de query uit te voeren |
| `Protocol` | Tekenreeks | Protocol dat tijdens de communicatie wordt gebruikt |
| `AccountName` | Tekenreeks | Gebruikersnaam van het account |
| `AccountDomain` | Tekenreeks | Domein van het account |
| `AccountUpn` | Tekenreeks | Gebruikersnaam (UPN) van het account |
| `AccountSid` | Tekenreeks | Beveiligings-id (SID) van het account |
| `AccountObjectId` | Tekenreeks | Unieke id voor het account in Azure AD |
| `AccountDisplayName` | Tekenreeks | Naam van de accountgebruiker die in het adresboek wordt weergegeven. Typisch een combinatie van een bepaalde of voornaam, een middelste initiatie, en een achternaam of achternaam. |
| `DeviceName` | Tekenreeks | Volledig gekwalificeerde domeinnaam (FQDN) van het eindpunt |
| `IPAddress` | Tekenreeks | IP-adres toegewezen aan het eindpunt en gebruikt tijdens gerelateerde netwerkcommunicatie |
| `DestinationDeviceName` | Tekenreeks | Naam van het apparaat waarop de servertoepassing wordt uitgevoerd die de geregistreerde actie heeft verwerkt |
| `DestinationIPAddress` | Tekenreeks | IP-adres van het apparaat waarop de servertoepassing wordt uitgevoerd die de geregistreerde actie heeft verwerkt |
| `TargetDeviceName` | Tekenreeks | Volledig gekwalificeerde domeinnaam (FQDN) van het apparaat waarop de geregistreerde actie is toegepast |
| `TargetAccountUpn` | Tekenreeks | Gebruikersnaam (UPN) van het account waarop de geregistreerde actie is toegepast |
| `TargetAccountDisplayName` | Tekenreeks | De naam weergeven van het account waarop de geregistreerde actie is toegepast |
| `Location` | Tekenreeks | Plaats, land of andere geografische locatie die aan het evenement is gekoppeld |
| `ReportId` | Lange | Unieke id voor het evenement |
| `AdditionalFields` | Tekenreeks | Aanvullende informatie over de entiteit of gebeurtenis |

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Zoek naar bedreigingen op verschillende apparaten en e-mails](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
