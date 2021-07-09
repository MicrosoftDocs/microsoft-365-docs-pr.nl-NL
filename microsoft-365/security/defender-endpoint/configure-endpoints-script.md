---
title: Onboarden Windows 10-apparaten met een lokaal script
description: Gebruik een lokaal script om het configuratiepakket op apparaten te implementeren om onboarding van de apparaten voor de service in te stellen.
keywords: apparaten configureren met behulp van een lokaal script, apparaatbeheer, Microsoft Defender configureren voor eindpuntapparaten
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
ms.technology: mde
ms.openlocfilehash: e15a02753c7a1b346021a4351af24b8fd28315da
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339644"
---
# <a name="onboard-the-windows-10-devices-using-a-local-script"></a><span data-ttu-id="3b354-104">Aan boord Windows 10 apparaten met een lokaal script</span><span class="sxs-lookup"><span data-stu-id="3b354-104">Onboard the Windows 10 devices using a local script</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

- [<span data-ttu-id="3b354-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3b354-105">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="3b354-106">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="3b354-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="3b354-107">Meld u aan voor een gratis proefversie.</span><span class="sxs-lookup"><span data-stu-id="3b354-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpointsscript-abovefoldlink)

<span data-ttu-id="3b354-108">U kunt ook afzonderlijke apparaten handmatig aan boord brengen van Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="3b354-108">You can also manually onboard individual devices to Defender for Endpoint.</span></span> <span data-ttu-id="3b354-109">Mogelijk wilt u dit eerst doen bij het testen van de service voordat u alle apparaten in uw netwerk gaat onboarden.</span><span class="sxs-lookup"><span data-stu-id="3b354-109">You might want to do this first when testing the service before you commit to onboarding all devices in your network.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3b354-110">Dit script is geoptimaliseerd voor gebruik op maximaal 10 apparaten.</span><span class="sxs-lookup"><span data-stu-id="3b354-110">This script has been optimized for use on up to 10 devices.</span></span>
>
> <span data-ttu-id="3b354-111">Gebruik andere implementatieopties om op schaal [te implementeren.](configure-endpoints.md)</span><span class="sxs-lookup"><span data-stu-id="3b354-111">To deploy at scale, use [other deployment options](configure-endpoints.md).</span></span> <span data-ttu-id="3b354-112">U kunt bijvoorbeeld een onboarding-script implementeren op meer dan 10 apparaten in productie met het script dat beschikbaar is in Onboard [Windows 10 apparaten met groepsbeleid.](configure-endpoints-gp.md)</span><span class="sxs-lookup"><span data-stu-id="3b354-112">For example, you can deploy an onboarding script to more than 10 devices in production with the script available in [Onboard Windows 10 devices using Group Policy](configure-endpoints-gp.md).</span></span>

## <a name="onboard-devices"></a><span data-ttu-id="3b354-113">Onboard-apparaten</span><span class="sxs-lookup"><span data-stu-id="3b354-113">Onboard devices</span></span> 

<span data-ttu-id="3b354-114">[![Afbeelding van het PDF-bestand met de verschillende implementatiepaden](images/onboard-script.png)](images/onboard-script.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="3b354-114">[![Image of the PDF showing the various deployment paths](images/onboard-script.png)](images/onboard-script.png#lightbox)</span></span>


<span data-ttu-id="3b354-115">Bekijk het [PDF-bestand](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf) of [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) om de verschillende paden te bekijken bij de implementatie van Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="3b354-115">Check out the [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  or  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) to see the various paths in deploying Defender for Endpoint.</span></span> 


1.  <span data-ttu-id="3b354-116">Open het GP-configuratiepakket .zip bestand *(WindowsDefenderATPOnboardingPackage.zip)* dat u hebt gedownload van de wizard Service onboarding.</span><span class="sxs-lookup"><span data-stu-id="3b354-116">Open the GP configuration package .zip file (*WindowsDefenderATPOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="3b354-117">U kunt het pakket ook downloaden van [Microsoft 365 Defender-portal:](https://security.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="3b354-117">You can also get the package from [Microsoft 365  Defender portal](https://security.microsoft.com/):</span></span>

    1. <span data-ttu-id="3b354-118">Selecteer in het navigatiedeelvenster **Instellingen**  >  **Endpoints**  >  **Device management**  >  **Onboarding**.</span><span class="sxs-lookup"><span data-stu-id="3b354-118">In the navigation pane, select **Settings** > **Endpoints** > **Device management** > **Onboarding**.</span></span>

    1. <span data-ttu-id="3b354-119">Selecteer Windows 10 als het besturingssysteem.</span><span class="sxs-lookup"><span data-stu-id="3b354-119">Select Windows 10 as the operating system.</span></span>

    1. <span data-ttu-id="3b354-120">Selecteer **lokaal** script in het veld **Implementatiemethode.**</span><span class="sxs-lookup"><span data-stu-id="3b354-120">In the **Deployment method** field, select **Local Script**.</span></span>

    1. <span data-ttu-id="3b354-121">Klik **op Pakket downloaden** en sla het .zip op.</span><span class="sxs-lookup"><span data-stu-id="3b354-121">Click **Download package** and save the .zip file.</span></span>

  
2.  <span data-ttu-id="3b354-122">Haal de inhoud van het configuratiepakket op naar een locatie op het apparaat dat u wilt inpakken (bijvoorbeeld het bureaublad).</span><span class="sxs-lookup"><span data-stu-id="3b354-122">Extract the contents of the configuration package to a location on the device you want to onboard (for example, the Desktop).</span></span> <span data-ttu-id="3b354-123">U moet een bestand met de naam *WindowsDefenderATPLocalOnboardingScript.cmd hebben.*</span><span class="sxs-lookup"><span data-stu-id="3b354-123">You should have a file named *WindowsDefenderATPLocalOnboardingScript.cmd*.</span></span>

3.  <span data-ttu-id="3b354-124">Open een opdrachtregelprompt met verhoogde opdrachtregel op het apparaat en voer het script uit:</span><span class="sxs-lookup"><span data-stu-id="3b354-124">Open an elevated command-line prompt on the device and run the script:</span></span>

    1.  <span data-ttu-id="3b354-125">Go to **Start** and type **cmd**.</span><span class="sxs-lookup"><span data-stu-id="3b354-125">Go to **Start** and type **cmd**.</span></span>

    1.  <span data-ttu-id="3b354-126">Klik met de rechtermuisknop op **Opdrachtprompt** en selecteer **Als beheerder uitvoeren**.</span><span class="sxs-lookup"><span data-stu-id="3b354-126">Right-click **Command prompt** and select **Run as administrator**.</span></span>

        ![Venster Startmenu als beheerder uitvoeren](images/run-as-admin.png)

4.  <span data-ttu-id="3b354-128">Typ de locatie van het scriptbestand.</span><span class="sxs-lookup"><span data-stu-id="3b354-128">Type the location of the script file.</span></span> <span data-ttu-id="3b354-129">Als u het bestand naar het bureaublad hebt gekopieerd, typt u: *%userprofile%\Desktop\WindowsDefenderATPLocalOnboardingScript.cmd*</span><span class="sxs-lookup"><span data-stu-id="3b354-129">If you copied the file to the desktop, type: *%userprofile%\Desktop\WindowsDefenderATPLocalOnboardingScript.cmd*</span></span>

5.  <span data-ttu-id="3b354-130">Druk op **Enter** of klik op **OK.**</span><span class="sxs-lookup"><span data-stu-id="3b354-130">Press the **Enter** key or click **OK**.</span></span>

<span data-ttu-id="3b354-131">Zie Problemen met de onboarding van Microsoft Defender voor eindpunten oplossen voor informatie over hoe u handmatig kunt valideren dat het apparaat compatibel is en sensorgegevens correct [rapporteert.](troubleshoot-onboarding.md)</span><span class="sxs-lookup"><span data-stu-id="3b354-131">For information on how you can manually validate that the device is compliant and correctly reports sensor data see, [Troubleshoot Microsoft Defender for Endpoint onboarding issues](troubleshoot-onboarding.md).</span></span>


>[!TIP]
> <span data-ttu-id="3b354-132">Nadat u het apparaat hebt onboarding, kunt u ervoor kiezen om een detectietest uit te voeren om te controleren of een apparaat correct is aan boord van de service.</span><span class="sxs-lookup"><span data-stu-id="3b354-132">After onboarding the device, you can choose to run a detection test to verify that an device is properly onboarded to the service.</span></span> <span data-ttu-id="3b354-133">Zie Een detectietest uitvoeren op een nieuw ingebouwde [Microsoft Defender voor eindpunten voor meer informatie.](run-detection-test.md)</span><span class="sxs-lookup"><span data-stu-id="3b354-133">For more information, see [Run a detection test on a newly onboarded Microsoft Defender for Endpoint endpoint](run-detection-test.md).</span></span>

## <a name="configure-sample-collection-settings"></a><span data-ttu-id="3b354-134">Voorbeeldverzamelingsinstellingen configureren</span><span class="sxs-lookup"><span data-stu-id="3b354-134">Configure sample collection settings</span></span>
<span data-ttu-id="3b354-135">Voor elk apparaat kunt u een configuratiewaarde instellen om aan te geven of steekproeven kunnen worden verzameld vanaf het apparaat wanneer een aanvraag wordt ingediend via Microsoft 365 Defender om een bestand in te dienen voor uitgebreide analyse.</span><span class="sxs-lookup"><span data-stu-id="3b354-135">For each device, you can set a configuration value to state whether samples can be collected from the device when a request is made through Microsoft 365 Defender to submit a file for deep analysis.</span></span>

<span data-ttu-id="3b354-136">U kunt de instelling voor het delen van voorbeelden op het apparaat handmatig configureren met behulp van *regedit* of het maken en uitvoeren van *een REG-bestand.*</span><span class="sxs-lookup"><span data-stu-id="3b354-136">You can manually configure the sample sharing setting on the device by using *regedit* or creating and running a *.reg* file.</span></span>  

<span data-ttu-id="3b354-137">De configuratie wordt ingesteld via de volgende registersleutelinvoer:</span><span class="sxs-lookup"><span data-stu-id="3b354-137">The configuration is set through the following registry key entry:</span></span>

```console
Path: “HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection”
Name: "AllowSampleCollection"
Value: 0 or 1
```
<span data-ttu-id="3b354-138">Waarbij:</span><span class="sxs-lookup"><span data-stu-id="3b354-138">Where:</span></span><br>
<span data-ttu-id="3b354-139">Naamtype is een D-WORD.</span><span class="sxs-lookup"><span data-stu-id="3b354-139">Name type is a D-WORD.</span></span> <br>
<span data-ttu-id="3b354-140">Mogelijke waarden zijn:</span><span class="sxs-lookup"><span data-stu-id="3b354-140">Possible values are:</span></span>
- <span data-ttu-id="3b354-141">0 - is het delen van voorbeelden vanaf dit apparaat niet toegestaan</span><span class="sxs-lookup"><span data-stu-id="3b354-141">0 - doesn't allow sample sharing  from this device</span></span>
- <span data-ttu-id="3b354-142">1 : hiermee kunt u alle bestandstypen vanaf dit apparaat delen</span><span class="sxs-lookup"><span data-stu-id="3b354-142">1 - allows sharing of all file types from this device</span></span>

<span data-ttu-id="3b354-143">De standaardwaarde voor het geval de registersleutel niet bestaat, is 1.</span><span class="sxs-lookup"><span data-stu-id="3b354-143">The default value in case the registry key doesn’t exist is 1.</span></span>


## <a name="offboard-devices-using-a-local-script"></a><span data-ttu-id="3b354-144">Offboard-apparaten met een lokaal script</span><span class="sxs-lookup"><span data-stu-id="3b354-144">Offboard devices using a local script</span></span>
<span data-ttu-id="3b354-145">Om veiligheidsredenen verloopt het pakket dat wordt gebruikt voor Offboard-apparaten 30 dagen na de datum waarop het is gedownload.</span><span class="sxs-lookup"><span data-stu-id="3b354-145">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="3b354-146">Verlopen offboarding-pakketten die naar een apparaat zijn verzonden, worden geweigerd.</span><span class="sxs-lookup"><span data-stu-id="3b354-146">Expired offboarding packages sent to an device will be rejected.</span></span> <span data-ttu-id="3b354-147">Wanneer u een offboarding-pakket downloadt, wordt u op de hoogte gesteld van de vervaldatum van de pakketten en wordt het ook opgenomen in de pakketnaam.</span><span class="sxs-lookup"><span data-stu-id="3b354-147">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="3b354-148">Onboarding- en offboarding-beleid mag niet tegelijkertijd op hetzelfde apparaat worden geïmplementeerd, anders veroorzaakt dit onvoorspelbare botsingen.</span><span class="sxs-lookup"><span data-stu-id="3b354-148">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="3b354-149">Haal het offboarding-pakket van [Microsoft 365 Defender portal:](https://security.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="3b354-149">Get the offboarding package from [Microsoft 365 Defender portal](https://security.microsoft.com/):</span></span>

    1. <span data-ttu-id="3b354-150">Selecteer in het navigatiedeelvenster **Instellingen**  >  **Endpoints**  >  **Device management**  > **Offboarding**.</span><span class="sxs-lookup"><span data-stu-id="3b354-150">In the navigation pane, select **Settings** > **Endpoints** > **Device management** >**Offboarding**.</span></span>

    1. <span data-ttu-id="3b354-151">Selecteer Windows 10 als het besturingssysteem.</span><span class="sxs-lookup"><span data-stu-id="3b354-151">Select Windows 10 as the operating system.</span></span>

    1. <span data-ttu-id="3b354-152">Selecteer **lokaal** script in het veld **Implementatiemethode.**</span><span class="sxs-lookup"><span data-stu-id="3b354-152">In the **Deployment method** field, select **Local Script**.</span></span>

    1. <span data-ttu-id="3b354-153">Klik **op Pakket downloaden** en sla het .zip op.</span><span class="sxs-lookup"><span data-stu-id="3b354-153">Click **Download package** and save the .zip file.</span></span>

2. <span data-ttu-id="3b354-154">Haal de inhoud van het .zip op naar een gedeelde, alleen-lezen locatie die toegankelijk is voor de apparaten.</span><span class="sxs-lookup"><span data-stu-id="3b354-154">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the devices.</span></span> <span data-ttu-id="3b354-155">U moet een bestand met de *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd hebben.*</span><span class="sxs-lookup"><span data-stu-id="3b354-155">You should have a file named *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span></span>

3.  <span data-ttu-id="3b354-156">Open een opdrachtregelprompt met verhoogde opdrachtregel op het apparaat en voer het script uit:</span><span class="sxs-lookup"><span data-stu-id="3b354-156">Open an elevated command-line prompt on the device and run the script:</span></span>

    1.  <span data-ttu-id="3b354-157">Go to **Start** and type **cmd**.</span><span class="sxs-lookup"><span data-stu-id="3b354-157">Go to **Start** and type **cmd**.</span></span>

    1.  <span data-ttu-id="3b354-158">Klik met de rechtermuisknop op **Opdrachtprompt** en selecteer **Als beheerder uitvoeren**.</span><span class="sxs-lookup"><span data-stu-id="3b354-158">Right-click **Command prompt** and select **Run as administrator**.</span></span>

        ![Venster Startmenu als beheerder uitvoeren](images/run-as-admin.png)

4.  <span data-ttu-id="3b354-160">Typ de locatie van het scriptbestand.</span><span class="sxs-lookup"><span data-stu-id="3b354-160">Type the location of the script file.</span></span> <span data-ttu-id="3b354-161">Als u het bestand naar het bureaublad hebt gekopieerd, typt u: *%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*</span><span class="sxs-lookup"><span data-stu-id="3b354-161">If you copied the file to the desktop, type: *%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*</span></span>

5.  <span data-ttu-id="3b354-162">Druk op **Enter** of klik op **OK.**</span><span class="sxs-lookup"><span data-stu-id="3b354-162">Press the **Enter** key or click **OK**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3b354-163">Offboarding zorgt ervoor dat het apparaat stopt met het verzenden van sensorgegevens naar de portal, maar gegevens van het apparaat, inclusief verwijzingen naar eventuele waarschuwingen die het heeft ontvangen, blijven maximaal 6 maanden bewaard.</span><span class="sxs-lookup"><span data-stu-id="3b354-163">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="3b354-164">Apparaatconfiguratie controleren</span><span class="sxs-lookup"><span data-stu-id="3b354-164">Monitor device configuration</span></span>
<span data-ttu-id="3b354-165">U kunt de verschillende verificatiestappen volgen in de [onboarding-problemen](troubleshoot-onboarding.md) oplossen om te controleren of het script is voltooid en of de agent wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="3b354-165">You can follow the different verification steps in the [Troubleshoot onboarding issues](troubleshoot-onboarding.md) to verify that the script completed successfully and the agent is running.</span></span>

<span data-ttu-id="3b354-166">Controle kan ook rechtstreeks in de portal of met behulp van de verschillende implementatiehulpmiddelen worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="3b354-166">Monitoring can also be done directly on the portal, or by using the different deployment tools.</span></span>

### <a name="monitor-devices-using-the-portal"></a><span data-ttu-id="3b354-167">Apparaten controleren met behulp van de portal</span><span class="sxs-lookup"><span data-stu-id="3b354-167">Monitor devices using the portal</span></span>
1. <span data-ttu-id="3b354-168">Ga naar Microsoft 365 Defender portal.</span><span class="sxs-lookup"><span data-stu-id="3b354-168">Go to Microsoft 365 Defender portal.</span></span>

2. <span data-ttu-id="3b354-169">Klik **op Inventaris van apparaten.**</span><span class="sxs-lookup"><span data-stu-id="3b354-169">Click **Devices inventory**.</span></span>

3. <span data-ttu-id="3b354-170">Controleer of apparaten worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="3b354-170">Verify that devices are appearing.</span></span>


## <a name="related-topics"></a><span data-ttu-id="3b354-171">Gerelateerde onderwerpen</span><span class="sxs-lookup"><span data-stu-id="3b354-171">Related topics</span></span>
- [<span data-ttu-id="3b354-172">Onboard Windows 10 apparaten met groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="3b354-172">Onboard Windows 10 devices using Group Policy</span></span>](configure-endpoints-gp.md)
- [<span data-ttu-id="3b354-173">Onboard Windows 10 apparaten met Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="3b354-173">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md)
- [<span data-ttu-id="3b354-174">Onboarden Windows 10-apparaten met hulpmiddelen voor Mobile Device Management</span><span class="sxs-lookup"><span data-stu-id="3b354-174">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md)
- [<span data-ttu-id="3b354-175">Onboarden niet-permanente virtual desktop infrastructure (VDI)-apparaten</span><span class="sxs-lookup"><span data-stu-id="3b354-175">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](configure-endpoints-vdi.md)
- [<span data-ttu-id="3b354-176">Een detectietest uitvoeren op een nieuw ingebouwde Microsoft Defender voor eindpuntapparaat</span><span class="sxs-lookup"><span data-stu-id="3b354-176">Run a detection test on a newly onboarded Microsoft Defender for Endpoint device</span></span>](run-detection-test.md)
- [<span data-ttu-id="3b354-177">Problemen met de onboarding van Microsoft Defender voor eindpunten oplossen</span><span class="sxs-lookup"><span data-stu-id="3b354-177">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
