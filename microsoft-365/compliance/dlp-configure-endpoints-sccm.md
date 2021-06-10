---
title: Onboarden Windows 10-updates met Configuration Manager
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
description: Gebruik Configuration Manager om het configuratiepakket op apparaten te implementeren, zodat ze zijn aan boord van de service.
ms.openlocfilehash: ac05581ce33e94859dbd67848197878595d5ed0f
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/20/2021
ms.locfileid: "52162698"
---
# <a name="onboard-windows-10-devices-using-configuration-manager"></a><span data-ttu-id="7da8d-103">Onboarden Windows 10-updates met Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="7da8d-103">Onboard Windows 10 devices using Configuration Manager</span></span>

<span data-ttu-id="7da8d-104">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="7da8d-104">**Applies to:**</span></span>

- [<span data-ttu-id="7da8d-105">Microsoft 365 Preventie van gegevensverlies in eindpunten (DLP)</span><span class="sxs-lookup"><span data-stu-id="7da8d-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](./endpoint-dlp-learn-about.md)
- <span data-ttu-id="7da8d-106">System Center 2012 R2 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="7da8d-106">System Center 2012 R2 Configuration Manager</span></span>

### <a name="onboard-devices-using-system-center-configuration-manager"></a><span data-ttu-id="7da8d-107">Onboard-apparaten met System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="7da8d-107">Onboard devices using System Center Configuration Manager</span></span>

1. <span data-ttu-id="7da8d-108">Open het configuratiepakket Configuratiebeheer .zip bestand *(DeviceComplianceOnboardingPackage.zip)* dat u hebt gedownload uit de wizard Service onboarding.</span><span class="sxs-lookup"><span data-stu-id="7da8d-108">Open the Configuration Manager configuration package .zip file (*DeviceComplianceOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="7da8d-109">U kunt het pakket ook kopen in [het Microsoft Compliance Center.](https://compliance.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="7da8d-109">You can also get the package from [Microsoft Compliance center](https://compliance.microsoft.com/).</span></span>

2. <span data-ttu-id="7da8d-110">Selecteer in het navigatiedeelvenster **Instellingen**  >  **Onboarding van apparaat.**  >  </span><span class="sxs-lookup"><span data-stu-id="7da8d-110">In the navigation pane, select **Settings** > **Device Onboarding** > **Onboarding**.</span></span>

3. <span data-ttu-id="7da8d-111">Selecteer in **het veld** **Implementatiemethode Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602**.</span><span class="sxs-lookup"><span data-stu-id="7da8d-111">In the **Deployment method** field, select **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602**.</span></span>
 
4. <span data-ttu-id="7da8d-112">Selecteer **Pakket downloaden** en sla het .zip op.</span><span class="sxs-lookup"><span data-stu-id="7da8d-112">Select **Download package**, and save the .zip file.</span></span>

5. <span data-ttu-id="7da8d-113">Haal de inhoud van het .zip bestand op naar een gedeelde, alleen-lezen locatie die kan worden gebruikt door de netwerkbeheerders die het pakket zullen implementeren.</span><span class="sxs-lookup"><span data-stu-id="7da8d-113">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="7da8d-114">U moet een bestand met de naam *DeviceComplianceOnboardingScript.cmd hebben.*</span><span class="sxs-lookup"><span data-stu-id="7da8d-114">You should have a file named *DeviceComplianceOnboardingScript.cmd*.</span></span>

6. <span data-ttu-id="7da8d-115">Implementeer het pakket door de stappen in het artikel Pakketten en programma's [in System Center 2012 R2 Configuration Manager te](/previous-versions/system-center/system-center-2012-R2/gg699369(v=technet.10)) volgen.</span><span class="sxs-lookup"><span data-stu-id="7da8d-115">Deploy the package by following the steps in the [Packages and Programs in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg699369(v=technet.10)) article.</span></span>

7. <span data-ttu-id="7da8d-116">Kies een vooraf gedefinieerde apparaatverzameling om het pakket te implementeren.</span><span class="sxs-lookup"><span data-stu-id="7da8d-116">Choose a predefined device collection to deploy the package to.</span></span>

> [!NOTE]
> <span data-ttu-id="7da8d-117">Microsoft 365 Preventie van endpoint-gegevensverlies biedt geen ondersteuning voor onboarding tijdens de [OOBE-fase (Out-Of-Box Experience).](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87)</span><span class="sxs-lookup"><span data-stu-id="7da8d-117">Microsoft 365 Endpoint data loss prevention doesn't support onboarding during the [Out-Of-Box Experience (OOBE)](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87) phase.</span></span> <span data-ttu-id="7da8d-118">Zorg ervoor dat gebruikers OOBE voltooien na het uitvoeren Windows installatie of upgrade.</span><span class="sxs-lookup"><span data-stu-id="7da8d-118">Make sure users complete OOBE after running Windows installation or upgrading.</span></span>

>[!TIP]
> <span data-ttu-id="7da8d-119">Nadat u het apparaat hebt onboarding, kunt u ervoor kiezen om een detectietest uit te voeren om te controleren of een apparaat correct is aan boord van de service.</span><span class="sxs-lookup"><span data-stu-id="7da8d-119">After onboarding the device, you can choose to run a detection test to verify that an device is properly onboarded to the service.</span></span> <span data-ttu-id="7da8d-120">Zie Een detectietest uitvoeren op een nieuw ingebouwde [Microsoft Defender voor eindpuntapparaat](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="7da8d-120">For more information, see [Run a detection test on a newly onboarded Microsoft Defender for Endpoint device](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test).</span></span>
>
> <span data-ttu-id="7da8d-121">Houd er rekening mee dat het mogelijk is om een detectieregel te maken in een Configuration Manager-toepassing om continu te controleren of een apparaat is onboarded.</span><span class="sxs-lookup"><span data-stu-id="7da8d-121">Note that it is possible to create a detection rule on a Configuration Manager application to continuously check if a device has been onboarded.</span></span> <span data-ttu-id="7da8d-122">Een toepassing is een ander type object dan een pakket en programma.</span><span class="sxs-lookup"><span data-stu-id="7da8d-122">An application is a different type of object than a package and program.</span></span>
> <span data-ttu-id="7da8d-123">Als een apparaat nog niet is onboarded (vanwege in behandeling zijnde OOBE-voltooiing of een andere reden), wordt configuratiebeheer opnieuw gebruikt om het apparaat aan te sluiten totdat de regel de statuswijziging detecteert.</span><span class="sxs-lookup"><span data-stu-id="7da8d-123">If a device is not yet onboarded (due to pending OOBE completion or any other reason), Configuration Manager will retry to onboard the device until the rule detects the status change.</span></span>
> 
> <span data-ttu-id="7da8d-124">Dit gedrag kan worden bereikt door een detectieregel te maken die controleert of de registerwaarde 'OnboardingState' (van type REG_DWORD) = 1.</span><span class="sxs-lookup"><span data-stu-id="7da8d-124">This behavior can be accomplished by creating a detection rule checking if the "OnboardingState" registry value (of type REG_DWORD) = 1.</span></span>
> <span data-ttu-id="7da8d-125">Deze registerwaarde bevindt zich onder 'HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status'.</span><span class="sxs-lookup"><span data-stu-id="7da8d-125">This registry value is located under "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status".</span></span>
<span data-ttu-id="7da8d-126">Zie Detectiemethoden configureren [in System Center 2012 R2 Configuration Manager voor meer informatie.](/previous-versions/system-center/system-center-2012-R2/gg682159(v=technet.10)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type)</span><span class="sxs-lookup"><span data-stu-id="7da8d-126">For more information, see [Configure Detection Methods in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg682159(v=technet.10)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type).</span></span>

### <a name="configure-sample-collection-settings"></a><span data-ttu-id="7da8d-127">Voorbeeldverzamelingsinstellingen configureren</span><span class="sxs-lookup"><span data-stu-id="7da8d-127">Configure sample collection settings</span></span>

<span data-ttu-id="7da8d-128">Voor elk apparaat kunt u een configuratiewaarde instellen om aan te geven of steekproeven vanaf het apparaat kunnen worden verzameld wanneer een aanvraag wordt ingediend via Microsoft Defender-beveiligingscentrum om een bestand in te dienen voor uitgebreide analyse.</span><span class="sxs-lookup"><span data-stu-id="7da8d-128">For each device, you can set a configuration value to state whether samples can be collected from the device when a request is made through Microsoft Defender Security Center to submit a file for deep analysis.</span></span>

>[!NOTE]
><span data-ttu-id="7da8d-129">Deze configuratie-instellingen worden meestal uitgevoerd via Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="7da8d-129">These configuration settings are typically done through Configuration Manager.</span></span> 

<span data-ttu-id="7da8d-130">U kunt een complianceregel instellen voor configuratie-item in Configuration Manager om de instelling voor voorbeeld delen op een apparaat te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="7da8d-130">You can set a compliance rule for configuration item in Configuration Manager to change the sample share setting on a device.</span></span>

<span data-ttu-id="7da8d-131">Deze regel moet een *configuratie-item* voor complianceregel zijn dat de waarde van een registersleutel op gerichte apparaten in stelt om ervoor te zorgen dat ze een klacht indienen.</span><span class="sxs-lookup"><span data-stu-id="7da8d-131">This rule should be a *remediating* compliance rule configuration item that sets the value of a registry key on targeted devices to make sure they’re complaint.</span></span>

<span data-ttu-id="7da8d-132">De configuratie wordt ingesteld via de volgende registersleutelinvoer:</span><span class="sxs-lookup"><span data-stu-id="7da8d-132">The configuration is set through the following registry key entry:</span></span>

```
Path: “HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection”
Name: "AllowSampleCollection"
Value: 0 or 1
```
<span data-ttu-id="7da8d-133">Waarbij:</span><span class="sxs-lookup"><span data-stu-id="7da8d-133">Where:</span></span><br>
<span data-ttu-id="7da8d-134">Het type toets is een D-WORD.</span><span class="sxs-lookup"><span data-stu-id="7da8d-134">Key type is a D-WORD.</span></span> <br>
<span data-ttu-id="7da8d-135">Mogelijke waarden zijn:</span><span class="sxs-lookup"><span data-stu-id="7da8d-135">Possible values are:</span></span>
- <span data-ttu-id="7da8d-136">0 - is het delen van voorbeelden vanaf dit apparaat niet toegestaan</span><span class="sxs-lookup"><span data-stu-id="7da8d-136">0 - doesn't allow sample sharing  from this device</span></span>
- <span data-ttu-id="7da8d-137">1 : hiermee kunt u alle bestandstypen vanaf dit apparaat delen</span><span class="sxs-lookup"><span data-stu-id="7da8d-137">1 - allows sharing of all file types from this device</span></span>

<span data-ttu-id="7da8d-138">De standaardwaarde voor het geval de registersleutel niet bestaat, is 1.</span><span class="sxs-lookup"><span data-stu-id="7da8d-138">The default value in case the registry key doesn’t exist is 1.</span></span>

<span data-ttu-id="7da8d-139">Zie Inleiding tot nalevingsinstellingen in System Center Configuration Manager [2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg682139(v=technet.10))voor meer informatie over System Center compliance-instellingen.</span><span class="sxs-lookup"><span data-stu-id="7da8d-139">For more information about System Center Configuration Manager Compliance, see [Introduction to compliance settings in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg682139(v=technet.10)).</span></span>


## <a name="other-recommended-configuration-settings"></a><span data-ttu-id="7da8d-140">Andere aanbevolen configuratie-instellingen</span><span class="sxs-lookup"><span data-stu-id="7da8d-140">Other recommended configuration settings</span></span>
<span data-ttu-id="7da8d-141">Nadat u apparaten hebt toegevoegd aan de service, is het belangrijk om te profiteren van de meegeleverde mogelijkheden voor bedreigingsbeveiliging door ze in te stellen met de volgende aanbevolen configuratie-instellingen.</span><span class="sxs-lookup"><span data-stu-id="7da8d-141">After onboarding devices to the service, it's important to take advantage of the included threat protection capabilities by enabling them with the following recommended configuration settings.</span></span>

### <a name="device-collection-configuration"></a><span data-ttu-id="7da8d-142">Apparaatverzamelingsconfiguratie</span><span class="sxs-lookup"><span data-stu-id="7da8d-142">Device collection configuration</span></span>
<span data-ttu-id="7da8d-143">Als u Endpoint Configuration Manager, versie 2002 of hoger, gebruikt, kunt u ervoor kiezen om de implementatie uit te lijnen met servers of down-level clients.</span><span class="sxs-lookup"><span data-stu-id="7da8d-143">If you're using Endpoint Configuration Manager, version 2002 or later, you can choose to broaden the deployment to include servers or down-level clients.</span></span>


### <a name="next-generation-protection-configuration"></a><span data-ttu-id="7da8d-144">Beveiligingsconfiguratie van de volgende generatie</span><span class="sxs-lookup"><span data-stu-id="7da8d-144">Next generation protection configuration</span></span>

<span data-ttu-id="7da8d-145">De volgende configuratie-instellingen worden aanbevolen:</span><span class="sxs-lookup"><span data-stu-id="7da8d-145">The following configuration settings are recommended:</span></span>

<span data-ttu-id="7da8d-146">**Scannen**</span><span class="sxs-lookup"><span data-stu-id="7da8d-146">**Scan**</span></span>

- <span data-ttu-id="7da8d-147">Verwisselbare opslagapparaten scannen, zoals USB-stations: Ja</span><span class="sxs-lookup"><span data-stu-id="7da8d-147">Scan removable storage devices such as USB drives: Yes</span></span>

<span data-ttu-id="7da8d-148">**Realtime beveiliging**</span><span class="sxs-lookup"><span data-stu-id="7da8d-148">**Real-time Protection**</span></span>

- <span data-ttu-id="7da8d-149">Gedragscontrole inschakelen: Ja</span><span class="sxs-lookup"><span data-stu-id="7da8d-149">Enable Behavioral Monitoring: Yes</span></span>
- <span data-ttu-id="7da8d-150">Beveiliging inschakelen tegen potentieel ongewenste toepassingen bij downloaden en vóór de installatie: Ja</span><span class="sxs-lookup"><span data-stu-id="7da8d-150">Enable protection against Potentially Unwanted Applications at download and prior to installation: Yes</span></span>

<span data-ttu-id="7da8d-151">**Cloudbeveiligingsservice**</span><span class="sxs-lookup"><span data-stu-id="7da8d-151">**Cloud Protection Service**</span></span>

- <span data-ttu-id="7da8d-152">Lidmaatschapstype Cloud Protection Service: Geavanceerd lidmaatschap</span><span class="sxs-lookup"><span data-stu-id="7da8d-152">Cloud Protection Service membership type: Advanced membership</span></span>

<span data-ttu-id="7da8d-153">**Surface-beperking voor aanvallen** Configureer alle beschikbare regels om te controleren.</span><span class="sxs-lookup"><span data-stu-id="7da8d-153">**Attack surface reduction** Configure all available rules to Audit.</span></span>

>[!NOTE]
> <span data-ttu-id="7da8d-154">Het blokkeren van deze activiteiten kan legitieme bedrijfsprocessen onderbreken.</span><span class="sxs-lookup"><span data-stu-id="7da8d-154">Blocking these activities may interrupt legitimate business processes.</span></span> <span data-ttu-id="7da8d-155">De beste methode is om alles in te stellen op controle, om te bepalen welke veilig zijn om in te zetten en vervolgens de instellingen in te stellen op eindpunten die geen fout-positieve detecties hebben.</span><span class="sxs-lookup"><span data-stu-id="7da8d-155">The best approach is setting everything to audit, identifying which ones are safe to turn on, and then enabling those settings on endpoints which do not have false positive detections.</span></span>

<span data-ttu-id="7da8d-156">**Netwerkbeveiliging**</span><span class="sxs-lookup"><span data-stu-id="7da8d-156">**Network protection**</span></span>

<span data-ttu-id="7da8d-157">Voordat u netwerkbeveiliging in de audit- of blokmodus inschakelen, moet u ervoor zorgen dat u de antimalware-platformupdate hebt geïnstalleerd, die kan worden verkregen via de [ondersteuningspagina.](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing)</span><span class="sxs-lookup"><span data-stu-id="7da8d-157">Prior to enabling network protection in audit or block mode, ensure that you've installed the antimalware platform update, which can be obtained from the [support page](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing).</span></span>


<span data-ttu-id="7da8d-158">**Beheerde maptoegang**</span><span class="sxs-lookup"><span data-stu-id="7da8d-158">**Controlled folder access**</span></span>

<span data-ttu-id="7da8d-159">Schakel de functie in de auditmodus minimaal 30 dagen in.</span><span class="sxs-lookup"><span data-stu-id="7da8d-159">Enable the feature in audit mode for at least 30 days.</span></span> <span data-ttu-id="7da8d-160">Na deze periode controleert u detecties en maakt u een lijst met toepassingen die mogen schrijven naar beveiligde directories.</span><span class="sxs-lookup"><span data-stu-id="7da8d-160">After this period, review detections and create a list of applications that are allowed to write to protected directories.</span></span>

<span data-ttu-id="7da8d-161">Zie Beheerde maptoegang evalueren voor meer [informatie.](/windows/security/threat-protection/microsoft-defender-atp/evaluate-controlled-folder-access)</span><span class="sxs-lookup"><span data-stu-id="7da8d-161">For more information, see [Evaluate controlled folder access](/windows/security/threat-protection/microsoft-defender-atp/evaluate-controlled-folder-access).</span></span>


## <a name="offboard-devices-using-configuration-manager"></a><span data-ttu-id="7da8d-162">Offboard-apparaten met Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="7da8d-162">Offboard devices using Configuration Manager</span></span>

<span data-ttu-id="7da8d-163">Om veiligheidsredenen verloopt het pakket dat wordt gebruikt voor Offboard-apparaten 30 dagen na de datum waarop het is gedownload.</span><span class="sxs-lookup"><span data-stu-id="7da8d-163">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="7da8d-164">Verlopen offboarding-pakketten die naar een apparaat zijn verzonden, worden geweigerd.</span><span class="sxs-lookup"><span data-stu-id="7da8d-164">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="7da8d-165">Wanneer u een offboarding-pakket downloadt, wordt u op de hoogte gesteld van de vervaldatum van de pakketten en wordt het ook opgenomen in de pakketnaam.</span><span class="sxs-lookup"><span data-stu-id="7da8d-165">When downloading an offboarding package, you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="7da8d-166">Onboarding- en offboarding-beleid mag niet tegelijkertijd op hetzelfde apparaat worden geïmplementeerd, anders veroorzaakt dit onvoorspelbare botsingen.</span><span class="sxs-lookup"><span data-stu-id="7da8d-166">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

### <a name="offboard-devices-using-microsoft-endpoint-configuration-manager-current-branch"></a><span data-ttu-id="7da8d-167">Offboard-apparaten met Microsoft Endpoint Configuration Manager huidige vertakking</span><span class="sxs-lookup"><span data-stu-id="7da8d-167">Offboard devices using Microsoft Endpoint Configuration Manager current branch</span></span>

<span data-ttu-id="7da8d-168">Zie Een [offboarding-configuratiebestand](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file)maken als Microsoft Endpoint Configuration Manager huidige vertakking gebruikt.</span><span class="sxs-lookup"><span data-stu-id="7da8d-168">If you use Microsoft Endpoint Configuration Manager current branch, see [Create an offboarding configuration file](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file).</span></span>

### <a name="offboard-devices-using-system-center-2012-r2-configuration-manager"></a><span data-ttu-id="7da8d-169">Offboard-apparaten met System Center 2012 R2 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="7da8d-169">Offboard devices using System Center 2012 R2 Configuration Manager</span></span>

1. <span data-ttu-id="7da8d-170">Haal het offboarding-pakket op in [het Microsoft Compliance Center:](https://compliance.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="7da8d-170">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com/):</span></span>

2. <span data-ttu-id="7da8d-171">Selecteer in het navigatiedeelvenster **Instellingen**  >   **Onboarding** >  **offboarding** voor apparaten.</span><span class="sxs-lookup"><span data-stu-id="7da8d-171">In the navigation pane, select **Settings** >  **Device onboarding**> **Offboarding**.</span></span>

3. <span data-ttu-id="7da8d-172">Selecteer Windows 10 als het besturingssysteem.</span><span class="sxs-lookup"><span data-stu-id="7da8d-172">Select Windows 10 as the operating system.</span></span>

4. <span data-ttu-id="7da8d-173">Selecteer in **het veld** **Implementatiemethode Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602**.</span><span class="sxs-lookup"><span data-stu-id="7da8d-173">In the **Deployment method** field, select **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602**.</span></span>
    
5. <span data-ttu-id="7da8d-174">Selecteer **Pakket downloaden** en sla het .zip op.</span><span class="sxs-lookup"><span data-stu-id="7da8d-174">Select **Download package**, and save the .zip file.</span></span>

6. <span data-ttu-id="7da8d-175">Haal de inhoud van het .zip bestand op naar een gedeelde, alleen-lezen locatie die kan worden gebruikt door de netwerkbeheerders die het pakket zullen implementeren.</span><span class="sxs-lookup"><span data-stu-id="7da8d-175">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="7da8d-176">U moet een bestand met de naam *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd* hebben.</span><span class="sxs-lookup"><span data-stu-id="7da8d-176">You should have a file named *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span></span>

7. <span data-ttu-id="7da8d-177">Implementeer het pakket door de stappen in het artikel Pakketten en programma's [in System Center 2012 R2 Configuration Manager te](/previous-versions/system-center/system-center-2012-R2/gg699369(v=technet.10)) volgen.</span><span class="sxs-lookup"><span data-stu-id="7da8d-177">Deploy the package by following the steps in the [Packages and Programs in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg699369(v=technet.10)) article.</span></span>

8. <span data-ttu-id="7da8d-178">Kies een vooraf gedefinieerde apparaatverzameling om het pakket te implementeren.</span><span class="sxs-lookup"><span data-stu-id="7da8d-178">Choose a predefined device collection to deploy the package to.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7da8d-179">Offboarding zorgt ervoor dat het apparaat stopt met het verzenden van sensorgegevens naar de portal, maar gegevens van het apparaat, inclusief verwijzingen naar eventuele waarschuwingen die het heeft ontvangen, blijven maximaal 6 maanden bewaard.</span><span class="sxs-lookup"><span data-stu-id="7da8d-179">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="7da8d-180">Apparaatconfiguratie controleren</span><span class="sxs-lookup"><span data-stu-id="7da8d-180">Monitor device configuration</span></span>

<span data-ttu-id="7da8d-181">Als u de huidige Microsoft Endpoint Configuration Manager gebruikt, gebruikt u het ingebouwde Dashboard van Microsoft Defender voor eindpunt in de console Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="7da8d-181">If you're using Microsoft Endpoint Configuration Manager current branch, use the built-in Microsoft Defender for Endpoint dashboard in the Configuration Manager console.</span></span> <span data-ttu-id="7da8d-182">Zie de Microsoft Defender Advanced Threat Protection [- Monitor voor meer informatie.](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor)</span><span class="sxs-lookup"><span data-stu-id="7da8d-182">For more information, see [Microsoft Defender Advanced Threat Protection - Monitor](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor).</span></span>

<span data-ttu-id="7da8d-183">Als u configuratiebeheer System Center 2012 R2 gebruikt, bestaat monitoring uit twee onderdelen:</span><span class="sxs-lookup"><span data-stu-id="7da8d-183">If you're using System Center 2012 R2 Configuration Manager, monitoring consists of two parts:</span></span>

1. <span data-ttu-id="7da8d-184">Bevestigen dat het configuratiepakket correct is geïmplementeerd en wordt uitgevoerd (of is uitgevoerd) op de apparaten in uw netwerk.</span><span class="sxs-lookup"><span data-stu-id="7da8d-184">Confirming the configuration package has been correctly deployed and is running (or has successfully run) on the devices in your network.</span></span>

2. <span data-ttu-id="7da8d-185">Controleren of de apparaten voldoen aan de Microsoft 365 Endpoint-service voor preventie van gegevensverlies (dit zorgt ervoor dat het apparaat het onboardingproces kan voltooien en gegevens kan blijven rapporteren aan de service).</span><span class="sxs-lookup"><span data-stu-id="7da8d-185">Checking that the devices are compliant with the Microsoft 365 Endpoint data loss prevention service (this ensures the device can complete the onboarding process and can continue to report data to the service).</span></span>

### <a name="confirm-the-configuration-package-has-been-correctly-deployed"></a><span data-ttu-id="7da8d-186">Controleren of het configuratiepakket correct is geïmplementeerd</span><span class="sxs-lookup"><span data-stu-id="7da8d-186">Confirm the configuration package has been correctly deployed</span></span>

1. <span data-ttu-id="7da8d-187">Klik in de console Configuration Manager op **Controleren** onder aan het navigatiedeelvenster.</span><span class="sxs-lookup"><span data-stu-id="7da8d-187">In the Configuration Manager console, click **Monitoring** at the bottom of the navigation pane.</span></span>

2. <span data-ttu-id="7da8d-188">Selecteer **Overzicht** en vervolgens **Implementaties.**</span><span class="sxs-lookup"><span data-stu-id="7da8d-188">Select **Overview** and then **Deployments**.</span></span>

3. <span data-ttu-id="7da8d-189">Selecteer op de implementatie met de naam van het pakket.</span><span class="sxs-lookup"><span data-stu-id="7da8d-189">Select on the deployment with the package name.</span></span>

4. <span data-ttu-id="7da8d-190">Bekijk de statusindicatoren onder **Voltooiingsstatistieken** en **Inhoudsstatus**.</span><span class="sxs-lookup"><span data-stu-id="7da8d-190">Review the status indicators under **Completion Statistics** and **Content Status**.</span></span>

    <span data-ttu-id="7da8d-191">Als er mislukte implementaties zijn (apparaten met **fout,** niet-voldaane vereisten of mislukte **statussen),** moet u mogelijk problemen met de apparaten oplossen.</span><span class="sxs-lookup"><span data-stu-id="7da8d-191">If there are failed deployments (devices with **Error**, **Requirements Not Met**, or **Failed statuses**), you may need to  troubleshoot the devices.</span></span> <span data-ttu-id="7da8d-192">Zie Problemen met [onboarding](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)oplossen Microsoft Defender Advanced Threat Protection meer informatie.</span><span class="sxs-lookup"><span data-stu-id="7da8d-192">For more information, see, [Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding).</span></span>

    ![Configuration Manager met een geslaagde implementatie zonder fouten](../media/sccm-deployment.png)

### <a name="check-that-the-devices-are-compliant-with-the-microsoft-365-endpoint-data-loss-prevention-service"></a><span data-ttu-id="7da8d-194">Controleer of de apparaten voldoen aan de Microsoft 365 endpoint-service voor preventie van gegevensverlies</span><span class="sxs-lookup"><span data-stu-id="7da8d-194">Check that the devices are compliant with the Microsoft 365 Endpoint data loss prevention service</span></span>

<span data-ttu-id="7da8d-195">U kunt een complianceregel instellen voor configuratie-item in System Center 2012 R2 Configuration Manager om uw implementatie te controleren.</span><span class="sxs-lookup"><span data-stu-id="7da8d-195">You can set a compliance rule for configuration item in System Center 2012 R2 Configuration Manager to monitor your deployment.</span></span>

> [!NOTE]
> <span data-ttu-id="7da8d-196">Deze procedure en registerinvoer zijn van toepassing op Endpoint DLP en Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="7da8d-196">This procedure and registry entry applies to Endpoint DLP as well as Advanced Threat Protection.</span></span>

<span data-ttu-id="7da8d-197">Deze regel moet een *configuratieitem voor complianceregelen* zijn dat de waarde van een registersleutel op gerichte apparaten controleert.</span><span class="sxs-lookup"><span data-stu-id="7da8d-197">This rule should be a *non-remediating* compliance rule configuration item that monitors the value of a registry key on targeted devices.</span></span>

<span data-ttu-id="7da8d-198">De volgende registersleutelinvoer controleren:</span><span class="sxs-lookup"><span data-stu-id="7da8d-198">Monitor the following registry key entry:</span></span>
```
Path: “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status”
Name: “OnboardingState”
Value: “1”
```
<span data-ttu-id="7da8d-199">Zie Inleiding tot compliance-instellingen [in System Center 2012 R2 Configuration Manager voor meer informatie.](/previous-versions/system-center/system-center-2012-R2/gg682139(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="7da8d-199">For more information, see [Introduction to compliance settings in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg682139(v=technet.10)).</span></span>

## <a name="related-topics"></a><span data-ttu-id="7da8d-200">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="7da8d-200">Related topics</span></span>
- [<span data-ttu-id="7da8d-201">Onboard Windows 10 apparaten met groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="7da8d-201">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="7da8d-202">Onboarden Windows 10-apparaten met hulpmiddelen voor Mobile Device Management</span><span class="sxs-lookup"><span data-stu-id="7da8d-202">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="7da8d-203">Onboarden Windows 10-apparaten met een lokaal script</span><span class="sxs-lookup"><span data-stu-id="7da8d-203">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="7da8d-204">Onboarden niet-permanente virtual desktop infrastructure (VDI)-apparaten</span><span class="sxs-lookup"><span data-stu-id="7da8d-204">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="7da8d-205">Een detectietest uitvoeren op een nieuw ingebouwde Microsoft Defender voor eindpuntapparaat</span><span class="sxs-lookup"><span data-stu-id="7da8d-205">Run a detection test on a newly onboarded Microsoft Defender for Endpoint device</span></span>](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [<span data-ttu-id="7da8d-206">Problemen met Microsoft Defender Advanced Threat Protection onboarding oplossen</span><span class="sxs-lookup"><span data-stu-id="7da8d-206">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)