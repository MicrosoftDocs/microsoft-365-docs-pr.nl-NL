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
ms.openlocfilehash: 92fcd6f39ffff97d7a4ecd2a69626ece54b481b2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904250"
---
# <a name="get-details-about-basic-mobility-and-security-managed-devices"></a><span data-ttu-id="94004-103">Meer informatie over beheerde basisapparaten voor mobiliteit en beveiliging</span><span class="sxs-lookup"><span data-stu-id="94004-103">Get details about Basic Mobility and Security managed devices</span></span>

<span data-ttu-id="94004-104">In dit artikel wordt beschreven hoe u Windows PowerShell gebruikt voor meer informatie over de apparaten in uw organisatie die u hebt ingesteld voor Basismobiliteit en Beveiliging.</span><span class="sxs-lookup"><span data-stu-id="94004-104">This article shows you how to use Windows PowerShell to get details about the devices in your organization that you set up for Basic Mobility and Security.</span></span>

<span data-ttu-id="94004-105">Hier ziet u een overzicht van de apparaatdetails die voor u beschikbaar zijn.</span><span class="sxs-lookup"><span data-stu-id="94004-105">Here's a breakdown for the device details available to you.</span></span>

|<span data-ttu-id="94004-106">**Details**</span><span class="sxs-lookup"><span data-stu-id="94004-106">**Detail**</span></span>|<span data-ttu-id="94004-107">**Waar moet u naar zoeken in PowerShell**</span><span class="sxs-lookup"><span data-stu-id="94004-107">**What to look for in PowerShell**</span></span>|
|:----------------|:------------------------------------------------------------------------------|
|<span data-ttu-id="94004-108">Apparaat is geregistreerd voor Basismobiliteit en Beveiliging.</span><span class="sxs-lookup"><span data-stu-id="94004-108">Device is enrolled in Basic Mobility and Security.</span></span> <span data-ttu-id="94004-109">Zie Uw mobiele apparaat registreren met [basismobiliteit en beveiliging voor meer informatie.](enroll-your-mobile-device.md)</span><span class="sxs-lookup"><span data-stu-id="94004-109">For more info, see [Enroll your mobile device using Basic Mobility and Security](enroll-your-mobile-device.md)</span></span>|<span data-ttu-id="94004-110">De waarde van de *parameter isManaged*   is:</span><span class="sxs-lookup"><span data-stu-id="94004-110">The value of the *isManaged* parameter is:</span></span><br/><span data-ttu-id="94004-111">**True**= apparaat is geregistreerd.</span><span class="sxs-lookup"><span data-stu-id="94004-111">**True**= device is enrolled.</span></span><br/><span data-ttu-id="94004-112">**False**= apparaat is niet geregistreerd.</span><span class="sxs-lookup"><span data-stu-id="94004-112">**False**= device is not enrolled.</span></span> |
|<span data-ttu-id="94004-113">Apparaat voldoet aan het beveiligingsbeleid van uw apparaat.</span><span class="sxs-lookup"><span data-stu-id="94004-113">Device is compliant with your device security policies.</span></span> <span data-ttu-id="94004-114">Zie Apparaatbeveiligingsbeleid [maken voor meer informatie](create-device-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="94004-114">For more info, see [Create device security policies](create-device-security-policies.md)</span></span>|<span data-ttu-id="94004-115">De waarde van de *parameter IsCompliant*   is:</span><span class="sxs-lookup"><span data-stu-id="94004-115">The value of the *isCompliant* parameter is:</span></span><br/><span data-ttu-id="94004-116">**Waar**   = apparaat voldoet aan beleidsregels.</span><span class="sxs-lookup"><span data-stu-id="94004-116">**True** = device is compliant with policies.</span></span><br/><span data-ttu-id="94004-117">**Onwaar**   = apparaat voldoet niet aan beleidsregels.</span><span class="sxs-lookup"><span data-stu-id="94004-117">**False** = device is not compliant with policies.</span></span>|

:::image type="content" source="../../media/basic-mobility-security/bms-7-powershell-parameters.png" alt-text="PowerShell-parameters voor basismobiliteit en beveiliging":::

>[!NOTE]
><span data-ttu-id="94004-119">De opdrachten en scripts in dit artikel geven ook informatie weer over apparaten die worden beheerd door [Microsoft Intune.](https://www.microsoft.com/cloud-platform/microsoft-intune)</span><span class="sxs-lookup"><span data-stu-id="94004-119">The commands and scripts in this article also return details about any devices managed by [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="94004-120">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="94004-120">Before you begin</span></span>

<span data-ttu-id="94004-121">Er zijn een paar dingen die u moet instellen om de opdrachten en scripts uit te voeren die in dit artikel worden beschreven.</span><span class="sxs-lookup"><span data-stu-id="94004-121">There are a few things you need to set up to run the commands and scripts described in this article.</span></span>

### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="94004-122">Stap 1: De Azure Active Directory-module voor Windows PowerShell downloaden en installeren</span><span class="sxs-lookup"><span data-stu-id="94004-122">Step 1: Download and install the Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="94004-123">Zie Verbinding maken met [Microsoft 365 met PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell)voor meer informatie over deze stappen.</span><span class="sxs-lookup"><span data-stu-id="94004-123">For more info on these steps, see [Connect to Microsoft 365 with PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell).</span></span>

1. <span data-ttu-id="94004-124">Ga naar Microsoft Online Services Sign-In Assistent voor [IT-professionals RTWl](https://www.microsoft.com/download/details.aspx?id=41950)en   selecteer Downloaden voor Microsoft Online Services  **Aanmeldingsassistent**.</span><span class="sxs-lookup"><span data-stu-id="94004-124">Go to [Microsoft Online Services Sign-In Assistant for IT Professionals RTWl](https://www.microsoft.com/download/details.aspx?id=41950) and select  **Download for Microsoft Online Services Sign-in Assistant**.</span></span>

2. <span data-ttu-id="94004-125">Installeer de module Microsoft Azure Active Directory voor Windows PowerShell met deze stappen:</span><span class="sxs-lookup"><span data-stu-id="94004-125">Install the Microsoft Azure Active Directory Module for Windows PowerShell with these steps:</span></span>

    1. <span data-ttu-id="94004-126">Open een PowerShell-opdrachtprompt op beheerdersniveau.</span><span class="sxs-lookup"><span data-stu-id="94004-126">Open an administrator-level PowerShell command prompt.</span></span>  

    2. <span data-ttu-id="94004-127">Voer de installatie-module MSOnline uit.</span><span class="sxs-lookup"><span data-stu-id="94004-127">Run the Install-Module MSOnline command.</span></span>

    3. <span data-ttu-id="94004-128">Als u wordt gevraagd om de NuGet provider te installeren, typt u Y en drukt u op ENTER.</span><span class="sxs-lookup"><span data-stu-id="94004-128">If prompted to install the NuGet provider, type Y and press ENTER.</span></span>

    4. <span data-ttu-id="94004-129">Als u wordt gevraagd om de module van PSGallery te installeren, typt u Y en drukt u op ENTER.</span><span class="sxs-lookup"><span data-stu-id="94004-129">If prompted to install the module from PSGallery, type Y and press ENTER.</span></span>

    5. <span data-ttu-id="94004-130">Sluit na de installatie het powershell-opdrachtvenster.</span><span class="sxs-lookup"><span data-stu-id="94004-130">After installation, close the PowerShell command window.</span></span>

### <a name="step-2-connect-to-your-microsoft-365-subscription"></a><span data-ttu-id="94004-131">Stap 2: Verbinding maken met uw Microsoft 365-abonnement</span><span class="sxs-lookup"><span data-stu-id="94004-131">Step 2: Connect to your Microsoft 365 subscription</span></span>

1. <span data-ttu-id="94004-132">Voer in de Windows Azure Active Directory-module voor Windows PowerShell de volgende opdracht uit.</span><span class="sxs-lookup"><span data-stu-id="94004-132">In the Windows Azure Active Directory Module for Windows PowerShell, run the following command.</span></span>  

    <span data-ttu-id="94004-133">$UserCredential = Get-Credential</span><span class="sxs-lookup"><span data-stu-id="94004-133">$UserCredential = Get-Credential</span></span>

2. <span data-ttu-id="94004-134">Typ in het dialoogvenster Aanmeldingsaanvraag voor Windows PowerShell de gebruikersnaam en het wachtwoord voor uw globale beheerdersaccount van Microsoft 365 en selecteer **OK.**</span><span class="sxs-lookup"><span data-stu-id="94004-134">In the Windows PowerShell Credential Request dialog box, type the user name and password for your Microsoft 365 global admin account, and then select **OK**.</span></span>

3. <span data-ttu-id="94004-135">Voer de volgende opdracht uit.</span><span class="sxs-lookup"><span data-stu-id="94004-135">Run the following command.</span></span>

    <span data-ttu-id="94004-136">Connect-MsolService -Credential $UserCredential</span><span class="sxs-lookup"><span data-stu-id="94004-136">Connect-MsolService -Credential $UserCredential</span></span>

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a><span data-ttu-id="94004-137">Stap 3: Zorg ervoor dat u PowerShell-scripts kunt uitvoeren</span><span class="sxs-lookup"><span data-stu-id="94004-137">Step 3: Make sure you’re able to run PowerShell scripts</span></span>

>[!NOTE]
><span data-ttu-id="94004-138">U kunt deze stap overslaan als u al bent ingesteld voor het uitvoeren van PowerShell-scripts.</span><span class="sxs-lookup"><span data-stu-id="94004-138">You can skip this step if you’re already set up to run PowerShell scripts.</span></span>

<span data-ttu-id="94004-139">Als u het script Get-MsolUserDeviceComplianceStatus.ps1 uitvoeren, moet u het uitvoeren van PowerShell-scripts inschakelen.</span><span class="sxs-lookup"><span data-stu-id="94004-139">To run the Get-MsolUserDeviceComplianceStatus.ps1 script, you need to enable the running of PowerShell scripts.</span></span>

1. <span data-ttu-id="94004-140">Selecteer start op uw Windows-bureaublad **en** typ vervolgens Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="94004-140">From your Windows Desktop, select **Start**, and then type Windows PowerShell.</span></span> <span data-ttu-id="94004-141">Klik met de rechtermuisknop op Windows PowerShell en selecteer **vervolgens Uitvoeren als beheerder.**</span><span class="sxs-lookup"><span data-stu-id="94004-141">Right-click Windows PowerShell, and then select **Run as administrator**.</span></span>

2. <span data-ttu-id="94004-142">Voer de volgende opdracht uit.</span><span class="sxs-lookup"><span data-stu-id="94004-142">Run the following command.</span></span>

    <span data-ttu-id="94004-143">Set-ExecutionPolicy RemoteSigned</span><span class="sxs-lookup"><span data-stu-id="94004-143">Set-ExecutionPolicy  RemoteSigned</span></span>

3. <span data-ttu-id="94004-144">Wanneer u daarom wordt gevraagd, typt u Y en drukt u op Enter.</span><span class="sxs-lookup"><span data-stu-id="94004-144">When prompted, type Y and then press Enter.</span></span>

<span data-ttu-id="94004-145">**Voer de Get-MsolDevice cmdlet uit om details weer te geven voor alle apparaten in uw organisatie**</span><span class="sxs-lookup"><span data-stu-id="94004-145">**Run the Get-MsolDevice cmdlet to display details for all devices in your organization**</span></span>

1. <span data-ttu-id="94004-146">Open de Microsoft Azure Active Directory-module voor Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="94004-146">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>  

2. <span data-ttu-id="94004-147">Voer de volgende opdracht uit.</span><span class="sxs-lookup"><span data-stu-id="94004-147">Run the following command.</span></span>

    <span data-ttu-id="94004-148">Get-MsolDevice -All -ReturnRegisteredOwners | Where-Object {$_. RegisteredOwners.Count -gt 0}</span><span class="sxs-lookup"><span data-stu-id="94004-148">Get-MsolDevice -All -ReturnRegisteredOwners | Where-Object {$_.RegisteredOwners.Count -gt 0}</span></span>

<span data-ttu-id="94004-149">Zie  [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=2157939)voor meer voorbeelden.</span><span class="sxs-lookup"><span data-stu-id="94004-149">For more examples, see  [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=2157939).</span></span>

## <a name="run-a-script-to-get-device-details"></a><span data-ttu-id="94004-150">Een script uitvoeren om apparaatdetails op te halen</span><span class="sxs-lookup"><span data-stu-id="94004-150">Run a script to get device details</span></span>

<span data-ttu-id="94004-151">Sla eerst het script op uw computer op.</span><span class="sxs-lookup"><span data-stu-id="94004-151">First, save the script to your computer.</span></span>

1. <span data-ttu-id="94004-152">Kopieer en plak de volgende tekst in Kladblok.</span><span class="sxs-lookup"><span data-stu-id="94004-152">Copy and paste the following text into Notepad.</span></span>  

2.  <span data-ttu-id="94004-153">param (</span><span class="sxs-lookup"><span data-stu-id="94004-153">param (</span></span>

3.  <span data-ttu-id="94004-154">[PSObject[]]$users = @(),</span><span class="sxs-lookup"><span data-stu-id="94004-154">[PSObject[]]$users = @(),</span></span>

4.  <span data-ttu-id="94004-155">[Schakel]$export,</span><span class="sxs-lookup"><span data-stu-id="94004-155">[Switch]$export,</span></span>

5.  <span data-ttu-id="94004-156">[Tekenreeks]$exportFileName = "UserDeviceComplianceStatus_" + (Get-Date -Format "yyMMdd_HHMMss") + ".csv",</span><span class="sxs-lookup"><span data-stu-id="94004-156">[String]$exportFileName = "UserDeviceComplianceStatus_" + (Get-Date -Format "yyMMdd_HHMMss") + ".csv",</span></span>

6.  <span data-ttu-id="94004-157">[Tekenreeks]$exportPath = [Omgeving]::GetFolderPath("Bureaublad")</span><span class="sxs-lookup"><span data-stu-id="94004-157">[String]$exportPath = [Environment]::GetFolderPath("Desktop")</span></span>

7.  <span data-ttu-id="94004-158">)</span><span class="sxs-lookup"><span data-stu-id="94004-158">)</span></span>

9.  <span data-ttu-id="94004-159">[System.Collections.IDictionary]$script:schema = @{</span><span class="sxs-lookup"><span data-stu-id="94004-159">[System.Collections.IDictionary]$script:schema = @{</span></span>

11.  <span data-ttu-id="94004-160">DeviceId = ''</span><span class="sxs-lookup"><span data-stu-id="94004-160">DeviceId = ''</span></span>

12.  <span data-ttu-id="94004-161">DeviceOSType = ''</span><span class="sxs-lookup"><span data-stu-id="94004-161">DeviceOSType = ''</span></span>

13.  <span data-ttu-id="94004-162">DeviceOSVersion = ''</span><span class="sxs-lookup"><span data-stu-id="94004-162">DeviceOSVersion = ''</span></span>

14.  <span data-ttu-id="94004-163">DeviceTrustLevel = ''</span><span class="sxs-lookup"><span data-stu-id="94004-163">DeviceTrustLevel = ''</span></span>

15.  <span data-ttu-id="94004-164">DisplayName = ''</span><span class="sxs-lookup"><span data-stu-id="94004-164">DisplayName = ''</span></span>

16.  <span data-ttu-id="94004-165">IsCompliant = ''</span><span class="sxs-lookup"><span data-stu-id="94004-165">IsCompliant = ''</span></span>

17.  <span data-ttu-id="94004-166">IsManaged = ''</span><span class="sxs-lookup"><span data-stu-id="94004-166">IsManaged = ''</span></span>

18.  <span data-ttu-id="94004-167">ApproximateLastLogonTimestamp = ''</span><span class="sxs-lookup"><span data-stu-id="94004-167">ApproximateLastLogonTimestamp = ''</span></span>

19.  <span data-ttu-id="94004-168">DeviceObjectId = ''</span><span class="sxs-lookup"><span data-stu-id="94004-168">DeviceObjectId = ''</span></span>

20.  <span data-ttu-id="94004-169">RegisteredOwnerUpn = ''</span><span class="sxs-lookup"><span data-stu-id="94004-169">RegisteredOwnerUpn = ''</span></span>

21.  <span data-ttu-id="94004-170">RegisteredOwnerObjectId = ''</span><span class="sxs-lookup"><span data-stu-id="94004-170">RegisteredOwnerObjectId = ''</span></span>
    

22.  <span data-ttu-id="94004-171">RegisteredOwnerDisplayName = ''</span><span class="sxs-lookup"><span data-stu-id="94004-171">RegisteredOwnerDisplayName = ''</span></span>
    

23.  <span data-ttu-id="94004-172">}</span><span class="sxs-lookup"><span data-stu-id="94004-172">}</span></span>
    

25.  <span data-ttu-id="94004-173">functie createResultObject</span><span class="sxs-lookup"><span data-stu-id="94004-173">function createResultObject</span></span>
    

26.  <span data-ttu-id="94004-174">{</span><span class="sxs-lookup"><span data-stu-id="94004-174">{</span></span>
    

28.  <span data-ttu-id="94004-175">[PSObject]$resultObject = New-Object -TypeName PSObject -Eigenschap $script:schema</span><span class="sxs-lookup"><span data-stu-id="94004-175">[PSObject]$resultObject = New-Object -TypeName PSObject -Property $script:schema</span></span>
    

30.  <span data-ttu-id="94004-176">retourn $resultObject</span><span class="sxs-lookup"><span data-stu-id="94004-176">return $resultObject</span></span>
    

31.  <span data-ttu-id="94004-177">}</span><span class="sxs-lookup"><span data-stu-id="94004-177">}</span></span>
    

33.  <span data-ttu-id="94004-178">Als ($users. Aantal -eq 0)</span><span class="sxs-lookup"><span data-stu-id="94004-178">If ($users.Count -eq 0)</span></span>
    

34.  <span data-ttu-id="94004-179">{</span><span class="sxs-lookup"><span data-stu-id="94004-179">{</span></span>
    

35.  <span data-ttu-id="94004-180">$users = Get-MsolUser</span><span class="sxs-lookup"><span data-stu-id="94004-180">$users = Get-MsolUser</span></span>
    

36.  <span data-ttu-id="94004-181">}</span><span class="sxs-lookup"><span data-stu-id="94004-181">}</span></span>
    

38.  <span data-ttu-id="94004-182">[PSObject[]]$result = foreach ($u in $users)</span><span class="sxs-lookup"><span data-stu-id="94004-182">[PSObject[]]$result = foreach ($u in $users)</span></span>
    

39.  <span data-ttu-id="94004-183">{</span><span class="sxs-lookup"><span data-stu-id="94004-183">{</span></span>
    

41.  <span data-ttu-id="94004-184">[PSObject]$devices = get-msoldevice -RegisteredOwnerUpn $u.UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="94004-184">[PSObject]$devices = get-msoldevice -RegisteredOwnerUpn $u.UserPrincipalName</span></span>
    

42.  <span data-ttu-id="94004-185">foreach ($d in $devices)</span><span class="sxs-lookup"><span data-stu-id="94004-185">foreach ($d in $devices)</span></span>
    

43.  <span data-ttu-id="94004-186">{</span><span class="sxs-lookup"><span data-stu-id="94004-186">{</span></span>
    

44.  <span data-ttu-id="94004-187">[PSObject]$deviceResult = createResultObject</span><span class="sxs-lookup"><span data-stu-id="94004-187">[PSObject]$deviceResult = createResultObject</span></span>
    

45.  <span data-ttu-id="94004-188">$deviceResult.DeviceId = $d.DeviceId</span><span class="sxs-lookup"><span data-stu-id="94004-188">$deviceResult.DeviceId = $d.DeviceId</span></span>
    

46.  <span data-ttu-id="94004-189">$deviceResult.DeviceOSType = $d.DeviceOSType</span><span class="sxs-lookup"><span data-stu-id="94004-189">$deviceResult.DeviceOSType = $d.DeviceOSType</span></span>
    

47.  <span data-ttu-id="94004-190">$deviceResult.DeviceOSVersion = $d.DeviceOSVersion</span><span class="sxs-lookup"><span data-stu-id="94004-190">$deviceResult.DeviceOSVersion = $d.DeviceOSVersion</span></span>
    

48.  <span data-ttu-id="94004-191">$deviceResult.DeviceTrustLevel = $d.DeviceTrustLevel</span><span class="sxs-lookup"><span data-stu-id="94004-191">$deviceResult.DeviceTrustLevel = $d.DeviceTrustLevel</span></span>
    

49.  <span data-ttu-id="94004-192">$deviceResult.DisplayName = $d.DisplayName</span><span class="sxs-lookup"><span data-stu-id="94004-192">$deviceResult.DisplayName = $d.DisplayName</span></span>
    

50.  <span data-ttu-id="94004-193">$deviceResult.IsCompliant = $d.GraphDeviceObject.IsCompliant</span><span class="sxs-lookup"><span data-stu-id="94004-193">$deviceResult.IsCompliant = $d.GraphDeviceObject.IsCompliant</span></span>
    

51.  <span data-ttu-id="94004-194">$deviceResult.IsManaged = $d.GraphDeviceObject.IsManaged</span><span class="sxs-lookup"><span data-stu-id="94004-194">$deviceResult.IsManaged = $d.GraphDeviceObject.IsManaged</span></span>
    

52.  <span data-ttu-id="94004-195">$deviceResult.DeviceObjectId = $d.ObjectId</span><span class="sxs-lookup"><span data-stu-id="94004-195">$deviceResult.DeviceObjectId = $d.ObjectId</span></span>
    

53.  <span data-ttu-id="94004-196">$deviceResult.RegisteredOwnerUpn = $u.UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="94004-196">$deviceResult.RegisteredOwnerUpn = $u.UserPrincipalName</span></span>
    

54.  <span data-ttu-id="94004-197">$deviceResult.RegisteredOwnerObjectId = $u.ObjectId</span><span class="sxs-lookup"><span data-stu-id="94004-197">$deviceResult.RegisteredOwnerObjectId = $u.ObjectId</span></span>
    

55.  <span data-ttu-id="94004-198">$deviceResult.RegisteredOwnerDisplayName = $u.DisplayName</span><span class="sxs-lookup"><span data-stu-id="94004-198">$deviceResult.RegisteredOwnerDisplayName = $u.DisplayName</span></span>
    

56.  <span data-ttu-id="94004-199">$deviceResult.ApproximateLastLogonTimestamp = $d.ApproximateLastLogonTimestamp</span><span class="sxs-lookup"><span data-stu-id="94004-199">$deviceResult.ApproximateLastLogonTimestamp = $d.ApproximateLastLogonTimestamp</span></span>
    

58.  <span data-ttu-id="94004-200">$deviceResult</span><span class="sxs-lookup"><span data-stu-id="94004-200">$deviceResult</span></span>
    

59.  <span data-ttu-id="94004-201">}</span><span class="sxs-lookup"><span data-stu-id="94004-201">}</span></span>
    

61.  <span data-ttu-id="94004-202">}</span><span class="sxs-lookup"><span data-stu-id="94004-202">}</span></span>
    

63.  <span data-ttu-id="94004-203">Als ($export)</span><span class="sxs-lookup"><span data-stu-id="94004-203">If ($export)</span></span>
    

64.  <span data-ttu-id="94004-204">{</span><span class="sxs-lookup"><span data-stu-id="94004-204">{</span></span>
    

65.  <span data-ttu-id="94004-205">$result | Export-Csv -pad ($exportPath + " \" + $exportFileName) -NoTypeInformation</span><span class="sxs-lookup"><span data-stu-id="94004-205">$result | Export-Csv -path ($exportPath + "\" + $exportFileName) -NoTypeInformation</span></span>
    

66.  <span data-ttu-id="94004-206">}</span><span class="sxs-lookup"><span data-stu-id="94004-206">}</span></span>
    

67.  <span data-ttu-id="94004-207">Else</span><span class="sxs-lookup"><span data-stu-id="94004-207">Else</span></span>
    

68.  <span data-ttu-id="94004-208">{</span><span class="sxs-lookup"><span data-stu-id="94004-208">{</span></span>
    

69.  <span data-ttu-id="94004-209">$result</span><span class="sxs-lookup"><span data-stu-id="94004-209">$result</span></span>
    

70.  <span data-ttu-id="94004-210">}</span><span class="sxs-lookup"><span data-stu-id="94004-210">}</span></span>
    

71.  <span data-ttu-id="94004-211">Sla het op als een Windows PowerShell-scriptbestand met de bestandsextensie .ps1; bijvoorbeeld Get-MsolUserDeviceComplianceStatus.ps1.</span><span class="sxs-lookup"><span data-stu-id="94004-211">Save it as a Windows PowerShell script file by using the file extension .ps1; for example, Get-MsolUserDeviceComplianceStatus.ps1.</span></span>   

## <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a><span data-ttu-id="94004-212">Voer het script uit om apparaatgegevens voor één gebruikersaccount op te halen</span><span class="sxs-lookup"><span data-stu-id="94004-212">Run the script to get device information for a single user account</span></span>

1. <span data-ttu-id="94004-213">Open de Microsoft Azure Active Directory-module voor Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="94004-213">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>
    
2. <span data-ttu-id="94004-214">Ga naar de map waar u het script hebt opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="94004-214">Go to the folder where you saved the script.</span></span> <span data-ttu-id="94004-215">Als u de opdracht bijvoorbeeld hebt opgeslagen in C:\PS-Scripts, voer dan de volgende opdracht uit.</span><span class="sxs-lookup"><span data-stu-id="94004-215">For example, if you saved it to C:\PS-Scripts, run the following command.</span></span>
    
    <span data-ttu-id="94004-216">cd C:\PS-Scripts</span><span class="sxs-lookup"><span data-stu-id="94004-216">cd C:\PS-Scripts</span></span>

3. <span data-ttu-id="94004-217">Voer de volgende opdracht uit om de gebruiker te identificeren voor wie u apparaatgegevens wilt krijgen.</span><span class="sxs-lookup"><span data-stu-id="94004-217">Run the following command to identify the user you want to get device details for.</span></span> <span data-ttu-id="94004-218">In dit voorbeeld worden details voor bar@example.com.</span><span class="sxs-lookup"><span data-stu-id="94004-218">This example gets details for bar@example.com.</span></span>
    
    <span data-ttu-id="94004-219">$u = Get-MsolUser -UserPrincipalName bar@example.com</span><span class="sxs-lookup"><span data-stu-id="94004-219">$u = Get-MsolUser -UserPrincipalName bar@example.com</span></span>

4. <span data-ttu-id="94004-220">Voer de volgende opdracht uit om het script te starten.</span><span class="sxs-lookup"><span data-stu-id="94004-220">Run the following command to initiate the script.</span></span>

    <span data-ttu-id="94004-221">.\Get-MsolUserDeviceComplianceStatus.ps1 -Gebruiker $u -Exporteren</span><span class="sxs-lookup"><span data-stu-id="94004-221">.\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export</span></span>

<span data-ttu-id="94004-222">De gegevens worden geëxporteerd naar uw Windows-bureaublad als csv-bestand.</span><span class="sxs-lookup"><span data-stu-id="94004-222">The information is exported to your Windows Desktop as a CSV file.</span></span> <span data-ttu-id="94004-223">U kunt extra parameters gebruiken om de bestandsnaam en het pad van de CSV op te geven.</span><span class="sxs-lookup"><span data-stu-id="94004-223">You can use additional parameters to specify the file name and path of the CSV.</span></span>

## <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a><span data-ttu-id="94004-224">Voer het script uit om apparaatgegevens voor een groep gebruikers op te halen</span><span class="sxs-lookup"><span data-stu-id="94004-224">Run the script to get device information for a group of users</span></span>

1. <span data-ttu-id="94004-225">Open de Microsoft Azure Active Directory-module voor Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="94004-225">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>
    
2. <span data-ttu-id="94004-226">Ga naar de map waar u het script hebt opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="94004-226">Go to the folder where you saved the script.</span></span> <span data-ttu-id="94004-227">Als u de opdracht bijvoorbeeld hebt opgeslagen in C:\PS-Scripts, voer dan de volgende opdracht uit.</span><span class="sxs-lookup"><span data-stu-id="94004-227">For example, if you saved it to C:\PS-Scripts, run the following command.</span></span>   

    <span data-ttu-id="94004-228">cd C:\PS-Scripts</span><span class="sxs-lookup"><span data-stu-id="94004-228">cd C:\PS-Scripts</span></span>

3. <span data-ttu-id="94004-229">Voer de volgende opdracht uit om de groep te identificeren voor wie u apparaatgegevens wilt krijgen.</span><span class="sxs-lookup"><span data-stu-id="94004-229">Run the following command to identify the group you want to get device details for.</span></span> <span data-ttu-id="94004-230">In dit voorbeeld worden details voor gebruikers in de groep FinanceStaff op de voor u staan.</span><span class="sxs-lookup"><span data-stu-id="94004-230">This example gets details for users in the FinanceStaff group.</span></span> 

    <span data-ttu-id="94004-231">$u = Get-MsolGroupMember -SearchString "FinanceStaff" | % { Get-MsolUser -ObjectId $_. ObjectId }</span><span class="sxs-lookup"><span data-stu-id="94004-231">$u = Get-MsolGroupMember -SearchString "FinanceStaff" | % { Get-MsolUser -ObjectId $_.ObjectId }</span></span>

4. <span data-ttu-id="94004-232">Voer de volgende opdracht uit om het script te starten.</span><span class="sxs-lookup"><span data-stu-id="94004-232">Run the following command to initiate the script.</span></span>

    <span data-ttu-id="94004-233">.\Get-MsolUserDeviceComplianceStatus.ps1 -Gebruiker $u -Exporteren</span><span class="sxs-lookup"><span data-stu-id="94004-233">.\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export</span></span>

<span data-ttu-id="94004-234">De gegevens worden geëxporteerd naar uw Windows-bureaublad als csv-bestand.</span><span class="sxs-lookup"><span data-stu-id="94004-234">The information is exported to your Windows Desktop as a CSV file.</span></span> <span data-ttu-id="94004-235">U kunt extra parameters gebruiken om de bestandsnaam en het pad van de CSV op te geven.</span><span class="sxs-lookup"><span data-stu-id="94004-235">You can use additional parameters to specify the file name and path of the CSV.</span></span>

## <a name="related-topics"></a><span data-ttu-id="94004-236">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="94004-236">Related topics</span></span>

[<span data-ttu-id="94004-237">Microsoft Connect is met pensioen</span><span class="sxs-lookup"><span data-stu-id="94004-237">Microsoft Connect Has Been Retired</span></span>](/collaborate/connect-redirect)

[<span data-ttu-id="94004-238">Overzicht van de Basic Mobility en Security</span><span class="sxs-lookup"><span data-stu-id="94004-238">Overview of Basic Mobility and Security</span></span>](overview.md)

[<span data-ttu-id="94004-239">Get-MsolDevice</span><span class="sxs-lookup"><span data-stu-id="94004-239">Get-MsolDevice</span></span>](https://go.microsoft.com/fwlink/?linkid=2157939)