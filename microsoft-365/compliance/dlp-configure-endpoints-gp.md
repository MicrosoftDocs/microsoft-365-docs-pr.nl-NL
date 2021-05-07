---
title: Onboarden Windows 10-apparaten via Groepsbeleid
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Gebruik Groepsbeleid om het configuratiepakket te implementeren op Windows 10 apparaten, zodat ze zijn aan boord van de service.
ms.openlocfilehash: 284de5169324b6da4038cfe0b50b2f2ffa40e3fd
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/20/2021
ms.locfileid: "52162699"
---
# <a name="onboard-windows-10-devices-using-group-policy"></a><span data-ttu-id="d800b-103">Onboard Windows 10 apparaten met groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="d800b-103">Onboard Windows 10 devices using Group Policy</span></span> 

<span data-ttu-id="d800b-104">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="d800b-104">**Applies to:**</span></span>

- [<span data-ttu-id="d800b-105">Microsoft 365 Preventie van gegevensverlies in eindpunten (DLP)</span><span class="sxs-lookup"><span data-stu-id="d800b-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](./endpoint-dlp-learn-about.md)
- <span data-ttu-id="d800b-106">Groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="d800b-106">Group Policy</span></span>

> [!NOTE]
> <span data-ttu-id="d800b-107">Als u gp-updates (Group Policy) wilt gebruiken om het pakket te implementeren, moet u zich Windows Server 2008 R2 of hoger.</span><span class="sxs-lookup"><span data-stu-id="d800b-107">To use Group Policy (GP) updates to deploy the package, you must be on Windows Server 2008 R2 or later.</span></span>

> <span data-ttu-id="d800b-108">Voor Windows Server 2019 moet u mogelijk NT AUTHORITY\Well-Known-System-Account vervangen door NT AUTHORITY\SYSTEM van het XML-bestand dat door de groepsbeleidsvoorkeur wordt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="d800b-108">For Windows Server 2019, you may need to replace NT AUTHORITY\Well-Known-System-Account with NT AUTHORITY\SYSTEM of the XML file that the Group Policy preference creates.</span></span>

## <a name="onboard-devices-using-group-policy"></a><span data-ttu-id="d800b-109">Onboarden apparaten met Groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="d800b-109">Onboard devices using Group Policy</span></span>

1. <span data-ttu-id="d800b-110">Open het GP-configuratiepakket .zip bestand *(DeviceComplianceOnboardingPackage.zip)* dat u hebt gedownload van de wizard Service onboarding.</span><span class="sxs-lookup"><span data-stu-id="d800b-110">Open the GP configuration package .zip file (*DeviceComplianceOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="d800b-111">U kunt het pakket ook krijgen in [het Microsoft Compliance Center](https://compliance.microsoft.com/compliancesettings/deviceonboarding)</span><span class="sxs-lookup"><span data-stu-id="d800b-111">You can also get the package from [Microsoft Compliance center](https://compliance.microsoft.com/compliancesettings/deviceonboarding)</span></span>

2. <span data-ttu-id="d800b-112">Selecteer in het navigatiedeelvenster **Instellingen**  >  **Onboarding van apparaat.**</span><span class="sxs-lookup"><span data-stu-id="d800b-112">In the navigation pane, select **Settings** > **Device Onboarding**.</span></span>

3. <span data-ttu-id="d800b-113">Selecteer groepsbeleid in **het veld** **Implementatiemethode.**</span><span class="sxs-lookup"><span data-stu-id="d800b-113">In the **Deployment method** field, select **Group policy**.</span></span>

4. <span data-ttu-id="d800b-114">Klik **op Pakket downloaden** en sla het .zip op.</span><span class="sxs-lookup"><span data-stu-id="d800b-114">Click **Download package** and save the .zip file.</span></span>

5. <span data-ttu-id="d800b-115">Haal de inhoud van het .zip naar een gedeelde, alleen-lezen locatie die toegankelijk is voor het apparaat.</span><span class="sxs-lookup"><span data-stu-id="d800b-115">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="d800b-116">U moet een map met de naam *OptionalParamsPolicy en* het bestand *DeviceComplianceLocalOnboardingScript.cmd hebben.*</span><span class="sxs-lookup"><span data-stu-id="d800b-116">You should have a folder called *OptionalParamsPolicy* and the file *DeviceComplianceLocalOnboardingScript.cmd*.</span></span>

6. <span data-ttu-id="d800b-117">Open de GPMC (Group [Policy Management Console),](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en klik op **Bewerken.**</span><span class="sxs-lookup"><span data-stu-id="d800b-117">Open the [Group Policy Management Console](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>

7. <span data-ttu-id="d800b-118">Ga in **de Editor voor groepsbeleidsbeheer** naar **Computerconfiguratie,** vervolgens **Voorkeuren** en vervolgens **naar Configuratiescherminstellingen.**</span><span class="sxs-lookup"><span data-stu-id="d800b-118">In the **Group Policy Management Editor**, go to **Computer configuration**, then **Preferences**, and then **Control panel settings**.</span></span>

8. <span data-ttu-id="d800b-119">Klik met de rechtermuisknop **op Geplande taken,** wijs **Nieuw** aan en klik vervolgens op Onmiddellijke **taak (ten minste Windows 7).**</span><span class="sxs-lookup"><span data-stu-id="d800b-119">Right-click **Scheduled tasks**, point to **New**, and then click **Immediate Task (At least Windows 7)**.</span></span>

9. <span data-ttu-id="d800b-120">Ga in **het** venster Taak dat wordt geopend naar het **tabblad** Algemeen. Klik **onder Beveiligingsopties** **op Gebruiker of Groep wijzigen** en typ SYSTEEM en klik vervolgens op Namen **controleren** en vervolgens **OP OK.**</span><span class="sxs-lookup"><span data-stu-id="d800b-120">In the **Task** window that opens, go to the **General** tab. Under **Security options** click **Change User or Group** and type SYSTEM and then click **Check Names** then **OK**.</span></span> <span data-ttu-id="d800b-121">NT AUTHORITY\SYSTEM wordt weergegeven als het gebruikersaccount dat de taak als wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="d800b-121">NT AUTHORITY\SYSTEM appears as the user account the task will run as.</span></span>

10. <span data-ttu-id="d800b-122">Schakel **Uitvoeren in of de gebruiker al** dan niet is aangemeld en schakel het selectievakje Uitvoeren met hoogste **bevoegdheden** in.</span><span class="sxs-lookup"><span data-stu-id="d800b-122">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check box.</span></span>

11. <span data-ttu-id="d800b-123">Ga naar het **tabblad Acties** en klik op **Nieuw...** Zorg ervoor **dat Een programma starten** is geselecteerd in het **veld** Actie.</span><span class="sxs-lookup"><span data-stu-id="d800b-123">Go to the **Actions** tab and click **New...** Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="d800b-124">Voer de bestandsnaam en locatie in van het gedeelde *WindowsDefenderATPOnboardingScript.cmd-bestand.*</span><span class="sxs-lookup"><span data-stu-id="d800b-124">Enter the file name and location of the shared *WindowsDefenderATPOnboardingScript.cmd* file.</span></span>

12. <span data-ttu-id="d800b-125">Klik **op OK** en sluit alle geopende GPMC-vensters.</span><span class="sxs-lookup"><span data-stu-id="d800b-125">Click **OK** and close any open GPMC windows.</span></span>


## <a name="offboard-devices-using-group-policy"></a><span data-ttu-id="d800b-126">Offboard-apparaten met groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="d800b-126">Offboard devices using Group Policy</span></span>
<span data-ttu-id="d800b-127">Om veiligheidsredenen verloopt het pakket dat wordt gebruikt voor Offboard-apparaten 30 dagen na de datum waarop het is gedownload.</span><span class="sxs-lookup"><span data-stu-id="d800b-127">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="d800b-128">Verlopen offboarding-pakketten die naar een apparaat zijn verzonden, worden geweigerd.</span><span class="sxs-lookup"><span data-stu-id="d800b-128">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="d800b-129">Wanneer u een offboarding-pakket downloadt, wordt u op de hoogte gesteld van de vervaldatum van de pakketten en wordt het ook opgenomen in de pakketnaam.</span><span class="sxs-lookup"><span data-stu-id="d800b-129">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="d800b-130">Onboarding- en offboarding-beleid mag niet tegelijkertijd op hetzelfde apparaat worden geïmplementeerd, anders veroorzaakt dit onvoorspelbare botsingen.</span><span class="sxs-lookup"><span data-stu-id="d800b-130">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="d800b-131">Haal het offboarding-pakket op in [het Microsoft Compliance Center.](https://compliance.microsoft.com/compliancesettings/deviceonboarding)</span><span class="sxs-lookup"><span data-stu-id="d800b-131">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com/compliancesettings/deviceonboarding).</span></span>

2. <span data-ttu-id="d800b-132">Selecteer in het navigatiedeelvenster **Instellingen**  >  **/Device onboarding**  >  **Offboarding**.</span><span class="sxs-lookup"><span data-stu-id="d800b-132">In the navigation pane, select **Settings** > **//Device onboarding** > **Offboarding**.</span></span>

3. <span data-ttu-id="d800b-133">Selecteer groepsbeleid in **het veld** **Implementatiemethode.**</span><span class="sxs-lookup"><span data-stu-id="d800b-133">In the **Deployment method** field, select **Group policy**.</span></span>

4. <span data-ttu-id="d800b-134">Klik **op Pakket downloaden** en sla het .zip op.</span><span class="sxs-lookup"><span data-stu-id="d800b-134">Click **Download package** and save the .zip file.</span></span>

5. <span data-ttu-id="d800b-135">Haal de inhoud van het .zip naar een gedeelde, alleen-lezen locatie die toegankelijk is voor het apparaat.</span><span class="sxs-lookup"><span data-stu-id="d800b-135">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="d800b-136">U moet een bestand met de naam *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd* hebben.</span><span class="sxs-lookup"><span data-stu-id="d800b-136">You should have a file named *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span></span>

6. <span data-ttu-id="d800b-137">Open de GPMC (Group [Policy Management Console),](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en klik op **Bewerken.**</span><span class="sxs-lookup"><span data-stu-id="d800b-137">Open the [Group Policy Management Console](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>

7. <span data-ttu-id="d800b-138">Ga in **de Editor voor groepsbeleidsbeheer** naar **Computerconfiguratie,** vervolgens **Voorkeuren** en vervolgens **naar Configuratiescherminstellingen.**</span><span class="sxs-lookup"><span data-stu-id="d800b-138">In the **Group Policy Management Editor**, go to **Computer configuration,** then **Preferences**, and then **Control panel settings**.</span></span>

8. <span data-ttu-id="d800b-139">Klik met de rechtermuisknop **op Geplande taken,** wijs **Nieuw** aan en klik vervolgens op **Onmiddellijke taak.**</span><span class="sxs-lookup"><span data-stu-id="d800b-139">Right-click **Scheduled tasks**, point to **New**, and then click **Immediate task**.</span></span>

9. <span data-ttu-id="d800b-140">Ga in **het** venster Taak dat wordt geopend naar het **tabblad** Algemeen. Kies het lokale SYSTEEM-gebruikersaccount (BUILTIN\SYSTEM) onder **Beveiligingsopties.**</span><span class="sxs-lookup"><span data-stu-id="d800b-140">In the **Task** window that opens, go to the **General** tab. Choose the local SYSTEM user account (BUILTIN\SYSTEM) under **Security options**.</span></span>

10. <span data-ttu-id="d800b-141">Schakel **Uitvoeren in of de gebruiker al** dan niet is aangemeld en schakel het selectievakje Uitvoeren met hoogste **bevoegdheden** in.</span><span class="sxs-lookup"><span data-stu-id="d800b-141">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check-box.</span></span>

11. <span data-ttu-id="d800b-142">Ga naar het **tabblad Acties** en klik op **Nieuw...**. Zorg ervoor **dat Een programma starten** is geselecteerd in het **veld** Actie.</span><span class="sxs-lookup"><span data-stu-id="d800b-142">Go to the **Actions** tab and click **New...**. Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="d800b-143">Voer de bestandsnaam en de locatie van het gedeelde  *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd-bestand* in.</span><span class="sxs-lookup"><span data-stu-id="d800b-143">Enter the file name and location of the shared  *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd* file.</span></span>

12. <span data-ttu-id="d800b-144">Klik **op OK** en sluit alle geopende GPMC-vensters.</span><span class="sxs-lookup"><span data-stu-id="d800b-144">Click **OK** and close any open GPMC windows.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d800b-145">Offboarding zorgt ervoor dat het apparaat stopt met het verzenden van sensorgegevens naar de portal, maar gegevens van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="d800b-145">Offboarding causes the device to stop sending sensor data to the portal but data from the device.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="d800b-146">Apparaatconfiguratie controleren</span><span class="sxs-lookup"><span data-stu-id="d800b-146">Monitor device configuration</span></span>
<span data-ttu-id="d800b-147">Met Groepsbeleid is er geen optie om de implementatie van beleidsregels op de apparaten te controleren.</span><span class="sxs-lookup"><span data-stu-id="d800b-147">With Group Policy there isn’t an option to monitor deployment of policies on the devices.</span></span> <span data-ttu-id="d800b-148">Monitoring kan rechtstreeks in de portal of met behulp van de verschillende implementatiehulpmiddelen worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="d800b-148">Monitoring can be done directly on the portal, or by using the different deployment tools.</span></span>

## <a name="monitor-devices-using-the-portal"></a><span data-ttu-id="d800b-149">Apparaten controleren met behulp van de portal</span><span class="sxs-lookup"><span data-stu-id="d800b-149">Monitor devices using the portal</span></span>
1. <span data-ttu-id="d800b-150">Ga naar [Microsoft Compliance Center.](https://compliance.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="d800b-150">Go to [Microsoft Compliance center](https://compliance.microsoft.com/).</span></span>
2. <span data-ttu-id="d800b-151">Klik **op De lijst** Apparaten.</span><span class="sxs-lookup"><span data-stu-id="d800b-151">Click **Devices** list.</span></span>
3. <span data-ttu-id="d800b-152">Controleer of apparaten worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="d800b-152">Verify that devices are appearing.</span></span>

> [!NOTE]
> <span data-ttu-id="d800b-153">Het kan enkele dagen duren voordat apparaten worden weergegeven in de **lijst Apparaten.**</span><span class="sxs-lookup"><span data-stu-id="d800b-153">It can take several days for devices to start showing on the **Devices list**.</span></span> <span data-ttu-id="d800b-154">Dit omvat de tijd die nodig is voor de distributie van het beleid naar het apparaat, de tijd die nodig is voordat de gebruiker zich aanmeldt en de tijd die nodig is voor het eindpunt om te beginnen met rapporteren.</span><span class="sxs-lookup"><span data-stu-id="d800b-154">This includes the time it takes for the policies to be distributed to the device, the time it takes before the user logs on, and the time it takes for the endpoint to start reporting.</span></span>


## <a name="related-topics"></a><span data-ttu-id="d800b-155">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="d800b-155">Related topics</span></span>
- [<span data-ttu-id="d800b-156">Onboard Windows 10 apparaten met Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="d800b-156">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="d800b-157">Onboarden Windows 10-apparaten met hulpmiddelen voor Mobile Device Management</span><span class="sxs-lookup"><span data-stu-id="d800b-157">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="d800b-158">Onboarden Windows 10-apparaten met een lokaal script</span><span class="sxs-lookup"><span data-stu-id="d800b-158">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="d800b-159">Onboarden niet-permanente virtual desktop infrastructure (VDI)-apparaten</span><span class="sxs-lookup"><span data-stu-id="d800b-159">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="d800b-160">Een detectietest uitvoeren op een nieuw ingebouwde Microsoft Defender voor eindpuntapparaten</span><span class="sxs-lookup"><span data-stu-id="d800b-160">Run a detection test on a newly onboarded Microsoft Defender for Endpoint devices</span></span>](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [<span data-ttu-id="d800b-161">Problemen met Microsoft Defender Advanced Threat Protection onboarding oplossen</span><span class="sxs-lookup"><span data-stu-id="d800b-161">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)