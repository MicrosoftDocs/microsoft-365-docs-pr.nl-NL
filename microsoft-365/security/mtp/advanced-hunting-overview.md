---
title: Overzicht van geavanceerde jacht in Microsoft Threat Protection
description: Meer informatie over geavanceerde jachtquery's in Microsoft 365 en hoe u deze gebruiken om bedreigingen en zwakke punten in uw netwerk proactief te vinden
keywords: geavanceerde jacht, dreigingsjacht, cyberdreigingsjacht, bescherming tegen microsoft-bedreigingen, microsoft 365, mtp, m365, zoeken, query, telemetrie, aangepaste detecties, schema, kusto, microsoft 365, Microsoft Threat Protection
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
ms.openlocfilehash: 598ef669e95081ef098dfa9cfdb5473b21b28306
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/24/2020
ms.locfileid: "42810454"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-threat-protection"></a>Proactief op zoek naar bedreigingen met geavanceerde jacht in Microsoft Threat Protection

**Van toepassing op:**
- Microsoft-bedreigingsbeveiliging



Geavanceerde jacht is een query-gebaseerde bedreiging-jacht tool waarmee u verkennen tot 30 dagen van ruwe gegevens. U gebeurtenissen in uw netwerk proactief inspecteren om interessante indicatoren en entiteiten te vinden. De flexibele toegang tot gegevens vergemakkelijkt de ongedwongen jacht op zowel bekende als potentiële bedreigingen.

In het Microsoft 365-beveiligingscentrum ondersteunt advanced hunting query's die gegevens van zowel Microsoft Defender ATP, die gegevens van apparaten aan boord bevatten, als Office 365 ATP, die gegevens uit e-mails verstrekken. Als u geavanceerde jacht wilt gebruiken, [schakelt u Microsoft Threat Protection in.](mtp-enable.md)

## <a name="get-started-with-advanced-hunting"></a>Aan de slag met geavanceerde jacht

We raden aan om verschillende stappen te doorlopen om snel aan de slag te gaan met geavanceerde jacht.

| Leerdoel | Beschrijving | Resource |
|--|--|--|
| **Krijg een gevoel voor de taal** | Geavanceerde jacht is gebaseerd op de [Kusto-querytaal,](https://docs.microsoft.com/azure/kusto/query/)die dezelfde syntaxis en operatoren ondersteunt. Begin met het leren van de querytaal door uw eerste query uit te voeren. | [Overzicht van querytalen](advanced-hunting-query-language.md) |
| **Het schema begrijpen** | Krijg een goed, hoog niveau inzicht in de tabellen in het schema en hun kolommen. Zo u bepalen waar u naar gegevens moet zoeken en hoe u uw query's samenstellen. | [Schemaverwijzing](advanced-hunting-schema-tables.md) |
| **Vooraf gedefinieerde query's gebruiken** | Bekijk verzamelingen van vooraf gedefinieerde query's die verschillende scenario's voor bedreigingsjacht behandelen. | [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
| **Query's optimaliseren** | Meer informatie over het maken van efficiënte query's en query's die gegevens van e-mails en apparaten combineren. | [Best practices opvragen,](advanced-hunting-shared-queries.md) [op zoek naar apparaten en e-mails](advanced-hunting-best-practices.md)

## <a name="get-help-as-you-write-queries"></a>Hulp krijgen bij het schrijven van query's
Profiteer van de volgende functionaliteit om sneller query's te schrijven:
- **Autosuggest** - als je query's schrijft, geavanceerde jacht biedt suggesties. 
- **Schemaverwijzing** : naast uw werkgebied wordt een schemaverwijzing weergegeven met de lijst met tabellen en hun kolommen. Voor meer informatie, zweven over een item. Dubbelklik op een item om het in te voegen in de queryeditor.

## <a name="drilldown-from-query-results"></a>Drilldown van queryresultaten
Als u meer informatie wilt weergeven over entiteiten, zoals machines, bestanden, gebruikers, IP-adressen en URL's, klikt u in uw queryresultaten op de entiteits-id. Hiermee wordt een gedetailleerde profielpagina geopend voor de geselecteerde entiteit in Microsoft Defender Security Center.

## <a name="tweak-your-queries-from-the-results"></a>Uw query's aanpassen aan de resultaten
Klik met de rechtermuisknop op een waarde in de resultatenset om uw query snel te verbeteren. U de opties gebruiken om:

- Expliciet zoeken naar de`==`geselecteerde waarde ( )
- De geselecteerde waarde uitsluiten`!=`van de query ( )
- Meer geavanceerde operators voor het toevoegen van `contains`de `starts with` waarde aan uw query, zoals , en`ends with` 

![Afbeelding van Microsoft Defender ATP geavanceerde jacht resultaat set](../../media/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a>De queryresultaten filteren
De filters die rechts worden weergegeven, geven een overzicht van de resultatenset. Elke kolom heeft een eigen sectie met de verschillende waarden die voor die kolom zijn gevonden en het aantal exemplaren.

Verfijn uw query door de knoppen '+' of '-' te selecteren op de waarden die u wilt opnemen of uit te sluiten en vervolgens **Query uitvoeren**te selecteren .

![Beeld van geavanceerd jachtfilter](../../media/advanced-hunting-filter.png)

Zodra u het filter toepast om de query te wijzigen en de query vervolgens uit te voeren, worden de resultaten dienovereenkomstig bijgewerkt.

## <a name="related-topics"></a>Verwante onderwerpen
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Zoek naar bedreigingen op verschillende apparaten en e-mails](advanced-hunting-query-emails-devices.md)
- [Het schema begrijpen](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
