---
title: Voorspellende codering in Advanced eDiscovery - Snel aan de slag
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
description: Lees hoe u aan de slag kunt met de module voor voorspellende codering in Advanced eDiscovery. In dit artikel vindt u een overzicht van het end-to-endproces van het gebruik van voorspellende codering om inhoud te identificeren in een revisieset die het meest relevant is voor uw onderzoek.
ms.openlocfilehash: 16fb92af5048ae6cd953e522b2e5e5d8f5a7256f
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822509"
---
# <a name="quick-start-predictive-coding-in-advanced-ediscovery-preview"></a>Aan de slag: Voorspellende codering in Advanced eDiscovery (voorbeeld)

In dit artikel wordt een beknopt begin beschreven voor het gebruik van voorspellende codering in Advanced eDiscovery. De module voor voorspellende codering in Advanced eDiscovery maakt gebruik van de intelligente, machine learning-mogelijkheden in Advanced eDiscovery om de hoeveelheid te controleren inhoud te verminderen. Met voorspellende codering kunt u grote hoeveelheden case-inhoud beperken en verwijderen tot een relevante set items die u voor controle kunt prioriteren. Dit wordt gedaan door uw eigen voorspellende coderingsmodellen te maken en te trainen, zodat u prioriteit kunt geven aan de beoordeling van de meest relevante items in een revisieset.

Hier volgen een kort overzicht van het voorspellende coderingsproces:

![Snelstartproces voor voorspellingscodering](..\media\PredictiveCodingQuickStartProcess.png)

Om aan de slag te gaan, maakt u een model, labelt u maar liefst 50 items als relevant of niet relevant. Het systeem gebruikt deze training vervolgens om voorspellingsscores toe te passen op elk item in de revisieset. Hiermee kunt u items filteren op basis van de voorspellingsscore, zodat u eerst de meest relevante (of niet-relevante) items kunt bekijken. Als u modellen met hogere nauwkeurigheid en terugroeptarieven wilt trainen, kunt u items in de volgende trainingsronden blijven labelen totdat het model zich stabiliseert. Wanneer het model is gestabiliseerd, kunt u het uiteindelijke voorspellingsfilter toepassen om prioriteit te geven aan items die moeten worden beoordeeld.

Zie Meer informatie over voorspellende codering [in](predictive-coding-overview.md)Advanced eDiscovery.

## <a name="step-1-create-a-new-predictive-coding-model"></a>Stap 1: Een nieuw voorspellend coderingsmodel maken

De eerste stap is het maken van een nieuw voorspellend coderingsmodel in de revisieset

1. Open in Microsoft 365 compliancecentrum een Advanced eDiscovery en selecteer vervolgens **het tabblad Revisiesets.**

2. Open een revisieset en klik vervolgens op **Voorspellende** codering beheren  >  **(voorbeeld)**.

   ![Klik in de vervolgkeuzelijst Analyseren in de revisieset om naar de pagina Voorspellende codering te gaan](..\media\ManagePredictiveCoding.png)

3. Klik op **de pagina Voorspellende coderingsmodellen (voorbeeld)** op **Nieuw model.**

4. Typ op de flyoutpagina een naam voor het model en een optionele beschrijving.

5. Klik **op Opslaan** om het model te maken.

   Het duurt een paar minuten voordat het systeem uw model heeft voorbereid. Nadat het klaar is, kunt u de eerste trainingsronde uitvoeren.

Zie Een voorspellend coderingsmodel maken voor meer [gedetailleerde instructies.](predictive-coding-create-model.md)

## <a name="step-2-perform-the-first-training-round"></a>Stap 2: De eerste trainingsronde uitvoeren

Nadat u het model hebt gemaakt, is de volgende stap het voltooien van de eerste trainingsronde door items te labelen als relevant of niet relevant.

1. Open de revisieset en klik vervolgens op **Voorspellende** codering beheren  >  **(voorbeeld)**.

2. Selecteer op **de pagina Voorspellende coderingsmodellen (voorbeeld)** het model dat u wilt trainen.

3. Klik op **het** tabblad Overzicht onder **Ronde 1** op **Volgende trainingsronde starten.**

   Het **tabblad** Training wordt weergegeven en bevat 50 items die u kunt labelen.

4. Controleer elk document en selecteer vervolgens de **knop Relevant** of **Niet relevant** onder aan het leesvenster om het te labelen.

   ![Elk document als relevant of niet relevant labelen](..\media\TrainModel1.png)

5. Nadat u alle 50 items hebt gelabeld, klikt u op **Voltooien.**

    Het duurt een paar minuten voordat het systeem 'leert' van uw labeling en het model bij werkt. Wanneer dit proces is voltooid, wordt de status **Ready** weergegeven voor het model op de pagina **Voorspellende coderingsmodellen (preview).**

Zie Een voorspellend coderingsmodel trainen voor meer [gedetailleerde instructies.](predictive-coding-train-model.md)

## <a name="step-3-apply-the-prediction-score-filter-to-items-in-review-set"></a>Stap 3: Het voorspellingsscorefilter toepassen op items in de revisieset

Nadat u één trainingsronde hebt gedaan bij lease, kunt u het filter voor de voorspellingsscore toepassen op items in de revisieset. Op deze manier kunt u de items bekijken die het model heeft voorspeld als relevant of niet relevant.   

1. Open de revisieset.

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

Zie Een voorspellingsfilter toepassen op een revisieset voor meer [gedetailleerde instructies.](predictive-coding-apply-prediction-filter.md)

## <a name="step-4-perform-more-training-rounds"></a>Stap 4: Meer trainingsronden uitvoeren

Waarschijnlijk moet u meer trainingsronden uitvoeren om de module te trainen om relevante en niet-relevante items in de revisieset beter te voorspellen. Over het algemeen traint u het model vaak genoeg totdat het voldoende stabiel is om aan uw vereisten te voldoen.

Zie Aanvullende trainingsronden [uitvoeren voor meer informatie.](predictive-coding-train-model.md#perform-additional-training-rounds)

## <a name="step-5-apply-the-final-prediction-score-filter-to-prioritize-review"></a>Stap 5: Het filter voor de uiteindelijke voorspellingsscore toepassen om prioriteit te geven aan de beoordeling

Herhaal de instructies in stap 3 om de uiteindelijke voorspellingsscore toe te passen op de revisieset om prioriteit te geven aan de beoordeling van relevante en niet-relevante items nadat u alle trainingsronden hebt voltooid en het model hebt gestabiliseerd.
