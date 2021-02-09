---
title: Tabel IdentityLogonEvents in het geavanceerde schema voor zoeken
description: Meer informatie over verificatiegebeurtenissen die zijn vastgelegd door Active Directory in de tabel IdentityLogonEvents van het geavanceerde schema voor zoeken
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, IdentityLogonEvents, Azure AD, Active Directory, Azure ATP, identities
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
ms.openlocfilehash: 87ac6194374e8e042cf9d00271b17dd8bb785d64
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145347"
---
# <a name="identitylogonevents"></a>IdentityLogonEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

De tabel in het geavanceerde zoekschema bevat informatie over verificatieactiviteiten die zijn gemaakt via uw on-premises Active Directory en zijn vastgelegd door Microsoft Defender voor identiteits- en verificatieactiviteiten met betrekking tot Microsoft-onlineservices die zijn vastgelegd door `IdentityLogonEvents` Microsoft Cloud App Security. [](advanced-hunting-overview.md) Gebruik deze verwijzing om query's te maken die gegevens uit deze tabel retourneren.

>[!TIP]
> Voor gedetailleerde informatie over de gebeurtenistypen (waarden) die door een tabel worden ondersteund, gebruikt u de `ActionType` [ingebouwde schemaverwijzing in](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) het beveiligingscentrum.

>[!NOTE]
>In deze tabel worden aanmeldingsactiviteiten van Azure Active Directory (AD) beslaat die worden bijgeslagen door Cloud App Security, met name interactieve aanmeldingen en verificatieactiviteiten met behulp van ActiveSync en andere oudere protocollen. Niet-interactieve aanmeldingen die niet beschikbaar zijn in deze tabel, kunnen worden bekeken in het Azure AD-auditlogboek. [Meer informatie over het verbinden van Cloud App Security met Microsoft 365](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security)

Zie het geavanceerde zoekschema voor meer informatie over andere tabellen in het geavanceerde schema [voor zoeken.](advanced-hunting-schema-tables.md)

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum en tijd waarop de gebeurtenis is vastgelegd |
| `ActionType` | tekenreeks | Het type activiteit dat de gebeurtenis heeft geactiveerd. Zie de [schemaverwijzing in de portal](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) voor meer informatie |
| `LogonType` | tekenreeks | Het type aanmeldingssessie, met name:<br><br> - **Interactief:** de gebruiker werkt fysiek met de computer via het lokale toetsenbord en scherm<br><br> - **Externe interactieve aanmeldingsservices (RDP),** de gebruiker werkt op afstand met de computer via Extern bureaublad, Terminal Services, Hulp op afstand of andere RDP-clients<br><br> - **Netwerk:** de sessie wordt gestart wanneer de computer wordt gebruikt met PsExec of wanneer gedeelde bronnen op de computer, zoals printers en gedeelde mappen, worden gebruikt<br><br> - **Batch:** sessie gestart door geplande taken<br><br> - **Service:** een sessie gestart door services terwijl ze beginnen |
| `Application` | tekenreeks | Toepassing die de opgenomen actie heeft uitgevoerd |
| `Protocol` | tekenreeks | Netwerkprotocol gebruikt |
| `FailureReason` | tekenreeks | Informatie waarin wordt uitgelegd waarom de opgenomen actie is mislukt |
| `AccountName` | tekenreeks | Gebruikersnaam van het account |
| `AccountDomain` | tekenreeks | Domein van het account |
| `AccountUpn` | tekenreeks | UPN (User Principal Name) van het account |
| `AccountSid` | tekenreeks | Security Identifier (SID) van het account |
| `AccountObjectId` | tekenreeks | Unieke id voor het account in Azure AD |
| `AccountDisplayName` | tekenreeks | De naam van de accountgebruiker die wordt weergegeven in het adresboek. Meestal een combinatie van een bepaalde of voornaam, een middelste start en een achternaam of achternaam. |
| `DeviceName` | tekenreeks | FQDN (Fully Qualified Domain Name) van het apparaat |
| `DeviceType` | tekenreeks | Type apparaat |
| `OSPlatform` | tekenreeks | Platform van het besturingssysteem dat op de computer wordt uitgevoerd. Dit geeft specifieke besturingssystemen aan, inclusief variaties binnen dezelfde familie, zoals Windows 10 en Windows 7. |
| `IPAddress` | tekenreeks | IP-adres dat aan het eindpunt is toegewezen en dat is gebruikt tijdens gerelateerde netwerkcommunicatie |
| `Port` | tekenreeks | TCP-poort gebruikt tijdens communicatie |
| `DestinationDeviceName` | tekenreeks | Naam van het apparaat met de servertoepassing die de opgenomen actie heeft verwerkt |
| `DestinationIPAddress` | tekenreeks | Het IP-adres van het apparaat met de servertoepassing dat de opgenomen actie heeft verwerkt |
| `DestinationPort` | tekenreeks | Bestemmingspoort van gerelateerde netwerkcommunicatie |
| `TargetDeviceName` | tekenreeks | FQDN (Fully Qualified Domain Name) van het apparaat waar de opgenomen actie op is toegepast |
| `TargetAccountDisplayName` | tekenreeks | Weergavenaam van het account waar de opgenomen actie op is toegepast |
| `Location` | tekenreeks | Plaats, land of andere geografische locatie die is gekoppeld aan de gebeurtenis |
| `Isp` | tekenreeks | Internetprovider (ISP) die is gekoppeld aan het IP-adres van het eindpunt |
| `ReportId` | lang | Unieke id voor de gebeurtenis |
| `AdditionalFields` | tekenreeks | Aanvullende informatie over de entiteit of gebeurtenis |

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Opsporen op apparaten en in e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
