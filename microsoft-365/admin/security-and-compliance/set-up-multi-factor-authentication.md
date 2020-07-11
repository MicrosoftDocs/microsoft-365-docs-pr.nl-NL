---
title: Meervoudige verificatie instellen voor gebruikers
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 8f0454b2-f51a-4d9c-bcde-2c48e41621c6
description: Instructies voor het instellen van meervoudige verificatie voor uw organisatie.
monikerRange: o365-worldwide
ms.openlocfilehash: 56ca51e77b2ba4fa370a2814a7be9df1393c29dc
ms.sourcegitcommit: 3951147f74510e2ead6c11ceab92854f0937426b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/08/2020
ms.locfileid: "45083536"
---
# <a name="set-up-multi-factor-authentication"></a>Meervoudige verificatie instellen
  
Gezien uw ervaring met [meervoudige verificatie (MFA) en de bijbehorende ondersteuning in Microsoft 365](multi-factor-authentication-microsoft-365.md), is het tijd om dit in te stellen en te implementeren in uw organisatie.

Controleer voordat u begint of een van de volgende situaties op u van toepassing is en voer indien nodig de bijbehorende actie uit:

- Als u Office 2013-clients op Windows-apparaten hebt, [moet u Moderne verificatie](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication) inschakelen.

- Als u adreslijstservices van derden van Active Directory Federation Services (AD FS) hebt, moet u de Azure MFA-server instellen. Raadpleeg [geavanceerde scenario's met Azure Multi-Factor Authentication en VPN-oplossingen van derden](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) voor meer informatie.

Alle andere gebruikers wordt gevraagd om indien nodig aanvullende verificatie uit te voeren. Voor meer informatie gaat u naar [tweeledige verificatiemethode en -instellingen](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-manage-settings#turn-on-two-factor-verification-prompts-on-a-trusted-device).

## <a name="step-1-decide-on-the-method-of-requiring-your-users-to-use-mfa"></a>Stap 1: bepaal hoe uw gebruikers MFA moeten gebruiken

> [!NOTE]
> U moet een algemeen beheerder zijn om MFA in te stellen of te wijzigen. Er zijn drie manieren om uw gebruikers MFA te laten gebruiken voor aanmelding. Zie [MFA-ondersteuning in Microsoft 365](multi-factor-authentication-microsoft-365.md) voor meer details hierover.

- Standaardinstellingen voor beveiliging (aanbevolen voor kleine bedrijven)

  Als u na 21 oktober 2019 uw abonnement of proefabonnement hebt afgesloten en u wordt onverwacht gevraagd om aanvullende verificatie met MFA, zijn de [standaardinstellingen voor beveiliging](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) automatisch ingeschakeld voor uw abonnement.
  
  De standaardinstellingen voor beveiliging zijn automatisch ingeschakeld voor elk nieuw abonnement op Microsoft 365. Dit betekent dat elke gebruiker MFA moet instellen en de Microsoft Authenticator-app op zijn mobiele apparaat moet installeren.

  Alle gebruikers moeten de Microsoft Authenticator-app als extra verificatiemethode gebruiken en de oude methode wordt geblokkeerd. 

- Beleid voor voorwaardelijke toegang (aanbevolen voor bedrijven)

  Gebruikers kiezen de aanvullende verificatiemethode tijdens de MFA-registratie.

- Account per gebruiker (niet aanbevolen)

  Gebruikers kiezen de aanvullende verificatiemethode tijdens de MFA-registratie.

## <a name="step-2-test-mfa-on-your-pilot-users"></a>Stap 2. MFA testen met testfasedeelnemers 

Als u een beleid voor voorwaardelijke toegang hanteert of MFA per gebruiker (niet aanbevolen), selecteert u testfasedeelnemers in uw bedrijf of organisatie om MFA-registratie en -aanmelding te testen. Bijvoorbeeld:

- Voor beleid voor voorwaardelijke toegang maakt u een testfasedeelnemersgroep aan en een beleid dat MFA vereist voor de leden van de groep en voor alle-apps. Vervolgens voegt u de accounts van de testfasedeelnemers toe aan de groep.

- Voor MFA per gebruiker schakelt u MFA voor de gebruikersaccounts van de testfasedeelnemers een voor een in.

Werk samen met de testfasedeelnemers om vragen en problemen op te lossen om een soepele implementatie in uw organisatie voor te bereiden.

## <a name="step-3-inform-your-organization-that-mfa-is-coming"></a>Stap 3. Laat uw organisatie weten dat MFA eraan komt

Gebruik e-mailmeldingen, posters op de gang, teamvergaderingen of formele training om te zorgen dat uw medewerkers begrijpen:

- waarom MFA vereist is voor aanmelding
- [hoe ze zich kunnen registreren voor de aanvullende verificatiemethode](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)
- [hoe ze zich moeten aanmelden na registratie](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)
- [hoe ze de aanvullende verificatiemethode kunnen wijzigen](https://support.microsoft.com/office/956ec8d0-7081-4518-a701-f8414cc20831)
- [hoe ze moeten omgaan met situaties als een nieuwe smartphone](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2)

Het belangrijkste is dat uw medewerkers weten ***vanaf wanneer MFA vereist is***, zodat het niet onverwachts komt.

## <a name="step-4-roll-out-the-mfa-requirement-to-your-organization-or-users"></a>Stap 4. MFA implementeren voor uw organisatie of gebruikers

Implementeer MFA voor de werknemers en niet meer voor de testfasedeelnemers op basis van de gekozen MFA-verificatiemethode.

### <a name="security-defaults"></a>Standaardinstellingen voor beveiliging

U kunt standaardinstellingen voor beveiliging in- of uitschakelen vanuit het deelvenster **Eigenschappen** voor Azure Active Directory (Azure AD) in Azure Portal.

1.  Meld u aan bij [Microsoft 365-beheercentrum](https://admin.microsoft.com) met algemeen beheerdersreferenties.
2.  Ga naar de [eigenschappenpagina van Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).
3.  Kies onderaan de pagina de optie **Standaardinstellingen voor beveiliging beheren**.
4.  Kies **Ja** als u de standaardinstellingen voor beveiliging wilt inschakelen of **Nee** om deze uit te schakelen en kies vervolgens **Opslaan**.

Als u [beleid voor voorwaardelijke toegang volgens basislijn](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection) gebruikt, gaat u als volgt te werk om de standaardinstellingen voor beveiliging te gebruiken.

1.  Ga naar de [pagina met beleidsregels voor voorwaardelijke toegang](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).
2.  Kies elk basislijnbeleid dat **Aan** staat en zet **Beleid inschakelen** **Uit**.
2.  Ga naar de [eigenschappenpagina van Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).
4.  Kies onderaan de pagina de optie **Standaardinstellingen voor beveiliging beheren**.
5.  Kies **Ja** als u de standaardinstellingen voor beveiliging wilt inschakelen of **Nee** om deze uit te schakelen en kies vervolgens **Opslaan**.

### <a name="conditional-access-policies"></a>Beleidsregels voor voorwaardelijke toegang

De juiste beleidsregels aanmaken, configureren en inschakelen voor de gebruikersgroep die zich met MFA moet aanmelden.

### <a name="per-user-mfa-not-recommended"></a>MFA per gebruiker (niet aanbevolen)

Schakel gebruikersaccounts in voor MFA in overeenstemming met uw implementatie.

### <a name="supporting-your-employees"></a>Ondersteuning voor uw werknemers

Zorg ervoor dat IT-specialisten, IT-afdeling of helpdesk snel vragen kan beantwoorden en problemen kan oplossen als uw werknemers zich registreren en gaan aanmelden met MFA.

Raadpleeg dit artikel voor [informatie over het oplossen van problemen bij het aanmelden met MFA](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2). 


