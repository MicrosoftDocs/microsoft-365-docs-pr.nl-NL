---
title: Wachtwoorden voor gebruikersaccounts van Microsoft 365 beheren
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
description: Meer informatie over het beheren van wachtwoorden voor gebruikersaccounts van Microsoft 365.
ms.openlocfilehash: 2062da49310121ec18f7ce21f523531f10d6df9b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905090"
---
# <a name="manage-microsoft-365-user-account-passwords"></a><span data-ttu-id="73f9f-103">Wachtwoorden voor gebruikersaccounts van Microsoft 365 beheren</span><span class="sxs-lookup"><span data-stu-id="73f9f-103">Manage Microsoft 365 user account passwords</span></span>

<span data-ttu-id="73f9f-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="73f9f-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="73f9f-105">U kunt wachtwoorden voor gebruikersaccounts van Microsoft 365 op verschillende manieren beheren, afhankelijk van uw identiteitsconfiguratie.</span><span class="sxs-lookup"><span data-stu-id="73f9f-105">You can manage Microsoft 365 user account passwords in several different ways, depending on your identity configuration.</span></span> <span data-ttu-id="73f9f-106">U kunt gebruikersaccounts beheren in het [Microsoft 365-beheercentrum](../admin/add-users/index.yml), in Ad DS (Active Directory Domain Services) of in het Azure Active Directory-beheercentrum (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="73f9f-106">You can manage user accounts in the [Microsoft 365 admin center](../admin/add-users/index.yml), in Active Directory Domain Services (AD DS), or in the Azure Active Directory (Azure AD) admin center.</span></span>

## <a name="plan-for-where-and-how-you-will-manage-your-user-account-passwords"></a><span data-ttu-id="73f9f-107">Plannen voor waar en hoe u wachtwoorden voor uw gebruikersaccount gaat beheren</span><span class="sxs-lookup"><span data-stu-id="73f9f-107">Plan for where and how you will manage your user account passwords</span></span>

<span data-ttu-id="73f9f-108">Waar en hoe u uw gebruikersaccounts kunt beheren, is afhankelijk van het identiteitsmodel dat u wilt gebruiken voor uw Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="73f9f-108">Where and how you can manage your user accounts depends on the identity model you want to use for your Microsoft 365.</span></span> <span data-ttu-id="73f9f-109">De twee modellen zijn alleen-in de cloud en hybride.</span><span class="sxs-lookup"><span data-stu-id="73f9f-109">The two models are cloud-only and hybrid.</span></span>
  
### <a name="cloud-only"></a><span data-ttu-id="73f9f-110">Alleen in de cloud</span><span class="sxs-lookup"><span data-stu-id="73f9f-110">Cloud-only</span></span>

<span data-ttu-id="73f9f-111">U beheert wachtwoorden voor gebruikersaccounts in:</span><span class="sxs-lookup"><span data-stu-id="73f9f-111">You manage user account passwords in:</span></span>

- [<span data-ttu-id="73f9f-112">Het Microsoft 365-beheercentrum</span><span class="sxs-lookup"><span data-stu-id="73f9f-112">The Microsoft 365 admin center</span></span>](../admin/add-users/index.yml)
- <span data-ttu-id="73f9f-113">Het Azure AD-beheercentrum</span><span class="sxs-lookup"><span data-stu-id="73f9f-113">The Azure AD admin center</span></span>
    
### <a name="hybrid"></a><span data-ttu-id="73f9f-114">Hybride</span><span class="sxs-lookup"><span data-stu-id="73f9f-114">Hybrid</span></span>

<span data-ttu-id="73f9f-115">Bij hybride identiteit worden wachtwoorden opgeslagen in AD DS, dus u moet on-premises AD DS-hulpprogramma's gebruiken om wachtwoorden voor gebruikersaccounts te beheren.</span><span class="sxs-lookup"><span data-stu-id="73f9f-115">With hybrid identity, passwords are stored in AD DS so you must use on-premises AD DS tools to manage user account passwords.</span></span> <span data-ttu-id="73f9f-116">Zelfs wanneer u Wachtwoordhashsynchronisatie (PHS) gebruikt, waarin In Azure AD een gehashte versie van de al gehashte versie in AD DS wordt opgeslagen, moeten u en gebruikers hun wachtwoorden beheren in AD DS.</span><span class="sxs-lookup"><span data-stu-id="73f9f-116">Even when using Password Hash Synchronization (PHS), in which Azure AD stores a hashed version of the already hashed version in AD DS, you and users must manage their passwords in AD DS.</span></span>

<span data-ttu-id="73f9f-117">Met [wachtwoordschrijven kunnen](#pw_writeback)uw gebruikers hun AD DS-wachtwoorden wijzigen via Azure AD.</span><span class="sxs-lookup"><span data-stu-id="73f9f-117">With [password writeback](#pw_writeback), your users can change their AD DS passwords through Azure AD.</span></span>

## <a name="prevent-bad-passwords"></a><span data-ttu-id="73f9f-118">Slechte wachtwoorden voorkomen</span><span class="sxs-lookup"><span data-stu-id="73f9f-118">Prevent bad passwords</span></span>

<span data-ttu-id="73f9f-119">Al uw gebruikers dienen de [Wachtwoordondersteuning van Microsoft](https://www.microsoft.com/research/publication/password-guidance) te gebruiken om de wachtwoorden voor hun gebruikersaccounts te maken.</span><span class="sxs-lookup"><span data-stu-id="73f9f-119">All your users should be using [Microsoft's password guidance](https://www.microsoft.com/research/publication/password-guidance) to create their user account passwords.</span></span>

<span data-ttu-id="73f9f-120">Als u wilt voorkomen dat gebruikers een te makkelijk wachtwoord aanmaken, gebruikt u Azure AD-wachtwoordbeveiliging. Hierbij wordt gebruikgemaakt van een wereldwijd geblokkeerde wachtwoordlijst en een optionele, aangepaste lijst met geblokkeerde wachtwoorden die u kunt vaststellen.</span><span class="sxs-lookup"><span data-stu-id="73f9f-120">To prevent users from creating an easily-determined password, use Azure AD password protection, which uses both a global banned password list and an optional custom banned password list that you specify.</span></span> <span data-ttu-id="73f9f-121">U kunt bijvoorbeeld termen op deze lijst zetten die specifiek voor uw organisatie zijn, zoals:</span><span class="sxs-lookup"><span data-stu-id="73f9f-121">For example, you can specify terms that are specific to your organization, such as:</span></span>

- <span data-ttu-id="73f9f-122">Merknamen</span><span class="sxs-lookup"><span data-stu-id="73f9f-122">Brand names</span></span>
- <span data-ttu-id="73f9f-123">Productnamen</span><span class="sxs-lookup"><span data-stu-id="73f9f-123">Product names</span></span>
- <span data-ttu-id="73f9f-124">Locaties (zoals bijvoorbeeld het hoofdkantoor van het bedrijf)</span><span class="sxs-lookup"><span data-stu-id="73f9f-124">Locations (for example, such as company headquarters)</span></span>
- <span data-ttu-id="73f9f-125">Bedrijfsspecifieke interne termen</span><span class="sxs-lookup"><span data-stu-id="73f9f-125">Company-specific internal terms</span></span>
- <span data-ttu-id="73f9f-126">Afkortingen met een specifieke betekenis binnen het bedrijf</span><span class="sxs-lookup"><span data-stu-id="73f9f-126">Abbreviations that have specific company meaning</span></span>

<span data-ttu-id="73f9f-127">U kunt slechte wachtwoorden [in de cloud en](/azure/active-directory/authentication/concept-password-ban-bad) voor uw [on-premises AD DS verbieden.](/azure/active-directory/authentication/concept-password-ban-bad-on-premises)</span><span class="sxs-lookup"><span data-stu-id="73f9f-127">You can ban bad passwords [in the cloud](/azure/active-directory/authentication/concept-password-ban-bad) and for your [on-premises AD DS](/azure/active-directory/authentication/concept-password-ban-bad-on-premises).</span></span>

## <a name="simplify-user-sign-in"></a><span data-ttu-id="73f9f-128">Gebruikersaanmelding vereenvoudigen</span><span class="sxs-lookup"><span data-stu-id="73f9f-128">Simplify user sign-in</span></span>

<span data-ttu-id="73f9f-129">Azure AD Seamless Single Sign-On (Azure AD Seamless SSO) werkt met PHS en Pass-Through Authentication (PTA), zodat uw gebruikers zich kunnen aanmelden bij services die Azure AD-gebruikersaccounts gebruiken zonder hun wachtwoorden en in veel gevallen hun gebruikersnaam in te typen.</span><span class="sxs-lookup"><span data-stu-id="73f9f-129">Azure AD Seamless Single Sign-On (Azure AD Seamless SSO) works with PHS and Pass-Through Authentication (PTA), to allow your users to sign in to services that use Azure AD user accounts without having to type in their passwords, and in many cases, their usernames.</span></span> <span data-ttu-id="73f9f-130">Dit geeft uw gebruikers eenvoudiger toegang tot toepassingen in de cloud, zoals Office 365, zonder extra onderdelen op locatie nodig te hebben, zoals identiteitsfederatie-servers.</span><span class="sxs-lookup"><span data-stu-id="73f9f-130">This gives your users easier access to cloud-based applications, such as Office 365, without needing any additional on-premises components such as identity federation servers.</span></span>

<span data-ttu-id="73f9f-131">U configureert naadloze eenmalige aanmelding via Azure AD met het hulpprogramma Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="73f9f-131">You configure Azure AD Seamless SSO with the Azure AD Connect tool.</span></span> <span data-ttu-id="73f9f-132">Zie [instructies voor het configureren naadloze eenmalige aanmelding via Azure AD](/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span><span class="sxs-lookup"><span data-stu-id="73f9f-132">See the [instructions to configure Azure AD Seamless SSO](/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span></span>

<a name="pw_writeback"></a>
## <a name="simplify-password-updates-to-ad-ds"></a><span data-ttu-id="73f9f-133">Wachtwoordupdates voor AD DS vereenvoudigen</span><span class="sxs-lookup"><span data-stu-id="73f9f-133">Simplify password updates to AD DS</span></span>

<span data-ttu-id="73f9f-134">Met wachtwoordschrijven kunt u toestaan dat gebruikers hun wachtwoorden opnieuw instellen via Azure AD, dat vervolgens wordt gerepliceerd naar AD DS.</span><span class="sxs-lookup"><span data-stu-id="73f9f-134">With password writeback, you can allow users to reset their passwords through Azure AD, which is then replicated to AD DS.</span></span> <span data-ttu-id="73f9f-135">Gebruikers hoeven hun on-premises AD DS niet te openen om hun wachtwoorden bij te werken.</span><span class="sxs-lookup"><span data-stu-id="73f9f-135">Users don’t need to access their on-premises AD DS to update their passwords.</span></span> <span data-ttu-id="73f9f-136">Dit is handig bij roaming en gebruikers die extern werken die geen RAS-verbinding met het on-premises netwerk hebben.</span><span class="sxs-lookup"><span data-stu-id="73f9f-136">This is valuable to roaming or remote users who do not have a remote access connection to the on-premises network.</span></span>

<span data-ttu-id="73f9f-137">Wachtwoord terugschrijven is vereist om volledig gebruik te kunnen maken van de mogelijkheden van Identity Protection-functies, zoals vereisen dat gebruikers hun on-premises wachtwoorden wijzigen wanneer er een hoog risico op inbreuk van accounts is gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="73f9f-137">Password writeback is required to fully utilize Azure AD Identity Protection capabilities, such as requiring users to change their on-premises passwords when there has been a high risk of account compromise detected.</span></span>

<span data-ttu-id="73f9f-138">Zie [Azure AD SSPR met wachtwoord terugschrijven](/azure/active-directory/active-directory-passwords-writeback) voor meer informatie en configuratie-instructies.</span><span class="sxs-lookup"><span data-stu-id="73f9f-138">For additional information and configuration instructions, see [Azure AD SSPR with password writeback](/azure/active-directory/active-directory-passwords-writeback).</span></span>

>[!Note]
><span data-ttu-id="73f9f-139">Voer een upgrade uit naar de nieuwste versie van Azure AD Connect om te zorgen voor een optimale ervaring en nieuwe functies zodra deze beschikbaar komen.</span><span class="sxs-lookup"><span data-stu-id="73f9f-139">Upgrade to the latest version of Azure AD Connect to ensure the best possible experience and new features as they are released.</span></span> <span data-ttu-id="73f9f-140">Zie [Aangepaste installatie van Azure AD Connect](/azure/active-directory/connect/active-directory-aadconnect-get-started-custom) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="73f9f-140">For more information, see [Custom installation of Azure AD Connect](/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).</span></span>
>

## <a name="simplify-password-resets"></a><span data-ttu-id="73f9f-141">Het opnieuw instellen van wachtwoorden vereenvoudigen</span><span class="sxs-lookup"><span data-stu-id="73f9f-141">Simplify password resets</span></span>

<span data-ttu-id="73f9f-142">Met SelfService Password Reset (SSPR) kunnen gebruikers hun wachtwoorden of accounts opnieuw instellen of ontgrendelen.</span><span class="sxs-lookup"><span data-stu-id="73f9f-142">Self-service password reset (SSPR) allows users to reset or unlock their passwords or accounts.</span></span> <span data-ttu-id="73f9f-143">Als u wilt worden gewaarschuwd voor misbruik, kunt u gebruikmaken van gedetailleerde rapporten die bijhouden en meldingen geven wanneer gebruikers het systeem openen.</span><span class="sxs-lookup"><span data-stu-id="73f9f-143">To alert you to misuse or abuse, you can use the detailed reporting that tracks when users access the system, along with notifications.</span></span> <span data-ttu-id="73f9f-144">U moet [wachtwoordschrijven inschakelen voordat](#pw_writeback) u wachtwoordinstellingen kunt implementeren.</span><span class="sxs-lookup"><span data-stu-id="73f9f-144">You must enable [password writeback](#pw_writeback) before you can deploy password resets.</span></span>

<span data-ttu-id="73f9f-145">Zie de [instructies voor het invoeren van wachtwoordherstel](/azure/active-directory/authentication/howto-sspr-deployment).</span><span class="sxs-lookup"><span data-stu-id="73f9f-145">See the [instructions to roll out password reset](/azure/active-directory/authentication/howto-sspr-deployment).</span></span>