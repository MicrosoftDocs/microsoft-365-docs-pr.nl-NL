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
description: Maak verbinding met uw Microsoft 365-Tenant met PowerShell voor Microsoft 365 voor het uitvoeren van Beheercentrum taken vanaf de opdrachtregel.
ms.openlocfilehash: 9b4cdbe9fcdea48df456e75095f8d269ab84696f
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950554"
---
# <a name="connect-to-microsoft-365-with-powershell"></a><span data-ttu-id="93739-103">Verbinding maken met Microsoft 365 met PowerShell</span><span class="sxs-lookup"><span data-stu-id="93739-103">Connect to Microsoft 365 with PowerShell</span></span>

<span data-ttu-id="93739-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="93739-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="93739-105">Met PowerShell voor Microsoft 365 kunt u de instellingen van Microsoft 365 beheren vanaf de opdrachtregel.</span><span class="sxs-lookup"><span data-stu-id="93739-105">PowerShell for Microsoft 365 lets you manage your Microsoft 365 settings from the command line.</span></span> <span data-ttu-id="93739-106">Verbinding maken met PowerShell is een eenvoudig proces waar u de vereiste software installeert en vervolgens verbinding maakt met uw Microsoft 365-organisatie.</span><span class="sxs-lookup"><span data-stu-id="93739-106">Connecting to PowerShell is a simple process where you install the required software and then connect to your Microsoft 365 organization.</span></span> 

<span data-ttu-id="93739-107">Er zijn twee versies van de PowerShell-module die u gebruikt om verbinding te maken met Microsoft 365 en gebruikersaccounts, groepen en licenties te beheren:</span><span class="sxs-lookup"><span data-stu-id="93739-107">There are two versions of the PowerShell module that you use to connect to Microsoft 365 and administer user accounts, groups, and licenses:</span></span>

- <span data-ttu-id="93739-108">Azure Active Directory PowerShell voor Graph (cmdlets bevatten **AzureAD** in hun naam)</span><span class="sxs-lookup"><span data-stu-id="93739-108">Azure Active Directory PowerShell for Graph (cmdlets include **AzureAD** in their name)</span></span>
- <span data-ttu-id="93739-109">Microsoft Azure Active Directory-module voor Windows PowerShell (cmdlets bevatten **MSol** in hun naam)</span><span class="sxs-lookup"><span data-stu-id="93739-109">Microsoft Azure Active Directory Module for Windows PowerShell (cmdlets include **MSol** in their name)</span></span> 

<span data-ttu-id="93739-110">Vanaf de datum van dit artikel vervangt de module Azure Active Directory PowerShell voor Graph de functionaliteit in de cmdlets van de Microsoft Azure Active Directory-module voor Windows PowerShell-module voor de gebruikers-, groeps-en licentiebeheer functie niet volledig.</span><span class="sxs-lookup"><span data-stu-id="93739-110">As of the date of this article, the Azure Active Directory PowerShell for Graph module does not completely replace the functionality in the cmdlets of Microsoft Azure Active Directory Module for Windows PowerShell module for user, group, and license administration.</span></span> <span data-ttu-id="93739-111">In sommige gevallen moet u beide versies gebruiken.</span><span class="sxs-lookup"><span data-stu-id="93739-111">In some cases, you need to use both versions.</span></span> <span data-ttu-id="93739-112">U kunt beide versies op dezelfde computer veilig installeren.</span><span class="sxs-lookup"><span data-stu-id="93739-112">You can safely install both versions on the same computer.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="93739-113">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="93739-113">What do you need to know before you begin?</span></span>

<span data-ttu-id="93739-114">U kunt de volgende versies van Windows gebruiken:</span><span class="sxs-lookup"><span data-stu-id="93739-114">You can use the following versions of Windows:</span></span>
    
  - <span data-ttu-id="93739-115">Windows 10, Windows 8.1, Windows 8, of Windows 7 Service Pack 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="93739-115">Windows 10, Windows 8.1, Windows 8, or Windows 7 Service Pack 1 (SP1)</span></span> 
    
  - <span data-ttu-id="93739-116">Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012, of Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="93739-116">Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012, or Windows Server 2008 R2 SP1</span></span>

    > [!NOTE]
    > <span data-ttu-id="93739-117">Voor de Azure Active Directory PowerShell-module voor Graph moet u PowerShell-versie 5.1 of hoger gebruiken.</span><span class="sxs-lookup"><span data-stu-id="93739-117">For the Azure Active Directory PowerShell for Graph module, you must use PowerShell version 5.1 or later.</span></span> <span data-ttu-id="93739-118">Voor de Microsoft Azure Active Directory-module voor Windows PowerShell-module moet u PowerShell-versie 5.1 of hoger tot PowerShell versie 6.</span><span class="sxs-lookup"><span data-stu-id="93739-118">For the Microsoft Azure Active Directory Module for Windows PowerShell module, you must use PowerShell version 5.1 or later up to PowerShell version 6.</span></span> <span data-ttu-id="93739-119">PowerShell versie 7 kan niet worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="93739-119">You cannot use PowerShell version 7.</span></span> <span data-ttu-id="93739-120">Voor Windows 8,1, Windows 8, Windows 7 Service Pack 1 (SP1), Windows Server 2012 R2, Windows Server 2012 en Windows Server 2008 R2 SP1 kunt u het [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616)downloaden en installeren.</span><span class="sxs-lookup"><span data-stu-id="93739-120">For Windows 8.1, Windows 8, Windows 7 Service Pack 1 (SP1), Windows Server 2012 R2, Windows Server 2012, and Windows Server 2008 R2 SP1, download and install the [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616).</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="93739-121">Voor een 64-bits versie van Windows.</span><span class="sxs-lookup"><span data-stu-id="93739-121">Use a 64-bit version of Windows.</span></span> <span data-ttu-id="93739-122">Ondersteuning voor de 32-bits versie de Microsoft Azure Active Directory-module voor Windows PowerShell is stopgezet in oktober 2014.</span><span class="sxs-lookup"><span data-stu-id="93739-122">Support for the 32-bit version the Microsoft Azure Active Directory Module for Windows PowerShell was discontinued in October of 2014.</span></span>
    
<span data-ttu-id="93739-123">Deze procedures zijn bedoeld voor gebruikers die lid zijn van een Microsoft 365-beheerdersrol.</span><span class="sxs-lookup"><span data-stu-id="93739-123">These procedures are intended for users who are members of a Microsoft 365 admin role.</span></span> <span data-ttu-id="93739-124">Raadpleeg [Over beheerdersrollen](https://go.microsoft.com/fwlink/p/?LinkId=532367) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="93739-124">For more information, see [About admin roles](https://go.microsoft.com/fwlink/p/?LinkId=532367).</span></span>


## <a name="connect-with-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="93739-125">Maak verbinding met de Windows PowerShell voor Graph-module van Microsoft Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="93739-125">Connect with the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="93739-126">Opdrachten in de module Azure Active Directory PowerShell voor Graph hebben **AzureAD** in de naam van de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="93739-126">Commands in the Azure Active Directory PowerShell for Graph module have **AzureAD** in their cmdlet name.</span></span> <span data-ttu-id="93739-127">U kunt de module [ Azure Active Directory PowerShell voor Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) of [Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-az-ps) installeren.</span><span class="sxs-lookup"><span data-stu-id="93739-127">You can install the [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) module or [Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-az-ps).</span></span>

<span data-ttu-id="93739-128">Voer de volgende stappen uit om de module te installeren en verbinding te maken met uw Microsoft 365-abonnement voor procedures waarvoor de nieuwe cmdlets in de module Azure Active Directory PowerShell voor Graph zijn vereist.</span><span class="sxs-lookup"><span data-stu-id="93739-128">For procedures that require the new cmdlets in the Azure Active Directory PowerShell for Graph module, use these steps to install the module and connect to your Microsoft 365 subscription.</span></span>

> [!Note]
> <span data-ttu-id="93739-129">Zie [Azure Active Directory PowerShell voor Graph module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) voor informatie over de ondersteuning voor verschillende versies van Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="93739-129">See [Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) for information about the support for different versions of Microsoft Windows.</span></span>

### <a name="step-1-install-required-software"></a><span data-ttu-id="93739-130">Stap 1: vereiste software installeren</span><span class="sxs-lookup"><span data-stu-id="93739-130">Step 1: Install required software</span></span>

<span data-ttu-id="93739-131">Deze stappen zijn eenmalig vereist op uw computer, niet telkens wanneer u verbinding maakt.</span><span class="sxs-lookup"><span data-stu-id="93739-131">These steps are required once on your computer, not every time you connect.</span></span> <span data-ttu-id="93739-132">Het is echter waarschijnlijk dat u regelmatig nieuwere versies van de software moet installeren.</span><span class="sxs-lookup"><span data-stu-id="93739-132">However, you'll likely need to install newer versions of the software periodically.</span></span>
  
1. <span data-ttu-id="93739-133">Open een verhoogde Windows PowerShell-opdrachtprompt (Voer Windows PowerShell uit als beheerder).</span><span class="sxs-lookup"><span data-stu-id="93739-133">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an administrator).</span></span>
    
2. <span data-ttu-id="93739-134">Voer deze opdracht uit op de **Beheerder: Windows PowerShell**-opdrachtprompt op beheerdersniveau:</span><span class="sxs-lookup"><span data-stu-id="93739-134">In the **Administrator: Windows PowerShell** command window, run this command:</span></span>
    
  ```powershell
  Install-Module -Name AzureAD
  ```

<span data-ttu-id="93739-135">Als u wordt gevraagd een module te installeren vanuit een niet-vertrouwde opslagplaats, typt u **Y** en drukt u op ENTER.</span><span class="sxs-lookup"><span data-stu-id="93739-135">If prompted about installing a module from an untrusted repository, type **Y** and press ENTER.</span></span>

### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a><span data-ttu-id="93739-136">Stap 2: verbinding maken met Azure AD voor uw abonnement op Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="93739-136">Step 2: Connect to Azure AD for your Microsoft 365 subscription</span></span>

<span data-ttu-id="93739-137">Als u verbinding wilt maken met Azure AD voor uw abonnement op Microsoft 365 met een accountnaam en wachtwoord of met multi-factor Authentication (MFA), voert u een van de volgende opdrachten uit vanui een Windows PowerShell-opdrachtprompt (deze hoeft niet verhoogd te zijn).</span><span class="sxs-lookup"><span data-stu-id="93739-137">To connect to Azure AD for your Microsoft 365 subscription with an account name and password or with multi-factor authentication (MFA), run one of these commands from a Windows PowerShell command prompt (it does not have to be elevated).</span></span>

| <span data-ttu-id="93739-138">Office 365-cloud</span><span class="sxs-lookup"><span data-stu-id="93739-138">Office 365 cloud</span></span> | <span data-ttu-id="93739-139">Opdracht</span><span class="sxs-lookup"><span data-stu-id="93739-139">Command</span></span> |
|:-------|:-----|
| <span data-ttu-id="93739-140">Office 365 wereldwijd (+ GCC)</span><span class="sxs-lookup"><span data-stu-id="93739-140">Office 365 Worldwide (+GCC)</span></span> | `Connect-AzureAD` |
| <span data-ttu-id="93739-141">Office 365 beheerd door 21 Vianet</span><span class="sxs-lookup"><span data-stu-id="93739-141">Office 365 operated by 21 Vianet</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureChinaCloud` |
| <span data-ttu-id="93739-142">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="93739-142">Office 365 Germany</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureGermanyCloud` |
| <span data-ttu-id="93739-143">Office 365 U.S. Government DoD en Office 365 U.S. Government GCC High</span><span class="sxs-lookup"><span data-stu-id="93739-143">Office 365 U.S. Government DoD and Office 365 U.S. Government GCC High</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureUSGovernment` |
|||

<span data-ttu-id="93739-144">Typ de gebruikersnaam en het wachtwoord voor uw Microsoft 365-werk-of schoolaccount in het dialoogvenster **aanmelden bij uw account** en klik vervolgens op **OK**.</span><span class="sxs-lookup"><span data-stu-id="93739-144">In the **Sign into your account** dialog box, type your Microsoft 365 work or school account user name and password, and then click **OK**.</span></span>

<span data-ttu-id="93739-145">Als u MFA gebruikt, volg de instructies in het extra dialoogvenster om aanvullende verificatiegegevens op te geven, zoals een verificatiecode.</span><span class="sxs-lookup"><span data-stu-id="93739-145">If you are using MFA, follow the instructions in the additional dialog boxes to provide more authentication information, such as a verification code.</span></span>

<span data-ttu-id="93739-146">Nadat u verbinding hebt gemaakt, kunt u de cmdlets voor de [module Azure Active Directory PowerShell voor Graph](https://docs.microsoft.com/powershell/azuread/v2/azureactivedirectory)gebruiken.</span><span class="sxs-lookup"><span data-stu-id="93739-146">After connecting, you can use the cmdlets for the [Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/powershell/azuread/v2/azureactivedirectory).</span></span>
  

## <a name="connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="93739-147">Maak verbinding met de Microsoft Azure Active Directory-module voor Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="93739-147">Connect with the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="93739-148">Opdrachten in de module Microsoft Azure Active Directory voor Windows PowerShell hebben**MSol** in hun cmdlet-naam.</span><span class="sxs-lookup"><span data-stu-id="93739-148">Commands in the Microsoft Azure Active Directory Module for Windows PowerShell have **Msol** in their cmdlet name.</span></span>

<span data-ttu-id="93739-149">PowerShell versie 7 biedt geen ondersteuning voor de module Microsoft Azure Active Directory voor Windows PowerShell-module en cmdlets met **Msol** in hun naam.</span><span class="sxs-lookup"><span data-stu-id="93739-149">PowerShell version 7 and later do not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="93739-150">Voor PowerShell versie 7 en hoger, moet u de module Azure Active Directory PowerShell voor Graph gebruiken.</span><span class="sxs-lookup"><span data-stu-id="93739-150">For PowerShell version 7 and later, you must use the Azure Active Directory PowerShell for Graph module or Azure PowerShell.</span></span>

<span data-ttu-id="93739-151">PowerShell Core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell-module en cmdlets met **Msol** in hun naam.</span><span class="sxs-lookup"><span data-stu-id="93739-151">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="93739-152">Als u deze cmdlets wilt blijven gebruiken, moet u deze uitvoeren vanuit Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="93739-152">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span> 
    
### <a name="step-1-install-required-software"></a><span data-ttu-id="93739-153">Stap 1: vereiste software installeren</span><span class="sxs-lookup"><span data-stu-id="93739-153">Step 1: Install required software</span></span>

<span data-ttu-id="93739-154">Deze stappen zijn eenmalig vereist op uw computer, niet telkens wanneer u verbinding maakt.</span><span class="sxs-lookup"><span data-stu-id="93739-154">These steps are required once on your computer, not every time you connect.</span></span> <span data-ttu-id="93739-155">Het is echter waarschijnlijk dat u regelmatig nieuwere versies van de software moet installeren.</span><span class="sxs-lookup"><span data-stu-id="93739-155">However, you'll likely need to install newer versions of the software periodically.</span></span>
  
1.  <span data-ttu-id="93739-156">Als u geen Windows 10 gebruikt, installeer de 64-bits versie van de Microsoft Online Services-aanmeldhulp: [Microsoft Online Services-aanmeldhulp voor IT-professionals RTW](https://go.microsoft.com/fwlink/p/?LinkId=286152).</span><span class="sxs-lookup"><span data-stu-id="93739-156">If you are not running Windows 10, install the 64-bit version of the Microsoft Online Services Sign-in Assistant: [Microsoft Online Services Sign-in Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/p/?LinkId=286152).</span></span>
    
2. <span data-ttu-id="93739-157">Installeer de module Microsoft Azure Active Directory voor Windows PowerShell met deze stappen:</span><span class="sxs-lookup"><span data-stu-id="93739-157">Install the Microsoft Azure Active Directory Module for Windows PowerShell with these steps:</span></span>
    
  - <span data-ttu-id="93739-158">Open een verhoogde Windows PowerShell-opdrachtprompt (Voer Windows PowerShell uit als beheerder).</span><span class="sxs-lookup"><span data-stu-id="93739-158">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an administrator).</span></span>
  - <span data-ttu-id="93739-159">Voer de **installatie-module MSOnline** uit.</span><span class="sxs-lookup"><span data-stu-id="93739-159">Run the **Install-Module MSOnline** command.</span></span>
  - <span data-ttu-id="93739-160">Als u wordt gevraagd om de NuGet provider te installeren, typt u **Y** en drukt u op ENTER.</span><span class="sxs-lookup"><span data-stu-id="93739-160">If prompted to install the NuGet provider, type **Y** and press ENTER.</span></span>
  - <span data-ttu-id="93739-161">Als u wordt gevraagd om de module van PSGallery te installeren, typt u **Y** en drukt u op ENTER.</span><span class="sxs-lookup"><span data-stu-id="93739-161">If prompted to install the module from PSGallery, type **Y** and press ENTER.</span></span>
    
### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a><span data-ttu-id="93739-162">Stap 2: verbinding maken met Azure AD voor uw abonnement op Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="93739-162">Step 2: Connect to Azure AD for your Microsoft 365 subscription</span></span>

<span data-ttu-id="93739-163">Als u verbinding wilt maken met Azure AD voor uw abonnement op Microsoft 365 met een accountnaam en wachtwoord of met multi-factor Authentication (MFA), voert u een van de volgende opdrachten uit vanui een Windows PowerShell-opdrachtprompt (deze hoeft niet verhoogd te zijn).</span><span class="sxs-lookup"><span data-stu-id="93739-163">To connect to Azure AD for your Microsoft 365 subscription with an account name and password or with multi-factor authentication (MFA), run one of these commands from a Windows PowerShell command prompt (it does not have to be elevated).</span></span>

| <span data-ttu-id="93739-164">Office 365-cloud</span><span class="sxs-lookup"><span data-stu-id="93739-164">Office 365 cloud</span></span> | <span data-ttu-id="93739-165">Opdracht</span><span class="sxs-lookup"><span data-stu-id="93739-165">Command</span></span> |
|:-------|:-----|
| <span data-ttu-id="93739-166">Office 365 wereldwijd (+ GCC)</span><span class="sxs-lookup"><span data-stu-id="93739-166">Office 365 Worldwide (+GCC)</span></span> | `Connect-MsolService` |
| <span data-ttu-id="93739-167">Office 365 beheerd door 21 Vianet</span><span class="sxs-lookup"><span data-stu-id="93739-167">Office 365 operated by 21 Vianet</span></span> | `Connect-MsolService -AzureEnvironment AzureChinaCloud` |
| <span data-ttu-id="93739-168">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="93739-168">Office 365 Germany</span></span> | `Connect-MsolService -AzureEnvironment AzureGermanyCloud` |
| <span data-ttu-id="93739-169">Office 365 U.S. Government DoD en Office 365 U.S. Government GCC High</span><span class="sxs-lookup"><span data-stu-id="93739-169">Office 365 U.S. Government DoD and Office 365 U.S. Government GCC High</span></span> | `Connect-MsolService -AzureEnvironment USGovernment` |
|||

<span data-ttu-id="93739-170">Typ de gebruikersnaam en het wachtwoord voor uw Microsoft 365-werk-of schoolaccount in het dialoogvenster **aanmelden bij uw account** en klik vervolgens op **OK**.</span><span class="sxs-lookup"><span data-stu-id="93739-170">In the **Sign into your account** dialog box, type your Microsoft 365 work or school account user name and password, and then click **OK**.</span></span>

<span data-ttu-id="93739-171">Als u MFA gebruikt, volg de instructies in het extra dialoogvenster om aanvullende verificatiegegevens op te geven, zoals een verificatiecode.</span><span class="sxs-lookup"><span data-stu-id="93739-171">If you are using MFA, follow the instructions in the additional dialog boxes to provide more authentication information, such as a verification code.</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="93739-172">Hoe weet u of dit heeft gewerkt?</span><span class="sxs-lookup"><span data-stu-id="93739-172">How do you know this worked?</span></span>

<span data-ttu-id="93739-173">Als er geen fouten worden ontvangen, bent u succesvol verbonden.</span><span class="sxs-lookup"><span data-stu-id="93739-173">If you don't receive any errors, you connected successfully.</span></span> <span data-ttu-id="93739-174">Een snelle test is het uitvoeren van een Microsoft 365-cmdlet, bijvoorbeeld **Get-MsolUser** - en bekijk de resultaten.</span><span class="sxs-lookup"><span data-stu-id="93739-174">A quick test is to run a Microsoft 365 cmdlet—for example, **Get-MsolUser** —and see the results.</span></span>
  
<span data-ttu-id="93739-175">Als er fouten worden ontvangen, controleert u de volgende vereisten:</span><span class="sxs-lookup"><span data-stu-id="93739-175">If you receive errors, check the following requirements:</span></span>
  
- <span data-ttu-id="93739-176">**Een veelvoorkomend probleem is een onjuist wachtwoord**.</span><span class="sxs-lookup"><span data-stu-id="93739-176">**A common problem is an incorrect password**.</span></span> <span data-ttu-id="93739-177">Voer stap 2 nogmaals uit.</span><span class="sxs-lookup"><span data-stu-id="93739-177">Run Step 2 again.</span></span> <span data-ttu-id="93739-178">en let goed op de gebruikersnaam en het wachtwoord dat u invoert.</span><span class="sxs-lookup"><span data-stu-id="93739-178">and pay close attention to the user name and password you enter.</span></span>
    
- <span data-ttu-id="93739-179">**De module Microsoft Azure Active Directory voor Windows PowerShell vereist dat Microsoft .NET Framework 3.5.* x *-functie is ingeschakeld op uw computer\*\*. De kans is groot dat er een nieuwere versie van op uw computer is geïnstalleerd (bijvoorbeeld 4 of 4.5.* x*), maar terugwaartse compatibiliteit met oudere versies van .NET Framework kan worden ingeschakeld of uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="93739-179">**The Microsoft Azure Active Directory Module for Windows PowerShell requires that the Microsoft .NET Framework 3.5.* x* feature is enabled on your computer**. It's likely that your computer has a newer version installed (for example, 4 or 4.5.* x*), but backwards compatibility with older versions of the .NET Framework can be enabled or disabled.</span></span> <span data-ttu-id="93739-180">Zie de volgende onderwerpen voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="93739-180">For more information, see the following topics:</span></span>
    
  - <span data-ttu-id="93739-181">Zie voor Windows Server 2012 of Windows Server 2012 R2 [.NET Framework 3,5 inschakelen met behulp van de wizard functies en onderdelen toevoegen](https://go.microsoft.com/fwlink/p/?LinkId=532368)</span><span class="sxs-lookup"><span data-stu-id="93739-181">For Windows Server 2012 or Windows Server 2012 R2, see [Enable .NET Framework 3.5 by using the Add Roles and Features Wizard](https://go.microsoft.com/fwlink/p/?LinkId=532368)</span></span>
    
  - <span data-ttu-id="93739-182">Zie voor Windows 7 of Windows Server 2008 R2 [U kunt de Azure Active Directory-module voor Windows PowerShell niet openen](https://go.microsoft.com/fwlink/p/?LinkId=532370)</span><span class="sxs-lookup"><span data-stu-id="93739-182">For Windows 7 or Windows Server 2008 R2, see [You can't open the Azure Active Directory Module for Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=532370)</span></span>

  - <span data-ttu-id="93739-183">Zie voor Windows 10, Windows 8,1 en Windows 8 [.NET Framework 3.5 installeren in Windows 10, Windows 8,1 en Windows 8](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10)</span><span class="sxs-lookup"><span data-stu-id="93739-183">For Windows 10, Windows 8.1, and Windows 8, see [Install the .NET Framework 3.5 on Windows 10, Windows 8.1, and Windows 8](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10)</span></span>

  
- <span data-ttu-id="93739-184">**Uw versie van de module Microsoft Azure Active Directory voor Windows PowerShell is wellicht verouderd.**</span><span class="sxs-lookup"><span data-stu-id="93739-184">**Your version of the Microsoft Azure Active Directory Module for Windows PowerShell might be out of date.**</span></span> <span data-ttu-id="93739-185">Als u dit wilt controleren, voert u de volgende opdracht uit in PowerShell voor Microsoft 365 of de Microsoft Azure Active Directory-module voor Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="93739-185">To check, run the following command in PowerShell for Microsoft 365 or the Microsoft Azure Active Directory Module for Windows PowerShell:</span></span>
    
  ```powershell
  (Get-Item C:\Windows\System32\WindowsPowerShell\v1.0\Modules\MSOnline\Microsoft.Online.Administration.Automation.PSModule.dll).VersionInfo.FileVersion
  ```

    <span data-ttu-id="93739-186">Als het geretourneerde versienummer lager is dan de waarde 1.0.8070.2, verwijdert u de Microsoft Azure Active Directory-module voor Windows PowerShell en installeert u deze uit stap 1 hierboven.</span><span class="sxs-lookup"><span data-stu-id="93739-186">If the version number returned is lower than the value 1.0.8070.2, uninstall the Microsoft Azure Active Directory Module for Windows PowerShell and install from Step 1 above.</span></span>

- <span data-ttu-id="93739-187">**Als er een verbindingsfout wordt ontvangen, raadpleegt u dit onderwerp:** ['verbinden-MsolService: uitzondering van type is opgetreden'](https://go.microsoft.com/fwlink/p/?LinkId=532377).</span><span class="sxs-lookup"><span data-stu-id="93739-187">**If you receive a connection error, see this topic:** ["Connect-MsolService: Exception of type was thrown" error](https://go.microsoft.com/fwlink/p/?LinkId=532377).</span></span>
    
- <span data-ttu-id="93739-188">**Als u het foutbericht Get-item: kan pad niet vinden ontvangt, gebruikt u de volgende opdracht:**</span><span class="sxs-lookup"><span data-stu-id="93739-188">**If you receive a "Get-Item : Cannot find path" error, use this command:**</span></span> 

```powershell
  (dir "C:\Program Files\WindowsPowerShell\Modules\MSOnline").Name
```

## <a name="see-also"></a><span data-ttu-id="93739-189">Zie ook</span><span class="sxs-lookup"><span data-stu-id="93739-189">See also</span></span>

- [<span data-ttu-id="93739-190">Microsoft 365 beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="93739-190">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
- [<span data-ttu-id="93739-191">Aan de slag met PowerShell voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="93739-191">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
- [<span data-ttu-id="93739-192">Verbinding maken met alle Microsoft 365-services in één Windows PowerShell-venster</span><span class="sxs-lookup"><span data-stu-id="93739-192">Connect to all Microsoft 365 services in a single Windows PowerShell window</span></span>](connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window.md)
