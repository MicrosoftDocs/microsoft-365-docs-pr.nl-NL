---
title: Fouten afhandelen in de geavanceerde jacht voor Microsoft Threat Protection
description: Wat zijn de fouten die worden weergegeven bij gebruik van geavanceerde jacht
keywords: geavanceerde jacht, bedreigings jacht, Cyber Threat jacht, Microsoft Threat Protection, Microsoft 365, MTP, m365, Search, query, Telemetry, schema, kusto, timeout, bronnen, fouten, onbekende fout, limieten, quota, parameter, toewijzing
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
ms.openlocfilehash: 8b9c46e312d28c7a08efbfa74f96dc33b90fee0a
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/21/2020
ms.locfileid: "48636891"
---
# <a name="handle-advanced-hunting-errors"></a>Geavanceerde jacht-fouten verwerken

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


Met geavanceerde jacht worden fouten weergegeven om te melden bij syntaxisfouten en wanneer query's [vooraf vooraf gedefinieerde quota's en gebruiks parameters](advanced-hunting-limits.md)aanraken. Raadpleeg de onderstaande tabel voor tips over het oplossen of vermijden van fouten.

| Type fout | Oorzaak | Oplossing | Voorbeelden van foutberichten |
|--|--|--|--|
| Syntaxisfouten | De query bevat onbekende namen, waaronder verwijzingen naar niet-bestaande operatoren, kolommen, functies of tabellen. | Zorg ervoor dat verwijzingen naar [operatoren en functies van Kusto](https://docs.microsoft.com/azure/data-explorer/kusto/query/) juist zijn. Controleer [het schema](advanced-hunting-schema-tables.md) voor de juiste geavanceerde jacht kolommen, functies en tabellen. Plaats variabelen reeksen tussen aanhalingstekens zodat deze worden herkend. Gebruik tijdens het schrijven van uw query's de suggesties van automatisch aanvullen van IntelliSense. | `A recognition error occurred.` |
| Semantische fouten | Wanneer de query gebruikmaakt van geldige operator, kolom, functie of tabelnamen, zijn er fouten in de structuur en de bijbehorende logica. In sommige gevallen wordt met geavanceerde jacht de specifieke operator aangegeven die de fout veroorzaakte. | Controleer op fouten in de structuur van de query. Raadpleeg [Kusto documentatie](https://docs.microsoft.com/azure/data-explorer/kusto/query/) voor hulp. Gebruik tijdens het schrijven van uw query's de suggesties van automatisch aanvullen van IntelliSense. |  `'project' operator: Failed to resolve scalar expression named 'x'`|
| Outs | Een query kan slechts binnen een [beperkte periode worden uitgevoerd voordat de tijdsinstelling uitvalt](advanced-hunting-limits.md). Deze fout kan vaak optreden bij het uitvoeren van complexe query's. | [De query optimaliseren](advanced-hunting-best-practices.md) | `Query exceeded the timeout period.` |
| PROCESSOR beperking | Query's in dezelfde Tenant hebben de CPU- [resources](advanced-hunting-limits.md) overschreden die zijn toegewezen op basis van Tenant grootte. | De service controleert het verbruik van CPU-bronnen elke 15 minuten en dagelijks en geeft waarschuwingen weer na gebruik van de toegewezen quota. Als u 100% gebruikt, blok keert de service query's tot na de volgende dag of een cyclus van 15 minuten. [Optimaliseer uw query's om te voorkomen dat u op zoek bent naar CPU-quota](advanced-hunting-best-practices.md) | - `This query used X% of your organization's allocated resources for the current 15 minutes.`<br>- `You have exceeded processing resources allocated to this tenant. You can run queries again in <duration>.` |
| Maximale grootte van resultaten is overschreden  | De totale grootte van de resultatenset voor de query is groter dan de maximale grootte. Deze fout kan optreden als de resultatenset zo groot is dat de afkapping van de limiet voor 10.000-record geen beperking oplevert voor een acceptabel formaat. Resultaten met meerdere kolommen met een aflopende inhoud worden waarschijnlijk beïnvloed door deze fout. | [De query optimaliseren](advanced-hunting-best-practices.md) | `Result size limit exceeded. Use "summarize" to aggregate results, "project" to drop uninteresting columns, or "take" to truncate results.` |
| Buitensporig verbruik van bronnen | De query bevat overtollige bedragen van resources en is gestopt voor voltooien. In sommige gevallen identificeert geavanceerde jacht de specifieke operator die niet is geoptimaliseerd. | [De query optimaliseren](advanced-hunting-best-practices.md) | -`Query stopped due to excessive resource consumption.`<br>-`Query stopped. Adjust use of the <operator name> operator to avoid excessive resource consumption.` |
| Onbekende fouten | De query is mislukt vanwege een onbekende reden. | Voer de query opnieuw uit. Neem contact op met Microsoft via de portal als query's de onbekende fouten blijven retourneren. | `An unexpected error occurred during query execution. Please try again in a few minutes.`

## <a name="related-topics"></a>Verwante onderwerpen
- [Best practices voor geavanceerde jacht](advanced-hunting-best-practices.md)
- [Quota en gebruiks parameters](advanced-hunting-limits.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Overzicht van Kusto query taal](https://docs.microsoft.com/azure/data-explorer/kusto/query/)
