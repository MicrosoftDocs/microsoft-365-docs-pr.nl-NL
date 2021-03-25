---
title: Inzicht in uitgaande en binnenkomende e-mailstroom in het e-mailstroomdashboard
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
description: Beheerders kunnen meer informatie krijgen over het inzicht in uitgaande en binnenkomende e-mailstroom in het e-mailstroomdashboard in het beveiligings- & Compliancecentrum.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4a3117223e466a4a7aad7edf25ecdbcf0a3de719
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204135"
---
# <a name="outbound-and-inbound-mail-flow-insight-in-the-security--compliance-center"></a>Inzicht in uitgaande en binnenkomende e-mailstroom in het beveiligings- & compliancecentrum

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Het inzicht in uitgaande en **binnenkomende** e-mailstroom in het E-mailstroomdashboard in het [](mail-flow-insights-v2.md) [Beveiligings- & Compliancecentrum](https://protection.office.com) combineert de gegevens uit het [connectorrapport](view-mail-flow-reports.md#connector-report) en het voormalige **TLS-overzichtsrapport** op één plaats.

De widget bevat de TLS-versleuteling die wordt gebruikt voor de verbinding wanneer berichten van en naar uw organisatie worden bezorgd. De verbindingen die zijn tot stand gebracht met andere e-mailservices, worden versleuteld door TLS wanneer TLS door beide zijden wordt aangeboden. De widget biedt een momentopname van de laatste week van de e-mailstroom.

![Widget Uitgaande en binnenkomende e-mailstroom in het e-mailstroomdashboard in & Compliance center](../../media/mfi-outbound-and-inbound-mail-flow-report-widget.png)

De informatie in de widget is gerelateerd aan connectors en TLS-berichtbeveiliging in Microsoft 365. Zie deze onderwerpen voor meer informatie:

- [E-mailstroom configureren met behulp van verbindingslijnen](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)
- [Hoe Exchange Online TLS gebruikt om e-mailverbindingen te beveiligen](../../compliance/exchange-online-uses-tls-to-secure-email-connections.md)
- [Technische informatie over versleuteling in Microsoft 365](../../compliance/technical-reference-details-about-encryption.md)

## <a name="message-protected-in-transit-by-tls"></a>Bericht beveiligd tijdens doorvoer (met TLS)

Wanneer u op **Details weergeven** op de widget klikt, wordt in het flyout Bericht beveiligd tijdens doorvoer **(door TLS)** de TLS-beveiliging weergegeven voor berichten die uw organisatie binnenkomen en verlaten.

![Beveiligde berichten tijdens doorvoer (met TLS)-flyout die wordt weergegeven nadat u op Details weergeven hebt geklikt in de widget Uitgaande en binnenkomende e-mail](../../media/mfi-outbound-and-inbound-mail-flow-report-details.png)

Momenteel is TLS 1.2 de veiligste versie van TLS die wordt aangeboden door Microsoft 365. Vaak moet u de TLS-versleuteling kennen die wordt gebruikt voor nalevingscontroles. U hebt waarschijnlijk geen directe relatie met de meeste bron- en doel-e-mailservers (u bent niet de eigenaar van deze servers en Microsoft ook niet), dus u hebt niet veel opties om de TLS-versleuteling te verbeteren die door deze servers wordt gebruikt.

Maar u kunt [verbindingslijnen gebruiken](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) om de best beschikbare TLS-beveiliging te garanderen voor berichten die worden verzonden tussen uw e-mailservers en Microsoft 365. E-mailstroom tussen Microsoft 365 en uw eigen e-mailservers of servers die deel uitmaken van uw partners is vaak belangrijker en gevoeliger dan gewone berichten, dus u wilt extra beveiliging en waakzaamheid toepassen op die berichten.

U kunt uw eigen e-mailservers upgraden of herstellen om de TLS-versleuteling te verbeteren die wordt gebruikt, of contact op te zoeken met uw partners om hetzelfde te doen. In **het connectorrapport** worden zowel het volume van de e-mailstroom als de TLS-versleuteling weergegeven voor berichten die gebruikmaken van uw Microsoft 365-connectors.

U kunt op de **koppeling Verbindingslijnrapport** klikken om naar het [connectorrapport te gaan.](view-mail-flow-reports.md#connector-report) De volgende inzichten zijn mogelijk beschikbaar op de rapportpagina **Connector** als de bijbehorende voorwaarde is gedetecteerd:

- **Inkomende partnerconnector ziet significante TLS1.0-e-mailstroom**
- **Inkomende OnPremises-connector met significante TLS1.0-e-mailstroom**

Voor TLS 1.0-verbindingen moet u uw e-mailserver of de server van uw partner echt upgraden of oplossen om problemen te voorkomen wanneer TLS 1.0-ondersteuning uiteindelijk wordt afgeschaft in Microsoft 365.

## <a name="see-also"></a>Zie ook

Zie E-mailstroominzichten in het Beveiligings- & compliancecentrum voor meer informatie over andere inzichten [in het e-mailstroomdashboard.](mail-flow-insights-v2.md)