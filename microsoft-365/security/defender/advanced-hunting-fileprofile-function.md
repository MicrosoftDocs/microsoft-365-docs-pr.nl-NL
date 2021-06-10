---
title: FileProfile() functie in advanced hunting for Microsoft 365 Defender
description: Meer informatie over het gebruik van FileProfile() om informatie over bestanden in de geavanceerde resultaten van de query te verrijken
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, FileProfile, file profile, function, enrichment
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
ms.openlocfilehash: 67295529cdb7b8a3e93e663f2a8a28d27a8f6737
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935843"
---
# <a name="fileprofile"></a>FileProfile()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

De `FileProfile()` functie is een verrijkingsfunctie in geavanceerde [zoekopdrachten](advanced-hunting-overview.md) die de volgende gegevens toevoegt aan bestanden die door de query worden gevonden.

| Kolom | Gegevenstype | Beschrijving |
|------------|---------------|-------------|
| `SHA1` | tekenreeks | SHA-1 van het bestand waar de opgenomen actie op is toegepast |
| `SHA256` | tekenreeks | SHA-256 van het bestand waar de opgenomen actie op is toegepast |
| `MD5` | tekenreeks | MD5-hash van het bestand waar de opgenomen actie op is toegepast |
| `FileSize` | int | Grootte van het bestand in bytes |
| `GlobalPrevalence` | int | Aantal exemplaren van de entiteit die wereldwijd door Microsoft is waargenomen |
| `GlobalFirstSeen` | datetime | Datum en tijd waarop de entiteit voor het eerst wereldwijd door Microsoft is waargenomen |
| `GlobalLastSeen` | datetime | Datum en tijd waarop de entiteit voor het laatst wereldwijd is waargenomen door Microsoft |
| `Signer` | tekenreeks | Informatie over de ondertekenaar van het bestand |
| `Issuer` | tekenreeks | Informatie over de certificeringsinstantie voor afgifte (CA) |
| `SignerHash` | tekenreeks | Unieke hashwaarde die de ondertekenaar identificeert |
| `IsCertificateValid` | booleaanse | Of het certificaat dat wordt gebruikt om het bestand te ondertekenen geldig is |
| `IsRootSignerMicrosoft` | booleaanse | Geeft aan of de ondertekenaar van het hoofdcertificaat Microsoft is |
| `SignatureState` | tekenreeks | Status van de bestandshandtekening: SignedValid - het bestand is ondertekend met een geldige handtekening, SignedInvalid - het bestand is ondertekend, maar het certificaat is ongeldig, Niet ondertekend - het bestand is niet ondertekend, Onbekend - informatie over het bestand kan niet worden opgehaald
| `IsExecutable` | booleaanse | Of het bestand een PE-bestand (Portable Executable) is |
| `ThreatName` | tekenreeks | Detectienaam voor malware of andere gevonden bedreigingen |
| `Publisher` | tekenreeks | Naam van de organisatie die het bestand heeft gepubliceerd |
| `SoftwareName` | tekenreeks | Naam van het softwareproduct |

## <a name="syntax"></a>Syntaxis

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a>Argumenten

- **x**-kolom `SHA1` `SHA256` `InitiatingProcessSHA1` `InitiatingProcessSHA256` `SHA1` bestands-id voor gebruik: , , of ; functie gebruikt indien niet gespecificeerd
- **y**: limiet voor het aantal records dat moet worden verrijken, 1-1000; functie gebruikt 100 als niet-gespecificeerd


>[!TIP]
> Verrijkingsfuncties bevatten alleen aanvullende informatie wanneer ze beschikbaar zijn. De beschikbaarheid van informatie is gevarieerd en is afhankelijk van een groot aantal factoren. Houd hier rekening mee bij het gebruik van FileProfile() in uw query's of bij het maken van aangepaste detecties. Voor de beste resultaten wordt u aangeraden de functie FileProfile() te gebruiken met SHA1.

## <a name="examples"></a>Voorbeelden

### <a name="project-only-the-sha1-column-and-enrich-it"></a>Project alleen de kolom SHA1 en verrijken deze

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a>Verrijk de eerste 500 records en vermeld bestanden met lage prevalentie

```kusto
DeviceFileEvents
| where ActionType == "FileCreated" and Timestamp > ago(1d)
| project CreatedOn = Timestamp, FileName, FolderPath, SHA1
| invoke FileProfile("SHA1", 500) 
| where GlobalPrevalence < 15
```

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Meer queryvoorbeelden](advanced-hunting-shared-queries.md)
