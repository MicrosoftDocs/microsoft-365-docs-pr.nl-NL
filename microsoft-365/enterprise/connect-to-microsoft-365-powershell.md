---
title: Verbinding maken met Microsoft 365 met PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- LIL_Placement
- O365ITProTrain
- Ent_Office_Other
ms.assetid: 5ebc0e21-b72d-46d8-96fa-00643b18eaec
description: Maak verbinding met je Microsoft 365-tenant via PowerShell voor Microsoft 365 om Beheercentrum-taken vanaf de opdrachtregel uit te voeren.
ms.openlocfilehash: 33f9af45418ae8a1f126d2b321e7246201bd1f6e
ms.sourcegitcommit: f07442d077eb4357fa5d99d051b035705eb30efa
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/12/2020
ms.locfileid: "49002403"
---
# <a name="connect-to-microsoft-365-with-powershell"></a><span data-ttu-id="1036b-103">Verbinding maken met Microsoft 365 met PowerShell</span><span class="sxs-lookup"><span data-stu-id="1036b-103">Connect to Microsoft 365 with PowerShell</span></span>

<span data-ttu-id="1036b-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="1036b-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="1036b-105">Met PowerShell voor Microsoft 365 kun je de instellingen van Microsoft 365 beheren vanaf de opdrachtregel.</span><span class="sxs-lookup"><span data-stu-id="1036b-105">PowerShell for Microsoft 365 enables you to manage your Microsoft 365 settings from the command line.</span></span> <span data-ttu-id="1036b-106">Als je verbinding wilt maken met PowerShell, installeer je gewoon de vereiste software en maak je verbinding met je Microsoft 365-organisatie.</span><span class="sxs-lookup"><span data-stu-id="1036b-106">To connect to PowerShell, just install the required software and then connect to your Microsoft 365 organization.</span></span>

<span data-ttu-id="1036b-107">Er zijn twee versies van de PowerShell-module die je kunt gebruiken om verbinding te maken met Microsoft 365 en gebruikersaccounts, groepen en licenties te beheren:</span><span class="sxs-lookup"><span data-stu-id="1036b-107">There are two versions of the PowerShell module that you can use to connect to Microsoft 365 and administer user accounts, groups, and licenses:</span></span>

- <span data-ttu-id="1036b-108">Azure Active Directory PowerShell voor Graph, waarvan de cmdlets *AzureAD* in de naam hebben</span><span class="sxs-lookup"><span data-stu-id="1036b-108">Azure Active Directory PowerShell for Graph, whose cmdlets include *AzureAD* in their name</span></span>
- <span data-ttu-id="1036b-109">Microsoft Azure Active Directory-module voor Windows PowerShell, waarvan cmdlets *MSol* in de naam hebben</span><span class="sxs-lookup"><span data-stu-id="1036b-109">Microsoft Azure Active Directory Module for Windows PowerShell, whose cmdlets include *Msol* in their name</span></span>

<span data-ttu-id="1036b-110">Momenteel vervangt de module Azure Active Directory PowerShell voor Graph nog niet alle functionaliteit van de Microsoft Azure Active Directory-module voor Windows PowerShell voor het beheer van gebruikers, groepen en licenties.</span><span class="sxs-lookup"><span data-stu-id="1036b-110">Currently, the Azure Active Directory PowerShell for Graph module doesn't completely replace the functionality of the Microsoft Azure Active Directory Module for Windows PowerShell module for user, group, and license administration.</span></span> <span data-ttu-id="1036b-111">In sommige gevallen moet je beide versies gebruiken.</span><span class="sxs-lookup"><span data-stu-id="1036b-111">In some cases, you need to use both versions.</span></span> <span data-ttu-id="1036b-112">Je kunt beide versies veilig op dezelfde computer installeren.</span><span class="sxs-lookup"><span data-stu-id="1036b-112">You can safely install both versions on the same computer.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="1036b-113">Wat moet je weten voordat je begint?</span><span class="sxs-lookup"><span data-stu-id="1036b-113">What do you need to know before you begin?</span></span>


<span data-ttu-id="1036b-114">**Besturingssysteem**</span><span class="sxs-lookup"><span data-stu-id="1036b-114">**Operating system**</span></span>

<span data-ttu-id="1036b-115">Je moet een 64-bits versie van Windows gebruiken.</span><span class="sxs-lookup"><span data-stu-id="1036b-115">You must use a 64-bit version of Windows.</span></span> <span data-ttu-id="1036b-116">Ondersteuning voor de 32-bits versie van de Microsoft Azure Active Directory-module voor Windows PowerShell is in 2014 beëindigd.</span><span class="sxs-lookup"><span data-stu-id="1036b-116">Support for the 32-bit version of the Microsoft Azure Active Directory Module for Windows PowerShell ended in 2014.</span></span>

<span data-ttu-id="1036b-117">Je kunt de volgende versies van Windows gebruiken:</span><span class="sxs-lookup"><span data-stu-id="1036b-117">You can use the following versions of Windows:</span></span>
    
  - <span data-ttu-id="1036b-118">Windows 10, Windows 8.1, Windows 8 of Windows 7 Service Pack 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="1036b-118">Windows 10, Windows 8.1, Windows 8, or Windows 7 Service Pack 1 (SP1)</span></span> 
    
  - <span data-ttu-id="1036b-119">Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012 of Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="1036b-119">Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012, or Windows Server 2008 R2 SP1</span></span>

>[!Note]
><span data-ttu-id="1036b-120">Voor Windows 8.1, Windows 8, Windows 7 Service Pack 1 (SP1), Windows Server 2012 R2, Windows Server 2012 en Windows Server 2008 R2 SP1 kun je het [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616) downloaden en installeren.</span><span class="sxs-lookup"><span data-stu-id="1036b-120">For Windows 8.1, Windows 8, Windows 7 Service Pack 1 (SP1), Windows Server 2012 R2, Windows Server 2012, and Windows Server 2008 R2 SP1, download and install the [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616).</span></span>

<span data-ttu-id="1036b-121">**PowerShell**</span><span class="sxs-lookup"><span data-stu-id="1036b-121">**PowerShell**</span></span>

- <span data-ttu-id="1036b-122">Voor de module Azure Active Directory PowerShell voor Graph moet je PowerShell versie 5.1 of hoger gebruiken.</span><span class="sxs-lookup"><span data-stu-id="1036b-122">For the Azure Active Directory PowerShell for Graph module, you must use PowerShell version 5.1 or later.</span></span>

- <span data-ttu-id="1036b-123">Voor de Microsoft Azure Active Directory-module voor Windows PowerShell moet je PowerShell versie 5.1 of hoger gebruiken, tot PowerShell versie 6.</span><span class="sxs-lookup"><span data-stu-id="1036b-123">For the Microsoft Azure Active Directory Module for Windows PowerShell module, you must use PowerShell version 5.1 or later, up to PowerShell version 6.</span></span> <span data-ttu-id="1036b-124">PowerShell versie 7 kan niet worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="1036b-124">You can't use PowerShell version 7.</span></span>
       
>[!Note]
><span data-ttu-id="1036b-125">Deze procedures zijn bedoeld voor gebruikers die lid zijn van een Microsoft 365-beheerdersrol.</span><span class="sxs-lookup"><span data-stu-id="1036b-125">These procedures are intended for users who are members of a Microsoft 365 admin role.</span></span> <span data-ttu-id="1036b-126">Raadpleeg [Over beheerdersrollen](https://go.microsoft.com/fwlink/p/?LinkId=532367) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="1036b-126">For more information, see [About admin roles](https://go.microsoft.com/fwlink/p/?LinkId=532367).</span></span>


## <a name="connect-with-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="1036b-127">Maak verbinding met de Azure Active Directory PowerShell voor Graph-module.</span><span class="sxs-lookup"><span data-stu-id="1036b-127">Connect with the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="1036b-128">Opdrachten in de module Azure Active Directory PowerShell voor Graph hebben *AzureAD* in de naam van de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1036b-128">Commands in the Azure Active Directory PowerShell for Graph module have *AzureAD* in their cmdlet name.</span></span> <span data-ttu-id="1036b-129">Je kunt de module [Azure Active Directory PowerShell voor Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) of [Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-az-ps) installeren.</span><span class="sxs-lookup"><span data-stu-id="1036b-129">You can install the [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) module or [Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-az-ps).</span></span>

<span data-ttu-id="1036b-130">Voer de volgende stappen uit om de module te installeren en verbinding te maken met je Microsoft 365-abonnement voor procedures waarvoor de nieuwe cmdlets in de module Azure Active Directory PowerShell voor Graph zijn vereist.</span><span class="sxs-lookup"><span data-stu-id="1036b-130">For procedures that require the new cmdlets in the Azure Active Directory PowerShell for Graph module, follow these steps to install the module and connect to your Microsoft 365 subscription.</span></span>

> [!Note]
> <span data-ttu-id="1036b-131">Zie [Module Azure Active Directory PowerShell voor Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) voor informatie over de ondersteuning voor verschillende versies van Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="1036b-131">For information about support for different versions of Windows, see [Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) .</span></span>

### <a name="step-1-install-the-required-software"></a><span data-ttu-id="1036b-132">Stap 1:Installeer de vereiste software</span><span class="sxs-lookup"><span data-stu-id="1036b-132">Step 1: Install the required software</span></span>

<span data-ttu-id="1036b-133">Deze stappen hoef je maar één keer uit te voeren op je computer.</span><span class="sxs-lookup"><span data-stu-id="1036b-133">These steps are required only one time on your computer.</span></span> <span data-ttu-id="1036b-134">Maar waarschijnlijk moet je de software regelmatig bijwerken.</span><span class="sxs-lookup"><span data-stu-id="1036b-134">But you'll likely need to update the software periodically.</span></span>
  
1. <span data-ttu-id="1036b-135">Open een Windows PowerShell-opdrachtprompt met verhoogde bevoegdheid (voer Windows PowerShell uit als beheerder).</span><span class="sxs-lookup"><span data-stu-id="1036b-135">Open an elevated Windows PowerShell Command Prompt window (run Windows PowerShell as an administrator).</span></span>
    
2. <span data-ttu-id="1036b-136">Voer de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="1036b-136">Run this command:</span></span>
    
    ```powershell
    Install-Module -Name AzureAD
    ```

   <span data-ttu-id="1036b-137">Als je wordt gevraagd een module te installeren vanuit een niet-vertrouwde opslagplaats, typ je **Y** en druk je op Enter.</span><span class="sxs-lookup"><span data-stu-id="1036b-137">If you're prompted to install a module from an untrusted repository, type **Y** and press Enter.</span></span>

### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a><span data-ttu-id="1036b-138">Stap 2: Maak verbinding met Azure AD voor jouw Microsoft 365-abonnement</span><span class="sxs-lookup"><span data-stu-id="1036b-138">Step 2: Connect to Azure AD for your Microsoft 365 subscription</span></span>

<span data-ttu-id="1036b-139">Als je verbinding wilt maken met Azure Active Directory (Azure AD) voor jouw Microsoft 365-abonnement met een accountnaam en wachtwoord of met meervoudige verificatie, voer je een van de volgende opdrachten uit vanaf een Windows PowerShell-opdrachtprompt.</span><span class="sxs-lookup"><span data-stu-id="1036b-139">To connect to Azure Active Directory (Azure AD) for your Microsoft 365 subscription with an account name and password or with multi-factor authentication, run one of these commands from a Windows PowerShell command prompt.</span></span> <span data-ttu-id="1036b-140">(Deze hoeft geen verhoogde bevoegdheid te hebben.)</span><span class="sxs-lookup"><span data-stu-id="1036b-140">(It doesn't have to be elevated.)</span></span>

| <span data-ttu-id="1036b-141">Office 365-cloud</span><span class="sxs-lookup"><span data-stu-id="1036b-141">Office 365 cloud</span></span> | <span data-ttu-id="1036b-142">Opdracht</span><span class="sxs-lookup"><span data-stu-id="1036b-142">Command</span></span> |
|:-------|:-----|
| <span data-ttu-id="1036b-143">Office 365 wereldwijd (+ GCC)</span><span class="sxs-lookup"><span data-stu-id="1036b-143">Office 365 Worldwide (+GCC)</span></span> | `Connect-AzureAD` |
| <span data-ttu-id="1036b-144">Office 365 beheerd door 21 Vianet</span><span class="sxs-lookup"><span data-stu-id="1036b-144">Office 365 operated by 21 Vianet</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureChinaCloud` |
| <span data-ttu-id="1036b-145">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="1036b-145">Office 365 Germany</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureGermanyCloud` |
| <span data-ttu-id="1036b-146">Office 365 U.S. Government DoD en Office 365 U.S. Government GCC High</span><span class="sxs-lookup"><span data-stu-id="1036b-146">Office 365 U.S. Government DoD and Office 365 U.S. Government GCC High</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureUSGovernment` |
|||

<span data-ttu-id="1036b-147">Typ de gebruikersnaam en het wachtwoord voor jouw werk- of schoolaccount van Microsoft 365 in het dialoogvenster **Aanmelden bij uw account** en selecteer vervolgens **OK**.</span><span class="sxs-lookup"><span data-stu-id="1036b-147">In the **Sign into your account** dialog box, type your Microsoft 365 work or school account user name and password, and then select **OK**.</span></span>

<span data-ttu-id="1036b-148">Als je meervoudige verificatie gebruikt, volg je de instructies om aanvullende verificatiegegevens op te geven, zoals een verificatiecode.</span><span class="sxs-lookup"><span data-stu-id="1036b-148">If you're using multi-factor authentication, follow the instructions to provide additional authentication information, such as a verification code.</span></span>

<span data-ttu-id="1036b-149">Nadat je verbinding hebt gemaakt, kun je de cmdlets voor de [module Azure Active Directory PowerShell voor Graph](https://docs.microsoft.com/powershell/module/azuread) gebruiken.</span><span class="sxs-lookup"><span data-stu-id="1036b-149">After you connect, you can use the cmdlets for the [Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/powershell/module/azuread).</span></span>

## <a name="connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="1036b-150">Maak verbinding met de Microsoft Azure Active Directory-module voor Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1036b-150">Connect with the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

>[!Note]
><span data-ttu-id="1036b-151">Cmdlets in de Microsoft Azure Active Directory-module voor Windows PowerShell hebben *MSol* in de naam.</span><span class="sxs-lookup"><span data-stu-id="1036b-151">Cmdlets in the Microsoft Azure Active Directory Module for Windows PowerShell have *Msol* in their name.</span></span>

<span data-ttu-id="1036b-152">PowerShell versie 7 biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell en cmdlets met *Msol* in de naam.</span><span class="sxs-lookup"><span data-stu-id="1036b-152">PowerShell version 7 and later don't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="1036b-153">Voor PowerShell versie 7 en hoger moet je de module Azure Active Directory PowerShell voor Graph gebruiken.</span><span class="sxs-lookup"><span data-stu-id="1036b-153">For PowerShell version 7 and later, you must use the Azure Active Directory PowerShell for Graph module or Azure PowerShell.</span></span>

<span data-ttu-id="1036b-154">PowerShell Core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell en cmdlets met *Msol* in hun naam.</span><span class="sxs-lookup"><span data-stu-id="1036b-154">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="1036b-155">Voer deze cmdlets uit vanuit Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1036b-155">Run these cmdlets from Windows PowerShell.</span></span>
    
### <a name="step-1-install-the-required-software"></a><span data-ttu-id="1036b-156">Stap 1:Installeer de vereiste software</span><span class="sxs-lookup"><span data-stu-id="1036b-156">Step 1: Install the required software</span></span>

<span data-ttu-id="1036b-157">Deze stappen hoef je maar één keer uit te voeren op je computer.</span><span class="sxs-lookup"><span data-stu-id="1036b-157">These steps are required only one time on your computer.</span></span> <span data-ttu-id="1036b-158">Maar waarschijnlijk moet je de software regelmatig bijwerken.</span><span class="sxs-lookup"><span data-stu-id="1036b-158">But you'll likely need to update the software periodically.</span></span>
  
1.  <span data-ttu-id="1036b-159">Als je geen Windows 10 gebruikt, installeer je de 64-bits versie van de Microsoft Online Services-aanmeldhulp: [Microsoft Online Services-aanmeldhulp voor IT-professionals RTW](https://go.microsoft.com/fwlink/p/?LinkId=286152).</span><span class="sxs-lookup"><span data-stu-id="1036b-159">If you're not running Windows 10, install the 64-bit version of the Microsoft Online Services Sign-in Assistant: [Microsoft Online Services Sign-in Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/p/?LinkId=286152).</span></span>
    
2. <span data-ttu-id="1036b-160">Installeer de Microsoft Azure Active Directory-module voor Windows PowerShell met deze stappen:</span><span class="sxs-lookup"><span data-stu-id="1036b-160">Follow these steps to install the Microsoft Azure Active Directory Module for Windows PowerShell:</span></span>
    
   1. <span data-ttu-id="1036b-161">Open een verhoogde Windows PowerShell-opdrachtprompt (Voer Windows PowerShell uit als beheerder).</span><span class="sxs-lookup"><span data-stu-id="1036b-161">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an administrator).</span></span>
   1.  <span data-ttu-id="1036b-162">Voer de **installatie-module MSOnline** uit.</span><span class="sxs-lookup"><span data-stu-id="1036b-162">Run the **Install-Module MSOnline** command.</span></span>
   1. <span data-ttu-id="1036b-163">Als je wordt gevraagd om de NuGet-provider te installeren, typ je **Y** en druk je op Enter.</span><span class="sxs-lookup"><span data-stu-id="1036b-163">If you're prompted to install the NuGet provider, type **Y** and press Enter.</span></span>
   1. <span data-ttu-id="1036b-164">Als je wordt gevraagd om de module van PSGallery te installeren, typ je **Y** en druk je op Enter.</span><span class="sxs-lookup"><span data-stu-id="1036b-164">If you're prompted to install the module from PSGallery, type **Y** and press Enter.</span></span>
    
### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a><span data-ttu-id="1036b-165">Stap 2: Maak verbinding met Azure AD voor jouw Microsoft 365-abonnement</span><span class="sxs-lookup"><span data-stu-id="1036b-165">Step 2: Connect to Azure AD for your Microsoft 365 subscription</span></span>

<span data-ttu-id="1036b-166">Om verbinding te maken met Azure AD voor jouw Microsoft 365-abonnement met een accountnaam en wachtwoord of met meervoudige verificatie, voer je een van de volgende opdrachten uit vanaf een Windows PowerShell-opdrachtprompt.</span><span class="sxs-lookup"><span data-stu-id="1036b-166">To connect to Azure AD for your Microsoft 365 subscription with an account name and password or with multi-factor authentication, run one of these commands from a Windows PowerShell command prompt.</span></span> <span data-ttu-id="1036b-167">(Deze hoeft geen verhoogde bevoegdheid te hebben.)</span><span class="sxs-lookup"><span data-stu-id="1036b-167">(It doesn't have to be elevated.)</span></span>

| <span data-ttu-id="1036b-168">Office 365-cloud</span><span class="sxs-lookup"><span data-stu-id="1036b-168">Office 365 cloud</span></span> | <span data-ttu-id="1036b-169">Opdracht</span><span class="sxs-lookup"><span data-stu-id="1036b-169">Command</span></span> |
|:-------|:-----|
| <span data-ttu-id="1036b-170">Office 365 wereldwijd (+ GCC)</span><span class="sxs-lookup"><span data-stu-id="1036b-170">Office 365 Worldwide (+GCC)</span></span> | `Connect-MsolService` |
| <span data-ttu-id="1036b-171">Office 365 beheerd door 21 Vianet</span><span class="sxs-lookup"><span data-stu-id="1036b-171">Office 365 operated by 21 Vianet</span></span> | `Connect-MsolService -AzureEnvironment AzureChinaCloud` |
| <span data-ttu-id="1036b-172">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="1036b-172">Office 365 Germany</span></span> | `Connect-MsolService -AzureEnvironment AzureGermanyCloud` |
| <span data-ttu-id="1036b-173">Office 365 U.S. Government DoD en Office 365 U.S. Government GCC High</span><span class="sxs-lookup"><span data-stu-id="1036b-173">Office 365 U.S. Government DoD and Office 365 U.S. Government GCC High</span></span> | `Connect-MsolService -AzureEnvironment USGovernment` |
|||

<span data-ttu-id="1036b-174">Typ de gebruikersnaam en het wachtwoord voor jouw werk- of schoolaccount van Microsoft 365 in het dialoogvenster **Aanmelden bij uw account** en selecteer vervolgens **OK**.</span><span class="sxs-lookup"><span data-stu-id="1036b-174">In the **Sign into your account** dialog box, type your Microsoft 365 work or school account user name and password, and then select **OK**.</span></span>

<span data-ttu-id="1036b-175">Als je meervoudige verificatie gebruikt, volg je de instructies om aanvullende verificatiegegevens op te geven, zoals een verificatiecode.</span><span class="sxs-lookup"><span data-stu-id="1036b-175">If you're using multi-factor authentication, follow the instructions to provide additional authentication information, such as a verification code.</span></span>

### <a name="how-do-you-know-it-worked"></a><span data-ttu-id="1036b-176">Hoe weet ik dat het werkt?</span><span class="sxs-lookup"><span data-stu-id="1036b-176">How do you know it worked?</span></span>

<span data-ttu-id="1036b-177">Als je geen foutmelding krijgt, ben je verbonden.</span><span class="sxs-lookup"><span data-stu-id="1036b-177">If you don't get an error message, you connected successfully.</span></span> <span data-ttu-id="1036b-178">Een snelle test is het uitvoeren van een Microsoft 365-cmdlet, bijvoorbeeld **Get-MsolUser** , en bekijk de resultaten.</span><span class="sxs-lookup"><span data-stu-id="1036b-178">For quick test,  run a Microsoft 365 cmdlet, such as  **Get-MsolUser** , and see the results.</span></span>
  
<span data-ttu-id="1036b-179">Als er een foutbericht wordt weergegeven, controleer je de volgende problemen:</span><span class="sxs-lookup"><span data-stu-id="1036b-179">If you get an error message, check the following issues:</span></span>
  
- <span data-ttu-id="1036b-180">**Een veelvoorkomend probleem is een onjuist wachtwoord**.</span><span class="sxs-lookup"><span data-stu-id="1036b-180">**A common problem is an incorrect password**.</span></span> <span data-ttu-id="1036b-181">Voer [stap 2](#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) opnieuw uit en let goed op de gebruikersnaam en het wachtwoord die je invoert.</span><span class="sxs-lookup"><span data-stu-id="1036b-181">Run [Step 2](#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) again, and pay close attention to the user name and password that you enter.</span></span>
    
- <span data-ttu-id="1036b-182">**De Microsoft Azure Active Directory-module voor Windows PowerShell vereist dat Microsoft .NET Framework 3.5.* x* is ingeschakeld op de computer**. Op je computer is waarschijnlijk een nieuwere versie geïnstalleerd (bijvoorbeeld 4 of 4.5.* x*).</span><span class="sxs-lookup"><span data-stu-id="1036b-182">**The Microsoft Azure Active Directory Module for Windows PowerShell requires that Microsoft .NET Framework 3.5.* x* is enabled on your computer**. It's likely that your computer has a newer version installed (for example, 4 or 4.5.* x*).</span></span> <span data-ttu-id="1036b-183">Maar compatibiliteit met eerdere versies van .NET Framework kan worden ingeschakeld of uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="1036b-183">But backward compatibility with older versions of the .NET Framework can be enabled or disabled.</span></span> <span data-ttu-id="1036b-184">Zie de volgende artikelen voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="1036b-184">For more information, see the following articles:</span></span>
    
  - <span data-ttu-id="1036b-185">Zie voor Windows Server 2012 of Windows Server 2012 R2 [.NET Framework 3.5 inschakelen met behulp van de wizard Functies en onderdelen toevoegen](https://go.microsoft.com/fwlink/p/?LinkId=532368).</span><span class="sxs-lookup"><span data-stu-id="1036b-185">For Windows Server 2012 or Windows Server 2012 R2, see [Enable .NET Framework 3.5 by using the Add Roles and Features Wizard](https://go.microsoft.com/fwlink/p/?LinkId=532368).</span></span>
    
  - <span data-ttu-id="1036b-186">Zie voor Windows 7 of Windows Server 2008 R2 [Je kunt de module Azure Active Directory voor Windows PowerShell niet openen](https://go.microsoft.com/fwlink/p/?LinkId=532370).</span><span class="sxs-lookup"><span data-stu-id="1036b-186">For Windows 7 or Windows Server 2008 R2, see [You can't open the Azure Active Directory Module for Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=532370).</span></span>

  - <span data-ttu-id="1036b-187">Zie voor Windows 10, Windows 8.1 en Windows 8 [.NET Framework 3.5 installeren in Windows 10, Windows 8.1 en Windows 8](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10)</span><span class="sxs-lookup"><span data-stu-id="1036b-187">For Windows 10, Windows 8.1, and Windows 8, see [Install the .NET Framework 3.5 on Windows 10, Windows 8.1, and Windows 8](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10).</span></span>

  
- <span data-ttu-id="1036b-188">**Jouw versie van de module Microsoft Azure Active Directory voor Windows PowerShell is mogelijk verouderd.**</span><span class="sxs-lookup"><span data-stu-id="1036b-188">**Your version of the Microsoft Azure Active Directory Module for Windows PowerShell might be out of date.**</span></span> <span data-ttu-id="1036b-189">Als je dit wilt controleren, voer je de volgende opdracht uit in PowerShell voor Microsoft 365 of de Microsoft Azure Active Directory-module voor Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="1036b-189">To check, run the following command in PowerShell for Microsoft 365 or the Microsoft Azure Active Directory Module for Windows PowerShell:</span></span>
    
  ```powershell
  (Get-Item C:\Windows\System32\WindowsPowerShell\v1.0\Modules\MSOnline\Microsoft.Online.Administration.Automation.PSModule.dll).VersionInfo.FileVersion
  ```

    <span data-ttu-id="1036b-190">Als het geretourneerde versienummer lager is dan de waarde *1.0.8070.2* , verwijder je de Microsoft Azure Active Directory-module voor Windows PowerShell en installeer je deze vanuit [Stap 1](#step-1-install-the-required-software) hierboven.</span><span class="sxs-lookup"><span data-stu-id="1036b-190">If the version number returned is lower than *1.0.8070.2* , uninstall the Microsoft Azure Active Directory Module for Windows PowerShell and install from [Step 1](#step-1-install-the-required-software), above.</span></span>

- <span data-ttu-id="1036b-191">**Als je een verbindingsfoutbericht krijgt** , raadpleeg je [Foutbericht 'Connect-MsolService: Exception of type was thrown'](https://go.microsoft.com/fwlink/p/?LinkId=532377).</span><span class="sxs-lookup"><span data-stu-id="1036b-191">**If you get a connection error message** , see ["Connect-MsolService: Exception of type was thrown" error](https://go.microsoft.com/fwlink/p/?LinkId=532377).</span></span>
    
- <span data-ttu-id="1036b-192">**Als je de foutmelding 'Get-Item: Cannot find path' krijgt** , voer je de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="1036b-192">**If you get a "Get-Item: Cannot find path" error message** , run this command:</span></span>


   ```powershell
     (dir "C:\Program Files\WindowsPowerShell\Modules\MSOnline").Name
   ```

## <a name="see-also"></a><span data-ttu-id="1036b-193">Zie ook</span><span class="sxs-lookup"><span data-stu-id="1036b-193">See also</span></span>

- [<span data-ttu-id="1036b-194">Microsoft 365 beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="1036b-194">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
- [<span data-ttu-id="1036b-195">Aan de slag met PowerShell voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1036b-195">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
- [<span data-ttu-id="1036b-196">Verbinding maken met alle Microsoft 365-services in één Windows PowerShell-venster</span><span class="sxs-lookup"><span data-stu-id="1036b-196">Connect to all Microsoft 365 services in a single Windows PowerShell window</span></span>](connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window.md)
