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
# <a name="identity-for-the-contoso-corporation"></a><span data-ttu-id="1b0c2-103">Identiteit voor Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="1b0c2-103">Identity for the Contoso Corporation</span></span>

<span data-ttu-id="1b0c2-104">Microsoft biedt een Identiteit als een service (IDaaS)aan voor zijn cloud-diensten met Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="1b0c2-104">Microsoft provides an Identity as a Service (IDaaS) across its cloud offerings with Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="1b0c2-105">Om Microsoft 365 Enterprise toe te passen, moest de IDaaS-oplossing van Contoso gebruikmaken van de lokale identiteitsprovider, maar wel met federatieve verificatie met hun bestaande vertrouwde derde identiteitsproviders.</span><span class="sxs-lookup"><span data-stu-id="1b0c2-105">To adopt Microsoft 365 Enterprise, Contoso's IDaaS solution had to leverage their on-premises identity provider and still include federated authentication with their existing trusted, third-party identity providers.</span></span>

## <a name="contosos-active-directory-domain-services-forest"></a><span data-ttu-id="1b0c2-106">Contoso‘s Active Directory Domain Services-forest</span><span class="sxs-lookup"><span data-stu-id="1b0c2-106">Contoso's Active Directory Domain Services forest</span></span>

<span data-ttu-id="1b0c2-107">Contoso gebruikt één Active Directory Domain Services-forest (AD DS) voor contoso.com met zeven subdomeinen, één voor elke regio van de wereld.</span><span class="sxs-lookup"><span data-stu-id="1b0c2-107">Contoso uses a single Active Directory Domain Services (AD DS) forest for contoso.com with seven sub-domains, one for each region of the world.</span></span> <span data-ttu-id="1b0c2-108">De hoofdkantoren, regionale regiokantoren en satellietkantoren bevatten domeincontrollers voor lokale verificatie en autorisatie.</span><span class="sxs-lookup"><span data-stu-id="1b0c2-108">The headquarters, regional hub offices, and satellite offices contain domain controllers for local authentication and authorization.</span></span>

<span data-ttu-id="1b0c2-109">Dit is het Contoso-forest met regionale domeinen voor de verschillende delen van de wereld met regionale hubs.</span><span class="sxs-lookup"><span data-stu-id="1b0c2-109">Here is the Contoso forest with regional domains for the different parts of the world that contain regional hubs.</span></span>

![Het forest en de domeinen van Contoso wereldwijd](../media/contoso-identity/contoso-identity-fig1.png)
 
<span data-ttu-id="1b0c2-111">Contoso wilde de accounts en groepen in het contoso.com-forest gebruiken voor verificatie en machtiging voor de werkbelastingen en services van zijn Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1b0c2-111">Contoso wanted to use the accounts and groups in the contoso.com forest for authentication and authorization for its Microsoft 365 workloads and services.</span></span>

## <a name="contosos-federated-authentication-infrastructure"></a><span data-ttu-id="1b0c2-112">De federatieve verificatie-infrastructuur van Contoso</span><span class="sxs-lookup"><span data-stu-id="1b0c2-112">Contoso's federated authentication infrastructure</span></span>

<span data-ttu-id="1b0c2-113">Met Contoso kunnen:</span><span class="sxs-lookup"><span data-stu-id="1b0c2-113">Contoso allows:</span></span>

- <span data-ttu-id="1b0c2-114">gebruikers hun Microsoft, Facebook of Google Mail-accounts gebruiken om in te loggen op hun publieke website.</span><span class="sxs-lookup"><span data-stu-id="1b0c2-114">Customers to use their Microsoft, Facebook, or Google Mail accounts to sign in to their public web site.</span></span>
- <span data-ttu-id="1b0c2-115">leveranciers en partners hun LinkedIn, Salesforce of Google mail-accounts gebruiken om zich aan te melden bij het extranet van de partner.</span><span class="sxs-lookup"><span data-stu-id="1b0c2-115">Vendors and partners to use their LinkedIn, Salesforce, or Google Mail accounts to sign in to the partner extranet.</span></span>

<span data-ttu-id="1b0c2-116">Dit is de Contoso-DMZ met een openbare website, een partner extranet en een set Active Directory Federation Services-servers (AD FS).</span><span class="sxs-lookup"><span data-stu-id="1b0c2-116">Here is the Contoso DMZ containing a public web site, a partner extranet, and a set of Active Directory Federation Services (AD FS) servers.</span></span> <span data-ttu-id="1b0c2-117">De DMZ is verbonden met het internet waar de klanten, partners en Internet Services zijn te vinden.</span><span class="sxs-lookup"><span data-stu-id="1b0c2-117">The DMZ is connected to the Internet that contains customers, partners, and Internet services.</span></span>

![Ondersteuning van Contoso voor federatieve verificatie voor klanten en partners](../media/contoso-identity/contoso-identity-fig2.png)
 
<span data-ttu-id="1b0c2-119">Met AD FS-servers in het DMZ wordt de verificatie van de inloggegevens van de klant door hun identiteisproviders vergemakkelijkt voor toegang tot de openbare website en inloggegevens van partners voor toegang tot het partner-extranet.</span><span class="sxs-lookup"><span data-stu-id="1b0c2-119">AD FS servers in the DMZ facilitate the authentication of customer credentials by their identity providers for access to the public web site and partner credentials for access to the partner extranet.</span></span>

<span data-ttu-id="1b0c2-120">Contoso besloot de infrastructuur te behouden en deze in te zetten voor klant- en partner-authenticaties.</span><span class="sxs-lookup"><span data-stu-id="1b0c2-120">Contoso decided to keep this infrastructure and dedicate it to customer and partner authentications.</span></span> <span data-ttu-id="1b0c2-121">De architecten van de identiteits-infrastructuur onderzoeken de conversie van deze infrastructuur naar Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) en [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles)-oplossingen.</span><span class="sxs-lookup"><span data-stu-id="1b0c2-121">Contoso identity architects are investigating the conversion of this infrastructure to Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) and [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles) solutions.</span></span>

## <a name="hybrid-identity-with-password-hash-synchronization-for-cloud-based-authentication"></a><span data-ttu-id="1b0c2-122">Hybride identiteit met wachtwoord-hash-synchronisatie voor cloud-based verificatie</span><span class="sxs-lookup"><span data-stu-id="1b0c2-122">Hybrid identity with password hash synchronization for cloud-based authentication</span></span>

<span data-ttu-id="1b0c2-123">Contoso wilde een lokale AD DS-forest gebruiken voor verificatie bij cloudresources van Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1b0c2-123">Contoso wanted to leverage its on-premises AD DS forest for authentication to Microsoft 365 cloud resources.</span></span> <span data-ttu-id="1b0c2-124">Ze besloten wachtwoord-hash-synchronisatie (PHS) toe te passen.</span><span class="sxs-lookup"><span data-stu-id="1b0c2-124">It decided on password hash synchronization (PHS).</span></span>

<span data-ttu-id="1b0c2-125">PHS synchroniseert het lokale AD DS-forest met de Azure AD-tenant van hun Microsoft 365 Enterprise-abonnement, en kopieert gebruikers-en groepsaccounts en een gehashte versie van gebruikersaccountswachtwoorden.</span><span class="sxs-lookup"><span data-stu-id="1b0c2-125">PHS synchronizes the on-premises AD DS forest with the Azure AD tenant of their Microsoft 365 Enterprise subscription, copying user and group accounts and a hashed version of user account passwords.</span></span> 

<span data-ttu-id="1b0c2-126">Om de doorlopende adreslijstsynchronisatie uit te voeren, heeft Contoso het Azure AD Connect-hulpprogramma geïmplementeerd op een server op zijn datacenter in Parijs.</span><span class="sxs-lookup"><span data-stu-id="1b0c2-126">To perform the ongoing directory synchronization, Contoso has deployed the Azure AD Connect tool on a server in its Paris datacenter.</span></span> 

<span data-ttu-id="1b0c2-127">Dit is de server met Azure AD Connect die het AD DS-forest van Contoso verzoekt om wijzigingen aan te brengen. Vervolgens worden deze wijzigingen gesynchroniseerd met de Azure AD-tenant.</span><span class="sxs-lookup"><span data-stu-id="1b0c2-127">Here is the server running Azure AD Connect polling the Contoso AD DS forest for changes and then synchronizing those changes with the Azure AD tenant.</span></span>

![PHS adreslijstsynchronisatie-infrastructuur van Contoso](../media/contoso-identity/contoso-identity-fig4.png)
 
## <a name="conditional-access-policies-for-identity-and-device-access"></a><span data-ttu-id="1b0c2-129">Voorwaardelijk toegangsbeleid voor identiteits- en apparaattoegang</span><span class="sxs-lookup"><span data-stu-id="1b0c2-129">Conditional Access policies for identity and device access</span></span>

<span data-ttu-id="1b0c2-130">Contoso heeft een set van Azure AD-en Intune [Voorwaardelijk toegangsbeleidsregels gemaakt](identity-access-policies.md) voor drie beveiligingsniveaus:</span><span class="sxs-lookup"><span data-stu-id="1b0c2-130">Contoso created a set of Azure AD and Intune [Conditional Access policies](identity-access-policies.md) for three protection levels:</span></span>

- <span data-ttu-id="1b0c2-131">**Basis**beveiligingsmaatregelen gelden voor alle gebruikersaccounts</span><span class="sxs-lookup"><span data-stu-id="1b0c2-131">**Baseline** protections apply to all user accounts</span></span>
- <span data-ttu-id="1b0c2-132">**Gevoelige** beveiligingsmaatregelen zijn van toepassing op leidinggevenden en directie-medewerkers</span><span class="sxs-lookup"><span data-stu-id="1b0c2-132">**Sensitive** protections apply to senior leadership and executive staff</span></span>
- <span data-ttu-id="1b0c2-133">**Zeer gereguleerde** beveiligingsmaatregelen zijn van toepassing op specifieke gebruikers van de Financiële, juridische en onderzoeksafdelingen die toegang hebben tot zeer gereglementeerde gegevens</span><span class="sxs-lookup"><span data-stu-id="1b0c2-133">**Highly Regulated** protections apply to specific users in the finance, legal, and research departments that have access to highly regulated data</span></span>

<span data-ttu-id="1b0c2-134">Hieronder ziet u Contoso‘s resultatenset van Voorwaardelijke toegangsbeleidsregels voor apparaten. </span><span class="sxs-lookup"><span data-stu-id="1b0c2-134">Here is Contoso's resulting set of identity and device Conditional Access policies.</span></span>

![Contoso‘s Voorwaardelijke toegangsbeleidsregels voor identiteits- en apparaattoegang](../media/contoso-identity/contoso-identity-fig5.png)
 
## <a name="next-step"></a><span data-ttu-id="1b0c2-136">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="1b0c2-136">Next step</span></span>

<span data-ttu-id="1b0c2-137">[Lees](contoso-win10.md) hier hoe Contoso zijn infrastructuur voor Microsoft-Endpoint Configuratiebeheer gebruikt voor het implementeren en onderhouden van Windows 10 Enterprise in de hele organisatie.</span><span class="sxs-lookup"><span data-stu-id="1b0c2-137">[Learn](contoso-win10.md) how Contoso is leveraging its Microsoft Endpoint Configuration Manager infrastructure to deploy and keep current Windows 10 Enterprise across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="1b0c2-138">Zie ook</span><span class="sxs-lookup"><span data-stu-id="1b0c2-138">See also</span></span>

[<span data-ttu-id="1b0c2-139">Identiteit voor Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="1b0c2-139">Identity for Microsoft 365 Enterprise</span></span>](identity-infrastructure.md)

[<span data-ttu-id="1b0c2-140">Implementatiehandleiding</span><span class="sxs-lookup"><span data-stu-id="1b0c2-140">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="1b0c2-141">Testlabrichtlijnen</span><span class="sxs-lookup"><span data-stu-id="1b0c2-141">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
