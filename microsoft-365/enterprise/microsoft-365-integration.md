---
title: Microsoft 365 integratie met on-premises omgevingen
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- Ent_O365
search.appverid:
- MET150
- LYN150
- SPS150
- MOE150
- MED150
ms.assetid: 263faf8d-aa21-428b-aed3-2021837a4b65
description: In dit artikel leert u hoe u uw Microsoft 365 met uw bestaande adreslijstservices en on-premises omgevingen kunt integreren.
ms.openlocfilehash: c0453b7685254ccbbb301a17749fe48549fae78d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923964"
---
# <a name="microsoft-365-integration-with-on-premises-environments"></a><span data-ttu-id="7fc5b-103">Microsoft 365 integratie met on-premises omgevingen</span><span class="sxs-lookup"><span data-stu-id="7fc5b-103">Microsoft 365 integration with on-premises environments</span></span>

<span data-ttu-id="7fc5b-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="7fc5b-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="7fc5b-105">U kunt Microsoft 365 integreren met uw bestaande on-premises Active Directory Domain Services (AD DS) en met on-premises installaties van Exchange Server, Skype voor Bedrijven Server 2015 of SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="7fc5b-105">You can integrate Microsoft 365 with your existing on-premises Active Directory Domain Services (AD DS) and with on-premises installations of Exchange Server, Skype for Business Server 2015, or SharePoint Server.</span></span>
  
 - <span data-ttu-id="7fc5b-106">Wanneer u AD DS integreert, kunt u gebruikersaccounts voor beide omgevingen synchroniseren en beheren.</span><span class="sxs-lookup"><span data-stu-id="7fc5b-106">When you integrate AD DS, you can synchronize and manage user accounts for both environments.</span></span> <span data-ttu-id="7fc5b-107">U kunt ook wachtwoordhashsynchronisatie (PHS) of eenmalige aanmelding (SSO) toevoegen, zodat gebruikers zich kunnen aanmelden bij beide omgevingen met hun on-premises referenties.</span><span class="sxs-lookup"><span data-stu-id="7fc5b-107">You can also add password hash synchronization (PHS) or single sign-on (SSO) so users can log on to both environments with their on-premises credentials.</span></span>
 - <span data-ttu-id="7fc5b-108">Wanneer u integreert met on-premises serverproducten, maakt u een hybride omgeving.</span><span class="sxs-lookup"><span data-stu-id="7fc5b-108">When you integrate with on-premises server products, you create a hybrid environment.</span></span> <span data-ttu-id="7fc5b-109">Een hybride omgeving kan u helpen wanneer u gebruikers of informatie migreert naar Microsoft 365, of u kunt bepaalde gebruikers of bepaalde informatie on-premises en sommige informatie in de cloud blijven gebruiken.</span><span class="sxs-lookup"><span data-stu-id="7fc5b-109">A hybrid environment can help as you migrate users or information to Microsoft 365, or you can continue to have some users or some information on-premises and some in the cloud.</span></span> <span data-ttu-id="7fc5b-110">Zie hybride cloud voor meer informatie over [hybride omgevingen.](../solutions/cloud-architecture-models.md#hybrid)</span><span class="sxs-lookup"><span data-stu-id="7fc5b-110">For more information about hybrid environments, see [hybrid cloud](../solutions/cloud-architecture-models.md#hybrid).</span></span>

<span data-ttu-id="7fc5b-111">U kunt ook de adviseurs Azure Active Directory (Azure AD) gebruiken voor aangepaste installatie-richtlijnen in het Microsoft 365-beheercentrum (u moet zijn aangemeld bij Microsoft 365):</span><span class="sxs-lookup"><span data-stu-id="7fc5b-111">You can also use the Azure Active Directory (Azure AD) advisors for customized setup guidance in the Microsoft 365 admin center (you must be signed in to Microsoft 365):</span></span>

- [<span data-ttu-id="7fc5b-112">Installatiehandleiding voor Azure AD</span><span class="sxs-lookup"><span data-stu-id="7fc5b-112">Azure AD setup guide</span></span>](https://aka.ms/aadpguidance)
- [<span data-ttu-id="7fc5b-113">Gebruikers synchroniseren vanuit de adreslijst van uw organisatie</span><span class="sxs-lookup"><span data-stu-id="7fc5b-113">Sync users from your org's directory</span></span>](https://aka.ms/aadconnectpwsync)
- [<span data-ttu-id="7fc5b-114">Ad FS-implementatieadviseur (Active Directory Federation Services)</span><span class="sxs-lookup"><span data-stu-id="7fc5b-114">Active Directory Federation Services (AD FS) deployment advisor</span></span>](https://aka.ms/adfsguidance)
   
## <a name="before-you-begin"></a><span data-ttu-id="7fc5b-115">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="7fc5b-115">Before you begin</span></span>

<span data-ttu-id="7fc5b-116">Voordat u een Microsoft 365 en een on-premises omgeving integreert, moet u ook netwerkplanning en [prestatieafstemming doen.](network-planning-and-performance.md)</span><span class="sxs-lookup"><span data-stu-id="7fc5b-116">Before you integrate Microsoft 365 and an on-premises environment, you also need to do [network planning and performance tuning](network-planning-and-performance.md).</span></span> <span data-ttu-id="7fc5b-117">U wilt ook de beschikbare [identiteitsmodellen begrijpen.](about-microsoft-365-identity.md)</span><span class="sxs-lookup"><span data-stu-id="7fc5b-117">You will also want to understand the available [identity models](about-microsoft-365-identity.md).</span></span> 

<span data-ttu-id="7fc5b-118">Zie [Beheer Microsoft 365 accounts voor](manage-microsoft-365-accounts.md) een lijst met hulpprogramma's die u kunt gebruiken om uw gebruikersaccounts Microsoft 365 beheren.</span><span class="sxs-lookup"><span data-stu-id="7fc5b-118">See [manage Microsoft 365 accounts](manage-microsoft-365-accounts.md) for a list of tools you can use to manage Microsoft 365 user accounts.</span></span> 
  
## <a name="integrate-microsoft-365-with-ad-ds"></a><span data-ttu-id="7fc5b-119">Integratie Microsoft 365 met AD DS</span><span class="sxs-lookup"><span data-stu-id="7fc5b-119">Integrate Microsoft 365 with AD DS</span></span>

<span data-ttu-id="7fc5b-120">Als u bestaande gebruikersaccounts hebt in AD DS, wilt u niet al deze accounts opnieuw maken in Microsoft 365 en kunt u verschillen of fouten tussen de omgevingen introduceren.</span><span class="sxs-lookup"><span data-stu-id="7fc5b-120">If you have existing user accounts in AD DS, you don't want to re-create all of those accounts in Microsoft 365 and risk introducing differences or errors between the environments.</span></span> <span data-ttu-id="7fc5b-121">Met adreslijstsynchronisatie kunt u deze accounts spiegelen tussen uw on-premises en onlineomgevingen.</span><span class="sxs-lookup"><span data-stu-id="7fc5b-121">Directory synchronization helps you mirror those accounts between your on-premises and online environments.</span></span> <span data-ttu-id="7fc5b-122">Met adreslijstsynchronisatie hoeven uw gebruikers geen nieuwe informatie voor elke omgeving te onthouden en hoeft u geen accounts tweemaal te maken of bij te werken.</span><span class="sxs-lookup"><span data-stu-id="7fc5b-122">With directory synchronization, your users don't have to remember new information for each environment, and you don't have to create or update accounts twice.</span></span> <span data-ttu-id="7fc5b-123">U moet uw [on-premises adreslijst voorbereiden](prepare-for-directory-synchronization.md) op adreslijstsynchronisatie.</span><span class="sxs-lookup"><span data-stu-id="7fc5b-123">You will need to [prepare your on-premises directory](prepare-for-directory-synchronization.md) for directory synchronization.</span></span>
  
![Adreslijstsynchronisatie gebruiken om on-premises en online gebruikersaccountgegevens gesynchroniseerd te houden](../media/microsoft-365-integration/directory-synchronization.png)
  
<span data-ttu-id="7fc5b-125">Als u wilt dat gebruikers zich kunnen aanmelden bij Microsoft 365 on-premises referenties, kunt u ook eenmalige aanmelding configureren.</span><span class="sxs-lookup"><span data-stu-id="7fc5b-125">If you want users to be able to log on to Microsoft 365 with their on-premises credentials, you can also configure SSO.</span></span> <span data-ttu-id="7fc5b-126">Met SSO is Microsoft 365 geconfigureerd om de on-premises omgeving voor gebruikersverificatie te vertrouwen.</span><span class="sxs-lookup"><span data-stu-id="7fc5b-126">With SSO, Microsoft 365 is configured to trust the on-premises environment for user authentication.</span></span>
  
![Met één aanmelding is hetzelfde account beschikbaar in zowel de on-premises als onlineomgevingen](../media/microsoft-365-integration/single-sign-on.png)

### <a name="directory-synchronization-with-or-without-password-hash-synchronization-or-pass-through-authentication-pta"></a><span data-ttu-id="7fc5b-128">Adreslijstsynchronisatie met of zonder wachtwoordhashsynchronisatie of pass-throughverificatie (PTA)</span><span class="sxs-lookup"><span data-stu-id="7fc5b-128">Directory synchronization with or without password hash synchronization or pass-through authentication (PTA)</span></span>

<span data-ttu-id="7fc5b-129">Een gebruiker meldt zich aan bij de on-premises omgeving met zijn of haar gebruikersaccount (domein\gebruikersnaam).</span><span class="sxs-lookup"><span data-stu-id="7fc5b-129">A user logs on to their on-premises environment with their user account (domain\username).</span></span> <span data-ttu-id="7fc5b-130">Wanneer ze naar Microsoft 365 gaan, moeten ze zich opnieuw aanmelden met hun werk- of schoolaccount (user@domain.com).</span><span class="sxs-lookup"><span data-stu-id="7fc5b-130">When they go to Microsoft 365, they must log on again with their work or school account (user@domain.com).</span></span> <span data-ttu-id="7fc5b-131">De gebruikersnaam is in beide omgevingen hetzelfde.</span><span class="sxs-lookup"><span data-stu-id="7fc5b-131">The user name is the same in both environments.</span></span> <span data-ttu-id="7fc5b-132">Wanneer u PHS of PTA toevoegt, heeft de gebruiker hetzelfde wachtwoord voor beide omgevingen, maar moet deze referenties opnieuw opgeven wanneer ze zich aanmelden bij Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7fc5b-132">When you add PHS or PTA, the user has the same password for both environments, but will have to provide those credentials again when logging on to Microsoft 365.</span></span> <span data-ttu-id="7fc5b-133">Adreslijstsynchronisatie met PHS is de meestgebruikte adreslijstsynchronisatie.</span><span class="sxs-lookup"><span data-stu-id="7fc5b-133">Directory synchronization with PHS is the most commonly used directory synchronization .</span></span>

<span data-ttu-id="7fc5b-134">Als u adreslijstsynchronisatie wilt instellen, gebruikt u Azure AD-Verbinding maken.</span><span class="sxs-lookup"><span data-stu-id="7fc5b-134">To set up directory synchronization, use Azure AD Connect.</span></span> <span data-ttu-id="7fc5b-135">Zie Adreslijstsynchronisatie instellen voor Microsoft 365 en [Azure AD-Verbinding maken met express-instellingen voor instructies.](/azure/active-directory/hybrid/how-to-connect-install-express) [](set-up-directory-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="7fc5b-135">For instructions, see [Set up directory synchronization for Microsoft 365](set-up-directory-synchronization.md) and [Azure AD Connect with express settings](/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

<span data-ttu-id="7fc5b-136">Meer informatie over [het voorbereiden van adreslijstsynchronisatie om Microsoft 365.](prepare-for-directory-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="7fc5b-136">Learn more about [preparing for directory synchronization to Microsoft 365](prepare-for-directory-synchronization.md).</span></span>

### <a name="directory-synchronization-with-sso"></a><span data-ttu-id="7fc5b-137">Adreslijstsynchronisatie met SSO</span><span class="sxs-lookup"><span data-stu-id="7fc5b-137">Directory synchronization with SSO</span></span>

<span data-ttu-id="7fc5b-138">Een gebruiker meldt zich aan bij zijn of haar on-premises omgeving met zijn of haar gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="7fc5b-138">A user logs on to their on-premises environment with their user account.</span></span> <span data-ttu-id="7fc5b-139">Wanneer ze naar Microsoft 365, worden ze automatisch aangemeld of melden ze zich aan met dezelfde referenties die ze gebruiken voor hun on-premises omgeving (domein\gebruikersnaam).</span><span class="sxs-lookup"><span data-stu-id="7fc5b-139">When they go to Microsoft 365, they are either logged on automatically, or they log on using the same credentials they use for their on-premises environment (domain\username).</span></span>

<span data-ttu-id="7fc5b-140">Als u SSO wilt instellen, gebruikt u ook Azure AD-Verbinding maken.</span><span class="sxs-lookup"><span data-stu-id="7fc5b-140">To set up SSO you also use Azure AD Connect.</span></span> <span data-ttu-id="7fc5b-141">Zie Aangepaste installatie [van Azure AD-Verbinding maken.](/azure/active-directory/hybrid/how-to-connect-install-custom)</span><span class="sxs-lookup"><span data-stu-id="7fc5b-141">For instructions, see [Custom installation of Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-custom).</span></span>

<span data-ttu-id="7fc5b-142">Zie een enkele aanmelding voor [meer informatie.](/azure/active-directory/manage-apps/what-is-single-sign-on)</span><span class="sxs-lookup"><span data-stu-id="7fc5b-142">For more information, see [single sign-on](/azure/active-directory/manage-apps/what-is-single-sign-on).</span></span>

## <a name="azure-ad-connect"></a><span data-ttu-id="7fc5b-143">Azure AD Verbinding maken</span><span class="sxs-lookup"><span data-stu-id="7fc5b-143">Azure AD Connect</span></span>

<span data-ttu-id="7fc5b-144">Azure AD Verbinding maken vervangt oudere versies van hulpprogramma's voor identiteitsintegratie, zoals DirSync en Azure AD Sync. Als u wilt bijwerken van Azure Active Directory Synchroniseren met Azure AD-Verbinding maken, bekijkt u [de upgrade-instructies.](/azure/active-directory/hybrid/how-to-dirsync-upgrade-get-started)</span><span class="sxs-lookup"><span data-stu-id="7fc5b-144">Azure AD Connect replaces older versions of identity integration tools such as DirSync and Azure AD Sync. If you want to update from Azure Active Directory Sync to Azure AD Connect, see [the upgrade instructions](/azure/active-directory/hybrid/how-to-dirsync-upgrade-get-started).</span></span> 

## <a name="see-also"></a><span data-ttu-id="7fc5b-145">Zie ook</span><span class="sxs-lookup"><span data-stu-id="7fc5b-145">See also</span></span>

[<span data-ttu-id="7fc5b-146">Microsoft 365 Enterprise overzicht</span><span class="sxs-lookup"><span data-stu-id="7fc5b-146">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)