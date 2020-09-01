---
title: Verbinding maken met alle Microsoft 365-services in een enkel PowerShell-venster
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/26/2020
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
ms.openlocfilehash: af676434017cbe7025baa5e8509e6203a5d59674
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/29/2020
ms.locfileid: "47307623"
---
# <a name="connect-to-all-microsoft-365-services-in-a-single-powershell-window"></a><span data-ttu-id="ef8f1-103">Verbinding maken met alle Microsoft 365-services in een enkel PowerShell-venster</span><span class="sxs-lookup"><span data-stu-id="ef8f1-103">Connect to all Microsoft 365 services in a single PowerShell window</span></span>

<span data-ttu-id="ef8f1-104">Wanneer u PowerShell gebruikt om Microsoft 365 te beheren, is het mogelijk om meerdere Windows PowerShell-sessies tegelijkertijd open te hebben die overeenkomen met het beheren van gebruikersaccounts, SharePoint Online, Exchange Online, Skype voor Bedrijven Online, Microsoft Teams en het Beveiligings- &amp; en compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="ef8f1-104">When you use PowerShell to manage Microsoft 365, it is possible to have multiple PowerShell sessions open at the same time in different PowerShell windows corresponding to managing user accounts, SharePoint Online, Exchange Online, Skype for Business Online, Microsoft Teams, and the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="ef8f1-105">Dit is niet optimaal voor het beheer van Microsoft 365, omdat u geen gegevens kunt uitwisselen tussen deze vensters voor servicebeheer.</span><span class="sxs-lookup"><span data-stu-id="ef8f1-105">This is not optimal for managing Microsoft 365 because you can't exchange data among those windows for cross-service management.</span></span> <span data-ttu-id="ef8f1-106">In dit onderwerp wordt beschreven hoe u één exemplaar van Windows PowerShell kunt gebruiken van waaruit u Microsoft 365-accounts, Skype voor Bedrijven Online, Exchange Online, SharePoint Online, Microsoft Teams en het Beveiligings- &amp;en compliancecentrum kunt beheren.</span><span class="sxs-lookup"><span data-stu-id="ef8f1-106">This topic describes how to use a single instance of PowerShell from which you can manage Microsoft 365 accounts, Skype for Business Online, Exchange Online, SharePoint Online, Microsoft Teams, and the Security &amp; Compliance Center.</span></span>

>[!Note]
><span data-ttu-id="ef8f1-107">Dit artikel bevat momenteel alleen de opdrachten om verbinding te maken met de wereldwijde (+GCC) cloud.</span><span class="sxs-lookup"><span data-stu-id="ef8f1-107">This article currently only contains the commands to connect to the Worldwide (+GCC) cloud.</span></span> <span data-ttu-id="ef8f1-108">Notities bevatten koppelingen naar artikelen met informatie over het maken van verbinding met de andere Microsoft 365-clouds.</span><span class="sxs-lookup"><span data-stu-id="ef8f1-108">Notes provide links to articles with information about connecting to the other Microsoft 365 clouds.</span></span>
>

## <a name="before-you-begin"></a><span data-ttu-id="ef8f1-109">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="ef8f1-109">Before you begin</span></span>

<span data-ttu-id="ef8f1-110">Voordat u Microsoft 365 vanuit één exemplaar van Windows PowerShell kunt beheren, moet u rekening houden met de volgende vereisten:</span><span class="sxs-lookup"><span data-stu-id="ef8f1-110">Before you can manage all of Microsoft 365 from a single instance of PowerShell, consider the following prerequisites:</span></span>
  
- <span data-ttu-id="ef8f1-111">Het werk- of schoolaccount van Microsoft 365 dat u voor deze procedures gebruikt, moet lid zijn van een Microsoft 365-beheerdersrol.</span><span class="sxs-lookup"><span data-stu-id="ef8f1-111">The Microsoft 365 work or school account that you use for these procedures needs to be a member of a Microsoft 365 admin role.</span></span> <span data-ttu-id="ef8f1-112">Raadpleeg [Over beheerdersrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="ef8f1-112">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide).</span></span> <span data-ttu-id="ef8f1-113">Dit is een vereiste voor PowerShell voor Microsoft 365, niet per se voor alle andere Microsoft 365-services.</span><span class="sxs-lookup"><span data-stu-id="ef8f1-113">This a requirement for PowerShell for Microsoft 365, not necessarily for all other Microsoft 365 services.</span></span>
    
- <span data-ttu-id="ef8f1-114">U kunt de volgende 64-bits versies van Windows gebruiken:</span><span class="sxs-lookup"><span data-stu-id="ef8f1-114">You can use the following 64-bit versions of Windows:</span></span>
    
  - <span data-ttu-id="ef8f1-115">Windows 10</span><span class="sxs-lookup"><span data-stu-id="ef8f1-115">Windows 10</span></span>
    
  - <span data-ttu-id="ef8f1-116">Windows 8.1 of Windows 8</span><span class="sxs-lookup"><span data-stu-id="ef8f1-116">Windows 8.1 or Windows 8</span></span>
    
  - <span data-ttu-id="ef8f1-117">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="ef8f1-117">Windows Server 2019</span></span>
    
  - <span data-ttu-id="ef8f1-118">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="ef8f1-118">Windows Server 2016</span></span>
    
  - <span data-ttu-id="ef8f1-119">Windows Server 2012 R2 of Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="ef8f1-119">Windows Server 2012 R2 or Windows Server 2012</span></span>
    
  - <span data-ttu-id="ef8f1-120">Windows 7 Service Pack 1 (SP1)\*</span><span class="sxs-lookup"><span data-stu-id="ef8f1-120">Windows 7 Service Pack 1 (SP1)\*</span></span>
    
  - <span data-ttu-id="ef8f1-121">Windows Server 2008 R2 SP1\*</span><span class="sxs-lookup"><span data-stu-id="ef8f1-121">Windows Server 2008 R2 SP1\*</span></span>
    
    <span data-ttu-id="ef8f1-122">\* U moet Microsoft .NET Framework 4.5 installeren.*x* en vervolgens Windows Management Framework 3.0 of Windows Management Framework 4.0.</span><span class="sxs-lookup"><span data-stu-id="ef8f1-122">\* You need to install the Microsoft .NET Framework 4.5.*x* and then either the Windows Management Framework 3.0 or the Windows Management Framework 4.0.</span></span> <span data-ttu-id="ef8f1-123">Zie [.NET Framework installeren](https://go.microsoft.com/fwlink/p/?LinkId=257868) en [Windows Management Framework 3.0](https://go.microsoft.com/fwlink/p/?LinkId=272757) of [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/p/?LinkId=391344) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="ef8f1-123">For more information, see [Installing the .NET Framework](https://go.microsoft.com/fwlink/p/?LinkId=257868) and [Windows Management Framework 3.0](https://go.microsoft.com/fwlink/p/?LinkId=272757) or [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/p/?LinkId=391344).</span></span>
    
    <span data-ttu-id="ef8f1-124">U moet een 64-bits versie van Windows gebruiken vanwege de vereisten voor de module Skype voor Bedrijven Online en een van de Microsoft 365-modules.</span><span class="sxs-lookup"><span data-stu-id="ef8f1-124">You need to use a 64-bit version of Windows because of the requirements for the Skype for Business Online module and one of the Microsoft 365 modules.</span></span>
    
- <span data-ttu-id="ef8f1-125">U moet de modules installeren die vereist zijn voor Azure Active Directory (Azure AD), Exchange Online, SharePoint Online, Skype voor Bedrijven Online en Teams:</span><span class="sxs-lookup"><span data-stu-id="ef8f1-125">You need to install the modules that are required for Azure Active Directory (Azure AD), Exchange Online, SharePoint Online, Skype for Business Online and Teams:</span></span>
    
   - [<span data-ttu-id="ef8f1-126">Azure Active Directory V2</span><span class="sxs-lookup"><span data-stu-id="ef8f1-126">Azure Active Directory V2</span></span>](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
   - [<span data-ttu-id="ef8f1-127">SharePoint Online Management Shell</span><span class="sxs-lookup"><span data-stu-id="ef8f1-127">SharePoint Online Management Shell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=255251)
   - [<span data-ttu-id="ef8f1-128">Skype voor Bedrijven Online, Windows PowerShell-module</span><span class="sxs-lookup"><span data-stu-id="ef8f1-128">Skype for Business Online, PowerShell Module</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=532439)
   - [<span data-ttu-id="ef8f1-129">Exchange Online PowerShell V2</span><span class="sxs-lookup"><span data-stu-id="ef8f1-129">Exchange Online PowerShell V2</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module)
   - [<span data-ttu-id="ef8f1-130">Overzicht van PowerShell voor Teams</span><span class="sxs-lookup"><span data-stu-id="ef8f1-130">Teams PowerShell Overview</span></span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview)
    
-  <span data-ttu-id="ef8f1-131">Windows PowerShell moet worden geconfigureerd voor het uitvoeren van ondertekende scripts voor Skype voor Bedrijven Online en het Beveiligings- &amp; en compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="ef8f1-131">PowerShell needs to be configured to run signed scripts for Skype for Business Online and the Security &amp; Compliance Center.</span></span> <span data-ttu-id="ef8f1-132">U doet dit door de volgende opdracht uit te voeren in een Windows PowerShell-sessie met een verhoogde bevoegdheid (een Windows PowerShell-venster dat u opent door **Als beheerder uitvoeren** te selecteren).</span><span class="sxs-lookup"><span data-stu-id="ef8f1-132">To do this, run the following command in an elevated PowerShell session (a PowerShell window you open by selecting **Run as administrator**).</span></span>
    
   ```powershell
   Set-ExecutionPolicy RemoteSigned
   ```

## <a name="connection-steps-when-using-just-a-password"></a><span data-ttu-id="ef8f1-133">Verbindingsstappen als u alleen een wachtwoord gebruikt</span><span class="sxs-lookup"><span data-stu-id="ef8f1-133">Connection steps when using just a password</span></span>

<span data-ttu-id="ef8f1-134">Hier volgen de stappen voor het maken van verbinding met alle services in één PowerShell-venster wanneer u alleen een wachtwoord gebruikt voor aanmelding.</span><span class="sxs-lookup"><span data-stu-id="ef8f1-134">Here are the steps to connect to all the services in a single PowerShell window when you are using just a password for sign-in.</span></span>
  
1. <span data-ttu-id="ef8f1-135">Open Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ef8f1-135">Open Windows PowerShell.</span></span>
    
2. <span data-ttu-id="ef8f1-136">Voer deze opdracht uit en voer de referenties voor uw werk- of schoolaccount van Microsoft 365 in.</span><span class="sxs-lookup"><span data-stu-id="ef8f1-136">Run this command and enter your Microsoft 365 work or school account credentials.</span></span>
    
   ```powershell
   $credential = Get-Credential
   ```

3. <span data-ttu-id="ef8f1-137">Voer deze opdracht uit om verbinding te maken met Azure AD met de Azure Active Directory PowerShell voor Graph-module.</span><span class="sxs-lookup"><span data-stu-id="ef8f1-137">Run this command to connect to Azure AD using the Azure Active Directory PowerShell for Graph module.</span></span>
    
   ```powershell
   Connect-AzureAD -Credential $credential
   ```
  
   <span data-ttu-id="ef8f1-138">Als u de Microsoft Azure Active Directory-module voor Windows PowerShell gebruikt, voert u deze opdracht uit.</span><span class="sxs-lookup"><span data-stu-id="ef8f1-138">Alternately, if you are using the Microsoft Azure Active Directory Module for PowerShell module, run this command.</span></span>
      
   ```powershell
   Connect-MsolService -Credential $credential
   ```

   > [!Note]
   > <span data-ttu-id="ef8f1-139">PowerShell Core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell en cmdlets met **Msol** in hun naam.</span><span class="sxs-lookup"><span data-stu-id="ef8f1-139">PowerShell Core does not support the Microsoft Azure Active Directory Module for PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="ef8f1-140">Als u deze cmdlets wilt blijven gebruiken, moet u deze uitvoeren vanuit Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ef8f1-140">To continue using these cmdlets, you must run them from PowerShell.</span></span>

4. <span data-ttu-id="ef8f1-141">Voer deze opdrachten uit om verbinding te maken met SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="ef8f1-141">Run these commands to connect to SharePoint Online.</span></span> <span data-ttu-id="ef8f1-142">Geef de naam van de organisatie op voor uw domein.</span><span class="sxs-lookup"><span data-stu-id="ef8f1-142">Specify the organization name for your domain.</span></span> <span data-ttu-id="ef8f1-143">Voor 'litwareinc.onmicrosoft.com' is de waarde van de organisatienaam bijvoorbeeld 'litwareinc'.</span><span class="sxs-lookup"><span data-stu-id="ef8f1-143">For example, for "litwareinc.onmicrosoft.com", the  organization name value is "litwareinc".</span></span>
    
   ```powershell
   $orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
   Connect-SPOService -Url https://$orgName-admin.sharepoint.com -Credential $userCredential
   ```

5. <span data-ttu-id="ef8f1-144">Voer deze opdrachten uit om verbinding te maken met Skype voor Bedrijven Online.</span><span class="sxs-lookup"><span data-stu-id="ef8f1-144">Run these commands to connect to Skype for Business Online.</span></span> <span data-ttu-id="ef8f1-145">Een waarschuwing over het verhogen van de `WSMan NetworkDelayms`-waarde wordt verwacht als u voor het eerst verbinding maakt; deze waarschuwing kunt u negeren.</span><span class="sxs-lookup"><span data-stu-id="ef8f1-145">A warning about increasing the `WSMan NetworkDelayms` value is expected the first time you connect and should be ignored.</span></span>
     
   ```powershell
   Import-Module SkypeOnlineConnector
   $sfboSession = New-CsOnlineSession -Credential $credential
   Import-PSSession $sfboSession
   ```

6. <span data-ttu-id="ef8f1-146">Voer deze opdracht uit om verbinding te maken met Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ef8f1-146">Run this command to connect to Exchange Online.</span></span>
    
   ```powershell
   Connect-ExchangeOnline -Credential $credential -ShowProgress $true
   ```

   > [!Note]
   > <span data-ttu-id="ef8f1-147">Als u verbinding wilt maken met andere Exchange Online voor Microsoft 365-clouds dan 'Worldwide', gebruikt u de **ExchangeEnvironmentName**-parameter.</span><span class="sxs-lookup"><span data-stu-id="ef8f1-147">To connect to Exchange Online for Microsoft 365 clouds other than Worldwide, use the **-ExchangeEnvironmentName** parameter.</span></span> <span data-ttu-id="ef8f1-148">Zie [Verbinding maken met Exchange Online](https://docs.microsoft.com/powershell/module/exchange/powershell-v2-module/connect-exchangeonline?view=exchange-ps) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="ef8f1-148">See [Connect-ExchangeOnline](https://docs.microsoft.com/powershell/module/exchange/powershell-v2-module/connect-exchangeonline?view=exchange-ps) for more information.</span></span>

7. <span data-ttu-id="ef8f1-149">Voer deze opdrachten uit om verbinding te maken met PowerShell voor Teams.</span><span class="sxs-lookup"><span data-stu-id="ef8f1-149">Run these commands to connect to Teams PowerShell.</span></span>
    
   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams -Credential $credential
   ```
  
   > [!Note]
   > <span data-ttu-id="ef8f1-150">Zie [Verbinding maken met Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps) om verbinding te maken met andere Microsoft Teams-clouds dan 'Worldwide'.</span><span class="sxs-lookup"><span data-stu-id="ef8f1-150">To connect to Microsoft Teams clouds other than Worldwide, see [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps).</span></span>

8. <span data-ttu-id="ef8f1-151">Voer deze opdrachten uit om verbinding te maken met het Beveiligings- en compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="ef8f1-151">Run these commands to connect to the Security &amp; Compliance Center.</span></span>
    
   ```powershell
   $SccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $credential -Authentication "Basic" -AllowRedirection
   Import-PSSession $SccSession -Prefix cc
   ```

   > [!Note]
   > <span data-ttu-id="ef8f1-152">Raadpleeg dit artikel over [het verbinding maken met Powershell voor het Beveiligings- en compliancecentrum](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) (Engelstalig) om verbinding te maken met het Beveiligings- en compliancecentrum voor andere Microsoft 365-clouds dan 'Worldwide'.</span><span class="sxs-lookup"><span data-stu-id="ef8f1-152">To connect to the Security &amp; Compliance Center for Microsoft 365 clouds other than Worldwide, see [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

<span data-ttu-id="ef8f1-153">Hier vindt u alle opdrachten in één blok wanneer u de Azure Active Directory PowerShell voor Graph-module gebruikt.</span><span class="sxs-lookup"><span data-stu-id="ef8f1-153">Here are all the commands in a single block when using the Azure Active Directory PowerShell for Graph module.</span></span> <span data-ttu-id="ef8f1-154">Geef de naam op van uw domeinhost en voer ze allemaal tegelijk uit.</span><span class="sxs-lookup"><span data-stu-id="ef8f1-154">Specify the name of your domain host, and then run them all at one time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$credential = Get-Credential
Connect-AzureAD -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module SkypeOnlineConnector
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
$SccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $credential -Authentication "Basic" -AllowRedirection
Import-PSSession $SccSession -Prefix cc
Connect-ExchangeOnline -Credential $credential -ShowProgress $true
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

<span data-ttu-id="ef8f1-155">U ziet hier ook alle opdrachten in één blok bij gebruik van de Microsoft Azure Active Directory-module voor Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ef8f1-155">Alternately, here are all the commands in a single block when using the Microsoft Azure Active Directory Module for PowerShell module.</span></span> <span data-ttu-id="ef8f1-156">Geef de naam op van uw domeinhost en voer ze allemaal tegelijk uit.</span><span class="sxs-lookup"><span data-stu-id="ef8f1-156">Specify the name of your domain host, and then run them all at one time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$credential = Get-Credential
Connect-MsolService -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module SkypeOnlineConnector
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
$SccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $credential -Authentication "Basic" -AllowRedirection
Import-PSSession $SccSession -Prefix cc
Connect-ExchangeOnline -Credential $credential -ShowProgress $true
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

<span data-ttu-id="ef8f1-157">Wanneer u gereed bent om het Windows PowerShell-venster te sluiten, voert u deze opdracht uit om de actieve sessies naar Skype voor Bedrijven Online, SharePoint Online, het Beveiligings- &amp; en compliancecentrum en Teams te verwijderen:</span><span class="sxs-lookup"><span data-stu-id="ef8f1-157">When you are ready to close down the PowerShell window, run this command to remove the active sessions to Skype for Business Online, SharePoint Online, the Security &amp; Compliance Center, and Teams:</span></span>
  
```powershell
Remove-PSSession $sfboSession ; Remove-PSSession $SccSession ; Disconnect-SPOService ; Disconnect-MicrosoftTeams 
```

## <a name="connection-steps-when-using-multi-factor-authentication"></a><span data-ttu-id="ef8f1-158">Verbindingsstappen wanneer u meervoudige verificatie gebruikt</span><span class="sxs-lookup"><span data-stu-id="ef8f1-158">Connection steps when using multi-factor authentication</span></span>

<span data-ttu-id="ef8f1-159">Hier vindt u alle opdrachten in één blok om verbinding te maken met Azure AD, SharePoint Online, Skype voor Bedrijven, Exchange Online en Teams met behulp van meervoudige verificatie in één venster met de Azure Active Directory PowerShell voor Graph-module.</span><span class="sxs-lookup"><span data-stu-id="ef8f1-159">Here are all the commands in a single block to connect to Azure AD, SharePoint Online, Skype for Business, Exchange Online, and Teams using multi-factor authentication in a single window using the Azure Active Directory PowerShell for Graph module.</span></span> <span data-ttu-id="ef8f1-160">Geef de UPN-naam (User Principal Name) op van een gebruikersaccount en de naam van uw domeinhost en voer ze vervolgens allemaal tegelijk uit.</span><span class="sxs-lookup"><span data-stu-id="ef8f1-160">Specify the user principal name (UPN) name of a user account and your domain host name, and then run them all at one time.</span></span>

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-AzureAD
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
$sfboSession = New-CsOnlineSession -UserName $acctName
Import-PSSession $sfboSession
#Exchange Online
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```

<span data-ttu-id="ef8f1-161">U ziet hier ook alle opdrachten bij gebruik van de Microsoft Azure Active Directory-module voor Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ef8f1-161">Alternately, here are all the commands when using the Microsoft Azure Active Directory Module for PowerShell module.</span></span>

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-MsolService
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
$sfboSession = New-CsOnlineSession -UserName $acctName
Import-PSSession $sfboSession
#Exchange Online
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```

<span data-ttu-id="ef8f1-162">Zie voor het Beveiligings- en compliancecentrum dit artikel over [het verbinding maken met Powershell voor het Beveiligings- en compliancecentrum met behulp van meervoudige verificatie](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell?view=exchange-ps) (Engelstalig) om verbinding te maken met behulp van meervoudige verificatie:</span><span class="sxs-lookup"><span data-stu-id="ef8f1-162">For the Security &amp; Compliance Center, see [Connect to Security & Compliance Center PowerShell using multi-factor authentication](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell?view=exchange-ps) to connect using multi-factor authentication:</span></span>

## <a name="see-also"></a><span data-ttu-id="ef8f1-163">Zie ook</span><span class="sxs-lookup"><span data-stu-id="ef8f1-163">See also</span></span>

- [<span data-ttu-id="ef8f1-164">Verbinding maken met Microsoft 365 met PowerShell</span><span class="sxs-lookup"><span data-stu-id="ef8f1-164">Connect to Microsoft 365 with PowerShell</span></span>](connect-to-microsoft-365-powershell.md)
- [<span data-ttu-id="ef8f1-165">SharePoint Online beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="ef8f1-165">Manage SharePoint Online with PowerShell</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)
- [<span data-ttu-id="ef8f1-166">Microsoft 365-gebruikersaccounts, -licenties en -groepen beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="ef8f1-166">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
