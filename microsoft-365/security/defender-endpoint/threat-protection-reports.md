---
title: Rapport bedreigingsbeveiliging in MICROSOFT Defender ATP
description: Waarschuwingsdetecties, categorieën en ernst bijhouden met behulp van het rapport bedreigingsbeveiliging
keywords: waarschuwingsdetectie, bron, waarschuwing per categorie, ernst van waarschuwing, waarschuwingsclassificatie, bepaling
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4ecd2df31e1e03da5134d3d4180dcba75d3cee26
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51183835"
---
# <a name="threat-protection-report-in-microsoft-defender-for-endpoint"></a>Rapport bedreigingsbeveiliging in Microsoft Defender voor Eindpunt

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

Het rapport bedreigingsbeveiliging bevat informatie op hoog niveau over waarschuwingen die in uw organisatie worden gegenereerd. Het rapport bevat trendgegevens met de detectiebronnen, categorieën, ernst, statussen, classificaties en de bepaling van waarschuwingen in de tijd.

Het dashboard is gestructureerd in twee secties:

![Afbeelding van het rapport bedreigingsbeveiliging](images/threat-protection-reports.png)

Sectie | Beschrijving 
:---|:---
1 | Trends in waarschuwingen
2 | Overzicht van waarschuwingen

## <a name="alert-trends"></a>Waarschuwingstrends
Standaard worden in de waarschuwingstrends waarschuwingsgegevens weergegeven uit de periode van 30 dagen die eindigt op de laatste volledige dag. Als u meer inzicht wilt krijgen in trends in uw organisatie, kunt u de rapportageperiode aanpassen door de weergegeven periode aan te passen. Als u de periode wilt aanpassen, selecteert u een tijdsbereik in de vervolgkeuzeopties:

- 30 dagen
- 3 maanden
- 6 maanden
- Aangepast

>[!NOTE]
>Deze filters worden alleen toegepast op de sectie waarschuwingstrends. Dit heeft geen invloed op de sectie Overzicht van waarschuwingen.


## <a name="alert-summary"></a>Overzicht van waarschuwingen
Terwijl de waarschuwingstrends trending waarschuwingsgegevens laten zien, worden in de overzichtsoverzicht van waarschuwingen waarschuwingsinformatie voor de huidige dag gegeven.

 Met het overzicht van waarschuwingen kunt u inzoomen op een bepaalde waarschuwingswachtrij waarbij het bijbehorende filter erop is toegepast. Als u bijvoorbeeld op de EDR-balk in de kaart Detectiebronnen klikt, wordt de wachtrij voor waarschuwingen weergegeven met alleen waarschuwingen die zijn gegenereerd op basis van EDR-detecties. 

>[!NOTE]
>De gegevens die in de samenvattingssectie worden weergegeven, hebben een bereik van 180 dagen vóór de huidige datum. Als de datum van vandaag bijvoorbeeld 5 november 2019 is, worden in de gegevens in de samenvattingssectie getallen weergegeven die beginnen van 5 mei 2019 tot en met 5 november 2019.<br>
> Het filter dat is toegepast op de sectie Trends, wordt niet toegepast op de samenvattingssectie. 

## <a name="alert-attributes"></a>Waarschuwingskenmerken
Het rapport bestaat uit kaarten met de volgende waarschuwingskenmerken:

- **Detectiebronnen:** geeft informatie weer over de sensoren en detectietechnologieën die de gegevens bevatten die door Microsoft Defender voor Eindpunt worden gebruikt om waarschuwingen te activeren.

- **Bedreigingscategorieën:** geeft de typen bedreigings- of aanvalsactiviteiten weer die waarschuwingen hebben geactiveerd, waarmee mogelijke focusgebieden voor uw beveiligingsbewerkingen worden aangegeven.

- **Ernst:** geeft het ernstniveau van waarschuwingen weer, wat aangeeft wat de mogelijke gevolgen zijn van bedreigingen voor uw organisatie en het antwoordniveau dat nodig is om deze aan te pakken.

- **Status:** geeft de resolutiestatus van waarschuwingen weer, waarmee de efficiëntie van uw handmatige waarschuwingsreacties en van geautomatiseerde herstel (indien ingeschakeld) wordt aangegeven. 

- **Classificatie &** bepaling: laat zien hoe u waarschuwingen hebt geclassificeerd bij resolutie, of u deze hebt geclassificeerd als werkelijke bedreigingen (echte waarschuwingen) of als onjuiste detecties (onwaar waarschuwingen). Deze kaarten geven ook de bepaling van opgeloste waarschuwingen weer, wat extra inzicht geeft, zoals de typen werkelijke bedreigingen die zijn gevonden of de legitieme activiteiten die ten onrechte zijn gedetecteerd.


 

## <a name="filter-data"></a>Gegevens filteren

Gebruik de meegeleverde filters om waarschuwingen met bepaalde kenmerken op te nemen of uit te sluiten.

>[!NOTE]
>Deze filters zijn van **toepassing op alle** kaarten in het rapport.

Als u bijvoorbeeld alleen gegevens wilt weergeven over waarschuwingen met hoge ernst:

1. Selecteer **onder Filters > Ernst** de optie **Hoog**
2. Zorg ervoor dat alle andere opties onder **Ernst** worden uitgeschakeld.
3. Selecteer **Toepassen.** 

## <a name="related-topic"></a>Verwant onderwerp
- [Rapport apparaattoestand en naleving](machine-reports.md)
