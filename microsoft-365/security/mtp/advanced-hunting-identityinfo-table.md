---
title: IdentityInfo tabel in het geavanceerde jachtschema
description: Meer informatie over gebruikersaccountgegevens in de tabel IdentityInfo van het geavanceerde jachtschema
keywords: geavanceerde jacht, dreigingjacht, cyberdreigingsjacht, bescherming tegen microsoft-dreigingen, microsoft 365, mtp, m365, zoekopdracht, query, telemetrie, schemareferentie, kusto, tabel, kolom, gegevenstype, beschrijving, AccountInfo, IdentityInfo, account
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
ms.openlocfilehash: 12f8d0995d00daffe8a1ca1c2c8d9dfe25a11581
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209773"
---
# <a name="identityinfo"></a>Identiteitsinfo

**Geldt voor:**
- Microsoft Threat Protection

De `IdentityInfo` tabel in het geavanceerde [jachtschema](advanced-hunting-overview.md) bevat informatie over gebruikersaccounts die zijn verkregen uit verschillende services, waaronder Azure Active Directory. Gebruik deze verwijzing om query's te construeren die informatie uit deze tabel retourneren.

>[!NOTE]
>Deze tabel is hernoemd van `AccountInfo` . Tijdens het hernoemen worden alle query's die in de portal zijn opgeslagen, automatisch bijgewerkt. Controleer query's die u elders hebt opgeslagen.

Voor informatie over andere tabellen in de geavanceerde jacht schema, [zie de geavanceerde jacht referentie](advanced-hunting-schema-tables.md).

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `AccountObjectId` | Tekenreeks | Unieke id voor het account in Azure AD |
| `AccountUpn` | Tekenreeks | Gebruikersnaam (UPN) van het account |
| `OnPremSid` | Tekenreeks | On-premises beveiligingsidentificatie (SID) van de rekening |
| `CloudSid` | Tekenreeks | Cloudbeveiligings-id van het account |
| `GivenName` | Tekenreeks | Voornaam of voornaam van de accountgebruiker |
| `Surname` | Tekenreeks | Achternaam, familienaam of achternaam van de accountgebruiker |
| `AccountDisplayName` | Tekenreeks | Naam van de accountgebruiker die in het adresboek wordt weergegeven. Typisch een combinatie van een bepaalde of voornaam, een middelste initiatie, en een achternaam of achternaam. |
| `Department` | Tekenreeks | Naam van de afdeling waartoe de accountgebruiker behoort |
| `JobTitle` | Tekenreeks | Functietitel van de accountgebruiker |
| `AccountName` | Tekenreeks | Gebruikersnaam van het account |
| `AccountDomain` | Tekenreeks | Domein van het account |
| `EmailAddress` | Tekenreeks | SMTP-adres van het account |
| `SipProxyAddress` | Tekenreeks | Voice of over IP (VOIP) sessie initiatie protocol (SIP) adres van het account |
| `City` | Tekenreeks | Plaats waar de accountgebruiker zich bevindt |
| `Country` | Tekenreeks | Land/regio waar de accountgebruiker zich bevindt |
| `IsAccountEnabled` | Booleaanse | Geeft aan of het account is ingeschakeld of niet |

## <a name="related-topics"></a>Verwante onderwerpen
- [Proactief op zoek naar bedreigingen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Zoek naar bedreigingen op verschillende apparaten en e-mails](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
