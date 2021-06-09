---
title: Een voorspellend coderingsmodel maken in Advanced eDiscovery
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
description: Meer informatie over het maken van een voorspellend coderingsmodel in Advanced eDiscovery. Dit is de eerste stap in het gebruik van de mogelijkheden voor machine learning in Advanced eDiscovery om relevante en niet-relevante inhoud in een revisieset te identificeren.
ms.openlocfilehash: 7724062848d8d757fbfd3a7870853d6f2c409d84
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822516"
---
# <a name="create-a-predictive-coding-model-preview"></a>Een voorspellend coderingsmodel maken (voorbeeld)

De eerste stap bij het gebruik van de mogelijkheden voor machine learning van voorspellende codering in Advanced eDiscovery is het maken van een voorspellend coderingsmodel. Nadat u een model hebt gemaakt, kunt u het model trainen om de relevante en niet-relevante inhoud in een revisieset te identificeren.

Zie Meer informatie over voorspellende codering [in](predictive-coding-overview.md#the-predictive-coding-workflow) Advanced eDiscovery

## <a name="before-you-create-a-model"></a>Voordat u een model maakt

- Er moeten minimaal 2000 items in een revisieset staan om een voorspellend coderingsmodel te maken.

- Zorg ervoor dat u alle verzamelingen aan de revisieset verbindt voordat u een model maakt. Items die zijn toegevoegd aan een revisieset nadat het model is gemaakt, worden niet verwerkt en krijgen een voorspellingsscore die door het model wordt gegenereerd.

- Elk item in de revisieset dat geen tekst bevat, wordt niet verwerkt door het model of een voorspellingsscore toegewezen. Items met tekst worden opgenomen in de besturingselementset of een trainingsset.

## <a name="create-a-model"></a>Een model kiezen

1. Open in Microsoft 365 compliancecentrum een Advanced eDiscovery en selecteer vervolgens **het tabblad Revisiesets.**

2. Open een revisieset en klik vervolgens op **Voorspellende** codering beheren  >  **(voorbeeld)**.

   ![Klik in de vervolgkeuzelijst Analyseren in de revisieset om naar de pagina Voorspellende codering te gaan](..\media\ManagePredictiveCoding.png)

3. Klik op **de pagina Voorspellende coderingsmodellen (voorbeeld)** op **Nieuw model.**

4. Typ op de flyoutpagina een naam voor het model en een optionele beschrijving.

5. Desgewenst kunt u geavanceerde instellingen configureren  (door te klikken op Geavanceerde opties op de flyoutpagina) die betrekking hebben op het betrouwbaarheidsniveau en de foutmarge. Deze instellingen zijn van invloed op het aantal items in de besturingselementset. De *besturingselementset* wordt gebruikt tijdens het trainingsproces om de voorspellingsscores te evalueren die het model aan items toewijst met de labeling die u tijdens de trainingsronden uit te voeren. Als uw organisatie richtlijnen heeft voor betrouwbaarheidsniveau en foutmarge voor documentbeoordeling, geeft u deze op in de juiste vakken. Gebruik anders de standaardinstellingen.

6. Klik **op Opslaan** om het model te maken.

   Het duurt een paar minuten voordat het systeem uw model heeft voorbereid. Nadat het klaar is, kunt u de eerste trainingsronde uitvoeren.

## <a name="what-happens-after-you-create-a-model"></a>Wat gebeurt er nadat u een model hebt gemaakt

Nadat u een model hebt gemaakt, treden de volgende dingen op de achtergrond op tijdens het maken en voorbereiden van het model:

- Het systeem berekent het aantal items voor de besturingselementset. Deze grootte is gebaseerd op het aantal items in de revisieset en de instellingen voor het betrouwbaarheidsniveau en de foutmarge. Items voor de besturingselementset worden willekeurig geselecteerd en aangewezen als items in de besturingselementset. Het systeem bevat 10 items uit de besturingselementset in de eerste trainingsronde.

- Het systeem selecteert willekeurig 40 items uit de revisieset die moeten worden opgenomen in de trainingsset voor de eerste trainingsronde. Daarom bevat de eerste trainingsronde 50 items voor labeling: 40 items uit de trainingsset en 10 items uit de besturingselementset.

## <a name="next-steps"></a>Volgende stappen

Nadat u een model voor een revisieset hebt gemaakt, is de volgende stap het uitvoeren van trainingsronden om het model te 'onderwijzen' om inhoud te identificeren die relevant is voor uw onderzoek. Zie Een voorspellend coderingsmodel trainen voor [meer informatie.](predictive-coding-train-model.md)
