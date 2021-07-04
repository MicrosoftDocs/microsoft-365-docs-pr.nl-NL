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
ms.topic: article
ms.openlocfilehash: 0f089efedef1e4fb6b146692da3f1a630f2bacac
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289689"
---
# <a name="device-control-printer-protection"></a><span data-ttu-id="b662b-103">Printerbeveiliging voor apparaatbesturingselementen</span><span class="sxs-lookup"><span data-stu-id="b662b-103">Device Control Printer Protection</span></span>

<span data-ttu-id="b662b-104">Microsoft Defender for Endpoint Device Control Printer Protection blokkeert afdrukken via niet-bedrijfsprinters of niet-goedgekeurde USB-printer.</span><span class="sxs-lookup"><span data-stu-id="b662b-104">Microsoft Defender for Endpoint Device Control Printer Protection blocks people from printing via non-corporate printers or non-approved USB printer.</span></span>

## <a name="licensing"></a><span data-ttu-id="b662b-105">Licenties</span><span class="sxs-lookup"><span data-stu-id="b662b-105">Licensing</span></span>

<span data-ttu-id="b662b-106">Voordat u aan de slag gaat met Printerbeveiliging, moet u [uw Microsoft 365 bevestigen.](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)</span><span class="sxs-lookup"><span data-stu-id="b662b-106">Before you get started with Printer Protection, you should [confirm your Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1).</span></span> <span data-ttu-id="b662b-107">Als u Printerbeveiliging wilt openen en gebruiken, moet u het volgende hebben:</span><span class="sxs-lookup"><span data-stu-id="b662b-107">To access and use Printer Protection, you must have the following:</span></span>

- <span data-ttu-id="b662b-108">Microsoft 365 E3 voor functionaliteit/beleidsimplementatie</span><span class="sxs-lookup"><span data-stu-id="b662b-108">Microsoft 365 E3 for functionality/policy deployment</span></span>
- <span data-ttu-id="b662b-109">Microsoft 365 E5 voor rapportage</span><span class="sxs-lookup"><span data-stu-id="b662b-109">Microsoft 365 E5 for reporting</span></span>

## <a name="permission"></a><span data-ttu-id="b662b-110">Machtiging</span><span class="sxs-lookup"><span data-stu-id="b662b-110">Permission</span></span>

<span data-ttu-id="b662b-111">Voor beleidsimplementatie in Intune moet het account machtigingen hebben voor het maken, bewerken, bijwerken of verwijderen van apparaatconfiguratieprofielen als u beleid wilt implementeren via OMA-URI.</span><span class="sxs-lookup"><span data-stu-id="b662b-111">For Policy deployment in Intune, to deploy policy via OMA-URI, the account must have permissions to create, edit, update, or delete device configuration profiles.</span></span> <span data-ttu-id="b662b-112">U kunt aangepaste rollen maken of een van de ingebouwde rollen gebruiken met deze machtigingen:</span><span class="sxs-lookup"><span data-stu-id="b662b-112">You can create custom roles or use any of the built-in roles with these permissions:</span></span>

- <span data-ttu-id="b662b-113">Rol beleid en profielbeheer.</span><span class="sxs-lookup"><span data-stu-id="b662b-113">Policy and profile Manager role.</span></span>
- <span data-ttu-id="b662b-114">Of aangepaste rol met machtigingen maken/bewerken/bijwerken/lezen/verwijderen/rapporten weergeven ingeschakeld voor apparaatconfiguratieprofielen</span><span class="sxs-lookup"><span data-stu-id="b662b-114">Or custom role with Create/Edit/Update/Read/Delete/View Reports permissions turned on for Device Configuration profiles</span></span>
- <span data-ttu-id="b662b-115">Of globale beheerder</span><span class="sxs-lookup"><span data-stu-id="b662b-115">Or Global admin</span></span>

<span data-ttu-id="b662b-116">Als u apparaatconfiguratierapporten wilt zien, moet het account rapportenmachtigingen hebben.</span><span class="sxs-lookup"><span data-stu-id="b662b-116">To see device configuration reports, the account must have view reports permissions.</span></span> <span data-ttu-id="b662b-117">U kunt aangepaste rollen maken of de ingebouwde rollen gebruiken met deze machtigingen:</span><span class="sxs-lookup"><span data-stu-id="b662b-117">You can create custom roles or use the built-in roles with these permissions:</span></span>

- <span data-ttu-id="b662b-118">Globale beveiligingsbeheerder</span><span class="sxs-lookup"><span data-stu-id="b662b-118">Global security admin</span></span>
- <span data-ttu-id="b662b-119">Beveiligingsbeheerder</span><span class="sxs-lookup"><span data-stu-id="b662b-119">Security admin</span></span>
- <span data-ttu-id="b662b-120">Beveiligingslezer</span><span class="sxs-lookup"><span data-stu-id="b662b-120">Security Reader</span></span>

## <a name="prepare-your-endpoints"></a><span data-ttu-id="b662b-121">Uw eindpunten voorbereiden</span><span class="sxs-lookup"><span data-stu-id="b662b-121">Prepare your endpoints</span></span>

<span data-ttu-id="b662b-122">Zorg ervoor dat de Windows 10 die u van plan bent printerbeveiliging te implementeren om aan deze vereisten te voldoen.</span><span class="sxs-lookup"><span data-stu-id="b662b-122">Make sure that the Windows 10 devices that you plan on deploying Printer Protection to meet these requirements.</span></span>

1. <span data-ttu-id="b662b-123">Deelnemen aan het Insider-programma.</span><span class="sxs-lookup"><span data-stu-id="b662b-123">Join the Insider Program.</span></span>

1. <span data-ttu-id="b662b-124">De volgende Windows-updates zijn geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="b662b-124">The following Windows Updates are installed.</span></span>
    - <span data-ttu-id="b662b-125">Voor Windows 1809: installatie Windows [KB5003217 bijwerken](https://support.microsoft.com/topic/may-20-2021-kb5003217-os-build-17763-1971-preview-08687c95-0740-421b-a205-54aa2c716b46)</span><span class="sxs-lookup"><span data-stu-id="b662b-125">For Windows 1809: install Windows Update [KB5003217](https://support.microsoft.com/topic/may-20-2021-kb5003217-os-build-17763-1971-preview-08687c95-0740-421b-a205-54aa2c716b46)</span></span>
    - <span data-ttu-id="b662b-126">Voor Windows 1909: installatie Windows [KB5003212 bijwerken](https://support.microsoft.com/topic/may-20-2021-kb5003212-os-build-18363-1593-preview-05381524-8380-4b30-b783-e330cad3d4a1)</span><span class="sxs-lookup"><span data-stu-id="b662b-126">For Windows 1909: install Windows Update [KB5003212](https://support.microsoft.com/topic/may-20-2021-kb5003212-os-build-18363-1593-preview-05381524-8380-4b30-b783-e330cad3d4a1)</span></span>
    - <span data-ttu-id="b662b-127">Voor Windows 2004 of hoger</span><span class="sxs-lookup"><span data-stu-id="b662b-127">For Windows 2004 or later</span></span>

1. <span data-ttu-id="b662b-128">Als u beleid wilt implementeren via groepsbeleid, moet het apparaat zijn samengevoegd met MDATP. als u van plan bent beleid te implementeren via MEM, moet het apparaat zijn verbonden met Intune.</span><span class="sxs-lookup"><span data-stu-id="b662b-128">If you're planning to deploy policy via Group Policy, the device must be MDATP joined; if you're planning to deploy policy via MEM, the device must be Intune joined.</span></span>

## <a name="deploy-device-control-printer-protection-policy"></a><span data-ttu-id="b662b-129">Apparaatbesturingselement printerbeveiligingsbeleid implementeren</span><span class="sxs-lookup"><span data-stu-id="b662b-129">Deploy Device Control Printer Protection policy</span></span>

<span data-ttu-id="b662b-130">U kunt het beleid implementeren via Groepsbeleid of Intune.</span><span class="sxs-lookup"><span data-stu-id="b662b-130">You can deploy the policy via Group Policy or Intune.</span></span>

<br>

****

|<span data-ttu-id="b662b-131">Title</span><span class="sxs-lookup"><span data-stu-id="b662b-131">Title</span></span>|<span data-ttu-id="b662b-132">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="b662b-132">Description</span></span>|<span data-ttu-id="b662b-133">CSP-ondersteuning</span><span class="sxs-lookup"><span data-stu-id="b662b-133">CSP Support</span></span> | <span data-ttu-id="b662b-134">Ondersteuning voor GPO</span><span class="sxs-lookup"><span data-stu-id="b662b-134">GPO Support</span></span> | <span data-ttu-id="b662b-135">Ondersteuning op basis van gebruikers</span><span class="sxs-lookup"><span data-stu-id="b662b-135">User-based Support</span></span> | <span data-ttu-id="b662b-136">Ondersteuning op basis van machines</span><span class="sxs-lookup"><span data-stu-id="b662b-136">Machine-based Support</span></span> |
|---|---|:---:|:---:|:---:|:---:|
|<span data-ttu-id="b662b-137">**Apparaatbesturingselement afdrukbeperkingen inschakelen**</span><span class="sxs-lookup"><span data-stu-id="b662b-137">**Enable Device control Printing Restrictions**</span></span>|<span data-ttu-id="b662b-138">Personen blokkeren om af te drukken via een niet-zakelijke printer</span><span class="sxs-lookup"><span data-stu-id="b662b-138">Block people from printing via non-corporate printer</span></span>|<span data-ttu-id="b662b-139">Ja</span><span class="sxs-lookup"><span data-stu-id="b662b-139">Yes</span></span>|<span data-ttu-id="b662b-140">Ja</span><span class="sxs-lookup"><span data-stu-id="b662b-140">Yes</span></span>|<span data-ttu-id="b662b-141">Ja</span><span class="sxs-lookup"><span data-stu-id="b662b-141">Yes</span></span>|<span data-ttu-id="b662b-142">Ja</span><span class="sxs-lookup"><span data-stu-id="b662b-142">Yes</span></span>|
|<span data-ttu-id="b662b-143">**Lijst met goedgekeurde usb-verbonden afdrukapparaten**\*</span><span class="sxs-lookup"><span data-stu-id="b662b-143">**List of Approved USB-connected print devices**\*</span></span>|<span data-ttu-id="b662b-144">Specifieke USB-printer toestaan</span><span class="sxs-lookup"><span data-stu-id="b662b-144">Allow specific USB printer</span></span>|<span data-ttu-id="b662b-145">Ja</span><span class="sxs-lookup"><span data-stu-id="b662b-145">Yes</span></span>|<span data-ttu-id="b662b-146">Ja</span><span class="sxs-lookup"><span data-stu-id="b662b-146">Yes</span></span>|<span data-ttu-id="b662b-147">Ja</span><span class="sxs-lookup"><span data-stu-id="b662b-147">Yes</span></span>|<span data-ttu-id="b662b-148">Ja</span><span class="sxs-lookup"><span data-stu-id="b662b-148">Yes</span></span>|
|

<span data-ttu-id="b662b-149">\*Dit beleid moet samen met Afdrukbeperkingen **apparaatbesturingselement inschakelen worden gebruikt.**</span><span class="sxs-lookup"><span data-stu-id="b662b-149">\* This policy must be used together with **Enable Device control Printing Restrictions**.</span></span>

## <a name="deploy-policy-via-intune"></a><span data-ttu-id="b662b-150">Beleid implementeren via Intune</span><span class="sxs-lookup"><span data-stu-id="b662b-150">Deploy policy via Intune</span></span>

<span data-ttu-id="b662b-151">Voor Intune ondersteunt apparaatbesturingselementprinterbeveiliging op dit moment alleen OMA-URI.</span><span class="sxs-lookup"><span data-stu-id="b662b-151">For Intune, currently Device Control Printer Protection supports OMA-URI only.</span></span>

### <a name="scenario-1-block-people-from-printing-via-any-non-corporate-printer-using-intune"></a><span data-ttu-id="b662b-152">Scenario 1: Voorkomen dat personen afdrukken via een niet-zakelijke printer met Intune</span><span class="sxs-lookup"><span data-stu-id="b662b-152">Scenario 1: Block people from printing via any non-corporate printer using Intune</span></span>

- <span data-ttu-id="b662b-153">Beleid toepassen op computer:</span><span class="sxs-lookup"><span data-stu-id="b662b-153">Apply policy over machine:</span></span>

  `./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControl`

- <span data-ttu-id="b662b-154">Beleid toepassen op gebruiker:</span><span class="sxs-lookup"><span data-stu-id="b662b-154">Apply policy over user:</span></span>

  `./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControlUser`

<span data-ttu-id="b662b-155">De CSP-ondersteuningsreeks `<enabled/>` met:</span><span class="sxs-lookup"><span data-stu-id="b662b-155">The CSP support string with `<enabled/>`:</span></span>

:::image type="content" source="../../media/customeditrow.png" alt-text="aangepaste bewerkingsrij":::

### <a name="scenario-2-allow-specific-approved-usb-printers-using-intune"></a><span data-ttu-id="b662b-157">Scenario 2: Specifieke goedgekeurde USB-printers toestaan met Intune</span><span class="sxs-lookup"><span data-stu-id="b662b-157">Scenario 2: Allow specific approved USB printers using Intune</span></span>

- <span data-ttu-id="b662b-158">Beleid toepassen op computer:</span><span class="sxs-lookup"><span data-stu-id="b662b-158">Apply policy over machine:</span></span>

  `./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevices`

- <span data-ttu-id="b662b-159">Beleid toepassen op gebruiker:</span><span class="sxs-lookup"><span data-stu-id="b662b-159">Apply policy over user:</span></span>

  `./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevicesUser`

<span data-ttu-id="b662b-160">De CSP-ondersteuningsreeks met goedgekeurde USB-printers via de eigenschap ApprovedUsbPrintDevices, `<enabled><data id="ApprovedUsbPrintDevices_List" value="03F0/0853,0351/0872">` bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="b662b-160">The CSP support string with approved USB printers via 'ApprovedUsbPrintDevices' property, example `<enabled><data id="ApprovedUsbPrintDevices_List" value="03F0/0853,0351/0872">`:</span></span>

:::image type="content" source="../../media/editrow.png" alt-text="rij bewerken":::

## <a name="deploy-policy-via-group-policy"></a><span data-ttu-id="b662b-162">Beleid implementeren via groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="b662b-162">Deploy policy via Group Policy</span></span>

<span data-ttu-id="b662b-163">Als het apparaat niet is verbonden met Intune, kunt u het beleid ook implementeren via groepsbeleid.</span><span class="sxs-lookup"><span data-stu-id="b662b-163">If the device isn't Intune joined, you can also deploy the policy via Group Policy.</span></span>

### <a name="scenario-1-block-people-from-printing-via-any-non-corporate-printer-using-group-policy"></a><span data-ttu-id="b662b-164">Scenario 1: Voorkomen dat personen afdrukken via een niet-zakelijke printer met groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="b662b-164">Scenario 1: Block people from printing via any non-corporate printer using Group Policy</span></span>

- <span data-ttu-id="b662b-165">Beleid toepassen op computer:</span><span class="sxs-lookup"><span data-stu-id="b662b-165">Apply policy over machine:</span></span>

  <span data-ttu-id="b662b-166">Printer voor \> beheersjablonen voor computerconfiguratie: \> Afdrukbeperkingen voor apparaatbesturingselementen inschakelen</span><span class="sxs-lookup"><span data-stu-id="b662b-166">Computer Configuration \> Administrative Templates \> Printer: Enable Device control Printing Restrictions</span></span>

- <span data-ttu-id="b662b-167">Beleid toepassen op gebruiker:</span><span class="sxs-lookup"><span data-stu-id="b662b-167">Apply policy over user:</span></span>

  <span data-ttu-id="b662b-168">\>Configuratiebeheersjablonen \> \> configuratieschermprinters voor gebruikersconfiguratie: Afdrukbeperkingen voor apparaatbesturingselementen inschakelen</span><span class="sxs-lookup"><span data-stu-id="b662b-168">User Configuration \> Administrative Templates \> Control Panel \> Printers: Enable Device control Printing Restrictions</span></span>

:::image type="content" source="../../media/enable-device-ctrl-printing-restrictions.png" alt-text="beperkingen voor het afdrukken van apparaten inschakelen":::

### <a name="scenario-2-allow-specific-approved-usb-printers-using-group-policy"></a><span data-ttu-id="b662b-170">Scenario 2: Specifieke goedgekeurde USB-printers toestaan met groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="b662b-170">Scenario 2: Allow specific approved USB printers using Group Policy</span></span>

- <span data-ttu-id="b662b-171">Beleid toepassen op computer:</span><span class="sxs-lookup"><span data-stu-id="b662b-171">Apply policy over machine:</span></span>

  <span data-ttu-id="b662b-172">Printer voor \> beheersjablonen voor computerconfiguratie: \> lijst met goedgekeurde afdrukapparaten met USB-verbinding</span><span class="sxs-lookup"><span data-stu-id="b662b-172">Computer Configuration \> Administrative Templates \> Printer:  List of Approved USB-connected print devices</span></span>

- <span data-ttu-id="b662b-173">Beleid toepassen op gebruiker:</span><span class="sxs-lookup"><span data-stu-id="b662b-173">Apply policy over user:</span></span>

  <span data-ttu-id="b662b-174">\>Configuratiebeheersjablonen \> \> configuratieschermprinters voor gebruikersconfiguratie: lijst met goedgekeurde afdrukapparaten met USB-verbinding</span><span class="sxs-lookup"><span data-stu-id="b662b-174">User Configuration \> Administrative Templates \> Control Panel \> Printers: List of Approved USB-connected print devices</span></span>

:::image type="content" source="../../media/list-of-approved-connected-print-devices.png" alt-text="lijst met goedgekeurde usb-verbonden afdrukapparaten":::

## <a name="view-device-control-printer-protection-data-in-microsoft-defender-for-endpoint-portal"></a><span data-ttu-id="b662b-176">Apparaatbesturingselement printerbeveiligingsgegevens weergeven in microsoft Defender voor eindpuntportal</span><span class="sxs-lookup"><span data-stu-id="b662b-176">View Device Control Printer Protection data in Microsoft Defender for Endpoint portal</span></span>

<span data-ttu-id="b662b-177">In [Microsoft 365 beveiligingscentrum ziet](https://security.microsoft.com) u afdrukken die zijn geblokkeerd door het beleid voor apparaatbesturingselementprinterbeveiliging hierboven.</span><span class="sxs-lookup"><span data-stu-id="b662b-177">The [Microsoft 365 security center](https://security.microsoft.com) shows printing blocked by the Device Control Printer Protection policy above.</span></span>

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
