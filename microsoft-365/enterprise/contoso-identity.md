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
ms.openlocfilehash: f3c8746345683652ce601400ae7297e96fff2ee3
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051518"
---
# <a name="identity-for-the-contoso-corporation"></a><span data-ttu-id="48d8e-103">Identiteit voor Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="48d8e-103">Identity for the Contoso Corporation</span></span>

<span data-ttu-id="48d8e-104">Microsoft biedt Identity as a Service (IDaaS) via de cloudaanbiedingen via Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="48d8e-104">Microsoft provides Identity as a Service (IDaaS) across its cloud offerings through Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="48d8e-105">Als u Microsoft 365 voor ondernemingen wilt gebruiken, moest de Contoso IDaaS-oplossing hun on-premises identiteitsprovider gebruiken en federatief verificatie opnemen met hun bestaande vertrouwde, externe identiteitsproviders.</span><span class="sxs-lookup"><span data-stu-id="48d8e-105">To adopt Microsoft 365 for enterprise, the Contoso IDaaS solution had to use their on-premises identity provider and include federated authentication with their existing trusted, third-party identity providers.</span></span>

## <a name="the-contoso-active-directory-domain-services-forest"></a><span data-ttu-id="48d8e-106">Het Contoso Active Directory Domain Services-forest</span><span class="sxs-lookup"><span data-stu-id="48d8e-106">The Contoso Active Directory Domain Services forest</span></span>

<span data-ttu-id="48d8e-107">Contoso gebruikt één AD DS-forest (Active Directory Domain Services) voor contoso com met zeven subdomeinen, één voor elke regio \. ter wereld.</span><span class="sxs-lookup"><span data-stu-id="48d8e-107">Contoso uses a single Active Directory Domain Services (AD DS) forest for contoso\.com with seven subdomains, one for each region of the world.</span></span> <span data-ttu-id="48d8e-108">De hoofdkantoren, regionale regiokantoren en satellietkantoren bevatten domeincontrollers voor lokale verificatie en autorisatie.</span><span class="sxs-lookup"><span data-stu-id="48d8e-108">The headquarters, regional hub offices, and satellite offices contain domain controllers for local authentication and authorization.</span></span>

<span data-ttu-id="48d8e-109">Hier is het Contoso-bos met regionale domeinen voor de verschillende delen van de wereld die regionale hubs bevatten.</span><span class="sxs-lookup"><span data-stu-id="48d8e-109">Here's the Contoso forest with regional domains for the different parts of the world that contain regional hubs.</span></span>

![Het forest en de domeinen van Contoso wereldwijd](../media/contoso-identity/contoso-identity-fig1.png)
 
<span data-ttu-id="48d8e-111">Contoso heeft besloten de accounts en groepen in het contoso-combos te gebruiken voor verificatie en autorisatie voor de Microsoft 365 \. werkbelasting en services.</span><span class="sxs-lookup"><span data-stu-id="48d8e-111">Contoso decided to use the accounts and groups in the contoso\.com forest for authentication and authorization for its Microsoft 365 workloads and services.</span></span>

## <a name="the-contoso-federated-authentication-infrastructure"></a><span data-ttu-id="48d8e-112">De contoso-federatief verificatie-infrastructuur</span><span class="sxs-lookup"><span data-stu-id="48d8e-112">The Contoso federated authentication infrastructure</span></span>

<span data-ttu-id="48d8e-113">Met Contoso kunnen:</span><span class="sxs-lookup"><span data-stu-id="48d8e-113">Contoso allows:</span></span>

- <span data-ttu-id="48d8e-114">Klanten kunnen hun Microsoft-, Facebook- of Google Mail-accounts gebruiken om zich aan te melden bij de openbare website van het bedrijf.</span><span class="sxs-lookup"><span data-stu-id="48d8e-114">Customers to use their Microsoft, Facebook, or Google Mail accounts to sign in to the company's public web site.</span></span>
- <span data-ttu-id="48d8e-115">Leveranciers en partners kunnen hun LinkedIn-, Salesforce- of Google Mail-accounts gebruiken om zich aan te melden bij het partner-extranet van het bedrijf.</span><span class="sxs-lookup"><span data-stu-id="48d8e-115">Vendors and partners to use their LinkedIn, Salesforce, or Google Mail accounts to sign in to the company's partner extranet.</span></span>

<span data-ttu-id="48d8e-116">Hier is de Contoso DMZ met een openbare website, een partner extranet en een set AD FS-servers (Active Directory Federation Services).</span><span class="sxs-lookup"><span data-stu-id="48d8e-116">Here's the Contoso DMZ containing a public web site, a partner extranet, and a set of Active Directory Federation Services (AD FS) servers.</span></span> <span data-ttu-id="48d8e-117">De DMZ is verbonden met internet dat klanten, partners en internetservices bevat.</span><span class="sxs-lookup"><span data-stu-id="48d8e-117">The DMZ is connected to the internet that contains customers, partners, and internet services.</span></span>

![Contoso-ondersteuning voor federatief verificatie voor klanten en partners](../media/contoso-identity/contoso-identity-fig2.png)
 
<span data-ttu-id="48d8e-119">AD FS-servers in de DMZ vergemakkelijken verificatie van klantreferenties door hun identiteitsproviders voor toegang tot de openbare website en partnerreferenties voor toegang tot het partner extranet.</span><span class="sxs-lookup"><span data-stu-id="48d8e-119">AD FS servers in the DMZ facilitate authentication of customer credentials by their identity providers for access to the public web site and partner credentials for access to the partner extranet.</span></span>

<span data-ttu-id="48d8e-120">Contoso heeft besloten deze infrastructuur te behouden en deze te wijden aan klant- en partnerverificatie.</span><span class="sxs-lookup"><span data-stu-id="48d8e-120">Contoso decided to keep this infrastructure and dedicate it to customer and partner authentication.</span></span> <span data-ttu-id="48d8e-121">De architecten van de identiteits-infrastructuur onderzoeken de conversie van deze infrastructuur naar Azure AD [B2B](/azure/active-directory/b2b/hybrid-organizations) en [B2C](/azure/active-directory-b2c/solution-articles)-oplossingen.</span><span class="sxs-lookup"><span data-stu-id="48d8e-121">Contoso identity architects are investigating the conversion of this infrastructure to Azure AD [B2B](/azure/active-directory/b2b/hybrid-organizations) and [B2C](/azure/active-directory-b2c/solution-articles) solutions.</span></span>

## <a name="hybrid-identity-with-password-hash-synchronization-for-cloud-based-authentication"></a><span data-ttu-id="48d8e-122">Hybride identiteit met wachtwoord-hash-synchronisatie voor cloud-based verificatie</span><span class="sxs-lookup"><span data-stu-id="48d8e-122">Hybrid identity with password hash synchronization for cloud-based authentication</span></span>

<span data-ttu-id="48d8e-123">Contoso wilde de on-premises AD DS-forest gebruiken voor verificatie om Microsoft 365 cloudbronnen.</span><span class="sxs-lookup"><span data-stu-id="48d8e-123">Contoso wanted to use its on-premises AD DS forest for authentication to Microsoft 365 cloud resources.</span></span> <span data-ttu-id="48d8e-124">Er is besloten om wachtwoordhashsynchronisatie (PHS) te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="48d8e-124">It decided to use password hash synchronization (PHS).</span></span>

<span data-ttu-id="48d8e-125">PHS synchroniseert het on-premises AD DS-forest met de Azure AD-tenant van hun Microsoft 365 voor ondernemingsabonnement, het kopiëren van gebruikers- en groepsaccounts en een gehashte versie van wachtwoorden voor gebruikersaccounts.</span><span class="sxs-lookup"><span data-stu-id="48d8e-125">PHS synchronizes the on-premises AD DS forest with the Azure AD tenant of their Microsoft 365 for enterprise subscription, copying user and group accounts and a hashed version of user account passwords.</span></span>

<span data-ttu-id="48d8e-126">Als u adreslijstsynchronisatie wilt uitvoeren, heeft Contoso het hulpprogramma Azure AD Verbinding maken geïmplementeerd op een server in het parijse datacenter.</span><span class="sxs-lookup"><span data-stu-id="48d8e-126">To do directory synchronization, Contoso deployed the Azure AD Connect tool on a server in its Paris datacenter.</span></span>

<span data-ttu-id="48d8e-127">Hier is de server met Azure AD Verbinding maken het Contoso AD DS-forest peilen naar wijzigingen en deze wijzigingen vervolgens synchroniseren met de Azure AD-tenant.</span><span class="sxs-lookup"><span data-stu-id="48d8e-127">Here's the server running Azure AD Connect polling the Contoso AD DS forest for changes and then synchronizing those changes with the Azure AD tenant.</span></span>

![De contoso PHS-adreslijstsynchronisatie-infrastructuur](../media/contoso-identity/contoso-identity-fig4.png)
 
## <a name="conditional-access-policies-for-identity-and-device-access"></a><span data-ttu-id="48d8e-129">Voorwaardelijk toegangsbeleid voor identiteits- en apparaattoegang</span><span class="sxs-lookup"><span data-stu-id="48d8e-129">Conditional Access policies for identity and device access</span></span>

<span data-ttu-id="48d8e-130">Contoso heeft een set van Azure AD-en Intune [Voorwaardelijk toegangsbeleidsregels gemaakt](../security/defender-365-security/identity-access-policies.md) voor drie beveiligingsniveaus:</span><span class="sxs-lookup"><span data-stu-id="48d8e-130">Contoso created a set of Azure AD and Intune [Conditional Access policies](../security/defender-365-security/identity-access-policies.md) for three protection levels:</span></span>

- <span data-ttu-id="48d8e-131">*Basislijnbeveiligingen* zijn van toepassing op alle gebruikersaccounts.</span><span class="sxs-lookup"><span data-stu-id="48d8e-131">*Baseline* protections apply to all user accounts.</span></span>
- <span data-ttu-id="48d8e-132">*Gevoelige* beveiligingen zijn van toepassing op leidinggevenden en leidinggevenden.</span><span class="sxs-lookup"><span data-stu-id="48d8e-132">*Sensitive* protections apply to senior leadership and executive staff.</span></span>
- <span data-ttu-id="48d8e-133">*Sterk gereguleerde* beveiligingen zijn van toepassing op specifieke gebruikers in de financiële, juridische en onderzoeksafdelingen die toegang hebben tot sterk gereguleerde gegevens.</span><span class="sxs-lookup"><span data-stu-id="48d8e-133">*Highly Regulated* protections apply to specific users in the finance, legal, and research departments who have access to highly regulated data.</span></span>

<span data-ttu-id="48d8e-134">Hier is de resulterende set beleidsregels voor Contoso-identiteit en apparaat Voorwaardelijke toegang.</span><span class="sxs-lookup"><span data-stu-id="48d8e-134">Here's the resulting set of Contoso identity and device Conditional Access policies.</span></span>

![Contoso‘s Voorwaardelijke toegangsbeleidsregels voor identiteits- en apparaattoegang](../media/contoso-identity/contoso-identity-fig5.png)
 
## <a name="next-step"></a><span data-ttu-id="48d8e-136">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="48d8e-136">Next step</span></span>

<span data-ttu-id="48d8e-137">Lees hoe Contoso de Microsoft Endpoint Configuration Manager gebruikt [](contoso-win10.md) om de huidige Windows 10 Enterprise binnen de organisatie te implementeren en te behouden.</span><span class="sxs-lookup"><span data-stu-id="48d8e-137">Learn how Contoso uses its Microsoft Endpoint Configuration Manager infrastructure to [deploy and keep current Windows 10 Enterprise](contoso-win10.md) across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="48d8e-138">Zie ook</span><span class="sxs-lookup"><span data-stu-id="48d8e-138">See also</span></span>

[<span data-ttu-id="48d8e-139">Identiteits-roadmap voor Microsoft 365 herkennen</span><span class="sxs-lookup"><span data-stu-id="48d8e-139">Identity roadmap for Microsoft 365</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="48d8e-140">Overzicht van Microsoft 365 voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="48d8e-140">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="48d8e-141">Testlabrichtlijnen</span><span class="sxs-lookup"><span data-stu-id="48d8e-141">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)