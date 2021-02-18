---
title: Inzichten in de uitgaande en binnenkomende e-mailstroom in het dashboard E-mailstroom
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
description: Beheerders kunnen meer informatie krijgen over het inzicht in de stroom voor uitgaande en binnenkomende e-mail in het dashboard E-mailstroom in het & compliancecentrum.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 87c5bd9ab0d550f50feabbb96176debbe04863e5
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289447"
---
# <a name="outbound-and-inbound-mail-flow-insight-in-the-security--compliance-center"></a>Inzichten in de uitgaande en binnenkomende e-mailstroom in het & compliancecentrum

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Het inzicht in de uitgaande en **binnenkomende e-mailstroom** in het [dashboard](mail-flow-insights-v2.md) E-mailstroom in het [beveiligings- & Compliancecentrum](https://protection.office.com) combineert de informatie uit het [rapport Connector](view-mail-flow-reports.md#connector-report) en het voormalige overzichtsrapport **TLS** op één plaats.

In de widget wordt de TLS-versleuteling weergegeven die wordt gebruikt voor de verbinding wanneer berichten worden bezorgd bij en van uw organisatie. De verbindingen die tot stand worden gebracht met andere e-mailservices worden versleuteld door TLS wanneer TLS aan beide zijden wordt aangeboden. De widget bevat een momentopname van de laatste week van de e-mailstroom.

![Widget Voor uitgaande en binnenkomende e-mailstroom in het dashboard E-mailstroom in het & compliancecentrum](../../media/mfi-outbound-and-inbound-mail-flow-report-widget.png)

De informatie in de widget heeft betrekking op connectors en TLS-berichtbeveiliging in Microsoft 365. Zie de volgende onderwerpen voor meer informatie:

- [E-mailstroom configureren met connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)
- [Exchange Online gebruikt TLS om e-mailverbindingen te beveiligen](../../compliance/exchange-online-uses-tls-to-secure-email-connections.md)
- [Technische naslaginformatie over versleuteling in Microsoft 365](../../compliance/technical-reference-details-about-encryption.md)

## <a name="message-protected-in-transit-by-tls"></a>Bericht wordt tijdens overdracht beveiligd (door TLS)

Wanneer u op **Details weergeven** in de widget klikt, wordt in de flyout Bericht beveiligd tijdens **overdracht (met TLS) TLS-beveiliging** weergegeven voor berichten die worden weergegeven voor berichten die worden weergegeven bij het invoeren en verlaten van uw organisatie.

![Flyout Berichten die tijdens het verzenden zijn beveiligd (met TLS) wordt weergegeven nadat u op Details weergeven hebt geklikt in de widget Uitgaande en binnenkomende e-mail](../../media/mfi-outbound-and-inbound-mail-flow-report-details.png)

Op dit moment is TLS 1.2 de veiligste versie van TLS die wordt aangeboden door Microsoft 365. Vaak moet u de TLS-versleuteling kennen die wordt gebruikt voor nalevingscontroles. U hebt waarschijnlijk geen directe relatie met de meeste bron- en doel-e-mailservers (u bent niet de eigenaar en Microsoft ook niet). U hebt dus niet veel opties om de TLS-versleuteling te verbeteren die door deze servers wordt gebruikt.

Maar u kunt [connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) gebruiken om ervoor te zorgen dat berichten die tussen uw e-mailservers en Microsoft 365 worden verzonden, de beste TLS-beveiliging bieden. De e-mailstroom tussen Microsoft 365 en uw eigen e-mailservers of -servers die tot uw partners behoren, is vaak belangrijker en gevoeliger dan normale berichten, dus u zult extra beveiliging en beveiliging op deze berichten willen toepassen.

U kunt uw eigen e-mailservers upgraden of herstellen om de TLS-versleuteling te verbeteren die wordt gebruikt, of contact op met uw partners om hetzelfde te doen. In **het connectorrapport** worden zowel het volume van de e-mailstroom als de TLS-versleuteling weergegeven voor berichten die uw Microsoft 365-connectors gebruiken.

U kunt klikken op de **koppeling Connectorrapport** om naar het [rapport Connector te gaan.](view-mail-flow-reports.md#connector-report) De volgende inzichten zijn mogelijk beschikbaar op de rapportpagina **connector** als de bijbehorende voorwaarde is gedetecteerd:

- **Binnenkomende partnerconnector ziet belangrijke TLS1.0-e-mailstroom**
- **Binnenkomende OnPremises-connector ziet belangrijke TLS1.0-e-mailstroom**

Voor TLS 1.0-verbindingen moet u de e-mailserver of de server van uw partner upgraden of oplossen om problemen te voorkomen wanneer de ondersteuning voor TLS 1.0 uiteindelijk wordt afgeschaft in Microsoft 365.

## <a name="see-also"></a>Zie ook

Voor informatie over andere inzichten in het dashboard voor de e-mailstroom, bekijkt u inzichten in de e-mailstroom in het & [compliancecentrum.](mail-flow-insights-v2.md)
