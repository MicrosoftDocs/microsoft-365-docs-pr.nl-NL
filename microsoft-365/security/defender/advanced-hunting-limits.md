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
ms.openlocfilehash: d7563a8299bbe7d543b065bb25eeb3bc90a854b9
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245598"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a>Geavanceerde jachtquota en gebruiksparameters

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

Als u de service performant en responsief wilt houden, stelt geavanceerd zoeken verschillende quota's en gebruiksparameters in (ook wel 'servicelimieten' genoemd). Deze quota's en parameters zijn afzonderlijk van toepassing op query's die handmatig worden uitgevoerd en op query's die worden uitgevoerd met [aangepaste detectieregels.](custom-detection-rules.md) Klanten die regelmatig meerdere query's uitvoeren, moeten rekening houden met deze limieten en [optimalisatie-best practices](advanced-hunting-best-practices.md) toepassen om onderbrekingen te minimaliseren.

Raadpleeg de volgende tabel om inzicht te krijgen in bestaande quota en gebruiksparameters.

| Quotum of parameter | Grootte | Vernieuwingscyclus | Omschrijving |
|--|--|--|--|
| Gegevensbereik | 30 dagen | Elke query | Elke query kan gegevens opvragen van maximaal de afgelopen 30 dagen. |
| Resultatenset | 10.000 rijen | Elke query | Elke query kan maximaal 10.000 records retourneren. |
| Time-out | 10 minuten | Elke query | Elke query kan maximaal 10 minuten duren. Als de service niet binnen 10 minuten is voltooid, wordt er een fout weergegeven in de service.
| CPU-resources | Op basis van tenantgrootte | Elke 15 minuten | De [portal geeft een fout weer](advanced-hunting-errors.md) wanneer een query wordt uitgevoerd en de tenant meer dan 10% van de toegewezen resources heeft verbruikt. Query's worden geblokkeerd als de tenant 100% heeft bereikt tot na de volgende cyclus van 15 minuten. |

>[!NOTE] 
>Er is een aparte set quota's en parameters van toepassing op geavanceerde query's die via de API worden uitgevoerd. [Meer informatie over geavanceerde api's voor jagen](./api-advanced-hunting.md)

## <a name="related-topics"></a>Verwante onderwerpen

- [Geavanceerde best practices voor jagen](advanced-hunting-best-practices.md)
- [Geavanceerde zoekfouten verwerken](advanced-hunting-errors.md)
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [Overzicht van aangepaste detectie](custom-detections-overview.md)