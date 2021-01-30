---
title: Training voor experts op het gebied van geavanceerd zoeken
description: Gratis training en hulp van geavanceerde zoekexperts
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, language, training, scenarios, basic to advanced, videos, step-by-step
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
ms.openlocfilehash: aba0a6ab2c82c038eda8e66890c0c95303dea947
ms.sourcegitcommit: ea8a096df5acedecdce1780969f2b189c3fadf73
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2021
ms.locfileid: "50053833"
---
# <a name="get-expert-training-on-advanced-hunting"></a>Training voor experts op het gebied van geavanceerd zoeken

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

Vernieuw uw kennis van geavanceerd zoeken snel met Het bijhouden van de achtige, een webcastreeks voor nieuwe beveiligingsanalisten en doorgefinterde bedreigingen. De reeks begeleidt u door de basisbeginselen voor het maken van uw eigen geavanceerde query's. Begin met de eerste video over basisprincipes of ga naar geavanceerdere video's die bij uw ervaring passen.


| Title | Omschrijving | Bekijken | Query's | 
|--|--|--|--|
| Aflevering 1: Basisprincipes van KQL | In deze aflevering worden de basisbeginselen van geavanceerd zoeken in Microsoft 365 Defender bestrijkt. Meer informatie over de beschikbare geavanceerde zoekgegevens en basis-KQL-syntaxis en operatoren. | [YouTube](https://youtu.be/0D9TkGjeJwM?t=351) (54:14) | [CSL-bestand](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%201%20-%20KQL%20Fundamentals.csl) |
| Aflevering 2: Joins | Blijf meer te weten komen over gegevens op geavanceerd zoeken en tabellen bij elkaar brengen. Meer informatie over , en joins, en de `inner` `outer` nuances van de standaard `unique` `semi` `innerunique` Kusto-join. | [YouTube](https://youtu.be/LMrO6K5TWOU?t=297) (53:33) | [CSL-bestand](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%202%20-%20Joins.csl) |
| Aflevering 3: gegevens samenvatten, draaien en visualiseren | Nu u gegevens hebt leren filteren, manipuleren en joinen, kunt u gegevens gaan samenvatten, kwantificeren, draaien en visualiseren. In deze aflevering worden de `summarize` operator en verschillende berekeningen besproken en worden aanvullende tabellen in het schema weergegeven. U leert ook hoe u gegevenssets kunt veranderen in grafieken waarmee u inzichten kunt extraheren. | [YouTube](https://youtu.be/UKnk9U1NH6Y?t=296) (48:52) | [CSL-bestand](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%203%20-%20Summarizing%2C%20Pivoting%2C%20and%20Joining.csl) |
| Aflevering 4: Laten we op zoek gaan! KQL toepassen op het bijhouden van incidenten | In deze aflevering leert u om enkele aanvalleractiviteiten bij te houden. We gebruiken ons verbeterde inzicht in Kusto en geavanceerd zoeken om een aanval te volgen. Meer informatie over werkelijke trucs die in het veld worden gebruikt, waaronder de ABCs van uw pc en hoe u deze kunt toepassen op reactie op incidenten. | [YouTube](https://youtu.be/2EUxOc_LNd8?t=291) (59:36) | [CSL-bestand](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%204%20-%20Lets%20Hunt.csl) 


Krijg meer experttraining met *L33TSP3AK: Geavanceerd zoeken in Microsoft 365 Defender,* een webcastreeks voor analisten die hun technische kennis en praktische vaardigheden willen uitbreiden om beveiligingsonderzoeken te leiden met Geavanceerd zoeken in Microsoft 365 Defender. 

| Title | Omschrijving | Bekijken | Query's | 
|--|--|--|--|
| Aflevering 1  | In deze aflevering leert u verschillende best practices bij het uitvoeren van geavanceerde zoekquery's. Een van de onderwerpen die worden besproken zijn: het optimaliseren van uw query's, het gebruik van geavanceerd zoeken naar ransomware, het verwerken van JSON als een dynamisch type en het werken met operatoren voor externe gegevens. | [YouTube](https://www.youtube.com/watch?v=nMGbK-ALaVg&feature=youtu.be) (56:34) | [CSL-bestand](https://github.com/microsoft/Microsoft-365-Defender-Hunting-Queries/blob/master/Webcasts/l33tSpeak/Performance%2C%20Json%20and%20dynamics%20operator%2C%20external%20data.csl)


## <a name="how-to-use-the-csl-file"></a>Het CSL-bestand gebruiken
Voordat u een aflevering begint, gaat u naar het [bijbehorende Kusto CSL-bestand](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/tree/master/Webcasts/TrackingTheAdversary) op GitHub en kopieert u de inhoud naar de geavanceerde queryeditor. Terwijl u een aflevering bekijkt, kunt u de gekopieerde inhoud gebruiken om de spreker te volgen en query's uit te voeren. 

Het volgende fragment uit een CSL-bestand bevat een uitgebreide reeks richtlijnen gemarkeerd met `//` opmerkingen.

```kusto
// DeviceLogonEvents
// A table containing a row for each logon a device enrolled in Microsoft Defender for Endpoint
// Contains
// - Account information associated with the logon
// - The device which the account logged onto
// - The process which performed the logon
// - Network information (for network logons)
// - Timestamp
```

Hetzelfde CSL-bestand bevat query's voor en na de opmerkingen, zoals hieronder wordt weergegeven. Als u een specifieke query wilt uitvoeren met [meerdere query's in](advanced-hunting-query-language.md#work-with-multiple-queries-in-the-editor)de editor, verplaatst u de cursor naar die query en selecteert u **Query uitvoeren.**   

```kusto
DeviceLogonEvents
| count

// DeviceLogonEvents
// A table containing a row for each logon a device enrolled in Microsoft Defender for Endpoint
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
- [De geavanceerde zoekquerytaal leren](advanced-hunting-query-language.md)
- [Werken met queryresultaten](advanced-hunting-query-results.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Opsporen op apparaten en in e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
