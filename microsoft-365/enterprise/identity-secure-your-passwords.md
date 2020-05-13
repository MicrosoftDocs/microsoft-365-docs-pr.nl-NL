---
title: 'Stap 2: Wachtwoorden beveiligen'
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
description: U moet de wachtwoorden binnen uw organisatie sterk en beheerbaar maken.
ms.openlocfilehash: 6e5c2567ee2027be2a84121fdad10ba873ec1c43
ms.sourcegitcommit: 1c90bcc5c56f24895f01c3e0423c3f6b73715c13
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/13/2020
ms.locfileid: "44214648"
---
# <a name="step-2-secure-your-passwords"></a>Stap 2: Wachtwoorden beveiligen

![Fase 2-Identiteit](../media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-password-prot"></a>
## <a name="prevent-bad-passwords"></a>Slechte wachtwoorden voorkomen

*Deze stap is optioneel en geldt voor zowel E3- als E5-versies van Microsoft 365*

Al uw gebruikers dienen de [Wachtwoordondersteuning van Microsoft](https://www.microsoft.com/research/publication/password-guidance) te gebruiken om de wachtwoorden voor hun gebruikersaccounts te maken.

Als u wilt voorkomen dat gebruikers een te makkelijk wachtwoord aanmaken, gebruikt u Azure AD-wachtwoordbeveiliging. Hierbij wordt gebruikgemaakt van een wereldwijd geblokkeerde wachtwoordlijst en een optionele, aangepaste lijst met geblokkeerde wachtwoorden die u kunt vaststellen. U kunt bijvoorbeeld termen op deze lijst zetten die specifiek voor uw organisatie zijn, zoals:

- Merknamen
- Productnamen
- Locaties (zoals bijvoorbeeld het hoofdkantoor van het bedrijf)
- Bedrijfsspecifieke interne termen
- Afkortingen met een specifieke betekenis binnen het bedrijf

U kunt slechte wachtwoorden [in de Cloud](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) en voor uw [Active Directory Domain Services (AD DS) op locatie](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises) verbieden.

Als tussentijds controlepunt kunt u de [afsluitcriteria](identity-exit-criteria.md#crit-password-prot) voor deze sectie bekijken.

<a name="identity-pw-reset"></a>
## <a name="simplify-password-resets"></a>Het opnieuw instellen van wachtwoorden vereenvoudigen

*Deze stap is optioneel en geldt voor zowel E3- als E5-versies van Microsoft 365*

In deze sectie kunt u de selfservice voor het opnieuw instellen van wachtwoorden (SSPR) inschakelen, zodat gebruikers hun wachtwoorden of accounts opnieuw kunnen instellen of ontgrendelen. Als u wilt worden gewaarschuwd voor misbruik, kunt u gebruikmaken van gedetailleerde rapporten die bijhouden en meldingen geven wanneer gebruikers het systeem openen. U moet het terugschrijven van wachtwoorden inschakelen voordat u het opnieuw instellen van wachtwoord kunt implementeren.

Zie de [instructies voor het invoeren van wachtwoordherstel](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment).

|||
|:-------|:-----|
|![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Testlabrichtlijn: Wachtwoord opnieuw instellen](password-reset-m365-ent-test-environment.md) |
|||

Als tussentijds controlepunt kunt u de [afsluitcriteria](identity-exit-criteria.md#crit-identity-pw-reset) voor deze sectie bekijken.


<a name="identity-sso"></a>
## <a name="simplify-user-sign-in"></a>Gebruikersaanmelding vereenvoudigen

*Deze stap is optioneel voor hybride omgevingen en geldt voor zowel E3- als E5-versies van Microsoft 365 Enterprise*

In deze sectie stelt u naadloze eenmalige aanmelding via Azure Active Directory in, dat met wachtwoord-hash-synchronisatie en pass-through-verificatie werkt om ervoor te zorgen dat uw gebruikers zich kunnen aanmelden bij services die gebruikmaken van Azure Active Directory-gebruikersaccounts, zonder dat ze hun wachtwoorden en in veel gevallen zelfs hun gebruikersnamen hoeven in te voeren. Dit geeft uw gebruikers eenvoudiger toegang tot toepassingen in de cloud, zoals Office 365, zonder extra onderdelen op locatie nodig te hebben, zoals identiteitsfederatie-servers.

U configureert naadloze eenmalige aanmelding via Azure AD met het hulpprogramma Azure AD Connect.

Zie [instructies voor het configureren naadloze eenmalige aanmelding via Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).

|||
|:-------|:-----|
|![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Testlabrichtlijn: naadloze eenmalige aanmelding via Azure AD](single-sign-on-m365-ent-test-environment.md) |
|||

Als tussentijds controlepunt kunt u de [afsluitcriteria](identity-exit-criteria.md#crit-identity-sso) voor dit gedeelte bekijken.


<a name="identity-custom-sign-in"></a>
## <a name="customize-the-sign-in-page"></a>De aanmeldingspagina aanpassen

*Deze stap is optioneel en geldt voor zowel E3- als E5-versies van Microsoft 365 Enterprise*

Met deze stap helpt u gebruikers de aanmeldingspagina van uw organisatie te herkennen door uw bedrijfsnaam, -logo en andere herkenbare elementen toe te voegen. 

Met Microsoft 365 Enterprise kunt u het uiterlijk van de aanmeldings- en toegangspagina’s aanpassen, zodat ze uw bedrijfslogo, kleurenschema’s en aangepaste gebruikersgegevens bevatten. 

Zie [Huisstijl van uw bedrijf toevoegen aan de aanmeldingspagina van Microsoft 365](https://docs.microsoft.com/office365/admin/setup/customize-sign-in-page) voor meer informatie.

Zie [Huisstijl van uw bedrijf toevoegen aan de aanmeldings- en toegangspagina’s](https://aka.ms/aadpaddbranding) voor configuratie-instructies.

Als tussentijds controlepunt kunt u de [afsluitcriteria](identity-exit-criteria.md#crit-identity-custom-sign-in) voor deze sectie bekijken.

## <a name="next-step"></a>Volgende stap

|||
|:-------|:-----|
|![Stap 3](../media/stepnumbers/Step3.png)| [Gebruikersaanmeldingen beveiligen en beheren](identity-secure-user-sign-ins.md) |
