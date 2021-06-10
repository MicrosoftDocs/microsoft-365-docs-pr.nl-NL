---
title: Onboarden niet-permanente virtual desktop infrastructure (VDI)-apparaten
description: Implementeer het configuratiepakket op VDI-apparaat (Virtual Desktop Infrastructure), zodat ze zijn onboarded bij de Microsoft Defender for Endpoint-service.
keywords: virtual desktop infrastructure (VDI) device, vdi, device management, configure Microsoft Defender for Endpoint, endpoints configureren
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 04/16/2020
ms.technology: mde
ms.openlocfilehash: d09967a18848365702f52f65a7f0624d2b2ae3d6
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843208"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a><span data-ttu-id="6803b-104">Onboarden niet-permanente virtual desktop infrastructure (VDI)-apparaten</span><span class="sxs-lookup"><span data-stu-id="6803b-104">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6803b-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="6803b-105">**Applies to:**</span></span>
- [<span data-ttu-id="6803b-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="6803b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6803b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6803b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
- <span data-ttu-id="6803b-108">VDI-apparaten (Virtual Desktop Infrastructure)</span><span class="sxs-lookup"><span data-stu-id="6803b-108">Virtual desktop infrastructure (VDI) devices</span></span>
- <span data-ttu-id="6803b-109">Windows 10, Windows Server 2019, Windows Server 2008R2/2012R2/2016</span><span class="sxs-lookup"><span data-stu-id="6803b-109">Windows 10, Windows Server 2019, Windows Server 2008R2/2012R2/2016</span></span>

><span data-ttu-id="6803b-110">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="6803b-110">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="6803b-111">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="6803b-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configvdi-abovefoldlink)

## <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a><span data-ttu-id="6803b-112">Onboarden niet-permanente virtual desktop infrastructure (VDI)-apparaten</span><span class="sxs-lookup"><span data-stu-id="6803b-112">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>

<span data-ttu-id="6803b-113">Defender for Endpoint ondersteunt niet-permanente VDI-sessie onboarding.</span><span class="sxs-lookup"><span data-stu-id="6803b-113">Defender for Endpoint supports non-persistent VDI session onboarding.</span></span> 


<span data-ttu-id="6803b-114">Er kunnen gekoppelde uitdagingen zijn bij het onboarden van VDIs.</span><span class="sxs-lookup"><span data-stu-id="6803b-114">There might be associated challenges when onboarding VDIs.</span></span> <span data-ttu-id="6803b-115">Hier volgen de volgende typische uitdagingen voor dit scenario:</span><span class="sxs-lookup"><span data-stu-id="6803b-115">The following are typical challenges for this scenario:</span></span>

- <span data-ttu-id="6803b-116">Direct vroeg onboarding van een sessies van korte duur, die vóór de feitelijke inrichting moeten worden onboarded bij Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="6803b-116">Instant early onboarding of a short-lived sessions, which must be onboarded to Defender for Endpoint prior to the actual provisioning.</span></span>
- <span data-ttu-id="6803b-117">De naam van het apparaat wordt meestal opnieuw gebruikt voor nieuwe sessies.</span><span class="sxs-lookup"><span data-stu-id="6803b-117">The device name is typically reused for new sessions.</span></span>

<span data-ttu-id="6803b-118">VDI-apparaten kunnen als een van de volgende apparaten worden weergegeven in de Portal van Defender voor Eindpunt:</span><span class="sxs-lookup"><span data-stu-id="6803b-118">VDI devices can appear in Defender for Endpoint portal as either:</span></span>

- <span data-ttu-id="6803b-119">Eén invoer voor elk apparaat.</span><span class="sxs-lookup"><span data-stu-id="6803b-119">Single entry for each device.</span></span>

  > [!NOTE]
  > <span data-ttu-id="6803b-120">In dit geval moet *dezelfde* apparaatnaam worden geconfigureerd wanneer de sessie wordt gemaakt, bijvoorbeeld met een onbeheerd antwoordbestand.</span><span class="sxs-lookup"><span data-stu-id="6803b-120">In this case, the *same* device name must be configured when the session is created, for example using an unattended answer file.</span></span>

- <span data-ttu-id="6803b-121">Meerdere items voor elk apparaat: één voor elke sessie.</span><span class="sxs-lookup"><span data-stu-id="6803b-121">Multiple entries for each device - one for each session.</span></span>

<span data-ttu-id="6803b-122">De volgende stappen helpen u bij het onboarden van VDI-apparaten en markeren stappen voor enkele en meerdere items.</span><span class="sxs-lookup"><span data-stu-id="6803b-122">The following steps will guide you through onboarding VDI devices and will highlight steps for single and multiple entries.</span></span>

>[!WARNING]
> <span data-ttu-id="6803b-123">Voor omgevingen met lage resourceconfiguraties kan de VDI-opstartprocedure de onboarding van de Defender voor Eindpunt-sensor vertragen.</span><span class="sxs-lookup"><span data-stu-id="6803b-123">For environments where there are low resource configurations, the VDI boot procedure might slow the Defender for Endpoint sensor onboarding.</span></span> 


### <a name="for-windows-10-or-windows-server-2019"></a><span data-ttu-id="6803b-124">Voor Windows 10 of Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="6803b-124">For Windows 10 or Windows Server 2019</span></span>

1.  <span data-ttu-id="6803b-125">Open het VDI-configuratiepakket .zip bestand *(WindowsDefenderATPOnboardingPackage.zip)* dat u hebt gedownload van de wizard Service onboarding.</span><span class="sxs-lookup"><span data-stu-id="6803b-125">Open the VDI configuration package .zip file (*WindowsDefenderATPOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="6803b-126">U kunt het pakket ook van [Microsoft Defender-beveiligingscentrum:](https://securitycenter.windows.com/)</span><span class="sxs-lookup"><span data-stu-id="6803b-126">You can also get the package from [Microsoft Defender Security Center](https://securitycenter.windows.com/):</span></span>

    1.  <span data-ttu-id="6803b-127">Selecteer in het navigatiedeelvenster **Instellingen**  >  **Onboarding.**</span><span class="sxs-lookup"><span data-stu-id="6803b-127">In the navigation pane, select **Settings** > **Onboarding**.</span></span>

    1. <span data-ttu-id="6803b-128">Selecteer Windows 10 als het besturingssysteem.</span><span class="sxs-lookup"><span data-stu-id="6803b-128">Select Windows 10 as the operating system.</span></span>

    1.  <span data-ttu-id="6803b-129">Selecteer in **het veld** Implementatiemethode **VDI-onboarding-scripts voor niet-permanente eindpunten.**</span><span class="sxs-lookup"><span data-stu-id="6803b-129">In the **Deployment method** field, select **VDI onboarding scripts for non-persistent endpoints**.</span></span>

    1. <span data-ttu-id="6803b-130">Klik **op Pakket downloaden** en sla het .zip op.</span><span class="sxs-lookup"><span data-stu-id="6803b-130">Click **Download package** and save the .zip file.</span></span>

2. <span data-ttu-id="6803b-131">Kopieer de bestanden uit de map WindowsDefenderATPOnboardingPackage uit het .zip bestand naar de `golden/master` afbeelding onder het `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` pad.</span><span class="sxs-lookup"><span data-stu-id="6803b-131">Copy the files from the WindowsDefenderATPOnboardingPackage folder extracted from the .zip file into the `golden/master` image under the path `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup`.</span></span> 

    1. <span data-ttu-id="6803b-132">Als u geen enkele vermelding voor elk apparaat implementeert, kopieert u WindowsDefenderATPOnboardingScript.cmd.</span><span class="sxs-lookup"><span data-stu-id="6803b-132">If you are not implementing a single entry for each device, copy WindowsDefenderATPOnboardingScript.cmd.</span></span>

    1. <span data-ttu-id="6803b-133">Als u één invoer implementeert voor elk apparaat, kopieert u zowel Onboard-NonPersistentMachine.ps1 als WindowsDefenderATPOnboardingScript.cmd.</span><span class="sxs-lookup"><span data-stu-id="6803b-133">If you are implementing a single entry for each device, copy both Onboard-NonPersistentMachine.ps1 and WindowsDefenderATPOnboardingScript.cmd.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6803b-134">Als u de map niet `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` ziet, is deze mogelijk verborgen.</span><span class="sxs-lookup"><span data-stu-id="6803b-134">If you don't see the `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` folder, it might be hidden.</span></span> <span data-ttu-id="6803b-135">U moet de optie  Verborgen bestanden en mappen weergeven kiezen in Verkenner.</span><span class="sxs-lookup"><span data-stu-id="6803b-135">You'll need to choose the **Show hidden files and folders** option from File Explorer.</span></span>

3. <span data-ttu-id="6803b-136">Open een venster Van lokale groepsbeleidseditor en navigeer naar **Computerconfiguratie**  >  **Windows Instellingen**  >  **scripts**  >  **opstarten.**</span><span class="sxs-lookup"><span data-stu-id="6803b-136">Open a Local Group Policy Editor window and navigate to **Computer Configuration** > **Windows Settings** > **Scripts** > **Startup**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="6803b-137">Domeingroepsbeleid kan ook worden gebruikt voor onboarding van niet-permanente VDI-apparaten.</span><span class="sxs-lookup"><span data-stu-id="6803b-137">Domain Group Policy may also be used for onboarding non-persistent VDI devices.</span></span>

4. <span data-ttu-id="6803b-138">Volg de juiste stappen, afhankelijk van de methode die u wilt implementeren:</span><span class="sxs-lookup"><span data-stu-id="6803b-138">Depending on the method you'd like to implement, follow the appropriate steps:</span></span>

   - <span data-ttu-id="6803b-139">Voor één invoer voor elk apparaat:</span><span class="sxs-lookup"><span data-stu-id="6803b-139">For single entry for each device:</span></span>
   
     <span data-ttu-id="6803b-140">Selecteer het **tabblad PowerShell-scripts** en klik vervolgens op Toevoegen **(Windows** Explorer wordt rechtstreeks geopend in het pad waar u het onboarding-script eerder hebt gekopieerd).</span><span class="sxs-lookup"><span data-stu-id="6803b-140">Select the **PowerShell Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="6803b-141">Navigeer naar onboarding PowerShell-script `Onboard-NonPersistentMachine.ps1` .</span><span class="sxs-lookup"><span data-stu-id="6803b-141">Navigate to onboarding PowerShell script `Onboard-NonPersistentMachine.ps1`.</span></span> <span data-ttu-id="6803b-142">U hoeft het andere bestand niet op te geven, omdat het automatisch wordt geactiveerd.</span><span class="sxs-lookup"><span data-stu-id="6803b-142">There is no need to specify the other file, as it will be triggered automatically.</span></span>
   
   - <span data-ttu-id="6803b-143">Voor meerdere vermeldingen voor elk apparaat:</span><span class="sxs-lookup"><span data-stu-id="6803b-143">For multiple entries for each device:</span></span>
   
     <span data-ttu-id="6803b-144">Selecteer het **tabblad Scripts** en klik vervolgens op **Toevoegen** (Windows Explorer wordt rechtstreeks geopend in het pad waar u het onboarding-script eerder hebt gekopieerd).</span><span class="sxs-lookup"><span data-stu-id="6803b-144">Select the **Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="6803b-145">Ga naar het onboarding `WindowsDefenderATPOnboardingScript.cmd` bash-script.</span><span class="sxs-lookup"><span data-stu-id="6803b-145">Navigate to the onboarding bash script `WindowsDefenderATPOnboardingScript.cmd`.</span></span>

5. <span data-ttu-id="6803b-146">Test uw oplossing:</span><span class="sxs-lookup"><span data-stu-id="6803b-146">Test your solution:</span></span>

   1. <span data-ttu-id="6803b-147">Maak een groep met één apparaat.</span><span class="sxs-lookup"><span data-stu-id="6803b-147">Create a pool with one device.</span></span>
      
   1. <span data-ttu-id="6803b-148">Aanmelding bij apparaat.</span><span class="sxs-lookup"><span data-stu-id="6803b-148">Logon to device.</span></span>
      
   1. <span data-ttu-id="6803b-149">Logoff van apparaat.</span><span class="sxs-lookup"><span data-stu-id="6803b-149">Logoff from device.</span></span>

   1. <span data-ttu-id="6803b-150">Aanmelding bij apparaat met een andere gebruiker.</span><span class="sxs-lookup"><span data-stu-id="6803b-150">Logon to device with another user.</span></span>
      
   1. <span data-ttu-id="6803b-151">Volg de juiste stappen, afhankelijk van de methode die u wilt implementeren:</span><span class="sxs-lookup"><span data-stu-id="6803b-151">Depending on the method you'd like to implement, follow the appropriate steps:</span></span>
   
      - <span data-ttu-id="6803b-152">Voor één invoer voor elk apparaat:</span><span class="sxs-lookup"><span data-stu-id="6803b-152">For single entry for each device:</span></span> 
    
        <span data-ttu-id="6803b-153">Controleer slechts één item in Microsoft Defender-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="6803b-153">Check only one entry in Microsoft Defender Security Center.</span></span>

      - <span data-ttu-id="6803b-154">Voor meerdere vermeldingen voor elk apparaat:</span><span class="sxs-lookup"><span data-stu-id="6803b-154">For multiple entries for each device:</span></span> 
       
        <span data-ttu-id="6803b-155">Controleer meerdere vermeldingen in Microsoft Defender-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="6803b-155">Check multiple entries in Microsoft Defender Security Center.</span></span>

6. <span data-ttu-id="6803b-156">Klik **op De lijst Apparaten** in het navigatiedeelvenster.</span><span class="sxs-lookup"><span data-stu-id="6803b-156">Click **Devices list** on the Navigation pane.</span></span>

7. <span data-ttu-id="6803b-157">Gebruik de zoekfunctie door de naam van het apparaat in te geven en **Apparaat te selecteren** als zoektype.</span><span class="sxs-lookup"><span data-stu-id="6803b-157">Use the search function by entering the device name and select **Device** as search type.</span></span>


## <a name="for-downlevel-skus"></a><span data-ttu-id="6803b-158">Voor downlevel-SKU's</span><span class="sxs-lookup"><span data-stu-id="6803b-158">For downlevel SKUs</span></span>

> [!NOTE]
> <span data-ttu-id="6803b-159">Het volgende register is alleen relevant als het doel is om een 'Enkelvoudige vermelding voor elk apparaat' te bereiken.</span><span class="sxs-lookup"><span data-stu-id="6803b-159">The following registry is relevant only when the aim is to achieve a 'Single entry for each device'.</span></span>

1. <span data-ttu-id="6803b-160">Registerwaarde instellen op:</span><span class="sxs-lookup"><span data-stu-id="6803b-160">Set registry value to:</span></span>

    ```console
   [HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging]
    "VDI"="NonPersistent"
    ```

    <span data-ttu-id="6803b-161">of met opdrachtregel:</span><span class="sxs-lookup"><span data-stu-id="6803b-161">or using command line:</span></span>

    ```console
    reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging" /v VDI /t REG_SZ /d "NonPersistent" /f
    ```

2. <span data-ttu-id="6803b-162">Volg het [onboardingproces van de server.](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016)</span><span class="sxs-lookup"><span data-stu-id="6803b-162">Follow the [server onboarding process](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016).</span></span> 



## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a><span data-ttu-id="6803b-163">Niet-permanente VDI-afbeeldingen (Virtual Desktop Infrastructure) bijwerken</span><span class="sxs-lookup"><span data-stu-id="6803b-163">Updating non-persistent virtual desktop infrastructure (VDI) images</span></span>
<span data-ttu-id="6803b-164">Het is raadzaam om offline servicehulpmiddelen te gebruiken om gouden/hoofdafbeeldingen te patchen.</span><span class="sxs-lookup"><span data-stu-id="6803b-164">As a best practice, we recommend using offline servicing tools to patch golden/master images.</span></span><br>
<span data-ttu-id="6803b-165">U kunt bijvoorbeeld de onderstaande opdrachten gebruiken om een update te installeren terwijl de afbeelding offline blijft:</span><span class="sxs-lookup"><span data-stu-id="6803b-165">For example, you can use the below commands to install an update while the image remains offline:</span></span>

```console
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing" 
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

<span data-ttu-id="6803b-166">Zie de artikelen hieronder voor meer informatie over DISM-opdrachten en offlineonderhoud:</span><span class="sxs-lookup"><span data-stu-id="6803b-166">For more information on DISM commands and offline servicing, please refer to the articles below:</span></span>
- [<span data-ttu-id="6803b-167">Een afbeelding Windows DISM wijzigen</span><span class="sxs-lookup"><span data-stu-id="6803b-167">Modify a Windows image using DISM</span></span>](/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [<span data-ttu-id="6803b-168">DISM Image Management Command-Line Opties</span><span class="sxs-lookup"><span data-stu-id="6803b-168">DISM Image Management Command-Line Options</span></span>](/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [<span data-ttu-id="6803b-169">De grootte van het onderdelenbestand in een offline-Windows verkleinen</span><span class="sxs-lookup"><span data-stu-id="6803b-169">Reduce the Size of the Component Store in an Offline Windows Image</span></span>](/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

<span data-ttu-id="6803b-170">Als offline service geen haalbare optie is voor uw niet-permanente VDI-omgeving, moeten de volgende stappen worden genomen om consistentie en sensortoestand te waarborgen:</span><span class="sxs-lookup"><span data-stu-id="6803b-170">If offline servicing is not a viable option for your non-persistent VDI environment, the following steps should be taken to ensure consistency and sensor health:</span></span>

1. <span data-ttu-id="6803b-171">Nadat u de hoofdafbeelding voor online onderhoud of patching heeft opgestart, kunt u een offboarding-script uitvoeren om de Defender voor Eindpunt-sensor uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="6803b-171">After booting the master image for online servicing or patching, run an offboarding script to turn off the Defender for Endpoint sensor.</span></span> <span data-ttu-id="6803b-172">Zie Offboard-apparaten met [een lokaal script voor meer informatie.](configure-endpoints-script.md#offboard-devices-using-a-local-script)</span><span class="sxs-lookup"><span data-stu-id="6803b-172">For more information, see [Offboard devices using a local script](configure-endpoints-script.md#offboard-devices-using-a-local-script).</span></span>

2. <span data-ttu-id="6803b-173">Zorg ervoor dat de sensor wordt gestopt door de onderstaande opdracht uit te voeren in een CMD-venster:</span><span class="sxs-lookup"><span data-stu-id="6803b-173">Ensure the sensor is stopped by running the command below in a CMD window:</span></span>

   ```console
   sc query sense
   ```

3. <span data-ttu-id="6803b-174">Service de afbeelding zo nodig.</span><span class="sxs-lookup"><span data-stu-id="6803b-174">Service the image as needed.</span></span>

4. <span data-ttu-id="6803b-175">Voer de onderstaande opdrachten uit PsExec.exe (waaruit kan worden gedownload om de inhoud van de cybermap op te schonen die de sensor mogelijk heeft verzameld sinds het https://download.sysinternals.com/files/PSTools.zip) opstarten:</span><span class="sxs-lookup"><span data-stu-id="6803b-175">Run the below commands using PsExec.exe (which can be downloaded from https://download.sysinternals.com/files/PSTools.zip) to cleanup the cyber folder contents that the sensor may have accumulated since boot:</span></span>

    ```console
    PsExec.exe -s cmd.exe
    cd "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Cyber"
    del *.* /f /s /q
    REG DELETE “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
    exit
    ```

5. <span data-ttu-id="6803b-176">Verzegel de afbeelding van het gouden/hoofdmodel opnieuw zoals u dat normaal zou doen.</span><span class="sxs-lookup"><span data-stu-id="6803b-176">Re-seal the golden/master image as you normally would.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6803b-177">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="6803b-177">Related topics</span></span>
- [<span data-ttu-id="6803b-178">Onboard Windows 10 apparaten met groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="6803b-178">Onboard Windows 10 devices using Group Policy</span></span>](configure-endpoints-gp.md)
- [<span data-ttu-id="6803b-179">Onboard Windows 10 apparaten met Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="6803b-179">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md)
- [<span data-ttu-id="6803b-180">Onboarden Windows 10-apparaten met hulpmiddelen voor Mobile Device Management</span><span class="sxs-lookup"><span data-stu-id="6803b-180">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md)
- [<span data-ttu-id="6803b-181">Onboarden Windows 10-apparaten met een lokaal script</span><span class="sxs-lookup"><span data-stu-id="6803b-181">Onboard Windows 10 devices using a local script</span></span>](configure-endpoints-script.md)
- [<span data-ttu-id="6803b-182">Problemen met de onboarding van Microsoft Defender voor eindpunten oplossen</span><span class="sxs-lookup"><span data-stu-id="6803b-182">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
