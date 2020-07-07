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
localization_priority: Normal
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
description: Meer informatie over het instellen van meerstapverificatie voor uw organisatie.
monikerRange: o365-worldwide
ms.openlocfilehash: b0fd16fc74319c88a6f91bf56ac96346915c35ac
ms.sourcegitcommit: 7c1b34205746ff0690ffc774a74bdfd434256cf5
ms.contentlocale: nl-NL
ms.lasthandoff: 07/07/2020
ms.locfileid: "45049758"
---
# <a name="set-up-multi-factor-authentication"></a>Meervoudige verificatie instellen
  
Op basis van uw begrip van [multi-factor authenticatie (MFA) en de ondersteuning ervan in Microsoft 365,](multi-factor-authentication-microsoft-365.md)is het tijd om het in te stellen en uit te rollen naar uw organisatie.

Voordat u begint, u bepalen of deze speciale voorwaarden op u van toepassing zijn en de juiste actie ondernemen:

- Als u Office 2013-clients op Windows-apparaten hebt, [schakelt u Moderne verificatie in](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication).

- Als u directoryservices van derden hebt met Active Directory Federation Services (AD FS), stelt u de Azure MFA-server in. Bekijk [geavanceerde scenario's met Azure Multi-Factor Authentication en VPN-oplossingen van derden](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) voor meer informatie.

Alle andere gebruikers wordt gevraagd om indien nodig extra verificatie uit te voeren. Ga voor meer informatie naar [de verificatiemethode en -instellingen met twee factoren.](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-manage-settings#turn-on-two-factor-verification-prompts-on-a-trusted-device)

## <a name="step-1-decide-on-the-method-of-requiring-your-users-to-use-mfa"></a>Stap 1: Bepaal de methode om uw gebruikers te verplichten MFA te gebruiken

> [!NOTE]
> U moet een globale beheerder zijn om MFA in te stellen of te wijzigen. Er zijn drie manieren om uw gebruikers te verplichten MFA te gebruiken voor aanmeldingen. Zie [MFA-ondersteuning in Microsoft 365](multi-factor-authentication-microsoft-365.md) voor de details.

- Standaardinstellingen voor beveiliging (aanbevolen voor kleine bedrijven)

  Als u uw abonnement of proefversie na 21 oktober 2019 hebt gekocht en u onverwacht wordt gevraagd om MFA, zijn [beveiligingsstandaarden](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) automatisch ingeschakeld voor uw abonnement.
  
  Bij elk nieuw Microsoft 365-abonnement zijn automatisch beveiligingsstandaarden ingeschakeld. Dit betekent dat elke gebruiker MFA moet instellen en de Microsoft Authenticator-app op zijn mobiele apparaat moet installeren.

  Alle gebruikers moeten de Microsoft Authenticator-app gebruiken omdat hun extra verificatiemethode en verouderde verificatie worden geblokkeerd. 

- Beleid voor voorwaardelijke toegang (aanbevolen voor ondernemingen)

  Gebruikers kiezen de aanvullende verificatiemethode tijdens MFA-registratie.

- Account per gebruiker (niet aanbevolen)

  Gebruikers kiezen de aanvullende verificatiemethode tijdens MFA-registratie.

## <a name="step-2-test-mfa-on-your-pilot-users"></a>Stap 2. Test MFA op uw pilootgebruikers

Als u het beleid voor voorwaardelijke toegang of MFA per gebruiker gebruikt (niet aanbevolen), selecteert u proefgebruikers in uw bedrijf of organisatie om MFA-registratie en aanmeldingen te testen. Bijvoorbeeld:

- Maak voor het beleid voor voorwaardelijke toegang een groep proefgebruikers en een beleid waarvoor MFA vereist is voor de leden van de groep en voor alle apps. Voeg vervolgens de accounts van de pilootgebruiker toe aan de groep.

- Schakel voor MFA per gebruiker MFA één keer in voor de gebruikersaccounts van uw pilootgebruikers.

Werk samen met uw proefgebruikers om vragen en problemen aan te pakken om u voor te bereiden op een soepele uitrol naar uw organisatie.

## <a name="step-3-inform-your-organization-that-mfa-is-coming"></a>Stap 3. Uw organisatie informeren dat MFA eraan komt

Gebruik e-mailmeldingen, gangposters, teamvergaderingen of formele training om ervoor te zorgen dat uw medewerkers het begrijpen:

- Waarom MFA nodig is voor aanmeldingen
- [Hoe te registreren voor hun aanvullende verificatiemethode](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)
- [Aanmelden na registratie](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)
- [Hoe de aanvullende verificatiemethode te wijzigen](https://support.microsoft.com/office/956ec8d0-7081-4518-a701-f8414cc20831)
- [Hoe om te gaan met situaties zoals een nieuwe smartphone](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2)

Het belangrijkste is dat uw medewerkers begrijpen ***wanneer de MFA-eis wordt opgelegd,*** zodat het hen niet verbaast.

## <a name="step-4-roll-out-the-mfa-requirement-to-your-organization-or-users"></a>Stap 4. De MFA-eis uitrollen naar uw organisatie of gebruikers

Op basis van de gekozen MFA-vereistemethode rolt u MFA-verificatie uit naar de werknemers buiten uw pilottesters.

### <a name="security-defaults"></a>Standaardinstellingen voor beveiliging

U schakelt beveiligingsstandaarden in of uit vanuit het deelvenster **Eigenschappen** voor Azure Active Directory (Azure AD) in de Azure-portal.

1.  Meld u aan bij het [Microsoft 365-beheercentrum](https://admin.microsoft.com) met globale beheerdersreferenties.
2.  Ga naar de [pagina Azure Active Directory - Eigenschappen](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).
3.  Kies onderaan de pagina de optie **Standaardinstellingen voor beveiliging beheren**.
4.  Kies **Ja** om beveiligingsstandaardinstellingen in te schakelen en **Nee** om beveiligingsstandaarden uit te schakelen en kies **Opslaan**.

Als u het [beleid voor voorwaardelijke toegang basislijn](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)hebt gebruikt, gaat u als u over tot het gebruik van beveiligingsstandaarden.

1.  Ga naar de [pagina Voorwaardelijke toegang - Beleidsregels](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).
2.  Kies elk basislijnbeleid dat is **ingeschakeld** en stel **Beleid inschakelen** in **op Uit**.
2.  Ga naar de [pagina Azure Active Directory - Eigenschappen](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).
4.  Kies onderaan de pagina de optie **Standaardinstellingen voor beveiliging beheren**.
5.  Kies **Ja** om beveiligingsstandaardinstellingen in te schakelen en **Nee** om beveiligingsstandaarden uit te schakelen en kies **Opslaan**.

### <a name="conditional-access-policies"></a>Beleid voor voorwaardelijke toegang

Maak, configureer en schakel het juiste beleid in dat de groep gebruikers omvat waarvoor MFA moet worden aangemeld.

### <a name="per-user-mfa-not-recommended"></a>MFA per gebruiker (niet aanbevolen)

Gebruikersaccounts inschakelen voor MFA die overeenkomt met uw implementatie.

### <a name="supporting-your-employees"></a>Ondersteuning van uw medewerkers

Terwijl uw medewerkers zich registreren en beginnen met inloggen bij MFA, zorg er dan voor dat uw IT-specialisten, IT-afdeling of helpdesk vragen kunnen beantwoorden en problemen snel kunnen oplossen.

Zie dit artikel voor [informatie over het oplossen van MFA-aanmeldingen](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2). 


