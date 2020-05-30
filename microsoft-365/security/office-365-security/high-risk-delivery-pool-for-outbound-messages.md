---
title: Uitgaande bezorgpools
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
description: Ontdek hoe de leveringspools worden gebruikt om de reputatie van e-mailservers in de Microsoft 365-datacenters te beschermen.
ms.openlocfilehash: 213149eda3dd121b65b64e3bddbb4bd73d66f57c
ms.sourcegitcommit: 6746fae2f68400fd985711b1945b66766d2a59a4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/29/2020
ms.locfileid: "44419158"
---
# <a name="outbound-delivery-pools"></a>Uitgaande bezorgpools

E-mailservers in de Microsoft 365-datacenters maken zich mogelijk tijdelijk schuldig aan het verzenden van spam. Bijvoorbeeld een malware- of kwaadaardige spamaanval in een on-premises e-mailorganisatie die uitgaande e-mail verzendt via Microsoft 365 of Microsoft 365-accounts heeft gecompromitteerd. Aanvallers proberen ook detectie te voorkomen door berichten door te geven via Microsoft 365 forwarding.

Deze scenario's kunnen resulteren in het IP-adres van de getroffen Microsoft 365-datacenterservers die worden weergegeven in bloklijsten van derden. Doel-e-mailorganisaties die deze blokkeerlijsten gebruiken, weigeren e-mail uit die berichtenbronnen.

## <a name="high-risk-delivery-pool"></a>Hoogrisico leveringspool
Om dit te voorkomen, worden alle uitgaande berichten van Microsoft 365 datacenterservers die als spam zijn vastgesteld of die de verzendlimieten van [de service](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) of [uitgaande spambeleid](configure-the-outbound-spam-policy.md) overschrijden, verzonden via de _leveringspool met een hoog risico._

De leveringspool met een hoog risico is een aparte IP-adresgroep voor uitgaande e-mail die alleen wordt gebruikt om berichten van "lage kwaliteit" te verzenden (bijvoorbeeld spam en [backscatter).](backscatter-messages-and-eop.md) Het gebruik van de pool met een hoog risico helpt voorkomen dat de normale IP-adresgroep voor uitgaande e-mail spam verzendt. De normale IP-adresgroep voor uitgaande e-mail behoudt de reputatie die berichten van "hoge kwaliteit" verzendt, waardoor de kans wordt verkort dat dit IP-adres op IP-bloklijsten wordt weergegeven.

De zeer reële mogelijkheid dat IP-adressen in de hoog-risico leveringspool op IP-bloklijsten zullen worden geplaatst blijft, maar dit is door het ontwerp. Levering aan de beoogde ontvangers is niet gegarandeerd, omdat veel e-mailorganisaties geen berichten accepteren uit de leveringspool met een hoog risico.

Zie [Uitgaande spam controleren voor](outbound-spam-controls.md)meer informatie.

> [!NOTE]
> Berichten waarin het brone-maildomein geen A-record heeft en geen MX-record gedefinieerd in openbare DNS, worden altijd doorgestuurd via de leveringspool met een hoog risico, ongeacht hun spam of het verzenden van limietvermeldingen.

### <a name="bounce-messages"></a>Berichten bounceen

De uitgaande leveringspool met een hoog risico beheert de levering voor alle rapporten zonder levering (ook bekend als NDR's, bounceberichten, meldingen van leveringsstatuss of DSN's).

Mogelijke oorzaken voor een stijging van de NDR's zijn:

- Een spoofing-campagne die van invloed is op een van de klanten die de service gebruiken.
- Een directory harvest aanval.
- Een spamaanval.
- Een malafide e-mailserver.

Al deze problemen kunnen resulteren in een plotselinge toename van het aantal NDR's wordt verwerkt door de dienst. Vele malen, deze NDR's lijken te zijn spam naar andere e-mailservers en diensten (ook bekend als _[backscatter](backscatter-messages-and-eop.md)_).

## <a name="relay-pool"></a>Relaispool

Berichten die worden doorgestuurd of doorgegeven vanuit Microsoft 365, worden verzonden met behulp van een speciale relaypool, omdat de eindbestemming Microsoft 365 niet als de werkelijke afzender moet beschouwen. Het is ook belangrijk voor ons om dit verkeer te isoleren, omdat er legitieme en slechtegitmate scenario's zijn voor autoforwarding of relaying e-mail uit Microsoft 365. Net als bij de leveringspool met een hoog risico wordt een aparte IP-adresgroep gebruikt voor doorgegeven e-mail. Deze adresgroep wordt niet gepubliceerd omdat deze vaak kan veranderen. 

Microsoft 365 moet controleren of de oorspronkelijke afzender legitiem is, zodat we het doorgestuurde bericht met vertrouwen kunnen overbrengen. Om dat te doen, moet e-mailverificatie (SPF, DKIM en DMARC) worden doorgegeven wanneer het bericht naar ons komt. In gevallen waarin we de afzender kunnen verifiëren, gebruiken we Sender Rewriting om de ontvanger te laten weten dat het doorgestuurde bericht afkomstig is van een vertrouwde bron. U meer lezen over hoe dat werkt en wat u doen om ervoor te zorgen dat het verzendende domein verificatie doorgeeft in [Sender Rewriting Scheme (SRS).](https://docs.microsoft.com/office365/troubleshoot/antispam/sender-rewriting-scheme)
