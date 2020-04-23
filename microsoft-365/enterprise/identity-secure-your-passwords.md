---
title: 'Stap 2: Wachtwoorden beveiligen'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: U moet de wachtwoorden binnen uw organisatie sterk en beheerbaar maken.
ms.openlocfilehash: b4eb1861eb8d1c483972cf6a7c22a339dc1b0b36
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637046"
---
# <a name="step-2-secure-your-passwords"></a><span data-ttu-id="abf45-103">Stap 2: Wachtwoorden beveiligen</span><span class="sxs-lookup"><span data-stu-id="abf45-103">Step 2: Secure your passwords</span></span>

![Fase 2-Identiteit](../media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-password-prot"></a>
## <a name="prevent-bad-passwords"></a><span data-ttu-id="abf45-105">Slechte wachtwoorden voorkomen</span><span class="sxs-lookup"><span data-stu-id="abf45-105">Prevent bad passwords</span></span>

<span data-ttu-id="abf45-106">*Deze stap is optioneel en geldt voor zowel E3- als E5-versies van Microsoft 365*</span><span class="sxs-lookup"><span data-stu-id="abf45-106">*This is optional and applies to both the E3 and E5 versions of Microsoft 365*</span></span>

<span data-ttu-id="abf45-107">Al uw gebruikers dienen de [Wachtwoordondersteuning van Microsoft](https://www.microsoft.com/research/publication/password-guidance/) te gebruiken om de wachtwoorden voor hun gebruikersaccounts te maken.</span><span class="sxs-lookup"><span data-stu-id="abf45-107">All your users should be using [Microsoft's password guidance](https://www.microsoft.com/research/publication/password-guidance/) to create their user account passwords.</span></span>

<span data-ttu-id="abf45-108">Als u wilt voorkomen dat gebruikers een te makkelijk wachtwoord aanmaken, gebruikt u Azure AD-wachtwoordbeveiliging. Hierbij wordt gebruikgemaakt van een wereldwijd geblokkeerde wachtwoordlijst en een optionele, aangepaste lijst met geblokkeerde wachtwoorden die u kunt vaststellen.</span><span class="sxs-lookup"><span data-stu-id="abf45-108">To prevent users from creating an easily-determined password, use Azure AD password protection, which uses both a global banned password list and an optional custom banned password list that you specify.</span></span> <span data-ttu-id="abf45-109">U kunt bijvoorbeeld termen op deze lijst zetten die specifiek voor uw organisatie zijn, zoals:</span><span class="sxs-lookup"><span data-stu-id="abf45-109">For example, you can specify terms that are specific to your organization, such as:</span></span>

- <span data-ttu-id="abf45-110">Merknamen</span><span class="sxs-lookup"><span data-stu-id="abf45-110">Brand names</span></span>
- <span data-ttu-id="abf45-111">Productnamen</span><span class="sxs-lookup"><span data-stu-id="abf45-111">Product names</span></span>
- <span data-ttu-id="abf45-112">Locaties (zoals bijvoorbeeld het hoofdkantoor van het bedrijf)</span><span class="sxs-lookup"><span data-stu-id="abf45-112">Locations (for example, such as company headquarters)</span></span>
- <span data-ttu-id="abf45-113">Bedrijfsspecifieke interne termen</span><span class="sxs-lookup"><span data-stu-id="abf45-113">Company-specific internal terms</span></span>
- <span data-ttu-id="abf45-114">Afkortingen met een specifieke betekenis binnen het bedrijf</span><span class="sxs-lookup"><span data-stu-id="abf45-114">Abbreviations that have specific company meaning</span></span>

<span data-ttu-id="abf45-115">U kunt slechte wachtwoorden [in de Cloud](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) en voor uw [Active Directory Domain Services (AD DS) op locatie](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises) verbieden.</span><span class="sxs-lookup"><span data-stu-id="abf45-115">You can ban bad passwords [in the cloud](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) and for your [on-premises Active Directory Domain Services (AD DS)](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises).</span></span>

<span data-ttu-id="abf45-116">Als tussentijds controlepunt kunt u de [afsluitcriteria](identity-exit-criteria.md#crit-password-prot) voor deze sectie bekijken.</span><span class="sxs-lookup"><span data-stu-id="abf45-116">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-password-prot) for this section.</span></span>

<a name="identity-pw-reset"></a>
## <a name="simplify-password-resets"></a><span data-ttu-id="abf45-117">Het opnieuw instellen van wachtwoorden vereenvoudigen</span><span class="sxs-lookup"><span data-stu-id="abf45-117">Simplify password resets</span></span>

<span data-ttu-id="abf45-118">*Deze stap is optioneel en geldt voor zowel E3- als E5-versies van Microsoft 365*</span><span class="sxs-lookup"><span data-stu-id="abf45-118">*This is optional and applies to both the E3 and E5 versions of Microsoft 365*</span></span>

<span data-ttu-id="abf45-119">In deze sectie kunt u de selfservice voor het opnieuw instellen van wachtwoorden (SSPR) inschakelen, zodat gebruikers hun wachtwoorden of accounts opnieuw kunnen instellen of ontgrendelen.</span><span class="sxs-lookup"><span data-stu-id="abf45-119">In this section, you'll enable self-service password reset (SSPR) to allow users to reset or unlock their passwords or accounts.</span></span> <span data-ttu-id="abf45-120">Als u wilt worden gewaarschuwd voor misbruik, kunt u gebruikmaken van gedetailleerde rapporten die bijhouden en meldingen geven wanneer gebruikers het systeem openen.</span><span class="sxs-lookup"><span data-stu-id="abf45-120">To alert you to misuse or abuse, you can use the detailed reporting that tracks when users access the system, along with notifications.</span></span> <span data-ttu-id="abf45-121">U moet het terugschrijven van wachtwoorden inschakelen voordat u het opnieuw instellen van wachtwoord kunt implementeren.</span><span class="sxs-lookup"><span data-stu-id="abf45-121">You must enable password writeback before you can deploy password resets.</span></span>

<span data-ttu-id="abf45-122">Zie de [instructies voor het invoeren van wachtwoordherstel](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment).</span><span class="sxs-lookup"><span data-stu-id="abf45-122">See the [instructions to roll out password reset](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment).</span></span>

|||
|:-------|:-----|
|![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="abf45-124">Testlabrichtlijn: Wachtwoord opnieuw instellen</span><span class="sxs-lookup"><span data-stu-id="abf45-124">Test Lab Guide: Password reset</span></span>](password-reset-m365-ent-test-environment.md) |
|||

<span data-ttu-id="abf45-125">Als tussentijds controlepunt kunt u de [afsluitcriteria](identity-exit-criteria.md#crit-identity-pw-reset) voor deze sectie bekijken.</span><span class="sxs-lookup"><span data-stu-id="abf45-125">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pw-reset) for this section.</span></span>


<a name="identity-sso"></a>
## <a name="simplify-user-sign-in"></a><span data-ttu-id="abf45-126">Gebruikersaanmelding vereenvoudigen</span><span class="sxs-lookup"><span data-stu-id="abf45-126">Simplify user sign-in</span></span>

<span data-ttu-id="abf45-127">*Deze stap is optioneel voor hybride omgevingen en geldt voor zowel E3- als E5-versies van Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="abf45-127">*This is optional for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="abf45-128">In deze sectie stelt u naadloze eenmalige aanmelding via Azure Active Directory in, dat met wachtwoord-hash-synchronisatie en pass-through-verificatie werkt om ervoor te zorgen dat uw gebruikers zich kunnen aanmelden bij services die gebruikmaken van Azure Active Directory-gebruikersaccounts, zonder dat ze hun wachtwoorden en in veel gevallen zelfs hun gebruikersnamen hoeven in te voeren.</span><span class="sxs-lookup"><span data-stu-id="abf45-128">In this section, you'll set up Azure Active Directory Seamless Single Sign-On (Azure AD Seamless SSO), which works with Password Hash Synchronization (PHS) and Pass-Through Authentication (PTA), to allow your users to sign in to services that use Azure AD user accounts without having to type in their passwords, and in many cases, their usernames.</span></span> <span data-ttu-id="abf45-129">Dit geeft uw gebruikers eenvoudiger toegang tot toepassingen in de cloud, zoals Office 365, zonder extra onderdelen op locatie nodig te hebben, zoals identiteitsfederatie-servers.</span><span class="sxs-lookup"><span data-stu-id="abf45-129">This gives your users easier access to cloud-based applications, such as Office 365, without needing any additional on-premises components such as identity federation servers.</span></span>

<span data-ttu-id="abf45-130">U configureert naadloze eenmalige aanmelding via Azure AD met het hulpprogramma Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="abf45-130">You configure Azure AD Seamless SSO with the Azure AD Connect tool.</span></span>

<span data-ttu-id="abf45-131">Zie [instructies voor het configureren naadloze eenmalige aanmelding via Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span><span class="sxs-lookup"><span data-stu-id="abf45-131">See the [instructions to configure Azure AD Seamless SSO](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span></span>

|||
|:-------|:-----|
|![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="abf45-133">Testlabrichtlijn: naadloze eenmalige aanmelding via Azure AD</span><span class="sxs-lookup"><span data-stu-id="abf45-133">Test Lab Guide: Azure AD Seamless Single Sign-on</span></span>](single-sign-on-m365-ent-test-environment.md) |
|||

<span data-ttu-id="abf45-134">Als tussentijds controlepunt kunt u de [afsluitcriteria](identity-exit-criteria.md#crit-identity-sso) voor dit gedeelte bekijken.</span><span class="sxs-lookup"><span data-stu-id="abf45-134">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sso) for this section.</span></span>


<a name="identity-custom-sign-in"></a>
## <a name="customize-the-sign-in-page"></a><span data-ttu-id="abf45-135">De aanmeldingspagina aanpassen</span><span class="sxs-lookup"><span data-stu-id="abf45-135">Customize the sign-in page</span></span>

<span data-ttu-id="abf45-136">*Deze stap is optioneel en geldt voor zowel E3- als E5-versies van Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="abf45-136">*This is optional and for both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="abf45-137">Met deze stap helpt u gebruikers de aanmeldingspagina van uw organisatie te herkennen door uw bedrijfsnaam, -logo en andere herkenbare elementen toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="abf45-137">In this section, you'll help users recognize your organization’s sign-in page by adding your company name, logo, and other recognizable elements.</span></span> 

<span data-ttu-id="abf45-138">Met Microsoft 365 Enterprise kunt u het uiterlijk van de aanmeldings- en toegangspagina’s aanpassen, zodat ze uw bedrijfslogo, kleurenschema’s en aangepaste gebruikersgegevens bevatten.</span><span class="sxs-lookup"><span data-stu-id="abf45-138">With Microsoft 365 Enterprise, you can customize the appearance of the sign-in and Access Panel pages so they include your company logo, color schemes, and custom user information.</span></span> 

<span data-ttu-id="abf45-139">Zie [Huisstijl van uw bedrijf toevoegen aan de aanmeldingspagina van Microsoft 365](https://docs.microsoft.com/office365/admin/setup/customize-sign-in-page) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="abf45-139">For more information, see [Add your company branding to Microsoft 365 Sign In page](https://docs.microsoft.com/office365/admin/setup/customize-sign-in-page).</span></span>

<span data-ttu-id="abf45-140">Zie [Huisstijl van uw bedrijf toevoegen aan de aanmeldings- en toegangspagina’s](https://aka.ms/aadpaddbranding) voor configuratie-instructies.</span><span class="sxs-lookup"><span data-stu-id="abf45-140">For configuration instructions, see [Add company branding to your sign-in and Access Panel pages](https://aka.ms/aadpaddbranding).</span></span>

<span data-ttu-id="abf45-141">Als tussentijds controlepunt kunt u de [afsluitcriteria](identity-exit-criteria.md#crit-identity-custom-sign-in) voor deze sectie bekijken.</span><span class="sxs-lookup"><span data-stu-id="abf45-141">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-custom-sign-in) for this section.</span></span>

## <a name="next-step"></a><span data-ttu-id="abf45-142">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="abf45-142">Next step</span></span>

|||
|:-------|:-----|
|![Stap 3](../media/stepnumbers/Step3.png)| [<span data-ttu-id="abf45-144">Gebruikersaanmeldingen beveiligen en beheren</span><span class="sxs-lookup"><span data-stu-id="abf45-144">Secure and manage your user sign-ins</span></span>](identity-secure-user-sign-ins.md) |
