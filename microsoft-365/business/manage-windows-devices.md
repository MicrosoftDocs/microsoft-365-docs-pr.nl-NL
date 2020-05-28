---
title: Ingeschakeld voor windows 10-apparaten met domeindie worden beheerd door Microsoft 365 voor bedrijven
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: Lees hoe u Microsoft 365 in staat stelt om lokale Windows 10-apparaten met Active Directory in slechts een paar stappen te beschermen.
ms.openlocfilehash: e7f83e620fbb43a478dba98f78d5f471a541aea7
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2020
ms.locfileid: "44403053"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-for-business"></a><span data-ttu-id="1b0d7-103">Ingeschakeld voor windows 10-apparaten met domeindie worden beheerd door Microsoft 365 voor bedrijven</span><span class="sxs-lookup"><span data-stu-id="1b0d7-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 for business</span></span>

<span data-ttu-id="1b0d7-104">Als uw organisatie on-premises Windows Server Active Directory gebruikt, u Microsoft 365 voor bedrijven instellen om uw Windows 10-apparaten te beschermen, terwijl u toch toegang behoudt tot on-premises bronnen waarvoor lokale verificatie vereist is.</span><span class="sxs-lookup"><span data-stu-id="1b0d7-104">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 for business to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span>
<span data-ttu-id="1b0d7-105">Als u deze beveiliging wilt instellen, u **hybride Azure AD-apparaten**implementeren.</span><span class="sxs-lookup"><span data-stu-id="1b0d7-105">To set up this protection, you can implement **Hybrid Azure AD joined devices**.</span></span> <span data-ttu-id="1b0d7-106">Deze apparaten zijn verbonden met zowel uw on-premises Active Directory als uw Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1b0d7-106">These devices are joined to both your on-premises Active Directory and your Azure Active Directory.</span></span>

<span data-ttu-id="1b0d7-107">In deze video worden de stappen beschreven voor het instellen van dit scenario voor het meest voorkomende scenario, dat ook wordt beschreven in de volgende stappen.</span><span class="sxs-lookup"><span data-stu-id="1b0d7-107">This video describes the steps for how to set this up for the most common scenario, which is also detailed in the steps that follow.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="1-prepare-for-directory-synchronization"></a><span data-ttu-id="1b0d7-108">1. Voorbereiden op adreslijstsynchronisatie</span><span class="sxs-lookup"><span data-stu-id="1b0d7-108">1. Prepare for Directory Synchronization</span></span> 

<span data-ttu-id="1b0d7-109">Voordat u uw gebruikers en computers synchroniseert vanuit het lokale Active Directory-domein, controleert [u Voorbereiden op adreslijstsynchronisatie naar Office 365](https://docs.microsoft.com/office365/enterprise/prepare-for-directory-synchronization).</span><span class="sxs-lookup"><span data-stu-id="1b0d7-109">Before you synchronize your users and computers from the local Active Directory Domain, review [Prepare for directory synchronization to Office 365](https://docs.microsoft.com/office365/enterprise/prepare-for-directory-synchronization).</span></span> <span data-ttu-id="1b0d7-110">In het bijzonder:</span><span class="sxs-lookup"><span data-stu-id="1b0d7-110">In particular:</span></span>

   - <span data-ttu-id="1b0d7-111">Zorg ervoor dat er geen duplicaten in uw map bestaan voor de volgende kenmerken: **e-mail,** **proxyAdressen**en **userPrincipalName**.</span><span class="sxs-lookup"><span data-stu-id="1b0d7-111">Make sure that no duplicates exist in your directory for the following attributes: **mail**, **proxyAddresses**, and **userPrincipalName**.</span></span> <span data-ttu-id="1b0d7-112">Deze waarden moeten uniek zijn en eventuele duplicaten moeten worden verwijderd.</span><span class="sxs-lookup"><span data-stu-id="1b0d7-112">These values must be unique and any duplicates must be removed.</span></span>
   
   - <span data-ttu-id="1b0d7-113">We raden u aan het kenmerk **userPrincipalName** (UPN) voor elk lokaal gebruikersaccount te configureren op het primaire e-mailadres dat overeenkomt met de gelicentieerde Microsoft 365-gebruiker.</span><span class="sxs-lookup"><span data-stu-id="1b0d7-113">We recommend that you configure the **userPrincipalName** (UPN) attribute for each local user account to match the primary email address that corresponds to the licensed Microsoft 365 user.</span></span> <span data-ttu-id="1b0d7-114">Bijvoorbeeld: *mary.shelley@contoso.com* in plaats van *mary@contoso.local*</span><span class="sxs-lookup"><span data-stu-id="1b0d7-114">For example: *mary.shelley@contoso.com* rather than *mary@contoso.local*</span></span>
   
   - <span data-ttu-id="1b0d7-115">Als het Active Directory-domein eindigt in een niet-routable achtervoegsel zoals *.local* of *.lan,* in plaats van een internetroutable achtervoegsel zoals *.com* of *.org,* past u het UPN-achtervoegsel van de lokale gebruikersaccounts eerst aan zoals beschreven in [Een niet-routeerbaar domein voorbereiden voor adreslijstsynchronisatie](https://docs.microsoft.com/office365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization).</span><span class="sxs-lookup"><span data-stu-id="1b0d7-115">If the Active Directory domain ends in a non-routable suffix like *.local* or *.lan*, instead of an internet routable suffix such as *.com* or *.org*, adjust the UPN suffix of the local user accounts first as described in [Prepare a non-routable domain for directory synchronization](https://docs.microsoft.com/office365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization).</span></span> 

## <a name="2-install-and-configure-azure-ad-connect"></a><span data-ttu-id="1b0d7-116">2. Azure AD Connect installeren en configureren</span><span class="sxs-lookup"><span data-stu-id="1b0d7-116">2. Install and configure Azure AD Connect</span></span>

<span data-ttu-id="1b0d7-117">Als u uw gebruikers, groepen en contactpersonen vanuit de lokale Active Directory wilt synchroniseren met Azure Active Directory, installeert u Azure Active Directory Connect en stelt u adreslijstsynchronisatie in.</span><span class="sxs-lookup"><span data-stu-id="1b0d7-117">To synchronize your users, groups, and contacts from the local Active Directory into Azure Active Directory, install Azure Active Directory Connect and set up directory synchronization.</span></span> <span data-ttu-id="1b0d7-118">Zie [Adreslijstsynchronisatie instellen voor Office 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="1b0d7-118">See [Set up directory synchronization for Office 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) to learn more.</span></span>

> [!NOTE]
> <span data-ttu-id="1b0d7-119">De stappen zijn precies hetzelfde voor Microsoft 365 voor bedrijven.</span><span class="sxs-lookup"><span data-stu-id="1b0d7-119">The steps are exactly the same for Microsoft 365 for business.</span></span> 

<span data-ttu-id="1b0d7-120">Terwijl u uw opties voor Azure AD Connect configureert, raden we u aan **wachtwoordsynchronisatie,** **naadloze aanmelding**en de functie **voor het terugschrijven** van wachtwoorden in te schakelen, die ook wordt ondersteund in Microsoft 365 voor bedrijven.</span><span class="sxs-lookup"><span data-stu-id="1b0d7-120">As you configure your options for Azure AD Connect, we recommend that you enable **Password Synchronization**, **Seamless Single Sign-On**, and the **password writeback** feature, which is also supported in Microsoft 365 for business.</span></span>

> [!NOTE]
> <span data-ttu-id="1b0d7-121">Er zijn enkele aanvullende stappen voor het terugschrijven van wachtwoorden buiten het selectievakje in Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="1b0d7-121">There are some additional steps for password writeback beyond the check box in Azure AD Connect.</span></span> <span data-ttu-id="1b0d7-122">Zie [How-to: wachtwoordterugschrijven configureren](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="1b0d7-122">For more information, see [How-to: configure password writeback](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback).</span></span> 

## <a name="3-configure-hybrid-azure-ad-join"></a><span data-ttu-id="1b0d7-123">3. Hybride Azure AD configureren Join</span><span class="sxs-lookup"><span data-stu-id="1b0d7-123">3. Configure Hybrid Azure AD Join</span></span>

<span data-ttu-id="1b0d7-124">Voordat u Windows 10-apparaten hybride Azure AD inschakelt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:</span><span class="sxs-lookup"><span data-stu-id="1b0d7-124">Before you enable Windows 10 devices to be Hybrid Azure AD joined, make sure that you meet the following prerequisites:</span></span>

   - <span data-ttu-id="1b0d7-125">U voert de nieuwste versie van Azure AD Connect uit.</span><span class="sxs-lookup"><span data-stu-id="1b0d7-125">You're running the latest version of Azure AD Connect.</span></span>

   - <span data-ttu-id="1b0d7-126">Azure AD Connect heeft alle computerobjecten gesynchroniseerd van de apparaten waaraan hybride Azure AD wilt zijn.</span><span class="sxs-lookup"><span data-stu-id="1b0d7-126">Azure AD connect has synchronized all the computer objects of the devices you want to be hybrid Azure AD joined.</span></span> <span data-ttu-id="1b0d7-127">Als de computerobjecten deel uitmaken van specifieke organisatie-eenheden (OU), controleert u of deze GEGEVENS ook zijn ingesteld voor synchronisatie in Azure AD-verbinding.</span><span class="sxs-lookup"><span data-stu-id="1b0d7-127">If the computer objects belong to specific organizational units (OU), then make sure these OUs are set for synchronization in Azure AD connect as well.</span></span>

<span data-ttu-id="1b0d7-128">Als u bestaande met een domein verbonden Windows 10-apparaten wilt registreren als Hybride Azure AD is toegetreden, voert u de stappen uit in de [zelfstudie: Hybride Azure Active Directory join configureren voor beheerde domeinen](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join).</span><span class="sxs-lookup"><span data-stu-id="1b0d7-128">To register existing domain-joined Windows 10 devices as Hybrid Azure AD joined, follow the steps in the [Tutorial: Configure hybrid Azure Active Directory join for managed domains](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join).</span></span> <span data-ttu-id="1b0d7-129">Met deze hybride kunnen uw bestaande on-premises Active Directory lid worden van Windows 10-computers en maken ze cloudklaar.</span><span class="sxs-lookup"><span data-stu-id="1b0d7-129">This hybrid-enables your existing on-premises Active Directory joined Windows 10 computers and make them cloud ready.</span></span>
    
## <a name="4-enable-automatic-enrollment-for-windows-10"></a><span data-ttu-id="1b0d7-130">4. Automatische inschrijving inschakelen voor Windows 10</span><span class="sxs-lookup"><span data-stu-id="1b0d7-130">4. Enable automatic enrollment for Windows 10</span></span>

 <span data-ttu-id="1b0d7-131">Zie [Een Windows 10-apparaat automatisch inschrijven voor](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy)het beheer van mobiele apparaten in Intune.</span><span class="sxs-lookup"><span data-stu-id="1b0d7-131">To automatically enroll Windows 10 devices for mobile device management in Intune, see [Enroll a Windows 10 device automatically using Group Policy](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy).</span></span> <span data-ttu-id="1b0d7-132">U het groepsbeleid instellen op lokaal computerniveau of voor bulkbewerkingen, u de console groepsbeleidsbeheer en ADMX-sjablonen gebruiken om deze groepsbeleidsinstelling op uw domeincontroller te maken.</span><span class="sxs-lookup"><span data-stu-id="1b0d7-132">You can set the Group Policy at a local computer level, or for bulk operations, you can use the Group Policy Management Console and ADMX templates to create this Group Policy setting on your Domain Controller.</span></span>

## <a name="5-configure-seamless-single-sign-on"></a><span data-ttu-id="1b0d7-133">5. Naadloze aanmelding configureren</span><span class="sxs-lookup"><span data-stu-id="1b0d7-133">5. Configure Seamless Single Sign-On</span></span>

  <span data-ttu-id="1b0d7-134">Naadloze SSO ondertekent gebruikers automatisch in hun Microsoft 365-cloudbronnen wanneer ze bedrijfscomputers gebruiken.</span><span class="sxs-lookup"><span data-stu-id="1b0d7-134">Seamless SSO automatically signs users into their Microsoft 365 cloud resources when they use corporate computers.</span></span> <span data-ttu-id="1b0d7-135">Implementeer eenvoudig een van de twee groepsbeleidsopties die zijn beschreven in [Azure Active Directory Seamless Single Sign-On: Snel starten](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sso-quick-start#step-2-enable-the-feature).</span><span class="sxs-lookup"><span data-stu-id="1b0d7-135">Simply deploy one of the two Group Policy options described in [Azure Active Directory Seamless Single Sign-On: Quick start](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sso-quick-start#step-2-enable-the-feature).</span></span> <span data-ttu-id="1b0d7-136">Met de optie **Groepsbeleid** kunnen gebruikers hun instellingen niet wijzigen, terwijl de optie **Groepsbeleidsvoorkeur** de waarden instelt, maar ze ook door de gebruiker kan worden geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="1b0d7-136">The **Group Policy** option doesn't allow users to change their settings, while the **Group Policy Preference** option sets the values but also leaves them user-configurable.</span></span>

## <a name="6-set-up-windows-hello-for-business"></a><span data-ttu-id="1b0d7-137">6. Windows Hello for Business instellen</span><span class="sxs-lookup"><span data-stu-id="1b0d7-137">6. Set up Windows Hello for Business</span></span>

 <span data-ttu-id="1b0d7-138">Windows Hello for Business vervangt wachtwoorden door sterke tweestapsverificatie (2FA) voor het aanmelden bij een lokale computer.</span><span class="sxs-lookup"><span data-stu-id="1b0d7-138">Windows Hello for Business replaces passwords with strong two-factor authentication (2FA) for signing into a local computer.</span></span> <span data-ttu-id="1b0d7-139">De ene factor is een asymmetrisch sleutelpaar, en de andere is een pincode of een ander lokaal gebaar, zoals vingerafdruk of gezichtsherkenning als uw apparaat dit ondersteunt.</span><span class="sxs-lookup"><span data-stu-id="1b0d7-139">One factor is an asymmetric key pair, and the other is a PIN or other local gesture such as fingerprint or facial recognition if your device supports it.</span></span> <span data-ttu-id="1b0d7-140">We raden u aan om wachtwoorden waar mogelijk te vervangen door 2FA en Windows Hello for Business.</span><span class="sxs-lookup"><span data-stu-id="1b0d7-140">We recommend that you replace passwords with 2FA and Windows Hello for Business where possible.</span></span>

<span data-ttu-id="1b0d7-141">Als u Hybride Windows Hello voor Bedrijven wilt configureren, controleert u de [vertrouwensrelatie met de hybride sleutel windows hello voor bedrijven.](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-trust-prereqs)</span><span class="sxs-lookup"><span data-stu-id="1b0d7-141">To configure Hybrid Windows Hello for Business, review the [Hybrid Key trust Windows Hello for Business Prerequisites](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-trust-prereqs).</span></span> <span data-ttu-id="1b0d7-142">Volg vervolgens de instructies in [De vertrouwensinstellingen voor hybride Windows Hello voor Bedrijven configureren.](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-whfb-settings)</span><span class="sxs-lookup"><span data-stu-id="1b0d7-142">Then follow the instructions in [Configure Hybrid Windows Hello for Business key trust settings](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-whfb-settings).</span></span> 
