---
title: Gebruiksanalyse documentbegripmodellen
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Informatie over het toepassen van een retentietag op een documentbegripmodel
ms.openlocfilehash: 92115d8b1985fa84cd72671442aca18f255355de
ms.sourcegitcommit: d354727303d9574991b5a0fd298d2c9414e19f6c
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/02/2021
ms.locfileid: "50080418"
---
# <a name="document-understanding-model-usage-analytics"></a>Gebruiksanalyse documentbegripmodellen

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GnhX]  

</br>


U kunt analysemodellen gebruiken in uw Microsoft SharePoint Syntex-inhoudscentrum, voor meer informatie over de manier waarop de modellen die zijn gepubliceerd vanuit het inhoudscentrum worden gebruikt. De sectie<b>Hoe uw modellen hebben gepresteerd in de afgelopen 30 dagen</b> van het inhoudscentrum bevat een rollup van de gebruiksanalysegegevens voor 30 dagen in de volgende grafieken en lijsten:

- Classificatie per model
- Classificatie per bibliotheek
- Modelgebruik 

 ![Modelanalyse](../media/content-understanding/model-analytics.png) </br>

### <a name="roll-up-of-model-usage-data-in-the-default-content-center"></a>Rollup van modelgebruiksgegevens in het standaardinhoudscentrum

In SharePoint Syntex wordt het standaardinhoudscentrum gemaakt tijdens de installatie. U kunt zo nodig ook aanvullende inhoudscentra maken. Afdelingen kunnen bijvoorbeeld hun eigen inhoudscentra maken om hun modellen te maken en beheren. 

Wat betreft modelgebruiksanalyses moet u rekening houden met het volgende:

- In het standaardinhoudscentrum worden modelgebruiksanalyses weergegeven voor alle inhoudscentra en modellen in uw organisatie, inclusief de analyses die zijn gemaakt in extra inhoudscentra. Hiermee krijgen inhoudsbeheerders en andere belanghebbenden een gecentraliseerde portal voor beheer en toezicht op de inhoudscentra en modellen in het hele bedrijf.  
- In andere inhoudscentra worden alleen modelgebruiksanalyses voor de modellen in de inhoudscentra weergegeven. Hiermee krijgen inhoudsbeheerders inzicht in gebruiksgegevens voor alleen de modellen die voor hen relevant zijn.


## <a name="classification-by-model"></a>Classificatie per model

   ![Percentage van alle modellen](../media/content-understanding/total-model-percentage.png) </br>

In **Classificatie per model** geeft het cirkeldiagram weer welke modellen de meeste bestanden hebben geclassificeerd. Het diagram toont elk gepubliceerd model als een percentage van het totale aantal bestanden dat is verwerkt door alle gepubliceerde modellen in het inhoudscentrum.

Voor elk model wordt ook de **Voltooiingspercentage** weergeven, oftewel het percentage geüploade bestanden dat door het model is geanalyseerd. Een laag voltooiingspercentage kan betekenen dat er problemen zijn met het model of de bestanden die worden geanalyseerd.

## <a name="classification-by-library"></a>Classificatie per bibliotheek

   ![Verwerkte bestanden](../media/content-understanding/files-processed-over-time.png) </br>

Met **Classificatie per bibliotheek** kunt u de effectiviteit van inhoudsbegrip in uw organisatie bepalen.  U ziet niet alleen het aantal bestanden dat in de loop van de tijd is verwerkt door elk model, maar wanneer u een kolom in een diagram selecteert, ziet u ook de documentbibliotheken waarop het model is toegepast.


## <a name="model-usage"></a>Modelgebruik

De lijst Modelgebruik toont gebruiksanalyses voor de modellen die zijn gemaakt via het inhoudscentrum.  

> [!NOTE]
> Als u zich in het standaardinhoudscentrum bevindt en extra inhoudscentra in uw organisatie hebt, wordt de lijst met modelgebruik gegroepeerd op inhoudscentrum.

Elk model in de lijst Modelgebruik toont de volgende gebruiksgegevens:

- Het aantal geclassificeerde items: het aantal bestanden dat door het model wordt verwerkt.
- Gemiddelde betrouwbaarheidsscore: de gemiddelde nauwkeurigheid van het model wanneer dit wordt uitgevoerd op bestanden.
- URL van de doellijst: de SharePoint-documentbibliotheek waarop het model wordt toegepast.



## <a name="see-also"></a>Zie ook
[Een classificatie maken](create-a-classifier.md)

[Een extractor maken](create-an-extractor.md)

[Overzicht van documentbegrip](document-understanding-overview.md)

[Een formulierverwerkingsmodel maken](create-a-form-processing-model.md)  
