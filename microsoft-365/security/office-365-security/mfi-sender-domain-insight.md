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
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen meer te weten komen over het domeininzicht van de afzender op de correctie in het dashboard van de e-mailstroom in het Security & Compliance Center.
ms.openlocfilehash: c4cf4a87ad770325ca6ad2f0b87ac8ce52c345c2
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818829"
---
# <a name="fix-sender-domain-insight"></a>Inzicht in verzenddomein oplossen

Microsoft 365 vereist berichten die vanuit interne on-premises e-mailomgevingen naar Microsoft 365 worden verzonden om aan bepaalde beveiligingscriteria te voldoen:

- U hebt een binnenkomende connector gemaakt in Microsoft 365 om SMTP-verbindingen te verifiëren vanaf uw on-premises e-mailserver met behulp van het bron-IP-adres of een certificaat.

- U hebt uw on-premises e-mailserver geconfigureerd om e-mail via Microsoft 365 door te geven aan de buitenwereld.

- In uw configuratie is een van de volgende instructies waar:

  - Het e-maildomein van de afzender is geregistreerd in uw organisatie. Raadpleeg voor meer informatie Domeinen toevoegen in Office 365.

  - Uw on-premises e-mailserver is geconfigureerd om een certificaat te gebruiken om e-mail naar Microsoft 365 te verzenden, het certificaat bevat of komt precies overeen met een domeinnaam die u hebt geregistreerd in Microsoft 365 en u hebt een op certificaten gebaseerde connector in Microsoft 365 met dat domein gemaakt. 

Berichten die niet aan de criteria voldoen, worden niet aan de organisatie toegeschreven en kunnen worden geweigerd.

Het **domeininzicht voor fix-afzender** toont u e-mail vanuit uw on-premises omgeving die niet aan de criteria voldoet, helpt u mogelijk gecompromitteerde machines en gebruikersaccounts in uw on-premises e-mailomgeving te identificeren en helpt u bij het uitvoeren van herstelacties.

![Het domeininzicht voor afzender herstellen in het e-mailstroomdashboard in het Security & Compliance Center](../../media/sender-domain-insight-selected.png)

Wanneer u op **Details weergeven**klikt, wordt u naar een ander widget gebracht met meer details zoals weergegeven in het volgende diagram:

![Het object Details in het domeininzicht fixer](../../media/sender-domain-view-details.png)

U ziet de binnenkomende connector die is gebruikt om de berichten naar Office 365 te brengen. U ook op **voorbeeld-id's voor voorbeeldberichten** klikken om details te zien voor de berichten die vanuit uw on-premises e-mailomgeving zijn verzonden. Omdat deze berichten zijn geweigerd door Office 365, u geen berichttracering gebruiken, maar u de voorbeeld-bericht-id's gebruiken om de berichten in uw on-premises e-mailomgeving bij te houden.

![Voorbeeld-bericht-id's weergeven in het domeininzicht voor afzender herstellen](../../media/sender-domain-view-sample-message-ids.png)

## <a name="related-topics"></a>Verwante onderwerpen

Zie [E-mailstroominzichten in het Security & Compliance Center](mail-flow-insights-v2.md)voor meer informatie over andere e-mailstroominzichten in het dashboard voor e-mailstromen.
