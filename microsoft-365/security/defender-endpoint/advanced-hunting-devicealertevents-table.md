---
title: Tabel DeviceAlertEvents in het geavanceerde schema voor de jacht
description: Meer informatie over gebeurtenissen bij het genereren van waarschuwingen in de tabel DeviceAlertEvents van het geavanceerde schema voor de jacht
keywords: advanced hunting, threat hunting, cyber threat hunting, mdatp, microsoft defender atp, microsoft defender for endpoint, wdatp search, query, telemetry, schema reference, kusto, table, column, data type, description, DeviceAlertEvents, alert, ernst, categorie
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
ms.date: 01/22/2020
ms.technology: mde
ms.openlocfilehash: f4f6ecdc57d8602f49fb389c741c5e01dc1b41b5
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939646"
---
# <a name="devicealertevents"></a>DeviceAlertEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)



>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

De `DeviceAlertEvents` tabel in het geavanceerde schema [bevat](advanced-hunting-overview.md) informatie over waarschuwingen in Microsoft Defender-beveiligingscentrum. Gebruik deze verwijzing om query's te maken die gegevens uit de tabel retourneren.

Zie de geavanceerde verwijzing naar het schema voor de jacht voor meer informatie over andere tabellen in het geavanceerde schema voor [de jacht.](advanced-hunting-schema-reference.md)

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `AlertId` | tekenreeks | Unieke id voor de waarschuwing |
| `Timestamp` | datetime | Datum en tijd waarop de gebeurtenis is opgenomen |
| `DeviceId` | tekenreeks | Unieke id voor het apparaat in de service |
| `DeviceName` | tekenreeks | Volledig gekwalificeerde domeinnaam (FQDN) van het apparaat |
| `Severity` | tekenreeks | Geeft het mogelijke effect (hoog, gemiddeld of laag) aan van de bedreigingsindicator of inbreukactiviteit die door de waarschuwing is geïdentificeerd |
| `Category` | tekenreeks | Type bedreigingsindicator of inbreukactiviteit die door de waarschuwing is geïdentificeerd |
| `Title` | tekenreeks | Titel van de waarschuwing |
| `FileName` | tekenreeks | Naam van het bestand waar de opgenomen actie op is toegepast |
| `SHA1` | tekenreeks | SHA-1 van het bestand waar de opgenomen actie op is toegepast |
| `RemoteUrl` | tekenreeks | URL of volledig gekwalificeerde domeinnaam (FQDN) die werd verbonden met |
| `RemoteIP` | tekenreeks | IP-adres dat werd verbonden met |
| `AttackTechniques` | tekenreeks | MITRE ATT&CK-technieken die zijn gekoppeld aan de activiteit die de waarschuwing heeft geactiveerd |
| `ReportId` | lang | Gebeurtenis-id op basis van een herhalende teller. Als u unieke gebeurtenissen wilt identificeren, moet deze kolom worden gebruikt in combinatie met de `DeviceName` kolommen en `Timestamp` de kolommen |
| `Table` | tekenreeks | Tabel met de details van de gebeurtenis |

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Meer informatie over het schema](advanced-hunting-schema-reference.md)
