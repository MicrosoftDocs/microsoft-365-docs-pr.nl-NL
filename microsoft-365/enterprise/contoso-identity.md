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
ms.openlocfilehash: dea0f53ef1c3fdc2ea32256303c6120c614c904d
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754634"
---
# <a name="identity-for-the-contoso-corporation"></a>Identiteit voor Contoso Corporation

Microsoft biedt Identity als een service (IDaaS) in de Cloud aanbiedingen via Azure Active Directory (Azure AD). Voor de aanneming van Microsoft 365 for Enterprise kon de contoso IDaaS-oplossing gebruikmaken van hun on-premises identiteitsprovider en federatieve verificatie opnemen met hun bestaande, van derden betrouwbare identiteitsproviders.

## <a name="the-contoso-active-directory-domain-services-forest"></a>Het Active Directory Domain Services-forest van contoso

Contoso gebruikt een enkelvoudig Active Directory Domain Services (AD DS)-forest voor contoso \. com met zeven subdomeinen, één voor elk gebied van de wereld. De hoofdkantoren, regionale regiokantoren en satellietkantoren bevatten domeincontrollers voor lokale verificatie en autorisatie.

Hier is het contoso-forest met regionale domeinen voor de verschillende delen van de wereld die regionale hubs bevatten.

![Het forest en de domeinen van Contoso wereldwijd](../media/contoso-identity/contoso-identity-fig1.png)
 
Contoso heeft besloten de accounts en groepen in het domein contoso \. com te gebruiken voor verificatie en autorisatie voor de werkbelasting en services van Microsoft 365.

## <a name="the-contoso-federated-authentication-infrastructure"></a>De federatieve verificatie-infrastructuur van contoso

Met Contoso kunnen:

- Klanten die hun Microsoft-, Facebook-of Google-e-mail accounts gebruiken om zich aan te melden bij de openbare website van het bedrijf.
- Leveranciers en partners voor het gebruik van hun LinkedIn-, Salesforce-of Google-e-mail accounts om u aan te melden bij het partner extranet van het bedrijf.

Hier is de contoso-DMZ met een openbare website, een partner extranet en een set Active Directory Federation Services (AD FS)-servers. De DMZ is verbonden met het Internet, met klanten, partners en Internet Services.

![Ondersteuning door contoso voor federatieve verificatie voor klanten en partners](../media/contoso-identity/contoso-identity-fig2.png)
 
Met AD FS-servers in de DMZ kunt u de verificatie van klant referenties door hun id-providers vergemakkelijken voor toegang tot de openbare website en partner referenties voor de toegang tot de partner extranet.

Contoso heeft besloten deze infrastructuur te beschermen en de verificatie van klanten en partners te reserveren. De architecten van de identiteits-infrastructuur onderzoeken de conversie van deze infrastructuur naar Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) en [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles)-oplossingen.

## <a name="hybrid-identity-with-password-hash-synchronization-for-cloud-based-authentication"></a>Hybride identiteit met wachtwoord-hash-synchronisatie voor cloud-based verificatie

Contoso wilde het on-premises Active Directory-forest gebruiken voor verificatie voor Microsoft 365-Cloud bronnen. Besloten hash-synchronisatie (PHS) te gebruiken.

PHS synchroniseert het on-premises AD DS-forest met de Azure AD-Tenant van hun Microsoft 365 for Enterprise-abonnement, het kopiëren van gebruikers-en groepsaccounts en een gehasheerde versie van wachtwoorden van gebruikersaccounts.

Om adreslijstsynchronisatie uit te voeren, heeft Contoso het hulpprogramma voor Azure AD Connect op een server in zijn Parijs geïmplementeerd.

Hier is de server met Azure AD Connect polling voor wijzigingen en vervolgens worden deze wijzigingen met de Azure AD-Tenant gesynchroniseerd.

![De adreslijstsynchronisatie-infrastructuur contoso PHS](../media/contoso-identity/contoso-identity-fig4.png)
 
## <a name="conditional-access-policies-for-identity-and-device-access"></a>Voorwaardelijk toegangsbeleid voor identiteits- en apparaattoegang

Contoso heeft een set van Azure AD-en Intune [Voorwaardelijk toegangsbeleidsregels gemaakt](identity-access-policies.md) voor drie beveiligingsniveaus:

- *Basislijnen* voor beveiliging gelden voor alle gebruikersaccounts.
- *Gevoelige* beveiligingsmaatregelen gelden voor Senior leiders en leidinggevenden.
- *Uiterst gereguleerde* bescherming geldt voor specifieke gebruikers in de afdelingen Financiën, juridisch en onderzoek die toegang hebben tot zeer gereglementeerde gegevens.

Dit is de daaruit voortvloeiende set met regels voor voorwaardelijke toegang van Contoso-identiteit en apparaten.

![Contoso‘s Voorwaardelijke toegangsbeleidsregels voor identiteits- en apparaattoegang](../media/contoso-identity/contoso-identity-fig5.png)
 
## <a name="next-step"></a>Volgende stap

Meer informatie over hoe Contoso de infrastructuur van Microsoft endpoint Configuration Manager gebruikt om de huidige organisatie van [Windows 10 Enterprise](contoso-win10.md) binnen de organisatie te implementeren en te behouden.

## <a name="see-also"></a>Zie ook

[Identiteits-roadmap voor Microsoft 365 herkennen](identity-roadmap-microsoft-365.md)

[Overzicht van Microsoft 365 voor ondernemingen](microsoft-365-overview.md)

[Testlabrichtlijnen](m365-enterprise-test-lab-guides.md)
