---
title: Groep met verhoogd risico voor uitgaande berichten
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: Ontdek hoe de leveringspool met een hoog risico wordt gebruikt om de reputatie van e-mailservers in de Microsoft 365-datacenters te beschermen.
ms.openlocfilehash: 7fb4788361534335be1e07bae44ed7511bebe434
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43638032"
---
# <a name="high-risk-delivery-pool-for-outbound-messages"></a>Groep met verhoogd risico voor uitgaande berichten

E-mailservers in de Microsoft 365-datacenters maken zich mogelijk tijdelijk schuldig aan het verzenden van spam. Bijvoorbeeld een malware- of schadelijke spamaanval in een on-premises e-mailorganisatie die uitgaande e-mail verzendt via Microsoft 365 of microsoft 365-accounts heeft gecompromitteerd. Deze scenario's kunnen ertoe leiden dat het IP-adres van de getroffen Microsoft 365-datacenterservers wordt weergegeven op bloklijsten van derden. Bestemmingse-e-mailorganisaties die deze bloklijsten gebruiken, weigeren e-mail van deze berichtenbronnen.

Om dit te voorkomen, worden alle uitgaande berichten van Microsoft 365-datacenterservers waarvan is vastgesteld dat ze spam zijn of die de verzendlimieten van [de service](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) of het [uitgaande spambeleid](configure-the-outbound-spam-policy.md) overschrijden, verzonden via de _groep voor levering met een hoog risico._

De groep voor levering met een hoog risico is een secundaire IP-adresgroep voor uitgaande e-mail die alleen wordt gebruikt om berichten van "lage kwaliteit" te verzenden (bijvoorbeeld spam en [backscatter).](backscatter-messages-and-eop.md) Als u de groep voor levering met een hoog risico gebruikt, voorkomt u dat de normale IP-adresgroep voor uitgaande e-mail spam verzendt. De normale IP-adresgroep voor uitgaande e-mail behoudt de reputatie die berichten van "hoge kwaliteit" verzendt, waardoor de kans kleiner is dat dit IP-adres op IP-bloklijsten wordt weergegeven.

De zeer reële mogelijkheid dat IP-adressen in de risicogroep worden geplaatst op IP-bloklijsten blijft bestaan, maar dit is door het ontwerp. Levering aan de beoogde ontvangers is niet gegarandeerd, omdat veel e-mailorganisaties geen berichten accepteren uit de groep voor levering met een hoog risico.

Zie [Outbound Spam beheren](outbound-spam-controls.md)voor meer informatie .

> [!NOTE]
> Berichten waarbij het brone-maildomein geen A-record heeft en geen MX-record die is gedefinieerd in openbare DNS, worden altijd door de groep met een hoog risico geleid, ongeacht hun spam of het verzenden van limietdispositie.

## <a name="bounce-messages"></a>Bounceberichten

De uitgaande delivery pool met hoog risico beheert de levering voor alle niet-leveringsrapporten (ook bekend als NDR's, bounceberichten, meldingen over de leveringsstatus of DSN's).

Mogelijke oorzaken voor een stijging van de NDR's zijn:

- Een spoofing-campagne die van invloed is op een van de klanten die de service gebruiken.

- Een directory oogst aanval.

- Een spamaanval.

- Een malafide e-mailserver.

Al deze problemen kunnen resulteren in een plotselinge toename van het aantal NDR's dat door de service wordt verwerkt. Vele malen, deze NDR's lijken te zijn spam naar andere e-mailservers en diensten (ook wel bekend als _[backscatter).](backscatter-messages-and-eop.md)_
