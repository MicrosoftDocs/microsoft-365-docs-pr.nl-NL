---
title: Wachtrijwaarschuwingen en wachtrijen
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37640c80-ce6f-47e2-afd1-bc1d3c50e637
description: Beheerders kunnen meer te weten komen over wachtrijwaarschuwingen en wachtrijen in het dashboard van de e-mailstroom in het Beveiligings- & Compliance Center.
ms.openlocfilehash: 7bb103bad89ee39991a5c16d7101ab4658842479
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635182"
---
# <a name="queue-alerts-and-queues"></a>Wachtrijwaarschuwingen en wachtrijen

## <a name="queue-alerts"></a>Wachtrijwaarschuwingen

Wanneer berichten niet kunnen worden verzonden van uw organisatie naar uw on-premises of partnere-mailservers met behulp van connectors, worden de berichten in de wachtrij geplaatst in Office 365. Veelvoorkomende voorbeelden die deze aandoening veroorzaken zijn:

- De connector is onjuist geconfigureerd.

- Er zijn netwerk- of firewallwijzigingen geweest in uw on-premises omgeving.

Microsoft 365 blijft 24 uur opnieuw leveren. Na 24 uur verlopen de berichten en worden ze teruggestuurd naar de afzenders in niet-leveringsrapporten (ook wel NDR's of bounceberichten genoemd).

Als het e-mailvolume in de wachtrij de vooraf gedefinieerde drempelwaarde overschrijdt (de standaardwaarde is 2000 berichten), zijn de waarschuwingen beschikbaar in het dashboard van de e-mailstroom bij **Recente waarschuwingen**en ontvangen beheerders een e-mailmelding (naar hun alternatieve e-mailadres). Zie de sectie **Wachtrijwaarschuwingen aanpassen** als u de waarschuwingsdrempel, de dagelijkse meldingslimiet en/of ontvangers van de waarschuwing wilt configureren.

![Wachtrijwaarschuwingen in het gebied Recente waarschuwingen van het dashboard met e-mailstroom in het beveiligingscentrum & Compliance Center](../../media/5fc4a51c-6118-4270-960b-c6b176ef94ae.png)

## <a name="customize-queue-alerts"></a>Wachtrijwaarschuwingen aanpassen

E-mailstroominzichten maken een waarschuwingsbeleid met de naam **Berichten zijn vertraagd** (het selectievakje **E-mailmeldingen verzenden** in het onderstaande voorbeeldschermafbeelding) in **waarschuwingswaarschuwingsbeleid** **Alerts** \> . U de drempelwaarde wijzigen en geadresseerden waarschuwen door op het beleid te klikken.

![Navigatie waarschuwingen](../../media/efb95976-9e0b-484e-a2fd-093c5bc7a40f.png)

U ziet een nieuw beleidsinformatieblad, u nu op **Beleid bewerken**klikken.

![Beleid bewerken](../../media/ed2aceae-3ee2-4849-a17e-87915987a7dd.png)

Het informatieblad wordt gewijzigd in het **bewerkingsbeleid**. U nu de geadresseerden voor de waarschuwingse-mail, de limiet voor het aantal meldingen per dag en de minimale drempelwaarde om de waarschuwing te activeren (200 of meer) wijzigen.

![Beleidsblad bewerken](../../media/c657cc74-7867-474c-b2c9-dc478449f990.png)

## <a name="queue-alert-details"></a>Details van wachtrijwaarschuwingen

Wanneer u op de waarschuwing klikt, worden de waarschuwingsgegevens weergegeven in een flyout-deelvenster.

![Selecteer een wachtrijwaarschuwing in het gebied Recente waarschuwingen van het dashboard van de e-mailstroom in het beveiligingscentrum & Compliance Center](../../media/1f6b0e96-5b2c-41ef-9684-9d813b3fabe6.png)

![De wachtrijwaarschuwing Details flyout in het Security & Compliance Center](../../media/105c8fff-912f-4763-8806-2740ebdecd4b.png)

U op **Wachtrij weergeven** in de waarschuwingsgegevens klikken om de wachtrijgegevens, problemen en koppelingen naar de beschikbare oplossingen in een nieuw flyoutvenster te bekijken.

![De wachtrijwaarschuwing Details flyout in het Security & Compliance Center](../../media/8ff60955-55ef-4f32-a966-85e02cb608d1.png)

![Wachtrij weergeven in de waarschuwingsgegevens](../../media/4eb088fe-5dd9-4bf4-b959-c1bb2545c515.png)

## <a name="queues"></a>Wachtrijen

Zelfs als het aantal berichten in de wachtrij de drempelwaarde niet heeft overschreden, u nog steeds het **wachtrijgebied** van het dashboard van de e-mailstroom gebruiken om berichten te zien die langer dan een uur in de wachtrij staan. U het gebied **Wachtrijen** gebruiken om het aantal in de wachtrij staande berichten te controleren (de waarde 0 geeft aan dat de e-mailstroom ok is) en actie te ondernemen voordat het aantal berichten in de wachtrij te groot wordt.

![Wachtrijen in het dashboard van de e-mailstroom in het Beveiligings& Compliance Center](../../media/0ef6e2ef-dd22-4363-9d4a-b20a00babc9f.png)

Wanneer u op het aantal in de wachtrij en **wachtrijen**staan, worden de wachtrijgegevens en richtlijnen voor het oplossen van het probleem weergegeven in een flyout-deelvenster (dezelfde flyout die wordt weergegeven nadat u op **Wachtrij weergeven** klikt in de details van een wachtrijwaarschuwing).

![Wachtrijgegevens](../../media/4eb088fe-5dd9-4bf4-b959-c1bb2545c515.png)

## <a name="see-also"></a>Zie ook

Zie Inzicht in [e-mailstroom in het Security & Compliance Center](mail-flow-insights-v2.md)voor meer informatie over andere e-mailstroominzichten in het dashboard voor e-mailstromen.
