---
title: Microsoft Defender voor Endpoint Device Control Verwisselbare Storage beveiliging
description: Inzicht in de 'mogelijkheden die helpen voorkomen dat gebruiker of computer of beide niet-geautoriseerde verwisselbare opslagmedia gebruiken
keywords: verwisselbare opslagmedia
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-smandalika
author: v-smandalika
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: ec5cfa78852d65db808c4e853f90f5639df25d6f
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300148"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-protection"></a><span data-ttu-id="2b6c6-104">Microsoft Defender voor Endpoint Device Control Verwisselbare Storage beveiliging</span><span class="sxs-lookup"><span data-stu-id="2b6c6-104">Microsoft Defender for Endpoint Device Control Removable Storage Protection</span></span>

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="2b6c6-105">Microsoft Defender voor Endpoint Device Control Verwisselbare Storage beveiliging voorkomt dat gebruiker of computer of beide niet-geautoriseerde verwisselbare opslagmedia gebruiken.</span><span class="sxs-lookup"><span data-stu-id="2b6c6-105">Microsoft Defender for Endpoint Device Control Removable Storage Protection prevents user or machine or both from using unauthorized removable storage media.</span></span>

<span data-ttu-id="2b6c6-106">**Microsoft Defender for Endpoint Removable Storage Protection**</span><span class="sxs-lookup"><span data-stu-id="2b6c6-106">**Microsoft Defender for Endpoint Removable Storage Protection**</span></span>


|<span data-ttu-id="2b6c6-107">Beleid</span><span class="sxs-lookup"><span data-stu-id="2b6c6-107">Policy</span></span>  |<span data-ttu-id="2b6c6-108">Mogelijkheid</span><span class="sxs-lookup"><span data-stu-id="2b6c6-108">Capability</span></span> |<span data-ttu-id="2b6c6-109">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="2b6c6-109">Description</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="2b6c6-110">Apparaatinstallatie</span><span class="sxs-lookup"><span data-stu-id="2b6c6-110">Device Installation</span></span>    |  <span data-ttu-id="2b6c6-111">Installatie voorkomen met of zonder uitsluiting - Specifieke apparaten toestaan op basis van verschillende eigenschappen; Zie de sectie [Apparaateigenschappen](#device-properties) hieronder voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="2b6c6-111">Prevent installation with or without exclusion - Allow specific devices based on various properties; for more information, see the [Device properties](#device-properties) section below.</span></span>        |    <span data-ttu-id="2b6c6-112">Werkt op de computer: Verschillende gebruikers die zich aanmelden bij dezelfde computer, worden beperkt door hetzelfde beleid.</span><span class="sxs-lookup"><span data-stu-id="2b6c6-112">Works on the machine: Different users logging in to the same machine will be restricted by the same policy.</span></span> <span data-ttu-id="2b6c6-113">Zie Usb-apparaten en andere [verwisselbare media beheren](control-usb-devices-using-intune.md)met Microsoft Defender voor Eindpunt voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="2b6c6-113">For information, see [How to control USB devices and other removable media using Microsoft Defender for Endpoint](control-usb-devices-using-intune.md).</span></span>     |
|<span data-ttu-id="2b6c6-114">Verwisselbare opslagToegangsbesturingselement</span><span class="sxs-lookup"><span data-stu-id="2b6c6-114">Removable storage Access Control</span></span>      | <span data-ttu-id="2b6c6-115">(1) Controleer lees- of schrijf- of uitvoertoegang tot verwisselbare opslag op basis van verschillende apparaateigenschappen, met of zonder uitzondering.</span><span class="sxs-lookup"><span data-stu-id="2b6c6-115">(1) Audit Read or Write or Execute access to removable storage based on various device properties, with or without exception.</span></span> <span data-ttu-id="2b6c6-116">Zie de sectie Apparaateigenschappen hieronder [voor](#device-properties) meer informatie.</span><span class="sxs-lookup"><span data-stu-id="2b6c6-116">For more information, see the [Device properties](#device-properties) section below.</span></span> <span data-ttu-id="2b6c6-117">(2) Lees- of schrijf- of uitvoertoegang voorkomen met of zonder uitsluiting - Specifieke apparaten toestaan op basis van verschillende apparaateigenschappen; Zie de sectie Apparaateigenschappen hieronder [](#device-properties) voor meer informatie over de apparaateigenschappen.</span><span class="sxs-lookup"><span data-stu-id="2b6c6-117">(2) Prevent Read or Write or Execute access with or without exclusion - Allow specific devices based on various device properties; for more information on the device properties, see the [Device properties](#device-properties) section below.</span></span>     |     <span data-ttu-id="2b6c6-118">Werkt op een computer of gebruiker of beide: Sta alleen specifieke personen toe die lees-/schrijf-/uitvoertoegang tot specifieke verwisselbare opslag op een specifieke computer uitvoeren; voor functie in Windows, zie [Verwisselbare opslagToegangsbesturingselement](device-control-removable-storage-access-control.md); zie Apparaatbesturingselement [voor macOS](mac-device-control-overview.md)voor functie in Mac.</span><span class="sxs-lookup"><span data-stu-id="2b6c6-118">Works on either machine or user or both: Only allow specific people performing Read/Write/Execute access to specific removable storage on a specific machine; for feature in Windows, see [Removable storage Access Control](device-control-removable-storage-access-control.md); for feature in Mac, see [Device control for macOS](mac-device-control-overview.md).</span></span>     |
|<span data-ttu-id="2b6c6-119">Verwisselbare opslag van eindpunt DLP</span><span class="sxs-lookup"><span data-stu-id="2b6c6-119">Endpoint DLP Removable storage</span></span>      |    <span data-ttu-id="2b6c6-120">Controleer of waarschuw of voorkom dat een gebruiker een item of informatie kopieert naar verwisselbare media of USB-apparaten.</span><span class="sxs-lookup"><span data-stu-id="2b6c6-120">Audit or warn or prevent a user from copying an item or information to removable media or USB device.</span></span>     |  <span data-ttu-id="2b6c6-121">Zie [Microsoft Endpoint DLP](/compliance/endpoint-dlp-learn-about.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="2b6c6-121">For more information, see [Microsoft Endpoint DLP](/compliance/endpoint-dlp-learn-about.md).</span></span>       |
|<span data-ttu-id="2b6c6-122">BitLocker</span><span class="sxs-lookup"><span data-stu-id="2b6c6-122">BitLocker</span></span>    |     <span data-ttu-id="2b6c6-123">Gegevens blokkeren die moeten worden geschreven naar verwisselbare stations die niet BitLocker beveiligd: Toegang tot verwisselbare stations blokkeren, tenzij ze zijn versleuteld op een computer die eigendom is van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="2b6c6-123">Block data that are to be written to removable drives that aren't BitLocker protected: Block access to removable drives unless they were encrypted on a computer owned by your organization.</span></span>    |   <span data-ttu-id="2b6c6-124">Zie voor meer informatie BitLocker - [Verwisselbaar station Instellingen.](/mem/intune/protect/endpoint-security-disk-encryption-profile-settings#bitlocker---removable-drive-settings.md)</span><span class="sxs-lookup"><span data-stu-id="2b6c6-124">For more information, see BitLocker – [Removable Drive Settings](/mem/intune/protect/endpoint-security-disk-encryption-profile-settings#bitlocker---removable-drive-settings.md).</span></span>      |

## <a name="device-properties"></a><span data-ttu-id="2b6c6-125">Apparaateigenschappen</span><span class="sxs-lookup"><span data-stu-id="2b6c6-125">Device properties</span></span>

<span data-ttu-id="2b6c6-126">Met Microsoft Defender for Endpoint Device Control Verwisselbare Storage Protection kunt u de verwisselbare opslagtoegang beperken op basis van de eigenschappen die in de onderstaande tabel worden beschreven:</span><span class="sxs-lookup"><span data-stu-id="2b6c6-126">Microsoft Defender for Endpoint Device Control Removable Storage Protection allows you to restrict the removable storage access based on the properties described in the table below:</span></span>


|<span data-ttu-id="2b6c6-127">Eigenschapsnaam</span><span class="sxs-lookup"><span data-stu-id="2b6c6-127">Property Name</span></span>  |<span data-ttu-id="2b6c6-128">Toepasselijke beleidsregels</span><span class="sxs-lookup"><span data-stu-id="2b6c6-128">Applicable Policies</span></span>  |<span data-ttu-id="2b6c6-129">Van toepassing op besturingssystemen</span><span class="sxs-lookup"><span data-stu-id="2b6c6-129">Applies to Operating Systems</span></span>  |<span data-ttu-id="2b6c6-130">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="2b6c6-130">Description</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="2b6c6-131">Apparaatklasse</span><span class="sxs-lookup"><span data-stu-id="2b6c6-131">Device Class</span></span>    |     [<span data-ttu-id="2b6c6-132">USB-apparaten en andere verwisselbare media beheren met Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="2b6c6-132">How to control USB devices and other removable media using Microsoft Defender for Endpoint</span></span>](control-usb-devices-using-intune.md)     |   <span data-ttu-id="2b6c6-133">Windows</span><span class="sxs-lookup"><span data-stu-id="2b6c6-133">Windows</span></span>      |  <span data-ttu-id="2b6c6-134">Zie apparaatconfiguratieklasse voor informatie over [apparaat-id-indelingen.](/windows-hardware/drivers/install/system-defined-device-setup-classes-available-to-vendors)</span><span class="sxs-lookup"><span data-stu-id="2b6c6-134">For information about Device ID formats, see [device setup class](/windows-hardware/drivers/install/system-defined-device-setup-classes-available-to-vendors).</span></span> <span data-ttu-id="2b6c6-135">**Opmerking:** Apparaatinstallatie kan worden toegepast op alle apparaten, niet alleen op verwisselbare opslag.</span><span class="sxs-lookup"><span data-stu-id="2b6c6-135">**Note**: Device Installation can be applied to any devices, not only Removable storage.</span></span>       |
|<span data-ttu-id="2b6c6-136">Primaire id</span><span class="sxs-lookup"><span data-stu-id="2b6c6-136">Primary ID</span></span>   |     <span data-ttu-id="2b6c6-137">Verwisselbare opslagToegangsbesturingselement</span><span class="sxs-lookup"><span data-stu-id="2b6c6-137">Removable storage Access Control</span></span>    |   <span data-ttu-id="2b6c6-138">Windows</span><span class="sxs-lookup"><span data-stu-id="2b6c6-138">Windows</span></span>      |      <span data-ttu-id="2b6c6-139">De primaire id bevat verwisselbare opslag en cd/dvd.</span><span class="sxs-lookup"><span data-stu-id="2b6c6-139">The Primary ID includes removable storage and CD/DVD.</span></span>   |
|<span data-ttu-id="2b6c6-140">Apparaat-id</span><span class="sxs-lookup"><span data-stu-id="2b6c6-140">Device ID</span></span>     |  <span data-ttu-id="2b6c6-141">[Usb-apparaten en andere verwisselbare media beheren met Microsoft Defender voor Eindpunt;](control-usb-devices-using-intune.md) Verwisselbare opslagToegangsbesturingselement</span><span class="sxs-lookup"><span data-stu-id="2b6c6-141">[How to control USB devices and other removable media using Microsoft Defender for Endpoint](control-usb-devices-using-intune.md); Removable storage Access Control</span></span>       |      <span data-ttu-id="2b6c6-142">Windows</span><span class="sxs-lookup"><span data-stu-id="2b6c6-142">Windows</span></span>   |    <span data-ttu-id="2b6c6-143">Zie Standaard USB-id's [](/windows-hardware/drivers/install/standard-usb-identifiers)voor informatie over apparaat-id-indelingen, bijvoorbeeld USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07</span><span class="sxs-lookup"><span data-stu-id="2b6c6-143">For information about Device ID formats, see [Standard USB Identifiers](/windows-hardware/drivers/install/standard-usb-identifiers), for example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07</span></span>      |
|<span data-ttu-id="2b6c6-144">Hardware-id</span><span class="sxs-lookup"><span data-stu-id="2b6c6-144">Hardware ID</span></span>     |     <span data-ttu-id="2b6c6-145">[Usb-apparaten en andere verwisselbare media beheren met Microsoft Defender voor Eindpunt;](control-usb-devices-using-intune.md) Verwisselbare opslagToegangsbesturingselement</span><span class="sxs-lookup"><span data-stu-id="2b6c6-145">[How to control USB devices and other removable media using Microsoft Defender for Endpoint](control-usb-devices-using-intune.md); Removable storage Access Control</span></span>    |     <span data-ttu-id="2b6c6-146">Windows</span><span class="sxs-lookup"><span data-stu-id="2b6c6-146">Windows</span></span>    |    <span data-ttu-id="2b6c6-147">Een tekenreeks heeft het apparaat in het systeem geïdentificeerd, bijvoorbeeld USBSTOR\DiskGeneric_Flash_Disk______8.07; **Opmerking:** Hardware-id is niet uniek; verschillende apparaten kunnen dezelfde waarde delen.</span><span class="sxs-lookup"><span data-stu-id="2b6c6-147">A string identified the device in the system, for example, USBSTOR\DiskGeneric_Flash_Disk______8.07; **Note**: Hardware ID is not unique; different devices may share same value.</span></span>|
|<span data-ttu-id="2b6c6-148">Exemplaar-id</span><span class="sxs-lookup"><span data-stu-id="2b6c6-148">Instance ID</span></span>    | <span data-ttu-id="2b6c6-149">Apparaatinstallatie; Verwisselbare opslagToegangsbesturingselement</span><span class="sxs-lookup"><span data-stu-id="2b6c6-149">Device Installation; Removable storage Access Control</span></span>     |     <span data-ttu-id="2b6c6-150">Windows</span><span class="sxs-lookup"><span data-stu-id="2b6c6-150">Windows</span></span>    |   <span data-ttu-id="2b6c6-151">Een tekenreeks identificeert het apparaat in het systeem, bijvoorbeeld USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0</span><span class="sxs-lookup"><span data-stu-id="2b6c6-151">A string uniquely identifies the device in the system, for example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0</span></span>      |
|<span data-ttu-id="2b6c6-152">Vriendelijke naam</span><span class="sxs-lookup"><span data-stu-id="2b6c6-152">Friendly Name</span></span>     |     <span data-ttu-id="2b6c6-153">Verwisselbare opslagToegangsbesturingselement</span><span class="sxs-lookup"><span data-stu-id="2b6c6-153">Removable storage Access Control</span></span>    |   <span data-ttu-id="2b6c6-154">Windows</span><span class="sxs-lookup"><span data-stu-id="2b6c6-154">Windows</span></span>      |    <span data-ttu-id="2b6c6-155">Een tekenreeks die is gekoppeld aan het apparaat, bijvoorbeeld Generic Flash Disk USB Device</span><span class="sxs-lookup"><span data-stu-id="2b6c6-155">A string attached to the device, for example, Generic Flash Disk USB Device</span></span>     |
|<span data-ttu-id="2b6c6-156">Leverancier-id/product-id</span><span class="sxs-lookup"><span data-stu-id="2b6c6-156">Vendor ID / Product ID</span></span>     |  <span data-ttu-id="2b6c6-157">Verwisselbare opslagToegangsbesturingselement</span><span class="sxs-lookup"><span data-stu-id="2b6c6-157">Removable storage Access Control</span></span>       |   <span data-ttu-id="2b6c6-158">Windows Mac</span><span class="sxs-lookup"><span data-stu-id="2b6c6-158">Windows Mac</span></span>      |     <span data-ttu-id="2b6c6-159">Leverancier-id is de leveranciercode met vier cijfers die door de USB-commissie aan de leverancier wordt toegewezen.</span><span class="sxs-lookup"><span data-stu-id="2b6c6-159">Vendor ID is the four-digit vendor code that the USB committee assigns to the vendor.</span></span> <span data-ttu-id="2b6c6-160">Product-id is de viercijferige productcode die de leverancier aan het apparaat toewijst. Ondersteunings jokerteken.</span><span class="sxs-lookup"><span data-stu-id="2b6c6-160">Product ID is the four-digit product code that the vendor assigns to the device; Support wildcard.</span></span>    |
|<span data-ttu-id="2b6c6-161">Serienummer</span><span class="sxs-lookup"><span data-stu-id="2b6c6-161">Serial NumberId</span></span>     |     <span data-ttu-id="2b6c6-162">Verwisselbare opslagToegangsbesturingselement</span><span class="sxs-lookup"><span data-stu-id="2b6c6-162">Removable storage Access Control</span></span>    |      <span data-ttu-id="2b6c6-163">Windows Mac</span><span class="sxs-lookup"><span data-stu-id="2b6c6-163">Windows Mac</span></span>   |     <span data-ttu-id="2b6c6-164">Bijvoorbeeld <SerialNumberId>002324B534BCB431B000058A</SerialNumberId></span><span class="sxs-lookup"><span data-stu-id="2b6c6-164">For example, <SerialNumberId>002324B534BCB431B000058A</SerialNumberId></span></span>    |

## <a name="related-topic"></a><span data-ttu-id="2b6c6-165">Verwant onderwerp</span><span class="sxs-lookup"><span data-stu-id="2b6c6-165">Related topic</span></span>

- [<span data-ttu-id="2b6c6-166">Microsoft Defender voor Endpoint Device Control Verwisselbare Storage Access Control</span><span class="sxs-lookup"><span data-stu-id="2b6c6-166">Microsoft Defender for Endpoint Device Control Removable Storage Access Control</span></span>](device-control-removable-storage-access-control.md)