---
title: Tabel IdentityQueryEvents in het geavanceerde jachtschema
description: Meer informatie over Active Directory-querygebeurtenissen in de tabel IdentityQueryEvents van het geavanceerde jachtschema
keywords: geavanceerde jacht, bedreigingsjacht, cyberdreigingsjacht, bescherming tegen microsoft-bedreigingen, microsoft 365, mtp, m365, zoekopdracht, query, telemetrie, schemaverwijzing, kusto, tabel, kolom, gegevenstype, beschrijving, IdentityQueryEvents, Azure AD, Active Directory, Azure ATP, identiteiten, LDAP-query's
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
ms.openlocfilehash: b2fc94d6ac6606c97b4824bc556b7299a2bd8ec7
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929166"
---
# <a name="identityqueryevents"></a>IdentityQueryGebeurtenissen

**Van toepassing op:**
- Microsoft-bedreigingsbeveiliging

De `IdentityQueryEvents` tabel in het [geavanceerde jachtschema](advanced-hunting-overview.md) bevat informatie over query's die zijn uitgevoerd met Active Directory-objecten, zoals gebruikers, groepen, apparaten en domeinen. Gebruik deze verwijzing om query's te construeren die informatie uit deze tabel retourneren.

Voor informatie over andere tabellen in de geavanceerde jacht schema, [zie de geavanceerde jacht referentie](advanced-hunting-schema-tables.md).

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | Datetime | Datum en tijdstip waarop de gebeurtenis is geregistreerd |
| `ActionType` | Tekenreeks | Type activiteit dat de gebeurtenis heeft geactiveerd |
| `Application` | Tekenreeks | Toepassing die de geregistreerde actie heeft uitgevoerd |
| `Query` | Tekenreeks | Type query: QueryGroep, QueryUser of Gebruikers opsommen |
| `QueryObject` | Tekenreeks | Naam van de gebruiker, groep, apparaat, domein of een ander entiteitstype dat wordt opgevraagd |
| `Protocol` | Tekenreeks | Protocol dat tijdens de communicatie wordt gebruikt |
| `AccountName` | Tekenreeks | Gebruikersnaam van het account |
| `AccountDomain` | Tekenreeks | Domein van het account |
| `AccountUpn` | Tekenreeks | Gebruikersnaam (UPN) van het account |
| `AccountSid` | Tekenreeks | Beveiligings-id (SID) van het account |
| `AccountObjectId` | Tekenreeks | Unieke id voor het account in Azure AD |
| `AccountDisplayName` | Tekenreeks | Naam van de accountgebruiker die in het adresboek wordt weergegeven. Typisch een combinatie van een bepaalde of voornaam, een middelste initiatie, en een achternaam of achternaam. |
| `DeviceName` | Tekenreeks | Volledig gekwalificeerde domeinnaam (FQDN) van het eindpunt |
| `IPAddress` | Tekenreeks | IP-adres toegewezen aan het eindpunt en gebruikt tijdens gerelateerde netwerkcommunicatie |
| `Location` | Tekenreeks | Stad, land of andere geografische locatie die aan de gebeurtenis is gekoppeld |

## <a name="related-topics"></a>Verwante onderwerpen
- [Proactief op zoek naar bedreigingen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Zoek naar bedreigingen op verschillende apparaten en e-mails](advanced-hunting-query-emails-devices.md)
- [Het schema begrijpen](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
