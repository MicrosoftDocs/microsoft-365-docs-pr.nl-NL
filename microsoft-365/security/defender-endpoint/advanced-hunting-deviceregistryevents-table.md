---
title: Tabel DeviceRegistryEvents in het geavanceerde schema voor de jacht
description: Meer informatie over registergebeurtenissen die u kunt opvragen in de tabel DeviceRegistryEvents van het geavanceerde schema voor de jacht
keywords: advanced hunting, threat hunting, cyber threat hunting, search, query, telemetry, schema reference, kusto, table, column, data type, deviceregistryevents, registry, key, subkey, value, RegistryEvents
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
ms.openlocfilehash: 31fe2bb882bc59eb516773c0c319b1f25f56a95e
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498770"
---
# <a name="deviceregistryevents"></a>DeviceRegistryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)


>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

De `DeviceRegistryEvents` tabel in het geavanceerde schema [bevat](advanced-hunting-overview.md) informatie over het maken en wijzigen van registergegevens. Gebruik deze verwijzing om query's te maken die gegevens uit de tabel retourneren.

Zie de geavanceerde verwijzing naar het schema voor de jacht voor meer informatie over andere tabellen in het geavanceerde schema voor [de jacht.](advanced-hunting-schema-reference.md)

| Kolomnaam | Gegevenstype | Omschrijving |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum en tijd waarop de gebeurtenis is opgenomen |
| `DeviceId` | tekenreeks | Unieke id voor het apparaat in de service |
| `DeviceName` | tekenreeks | Volledig gekwalificeerde domeinnaam (FQDN) van het apparaat |
| `ActionType` | tekenreeks | Type activiteit dat de gebeurtenis heeft geactiveerd |
| `RegistryKey` | tekenreeks | Registersleutel waar de opgenomen actie op is toegepast |
| `RegistryValueType` | tekenreeks | Gegevenstype, zoals binair of tekenreeks, van de registerwaarde waar de opgenomen actie op is toegepast |
| `RegistryValueName` | tekenreeks | Naam van de registerwaarde waar de opgenomen actie op is toegepast |
| `RegistryValueData` | tekenreeks | Gegevens van de registerwaarde waar de opgenomen actie op is toegepast |
| `PreviousRegistryValueName` | tekenreeks | Oorspronkelijke naam van de registerwaarde voordat deze werd gewijzigd |
| `PreviousRegistryValueData` | tekenreeks | Oorspronkelijke gegevens van de registerwaarde voordat deze werd gewijzigd |
| `InitiatingProcessAccountDomain` | tekenreeks | Domein van het account dat het proces heeft doorlopen dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessAccountName` | tekenreeks | Gebruikersnaam van het account dat het proces heeft doorlopen dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessAccountSid` | tekenreeks | Beveiligingsaanduiding (SID) van het account dat het proces heeft doorlopen dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessSHA1` | tekenreeks | SHA-1 van het proces (afbeeldingsbestand) dat de gebeurtenis heeft gestart |
| `InitiatingProcessMD5` | tekenreeks | MD5-hash van het proces (afbeeldingsbestand) dat de gebeurtenis heeft gestart |
| `InitiatingProcessFileName` | tekenreeks | Naam van het proces dat de gebeurtenis heeft gestart |
| `InitiatingProcessId` | int | Proces-id (PID) van het proces dat de gebeurtenis heeft gestart |
| `InitiatingProcessCommandLine` | tekenreeks | Opdrachtregel die wordt gebruikt om het proces uit te voeren waarmee de gebeurtenis is gestart |
| `InitiatingProcessCreationTime` | datetime | Datum en tijd waarop het proces dat de gebeurtenis heeft gestart is gestart |
| `InitiatingProcessFolderPath` | tekenreeks | Map met het proces (afbeeldingsbestand) dat de gebeurtenis heeft gestart |
| `InitiatingProcessParentId` | int | Proces-id (PID) van het bovenliggende proces dat het proces heeft voortgebracht dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessParentFileName` | tekenreeks | Naam van het bovenliggende proces dat het proces heeft voortgebracht dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessParentCreationTime` | datetime | Datum en tijd waarop het bovenliggende deel van het proces dat verantwoordelijk is voor de gebeurtenis is gestart |
| `InitiatingProcessIntegrityLevel` | tekenreeks | Integriteitsniveau van het proces dat de gebeurtenis heeft gestart. Windows wijst integriteitsniveaus toe aan processen op basis van bepaalde kenmerken, bijvoorbeeld als ze zijn gestart via een internet-download. Deze integriteitsniveaus zijn van invloed op machtigingen voor resources |
| `InitiatingProcessTokenElevation` | tekenreeks | Tokentype dat aangeeft dat de aanwezigheid of afwezigheid van UAC-bevoegdheden (User Access Control) is toegepast op het proces waarmee de gebeurtenis is gestart |
| `ReportId` | lang | Gebeurtenis-id op basis van een herhalende teller. Als u unieke gebeurtenissen wilt identificeren, moet deze kolom worden gebruikt in combinatie met de `DeviceName` kolommen en `Timestamp` de kolommen |
| `AppGuardContainerId` | tekenreeks | Id voor de gevirtualiseerde container die door Application Guard wordt gebruikt om browseractiviteit te isoleren |

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Meer informatie over het schema](advanced-hunting-schema-reference.md)
