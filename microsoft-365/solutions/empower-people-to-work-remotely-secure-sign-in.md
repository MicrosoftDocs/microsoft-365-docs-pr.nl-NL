---
title: Stap 1. Aanmeldingsbeveiliging voor hybride werknemers verbeteren met MFA
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- m365solution-remotework
- m365solution-scenario
ms.custom: ''
description: Vereis dat uw hybride werknemers zich aanmelden met meervoudige verificatie (MFA).
ms.openlocfilehash: 105c2f7170b4bea648427b0fda57ad081cb99a86
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/06/2021
ms.locfileid: "52788956"
---
# <a name="step-1-increase-sign-in-security-for-hybrid-workers-with-mfa"></a>Stap 1. Aanmeldingsbeveiliging voor hybride werknemers verbeteren met MFA

U kunt de aanmeldingsbeveiliging voor uw hybride werknemers verbeteren door gebruik te maken van meervoudige verificatie (MFA). Bij MFA is er voor gebruikersaanmeldingen extra verificatie naast het wachtwoord voor het gebruikersaccount nodig. Zelfs als kwaadwillende gebruikers het wachtwoord voor een gebruikersaccount achterhalen, moeten ze ook kunnen reageren op de extra verificatie, zoals een sms die naar een smartphone wordt gestuurd voordat er toegang wordt verleend.

![Het juiste wachtwoord plus een extra verificatie resulteert in een geslaagde aanmelding](../media/empower-people-to-work-remotely/remote-workers-mfa.png)

Voor alle gebruikers, met inbegrip van hybride werknemers en met name beheerders, wordt MFA ten zeerste aanbevolen.

Er zijn drie manieren waarop u uw gebruikers kunt verplichten MFA te gebruiken op basis van uw Microsoft 365-abonnement.

|Abonnement  |Aanbeveling  |
|---------|---------|
|Alle Microsoft 365-abonnementen (zonder Azure AD Premium P1- of P2-licenties)     |[Schakel standaardinstellingen voor beveiliging in Azure AD in](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults). De standaardinstellingen voor beveiliging in Azure AD omvatten MFA voor gebruikers en beheerders.   |
|Microsoft 365 E3 (bevat Azure AD Premium P1-licenties)     | Gebruik [algemeen beleid voor voorwaardelijke toegang](/azure/active-directory/conditional-access/concept-conditional-access-policy-common) om het volgende beleid te configureren: <br>- [MFA vereisen voor beheerders](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa) <br>- [MFA vereisen voor alle gebruikers](/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa) <br> - [Verouderde verificatie blokkeren](/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)       |
|Microsoft 365 E5 (bevat Azure AD Premium P2-licenties)     | Als u gebruikmaakt van Azure AD Identity Protection, begint u het implementeren van de [aanbevolen set beleidsregels voor voorwaardelijke toegang en verwante beleidsregels](../security/office-365-security/identity-access-policies.md) van Microsoft door de volgende beleidsregels te maken:<br> - [MFA vereisen bij een normaal of hoog risico bij het aanmelden](../security/office-365-security/identity-access-policies.md#require-mfa-based-on-sign-in-risk) <br>- [Clients blokkeren die moderne verificatie niet ondersteunen](../security/office-365-security/identity-access-policies.md#block-clients-that-dont-support-multi-factor)<br>- [Gebruikers met een hoog risico moeten het wachtwoord wijzigen](../security/office-365-security/identity-access-policies.md#high-risk-users-must-change-password)       |
| | |

## <a name="security-defaults"></a>Standaardinstellingen voor beveiliging

De standaardinstellingen voor beveiliging zijn een nieuwe functie voor betaalde Microsoft 365- en Office 365-abonnementen en proefabonnementen van Microsoft 365 en Office 365 die zijn gemaakt na 21 oktober 2019. Bij deze abonnementen zijn de standaardinstellingen voor beveiliging ingeschakeld waarmee ***al uw gebruikers MFA met de Microsoft Authenticator-app moeten gebruiken***.
 
Gebruikers hebben 14 dagen de tijd om zich te registreren voor MFA met de Microsoft Authenticator-app vanaf hun smartphone. Deze periode gaat in bij de eerste aanmelding nadat de standaardinstellingen voor beveiliging zijn ingeschakeld. Na 14 dagen kunnen gebruikers zich alleen aanmelden als de MFA-registratie is voltooid.

De standaardinstellingen voor beveiliging bieden organisaties een basisbeveiligingsniveau voor gebruikersaanmeldingen dat standaard is ingeschakeld. U kunt de standaardinstellingen voor beveiliging uitschakelen ten gunste van MFA met voorwaardelijk toegangsbeleid of voor afzonderlijke accounts.

Zie dit [overzicht van gevoeligheidslabels](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) voor meer informatie.

## <a name="conditional-access-policies"></a>Beleid voor voorwaardelijke toegang

Beleidsregels voor voorwaardelijke toegang zijn regels waarmee wordt aangegeven wanneer aanmeldingen worden beoordeeld en toegestaan. U kunt bijvoorbeeld een toegangsbeleid met de volgende voorwaarden maken:

- Als de naam van het gebruikersaccount lid is van een groep gebruikers die is toegewezen aan een Exchange-, gebruikers-, wachtwoord-, beveiligings-, SharePoint- of globale beheerdersrol, wordt MFA vereist om toegang te verlenen.

Met dit beleid kunt u MFA op basis van groepslidmaatschap vereisen in plaats van dat u afzonderlijke gebruikersaccounts voor MFA gaat configureren wanneer deze worden toegewezen (of als de toewijzing ongedaan wordt gemaakt) vanuit deze beheerdersrollen.

U kunt beleidsregels voor voorwaardelijke toegang ook gebruiken voor meer geavanceerde mogelijkheden, zoals vereisen dat de aanmelding wordt uitgevoerd vanaf een compatibel apparaat, zoals uw laptop met Windows 10.

Voor voorwaardelijke toegang zijn Azure AD Premium P1-licenties vereist, die deel uitmaken van Microsoft 365 E3 en E5.

Zie dit [overzicht van voorwaardelijke toegang](/azure/active-directory/conditional-access/overview) voor meer informatie.

## <a name="azure-ad-identity-protection-support"></a>Ondersteuning voor Azure AD Identity Protection

Met Azure AD Identity Protection kunt u een aanvullend beleid voor voorwaardelijke toegang maken. Hierin wordt het volgende gesteld:

- Als het aanmeldingsrisico op Gemiddeld of Hoog wordt vastgesteld, is MFA vereist.

Voor Azure AD Identity Protection zijn Azure AD Premium P2-licenties vereist, die deel uitmaken van Microsoft 365 E5.

Zie [Risk-based Conditional Access](/azure/active-directory/conditional-access/howto-conditional-access-policy-risk#require-mfa-medium-or-high-sign-in-risk-users) (Op risico's gebaseerde voorwaardelijke toegang) voor meer informatie.

Met Azure Active Directory Identity Protection kunt u ook een beleid maken om te vereisen dat uw gebruikers zich registreren voor MFA. Voor meer informatie, zie [Het beleid voor Azure AD Multi-Factor Authentication-registratie configureren](/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy)


## <a name="using-these-methods-together"></a>Deze methoden samen gebruiken

Houd het volgende in gedachten:

- U kunt geen standaardinstellingen voor beveiliging inschakelen als er beleidsregels voor voorwaardelijke toegang zijn ingeschakeld.
- Het is niet mogelijk om beleidsregels voor voorwaardelijke toegang in te schakelen als er standaardinstellingen voor beveiliging zijn ingeschakeld.

Als de standaardinstellingen voor beveiliging zijn ingeschakeld, moeten alle nieuwe gebruikers zich voor MFA registreren en de Microsoft Authenticator-app gebruiken. 

In deze tabel ziet u de resultaten na het inschakelen van MFA met de standaardinstellingen voor beveiliging en het beleid voor voorwaardelijke toegang.

| Methode | Ingeschakeld | Uitgeschakeld | Extra verificatiemethode |
|:-------|:-----|:-------|:-------|
| **Standaardinstellingen voor beveiliging**  | Kan geen beleid voor voorwaardelijke toegang gebruiken | Kan beleid voor voorwaardelijke toegang gebruiken | De Microsoft Authenticator-app |
| **Beleidsregels voor voorwaardelijke toegang** | Als er een of meer zijn ingeschakeld, kunt u de standaardinstellingen voor beveiliging niet inschakelen | Als ze allemaal zijn uitgeschakeld, kunt u de standaardinstellingen voor beveiliging inschakelen  | Opgeven door gebruiker tijdens MFA-registratie  |
||||

## <a name="let-your-users-reset-their-own-passwords"></a>Gebruikers toestaan hun eigen wachtwoord opnieuw in te stellen

Met self-service voor wachtwoordherstel (SSPR) kunnen gebruikers hun eigen wachtwoord opnieuw instellen zonder de IT-medewerkers te belasten. Gebruikers kunnen hun wachtwoord op elk moment en vanaf elke locatie snel opnieuw instellen. Voor meer informatie, zie [Een implementatie voor self-service voor wachtwoordherstel van Azure AD plannen](/azure/active-directory/authentication/howto-sspr-deployment).

## <a name="sign-in-to-saas-apps-with-azure-ad"></a>Aanmelden bij SaaS-apps met Azure AD

Azure AD kan naast het bieden van cloudverificatie voor gebruikers ook worden gebruikt om al uw apps centraal te beveiligen, ongeacht of ze zich on-premises, in de Microsoft-cloud of in een andere cloud bevinden. Door het [integreren van apps in azure AD](/azure/active-directory/manage-apps/plan-an-application-integration), kunt u het hybride werknemers gemakkelijk maken om de toepassingen te vinden die ze nodig hebben en zich veilig hierbij aan te melden.

## <a name="admin-technical-resources-for-mfa-and-identity"></a>Technische informatiebronnen voor beheerders voor MFA en identiteit

- [Belangrijkste vijf manieren waarop Azure AD helpt bij werken op afstand](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/top-5-ways-your-azure-ad-can-help-you-enable-remote-work/ba-p/1144691)
- [Identiteits-roadmap voor Microsoft 365 herkennen](../enterprise/identity-roadmap-microsoft-365.md)
- [Azure Academy Azure AD-trainingsvideo's](https://www.youtube.com/watch?v=pN8o0owHfI0&list=PL-V4YVm6AmwUFpC3rXr2i2piRQ708q_ia)

## <a name="results-of-step-1"></a>Resultaten van stap 1

Na de implementatie van MFA moeten uw gebruikers:

- MFA voor aanmeldingen gebruiken.
- Het MFA-registratieproces hebben voltooid en MFA voor alle aanmeldingen gebruiken.
- SSPR gebruiken om hun eigen wachtwoord opnieuw in te stellen.

## <a name="next-step"></a>Volgende stap

[![Stap 2: Externe toegang tot on-premises apps en services bieden](../media/empower-people-to-work-remotely/remote-workers-step-grid-2.png)](empower-people-to-work-remotely-remote-access.md)

Ga verder met [stap 2](empower-people-to-work-remotely-remote-access.md) om externe toegang tot on-premises apps en services te bieden.