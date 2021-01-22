---
title: Werken met geavanceerde queryresultaten in Microsoft 365 Defender
description: Maak zo veel mogelijk gebruik van de queryresultaten die het resultaat zijn van geavanceerd zoeken in Microsoft 365 Defender
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, custom detections, schema, kusto, microsoft 365, Microsoft Threat Protection, visualization, chart, filters, drill-down
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
ms.openlocfilehash: 462ba35f584b45bbfeb0d8a3de3b118ba1c9e17c
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932320"
---
# <a name="work-with-advanced-hunting-query-results"></a>Werken met geavanceerde queryresultaten

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Hoewel u geavanceerde [](advanced-hunting-overview.md) zoekquery's kunt maken om zeer nauwkeurige gegevens te retourneren, kunt u ook met de queryresultaten werken om meer inzicht te krijgen en specifieke activiteiten en indicatoren te onderzoeken. U kunt de volgende acties uitvoeren op uw queryresultaten:

- Resultaten weergeven als een tabel of grafiek
- Tabellen en grafieken exporteren
- Inzoomen op gedetailleerde informatie over de entiteit
- Uw query's rechtstreeks aanpassen aan de hand van de resultaten of filters toepassen

## <a name="view-query-results-as-a-table-or-chart"></a>Queryresultaten weergeven als een tabel of grafiek
Bij geavanceerd zoeken worden queryresultaten standaard weergegeven als tabelgegevens. U kunt dezelfde gegevens ook als een grafiek weergeven. Geavanceerd zoeken ondersteunt de volgende weergaven:

| Weergavetype | Beschrijving |
| -- | -- |
| **Tabel** | Geeft de queryresultaten weer in tabelindeling |
| **Kolomdiagram** | Geeft een reeks unieke items op de x-as weer als verticale balken waarvan de hoogte numerieke waarden uit een ander veld vertegenwoordigt |
| **Gestapeld kolomdiagram** | Geeft een reeks unieke items op de x-as weer als gestapelde verticale balken waarvan de hoogte numerieke waarden uit een of meer andere velden vertegenwoordigt |
| **Cirkeldiagram** | Hiermee worden sectie cirkels weergegeven die unieke items vertegenwoordigen. De grootte van elke cirkel vertegenwoordigt numerieke waarden uit een ander veld. |
| **Donut chart** | Hiermee worden sectiebogen weergegeven die unieke items vertegenwoordigen. De lengte van elke boog vertegenwoordigt numerieke waarden uit een ander veld. |
| **Lijndiagram** | Zet numerieke waarden uit voor een reeks unieke items en verbindt de uitgezet waarden |
| **Spreidingsdiagram** | Numerieke waarden uitlijnen voor een reeks unieke items |
| **Vlakdiagram** | Zet numerieke waarden uit voor een reeks unieke items en vult de secties onder de uitgezete waarden |

### <a name="construct-queries-for-effective-charts"></a>Query's maken voor effectieve grafieken
Bij het weergeven van grafieken herkent geavanceerd zoeken automatisch de aandachtskolommen en de numerieke waarden die moeten worden samengevoegd. Voor een zinvolle grafiek kunt u query's maken om de specifieke waarden te retourneren die u wilt visualiseren. Hier zijn enkele voorbeeldquery's en de resulterende grafieken.

#### <a name="alerts-by-severity"></a>Waarschuwingen op ernst
Gebruik de `summarize` operator om een numerieke telling te verkrijgen van de waarden die u in een grafiek wilt onder brengen. In de onderstaande query wordt `summarize` de operator gebruikt om het aantal waarschuwingen op ernst op te vragen.

```kusto
AlertInfo
| summarize Total = count() by Severity
```
Bij het weergeven van de resultaten wordt in een kolomdiagram elke ernstwaarde als een aparte kolom weergegeven:

![Afbeelding van geavanceerde queryresultaten in de query als kolomdiagram Queryresultaten voor waarschuwingen op ernst ](../../media/advanced-hunting-column-chart.jpg)
 *die als kolomdiagram worden weergegeven*

#### <a name="alert-severity-by-operating-system"></a>Ernst van waarschuwingen per besturingssysteem
U kunt de operator ook gebruiken om de resultaten voor te bereiden voor het in kaart brengen `summarize` van waarden uit meerdere velden. U wilt bijvoorbeeld weten hoe ernst van waarschuwingen is verdeeld over het besturingssysteem. 

De onderstaande query gebruikt een operator om OS-gegevens op te halen uit de tabel en wordt vervolgens gebruikt om waarden in zowel de tabel als de kolommen `join` `DeviceInfo` te `summarize` `OSPlatform` `Severity` tellen:

```kusto
AlertInfo
| join AlertEvidence on AlertId
| join DeviceInfo on DeviceId
| summarize Count = count() by OSPlatform, Severity 
```
Deze resultaten worden het best gevisualiseerd met behulp van een gestapeld kolomdiagram:

![Afbeelding van geavanceerde queryresultaten in een gestapelde grafiek voor waarschuwingen per besturingssysteem en ernst die worden weergegeven ](../../media/advanced-hunting-stacked-chart.jpg)
 *als een gestapelde grafiek*

#### <a name="phishing-emails-across-top-ten-sender-domains"></a>Phishing-e-mailberichten in de tien belangrijkste afzenderdomeinen
Als u te maken hebt met een lijst met waarden die niet is eindig, kunt u de operator gebruiken om alleen de waarden in een grafiek met `Top` de meeste gevallen weer te geven. Gebruik de onderstaande query om de tien topdomeinen met de meeste phishing-e-mailberichten op te halen:

```kusto
EmailEvents
| where PhishFilterVerdict == "Phish"
| summarize Count = count() by SenderFromDomain
| top 10 by Count
```
Gebruik de weergave cirkeldiagram om effectief de verdeling over de belangrijkste domeinen weer te geven:

![Afbeelding van geavanceerde queryresultaten in een cirkeldiagram waarin de distributie van phishing-e-mailberichten over de domeinen van de ](../../media/advanced-hunting-pie-chart.jpg)
 *belangrijkste afzender wordt weergegeven*

#### <a name="file-activities-over-time"></a>Bestandsactiviteiten in de tijd
Met de operator voor de functie kunt u controleren op gebeurtenissen met `summarize` een bepaalde indicator in de `bin()` tijd. Met de onderstaande query worden gebeurtenissen met betrekking tot het bestand geteld met intervallen van 30 minuten om pieken weer te geven in activiteit die `invoice.doc` betrekking heeft op dat bestand:

```kusto
AppFileEvents
| union DeviceFileEvents
| where FileName == "invoice.doc"
| summarize FileCount = count() by bin(Timestamp, 30m)
```
In het onderstaande lijndiagram worden perioden duidelijk aangegeven met meer activiteiten met betrekking `invoice.doc` tot: 

![Afbeelding van geavanceerde queryresultaten in een lijndiagram met het aantal gebeurtenissen voor een bestand ](../../media/advanced-hunting-line-chart.jpg)
 *in de tijd*


## <a name="export-tables-and-charts"></a>Tabellen en grafieken exporteren
Nadat u een query hebt uitgevoerd, **selecteert u Exporteren om** de resultaten op te slaan in een lokaal bestand. De gekozen weergave bepaalt hoe de resultaten worden geëxporteerd:

- **Tabelweergave:** de queryresultaten worden in tabelvorm geëxporteerd als een Microsoft Excel-werkmap
- **Een grafiek:** de queryresultaten worden geëxporteerd als JPEG-afbeelding van de weergegeven grafiek

## <a name="drill-down-from-query-results"></a>Inzoomen op queryresultaten
Als u snel een record in de queryresultaten wilt controleren, selecteert u de bijbehorende rij om het **deelvenster Record controleren te** openen. In het deelvenster wordt de volgende informatie weergegeven op basis van de geselecteerde record:

- **Activa:** samengevatte weergave van de belangrijkste activa (postvakken, apparaten en gebruikers) die in de record zijn gevonden, die worden uitgebreid met beschikbare informatie, zoals risico- en blootstellingsniveaus
- **Processtructuur:** gegenereerd voor records met procesinformatie en wordt gebruikt met behulp van beschikbare contextuele informatie; In het algemeen kunnen query's die meer kolommen retourneren resulteren in uitgebreidere procesbomen.
- **Alle details:** alle waarden uit de kolommen in de record  

![Afbeelding van de geselecteerde record met deelvenster voor het controleren van de record](../../media/mtp-ah/inspect-record.png)

Als u meer informatie wilt weergeven over een specifieke entiteit in uw queryresultaten, zoals een computer, bestand, gebruiker, IP-adres of URL, selecteert u de entiteits-id om een gedetailleerde profielpagina voor die entiteit te openen.

## <a name="tweak-your-queries-from-the-results"></a>Uw query's aanpassen aan de hand van de resultaten
Klik met de rechtermuisknop op een waarde in de resultatenset om uw query snel te verbeteren. U kunt de volgende opties gebruiken:

- De geselecteerde waarde expliciet zoeken `==` ()
- De geselecteerde waarde uitsluiten van de query ( `!=` )
- Geavanceerdere operatoren voor het toevoegen van de waarde aan uw query, `contains` zoals `starts with``ends with` 

![Afbeelding van geavanceerde resultatenset voor zoeken](../../media/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a>De queryresultaten filteren
De rechts weergegeven filters geven een overzicht van de resultatenset. Elke kolom heeft een eigen sectie met de unieke waarden die voor die kolom zijn gevonden en het aantal exemplaren.

Verfijn uw query door de (knoppen) te selecteren op de waarden die u wilt opnemen of uitsluiten en selecteer `+` `-` vervolgens Query **uitvoeren.**

![Afbeelding van geavanceerd zoekfilter](../../media/advanced-hunting-filter.png)

Nadat u het filter hebt toegepast om de query te wijzigen en de query vervolgens uit te voeren, worden de resultaten dienovereenkomstig bijgewerkt.

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Opsporen op apparaten en in e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
- [Overzicht van aangepaste detectie](custom-detections-overview.md)
