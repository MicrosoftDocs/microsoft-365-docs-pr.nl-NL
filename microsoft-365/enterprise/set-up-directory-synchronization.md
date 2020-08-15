---
title: Adreslijstsynchronisatie voor Microsoft 365 instellen
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 06/15/2020
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED15
- MBS150
- BCS160
ms.assetid: 1b3b5318-6977-42ed-b5c7-96fa74b08846
description: Leer hoe u adreslijstsynchronisatie tussen Microsoft 365 en uw on-premises Active Directory kunt instellen.
ms.openlocfilehash: 3a846a6c558f221c1869dce6da27e3d34680f75d
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689007"
---
# <a name="set-up-directory-synchronization-for-microsoft-365"></a><span data-ttu-id="38726-103">Adreslijstsynchronisatie voor Microsoft 365 instellen</span><span class="sxs-lookup"><span data-stu-id="38726-103">Set up directory synchronization for Microsoft 365</span></span>

<span data-ttu-id="38726-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="38726-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="38726-105">In Microsoft 365 wordt een Azure Active Directory (Azure AD)-Tenant gebruikt voor het opslaan en beheren van identiteiten voor verificatie en machtigingen voor toegang tot Cloud bronnen.</span><span class="sxs-lookup"><span data-stu-id="38726-105">Microsoft 365 uses an Azure Active Directory (Azure AD) tenant to store and manage identities for authentication and permissions to access cloud-based resources.</span></span> 

<span data-ttu-id="38726-106">Als u een on-premises Active Directory Domain Services (AD DS) hebt, kunt u uw gebruikersaccounts, groepen en contactpersonen van AD DS synchroniseren met de Azure AD-Tenant van uw Microsoft 365-abonnement.</span><span class="sxs-lookup"><span data-stu-id="38726-106">If you have an on-premises Active Directory Domain Services (AD DS), you can synchronize your AD DS user accounts, groups, and contacts with the Azure AD tenant of your Microsoft 365 subscription.</span></span> <span data-ttu-id="38726-107">Dit is de hybride identiteit voor Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="38726-107">This is hybrid identity for Microsoft 365.</span></span> <span data-ttu-id="38726-108">Hier volgen de onderdelen.</span><span class="sxs-lookup"><span data-stu-id="38726-108">Here are its components.</span></span>

![Onderdelen van adreslijstsynchronisatie voor Microsoft 365](../media/about-microsoft-365-identity/hybrid-identity.png)

<span data-ttu-id="38726-110">Azure AD Connect wordt uitgevoerd op een on-premises server en de AD DS wordt gesynchroniseerd met de Azure AD-Tenant.</span><span class="sxs-lookup"><span data-stu-id="38726-110">Azure AD Connect runs on an on-premises server and synchronizes your AD DS with the Azure AD tenant.</span></span> <span data-ttu-id="38726-111">Naast adreslijstsynchronisatie kunt u ook deze verificatie-opties opgeven:</span><span class="sxs-lookup"><span data-stu-id="38726-111">Along with directory synchronization, you can also specify these authentication options:</span></span>

- <span data-ttu-id="38726-112">Synchronisatie van wachtwoord hash (PHS)</span><span class="sxs-lookup"><span data-stu-id="38726-112">Password hash synchronization (PHS)</span></span>

  <span data-ttu-id="38726-113">Azure AD voert de authenticatie zelf uit.</span><span class="sxs-lookup"><span data-stu-id="38726-113">Azure AD performs the authentication itself.</span></span>

- <span data-ttu-id="38726-114">Pass Through-verificatie (PTA)</span><span class="sxs-lookup"><span data-stu-id="38726-114">Pass-through authentication (PTA)</span></span>

  <span data-ttu-id="38726-115">Azure AD Active Directory heeft de authenticatie uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="38726-115">Azure AD has AD DS perform the authentication.</span></span>

- <span data-ttu-id="38726-116">Federatieve verificatie</span><span class="sxs-lookup"><span data-stu-id="38726-116">Federated authentication</span></span>

  <span data-ttu-id="38726-117">Azure AD stuurt de clientcomputer om authenticatie vragen om contact op te nemen met een andere identiteitsprovider.</span><span class="sxs-lookup"><span data-stu-id="38726-117">Azure AD redirects the client computer requesting authentication to contact another identity provider.</span></span>

<span data-ttu-id="38726-118">Zie [hybride identiteiten](plan-for-directory-synchronization.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="38726-118">See [Hybrid identities](plan-for-directory-synchronization.md) for more information.</span></span>
  
## <a name="1-review-prerequisites-for-azure-ad-connect"></a><span data-ttu-id="38726-119">1. vereisten voor Azure AD Connect controleren</span><span class="sxs-lookup"><span data-stu-id="38726-119">1. Review prerequisites for Azure AD Connect</span></span>

<span data-ttu-id="38726-120">U krijgt een gratis Azure AD-abonnement met uw abonnement op Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="38726-120">You get a free Azure AD subscription with your Microsoft 365 subscription.</span></span> <span data-ttu-id="38726-121">Wanneer u adreslijstsynchronisatie instelt, installeert u Azure AD Connect op een van uw on-premises servers.</span><span class="sxs-lookup"><span data-stu-id="38726-121">When you set up directory synchronization, you will install Azure AD Connect on one of your on-premises servers.</span></span>
  
<span data-ttu-id="38726-122">Voor Microsoft 365 moet u het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="38726-122">For Microsoft 365 you'll need to:</span></span>
  
- <span data-ttu-id="38726-123">Controleer uw on-premises domein.</span><span class="sxs-lookup"><span data-stu-id="38726-123">Verify your on-premises domain.</span></span> <span data-ttu-id="38726-124">Met de wizard Azure AD Connect wordt u begeleid.</span><span class="sxs-lookup"><span data-stu-id="38726-124">The Azure AD Connect wizard guides you through this.</span></span>
- <span data-ttu-id="38726-125">Download de gebruikersnamen en wachtwoorden voor de beheerdersaccounts van uw Microsoft 365-Tenant en AD DS.</span><span class="sxs-lookup"><span data-stu-id="38726-125">Obtain the user names and passwords for the admin accounts of your Microsoft 365 tenant and AD DS.</span></span>

<span data-ttu-id="38726-126">Voor uw on-premises server waarop u Azure AD Connect installeert, hebt u het volgende nodig:</span><span class="sxs-lookup"><span data-stu-id="38726-126">For your on-premises server on which you install Azure AD Connect, you'll need:</span></span>
  
|<span data-ttu-id="38726-127">**Server OS**</span><span class="sxs-lookup"><span data-stu-id="38726-127">**Server OS**</span></span>|<span data-ttu-id="38726-128">**Overige software**</span><span class="sxs-lookup"><span data-stu-id="38726-128">**Other software**</span></span>|
|:-----|:-----|
|<span data-ttu-id="38726-129">Windows Server 2012 R2 en hoger</span><span class="sxs-lookup"><span data-stu-id="38726-129">Windows Server 2012 R2 and later</span></span> | <span data-ttu-id="38726-130">-PowerShell is standaard geïnstalleerd; geen actie vereist.</span><span class="sxs-lookup"><span data-stu-id="38726-130">- PowerShell is installed by default, no action is required.</span></span>  <br> <span data-ttu-id="38726-131">-Net 4.5.1 en nieuwere versies zijn beschikbaar via Windows Update.</span><span class="sxs-lookup"><span data-stu-id="38726-131">- Net 4.5.1 and later releases are offered through Windows Update.</span></span> <span data-ttu-id="38726-132">Zorg dat u de meest recente updates voor Windows Server hebt geïnstalleerd in het Configuratiescherm.</span><span class="sxs-lookup"><span data-stu-id="38726-132">Make sure you have installed the latest updates to Windows Server in the Control Panel.</span></span> |
|<span data-ttu-id="38726-133">Windows Server 2008 R2 met Service Pack 1 (SP1) \* \* of Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="38726-133">Windows Server 2008 R2 with Service Pack 1 (SP1)\*\* or Windows Server 2012</span></span> | <span data-ttu-id="38726-134">-De nieuwste versie van PowerShell is beschikbaar in Windows Management Framework 4,0.</span><span class="sxs-lookup"><span data-stu-id="38726-134">- The latest version of PowerShell is available in Windows Management Framework 4.0.</span></span> <span data-ttu-id="38726-135">Zoek de app op het [Microsoft Download centrum](https://go.microsoft.com/fwlink/p/?LinkId=717996).</span><span class="sxs-lookup"><span data-stu-id="38726-135">Search for it on [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996).</span></span>  <br> <span data-ttu-id="38726-136">-.Net 4.5.1 en nieuwere releases zijn beschikbaar in het [Microsoft Download centrum](https://go.microsoft.com/fwlink/p/?LinkId=717996).</span><span class="sxs-lookup"><span data-stu-id="38726-136">- .Net 4.5.1 and later releases are available on [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996).</span></span> |
|<span data-ttu-id="38726-137">Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="38726-137">Windows Server 2008</span></span> | <span data-ttu-id="38726-138">-De nieuwste ondersteunde versie van PowerShell is beschikbaar in Windows Management Framework 3,0, dat beschikbaar is in het [Microsoft Download centrum](https://go.microsoft.com/fwlink/p/?LinkId=717996).</span><span class="sxs-lookup"><span data-stu-id="38726-138">- The latest supported version of PowerShell is available in Windows Management Framework 3.0, available on [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996).</span></span>  <br> <span data-ttu-id="38726-139">-.Net 4.5.1 en nieuwere releases zijn beschikbaar in het [Microsoft Download centrum](https://go.microsoft.com/fwlink/p/?LinkId=717996).</span><span class="sxs-lookup"><span data-stu-id="38726-139">- .Net 4.5.1 and later releases are available on [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996).</span></span> |

<span data-ttu-id="38726-140">Zie vereisten [voor Azure Active Directory Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites) voor de details van hardware, software, account-en machtigings vereisten, vereisten voor de SSL-certificaten en de object limieten voor Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="38726-140">See [Prerequisites for Azure Active Directory Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites) for the details of hardware, software, account and permissions requirements, SSL certificate requirements, and object limits for Azure AD Connect.</span></span>
  
<span data-ttu-id="38726-141">U kunt ook de geschiedenis van de [release geschiedenis](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-version-history) van Azure AD Connect bekijken om te zien wat er is inbegrepen en opgelost in elke versie.</span><span class="sxs-lookup"><span data-stu-id="38726-141">You can also review the Azure AD Connect [version release history](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-version-history) to see what is included and fixed in each release.</span></span>

## <a name="2-install-azure-ad-connect-and-configure-directory-synchronization"></a><span data-ttu-id="38726-142">2. Azure AD Connect installeren en Adreslijstsynchronisatie configureren</span><span class="sxs-lookup"><span data-stu-id="38726-142">2. Install Azure AD Connect and configure directory synchronization</span></span>

<span data-ttu-id="38726-143">Voordat u begint, moet u het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="38726-143">Before you begin, make sure you have:</span></span>

- <span data-ttu-id="38726-144">De gebruikersnaam en het wachtwoord van een globale beheerder van Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="38726-144">The user name and password of a Microsoft 365 global admin</span></span>
- <span data-ttu-id="38726-145">De gebruikersnaam en het wachtwoord van een AD DS-domeinbeheerder</span><span class="sxs-lookup"><span data-stu-id="38726-145">The user name and password of an AD DS domain administrator</span></span>
- <span data-ttu-id="38726-146">Welke verificatiemethode (PHS, PTA, federatieve)</span><span class="sxs-lookup"><span data-stu-id="38726-146">Which authentication method (PHS, PTA, federated)</span></span>
- <span data-ttu-id="38726-147">Of u gebruikmaakt [van eenmalige aanmelding via Azure AD (SSO)](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sso)</span><span class="sxs-lookup"><span data-stu-id="38726-147">Whether you want to use [Azure AD Seamless Single Sign-on (SSO)](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sso)</span></span>

<span data-ttu-id="38726-148">Volg deze stappen:</span><span class="sxs-lookup"><span data-stu-id="38726-148">Follow these steps:</span></span>

1. <span data-ttu-id="38726-149">Meld u aan bij het [Microsoft 365-Beheercentrum](https://admin.microsoft.com) ( https://admin.microsoft.com) en kies **gebruikers** \> **actieve gebruikers** in de navigatie aan de linkerkant.</span><span class="sxs-lookup"><span data-stu-id="38726-149">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) (https://admin.microsoft.com) and choose **Users** \> **Active Users** on the left navigation.</span></span>
2. <span data-ttu-id="38726-150">Kies op de pagina **actieve gebruikers** de optie **meer** (drie stippen) \> **adreslijstsynchronisatie**.</span><span class="sxs-lookup"><span data-stu-id="38726-150">On the **Active users** page, choose **More** (three dots) \> **Directory synchronization**.</span></span>
  
3. <span data-ttu-id="38726-151">Selecteer op de pagina **Azure Active Directory Preparation** de optie **Ga naar het Download centrum om de koppeling naar het Azure AD Connect-hulpprogramma** te downloaden om aan de slag te gaan.</span><span class="sxs-lookup"><span data-stu-id="38726-151">On the **Azure Active Directory preparation** page, select the **Go to the Download center to get the Azure AD Connect tool** link to get started.</span></span> 
4. <span data-ttu-id="38726-152">Voer de stappen uit in [Azure AD Connect en Azure AD Connect Health Installation](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-roadmap).</span><span class="sxs-lookup"><span data-stu-id="38726-152">Follow the steps in [Azure AD Connect and Azure AD Connect Health installation roadmap](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-roadmap).</span></span>

## <a name="3-finish-setting-up-domains"></a><span data-ttu-id="38726-153">3. het instellen van domeinen voltooien</span><span class="sxs-lookup"><span data-stu-id="38726-153">3. Finish setting up domains</span></span>

<span data-ttu-id="38726-154">Volg de stappen in [DNS-records voor Microsoft 365 maken wanneer u uw DNS-records beheert](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) om het instellen van uw domein te voltooien.</span><span class="sxs-lookup"><span data-stu-id="38726-154">Follow the steps in [Create DNS records for Microsoft 365 when you manage your DNS records](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) to finish setting up your domains.</span></span>

## <a name="next-step"></a><span data-ttu-id="38726-155">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="38726-155">Next step</span></span>

[<span data-ttu-id="38726-156">Licenties toewijzen aan gebruikersaccounts</span><span class="sxs-lookup"><span data-stu-id="38726-156">Assign licenses to user accounts</span></span>](assign-licenses-to-user-accounts.md)
