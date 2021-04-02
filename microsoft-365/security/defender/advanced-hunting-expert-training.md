---
title: Krijg deskundige training over geavanceerd jagen
description: Gratis training en begeleiding van geavanceerde experts op het gebied van jagen
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, language, training, scenarios, basic to advanced, videos, step-by-step
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
ms.openlocfilehash: 3aee0a210b9381174650a4a817be510bcfaa00c2
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498531"
---
# <a name="get-expert-training-on-advanced-hunting"></a>Krijg deskundige training over geavanceerd jagen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

Vergroot uw kennis van geavanceerde jacht snel met _Het bijhouden_ van de tegenpartij, een webcastreeks voor nieuwe beveiligingsanalisten en doorgevinterde bedreigingsjagers. De reeks begeleidt u door de basisbeginselen tot aan het maken van uw eigen geavanceerde query's. Begin met de eerste video over grondbeginselen of ga naar meer geavanceerde video's die passen bij uw ervaringsniveau.

| Title | Omschrijving | Kijken | Query's | 
|--|--|--|--|
| Aflevering 1: KQL-fundamentals | In deze aflevering worden de basisbeginselen van geavanceerde jacht in Microsoft 365 Defender bestrijkt. Meer informatie over beschikbare geavanceerde zoekgegevens en basis-syntaxis en operatoren van KQL. | [YouTube](https://youtu.be/0D9TkGjeJwM?t=351) (54:14) | [CSL-bestand](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%201%20-%20KQL%20Fundamentals.csl) |
| Aflevering 2: Joins | Lees verder over gegevens in geavanceerde zoekprocessen en hoe u tabellen kunt samenbrengen. Lees meer `inner` over `outer` , en `unique` `semi` joins en begrijp de nuances van de standaard `innerunique` Kusto-join. | [YouTube](https://youtu.be/LMrO6K5TWOU?t=297) (53:33) | [CSL-bestand](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%202%20-%20Joins.csl) |
| Aflevering 3: Gegevens samenvatten, draaien en visualiseren | Nu u hebt geleerd gegevens te filteren, te manipuleren en deel te nemen, is het tijd om gegevens samen te vatten, kwantificeren, te draaien en te visualiseren. In deze aflevering worden de operator en verschillende berekeningen besproken, terwijl u aanvullende `summarize` tabellen in het schema introduceert. U leert ook gegevenssets om te zetten in grafieken waarmee u inzicht kunt verkrijgen. | [YouTube](https://youtu.be/UKnk9U1NH6Y?t=296) (48:52) | [CSL-bestand](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%203%20-%20Summarizing%2C%20Pivoting%2C%20and%20Joining.csl) |
| Aflevering 4: Laten we op zoek gaan! KQL toepassen op het bijhouden van incidenten | In deze aflevering leert u hoe u bepaalde activiteiten van aanvallers kunt bijhouden. We gebruiken ons verbeterde begrip van Kusto en geavanceerde jacht om een aanval bij te houden. Leer de werkelijke trucs die in het veld worden gebruikt, waaronder de ABC's van cyberbeveiliging en hoe u deze kunt toepassen op incidentrespons. | [YouTube](https://youtu.be/2EUxOc_LNd8?t=291) (59:36) | [CSL-bestand](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%204%20-%20Lets%20Hunt.csl) 


Krijg meer deskundige training met *L33TSP3AK:* Geavanceerde jacht in Microsoft 365 Defender , een webcastreeks voor analisten die hun technische kennis en praktische vaardigheden willen uitbreiden bij het uitvoeren van beveiligingsonderzoeken met behulp van geavanceerde jacht in Microsoft 365 Defender. 

| Title | Omschrijving | Kijken | Query's | 
|--|--|--|--|
| Aflevering 1  | In deze aflevering leert u verschillende best practices voor het uitvoeren van geavanceerde zoekquery's. Een van de onderwerpen die worden besproken zijn: het optimaliseren van uw query's, het gebruik van geavanceerde zoek naar ransomware, het verwerken van JSON als een dynamisch type en het werken met externe gegevensoperatoren. | [YouTube](https://www.youtube.com/watch?v=nMGbK-ALaVg&feature=youtu.be) (56:34) | [CSL-bestand](https://github.com/microsoft/Microsoft-365-Defender-Hunting-Queries/blob/master/Webcasts/l33tSpeak/Performance%2C%20Json%20and%20dynamics%20operator%2C%20external%20data.csl)


## <a name="how-to-use-the-csl-file"></a>Het CSL-bestand gebruiken
Voordat u een aflevering start, hebt u toegang tot het bijbehorende [CSL-bestand Kusto op GitHub](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/tree/master/Webcasts/TrackingTheAdversary) en kopieert u de inhoud ervan naar de geavanceerde queryeditor. Terwijl u een aflevering bekijkt, kunt u de gekopieerde inhoud gebruiken om de spreker te volgen en query's uit te voeren. 

In het volgende fragment uit een CSL-bestand ziet u een uitgebreide set richtlijnen die zijn gemarkeerd als opmerkingen met `//` .

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

Hetzelfde CSL-bestand bevat query's voor en na de opmerkingen zoals hieronder wordt weergegeven. Als u een specifieke query wilt uitvoeren met [meerdere query's in](advanced-hunting-query-language.md#work-with-multiple-queries-in-the-editor)de editor, verplaatst u de cursor naar die query en selecteert u **Query uitvoeren.**   

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
