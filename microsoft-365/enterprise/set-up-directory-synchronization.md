---
title: Adreslijstsynchronisatie instellen voor Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
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
description: Meer informatie over het instellen van adreslijstsynchronisatie tussen Microsoft 365 en uw on-premises Active Directory.
ms.openlocfilehash: 51cf52bd81004157606c884fd4f0b5d3604b877a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924902"
---
# <a name="set-up-directory-synchronization-for-microsoft-365"></a><span data-ttu-id="ef505-103">Adreslijstsynchronisatie instellen voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ef505-103">Set up directory synchronization for Microsoft 365</span></span>

<span data-ttu-id="ef505-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="ef505-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="ef505-105">Microsoft 365 gebruikt een Azure Active Directory (Azure AD)-tenant om identiteiten op te slaan en te beheren voor verificatie en machtigingen voor toegang tot cloudbronnen.</span><span class="sxs-lookup"><span data-stu-id="ef505-105">Microsoft 365 uses an Azure Active Directory (Azure AD) tenant to store and manage identities for authentication and permissions to access cloud-based resources.</span></span> 

<span data-ttu-id="ef505-106">Als u een on-premises AD DS-domein of -forest (Active Directory Domain Services) hebt, kunt u uw AD DS-gebruikersaccounts, groepen en contactpersonen synchroniseren met de Azure AD-tenant van uw Microsoft 365-abonnement.</span><span class="sxs-lookup"><span data-stu-id="ef505-106">If you have an on-premises Active Directory Domain Services (AD DS) domain or forest, you can synchronize your AD DS user accounts, groups, and contacts with the Azure AD tenant of your Microsoft 365 subscription.</span></span> <span data-ttu-id="ef505-107">Dit is een hybride identiteit voor Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ef505-107">This is hybrid identity for Microsoft 365.</span></span> <span data-ttu-id="ef505-108">Hier zijn de onderdelen.</span><span class="sxs-lookup"><span data-stu-id="ef505-108">Here are its components.</span></span>

![Onderdelen van adreslijstsynchronisatie voor Microsoft 365](../media/about-microsoft-365-identity/hybrid-identity.png)

<span data-ttu-id="ef505-110">Azure AD Verbinding maken wordt uitgevoerd op een on-premises server en synchroniseert uw AD DS met de Azure AD-tenant.</span><span class="sxs-lookup"><span data-stu-id="ef505-110">Azure AD Connect runs on an on-premises server and synchronizes your AD DS with the Azure AD tenant.</span></span> <span data-ttu-id="ef505-111">Naast adreslijstsynchronisatie kunt u ook de volgende verificatieopties opgeven:</span><span class="sxs-lookup"><span data-stu-id="ef505-111">Along with directory synchronization, you can also specify these authentication options:</span></span>

- <span data-ttu-id="ef505-112">Wachtwoordhashsynchronisatie (PHS)</span><span class="sxs-lookup"><span data-stu-id="ef505-112">Password hash synchronization (PHS)</span></span>

  <span data-ttu-id="ef505-113">Azure AD voert de verificatie zelf uit.</span><span class="sxs-lookup"><span data-stu-id="ef505-113">Azure AD performs the authentication itself.</span></span>

- <span data-ttu-id="ef505-114">Pass Through-verificatie (PTA)</span><span class="sxs-lookup"><span data-stu-id="ef505-114">Pass-through authentication (PTA)</span></span>

  <span data-ttu-id="ef505-115">Azure AD heeft AD DS de verificatie laten uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="ef505-115">Azure AD has AD DS perform the authentication.</span></span>

- <span data-ttu-id="ef505-116">Federatieve verificatie</span><span class="sxs-lookup"><span data-stu-id="ef505-116">Federated authentication</span></span>

  <span data-ttu-id="ef505-117">Azure AD verwijst de clientcomputer die verificatie aanvraagt naar een andere identiteitsprovider.</span><span class="sxs-lookup"><span data-stu-id="ef505-117">Azure AD refers the client computer requesting authentication to another identity provider.</span></span>

<span data-ttu-id="ef505-118">Zie [Hybride identiteiten voor](plan-for-directory-synchronization.md) meer informatie.</span><span class="sxs-lookup"><span data-stu-id="ef505-118">See [Hybrid identities](plan-for-directory-synchronization.md) for more information.</span></span>
  
## <a name="1-review-prerequisites-for-azure-ad-connect"></a><span data-ttu-id="ef505-119">1. Controleer vereisten voor Azure AD-Verbinding maken</span><span class="sxs-lookup"><span data-stu-id="ef505-119">1. Review prerequisites for Azure AD Connect</span></span>

<span data-ttu-id="ef505-120">U krijgt een gratis Azure AD-abonnement met uw Microsoft 365 abonnement.</span><span class="sxs-lookup"><span data-stu-id="ef505-120">You get a free Azure AD subscription with your Microsoft 365 subscription.</span></span> <span data-ttu-id="ef505-121">Wanneer u adreslijstsynchronisatie in stelt, installeert u Azure AD Verbinding maken op een van uw on-premises servers.</span><span class="sxs-lookup"><span data-stu-id="ef505-121">When you set up directory synchronization, you will install Azure AD Connect on one of your on-premises servers.</span></span>
  
<span data-ttu-id="ef505-122">Voor Microsoft 365 moet u het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="ef505-122">For Microsoft 365 you'll need to:</span></span>
  
- <span data-ttu-id="ef505-123">Controleer uw on-premises domein.</span><span class="sxs-lookup"><span data-stu-id="ef505-123">Verify your on-premises domain.</span></span> <span data-ttu-id="ef505-124">De wizard Azure AD Verbinding maken begeleidt u hier doorheen.</span><span class="sxs-lookup"><span data-stu-id="ef505-124">The Azure AD Connect wizard guides you through this.</span></span>
- <span data-ttu-id="ef505-125">Verkrijg de gebruikersnamen en wachtwoorden voor de beheerdersaccounts van uw Microsoft 365 tenant en AD DS.</span><span class="sxs-lookup"><span data-stu-id="ef505-125">Obtain the user names and passwords for the admin accounts of your Microsoft 365 tenant and AD DS.</span></span>

<span data-ttu-id="ef505-126">Voor uw on-premises server waarop u Azure AD Verbinding maken, hebt u het volgende nodig:</span><span class="sxs-lookup"><span data-stu-id="ef505-126">For your on-premises server on which you install Azure AD Connect, you'll need:</span></span>
  
|<span data-ttu-id="ef505-127">**Server OS**</span><span class="sxs-lookup"><span data-stu-id="ef505-127">**Server OS**</span></span>|<span data-ttu-id="ef505-128">**Andere software**</span><span class="sxs-lookup"><span data-stu-id="ef505-128">**Other software**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ef505-129">Windows Server 2012 R2 en hoger</span><span class="sxs-lookup"><span data-stu-id="ef505-129">Windows Server 2012 R2 and later</span></span> | <span data-ttu-id="ef505-130">- PowerShell is standaard geïnstalleerd, er is geen actie vereist.</span><span class="sxs-lookup"><span data-stu-id="ef505-130">- PowerShell is installed by default, no action is required.</span></span>  <br> <span data-ttu-id="ef505-131">- Net 4.5.1 en latere versies worden aangeboden via Windows Update.</span><span class="sxs-lookup"><span data-stu-id="ef505-131">- Net 4.5.1 and later releases are offered through Windows Update.</span></span> <span data-ttu-id="ef505-132">Zorg ervoor dat u de meest recente updates hebt geïnstalleerd Windows Server in het Configuratiescherm.</span><span class="sxs-lookup"><span data-stu-id="ef505-132">Make sure you have installed the latest updates to Windows Server in the Control Panel.</span></span> |
|<span data-ttu-id="ef505-133">Windows Server 2008 R2 met Service Pack 1 (SP1)\*\* of Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="ef505-133">Windows Server 2008 R2 with Service Pack 1 (SP1)\*\* or Windows Server 2012</span></span> | <span data-ttu-id="ef505-134">- De nieuwste versie van PowerShell is beschikbaar in Windows Management Framework 4.0.</span><span class="sxs-lookup"><span data-stu-id="ef505-134">- The latest version of PowerShell is available in Windows Management Framework 4.0.</span></span> <span data-ttu-id="ef505-135">Zoek deze in [het Microsoft Downloadcentrum.](https://go.microsoft.com/fwlink/p/?LinkId=717996)</span><span class="sxs-lookup"><span data-stu-id="ef505-135">Search for it on [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996).</span></span>  <br> <span data-ttu-id="ef505-136">- .Net 4.5.1 en latere versies zijn beschikbaar in [het Microsoft Downloadcentrum.](https://go.microsoft.com/fwlink/p/?LinkId=717996)</span><span class="sxs-lookup"><span data-stu-id="ef505-136">- .Net 4.5.1 and later releases are available on [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996).</span></span> |
|<span data-ttu-id="ef505-137">Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="ef505-137">Windows Server 2008</span></span> | <span data-ttu-id="ef505-138">- De meest recente ondersteunde versie van PowerShell is beschikbaar in Windows Management Framework 3.0, beschikbaar in [het Microsoft Downloadcentrum.](https://go.microsoft.com/fwlink/p/?LinkId=717996)</span><span class="sxs-lookup"><span data-stu-id="ef505-138">- The latest supported version of PowerShell is available in Windows Management Framework 3.0, available on [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996).</span></span>  <br> <span data-ttu-id="ef505-139">- .Net 4.5.1 en latere versies zijn beschikbaar in [het Microsoft Downloadcentrum.](https://go.microsoft.com/fwlink/p/?LinkId=717996)</span><span class="sxs-lookup"><span data-stu-id="ef505-139">- .Net 4.5.1 and later releases are available on [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996).</span></span> |

<span data-ttu-id="ef505-140">Zie [Vereisten voor Azure Active Directory Verbinding maken](/azure/active-directory/hybrid/how-to-connect-install-prerequisites) voor de details van hardware-, software-, account- en machtigingsvereisten, SSL-certificaatvereisten en objectlimieten voor Azure AD-Verbinding maken.</span><span class="sxs-lookup"><span data-stu-id="ef505-140">See [Prerequisites for Azure Active Directory Connect](/azure/active-directory/hybrid/how-to-connect-install-prerequisites) for the details of hardware, software, account and permissions requirements, SSL certificate requirements, and object limits for Azure AD Connect.</span></span>
  
<span data-ttu-id="ef505-141">U kunt ook de versieversiegeschiedenis van Azure AD Verbinding maken [bekijken](/azure/active-directory/hybrid/reference-connect-version-history) om te zien wat er is opgenomen en opgelost in elke release.</span><span class="sxs-lookup"><span data-stu-id="ef505-141">You can also review the Azure AD Connect [version release history](/azure/active-directory/hybrid/reference-connect-version-history) to see what is included and fixed in each release.</span></span>

## <a name="2-install-azure-ad-connect-and-configure-directory-synchronization"></a><span data-ttu-id="ef505-142">2. Azure AD installeren Verbinding maken adreslijstsynchronisatie configureren</span><span class="sxs-lookup"><span data-stu-id="ef505-142">2. Install Azure AD Connect and configure directory synchronization</span></span>

<span data-ttu-id="ef505-143">Zorg ervoor dat u het volgende hebt voordat u begint:</span><span class="sxs-lookup"><span data-stu-id="ef505-143">Before you begin, make sure you have:</span></span>

- <span data-ttu-id="ef505-144">De gebruikersnaam en het wachtwoord van een Microsoft 365 globale beheerder</span><span class="sxs-lookup"><span data-stu-id="ef505-144">The user name and password of a Microsoft 365 global admin</span></span>
- <span data-ttu-id="ef505-145">De gebruikersnaam en het wachtwoord van een AD DS-domeinbeheerder</span><span class="sxs-lookup"><span data-stu-id="ef505-145">The user name and password of an AD DS domain administrator</span></span>
- <span data-ttu-id="ef505-146">Welke verificatiemethode (PHS, PTA, federatief)</span><span class="sxs-lookup"><span data-stu-id="ef505-146">Which authentication method (PHS, PTA, federated)</span></span>
- <span data-ttu-id="ef505-147">Of u Azure [AD Seamless Single Sign-on (SSO) wilt gebruiken](/azure/active-directory/hybrid/how-to-connect-sso)</span><span class="sxs-lookup"><span data-stu-id="ef505-147">Whether you want to use [Azure AD Seamless Single Sign-on (SSO)](/azure/active-directory/hybrid/how-to-connect-sso)</span></span>

<span data-ttu-id="ef505-148">Volg deze stappen:</span><span class="sxs-lookup"><span data-stu-id="ef505-148">Follow these steps:</span></span>

1. <span data-ttu-id="ef505-149">Meld u aan bij [het Microsoft 365 beheercentrum](https://admin.microsoft.com) ( https://admin.microsoft.com) en kies **Gebruikers** \> **actieve gebruikers** aan de linkerkant van de navigatie.</span><span class="sxs-lookup"><span data-stu-id="ef505-149">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) (https://admin.microsoft.com) and choose **Users** \> **Active Users** on the left navigation.</span></span>
2. <span data-ttu-id="ef505-150">Kies op **de pagina** Actieve gebruikers de **optie Meer** (drie puntjes) \> **Adreslijstsynchronisatie.**</span><span class="sxs-lookup"><span data-stu-id="ef505-150">On the **Active users** page, choose **More** (three dots) \> **Directory synchronization**.</span></span>
  
3. <span data-ttu-id="ef505-151">Selecteer op **Azure Active Directory pagina Voorbereiding** de optie Ga naar het Downloadcentrum om de koppeling Azure AD Verbinding maken **aan** de slag te gaan.</span><span class="sxs-lookup"><span data-stu-id="ef505-151">On the **Azure Active Directory preparation** page, select the **Go to the Download center to get the Azure AD Connect tool** link to get started.</span></span> 
4. <span data-ttu-id="ef505-152">Volg de stappen in [Azure AD Verbinding maken en Azure AD Verbinding maken Health installation roadmap](/azure/active-directory/hybrid/how-to-connect-install-roadmap).</span><span class="sxs-lookup"><span data-stu-id="ef505-152">Follow the steps in [Azure AD Connect and Azure AD Connect Health installation roadmap](/azure/active-directory/hybrid/how-to-connect-install-roadmap).</span></span>

## <a name="3-finish-setting-up-domains"></a><span data-ttu-id="ef505-153">3. Het instellen van domeinen voltooien</span><span class="sxs-lookup"><span data-stu-id="ef505-153">3. Finish setting up domains</span></span>

<span data-ttu-id="ef505-154">Volg de stappen in [DNS-records maken voor Microsoft 365 wanneer](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) u uw DNS-records beheert om het instellen van uw domeinen te voltooien.</span><span class="sxs-lookup"><span data-stu-id="ef505-154">Follow the steps in [Create DNS records for Microsoft 365 when you manage your DNS records](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) to finish setting up your domains.</span></span>

## <a name="next-step"></a><span data-ttu-id="ef505-155">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="ef505-155">Next step</span></span>

[<span data-ttu-id="ef505-156">Licenties aan gebruikersaccounts toewijzen</span><span class="sxs-lookup"><span data-stu-id="ef505-156">Assign licenses to user accounts</span></span>](assign-licenses-to-user-accounts.md)