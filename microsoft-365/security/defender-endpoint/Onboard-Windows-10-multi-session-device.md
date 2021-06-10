---
title: Onboarden Windows 10 multi-sessie apparaten in Windows Virtual Desktop (Virtuele bureaubladversie)
description: Lees meer in dit artikel over Onboarding Windows 10 multi-session devices in Windows Virtual Desktop
keywords: Windows Virtual Desktop, WVD, microsoft defender, eindpunt, onboard
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
ms.topic: article
author: dansimp
ms.author: dansimp
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: 5bf9f856e93ae1424373a917490a264c04e07feb
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861177"
---
# <a name="onboard-windows-10-multi-session-devices-in-windows-virtual-desktop"></a><span data-ttu-id="73780-104">Onboarden Windows 10 multi-sessie apparaten in Windows Virtual Desktop (Virtuele bureaubladversie)</span><span class="sxs-lookup"><span data-stu-id="73780-104">Onboard Windows 10 multi-session devices in Windows Virtual Desktop</span></span> 
<span data-ttu-id="73780-105">6 minuten om te lezen</span><span class="sxs-lookup"><span data-stu-id="73780-105">6 minutes to read</span></span> 

<span data-ttu-id="73780-106">Van toepassing op:</span><span class="sxs-lookup"><span data-stu-id="73780-106">Applies to:</span></span> 
- <span data-ttu-id="73780-107">Windows 10 multi-session running on Windows Virtual Desktop (WVD)</span><span class="sxs-lookup"><span data-stu-id="73780-107">Windows 10 multi-session running on Windows Virtual Desktop (WVD)</span></span> 

<span data-ttu-id="73780-108">Microsoft Defender voor Eindpunt ondersteunt het controleren van VDI- en Windows Virtual Desktop-sessies.</span><span class="sxs-lookup"><span data-stu-id="73780-108">Microsoft Defender for Endpoint supports monitoring both VDI and Windows Virtual Desktop sessions.</span></span> <span data-ttu-id="73780-109">Afhankelijk van de behoeften van uw organisatie, moet u mogelijk VDI- of Windows Virtual Desktop-sessies implementeren om uw werknemers toegang te geven tot bedrijfsgegevens en -apps vanaf een niet-beheerd apparaat, externe locatie of vergelijkbaar scenario.</span><span class="sxs-lookup"><span data-stu-id="73780-109">Depending on your organization's needs, you might need to implement VDI or Windows Virtual Desktop sessions to help your employees access corporate data and apps from an unmanaged device, remote location, or similar scenario.</span></span> <span data-ttu-id="73780-110">Met Microsoft Defender voor Eindpunt kunt u deze virtuele machines controleren op afwijkende activiteiten.</span><span class="sxs-lookup"><span data-stu-id="73780-110">With Microsoft Defender for Endpoint, you can monitor these virtual machines for anomalous activity.</span></span>

 ## <a name="before-you-begin"></a><span data-ttu-id="73780-111">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="73780-111">Before you begin</span></span>
<span data-ttu-id="73780-112">Vertrouwd raken met de [overwegingen voor niet-permanente VDI.](/microsoft-365/security/defender-endpoint/configure-endpoints-vdi#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1)</span><span class="sxs-lookup"><span data-stu-id="73780-112">Familiarize yourself with the [considerations for non-persistent VDI](/microsoft-365/security/defender-endpoint/configure-endpoints-vdi#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1).</span></span> <span data-ttu-id="73780-113">Hoewel [Windows Virtual Desktop](/azure/virtual-desktop/overview) geen niet-persistente opties biedt, biedt het wel manieren om een gouden Windows-afbeelding te gebruiken die kan worden gebruikt voor het inrichten van nieuwe hosts en herdeploy-machines.</span><span class="sxs-lookup"><span data-stu-id="73780-113">While [Windows Virtual Desktop](/azure/virtual-desktop/overview) doesn't provide non-persistence options, it does provide ways to use a golden Windows image that can be used to provision new hosts and redeploy machines.</span></span> <span data-ttu-id="73780-114">Dit verhoogt de vluchtigheid in de omgeving en is dus van invloed op de items die worden gemaakt en onderhouden in de Microsoft Defender for Endpoint-portal, waardoor de zichtbaarheid voor uw beveiligingsanalisten mogelijk wordt verkleind.</span><span class="sxs-lookup"><span data-stu-id="73780-114">This increases volatility in the environment and thus impacts what entries are created and maintained in the Microsoft Defender for Endpoint portal, potentially reducing visibility for your security analysts.</span></span>

> [!NOTE]
> <span data-ttu-id="73780-115">Afhankelijk van de keuze van de onboarding-methode, kunnen apparaten als een van beide worden weergegeven in de Microsoft Defender voor Endpoint-portal:</span><span class="sxs-lookup"><span data-stu-id="73780-115">Depending on your choice of onboarding method, devices can appear in Microsoft Defender for Endpoint portal as either:</span></span> 
> - <span data-ttu-id="73780-116">Eén invoer voor elk virtueel bureaublad</span><span class="sxs-lookup"><span data-stu-id="73780-116">Single entry for each virtual desktop</span></span> 
> - <span data-ttu-id="73780-117">Meerdere items voor elk virtueel bureaublad</span><span class="sxs-lookup"><span data-stu-id="73780-117">Multiple entries for each virtual desktop</span></span> 

<span data-ttu-id="73780-118">Microsoft raadt onboarding Windows Virtual Desktop aan als één item per virtueel bureaublad.</span><span class="sxs-lookup"><span data-stu-id="73780-118">Microsoft recommends onboarding Windows Virtual Desktop as a single entry per virtual desktop.</span></span> <span data-ttu-id="73780-119">Dit zorgt ervoor dat de onderzoekservaring in de Microsoft Defender Endpoint-portal binnen de context van één apparaat valt op basis van de computernaam.</span><span class="sxs-lookup"><span data-stu-id="73780-119">This ensures that the investigation experience in the Microsoft Defender Endpoint portal is in the context of one device based on the machine name.</span></span> <span data-ttu-id="73780-120">Organisaties die vaak WVD-hosts verwijderen en opnieuw deployeren, moeten deze methode sterk overwegen omdat hiermee wordt voorkomen dat meerdere objecten voor dezelfde computer worden gemaakt in de Microsoft Defender voor Eindpunt-portal.</span><span class="sxs-lookup"><span data-stu-id="73780-120">Organizations that frequently delete and redeploy WVD hosts should strongly consider using this method as it prevents multiple objects for the same machine from being created in the Microsoft Defender for Endpoint portal.</span></span> <span data-ttu-id="73780-121">Dit kan leiden tot verwarring bij het onderzoeken van incidenten.</span><span class="sxs-lookup"><span data-stu-id="73780-121">This can lead to confusion when investigating incidents.</span></span> <span data-ttu-id="73780-122">Voor test- of niet-vluchtige omgevingen kunt u ervoor kiezen om anders te kiezen.</span><span class="sxs-lookup"><span data-stu-id="73780-122">For test or non-volatile environments, you may opt to choose differently.</span></span> 

<span data-ttu-id="73780-123">Microsoft raadt aan het onboardingscript van Microsoft Defender voor eindpunt toe te voegen aan de gouden afbeelding van WVD.</span><span class="sxs-lookup"><span data-stu-id="73780-123">Microsoft recommends adding the Microsoft Defender for Endpoint onboarding script to the WVD golden image.</span></span> <span data-ttu-id="73780-124">Op deze manier kunt u er zeker van zijn dat dit onboarding-script direct bij het opstarten wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="73780-124">This way, you can be sure that this onboarding script runs immediately at first boot.</span></span> <span data-ttu-id="73780-125">Het wordt uitgevoerd als een opstartscript bij het opstarten op alle WVD-machines die zijn ingericht vanuit de gouden afbeelding van WVD.</span><span class="sxs-lookup"><span data-stu-id="73780-125">It's executed as a startup script at first boot on all the WVD machines that are provisioned from the WVD golden image.</span></span> <span data-ttu-id="73780-126">Als u echter een van de galerieafbeeldingen zonder wijziging gebruikt, zet u het script op een gedeelde locatie en belt u het vanuit lokaal of domeingroepsbeleid.</span><span class="sxs-lookup"><span data-stu-id="73780-126">However, if you're using one of the gallery images without modification, place the script in a shared location and call it from either local or domain group policy.</span></span> 

> [!NOTE]
> <span data-ttu-id="73780-127">De plaatsing en configuratie van het VDI onboarding-opstartscript op de gouden afbeelding van WVD configureert het script als een opstartscript dat wordt uitgevoerd wanneer de WVD wordt gestart.</span><span class="sxs-lookup"><span data-stu-id="73780-127">The placement and configuration of the VDI onboarding startup script on the WVD golden image configures it as a startup script that runs when the WVD starts.</span></span> <span data-ttu-id="73780-128">Het is NIET raadzaam om de werkelijke gouden afbeelding van WVD aan te boord te nemen.</span><span class="sxs-lookup"><span data-stu-id="73780-128">It's NOT recommended to onboard the actual WVD golden image.</span></span> <span data-ttu-id="73780-129">Een andere overweging is de methode die wordt gebruikt om het script uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="73780-129">Another consideration is the method used to run the script.</span></span> <span data-ttu-id="73780-130">Het moet zo vroeg mogelijk in het opstart-/inrichtingsproces worden uitgevoerd om de tijd tussen de machine die beschikbaar is voor het ontvangen van sessies en de onboarding van het apparaat bij de service te verminderen.</span><span class="sxs-lookup"><span data-stu-id="73780-130">It should run as early in the startup/provisioning process as possible to reduce the time between the machine being available to receive sessions and the device onboarding to the service.</span></span> <span data-ttu-id="73780-131">In onderstaande scenario'& 2 wordt hiermee rekening gehouden.</span><span class="sxs-lookup"><span data-stu-id="73780-131">Below scenarios 1 & 2 take this into account.</span></span>

### <a name="scenarios"></a><span data-ttu-id="73780-132">Scenario's</span><span class="sxs-lookup"><span data-stu-id="73780-132">Scenarios</span></span>
<span data-ttu-id="73780-133">Er zijn verschillende manieren om een WVD-hostcomputer aan te boord te nemen:</span><span class="sxs-lookup"><span data-stu-id="73780-133">There are several ways to onboard a WVD host machine:</span></span>

- <span data-ttu-id="73780-134">Voer het script uit in de gouden afbeelding (of vanaf een gedeelde locatie) tijdens het opstarten.</span><span class="sxs-lookup"><span data-stu-id="73780-134">Run the script in the golden image (or from a shared location) during startup.</span></span>
- <span data-ttu-id="73780-135">Gebruik een beheerhulpmiddel om het script uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="73780-135">Use a management tool to run the script.</span></span>

#### <a name="scenario-1-using-local-group-policy"></a><span data-ttu-id="73780-136">*Scenario 1: Lokaal groepsbeleid gebruiken*</span><span class="sxs-lookup"><span data-stu-id="73780-136">*Scenario 1: Using local group policy*</span></span>
<span data-ttu-id="73780-137">In dit scenario moet het script in een gouden afbeelding worden geplaatst en wordt lokaal groepsbeleid gebruikt om het begin van het opstartproces uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="73780-137">This scenario requires placing the script in a golden image and uses local group policy to run early in the boot process.</span></span>

<span data-ttu-id="73780-138">Gebruik de instructies in [VDI-apparaten met niet-permanente virtuele bureaubladinfrastructuur](configure-endpoints-vdi.md#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1)aan boord.</span><span class="sxs-lookup"><span data-stu-id="73780-138">Use the instructions in [Onboard non-persistent virtual desktop infrastructure VDI devices](configure-endpoints-vdi.md#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1).</span></span>

<span data-ttu-id="73780-139">Volg de instructies voor één vermelding voor elk apparaat.</span><span class="sxs-lookup"><span data-stu-id="73780-139">Follow the instructions for a single entry for each device.</span></span>

#### <a name="scenario-2-using-domain-group-policy"></a><span data-ttu-id="73780-140">*Scenario 2: Domeingroepsbeleid gebruiken*</span><span class="sxs-lookup"><span data-stu-id="73780-140">*Scenario 2: Using domain group policy*</span></span>
<span data-ttu-id="73780-141">In dit scenario wordt een centraal gelegen script gebruikt en wordt het uitgevoerd met een groepsbeleid op basis van een domein.</span><span class="sxs-lookup"><span data-stu-id="73780-141">This scenario uses a centrally located script and runs it using a domain-based group policy.</span></span> <span data-ttu-id="73780-142">U kunt het script ook in de gouden afbeelding plaatsen en op dezelfde manier uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="73780-142">You can also place the script in the golden image and run it in the same way.</span></span>

<span data-ttu-id="73780-143">**Het WindowsDefenderATPOnboardingPackage.zip downloaden van het Windows Defender beveiligingscentrum**</span><span class="sxs-lookup"><span data-stu-id="73780-143">**Download the WindowsDefenderATPOnboardingPackage.zip file from the Windows Defender Security Center**</span></span>

1. <span data-ttu-id="73780-144">Het VDI-configuratiepakket .zip bestand (WindowsDefenderATPOnboardingPackage.zip)</span><span class="sxs-lookup"><span data-stu-id="73780-144">Open the VDI configuration package .zip file (WindowsDefenderATPOnboardingPackage.zip)</span></span>  

    1. <span data-ttu-id="73780-145">Selecteer in Microsoft Defender-beveiligingscentrum navigatiedeelvenster **Instellingen**  >  **Onboarding.**</span><span class="sxs-lookup"><span data-stu-id="73780-145">In the Microsoft Defender Security Center navigation pane, select **Settings** > **Onboarding**.</span></span> 
    1. <span data-ttu-id="73780-146">Selecteer Windows 10 als het besturingssysteem.</span><span class="sxs-lookup"><span data-stu-id="73780-146">Select Windows 10 as the operating system.</span></span> 
    1. <span data-ttu-id="73780-147">Selecteer in **het veld** Implementatiemethode VDI-onboarding-scripts voor niet-permanente eindpunten.</span><span class="sxs-lookup"><span data-stu-id="73780-147">In the **Deployment method** field, select VDI onboarding scripts for non-persistent endpoints.</span></span> 
    1. <span data-ttu-id="73780-148">Klik **op Pakket downloaden** en sla het .zip op.</span><span class="sxs-lookup"><span data-stu-id="73780-148">Click **Download package** and save the .zip file.</span></span> 

2. <span data-ttu-id="73780-149">Haal de inhoud van het .zip naar een gedeelde, alleen-lezen locatie die toegankelijk is voor het apparaat.</span><span class="sxs-lookup"><span data-stu-id="73780-149">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="73780-150">U hebt een map met de naam **OptionalParamsPolicy** en de bestanden **WindowsDefenderATPOnboardingScript.cmd** en **Onboard-NonPersistentMachine.ps1.**</span><span class="sxs-lookup"><span data-stu-id="73780-150">You should have a folder called **OptionalParamsPolicy** and the files **WindowsDefenderATPOnboardingScript.cmd** and **Onboard-NonPersistentMachine.ps1**.</span></span>

<span data-ttu-id="73780-151">**Groepsbeleidsbeheerconsole gebruiken om het script uit te voeren wanneer de virtuele machine wordt gestart**</span><span class="sxs-lookup"><span data-stu-id="73780-151">**Use Group Policy management console to run the script when the virtual machine starts**</span></span>

1. <span data-ttu-id="73780-152">Open de GPMC (Group Policy Management Console), klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en klik op **Bewerken.**</span><span class="sxs-lookup"><span data-stu-id="73780-152">Open the Group Policy Management Console (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="73780-153">Ga in de Editor voor groepsbeleidsbeheer naar Instellingen van het **Configuratiescherm voor** \>  \> **computerconfiguratie**.</span><span class="sxs-lookup"><span data-stu-id="73780-153">In the Group Policy Management Editor, go to **Computer configuration** \> **Preferences** \> **Control panel settings**.</span></span> 

3. <span data-ttu-id="73780-154">Klik met de rechtermuisknop **op Geplande taken,** klik op **Nieuw** en klik vervolgens op **Onmiddellijke taak** (ten minste Windows 7).</span><span class="sxs-lookup"><span data-stu-id="73780-154">Right-click **Scheduled tasks**, click **New**, and then click **Immediate Task** (At least Windows 7).</span></span> 

4. <span data-ttu-id="73780-155">Ga in het venster Taak dat wordt geopend naar het **tabblad** Algemeen. Klik **onder Beveiligingsopties** **op Gebruiker of Groep wijzigen en** typ SYSTEEM.</span><span class="sxs-lookup"><span data-stu-id="73780-155">In the Task window that opens, go to the **General** tab. Under **Security options** click **Change User or Group** and type SYSTEM.</span></span> <span data-ttu-id="73780-156">Klik **op Namen controleren** en klik vervolgens op OK.</span><span class="sxs-lookup"><span data-stu-id="73780-156">Click **Check Names** and then click OK.</span></span> <span data-ttu-id="73780-157">NT AUTHORITY\SYSTEM wordt weergegeven als het gebruikersaccount dat de taak als wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="73780-157">NT AUTHORITY\SYSTEM appears as the user account the task will run as.</span></span> 

5. <span data-ttu-id="73780-158">Schakel **Uitvoeren in of de gebruiker al** dan niet is aangemeld en schakel het selectievakje Uitvoeren met hoogste **bevoegdheden** in.</span><span class="sxs-lookup"><span data-stu-id="73780-158">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check box.</span></span> 

6. <span data-ttu-id="73780-159">Ga naar het **tabblad Acties** en klik op **Nieuw.**</span><span class="sxs-lookup"><span data-stu-id="73780-159">Go to the **Actions** tab and click **New**.</span></span> <span data-ttu-id="73780-160">Zorg ervoor **dat Een programma starten** is geselecteerd in het veld Actie.</span><span class="sxs-lookup"><span data-stu-id="73780-160">Ensure that **Start a program** is selected in the Action field.</span></span> <span data-ttu-id="73780-161">Voer het volgende in:</span><span class="sxs-lookup"><span data-stu-id="73780-161">Enter the following:</span></span> 

   `Action = "Start a program"`

   `Program/Script = C:\WINDOWS\system32\WindowsPowerShell\v1.0\powershell.exe`

   `Add Arguments (optional) = -ExecutionPolicy Bypass -command "& \\Path\To\Onboard-NonPersistentMachine.ps1"`

   <span data-ttu-id="73780-162">Selecteer vervolgens **OK** en sluit alle geopende GPMC-vensters.</span><span class="sxs-lookup"><span data-stu-id="73780-162">Then select **OK** and close any open GPMC windows.</span></span>

#### <a name="scenario-3-onboarding-using-management-tools"></a><span data-ttu-id="73780-163">*Scenario 3: Onboarding met behulp van beheerhulpmiddelen*</span><span class="sxs-lookup"><span data-stu-id="73780-163">*Scenario 3: Onboarding using management tools*</span></span>

<span data-ttu-id="73780-164">Als u van plan bent om uw machines te beheren met behulp van een beheerhulpmiddel, kunt u apparaten met een Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="73780-164">If you plan to manage your machines using a management tool, you can onboard devices with Microsoft Endpoint Configuration Manager.</span></span>

<span data-ttu-id="73780-165">Zie Onboard Windows 10 met Configuration Manager voor [meer informatie.](configure-endpoints-sccm.md)</span><span class="sxs-lookup"><span data-stu-id="73780-165">For more information, see [Onboard Windows 10 devices using Configuration Manager](configure-endpoints-sccm.md).</span></span>

> [!WARNING]
> <span data-ttu-id="73780-166">Als u van plan bent om [Attack Surface-beperkingsregels](attack-surface-reduction.md)te gebruiken, moet u de regel 'Procescreaties blokkeren die afkomstig zijn van[PSExec-](attack-surface-reduction.md#block-process-creations-originating-from-psexec-and-wmi-commands)en WMI-opdrachten' niet gebruiken, omdat deze regel niet compatibel is met het beheer via Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="73780-166">If you plan to use [Attack Surface reduction Rules](attack-surface-reduction.md), note that the rule “[Block process creations originating from PSExec and WMI commands](attack-surface-reduction.md#block-process-creations-originating-from-psexec-and-wmi-commands)" should not be used, because that rule is incompatible with management through Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="73780-167">De regel blokkeert WMI-opdrachten die door de Configuration Manager-client worden gebruikt om correct te werken.</span><span class="sxs-lookup"><span data-stu-id="73780-167">The rule blocks WMI commands that the Configuration Manager client uses to function correctly.</span></span> 

> [!TIP]
> <span data-ttu-id="73780-168">Nadat u het apparaat hebt onboarding, kunt u ervoor kiezen om een detectietest uit te voeren om te controleren of het apparaat correct is aan boord van de service.</span><span class="sxs-lookup"><span data-stu-id="73780-168">After onboarding the device, you can choose to run a detection test to verify that the device is properly onboarded to the service.</span></span> <span data-ttu-id="73780-169">Zie Een detectietest uitvoeren op een nieuw ingebouwde [Microsoft Defender voor eindpuntapparaat](run-detection-test.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="73780-169">For more information, see [Run a detection test on a newly onboarded Microsoft Defender for Endpoint device](run-detection-test.md).</span></span> 

#### <a name="tagging-your-machines-when-building-your-golden-image"></a><span data-ttu-id="73780-170">Uw machines labelen bij het maken van uw gouden afbeelding</span><span class="sxs-lookup"><span data-stu-id="73780-170">Tagging your machines when building your golden image</span></span> 

<span data-ttu-id="73780-171">Als onderdeel van uw onboarding kunt u overwegen om een machinelabel in te stellen om WVD-machines gemakkelijker van elkaar te onderscheiden in het Microsoft-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="73780-171">As part of your onboarding, you may want to consider setting a machine tag to can differentiate WVD machines more easily in the Microsoft Security Center.</span></span> <span data-ttu-id="73780-172">Zie Apparaatlabels toevoegen door een registersleutelwaarde in te stellen voor [meer informatie.](machine-tags.md#add-device-tags-by-setting-a-registry-key-value)</span><span class="sxs-lookup"><span data-stu-id="73780-172">For more information, see [Add device tags by setting a registry key value](machine-tags.md#add-device-tags-by-setting-a-registry-key-value).</span></span> 

#### <a name="other-recommended-configuration-settings"></a><span data-ttu-id="73780-173">Andere aanbevolen configuratie-instellingen</span><span class="sxs-lookup"><span data-stu-id="73780-173">Other recommended configuration settings</span></span> 

<span data-ttu-id="73780-174">Wanneer u een gouden afbeelding opbouwt, wilt u mogelijk ook de eerste beveiligingsinstellingen configureren.</span><span class="sxs-lookup"><span data-stu-id="73780-174">When building your golden image, you may want to configure initial protection settings as well.</span></span> <span data-ttu-id="73780-175">Zie Overige aanbevolen [configuratie-instellingen voor meer informatie.](configure-endpoints-gp.md#other-recommended-configuration-settings)</span><span class="sxs-lookup"><span data-stu-id="73780-175">For more information, see [Other recommended configuration settings](configure-endpoints-gp.md#other-recommended-configuration-settings).</span></span> 

<span data-ttu-id="73780-176">Als u FSlogix-gebruikersprofielen gebruikt, raden we u aan de volgende bestanden uit te sluiten van de always-on-beveiliging:</span><span class="sxs-lookup"><span data-stu-id="73780-176">Also, if you're using FSlogix user profiles, we recommend you exclude the following files from always-on protection:</span></span> 

<span data-ttu-id="73780-177">**Bestanden uitsluiten:**</span><span class="sxs-lookup"><span data-stu-id="73780-177">**Exclude Files:**</span></span> 

`%ProgramFiles%\FSLogix\Apps\frxdrv.sys`

`%ProgramFiles%\FSLogix\Apps\frxdrvvt.sys`

`%ProgramFiles%\FSLogix\Apps\frxccd.sys`

`%TEMP%\*.VHD`

`%TEMP%\*.VHDX`

`%Windir%\TEMP\*.VHD`

`%Windir%\TEMP\*.VHDX`

`\\storageaccount.file.core.windows.net\share\*\*.VHD`

`\\storageaccount.file.core.windows.net\share\*\*.VHDX`

<span data-ttu-id="73780-178">**Processen uitsluiten:**</span><span class="sxs-lookup"><span data-stu-id="73780-178">**Exclude Processes:**</span></span>

`%ProgramFiles%\FSLogix\Apps\frxccd.exe`

`%ProgramFiles%\FSLogix\Apps\frxccds.exe`

`%ProgramFiles%\FSLogix\Apps\frxsvc.exe`

#### <a name="licensing-requirements"></a><span data-ttu-id="73780-179">Licentievereisten</span><span class="sxs-lookup"><span data-stu-id="73780-179">Licensing requirements</span></span> 

<span data-ttu-id="73780-180">Opmerking over licenties: Wanneer u Windows 10 Enterprise meerdere sessies gebruikt, afhankelijk van uw vereisten, kunt u ervoor kiezen om alle gebruikers een licentie te geven via Microsoft Defender voor Eindpunt (per gebruiker), Windows Enterprise E5, Microsoft 365 Security of Microsoft 365 E5, of om de VM te laten gelicentieerd via Azure Defender.</span><span class="sxs-lookup"><span data-stu-id="73780-180">Note on licensing: When using Windows 10 Enterprise multi-session, depending on your requirements, you can choose to either have all users licensed through Microsoft Defender for Endpoint (per user), Windows Enterprise E5, Microsoft 365 Security, or Microsoft 365 E5, or have the VM licensed through Azure Defender.</span></span>
<span data-ttu-id="73780-181">Licentievereisten voor Microsoft Defender voor eindpunten vindt u op: [Licentievereisten.](minimum-requirements.md#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="73780-181">Licensing requirements for Microsoft Defender for endpoint can be found at: [Licensing requirements](minimum-requirements.md#licensing-requirements).</span></span>

#### <a name="related-links"></a><span data-ttu-id="73780-182">Gerelateerde koppelingen</span><span class="sxs-lookup"><span data-stu-id="73780-182">Related Links</span></span>

[<span data-ttu-id="73780-183">Uitsluitingen voor Microsoft Defender toevoegen met PowerShell</span><span class="sxs-lookup"><span data-stu-id="73780-183">Add exclusions for Microsoft Defender by using PowerShell</span></span>](/azure/architecture/example-scenario/wvd/windows-virtual-desktop-fslogix#add-exclusions-for-windows-defender-by-using-powershell)
