---
title: Verbinding maken met Microsoft 365 met PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
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
ms.openlocfilehash: 6b8f98441c7d727984bde8775dea496a9324d50c
ms.sourcegitcommit: 4d26a57c37ff7efbb8d235452c78498b06a59714
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/22/2021
ms.locfileid: "53053057"
---
# <a name="connect-to-microsoft-365-with-powershell"></a><span data-ttu-id="c30bb-103">Verbinding maken met Microsoft 365 met PowerShell</span><span class="sxs-lookup"><span data-stu-id="c30bb-103">Connect to Microsoft 365 with PowerShell</span></span>

<span data-ttu-id="c30bb-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="c30bb-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="c30bb-105">Met PowerShell voor Microsoft 365 kun je de instellingen van Microsoft 365 beheren vanaf de opdrachtregel.</span><span class="sxs-lookup"><span data-stu-id="c30bb-105">PowerShell for Microsoft 365 enables you to manage your Microsoft 365 settings from the command line.</span></span> <span data-ttu-id="c30bb-106">Als je verbinding wilt maken met PowerShell, installeer je gewoon de vereiste software en maak je verbinding met je Microsoft 365-organisatie.</span><span class="sxs-lookup"><span data-stu-id="c30bb-106">To connect to PowerShell, just install the required software and then connect to your Microsoft 365 organization.</span></span>

<span data-ttu-id="c30bb-107">Er zijn twee versies van de PowerShell-module die je kunt gebruiken om verbinding te maken met Microsoft 365 en gebruikersaccounts, groepen en licenties te beheren:</span><span class="sxs-lookup"><span data-stu-id="c30bb-107">There are two versions of the PowerShell module that you can use to connect to Microsoft 365 and administer user accounts, groups, and licenses:</span></span>

- <span data-ttu-id="c30bb-108">Azure Active Directory PowerShell voor Graph, waarvan de cmdlets *AzureAD* in de naam hebben</span><span class="sxs-lookup"><span data-stu-id="c30bb-108">Azure Active Directory PowerShell for Graph, whose cmdlets include *AzureAD* in their name</span></span>
- <span data-ttu-id="c30bb-109">Microsoft Azure Active Directory-module voor Windows PowerShell, waarvan cmdlets *MSol* in de naam hebben</span><span class="sxs-lookup"><span data-stu-id="c30bb-109">Microsoft Azure Active Directory Module for Windows PowerShell, whose cmdlets include *Msol* in their name</span></span>

<span data-ttu-id="c30bb-110">Momenteel vervangt de module Azure Active Directory PowerShell voor Graph nog niet alle functionaliteit van de Microsoft Azure Active Directory-module voor Windows PowerShell voor het beheer van gebruikers, groepen en licenties.</span><span class="sxs-lookup"><span data-stu-id="c30bb-110">Currently, the Azure Active Directory PowerShell for Graph module doesn't completely replace the functionality of the Microsoft Azure Active Directory Module for Windows PowerShell module for user, group, and license administration.</span></span> <span data-ttu-id="c30bb-111">In sommige gevallen moet u beide versies gebruiken.</span><span class="sxs-lookup"><span data-stu-id="c30bb-111">In some cases, you need to use both versions.</span></span> <span data-ttu-id="c30bb-112">U kunt beide versies op dezelfde computer veilig installeren.</span><span class="sxs-lookup"><span data-stu-id="c30bb-112">You can safely install both versions on the same computer.</span></span>

>[!Note]
><span data-ttu-id="c30bb-113">U kunt ook verbinding maken met [Azure Cloud Shell](#connect-with-the-azure-cloud-shell) vanuit het Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="c30bb-113">You can also connect with the [Azure Cloud Shell](#connect-with-the-azure-cloud-shell) from the Microsoft 365 admin center.</span></span>
>


## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c30bb-114">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="c30bb-114">What do you need to know before you begin?</span></span>


<span data-ttu-id="c30bb-115">**Besturingssysteem**</span><span class="sxs-lookup"><span data-stu-id="c30bb-115">**Operating system**</span></span>

<span data-ttu-id="c30bb-p103">Gebruik een 64-bits versie van Windows. Ondersteuning voor de 32-bits versie van de Microsoft Azure Active Directory-module voor Windows PowerShell is in 2014 beëindigd.</span><span class="sxs-lookup"><span data-stu-id="c30bb-p103">You must use a 64-bit version of Windows. Support for the 32-bit version of the Microsoft Azure Active Directory Module for Windows PowerShell ended in 2014.</span></span>

<span data-ttu-id="c30bb-118">U kunt de volgende versies van Windows gebruiken:</span><span class="sxs-lookup"><span data-stu-id="c30bb-118">You can use the following versions of Windows:</span></span>
    
  - <span data-ttu-id="c30bb-119">Windows 10, Windows 8.1, Windows 8, of Windows 7 Service Pack 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="c30bb-119">Windows 10, Windows 8.1, Windows 8, or Windows 7 Service Pack 1 (SP1)</span></span> 
    
  - <span data-ttu-id="c30bb-120">Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012, of Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="c30bb-120">Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012, or Windows Server 2008 R2 SP1</span></span>

>[!Note]
><span data-ttu-id="c30bb-121">Voor Windows 8,1, Windows 8, Windows 7 Service Pack 1 (SP1), Windows Server 2012 R2, Windows Server 2012 en Windows Server 2008 R2 SP1 kunt u het [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616)downloaden en installeren.</span><span class="sxs-lookup"><span data-stu-id="c30bb-121">For Windows 8.1, Windows 8, Windows 7 Service Pack 1 (SP1), Windows Server 2012 R2, Windows Server 2012, and Windows Server 2008 R2 SP1, download and install the [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616).</span></span>

<span data-ttu-id="c30bb-122">**PowerShell**</span><span class="sxs-lookup"><span data-stu-id="c30bb-122">**PowerShell**</span></span>

- <span data-ttu-id="c30bb-123">Voor de module Azure Active Directory PowerShell voor Graph moet je PowerShell versie 5.1 of hoger gebruiken.</span><span class="sxs-lookup"><span data-stu-id="c30bb-123">For the Azure Active Directory PowerShell for Graph module, you must use PowerShell version 5.1 or later.</span></span>

- <span data-ttu-id="c30bb-p104">Voor de Microsoft Azure Active Directory-module voor Windows PowerShell moet u PowerShell versie 5.1 of hoger gebruiken, tot PowerShell versie 6. PowerShell versie 7 kan niet meer worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="c30bb-p104">For the Microsoft Azure Active Directory Module for Windows PowerShell module, you must use PowerShell version 5.1 or later, up to PowerShell version 6. You can't use PowerShell version 7.</span></span>
       
>[!Note]
><span data-ttu-id="c30bb-126">Deze procedures zijn bedoeld voor gebruikers die lid zijn van een Microsoft 365-beheerdersrol.</span><span class="sxs-lookup"><span data-stu-id="c30bb-126">These procedures are intended for users who are members of a Microsoft 365 admin role.</span></span> <span data-ttu-id="c30bb-127">Raadpleeg [Over beheerdersrollen](../admin/add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="c30bb-127">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>


## <a name="connect-with-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="c30bb-128">Maak verbinding met de Windows PowerShell voor Graph-module van Microsoft Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c30bb-128">Connect with the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="c30bb-129">Opdrachten in de module Azure Active Directory PowerShell voor Graph hebben *AzureAD* in de naam van de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c30bb-129">Commands in the Azure Active Directory PowerShell for Graph module have *AzureAD* in their cmdlet name.</span></span> <span data-ttu-id="c30bb-130">U kunt de module [ Azure Active Directory PowerShell voor Graph](/powershell/azure/active-directory/install-adv2) of [Azure PowerShell](/powershell/azure/install-az-ps) installeren.</span><span class="sxs-lookup"><span data-stu-id="c30bb-130">You can install the [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2) module or [Azure PowerShell](/powershell/azure/install-az-ps).</span></span>

<span data-ttu-id="c30bb-131">Voer de volgende stappen uit om de module te installeren en verbinding te maken met je Microsoft 365-abonnement voor procedures waarvoor de nieuwe cmdlets in de module Azure Active Directory PowerShell voor Graph zijn vereist.</span><span class="sxs-lookup"><span data-stu-id="c30bb-131">For procedures that require the new cmdlets in the Azure Active Directory PowerShell for Graph module, follow these steps to install the module and connect to your Microsoft 365 subscription.</span></span>

> [!Note]
> <span data-ttu-id="c30bb-132">Zie [Module Azure Active Directory PowerShell voor Graph](/powershell/azure/active-directory/install-adv2) voor informatie over de ondersteuning voor verschillende versies van Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="c30bb-132">For information about support for different versions of Windows, see [Azure Active Directory PowerShell for Graph module](/powershell/azure/active-directory/install-adv2) .</span></span>

### <a name="step-1-install-the-required-software"></a><span data-ttu-id="c30bb-133">Stap 1:Installeer de vereiste software</span><span class="sxs-lookup"><span data-stu-id="c30bb-133">Step 1: Install the required software</span></span>

<span data-ttu-id="c30bb-134">Deze stappen hoef je maar één keer uit te voeren op je computer.</span><span class="sxs-lookup"><span data-stu-id="c30bb-134">These steps are required only one time on your computer.</span></span> <span data-ttu-id="c30bb-135">Maar waarschijnlijk moet je de software regelmatig bijwerken.</span><span class="sxs-lookup"><span data-stu-id="c30bb-135">But you'll likely need to update the software periodically.</span></span>
  
1. <span data-ttu-id="c30bb-136">Open een Windows PowerShell-opdrachtprompt met verhoogde bevoegdheid (voer Windows PowerShell uit als beheerder).</span><span class="sxs-lookup"><span data-stu-id="c30bb-136">Open an elevated Windows PowerShell Command Prompt window (run Windows PowerShell as an administrator).</span></span>
    
2. <span data-ttu-id="c30bb-137">Voer de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="c30bb-137">Run this command:</span></span>
    
    ```powershell
    Install-Module -Name AzureAD
    ```

  <span data-ttu-id="c30bb-138">PowerShell Gallery (PSGallery) is niet geconfigureerd als vertrouwde opslagplaats voor **PowerShellGet**.</span><span class="sxs-lookup"><span data-stu-id="c30bb-138">By default, the PowerShell Gallery (PSGallery) isn't configured as a trusted repository for **PowerShellGet**.</span></span> <span data-ttu-id="c30bb-139">De eerste keer dat u PSGallery gebruikt, ziet u het volgende bericht:</span><span class="sxs-lookup"><span data-stu-id="c30bb-139">The first time you use the PSGallery, you'll see the following message:</span></span>

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="c30bb-140">Antwoord **Ja** of **Ja op alles** om door te gaan met de installatie.</span><span class="sxs-lookup"><span data-stu-id="c30bb-140">Answer **Yes** or **Yes to All** to continue with the installation.</span></span>


### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a><span data-ttu-id="c30bb-141">Stap 2: Maak verbinding met Azure AD voor jouw Microsoft 365-abonnement</span><span class="sxs-lookup"><span data-stu-id="c30bb-141">Step 2: Connect to Azure AD for your Microsoft 365 subscription</span></span>

<span data-ttu-id="c30bb-p109">Als u verbinding wilt maken met Azure Active Directory (Azure AD) voor uw Microsoft 365-abonnement met een accountnaam en wachtwoord of met meervoudige verificatie, voert u een van de volgende opdrachten uit vanaf een Windows PowerShell-opdrachtprompt (de opdracht hoeft geen verhoogde bevoegdheden te bevatten).</span><span class="sxs-lookup"><span data-stu-id="c30bb-p109">To connect to Azure Active Directory (Azure AD) for your Microsoft 365 subscription with an account name and password or with multi-factor authentication, run one of these commands from a Windows PowerShell command prompt. (It doesn't have to be elevated.)</span></span>

| <span data-ttu-id="c30bb-144">Office 365-cloud</span><span class="sxs-lookup"><span data-stu-id="c30bb-144">Office 365 cloud</span></span> | <span data-ttu-id="c30bb-145">Opdracht</span><span class="sxs-lookup"><span data-stu-id="c30bb-145">Command</span></span> |
|:-------|:-----|
| <span data-ttu-id="c30bb-146">Office 365 wereldwijd (+ GCC)</span><span class="sxs-lookup"><span data-stu-id="c30bb-146">Office 365 Worldwide (+GCC)</span></span> | `Connect-AzureAD` |
| <span data-ttu-id="c30bb-147">Office 365 beheerd door 21 Vianet</span><span class="sxs-lookup"><span data-stu-id="c30bb-147">Office 365 operated by 21 Vianet</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureChinaCloud` |
| <span data-ttu-id="c30bb-148">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="c30bb-148">Office 365 Germany</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureGermanyCloud` |
| <span data-ttu-id="c30bb-149">Office 365 U.S. Government DoD en Office 365 U.S. Government GCC High</span><span class="sxs-lookup"><span data-stu-id="c30bb-149">Office 365 U.S. Government DoD and Office 365 U.S. Government GCC High</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureUSGovernment` |
|||

<span data-ttu-id="c30bb-150">Typ de gebruikersnaam en het wachtwoord voor jouw werk- of schoolaccount van Microsoft 365 in het dialoogvenster **Aanmelden bij uw account** en selecteer vervolgens **OK**.</span><span class="sxs-lookup"><span data-stu-id="c30bb-150">In the **Sign into your account** dialog box, type your Microsoft 365 work or school account user name and password, and then select **OK**.</span></span>

<span data-ttu-id="c30bb-151">Als je meervoudige verificatie gebruikt, volg je de instructies om aanvullende verificatiegegevens op te geven, zoals een verificatiecode.</span><span class="sxs-lookup"><span data-stu-id="c30bb-151">If you're using multi-factor authentication, follow the instructions to provide additional authentication information, such as a verification code.</span></span>

<span data-ttu-id="c30bb-152">Nadat je verbinding hebt gemaakt, kun je de cmdlets voor de [module Azure Active Directory PowerShell voor Graph](/powershell/module/azuread) gebruiken.</span><span class="sxs-lookup"><span data-stu-id="c30bb-152">After you connect, you can use the cmdlets for the [Azure Active Directory PowerShell for Graph module](/powershell/module/azuread).</span></span>

## <a name="connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="c30bb-153">Maak verbinding met de Microsoft Azure Active Directory-module voor Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c30bb-153">Connect with the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

>[!Note]
><span data-ttu-id="c30bb-154">Cmdlets in de Microsoft Azure Active Directory-module voor Windows PowerShell hebben *MSol* in de naam.</span><span class="sxs-lookup"><span data-stu-id="c30bb-154">Cmdlets in the Microsoft Azure Active Directory Module for Windows PowerShell have *Msol* in their name.</span></span>

<span data-ttu-id="c30bb-155">PowerShell versie 7 biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell en cmdlets met *Msol* in de naam.</span><span class="sxs-lookup"><span data-stu-id="c30bb-155">PowerShell version 7 and later don't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="c30bb-156">Voor PowerShell versie 7 en hoger moet je de module Azure Active Directory PowerShell voor Graph gebruiken.</span><span class="sxs-lookup"><span data-stu-id="c30bb-156">For PowerShell version 7 and later, you must use the Azure Active Directory PowerShell for Graph module or Azure PowerShell.</span></span>

<span data-ttu-id="c30bb-157">PowerShell Core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell en cmdlets met *Msol* in hun naam.</span><span class="sxs-lookup"><span data-stu-id="c30bb-157">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="c30bb-158">Voer deze cmdlets uit vanuit Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c30bb-158">Run these cmdlets from Windows PowerShell.</span></span>
    
### <a name="step-1-install-the-required-software"></a><span data-ttu-id="c30bb-159">Stap 1:Installeer de vereiste software</span><span class="sxs-lookup"><span data-stu-id="c30bb-159">Step 1: Install the required software</span></span>

<span data-ttu-id="c30bb-160">Deze stappen hoef je maar één keer uit te voeren op je computer.</span><span class="sxs-lookup"><span data-stu-id="c30bb-160">These steps are required only one time on your computer.</span></span> <span data-ttu-id="c30bb-161">Maar waarschijnlijk moet je de software regelmatig bijwerken.</span><span class="sxs-lookup"><span data-stu-id="c30bb-161">But you'll likely need to update the software periodically.</span></span>
  
1.  <span data-ttu-id="c30bb-162">Als je geen Windows 10 gebruikt, installeer je de 64-bits versie van de Microsoft Online Services-aanmeldhulp: [Microsoft Online Services-aanmeldhulp voor IT-professionals RTW](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi).</span><span class="sxs-lookup"><span data-stu-id="c30bb-162">If you're not running Windows 10, install the 64-bit version of the Microsoft Online Services Sign-in Assistant: [Microsoft Online Services Sign-in Assistant for IT Professionals RTW](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi).</span></span>
    
2. <span data-ttu-id="c30bb-163">Installeer de Microsoft Azure Active Directory-module voor Windows PowerShell met deze stappen:</span><span class="sxs-lookup"><span data-stu-id="c30bb-163">Follow these steps to install the Microsoft Azure Active Directory Module for Windows PowerShell:</span></span>
    
   1. <span data-ttu-id="c30bb-164">Open een verhoogde Windows PowerShell-opdrachtprompt (Voer Windows PowerShell uit als beheerder).</span><span class="sxs-lookup"><span data-stu-id="c30bb-164">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an administrator).</span></span>
   1.  <span data-ttu-id="c30bb-165">Voer de **installatie-module MSOnline** uit.</span><span class="sxs-lookup"><span data-stu-id="c30bb-165">Run the **Install-Module MSOnline** command.</span></span>
   1. <span data-ttu-id="c30bb-166">Als je wordt gevraagd om de NuGet-provider te installeren, typ je **Y** en druk je op Enter.</span><span class="sxs-lookup"><span data-stu-id="c30bb-166">If you're prompted to install the NuGet provider, type **Y** and press Enter.</span></span>
   1. <span data-ttu-id="c30bb-167">Als je wordt gevraagd om de module van PSGallery te installeren, typ je **Y** en druk je op Enter.</span><span class="sxs-lookup"><span data-stu-id="c30bb-167">If you're prompted to install the module from PSGallery, type **Y** and press Enter.</span></span>
    
### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a><span data-ttu-id="c30bb-168">Stap 2: Maak verbinding met Azure AD voor jouw Microsoft 365-abonnement</span><span class="sxs-lookup"><span data-stu-id="c30bb-168">Step 2: Connect to Azure AD for your Microsoft 365 subscription</span></span>

<span data-ttu-id="c30bb-p113">Als u verbinding wilt maken met Azure AD voor uw Microsoft 365-abonnement met een accountnaam en wachtwoord of met meervoudige verificatie, voert u een van de volgende opdrachten uit vanaf een Windows PowerShell-opdrachtprompt (deze hoeft geen verhoogde bevoegdheden te bevatten).</span><span class="sxs-lookup"><span data-stu-id="c30bb-p113">To connect to Azure AD for your Microsoft 365 subscription with an account name and password or with multi-factor authentication, run one of these commands from a Windows PowerShell command prompt. (It doesn't have to be elevated.)</span></span>

| <span data-ttu-id="c30bb-171">Office 365-cloud</span><span class="sxs-lookup"><span data-stu-id="c30bb-171">Office 365 cloud</span></span> | <span data-ttu-id="c30bb-172">Opdracht</span><span class="sxs-lookup"><span data-stu-id="c30bb-172">Command</span></span> |
|:-------|:-----|
| <span data-ttu-id="c30bb-173">Office 365 wereldwijd (+ GCC)</span><span class="sxs-lookup"><span data-stu-id="c30bb-173">Office 365 Worldwide (+GCC)</span></span> | `Connect-MsolService` |
| <span data-ttu-id="c30bb-174">Office 365 beheerd door 21 Vianet</span><span class="sxs-lookup"><span data-stu-id="c30bb-174">Office 365 operated by 21 Vianet</span></span> | `Connect-MsolService -AzureEnvironment AzureChinaCloud` |
| <span data-ttu-id="c30bb-175">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="c30bb-175">Office 365 Germany</span></span> | `Connect-MsolService -AzureEnvironment AzureGermanyCloud` |
| <span data-ttu-id="c30bb-176">Office 365 U.S. Government DoD en Office 365 U.S. Government GCC High</span><span class="sxs-lookup"><span data-stu-id="c30bb-176">Office 365 U.S. Government DoD and Office 365 U.S. Government GCC High</span></span> | `Connect-MsolService -AzureEnvironment USGovernment` |
|||

<span data-ttu-id="c30bb-177">Typ de gebruikersnaam en het wachtwoord voor jouw werk- of schoolaccount van Microsoft 365 in het dialoogvenster **Aanmelden bij uw account** en selecteer vervolgens **OK**.</span><span class="sxs-lookup"><span data-stu-id="c30bb-177">In the **Sign into your account** dialog box, type your Microsoft 365 work or school account user name and password, and then select **OK**.</span></span>

<span data-ttu-id="c30bb-178">Als je meervoudige verificatie gebruikt, volg je de instructies om aanvullende verificatiegegevens op te geven, zoals een verificatiecode.</span><span class="sxs-lookup"><span data-stu-id="c30bb-178">If you're using multi-factor authentication, follow the instructions to provide additional authentication information, such as a verification code.</span></span>

### <a name="how-do-you-know-it-worked"></a><span data-ttu-id="c30bb-179">Hoe weet ik dat het werkt?</span><span class="sxs-lookup"><span data-stu-id="c30bb-179">How do you know it worked?</span></span>

<span data-ttu-id="c30bb-180">Als je geen foutmelding krijgt, ben je verbonden.</span><span class="sxs-lookup"><span data-stu-id="c30bb-180">If you don't get an error message, you connected successfully.</span></span> <span data-ttu-id="c30bb-181">Een snelle test is het uitvoeren van een Microsoft 365-cmdlet, bijvoorbeeld **Get-MsolUser**, en bekijk de resultaten.</span><span class="sxs-lookup"><span data-stu-id="c30bb-181">For quick test,  run a Microsoft 365 cmdlet, such as  **Get-MsolUser**, and see the results.</span></span>
  
<span data-ttu-id="c30bb-182">Als er een foutbericht wordt weergegeven, controleer je de volgende problemen:</span><span class="sxs-lookup"><span data-stu-id="c30bb-182">If you get an error message, check the following issues:</span></span>
  
- <span data-ttu-id="c30bb-183">**Een veelvoorkomend probleem is een onjuist wachtwoord**.</span><span class="sxs-lookup"><span data-stu-id="c30bb-183">**A common problem is an incorrect password**.</span></span> <span data-ttu-id="c30bb-184">Voer [stap 2](#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) opnieuw uit en let goed op de gebruikersnaam en het wachtwoord die je invoert.</span><span class="sxs-lookup"><span data-stu-id="c30bb-184">Run [Step 2](#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) again, and pay close attention to the user name and password that you enter.</span></span>
    
- <span data-ttu-id="c30bb-185">**De Microsoft Azure Active Directory-module voor Windows PowerShell vereist dat Microsoft .NET Framework 3.5.* x* is ingeschakeld op de computer**. Op je computer is waarschijnlijk een nieuwere versie geïnstalleerd (bijvoorbeeld 4 of 4.5.* x*).</span><span class="sxs-lookup"><span data-stu-id="c30bb-185">**The Microsoft Azure Active Directory Module for Windows PowerShell requires that Microsoft .NET Framework 3.5.* x* is enabled on your computer**. It's likely that your computer has a newer version installed (for example, 4 or 4.5.* x*).</span></span> <span data-ttu-id="c30bb-186">Maar compatibiliteit met eerdere versies van .NET Framework kan worden ingeschakeld of uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="c30bb-186">But backward compatibility with older versions of the .NET Framework can be enabled or disabled.</span></span> <span data-ttu-id="c30bb-187">Zie de volgende artikelen voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="c30bb-187">For more information, see the following articles:</span></span>
    
  - <span data-ttu-id="c30bb-188">Zie voor Windows Server 2012 of Windows Server 2012 R2 [.NET Framework 3.5 inschakelen met behulp van de wizard Functies en onderdelen toevoegen](/previous-versions/windows/it-pro/windows-8.1-and-8/dn482071(v=win.10)).</span><span class="sxs-lookup"><span data-stu-id="c30bb-188">For Windows Server 2012 or Windows Server 2012 R2, see [Enable .NET Framework 3.5 by using the Add Roles and Features Wizard](/previous-versions/windows/it-pro/windows-8.1-and-8/dn482071(v=win.10)).</span></span>
    
  - <span data-ttu-id="c30bb-189">Zie voor Windows 7 of Windows Server 2008 R2 [Je kunt de module Azure Active Directory voor Windows PowerShell niet openen](/troubleshoot/azure/active-directory/cant-open-aad-module-powershell).</span><span class="sxs-lookup"><span data-stu-id="c30bb-189">For Windows 7 or Windows Server 2008 R2, see [You can't open the Azure Active Directory Module for Windows PowerShell](/troubleshoot/azure/active-directory/cant-open-aad-module-powershell).</span></span>

  - <span data-ttu-id="c30bb-190">Zie voor Windows 10, Windows 8.1 en Windows 8 [.NET Framework 3.5 installeren in Windows 10, Windows 8.1 en Windows 8](/dotnet/framework/install/dotnet-35-windows-10)</span><span class="sxs-lookup"><span data-stu-id="c30bb-190">For Windows 10, Windows 8.1, and Windows 8, see [Install the .NET Framework 3.5 on Windows 10, Windows 8.1, and Windows 8](/dotnet/framework/install/dotnet-35-windows-10).</span></span>

  
- <span data-ttu-id="c30bb-191">**Uw versie van de module Microsoft Azure Active Directory voor Windows PowerShell is wellicht verouderd.**</span><span class="sxs-lookup"><span data-stu-id="c30bb-191">**Your version of the Microsoft Azure Active Directory Module for Windows PowerShell might be out of date.**</span></span> <span data-ttu-id="c30bb-192">Als u dit wilt controleren, voert u de volgende opdracht uit in PowerShell voor Microsoft 365 of de Microsoft Azure Active Directory-module voor Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c30bb-192">To check, run the following command in PowerShell for Microsoft 365 or the Microsoft Azure Active Directory Module for Windows PowerShell:</span></span>
    
  ```powershell
  (Get-Item C:\Windows\System32\WindowsPowerShell\v1.0\Modules\MSOnline\Microsoft.Online.Administration.Automation.PSModule.dll).VersionInfo.FileVersion
  ```

    <span data-ttu-id="c30bb-193">Als het geretourneerde versienummer lager is dan de waarde *1.0.8070.2*, verwijder je de Microsoft Azure Active Directory-module voor Windows PowerShell en installeer je deze vanuit [Stap 1](#step-1-install-the-required-software) hierboven.</span><span class="sxs-lookup"><span data-stu-id="c30bb-193">If the version number returned is lower than *1.0.8070.2*, uninstall the Microsoft Azure Active Directory Module for Windows PowerShell and install from [Step 1](#step-1-install-the-required-software), above.</span></span>

- <span data-ttu-id="c30bb-194">**Als je een verbindingsfoutbericht krijgt**, raadpleeg je [Foutbericht 'Connect-MsolService: Exception of type was thrown'](/office365/troubleshoot/active-directory/connect-msoservice-throw-exception).</span><span class="sxs-lookup"><span data-stu-id="c30bb-194">**If you get a connection error message**, see ["Connect-MsolService: Exception of type was thrown" error](/office365/troubleshoot/active-directory/connect-msoservice-throw-exception).</span></span>
    
- <span data-ttu-id="c30bb-195">**Als je de foutmelding 'Get-Item: Cannot find path' krijgt**, voer je de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="c30bb-195">**If you get a "Get-Item: Cannot find path" error message**, run this command:</span></span>


   ```powershell
     (dir "C:\Program Files\WindowsPowerShell\Modules\MSOnline").Name
   ```

## <a name="connect-with-the-azure-cloud-shell"></a><span data-ttu-id="c30bb-196">Verbinding maken met Azure Cloud Shell</span><span class="sxs-lookup"><span data-stu-id="c30bb-196">Connect with the Azure Cloud Shell</span></span>

<span data-ttu-id="c30bb-197">Als u verbinding wilt maken met Azure Cloud Shell vanuit het Microsoft 365-beheercentrum en dit wilt gebruiken, selecteert u in de rechterbovenhoek van de taakbalk het PowerShell-vensterpictogram.</span><span class="sxs-lookup"><span data-stu-id="c30bb-197">To connect with and use the Azure Cloud Shell from the Microsoft 365 admin center, select the PowerShell window icon from the upper-right corner of the task bar.</span></span> <span data-ttu-id="c30bb-198">Selecteer in het deelvenster **Welkom bij Azure Cloud Shell** de optie **PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="c30bb-198">In the **Welcome to Azure Cloud Shell** pane, select **PowerShell**.</span></span>

<span data-ttu-id="c30bb-199">Voor uw organisatie hebt u een actief Azure-abonnement nodig dat is gekoppeld aan uw Microsoft 365-abonnement.</span><span class="sxs-lookup"><span data-stu-id="c30bb-199">You will need an active Azure subscription for your organization that is tied to your Microsoft 365 subscription.</span></span> <span data-ttu-id="c30bb-200">Als u nog geen account hebt, kunt u er een maken.</span><span class="sxs-lookup"><span data-stu-id="c30bb-200">If you don't already have one, you can create one.</span></span> <span data-ttu-id="c30bb-201">Zodra u een Azure-abonnement hebt, wordt er een PowerShell-venster geopend waarin u PowerShell-opdrachten en -scripts kunt uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="c30bb-201">Once you have an Azure subscription, a PowerShell window opens from which you can run PowerShell commands and scripts.</span></span>

<span data-ttu-id="c30bb-202">Zie [Azure Cloud Shell](/azure/cloud-shell/overview) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="c30bb-202">For more information, see [Azure Cloud Shell](/azure/cloud-shell/overview).</span></span>

## <a name="see-also"></a><span data-ttu-id="c30bb-203">Zie ook</span><span class="sxs-lookup"><span data-stu-id="c30bb-203">See also</span></span>

- [<span data-ttu-id="c30bb-204">Microsoft 365 beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="c30bb-204">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
- [<span data-ttu-id="c30bb-205">Aan de slag met PowerShell voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c30bb-205">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
- [<span data-ttu-id="c30bb-206">Verbinding maken met alle Microsoft 365-services in één Windows PowerShell-venster</span><span class="sxs-lookup"><span data-stu-id="c30bb-206">Connect to all Microsoft 365 services in a single Windows PowerShell window</span></span>](connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window.md)
