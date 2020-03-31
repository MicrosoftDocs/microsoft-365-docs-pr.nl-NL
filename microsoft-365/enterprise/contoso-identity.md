---
title: Identiteit voor Contoso Corporation
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Hoe Contoso gebruikmaakt van Identiteit als een service (IDaaS) en cloud-based verificatie voor haar werknemers en federatieve verificatie voor haar partners en klanten verstrekt.
ms.openlocfilehash: 77c90740fd39080ccc204552bc8407aa107e354a
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/13/2020
ms.locfileid: "42812762"
---
# <a name="identity-for-the-contoso-corporation"></a>Identiteit voor Contoso Corporation

Microsoft biedt een Identiteit als een service (IDaaS)aan voor zijn cloud-diensten met Azure Active Directory (Azure AD). Om Microsoft 365 Enterprise toe te passen, moest de IDaaS-oplossing van Contoso gebruikmaken van de lokale identiteitsprovider, maar wel met federatieve verificatie met hun bestaande vertrouwde derde identiteitsproviders.

## <a name="contosos-active-directory-domain-services-forest"></a>Contoso‘s Active Directory Domain Services-forest

Contoso gebruikt één Active Directory Domain Services-forest (AD DS) voor contoso.com met zeven subdomeinen, één voor elke regio van de wereld. De hoofdkantoren, regionale regiokantoren en satellietkantoren bevatten domeincontrollers voor lokale verificatie en autorisatie.

Dit is het Contoso-forest met regionale domeinen voor de verschillende delen van de wereld met regionale hubs.

![Het forest en de domeinen van Contoso wereldwijd](../media/contoso-identity/contoso-identity-fig1.png)
 
Contoso wilde de accounts en groepen in het contoso.com-forest gebruiken voor verificatie en machtiging voor de werkbelastingen en services van zijn Microsoft 365.

## <a name="contosos-federated-authentication-infrastructure"></a>De federatieve verificatie-infrastructuur van Contoso

Met Contoso kunnen:

- gebruikers hun Microsoft, Facebook of Google Mail-accounts gebruiken om in te loggen op hun publieke website.
- leveranciers en partners hun LinkedIn, Salesforce of Google mail-accounts gebruiken om zich aan te melden bij het extranet van de partner.

Dit is de Contoso-DMZ met een openbare website, een partner extranet en een set Active Directory Federation Services-servers (AD FS). De DMZ is verbonden met het internet waar de klanten, partners en Internet Services zijn te vinden.

![Ondersteuning van Contoso voor federatieve verificatie voor klanten en partners](../media/contoso-identity/contoso-identity-fig2.png)
 
Met AD FS-servers in het DMZ wordt de verificatie van de inloggegevens van de klant door hun identiteisproviders vergemakkelijkt voor toegang tot de openbare website en inloggegevens van partners voor toegang tot het partner-extranet.

Contoso besloot de infrastructuur te behouden en deze in te zetten voor klant- en partner-authenticaties. De architecten van de identiteits-infrastructuur onderzoeken de conversie van deze infrastructuur naar Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) en [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles)-oplossingen.

## <a name="hybrid-identity-with-password-hash-synchronization-for-cloud-based-authentication"></a>Hybride identiteit met wachtwoord-hash-synchronisatie voor cloud-based verificatie

Contoso wilde een lokale AD DS-forest gebruiken voor verificatie bij cloudresources van Microsoft 365. Ze besloten wachtwoord-hash-synchronisatie (PHS) toe te passen.

PHS synchroniseert het lokale AD DS-forest met de Azure AD-tenant van hun Microsoft 365 Enterprise-abonnement, en kopieert gebruikers-en groepsaccounts en een gehashte versie van gebruikersaccountswachtwoorden. 

Om de doorlopende adreslijstsynchronisatie uit te voeren, heeft Contoso het Azure AD Connect-hulpprogramma geïmplementeerd op een server op zijn datacenter in Parijs. 

Dit is de server met Azure AD Connect die het AD DS-forest van Contoso verzoekt om wijzigingen aan te brengen. Vervolgens worden deze wijzigingen gesynchroniseerd met de Azure AD-tenant.

![PHS adreslijstsynchronisatie-infrastructuur van Contoso](../media/contoso-identity/contoso-identity-fig4.png)
 
## <a name="conditional-access-policies-for-identity-and-device-access"></a>Voorwaardelijk toegangsbeleid voor identiteits- en apparaattoegang

Contoso heeft een set van Azure AD-en Intune [Voorwaardelijk toegangsbeleidsregels gemaakt](identity-access-policies.md) voor drie beveiligingsniveaus:

- **Basis**beveiligingsmaatregelen gelden voor alle gebruikersaccounts
- **Gevoelige** beveiligingsmaatregelen zijn van toepassing op leidinggevenden en directie-medewerkers
- **Zeer gereguleerde** beveiligingsmaatregelen zijn van toepassing op specifieke gebruikers van de Financiële, juridische en onderzoeksafdelingen die toegang hebben tot zeer gereglementeerde gegevens

Hieronder ziet u Contoso‘s resultatenset van Voorwaardelijke toegangsbeleidsregels voor apparaten. 

![Contoso‘s Voorwaardelijke toegangsbeleidsregels voor identiteits- en apparaattoegang](../media/contoso-identity/contoso-identity-fig5.png)
 
## <a name="next-step"></a>Volgende stap

[Lees](contoso-win10.md) hier hoe Contoso zijn infrastructuur voor Microsoft-Endpoint Configuratiebeheer gebruikt voor het implementeren en onderhouden van Windows 10 Enterprise in de hele organisatie.

## <a name="see-also"></a>Zie ook

[Identiteit voor Microsoft 365 Enterprise](identity-infrastructure.md)

[Implementatiehandleiding](deploy-microsoft-365-enterprise.md)

[Testlabrichtlijnen](m365-enterprise-test-lab-guides.md)
