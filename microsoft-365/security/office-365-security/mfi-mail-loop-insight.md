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
description: Beheerders kunnen leren hoe ze het inzicht in mogelijke e-maillus oplossen in het e-mailstroomdashboard in het Beveiligings- & Compliancecentrum kunnen gebruiken om e-mailluss in hun organisatie te identificeren en op te lossen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8bb08eb2f9a5ea0eb72433f92b6d28175edc75b8
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204559"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a>Mogelijk inzicht in e-maillus oplossen in het beveiligings- & compliancecentrum

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

E-mailluss zijn slecht omdat:

- Ze verspillen systeembronnen.
- Ze gebruiken het e-mailvolumequotum van uw organisatie.
- Ze verzenden verwarrende rapporten over niet-bezorging (ook wel NR's of niet-bezorgde berichten genoemd) naar de oorspronkelijke afzenders van het bericht.

Het inzicht in mogelijke  **e-maillus** oplossen in het gebied Aanbevolen voor u van het e-mailstroomdashboard in het [beveiligings- & compliancecentrum](https://protection.office.com) meldt u wanneer er een e-maillus wordt gedetecteerd in uw organisatie. [](mail-flow-insights-v2.md)

Dit inzicht wordt alleen weergegeven nadat de voorwaarde is gedetecteerd (als u geen e-mailluss hebt, ziet u het inzicht niet).

![Inzicht in regels voor trage e-mailstroom oplossen in het gebied Aanbevolen voor u van het e-mailstroomdashboard](../../media/mfi-fix-possible-mail-loop.png)

Wanneer u op **Details weergeven** op de widget klikt, wordt er een flyout weergegeven met meer informatie:

- **Domein**
- **Aantal berichten:** U kunt op [](message-trace-scc.md) **Voorbeeldberichten weergeven** klikken om de resultaten van bericht trace te bekijken voor een voorbeeld van de berichten die door de lus zijn beïnvloed.
- **Domeintype**" Bijvoorbeeld Gezaghebbend of Niet-gezaghebbend.
- **MX-record:** De host **(Mail server)** en **Prioriteitswaarden** van de MX-record voor het domein.
- **Reden voor lus** **en Oplossing:** We identificeren de meest voorkomende scenario's voor e-maillus en bieden aanbevolen acties om de lus op te lossen.

![Details flyout that appears after clicking View details on the Fix possible mail loop insight](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="see-also"></a>Zie ook

Zie E-mailstroominzichten in het Beveiligings- & compliancecentrum voor meer informatie over andere inzichten [in het e-mailstroomdashboard.](mail-flow-insights-v2.md)
