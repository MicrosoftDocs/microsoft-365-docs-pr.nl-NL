---
title: AlertEvidence tabel in het geavanceerde jachtschema
description: Meer informatie over bestands-, netwerkadres-, gebruikers- of apparaatgegevens die zijn gekoppeld aan gegenereerde waarschuwingen in de tabel AlertEvidence van het geavanceerde jachtschema
keywords: geavanceerde jacht, dreigingsjacht, cyberdreigingsjacht, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetrie, schemareferentie, kusto, tabel, kolom, gegevenstype, beschrijving, AlertInfo, alert, entiteiten, bewijs, bestand, IP-adres, apparaat, machine, gebruiker, account
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
ms.openlocfilehash: 1a58d1e5db2ea8689d4909e6e9c47b08a6e94d34
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929148"
---
# <a name="alertevidence"></a>AlertEvidence

**Van toepassing op:**
- Microsoft-bedreigingsbeveiliging

De `AlertEvidence` tabel in het [geavanceerde jachtschema](advanced-hunting-overview.md) bevat informatie over verschillende entiteiten - bestanden, IP-adressen, URL's, gebruikers of apparaten - die zijn gekoppeld aan waarschuwingen van Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security en ATP Azure. Gebruik deze verwijzing om query's te construeren die informatie uit deze tabel retourneren.

Voor informatie over andere tabellen in de geavanceerde jacht schema, [zie de geavanceerde jacht referentie](advanced-hunting-schema-tables.md).

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | Datetime | Datum en tijdstip waarop de gebeurtenis is geregistreerd |
| `AlertId` | Tekenreeks | Unieke id voor de waarschuwing |
| `EntityType` | Tekenreeks | Type object, zoals een bestand, een proces, een apparaat of een gebruiker |
| `EvidenceRole` | Tekenreeks | Hoe de entiteit betrokken is bij een waarschuwing, die aangeeft of deze wordt beïnvloed of slechts gerelateerd is |
| `SHA1` | Tekenreeks | SHA-1 van het bestand waarop de opgenomen actie is toegepast |
| `SHA256` | Tekenreeks | SHA-256 van het bestand waarop de opgenomen actie is toegepast. Dit veld is meestal niet gevuld: gebruik de SHA1-kolom indien beschikbaar. |
| `RemoteIP` | Tekenreeks | IP-adres dat werd verbonden met |
| `RemoteUrl` | Tekenreeks | URL of volledig gekwalificeerde domeinnaam (FQDN) die werd verbonden met |
| `AccountName` | Tekenreeks | Gebruikersnaam van het account |
| `AccountDomain` | Tekenreeks | Domein van het account |
| `AccountSid` | Tekenreeks | Beveiligings-id (SID) van het account |
| `AccountObjectId` | Tekenreeks | Unieke id voor het account in Azure AD |
| `DeviceId` | Tekenreeks | Unieke id voor de machine in de service |
| `ThreatFamily` | Tekenreeks | Malware familie dat de verdachte of kwaadaardige bestand of proces is geclassificeerd onder |
| `EvidenceDirection` | Tekenreeks | Geeft aan of de entiteit de bron of de bestemming van een netwerkverbinding is |
| `AdditionalFields` | Tekenreeks | Aanvullende informatie over de gebeurtenis in JSON-arrayindeling |

## <a name="related-topics"></a>Verwante onderwerpen
- [Proactief op zoek naar bedreigingen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Zoek naar bedreigingen op verschillende apparaten en e-mails](advanced-hunting-query-emails-devices.md)
- [Het schema begrijpen](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
