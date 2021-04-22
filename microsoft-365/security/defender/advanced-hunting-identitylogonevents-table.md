---
title: Tabel IdentityLogonEvents in het geavanceerde schema voor de jacht
description: Meer informatie over verificatiegebeurtenissen die zijn geregistreerd door Active Directory in de tabel IdentityLogonEvents van het geavanceerde schema voor de jacht
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, IdentityLogonEvents, Azure AD, Active Directory, Microsoft Defender for Identity, identits
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
ms.openlocfilehash: 55ec52acd5419729f46779f1d4205cd55ce27f9d
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935807"
---
# <a name="identitylogonevents"></a>IdentityLogonEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

De tabel in het geavanceerde schema bevat informatie over verificatieactiviteiten die zijn gemaakt via uw on-premises Active Directory die is vastgelegd door Microsoft Defender voor identiteits- en verificatieactiviteiten met betrekking tot microsoft-onlineservices die zijn vastgelegd door `IdentityLogonEvents` Microsoft Cloud App Security. [](advanced-hunting-overview.md) Gebruik deze verwijzing om query's te maken die gegevens uit deze tabel retourneren.

>[!TIP]
> Voor gedetailleerde informatie over de gebeurtenissentypen (waarden) die door een tabel worden ondersteund, gebruikt u de `ActionType` ingebouwde schemaverwijzing die beschikbaar is in het beveiligingscentrum.

>[!NOTE]
>Deze tabel bevat aanmeldingsactiviteiten van Azure Active Directory (AD) die worden bijgeboekt door Cloud App Security, met name interactieve aanmeldingen en verificatieactiviteiten met ActiveSync en andere oudere protocollen. Niet-interactieve aanmeldingen die niet beschikbaar zijn in deze tabel, kunnen worden bekeken in het Auditlogboek van Azure AD. [Meer informatie over het verbinden van Cloud App-beveiliging met Microsoft 365](/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security)

Zie de geavanceerde zoekverwijzing voor meer informatie over andere tabellen in het geavanceerde schema voor [de jacht.](advanced-hunting-schema-tables.md)

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum en tijd waarop de gebeurtenis is opgenomen |
| `ActionType` | tekenreeks | Type activiteit dat de gebeurtenis heeft geactiveerd. Zie de [in-portal schemaverwijzing voor](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) meer informatie |
| `Application` | tekenreeks | Toepassing die de opgenomen actie heeft uitgevoerd |
| `LogonType` | tekenreeks | Type aanmeldingssessie, met name:<br><br> - **Interactief:** gebruiker werkt fysiek met de computer met behulp van het lokale toetsenbord en scherm<br><br> - **RDP-aanmeldingen (Remote Interactive)** - Gebruiker werkt op afstand met de computer met behulp van Extern bureaublad, Terminal Services, Hulp op afstand of andere RDP-clients<br><br> - **Netwerk:** sessie gestart wanneer de computer wordt gebruikt met PsExec of wanneer gedeelde resources op de computer, zoals printers en gedeelde mappen, worden gebruikt<br><br> - **Batch** : sessie die is gestart door geplande taken<br><br> - **Service** - Sessie gestart door services terwijl deze beginnen |
| `Protocol` | tekenreeks | Netwerkprotocol gebruikt |
| `FailureReason` | tekenreeks | Informatie waarin wordt uitgelegd waarom de opgenomen actie is mislukt |
| `AccountName` | tekenreeks | Gebruikersnaam van het account |
| `AccountDomain` | tekenreeks | Domein van het account |
| `AccountUpn` | tekenreeks | Gebruikersnaam (UPN) van het account |
| `AccountSid` | tekenreeks | Beveiligings-id (SID) van het account |
| `AccountObjectId` | tekenreeks | Unieke id voor het account in Azure AD |
| `AccountDisplayName` | tekenreeks | Naam van de accountgebruiker die wordt weergegeven in het adresboek. Meestal een combinatie van een bepaalde of voornaam, een middelste initiatie en een achternaam of achternaam. |
| `DeviceName` | tekenreeks | Volledig gekwalificeerde domeinnaam (FQDN) van het apparaat |
| `DeviceType` | tekenreeks | Type apparaat |
| `OSPlatform` | tekenreeks | Platform van het besturingssysteem dat op de computer wordt uitgevoerd. Dit geeft specifieke besturingssystemen aan, waaronder variaties binnen dezelfde familie, zoals Windows 10 en Windows 7. |
| `IPAddress` | tekenreeks | IP-adres toegewezen aan het eindpunt en gebruikt tijdens gerelateerde netwerkcommunicatie |
| `Port` | tekenreeks | TCP-poort die tijdens communicatie wordt gebruikt |
| `DestinationDeviceName` | tekenreeks | Naam van het apparaat met de servertoepassing die de opgenomen actie heeft verwerkt |
| `DestinationIPAddress` | tekenreeks | IP-adres van het apparaat met de servertoepassing die de opgenomen actie heeft verwerkt |
| `DestinationPort` | tekenreeks | Doelpoort van gerelateerde netwerkcommunicatie |
| `TargetDeviceName` | tekenreeks | Volledig gekwalificeerde domeinnaam (FQDN) van het apparaat waar de opgenomen actie op is toegepast |
| `TargetAccountDisplayName` | tekenreeks | Weergavenaam van het account waar de opgenomen actie op is toegepast |
| `Location` | tekenreeks | Plaats, land of andere geografische locatie die is gekoppeld aan de gebeurtenis |
| `Isp` | tekenreeks | Internetprovider die is gekoppeld aan het IP-adres van het eindpunt |
| `ReportId` | lang | Unieke id voor de gebeurtenis |
| `AdditionalFields` | tekenreeks | Aanvullende informatie over de entiteit of gebeurtenis |

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Opsporen op apparaten en in e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)