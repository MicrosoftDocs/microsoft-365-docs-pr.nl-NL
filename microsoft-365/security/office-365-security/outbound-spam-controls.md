---
title: Uitgaande spam beheren in Office 365
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
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
description: Als uw organisatie veel bulke-mail verzendt die is gemarkeerd als spam, u worden geblokkeerd voor het verzenden van e-mail met Office 365. Lees dit artikel voor meer informatie over waarom dit gebeurt en wat je eraan doen.
ms.openlocfilehash: e1b1e0f56398db774a9aabc56cdcde52ad17791a
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "42812429"
---
# <a name="control-outbound-spam-in-office-365"></a>Uitgaande spam beheren in Office 365

We nemen het beheer van uitgaande spam serieus omdat de onze een gedeelde service is.  Er zijn veel klanten achter een gedeelde pool van bronnen, waar als een klant stuurt uitgaande spam, het kan degraderen de uitgaande IP-reputatie van de dienst en beïnvloedt de succesvolle deliverability van e-mail voor andere klanten.

> [!IMPORTANT]
> De melding voor wanneer een afzender is beperkt, maakt nu deel uit van het waarschuwingsplatform Security & Compliance Center (SCC). In plaats van onderstaande methoden te gebruiken om meldingen te verzenden, is de lijst met gebruikers om te waarschuwen te vinden in de gebruiker die is beperkt voor het **verzenden van e-mailwaarschuwing.** Gebruik de [pagina Waarschuwingsbeleid](https://sip.protection.office.com/alertpolicies) in het Security & Compliance Center om de waarschuwing te configureren, omdat de eerdere methode in de toekomst wordt verwijderd. Lees meer over de nieuwe [verwijderen van een gebruiker uit de portal Beperkte Gebruikers na het verzenden van spam-e-mail."](removing-user-from-restricted-users-portal-after-spam.md)

## <a name="what-admins-can-do-to-control-outbound-spam"></a>Wat beheerders kunnen doen om uitgaande spam te beheren

- **Meldingen inschakelen wanneer een account spam verzendt of afsluit:** beheerders kunnen bcc'ed krijgen wanneer een bericht is gemarkeerd als uitgaande spam en via de groep Hoog risico wordt verzonden. Door dit postvak te controleren, kan een beheerder detecteren of ze een gecompromitteerd account in hun netwerk hebben of dat het spamfilter per ongeluk zijn e-mail als spam markeert. Meer informatie over het instellen van het uitgaande spambeleid vindt [u hier.](configure-the-outbound-spam-policy.md)

- **Controleer handmatig spamklachten van externe e-mailproviders**: Veel e-mailservices van derden, zoals Outlook.com, Yahoo en AOL, bieden een feedbackloop waarbij als een gebruiker in hun service een e-mail van onze service markeert als spam, het bericht wordt verpakt en naar ons wordt teruggestuurd voor beoordeling. Klik [hier](https://sendersupport.olc.protection.outlook.com/pm/services.aspx)voor meer informatie over de ondersteuning van de afzender voor Outlook.com.

## <a name="what-eop-does-to-control-outbound-spam"></a>Wat EOP doet om uitgaande spam te controleren

1. **Segregatie van uitgaand verkeer in afzonderlijke pools van IP's**: Elk bericht dat klanten via de service uitgaan, wordt gescand op spam. Als het bericht spam is, wordt het doorgestuurd via de groep High Risk Delivery. Deze IP-groep bevat niet-leverbare statusmeldingen en spam. Levering aan de beoogde ontvanger is niet gegarandeerd, omdat veel derden geen e-mail accepteren omdat de kwaliteit van e-mail die het uitzendt.

   Het splitsen van het verkeer op deze manier zorgt ervoor dat de lagere kwaliteit e-mail (spam, backscatter NDR's) niet slepen naar beneden de reputatie van de reguliere uitgaande e-mail pools. De hoog risico zwembad heeft meestal een lage reputatie bij veel ontvangers rond het internet, hoewel dit niet universeel is.

2. **Monitoring van IP-reputatie**: Office 365 bevraagt verschillende IP-blocklists van derden en genereert waarschuwingen als een van onze uitgaande IP's erop staat. Dit stelt ons in staat om snel te reageren wanneer spam heeft geleid tot onze reputatie te degraderen. Wanneer een waarschuwing wordt gegenereerd, hebben we interne documentatie die aandeed welke stappen moeten worden genomen om te worden verwijderd.

3. **Het uitschakelen van beledigende accounts wanneer ze te veel e-mail verzenden gemarkeerd als spam:** Hoewel we onze spam en niet-spam scheiden in twee afzonderlijke uitgaande IP-pools, kunnen de e-mailaccounts geen spam voor onbepaalde tijd verzenden. We controleren welke accounts spam verzenden en als deze een geheime limiet overschrijdt, wordt het account geblokkeerd voor het verzenden van spam.

   Een enkel bericht gemarkeerd als spam kan een verkeerde classificatie door de spam-engine en ook wel bekend als een vals positief. We sturen het door de High Risk pool om het een kans te geven om uit te gaan; Echter, een groot aantal berichten in een kort tijdsbestek is indicatief voor een probleem en wanneer dat gebeurt, blokkeren we het account van het verzenden van meer e-mail. Er zijn verschillende drempelwaarden die bestaan voor individuele e-mailaccounts en in totaal voor de hele tenant.

4. **Uitschakelen van beledigende accounts wanneer ze te veel e-mail verzenden in een te kort tijdsbestek**: Naast de bovenstaande limieten die zoeken naar een deel van de berichten gemarkeerd als spam, zijn er ook limieten die accounts blokkeren wanneer ze een algemene limiet bereiken, ongeacht of de berichten zijn gemarkeerd als spam. De reden dat deze limiet bestaat is omdat een gecompromitteerd account zero-day spam kan verzenden die wordt gemist door het spamfilter. Omdat het moeilijk, zo niet onmogelijk is om soms het verschil te vertellen tussen een legitieme massamailingcampagne en een massale spamcampagne, worden deze limieten geactiveerd om eventuele schade te beperken.

> [!NOTE]
> Voor zowel #3 als #4 adverteren we niet de exacte limieten om te voorkomen dat spammers het systeem gamen en ervoor zorgen dat we de limieten kunnen wijzigen wanneer dat nodig is. De limieten zijn hoog genoeg, zodat een gemiddelde zakelijke gebruiker nooit zal raken en laag genoeg dat het de meeste van de schade een spammer kan doen bevat.

## <a name="recommended-workarounds-for-customers-who-want-to-send-outbound-a-lot-of-email-through-eop"></a>Aanbevolen oplossingen voor klanten die veel e-mail via EOP willen verzenden

Het is moeilijk om een evenwicht te vinden tussen klanten die een grote hoeveelheid e-mail willen verzenden versus het beschermen van de service tegen gecompromitteerde accounts en bulke-mailers met slechte list acquisition praktijken. Nogmaals, de kosten van een uitgaande IP landing op een 3rd party blocklist is hoger dan het blokkeren van een klant van het verzenden van uitgaande e-mail. Zoals beschreven in de Beschrijving van de [Exchange Online-service,](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)is het gebruik van EOP om bulke-mail te verzenden geen ondersteund gebruik van de service en is het alleen toegestaan op basis van "best-effort". Voor klanten die bulke-mail wel willen verzenden, raden we het volgende aan:

1. **Stuur de bulke-mail via zijn eigen on-premises mailservers**: Dit betekent dat de klant zijn eigen e-mailinfrastructuur moet onderhouden voor dit type e-mail.

2. **Gebruik een 3rd party bulk e-mailer om de massa communicatie te sturen:** Er zijn verschillende 3rd party bulk e-mailers wiens enige bedrijf is het verzenden van bulk e-mail. Ze kunnen samenwerken met klanten om ervoor te zorgen dat ze goede e-mailpraktijken hebben en ze hebben middelen die zijn gewijd aan het afdwingen ervan.

De Messaging, Mobile, Malware Anti-Abuse Working Group (MAAWG) publiceert haar lidmaatschap rooster [hier](https://www.maawg.org/about/roster). Verschillende bulk e-mail providers zijn op de lijst en staan bekend als verantwoordelijke internetburgers.

## <a name="for-more-information"></a>Voor meer informatie

[Voorbeeldmelding wanneer een afzender wordt geblokkeerd bij het verzenden van uitgaande spam](sample-notification-when-a-sender-is-blocked-sending-outbound-spam.md)

[Office 365 email anti-spam protection](anti-spam-protection.md)

[Bescherming tegen spoofing in Office 365](anti-spoofing-protection.md)

[Vertrouwensniveaus voor spam](spam-confidence-levels.md)
