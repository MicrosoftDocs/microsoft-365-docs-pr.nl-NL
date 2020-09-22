---
title: Geavanceerde jacht limieten in Microsoft Threat Protection
description: Meer informatie over de verschillende service limieten waarmee de Advanced jacht-service kan reageren
keywords: geavanceerde jacht, bedreigings jacht, Cyber Threat jacht, Microsoft Threat Protection, Microsoft 365, MTP, m365, Search, query, Telemetry, schema, kusto, processorlimiet, query limiet, bronnen, maximum resultaten
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
ms.openlocfilehash: aaba01f5970c9abf55f5fae760d1ba1fed8ba914
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48199875"
---
# <a name="advanced-hunting-service-limits"></a>Geavanceerde jacht-service limieten

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft Threat Protection

Om de dienst in werking te houden en op de hoogte te houden, worden in geavanceerde jacht diverse limieten ingesteld voor query's handmatig en op basis van [aangepaste detectieregels](custom-detection-rules.md). Raadpleeg de volgende tabel voor meer informatie over deze limieten.

| Limiet | Grootte | Vernieuwingscyclus | Beschrijving |
|--|--|--|--|
| Gegevensbereik | 30 dagen | Elke query | Met elke query kunnen gegevens worden opgezocht van de afgelopen 30 dagen. |
| Resultatenset | rijen in 10.000 | Elke query | Elke query kan resulteren in 10.000-records. |
| Waar | 10 minuten | Elke query | Een query kan maximaal 10 minuten worden uitgevoerd. Als de service niet binnen 10 minuten wordt voltooid, wordt er een fout weergegeven.
| CPU-resources | Gebaseerd op Tenant grootte | -Op het uur en vervolgens elke 15 minuten<br>-Dagelijks voor 12 middernacht | De service dwingt de dagelijkse en de limiet van 15 minuten apart af. Voor elke limiet wordt in de [Portal een fout weergegeven](advanced-hunting-errors.md) wanneer een query wordt uitgevoerd en de Tenant heeft gekostd via 10% van toegewezen resources. Query's worden geblokkeerd als de Tenant 100% heeft bereikt tot na de volgende dag of een cyclus van 15 minuten. |

>[!NOTE] 
>Er is een aparte set beperkingen van toepassing op geavanceerde zoekopdrachten die via de API worden uitgevoerd. [Meer informatie over geavanceerde jacht-Api's](https://docs.microsoft.com/microsoft-365/security/mtp/api-advanced-hunting)

Klanten die regelmatig meerdere query's uitvoeren, moeten de optie verbruik bijhouden en [Best practices toepassen](advanced-hunting-best-practices.md) om onderbrekingen te beperken die het gevolg zijn van het overschrijden van deze limieten.

## <a name="related-topics"></a>Verwante onderwerpen

- [Best practices voor geavanceerde jacht](advanced-hunting-best-practices.md)
- [Geavanceerde jacht-fouten verwerken](advanced-hunting-errors.md)
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [Overzicht van aangepaste detectie](custom-detections-overview.md)
