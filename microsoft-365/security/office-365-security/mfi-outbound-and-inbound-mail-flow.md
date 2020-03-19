---
title: Uitgaande en inkomende e-mailstroom
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 8/7/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f2738dec-41b0-43c4-b814-84c0a4e45c6d
description: Beheerders kunnen meer te weten komen over de widget Uitgaande en inkomende e-mailstroom in het dashboard voor e-mailstroom in het Security & Compliance Center.
ms.openlocfilehash: 5c86db8e33ff3ee1dc4d9d126239465b3c84bde5
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42805907"
---
# <a name="outbound-and-inbound-mail-flow"></a>Uitgaande en inkomende e-mailstroom

De **widget Uitgaande en inkomende e-mailstroom** combineert de informatie uit het **Connector-rapport** en het voormalige **TLS-overzichtsrapport** op één plaats.

![Het rapport Uitgaande en binnenkomende e-mailstroom in het dashboard voor e-mailstroom in het Security & Compliance Center](../../media/2c591d1c-bad6-4b72-890e-f8fdfd4f447a.png)

De informatie in de widget is gerelateerd aan connectors en TLS-berichtbeveiliging in Office 365. Zie voor meer informatie de volgende onderwerpen:

- [E-mailstroom configureren met connectors in Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)

- [Hoe Exchange Online TLS gebruikt om e-mailverbindingen in Office 365 te beveiligen](https://docs.microsoft.com/microsoft-365/compliance/exchange-online-uses-tls-to-secure-email-connections)

## <a name="message-protected-in-transit-by-tls"></a>Bericht dat tijdens doorvoer is beveiligd (door TLS)

In de widget **Uitgaande en binnenkomende e-mailstroom** wordt de TLS-versleuteling weergegeven die wordt gebruikt voor de verbinding wanneer berichten van en naar uw Office 365-organisatie worden bezorgd. De verbindingen die zijn gemaakt met andere e-mailservices worden versleuteld door TLS wanneer TLS door beide partijen wordt aangeboden. De widget biedt een momentopname van de laatste week van de mailflow. Wanneer u op **Details weergeven**klikt, toont de flyout van het **bericht dat tijdens de doorvoer (door TLS) is beveiligd,** de TLS-beveiliging voor berichten die uw organisatie binnenkomen en verlaten.

![De berichten die tijdens het transport (door TLS) worden beveiligd in het Security & Compliance Center](../../media/825aa74c-413d-4141-8e3c-dfe68ae78eed.png)

Momenteel is TLS 1.2 de veiligste versie van TLS die wordt aangeboden door Office 365. Vaak moet u de TLS-versleuteling kennen die wordt gebruikt voor nalevingsaudits. U hebt waarschijnlijk geen directe relatie met de meeste bron- en doele-mailservers (u bent niet de eigenaar van deze servers en Microsoft ook niet), zodat u niet veel opties hebt om de TLS-versleuteling te verbeteren die door die servers wordt gebruikt.

U echter [connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) gebruiken om de beste beschikbare TLS-beveiliging te garanderen voor berichten die tussen uw e-mailservers en Office 365 worden verzonden. De e-mailstroom tussen Office 365 en uw eigen e-mailservers of servers die tot uw partners behoren, is vaak belangrijker en gevoeliger dan gewone berichten, dus u wilt extra beveiliging en waakzaamheid toepassen op die berichten. U uw eigen e-mailservers upgraden of repareren om de TLS-versleuteling die wordt gebruikt te verbeteren, of contact opnemen met uw partners om hetzelfde te doen. **In het verbindingsrapport** worden zowel het volume van de e-mailstroom als tls-versleuteling weergegeven voor berichten die uw Office 365-connectors gebruiken.

## <a name="connector-report"></a>Verbindingsrapport

Wanneer u op de koppeling **Connectorrapport** klikt vanuit de flyout **Message protected in transit (by TLS),** worden in het rapport informatie weergegeven over berichten die met connectors van en naar uw Office 365-organisatie worden bezorgd. U gebruikt connectors tussen uw eigen e-mailservers en Office 365 of de servers van uw partner en Office 365. Het berichtvolume voor elke connector en de TLS-versleuteling voor de verbinding is beschikbaar. Daarnaast u ook gegevens bekijken voor berichten die zijn verzonden of ontvangen in Office 365 zonder een connector te gebruiken.

In de **weergave Mailflow** wordt het aantal berichten weergegeven via de connector van de afgelopen week. U het datumbereik wijzigen door **Filter** te selecteren waar u het bereik verhogen tot maximaal 30 dagen. In de weergave **All Mail Flow** worden alle e-mailstroom van en naar uw Office 365-organisatie weergegeven via alle connectoren. U een specifieke connector op naam selecteren in het vervolgkeuzemenu.

U de **TLS-gebruiksweergave** selecteren in de vervolgkeuzelijst naar beneden om de uitsplitsing van TLS-beveiliging voor berichten via de connector te bekijken. Net als bij het **TLS-overzichtsrapport** toont deze weergave het percentage van de verschillende TLS-versies. Voor TLS 1.0-verbindingen moet u echt uw e-mailserver of de server van uw partner upgraden of repareren om problemen te voorkomen wanneer TLS 1.0-ondersteuning uiteindelijk wordt afgeschaft in Office 365. Zie [Technische referentiegegevens over versleuteling in Office 365](https://docs.microsoft.com/microsoft-365/compliance/technical-reference-details-about-encryption)voor meer informatie.

Inzichten wijzen op connectors om uw aandacht te vestigen op mogelijke TLS-versleutelingsproblemen voor de connector. De inzichten zijn: **Geen TLS is meer dan 25%** of TLS **1.0 is boven de 50%.** Als u deze inzichten ziet, moet u uw e-mailservers onderzoeken die aan de connector zijn gekoppeld of contact opnemen met uw partnerorganisatie.

## <a name="see-also"></a>Zie ook

Zie Inzichten in de [stroomstromen in het Security & Compliance Center](mail-flow-insights-v2.md)voor meer informatie over andere e-mailstroom-inzichten in het dashboard voor e-mailstroom.
