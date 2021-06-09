---
title: Module voor voorspellende codering voor Advanced eDiscovery (voorbeeld)
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
description: De nieuwe module voor voorspellende codering in Advanced eDiscovery gebruikt machine learning om items in een revisieset te analyseren om te voorspellen welke items relevant zijn voor uw zaak of onderzoek.
ms.openlocfilehash: 3c8fbd75bd585dd6ae722bf17deea906611d8df6
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822034"
---
# <a name="learn-about-predictive-coding-in-advanced-ediscovery-preview"></a>Meer informatie over voorspellende codering in Advanced eDiscovery (voorbeeld)

De module voor voorspellende codering in Advanced eDiscovery maakt gebruik van de intelligente, machine learning-mogelijkheden om u te helpen de hoeveelheid te controleren inhoud te beperken. Met voorspellende codering kunt u grote hoeveelheden case-inhoud beperken en verwijderen tot een relevante set items die u voor controle kunt prioriteren. Dit wordt gedaan door uw eigen voorspellende coderingsmodellen te maken en te trainen, zodat u prioriteit kunt geven aan de beoordeling van de meest relevante items in een revisieset.

De module voor voorspellende codering is ontworpen om de complexiteit van het beheren van een model in een revisieset te stroomlijnen en biedt een iteratieve benadering voor het trainen van uw model, zodat u sneller aan de slag kunt met de mogelijkheden voor machine learning in Advanced eDiscovery. Om aan de slag te gaan, kunt u een model maken, maar liefst 50 items labelen als relevant of niet relevant. Het systeem gebruikt deze training om voorspellingsscores toe te passen op elk item in de revisieset. Hiermee kunt u items filteren op basis van de voorspellingsscore, zodat u eerst de meest relevante (of niet-relevante) items kunt bekijken. Als u modellen met hogere nauwkeurigheid en terugroeptarieven wilt trainen, kunt u items in de volgende trainingsronden blijven labelen totdat het model zich stabiliseert.  

## <a name="the-predictive-coding-workflow"></a>De werkstroom voor voorspellende codering

Hier is een overzicht en beschrijving van elke stap voorspellende coderingswerkstroom. Zie Predictive coding reference (Voorspellende coderingsverwijzing) voor een gedetailleerdere beschrijving van de concepten en terminologie van het [voorspellende coderingsproces.](predictive-coding-reference.md)

![Werkstroom voor voorspellende codering](..\media\PredictiveCodingWorkflow.png)

1. **Maak een nieuw voorspellend coderingsmodel in de revisieset.** De eerste stap is het maken van een nieuw voorspellend coderingsmodel in de revisieset. U moet ten minste 2.000 items in de revisieset hebben om een model te maken. Nadat u een model hebt gemaakt, bepaalt het systeem het aantal items dat als *besturingselementset moet worden gebruikt.* De besturingselementenset wordt gebruikt tijdens het trainingsproces om de voorspellingsscores te evalueren die het model aan items toewijst met de labeling die u tijdens trainingsronden voert. De grootte van de besturingselementset is gebaseerd op het aantal items in de revisieset en het betrouwbaarheidsniveau en de marge van foutwaarden die zijn ingesteld bij het maken van het model. Items in de besturingselementset worden nooit gewijzigd en zijn niet identificeerbaar voor gebruikers.

   Zie Een [voorspellend coderingsmodel maken](predictive-coding-create-model.md)voor meer informatie.

2. **Voltooi de eerste trainingsronde door items te labelen als relevant of niet relevant.** De volgende stap is het trainen van het model door de eerste trainingsronde te starten. Wanneer u een trainingsronde start, selecteert het model willekeurig extra items uit de revisieset, die de *trainingsset wordt genoemd.* Deze items (zowel uit de besturingselementenset als de trainingsset) worden aan u gepresenteerd, zodat u elke items kunt labelen als 'relevant' of 'niet relevant'. Relevantie is gebaseerd op de inhoud in het item en niet op een van de metagegevens van het document. Nadat u het labelproces in de trainingsronde hebt voltooid, wordt het model 'leren' op basis van hoe u de items in de trainingsset hebt gelabeld. Op basis van deze training verwerkt het model de items in de revisieset en wordt een voorspellingsscore op elk van de items toegepast.

   Zie Een voorspellend coderingsmodel trainen voor [meer informatie.](predictive-coding-train-model.md)

3. **Pas het voorspellingsscorefilter toe op items in de revisieset.** Nadat de vorige trainingsstap is voltooid, is de volgende stap het toepassen van het voorspellingsscorefilter op de items in de revisie om de items weer te geven die volgens het model het meest relevant zijn (u kunt ook een voorspellingsfilter gebruiken om items weer te geven die 'niet relevant' zijn). Wanneer u het voorspellingsfilter toe te passen, geeft u een bereik van voorspellingsscores op om te filteren. Het bereik van de voorspellingsscores valt tussen **0** en **1,** met **0** als 'niet-relevant' en **1** als relevant. In het algemeen worden items met voorspellingsscores tussen **0** en **0,5** beschouwd als 'niet-relevant' en items met voorspellingsscores tussen **0,5** en **1** worden als relevant beschouwd.

   Zie Een voorspellingsfilter [toepassen op een revisieset voor meer informatie.](predictive-coding-apply-prediction-filter.md)

4. **Voer meer trainingsronden uit totdat het model is gestabiliseerd.** U kunt extra trainingsronden uitvoeren als u een model wilt maken met een hogere nauwkeurigheid van de voorspelling en hogere terugroeptarieven. *Inroepsnelheid* meet het percentage items dat het voorspelde model relevant was voor items die daadwerkelijk relevant zijn (de items die u tijdens de training hebt gemarkeerd als relevant). De score voor inroepen varieert **van 0** tot **1**. Een score dichter bij **1** geeft aan dat het model relevantere items identificeert. In een nieuwe trainingsronde labelt u extra items in een nieuwe trainingsset. Nadat u de trainingsronde hebt voltooid, wordt het model bijgewerkt op basis van nieuwe informatie over uw meest recente ronde labelitems in de trainingsset. Het model verwerkt de items in de revisieset opnieuw en pas nieuwe voorspellingsscores toe. U kunt trainingsrondes blijven uitvoeren totdat uw model is gestabiliseerd. Een model wordt als stabiel beschouwd wanneer het verlooppercentage na de laatste trainingsronde kleiner is dan 5%. *Het verlooppercentage* wordt gedefinieerd als percentage van items in een revisieset waarin de voorspellingsscore tussen trainingsronden is gewijzigd. Het dashboard voor voorspellende codering bevat informatie en statistieken die u helpen bij het beoordelen van de stabiliteit van een model.

5. **Pas het filter 'uiteindelijke' voorspellingsscore toe om de setitems te controleren om prioriteit te geven aan de beoordeling.** Nadat u alle trainingsronden hebt voltooid en het model hebt gestabiliseerd, is de laatste stap het toepassen van de uiteindelijke voorspellingsscore op de revisieset om prioriteit te geven aan de beoordeling van relevante en niet-relevante items. Dit is dezelfde taak die u hebt uitgevoerd in stap 3, maar op dit moment is het model stabiel en bent u niet van plan meer trainingsronden uit te voeren.
