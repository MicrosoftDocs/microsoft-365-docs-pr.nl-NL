---
title: Wachtwoorden voor Microsoft 365-gebruikersaccounts beheren
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: Meer informatie over het beheren van wachtwoorden voor Microsoft 365-gebruikersaccounts.
ms.openlocfilehash: af64002ad54b517a6e8f0b687a00d6bed9ab0214
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328493"
---
# <a name="manage-microsoft-365-user-account-passwords"></a><span data-ttu-id="1c44c-103">Wachtwoorden voor Microsoft 365-gebruikersaccounts beheren</span><span class="sxs-lookup"><span data-stu-id="1c44c-103">Manage Microsoft 365 user account passwords</span></span>

<span data-ttu-id="1c44c-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="1c44c-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="1c44c-105">U kunt wachtwoorden van gebruikersaccounts van Microsoft 365 op verschillende manieren beheren, afhankelijk van de configuratie van uw identiteit.</span><span class="sxs-lookup"><span data-stu-id="1c44c-105">You can manage Microsoft 365 user account passwords in several different ways, depending on your identity configuration.</span></span> <span data-ttu-id="1c44c-106">U kunt gebruikersaccounts beheren in het [Microsoft 365-Beheercentrum](https://docs.microsoft.com/microsoft-365/admin/add-users/), in Active Directory Domain Services (AD DS) of in het Azure Active Directory (Azure AD)-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="1c44c-106">You can manage user accounts in the [Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/add-users/), in Active Directory Domain Services (AD DS), or in the Azure Active Directory (Azure AD) admin center.</span></span>

## <a name="plan-for-where-and-how-you-will-manage-your-user-account-passwords"></a><span data-ttu-id="1c44c-107">Plannen waar en hoe u uw wachtwoorden voor uw gebruikersaccount beheert</span><span class="sxs-lookup"><span data-stu-id="1c44c-107">Plan for where and how you will manage your user account passwords</span></span>

<span data-ttu-id="1c44c-108">Waar en hoe u uw gebruikersaccounts kunt beheren, is afhankelijk van het identiteits model dat u wilt gebruiken voor uw Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1c44c-108">Where and how you can manage your user accounts depends on the identity model you want to use for your Microsoft 365.</span></span> <span data-ttu-id="1c44c-109">De twee modellen zijn alleen voor de Cloud en hybride.</span><span class="sxs-lookup"><span data-stu-id="1c44c-109">The two models are cloud-only and hybrid.</span></span>
  
### <a name="cloud-only"></a><span data-ttu-id="1c44c-110">Alleen in de cloud</span><span class="sxs-lookup"><span data-stu-id="1c44c-110">Cloud-only</span></span>

<span data-ttu-id="1c44c-111">U beheert wachtwoorden van gebruikersaccounts in:</span><span class="sxs-lookup"><span data-stu-id="1c44c-111">You manage user account passwords in:</span></span>

- [<span data-ttu-id="1c44c-112">Het Microsoft 365-beheercentrum</span><span class="sxs-lookup"><span data-stu-id="1c44c-112">The Microsoft 365 admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/)
- <span data-ttu-id="1c44c-113">Het Azure AD-Beheercentrum</span><span class="sxs-lookup"><span data-stu-id="1c44c-113">The Azure AD admin center</span></span>
    
### <a name="hybrid"></a><span data-ttu-id="1c44c-114">Hybride</span><span class="sxs-lookup"><span data-stu-id="1c44c-114">Hybrid</span></span>

<span data-ttu-id="1c44c-115">Met de Hybrid Identity worden wachtwoorden opgeslagen in AD DS, zodat u on-premises hulpmiddelen voor AD DS moet gebruiken voor het beheren van wachtwoorden van gebruikersaccounts.</span><span class="sxs-lookup"><span data-stu-id="1c44c-115">With hybrid identity, passwords are stored in AD DS so you must use on-premises AD DS tools to manage user account passwords.</span></span> <span data-ttu-id="1c44c-116">Ook als u hash-synchronisatie (PHS) gebruikt waarin in azure AD een hash-versie van de al hashed-versie is opgeslagen in AD DS, moeten u en gebruikers hun wachtwoord beheren in AD DS.</span><span class="sxs-lookup"><span data-stu-id="1c44c-116">Even when using Password Hash Synchronization (PHS), in which Azure AD stores a hashed version of the already hashed version in AD DS, you and users must manage their passwords in AD DS.</span></span>

<span data-ttu-id="1c44c-117">Met het [terugschrijven van wachtwoorden](#pw_writeback)kunnen gebruikers hun AD DS-wachtwoorden via Azure AD wijzigen.</span><span class="sxs-lookup"><span data-stu-id="1c44c-117">With [password writeback](#pw_writeback), your users can change their AD DS passwords through Azure AD.</span></span>

## <a name="prevent-bad-passwords"></a><span data-ttu-id="1c44c-118">Slechte wachtwoorden voorkomen</span><span class="sxs-lookup"><span data-stu-id="1c44c-118">Prevent bad passwords</span></span>

<span data-ttu-id="1c44c-119">Al uw gebruikers dienen de [Wachtwoordondersteuning van Microsoft](https://www.microsoft.com/research/publication/password-guidance) te gebruiken om de wachtwoorden voor hun gebruikersaccounts te maken.</span><span class="sxs-lookup"><span data-stu-id="1c44c-119">All your users should be using [Microsoft's password guidance](https://www.microsoft.com/research/publication/password-guidance) to create their user account passwords.</span></span>

<span data-ttu-id="1c44c-120">Als u wilt voorkomen dat gebruikers een te makkelijk wachtwoord aanmaken, gebruikt u Azure AD-wachtwoordbeveiliging. Hierbij wordt gebruikgemaakt van een wereldwijd geblokkeerde wachtwoordlijst en een optionele, aangepaste lijst met geblokkeerde wachtwoorden die u kunt vaststellen.</span><span class="sxs-lookup"><span data-stu-id="1c44c-120">To prevent users from creating an easily-determined password, use Azure AD password protection, which uses both a global banned password list and an optional custom banned password list that you specify.</span></span> <span data-ttu-id="1c44c-121">U kunt bijvoorbeeld termen op deze lijst zetten die specifiek voor uw organisatie zijn, zoals:</span><span class="sxs-lookup"><span data-stu-id="1c44c-121">For example, you can specify terms that are specific to your organization, such as:</span></span>

- <span data-ttu-id="1c44c-122">Merknamen</span><span class="sxs-lookup"><span data-stu-id="1c44c-122">Brand names</span></span>
- <span data-ttu-id="1c44c-123">Productnamen</span><span class="sxs-lookup"><span data-stu-id="1c44c-123">Product names</span></span>
- <span data-ttu-id="1c44c-124">Locaties (zoals bijvoorbeeld het hoofdkantoor van het bedrijf)</span><span class="sxs-lookup"><span data-stu-id="1c44c-124">Locations (for example, such as company headquarters)</span></span>
- <span data-ttu-id="1c44c-125">Bedrijfsspecifieke interne termen</span><span class="sxs-lookup"><span data-stu-id="1c44c-125">Company-specific internal terms</span></span>
- <span data-ttu-id="1c44c-126">Afkortingen met een specifieke betekenis binnen het bedrijf</span><span class="sxs-lookup"><span data-stu-id="1c44c-126">Abbreviations that have specific company meaning</span></span>

<span data-ttu-id="1c44c-127">U kunt beschadigde wachtwoorden [in de Cloud](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) en voor uw [on-PREMISes AD DS](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises)blokkeren.</span><span class="sxs-lookup"><span data-stu-id="1c44c-127">You can ban bad passwords [in the cloud](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) and for your [on-premises AD DS](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises).</span></span>

## <a name="simplify-user-sign-in"></a><span data-ttu-id="1c44c-128">Gebruikersaanmelding vereenvoudigen</span><span class="sxs-lookup"><span data-stu-id="1c44c-128">Simplify user sign-in</span></span>

<span data-ttu-id="1c44c-129">Probleemloos eenmalige aanmelding met Azure AD (Azure AD naadloos SSO) werkt met PHS en Pass-Through-verificatie (PTA), zodat gebruikers zich kunnen aanmelden bij services die gebruikmaken van Azure AD-gebruikersaccounts zonder dat ze hun wachtwoorden moeten typen, en in veel gevallen, zijn hun gebruikersnamen.</span><span class="sxs-lookup"><span data-stu-id="1c44c-129">Azure AD Seamless Single Sign-On (Azure AD Seamless SSO) works with PHS and Pass-Through Authentication (PTA), to allow your users to sign in to services that use Azure AD user accounts without having to type in their passwords, and in many cases, their usernames.</span></span> <span data-ttu-id="1c44c-130">Dit geeft uw gebruikers eenvoudiger toegang tot toepassingen in de cloud, zoals Office 365, zonder extra onderdelen op locatie nodig te hebben, zoals identiteitsfederatie-servers.</span><span class="sxs-lookup"><span data-stu-id="1c44c-130">This gives your users easier access to cloud-based applications, such as Office 365, without needing any additional on-premises components such as identity federation servers.</span></span>

<span data-ttu-id="1c44c-131">U configureert naadloze eenmalige aanmelding via Azure AD met het hulpprogramma Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="1c44c-131">You configure Azure AD Seamless SSO with the Azure AD Connect tool.</span></span> <span data-ttu-id="1c44c-132">Zie [instructies voor het configureren naadloze eenmalige aanmelding via Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span><span class="sxs-lookup"><span data-stu-id="1c44c-132">See the [instructions to configure Azure AD Seamless SSO](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span></span>

<a name="pw_writeback"></a>
## <a name="simplify-password-updates-to-ad-ds"></a><span data-ttu-id="1c44c-133">Wachtwoord updates vereenvoudigen voor AD DS</span><span class="sxs-lookup"><span data-stu-id="1c44c-133">Simplify password updates to AD DS</span></span>

<span data-ttu-id="1c44c-134">Met wachtwoord terugschrijven kunt u toestaan dat gebruikers hun wachtwoord opnieuw kunnen instellen via Azure AD, dat vervolgens wordt gerepliceerd naar AD DS.</span><span class="sxs-lookup"><span data-stu-id="1c44c-134">With password writeback, you can allow users to reset their passwords through Azure AD, which is then replicated to AD DS.</span></span> <span data-ttu-id="1c44c-135">Gebruikers hoeven geen toegang te krijgen tot hun on-premises AD DS om hun wachtwoord bij te werken.</span><span class="sxs-lookup"><span data-stu-id="1c44c-135">Users don’t need to access their on-premises AD DS to update their passwords.</span></span> <span data-ttu-id="1c44c-136">Dit is handig bij roaming en gebruikers die extern werken die geen RAS-verbinding met het on-premises netwerk hebben.</span><span class="sxs-lookup"><span data-stu-id="1c44c-136">This is valuable to roaming or remote users who do not have a remote access connection to the on-premises network.</span></span>

<span data-ttu-id="1c44c-137">Wachtwoord terugschrijven is vereist om volledig gebruik te kunnen maken van de mogelijkheden van Identity Protection-functies, zoals vereisen dat gebruikers hun on-premises wachtwoorden wijzigen wanneer er een hoog risico op inbreuk van accounts is gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="1c44c-137">Password writeback is required to fully utilize Azure AD Identity Protection capabilities, such as requiring users to change their on-premises passwords when there has been a high risk of account compromise detected.</span></span>

<span data-ttu-id="1c44c-138">Zie [Azure AD SSPR met wachtwoord terugschrijven](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback) voor meer informatie en configuratie-instructies.</span><span class="sxs-lookup"><span data-stu-id="1c44c-138">For additional information and configuration instructions, see [Azure AD SSPR with password writeback](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback).</span></span>

>[!Note]
><span data-ttu-id="1c44c-139">Voer een upgrade uit naar de nieuwste versie van Azure AD Connect om te zorgen voor een optimale ervaring en nieuwe functies zodra deze beschikbaar komen.</span><span class="sxs-lookup"><span data-stu-id="1c44c-139">Upgrade to the latest version of Azure AD Connect to ensure the best possible experience and new features as they are released.</span></span> <span data-ttu-id="1c44c-140">Zie [Aangepaste installatie van Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="1c44c-140">For more information, see [Custom installation of Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).</span></span>
>

## <a name="simplify-password-resets"></a><span data-ttu-id="1c44c-141">Het opnieuw instellen van wachtwoorden vereenvoudigen</span><span class="sxs-lookup"><span data-stu-id="1c44c-141">Simplify password resets</span></span>

<span data-ttu-id="1c44c-142">Met selfservice voor wachtwoordherstel (SSPR) kunnen gebruikers hun wachtwoorden of accounts opnieuw instellen of ontgrendelen.</span><span class="sxs-lookup"><span data-stu-id="1c44c-142">Self-service password reset (SSPR) allows users to reset or unlock their passwords or accounts.</span></span> <span data-ttu-id="1c44c-143">Als u wilt worden gewaarschuwd voor misbruik, kunt u gebruikmaken van gedetailleerde rapporten die bijhouden en meldingen geven wanneer gebruikers het systeem openen.</span><span class="sxs-lookup"><span data-stu-id="1c44c-143">To alert you to misuse or abuse, you can use the detailed reporting that tracks when users access the system, along with notifications.</span></span> <span data-ttu-id="1c44c-144">U moet [wachtwoord terugschrijven](#pw_writeback) inschakelen voordat u het opnieuw instellen van wachtwoorden kunt implementeren.</span><span class="sxs-lookup"><span data-stu-id="1c44c-144">You must enable [password writeback](#pw_writeback) before you can deploy password resets.</span></span>

<span data-ttu-id="1c44c-145">Zie de [instructies voor het invoeren van wachtwoordherstel](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment).</span><span class="sxs-lookup"><span data-stu-id="1c44c-145">See the [instructions to roll out password reset](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment).</span></span>

