---
title: Verbinding maken met alle Microsoft 365-services in een enkel PowerShell-venster
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/10/2020
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
ms.openlocfilehash: 08d2f4c6ce67aa9fea196d56b2eb5f36a36d7943
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430044"
---
# <a name="connect-to-all-microsoft-365-services-in-a-single-powershell-window"></a><span data-ttu-id="b72a4-103">Verbinding maken met alle Microsoft 365-services in een enkel PowerShell-venster</span><span class="sxs-lookup"><span data-stu-id="b72a4-103">Connect to all Microsoft 365 services in a single PowerShell window</span></span>

<span data-ttu-id="b72a4-104">Wanneer u PowerShell gebruikt om Microsoft 365 te beheren, is het mogelijk om meerdere Windows PowerShell-sessies tegelijkertijd open te hebben die overeenkomen met het beheren van gebruikersaccounts, SharePoint Online, Exchange Online, Skype voor Bedrijven Online, Microsoft Teams en het Beveiligings- &amp; en compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="b72a4-104">When you use PowerShell to manage Microsoft 365, it is possible to have multiple PowerShell sessions open at the same time in different PowerShell windows corresponding to managing user accounts, SharePoint Online, Exchange Online, Skype for Business Online, Microsoft Teams, and the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="b72a4-105">Dit is niet optimaal voor het beheer van Microsoft 365, omdat u geen gegevens kunt uitwisselen tussen deze vensters voor servicebeheer.</span><span class="sxs-lookup"><span data-stu-id="b72a4-105">This is not optimal for managing Microsoft 365 because you can't exchange data among those windows for cross-service management.</span></span> <span data-ttu-id="b72a4-106">In dit onderwerp wordt beschreven hoe u één exemplaar van Windows PowerShell kunt gebruiken van waaruit u Microsoft 365-accounts, Skype voor Bedrijven Online, Exchange Online, SharePoint Online, Microsoft Teams en het Beveiligings- &amp;en compliancecentrum kunt beheren.</span><span class="sxs-lookup"><span data-stu-id="b72a4-106">This topic describes how to use a single instance of PowerShell from which you can manage Microsoft 365 accounts, Skype for Business Online, Exchange Online, SharePoint Online, Microsoft Teams, and the Security &amp; Compliance Center.</span></span>

>[!Note]
><span data-ttu-id="b72a4-107">Dit artikel bevat momenteel alleen de opdrachten om verbinding te maken met de wereldwijde (+GCC) cloud.</span><span class="sxs-lookup"><span data-stu-id="b72a4-107">This article currently only contains the commands to connect to the Worldwide (+GCC) cloud.</span></span> <span data-ttu-id="b72a4-108">Notities bevatten koppelingen naar artikelen met informatie over het maken van verbinding met de andere Microsoft 365-clouds.</span><span class="sxs-lookup"><span data-stu-id="b72a4-108">Notes provide links to articles with information about connecting to the other Microsoft 365 clouds.</span></span>
>

## <a name="before-you-begin"></a><span data-ttu-id="b72a4-109">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="b72a4-109">Before you begin</span></span>

<span data-ttu-id="b72a4-110">Voordat u Microsoft 365 vanuit één exemplaar van Windows PowerShell kunt beheren, moet u rekening houden met de volgende vereisten:</span><span class="sxs-lookup"><span data-stu-id="b72a4-110">Before you can manage all of Microsoft 365 from a single instance of PowerShell, consider the following prerequisites:</span></span>
  
- <span data-ttu-id="b72a4-111">Het werk- of schoolaccount van Microsoft 365 dat u voor deze procedures gebruikt, moet lid zijn van een Microsoft 365-beheerdersrol.</span><span class="sxs-lookup"><span data-stu-id="b72a4-111">The Microsoft 365 work or school account that you use for these procedures needs to be a member of a Microsoft 365 admin role.</span></span> <span data-ttu-id="b72a4-112">Raadpleeg [Over beheerdersrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="b72a4-112">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span> <span data-ttu-id="b72a4-113">Dit is een vereiste voor PowerShell voor Microsoft 365, niet per se voor alle andere Microsoft 365-services.</span><span class="sxs-lookup"><span data-stu-id="b72a4-113">This a requirement for PowerShell for Microsoft 365, not necessarily for all other Microsoft 365 services.</span></span>
    
- <span data-ttu-id="b72a4-114">U kunt de volgende 64-bits versies van Windows gebruiken:</span><span class="sxs-lookup"><span data-stu-id="b72a4-114">You can use the following 64-bit versions of Windows:</span></span>
    
  - <span data-ttu-id="b72a4-115">Windows 10</span><span class="sxs-lookup"><span data-stu-id="b72a4-115">Windows 10</span></span>
    
  - <span data-ttu-id="b72a4-116">Windows 8.1 of Windows 8</span><span class="sxs-lookup"><span data-stu-id="b72a4-116">Windows 8.1 or Windows 8</span></span>
    
  - <span data-ttu-id="b72a4-117">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="b72a4-117">Windows Server 2019</span></span>
    
  - <span data-ttu-id="b72a4-118">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="b72a4-118">Windows Server 2016</span></span>
    
  - <span data-ttu-id="b72a4-119">Windows Server 2012 R2 of Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="b72a4-119">Windows Server 2012 R2 or Windows Server 2012</span></span>
    
  - <span data-ttu-id="b72a4-120">Windows 7 Service Pack 1 (SP1)\*</span><span class="sxs-lookup"><span data-stu-id="b72a4-120">Windows 7 Service Pack 1 (SP1)\*</span></span>
    
  - <span data-ttu-id="b72a4-121">Windows Server 2008 R2 SP1\*</span><span class="sxs-lookup"><span data-stu-id="b72a4-121">Windows Server 2008 R2 SP1\*</span></span>
    
    <span data-ttu-id="b72a4-122">\* U moet Microsoft .NET Framework 4.5 installeren.*x* en vervolgens Windows Management Framework 3.0 of Windows Management Framework 4.0.</span><span class="sxs-lookup"><span data-stu-id="b72a4-122">\* You need to install the Microsoft .NET Framework 4.5.*x* and then either the Windows Management Framework 3.0 or the Windows Management Framework 4.0.</span></span> <span data-ttu-id="b72a4-123">Zie [.NET Framework installeren](https://go.microsoft.com/fwlink/p/?LinkId=257868) en [Windows Management Framework 3.0](https://go.microsoft.com/fwlink/p/?LinkId=272757) of [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/p/?LinkId=391344) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="b72a4-123">For more information, see [Installing the .NET Framework](https://go.microsoft.com/fwlink/p/?LinkId=257868) and [Windows Management Framework 3.0](https://go.microsoft.com/fwlink/p/?LinkId=272757) or [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/p/?LinkId=391344).</span></span>
    
    <span data-ttu-id="b72a4-124">U moet een 64-bits versie van Windows gebruiken vanwege de vereisten voor de module Skype voor Bedrijven Online en een van de Microsoft 365-modules.</span><span class="sxs-lookup"><span data-stu-id="b72a4-124">You need to use a 64-bit version of Windows because of the requirements for the Skype for Business Online module and one of the Microsoft 365 modules.</span></span>
    
- <span data-ttu-id="b72a4-125">U moet de modules installeren die vereist zijn voor Azure Active Directory (Azure AD), Exchange Online, SharePoint Online, Skype voor Bedrijven Online en Teams:</span><span class="sxs-lookup"><span data-stu-id="b72a4-125">You need to install the modules that are required for Azure Active Directory (Azure AD), Exchange Online, SharePoint Online, Skype for Business Online and Teams:</span></span>
    
   - [<span data-ttu-id="b72a4-126">Azure Active Directory V2</span><span class="sxs-lookup"><span data-stu-id="b72a4-126">Azure Active Directory V2</span></span>](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
   - [<span data-ttu-id="b72a4-127">SharePoint Online Management Shell</span><span class="sxs-lookup"><span data-stu-id="b72a4-127">SharePoint Online Management Shell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=255251)
   - [<span data-ttu-id="b72a4-128">Skype voor Bedrijven Online, Windows PowerShell-module</span><span class="sxs-lookup"><span data-stu-id="b72a4-128">Skype for Business Online, PowerShell Module</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=532439)
   - [<span data-ttu-id="b72a4-129">Exchange Online PowerShell V2</span><span class="sxs-lookup"><span data-stu-id="b72a4-129">Exchange Online PowerShell V2</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2#install-and-maintain-the-exchange-online-powershell-v2-module)
   - [<span data-ttu-id="b72a4-130">Overzicht van PowerShell voor Teams</span><span class="sxs-lookup"><span data-stu-id="b72a4-130">Teams PowerShell Overview</span></span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview)
    
-  <span data-ttu-id="b72a4-131">Windows PowerShell moet worden geconfigureerd voor het uitvoeren van ondertekende scripts voor Skype voor Bedrijven Online en het Beveiligings- &amp; en compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="b72a4-131">PowerShell needs to be configured to run signed scripts for Skype for Business Online and the Security &amp; Compliance Center.</span></span> <span data-ttu-id="b72a4-132">U doet dit door de volgende opdracht uit te voeren in een Windows PowerShell-sessie met een verhoogde bevoegdheid (een Windows PowerShell-venster dat u opent door **Als beheerder uitvoeren** te selecteren).</span><span class="sxs-lookup"><span data-stu-id="b72a4-132">To do this, run the following command in an elevated PowerShell session (a PowerShell window you open by selecting **Run as administrator**).</span></span>
    
   ```powershell
   Set-ExecutionPolicy RemoteSigned
   ```

## <a name="exchange-online-and-security-amp-compliance-center-with-the-exchange-online-powershell-v2-module"></a><span data-ttu-id="b72a4-133">Exchange Online en Beveiligings- &amp; en compliancecentrum met Exchange Online PowerShell V2-module</span><span class="sxs-lookup"><span data-stu-id="b72a4-133">Exchange Online and Security &amp; Compliance Center with the Exchange Online PowerShell V2 module</span></span>

<span data-ttu-id="b72a4-134">Dit artikel verbindt Exchange Online PowerShell V2-module met zowel Exchange Online als Beveiligings- &amp;en compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="b72a4-134">This article uses the Exchange Online PowerShell V2 module to connect to both Exchange Online and Security &amp; Compliance Center.</span></span> <span data-ttu-id="b72a4-135">Momenteel kan er\*\*in hetzelfde PowerShell-venster \*\*geen verbinding worden gemaakt met zowel Exchange Online als het Beveiligings- &amp;en compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="b72a4-135">However, at this time you cannot connect to both Exchange Online and the Security &amp; Compliance Center **in the same PowerShell window**.</span></span>

<span data-ttu-id="b72a4-136">Verbind met Exchange Online *of* Beveiligings- &amp;en compliancecentrum tijdens het configureren van een PowerShell-venster voor meerdere Microsoft 365-services.</span><span class="sxs-lookup"><span data-stu-id="b72a4-136">Therefore, you must choose a connection with either Exchange Online *or* the Security &amp; Compliance Center when configuring a PowerShell window for multiple Microsoft 365 services.</span></span>

## <a name="connection-steps-when-using-just-a-password"></a><span data-ttu-id="b72a4-137">Verbindingsstappen als u alleen een wachtwoord gebruikt</span><span class="sxs-lookup"><span data-stu-id="b72a4-137">Connection steps when using just a password</span></span>

<span data-ttu-id="b72a4-138">Hier volgen de stappen voor het maken van verbinding met alle services in één PowerShell-venster wanneer u alleen een wachtwoord gebruikt voor aanmelding.</span><span class="sxs-lookup"><span data-stu-id="b72a4-138">Here are the steps to connect to all the services in a single PowerShell window when you are using just a password for sign-in.</span></span>
  
1. <span data-ttu-id="b72a4-139">Open Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b72a4-139">Open Windows PowerShell.</span></span>
    
2. <span data-ttu-id="b72a4-140">Voer deze opdracht uit en voer de referenties voor uw werk- of schoolaccount van Microsoft 365 in.</span><span class="sxs-lookup"><span data-stu-id="b72a4-140">Run this command and enter your Microsoft 365 work or school account credentials.</span></span>
    
   ```powershell
   $credential = Get-Credential
   ```

3. <span data-ttu-id="b72a4-141">Voer deze opdracht uit om verbinding te maken met Azure AD met de Azure Active Directory PowerShell voor Graph-module.</span><span class="sxs-lookup"><span data-stu-id="b72a4-141">Run this command to connect to Azure AD using the Azure Active Directory PowerShell for Graph module.</span></span>
    
   ```powershell
   Connect-AzureAD -Credential $credential
   ```
  
   <span data-ttu-id="b72a4-142">Als u de Microsoft Azure Active Directory-module voor Windows PowerShell gebruikt, voert u deze opdracht uit.</span><span class="sxs-lookup"><span data-stu-id="b72a4-142">Alternately, if you are using the Microsoft Azure Active Directory Module for Windows PowerShell module, run this command.</span></span>
      
   ```powershell
   Connect-MsolService -Credential $credential
   ```

   > [!Note]
   > <span data-ttu-id="b72a4-143">PowerShell Core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell en cmdlets met **Msol** in hun naam.</span><span class="sxs-lookup"><span data-stu-id="b72a4-143">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="b72a4-144">Als u deze cmdlets wilt blijven gebruiken, moet u deze uitvoeren vanuit Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b72a4-144">To continue using these cmdlets, you must run them from PowerShell.</span></span>

4. <span data-ttu-id="b72a4-145">Voer deze opdrachten uit om verbinding te maken met SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="b72a4-145">Run these commands to connect to SharePoint Online.</span></span> <span data-ttu-id="b72a4-146">Geef de naam van de organisatie op voor uw domein.</span><span class="sxs-lookup"><span data-stu-id="b72a4-146">Specify the organization name for your domain.</span></span> <span data-ttu-id="b72a4-147">Voor 'litwareinc.onmicrosoft.com' is de waarde van de organisatienaam bijvoorbeeld 'litwareinc'.</span><span class="sxs-lookup"><span data-stu-id="b72a4-147">For example, for "litwareinc.onmicrosoft.com", the  organization name value is "litwareinc".</span></span>
    
   ```powershell
   $orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
   Connect-SPOService -Url https://$orgName-admin.sharepoint.com -Credential $userCredential
   ```

5. <span data-ttu-id="b72a4-148">Voer deze opdrachten uit om verbinding te maken met Skype voor Bedrijven Online.</span><span class="sxs-lookup"><span data-stu-id="b72a4-148">Run these commands to connect to Skype for Business Online.</span></span> <span data-ttu-id="b72a4-149">Een waarschuwing over het verhogen van de `WSMan NetworkDelayms`-waarde wordt verwacht als u voor het eerst verbinding maakt; deze waarschuwing kunt u negeren.</span><span class="sxs-lookup"><span data-stu-id="b72a4-149">A warning about increasing the `WSMan NetworkDelayms` value is expected the first time you connect and should be ignored.</span></span>
     
   ```powershell
   Import-Module SkypeOnlineConnector
   $sfboSession = New-CsOnlineSession -Credential $credential
   Import-PSSession $sfboSession
   ```

6. <span data-ttu-id="b72a4-150">Voer deze opdracht uit om verbinding te maken met Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b72a4-150">Run this command to connect to Exchange Online.</span></span>
    
   ```powershell
   Import-Module ExchangeOnlineManagement
   Connect-ExchangeOnline -Credential $credential -ShowProgress $true
   ```

   > [!Note]
   > <span data-ttu-id="b72a4-151">Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) om verbinding te maken met andere Exchange Online voor Microsoft 365-clouds dan wereldwijd.</span><span class="sxs-lookup"><span data-stu-id="b72a4-151">To connect to Exchange Online for Microsoft 365 clouds other than Worldwide, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

7. <span data-ttu-id="b72a4-152">U kunt ook deze opdrachten uitvoeren om verbinding te maken met het Beveiligings-&amp; en compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="b72a4-152">Alternately, run these commands to connect to the Security &amp; Compliance Center.</span></span>
    
   ```powershell
   $acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
   Import-Module ExchangeOnlineManagement
   Connect-IPPSSession -UserPrincipalName $acctName
   ```

   > [!Note]
   > <span data-ttu-id="b72a4-153">Zie [Verbinding maken Beveiligings- en compliancecentrum Powershell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)om verbinding maken met andere Beveiligings-&amp; en compliancecentrum voor Microsoft 365-clouds dan wereldwijd.</span><span class="sxs-lookup"><span data-stu-id="b72a4-153">To connect to the Security &amp; Compliance Center for Microsoft 365 clouds other than Worldwide, see [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

8. <span data-ttu-id="b72a4-154">Voer deze opdrachten uit om verbinding te maken met PowerShell voor Teams.</span><span class="sxs-lookup"><span data-stu-id="b72a4-154">Run these commands to connect to Teams PowerShell.</span></span>
    
   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams -Credential $credential
   ```
  
   > [!Note]
   > <span data-ttu-id="b72a4-155">Zie [Verbinding maken met Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams) om verbinding te maken met andere Microsoft Teams-clouds dan 'Worldwide'.</span><span class="sxs-lookup"><span data-stu-id="b72a4-155">To connect to Microsoft Teams clouds other than Worldwide, see [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams).</span></span>


### <a name="azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="b72a4-156">Azure Active Directory PowerShell voor Graph-module</span><span class="sxs-lookup"><span data-stu-id="b72a4-156">Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="b72a4-157">Dit zijn de opdrachten voor alle services *behalve Beveiligings- &amp; en compliancecentrum* in één blok als Azure Active Directory PowerShell voor Graph-module wordt gebruikt.</span><span class="sxs-lookup"><span data-stu-id="b72a4-157">Here are the commands for all of the services *except Security &amp; Compliance Center* in a single block when using the Azure Active Directory PowerShell for Graph module.</span></span> <span data-ttu-id="b72a4-158">Geef de naam op van uw domeinhost en voer ze allemaal tegelijk uit.</span><span class="sxs-lookup"><span data-stu-id="b72a4-158">Specify the name of your domain host, and then run them all at one time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$credential = Get-Credential
Connect-AzureAD -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module SkypeOnlineConnector
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -Credential $credential -ShowProgress $true
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

<span data-ttu-id="b72a4-159">Dit zijn de opdrachten voor alle services *behalve Exchange Online* in één blok als Azure Active Directory PowerShell voor Graph-module wordt gebruikt.</span><span class="sxs-lookup"><span data-stu-id="b72a4-159">Here are the commands for all of the services *except Exchange Online* in a single block when using the Azure Active Directory PowerShell for Graph module.</span></span> <span data-ttu-id="b72a4-160">Geef de naam op van uw domeinhost en UPN voor het aanmelden en voer ze allemaal tegelijk uit.</span><span class="sxs-lookup"><span data-stu-id="b72a4-160">Specify the name of your domain host and the UPN for the sign-in, and then run them all at one time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName
Connect-AzureAD -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module SkypeOnlineConnector
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a><span data-ttu-id="b72a4-161">Microsoft Azure Active Directory-module voor Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b72a4-161">Microsoft Azure Active Directory Module for Windows PowerShell module</span></span>

<span data-ttu-id="b72a4-162">Dit zijn de opdrachten voor alle services *behalve Beveiligings- &amp; en compliancecentrum* in één blok als Microsoft Azure Active Directory-module voor Windows PowerShell wordt gebruikt.</span><span class="sxs-lookup"><span data-stu-id="b72a4-162">Here are the commands for all of the services *except Security &amp; Compliance Center* in a single block when using the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span> <span data-ttu-id="b72a4-163">Geef de naam op van uw domeinhost en voer ze allemaal tegelijk uit.</span><span class="sxs-lookup"><span data-stu-id="b72a4-163">Specify the name of your domain host, and then run them all at one time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$credential = Get-Credential
Connect-MsolService -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module SkypeOnlineConnector
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -Credential $credential -ShowProgress $true
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

<span data-ttu-id="b72a4-164">Dit zijn de opdrachten voor alle services *behalve Exchange Online* in één blok als Microsoft Azure Active Directory-module voor Windows PowerShell wordt gebruikt.</span><span class="sxs-lookup"><span data-stu-id="b72a4-164">Here are the commands for all of the services *except Exchange Online* in a single block when using the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span> <span data-ttu-id="b72a4-165">Geef de naam op van uw domeinhost en UPN voor het aanmelden en voer ze allemaal tegelijk uit.</span><span class="sxs-lookup"><span data-stu-id="b72a4-165">Specify the name of your domain host and the UPN for the sign-in, and then run them all at one time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName
Connect-AzureAD -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module SkypeOnlineConnector
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```
## <a name="connection-steps-when-using-multi-factor-authentication"></a><span data-ttu-id="b72a4-166">Verbindingsstappen als u meervoudige verificatie gebruikt</span><span class="sxs-lookup"><span data-stu-id="b72a4-166">Connection steps when using multi-factor authentication</span></span>

### <a name="azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="b72a4-167">Azure Active Directory PowerShell voor Graph-module</span><span class="sxs-lookup"><span data-stu-id="b72a4-167">Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="b72a4-168">Dit zijn de opdrachten in één blok voor alle services om verbinding te maken met meerdere Microsoft 365-services *behalve Beveiligings- &amp; en compliancecentrum* met meervoudige verificatie als Azure Active Directory PowerShell voor Graph-module wordt gebruikt.</span><span class="sxs-lookup"><span data-stu-id="b72a4-168">Here are all the commands in a single block to connect to multiple Microsoft 365 services *except Security &amp; Compliance Center* with multi-factor authentication using the Azure Active Directory PowerShell for Graph module.</span></span>

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
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
<span data-ttu-id="b72a4-169">Dit zijn de opdrachten in één blok voor alle services om verbinding te maken met meerdere Microsoft 365-services *behalve Exchange Online* met meervoudige verificatie als Azure Active Directory PowerShell voor Graph-module wordt gebruikt.</span><span class="sxs-lookup"><span data-stu-id="b72a4-169">Here are all the commands in a single block to connect to multiple Microsoft 365 services *except Exchange Online* with multi-factor authentication using the Azure Active Directory PowerShell for Graph module.</span></span>

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
#Security & Compliance Center
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a><span data-ttu-id="b72a4-170">Microsoft Azure Active Directory-module voor Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b72a4-170">Microsoft Azure Active Directory Module for Windows PowerShell module</span></span>

<span data-ttu-id="b72a4-171">Dit zijn de opdrachten in één blok voor alle services om verbinding te maken met meerdere Microsoft 365-services *behalve Beveiligings- &amp; en compliancecentrum* met meervoudige verificatie als Microsoft Azure Active Directory-module voor Windows PowerShell wordt gebruikt.</span><span class="sxs-lookup"><span data-stu-id="b72a4-171">Here are all the commands in a single block to connect to multiple Microsoft 365 services *except Security &amp; Compliance Center* with multi-factor authentication using the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span>

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
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
<span data-ttu-id="b72a4-172">Dit zijn de opdrachten in één blok voor alle services om verbinding te maken met meerdere Microsoft 365-services *behalve Exchange Online* met meervoudige verificatie als Microsoft Azure Active Directory-module voor Windows PowerShell wordt gebruikt.</span><span class="sxs-lookup"><span data-stu-id="b72a4-172">Here are all the commands in a single block to connect to multiple Microsoft 365 services *except Exchange Online* using multi-factor authentication with the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span>

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
#Security & Compliance Center
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```

## <a name="close-the-powershell-window"></a><span data-ttu-id="b72a4-173">Powershell-venster sluiten</span><span class="sxs-lookup"><span data-stu-id="b72a4-173">Close the PowerShell window</span></span>

<span data-ttu-id="b72a4-174">Wanneer u gereed bent om het Windows PowerShell-venster te sluiten, voert u deze opdracht uit om de actieve sessies naar Skype voor Bedrijven Online, SharePoint Online en Teams over te slaan:</span><span class="sxs-lookup"><span data-stu-id="b72a4-174">When you are ready to close down the PowerShell window, run this command to remove the active sessions to Skype for Business Online, SharePoint Online, and Teams:</span></span>
  
```powershell
Remove-PSSession $sfboSession ; Disconnect-SPOService ; Disconnect-MicrosoftTeams 
```


## <a name="see-also"></a><span data-ttu-id="b72a4-175">Zie ook</span><span class="sxs-lookup"><span data-stu-id="b72a4-175">See also</span></span>

- [<span data-ttu-id="b72a4-176">Verbinding maken met Microsoft 365 met PowerShell</span><span class="sxs-lookup"><span data-stu-id="b72a4-176">Connect to Microsoft 365 with PowerShell</span></span>](connect-to-microsoft-365-powershell.md)
- [<span data-ttu-id="b72a4-177">SharePoint Online beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="b72a4-177">Manage SharePoint Online with PowerShell</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)
- [<span data-ttu-id="b72a4-178">Microsoft 365-gebruikersaccounts, -licenties en -groepen beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="b72a4-178">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
