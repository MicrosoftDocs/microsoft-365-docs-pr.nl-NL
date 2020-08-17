---
title: Verbinding maken met alle Microsoft 365-services in één Windows PowerShell-venster
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/10/2020
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
description: 'Samenvatting: verbindt Windows PowerShell met alle Microsoft 365-services in één Windows PowerShell-venster.'
ms.openlocfilehash: d4e4bf6ec07ee4a0a5b2f8cb1c83ffacd221eaa0
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689304"
---
# <a name="connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window"></a><span data-ttu-id="cf91d-103">Verbinding maken met alle Microsoft 365-services in één Windows PowerShell-venster</span><span class="sxs-lookup"><span data-stu-id="cf91d-103">Connect to all Microsoft 365 services in a single Windows PowerShell window</span></span>

<span data-ttu-id="cf91d-104">Wanneer u PowerShell gebruikt om Microsoft 365 te beheren, is het mogelijk om maximaal vijf verschillende Windows PowerShell-sessies tegelijkertijd open te hebben die overeenkomen met het Microsoft 365-beheercentrum, SharePoint Online, Exchange Online, Skype voor Bedrijven Online, Microsoft Teams en het Beveiligings &amp;-compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="cf91d-104">When you use PowerShell to manage Microsoft 365, it is possible to have up to five different Windows PowerShell sessions open at the same time corresponding to Microsoft 365 admin center, SharePoint Online, Exchange Online, Skype for Business Online, Microsoft Teams, and the Security &amp; Compliance Center.</span></span> <span data-ttu-id="cf91d-105">Met vijf verschillende verbindingsmethoden in afzonderlijke Windows PowerShell-sessies kan het bureaublad er zo uitzien:</span><span class="sxs-lookup"><span data-stu-id="cf91d-105">With five different connection methods in separate Windows PowerShell sessions, your desktop could look like this:</span></span>
  
![Vijf Windows PowerShell-consoles die tegelijk worden uitgevoerd](../media/a1a852c2-89ea-4e8e-8d8b-dcdf596763d1.png)
  
<span data-ttu-id="cf91d-107">Dit is niet optimaal voor het beheer van Microsoft 365, omdat u geen gegevens kunt uitwisselen tussen die vijf vensters voor servicebeheer.</span><span class="sxs-lookup"><span data-stu-id="cf91d-107">This is not optimal for managing Microsoft 365 because you can't exchange data among those five windows for cross-service management.</span></span> <span data-ttu-id="cf91d-108">In dit onderwerp wordt beschreven hoe u één exemplaar van Windows PowerShell gebruikt van waaruit u Microsoft 365-accounts, Skype voor Bedrijven Online, Exchange Online, SharePoint Online, Microsoft Teams en het Beveiligings &amp;-compliancecentrum kunt beheren.</span><span class="sxs-lookup"><span data-stu-id="cf91d-108">This topic describes how to use a single instance of Windows PowerShell from which you can manage Microsoft 365 accounts, Skype for Business Online, Exchange Online, SharePoint Online, Microsoft Teams, and the Security &amp; Compliance Center.</span></span>

>[!Note]
><span data-ttu-id="cf91d-109">Dit artikel bevat momenteel alleen de opdrachten om verbinding te maken met de wereldwijde (+GCC) cloud.</span><span class="sxs-lookup"><span data-stu-id="cf91d-109">This article currently only contains the commands to connect to the Worldwide (+GCC) cloud.</span></span> <span data-ttu-id="cf91d-110">Aanvullende notities bevatten koppelingen naar artikelen met informatie over het maken van verbinding met de andere Microsoft 365-clouds.</span><span class="sxs-lookup"><span data-stu-id="cf91d-110">Additional notes provide links to articles with information about connecting to the other Microsoft 365 clouds.</span></span>
>

## <a name="before-you-begin"></a><span data-ttu-id="cf91d-111">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="cf91d-111">Before you begin</span></span>

<span data-ttu-id="cf91d-112">Voordat u Microsoft 365 vanuit één exemplaar van Windows PowerShell kunt beheren, moet u rekening houden met de volgende vereisten:</span><span class="sxs-lookup"><span data-stu-id="cf91d-112">Before you can manage all of Microsoft 365 from a single instance of Windows PowerShell, consider the following prerequisites:</span></span>
  
- <span data-ttu-id="cf91d-113">Het werk- of schoolaccount van Microsoft 365 dat u voor deze procedures gebruikt, moet lid zijn van een Microsoft 365-beheerdersrol.</span><span class="sxs-lookup"><span data-stu-id="cf91d-113">The Microsoft 365 work or school account that you use for these procedures needs to be a member of a Microsoft 365 admin role.</span></span> <span data-ttu-id="cf91d-114">Raadpleeg [Over beheerdersrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="cf91d-114">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide).</span></span> <span data-ttu-id="cf91d-115">Dit is een vereiste voor PowerShell voor Microsoft 365, niet per se voor alle andere Microsoft 365-services.</span><span class="sxs-lookup"><span data-stu-id="cf91d-115">This a requirement for PowerShell for Microsoft 365, not necessarily for all other Microsoft 365 services.</span></span>
    
- <span data-ttu-id="cf91d-116">U kunt de volgende 64-bits versies van Windows gebruiken:</span><span class="sxs-lookup"><span data-stu-id="cf91d-116">You can use the following 64-bit versions of Windows:</span></span>
    
  - <span data-ttu-id="cf91d-117">Windows 10</span><span class="sxs-lookup"><span data-stu-id="cf91d-117">Windows 10</span></span>
    
  - <span data-ttu-id="cf91d-118">Windows 8.1 of Windows 8</span><span class="sxs-lookup"><span data-stu-id="cf91d-118">Windows 8.1 or Windows 8</span></span>
    
  - <span data-ttu-id="cf91d-119">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="cf91d-119">Windows Server 2019</span></span>
    
  - <span data-ttu-id="cf91d-120">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="cf91d-120">Windows Server 2016</span></span>
    
  - <span data-ttu-id="cf91d-121">Windows Server 2012 R2 of Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="cf91d-121">Windows Server 2012 R2 or Windows Server 2012</span></span>
    
  - <span data-ttu-id="cf91d-122">Windows 7 Service Pack 1 (SP1)\*</span><span class="sxs-lookup"><span data-stu-id="cf91d-122">Windows 7 Service Pack 1 (SP1)\*</span></span>
    
  - <span data-ttu-id="cf91d-123">Windows Server 2008 R2 SP1\*</span><span class="sxs-lookup"><span data-stu-id="cf91d-123">Windows Server 2008 R2 SP1\*</span></span>
    
    <span data-ttu-id="cf91d-124">\* U moet Microsoft .NET Framework 4.5 installeren.*x* en vervolgens Windows Management Framework 3.0 of Windows Management Framework 4.0.</span><span class="sxs-lookup"><span data-stu-id="cf91d-124">\* You need to install the Microsoft .NET Framework 4.5.*x* and then either the Windows Management Framework 3.0 or the Windows Management Framework 4.0.</span></span> <span data-ttu-id="cf91d-125">Zie [.NET Framework installeren](https://go.microsoft.com/fwlink/p/?LinkId=257868) en [Windows Management Framework 3.0](https://go.microsoft.com/fwlink/p/?LinkId=272757) of [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/p/?LinkId=391344) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="cf91d-125">For more information, see [Installing the .NET Framework](https://go.microsoft.com/fwlink/p/?LinkId=257868) and [Windows Management Framework 3.0](https://go.microsoft.com/fwlink/p/?LinkId=272757) or [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/p/?LinkId=391344).</span></span>
    
    <span data-ttu-id="cf91d-126">U moet een 64-bits versie van Windows gebruiken vanwege de vereisten voor de module Skype voor Bedrijven Online en een van de Microsoft 365-modules.</span><span class="sxs-lookup"><span data-stu-id="cf91d-126">You need to use a 64-bit version of Windows because of the requirements for the Skype for Business Online module and one of the Microsoft 365 modules.</span></span>
    
- <span data-ttu-id="cf91d-127">U moet de modules installeren die vereist zijn voor Azure Active Directory (Azure AD), Exchange Online, SharePoint Online, Skype voor Bedrijven Online en Teams:</span><span class="sxs-lookup"><span data-stu-id="cf91d-127">You need to install the modules that are required for Azure Active Directory (Azure AD), Exchange Online, SharePoint Online, Skype for Business Online and Teams:</span></span>
    
   - [<span data-ttu-id="cf91d-128">Azure Active Directory V2</span><span class="sxs-lookup"><span data-stu-id="cf91d-128">Azure Active Directory V2</span></span>](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
   - [<span data-ttu-id="cf91d-129">SharePoint Online Management Shell</span><span class="sxs-lookup"><span data-stu-id="cf91d-129">SharePoint Online Management Shell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=255251)
   - [<span data-ttu-id="cf91d-130">Skype voor Bedrijven Online, Windows PowerShell-module</span><span class="sxs-lookup"><span data-stu-id="cf91d-130">Skype for Business Online, Windows PowerShell Module</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=532439)
   - [<span data-ttu-id="cf91d-131">Exchange Online PowerShell V2</span><span class="sxs-lookup"><span data-stu-id="cf91d-131">Exchange Online PowerShell V2</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module)
   - [<span data-ttu-id="cf91d-132">Overzicht van Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="cf91d-132">Teams PowerShell Overview</span></span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview)
    
-  <span data-ttu-id="cf91d-133">Windows PowerShell moet worden geconfigureerd voor het uitvoeren van ondertekende scripts voor Skype voor Bedrijven Online en Het Beveiligings &amp;-compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="cf91d-133">Windows PowerShell needs to be configured to run signed scripts for Skype for Business Online and the Security &amp; Compliance Center.</span></span> <span data-ttu-id="cf91d-134">U doet dit door de volgende opdracht uit te voeren in een verhoogde Windows PowerShell-sessie (een Windows PowerShell-venster dat u opent door **Als administrator uitvoeren** te selecteren).</span><span class="sxs-lookup"><span data-stu-id="cf91d-134">To do this, run the following command in an elevated Windows PowerShell session (a Windows PowerShell window you open by selecting **Run as administrator**).</span></span>
    
   ```powershell
   Set-ExecutionPolicy RemoteSigned
   ```

## <a name="connection-steps-when-using-just-a-password"></a><span data-ttu-id="cf91d-135">Verbindingsstappen als u alleen een wachtwoord gebruikt</span><span class="sxs-lookup"><span data-stu-id="cf91d-135">Connection steps when using just a password</span></span>

<span data-ttu-id="cf91d-136">Hier volgen de stappen voor het maken van verbinding met alle services in één PowerShell-venster wanneer u alleen een wachtwoord gebruikt voor aanmelding.</span><span class="sxs-lookup"><span data-stu-id="cf91d-136">Here are the steps to connect to all the services in a single PowerShell window when you are using just a password for sign-in.</span></span>
  
1. <span data-ttu-id="cf91d-137">Open Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cf91d-137">Open Windows PowerShell.</span></span>
    
2. <span data-ttu-id="cf91d-138">Voer deze opdracht uit en voer de referenties voor uw werk- of schoolaccount van Microsoft 365 in.</span><span class="sxs-lookup"><span data-stu-id="cf91d-138">Run this command and enter your Microsoft 365 work or school account credentials.</span></span>
    
   ```powershell
   $credential = Get-Credential
   ```

3. <span data-ttu-id="cf91d-139">Voer deze opdracht uit om verbinding te maken met Azure AD met de Azure Active Directory PowerShell voor Graph-module.</span><span class="sxs-lookup"><span data-stu-id="cf91d-139">Run this command to connect to Azure AD using the Azure Active Directory PowerShell for Graph module.</span></span>
    
   ```powershell
   Connect-AzureAD -Credential $credential
   ```
  
   <span data-ttu-id="cf91d-140">Als u de Microsoft Azure Active Directory-module voor Windows PowerShell-module gebruikt, voert u deze opdracht uit.</span><span class="sxs-lookup"><span data-stu-id="cf91d-140">Alternately, if you are using the Microsoft Azure Active Directory Module for Windows PowerShell module, run this command.</span></span>
      
   ```powershell
   Connect-MsolService -Credential $credential
   ```

   > [!Note]
   > <span data-ttu-id="cf91d-141">PowerShell Core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell-module en cmdlets met **Msol** in hun naam.</span><span class="sxs-lookup"><span data-stu-id="cf91d-141">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="cf91d-142">Als u deze cmdlets wilt blijven gebruiken, moet u deze uitvoeren vanuit Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cf91d-142">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>

4. <span data-ttu-id="cf91d-143">Voer deze opdrachten uit om verbinding te maken met SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="cf91d-143">Run these commands to connect to SharePoint Online.</span></span> <span data-ttu-id="cf91d-144">Geef de naam van de organisatie op voor uw domein.</span><span class="sxs-lookup"><span data-stu-id="cf91d-144">Specify the organization name for your domain.</span></span> <span data-ttu-id="cf91d-145">Voor bijvoorbeeld 'litwareinc.onmicrosoft.com' is de waarde van de organisatienaam 'litwareinc'.</span><span class="sxs-lookup"><span data-stu-id="cf91d-145">For example, for "litwareinc.onmicrosoft.com", the  organization name value is "litwareinc".</span></span>
    
   ```powershell
   $orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
   Connect-SPOService -Url https://$orgName-admin.sharepoint.com -Credential $userCredential
   ```

5. <span data-ttu-id="cf91d-146">Voer deze opdrachten uit om verbinding te maken met Skype voor Bedrijven Online.</span><span class="sxs-lookup"><span data-stu-id="cf91d-146">Run these commands to connect to Skype for Business Online.</span></span> <span data-ttu-id="cf91d-147">Een waarschuwing over het verhogen van de `WSMan NetworkDelayms`-waarde wordt verwacht de eerste keer dat u verbinding maakt; deze moet worden genegeerd.</span><span class="sxs-lookup"><span data-stu-id="cf91d-147">A warning about increasing the `WSMan NetworkDelayms` value is expected the first time you connect and should be ignored.</span></span>
     
   ```powershell
   Import-Module SkypeOnlineConnector
   $sfboSession = New-CsOnlineSession -Credential $credential
   Import-PSSession $sfboSession
   ```

6. <span data-ttu-id="cf91d-148">Voer deze opdracht uit om verbinding te maken met Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="cf91d-148">Run this command to connect to Exchange Online.</span></span>
    
   ```powershell
   Connect-ExchangeOnline -Credential $credential -ShowProgress $true
   ```

   > [!Note]
   > <span data-ttu-id="cf91d-149">Als u verbinding wilt maken met Exchange Online voor Microsoft 365-clouds anders dan wereldwijd, gebruikt u de **ExchangeEnvironmentName**-parameter.</span><span class="sxs-lookup"><span data-stu-id="cf91d-149">To connect to Exchange Online for Microsoft 365 clouds other than Worldwide, use the **-ExchangeEnvironmentName** parameter.</span></span> <span data-ttu-id="cf91d-150">Zie [Connect-ExchangeOnline](https://docs.microsoft.com/powershell/module/exchange/powershell-v2-module/connect-exchangeonline?view=exchange-ps) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="cf91d-150">See [Connect-ExchangeOnline](https://docs.microsoft.com/powershell/module/exchange/powershell-v2-module/connect-exchangeonline?view=exchange-ps) for more information.</span></span>

7. <span data-ttu-id="cf91d-151">Voer deze opdrachten uit om verbinding te maken met Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cf91d-151">Run these commands to connect to Teams PowerShell.</span></span>
    
   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams -Credential $credential
   ```
  
   > [!Note]
   > <span data-ttu-id="cf91d-152">Zie [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps) om verbinding te maken met andere Microsoft Teams-clouds dan wereldwijd.</span><span class="sxs-lookup"><span data-stu-id="cf91d-152">To connect to Microsoft Teams clouds other than Worldwide, see [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps).</span></span>

8. <span data-ttu-id="cf91d-153">Voer deze opdrachten uit om verbinding te maken met het Beveiligings &amp;-compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="cf91d-153">Run these commands to connect to the Security &amp; Compliance Center.</span></span>
    
   ```powershell
   $SccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $credential -Authentication "Basic" -AllowRedirection
   Import-PSSession $SccSession -Prefix cc
   ```

   > [!Note]
   > <span data-ttu-id="cf91d-154">Zie [Verbinding maken met Beveiligings- en compliancecentrum PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) om verbinding te maken met het Security &amp; compliancecentrum voor Microsoft 365-clouds anders dan wereldwijd.</span><span class="sxs-lookup"><span data-stu-id="cf91d-154">To connect to the Security &amp; Compliance Center for Microsoft 365 clouds other than Worldwide, see [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

<span data-ttu-id="cf91d-155">Hier vindt u alle opdrachten in één blok wanneer u de Azure Active Directory PowerShell voor Graph-module gebruikt.</span><span class="sxs-lookup"><span data-stu-id="cf91d-155">Here are all the commands in a single block when using the Azure Active Directory PowerShell for Graph module.</span></span> <span data-ttu-id="cf91d-156">Geef de naam op van uw domeinhost en voer ze allemaal tegelijk uit.</span><span class="sxs-lookup"><span data-stu-id="cf91d-156">Specify the name of your domain host, and then run them all at one time.</span></span>
  
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

<span data-ttu-id="cf91d-157">Als alternatief zijn hier alle opdrachten in één blok bij gebruik van de Microsoft Azure Active Directory-module voor Windows PowerShell-module.</span><span class="sxs-lookup"><span data-stu-id="cf91d-157">Alternately, here are all the commands in a single block when using the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span> <span data-ttu-id="cf91d-158">Geef de naam op van uw domeinhost en voer ze allemaal tegelijk uit.</span><span class="sxs-lookup"><span data-stu-id="cf91d-158">Specify the name of your domain host, and then run them all at one time.</span></span>
  
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

<span data-ttu-id="cf91d-159">Wanneer u klaar bent om het Windows PowerShell-venster te sluiten, voert u deze opdracht uit om de actieve sessies naar Skype voor Bedrijven Online, SharePoint Online, het Security &amp;-nalevingscentrum en Teams te verwijderen:</span><span class="sxs-lookup"><span data-stu-id="cf91d-159">When you are ready to close down the Windows PowerShell window, run this command to remove the active sessions to Skype for Business Online, SharePoint Online, the Security &amp; Compliance Center, and Teams:</span></span>
  
```powershell
Remove-PSSession $sfboSession ; Remove-PSSession $SccSession ; Disconnect-SPOService ; Disconnect-MicrosoftTeams 
```

## <a name="connection-steps-when-using-multi-factor-authentication"></a><span data-ttu-id="cf91d-160">Verbindingsstappen wanneer u meervoudige verificatie gebruikt</span><span class="sxs-lookup"><span data-stu-id="cf91d-160">Connection steps when using multi-factor authentication</span></span>

<span data-ttu-id="cf91d-161">Hier vindt u alle opdrachten in één blok om verbinding te maken met Azure AD, SharePoint Online, Skype voor Bedrijven, Exchange Online en Teams met behulp van meervoudige verificatie in één venster met de Azure Active Directory PowerShell voor Graph-module.</span><span class="sxs-lookup"><span data-stu-id="cf91d-161">Here are all the commands in a single block to connect to Azure AD, SharePoint Online, Skype for Business, Exchange Online, and Teams using multi-factor authentication in a single window using the Azure Active Directory PowerShell for Graph module.</span></span> <span data-ttu-id="cf91d-162">Geef de UPN-naam (User Principal Name) op van een gebruikersaccount en de naam van uw domeinhost en voer ze vervolgens allemaal tegelijk uit.</span><span class="sxs-lookup"><span data-stu-id="cf91d-162">Specify the user principal name (UPN) name of a user account and your domain host name, and then run them all at one time.</span></span>

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

<span data-ttu-id="cf91d-163">Als alternatief zijn hier alle opdrachten bij gebruik van de Microsoft Azure Active Directory-module voor Windows PowerShell-module.</span><span class="sxs-lookup"><span data-stu-id="cf91d-163">Alternately, here are all the commands when using the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span>

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

<span data-ttu-id="cf91d-164">Zie voor het Beveiligings &amp;-compliancecentrum [Verbinding maken met Beveiligings- en compliancecentrum PowerShell met behulp van meervoudige verificatie](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell?view=exchange-ps) om verbinding te maken met behulp van meervoudige verificatie:</span><span class="sxs-lookup"><span data-stu-id="cf91d-164">For the Security &amp; Compliance Center, see [Connect to Security & Compliance Center PowerShell using multi-factor authentication](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell?view=exchange-ps) to connect using multi-factor authentication:</span></span>

## <a name="see-also"></a><span data-ttu-id="cf91d-165">Zie ook</span><span class="sxs-lookup"><span data-stu-id="cf91d-165">See also</span></span>

- [<span data-ttu-id="cf91d-166">Verbinding maken met Microsoft 365 met PowerShell</span><span class="sxs-lookup"><span data-stu-id="cf91d-166">Connect to Microsoft 365 with PowerShell</span></span>](connect-to-microsoft-365-powershell.md)
- [<span data-ttu-id="cf91d-167">SharePoint Online beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="cf91d-167">Manage SharePoint Online with PowerShell</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)
- [<span data-ttu-id="cf91d-168">Microsoft 365-gebruikersaccounts, -licenties en -groepen beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="cf91d-168">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
- [<span data-ttu-id="cf91d-169">Windows PowerShell gebruiken om rapporten te maken in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cf91d-169">Use Windows PowerShell to create reports in Microsoft 365</span></span>](use-windows-powershell-to-create-reports-in-microsoft-365.md)
