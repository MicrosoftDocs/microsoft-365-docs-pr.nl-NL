---
title: Microsoft 365-identiteits modellen en Azure Active Directory
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.date: 06/09/2020
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
description: Meer informatie over het beheren van de Azure AD User Identity-service in Microsoft 365 met Cloud only of Hybrid Identity types.
ms.openlocfilehash: d91e14f678e487365805b024e4025e9a39db0c2c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689530"
---
# <a name="microsoft-365-identity-models-and-azure-active-directory"></a><span data-ttu-id="c6b41-103">Microsoft 365-identiteits modellen en Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="c6b41-103">Microsoft 365 identity models and Azure Active Directory</span></span>

<span data-ttu-id="c6b41-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="c6b41-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="c6b41-105">Microsoft 365 maakt gebruik van Azure Active Directory (Azure AD), een op de cloud gebaseerde gebruikers-id en verificatieservice die deel uitmaakt van uw Microsoft 365-abonnement, voor het beheren van identiteiten en verificatie voor Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c6b41-105">Microsoft 365 uses Azure Active Directory (Azure AD), a cloud-based user identity and authentication service that is included with your Microsoft 365 subscription, to manage identities and authentication for Microsoft 365.</span></span> <span data-ttu-id="c6b41-106">De juiste configuratie van de identiteits infrastructuur is essentieel voor het beheren van gebruikers toegang en machtigingen voor Microsoft 365 voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="c6b41-106">Getting your identity infrastructure configured correctly is vital to managing Microsoft 365 user access and permissions for your organization.</span></span>

<span data-ttu-id="c6b41-107">Bekijk deze video voor een overzicht van identiteits modellen en authenticatie voor Microsoft 365 voordat u begint.</span><span class="sxs-lookup"><span data-stu-id="c6b41-107">Before you begin, watch this video for an overview of identity models and authentication for Microsoft 365.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

<span data-ttu-id="c6b41-108">Uw eerste planning is het identiteits model van Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c6b41-108">Your first planning choice is the Microsoft 365 identity model.</span></span>

## <a name="microsoft-365-identity-models"></a><span data-ttu-id="c6b41-109">Microsoft 365-identiteits modellen</span><span class="sxs-lookup"><span data-stu-id="c6b41-109">Microsoft 365 identity models</span></span>

<span data-ttu-id="c6b41-110">Voor het plannen van gebruikersaccounts moet u eerst inzicht krijgen in de twee identiteits modellen in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c6b41-110">To plan for user accounts, you first need to understand the two identity models in Microsoft 365.</span></span> <span data-ttu-id="c6b41-111">U kunt de identiteiten van uw organisatie alleen in de Cloud behouden, maar u kunt ook uw on-premises Active Directory Domain Services (AD DS)-id's bijhouden en ze gebruiken voor verificatie wanneer gebruikers toegang krijgen tot de Cloud Services van Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c6b41-111">You can maintain your organization's identities only in the cloud, or you can maintain your on-premises Active Directory Domain Services (AD DS) identities and use them for authentication when users access Microsoft 365 cloud services.</span></span>  

<span data-ttu-id="c6b41-112">Dit zijn de twee typen identiteiten, en het best passende en voordelen.</span><span class="sxs-lookup"><span data-stu-id="c6b41-112">Here are the two types of identity and their best fit and benefits.</span></span>

| <span data-ttu-id="c6b41-113">Kenmerk</span><span class="sxs-lookup"><span data-stu-id="c6b41-113">Attribute</span></span> | <span data-ttu-id="c6b41-114">Alleen voor Cloud-identiteit</span><span class="sxs-lookup"><span data-stu-id="c6b41-114">Cloud-only identity</span></span> | <span data-ttu-id="c6b41-115">Hybride identiteit</span><span class="sxs-lookup"><span data-stu-id="c6b41-115">Hybrid identity</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="c6b41-116">**Definitie**</span><span class="sxs-lookup"><span data-stu-id="c6b41-116">**Definition**</span></span> | <span data-ttu-id="c6b41-117">Het gebruikersaccount bestaat alleen in de Azure AD-Tenant voor uw Microsoft 365-abonnement.</span><span class="sxs-lookup"><span data-stu-id="c6b41-117">User account only exists in the Azure AD tenant for your Microsoft 365 subscription.</span></span> | <span data-ttu-id="c6b41-118">Gebruikersaccount bestaat in AD DS en een kopie bevindt zich ook in de Azure AD-Tenant voor uw Microsoft 365-abonnement.</span><span class="sxs-lookup"><span data-stu-id="c6b41-118">User account exists in AD DS and a copy is also in the Azure AD tenant for your Microsoft 365 subscription.</span></span> <span data-ttu-id="c6b41-119">Het gebruikersaccount in azure AD kan ook een gehasheerde versie van het wachtwoord voor een gehasheerde gebruikersaccount bevatten.</span><span class="sxs-lookup"><span data-stu-id="c6b41-119">The user account in Azure AD might also include a hashed version of the already hashed AD DS user account password.</span></span> |
| <span data-ttu-id="c6b41-120">**Hoe Microsoft 365 gebruikersreferenties verifieert**</span><span class="sxs-lookup"><span data-stu-id="c6b41-120">**How Microsoft 365 authenticates user credentials**</span></span> | <span data-ttu-id="c6b41-121">Met de Azure AD-Tenant voor uw Microsoft 365-abonnement wordt de authenticatie met de Cloud-identiteits account uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="c6b41-121">The Azure AD tenant for your Microsoft 365 subscription performs the authentication with the cloud identity account.</span></span> | <span data-ttu-id="c6b41-122">Met de Azure AD-Tenant voor uw Microsoft 365-abonnement wordt het verificatieproces verwerkt of wordt de gebruiker omgeleid naar een andere identiteitsprovider.</span><span class="sxs-lookup"><span data-stu-id="c6b41-122">The Azure AD tenant for your Microsoft 365 subscription either handles the authentication process or redirects the user to another identity provider.</span></span> |
| <span data-ttu-id="c6b41-123">**Geschikt voor**</span><span class="sxs-lookup"><span data-stu-id="c6b41-123">**Best for**</span></span> | <span data-ttu-id="c6b41-124">Organisaties die geen on-premises AD DS hebben of behoefte hebben.</span><span class="sxs-lookup"><span data-stu-id="c6b41-124">Organizations that do not have or need an on-premises AD DS.</span></span> | <span data-ttu-id="c6b41-125">Organisaties die AD DS of een andere identiteitsprovider gebruiken.</span><span class="sxs-lookup"><span data-stu-id="c6b41-125">Organizations using AD DS or another identity provider.</span></span> |
| <span data-ttu-id="c6b41-126">**Grootste voordeel**</span><span class="sxs-lookup"><span data-stu-id="c6b41-126">**Greatest benefit**</span></span> | <span data-ttu-id="c6b41-127">Eenvoudig te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="c6b41-127">Simple to use.</span></span> <span data-ttu-id="c6b41-128">Geen extra hulpmiddelen voor directory's of servers vereist.</span><span class="sxs-lookup"><span data-stu-id="c6b41-128">No extra directory tools or servers required.</span></span> | <span data-ttu-id="c6b41-129">Gebruikers kunnen dezelfde referenties gebruiken voor het openen van on-premises of Cloud bronnen.</span><span class="sxs-lookup"><span data-stu-id="c6b41-129">Users can use the same credentials when accessing on-premises or cloud-based resources.</span></span> |
||||

## <a name="cloud-only-identity"></a><span data-ttu-id="c6b41-130">Alleen voor Cloud-identiteit</span><span class="sxs-lookup"><span data-stu-id="c6b41-130">Cloud-only identity</span></span>

<span data-ttu-id="c6b41-131">Een identiteit in de Cloud maakt gebruik van gebruikersaccounts die alleen bestaan in azure AD.</span><span class="sxs-lookup"><span data-stu-id="c6b41-131">A cloud-only identity uses user accounts that exist only in Azure AD.</span></span> <span data-ttu-id="c6b41-132">De Cloud identiteit wordt meestal gebruikt door kleine organisaties die geen on-premises servers hebben en geen gebruik maken van AD DS voor het beheren van lokale identiteiten.</span><span class="sxs-lookup"><span data-stu-id="c6b41-132">Cloud identity is typically used by small organizations that do not have on-premises servers or do not use AD DS to manage local identities.</span></span> 

<span data-ttu-id="c6b41-133">Hier volgen de basisonderdelen van de identiteit van de Cloud.</span><span class="sxs-lookup"><span data-stu-id="c6b41-133">Here are the basic components of cloud-only identity.</span></span>
 
![Basisonderdelen van de alleen-Cloud identiteit](../media/about-microsoft-365-identity/cloud-only-identity.png)

<span data-ttu-id="c6b41-135">Gebruikers van on-premises en externe gebruikers (online) gebruiken hun gebruikersaccounts en wachtwoorden van Azure AD om toegang te krijgen tot de cloudservices van Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c6b41-135">Both on-premises and remote (online) users use their Azure AD user accounts and passwords to access Microsoft 365 cloud services.</span></span> <span data-ttu-id="c6b41-136">Azure AD verifieert gebruikersreferenties op basis van zijn opgeslagen gebruikersaccounts en wachtwoorden.</span><span class="sxs-lookup"><span data-stu-id="c6b41-136">Azure AD authenticates user credentials based on its stored user accounts and passwords.</span></span>

### <a name="administration"></a><span data-ttu-id="c6b41-137">Beheer</span><span class="sxs-lookup"><span data-stu-id="c6b41-137">Administration</span></span>
<span data-ttu-id="c6b41-138">Aangezien gebruikersaccounts alleen in azure AD zijn opgeslagen, beheert u Cloud Identities met hulpprogramma's zoals het [Microsoft 365-Beheercentrum](https://admin.microsoft.com) en [Windows PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="c6b41-138">Because user accounts are only stored in Azure AD, you manage cloud identities with tools such as the [Microsoft 365 admin center](https://admin.microsoft.com) and [Windows PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md).</span></span> 

## <a name="hybrid-identity"></a><span data-ttu-id="c6b41-139">Hybride identiteit</span><span class="sxs-lookup"><span data-stu-id="c6b41-139">Hybrid identity</span></span>

<span data-ttu-id="c6b41-140">De Hybrid Identity gebruikt accounts die afkomstig zijn van een on-premises AD DS en die een kopie hebben in de Azure AD-Tenant van een abonnement van Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c6b41-140">Hybrid identity uses accounts that originate in an on-premises AD DS and have a copy in the Azure AD tenant of a Microsoft 365 subscription.</span></span> <span data-ttu-id="c6b41-141">De meeste wijzigingen zijn echter maar één manier.</span><span class="sxs-lookup"><span data-stu-id="c6b41-141">However, most changes only flow one way.</span></span> <span data-ttu-id="c6b41-142">Wijzigingen die u aanbrengt in AD DS-gebruikersaccounts, worden gesynchroniseerd met hun kopie in azure AD.</span><span class="sxs-lookup"><span data-stu-id="c6b41-142">Changes that you make to AD DS user accounts are synchronized to their copy in Azure AD.</span></span> <span data-ttu-id="c6b41-143">Wijzigingen die zijn aangebracht in Cloud accounts in azure AD, zoals nieuwe gebruikersaccounts, worden niet gesynchroniseerd met AD DS.</span><span class="sxs-lookup"><span data-stu-id="c6b41-143">But changes made to cloud-based accounts in Azure AD, such as new user accounts, are not synchronized with AD DS.</span></span>

<span data-ttu-id="c6b41-144">Azure AD Connect biedt de voortdurende synchronisatie van uw account.</span><span class="sxs-lookup"><span data-stu-id="c6b41-144">Azure AD Connect provides the ongoing account synchronization.</span></span> <span data-ttu-id="c6b41-145">De app wordt uitgevoerd op een on-premises server, controleert op wijzigingen in de AD DS en stuurt deze wijzigingen door naar Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c6b41-145">It runs on an on-premises server, checks for changes in the AD DS, and forwards those changes to Azure AD.</span></span> <span data-ttu-id="c6b41-146">Azure AD Connect biedt de mogelijkheid om te filteren welke accounts worden gesynchroniseerd en of u een gehasheerde versie van gebruikerswachtwoorden wilt synchroniseren, ook wel hash-synchronisatie (PHS) genoemd.</span><span class="sxs-lookup"><span data-stu-id="c6b41-146">Azure AD Connect provides the ability to filter which accounts are synchronized and whether to synchronize a hashed version of user passwords, known as password hash synchronization (PHS).</span></span>

<span data-ttu-id="c6b41-147">Wanneer u hybride identiteit implementeert, is uw on-premises AD DS de gezaghebbende bron voor de accountgegevens.</span><span class="sxs-lookup"><span data-stu-id="c6b41-147">When you implement hybrid identity, your on-premises AD DS is the authoritative source for account information.</span></span> <span data-ttu-id="c6b41-148">Dit betekent dat u beheertaken doorgaans on-premise uitvoert, die vervolgens worden gesynchroniseerd met Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c6b41-148">This means that you perform administration tasks mostly on-premises, which are then synchronized to Azure AD.</span></span> 

<span data-ttu-id="c6b41-149">Hier volgen de onderdelen van de Hybrid Identity.</span><span class="sxs-lookup"><span data-stu-id="c6b41-149">Here are the components of hybrid identity.</span></span>

![Onderdelen van een hybride identiteit](../media/about-microsoft-365-identity/hybrid-identity.png)

<span data-ttu-id="c6b41-151">De Azure AD-Tenant heeft een kopie van de AD DS-accounts.</span><span class="sxs-lookup"><span data-stu-id="c6b41-151">The Azure AD tenant has a copy of the AD DS accounts.</span></span> <span data-ttu-id="c6b41-152">In deze configuratie wordt zowel on-premises als externe gebruikers die toegang hebben tot Microsoft 365 cloudservices verifiëren tegen Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c6b41-152">In this configuration, both on-premises and remote users accessing Microsoft 365 cloud services authenticate against Azure AD.</span></span>

>[!Note]
><span data-ttu-id="c6b41-153">U moet altijd Azure AD Connect gebruiken om gebruikersaccounts voor Hybrid Identity te synchroniseren.</span><span class="sxs-lookup"><span data-stu-id="c6b41-153">You always need to use Azure AD Connect to synchronize user accounts for hybrid identity.</span></span> <span data-ttu-id="c6b41-154">Voor het uitvoeren van licentietoewijzing en groepsbeheer kunt u de gesynchroniseerde gebruikersaccounts in azure AD uitvoeren, machtigingen configureren en andere beheertaken waarbij gebruikersaccounts worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="c6b41-154">You need the synchronized user accounts in Azure AD to perform license assignment and group management, configure permissions, and other administrative tasks that involve user accounts.</span></span>
>

### <a name="administration"></a><span data-ttu-id="c6b41-155">Beheer</span><span class="sxs-lookup"><span data-stu-id="c6b41-155">Administration</span></span>

<span data-ttu-id="c6b41-156">Aangezien de accounts voor de oorspronkelijke en gemachtigde gebruikers zijn opgeslagen in de on-premises AD DS, beheert u uw identiteiten met dezelfde hulpmiddelen als AD DS, zoals het hulpprogramma Active Directory gebruikers en computers.</span><span class="sxs-lookup"><span data-stu-id="c6b41-156">Because the original and authoritative user accounts are stored in the on-premises AD DS, you manage your identities with the same tools as AD DS, such as the Active Directory Users and Computers tool.</span></span> 

<span data-ttu-id="c6b41-157">U gebruikt het Microsoft 365-Beheercentrum of PowerShell voor Microsoft 365 niet voor het beheren van gesynchroniseerde gebruikersaccounts in azure AD.</span><span class="sxs-lookup"><span data-stu-id="c6b41-157">You don't use the Microsoft 365 admin center or PowerShell for Microsoft 365 to manage synchronized user accounts in Azure AD.</span></span>

## <a name="next-step"></a><span data-ttu-id="c6b41-158">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="c6b41-158">Next step</span></span>

<span data-ttu-id="c6b41-159">Als u het identiteits model voor de Cloud only nodig hebt, raadpleegt u de [Cloud-only-identiteit](cloud-only-identities.md).</span><span class="sxs-lookup"><span data-stu-id="c6b41-159">If you need the cloud-only identity model, see [Cloud-only identity](cloud-only-identities.md).</span></span>

<span data-ttu-id="c6b41-160">Als u het Hybrid Identity model nodig hebt, raadpleegt u [hybride identiteit](plan-for-directory-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="c6b41-160">If you need the hybrid identity model, see [Hybrid identity](plan-for-directory-synchronization.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="c6b41-161">Zie ook</span><span class="sxs-lookup"><span data-stu-id="c6b41-161">See also</span></span>

[<span data-ttu-id="c6b41-162">Overzicht van Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="c6b41-162">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)
