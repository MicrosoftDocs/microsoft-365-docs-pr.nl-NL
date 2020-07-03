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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9fa2539a-2211-41fd-85a0-bc37b9619ca4
description: Lees hoe u uw organisatie beter kunt beveiligen tegen wachtwoordaanvallen en waarom u veelgebruikte wachtwoorden moet verbieden en op risico gebaseerde meervoudige verificatie moet inschakelen.
ms.openlocfilehash: 1d6e399acb83751ec6a45eb0c811dedec394127e
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/01/2020
ms.locfileid: "45015921"
---
# <a name="password-policy-recommendations"></a>Aanbevelingen voor wachtwoordbeleid
 
As the admin of an organization, you're responsible for setting password policy for users in your organization. Setting password policy can be complicated and confusing, and this article provides recommendations to make your organization more secure against password attacks.
  
Zie [Een wachtwoordverloopbeleid instellen voor Microsoft 365](../manage/set-password-expiration-policy.md) om te bepalen hoe vaak Microsoft 365-wachtwoorden moeten verlopen in uw organisatie.

Zie de volgende [verwante artikelen](#related-articles)voor meer informatie over Microsoft 365-wachtwoorden.
  
## <a name="understanding-password-recommendations"></a>Wachtwoordaanbevelingen begrijpen

Goede wachtwoordpraktijken kunnen globaal in een aantal categorieën worden onderverdeeld:
  
- **Algemene aanvallen tegengaan** Dit omvat de keuze waar gebruikers wachtwoorden invoeren (bekende en vertrouwde apparaten met goede malwaredetectie, goedgekeurde sites) en de keuze van het wachtwoord (lengte en uniekheid).

- **Containing successful attacks** Containing successful hacker attacks is about limiting exposure to a specific service, or preventing that damage altogether, if a user's password gets stolen. For example, ensuring that a breach of your social networking credentials doesn't make your bank account vulnerable, or not letting a poorly guarded account accept reset links for an important account.

- **Understanding human nature** Many valid password practices fail in the face of natural human behaviors. Understanding human nature is critical because research shows that almost every rule you impose on your users will result in a weakening of password quality. Length requirements, special character requirements, and password change requirements all result in normalization of passwords, which makes it easier for attackers to guess or crack passwords.

## <a name="password-guidelines-for-administrators"></a>Wachtwoordrichtlijnen voor beheerders

The primary goal of a more secure password system is password diversity. You want your password policy to contain lots of different and hard to guess passwords. Here are a few recommendations for keeping your organization as secure as possible.
  
- Vereis een minimumlengte van acht tekens (langer is niet per se beter)

- Don't require character composition requirements. For example, \*&amp;(^%$

- Vereis niet dat wachtwoorden regelmatig opnieuw moeten worden ingesteld voor gebruikersaccounts

- Verbied algemene wachtwoorden om de meest kwetsbare wachtwoorden uit uw systeem te houden

- Vertel uw gebruikers dat ze hun organisatiewachtwoorden niet moeten hergebruiken voor niet-werkgerelateerde doeleinden

- Dwing registratie voor [meervoudige verificatie](../security-and-compliance/set-up-multi-factor-authentication.md) af

- Schakel risicogebaseerde meervoudige verificatie in

### <a name="password-guidance-for-your-users"></a>Wachtwoordrichtlijnen voor uw gebruikers

Here's some password guidance for users in your organization. Make sure to let your users know about these recommendations and enforce the recommended password policies at the organizational level.
  
- Gebruik geen wachtwoord dat hetzelfde of vrijwel hetzelfde is als een wachtwoord dat u op andere websites gebruikt

- Gebruik niet één woord, bijvoorbeeld **wachtwoord**, of een veelgebruikte uitdrukking zoals **ikhouvanje**

- Zorg dat wachtwoorden moeilijk te raden zijn, zelfs door degenen die u goed kennen, en gebruik dus niet de namen en verjaardagen van uw vrienden en familie, uw favoriete bands of uitdrukkingen die u vaak gebruikt

## <a name="some-common-approaches-and-their-negative-impacts"></a>Enkele algemene benaderingen en hun negatieve impacts

Hier volgen enkele van de meest gebruikte wachtwoordbeheerpraktijken, hoewel onderzoek ons waarschuwt over de negatieve impacts daarvan.
  
### <a name="password-expiration-requirements-for-users"></a>Wachtwoordverloopvereisten voor gebruikers

Password expiration requirements do more harm than good, because these requirements make users select predictable passwords, composed of sequential words and numbers which are closely related to each other. In these cases, the next password can be predicted based on the previous password. Password expiration requirements offer no containment benefits because cyber criminals almost always use credentials as soon as they compromise them.
  
### <a name="requiring-long-passwords"></a>Lange wachtwoorden vereisen

Password length requirements (greater than about 10 characters) can result in user behavior that is predictable and undesirable. For example, users who are required to have a 16-character password may choose repeating patterns like **fourfourfourfour** or **passwordpassword** that meet the character length requirement but aren't hard to guess. Additionally, length requirements increase the chances that users will adopt other insecure practices, such as writing their passwords down, re-using them, or storing them unencrypted in their documents. To encourage users to think about a unique password, we recommend keeping a reasonable 8-character minimum length requirement. 
  
### <a name="requiring-the-use-of-multiple-character-sets"></a>Het gebruik van meerdere tekensets vereisen

Password complexity requirements reduce key space and cause users to act in predictable ways, doing more harm than good. Most systems enforce some level of password complexity requirements. For example, passwords need characters from all three of the following categories:
  
- hoofdletters

- kleine letters

- niet-alfanumerieke tekens

Most people use similar patterns, for example, a capital letter in the first position, a symbol in the last, and a number in the last 2. Cyber criminals know this, so they run their dictionary attacks using the most common substitutions, "$" for "s", "@" for "a," "1" for "l". Forcing your users to choose a combination of upper, lower, digits, special characters has a negative effect. Some complexity requirements even prevent users from using secure and memorable passwords, and force them into coming up with less secure and less memorable passwords.
  
## <a name="successful-patterns"></a>Succesvolle patronen

Hier volgen enkele aanbevelingen voor het aanmoedigen van wachtwoorddiversiteit.
  
### <a name="ban-common-passwords"></a>Verbied algemene wachtwoorden

The most important password requirement you should put on your users when creating passwords is to ban the use of common passwords to reduce your organization's susceptibility to brute force password attacks. Common user passwords include, **abdcefg**, **password**, **monkey**.
  
### <a name="educate-users-to-not-re-use-organization-passwords-anywhere-else"></a>Vertel gebruikers organisatiewachtwoorden nergens anders te hergebruiken

One of the most important messages to get across to users in your organization is to not re-use their organization password anywhere else. The use of organization passwords in external websites greatly increases the likelihood that cyber criminals will compromise these passwords.
  
### <a name="enforce-multi-factor-authentication-registration"></a>Dwing registratie voor meervoudige verificatie af

Make sure your users update contact and security information, like an alternate email address, phone number, or a device registered for push notifications, so they can respond to security challenges and be notified of security events. Updated contact and security information helps users verify their identity if they ever forget their password, or if someone else tries to take over their account. It also provides an out of band notification channel in the case of security events such as login attempts or changed passwords. 
  
Zie [Meervoudige verificatie instellen](../security-and-compliance/set-up-multi-factor-authentication.md) voor meer informatie.
  
### <a name="enable-risk-based-multi-factor-authentication"></a>Schakel risicogebaseerde meervoudige verificatie in

Risicogebaseerde meervoudige verificatie verzekert dat wanneer ons systeem verdachte activiteiten detecteert, de gebruiker kan worden gecontroleerd om te verifiëren dat hij de legitieme accounteigenaar is. 
  
## <a name="want-to-know-more-recommended-reading"></a>Wilt u meer weten? Aanbevolen lectuur

- [Do Strong Web Passwords Accomplish Anything?](https://go.microsoft.com/fwlink/p/?linkid=861008)

- [Password Portfolios and the Finite-Effort User](https://go.microsoft.com/fwlink/p/?linkid=861014)

- [Preventing Weak Passwords by Reading Users' Minds](https://go.microsoft.com/fwlink/p/?linkid=861015)

- [Choosing Secure Passwords](https://go.microsoft.com/fwlink/p/?linkid=861016)

- [Time to rethink mandatory password changes](https://go.microsoft.com/fwlink/p/?linkid=861018)

- [Worst Passwords of 2015](https://go.microsoft.com/fwlink/p/?linkid=861020)

- [Bestanden van internet downloaden](https://go.microsoft.com/fwlink/p/?linkid=861029)

## <a name="related-articles"></a>Verwante artikelen

[Wachtwoorden opnieuw instellen](https://docs.microsoft.com/microsoft-365/admin/add-users/reset-passwords)

[Het wachtwoord van een gebruiker zo instellen dat het nooit verloopt](https://docs.microsoft.com/microsoft-365/admin/add-users/set-password-to-never-expire)

[Gebruikers toestaan hun eigen wachtwoord opnieuw in te stellen](https://docs.microsoft.com/microsoft-365/admin/add-users/let-users-reset-passwords)

[Het wachtwoord van een gebruiker opnieuw verzenden - Help voor beheerders](https://docs.microsoft.com/microsoft-365/admin/add-users/resend-user-password)
