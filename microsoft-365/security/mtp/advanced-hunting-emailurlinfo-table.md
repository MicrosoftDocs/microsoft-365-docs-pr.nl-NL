---
title: MailUrlInfo tabel in de geavanceerde jacht schema
description: Meer informatie over URL- of koppelingsgegevens in de tabel EmailUrlInfo van het geavanceerde jachtschema
keywords: geavanceerde jacht, bedreiging jacht, cyber bedreiging jacht, Microsoft threat protection, Microsoft 365, mtp, m365, zoeken, query, telemetrie, schema referentie, kusto, tabel, kolom, gegevenstype, beschrijving, EmailUrlInfo, netwerk bericht id, url, link
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
ms.openlocfilehash: 47486f34f9926d83e52ba206f63d3e85286527dc
ms.sourcegitcommit: eee4f651bd51d5aedd64e42d02bfed8ccb9be4cd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/02/2020
ms.locfileid: "44515817"
---
# <a name="emailurlinfo"></a>EmailUrlInfo

**Van toepassing op:**
- Microsoft Threat Protection

De `EmailUrlInfo` tabel in het geavanceerde [jachtschema](advanced-hunting-overview.md) bevat informatie over URL's op e-mails en bijlagen die door Office 365 ATP worden verwerkt. Gebruik deze verwijzing om query's te construeren die informatie uit deze tabel retourneren.

Zie [de geavanceerde jachtreferentie](advanced-hunting-schema-tables.md)voor informatie over andere tabellen in het geavanceerde jachtschema.

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | Datetime | Datum en tijdstip waarop de gebeurtenis is geregistreerd |
| `UrlId` | Tekenreeks | Unieke id voor de URL in het e-mailonderwerp, de hoofdtekst of de bijlage |
| `NetworkMessageId` | Tekenreeks | Unieke id voor de e-mail, gegenereerd door Microsoft 365 |
| `Url` | Tekenreeks | Volledige URL in het onderwerp, de hoofdtekst of de bijlage van de e-mail |

## <a name="related-topics"></a>Verwante onderwerpen
- [Proactief op zoek naar bedreigingen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Zoek naar bedreigingen op verschillende apparaten en e-mails](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
