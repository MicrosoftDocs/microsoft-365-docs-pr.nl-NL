---
title: E-mailUrlInfo-tabel in het geavanceerde jachtschema
description: Meer informatie over URL- of koppelingsgegevens in de tabel EmailUrlInfo van het geavanceerde jachtschema
keywords: geavanceerde jacht, dreigingjacht, cyberdreigingsjacht, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetrie, schemareferentie, kusto, tabel, kolom, gegevenstype, beschrijving, EmailUrlInfo, netwerkbericht-id, url, link
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
ms.openlocfilehash: 46849aa81da5a615a5dff7c5e2ac28566443d3ee
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633517"
---
# <a name="emailurlinfo"></a>EmailUrlInfo

**Geldt voor:**
- Microsoft Threat Protection



De `EmailUrlInfo` tabel in het [geavanceerde jachtschema](advanced-hunting-overview.md) bevat informatie over URL's op e-mails en bijlagen die zijn verwerkt door Office 365 ATP. Gebruik deze verwijzing om query's te construeren die informatie uit deze tabel retourneren.

Voor informatie over andere tabellen in de geavanceerde jacht schema, [zie de geavanceerde jacht referentie](advanced-hunting-schema-tables.md).

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | Datetime | Datum en tijdstip waarop de gebeurtenis is geregistreerd |
| `UrlId` | Tekenreeks | Unieke id voor de URL in het e-mailonderwerp, de hoofdtekst of de bijlage |
| `NetworkMessageId` | Tekenreeks | Unieke id voor de e-mail, gegenereerd door Microsoft 365 |
| `Url` | Tekenreeks | Volledige URL in het e-mailonderwerp, de hoofdtekst of de bijlage |

## <a name="related-topics"></a>Verwante onderwerpen
- [Proactief op zoek naar bedreigingen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Zoek naar bedreigingen op verschillende apparaten en e-mails](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
