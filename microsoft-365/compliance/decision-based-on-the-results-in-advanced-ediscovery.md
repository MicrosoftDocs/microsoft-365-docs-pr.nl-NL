---
title: Beslissing op basis van de resultaten in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: aed65bcd-0a4f-43e9-b5e5-b98cc376bdf8
description: Lees hoe het tabblad Beslissen in Advanced eDiscovery gegevens bevat die u kunnen helpen bij het bepalen van de juiste grootte van de revisieset met hoofddossiers.
ROBOTS: NOINDEX, NOFOLLOW
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7a4c2fe891a48451d9b8d852f603b225ab7b080d
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/06/2021
ms.locfileid: "52161664"
---
# <a name="decisions-based-on-relevance-results-in-advanced-ediscovery"></a>Beslissingen op basis van relevantieresultaten in Advanced eDiscovery
  
In de module Relevantie in Advanced eDiscovery bevat het tabblad Beslissen aanvullende informatie voor het weergeven en gebruiken van statistieken voor beslissingsondersteuning voor het bepalen van de grootte van de revisieset met hoofddossiers.
  
## <a name="using-the-decide-tab"></a>Het tabblad Beslissen gebruiken

![Relevantie bepalen](../media/f32fed89-f3b5-404a-90c7-ea25d2eb58a9.png)
  
Dit tabblad bevat de volgende onderdelen:
  
- **Probleem:** Hier kunt u het probleem van belang selecteren in de lijst.

- **Review-recall ratio:** Vergelijkingen van Advanced eDiscovery beoordeling op basis van relevantiescores. Het cutoff-punt in de grafiek vertegenwoordigt het percentage bestanden dat moet worden beoordeeld, dat is toegesneden op een relevantiescore. Dit wordt gebruikt in de fase Relevantietest en als exportdrempel voor ruiming. Het standaardbezuiningspunt voor het aantal bestanden dat moet worden beoordeeld, ligt op het punt waarop de balans tussen Inroepen en Precisie optimaal is. Het werkelijke snijpunt moet door de gebruiker worden bepaald, afhankelijk van de doelstellingen en de kostenruil (%beoordeling) en het risico (%recall). Met de schuifregelaar kunt u het snijpunt aanpassen en het effect op de grafiek en parameters zien, bij het aanpassen van het percentage relevante bestanden dat moet worden opgehaald en voordat u een beslissing valideert.

- **Parameters**: Controleren, Inroepen, Volgende relevante en totale kostenparameters zijn cumulatieve berekende statistieken met betrekking tot de revisieset ten opzichte van de verzameling voor het hele geval. Definities voor deze parameters zijn als volgt:

  - **Controleren:** Percentage bestanden dat u wilt controleren op basis van deze cutoff.

  - **Inroepen:** Percentage relevante bestanden in de revisieset.

  - **Volgende relevant:** Kosten voor het controleren en identificeren van een ander relevant bestand dat momenteel niet in de revisieset staat.

  - **Totale kosten:** Kosten voor het controleren van dit percentage van de casebestanden. Instellingen voor kostenparameters kunnen worden ingesteld door Case manager.

  - **Verdeling op relevantiescore:** Bestanden in de donkergrijse weergave aan de linkerkant staan onder de cutoffscore. Met een knoptip worden de relevantiescore en het gerelateerde percentage bestanden weergegeven in het revisiebestand dat is ingesteld ten opzichte van het totale aantal bestanden.

In het deelvenster **Uitgebreide details** worden meer details weergegeven. Bestanden in verzamelingscijfers bevatten geen lege of nevelige bestanden. Gezinsbestanden zijn bestanden die niet zijn geladen in Relevantie, maar nog steeds worden meegetelde als onderdeel van het gezin.
