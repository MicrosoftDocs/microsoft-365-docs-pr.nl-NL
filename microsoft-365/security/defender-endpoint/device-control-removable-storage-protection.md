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
ms.openlocfilehash: c9b97c2157ba8090628af23b2ab54cf38f04d8c6
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538385"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-protection"></a><span data-ttu-id="600ea-104">Microsoft Defender voor Endpoint Device Control Verwisselbare Storage beveiliging</span><span class="sxs-lookup"><span data-stu-id="600ea-104">Microsoft Defender for Endpoint Device Control Removable Storage Protection</span></span>

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="600ea-105">Microsoft Defender voor Endpoint Device Control Verwisselbare Storage beveiliging voorkomt dat gebruiker of computer of beide niet-geautoriseerde verwisselbare opslagmedia gebruiken.</span><span class="sxs-lookup"><span data-stu-id="600ea-105">Microsoft Defender for Endpoint Device Control Removable Storage Protection prevents user or machine or both from using unauthorized removable storage media.</span></span>

## <a name="protection-policies"></a><span data-ttu-id="600ea-106">Beveiligingsbeleid</span><span class="sxs-lookup"><span data-stu-id="600ea-106">Protection policies</span></span>

### <a name="device-installation"></a><span data-ttu-id="600ea-107">Apparaatinstallatie</span><span class="sxs-lookup"><span data-stu-id="600ea-107">Device installation</span></span>

<span data-ttu-id="600ea-108">**Mogelijkheden:** voorkom installatie met of zonder uitsluiting op basis van verschillende apparaateigenschappen.</span><span class="sxs-lookup"><span data-stu-id="600ea-108">**Capabilities** - Prevent installation with or without exclusion based on various device properties.</span></span>

<span data-ttu-id="600ea-109">**Beschrijving**</span><span class="sxs-lookup"><span data-stu-id="600ea-109">**Description**</span></span>
- <span data-ttu-id="600ea-110">Toegepast op machineniveau: hetzelfde beleid geldt voor aangemelde gebruikers.</span><span class="sxs-lookup"><span data-stu-id="600ea-110">Applied at machine level: the same policy applies for any logged on user.</span></span>
- <span data-ttu-id="600ea-111">Ondersteunt MEM en GPO.</span><span class="sxs-lookup"><span data-stu-id="600ea-111">Supports MEM and GPO.</span></span>
- <span data-ttu-id="600ea-112">Ondersteunde '[Apparaateigenschappen'](#device-properties)zoals vermeld.</span><span class="sxs-lookup"><span data-stu-id="600ea-112">Supported  ‘[Device Properties](#device-properties)’ as listed.</span></span>
- <span data-ttu-id="600ea-113">Zie Usb-apparaten en andere verwisselbare media beheren met Microsoft Defender voor eindpunt voor meer informatie over [Windows.](control-usb-devices-using-intune.md)</span><span class="sxs-lookup"><span data-stu-id="600ea-113">For more information on Windows, see [How to control USB devices and other removable media using Microsoft Defender for Endpoint](control-usb-devices-using-intune.md).</span></span>

<span data-ttu-id="600ea-114">**Ondersteund platform** - Windows 10</span><span class="sxs-lookup"><span data-stu-id="600ea-114">**Supported Platform** - Windows 10</span></span>

<span data-ttu-id="600ea-115">**Beschrijving**</span><span class="sxs-lookup"><span data-stu-id="600ea-115">**Description**</span></span>
- <span data-ttu-id="600ea-116">Toegepast op machineniveau: hetzelfde beleid geldt voor aangemelde gebruikers</span><span class="sxs-lookup"><span data-stu-id="600ea-116">Applied at machine level: the same policy applies for any logged on user</span></span>
- <span data-ttu-id="600ea-117">Zie Apparaatbesturingselement voor macOS voor specifieke informatie [over macOS.](mac-device-control-overview.md)</span><span class="sxs-lookup"><span data-stu-id="600ea-117">For macOS specific information, see [Device control for macOS](mac-device-control-overview.md).</span></span>
 
<span data-ttu-id="600ea-118">**Ondersteund platform** - macOS Catalina 10.15.4+ (met systeemextensies ingeschakeld)</span><span class="sxs-lookup"><span data-stu-id="600ea-118">**Supported platform** - macOS Catalina 10.15.4+ (with system extensions enabled)</span></span>

### <a name="removable-storage-access-control"></a><span data-ttu-id="600ea-119">Verwisselbare opslagToegangsbesturingselement</span><span class="sxs-lookup"><span data-stu-id="600ea-119">Removable storage Access Control</span></span>

<span data-ttu-id="600ea-120">**Mogelijkheden**</span><span class="sxs-lookup"><span data-stu-id="600ea-120">**Capabilities**</span></span>
- <span data-ttu-id="600ea-121">*Controle* Lees of Schrijf of Voer toegang tot verwisselbare opslag uit op basis van verschillende apparaateigenschappen, met of zonder uitsluiting.</span><span class="sxs-lookup"><span data-stu-id="600ea-121">*Audit* Read or Write or Execute access to removable storage based on various device properties, with or without an exclusion.</span></span>
- <span data-ttu-id="600ea-122">*Voorkomen* Lees- of schrijf- of uitvoertoegang met of zonder uitsluiting - Specifiek apparaat toestaan op basis van verschillende apparaateigenschappen.</span><span class="sxs-lookup"><span data-stu-id="600ea-122">*Prevent* Read or Write or Execute access with or without an exclusion - Allow specific device based on various device properties.</span></span>

<span data-ttu-id="600ea-123">**Beschrijving**</span><span class="sxs-lookup"><span data-stu-id="600ea-123">**Description**</span></span>
- <span data-ttu-id="600ea-124">Toegepast op een computer of gebruiker of beide: sta alleen specifieke personen toe die lees-/schrijf-/uitvoertoegang tot specifieke verwisselbare opslag op een bepaalde computer uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="600ea-124">Applied at either machine or user or both – only allow specific people performing Read/Write/Execute access to specific removable storage on specific machine.</span></span>
- <span data-ttu-id="600ea-125">Ondersteuning voor MEM OMA-URI en GPO.</span><span class="sxs-lookup"><span data-stu-id="600ea-125">Support MEM OMA-URI and GPO.</span></span>
- <span data-ttu-id="600ea-126">Ondersteunde '[Apparaateigenschappen'](#device-properties)zoals vermeld.</span><span class="sxs-lookup"><span data-stu-id="600ea-126">Supported  ‘[Device Properties](#device-properties)’ as listed.</span></span>
- <span data-ttu-id="600ea-127">Zie Verwisselbare Windows Access Control voor [verwisselbare opslag voor functies](device-control-removable-storage-access-control.md)in de Windows.</span><span class="sxs-lookup"><span data-stu-id="600ea-127">For feature in Windows, see [Removable storage Access Control](device-control-removable-storage-access-control.md).</span></span>

<span data-ttu-id="600ea-128">**Ondersteund platform** - Windows 10</span><span class="sxs-lookup"><span data-stu-id="600ea-128">**Supported Platform** - Windows 10</span></span>

<span data-ttu-id="600ea-129">**Beschrijving**</span><span class="sxs-lookup"><span data-stu-id="600ea-129">**Description**</span></span>
- <span data-ttu-id="600ea-130">Toegepast op machineniveau: hetzelfde beleid geldt voor aangemelde gebruikers.</span><span class="sxs-lookup"><span data-stu-id="600ea-130">Applied at machine level: the same policy applies for any logged on user.</span></span>
- <span data-ttu-id="600ea-131">Zie Apparaatbesturingselement voor macOS voor specifieke informatie [over macOS.](mac-device-control-overview.md)</span><span class="sxs-lookup"><span data-stu-id="600ea-131">For macOS specific information, see [Device control for macOS](mac-device-control-overview.md).</span></span>
 
<span data-ttu-id="600ea-132">**Ondersteund platform** - macOS Catalina 10.15.4+ (met systeemextensies ingeschakeld)</span><span class="sxs-lookup"><span data-stu-id="600ea-132">**Supported platform** - macOS Catalina 10.15.4+ (with system extensions enabled)</span></span>

### <a name="windows-portable-device-access-control"></a><span data-ttu-id="600ea-133">Windows Portable Device Access Control</span><span class="sxs-lookup"><span data-stu-id="600ea-133">Windows Portable Device Access Control</span></span>

<span data-ttu-id="600ea-134">**Mogelijkheden:** toegang tot lezen of schrijven weigeren tot een Windows draagbaar [apparaat,](/windows-hardware/drivers/portable/)bijvoorbeeld: Tablet, iPhone.</span><span class="sxs-lookup"><span data-stu-id="600ea-134">**Capabilities** - Deny Read or Write access to any [Windows Portable Device](/windows-hardware/drivers/portable/), for example: Tablet, iPhone.</span></span>

<span data-ttu-id="600ea-135">**Beschrijving**</span><span class="sxs-lookup"><span data-stu-id="600ea-135">**Description**</span></span>
- <span data-ttu-id="600ea-136">Toegepast op een computer of gebruiker of beide.</span><span class="sxs-lookup"><span data-stu-id="600ea-136">Applied at either machine or user or both.</span></span>
- <span data-ttu-id="600ea-137">Ondersteuning voor MEM OMA-URI en GPO.</span><span class="sxs-lookup"><span data-stu-id="600ea-137">Support MEM OMA-URI and GPO.</span></span>

<span data-ttu-id="600ea-138">**Ondersteund platform** - Windows 10</span><span class="sxs-lookup"><span data-stu-id="600ea-138">**Supported Platform** - Windows 10</span></span>

### <a name="endpoint-dlp-removable-storage"></a><span data-ttu-id="600ea-139">Verwisselbare opslag van eindpunt DLP</span><span class="sxs-lookup"><span data-stu-id="600ea-139">Endpoint DLP Removable storage</span></span>

<span data-ttu-id="600ea-140">**Mogelijkheden:** controleer of waarschuw of voorkom dat een gebruiker een item of informatie kopieert naar verwisselbare media of USB-apparaat.</span><span class="sxs-lookup"><span data-stu-id="600ea-140">**Capabilities** - Audit or Warn or Prevent a user from copying an item or information to removable media or USB device.</span></span>

<span data-ttu-id="600ea-141">**Beschrijving** - Zie Meer informatie over het voorkomen Microsoft 365 endpoint voor meer Windows informatie over het voorkomen van [gegevensverlies.](../../compliance/endpoint-dlp-learn-about.md)</span><span class="sxs-lookup"><span data-stu-id="600ea-141">**Description** - For more information on Windows, see [Learn about Microsoft 365 Endpoint data loss prevention](../../compliance/endpoint-dlp-learn-about.md).</span></span>

<span data-ttu-id="600ea-142">**Ondersteund platform** - Windows 10</span><span class="sxs-lookup"><span data-stu-id="600ea-142">**Supported Platform** - Windows 10</span></span>

### <a name="bitlocker"></a><span data-ttu-id="600ea-143">BitLocker</span><span class="sxs-lookup"><span data-stu-id="600ea-143">BitLocker</span></span> 

<span data-ttu-id="600ea-144">**Mogelijkheden**</span><span class="sxs-lookup"><span data-stu-id="600ea-144">**Capabilities**</span></span>
- <span data-ttu-id="600ea-145">Blokkeer gegevens die moeten worden geschreven naar verwisselbare stations die niet BitLocker beveiligd.</span><span class="sxs-lookup"><span data-stu-id="600ea-145">Block data to be written to removable drives that aren't BitLocker protected.</span></span>
- <span data-ttu-id="600ea-146">Toegang tot verwisselbare stations blokkeren, tenzij ze zijn versleuteld op een computer die eigendom is van uw organisatie</span><span class="sxs-lookup"><span data-stu-id="600ea-146">Block access to removable drives unless they were encrypted on a computer owned by your organization</span></span>
 
<span data-ttu-id="600ea-147">**Beschrijving** - Zie Windows - Verwisselbaar station BitLocker voor [meer Instellingen.](/mem/intune/protect/endpoint-security-disk-encryption-profile-settings)</span><span class="sxs-lookup"><span data-stu-id="600ea-147">**Description** - For more information on Windows, see [BitLocker – Removable Drive Settings](/mem/intune/protect/endpoint-security-disk-encryption-profile-settings).</span></span>

<span data-ttu-id="600ea-148">**Ondersteund platform** - Windows 10</span><span class="sxs-lookup"><span data-stu-id="600ea-148">**Supported Platform** - Windows 10</span></span>

## <a name="device-properties"></a><span data-ttu-id="600ea-149">Apparaateigenschappen</span><span class="sxs-lookup"><span data-stu-id="600ea-149">Device properties</span></span>

<span data-ttu-id="600ea-150">Met Microsoft Defender for Endpoint Device Control Verwisselbare Storage Protection kunt u de verwisselbare opslagtoegang beperken op basis van de eigenschappen die in de onderstaande tabel worden beschreven:</span><span class="sxs-lookup"><span data-stu-id="600ea-150">Microsoft Defender for Endpoint Device Control Removable Storage Protection allows you to restrict the removable storage access based on the properties described in the table below:</span></span>


|<span data-ttu-id="600ea-151">Eigenschapsnaam</span><span class="sxs-lookup"><span data-stu-id="600ea-151">Property Name</span></span>  |<span data-ttu-id="600ea-152">Toepasselijke beleidsregels</span><span class="sxs-lookup"><span data-stu-id="600ea-152">Applicable Policies</span></span>  |<span data-ttu-id="600ea-153">Van toepassing op besturingssystemen</span><span class="sxs-lookup"><span data-stu-id="600ea-153">Applies to Operating Systems</span></span>  |<span data-ttu-id="600ea-154">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="600ea-154">Description</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="600ea-155">Apparaatklasse</span><span class="sxs-lookup"><span data-stu-id="600ea-155">Device Class</span></span>    |     [<span data-ttu-id="600ea-156">USB-apparaten en andere verwisselbare media beheren met Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="600ea-156">How to control USB devices and other removable media using Microsoft Defender for Endpoint</span></span>](control-usb-devices-using-intune.md)     |   <span data-ttu-id="600ea-157">Windows</span><span class="sxs-lookup"><span data-stu-id="600ea-157">Windows</span></span>      |  <span data-ttu-id="600ea-158">Zie apparaatconfiguratieklasse voor informatie over [apparaat-id-indelingen.](/windows-hardware/drivers/install/system-defined-device-setup-classes-available-to-vendors)</span><span class="sxs-lookup"><span data-stu-id="600ea-158">For information about Device ID formats, see [device setup class](/windows-hardware/drivers/install/system-defined-device-setup-classes-available-to-vendors).</span></span> <span data-ttu-id="600ea-159">**Opmerking:** Apparaatinstallatie kan worden toegepast op alle apparaten, niet alleen op verwisselbare opslag.</span><span class="sxs-lookup"><span data-stu-id="600ea-159">**Note**: Device Installation can be applied to any devices, not only Removable storage.</span></span>       |
|<span data-ttu-id="600ea-160">Primaire id</span><span class="sxs-lookup"><span data-stu-id="600ea-160">Primary ID</span></span>   |     <span data-ttu-id="600ea-161">Verwisselbare opslagToegangsbesturingselement</span><span class="sxs-lookup"><span data-stu-id="600ea-161">Removable storage Access Control</span></span>    |   <span data-ttu-id="600ea-162">Windows</span><span class="sxs-lookup"><span data-stu-id="600ea-162">Windows</span></span>      |      <span data-ttu-id="600ea-163">De primaire id bevat verwisselbare opslag en cd/dvd.</span><span class="sxs-lookup"><span data-stu-id="600ea-163">The Primary ID includes removable storage and CD/DVD.</span></span>   |
|<span data-ttu-id="600ea-164">Apparaat-id</span><span class="sxs-lookup"><span data-stu-id="600ea-164">Device ID</span></span>     |  <span data-ttu-id="600ea-165">[Usb-apparaten en andere verwisselbare media beheren met Microsoft Defender voor Eindpunt;](control-usb-devices-using-intune.md) Verwisselbare opslagToegangsbesturingselement</span><span class="sxs-lookup"><span data-stu-id="600ea-165">[How to control USB devices and other removable media using Microsoft Defender for Endpoint](control-usb-devices-using-intune.md); Removable storage Access Control</span></span>       |      <span data-ttu-id="600ea-166">Windows</span><span class="sxs-lookup"><span data-stu-id="600ea-166">Windows</span></span>   |    <span data-ttu-id="600ea-167">Zie Standaard USB-id's [](/windows-hardware/drivers/install/standard-usb-identifiers)voor informatie over apparaat-id-indelingen, bijvoorbeeld USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07</span><span class="sxs-lookup"><span data-stu-id="600ea-167">For information about Device ID formats, see [Standard USB Identifiers](/windows-hardware/drivers/install/standard-usb-identifiers), for example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07</span></span>      |
|<span data-ttu-id="600ea-168">Hardware-id</span><span class="sxs-lookup"><span data-stu-id="600ea-168">Hardware ID</span></span>     |     <span data-ttu-id="600ea-169">[Usb-apparaten en andere verwisselbare media beheren met Microsoft Defender voor Eindpunt;](control-usb-devices-using-intune.md) Verwisselbare opslagToegangsbesturingselement</span><span class="sxs-lookup"><span data-stu-id="600ea-169">[How to control USB devices and other removable media using Microsoft Defender for Endpoint](control-usb-devices-using-intune.md); Removable storage Access Control</span></span>    |     <span data-ttu-id="600ea-170">Windows</span><span class="sxs-lookup"><span data-stu-id="600ea-170">Windows</span></span>    |    <span data-ttu-id="600ea-171">Een tekenreeks heeft het apparaat in het systeem geïdentificeerd, bijvoorbeeld USBSTOR\DiskGeneric_Flash_Disk______8.07; **Opmerking:** Hardware-id is niet uniek; verschillende apparaten kunnen dezelfde waarde delen.</span><span class="sxs-lookup"><span data-stu-id="600ea-171">A string identified the device in the system, for example, USBSTOR\DiskGeneric_Flash_Disk______8.07; **Note**: Hardware ID is not unique; different devices may share same value.</span></span>|
|<span data-ttu-id="600ea-172">Exemplaar-id</span><span class="sxs-lookup"><span data-stu-id="600ea-172">Instance ID</span></span>    | <span data-ttu-id="600ea-173">Apparaatinstallatie; Verwisselbare opslagToegangsbesturingselement</span><span class="sxs-lookup"><span data-stu-id="600ea-173">Device Installation; Removable storage Access Control</span></span>     |     <span data-ttu-id="600ea-174">Windows</span><span class="sxs-lookup"><span data-stu-id="600ea-174">Windows</span></span>    |   <span data-ttu-id="600ea-175">Een tekenreeks identificeert het apparaat in het systeem, bijvoorbeeld USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0</span><span class="sxs-lookup"><span data-stu-id="600ea-175">A string uniquely identifies the device in the system, for example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0</span></span>      |
|<span data-ttu-id="600ea-176">Vriendelijke naam</span><span class="sxs-lookup"><span data-stu-id="600ea-176">Friendly Name</span></span>     |     <span data-ttu-id="600ea-177">Verwisselbare opslagToegangsbesturingselement</span><span class="sxs-lookup"><span data-stu-id="600ea-177">Removable storage Access Control</span></span>    |   <span data-ttu-id="600ea-178">Windows</span><span class="sxs-lookup"><span data-stu-id="600ea-178">Windows</span></span>      |    <span data-ttu-id="600ea-179">Een tekenreeks die is gekoppeld aan het apparaat, bijvoorbeeld Generic Flash Disk USB Device</span><span class="sxs-lookup"><span data-stu-id="600ea-179">A string attached to the device, for example, Generic Flash Disk USB Device</span></span>     |
|<span data-ttu-id="600ea-180">Leverancier-id/product-id</span><span class="sxs-lookup"><span data-stu-id="600ea-180">Vendor ID / Product ID</span></span>     |  <span data-ttu-id="600ea-181">Verwisselbare opslagToegangsbesturingselement</span><span class="sxs-lookup"><span data-stu-id="600ea-181">Removable storage Access Control</span></span>       |   <span data-ttu-id="600ea-182">Windows Mac</span><span class="sxs-lookup"><span data-stu-id="600ea-182">Windows Mac</span></span>      |     <span data-ttu-id="600ea-183">Leverancier-id is de leveranciercode met vier cijfers die door de USB-commissie aan de leverancier wordt toegewezen.</span><span class="sxs-lookup"><span data-stu-id="600ea-183">Vendor ID is the four-digit vendor code that the USB committee assigns to the vendor.</span></span> <span data-ttu-id="600ea-184">Product-id is de viercijferige productcode die de leverancier aan het apparaat toewijst. Ondersteunings jokerteken.</span><span class="sxs-lookup"><span data-stu-id="600ea-184">Product ID is the four-digit product code that the vendor assigns to the device; Support wildcard.</span></span>    |
|<span data-ttu-id="600ea-185">Serienummer</span><span class="sxs-lookup"><span data-stu-id="600ea-185">Serial NumberId</span></span>     |     <span data-ttu-id="600ea-186">Verwisselbare opslagToegangsbesturingselement</span><span class="sxs-lookup"><span data-stu-id="600ea-186">Removable storage Access Control</span></span>    |      <span data-ttu-id="600ea-187">Windows Mac</span><span class="sxs-lookup"><span data-stu-id="600ea-187">Windows Mac</span></span>   |     <span data-ttu-id="600ea-188">Bijvoorbeeld <SerialNumberId>002324B534BCB431B000058A</SerialNumberId></span><span class="sxs-lookup"><span data-stu-id="600ea-188">For example, <SerialNumberId>002324B534BCB431B000058A</SerialNumberId></span></span>    |

## <a name="related-topic"></a><span data-ttu-id="600ea-189">Verwant onderwerp</span><span class="sxs-lookup"><span data-stu-id="600ea-189">Related topic</span></span>

- [<span data-ttu-id="600ea-190">Microsoft Defender voor Endpoint Device Control Verwisselbare Storage Access Control</span><span class="sxs-lookup"><span data-stu-id="600ea-190">Microsoft Defender for Endpoint Device Control Removable Storage Access Control</span></span>](device-control-removable-storage-access-control.md)

