---
title: DeviceFileCertificateInfoBeta tabel in de geavanceerde jacht schema
description: Meer informatie over gegevens over het ondertekenen van bestanden in de DeviceFileCertificateInfoBeta-tabel van het geavanceerde jachtschema
keywords: geavanceerde jacht, bedreigingjacht, cyberdreigingsjacht, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetrie, schemareferentie, kusto, tabel, kolom, gegevenstype, digitale handtekening, certificaat, bestandsondertekening, DeviceFileCertificateInfoBeta
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
ms.openlocfilehash: c1d6b9170f0cc236f2656ce2adb596c31d9ee2bd
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42811681"
---
# <a name="devicefilecertificateinfobeta"></a>DeviceFileCertificateInfoBeta

**Van toepassing op:**
- Microsoft-bedreigingsbeveiliging

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

De `DeviceFileCertificateInfoBeta` tabel in het [geavanceerde jachtschema](advanced-hunting-overview.md) bevat informatie over certificaten voor het ondertekenen van bestanden. Deze tabel gebruikt gegevens die zijn verkregen uit certificeringsverificatieactiviteiten die regelmatig worden uitgevoerd in bestanden op eindpunten.

Zie [de geavanceerde jachtreferentie](advanced-hunting-schema-tables.md)voor informatie over andere tabellen in het geavanceerde jachtschema.

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | Datetime | Datum en tijd waarop de gebeurtenis is geregistreerd |
| `DeviceId` | Tekenreeks | Unieke id voor de machine in de service |
| `DeviceName` | Tekenreeks | Volledig gekwalificeerde domeinnaam (FQDN) van de machine |
| `SHA1` | Tekenreeks | SHA-1 van het bestand waarop de opgenomen actie is toegepast |
| `IsSigned` | Booleaanse | Geeft aan of het bestand is ondertekend |
| `SignatureType` | Tekenreeks | Geeft aan of handtekeninggegevens zijn gelezen als ingesloten inhoud in het bestand zelf of uit een extern catalogusbestand zijn gelezen |
| `Signer` | Tekenreeks | Informatie over de ondertekenaar van het bestand |
| `SignerHash` | Tekenreeks | Unieke hashwaarde die de ondertekenaar identificeert |
| `Issuer` | Tekenreeks | Informatie over de instantie van afgifte certificaat (CA) |
| `IssuerHash` | Tekenreeks | Unieke hashwaarde die de instantie van afgiftecertificaat (CA) identificeert |
| `CertificateSerialNumber` | Tekenreeks | Identificatiecode voor het certificaat dat uniek is voor de instantie van afgifte van certificaten (CA) |
| `CrlDistributionPointUrls` | Tekenreeks |  JSON-array met de URL's van netwerkshares die certificaten en certificaatintrekkingslijsten (CRL's) bevatten |
| `CertificateCreationTime` | Datetime | Datum en tijd dat het certificaat is gemaakt |
| `CertificateExpirationTime` | Datetime | Datum en tijd dat het certificaat is verlopen |
| `CertificateCountersignatureTime` | Datetime | Datum en tijd dat het certificaat is tegengetekend |
| `IsTrusted` | Booleaanse | Hiermee geeft u aan of het bestand wordt vertrouwd op basis van de resultaten van de functie WinVerifyTrust, die controleert op onbekende basiscertificaatgegevens, ongeldige handtekeningen, ingetrokken certificaten en andere twijfelachtige kenmerken |
| `IsRootSignerMicrosoft` | Booleaanse | Geeft aan of de ondertekenaar van het basiscertificaat Microsoft is |
| `ReportId` | Lange | Gebeurtenis-id op basis van een herhalende teller. Om unieke gebeurtenissen te identificeren, moet deze kolom worden gebruikt in combinatie met de kolommen DeviceName en Timestamp. | 

## <a name="related-topics"></a>Verwante onderwerpen
- [Proactief jagen op bedreigingen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Op zoek naar bedreigingen op verschillende apparaten en e-mails](advanced-hunting-query-emails-devices.md)
- [Het schema begrijpen](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
