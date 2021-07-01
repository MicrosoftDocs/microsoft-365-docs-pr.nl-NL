---
title: Microsoft Defender voor Endpoint Device Control Verwisselbare Storage Access Control
description: Een walk-through over Microsoft Defender voor Endpoint
keywords: verwisselbare opslagmedia
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 8b32ab5162e0022d9500f7ddba2fe5bbca1017e7
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229573"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-access-control"></a><span data-ttu-id="9de1d-104">Microsoft Defender voor Endpoint Device Control Verwisselbare Storage Access Control</span><span class="sxs-lookup"><span data-stu-id="9de1d-104">Microsoft Defender for Endpoint Device Control Removable Storage Access Control</span></span>

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="9de1d-105">Met Microsoft Defender voor Endpoint Device Control Verwisselbaar Storage Access Control kunt u de volgende taak uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="9de1d-105">Microsoft Defender for Endpoint Device Control Removable Storage Access Control enables you to do the following task:</span></span>
- <span data-ttu-id="9de1d-106">het lezen, schrijven of uitvoeren van toegang tot verwisselbare opslag, met of zonder uitsluiting, toestaan of voorkomen</span><span class="sxs-lookup"><span data-stu-id="9de1d-106">auditing, allowing or preventing the read, write or execute access to removable storage with or without exclusion</span></span>

|<span data-ttu-id="9de1d-107">Privilege</span><span class="sxs-lookup"><span data-stu-id="9de1d-107">Privilege</span></span> |<span data-ttu-id="9de1d-108">Machtiging</span><span class="sxs-lookup"><span data-stu-id="9de1d-108">Permission</span></span>  |
|---------|---------|
|<span data-ttu-id="9de1d-109">Toegang</span><span class="sxs-lookup"><span data-stu-id="9de1d-109">Access</span></span>    |  <span data-ttu-id="9de1d-110">Lezen, Schrijven, Uitvoeren</span><span class="sxs-lookup"><span data-stu-id="9de1d-110">Read, Write, Execute</span></span>       |
|<span data-ttu-id="9de1d-111">Actiemodus</span><span class="sxs-lookup"><span data-stu-id="9de1d-111">Action Mode</span></span>    |    <span data-ttu-id="9de1d-112">Controleren, Toestaan, Voorkomen</span><span class="sxs-lookup"><span data-stu-id="9de1d-112">Audit, Allow, Prevent</span></span>     |
|<span data-ttu-id="9de1d-113">CSP-ondersteuning</span><span class="sxs-lookup"><span data-stu-id="9de1d-113">CSP Support</span></span>   |   <span data-ttu-id="9de1d-114">Ja</span><span class="sxs-lookup"><span data-stu-id="9de1d-114">Yes</span></span>      |
|<span data-ttu-id="9de1d-115">Ondersteuning voor GPO</span><span class="sxs-lookup"><span data-stu-id="9de1d-115">GPO Support</span></span>    |   <span data-ttu-id="9de1d-116">Ja</span><span class="sxs-lookup"><span data-stu-id="9de1d-116">Yes</span></span>      |
|<span data-ttu-id="9de1d-117">Ondersteuning op basis van gebruikers</span><span class="sxs-lookup"><span data-stu-id="9de1d-117">User-based Support</span></span>     |   <span data-ttu-id="9de1d-118">Ja</span><span class="sxs-lookup"><span data-stu-id="9de1d-118">Yes</span></span>      |
|<span data-ttu-id="9de1d-119">Ondersteuning op basis van machines</span><span class="sxs-lookup"><span data-stu-id="9de1d-119">Machine-based Support</span></span>    |    <span data-ttu-id="9de1d-120">Ja</span><span class="sxs-lookup"><span data-stu-id="9de1d-120">Yes</span></span>     |

## <a name="prepare-your-endpoints"></a><span data-ttu-id="9de1d-121">Uw eindpunten voorbereiden</span><span class="sxs-lookup"><span data-stu-id="9de1d-121">Prepare your endpoints</span></span>

<span data-ttu-id="9de1d-122">Verwisselbare Storage Access Control implementeren op Windows 10 apparaten met antimalwareclient **versie 4.18.2103.3 of hoger.**</span><span class="sxs-lookup"><span data-stu-id="9de1d-122">Deploy Removable Storage Access Control on Windows 10 devices that have antimalware client version **4.18.2103.3 or later**.</span></span>

- <span data-ttu-id="9de1d-123">**4.18.2104 of hoger:** SerialNumberId, VID_PID, filepath-based GPO support, ComputerSid</span><span class="sxs-lookup"><span data-stu-id="9de1d-123">**4.18.2104 or later**: Add SerialNumberId, VID_PID, filepath-based GPO support, ComputerSid</span></span>

- <span data-ttu-id="9de1d-124">**4.18.2105** of hoger : Jokertekenondersteuning toevoegen voor HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId, de combinatie van specifieke gebruiker op een specifieke computer, verwijderbare SSD (een SanDisk Extreme SSD)/USB Attached SCSI (UAS) ondersteuning</span><span class="sxs-lookup"><span data-stu-id="9de1d-124">**4.18.2105 or later**: Add Wildcard support for HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId, the combination of specific user on specific machine, removeable SSD (a SanDisk Extreme SSD)/USB Attached SCSI (UAS) support</span></span>

:::image type="content" source="images/powershell.png" alt-text="De PowerShell-interface":::

> [!NOTE]
> <span data-ttu-id="9de1d-126">Geen van Windows-beveiliging onderdelen hoeft actief te zijn, u kunt Verwisselbaar Storage Access Control uitvoeren, onafhankelijk van Windows-beveiliging status.</span><span class="sxs-lookup"><span data-stu-id="9de1d-126">None of Windows Security components need to be active, you can run Removable Storage Access Control independent of Windows Security status.</span></span>

## <a name="policy-properties"></a><span data-ttu-id="9de1d-127">Beleidseigenschappen</span><span class="sxs-lookup"><span data-stu-id="9de1d-127">Policy properties</span></span>

<span data-ttu-id="9de1d-128">U kunt de volgende eigenschappen gebruiken om een verwisselbare opslaggroep te maken:</span><span class="sxs-lookup"><span data-stu-id="9de1d-128">You can use the following properties to create a removable storage group:</span></span>

<span data-ttu-id="9de1d-129">**Naam van eigenschap: groeps-id**</span><span class="sxs-lookup"><span data-stu-id="9de1d-129">**Property name: Group Id**</span></span>

1. <span data-ttu-id="9de1d-130">Beschrijving: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), een unieke id, vertegenwoordigt de groep en wordt gebruikt in het beleid.</span><span class="sxs-lookup"><span data-stu-id="9de1d-130">Description: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), a unique ID, represents the group and will be used in the policy.</span></span>

<span data-ttu-id="9de1d-131">**Eigenschapsnaam: DescriptorIdList**</span><span class="sxs-lookup"><span data-stu-id="9de1d-131">**Property name: DescriptorIdList**</span></span>

1. <span data-ttu-id="9de1d-132">Beschrijving: Vermeld de apparaateigenschappen die u wilt gebruiken voor de groep.</span><span class="sxs-lookup"><span data-stu-id="9de1d-132">Description: List the device properties you want to use to cover in the group.</span></span>
<span data-ttu-id="9de1d-133">Vermeld de apparaateigenschappen die u wilt gebruiken voor de groep.</span><span class="sxs-lookup"><span data-stu-id="9de1d-133">List the device properties you want to use to cover in the group.</span></span>
<span data-ttu-id="9de1d-134">Zie voor elke apparaateigenschappen de sectie **Apparaateigenschappen** hierboven voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="9de1d-134">For each device property, see **Device Properties** section above for more detail.</span></span>

1. <span data-ttu-id="9de1d-135">Opties:</span><span class="sxs-lookup"><span data-stu-id="9de1d-135">Options:</span></span>

    - <span data-ttu-id="9de1d-136">Primaire id</span><span class="sxs-lookup"><span data-stu-id="9de1d-136">Primary ID</span></span>
        - <span data-ttu-id="9de1d-137">VerwisselbareMediaDevices</span><span class="sxs-lookup"><span data-stu-id="9de1d-137">RemovableMediaDevices</span></span>
        - <span data-ttu-id="9de1d-138">CdRomDevices</span><span class="sxs-lookup"><span data-stu-id="9de1d-138">CdRomDevices</span></span>
    - <span data-ttu-id="9de1d-139">DeviceId</span><span class="sxs-lookup"><span data-stu-id="9de1d-139">DeviceId</span></span>
    - <span data-ttu-id="9de1d-140">HardwareId</span><span class="sxs-lookup"><span data-stu-id="9de1d-140">HardwareId</span></span>
    - <span data-ttu-id="9de1d-141">InstancePathId: InstancePathId is een tekenreeks die het apparaat in het systeem uniek identificeert, bijvoorbeeld USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0.</span><span class="sxs-lookup"><span data-stu-id="9de1d-141">InstancePathId: InstancePathId is a string that uniquely identifies the device in the system, for example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0.</span></span> <span data-ttu-id="9de1d-142">Het getal aan het einde **(bijvoorbeeld&0)** vertegenwoordigt de beschikbare sleuf en kan veranderen van apparaat naar apparaat.</span><span class="sxs-lookup"><span data-stu-id="9de1d-142">The number at the end (for example **&0**) represents the available slot and may change from device to device.</span></span> <span data-ttu-id="9de1d-143">Voor de beste resultaten gebruikt u een jokerteken aan het einde.</span><span class="sxs-lookup"><span data-stu-id="9de1d-143">For best results, use a wildcard at the end.</span></span> <span data-ttu-id="9de1d-144">Bijvoorbeeld: USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611\*</span><span class="sxs-lookup"><span data-stu-id="9de1d-144">For example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611\*</span></span>
    - <span data-ttu-id="9de1d-145">FriendlyNameId</span><span class="sxs-lookup"><span data-stu-id="9de1d-145">FriendlyNameId</span></span>
    - <span data-ttu-id="9de1d-146">SerialNumberId</span><span class="sxs-lookup"><span data-stu-id="9de1d-146">SerialNumberId</span></span>
    - <span data-ttu-id="9de1d-147">VID</span><span class="sxs-lookup"><span data-stu-id="9de1d-147">VID</span></span>
    - <span data-ttu-id="9de1d-148">PID</span><span class="sxs-lookup"><span data-stu-id="9de1d-148">PID</span></span>
    - <span data-ttu-id="9de1d-149">VID_PID</span><span class="sxs-lookup"><span data-stu-id="9de1d-149">VID_PID</span></span>
        - <span data-ttu-id="9de1d-150">0751_55E0: overeenkomen met dit exacte VID/PID-paar</span><span class="sxs-lookup"><span data-stu-id="9de1d-150">0751_55E0: match this exact VID/PID pair</span></span>
        - <span data-ttu-id="9de1d-151">_55E0: overeenkomen met alle media met PID=55E0</span><span class="sxs-lookup"><span data-stu-id="9de1d-151">_55E0: match any media with PID=55E0</span></span>
        - <span data-ttu-id="9de1d-152">0751_: overeenkomen met alle media met VID=0751</span><span class="sxs-lookup"><span data-stu-id="9de1d-152">0751_: match any media with VID=0751</span></span>
        
<span data-ttu-id="9de1d-153">**Eigenschapsnaam: MatchType**</span><span class="sxs-lookup"><span data-stu-id="9de1d-153">**Property name: MatchType**</span></span> 

1. <span data-ttu-id="9de1d-154">Beschrijving: Wanneer er meerdere apparaateigenschappen worden gebruikt in de DescriptorIDList, definieert MatchType de relatie.</span><span class="sxs-lookup"><span data-stu-id="9de1d-154">Description: When there are multiple device properties being used in the DescriptorIDList, MatchType defines the relationship.</span></span>

1. <span data-ttu-id="9de1d-155">Opties:</span><span class="sxs-lookup"><span data-stu-id="9de1d-155">Options:</span></span>

    - <span data-ttu-id="9de1d-156">MatchAll: Alle kenmerken onder de DescriptorIdList zijn **En-relatie;** Als de beheerder bijvoorbeeld DeviceID en InstancePathID plaatst, controleert het systeem voor elke aangesloten USB of de USB aan beide waarden voldoet.</span><span class="sxs-lookup"><span data-stu-id="9de1d-156">MatchAll: Any attributes under the DescriptorIdList will be **And** relationship; for example, if administrator puts DeviceID and InstancePathID, for every connected USB, system will check to see whether the USB meets both values.</span></span>
    - <span data-ttu-id="9de1d-157">MatchAny: De kenmerken onder de DescriptorIdList zijn **Of-relatie;** Als de beheerder bijvoorbeeld DeviceID en InstancePathID plaatst, voert het systeem voor elke aangesloten  USB de afdwinging uit, zolang de USB een identieke Apparaat-id- of Exemplaar-id-waarde heeft. </span><span class="sxs-lookup"><span data-stu-id="9de1d-157">MatchAny: The attributes under the DescriptorIdList will be **Or** relationship; for example, if administrator puts DeviceID and InstancePathID, for every connected USB, system will do the enforcement as long as the USB has either an identical **DeviceID** or **InstanceID** value.</span></span>

<span data-ttu-id="9de1d-158">Hieronder volgen de eigenschappen van het toegangsbeheerbeleid:</span><span class="sxs-lookup"><span data-stu-id="9de1d-158">Following are the access control policy properties:</span></span>

<span data-ttu-id="9de1d-159">**Naam van eigenschap: PolicyRuleId**</span><span class="sxs-lookup"><span data-stu-id="9de1d-159">**Property name: PolicyRuleId**</span></span>

1. <span data-ttu-id="9de1d-160">Beschrijving: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), een unieke id, vertegenwoordigt het beleid en wordt gebruikt in de rapportage en probleemoplossing.</span><span class="sxs-lookup"><span data-stu-id="9de1d-160">Description: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), a unique ID, represents the policy and will be used in the reporting and troubleshooting.</span></span>

<span data-ttu-id="9de1d-161">**Naam van eigenschap: IncludedIdList**</span><span class="sxs-lookup"><span data-stu-id="9de1d-161">**Property name: IncludedIdList**</span></span>

2. <span data-ttu-id="9de1d-162">Beschrijving: De groep(en) waar het beleid op wordt toegepast.</span><span class="sxs-lookup"><span data-stu-id="9de1d-162">Description: The group(s) that the policy will be applied to.</span></span> <span data-ttu-id="9de1d-163">Als er meerdere groepen worden toegevoegd, wordt het beleid toegepast op alle media in al deze groepen.</span><span class="sxs-lookup"><span data-stu-id="9de1d-163">If multiple groups are added, the policy will be applied to any media in all those groups.</span></span>

3. <span data-ttu-id="9de1d-164">Opties: De groeps-id/GUID moet in dit exemplaar worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="9de1d-164">Options: The Group ID/GUID must be used at this instance.</span></span>

<span data-ttu-id="9de1d-165">In het volgende voorbeeld ziet u het gebruik van GroupID:</span><span class="sxs-lookup"><span data-stu-id="9de1d-165">The following example shows the usage of GroupID:</span></span>

`<IncludedIdList> <GroupId>{EAA4CCE5-F6C9-4760-8BAD-FDCC76A2ACA1}</GroupId> </IncludedIdList>`

<span data-ttu-id="9de1d-166">**Eigenschapsnaam: ExcludedIDList**</span><span class="sxs-lookup"><span data-stu-id="9de1d-166">**Property name: ExcludedIDList**</span></span>

<span data-ttu-id="9de1d-167">Beschrijving: De groep(en) waar het beleid niet op wordt toegepast.</span><span class="sxs-lookup"><span data-stu-id="9de1d-167">Description: The group(s) that the policy will not be applied to.</span></span>

<span data-ttu-id="9de1d-168">Opties: De groeps-id/GUID moet in dit exemplaar worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="9de1d-168">Options: The Group ID/GUID must be used at this instance.</span></span>

<span data-ttu-id="9de1d-169">**Naam van eigenschap: invoer-id**</span><span class="sxs-lookup"><span data-stu-id="9de1d-169">**Property name: Entry Id**</span></span>

1. <span data-ttu-id="9de1d-170">Beschrijving: Eén beleidsregel kan meerdere vermeldingen bevatten; Elke vermelding met een unieke GUID geeft apparaatbeheer één beperking aan.</span><span class="sxs-lookup"><span data-stu-id="9de1d-170">Description: One PolicyRule can have multiple entries; each entry with a unique GUID tells Device Control one restriction.</span></span>

<span data-ttu-id="9de1d-171">**Eigenschapsnaam: Type**</span><span class="sxs-lookup"><span data-stu-id="9de1d-171">**Property name: Type**</span></span>

1. <span data-ttu-id="9de1d-172">Beschrijving: Definieert de actie voor de verwisselbare opslaggroepen in IncludedIDList.</span><span class="sxs-lookup"><span data-stu-id="9de1d-172">Description: Defines the action for the removable storage groups in IncludedIDList.</span></span>
    - <span data-ttu-id="9de1d-173">Afdwinging: Toestaan of weigeren</span><span class="sxs-lookup"><span data-stu-id="9de1d-173">Enforcement: Allow or Deny</span></span>
    - <span data-ttu-id="9de1d-174">Audit: AuditAllowed or AuditDenied</span><span class="sxs-lookup"><span data-stu-id="9de1d-174">Audit: AuditAllowed or AuditDenied</span></span> 

2. <span data-ttu-id="9de1d-175">Opties:</span><span class="sxs-lookup"><span data-stu-id="9de1d-175">Options:</span></span>

    - <span data-ttu-id="9de1d-176">Toestaan</span><span class="sxs-lookup"><span data-stu-id="9de1d-176">Allow</span></span>
    - <span data-ttu-id="9de1d-177">Weigeren</span><span class="sxs-lookup"><span data-stu-id="9de1d-177">Deny</span></span>
    - <span data-ttu-id="9de1d-178">AuditAllowed: Definieert melding en gebeurtenis wanneer toegang is toegestaan</span><span class="sxs-lookup"><span data-stu-id="9de1d-178">AuditAllowed: Defines notification and event when access is allowed</span></span>
    - <span data-ttu-id="9de1d-179">AuditDenied: Definieert melding en gebeurtenis wanneer toegang wordt geweigerd; moet samenwerken met **Vermelding weigeren.**</span><span class="sxs-lookup"><span data-stu-id="9de1d-179">AuditDenied: Defines notification and event when access is denied; has to work together with **Deny** entry.</span></span>

<span data-ttu-id="9de1d-180">Wanneer er conflicttypen voor dezelfde media zijn, wordt het eerste conflict in het beleid toegepast.</span><span class="sxs-lookup"><span data-stu-id="9de1d-180">When there are conflict types for the same media, the system will apply the first one in the policy.</span></span> <span data-ttu-id="9de1d-181">Een voorbeeld van een conflicttype is **Toestaan** en **Weigeren.**</span><span class="sxs-lookup"><span data-stu-id="9de1d-181">An example of a conflict type is **Allow** and **Deny**.</span></span>

<span data-ttu-id="9de1d-182">**Naam van eigenschap: Sid**</span><span class="sxs-lookup"><span data-stu-id="9de1d-182">**Property name: Sid**</span></span>

<span data-ttu-id="9de1d-183">Beschrijving: Hiermee bepaalt u of u dit beleid moet toepassen op specifieke gebruikers of gebruikersgroep; een vermelding kan maximaal één Sid hebben en een vermelding zonder dat sid betekent dat het beleid op de computer wordt toegepast.</span><span class="sxs-lookup"><span data-stu-id="9de1d-183">Description: Defines whether apply this policy over specific user or user group; one entry can have maximum one Sid and an entry without any Sid means applying the policy over the machine.</span></span>

<span data-ttu-id="9de1d-184">**Naam van eigenschap: ComputerSid**</span><span class="sxs-lookup"><span data-stu-id="9de1d-184">**Property name: ComputerSid**</span></span>

<span data-ttu-id="9de1d-185">Beschrijving: Hiermee bepaalt u of u dit beleid moet toepassen op een specifieke machine- of machinegroep; één invoer kan maximaal één ComputerSid hebben en een vermelding zonder computerSid betekent dat u het beleid op de computer moet toepassen.</span><span class="sxs-lookup"><span data-stu-id="9de1d-185">Description: Defines whether apply this policy over specific machine or machine group; one entry can have maximum one ComputerSid and an entry without any ComputerSid means applying the policy over the machine.</span></span> <span data-ttu-id="9de1d-186">Als u een vermelding wilt toepassen op een specifieke gebruiker en specifieke computer, voegt u zowel Sid als ComputerSid toe aan dezelfde vermelding.</span><span class="sxs-lookup"><span data-stu-id="9de1d-186">If you want to apply an Entry to a specific user and specific machine, add both Sid and ComputerSid into the same Entry.</span></span>

<span data-ttu-id="9de1d-187">**Eigenschapsnaam: Opties**</span><span class="sxs-lookup"><span data-stu-id="9de1d-187">**Property name: Options**</span></span>

<span data-ttu-id="9de1d-188">Beschrijving: Definieert of u een melding wilt weergeven of niet.</span><span class="sxs-lookup"><span data-stu-id="9de1d-188">Description: Defines whether to display notification or not.</span></span>

   :::image type="content" source="images/device-status.png" alt-text="Het scherm waarop de status van het apparaat kan worden gezien":::

<span data-ttu-id="9de1d-190">Opties: 0-4.</span><span class="sxs-lookup"><span data-stu-id="9de1d-190">Options: 0-4.</span></span> <span data-ttu-id="9de1d-191">Wanneer Toestaan of Weigeren typen is geselecteerd:</span><span class="sxs-lookup"><span data-stu-id="9de1d-191">When Type Allow or Deny is selected:</span></span>

   - <span data-ttu-id="9de1d-192">0: niets</span><span class="sxs-lookup"><span data-stu-id="9de1d-192">0: nothing</span></span>
   - <span data-ttu-id="9de1d-193">4: Schakel **AuditAllowed en** **AuditDenied uit** voor deze vermelding.</span><span class="sxs-lookup"><span data-stu-id="9de1d-193">4: disable **AuditAllowed** and **AuditDenied** for this Entry.</span></span> <span data-ttu-id="9de1d-194">Zelfs als **Blokkering** wordt uitgevoerd en **de instelling AuditDenied** is geconfigureerd, wordt er geen melding in het systeem uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="9de1d-194">Even if **Block** happens and the **AuditDenied** is setting configured, the system will not show notification.</span></span>

   <span data-ttu-id="9de1d-195">Wanneer Type **AuditAllowed of** **AuditDenied** is geselecteerd:</span><span class="sxs-lookup"><span data-stu-id="9de1d-195">When Type **AuditAllowed** or **AuditDenied** is selected:</span></span>

   - <span data-ttu-id="9de1d-196">0: niets</span><span class="sxs-lookup"><span data-stu-id="9de1d-196">0: nothing</span></span>
   - <span data-ttu-id="9de1d-197">1: melding tonen</span><span class="sxs-lookup"><span data-stu-id="9de1d-197">1: show notification</span></span>
   - <span data-ttu-id="9de1d-198">2: gebeurtenis verzenden</span><span class="sxs-lookup"><span data-stu-id="9de1d-198">2: send event</span></span>
   - <span data-ttu-id="9de1d-199">3: melding tonen en gebeurtenis verzenden</span><span class="sxs-lookup"><span data-stu-id="9de1d-199">3: show notification and send event</span></span>

<span data-ttu-id="9de1d-200">**Naam van eigenschap: AccessMask**</span><span class="sxs-lookup"><span data-stu-id="9de1d-200">**Property name: AccessMask**</span></span>

<span data-ttu-id="9de1d-201">Beschrijving: Definieert de toegang.</span><span class="sxs-lookup"><span data-stu-id="9de1d-201">Description: Defines the access.</span></span>

<span data-ttu-id="9de1d-202">Opties 1-7:</span><span class="sxs-lookup"><span data-stu-id="9de1d-202">Options 1-7:</span></span>
  - <span data-ttu-id="9de1d-203">1: Lezen</span><span class="sxs-lookup"><span data-stu-id="9de1d-203">1: Read</span></span>
  - <span data-ttu-id="9de1d-204">2: Schrijven</span><span class="sxs-lookup"><span data-stu-id="9de1d-204">2: Write</span></span>
  - <span data-ttu-id="9de1d-205">3: Lezen en schrijven</span><span class="sxs-lookup"><span data-stu-id="9de1d-205">3: Read and Write</span></span>
  - <span data-ttu-id="9de1d-206">4: Uitvoeren</span><span class="sxs-lookup"><span data-stu-id="9de1d-206">4: Execute</span></span>
  - <span data-ttu-id="9de1d-207">5: Lezen en uitvoeren</span><span class="sxs-lookup"><span data-stu-id="9de1d-207">5: Read and Execute</span></span>
  - <span data-ttu-id="9de1d-208">6: Schrijven en uitvoeren</span><span class="sxs-lookup"><span data-stu-id="9de1d-208">6: Write and Execute</span></span>
  - <span data-ttu-id="9de1d-209">7: Lezen en schrijven en uitvoeren</span><span class="sxs-lookup"><span data-stu-id="9de1d-209">7: Read and Write and Execute</span></span>

## <a name="common-removable-storage-access-control-scenarios"></a><span data-ttu-id="9de1d-210">Veelvoorkomende verwisselbare Storage Access Control-scenario's</span><span class="sxs-lookup"><span data-stu-id="9de1d-210">Common Removable Storage Access Control scenarios</span></span>

<span data-ttu-id="9de1d-211">Om u vertrouwd te maken met Microsoft Defender voor eindpuntverwisselbaar Storage Access Control, hebben we een aantal veelvoorkomende scenario's voor u opgesteld die u kunt volgen.</span><span class="sxs-lookup"><span data-stu-id="9de1d-211">To help familiarize you with Microsoft Defender for Endpoint Removable Storage Access Control, we have put together some common scenarios for you to follow.</span></span>

### <a name="scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs"></a><span data-ttu-id="9de1d-212">Scenario 1: Schrijf- en uitvoertoegang tot iedereen voorkomen, maar sta specifieke goedgekeurde USB's toe</span><span class="sxs-lookup"><span data-stu-id="9de1d-212">Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs</span></span>

1. <span data-ttu-id="9de1d-213">Groepen aanmaken</span><span class="sxs-lookup"><span data-stu-id="9de1d-213">Create groups</span></span>

    1. <span data-ttu-id="9de1d-214">Groep 1: Eventuele verwisselbare opslag en cd/dvd.</span><span class="sxs-lookup"><span data-stu-id="9de1d-214">Group 1: Any removable storage and CD/DVD.</span></span> <span data-ttu-id="9de1d-215">Een voorbeeld van een verwisselbare opslag en cd/dvd is: Groep **9b28fae8-72f7-4267-a1a5-685f747a7146** in het voorbeeld Elk verwisselbaar Storage- en [cd-dvd-Group.xml-bestand.](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)</span><span class="sxs-lookup"><span data-stu-id="9de1d-215">An example of a removable storage and CD/DVD is: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** in the sample [Any Removable Storage and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="9de1d-216">Groep 2: Goedgekeurde USB's op basis van apparaateigenschappen.</span><span class="sxs-lookup"><span data-stu-id="9de1d-216">Group 2: Approved USBs based on device properties.</span></span> <span data-ttu-id="9de1d-217">Een voorbeeld van deze use case is: Instance ID – Group **65fa649a-a111-4912-9294-fb6337a25038** in the sample [Approved USBs Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span><span class="sxs-lookup"><span data-stu-id="9de1d-217">An example for this use case is: Instance ID – Group **65fa649a-a111-4912-9294-fb6337a25038** in the sample [Approved USBs Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9de1d-218">U moet vervangen `&` door `&amp;` in de waarde.</span><span class="sxs-lookup"><span data-stu-id="9de1d-218">You have to replace `&` with `&amp;` in the value.</span></span>

2. <span data-ttu-id="9de1d-219">Beleid maken</span><span class="sxs-lookup"><span data-stu-id="9de1d-219">Create policy</span></span>

    1. <span data-ttu-id="9de1d-220">Beleid 1: Schrijf- en uitvoertoegang blokkeren, maar goedgekeurde USB's toestaan.</span><span class="sxs-lookup"><span data-stu-id="9de1d-220">Policy 1: Block Write and Execute Access but allow approved USBs.</span></span> <span data-ttu-id="9de1d-221">Een voorbeeld van deze use case is: PolicyRule **c544a991-5786-4402-949e-a032cb790d0e** in het voorbeeld [scenario 1 Blokschrijven](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) en Access uitvoeren, maar goedgekeurd USBs.xml-bestand toestaan.</span><span class="sxs-lookup"><span data-stu-id="9de1d-221">An example for this use case is: PolicyRule **c544a991-5786-4402-949e-a032cb790d0e** in the sample [Scenario 1 Block Write and Execute Access but allow approved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="9de1d-222">Beleid 2: Controle schrijf- en uitvoertoegang tot toegestane USB's.</span><span class="sxs-lookup"><span data-stu-id="9de1d-222">Policy 2: Audit Write and Execute access to allowed USBs.</span></span> <span data-ttu-id="9de1d-223">Een voorbeeld van deze use case is: PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c** in het voorbeeld [van Scenario 1 Audit Write and Execute access to approved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span><span class="sxs-lookup"><span data-stu-id="9de1d-223">An example for this use case is: PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c** in the sample [Scenario 1 Audit Write and Execute access to approved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

### <a name="scenario-2-audit-write-and-execute-access-to-all-but-block-specific-unapproved-usbs"></a><span data-ttu-id="9de1d-224">Scenario 2: Audit Write and Execute access to all but block specific unapproved USBs</span><span class="sxs-lookup"><span data-stu-id="9de1d-224">Scenario 2: Audit Write and Execute access to all but block specific unapproved USBs</span></span>

1. <span data-ttu-id="9de1d-225">Groepen aanmaken</span><span class="sxs-lookup"><span data-stu-id="9de1d-225">Create groups</span></span>

    1. <span data-ttu-id="9de1d-226">Groep 1: Eventuele verwisselbare opslag en cd/dvd.</span><span class="sxs-lookup"><span data-stu-id="9de1d-226">Group 1: Any removable storage and CD/DVD.</span></span> <span data-ttu-id="9de1d-227">Een voorbeeld van dit gebruiksvoorbeeld is: Groep **9b28fae8-72f7-4267-a1a5-685f747a7146** in het voorbeeld Een verwisselbaar Storage- en [cd-dvd-Group.xml-bestand.](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)</span><span class="sxs-lookup"><span data-stu-id="9de1d-227">An example for this use case is: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** in the sample [Any Removable Storage and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="9de1d-228">Groep 2: Niet-goedgekeurde USB's op basis van apparaateigenschappen, bijvoorbeeld Leverancier-id/product-id, vriendelijke naam – Groep **65fa649a-a111-4912-9294-fb6337a25038** in het voorbeeld Van niet-goedgekeurde [USB's Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) bestand.</span><span class="sxs-lookup"><span data-stu-id="9de1d-228">Group 2: Unapproved USBs based on device properties, for example, Vendor ID / Product ID, Friendly Name – Group **65fa649a-a111-4912-9294-fb6337a25038** in the sample [Unapproved USBs Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="9de1d-229">U moet vervangen `&` door `&amp;` in de waarde.</span><span class="sxs-lookup"><span data-stu-id="9de1d-229">You have to replace `&` with `&amp;` in the value.</span></span>

2. <span data-ttu-id="9de1d-230">Beleid maken</span><span class="sxs-lookup"><span data-stu-id="9de1d-230">Create policy</span></span>

    1. <span data-ttu-id="9de1d-231">Beleid 1: De toegang voor schrijven en uitvoeren blokkeren tot alle niet-goedgekeurde USB's, behalve blokkeren.</span><span class="sxs-lookup"><span data-stu-id="9de1d-231">Policy 1: Block Write and Execute access to all but block specific unapproved USBs.</span></span> <span data-ttu-id="9de1d-232">Een voorbeeld van deze use case is: PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98** in het voorbeeld van Scenario 2 Audit Write and Execute access to all but block specific [unapproved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span><span class="sxs-lookup"><span data-stu-id="9de1d-232">An example of this use case is: PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98** in the sample [Scenario 2 Audit Write and Execute access to all but block specific unapproved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="9de1d-233">Beleid 2: audit schrijf- en uitvoertoegang tot anderen.</span><span class="sxs-lookup"><span data-stu-id="9de1d-233">Policy 2: Audit Write and Execute access to others.</span></span> <span data-ttu-id="9de1d-234">Een voorbeeld van deze use case is: PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48** in het voorbeeld [van Scenario 2 Audit Write and Execute access to others.xmlfile.](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)</span><span class="sxs-lookup"><span data-stu-id="9de1d-234">An example of this use case is: PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48** in the sample [Scenario 2 Audit Write and Execute access to others.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

## <a name="deploying-and-managing-policy-via-group-policy"></a><span data-ttu-id="9de1d-235">Beleid implementeren en beheren via groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="9de1d-235">Deploying and managing policy via Group Policy</span></span>

<span data-ttu-id="9de1d-236">Met de functie Storage Access Control kunt u beleid via groepsbeleid toepassen op gebruiker of apparaat of beide.</span><span class="sxs-lookup"><span data-stu-id="9de1d-236">The Removable Storage Access Control feature enables you to apply policy via Group Policy to either user or device, or both.</span></span>

### <a name="licensing"></a><span data-ttu-id="9de1d-237">Licenties</span><span class="sxs-lookup"><span data-stu-id="9de1d-237">Licensing</span></span>

<span data-ttu-id="9de1d-238">Voordat u aan de slag gaat met Verwisselbaar Storage Access Control, moet u uw Microsoft 365 [bevestigen.](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2)</span><span class="sxs-lookup"><span data-stu-id="9de1d-238">Before you get started with Removable Storage Access Control, you must confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2).</span></span> <span data-ttu-id="9de1d-239">Als u verwisselbare Storage access control wilt openen en gebruiken, moet u Microsoft 365 E3 of Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="9de1d-239">To access and use Removable Storage Access Control, you must have Microsoft 365 E3 or Microsoft 365 E5.</span></span>

### <a name="deploying-policy-via-group-policy"></a><span data-ttu-id="9de1d-240">Beleid implementeren via groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="9de1d-240">Deploying policy via Group Policy</span></span>

1. <span data-ttu-id="9de1d-241">Combineer alle groepen binnen `<Groups>` `</Groups>` in één xml-bestand.</span><span class="sxs-lookup"><span data-stu-id="9de1d-241">Combine all groups within `<Groups>` `</Groups>` into one xml file.</span></span> 

    <span data-ttu-id="9de1d-242">In de volgende afbeelding ziet u het voorbeeld van scenario 1: Geen schrijf- en uitvoertoegang tot alle, maar wel specifieke goedgekeurde [USB's toestaan.](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)</span><span class="sxs-lookup"><span data-stu-id="9de1d-242">The following image illustrates the example of [Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs).</span></span>
    
    :::image type="content" source="images/prevent-write-access-allow-usb.png" alt-text="Het scherm met de configuratie-instellingen waarmee specifieke goedgekeurde USB's op apparaten worden toegestaan":::
    
2. <span data-ttu-id="9de1d-244">Combineer alle regels binnen `<PolicyRules>` `</PolicyRules>` in één xml-bestand.</span><span class="sxs-lookup"><span data-stu-id="9de1d-244">Combine all rules within `<PolicyRules>` `</PolicyRules>` into one xml file.</span></span> 

    <span data-ttu-id="9de1d-245">Als u een specifieke gebruiker wilt beperken, gebruikt u de eigenschap SID in de vermelding.</span><span class="sxs-lookup"><span data-stu-id="9de1d-245">If you want to restrict a specific user, then use SID property into the Entry.</span></span> <span data-ttu-id="9de1d-246">Als er geen SID in de beleidsinvoer staat, wordt de vermelding toegepast op iedereen die zich voor de computer aanmeldt.</span><span class="sxs-lookup"><span data-stu-id="9de1d-246">If there is no SID in the policy Entry, the Entry will be applied to everyone login instance for the machine.</span></span>
    
    <span data-ttu-id="9de1d-247">In de volgende afbeelding ziet u het gebruik van de eigenschap SID en een voorbeeld van scenario 1: Geen schrijf- en uitvoertoegang tot alle, maar toestaan dat specifieke goedgekeurde [USB's worden gebruikt.](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)</span><span class="sxs-lookup"><span data-stu-id="9de1d-247">The following image illustrates the usage of SID property, and an example of [Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs).</span></span>
    
    :::image type="content" source="images/usage-sid-property.png" alt-text="Het scherm met een code die het gebruik van het eigenschapskenmerk SID aangeeft":::

3. <span data-ttu-id="9de1d-249">Sla zowel regel- als groep XML-bestanden op de map Netwerk delen op en plaats het mappad voor netwerk delen in de instelling Groepsbeleid: **Computerconfiguratie -> Beheersjablonen -> Windows Onderdelen -> Microsoft Defender Antivirus -> Apparaatbeheer: 'Beleidsgroepen** apparaatbeheer definiëren' en 'Beleidsregels voor apparaatbeheer definiëren' .</span><span class="sxs-lookup"><span data-stu-id="9de1d-249">Save both rule and group XML files on network share folder and put network share folder path into the Group Policy setting: **Computer Configuration -> Administrative Templates -> Windows Components -> Microsoft Defender Antivirus -> Device Control: ‘Define device control policy groups’ and ‘Define device control policy rules’**.</span></span>

    - <span data-ttu-id="9de1d-250">De doelmachine moet toegang hebben tot het netwerk delen om het beleid te hebben.</span><span class="sxs-lookup"><span data-stu-id="9de1d-250">The target machine must be able to access the network share to have the policy.</span></span> <span data-ttu-id="9de1d-251">Wanneer het beleid echter is gelezen, is de netwerkverbinding niet meer vereist, zelfs niet na het opnieuw opstarten van de computer.</span><span class="sxs-lookup"><span data-stu-id="9de1d-251">However, once the policy is read, the network share connection is no longer required, even after machine reboot.</span></span>

    :::image type="content" source="images/device-control.png" alt-text="Het scherm Apparaatbesturingselement":::

## <a name="deploying-and-managing-policy-via-intune-oma-uri"></a><span data-ttu-id="9de1d-253">Beleid implementeren en beheren via Intune OMA-URI</span><span class="sxs-lookup"><span data-stu-id="9de1d-253">Deploying and managing policy via Intune OMA-URI</span></span>

<span data-ttu-id="9de1d-254">Met de functie Verwisselbaar Storage Access Control kunt u beleid via OMA-URI toepassen op een gebruiker of apparaat of beide.</span><span class="sxs-lookup"><span data-stu-id="9de1d-254">The Removable Storage Access Control feature enables you to apply policy via OMA-URI to either user or device, or both.</span></span>

### <a name="licensing"></a><span data-ttu-id="9de1d-255">Licenties</span><span class="sxs-lookup"><span data-stu-id="9de1d-255">Licensing</span></span>

<span data-ttu-id="9de1d-256">Voordat u aan de slag gaat met Verwisselbaar Storage Access Control, moet u uw Microsoft 365 [bevestigen.](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2)</span><span class="sxs-lookup"><span data-stu-id="9de1d-256">Before you get started with Removable Storage Access Control, you  must confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2).</span></span> <span data-ttu-id="9de1d-257">Als u verwisselbare Storage access control wilt openen en gebruiken, moet u Microsoft 365 E3 of Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="9de1d-257">To access and use Removable Storage Access Control, you must have Microsoft 365 E3 or Microsoft 365 E5.</span></span>

### <a name="permission"></a><span data-ttu-id="9de1d-258">Machtiging</span><span class="sxs-lookup"><span data-stu-id="9de1d-258">Permission</span></span>

<span data-ttu-id="9de1d-259">Voor beleidsimplementatie in Intune moet het account machtigingen hebben voor het maken, bewerken, bijwerken of verwijderen van apparaatconfiguratieprofielen.</span><span class="sxs-lookup"><span data-stu-id="9de1d-259">For policy deployment in Intune, the account must have permissions to create, edit, update, or delete device configuration profiles.</span></span> <span data-ttu-id="9de1d-260">U kunt aangepaste rollen maken of een van de ingebouwde rollen met deze machtigingen gebruiken.</span><span class="sxs-lookup"><span data-stu-id="9de1d-260">You can create custom roles or use any of the built-in roles with these permissions.</span></span>

- <span data-ttu-id="9de1d-261">Rol beleids- en profielmanager</span><span class="sxs-lookup"><span data-stu-id="9de1d-261">Policy and profile Manager role</span></span>
- <span data-ttu-id="9de1d-262">Aangepaste rol met machtigingen maken/bewerken/bijwerken/lezen/verwijderen/rapporten weergeven ingeschakeld voor apparaatconfiguratieprofielen</span><span class="sxs-lookup"><span data-stu-id="9de1d-262">Custom role with Create/Edit/Update/Read/Delete/View Reports permissions turned on for Device Configuration profiles</span></span>
- <span data-ttu-id="9de1d-263">Globale beheerder</span><span class="sxs-lookup"><span data-stu-id="9de1d-263">Global administrator</span></span>

### <a name="deploying-policy-via-oma-uri"></a><span data-ttu-id="9de1d-264">Beleid implementeren via OMA-URI</span><span class="sxs-lookup"><span data-stu-id="9de1d-264">Deploying policy via OMA-URI</span></span>

<span data-ttu-id="9de1d-265">**Microsoft Endpoint Manager https://endpoint.microsoft.com/) -beheercentrum ( -> Apparaten -> Configuratieprofielen -> Profiel maken -> Platform: Windows 10 en hoger & Profiel: Aangepast**</span><span class="sxs-lookup"><span data-stu-id="9de1d-265">**Microsoft Endpoint Manager admin center (https://endpoint.microsoft.com/) -> Devices -> Configuration profiles -> Create profile -> Platform: Windows 10 and later & Profile: Custom**</span></span>

1. <span data-ttu-id="9de1d-266">Maak voor elke groep een OMA-URI-regel:</span><span class="sxs-lookup"><span data-stu-id="9de1d-266">For each Group, create an OMA-URI rule:</span></span>
    - <span data-ttu-id="9de1d-267">OMA-URI: </span><span class="sxs-lookup"><span data-stu-id="9de1d-267">OMA-URI:</span></span>

      <span data-ttu-id="9de1d-268">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b **GroupGUID**%7d/GroupData</span><span class="sxs-lookup"><span data-stu-id="9de1d-268">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b **GroupGUID**%7d/GroupData</span></span>

      <span data-ttu-id="9de1d-269">Voor een **verwisselbare opslag- en cd/dvd-groep** in het voorbeeld moet de koppeling bijvoorbeeld zijn:</span><span class="sxs-lookup"><span data-stu-id="9de1d-269">For example, for **any removable storage and CD/DVD** group in the sample, the link must be:</span></span>

      <span data-ttu-id="9de1d-270">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData</span><span class="sxs-lookup"><span data-stu-id="9de1d-270">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData</span></span>

    - <span data-ttu-id="9de1d-271">Gegevenstype: tekenreeks (XML-bestand)</span><span class="sxs-lookup"><span data-stu-id="9de1d-271">Data Type: String (XML file)</span></span>
    
      :::image type="content" source="images/xml-data-type-string.png" alt-text="Het xml-bestand voor het gegevenstype TEKENREEKS":::

2. <span data-ttu-id="9de1d-273">Maak voor elk beleid ook een OMA-URI:</span><span class="sxs-lookup"><span data-stu-id="9de1d-273">For each policy, also create an OMA-URI:</span></span>

    - <span data-ttu-id="9de1d-274">OMA-URI: </span><span class="sxs-lookup"><span data-stu-id="9de1d-274">OMA-URI:</span></span>

      <span data-ttu-id="9de1d-275">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bFA6BE102-0784-4A2A-B010-A0BEBEBF68E1%7d/RuleData</span><span class="sxs-lookup"><span data-stu-id="9de1d-275">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bFA6BE102-0784-4A2A-B010-A0BEBEBF68E1%7d/RuleData</span></span>

      <span data-ttu-id="9de1d-276">Voor de regel Blokschrijven en Access uitvoeren, maar goedgekeurde **USB's** toestaan in het voorbeeld, moet de koppeling bijvoorbeeld zijn:</span><span class="sxs-lookup"><span data-stu-id="9de1d-276">For example, for the **Block Write and Execute Access but allow approved USBs** rule in the sample, the link must be:</span></span> 

      <span data-ttu-id="9de1d-277">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData.</span><span class="sxs-lookup"><span data-stu-id="9de1d-277">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData.</span></span>

    - <span data-ttu-id="9de1d-278">Gegevenstype: tekenreeks (XML-bestand)</span><span class="sxs-lookup"><span data-stu-id="9de1d-278">Data Type: String (XML file)</span></span>

      :::image type="content" source="images/xml-data-type-string-2.png" lightbox="images/xml-data-type-string-2.png" alt-text="Weergave van XML-bestand voor het gegevenstype TEKENREEKS":::

## <a name="deploying-and-managing-policy-by-using-intune-user-interface"></a><span data-ttu-id="9de1d-280">Beleid implementeren en beheren met intune-gebruikersinterface</span><span class="sxs-lookup"><span data-stu-id="9de1d-280">Deploying and managing policy by using Intune user interface</span></span>

<span data-ttu-id="9de1d-281">Deze mogelijkheid (in Microsoft Endpoint Manager-beheercentrum (> Apparaten > Configuratieprofielen > Profiel > Platform maken: Windows 10 en https://endpoint.microsoft.com/) hoger & Profiel: Apparaatbesturingselement) is nog niet beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="9de1d-281">This capability (in Microsoft Endpoint Manager admin center (https://endpoint.microsoft.com/) > Devices > Configuration profiles > Create profile > Platform: Windows 10 and later & Profile: Device Control) is not yet available.</span></span> 

## <a name="view-device-control-removable-storage-access-control-data-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="9de1d-282">Verwisselbare apparaatbesturingselementen Storage Access Control-gegevens weergeven in Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="9de1d-282">View Device Control Removable Storage Access Control data in Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="9de1d-283">De Microsoft 365 beveiligingsportal toont verwisselbare opslag die is geblokkeerd door het verwisselbare apparaatbesturingselement Storage Access Control.</span><span class="sxs-lookup"><span data-stu-id="9de1d-283">The Microsoft 365 security portal shows removable storage blocked by the Device Control Removable Storage Access Control.</span></span> <span data-ttu-id="9de1d-284">Als u toegang wilt tot Microsoft 365 beveiliging, moet u het volgende abonnement hebben:</span><span class="sxs-lookup"><span data-stu-id="9de1d-284">To access the Microsoft 365 security, you must have the following subscription:</span></span>

- <span data-ttu-id="9de1d-285">Microsoft 365 voor E5-rapportage</span><span class="sxs-lookup"><span data-stu-id="9de1d-285">Microsoft 365 for E5 reporting</span></span>

```kusto
//events triggered by RemovableStoragePolicyTriggered
DeviceEvents
| where ActionType == &quot;RemovableStoragePolicyTriggered&quot; 
| extend parsed=parse_json(AdditionalFields) 
| extend RemovableStorageAccess = tostring(parsed.RemovableStorageAccess)  
| extend RemovableStoragePolicyVerdict = tostring(parsed.RemovableStoragePolicyVerdict)  
| extend MediaBusType = tostring(parsed.BusType)  
| extend MediaClassGuid = tostring(parsed.ClassGuid)
| extend MediaClassName = tostring(parsed.ClassName)
| extend MediaDeviceId = tostring(parsed.DeviceId) 
| extend MediaInstanceId = tostring(parsed.DeviceInstanceId) 
| extend MediaName = tostring(parsed.MediaName) 
| extend RemovableStoragePolicy = tostring(parsed.RemovableStoragePolicy)  
| extend MediaProductId = tostring(parsed.ProductId)  
| extend MediaVendorId = tostring(parsed.VendorId)  
| extend MediaSerialNumber = tostring(parsed.SerialNumber)  
| extend MediaVolume = tostring(parsed.Volume)  
| project Timestamp, DeviceId, DeviceName, ActionType, RemovableStorageAccess, RemovableStoragePolicyVerdict, MediaBusType, MediaClassGuid, MediaClassName, MediaDeviceId, MediaInstanceId, MediaName, RemovableStoragePolicy, MediaProductId, MediaVendorId, MediaSerialNumber, MediaVolume 
| order by Timestamp desc
```

:::image type="content" source="images/block-removable-storage.png" alt-text="Het scherm met de blokkering van de verwisselbare opslag":::

## <a name="frequently-asked-questions"></a><span data-ttu-id="9de1d-287">Veelgestelde vragen</span><span class="sxs-lookup"><span data-stu-id="9de1d-287">Frequently asked questions</span></span>
<span data-ttu-id="9de1d-288">**Wat is de beperking van verwisselbare opslagmedia voor het maximum aantal USB's?**</span><span class="sxs-lookup"><span data-stu-id="9de1d-288">**What is the removable storage media limitation for the maximum number of USBs?**</span></span>

<span data-ttu-id="9de1d-289">We hebben één USB-groep gevalideerd met 100.000 media- tot 7 MB groot.</span><span class="sxs-lookup"><span data-stu-id="9de1d-289">We have validated one USB group with 100,000 media - up to 7 MB in size.</span></span> <span data-ttu-id="9de1d-290">Het beleid werkt in zowel Intune als GPO zonder prestatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="9de1d-290">The policy works in both Intune and GPO without performance issues.</span></span>

<span data-ttu-id="9de1d-291">**Waarom werkt het beleid niet?**</span><span class="sxs-lookup"><span data-stu-id="9de1d-291">**Why does the policy not work?**</span></span>

<span data-ttu-id="9de1d-292">De meest voorkomende reden is dat er geen [vereiste antimalwareclientversie is.](/microsoft-365/security/defender-endpoint/device-control-removable-storage-access-control#prepare-your-endpoints)</span><span class="sxs-lookup"><span data-stu-id="9de1d-292">The most common reason is there is no required [antimalware client version](/microsoft-365/security/defender-endpoint/device-control-removable-storage-access-control#prepare-your-endpoints).</span></span>

<span data-ttu-id="9de1d-293">Een andere reden kan zijn dat het XML-bestand niet correct is opgemaakt, bijvoorbeeld door de juiste markeringsopmaak voor het teken '&' in het XML-bestand niet te gebruiken, of dat de teksteditor een byteorderteken (BOM) 0xEF 0xBB 0xBF aan het begin van de bestanden toevoegt, waardoor de XML-parsing niet werkt.</span><span class="sxs-lookup"><span data-stu-id="9de1d-293">Another reason could be that the XML file is not correctly formatted, for example, not using the correct markdown formatting for the "&" character in the XML file, or the text editor might add a byte order mark (BOM) 0xEF 0xBB 0xBF at the beginning of the files which causes the XML parsing not to work.</span></span> <span data-ttu-id="9de1d-294">Een eenvoudige oplossing is om het voorbeeldbestand [te downloaden](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) (selecteer **Raw** en vervolgens **Opslaan als)** en vervolgens bij te werken.</span><span class="sxs-lookup"><span data-stu-id="9de1d-294">One simple solution is to download the [sample file](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) (select **Raw** and then **Save as**) and then update.</span></span>

<span data-ttu-id="9de1d-295">Als er een waarde is en het beleid wordt beheerd via groepsbeleid, controleert u of het clientapparaat toegang heeft tot het XML-pad voor beleid.</span><span class="sxs-lookup"><span data-stu-id="9de1d-295">If there is a value and the policy is managed via Group Policy, check whether the client device can access the policy XML path.</span></span>

<span data-ttu-id="9de1d-296">**Hoe weet ik welke computer een verouderd antimalware-clientversie in de organisatie gebruikt?**</span><span class="sxs-lookup"><span data-stu-id="9de1d-296">**How can I know which machine is using out of date antimalware client version in the organization?**</span></span>

<span data-ttu-id="9de1d-297">U kunt volgende query gebruiken om de versie van de antimalwareclient op te halen in Microsoft 365 beveiligingsportal:</span><span class="sxs-lookup"><span data-stu-id="9de1d-297">You can use following query to get antimalware client version on the Microsoft 365 security portal:</span></span>
```kusto
//check the antimalware client version
DeviceFileEvents
| where FileName == "MsMpEng.exe"
| where FolderPath contains @"C:\ProgramData\Microsoft\Windows Defender\Platform\"
| extend PlatformVersion=tostring(split(FolderPath, "\\", 5))
//| project DeviceName, PlatformVersion // check which machine is using legacy platformVersion
| summarize dcount(DeviceName) by PlatformVersion // check how many machines are using which platformVersion
| order by PlatformVersion desc
```

