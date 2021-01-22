---
title: Fouten in geavanceerd zoeken naar Microsoft 365 Defender oplossen
description: Meer informatie over fouten die worden weergegeven bij het gebruik van geavanceerd zoeken
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema, kusto, timeout, resources, errors, unknown error, limits, quota, parameter, allocation
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
ms.openlocfilehash: 645e78de9d7a8a779be8741a7471e9c1a88ba538
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929644"
---
# <a name="handle-advanced-hunting-errors"></a>Geavanceerde zoekfouten verwerken

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


Bij geavanceerd zoeken worden fouten weergegeven die u kunt waarschuwen voor syntaxisfouten en wanneer query's een vooraf gedefinieerde quota en [gebruiksparameters raken.](advanced-hunting-limits.md) Raadpleeg de onderstaande tabel voor tips over het oplossen of voorkomen van fouten.

| Fouttype | Oorzaak | Oplossing | Voorbeelden van foutmeldingen |
|--|--|--|--|
| Syntaxisfouten | De query bevat niet-herkende namen, inclusief verwijzingen naar niet-bestaande operatoren, kolommen, functies of tabellen. | Zorg ervoor dat verwijzingen naar [kusto-operatoren en -functies](https://docs.microsoft.com/azure/data-explorer/kusto/query/) juist zijn. Controleer [het schema](advanced-hunting-schema-tables.md) voor de juiste geavanceerde zoekkolommen, -functies en -tabellen. Sluit variabele tekenreeksen tussen aanhalingstekens zodat ze worden herkend. Gebruik tijdens het schrijven van uw query's de suggesties van IntelliSense voor automatisch aanvullen. | `A recognition error occurred.` |
| Semantische fouten | De query maakt gebruik van geldige operator-, kolom-, functie- of tabelnamen, maar de structuur en de resulterende logica maken fouten. In sommige gevallen wordt bij geavanceerd zoeken de specifieke operator geïdentificeerd die de fout heeft veroorzaakt. | Controleer op fouten in de structuur van de query. Raadpleeg de [documentatie bij Kusto](https://docs.microsoft.com/azure/data-explorer/kusto/query/) voor hulp. Gebruik tijdens het schrijven van uw query's de suggesties van IntelliSense voor automatisch aanvullen. |  `'project' operator: Failed to resolve scalar expression named 'x'`|
| Time-outs | Een query kan slechts binnen een beperkte [periode worden uitgevoerd voordat de time-out wordt uitgevoerd.](advanced-hunting-limits.md) Deze fout kan zich vaker voor doen bij het uitvoeren van complexe query's. | [De query optimaliseren](advanced-hunting-best-practices.md) | `Query exceeded the timeout period.` |
| CPU-beperkingen | Query's in dezelfde tenant hebben de [CPU-bronnen](advanced-hunting-limits.md) overschreden die zijn toegewezen op basis van de grootte van de tenant. | De service controleert elke 15 minuten en dagelijks het CPU-resourcegebruik en geeft waarschuwingen weer nadat het gebruik meer dan 10% van het toegewezen quotum heeft overschreden. Als u het gebruik voor 100% hebt bereikt, worden query's door de service blokkeert tot na de volgende dagelijkse cyclus of na de volgende cyclus van 15 minuten. [Optimaliseer uw query's om te voorkomen dat cpu-quota worden in de problemen komen](advanced-hunting-best-practices.md) | - `This query used X% of your organization's allocated resources for the current 15 minutes.`<br>- `You have exceeded processing resources allocated to this tenant. You can run queries again in <duration>.` |
| Limiet voor resultaatgrootte overschreden  | De totale grootte van de resultatenset voor de query is overschreden. Deze fout kan optreden als de resultatenset zo groot is dat aflopen met de limiet van 10.000 records deze niet kan worden verkleind tot een acceptabele grootte. Resultaten met meerdere kolommen met grote inhoud worden waarschijnlijk beïnvloed door deze fout. | [De query optimaliseren](advanced-hunting-best-practices.md) | `Result size limit exceeded. Use "summarize" to aggregate results, "project" to drop uninteresting columns, or "take" to truncate results.` |
| Overmatig gebruik van resources | De query heeft overtollige hoeveelheden resources verbruikt en is gestopt met voltooien. In sommige gevallen wordt met geavanceerd zoeken de specifieke operator geïdentificeerd die niet is geoptimaliseerd. | [De query optimaliseren](advanced-hunting-best-practices.md) | -`Query stopped due to excessive resource consumption.`<br>-`Query stopped. Adjust use of the <operator name> operator to avoid excessive resource consumption.` |
| Onbekende fouten | De query is vanwege een onbekende reden mislukt. | Probeer de query opnieuw uit te voeren. Neem contact op met Microsoft via de portal als er nog steeds onbekende fouten worden gevonden. | `An unexpected error occurred during query execution. Please try again in a few minutes.`

## <a name="related-topics"></a>Verwante onderwerpen
- [Geavanceerde best practices voor zoeken](advanced-hunting-best-practices.md)
- [Quota en gebruiksparameters](advanced-hunting-limits.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Overzicht van de kusto-querytaal](https://docs.microsoft.com/azure/data-explorer/kusto/query/)
