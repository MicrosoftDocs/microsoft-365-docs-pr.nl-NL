---
title: IdentityDirectoryEvents-tabel in het geavanceerde jacht schema
description: Meer informatie over domeincontroller en Active Directory-gebeurtenissen in de tabel IdentityDirectoryEvents van het schema geavanceerde jacht
keywords: geavanceerde jacht, bedreigings jacht, Cyber Threat jacht, Microsoft Threat Protection, Microsoft 365, MTP, m365, Search, query, Telemetry, schema naslag, kusto, tabel, kolom, gegevenstype, beschrijving, IdentityDirectoryEvents, domeincontroller, Active Directory, Azure ATP, Identities
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
ms.openlocfilehash: 1a65a8e78dfa09bc0a417669a1efd35320e261da
ms.sourcegitcommit: 445b249a6f0420b32e49742fd7744006c7090b2b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/18/2020
ms.locfileid: "46798780"
---
# <a name="identitydirectoryevents"></a>IdentityDirectoryEvents

**Van toepassing op:**
- Microsoft Threat Protection

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

De `IdentityDirectoryEvents` tabel in het [geavanceerde jacht](advanced-hunting-overview.md) -schema bevat gebeurtenissen waarbij een lokale domeincontroller met Active Directory (AD) wordt uitgevoerd. In deze tabel worden verschillende identiteits gerelateerde gebeurtenissen vastgelegd, zoals het wijzigen van wachtwoorden, het verlopen van wachtwoorden en UPN (User Principal Name)-wijzigingen. Ook worden systeemgebeurtenissen vastgelegd op de domeincontroller, zoals het plannen van taken en PowerShell-activiteiten. Gebruik deze verwijzing voor het maken van query's waarmee informatie uit deze tabel wordt geretourneerd.

>[!TIP]
> Voor gedetailleerde informatie over de typen gebeurtenissen ( `ActionType` waarden) die door een tabel worden ondersteund, gebruikt u de [ingebouwde schema verwijzing](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) die beschikbaar is in het Beveiligingscentrum.

Zie voor meer informatie over andere tabellen in het geavanceerde jacht-schema [de Naslaggids voor Geavanceerd](advanced-hunting-schema-tables.md)zoeken.

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | tijd | De datum en tijd waarop de gebeurtenis is vastgelegd |
| `ActionType` | tekenreeks | Type activiteit waarmee de gebeurtenis wordt geactiveerd. Zie de [verwijzingen naar het portal schema](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) voor Details |
| `Application` | tekenreeks | De toepassing die de opgenomen actie heeft uitgevoerd |
| `TargetAccountUpn` | tekenreeks | De UPN (User Principal Name) van het account waarop de opgenomen actie is toegepast |
| `TargetAccountDisplayName` | tekenreeks | Weergavenaam van het account waarop de opgenomen actie is toegepast |
| `TargetDeviceName` | tekenreeks | FQDN-naam (Fully Qualified Domain Name) van het apparaat waarop de opgenomen actie is toegepast |
| `DestinationDeviceName` | tekenreeks | Naam van het apparaat waarop de servertoepassing wordt uitgevoerd die de opgenomen actie heeft verwerkt |
| `DestinationIPAddress` | tekenreeks | IP-adres van het apparaat waarop de servertoepassing wordt uitgevoerd die de opgenomen actie heeft verwerkt |
| `DestinationPort` | tekenreeks | Bestemmingspoort van de activiteit |
| `Protocol` | tekenreeks | Gebruikte protocol tijdens de communicatie |
| `AccountName` | tekenreeks | Gebruikersnaam van het account |
| `AccountDomain` | tekenreeks | Domein van het account |
| `AccountUpn` | tekenreeks | UPN (User Principal Name) van het account |
| `AccountSid` | tekenreeks | SID (Security Identifier) van het account |
| `AccountObjectId` | tekenreeks | Unieke id voor het account in azure AD |
| `AccountDisplayName` | tekenreeks | Naam van de account gebruiker die in het adresboek wordt weergegeven. Meestal een combinatie van een bepaalde of voornaam, een tweede opening en een achternaam of achternaam. |
| `DeviceName` | tekenreeks | FQDN (Fully Qualified Domain Name) van het apparaat |
| `IPAddress` | tekenreeks | IP-adres dat is toegewezen aan het apparaat tijdens de communicatie |
| `Port` | tekenreeks | TCP-poort gebruikt tijdens de communicatie |
| `Location` | tekenreeks | Plaats, land of andere geografische locatie die is gekoppeld aan de gebeurtenis |
| `ISP` | tekenreeks | Internet provider die is gekoppeld aan het IP-adres |
| `ReportId` | lang | Unieke id voor de gebeurtenis |
| `AdditionalFields` | tekenreeks | Aanvullende informatie over de entiteit of gebeurtenis |

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Opsporen op apparaten en in e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)