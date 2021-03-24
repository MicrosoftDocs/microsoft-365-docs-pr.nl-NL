---
title: Fouten in geavanceerde zoek naar Microsoft Defender ATP verwerken
description: Inzicht in fouten die worden weergegeven bij het gebruik van geavanceerde jacht
keywords: advanced hunting, threat hunting, cyber threat hunting, mdatp, microsoft defender atp, wdatp, m365, search, query, telemetry, schema, kusto, time-out, resources, fouten, onbekende fout
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
ms.openlocfilehash: 64c8a13ba9e8110d761245315969b9e1882b3448
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059998"
---
# <a name="handle-advanced-hunting-errors"></a>Geavanceerde zoekfouten verwerken

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)


>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

Bij geavanceerd zoeken worden fouten weergegeven om te waarschuwen voor syntaxisfouten en wanneer query's vooraf [gedefinieerde limieten raken.](advanced-hunting-limits.md) Raadpleeg de onderstaande tabel voor tips over het oplossen of voorkomen van fouten. 

| Fouttype | Oorzaak | Oplossing | Voorbeelden van foutmeldingen |
|--|--|--|--|
| Syntaxisfouten | De query bevat niet-herkende namen, waaronder verwijzingen naar niet-bestaande operatoren, kolommen, functies of tabellen. | Zorg ervoor dat verwijzingen naar [Kusto-operatoren en -functies](https://docs.microsoft.com/azure/data-explorer/kusto/query/) juist zijn. Controleer [het schema](advanced-hunting-schema-reference.md) voor de juiste geavanceerde zoekkolommen, functies en tabellen. Sluit variabele tekenreeksen tussen aanhalingstekens zodat ze worden herkend. Gebruik tijdens het schrijven van uw query's de suggesties voor automatisch aanvullen van IntelliSense. | `A recognition error occurred.` |
| Semantische fouten | Hoewel voor de query geldige operator- of kolom-, functie- of tabelnamen worden gebruikt, zijn er fouten in de structuur en de resulterende logica. In sommige gevallen identificeert geavanceerd zoeken de specifieke operator die de fout heeft veroorzaakt. | Controleer op fouten in de structuur van de query. Raadpleeg [Kusto-documentatie voor](https://docs.microsoft.com/azure/data-explorer/kusto/query/) richtlijnen. Gebruik tijdens het schrijven van uw query's de suggesties voor automatisch aanvullen van IntelliSense. |  `'project' operator: Failed to resolve scalar expression named 'x'`|
| Time-outs | Een query kan slechts binnen een beperkte periode [worden uitgevoerd voordat de tijdsinstellingen zijn uitgelopen.](advanced-hunting-limits.md) Deze fout kan vaker voorkomen bij het uitvoeren van complexe query's. | [De query optimaliseren](advanced-hunting-best-practices.md) | `Query exceeded the timeout period.` |
| CPU-beperking | Query's in dezelfde tenant hebben de [CPU-resources](advanced-hunting-limits.md) overschreden die zijn toegewezen op basis van tenantgrootte. | De service controleert het cpu-resourcegebruik elke 15 minuten en dagelijks en geeft waarschuwingen weer nadat het gebruik meer dan 10% van de toegewezen limiet overschrijdt. Als u 100% gebruik bereikt, worden query's door de service tot na de volgende dagelijkse cyclus of 15 minuten verwijderd. [Uw query's optimaliseren om te voorkomen dat cpu-limieten worden bereikt](advanced-hunting-best-practices.md) | - `This query used X% of your organization's allocated resources for the current 15 minutes.`<br>- `You have exceeded processing resources allocated to this tenant. You can run queries again in <duration>.` |
| Limiet voor de grootte van het resultaat overschreden  | De statistische grootte van de resultatenset voor de query heeft de maximumlimiet overschreden. Deze fout kan optreden als de resultatenset zo groot is dat de limiet van 10.000 records niet kan worden verkleind tot een acceptabele grootte. Resultaten met meerdere kolommen met aanzienlijke inhoud worden waarschijnlijk beïnvloed door deze fout. | [De query optimaliseren](advanced-hunting-best-practices.md) | `Result size limit exceeded. Use "summarize" to aggregate results, "project" to drop uninteresting columns, or "take" to truncate results.` |
| Overmatig verbruik van resources | De query heeft te veel resources verbruikt en is niet meer uitgevoerd. In sommige gevallen identificeert geavanceerd zoeken de specifieke operator die niet is geoptimaliseerd. | [De query optimaliseren](advanced-hunting-best-practices.md) | -`Query stopped due to excessive resource consumption.`<br>-`Query stopped. Adjust use of the <operator name> operator to avoid excessive resource consumption.` |
| Onbekende fouten | De query is mislukt vanwege een onbekende reden. | Probeer de query opnieuw uit te voeren. Neem contact op met Microsoft via de portal als query's onbekende fouten blijven retourneren. | `An unexpected error occurred during query execution. Please try again in a few minutes.`

## <a name="related-topics"></a>Verwante onderwerpen
- [Geavanceerde best practices voor jagen](advanced-hunting-best-practices.md)
- [Servicelimieten](advanced-hunting-limits.md)
- [Meer informatie over het schema](advanced-hunting-schema-reference.md)
- [Overzicht van kustoquerytaal](https://docs.microsoft.com/azure/data-explorer/kusto/query/)