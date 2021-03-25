---
title: Inzicht in de status van de hoogste domeinstroomstroom in het e-mailstroomdashboard
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen leren hoe ze het inzicht in de status van de hoogste domeinstroomstroom kunnen gebruiken in het e-mailstroomdashboard in het Beveiligings- & Compliancecentrum om problemen met de e-mailstroom met betrekking tot hun MX-records op te lossen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 850e72fa0ad7a3f41450a1d0a2c02dd3df4a0cb5
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204936"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a>Inzicht in de status van de hoogste domeinstroomstroom in het beveiligings- & compliancecentrum

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Het **inzicht in de status** van de hoogste domeinstroomstroom in het [e-mailstroomdashboard](mail-flow-insights-v2.md) in het Beveiligings- & [Compliancecentrum](https://protection.office.com) geeft u de huidige status van de e-mailstroom voor uw organisatie.

Met dit inzicht kunt u domeinen identificeren en oplossen die te maken hebben ***met e-mailstroomproblemen.*** Het domein kan bijvoorbeeld geen externe e-mail ontvangen omdat het domein is verlopen of omdat het domein een onjuiste MX-record heeft.

![De bovenste widget met domeinstroomstatus in het e-mailstroomdashboard in het beveiligings- & Compliancecentrum](../../media/mfi-top-domain-mail-flow-status-widget.png)

Wanneer u op **Details weergeven** in de widget klikt, wordt er een fly-out voor **domeinstatus** weergegeven waarin meer details worden weergegeven voor de status van elk domein:

- **Domein**
- **Vorige MX-record**
- **Huidige MX-record**
- **Status voor het ontvangen van e-mail**
- **Domeinstatus:** een groen vinkje geeft aan dat de huidige MX-record (op het moment dat u op de widget hebt geklikt) overeenkomt met de waarde die we hebben op de record en dat het domein de afgelopen twee uur e-mail heeft ontvangen.

  Een rode X geeft aan dat de MX-record is gewijzigd en dat het domein de afgelopen 6 uur geen e-mail heeft ontvangen. Dit geeft waarschijnlijk aan dat uw domein is verlopen of dat de MX-record onjuist is bijgewerkt. Neem contact op met uw domeinregistrar of DNS-hostingservice om te zien of het domein is verlopen of dat de MX-record van het domein onjuist is.

U kunt op **Meer weergeven** klikken om dezelfde informatie weer te geven voor meer domeinen.

![Details flyout in the Top domain mail flow status insight](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="see-also"></a>Zie ook

Zie E-mailstroominzichten in het Beveiligings- & compliancecentrum voor meer informatie over andere inzichten [in het e-mailstroomdashboard.](mail-flow-insights-v2.md)
