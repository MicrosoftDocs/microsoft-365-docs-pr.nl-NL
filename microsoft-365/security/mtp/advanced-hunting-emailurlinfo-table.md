---
title: Tabel EmailUrlInfo in het geavanceerde jachtschema
description: Meer informatie over URL of linkinformatie in de tabel EmailUrlInfo van het geavanceerde jachtschema
keywords: geavanceerde jacht, bedreigingjacht, cyberdreigingsjacht, microsoft-dreigingsbescherming, microsoft 365, mtp, m365, zoekopdracht, query, telemetrie, schemareferentie, kusto, tabel, kolom, gegevenstype, beschrijving, EmailUrlInfo, netwerkbericht-id, url, link
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
ms.openlocfilehash: 7f5912306700efa0db704fe8d0c0db006105fda6
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/24/2020
ms.locfileid: "42810967"
---
# <a name="emailurlinfo"></a>EmailUrlInfo

**Van toepassing op:**
- Microsoft-bedreigingsbeveiliging



De `EmailUrlInfo` tabel in het [geavanceerde jachtschema](advanced-hunting-overview.md) bevat informatie over URL's over e-mails en bijlagen die zijn verwerkt door Office 365 ATP. Gebruik deze verwijzing om query's te maken die informatie uit deze tabel retourneren.

Zie [de geavanceerde jachtreferentie](advanced-hunting-schema-tables.md)voor informatie over andere tabellen in het geavanceerde jachtschema.

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | Datetime | Datum en tijd waarop de gebeurtenis is geregistreerd |
| `UrlId` | Tekenreeks | Unieke id voor de URL in het e-mailonderwerp, de hoofdtekst of bijlage |
| `NetworkMessageId` | Tekenreeks | Unieke id voor de e-mail, gegenereerd door Office 365 |
| `Url` | Tekenreeks | Volledige URL in het onderwerp, de hoofdtekst of bijlage |

## <a name="related-topics"></a>Verwante onderwerpen
- [Proactief jagen op bedreigingen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Op zoek naar bedreigingen op verschillende apparaten en e-mails](advanced-hunting-query-emails-devices.md)
- [Het schema begrijpen](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
