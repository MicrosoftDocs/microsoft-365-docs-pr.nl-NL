---
title: Aanbevelingen voor wachtwoordbeleid
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- Adm_O365
- Adm_NonTOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9fa2539a-2211-41fd-85a0-bc37b9619ca4
description: Beveilig uw organisatie en tegen wachtwoordaanvallen en verbied veelgebruikte wachtwoorden en schakel op risico gebaseerde meervoudige verificatie in.
ms.openlocfilehash: f42905c6bf7769e558581338fd122f26d530423e
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635972"
---
# <a name="password-policy-recommendations"></a>Aanbevelingen voor wachtwoordbeleid

Als beheerder van een organisatie bent u verantwoordelijk voor het instellen van wachtwoordbeleid voor gebruikers in uw organisatie. Aangezien dit ingewikkeld en verwarrend kan zijn, biedt dit artikel aanbevelingen om uw organisatie beter te beschermen tegen wachtwoordaanvallen.
  
Zie [Een wachtwoordverloopbeleid instellen voor Microsoft 365](../manage/set-password-expiration-policy.md) om te bepalen hoe vaak Microsoft 365-wachtwoorden moeten verlopen in uw organisatie.

Voor meer informatie over Microsoft 365-wachtwoorden, zie:

[Wachtwoorden opnieuw instellen](../add-users/reset-passwords.md) (artikel)

[Het wachtwoord van een individuele gebruiker zo instellen dat het nooit verloopt](../add-users/set-password-to-never-expire.md) (artikel)

[Gebruikers toestaan hun eigen wachtwoord opnieuw in te stellen](../add-users/let-users-reset-passwords.md) (artikel)

[Het wachtwoord van een gebruiker opnieuw verzenden - Help voor beheerders](../add-users/resend-user-password.md) (artikel)
  
## <a name="understanding-password-recommendations"></a>Wachtwoordaanbevelingen begrijpen

Goede wachtwoordpraktijken kunnen globaal in een aantal categorieën worden onderverdeeld:
  
- **Algemene aanvallen tegengaan** Dit omvat de keuze waar gebruikers wachtwoorden invoeren (bekende en vertrouwde apparaten met goede malwaredetectie, goedgekeurde sites) en de keuze van het wachtwoord (lengte en uniekheid).

- **Succesvolle aanvallen beheersen** Om succesvolle hackeraanvallen te beheersen, moet u de blootstelling aan een specifieke service beperken, of dat soort schade helemaal voorkomen, als het wachtwoord van een gebruiker wordt gestolen. U doet dit bijvoorbeeld door te verzekeren dat een lek van uw sociale-netwerkgegevens uw bankrekening niet kwetsbaar maakt, of door geen koppelingen voor opnieuw instellen te accepteren voor een belangrijk account dat niet zo goed wordt beveiligd.

- **De menselijke aard begrijpen** Veel geldige wachtwoordpraktijken falen in de aanwezigheid van natuurlijk menselijk gedrag. Het  is essentieel de menselijke aard te begrijpen, want uit onderzoek blijkt dat vrijwel elke regel die u uw gebruikers oplegt in een zwakker wachtwoord resulteert. Vereisten voor lengte, speciale tekens en wachtwoordwijziging resulteren allemaal in normalisatie van wachtwoorden, waardoor aanvallers ze gemakkelijker kunnen raden of kraken.

## <a name="password-guidelines-for-administrators"></a>Wachtwoordrichtlijnen voor beheerders

Het voornaamste doel van een veiliger wachtwoordsysteem is wachtwoorddiversiteit. U wilt dat uw wachtwoordbeleid veel verschillende en moeilijk te raden wachtwoorden bevat. Hier volgen enkele aanbevelingen om uw organisatie zo veilig mogelijk te houden.
  
- Vereis een minimumlengte van acht tekens (langer is niet per se beter)

- Vereis niet wat voor soort tekens er moeten worden gebruikt, bijvoorbeeld \*&amp;(^%$

- Vereis niet dat wachtwoorden regelmatig opnieuw moeten worden ingesteld voor gebruikersaccounts

- Verbied algemene wachtwoorden om de meest kwetsbare wachtwoorden uit uw systeem te houden

- Vertel uw gebruikers dat ze hun organisatiewachtwoorden niet moeten hergebruiken voor niet-werkgerelateerde doeleinden

- Dwing registratie voor [meervoudige verificatie](../security-and-compliance/set-up-multi-factor-authentication.md) af

- Schakel risicogebaseerde meervoudige verificatie in

### <a name="password-guidance-for-your-users"></a>Wachtwoordrichtlijnen voor uw gebruikers

Hier volgen enkele wachtwoordrichtlijnen voor gebruikers in uw organisatie. Vertel uw gebruikers over deze aanbevelingen en dwing het aanbevolen wachtwoordbeleid op organisatieniveau af.
  
- Gebruik geen wachtwoord dat hetzelfde of vrijwel hetzelfde is als een wachtwoord dat u op andere websites gebruikt

- Gebruik niet één woord, bijvoorbeeld **wachtwoord**, of een veelgebruikte uitdrukking zoals **ikhouvanje**

- Zorg dat wachtwoorden moeilijk te raden zijn, zelfs door degenen die u goed kennen, en gebruik dus niet de namen en verjaardagen van uw vrienden en familie, uw favoriete bands of uitdrukkingen die u vaak gebruikt

## <a name="some-common-approaches-and-their-negative-impacts"></a>Enkele algemene benaderingen en hun negatieve impacts

Hier volgen enkele van de meest gebruikte wachtwoordbeheerpraktijken, hoewel onderzoek ons waarschuwt over de negatieve impacts daarvan.
  
### <a name="password-expiration-requirements-for-users"></a>Wachtwoordverloopvereisten voor gebruikers

Wachtwoordverloopvereisten doen meer kwaad dan goed, omdat gebruikers hierdoor voorspelbare wachtwoorden kiezen, bestaande uit opeenvolgende woorden en cijfers die nauw verwant zijn met elkaar. In deze gevallen kan het volgende wachtwoord worden voorspeld aan de hand van het vorige wachtwoord. Wachtwoordverloopvereisten bieden geen beheersingsvoordelen, omdat cybercriminelen gegevens vrijwel altijd meteen gebruiken zodra ze die te pakken hebben. Voor meer informatie, ga naar [Tijd om verplichte wachtwoordwijzigingen te herzien](https://go.microsoft.com/fwlink/p/?linkid=861018).
  
### <a name="requiring-long-passwords"></a>Lange wachtwoorden vereisen

Wachtwoordlengtevereisten (langer dan ongeveer tien tekens) kan resulteren in voorspelbaar en ongewenst gebruikersgedrag. Gebruikers die bijvoorbeeld een wachtwoord van minstens zestien tekens moeten hebben, kiezen misschien voor een herhaald patroon zoals **viervierviervier** of **wachtwoordwachtwoord**, dat wel aan de tekenlengtevereiste voldoet maar niet moeilijk te raden is. Bovendien vergroten lengtevereisten de kans dat gebruikers andere onveilige praktijken gebruiken, zoals hun wachtwoorden opschrijven, hergebruiken of onversleuteld opslaan in hun documenten. Om gebruikers aan te moedigen een uniek wachtwoord te bedenken, raden we aan een redelijke minimumlengte van acht tekens te vereisen.
  
### <a name="requiring-the-use-of-multiple-character-sets"></a>Het gebruik van meerdere tekensets vereisen

Vereisten voor wachtwoordcomplexiteit reduceren belangrijke ruimte en leiden ertoe dat gebruikers op voorspelbare manieren handelen, wat meer kwaad dan goed doet. De meeste systemen dwingen een bepaalde mate van wachtwoordcomplexiteit af. Wachtwoorden moeten bijvoorbeeld tekens uit de volgende drie categorieën bevatten:
  
- hoofdletters

- kleine letters

- niet-alfanumerieke tekens

De meeste mensen gebruiken hetzelfde soort patroon, bijvoorbeeld een hoofdletter als eerste teken, een symbool als laatste teken en een cijfer als een van de laatste twee tekens. Cybercriminelen weten dit en voeren hun woordenboekaanvallen dus uit met de meest gebruikte vervangingen, zoals "$" voor "s", "@" voor "a" en "1" voor "l". Uw gebruikers dwingen een combinatie van hoofdletters, kleine letters, cijfers en speciale tekens te kiezen heeft een negatief effect. Sommige complexiteitsvereisten voorkomen zelfs dat gebruikers veilige en gemakkelijk te onthouden wachtwoorden kunnen gebruiken, en dwingen hen minder veilige en moeilijker te onthouden wachtwoorden te verzinnen.
  
## <a name="successful-patterns"></a>Succesvolle patronen

Hier volgen enkele aanbevelingen voor het aanmoedigen van wachtwoorddiversiteit.
  
### <a name="ban-common-passwords"></a>Verbied algemene wachtwoorden

De belangrijkste wachtwoordvereiste die u uw gebruikers moet opleggen wanneer ze wachtwoorden bedenken, is het gebruik van algemene wachtwoorden te verbieden om uw organisatie zo min mogelijk bloot te stellen aan beveiligingsaanvallen via wachtwoorden. Algemene gebruikerswachtwoorden zijn onder meer **abcdefg**, **wachtwoord** en **aap**.
  
### <a name="educate-users-to-not-re-use-organization-passwords-anywhere-else"></a>Vertel gebruikers organisatiewachtwoorden nergens anders te hergebruiken

Een van de belangrijkste dingen die u gebruikers in uw organisatie moet vertellen, is hun organisatiewachtwoorden nergens anders te hergebruiken. Wanneer organisatiewachtwoorden op externe websites worden gebruikt, is de kans veel groter dat cybercriminelen deze wachtwoorden te pakken krijgen.
  
### <a name="enforce-multi-factor-authentication-registration"></a>Dwing registratie voor meervoudige verificatie af

Zorg ervoor dat uw gebruikers hun contact- en beveiligingsgegevens bijwerken, zoals een alternatief e-mailadres, een telefoonnummer of een apparaat dat is geregistreerd voor pushmeldingen, zodat ze kunnen reageren op beveiligingsvragen en op de hoogte kunnen worden gesteld van beveiligingsgebeurtenissen. Bijgewerkte contact- en beveiligingsgegevens helpen gebruikers hun identiteit te verifiëren als ze hun wachtwoord ooit vergeten of als iemand anders hun account probeert over te nemen. Het biedt ook een out-of-band meldingskanaal in het geval van beveiligingsgebeurtenissen zoals aanmeldingspogingen of gewijzigde wachtwoorden. 
  
Zie [Meervoudige verificatie instellen](../security-and-compliance/set-up-multi-factor-authentication.md) voor meer informatie.
  
### <a name="enable-risk-based-multi-factor-authentication"></a>Schakel risicogebaseerde meervoudige verificatie in

Risicogebaseerde meervoudige verificatie verzekert dat wanneer ons systeem verdachte activiteiten detecteert, de gebruiker kan worden gecontroleerd om te verifiëren dat hij de legitieme accounteigenaar is. 
  
## <a name="next-steps"></a>Volgende stappen

Wilt u meer weten over het beheren van wachtwoorden? Hier volgen enkele aanbevolen artikelen:

- [Do Strong Web Passwords Accomplish Anything?](https://go.microsoft.com/fwlink/p/?linkid=861008)

- [Password Portfolios and the Finite-Effort User](https://go.microsoft.com/fwlink/p/?linkid=861014)

- [Preventing Weak Passwords by Reading Users' Minds](https://go.microsoft.com/fwlink/p/?linkid=861015)

- [Choosing Secure Passwords](https://go.microsoft.com/fwlink/p/?linkid=861016)

- [Time to rethink mandatory password changes](https://go.microsoft.com/fwlink/p/?linkid=861018)

- [Worst Passwords of 2015](https://go.microsoft.com/fwlink/p/?linkid=861020)

## <a name="related-content"></a>Verwante inhoud

[Wachtwoorden opnieuw instellen](../add-users/reset-passwords.md) (artikel)\
[Het wachtwoord van een individuele gebruiker zo instellen dat het nooit verloopt](../add-users/set-password-to-never-expire.md) (artikel)\
[Gebruikers toestaan hun eigen wachtwoord opnieuw in te stellen](../add-users/let-users-reset-passwords.md) (artikel)\
[Het wachtwoord van een gebruiker opnieuw verzenden - Help voor beheerders](../add-users/resend-user-password.md) (artikel)
