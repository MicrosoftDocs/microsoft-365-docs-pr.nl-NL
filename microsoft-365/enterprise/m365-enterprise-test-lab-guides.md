---
title: Microsoft 365 Enterprise-testlabrichtlijnen
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/20/2019
audience: ITPro
ms.topic: hub-page
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: Gebruik de volgende testlabrichtlijnen voor het instellen van een demonstratie, testen van concept of ontwikkelomgevingen voor Microsoft 365 Enterprise.
ms.openlocfilehash: fefbb18fd108dceba6f387fb8244619c4bb1c167
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487468"
---
# <a name="microsoft-365-for-enterprise-test-lab-guides"></a><span data-ttu-id="70a65-103">Microsoft 365 Enterprise-testlabrichtlijnen</span><span class="sxs-lookup"><span data-stu-id="70a65-103">Microsoft 365 for enterprise Test Lab Guides</span></span>

<span data-ttu-id="70a65-104">*Dit is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="70a65-104">*This applies to both Microsoft 365 for enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="70a65-105">Met testlabrichtlijnen (TLG's) kunt u snel meer informatie krijgen over Microsoft-producten.</span><span class="sxs-lookup"><span data-stu-id="70a65-105">Test Lab Guides (TLGs) help you quickly learn about Microsoft products.</span></span> <span data-ttu-id="70a65-106">Zij bieden instructies voor het configureren van vereenvoudigde maar representatieve testomgevingen.</span><span class="sxs-lookup"><span data-stu-id="70a65-106">They provide prescriptive instructions to configure simplified but representative test environments.</span></span> <span data-ttu-id="70a65-107">U kunt deze omgevingen gebruiken voor demonstratie, aanpassing of het maken van complexe testconcepten voor de duur van een proefabonnement of een betaald abonnement.</span><span class="sxs-lookup"><span data-stu-id="70a65-107">You can use these environments for demonstration, customization, or creation of complex proofs of concept for the duration of a trial or paid subscription.</span></span>

<span data-ttu-id="70a65-108">TLG's zijn modulair ontworpen.</span><span class="sxs-lookup"><span data-stu-id="70a65-108">TLGs are designed to be modular.</span></span> <span data-ttu-id="70a65-109">Ze zijn op elkaar gebaseerd voor het maken van meerdere configuraties die beter aansluiten bij de behoeften van uw leer- en testconfiguratie.</span><span class="sxs-lookup"><span data-stu-id="70a65-109">They build upon each other to create multiple configurations that more closely match your learning or test configuration needs.</span></span> <span data-ttu-id="70a65-110">De "Ik heb het zelf opgebouwd en het werkt op een praktische manier, zodat u inzicht krijgt in de implementatievereisten van een nieuw product of scenario, zodat u beter kunt nagaan of het hosten van de productie verloopt.</span><span class="sxs-lookup"><span data-stu-id="70a65-110">The "I built it out myself and it works" hands-on experience helps you understand the deployment requirements of a new product or scenario, so that you can better plan for hosting it in production.</span></span>

<span data-ttu-id="70a65-111">U kunt Tlg's ook gebruiken om representatieve omgevingen te maken om toepassingen te ontwikkelen en testen, ook wel bekend als ontwikkelomgevingen.</span><span class="sxs-lookup"><span data-stu-id="70a65-111">You can also use TLGs to create representative environments to develop and test applications, also known as dev/test environments.</span></span>
  
![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

<span data-ttu-id="70a65-113">Voor een visuele kaart voor alle artikelen in de Microsoft 365 for Enterprise test lab Guide, vouwt u de volgende afbeelding uit of gaat u naar de [stack Microsoft 365 voor Enterprise test lab Guide](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="70a65-113">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, expand the following graphic or go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

<span data-ttu-id="70a65-114">[![Microsoft 365 Enterprise-testlabrichtlijnen-stack](../media/m365-enterprise-test-lab-guides/microsoft-365-enterprise-tlg-stack.png)](../downloads/Microsoft365EnterpriseTLGStack.pdf)</span><span class="sxs-lookup"><span data-stu-id="70a65-114">[![The Microsoft 365 for enterprise Test Lab Guide stack](../media/m365-enterprise-test-lab-guides/microsoft-365-enterprise-tlg-stack.png)](../downloads/Microsoft365EnterpriseTLGStack.pdf)</span></span>

## <a name="base-configuration"></a><span data-ttu-id="70a65-115">Basisconfiguratie</span><span class="sxs-lookup"><span data-stu-id="70a65-115">Base configuration</span></span>

<span data-ttu-id="70a65-116">Maak eerst een testomgeving voor [Microsoft 365 for Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/).</span><span class="sxs-lookup"><span data-stu-id="70a65-116">First, create a test environment for [Microsoft 365 for enterprise](https://docs.microsoft.com/microsoft-365-enterprise/).</span></span> <span data-ttu-id="70a65-117">U kunt twee soorten basisconfiguraties maken:</span><span class="sxs-lookup"><span data-stu-id="70a65-117">You can create two different types of base configurations:</span></span>

- <span data-ttu-id="70a65-118">[Configuratie van lichtgewicht](lightweight-base-configuration-microsoft-365-enterprise.md) functies: gebruik deze als u microsoft 365 wilt configureren en demonstreren voor Enterprise-functies en mogelijkheden in een omgeving met Cloud only, dat geen on-premises onderdelen bevat.</span><span class="sxs-lookup"><span data-stu-id="70a65-118">[Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md) - Use this when you want to configure and demonstrate Microsoft 365 for enterprise features and capabilities in a cloud-only environment, which does not include any on-premises components.</span></span>

- <span data-ttu-id="70a65-119">[Gesimuleerde Enterprise Base configuration](simulated-ent-base-configuration-microsoft-365-enterprise.md) : gebruik deze als u microsoft 365 wilt configureren en demonstreren voor Enterprise-functies en mogelijkheden in een hybride cloudomgeving, waarbij on-premises onderdelen worden gebruikt, zoals een AD DS-domein (Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="70a65-119">[Simulated enterprise base configuration](simulated-ent-base-configuration-microsoft-365-enterprise.md) - Use this when you want to configure and demonstrate Microsoft 365 for enterprise features and capabilities in a hybrid cloud environment, which uses on-premises components such as an Active Directory Domain Services (AD DS) domain.</span></span>

<span data-ttu-id="70a65-120">U kunt ook testomgevingen voor Office 365 E5 maken door niet de Microsoft 365 E5-licentie toe te voegen aan uw proefabonnement of productietestomgeving.</span><span class="sxs-lookup"><span data-stu-id="70a65-120">You can also create test environments for Office 365 E5 by not adding the Microsoft 365 E5 license to your trial or production test environment.</span></span>
    
## <a name="identity"></a><span data-ttu-id="70a65-121">Identiteit</span><span class="sxs-lookup"><span data-stu-id="70a65-121">Identity</span></span>

<span data-ttu-id="70a65-122">Zie voor meer informatie over identiteiten en functionaliteit:</span><span class="sxs-lookup"><span data-stu-id="70a65-122">To demonstrate identity-related features and capabilities, see:</span></span>

- [<span data-ttu-id="70a65-123">Wachtwoord-hash-synchronisatie</span><span class="sxs-lookup"><span data-stu-id="70a65-123">Password hash synchronization</span></span>](password-hash-sync-m365-ent-test-environment.md)
  
   <span data-ttu-id="70a65-124">Wachtwoord-hash-synchronisatie inschakelen en testen vanuit een AD DS-domeincontroller.</span><span class="sxs-lookup"><span data-stu-id="70a65-124">Enable and test password hash-based directory synchronization from an AD DS domain controller.</span></span>

- [<span data-ttu-id="70a65-125">Pass-through-verificatie</span><span class="sxs-lookup"><span data-stu-id="70a65-125">Pass-through authentication</span></span>](pass-through-auth-m365-ent-test-environment.md)
  
   <span data-ttu-id="70a65-126">Pass-through-verificatie inschakelen en testen vanuit een AD DS-domeincontroller.</span><span class="sxs-lookup"><span data-stu-id="70a65-126">Enable and test pass-through authentication to an AD DS domain controller.</span></span>

- [<span data-ttu-id="70a65-127">Federatieve verificatie</span><span class="sxs-lookup"><span data-stu-id="70a65-127">Federated authentication</span></span>](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
   <span data-ttu-id="70a65-128">Federatieve verificatie inschakelen en testen vanuit een AD DS-domeincontroller.</span><span class="sxs-lookup"><span data-stu-id="70a65-128">Enable and test federated authentication to an AD DS domain controller.</span></span>

- [<span data-ttu-id="70a65-129">Microsoft Azure Active Directory naadloze SSO</span><span class="sxs-lookup"><span data-stu-id="70a65-129">Azure AD Seamless Single Sign-on</span></span>](single-sign-on-m365-ent-test-environment.md)
  
   <span data-ttu-id="70a65-130">Azure AD naadloos eenmalige aanmelding (naadloze SSO) in-en testen met een AD DS-domeincontroller.</span><span class="sxs-lookup"><span data-stu-id="70a65-130">Enable and test Azure AD Seamless Single Sign-on (Seamless SSO) with an AD DS domain controller.</span></span>

- [<span data-ttu-id="70a65-131">Meervoudige verificatie</span><span class="sxs-lookup"><span data-stu-id="70a65-131">Multi-factor authentication</span></span>](multi-factor-authentication-microsoft-365-test-environment.md)
  
   <span data-ttu-id="70a65-132">Meervoudige verificatie op een smartphone inschakelen en testen voor een specifieke gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="70a65-132">Enable and test smart phone-based multi-factor authentication for a specific user account.</span></span>

- [<span data-ttu-id="70a65-133">Wereldwijde beheerdersaccounts beveiligen</span><span class="sxs-lookup"><span data-stu-id="70a65-133">Protect global administrator accounts</span></span>](protect-global-administrator-accounts-microsoft-365-test-environment.md)

   <span data-ttu-id="70a65-134">Vergrendel uw wereldwijde beheerdersaccounts met voorwaardelijke toegangsbeleid.</span><span class="sxs-lookup"><span data-stu-id="70a65-134">Lock down your global administrator accounts with conditional access policies.</span></span>

- [<span data-ttu-id="70a65-135">Wachtwoord write-back</span><span class="sxs-lookup"><span data-stu-id="70a65-135">Password writeback</span></span>](password-writeback-m365-ent-test-environment.md)

   <span data-ttu-id="70a65-136">Wachtwoord write-back gebruiken om het wachtwoord van uw AD DS-gebruikersaccount in Microsoft Azure Active Directory te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="70a65-136">Use password writeback to change the password on your AD DS user account from Azure AD.</span></span>

- [<span data-ttu-id="70a65-137">Wachtwoordherstel</span><span class="sxs-lookup"><span data-stu-id="70a65-137">Password reset</span></span>](password-reset-m365-ent-test-environment.md)

   <span data-ttu-id="70a65-138">Selfservice voor wachtwoordherstel gebruiken om uw wachtwoord opnieuw in te stellen.</span><span class="sxs-lookup"><span data-stu-id="70a65-138">Use self-service password reset to reset your password.</span></span>

- [<span data-ttu-id="70a65-139">Automatische licentie en groepslidmaatschap</span><span class="sxs-lookup"><span data-stu-id="70a65-139">Automatic licensing and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md)

   <span data-ttu-id="70a65-140">Het beheren van nieuwe accounts is eenvoudiger dan ooit dankzij automatische licentieverlening en dynamisch groepslidmaatschap.</span><span class="sxs-lookup"><span data-stu-id="70a65-140">Make administering new accounts easier than ever with automatic licensing and dynamic group membership.</span></span>

- [<span data-ttu-id="70a65-141">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="70a65-141">Azure AD Identity Protection</span></span>](azure-ad-identity-protection-microsoft-365-test-environment.md)

   <span data-ttu-id="70a65-142">Uw huidige gebruikersaccounts scannen op beveiligingsproblemen.</span><span class="sxs-lookup"><span data-stu-id="70a65-142">Scan your current user accounts for vulnerabilities.</span></span>

- [<span data-ttu-id="70a65-143">Identiteit en apparaattoegang</span><span class="sxs-lookup"><span data-stu-id="70a65-143">Identity and device access</span></span>](identity-device-access-m365-test-environment.md)

   <span data-ttu-id="70a65-144">Een omgeving maken voor het testen van aanbevolen identiteits- en toegangsconfiguraties en regels voor voorwaardelijke toegang.</span><span class="sxs-lookup"><span data-stu-id="70a65-144">Create an environment to test recommended identity and device access configurations and conditional access policies.</span></span>

## <a name="mobile-device-management"></a><span data-ttu-id="70a65-145">Mobile Device Management</span><span class="sxs-lookup"><span data-stu-id="70a65-145">Mobile device management</span></span>

<span data-ttu-id="70a65-146">Zie voor meer informatie over de functies en functionaliteiten van Mobile Device Management:</span><span class="sxs-lookup"><span data-stu-id="70a65-146">To demonstrate mobile device management-related features and capabilities, see:</span></span>

- [<span data-ttu-id="70a65-147">Nalevingsbeleid voor apparaten</span><span class="sxs-lookup"><span data-stu-id="70a65-147">Device compliance policies</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="70a65-148">Een gebruikersgroep en nalevingsbeleid voor Windows 10-apparaten maken.</span><span class="sxs-lookup"><span data-stu-id="70a65-148">Create a user group and a device compliance policy for Windows 10 devices.</span></span>
    
- [<span data-ttu-id="70a65-149">IOS- en Android-apparaten registreren</span><span class="sxs-lookup"><span data-stu-id="70a65-149">Enroll iOS and Android devices</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
   
   <span data-ttu-id="70a65-150">IOS- of Android-apparaten inschrijven en deze extern beheren.</span><span class="sxs-lookup"><span data-stu-id="70a65-150">Enroll iOS or Android devices and manage them remotely.</span></span>

## <a name="information-protection"></a><span data-ttu-id="70a65-151">Gegevensbeveiliging</span><span class="sxs-lookup"><span data-stu-id="70a65-151">Information protection</span></span>

<span data-ttu-id="70a65-152">Zie voor meer informatie over beveiligingsfuncties en -functionaliteiten:</span><span class="sxs-lookup"><span data-stu-id="70a65-152">To demonstrate information protection-related features and capabilities, see:</span></span>

- [<span data-ttu-id="70a65-153">Verbeterde Microsoft 365-beveiliging</span><span class="sxs-lookup"><span data-stu-id="70a65-153">Increased Microsoft 365 security</span></span>](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="70a65-154">Instellingen configureren voor verbeterde Microsoft 365-beveiliging en ingebouwde beveiligingshulpprogramma's onderzoeken.</span><span class="sxs-lookup"><span data-stu-id="70a65-154">Configure settings for increased Microsoft 365 security and investigate built-in security tools.</span></span>
  
- [<span data-ttu-id="70a65-155">Gegevensclassificatie</span><span class="sxs-lookup"><span data-stu-id="70a65-155">Data classification</span></span>](data-classification-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="70a65-156">Labels op een document op een SharePoint Online-team site configureren en toepassen.</span><span class="sxs-lookup"><span data-stu-id="70a65-156">Configure and apply labels to a document in a SharePoint Online team site.</span></span>
    
- [<span data-ttu-id="70a65-157">Privileged Access Management</span><span class="sxs-lookup"><span data-stu-id="70a65-157">Privileged access management</span></span>](privileged-access-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="70a65-158">Privileged Access Management configureren voor just-in-time-toegang tot verhoogde en bevoegde taken in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="70a65-158">Configure privileged access management for just-in-time access to elevated and privileged tasks in your organization.</span></span>
