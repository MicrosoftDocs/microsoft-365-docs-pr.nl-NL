---
title: Tabel DeviceInfo in het geavanceerde schema voor de jacht
description: Meer informatie over besturingssysteem, computernaam en andere apparaatgegevens in de tabel DeviceInfo van het geavanceerde schema voor de jacht
keywords: advanced hunting, threat hunting, cyber threat hunting, search, query, telemetry, schema reference, kusto, table, column, data type, description, deviceinfo, device, OS, platform, users, DeviceInfo
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
ms.openlocfilehash: e86cba39663e96beffc00aa94d6cbcdf7a6e1e42
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059794"
---
# <a name="deviceinfo"></a>DeviceInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)


>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

De tabel in het geavanceerde schema bevat informatie over apparaten in de organisatie, waaronder de `DeviceInfo` besturingssysteemversie, actieve gebruikers en de computernaam. [](advanced-hunting-overview.md) Gebruik deze verwijzing om query's te maken die gegevens uit de tabel retourneren.

Zie de geavanceerde verwijzing naar het schema voor de jacht voor meer informatie over andere tabellen in het geavanceerde schema voor [de jacht.](advanced-hunting-schema-reference.md)

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum en tijd waarop de gebeurtenis is opgenomen |
| `DeviceId` | tekenreeks | Unieke id voor het apparaat in de service |
| `DeviceName` | tekenreeks | Volledig gekwalificeerde domeinnaam (FQDN) van het apparaat |
| `ClientVersion` | tekenreeks | Versie van de eindpuntagent of -sensor die op het apparaat wordt uitgevoerd |
| `PublicIP` | tekenreeks | Openbaar IP-adres dat door het onboarded-apparaat wordt gebruikt om verbinding te maken met de Defender voor Endpoint-service. Dit kan het IP-adres van het apparaat zelf, een NAT-apparaat of een proxy zijn |
| `OSArchitecture` | tekenreeks | Architectuur van het besturingssysteem dat op het apparaat wordt uitgevoerd |
| `OSPlatform` | tekenreeks | Platform van het besturingssysteem dat op het apparaat wordt uitgevoerd. Dit geeft specifieke besturingssystemen aan, waaronder variaties binnen dezelfde familie, zoals Windows 10 en Windows 7 |
| `OSBuild` | tekenreeks | Build-versie van het besturingssysteem dat op het apparaat wordt uitgevoerd |
| `IsAzureADJoined` | booleaanse | Booleaanse indicator van of het apparaat is verbonden met de Azure Active Directory |
| `LoggedOnUsers` | tekenreeks | Lijst met alle gebruikers die zijn aangemeld op het apparaat op het moment van de gebeurtenis in de JSON-matrixindeling |
| `RegistryDeviceTag` | tekenreeks | Apparaatlabel toegevoegd via het register |
| `ReportId` | lang | Gebeurtenis-id op basis van een herhalende teller. Als u unieke gebeurtenissen wilt identificeren, moet deze kolom worden gebruikt in combinatie met de kolommen DeviceName en Timestamp |
| `OSVersion` | tekenreeks | Versie van het besturingssysteem dat op het apparaat wordt uitgevoerd |
| `MachineGroup` | tekenreeks | Machinegroep van de machine. Deze groep wordt gebruikt door op rollen gebaseerd toegangsbeheer om de toegang tot de computer te bepalen |

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Meer informatie over het schema](advanced-hunting-schema-reference.md)
