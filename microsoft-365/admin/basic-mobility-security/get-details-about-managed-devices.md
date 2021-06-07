---
title: Meer informatie over beheerde basisapparaten voor mobiliteit en beveiliging
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
description: Gebruik Windows PowerShell voor meer informatie over basismobiliteits- en beveiligingsapparaten in uw organisatie.
ms.openlocfilehash: 7cb2369c9a31210f26db12b0453e7a4228e1cccc
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782439"
---
# <a name="get-details-about-basic-mobility-and-security-managed-devices"></a><span data-ttu-id="aff9b-103">Meer informatie over beheerde basisapparaten voor mobiliteit en beveiliging</span><span class="sxs-lookup"><span data-stu-id="aff9b-103">Get details about Basic Mobility and Security managed devices</span></span>

<span data-ttu-id="aff9b-104">In dit artikel wordt beschreven hoe u Windows PowerShell voor meer informatie over de apparaten in uw organisatie die u hebt ingesteld voor Basismobiliteit en Beveiliging.</span><span class="sxs-lookup"><span data-stu-id="aff9b-104">This article shows you how to use Windows PowerShell to get details about the devices in your organization that you set up for Basic Mobility and Security.</span></span>

<span data-ttu-id="aff9b-105">Hier ziet u een overzicht van de apparaatdetails die voor u beschikbaar zijn.</span><span class="sxs-lookup"><span data-stu-id="aff9b-105">Here's a breakdown for the device details available to you.</span></span>

|<span data-ttu-id="aff9b-106">**Details**</span><span class="sxs-lookup"><span data-stu-id="aff9b-106">**Detail**</span></span>|<span data-ttu-id="aff9b-107">**Waar moet u naar zoeken in PowerShell**</span><span class="sxs-lookup"><span data-stu-id="aff9b-107">**What to look for in PowerShell**</span></span>|
|:----------------|:------------------------------------------------------------------------------|
|<span data-ttu-id="aff9b-108">Apparaat is geregistreerd voor Basismobiliteit en Beveiliging.</span><span class="sxs-lookup"><span data-stu-id="aff9b-108">Device is enrolled in Basic Mobility and Security.</span></span> <span data-ttu-id="aff9b-109">Zie Uw mobiele apparaat registreren met [basismobiliteit en beveiliging voor meer informatie.](enroll-your-mobile-device.md)</span><span class="sxs-lookup"><span data-stu-id="aff9b-109">For more info, see [Enroll your mobile device using Basic Mobility and Security](enroll-your-mobile-device.md)</span></span>|<span data-ttu-id="aff9b-110">De waarde van de *parameter isManaged*   is:</span><span class="sxs-lookup"><span data-stu-id="aff9b-110">The value of the *isManaged* parameter is:</span></span><br/><span data-ttu-id="aff9b-111">**True**= apparaat is geregistreerd.</span><span class="sxs-lookup"><span data-stu-id="aff9b-111">**True**= device is enrolled.</span></span><br/><span data-ttu-id="aff9b-112">**False**= apparaat is niet geregistreerd.</span><span class="sxs-lookup"><span data-stu-id="aff9b-112">**False**= device is not enrolled.</span></span> |
|<span data-ttu-id="aff9b-113">Apparaat voldoet aan het beveiligingsbeleid van uw apparaat.</span><span class="sxs-lookup"><span data-stu-id="aff9b-113">Device is compliant with your device security policies.</span></span> <span data-ttu-id="aff9b-114">Zie Apparaatbeveiligingsbeleid [maken voor meer informatie](create-device-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="aff9b-114">For more info, see [Create device security policies](create-device-security-policies.md)</span></span>|<span data-ttu-id="aff9b-115">De waarde van de *parameter IsCompliant*   is:</span><span class="sxs-lookup"><span data-stu-id="aff9b-115">The value of the *isCompliant* parameter is:</span></span><br/><span data-ttu-id="aff9b-116">**Waar**   = apparaat voldoet aan beleidsregels.</span><span class="sxs-lookup"><span data-stu-id="aff9b-116">**True** = device is compliant with policies.</span></span><br/><span data-ttu-id="aff9b-117">**Onwaar**   = apparaat voldoet niet aan beleidsregels.</span><span class="sxs-lookup"><span data-stu-id="aff9b-117">**False** = device is not compliant with policies.</span></span>|

:::image type="content" source="../../media/basic-mobility-security/bms-7-powershell-parameters.png" alt-text="PowerShell-parameters voor basismobiliteit en beveiliging":::

>[!NOTE]
><span data-ttu-id="aff9b-119">De opdrachten en scripts in dit artikel geven ook informatie weer over apparaten die worden beheerd door [Microsoft Intune.](https://www.microsoft.com/cloud-platform/microsoft-intune)</span><span class="sxs-lookup"><span data-stu-id="aff9b-119">The commands and scripts in this article also return details about any devices managed by [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="aff9b-120">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="aff9b-120">Before you begin</span></span>

<span data-ttu-id="aff9b-121">Er zijn een paar dingen die u moet instellen om de opdrachten en scripts uit te voeren die in dit artikel worden beschreven.</span><span class="sxs-lookup"><span data-stu-id="aff9b-121">There are a few things you need to set up to run the commands and scripts described in this article.</span></span>

### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="aff9b-122">Stap 1: Download en installeer de Azure Active Directory module voor Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="aff9b-122">Step 1: Download and install the Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="aff9b-123">Zie voor meer informatie over deze stappen [Verbinding maken te Microsoft 365 powershell.](/office365/enterprise/powershell/connect-to-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="aff9b-123">For more info on these steps, see [Connect to Microsoft 365 with PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell).</span></span>

1. <span data-ttu-id="aff9b-124">Ga naar Microsoft Online Services Sign-In Assistent voor [IT-professionals RTWl](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi)en   selecteer Downloaden voor Microsoft Online Services  **Aanmeldingsassistent**.</span><span class="sxs-lookup"><span data-stu-id="aff9b-124">Go to [Microsoft Online Services Sign-In Assistant for IT Professionals RTWl](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi) and select  **Download for Microsoft Online Services Sign-in Assistant**.</span></span>

2. <span data-ttu-id="aff9b-125">Installeer de module Microsoft Azure Active Directory voor Windows PowerShell met deze stappen:</span><span class="sxs-lookup"><span data-stu-id="aff9b-125">Install the Microsoft Azure Active Directory Module for Windows PowerShell with these steps:</span></span>

    1. <span data-ttu-id="aff9b-126">Open een PowerShell-opdrachtprompt op beheerdersniveau.</span><span class="sxs-lookup"><span data-stu-id="aff9b-126">Open an administrator-level PowerShell command prompt.</span></span>  

    2. <span data-ttu-id="aff9b-127">Voer de installatie-module MSOnline uit.</span><span class="sxs-lookup"><span data-stu-id="aff9b-127">Run the Install-Module MSOnline command.</span></span>

    3. <span data-ttu-id="aff9b-128">Als u wordt gevraagd om de NuGet provider te installeren, typt u Y en drukt u op ENTER.</span><span class="sxs-lookup"><span data-stu-id="aff9b-128">If prompted to install the NuGet provider, type Y and press ENTER.</span></span>

    4. <span data-ttu-id="aff9b-129">Als u wordt gevraagd om de module van PSGallery te installeren, typt u Y en drukt u op ENTER.</span><span class="sxs-lookup"><span data-stu-id="aff9b-129">If prompted to install the module from PSGallery, type Y and press ENTER.</span></span>

    5. <span data-ttu-id="aff9b-130">Sluit na de installatie het powershell-opdrachtvenster.</span><span class="sxs-lookup"><span data-stu-id="aff9b-130">After installation, close the PowerShell command window.</span></span>

### <a name="step-2-connect-to-your-microsoft-365-subscription"></a><span data-ttu-id="aff9b-131">Stap 2: Verbinding maken uw Microsoft 365 abonnement</span><span class="sxs-lookup"><span data-stu-id="aff9b-131">Step 2: Connect to your Microsoft 365 subscription</span></span>

1. <span data-ttu-id="aff9b-132">Voer in Windows Azure Active Directory module voor Windows PowerShell de volgende opdracht uit.</span><span class="sxs-lookup"><span data-stu-id="aff9b-132">In the Windows Azure Active Directory Module for Windows PowerShell, run the following command.</span></span>  

    <span data-ttu-id="aff9b-133">$UserCredential = Get-Credential</span><span class="sxs-lookup"><span data-stu-id="aff9b-133">$UserCredential = Get-Credential</span></span>

2. <span data-ttu-id="aff9b-134">Typ in Windows PowerShell dialoogvenster Aanvraag voor referenties de gebruikersnaam en het wachtwoord voor uw Microsoft 365 globale beheerdersaccount en selecteer **OK.**</span><span class="sxs-lookup"><span data-stu-id="aff9b-134">In the Windows PowerShell Credential Request dialog box, type the user name and password for your Microsoft 365 global admin account, and then select **OK**.</span></span>

3. <span data-ttu-id="aff9b-135">Voer de volgende opdracht uit.</span><span class="sxs-lookup"><span data-stu-id="aff9b-135">Run the following command.</span></span>

    <span data-ttu-id="aff9b-136">Connect-MsolService -Credential $UserCredential</span><span class="sxs-lookup"><span data-stu-id="aff9b-136">Connect-MsolService -Credential $UserCredential</span></span>

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a><span data-ttu-id="aff9b-137">Stap 3: Zorg ervoor dat u PowerShell-scripts kunt uitvoeren</span><span class="sxs-lookup"><span data-stu-id="aff9b-137">Step 3: Make sure you’re able to run PowerShell scripts</span></span>

>[!NOTE]
><span data-ttu-id="aff9b-138">U kunt deze stap overslaan als u al bent ingesteld voor het uitvoeren van PowerShell-scripts.</span><span class="sxs-lookup"><span data-stu-id="aff9b-138">You can skip this step if you’re already set up to run PowerShell scripts.</span></span>

<span data-ttu-id="aff9b-139">Als u het script Get-MsolUserDeviceComplianceStatus.ps1 uitvoeren, moet u het uitvoeren van PowerShell-scripts inschakelen.</span><span class="sxs-lookup"><span data-stu-id="aff9b-139">To run the Get-MsolUserDeviceComplianceStatus.ps1 script, you need to enable the running of PowerShell scripts.</span></span>

1. <span data-ttu-id="aff9b-140">Selecteer op Windows bureaublad **Start** en typ Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="aff9b-140">From your Windows Desktop, select **Start**, and then type Windows PowerShell.</span></span> <span data-ttu-id="aff9b-141">Klik met de rechtermuisknop Windows PowerShell en selecteer vervolgens **Uitvoeren als beheerder.**</span><span class="sxs-lookup"><span data-stu-id="aff9b-141">Right-click Windows PowerShell, and then select **Run as administrator**.</span></span>

2. <span data-ttu-id="aff9b-142">Voer de volgende opdracht uit.</span><span class="sxs-lookup"><span data-stu-id="aff9b-142">Run the following command.</span></span>

    <span data-ttu-id="aff9b-143">Set-ExecutionPolicy RemoteSigned</span><span class="sxs-lookup"><span data-stu-id="aff9b-143">Set-ExecutionPolicy  RemoteSigned</span></span>

3. <span data-ttu-id="aff9b-144">Wanneer u daarom wordt gevraagd, typt u Y en drukt u op Enter.</span><span class="sxs-lookup"><span data-stu-id="aff9b-144">When prompted, type Y and then press Enter.</span></span>

<span data-ttu-id="aff9b-145">**Voer de Get-MsolDevice cmdlet uit om details weer te geven voor alle apparaten in uw organisatie**</span><span class="sxs-lookup"><span data-stu-id="aff9b-145">**Run the Get-MsolDevice cmdlet to display details for all devices in your organization**</span></span>

1. <span data-ttu-id="aff9b-146">Open de Microsoft Azure Active Directory module voor Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="aff9b-146">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>  

2. <span data-ttu-id="aff9b-147">Voer de volgende opdracht uit.</span><span class="sxs-lookup"><span data-stu-id="aff9b-147">Run the following command.</span></span>

    <span data-ttu-id="aff9b-148">Get-MsolDevice -All -ReturnRegisteredOwners | Where-Object {$_. RegisteredOwners.Count -gt 0}</span><span class="sxs-lookup"><span data-stu-id="aff9b-148">Get-MsolDevice -All -ReturnRegisteredOwners | Where-Object {$_.RegisteredOwners.Count -gt 0}</span></span>

<span data-ttu-id="aff9b-149">Zie  [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=2157939)voor meer voorbeelden.</span><span class="sxs-lookup"><span data-stu-id="aff9b-149">For more examples, see  [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=2157939).</span></span>

## <a name="run-a-script-to-get-device-details"></a><span data-ttu-id="aff9b-150">Een script uitvoeren om apparaatdetails op te halen</span><span class="sxs-lookup"><span data-stu-id="aff9b-150">Run a script to get device details</span></span>

<span data-ttu-id="aff9b-151">Sla eerst het script op uw computer op.</span><span class="sxs-lookup"><span data-stu-id="aff9b-151">First, save the script to your computer.</span></span>

1. <span data-ttu-id="aff9b-152">Kopieer en plak de volgende tekst in Kladblok.</span><span class="sxs-lookup"><span data-stu-id="aff9b-152">Copy and paste the following text into Notepad.</span></span>  

2.  <span data-ttu-id="aff9b-153">param (</span><span class="sxs-lookup"><span data-stu-id="aff9b-153">param (</span></span>

3.  <span data-ttu-id="aff9b-154">[PSObject[]]$users = @(),</span><span class="sxs-lookup"><span data-stu-id="aff9b-154">[PSObject[]]$users = @(),</span></span>

4.  <span data-ttu-id="aff9b-155">[Schakel]$export,</span><span class="sxs-lookup"><span data-stu-id="aff9b-155">[Switch]$export,</span></span>

5.  <span data-ttu-id="aff9b-156">[Tekenreeks]$exportFileName = "UserDeviceComplianceStatus_" + (Get-Date -Format "yyMMdd_HHMMss") + ".csv",</span><span class="sxs-lookup"><span data-stu-id="aff9b-156">[String]$exportFileName = "UserDeviceComplianceStatus_" + (Get-Date -Format "yyMMdd_HHMMss") + ".csv",</span></span>

6.  <span data-ttu-id="aff9b-157">[Tekenreeks]$exportPath = [Omgeving]::GetFolderPath("Bureaublad")</span><span class="sxs-lookup"><span data-stu-id="aff9b-157">[String]$exportPath = [Environment]::GetFolderPath("Desktop")</span></span>

7.  <span data-ttu-id="aff9b-158">)</span><span class="sxs-lookup"><span data-stu-id="aff9b-158">)</span></span>

9.  <span data-ttu-id="aff9b-159">[System.Collections.IDictionary]$script:schema = @{</span><span class="sxs-lookup"><span data-stu-id="aff9b-159">[System.Collections.IDictionary]$script:schema = @{</span></span>

11.  <span data-ttu-id="aff9b-160">DeviceId = ''</span><span class="sxs-lookup"><span data-stu-id="aff9b-160">DeviceId = ''</span></span>

12.  <span data-ttu-id="aff9b-161">DeviceOSType = ''</span><span class="sxs-lookup"><span data-stu-id="aff9b-161">DeviceOSType = ''</span></span>

13.  <span data-ttu-id="aff9b-162">DeviceOSVersion = ''</span><span class="sxs-lookup"><span data-stu-id="aff9b-162">DeviceOSVersion = ''</span></span>

14.  <span data-ttu-id="aff9b-163">DeviceTrustLevel = ''</span><span class="sxs-lookup"><span data-stu-id="aff9b-163">DeviceTrustLevel = ''</span></span>

15.  <span data-ttu-id="aff9b-164">DisplayName = ''</span><span class="sxs-lookup"><span data-stu-id="aff9b-164">DisplayName = ''</span></span>

16.  <span data-ttu-id="aff9b-165">IsCompliant = ''</span><span class="sxs-lookup"><span data-stu-id="aff9b-165">IsCompliant = ''</span></span>

17.  <span data-ttu-id="aff9b-166">IsManaged = ''</span><span class="sxs-lookup"><span data-stu-id="aff9b-166">IsManaged = ''</span></span>

18.  <span data-ttu-id="aff9b-167">ApproximateLastLogonTimestamp = ''</span><span class="sxs-lookup"><span data-stu-id="aff9b-167">ApproximateLastLogonTimestamp = ''</span></span>

19.  <span data-ttu-id="aff9b-168">DeviceObjectId = ''</span><span class="sxs-lookup"><span data-stu-id="aff9b-168">DeviceObjectId = ''</span></span>

20.  <span data-ttu-id="aff9b-169">RegisteredOwnerUpn = ''</span><span class="sxs-lookup"><span data-stu-id="aff9b-169">RegisteredOwnerUpn = ''</span></span>

21.  <span data-ttu-id="aff9b-170">RegisteredOwnerObjectId = ''</span><span class="sxs-lookup"><span data-stu-id="aff9b-170">RegisteredOwnerObjectId = ''</span></span>
    

22.  <span data-ttu-id="aff9b-171">RegisteredOwnerDisplayName = ''</span><span class="sxs-lookup"><span data-stu-id="aff9b-171">RegisteredOwnerDisplayName = ''</span></span>
    

23.  <span data-ttu-id="aff9b-172">}</span><span class="sxs-lookup"><span data-stu-id="aff9b-172">}</span></span>
    

25.  <span data-ttu-id="aff9b-173">functie createResultObject</span><span class="sxs-lookup"><span data-stu-id="aff9b-173">function createResultObject</span></span>
    

26.  <span data-ttu-id="aff9b-174">{</span><span class="sxs-lookup"><span data-stu-id="aff9b-174">{</span></span>
    

28.  <span data-ttu-id="aff9b-175">[PSObject]$resultObject = New-Object -TypeName PSObject -Eigenschap $script:schema</span><span class="sxs-lookup"><span data-stu-id="aff9b-175">[PSObject]$resultObject = New-Object -TypeName PSObject -Property $script:schema</span></span>
    

30.  <span data-ttu-id="aff9b-176">retourn $resultObject</span><span class="sxs-lookup"><span data-stu-id="aff9b-176">return $resultObject</span></span>
    

31.  <span data-ttu-id="aff9b-177">}</span><span class="sxs-lookup"><span data-stu-id="aff9b-177">}</span></span>
    

33.  <span data-ttu-id="aff9b-178">Als ($users. Aantal -eq 0)</span><span class="sxs-lookup"><span data-stu-id="aff9b-178">If ($users.Count -eq 0)</span></span>
    

34.  <span data-ttu-id="aff9b-179">{</span><span class="sxs-lookup"><span data-stu-id="aff9b-179">{</span></span>
    

35.  <span data-ttu-id="aff9b-180">$users = Get-MsolUser</span><span class="sxs-lookup"><span data-stu-id="aff9b-180">$users = Get-MsolUser</span></span>
    

36.  <span data-ttu-id="aff9b-181">}</span><span class="sxs-lookup"><span data-stu-id="aff9b-181">}</span></span>
    

38.  <span data-ttu-id="aff9b-182">[PSObject[]]$result = foreach ($u in $users)</span><span class="sxs-lookup"><span data-stu-id="aff9b-182">[PSObject[]]$result = foreach ($u in $users)</span></span>
    

39.  <span data-ttu-id="aff9b-183">{</span><span class="sxs-lookup"><span data-stu-id="aff9b-183">{</span></span>
    

41.  <span data-ttu-id="aff9b-184">[PSObject]$devices = get-msoldevice -RegisteredOwnerUpn $u.UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="aff9b-184">[PSObject]$devices = get-msoldevice -RegisteredOwnerUpn $u.UserPrincipalName</span></span>
    

42.  <span data-ttu-id="aff9b-185">foreach ($d in $devices)</span><span class="sxs-lookup"><span data-stu-id="aff9b-185">foreach ($d in $devices)</span></span>
    

43.  <span data-ttu-id="aff9b-186">{</span><span class="sxs-lookup"><span data-stu-id="aff9b-186">{</span></span>
    

44.  <span data-ttu-id="aff9b-187">[PSObject]$deviceResult = createResultObject</span><span class="sxs-lookup"><span data-stu-id="aff9b-187">[PSObject]$deviceResult = createResultObject</span></span>
    

45.  <span data-ttu-id="aff9b-188">$deviceResult.DeviceId = $d.DeviceId</span><span class="sxs-lookup"><span data-stu-id="aff9b-188">$deviceResult.DeviceId = $d.DeviceId</span></span>
    

46.  <span data-ttu-id="aff9b-189">$deviceResult.DeviceOSType = $d.DeviceOSType</span><span class="sxs-lookup"><span data-stu-id="aff9b-189">$deviceResult.DeviceOSType = $d.DeviceOSType</span></span>
    

47.  <span data-ttu-id="aff9b-190">$deviceResult.DeviceOSVersion = $d.DeviceOSVersion</span><span class="sxs-lookup"><span data-stu-id="aff9b-190">$deviceResult.DeviceOSVersion = $d.DeviceOSVersion</span></span>
    

48.  <span data-ttu-id="aff9b-191">$deviceResult.DeviceTrustLevel = $d.DeviceTrustLevel</span><span class="sxs-lookup"><span data-stu-id="aff9b-191">$deviceResult.DeviceTrustLevel = $d.DeviceTrustLevel</span></span>
    

49.  <span data-ttu-id="aff9b-192">$deviceResult.DisplayName = $d.DisplayName</span><span class="sxs-lookup"><span data-stu-id="aff9b-192">$deviceResult.DisplayName = $d.DisplayName</span></span>
    

50.  <span data-ttu-id="aff9b-193">$deviceResult.IsCompliant = $d.GraphDeviceObject.IsCompliant</span><span class="sxs-lookup"><span data-stu-id="aff9b-193">$deviceResult.IsCompliant = $d.GraphDeviceObject.IsCompliant</span></span>
    

51.  <span data-ttu-id="aff9b-194">$deviceResult.IsManaged = $d.GraphDeviceObject.IsManaged</span><span class="sxs-lookup"><span data-stu-id="aff9b-194">$deviceResult.IsManaged = $d.GraphDeviceObject.IsManaged</span></span>
    

52.  <span data-ttu-id="aff9b-195">$deviceResult.DeviceObjectId = $d.ObjectId</span><span class="sxs-lookup"><span data-stu-id="aff9b-195">$deviceResult.DeviceObjectId = $d.ObjectId</span></span>
    

53.  <span data-ttu-id="aff9b-196">$deviceResult.RegisteredOwnerUpn = $u.UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="aff9b-196">$deviceResult.RegisteredOwnerUpn = $u.UserPrincipalName</span></span>
    

54.  <span data-ttu-id="aff9b-197">$deviceResult.RegisteredOwnerObjectId = $u.ObjectId</span><span class="sxs-lookup"><span data-stu-id="aff9b-197">$deviceResult.RegisteredOwnerObjectId = $u.ObjectId</span></span>
    

55.  <span data-ttu-id="aff9b-198">$deviceResult.RegisteredOwnerDisplayName = $u.DisplayName</span><span class="sxs-lookup"><span data-stu-id="aff9b-198">$deviceResult.RegisteredOwnerDisplayName = $u.DisplayName</span></span>
    

56.  <span data-ttu-id="aff9b-199">$deviceResult.ApproximateLastLogonTimestamp = $d.ApproximateLastLogonTimestamp</span><span class="sxs-lookup"><span data-stu-id="aff9b-199">$deviceResult.ApproximateLastLogonTimestamp = $d.ApproximateLastLogonTimestamp</span></span>
    

58.  <span data-ttu-id="aff9b-200">$deviceResult</span><span class="sxs-lookup"><span data-stu-id="aff9b-200">$deviceResult</span></span>
    

59.  <span data-ttu-id="aff9b-201">}</span><span class="sxs-lookup"><span data-stu-id="aff9b-201">}</span></span>
    

61.  <span data-ttu-id="aff9b-202">}</span><span class="sxs-lookup"><span data-stu-id="aff9b-202">}</span></span>
    

63.  <span data-ttu-id="aff9b-203">Als ($export)</span><span class="sxs-lookup"><span data-stu-id="aff9b-203">If ($export)</span></span>
    

64.  <span data-ttu-id="aff9b-204">{</span><span class="sxs-lookup"><span data-stu-id="aff9b-204">{</span></span>
    

65.  <span data-ttu-id="aff9b-205">$result | Export-Csv -pad ($exportPath + " \" + $exportFileName) -NoTypeInformation</span><span class="sxs-lookup"><span data-stu-id="aff9b-205">$result | Export-Csv -path ($exportPath + "\" + $exportFileName) -NoTypeInformation</span></span>
    

66.  <span data-ttu-id="aff9b-206">}</span><span class="sxs-lookup"><span data-stu-id="aff9b-206">}</span></span>
    

67.  <span data-ttu-id="aff9b-207">Else</span><span class="sxs-lookup"><span data-stu-id="aff9b-207">Else</span></span>
    

68.  <span data-ttu-id="aff9b-208">{</span><span class="sxs-lookup"><span data-stu-id="aff9b-208">{</span></span>
    

69.  <span data-ttu-id="aff9b-209">$result</span><span class="sxs-lookup"><span data-stu-id="aff9b-209">$result</span></span>
    

70.  <span data-ttu-id="aff9b-210">}</span><span class="sxs-lookup"><span data-stu-id="aff9b-210">}</span></span>
    

71.  <span data-ttu-id="aff9b-211">Sla het op als een Windows PowerShell scriptbestand met behulp van de bestandsextensie .ps1; bijvoorbeeld Get-MsolUserDeviceComplianceStatus.ps1.</span><span class="sxs-lookup"><span data-stu-id="aff9b-211">Save it as a Windows PowerShell script file by using the file extension .ps1; for example, Get-MsolUserDeviceComplianceStatus.ps1.</span></span>   

## <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a><span data-ttu-id="aff9b-212">Voer het script uit om apparaatgegevens voor één gebruikersaccount op te halen</span><span class="sxs-lookup"><span data-stu-id="aff9b-212">Run the script to get device information for a single user account</span></span>

1. <span data-ttu-id="aff9b-213">Open de Microsoft Azure Active Directory module voor Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="aff9b-213">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>
    
2. <span data-ttu-id="aff9b-214">Ga naar de map waar u het script hebt opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="aff9b-214">Go to the folder where you saved the script.</span></span> <span data-ttu-id="aff9b-215">Als u de opdracht bijvoorbeeld hebt opgeslagen in C:\PS-Scripts, voer dan de volgende opdracht uit.</span><span class="sxs-lookup"><span data-stu-id="aff9b-215">For example, if you saved it to C:\PS-Scripts, run the following command.</span></span>
    
    <span data-ttu-id="aff9b-216">cd C:\PS-Scripts</span><span class="sxs-lookup"><span data-stu-id="aff9b-216">cd C:\PS-Scripts</span></span>

3. <span data-ttu-id="aff9b-217">Voer de volgende opdracht uit om de gebruiker te identificeren voor wie u apparaatgegevens wilt krijgen.</span><span class="sxs-lookup"><span data-stu-id="aff9b-217">Run the following command to identify the user you want to get device details for.</span></span> <span data-ttu-id="aff9b-218">In dit voorbeeld worden details voor bar@example.com.</span><span class="sxs-lookup"><span data-stu-id="aff9b-218">This example gets details for bar@example.com.</span></span>
    
    <span data-ttu-id="aff9b-219">$u = Get-MsolUser -UserPrincipalName bar@example.com</span><span class="sxs-lookup"><span data-stu-id="aff9b-219">$u = Get-MsolUser -UserPrincipalName bar@example.com</span></span>

4. <span data-ttu-id="aff9b-220">Voer de volgende opdracht uit om het script te starten.</span><span class="sxs-lookup"><span data-stu-id="aff9b-220">Run the following command to initiate the script.</span></span>

    <span data-ttu-id="aff9b-221">.\Get-MsolUserDeviceComplianceStatus.ps1 -Gebruiker $u -Exporteren</span><span class="sxs-lookup"><span data-stu-id="aff9b-221">.\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export</span></span>

<span data-ttu-id="aff9b-222">De gegevens worden geëxporteerd naar uw Windows bureaublad als een CSV-bestand.</span><span class="sxs-lookup"><span data-stu-id="aff9b-222">The information is exported to your Windows Desktop as a CSV file.</span></span> <span data-ttu-id="aff9b-223">U kunt extra parameters gebruiken om de bestandsnaam en het pad van de CSV op te geven.</span><span class="sxs-lookup"><span data-stu-id="aff9b-223">You can use additional parameters to specify the file name and path of the CSV.</span></span>

## <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a><span data-ttu-id="aff9b-224">Voer het script uit om apparaatgegevens voor een groep gebruikers op te halen</span><span class="sxs-lookup"><span data-stu-id="aff9b-224">Run the script to get device information for a group of users</span></span>

1. <span data-ttu-id="aff9b-225">Open de Microsoft Azure Active Directory module voor Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="aff9b-225">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>
    
2. <span data-ttu-id="aff9b-226">Ga naar de map waar u het script hebt opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="aff9b-226">Go to the folder where you saved the script.</span></span> <span data-ttu-id="aff9b-227">Als u de opdracht bijvoorbeeld hebt opgeslagen in C:\PS-Scripts, voer dan de volgende opdracht uit.</span><span class="sxs-lookup"><span data-stu-id="aff9b-227">For example, if you saved it to C:\PS-Scripts, run the following command.</span></span>   

    <span data-ttu-id="aff9b-228">cd C:\PS-Scripts</span><span class="sxs-lookup"><span data-stu-id="aff9b-228">cd C:\PS-Scripts</span></span>

3. <span data-ttu-id="aff9b-229">Voer de volgende opdracht uit om de groep te identificeren voor wie u apparaatgegevens wilt krijgen.</span><span class="sxs-lookup"><span data-stu-id="aff9b-229">Run the following command to identify the group you want to get device details for.</span></span> <span data-ttu-id="aff9b-230">In dit voorbeeld worden details voor gebruikers in de groep FinanceStaff op de voor u staan.</span><span class="sxs-lookup"><span data-stu-id="aff9b-230">This example gets details for users in the FinanceStaff group.</span></span> 

    <span data-ttu-id="aff9b-231">$u = Get-MsolGroupMember -SearchString "FinanceStaff" | % { Get-MsolUser -ObjectId $_. ObjectId }</span><span class="sxs-lookup"><span data-stu-id="aff9b-231">$u = Get-MsolGroupMember -SearchString "FinanceStaff" | % { Get-MsolUser -ObjectId $_.ObjectId }</span></span>

4. <span data-ttu-id="aff9b-232">Voer de volgende opdracht uit om het script te starten.</span><span class="sxs-lookup"><span data-stu-id="aff9b-232">Run the following command to initiate the script.</span></span>

    <span data-ttu-id="aff9b-233">.\Get-MsolUserDeviceComplianceStatus.ps1 -Gebruiker $u -Exporteren</span><span class="sxs-lookup"><span data-stu-id="aff9b-233">.\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export</span></span>

<span data-ttu-id="aff9b-234">De gegevens worden geëxporteerd naar uw Windows bureaublad als een CSV-bestand.</span><span class="sxs-lookup"><span data-stu-id="aff9b-234">The information is exported to your Windows Desktop as a CSV file.</span></span> <span data-ttu-id="aff9b-235">U kunt extra parameters gebruiken om de bestandsnaam en het pad van de CSV op te geven.</span><span class="sxs-lookup"><span data-stu-id="aff9b-235">You can use additional parameters to specify the file name and path of the CSV.</span></span>

## <a name="related-topics"></a><span data-ttu-id="aff9b-236">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="aff9b-236">Related topics</span></span>

[<span data-ttu-id="aff9b-237">Microsoft Verbinding maken is met pensioen</span><span class="sxs-lookup"><span data-stu-id="aff9b-237">Microsoft Connect Has Been Retired</span></span>](/collaborate/connect-redirect)

[<span data-ttu-id="aff9b-238">Overzicht van de Basic Mobility en Security</span><span class="sxs-lookup"><span data-stu-id="aff9b-238">Overview of Basic Mobility and Security</span></span>](overview.md)

[<span data-ttu-id="aff9b-239">Get-MsolDevice</span><span class="sxs-lookup"><span data-stu-id="aff9b-239">Get-MsolDevice</span></span>](https://go.microsoft.com/fwlink/?linkid=2157939)