---
title: Inzicht in e-mailstroomstatus van hoofddomein
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
description: Beheerders kunnen meer te weten komen over het statusinzicht van de beste domeinmailstroom in het dashboard voor de &-naleving van de e-mailstroom.
ms.openlocfilehash: 22b0f8cefe8baacac682550126de55dcbf880d73
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818589"
---
# <a name="top-domain-mail-flow-status-insight"></a>Inzicht in e-mailstroomstatus van hoofddomein

Het statusinzicht voor de status van de **hoogste domeinmailstroom** geeft u de huidige status voor de domeinen van uw organisatie in termen van e-mailstroom. Met dit inzicht u domeinen identificeren en oplossen die problemen ondervinden die van invloed zijn op ***de e-mailstroom*** (bijvoorbeeld niet in staat om externe e-mail te ontvangen), met name domeinverloop of domeinen met onjuiste MX-records.

![Het inzicht in de status van de hoogste domeinstroom in het dashboard voor e-mailstroom in het Security & Compliance Center](../../media/domain-mail-flow-status-selected.png)

Wanneer u op **Details weergeven** in het inzicht klikt, verschijnt er een flyout die u meer details geeft voor de status van elk domein.

Een groen vinkje voor een domein geeft aan dat de huidige MX-record (wanneer u naar het dashboard voor e-mailstroomstatistieken hebt gebladerd) overeenkomt met de waarde die we hebben en dat het domein de afgelopen twee uur e-mail heeft ontvangen.

Een rode x voor een domein geeft aan dat de MX-record is gewijzigd en dat het domein de afgelopen 6 uur geen e-mail heeft ontvangen. Dit geeft waarschijnlijk aan dat uw domein is verlopen of dat de MX-record onjuist is bijgewerkt. Neem contact op met uw domeinregistrar of DNS-hostingservice om te zien of het domein is verlopen of dat de MX-record van het domein onjuist is.

![De flyout Details in het inzicht in de status van de status van de bovenste domeinstroom](../../media/domain-mail-flow-status-flyout.png)

## <a name="related-topics"></a>Verwante onderwerpen

Zie [E-mailstroominzichten in het Security & Compliance Center](mail-flow-insights-v2.md)voor meer informatie over andere e-mailstroominzichten in het dashboard voor e-mailstromen.
