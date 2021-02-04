---
title: Ondersteuning voor microsoft 365-client- en -services-app
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
description: In dit artikel vindt u meer informatie over ondersteuning voor microsoft 365-client- en -services-apps.
ms.openlocfilehash: 4e32e39281175ed66970a358ff632c2ddbb3ac1a
ms.sourcegitcommit: 8e696c084d097520209c864140af11aa055b979e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097478"
---
# <a name="microsoft-365-client-and-services-app-support"></a>Ondersteuning voor microsoft 365-client- en -services-app

Microsoft ondersteunt een groot aantal functies voor beveiliging, verificatie en naleving om klantgegevens veilig te houden en IT-beheerders in staat te stellen beleidsregels aan te passen in het Microsoft 365-beheercentrum voor hun gebruikers. De volgende functies zijn slechts een subset van de vele bedrijfsfuncties die u kunt configureren, afhankelijk van uw Microsoft 365-abonnement.

## <a name="client-and-service-support"></a>Client- en serviceondersteuning

### <a name="continuous-access-evaluation-preview"></a>Continue evaluatie van toegang (voorbeeld)

Continue evaluatie van toegang wordt geïmplementeerd door services, zoals Exchange Online, SharePoint Online en Teams, in te stellen om u te abonneren op kritieke gebeurtenissen in Azure Active Directory, zodat deze gebeurtenissen in realtime kunnen worden geëvalueerd en afgedwongen. Evaluatie van kritieke gebeurtenissen is niet afhankelijk van beleidsregels voor voorwaardelijke toegang, dus is beschikbaar in elke tenant.

De volgende gebeurtenissen worden momenteel geëvalueerd:

- Een gebruikersaccount wordt verwijderd of uitgeschakeld
- Het wachtwoord van een gebruiker wordt gewijzigd of opnieuw ingesteld
- Meervoudige verificatie is ingeschakeld voor de gebruiker
- Beheerder trekt alle vernieuwingstokens voor een gebruiker expliciet in
- Verhoogd gebruikersrisico gedetecteerd door Azure AD Identity Protection

Zie Continue toegangsevaluatie (preview) voor meer informatie over continue toegangsevaluatie voor ondersteuning van client- en [services-apps.](/azure/active-directory/conditional-access/concept-continuous-access-evaluation)

## <a name="client-support"></a>Clientondersteuning

### <a name="certificate-based-authentication"></a>Op certificaat gebaseerde verificatie

Verificatie op basis van certificaten (CBA) is het gebruik van een digitaal certificaat om een gebruiker, computer of apparaat te identificeren voordat u toegang verleent tot een bron, netwerk, toepassing of service. In gebruikersverificatie wordt deze vaak geïmplementeerd in samenwerking met traditionele methoden, zoals gebruikersnamen en wachtwoorden.

Sommige traditionele oplossingen werken alleen voor gebruikers, zoals authenticatie en een eentijdswachtwoorden (OTP). Met verificatie op basis van certificaten kan dezelfde oplossing voor alle eindpunten worden gebruikt. gebruikers, apparaten en het groeiende Internet of Things (IoT).

Zie Microsoft [365 Client App Support:](microsoft-365-client-support-certificate-based-authentication.md)Op certificaten gebaseerde verificatie voor ondersteuning op basis van een certificaat voor client- en services-app voor meer informatie over verificatie op basis van certificaten.

### <a name="conditional-access"></a>Voorwaardelijke toegang

Voorwaardelijke toegang is het hulpmiddel dat door Azure Active Directory wordt gebruikt om signalen samen te brengen, beslissingen te nemen en organisatietoegangsbeleid af te dwingen. Voorwaardelijke toegang staat centraal in het nieuwe model voor besturingselementen op identiteitsgestuurde manier.

Beleidsregels voor voorwaardelijke toegang zijn instructies voor het verlenen van toegang tot resources. Als een gebruiker toegang wil tot een bron, moet de gebruiker een actie voltooien. Veelvoorkomende signalen die voorwaardelijke toegang kan gebruiken bij het maken van een toegangsbeslissing tot het beleid zijn:

- Lidmaatschap van gebruiker of groep
- Ip-locatiegegevens
- Apparaatgegevens
- Toepassingsgegevens
- Detectie van realtime- en berekende risico's
- Microsoft Cloud App Security (MCAS)

Wanneer u deze toegangsbeslissingen neemt, kan het beleid verschillende acties uitvoeren:

- Het beleid kan toegang blokkeren: deze configuratie is de meest beperkende actie en voorkomt dat de gebruiker toegang heeft tot de bron.
- Het beleid kan toegang verlenen: deze configuratie is een minder beperkende beslissing en vereist mogelijk nog een of meer van de volgende opties:

    - Meervoudige verificatie
    - Het apparaat dat moet worden gemarkeerd als compatibel
    - Het apparaat is een hybride versie van Azure AD die is aangesloten op
    - Een goedgekeurde client-app
    - Beveiligingsbeleid voor apps geconfigureerd (preview)

Zie voor meer informatie over voorwaardelijke toegang voor ondersteuning van client- en services-apps:

- [Ondersteuning voor Microsoft 365-client-apps: Voorwaardelijke toegang op apparaten](microsoft-365-client-support-conditional-access.md)

### <a name="mobile-application-management"></a>Mobile Application Management

Gebruikers hebben vaak vanaf hetzelfde mobiele apparaat toegang tot zowel organisatiedocumenten als persoonlijke documenten, e-mail en gegevens. Deze apparaten zijn vaak persoonlijk en moeten worden geconfigureerd om zowel organisatiegegevens als de persoonlijke privacy van de gebruiker te beschermen.

Wanneer een gebruiker toegang heeft tot organisatiegegevens, moet de organisatie erop vertrouwen dat organisatiebeleid, zoals configuratiebeleid en beveiligingsbeleid, wordt toegepast om organisatiegegevens op het apparaat te helpen beschermen. Bovendien moet de persoonlijke inhoud van de gebruiker op het apparaat buiten het beheer van de organisatie blijven.

Voor inhoud die door de organisatie wordt beheerd, kunt u beleid voor toepassingsbeheer toepassen om te bepalen hoe gegevens worden gebruikt en hoe ze worden gebruikt met Microsoft Intune. De volgende acties worden bijvoorbeeld ondersteund:

- De beheerde inhoud van de organisatie (ook wel organisatiegegevens genoemd) op afstand wissen
- Voorkomen dat inhoud van organisaties op niet-organisatielocaties wordt geplaatst
- Een pincode vereisen om toegang te krijgen tot inhoud van uw organisatie
- Voorkomen dat beheerde apps worden uitgevoerd op apparaten die zijn overbroken of geroot
- Voorkomen dat inhoud van organisaties wordt opgeslagen in niet-goedgekeurde cloudopslagproviders
- Voorkomen dat niet-goedgekeurde inhoud wordt overgebracht naar beheerde toepassingen
- Toegang tot inhoud van de organisatie alleen toestaan nadat een beleid is toegepast
- Toepassingsconfiguratie leveren om het gedrag en de instellingen van de toepassing te beheren
- De beheerde toepassing beperken tot een gedefinieerde identiteit door het uitschakelen van mogelijkheden voor meerdere identiteiten of persoonlijk gebruik

Zie Wat [is Microsoft Intune-appbeheer?](/mem/intune/apps/app-management)

### <a name="multi-factor-authentication"></a>Meervoudige verificatie

[Meervoudige verificatie (Multi-Factor Authentication, MFA) is een methode voor computertoegangsbeheer waaraan een gebruiker pas toegang wordt verleend nadat diverse afzonderlijke bewijsstukken voor een verificatiemechanisme zijn verstrekt. Bij deze methode worden meestal ten minste twee van de volgende categorieën gebruikt:

- Kennis (iets wat ze weten)
- In bezit komen (iets wat ze hebben)
- Inherence (iets wat ze zijn)

Zie Microsoft [365 Client App Support: Meervoudige](microsoft-365-client-support-multi-factor-authentication.md)verificatie voor meer informatie over meervoudige verificatie voor client- en services-app-ondersteuning.

### <a name="single-sign-on"></a>Eenmalige aanmelding

Eenmalige aanmelding (SSO) zorgt voor beveiliging en gemak wanneer uw gebruikers zich aanmelden bij toepassingen in Azure Active Directory. Met een enkelvoudige aanmelding melden gebruikers zich één keer aan met één account voor toegang tot on-premises Active Directory Domain Services (AD DS) apparaten die lid zijn van een domein, SaaS-toepassingen (software as a service) en webtoepassingen in uw organisatie.

Zie microsoft 365 Client App Support: Een enkele aanmelding voor ondersteuning door de [Microsoft 365-client-app](microsoft-365-client-support-single-sign-on.md)voor meer informatie over een eenpersoons aanmelden voor app-ondersteuning voor klanten en services.

## <a name="services-support"></a>Ondersteuning voor services

### <a name="modern-authentication"></a>Moderne verificatie

Met moderne verificatie kunnen nieuwe scenario's voor klanten worden geverifieerd met Office 365 en tenantbeheerders om specifieke verificatievereisten voor de Office 365-tenancy af te dwingen, zoals:

- Ondersteuning voor meervoudige verificatie voor administratieve interactie met de tenancy en services en interactie tussen eindgebruikers met toepassingen en hun gegevens
- Voorwaardelijke toegang
- Aanmelden bij een id-provider op basis van SAML
- Smartcardlogboek op pc's
- Verificatie op basis van certificaten op mobiele apparaten
- Het verzenden van referenties via basisverificatie is niet meer vereist.

Zie Verificatie versus autorisatie voor meer informatie over ondersteuning voor moderne [verificatieservices.](/azure/active-directory/develop/authentication-vs-authorization)

### <a name="azure-active-directory-conditional-access"></a>Voorwaardelijke toegang in Azure Active Directory

Met regels voor voorwaardelijke toegang van Azure Active Directory (Azure AD) kunnen klanten de toegang tot onlineservices controleren op basis van kenmerken zoals apparaat compliance of netwerklocatie. De volgende oplossingen kunnen worden gebruikt:

- Voorwaardelijke toegang op basis van multi-factor authentication in Azure AD
- Voorwaardelijke toegang op basis van Azure AD-locatie
- Voorwaardelijke toegang op basis van Azure AD-apparaat

Regels voor voorwaardelijke toegang van Azure AD worden per toepassing toegepast en klanten kunnen de toegang controleren op basis van verschillende voorwaarden. Met [MDM (Mobile Device Management) of Intune](/mem/intune/fundamentals/what-is-device-management)moeten klanten de toegang tot Microsoft 365 kunnen beperken tot alleen die gebruikers die een organisatieapparaat gebruiken of die hun persoonlijke apparaat voor beheer hebben geregistreerd. Klanten kunnen bijvoorbeeld regels voor voorwaardelijke toegang configureren om besturingselementen af te dwingen, zoals:

- Alleen toegang toestaan vanaf apparaten die compatibel zijn met een domein of die compatibel zijn met een domein
- Meervoudige verificatie afdwingen voor alle toegang tot Exchange Online-services

Zie Wat is voorwaardelijke toegang voor Azure Active Directory voor meer informatie over [voorwaardelijke toegang in Azure Active Directory?](/azure/active-directory/conditional-access/overview)

### <a name="tls-12-support"></a>Ondersteuning voor TLS 1.2

Om onze klanten de beste versleuteling te bieden, is Microsoft van plan de ondersteuning voor TLS-versies (Transport Layer Security) versie 1.0 en 1.1 in Office 365 en Office 365 GCC te stoppen.

We begrijpen dat de beveiliging van uw gegevens belangrijk is en we streven naar transparantie met betrekking tot wijzigingen die van invloed kunnen zijn op uw gebruik van de TLS-service. Het is raadzaam dat alle combinaties van clientserver en browserserver met TLS 1.2 (of een latere versie) gebruiken om de verbinding met Office 365-services te behouden. Mogelijk moet u bepaalde combinaties van client-server en browserserver bijwerken.

Zie Voorbereiden voor [TLS 1.2 in Office 365 en Office 365 GCC](/microsoft-365/compliance/prepare-tls-1.2-in-office-365)voor meer informatie over ondersteuning voor TLS 1.2 en services.
