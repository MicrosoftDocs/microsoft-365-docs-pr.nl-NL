---
title: Nieuwe apparaten zelf registreren
description: Apparaten zelf registreren zodat ze kunnen worden beheerd door Microsoft Managed Desktop
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 8765d6ecd180d71d918a5feda8cd5089e7f561ee
ms.sourcegitcommit: 8d9509e617ede7cc5ba933c54fb9300d2d1c6344
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/22/2020
ms.locfileid: "44347817"
---
# <a name="register-new-devices-yourself"></a><span data-ttu-id="04eb7-103">Nieuwe apparaten zelf registreren</span><span class="sxs-lookup"><span data-stu-id="04eb7-103">Register new devices yourself</span></span>

<span data-ttu-id="04eb7-104">Microsoft Managed Desktop kan werken met gloednieuwe apparaten of u apparaten die u misschien al hebt opnieuw gebruiken (waarvoor u ze opnieuw moet afbeelding smaken).</span><span class="sxs-lookup"><span data-stu-id="04eb7-104">Microsoft Managed Desktop can work with brand-new devices or you can re-use devices you might already have (which will require that you re-image them).</span></span> <span data-ttu-id="04eb7-105">U apparaten registreren met Microsoft Managed Desktop op de Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="04eb7-105">You can register devices by using Microsoft Managed Desktop on the Azure Portal.</span></span>

> [!NOTE]
> <span data-ttu-id="04eb7-106">Samenwerken met een partner om apparaten te verkrijgen?</span><span class="sxs-lookup"><span data-stu-id="04eb7-106">Working with a partner to obtain devices?</span></span> <span data-ttu-id="04eb7-107">Als dat zo is, hoeft u zich geen zorgen te maken over het verkrijgen van de hardware hashes; Dat regelen ze wel voor je.</span><span class="sxs-lookup"><span data-stu-id="04eb7-107">If so, you don't need to worry about getting the hardware hashes; they'll take care of that for you.</span></span> <span data-ttu-id="04eb7-108">Zorg ervoor dat uw partner een relatie met u opbouwt in het [Partner Center.](https://partner.microsoft.com/dashboard)</span><span class="sxs-lookup"><span data-stu-id="04eb7-108">Make sure your partner establishes a relationship with you at the [Partner Center](https://partner.microsoft.com/dashboard).</span></span> <span data-ttu-id="04eb7-109">Uw partner kan meer informatie krijgen bij [Partner Center help.](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer)</span><span class="sxs-lookup"><span data-stu-id="04eb7-109">Your partner can learn more at [Partner Center help](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer).</span></span> <span data-ttu-id="04eb7-110">Zodra deze relatie is vastgesteld, zal uw partner gewoon apparaten namens u registreren - geen verdere actie die van u wordt verlangd.</span><span class="sxs-lookup"><span data-stu-id="04eb7-110">Once this relationship established, your partner will simply register devices on your behalf – no further action required from you.</span></span> <span data-ttu-id="04eb7-111">Zie Stappen voor partners om [apparaten te registreren](register-devices-partner.md)als u de details wilt zien of als uw partner vragen heeft.</span><span class="sxs-lookup"><span data-stu-id="04eb7-111">If you want to see the details, or your partner has questions, see [Steps for Partners to register devices](register-devices-partner.md).</span></span> <span data-ttu-id="04eb7-112">Zodra de apparaten zijn geregistreerd, u doorgaan met [het controleren van de afbeelding](#check-the-image) en het leveren van de [apparaten](#deliver-the-device) aan uw gebruikers.</span><span class="sxs-lookup"><span data-stu-id="04eb7-112">Once the devices are registered, you can proceed with [checking the image](#check-the-image) and [delivering the devices](#deliver-the-device) to your users.</span></span>

## <a name="prepare-to-register-brand-new-devices"></a><span data-ttu-id="04eb7-113">Voorbereiden om gloednieuwe apparaten te registreren</span><span class="sxs-lookup"><span data-stu-id="04eb7-113">Prepare to register brand-new devices</span></span>


<span data-ttu-id="04eb7-114">Zodra u de nieuwe apparaten in de hand hebt, volgt u de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="04eb7-114">Once you have the new devices in hand, you'll follow these steps:</span></span>

1. [<span data-ttu-id="04eb7-115">Verkrijg de hardwarehash voor elk apparaat.</span><span class="sxs-lookup"><span data-stu-id="04eb7-115">Obtain the hardware hash for each device.</span></span>](#obtain-the-hardware-hash)
2. [<span data-ttu-id="04eb7-116">De hashgegevens samenvoegen</span><span class="sxs-lookup"><span data-stu-id="04eb7-116">Merge the hash data</span></span>](#merge-hash-data)
3. <span data-ttu-id="04eb7-117">[Registreer de apparaten in Microsoft Managed Desktop](#register-devices).</span><span class="sxs-lookup"><span data-stu-id="04eb7-117">[Register the devices in Microsoft Managed Desktop](#register-devices).</span></span>
4. [<span data-ttu-id="04eb7-118">Controleer nogmaals of de afbeelding correct is.</span><span class="sxs-lookup"><span data-stu-id="04eb7-118">Double-check that the image is correct.</span></span>](#check-the-image)
5. [<span data-ttu-id="04eb7-119">Het apparaat leveren</span><span class="sxs-lookup"><span data-stu-id="04eb7-119">Deliver the device</span></span>](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a><span data-ttu-id="04eb7-120">De hardwarehash verkrijgen</span><span class="sxs-lookup"><span data-stu-id="04eb7-120">Obtain the hardware hash</span></span>

<span data-ttu-id="04eb7-121">Microsoft Managed Desktop identificeert elk apparaat uniek door te verwijzen naar de hardwarehash.</span><span class="sxs-lookup"><span data-stu-id="04eb7-121">Microsoft Managed Desktop identifies each device uniquely by referencing its hardware hash.</span></span> <span data-ttu-id="04eb7-122">Je hebt drie opties voor het verkrijgen van deze informatie:</span><span class="sxs-lookup"><span data-stu-id="04eb7-122">You have three options for getting this information:</span></span>

- <span data-ttu-id="04eb7-123">Vraag uw OEM-leverancier naar het AutoPilot-registratiebestand, dat de hardwarehashes bevat.</span><span class="sxs-lookup"><span data-stu-id="04eb7-123">Ask your OEM supplier for the AutoPilot registration file, which will include the hardware hashes.</span></span>
- <span data-ttu-id="04eb7-124">Voer een [Windows PowerShell-script](#powershell-script-method) uit op elk apparaat en verzamel de resultaten in een bestand.</span><span class="sxs-lookup"><span data-stu-id="04eb7-124">Run a [Windows PowerShell script](#powershell-script-method) on each device and collect the results in a file.</span></span>
- <span data-ttu-id="04eb7-125">Start elk apparaat- maar voltooi de Installatie-ervaring van Windows niet - en [verzamel de hashes op een verwisselbaar flashstation.](#flash-drive-method)</span><span class="sxs-lookup"><span data-stu-id="04eb7-125">Start each device--but don't complete the Windows setup experience--and [collect the hashes on a removable flash drive](#flash-drive-method).</span></span>

#### <a name="powershell-script-method"></a><span data-ttu-id="04eb7-126">PowerShell-scriptmethode</span><span class="sxs-lookup"><span data-stu-id="04eb7-126">PowerShell script method</span></span>

1.  <span data-ttu-id="04eb7-127">Open een PowerShell-prompt met beheerdersrechten.</span><span class="sxs-lookup"><span data-stu-id="04eb7-127">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="04eb7-128">Uitvoeren`Install-Script -Name Get-MMDRegistrationInfo`</span><span class="sxs-lookup"><span data-stu-id="04eb7-128">Run `Install-Script -Name Get-MMDRegistrationInfo`</span></span>
3.  <span data-ttu-id="04eb7-129">Uitvoeren`powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="04eb7-129">Run `powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span></span>

#### <a name="flash-drive-method"></a><span data-ttu-id="04eb7-130">Flash-stationmethode</span><span class="sxs-lookup"><span data-stu-id="04eb7-130">Flash drive method</span></span>

1. <span data-ttu-id="04eb7-131">Plaats een USB-station op een ander apparaat dan het apparaat dat u registreert.</span><span class="sxs-lookup"><span data-stu-id="04eb7-131">On a device other than the one you're registering, insert a USB drive.</span></span>
2. <span data-ttu-id="04eb7-132">Open een PowerShell-prompt met beheerdersrechten.</span><span class="sxs-lookup"><span data-stu-id="04eb7-132">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="04eb7-133">Uitvoeren`Save-Script -Name Get-MMDRegistrationInfo -Path <pathToUsb>`</span><span class="sxs-lookup"><span data-stu-id="04eb7-133">Run `Save-Script -Name Get-MMDRegistrationInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="04eb7-134">Schakel het apparaat in dat u registreert, maar *start de installatie-ervaring niet.*</span><span class="sxs-lookup"><span data-stu-id="04eb7-134">Turn on the device you are registering, but *do not start the setup experience*.</span></span> <span data-ttu-id="04eb7-135">Als u per ongeluk de installatie-ervaring start, moet u het apparaat opnieuw instellen of opnieuw inbeelden.</span><span class="sxs-lookup"><span data-stu-id="04eb7-135">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="04eb7-136">Plaats het USB-station en druk op Shift + F10.</span><span class="sxs-lookup"><span data-stu-id="04eb7-136">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="04eb7-137">Open een PowerShell-prompt met beheerdersrechten en voer vervolgens uit `cd <pathToUsb>` .</span><span class="sxs-lookup"><span data-stu-id="04eb7-137">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="04eb7-138">Uitvoeren`Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span><span class="sxs-lookup"><span data-stu-id="04eb7-138">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="04eb7-139">Uitvoeren`.\Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="04eb7-139">Run `.\Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span></span>
9. <span data-ttu-id="04eb7-140">Verwijder het USB-station en schakel het apparaat vervolgens uit door`shutdown -s -t 0`</span><span class="sxs-lookup"><span data-stu-id="04eb7-140">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>

>[!IMPORTANT]
><span data-ttu-id="04eb7-141">Ga niet meer in op het apparaat dat u registreert totdat u de registratie voor het apparaat hebt voltooid.</span><span class="sxs-lookup"><span data-stu-id="04eb7-141">Do not power on the device you are registering again until you've completed registration for it.</span></span> 


### <a name="merge-hash-data"></a><span data-ttu-id="04eb7-142">Hashgegevens samenvoegen</span><span class="sxs-lookup"><span data-stu-id="04eb7-142">Merge hash data</span></span>

<span data-ttu-id="04eb7-143">U moet de gegevens in de CSV-bestanden in één bestand hebben gecombineerd om de registratie te voltooien.</span><span class="sxs-lookup"><span data-stu-id="04eb7-143">You'll need to have the data in the CSV files combined into a single file to complete registration.</span></span> <span data-ttu-id="04eb7-144">Hier is een voorbeeld PowerShell script om dit eenvoudig te maken:</span><span class="sxs-lookup"><span data-stu-id="04eb7-144">Here's a sample PowerShell script to make this easy:</span></span>

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`
### <a name="register-devices"></a><span data-ttu-id="04eb7-145">Apparaten registreren</span><span class="sxs-lookup"><span data-stu-id="04eb7-145">Register devices</span></span>

<span data-ttu-id="04eb7-146">Het CSV-bestand moet zich in een bepaalde indeling voor registratie hebben.</span><span class="sxs-lookup"><span data-stu-id="04eb7-146">The CSV file must be in a particular format for registration.</span></span> <span data-ttu-id="04eb7-147">Als u de gegevens zelf hebt verzameld in de vorige stappen, moet het bestand al in de juiste indeling zijn; als u het bestand van een leverancier verkrijgt, moet u mogelijk de indeling aanpassen.</span><span class="sxs-lookup"><span data-stu-id="04eb7-147">If you collected the data yourself in the previous steps, the file should already be in the right format; if you obtain the file from a supplier, you might need to adjust the format.</span></span>

>[!NOTE]
><span data-ttu-id="04eb7-148">Voor uw gemak u een [voorbeeld CSV-bestand](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-self.csv)downloaden.</span><span class="sxs-lookup"><span data-stu-id="04eb7-148">For your convenience, you can download a [sample CSV file](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-self.csv).</span></span>

<span data-ttu-id="04eb7-149">Uw bestand moet **exact dezelfde kolomkoppen** bevatten als de voorbeeldkop (fabrikant, model, enz.), maar uw eigen gegevens voor de andere rijen.</span><span class="sxs-lookup"><span data-stu-id="04eb7-149">Your file needs to include the **exact same column headings** as the sample one (Manufacturer, Model, etc.), but your own data for the other rows.</span></span> <span data-ttu-id="04eb7-150">Als u de sjabloon gebruikt, opent u deze in een tekstbewerkingstool zoals Kladblok en overweegt u alle gegevens alleen in rij 1 achter te laten en alleen gegevens in rijen 2 en lager in te voeren.</span><span class="sxs-lookup"><span data-stu-id="04eb7-150">If you use the template, open it in a text editing tool such as Notepad, and consider leaving all the data in row 1 alone, only entering data in rows 2 and below.</span></span> 
    
  ```
 Manufacturer,Model,Serial Number,Hardware Hash
  SpiralOrbit,ContosoABC,000000000000,dGhpc2RldmljZWlzYW5tbWRkZXZpY2U
  
  
  ```

>[!NOTE]
><span data-ttu-id="04eb7-151">Als u vergeet een van de voorbeeldgegevens te wijzigen, mislukt de registratie.</span><span class="sxs-lookup"><span data-stu-id="04eb7-151">If you forget to change any of the sample data, registration will fail.</span></span>

#### <a name="register-devices-by-using-the-azure-portal"></a><span data-ttu-id="04eb7-152">Apparaten registreren met behulp van de Azure Portal</span><span class="sxs-lookup"><span data-stu-id="04eb7-152">Register devices by using the Azure Portal</span></span>

<span data-ttu-id="04eb7-153">Selecteer **Apparaten** in het linkernavigatiedeelvenster in de [Azure-portal](https://aka.ms/mmdportal)van Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="04eb7-153">From the Microsoft Managed Desktop [Azure Portal](https://aka.ms/mmdportal), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="04eb7-154">Selecteer **+ Apparaten registreren**; de fly-in opent:</span><span class="sxs-lookup"><span data-stu-id="04eb7-154">Select **+ Register devices**; the fly-in opens:</span></span>

<span data-ttu-id="04eb7-155">[![Fly-in na het selecteren van Register-apparaten, het vermelden van apparaten met kolommen voor toegewezen gebruikers, serienummer, status, laatst geziene datum en leeftijd](../../media/register-devices-flyin-sterile.png)](../../media/register-devices-flyin-sterile.png)</span><span class="sxs-lookup"><span data-stu-id="04eb7-155">[![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/register-devices-flyin-sterile.png)](../../media/register-devices-flyin-sterile.png)</span></span>


[//]: # (Helaas is dit niet waar. We kunnen deze notitie verwijderen - maar laten het nu totdat we een kans hebben om erover te praten.)

<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


<span data-ttu-id="04eb7-157">Volg deze stappen:</span><span class="sxs-lookup"><span data-stu-id="04eb7-157">Follow these steps:</span></span>

1. <span data-ttu-id="04eb7-158">Geef **in Het uploaden van**bestanden een pad naar het CSV-bestand dat u eerder hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="04eb7-158">In **File upload**, provide a path to the CSV file you created previously.</span></span>
2. <span data-ttu-id="04eb7-159">Optioneel u een **bestel-id** of **aankoop-id** toevoegen voor uw eigen trackingdoeleinden.</span><span class="sxs-lookup"><span data-stu-id="04eb7-159">Optionally, you can add an **Order ID** or **Purchase ID** for your own tracking purposes.</span></span> <span data-ttu-id="04eb7-160">Er zijn geen indelingsvereisten voor deze waarden.</span><span class="sxs-lookup"><span data-stu-id="04eb7-160">There are no format requirements for these values.</span></span>
3. <span data-ttu-id="04eb7-161">Selecteer **Apparaten registreren**.</span><span class="sxs-lookup"><span data-stu-id="04eb7-161">Select **Register devices**.</span></span> <span data-ttu-id="04eb7-162">Het systeem voegt de apparaten toe aan uw lijst met apparaten op het **apparaatblad**, gemarkeerd als **Registratie in behandeling**.</span><span class="sxs-lookup"><span data-stu-id="04eb7-162">The system will add the devices to your list of devices on the **Devices blade**, marked as **Registration Pending**.</span></span> <span data-ttu-id="04eb7-163">Registratie duurt meestal minder dan 10 minuten, en wanneer het apparaat succesvol is, wordt het weergegeven als **Klaar voor de gebruiker,** wat betekent dat het klaar is en wacht tot een eindgebruiker begint te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="04eb7-163">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for an end-user to start using.</span></span>


<span data-ttu-id="04eb7-164">U de voortgang van de apparaatregistratie controleren op de hoofdpagina **Microsoft Managed Desktop - Devices.**</span><span class="sxs-lookup"><span data-stu-id="04eb7-164">You can monitor the progress of device registration on the main **Microsoft Managed Desktop - Devices** page.</span></span> <span data-ttu-id="04eb7-165">Mogelijke staten die daar worden gemeld zijn:</span><span class="sxs-lookup"><span data-stu-id="04eb7-165">Possible states reported there include:</span></span>

| <span data-ttu-id="04eb7-166">Status</span><span class="sxs-lookup"><span data-stu-id="04eb7-166">State</span></span> | <span data-ttu-id="04eb7-167">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="04eb7-167">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="04eb7-168">Registratie in behandeling</span><span class="sxs-lookup"><span data-stu-id="04eb7-168">Registration pending</span></span> | <span data-ttu-id="04eb7-169">Registratie is nog niet gedaan.</span><span class="sxs-lookup"><span data-stu-id="04eb7-169">Registration is not done yet.</span></span> <span data-ttu-id="04eb7-170">Kom later terug.</span><span class="sxs-lookup"><span data-stu-id="04eb7-170">Check back later.</span></span> |
| <span data-ttu-id="04eb7-171">Registratie is mislukt</span><span class="sxs-lookup"><span data-stu-id="04eb7-171">Registration failed</span></span> | <span data-ttu-id="04eb7-172">De registratie kon niet worden voltooid.</span><span class="sxs-lookup"><span data-stu-id="04eb7-172">Registration could not be completed.</span></span> <span data-ttu-id="04eb7-173">Raadpleeg [apparaatregistratie probleemoplossing](#troubleshooting-device-registration) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="04eb7-173">Refer to [Troubleshooting device registration](#troubleshooting-device-registration) for more information.</span></span> |
| <span data-ttu-id="04eb7-174">Klaar voor gebruik</span><span class="sxs-lookup"><span data-stu-id="04eb7-174">Ready for user</span></span> | <span data-ttu-id="04eb7-175">Registratie geslaagd en het apparaat is nu klaar om te worden geleverd aan de eindgebruiker.</span><span class="sxs-lookup"><span data-stu-id="04eb7-175">Registration succeeded and the device is now ready to be delivered to the end user.</span></span> <span data-ttu-id="04eb7-176">Microsoft Managed Desktop begeleidt hen door de eerste set-up, dus u hoeft zich niet verder te voorbereiden.</span><span class="sxs-lookup"><span data-stu-id="04eb7-176">Microsoft Managed Desktop will guide them through first time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="04eb7-177">Actief</span><span class="sxs-lookup"><span data-stu-id="04eb7-177">Active</span></span> | <span data-ttu-id="04eb7-178">Het apparaat is geleverd aan de eindgebruiker en ze hebben zich geregistreerd bij uw tenant.</span><span class="sxs-lookup"><span data-stu-id="04eb7-178">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="04eb7-179">Dit geeft ook aan dat ze regelmatig gebruik maken van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="04eb7-179">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="04eb7-180">Inactief</span><span class="sxs-lookup"><span data-stu-id="04eb7-180">Inactive</span></span> | <span data-ttu-id="04eb7-181">Het apparaat is geleverd aan de eindgebruiker en ze hebben zich geregistreerd bij uw tenant.</span><span class="sxs-lookup"><span data-stu-id="04eb7-181">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="04eb7-182">Ze hebben het apparaat echter niet recent gebruikt (in de afgelopen 7 dagen).</span><span class="sxs-lookup"><span data-stu-id="04eb7-182">However, they have not used the device recently (in the last 7 days).</span></span>  | 

#### <a name="troubleshooting-device-registration"></a><span data-ttu-id="04eb7-183">Apparaatregistratie oplossen</span><span class="sxs-lookup"><span data-stu-id="04eb7-183">Troubleshooting device registration</span></span>

| <span data-ttu-id="04eb7-184">Foutbericht</span><span class="sxs-lookup"><span data-stu-id="04eb7-184">Error message</span></span> | <span data-ttu-id="04eb7-185">Details</span><span class="sxs-lookup"><span data-stu-id="04eb7-185">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="04eb7-186">Apparaat niet gevonden</span><span class="sxs-lookup"><span data-stu-id="04eb7-186">Device not found</span></span> | <span data-ttu-id="04eb7-187">We konden dit apparaat niet registreren omdat we geen overeenkomst konden vinden voor de meegeleverde fabrikant, model of serienummer.</span><span class="sxs-lookup"><span data-stu-id="04eb7-187">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="04eb7-188">Bevestig deze waarden met uw apparaatleverancier.</span><span class="sxs-lookup"><span data-stu-id="04eb7-188">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="04eb7-189">Hardwarehash niet geldig</span><span class="sxs-lookup"><span data-stu-id="04eb7-189">Hardware hash not valid</span></span> | <span data-ttu-id="04eb7-190">De hardwarehash die u voor dit apparaat hebt opgegeven, is niet correct geformatteerd.</span><span class="sxs-lookup"><span data-stu-id="04eb7-190">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="04eb7-191">Controleer de hardwarehash en voer deze vervolgens opnieuw in.</span><span class="sxs-lookup"><span data-stu-id="04eb7-191">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="04eb7-192">Apparaat al geregistreerd</span><span class="sxs-lookup"><span data-stu-id="04eb7-192">Device already registered</span></span> | <span data-ttu-id="04eb7-193">Dit apparaat is al geregistreerd bij uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="04eb7-193">This device is already registered to your organization.</span></span> <span data-ttu-id="04eb7-194">Geen verdere actie vereist.</span><span class="sxs-lookup"><span data-stu-id="04eb7-194">No further action required.</span></span> |
| <span data-ttu-id="04eb7-195">Apparaat dat is geclaimd door een andere organisatie</span><span class="sxs-lookup"><span data-stu-id="04eb7-195">Device claimed by another organization</span></span> | <span data-ttu-id="04eb7-196">Dit apparaat is al geclaimd door een andere organisatie.</span><span class="sxs-lookup"><span data-stu-id="04eb7-196">This device has already been claimed by another organization.</span></span> <span data-ttu-id="04eb7-197">Neem contact op met uw apparaatleverancier.</span><span class="sxs-lookup"><span data-stu-id="04eb7-197">Check with your device supplier.</span></span> |
| <span data-ttu-id="04eb7-198">Onverwachte fout</span><span class="sxs-lookup"><span data-stu-id="04eb7-198">Unexpected error</span></span> | <span data-ttu-id="04eb7-199">Uw aanvraag kan niet automatisch worden verwerkt.</span><span class="sxs-lookup"><span data-stu-id="04eb7-199">Your request could not be automatically processed.</span></span> <span data-ttu-id="04eb7-200">Neem contact op met de ondersteuning en geef de aanvraag-id op:<requestId></span><span class="sxs-lookup"><span data-stu-id="04eb7-200">Contact Support and provide the Request ID: <requestId></span></span> |

### <a name="check-the-image"></a><span data-ttu-id="04eb7-201">De afbeelding controleren</span><span class="sxs-lookup"><span data-stu-id="04eb7-201">Check the image</span></span>

<span data-ttu-id="04eb7-202">Als uw apparaat afkomstig is van een Microsoft Managed Desktop-partnerleverancier, moet de afbeelding correct zijn.</span><span class="sxs-lookup"><span data-stu-id="04eb7-202">If your device has come from a Microsoft Managed Desktop partner supplier, the image should be correct.</span></span>

<span data-ttu-id="04eb7-203">U bent ook van harte welkom om de afbeelding alleen toe te passen als u dat liever hebt.</span><span class="sxs-lookup"><span data-stu-id="04eb7-203">You’re also welcome to apply the image on your own if you prefer.</span></span> <span data-ttu-id="04eb7-204">Neem om aan de slag te gaan contact op met de Microsoft-vertegenwoordiger waarmee u werkt en geeft u de locatie en stappen voor het toepassen van de afbeelding.</span><span class="sxs-lookup"><span data-stu-id="04eb7-204">To get started, contact the Microsoft representative you’re working with and they will provide you the location and steps for applying the image.</span></span>

### <a name="deliver-the-device"></a><span data-ttu-id="04eb7-205">Het apparaat leveren</span><span class="sxs-lookup"><span data-stu-id="04eb7-205">Deliver the device</span></span>

> [!IMPORTANT]
> <span data-ttu-id="04eb7-206">Voordat u het apparaat aan uw gebruiker overhandigt, moet u ervoor zorgen dat u de [juiste licenties](../get-ready/prerequisites.md) voor die gebruiker hebt verkregen en toegepast.</span><span class="sxs-lookup"><span data-stu-id="04eb7-206">Before you hand off the device to your user, make sure you have obtained and applied the [appropriate licenses](../get-ready/prerequisites.md) for that user.</span></span>

<span data-ttu-id="04eb7-207">Als alle licenties worden toegepast, u [uw gebruikers klaar maken om apparaten te gebruiken,](get-started-devices.md)en vervolgens kan uw gebruiker het apparaat opstarten en doorgaan met de Windows-installatie-ervaring.</span><span class="sxs-lookup"><span data-stu-id="04eb7-207">If all the licenses are applied, you can [get your users ready to use devices](get-started-devices.md), and then your user can start up the device and proceed through the Windows setup experience.</span></span>






