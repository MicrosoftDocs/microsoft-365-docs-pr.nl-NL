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
description: Meer informatie over het instellen van multi-factor authenticatie voor uw organisatie.
monikerRange: o365-worldwide
ms.openlocfilehash: 2b4ac2b5950d2641254742e03f054f3e4c886833
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399120"
---
# <a name="set-up-multi-factor-authentication"></a>Meervoudige verificatie instellen
  
Op basis van uw kennis van [multi-factor authenticatie (MFA) en de ondersteuning ervan in Microsoft 365,](multi-factor-authentication-microsoft-365.md)is het tijd om het in te stellen en uit te rollen naar uw organisatie.

Bepaal voordat u begint of deze speciale voorwaarden op u van toepassing zijn en onderneem de juiste actie:

- Als u Office 2013-clients op Windows-apparaten hebt, [schakelt u Moderne verificatie in.](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication)

- Als u directoryservices van derden hebt met Active Directory Federation Services (AD FS), stelt u de Azure MFA-server in. Bekijk [geavanceerde scenario's met Azure Multi-Factor Authentication en VPN-oplossingen van derden](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) voor meer informatie.

## <a name="step-1-decide-on-the-method-of-requiring-your-users-to-use-mfa"></a>Stap 1: Bepaal de methode om uw gebruikers MFA te verplichten

Er zijn drie manieren om uw gebruikers te verplichten MFA te gebruiken voor aanmeldingen. Zie [MFA-ondersteuning in Microsoft 365](multi-factor-authentication-microsoft-365.md) voor de details.

- Beveiligingsstandaards (aanbevolen voor kleine bedrijven)

  Als u uw abonnement of proefversie na 21 oktober 2019 hebt gekocht en u onverwacht wordt gevraagd voor MFA, zijn [beveiligingsstandaards](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) automatisch ingeschakeld voor uw abonnement.
  
  Bij elk nieuw Microsoft 365-abonnement is automatisch beveiligingsstandaards ingeschakeld. Dit betekent dat elke gebruiker MFA moet instellen en de Microsoft Authenticator-app op zijn mobiele apparaat moet installeren.

  Alle gebruikers moeten de Microsoft Authenticator-app gebruiken omdat hun aanvullende verificatiemethode en verouderde verificatie worden geblokkeerd. 

- Beleid voor voorwaardelijke toegang (aanbevolen voor ondernemingen)

  Gebruikers kiezen de aanvullende verificatiemethode tijdens mfa-registratie.

- Account per gebruiker (niet aanbevolen)

  Gebruikers kiezen de aanvullende verificatiemethode tijdens mfa-registratie.

## <a name="step-2-test-mfa-on-your-pilot-users"></a>Stap 2. MFA testen op uw pilotgebruikers

Als u beleid voor voorwaardelijke toegang of MFA per gebruiker gebruikt (niet aanbevolen), selecteert u pilotgebruikers in uw bedrijf of organisatie om MFA-registratie en aanmeldingen te testen. Bijvoorbeeld:

- Maak voor beleid voor voorwaardelijke toegang een groep pilotgebruikers en een beleid waarvoor MFA vereist is voor de leden van de groep en voor alle apps. Voeg vervolgens de accounts van de pilootgebruiker toe aan de groep.

- Schakel MFA voor de gebruikersaccounts van uw pilotgebruikers één keer in.

Werk samen met uw pilootgebruikers om vragen en problemen aan te pakken om zich voor te bereiden op een soepele uitrol naar uw organisatie.

## <a name="step-3-inform-your-organization-that-mfa-is-coming"></a>Stap 3. Informeer uw organisatie dat MFA eraan komt

Gebruik e-mailmeldingen, gangposters, teamvergaderingen of formele training om ervoor te zorgen dat uw medewerkers het inzicht krijgen:

- Waarom MFA nodig is voor aanmeldingen
- [Registreren voor hun aanvullende verificatiemethode](https://support.office.com/article/set-up-your-microsoft-365-sign-in-for-multi-factor-authentication-ace1d096-61e5-449b-a875-58eb3d74de14?ui=en-US&rs=en-001&ad=US)
- [Aanmelden na registratie](https://support.office.com/article/sign-in-to-microsoft-365-with-multi-factor-authentication-2b856342-170a-438e-9a4f-3c092394d3cb)
- [Hun aanvullende verificatiemethode wijzigen](https://support.office.com/article/change-how-you-do-additional-verification-956ec8d0-7081-4518-a701-f8414cc20831)
- [Hoe om te gaan met situaties zoals een nieuwe smartphone](https://support.office.com/article/fix-common-problems-with-multi-factor-authentication-6951be76-af50-49a4-847f-21391eaa59f2)

Het belangrijkste is, zorg ervoor dat uw medewerkers begrijpen ***wanneer de MFA-eis zal worden opgelegd,*** zodat het hen niet verrast.

## <a name="step-4-roll-out-the-mfa-requirement-to-your-organization-or-users"></a>Stap 4. De MFA-vereiste uitrollen naar uw organisatie of gebruikers

Op basis van de door u gekozen MFA-vereistenmethode rolt u MFA-verificatie uit naar de werknemers buiten uw pilottesters.

### <a name="security-defaults"></a>Standaardinstellingen voor beveiliging

U schakelt beveiligingsstandaards in of uit vanuit het deelvenster **Eigenschappen** voor Azure Active Directory (Azure AD) in de Azure-portal.

1.  Meld u aan bij het [Microsoft 365-beheercentrum](https://admin.microsoft.com) met algemene beheerdersreferenties.
2.  Ga naar de [pagina Azure Active Directory - Eigenschappen](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).
3.  Kies onderaan de pagina de optie **Standaardinstellingen voor beveiliging beheren**.
4.  Kies **Ja** om beveiligingsstandaards in te schakelen en **Nee** om beveiligingsstandaards uit te schakelen en kies **Opslaan**.

Als u het [beleid voor voorwaardelijke basislijnhebt](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)gebruikt, gaat u als u over op het gebruik van beveiligingsstandaardinstellingen.

1.  Ga naar de [pagina Voorwaardelijke toegang - Beleid](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).
2.  Kies elk basislijnbeleid dat is **ingeschakeld** en stel **Beleid inschakelen** in **op Uit**.
2.  Ga naar de [pagina Azure Active Directory - Eigenschappen](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).
4.  Kies onderaan de pagina de optie **Standaardinstellingen voor beveiliging beheren**.
5.  Kies **Ja** om beveiligingsstandaards in te schakelen en **Nee** om beveiligingsstandaards uit te schakelen en kies **Opslaan**.

### <a name="conditional-access-policies"></a>Beleid voor voorwaardelijke toegang

Maak, configureer en schakel het juiste beleid in dat de groep gebruikers bevat die MFA nodig heeft voor aanmelding.

### <a name="per-user-mfa-not-recommended"></a>MFA per gebruiker (niet aanbevolen)

Gebruikersaccounts voor MFA inschakelen die overeenkomen met uw implementatie.

### <a name="supporting-your-employees"></a>Uw medewerkers ondersteunen

Zorg er tijdens het registreren van uw medewerkers voor dat uw IT-specialisten, IT-afdeling of helpdesk vragen kunnen beantwoorden en problemen snel kunnen oplossen.

Zie dit artikel voor [informatie over het oplossen van MFA-aanmeldingen](https://support.office.com/article/fix-common-problems-with-multi-factor-authentication-6951be76-af50-49a4-847f-21391eaa59f2). 


