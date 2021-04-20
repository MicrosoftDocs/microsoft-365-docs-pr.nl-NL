---
title: Bestaande apparaten zelf registreren
description: Herbruikbare apparaten registreren die u mogelijk al zelf hebt, zodat ze kunnen worden beheerd door Microsoft Managed Desktop
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 21b0062a337dbeb3c7dec8b715971dbbc4917db1
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893273"
---
# <a name="register-existing-devices-yourself"></a><span data-ttu-id="4719e-103">Bestaande apparaten zelf registreren</span><span class="sxs-lookup"><span data-stu-id="4719e-103">Register existing devices yourself</span></span>

>[!NOTE]
><span data-ttu-id="4719e-104">In dit onderwerp worden de stappen beschreven voor het opnieuw gebruiken van apparaten die u al hebt en registreren in Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="4719e-104">This topic describes the steps for you to reuse devices you already have and register them in Microsoft Managed Desktop.</span></span> <span data-ttu-id="4719e-105">Als u met gloednieuwe apparaten werkt, volgt u in plaats daarvan de stappen in Nieuwe apparaten [registreren in Microsoft Managed Desktop.](register-devices-self.md)</span><span class="sxs-lookup"><span data-stu-id="4719e-105">If you are working with brand-new devices, follow the steps in [Register new devices in Microsoft Managed Desktop yourself](register-devices-self.md) instead.</span></span>

<span data-ttu-id="4719e-106">Het proces voor Partners wordt beschreven in [Stappen voor Partners om apparaten te registreren.](register-devices-partner.md)</span><span class="sxs-lookup"><span data-stu-id="4719e-106">The process for Partners is documented in [Steps for Partners to register devices](register-devices-partner.md).</span></span>

<span data-ttu-id="4719e-107">Microsoft Managed Desktop kan werken met gloednieuwe apparaten of u kunt apparaten die u mogelijk al hebt opnieuw gebruiken (waarvoor u deze opnieuw moet weergeven).</span><span class="sxs-lookup"><span data-stu-id="4719e-107">Microsoft Managed Desktop can work with brand-new devices or you can reuse devices you might already have (which will require that you reimage them).</span></span> <span data-ttu-id="4719e-108">U kunt apparaten registreren met Microsoft Managed Desktop in de Microsoft Endpoint Manager-portal.</span><span class="sxs-lookup"><span data-stu-id="4719e-108">You can register devices with Microsoft Managed Desktop in the Microsoft Endpoint Manager portal.</span></span>

## <a name="prepare-to-register-existing-devices"></a><span data-ttu-id="4719e-109">Voorbereidingen treffen om bestaande apparaten te registreren</span><span class="sxs-lookup"><span data-stu-id="4719e-109">Prepare to register existing devices</span></span>


<span data-ttu-id="4719e-110">Als u bestaande apparaten wilt registreren, volgt u de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="4719e-110">To register existing devices, follow these steps:</span></span>

1. [<span data-ttu-id="4719e-111">Verkrijg de hardwarehash voor elk apparaat.</span><span class="sxs-lookup"><span data-stu-id="4719e-111">Obtain the hardware hash for each device.</span></span>](#obtain-the-hardware-hash)
2. [<span data-ttu-id="4719e-112">De hashgegevens samenvoegen</span><span class="sxs-lookup"><span data-stu-id="4719e-112">Merge the hash data</span></span>](#merge-hash-data)
3. <span data-ttu-id="4719e-113">[Registreer de apparaten in Microsoft Managed Desktop](#register-devices-by-using-the-admin-portal).</span><span class="sxs-lookup"><span data-stu-id="4719e-113">[Register the devices in Microsoft Managed Desktop](#register-devices-by-using-the-admin-portal).</span></span>
4. [<span data-ttu-id="4719e-114">Controleer of de afbeelding juist is.</span><span class="sxs-lookup"><span data-stu-id="4719e-114">Double-check that the image is correct.</span></span>](#check-the-image)
5. [<span data-ttu-id="4719e-115">Het apparaat leveren</span><span class="sxs-lookup"><span data-stu-id="4719e-115">Deliver the device</span></span>](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a><span data-ttu-id="4719e-116">De hardwarehash verkrijgen</span><span class="sxs-lookup"><span data-stu-id="4719e-116">Obtain the hardware hash</span></span>

<span data-ttu-id="4719e-117">Microsoft Managed Desktop identificeert elk apparaat uniek door te verwijzen naar de hardware-hash.</span><span class="sxs-lookup"><span data-stu-id="4719e-117">Microsoft Managed Desktop identifies each device uniquely by referencing its hardware hash.</span></span> <span data-ttu-id="4719e-118">U hebt vier opties voor het verkrijgen van deze informatie op apparaten die u al gebruikt:</span><span class="sxs-lookup"><span data-stu-id="4719e-118">You have four options for getting this information from devices you're already using:</span></span>

- <span data-ttu-id="4719e-119">Vraag uw OEM-leverancier om het AutoPilot-registratiebestand, dat de hardwarehashes bevat.</span><span class="sxs-lookup"><span data-stu-id="4719e-119">Ask your OEM supplier for the AutoPilot registration file, which will include the hardware hashes.</span></span>
- <span data-ttu-id="4719e-120">Gegevens verzamelen in [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager).</span><span class="sxs-lookup"><span data-stu-id="4719e-120">Collect information in [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager).</span></span>
- <span data-ttu-id="4719e-121">Voer een Windows PowerShell-script uit, [](#manual-powershell-script-method) hetzij via [Active Directory](#active-directory-powershell-script-method) of handmatig op elk apparaat, en verzamel de resultaten in een bestand.</span><span class="sxs-lookup"><span data-stu-id="4719e-121">Run a Windows PowerShell script--either by using [Active Directory](#active-directory-powershell-script-method) or [manually](#manual-powershell-script-method) on each device--and collect the results in a file.</span></span>
- <span data-ttu-id="4719e-122">Start elk apparaat, maar voltooi de Installatie-ervaring van Windows niet en verzamel de [hashes op een verwisselbaar flashstation.](#flash-drive-method)</span><span class="sxs-lookup"><span data-stu-id="4719e-122">Start each device--but don't complete the Windows setup experience--and [collect the hashes on a removable flash drive](#flash-drive-method).</span></span>

#### <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="4719e-123">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="4719e-123">Microsoft Endpoint Configuration Manager</span></span>

<span data-ttu-id="4719e-124">U kunt Microsoft Endpoint Configuration Manager gebruiken om de hardwarehashes te verzamelen van bestaande apparaten die u wilt registreren bij Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="4719e-124">You can use Microsoft Endpoint Configuration Manager to collect the hardware hashes from existing devices that you want to register with Microsoft Managed Desktop.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4719e-125">Alle apparaten voor wie u deze informatie wilt ontvangen, moeten Windows 10, versie 1703 of hoger gebruiken.</span><span class="sxs-lookup"><span data-stu-id="4719e-125">Any devices you want to get this information for must be running Windows 10, version 1703 or later.</span></span> 

<span data-ttu-id="4719e-126">Als u aan al deze vereisten hebt voldaan, kunt u de gegevens als volgt verzamelen:</span><span class="sxs-lookup"><span data-stu-id="4719e-126">If you've met all these prerequisites, you're ready to collect the information by following these steps:</span></span>

1. <span data-ttu-id="4719e-127">Selecteer in de console Configuration Manager de optie **Controleren.**</span><span class="sxs-lookup"><span data-stu-id="4719e-127">In the Configuration Manager console, select **Monitoring**.</span></span> 
2. <span data-ttu-id="4719e-128">Vouw in de werkruimte Controle het knooppunt **Rapportage** uit, vouw **Rapporten** uit en selecteer het **knooppunt Hardware - Algemeen.**</span><span class="sxs-lookup"><span data-stu-id="4719e-128">In the Monitoring workspace, expand the **Reporting** node, expand **Reports**, and select the **Hardware - General** node.</span></span> 
3. <span data-ttu-id="4719e-129">Voer het rapport uit, **Windows Autopilot-apparaatgegevens** en bekijk de resultaten.</span><span class="sxs-lookup"><span data-stu-id="4719e-129">Run the report, **Windows Autopilot Device Information**, and view the results.</span></span>
4. <span data-ttu-id="4719e-130">Selecteer in de rapportviewer het **pictogram Exporteren** en kies de **optie CSV (door komma's** scheidingstekens).</span><span class="sxs-lookup"><span data-stu-id="4719e-130">In the report viewer, select the **Export** icon, and choose the **CSV (comma-delimited)** option.</span></span>
5. <span data-ttu-id="4719e-131">Nadat u het bestand hebt opgeslagen, moet u de resultaten filteren op alleen de apparaten die u wilt registreren bij Microsoft Managed Desktop en de gegevens uploaden naar Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="4719e-131">After saving the file, you will need to filter results to just those devices you plan to register with Microsoft Managed Desktop and upload the data to Microsoft Managed Desktop.</span></span> <span data-ttu-id="4719e-132">Open Microsoft Endpoint Manager en navigeer naar **het** menu Apparaten, zoek vervolgens naar de sectie Beheerd bureaublad van Microsoft en selecteer **Apparaten.**</span><span class="sxs-lookup"><span data-stu-id="4719e-132">Open Microsoft Endpoint Manager and navigate to the **Devices** menu, then look for Microsoft Managed Desktop section and select **Devices**.</span></span> <span data-ttu-id="4719e-133">Selecteer **+ Registreer apparaten**, waarmee een in-fly-in wordt geopend om nieuwe apparaten te registreren.</span><span class="sxs-lookup"><span data-stu-id="4719e-133">Select **+ Register devices**, which opens a fly-in to register new devices.</span></span>


<span data-ttu-id="4719e-134">Raadpleeg Apparaten [registreren via de beheerportal voor](#register-devices-by-using-the-admin-portal) meer informatie.</span><span class="sxs-lookup"><span data-stu-id="4719e-134">Refer to [Register devices by using the Admin Portal](#register-devices-by-using-the-admin-portal) for more information.</span></span>


#### <a name="active-directory-powershell-script-method"></a><span data-ttu-id="4719e-135">Active Directory PowerShell-scriptmethode</span><span class="sxs-lookup"><span data-stu-id="4719e-135">Active Directory PowerShell script method</span></span>

<span data-ttu-id="4719e-136">In een Active Directory-omgeving kunt u de PowerShell-cmdlet gebruiken om de gegevens op afstand te verzamelen van `Get-WindowsAutoPilotInfo` apparaten in Active Directory-groepen met behulp van WinRM.</span><span class="sxs-lookup"><span data-stu-id="4719e-136">In an Active Directory environment, you can use the `Get-WindowsAutoPilotInfo` PowerShell cmdlet to remotely collect the information from devices in Active Directory Groups by using WinRM.</span></span> <span data-ttu-id="4719e-137">U kunt ook de cmdlet gebruiken en gefilterde resultaten krijgen voor een specifieke naam van `Get-AD Computer` het hardwaremodel in de catalogus.</span><span class="sxs-lookup"><span data-stu-id="4719e-137">You can also use the `Get-AD Computer` cmdlet and get filtered results for a specific hardware model name included in the catalog.</span></span> <span data-ttu-id="4719e-138">Voordat u verdergaat, bevestigt u eerst deze vereisten en gaat u verder met de stappen:</span><span class="sxs-lookup"><span data-stu-id="4719e-138">Before you proceed, first confirm these prerequisites, and then proceed with the steps:</span></span>

- <span data-ttu-id="4719e-139">WinRM is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="4719e-139">WinRM is enabled.</span></span>
- <span data-ttu-id="4719e-140">De apparaten die u wilt registreren, zijn actief op het netwerk (dat wil zeggen dat ze niet zijn losgekoppeld of uitgeschakeld).</span><span class="sxs-lookup"><span data-stu-id="4719e-140">The devices you want to register are active on the network (that is, they are not disconnected or turned off).</span></span>
- <span data-ttu-id="4719e-141">Zorg ervoor dat u een domeinreferentieparameter hebt die toestemming heeft om extern uit te voeren op de apparaten.</span><span class="sxs-lookup"><span data-stu-id="4719e-141">Make sure you have a domain credential parameter that has permission to execute remotely on the devices.</span></span>
- <span data-ttu-id="4719e-142">Zorg ervoor dat Windows Firewall toegang biedt tot WMI.</span><span class="sxs-lookup"><span data-stu-id="4719e-142">Make sure that Windows Firewall allows access to WMI.</span></span> <span data-ttu-id="4719e-143">Ga als volgt te werk om dit te doen:</span><span class="sxs-lookup"><span data-stu-id="4719e-143">To do that, follow these steps:</span></span>

    1. <span data-ttu-id="4719e-144">Open het **configuratiescherm van Windows Defender Firewall** en selecteer Een app of functie toestaan via Windows Defender **Firewall.**</span><span class="sxs-lookup"><span data-stu-id="4719e-144">Open the **Windows Defender Firewall** control panel and select **Allow an app or feature through Windows Defender Firewall**.</span></span>
    
    2. <span data-ttu-id="4719e-145">Zoek **Windows Management Instrumentation (WMI)** in de lijst, schakel privé en **openbaar** in en selecteer **OK.**</span><span class="sxs-lookup"><span data-stu-id="4719e-145">Find **Windows Management Instrumentation (WMI)** in the list, enable for both **Private and Public**, and then select **OK**.</span></span>

1.  <span data-ttu-id="4719e-146">Open een PowerShell-prompt met beheerdersrechten.</span><span class="sxs-lookup"><span data-stu-id="4719e-146">Open a PowerShell prompt with administrative rights.</span></span>

2.  <span data-ttu-id="4719e-147">Voer *een van deze* scripts uit:</span><span class="sxs-lookup"><span data-stu-id="4719e-147">Run *either one* of these scripts:</span></span>

    ```powershell
    Install-script -name Get-WindowsAutoPilotInfo 
    #example one – leverage Get-ADComputer to enumerate devices 
    Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname>
    ```

    ```powershell 
    #example two – target specific devices: 
    Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
    ```

3. <span data-ttu-id="4719e-148">Toegang tot alle directories waar mogelijk vermeldingen voor de apparaten staan.</span><span class="sxs-lookup"><span data-stu-id="4719e-148">Access any directories where there might be entries for the devices.</span></span> <span data-ttu-id="4719e-149">Verwijder items voor elk apparaat uit *alle mappen,* inclusief Windows Server Active Directory Domain Services en Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4719e-149">Remove entries for each device from *all* directories, including Windows Server Active Directory Domain Services and Azure Active Directory.</span></span> <span data-ttu-id="4719e-150">Het kan enkele uren duren voordat de verwijdering volledig is verwerkt.</span><span class="sxs-lookup"><span data-stu-id="4719e-150">Be aware that removal could take a few hours to completely process.</span></span>

4. <span data-ttu-id="4719e-151">Access management services where there might beentries for the devices.</span><span class="sxs-lookup"><span data-stu-id="4719e-151">Access management services where there might be entries for the devices.</span></span> <span data-ttu-id="4719e-152">Verwijder items voor elk apparaat uit *alle* beheerservices, waaronder Microsoft Endpoint Configuration Manager, Microsoft Intune en Windows Autopilot.</span><span class="sxs-lookup"><span data-stu-id="4719e-152">Remove entries for each device from *all* management services, including Microsoft Endpoint Configuration Manager, Microsoft Intune, and Windows Autopilot.</span></span> <span data-ttu-id="4719e-153">Het kan enkele uren duren voordat de verwijdering volledig is verwerkt.</span><span class="sxs-lookup"><span data-stu-id="4719e-153">Be aware that removal could take a few hours to completely process.</span></span>

<span data-ttu-id="4719e-154">U kunt nu doorgaan met het [registreren van apparaten.](#register-devices-by-using-the-admin-portal)</span><span class="sxs-lookup"><span data-stu-id="4719e-154">Now you can proceed to [register devices](#register-devices-by-using-the-admin-portal).</span></span>

#### <a name="manual-powershell-script-method"></a><span data-ttu-id="4719e-155">Handmatige PowerShell-scriptmethode</span><span class="sxs-lookup"><span data-stu-id="4719e-155">Manual PowerShell script method</span></span>

1.  <span data-ttu-id="4719e-156">Open een PowerShell-prompt met beheerdersrechten.</span><span class="sxs-lookup"><span data-stu-id="4719e-156">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="4719e-157">Uitvoeren `Install-Script -Name Get-WindowsAutoPilotInfo`</span><span class="sxs-lookup"><span data-stu-id="4719e-157">Run `Install-Script -Name Get-WindowsAutoPilotInfo`</span></span>
3.  <span data-ttu-id="4719e-158">Uitvoeren `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="4719e-158">Run `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
4. [<span data-ttu-id="4719e-159">Voeg de hashgegevens samen.</span><span class="sxs-lookup"><span data-stu-id="4719e-159">Merge the hash data.</span></span>](#merge-hash-data)

#### <a name="flash-drive-method"></a><span data-ttu-id="4719e-160">Flashstationmethode</span><span class="sxs-lookup"><span data-stu-id="4719e-160">Flash drive method</span></span>

1. <span data-ttu-id="4719e-161">Op een ander apparaat dan het apparaat dat u registreert, voegt u een USB-station in.</span><span class="sxs-lookup"><span data-stu-id="4719e-161">On a device other than the one you're registering, insert a USB drive.</span></span>
2. <span data-ttu-id="4719e-162">Open een PowerShell-prompt met beheerdersrechten.</span><span class="sxs-lookup"><span data-stu-id="4719e-162">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="4719e-163">Uitvoeren `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span><span class="sxs-lookup"><span data-stu-id="4719e-163">Run `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="4719e-164">Schakel het apparaat in dat u registreert, *maar start de installatie niet.*</span><span class="sxs-lookup"><span data-stu-id="4719e-164">Turn on the device you are registering, but *do not start the setup experience*.</span></span> <span data-ttu-id="4719e-165">Als u de installatie-ervaring per ongeluk start, moet u het apparaat opnieuw instellen of opnieuw instellen.</span><span class="sxs-lookup"><span data-stu-id="4719e-165">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="4719e-166">Voeg het USB-station in en druk vervolgens op Shift + F10.</span><span class="sxs-lookup"><span data-stu-id="4719e-166">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="4719e-167">Open een PowerShell-prompt met beheerdersrechten en voer vervolgens `cd <pathToUsb>` .</span><span class="sxs-lookup"><span data-stu-id="4719e-167">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="4719e-168">Uitvoeren `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span><span class="sxs-lookup"><span data-stu-id="4719e-168">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="4719e-169">Uitvoeren `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="4719e-169">Run `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
9. <span data-ttu-id="4719e-170">Verwijder het USB-station en sluit het apparaat vervolgens af door `shutdown -s -t 0`</span><span class="sxs-lookup"><span data-stu-id="4719e-170">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>
10. [<span data-ttu-id="4719e-171">Voeg de hashgegevens samen.</span><span class="sxs-lookup"><span data-stu-id="4719e-171">Merge the hash data.</span></span>](#merge-hash-data)

>[!IMPORTANT]
><span data-ttu-id="4719e-172">Gebruik het apparaat dat u registreert pas weer aan als u de registratie voor het apparaat hebt voltooid.</span><span class="sxs-lookup"><span data-stu-id="4719e-172">Do not power on the device you are registering again until you've completed registration for it.</span></span> 



### <a name="merge-hash-data"></a><span data-ttu-id="4719e-173">Hashgegevens samenvoegen</span><span class="sxs-lookup"><span data-stu-id="4719e-173">Merge hash data</span></span>

<span data-ttu-id="4719e-174">Als u de hardwarehashgegevens hebt verzameld met de handmatige PowerShell- of flashstationmethoden, moet u de gegevens in de CSV-bestanden nu in één bestand combineren om de registratie te voltooien.</span><span class="sxs-lookup"><span data-stu-id="4719e-174">If you collected the hardware hash data by the manual PowerShell or flash drive methods, you now need to have the data in the CSV files combined into a single file to complete registration.</span></span> <span data-ttu-id="4719e-175">Hier is een voorbeeld van een PowerShell-script om het eenvoudig te maken:</span><span class="sxs-lookup"><span data-stu-id="4719e-175">Here's a sample PowerShell script to make it easy:</span></span>

```powershell
Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv
```

<span data-ttu-id="4719e-176">Als de hashgegevens zijn samengevoegd tot één CSV-bestand, kunt u nu doorgaan met het [registreren van de apparaten.](#register-devices-by-using-the-admin-portal)</span><span class="sxs-lookup"><span data-stu-id="4719e-176">With the hash data merged into one CSV file, you can now proceed to [register the devices](#register-devices-by-using-the-admin-portal).</span></span>


## <a name="register-devices-by-using-the-admin-portal"></a><span data-ttu-id="4719e-177">Apparaten registreren met behulp van de beheerportal</span><span class="sxs-lookup"><span data-stu-id="4719e-177">Register devices by using the Admin Portal</span></span>

<span data-ttu-id="4719e-178">Selecteer [in Microsoft Endpoint Manager](https://endpoint.microsoft.com/)de optie **Apparaten** in het linkernavigatiedeelvenster.</span><span class="sxs-lookup"><span data-stu-id="4719e-178">In [Microsoft Endpoint Manager](https://endpoint.microsoft.com/), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="4719e-179">Zoek de sectie Microsoft Managed Desktop van het menu en selecteer **Apparaten.**</span><span class="sxs-lookup"><span data-stu-id="4719e-179">Look for the Microsoft Managed Desktop section of the menu and select **Devices**.</span></span> <span data-ttu-id="4719e-180">Selecteer + **Registreer** apparaten in de werkruimte Beheerde bureaubladapparaten van Microsoft, waarmee u een fly-in opent om nieuwe apparaten te registreren.</span><span class="sxs-lookup"><span data-stu-id="4719e-180">In the Microsoft Managed Desktop Devices workspace, Select **+ Register devices**, which opens a fly-in to register new devices.</span></span>

<!-- Update with new picture [![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png) -->


<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


<span data-ttu-id="4719e-181">Volg deze stappen:</span><span class="sxs-lookup"><span data-stu-id="4719e-181">Follow these steps:</span></span>

1. <span data-ttu-id="4719e-182">Geef **in Bestand uploaden** een pad op naar het CSV-bestand dat u eerder hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="4719e-182">In **File upload**, provide a path to the CSV file you created previously.</span></span>
2. <span data-ttu-id="4719e-183">Selecteer een [apparaatprofiel](../service-description/profiles.md) in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="4719e-183">Select a [device profile](../service-description/profiles.md) in the drop-down menu.</span></span>
3. <span data-ttu-id="4719e-184">Selecteer **Apparaten registreren.**</span><span class="sxs-lookup"><span data-stu-id="4719e-184">Select **Register devices**.</span></span> <span data-ttu-id="4719e-185">Het systeem voegt de apparaten toe aan uw lijst met apparaten op het **apparaatblad**, gemarkeerd als **Registratie in behandeling.**</span><span class="sxs-lookup"><span data-stu-id="4719e-185">The system will add the devices to your list of devices on the **Devices blade**, marked as **Registration Pending**.</span></span> <span data-ttu-id="4719e-186">Registratie duurt meestal minder dan 10 minuten en  wanneer het apparaat is geslaagd, wordt het apparaat als Gereed voor gebruiker gebruikt, wat betekent dat het klaar is en wacht totdat een gebruiker het gaat gebruiken.</span><span class="sxs-lookup"><span data-stu-id="4719e-186">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for a user to start using.</span></span>

> [!NOTE]
> <span data-ttu-id="4719e-187">Als u handmatig het AAD-groepslidmaatschap van Azure Active Directory van een apparaat wijzigt, wordt het automatisch opnieuw toegewezen aan de groep voor het apparaatprofiel en verwijderd uit conflicterende groepen.</span><span class="sxs-lookup"><span data-stu-id="4719e-187">If you manually change the Azure Active Directory (AAD) group membership of a device, it will be automatically reassigned to the group for its device profile and removed from any conflicting groups.</span></span>

<span data-ttu-id="4719e-188">U kunt de voortgang van apparaatregistratie op de hoofdpagina controleren.</span><span class="sxs-lookup"><span data-stu-id="4719e-188">You can monitor the progress of device registration on the main page.</span></span> <span data-ttu-id="4719e-189">Mogelijke staten die daar zijn gerapporteerd, zijn:</span><span class="sxs-lookup"><span data-stu-id="4719e-189">Possible states reported there include:</span></span>

| <span data-ttu-id="4719e-190">Status</span><span class="sxs-lookup"><span data-stu-id="4719e-190">State</span></span> | <span data-ttu-id="4719e-191">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="4719e-191">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="4719e-192">Registratie in behandeling</span><span class="sxs-lookup"><span data-stu-id="4719e-192">Registration Pending</span></span> | <span data-ttu-id="4719e-193">Registratie is nog niet klaar.</span><span class="sxs-lookup"><span data-stu-id="4719e-193">Registration is not done yet.</span></span> <span data-ttu-id="4719e-194">Controleer het later opnieuw.</span><span class="sxs-lookup"><span data-stu-id="4719e-194">Check back later.</span></span> |
| <span data-ttu-id="4719e-195">Registratie is mislukt</span><span class="sxs-lookup"><span data-stu-id="4719e-195">Registration failed</span></span> | <span data-ttu-id="4719e-196">Registratie kan niet worden voltooid.</span><span class="sxs-lookup"><span data-stu-id="4719e-196">Registration could not be completed.</span></span> <span data-ttu-id="4719e-197">Raadpleeg [Apparaatregistratie oplossen voor](#troubleshooting-device-registration) meer informatie.</span><span class="sxs-lookup"><span data-stu-id="4719e-197">Refer to [Troubleshooting device registration](#troubleshooting-device-registration) for more information.</span></span> |
| <span data-ttu-id="4719e-198">Klaar voor gebruiker</span><span class="sxs-lookup"><span data-stu-id="4719e-198">Ready for user</span></span> | <span data-ttu-id="4719e-199">Registratie is geslaagd en het apparaat is nu klaar om aan de gebruiker te worden geleverd.</span><span class="sxs-lookup"><span data-stu-id="4719e-199">Registration succeeded and the device is now ready to be delivered to the user.</span></span> <span data-ttu-id="4719e-200">Microsoft Managed Desktop begeleidt ze bij de eerste keer instellen, zodat u geen verdere voorbereidingen hoeft te treffen.</span><span class="sxs-lookup"><span data-stu-id="4719e-200">Microsoft Managed Desktop will guide them through first-time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="4719e-201">Actief</span><span class="sxs-lookup"><span data-stu-id="4719e-201">Active</span></span> | <span data-ttu-id="4719e-202">Het apparaat is geleverd aan de gebruiker en heeft zich geregistreerd bij uw tenant.</span><span class="sxs-lookup"><span data-stu-id="4719e-202">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="4719e-203">Dit geeft ook aan dat ze het apparaat regelmatig gebruiken.</span><span class="sxs-lookup"><span data-stu-id="4719e-203">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="4719e-204">Inactief</span><span class="sxs-lookup"><span data-stu-id="4719e-204">Inactive</span></span> | <span data-ttu-id="4719e-205">Het apparaat is geleverd aan de gebruiker en heeft zich geregistreerd bij uw tenant.</span><span class="sxs-lookup"><span data-stu-id="4719e-205">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="4719e-206">Ze hebben het apparaat echter onlangs (in de afgelopen 7 dagen) niet gebruikt.</span><span class="sxs-lookup"><span data-stu-id="4719e-206">However, they have not used the device recently (in the last 7 days).</span></span>  | 

### <a name="troubleshooting-device-registration"></a><span data-ttu-id="4719e-207">Apparaatregistratie oplossen</span><span class="sxs-lookup"><span data-stu-id="4719e-207">Troubleshooting device registration</span></span>

| <span data-ttu-id="4719e-208">Foutbericht</span><span class="sxs-lookup"><span data-stu-id="4719e-208">Error message</span></span> | <span data-ttu-id="4719e-209">Details</span><span class="sxs-lookup"><span data-stu-id="4719e-209">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="4719e-210">Apparaat niet gevonden</span><span class="sxs-lookup"><span data-stu-id="4719e-210">Device not found</span></span> | <span data-ttu-id="4719e-211">We konden dit apparaat niet registreren omdat we geen overeenkomst konden vinden voor de fabrikant, het model of het serienummer.</span><span class="sxs-lookup"><span data-stu-id="4719e-211">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="4719e-212">Bevestig deze waarden bij uw apparaatleverancier.</span><span class="sxs-lookup"><span data-stu-id="4719e-212">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="4719e-213">Hardware-hash niet geldig</span><span class="sxs-lookup"><span data-stu-id="4719e-213">Hardware hash not valid</span></span> | <span data-ttu-id="4719e-214">De hardwarehash die u voor dit apparaat hebt opgegeven, is niet correct opgemaakt.</span><span class="sxs-lookup"><span data-stu-id="4719e-214">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="4719e-215">Controleer de hardwarehash en vervolgens opnieuw.</span><span class="sxs-lookup"><span data-stu-id="4719e-215">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="4719e-216">Apparaat dat al is geregistreerd</span><span class="sxs-lookup"><span data-stu-id="4719e-216">Device already registered</span></span> | <span data-ttu-id="4719e-217">Dit apparaat is al geregistreerd bij uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="4719e-217">This device is already registered to your organization.</span></span> <span data-ttu-id="4719e-218">Geen verdere actie vereist.</span><span class="sxs-lookup"><span data-stu-id="4719e-218">No further action required.</span></span> |
| <span data-ttu-id="4719e-219">Apparaat dat door een andere organisatie is geclaimd</span><span class="sxs-lookup"><span data-stu-id="4719e-219">Device claimed by another organization</span></span> | <span data-ttu-id="4719e-220">Dit apparaat is al geclaimd door een andere organisatie.</span><span class="sxs-lookup"><span data-stu-id="4719e-220">This device has already been claimed by another organization.</span></span> <span data-ttu-id="4719e-221">Neem contact op met uw apparaatleverancier.</span><span class="sxs-lookup"><span data-stu-id="4719e-221">Check with your device supplier.</span></span> |
| <span data-ttu-id="4719e-222">Onverwachte fout</span><span class="sxs-lookup"><span data-stu-id="4719e-222">Unexpected error</span></span> | <span data-ttu-id="4719e-223">Uw aanvraag kan niet automatisch worden verwerkt.</span><span class="sxs-lookup"><span data-stu-id="4719e-223">Your request could not be automatically processed.</span></span> <span data-ttu-id="4719e-224">Neem contact op met ondersteuning en geef de aanvraag-id op: <requestId></span><span class="sxs-lookup"><span data-stu-id="4719e-224">Contact Support and provide the Request ID: <requestId></span></span> |

## <a name="check-the-image"></a><span data-ttu-id="4719e-225">De afbeelding controleren</span><span class="sxs-lookup"><span data-stu-id="4719e-225">Check the image</span></span>

<span data-ttu-id="4719e-226">Als uw apparaat afkomstig is van een Microsoft Managed Desktop-partnerleverancier, moet de afbeelding juist zijn.</span><span class="sxs-lookup"><span data-stu-id="4719e-226">If your device has come from a Microsoft Managed Desktop partner supplier, the image should be correct.</span></span>

<span data-ttu-id="4719e-227">U kunt de afbeelding ook zelf toepassen als u dat wilt.</span><span class="sxs-lookup"><span data-stu-id="4719e-227">You’re also welcome to apply the image on your own if you prefer.</span></span> <span data-ttu-id="4719e-228">Als u wilt beginnen, neemt u contact op met de Microsoft-vertegenwoordiger met wie u werkt. Deze vertegenwoordiger geeft u de locatie en stappen voor het toepassen van de afbeelding.</span><span class="sxs-lookup"><span data-stu-id="4719e-228">To get started, contact the Microsoft representative you’re working with and they will provide you the location and steps for applying the image.</span></span>

## <a name="deliver-the-device"></a><span data-ttu-id="4719e-229">Het apparaat leveren</span><span class="sxs-lookup"><span data-stu-id="4719e-229">Deliver the device</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4719e-230">Voordat u het apparaat aan uw gebruiker aflevert, [](../get-ready/prerequisites.md) moet u ervoor zorgen dat u de juiste licenties voor die gebruiker hebt verkregen en toegepast.</span><span class="sxs-lookup"><span data-stu-id="4719e-230">Before you hand off the device to your user, make sure you have obtained and applied the [appropriate licenses](../get-ready/prerequisites.md) for that user.</span></span>

<span data-ttu-id="4719e-231">Als alle licenties worden toegepast, kunt u uw gebruikers voorbereiden op het gebruik van apparaten [en](get-started-devices.md)vervolgens kan uw gebruiker het apparaat starten en doorgaan met de Installatie-ervaring van Windows.</span><span class="sxs-lookup"><span data-stu-id="4719e-231">If all the licenses are applied, you can [get your users ready to use devices](get-started-devices.md), and then your user can start up the device and proceed through the Windows setup experience.</span></span>









