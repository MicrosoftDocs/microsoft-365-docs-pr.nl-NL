---
title: Onboarden niet-permanente virtual desktop infrastructure (VDI)-apparaten
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Implementeer het configuratiepakket op VDI-apparaat (Virtual Desktop Infrastructure) zodat ze zijn onboarded bij de Microsoft 365 Endpoint Data Loss Prevention Service.
ms.openlocfilehash: 64d9bfed3d1d5600b5843c697e894577f83527fe
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226873"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a><span data-ttu-id="c7c20-103">Onboarden niet-permanente virtual desktop infrastructure (VDI)-apparaten</span><span class="sxs-lookup"><span data-stu-id="c7c20-103">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>

<span data-ttu-id="c7c20-104">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="c7c20-104">**Applies to:**</span></span>
- [<span data-ttu-id="c7c20-105">Microsoft 365 Preventie van gegevensverlies in eindpunten (DLP)</span><span class="sxs-lookup"><span data-stu-id="c7c20-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](./endpoint-dlp-learn-about.md)

- <span data-ttu-id="c7c20-106">VDI-apparaten (Virtual Desktop Infrastructure)</span><span class="sxs-lookup"><span data-stu-id="c7c20-106">Virtual desktop infrastructure (VDI) devices</span></span>

> [!WARNING]
> <span data-ttu-id="c7c20-107">Microsoft 365 Ondersteuning voor preventie van eindpunten voor gegevensverlies Windows virtuele bureaublad ondersteunt scenario's voor één sessie.</span><span class="sxs-lookup"><span data-stu-id="c7c20-107">Microsoft 365 Endpoint data loss prevention support for Windows Virtual Desktop supports single session scenarios.</span></span> <span data-ttu-id="c7c20-108">Scenario's met meerdere sessies op Windows virtuele bureaublad worden momenteel niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="c7c20-108">Multi-session scenarios on Windows Virtual Desktop are currently not supported.</span></span>

## <a name="onboard-vdi-devices"></a><span data-ttu-id="c7c20-109">Onboard VDI-apparaten</span><span class="sxs-lookup"><span data-stu-id="c7c20-109">Onboard VDI devices</span></span>

<span data-ttu-id="c7c20-110">Microsoft 365 Preventie van verlies van eindpunten ondersteunt niet-permanente VDI-sessie onboarding.</span><span class="sxs-lookup"><span data-stu-id="c7c20-110">Microsoft 365 Endpoint data loss prevention supports non-persistent VDI session onboarding.</span></span>

> [!NOTE]
> <span data-ttu-id="c7c20-111">Als u niet-permanente VDI-sessies wilt onboarden, moeten VDI-apparaten zijn Windows 10 1809 of hoger.</span><span class="sxs-lookup"><span data-stu-id="c7c20-111">To onboard non-persistent VDI sessions, VDI devices must be on Windows 10 1809 or higher.</span></span>

<span data-ttu-id="c7c20-112">Er kunnen gekoppelde uitdagingen zijn bij het onboarden van VDIs.</span><span class="sxs-lookup"><span data-stu-id="c7c20-112">There might be associated challenges when onboarding VDIs.</span></span> <span data-ttu-id="c7c20-113">Hier volgen de volgende typische uitdagingen voor dit scenario:</span><span class="sxs-lookup"><span data-stu-id="c7c20-113">The following are typical challenges for this scenario:</span></span>

- <span data-ttu-id="c7c20-114">Direct vroeg onboarding van een sessies van korte duur, die moeten worden onboarded om Microsoft 365 endpoint-preventie van gegevensverlies te voorkomen vóór de feitelijke inrichting.</span><span class="sxs-lookup"><span data-stu-id="c7c20-114">Instant early onboarding of a short-lived sessions, which must be onboarded to  Microsoft 365 Endpoint data loss prevention prior to the actual provisioning.</span></span>
- <span data-ttu-id="c7c20-115">De naam van het apparaat wordt meestal opnieuw gebruikt voor nieuwe sessies.</span><span class="sxs-lookup"><span data-stu-id="c7c20-115">The device name is typically reused for new sessions.</span></span>

<span data-ttu-id="c7c20-116">VDI-apparaten kunnen als Microsoft 365 worden weergegeven in het compliancecentrum:</span><span class="sxs-lookup"><span data-stu-id="c7c20-116">VDI devices can appear in the Microsoft 365 Compliance center as either:</span></span>

- <span data-ttu-id="c7c20-117">Eén invoer voor elk apparaat.</span><span class="sxs-lookup"><span data-stu-id="c7c20-117">Single entry for each device.</span></span>
<span data-ttu-id="c7c20-118">Houd er rekening mee dat in dit geval dezelfde *apparaatnaam* moet worden geconfigureerd wanneer de sessie wordt gemaakt, bijvoorbeeld met een onbeheerd antwoordbestand.</span><span class="sxs-lookup"><span data-stu-id="c7c20-118">Note that in this case, the *same* device name must be configured when the session is created, for example using an unattended answer file.</span></span>
- <span data-ttu-id="c7c20-119">Meerdere items voor elk apparaat: één voor elke sessie.</span><span class="sxs-lookup"><span data-stu-id="c7c20-119">Multiple entries for each device - one for each session.</span></span>

<span data-ttu-id="c7c20-120">De volgende stappen helpen u bij het onboarden van VDI-apparaten en markeren stappen voor enkele en meerdere items.</span><span class="sxs-lookup"><span data-stu-id="c7c20-120">The following steps will guide you through onboarding VDI devices and will highlight steps for single and multiple entries.</span></span>

> [!WARNING]
> <span data-ttu-id="c7c20-121">Voor omgevingen met lage resourceconfiguraties kan de VDI-opstartprocedure de onboarding van Microsoft 365 endpoint-gegevensverlies vertragen.</span><span class="sxs-lookup"><span data-stu-id="c7c20-121">For environments where there are low resource configurations, the VDI boot procedure might slow the Microsoft 365 Endpoint data loss prevention onboarding.</span></span>

1. <span data-ttu-id="c7c20-122">Open het VDI-configuratiepakket .zip bestand *(DeviceCompliancePackage.zip)* dat u hebt gedownload van de wizard Service onboarding.</span><span class="sxs-lookup"><span data-stu-id="c7c20-122">Open the VDI configuration package .zip file (*DeviceCompliancePackage.zip*) that you downloaded from the service onboarding wizard.</span></span>

2. <span data-ttu-id="c7c20-123">Selecteer in het navigatiedeelvenster **Instellingen**  >  **Onboarding van**  >  **apparaat.**</span><span class="sxs-lookup"><span data-stu-id="c7c20-123">In the navigation pane, select **Settings** > **Device onboarding** > **Onboarding**.</span></span>

3. <span data-ttu-id="c7c20-124">Selecteer in **het veld** Implementatiemethode **VDI-onboarding-scripts voor niet-permanente eindpunten.**</span><span class="sxs-lookup"><span data-stu-id="c7c20-124">In the **Deployment method** field, select **VDI onboarding scripts for non-persistent endpoints**.</span></span>

4. <span data-ttu-id="c7c20-125">Klik **op Pakket downloaden** en sla het .zip op.</span><span class="sxs-lookup"><span data-stu-id="c7c20-125">Click **Download package** and save the .zip file.</span></span>

5. <span data-ttu-id="c7c20-126">Kopieer de bestanden uit de map DeviceCompliancePackage die is geëxtraheerd uit het .zip naar de `golden/master` afbeelding onder het `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` pad.</span><span class="sxs-lookup"><span data-stu-id="c7c20-126">Copy the files from the DeviceCompliancePackage folder extracted from the .zip file into the `golden/master` image under the path `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup`.</span></span>

6. <span data-ttu-id="c7c20-127">Als u geen enkele vermelding voor elk apparaat implementeert, kopieert u DeviceComplianceOnboardingScript.cmd.</span><span class="sxs-lookup"><span data-stu-id="c7c20-127">If you are not implementing a single entry for each device, copy DeviceComplianceOnboardingScript.cmd.</span></span>

7. <span data-ttu-id="c7c20-128">Als u één invoer implementeert voor elk apparaat, kopieert u zowel Onboard-NonPersistentMachine.ps1 als DeviceComplianceOnboardingScript.cmd.</span><span class="sxs-lookup"><span data-stu-id="c7c20-128">If you are implementing a single entry for each device, copy both Onboard-NonPersistentMachine.ps1 and DeviceComplianceOnboardingScript.cmd.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c7c20-129">Als u de map niet `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` ziet, is deze mogelijk verborgen.</span><span class="sxs-lookup"><span data-stu-id="c7c20-129">If you don't see the `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` folder, it might be hidden.</span></span> <span data-ttu-id="c7c20-130">U moet de optie  Verborgen bestanden en mappen weergeven kiezen in Verkenner.</span><span class="sxs-lookup"><span data-stu-id="c7c20-130">You'll need to choose the **Show hidden files and folders** option from File Explorer.</span></span>

8. <span data-ttu-id="c7c20-131">Open een venster Van lokale groepsbeleidseditor en navigeer naar **Computerconfiguratie**  >  **Windows Instellingen**  >  **scripts**  >  **opstarten.**</span><span class="sxs-lookup"><span data-stu-id="c7c20-131">Open a Local Group Policy Editor window and navigate to **Computer Configuration** > **Windows Settings** > **Scripts** > **Startup**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="c7c20-132">Domeingroepsbeleid kan ook worden gebruikt voor onboarding van niet-permanente VDI-apparaten.</span><span class="sxs-lookup"><span data-stu-id="c7c20-132">Domain Group Policy may also be used for onboarding non-persistent VDI devices.</span></span>

9. <span data-ttu-id="c7c20-133">Volg de juiste stappen, afhankelijk van de methode die u wilt implementeren:</span><span class="sxs-lookup"><span data-stu-id="c7c20-133">Depending on the method you'd like to implement, follow the appropriate steps:</span></span>

   <span data-ttu-id="c7c20-134">**Voor één invoer voor elk apparaat**</span><span class="sxs-lookup"><span data-stu-id="c7c20-134">**For single entry for each device**</span></span>

   <span data-ttu-id="c7c20-135">Selecteer het **tabblad PowerShell-scripts** en klik vervolgens op Toevoegen **(Windows** Explorer wordt rechtstreeks geopend in het pad waar u het onboarding-script eerder hebt gekopieerd).</span><span class="sxs-lookup"><span data-stu-id="c7c20-135">Select the **PowerShell Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="c7c20-136">Navigeer naar onboarding PowerShell-script `Onboard-NonPersistentMachine.ps1` .</span><span class="sxs-lookup"><span data-stu-id="c7c20-136">Navigate to onboarding PowerShell script `Onboard-NonPersistentMachine.ps1`.</span></span>

   <span data-ttu-id="c7c20-137">**Voor meerdere vermeldingen voor elk apparaat:**</span><span class="sxs-lookup"><span data-stu-id="c7c20-137">**For multiple entries for each device**:</span></span>

   <span data-ttu-id="c7c20-138">Selecteer het **tabblad Scripts** en klik vervolgens op **Toevoegen** (Windows Explorer wordt rechtstreeks geopend in het pad waar u het onboarding-script eerder hebt gekopieerd).</span><span class="sxs-lookup"><span data-stu-id="c7c20-138">Select the **Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="c7c20-139">Ga naar het onboarding `DeviceComplianceOnboardingScript.cmd` bash-script.</span><span class="sxs-lookup"><span data-stu-id="c7c20-139">Navigate to the onboarding bash script `DeviceComplianceOnboardingScript.cmd`.</span></span>

10. <span data-ttu-id="c7c20-140">Test uw oplossing:</span><span class="sxs-lookup"><span data-stu-id="c7c20-140">Test your solution:</span></span>
    1. <span data-ttu-id="c7c20-141">Maak een groep met één apparaat.</span><span class="sxs-lookup"><span data-stu-id="c7c20-141">Create a pool with one device.</span></span>
    1. <span data-ttu-id="c7c20-142">Aanmelding bij apparaat.</span><span class="sxs-lookup"><span data-stu-id="c7c20-142">Logon to device.</span></span>
    1. <span data-ttu-id="c7c20-143">Logoff van apparaat.</span><span class="sxs-lookup"><span data-stu-id="c7c20-143">Logoff from device.</span></span>
    1. <span data-ttu-id="c7c20-144">Aanmelding bij apparaat met een andere gebruiker.</span><span class="sxs-lookup"><span data-stu-id="c7c20-144">Logon to device with another user.</span></span>
    1. <span data-ttu-id="c7c20-145">**Voor één invoer voor elk apparaat:** Controleer slechts één item in Microsoft Defender-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="c7c20-145">**For single entry for each device**: Check only one entry in Microsoft Defender Security Center.</span></span>
       <span data-ttu-id="c7c20-146">**Voor meerdere items voor elk apparaat:** Controleer meerdere vermeldingen in Microsoft Defender-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="c7c20-146">**For multiple entries for each device**: Check multiple entries in Microsoft Defender Security Center.</span></span>

11. <span data-ttu-id="c7c20-147">Klik **op De lijst Apparaten** in het navigatiedeelvenster.</span><span class="sxs-lookup"><span data-stu-id="c7c20-147">Click **Devices list** on the Navigation pane.</span></span>

12. <span data-ttu-id="c7c20-148">Gebruik de zoekfunctie door de naam van het apparaat in te geven en **Apparaat te selecteren** als zoektype.</span><span class="sxs-lookup"><span data-stu-id="c7c20-148">Use the search function by entering the device name and select **Device** as search type.</span></span>

## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a><span data-ttu-id="c7c20-149">Niet-permanente VDI-afbeeldingen (Virtual Desktop Infrastructure) bijwerken</span><span class="sxs-lookup"><span data-stu-id="c7c20-149">Updating non-persistent virtual desktop infrastructure (VDI) images</span></span>

<span data-ttu-id="c7c20-150">Het is raadzaam om offline servicehulpmiddelen te gebruiken om gouden/hoofdafbeeldingen te patchen.</span><span class="sxs-lookup"><span data-stu-id="c7c20-150">As a best practice, we recommend using offline servicing tools to patch golden/master images.</span></span>

<span data-ttu-id="c7c20-151">U kunt bijvoorbeeld de onderstaande opdrachten gebruiken om een update te installeren terwijl de afbeelding offline blijft:</span><span class="sxs-lookup"><span data-stu-id="c7c20-151">For example, you can use the below commands to install an update while the image remains offline:</span></span>

```console
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing"
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

<span data-ttu-id="c7c20-152">Zie de artikelen hieronder voor meer informatie over DISM-opdrachten en offlineonderhoud:</span><span class="sxs-lookup"><span data-stu-id="c7c20-152">For more information on DISM commands and offline servicing, please refer to the articles below:</span></span>

- [<span data-ttu-id="c7c20-153">Een afbeelding Windows DISM wijzigen</span><span class="sxs-lookup"><span data-stu-id="c7c20-153">Modify a Windows image using DISM</span></span>](/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [<span data-ttu-id="c7c20-154">DISM Image Management Command-Line Opties</span><span class="sxs-lookup"><span data-stu-id="c7c20-154">DISM Image Management Command-Line Options</span></span>](/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [<span data-ttu-id="c7c20-155">De grootte van het onderdelenbestand in een offline-Windows verkleinen</span><span class="sxs-lookup"><span data-stu-id="c7c20-155">Reduce the Size of the Component Store in an Offline Windows Image</span></span>](/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

<span data-ttu-id="c7c20-156">Als offline service geen haalbare optie is voor uw niet-permanente VDI-omgeving, moeten de volgende stappen worden genomen om consistentie en sensortoestand te waarborgen:</span><span class="sxs-lookup"><span data-stu-id="c7c20-156">If offline servicing is not a viable option for your non-persistent VDI environment, the following steps should be taken to ensure consistency and sensor health:</span></span>

1. <span data-ttu-id="c7c20-157">Nadat u de hoofdafbeelding voor online onderhoud of patching heeft opgestart, kunt u een offboarding-script uitvoeren om de Microsoft 365 endpoint-sensor voor preventie van gegevensverlies uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="c7c20-157">After booting the master image for online servicing or patching, run an offboarding script to turn off the Microsoft 365 Endpoint data loss prevention sensor.</span></span> <span data-ttu-id="c7c20-158">Zie Offboard-apparaten met [een lokaal script voor meer informatie.](dlp-configure-endpoints-script.md#offboard-devices-using-a-local-script)</span><span class="sxs-lookup"><span data-stu-id="c7c20-158">For more information, see [Offboard devices using a local script](dlp-configure-endpoints-script.md#offboard-devices-using-a-local-script).</span></span>

2. <span data-ttu-id="c7c20-159">Zorg ervoor dat de sensor wordt gestopt door de onderstaande opdracht uit te voeren in een CMD-venster:</span><span class="sxs-lookup"><span data-stu-id="c7c20-159">Ensure the sensor is stopped by running the command below in a CMD window:</span></span>

   ```console
   sc query sense
   ```

3. <span data-ttu-id="c7c20-160">Service de afbeelding zo nodig.</span><span class="sxs-lookup"><span data-stu-id="c7c20-160">Service the image as needed.</span></span>

4. <span data-ttu-id="c7c20-161">Voer de onderstaande opdrachten uit PsExec.exe (waaruit kan worden gedownload om de inhoud van de cybermap op te schonen die de sensor mogelijk heeft verzameld sinds het https://download.sysinternals.com/files/PSTools.zip) opstarten:</span><span class="sxs-lookup"><span data-stu-id="c7c20-161">Run the below commands using PsExec.exe (which can be downloaded from https://download.sysinternals.com/files/PSTools.zip) to cleanup the cyber folder contents that the sensor may have accumulated since boot:</span></span>

    ```console
    PsExec.exe -s cmd.exe
    cd "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Cyber"
    del *.* /f /s /q
    REG DELETE “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
    exit
    ```

5. <span data-ttu-id="c7c20-162">Verzegel de afbeelding van het gouden/hoofdmodel opnieuw zoals u dat normaal zou doen.</span><span class="sxs-lookup"><span data-stu-id="c7c20-162">Re-seal the golden/master image as you normally would.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c7c20-163">Gerelateerde onderwerpen</span><span class="sxs-lookup"><span data-stu-id="c7c20-163">Related topics</span></span>

- [<span data-ttu-id="c7c20-164">Onboard Windows 10 apparaten met groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="c7c20-164">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="c7c20-165">Onboard Windows 10 apparaten met Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="c7c20-165">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="c7c20-166">Onboarden Windows 10-apparaten met hulpmiddelen voor Mobile Device Management</span><span class="sxs-lookup"><span data-stu-id="c7c20-166">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="c7c20-167">Onboarden Windows 10-apparaten met een lokaal script</span><span class="sxs-lookup"><span data-stu-id="c7c20-167">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="c7c20-168">Problemen met de onboarding van Microsoft Defender Advanced Threat Protection oplossen</span><span class="sxs-lookup"><span data-stu-id="c7c20-168">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
