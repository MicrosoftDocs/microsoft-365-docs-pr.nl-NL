---
title: Scheduler voor Microsoft 365 veelgestelde vragen
ms.author: v-aiyengar
author: AshaIyengar21
manager: serdars
audience: Admin
ms.topic: article
ms.service: scheduler
localization_priority: Normal
description: Scheduler voor Microsoft 365 veelgestelde vragen
ms.openlocfilehash: d4cedf420dd605d04328b7f1edeabbd4e1bb5ac7
ms.sourcegitcommit: e1e275eb88153bafddf93327adf8f82318913a8d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52809163"
---
# <a name="scheduler-for-microsoft-365-faqs"></a>Scheduler voor Microsoft 365 veelgestelde vragen

**Vraag:** Hoe integreert Scheduler met andere Cortana-functies, zoals *Cortana voor* Windows, *Daily Briefing Email* en Mijn *e-mailberichten afspelen?*</br>
Scheduler is een onafhankelijke service van andere Cortana-functies. Andere Cortana-functies kunnen op tenantniveau worden uitgeschakeld en Scheduler kan nog steeds worden ingeschakeld met behulp van het cortana@yourdomain.com e-mailadres. Momenteel kunnen gebruikers alleen via e-mail met Scheduler communiceren.

**Vraag:** Werkt dit alleen met Outlook? Worden andere e-mailproducten ondersteund?</br>
Zolang u een licentie hebt, anders dan de drie bovenstaande vereisten, kunnen gebruikers e-mailen cortana@yourdomain.com e-mailclient op elk apparaat.

**Vraag:** Kunnen contactpersonen zich in een persoonlijke lijst met contactpersonen Outlook gal of een ander bedrijfsequivalent?</br>
Deelnemers aan de vergadering kunnen iedereen zijn met een e-mailadres binnen of buiten het bedrijf. Helaas kan Scheduler namen niet automatisch vertalen naar e-mailadressen/aliassen door deze vandaag op te zoeken in de gal.

**Vraag:** Kan ik Scheduler gebruiken met mijn geïnstalleerde versie (on-premises) versie van Outlook?</br>
Scheduler vereist Exchange Online. Werkt niet met Exchange Server (On-prem). Werkt met elke e-mailclient, Outlook bureaublad, OWA, iOS, android, gmail, en ga zo maar door.

**Vraag:** Moet Outlook op de achtergrond geopend zijn?</br>
Outlook hoeft niet op de achtergrond te worden geopend. Het enige wat u hoeft te doen, is Cortana een e-mail sturen en erop vertrouwen om het grootste deel van het werk te doen.

## <a name="frequently-asked-trust-and-privacy-questions"></a>Veelgestelde vragen over vertrouwen en privacy

**Vraag:** Hoe werkt Scheduler?</br>
Scheduler gebruikt Scheduling Intelligence (AI) die wordt uitgebreid met menselijke assistenten. Als AI-modellen ondersteuning nodig hebben in de natuurlijke communicatietaal met Cortana, escaleert het vergaderverzoek naar een mens voor controle en voltooiing.

**Vraag:** Wie zijn de mensen die geëscaleerde aanvragen bekijken? </br>
Planningsassistenten zijn Microsoft Supplier Security and Privacy Assurance (SSPA) gecertificeerd voor persoonlijke en zeer vertrouwelijke informatie. 

**Vraag:** Wat kunnen SSPA-assistenten weergeven?</br>
Scheduler en de SSPA-assistenten kunnen de e-mailberichten bekijken die zijn geadresseerd aan Cortana. In een threaded e-mailuitwisseling worden alleen de e-mailberichten verwerkt die het e-mailadres van Cortana bevatten, niet de eerdere e-mailberichten in de thread voordat Cortana werd toegevoegd.   

**Vraag:** Worden klantgegevens bewaard in de gegevensgegevens van de Flow? </br>
Scheduler slaat alle klantinhoud op binnen de tenantgrenzen en behoudt gegevens volgens de AVG-richtlijnen, Microsoft 365 Vertrouwen & privacybeleid en tenant-e-mailbeleid.

**Vraag:** Hoe verwerkt Scheduler de vrije/drukke gegevens van interne deelnemers? </br>
De automatisering van Scheduler maakt gebruik van *de findMeetingTimes-service* om tijden te identificeren die wederzijds beschikbaar zijn voor genodigden en de organisator. Deze service is van Outlook andere ervaringen, zoals *Voorgestelde tijden* in het Outlook vergaderingsformulier. Informatie over gratis/bezet ge attendee wordt niet expliciet gebruikt als vrije/bezet blokken. 

**Vraag:** Is Scheduler GDPR Compliant? </br>
Ja.

**Vraag:** Wie toegang tot het postvak van Cortana? </br>
Scheduler verwerkt vergaderverzoeken en bijbehorende e-mailberichten die naar het Cortana-postvak van uw tenant worden verzonden. Microsoft heeft geen andere toegang tot het Cortana-postvak, behalve via goedkeuring van Het Postvak IN op verzoek van de tenantbeheerder.  

**Vraag:** Worden klantgegevens gebruikt voor het trainen van AI-modellen?</br>
Er kan geen klantinhoud van Scheduler voor Microsoft 365 worden gebruikt voor gegevenstrainingssets. Alle klantinhoud bevindt zich in de klantten tenant.  

**Vraag:** Verwerkt Scheduler versleutelde e-mail?</br>
Nee, versleutelde e-mail wordt geweigerd door de werkstroom Scheduler. 




