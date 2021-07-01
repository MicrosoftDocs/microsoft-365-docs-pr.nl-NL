---
title: Een voorspellend coderingsmodel trainen in Advanced eDiscovery
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
description: ''
ms.openlocfilehash: 84bb34f8ec1b935dc30072e16f57b5f5665c3546
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226213"
---
# <a name="train-a-predictive-coding-model-preview"></a>Een voorspellend coderingsmodel trainen (voorbeeld)

Nadat u een voorspellend coderingsmodel hebt gemaakt in Advanced eDiscovery, is de volgende stap het uitvoeren van de eerste trainingsronde om het model te trainen op relevante en niet-relevante inhoud in de revisieset. Nadat u de eerste trainingsronde hebt voltooid, kunt u volgende trainingsronden uitvoeren om het model beter in staat te maken relevante en niet-relevante inhoud te voorspellen.

Zie Meer informatie over voorspellende codering [in](predictive-coding-overview.md#the-predictive-coding-workflow) Advanced eDiscovery

## <a name="before-you-train-a-model"></a>Voordat u een model traint

- Label tijdens een trainingsronde items als **Relevant** of **Niet relevant** op basis van de relevantie van de inhoud in het document. Baseer uw beslissing niet op de waarden in de metagegevensvelden. Voor e-mailberichten of Teams gesprekken kunt u uw labelbeslissing bijvoorbeeld niet baseren op de deelnemers aan het bericht.

## <a name="train-a-model-for-the-first-time"></a>Een model voor het eerst trainen

1. Open in Microsoft 365-compliancecentrum een Advanced eDiscovery en selecteer vervolgens het **tabblad Revisiesets.**

2. Open een revisieset en klik vervolgens op **Voorspellende** codering beheren  >  **(voorbeeld)**.

3. Selecteer op **de pagina Voorspellende coderingsmodellen (voorbeeld)** het model dat u wilt trainen.

4. Klik op **het** tabblad Overzicht onder **Ronde 1** op **Volgende trainingsronde starten.**

   Het **tabblad** Training wordt weergegeven en bevat 50 items die u kunt labelen.

5. Controleer elk document en selecteer vervolgens de **knop Relevant** of **Niet relevant** onder aan het leesvenster om het te labelen.

   ![Elk document als relevant of niet relevant labelen](..\media\TrainModel1.png)

6. Nadat u alle 50 items hebt gelabeld, klikt u op **Voltooien.**

    Het duurt een paar minuten voordat het systeem 'leert' van uw labeling en het model bij werkt. Wanneer dit proces is voltooid, wordt de status **Ready** weergegeven voor het model op de pagina **Voorspellende coderingsmodellen (preview).**

## <a name="perform-additional-training-rounds"></a>Extra trainingsronden uitvoeren

Nadat u de eerste trainingsronde hebt gevolgd, kunt u de volgende trainingsronden uitvoeren door de stappen in de vorige sectie te volgen. Het enige verschil is het aantal trainingsronden dat wordt bijgewerkt op het **tabblad** Overzicht van het model. Na de eerste trainingsronde kunt u bijvoorbeeld op **Volgende** trainingsronde starten klikken om de tweede trainingsronde te starten. En zo verder.

Elke trainingsronde (zowel de trainingsrondes die worden uitgevoerd als de trainingsrondjes die zijn voltooid) wordt weergegeven op het **tabblad** Training voor het model. Wanneer u een trainingsrondje selecteert, wordt een flyoutpagina met informatie en metrische gegevens voor de ronde weergegeven.

## <a name="what-happens-after-you-perform-a-training-round"></a>Wat gebeurt er na het uitvoeren van een trainingsronde

Nadat u de eerste trainingsronde hebt gedaan, wordt een taak gestart die de volgende dingen doet:

- Op basis van de manier waarop u de 40 items in de trainingsset hebt gelabeld, leert het model van uw labeling en werkt het zichzelf bij om nauwkeuriger te worden.

- Het model verwerkt vervolgens elk item in de hele revisieset en wijst een voorspellingsscore toe tussen **0** (niet relevant) en **1** (relevant).

- Het model wijst een voorspellingsscore toe aan de tien items in de besturingselementset die u tijdens de trainingsronde hebt gelabeld. Het model vergelijkt de voorspellingsscore van deze 10 items met het label dat u tijdens de trainingsronde aan het item hebt toegewezen. Op basis van deze vergelijking identificeert het model de volgende classificatie (de matrix Verwarringsmatrix control *set)* om de voorspellingsprestaties van het model te beoordelen:

  |          |Model voorspelt dat item relevant is |Model voorspelt dat item niet relevant is |
  |:---------|:---------|:---------|
  |**Revisorlabelsitem als relevant**| Waar positief| Onwaar positief |
  |**Revisorlabelsitem als niet relevant**| Onwaar negatief |Waar negatief |
  ||||

  Op basis van deze vergelijkingen ontleent het model waarden voor de F-score, precisie- en recallmetrische gegevens en de foutmarge voor elk model. Scores voor deze modelprestatiegegevens worden weergegeven op een flyoutpagina voor de trainingsronde. Zie Voorspellende coderingsverwijzing voor een beschrijving van [deze metrische gegevens.](predictive-coding-reference.md)

- Ten slotte bepaalt het model de volgende 50 items die worden gebruikt voor de volgende trainingsronde. Deze keer kan het model 20 items uit de besturingselementset en 30 nieuwe items uit de revisieset selecteren en deze als de trainingsset voor de volgende ronde aanwijzen. De steekproeven voor de volgende trainingsronde worden niet uniform bemonsterd. Het model optimaliseert de steekproefselectie van items uit de revisieset om items te selecteren waar de voorspelling dubbelzinnig is, wat betekent dat de voorspellingsscore zich in het bereik 0,5 heeft. Dit proces wordt *beïnvloede selectie genoemd.*

### <a name="what-happens-after-you-perform-subsequent-training-rounds"></a>Wat gebeurt er nadat u de volgende trainingsronden hebt gevolgd?

Nadat u de volgende trainingsronden hebt gedaan (na de eerste trainingsronde), doet het model de volgende dingen:

- Het model wordt bijgewerkt op basis van de etiketten die u hebt toegepast op de trainingsset in die trainingsronde.

- Het systeem evalueert de voorspellingsscore van het model voor de items in de besturingselementset en controleert of de score wordt uitgelijnd met de manier waarop u items in de besturingselementset hebt gelabeld. De evaluatie wordt uitgevoerd op alle gelabelde items uit de besturingselementset voor alle trainingsronden. De resultaten van deze evaluatie worden opgenomen in het dashboard op **het tabblad** Overzicht voor het model.

- Het bijgewerkte model verwerkt elk item in de revisieset en wijst elk item een bijgewerkte voorspellingsscore toe.

## <a name="next-steps"></a>Volgende stappen

Nadat u de eerste trainingsronde hebt gedaan, kunt u meer trainingsronden uitvoeren of het voorspellingsscorefilter van het model toepassen op de revisieset om de items te bekijken die het model heeft voorspeld als relevant of niet relevant. Zie Een voorspellingsscorefilter toepassen [op een revisieset voor meer informatie.](predictive-coding-apply-prediction-filter.md)
