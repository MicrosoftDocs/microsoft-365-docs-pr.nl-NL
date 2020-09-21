---
title: Bestaande apparaten zelf registreren
description: Hergebruikte apparaten registreren u hebt mogelijk al een nieuwe versie van Microsoft die door Microsoft worden beheerd
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 6c241894ab50b6b1341b06f47c107c8945fb6e8c
ms.sourcegitcommit: adaedd1418a3bd6e4875b77fd9e008b47e0b2a51
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/18/2020
ms.locfileid: "48104568"
---
# <a name="register-existing-devices-yourself"></a><span data-ttu-id="dd05a-103">Bestaande apparaten zelf registreren</span><span class="sxs-lookup"><span data-stu-id="dd05a-103">Register existing devices yourself</span></span>

>[!NOTE]
><span data-ttu-id="dd05a-104">In dit onderwerp worden de stappen beschreven die u moet uitvoeren om apparaten die u al hebt, opnieuw te gebruiken en deze te registreren in Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="dd05a-104">This topic describes the steps for you to re-use devices you already have and register them in Microsoft Managed Desktop.</span></span> <span data-ttu-id="dd05a-105">Als u werkt met merk-nieuwe apparaten, volgt u de stappen in [nieuwe apparaten registreren in Microsoft Managed Desktop](register-devices-self.md) .</span><span class="sxs-lookup"><span data-stu-id="dd05a-105">If you are working with brand-new devices, follow the steps in [Register new devices in Microsoft Managed Desktop yourself](register-devices-self.md) instead.</span></span>

<span data-ttu-id="dd05a-106">Het proces voor partners wordt gedocumenteerd in [stappen voor partners om apparaten te registreren](register-devices-partner.md).</span><span class="sxs-lookup"><span data-stu-id="dd05a-106">The process for Partners is documented in [Steps for Partners to register devices](register-devices-partner.md).</span></span>

<span data-ttu-id="dd05a-107">Microsoft Managed Desktop kan met gloednieuwe apparaten werken, maar u kunt ook apparaten die u al hebt, opnieuw gebruiken (welke u de afbeelding opnieuw moet maken.</span><span class="sxs-lookup"><span data-stu-id="dd05a-107">Microsoft Managed Desktop can work with brand-new devices or you can re-use devices you might already have (which will require that you re-image them).</span></span> <span data-ttu-id="dd05a-108">U kunt apparaten registreren met Microsoft Managed desktop in de portal van Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="dd05a-108">You can register devices with Microsoft Managed Desktop in the Microsoft Endpoint Manager portal.</span></span>

## <a name="prepare-to-register-existing-devices"></a><span data-ttu-id="dd05a-109">Voorbereidingen treffen om bestaande apparaten te registreren</span><span class="sxs-lookup"><span data-stu-id="dd05a-109">Prepare to register existing devices</span></span>


<span data-ttu-id="dd05a-110">Voer de volgende stappen uit als u bestaande apparaten wilt registreren:</span><span class="sxs-lookup"><span data-stu-id="dd05a-110">To register existing devices, follow these steps:</span></span>

1. [<span data-ttu-id="dd05a-111">De hardware-hash voor elk apparaat verkrijgen.</span><span class="sxs-lookup"><span data-stu-id="dd05a-111">Obtain the hardware hash for each device.</span></span>](#obtain-the-hardware-hash)
2. [<span data-ttu-id="dd05a-112">De hash-gegevens samenvoegen</span><span class="sxs-lookup"><span data-stu-id="dd05a-112">Merge the hash data</span></span>](#merge-hash-data)
3. <span data-ttu-id="dd05a-113">[Registreer de apparaten in Microsoft Managed Desktop](#register-devices-by-using-the-admin-portal).</span><span class="sxs-lookup"><span data-stu-id="dd05a-113">[Register the devices in Microsoft Managed Desktop](#register-devices-by-using-the-admin-portal).</span></span>
4. [<span data-ttu-id="dd05a-114">Controleer nog of de afbeelding klopt.</span><span class="sxs-lookup"><span data-stu-id="dd05a-114">Double-check that the image is correct.</span></span>](#check-the-image)
5. [<span data-ttu-id="dd05a-115">Het apparaat leveren</span><span class="sxs-lookup"><span data-stu-id="dd05a-115">Deliver the device</span></span>](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a><span data-ttu-id="dd05a-116">De hardware-hash verkrijgen</span><span class="sxs-lookup"><span data-stu-id="dd05a-116">Obtain the hardware hash</span></span>

<span data-ttu-id="dd05a-117">Microsoft Managed Desktop identificeert elk apparaat uniek door te verwijzen naar de hardware-hash.</span><span class="sxs-lookup"><span data-stu-id="dd05a-117">Microsoft Managed Desktop identifies each device uniquely by referencing its hardware hash.</span></span> <span data-ttu-id="dd05a-118">U hebt vier opties voor het verkrijgen van deze informatie van apparaten die u al gebruikt:</span><span class="sxs-lookup"><span data-stu-id="dd05a-118">You have four options for getting this information from devices you're already using:</span></span>

- <span data-ttu-id="dd05a-119">Neem contact op met de leverancier van de fabrikant voor het auto pilot-registratiebestand, waaronder de hardware-hashes.</span><span class="sxs-lookup"><span data-stu-id="dd05a-119">Ask your OEM supplier for the AutoPilot registration file, which will include the hardware hashes.</span></span>
- <span data-ttu-id="dd05a-120">Gegevens verzamelen in [Microsoft endpoint Configuration Manager](#microsoft-endpoint-configuration-manager).</span><span class="sxs-lookup"><span data-stu-id="dd05a-120">Collect information in [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager).</span></span>
- <span data-ttu-id="dd05a-121">Voer een Windows PowerShell-script uit, hetzij via [Active Directory](#active-directory-powershell-script-method) of [handmatig](#manual-powershell-script-method) op elk apparaat, en verzamel de resultaten in een bestand.</span><span class="sxs-lookup"><span data-stu-id="dd05a-121">Run a Windows PowerShell script--either by using [Active Directory](#active-directory-powershell-script-method) or [manually](#manual-powershell-script-method) on each device--and collect the results in a file.</span></span>
- <span data-ttu-id="dd05a-122">Start elk apparaat, maar voer de installatie van Windows niet uit, en [Verzamel de hashes op een verwisselbaar flashstation](#flash-drive-method).</span><span class="sxs-lookup"><span data-stu-id="dd05a-122">Start each device--but don't complete the Windows setup experience--and [collect the hashes on a removable flash drive](#flash-drive-method).</span></span>

#### <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="dd05a-123">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="dd05a-123">Microsoft Endpoint Configuration Manager</span></span>

<span data-ttu-id="dd05a-124">U kunt Microsoft endpoint Configuration Manager gebruiken om de hardware-hashes te verzamelen van bestaande apparaten die u wilt registreren bij Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="dd05a-124">You can use Microsoft Endpoint Configuration Manager to collect the hardware hashes from existing devices that you want to register with Microsoft Managed Desktop.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dd05a-125">Voor elk apparaat waarop u deze informatie wilt hebben, moet Windows 10, versie 1703 of hoger worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="dd05a-125">Any devices you want to get this information for must be running Windows 10, version 1703 or later.</span></span> 

<span data-ttu-id="dd05a-126">Als u al deze voorwaarden hebt voldaan, kunt u de gegevens op de volgende manier verzamelen:</span><span class="sxs-lookup"><span data-stu-id="dd05a-126">If you've met all these prerequisites, you're ready to collect the information by following these steps:</span></span>

1. <span data-ttu-id="dd05a-127">Selecteer op de console van Configuration Manager de optie **monitoring**.</span><span class="sxs-lookup"><span data-stu-id="dd05a-127">In the Configuration Manager console, select **Monitoring**.</span></span> 
2. <span data-ttu-id="dd05a-128">Vouw in de werkruimte **bewaking het knooppunt rapporten uit** , vouw **rapporten**uit en selecteer het knooppunt **Hardware-algemeen** .</span><span class="sxs-lookup"><span data-stu-id="dd05a-128">In the Monitoring workspace, expand the **Reporting** node, expand **Reports**, and select the **Hardware - General** node.</span></span> 
3. <span data-ttu-id="dd05a-129">Voer het rapport uit, de gegevens van de **Windows auto pilot-apparaten**en Bekijk de resultaten.</span><span class="sxs-lookup"><span data-stu-id="dd05a-129">Run the report, **Windows Autopilot Device Information**, and view the results.</span></span>
4. <span data-ttu-id="dd05a-130">Selecteer het pictogram **exporteren** in de rapportweergave en kies de optie **CSV (door komma's gescheiden)** .</span><span class="sxs-lookup"><span data-stu-id="dd05a-130">In the report viewer, select the **Export** icon, and choose the **CSV (comma-delimited)** option.</span></span>
5. <span data-ttu-id="dd05a-131">Nadat u het bestand hebt opgeslagen, moet u de resultaten filteren op alleen de apparaten die u wilt registreren met Microsoft Managed Desktop en de gegevens naar Microsoft beheerde bureaublad uploaden.</span><span class="sxs-lookup"><span data-stu-id="dd05a-131">After saving the file, you will need to filter results to just those devices you plan to register with Microsoft Managed Desktop and upload the data to Microsoft Managed Desktop.</span></span> <span data-ttu-id="dd05a-132">Open Microsoft Endpoint Manager, ga naar het menu **apparaten** en ga naar de sectie Microsoft Managed Desktop en selecteer **apparaten**.</span><span class="sxs-lookup"><span data-stu-id="dd05a-132">Open Microsoft Endpoint Manager and navigate to the **Devices** menu, then look for Microsoft Managed Desktop section and select **Devices**.</span></span> <span data-ttu-id="dd05a-133">Selecteer **+ register apparaten** om een invliegen te openen om nieuwe apparaten te registreren.</span><span class="sxs-lookup"><span data-stu-id="dd05a-133">Select **+ Register devices** which opens a fly-in to register new devices.</span></span>


<span data-ttu-id="dd05a-134">Zie [apparaten registreren met behulp van de beheer Portal](#register-devices-by-using-the-admin-portal) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="dd05a-134">Refer to [Register devices by using the Admin Portal](#register-devices-by-using-the-admin-portal) for more information.</span></span>


#### <a name="active-directory-powershell-script-method"></a><span data-ttu-id="dd05a-135">Scriptmethode voor Active Directory PowerShell</span><span class="sxs-lookup"><span data-stu-id="dd05a-135">Active Directory PowerShell script method</span></span>

<span data-ttu-id="dd05a-136">In een Active Directory-omgeving kunt u de `Get-WindowsAutoPilotInfo` PowerShell-cmdlet gebruiken om de gegevens op afstand te verzamelen van apparaten in Active Directory-groepen met behulp van WinRM.</span><span class="sxs-lookup"><span data-stu-id="dd05a-136">In an Active Directory environment, you can use the `Get-WindowsAutoPilotInfo` PowerShell cmdlet to remotely collect the information from devices in Active Directory Groups by using WinRM.</span></span> <span data-ttu-id="dd05a-137">U kunt ook de `Get-AD Computer` cmdlet gebruiken en gefilterde resultaten weergeven voor een specifieke naam van een hardware model in de catalogus.</span><span class="sxs-lookup"><span data-stu-id="dd05a-137">You can also use the `Get-AD Computer` cmdlet and get filtered results for a specific hardware model names included in the catalog.</span></span> <span data-ttu-id="dd05a-138">Voordat u dit doet, moet u eerst deze voorwaarden bevestigen en vervolgens de stappen uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="dd05a-138">To do this, first confirm these prerequisites, and then proceed with the steps:</span></span>

- <span data-ttu-id="dd05a-139">WinRM is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="dd05a-139">WinRM is enabled.</span></span>
- <span data-ttu-id="dd05a-140">De apparaten die u registreert, zijn actief op het netwerk (dat wil zeggen dat ze niet zijn verbonden of uitgeschakeld).</span><span class="sxs-lookup"><span data-stu-id="dd05a-140">The devices you want to register are active on the network (that is, they are not disconnected or turned off).</span></span>
- <span data-ttu-id="dd05a-141">Zorg dat u een parameter voor domeinreferenties hebt die gemachtigd is om extern uit te voeren op de apparaten.</span><span class="sxs-lookup"><span data-stu-id="dd05a-141">Make sure you have a domain credential parameter that has permission to execute remotely on the devices.</span></span>
- <span data-ttu-id="dd05a-142">Zorg ervoor dat de toegang tot WMI is toegestaan door Windows Firewall.</span><span class="sxs-lookup"><span data-stu-id="dd05a-142">Make sure that Windows Firewall allows access to WMI.</span></span> <span data-ttu-id="dd05a-143">Voer hiertoe de volgende stappen uit:</span><span class="sxs-lookup"><span data-stu-id="dd05a-143">To do that, follow these steps:</span></span>

    1. <span data-ttu-id="dd05a-144">Open het Configuratiescherm van **Windows Defender firewall** en selecteer **een app of functie toestaan via Windows Defender firewall**.</span><span class="sxs-lookup"><span data-stu-id="dd05a-144">Open the **Windows Defender Firewall** control panel and select **Allow an app or feature through Windows Defender Firewall**.</span></span>
    
    2. <span data-ttu-id="dd05a-145">U kunt **WMI (Windows Management Instrumentation)** zoeken in de lijst, inschakelen voor **privé en openbaar**, en selecteer vervolgens **OK**.</span><span class="sxs-lookup"><span data-stu-id="dd05a-145">Find **Windows Management Instrumentation (WMI)** in the list, enable for both **Private and Public**, and then select **OK**.</span></span>

1.  <span data-ttu-id="dd05a-146">Open een PowerShell-prompt met beheerdersrechten.</span><span class="sxs-lookup"><span data-stu-id="dd05a-146">Open a PowerShell prompt with administrative rights.</span></span>

2.  <span data-ttu-id="dd05a-147">Voer *een* van deze scripts uit:</span><span class="sxs-lookup"><span data-stu-id="dd05a-147">Run *either one* of these scripts:</span></span>

    ```powershell
    Install-script -name Get-WindowsAutoPilotInfo 
    #example one – leverage Get-ADComputer to enumerate devices 
    Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname>
    ```

    ```powershell 
    #example two – target specific devices: 
    Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
    ```

3. <span data-ttu-id="dd05a-148">Toegang krijgen tot mappen waar zich mogelijk vermeldingen bevinden voor de apparaten.</span><span class="sxs-lookup"><span data-stu-id="dd05a-148">Access any directories where there might be entries for the devices.</span></span> <span data-ttu-id="dd05a-149">Verwijdert vermeldingen voor elk apparaat uit *alle* directory's, waaronder Windows Server Active Directory Domain Services en Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="dd05a-149">Remove entries for each device from *all* directories, including Windows Server Active Directory Domain Services and Azure Active Directory.</span></span> <span data-ttu-id="dd05a-150">Het kan een paar uur duren voordat de bewerking is voltooid.</span><span class="sxs-lookup"><span data-stu-id="dd05a-150">Be aware that this removal could take a few hours to completely process.</span></span>

4. <span data-ttu-id="dd05a-151">Toegangsbeheer services waarbij mogelijk vermeldingen voor de apparaten zijn.</span><span class="sxs-lookup"><span data-stu-id="dd05a-151">Access management services where there might be entries for the devices.</span></span> <span data-ttu-id="dd05a-152">Verwijdert vermeldingen voor elk apparaat uit *alle* beheerservices, waaronder Microsoft-Configuratiebeheer, Microsoft intune en Windows auto pilot.</span><span class="sxs-lookup"><span data-stu-id="dd05a-152">Remove entries for each device from *all* management services, including Microsoft Endpoint Configuration Manager, Microsoft Intune, and Windows Autopilot.</span></span> <span data-ttu-id="dd05a-153">Het kan een paar uur duren voordat de bewerking is voltooid.</span><span class="sxs-lookup"><span data-stu-id="dd05a-153">Be aware that this removal could take a few hours to completely process.</span></span>

<span data-ttu-id="dd05a-154">U kunt nu doorgaan met het [registreren van apparaten](#register-devices-by-using-the-admin-portal).</span><span class="sxs-lookup"><span data-stu-id="dd05a-154">Now you can proceed to [register devices](#register-devices-by-using-the-admin-portal).</span></span>

#### <a name="manual-powershell-script-method"></a><span data-ttu-id="dd05a-155">Handmatige PowerShell-scriptmethode</span><span class="sxs-lookup"><span data-stu-id="dd05a-155">Manual PowerShell script method</span></span>

1.  <span data-ttu-id="dd05a-156">Open een PowerShell-prompt met beheerdersrechten.</span><span class="sxs-lookup"><span data-stu-id="dd05a-156">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="dd05a-157">Uitgevoerd `Install-Script -Name Get-WindowsAutoPilotInfo`</span><span class="sxs-lookup"><span data-stu-id="dd05a-157">Run `Install-Script -Name Get-WindowsAutoPilotInfo`</span></span>
3.  <span data-ttu-id="dd05a-158">Uitgevoerd `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="dd05a-158">Run `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
4. [<span data-ttu-id="dd05a-159">De hash-gegevens samenvoegen.</span><span class="sxs-lookup"><span data-stu-id="dd05a-159">Merge the hash data.</span></span>](#merge-hash-data)

#### <a name="flash-drive-method"></a><span data-ttu-id="dd05a-160">Methode Flash Drive</span><span class="sxs-lookup"><span data-stu-id="dd05a-160">Flash drive method</span></span>

1. <span data-ttu-id="dd05a-161">Op een ander apparaat dan de computer die u registreert, voegt u een USB-station in.</span><span class="sxs-lookup"><span data-stu-id="dd05a-161">On a device other than the one you're registering, insert a USB drive.</span></span>
2. <span data-ttu-id="dd05a-162">Open een PowerShell-prompt met beheerdersrechten.</span><span class="sxs-lookup"><span data-stu-id="dd05a-162">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="dd05a-163">Uitgevoerd `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span><span class="sxs-lookup"><span data-stu-id="dd05a-163">Run `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="dd05a-164">Schakel het apparaat in dat u registreert, maar *start niet de installatie*.</span><span class="sxs-lookup"><span data-stu-id="dd05a-164">Turn on the device you are registering, but *do not start the setup experience*.</span></span> <span data-ttu-id="dd05a-165">Als u de installatie-ervaring per ongeluk start, moet u het apparaat opnieuw instellen of opnieuw instellen.</span><span class="sxs-lookup"><span data-stu-id="dd05a-165">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="dd05a-166">Plaats het USB-station en druk op SHIFT + F10.</span><span class="sxs-lookup"><span data-stu-id="dd05a-166">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="dd05a-167">Open een PowerShell-prompt met beheerdersrechten en voer vervolgens de opdracht uit `cd <pathToUsb>` .</span><span class="sxs-lookup"><span data-stu-id="dd05a-167">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="dd05a-168">Uitgevoerd `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span><span class="sxs-lookup"><span data-stu-id="dd05a-168">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="dd05a-169">Uitgevoerd `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="dd05a-169">Run `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
9. <span data-ttu-id="dd05a-170">Verwijder het USB-station en sluit het apparaat af door het uit te voeren `shutdown -s -t 0`</span><span class="sxs-lookup"><span data-stu-id="dd05a-170">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>
10. [<span data-ttu-id="dd05a-171">De hash-gegevens samenvoegen.</span><span class="sxs-lookup"><span data-stu-id="dd05a-171">Merge the hash data.</span></span>](#merge-hash-data)

>[!IMPORTANT]
><span data-ttu-id="dd05a-172">Kracht niet op het apparaat dat u wilt registreren totdat u de registratie voor het apparaat hebt voltooid.</span><span class="sxs-lookup"><span data-stu-id="dd05a-172">Do not power on the device you are registering again until you've completed registration for it.</span></span> 



### <a name="merge-hash-data"></a><span data-ttu-id="dd05a-173">Hash-gegevens samenvoegen</span><span class="sxs-lookup"><span data-stu-id="dd05a-173">Merge hash data</span></span>

<span data-ttu-id="dd05a-174">Als u de hardware-hashgegevens hebt verzameld via de handmatige methoden voor PowerShell of Flash Drive, moet u de gegevens in de CSV-bestanden samenvatten in één bestand om de registratie te voltooien.</span><span class="sxs-lookup"><span data-stu-id="dd05a-174">If you collected the hardware hash data by the manual PowerShell or flash drive methods, you now need to have the data in the CSV files combined into a single file to complete registration.</span></span> <span data-ttu-id="dd05a-175">Hier ziet u een voorbeeld van een PowerShell-script om dit eenvoudig te maken:</span><span class="sxs-lookup"><span data-stu-id="dd05a-175">Here's a sample PowerShell script to make this easy:</span></span>

```powershell
Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv
```

<span data-ttu-id="dd05a-176">Met de hash-gegevens die zijn samengevoegd met een CSV-bestand, kunt u nu verdergaan met [de registratie van de apparaten](#register-devices-by-using-the-admin-portal).</span><span class="sxs-lookup"><span data-stu-id="dd05a-176">With the hash data merged into one CSV file, you can now proceed to [register the devices](#register-devices-by-using-the-admin-portal).</span></span>


#### <a name="register-devices-by-using-the-admin-portal"></a><span data-ttu-id="dd05a-177">Apparaten registreren met behulp van de beheer Portal</span><span class="sxs-lookup"><span data-stu-id="dd05a-177">Register devices by using the Admin Portal</span></span>

<span data-ttu-id="dd05a-178">Selecteer in [Microsoft Endpoint Manager](https://endpoint.microsoft.com/)de optie **apparaten** in het linker navigatiedeelvenster.</span><span class="sxs-lookup"><span data-stu-id="dd05a-178">In [Microsoft Endpoint Manager](https://endpoint.microsoft.com/), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="dd05a-179">Zoek de sectie Microsoft Managed Desktop van het menu en selecteer **apparaten**.</span><span class="sxs-lookup"><span data-stu-id="dd05a-179">Look for the Microsoft Managed Desktop section of the menu and select **Devices**.</span></span> <span data-ttu-id="dd05a-180">Selecteer op de werkruimte Microsoft Managed Desktop apparaten de optie **+ register apparaten** om nieuwe apparaten te registreren.</span><span class="sxs-lookup"><span data-stu-id="dd05a-180">In the Microsoft Managed Desktop Devices workspace, Select **+ Register devices** which opens a fly-in to register new devices.</span></span>

<!-- Update with new picture [![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png) -->


<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


<span data-ttu-id="dd05a-181">Volg deze stappen:</span><span class="sxs-lookup"><span data-stu-id="dd05a-181">Follow these steps:</span></span>

1. <span data-ttu-id="dd05a-182">In **bestand uploaden**geeft u het pad op naar het CSV-bestand dat u eerder hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="dd05a-182">In **File upload**, provide a path to the CSV file you created previously.</span></span>

1. <span data-ttu-id="dd05a-183">Selecteer **apparaten registreren**.</span><span class="sxs-lookup"><span data-stu-id="dd05a-183">Select **Register devices**.</span></span> <span data-ttu-id="dd05a-184">Het systeem voegt de apparaten toe aan uw lijst met apparaten op de **Blade van apparaten**, gemarkeerd als **AutopilotRegistrationRequested**.</span><span class="sxs-lookup"><span data-stu-id="dd05a-184">The system will add the devices to your list of devices on the **Devices blade**, marked as **AutopilotRegistrationRequested**.</span></span> <span data-ttu-id="dd05a-185">Registratie duurt meestal minder dan 10 minuten en wanneer het apparaat succesvol wordt weergegeven als u **klaar bent** , wordt de gebruiker gevraagd het programma te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="dd05a-185">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for a user to start using.</span></span>


<span data-ttu-id="dd05a-186">U kunt de voortgang van apparaatregistratie controleren op de hoofdpagina.</span><span class="sxs-lookup"><span data-stu-id="dd05a-186">You can monitor the progress of device registration on the main page.</span></span> <span data-ttu-id="dd05a-187">Mogelijke Staten hebben aangegeven:</span><span class="sxs-lookup"><span data-stu-id="dd05a-187">Possible states reported there include:</span></span>

| <span data-ttu-id="dd05a-188">Status</span><span class="sxs-lookup"><span data-stu-id="dd05a-188">State</span></span> | <span data-ttu-id="dd05a-189">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="dd05a-189">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="dd05a-190">AutopilotRegistrationRequested</span><span class="sxs-lookup"><span data-stu-id="dd05a-190">AutopilotRegistrationRequested</span></span> | <span data-ttu-id="dd05a-191">De registratie is nog niet voltooid.</span><span class="sxs-lookup"><span data-stu-id="dd05a-191">Registration is not done yet.</span></span> <span data-ttu-id="dd05a-192">Ga later terug.</span><span class="sxs-lookup"><span data-stu-id="dd05a-192">Check back later.</span></span> |
| <span data-ttu-id="dd05a-193">Registratie mislukt</span><span class="sxs-lookup"><span data-stu-id="dd05a-193">Registration failed</span></span> | <span data-ttu-id="dd05a-194">Registreren kon niet worden voltooid.</span><span class="sxs-lookup"><span data-stu-id="dd05a-194">Registration could not be completed.</span></span> <span data-ttu-id="dd05a-195">Zie [problemen met apparaatregistratie oplossen](#troubleshooting-device-registration) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="dd05a-195">Refer to [Troubleshooting device registration](#troubleshooting-device-registration) for more information.</span></span> |
| <span data-ttu-id="dd05a-196">Klaar voor gebruiker</span><span class="sxs-lookup"><span data-stu-id="dd05a-196">Ready for user</span></span> | <span data-ttu-id="dd05a-197">De registratie is gelukt en het apparaat is nu gereed voor levering aan de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="dd05a-197">Registration succeeded and the device is now ready to be delivered to the user.</span></span> <span data-ttu-id="dd05a-198">Microsoft Managed Desktop verstuurt deze door de eerste keer instellen, dus u hoeft verder geen voorbereidingen te treffen.</span><span class="sxs-lookup"><span data-stu-id="dd05a-198">Microsoft Managed Desktop will guide them through first time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="dd05a-199">Actief</span><span class="sxs-lookup"><span data-stu-id="dd05a-199">Active</span></span> | <span data-ttu-id="dd05a-200">Het apparaat is doorgegeven aan de gebruiker en is geregistreerd bij uw Tenant.</span><span class="sxs-lookup"><span data-stu-id="dd05a-200">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="dd05a-201">Dit geeft ook aan dat ze regelmatig gebruikmaken van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="dd05a-201">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="dd05a-202">Inactief</span><span class="sxs-lookup"><span data-stu-id="dd05a-202">Inactive</span></span> | <span data-ttu-id="dd05a-203">Het apparaat is doorgegeven aan de gebruiker en is geregistreerd bij uw Tenant.</span><span class="sxs-lookup"><span data-stu-id="dd05a-203">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="dd05a-204">Ze hebben dit echter niet onlangs gebruikt (in de afgelopen 7 dagen).</span><span class="sxs-lookup"><span data-stu-id="dd05a-204">However, they have not used the device recently (in the last 7 days).</span></span>  | 

#### <a name="troubleshooting-device-registration"></a><span data-ttu-id="dd05a-205">Problemen met apparaatregistratie oplossen</span><span class="sxs-lookup"><span data-stu-id="dd05a-205">Troubleshooting device registration</span></span>

| <span data-ttu-id="dd05a-206">Foutbericht</span><span class="sxs-lookup"><span data-stu-id="dd05a-206">Error message</span></span> | <span data-ttu-id="dd05a-207">Details</span><span class="sxs-lookup"><span data-stu-id="dd05a-207">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="dd05a-208">Apparaat niet gevonden</span><span class="sxs-lookup"><span data-stu-id="dd05a-208">Device not found</span></span> | <span data-ttu-id="dd05a-209">Dit apparaat kan niet worden geregistreerd omdat er geen overeenkomsten zijn gevonden voor de verstrekte fabrikant, model of serienummer.</span><span class="sxs-lookup"><span data-stu-id="dd05a-209">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="dd05a-210">Bevestig deze waarden met de leverancier van uw apparaat.</span><span class="sxs-lookup"><span data-stu-id="dd05a-210">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="dd05a-211">De hardware-hash is niet geldig</span><span class="sxs-lookup"><span data-stu-id="dd05a-211">Hardware hash not valid</span></span> | <span data-ttu-id="dd05a-212">De hardware-hash die u hebt opgegeven voor dit apparaat werd niet goed opgemaakt.</span><span class="sxs-lookup"><span data-stu-id="dd05a-212">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="dd05a-213">Controleer de hardware-hash en voer vervolgens opnieuw in.</span><span class="sxs-lookup"><span data-stu-id="dd05a-213">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="dd05a-214">Apparaat al geregistreerd</span><span class="sxs-lookup"><span data-stu-id="dd05a-214">Device already registered</span></span> | <span data-ttu-id="dd05a-215">Dit apparaat is al geregistreerd voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="dd05a-215">This device is already registered to your organization.</span></span> <span data-ttu-id="dd05a-216">Geen verdere actie vereist.</span><span class="sxs-lookup"><span data-stu-id="dd05a-216">No further action required.</span></span> |
| <span data-ttu-id="dd05a-217">Apparaat geclaimd door een andere organisatie</span><span class="sxs-lookup"><span data-stu-id="dd05a-217">Device claimed by another organization</span></span> | <span data-ttu-id="dd05a-218">Dit apparaat is al door een andere organisatie geclaimd.</span><span class="sxs-lookup"><span data-stu-id="dd05a-218">This device has already been claimed by another organization.</span></span> <span data-ttu-id="dd05a-219">Neem contact op met de leverancier van uw apparaat.</span><span class="sxs-lookup"><span data-stu-id="dd05a-219">Check with your device supplier.</span></span> |
| <span data-ttu-id="dd05a-220">Onverwachte fout</span><span class="sxs-lookup"><span data-stu-id="dd05a-220">Unexpected error</span></span> | <span data-ttu-id="dd05a-221">Uw aanvraag kon niet automatisch worden verwerkt.</span><span class="sxs-lookup"><span data-stu-id="dd05a-221">Your request could not be automatically processed.</span></span> <span data-ttu-id="dd05a-222">Neem contact op met de ondersteuning en voer de aanvraag-ID in: <requestId></span><span class="sxs-lookup"><span data-stu-id="dd05a-222">Contact Support and provide the Request ID: <requestId></span></span> |

### <a name="check-the-image"></a><span data-ttu-id="dd05a-223">De afbeelding controleren</span><span class="sxs-lookup"><span data-stu-id="dd05a-223">Check the image</span></span>

<span data-ttu-id="dd05a-224">Als uw apparaat afkomstig is van een leverancier van Microsoft beheerde desktop partners, moet de afbeelding correct zijn.</span><span class="sxs-lookup"><span data-stu-id="dd05a-224">If your device has come from a Microsoft Managed Desktop partner supplier, the image should be correct.</span></span>

<span data-ttu-id="dd05a-225">U kunt de afbeelding ook zelf toepassen als u dat wilt.</span><span class="sxs-lookup"><span data-stu-id="dd05a-225">You’re also welcome to apply the image on your own if you prefer.</span></span> <span data-ttu-id="dd05a-226">Als u aan de slag wilt gaan, neemt u contact op met de Microsoft-medewerker waarmee u samenwerkt en worden de locatie en de stappen beschreven voor het toepassen van de afbeelding.</span><span class="sxs-lookup"><span data-stu-id="dd05a-226">To get started, contact the Microsoft representative you’re working with and they will provide you the location and steps for applying the image.</span></span>

### <a name="deliver-the-device"></a><span data-ttu-id="dd05a-227">Het apparaat leveren</span><span class="sxs-lookup"><span data-stu-id="dd05a-227">Deliver the device</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dd05a-228">Voordat u het apparaat aan de gebruiker laat overleveren, controleert u of u de [juiste licenties](../get-ready/prerequisites.md) voor die gebruiker hebt verkregen en toegepast.</span><span class="sxs-lookup"><span data-stu-id="dd05a-228">Before you hand off the device to your user, make sure you have obtained and applied the [appropriate licenses](../get-ready/prerequisites.md) for that user.</span></span>

<span data-ttu-id="dd05a-229">Als alle licenties worden toegepast, kunt u de [gebruikers voorbereiden op het gebruik van apparaten](get-started-devices.md)en vervolgens uw gebruiker het apparaat laten opstarten en doorgaan met de installatie van Windows.</span><span class="sxs-lookup"><span data-stu-id="dd05a-229">If all the licenses are applied, you can [get your users ready to use devices](get-started-devices.md), and then your user can start up the device and proceed through the Windows setup experience.</span></span>









