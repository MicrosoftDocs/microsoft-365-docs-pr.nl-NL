---
title: De tabel IdentityDirectoryEvents in het geavanceerde schema voor zoeken
description: Meer informatie over domeincontroller en Active Directory-gebeurtenissen in de tabel IdentityDirectoryEvents van het geavanceerde schema voor zoeken
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, IdentityDirectoryEvents, domain controller, Active Directory, Azure ATP, identities
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
ms.openlocfilehash: d4e119bc0a2e600d5203231eb196cf201469bfd2
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/10/2021
ms.locfileid: "50712364"
---
# <a name="identitydirectoryevents"></a>IdentityDirectoryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

De tabel in het geavanceerde zoekschema bevat gebeurtenissen waarbij een `IdentityDirectoryEvents` on-premises [](advanced-hunting-overview.md) domeincontroller met Active Directory (AD) wordt uitgevoerd. Deze tabel legt diverse identiteitsgerelateerde gebeurtenissen vast, zoals wachtwoordwijzigingen, wachtwoordverloop en UPN-wijzigingen (User Principal Name). Ook worden systeemgebeurtenissen op de domeincontroller vastleggen, zoals het plannen van taken en PowerShell-activiteit. Gebruik deze verwijzing om query's te maken die gegevens uit deze tabel retourneren.

>[!TIP]
> Voor gedetailleerde informatie over de gebeurtenistypen (waarden) die door een tabel worden ondersteund, gebruikt u de `ActionType` ingebouwde schemaverwijzing in het beveiligingscentrum.

Zie het geavanceerde zoekschema voor informatie over andere tabellen in het geavanceerde schema voor [het zoeken.](advanced-hunting-schema-tables.md)

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum en tijd waarop de gebeurtenis is vastgelegd |
| `ActionType` | tekenreeks | Het type activiteit dat de gebeurtenis heeft geactiveerd. Zie de [schemaverwijzing in de portal](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) voor meer informatie |
| `Application` | tekenreeks | Toepassing die de opgenomen actie heeft uitgevoerd |
| `TargetAccountUpn` | tekenreeks | UPN (User Principal Name) van het account waar de opgenomen actie op is toegepast |
| `TargetAccountDisplayName` | tekenreeks | Weergavenaam van het account waar de opgenomen actie op is toegepast |
| `TargetDeviceName` | tekenreeks | FQDN (Fully Qualified Domain Name) van het apparaat waar de opgenomen actie op is toegepast |
| `DestinationDeviceName` | tekenreeks | Naam van het apparaat met de servertoepassing die de opgenomen actie heeft verwerkt |
| `DestinationIPAddress` | tekenreeks | Het IP-adres van het apparaat met de servertoepassing dat de opgenomen actie heeft verwerkt |
| `DestinationPort` | tekenreeks | Bestemmingspoort van de activiteit |
| `Protocol` | tekenreeks | Protocol dat is gebruikt tijdens de communicatie |
| `AccountName` | tekenreeks | Gebruikersnaam van het account |
| `AccountDomain` | tekenreeks | Domein van het account |
| `AccountUpn` | tekenreeks | UPN (User Principal Name) van het account |
| `AccountSid` | tekenreeks | Security Identifier (SID) van het account |
| `AccountObjectId` | tekenreeks | Unieke id voor het account in Azure Active Directory |
| `AccountDisplayName` | tekenreeks | De naam van de accountgebruiker die wordt weergegeven in het adresboek. Meestal een combinatie van een bepaalde of voornaam, een middelste start en een achternaam of achternaam. |
| `DeviceName` | tekenreeks | FQDN (Fully Qualified Domain Name) van het apparaat |
| `IPAddress` | tekenreeks | IP-adres dat tijdens communicatie aan het apparaat is toegewezen |
| `Port` | tekenreeks | TCP-poort gebruikt tijdens communicatie |
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
