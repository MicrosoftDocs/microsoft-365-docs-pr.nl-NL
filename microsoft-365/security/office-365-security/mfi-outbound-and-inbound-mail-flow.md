---
title: Uitgaand en binnenkomende e-mail stroom inzichtelijk in het dashboard voor e-mail stroom
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: f2738dec-41b0-43c4-b814-84c0a4e45c6d
description: Beheerders kunnen inzicht krijgen in de uitgaand en binnenkomende e-mail stroom informatie in het dashboard voor e-mail stroom in de beveiligings & nalevings centrum.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e46a0ebf0c14e31462d1e86d8a8d8c08486337af
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029820"
---
# <a name="outbound-and-inbound-mail-flow-insight-in-the-security--compliance-center"></a>Uitgaand en binnenkomende e-mail stroom inzicht in de beveiligings & nalevings centrum

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


De **uitgaande en binnenkomende e-mail stroom** informatie in het [Dashboard voor e-mail stroom](mail-flow-insights-v2.md) in de [beveiligings & nalevings centrum](https://protection.office.com) combineert de informatie uit het [verbindings rapport](view-mail-flow-reports.md#connector-report) en het voormalige **TLS-overzichtsrapport** op één plaats.

Het object geeft de TLS-versleuteling weer die wordt gebruikt voor de verbinding wanneer berichten worden bezorgd en van uw organisatie. De verbindingen die zijn gemaakt met andere e-mailservices, worden versleuteld door TLS wanneer TLS aan beide kanten wordt aangeboden. De widget biedt een momentopname van de laatste week van de e-mail stroom.

![Uitgaande en binnenkomende e-mail stroom widget in het dashboard voor e-mail stroom in het Beveiligingscentrum beveiligings &](../../media/mfi-outbound-and-inbound-mail-flow-report-widget.png)

De gegevens in de widget hebben betrekking op connectors en TLS-berichtbeveiliging in Microsoft 365. Zie de volgende onderwerpen voor meer informatie:

- [De e-mail stroom configureren met connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)
- [Hoe Exchange Online TLS gebruikt om verbinding te maken met e-mail verbindingen](https://docs.microsoft.com/microsoft-365/compliance/exchange-online-uses-tls-to-secure-email-connections)
- [Technische naslaginformatie over versleuteling in Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/technical-reference-details-about-encryption)

## <a name="message-protected-in-transit-by-tls"></a>Bericht beveiligd in transit (via TLS)

Wanneer u klikt op **Details weergeven** in de widget, ziet u in het bericht met de **tekst in het bericht in transit (per TLS)** de TLS-beveiliging voor berichten die uw organisatie binnenkomen en verlaten.

![Berichten die zijn beveiligd in de Transit (door TLS) flyout, die worden weergegeven nadat u op Details weergeven hebt geklikt in de widget uitgaande en binnenkomende e-mail](../../media/mfi-outbound-and-inbound-mail-flow-report-details.png)

Op dit moment TLS 1,2 is de veiligste versie van TLS die wordt aangeboden door Microsoft 365. Vaak moet u weten wat de TLS-codering is die wordt gebruikt voor nalevingscontroles. U hebt waarschijnlijk geen rechtstreekse relatie met de meeste bron-en doel-e-mailservers (u bezit ze niet, en hebt geen Microsoft), dus hebt u niet veel opties om de TLS-versleuteling te verbeteren die door die servers wordt gebruikt.

U kunt echter ook gebruikmaken van [connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) om te zorgen dat u de beste beschikbare TLS-beveiliging voor berichten die zijn verzonden tussen uw e-mailservers en microsoft 365. De e-mail stroom tussen Microsoft 365 en uw eigen e-mailservers of servers die deel uitmaken van uw partners, is vaak belangrijker en gevoeliger dan gewone berichten, dus wilt u extra beveiliging en waakzaamheid op deze berichten toepassen.

U kunt een upgrade uitvoeren naar uw eigen e-mailservers of deze oplossing voor het verbeteren van de gebruikte TLS-versleuteling of contact opnemen met uw partners. In het **rapport connector** ziet u het e-mail stroom volume en de TLS-versleuteling voor berichten die gebruikmaken van uw microsoft 365-connectors.

U kunt klikken op de koppeling van het **verbindingslijn** om naar het [verbindings rapport](view-mail-flow-reports.md#connector-report)te gaan. Mogelijk zijn de volgende inzichten beschikbaar op de pagina van het **connector rapport** als de bijbehorende voorwaarde is gedetecteerd:

- **Binnenkomende partner connector met significante TLS 1.0-e-mail stroom**
- **Binnenkomende OnPremises-connector met significante TLS 1.0-e-mail stroom**

Voor TLS 1,0-verbindingen moet u eerst uw e-mailserver of de server van uw partner of een upgrade naar de server of een oplossing voorkomen, zodat er geen problemen worden weergegeven wanneer TLS 1,0 voor ondersteuning in Microsoft 365 uiteindelijk is afgeschaft.

## <a name="see-also"></a>Zie ook

Zie voor meer informatie over andere inzichten in het dashboard voor e-mail stroom de [e-mail stroom inzichten in het artikel over de beveiliging & nalevings centrum](mail-flow-insights-v2.md).
