---
title: Stap 3. Identiteit van uw Microsoft 365 for Enterprise-tenants
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
ms.custom:
- Ent_Solutions
description: Implementeer het juiste identiteits model voor uw Microsoft 365-tenants en verstevigt gebruikersregistratie.
ms.openlocfilehash: 40ea67d9b30a385e36af45f57bd33906c10e495d
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908495"
---
# <a name="step-3-identity-for-your-microsoft-365-for-enterprise-tenants"></a>Stap 3. Identiteit van uw Microsoft 365 for Enterprise-tenants

Uw Microsoft 365-Tenant bevat een Azure AD-Tenant (Azure Active Directory) voor het beheren van identiteiten en authenticatie voor aanmelding. De juiste configuratie van de identiteits infrastructuur is essentieel voor het beheren van gebruikers toegang en machtigingen voor Microsoft 365 voor uw organisatie.

## <a name="cloud-only-vs-hybrid"></a>Alleen Cloud, versus hybride

Dit zijn de twee typen identiteits modellen en de beste voordelen.


| Model | Beschrijving | Hoe Microsoft 365 gebruikersreferenties verifieert | Geschikt voor | Grootste voordeel |
|:-------|:-----|:-----|:-----|:-----|
| Alleen in de cloud | Het gebruikersaccount bestaat alleen in de Azure AD-Tenant voor uw Microsoft 365-Tenant. | Met de Azure AD-Tenant voor uw Microsoft 365-Tenant wordt de authenticatie uitgevoerd met de Cloud-identiteits account. | Organisaties die geen on-premises AD DS hebben of behoefte hebben. | Eenvoudig te gebruiken. Geen extra hulpmiddelen voor directory's of servers vereist. |
| Hybride |  Het gebruikersaccount bestaat in uw on-premises Active Directory Domain Services (AD DS) en een kopie staat ook in de Azure AD-Tenant voor uw Microsoft 365-Tenant. Azure AD Connect wordt uitgevoerd op een on-premises server om AD DS-wijzigingen te synchroniseren met de Azure AD-Tenant. Het gebruikersaccount in azure AD kan ook een gehasheerde versie van het wachtwoord voor een gehasheerde gebruikersaccount bevatten. | Met de Azure AD-Tenant voor uw Microsoft 365-Tenant wordt het verificatieproces verwerkt of wordt de gebruiker omgeleid naar een andere identiteitsprovider. | Organisaties die AD DS of een andere identiteitsprovider gebruiken. | Gebruikers kunnen dezelfde referenties gebruiken voor het openen van on-premises of Cloud bronnen. |
||||||

Hier volgen de basisonderdelen van de identiteit van de Cloud.
 
![Basisonderdelen van de alleen-Cloud identiteit](../media/about-microsoft-365-identity/cloud-only-identity.png)

In deze afbeelding worden on-premises gebruikers en externe gebruikers aangemeld met accounts in de Azure AD-Tenant van hun Microsoft 365-Tenant.

Hier volgen de basisonderdelen van de Hybrid Identity.

![Basisonderdelen van een hybride identiteit](../media/about-microsoft-365-identity/hybrid-identity.png)

In deze afbeelding wordt on-premises en externe gebruikers aangemeld met hun Microsoft 365-Tenant met accounts in de Azure AD-Tenant die zijn gekopieerd vanuit hun on-premises AD DS.

## <a name="synchronizing-your-on-premises-ad-ds"></a>Uw on-premises AD DS synchroniseren

Afhankelijk van de behoeften van uw bedrijf en de technische vereisten, is dit de meest voorkomende optie voor Enterprise-klanten die Microsoft 365 aannemen. Met adreslijstsynchronisatie kunt u identiteiten beheren in uw AD DS en alle updates voor gebruikersaccounts, groepen en contactpersonen worden gesynchroniseerd met de Azure AD-Tenant van uw Microsoft 365-Tenant.

>[!Note]
>Wanneer Active Directory-gebruikersaccounts voor de eerste keer worden gesynchroniseerd, wordt er niet automatisch een Microsoft 365-licentie toegewezen en geen toegang tot Microsoft 365-Services, zoals e-mail. U moet ze eerst een gebruikslocatie toewijzen. Vervolgens kunt u een licentie toewijzen aan deze gebruikersaccounts, hetzij afzonderlijk of dynamisch via groepslidmaatschap.
>

Dit zijn de twee typen verificatie wanneer u het Hybrid Identity model gebruikt.

| Type verificatie | Beschrijving |
|:-------|:-----|
| Beheerde verificatie | Azure AD lost het authenticatieproces op met een lokaal opgeslagen hash-versie van het wachtwoord of verzendt de referenties naar een on-premises programma-agent om te worden geverifieerd door de on-premises AD DS. <br> <br>  Er zijn twee typen beheerde verificatie: wachtwoord hash-synchronisatie (PHS) en Pass Through-verificatie (PTA). Met PHS voert Azure AD de authenticatie zelf uit. Met PTA heeft Azure AD DS de authenticatie uitvoeren. |
| Federatieve verificatie | Azure AD stuurt de clientcomputer om authenticatie vragen aan een andere identiteitsprovider. |
|  |  |

Zie voor meer informatie [de juiste verificatiemethode kiezen](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) .

## <a name="enforcing-strong-sign-ins"></a>Sterke aantekening afdwingen

Gebruik de functies en functies in de volgende tabel om de beveiliging van gebruikersaanmeldingen te vergroten.

| Mogelijkheid | Beschrijving | Meer informatie | Licentievereisten |
|:-------|:-----|:-----|:-----|:-----|
| Windows Hello voor Bedrijven | Hiermee vervangt u wachtwoorden door sterke tweeledige verificatie wanneer u zich aanmeldt op een Windows-apparaat. De twee factoren zijn een nieuw type gebruikersreferentie dat is gekoppeld aan een apparaat en een biometrisch kenmerk of een pincode. | [Overzicht van Windows hello voor bedrijven](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview) | Microsoft 365 E3 of E5 |
| Azure AD-wachtwoordbeveiliging | Detecteert en blokkeert bekende zwakke wachtwoorden en hun varianten, en kan ook extra zwakke termen blokkeren die specifiek zijn voor uw organisatie. | [Azure AD-wachtwoordbeveiliging configureren](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) | Microsoft 365 E3 of E5 |
| Meervoudige verificatie (MFA) gebruiken | Voor MFA moet de aanmelding van gebruikers zijn onderworpen aan een extra verificatie buiten het wachtwoord van het gebruikersaccount, bijvoorbeeld verificatie met een smartphone-app of een tekstbericht dat naar een smartphone is verzonden. Bekijk [deze video](https://support.microsoft.com/office/set-up-multi-factor-authentication-in-microsoft-365-business-a32541df-079c-420d-9395-9d59354f7225) voor meer informatie over de manier waarop gebruikers MFA instellen. | [MFA voor Microsoft 365 for Enterprise](../enterprise/microsoft-365-secure-sign-in.md#mfa) | Microsoft 365 E3 of E5 |
| Configuratie van identiteiten en apparaattoegang | Instellingen en beleidsregels voor de aanbevolen functies en de instellingen van deze te combineren met voorwaardelijke toegang, intune en Azure AD Identity Protection-beleid om te bepalen of een bepaalde toegangsaanvraag moet worden toegewezen en onder welke voorwaarden.  | [Configuratie van identiteiten en apparaattoegang](../security/office-365-security/microsoft-365-policies-configurations.md) | Microsoft 365 E3 of E5 |
| Azure AD Identity Protection | Beveilig beveiliging tegenstrijdige gegevens, waarbij een kwaadwillende persoon de accountnaam en het wachtwoord van een gebruiker bepaalt om toegang te krijgen tot de cloudservices en-gegevens van een organisatie. | [Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection) | Microsoft 365 E5 of Microsoft 365 E3 met de identiteit & invoegtoepassing Bedreigingsbeveiliging |
|  |  |  |



## <a name="results-of-step-3"></a>Resultaten van stap 3

Voor de identiteit van uw Microsoft 365-Tenant hebt u het volgende vastgesteld:

- Welk identiteits model moet worden gebruikt.
- Hoe u sterke gebruikers toegang en Apparaattoegang afdwingt.

Hier ziet u een voorbeeld van een Tenant met de nieuwe Hybrid Identity Elements gemarkeerd.

![Voorbeeld van hybride identiteit voor een Tenant](../media/tenant-management-overview/tenant-management-tenant-build-step3.png)

In deze afbeelding is de Tenant:

- Een AD DS-forest dat wordt gesynchroniseerd met de Azure AD-Tenant met behulp van een DirSync-server en Azure AD Connect.
- Een kopie van de AD DS-gebruikersaccounts en andere objecten uit de AD DS-forest.
- Een set voorwaardelijke toegangsbeleidsregels waarmee u de beveiliging van gebruikers en toegangsrechten afdwingt op basis van het gebruikersaccount. 

## <a name="ongoing-maintenance-for-identity"></a>Voortdurend onderhoud van identiteit

Het kan zijn dat u het volgende moet doen:

- Gebruikersaccounts en groepen toevoegen of wijzigen. Voor alleen de Cloud-identiteit moet u uw gebruikers en groepen in de Cloud onderhouden met hulpprogramma's van Azure AD, zoals het Microsoft 365-Beheercentrum of PowerShell. Voor Hybrid Identity onderhoudt u uw on-premises gebruikers en groepen met hulpmiddelen voor AD DS.
- Voeg de identiteits-en Apparaattoegang-configuratie toe of wijzig deze voor het afdwingen van aanmeld beveiligingsvereisten.

## <a name="next-step"></a>Volgende stap

[![Stap 4. Uw on-premises Office-servers en-gegevens migreren](../media/tenant-management-overview/tenant-management-step-grid-migration.png)](tenant-management-migration.md)

Ga door [met het migreren](tenant-management-migration.md) van uw on-premises Office-servers en hun gegevens naar microsoft 365.
