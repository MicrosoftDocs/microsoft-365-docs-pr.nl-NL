---
title: AlertEvidence tabel in het geavanceerde jachtschema
description: Meer informatie over bestands-, netwerkadres-, gebruikers- of apparaatgegevens die zijn gekoppeld aan gegenereerde waarschuwingen in de tabel AlertEvidence van het geavanceerde jachtschema
keywords: geavanceerde jacht, bedreiging jacht, cyber bedreiging jacht, Microsoft threat protection, Microsoft 365, mtp, m365, zoeken, query, telemetrie, schema referentie, kusto, tabel, kolom, gegevenstype, beschrijving, AlertInfo, alert, entiteiten, bewijs, bestand, IP-adres, apparaat, machine, gebruiker, account
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
ms.openlocfilehash: a0f2ae36752a4415da7c1bc39ce35bd7f744a764
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899349"
---
# <a name="alertevidence"></a>AlertEvidence

**Van toepassing op:**
- Microsoft Threat Protection

De `AlertEvidence` tabel in het geavanceerde [jachtschema](advanced-hunting-overview.md) bevat informatie over verschillende entiteiten — bestanden, IP-adressen, URL's, gebruikers of apparaten — die zijn gekoppeld aan waarschuwingen van Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security en Azure ATP. Gebruik deze verwijzing om query's te construeren die informatie uit deze tabel retourneren.

Zie [de geavanceerde jachtreferentie](advanced-hunting-schema-tables.md)voor informatie over andere tabellen in het geavanceerde jachtschema.

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | Datetime | Datum en tijdstip waarop de gebeurtenis is geregistreerd |
| `AlertId` | Tekenreeks | Unieke id voor de waarschuwing |
| `EntityType` | Tekenreeks | Type object, zoals een bestand, een proces, een apparaat of een gebruiker |
| `EvidenceRole` | Tekenreeks | Hoe de entiteit betrokken is bij een waarschuwing, die aangeeft of deze is beïnvloed of alleen |
| `SHA1` | Tekenreeks | SHA-1 van het bestand waarop de geregistreerde actie is toegepast |
| `SHA256` | Tekenreeks | SHA-256 van het bestand waarop de geregistreerde actie is toegepast. Dit veld wordt meestal niet ingevuld - gebruik de SHA1-kolom indien beschikbaar. |
| `RemoteIP` | Tekenreeks | IP-adres waarmee werd verbonden |
| `RemoteUrl` | Tekenreeks | URL of volledig gekwalificeerde domeinnaam (FQDN) die werd verbonden met |
| `AccountName` | Tekenreeks | Gebruikersnaam van het account |
| `AccountDomain` | Tekenreeks | Domein van het account |
| `AccountSid` | Tekenreeks | Beveiligings-id (SID) van het account |
| `AccountObjectId` | Tekenreeks | Unieke id voor het account in Azure AD |
| `DeviceId` | Tekenreeks | Unieke id voor de machine in de service |
| `ThreatFamily` | Tekenreeks | Malwarefamilie waar het verdachte of kwaadwillige bestand of proces onder is ingedeeld |
| `EvidenceDirection` | Tekenreeks | Geeft aan of de entiteit de bron of de bestemming van een netwerkverbinding is |
| `AdditionalFields` | Tekenreeks | Aanvullende informatie over de gebeurtenis in de JSON-arrayindeling |

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Zoek naar bedreigingen op verschillende apparaten en e-mails](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
