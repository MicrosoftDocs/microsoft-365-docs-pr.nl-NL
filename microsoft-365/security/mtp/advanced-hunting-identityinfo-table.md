---
title: Tabel IdentityInfo in het geavanceerde schema voor zoeken
description: Meer informatie over gebruikersaccountgegevens in de tabel IdentityInfo van het geavanceerde schema voor zoeken
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, AccountInfo, IdentityInfo, account
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
ms.openlocfilehash: 6604e6d48e277e840b87ddc461580bcb69dd1bc7
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929908"
---
# <a name="identityinfo"></a>IdentityInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

De `IdentityInfo` tabel in het geavanceerde [zoekschema](advanced-hunting-overview.md) bevat informatie over gebruikersaccounts die zijn verkregen uit diverse services, waaronder Azure Active Directory. Gebruik deze verwijzing om query's te maken die gegevens uit deze tabel retourneren.

>[!NOTE]
>De naam van deze tabel is `AccountInfo` gewijzigd in . Tijdens het wijzigen van namen worden alle query's die zijn opgeslagen in de portal, automatisch bijgewerkt. Controleer de query's die u ergens anders hebt opgeslagen.

Zie het geavanceerde zoekschema voor meer informatie over andere tabellen in het geavanceerde schema [voor zoeken.](advanced-hunting-schema-tables.md)

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `AccountObjectId` | tekenreeks | Unieke id voor het account in Azure AD |
| `AccountUpn` | tekenreeks | UPN (User Principal Name) van het account |
| `OnPremSid` | tekenreeks | On-premises beveiligings-id (SID) van het account |
| `CloudSid` | tekenreeks | Cloudbeveiligings-id van het account |
| `GivenName` | tekenreeks | Gegeven naam of voornaam van de accountgebruiker |
| `Surname` | tekenreeks | Achternaam, familienaam of achternaam van de accountgebruiker |
| `AccountDisplayName` | tekenreeks | De naam van de accountgebruiker die wordt weergegeven in het adresboek. Meestal een combinatie van een bepaalde of voornaam, een middelste start en een achternaam of achternaam. |
| `Department` | tekenreeks | Naam van de afdeling van de accountgebruiker |
| `JobTitle` | tekenreeks | Functie van de accountgebruiker |
| `AccountName` | tekenreeks | Gebruikersnaam van het account |
| `AccountDomain` | tekenreeks | Domein van het account |
| `EmailAddress` | tekenreeks | SMTP-adres van het account |
| `SipProxyAddress` | tekenreeks | VOIP-adres (Voice over IP) voor DE SIP-sessie (Session Initiation Protocol) van het account |
| `City` | tekenreeks | Plaats waar de accountgebruiker zich bevindt |
| `Country` | tekenreeks | Land/regio waar de accountgebruiker zich bevindt |
| `IsAccountEnabled` | boolean | Geeft aan of het account is ingeschakeld of niet |

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Opsporen op apparaten en in e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
