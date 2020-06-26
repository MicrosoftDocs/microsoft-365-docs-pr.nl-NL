---
title: Werken met geavanceerde jachtqueryresultaten in Microsoft Threat Protection
description: Haal het meeste uit de queryresultaten die worden geretourneerd door geavanceerde jacht in Microsoft Threat Protection
keywords: geavanceerde jacht, bedreiging jacht, cyber bedreiging jacht, Microsoft Threat Protection, Microsoft 365, mtp, m365, zoeken, query, telemetrie, aangepaste detecties, schema, kusto, Microsoft 365, Microsoft Threat Protection, visualisatie, grafiek, filters, drill-down
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
ms.openlocfilehash: 14afd3c098c99a6e1e6ccfc7e9f6accbf8bf0e7d
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899078"
---
# <a name="work-with-advanced-hunting-query-results"></a>Werken met geavanceerde jachtqueryresultaten

**Van toepassing op:**
- Microsoft Threat Protection

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Hoewel u uw geavanceerde jachtquery's construeren om zeer nauwkeurige informatie terug te geven, u ook werken met de queryresultaten om meer inzicht te krijgen en specifieke activiteiten en indicatoren te onderzoeken. [advanced hunting](advanced-hunting-overview.md) U de volgende acties uitvoeren op uw queryresultaten:

- Resultaten weergeven als een tabel of grafiek
- Tabellen en grafieken exporteren
- Inzoomen op gedetailleerde entiteitsgegevens
- Uw query's rechtstreeks vanuit de resultaten aanpassen of filters toepassen

## <a name="view-query-results-as-a-table-or-chart"></a>Queryresultaten weergeven als een tabel of grafiek
Geavanceerde jacht geeft standaard queryresultaten weer als tabelgegevens. U ook dezelfde gegevens weergeven als een grafiek. Geavanceerde jacht ondersteunt de volgende standpunten:

| Type weergeven | Beschrijving |
| -- | -- |
| **Tabel** | Hiermee worden de queryresultaten weergegeven in tabelindeling |
| **Kolomdiagram** | Hiermee worden een reeks unieke items op de x-as weergegeven als verticale balken waarvan de hoogten numerieke waarden uit een ander veld weergeven |
| **Gestapeld kolomdiagram** | Hiermee worden een reeks unieke items op de x-as weergegeven als gestapelde verticale balken waarvan de hoogten numerieke waarden van een of meer andere velden weergeven |
| **Cirkeldiagram** | Hiermee worden sectionele cirkels weergegeven die unieke items vertegenwoordigen. De grootte van elke cirkel vertegenwoordigt numerieke waarden uit een ander veld. |
| **Donut-diagram** | Hiermee worden sectionele bogen weergegeven die unieke items vertegenwoordigen. De lengte van elke boog vertegenwoordigt numerieke waarden uit een ander veld. |
| **Lijndiagram** | Hiermee worden numerieke waarden gecompseerd voor een reeks unieke items en worden de uitgezette waarden verbonden |
| **Spreidingsdiagram** | Plots numerieke waarden voor een reeks unieke items |
| **Gebiedsdiagram** | Hiermee worden numerieke waarden geperceleerd voor een reeks unieke items en worden de secties onder de uitgezette waarden gevuld |

### <a name="construct-queries-for-effective-charts"></a>Query's maken voor effectieve grafieken
Bij het renderen van grafieken identificeert geavanceerde jacht automatisch kolommen van belang en de numerieke waarden die moeten worden samengevoegd. Als u zinvolle grafieken wilt krijgen, maakt u uw query's om de specifieke waarden die u wilt zien te retourneren. Hier volgen enkele voorbeeldquery's en de resulterende grafieken.

#### <a name="alerts-by-severity"></a>Waarschuwingen op ernst
Gebruik de `summarize` operator om een numeriek aantal te verkrijgen van de waarden die u wilt in kaart brengen. De onderstaande query gebruikt de `summarize` operator om het aantal waarschuwingen op ernst te krijgen.

```kusto
AlertInfo
| summarize Total = count() by Severity
```
Bij het renderen van de resultaten wordt in een kolomdiagram elke ernstwaarde weergegeven als een afzonderlijke kolom:

![Afbeelding van geavanceerde jachtqueryresultaten weergegeven als kolomdiagram ](../../media/advanced-hunting-column-chart.jpg)
 *Queryresultaten voor waarschuwingen op ernst die worden weergegeven als een kolomdiagram*

#### <a name="alert-severity-by-operating-system"></a>Ernst waarschuwing door besturingssysteem
U de operator ook gebruiken `summarize` om resultaten voor te bereiden op het in kaart brengen van waarden uit meerdere velden. U bijvoorbeeld begrijpen hoe de ernst van de waarschuwing over besturingssystemen (OS) wordt verdeeld. 

De onderstaande query gebruikt een `join` operator om OS-informatie uit de tabel te halen `DeviceInfo` en gebruikt vervolgens om waarden te tellen `summarize` in zowel de als de `OSPlatform` `Severity` kolommen:

```kusto
AlertInfo
| join AlertEvidence on AlertId
| join DeviceInfo on DeviceId
| summarize Count = count() by OSPlatform, Severity 
```
Deze resultaten worden het best gevisualiseerd met behulp van een gestapeld kolomdiagram:

![Afbeelding van geavanceerde jachtqueryresultaten weergegeven als gestapelde grafiek ](../../media/advanced-hunting-stacked-chart.jpg)
 *Queryresultaten voor waarschuwingen per besturingssysteem en ernst weergegeven als een gestapelde grafiek*

#### <a name="phishing-emails-across-top-ten-sender-domains"></a>Phishing-e-mails in de tien beste afzenderdomeinen
Als u te maken hebt met een lijst met waarden die niet eindig zijn, u de operator gebruiken `Top` om alleen de waarden met de meeste instanties in kaart te brengen. Gebruik bijvoorbeeld de onderstaande query om de top tien van afzenderdomeinen met de meeste phishing-e-mails te krijgen:

```kusto
EmailEvents
| where PhishFilterVerdict == "Phish"
| summarize Count = count() by SenderFromDomain
| top 10 by Count
```
Gebruik de cirkeldiagramweergave om de verdeling over de bovenste domeinen effectief weer te geven:

![Afbeelding van geavanceerde jachtqueryresultaten weergegeven als een cirkeldiagram ](../../media/advanced-hunting-pie-chart.jpg)
 *Cirkeldiagram met de distributie van phishing-e-mails over de bovenste afzenderdomeinen*

#### <a name="file-activities-over-time"></a>Bestandsactiviteiten in de loop van de tijd
Met behulp van de `summarize` operator met de `bin()` functie, u controleren op gebeurtenissen waarbij een bepaalde indicator in de tijd. De onderstaande query telt gebeurtenissen met het bestand `invoice.doc` met intervallen van 30 minuten om pieken in activiteit met betrekking tot dat bestand weer te geven:

```kusto
AppFileEvents
| union DeviceFileEvents
| where FileName == "invoice.doc"
| summarize FileCount = count() by bin(Timestamp, 30m)
```
In het onderstaande lijndiagram worden tijdsperioden met meer activiteit duidelijk `invoice.doc` weergegeven: 

![Afbeelding van geavanceerde jachtqueryresultaten weergegeven als een lijndiagram ](../../media/advanced-hunting-line-chart.jpg)
 *Lijndiagram met het aantal gebeurtenissen met een bestand in de loop van de tijd*


## <a name="export-tables-and-charts"></a>Tabellen en grafieken exporteren
Nadat u een query hebt uitgevoerd, selecteert u **Exporteren** om de resultaten op te slaan in het lokale bestand. De door u gekozen weergave bepaalt hoe de resultaten worden geëxporteerd:

- **Tabelweergave** — de queryresultaten worden in tabelvorm geëxporteerd als een Microsoft Excel-werkmap
- **Elke grafiek** — de queryresultaten worden geëxporteerd als jpeg-afbeelding van de gerenderde grafiek

## <a name="drill-down-from-query-results"></a>Inzoomen op queryresultaten
Als u snel een record in uw queryresultaten wilt inspecteren, selecteert u de bijbehorende rij om het **recordpaneel Inspecteren** te openen. Het deelvenster geeft de volgende informatie op basis van de geselecteerde record:

- **Activa** — samengevat overzicht van de belangrijkste elementen (postvakken, apparaten en gebruikers) in de record, verrijkt met beschikbare informatie, zoals risico- en blootstellingsniveaus
- **Processtructuur** — gegenereerd voor records met procesinformatie en verrijkt met behulp van beschikbare contextuele informatie; in het algemeen kunnen query's die meer kolommen retourneren resulteren in rijkere procesbomen.
- **Alle details** — alle waarden uit de kolommen in de record  

![Afbeelding van geselecteerde record met deelvenster voor het inspecteren van de record](../../media/mtp-ah/inspect-record.png)

Als u meer informatie over een specifieke entiteit wilt weergeven in uw queryresultaten, zoals een machine, bestand, gebruiker, IP-adres of URL, selecteert u de entiteitsidentyzer om een gedetailleerde profielpagina voor die entiteit te openen.

## <a name="tweak-your-queries-from-the-results"></a>Uw query's aanpassen aan de resultaten
Klik met de rechtermuisknop op een waarde in de resultatenset om uw query snel te verbeteren. U de opties gebruiken om:

- Zoek expliciet naar de geselecteerde waarde ( `==` )
- De geselecteerde waarde uitsluiten van de query ( `!=` )
- Meer geavanceerde operators ophalen voor het toevoegen van de waarde aan uw query, zoals `contains` , `starts with` en`ends with` 

![Beeld van geavanceerde reeks van het jachtresultaat](../../media/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a>De queryresultaten filteren
De filters die rechts worden weergegeven, geven een overzicht van de resultatenset. Elke kolom heeft een eigen sectie met de afzonderlijke waarden die voor die kolom zijn gevonden en het aantal instanties.

Verfijn uw query door de of knoppen te selecteren `+` op de waarden die u wilt opnemen of uitsluiten en selecteer `-` **vervolgens Query uitvoeren**.

![Afbeelding van geavanceerd jachtfilter](../../media/advanced-hunting-filter.png)

Zodra u het filter toepast om de query te wijzigen en vervolgens de query uit te voeren, worden de resultaten dienovereenkomstig bijgewerkt.

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Zoek naar bedreigingen op verschillende apparaten en e-mails](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
- [Overzicht van aangepaste detectie](custom-detections-overview.md)
