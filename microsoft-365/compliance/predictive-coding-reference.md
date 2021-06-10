---
title: Referentie predictief coderen
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
ms.openlocfilehash: 90c76fade54c109fc02e145a49bbe93d11ad8b79
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822492"
---
# <a name="predictive-coding-reference-preview"></a>Voorspellende coderingsverwijzing (voorbeeld)

In dit artikel worden de belangrijkste concepten en metrische gegevens beschreven van het hulpprogramma voor voorspellende codering in Advanced eDiscovery. De secties in het artikel worden in alfabetische volgorde weergegeven.

## <a name="confidence-level"></a>Betrouwbaarheidsniveau

Het betrouwbaarheidsniveau is een geavanceerde instelling wanneer u een voorspellend coderingsmodel maakt. Het definieert dat de prestatiegegevens van het model (bijvoorbeeld rijkheid, precisie en terugroepen) binnen een opgegeven bereik vallen (dat de foutmarge bepaalt die voor het model is gedefinieerd) die representatief is voor de werkelijke waarden van de voorspellingsscores die het model toewijst aan items in de revisieset. De waarden voor het betrouwbaarheidsniveau en de foutmarge bepalen ook hoeveel items in de besturingselementset zijn opgenomen. De standaardwaarde voor het betrouwbaarheidsniveau is 0,95 of 95%.

## <a name="control-set"></a>Besturingselementset

Een besturingselementset wordt gebruikt tijdens het trainingsproces van een voorspellend coderingsmodel. De besturingselementset is om de voorspellingsscores te evalueren die het model aan items toewijst met de labeling die u tijdens trainingsronden voert. De grootte van de besturingselementset is gebaseerd op het aantal items in de revisieset en het betrouwbaarheidsniveau en de marge van foutwaarden die zijn ingesteld bij het maken van het model. Items in de besturingselementset worden nooit gewijzigd en zijn niet identificeerbaar voor gebruikers. Het totale aantal items in de besturingselementset wordt weergegeven op de flyoutpagina voor een trainingsronde.

## <a name="control-set-confusion-matrix"></a>Besturingselementen instellen verwarringsmatrix

Nadat u een trainingsronde hebt voltooid, wijst het model een voorspellingsscore toe aan de tien items in de besturingselementset die u tijdens de trainingsronde hebt gelabeld. Het model vergelijkt de voorspellingsscore van deze 10 items met het label dat u tijdens de trainingsronde aan het item hebt toegewezen. Op basis van deze vergelijking identificeert het model de volgende classificaties om de voorspellingsprestaties van het model te beoordelen:
  
  |          |Model voorspelt dat item relevant is |Model voorspelt dat item niet relevant is |
  |:---------|:---------|:---------|
  |**Revisorlabelsitem als relevant**| Waar positief| Onwaar positief |
  |**Revisorlabelsitem als niet relevant**| Onwaar negatief |Waar negatief |
  ||||

  Op basis van deze vergelijkingen ontleent het model waarden voor de F-score, precisie- en recallmetrische gegevens en de foutmarge voor elk model. Het aantal verwarringstypen uit de matrix wordt weergegeven op de flyoutpagina voor een trainingsronde.

## <a name="f-score"></a>F-score

De F-score is een gewogen gemiddelde van de scores voor de precisie- en terugroepmetingen.  Het bereik van de scores voor deze metriek is **0** tot **1**. Een score dichter bij **1** geeft aan dat het model relevante items nauwkeuriger detecteert. De metrische F-score wordt weergegeven op het modeldashboard en op de flyoutpagina voor elke trainingsronde.

## <a name="margin-of-error"></a>Foutmarge

De foutmarge is een geavanceerde instelling wanneer u een voorspellende coderingsmodus maakt. Hiermee wordt de mate van fout opgegeven in prestatiemetrische gegevens (bijvoorbeeld rijkheid, precisie en inroepen) die is afgeleid van de willekeurige steekproef van items in uw besturingselementset. Voor een lagere foutmarge is een grotere besturingsset vereist om ervoor te zorgen dat de prestatiegegevens van het model binnen een kleiner bereik vallen. De waarden voor de foutmarge en het betrouwbaarheidsniveau bepalen ook hoeveel items in de besturingselementset zijn opgenomen. De standaardwaarde voor de foutmarge is 0,05 of 5%.

## <a name="model-stability"></a>Modelstabiliteit

Modelstabiliteit geeft aan dat het model in staat is om nauwkeurig te voorspellen of een document in een revisieset relevant is of niet. Als een model instabiel is, moeten mogelijk meer trainingsronden worden uitgevoerd om de stabiliteit van het model op te nemen. Als het model stabiel is, hoeven er mogelijk geen trainingsronden meer te worden uitgevoerd. Het modeldashboard geeft de huidige status van de stabiliteit van het model aan. Wanneer een model stabiel is, hebben de prestatiegegevens een niveau bereikt dat overeenkomt met de instellingen voor het betrouwbaarheidsniveau en de foutmarge.

## <a name="overturn-rate"></a>Omverdraaiingstarief

De omslagsnelheid is het percentage items in de revisieset waarin de voorspellingsscore tussen trainingsronden is gewijzigd. Een model wordt als stabiel beschouwd wanneer de ombouwsnelheid kleiner is dan 5%. De metrische omslagsnelheid wordt weergegeven op het modeldashboard en op de flyoutpagina voor elke trainingsronde. De kantelsnelheid voor de eerste trainingsronde is nul omdat er geen eerdere voorspellingsscore is die moet worden omgedraaid.

## <a name="precision"></a>Precisie

De precisiemetrische meet de verhouding van de items die daadwerkelijk relevant zijn voor de items die het voorspelde model relevant was. Dit betekent dat items in de besturingselementenset het label relevant vinden voor de revisor en worden voorspeld als relevant voor het model. Het bereik van de scores voor deze metriek is **0** tot **1**. Een score dichter bij **1** geeft aan dat het model minder niet-relevante items identificeert. De precisiemetrische gegevens worden weergegeven op het modeldashboard en op de flyoutpagina voor elke trainingsronde.

## <a name="prediction-score"></a>Voorspellingsscore

Dit is de score die een model aan elk document in een revisieset toewijst. De score is gebaseerd op de relevantie van het document in vergelijking met het leren van het model uit de trainingsronden. In het algemeen worden items met voorspellingsscores tussen **0** en **0,5** als niet relevant beschouwd en items met voorspellingsscores tussen **0,5** en **1** worden als relevant beschouwd. De voorspellingsscore staat in een metagegevensveld van een document. U kunt een voorspellingsfilter gebruiken om de items weer te geven in een revisieset die binnen een opgegeven voorspellingsbereik vallen.

## <a name="recall"></a>Inroepen

De inroepingsmetrische meet meet het deel van de items die het voorspelde model relevant was voor items die daadwerkelijk relevant zijn. Dit betekent dat items in de besturingselementset die volgens het voorspelde model relevant waren, ook door de revisor als relevant zijn aangeduid. Het bereik van de scores voor deze metriek is **0** tot **1**. Een score dichter bij **1** geeft aan dat het model een groter deel van de relevante items identificeert. De inroepingsmetrische gegevens worden weergegeven op het modeldashboard en op de flyoutpagina voor elke trainingsronde.

## <a name="review-set"></a>Revisieset

Een revisieset biedt het bereik van een voorspellend coderingsmodel. Wanneer u een nieuw model voor de revisieset maakt, worden items voor de besturingselementset en trainingssets geselecteerd in de revisieset. Wanneer het model voorspellingsscores toewijst, worden deze scores toegewezen aan de items in de revisie. U moet alle items toevoegen aan de revisieset voordat u een voorspellend coderingsmodel maakt. Als u items toevoegt nadat u een model hebt gemaakt, krijgen deze items geen voorspellingsscore toegewezen.

## <a name="richness"></a>Rijkheid

De rijkheidsmetrische meet het percentage revisiesetitems dat het model als relevant voorspelt. Het bereik van de scores voor deze metriek is **0** tot **1**. De rijkheidsmetrische gegevens worden weergegeven op het modeldashboard.

## <a name="sampled-items"></a>Bemonsterde items

De term *bemonsterde items* is een verwijzing naar willekeurige voorbeelden van items in een revisieset (die tekst bevatten) die zijn geselecteerd en gekoppeld aan de besturingselementenset wanneer u een voorspellend coderingsmodel maakt. Er wordt ook een steekproef met items geselecteerd voor elke trainingsronde. Items die zijn geselecteerd voor de besturingselementset van een model, worden nooit opgenomen in een trainingsset voor hetzelfde model. Het omgekeerde geldt ook: trainingssetitems worden nooit opgenomen in de besturingselementenset.

## <a name="training-set"></a>Trainingsset

Het model selecteert willekeurig items uit de revisieset en voegt deze toe aan een trainingsset. Tijdens een trainingsronde worden items uit de trainingsset (naast items uit de besturingselementset) aan u gepresenteerd, zodat u ze allemaal kunt labelen als 'relevant' of 'niet relevant'. Met dit labeling- of trainingsproces leert het model hoe u kunt voorspellen welke items in de revisie relevant of niet relevant zijn. Telkens wanneer u een trainingsronde voert, selecteert het model meer items uit de review en voegt het deze toe aan de trainingsset voor die trainingsronde. Items uit de besturingselementset worden nooit geselecteerd voor een trainingsset.
