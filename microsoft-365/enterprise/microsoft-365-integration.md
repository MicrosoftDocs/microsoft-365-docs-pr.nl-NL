---
title: Microsoft 365-integratie met on-premises omgevingen
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
description: In dit artikel leest u hoe u Microsoft 365 kunt integreren met uw bestaande adreslijstservices en on-premises omgevingen.
ms.openlocfilehash: 9c5e287ed4a440d1f62081a4c94e39f0f162b4dc
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384882"
---
# <a name="microsoft-365-integration-with-on-premises-environments"></a><span data-ttu-id="07a83-103">Microsoft 365-integratie met on-premises omgevingen</span><span class="sxs-lookup"><span data-stu-id="07a83-103">Microsoft 365 integration with on-premises environments</span></span>

<span data-ttu-id="07a83-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="07a83-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="07a83-105">U kunt Microsoft 365 integreren met uw bestaande on-premises Active Directory Domain Services (AD DS) en met on-premises installaties van Exchange Server, Skype voor bedrijven server 2015 of SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="07a83-105">You can integrate Microsoft 365 with your existing on-premises Active Directory Domain Services (AD DS) and with on-premises installations of Exchange Server, Skype for Business Server 2015, or SharePoint Server.</span></span>
  
 - <span data-ttu-id="07a83-106">Wanneer u ACTIVEert, kunt u gebruikersaccounts voor beide omgevingen synchroniseren en beheren.</span><span class="sxs-lookup"><span data-stu-id="07a83-106">When you integrate AD DS, you can synchronize and manage user accounts for both environments.</span></span> <span data-ttu-id="07a83-107">U kunt ook wachtwoord hash-synchronisatie (PHS) of eenmalige aanmelding (SSO) toevoegen, zodat gebruikers zich kunnen aanmelden bij beide omgevingen met hun on-premises referenties.</span><span class="sxs-lookup"><span data-stu-id="07a83-107">You can also add password hash synchronization (PHS) or single sign-on (SSO) so users can log on to both environments with their on-premises credentials.</span></span>
 - <span data-ttu-id="07a83-108">Als u integratie met lokale server producten uitvoert, maakt u een hybride omgeving.</span><span class="sxs-lookup"><span data-stu-id="07a83-108">When you integrate with on-premises server products, you create a hybrid environment.</span></span> <span data-ttu-id="07a83-109">Een hybride omgeving kan u helpen bij het migreren van gebruikers of gegevens naar Microsoft 365, of u kunt in de Cloud bepaalde gebruikers of bepaalde informatie on-premises blijven hebben.</span><span class="sxs-lookup"><span data-stu-id="07a83-109">A hybrid environment can help as you migrate users or information to Microsoft 365, or you can continue to have some users or some information on-premises and some in the cloud.</span></span> <span data-ttu-id="07a83-110">Zie voor meer informatie over hybride omgevingen [hybride Cloud](../solutions/cloud-architecture-models.md#hybrid).</span><span class="sxs-lookup"><span data-stu-id="07a83-110">For more information about hybrid environments, see [hybrid cloud](../solutions/cloud-architecture-models.md#hybrid).</span></span>

<span data-ttu-id="07a83-111">U kunt ook de Azure Active Directory (Azure AD) adviseurs voor aangepaste instellingsrichtlijnen gebruiken in het Microsoft 365-Beheercentrum (u moet zijn aangemeld bij Microsoft 365):</span><span class="sxs-lookup"><span data-stu-id="07a83-111">You can also use the Azure Active Directory (Azure AD) advisors for customized setup guidance in the Microsoft 365 admin center (you must be signed in to Microsoft 365):</span></span>

- [<span data-ttu-id="07a83-112">Installatiehandleiding voor Azure AD</span><span class="sxs-lookup"><span data-stu-id="07a83-112">Azure AD setup guide</span></span>](https://aka.ms/aadpguidance)
- [<span data-ttu-id="07a83-113">Gebruikers synchroniseren vanuit de adreslijst van uw organisatie</span><span class="sxs-lookup"><span data-stu-id="07a83-113">Sync users from your org's directory</span></span>](https://aka.ms/aadconnectpwsync)
- [<span data-ttu-id="07a83-114">Active Directory Federation Services (AD FS) Deployment adviseur</span><span class="sxs-lookup"><span data-stu-id="07a83-114">Active Directory Federation Services (AD FS) deployment advisor</span></span>](https://aka.ms/adfsguidance)
   
## <a name="before-you-begin"></a><span data-ttu-id="07a83-115">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="07a83-115">Before you begin</span></span>

<span data-ttu-id="07a83-116">Voordat u Microsoft 365 en een lokale omgeving integreert, moet u ook [netwerk planning en prestaties optimaliseren](network-planning-and-performance.md).</span><span class="sxs-lookup"><span data-stu-id="07a83-116">Before you integrate Microsoft 365 and an on-premises environment, you also need to do [network planning and performance tuning](network-planning-and-performance.md).</span></span> <span data-ttu-id="07a83-117">U kunt ook inzicht krijgen in de beschikbare [identiteits modellen](about-microsoft-365-identity.md).</span><span class="sxs-lookup"><span data-stu-id="07a83-117">You will also want to understand the available [identity models](about-microsoft-365-identity.md).</span></span> 

<span data-ttu-id="07a83-118">Zie [Microsoft 365-accounts beheren](manage-microsoft-365-accounts.md) voor een lijst met hulpmiddelen die u kunt gebruiken voor het beheren van gebruikersaccounts van microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="07a83-118">See [manage Microsoft 365 accounts](manage-microsoft-365-accounts.md) for a list of tools you can use to manage Microsoft 365 user accounts.</span></span> 
  
## <a name="integrate-microsoft-365-with-ad-ds"></a><span data-ttu-id="07a83-119">Microsoft 365 integreren met Active Directory</span><span class="sxs-lookup"><span data-stu-id="07a83-119">Integrate Microsoft 365 with AD DS</span></span>

<span data-ttu-id="07a83-120">Als u beschikt over bestaande gebruikersaccounts in AD DS, wilt u niet al deze accounts opnieuw maken in Microsoft 365 en risico, waarbij de verschillen of fouten tussen de omgevingen worden geïntroduceerd.</span><span class="sxs-lookup"><span data-stu-id="07a83-120">If you have existing user accounts in AD DS, you don't want to re-create all of those accounts in Microsoft 365 and risk introducing differences or errors between the environments.</span></span> <span data-ttu-id="07a83-121">Met adreslijstsynchronisatie kunt u de accounts in uw on-premises en online omgevingen spiegelen.</span><span class="sxs-lookup"><span data-stu-id="07a83-121">Directory synchronization helps you mirror those accounts between your on-premises and online environments.</span></span> <span data-ttu-id="07a83-122">Met adreslijstsynchronisatie hoeven gebruikers geen nieuwe informatie voor elke omgeving te onthouden en hoeft u niet twee keer accounts te maken of bij te werken.</span><span class="sxs-lookup"><span data-stu-id="07a83-122">With directory synchronization, your users don't have to remember new information for each environment, and you don't have to create or update accounts twice.</span></span> <span data-ttu-id="07a83-123">U moet [uw on-premises adreslijst voorbereiden](prepare-for-directory-synchronization.md) op adreslijstsynchronisatie.</span><span class="sxs-lookup"><span data-stu-id="07a83-123">You will need to [prepare your on-premises directory](prepare-for-directory-synchronization.md) for directory synchronization.</span></span>
  
![Adreslijstsynchronisatie gebruiken om on-premises en online gegevens van gebruikersaccounts gesynchroniseerd te houden](../media/microsoft-365-integration/directory-synchronization.png)
  
<span data-ttu-id="07a83-125">Als u wilt dat gebruikers zich kunnen aanmelden bij Microsoft 365 met hun on-premises referenties, kunt u ook eenmalige aanmelding configureren.</span><span class="sxs-lookup"><span data-stu-id="07a83-125">If you want users to be able to log on to Microsoft 365 with their on-premises credentials, you can also configure SSO.</span></span> <span data-ttu-id="07a83-126">Met eenmalige aanmelding is Microsoft 365 geconfigureerd voor het vertrouwen van de on-premises omgeving voor gebruikersauthenticatie.</span><span class="sxs-lookup"><span data-stu-id="07a83-126">With SSO, Microsoft 365 is configured to trust the on-premises environment for user authentication.</span></span>
  
![Met eenmalige aanmelding is hetzelfde account beschikbaar in de on-premises omgeving en de online omgeving](../media/microsoft-365-integration/single-sign-on.png)

### <a name="directory-synchronization-with-or-without-password-hash-synchronization-or-pass-through-authentication-pta"></a><span data-ttu-id="07a83-128">Adreslijstsynchronisatie met of zonder wachtwoord-hash-synchronisatie of Pass Through-verificatie (PTA)</span><span class="sxs-lookup"><span data-stu-id="07a83-128">Directory synchronization with or without password hash synchronization or pass-through authentication (PTA)</span></span>

<span data-ttu-id="07a83-129">Een gebruiker meldt zich aan bij hun on-premises omgeving met hun gebruikersaccount (DOMEIN\gebruikersnaam).</span><span class="sxs-lookup"><span data-stu-id="07a83-129">A user logs on to their on-premises environment with their user account (domain\username).</span></span> <span data-ttu-id="07a83-130">Wanneer ze naar Microsoft 365 gaan, moeten ze zich opnieuw aanmelden met hun werk-of schoolaccount (user@domain.com).</span><span class="sxs-lookup"><span data-stu-id="07a83-130">When they go to Microsoft 365, they must log on again with their work or school account (user@domain.com).</span></span> <span data-ttu-id="07a83-131">De gebruikersnaam is hetzelfde in beide omgevingen.</span><span class="sxs-lookup"><span data-stu-id="07a83-131">The user name is the same in both environments.</span></span> <span data-ttu-id="07a83-132">Wanneer u PHS of PTA toevoegt, heeft de gebruiker hetzelfde wachtwoord voor beide omgevingen, maar deze referenties moeten opnieuw worden opgegeven bij het aanmelden bij Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="07a83-132">When you add PHS or PTA, the user has the same password for both environments, but will have to provide those credentials again when logging on to Microsoft 365.</span></span> <span data-ttu-id="07a83-133">Adreslijstsynchronisatie met PHS is de meestgebruikte adreslijstsynchronisatie.</span><span class="sxs-lookup"><span data-stu-id="07a83-133">Directory synchronization with PHS is the most commonly used directory synchronization .</span></span>

<span data-ttu-id="07a83-134">Als u adreslijstsynchronisatie wilt instellen, gebruikt u Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="07a83-134">To set up directory synchronization, use Azure AD Connect.</span></span> <span data-ttu-id="07a83-135">Zie [adreslijstsynchronisatie instellen voor Microsoft 365](set-up-directory-synchronization.md) en [Azure AD Connect met expres instellingen](https://go.microsoft.com/fwlink/p/?LinkId=698537)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="07a83-135">For instructions, see [Set up directory synchronization for Microsoft 365](set-up-directory-synchronization.md) and [Azure AD Connect with express settings](https://go.microsoft.com/fwlink/p/?LinkId=698537).</span></span>

<span data-ttu-id="07a83-136">Meer informatie over [het voorbereiden van adreslijstsynchronisatie met Microsoft 365](prepare-for-directory-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="07a83-136">Learn more about [preparing for directory synchronization to Microsoft 365](prepare-for-directory-synchronization.md).</span></span>

### <a name="directory-synchronization-with-sso"></a><span data-ttu-id="07a83-137">Adreslijstsynchronisatie met SSO</span><span class="sxs-lookup"><span data-stu-id="07a83-137">Directory synchronization with SSO</span></span>

<span data-ttu-id="07a83-138">Een gebruiker meldt zich aan bij hun on-premises omgeving met hun gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="07a83-138">A user logs on to their on-premises environment with their user account.</span></span> <span data-ttu-id="07a83-139">Wanneer de persoon naar Microsoft 365 gaat, meldt u zich automatisch aan of worden ze aangemeld met de referenties die ze voor hun on-premises omgeving gebruiken.</span><span class="sxs-lookup"><span data-stu-id="07a83-139">When they go to Microsoft 365, they are either logged on automatically, or they log on using the same credentials they use for their on-premises environment (domain\username).</span></span>

<span data-ttu-id="07a83-140">Voor het instellen van eenmalige aanmelding gebruikt u ook Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="07a83-140">To set up SSO you also use Azure AD Connect.</span></span> <span data-ttu-id="07a83-141">Voor instructies raadpleegt u [aangepaste installatie van Azure AD Connect](https://go.microsoft.com/fwlink/p/?LinkID=698430).</span><span class="sxs-lookup"><span data-stu-id="07a83-141">For instructions, see [Custom installation of Azure AD Connect](https://go.microsoft.com/fwlink/p/?LinkID=698430).</span></span>

<span data-ttu-id="07a83-142">Zie voor meer informatie [eenmalige aanmelding](https://go.microsoft.com/fwlink/p/?LinkId=698604).</span><span class="sxs-lookup"><span data-stu-id="07a83-142">For more information, see [single sign-on](https://go.microsoft.com/fwlink/p/?LinkId=698604).</span></span>

## <a name="azure-ad-connect"></a><span data-ttu-id="07a83-143">Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="07a83-143">Azure AD Connect</span></span>

<span data-ttu-id="07a83-144">Azure AD Connect vervangt oudere versies van hulpmiddelen voor identiteits integratie, zoals DirSync en Azure AD-synchronisatie. Als u wilt bijwerken van Azure Active Directory-synchronisatie met Azure AD Connect, raadpleegt u [de upgrade-instructies](https://go.microsoft.com/fwlink/p/?LinkId=733240).</span><span class="sxs-lookup"><span data-stu-id="07a83-144">Azure AD Connect replaces older versions of identity integration tools such as DirSync and Azure AD Sync. If you want to update from Azure Active Directory Sync to Azure AD Connect, see [the upgrade instructions](https://go.microsoft.com/fwlink/p/?LinkId=733240).</span></span> 

## <a name="see-also"></a><span data-ttu-id="07a83-145">Zie ook</span><span class="sxs-lookup"><span data-stu-id="07a83-145">See also</span></span>

[<span data-ttu-id="07a83-146">Overzicht van Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="07a83-146">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)
