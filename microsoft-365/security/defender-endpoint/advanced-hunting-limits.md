---
title: Geavanceerde zoeklimieten in Microsoft Defender ATP
description: Verschillende servicelimieten begrijpen die ervoor zorgen dat de geavanceerde huntingservice snel reageert
keywords: advanced hunting, threat hunting, cyber threat hunting, mdatp, microsoft defender atp, wdatp, search, query, telemetry, schema, kusto, CPU limit, query limit, resources, maximum results
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
ms.openlocfilehash: 127ebc8c0eaba433710bc272a2cf602e7c9a9730
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060234"
---
# <a name="advanced-hunting-service-limits"></a>Geavanceerde limieten voor de jachtservice

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)

>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

Als u de service performant en responsief wilt houden, stelt geavanceerd zoeken verschillende limieten in voor query's die handmatig en volgens [aangepaste detectieregels worden uitgevoerd.](custom-detection-rules.md) Raadpleeg de volgende tabel om deze limieten te begrijpen.

| Limiet | Grootte | Vernieuwingscyclus | Beschrijving |
|--|--|--|--|
| Gegevensbereik | 30 dagen | Elke query | Elke query kan gegevens opvragen van maximaal de afgelopen 30 dagen. |
| Resultatenset | 10.000 rijen | Elke query | Elke query kan maximaal 10.000 records retourneren. |
| Time-out | 10 minuten | Elke query | Elke query kan maximaal 10 minuten duren. Als de service niet binnen 10 minuten is voltooid, wordt er een fout weergegeven in de service.
| CPU-resources | Op basis van tenantgrootte | - Op het uur en vervolgens om de 15 minuten<br>- Dagelijks om 12:00 uur | De service dwingt de dagelijkse limiet en de limiet van 15 minuten afzonderlijk af. Voor elke limiet wordt in [de portal](advanced-hunting-errors.md) een fout weergegeven wanneer een query wordt uitgevoerd en de tenant meer dan 10% van de toegewezen resources heeft verbruikt. Query's worden geblokkeerd als de tenant 100% heeft bereikt tot na de volgende dagelijkse cyclus of 15 minuten. |

>[!NOTE] 
>Er is een aparte set limieten van toepassing op geavanceerde query's die via de API worden uitgevoerd. [Meer informatie over geavanceerde api's voor jagen](run-advanced-query-api.md)

Klanten die regelmatig meerdere query's uitvoeren, moeten het verbruik bijhouden en [optimalisatie-best practices](advanced-hunting-best-practices.md) toepassen om verstoringen als gevolg van het overschrijden van deze limieten tot een minimum te beperken.

## <a name="related-topics"></a>Verwante onderwerpen

- [Geavanceerde best practices voor jagen](advanced-hunting-best-practices.md)
- [Geavanceerde zoekfouten verwerken](advanced-hunting-errors.md)
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [Aangepaste detectieregels](custom-detection-rules.md)
