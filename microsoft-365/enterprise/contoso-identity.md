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
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Hoe Contoso gebruikmaakt van Identiteit als een service (IDaaS) en cloud-based verificatie voor haar werknemers en federatieve verificatie voor haar partners en klanten verstrekt.
ms.openlocfilehash: 10db0a35024595c4dba9a33ad83ae75bcad3870c
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/21/2020
ms.locfileid: "48637245"
---
# <a name="identity-for-the-contoso-corporation"></a><span data-ttu-id="40acd-103">Identiteit voor Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="40acd-103">Identity for the Contoso Corporation</span></span>

<span data-ttu-id="40acd-104">Microsoft biedt Identity als een service (IDaaS) in de Cloud aanbiedingen via Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="40acd-104">Microsoft provides Identity as a Service (IDaaS) across its cloud offerings through Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="40acd-105">Voor de aanneming van Microsoft 365 for Enterprise kon de contoso IDaaS-oplossing gebruikmaken van hun on-premises identiteitsprovider en federatieve verificatie opnemen met hun bestaande, van derden betrouwbare identiteitsproviders.</span><span class="sxs-lookup"><span data-stu-id="40acd-105">To adopt Microsoft 365 for enterprise, the Contoso IDaaS solution had to use their on-premises identity provider and include federated authentication with their existing trusted, third-party identity providers.</span></span>

## <a name="the-contoso-active-directory-domain-services-forest"></a><span data-ttu-id="40acd-106">Het Active Directory Domain Services-forest van contoso</span><span class="sxs-lookup"><span data-stu-id="40acd-106">The Contoso Active Directory Domain Services forest</span></span>

<span data-ttu-id="40acd-107">Contoso gebruikt een enkelvoudig Active Directory Domain Services (AD DS)-forest voor contoso \. com met zeven subdomeinen, één voor elk gebied van de wereld.</span><span class="sxs-lookup"><span data-stu-id="40acd-107">Contoso uses a single Active Directory Domain Services (AD DS) forest for contoso\.com with seven subdomains, one for each region of the world.</span></span> <span data-ttu-id="40acd-108">De hoofdkantoren, regionale regiokantoren en satellietkantoren bevatten domeincontrollers voor lokale verificatie en autorisatie.</span><span class="sxs-lookup"><span data-stu-id="40acd-108">The headquarters, regional hub offices, and satellite offices contain domain controllers for local authentication and authorization.</span></span>

<span data-ttu-id="40acd-109">Hier is het contoso-forest met regionale domeinen voor de verschillende delen van de wereld die regionale hubs bevatten.</span><span class="sxs-lookup"><span data-stu-id="40acd-109">Here's the Contoso forest with regional domains for the different parts of the world that contain regional hubs.</span></span>

![Het forest en de domeinen van Contoso wereldwijd](../media/contoso-identity/contoso-identity-fig1.png)
 
<span data-ttu-id="40acd-111">Contoso heeft besloten de accounts en groepen in het domein contoso \. com te gebruiken voor verificatie en autorisatie voor de werkbelasting en services van Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="40acd-111">Contoso decided to use the accounts and groups in the contoso\.com forest for authentication and authorization for its Microsoft 365 workloads and services.</span></span>

## <a name="the-contoso-federated-authentication-infrastructure"></a><span data-ttu-id="40acd-112">De federatieve verificatie-infrastructuur van contoso</span><span class="sxs-lookup"><span data-stu-id="40acd-112">The Contoso federated authentication infrastructure</span></span>

<span data-ttu-id="40acd-113">Met Contoso kunnen:</span><span class="sxs-lookup"><span data-stu-id="40acd-113">Contoso allows:</span></span>

- <span data-ttu-id="40acd-114">Klanten die hun Microsoft-, Facebook-of Google-e-mail accounts gebruiken om zich aan te melden bij de openbare website van het bedrijf.</span><span class="sxs-lookup"><span data-stu-id="40acd-114">Customers to use their Microsoft, Facebook, or Google Mail accounts to sign in to the company's public web site.</span></span>
- <span data-ttu-id="40acd-115">Leveranciers en partners voor het gebruik van hun LinkedIn-, Salesforce-of Google-e-mail accounts om u aan te melden bij het partner extranet van het bedrijf.</span><span class="sxs-lookup"><span data-stu-id="40acd-115">Vendors and partners to use their LinkedIn, Salesforce, or Google Mail accounts to sign in to the company's partner extranet.</span></span>

<span data-ttu-id="40acd-116">Hier is de contoso DMZ met een openbare website, een partner extranet en een set AD FS-servers.</span><span class="sxs-lookup"><span data-stu-id="40acd-116">Here's the Contoso DMZ containing a public web site, a partner extranet, and a set of AD FS servers.</span></span> <span data-ttu-id="40acd-117">De DMZ is verbonden met het Internet, met klanten, partners en Internet Services.</span><span class="sxs-lookup"><span data-stu-id="40acd-117">The DMZ is connected to the internet that contains customers, partners, and internet services.</span></span>

![Ondersteuning door contoso voor federatieve verificatie voor klanten en partners](../media/contoso-identity/contoso-identity-fig2.png)
 
<span data-ttu-id="40acd-119">Met AD FS-servers in de DMZ kunt u de verificatie van klant referenties door hun id-providers vergemakkelijken voor toegang tot de openbare website en partner referenties voor de toegang tot de partner extranet.</span><span class="sxs-lookup"><span data-stu-id="40acd-119">AD FS servers in the DMZ facilitate authentication of customer credentials by their identity providers for access to the public web site and partner credentials for access to the partner extranet.</span></span>

<span data-ttu-id="40acd-120">Contoso heeft besloten deze infrastructuur te beschermen en de verificatie van klanten en partners te reserveren.</span><span class="sxs-lookup"><span data-stu-id="40acd-120">Contoso decided to keep this infrastructure and dedicate it to customer and partner authentication.</span></span> <span data-ttu-id="40acd-121">De architecten van de identiteits-infrastructuur onderzoeken de conversie van deze infrastructuur naar Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) en [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles)-oplossingen.</span><span class="sxs-lookup"><span data-stu-id="40acd-121">Contoso identity architects are investigating the conversion of this infrastructure to Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) and [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles) solutions.</span></span>

## <a name="hybrid-identity-with-password-hash-synchronization-for-cloud-based-authentication"></a><span data-ttu-id="40acd-122">Hybride identiteit met wachtwoord-hash-synchronisatie voor cloud-based verificatie</span><span class="sxs-lookup"><span data-stu-id="40acd-122">Hybrid identity with password hash synchronization for cloud-based authentication</span></span>

<span data-ttu-id="40acd-123">Contoso wilde het on-premises Active Directory-forest gebruiken voor verificatie voor Microsoft 365-Cloud bronnen.</span><span class="sxs-lookup"><span data-stu-id="40acd-123">Contoso wanted to use its on-premises AD DS forest for authentication to Microsoft 365 cloud resources.</span></span> <span data-ttu-id="40acd-124">Besloten hash-synchronisatie (PHS) te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="40acd-124">It decided to use password hash synchronization (PHS).</span></span>

<span data-ttu-id="40acd-125">PHS synchroniseert het on-premises AD DS-forest met de Azure AD-Tenant van hun Microsoft 365 for Enterprise-abonnement, het kopiëren van gebruikers-en groepsaccounts en een gehasheerde versie van wachtwoorden van gebruikersaccounts.</span><span class="sxs-lookup"><span data-stu-id="40acd-125">PHS synchronizes the on-premises AD DS forest with the Azure AD tenant of their Microsoft 365 for enterprise subscription, copying user and group accounts and a hashed version of user account passwords.</span></span>

<span data-ttu-id="40acd-126">Om adreslijstsynchronisatie uit te voeren, heeft Contoso het hulpprogramma voor Azure AD Connect op een server in zijn Parijs geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="40acd-126">To do directory synchronization, Contoso deployed the Azure AD Connect tool on a server in its Paris datacenter.</span></span>

<span data-ttu-id="40acd-127">Hier is de server met Azure AD Connect polling voor wijzigingen en vervolgens worden deze wijzigingen met de Azure AD-Tenant gesynchroniseerd.</span><span class="sxs-lookup"><span data-stu-id="40acd-127">Here's the server running Azure AD Connect polling the Contoso AD DS forest for changes and then synchronizing those changes with the Azure AD tenant.</span></span>

![De adreslijstsynchronisatie-infrastructuur contoso PHS](../media/contoso-identity/contoso-identity-fig4.png)
 
## <a name="conditional-access-policies-for-identity-and-device-access"></a><span data-ttu-id="40acd-129">Voorwaardelijk toegangsbeleid voor identiteits- en apparaattoegang</span><span class="sxs-lookup"><span data-stu-id="40acd-129">Conditional Access policies for identity and device access</span></span>

<span data-ttu-id="40acd-130">Contoso heeft een set van Azure AD-en Intune [Voorwaardelijk toegangsbeleidsregels gemaakt](identity-access-policies.md) voor drie beveiligingsniveaus:</span><span class="sxs-lookup"><span data-stu-id="40acd-130">Contoso created a set of Azure AD and Intune [Conditional Access policies](identity-access-policies.md) for three protection levels:</span></span>

- <span data-ttu-id="40acd-131">*Basislijnen* voor beveiliging gelden voor alle gebruikersaccounts.</span><span class="sxs-lookup"><span data-stu-id="40acd-131">*Baseline* protections apply to all user accounts.</span></span>
- <span data-ttu-id="40acd-132">*Gevoelige* beveiligingsmaatregelen gelden voor Senior leiders en leidinggevenden.</span><span class="sxs-lookup"><span data-stu-id="40acd-132">*Sensitive* protections apply to senior leadership and executive staff.</span></span>
- <span data-ttu-id="40acd-133">*Uiterst gereguleerde* bescherming geldt voor specifieke gebruikers in de afdelingen Financiën, juridisch en onderzoek die toegang hebben tot zeer gereglementeerde gegevens.</span><span class="sxs-lookup"><span data-stu-id="40acd-133">*Highly Regulated* protections apply to specific users in the finance, legal, and research departments who have access to highly regulated data.</span></span>

<span data-ttu-id="40acd-134">Dit is de daaruit voortvloeiende set met regels voor voorwaardelijke toegang van Contoso-identiteit en apparaten.</span><span class="sxs-lookup"><span data-stu-id="40acd-134">Here's the resulting set of Contoso identity and device Conditional Access policies.</span></span>

![Contoso‘s Voorwaardelijke toegangsbeleidsregels voor identiteits- en apparaattoegang](../media/contoso-identity/contoso-identity-fig5.png)
 
## <a name="next-step"></a><span data-ttu-id="40acd-136">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="40acd-136">Next step</span></span>

<span data-ttu-id="40acd-137">[Meer informatie](contoso-win10.md) over hoe Contoso de infrastructuur van Microsoft endpoint Configuration Manager gebruikt om de huidige organisatie van Windows 10 Enterprise binnen de organisatie te implementeren en te behouden.</span><span class="sxs-lookup"><span data-stu-id="40acd-137">[Learn](contoso-win10.md) how Contoso uses its Microsoft Endpoint Configuration Manager infrastructure to deploy and keep current Windows 10 Enterprise across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="40acd-138">Zie ook</span><span class="sxs-lookup"><span data-stu-id="40acd-138">See also</span></span>

[<span data-ttu-id="40acd-139">Identiteits-roadmap voor Microsoft 365 herkennen</span><span class="sxs-lookup"><span data-stu-id="40acd-139">Identity roadmap for Microsoft 365</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="40acd-140">Overzicht van Microsoft 365 voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="40acd-140">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="40acd-141">Testlabrichtlijnen</span><span class="sxs-lookup"><span data-stu-id="40acd-141">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
