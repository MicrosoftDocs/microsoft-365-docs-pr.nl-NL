---
title: IdentityLogonEvents-tabel in het geavanceerde jacht schema
description: Meer informatie over verificatiegebeurtenissen die zijn opgenomen in Active Directory in de tabel IdentityLogonEvents van het schema geavanceerde jacht
keywords: geavanceerde jacht, bedreigings jacht, Cyber Threat jacht, Microsoft Threat Protection, Microsoft 365, MTP, m365, Search, query, Telemetry, schema naslag, kusto, tabel, kolom, gegevenstype, beschrijving, IdentityLogonEvents, Azure AD, Active Directory, Azure ATP, Identities
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
ms.openlocfilehash: aec5bf5dfe29dd55bf5e5df471126db46fdfcb4c
ms.sourcegitcommit: 51097b18d94da20aa727ebfbeb6ec84c263b25c3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/12/2020
ms.locfileid: "46648825"
---
# <a name="identitylogonevents"></a>IdentityLogonEvents

**Van toepassing op:**
- Microsoft Threat Protection

De `IdentityLogonEvents` tabel in het [Geavanceerde](advanced-hunting-overview.md) begeleidings schema bevat informatie over verificatie activiteiten die zijn gemaakt via uw on-premises Active Directory, vastgelegd door Azure ATP en authenticatie activiteiten met betrekking tot Microsoft Online-Services die zijn vastgelegd via beveiliging van de Microsoft Cloud-app. Gebruik deze verwijzing voor het maken van query's waarmee informatie uit deze tabel wordt geretourneerd.

>[!NOTE]
>Deze tabel bevat een overzicht van de aanmeldings activiteiten van Azure Active Directory (AD) die worden bijgehouden door de beveiliging van Cloud apps, specifiek voor interactieve aanmelding en verificatie activiteiten met behulp van ActiveSync en andere oudere protocollen. Niet-interactieve aanmeldingen die niet beschikbaar zijn in deze tabel, kunnen worden weergegeven in het Azure AD auditlogboek. [Meer informatie over het verbinden van de beveiliging van de Cloud-app met Microsoft 365](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security)

Zie voor meer informatie over andere tabellen in het geavanceerde jacht-schema [de Naslaggids voor Geavanceerd](advanced-hunting-schema-tables.md)zoeken.

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | tijd | De datum en tijd waarop de gebeurtenis is vastgelegd |
| `ActionType` | tekenreeks | Type activiteit waarmee de gebeurtenis wordt geactiveerd |
| `LogonType` | tekenreeks | Type aanmeldingssessie, met name:<br><br> - **Interactieve** gebruiker werkt fysiek samen met de computer met het lokale toetsenbord en scherm<br><br> - **Externe interactieve (RDP) aanmeldinging** -gebruikers onderlinge interactie met de computer met behulp van extern bureaublad, Terminal Services, hulp op afstand of andere RDP-clients<br><br> - **Netwerk** -sessie gestart wanneer de computer wordt geopend met behulp van PsExec of wanneer gedeelde bronnen op de computer, zoals printers en gedeelde mappen, worden geopend<br><br> - **Batch** -sessie geïnitieerd door geplande taken<br><br> - **Service** -sessie gestart door een service als deze wordt gestart |
| `Application` | tekenreeks | De toepassing die de opgenomen actie heeft uitgevoerd |
| `Protocol` | tekenreeks | Gebruikte netwerkprotocollen |
| `FailureReason` | tekenreeks | Informatie over waarom de opgenomen actie is mislukt |
| `AccountName` | tekenreeks | Gebruikersnaam van het account |
| `AccountDomain` | tekenreeks | Domein van het account |
| `AccountUpn` | tekenreeks | UPN (User Principal Name) van het account |
| `AccountSid` | tekenreeks | SID (Security Identifier) van het account |
| `AccountObjectId` | tekenreeks | Unieke id voor het account in azure AD |
| `AccountDisplayName` | tekenreeks | Naam van de account gebruiker die in het adresboek wordt weergegeven. Meestal een combinatie van een bepaalde of voornaam, een tweede opening en een achternaam of achternaam. |
| `DeviceName` | tekenreeks | FQDN (Fully Qualified Domain Name) van het apparaat |
| `DeviceType` | tekenreeks | Type apparaat |
| `OSPlatform` | tekenreeks | Platform van het besturingssysteem dat op de computer wordt uitgevoerd. Dit geeft specifieke besturingssystemen aan, met inbegrip van variaties in dezelfde familie, zoals Windows 10 en Windows 7. |
| `IPAddress` | tekenreeks | Het IP-adres dat is toegewezen aan het eindpunt en die wordt gebruikt tijdens gerelateerde netwerkcommunicatie |
| `DestinationDeviceName` | tekenreeks | Naam van het apparaat waarop de servertoepassing wordt uitgevoerd die de opgenomen actie heeft verwerkt |
| `DestinationIPAddress` | tekenreeks | IP-adres van het apparaat waarop de servertoepassing wordt uitgevoerd die de opgenomen actie heeft verwerkt |
| `TargetDeviceName` | tekenreeks | FQDN-naam (Fully Qualified Domain Name) van het apparaat waarop de opgenomen actie is toegepast |
| `TargetAccountDisplayName` | tekenreeks | Weergavenaam van het account waarop de opgenomen actie is toegepast |
| `Location` | tekenreeks | Plaats, land of andere geografische locatie die is gekoppeld aan de gebeurtenis |
| `Isp` | tekenreeks | Internetprovider (ISP) die is gekoppeld aan het IP-adres van het eindpunt |
| `ReportId` | lang | Unieke id voor de gebeurtenis |
| `AdditionalFields` | tekenreeks | Aanvullende informatie over de entiteit of gebeurtenis |

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Jacht op apparaten, e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)