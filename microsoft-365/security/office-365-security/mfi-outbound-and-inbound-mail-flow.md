---
title: Uitgaande en binnenkomende e-mailstroom
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
description: Beheerders kunnen meer te weten komen over de widget Uitgaande en binnenkomende e-mailstroom in het dashboard van de e-mailstroom in het Beveiligings- & Compliance Center.
ms.openlocfilehash: a1070783f60edf2de62d78c3094e9c20e3dd26f3
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635194"
---
# <a name="outbound-and-inbound-mail-flow"></a>Uitgaande en binnenkomende e-mailstroom

De **widget Uitgaande en binnenkomende e-mailstroom** combineert de informatie uit het **connectorrapport** en het voormalige **TLS-overzichtsrapport op** één plaats.

![Het rapport Uitgaande en binnenkomende e-mailstroom in het dashboard van de e-mailstroom in het Beveiligings& Compliance Center](../../media/2c591d1c-bad6-4b72-890e-f8fdfd4f447a.png)

De informatie in de widget is gerelateerd aan connectors en TLS-berichtbeveiliging in Office 365. Zie voor meer informatie de volgende onderwerpen:

- [E-mailstroom configureren met connectors in Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)

- [Hoe Exchange Online TLS gebruikt om e-mailverbindingen in Office 365 te beveiligen](https://docs.microsoft.com/microsoft-365/compliance/exchange-online-uses-tls-to-secure-email-connections)

## <a name="message-protected-in-transit-by-tls"></a>Bericht beveiligd tijdens het transport (door TLS)

Met de widget **Uitgaande en binnenkomende e-mailstroom** wordt de TLS-versleuteling weergegeven die wordt gebruikt voor de verbinding wanneer berichten van en naar uw organisatie worden bezorgd. De verbindingen die worden gemaakt met andere e-mailservices worden versleuteld door TLS wanneer TLS door beide partijen wordt aangeboden. De widget biedt een momentopname van de laatste week van de e-mailstroom. Wanneer u op **Details weergeven**klikt, ziet de flyout **Van Message protected in transit (by TLS)** de TLS-bescherming voor berichten die uw organisatie invoeren en verlaten.

![De flyout Berichten beveiligd tijdens het transport (door TLS) in het Security & Compliance Center](../../media/825aa74c-413d-4141-8e3c-dfe68ae78eed.png)

Momenteel is TLS 1.2 de veiligste versie van TLS die wordt aangeboden door Office 365. Vaak moet u de TLS-versleuteling kennen die wordt gebruikt voor nalevingsaudits. U hebt waarschijnlijk geen directe relatie met de meeste e-mailservers voor bron en bestemming (u bent niet de eigenaar, en Microsoft ook niet), dus u hebt niet veel opties om de TLS-versleuteling te verbeteren die door die servers wordt gebruikt.

U echter [wel connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) gebruiken om de best beschikbare TLS-bescherming te garanderen voor berichten die worden verzonden tussen uw e-mailservers en Office 365. De e-mailstroom tussen Microsoft 365 en uw eigen e-mailservers of servers die eigendom zijn van uw partners is vaak belangrijker en gevoeliger dan gewone berichten, dus u wilt extra beveiliging en waakzaamheid toepassen op die berichten. U uw eigen e-mailservers upgraden of repareren om de TLS-versleuteling die wordt gebruikt te verbeteren, of contact opnemen met uw partners om hetzelfde te doen. In **het connectorrapport** worden zowel het volume van de e-mailstroom als de TLS-versleuteling weergegeven voor berichten die uw Microsoft 365-connectors gebruiken.

## <a name="connector-report"></a>Connectorrapport

Wanneer u op de koppeling **Connectorrapport** klikt vanuit de flyout **Message protected in transit (by TLS),** wordt in het rapport informatie weergegeven over berichten die van en naar uw organisatie worden geleverd met behulp van connectors. U gebruikt connectoren tussen uw eigen e-mailservers en Microsoft 365 of de servers van uw partner en Office 365. Het berichtvolume voor elke connector en de TLS-versleuteling voor de verbinding is beschikbaar. Bovendien u ook gegevens weergeven voor berichten die zijn verzonden of ontvangen in Microsoft 365 zonder een connector te gebruiken.

In de weergave **E-mailstroom** wordt het volume van de berichten via de connector van de afgelopen week weergegeven. U het datumbereik wijzigen door **Filter** te selecteren waar u het bereik verhogen tot maximaal 30 dagen. In de weergave **Alle e-mailstroom** wordt alle e-mailstroom van en naar uw organisatie weergegeven via alle connectoren. U een specifieke connector op naam selecteren in het vervolgkeuzemenu.

U de **TLS-gebruiksweergave** selecteren in de vervolgkeuzelijst om de uitsplitsing van TLS-beveiliging voor berichten via de connector te bekijken. Net als in het **rapport-TLS-overzichtsrapport** wordt in deze weergave het percentage van de verschillende TLS-versies weergegeven. Voor TLS 1.0-verbindingen moet u uw e-mailserver of de server van uw partner echt upgraden of repareren om problemen te voorkomen wanneer TLS 1.0-ondersteuning uiteindelijk wordt afgeschaft in Office 365. Zie [Technische naslaggegevens over versleuteling in Office 365](https://docs.microsoft.com/microsoft-365/compliance/technical-reference-details-about-encryption)voor meer informatie.

Inzichten wijzen op connectors om uw aandacht te vestigen op mogelijke TLS-versleutelingsproblemen voor de connector. De inzichten zijn: **Geen TLS is meer dan 25%** of TLS **1.0 is boven de 50%.** Als u deze inzichten ziet, moet u uw e-mailservers onderzoeken die aan de connector zijn gekoppeld of contact opnemen met uw partnerorganisatie.

## <a name="see-also"></a>Zie ook

Zie Inzicht in [e-mailstroom in het Security & Compliance Center](mail-flow-insights-v2.md)voor meer informatie over andere e-mailstroominzichten in het dashboard voor e-mailstromen.
