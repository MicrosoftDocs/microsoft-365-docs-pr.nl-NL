---
title: 'Stap 3: gebruikersaanmeldingen beveiligen en beheren'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: U kunt gebruikersaanmeldingen voor Windows-apparaten en voor Microsoft 365 veiliger maken.
ms.openlocfilehash: c541f5b74fe3ea6e94b002212f21ec8645e8e87e
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/13/2020
ms.locfileid: "42806847"
---
# <a name="step-3-secure-and-manage-your-user-sign-ins"></a>Stap 3: gebruikersaanmeldingen beveiligen en beheren

![Fase 2-identiteit](../media/deploy-foundation-infrastructure/identity_icon-small.png)


<a name="identity-windows-hello"></a>
## <a name="use-windows-hello-for-business"></a>Windows Hello voor Bedrijven gebruiken

*Deze stap is optioneel en geldt voor zowel E3- als E5-versies van Microsoft 365*

Windows Hello voor Bedrijven in Windows 10 Enterprise vervangt wachtwoorden met sterke tweeledige verificatie bij het ondertekenen op een Windows-apparaat. De twee factoren zijn een nieuw type gebruikersreferentie dat is gekoppeld aan een apparaat en een biometrisch kenmerk of een pincode.

Zie [Overzicht Windows Hello voor Bedrijven](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview)voor meer informatie.


<a name="identity-mfa"></a>
## <a name="set-up-azure-multi-factor-authentication"></a>Meervoudige verificatie instellen in Azure

*Deze stap is optioneel en geldt voor zowel E3- als E5-versies van Microsoft 365*

In deze stap stelt u Azure MFA (Multi-Factor Authentication) in om een tweede beveiligingslaag toe te voegen aan gebruikersaanmeldingen en transacties. MFA vereist een aanvullende verificatiemethode nadat gebruikers hun wachtwoord correct hebben ingevoerd. Zonder MFA is het wachtwoord de enige verificatiemethode. Het probleem met wachtwoorden is dat veel ervan gemakkelijk kunnen worden geraden door een aanvaller of onbewust worden gedeeld met niet-vertrouwde partijen.

Met MFA kan de tweede beveiligingslaag bestaan uit:

- Een persoonlijk en vertrouwd apparaat dat niet eenvoudig kan worden vervalst of gedupliceerd, zoals een smartphone.
- Een biometrisch kenmerk, zoals een vingerafdruk.

U schakelt MFA in en configureert de secundaire verificatiemethode met [beleid voor voorwaardelijke toegang](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access), waarmee u Azure Active Directory (Azure AD)-groepen kunt gebruiken om MFA uit te rollen naar bepaalde groepen gebruikers, zoals pilotgebruikers, geografische regio's of afdelingen. Zorg ervoor dat uw gebruikers weten dat MFA is ingeschakeld, zodat ze de vereisten begrijpen, zoals het verplichte gebruik van een smartphone om in te loggen, en ze met succes kunnen inloggen. 

Zie voor meer informatie [Een cloudgebaseerde implementatie van Azure Multi-Factor Authentication plannen](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted).

|||
|:-------|:-----|
|![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Testlabrichtlijn: meervoudige verificatie in Azure](multi-factor-authentication-microsoft-365-test-environment.md) |
|||

Als tussentijds controlepunt kunt u de [afsluitcriteria](identity-exit-criteria.md#crit-identity-mfa) voor deze stap bekijken.

<a name="identity-ident-prot"></a>
## <a name="protect-against-credential-compromise"></a>Bescherming tegen inbreuk op referenties

*Dit is optioneel en geldt alleen voor de E5-versie van Microsoft 365 Enterprise*

In dit gedeelte leert u hoe u beleidsregels configureert die bescherming bieden tegen inbreuken op referenties, waarbij een kwaadwillende gebruiker een aanval uitvoert op de accountnaam en wachtwoord van een gebruiker om toegang te krijgen tot de cloudservices en gegevens van een organisatie. Azure AD Identity Protection biedt verschillende manieren om te voorkomen dat een kwaadwillende gebruiker de referenties van een gebruikersaccount in gevaar kan brengen.

Met Azure AD Identity Protection kunt u:

|||
|:---------|:---------|
|Mogelijke beveiligingslekken in de identiteiten van uw organisatie vaststellen en verhelpen|Azure AD gebruikt machine learning om afwijkingen en verdachte activiteiten te detecteren, zoals aanmeldingen en activiteiten na aanmelding. Met deze gegevens genereert Azure AD Identity Protection rapporten en waarschuwingen om u te helpen bij het evalueren van problemen en het ondernemen van actie. |
|Verdachte acties opsporen die zijn gerelateerd aan de identiteiten van uw organisatie en automatisch op deze acties reageren|U kunt beleidsregels met betrekking tot risicobeheer zodanig configureren dat deze automatisch reageren op opgespoorde problemen als een bepaald risiconiveau is bereikt. Met deze beleidsregels kunt u, naast andere besturingselementen voor voorwaardelijke toegang die worden geboden door Azure AD en Microsoft Intune, de toegang automatisch blokkeren of corrigerende acties ondernemen, waaronder wachtwoordherstel en vereiste meervoudige verificatie in Azure voor volgende aanmeldingen.|
|Verdachte incidenten onderzoeken en deze oplossen met beheertaken|U kunt risico gebeurtenissen onderzoeken door informatie over het beveiligingsincident te gebruiken. Er zijn eenvoudige werkstromen beschikbaar om onderzoek bij te houden en herstelbewerkingen uit te voeren, zoals het opnieuw instellen van wachtwoorden.|

Zie [meer informatie over Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).

Zie de [stappen voor het inschakelen van de Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).

Het resultaat van deze stap is dat de Azure AD Identity Protection is ingeschakeld en u deze gebruikt voor het volgende:

- Mogelijke beveiligingslekken met een identiteit oplossen.
- Mogelijke inbreuk op referenties op te sporen.
- Het onderzoeken en adresseren van voortdurende verdachte identiteitsincidenten.

|||
|:-------|:-----|
|![Labrichtlijnen testen voor de Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Testlabrichtlijnen: Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md) |
|||

Als tussentijds controlepunt kunt u de [afsluitcriteria](identity-exit-criteria.md#crit-identity-ident-prot) voor dit gedeelte bekijken.

|||
|:-------|:-----|
|![Stap 4](../media/stepnumbers/Step4.png)| [Gebruikersaccounts toevoegen](identity-add-user-accounts.md) |
