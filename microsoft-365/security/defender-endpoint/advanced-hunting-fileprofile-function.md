---
title: FileProfile() functie in advanced hunting for Microsoft Defender for Endpoint
description: Meer informatie over het gebruik van FileProfile() om informatie over bestanden in de geavanceerde resultaten van de query te verrijken
keywords: advanced hunting, threat hunting, cyber threat hunting, mdatp, Microsoft Defender ATP, Microsoft Defender for Endpoint, Windows Defender, Windows Defender ATP, Windows Defender Advanced Threat Protection, search, query, telemetry, schema reference, kusto, FileProfile, file profile, function, enrichment
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 09/20/2020
ms.technology: mde
ms.openlocfilehash: 668b3fe503268c46e4a1313f0c4cfb8a6a3dd602
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060246"
---
# <a name="fileprofile"></a>FileProfile()

**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

De `FileProfile()` functie is een verrijkingsfunctie in geavanceerde [zoekopdrachten](advanced-hunting-overview.md) die de volgende gegevens toevoegt aan bestanden die door de query worden gevonden.

Kolom | Gegevenstype | Beschrijving
-|-|-
SHA1 | tekenreeks | SHA-1 van het bestand waar de opgenomen actie op is toegepast
SHA256 | tekenreeks | SHA-256 van het bestand waar de opgenomen actie op is toegepast
MD5 | tekenreeks | MD5-hash van het bestand waar de opgenomen actie op is toegepast
Bestandsgrootte | int | Grootte van het bestand in bytes
GlobalPrevalence | int | Aantal exemplaren van de entiteit die wereldwijd door Microsoft is waargenomen
GlobalFirstSeen | datetime | Datum en tijd waarop de entiteit voor het eerst wereldwijd door Microsoft is waargenomen
GlobalLastSeen | datetime | Datum en tijd waarop de entiteit voor het laatst wereldwijd is waargenomen door Microsoft
Ondertekenaar | tekenreeks | Informatie over de ondertekenaar van het bestand
Uitgevende gever | tekenreeks | Informatie over de certificeringsinstantie voor afgifte (CA)
SignerHash | tekenreeks | Unieke hashwaarde die de ondertekenaar identificeert
IsCertificateValid | booleaanse | Of het certificaat dat wordt gebruikt om het bestand te ondertekenen geldig is
IsRootSignerMicrosoft | booleaanse | Geeft aan of de ondertekenaar van het hoofdcertificaat Microsoft is
IsExecutable | booleaanse | Of het bestand een PE-bestand (Portable Executable) is
ThreatName | tekenreeks | Detectienaam voor malware of andere gevonden bedreigingen
Publisher | tekenreeks | Naam van de organisatie die het bestand heeft gepubliceerd
SoftwareName | tekenreeks | Naam van het softwareproduct

## <a name="syntax"></a>Syntaxis

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a>Argumenten

- **x** : kolom `SHA1` `SHA256` `InitiatingProcessSHA1` `InitiatingProcessSHA256` `SHA1` bestands-id die u wilt gebruiken: , of ; functie gebruikt indien niet gespecificeerd
- **y:** limiet voor het aantal records dat moet worden verrijken, 1-1000; functie gebruikt 100 als niet-gespecificeerd

## <a name="examples"></a>Voorbeelden

### <a name="project-only-the-sha1-column-and-enrich-it"></a>Project alleen de kolom SHA1 en verrijk deze

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
- [Meer informatie over het schema](advanced-hunting-schema-reference.md)
