---
title: Vereisten voor identiteits- en apparaattoegang voor pass-through-verificatie in uw Microsoft 365-testomgeving.
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Maak een Microsoft 365-omgeving voor het testen van identiteits- en apparaattoegang met de vereisten voor pass-through-verificatie.
ms.openlocfilehash: 3d7b92bb064ee1b008ac98f836aff6e0287739af
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928998"
---
# <a name="identity-and-device-access-prerequisites-for-pass-through-authentication-in-your-microsoft-365-test-environment"></a><span data-ttu-id="fe29a-103">Vereisten voor identiteits- en apparaattoegang voor pass-through-verificatie in uw Microsoft 365-testomgeving.</span><span class="sxs-lookup"><span data-stu-id="fe29a-103">Identity and device access prerequisites for pass-through authentication in your Microsoft 365 test environment</span></span>

<span data-ttu-id="fe29a-104">*Deze testlaborator kan alleen worden gebruikt voor Microsoft 365 voor testomgevingen voor ondernemingen.*</span><span class="sxs-lookup"><span data-stu-id="fe29a-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="fe29a-105">[Configuraties voor identiteits-](../security/office-365-security/microsoft-365-policies-configurations.md) en apparaattoegang zijn een set configuraties en beleid voor voorwaardelijke toegang om de toegang tot alle services in Microsoft 365 voor ondernemingen te beschermen die zijn geïntegreerd met Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="fe29a-105">[Identity and device access configurations](../security/office-365-security/microsoft-365-policies-configurations.md) are a set of configurations and conditional access policies to protect access to all services in Microsoft 365 for enterprise that are integrated with Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="fe29a-106">In dit artikel wordt beschreven hoe u een Microsoft 365-testomgeving kunt configureren die voldoet aan de vereisten van de [configuratie voor pass-through-verificatie](../security/office-365-security/identity-access-prerequisites.md#prerequisites) voor identiteits- en apparaattoegang.</span><span class="sxs-lookup"><span data-stu-id="fe29a-106">This article describes how you can configure a Microsoft 365 test environment that meets the requirements of the [Pass-through authentication prerequisite configuration](../security/office-365-security/identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span>

<span data-ttu-id="fe29a-107">Er zijn tien fasen voor het instellen van deze testomgeving:</span><span class="sxs-lookup"><span data-stu-id="fe29a-107">There are ten phases to setting up this test environment:</span></span>

1. <span data-ttu-id="fe29a-108">Uw gesimuleerde Enterprise uitbreiden met een Microsoft 365-testomgeving met pass-through-verificatie</span><span class="sxs-lookup"><span data-stu-id="fe29a-108">Build out your simulated enterprise with pass-through authentication Microsoft 365 test environment</span></span>
2. <span data-ttu-id="fe29a-109">Naadloze eenmalige Azure AD-aanmelding configureren</span><span class="sxs-lookup"><span data-stu-id="fe29a-109">Configure Azure AD seamless single sign-on</span></span>
3. <span data-ttu-id="fe29a-110">Benoemde locaties configureren</span><span class="sxs-lookup"><span data-stu-id="fe29a-110">Configure named locations</span></span>
4. <span data-ttu-id="fe29a-111">Wachtwoord terugschrijven configureren</span><span class="sxs-lookup"><span data-stu-id="fe29a-111">Configure password writeback</span></span>
5. <span data-ttu-id="fe29a-112">Self-service voor wachtwoordherstel configureren</span><span class="sxs-lookup"><span data-stu-id="fe29a-112">Configure self-service password reset</span></span>
6. <span data-ttu-id="fe29a-113">Meervoudige verificatie configureren</span><span class="sxs-lookup"><span data-stu-id="fe29a-113">Configure multifactor authentication</span></span>
7. <span data-ttu-id="fe29a-114">Automatische apparaatregistratie van windows-computers met een domein inschakelen</span><span class="sxs-lookup"><span data-stu-id="fe29a-114">Enable automatic device registration of domain-joined Windows computers</span></span>
8. <span data-ttu-id="fe29a-115">Azure AD-wachtwoordbeveiliging configureren</span><span class="sxs-lookup"><span data-stu-id="fe29a-115">Configure Azure AD password protection</span></span> 
9. <span data-ttu-id="fe29a-116">Azure AD Identity Protection inschakelen</span><span class="sxs-lookup"><span data-stu-id="fe29a-116">Enable Azure AD Identity Protection</span></span>
10. <span data-ttu-id="fe29a-117">Moderne verificatie inschakelen voor Exchange Online en Skype voor Bedrijven Online</span><span class="sxs-lookup"><span data-stu-id="fe29a-117">Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

## <a name="phase-1-build-out-your-simulated-enterprise-with-pass-through-authentication-microsoft-365-test-environment"></a><span data-ttu-id="fe29a-118">Fase 1: Uw gesimuleerde Enterprise uitbreiden met een Microsoft 365-testomgeving met pass-through-verificatie</span><span class="sxs-lookup"><span data-stu-id="fe29a-118">Phase 1: Build out your simulated enterprise with pass-through authentication Microsoft 365 test environment</span></span>

<span data-ttu-id="fe29a-119">Volg de instructies in [Pass-through-verificatie](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="fe29a-119">Follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>

<span data-ttu-id="fe29a-120">Dit is de resulterende configuratie.</span><span class="sxs-lookup"><span data-stu-id="fe29a-120">Here is the resulting configuration.</span></span>

![De gesimuleerde Enterprise met een testomgeving met pass-through-verificatie](../media/pass-through-auth-m365-ent-test-environment/Phase2.png)
 
## <a name="phase-2-configure-azure-ad-seamless-single-sign-on"></a><span data-ttu-id="fe29a-122">Fase 2: Naadloze eenmalige Azure AD-aanmelding configureren</span><span class="sxs-lookup"><span data-stu-id="fe29a-122">Phase 2: Configure Azure AD seamless single sign-on</span></span>

<span data-ttu-id="fe29a-123">Volg de instructies in [Fase 2 van testlabrichtlijn Naadloze eenmalige Azure AD-aanmelding](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso).</span><span class="sxs-lookup"><span data-stu-id="fe29a-123">Follow the instructions in [Phase 2 of the Azure AD Seamless Single Sign-on Test Lab Guide](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso).</span></span>

## <a name="phase-3-configure-named-locations"></a><span data-ttu-id="fe29a-124">Fase 3: Benoemde locaties configureren</span><span class="sxs-lookup"><span data-stu-id="fe29a-124">Phase 3: Configure named locations</span></span>

<span data-ttu-id="fe29a-125">Bepaal eerst de openbare IP-adressen of adresbereiken die worden gebruikt door uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="fe29a-125">First, determine the public IP addresses or address ranges used by your organization.</span></span>

<span data-ttu-id="fe29a-126">Volg daarna de instructies in [Benoemde locaties configureren in Azure Active Directory](/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) om de adressen of adresbereiken als benoemde locaties toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="fe29a-126">Next, follow the instructions in [Configure named locations in Azure Active Directory](/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) to add the addresses or address ranges as named locations.</span></span> 

## <a name="phase-4-configure-password-writeback"></a><span data-ttu-id="fe29a-127">Fase 4: Wachtwoord terugschrijven configureren</span><span class="sxs-lookup"><span data-stu-id="fe29a-127">Phase 4: Configure password writeback</span></span>

<span data-ttu-id="fe29a-128">Volg de instructies in [Fase 2 van testlabrichtlijn Wachtwoord terugschrijven](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span><span class="sxs-lookup"><span data-stu-id="fe29a-128">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

## <a name="phase-5-configure-self-service-password-reset"></a><span data-ttu-id="fe29a-129">Fase 5: Self-service voor wachtwoordherstel configureren</span><span class="sxs-lookup"><span data-stu-id="fe29a-129">Phase 5: Configure self-service password reset</span></span>

<span data-ttu-id="fe29a-130">Volg de instructies in [Fase 3 van testlabrichtlijn Wachtwoordherstel](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span><span class="sxs-lookup"><span data-stu-id="fe29a-130">Follow the instructions in [Phase 3 of the password reset Test Lab Guide](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span></span> 

<span data-ttu-id="fe29a-131">Wanneer u wachtwoordherstel inschakelt voor de accounts in een specifieke Azure AD-groep, voegt u deze accounts toe aan de groep **Wachtwoord opnieuw instellen**:</span><span class="sxs-lookup"><span data-stu-id="fe29a-131">When enabling password reset for the accounts in a specific Azure AD group, add these accounts to the **Password reset** group:</span></span>

- <span data-ttu-id="fe29a-132">Gebruiker 2</span><span class="sxs-lookup"><span data-stu-id="fe29a-132">User 2</span></span>
- <span data-ttu-id="fe29a-133">Gebruiker 3</span><span class="sxs-lookup"><span data-stu-id="fe29a-133">User 3</span></span>
- <span data-ttu-id="fe29a-134">Gebruiker 4</span><span class="sxs-lookup"><span data-stu-id="fe29a-134">User 4</span></span>
- <span data-ttu-id="fe29a-135">Gebruiker 5</span><span class="sxs-lookup"><span data-stu-id="fe29a-135">User 5</span></span>

<span data-ttu-id="fe29a-136">Test wachtwoordherstel alleen voor het Gebruiker 2-account.</span><span class="sxs-lookup"><span data-stu-id="fe29a-136">Test password reset only for the User 2 account.</span></span>

## <a name="phase-6-configure-multi-factor-authentication"></a><span data-ttu-id="fe29a-137">Fase 6: Meervoudige verificatie configureren</span><span class="sxs-lookup"><span data-stu-id="fe29a-137">Phase 6: Configure multi-factor authentication</span></span>

<span data-ttu-id="fe29a-138">Volg de instructies in [Fase 2 van testlabrichtlijn Meervoudige verificatie](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) voor de volgende gebruikersaccounts:</span><span class="sxs-lookup"><span data-stu-id="fe29a-138">Follow the instructions in [Phase 2 of the multi-factor authentication Test Lab Guide](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) for the following user accounts:</span></span>

- <span data-ttu-id="fe29a-139">Gebruiker 2</span><span class="sxs-lookup"><span data-stu-id="fe29a-139">User 2</span></span>
- <span data-ttu-id="fe29a-140">Gebruiker 3</span><span class="sxs-lookup"><span data-stu-id="fe29a-140">User 3</span></span>
- <span data-ttu-id="fe29a-141">Gebruiker 4</span><span class="sxs-lookup"><span data-stu-id="fe29a-141">User 4</span></span>
- <span data-ttu-id="fe29a-142">Gebruiker 5</span><span class="sxs-lookup"><span data-stu-id="fe29a-142">User 5</span></span>

<span data-ttu-id="fe29a-143">Test meervoudige verificatie alleen voor het Gebruiker 2-account.</span><span class="sxs-lookup"><span data-stu-id="fe29a-143">Test multi-factor authentication only for the User 2 account.</span></span>

## <a name="phase-7-enable-automatic-device-registration-of-domain-joined-windows-computers"></a><span data-ttu-id="fe29a-144">Fase 7: Automatische apparaatregistratie van windows-computers met een domein inschakelen</span><span class="sxs-lookup"><span data-stu-id="fe29a-144">Phase 7: Enable automatic device registration of domain-joined Windows computers</span></span> 

<span data-ttu-id="fe29a-145">Volg [deze instructies om](/azure/active-directory/devices/hybrid-azuread-join-plan) automatische apparaatregistratie van windows-computers met een domein in te stellen.</span><span class="sxs-lookup"><span data-stu-id="fe29a-145">Follow [these instructions](/azure/active-directory/devices/hybrid-azuread-join-plan) to enable automatic device registration of domain-joined Windows computers.</span></span>

## <a name="phase-8-configure-azure-ad-password-protection"></a><span data-ttu-id="fe29a-146">Fase 8: Azure AD-wachtwoordbeveiliging configureren</span><span class="sxs-lookup"><span data-stu-id="fe29a-146">Phase 8: Configure Azure AD password protection</span></span> 

<span data-ttu-id="fe29a-147">Volg [deze instructies om](/azure/active-directory/authentication/concept-password-ban-bad) bekende zwakke wachtwoorden en hun varianten te blokkeren.</span><span class="sxs-lookup"><span data-stu-id="fe29a-147">Follow [these instructions](/azure/active-directory/authentication/concept-password-ban-bad) to block known weak passwords and their variants.</span></span>

## <a name="phase-9-enable-azure-ad-identity-protection"></a><span data-ttu-id="fe29a-148">Fase 9: Azure AD Identity Protection inschakelen</span><span class="sxs-lookup"><span data-stu-id="fe29a-148">Phase 9: Enable Azure AD Identity Protection</span></span>

<span data-ttu-id="fe29a-149">Volg de instructies in [Fase 2 van testlabrichtlijn Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection).</span><span class="sxs-lookup"><span data-stu-id="fe29a-149">Follow the instructions in [Phase 2 of the Azure AD Identity Protection Test Lab Guide](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection).</span></span> 

## <a name="phase-10-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="fe29a-150">Fase 10: Moderne verificatie inschakelen voor Exchange Online en Skype voor Bedrijven Online</span><span class="sxs-lookup"><span data-stu-id="fe29a-150">Phase 10: Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="fe29a-151">Volg voor Exchange Online [deze instructies](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span><span class="sxs-lookup"><span data-stu-id="fe29a-151">For Exchange Online, follow [these instructions](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span></span> 

<span data-ttu-id="fe29a-152">Voor Skype voor Bedrijven Online:</span><span class="sxs-lookup"><span data-stu-id="fe29a-152">For Skype for Business Online:</span></span>

1. <span data-ttu-id="fe29a-153">Maak verbinding met [Skype voor Bedrijven Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="fe29a-153">Connect to [Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

2. <span data-ttu-id="fe29a-154">Voer deze opdracht uit.</span><span class="sxs-lookup"><span data-stu-id="fe29a-154">Run this command.</span></span>

  ```powershell
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. <span data-ttu-id="fe29a-155">Controleer of het wijzigen met behulp van deze opdracht is gelukt.</span><span class="sxs-lookup"><span data-stu-id="fe29a-155">Verify that the change was successful with this command.</span></span>

  ```powershell
  Get-CsOAuthConfiguration
  ```

<span data-ttu-id="fe29a-156">Het resultaat is een testomgeving die voldoet aan de vereisten van de [vereiste configuratie van pass-through-verificatie](../security/office-365-security/identity-access-prerequisites.md#prerequisites) voor identiteits- en apparaattoegang.</span><span class="sxs-lookup"><span data-stu-id="fe29a-156">The result is a test environment that meets the requirements of the [Pass-through authentication prerequisite configuration](../security/office-365-security/identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span> 

## <a name="next-step"></a><span data-ttu-id="fe29a-157">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="fe29a-157">Next step</span></span>

<span data-ttu-id="fe29a-158">Gebruik [algemeen beleid voor identiteits- en apparaattoegang](../security/office-365-security/identity-access-policies.md) voor het configureren van het beleid dat is gebaseerd op de vereisten, en bescherm identiteiten en apparaten.</span><span class="sxs-lookup"><span data-stu-id="fe29a-158">Use [Common identity and device access policies](../security/office-365-security/identity-access-policies.md) to configure the policies that build on the prerequisites and protect identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="fe29a-159">Zie ook</span><span class="sxs-lookup"><span data-stu-id="fe29a-159">See also</span></span>

[<span data-ttu-id="fe29a-160">Aanvullende testlabrichtlijnen voor identiteit</span><span class="sxs-lookup"><span data-stu-id="fe29a-160">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="fe29a-161">Routekaart voor identiteit</span><span class="sxs-lookup"><span data-stu-id="fe29a-161">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="fe29a-162">Microsoft 365 Enterprise-testlabrichtlijnen</span><span class="sxs-lookup"><span data-stu-id="fe29a-162">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="fe29a-163">Overzicht van Microsoft 365 voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="fe29a-163">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="fe29a-164">Microsoft 365 enterprise-documentatie</span><span class="sxs-lookup"><span data-stu-id="fe29a-164">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)