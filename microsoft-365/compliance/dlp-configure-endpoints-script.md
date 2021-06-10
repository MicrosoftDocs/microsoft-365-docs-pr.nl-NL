---
title: Onboarden Windows 10-apparaten met een lokaal script
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
description: Gebruik een lokaal script om het configuratiepakket op apparaten te implementeren, zodat ze zijn aan boord van de service.
ms.openlocfilehash: 55109d8fda52db6651d4398cd84ffd6668b4d871
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843444"
---
# <a name="onboard-windows-10-devices-using-a-local-script"></a><span data-ttu-id="3b0ed-103">Onboarden Windows 10-apparaten met een lokaal script</span><span class="sxs-lookup"><span data-stu-id="3b0ed-103">Onboard Windows 10 devices using a local script</span></span>

<span data-ttu-id="3b0ed-104">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="3b0ed-104">**Applies to:**</span></span>

- [<span data-ttu-id="3b0ed-105">Microsoft 365 Preventie van gegevensverlies in eindpunten (DLP)</span><span class="sxs-lookup"><span data-stu-id="3b0ed-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](./endpoint-dlp-learn-about.md)

<span data-ttu-id="3b0ed-106">U kunt ook afzonderlijke apparaten handmatig onboarden om Microsoft 365 voorkomen dat eindpunten verloren gaan.</span><span class="sxs-lookup"><span data-stu-id="3b0ed-106">You can also manually onboard individual devices to Microsoft 365 Endpoint data loss prevention.</span></span> <span data-ttu-id="3b0ed-107">Mogelijk wilt u dit eerst doen bij het testen van de service voordat u alle apparaten in uw netwerk gaat onboarden.</span><span class="sxs-lookup"><span data-stu-id="3b0ed-107">You might want to do this first when testing the service before you commit to onboarding all devices in your network.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3b0ed-108">Dit script is geoptimaliseerd voor gebruik op maximaal 10 apparaten.</span><span class="sxs-lookup"><span data-stu-id="3b0ed-108">This script has been optimized for use on up to 10 devices.</span></span>
>
> <span data-ttu-id="3b0ed-109">Gebruik andere implementatieopties om op schaal [te implementeren.](dlp-configure-endpoints.md)</span><span class="sxs-lookup"><span data-stu-id="3b0ed-109">To deploy at scale, use [other deployment options](dlp-configure-endpoints.md).</span></span> <span data-ttu-id="3b0ed-110">U kunt bijvoorbeeld een onboarding-script implementeren op meer dan 10 apparaten in productie met het script dat beschikbaar is in Onboard [Windows 10 apparaten met groepsbeleid.](dlp-configure-endpoints-gp.md)</span><span class="sxs-lookup"><span data-stu-id="3b0ed-110">For example, you can deploy an onboarding script to more than 10 devices in production with the script available in [Onboard Windows 10 devices using Group Policy](dlp-configure-endpoints-gp.md).</span></span>

## <a name="onboard-devices"></a><span data-ttu-id="3b0ed-111">Onboard-apparaten</span><span class="sxs-lookup"><span data-stu-id="3b0ed-111">Onboard devices</span></span>
 
1.  <span data-ttu-id="3b0ed-112">Open het GP-configuratiepakket .zip bestand *(DeviceComplianceOnboardingPackage.zip)* dat u hebt gedownload van de wizard Service onboarding.</span><span class="sxs-lookup"><span data-stu-id="3b0ed-112">Open the GP configuration package .zip file (*DeviceComplianceOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="3b0ed-113">U kunt het pakket ook krijgen in [het Microsoft Compliance Center](https://compliance.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="3b0ed-113">You can also get the package from [Microsoft Compliance center](https://compliance.microsoft.com)</span></span>

2. <span data-ttu-id="3b0ed-114">Selecteer in het navigatiedeelvenster **Instellingen**  >  **Onboarding van apparaat.**</span><span class="sxs-lookup"><span data-stu-id="3b0ed-114">In the navigation pane, select **Settings** > **Device onboarding**.</span></span>

3. <span data-ttu-id="3b0ed-115">Selecteer **lokaal** script in het veld **Implementatiemethode.**</span><span class="sxs-lookup"><span data-stu-id="3b0ed-115">In the **Deployment method** field, select **Local Script**.</span></span>

4. <span data-ttu-id="3b0ed-116">Klik **op Pakket downloaden** en sla het .zip op.</span><span class="sxs-lookup"><span data-stu-id="3b0ed-116">Click **Download package** and save the .zip file.</span></span>
  
5. <span data-ttu-id="3b0ed-117">Haal de inhoud van het configuratiepakket op naar een locatie op het apparaat dat u wilt inpakken (bijvoorbeeld het bureaublad).</span><span class="sxs-lookup"><span data-stu-id="3b0ed-117">Extract the contents of the configuration package to a location on the device you want to onboard (for example, the Desktop).</span></span> <span data-ttu-id="3b0ed-118">U moet een bestand met de naam *DeviceOnboardingScript.cmd hebben.*</span><span class="sxs-lookup"><span data-stu-id="3b0ed-118">You should have a file named *DeviceOnboardingScript.cmd*.</span></span>

6.  <span data-ttu-id="3b0ed-119">Open een opdrachtregelprompt met verhoogde opdrachtregel op het apparaat en voer het script uit:</span><span class="sxs-lookup"><span data-stu-id="3b0ed-119">Open an elevated command-line prompt on the device and run the script:</span></span>

7.  <span data-ttu-id="3b0ed-120">Go to **Start** and type **cmd**.</span><span class="sxs-lookup"><span data-stu-id="3b0ed-120">Go to **Start** and type **cmd**.</span></span>

8.  <span data-ttu-id="3b0ed-121">Klik met de rechtermuisknop op **Opdrachtprompt** en selecteer **Als beheerder uitvoeren**.</span><span class="sxs-lookup"><span data-stu-id="3b0ed-121">Right-click **Command prompt** and select **Run as administrator**.</span></span>

    ![Venster startmenu dat verwijst naar Uitvoeren als beheerder](../media/dlp-run-as-admin.png)

9.  <span data-ttu-id="3b0ed-123">Typ de locatie van het scriptbestand.</span><span class="sxs-lookup"><span data-stu-id="3b0ed-123">Type the location of the script file.</span></span> <span data-ttu-id="3b0ed-124">Als u het bestand naar het bureaublad hebt gekopieerd, typt u: *%userprofile%\Desktop\WindowsDefenderATPOnboardingScript.cmd*</span><span class="sxs-lookup"><span data-stu-id="3b0ed-124">If you copied the file to the desktop, type: *%userprofile%\Desktop\WindowsDefenderATPOnboardingScript.cmd*</span></span>

10.  <span data-ttu-id="3b0ed-125">Druk op **Enter** of klik op **OK.**</span><span class="sxs-lookup"><span data-stu-id="3b0ed-125">Press the **Enter** key or click **OK**.</span></span>

<span data-ttu-id="3b0ed-126">Zie Problemen met onboarding oplossen voor informatie over hoe u handmatig kunt valideren of het Microsoft Defender Advanced Threat Protection apparaat compatibel is en sensorgegevens correct [rapporteert.](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)</span><span class="sxs-lookup"><span data-stu-id="3b0ed-126">For information on how you can manually validate that the device is compliant and correctly reports sensor data see, [Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding).</span></span>

## <a name="offboard-devices-using-a-local-script"></a><span data-ttu-id="3b0ed-127">Offboard-apparaten met een lokaal script</span><span class="sxs-lookup"><span data-stu-id="3b0ed-127">Offboard devices using a local script</span></span>
<span data-ttu-id="3b0ed-128">Om veiligheidsredenen verloopt het pakket dat wordt gebruikt voor Offboard-apparaten 30 dagen na de datum waarop het is gedownload.</span><span class="sxs-lookup"><span data-stu-id="3b0ed-128">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="3b0ed-129">Verlopen offboarding-pakketten die naar een apparaat zijn verzonden, worden geweigerd.</span><span class="sxs-lookup"><span data-stu-id="3b0ed-129">Expired offboarding packages sent to an device will be rejected.</span></span> <span data-ttu-id="3b0ed-130">Wanneer u een offboarding-pakket downloadt, wordt u op de hoogte gesteld van de vervaldatum van de pakketten en wordt het ook opgenomen in de pakketnaam.</span><span class="sxs-lookup"><span data-stu-id="3b0ed-130">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="3b0ed-131">Onboarding- en offboarding-beleid mag niet tegelijkertijd op hetzelfde apparaat worden geïmplementeerd, anders veroorzaakt dit onvoorspelbare botsingen.</span><span class="sxs-lookup"><span data-stu-id="3b0ed-131">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="3b0ed-132">Het offboarding-pakket kopen bij [Microsoft Compliance Center](https://compliance.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="3b0ed-132">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com)</span></span>

2. <span data-ttu-id="3b0ed-133">Selecteer in het navigatiedeelvenster **Instellingen**  >  **Offboarding apparaat**.</span><span class="sxs-lookup"><span data-stu-id="3b0ed-133">In the navigation pane, select **Settings** > **Device offboarding**.</span></span>

3. <span data-ttu-id="3b0ed-134">Selecteer **lokaal** script in het veld **Implementatiemethode.**</span><span class="sxs-lookup"><span data-stu-id="3b0ed-134">In the **Deployment method** field, select **Local Script**.</span></span>

4. <span data-ttu-id="3b0ed-135">Klik **op Pakket downloaden** en sla het .zip op.</span><span class="sxs-lookup"><span data-stu-id="3b0ed-135">Click **Download package** and save the .zip file.</span></span>

5. <span data-ttu-id="3b0ed-136">Haal de inhoud van het .zip op naar een gedeelde, alleen-lezen locatie die toegankelijk is voor de apparaten.</span><span class="sxs-lookup"><span data-stu-id="3b0ed-136">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the devices.</span></span> <span data-ttu-id="3b0ed-137">U moet een bestand met de naam *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd* hebben.</span><span class="sxs-lookup"><span data-stu-id="3b0ed-137">You should have a file named *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span></span>

6.  <span data-ttu-id="3b0ed-138">Open een opdrachtregelprompt met verhoogde opdrachtregel op het apparaat en voer het script uit:</span><span class="sxs-lookup"><span data-stu-id="3b0ed-138">Open an elevated command-line prompt on the device and run the script:</span></span>

7.  <span data-ttu-id="3b0ed-139">Go to **Start** and type **cmd**.</span><span class="sxs-lookup"><span data-stu-id="3b0ed-139">Go to **Start** and type **cmd**.</span></span>

8.  <span data-ttu-id="3b0ed-140">Klik met de rechtermuisknop op **Opdrachtprompt** en selecteer **Als beheerder uitvoeren**.</span><span class="sxs-lookup"><span data-stu-id="3b0ed-140">Right-click **Command prompt** and select **Run as administrator**.</span></span>

    ![Venster startmenu dat verwijst naar Uitvoeren als beheerder](../media/dlp-run-as-admin.png)

9.  <span data-ttu-id="3b0ed-142">Typ de locatie van het scriptbestand.</span><span class="sxs-lookup"><span data-stu-id="3b0ed-142">Type the location of the script file.</span></span> <span data-ttu-id="3b0ed-143">Als u het bestand naar het bureaublad hebt gekopieerd, typt u: *%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*</span><span class="sxs-lookup"><span data-stu-id="3b0ed-143">If you copied the file to the desktop, type: *%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*</span></span>

10.  <span data-ttu-id="3b0ed-144">Druk op **Enter** of klik op **OK.**</span><span class="sxs-lookup"><span data-stu-id="3b0ed-144">Press the **Enter** key or click **OK**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3b0ed-145">Offboarding zorgt ervoor dat het apparaat stopt met het verzenden van sensorgegevens naar de portal.</span><span class="sxs-lookup"><span data-stu-id="3b0ed-145">Offboarding causes the device to stop sending sensor data to the portal.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="3b0ed-146">Apparaatconfiguratie controleren</span><span class="sxs-lookup"><span data-stu-id="3b0ed-146">Monitor device configuration</span></span>
<span data-ttu-id="3b0ed-147">U kunt de verschillende verificatiestappen volgen in de [Problemen met onboarding oplossen](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding) om te controleren of het script is voltooid en of de agent actief is.</span><span class="sxs-lookup"><span data-stu-id="3b0ed-147">You can follow the different verification steps in the [Troubleshoot onboarding issues]((/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding) to verify that the script completed successfully and the agent is running.</span></span>

<span data-ttu-id="3b0ed-148">Controle kan ook rechtstreeks in de portal of met behulp van de verschillende implementatiehulpmiddelen worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="3b0ed-148">Monitoring can also be done directly on the portal, or by using the different deployment tools.</span></span>

### <a name="monitor-devices-using-the-portal"></a><span data-ttu-id="3b0ed-149">Apparaten controleren met behulp van de portal</span><span class="sxs-lookup"><span data-stu-id="3b0ed-149">Monitor devices using the portal</span></span>
1. <span data-ttu-id="3b0ed-150">Ga naar [Microsoft 365 compliancecentrum.](https://compliance.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="3b0ed-150">Go to [Microsoft 365 Compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="3b0ed-151">Kies **Instellingen**  >  **Apparaat onboarding-apparaten**  >  .</span><span class="sxs-lookup"><span data-stu-id="3b0ed-151">Choose **Settings** > **Device onboarding** > **Devices**.</span></span>

3. <span data-ttu-id="3b0ed-152">Controleer of apparaten worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="3b0ed-152">Verify that devices are appearing.</span></span>


## <a name="related-topics"></a><span data-ttu-id="3b0ed-153">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="3b0ed-153">Related topics</span></span>
- [<span data-ttu-id="3b0ed-154">Onboard Windows 10 apparaten met groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="3b0ed-154">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="3b0ed-155">Onboard Windows 10 apparaten met Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="3b0ed-155">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="3b0ed-156">Onboarden Windows 10-apparaten met hulpmiddelen voor Mobile Device Management</span><span class="sxs-lookup"><span data-stu-id="3b0ed-156">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="3b0ed-157">Onboarden niet-permanente virtual desktop infrastructure (VDI)-apparaten</span><span class="sxs-lookup"><span data-stu-id="3b0ed-157">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="3b0ed-158">Een detectietest uitvoeren op een nieuw ingebouwde Microsoft Defender voor eindpuntapparaat</span><span class="sxs-lookup"><span data-stu-id="3b0ed-158">Run a detection test on a newly onboarded Microsoft Defender for Endpoint device</span></span>](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [<span data-ttu-id="3b0ed-159">Problemen met Microsoft Defender Advanced Threat Protection onboarding oplossen</span><span class="sxs-lookup"><span data-stu-id="3b0ed-159">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)