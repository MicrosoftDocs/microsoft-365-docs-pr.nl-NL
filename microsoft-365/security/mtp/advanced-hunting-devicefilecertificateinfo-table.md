---
title: DeviceFileCertificateInfo-tabel in het geavanceerde schema voor zoeken
description: Meer informatie over bestands ondertekeningsgegevens in de tabel DeviceFileCertificateInfo van het geavanceerde schema voor zoeken
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, digital signature, certificate, file signing, DeviceFileCertificateInfo
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
ms.openlocfilehash: e35e8e86f6814a5f90a7921f71ccab7247fcc1bc
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931312"
---
# <a name="devicefilecertificateinfo"></a>DeviceFileCertificateInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

De `DeviceFileCertificateInfo` tabel in het geavanceerde schema voor [zoeken](advanced-hunting-overview.md) bevat informatie over certificaten voor bestands ondertekening. In deze tabel worden gegevens gebruikt die zijn verkregen uit verificatieactiviteiten van certificaten die regelmatig worden uitgevoerd voor bestanden op eindpunten.

Zie het geavanceerde zoekschema voor meer informatie over andere tabellen in het geavanceerde schema [voor zoeken.](advanced-hunting-schema-tables.md)

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum en tijd waarop de gebeurtenis is vastgelegd |
| `DeviceId` | tekenreeks | Unieke id voor de computer in de service |
| `DeviceName` | tekenreeks | FQDN (Fully Qualified Domain Name) van de computer |
| `SHA1` | tekenreeks | SHA-1 van het bestand waar de opgenomen actie op is toegepast |
| `IsSigned` | boolean | Hiermee wordt aangegeven of het bestand is ondertekend |
| `SignatureType` | tekenreeks | Geeft aan of handtekeninginformatie is gelezen als ingesloten inhoud in het bestand zelf of is gelezen vanuit een extern catalogusbestand |
| `Signer` | tekenreeks | Informatie over de ondertekenaar van het bestand |
| `SignerHash` | tekenreeks | Unieke hashwaarde die de ondertekenaar identificeert |
| `Issuer` | tekenreeks | Informatie over de certificeringsinstantie (CA) |
| `IssuerHash` | tekenreeks | Unieke hashwaarde identificerende certificeringsinstantie (CA) |
| `CertificateSerialNumber` | tekenreeks | Id voor het certificaat dat uniek is voor de certificeringsinstantie (CA) |
| `CrlDistributionPointUrls` | tekenreeks |  JSON-matrix met de URL's van netwerk shares die certificaten en certificaatverroepingslijsten (CRL's) bevatten |
| `CertificateCreationTime` | datetime | Datum en tijd waarop het certificaat is gemaakt |
| `CertificateExpirationTime` | datetime | Datum en tijd waarop het certificaat is ingesteld om te verlopen |
| `CertificateCountersignatureTime` | datetime | Datum en tijd waarop het certificaat is ondertekend |
| `IsTrusted` | boolean | Hiermee wordt aangegeven of het bestand wordt vertrouwd op basis van de resultaten van de functie WinVerifyTrust, waarmee wordt gecontroleerd op onbekende basiscertificaatgegevens, ongeldige handtekeningen, ingetrokken certificaten en andere twijfelachtige kenmerken. |
| `IsRootSignerMicrosoft` | boolean | Hiermee wordt aangegeven of Microsoft de ondertekenaar van het basiscertificaat is |
| `ReportId` | lang | Gebeurtenis-id op basis van een herhalende teller. Als u unieke gebeurtenissen wilt identificeren, moet deze kolom worden gebruikt in combinatie met de kolommen DeviceName en Timestamp. | 

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Opsporen op apparaten en in e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
