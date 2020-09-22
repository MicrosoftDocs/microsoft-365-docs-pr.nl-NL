---
title: Werken met geavanceerde zoekopdrachten voor de jacht in Microsoft Threat Protection
description: Maak optimaal resultaten van de queryresultaten die worden geretourneerd door de geavanceerde jacht in Microsoft Threat Protection
keywords: geavanceerde jacht, bedreigings jacht, Cyber Threat jacht, Microsoft Threat Protection, Microsoft 365, MTP, m365, Search, query, telemetrie, aangepaste detectie, schema, kusto, Microsoft 365, Microsoft Threat Protection, visualisatie, grafiek, filters en inzoomen
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
ms.openlocfilehash: d9650811a264992c20a1ed88939e06694373b25c
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197701"
---
# <a name="work-with-advanced-hunting-query-results"></a>Werken met geavanceerde zoekresultaten van de jacht

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft Threat Protection

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Hoewel u uw [Geavanceerde](advanced-hunting-overview.md) zoekopdrachten kunt maken om zeer nauwkeurige informatie te retourneren, kunt u ook werken met de queryresultaten om meer inzicht te krijgen en specifieke activiteiten en indicatoren te onderzoeken. U kunt de volgende acties uitvoeren op uw queryresultaten:

- Resultaten als een tabel of grafiek weergeven
- Tabellen en grafieken exporteren
- Inzoomen op gedetailleerde entiteits informatie
- Uw zoekopdrachten direct toepassen op de resultaten of filters toepassen

## <a name="view-query-results-as-a-table-or-chart"></a>Queryresultaten als tabel of in een grafiek weergeven
Standaard worden in geavanceerde jacht queryresultaten weergegeven als tabelgegevens. U kunt ook dezelfde gegevens weergeven als een grafiek. Geavanceerde jacht ondersteuning voor de volgende weergaven:

| Weergavetype | Beschrijving |
| -- | -- |
| **Tabel** | De queryresultaten worden in tabelvorm weergegeven |
| **Kolomdiagram** | Geeft een reeks unieke items weer op de x-as met verticale balken waarvan de numerieke waarden uit een ander veld aangeven |
| **Gestapeld kolomdiagram** | Geeft een reeks unieke items op de x-as weer als gestapelde verticale balken waarvan de numerieke waarden in een of meer andere velden aangeven |
| **Cirkeldiagram** | Geeft een Pies weer en vertegenwoordigen unieke items. De grootte van elk cirkeldiagram bevat numerieke waarden uit een ander veld. |
| **Ringdiagram** | Rendert sectietab van de secties die unieke items vertegenwoordigen. Elke boog bevat numerieke waarden uit een ander veld. |
| **Lijndiagram** | De numerieke waarden voor een reeks unieke items tekenen en de geplotte waarden verbinden |
| **Spreidingsdiagram** | Numerieke waarden voor een reeks unieke items tekenen |
| **Vlakdiagram** | Hiermee tekent u numerieke waarden voor een reeks unieke items en vult u de secties onder de gevolgde waarden door |

### <a name="construct-queries-for-effective-charts"></a>Query's opstellen voor effectieve grafieken
Bij het weergeven van grafieken worden in geavanceerde jacht automatisch de kolommen rente en de numerieke waarden aangegeven voor statistische functies. Als u zinvolle grafieken wilt weergeven, maakt u de query's om de specifieke waarden te retourneren die u wilt weergeven. Hier volgen enkele voorbeelden van query's en de gemaakte grafieken.

#### <a name="alerts-by-severity"></a>Waarschuwingen per Ernst
Gebruik de `summarize` operator om een numeriek aantal te verkrijgen voor de waarden die u in een grafiek wilt opnemen. Voor de onderstaande query wordt de `summarize` operator gebruikt om het aantal waarschuwingen per ernst te ontvangen.

```kusto
AlertInfo
| summarize Total = count() by Severity
```
Bij het weergeven van de resultaten ziet u in een kolomdiagram elke waarde voor de ernst als een afzonderlijke kolom:

![Afbeelding van geavanceerde zoekresultaten die worden weergegeven als kolomdiagram ](../../media/advanced-hunting-column-chart.jpg)
 *queryresultaten voor waarschuwingen per Ernst weergegeven als kolomdiagram*

#### <a name="alert-severity-by-operating-system"></a>Ernst van waarschuwingen via besturingssysteem
U kunt ook de `summarize` operator gebruiken om resultaten voor de grafiekwaarden uit meerdere velden voor te bereiden. U kunt bijvoorbeeld inzicht krijgen in de beschikbaarheid van waarschuwings punten voor het besturingssysteem (OS). 

In de onderstaande query wordt een `join` operator gebruikt om besturingssysteemgegevens uit de tabel op te halen `DeviceInfo` en wordt gebruikt `summarize` om waarden te tellen in zowel de `OSPlatform` kolommen als `Severity` :

```kusto
AlertInfo
| join AlertEvidence on AlertId
| join DeviceInfo on DeviceId
| summarize Count = count() by OSPlatform, Severity 
```
Dit zijn de beste visuele resultaten met behulp van een gestapeld kolomdiagram:

![Afbeelding van geavanceerde zoekresultaten die worden weergegeven als een gestapeld diagram ](../../media/advanced-hunting-stacked-chart.jpg)
 *queryresultaten voor waarschuwingen per OS en ernst weergegeven als gestapelde grafiek*

#### <a name="phishing-emails-across-top-ten-sender-domains"></a>Phishing-e-mails in de bovenste tien verzender domeinen
Als u wilt werken met een lijst met waarden die niet beperkt zijn, kunt u de `Top` operator gebruiken om alleen de waarden in een grafiek te plaatsen. Als u bijvoorbeeld de meeste tien verzender domeinen met de meest verduidelijkende e-mail wilt ophalen, gebruikt u de onderstaande query:

```kusto
EmailEvents
| where PhishFilterVerdict == "Phish"
| summarize Count = count() by SenderFromDomain
| top 10 by Count
```
In de weergave cirkeldiagram kunt u de verdeling effectief weergeven op de meest voorkomende domeinen:

![Afbeelding van geavanceerde zoekresultaten die worden weergegeven als een cirkeldiagram met een cirkeldiagram ](../../media/advanced-hunting-pie-chart.jpg)
 *waarin de distributie van malafide e-mailberichten in domeinen van de belangrijkste afzender wordt getoond*

#### <a name="file-activities-over-time"></a>Bestandsactiviteiten gedurende een bepaalde periode
Met de `summarize` operator met de `bin()` functie, kunt u controleren op gebeurtenissen met een bepaalde indicator gedurende een bepaalde periode. Met de query eronder worden de gebeurtenissen met het bestand `invoice.doc` bij 30 minuten geteld om uitschieters weer te geven in activiteiten met betrekking tot dat bestand:

```kusto
AppFileEvents
| union DeviceFileEvents
| where FileName == "invoice.doc"
| summarize FileCount = count() by bin(Timestamp, 30m)
```
In het lijndiagram onder duidelijk worden tijdsperioden gemarkeerd met meer activiteiten `invoice.doc` : 

![Afbeelding van geavanceerde zoekresultaten van de zoekactie die worden weergegeven als lijndiagram ](../../media/advanced-hunting-line-chart.jpg)
 *met meerdere gebeurtenissen*


## <a name="export-tables-and-charts"></a>Tabellen en grafieken exporteren
Na het uitvoeren van een query, selecteert u **exporteren** om de resultaten in het lokale bestand op te slaan. Met de gekozen weergave wordt bepaald hoe de resultaten worden geëxporteerd:

- **Tabel weergave** : de queryresultaten worden in tabelvorm geëxporteerd als een Microsoft Excel-werkmap
- **Een grafiek** : de queryresultaten worden geëxporteerd als een JPEG-afbeelding van de weergegeven grafiek

## <a name="drill-down-from-query-results"></a>Inzoomen op queryresultaten
Als u in uw queryresultaten snel een record wilt controleren, selecteert u de bijbehorende rij om het deelvenster **record controleren** te openen. Het deelvenster bevat de volgende informatie op basis van de geselecteerde record:

- **Activa** : een overzichtsweergave van de belangrijkste activa (postvakken, apparaten en gebruikers) die zijn gevonden in de record, verrijkd met de beschikbare informatie, zoals risico en belichtings niveau
- **Processtructuur** : gegenereerd voor records met procesinformatie en verrijking met behulp van beschikbare contextuele informatie. in het algemeen kunnen query's die meer kolommen retourneren, resulteren in uitgebreide processen.
- **Alle details** : alle waarden uit de kolommen in de record  

![Afbeelding van geselecteerde record met deelvenster voor inspectie van de record](../../media/mtp-ah/inspect-record.png)

Als u meer informatie wilt bekijken over een bepaalde entiteit in uw queryresultaten, zoals een computer, bestand, gebruiker, IP-adres of URL, selecteert u de entiteits-id om een gedetailleerde profielpagina voor die entiteit te openen.

## <a name="tweak-your-queries-from-the-results"></a>De query's van de zoekresultaten verfijnen
Klik met de rechtermuisknop op een waarde in de resultatenset om uw query snel te verbeteren. Met de opties kunt u:

- Zoek expliciet naar de geselecteerde waarde ( `==` ).
- De geselecteerde waarde van de query uitsluiten `!=`
- Meer geavanceerde operatoren voor het toevoegen van een waarde aan uw query, zoals `contains` , `starts with` en `ends with` 

![Afbeelding van geavanceerde resultatenset van jacht](../../media/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a>De queryresultaten filteren
De filters rechts geven een overzicht van de resultatenset. Elke kolom heeft een eigen sectie met daarin de unieke waarden die zijn gevonden voor de kolom en het aantal exemplaren.

Verfijn uw zoekopdracht door de `+` knoppen of de knoppen te selecteren `-` voor de waarden die u wilt opnemen of uitsluiten en vervolgens **query uitvoeren**te selecteren.

![Afbeelding van een geavanceerd jacht filter](../../media/advanced-hunting-filter.png)

Wanneer u het filter hebt toegepast om de query te wijzigen en vervolgens de query uit te voeren, worden de resultaten dienovereenkomstig bijgewerkt.

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Opsporen op apparaten en in e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
- [Overzicht van aangepaste detectie](custom-detections-overview.md)
