---
title: Beveiliging tegen uitgaande spam
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Lees als beheerder hoe Office 365 en Exchange Online Protection (EOP) klanten beschermt tegen uitgaande spam en wat u moet doen als u massamailings moet verzenden.
ms.openlocfilehash: ffedcf68489914865c00eb68aecfa6c74e519ee2
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/05/2020
ms.locfileid: "44033924"
---
# <a name="outbound-spam-protection"></a>Beveiliging tegen uitgaande spam

We nemen het beheer van uitgaande spam serieus, omdat Microsoft 365 (Exchange Online of standalone Exchange Online Protection (EOP) zonder Exchange Online-postvakken) een online service is waar veel klanten een gedeelde groep bronnen gebruiken. Eén Microsoft 365-klant die opzettelijk of onbedoeld spam van zijn organisatie verzendt, kan de reputatie van de hele service verslechteren en de bezorging van e-mail voor andere klanten beïnvloeden.

In dit onderwerp worden de besturingselementen en meldingen beschreven die zijn ontworpen om uitgaande spam te voorkomen en wat u doen als u massamailings moet verzenden.

## <a name="what-admins-can-do-to-control-outbound-spam"></a>Wat beheerders kunnen doen om uitgaande spam te beheren

- **Ingebouwde meldingen gebruiken:** Wanneer een gebruiker de verzendlimieten van [de service](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) of het uitgaande [spambeleid](configure-the-outbound-spam-policy.md) overschrijdt en geen e-mail verzendt, verzendt het standaardwaarschuwingsbeleid met de naam **Gebruiker beperkt e-mail** meldingen naar leden van de groep **TenantAdministrators** **(Globale beheerders).** Zie [De waarschuwingsinstellingen voor beperkte gebruikers verifiëren](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)om te configureren wie deze meldingen nog meer ontvangt. Ook het standaardwaarschuwingsbeleid met de naam **E-mailverzendenlimiet overschreden** en **Verdachte e-mailverzendpatronen gedetecteerd** e-mailmeldingen verzenden naar leden van de groep **TenantAdministrators** **(Globale beheerders).** Zie voor meer informatie over waarschuwingsbeleid, [Waarschuwingsbeleid in het beveiligings- en compliancecentrum](../../compliance/alert-policies.md).

- **Spamklachten van externe e-mailproviders**bekijken: Veel e-mailservices zoals Outlook.com, Yahoo en AOL bieden een feedbacklus waarbij als een gebruiker in hun service een e-mail van Microsoft 365 markeert als spam, het bericht wordt verpakt en teruggestuurd naar ons voor beoordeling. Ga voor meer informatie over de <https://sendersupport.olc.protection.outlook.com/pm/services.aspx>ondersteuning van afzenders voor Outlook.com naar .

## <a name="how-eop-controls-outbound-spam"></a>Hoe EOP uitgaande spam becontroleert

- **Scheiding van uitgaand e-mailverkeer:** Elk uitgaand bericht dat via de service wordt verzonden, wordt gescand op spam. Als het bericht is bepaald als spam, wordt het geleverd vanuit een secundaire, minder gerenommeerde IP-adresgroep met de naam de _leveringspool met een hoog risico._ Zie Groep voor levering met [een hoog risico voor uitgaande berichten in Office 365 voor](high-risk-delivery-pool-for-outbound-messages.md)meer informatie.

- **Monitoring our source IP address reputation:** Microsoft 365 queries various third party IP block lists. Er wordt een waarschuwing gegenereerd als een van de IP-adressen die we gebruiken voor uitgaande e-mail op deze lijsten wordt weergegeven. Dit stelt ons in staat om snel te reageren wanneer spam heeft geleid tot onze reputatie te degraderen. Wanneer een waarschuwing wordt gegenereerd, hebben we interne documentatie die beschrijft hoe u onze IP-adressen verwijderen (verwijderd) uit bloklijsten.

- **Schakel accounts uit die te veel spam**<sup>\*</sup>verzenden: Hoewel we uitgaande spam scheiden in de leveringspool met een hoog risico, kunnen we niet toestaan dat een account (vaak een gecompromitteerd account) voor onbepaalde tijd spam verzendt. We controleren accounts die spam verzenden en wanneer ze een geheime limiet overschrijden, wordt het account geblokkeerd voor het verzenden van e-mail. Er zijn verschillende drempelwaarden voor individuele gebruikers en de gehele tenant.

- **Accounts uitschakelen die te snel te veel e-mail**<sup>\*</sup>verzenden: Naast de limieten die zoeken naar berichten die als spam zijn gemarkeerd, zijn er ook limieten die accounts blokkeren wanneer ze een algemene uitgaande berichtlimiet bereiken, ongeacht het spamfiltervonnis voor de uitgaande berichten. Een gecompromitteerd account kan zero-day (voorheen niet herkende) spam verzenden die wordt gemist door het spamfilter. Omdat het moeilijk kan zijn om een legitieme massamailingcampagne te identificeren versus een spamcampagne, helpen deze limieten om eventuele schade te minimaliseren.

<sup>\*</sup>We adverteren niet de exacte limieten, zodat spammers het systeem niet kunnen spelen, en dus kunnen we de limieten verhogen of verlagen als dat nodig is. De limieten zijn hoog genoeg om te voorkomen dat een gemiddelde zakelijke gebruiker ze ooit overschrijdt, en laag genoeg om de schade veroorzaakt door een spammer te helpen beperken.

## <a name="recommendations-for-customers-who-want-to-send-mass-mailings-through-eop"></a>Aanbevelingen voor klanten die massamailings willen versturen via EOP

Het is moeilijk om een evenwicht te vinden tussen klanten die een groot aantal e-mail willen verzenden vs. de service te beschermen tegen gecompromitteerde accounts en bulke-mailafzenders met slechte acquisitiepraktijken voor ontvangers. De kosten van een Microsoft 365-e-mailbron die op een IP-bloklijst van derden landt, zijn groter dan het blokkeren van een gebruiker die te veel e-mail verzendt.

Zoals beschreven in de [Exchange Online Service Description](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits), is het gebruik van EOP om bulke-mail te verzenden geen ondersteund gebruik van de service en is het alleen toegestaan op basis van "best-effort". Voor klanten die wel bulke-mail willen verzenden, raden we de volgende oplossingen aan:

- **Bulk-e-mail verzenden via on-premises e-mailservers:** Dit betekent dat klanten hun eigen e-mailinfrastructuur moeten onderhouden voor massamailings.

- **Gebruik een bulke-mailprovider van**derden: Er zijn verschillende leveranciers van bulke-mailoplossingen van derden die u gebruiken om massamailings te verzenden. Deze bedrijven hebben een gevestigd belang bij het werken met klanten om goede e-mail verzenden praktijken te waarborgen.

De Messaging, Mobile, Malware Anti-Abuse Working Group (MAAWG) publiceert haar lidmaatschap rooster op <https://www.maawg.org/about/roster>. Verschillende bulk e-mail providers zijn op de lijst, en staan bekend als verantwoordelijke internet burgers.
