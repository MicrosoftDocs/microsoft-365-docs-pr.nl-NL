---
title: Stap 1. Aanmeldingsbeveiliging voor externe werknemers verbeteren met MFA
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 06/22/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- m365solution-remotework
ms.custom: ''
description: Vereis dat uw externe werknemers zich aanmelden met meervoudige verificatie (MFA).
ms.openlocfilehash: a8c0b8ac689407fa871d2373f1ca0a3658bb1668
ms.sourcegitcommit: 0f71042edc7c3a7f10a7b92e1943abf51532cbf5
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/29/2020
ms.locfileid: "46521515"
---
# <a name="step-1-increase-sign-in-security-for-remote-workers-with-mfa"></a>Stap 1. Aanmeldingsbeveiliging voor externe werknemers verbeteren met MFA

U kunt de aanmeldingsbeveiliging voor uw externe werknemers verbeteren door gebruik te maken van meervoudige verificatie (MFA). Bij MFA is er voor gebruikersaanmeldingen extra verificatie naast het wachtwoord voor het gebruikersaccount nodig. Zelfs als kwaadwillende gebruikers het wachtwoord voor een gebruikersaccount achterhalen, moeten ze ook kunnen reageren op de extra verificatie, zoals een sms die naar een smartphone wordt gestuurd voordat er toegang wordt verleend.

![Het juiste wachtwoord plus een extra verificatie resulteert in een geslaagde aanmelding](../media/empower-people-to-work-remotely/remote-workers-mfa.png)

Voor alle gebruikers, met inbegrip van externe werknemers en met name beheerders, wordt MFA ten zeerste aanbevolen.

Er zijn drie manieren waarop u uw gebruikers kunt verplichten MFA te gebruiken op basis van uw Microsoft 365-abonnement.

|Abonnement  |Aanbeveling  |
|---------|---------|
|Alle Microsoft 365-abonnementen (zonder Azure AD Premium P1- of P2-licenties)     |[Schakel standaardinstellingen voor beveiliging in Azure AD in](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults). De standaardinstellingen voor beveiliging in Azure AD omvatten MFA voor gebruikers en beheerders.   |
|Microsoft 365 E3 (bevat Azure AD Premium P1-licenties)     | Gebruik [algemeen beleid voor voorwaardelijke toegang](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) om het volgende beleid te configureren: <br>- [MFA vereisen voor beheerders](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa) <br>- [MFA vereisen voor alle gebruikers](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa) <br> - [Verouderde verificatie blokkeren](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)       |
|Microsoft 365 E5 (bevat Azure AD Premium P2-licenties)     | Als u gebruikmaakt van Azure AD Identity Protection, begint u het implementeren van de [aanbevolen set beleidsregels voor voorwaardelijke toegang en verwante beleidsregels](../enterprise/identity-access-policies.md) van Microsoft door de volgende twee beleidsregels te maken:<br> - [MFA vereisen bij een normaal of hoog risico bij het aanmelden](../enterprise/identity-access-policies.md#require-mfa-based-on-sign-in-risk) <br>- [Clients blokkeren die moderne verificatie niet ondersteunen](../enterprise/identity-access-policies.md#block-clients-that-dont-support-modern-authentication)<br>- [Gebruikers met een hoog risico moeten het wachtwoord wijzigen](../enterprise/identity-access-policies.md#high-risk-users-must-change-password)       |
| | |

## <a name="security-defaults"></a>Standaardinstellingen voor beveiliging

De standaardinstellingen voor beveiliging zijn een nieuwe functie voor betaalde Microsoft 365- en Office 365-abonnementen en proefabonnementen van Microsoft 365 en Office 365 die zijn gemaakt na 21 oktober 2019. Bij deze abonnementen zijn de standaardinstellingen voor beveiliging ingeschakeld waarmee ***al uw gebruikers MFA met de Microsoft Authenticator-app moeten gebruiken***.
 
Gebruikers hebben 14 dagen de tijd om zich te registreren voor MFA met de Microsoft Authenticator-app vanaf hun smartphone. Deze periode gaat in bij de eerste aanmelding nadat de standaardinstellingen voor beveiliging zijn ingeschakeld. Na 14 dagen kunnen gebruikers zich alleen aanmelden als de MFA-registratie is voltooid.

De standaardinstellingen voor beveiliging bieden organisaties een basisbeveiligingsniveau voor gebruikersaanmeldingen dat standaard is ingeschakeld. U kunt de standaardinstellingen voor beveiliging uitschakelen ten gunste van MFA met voorwaardelijk toegangsbeleid of voor afzonderlijke accounts.

Zie dit [overzicht van gevoeligheidslabels](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) voor meer informatie.

## <a name="conditional-access-policies"></a>Beleid voor voorwaardelijke toegang

Beleidsregels voor voorwaardelijke toegang zijn regels waarmee wordt aangegeven wanneer aanmeldingen worden beoordeeld en toegestaan. U kunt bijvoorbeeld een toegangsbeleid met de volgende voorwaarden maken:

- Als de naam van het gebruikersaccount lid is van een groep gebruikers die is toegewezen aan een Exchange-, gebruikers-, wachtwoord-, beveiligings-, SharePoint- of globale beheerdersrol, wordt MFA vereist om toegang te verlenen.

Met dit beleid kunt u MFA op basis van groepslidmaatschap vereisen in plaats van dat u afzonderlijke gebruikersaccounts voor MFA gaat configureren wanneer deze worden toegewezen (of als de toewijzing ongedaan wordt gemaakt) vanuit deze beheerdersrollen.

U kunt beleidsregels voor voorwaardelijke toegang ook gebruiken voor meer geavanceerde mogelijkheden, zoals vereisen dat de aanmelding wordt uitgevoerd vanaf een compatibel apparaat, zoals uw laptop met Windows 10.

Voor voorwaardelijke toegang zijn Azure AD Premium P1-licenties vereist, die deel uitmaken van Microsoft 365 E3 en E5.

Zie dit [overzicht van voorwaardelijke toegang](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) voor meer informatie.

## <a name="azure-ad-identity-protection-support"></a>Ondersteuning voor Azure AD Identity Protection

Met Azure AD Identity Protection kunt u een aanvullend beleid voor voorwaardelijke toegang maken. Hierin wordt het volgende gesteld:

- Als het aanmeldingsrisico op Gemiddeld of Hoog wordt vastgesteld, is MFA vereist.

Voor Azure AD Identity Protection zijn Azure AD Premium P2-licenties vereist, die deel uitmaken van Microsoft 365 E5.

Zie [Risk-based Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-risk#require-mfa-medium-or-high-sign-in-risk-users) (Op risico's gebaseerde voorwaardelijke toegang) voor meer informatie.

## <a name="using-these-methods-together"></a>Deze methoden samen gebruiken

Houd het volgende in gedachten:

- U kunt geen standaardinstellingen voor beveiliging inschakelen als er beleidsregels voor voorwaardelijke toegang zijn ingeschakeld.
- Het is niet mogelijk om beleidsregels voor voorwaardelijke toegang in te schakelen als er standaardinstellingen voor beveiliging zijn ingeschakeld.

Als de standaardinstellingen voor beveiliging zijn ingeschakeld, moeten alle nieuwe gebruikers zich voor MFA registreren en de Microsoft Authenticator-app gebruiken. 

In deze tabel ziet u de resultaten na het inschakelen van MFA met de standaardinstellingen voor beveiliging en het beleid voor voorwaardelijke toegang.

|| Ingeschakeld | Uitgeschakeld | Extra verificatiemethode |
|:-------|:-----|:-------|:-------|
| **Standaardinstellingen voor beveiliging**  | Kan geen beleid voor voorwaardelijke toegang gebruiken | Kan beleid voor voorwaardelijke toegang gebruiken | De Microsoft Authenticator-app |
| **Beleidsregels voor voorwaardelijke toegang** | Als er een of meer zijn ingeschakeld, kunt u de standaardinstellingen voor beveiliging niet inschakelen | Als ze allemaal zijn uitgeschakeld, kunt u de standaardinstellingen voor beveiliging inschakelen  | Opgeven door gebruiker tijdens MFA-registratie  |
||||

## <a name="let-your-users-reset-their-own-passwords"></a>Gebruikers toestaan hun eigen wachtwoord opnieuw in te stellen

Met self-service voor wachtwoordherstel (SSPR) kunnen gebruikers hun eigen wachtwoord opnieuw instellen zonder de IT-medewerkers te belasten. Gebruikers kunnen hun wachtwoord op elk moment en vanaf elke locatie snel opnieuw instellen. Bekijk [deze video](https://go.microsoft.com/fwlink/?linkid=2128524) om SSPR in te stellen.

## <a name="sign-in-to-saas-apps-with-azure-ad"></a>Aanmelden bij SaaS-apps met Azure AD

Azure AD kan naast het bieden van cloudverificatie voor gebruikers ook worden gebruikt om al uw apps centraal te beveiligen, ongeacht of ze zich on-premises, in de Microsoft-cloud of in een andere cloud bevinden. Door het [integreren van apps in azure AD](https://docs.microsoft.com/azure/active-directory/manage-apps/plan-an-application-integration), kunt u het externe medewerkers gemakkelijk maken om de toepassingen te vinden die ze nodig hebben en zich veilig hierop aan te melden.

## <a name="admin-technical-resources-for-mfa-and-identity"></a>Technische informatiebronnen voor beheerders voor MFA en identiteit

- [MFA voor Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/multi-factor-authentication-microsoft-365)
- [Belangrijkste vijf manieren waarop Azure AD helpt bij werken op afstand](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/top-5-ways-your-azure-ad-can-help-you-enable-remote-work/ba-p/1144691)
- [Uw Microsoft 365 Enterprise-identiteitsinfrastructuur plannen en implementeren](https://docs.microsoft.com/microsoft-365/enterprise/identity-infrastructure?view=o365-worldwide#plan-and-deploy-your-microsoft-365-enterprise-identity-infrastructure)
- [Azure Academy Azure AD-trainingsvideo's](https://www.youtube.com/watch?v=pN8o0owHfI0&list=PL-V4YVm6AmwUFpC3rXr2i2piRQ708q_ia)
- [Het beleid voor Azure Multi-Factor Authentication-registratie configureren](https://docs.microsoft.com/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy)
- [Een implementatie voor self-service voor wachtwoordherstel van Azure AD plannen](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment)

## <a name="results-of-step-1"></a>Resultaten van stap 1

Na de implementatie van MFA moeten uw gebruikers:

- MFA voor aanmeldingen gebruiken.
- Het MFA-registratieproces hebben voltooid en MFA voor alle aanmeldingen gebruiken.
- SSPR gebruiken om hun eigen wachtwoord opnieuw in te stellen.

## <a name="next-step"></a>Volgende stap

Ga verder met [stap 2](empower-people-to-work-remotely-remote-access.md) om externe toegang tot on-premises apps en services te bieden.
