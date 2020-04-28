---
title: DeviceFileCertificateInfo-tabel in het geavanceerde jachtschema
description: Meer informatie over bestandsondertekeningsgegevens in de tabel DeviceFileCertificateInfo van het geavanceerde jachtschema
keywords: geavanceerde jacht, dreigingjacht, cyberdreigingsjacht, bescherming tegen microsoft-dreigingen, microsoft 365, mtp, m365, zoekopdracht, query, telemetrie, schemareferentie, kusto, tabel, kolom, gegevenstype, digitale handtekening, certificaat, bestandsondertekening, DeviceFileCertificateInfo
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
ms.openlocfilehash: fcbd487aeed633176c86fd22bfcd156be02fea22
ms.sourcegitcommit: b6c4b514b2cb6739af949780d7e2a5a5c8dcc161
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/27/2020
ms.locfileid: "43900787"
---
# <a name="devicefilecertificateinfo"></a>DeviceFileCertificateInfo

**Geldt voor:**
- Microsoft Threat Protection

De `DeviceFileCertificateInfo` tabel in het [geavanceerde jachtschema](advanced-hunting-overview.md) bevat informatie over certificaten voor het ondertekenen van bestanden. In deze tabel worden gegevens gebruikt die zijn verkregen uit certificaatverificatieactiviteiten die regelmatig worden uitgevoerd op bestanden op eindpunten.

Voor informatie over andere tabellen in de geavanceerde jacht schema, [zie de geavanceerde jacht referentie](advanced-hunting-schema-tables.md).

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | Datetime | Datum en tijdstip waarop de gebeurtenis is geregistreerd |
| `DeviceId` | Tekenreeks | Unieke id voor de machine in de service |
| `DeviceName` | Tekenreeks | Volledig gekwalificeerde domeinnaam (FQDN) van de machine |
| `SHA1` | Tekenreeks | SHA-1 van het bestand waarop de opgenomen actie is toegepast |
| `IsSigned` | Booleaanse | Geeft aan of het bestand is ondertekend |
| `SignatureType` | Tekenreeks | Geeft aan of handtekeninggegevens zijn gelezen als ingesloten inhoud in het bestand zelf of is gelezen uit een extern catalogusbestand |
| `Signer` | Tekenreeks | Informatie over de ondertekenaar van het bestand |
| `SignerHash` | Tekenreeks | Unieke hashwaarde die de ondertekenaar identificeert |
| `Issuer` | Tekenreeks | Informatie over de instantie van afgifte van certificaten (CA) |
| `IssuerHash` | Tekenreeks | Unieke hashwaarde die de instantie voor afgifte van certificaten (CA) identificeert |
| `CertificateSerialNumber` | Tekenreeks | Identificatienummer voor het certificaat dat uniek is voor de instantie van afgifte van certificaten (CA) |
| `CrlDistributionPointUrls` | Tekenreeks |  JSON-array met de URL's van netwerkshares die certificaten en certificaatintrekkingslijsten (CRL's) bevatten |
| `CertificateCreationTime` | Datetime | Datum en tijd van het certificaat is gemaakt |
| `CertificateExpirationTime` | Datetime | Datum en tijd dat het certificaat verloopt |
| `CertificateCountersignatureTime` | Datetime | Datum en tijd waarop het certificaat is ondertekend |
| `IsTrusted` | Booleaanse | Geeft aan of het bestand wordt vertrouwd op basis van de resultaten van de functie WinVerifyTrust, die controleert op onbekende basiscertificaatgegevens, ongeldige handtekeningen, ingetrokken certificaten en andere twijfelachtige kenmerken |
| `IsRootSignerMicrosoft` | Booleaanse | Geeft aan of de ondertekenaar van het hoofdcertificaat Microsoft is |
| `ReportId` | Lange | Gebeurtenis-id op basis van een herhalingsteller. Om unieke gebeurtenissen te identificeren, moet deze kolom worden gebruikt in combinatie met de kolommen DeviceName en Timestamp. | 

## <a name="related-topics"></a>Verwante onderwerpen
- [Proactief op zoek naar bedreigingen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Zoek naar bedreigingen op verschillende apparaten en e-mails](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
