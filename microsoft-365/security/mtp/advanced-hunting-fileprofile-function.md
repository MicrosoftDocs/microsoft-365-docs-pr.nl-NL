---
title: FileProfile() in geavanceerd zoeken naar Microsoft 365 Defender
description: Informatie over het gebruik van FileProfile() voor het verbeteren van informatie over bestanden in uw geavanceerde queryresultaten
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, FileProfile, file profile, function, enrichment
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
ms.openlocfilehash: 68196f126ac470088d7ba5e2923accc492d8764c
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929548"
---
# <a name="fileprofile"></a>FileProfile()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

De `FileProfile()` functie is een verrijkingsfunctie in geavanceerde [zoekopdrachten](advanced-hunting-overview.md) die de volgende gegevens toevoegt aan bestanden die met de query worden gevonden.

| Kolom | Gegevenstype | Beschrijving |
|------------|-------------|-------------|
| SHA1 | tekenreeks | SHA-1 van het bestand waar de opgenomen actie op is toegepast |
| SHA256 | tekenreeks | SHA-256 van het bestand waar de opgenomen actie op is toegepast |
| MD5 | tekenreeks | MD5-hash van het bestand waar de opgenomen actie op is toegepast |
| FileSize | int | Grootte van het bestand in bytes |
| GlobalPrevalence | int | Aantal instanties van de entiteit die wereldwijd door Microsoft wordt waargenomen |
| GlobalFirstSeen | datetime | Datum en tijd waarop de entiteit voor het eerst door Microsoft globaal is waargenomen |
| GlobalLastSeen | datetime | Datum en tijd waarop de entiteit voor het laatst door Microsoft wereldwijd is waargenomen |
| Ondertekenaar | tekenreeks | Informatie over de ondertekenaar van het bestand |
| Gever | tekenreeks | Informatie over de certificeringsinstantie (CA) |
| SignerHash | tekenreeks | Unieke hashwaarde die de ondertekenaar identificeert |
| IsCertificateValid | boolean | Of het certificaat waarmee het bestand is ondertekenen, geldig is |
| IsRootSignerMicrosoft | boolean | Hiermee wordt aangegeven of Microsoft de ondertekenaar van het basiscertificaat is |
| IsExecutable | boolean | Of het bestand een PE-bestand (Portable Executable) is |
| ThreatName | tekenreeks | Naam van detectie voor malware of andere bedreigingen gevonden |
| Publisher | tekenreeks | Naam van de organisatie die het bestand heeft gepubliceerd |
| SoftwareName | tekenreeks | Naam van het softwareproduct |

## <a name="syntax"></a>Syntaxis

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a>Argumenten

- **x**—kolom bestands-id voor gebruik: , , of ; functie gebruikt `SHA1` `SHA256` indien niet `InitiatingProcessSHA1` `InitiatingProcessSHA256` `SHA1` gespecificeerd
- **y:** beperk het aantal records dat u wilt verrijken, 1-1000; de functie gebruikt 100 indien niet gespecificeerd

## <a name="examples"></a>Voorbeelden

### <a name="project-only-the-sha1-column-and-enrich-it"></a>Alleen de kolom SHA1 projecten en deze verrijken

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a>De eerste 500 records verrijken en bestanden met weinig bestanden in een lijst zetten

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
- [Meer queryvoorbeelden bekijken](advanced-hunting-shared-queries.md)
