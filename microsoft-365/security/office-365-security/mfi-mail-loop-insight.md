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
description: Beheerders kunnen in het dashboard E-mailstroom in het beveiligings- & Compliancecentrum leren hoe ze het inzicht in mogelijke e-mailluss in het dashboard E-maillus herstellen kunnen gebruiken om e-maillussen in hun organisatie te identificeren en te herstellen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3c9607f053fb5011b8c8af3c8bb2073a9d022909
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150229"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a>Inzicht in mogelijke e-maillus herstellen in het & compliancecentrum

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender voor Office 365-abonnement 1 en abonnement 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

E-maillussen zijn slecht omdat:

- Ze verspillen systeembronnen.
- Ze verbruiken het volumequotum voor e-mail van uw organisatie.
- Ze verzenden verwarrende rapporten over niet-bezorging (ook wel NR's of niet-bezorgdberichten genoemd) naar de oorspronkelijke afzenders van het bericht.

Het inzicht in mogelijke  **e-mailluss** in het gebied Aanbevolen voor u in het [dashboard](mail-flow-insights-v2.md) E-mailstroom in het [beveiligings- & Compliancecentrum](https://protection.office.com) wordt u op de hoogte stellen wanneer een e-maillus wordt gedetecteerd in uw organisatie.

Dit inzicht wordt pas weergegeven nadat de voorwaarde is gedetecteerd (als u geen e-maillussen hebt, ziet u het inzicht niet).

![Inzicht in regels voor trage e-mailstroom oplossen in het gebied Aanbevolen voor u in het dashboard E-mailstroom](../../media/mfi-fix-possible-mail-loop.png)

Wanneer u op **Details weergeven** in de widget klikt, verschijnt er een flyout met meer informatie:

- **Domein**
- **Aantal berichten:** u kunt op [](message-trace-scc.md) **Voorbeeldberichten** weergeven klikken om de resultaten van bericht traceren te bekijken voor een voorbeeld van de berichten die door de lus zijn beïnvloed.
- **Domeintype"** Bijvoorbeeld Gezaghebbend of Niet-gezaghebbend.
- **MX-record:** De host **(Mail Server)** en **prioriteitswaarden** van de MX-record voor het domein.
- **Loop reason** and **How to fix:** We'll identify the most common mail loop scenarios and provide recommended actions to fix the loop.

![Flyout details die wordt weergegeven nadat u op Details weergeven hebt geklikt op het inzicht in Mogelijke e-maillus herstellen](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="see-also"></a>Zie ook

Voor informatie over andere inzichten in het dashboard voor de e-mailstroom, bekijkt u inzichten in de e-mailstroom in het & [compliancecentrum.](mail-flow-insights-v2.md)
