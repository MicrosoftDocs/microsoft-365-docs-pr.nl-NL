---
title: Inzicht in regels voor langzame e-mailstroom oplossen
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: 37125cdb-715d-42d0-b669-1a8efa140813
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen in het beveiligings- &-compliancecentrum weten hoe ze niet-efficiënt of niet-efficiënt werkende regels voor de e-mailstroom (ook wel transportregels genoemd) in hun organisatie kunnen vaststellen en oplossen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f7f084735decda922b5bcc57c029f2b384114d30
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150782"
---
# <a name="fix-slow-mail-flow-rules-insight-in-the-security--compliance-center"></a>Inzicht in regels voor trage e-mailstroom oplossen in het & compliancecentrum

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender voor Office 365-abonnement 1 en abonnement 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Niet-efficiënt e-mailstroomregels (ook wel transportregels genoemd) kunnen leiden tot vertragingen in de e-mailstroom voor uw organisatie. Dit inzicht rapporteert regels voor de e-mailstroom die van invloed zijn op de e-mailstroom van uw organisatie. Voorbeelden van deze soorten regels zijn:

- Voorwaarden die gebruikmaken **van Is lid van** grote groepen.
- Voorwaarden die gebruikmaken van complexe reguliere expressiepatronen (regex).
- Voorwaarden die gebruikmaken van het controleren van inhoud in bijlagen.

Informatie over regels voor trage  **e-mailstroom** oplossen in het gebied Aanbevolen voor u in het [dashboard](mail-flow-insights-v2.md) E-mailstroom in het [beveiligings- & Compliancecentrum](https://protection.office.com) laat u weten wanneer het te lang duurt voordat een e-mailstroomregel is voltooid.

Dit inzicht wordt pas weergegeven nadat de voorwaarde is gedetecteerd (als u geen e-maillussen hebt, ziet u het inzicht niet).

U kunt deze melding gebruiken om regels voor de e-mailstroom te identificeren en aan te passen om de vertraging van de e-mailstroom te beperken.

![Inzicht in regels voor langzame e-mailstroom oplossen in het gebied Aanbevolen voor u in het dashboard E-mailstroom](../../media/mfi-fix-slow-mail-flow-rules.png)

Wanneer u op **Details weergeven** in de widget klikt, verschijnt er een flyout met meer informatie:

- **Regel:** u kunt de muisaanwijzer op het overzicht houden om alle voorwaarden, uitzonderingen en acties van de regel te bekijken. U kunt op de samenvatting klikken om de regel te bewerken in het Exchange-beheercentrum (EAC).
- **Aantal geëvalueerde** berichten:  U kunt op [](message-trace-scc.md) Voorbeeldberichten weergeven klikken om de resultaten van bericht traceren te bekijken voor een voorbeeld van de berichten die door de regel zijn beïnvloed.
- **Gemiddelde tijd besteed aan elk bericht**
- **Mediaantijd besteed aan een bericht:** de middelste waarde die de bovenste helft scheidt van de onderste helft van de tijdgegevens.

![Flyout details die wordt weergegeven nadat u op Details weergeven hebt geklikt op het inzicht in regels voor vertraagde e-mailstroom herstellen](../../media/mfi-fix-slow-mail-flow-rules-details.png)

Zie voorwaarden en uitzonderingen voor e-mailstroomregels en uitzonderingen (predicaten) in Exchange Online voor meer informatie over voorwaarden en [uitzonderingen in regels voor de e-mailstroom.](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

## <a name="see-also"></a>Zie ook

Zie inzichten in de e-mailstroom in het beveiligings- en compliancecentrum voor meer informatie & [inzichten in het dashboard E-mailstroom.](mail-flow-insights-v2.md)
