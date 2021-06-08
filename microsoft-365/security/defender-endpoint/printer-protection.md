---
title: Microsoft Defender voor endpoint Device Control Printer Protection
description: Microsoft Defender for Endpoint Device Control Printer Protection blokkeert afdrukken via niet-bedrijfsprinters of niet-goedgekeurde USB-printer.
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.author: v-lsaldanha
author: lovina-saldanha
ms.reviewer: dansimp
manager: dansimp
audience: ITPro
ms.technology: mde
ms.openlocfilehash: 431497ded684543c33d91c49a0da47e92297321f
ms.sourcegitcommit: e1e275eb88153bafddf93327adf8f82318913a8d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52809228"
---
# <a name="device-control-printer-protection"></a><span data-ttu-id="6bdc7-103">Apparaatbesturingselement printerbeveiliging</span><span class="sxs-lookup"><span data-stu-id="6bdc7-103">Device Control Printer Protection</span></span> 

<span data-ttu-id="6bdc7-104">Microsoft Defender for Endpoint Device Control Printer Protection blokkeert afdrukken via niet-bedrijfsprinters of niet-goedgekeurde USB-printer.</span><span class="sxs-lookup"><span data-stu-id="6bdc7-104">Microsoft Defender for Endpoint Device Control Printer Protection blocks people from printing via non-corporate printers or non-approved USB printer.</span></span>

## <a name="licensing"></a><span data-ttu-id="6bdc7-105">Licenties</span><span class="sxs-lookup"><span data-stu-id="6bdc7-105">Licensing</span></span> 

<span data-ttu-id="6bdc7-106">Voordat u aan de slag gaat met Printerbeveiliging, moet u [uw Microsoft 365 bevestigen.](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)</span><span class="sxs-lookup"><span data-stu-id="6bdc7-106">Before you get started with Printer Protection, you should [confirm your Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1).</span></span> <span data-ttu-id="6bdc7-107">Als u Printerbeveiliging wilt openen en gebruiken, moet u het volgende hebben:</span><span class="sxs-lookup"><span data-stu-id="6bdc7-107">To access and use Printer Protection, you must have the following:</span></span>

- <span data-ttu-id="6bdc7-108">Microsoft 365 E3 voor functionaliteit/beleidsimplementatie</span><span class="sxs-lookup"><span data-stu-id="6bdc7-108">Microsoft 365 E3 for functionality/policy deployment</span></span> 
- <span data-ttu-id="6bdc7-109">Microsoft 365 E5 voor rapportage</span><span class="sxs-lookup"><span data-stu-id="6bdc7-109">Microsoft 365 E5 for reporting</span></span> 

## <a name="permission"></a><span data-ttu-id="6bdc7-110">Machtiging</span><span class="sxs-lookup"><span data-stu-id="6bdc7-110">Permission</span></span> 

<span data-ttu-id="6bdc7-111">Voor beleidsimplementatie in Intune moet het account machtigingen hebben voor het maken, bewerken, bijwerken of verwijderen van apparaatconfiguratieprofielen als u beleid wilt implementeren via OMA-URI.</span><span class="sxs-lookup"><span data-stu-id="6bdc7-111">For Policy deployment in Intune, to deploy policy via OMA-URI, the account must have permissions to create, edit, update, or delete device configuration profiles.</span></span> <span data-ttu-id="6bdc7-112">U kunt aangepaste rollen maken of een van de ingebouwde rollen gebruiken met deze machtigingen:</span><span class="sxs-lookup"><span data-stu-id="6bdc7-112">You can create custom roles or use any of the built-in roles with these permissions:</span></span>  

- <span data-ttu-id="6bdc7-113">Rol beleid en profielbeheer.</span><span class="sxs-lookup"><span data-stu-id="6bdc7-113">Policy and profile Manager role.</span></span> 
- <span data-ttu-id="6bdc7-114">Of aangepaste rol met machtigingen maken/bewerken/bijwerken/lezen/verwijderen/rapporten weergeven ingeschakeld voor apparaatconfiguratieprofielen</span><span class="sxs-lookup"><span data-stu-id="6bdc7-114">Or custom role with Create/Edit/Update/Read/Delete/View Reports permissions turned on for Device Configuration profiles</span></span>  
- <span data-ttu-id="6bdc7-115">Of globale beheerder</span><span class="sxs-lookup"><span data-stu-id="6bdc7-115">Or Global admin</span></span>

<span data-ttu-id="6bdc7-116">Als u apparaatconfiguratierapporten wilt zien, moet het account rapportenmachtigingen hebben.</span><span class="sxs-lookup"><span data-stu-id="6bdc7-116">To see device configuration reports, the account must have view reports permissions.</span></span> <span data-ttu-id="6bdc7-117">U kunt aangepaste rollen maken of de ingebouwde rollen gebruiken met deze machtigingen:</span><span class="sxs-lookup"><span data-stu-id="6bdc7-117">You can create custom roles or use the built-in roles with these permissions:</span></span>  

- <span data-ttu-id="6bdc7-118">Globale beveiligingsbeheerder</span><span class="sxs-lookup"><span data-stu-id="6bdc7-118">Global security admin</span></span>
- <span data-ttu-id="6bdc7-119">Beveiligingsbeheerder</span><span class="sxs-lookup"><span data-stu-id="6bdc7-119">Security admin</span></span>
- <span data-ttu-id="6bdc7-120">Beveiligingslezer</span><span class="sxs-lookup"><span data-stu-id="6bdc7-120">Security Reader</span></span> 

## <a name="prepare-your-endpoints"></a><span data-ttu-id="6bdc7-121">Uw eindpunten voorbereiden</span><span class="sxs-lookup"><span data-stu-id="6bdc7-121">Prepare your endpoints</span></span>

<span data-ttu-id="6bdc7-122">Zorg ervoor dat de Windows 10 die u van plan bent printerbeveiliging te implementeren om aan deze vereisten te voldoen.</span><span class="sxs-lookup"><span data-stu-id="6bdc7-122">Make sure that the Windows 10 devices that you plan on deploying Printer Protection to meet these requirements.</span></span>

1. <span data-ttu-id="6bdc7-123">Deelnemen aan het Insider-programma.</span><span class="sxs-lookup"><span data-stu-id="6bdc7-123">Join the Insider Program.</span></span>

1. <span data-ttu-id="6bdc7-124">De volgende Windows-updates zijn geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="6bdc7-124">The following Windows Updates are installed.</span></span> 

    - <span data-ttu-id="6bdc7-125">Voor Windows 1809: installatie Windows [KB5003217 bijwerken](https://support.microsoft.com/en-us/topic/may-20-2021-kb5003217-os-build-17763-1971-preview-08687c95-0740-421b-a205-54aa2c716b46)</span><span class="sxs-lookup"><span data-stu-id="6bdc7-125">For Windows 1809: install Windows Update [KB5003217](https://support.microsoft.com/en-us/topic/may-20-2021-kb5003217-os-build-17763-1971-preview-08687c95-0740-421b-a205-54aa2c716b46)</span></span> 
    - <span data-ttu-id="6bdc7-126">Voor Windows 1909: installatie Windows [KB5003212 bijwerken](https://support.microsoft.com/en-us/topic/may-20-2021-kb5003212-os-build-18363-1593-preview-05381524-8380-4b30-b783-e330cad3d4a1)</span><span class="sxs-lookup"><span data-stu-id="6bdc7-126">For Windows 1909: install Windows Update [KB5003212](https://support.microsoft.com/en-us/topic/may-20-2021-kb5003212-os-build-18363-1593-preview-05381524-8380-4b30-b783-e330cad3d4a1)</span></span>
    - <span data-ttu-id="6bdc7-127">Voor Windows 2004 of hoger</span><span class="sxs-lookup"><span data-stu-id="6bdc7-127">For Windows 2004 or later</span></span> 
    
1. <span data-ttu-id="6bdc7-128">Als u beleid wilt implementeren via groepsbeleid, moet het apparaat MDATP zijn. als u van plan bent beleid te implementeren via MEM, moet het apparaat zijn verbonden met Intune.</span><span class="sxs-lookup"><span data-stu-id="6bdc7-128">If you're planning to deploy policy via Group Policy, the device must be MDATP joined; if you're planning to deploy policy via MEM, the device must be Intune joined.</span></span>

## <a name="deploy-device-control-printer-protection-policy"></a><span data-ttu-id="6bdc7-129">Apparaatbesturingselement printerbeveiligingsbeleid implementeren</span><span class="sxs-lookup"><span data-stu-id="6bdc7-129">Deploy Device Control Printer Protection policy</span></span>

<span data-ttu-id="6bdc7-130">U kunt het beleid implementeren via Groepsbeleid of Intune.</span><span class="sxs-lookup"><span data-stu-id="6bdc7-130">You can deploy the policy via Group Policy or Intune.</span></span>

| <span data-ttu-id="6bdc7-131">Title</span><span class="sxs-lookup"><span data-stu-id="6bdc7-131">Title</span></span> | <span data-ttu-id="6bdc7-132">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="6bdc7-132">Description</span></span> | <span data-ttu-id="6bdc7-133">CSP-ondersteuning</span><span class="sxs-lookup"><span data-stu-id="6bdc7-133">CSP Support</span></span> | <span data-ttu-id="6bdc7-134">Ondersteuning voor GPO</span><span class="sxs-lookup"><span data-stu-id="6bdc7-134">GPO Support</span></span> | <span data-ttu-id="6bdc7-135">Ondersteuning op basis van gebruikers</span><span class="sxs-lookup"><span data-stu-id="6bdc7-135">User-based Support</span></span> | <span data-ttu-id="6bdc7-136">Ondersteuning op basis van machines</span><span class="sxs-lookup"><span data-stu-id="6bdc7-136">Machine-based Support</span></span> |
|:--|:--|:--|:--|:--|:--|
|<span data-ttu-id="6bdc7-137">**Apparaatbesturingselement afdrukbeperkingen inschakelen**</span><span class="sxs-lookup"><span data-stu-id="6bdc7-137">**Enable Device control Printing Restrictions**</span></span>|<span data-ttu-id="6bdc7-138">Personen blokkeren om af te drukken via een niet-zakelijke printer</span><span class="sxs-lookup"><span data-stu-id="6bdc7-138">Block people from printing via non-corporate printer</span></span>|<span data-ttu-id="6bdc7-139">Ja</span><span class="sxs-lookup"><span data-stu-id="6bdc7-139">Yes</span></span>|<span data-ttu-id="6bdc7-140">Ja</span><span class="sxs-lookup"><span data-stu-id="6bdc7-140">Yes</span></span>|<span data-ttu-id="6bdc7-141">Ja</span><span class="sxs-lookup"><span data-stu-id="6bdc7-141">Yes</span></span>|<span data-ttu-id="6bdc7-142">Ja</span><span class="sxs-lookup"><span data-stu-id="6bdc7-142">Yes</span></span>|
|<span data-ttu-id="6bdc7-143">**Lijst met goedgekeurde usb-verbonden afdrukapparaten**\*</span><span class="sxs-lookup"><span data-stu-id="6bdc7-143">**List of Approved USB-connected print devices** \*</span></span>|<span data-ttu-id="6bdc7-144">Specifieke USB-printer toestaan</span><span class="sxs-lookup"><span data-stu-id="6bdc7-144">Allow specific USB printer</span></span>|<span data-ttu-id="6bdc7-145">Ja</span><span class="sxs-lookup"><span data-stu-id="6bdc7-145">Yes</span></span>|<span data-ttu-id="6bdc7-146">Ja</span><span class="sxs-lookup"><span data-stu-id="6bdc7-146">Yes</span></span>|<span data-ttu-id="6bdc7-147">Ja</span><span class="sxs-lookup"><span data-stu-id="6bdc7-147">Yes</span></span>|<span data-ttu-id="6bdc7-148">Ja</span><span class="sxs-lookup"><span data-stu-id="6bdc7-148">Yes</span></span>|
|||||||

<span data-ttu-id="6bdc7-149">\* Dit beleid moet samen met Afdrukbeperkingen apparaatbesturingselement **inschakelen worden gebruikt**</span><span class="sxs-lookup"><span data-stu-id="6bdc7-149">\* This policy must be used together with **Enable Device control Printing Restrictions**</span></span>
## <a name="deploy-policy-via-intune"></a><span data-ttu-id="6bdc7-150">Beleid implementeren via Intune</span><span class="sxs-lookup"><span data-stu-id="6bdc7-150">Deploy policy via Intune</span></span> 

<span data-ttu-id="6bdc7-151">Voor Intune ondersteunt apparaatbesturingselementprinterbeveiliging op dit moment alleen OMA-URI.</span><span class="sxs-lookup"><span data-stu-id="6bdc7-151">For Intune, currently Device Control Printer Protection supports OMA-URI only.</span></span>

<span data-ttu-id="6bdc7-152">**Scenario 1: Voorkomen dat personen afdrukken via een niet-zakelijke printer**</span><span class="sxs-lookup"><span data-stu-id="6bdc7-152">**Scenario 1: Block people from printing via any non-corporate printer**</span></span> 

 - <span data-ttu-id="6bdc7-153">Beleid toepassen op computer:</span><span class="sxs-lookup"><span data-stu-id="6bdc7-153">Apply policy over machine:</span></span> 

    - <span data-ttu-id="6bdc7-154">./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControl</span><span class="sxs-lookup"><span data-stu-id="6bdc7-154">./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControl</span></span> 

- <span data-ttu-id="6bdc7-155">Beleid toepassen op gebruiker:</span><span class="sxs-lookup"><span data-stu-id="6bdc7-155">Apply policy over user:</span></span> 

    - <span data-ttu-id="6bdc7-156">./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControlUser</span><span class="sxs-lookup"><span data-stu-id="6bdc7-156">./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControlUser</span></span> 

<span data-ttu-id="6bdc7-157">De CSP-ondersteuningsreeks `` <enabled/>`` met:</span><span class="sxs-lookup"><span data-stu-id="6bdc7-157">The CSP support string with `` <enabled/>``:</span></span> 

:::image type="content" source="../../media/customeditrow.png" alt-text="aangepaste bewerkingsrij":::

<span data-ttu-id="6bdc7-159">**Scenario 2: Specifieke goedgekeurde USB-printers toestaan**</span><span class="sxs-lookup"><span data-stu-id="6bdc7-159">**Scenario 2: Allow specific approved USB printers**</span></span>

- <span data-ttu-id="6bdc7-160">Beleid toepassen op computer:</span><span class="sxs-lookup"><span data-stu-id="6bdc7-160">Apply policy over machine:</span></span> 

    - <span data-ttu-id="6bdc7-161">./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevices</span><span class="sxs-lookup"><span data-stu-id="6bdc7-161">./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevices</span></span> 

- <span data-ttu-id="6bdc7-162">Beleid toepassen op gebruiker:</span><span class="sxs-lookup"><span data-stu-id="6bdc7-162">Apply policy over user:</span></span> 

    - <span data-ttu-id="6bdc7-163">./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevicesUser</span><span class="sxs-lookup"><span data-stu-id="6bdc7-163">./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevicesUser</span></span>  

<span data-ttu-id="6bdc7-164">De CSP-ondersteuningsreeks met goedgekeurde USB-printers via de eigenschap ApprovedUsbPrintDevices, `` <enabled/><data id="ApprovedUsbPrintDevices_List" value="03F0/0853,0351/0872"/>`` bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="6bdc7-164">The CSP support string with approved USB printers via ‘ApprovedUsbPrintDevices’ property, example `` <enabled/><data id="ApprovedUsbPrintDevices_List" value="03F0/0853,0351/0872"/>``:</span></span> 

:::image type="content" source="../../media/editrow.png" alt-text="rij bewerken":::

## <a name="deploy-policy-via-group-policy"></a><span data-ttu-id="6bdc7-166">Beleid implementeren via groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="6bdc7-166">Deploy policy via Group Policy</span></span> 

<span data-ttu-id="6bdc7-167">Als het apparaat niet is verbonden met Intune, kunt u het beleid ook implementeren via groepsbeleid.</span><span class="sxs-lookup"><span data-stu-id="6bdc7-167">If the device isn't Intune joined, you can also deploy the policy via Group Policy.</span></span> 

<span data-ttu-id="6bdc7-168">**Scenario 1: Voorkomen dat personen afdrukken via een niet-zakelijke printer**</span><span class="sxs-lookup"><span data-stu-id="6bdc7-168">**Scenario 1: Block people from printing via any non-corporate printer**</span></span> 

- <span data-ttu-id="6bdc7-169">Beleid toepassen op computer:</span><span class="sxs-lookup"><span data-stu-id="6bdc7-169">Apply policy over machine:</span></span> 

    - <span data-ttu-id="6bdc7-170">Computerconfiguratie > beheersjablonen > Printer: Apparaatbesturingselement afdrukbeperkingen inschakelen</span><span class="sxs-lookup"><span data-stu-id="6bdc7-170">Computer Configuration > Administrative Templates > Printer: Enable Device control Printing Restrictions</span></span> 

- <span data-ttu-id="6bdc7-171">Beleid toepassen op gebruiker:</span><span class="sxs-lookup"><span data-stu-id="6bdc7-171">Apply policy over user:</span></span> 

    - <span data-ttu-id="6bdc7-172">Gebruikersconfiguratie > beheersjablonen > configuratiescherm > printers: Apparaatbesturingselementafdrukbeperkingen inschakelen</span><span class="sxs-lookup"><span data-stu-id="6bdc7-172">User Configuration > Administrative Templates > Control Panel > Printers: Enable Device control Printing Restrictions</span></span> 

:::image type="content" source="../../media/enable-device-ctrl-printing-restrictions.png" alt-text="beperkingen voor het afdrukken van apparaten inschakelen":::
 

<span data-ttu-id="6bdc7-174">**Scenario 2: Specifieke goedgekeurde USB-printers toestaan**</span><span class="sxs-lookup"><span data-stu-id="6bdc7-174">**Scenario 2: Allow specific approved USB printers**</span></span>

- <span data-ttu-id="6bdc7-175">Beleid toepassen op computer:</span><span class="sxs-lookup"><span data-stu-id="6bdc7-175">Apply policy over machine:</span></span> 

    - <span data-ttu-id="6bdc7-176">Computerconfiguratie > beheersjablonen > printer: lijst met goedgekeurde afdrukapparaten met USB-verbinding</span><span class="sxs-lookup"><span data-stu-id="6bdc7-176">Computer Configuration > Administrative Templates > Printer:  List of Approved USB-connected print devices</span></span> 

- <span data-ttu-id="6bdc7-177">Beleid toepassen op gebruiker:</span><span class="sxs-lookup"><span data-stu-id="6bdc7-177">Apply policy over user:</span></span>  

    - <span data-ttu-id="6bdc7-178">Gebruikersconfiguratie > beheersjablonen > configuratiescherm > printers: Lijst met goedgekeurde usb-aangesloten afdrukapparaten</span><span class="sxs-lookup"><span data-stu-id="6bdc7-178">User Configuration > Administrative Templates > Control Panel > Printers: List of Approved USB-connected print devices</span></span> 
 
 :::image type="content" source="../../media/list-of-approved-connected-print-devices.png" alt-text="lijst met goedgekeurde usb-verbonden afdrukapparaten":::

## <a name="view-device-control-printer-protection-data-in-microsoft-defender-for-endpoint-portal"></a><span data-ttu-id="6bdc7-180">Apparaatbesturingselement printerbeveiligingsgegevens weergeven in microsoft Defender voor eindpuntportal</span><span class="sxs-lookup"><span data-stu-id="6bdc7-180">View Device Control Printer Protection data in Microsoft Defender for Endpoint portal</span></span> 

<span data-ttu-id="6bdc7-181">In [Microsoft 365 beveiligingscentrum ziet](https://security.microsoft.com) u afdrukken die zijn geblokkeerd door het beleid voor apparaatbesturingselementprinterbeveiliging hierboven.</span><span class="sxs-lookup"><span data-stu-id="6bdc7-181">The [Microsoft 365 security center](https://security.microsoft.com) shows printing blocked by the Device Control Printer Protection policy above.</span></span>
 
```sql
DeviceEvents 

|where ActionType == 'PrintJobBlocked' 

| extend parsed=parse_json(AdditionalFields) 

| extend PrintedFile=tostring(parsed.JobOrDocumentName) 

| extend PrintPortName=tostring(parsed.PortName) 

| extend PrinterName=tostring(parsed.PrinterName) 

| extend Policy=tostring(parsed.RestrictionReason)  

| project Timestamp, DeviceId, DeviceName, ActionType, InitiatingProcessAccountName,Policy, PrintedFile, PrinterName, PrintPortName, AdditionalFields 

| order by Timestamp desc 
```

 :::image type="content" source="../../media/device-control-advanced-hunting.png" alt-text="geavanceerd zoeken":::
