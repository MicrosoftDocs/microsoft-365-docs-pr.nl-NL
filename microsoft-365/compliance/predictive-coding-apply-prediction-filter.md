---
title: Het voorspellingsscorefilter toepassen op items in een revisieset
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
ms.reviewer: jefwan
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: Gebruik een voorspellingsscorefilter om items weer te geeft die een voorspellend coderingsmodel zijn, zoals voorspeld als relevant of niet relevant.
ms.openlocfilehash: 0ca2770d5ccbcc3ea5f3dec8394f69d1f5117da5
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822493"
---
# <a name="apply-a-prediction-score-filter-to-a-review-set-preview"></a>Een voorspellingsscorefilter toepassen op een revisieset (voorbeeld)

Nadat u een voorspellend coderingsmodel hebt gemaakt in Advanced eDiscovery en dit hebt getrained naar het punt waar het stabiel is, kunt u het voorspellingsscorefilter toepassen om de items in de revisieset weer te geven die volgens het model relevant zijn (of niet relevant). Wanneer u een model maakt, wordt er ook een bijbehorend voorspellingsscorefilter gemaakt. U kunt dit filter gebruiken om items weer te geven die een voorspellingsscore binnen een opgegeven bereik hebben gekregen. In het algemeen zijn voorspellingsscores **tussen 0** en **0,5** toegewezen aan items die door het model zijn voorspeld, niet relevant. Items die zijn toegewezen voorspellingsscores **tussen 0,5** en **1,0** zijn items die het model heeft voorspeld, zijn relevant.

Hier zijn twee manieren waarop u het voorspellingsscorefilter kunt gebruiken:

- Geef prioriteit aan het controleren van items in een revisieset die het model heeft voorspeld, zijn relevant.

- Items verwijderen uit de revisieset die het model heeft voorspeld, zijn niet relevant. U kunt ook het voorspellingsscorefilter gebruiken om de prioriteit voor het controleren van niet-relevante items te de-prioriteren.

## <a name="before-you-apply-a-prediction-score-filter"></a>Voordat u een voorspellingsscorefilter toe te passen

- Maak een voorspellend coderingsmodel zodat er een overeenkomend voorspellingsscorefilter wordt gemaakt.

- U kunt een voorspellingsscorefilter toepassen na een van de trainingsronden. Maar misschien wilt u wachten nadat u meerdere rondes hebt gedaan of totdat het model stabiel is voordat u het voorspellingsscorefilter gebruikt.

## <a name="apply-a-prediction-score-filter"></a>Een voorspellingsscorefilter toepassen

1. Open in Microsoft 365 compliancecentrum het hoofd- Advanced eDiscovery, selecteer  het tabblad Revisiesets en open de revisieset.

   ![Klik op Filters om de flyoutpagina Filters weer te geven](..\media\PredictionScoreFilter0.png)   

   De vooraf geladen standaardfilters worden boven aan de pagina met revisiesets weergegeven. U kunt deze instellen op **Any**.

2. Klik **op Filters** om de flyoutpagina **Filters** weer te geven.

3. Vouw de **sectie Analyse & voorspellende codering** uit om een set filters weer te geven.

      ![Voorspellingsscorefilter in de sectie & voorspellende codering](..\media\PredictionScoreFilter1.png)

   De naamgevingsconventie voor voorspellingsscorefilters is **Voorspellingsscore (modelnaam)**. De naam van het voorspellingsscorefilter voor een model met de naam **Model A** is **bijvoorbeeld Voorspellingsscore (model A).**

4. Selecteer het voorspellingsscorefilter dat u wilt gebruiken en klik vervolgens op **Klaar.**

5. Klik op de pagina revisieset op de vervolgkeuzekeuze voor het voorspellingsscorefilter en typ minimum- en maximumwaarden voor het voorspellingsscorebereik. In de volgende schermafbeelding ziet u bijvoorbeeld een voorspellingsscorebereik tussen **0,5** en **1,0**.

   ![Minimum- en maximumwaarden voor het voorspellingsscorefilter](..\media\PredictionScoreFilter2.png)

6. Klik buiten het filter om het filter automatisch toe te passen op de revisieset.

  Een lijst met documenten met een voorspellingsscore binnen het opgegeven bereik wordt weergegeven op de pagina met revisiesets. 

  > [!TIP]
  > Als u de werkelijke voorspellingsscore wilt weergeven die aan een document is toegewezen, klikt u op het **tabblad** Metagegevens in het leesvenster. De voorspellingsscores voor alle modellen in de revisieset worden weergegeven in de **eigenschap Relevantiescores** metagegevens.

## <a name="more-information"></a>Meer informatie

- Zie Inhoud query's en [filteren in een revisieset](review-set-search.md)voor meer informatie over het gebruik van filters.
