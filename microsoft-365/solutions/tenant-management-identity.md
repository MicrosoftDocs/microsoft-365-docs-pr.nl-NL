---
title: Stap 3. Identiteit voor uw Microsoft 365 voor enterprise-tenants
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
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: Implementeer het juiste identiteitsmodel voor uw Microsoft 365-tenants en dwing sterke aanmeldingen voor gebruikers af.
ms.openlocfilehash: ca545e0152b567cd566ce939e369988f864042a9
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/03/2021
ms.locfileid: "50407168"
---
# <a name="step-3-identity-for-your-microsoft-365-for-enterprise-tenants"></a>Stap 3. Identiteit voor uw Microsoft 365 voor enterprise-tenants

Uw Microsoft 365-tenant bevat een Azure Active Directory-tenant (Azure AD) voor het beheren van identiteiten en verificatie voor aanmeldingen. Het op de juiste manier configureren van uw identiteitsinfrastructuur is essentieel voor het beheren van de gebruikerstoegang en machtigingen van Microsoft 365 voor uw organisatie.

## <a name="cloud-only-vs-hybrid"></a>Alleen in de cloud versus hybride

Hier zijn de twee soorten identiteitsmodellen en de beste passendheid en voordelen.


| Model | Beschrijving | Hoe Microsoft 365 gebruikersreferenties verifieert | Het beste voor | Grootste voordeel |
|:-------|:-----|:-----|:-----|:-----|
| Alleen in de cloud | Gebruikersaccount bestaat alleen in de Azure AD-tenant voor uw Microsoft 365-tenant. | De Azure AD-tenant voor uw Microsoft 365-tenant voert de verificatie uit met het cloudidentiteitsaccount. | Organisaties die geen on-premises AD DS hebben of nodig hebben. | Eenvoudig te gebruiken. Er zijn geen extra directory-hulpprogramma's of -servers vereist. |
| Hybride |  Gebruikersaccount bestaat in uw on-premises Active Directory Domain Services (AD DS) en een kopie bevindt zich ook in de Azure AD-tenant voor uw Microsoft 365-tenant. Azure AD Connect wordt uitgevoerd op een on-premises server om AD DS-wijzigingen te synchroniseren met uw Azure AD-tenant. Het gebruikersaccount in Azure AD kan ook een gehashte versie bevatten van het wachtwoord van het ad DS-gebruikersaccount dat al is gehasht. | De Azure AD-tenant voor uw Microsoft 365-tenant verwerkt het verificatieproces of leidt de gebruiker om naar een andere identiteitsprovider. | Organisaties die AD DS of een andere identiteitsprovider gebruiken. | Gebruikers kunnen dezelfde referenties gebruiken bij het openen van on-premises bronnen of cloudbronnen. |
||||||

Dit zijn de basisonderdelen van identiteiten die alleen in de cloud beschikbaar zijn.
 
![Basisonderdelen van identiteiten in de cloud](../media/about-microsoft-365-identity/cloud-only-identity.png)

In deze afbeelding melden on-premises en externe gebruikers zich aan met accounts in de Azure AD-tenant van hun Microsoft 365-tenant.

Dit zijn de basisonderdelen van hybride identiteit.

![Basisonderdelen van hybride identiteit](../media/about-microsoft-365-identity/hybrid-identity.png)

In deze afbeelding melden on-premises en externe gebruikers zich aan bij hun Microsoft 365-tenant met accounts in de Azure AD-tenant die zijn gekopieerd vanuit hun on-premises AD DS.

## <a name="synchronizing-your-on-premises-ad-ds"></a>Uw on-premises AD DS synchroniseren

Afhankelijk van de behoeften en technische vereisten van uw bedrijf, is het hybride identiteitsmodel en adreslijstsynchronisatie de meest gebruikte optie voor zakelijke klanten die over gaan op Microsoft 365. Met adreslijstsynchronisatie kunt u identiteiten beheren in uw AD DS, zodat alle updates voor gebruikersaccounts, groepen en contactpersonen worden gesynchroniseerd met de Azure AD-tenant van uw Microsoft 365-tenant.

>[!Note]
>Wanneer AD DS-gebruikersaccounts voor het eerst worden gesynchroniseerd, wordt aan deze gebruikers niet automatisch een Microsoft 365-licentie toegewezen en hebben ze geen toegang tot Microsoft 365-services, zoals e-mail. U moet ze eerst een gebruikslocatie toewijzen. Wijs vervolgens een licentie toe aan deze gebruikersaccounts, afzonderlijk of dynamisch via groepslidmaatschap.
>

Hier zijn de twee typen verificatie bij het gebruik van het model voor hybride identiteit.

| Verificatietype | Beschrijving |
|:-------|:-----|
| Beheerde verificatie | Azure AD verwerkt het verificatieproces met behulp van een lokaal opgeslagen hashed versie van het wachtwoord of verzendt de referenties naar een on-premises softwareagent die moet worden geverifieerd door de on-premises AD DS. <br> <br>  Er zijn twee typen beheerde verificatie: WACHTWOORD-hashsynchronisatie (PHS) en Pass Through-verificatie (PTA). Met PHS voert Azure AD de verificatie zelf uit. Met PTA wordt de verificatie door AD DS uitgevoerd in Azure AD. |
| Federatieve verificatie | Azure AD stuurt de clientcomputer die verificatie aanvraagt om naar een andere identiteitsprovider. |
|  |  |

Zie [de juiste verificatiemethode voor](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) meer informatie.

## <a name="enforcing-strong-sign-ins"></a>Sterke aanmeldingen afdwingen

Gebruik de functies en mogelijkheden in de volgende tabel als u de beveiliging van aanmeldingen van gebruikers wilt vergroten.

| Mogelijkheid | Beschrijving | Meer informatie | Licentievereisten |
|:-------|:-----|:-----|:-----|:-----|
| Windows Hello voor Bedrijven | Wachtwoorden worden vervangen door sterke tweestapsverificatie wanneer u zich aanmeldt op een Windows-apparaat. De twee factoren zijn een nieuw type gebruikersreferentie dat is gekoppeld aan een apparaat en een biometrisch kenmerk of een pincode. | [Overzicht van Windows Hello voor Bedrijven](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview) | Microsoft 365 E3 of E5 |
| Azure AD-wachtwoordbeveiliging | Detecteert en blokkeert bekende zwakke wachtwoorden en hun varianten en kan ook aanvullende zwakke termen blokkeren die specifiek zijn voor uw organisatie. | [Wachtwoordbeveiliging voor Azure AD configureren](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) | Microsoft 365 E3 of E5 |
| Meervoudige verificatie (MFA) gebruiken | MFA vereist dat gebruikersmeldingen onderworpen zijn aan een extra verificatie buiten het wachtwoord van het gebruikersaccount, zoals verificatie met een smartphone-app of een sms-bericht dat naar een smartphone is verzonden. Bekijk [deze video](https://support.microsoft.com/office/set-up-multi-factor-authentication-in-microsoft-365-business-a32541df-079c-420d-9395-9d59354f7225) voor instructies over hoe gebruikers MFA instellen. | [MFA voor Microsoft 365 voor ondernemingen](../enterprise/microsoft-365-secure-sign-in.md#mfa) | Microsoft 365 E3 of E5 |
| Configuratie van identiteiten en apparaattoegang | Instellingen en beleid die bestaan uit aanbevolen vereiste functies en de instellingen in combinatie met beleidsregels voor voorwaardelijke toegang, Intune en Azure AD Identity Protection die bepalen of een bepaalde toegangsaanvraag moet worden verleend en onder welke voorwaarden.  | [Configuratie van identiteiten en apparaattoegang](../security/office-365-security/microsoft-365-policies-configurations.md) | Microsoft 365 E3 of E5 |
| Azure AD Identity Protection | Bescherm u tegen referentiecompromitteerdheid, waarbij een aanvaller de accountnaam en het wachtwoord van een gebruiker bepaalt om toegang te krijgen tot de cloudservices en gegevens van een organisatie. | [Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection) | Microsoft 365 E5 of Microsoft 365 E3 met de invoeg toevoegen & Threat Protection |
|  |  |  |



## <a name="results-of-step-3"></a>Resultaten van stap 3

Voor identiteit voor uw Microsoft 365-tenant hebt u het volgende vastgesteld:

- Welk identiteitsmodel moet worden gebruikt.
- Hoe u sterke toegang tot gebruikers en apparaten afdwingt.

Hier is een voorbeeld van een tenant met de nieuwe hybride identiteitselementen gemarkeerd.

![Voorbeeld van hybride identiteit voor een tenant](../media/tenant-management-overview/tenant-management-tenant-build-step3.png)

In deze afbeelding heeft de tenant:

- Een AD DS-forest die wordt gesynchroniseerd met de Azure AD-tenant via een DirSync-server en Azure AD Connect.
- Een kopie van de AD DS-gebruikersaccounts en andere objecten uit de AD DS-forest.
- Een reeks beleidsregels voor voorwaardelijke toegang voor het afdwingen van veilige aanmeldingen voor gebruikers en toegang op basis van het gebruikersaccount. 

## <a name="ongoing-maintenance-for-identity"></a>Doorlopend onderhoud voor identiteit

Oplopende basis moet u mogelijk het volgende doen:

- Gebruikersaccounts en -groepen toevoegen of wijzigen. Voor identiteiten in de cloud blijven uw cloudgebruikers en -groepen behouden met Azure AD-hulpprogramma's zoals het Microsoft 365-beheercentrum of PowerShell. Voor hybride identiteiten onderhoudt u uw on-premises gebruikers en groepen met AD DS-hulpprogramma's.
- Voeg uw configuratie voor identiteits- en apparaattoegang toe of wijzig deze om beveiligingsvereisten voor aanmelding af te dwingen.

## <a name="next-step"></a>Volgende stap

[![Stap 4. Uw on-premises Office-servers en -gegevens migreren](../media/tenant-management-overview/tenant-management-step-grid-migration.png)](tenant-management-migration.md)

Ga verder [met de migratie](tenant-management-migration.md) om uw on-premises Office-servers en hun gegevens te migreren naar Microsoft 365.
