---
title: Het statusinzicht van de status van de topmailstroom
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
description: Beheerders kunnen meer te weten komen over het inzicht in de status van de domeinmailstroom in het dashboard voor e-mailstroom in het Security & Compliance Center.
ms.openlocfilehash: 42ce0545dad2804829d15572ce6e1f5a0ca6b49f
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42808809"
---
# <a name="top-domain-mail-flow-status-insight"></a>Het statusinzicht van de status van de topmailstroom

Het inzicht in de status van de **top-domeinmailstroom** geeft u de huidige status voor de domeinen van uw organisatie op het gebied van e-mailstroom. Met dit inzicht u domeinen identificeren en oplossen die problemen ondervinden met ***e-mailstromen*** (bijvoorbeeld geen externe e-mail kunnen ontvangen), met name domeinvervaldatums of domeinen met onjuiste MX-records.

![Het inzicht in de status van de domeinstroom top in het dashboard voor e-mailstroom in het Security & Compliance Center](../../media/domain-mail-flow-status-selected.png)

Wanneer u op Details in het inzicht **weergeven** klikt, verschijnt er een flyout die u meer details voor de status van elk domein weergeeft.

Een groen vinkje voor een domein geeft de huidige MX-record aan (wanneer u naar het dashboard met de resultaten van de e-mailstroom hebt gebladerd) komt overeen met de waarde die we hebben geregistreerd en dat het domein de afgelopen twee uur e-mail heeft ontvangen.

Een rode x voor een domein geeft aan dat de MX-record is gewijzigd en dat het domein de afgelopen 6 uur geen e-mail heeft ontvangen. Dit geeft waarschijnlijk aan dat uw domein is verlopen of dat de MX-record onjuist is bijgewerkt. Neem contact op met uw domeinregistrar of DNS-hostingservice om te zien of het domein is verlopen of of de MX-record van het domein onjuist is.

![De flyout details in het inzicht in de status van de hoogste domeinstroom](../../media/domain-mail-flow-status-flyout.png)

## <a name="see-also"></a>Zie ook

Zie Inzichten in de [stroomstromen in het Security & Compliance Center](mail-flow-insights-v2.md)voor meer informatie over andere e-mailstroom-inzichten in het dashboard voor e-mailstroom.
