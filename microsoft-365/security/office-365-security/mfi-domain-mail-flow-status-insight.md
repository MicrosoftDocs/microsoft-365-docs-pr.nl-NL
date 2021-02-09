---
title: Het belangrijkste inzicht in de status van de domein-e-mailstroom in het dashboard E-mailstroom
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
description: Beheerders kunnen in het beveiligings- & Compliancecentrum in het dashboard E-mailstroom het belangrijkste inzicht in de status van de domeinstroomstroom gebruiken om problemen met de e-mailstroom met betrekking tot hun MX-records op te lossen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: df0f571d29d72b23e7b2e210b61a4fb1676175aa
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150205"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a>Belangrijkste inzicht in de status van de domein-e-mailstroom in het & compliancecentrum

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender voor Office 365-abonnement 1 en abonnement 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Het **belangrijkste inzicht in de status** van de domeinstroomstroom in het dashboard E-mailstroom in het beveiligings- & [compliancecentrum](https://protection.office.com) geeft u de huidige status van de e-mailstroom voor uw organisatie. [](mail-flow-insights-v2.md)

Met dit inzicht kunt u domeinen identificeren en oplossen die problemen met ***de e-mailstroom*** ondervinden. Het domein kan bijvoorbeeld geen externe e-mail ontvangen omdat het domein is verlopen of omdat het domein een onjuiste MX-record heeft.

![De belangrijkste widget voor de domeinstroomstatus in het dashboard E-mailstroom in het & Compliancecentrum](../../media/mfi-top-domain-mail-flow-status-widget.png)

Wanneer u op **Details weergeven** in de widget klikt, wordt een **flyout** voor de domeinstatus weergegeven met meer details over de status van elk domein:

- **Domein**
- **Vorige MX-record**
- **Huidige MX-record**
- **Status van e-mail die wordt ontvangen**
- **Domeinstatus:** een groen vinkje geeft aan dat de huidige MX-record (op het moment dat u op de widget hebt geklikt) overeenkomt met de waarde die is op registreren en dat het domein de afgelopen twee uur e-mail heeft ontvangen.

  Een rode X geeft aan dat de MX-record is gewijzigd en dat het domein de afgelopen 6 uur geen e-mail heeft ontvangen. Dit geeft waarschijnlijk aan dat uw domein is verlopen of dat de MX-record onjuist is bijgewerkt. Neem contact op met uw domeinregistrar of de DNS-hostingservice om te controleren of het domein is verlopen of dat de MX-record van het domein onjuist is.

U kunt op **Meer weergeven** klikken om dezelfde informatie voor meer domeinen weer te geven.

![Flyout Details in het statusinzicht van de e-mailstroom van het hoogste domein](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="see-also"></a>Zie ook

Zie inzichten in de e-mailstroom in het beveiligings- en compliancecentrum voor meer informatie & [inzichten in het dashboard E-mailstroom.](mail-flow-insights-v2.md)
