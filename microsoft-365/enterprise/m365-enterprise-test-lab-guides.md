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
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: Gebruik de volgende testlabrichtlijnen voor het instellen van een demonstratie, testen van concept of ontwikkelomgevingen voor Microsoft 365 Enterprise.
ms.openlocfilehash: 4190eb4619f4732310786b5a7dde6bb590a969c1
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42805271"
---
# <a name="microsoft-365-for-enterprise-test-lab-guides"></a><span data-ttu-id="9a73a-103">Microsoft 365 Enterprise-testlabrichtlijnen</span><span class="sxs-lookup"><span data-stu-id="9a73a-103">Microsoft 365 for enterprise Test Lab Guides</span></span>

<span data-ttu-id="9a73a-104">*Dit is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="9a73a-104">*This applies to both Microsoft 365 for enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="9a73a-105">Met testlabrichtlijnen (TLG's) kunt u snel meer informatie krijgen over Microsoft-producten.</span><span class="sxs-lookup"><span data-stu-id="9a73a-105">Test Lab Guides (TLGs) help you quickly learn about Microsoft products.</span></span> <span data-ttu-id="9a73a-106">Zij bieden instructies voor het configureren van vereenvoudigde maar representatieve testomgevingen.</span><span class="sxs-lookup"><span data-stu-id="9a73a-106">They provide prescriptive instructions to configure simplified but representative test environments.</span></span> <span data-ttu-id="9a73a-107">U kunt deze omgevingen gebruiken voor demonstratie, aanpassing of het maken van complexe testconcepten voor de duur van een proefabonnement of een betaald abonnement.</span><span class="sxs-lookup"><span data-stu-id="9a73a-107">You can use these environments for demonstration, customization, or creation of complex proofs of concept for the duration of a trial or paid subscription.</span></span> 

<span data-ttu-id="9a73a-108">TLG's zijn modulair ontworpen.</span><span class="sxs-lookup"><span data-stu-id="9a73a-108">TLGs are designed to be modular.</span></span> <span data-ttu-id="9a73a-109">Ze zijn op elkaar gebaseerd voor het maken van meerdere configuraties die beter aansluiten bij de behoeften van uw leer- en testconfiguratie.</span><span class="sxs-lookup"><span data-stu-id="9a73a-109">They build upon each other to create multiple configurations that more closely match your learning or test configuration needs.</span></span> <span data-ttu-id="9a73a-110">De 'Ik heb het zelf gebouwd en het werkt'-praktijkervaring helpt u om inzicht te krijgen in de implementatievereisten van een nieuw product of scenario. Hiermee kunt u zich beter voorbereiden voor het hosten in productie.</span><span class="sxs-lookup"><span data-stu-id="9a73a-110">The "I built it out myself and it works" hands-on experience helps you understand the deployment requirements of a new product or scenario so you can better plan for hosting it in production.</span></span>

<span data-ttu-id="9a73a-111">U kunt TLG's ook gebruiken om representatieve omgevingen te maken voor het ontwikkelen en testen van toepassingen, ook wel bekend als ontwikkel-/testomgevingen.</span><span class="sxs-lookup"><span data-stu-id="9a73a-111">You can also use TLGs to create representative environments for development and testing of applications, also known as dev/test environments.</span></span>
  
![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

<span data-ttu-id="9a73a-113">Klik op [Hier](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) voor een visuele kaart voor alle artikelen in de stack van Microsoft 365 voor Enterprise-testlabrichtlijnen.</span><span class="sxs-lookup"><span data-stu-id="9a73a-113">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>

<span data-ttu-id="9a73a-114">[![Microsoft 365 Enterprise-testlabrichtlijnen-stack](../media/m365-enterprise-test-lab-guides/microsoft-365-enterprise-tlg-stack.png)](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)</span><span class="sxs-lookup"><span data-stu-id="9a73a-114">[![The Microsoft 365 for enterprise Test Lab Guide stack](../media/m365-enterprise-test-lab-guides/microsoft-365-enterprise-tlg-stack.png)](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)</span></span>

## <a name="base-configuration"></a><span data-ttu-id="9a73a-115">Basisconfiguratie</span><span class="sxs-lookup"><span data-stu-id="9a73a-115">Base configuration</span></span>

<span data-ttu-id="9a73a-116">Eerst maakt u een testomgeving voor [Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/) waarin Office 365 Enterprise E5, Enterprise Mobility + Security (EMS) E5 en Windows 10 Enterprise zijn opgenomen.</span><span class="sxs-lookup"><span data-stu-id="9a73a-116">First, you create a test environment for [Microsoft 365 for enterprise](https://docs.microsoft.com/microsoft-365-enterprise/) that includes Office 365 E5, Enterprise Mobility + Security (EMS) E5, and Windows 10 Enterprise.</span></span> <span data-ttu-id="9a73a-117">U kunt twee soorten basisconfiguraties maken:</span><span class="sxs-lookup"><span data-stu-id="9a73a-117">You can create two different types of base configurations:</span></span>

- <span data-ttu-id="9a73a-118">Gebruik de [lichtgewicht basisconfiguratie](lightweight-base-configuration-microsoft-365-enterprise.md) als u Microsoft 365 wilt configureren en demonstreren voor Enterprise-functies en-functionaliteit in een cloudomgeving die geen on-premises onderdelen bevat.</span><span class="sxs-lookup"><span data-stu-id="9a73a-118">Use the [lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md) when you want to configure and demonstrate Microsoft 365 for enterprise features and capabilities in a cloud-only environment, which does not include any on-premises components.</span></span>

- <span data-ttu-id="9a73a-119">Gebruik de [gesimuleerde Enterprise basisconfiguratie](simulated-ent-base-configuration-microsoft-365-enterprise.md) als u Microsoft 365 wilt configureren en demonstreren voor Enterprise-functies en-functionaliteit in een hybride cloudomgeving, die gebruikmaakt van on-premises onderdelen, zoals een Active Directory Domain Services-domein (AD DS).</span><span class="sxs-lookup"><span data-stu-id="9a73a-119">Use the [simulated enterprise base configuration](simulated-ent-base-configuration-microsoft-365-enterprise.md) when you want to configure and demonstrate Microsoft 365 for enterprise features and capabilities in a hybrid cloud environment, which uses on-premises components such as an Active Directory Domain Services (AD DS) domain.</span></span>

<span data-ttu-id="9a73a-120">U kunt ook testomgevingen voor Office 365 E5 maken door niet de Microsoft 365 E5-licentie toe te voegen aan uw proefabonnement of productietestomgeving.</span><span class="sxs-lookup"><span data-stu-id="9a73a-120">You can also create test environments for Office 365 E5 by not adding the Microsoft 365 E5 license to your trial or production test environment.</span></span>
    
## <a name="identity"></a><span data-ttu-id="9a73a-121">Identiteit</span><span class="sxs-lookup"><span data-stu-id="9a73a-121">Identity</span></span>

<span data-ttu-id="9a73a-122">Zie voor meer informatie over identiteiten en functionaliteit:</span><span class="sxs-lookup"><span data-stu-id="9a73a-122">To demonstrate identity-related features and capabilities, see:</span></span>

- [<span data-ttu-id="9a73a-123">Wachtwoord-hash-synchronisatie</span><span class="sxs-lookup"><span data-stu-id="9a73a-123">Password hash synchronization</span></span>](password-hash-sync-m365-ent-test-environment.md)
  
   <span data-ttu-id="9a73a-124">Wachtwoord-hash-synchronisatie inschakelen en testen vanuit een AD DS-domeincontroller.</span><span class="sxs-lookup"><span data-stu-id="9a73a-124">Enable and test password hash-based directory synchronization from an AD DS domain controller.</span></span>

- [<span data-ttu-id="9a73a-125">Pass-through-verificatie</span><span class="sxs-lookup"><span data-stu-id="9a73a-125">Pass-through authentication</span></span>](pass-through-auth-m365-ent-test-environment.md)
  
   <span data-ttu-id="9a73a-126">Pass-through-verificatie inschakelen en testen vanuit een AD DS-domeincontroller.</span><span class="sxs-lookup"><span data-stu-id="9a73a-126">Enable and test pass-through authentication to an AD DS domain controller.</span></span>

- [<span data-ttu-id="9a73a-127">Federatieve verificatie</span><span class="sxs-lookup"><span data-stu-id="9a73a-127">Federated authentication</span></span>](federated-identity-for-your-office-365-dev-test-environment.md)
  
   <span data-ttu-id="9a73a-128">Federatieve verificatie inschakelen en testen vanuit een AD DS-domeincontroller.</span><span class="sxs-lookup"><span data-stu-id="9a73a-128">Enable and test federated authentication to an AD DS domain controller.</span></span>

- [<span data-ttu-id="9a73a-129">Microsoft Azure Active Directory naadloze SSO</span><span class="sxs-lookup"><span data-stu-id="9a73a-129">Azure AD Seamless Single Sign-on</span></span>](single-sign-on-m365-ent-test-environment.md)
  
   <span data-ttu-id="9a73a-130">Microsoft Azure Active Directory naadloze SSO inschakelen en testen vanuit een AD DS-domeincontroller.</span><span class="sxs-lookup"><span data-stu-id="9a73a-130">Enable and test Azure AD Seamless Single Sign-on (SSO) with an AD DS domain controller.</span></span>

- [<span data-ttu-id="9a73a-131">Meervoudige verificatie</span><span class="sxs-lookup"><span data-stu-id="9a73a-131">Multi-factor authentication</span></span>](multi-factor-authentication-microsoft-365-test-environment.md)
  
   <span data-ttu-id="9a73a-132">Meervoudige verificatie op een smartphone inschakelen en testen voor een specifieke gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="9a73a-132">Enable and test smart phone-based multi-factor authentication for a specific user account.</span></span>

- [<span data-ttu-id="9a73a-133">Wereldwijde beheerdersaccounts beveiligen</span><span class="sxs-lookup"><span data-stu-id="9a73a-133">Protect global administrator accounts</span></span>](protect-global-administrator-accounts-microsoft-365-test-environment.md)
 
   <span data-ttu-id="9a73a-134">Vergrendel uw wereldwijde beheerdersaccounts met voorwaardelijke toegangsbeleid.</span><span class="sxs-lookup"><span data-stu-id="9a73a-134">Lock down your global administrator accounts with conditional access policies.</span></span>

- [<span data-ttu-id="9a73a-135">Wachtwoord write-back</span><span class="sxs-lookup"><span data-stu-id="9a73a-135">Password writeback</span></span>](password-writeback-m365-ent-test-environment.md)

   <span data-ttu-id="9a73a-136">Wachtwoord write-back gebruiken om het wachtwoord van uw AD DS-gebruikersaccount in Microsoft Azure Active Directory te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="9a73a-136">Use password writeback to change the password on your AD DS user account from Azure AD.</span></span>

- [<span data-ttu-id="9a73a-137">Wachtwoordherstel</span><span class="sxs-lookup"><span data-stu-id="9a73a-137">Password reset</span></span>](password-reset-m365-ent-test-environment.md)

   <span data-ttu-id="9a73a-138">Selfservice wachtwoordherstel (SSPR) gebruiken voor het herstellen van uw wachtwoord.</span><span class="sxs-lookup"><span data-stu-id="9a73a-138">Use self-service password reset (SSPR) to reset your password.</span></span>

- [<span data-ttu-id="9a73a-139">Automatische licentie en groepslidmaatschap</span><span class="sxs-lookup"><span data-stu-id="9a73a-139">Automatic licensing and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md)

   <span data-ttu-id="9a73a-140">Het beheren van nieuwe accounts is eenvoudiger dan ooit dankzij automatische licentieverlening en dynamisch groepslidmaatschap.</span><span class="sxs-lookup"><span data-stu-id="9a73a-140">Make administering new accounts easier than ever with automatic licensing and dynamic group membership.</span></span>

- [<span data-ttu-id="9a73a-141">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="9a73a-141">Azure AD Identity Protection</span></span>](azure-ad-identity-protection-microsoft-365-test-environment.md)

   <span data-ttu-id="9a73a-142">Uw huidige gebruikersaccounts scannen op beveiligingsproblemen.</span><span class="sxs-lookup"><span data-stu-id="9a73a-142">Scan your current user accounts for vulnerabilities.</span></span>

- [<span data-ttu-id="9a73a-143">Identiteit en apparaattoegang</span><span class="sxs-lookup"><span data-stu-id="9a73a-143">Identity and device access</span></span>](identity-device-access-m365-test-environment.md)

   <span data-ttu-id="9a73a-144">Een omgeving maken voor het testen van aanbevolen identiteits- en toegangsconfiguraties en regels voor voorwaardelijke toegang.</span><span class="sxs-lookup"><span data-stu-id="9a73a-144">Create an environment to test recommended identity and device access configurations and conditional access policies.</span></span>


## <a name="mobile-device-management"></a><span data-ttu-id="9a73a-145">Mobile Device Management</span><span class="sxs-lookup"><span data-stu-id="9a73a-145">Mobile device management</span></span>

<span data-ttu-id="9a73a-146">Zie voor meer informatie over de functies en functionaliteiten van Mobile Device Management:</span><span class="sxs-lookup"><span data-stu-id="9a73a-146">To demonstrate mobile device management-related features and capabilities, see:</span></span>

- [<span data-ttu-id="9a73a-147">Nalevingsbeleid voor apparaten</span><span class="sxs-lookup"><span data-stu-id="9a73a-147">Device compliance policies</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="9a73a-148">Een gebruikersgroep en nalevingsbeleid voor Windows 10-apparaten maken.</span><span class="sxs-lookup"><span data-stu-id="9a73a-148">Create a user group and a device compliance policy for Windows 10 devices.</span></span>
    
- [<span data-ttu-id="9a73a-149">IOS- en Android-apparaten registreren</span><span class="sxs-lookup"><span data-stu-id="9a73a-149">Enroll iOS and Android devices</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
   
   <span data-ttu-id="9a73a-150">IOS- of Android-apparaten inschrijven en deze extern beheren.</span><span class="sxs-lookup"><span data-stu-id="9a73a-150">Enroll iOS or Android devices and manage them remotely.</span></span>


## <a name="information-protection"></a><span data-ttu-id="9a73a-151">Gegevensbeveiliging</span><span class="sxs-lookup"><span data-stu-id="9a73a-151">Information protection</span></span>

<span data-ttu-id="9a73a-152">Zie voor meer informatie over beveiligingsfuncties en -functionaliteiten:</span><span class="sxs-lookup"><span data-stu-id="9a73a-152">To demonstrate information protection-related features and capabilities, see:</span></span>

- [<span data-ttu-id="9a73a-153">Verbeterde Office 365-beveiliging</span><span class="sxs-lookup"><span data-stu-id="9a73a-153">Increased Office 365 security</span></span>](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="9a73a-154">Instellingen configureren voor verbeterde Office 365-beveiliging en ingebouwde beveiligingshulpprogramma's onderzoeken.</span><span class="sxs-lookup"><span data-stu-id="9a73a-154">Configure settings for increased Office 365 security and investigate built-in security tools.</span></span>
  
- [<span data-ttu-id="9a73a-155">Gegevensclassificatie</span><span class="sxs-lookup"><span data-stu-id="9a73a-155">Data classification</span></span>](data-classification-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="9a73a-156">Office 365-labels op een document op een SharePoint Online-team site configureren en toepassen.</span><span class="sxs-lookup"><span data-stu-id="9a73a-156">Configure and apply Office 365 labels to a document in a SharePoint Online team site.</span></span>
    
- [<span data-ttu-id="9a73a-157">Privileged Access Management</span><span class="sxs-lookup"><span data-stu-id="9a73a-157">Privileged access management</span></span>](privileged-access-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="9a73a-158">Privileged Access Management configureren voor just-in-time-toegang tot verhoogde en bevoegde taken in uw Office 365-organisatie.</span><span class="sxs-lookup"><span data-stu-id="9a73a-158">Configure privileged access management for just-in-time access to elevated and privileged tasks in your Office 365 organization.</span></span>


