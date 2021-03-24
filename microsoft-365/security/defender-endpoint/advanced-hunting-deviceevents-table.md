---
title: Tabel DeviceEvents in het geavanceerde schema voor de jacht
description: Meer informatie over antivirus, firewall en andere gebeurtenistypen in de tabel diverse apparaatgebeurtenissen (DeviceEvents) van het geavanceerde schema voor de jacht
keywords: advanced hunting, threat hunting, cyber threat hunting, search, query, telemetry, schema reference, kusto, table, column, data type, security events, antivirus, firewall, exploit guard, MiscEvents
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
ms.technology: mde
ms.openlocfilehash: 49a0b608caa6d759f58889e6f831f84d2b4b90d3
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058454"
---
# <a name="deviceevents"></a>DeviceEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)


> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

De diverse apparaatgebeurtenissen of -tabel in het geavanceerde schema bevat informatie over verschillende gebeurtenistypen, waaronder gebeurtenissen die worden veroorzaakt door beveiligingsbesturingselementen, zoals Microsoft Defender Antivirus en `DeviceEvents` exploitbeveiliging. [](advanced-hunting-overview.md) Gebruik deze verwijzing om query's te maken die gegevens uit de tabel retourneren.

Zie de geavanceerde verwijzing naar het schema voor de jacht voor meer informatie over andere tabellen in het geavanceerde schema voor [de jacht.](advanced-hunting-schema-reference.md)

| Kolomnaam | Gegevenstype | Beschrijving |
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
| `AccountDomain` | tekenreeks | Domein van het account |
| `AccountName` |tekenreeks | Gebruikersnaam van het account |
| `AccountSid` | tekenreeks | Beveiligings-id (SID) van het account |
| `RemoteUrl` | tekenreeks | URL of volledig gekwalificeerde domeinnaam (FQDN) die werd verbonden met |
| `RemoteDeviceName` | tekenreeks | Naam van het apparaat dat een externe bewerking heeft uitgevoerd op het betreffende apparaat. Afhankelijk van de gebeurtenis die wordt gerapporteerd, kan deze naam een volledig gekwalificeerde domeinnaam (FQDN), een NetBIOS-naam of een hostnaam zonder domeingegevens zijn |
| `ProcessId` | int | Proces-id (PID) van het nieuw gemaakte proces |
| `ProcessCommandLine` | tekenreeks | Opdrachtregel die wordt gebruikt om het nieuwe proces te maken |
| `ProcessCreationTime` | datetime | Datum en tijd waarop het proces is gemaakt |
| `ProcessTokenElevation` | tekenreeks | Tokentype dat de aanwezigheid of afwezigheid aangeeft van UAC-bevoegdheden (User Access Control) die zijn toegepast op het nieuw gemaakte proces |
| `LogonId` | tekenreeks | Id voor een aanmeldingssessie. Deze id is alleen uniek op hetzelfde apparaat tussen herstarten |
| `RegistryKey` | tekenreeks | Registersleutel waar de opgenomen actie op is toegepast |
| `RegistryValueName` | tekenreeks | Naam van de registerwaarde waar de opgenomen actie op is toegepast |
| `RegistryValueData` | tekenreeks | Gegevens van de registerwaarde waar de opgenomen actie op is toegepast |
| `RemoteIP` | tekenreeks | IP-adres dat werd verbonden met |
| `RemotePort` | int | TCP-poort op het externe apparaat waar verbinding mee werd |
| `LocalIP` | tekenreeks | IP-adres dat is toegewezen aan het lokale apparaat dat tijdens communicatie wordt gebruikt |
| `LocalPort` | int | TCP-poort op het lokale apparaat dat tijdens communicatie wordt gebruikt |
| `FileOriginUrl` | tekenreeks | URL waar het bestand is gedownload |
| `FileOriginIP` | tekenreeks | IP-adres waar het bestand is gedownload |
| `AdditionalFields` | tekenreeks | Aanvullende informatie over de gebeurtenis in de JSON-matrixindeling |
| `InitiatingProcessSHA1` | tekenreeks | SHA-1 van het proces (afbeeldingsbestand) dat de gebeurtenis heeft gestart |
| `InitiatingProcessSHA256` | tekenreeks | SHA-256 van het proces (afbeeldingsbestand) dat de gebeurtenis heeft gestart. Dit veld wordt meestal niet ingevuld: gebruik de kolom SHA1 wanneer deze beschikbaar is |
| `InitiatingProcessFileName` | tekenreeks | Naam van het proces dat de gebeurtenis heeft gestart |
| `InitiatingProcessFolderPath` | tekenreeks | Map met het proces (afbeeldingsbestand) dat de gebeurtenis heeft gestart |
| `InitiatingProcessId` | int | Proces-id (PID) van het proces dat de gebeurtenis heeft gestart |
| `InitiatingProcessCommandLine` | tekenreeks | Opdrachtregel die wordt gebruikt om het proces uit te voeren waarmee de gebeurtenis is gestart |
| `InitiatingProcessCreationTime` | datetime | Datum en tijd waarop het proces dat de gebeurtenis heeft gestart is gestart |
| `InitiatingProcessParentId` | int | Proces-id (PID) van het bovenliggende proces dat het proces heeft voortgebracht dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessParentFileName` | tekenreeks | Naam van het bovenliggende proces dat het proces heeft voortgebracht dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessParentCreationTime` | datetime | Datum en tijd waarop het bovenliggende deel van het proces dat verantwoordelijk is voor de gebeurtenis is gestart |
| `InitiatingProcessMD5` | tekenreeks | MD5-hash van het proces (afbeeldingsbestand) dat de gebeurtenis heeft gestart |
| `InitiatingProcessAccountDomain` | tekenreeks | Domein van het account dat het proces heeft doorlopen dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessAccountName` | tekenreeks | Gebruikersnaam van het account dat het proces heeft doorlopen dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessAccountSid` | tekenreeks | Beveiligingsaanduiding (SID) van het account dat het proces heeft doorlopen dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessLogonId` | tekenreeks | Id voor een aanmeldingssessie van het proces dat de gebeurtenis heeft gestart. Deze id is alleen uniek op hetzelfde apparaat tussen herstarten |
| `ReportId` | lang | Gebeurtenis-id op basis van een herhalende teller. Als u unieke gebeurtenissen wilt identificeren, moet deze kolom worden gebruikt in combinatie met de `DeviceName` kolommen en `Timestamp` de kolommen |
| `AppGuardContainerId` | tekenreeks | Id voor de gevirtualiseerde container die door Application Guard wordt gebruikt om browseractiviteit te isoleren |


## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Meer informatie over het schema](advanced-hunting-schema-reference.md)
