---
title: Verbinding maken met alle Microsoft 365-services in een enkel PowerShell-venster
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 02/02/2021
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- LIL_Placement
- Ent_Office_Other
- O365ITProTrain
- httpsfix
ms.assetid: 53d3eef6-4a16-4fb9-903c-816d5d98d7e8
description: 'Samenvatting: verbinding maken met alle Microsoft 365-services in een enkel PowerShell-venster.'
ms.openlocfilehash: 923e4bc39ae4391d4deaa2c232e19b9479c2efbe
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/20/2021
ms.locfileid: "52583122"
---
# <a name="connect-to-all-microsoft-365-services-in-a-single-powershell-window"></a><span data-ttu-id="b6441-103">Verbinding maken met alle Microsoft 365-services in een enkel PowerShell-venster</span><span class="sxs-lookup"><span data-stu-id="b6441-103">Connect to all Microsoft 365 services in a single PowerShell window</span></span>

<span data-ttu-id="b6441-104">Wanneer u PowerShell gebruikt om Microsoft 365 te beheren, kunt u meerdere PowerShell-sessies tegelijk openen.</span><span class="sxs-lookup"><span data-stu-id="b6441-104">When you use PowerShell to manage Microsoft 365, you can have multiple PowerShell sessions open at the same time.</span></span> <span data-ttu-id="b6441-105">Mogelijk hebt u verschillende PowerShell-Vensters voor het beheren van gebruikersaccounts, SharePoint Online, Exchange Online, Skype voor Bedrijven Online, Microsoft Teams en het Beveiligings- &amp;en compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="b6441-105">You might have different PowerShell windows to manage user accounts, SharePoint Online, Exchange Online, Skype for Business Online, Microsoft Teams, and the Security &amp; Compliance center.</span></span>
  
<span data-ttu-id="b6441-106">Dit is niet optimaal voor het beheer van Microsoft 365, omdat u geen gegevens kunt uitwisselen tussen deze vensters voor servicebeheer.</span><span class="sxs-lookup"><span data-stu-id="b6441-106">This scenario isn't optimal for managing Microsoft 365, because you can't exchange data among those windows for cross-service management.</span></span> <span data-ttu-id="b6441-107">In dit artikel wordt beschreven hoe u één exemplaar van Windows PowerShell kunt gebruiken waarmee u Microsoft 365-accounts, Skype voor Bedrijven Online, Exchange Online, SharePoint Online, Microsoft Teams en het Beveiligings- &amp;en compliancecentrum kunt beheren.</span><span class="sxs-lookup"><span data-stu-id="b6441-107">This article describes how to use a single instance of PowerShell to manage Microsoft 365 accounts, Skype for Business Online, Exchange Online, SharePoint Online, Microsoft Teams, and the Security &amp; Compliance Center.</span></span>

>[!Note]
><span data-ttu-id="b6441-108">Dit artikel bevat momenteel alleen de opdrachten om verbinding te maken met de wereldwijde (+GCC) cloud.</span><span class="sxs-lookup"><span data-stu-id="b6441-108">This article currently only contains the commands to connect to the Worldwide (+GCC) cloud.</span></span> <span data-ttu-id="b6441-109">Notities bevatten koppelingen naar artikelen over het maken van verbinding met de andere Microsoft 365-clouds.</span><span class="sxs-lookup"><span data-stu-id="b6441-109">Notes provide links to articles about connecting to the other Microsoft 365 clouds.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="b6441-110">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="b6441-110">Before you begin</span></span>

<span data-ttu-id="b6441-111">Voordat u Microsoft 365 vanuit één exemplaar van Windows PowerShell kunt beheren, moet u rekening houden met de volgende vereisten:</span><span class="sxs-lookup"><span data-stu-id="b6441-111">Before you can manage all of Microsoft 365 from a single instance of PowerShell, consider the following prerequisites:</span></span>
  
- <span data-ttu-id="b6441-112">Het werk- of schoolaccount van Microsoft 365 dat u gebruikt, moet lid zijn van een Microsoft 365-beheerdersrol.</span><span class="sxs-lookup"><span data-stu-id="b6441-112">The Microsoft 365 work or school account that you use must be a member of a Microsoft 365 admin role.</span></span> <span data-ttu-id="b6441-113">Raadpleeg [Over beheerdersrollen](../admin/add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="b6441-113">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span> <span data-ttu-id="b6441-114">Dit is een vereiste voor PowerShell voor Microsoft 365, niet per se voor alle andere Microsoft 365-services.</span><span class="sxs-lookup"><span data-stu-id="b6441-114">This is a requirement for PowerShell for Microsoft 365, but not necessarily for all other Microsoft 365 services.</span></span>
    
- <span data-ttu-id="b6441-115">U kunt de volgende 64-bits versies van Windows gebruiken:</span><span class="sxs-lookup"><span data-stu-id="b6441-115">You can use the following 64-bit versions of Windows:</span></span>
    
  - <span data-ttu-id="b6441-116">Windows 10</span><span class="sxs-lookup"><span data-stu-id="b6441-116">Windows 10</span></span>
    
  - <span data-ttu-id="b6441-117">Windows 8.1 of Windows 8</span><span class="sxs-lookup"><span data-stu-id="b6441-117">Windows 8.1 or Windows 8</span></span>
    
  - <span data-ttu-id="b6441-118">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="b6441-118">Windows Server 2019</span></span>
    
  - <span data-ttu-id="b6441-119">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="b6441-119">Windows Server 2016</span></span>
    
  - <span data-ttu-id="b6441-120">Windows Server 2012 R2 of Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="b6441-120">Windows Server 2012 R2 or Windows Server 2012</span></span>
    
  - <span data-ttu-id="b6441-121">Windows 7 Service Pack 1 (SP1)\*</span><span class="sxs-lookup"><span data-stu-id="b6441-121">Windows 7 Service Pack 1 (SP1)\*</span></span>
    
  - <span data-ttu-id="b6441-122">Windows Server 2008 R2 SP1\*</span><span class="sxs-lookup"><span data-stu-id="b6441-122">Windows Server 2008 R2 SP1\*</span></span>
    
    <span data-ttu-id="b6441-123">\* U moet Microsoft .NET Framework 4.5 *x* installeren en vervolgens Windows Management Framework 3.0 of 4.0.</span><span class="sxs-lookup"><span data-stu-id="b6441-123">\* You need to install Microsoft .NET Framework 4.5.*x* and then Windows Management Framework 3.0 or 4.0.</span></span> <span data-ttu-id="b6441-124">Zie [Windows Management Framework](/powershell/scripting/windows-powershell/wmf/overview)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="b6441-124">For more information, see [Windows Management Framework](/powershell/scripting/windows-powershell/wmf/overview).</span></span>
    
    <span data-ttu-id="b6441-125">U moet een 64-bits versie van Windows gebruiken vanwege de vereisten voor de module Skype voor Bedrijven Online en een van de Microsoft 365-modules.</span><span class="sxs-lookup"><span data-stu-id="b6441-125">You need to use a 64-bit version of Windows because of the requirements for the Skype for Business Online module and one of the Microsoft 365 modules.</span></span>
    
- <span data-ttu-id="b6441-126">U moet de modules installeren die vereist zijn voor Azure Active Directory (Azure AD), Exchange Online, SharePoint Online, Skype voor Bedrijven Online en Teams:</span><span class="sxs-lookup"><span data-stu-id="b6441-126">You need to install the modules that are required for Azure Active Directory (Azure AD), Exchange Online, SharePoint Online, Skype for Business Online and Teams:</span></span>
    
  - [<span data-ttu-id="b6441-127">Azure Active Directory V2</span><span class="sxs-lookup"><span data-stu-id="b6441-127">Azure Active Directory V2</span></span>](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  - [<span data-ttu-id="b6441-128">SharePoint Online Management Shell</span><span class="sxs-lookup"><span data-stu-id="b6441-128">SharePoint Online Management Shell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=255251)
  - [<span data-ttu-id="b6441-129">Skype voor Bedrijven Online, Windows PowerShell-module</span><span class="sxs-lookup"><span data-stu-id="b6441-129">Skype for Business Online, PowerShell Module</span></span>](/microsoftteams/teams-powershell-overview)
  - [<span data-ttu-id="b6441-130">Exchange Online PowerShell V2</span><span class="sxs-lookup"><span data-stu-id="b6441-130">Exchange Online PowerShell V2</span></span>](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exchange-online-powershell-v2-module)
  - [<span data-ttu-id="b6441-131">Overzicht van PowerShell voor Teams</span><span class="sxs-lookup"><span data-stu-id="b6441-131">Teams PowerShell Overview</span></span>](/microsoftteams/teams-powershell-overview)
    
-  <span data-ttu-id="b6441-132">Windows PowerShell moet worden geconfigureerd voor het uitvoeren van ondertekende scripts voor Skype voor Bedrijven Online en het Beveiligings- &amp; en compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="b6441-132">PowerShell must be configured to run signed scripts for Skype for Business Online and the Security &amp; Compliance Center.</span></span> <span data-ttu-id="b6441-133">Voer de volgende opdracht uit in een Windows PowerShell-sessie met een verhoogde bevoegdheid (een Windows PowerShell-sessie die u **Als beheerder uitvoert**).</span><span class="sxs-lookup"><span data-stu-id="b6441-133">Run the following command in an elevated PowerShell session (a PowerShell session that you **Run as administrator**).</span></span>
    
   ```powershell
   Set-ExecutionPolicy RemoteSigned
   ```

## <a name="connection-steps-when-using-just-a-password"></a><span data-ttu-id="b6441-134">Verbindingsstappen als u alleen een wachtwoord gebruikt</span><span class="sxs-lookup"><span data-stu-id="b6441-134">Connection steps when using just a password</span></span>

<span data-ttu-id="b6441-135">Hier volgen de stappen voor het maken van verbinding met alle services in één PowerShell-venster wanneer u alleen een wachtwoord gebruikt voor aanmelding.</span><span class="sxs-lookup"><span data-stu-id="b6441-135">Follow these steps to connect to all the services in a single PowerShell window when you're using just a password for sign-in.</span></span>
  
1. <span data-ttu-id="b6441-136">Open Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b6441-136">Open Windows PowerShell.</span></span>
    
2. <span data-ttu-id="b6441-137">Voer deze opdracht uit en voer de referenties voor uw werk- of schoolaccount van Microsoft 365 in.</span><span class="sxs-lookup"><span data-stu-id="b6441-137">Run this command and enter your Microsoft 365 work or school account credentials.</span></span>
    
   ```powershell
   $credential = Get-Credential
   ```

3. <span data-ttu-id="b6441-138">Voer deze opdracht uit om verbinding te maken met Azure AD met behulp van de Azure Active Directory PowerShell voor Graph-module.</span><span class="sxs-lookup"><span data-stu-id="b6441-138">Run this command to connect to Azure AD by using the Azure Active Directory PowerShell for Graph module.</span></span>
    
   ```powershell
   Connect-AzureAD -Credential $credential
   ```
  
   <span data-ttu-id="b6441-139">Als u de Microsoft Azure Active Directory-module voor Windows PowerShell gebruikt, voert u de volgende opdracht uit.</span><span class="sxs-lookup"><span data-stu-id="b6441-139">Or if you're using the Microsoft Azure Active Directory Module for Windows PowerShell module, run this command.</span></span>
      
   ```powershell
   Connect-MsolService -Credential $credential
   ```

   > [!Note]
   > <span data-ttu-id="b6441-140">PowerShell Core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell en cmdlets met *Msol* in hun naam.</span><span class="sxs-lookup"><span data-stu-id="b6441-140">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="b6441-141">Voer deze cmdlets uit vanuit Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b6441-141">You must run these cmdlets from PowerShell.</span></span>

4. <span data-ttu-id="b6441-142">Voer deze opdrachten uit om verbinding te maken met SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="b6441-142">Run these commands to connect to SharePoint Online.</span></span> <span data-ttu-id="b6441-143">Geef de naam van de organisatie op voor uw domein.</span><span class="sxs-lookup"><span data-stu-id="b6441-143">Specify the organization name for your domain.</span></span> <span data-ttu-id="b6441-144">Voor 'litwareinc\.onmicrosoft.com' is de waarde van de organisatienaam bijvoorbeeld 'litwareinc'.</span><span class="sxs-lookup"><span data-stu-id="b6441-144">For example, for "litwareinc\.onmicrosoft.com", the  organization name value is "litwareinc".</span></span>
    
   ```powershell
   $orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
   Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
   Connect-SPOService -Url https://$orgName-admin.sharepoint.com -Credential $Credential
   ```

5. <span data-ttu-id="b6441-145">Voer deze opdrachten uit om verbinding te maken met Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b6441-145">Run these commands to connect to Exchange Online.</span></span>
    
   ```powershell
   Import-Module ExchangeOnlineManagement
   Connect-ExchangeOnline -ShowProgress $true
   ```

   > [!Note]
   > <span data-ttu-id="b6441-146">Zie [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) om verbinding te maken met andere Exchange Online voor Microsoft 365-clouds dan wereldwijd.</span><span class="sxs-lookup"><span data-stu-id="b6441-146">To connect to Exchange Online for Microsoft 365 clouds other than Worldwide, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

6. <span data-ttu-id="b6441-147">Voer deze opdrachten uit om verbinding te maken met het Beveiligings- en compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="b6441-147">Run these commands to connect to the Security &amp; Compliance Center.</span></span>
    
   ```powershell
   $acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
   Connect-IPPSSession -UserPrincipalName $acctName
   ```

   > [!Note]
   > <span data-ttu-id="b6441-148">Zie [Verbinding maken Beveiligings- en compliancecentrum Powershell](/powershell/exchange/connect-to-scc-powershell)om verbinding maken met andere Beveiligings-&amp; en compliancecentrum voor Microsoft 365-clouds dan wereldwijd.</span><span class="sxs-lookup"><span data-stu-id="b6441-148">To connect to the Security &amp; Compliance Center for Microsoft 365 clouds other than Worldwide, see [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

7. <span data-ttu-id="b6441-149">Voer deze opdrachten uit om verbinding te maken met Teams PowerShell (en Skype voor Bedrijven Online).</span><span class="sxs-lookup"><span data-stu-id="b6441-149">Run these commands to connect to Teams PowerShell (and Skype for Business Online).</span></span>
    
   ```powershell
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
  
   > [!Note]
   > <span data-ttu-id="b6441-150">Skype voor Bedrijven Online-connector maakt momenteel deel uit van de nieuwste Teams PowerShell-module.</span><span class="sxs-lookup"><span data-stu-id="b6441-150">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="b6441-151">Als u de meest recente openbare versie van Teams PowerShell gebruikt, hoeft u de Skype voor Bedrijven Online-connector niet te installeren.</span><span class="sxs-lookup"><span data-stu-id="b6441-151">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
  
   > [!Note]
   > <span data-ttu-id="b6441-152">Zie [Connect-MicrosoftTeams](/powershell/module/teams/connect-microsoftteams) om verbinding te maken met andere Microsoft Teams-clouds dan *Worldwide*.</span><span class="sxs-lookup"><span data-stu-id="b6441-152">To connect to Microsoft Teams clouds other than *Worldwide*, see [Connect-MicrosoftTeams](/powershell/module/teams/connect-microsoftteams).</span></span>
  


### <a name="azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="b6441-153">Azure Active Directory PowerShell voor Graph-module</span><span class="sxs-lookup"><span data-stu-id="b6441-153">Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="b6441-154">Dit zijn de opdrachten voor alle services in één blok als u de Azure Active Directory PowerShell voor Graph-module gebruikt.</span><span class="sxs-lookup"><span data-stu-id="b6441-154">Here are the commands for all the services in a single block when you use the Azure Active Directory PowerShell for Graph module.</span></span> <span data-ttu-id="b6441-155">Geef de naam op van uw domeinhost en de UPN voor het aanmelden en voer ze allemaal tegelijk uit.</span><span class="sxs-lookup"><span data-stu-id="b6441-155">Specify the name of your domain host and the UPN for the sign-in and run them all at the same time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName -Message "Type the account's password."
#Azure Active Directory
Connect-AzureAD -Credential $credential
#SharePoint Online
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -ShowProgress $true
#Security & Compliance Center
Connect-IPPSSession -UserPrincipalName $acctName
#Teams and Skype for Business Online
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a><span data-ttu-id="b6441-156">Microsoft Azure Active Directory-module voor Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b6441-156">Microsoft Azure Active Directory Module for Windows PowerShell module</span></span>

<span data-ttu-id="b6441-157">Dit zijn de opdrachten voor alle services in één blok als u de Microsoft Azure Active Directory-module voor Windows PowerShell gebruikt.</span><span class="sxs-lookup"><span data-stu-id="b6441-157">Here are the commands for all the services in a single block when you use the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span> <span data-ttu-id="b6441-158">Geef de naam op van uw domeinhost en de UPN voor het aanmelden en voer ze allemaal tegelijk uit.</span><span class="sxs-lookup"><span data-stu-id="b6441-158">Specify the name of your domain host and the UPN for the sign-in and run them all at one time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName -Message "Type the account's password."
#Azure Active Directory
Connect-MsolService -Credential $credential
#SharePoint Online
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -ShowProgress $true
#Security & Compliance Center
Connect-IPPSSession -UserPrincipalName $acctName
#Teams and Skype for Business Online
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

## <a name="connection-steps-when-using-multi-factor-authentication"></a><span data-ttu-id="b6441-159">Verbindingsstappen als u meervoudige verificatie gebruikt</span><span class="sxs-lookup"><span data-stu-id="b6441-159">Connection steps when using multi-factor authentication</span></span>

### <a name="azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="b6441-160">Azure Active Directory PowerShell voor Graph-module</span><span class="sxs-lookup"><span data-stu-id="b6441-160">Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="b6441-161">Dit zijn de opdrachten in één blok voor alle services om verbinding te maken met meerdere Microsoft 365-services met meervoudige verificatie als u de Azure Active Directory PowerShell voor Graph-module gebruikt.</span><span class="sxs-lookup"><span data-stu-id="b6441-161">Here are all the commands in a single block to connect to multiple Microsoft 365 services when you use multi-factor authentication with the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-AzureAD
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Security & Compliance Center
Connect-IPPSSession -UserPrincipalName $acctName
#Teams and Skype for Business Online
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a><span data-ttu-id="b6441-162">Microsoft Azure Active Directory-module voor Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b6441-162">Microsoft Azure Active Directory Module for Windows PowerShell module</span></span>

<span data-ttu-id="b6441-163">Dit zijn de opdrachten in één blok voor alle services om verbinding te maken met meerdere Microsoft 365-services met meervoudige verificatie als u de Microsoft Azure Active Directory-module voor Windows PowerShell gebruikt.</span><span class="sxs-lookup"><span data-stu-id="b6441-163">Here are all the commands in a single block to connect to multiple Microsoft 365 services when you use multi-factor authentication with the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span>

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-MsolService
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Security & Compliance Center
Connect-IPPSSession -UserPrincipalName $acctName
#Teams and Skype for Business Online
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```

## <a name="close-the-powershell-window"></a><span data-ttu-id="b6441-164">Powershell-venster sluiten</span><span class="sxs-lookup"><span data-stu-id="b6441-164">Close the PowerShell window</span></span>

<span data-ttu-id="b6441-165">Om het Windows PowerShell-venster te sluiten, voert u deze opdracht uit om de actieve sessies naar Skype voor Bedrijven Online, SharePoint Online en Teams te verwijderen:</span><span class="sxs-lookup"><span data-stu-id="b6441-165">To close down the PowerShell window, run this command to remove the active sessions to Skype for Business Online, SharePoint Online, and Teams:</span></span>
  
```powershell
Remove-PSSession $sfboSession ; Disconnect-SPOService ; Disconnect-MicrosoftTeams 
```

## <a name="see-also"></a><span data-ttu-id="b6441-166">Zie ook</span><span class="sxs-lookup"><span data-stu-id="b6441-166">See also</span></span>

- [<span data-ttu-id="b6441-167">Verbinding maken met Microsoft 365 met PowerShell</span><span class="sxs-lookup"><span data-stu-id="b6441-167">Connect to Microsoft 365 with PowerShell</span></span>](connect-to-microsoft-365-powershell.md)
- [<span data-ttu-id="b6441-168">SharePoint Online beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="b6441-168">Manage SharePoint Online with PowerShell</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)
- [<span data-ttu-id="b6441-169">Microsoft 365-gebruikersaccounts, -licenties en -groepen beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="b6441-169">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
