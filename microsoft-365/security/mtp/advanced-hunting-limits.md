---
title: Geavanceerde zoekquota's en gebruiksparameters in Microsoft 365 Defender
description: Inzicht krijgen in verschillende quota's en gebruiksparameters (servicelimieten) die ervoor zorgen dat de geavanceerde zoekservice snel reageert
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema, kusto, CPU limit, query limit, resources, maximum results, quota, parameters, allocation
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 3d3b1055408b51e8d217f2abcb0e83ef7dd74949
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929788"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a>Geavanceerde zoekquota's en gebruiksparameters

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

Om de service snel en snel te houden, stelt geavanceerd zoeken verschillende quota's en gebruiksparameters in (ook wel 'servicelimieten' genoemd). Deze quota en parameters zijn van toepassing op query's die handmatig en volgens aangepaste [detectieregels worden uitgevoerd.](custom-detection-rules.md) Klanten die regelmatig meerdere query's uitvoeren, moeten het verbruik bijhouden en optimalisatieprocedures toepassen [om](advanced-hunting-best-practices.md) onderbrekingen tot een minimum te beperken.

Raadpleeg de volgende tabel om inzicht te krijgen in bestaande quota's en gebruiksparameters.

| Quotum of parameter | Grootte | Vernieuwingscyclus | Beschrijving |
|--|--|--|--|
| Gegevensbereik | 30 dagen | Elke query | Met elke query kunnen gegevens van de afgelopen 30 dagen worden opgevraagd. |
| Resultaatset | 10.000 rijen | Elke query | Elke query kan maximaal 10.000 records retourneren. |
| Timeout | 10 minuten | Elke query | Elke query kan maximaal 10 minuten worden uitgevoerd. Als de taak niet binnen 10 minuten wordt voltooid, wordt er een foutbericht weergegeven.
| CPU-bronnen | Op basis van de grootte van de tenant | - Op het uur en vervolgens elke 15 minuten<br>- Dagelijks om 12 middernacht | De service dwingt de dagelijkse limiet en het quotum van 15 minuten afzonderlijk af. Voor elk quotum wordt [in de portal](advanced-hunting-errors.md) een fout weergegeven wanneer een query wordt uitgevoerd en de tenant meer dan 10% van de toegewezen resources heeft verbruikt. Query's worden geblokkeerd als de tenant 100% heeft bereikt tot na de volgende dagelijkse cyclus of 15 minuten. |

>[!NOTE] 
>Er is een afzonderlijke set quota's en parameters van toepassing op geavanceerde zoekquery's die worden uitgevoerd via de API. [Meer informatie over geavanceerde api's voor zoeken](https://docs.microsoft.com/microsoft-365/security/mtp/api-advanced-hunting)

## <a name="related-topics"></a>Verwante onderwerpen

- [Geavanceerde best practices voor zoeken](advanced-hunting-best-practices.md)
- [Geavanceerde zoekfouten verwerken](advanced-hunting-errors.md)
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [Overzicht van aangepaste detectie](custom-detections-overview.md)