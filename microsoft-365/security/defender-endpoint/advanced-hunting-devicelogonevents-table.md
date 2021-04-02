---
title: Tabel DeviceLogonEvents in het geavanceerde schema voor de jacht
description: Meer informatie over verificatie- of aanmeldingsgebeurtenissen in de tabel DeviceLogonEvents van het geavanceerde schema voor de jacht
keywords: advanced hunting, threat hunting, cyber threat hunting, search, query, telemetry, schema reference, kusto, table, column, data type, description, devicelogonevents, authentication, logon, sign in, LogonEvents
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
ms.openlocfilehash: c270f54c856c1ed504533c826ca884786c784549
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499156"
---
# <a name="devicelogonevents"></a>DeviceLogonEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)


>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

De tabel in het geavanceerde schema bevat informatie over aanmeldingen van gebruikers `DeviceLogonEvents` en andere [](advanced-hunting-overview.md) verificatiegebeurtenissen. Gebruik deze verwijzing om query's te maken die gegevens uit de tabel retourneren.

> [!NOTE]
> Verzameling deviceLogonEvents wordt niet ondersteund in Windows 7 of Windows Server 2008 R2.
> We raden u aan een upgrade uit te voeren naar Windows 10 of Windows Server 2019 voor een optimale zichtbaarheid van de aanmeldingsactiviteit van gebruikers.

Zie de geavanceerde verwijzing naar het schema voor de jacht voor meer informatie over andere tabellen in het geavanceerde schema voor [de jacht.](advanced-hunting-schema-reference.md)

| Kolomnaam | Gegevenstype | Omschrijving |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum en tijd waarop de gebeurtenis is opgenomen |
| `DeviceId` | tekenreeks | Unieke id voor het apparaat in de service |
| `DeviceName` | tekenreeks | Volledig gekwalificeerde domeinnaam (FQDN) van het apparaat |
| `ActionType` | tekenreeks |Type activiteit dat de gebeurtenis heeft geactiveerd |
| `AccountDomain` | tekenreeks | Domein van het account |
| `AccountName` | tekenreeks | Gebruikersnaam van het account |
| `AccountSid` | tekenreeks | Beveiligings-id (SID) van het account |
| `LogonType` | tekenreeks | Type aanmeldingssessie, met name:<br><br> - **Interactief:** gebruiker werkt fysiek met het apparaat met behulp van het lokale toetsenbord en scherm<br><br> - **RDP-aanmeldingen (Remote Interactive)** - Gebruiker werkt op afstand met het apparaat met behulp van Extern bureaublad, Terminal Services, Hulp op afstand of andere RDP-clients<br><br> - **Netwerk:** sessie gestart wanneer het apparaat wordt gebruikt met PsExec of wanneer gedeelde resources op het apparaat, zoals printers en gedeelde mappen, worden gebruikt<br><br> - **Batch** : sessie die is gestart door geplande taken<br><br> - **Service** - Sessie gestart door services terwijl deze beginnen<br> |
| `LogonId` | tekenreeks | Id voor een aanmeldingssessie. Deze id is alleen uniek op hetzelfde apparaat tussen herstarten |
| `RemoteDeviceName` | tekenreeks | Naam van het apparaat dat een externe bewerking heeft uitgevoerd op het betreffende apparaat. Afhankelijk van de gebeurtenis die wordt gerapporteerd, kan deze naam een volledig gekwalificeerde domeinnaam (FQDN), een NetBIOS-naam of een hostnaam zonder domeingegevens zijn |
| `RemoteIP` | tekenreeks | IP-adres dat werd verbonden met |
| `RemoteIPType` | tekenreeks | Type IP-adres, bijvoorbeeld Openbaar, Privé, Gereserveerd, Loopback, Teredo, FourToSixMapping en Broadcast |
| `RemotePort` | int | TCP-poort op het externe apparaat waar verbinding mee werd |
| `AdditionalFields` | tekenreeks | Aanvullende informatie over de gebeurtenis in de JSON-matrixindeling |
| `InitiatingProcessAccountDomain` | tekenreeks | Domein van het account dat het proces heeft doorlopen dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessAccountName` | tekenreeks | Gebruikersnaam van het account dat het proces heeft doorlopen dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessAccountSid` | tekenreeks | Beveiligingsaanduiding (SID) van het account dat het proces heeft doorlopen dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessIntegrityLevel` | tekenreeks | Integriteitsniveau van het proces dat de gebeurtenis heeft gestart. Windows wijst integriteitsniveaus toe aan processen op basis van bepaalde kenmerken, bijvoorbeeld als ze zijn gestart via een internet-download. Deze integriteitsniveaus zijn van invloed op machtigingen voor resources |
| `InitiatingProcessTokenElevation` | tekenreeks | Tokentype dat aangeeft dat de aanwezigheid of afwezigheid van UAC-bevoegdheden (User Access Control) is toegepast op het proces waarmee de gebeurtenis is gestart |
| `InitiatingProcessSHA1` | tekenreeks | SHA-1 van het proces (afbeeldingsbestand) dat de gebeurtenis heeft gestart |
| `InitiatingProcessSHA256` | tekenreeks | SHA-256 van het proces (afbeeldingsbestand) dat de gebeurtenis heeft gestart. Dit veld wordt meestal niet ingevuld: gebruik de kolom SHA1 wanneer deze beschikbaar is |
| `InitiatingProcessMD5` | tekenreeks | MD5-hash van het proces (afbeeldingsbestand) dat de gebeurtenis heeft gestart |
| `InitiatingProcessFileName` | tekenreeks | Naam van het proces dat de gebeurtenis heeft gestart |
| `InitiatingProcessId` | int | Proces-id (PID) van het proces dat de gebeurtenis heeft gestart |
| `InitiatingProcessCommandLine` | tekenreeks | Opdrachtregel die wordt gebruikt om het proces uit te voeren waarmee de gebeurtenis is gestart |
| `InitiatingProcessCreationTime` | datetime | Datum en tijd waarop het proces dat de gebeurtenis heeft gestart is gestart |
| `InitiatingProcessFolderPath` | tekenreeks | Map met het proces (afbeeldingsbestand) dat de gebeurtenis heeft gestart |
| `InitiatingProcessParentId` | int | Proces-id (PID) van het bovenliggende proces dat het proces heeft voortgebracht dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessParentFileName` | tekenreeks | Naam van het bovenliggende proces dat het proces heeft voortgebracht dat verantwoordelijk is voor de gebeurtenis |
| `InitiatingProcessParentCreationTime` | datetime | Datum en tijd waarop het bovenliggende deel van het proces dat verantwoordelijk is voor de gebeurtenis is gestart |
| `ReportId` | lang | Gebeurtenis-id op basis van een herhalende teller. Als u unieke gebeurtenissen wilt identificeren, moet deze kolom worden gebruikt in combinatie met de `DeviceName` kolommen en `Timestamp` de kolommen |
| `AppGuardContainerId` | tekenreeks | Id voor de gevirtualiseerde container die door Application Guard wordt gebruikt om browseractiviteit te isoleren |
| `IsLocalAdmin` | booleaanse | Booleaanse indicator van of de gebruiker een lokale beheerder op het apparaat is |

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Meer informatie over het schema](advanced-hunting-schema-reference.md)
