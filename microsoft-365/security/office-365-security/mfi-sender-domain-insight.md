---
title: Inzicht in verzenddomein herstellen
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
description: Beheerders kunnen meer te weten komen over het inzicht in het domeinvan de afzender in het dashboard voor e-mailstroom in het Security & Compliance Center.
ms.openlocfilehash: 2db1b971ef39f8b207b349ca53237ff87cc9193e
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42810226"
---
# <a name="fix-sender-domain-insight"></a>Inzicht in verzenddomein herstellen

Office 365 vereist dat berichten die vanuit interne on-premises e-mailomgevingen naar Office 365 worden verzonden, voldoen aan bepaalde beveiligingscriteria:

- U hebt een binnenkomende connector in Office 365 gemaakt om SMTP-verbindingen vanaf uw on-premises e-mailserver te verifiëren met behulp van het bron-IP-adres of een certificaat.

- U hebt uw on-premises e-mailserver geconfigureerd om e-mail via Office 365 door te sturen naar de buitenwereld.

- In uw configuratie geldt een van de volgende uitspraken:

  - Het e-maildomein van de afzender is geregistreerd in uw Office 365-organisatie. Zie Domeinen toevoegen in Office 365 voor meer informatie.

  - Uw on-premises e-mailserver is geconfigureerd om een certificaat te gebruiken om e-mail naar Office 365 te verzenden, het certificaat bevat of komt precies overeen met een domeinnaam die u hebt geregistreerd in Office 365 en u hebt daarmee een op certificaten gebaseerde connector in Office 365 gemaakt Domein. 

Berichten die niet aan de criteria voldoen, worden niet aan de organisatie toegeschreven en kunnen worden afgewezen.

Het inzicht in het domein van **de afzender fix** toont u e-mail vanuit uw on-premises omgeving die niet aan de criteria voldoet, helpt u om mogelijk gecompromitteerde machines en gebruikersaccounts in uw on-premises e-mailomgeving te identificeren en helpt u bij het uitvoeren van herstelacties.

![Het inzicht van het verzenddomein oplossen in het dashboard voor e-mailstroom in het Security & Compliance Center](../../media/sender-domain-insight-selected.png)

Wanneer u op **Details weergeven**klikt, wordt u naar een andere widget geleid met meer details zoals weergegeven in het volgende diagram:

![De widget Details in het inzicht van het afzenderdomein herstellen](../../media/sender-domain-view-details.png)

U ziet de binnenkomende connector die is gebruikt om de berichten naar Office 365 te leveren. U ook op **voorbeeldbericht-id's weergeven** klikken om details te zien voor de berichten die vanuit uw e-mailomgeving ter plaatse zijn verzonden. Omdat deze berichten zijn geweigerd door Office 365, u geen berichttracering gebruiken, maar u de voorbeeldbericht-id's gebruiken om de berichten in uw on-premises e-mailomgeving bij te houden.

![Voorbeeldbericht-id's weergeven in het inzicht van het afzenderdomein herstellen](../../media/sender-domain-view-sample-message-ids.png)

## <a name="see-also"></a>Zie ook

Zie Inzichten in de [stroomstromen in het Security & Compliance Center](mail-flow-insights-v2.md)voor meer informatie over andere e-mailstroom-inzichten in het dashboard voor e-mailstroom.
