---
title: Inzicht in regels voor langzame e-mailstroom oplossen
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37125cdb-715d-42d0-b669-1a8efa140813
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen leren hoe u het probleem kunt verhelpen met behulp van het artikel over het oplossen van problemen in de beveiliging & nalevings centrum voor het identificeren en oplossen van onjuiste of verbroken e-mail stroom regels (ook wel een transportregel genoemd) in hun organisatie.
ms.openlocfilehash: c933a6816c82161d0f4a6199ff1a339dd8a10eae
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/03/2020
ms.locfileid: "47357342"
---
# <a name="fix-slow-mail-flow-rules-insight-in-the-security--compliance-center"></a>Inzicht in langzame e-mail stroom regels in het nalevings centrum voor beveiliging &

In de efficiëntie regels voor de e-mail stroom (ook wel transport-regels genoemd) kan de e-mail stroom vertragingen voor uw organisatie veroorzaken. Dit inzicht geeft een overzicht van e-mail stroom regels met gevolgen voor de e-mail stroom van uw organisatie. Voorbeelden van dit soort regels zijn:

- Voorwaarden die **deel uitmaakt van** grote groepen.
- Voorwaarden die gebruikmaken van complexe reguliere expressies (regex)-patroon.
- Voorwaarden voor het gebruik van inhouds controle in bijlagen.

Met het beleid voor **trage e-mail stroom** kunt u het aanbevolen gebied van het [Dashboard voor e-mail stroom](mail-flow-insights-v2.md) in het [Beveiligingscentrum](https://protection.office.com) **voor** e-mail stroom op de beveiliging & Dit inzicht wordt alleen weergegeven nadat de voorwaarde is vastgesteld (als u geen e-mail lussen hebt, ziet u het inzicht niet).

U kunt deze melding gebruiken om de regels voor de e-mail stroom te identificeren en te perfectioneren, zodat de vertragingen van e-mailberichten kunnen worden beperkt.

![Meer inzicht in langzame e-mail stroom regels op het gebied aanbevolen voor u in het dashboard voor e-mail stroom](../../media/mfi-fix-slow-mail-flow-rules.png)

Wanneer u op Details van het object **weergeven** klikt, verschijnt er een flyout met meer informatie:

- **Regel**: u kunt de muisaanwijzer op het overzicht plaatsen om alle voorwaarden, uitzonderingen en acties van de regel te zien. U kunt op het overzicht klikken om de regel in het Exchange-Beheercentrum (SBV) te bewerken.
- **Aantal geëvalueerde berichten**: u kunt op **voorbeeldberichten weergeven** klikken om de resultaten van de [bericht tracering](message-trace-scc.md) te zien voor een voorbeeld van de berichten die door de regel werden beïnvloed.
- **Gemiddelde tijd die is besteed aan elk bericht**
- **Mediaan tijd besteed aan een bericht**: de middelste waarde die de bovenste helft van de onderste helft van de gegevens scheidt.

![Voorbeeld van een flyout dat wordt weergegeven nadat u op Details weergeven hebt geklikt in de regel langzame e-mail stroom](../../media/mfi-fix-slow-mail-flow-rules-details.png)

Zie voor meer informatie over voorwaarden en uitzonderingen in de e-mail stroom regels in Exchange Online: [voorwaarden voor de e-mail stroom regels en uitzonderingen (predikaten) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).

## <a name="related-topics"></a>Verwante onderwerpen

Zie voor meer informatie over andere inzichten in het dashboard voor e-mail stroom de [e-mail stroom inzichten in het artikel over de beveiliging & nalevings centrum](mail-flow-insights-v2.md).
