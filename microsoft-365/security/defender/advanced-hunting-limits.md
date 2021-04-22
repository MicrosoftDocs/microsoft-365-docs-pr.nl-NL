---
title: Geavanceerde jachtquota en gebruiksparameters in Microsoft 365 Defender
description: Inzicht in verschillende quota en gebruiksparameters (servicelimieten) die ervoor zorgen dat de geavanceerde huntingservice reageert
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema, kusto, CPU limit, query limit, resources, maximum results, quota, parameters, allocation
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: c9526363b0430514455db1fbdf12cfb7a18229f1
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932987"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a>Geavanceerde jachtquota en gebruiksparameters

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

Als u de service performant en responsief wilt houden, stelt geavanceerd zoeken verschillende quota's en gebruiksparameters in (ook wel 'servicelimieten' genoemd). Deze quota's en parameters zijn van toepassing op query's die handmatig en volgens [aangepaste detectieregels worden uitgevoerd.](custom-detection-rules.md) Klanten die regelmatig meerdere query's uitvoeren, moeten het verbruik bijhouden en [optimalisatie-best practices](advanced-hunting-best-practices.md) toepassen om onderbrekingen te minimaliseren.

Raadpleeg de volgende tabel om inzicht te krijgen in bestaande quota en gebruiksparameters.

| Quotum of parameter | Grootte | Vernieuwingscyclus | Beschrijving |
|--|--|--|--|
| Gegevensbereik | 30 dagen | Elke query | Elke query kan gegevens opvragen van maximaal de afgelopen 30 dagen. |
| Resultatenset | 10.000 rijen | Elke query | Elke query kan maximaal 10.000 records retourneren. |
| Time-out | 10 minuten | Elke query | Elke query kan maximaal 10 minuten duren. Als de service niet binnen 10 minuten is voltooid, wordt er een fout weergegeven in de service.
| CPU-resources | Op basis van tenantgrootte | - Op het uur en vervolgens om de 15 minuten<br>- Dagelijks om 12:00 uur | De service dwingt het dagelijkse quotum en het quotum van 15 minuten afzonderlijk af. Voor elk quotum wordt in [de portal](advanced-hunting-errors.md) een fout weergegeven wanneer een query wordt uitgevoerd en de tenant meer dan 10% van de toegewezen resources heeft verbruikt. Query's worden geblokkeerd als de tenant 100% heeft bereikt tot na de volgende dagelijkse cyclus of 15 minuten. |

>[!NOTE] 
>Er is een aparte set quota's en parameters van toepassing op geavanceerde query's die via de API worden uitgevoerd. [Meer informatie over geavanceerde api's voor jagen](./api-advanced-hunting.md)

## <a name="related-topics"></a>Verwante onderwerpen

- [Geavanceerde best practices voor jagen](advanced-hunting-best-practices.md)
- [Geavanceerde zoekfouten verwerken](advanced-hunting-errors.md)
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [Overzicht van aangepaste detectie](custom-detections-overview.md)