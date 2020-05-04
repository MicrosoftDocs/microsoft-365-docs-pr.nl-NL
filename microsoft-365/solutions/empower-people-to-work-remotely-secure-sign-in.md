---
title: Stap 1. Aanmeldingsbeveiliging voor externe werknemers verbeteren met MFA
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 05/01/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
ms.custom:
- M365solutions
description: Vereis dat uw externe werknemers zich aanmelden met meervoudige verificatie (MFA).
ms.openlocfilehash: f8154f35baaf693bb51c523cfe4c44374437de02
ms.sourcegitcommit: 101084f9c81616342d78493232d8f13f5ffa4ddf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/01/2020
ms.locfileid: "44003577"
---
# <a name="step-1-increase-sign-in-security-for-remote-workers-with-mfa"></a>Stap 1. Aanmeldingsbeveiliging voor externe werknemers verbeteren met MFA

U kunt de aanmeldingsbeveiliging voor uw externe werknemers verbeteren door gebruik te maken van meervoudige verificatie (MFA). Bij MFA is er voor gebruikersaanmeldingen extra verificatie naast het wachtwoord voor het gebruikersaccount nodig. Zelfs als kwaadwillende gebruikers het wachtwoord voor een gebruikersaccount achterhalen, moeten ze ook kunnen reageren op de extra verificatie, zoals een sms die naar een smartphone wordt gestuurd voordat er toegang wordt verleend.

Voor alle gebruikers, met inbegrip van externe werknemers en met name beheerders, wordt MFA ten zeerste aanbevolen.

Er zijn drie manieren waarop u uw gebruikers kunt verplichten MFA te gebruiken op basis van uw Microsoft 365-abonnement.

|Abonnement  |Aanbeveling  |
|---------|---------|
|Microsoft 365-abonnementen (zonder Azure AD Premium P1 of P2)     |[Schakel standaardinstellingen voor beveiliging in Azure AD in](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults). De standaardinstellingen voor beveiliging in Azure AD omvatten MFA voor gebruikers en beheerders.   |
|Microsoft 365 E3 (met Azure AD Premium P1)     | Gebruik [algemeen beleid voor voorwaardelijke toegang](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) om het volgende beleid te configureren: <br>- [MFA vereisen voor beheerders](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa) <br>- [MFA vereisen voor alle gebruikers](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa) <br> - [Verouderde verificatie blokkeren](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)       |
|Microsoft 365 E5 (met Azure AD Premium P2)     | Als u gebruikmaakt van Azure AD Identity Protection, begint u het implementeren van de [aanbevolen set beleidsregels voor voorwaardelijke toegang en verwante beleidsregels](../enterprise/identity-access-policies.md) van Microsoft door de volgende twee beleidsregels te maken:<br> - [MFA vereisen bij een normaal of hoog risico bij het aanmelden](../enterprise/identity-access-policies.md#require-mfa-based-on-sign-in-risk) <br>- [Clients blokkeren die moderne verificatie niet ondersteunen](../enterprise/identity-access-policies.md#block-clients-that-dont-support-modern-authentication)<br>- [Gebruikers met een hoog risico moeten het wachtwoord wijzigen](../enterprise/identity-access-policies.md#high-risk-users-must-change-password)       |
| | |

## <a name="security-defaults"></a>Standaardinstellingen voor beveiliging

De standaardinstellingen voor beveiliging zijn een nieuwe functie voor betaalde Microsoft 365- en Office 365-abonnementen en proefabonnementen van Microsoft 365 en Office 365 die zijn gemaakt na 21 oktober 2019. Bij deze abonnementen zijn de standaardinstellingen voor beveiliging ingeschakeld waarmee ***al uw gebruikers MFA met de Microsoft Authenticator-app moeten gebruiken***.
 
Gebruikers hebben 14 dagen de tijd om zich te registreren voor MFA met de Microsoft Authenticator-app vanaf hun smartphone. Deze periode gaat in bij de eerste aanmelding nadat de standaardinstellingen voor beveiliging zijn ingeschakeld. Na 14 dagen kunnen gebruikers zich alleen aanmelden als de MFA-registratie is voltooid.

De standaardinstellingen voor beveiliging bieden organisaties een basisbeveiligingsniveau voor gebruikersaanmeldingen dat standaard is ingeschakeld. U kunt de standaardinstellingen voor beveiliging uitschakelen ten gunste van MFA met voorwaardelijk toegangsbeleid of voor afzonderlijke accounts.

Zie dit [overzicht van gevoeligheidslabels](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) voor meer informatie.

## <a name="conditional-access-policies"></a>Beleid voor voorwaardelijke toegang

Beleidsregels voor voorwaardelijke toegang zijn regels waarmee wordt aangegeven wanneer aanmeldingen worden beoordeeld en toegestaan. U kunt bijvoorbeeld een toegangsbeleid met de volgende voorwaarden maken:

- Als de gebruikersaccountnaam staat voor een gebruiker die een Exchange-, gebruikers-, wachtwoord-, beveiligings-, SharePoint- of globale beheerder is, wordt MFA vereist om toegang te verlenen.

Dit beleid is eenvoudiger dan proberen te onthouden afzonderlijke gebruikersaccounts te configureren voor MFA als deze worden toegevoegd aan of verwijderd uit deze beheerdersrollen.

U kunt beleidsregels voor voorwaardelijke toegang ook gebruiken voor meer geavanceerde mogelijkheden, zoals vereisen dat de aanmelding wordt uitgevoerd vanaf een compatibel apparaat, zoals uw laptop met Windows 10.

Voor voorwaardelijke toegang is Azure AD Premium P1 vereist, dat deel uitmaakt van Microsoft 365 E3 en E5.

Zie dit [overzicht van voorwaardelijke toegang](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) voor meer informatie.

## <a name="azure-ad-identity-protection-policies"></a>Azure AD Identity Protection-beleid

Azure AD Identity Protection-beleid bestaat uit regels waarmee wordt aangegeven wanneer aanmeldingen worden beoordeeld en toegestaan. U kunt bijvoorbeeld een Azure AD Identity Protection-beleid maken waarin het volgende wordt aangegeven:

- Als het risico van de aanmelding als gemiddeld of hoog wordt beschouwd, moet de gebruiker MFA gebruiken om zich aan te melden.

Voor Azure AD Identity Protection is Azure AD Premium P2 vereist, dat deel uitmaakt van Microsoft 365 E5.

Zie dit [overzicht van Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection) voor meer informatie.

## <a name="using-these-methods-together"></a>Deze methoden samen gebruiken

Houd het volgende in gedachten:

- U kunt geen standaardinstellingen voor beveiliging inschakelen als er beleidsregels voor voorwaardelijke toegang zijn ingeschakeld.
- Het is niet mogelijk om beleidsregels voor voorwaardelijke toegang in te schakelen als er standaardinstellingen voor beveiliging zijn ingeschakeld.

Als de standaardinstellingen voor beveiliging zijn ingeschakeld, moeten alle nieuwe gebruikers zich voor MFA registreren en de Microsoft Authenticator-app gebruiken. 

In deze tabel ziet u de resultaten van het inschakelen van MFA met de standaardinstellingen voor beveiliging, het beleid voor voorwaardelijke toegang en de instellingen per gebruikersaccount.

|| Ingeschakeld | Uitgeschakeld | Secundaire verificatiemethode |
|:-------|:-----|:-------|:-------|
| **Standaardinstellingen voor beveiliging**  | Kan geen beleid voor voorwaardelijke toegang gebruiken | Kan beleid voor voorwaardelijke toegang gebruiken | De Microsoft Authenticator-app |
| **Beleidsregels voor voorwaardelijke toegang** | Als er een of meer zijn ingeschakeld, kunt u de standaardinstellingen voor beveiliging niet inschakelen | Als er geen een is ingeschakeld, kunt u de standaardinstellingen voor beveiliging inschakelen  | Door gebruiker opgegeven tijdens MFA-registratie  |
||||

## <a name="admin-training-and-technical-resources-for-mfa-and-identity"></a>Training voor beheerders en technische informatiebronnen voor MFA en identiteit

- [MFA-planning voor Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/multi-factor-authentication-plan)
- [Belangrijkste vijf manieren waarop Azure AD helpt bij werken op afstand](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/top-5-ways-your-azure-ad-can-help-you-enable-remote-work/ba-p/1144691)
- [Uw Microsoft 365 Enterprise-identiteitsinfrastructuur plannen en implementeren](https://docs.microsoft.com/microsoft-365/enterprise/identity-infrastructure?view=o365-worldwide#plan-and-deploy-your-microsoft-365-enterprise-identity-infrastructure)
- [Azure Academy Azure AD-trainingsvideo's](https://www.youtube.com/watch?v=pN8o0owHfI0&list=PL-V4YVm6AmwUFpC3rXr2i2piRQ708q_ia)
- [Het beleid voor Azure Multi-Factor Authentication-registratie configureren](https://docs.microsoft.com/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy)

## <a name="results-of-step-1"></a>Resultaten van stap 1

Na de implementatie van MFA moeten uw gebruikers:

- MFA voor aanmeldingen gebruiken.
- Het MFA-registratieproces hebben voltooid en MFA voor alle aanmeldingen gebruiken.

## <a name="next-step"></a>Volgende stap

Ga verder met [stap 2](empower-people-to-work-remotely-remote-access.md) om externe toegang tot on-premises apps en services te bieden.
