---
title: Tabel IdentityInfo in het geavanceerde schema voor de jacht
description: Meer informatie over gebruikersaccountgegevens in de tabel IdentityInfo van het geavanceerde schema voor de jacht
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, AccountInfo, IdentityInfo, account
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: d7e1ad4d10c3b71a04421d92304dc2bfcb6147da
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498204"
---
# <a name="identityinfo"></a>IdentityInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

De tabel in het geavanceerde schema bevat informatie over gebruikersaccounts die zijn verkregen `IdentityInfo` uit verschillende services, waaronder Azure Active [](advanced-hunting-overview.md) Directory. Gebruik deze verwijzing om query's te maken die gegevens uit deze tabel retourneren.

>[!NOTE]
>De naam van deze tabel is gewijzigd in `AccountInfo` . Tijdens de naamsnoemingen worden alle query's die in de portal zijn opgeslagen, automatisch bijgewerkt. Controleer query's die u ergens anders hebt opgeslagen.

Zie de geavanceerde zoekverwijzing voor meer informatie over andere tabellen in het geavanceerde schema voor [de jacht.](advanced-hunting-schema-tables.md)

| Kolomnaam | Gegevenstype | Omschrijving |
|-------------|-----------|-------------|
| `AccountObjectId` | tekenreeks | Unieke id voor het account in Azure AD |
| `AccountUpn` | tekenreeks | Gebruikersnaam (UPN) van het account |
| `OnPremSid` | tekenreeks | On-premises beveiligingsaanduiding (SID) van het account |
| `CloudSid` | tekenreeks | Cloudbeveiligingsaanduiding van het account |
| `GivenName` | tekenreeks | Opgegeven naam of voornaam van de accountgebruiker |
| `Surname` | tekenreeks | Achternaam, familienaam of achternaam van de accountgebruiker |
| `AccountDisplayName` | tekenreeks | Naam van de accountgebruiker die wordt weergegeven in het adresboek. Meestal een combinatie van een bepaalde of voornaam, een middelste initiatie en een achternaam of achternaam. |
| `Department` | tekenreeks | Naam van de afdeling van de accountgebruiker |
| `JobTitle` | tekenreeks | Functie van de accountgebruiker |
| `AccountName` | tekenreeks | Gebruikersnaam van het account |
| `AccountDomain` | tekenreeks | Domein van het account |
| `EmailAddress` | tekenreeks | SMTP-adres van het account |
| `SipProxyAddress` | tekenreeks | Voice over IP (VOIP) session initiation protocol (SIP) address of the account |
| `City` | tekenreeks | Plaats waar de accountgebruiker zich bevindt |
| `Country` | tekenreeks | Land/regio waar de accountgebruiker zich bevindt |
| `IsAccountEnabled` | booleaanse | Geeft aan of het account is ingeschakeld of niet |

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Opsporen op apparaten en in e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
