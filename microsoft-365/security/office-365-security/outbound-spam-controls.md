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
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen meer informatie krijgen over de besturingselementen voor uitgaande spam in Exchange Online Protection (EOP) en wat u moet doen als u massamailings wilt verzenden.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0fb6bfe5d83c551c0a93cc7b453b27a2d7b476bc
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538733"
---
# <a name="outbound-spam-protection-in-eop"></a>Beveiliging tegen uitgaande spam in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

In Microsoft 365 organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection (EOP) organisaties zonder Exchange Online postvakken, nemen we het beheren van uitgaande spam serieus. Zelfs als een klant opzettelijk of onbedoeld spam verzendt vanuit de organisatie, kan deze actie de reputatie van de hele service verslechteren en kan dit gevolgen hebben voor de bezorging van e-mail voor andere klanten.

In dit artikel worden de besturingselementen en meldingen beschreven die zijn ontworpen om uitgaande spam te voorkomen en wat u kunt doen als u massamailings wilt verzenden.

## <a name="what-admins-can-do-to-control-outbound-spam"></a>Wat beheerders kunnen doen om uitgaande spam te beheren

- Ingebouwde meldingen gebruiken: wanneer een gebruiker de limieten voor het verzenden van de [service](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) of het  uitgaande [spambeleid](configure-the-outbound-spam-policy.md) overschrijdt en geen **e-mail** mag verzenden, wordt het standaardmeldingsbeleid met de naam Gebruiker beperkt tot het verzenden van e-mailmeldingen verzonden naar leden van de **groep TenantAdmins** **(Globale** beheerders). Zie De waarschuwingsinstellingen voor beperkte gebruikers controleren als u wilt configureren wie deze meldingen [nog meer ontvangt.](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users) Ook is de standaardwaarschuwingsbeleid met de  naam E-mail verzenden limiet overschreden en verdachte e-mail verzenden patronen gedetecteerd e-mailmeldingen verzenden naar leden van de **TenantAdmins** (**Globale beheerders**) groep.  Zie voor meer informatie over waarschuwingsbeleid, [Waarschuwingsbeleid in Microsoft 365](../../compliance/alert-policies.md).

- Spam-klachten van externe e-mailproviders controleren: Veel e-mailservices zoals Outlook.com, Yahoo en AOL geven een feedbacklus waarbij als een gebruiker in de service een **e-mail** van Microsoft 365 markeert als spam, het bericht wordt verpakt en naar ons wordt verzonden voor controle. Voor meer informatie over de ondersteuning van afzenders voor Outlook.com gaat u naar <https://sendersupport.olc.protection.outlook.com/pm/services.aspx> .

## <a name="how-eop-controls-outbound-spam"></a>Hoe EOP uitgaande spam controleert

- **Segregatie van uitgaand e-mailverkeer:** elk uitgaande bericht dat via de service wordt verzonden, wordt gescand op spam. Als wordt vastgesteld dat het bericht spam is, wordt het bezorgd vanuit een secundaire, minder betrouwbare _IP-adresgroep_ met de naam van de groep met een hoog risico. Zie Risicovolle [bezorgingsgroep voor](high-risk-delivery-pool-for-outbound-messages.md)uitgaande berichten voor meer informatie.

- **Onze bron-IP-adresreputatie** controleren: Microsoft 365 query's uitvoeren op verschillende IP-bloklijsten van derden. Er wordt een waarschuwing gegenereerd als een van de IP-adressen die we gebruiken voor uitgaande e-mail in deze lijsten wordt weergegeven. Met deze controle kunnen we snel reageren wanneer spam onze reputatie heeft doen verslechteren. Wanneer een waarschuwing wordt gegenereerd, hebben we interne documentatie waarin wordt beschreven hoe we onze IP-adressen kunnen verwijderen (verwijderd) uit bloklijsten.

- Accounts die te veel **spam** verzenden uitschakelen: Hoewel we uitgaande spam scheiden in de groep met hoge risico's, kunnen we niet toestaan dat een account (vaak een gekromd account) spam voor onbepaalde tijd <sup>\*</sup> verzendt. We controleren accounts die spam verzenden en wanneer ze een niet-bekendgemaakte limiet overschrijden, wordt het account geblokkeerd voor het verzenden van e-mail. Er zijn verschillende drempelwaarden voor afzonderlijke gebruikers en de hele tenant.

- Accounts die te snel te veel e-mail verzenden uitschakelen: Naast de limieten voor berichten die zijn gemarkeerd als spam, zijn er ook limieten die accounts blokkeren wanneer ze een algemene limiet voor uitgaande berichten bereiken, ongeacht de uitspraak over spamfilters op de uitgaande <sup>\*</sup> berichten. Een gekromd account kan zero-day (voorheen niet-herkende) spam verzenden die wordt gemist door het spamfilter. Omdat het lastig kan zijn om een legitieme massamailingcampagne versus een spamcampagne te identificeren, helpen deze limieten eventuele schade te minimaliseren.

<sup>\*</sup> We maken geen reclame voor de exacte limieten, zodat spammers het systeem niet kunnen gamen, zodat we de limieten zo nodig kunnen verhogen of verlagen. De limieten zijn hoog genoeg om te voorkomen dat een gemiddelde zakelijke gebruiker deze ooit overschrijdt en laag genoeg om de schade te beperken die wordt veroorzaakt door een spammer.

## <a name="recommendations-for-customers-who-want-to-send-mass-mailings-through-eop"></a>Aanbevelingen voor klanten die massamailings willen verzenden via EOP

Het is moeilijk om een evenwicht te vinden tussen klanten die een groot aantal e-mail willen verzenden versus het beschermen van de service tegen gecompromitteerde accounts en bulk-afzenders van e-mail met slechte aankooppraktijken voor geadresseerden. De kosten van een Microsoft 365 e-mailbron die op een LIJST met IP-blokkeringen van derden wordt geplaatst, is groter dan het blokkeren van een gebruiker die te veel e-mail verstuurt.

Zoals wordt beschreven in [de Exchange Online Servicebeschrijving,](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)is het gebruik van EOP voor het verzenden van bulk-e-mail geen ondersteund gebruik van de service en is deze alleen toegestaan op basis van 'best-effort'. Voor klanten die bulk-e-mail willen verzenden, raden we de volgende oplossingen aan:

- **Bulk-e-mail verzenden via on-premises e-mailservers:** Klanten onderhouden hun eigen e-mailinfrastructuur voor massamailings.

- **Een bulk-e-mailprovider** van derden gebruiken: er zijn verschillende leveranciers van bulk-e-mailoplossing van derden die u kunt gebruiken om massamailings te verzenden. Deze bedrijven hebben er belang bij om samen te werken met klanten om ervoor te zorgen dat e-mail goed wordt verzonden.

De werkgroep Messaging, Mobile, Malware Anti-Abuse (MAAWG) publiceert het lidmaatschapsrooster op <https://www.maawg.org/about/roster> . Verschillende bulk-e-mailproviders staan in de lijst en staan bekend als verantwoordelijke internetburgers.
