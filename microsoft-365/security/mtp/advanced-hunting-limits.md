---
title: Geavanceerde jacht-quota's en gebruiks parameters in Microsoft 365 Defender
description: Meer informatie over diverse quota's en gebruiks parameters (Service limieten) waarmee de Advanced USMT-service kan reageren
keywords: geavanceerde jacht, bedreigings jacht, Cyber Threat jacht, Microsoft Threat Protection, Microsoft 365, MTP, m365, Search, query, Telemetry, schema, kusto, processorlimiet, query limiet, bronnen, maximum resultaten, quota, parameters, toewijzing
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: bab63d9e5939f87f6a1edbf62d256b82552e4fe9
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847366"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a>Geavanceerde jacht-quota's en gebruiks parameters

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

Als u de service wilt blijven gebruiken, stelt u in geavanceerde jacht diverse quota's en gebruiks parameters in (ook wel ' service limieten ' genoemd). Deze quota's en parameters zijn van toepassing op handmatig en door [aangepaste detectieregels](custom-detection-rules.md)worden uitgevoerd. Klanten die regelmatig meerdere query's uitvoeren, moeten verbruik bijhouden en [Best practices toepassen](advanced-hunting-best-practices.md) om onderbrekingen te beperken.

Raadpleeg de volgende tabel voor meer informatie over bestaande quota's en gebruiks parameters.

| Target of parameter | Grootte | Vernieuwingscyclus | Beschrijving |
|--|--|--|--|
| Gegevensbereik | 30 dagen | Elke query | Met elke query kunnen gegevens worden opgezocht van de afgelopen 30 dagen. |
| Resultatenset | rijen in 10.000 | Elke query | Elke query kan resulteren in 10.000-records. |
| Waar | 10 minuten | Elke query | Een query kan maximaal 10 minuten worden uitgevoerd. Als de service niet binnen 10 minuten wordt voltooid, wordt er een fout weergegeven.
| CPU-resources | Gebaseerd op Tenant grootte | -Op het uur en vervolgens elke 15 minuten<br>-Dagelijks voor 12 middernacht | De service belegt de dagelijkse en de quota voor 15 minuten apart af. Voor elk quotum wordt in de [Portal een fout weergegeven](advanced-hunting-errors.md) wanneer een query wordt uitgevoerd en de Tenant is geverbruikt op 10% van toegewezen resources. Query's worden geblokkeerd als de Tenant 100% heeft bereikt tot na de volgende dag of een cyclus van 15 minuten. |

>[!NOTE] 
>Er gelden een aparte set quota's en parameters voor geavanceerde zoekopdrachten die via de API worden uitgevoerd. [Meer informatie over geavanceerde jacht-Api's](https://docs.microsoft.com/microsoft-365/security/mtp/api-advanced-hunting)

## <a name="related-topics"></a>Verwante onderwerpen

- [Best practices voor geavanceerde jacht](advanced-hunting-best-practices.md)
- [Geavanceerde jacht-fouten verwerken](advanced-hunting-errors.md)
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [Overzicht van aangepaste detectie](custom-detections-overview.md)