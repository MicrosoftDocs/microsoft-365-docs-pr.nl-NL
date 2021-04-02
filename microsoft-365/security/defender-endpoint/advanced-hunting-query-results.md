---
title: Werken met geavanceerde zoekqueryresultaten in Microsoft Defender ATP
description: Maak gebruik van de queryresultaten die worden geretourneerd door geavanceerd zoeken in Microsoft Defender ATP
keywords: advanced hunting, threat hunting, cyber threat hunting, mdatp, microsoft defender atp, wdatp search, query, telemetry, custom detections, schema, kusto, visualisatie, grafiek, filters, inzoomen
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4abec618a79704804b5e3349f5c4c5a4827d35ef
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499434"
---
# <a name="work-with-advanced-hunting-query-results"></a>Werken met geavanceerde resultaten van query's

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)

>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

Hoewel u geavanceerde [](advanced-hunting-overview.md) zoekquery's kunt maken om zeer nauwkeurige informatie te retourneren, kunt u ook met de queryresultaten werken om meer inzicht te krijgen en specifieke activiteiten en indicatoren te onderzoeken. U kunt de volgende acties uitvoeren voor de queryresultaten:

- Resultaten weergeven als een tabel of grafiek
- Tabellen en grafieken exporteren
- Inzoomen op gedetailleerde entiteitsgegevens
- Uw query's rechtstreeks aanpassen aan de resultaten of filters toepassen

## <a name="view-query-results-as-a-table-or-chart"></a>Queryresultaten weergeven als een tabel of grafiek
Standaard worden queryresultaten in geavanceerde query's weergegeven als tabelgegevens. U kunt ook dezelfde gegevens als een grafiek weergeven. Geavanceerde jacht ondersteunt de volgende weergaven:

| Weergavetype | Omschrijving |
| -- | -- |
| **Tabel** | Geeft de queryresultaten weer in tabelvorm |
| **Kolomdiagram** | Geeft een reeks unieke items op de x-as weer als verticale balken waarvan de hoogten numerieke waarden uit een ander veld vertegenwoordigen |
| **Gestapeld kolomdiagram** | Geeft een reeks unieke items op de x-as weer als gestapelde verticale balken waarvan de hoogten numerieke waarden uit een of meer andere velden vertegenwoordigen |
| **Cirkeldiagram** | Hiermee worden sectie-cirkels weergegeven die unieke items vertegenwoordigen. De grootte van elke cirkel vertegenwoordigt numerieke waarden uit een ander veld. |
| **Donut-diagram** | Hiermee worden sectiebogen weergegeven die unieke items vertegenwoordigen. De lengte van elke boog vertegenwoordigt numerieke waarden uit een ander veld. |
| **Lijndiagram** | Plots numerieke waarden voor een reeks unieke items en verbindt de uitgezete waarden |
| **Spreidingsdiagram** | Numerieke waarden voor een reeks unieke items plots |
| **Vlakdiagram** | Plots numerieke waarden voor een reeks unieke items en vult de secties onder de uitgezete waarden |

### <a name="construct-queries-for-effective-charts"></a>Query's maken voor effectieve grafieken
Bij het weergeven van grafieken worden met geavanceerde jacht automatisch de kolommen met interesse en de numerieke waarden geïdentificeerd die moeten worden samengevoegd. Als u zinvolle grafieken wilt krijgen, maakt u uw query's om de specifieke waarden te retourneren die u wilt visualiseren. Hier zijn enkele voorbeeldquery's en de resulterende grafieken.

#### <a name="alerts-by-severity"></a>Waarschuwingen op ernst
Gebruik de operator om een numeriek aantal waarden te verkrijgen dat `summarize` u wilt grafieken. In de onderstaande query wordt `summarize` de operator gebruikt om het aantal waarschuwingen op ernst te krijgen.

```kusto
DeviceAlertEvents
| summarize Total = count() by Severity
```
Bij het weergeven van de resultaten wordt in een kolomdiagram elke ernstwaarde weergegeven als een afzonderlijke kolom:

![Afbeelding van geavanceerde resultaten van query's die worden weergegeven als kolomdiagram Queryresultaten voor waarschuwingen op ernst die als ](images/advanced-hunting-column-chart.jpg)
 *kolomdiagram worden weergegeven*

#### <a name="alert-severity-by-operating-system"></a>Ernst van waarschuwing per besturingssysteem
U kunt de operator ook `summarize` gebruiken om resultaten voor te bereiden voor het in kaart brengen van waarden uit meerdere velden. U wilt bijvoorbeeld weten hoe de ernst van waarschuwingen wordt verdeeld over besturingssystemen (OS). 

In de onderstaande query wordt een operator gebruikt om besturingssysteemgegevens uit de tabel te halen en vervolgens waarden in zowel de tabel als `join` `DeviceInfo` de kolommen te `summarize` `OSPlatform` `Severity` tellen:

```kusto
DeviceAlertEvents
| join DeviceInfo on DeviceId
| summarize Count = count() by OSPlatform, Severity
```
Deze resultaten worden het best gevisualiseerd met behulp van een gestapeld kolomdiagram:

![Afbeelding van geavanceerde resultaten van query's die worden weergegeven als een gestapelde grafiek Queryresultaten voor waarschuwingen per besturingssysteem en ernst die worden weergegeven ](images/advanced-hunting-stacked-chart.jpg)
 *als een gestapelde grafiek*

#### <a name="top-ten-device-groups-with-alerts"></a>Tien apparaatgroepen met waarschuwingen
Als u te maken hebt met een lijst met waarden die niet eindig is, kunt u de operator gebruiken om alleen de waarden met de meeste `Top` exemplaren in kaart te brengen. Als u bijvoorbeeld de tien beste apparaatgroepen met de meeste waarschuwingen wilt krijgen, gebruikt u de onderstaande query:

```kusto
DeviceAlertEvents
| join DeviceInfo on DeviceId
| summarize Count = count() by MachineGroup
| top 10 by Count
```
Gebruik de cirkeldiagramweergave om de verdeling over de bovenste groepen effectief weer te geven:

![Afbeelding van geavanceerde resultaten van query's die worden weergegeven als cirkeldiagram Cirkeldiagram met ](images/advanced-hunting-pie-chart.jpg)
 *de verdeling van waarschuwingen over apparaatgroepen*

#### <a name="malware-detections-over-time"></a>Malwaredetecties in de tijd
Met behulp `summarize` van de operator met de functie kunt u controleren op gebeurtenissen met een bepaalde indicator in de `bin()` tijd. Met de onderstaande query worden detecties van een EICAR-testbestand met intervallen van 30 minuten geteld om pieken in detecties van dat bestand weer te geven:

```kusto
DeviceEvents
| where ActionType == "AntivirusDetection"
| where SHA1 == "3395856ce81f2b7382dee72602f798b642f14140"
| summarize Detections = count() by bin(Timestamp, 30m)
```
In het lijndiagram hieronder worden duidelijk perioden met meer detecties van de testmalware belicht: 

![Afbeelding van geavanceerde resultaten van query's die worden weergegeven als lijndiagram Lijndiagram met het aantal detecties van ](images/advanced-hunting-line-chart.jpg)
 *een test malware in de tijd*


## <a name="export-tables-and-charts"></a>Tabellen en grafieken exporteren
Nadat u een query hebt uitgevoerd, **selecteert u Exporteren om** de resultaten op te slaan in een lokaal bestand. De gekozen weergave bepaalt hoe de resultaten worden geëxporteerd:

- **Tabelweergave:** de queryresultaten worden in tabelvorm geëxporteerd als een Microsoft Excel-werkmap
- **Een grafiek:** de queryresultaten worden geëxporteerd als EEN JPEG-afbeelding van de weergegeven grafiek

## <a name="drill-down-from-query-results"></a>Inzoomen op queryresultaten
Als u meer informatie wilt weergeven over entiteiten, zoals apparaten, bestanden, gebruikers, IP-adressen en URL's, klikt u in de queryresultaten op de entiteit-id. Hiermee wordt een gedetailleerde profielpagina voor de geselecteerde entiteit geopend.

Als u snel een record in de queryresultaten wilt controleren, selecteert u de bijbehorende rij om het deelvenster Record controleren te openen. Het deelvenster bevat de volgende informatie op basis van de geselecteerde record:

- **Activa:** een samengevatte weergave van de belangrijkste activa (postvakken, apparaten en gebruikers) die in de record zijn gevonden, aangevuld met beschikbare informatie, zoals risico- en blootstellingsniveaus
- **Processtructuur:** een grafiek die wordt gegenereerd voor records met procesgegevens en die is uitgebreid met behulp van beschikbare contextuele informatie; Query's die meer kolommen retourneren, kunnen over het algemeen leiden tot rijkere procesbomen.
- **Alle details:** bevat alle waarden uit de kolommen in de record

## <a name="tweak-your-queries-from-the-results"></a>Uw query's aanpassen aan de hand van de resultaten
Klik met de rechtermuisknop op een waarde in de resultatenset om de query snel te verbeteren. U kunt de opties gebruiken om:

- Zoek expliciet naar de geselecteerde waarde ( `==` )
- De geselecteerde waarde uitsluiten van de query ( `!=` )
- Meer geavanceerde operatoren voor het toevoegen van de waarde aan uw query, zoals `contains` , `starts with` en `ends with` 

![Afbeelding van geavanceerde resultatenset voor de jacht](images/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a>De queryresultaten filteren
De filters die in het rechterdeelvenster worden weergegeven, geven een overzicht van de resultatenset. Elke kolom heeft een eigen sectie in het deelvenster, met elk de waarden in die kolom en het aantal exemplaren.

Verfijn de query door de of knoppen te selecteren op de waarden `+` die u wilt opnemen of `-` uitsluiten. Selecteer vervolgens **Query uitvoeren.**

![Afbeelding van geavanceerd zoekfilter](images/advanced-hunting-filter.png)

Nadat u het filter hebt toegepast om de query te wijzigen en de query vervolgens uit te voeren, worden de resultaten dienovereenkomstig bijgewerkt.

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Meer informatie over het schema](advanced-hunting-schema-reference.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
- [Overzicht van aangepaste detectie](overview-custom-detections.md)
