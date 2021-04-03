---
title: Tabel IdentityDirectoryEvents in het geavanceerde schema voor de jacht
description: Meer informatie over domeincontrollers en Active Directory-gebeurtenissen in de tabel IdentityDirectoryEvents van het geavanceerde schema voor de jacht
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, IdentityDirectoryEvents, domain controller, Active Directory, Azure ATP, identits
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
ms.openlocfilehash: 73018bb65c011d10234ec9c02fc61bfb93fa125a
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/01/2021
ms.locfileid: "51501134"
---
# <a name="identitydirectoryevents"></a>IdentityDirectoryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

De tabel in het geavanceerde schema bevat gebeurtenissen met een `IdentityDirectoryEvents` on-premises [](advanced-hunting-overview.md) domeincontroller met Active Directory (AD). Deze tabel legt verschillende identiteitsgerelateerde gebeurtenissen vast, zoals wachtwoordwijzigingen, wachtwoordverloop en upn-wijzigingen (User Principal Name). Ook worden systeemgebeurtenissen op de domeincontroller vastge leggen, zoals het plannen van taken en PowerShell-activiteiten. Gebruik deze verwijzing om query's te maken die gegevens uit deze tabel retourneren.

>[!TIP]
> Voor gedetailleerde informatie over de gebeurtenissentypen (waarden) die door een tabel worden ondersteund, gebruikt u de `ActionType` ingebouwde schemaverwijzing die beschikbaar is in het beveiligingscentrum.

Zie de geavanceerde zoekverwijzing voor meer informatie over andere tabellen in het geavanceerde schema voor [de jacht.](advanced-hunting-schema-tables.md)

| Kolomnaam | Gegevenstype | Omschrijving |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum en tijd waarop de gebeurtenis is opgenomen |
| `ActionType` | tekenreeks | Type activiteit dat de gebeurtenis heeft geactiveerd. Zie de [in-portal schemaverwijzing voor](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) meer informatie |
| `Application` | tekenreeks | Toepassing die de opgenomen actie heeft uitgevoerd |
| `TargetAccountUpn` | tekenreeks | User principal name (UPN) of the account that the recorded action was applied to |
| `TargetAccountDisplayName` | tekenreeks | Weergavenaam van het account waar de opgenomen actie op is toegepast |
| `TargetDeviceName` | tekenreeks | Volledig gekwalificeerde domeinnaam (FQDN) van het apparaat waar de opgenomen actie op is toegepast |
| `DestinationDeviceName` | tekenreeks | Naam van het apparaat met de servertoepassing die de opgenomen actie heeft verwerkt |
| `DestinationIPAddress` | tekenreeks | IP-adres van het apparaat met de servertoepassing die de opgenomen actie heeft verwerkt |
| `DestinationPort` | tekenreeks | Bestemmingspoort van de activiteit |
| `Protocol` | tekenreeks | Protocol dat tijdens de communicatie wordt gebruikt |
| `AccountName` | tekenreeks | Gebruikersnaam van het account |
| `AccountDomain` | tekenreeks | Domein van het account |
| `AccountUpn` | tekenreeks | Gebruikersnaam (UPN) van het account |
| `AccountSid` | tekenreeks | Beveiligings-id (SID) van het account |
| `AccountObjectId` | tekenreeks | Unieke id voor het account in Azure Active Directory |
| `AccountDisplayName` | tekenreeks | Naam van de accountgebruiker die wordt weergegeven in het adresboek. Meestal een combinatie van een bepaalde of voornaam, een middelste initiatie en een achternaam of achternaam. |
| `DeviceName` | tekenreeks | Volledig gekwalificeerde domeinnaam (FQDN) van het apparaat |
| `IPAddress` | tekenreeks | IP-adres dat tijdens communicatie aan het apparaat is toegewezen |
| `Port` | tekenreeks | TCP-poort die tijdens communicatie wordt gebruikt |
| `Location` | tekenreeks | Plaats, land of andere geografische locatie die is gekoppeld aan de gebeurtenis |
| `ISP` | tekenreeks | Internetprovider die is gekoppeld aan het IP-adres |
| `ReportId` | lang | Unieke id voor de gebeurtenis |
| `AdditionalFields` | tekenreeks | Aanvullende informatie over de entiteit of gebeurtenis |

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Opsporen op apparaten en in e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
