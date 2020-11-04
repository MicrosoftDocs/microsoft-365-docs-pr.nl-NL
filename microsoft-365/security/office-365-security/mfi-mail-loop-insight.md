---
title: Inzicht in mogelijke e-maillus oplossen
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: cb801985-3c89-4979-9c18-17829a4cb563
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen leren hoe u met behulp & van het hulpprogramma voor het oplossen van e-mail lussen in hun organisatie e-mail lussen kunt identificeren en oplossen.
ms.openlocfilehash: 15ad5c467d18ce3038bcb05db798a9b5a7c3e391
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877501"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a>Mogelijke oplossing voor e-mail lussen in de beveiligings & nalevings centrum

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Een lus voor e-mailberichten is slecht omdat dit de systeembronnen verspilt, het volume quotum van uw organisatie gebruikt en geen rapporten van niet-uitgevoerde bezorging (ook wel Ndr's genoemd) aan de oorspronkelijke afzenders stuurt.

In het gedeelte **voor** het aanvullen van e-mail van het [Dashboard voor e-mail stroom](mail-flow-insights-v2.md) in de [& beveiligings](https://protection.office.com) **Update** wordt u gewaarschuwd wanneer een e-mail in uw organisatie wordt gedetecteerd. Dit inzicht wordt alleen weergegeven nadat de voorwaarde is vastgesteld (als u geen e-mail lussen hebt, ziet u het inzicht niet).

![Meer inzicht in langzame e-mail stroom regels op het gebied aanbevolen voor u in het dashboard voor e-mail stroom](../../media/mfi-fix-possible-mail-loop.png)

Wanneer u op Details van het object **weergeven** klikt, verschijnt er een flyout met meer informatie:

- **Domein**
- **Aantal berichten** : u kunt op **voorbeeldberichten weergeven** klikken om de resultaten van de [bericht tracering](message-trace-scc.md) te zien voor een voorbeeld van de berichten die door de lus werden beïnvloed.
- **Domeintype** , bijvoorbeeld bindend of niet-bindend.
- **MX-record** : de host ( **e-mail server** ) en de **prioriteits** waarden van de MX-record voor het domein.
- **Reden voor herhaling** en **oplossing** : we proberen de meest voorkomende scenario's voor e-mail lussen te identificeren en de aanbevolen acties te geven (indien beschikbaar) om de lus te verhelpen.

![Voorbeeld van een flyout dat wordt weergegeven nadat u op Details weergeven hebt geklikt in de mogelijke oplossing voor e-mail](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="related-topics"></a>Verwante onderwerpen

Zie voor meer informatie over andere inzichten in het dashboard voor e-mail stroom de [e-mail stroom inzichten in het artikel over de beveiliging & nalevings centrum](mail-flow-insights-v2.md).
