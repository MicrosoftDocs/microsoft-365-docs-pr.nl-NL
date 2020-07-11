---
title: Nieuwe apparaten zelf registreren
description: Registreer apparaten zelf zodat ze kunnen worden beheerd door Microsoft Managed Desktop
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 3c43c42ba2cb1feb339ad61b76d28fde4ed94298
ms.sourcegitcommit: a5ed189fa789975f8c3ed39db1d52f2ef7d671aa
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/10/2020
ms.locfileid: "45101657"
---
# <a name="register-new-devices-yourself"></a><span data-ttu-id="f6bb5-103">Nieuwe apparaten zelf registreren</span><span class="sxs-lookup"><span data-stu-id="f6bb5-103">Register new devices yourself</span></span>

<span data-ttu-id="f6bb5-104">Microsoft Managed Desktop kan werken met gloednieuwe apparaten of u apparaten die u mogelijk al hebt hergebruiken (waarvoor u ze opnieuw moet imagen).</span><span class="sxs-lookup"><span data-stu-id="f6bb5-104">Microsoft Managed Desktop can work with brand-new devices or you can re-use devices you might already have (which will require that you re-image them).</span></span> <span data-ttu-id="f6bb5-105">U apparaten registreren met behulp van de Microsoft Managed Desktop Admin Portal.</span><span class="sxs-lookup"><span data-stu-id="f6bb5-105">You can register devices by using the Microsoft Managed Desktop Admin Portal.</span></span>

> [!NOTE]
> <span data-ttu-id="f6bb5-106">Werken met een partner om apparaten te verkrijgen?</span><span class="sxs-lookup"><span data-stu-id="f6bb5-106">Working with a partner to obtain devices?</span></span> <span data-ttu-id="f6bb5-107">Als dat zo is, hoeft u zich geen zorgen te maken over het verkrijgen van de hardware hashes; Dat regelen ze wel voor je.</span><span class="sxs-lookup"><span data-stu-id="f6bb5-107">If so, you don't need to worry about getting the hardware hashes; they'll take care of that for you.</span></span> <span data-ttu-id="f6bb5-108">Zorg ervoor dat uw partner een relatie met u aangaat in het [Partner Center.](https://partner.microsoft.com/dashboard)</span><span class="sxs-lookup"><span data-stu-id="f6bb5-108">Make sure your partner establishes a relationship with you at the [Partner Center](https://partner.microsoft.com/dashboard).</span></span> <span data-ttu-id="f6bb5-109">Uw partner kan meer informatie leren bij [Partner Center help.](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer)</span><span class="sxs-lookup"><span data-stu-id="f6bb5-109">Your partner can learn more at [Partner Center help](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer).</span></span> <span data-ttu-id="f6bb5-110">Zodra deze relatie tot stand is gekomen, zal uw partner eenvoudig apparaten namens u registreren - geen verdere actie van u vereist.</span><span class="sxs-lookup"><span data-stu-id="f6bb5-110">Once this relationship established, your partner will simply register devices on your behalf – no further action required from you.</span></span> <span data-ttu-id="f6bb5-111">Zie Stappen voor partners om [apparaten te registreren](register-devices-partner.md)als u de gegevens wilt zien of als uw partner vragen heeft.</span><span class="sxs-lookup"><span data-stu-id="f6bb5-111">If you want to see the details, or your partner has questions, see [Steps for Partners to register devices](register-devices-partner.md).</span></span> <span data-ttu-id="f6bb5-112">Zodra de apparaten zijn geregistreerd, u doorgaan met [het controleren van de afbeelding](#check-the-image) en het leveren van de [apparaten](#deliver-the-device) aan uw gebruikers.</span><span class="sxs-lookup"><span data-stu-id="f6bb5-112">Once the devices are registered, you can proceed with [checking the image](#check-the-image) and [delivering the devices](#deliver-the-device) to your users.</span></span>

## <a name="prepare-to-register-brand-new-devices"></a><span data-ttu-id="f6bb5-113">Voorbereiden om gloednieuwe apparaten te registreren</span><span class="sxs-lookup"><span data-stu-id="f6bb5-113">Prepare to register brand-new devices</span></span>


<span data-ttu-id="f6bb5-114">Zodra u de nieuwe apparaten in de hand hebt, volgt u de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="f6bb5-114">Once you have the new devices in hand, you'll follow these steps:</span></span>

1. [<span data-ttu-id="f6bb5-115">Verkrijg de hardwarehash voor elk apparaat.</span><span class="sxs-lookup"><span data-stu-id="f6bb5-115">Obtain the hardware hash for each device.</span></span>](#obtain-the-hardware-hash)
2. [<span data-ttu-id="f6bb5-116">De hash-gegevens samenvoegen</span><span class="sxs-lookup"><span data-stu-id="f6bb5-116">Merge the hash data</span></span>](#merge-hash-data)
3. <span data-ttu-id="f6bb5-117">[Registreer de apparaten in Microsoft Managed Desktop](#register-devices).</span><span class="sxs-lookup"><span data-stu-id="f6bb5-117">[Register the devices in Microsoft Managed Desktop](#register-devices).</span></span>
4. [<span data-ttu-id="f6bb5-118">Controleer of de afbeelding juist is.</span><span class="sxs-lookup"><span data-stu-id="f6bb5-118">Double-check that the image is correct.</span></span>](#check-the-image)
5. [<span data-ttu-id="f6bb5-119">Het apparaat leveren</span><span class="sxs-lookup"><span data-stu-id="f6bb5-119">Deliver the device</span></span>](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a><span data-ttu-id="f6bb5-120">De hardwarehash verkrijgen</span><span class="sxs-lookup"><span data-stu-id="f6bb5-120">Obtain the hardware hash</span></span>

<span data-ttu-id="f6bb5-121">Microsoft Managed Desktop identificeert elk apparaat op unieke wijze door te verwijzen naar de hardwarehash.</span><span class="sxs-lookup"><span data-stu-id="f6bb5-121">Microsoft Managed Desktop identifies each device uniquely by referencing its hardware hash.</span></span> <span data-ttu-id="f6bb5-122">Je hebt drie opties voor het verkrijgen van deze informatie:</span><span class="sxs-lookup"><span data-stu-id="f6bb5-122">You have three options for getting this information:</span></span>

- <span data-ttu-id="f6bb5-123">Vraag uw OEM-leverancier om het AutoPilot-registratiebestand, dat de hardwarehashes bevat.</span><span class="sxs-lookup"><span data-stu-id="f6bb5-123">Ask your OEM supplier for the AutoPilot registration file, which will include the hardware hashes.</span></span>
- <span data-ttu-id="f6bb5-124">Voer een [Windows PowerShell-script](#powershell-script-method) uit op elk apparaat en verzamel de resultaten in een bestand.</span><span class="sxs-lookup"><span data-stu-id="f6bb5-124">Run a [Windows PowerShell script](#powershell-script-method) on each device and collect the results in a file.</span></span>
- <span data-ttu-id="f6bb5-125">Start elk apparaat - maar voltooi de Windows-installatieervaring niet - en [verzamel de hashes op een verwisselbaar flashstation](#flash-drive-method).</span><span class="sxs-lookup"><span data-stu-id="f6bb5-125">Start each device--but don't complete the Windows setup experience--and [collect the hashes on a removable flash drive](#flash-drive-method).</span></span>

#### <a name="powershell-script-method"></a><span data-ttu-id="f6bb5-126">PowerShell-scriptmethode</span><span class="sxs-lookup"><span data-stu-id="f6bb5-126">PowerShell script method</span></span>

1.  <span data-ttu-id="f6bb5-127">Open een PowerShell-prompt met beheerdersrechten.</span><span class="sxs-lookup"><span data-stu-id="f6bb5-127">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="f6bb5-128">Uitvoeren`Install-Script -Name Get-MMDRegistrationInfo`</span><span class="sxs-lookup"><span data-stu-id="f6bb5-128">Run `Install-Script -Name Get-MMDRegistrationInfo`</span></span>
3.  <span data-ttu-id="f6bb5-129">Uitvoeren`powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="f6bb5-129">Run `powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span></span>

#### <a name="flash-drive-method"></a><span data-ttu-id="f6bb5-130">Flash-stationmethode</span><span class="sxs-lookup"><span data-stu-id="f6bb5-130">Flash drive method</span></span>

1. <span data-ttu-id="f6bb5-131">Plaats een ander apparaat dan het apparaat dat u registreert, een USB-station.</span><span class="sxs-lookup"><span data-stu-id="f6bb5-131">On a device other than the one you're registering, insert a USB drive.</span></span>
2. <span data-ttu-id="f6bb5-132">Open een PowerShell-prompt met beheerdersrechten.</span><span class="sxs-lookup"><span data-stu-id="f6bb5-132">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="f6bb5-133">Uitvoeren`Save-Script -Name Get-MMDRegistrationInfo -Path <pathToUsb>`</span><span class="sxs-lookup"><span data-stu-id="f6bb5-133">Run `Save-Script -Name Get-MMDRegistrationInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="f6bb5-134">Schakel het apparaat in dat u registreert, maar *start de installatie-ervaring niet.*</span><span class="sxs-lookup"><span data-stu-id="f6bb5-134">Turn on the device you are registering, but *do not start the setup experience*.</span></span> <span data-ttu-id="f6bb5-135">Als u per ongeluk de installatie-ervaring start, moet u het apparaat opnieuw instellen of opnieuwimen.</span><span class="sxs-lookup"><span data-stu-id="f6bb5-135">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="f6bb5-136">Plaats het USB-station en druk op Shift + F10.</span><span class="sxs-lookup"><span data-stu-id="f6bb5-136">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="f6bb5-137">Open een PowerShell-prompt met beheerdersrechten en voer `cd <pathToUsb>` vervolgens uit .</span><span class="sxs-lookup"><span data-stu-id="f6bb5-137">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="f6bb5-138">Uitvoeren`Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span><span class="sxs-lookup"><span data-stu-id="f6bb5-138">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="f6bb5-139">Uitvoeren`.\Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="f6bb5-139">Run `.\Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span></span>
9. <span data-ttu-id="f6bb5-140">Verwijder het USB-station en schakel het apparaat uit door`shutdown -s -t 0`</span><span class="sxs-lookup"><span data-stu-id="f6bb5-140">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>

>[!IMPORTANT]
><span data-ttu-id="f6bb5-141">Geef het apparaat dat u opnieuw registreert niet weer aan totdat u de registratie ervoor hebt voltooid.</span><span class="sxs-lookup"><span data-stu-id="f6bb5-141">Do not power on the device you are registering again until you've completed registration for it.</span></span> 


### <a name="merge-hash-data"></a><span data-ttu-id="f6bb5-142">Hash-gegevens samenvoegen</span><span class="sxs-lookup"><span data-stu-id="f6bb5-142">Merge hash data</span></span>

<span data-ttu-id="f6bb5-143">U moet de gegevens in de CSV-bestanden hebben gecombineerd in één bestand om de registratie te voltooien.</span><span class="sxs-lookup"><span data-stu-id="f6bb5-143">You'll need to have the data in the CSV files combined into a single file to complete registration.</span></span> <span data-ttu-id="f6bb5-144">Hier volgt een PowerShell-script om dit eenvoudig te maken:</span><span class="sxs-lookup"><span data-stu-id="f6bb5-144">Here's a sample PowerShell script to make this easy:</span></span>

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`
### <a name="register-devices"></a><span data-ttu-id="f6bb5-145">Apparaten registreren</span><span class="sxs-lookup"><span data-stu-id="f6bb5-145">Register devices</span></span>

<span data-ttu-id="f6bb5-146">Het CSV-bestand moet in een bepaald formaat voor registratie staan.</span><span class="sxs-lookup"><span data-stu-id="f6bb5-146">The CSV file must be in a particular format for registration.</span></span> <span data-ttu-id="f6bb5-147">Als u de gegevens zelf hebt verzameld in de vorige stappen, moet het bestand al in de juiste indeling zijn. als u het bestand bij een leverancier verkrijgt, moet u mogelijk het formaat aanpassen.</span><span class="sxs-lookup"><span data-stu-id="f6bb5-147">If you collected the data yourself in the previous steps, the file should already be in the right format; if you obtain the file from a supplier, you might need to adjust the format.</span></span>

>[!NOTE]
><span data-ttu-id="f6bb5-148">Voor uw gemak u een [voorbeeld van CSV-bestand](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-self.csv)downloaden.</span><span class="sxs-lookup"><span data-stu-id="f6bb5-148">For your convenience, you can download a [sample CSV file](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-self.csv).</span></span>

<span data-ttu-id="f6bb5-149">Uw bestand moet **exact dezelfde kolomkoppen** bevatten als de voorbeeldkoppen (fabrikant, model, enz.), maar uw eigen gegevens voor de andere rijen.</span><span class="sxs-lookup"><span data-stu-id="f6bb5-149">Your file needs to include the **exact same column headings** as the sample one (Manufacturer, Model, etc.), but your own data for the other rows.</span></span> <span data-ttu-id="f6bb5-150">Als u de sjabloon gebruikt, opent u deze in een tekstbewerkingsgereedschap zoals Kladblok en u overwegen alle gegevens in rij 1 alleen te laten, waarbij alleen gegevens in rij 2 en lager worden invoeren.</span><span class="sxs-lookup"><span data-stu-id="f6bb5-150">If you use the template, open it in a text editing tool such as Notepad, and consider leaving all the data in row 1 alone, only entering data in rows 2 and below.</span></span> 
    
  ```
 Manufacturer,Model,Serial Number,Hardware Hash
  SpiralOrbit,ContosoABC,000000000000,dGhpc2RldmljZWlzYW5tbWRkZXZpY2U
  
  
  ```

>[!NOTE]
><span data-ttu-id="f6bb5-151">Als u vergeet een van de voorbeeldgegevens te wijzigen, mislukt de registratie.</span><span class="sxs-lookup"><span data-stu-id="f6bb5-151">If you forget to change any of the sample data, registration will fail.</span></span>

#### <a name="register-devices-by-using-the-admin-portal"></a><span data-ttu-id="f6bb5-152">Apparaten registreren met behulp van de adminportal</span><span class="sxs-lookup"><span data-stu-id="f6bb5-152">Register devices by using the Admin Portal</span></span>

<span data-ttu-id="f6bb5-153">Selecteer **Apparaten** in het linkernavigatiedeelvenster in de Microsoft Managed Desktop [Admin Portal.](https://aka.ms/mmdportal)</span><span class="sxs-lookup"><span data-stu-id="f6bb5-153">From the Microsoft Managed Desktop [Admin Portal](https://aka.ms/mmdportal), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="f6bb5-154">Selecteer **+ Apparaten registreren**; de fly-in opent:</span><span class="sxs-lookup"><span data-stu-id="f6bb5-154">Select **+ Register devices**; the fly-in opens:</span></span>

<span data-ttu-id="f6bb5-155">[![Fly-in na het selecteren van Apparaten registreren, apparaten met kolommen voor toegewezen gebruikers, serienummer, status, laatst geziene datum en leeftijd vermelden](../../media/register-devices-flyin-sterile.png)](../../media/register-devices-flyin-sterile.png)</span><span class="sxs-lookup"><span data-stu-id="f6bb5-155">[![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/register-devices-flyin-sterile.png)](../../media/register-devices-flyin-sterile.png)</span></span>


[//]: # (Helaas is dit niet waar. We kunnen deze notitie verwijderen - maar laat het nu tot we een kans om te chatten over.)

<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


<span data-ttu-id="f6bb5-157">Volg deze stappen:</span><span class="sxs-lookup"><span data-stu-id="f6bb5-157">Follow these steps:</span></span>

1. <span data-ttu-id="f6bb5-158">Geef in **Bestandsupload**een pad op naar het CSV-bestand dat u eerder hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="f6bb5-158">In **File upload**, provide a path to the CSV file you created previously.</span></span>
2. <span data-ttu-id="f6bb5-159">Optioneel u een **bestel-id** of **aankoop-id** toevoegen voor uw eigen trackingdoeleinden.</span><span class="sxs-lookup"><span data-stu-id="f6bb5-159">Optionally, you can add an **Order ID** or **Purchase ID** for your own tracking purposes.</span></span> <span data-ttu-id="f6bb5-160">Er zijn geen indelingsvereisten voor deze waarden.</span><span class="sxs-lookup"><span data-stu-id="f6bb5-160">There are no format requirements for these values.</span></span>
3. <span data-ttu-id="f6bb5-161">Selecteer **Apparaten registreren**.</span><span class="sxs-lookup"><span data-stu-id="f6bb5-161">Select **Register devices**.</span></span> <span data-ttu-id="f6bb5-162">Het systeem voegt de apparaten toe aan uw lijst met apparaten op het **apparaatblad,** gemarkeerd als **Registratie in behandeling.**</span><span class="sxs-lookup"><span data-stu-id="f6bb5-162">The system will add the devices to your list of devices on the **Devices blade**, marked as **Registration Pending**.</span></span> <span data-ttu-id="f6bb5-163">Registratie duurt meestal minder dan 10 minuten, en wanneer het apparaat succesvol is, wordt weergegeven als **Klaar voor de gebruiker,** wat betekent dat het klaar is en wacht tot een eindgebruiker begint te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="f6bb5-163">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for an end-user to start using.</span></span>


<span data-ttu-id="f6bb5-164">U de voortgang van apparaatregistratie volgen op de hoofdpagina **van Microsoft Managed Desktop - Devices.**</span><span class="sxs-lookup"><span data-stu-id="f6bb5-164">You can monitor the progress of device registration on the main **Microsoft Managed Desktop - Devices** page.</span></span> <span data-ttu-id="f6bb5-165">Mogelijke staten gemeld zijn er:</span><span class="sxs-lookup"><span data-stu-id="f6bb5-165">Possible states reported there include:</span></span>

| <span data-ttu-id="f6bb5-166">Status</span><span class="sxs-lookup"><span data-stu-id="f6bb5-166">State</span></span> | <span data-ttu-id="f6bb5-167">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="f6bb5-167">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="f6bb5-168">Inschrijving in behandeling</span><span class="sxs-lookup"><span data-stu-id="f6bb5-168">Registration pending</span></span> | <span data-ttu-id="f6bb5-169">Registratie is nog niet gedaan.</span><span class="sxs-lookup"><span data-stu-id="f6bb5-169">Registration is not done yet.</span></span> <span data-ttu-id="f6bb5-170">Kom later terug.</span><span class="sxs-lookup"><span data-stu-id="f6bb5-170">Check back later.</span></span> |
| <span data-ttu-id="f6bb5-171">Registratie is mislukt</span><span class="sxs-lookup"><span data-stu-id="f6bb5-171">Registration failed</span></span> | <span data-ttu-id="f6bb5-172">De inschrijving kon niet worden voltooid.</span><span class="sxs-lookup"><span data-stu-id="f6bb5-172">Registration could not be completed.</span></span> <span data-ttu-id="f6bb5-173">Raadpleeg [de registratie van het apparaat voor probleemoplossing](#troubleshooting-device-registration) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="f6bb5-173">Refer to [Troubleshooting device registration](#troubleshooting-device-registration) for more information.</span></span> |
| <span data-ttu-id="f6bb5-174">Klaar voor de gebruiker</span><span class="sxs-lookup"><span data-stu-id="f6bb5-174">Ready for user</span></span> | <span data-ttu-id="f6bb5-175">De registratie is geslaagd en het apparaat is nu klaar om te worden geleverd aan de eindgebruiker.</span><span class="sxs-lookup"><span data-stu-id="f6bb5-175">Registration succeeded and the device is now ready to be delivered to the end user.</span></span> <span data-ttu-id="f6bb5-176">Microsoft Managed Desktop begeleidt ze door de eerste tijdset-up, dus u hoeft geen verdere voorbereidingen te treffen.</span><span class="sxs-lookup"><span data-stu-id="f6bb5-176">Microsoft Managed Desktop will guide them through first time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="f6bb5-177">Actief</span><span class="sxs-lookup"><span data-stu-id="f6bb5-177">Active</span></span> | <span data-ttu-id="f6bb5-178">Het apparaat is geleverd aan de eindgebruiker en ze hebben zich geregistreerd bij uw tenant.</span><span class="sxs-lookup"><span data-stu-id="f6bb5-178">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="f6bb5-179">Dit geeft ook aan dat ze het apparaat regelmatig gebruiken.</span><span class="sxs-lookup"><span data-stu-id="f6bb5-179">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="f6bb5-180">Inactief</span><span class="sxs-lookup"><span data-stu-id="f6bb5-180">Inactive</span></span> | <span data-ttu-id="f6bb5-181">Het apparaat is geleverd aan de eindgebruiker en ze hebben zich geregistreerd bij uw tenant.</span><span class="sxs-lookup"><span data-stu-id="f6bb5-181">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="f6bb5-182">Ze hebben het apparaat echter niet onlangs (in de afgelopen 7 dagen) gebruikt.</span><span class="sxs-lookup"><span data-stu-id="f6bb5-182">However, they have not used the device recently (in the last 7 days).</span></span>  | 

#### <a name="troubleshooting-device-registration"></a><span data-ttu-id="f6bb5-183">Apparaatregistratie oplossen</span><span class="sxs-lookup"><span data-stu-id="f6bb5-183">Troubleshooting device registration</span></span>

| <span data-ttu-id="f6bb5-184">Foutbericht</span><span class="sxs-lookup"><span data-stu-id="f6bb5-184">Error message</span></span> | <span data-ttu-id="f6bb5-185">Details</span><span class="sxs-lookup"><span data-stu-id="f6bb5-185">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="f6bb5-186">Apparaat niet gevonden</span><span class="sxs-lookup"><span data-stu-id="f6bb5-186">Device not found</span></span> | <span data-ttu-id="f6bb5-187">We konden dit apparaat niet registreren omdat we geen overeenkomst konden vinden voor de geleverde fabrikant, het model of het serienummer.</span><span class="sxs-lookup"><span data-stu-id="f6bb5-187">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="f6bb5-188">Bevestig deze waarden met uw apparaatleverancier.</span><span class="sxs-lookup"><span data-stu-id="f6bb5-188">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="f6bb5-189">Hardware hash niet geldig</span><span class="sxs-lookup"><span data-stu-id="f6bb5-189">Hardware hash not valid</span></span> | <span data-ttu-id="f6bb5-190">De hardwarehash die u voor dit apparaat hebt geleverd, is niet correct opgemaakt.</span><span class="sxs-lookup"><span data-stu-id="f6bb5-190">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="f6bb5-191">Controleer de hardware hash en vervolgens opnieuw in te dienen.</span><span class="sxs-lookup"><span data-stu-id="f6bb5-191">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="f6bb5-192">Apparaat al geregistreerd</span><span class="sxs-lookup"><span data-stu-id="f6bb5-192">Device already registered</span></span> | <span data-ttu-id="f6bb5-193">Dit apparaat is al geregistreerd bij uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="f6bb5-193">This device is already registered to your organization.</span></span> <span data-ttu-id="f6bb5-194">Geen verdere actie vereist.</span><span class="sxs-lookup"><span data-stu-id="f6bb5-194">No further action required.</span></span> |
| <span data-ttu-id="f6bb5-195">Apparaat geclaimd door een andere organisatie</span><span class="sxs-lookup"><span data-stu-id="f6bb5-195">Device claimed by another organization</span></span> | <span data-ttu-id="f6bb5-196">Dit apparaat is al geclaimd door een andere organisatie.</span><span class="sxs-lookup"><span data-stu-id="f6bb5-196">This device has already been claimed by another organization.</span></span> <span data-ttu-id="f6bb5-197">Neem contact op met uw apparaatleverancier.</span><span class="sxs-lookup"><span data-stu-id="f6bb5-197">Check with your device supplier.</span></span> |
| <span data-ttu-id="f6bb5-198">Onverwachte fout</span><span class="sxs-lookup"><span data-stu-id="f6bb5-198">Unexpected error</span></span> | <span data-ttu-id="f6bb5-199">Uw aanvraag kan niet automatisch worden verwerkt.</span><span class="sxs-lookup"><span data-stu-id="f6bb5-199">Your request could not be automatically processed.</span></span> <span data-ttu-id="f6bb5-200">Neem contact op met de ondersteuning en geef de aanvraag-id op:<requestId></span><span class="sxs-lookup"><span data-stu-id="f6bb5-200">Contact Support and provide the Request ID: <requestId></span></span> |

### <a name="check-the-image"></a><span data-ttu-id="f6bb5-201">De afbeelding controleren</span><span class="sxs-lookup"><span data-stu-id="f6bb5-201">Check the image</span></span>

<span data-ttu-id="f6bb5-202">Als uw apparaat afkomstig is van een microsoft managed desktop-partnerleverancier, moet de afbeelding correct zijn.</span><span class="sxs-lookup"><span data-stu-id="f6bb5-202">If your device has come from a Microsoft Managed Desktop partner supplier, the image should be correct.</span></span>

<span data-ttu-id="f6bb5-203">U bent ook van harte welkom om de afbeelding toe te passen op uw eigen als u dat liever.</span><span class="sxs-lookup"><span data-stu-id="f6bb5-203">You’re also welcome to apply the image on your own if you prefer.</span></span> <span data-ttu-id="f6bb5-204">Neem voor u contact op met de Microsoft-vertegenwoordiger waarmee u werkt en deze biedt u de locatie en stappen voor het toepassen van de afbeelding.</span><span class="sxs-lookup"><span data-stu-id="f6bb5-204">To get started, contact the Microsoft representative you’re working with and they will provide you the location and steps for applying the image.</span></span>

### <a name="deliver-the-device"></a><span data-ttu-id="f6bb5-205">Het apparaat leveren</span><span class="sxs-lookup"><span data-stu-id="f6bb5-205">Deliver the device</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f6bb5-206">Voordat u het apparaat aan uw gebruiker overhandigt, moet u ervoor zorgen dat u de [juiste licenties](../get-ready/prerequisites.md) voor die gebruiker hebt verkregen en toegepast.</span><span class="sxs-lookup"><span data-stu-id="f6bb5-206">Before you hand off the device to your user, make sure you have obtained and applied the [appropriate licenses](../get-ready/prerequisites.md) for that user.</span></span>

<span data-ttu-id="f6bb5-207">Als alle licenties worden toegepast, u [uw gebruikers klaar maken om apparaten te gebruiken,](get-started-devices.md)en vervolgens kan uw gebruiker het apparaat opstarten en doorgaan met de Windows-installatieervaring.</span><span class="sxs-lookup"><span data-stu-id="f6bb5-207">If all the licenses are applied, you can [get your users ready to use devices](get-started-devices.md), and then your user can start up the device and proceed through the Windows setup experience.</span></span>






