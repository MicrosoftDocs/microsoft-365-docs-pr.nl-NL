---
title: IdentityInfo-tabel in het geavanceerde jacht schema
description: Meer informatie over gegevens van gebruikersaccounts in de tabel IdentityInfo van het schema geavanceerde jacht
keywords: geavanceerde jacht, bedreigings jacht, Cyber Threat jacht, Microsoft Threat Protection, Microsoft 365, MTP, m365, Search, query, Telemetry, schema naslag, kusto, tabel, kolom, gegevenstype, beschrijving, AccountInfo, IdentityInfo, account
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
ms.openlocfilehash: 3d59f987ae4d670e3d7c6f1638f8090ffc3ba7fe
ms.sourcegitcommit: 51097b18d94da20aa727ebfbeb6ec84c263b25c3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/12/2020
ms.locfileid: "46649305"
---
# <a name="identityinfo"></a>IdentityInfo

**Van toepassing op:**
- Microsoft Threat Protection

De `IdentityInfo` tabel in het [geavanceerde jacht](advanced-hunting-overview.md) -schema bevat informatie over gebruikersaccounts die zijn verkregen van diverse services, waaronder Azure Active Directory. Gebruik deze verwijzing voor het maken van query's waarmee informatie uit deze tabel wordt geretourneerd.

>[!NOTE]
>Naam van de tabel werd gewijzigd `AccountInfo` . Bij hernoemen worden alle query's die zijn opgeslagen in de portal automatisch bijgewerkt. Controleer de query's die u elders hebt opgeslagen.

Zie voor meer informatie over andere tabellen in het geavanceerde jacht-schema [de Naslaggids voor Geavanceerd](advanced-hunting-schema-tables.md)zoeken.

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `AccountObjectId` | tekenreeks | Unieke id voor het account in azure AD |
| `AccountUpn` | tekenreeks | UPN (User Principal Name) van het account |
| `OnPremSid` | tekenreeks | SID (on-premises Security Identifier) van het account |
| `CloudSid` | tekenreeks | Cloud beveiligings-id van het account |
| `GivenName` | tekenreeks | Opgegeven naam of voornaam van de account gebruiker |
| `Surname` | tekenreeks | Naam, familienaam of achternaam van de gebruiker van het account |
| `AccountDisplayName` | tekenreeks | Naam van de account gebruiker die in het adresboek wordt weergegeven. Meestal een combinatie van een bepaalde of voornaam, een tweede opening en een achternaam of achternaam. |
| `Department` | tekenreeks | Naam van de afdeling waartoe de account gebruiker behoort |
| `JobTitle` | tekenreeks | Functienaam van de account gebruiker |
| `AccountName` | tekenreeks | Gebruikersnaam van het account |
| `AccountDomain` | tekenreeks | Domein van het account |
| `EmailAddress` | tekenreeks | SMTP-adres van het account |
| `SipProxyAddress` | tekenreeks | Voice over IP (VOIP)-adres van het Start Protocol (SIP) van de rekening |
| `City` | tekenreeks | Plaats waar de account gebruiker zich bevindt |
| `Country` | tekenreeks | Het land of de regio waar het account van de gebruiker zich bevindt |
| `IsAccountEnabled` | Boolean | Geeft aan of het account is ingeschakeld of niet |

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Jacht op apparaten, e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
