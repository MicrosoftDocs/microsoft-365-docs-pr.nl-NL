---
title: Meer inzicht krijgen middels aanvalssimulatietraining
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Beheerders kunnen leren hoe training voor de aanvalssimulatie in het Microsoft 365-beveiligingscentrum van invloed is op werknemers en inzichten kunnen krijgen uit simulatie- en trainingsresultaten.
ms.technology: mdo
ms.openlocfilehash: 93d8829f9fbc4271d33e3208e5564529b4022fc3
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204075"
---
# <a name="gain-insights-through-attack-simulation-training"></a>Meer inzicht krijgen middels aanvalssimulatietraining

In de trainingstraining aanvalssimulatie biedt Microsoft u inzichten op basis van resultaten van simulaties en trainingen die werknemers hebben doormaakt. Deze inzichten helpen u op de hoogte te blijven van de voortgang van de bedreigingsbereidheid van uw werknemers en u kunt ook de volgende stappen aanbevelen om uw werknemers en uw omgeving beter voor te bereiden op aanvallen.

We werken voortdurend aan het uitbreiden van de inzichten die voor u beschikbaar zijn. Gedrag en aanbevolen acties zijn momenteel beschikbaar. Om te beginnen gaat u naar De training voor de [aanvalssimulatie in het Microsoft 365-beveiligingscentrum.](https://security.microsoft.com/attacksimulator?viewid=overview)

## <a name="behavior-impact-on-compromise-rate"></a>Effect op het gedrag van compromissen

Op het **tabblad Overzicht** van de trainingstraining aanvalssimulatie vindt u de invloed van het gedrag op de kaart **met compromispercentages.** Op deze kaart ziet u hoe werknemers om zijngegaan met de simulaties die u hebt uitgevoerd, in tegenstelling tot het **voorspelde compromispercentage.** U kunt deze inzichten gebruiken om de voortgang in de gereedheid van bedreigingen voor werknemers bij te houden door meerdere simulaties uit te werken tegen dezelfde groepen werknemers.

In de grafiek ziet u:

- **Voorspelde compromissnelheid** die de gemiddelde compromissnelheid weerspiegelt voor simulaties die hetzelfde type payload gebruiken voor andere Microsoft 365-tenants die gebruikmaken van de trainingstraining Aanvalssimulatie.
- **Het werkelijke compromispercentage** weerspiegelt het percentage werknemers dat voor de simulatie is gevallen.

Daarnaast wordt het verschil weerspiegeld tussen het werkelijke aantal werknemers dat door de aanval is gecompromitteerd `<number> less susceptible to phishing` en het voorspelde compromispercentage. Dit aantal werknemers wordt in de toekomst minder vaak door soortgelijke aanvallen gecompromitteerd, maar geeft aan hoe werknemers het over het algemeen hebben gedaan, in tegenstelling tot het `<percent%> better than predicted rate` voorspelde compromispercentage.

> [!div class="mx-imgBorder"]
> ![Behavior impact card on Attack simulation training overview](../../media/attack-sim-preview-behavior-impact-card.png)

Als u een gedetailleerder rapport wilt bekijken, klikt u op Simulaties en **trainingsre doeltreffendheidsrapport weergeven.** Dit rapport bevat dezelfde informatie met aanvullende context uit de simulatie zelf (bijvoorbeeld de simulatietechniek en het totale aantal beoogde gebruikers).

## <a name="recommended-actions"></a>Aanbevolen acties

Op het [ **tabblad Simulaties** gaat](https://security.microsoft.com/attacksimulator?viewid=simulations)u met het selecteren van een simulatie naar de details van de simulatie, waar u de sectie **Aanbevolen acties** vindt.

In de sectie Aanbevolen acties worden aanbevelingen be details gegeven die beschikbaar zijn in [Microsoft Secure Score.](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-secure-score) Deze aanbevelingen zijn gebaseerd op de payload die in de simulatie wordt gebruikt en helpen u uw werknemers en uw omgeving te beschermen. Als u op elke verbeteringsactie klikt, krijgt u de details.

> [!div class="mx-imgBorder"]
> ![Sectie Aanbevelingsacties over training voor aanvalssimulatie](../../media/attack-sim-preview-recommended-actions.png)

## <a name="related-links"></a>Gerelateerde koppelingen

[Aan de slag met aanvalssimulatietraining](attack-simulation-training-get-started.md)

[Een phishing-aanvalssimulatie maken](attack-simulation-training.md)

[een payload maken voor het trainen van uw personen](attack-simulation-training-payloads.md)
