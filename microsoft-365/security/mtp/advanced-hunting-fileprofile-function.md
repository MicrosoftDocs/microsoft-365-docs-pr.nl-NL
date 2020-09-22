---
title: FileProfile (), functie in geavanceerde jacht voor Microsoft Threat Protection
description: Meer informatie over het gebruik van de FileProfile () om informatie te verrijken over bestanden in uw geavanceerde zoekresultaten voor de jacht
keywords: geavanceerde jacht, bedreigings jacht, Cyber Threat jacht, Microsoft Threat Protection, Microsoft 365, MTP, m365, Search, query, Telemetry, schema naslag, kusto, FileProfile, bestands profiel, functie, verrijking
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
ms.openlocfilehash: 3fc563c762e7cd00888665b63e66159e4d3d9612
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196975"
---
# <a name="fileprofile"></a>FileProfile()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft Threat Protection

De `FileProfile()` functie is een verrijkings functie in de [geavanceerde jacht](advanced-hunting-overview.md) waarmee de volgende gegevens worden toegevoegd aan bestanden die door de query zijn gevonden.

| Kolom | Gegevenstype | Beschrijving |
|------------|-------------|-------------|
| SHA1 | tekenreeks | SHA-1 van het bestand waarop de opgenomen actie is toegepast |
| SHA256 | tekenreeks | SHA-256 van het bestand waarop de opgenomen actie is toegepast |
| MD5 () | tekenreeks | MD5-hash van het bestand waarop de opgenomen actie is toegepast |
| FileSize | int | Bestandsgrootte in bytes |
| GlobalPrevalence | int | Aantal exemplaren van de entiteit die is waargenomen door Microsoft Global |
| GlobalFirstSeen | tijd | De datum en tijd waarop de entiteit voor het eerst werd gevolgd door Microsoft Global |
| GlobalLastSeen | tijd | De datum en tijd waarop de entiteit voor het laatst is geobserveerd door Microsoft Global |
| Ondertekenaar | tekenreeks | Informatie over de ondertekenaar van het bestand |
| Verstrekker | tekenreeks | Informatie over de uitgevende certificeringsinstantie (CA) |
| SignerHash | tekenreeks | Unieke hash-waarde die de ondertekenaar identificeert |
| IsCertificateValid | Boolean | Opgeven of het certificaat dat wordt gebruikt om het bestand te ondertekenen geldig is |
| IsRootSignerMicrosoft | Boolean | Geeft aan of de ondertekenaar van het basiscertificaat Microsoft is |
| IsExecutable | Boolean | Opgeven of het bestand een bestand is van een Portable Executable (PE) |
| Bedreiging | tekenreeks | Detectie naam voor malware of andere bedreigingen gevonden |
| Publisher | tekenreeks | Naam van de organisatie die het bestand heeft gepubliceerd |
| Softwarenaam | tekenreeks | Naam van het SOFTWAREPRODUCT |

## <a name="syntax"></a>Syntaxis

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a>Argumenten

- **x** — kolom bestand-id voor gebruik: `SHA1` , `SHA256` , `InitiatingProcessSHA1` of `InitiatingProcessSHA256` ; functie gebruikt indien niet `SHA1` opgegeven
- **y** : Beperk het aantal records tot rijk, 1-1000; functie gebruikt 100 indien niet opgegeven

## <a name="examples"></a>Voorbeelden

### <a name="project-only-the-sha1-column-and-enrich-it"></a>Project only the SHA1-kolom en verrijken

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a>De eerste 500 records verrijken en bestanden met lage prevalentie verrijken

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
- [Voorbeelden van meer query](advanced-hunting-shared-queries.md)
