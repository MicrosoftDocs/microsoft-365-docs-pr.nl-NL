---
title: Tabel DeviceFileCertificateInfo in het geavanceerde schema voor de jacht
description: Meer informatie over bestands ondertekeningsgegevens in de tabel DeviceFileCertificateInfo van het geavanceerde schema voor de jacht
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, digital signature, certificate, file signing, DeviceFileCertificateInfo
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
ms.openlocfilehash: 1f894f3fc8cff2113004ff9c9e34ec2ca0144799
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023211"
---
# <a name="devicefilecertificateinfo"></a>DeviceFileCertificateInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender
- Microsoft Defender voor Eindpunt

De `DeviceFileCertificateInfo` tabel in het geavanceerde schema voor de [jacht](advanced-hunting-overview.md) bevat informatie over certificaat voor bestands ondertekening. In deze tabel worden gegevens gebruikt die zijn verkregen uit activiteiten voor certificaatverificatie die regelmatig worden uitgevoerd op bestanden op eindpunten.

Zie de geavanceerde zoekverwijzing voor meer informatie over andere tabellen in het geavanceerde schema voor [de jacht.](advanced-hunting-schema-tables.md)

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum en tijd waarop de gebeurtenis is opgenomen |
| `DeviceId` | tekenreeks | Unieke id voor de machine in de service |
| `DeviceName` | tekenreeks | Volledig gekwalificeerde domeinnaam (FQDN) van de computer |
| `SHA1` | tekenreeks | SHA-1 van het bestand waar de opgenomen actie op is toegepast |
| `IsSigned` | booleaanse | Geeft aan of het bestand is ondertekend |
| `SignatureType` | tekenreeks | Geeft aan of handtekeninggegevens zijn gelezen als ingesloten inhoud in het bestand zelf of gelezen uit een extern catalogusbestand |
| `Signer` | tekenreeks | Informatie over de ondertekenaar van het bestand |
| `SignerHash` | tekenreeks | Unieke hashwaarde die de ondertekenaar identificeert |
| `Issuer` | tekenreeks | Informatie over de certificeringsinstantie voor afgifte (CA) |
| `IssuerHash` | tekenreeks | Unieke hashwaarde voor het identificeren van certificeringsinstantie (CA) |
| `CertificateSerialNumber` | tekenreeks | Id voor het certificaat dat uniek is voor de certificeringsinstantie voor afgifte (CA) |
| `CrlDistributionPointUrls` | tekenreeks |  JSON-matrix met de URL's van netwerkaandelen die certificaten en certificaatteroeplijsten (CRL's) bevatten |
| `CertificateCreationTime` | datetime | Datum en tijd waarop het certificaat is gemaakt |
| `CertificateExpirationTime` | datetime | Datum en tijd waarop het certificaat is ingesteld op verlopen |
| `CertificateCountersignatureTime` | datetime | Datum en tijd waarop het certificaat is ondertekend |
| `IsTrusted` | booleaanse | Geeft aan of het bestand wordt vertrouwd op basis van de resultaten van de functie WinVerifyTrust, die controleert op onbekende basiscertificaatgegevens, ongeldige handtekeningen, ingetrokken certificaten en andere twijfelachtige kenmerken |
| `IsRootSignerMicrosoft` | booleaanse | Geeft aan of de ondertekenaar van het hoofdcertificaat Microsoft is |
| `ReportId` | lang | Gebeurtenis-id op basis van een herhalende teller. Als u unieke gebeurtenissen wilt identificeren, moet deze kolom worden gebruikt in combinatie met de kolommen DeviceName en Timestamp. | 

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Opsporen op apparaten en in e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
