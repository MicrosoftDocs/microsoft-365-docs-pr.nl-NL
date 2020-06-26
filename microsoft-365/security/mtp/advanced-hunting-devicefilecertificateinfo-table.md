---
title: DeviceFileCertificateInfo-tabel in het geavanceerde jachtschema
description: Meer informatie over informatie over het ondertekenen van bestanden vindt u in de tabel DeviceFileCertificateInfo van het geavanceerde jachtschema
keywords: geavanceerde jacht, bedreiging jacht, cyber bedreiging jacht, Microsoft threat protection, Microsoft 365, mtp, m365, zoeken, query, telemetrie, schema referentie, kusto, tabel, kolom, gegevenstype, digitale handtekening, certificaat, bestand ondertekening, DeviceFileCertificateInfo
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
ms.openlocfilehash: cba27b5b43141c8c90f9a8bc7f70c55aabc1979d
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899313"
---
# <a name="devicefilecertificateinfo"></a>DeviceFileCertificateInfo

**Van toepassing op:**
- Microsoft Threat Protection

De `DeviceFileCertificateInfo` tabel in het geavanceerde [jachtschema](advanced-hunting-overview.md) bevat informatie over certificaten voor het ondertekenen van bestanden. Deze tabel maakt gebruik van gegevens die zijn verkregen uit certificaatverificatieactiviteiten die regelmatig worden uitgevoerd in bestanden op eindpunten.

Zie [de geavanceerde jachtreferentie](advanced-hunting-schema-tables.md)voor informatie over andere tabellen in het geavanceerde jachtschema.

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | Datetime | Datum en tijdstip waarop de gebeurtenis is geregistreerd |
| `DeviceId` | Tekenreeks | Unieke id voor de machine in de service |
| `DeviceName` | Tekenreeks | Volledig gekwalificeerde domeinnaam (FQDN) van de machine |
| `SHA1` | Tekenreeks | SHA-1 van het bestand waarop de geregistreerde actie is toegepast |
| `IsSigned` | Booleaanse | Geeft aan of het bestand is ondertekend |
| `SignatureType` | Tekenreeks | Geeft aan of handtekeninggegevens zijn gelezen als ingesloten inhoud in het bestand zelf of gelezen vanuit een extern catalogusbestand |
| `Signer` | Tekenreeks | Informatie over de ondertekenaar van het bestand |
| `SignerHash` | Tekenreeks | Unieke hashwaarde die de ondertekenaar identificeert |
| `Issuer` | Tekenreeks | Informatie over de instantie van afgiftecertificaat (CA) |
| `IssuerHash` | Tekenreeks | Unieke hashwaarde die de uitgiftecertificaatautoriteit (CA) identificeert |
| `CertificateSerialNumber` | Tekenreeks | Identificatienummer voor het certificaat dat uniek is voor de instantie van afgiftecertificaat (CA) |
| `CrlDistributionPointUrls` | Tekenreeks |  JSON-array met de URL's van netwerkshares die certificaten en certificaatintrekkingslijsten (CRL's) bevatten |
| `CertificateCreationTime` | Datetime | Datum en tijd waarop het certificaat is gemaakt |
| `CertificateExpirationTime` | Datetime | Datum en tijd waarop het certificaat is ingesteld om te verlopen |
| `CertificateCountersignatureTime` | Datetime | Datum en tijd waarop het certificaat is ondertekend |
| `IsTrusted` | Booleaanse | Geeft aan of het bestand wordt vertrouwd op basis van de resultaten van de functie WinVerifyTrust, die controleert op onbekende basiscertificaatgegevens, ongeldige handtekeningen, ingetrokken certificaten en andere twijfelachtige kenmerken |
| `IsRootSignerMicrosoft` | Booleaanse | Geeft aan of de ondertekenaar van het basiscertificaat Microsoft is |
| `ReportId` | Lange | Gebeurtenis-id op basis van een herhalende teller. Om unieke gebeurtenissen te identificeren, moet deze kolom worden gebruikt in combinatie met de kolommen DeviceName en Timestamp. | 

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Zoek naar bedreigingen op verschillende apparaten en e-mails](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
