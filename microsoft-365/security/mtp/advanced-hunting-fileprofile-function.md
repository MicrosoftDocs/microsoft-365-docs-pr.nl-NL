---
title: FileProfile() functie in geavanceerde jacht op Microsoft Threat Protection
description: Meer informatie over het gebruik van de FileProfile() om informatie over bestanden te verrijken in uw geavanceerde resultaten voor jachtquery's
keywords: geavanceerde jacht, bedreiging jacht, cyber bedreiging jacht, Microsoft threat protection, Microsoft 365, mtp, m365, zoeken, query, telemetrie, schema referentie, kusto, FileProfile, bestandsprofiel, functie, verrijking
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
ms.openlocfilehash: 6465821ff1b8e8ea23cc5cf6b205f65a483bbe82
ms.sourcegitcommit: b4119682bd3c036289e851fff56fde869c816479
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/22/2020
ms.locfileid: "45204945"
---
# <a name="fileprofile"></a>FileProfile()

**Van toepassing op:**
- Microsoft Threat Protection

De `FileProfile()` functie is een verrijkingsfunctie in geavanceerde [jacht](advanced-hunting-overview.md) die de volgende gegevens toevoegt aan bestanden die door de query worden gevonden.

| Kolom | Gegevenstype | Beschrijving |
|------------|-------------|-------------|
| SHA1 SHA1 | Tekenreeks | SHA-1 van het bestand waarop de geregistreerde actie is toegepast |
| SHA256 SHA256 | Tekenreeks | SHA-256 van het bestand waarop de geregistreerde actie is toegepast |
| MD5 MD5 | Tekenreeks | MD5-hash van het bestand waarop de geregistreerde actie is toegepast |
| Bestandsgrootte | Int | Grootte van het bestand in bytes |
| GlobalPrevalence | Int | Aantal exemplaren van de entiteit die wereldwijd door Microsoft wordt waargenomen |
| GlobalFirstSeen | Datetime | Datum en tijd waarop de entiteit wereldwijd voor het eerst werd waargenomen door Microsoft |
| GlobalLastSeen | Datetime | Datum en tijd waarop de entiteit wereldwijd voor het laatst door Microsoft is waargenomen |
| Ondertekenaar | Tekenreeks | Informatie over de ondertekenaar van het bestand |
| Uitgevende instelling | Tekenreeks | Informatie over de instantie van afgiftecertificaat (CA) |
| OndertekenaarHash | Tekenreeks | Unieke hashwaarde die de ondertekenaar identificeert |
| IsCertificateValid | Booleaanse | Of het certificaat dat wordt gebruikt om het bestand te ondertekenen geldig is |
| IsRootSignerMicrosoft IsRootSignerMicrosoft | Booleaanse | Geeft aan of de ondertekenaar van het basiscertificaat Microsoft is |
| IsExecutable | Booleaanse | Of het bestand een PE-bestand (Portable Executable) is |
| ThreatName ThreatName | Tekenreeks | Detectienaam voor malware of andere bedreigingen gevonden |
| Publisher | Tekenreeks | Naam van de organisatie die het bestand heeft gepubliceerd |
| SoftwareName | Tekenreeks | Naam van het softwareproduct |

## <a name="syntax"></a>Syntaxis

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a>Argumenten

- **x** — kolom bestands-id om te gebruiken: `SHA1` , , of , functie gebruikt als `SHA256` `InitiatingProcessSHA1` `InitiatingProcessSHA256` `SHA1` niet-gespecificeerd
- **y** — beperking van het aantal records om te verrijken, 1-1000; functie gebruikt 100 als niet-gespecificeerd

## <a name="examples"></a>Voorbeelden

### <a name="project-only-the-sha1-column-and-enrich-it"></a>Projecteer alleen de SHA1-kolom en verrijk deze

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a>De eerste 500 records verrijken en lage prevalentiebestanden aanbieden

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