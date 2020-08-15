---
title: Verbinding maken met Exchange Online-tenants met externe Windows PowerShell voor DAP partners
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: ae5f1a87-8b77-4f93-a1b8-56f800aeb283
description: 'Overzicht: externe Windows PowerShell gebruiken om verbinding te maken met Exchange Online met behulp van de DelegatedOrg-waarde.'
ms.openlocfilehash: 1351a6a6d19fac408b673796c1179bca0ede9c9f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689303"
---
# <a name="connect-to-exchange-online-tenants-with-remote-windows-powershell-for-delegated-access-permissions-dap-partners"></a><span data-ttu-id="00756-103">Verbinding maken met Exchange Online-tenants met Remote Windows PowerShell voor gedelegeerde toegangsmachtigingen (DAP)</span><span class="sxs-lookup"><span data-stu-id="00756-103">Connect to Exchange Online tenants with remote Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>

<span data-ttu-id="00756-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="00756-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

> [!IMPORTANT]
> <span data-ttu-id="00756-105">De procedures in dit onderwerp zijn alleen bedoeld voor partners met een gedelegeerde toegangsrechten (DAP).</span><span class="sxs-lookup"><span data-stu-id="00756-105">The procedures in this topic are only for Delegated Access Permission (DAP) partners.</span></span> <span data-ttu-id="00756-106">Gebruik niet de procedures in dit onderwerp als u geen DAP partner bent.</span><span class="sxs-lookup"><span data-stu-id="00756-106">If you aren't a DAP partner, don't use the procedures in this topic.</span></span> 
  
<span data-ttu-id="00756-107">DAP partners zijn RSS-partners en Cloud solution providers.</span><span class="sxs-lookup"><span data-stu-id="00756-107">DAP partners are Syndication and Cloud Solution Providers (CSP) partners.</span></span> <span data-ttu-id="00756-108">Vaak zijn ze netwerk-of telecommunicatie providers van andere bedrijven.</span><span class="sxs-lookup"><span data-stu-id="00756-108">They are frequently network or telecom providers to other companies.</span></span> <span data-ttu-id="00756-109">Ze bundelt abonnementen in hun serviceaanbiedingen voor hun klanten.</span><span class="sxs-lookup"><span data-stu-id="00756-109">They bundle subscriptions into their service offerings to their customers.</span></span> <span data-ttu-id="00756-110">Ze hebben een partner pacht die automatisch beheer verleent aan de machtigingen van (AOBO) voor hun Microsoft 365 Customer tenancies, zodat ze al hun klant tenancies kunnen beheren en rapporteren.</span><span class="sxs-lookup"><span data-stu-id="00756-110">They own a partner tenancy that is automatically granted Administer On Behalf Of (AOBO) permissions to their Microsoft 365 customer tenancies so they can administer and report on all of their customer tenancies.</span></span>

<span data-ttu-id="00756-111">DAP partners kunnen Exchange Online PowerShell gebruiken voor het beheren van de instellingen van klanten Exchange Online en Microsoft 365-rapporten van de opdrachtregel weergeven.</span><span class="sxs-lookup"><span data-stu-id="00756-111">DAP partners can use Exchange Online PowerShell to manage customer Exchange Online settings and get Microsoft 365 reports from the command line.</span></span> <span data-ttu-id="00756-112">U gebruikt Windows PowerShell op uw lokale computer om een externe PowerShell-sessie te maken voor Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="00756-112">You use Windows PowerShell on your local computer to create a remote PowerShell session to Exchange Online.</span></span> <span data-ttu-id="00756-113">Het is eenvoudig om uw referenties in te voeren, maar u moet de vereiste verbindingsinstellingen opgeven en vervolgens de cmdlets van Exchange Online in uw lokale Windows PowerShell-sessie importeren, zodat u deze kunt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="00756-113">It's a simple three-step process where you enter your credentials, provide the required connection settings, and then import the Exchange Online cmdlets into your local Windows PowerShell session so that you can use them.</span></span>

> [!NOTE]
> <span data-ttu-id="00756-114">DAP partners kunnen de procedures in [verbinding maken met Exchange Online PowerShell met multi-factor Authentication met behulp van multi-factor Authentication](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell) om verbinding te maken met de Tenant-organisaties van de klant in Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="00756-114">DAP partners can't use the procedures in [Connect to Exchange Online PowerShell using multi-factor authentication](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell) to connect to their customer tenant organizations in Exchange Online PowerShell.</span></span> <span data-ttu-id="00756-115">MFA en de Exchange Online Remote PowerShell-module werken niet met gedelegeerde verificatie.</span><span class="sxs-lookup"><span data-stu-id="00756-115">MFA and the Exchange Online Remote PowerShell Module don't work with delegated authentication.</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="00756-116">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="00756-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="00756-117">Geschatte tijdsduur: 5 minuten</span><span class="sxs-lookup"><span data-stu-id="00756-117">Estimated time to complete: 5 minutes</span></span>

- <span data-ttu-id="00756-118">U kunt de volgende versies van Windows gebruiken:</span><span class="sxs-lookup"><span data-stu-id="00756-118">You can use the following versions of Windows:</span></span>
    
  - <span data-ttu-id="00756-119">Windows 10</span><span class="sxs-lookup"><span data-stu-id="00756-119">Windows 10</span></span>

  - <span data-ttu-id="00756-120">Windows 8,1</span><span class="sxs-lookup"><span data-stu-id="00756-120">Windows 8.1</span></span>

  - <span data-ttu-id="00756-121">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="00756-121">Windows Server 2016</span></span>

  - <span data-ttu-id="00756-122">Windows Server 2012 of Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="00756-122">Windows Server 2012 or Windows Server 2012 R2</span></span>

  - <span data-ttu-id="00756-123">Windows 7 Service Pack 1 (SP1)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="00756-123">Windows 7 Service Pack 1 (SP1)<sup>\*</sup></span></span>

  - <span data-ttu-id="00756-124">Windows Server 2008 R2 SP1<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="00756-124">Windows Server 2008 R2 SP1<sup>\*</sup></span></span>

    <span data-ttu-id="00756-125"><sup>\*</sup> Voor oudere versies van Windows moet u Microsoft.NET Framework 4,5 of hoger installeren en vervolgens een bijgewerkte versie van Windows Management Framework: 3,0, 4,0 of 5,1 (maar één).</span><span class="sxs-lookup"><span data-stu-id="00756-125"><sup>\*</sup> For older versions of Windows, you need to install the Microsoft.NET Framework 4.5 or later and then an updated version of the Windows Management Framework: 3.0, 4.0, or 5.1 (only one).</span></span> <span data-ttu-id="00756-126">Zie voor meer informatie [het artikel .NET Framework](https://go.microsoft.com/fwlink/p/?LinkId=257868), [windows Management Framework 3,0](https://go.microsoft.com/fwlink/p/?LinkId=272757), [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/p/?LinkId=391344)en [Windows Management Framework 5,1](https://aka.ms/wmf5download)installeren.</span><span class="sxs-lookup"><span data-stu-id="00756-126">For more information, see [Installing the .NET Framework](https://go.microsoft.com/fwlink/p/?LinkId=257868), [Windows Management Framework 3.0](https://go.microsoft.com/fwlink/p/?LinkId=272757), [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/p/?LinkId=391344), and [Windows Management Framework 5.1](https://aka.ms/wmf5download).</span></span>

- <span data-ttu-id="00756-127">Windows PowerShell moet zijn geconfigureerd voor het uitvoeren van scripts, en dit is standaard niet.</span><span class="sxs-lookup"><span data-stu-id="00756-127">Windows PowerShell needs to be configured to run scripts, and by default, it isn't.</span></span> <span data-ttu-id="00756-128">Wanneer u verbinding probeert te maken, wordt het volgende foutbericht weergegeven:</span><span class="sxs-lookup"><span data-stu-id="00756-128">You'll get the following error when you try to connect:</span></span>

  `Files cannot be loaded because running scripts is disabled on this system. Provide a valid certificate with which to sign the files.`

  <span data-ttu-id="00756-129">Als u wilt dat alle PowerShell-scripts die u downloadt via internet, zijn ondertekend door een vertrouwde uitgever, voert u de volgende opdracht uit in het venster van Windows PowerShell (een Windows PowerShell-venster dat u opent door **als administrator uitvoeren**te selecteren).</span><span class="sxs-lookup"><span data-stu-id="00756-129">To require all PowerShell scripts that you download from the internet are signed by a trusted publisher, run the following command in an elevated Windows PowerShell window (a Windows PowerShell window you open by selecting **Run as administrator**):</span></span>

    ```
    Set-ExecutionPolicy RemoteSigned
    ```

  <span data-ttu-id="00756-130">U hoeft deze instelling maar één keer op uw computer te configureren, niet telkens wanneer u verbinding maakt.</span><span class="sxs-lookup"><span data-stu-id="00756-130">You need to configure this setting only once on your computer, not every time you connect.</span></span>

- <span data-ttu-id="00756-131">Zie [Toetsenbordsneltoetsen in het Exchange-Beheercentrum](https://go.microsoft.com/fwlink/p/?LinkId=534017)voor informatie over toetscombinaties die van toepassing kunnen zijn op de procedures in dit onderwerp.</span><span class="sxs-lookup"><span data-stu-id="00756-131">For information about keyboard shortcuts that might apply to the procedures in this topic, see [Keyboard shortcuts in the Exchange admin center](https://go.microsoft.com/fwlink/p/?LinkId=534017).</span></span>

## <a name="connect-to-exchange-online-for-customer-organizations"></a><span data-ttu-id="00756-132">Verbinding maken met Exchange Online voor klanten organisaties</span><span class="sxs-lookup"><span data-stu-id="00756-132">Connect to Exchange Online for customer organizations</span></span>

1. <span data-ttu-id="00756-133">Open Windows PowerShell op uw lokale computer en voer de volgende opdracht uit.</span><span class="sxs-lookup"><span data-stu-id="00756-133">On your local computer, open Windows PowerShell and run the following command.</span></span>
    
    ```
    $UserCredential = Get-Credential
    ```

    <span data-ttu-id="00756-134">Voer in het dialoogvenster **referentie aanvraag voor Windows PowerShell** uw gebruikersnaam en wachtwoord voor de beheerder van de gebruikersnaam in en klik op **OK**.</span><span class="sxs-lookup"><span data-stu-id="00756-134">In the **Windows PowerShell Credential Request** dialog box, enter your DAP administrator user name and password, and then click **OK**.</span></span>
    
2. <span data-ttu-id="00756-135">Vervang de _\<customer tenant domain name\>_ naam van het Tenant domein waarmee u verbinding wilt maken en voer de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="00756-135">Replace _\<customer tenant domain name\>_ with the name of the tenant domain that you want to connect to, and run the following command:</span></span>
    
    ```
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid?DelegatedOrg=<customer tenant domain name> -Credential $UserCredential -Authentication Basic -AllowRedirection
    ```

    <span data-ttu-id="00756-136">Met de sleutel stap in deze opdracht geeft u aan welke klant toegang heeft voor de rapportagegegevens.</span><span class="sxs-lookup"><span data-stu-id="00756-136">The key step in this command is specifying which customer to access for the reporting information.</span></span> <span data-ttu-id="00756-137">U doet dit in de parameter  _ConnectionURI_ , waarbij u de FQDN van de oorspronkelijke domeinnaam opgeeft als de waarde voor `?DelegatedOrg=` .</span><span class="sxs-lookup"><span data-stu-id="00756-137">You do this in the  _ConnectionURI_ parameter, where you provide the FQDN of the initial domain name as the value for `?DelegatedOrg=`.</span></span> <span data-ttu-id="00756-138">Met deze waarde wordt het juiste Exchange Online PowerShell-eindpunt aangegeven waarmee verbinding moet worden gemaakt.</span><span class="sxs-lookup"><span data-stu-id="00756-138">This value indicates the correct Exchange Online PowerShell endpoint to connect to.</span></span> <span data-ttu-id="00756-139">Externe PowerShell moet in de context van een specifieke klant verbinding maken met Microsoft 365-rapportage wanneer een rapport wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="00756-139">Remote PowerShell must connect to Microsoft 365 reporting in the context of a specific customer each time a report is run.</span></span> <span data-ttu-id="00756-140">Nadat u verbinding hebt gemaakt met Exchange Online PowerShell, worden alle volgende opdrachten uitgevoerd in de context van de klant, zodat u toegang hebt tot alle beschikbare rapporten voor de klant.</span><span class="sxs-lookup"><span data-stu-id="00756-140">After you connect to Exchange Online PowerShell, all subsequent commands are run in the context of the customer, which gives you access to all of the available reports for the customer.</span></span>
    
3. <span data-ttu-id="00756-141">Voer de volgende opdracht uit.</span><span class="sxs-lookup"><span data-stu-id="00756-141">Run the following command.</span></span>
    
    ```
    Import-PSSession $Session
    ```

> [!NOTE]
> <span data-ttu-id="00756-142">U kunt maximaal drie gelijktijdige sessies uitvoeren onder één account.</span><span class="sxs-lookup"><span data-stu-id="00756-142">There's a limit of three simultaneous sessions that can run under one account.</span></span> <span data-ttu-id="00756-143">Zorg ervoor dat u de externe PowerShell-sessie verbreekt wanneer u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="00756-143">Be sure to disconnect the remote PowerShell session when you're finished.</span></span> <span data-ttu-id="00756-144">Als u het venster van Windows PowerShell sluit zonder de sessie te beëindigen, kunt u alle externe PowerShell-sessies gebruiken die beschikbaar zijn voor u, en moet u wachten tot de sessies zijn verlopen.</span><span class="sxs-lookup"><span data-stu-id="00756-144">If you close the Windows PowerShell window without disconnecting the session, you can use up all the remote PowerShell sessions available to you, and you'll need to wait for the sessions to expire.</span></span> <span data-ttu-id="00756-145">Voer de volgende opdracht uit om de externe PowerShell-sessie te verbreken:</span><span class="sxs-lookup"><span data-stu-id="00756-145">To disconnect the remote PowerShell session, run the following command:</span></span>

```
Remove-PSSession $Session
```
  
## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="00756-146">Hoe weet u of dit heeft gewerkt?</span><span class="sxs-lookup"><span data-stu-id="00756-146">How do you know this worked?</span></span>

<span data-ttu-id="00756-147">Na stap 3 worden de cmdlets van Exchange Online in uw lokale Windows PowerShell-sessie geïmporteerd, zoals bijgehouden door een voortgangsbalk.</span><span class="sxs-lookup"><span data-stu-id="00756-147">After Step 3, the Exchange Online cmdlets are imported into your local Windows PowerShell session as tracked by a progress bar.</span></span> <span data-ttu-id="00756-148">Als u geen fouten ontvangt, is er verbinding met internet.</span><span class="sxs-lookup"><span data-stu-id="00756-148">If you don't receive any errors, you connected successfully.</span></span> <span data-ttu-id="00756-149">Een snelle test is het uitvoeren van een cmdlet van Exchange Online (bijvoorbeeld **Get-Mailbox**) en de resultaten te zien.</span><span class="sxs-lookup"><span data-stu-id="00756-149">A quick test is to run an Exchange Online cmdlet (for example, **Get-Mailbox**) and see the results.</span></span>
  
<span data-ttu-id="00756-150">Als u fouten ontvangt, controleert u de volgende vereisten:</span><span class="sxs-lookup"><span data-stu-id="00756-150">If you receive errors, check the following requirements:</span></span>
  
- <span data-ttu-id="00756-151">Een veelvoorkomend probleem is een onjuist wachtwoord.</span><span class="sxs-lookup"><span data-stu-id="00756-151">A common problem is an incorrect password.</span></span> <span data-ttu-id="00756-152">Voer de drie stappen opnieuw uit en Let op de aandacht voor de gebruikersnaam en het wachtwoord die u in stap 1 invoert.</span><span class="sxs-lookup"><span data-stu-id="00756-152">Run the three steps again and pay close attention to the user name and password you enter in Step 1.</span></span>
    
- <span data-ttu-id="00756-153">Het account dat u gebruikt om verbinding te maken met Exchange Online, moet zijn ingeschakeld voor Remote PowerShell.</span><span class="sxs-lookup"><span data-stu-id="00756-153">The account you use to connect to Exchange Online must be enabled for remote PowerShell.</span></span> <span data-ttu-id="00756-154">Zie [toegang tot Exchange Online PowerShell in-of uitschakelen](https://go.microsoft.com/fwlink/p/?LinkId=534018)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="00756-154">For more information, see [Enable or disable access to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=534018).</span></span>
    
- <span data-ttu-id="00756-155">TCP-poort 80 verkeer moet worden geopend tussen uw lokale computer en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="00756-155">TCP port 80 traffic needs to be open between your local computer and Exchange Online.</span></span> <span data-ttu-id="00756-156">Het is waarschijnlijk geopend, maar het is een goed idee om u ervan te bedenken of uw organisatie een beperkt toegangsbeleid voor Internet heeft.</span><span class="sxs-lookup"><span data-stu-id="00756-156">It's probably open, but it's something to consider if your organization has a restrictive Internet access policy.</span></span>
    
## <a name="call-the-cmdlet-directly-with-invoke-command"></a><span data-ttu-id="00756-157">Bel de cmdlet rechtstreeks met de opdracht invoke</span><span class="sxs-lookup"><span data-stu-id="00756-157">Call the cmdlet directly with Invoke-Command</span></span>

<span data-ttu-id="00756-158">Het importeren van een externe PowerShell-sessie (stap 3) kan een langdurige procedure zijn, omdat deze _alle_ cmdlets van Exchange Online overbrengt.</span><span class="sxs-lookup"><span data-stu-id="00756-158">Importing a remote PowerShell session (Step 3) can be a lengthy process because it brings in _all_ Exchange Online cmdlets.</span></span> <span data-ttu-id="00756-159">Dit kan een probleem met de verwerking van batches zijn (bijvoorbeeld wanneer u rapporten uitvoert of bulk wijzigingen aanbrengt voor verschillende tenants).</span><span class="sxs-lookup"><span data-stu-id="00756-159">This can be an issue in batch processing (for example, when you're running reports or making bulk changes for different tenants).</span></span> <span data-ttu-id="00756-160">Als alternatief voor het gebruik van **import-PSSession**kunt u cmdlets bellen die u rechtstreeks wilt gebruiken met de **opdracht invoke**.</span><span class="sxs-lookup"><span data-stu-id="00756-160">As an alternative to using **Import-PSSession**, you can call cmdlets you want to use directly with **Invoke-Command**.</span></span> <span data-ttu-id="00756-161">Als u bijvoorbeeld de cmdlet **Get-Milbox** wilt bellen, vervangt u deze syntaxis voor de `Import-PSSession $Session` opdracht in stap 3:</span><span class="sxs-lookup"><span data-stu-id="00756-161">For example, to call the **Get-Milbox** cmdlet, substitute this syntax for the `Import-PSSession $Session` command in Step 3:</span></span>
  
```
Invoke-Command -Session $Session -ScriptBlock {Get-Mailbox}
```

## <a name="more-reporting-cmdlets"></a><span data-ttu-id="00756-162">Meer cmdlets voor rapporten</span><span class="sxs-lookup"><span data-stu-id="00756-162">More reporting cmdlets</span></span>

<span data-ttu-id="00756-163">De cmdlets die u in dit onderwerp gebruikt, zijn Windows PowerShell-cmdlets.</span><span class="sxs-lookup"><span data-stu-id="00756-163">The cmdlets that you used in this topic are Windows PowerShell cmdlets.</span></span> <span data-ttu-id="00756-164">Zie de volgende onderwerpen voor meer informatie over deze cmdlets:</span><span class="sxs-lookup"><span data-stu-id="00756-164">For more information about these cmdlets, see the following topics:</span></span>
  
- [<span data-ttu-id="00756-165">Get-Credential</span><span class="sxs-lookup"><span data-stu-id="00756-165">Get-Credential</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=389618)
    
- [<span data-ttu-id="00756-166">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="00756-166">New-PSSession</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=389621)
    
- [<span data-ttu-id="00756-167">Import-PSSession</span><span class="sxs-lookup"><span data-stu-id="00756-167">Import-PSSession</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=389619)
    
- [<span data-ttu-id="00756-168">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="00756-168">Remove-PSSession</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=389620)
    
- [<span data-ttu-id="00756-169">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="00756-169">Set-ExecutionPolicy</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=389623)
    

