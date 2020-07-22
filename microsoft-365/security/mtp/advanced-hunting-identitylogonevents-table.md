---
title: IdentityLogonEvents tabel in het geavanceerde jachtschema
description: Meer informatie over verificatiegebeurtenissen die door Active Directory zijn geregistreerd in de tabel IdentityLogonEvents van het geavanceerde jachtschema
keywords: geavanceerde jacht, bedreiging jacht, cyber bedreiging jacht, Microsoft threat protection, Microsoft 365, mtp, m365, zoeken, query, telemetrie, schema referentie, kusto, tabel, kolom, gegevenstype, beschrijving, IdentityLogonEvents, Azure AD, Active Directory, Azure ATP, identiteiten
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
ms.openlocfilehash: 19437caf4f3b0dcb6eb6ccad81d1ed3917df7996
ms.sourcegitcommit: b4119682bd3c036289e851fff56fde869c816479
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/22/2020
ms.locfileid: "45204909"
---
# <a name="identitylogonevents"></a>IdentityLogonEvents

**Van toepassing op:**
- Microsoft Threat Protection

De `IdentityLogonEvents` tabel in het geavanceerde [jachtschema](advanced-hunting-overview.md) bevat informatie over verificatieactiviteiten die zijn gemaakt via uw on-premises Active Directory die is vastgelegd door Azure ATP en verificatieactiviteiten met betrekking tot microsoft onlineservices die zijn vastgelegd door Microsoft Cloud App Security. Gebruik deze verwijzing om query's te construeren die informatie uit deze tabel retourneren.

>[!NOTE]
>Deze tabel bevat aanmeldingsactiviteiten van Azure Active Directory (AD) die worden bijgehouden door Cloud App Security, met name interactieve aanmeldingen en verificatieactiviteiten met Behulp van ActiveSync en andere verouderde protocollen. Niet-interactieve aanmeldingen die niet beschikbaar zijn in deze tabel, kunnen worden weergegeven in het Azure AD-controlelogboek. [Meer informatie over het verbinden van Cloud App Security met Microsoft 365](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security)

Zie [de geavanceerde jachtreferentie](advanced-hunting-schema-tables.md)voor informatie over andere tabellen in het geavanceerde jachtschema.

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | Datetime | Datum en tijdstip waarop de gebeurtenis is geregistreerd |
| `ActionType` | Tekenreeks | Type activiteit dat de gebeurtenis heeft geactiveerd |
| `LogonType` | Tekenreeks | Type aanmeldingssessie, met name:<br><br> - **Interactief** - Gebruiker communiceert fysiek met de machine via het lokale toetsenbord en scherm<br><br> - **Remote interactive (RDP) logons** - Gebruiker communiceert op afstand met de machine met Remote Desktop, Terminal Services, Remote Assistance of andere RDP-clients<br><br> - **Netwerk** - Sessie die wordt gestart wanneer de machine wordt geopend met PsExec of wanneer gedeelde bronnen op de machine, zoals printers en gedeelde mappen, worden geopend<br><br> - **Batch** - Sessie geïnitieerd door geplande taken<br><br> - **Service** - Sessie geïnitieerd door services bij het starten |
| `Application` | Tekenreeks | Toepassing die de opgenomen actie heeft uitgevoerd |
| `Protocol` | Tekenreeks | Netwerkprotocol gebruikt |
| `FailureReason` | Tekenreeks | Informatie waarin wordt uitgelegd waarom de geregistreerde actie is mislukt |
| `AccountName` | Tekenreeks | Gebruikersnaam van het account |
| `AccountDomain` | Tekenreeks | Domein van het account |
| `AccountUpn` | Tekenreeks | Gebruikersnaam (UPN) van het account |
| `AccountSid` | Tekenreeks | Beveiligings-id (SID) van het account |
| `AccountObjectId` | Tekenreeks | Unieke id voor het account in Azure AD |
| `AccountDisplayName` | Tekenreeks | Naam van de accountgebruiker die in het adresboek wordt weergegeven. Typisch een combinatie van een bepaalde of voornaam, een middelste initiatie, en een achternaam of achternaam. |
| `DeviceName` | Tekenreeks | Volledig gekwalificeerde domeinnaam (FQDN) van het apparaat |
| `DeviceType` | Tekenreeks | Type apparaat |
| `OSPlatform` | Tekenreeks | Platform van het besturingssysteem dat op de machine draait. Dit duidt op specifieke besturingssystemen, waaronder variaties binnen dezelfde familie, zoals Windows 10 en Windows 7. |
| `IPAddress` | Tekenreeks | IP-adres toegewezen aan het eindpunt en gebruikt tijdens gerelateerde netwerkcommunicatie |
| `DestinationDeviceName` | Tekenreeks | Naam van het apparaat waarop de servertoepassing wordt uitgevoerd die de geregistreerde actie heeft verwerkt |
| `DestinationIPAddress` | Tekenreeks | IP-adres van het apparaat waarop de servertoepassing wordt uitgevoerd die de geregistreerde actie heeft verwerkt |
| `TargetDeviceName` | Tekenreeks | Volledig gekwalificeerde domeinnaam (FQDN) van het apparaat waarop de geregistreerde actie is toegepast |
| `TargetAccountDisplayName` | Tekenreeks | De naam weergeven van het account waarop de geregistreerde actie is toegepast |
| `Location` | Tekenreeks | Plaats, land of andere geografische locatie die aan het evenement is gekoppeld |
| `Isp` | Tekenreeks | Internetserviceprovider (ISP) die is gekoppeld aan het IP-adres van het eindpunt |
| `ReportId` | Lange | Unieke id voor het evenement |
| `AdditionalFields` | Tekenreeks | Aanvullende informatie over de entiteit of gebeurtenis |

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Zoek naar bedreigingen op verschillende apparaten en e-mails](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)