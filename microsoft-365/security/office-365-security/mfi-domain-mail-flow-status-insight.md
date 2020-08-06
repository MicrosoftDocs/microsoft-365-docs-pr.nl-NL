---
title: Belangrijkste e-mail stroom status van e-mail stroom in het dashboard voor e-mail stroom
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen leren hoe u het e-mail stroom status inzicht van de belangrijkste domein kunt gebruiken in het dashboard voor e-mail stroom in het nalevings centrum voor beveiliging & voor het oplossen van problemen met de e-mail stroom in hun e-mail domeinen.
ms.openlocfilehash: 6366e3aee0ab50096f1396776397c80fabc8aaf2
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/06/2020
ms.locfileid: "46577743"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a>Belangrijkste status inzicht in de e-mail stroom van het domein in het beveiligings & nalevings centrum

Met de **belangrijkste status van de e-mail stroom** van de e-mail in het Beveiligingscentrum van de e-mail in het compliance [-&](mail-flow-insights-v2.md) Beveiligingscentrum beschikt u over de huidige status voor de domeinen van uw organisatie in de voorwaarden voor de e-mail stroom. Met deze functie kunt u problemen met domeinen identificeren en oplossen die problemen met de ***e-mail stroom*** kunnen veroorzaken (bijvoorbeeld om externe e-mail te ontvangen), met name domein vervaldatums of domeinen met onjuiste MX-records.

![De widget hoofddomein stroom status in het dashboard voor e-mail stroom in de beveiligings & nalevings centrum](../../media/mfi-top-domain-mail-flow-status-widget.png)

Wanneer u klikt op **Details weergeven** in de widget, verschijnt er een flyout met een **domein status** waarin meer Details voor de status van elk domein worden weergegeven:

- **Domein**
- **Vorige MX-record**
- **Huidige MX-record**
- **Status van ontvangen e-mail**
- **Domein status**: een groen vinkje geeft de huidige MX-record aan (op het moment dat u hebt geklikt op de widget) komt overeen met de waarde die we hebben voor de record en het domein heeft een e-mail ontvangen in de afgelopen twee uur.

  Een rode X geeft aan dat de MX-record is gewijzigd en dat het domein geen e-mailbericht heeft ontvangen in de afgelopen 6 uur. Dit geeft waarschijnlijk aan dat uw domein is verlopen of dat de MX-record onjuist is bijgewerkt. Neem contact op met uw domeinregistratieservice of DNS-hostingservice om te zien of het domein is verlopen, of dat de MX-record van het domein onjuist is.

U kunt klikken op **meer weergeven** om dezelfde gegevens te bekijken voor meer domeinen.

![Flyout Details in de e-mail stroom status van het belangrijkste domein](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="related-topics"></a>Verwante onderwerpen

Zie voor meer informatie over andere inzichten in het dashboard voor e-mail stroom de [e-mail stroom inzichten in het artikel over de beveiliging & nalevings centrum](mail-flow-insights-v2.md).
