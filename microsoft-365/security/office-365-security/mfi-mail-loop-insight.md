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
ms.openlocfilehash: 7fde0041dfb9901cb0a327eafec78d98a40b4cb9
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290559"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a>Inzicht in mogelijke e-maillus herstellen in het & compliancecentrum

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

E-maillussen zijn slecht omdat:

- Ze verspillen systeembronnen.
- Ze verbruiken het volumequotum voor e-mail van uw organisatie.
- Ze verzenden verwarrende rapporten over niet-bezorging (ook wel NDR's of niet-bezorgdberichten genoemd) naar de oorspronkelijke afzenders van het bericht.

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

Zie inzichten in de e-mailstroom in het beveiligings- en compliancecentrum voor meer informatie & [inzichten in het dashboard E-mailstroom.](mail-flow-insights-v2.md)
