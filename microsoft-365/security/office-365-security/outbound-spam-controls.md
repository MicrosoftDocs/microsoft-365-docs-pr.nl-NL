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
description: Beheerders kunnen meer te weten komen over de besturingselementen voor uitgaande spam in Exchange Online Protection (EOP) en wat ze moeten doen als u grote mailings moet verzenden.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6d5a82b4a2c7f94b3c5d0958abc8c4552cc04032
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150686"
---
# <a name="outbound-spam-protection-in-eop"></a>Beveiliging tegen uitgaande spam in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender voor Office 365-abonnement 1 en abonnement 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Organisaties van Exchange Online Protection (EOP) zonder Exchange Online-postvakken nemen we het beheren van uitgaande spam serieus. Een klant die bewust of per ongeluk spam van de organisatie verzendt, kan de reputatie van de hele service verslechteren en kan van invloed zijn op de bezorging van e-mail voor andere klanten.

In dit onderwerp worden besturingselementen en meldingen beschreven die zijn ontworpen om uitgaande spam te helpen voorkomen en wat u kunt doen als u massamailings moet verzenden.

## <a name="what-admins-can-do-to-control-outbound-spam"></a>Wat beheerders kunnen doen om uitgaande spam tegen te gaan

- Gebruik ingebouwde meldingen: als een gebruiker de limieten voor het verzenden van [de service](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) of het  uitgaande [spambeleid](configure-the-outbound-spam-policy.md) overschrijdt en geen e-mail meer kan verzenden, verzendt het standaardbeleid voor waarschuwingen met de naam Gebruiker dat geen e-mail kan verzenden **e-mailmeldingen** naar leden van de groep **TenantAdmins** **(globale** beheerders). Zie De instellingen voor meldingen controleren voor beperkte gebruikers als u wilt configureren wie deze meldingen [nog meer ontvangt.](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users) Bovendien zijn de standaardwaarschuwingsbeleidsregels met  de naam Verzenden per e-mail overschreden en patronen voor het verzenden van verdachte e-mailberichten gedetecteerd om e-mailmeldingen te verzenden naar leden van de groep **TenantAdmins** **(globale** beheerders).  Zie voor meer informatie over waarschuwingsbeleid, [Waarschuwingsbeleid in het beveiligings- en compliancecentrum](../../compliance/alert-policies.md).

- **Spam-klachten** van e-mailproviders van derden bekijken: Veel e-mailservices zoals Outlook.com, Yahoo en AOL geven een feedbacklus door wanneer een gebruiker in de service een e-mail van Microsoft 365 markeert als spam, wordt het bericht verpakt en voor revisie naar ons verzonden. Voor meer informatie over ondersteuning voor afzenders Outlook.com, gaat u naar <https://sendersupport.olc.protection.outlook.com/pm/services.aspx> .

## <a name="how-eop-controls-outbound-spam"></a>Hoe uitgaande spam door EOP wordt gecontroleerd

- **Scheiding van uitgaand e-mailverkeer:** elk uitgaand bericht dat via de service wordt verzonden, wordt gescand op spam. Als het bericht als spam wordt beschouwd, wordt het bezorgd via een secundaire, minder betrouwbare IP-adresgroep, de bezorgingsgroep met _hoog risico._ Zie de [bezorgingsgroep met hoog risico voor uitgaande berichten voor meer informatie.](high-risk-delivery-pool-for-outbound-messages.md)

- **Monitoring our source IP address reputation:** Microsoft 365 query's various third party IP block lists. Er wordt een waarschuwing gegenereerd als een van de IP-adressen die we gebruiken voor uitgaande e-mail in deze lijsten wordt weergegeven. Hierdoor kunnen we snel reageren wanneer spam onze reputatie heeft verslechtert. Wanneer een waarschuwing wordt gegenereerd, hebben we interne documentatie waarin wordt beschreven hoe u ervoor kunt zorgen dat IP-adressen worden verwijderd (verwijderd) uit blokkeringslijsten.

- Schakel accounts uit die te veel **spam** verzenden. Hoewel uitgaande spam wordt gefilterd in de bezorgingsgroep met hoog risico, kunnen we een account (vaak een gekromd account) niet toestaan spam voor onbepaalde tijd te <sup>\*</sup> verzenden. We controleren accounts die spam verzenden, en wanneer ze een niet-openbaar wordende limiet overschrijden, wordt het account geblokkeerd voor het verzenden van e-mail. Er zijn verschillende drempelwaarden voor afzonderlijke gebruikers en voor de hele tenant.

- Accounts die te snel te veel e-mailberichten verzenden uitschakelen: Naast de limieten voor berichten die als spam zijn gemarkeerd, zijn er ook limieten die accounts blokkeren wanneer ze een algehele limiet voor uitgaande berichten bereiken, ongeacht de spamfiltering voor de uitgaande <sup>\*</sup> berichten. Een gekromd account kan ongewenste e-mail van nul dagen (voorheen niet herkend) verzenden die door het spamfilter wordt gemist. Omdat het moeilijk kan zijn om een legitieme grootschalige mailingcampagne te identificeren versus een spamcampagne, helpen deze limieten om potentiële schade tot een minimum te beperken.

<sup>\*</sup> We adverteren de exacte limieten niet, dus spammers kunnen het systeem niet gamen en daarom kunnen we de limieten zo nodig verhogen of verlagen. De limieten zijn hoog genoeg om te voorkomen dat een gemiddelde zakelijke gebruiker deze ooit overschrijdt en zo laag dat de schade die door een spammer wordt veroorzaakt, wordt beperkt.

## <a name="recommendations-for-customers-who-want-to-send-mass-mailings-through-eop"></a>Aanbevelingen voor klanten die grote mailings willen verzenden via EOP

Het is moeilijk om een balans te vinden tussen klanten die een grote hoeveelheid e-mail willen verzenden en het beveiligen van de service tegen gekromde accounts en bulkmail afzenders met slechte aankooppraktijken voor geadresseerden. De kosten van een Microsoft 365-e-mailbron die op een lijst met IP-blokkeringen van derden wordt geplaatst, zijn hoger dan de kosten die een gebruiker blokkeren die te veel e-mail verstuurt.

Zoals wordt beschreven in de beschrijving van de [Exchange Online-service,](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)wordt het gebruik van EOP voor het verzenden van bulk-e-mail geen ondersteund gebruik van de service en is deze alleen toegestaan op best-effort basis. Voor klanten die wel bulk-e-mail willen verzenden, raden we de volgende oplossingen aan:

- **Verzend bulk-e-mail via on-premises e-mailservers:** dit betekent dat klanten hun eigen e-mailinfrastructuur voor massamailings moeten onderhouden.

- **Gebruik een externe provider voor bulk-e-mail:** er zijn verschillende providers voor bulk-e-mailoplossing van derden die u kunt gebruiken voor het verzenden van massamailings. Deze bedrijven zijn geïnteresseerd in het samenwerken met klanten om ervoor te zorgen dat e-mail goed wordt verzonden.

De groep Messaging, Mobile, Malware Anti Abuse Working Group (WGWG) publiceert het lidmaatschapsschema op <https://www.maawg.org/about/roster> . Verschillende grote e-mailproviders staan op de lijst en staan bekend als verantwoordelijke internet-burgers.
