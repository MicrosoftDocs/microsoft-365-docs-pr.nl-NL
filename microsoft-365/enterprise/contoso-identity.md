---
title: Identiteit voor Contoso Corporation
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Hoe Contoso gebruikmaakt van Identiteit als een service (IDaaS) en cloud-based verificatie voor haar werknemers en federatieve verificatie voor haar partners en klanten verstrekt.
ms.openlocfilehash: accd60f6699e7ebf04963213128d1ca1ffc8f7fe
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911070"
---
# <a name="identity-for-the-contoso-corporation"></a>Identiteit voor Contoso Corporation

Microsoft biedt Identity as a Service (IDaaS) in de cloud via Azure Active Directory (Azure AD). Als u Microsoft 365 voor ondernemingen wilt gebruiken, moet de Contoso IDaaS-oplossing hun on-premises identiteitsprovider gebruiken en federatief verificatie opnemen met hun bestaande vertrouwde, externe identiteitsproviders.

## <a name="the-contoso-active-directory-domain-services-forest"></a>Het Contoso Active Directory Domain Services-forest

Contoso gebruikt één AD DS-forest (Active Directory Domain Services) voor contoso com met zeven subdomeinen, één voor elke regio \. ter wereld. De hoofdkantoren, regionale regiokantoren en satellietkantoren bevatten domeincontrollers voor lokale verificatie en autorisatie.

Hier is het Contoso-bos met regionale domeinen voor de verschillende delen van de wereld die regionale hubs bevatten.

![Het forest en de domeinen van Contoso wereldwijd](../media/contoso-identity/contoso-identity-fig1.png)
 
Contoso heeft besloten om de accounts en groepen in het contoso-combos te gebruiken voor verificatie en autorisatie voor de Werkbelasting en services van \. Microsoft 365.

## <a name="the-contoso-federated-authentication-infrastructure"></a>De contoso-federatief verificatie-infrastructuur

Met Contoso kunnen:

- Klanten kunnen hun Microsoft-, Facebook- of Google Mail-accounts gebruiken om zich aan te melden bij de openbare website van het bedrijf.
- Leveranciers en partners kunnen hun LinkedIn-, Salesforce- of Google Mail-accounts gebruiken om zich aan te melden bij het partner-extranet van het bedrijf.

Hier is de Contoso DMZ met een openbare website, een partner extranet en een set AD FS-servers (Active Directory Federation Services). De DMZ is verbonden met internet dat klanten, partners en internetservices bevat.

![Contoso-ondersteuning voor federatief verificatie voor klanten en partners](../media/contoso-identity/contoso-identity-fig2.png)
 
AD FS-servers in de DMZ vergemakkelijken verificatie van klantreferenties door hun identiteitsproviders voor toegang tot de openbare website en partnerreferenties voor toegang tot het partner extranet.

Contoso heeft besloten deze infrastructuur te behouden en deze te wijden aan klant- en partnerverificatie. De architecten van de identiteits-infrastructuur onderzoeken de conversie van deze infrastructuur naar Azure AD [B2B](/azure/active-directory/b2b/hybrid-organizations) en [B2C](/azure/active-directory-b2c/solution-articles)-oplossingen.

## <a name="hybrid-identity-with-password-hash-synchronization-for-cloud-based-authentication"></a>Hybride identiteit met wachtwoord-hash-synchronisatie voor cloud-based verificatie

Contoso wilde de on-premises AD DS-forest gebruiken voor verificatie naar Microsoft 365-cloudbronnen. Er is besloten om wachtwoordhashsynchronisatie (PHS) te gebruiken.

PHS synchroniseert het on-premises AD DS-forest met de Azure AD-tenant van hun Microsoft 365 voor enterprise-abonnement, het kopiëren van gebruikers- en groepsaccounts en een gehashte versie van wachtwoorden voor gebruikersaccounts.

Als u adreslijstsynchronisatie wilt uitvoeren, heeft Contoso het hulpprogramma Azure AD Connect geïmplementeerd op een server in het parijse datacenter.

Hier is de server met Azure AD Connect die het Contoso AD DS-forest peilt naar wijzigingen en deze wijzigingen vervolgens synchroniseert met de Azure AD-tenant.

![De contoso PHS-adreslijstsynchronisatie-infrastructuur](../media/contoso-identity/contoso-identity-fig4.png)
 
## <a name="conditional-access-policies-for-identity-and-device-access"></a>Voorwaardelijk toegangsbeleid voor identiteits- en apparaattoegang

Contoso heeft een set van Azure AD-en Intune [Voorwaardelijk toegangsbeleidsregels gemaakt](../security/office-365-security/identity-access-policies.md) voor drie beveiligingsniveaus:

- *Basislijnbeveiligingen* zijn van toepassing op alle gebruikersaccounts.
- *Gevoelige* beveiligingen zijn van toepassing op leidinggevenden en leidinggevenden.
- *Sterk gereguleerde* beveiligingen zijn van toepassing op specifieke gebruikers in de financiële, juridische en onderzoeksafdelingen die toegang hebben tot sterk gereguleerde gegevens.

Hier is de resulterende set beleidsregels voor Contoso-identiteit en apparaat Voorwaardelijke toegang.

![Contoso‘s Voorwaardelijke toegangsbeleidsregels voor identiteits- en apparaattoegang](../media/contoso-identity/contoso-identity-fig5.png)
 
## <a name="next-step"></a>Volgende stap

Lees hoe Contoso de Microsoft Endpoint Configuration Manager-infrastructuur gebruikt om de huidige [Windows 10 Enterprise](contoso-win10.md) binnen de organisatie te implementeren en te behouden.

## <a name="see-also"></a>Zie ook

[Identiteits-roadmap voor Microsoft 365 herkennen](identity-roadmap-microsoft-365.md)

[Overzicht van Microsoft 365 voor ondernemingen](microsoft-365-overview.md)

[Testlabrichtlijnen](m365-enterprise-test-lab-guides.md)