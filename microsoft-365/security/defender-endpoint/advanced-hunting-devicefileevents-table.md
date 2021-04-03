---
title: Tabel DeviceFileEvents in het geavanceerde schema voor de jacht
description: Meer informatie over bestandsgerelateerde gebeurtenissen in de tabel DeviceFileEvents van het geavanceerde schema voor de jacht
keywords: advanced hunting, threat hunting, cyber threat hunting, search, query, telemetry, schema reference, kusto, table, column, data type, description, devicefileevents, files, path, hash, sha1, sha256, md5, FileCreationEvents
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 323cc8e809b81f937a29e41f24c2976c3d5c175b
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500855"
---
# <a name="devicefileevents"></a>DeviceFileEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)


>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

De `DeviceFileEvents` tabel in het geavanceerde schema [bevat](advanced-hunting-overview.md) informatie over het maken, wijzigen en andere bestandssysteemgebeurtenissen. Gebruik deze verwijzing om query's te maken die gegevens uit de tabel retourneren.

Zie de geavanceerde verwijzing naar het schema voor de jacht voor meer informatie over andere tabellen in het geavanceerde schema voor [de jacht.](advanced-hunting-schema-reference.md)

| Kolomnaam | Gegevenstype | Omschrijving |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum en tijd waarop de gebeurtenis is opgenomen |
| `DeviceId` | tekenreeks | Unieke id voor het apparaat in de service |
| `DeviceName` | tekenreeks | Volledig gekwalificeerde domeinnaam (FQDN) van het apparaat |
| `ActionType` | tekenreeks | Type activiteit dat de gebeurtenis heeft geactiveerd |
| `FileName` | tekenreeks | Naam van het bestand waar de opgenomen actie op is toegepast |
| `FolderPath` | tekenreeks | Map met het bestand waarin de opgenomen actie is toegepast |
| `SHA1` | tekenreeks | SHA-1 van het bestand waar de opgenomen actie op is toegepast |
| `SHA256` | tekenreeks | SHA-256 van het bestand waar de opgenomen actie op is toegepast. Dit veld wordt meestal niet ingevuld: gebruik de kolom SHA1 wanneer deze beschikbaar is |
| `MD5` | tekenreeks | MD5-hash van het bestand waar de opgenomen actie op is toegepast |
| `FileOriginUrl` | tekenreeks | URL waar het bestand is gedownload |
| `FileOriginReferrerUrl` | tekenreeks | URL van de webpagina die een koppeling naar het gedownloade bestand bevat |
| `FileOriginIP` | tekenreeks | IP-adres waar het bestand is gedownload |
| `InitiatingProcessAccountDomain` | tekenreeks | Domein van het account dat het proces heeft doorlopen dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessAccountName` | tekenreeks | Gebruikersnaam van het account dat het proces heeft doorlopen dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessAccountSid` | tekenreeks | Beveiligingsaanduiding (SID) van het account dat het proces heeft doorlopen dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessMD5` | tekenreeks | MD5-hash van het proces (afbeeldingsbestand) dat de gebeurtenis heeft gestart |
| `InitiatingProcessSHA1` | tekenreeks | SHA-1 van het proces (afbeeldingsbestand) dat de gebeurtenis heeft gestart |
| `InitiatingProcessFolderPath` | tekenreeks | Map met het proces (afbeeldingsbestand) dat de gebeurtenis heeft gestart |
| `InitiatingProcessFileName` | tekenreeks | Naam van het proces dat de gebeurtenis heeft gestart |
| `InitiatingProcessId` | int | Proces-id (PID) van het proces dat de gebeurtenis heeft gestart |
| `InitiatingProcessCommandLine` | tekenreeks | Opdrachtregel die wordt gebruikt om het proces uit te voeren waarmee de gebeurtenis is gestart |
| `InitiatingProcessCreationTime` | datetime | Datum en tijd waarop het proces dat de gebeurtenis heeft gestart is gestart |
| `InitiatingProcessIntegrityLevel` | tekenreeks | integriteitsniveau van het proces dat de gebeurtenis heeft gestart. Windows wijst integriteitsniveaus toe aan processen op basis van bepaalde kenmerken, bijvoorbeeld als ze zijn gestart via een internet-download. Deze integriteitsniveaus zijn van invloed op machtigingen voor resources |
| `InitiatingProcessTokenElevation` | tekenreeks | Tokentype dat aangeeft dat de aanwezigheid of afwezigheid van UAC-bevoegdheden (User Access Control) is toegepast op het proces waarmee de gebeurtenis is gestart |
| `InitiatingProcessParentId` | int | Proces-id (PID) van het bovenliggende proces dat het proces heeft voortgebracht dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessParentFileName` | tekenreeks | Naam van het bovenliggende proces dat het proces heeft voortgebracht dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessParentCreationTime` | datetime | Datum en tijd waarop het bovenliggende deel van het proces dat verantwoordelijk is voor de gebeurtenis is gestart |
| `RequestProtocol` | tekenreeks | Netwerkprotocol, indien van toepassing, dat wordt gebruikt om de activiteit te starten: Onbekend, Lokaal, SMB of NFS |
| `ShareName` | tekenreeks | Naam van de gedeelde map met het bestand |
| `RequestSourceIP` | tekenreeks | IPv4- of IPv6-adres van het externe apparaat dat de activiteit heeft gestart |
| `RequestSourcePort` | tekenreeks | Bronpoort op het externe apparaat dat de activiteit heeft gestart |
| `RequestAccountName` | tekenreeks | Gebruikersnaam van het account dat wordt gebruikt om de activiteit op afstand te starten |
| `RequestAccountDomain` | tekenreeks | Domein van het account dat wordt gebruikt om de activiteit op afstand te starten |
| `RequestAccountSid` | tekenreeks | Beveiligings-id (SID) van het account om de activiteit op afstand te starten |
| `ReportId` | lang | Gebeurtenis-id op basis van een herhalende teller. Als u unieke gebeurtenissen wilt identificeren, moet deze kolom worden gebruikt in combinatie met de kolommen DeviceName en Timestamp |
| `AppGuardContainerId` | tekenreeks | Id voor de gevirtualiseerde container die door Application Guard wordt gebruikt om browseractiviteit te isoleren |
| `SensitivityLabel` | tekenreeks | Label toegepast op een e-mailbericht, bestand of andere inhoud om deze te classificeren voor informatiebeveiliging |
| `SensitivitySubLabel` | tekenreeks | Sublabel dat is toegepast op een e-mailbericht, bestand of andere inhoud om deze te classificeren voor informatiebeveiliging; gevoeligheidssublabels worden gegroepeerd onder gevoeligheidslabels, maar worden onafhankelijk van elkaar behandeld |
| `IsAzureInfoProtectionApplied` | booleaanse | Geeft aan of het bestand is versleuteld door Azure Information Protection |

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Meer informatie over het schema](advanced-hunting-schema-reference.md)
