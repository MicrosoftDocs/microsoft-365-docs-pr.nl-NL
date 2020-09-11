---
title: Meer informatie over basis apparatuur voor de mobiliteit en beveiliging
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: Gebruik Windows PowerShell voor informatie over de basis-en beveiligingsapparaten van uw organisatie.
ms.openlocfilehash: d34263ee215c568834034f2735bb69d9cef9ac6d
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430139"
---
# <a name="get-details-about-basic-mobility-and-security-managed-devices"></a><span data-ttu-id="a8dc8-103">Meer informatie over basis apparatuur voor de mobiliteit en beveiliging</span><span class="sxs-lookup"><span data-stu-id="a8dc8-103">Get details about Basic Mobility and Security managed devices</span></span>

<span data-ttu-id="a8dc8-104">In dit artikel leest u hoe u Windows PowerShell kunt gebruiken voor informatie over de apparaten in uw organisatie die u instelt voor eenvoudige mobiliteit en beveiliging.</span><span class="sxs-lookup"><span data-stu-id="a8dc8-104">This article shows you how to use Windows PowerShell to get details about the devices in your organization that you set up for Basic Mobility and Security.</span></span>

<span data-ttu-id="a8dc8-105">Dit is een uitsplitsing van de details van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="a8dc8-105">Here's a breakdown for the device details available to you.</span></span>

|<span data-ttu-id="a8dc8-106">**Details**</span><span class="sxs-lookup"><span data-stu-id="a8dc8-106">**Detail**</span></span>|<span data-ttu-id="a8dc8-107">**Waarnaar moet worden gezocht in PowerShell**</span><span class="sxs-lookup"><span data-stu-id="a8dc8-107">**What to look for in PowerShell**</span></span>|
|:----------------|:------------------------------------------------------------------------------|
|<span data-ttu-id="a8dc8-108">Apparaat is ingeschreven voor eenvoudige mobiliteit en beveiliging.</span><span class="sxs-lookup"><span data-stu-id="a8dc8-108">Device is enrolled in Basic Mobility and Security.</span></span> <span data-ttu-id="a8dc8-109">Zie voor meer informatie [uw mobiele apparaat registreren met behulp van eenvoudige mobiliteit en beveiliging](enroll-your-mobile-device.md)</span><span class="sxs-lookup"><span data-stu-id="a8dc8-109">For more info, see [Enroll your mobile device using Basic Mobility and Security](enroll-your-mobile-device.md)</span></span>|<span data-ttu-id="a8dc8-110">De waarde van de *isManaged*   parameter isManaged is:</span><span class="sxs-lookup"><span data-stu-id="a8dc8-110">The value of the *isManaged* parameter is:</span></span><br/><span data-ttu-id="a8dc8-111">**Waar**= apparaat is ingeschreven.</span><span class="sxs-lookup"><span data-stu-id="a8dc8-111">**True**= device is enrolled.</span></span><br/><span data-ttu-id="a8dc8-112">**Onwaar**= apparaat is niet geregistreerd.</span><span class="sxs-lookup"><span data-stu-id="a8dc8-112">**False**= device is not enrolled.</span></span> |
|<span data-ttu-id="a8dc8-113">Apparaat is compatibel met uw beveiligingsbeleid voor apparaten.</span><span class="sxs-lookup"><span data-stu-id="a8dc8-113">Device is compliant with your device security policies.</span></span> <span data-ttu-id="a8dc8-114">Zie [beveiligingsbeleid voor apparaten maken](create-device-security-policies.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="a8dc8-114">For more info, see [Create device security policies](create-device-security-policies.md)</span></span>|<span data-ttu-id="a8dc8-115">De waarde van de *isCompliant*   parameter isCompliant is:</span><span class="sxs-lookup"><span data-stu-id="a8dc8-115">The value of the *isCompliant* parameter is:</span></span><br/><span data-ttu-id="a8dc8-116">**Waar**   = apparaat is compatibel met beleidsregels.</span><span class="sxs-lookup"><span data-stu-id="a8dc8-116">**True** = device is compliant with policies.</span></span><br/><span data-ttu-id="a8dc8-117">**Onwaar**   = apparaat is niet compatibel met beleidsregels.</span><span class="sxs-lookup"><span data-stu-id="a8dc8-117">**False** = device is not compliant with policies.</span></span>|

:::image type="content" source="../../media/basic-mobility-security/bms-7-powershell-parameters.png" alt-text="Basisparameters voor mobiliteit en beveiliging PowerShell":::

>[!NOTE]
><span data-ttu-id="a8dc8-119">De opdrachten en scripts in dit artikel geven ook details weer over de apparaten die door [Microsoft intune](https://www.microsoft.com/cloud-platform/microsoft-intune)worden beheerd.</span><span class="sxs-lookup"><span data-stu-id="a8dc8-119">The commands and scripts in this article also return details about any devices managed by [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="a8dc8-120">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="a8dc8-120">Before you begin</span></span>

<span data-ttu-id="a8dc8-121">Er zijn een paar dingen die u moet instellen om de opdrachten en scripts uit te voeren die in dit artikel worden beschreven.</span><span class="sxs-lookup"><span data-stu-id="a8dc8-121">There are a few things you need to set up to run the commands and scripts described in this article.</span></span>

### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="a8dc8-122">Stap 1: de Azure Active Directory-module voor Windows PowerShell downloaden en installeren</span><span class="sxs-lookup"><span data-stu-id="a8dc8-122">Step 1: Download and install the Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="a8dc8-123">Zie [verbinding maken met Microsoft 365 met PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell)voor meer informatie over deze stappen.</span><span class="sxs-lookup"><span data-stu-id="a8dc8-123">For more info on these steps, see [Connect to Microsoft 365 with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell).</span></span>

1. <span data-ttu-id="a8dc8-124">Ga naar de [Microsoft Online Services-aanmeldhulp voor IT-professionals RTWl](https://www.microsoft.com/download/details.aspx?id=41950)   en selecteer  **downloaden voor Microsoft Online Services-aanmeldhulp**.</span><span class="sxs-lookup"><span data-stu-id="a8dc8-124">Go to [Microsoft Online Services Sign-In Assistant for IT Professionals RTWl](https://www.microsoft.com/download/details.aspx?id=41950) and select  **Download for Microsoft Online Services Sign-in Assistant**.</span></span>   

2. <span data-ttu-id="a8dc8-125">Installeer de module Microsoft Azure Active Directory voor Windows PowerShell met deze stappen:</span><span class="sxs-lookup"><span data-stu-id="a8dc8-125">Install the Microsoft Azure Active Directory Module for Windows PowerShell with these steps:</span></span>   

    1. <span data-ttu-id="a8dc8-126">Open een opdrachtprompt voor de PowerShell-beheerniveau.</span><span class="sxs-lookup"><span data-stu-id="a8dc8-126">Open an administrator-level PowerShell command prompt.</span></span>  

    2. <span data-ttu-id="a8dc8-127">Voer de installatie-module MSOnline uit.</span><span class="sxs-lookup"><span data-stu-id="a8dc8-127">Run the Install-Module MSOnline command.</span></span>
    
    3. <span data-ttu-id="a8dc8-128">Als u wordt gevraagd om de NuGet provider te installeren, typt u Y en drukt u op ENTER.</span><span class="sxs-lookup"><span data-stu-id="a8dc8-128">If prompted to install the NuGet provider, type Y and press ENTER.</span></span>   

    4. <span data-ttu-id="a8dc8-129">Als u wordt gevraagd om de module van PSGallery te installeren, typt u Y en drukt u op ENTER.</span><span class="sxs-lookup"><span data-stu-id="a8dc8-129">If prompted to install the module from PSGallery, type Y and press ENTER.</span></span>   

    5. <span data-ttu-id="a8dc8-130">Na de installatie sluit u het PowerShell-opdrachtvenster.</span><span class="sxs-lookup"><span data-stu-id="a8dc8-130">After installation, close the PowerShell command window.</span></span>
    
### <a name="step-2-connect-to-your-microsoft-365-subscription"></a><span data-ttu-id="a8dc8-131">Stap 2: verbinding maken met uw Microsoft 365-abonnement</span><span class="sxs-lookup"><span data-stu-id="a8dc8-131">Step 2: Connect to your Microsoft 365 subscription</span></span>

1. <span data-ttu-id="a8dc8-132">Voer de volgende opdracht uit in de Windows Azure Active Directory-module voor Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a8dc8-132">In the Windows Azure Active Directory Module for Windows PowerShell, run the following command.</span></span>  

    <span data-ttu-id="a8dc8-133">$UserCredential = Get-Credential</span><span class="sxs-lookup"><span data-stu-id="a8dc8-133">$UserCredential = Get-Credential</span></span>

2. <span data-ttu-id="a8dc8-134">Typ in het dialoogvenster referentie aanvraag voor Windows PowerShell de gebruikersnaam en het wachtwoord voor uw globale beheerdersaccount van Microsoft 365 en selecteer **OK**.</span><span class="sxs-lookup"><span data-stu-id="a8dc8-134">In the Windows PowerShell Credential Request dialog box, type the user name and password for your Microsoft 365 global admin account, and then select **OK**.</span></span>
    
3. <span data-ttu-id="a8dc8-135">Voer de volgende opdracht uit.</span><span class="sxs-lookup"><span data-stu-id="a8dc8-135">Run the following command.</span></span>
    
    <span data-ttu-id="a8dc8-136">Connect-MsolService-Credential $UserCredential</span><span class="sxs-lookup"><span data-stu-id="a8dc8-136">Connect-MsolService -Credential $UserCredential</span></span>

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a><span data-ttu-id="a8dc8-137">Stap 3: controleren of u PowerShell-scripts kunt uitvoeren</span><span class="sxs-lookup"><span data-stu-id="a8dc8-137">Step 3: Make sure you’re able to run PowerShell scripts</span></span>

>[!NOTE]
><span data-ttu-id="a8dc8-138">U kunt deze stap overslaan als u al bent geconfigureerd voor het uitvoeren van PowerShell-scripts.</span><span class="sxs-lookup"><span data-stu-id="a8dc8-138">You can skip this step if you’re already set up to run PowerShell scripts.</span></span>

<span data-ttu-id="a8dc8-139">Als u het Get-MsolUserDeviceComplianceStatus.ps1 script wilt uitvoeren, moet u de uitvoering van PowerShell-scripts inschakelen.</span><span class="sxs-lookup"><span data-stu-id="a8dc8-139">To run the Get-MsolUserDeviceComplianceStatus.ps1 script, you need to enable the running of PowerShell scripts.</span></span>

1. <span data-ttu-id="a8dc8-140">Selecteer op het Windows-bureaublad de optie **Start**en typ Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a8dc8-140">From your Windows Desktop, select **Start**, and then type Windows PowerShell.</span></span> <span data-ttu-id="a8dc8-141">Klik met de rechtermuisknop op Windows PowerShell en selecteer **als administrator uitvoeren**.</span><span class="sxs-lookup"><span data-stu-id="a8dc8-141">Right-click Windows PowerShell, and then select **Run as administrator**.</span></span>

2. <span data-ttu-id="a8dc8-142">Voer de volgende opdracht uit.</span><span class="sxs-lookup"><span data-stu-id="a8dc8-142">Run the following command.</span></span>
    
    <span data-ttu-id="a8dc8-143">Set-ExecutionPolicy RemoteSigned</span><span class="sxs-lookup"><span data-stu-id="a8dc8-143">Set-ExecutionPolicy  RemoteSigned</span></span>

3. <span data-ttu-id="a8dc8-144">Wanneer u hierom wordt gevraagd, typt u Y en drukt u op ENTER.</span><span class="sxs-lookup"><span data-stu-id="a8dc8-144">When prompted, type Y and then press Enter.</span></span>
    
<span data-ttu-id="a8dc8-145">**De cmdlet Get-MsolDevice uitvoeren om de details weer te geven van alle apparaten in uw organisatie**</span><span class="sxs-lookup"><span data-stu-id="a8dc8-145">**Run the Get-MsolDevice cmdlet to display details for all devices in your organization**</span></span>

1. <span data-ttu-id="a8dc8-146">Open de Microsoft Azure Active Directory-module voor Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a8dc8-146">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>  

2. <span data-ttu-id="a8dc8-147">Voer de volgende opdracht uit.</span><span class="sxs-lookup"><span data-stu-id="a8dc8-147">Run the following command.</span></span>
    
    <span data-ttu-id="a8dc8-148">Get-MsolDevice-all-ReturnRegisteredOwners | Where-object {$ _. RegisteredOwners. Count-gt 0}</span><span class="sxs-lookup"><span data-stu-id="a8dc8-148">Get-MsolDevice -All -ReturnRegisteredOwners | Where-Object {$_.RegisteredOwners.Count -gt 0}</span></span>

<span data-ttu-id="a8dc8-149">Zie  [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=841721)voor meer voorbeelden.</span><span class="sxs-lookup"><span data-stu-id="a8dc8-149">For more examples, see  [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=841721).</span></span>

## <a name="run-a-script-to-get-device-details"></a><span data-ttu-id="a8dc8-150">Een script uitvoeren om details van apparaat te achterhalen</span><span class="sxs-lookup"><span data-stu-id="a8dc8-150">Run a script to get device details</span></span>

<span data-ttu-id="a8dc8-151">Sla eerst het script op uw computer op.</span><span class="sxs-lookup"><span data-stu-id="a8dc8-151">First, save the script to your computer.</span></span>

1. <span data-ttu-id="a8dc8-152">Kopieer en plak de volgende tekst in Kladblok.</span><span class="sxs-lookup"><span data-stu-id="a8dc8-152">Copy and paste the following text into Notepad.</span></span>  

2.  <span data-ttu-id="a8dc8-153">wil zeggen param</span><span class="sxs-lookup"><span data-stu-id="a8dc8-153">param (</span></span>
    

3.  <span data-ttu-id="a8dc8-154">[PSObject []] $users = @ (),</span><span class="sxs-lookup"><span data-stu-id="a8dc8-154">[PSObject[]]$users = @(),</span></span>
    

4.  <span data-ttu-id="a8dc8-155">[Schakeloptie] $export</span><span class="sxs-lookup"><span data-stu-id="a8dc8-155">[Switch]$export,</span></span>
    

5.  <span data-ttu-id="a8dc8-156">[Tekenreeks] $exportFileName = "UserDeviceComplianceStatus_" + (Get-date-indeling "yyMMdd_HHMMss") + ". csv",</span><span class="sxs-lookup"><span data-stu-id="a8dc8-156">[String]$exportFileName = "UserDeviceComplianceStatus_" + (Get-Date -Format "yyMMdd_HHMMss") + ".csv",</span></span>
    

6.  <span data-ttu-id="a8dc8-157">[Tekenreeks] $exportPath = [Environment]:: GetFolderPath ("bureaublad")</span><span class="sxs-lookup"><span data-stu-id="a8dc8-157">[String]$exportPath = [Environment]::GetFolderPath("Desktop")</span></span>
    

7.  <span data-ttu-id="a8dc8-158">)</span><span class="sxs-lookup"><span data-stu-id="a8dc8-158">)</span></span>
    

9.  <span data-ttu-id="a8dc8-159">[System. Collection. IDictionary] $script: schema = @ {</span><span class="sxs-lookup"><span data-stu-id="a8dc8-159">[System.Collections.IDictionary]$script:schema = @{</span></span>
    

11.  <span data-ttu-id="a8dc8-160">DeviceId = ' '</span><span class="sxs-lookup"><span data-stu-id="a8dc8-160">DeviceId = ''</span></span>
    

12.  <span data-ttu-id="a8dc8-161">DeviceOSType = ' '</span><span class="sxs-lookup"><span data-stu-id="a8dc8-161">DeviceOSType = ''</span></span>
    

13.  <span data-ttu-id="a8dc8-162">DeviceOSVersion = ' '</span><span class="sxs-lookup"><span data-stu-id="a8dc8-162">DeviceOSVersion = ''</span></span>
    

14.  <span data-ttu-id="a8dc8-163">DeviceTrustLevel = ' '</span><span class="sxs-lookup"><span data-stu-id="a8dc8-163">DeviceTrustLevel = ''</span></span>
    

15.  <span data-ttu-id="a8dc8-164">DisplayName = ' '</span><span class="sxs-lookup"><span data-stu-id="a8dc8-164">DisplayName = ''</span></span>
    

16.  <span data-ttu-id="a8dc8-165">IsCompliant = ' '</span><span class="sxs-lookup"><span data-stu-id="a8dc8-165">IsCompliant = ''</span></span>
    

17.  <span data-ttu-id="a8dc8-166">IsManaged = ' '</span><span class="sxs-lookup"><span data-stu-id="a8dc8-166">IsManaged = ''</span></span>
    

18.  <span data-ttu-id="a8dc8-167">ApproximateLastLogonTimestamp = ' '</span><span class="sxs-lookup"><span data-stu-id="a8dc8-167">ApproximateLastLogonTimestamp = ''</span></span>
    

19.  <span data-ttu-id="a8dc8-168">DeviceObjectId = ' '</span><span class="sxs-lookup"><span data-stu-id="a8dc8-168">DeviceObjectId = ''</span></span>
    

20.  <span data-ttu-id="a8dc8-169">RegisteredOwnerUpn = ' '</span><span class="sxs-lookup"><span data-stu-id="a8dc8-169">RegisteredOwnerUpn = ''</span></span>
    

21.  <span data-ttu-id="a8dc8-170">RegisteredOwnerObjectId = ' '</span><span class="sxs-lookup"><span data-stu-id="a8dc8-170">RegisteredOwnerObjectId = ''</span></span>
    

22.  <span data-ttu-id="a8dc8-171">RegisteredOwnerDisplayName = ' '</span><span class="sxs-lookup"><span data-stu-id="a8dc8-171">RegisteredOwnerDisplayName = ''</span></span>
    

23.  <span data-ttu-id="a8dc8-172">}</span><span class="sxs-lookup"><span data-stu-id="a8dc8-172">}</span></span>
    

25.  <span data-ttu-id="a8dc8-173">createResultObject, functie</span><span class="sxs-lookup"><span data-stu-id="a8dc8-173">function createResultObject</span></span>
    

26.  <span data-ttu-id="a8dc8-174">{</span><span class="sxs-lookup"><span data-stu-id="a8dc8-174">{</span></span>
    

28.  <span data-ttu-id="a8dc8-175">[PSObject] $resultObject = New-object-TypeName PSObject-eigenschap $script: schema</span><span class="sxs-lookup"><span data-stu-id="a8dc8-175">[PSObject]$resultObject = New-Object -TypeName PSObject -Property $script:schema</span></span>
    

30.  <span data-ttu-id="a8dc8-176">retour $resultObject</span><span class="sxs-lookup"><span data-stu-id="a8dc8-176">return $resultObject</span></span>
    

31.  <span data-ttu-id="a8dc8-177">}</span><span class="sxs-lookup"><span data-stu-id="a8dc8-177">}</span></span>
    

33.  <span data-ttu-id="a8dc8-178">Als ($users. Aantal-EQ 0)</span><span class="sxs-lookup"><span data-stu-id="a8dc8-178">If ($users.Count -eq 0)</span></span>
    

34.  <span data-ttu-id="a8dc8-179">{</span><span class="sxs-lookup"><span data-stu-id="a8dc8-179">{</span></span>
    

35.  <span data-ttu-id="a8dc8-180">$users = get-MsolUser</span><span class="sxs-lookup"><span data-stu-id="a8dc8-180">$users = Get-MsolUser</span></span>
    

36.  <span data-ttu-id="a8dc8-181">}</span><span class="sxs-lookup"><span data-stu-id="a8dc8-181">}</span></span>
    

38.  <span data-ttu-id="a8dc8-182">[PSObject []] $result = foreach ($u in $users)</span><span class="sxs-lookup"><span data-stu-id="a8dc8-182">[PSObject[]]$result = foreach ($u in $users)</span></span>
    

39.  <span data-ttu-id="a8dc8-183">{</span><span class="sxs-lookup"><span data-stu-id="a8dc8-183">{</span></span>
    

41.  <span data-ttu-id="a8dc8-184">[PSObject] $devices = Get-msoldevice-RegisteredOwnerUpn $u. UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="a8dc8-184">[PSObject]$devices = get-msoldevice -RegisteredOwnerUpn $u.UserPrincipalName</span></span>
    

42.  <span data-ttu-id="a8dc8-185">foreach ($d in $devices)</span><span class="sxs-lookup"><span data-stu-id="a8dc8-185">foreach ($d in $devices)</span></span>
    

43.  <span data-ttu-id="a8dc8-186">{</span><span class="sxs-lookup"><span data-stu-id="a8dc8-186">{</span></span>
    

44.  <span data-ttu-id="a8dc8-187">[PSObject] $deviceResult = createResultObject</span><span class="sxs-lookup"><span data-stu-id="a8dc8-187">[PSObject]$deviceResult = createResultObject</span></span>
    

45.  <span data-ttu-id="a8dc8-188">$deviceResult. DeviceId = $d. DeviceId</span><span class="sxs-lookup"><span data-stu-id="a8dc8-188">$deviceResult.DeviceId = $d.DeviceId</span></span>
    

46.  <span data-ttu-id="a8dc8-189">$deviceResult. DeviceOSType = $d. DeviceOSType</span><span class="sxs-lookup"><span data-stu-id="a8dc8-189">$deviceResult.DeviceOSType = $d.DeviceOSType</span></span>
    

47.  <span data-ttu-id="a8dc8-190">$deviceResult. DeviceOSVersion = $d. DeviceOSVersion</span><span class="sxs-lookup"><span data-stu-id="a8dc8-190">$deviceResult.DeviceOSVersion = $d.DeviceOSVersion</span></span>
    

48.  <span data-ttu-id="a8dc8-191">$deviceResult. DeviceTrustLevel = $d. DeviceTrustLevel</span><span class="sxs-lookup"><span data-stu-id="a8dc8-191">$deviceResult.DeviceTrustLevel = $d.DeviceTrustLevel</span></span>
    

49.  <span data-ttu-id="a8dc8-192">$deviceResult. naam = $d. DisplayName</span><span class="sxs-lookup"><span data-stu-id="a8dc8-192">$deviceResult.DisplayName = $d.DisplayName</span></span>
    

50.  <span data-ttu-id="a8dc8-193">$deviceResult. IsCompliant = $d. GraphDeviceObject. IsCompliant</span><span class="sxs-lookup"><span data-stu-id="a8dc8-193">$deviceResult.IsCompliant = $d.GraphDeviceObject.IsCompliant</span></span>
    

51.  <span data-ttu-id="a8dc8-194">$deviceResult. IsManaged = $d. GraphDeviceObject. IsManaged</span><span class="sxs-lookup"><span data-stu-id="a8dc8-194">$deviceResult.IsManaged = $d.GraphDeviceObject.IsManaged</span></span>
    

52.  <span data-ttu-id="a8dc8-195">$deviceResult. DeviceObjectId = $d. ObjectId</span><span class="sxs-lookup"><span data-stu-id="a8dc8-195">$deviceResult.DeviceObjectId = $d.ObjectId</span></span>
    

53.  <span data-ttu-id="a8dc8-196">$deviceResult. RegisteredOwnerUpn = $u. UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="a8dc8-196">$deviceResult.RegisteredOwnerUpn = $u.UserPrincipalName</span></span>
    

54.  <span data-ttu-id="a8dc8-197">$deviceResult. RegisteredOwnerObjectId = $u. ObjectId</span><span class="sxs-lookup"><span data-stu-id="a8dc8-197">$deviceResult.RegisteredOwnerObjectId = $u.ObjectId</span></span>
    

55.  <span data-ttu-id="a8dc8-198">$deviceResult. RegisteredOwnerDisplayName = $u. DisplayName</span><span class="sxs-lookup"><span data-stu-id="a8dc8-198">$deviceResult.RegisteredOwnerDisplayName = $u.DisplayName</span></span>
    

56.  <span data-ttu-id="a8dc8-199">$deviceResult. ApproximateLastLogonTimestamp = $d. ApproximateLastLogonTimestamp</span><span class="sxs-lookup"><span data-stu-id="a8dc8-199">$deviceResult.ApproximateLastLogonTimestamp = $d.ApproximateLastLogonTimestamp</span></span>
    

58.  <span data-ttu-id="a8dc8-200">$deviceResult</span><span class="sxs-lookup"><span data-stu-id="a8dc8-200">$deviceResult</span></span>
    

59.  <span data-ttu-id="a8dc8-201">}</span><span class="sxs-lookup"><span data-stu-id="a8dc8-201">}</span></span>
    

61.  <span data-ttu-id="a8dc8-202">}</span><span class="sxs-lookup"><span data-stu-id="a8dc8-202">}</span></span>
    

63.  <span data-ttu-id="a8dc8-203">Als ($export)</span><span class="sxs-lookup"><span data-stu-id="a8dc8-203">If ($export)</span></span>
    

64.  <span data-ttu-id="a8dc8-204">{</span><span class="sxs-lookup"><span data-stu-id="a8dc8-204">{</span></span>
    

65.  <span data-ttu-id="a8dc8-205">$result | Export-csv-pad ($exportPath + " \" + $exportFileName)-NoTypeInformation</span><span class="sxs-lookup"><span data-stu-id="a8dc8-205">$result | Export-Csv -path ($exportPath + "\" + $exportFileName) -NoTypeInformation</span></span>
    

66.  <span data-ttu-id="a8dc8-206">}</span><span class="sxs-lookup"><span data-stu-id="a8dc8-206">}</span></span>
    

67.  <span data-ttu-id="a8dc8-207">Zaken</span><span class="sxs-lookup"><span data-stu-id="a8dc8-207">Else</span></span>
    

68.  <span data-ttu-id="a8dc8-208">{</span><span class="sxs-lookup"><span data-stu-id="a8dc8-208">{</span></span>
    

69.  <span data-ttu-id="a8dc8-209">$result</span><span class="sxs-lookup"><span data-stu-id="a8dc8-209">$result</span></span>
    

70.  <span data-ttu-id="a8dc8-210">}</span><span class="sxs-lookup"><span data-stu-id="a8dc8-210">}</span></span>
    

71.  <span data-ttu-id="a8dc8-211">Sla het bestand op als een Windows PowerShell-scriptbestand met de bestandsextensie. ps1. Get-MsolUserDeviceComplianceStatus.ps1 bijvoorbeeld.</span><span class="sxs-lookup"><span data-stu-id="a8dc8-211">Save it as a Windows PowerShell script file by using the file extension .ps1; for example, Get-MsolUserDeviceComplianceStatus.ps1.</span></span>   

## <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a><span data-ttu-id="a8dc8-212">Voer het script uit om apparaatgegevens voor één gebruikersaccount op te halen</span><span class="sxs-lookup"><span data-stu-id="a8dc8-212">Run the script to get device information for a single user account</span></span>

1. <span data-ttu-id="a8dc8-213">Open de Microsoft Azure Active Directory-module voor Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a8dc8-213">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>
    
2. <span data-ttu-id="a8dc8-214">Ga naar de map waarin u het script hebt opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="a8dc8-214">Go to the folder where you saved the script.</span></span> <span data-ttu-id="a8dc8-215">Voer de volgende opdracht uit als u het bestand hebt opgeslagen op C:\PS-Scripts.</span><span class="sxs-lookup"><span data-stu-id="a8dc8-215">For example, if you saved it to C:\PS-Scripts, run the following command.</span></span>
    
    <span data-ttu-id="a8dc8-216">CD-C:\PS-Scripts</span><span class="sxs-lookup"><span data-stu-id="a8dc8-216">cd C:\PS-Scripts</span></span>

3. <span data-ttu-id="a8dc8-217">Voer de volgende opdracht uit om de gebruiker te identificeren voor wie u informatie over apparaten wilt hebben.</span><span class="sxs-lookup"><span data-stu-id="a8dc8-217">Run the following command to identify the user you want to get device details for.</span></span> <span data-ttu-id="a8dc8-218">In dit voorbeeld worden gegevens opgehaald voor bar@example.com.</span><span class="sxs-lookup"><span data-stu-id="a8dc8-218">This example gets details for bar@example.com.</span></span>
    
    <span data-ttu-id="a8dc8-219">$u = Get-MsolUser-UserPrincipalName bar@example.com</span><span class="sxs-lookup"><span data-stu-id="a8dc8-219">$u = Get-MsolUser -UserPrincipalName bar@example.com</span></span>

4. <span data-ttu-id="a8dc8-220">Voer de volgende opdracht uit om het script te starten.</span><span class="sxs-lookup"><span data-stu-id="a8dc8-220">Run the following command to initiate the script.</span></span>

    <span data-ttu-id="a8dc8-221">.\Get-MsolUserDeviceComplianceStatus.ps1-gebruikers $u-exporteren</span><span class="sxs-lookup"><span data-stu-id="a8dc8-221">.\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export</span></span>

<span data-ttu-id="a8dc8-222">De gegevens worden geëxporteerd naar het Windows-bureaublad als een CSV-bestand.</span><span class="sxs-lookup"><span data-stu-id="a8dc8-222">The information is exported to your Windows Desktop as a CSV file.</span></span> <span data-ttu-id="a8dc8-223">U kunt aanvullende parameters gebruiken om de bestandsnaam en het pad van het CSV-bestand op te geven.</span><span class="sxs-lookup"><span data-stu-id="a8dc8-223">You can use additional parameters to specify the file name and path of the CSV.</span></span>

## <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a><span data-ttu-id="a8dc8-224">Voer het script uit om informatie over apparaten te krijgen voor een groep gebruikers</span><span class="sxs-lookup"><span data-stu-id="a8dc8-224">Run the script to get device information for a group of users</span></span>

1. <span data-ttu-id="a8dc8-225">Open de Microsoft Azure Active Directory-module voor Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a8dc8-225">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>
    
2. <span data-ttu-id="a8dc8-226">Ga naar de map waarin u het script hebt opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="a8dc8-226">Go to the folder where you saved the script.</span></span> <span data-ttu-id="a8dc8-227">Voer de volgende opdracht uit als u het bestand hebt opgeslagen op C:\PS-Scripts.</span><span class="sxs-lookup"><span data-stu-id="a8dc8-227">For example, if you saved it to C:\PS-Scripts, run the following command.</span></span>   

    <span data-ttu-id="a8dc8-228">CD-C:\PS-Scripts</span><span class="sxs-lookup"><span data-stu-id="a8dc8-228">cd C:\PS-Scripts</span></span>

3. <span data-ttu-id="a8dc8-229">Voer de volgende opdracht uit om te achterhalen met welke groep u apparaatgegevens moet achterhalen.</span><span class="sxs-lookup"><span data-stu-id="a8dc8-229">Run the following command to identify the group you want to get device details for.</span></span> <span data-ttu-id="a8dc8-230">In dit voorbeeld worden de details van gebruikers in de FinanceStaff-groep opgehaald.</span><span class="sxs-lookup"><span data-stu-id="a8dc8-230">This example gets details for users in the FinanceStaff group.</span></span> 

    <span data-ttu-id="a8dc8-231">$u = Get-MsolGroupMember-SearchString "FinanceStaff" | % {Get-MsolUser-ObjectId $ _. ObjectId</span><span class="sxs-lookup"><span data-stu-id="a8dc8-231">$u = Get-MsolGroupMember -SearchString "FinanceStaff" | % { Get-MsolUser -ObjectId $_.ObjectId }</span></span>

4. <span data-ttu-id="a8dc8-232">Voer de volgende opdracht uit om het script te starten.</span><span class="sxs-lookup"><span data-stu-id="a8dc8-232">Run the following command to initiate the script.</span></span>   

    <span data-ttu-id="a8dc8-233">.\Get-MsolUserDeviceComplianceStatus.ps1-gebruikers $u-exporteren</span><span class="sxs-lookup"><span data-stu-id="a8dc8-233">.\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export</span></span>

<span data-ttu-id="a8dc8-234">De gegevens worden geëxporteerd naar het Windows-bureaublad als een CSV-bestand.</span><span class="sxs-lookup"><span data-stu-id="a8dc8-234">The information is exported to your Windows Desktop as a CSV file.</span></span> <span data-ttu-id="a8dc8-235">U kunt aanvullende parameters gebruiken om de bestandsnaam en het pad van het CSV-bestand op te geven.</span><span class="sxs-lookup"><span data-stu-id="a8dc8-235">You can use additional parameters to specify the file name and path of the CSV.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a8dc8-236">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="a8dc8-236">Related topics</span></span>

[<span data-ttu-id="a8dc8-237">Microsoft Connect is buiten gebruik gesteld</span><span class="sxs-lookup"><span data-stu-id="a8dc8-237">Microsoft Connect Has Been Retired</span></span>](https://docs.microsoft.com/collaborate/connect-redirect)

[<span data-ttu-id="a8dc8-238">Overzicht van eenvoudige mobiliteit en beveiliging</span><span class="sxs-lookup"><span data-stu-id="a8dc8-238">Overview of Basic Mobility and Security</span></span>](overview.md)

[<span data-ttu-id="a8dc8-239">Get-MsolDevice</span><span class="sxs-lookup"><span data-stu-id="a8dc8-239">Get-MsolDevice</span></span>](https://go.microsoft.com/fwlink/?linkid=841721)