---
title: Stappen voor partners om apparaten te registreren
description: Hoe partners apparaten kunnen registreren zodat ze kunnen worden beheerd door Microsoft Managed Desktop
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: dc446281e8a791b59a9ac97592ff6a53dcde310c
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/07/2020
ms.locfileid: "42806827"
---
# <a name="steps-for-partners-to-register-devices"></a><span data-ttu-id="ec6b3-103">Stappen voor partners om apparaten te registreren</span><span class="sxs-lookup"><span data-stu-id="ec6b3-103">Steps for Partners to register devices</span></span>


<span data-ttu-id="ec6b3-104">In dit onderwerp worden de stappen beschreven die Partners moeten volgen om apparaten te registreren.</span><span class="sxs-lookup"><span data-stu-id="ec6b3-104">This topic describes the steps for Partners to follow to register devices.</span></span> <span data-ttu-id="ec6b3-105">Het proces voor het zelf registreren van apparaten is gedocumenteerd in [Register-apparaten in Microsoft Managed Desktop zelf.](register-devices-self.md)</span><span class="sxs-lookup"><span data-stu-id="ec6b3-105">The process for registering devices yourself is documented in [Register devices in Microsoft Managed Desktop yourself](register-devices-self.md).</span></span>



## <a name="prepare-for-registration"></a><span data-ttu-id="ec6b3-106">Bereid je voor op registratie</span><span class="sxs-lookup"><span data-stu-id="ec6b3-106">Prepare for registration</span></span> 
<span data-ttu-id="ec6b3-107">Voordat u de registratie voor een klant voltooit, moet u eerst een relatie met hen aangaan in het [Partner Center.](https://partner.microsoft.com/dashboard)</span><span class="sxs-lookup"><span data-stu-id="ec6b3-107">Before completing registration for a customer, you must first establish a relationship with them at the [Partner Center](https://partner.microsoft.com/dashboard).</span></span> <span data-ttu-id="ec6b3-108">Selecteer **gedelegeerde beheerbevoegdheden voor Azure Active Directory en Office 365.**</span><span class="sxs-lookup"><span data-stu-id="ec6b3-108">Be sure to select **Include delegated administration privileges for Azure Active Directory and Office 365**.</span></span> <span data-ttu-id="ec6b3-109">Meer informatie bij [Partner Center help](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer).</span><span class="sxs-lookup"><span data-stu-id="ec6b3-109">Learn more at [Partner Center help](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer).</span></span>

<span data-ttu-id="ec6b3-110">Als u de registratie voor uw klant wilt voltooien, maakt u eerst een CSV-bestand.</span><span class="sxs-lookup"><span data-stu-id="ec6b3-110">To complete registration for your customer, first create a CSV file.</span></span>

>[!NOTE]
><span data-ttu-id="ec6b3-111">Voor uw gemak u een [voorbeeld CSV-bestand](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-partner.csv) downloaden voor deze *Partner-versie.*</span><span class="sxs-lookup"><span data-stu-id="ec6b3-111">For your convenience, you can download a [sample CSV file](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-partner.csv) for this *Partner version*.</span></span>

<span data-ttu-id="ec6b3-112">Uw bestand moet **exact dezelfde kolomkoppen** bevatten als het voorbeeld (fabrikant, model, enz.), maar uw eigen gegevens voor de andere rijen.</span><span class="sxs-lookup"><span data-stu-id="ec6b3-112">Your file needs to include the **exact same column headings** as the sample one (Manufacturer, Model, etc.), but your own data for the other rows.</span></span> <span data-ttu-id="ec6b3-113">Als u de sjabloon gebruikt, opent u deze in een tekstbewerkingstool zoals Kladblok en overweegt u alle gegevens alleen in rij 1 te laten, alleen gegevens invoeren in rijen 2 en lager.</span><span class="sxs-lookup"><span data-stu-id="ec6b3-113">If you use the template, open it in a text editing tool such as Notepad, and consider leaving all the data in row 1 alone, only entering data in rows 2 and below.</span></span> 
    
  ```
 Manufacturer,Model,Serial Number
  SpiralOrbit,ContosoABC,000000000000
  
  
  ```




>[!NOTE]
><span data-ttu-id="ec6b3-114">Deze indeling is alleen voor het partnerproces.</span><span class="sxs-lookup"><span data-stu-id="ec6b3-114">This format is only for the Partner process.</span></span> <span data-ttu-id="ec6b3-115">Het proces voor zelfregistratie wordt zelf gedocumenteerd in [Register-apparaten in Microsoft Managed Desktop.](register-devices-self.md)</span><span class="sxs-lookup"><span data-stu-id="ec6b3-115">The process for self-registration is documented in [Register devices in Microsoft Managed Desktop yourself](register-devices-self.md).</span></span>

>[!IMPORTANT]
><span data-ttu-id="ec6b3-116">Deze waarden moeten exact overeenkomen met de waarden van de fabrikant van SMBIOS, inclusief hoofdletters en speciale tekens.</span><span class="sxs-lookup"><span data-stu-id="ec6b3-116">These values must match the manufacturer values from SMBIOS exactly, including capitalization and special characters.</span></span> 

- <span data-ttu-id="ec6b3-117">Fabrikant van het apparaat (voorbeeld: SpiralOrbit)</span><span class="sxs-lookup"><span data-stu-id="ec6b3-117">Device manufacturer (example: SpiralOrbit)</span></span> 
- <span data-ttu-id="ec6b3-118">Apparaatmodel (voorbeeld: ContosoABC)</span><span class="sxs-lookup"><span data-stu-id="ec6b3-118">Device model (example: ContosoABC)</span></span>
- <span data-ttu-id="ec6b3-119">Serienummer van het apparaat</span><span class="sxs-lookup"><span data-stu-id="ec6b3-119">Device serial number</span></span>

## <a name="register-devices-by-using-the-azure-portal"></a><span data-ttu-id="ec6b3-120">Apparaten registreren met behulp van de Azure Portal</span><span class="sxs-lookup"><span data-stu-id="ec6b3-120">Register devices by using the Azure Portal</span></span>

<span data-ttu-id="ec6b3-121">Registreren met behulp van de Azure Portal is hetzelfde als voor selfservice, behalve dat u de portal anders opent.</span><span class="sxs-lookup"><span data-stu-id="ec6b3-121">Registering by using the Azure Portal is the same as for self-service, except you access the portal differently.</span></span> <span data-ttu-id="ec6b3-122">Voer de volgende stappen uit:</span><span class="sxs-lookup"><span data-stu-id="ec6b3-122">Follow these steps:</span></span>

1. <span data-ttu-id="ec6b3-123">Navigeren naar [partnercentrum](https://partner.microsoft.com/dashboard)</span><span class="sxs-lookup"><span data-stu-id="ec6b3-123">Navigate to [Partner Center](https://partner.microsoft.com/dashboard)</span></span>
2. <span data-ttu-id="ec6b3-124">Selecteer **Klanten**.</span><span class="sxs-lookup"><span data-stu-id="ec6b3-124">Select **Customers**.</span></span>
3. <span data-ttu-id="ec6b3-125">Selecteer de klant die u wilt beheren.</span><span class="sxs-lookup"><span data-stu-id="ec6b3-125">Select the customer you want to manage.</span></span>
4. <span data-ttu-id="ec6b3-126">Selecteer **Servicebeheer**.</span><span class="sxs-lookup"><span data-stu-id="ec6b3-126">Select **Service Administration**.</span></span>
5. <span data-ttu-id="ec6b3-127">Selecteer **Intune**.</span><span class="sxs-lookup"><span data-stu-id="ec6b3-127">Select **Intune**.</span></span>
6. <span data-ttu-id="ec6b3-128">Zoek naar 'mmd' in het bovenste zoekvak van de Azure-portal.</span><span class="sxs-lookup"><span data-stu-id="ec6b3-128">Search for "mmd" in the top search box of the Azure portal.</span></span>
7. <span data-ttu-id="ec6b3-129">Selecteer **Apparaten**.</span><span class="sxs-lookup"><span data-stu-id="ec6b3-129">Select **Devices**.</span></span>
8. <span data-ttu-id="ec6b3-130">Geef in **Het uploaden**van bestanden een pad naar het CSV-bestand dat u eerder hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="ec6b3-130">In **File upload**, provide a path to the CSV file you created previously.</span></span>
9. <span data-ttu-id="ec6b3-131">Optioneel u een **order-id** of **aankoop-id** toevoegen voor uw eigen trackingdoeleinden.</span><span class="sxs-lookup"><span data-stu-id="ec6b3-131">Optionally, you can add an **Order ID** or **Purchase ID** for your own tracking purposes.</span></span> <span data-ttu-id="ec6b3-132">Er zijn geen opmaakvereisten voor deze waarden.</span><span class="sxs-lookup"><span data-stu-id="ec6b3-132">There are no format requirements for these values.</span></span>
10. <span data-ttu-id="ec6b3-133">Selecteer **Apparaten registreren**.</span><span class="sxs-lookup"><span data-stu-id="ec6b3-133">Select **Register devices**.</span></span> <span data-ttu-id="ec6b3-134">Het systeem voegt de apparaten toe aan uw lijst met apparaten op het **apparaatblad**, gemarkeerd als **registratie in behandeling.**</span><span class="sxs-lookup"><span data-stu-id="ec6b3-134">The system will add the devices to your list of devices on the **Devices blade**, marked as **Registration Pending**.</span></span> <span data-ttu-id="ec6b3-135">Registratie duurt meestal minder dan 10 minuten, en wanneer succesvol het apparaat zal worden weergegeven als **Klaar voor de gebruiker** wat betekent dat het klaar is en wachten op een eindgebruiker om te beginnen met het gebruik.</span><span class="sxs-lookup"><span data-stu-id="ec6b3-135">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for an end-user to start using.</span></span>


<span data-ttu-id="ec6b3-136">U de voortgang van apparaatregistratie controleren op de hoofdpagina **Microsoft Managed Desktop - Devices.**</span><span class="sxs-lookup"><span data-stu-id="ec6b3-136">You can monitor the progress of device registration on the main **Microsoft Managed Desktop - Devices** page.</span></span> <span data-ttu-id="ec6b3-137">Mogelijke staten die daar worden gemeld zijn:</span><span class="sxs-lookup"><span data-stu-id="ec6b3-137">Possible states reported there include:</span></span>

| <span data-ttu-id="ec6b3-138">Status</span><span class="sxs-lookup"><span data-stu-id="ec6b3-138">State</span></span> | <span data-ttu-id="ec6b3-139">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="ec6b3-139">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="ec6b3-140">Inschrijving in behandeling</span><span class="sxs-lookup"><span data-stu-id="ec6b3-140">Registration pending</span></span> | <span data-ttu-id="ec6b3-141">Registratie is nog niet gedaan.</span><span class="sxs-lookup"><span data-stu-id="ec6b3-141">Registration is not done yet.</span></span> <span data-ttu-id="ec6b3-142">Kom later terug.</span><span class="sxs-lookup"><span data-stu-id="ec6b3-142">Check back later.</span></span> |
| <span data-ttu-id="ec6b3-143">Registratie is mislukt</span><span class="sxs-lookup"><span data-stu-id="ec6b3-143">Registration failed</span></span> | <span data-ttu-id="ec6b3-144">Registratie kon niet worden voltooid.</span><span class="sxs-lookup"><span data-stu-id="ec6b3-144">Registration could not be completed.</span></span> <span data-ttu-id="ec6b3-145">Raadpleeg [apparaatregistratie oplossen](register-devices-self.md#troubleshooting-device-registration) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="ec6b3-145">Refer to [Troubleshooting device registration](register-devices-self.md#troubleshooting-device-registration) for more information.</span></span> |
| <span data-ttu-id="ec6b3-146">Klaar voor gebruiker</span><span class="sxs-lookup"><span data-stu-id="ec6b3-146">Ready for user</span></span> | <span data-ttu-id="ec6b3-147">Registratie geslaagd en het apparaat is nu klaar om te worden geleverd aan de eindgebruiker.</span><span class="sxs-lookup"><span data-stu-id="ec6b3-147">Registration succeeded and the device is now ready to be delivered to the end user.</span></span> <span data-ttu-id="ec6b3-148">Microsoft Managed Desktop begeleidt hen door de eerste set-up, dus u hoeft geen verdere voorbereidingen te treffen.</span><span class="sxs-lookup"><span data-stu-id="ec6b3-148">Microsoft Managed Desktop will guide them through first time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="ec6b3-149">Actief</span><span class="sxs-lookup"><span data-stu-id="ec6b3-149">Active</span></span> | <span data-ttu-id="ec6b3-150">Het apparaat is geleverd aan de eindgebruiker en ze hebben zich geregistreerd bij uw tenant.</span><span class="sxs-lookup"><span data-stu-id="ec6b3-150">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="ec6b3-151">Dit geeft ook aan dat ze het apparaat regelmatig gebruiken.</span><span class="sxs-lookup"><span data-stu-id="ec6b3-151">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="ec6b3-152">Inactief</span><span class="sxs-lookup"><span data-stu-id="ec6b3-152">Inactive</span></span> | <span data-ttu-id="ec6b3-153">Het apparaat is geleverd aan de eindgebruiker en ze hebben zich geregistreerd bij uw tenant.</span><span class="sxs-lookup"><span data-stu-id="ec6b3-153">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="ec6b3-154">Ze hebben het apparaat echter niet onlangs (in de afgelopen 7 dagen) gebruikt.</span><span class="sxs-lookup"><span data-stu-id="ec6b3-154">However, they have not used the device recently (in the last 7 days).</span></span>  |



## <a name="troubleshooting"></a><span data-ttu-id="ec6b3-155">Problemen oplossen</span><span class="sxs-lookup"><span data-stu-id="ec6b3-155">Troubleshooting</span></span>

| <span data-ttu-id="ec6b3-156">Foutbericht</span><span class="sxs-lookup"><span data-stu-id="ec6b3-156">Error message</span></span> | <span data-ttu-id="ec6b3-157">Details</span><span class="sxs-lookup"><span data-stu-id="ec6b3-157">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="ec6b3-158">Apparaat niet gevonden</span><span class="sxs-lookup"><span data-stu-id="ec6b3-158">Device not found</span></span> | <span data-ttu-id="ec6b3-159">We konden dit apparaat niet registreren omdat we geen overeenkomst konden vinden voor de meegeleverde fabrikant, model of serienummer.</span><span class="sxs-lookup"><span data-stu-id="ec6b3-159">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="ec6b3-160">Bevestig deze waarden met uw leverancier van apparaten.</span><span class="sxs-lookup"><span data-stu-id="ec6b3-160">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="ec6b3-161">Hardwarehash niet geldig</span><span class="sxs-lookup"><span data-stu-id="ec6b3-161">Hardware hash not valid</span></span> | <span data-ttu-id="ec6b3-162">De hardwarehash die u voor dit apparaat hebt opgegeven, is niet correct opgemaakt.</span><span class="sxs-lookup"><span data-stu-id="ec6b3-162">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="ec6b3-163">Controleer de hardwarehash dubbel en stuur deze vervolgens opnieuw in.</span><span class="sxs-lookup"><span data-stu-id="ec6b3-163">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="ec6b3-164">Apparaat dat al is geregistreerd</span><span class="sxs-lookup"><span data-stu-id="ec6b3-164">Device already registered</span></span> | <span data-ttu-id="ec6b3-165">Dit apparaat is al geregistreerd bij uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="ec6b3-165">This device is already registered to your organization.</span></span> <span data-ttu-id="ec6b3-166">Geen verdere actie vereist.</span><span class="sxs-lookup"><span data-stu-id="ec6b3-166">No further action required.</span></span> |
| <span data-ttu-id="ec6b3-167">Apparaat dat door een andere organisatie wordt geclaimd</span><span class="sxs-lookup"><span data-stu-id="ec6b3-167">Device claimed by another organization</span></span> | <span data-ttu-id="ec6b3-168">Dit apparaat is al geclaimd door een andere organisatie.</span><span class="sxs-lookup"><span data-stu-id="ec6b3-168">This device has already been claimed by another organization.</span></span> <span data-ttu-id="ec6b3-169">Neem contact op met uw leverancier van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="ec6b3-169">Check with your device supplier.</span></span> |
| <span data-ttu-id="ec6b3-170">Onverwachte fout</span><span class="sxs-lookup"><span data-stu-id="ec6b3-170">Unexpected error</span></span> | <span data-ttu-id="ec6b3-171">Uw aanvraag kan niet automatisch worden verwerkt.</span><span class="sxs-lookup"><span data-stu-id="ec6b3-171">Your request could not be automatically processed.</span></span> <span data-ttu-id="ec6b3-172">Neem contact<support link>op met ondersteuning ( ) en geef de aanvraag-id:<requestId></span><span class="sxs-lookup"><span data-stu-id="ec6b3-172">Contact Support (<support link>) and provide the Request ID: <requestId></span></span> |
