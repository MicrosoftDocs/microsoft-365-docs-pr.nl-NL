---
title: Werken met geavanceerde resultaten van jachtquery's in Microsoft Threat Protection
description: Haal het meeste uit de queryresultaten die zijn geretourneerd door geavanceerde jacht in Microsoft Threat Protection
keywords: geavanceerde jacht, dreigingjacht, cyberdreigingsjacht, bescherming tegen microsoft-bedreigingen, microsoft 365, mtp, m365, zoeken, query, telemetrie, aangepaste detecties, schema, kusto, microsoft 365, Microsoft Threat Protection, visualisatie, grafiek, filters, inzoomen
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
ms.openlocfilehash: f9838908ca0dbfb498601c3509b920b064a2eb22
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929149"
---
# <a name="work-with-advanced-hunting-query-results"></a>Werken met geavanceerde resultaten van jachtquery's

**Van toepassing op:**
- Microsoft-bedreigingsbeveiliging

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Hoewel u uw [geavanceerde jachtquery's](advanced-hunting-overview.md) samenstellen om zeer nauwkeurige informatie terug te geven, u ook met de queryresultaten werken om meer inzicht te krijgen en specifieke activiteiten en indicatoren te onderzoeken. U de volgende acties uitvoeren op uw queryresultaten:

- Resultaten weergeven als een tabel of grafiek
- Tabellen en grafieken exporteren
- Inzoomen op gedetailleerde entiteitsinformatie
- Uw query's rechtstreeks vanuit de resultaten aanpassen of filters toepassen

## <a name="view-query-results-as-a-table-or-chart"></a>Queryresultaten weergeven als een tabel of grafiek
Geavanceerde jacht geeft standaard queryresultaten weer als tabelgegevens. U ook dezelfde gegevens weergeven als een grafiek. Geavanceerde jacht ondersteunt de volgende standpunten:

| Weergavetype | Beschrijving |
| -- | -- |
| **Tabel** | Geeft de queryresultaten in tabelindeling weer |
| **Kolomdiagram** | Hiermee wordt een reeks unieke items op de x-as weergegeven als verticale balken waarvan de hoogte smeudatumewaarden uit een ander veld vertegenwoordigen |
| **Gestapeld kolomdiagram** | Hiermee worden een reeks unieke items op de x-as weergegeven als gestapelde verticale balken waarvan de hoogtes numerieke waarden van een of meer andere velden vertegenwoordigen |
| **Cirkeldiagram** | Renders sectionele taarten die unieke items vertegenwoordigen. De grootte van elke cirkel vertegenwoordigt numerieke waarden uit een ander veld. |
| **Donutdiagram** | Hiermee worden sectionele bogen weergegeven die unieke items vertegenwoordigen. De lengte van elke boog vertegenwoordigt numerieke waarden uit een ander veld. |
| **Lijndiagram** | Hiermee worden numerieke waarden voor een reeks unieke items inkaart en de uitgezette waarden met elkaar verbonden |
| **Spreidingsdiagram** | Numerieke waarden voor een reeks unieke items in- en uitplannen |
| **Gebiedsdiagram** | Hiermee worden numerieke waarden voor een reeks unieke items inkaart en worden de secties onder de uitgezette waarden gevuld |

### <a name="construct-queries-for-effective-charts"></a>Query's maken voor effectieve grafieken
Bij het renderen van grafieken identificeert geavanceerde jacht automatisch kolommen van belang en de numerieke waarden die u wilt samenvoegen. Als u zinvolle grafieken wilt maken, maakt u uw query's om de specifieke waarden die u wilt zien, gevisualiseerd weer te geven. Hier volgen enkele voorbeeldquery's en de resulterende grafieken.

#### <a name="alerts-by-severity"></a>Waarschuwingen op ernst
Gebruik `summarize` de operator om een numeriek aantal te verkrijgen van de waarden die u wilt in kaart brengen. De onderstaande `summarize` query gebruikt de operator om het aantal waarschuwingen per ernst te krijgen.

```kusto
AlertInfo
| summarize Total = count() by Severity
```
Bij het renderen van de resultaten geeft een kolomdiagram elke ernstwaarde weer als een afzonderlijke kolom:

![Afbeelding van geavanceerde resultaten van de](../../media/advanced-hunting-column-chart.jpg)
jachtquery die worden weergegeven als een kolomdiagram*Queryresultaten voor waarschuwingen op ernst die worden weergegeven als een kolomdiagram*

#### <a name="alert-severity-by-operating-system"></a>Ernst van de waarschuwing per besturingssysteem
U de `summarize` operator ook gebruiken om resultaten voor te bereiden op het in kaart brengen van waarden uit meerdere velden. U wilt bijvoorbeeld begrijpen hoe waarschuwingsernst over besturingssystemen (os) wordt verdeeld. 

De onderstaande `join` query gebruikt een operator `DeviceInfo` om OS-informatie `summarize` uit de tabel `OSPlatform` `Severity` op te halen en vervolgens te gebruiken om waarden in zowel de kolommen als de kolommen te tellen:

```kusto
AlertInfo
| join AlertEvidence on AlertId
| join DeviceInfo on DeviceId
| summarize Count = count() by OSPlatform, Severity 
```
Deze resultaten kunnen het beste worden gevisualiseerd met behulp van een gestapeld kolomdiagram:

![Afbeelding van geavanceerde resultaten van de jachtquery die worden weergegeven als een gestapeld grafiek](../../media/advanced-hunting-stacked-chart.jpg)
*Queryresultaten voor waarschuwingen per besturingssysteem en ernst die worden weergegeven als een gestapeld diagram*

#### <a name="phishing-emails-across-top-ten-sender-domains"></a>Phishing-e-mails in top tien afzenderdomeinen
Als u te maken hebt met een lijst met waarden `Top` die niet eindig zijn, u de operator gebruiken om alleen de waarden met de meeste instanties in kaart te brengen. Bijvoorbeeld, om de top tien afzender domeinen met de meeste phishing e-mails te krijgen, gebruik maken van de onderstaande query:

```kusto
EmailEvents
| where PhishFilterVerdict == "Phish"
| summarize Count = count() by SenderFromDomain
| top 10 by Count
```
Gebruik de grafiekweergave om de distributie over de topdomeinen effectief weer te geven:

![Afbeelding van geavanceerde resultaten van jachtquery's die worden weergegeven als een cirkeldiagram](../../media/advanced-hunting-pie-chart.jpg)
*Cirkeldiagram met de distributie van phishing-e-mails over topdomeinen van afzenders*

#### <a name="file-activities-over-time"></a>Bestandsactiviteiten in de loop van de tijd
Met `summarize` behulp van `bin()` de operator met de functie, u controleren op gebeurtenissen waarbij een bepaalde indicator in de tijd. De onderstaande query telt `invoice.doc` gebeurtenissen met het bestand met intervallen van 30 minuten om pieken in activiteit met betrekking tot dat bestand weer te geven:

```kusto
AppFileEvents
| union DeviceFileEvents
| where FileName == "invoice.doc"
| summarize FileCount = count() by bin(Timestamp, 30m)
```
In het onderstaande lijndiagram worden duidelijk `invoice.doc`perioden aangegeven met meer activiteit: 

![Afbeelding van geavanceerde resultaten van de](../../media/advanced-hunting-line-chart.jpg)
jachtquery die worden weergegeven als een lijndiagram*Lijndiagram met het aantal gebeurtenissen met betrekking tot een bestand in de loop van de tijd*


## <a name="export-tables-and-charts"></a>Tabellen en grafieken exporteren
Nadat u een query hebt uitgevoerd, selecteert u **Exporteren** om de resultaten op te slaan in lokaal bestand. De door u gekozen weergave bepaalt hoe de resultaten worden geëxporteerd:

- **Tabelweergave** : de queryresultaten worden in tabelvorm geëxporteerd als een Microsoft Excel-werkmap
- **Elke grafiek** : de queryresultaten worden geëxporteerd als een JPEG-afbeelding van het gerenderde grafiek

## <a name="drill-down-from-query-results"></a>Inzoomen op queryresultaten
Als u meer informatie wilt weergeven over entiteiten, zoals machines, bestanden, gebruikers, IP-adressen en URL's, klikt u in uw queryresultaten op de entiteits-id. Hiermee wordt een gedetailleerde profielpagina geopend voor de geselecteerde entiteit in Microsoft Defender Security Center.

## <a name="tweak-your-queries-from-the-results"></a>Uw query's aanpassen aan de resultaten
Klik met de rechtermuisknop op een waarde in de resultatenset om uw query snel te verbeteren. U de opties gebruiken om:

- Expliciet zoeken naar de`==`geselecteerde waarde ( )
- De geselecteerde waarde uitsluiten`!=`van de query ( )
- Meer geavanceerde operators voor het toevoegen van `contains`de `starts with` waarde aan uw query, zoals , en`ends with` 

![Beeld van geavanceerde reeks van het jachtresultaat](../../media/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a>De queryresultaten filteren
De filters die rechts worden weergegeven, geven een overzicht van de resultatenset. Elke kolom heeft een eigen sectie met de verschillende waarden die voor die kolom zijn gevonden en het aantal exemplaren.

Verfijn uw query `+` `-` door de or-knoppen te selecteren op de waarden die u wilt opnemen of uit te sluiten en selecteer query **uitvoeren**.

![Beeld van geavanceerd jachtfilter](../../media/advanced-hunting-filter.png)

Zodra u het filter toepast om de query te wijzigen en de query vervolgens uit te voeren, worden de resultaten dienovereenkomstig bijgewerkt.

## <a name="related-topics"></a>Verwante onderwerpen
- [Geavanceerd jachtoverzicht](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Zoek naar bedreigingen op verschillende apparaten en e-mails](advanced-hunting-query-emails-devices.md)
- [Het schema begrijpen](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
- [Overzicht van aangepaste detecties](custom-detections-overview.md)
