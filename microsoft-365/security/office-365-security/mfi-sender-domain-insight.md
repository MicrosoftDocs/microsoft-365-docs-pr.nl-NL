---
title: Inzicht in verzenddomein oplossen
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
description: Beheerders kunnen meer te weten komen over het domeininzicht voor de afzender in het dashboard met e-mailstromen in het Security & Compliance Center.
ms.openlocfilehash: a416b4d15ff52a611f00a88de8440c749ff08ad3
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635170"
---
# <a name="fix-sender-domain-insight"></a>Inzicht in verzenddomein oplossen

Microsoft 365 vereist dat berichten die vanuit interne on-premises e-mailomgevingen naar Microsoft 365 worden verzonden, aan bepaalde beveiligingscriteria voldoen:

- U hebt een binnenkomende connector in Microsoft 365 gemaakt om SMTP-verbindingen te verifiëren vanaf uw on-premises e-mailserver met behulp van het bron-IP-adres of een certificaat.

- U hebt uw on-premises e-mailserver geconfigureerd om e-mail via Microsoft 365 door te sturen naar de buitenwereld.

- In uw configuratie is een van de volgende uitspraken waar:

  - Het e-maildomein van de afzender is geregistreerd in uw organisatie. Zie Domeinen toevoegen in Office 365 voor meer informatie.

  - Uw on-premises e-mailserver is geconfigureerd om een certificaat te gebruiken om e-mail naar Microsoft 365 te verzenden, het certificaat bevat of komt precies overeen met een domeinnaam die u hebt geregistreerd in Microsoft 365 en u hebt een op certificaten gebaseerde connector in Microsoft 365 met dat domein gemaakt. 

Berichten die niet aan de criteria voldoen, worden niet aan de organisatie toegeschreven en kunnen worden afgewezen.

Het domeininzicht **Voor afzenderen** van de oplossing toont u e-mail vanuit uw on-premises omgeving die niet aan de criteria voldoet, helpt u mogelijk gecompromitteerde machines en gebruikersaccounts te identificeren in uw on-premises e-mailomgeving en helpt u bij het uitvoeren van herstelacties.

![Het domeininzicht van afzenders herstellen in het dashboard met e-mailstroom in het Beveiligings- & Compliance Center](../../media/sender-domain-insight-selected.png)

Wanneer u op **Details weergeven**klikt, wordt u naar een andere widget geleid met meer details, zoals in het volgende diagram wordt weergegeven:

![De widget Details in het domeininzicht Afzenderoplossen](../../media/sender-domain-view-details.png)

U ziet de binnenkomende connector die is gebruikt om de berichten naar Office 365 te leveren. U ook op **Voorbeeldbericht-id's weergeven** om details te zien voor de berichten die zijn verzonden vanuit uw on-premises e-mailomgeving. Omdat deze berichten zijn afgewezen door Office 365, u berichttracering niet gebruiken, maar u de id's van het voorbeeldbericht gebruiken om de berichten in uw on-premises e-mailomgeving bij te houden.

![Voorbeeldbericht-id's weergeven in het domeininzicht Van afzenderherstellen](../../media/sender-domain-view-sample-message-ids.png)

## <a name="see-also"></a>Zie ook

Zie Inzicht in [e-mailstroom in het Security & Compliance Center](mail-flow-insights-v2.md)voor meer informatie over andere e-mailstroominzichten in het dashboard voor e-mailstromen.
