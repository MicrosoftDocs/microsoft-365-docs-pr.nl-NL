---
title: Belangrijkste e-mail stroom status van e-mail stroom in het dashboard voor e-mail stroom
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen leren hoe u met behulp van de belangrijkste status van de e-mail stroom van het e-mailsysteem in het Beveiligingscentrum van het & Beveiligingscentrum van uw MX-records problemen met de e-mail stroom kunt oplossen.
ms.openlocfilehash: 0d750ab4dbe5875796118086fae1d9119dc486f0
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920582"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a>Belangrijkste status inzicht in de e-mail stroom van het domein in het beveiligings & nalevings centrum

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Met de **belangrijkste status van de e-mail stroom** van het domein in het nalevings [Dashboard](mail-flow-insights-v2.md) van de [beveiligings &](https://protection.office.com) hebt u de huidige status van de e-mail stroom voor uw organisatie.

Dit inzicht helpt bij het identificeren en oplossen van domeinen met een *_e-mail stroom_* _ problemen. Het domein kan bijvoorbeeld geen externe e-mail ontvangen omdat het domein is verlopen of het domein een onjuiste MX-record heeft.

![De widget hoofddomein stroom status in het dashboard voor e-mail stroom in de beveiligings & nalevings centrum](../../media/mfi-top-domain-mail-flow-status-widget.png)

Wanneer u klikt op _ *weergave Details* * in de widget, verschijnt er een flyout met een **domein status** waarin meer Details voor de status van elk domein worden weergegeven:

- **Domein**
- **Vorige MX-record**
- **Huidige MX-record**
- **Status van ontvangen e-mail**
- **Domein status** : een groen vinkje geeft de huidige MX-record aan (op het moment dat u hebt geklikt op de widget) komt overeen met de waarde die we hebben voor de record en het domein heeft een e-mail ontvangen in de afgelopen twee uur.

  Een rode X geeft aan dat de MX-record is gewijzigd en dat het domein geen e-mailbericht heeft ontvangen in de afgelopen 6 uur. Dit geeft waarschijnlijk aan dat uw domein is verlopen of dat de MX-record onjuist is bijgewerkt. Neem contact op met uw domeinregistratieservice of DNS-hostingservice om te zien of het domein is verlopen, of dat de MX-record van het domein onjuist is.

U kunt klikken op **meer weergeven** om dezelfde gegevens te bekijken voor meer domeinen.

![Flyout Details in de e-mail stroom status van het belangrijkste domein](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="see-also"></a>Zie ook

Zie voor meer informatie over andere inzichten in het dashboard voor e-mail stroom de [e-mail stroom inzichten in het artikel over de beveiliging & nalevings centrum](mail-flow-insights-v2.md).
