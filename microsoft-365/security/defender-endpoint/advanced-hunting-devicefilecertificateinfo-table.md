---
title: Tabel DeviceFileCertificateInfo in het geavanceerde schema voor de jacht
description: Meer informatie over bestands ondertekeningsgegevens in de tabel DeviceFileCertificateInfo van het geavanceerde schema voor de jacht
keywords: advanced hunting, threat hunting, cyber threat hunting, mdatp, microsoft defender atp, wdatp search, query, telemetry, schema reference, kusto, table, column, data type, description, digital signature, certificate, file signing, DeviceFileCertificateInfo
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
ms.date: 01/14/2020
ms.technology: mde
ms.openlocfilehash: b3b5af8093107925c6c12c901e8138960c5eeaf6
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058453"
---
# <a name="devicefilecertificateinfo"></a>DeviceFileCertificateInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)


>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

De `DeviceFileCertificateInfo` tabel in het geavanceerde schema voor de [jacht](advanced-hunting-overview.md) bevat informatie over certificaat voor bestands ondertekening. In deze tabel worden gegevens gebruikt die zijn verkregen uit activiteiten voor certificaatverificatie die regelmatig worden uitgevoerd op bestanden op eindpunten.

Zie de geavanceerde verwijzing naar het schema voor de jacht voor meer informatie over andere tabellen in het geavanceerde schema voor [de jacht.](advanced-hunting-schema-reference.md)

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum en tijd waarop de gebeurtenis is opgenomen |
| `DeviceId` | tekenreeks | Unieke id voor het apparaat in de service |
| `DeviceName` | tekenreeks | Volledig gekwalificeerde domeinnaam (FQDN) van het apparaat |
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
- [Meer informatie over het schema](advanced-hunting-schema-reference.md)
