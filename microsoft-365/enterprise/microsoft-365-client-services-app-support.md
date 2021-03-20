---
title: Ondersteuning voor microsoft 365-client- en services-app
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
search.appverid:
- MET150
f1.keywords:
- NOCSH
description: In dit artikel vindt u meer informatie over ondersteuning voor microsoft 365-client- en services-apps.
ms.openlocfilehash: e380efffc1bf29cbd4d3a77d32e4d1f8b2994da3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905006"
---
# <a name="microsoft-365-client-and-services-app-support"></a>Ondersteuning voor microsoft 365-client- en services-app

Microsoft ondersteunt een breed scala aan beveiligings-, verificatie- en compliancefuncties om klantgegevens veilig te houden en it-beheerders in staat te stellen beleidsregels aan te passen in het Microsoft 365-beheercentrum voor hun gebruikers. De volgende functies zijn slechts een subset van de vele bedrijfsfuncties die u kunt configureren, afhankelijk van uw Microsoft 365-abonnement.

## <a name="client-and-service-support"></a>Client- en serviceondersteuning

### <a name="continuous-access-evaluation-preview"></a>Evaluatie van continue toegang (voorbeeld)

Continue toegangsevaluatie wordt geïmplementeerd door services, zoals Exchange Online, SharePoint Online en Teams, in te staat te stellen zich te abonneren op kritieke gebeurtenissen in Azure Active Directory, zodat deze gebeurtenissen in realtime kunnen worden geëvalueerd en afgedwongen. Evaluatie van kritieke gebeurtenissen is niet afhankelijk van beleid voor voorwaardelijke toegang, dus is beschikbaar in elke tenant.

De volgende gebeurtenissen worden momenteel geëvalueerd:

- Een gebruikersaccount wordt verwijderd of uitgeschakeld
- Het wachtwoord voor een gebruiker wordt gewijzigd of opnieuw ingesteld
- Meervoudige verificatie is ingeschakeld voor de gebruiker
- Beheerder trekt alle vernieuwingstokens voor een gebruiker expliciet in
- Verhoogd gebruikersrisico gedetecteerd door Azure AD Identity Protection

Zie Continue toegangsevaluatie [(preview)](/azure/active-directory/conditional-access/concept-continuous-access-evaluation)voor meer informatie over continue toegangsevaluatie voor ondersteuning voor client- en services-apps.

## <a name="client-support"></a>Clientondersteuning

### <a name="certificate-based-authentication"></a>Op certificaat gebaseerde verificatie

Certificaatverificatie (CBA) is het gebruik van een digitaal certificaat om een gebruiker, computer of apparaat te identificeren voordat u toegang verleent tot een resource, netwerk, toepassing of service. In gebruikersverificatie wordt deze vaak geïmplementeerd in coördinatie met traditionele methoden, zoals gebruikersnamen en wachtwoorden.

Sommige traditionele oplossingen werken alleen voor gebruikers, zoals biometrie en een een time passwords (OTP). Met verificatie op basis van certificaten kan dezelfde oplossing worden gebruikt voor alle eindpunten. gebruikers, apparaten en het groeiende Internet of Things (IoT).

Zie [Microsoft 365 Client App Support: Certificate-based Authentication](microsoft-365-client-support-certificate-based-authentication.md)voor meer informatie over verificatie op basis van certificaten voor client- en services-app-ondersteuning.

### <a name="conditional-access"></a>Voorwaardelijke toegang

Voorwaardelijke toegang is het hulpprogramma dat door Azure Active Directory wordt gebruikt om signalen samen te brengen, beslissingen te nemen en beleid voor organisatietoegang af te dwingen. Voorwaardelijke toegang staat centraal in het nieuwe, op identiteitsgestuurde besturingselementmodel.

Beleid voor voorwaardelijke toegang zijn als-dan-instructies voor het verlenen van toegang tot resources. Als een gebruiker toegang wil tot een resource, moet de gebruiker een actie voltooien. Veelvoorkomende signalen die Voorwaardelijke toegang kan gebruiken bij het maken van een beleidstoegangsbeslissing zijn:

- Lidmaatschap van gebruiker of groep
- IP-locatiegegevens
- Apparaatgegevens
- Toepassingsgegevens
- Realtime en berekende risicodetectie
- Microsoft Cloud App Security (MCAS)

Wanneer u deze toegangsbeslissingen neemt, kunnen de beleidsregels verschillende acties uitvoeren:

- Het beleid kan toegang blokkeren: Deze configuratie is de meest beperkende actie en voorkomt dat de gebruiker toegang heeft tot de resource.
- Het beleid kan toegang verlenen: deze configuratie is een minder beperkend besluit en kan nog steeds een of meer van de volgende opties vereisen:

    - Meervoudige verificatie
    - Het apparaat dat moet worden gemarkeerd als compatibel
    - Het apparaat is hybride Azure AD-lid
    - Een goedgekeurde client-app
    - Beleid voor app-beveiliging geconfigureerd (voorbeeld)

Zie voor meer informatie over ondersteuning voor voorwaardelijke toegang voor client- en services-apps:

- [Microsoft 365 Client App-ondersteuning: Voorwaardelijke toegang op apparaatbasis](microsoft-365-client-support-conditional-access.md)

### <a name="mobile-application-management"></a>Mobiel toepassingsbeheer

Gebruikers hebben vaak toegang tot zowel organisatie- als persoonlijke documenten, e-mail en gegevens vanaf hetzelfde mobiele apparaat. Deze apparaten zijn vaak persoonlijk eigendom en moeten worden geconfigureerd om zowel de organisatiegegevens als de persoonlijke privacy van de gebruiker te beschermen.

Wanneer een gebruiker toegang heeft tot organisatiegegevens, moet de organisatie erop vertrouwen dat organisatiebeleid, zoals configuratiebeleid en beveiligingsbeleid, wordt toegepast om organisatiegegevens op het apparaat te beschermen. Bovendien moet de persoonlijke inhoud van de gebruiker op het apparaat buiten het beheer van de organisatie blijven.

Voor door de organisatie beheerde inhoud kunt u beleidsregels voor toepassingsbeheer toepassen om te bepalen hoe gegevens worden gebruikt, toegankelijk, gedeeld en gebruikt met Microsoft Intune. De volgende acties worden bijvoorbeeld ondersteund:

- De beheerde organisatie-inhoud op afstand wissen (ook wel organisatiegegevens genoemd)
- Voorkomen dat organisatie-inhoud in niet-organisatielocaties wordt ge past
- Een pincode vereisen om toegang te krijgen tot organisatie-inhoud
- Voorkomen dat beheerde apps worden uitgevoerd op jailbroken of geroote apparaten
- Voorkomen dat organisatieinhoud wordt opgeslagen in niet-goedgekeurde cloudopslagproviders
- Voorkomen dat niet-goedgekeurde inhoud wordt overgebracht naar beheerde toepassingen
- Toegang tot organisatie-inhoud alleen toestaan nadat beleid is toegepast
- Toepassingsconfiguratie leveren om het gedrag en de instellingen van de toepassing te beheren
- De beheerde toepassing beperken tot een gedefinieerde identiteit door mogelijkheden voor meerdere identiteiten of persoonlijk gebruik uit te stellen

Zie Wat [is Microsoft Intune-appbeheer?](/mem/intune/apps/app-management) voor meer informatie over het beheer van mobiele toepassingen met Microsoft Intune.

### <a name="multi-factor-authentication"></a>Meervoudige verificatie

[Meervoudige verificatie (MFA) is een methode voor computertoegangsbeheer waarbij een gebruiker alleen toegang krijgt nadat hij of zij verschillende afzonderlijke bewijsstukken aan een verificatiemechanisme heeft verstrekt. Deze methode gebruikt meestal ten minste twee van de volgende categorieën:

- Kennis (iets wat ze weten)
- Bezit (iets wat ze hebben)
- Inherence (iets wat ze zijn)

Zie [Microsoft 365 Client App Support: Meervoudige verificatie](microsoft-365-client-support-multi-factor-authentication.md)voor ondersteuning voor client- en services-apps voor meer informatie over meervoudige verificatie.

### <a name="single-sign-on"></a>Eenmalige aanmelding

Eenmalige aanmelding (SSO) voegt beveiliging en gemak toe wanneer uw gebruikers zich aanmelden bij toepassingen in Azure Active Directory. Met één aanmelding melden gebruikers zich eenmaal aan met één account om toegang te krijgen tot on-premises Ad DS-domeinapparaten (Ad DS), software as a service-toepassingen (SaaS) en webtoepassingen in uw organisatie.

Zie [Microsoft 365 Client App Support: Single sign-on](microsoft-365-client-support-single-sign-on.md)voor meer informatie over ondersteuning voor een enkele aanmelding voor client- en services-apps.

## <a name="services-support"></a>Services-ondersteuning

### <a name="modern-authentication"></a>Moderne verificatie

Met moderne verificatie kunnen nieuwe scenario's voor klanten worden geverifieerd met Office 365 en voor tenantbeheerders om specifieke verificatievereisten af te dwingen in de office 365-huurovereenkomst, zoals:

- Ondersteuning voor meervoudige verificatie voor administratieve interactie met de huurovereenkomst en services, en interactie tussen eindgebruikers met toepassingen en hun gegevens
- Voorwaardelijke toegang
- Aanmelding op saml-gebaseerde externe identiteitsprovider
- Smartcardlogboek op persoonlijke computers
- Verificatie op basis van certificaten op mobiele apparaten
- Het verzenden van referenties via basisverificatie is niet meer vereist.

Zie Verificatie versus autorisatie voor meer informatie over ondersteuning voor moderne [verificatieservices.](/azure/active-directory/develop/authentication-vs-authorization)

### <a name="azure-active-directory-conditional-access"></a>Voorwaardelijke toegang in Azure Active Directory

Met Azure Active Directory(Azure AD) Voorwaardelijke toegangsregels kunnen klanten de toegang tot onlineservices bepalen op basis van kenmerken zoals apparaat compliance of netwerklocatie. De volgende oplossingen kunnen worden gebruikt:

- Azure AD multi-factor authentication-based Conditional Access
- Voorwaardelijke toegang op basis van Azure AD-locatie
- Voorwaardelijke toegang op Azure AD-apparaat

Azure AD Regels voor voorwaardelijke toegang worden per toepassing toegepast en zijn beschikbaar voor klanten om toegang te controleren op basis van verschillende voorwaarden. Met [MDM (Mobile Device Management) of Intune](/mem/intune/fundamentals/what-is-device-management)kunnen klanten de toegang tot Microsoft 365 beperken tot alleen gebruikers die een organisatieapparaat gebruiken of die hun persoonlijke apparaat hebben geregistreerd voor beheer. Klanten kunnen bijvoorbeeld regels voor voorwaardelijke toegang configureren om besturingselementen af te dwingen, zoals:

- Alleen toegang toestaan vanaf apparaten die domein zijn samengevoegd of domeinconform zijn
- Meervoudige verificatie afdwingen voor alle toegang tot Exchange Online-services

Zie Wat [is voorwaardelijke toegang?](/azure/active-directory/conditional-access/overview) voor meer informatie over voorwaardelijke toegang in Azure Active Directory.

### <a name="tls-12-support"></a>Ondersteuning voor TLS 1.2

Om onze klanten de beste versleuteling te bieden, is Microsoft van plan de ondersteuning voor TLS-versies (Transport Layer Security) 1.0 en 1.1 in Office 365 en Office 365 GCC te stoppen.

We begrijpen dat de beveiliging van uw gegevens belangrijk is en we streven naar transparantie met betrekking tot wijzigingen die van invloed kunnen zijn op uw gebruik van de TLS-service. Het is raadzaam dat alle combinaties van clientservers en browserservers TLS 1.2 (of een latere versie) gebruiken om de verbinding met Office 365-services te behouden. Mogelijk moet u bepaalde combinaties van client-server en browserserver bijwerken.

Zie Voorbereiden op [TLS 1.2 in Office 365 en Office 365 GCC](../compliance/prepare-tls-1.2-in-office-365.md)voor meer informatie over ondersteuning en services van TLS 1.2.