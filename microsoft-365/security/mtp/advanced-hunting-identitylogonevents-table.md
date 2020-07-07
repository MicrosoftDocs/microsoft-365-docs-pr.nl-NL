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
ms.openlocfilehash: 2116d8f6f1006f5acf9d468006fa07a04e13087b
ms.sourcegitcommit: 11218af1d792af297b4280ca5975d139d2bbe350
ms.contentlocale: nl-NL
ms.lasthandoff: 07/06/2020
ms.locfileid: "45046026"
---
# <a name="identitylogonevents"></a>IdentityLogonEvents

**Van toepassing op:**
- Microsoft Threat Protection

De `IdentityLogonEvents` tabel in het geavanceerde [jachtschema](advanced-hunting-overview.md) bevat informatie over verificatieactiviteiten die zijn gemaakt via uw on-premises Active Directory die is vastgelegd door Azure ATP en verificatieactiviteiten met betrekking tot microsoft onlineservices die zijn vastgelegd door Microsoft Cloud App Security. Gebruik deze verwijzing om query's te construeren die informatie uit deze tabel retourneren.

Zie [de geavanceerde jachtreferentie](advanced-hunting-schema-tables.md)voor informatie over andere tabellen in het geavanceerde jachtschema.

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | Datetime | Datum en tijdstip waarop de gebeurtenis is geregistreerd |
| `ActionType` | Tekenreeks | Type activiteit dat de gebeurtenis heeft geactiveerd |
| `LogonType` | Tekenreeks | Type aanmeldingssessie, met name:<br><br> - **Interactief** - Gebruiker communiceert fysiek met de machine via het lokale toetsenbord en scherm<br><br> - **Remote interactive (RDP) logons** - Gebruiker communiceert op afstand met de machine met Remote Desktop, Terminal Services, Remote Assistance of andere RDP-clients<br><br> - **Netwerk** - Sessie die wordt gestart wanneer de machine wordt geopend met PsExec of wanneer gedeelde bronnen op de machine, zoals printers en gedeelde mappen, worden geopend<br><br> - **Batch** - Sessie geïnitieerd door geplande taken<br><br> - **Service** - Sessie geïnitieerd door services bij het starten |
| `Application` | Tekenreeks | Toepassing die de opgenomen actie heeft uitgevoerd |
| `Protocol` | Tekenreeks | Protocol dat tijdens de communicatie wordt gebruikt |
| `AccountName` | Tekenreeks | Gebruikersnaam van het account |
| `AccountDomain` | Tekenreeks | Domein van het account |
| `AccountUpn` | Tekenreeks | Gebruikersnaam (UPN) van het account |
| `AccountSid` | Tekenreeks | Beveiligings-id (SID) van het account |
| `AccountObjectId` | Tekenreeks | Unieke id voor het account in Azure AD |
| `AccountDisplayName` | Tekenreeks | Naam van de accountgebruiker die in het adresboek wordt weergegeven. Typisch een combinatie van een bepaalde of voornaam, een middelste initiatie, en een achternaam of achternaam. |
| `DeviceName` | Tekenreeks | Volledig gekwalificeerde domeinnaam (FQDN) van de machine |
| `DeviceType` | Tekenreeks | Type apparaat |
| `OSPlatform` | Tekenreeks | Platform van het besturingssysteem dat op de machine draait. Dit duidt op specifieke besturingssystemen, waaronder variaties binnen dezelfde familie, zoals Windows 10 en Windows 7. |
| `IPAddress` | Tekenreeks | IP-adres toegewezen aan het eindpunt en gebruikt tijdens gerelateerde netwerkcommunicatie |
| `Location` | Tekenreeks | Plaats, land of andere geografische locatie die aan het evenement is gekoppeld |
| `Isp` | Tekenreeks | Internetserviceprovider (ISP) die is gekoppeld aan het IP-adres van het eindpunt |

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Zoek naar bedreigingen op verschillende apparaten en e-mails](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
