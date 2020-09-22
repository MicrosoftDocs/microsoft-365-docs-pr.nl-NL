---
title: DeviceFileCertificateInfo-tabel in het geavanceerde jacht schema
description: Meer informatie over informatie over bestands ondertekening in de tabel DeviceFileCertificateInfo van het schema geavanceerde jacht
keywords: geavanceerde jacht, bedreigings jacht, Cyber Threat jacht, Microsoft Threat Protection, Microsoft 365, MTP, m365, Search, query, Telemetry, schema verwijzing, kusto, tabel, kolom, gegevenstype, digitale handtekening, certificaat, bestands ondertekening, DeviceFileCertificateInfo
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
ms.openlocfilehash: 69669366f4f4d79f7c9ec7f28c8ccf1336e96adc
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198221"
---
# <a name="devicefilecertificateinfo"></a>DeviceFileCertificateInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft Threat Protection

De `DeviceFileCertificateInfo` tabel in het [geavanceerde jacht](advanced-hunting-overview.md) -schema bevat informatie over het ondertekenen van certificaten. In deze tabel worden de gegevens gebruikt die zijn verkregen van activiteiten voor certificaatverificatie, die regelmatig worden uitgevoerd voor bestanden op eindpunten.

Zie voor meer informatie over andere tabellen in het geavanceerde jacht-schema [de Naslaggids voor Geavanceerd](advanced-hunting-schema-tables.md)zoeken.

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | tijd | De datum en tijd waarop de gebeurtenis is vastgelegd |
| `DeviceId` | tekenreeks | Unieke id voor de computer in de service |
| `DeviceName` | tekenreeks | FQDN-naam (Fully Qualified Domain Name) van de computer |
| `SHA1` | tekenreeks | SHA-1 van het bestand waarop de opgenomen actie is toegepast |
| `IsSigned` | Boolean | Geeft aan of het bestand is ondertekend |
| `SignatureType` | tekenreeks | Hiermee wordt aangegeven of de gegevens in het bestand zelf zijn ingesloten in het bestand zelf en uit een extern catalogusbestand gelezen. |
| `Signer` | tekenreeks | Informatie over de ondertekenaar van het bestand |
| `SignerHash` | tekenreeks | Unieke hash-waarde die de ondertekenaar identificeert |
| `Issuer` | tekenreeks | Informatie over de uitgevende certificeringsinstantie (CA) |
| `IssuerHash` | tekenreeks | Unieke hashwaarde die een certificeringsinstantie (CA) identificeert |
| `CertificateSerialNumber` | tekenreeks | De id van het certificaat dat uniek is voor de uitgevende certificeringsinstantie (CA) |
| `CrlDistributionPointUrls` | tekenreeks |  JSON-matrix met de Url's van netwerkshares die certificaten en certificaatintrekkingslijsten (Crl's) bevatten |
| `CertificateCreationTime` | tijd | De datum en tijd waarop het certificaat is gemaakt |
| `CertificateExpirationTime` | tijd | Datum en tijd waarop het certificaat is ingesteld op verloopt |
| `CertificateCountersignatureTime` | tijd | De datum en tijd waarop het certificaat is ondertekend |
| `IsTrusted` | Boolean | Hiermee wordt aangegeven of het bestand wordt vertrouwd op basis van de resultaten van de functie WinVerifyTrust, waarmee wordt gecontroleerd op onbekende basis certificerings informatie, ongeldige handtekeningen, ingetrokken certificaten en andere betrouwbare kenmerken |
| `IsRootSignerMicrosoft` | Boolean | Geeft aan of de ondertekenaar van het basiscertificaat Microsoft is |
| `ReportId` | lang | Gebeurtenis-id op basis van een herhalende teller. Als u unieke gebeurtenissen wilt identificeren, moet deze kolom worden gebruikt in combinatie met de de naam van het apparaat en de timestamp-kolommen. | 

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Opsporen op apparaten en in e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
