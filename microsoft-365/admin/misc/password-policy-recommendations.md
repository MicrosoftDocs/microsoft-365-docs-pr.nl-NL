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
ms.openlocfilehash: b4437f2af409fa3040894a1b0f802140df169635
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399312"
---
# <a name="password-policy-recommendations"></a><span data-ttu-id="6fa0c-103">Aanbevelingen voor wachtwoordbeleid</span><span class="sxs-lookup"><span data-stu-id="6fa0c-103">Password policy recommendations</span></span>
 
<span data-ttu-id="6fa0c-p101">Als beheerder van een organisatie bent u verantwoordelijk voor het instellen van wachtwoordbeleid voor gebruikers in uw organisatie. Aangezien dit ingewikkeld en verwarrend kan zijn, biedt dit artikel aanbevelingen om uw organisatie beter te beschermen tegen wachtwoordaanvallen.</span><span class="sxs-lookup"><span data-stu-id="6fa0c-p101">As the admin of an organization, you're responsible for setting password policy for users in your organization. Setting password policy can be complicated and confusing, and this article provides recommendations to make your organization more secure against password attacks.</span></span>
  
<span data-ttu-id="6fa0c-106">Zie [Een wachtwoordverloopbeleid instellen voor Microsoft 365](../manage/set-password-expiration-policy.md) om te bepalen hoe vaak Microsoft 365-wachtwoorden moeten verlopen in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="6fa0c-106">To determine how often Microsoft 365 passwords expire in your organization, see [Set password expiration policy for Microsoft 365](../manage/set-password-expiration-policy.md).</span></span>
  
## <a name="understanding-password-recommendations"></a><span data-ttu-id="6fa0c-107">Wachtwoordaanbevelingen begrijpen</span><span class="sxs-lookup"><span data-stu-id="6fa0c-107">Understanding password recommendations</span></span>

<span data-ttu-id="6fa0c-108">Goede wachtwoordpraktijken kunnen globaal in een aantal categorieën worden onderverdeeld:</span><span class="sxs-lookup"><span data-stu-id="6fa0c-108">Good password practices fall into a few broad categories:</span></span>
  
- <span data-ttu-id="6fa0c-109">**Algemene aanvallen tegengaan** Dit omvat de keuze waar gebruikers wachtwoorden invoeren (bekende en vertrouwde apparaten met goede malwaredetectie, goedgekeurde sites) en de keuze van het wachtwoord (lengte en uniekheid).</span><span class="sxs-lookup"><span data-stu-id="6fa0c-109">**Resisting common attacks** This involves the choice of where users enter passwords (known and trusted devices with good malware detection, validated sites), and the choice of what password to choose (length and uniqueness).</span></span>

- <span data-ttu-id="6fa0c-p102">**Succesvolle aanvallen beheersen** Om succesvolle hackeraanvallen te beheersen, moet u de blootstelling aan een specifieke service beperken, of dat soort schade helemaal voorkomen, als het wachtwoord van een gebruiker wordt gestolen. U doet dit bijvoorbeeld door te verzekeren dat een lek van uw sociale-netwerkgegevens uw bankrekening niet kwetsbaar maakt, of door geen koppelingen voor opnieuw instellen te accepteren voor een belangrijk account dat niet zo goed wordt beveiligd.</span><span class="sxs-lookup"><span data-stu-id="6fa0c-p102">**Containing successful attacks** Containing successful hacker attacks is about limiting exposure to a specific service, or preventing that damage altogether, if a user's password gets stolen. For example, ensuring that a breach of your social networking credentials doesn't make your bank account vulnerable, or not letting a poorly guarded account accept reset links for an important account.</span></span>

- <span data-ttu-id="6fa0c-p103">**De menselijke aard begrijpen** Veel geldige wachtwoordpraktijken falen in de aanwezigheid van natuurlijk menselijk gedrag. Het  is essentieel de menselijke aard te begrijpen, want uit onderzoek blijkt dat vrijwel elke regel die u uw gebruikers oplegt in een zwakker wachtwoord resulteert. Vereisten voor lengte, speciale tekens en wachtwoordwijziging resulteren allemaal in normalisatie van wachtwoorden, waardoor aanvallers ze gemakkelijker kunnen raden of kraken.</span><span class="sxs-lookup"><span data-stu-id="6fa0c-p103">**Understanding human nature** Many valid password practices fail in the face of natural human behaviors. Understanding human nature is critical because research shows that almost every rule you impose on your users will result in a weakening of password quality. Length requirements, special character requirements, and password change requirements all result in normalization of passwords, which makes it easier for attackers to guess or crack passwords.</span></span>

## <a name="password-guidelines-for-administrators"></a><span data-ttu-id="6fa0c-115">Wachtwoordrichtlijnen voor beheerders</span><span class="sxs-lookup"><span data-stu-id="6fa0c-115">Password guidelines for administrators</span></span>

<span data-ttu-id="6fa0c-p104">Het voornaamste doel van een veiliger wachtwoordsysteem is wachtwoorddiversiteit. U wilt dat uw wachtwoordbeleid veel verschillende en moeilijk te raden wachtwoorden bevat. Hier volgen enkele aanbevelingen om uw organisatie zo veilig mogelijk te houden.</span><span class="sxs-lookup"><span data-stu-id="6fa0c-p104">The primary goal of a more secure password system is password diversity. You want your password policy to contain lots of different and hard to guess passwords. Here are a few recommendations for keeping your organization as secure as possible.</span></span>
  
- <span data-ttu-id="6fa0c-119">Vereis een minimumlengte van acht tekens (langer is niet per se beter)</span><span class="sxs-lookup"><span data-stu-id="6fa0c-119">Maintain an 8-character minimum length requirement (longer isn't necessarily better)</span></span>

- <span data-ttu-id="6fa0c-p105">Vereis niet wat voor soort tekens er moeten worden gebruikt, bijvoorbeeld \*&amp;(^%$</span><span class="sxs-lookup"><span data-stu-id="6fa0c-p105">Don't require character composition requirements. For example, \*&amp;(^%$</span></span>

- <span data-ttu-id="6fa0c-122">Vereis niet dat wachtwoorden regelmatig opnieuw moeten worden ingesteld voor gebruikersaccounts</span><span class="sxs-lookup"><span data-stu-id="6fa0c-122">Don't require mandatory periodic password resets for user accounts</span></span>

- <span data-ttu-id="6fa0c-123">Verbied algemene wachtwoorden om de meest kwetsbare wachtwoorden uit uw systeem te houden</span><span class="sxs-lookup"><span data-stu-id="6fa0c-123">Ban common passwords, to keep the most vulnerable passwords out of your system</span></span>

- <span data-ttu-id="6fa0c-124">Vertel uw gebruikers dat ze hun organisatiewachtwoorden niet moeten hergebruiken voor niet-werkgerelateerde doeleinden</span><span class="sxs-lookup"><span data-stu-id="6fa0c-124">Educate your users to not re-use their organization passwords for non-work related purposes</span></span>

- <span data-ttu-id="6fa0c-125">Dwing registratie voor [meervoudige verificatie](../security-and-compliance/set-up-multi-factor-authentication.md) af</span><span class="sxs-lookup"><span data-stu-id="6fa0c-125">Enforce registration for [multi-factor authentication](../security-and-compliance/set-up-multi-factor-authentication.md)</span></span>

- <span data-ttu-id="6fa0c-126">Schakel risicogebaseerde meervoudige verificatie in</span><span class="sxs-lookup"><span data-stu-id="6fa0c-126">Enable risk-based multi-factor authentication challenges</span></span>

### <a name="password-guidance-for-your-users"></a><span data-ttu-id="6fa0c-127">Wachtwoordrichtlijnen voor uw gebruikers</span><span class="sxs-lookup"><span data-stu-id="6fa0c-127">Password guidance for your users</span></span>

<span data-ttu-id="6fa0c-p106">Hier volgen enkele wachtwoordrichtlijnen voor gebruikers in uw organisatie. Vertel uw gebruikers over deze aanbevelingen en dwing het aanbevolen wachtwoordbeleid op organisatieniveau af.</span><span class="sxs-lookup"><span data-stu-id="6fa0c-p106">Here's some password guidance for users in your organization. Make sure to let your users know about these recommendations and enforce the recommended password policies at the organizational level.</span></span>
  
- <span data-ttu-id="6fa0c-130">Gebruik geen wachtwoord dat hetzelfde of vrijwel hetzelfde is als een wachtwoord dat u op andere websites gebruikt</span><span class="sxs-lookup"><span data-stu-id="6fa0c-130">Don't use a password that is the same or similar to one you use on any other websites</span></span>

- <span data-ttu-id="6fa0c-131">Gebruik niet één woord, bijvoorbeeld **wachtwoord**, of een veelgebruikte uitdrukking zoals **ikhouvanje**</span><span class="sxs-lookup"><span data-stu-id="6fa0c-131">Don't use a single word, for example, **password**, or a commonly-used phrase like **Iloveyou**</span></span>

- <span data-ttu-id="6fa0c-132">Zorg dat wachtwoorden moeilijk te raden zijn, zelfs door degenen die u goed kennen, en gebruik dus niet de namen en verjaardagen van uw vrienden en familie, uw favoriete bands of uitdrukkingen die u vaak gebruikt</span><span class="sxs-lookup"><span data-stu-id="6fa0c-132">Make passwords hard to guess, even by those who know a lot about you, such as the names and birthdays of your friends and family, your favorite bands, and phrases you like to use</span></span>

## <a name="some-common-approaches-and-their-negative-impacts"></a><span data-ttu-id="6fa0c-133">Enkele algemene benaderingen en hun negatieve impacts</span><span class="sxs-lookup"><span data-stu-id="6fa0c-133">Some common approaches and their negative impacts</span></span>

<span data-ttu-id="6fa0c-134">Hier volgen enkele van de meest gebruikte wachtwoordbeheerpraktijken, hoewel onderzoek ons waarschuwt over de negatieve impacts daarvan.</span><span class="sxs-lookup"><span data-stu-id="6fa0c-134">These are some of the most commonly used password management practices, but research warns us about the negative impacts of them.</span></span>
  
### <a name="password-expiration-requirements-for-users"></a><span data-ttu-id="6fa0c-135">Wachtwoordverloopvereisten voor gebruikers</span><span class="sxs-lookup"><span data-stu-id="6fa0c-135">Password expiration requirements for users</span></span>

<span data-ttu-id="6fa0c-p107">Wachtwoordverloopvereisten doen meer kwaad dan goed, omdat gebruikers hierdoor voorspelbare wachtwoorden kiezen, bestaande uit opeenvolgende woorden en cijfers die nauw verwant zijn met elkaar. In deze gevallen kan het volgende wachtwoord worden voorspeld aan de hand van het vorige wachtwoord. Wachtwoordverloopvereisten bieden geen beheersingsvoordelen, omdat cybercriminelen gegevens vrijwel altijd meteen gebruiken zodra ze die te pakken hebben.</span><span class="sxs-lookup"><span data-stu-id="6fa0c-p107">Password expiration requirements do more harm than good, because these requirements make users select predictable passwords, composed of sequential words and numbers which are closely related to each other. In these cases, the next password can be predicted based on the previous password. Password expiration requirements offer no containment benefits because cyber criminals almost always use credentials as soon as they compromise them.</span></span>
  
### <a name="requiring-long-passwords"></a><span data-ttu-id="6fa0c-139">Lange wachtwoorden vereisen</span><span class="sxs-lookup"><span data-stu-id="6fa0c-139">Requiring long passwords</span></span>

<span data-ttu-id="6fa0c-p108">Wachtwoordlengtevereisten (langer dan ongeveer tien tekens) kan resulteren in voorspelbaar en ongewenst gebruikersgedrag. Gebruikers die bijvoorbeeld een wachtwoord van minstens zestien tekens moeten hebben, kiezen misschien voor een herhaald patroon zoals **viervierviervier** of **wachtwoordwachtwoord**, dat wel aan de tekenlengtevereiste voldoet maar niet moeilijk te raden is. Bovendien vergroten lengtevereisten de kans dat gebruikers andere onveilige praktijken gebruiken, zoals hun wachtwoorden opschrijven, hergebruiken of onversleuteld opslaan in hun documenten. Om gebruikers aan te moedigen een uniek wachtwoord te bedenken, raden we aan een redelijke minimumlengte van acht tekens te vereisen.</span><span class="sxs-lookup"><span data-stu-id="6fa0c-p108">Password length requirements (greater than about 10 characters) can result in user behavior that is predictable and undesirable. For example, users who are required to have a 16-character password may choose repeating patterns like **fourfourfourfour** or **passwordpassword** that meet the character length requirement but aren't hard to guess. Additionally, length requirements increase the chances that users will adopt other insecure practices, such as writing their passwords down, re-using them, or storing them unencrypted in their documents. To encourage users to think about a unique password, we recommend keeping a reasonable 8-character minimum length requirement.</span></span> 
  
### <a name="requiring-the-use-of-multiple-character-sets"></a><span data-ttu-id="6fa0c-144">Het gebruik van meerdere tekensets vereisen</span><span class="sxs-lookup"><span data-stu-id="6fa0c-144">Requiring the use of multiple character sets</span></span>

<span data-ttu-id="6fa0c-p109">Vereisten voor wachtwoordcomplexiteit reduceren belangrijke ruimte en leiden ertoe dat gebruikers op voorspelbare manieren handelen, wat meer kwaad dan goed doet. De meeste systemen dwingen een bepaalde mate van wachtwoordcomplexiteit af. Wachtwoorden moeten bijvoorbeeld tekens uit de volgende drie categorieën bevatten:</span><span class="sxs-lookup"><span data-stu-id="6fa0c-p109">Password complexity requirements reduce key space and cause users to act in predictable ways, doing more harm than good. Most systems enforce some level of password complexity requirements. For example, passwords need characters from all three of the following categories:</span></span>
  
- <span data-ttu-id="6fa0c-148">hoofdletters</span><span class="sxs-lookup"><span data-stu-id="6fa0c-148">uppercase characters</span></span>

- <span data-ttu-id="6fa0c-149">kleine letters</span><span class="sxs-lookup"><span data-stu-id="6fa0c-149">lowercase characters</span></span>

- <span data-ttu-id="6fa0c-150">niet-alfanumerieke tekens</span><span class="sxs-lookup"><span data-stu-id="6fa0c-150">non-alphanumeric characters</span></span>

<span data-ttu-id="6fa0c-p110">De meeste mensen gebruiken hetzelfde soort patroon, bijvoorbeeld een hoofdletter als eerste teken, een symbool als laatste teken en een cijfer als een van de laatste twee tekens. Cybercriminelen weten dit en voeren hun woordenboekaanvallen dus uit met de meest gebruikte vervangingen, zoals "$" voor "s", "@" voor "a" en "1" voor "l". Uw gebruikers dwingen een combinatie van hoofdletters, kleine letters, cijfers en speciale tekens te kiezen heeft een negatief effect. Sommige complexiteitsvereisten voorkomen zelfs dat gebruikers veilige en gemakkelijk te onthouden wachtwoorden kunnen gebruiken, en dwingen hen minder veilige en moeilijker te onthouden wachtwoorden te verzinnen.</span><span class="sxs-lookup"><span data-stu-id="6fa0c-p110">Most people use similar patterns, for example, a capital letter in the first position, a symbol in the last, and a number in the last 2. Cyber criminals know this, so they run their dictionary attacks using the most common substitutions, "$" for "s", "@" for "a," "1" for "l". Forcing your users to choose a combination of upper, lower, digits, special characters has a negative effect. Some complexity requirements even prevent users from using secure and memorable passwords, and force them into coming up with less secure and less memorable passwords.</span></span>
  
## <a name="successful-patterns"></a><span data-ttu-id="6fa0c-155">Succesvolle patronen</span><span class="sxs-lookup"><span data-stu-id="6fa0c-155">Successful Patterns</span></span>

<span data-ttu-id="6fa0c-156">Hier volgen enkele aanbevelingen voor het aanmoedigen van wachtwoorddiversiteit.</span><span class="sxs-lookup"><span data-stu-id="6fa0c-156">In contrast, here are some recommendations in encouraging password diversity.</span></span>
  
### <a name="ban-common-passwords"></a><span data-ttu-id="6fa0c-157">Verbied algemene wachtwoorden</span><span class="sxs-lookup"><span data-stu-id="6fa0c-157">Ban common passwords</span></span>

<span data-ttu-id="6fa0c-p111">De belangrijkste wachtwoordvereiste die u uw gebruikers moet opleggen wanneer ze wachtwoorden bedenken, is het gebruik van algemene wachtwoorden te verbieden om uw organisatie zo min mogelijk bloot te stellen aan wrede wachtwoordaanvallen. Algemene gebruikerswachtwoorden zijn onder meer **abcdefg**, **wachtwoord** en **aap**.</span><span class="sxs-lookup"><span data-stu-id="6fa0c-p111">The most important password requirement you should put on your users when creating passwords is to ban the use of common passwords to reduce your organization's susceptibility to brute force password attacks. Common user passwords include, **abdcefg**, **password**, **monkey**.</span></span>
  
### <a name="educate-users-to-not-re-use-organization-passwords-anywhere-else"></a><span data-ttu-id="6fa0c-160">Vertel gebruikers organisatiewachtwoorden nergens anders te hergebruiken</span><span class="sxs-lookup"><span data-stu-id="6fa0c-160">Educate users to not re-use organization passwords anywhere else</span></span>

<span data-ttu-id="6fa0c-p112">Een van de belangrijkste dingen die u gebruikers in uw organisatie moet vertellen, is hun organisatiewachtwoorden nergens anders te hergebruiken. Wanneer organisatiewachtwoorden op externe websites worden gebruikt, is de kans veel groter dat cybercriminelen deze wachtwoorden te pakken krijgen.</span><span class="sxs-lookup"><span data-stu-id="6fa0c-p112">One of the most important messages to get across to users in your organization is to not re-use their organization password anywhere else. The use of organization passwords in external websites greatly increases the likelihood that cyber criminals will compromise these passwords.</span></span>
  
### <a name="enforce-multi-factor-authentication-registration"></a><span data-ttu-id="6fa0c-163">Dwing registratie voor meervoudige verificatie af</span><span class="sxs-lookup"><span data-stu-id="6fa0c-163">Enforce Multi-Factor Authentication registration</span></span>

<span data-ttu-id="6fa0c-p113">Zorg ervoor dat uw gebruikers hun contact- en beveiligingsgegevens bijwerken, zoals een alternatief e-mailadres, een telefoonnummer of een apparaat dat is geregistreerd voor pushmeldingen, zodat ze kunnen reageren op beveiligingsvragen en op de hoogte kunnen worden gesteld van beveiligingsgebeurtenissen. Bijgewerkte contact- en beveiligingsgegevens helpen gebruikers hun identiteit te verifiëren als ze hun wachtwoord ooit vergeten of als iemand anders hun account probeert over te nemen. Het biedt ook een out-of-band meldingskanaal in het geval van beveiligingsgebeurtenissen zoals aanmeldingspogingen of gewijzigde wachtwoorden.</span><span class="sxs-lookup"><span data-stu-id="6fa0c-p113">Make sure your users update contact and security information, like an alternate email address, phone number, or a device registered for push notifications, so they can respond to security challenges and be notified of security events. Updated contact and security information helps users verify their identity if they ever forget their password, or if someone else tries to take over their account. It also provides an out of band notification channel in the case of security events such as login attempts or changed passwords.</span></span> 
  
<span data-ttu-id="6fa0c-167">Zie [Meervoudige verificatie instellen](../security-and-compliance/set-up-multi-factor-authentication.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="6fa0c-167">To learn more, see [Set up multi-factor authentication](../security-and-compliance/set-up-multi-factor-authentication.md).</span></span>
  
### <a name="enable-risk-based-multi-factor-authentication"></a><span data-ttu-id="6fa0c-168">Schakel risicogebaseerde meervoudige verificatie in</span><span class="sxs-lookup"><span data-stu-id="6fa0c-168">Enable risk-based multi-factor authentication</span></span>

<span data-ttu-id="6fa0c-169">Risicogebaseerde meervoudige verificatie verzekert dat wanneer ons systeem verdachte activiteiten detecteert, de gebruiker kan worden gecontroleerd om te verifiëren dat hij de legitieme accounteigenaar is.</span><span class="sxs-lookup"><span data-stu-id="6fa0c-169">Risk-based multi-factor authentication ensures that when our system detects suspicious activity, it can challenge the user to ensure that they are the legitimate account owner.</span></span> 
  
## <a name="want-to-know-more-recommended-reading"></a><span data-ttu-id="6fa0c-170">Wilt u meer weten?</span><span class="sxs-lookup"><span data-stu-id="6fa0c-170">Want to know more?</span></span> <span data-ttu-id="6fa0c-171">Aanbevolen lectuur</span><span class="sxs-lookup"><span data-stu-id="6fa0c-171">Recommended reading</span></span>

- [<span data-ttu-id="6fa0c-172">Do Strong Web Passwords Accomplish Anything?</span><span class="sxs-lookup"><span data-stu-id="6fa0c-172">Do Strong Web Passwords Accomplish Anything?</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861008)

- [<span data-ttu-id="6fa0c-173">Password Portfolios and the Finite-Effort User</span><span class="sxs-lookup"><span data-stu-id="6fa0c-173">Password Portfolios and the Finite-Effort User</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861014)

- [<span data-ttu-id="6fa0c-174">Preventing Weak Passwords by Reading Users' Minds</span><span class="sxs-lookup"><span data-stu-id="6fa0c-174">Preventing Weak Passwords by Reading Users' Minds</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861015)

- [<span data-ttu-id="6fa0c-175">Choosing Secure Passwords</span><span class="sxs-lookup"><span data-stu-id="6fa0c-175">Choosing Secure Passwords</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861016)

- [<span data-ttu-id="6fa0c-176">Time to rethink mandatory password changes</span><span class="sxs-lookup"><span data-stu-id="6fa0c-176">Time to rethink mandatory password changes</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861018)

- [<span data-ttu-id="6fa0c-177">Worst Passwords of 2015</span><span class="sxs-lookup"><span data-stu-id="6fa0c-177">Worst Passwords of 2015</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861020)

- [<span data-ttu-id="6fa0c-178">Bestanden van internet downloaden</span><span class="sxs-lookup"><span data-stu-id="6fa0c-178">Download files from the web</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861029)
