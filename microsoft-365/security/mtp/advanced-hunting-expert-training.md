---
title: Professionele training krijgen bij een geavanceerde jacht
description: Gratis training en richtlijnen van geavanceerde jacht experts
keywords: geavanceerde jacht, bedreigings jacht, Cyber Threat jacht, Microsoft Threat Protection, Microsoft 365, MTP, m365, Search, query, taal, training, scenario's, Basic voor Geavanceerd, Video's, stap voor stap
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
ms.openlocfilehash: 23f35c087d55208f7251a6b921cfe7532616742a
ms.sourcegitcommit: 62a8c226422eac9c085cc886b4836b037f95ef6d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/16/2020
ms.locfileid: "47840757"
---
# <a name="get-expert-training-on-advanced-hunting"></a>Professionele training krijgen bij een geavanceerde jacht

**Van toepassing op:**
- Microsoft Threat Protection

Breid uw kennis van geavanceerde jacht snel uit met _het bijhouden van de Adversary_, een webcast reeks voor nieuwe beveiligings analisten en geseizoensgebondene bedreigingen. De reeks begeleidt u door de basisbeginselen voor het maken van uw eigen verfijnde query's. Begin met de eerste video op basis van basisprincipes of ga naar meer geavanceerde Video's die op uw niveau van ervaring passen.


| Title | Beschrijving | Visualisatie | Aanvragen | 
|--|--|--|--|
| Aflevering 1: basisprincipes van KQL | Deze aflevering omvat de basisbeginselen van de geavanceerde jacht in Microsoft Threat Protection. Lees meer over de beschikbare geavanceerde jacht-gegevens en de Basic KQL syntaxis en operatoren. | [YouTube](https://youtu.be/0D9TkGjeJwM?t=351) (54:14) | [CSL-bestand](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%201%20-%20KQL%20Fundamentals.csl) |
| Aflevering 2: joins | Ga verder met het leren van gegevens in de geavanceerde jacht en het samenvoegen van tabellen. Meer informatie over `inner` ,, `outer` `unique` , en `semi` deelnemen en uitleg van de nuances van de standaard `innerunique` join voor Kusto. | [YouTube](https://youtu.be/LMrO6K5TWOU?t=297) (53:33) | [CSL-bestand](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%202%20-%20Joins.csl) |
| Aflevering 3: gegevens samenvatten, draaien en visualiseren | Nu u hebt geleerd hoe u gegevens wilt filteren, manipuleren en samenvoegen, is het tijd om samen te vatten, te kwantificeren, te draaien en te visualiseren. In deze aflevering wordt de `summarize` operator en verschillende berekeningen besproken en worden er extra tabellen in het schema geïntroduceerd. U leert ook gegevenssets omzetten in grafieken die u kunnen helpen om inzicht te verkrijgen. | [YouTube](https://youtu.be/UKnk9U1NH6Y?t=296) (48:52) | [CSL-bestand](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%203%20-%20Summarizing%2C%20Pivoting%2C%20and%20Joining.csl) |
| Aflevering 4: laten we beginnen. KQL toepassen op incidenten bijhouden | In deze aflevering leert u hoe u een deel van de activiteiten van derden bijhoudt. We gebruiken onze verbeterde inzicht in Kusto en de geavanceerde jacht om een aanval bij te houden. Meer informatie over werkelijke trucs die in het veld zijn gebruikt, waaronder de ABCs van Cyber Security en hoe u ze toepast op antwoord op een incident. | [YouTube](https://youtu.be/2EUxOc_LNd8?t=291) (59:36) | [CSL-bestand](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%204%20-%20Lets%20Hunt.csl)

## <a name="how-to-use-the-csl-file"></a>Het CSL-bestand gebruiken
Voordat u een aflevering begint, opent u het bijbehorende [KUSTO CSL-bestand op github](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/tree/master/Webcasts/TrackingTheAdversary) en kopieert u de inhoud hiervan naar de query editor voor geavanceerde jacht. Tijdens het bekijken van een aflevering kunt u de gekopieerde inhoud gebruiken om de luidspreker te volgen en query's uit te voeren. 

Het volgende fragment van een CSL-bestand bevat een uitgebreide set richtlijnen die als opmerkingen zijn gemarkeerd `//` .

```kusto
// DeviceLogonEvents
// A table containing a row for each logon a device enrolled in Defender ATP
// Contains
// - Account information associated with the logon
// - The device which the account logged onto
// - The process which performed the logon
// - Network information (for network logons)
// - Timestamp
```

Het CSL-bestand bevat query's voor en na de opmerkingen, zoals hieronder weergegeven. Als u een specifieke query wilt uitvoeren met [meerdere query's in de editor](advanced-hunting-query-language.md#work-with-multiple-queries-in-the-editor), verplaatst u de cursor naar deze query en selecteert u **query uitvoeren**.   

```kusto
DeviceLogonEvents
| count

// DeviceLogonEvents
// A table containing a row for each logon a device enrolled in Defender ATP
// Contains
// - Account information associated with the logon
// - The device which the account logged onto
// - The process which performed the logon
// - Network information (for network logons)
// - Timestamp

AppFileEvents
| take 100
| sort by Timestamp desc
```
     
## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [Meer informatie over de querytaal Advanced jacht](advanced-hunting-query-language.md)
- [Werken met queryresultaten](advanced-hunting-query-results.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Opsporen op apparaten en in e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)