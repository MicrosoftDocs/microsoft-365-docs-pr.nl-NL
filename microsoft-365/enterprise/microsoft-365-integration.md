---
title: Microsoft 365-integratie met on-premises omgevingen
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 10/08/2019
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
ms.openlocfilehash: 46f0fab6396dd1db82524ea1aeedc6894ce7ab70
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689512"
---
# <a name="microsoft-365-integration-with-on-premises-environments"></a><span data-ttu-id="e9b89-103">Microsoft 365-integratie met on-premises omgevingen</span><span class="sxs-lookup"><span data-stu-id="e9b89-103">Microsoft 365 integration with on-premises environments</span></span>

<span data-ttu-id="e9b89-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="e9b89-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="e9b89-105">U kunt Microsoft 365 integreren met uw bestaande adreslijstservices en met een lokale installatie van Exchange Server, Skype voor bedrijven server 2015 of SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="e9b89-105">You can integrate Microsoft 365 with your existing directory services and with an on-premises installation of Exchange Server, Skype for Business Server 2015, or SharePoint Server.</span></span>
  
 - <span data-ttu-id="e9b89-106">Als u integratie met adreslijstservices, kunt u gebruikersaccounts synchroniseren en beheren voor beide omgevingen.</span><span class="sxs-lookup"><span data-stu-id="e9b89-106">When you integrate with directory services, you can synchronize and manage user accounts for both environments.</span></span> <span data-ttu-id="e9b89-107">U kunt ook hash-synchronisatie voor wachtwoord of eenmalige aanmelding (SSO) toevoegen, zodat gebruikers zich kunnen aanmelden bij beide omgevingen met hun on-premises referenties.</span><span class="sxs-lookup"><span data-stu-id="e9b89-107">You can also add password hash synchronization or single sign-on (SSO) so users can log on to both environments with their on-premises credentials.</span></span>
 - <span data-ttu-id="e9b89-108">Als u integratie met lokale server producten uitvoert, maakt u een hybride omgeving.</span><span class="sxs-lookup"><span data-stu-id="e9b89-108">When you integrate with on-premises server products, you create a hybrid environment.</span></span> <span data-ttu-id="e9b89-109">Een hybride omgeving kan u helpen bij het migreren van gebruikers of gegevens naar Microsoft 365, of u kunt in de Cloud bepaalde gebruikers of bepaalde informatie on-premises blijven hebben.</span><span class="sxs-lookup"><span data-stu-id="e9b89-109">A hybrid environment can help as you migrate users or information to Microsoft 365, or you can continue to have some users or some information on-premises and some in the cloud.</span></span> <span data-ttu-id="e9b89-110">Zie voor meer informatie over hybride omgevingen [hybride Cloud Overview](https://docs.microsoft.com/Office365/Enterprise/hybrid-cloud-overview).</span><span class="sxs-lookup"><span data-stu-id="e9b89-110">For more information about hybrid environments, see [Hybrid cloud overview](https://docs.microsoft.com/Office365/Enterprise/hybrid-cloud-overview).</span></span>

<span data-ttu-id="e9b89-111">U kunt ook de Azure Active Directory (Azure AD) adviseurs gebruiken voor aangepaste instel richtlijnen (u moet zijn aangemeld bij Microsoft 365):</span><span class="sxs-lookup"><span data-stu-id="e9b89-111">You can also use the Azure Active Directory (Azure AD) advisors for customized setup guidance (you must be signed in to Microsoft 365):</span></span>

- [<span data-ttu-id="e9b89-112">Gebruikers synchroniseren vanuit de adreslijst van uw organisatie</span><span class="sxs-lookup"><span data-stu-id="e9b89-112">Sync users from your org's directory</span></span>](https://aka.ms/aadconnectpwsync)
- [<span data-ttu-id="e9b89-113">AD FS-implementatie adviseur</span><span class="sxs-lookup"><span data-stu-id="e9b89-113">AD FS deployment advisor</span></span>](https://aka.ms/adfsguidance)
- [<span data-ttu-id="e9b89-114">Installatiehandleiding voor Azure AD</span><span class="sxs-lookup"><span data-stu-id="e9b89-114">Azure AD setup guide</span></span>](https://aka.ms/aadpguidance)
   
## <a name="before-you-begin"></a><span data-ttu-id="e9b89-115">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="e9b89-115">Before you begin</span></span>

<span data-ttu-id="e9b89-116">Voordat u Microsoft 365 en een lokale omgeving integreert, moet u ook een [netwerk planning en prestaties afstemmen](network-planning-and-performance.md).</span><span class="sxs-lookup"><span data-stu-id="e9b89-116">Before you integrate Microsoft 365 and an on-premises environment, you also need to attend to [network planning and performance tuning](network-planning-and-performance.md).</span></span> <span data-ttu-id="e9b89-117">U kunt ook inzicht krijgen in de beschikbare [identiteits modellen](about-microsoft-365-identity.md).</span><span class="sxs-lookup"><span data-stu-id="e9b89-117">You will also want to understand the available [identity models](about-microsoft-365-identity.md).</span></span> 

<span data-ttu-id="e9b89-118">Zie [waar kunt u Microsoft 365-accounts beheren](manage-microsoft-365-accounts.md) voor een lijst met hulpmiddelen die u kunt gebruiken voor het beheren van gebruikers en accounts van microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e9b89-118">See [where to manage Microsoft 365 accounts](manage-microsoft-365-accounts.md) for a list of tools you can use to manage Microsoft 365 users and accounts.</span></span> 
  
## <a name="integrate-microsoft-365-with-directory-services"></a><span data-ttu-id="e9b89-119">Microsoft 365 integreren met adreslijstservices</span><span class="sxs-lookup"><span data-stu-id="e9b89-119">Integrate Microsoft 365 with directory services</span></span>
<span data-ttu-id="e9b89-120">Als u bestaande gebruikersaccounts hebt in een on-premises adreslijst, kunt u niet al deze accounts opnieuw maken in Microsoft 365 en risico, waarbij de verschillen of fouten tussen de omgevingen worden geïntroduceerd.</span><span class="sxs-lookup"><span data-stu-id="e9b89-120">If you have existing user accounts in an on-premises directory, you don't want to re-create all of those accounts in Microsoft 365 and risk introducing differences or errors between the environments.</span></span> <span data-ttu-id="e9b89-121">Met adreslijstsynchronisatie kunt u de accounts van uw online en on-premises omgevingen spiegelen.</span><span class="sxs-lookup"><span data-stu-id="e9b89-121">Directory synchronization helps you mirror those accounts between your online and on-premises environments.</span></span> <span data-ttu-id="e9b89-122">Met adreslijstsynchronisatie hoeven gebruikers geen nieuwe informatie voor elke omgeving te onthouden en hoeft u niet twee keer accounts te maken of bij te werken.</span><span class="sxs-lookup"><span data-stu-id="e9b89-122">With directory synchronization, your users don't have to remember new information for each environment, and you don't have to create or update accounts twice.</span></span> <span data-ttu-id="e9b89-123">U moet [uw on-premises adreslijst voorbereiden](prepare-for-directory-synchronization.md) op adreslijstsynchronisatie.</span><span class="sxs-lookup"><span data-stu-id="e9b89-123">You will need to [prepare your on-premises directory](prepare-for-directory-synchronization.md) for directory synchronization.</span></span>
  
![Adreslijstsynchronisatie gebruiken om on-premises en online gegevens van gebruikersaccounts gesynchroniseerd te houden](../media/a64af0d0-9be6-46b1-8727-277e683abf5e.png)
  
<span data-ttu-id="e9b89-125">Als u wilt dat gebruikers zich kunnen aanmelden bij Microsoft 365 met hun on-premises referenties, kunt u ook eenmalige aanmelding configureren.</span><span class="sxs-lookup"><span data-stu-id="e9b89-125">If you want users to be able to log on to Microsoft 365 with their on-premises credentials, you can also configure SSO.</span></span> <span data-ttu-id="e9b89-126">Met eenmalige aanmelding is Microsoft 365 geconfigureerd voor het vertrouwen van de on-premises omgeving voor gebruikersauthenticatie.</span><span class="sxs-lookup"><span data-stu-id="e9b89-126">With SSO, Microsoft 365 is configured to trust the on-premises environment for user authentication.</span></span>
  
![Met eenmalige aanmelding is hetzelfde account beschikbaar in de on-premises omgeving en de online omgeving](../media/d76235f2-8a53-405e-b8ef-dfa4cfc208b8.png)
  
<span data-ttu-id="e9b89-128">Verschillende technieken voor Gebruikersaccountbeheer maken een afwijkende ervaring voor uw gebruikers, zoals wordt weergegeven in de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="e9b89-128">Different user account management techniques provide different experiences for your users, as shown in the following table.</span></span>
 
### <a name="directory-synchronization-with-or-without-password-hash-synchronization-or-pass-through-authentication"></a><span data-ttu-id="e9b89-129">Adreslijstsynchronisatie met of zonder wachtwoord-hash synchronisatie of Pass Through-verificatie</span><span class="sxs-lookup"><span data-stu-id="e9b89-129">Directory synchronization with or without password hash synchronization or pass-through authentication</span></span>

<span data-ttu-id="e9b89-130">Een gebruiker meldt zich aan bij hun on-premises omgeving met hun gebruikersaccount (DOMEIN\gebruikersnaam).</span><span class="sxs-lookup"><span data-stu-id="e9b89-130">A user logs on to their on-premises environment with their user account (domain\username).</span></span> <span data-ttu-id="e9b89-131">Wanneer ze naar Microsoft 365 gaan, moeten ze zich opnieuw aanmelden met hun werk-of schoolaccount (user@domain.com).</span><span class="sxs-lookup"><span data-stu-id="e9b89-131">When they go to Microsoft 365, they must log on again with their work or school account (user@domain.com).</span></span> <span data-ttu-id="e9b89-132">De gebruikersnaam is hetzelfde in beide omgevingen.</span><span class="sxs-lookup"><span data-stu-id="e9b89-132">The user name is the same in both environments.</span></span> <span data-ttu-id="e9b89-133">Wanneer u een hash-synchronisatie via een wachtwoord toevoegt of een Pass-Through-verificatie toevoegt, heeft de gebruiker hetzelfde wachtwoord voor beide omgevingen, maar deze referenties moeten opnieuw worden opgegeven bij het aanmelden bij Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e9b89-133">When you add password hash sync or pass-through authentication, the user has the same password for both environments, but will have to provide those credentials again when logging on to Microsoft 365.</span></span> <span data-ttu-id="e9b89-134">Adreslijstsynchronisatie met wachtwoord hash is het meestgebruikte scenario voor Directory synchronisatie.</span><span class="sxs-lookup"><span data-stu-id="e9b89-134">Directory synchronization with password hash sync is the most commonly used directory sync scenario.</span></span>

<span data-ttu-id="e9b89-135">Als u adreslijstsynchronisatie wilt instellen, maakt u gebruik van Azure Active Directory Connect.</span><span class="sxs-lookup"><span data-stu-id="e9b89-135">To set up directory synchronization, use Azure Active Directory Connect.</span></span> <span data-ttu-id="e9b89-136">Zie [adreslijstsynchronisatie instellen voor Microsoft 365](set-up-directory-synchronization.md)en [Azure AD Connect met expres instellingen](https://go.microsoft.com/fwlink/p/?LinkId=698537)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="e9b89-136">For instructions, read [Set up directory synchronization for Microsoft 365](set-up-directory-synchronization.md), and [Azure AD Connect with express settings](https://go.microsoft.com/fwlink/p/?LinkId=698537).</span></span>

<span data-ttu-id="e9b89-137">Meer informatie over het [voorbereiden van adreslijstsynchronisatie met Microsoft 365](prepare-for-directory-synchronization.md) en [het integreren van uw on-premises identificaties met Azure Active Directory](https://go.microsoft.com/fwlink/?LinkId=518101).</span><span class="sxs-lookup"><span data-stu-id="e9b89-137">Learn more about [preparing for directory synchronization to Microsoft 365](prepare-for-directory-synchronization.md) and [integrating your on-premises identifies with Azure Active Directory](https://go.microsoft.com/fwlink/?LinkId=518101).</span></span>

### <a name="directory-synchronization-with-sso"></a><span data-ttu-id="e9b89-138">Adreslijstsynchronisatie met SSO</span><span class="sxs-lookup"><span data-stu-id="e9b89-138">Directory synchronization with SSO</span></span>

<span data-ttu-id="e9b89-139">Een gebruiker meldt zich aan bij hun on-premises omgeving met hun gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="e9b89-139">A user logs on to their on-premises environment with their user account.</span></span> <span data-ttu-id="e9b89-140">Wanneer de persoon naar Microsoft 365 gaat, meldt u zich automatisch aan of worden ze aangemeld met de referenties die ze voor hun on-premises omgeving gebruiken.</span><span class="sxs-lookup"><span data-stu-id="e9b89-140">When they go to Microsoft 365, they are either logged on automatically, or they log on using the same credentials they use for their on-premises environment (domain\username).</span></span>

<span data-ttu-id="e9b89-141">Voor het instellen van eenmalige aanmelding gebruikt u ook Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="e9b89-141">To set up SSO you also use Azure AD Connect.</span></span> <span data-ttu-id="e9b89-142">Voor instructies raadpleegt u [aangepaste installatie van Azure AD Connect](https://go.microsoft.com/fwlink/p/?LinkID=698430).</span><span class="sxs-lookup"><span data-stu-id="e9b89-142">For instructions, read [Custom installation of Azure AD Connect](https://go.microsoft.com/fwlink/p/?LinkID=698430).</span></span>

<span data-ttu-id="e9b89-143">Meer informatie over [eenmalige aanmelding bij toepassingen in azure Active Directory](https://go.microsoft.com/fwlink/p/?LinkId=698604).</span><span class="sxs-lookup"><span data-stu-id="e9b89-143">Learn more about [single sign-on to applications in Azure Active Directory](https://go.microsoft.com/fwlink/p/?LinkId=698604).</span></span>

## <a name="azure-ad-connect"></a><span data-ttu-id="e9b89-144">Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="e9b89-144">Azure AD Connect</span></span>

<span data-ttu-id="e9b89-145">Azure AD Connect vervangt oudere versies van hulpmiddelen voor identiteits integratie, zoals DirSync en Azure AD-synchronisatie. Zie [Wat is hybride identiteit met Azure Active Directory?](https://go.microsoft.com/fwlink/p/?LinkId=527969)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="e9b89-145">Azure AD Connect replaces older versions of identity integration tools such as DirSync and Azure AD Sync. For more information, see [What is hybrid identity with Azure Active Directory?](https://go.microsoft.com/fwlink/p/?LinkId=527969).</span></span> <span data-ttu-id="e9b89-146">Als u wilt bijwerken van Azure Active Directory-synchronisatie met Azure AD Connect, raadpleegt u [de upgrade-instructies](https://go.microsoft.com/fwlink/p/?LinkId=733240).</span><span class="sxs-lookup"><span data-stu-id="e9b89-146">If you want to update from Azure Active Directory Sync to Azure AD Connect, see [the upgrade instructions](https://go.microsoft.com/fwlink/p/?LinkId=733240).</span></span> 

<span data-ttu-id="e9b89-147">Zie ook [Microsoft 365 Directory-synchronisatie implementeren in Microsoft Azure](https://go.microsoft.com/fwlink/?LinkId=517887).</span><span class="sxs-lookup"><span data-stu-id="e9b89-147">Also see [Deploy Microsoft 365 Directory Synchronization in Microsoft Azure](https://go.microsoft.com/fwlink/?LinkId=517887).</span></span>

## <a name="see-also"></a><span data-ttu-id="e9b89-148">Zie ook</span><span class="sxs-lookup"><span data-stu-id="e9b89-148">See also</span></span>

[<span data-ttu-id="e9b89-149">Overzicht van Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="e9b89-149">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)
