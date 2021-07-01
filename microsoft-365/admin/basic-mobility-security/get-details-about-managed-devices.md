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
ms.openlocfilehash: 2edee1b08f137d3e4f977b4d6800c1b0fc0e0473
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228169"
---
# <a name="get-details-about-basic-mobility-and-security-managed-devices"></a><span data-ttu-id="e4996-103">Meer informatie over beheerde basisapparaten voor mobiliteit en beveiliging</span><span class="sxs-lookup"><span data-stu-id="e4996-103">Get details about Basic Mobility and Security managed devices</span></span>

<span data-ttu-id="e4996-104">In dit artikel wordt beschreven hoe u Windows PowerShell voor meer informatie over de apparaten in uw organisatie die u hebt ingesteld voor Basismobiliteit en Beveiliging.</span><span class="sxs-lookup"><span data-stu-id="e4996-104">This article shows you how to use Windows PowerShell to get details about the devices in your organization that you set up for Basic Mobility and Security.</span></span>

<span data-ttu-id="e4996-105">Hier ziet u een overzicht van de apparaatdetails die voor u beschikbaar zijn.</span><span class="sxs-lookup"><span data-stu-id="e4996-105">Here's a breakdown for the device details available to you.</span></span>

|<span data-ttu-id="e4996-106">**Details**</span><span class="sxs-lookup"><span data-stu-id="e4996-106">**Detail**</span></span>|<span data-ttu-id="e4996-107">**Waar moet u naar zoeken in PowerShell**</span><span class="sxs-lookup"><span data-stu-id="e4996-107">**What to look for in PowerShell**</span></span>|
|:----------------|:------------------------------------------------------------------------------|
|<span data-ttu-id="e4996-108">Apparaat is geregistreerd voor Basismobiliteit en Beveiliging.</span><span class="sxs-lookup"><span data-stu-id="e4996-108">Device is enrolled in Basic Mobility and Security.</span></span> <span data-ttu-id="e4996-109">Zie Uw mobiele apparaat registreren met [basismobiliteit en beveiliging voor meer informatie.](enroll-your-mobile-device.md)</span><span class="sxs-lookup"><span data-stu-id="e4996-109">For more info, see [Enroll your mobile device using Basic Mobility and Security](enroll-your-mobile-device.md)</span></span>|<span data-ttu-id="e4996-110">De waarde van de *parameter isManaged*   is:</span><span class="sxs-lookup"><span data-stu-id="e4996-110">The value of the *isManaged* parameter is:</span></span><br/><span data-ttu-id="e4996-111">**True**= apparaat is geregistreerd.</span><span class="sxs-lookup"><span data-stu-id="e4996-111">**True**= device is enrolled.</span></span><br/><span data-ttu-id="e4996-112">**False**= apparaat is niet geregistreerd.</span><span class="sxs-lookup"><span data-stu-id="e4996-112">**False**= device is not enrolled.</span></span> |
|<span data-ttu-id="e4996-113">Apparaat voldoet aan het beveiligingsbeleid van uw apparaat.</span><span class="sxs-lookup"><span data-stu-id="e4996-113">Device is compliant with your device security policies.</span></span> <span data-ttu-id="e4996-114">Zie Apparaatbeveiligingsbeleid [maken voor meer informatie](create-device-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="e4996-114">For more info, see [Create device security policies](create-device-security-policies.md)</span></span>|<span data-ttu-id="e4996-115">De waarde van de *parameter IsCompliant*   is:</span><span class="sxs-lookup"><span data-stu-id="e4996-115">The value of the *isCompliant* parameter is:</span></span><br/><span data-ttu-id="e4996-116">**Waar**   = apparaat voldoet aan beleidsregels.</span><span class="sxs-lookup"><span data-stu-id="e4996-116">**True** = device is compliant with policies.</span></span><br/><span data-ttu-id="e4996-117">**Onwaar**   = apparaat voldoet niet aan beleidsregels.</span><span class="sxs-lookup"><span data-stu-id="e4996-117">**False** = device is not compliant with policies.</span></span>|

:::image type="content" source="../../media/basic-mobility-security/bms-7-powershell-parameters.png" alt-text="PowerShell-parameters voor basismobiliteit en beveiliging":::

> [!NOTE]
> <span data-ttu-id="e4996-119">De opdrachten en scripts in dit artikel geven ook informatie weer over apparaten die worden beheerd door [Microsoft Intune.](https://www.microsoft.com/cloud-platform/microsoft-intune)</span><span class="sxs-lookup"><span data-stu-id="e4996-119">The commands and scripts in this article also return details about any devices managed by [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="e4996-120">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="e4996-120">Before you begin</span></span>

<span data-ttu-id="e4996-121">Er zijn een paar dingen die u moet instellen om de opdrachten en scripts uit te voeren die in dit artikel worden beschreven.</span><span class="sxs-lookup"><span data-stu-id="e4996-121">There are a few things you need to set up to run the commands and scripts described in this article.</span></span>

### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="e4996-122">Stap 1: Download en installeer de Azure Active Directory module voor Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e4996-122">Step 1: Download and install the Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="e4996-123">Zie voor meer informatie over deze stappen [Verbinding maken te Microsoft 365 powershell.](/office365/enterprise/powershell/connect-to-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="e4996-123">For more info on these steps, see [Connect to Microsoft 365 with PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell).</span></span>

1. <span data-ttu-id="e4996-124">Ga naar Microsoft Online Services Sign-In Assistent voor [IT-professionals RTWl](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi)en   selecteer Downloaden voor Microsoft Online Services  **Aanmeldingsassistent**.</span><span class="sxs-lookup"><span data-stu-id="e4996-124">Go to [Microsoft Online Services Sign-In Assistant for IT Professionals RTWl](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi) and select  **Download for Microsoft Online Services Sign-in Assistant**.</span></span>

2. <span data-ttu-id="e4996-125">Installeer de module Microsoft Azure Active Directory voor Windows PowerShell met deze stappen:</span><span class="sxs-lookup"><span data-stu-id="e4996-125">Install the Microsoft Azure Active Directory Module for Windows PowerShell with these steps:</span></span>

    1. <span data-ttu-id="e4996-126">Open een PowerShell-opdrachtprompt op beheerdersniveau.</span><span class="sxs-lookup"><span data-stu-id="e4996-126">Open an administrator-level PowerShell command prompt.</span></span>

    2. <span data-ttu-id="e4996-127">Voer de `Install-Module MSOnline` opdracht uit.</span><span class="sxs-lookup"><span data-stu-id="e4996-127">Run the `Install-Module MSOnline` command.</span></span>

    3. <span data-ttu-id="e4996-128">Als u wordt gevraagd om de NuGet provider te installeren, typt u Y en drukt u op ENTER.</span><span class="sxs-lookup"><span data-stu-id="e4996-128">If prompted to install the NuGet provider, type Y and press ENTER.</span></span>

    4. <span data-ttu-id="e4996-129">Als u wordt gevraagd om de module van PSGallery te installeren, typt u Y en drukt u op ENTER.</span><span class="sxs-lookup"><span data-stu-id="e4996-129">If prompted to install the module from PSGallery, type Y and press ENTER.</span></span>

    5. <span data-ttu-id="e4996-130">Sluit na de installatie het powershell-opdrachtvenster.</span><span class="sxs-lookup"><span data-stu-id="e4996-130">After installation, close the PowerShell command window.</span></span>

### <a name="step-2-connect-to-your-microsoft-365-subscription"></a><span data-ttu-id="e4996-131">Stap 2: Verbinding maken uw Microsoft 365 abonnement</span><span class="sxs-lookup"><span data-stu-id="e4996-131">Step 2: Connect to your Microsoft 365 subscription</span></span>

1. <span data-ttu-id="e4996-132">Voer in Windows Azure Active Directory module voor Windows PowerShell de volgende opdracht uit.</span><span class="sxs-lookup"><span data-stu-id="e4996-132">In the Windows Azure Active Directory Module for Windows PowerShell, run the following command.</span></span>

   ```powershell
   $UserCredential = Get-Credential
   ```

2. <span data-ttu-id="e4996-133">Typ in Windows PowerShell dialoogvenster Aanvraag voor referenties de gebruikersnaam en het wachtwoord voor uw Microsoft 365 globale beheerdersaccount en selecteer **OK.**</span><span class="sxs-lookup"><span data-stu-id="e4996-133">In the Windows PowerShell Credential Request dialog box, type the user name and password for your Microsoft 365 global admin account, and then select **OK**.</span></span>

3. <span data-ttu-id="e4996-134">Voer de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="e4996-134">Run the following command.</span></span>

   ```powershell
   Connect-MsolService -Credential $UserCredential
   ```

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a><span data-ttu-id="e4996-135">Stap 3: Zorg ervoor dat u PowerShell-scripts kunt uitvoeren</span><span class="sxs-lookup"><span data-stu-id="e4996-135">Step 3: Make sure you’re able to run PowerShell scripts</span></span>

> [!NOTE]
> <span data-ttu-id="e4996-136">U kunt deze stap overslaan als u al bent ingesteld voor het uitvoeren van PowerShell-scripts.</span><span class="sxs-lookup"><span data-stu-id="e4996-136">You can skip this step if you’re already set up to run PowerShell scripts.</span></span>

<span data-ttu-id="e4996-137">Als u het script Get-MsolUserDeviceComplianceStatus.ps1 uitvoeren, moet u het uitvoeren van PowerShell-scripts inschakelen.</span><span class="sxs-lookup"><span data-stu-id="e4996-137">To run the Get-MsolUserDeviceComplianceStatus.ps1 script, you need to enable the running of PowerShell scripts.</span></span>

1. <span data-ttu-id="e4996-138">Selecteer op Windows bureaublad **Start** en typ Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e4996-138">From your Windows Desktop, select **Start**, and then type Windows PowerShell.</span></span> <span data-ttu-id="e4996-139">Klik met de rechtermuisknop Windows PowerShell en selecteer vervolgens **Uitvoeren als beheerder.**</span><span class="sxs-lookup"><span data-stu-id="e4996-139">Right-click Windows PowerShell, and then select **Run as administrator**.</span></span>

2. <span data-ttu-id="e4996-140">Voer de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="e4996-140">Run the following command.</span></span>

   ```powershell
   Set-ExecutionPolicy  RemoteSigned
   ```

3. <span data-ttu-id="e4996-141">Wanneer u daarom wordt gevraagd, typt u Y en drukt u op Enter.</span><span class="sxs-lookup"><span data-stu-id="e4996-141">When prompted, type Y and then press Enter.</span></span>

#### <a name="run-the-get-msoldevice-cmdlet-to-display-details-for-all-devices-in-your-organization"></a><span data-ttu-id="e4996-142">Voer de Get-MsolDevice cmdlet uit om details weer te geven voor alle apparaten in uw organisatie</span><span class="sxs-lookup"><span data-stu-id="e4996-142">Run the Get-MsolDevice cmdlet to display details for all devices in your organization</span></span>

1. <span data-ttu-id="e4996-143">Open de Microsoft Azure Active Directory module voor Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e4996-143">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>

2. <span data-ttu-id="e4996-144">Voer de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="e4996-144">Run the following command.</span></span>

   ```powershell
   Get-MsolDevice -All -ReturnRegisteredOwners | Where-Object {$_.RegisteredOwners.Count -gt 0}
   ```

<span data-ttu-id="e4996-145">Zie  [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=2157939)voor meer voorbeelden.</span><span class="sxs-lookup"><span data-stu-id="e4996-145">For more examples, see  [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=2157939).</span></span>

## <a name="run-a-script-to-get-device-details"></a><span data-ttu-id="e4996-146">Een script uitvoeren om apparaatdetails op te halen</span><span class="sxs-lookup"><span data-stu-id="e4996-146">Run a script to get device details</span></span>

<span data-ttu-id="e4996-147">Sla eerst het script op uw computer op.</span><span class="sxs-lookup"><span data-stu-id="e4996-147">First, save the script to your computer.</span></span>

1. <span data-ttu-id="e4996-148">Kopieer en plak de volgende tekst in Kladblok.</span><span class="sxs-lookup"><span data-stu-id="e4996-148">Copy and paste the following text into Notepad.</span></span>

   ```powershell
   param (
   [PSObject[]]$users = @(),
   [Switch]$export,
   [String]$exportFileName = "UserDeviceComplianceStatus_" + (Get-Date -Format "yyMMdd_HHMMss") + ".csv",
   [String]$exportPath = [Environment]::GetFolderPath("Desktop")
   )
   [System.Collections.IDictionary]$script:schema = @{
   DeviceId = ''
   DeviceOSType = ''
   DeviceOSVersion = ''
   DeviceTrustLevel = ''
   DisplayName = ''
   IsCompliant = ''
   IsManaged = ''
   ApproximateLastLogonTimestamp = ''
   DeviceObjectId = ''
   RegisteredOwnerUpn = ''
   RegisteredOwnerObjectId = ''
   RegisteredOwnerDisplayName = ''
   }
   function createResultObject
   {
   [PSObject]$resultObject = New-Object -TypeName PSObject -Property $script:schema
   return $resultObject
   }
   If ($users.Count -eq 0)
   {
   $users = Get-MsolUser
   }
   [PSObject[]]$result = foreach ($u in $users)
   {
   [PSObject]$devices = get-msoldevice -RegisteredOwnerUpn $u.UserPrincipalName
   foreach ($d in $devices)
   {
   [PSObject]$deviceResult = createResultObject
   $deviceResult.DeviceId = $d.DeviceId
   $deviceResult.DeviceOSType = $d.DeviceOSType
   $deviceResult.DeviceOSVersion = $d.DeviceOSVersion
   $deviceResult.DeviceTrustLevel = $d.DeviceTrustLevel
   $deviceResult.DisplayName = $d.DisplayName
   $deviceResult.IsCompliant = $d.GraphDeviceObject.IsCompliant
   $deviceResult.IsManaged = $d.GraphDeviceObject.IsManaged
   $deviceResult.DeviceObjectId = $d.ObjectId
   $deviceResult.RegisteredOwnerUpn = $u.UserPrincipalName
   $deviceResult.RegisteredOwnerObjectId = $u.ObjectId
   $deviceResult.RegisteredOwnerDisplayName = $u.DisplayName
   $deviceResult.ApproximateLastLogonTimestamp = $d.ApproximateLastLogonTimestamp
   $deviceResult
   }
   }
   If ($export)
   {
   $result | Export-Csv -path ($exportPath + "\" + $exportFileName) -NoTypeInformation
   }
   Else
   {
   $result
   }
   ```

2. <span data-ttu-id="e4996-149">Sla het op als een Windows PowerShell scriptbestand met behulp van de bestandsextensie .ps1; bijvoorbeeld Get-MsolUserDeviceComplianceStatus.ps1.</span><span class="sxs-lookup"><span data-stu-id="e4996-149">Save it as a Windows PowerShell script file by using the file extension .ps1; for example, Get-MsolUserDeviceComplianceStatus.ps1.</span></span>

## <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a><span data-ttu-id="e4996-150">Voer het script uit om apparaatgegevens voor één gebruikersaccount op te halen</span><span class="sxs-lookup"><span data-stu-id="e4996-150">Run the script to get device information for a single user account</span></span>

1. <span data-ttu-id="e4996-151">Open de Microsoft Azure Active Directory module voor Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e4996-151">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>

2. <span data-ttu-id="e4996-152">Ga naar de map waar u het script hebt opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="e4996-152">Go to the folder where you saved the script.</span></span> <span data-ttu-id="e4996-153">Als u de opdracht bijvoorbeeld hebt opgeslagen in C:\PS-Scripts, voer dan de volgende opdracht uit.</span><span class="sxs-lookup"><span data-stu-id="e4996-153">For example, if you saved it to C:\PS-Scripts, run the following command.</span></span>

   ```powershell
   cd C:\PS-Scripts
   ```

3. <span data-ttu-id="e4996-154">Voer de volgende opdracht uit om de gebruiker te identificeren voor wie u apparaatgegevens wilt krijgen.</span><span class="sxs-lookup"><span data-stu-id="e4996-154">Run the following command to identify the user you want to get device details for.</span></span> <span data-ttu-id="e4996-155">In dit voorbeeld worden details voor bar@example.com.</span><span class="sxs-lookup"><span data-stu-id="e4996-155">This example gets details for bar@example.com.</span></span>

   ```powershell
   $u = Get-MsolUser -UserPrincipalName bar@example.com
   ```

4. <span data-ttu-id="e4996-156">Voer de volgende opdracht uit om het script te starten.</span><span class="sxs-lookup"><span data-stu-id="e4996-156">Run the following command to initiate the script.</span></span>

   ```powershell
   .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export
   ```

<span data-ttu-id="e4996-157">De gegevens worden geëxporteerd naar uw Windows bureaublad als een CSV-bestand.</span><span class="sxs-lookup"><span data-stu-id="e4996-157">The information is exported to your Windows Desktop as a CSV file.</span></span> <span data-ttu-id="e4996-158">U kunt extra parameters gebruiken om de bestandsnaam en het pad van de CSV op te geven.</span><span class="sxs-lookup"><span data-stu-id="e4996-158">You can use additional parameters to specify the file name and path of the CSV.</span></span>

## <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a><span data-ttu-id="e4996-159">Voer het script uit om apparaatgegevens voor een groep gebruikers op te halen</span><span class="sxs-lookup"><span data-stu-id="e4996-159">Run the script to get device information for a group of users</span></span>

1. <span data-ttu-id="e4996-160">Open de Microsoft Azure Active Directory module voor Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e4996-160">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>

2. <span data-ttu-id="e4996-161">Ga naar de map waar u het script hebt opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="e4996-161">Go to the folder where you saved the script.</span></span> <span data-ttu-id="e4996-162">Als u de opdracht bijvoorbeeld hebt opgeslagen in C:\PS-Scripts, voer dan de volgende opdracht uit.</span><span class="sxs-lookup"><span data-stu-id="e4996-162">For example, if you saved it to C:\PS-Scripts, run the following command.</span></span>

   ```powershell
   cd C:\PS-Scripts
   ```

3. <span data-ttu-id="e4996-163">Voer de volgende opdracht uit om de groep te identificeren voor wie u apparaatgegevens wilt krijgen.</span><span class="sxs-lookup"><span data-stu-id="e4996-163">Run the following command to identify the group you want to get device details for.</span></span> <span data-ttu-id="e4996-164">In dit voorbeeld worden details voor gebruikers in de groep FinanceStaff op de voor u staan.</span><span class="sxs-lookup"><span data-stu-id="e4996-164">This example gets details for users in the FinanceStaff group.</span></span>

   ```powershell
   $u = Get-MsolGroupMember -SearchString "FinanceStaff" | % { Get-MsolUser -ObjectId $_.ObjectId }
   ```

4. <span data-ttu-id="e4996-165">Voer de volgende opdracht uit om het script te starten.</span><span class="sxs-lookup"><span data-stu-id="e4996-165">Run the following command to initiate the script.</span></span>

   ```powershell
   .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export
   ```

<span data-ttu-id="e4996-166">De gegevens worden geëxporteerd naar uw Windows bureaublad als een CSV-bestand.</span><span class="sxs-lookup"><span data-stu-id="e4996-166">The information is exported to your Windows Desktop as a CSV file.</span></span> <span data-ttu-id="e4996-167">U kunt extra parameters gebruiken om de bestandsnaam en het pad van de CSV op te geven.</span><span class="sxs-lookup"><span data-stu-id="e4996-167">You can use additional parameters to specify the file name and path of the CSV.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e4996-168">Gerelateerde onderwerpen</span><span class="sxs-lookup"><span data-stu-id="e4996-168">Related topics</span></span>

[<span data-ttu-id="e4996-169">Microsoft Verbinding maken is met pensioen</span><span class="sxs-lookup"><span data-stu-id="e4996-169">Microsoft Connect Has Been Retired</span></span>](/collaborate/connect-redirect)

[<span data-ttu-id="e4996-170">Overzicht van de Basic Mobility en Security</span><span class="sxs-lookup"><span data-stu-id="e4996-170">Overview of Basic Mobility and Security</span></span>](overview.md)

[<span data-ttu-id="e4996-171">Get-MsolDevice</span><span class="sxs-lookup"><span data-stu-id="e4996-171">Get-MsolDevice</span></span>](https://go.microsoft.com/fwlink/?linkid=2157939)
