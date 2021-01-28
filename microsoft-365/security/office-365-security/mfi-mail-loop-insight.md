---
title: Inzicht in mogelijke e-maillus oplossen
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: cb801985-3c89-4979-9c18-17829a4cb563
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen leren hoe u met behulp & van het hulpprogramma voor het oplossen van e-mail lussen in hun organisatie e-mail lussen kunt identificeren en oplossen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f08c27c761cdfe4acbbd8cf80e8ab6da8012b55f
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029892"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a>Mogelijke oplossing voor e-mail lussen in de beveiligings & nalevings centrum

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


E-mail lussen zijn ongeldig omdat:

- Ze verspillen systeembronnen.
- De persoon die het e-mail volume quotum van uw organisatie gebruikt.
- Ze verzenden ongeniet-bezorgingsrapporten (ook wel Ndr's genoemd of berichten die berichten versturen) naar de oorspronkelijke afzenders van het bericht.

In het gedeelte **voor** het aanvullen van e-mail van het [Dashboard voor e-mail stroom](mail-flow-insights-v2.md) in de [& beveiligings](https://protection.office.com) **Update** wordt u gewaarschuwd wanneer een e-mail in uw organisatie wordt gedetecteerd.

Dit inzicht wordt alleen weergegeven nadat de voorwaarde is vastgesteld (als u geen e-mail lussen hebt, ziet u het inzicht niet).

![Meer inzicht in langzame e-mail stroom regels op het gebied aanbevolen voor u in het dashboard voor e-mail stroom](../../media/mfi-fix-possible-mail-loop.png)

Wanneer u op Details van het object **weergeven** klikt, verschijnt er een flyout met meer informatie:

- **Domein**
- **Aantal berichten**: u kunt op **voorbeeldberichten weergeven** klikken om de resultaten van de [bericht tracering](message-trace-scc.md) te zien voor een voorbeeld van de berichten die door de lus werden beïnvloed.
- **Domeintype**, bijvoorbeeld bindend of niet-bindend.
- **MX-record**: de host (**e-mail server**) en de **prioriteits** waarden van de MX-record voor het domein.
- **Reden voor herhaling** en **oplossing**: de meest voorkomende scenario's voor mail lussen worden aangeduid met de meest voorkomende scenario's voor e-mail lussen en bieden aanbevolen acties om de lus op te lossen.

![Voorbeeld van een flyout dat wordt weergegeven nadat u op Details weergeven hebt geklikt in de mogelijke oplossing voor e-mail](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="see-also"></a>Zie ook

Zie voor meer informatie over andere inzichten in het dashboard voor e-mail stroom de [e-mail stroom inzichten in het artikel over de beveiliging & nalevings centrum](mail-flow-insights-v2.md).
