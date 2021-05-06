---
title: Uittreding van relevantiemodule in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: De module Relevantie in Advanced eDiscovery wordt op 10 maart 2021 ingetrokken. In dit artikel wordt uitgelegd wat u moet doen voordat Relevantie wordt ingetrokken. Met name het afronden van onvoltooide modellen door batchberekening uit te voeren, zodat u de metagegevens van het model kunt behouden.
ms.openlocfilehash: 22a7fc37a62dc665d4d798525d5e1e55250d0cb1
ms.sourcegitcommit: 719b89baca1bae14455acf2e517ec18fc473636c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/05/2021
ms.locfileid: "52161682"
---
# <a name="retirement-of-the-relevance-module-in-advanced-ediscovery"></a>De uittreding van de module Relevantie in Advanced eDiscovery

Op 10 maart 2021 trekken we de module Relevantie in Advanced eDiscovery. Deze uittreding betekent dat organisaties geen toegang meer hebben tot de module Relevantie (door te gaan naar Revisieset Relevantie beheren in een Advanced eDiscovery geval) of toegang hebben tot bestaande  >   relevantiemodellen. De huidige relevantiemodule die wordt uitgetrokken, wordt vervangen door een nieuwe oplossing voor voorspellende codering in Q2 CY 2021. Met deze nieuwe functionaliteit kunnen organisaties hun eigen voorspellende coderingsmodellen bouwen in een eenvoudigere en intuïtievere werkstroom.

Ter voorbereiding op deze aanstaande uittreding raden we organisaties aan die de uitvoer van hun model vóór de pensioendatum gebruiken, te exporteren door een batchberekening uit te voeren voor alle bestaande modellen. Alle relevantiescores van uw model worden permanent opgeslagen in de bijbehorende revisieset en toegankelijk wanneer documenten worden geëxporteerd. Relevantiescores blijven ook behouden als metagegevens in het laadbestand. U kunt ook nog steeds inhoud filteren in de revisieset op basis van relevantiescore en toegang hebben tot alle metagegevens die worden geproduceerd door uw relevantiemodellen.

## <a name="complete-unfinished-models"></a>Voltooide onvoltooide modellen

Voor onvoltooide relevantiemodellen kunt u de beoordeling, training en batchberekening voltooien, zodat u het model kunt toepassen op de documenten in een revisieset. Als u de batchberekening voltooit, blijven de gegevens behouden na de pensioendatum van de module Relevantie.

Hier volgen de stappen voor het voltooien van onvoltooide modellen:

1. Train uw model totdat het is gestabiliseerd en klaar is voor batchberekening. Zie [Training voor labelen en relevantie.](tagging-and-relevance-training-in-advanced-ediscovery.md)

   In de volgende schermafbeelding ziet u een module die klaar is voor een batchberekening. De evaluatie en training zijn voltooid en de volgende stap is het uitvoeren van batchberekening.

   ![Schermafbeelding van model dat klaar is voor batchberekening](../media/ReadyForBatchCalculation.png)

2. Voer de batchberekening uit. Zie [Batchberekening uitvoeren.](track-relevance-analysis-in-advanced-ediscovery.md#performing-batch-calculation)

3. Controleer of batchberekening is gelukt. Zie [Batchberekeningsresultaten](track-relevance-analysis-in-advanced-ediscovery.md#batch-calculation-results).

Neem contact op met Microsoft Support voor hulp bij het voltooien van onvoltooide relevantiemodellen.
