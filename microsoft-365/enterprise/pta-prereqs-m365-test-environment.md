---
title: Vereisten voor identiteits- en apparaattoegang voor pass-through-verificatie in uw Microsoft 365-testomgeving.
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 12/12/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Maak een Microsoft 365-omgeving voor het testen van identiteits- en apparaattoegang met de vereisten voor pass-through-verificatie.
ms.openlocfilehash: f9f5fd8f235787512d59b29dc06b080bc9cfa0ff
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42807309"
---
# <a name="identity-and-device-access-prerequisites-for-pass-through-authentication-in-your-microsoft-365-test-environment"></a><span data-ttu-id="efc5b-103">Vereisten voor identiteits- en apparaattoegang voor pass-through-verificatie in uw Microsoft 365-testomgeving.</span><span class="sxs-lookup"><span data-stu-id="efc5b-103">Identity and device access prerequisites for pass-through authentication in your Microsoft 365 test environment</span></span>

<span data-ttu-id="efc5b-104">*Deze testlabrichtlijn kan alleen worden gebruikt voor Microsoft 365 Enterprise-testomgevingen.*</span><span class="sxs-lookup"><span data-stu-id="efc5b-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="efc5b-105">[Configuraties voor identiteits- en apparaattoegang](microsoft-365-policies-configurations.md) is een set configuraties en beleid voor voorwaardelijke toegang om de toegang tot alle services te beveiligen die zijn geïntegreerd met Azure Active Directory (Azure AD), met inbegrip van Office 365 en Enterprise Mobility + Security (EMS) in Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="efc5b-105">[Identity and device access configurations](microsoft-365-policies-configurations.md) are a set of configurations and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD), including Office 365 and Enterprise Mobility + Security (EMS) in Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="efc5b-106">In dit artikel wordt beschreven hoe u een Microsoft 365-testomgeving kunt configureren die voldoet aan de vereisten van de [configuratie voor pass-through-verificatie](identity-access-prerequisites.md#prerequisites) voor identiteits- en apparaattoegang.</span><span class="sxs-lookup"><span data-stu-id="efc5b-106">This article describes how you can configure a Microsoft 365 test environment that meets the requirements of the [Pass-through authentication prerequisite configuration](identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span>

<span data-ttu-id="efc5b-107">Er zijn acht fasen om deze testomgeving in te stellen:</span><span class="sxs-lookup"><span data-stu-id="efc5b-107">There are eight phases to setting up this test environment:</span></span>

1.  <span data-ttu-id="efc5b-108">Uw gesimuleerde Enterprise uitbreiden met een Microsoft 365-testomgeving met pass-through-verificatie</span><span class="sxs-lookup"><span data-stu-id="efc5b-108">Build out your simulated enterprise with pass-through authentication Microsoft 365 test environment</span></span>
2.  <span data-ttu-id="efc5b-109">Naadloze eenmalige Azure AD-aanmelding configureren</span><span class="sxs-lookup"><span data-stu-id="efc5b-109">Configure Azure AD seamless single sign-on</span></span>
3.  <span data-ttu-id="efc5b-110">Benoemde locaties configureren</span><span class="sxs-lookup"><span data-stu-id="efc5b-110">Configure named locations</span></span>
4.  <span data-ttu-id="efc5b-111">Wachtwoord terugschrijven configureren</span><span class="sxs-lookup"><span data-stu-id="efc5b-111">Configure password writeback</span></span>
5.  <span data-ttu-id="efc5b-112">Self-service voor wachtwoordherstel configureren</span><span class="sxs-lookup"><span data-stu-id="efc5b-112">Configure self-service password reset</span></span>
6.  <span data-ttu-id="efc5b-113">Meervoudige verificatie configureren</span><span class="sxs-lookup"><span data-stu-id="efc5b-113">Configure multifactor authentication</span></span>
7.  <span data-ttu-id="efc5b-114">Azure AD Identity Protection inschakelen</span><span class="sxs-lookup"><span data-stu-id="efc5b-114">Enable Azure AD Identity Protection</span></span>
8.  <span data-ttu-id="efc5b-115">Moderne verificatie inschakelen voor Exchange Online en Skype voor Bedrijven Online</span><span class="sxs-lookup"><span data-stu-id="efc5b-115">Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

## <a name="phase-1-build-out-your-simulated-enterprise-with-pass-through-authentication-microsoft-365-test-environment"></a><span data-ttu-id="efc5b-116">Fase 1: Uw gesimuleerde Enterprise uitbreiden met een Microsoft 365-testomgeving met pass-through-verificatie</span><span class="sxs-lookup"><span data-stu-id="efc5b-116">Phase 1: Build out your simulated enterprise with pass-through authentication Microsoft 365 test environment</span></span>

<span data-ttu-id="efc5b-117">Volg de instructies in [Pass-through-verificatie](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="efc5b-117">Follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>

<span data-ttu-id="efc5b-118">Dit is de resulterende configuratie.</span><span class="sxs-lookup"><span data-stu-id="efc5b-118">Here is the resulting configuration.</span></span>

![De gesimuleerde Enterprise met een testomgeving met pass-through-verificatie](../media/pass-through-auth-m365-ent-test-environment/Phase2.png)
 
## <a name="phase-2-configure-azure-ad-seamless-single-sign-on"></a><span data-ttu-id="efc5b-120">Fase 2: Naadloze eenmalige Azure AD-aanmelding configureren</span><span class="sxs-lookup"><span data-stu-id="efc5b-120">Phase 2: Configure Azure AD seamless single sign-on</span></span>

<span data-ttu-id="efc5b-121">Volg de instructies in [Fase 2 van testlabrichtlijn Naadloze eenmalige Azure AD-aanmelding](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso).</span><span class="sxs-lookup"><span data-stu-id="efc5b-121">Follow the instructions in [Phase 2 of the Azure AD Seamless Single Sign-on Test Lab Guide](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso).</span></span>

## <a name="phase-3-configure-named-locations"></a><span data-ttu-id="efc5b-122">Fase 3: Benoemde locaties configureren</span><span class="sxs-lookup"><span data-stu-id="efc5b-122">Phase 3: Configure named locations</span></span>

<span data-ttu-id="efc5b-123">Bepaal eerst de openbare IP-adressen of adresbereiken die worden gebruikt door uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="efc5b-123">First, determine the public IP addresses or address ranges used by your organization.</span></span>

<span data-ttu-id="efc5b-124">Volg daarna de instructies in [Benoemde locaties configureren in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) om de adressen of adresbereiken als benoemde locaties toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="efc5b-124">Next, follow the instructions in [Configure named locations in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) to add the addresses or address ranges as named locations.</span></span> 

## <a name="phase-4-configure-password-writeback"></a><span data-ttu-id="efc5b-125">Fase 4: Wachtwoord terugschrijven configureren</span><span class="sxs-lookup"><span data-stu-id="efc5b-125">Phase 4: Configure password writeback</span></span>

<span data-ttu-id="efc5b-126">Volg de instructies in [Fase 2 van testlabrichtlijn Wachtwoord terugschrijven](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span><span class="sxs-lookup"><span data-stu-id="efc5b-126">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

## <a name="phase-5-configure-self-service-password-reset"></a><span data-ttu-id="efc5b-127">Fase 5: Self-service voor wachtwoordherstel configureren</span><span class="sxs-lookup"><span data-stu-id="efc5b-127">Phase 5: Configure self-service password reset</span></span>

<span data-ttu-id="efc5b-128">Volg de instructies in [Fase 3 van testlabrichtlijn Wachtwoordherstel](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span><span class="sxs-lookup"><span data-stu-id="efc5b-128">Follow the instructions in [Phase 3 of the password reset Test Lab Guide](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span></span> 

<span data-ttu-id="efc5b-129">Wanneer u wachtwoordherstel inschakelt voor de accounts in een specifieke Azure AD-groep, voegt u deze accounts toe aan de groep **Wachtwoord opnieuw instellen**:</span><span class="sxs-lookup"><span data-stu-id="efc5b-129">When enabling password reset for the accounts in a specific Azure AD group, add these accounts to the **Password reset** group:</span></span>

- <span data-ttu-id="efc5b-130">Gebruiker 2</span><span class="sxs-lookup"><span data-stu-id="efc5b-130">User 2</span></span>
- <span data-ttu-id="efc5b-131">Gebruiker 3</span><span class="sxs-lookup"><span data-stu-id="efc5b-131">User 3</span></span>
- <span data-ttu-id="efc5b-132">Gebruiker 4</span><span class="sxs-lookup"><span data-stu-id="efc5b-132">User 4</span></span>
- <span data-ttu-id="efc5b-133">Gebruiker 5</span><span class="sxs-lookup"><span data-stu-id="efc5b-133">User 5</span></span>

<span data-ttu-id="efc5b-134">Test wachtwoordherstel alleen voor het Gebruiker 2-account.</span><span class="sxs-lookup"><span data-stu-id="efc5b-134">Test password reset only for the User 2 account.</span></span>

## <a name="phase-6-configure-multi-factor-authentication"></a><span data-ttu-id="efc5b-135">Fase 6: Meervoudige verificatie configureren</span><span class="sxs-lookup"><span data-stu-id="efc5b-135">Phase 6: Configure multi-factor authentication</span></span>

<span data-ttu-id="efc5b-136">Volg de instructies in [Fase 2 van testlabrichtlijn Meervoudige verificatie](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) voor de volgende gebruikersaccounts:</span><span class="sxs-lookup"><span data-stu-id="efc5b-136">Follow the instructions in [Phase 2 of the multi-factor authentication Test Lab Guide](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) for the following user accounts:</span></span>

- <span data-ttu-id="efc5b-137">Gebruiker 2</span><span class="sxs-lookup"><span data-stu-id="efc5b-137">User 2</span></span>
- <span data-ttu-id="efc5b-138">Gebruiker 3</span><span class="sxs-lookup"><span data-stu-id="efc5b-138">User 3</span></span>
- <span data-ttu-id="efc5b-139">Gebruiker 4</span><span class="sxs-lookup"><span data-stu-id="efc5b-139">User 4</span></span>
- <span data-ttu-id="efc5b-140">Gebruiker 5</span><span class="sxs-lookup"><span data-stu-id="efc5b-140">User 5</span></span>

<span data-ttu-id="efc5b-141">Test meervoudige verificatie alleen voor het Gebruiker 2-account.</span><span class="sxs-lookup"><span data-stu-id="efc5b-141">Test multi-factor authentication only for the User 2 account.</span></span>

## <a name="phase-7-enable-azure-ad-identity-protection"></a><span data-ttu-id="efc5b-142">Fase 7: Azure AD Identity Protection inschakelen</span><span class="sxs-lookup"><span data-stu-id="efc5b-142">Phase 7: Enable Azure AD Identity Protection</span></span>

<span data-ttu-id="efc5b-143">Volg de instructies in [Fase 2 van testlabrichtlijn Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection).</span><span class="sxs-lookup"><span data-stu-id="efc5b-143">Follow the instructions in [Phase 2 of the Azure AD Identity Protection Test Lab Guide](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection).</span></span> 

## <a name="phase-8-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="efc5b-144">Fase 8: Moderne verificatie inschakelen voor Exchange Online en Skype voor Bedrijven Online</span><span class="sxs-lookup"><span data-stu-id="efc5b-144">Phase 8: Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="efc5b-145">Volg voor Exchange Online [deze instructies](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span><span class="sxs-lookup"><span data-stu-id="efc5b-145">For Exchange Online, follow [these instructions](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span></span> 

<span data-ttu-id="efc5b-146">Voor Skype voor Bedrijven Online:</span><span class="sxs-lookup"><span data-stu-id="efc5b-146">For Skype for Business Online:</span></span>

1. <span data-ttu-id="efc5b-147">Maak verbinding met [Skype voor Bedrijven Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="efc5b-147">Connect to [Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

2. <span data-ttu-id="efc5b-148">Voer deze opdracht uit.</span><span class="sxs-lookup"><span data-stu-id="efc5b-148">Run this command.</span></span>

  ```powershell
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. <span data-ttu-id="efc5b-149">Controleer of het wijzigen met behulp van deze opdracht is gelukt.</span><span class="sxs-lookup"><span data-stu-id="efc5b-149">Verify that the change was successful with this command.</span></span>

  ```powershell
  Get-CsOAuthConfiguration
  ```

<span data-ttu-id="efc5b-150">Het resultaat is een testomgeving die voldoet aan de vereisten van de [vereiste configuratie van pass-through-verificatie](identity-access-prerequisites.md#prerequisites) voor identiteits- en apparaattoegang.</span><span class="sxs-lookup"><span data-stu-id="efc5b-150">The result is a test environment that meets the requirements of the [Pass-through authentication prerequisite configuration](identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span> 

## <a name="next-step"></a><span data-ttu-id="efc5b-151">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="efc5b-151">Next step</span></span>

<span data-ttu-id="efc5b-152">Gebruik [algemeen beleid voor identiteits- en apparaattoegang](identity-access-policies.md) voor het configureren van het beleid dat is gebaseerd op de vereisten, en bescherm identiteiten en apparaten.</span><span class="sxs-lookup"><span data-stu-id="efc5b-152">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites and protect identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="efc5b-153">Zie ook</span><span class="sxs-lookup"><span data-stu-id="efc5b-153">See also</span></span>

[<span data-ttu-id="efc5b-154">Aanvullende testlabrichtlijnen voor identiteit</span><span class="sxs-lookup"><span data-stu-id="efc5b-154">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="efc5b-155">Fase 2: Identiteit</span><span class="sxs-lookup"><span data-stu-id="efc5b-155">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="efc5b-156">Microsoft 365 Enterprise-testlabrichtlijnen</span><span class="sxs-lookup"><span data-stu-id="efc5b-156">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="efc5b-157">Microsoft 365 Enterprise-implementatie</span><span class="sxs-lookup"><span data-stu-id="efc5b-157">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="efc5b-158">Microsoft 365 Enterprise-documentatie</span><span class="sxs-lookup"><span data-stu-id="efc5b-158">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

