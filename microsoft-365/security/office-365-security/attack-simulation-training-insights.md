---
title: Meer inzicht krijgen middels aanvalssimulatietraining
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Beheerders kunnen zien hoe aanvals training in het Microsoft 365-Beveiligingscentrum van invloed is op werknemers en inzicht krijgen in de resultaten van simulatie en training.
ms.openlocfilehash: 54855a4ce8e64f4d58b9ff2697395ed684be2773
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794554"
---
# <a name="gain-insights-through-attack-simulation-training"></a>Meer inzicht krijgen middels aanvalssimulatietraining

In simulatie training voor een aanval biedt Microsoft u inzichten op basis van de resultaten van simulaties en opleidingen waarvan de werknemers zijn gekomen. Met deze inzichten wordt u op de hoogte gehouden van de voortgang van uw werknemers, en adviseert u de volgende stappen om uw werknemers en uw omgeving beter voor te bereiden op aanvallen.

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

We werken voortdurend aan de uitbreiding van de inzichten die voor u beschikbaar is. De werking van gedrag en aanbevolen acties zijn momenteel beschikbaar. Als u wilt beginnen, gaat u naar [training voor simulatie van aanval in het Microsoft 365-Beveiligingscentrum](https://security.microsoft.com/attacksimulator?viewid=overview).

## <a name="behavior-impact-on-compromise-rate"></a>Werking van invloed op compromissen

Op het tabblad **overzicht** van simulatie van aanval aanval ziet u de **gevolgen voor compromissen voor de beoordeling van de compromissen** . Op deze kaart ziet u hoe werknemers omgaan met de simulaties die u hebt gemaakt, contrast voor de **voorspelde compromis graad**. U kunt deze inzichten gebruiken om de voortgang van de werknemers gereed te houden door meerdere simulaties uit te voeren voor dezelfde groepen werknemers.

In de grafiek ziet u:

- **Voorspelbare compromis graad** waarbij de gemiddelde compromis graad voor simulaties wordt gebruikt met hetzelfde type nettolading in andere microsoft 365-tenants die gebruikmaken van simulatie training.
- De **effectieve baudrate** weerspiegelt het percentage van de werknemers dat is gezakt voor de simulatie.

Daarnaast `<number> less susceptible to phishing` weerspiegelt het verschil tussen het werkelijke aantal werknemers dat is aangetast door de aanval en de voorspelde compromissen. Dit aantal werknemers is minder waarschijnlijk met soortgelijke aanvallen in de toekomst, terwijl ook `<percent%> better than predicted rate` wordt aangegeven hoe werknemers in het geheel hebben gereageerd op het voor spelde compromis.

> [!div class="mx-imgBorder"]
> ![Kaart voor gedrag van gedrag bij simulatie van aanvals overzicht](../../media/attack-sim-preview-behavior-impact-card.png)

Als u een gedetailleerdere rapporten wilt weergeven, klikt u op **simulaties weergeven en rapport over trainings effectiviteit**. Dit rapport bevat dezelfde informatie met aanvullende context uit de simulatie zelf (bijvoorbeeld simulatie techniek en totaal aantal gebruikers die zijn gericht).

## <a name="recommended-actions"></a>Aanbevolen acties

Wanneer u op het [tabblad **simulaties**](https://security.microsoft.com/attacksimulator?viewid=simulations)een simulatie selecteert, krijgt u de gewenste details van de simulatie, waar u de sectie **aanbevolen acties** vindt.

De sectie aanbevolen acties bevat een beschrijving van de aanbevelingen die beschikbaar zijn in [Microsoft Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score). Deze aanbevelingen zijn gebaseerd op de nettolading die wordt gebruikt in de simulatie en helpt u bij het beschermen van uw werknemers en uw omgeving. Door te klikken op elke actie bij verbetering gaat u naar de details.

> [!div class="mx-imgBorder"]
> ![Sectie aanbevelings acties voor simulatie van aanval](../../media/attack-sim-preview-recommended-actions.png)

## <a name="related-links"></a>Verwante koppelingen

**Aanvals Simulator** [Maak een simulatie aanval](attack-simulation-training.md) en [Maak een nettolading voor de opleiding van uw personen](attack-simulation-training-payloads.md)
