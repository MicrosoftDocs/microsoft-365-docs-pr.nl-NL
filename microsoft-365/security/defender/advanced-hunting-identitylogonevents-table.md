---
title: IdentityLogonEvents-tabel in het geavanceerde jachtschema
description: Meer informatie over verificatiegebeurtenissen die zijn vastgelegd door Active Directory in de tabel IdentityLogonEvents van het geavanceerde jachtschema
keywords: geavanceerde jacht, bedreigingsjacht, jacht op cyberdreigingen, Microsoft 365 Defender, microsoft 365, m365, zoeken, query, telemetrie, schemaverwijzing, kusto, tabel, kolom, gegevenstype, beschrijving, IdentityLogonEvents, Azure AD, Active Directory, Microsoft Defender for Identity, identiteiten
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
ms.openlocfilehash: 3cd0c0f371c73a515704791e829be7266d400580
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572751"
---
# <a name="identitylogonevents"></a>IdentityLogonEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

De `IdentityLogonEvents` tabel in het geavanceerde [jachtschema](advanced-hunting-overview.md) bevat informatie over verificatieactiviteiten die zijn uitgevoerd via uw on-premises Active Directory die is vastgelegd door Microsoft Defender voor identiteits- en verificatieactiviteiten met betrekking tot onlineservices van Microsoft die zijn vastgelegd door Microsoft Cloud App Security. Gebruik deze verwijzing om query's te maken die informatie uit deze tabel retourneren.

>[!TIP]
> Gebruik de ingebouwde schemaverwijzing die beschikbaar is in het beveiligingscentrum voor gedetailleerde informatie over de gebeurtenistypen `ActionType` (waarden) die door een tabel worden ondersteund.

>[!NOTE]
>Deze tabel bevat Azure Active Directory (Azure AD) aanmeldingsactiviteiten die worden bijgehouden door Cloud App Security, met name interactieve aanmeldingen en verificatieactiviteiten met ActiveSync en andere verouderde protocollen. Niet-interactieve aanmeldingen die niet beschikbaar zijn in deze tabel, kunnen worden weer geven in het Azure AD-controlelogboek. [Meer informatie over het verbinden van Cloud App Security met Microsoft 365](/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security)

Zie [de geavanceerde jachtreferentie](advanced-hunting-schema-tables.md)voor informatie over andere tabellen in het geavanceerde jachtschema.

| Kolomnaam | Gegevenstype | Omschrijving |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum en tijd waarop de gebeurtenis is vastgelegd |
| `ActionType` | snaar | Type activiteit dat de gebeurtenis heeft geactiveerd. Zie de [in-portal schema referentie](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) voor meer informatie |
| `Application` | snaar | Toepassing die de opgenomen actie heeft uitgevoerd |
| `LogonType` | snaar | Type aanmeldingssessie, met name:<br><br> - **Interactief** - Gebruiker communiceert fysiek met de machine met behulp van het lokale toetsenbord en scherm<br><br> - **Rdp-aanmeldingen (Remote Interactive)** - De gebruiker communiceert op afstand met de machine via Extern bureaublad, Terminal Services, Hulp op afstand of andere RDP-clients<br><br> - **Netwerk** - Sessie gestart wanneer de machine wordt geopend met PsExec of wanneer gedeelde bronnen op de computer, zoals printers en gedeelde mappen, worden geopend<br><br> - **Batch** - Sessie gestart door geplande taken<br><br> - **Service** - Sessie geïnitieerd door services wanneer deze worden gestart |
| `Protocol` | snaar | Netwerkprotocol gebruikt |
| `FailureReason` | snaar | Informatie die uitlegt waarom de geregistreerde actie is mislukt |
| `AccountName` | snaar | Gebruikersnaam van het account |
| `AccountDomain` | snaar | Domein van het account |
| `AccountUpn` | snaar | Gebruikersnaam (UPN) van het account |
| `AccountSid` | snaar | Beveiligingsidentificatiecode (SID) van het account |
| `AccountObjectId` | snaar | Unieke id voor het account in Azure AD |
| `AccountDisplayName` | snaar | Naam van de accountgebruiker die in het adresboek wordt weergegeven. Meestal een combinatie van een bepaalde of voornaam, een middelste initiatie en een achternaam of achternaam. |
| `DeviceName` | snaar | Volledig gekwalificeerde domeinnaam (FQDN) van het apparaat |
| `DeviceType` | snaar | Type apparaat |
| `OSPlatform` | snaar | Platform van het besturingssysteem dat op de machine draait. Dit duidt op specifieke besturingssystemen, waaronder variaties binnen dezelfde familie, zoals Windows 10 en Windows 7. |
| `IPAddress` | snaar | IP-adres toegewezen aan het eindpunt en gebruikt tijdens gerelateerde netwerkcommunicatie |
| `Port` | snaar | TCP-poort die wordt gebruikt tijdens communicatie |
| `DestinationDeviceName` | snaar | Naam van het apparaat waarop de servertoepassing wordt uitgevoerd waarmee de opgenomen actie is verwerkt |
| `DestinationIPAddress` | snaar | IP-adres van het apparaat waarop de servertoepassing wordt uitgevoerd die de opgenomen actie heeft verwerkt |
| `DestinationPort` | snaar | Bestemmingshaven van gerelateerde netwerkcommunicatie |
| `TargetDeviceName` | snaar | Volledig gekwalificeerde domeinnaam (FQDN) van het apparaat waarop de geregistreerde actie is toegepast |
| `TargetAccountDisplayName` | snaar | Naam weergeven van de rekening waarop de geregistreerde actie is toegepast |
| `Location` | snaar | Plaats, land of andere geografische locatie die aan het evenement is gekoppeld |
| `Isp` | snaar | Internetprovider (ISP) gekoppeld aan het IP-adres van het eindpunt |
| `ReportId` | lang | Unieke id voor de gebeurtenis |
| `AdditionalFields` | snaar | Aanvullende informatie over de entiteit of gebeurtenis |

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Opsporen op apparaten en in e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)