---
title: Microsoft 365-identiteitsmodellen en Azure Active Directory
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.date: 09/30/2020
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- M365-identity-device-management
- M365-security-compliance
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 06a189e7-5ec6-4af2-94bf-a22ea225a7a9
description: Meer informatie over het beheren van de Azure AD-gebruikersidentiteitsservice in Microsoft 365 met behulp van alleen-cloud- of hybride identiteitsmodellen.
ms.openlocfilehash: b54ccce6ea2a468e02d9db95e7932d847df4e64b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905702"
---
# <a name="microsoft-365-identity-models-and-azure-active-directory"></a><span data-ttu-id="b7918-103">Microsoft 365-identiteitsmodellen en Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="b7918-103">Microsoft 365 identity models and Azure Active Directory</span></span>

<span data-ttu-id="b7918-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="b7918-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="b7918-105">Microsoft 365 gebruikt Azure Active Directory (Azure AD), een cloudgebaseerde gebruikersidentiteits- en verificatieservice die is opgenomen in uw Microsoft 365-abonnement, om identiteiten en verificatie voor Microsoft 365 te beheren.</span><span class="sxs-lookup"><span data-stu-id="b7918-105">Microsoft 365 uses Azure Active Directory (Azure AD), a cloud-based user identity and authentication service that is included with your Microsoft 365 subscription, to manage identities and authentication for Microsoft 365.</span></span> <span data-ttu-id="b7918-106">Het correct configureren van uw identiteitsinfrastructuur is essentieel voor het beheren van microsoft 365-gebruikerstoegang en -machtigingen voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="b7918-106">Getting your identity infrastructure configured correctly is vital to managing Microsoft 365 user access and permissions for your organization.</span></span>

<span data-ttu-id="b7918-107">Voordat u begint, bekijkt u deze video voor een overzicht van identiteitsmodellen en verificatie voor Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b7918-107">Before you begin, watch this video for an overview of identity models and authentication for Microsoft 365.</span></span>

<span data-ttu-id="b7918-108"><p> </p></span><span class="sxs-lookup"><span data-stu-id="b7918-108"><p> </p></span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

<span data-ttu-id="b7918-109">Uw eerste planningskeuze is het Microsoft 365-identiteitsmodel.</span><span class="sxs-lookup"><span data-stu-id="b7918-109">Your first planning choice is the Microsoft 365 identity model.</span></span>

## <a name="microsoft-365-identity-models"></a><span data-ttu-id="b7918-110">Microsoft 365-identiteitsmodellen</span><span class="sxs-lookup"><span data-stu-id="b7918-110">Microsoft 365 identity models</span></span>

<span data-ttu-id="b7918-111">Als u gebruikersaccounts wilt plannen, moet u eerst de twee identiteitsmodellen in Microsoft 365 begrijpen.</span><span class="sxs-lookup"><span data-stu-id="b7918-111">To plan for user accounts, you first need to understand the two identity models in Microsoft 365.</span></span> <span data-ttu-id="b7918-112">U kunt de identiteiten van uw organisatie alleen in de cloud behouden of u kunt uw on-premises AD DS-identiteiten (Active Directory Domain Services) behouden en deze gebruiken voor verificatie wanneer gebruikers toegang hebben tot Microsoft 365-cloudservices.</span><span class="sxs-lookup"><span data-stu-id="b7918-112">You can maintain your organization's identities only in the cloud, or you can maintain your on-premises Active Directory Domain Services (AD DS) identities and use them for authentication when users access Microsoft 365 cloud services.</span></span>  

<span data-ttu-id="b7918-113">Hier zijn de twee typen identiteit en de beste pasvorm en voordelen.</span><span class="sxs-lookup"><span data-stu-id="b7918-113">Here are the two types of identity and their best fit and benefits.</span></span>

| <span data-ttu-id="b7918-114">Attribuut</span><span class="sxs-lookup"><span data-stu-id="b7918-114">Attribute</span></span> | <span data-ttu-id="b7918-115">Alleen cloudidentiteit</span><span class="sxs-lookup"><span data-stu-id="b7918-115">Cloud-only identity</span></span> | <span data-ttu-id="b7918-116">Hybride identiteit</span><span class="sxs-lookup"><span data-stu-id="b7918-116">Hybrid identity</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="b7918-117">**Definitie**</span><span class="sxs-lookup"><span data-stu-id="b7918-117">**Definition**</span></span> | <span data-ttu-id="b7918-118">Gebruikersaccount bestaat alleen in de Azure AD-tenant voor uw Microsoft 365-abonnement.</span><span class="sxs-lookup"><span data-stu-id="b7918-118">User account only exists in the Azure AD tenant for your Microsoft 365 subscription.</span></span> | <span data-ttu-id="b7918-119">Gebruikersaccount bestaat in AD DS en een kopie bevindt zich ook in de Azure AD-tenant voor uw Microsoft 365-abonnement.</span><span class="sxs-lookup"><span data-stu-id="b7918-119">User account exists in AD DS and a copy is also in the Azure AD tenant for your Microsoft 365 subscription.</span></span> <span data-ttu-id="b7918-120">Het gebruikersaccount in Azure AD kan ook een gehashte versie van het wachtwoord van het al gehashte AD DS-gebruikersaccount bevatten.</span><span class="sxs-lookup"><span data-stu-id="b7918-120">The user account in Azure AD might also include a hashed version of the already hashed AD DS user account password.</span></span> |
| <span data-ttu-id="b7918-121">**Hoe microsoft 365 gebruikersreferenties verifieert**</span><span class="sxs-lookup"><span data-stu-id="b7918-121">**How Microsoft 365 authenticates user credentials**</span></span> | <span data-ttu-id="b7918-122">De Azure AD-tenant voor uw Microsoft 365-abonnement voert de verificatie uit met het cloudidentiteitsaccount.</span><span class="sxs-lookup"><span data-stu-id="b7918-122">The Azure AD tenant for your Microsoft 365 subscription performs the authentication with the cloud identity account.</span></span> | <span data-ttu-id="b7918-123">De Azure AD-tenant voor uw Microsoft 365-abonnement verwerkt het verificatieproces of leidt de gebruiker om naar een andere identiteitsprovider.</span><span class="sxs-lookup"><span data-stu-id="b7918-123">The Azure AD tenant for your Microsoft 365 subscription either handles the authentication process or redirects the user to another identity provider.</span></span> |
| <span data-ttu-id="b7918-124">**Het beste voor**</span><span class="sxs-lookup"><span data-stu-id="b7918-124">**Best for**</span></span> | <span data-ttu-id="b7918-125">Organisaties die geen on-premises AD DS hebben of nodig hebben.</span><span class="sxs-lookup"><span data-stu-id="b7918-125">Organizations that do not have or need an on-premises AD DS.</span></span> | <span data-ttu-id="b7918-126">Organisaties die AD DS of een andere identiteitsprovider gebruiken.</span><span class="sxs-lookup"><span data-stu-id="b7918-126">Organizations using AD DS or another identity provider.</span></span> |
| <span data-ttu-id="b7918-127">**Grootste voordeel**</span><span class="sxs-lookup"><span data-stu-id="b7918-127">**Greatest benefit**</span></span> | <span data-ttu-id="b7918-128">Eenvoudig te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="b7918-128">Simple to use.</span></span> <span data-ttu-id="b7918-129">Er zijn geen extra adreslijsthulpmiddelen of -servers vereist.</span><span class="sxs-lookup"><span data-stu-id="b7918-129">No extra directory tools or servers required.</span></span> | <span data-ttu-id="b7918-130">Gebruikers kunnen dezelfde referenties gebruiken bij het openen van on-premises of cloudbronnen.</span><span class="sxs-lookup"><span data-stu-id="b7918-130">Users can use the same credentials when accessing on-premises or cloud-based resources.</span></span> |
||||

## <a name="cloud-only-identity"></a><span data-ttu-id="b7918-131">Alleen cloudidentiteit</span><span class="sxs-lookup"><span data-stu-id="b7918-131">Cloud-only identity</span></span>

<span data-ttu-id="b7918-132">Voor een cloudidentiteit worden gebruikersaccounts gebruikt die alleen in Azure AD bestaan.</span><span class="sxs-lookup"><span data-stu-id="b7918-132">A cloud-only identity uses user accounts that exist only in Azure AD.</span></span> <span data-ttu-id="b7918-133">Cloud-only-identiteit wordt meestal gebruikt door kleine organisaties die geen on-premises servers hebben of GEEN AD DS gebruiken om lokale identiteiten te beheren.</span><span class="sxs-lookup"><span data-stu-id="b7918-133">Cloud-only identity is typically used by small organizations that do not have on-premises servers or do not use AD DS to manage local identities.</span></span> 

<span data-ttu-id="b7918-134">Hier zijn de basisonderdelen van alleen-cloudidentiteit.</span><span class="sxs-lookup"><span data-stu-id="b7918-134">Here are the basic components of cloud-only identity.</span></span>
 
![Basisonderdelen van alleen-cloudidentiteit](../media/about-microsoft-365-identity/cloud-only-identity.png)

<span data-ttu-id="b7918-136">Zowel on-premises als externe (online) gebruikers gebruiken hun Azure AD-gebruikersaccounts en -wachtwoorden om toegang te krijgen tot Microsoft 365-cloudservices.</span><span class="sxs-lookup"><span data-stu-id="b7918-136">Both on-premises and remote (online) users use their Azure AD user accounts and passwords to access Microsoft 365 cloud services.</span></span> <span data-ttu-id="b7918-137">Azure AD verifieert gebruikersreferenties op basis van de opgeslagen gebruikersaccounts en wachtwoorden.</span><span class="sxs-lookup"><span data-stu-id="b7918-137">Azure AD authenticates user credentials based on its stored user accounts and passwords.</span></span>

### <a name="administration"></a><span data-ttu-id="b7918-138">Beheer</span><span class="sxs-lookup"><span data-stu-id="b7918-138">Administration</span></span>
<span data-ttu-id="b7918-139">Omdat gebruikersaccounts alleen worden opgeslagen in Azure AD, beheert u cloudidentiteiten met hulpprogramma's zoals het [Microsoft 365-beheercentrum](../admin/add-users/index.yml) en [Windows PowerShell.](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="b7918-139">Because user accounts are only stored in Azure AD, you manage cloud identities with tools such as the [Microsoft 365 admin center](../admin/add-users/index.yml) and [Windows PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md).</span></span> 

## <a name="hybrid-identity"></a><span data-ttu-id="b7918-140">Hybride identiteit</span><span class="sxs-lookup"><span data-stu-id="b7918-140">Hybrid identity</span></span>

<span data-ttu-id="b7918-141">Hybride identiteit maakt gebruik van accounts die afkomstig zijn van een on-premises AD DS en die een kopie hebben in de Azure AD-tenant van een Microsoft 365-abonnement.</span><span class="sxs-lookup"><span data-stu-id="b7918-141">Hybrid identity uses accounts that originate in an on-premises AD DS and have a copy in the Azure AD tenant of a Microsoft 365 subscription.</span></span> <span data-ttu-id="b7918-142">De meeste wijzigingen stromen echter maar op één manier.</span><span class="sxs-lookup"><span data-stu-id="b7918-142">However, most changes only flow one way.</span></span> <span data-ttu-id="b7918-143">Wijzigingen die u aan te brengen in AD DS-gebruikersaccounts worden gesynchroniseerd met de kopie in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="b7918-143">Changes that you make to AD DS user accounts are synchronized to their copy in Azure AD.</span></span> <span data-ttu-id="b7918-144">Wijzigingen in cloudaccounts in Azure AD, zoals nieuwe gebruikersaccounts, worden echter niet gesynchroniseerd met AD DS.</span><span class="sxs-lookup"><span data-stu-id="b7918-144">But changes made to cloud-based accounts in Azure AD, such as new user accounts, are not synchronized with AD DS.</span></span>

<span data-ttu-id="b7918-145">Azure AD Connect biedt de lopende accountsynchronisatie.</span><span class="sxs-lookup"><span data-stu-id="b7918-145">Azure AD Connect provides the ongoing account synchronization.</span></span> <span data-ttu-id="b7918-146">Deze wordt uitgevoerd op een on-premises server, controleert op wijzigingen in de AD DS en doorgestuurd naar Azure AD.</span><span class="sxs-lookup"><span data-stu-id="b7918-146">It runs on an on-premises server, checks for changes in the AD DS, and forwards those changes to Azure AD.</span></span> <span data-ttu-id="b7918-147">Azure AD Connect biedt de mogelijkheid om te filteren welke accounts worden gesynchroniseerd en of u een gehashte versie van gebruikerswachtwoorden wilt synchroniseren, ook wel wachtwoordhashsynchronisatie (PHS) genoemd.</span><span class="sxs-lookup"><span data-stu-id="b7918-147">Azure AD Connect provides the ability to filter which accounts are synchronized and whether to synchronize a hashed version of user passwords, known as password hash synchronization (PHS).</span></span>

<span data-ttu-id="b7918-148">Wanneer u hybride identiteit implementeert, is uw on-premises AD DS de gezaghebbende bron voor accountgegevens.</span><span class="sxs-lookup"><span data-stu-id="b7918-148">When you implement hybrid identity, your on-premises AD DS is the authoritative source for account information.</span></span> <span data-ttu-id="b7918-149">Dit betekent dat u beheertaken voornamelijk on-premises uitvoert, die vervolgens worden gesynchroniseerd met Azure AD.</span><span class="sxs-lookup"><span data-stu-id="b7918-149">This means that you perform administration tasks mostly on-premises, which are then synchronized to Azure AD.</span></span> 

<span data-ttu-id="b7918-150">Hier zijn de onderdelen van hybride identiteit.</span><span class="sxs-lookup"><span data-stu-id="b7918-150">Here are the components of hybrid identity.</span></span>

![Onderdelen van hybride identiteit](../media/about-microsoft-365-identity/hybrid-identity.png)

<span data-ttu-id="b7918-152">De Azure AD-tenant heeft een kopie van de AD DS-accounts.</span><span class="sxs-lookup"><span data-stu-id="b7918-152">The Azure AD tenant has a copy of the AD DS accounts.</span></span> <span data-ttu-id="b7918-153">In deze configuratie verifiëren zowel on-premises als externe gebruikers die toegang hebben tot Microsoft 365-cloudservices zich tegen Azure AD.</span><span class="sxs-lookup"><span data-stu-id="b7918-153">In this configuration, both on-premises and remote users accessing Microsoft 365 cloud services authenticate against Azure AD.</span></span>

>[!Note]
><span data-ttu-id="b7918-154">U moet altijd Azure AD Connect gebruiken om gebruikersaccounts te synchroniseren voor hybride identiteit.</span><span class="sxs-lookup"><span data-stu-id="b7918-154">You always need to use Azure AD Connect to synchronize user accounts for hybrid identity.</span></span> <span data-ttu-id="b7918-155">U hebt de gesynchroniseerde gebruikersaccounts in Azure AD nodig voor het uitvoeren van licentietoewijzing en groepsbeheer, het configureren van machtigingen en andere beheertaken waarbij gebruikersaccounts zijn betrokken.</span><span class="sxs-lookup"><span data-stu-id="b7918-155">You need the synchronized user accounts in Azure AD to perform license assignment and group management, configure permissions, and other administrative tasks that involve user accounts.</span></span>
>

### <a name="administration"></a><span data-ttu-id="b7918-156">Beheer</span><span class="sxs-lookup"><span data-stu-id="b7918-156">Administration</span></span>

<span data-ttu-id="b7918-157">Omdat de oorspronkelijke en gezaghebbende gebruikersaccounts zijn opgeslagen in de on-premises AD DS, beheert u uw identiteiten met dezelfde hulpprogramma's als uw AD DS.</span><span class="sxs-lookup"><span data-stu-id="b7918-157">Because the original and authoritative user accounts are stored in the on-premises AD DS, you manage your identities with the same tools as you manage your AD DS.</span></span> 

<span data-ttu-id="b7918-158">U gebruikt het Microsoft 365-beheercentrum of PowerShell voor Microsoft 365 niet om gesynchroniseerde gebruikersaccounts te beheren in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="b7918-158">You don't use the Microsoft 365 admin center or PowerShell for Microsoft 365 to manage synchronized user accounts in Azure AD.</span></span>

## <a name="next-step"></a><span data-ttu-id="b7918-159">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="b7918-159">Next step</span></span>

<span data-ttu-id="b7918-160">Zie [Alleen-cloudidentiteit](cloud-only-identities.md)als u het cloud-only-identiteitsmodel nodig hebt.</span><span class="sxs-lookup"><span data-stu-id="b7918-160">If you need the cloud-only identity model, see [Cloud-only identity](cloud-only-identities.md).</span></span>

<span data-ttu-id="b7918-161">Zie Hybride identiteit als u het hybride identiteitsmodel [nodig hebt.](plan-for-directory-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="b7918-161">If you need the hybrid identity model, see [Hybrid identity](plan-for-directory-synchronization.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="b7918-162">Zie ook</span><span class="sxs-lookup"><span data-stu-id="b7918-162">See also</span></span>

[<span data-ttu-id="b7918-163">Overzicht van Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="b7918-163">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)