---
title: IdentityQueryEvents-tabel in het geavanceerde jacht schema
description: Meer informatie over Active Directory-querygebeurtenissen in de tabel IdentityQueryEvents van het schema geavanceerde jacht
keywords: geavanceerde jacht, bedreigings jacht, Cyber Threat jacht, Microsoft Threat Protection, Microsoft 365, MTP, m365, Search, query, Telemetry, schema naslag, kusto, tabel, kolom, gegevenstype, beschrijving, IdentityQueryEvents, Azure AD, Active Directory, Azure ATP, Identities, LDAP-query's
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
ms.openlocfilehash: cf2038a15242139817eb073ec2a6408905824123
ms.sourcegitcommit: 51097b18d94da20aa727ebfbeb6ec84c263b25c3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/12/2020
ms.locfileid: "46649317"
---
# <a name="identityqueryevents"></a>IdentityQueryEvents

**Van toepassing op:**
- Microsoft Threat Protection

De `IdentityQueryEvents` tabel in het [geavanceerde jacht](advanced-hunting-overview.md) -schema bevat informatie over query's die zijn uitgevoerd voor Active Directory-objecten, zoals gebruikers, groepen, apparaten en domeinen. Gebruik deze verwijzing voor het maken van query's waarmee informatie uit deze tabel wordt geretourneerd.

Zie voor meer informatie over andere tabellen in het geavanceerde jacht-schema [de Naslaggids voor Geavanceerd](advanced-hunting-schema-tables.md)zoeken.

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | tijd | De datum en tijd waarop de gebeurtenis is vastgelegd |
| `ActionType` | tekenreeks | Type activiteit waarmee de gebeurtenis wordt geactiveerd |
| `Application` | tekenreeks | De toepassing die de opgenomen actie heeft uitgevoerd |
| `QueryType` | tekenreeks | Type query, zoals QueryGroup, QueryUser of EnumerateUsers |
| `QueryTarget` | tekenreeks | De naam van de gebruiker, groep, het apparaat, het domein of een ander entiteitstype dat wordt opgevraagd |
| `Query` | tekenreeks | Tekenreeks die wordt gebruikt om de query uit te voeren |
| `Protocol` | tekenreeks | Gebruikte protocol tijdens de communicatie |
| `AccountName` | tekenreeks | Gebruikersnaam van het account |
| `AccountDomain` | tekenreeks | Domein van het account |
| `AccountUpn` | tekenreeks | UPN (User Principal Name) van het account |
| `AccountSid` | tekenreeks | SID (Security Identifier) van het account |
| `AccountObjectId` | tekenreeks | Unieke id voor het account in azure AD |
| `AccountDisplayName` | tekenreeks | Naam van de account gebruiker die in het adresboek wordt weergegeven. Meestal een combinatie van een bepaalde of voornaam, een tweede opening en een achternaam of achternaam. |
| `DeviceName` | tekenreeks | FQDN-naam (Fully Qualified Domain Name) van het eindpunt |
| `IPAddress` | tekenreeks | Het IP-adres dat is toegewezen aan het eindpunt en die wordt gebruikt tijdens gerelateerde netwerkcommunicatie |
| `DestinationDeviceName` | tekenreeks | Naam van het apparaat waarop de servertoepassing wordt uitgevoerd die de opgenomen actie heeft verwerkt |
| `DestinationIPAddress` | tekenreeks | IP-adres van het apparaat waarop de servertoepassing wordt uitgevoerd die de opgenomen actie heeft verwerkt |
| `TargetDeviceName` | tekenreeks | FQDN-naam (Fully Qualified Domain Name) van het apparaat waarop de opgenomen actie is toegepast |
| `TargetAccountUpn` | tekenreeks | De UPN (User Principal Name) van het account waarop de opgenomen actie is toegepast |
| `TargetAccountDisplayName` | tekenreeks | Weergavenaam van het account waarop de opgenomen actie is toegepast |
| `Location` | tekenreeks | Plaats, land of andere geografische locatie die is gekoppeld aan de gebeurtenis |
| `ReportId` | lang | Unieke id voor de gebeurtenis |
| `AdditionalFields` | tekenreeks | Aanvullende informatie over de entiteit of gebeurtenis |

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Jacht op apparaten, e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
