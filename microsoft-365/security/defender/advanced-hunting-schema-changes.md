---
title: Naamgevingswijzigingen in het geavanceerde schema voor de microsoft 365 Defender-jacht
description: Naamgevingswijzigingen bijhouden en controleren tabellen en kolommen in het geavanceerde schema voor de jacht
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, data, naming changes, rename, Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: acb259088717b2772ec9798027545f2ff6dbc5e0
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060597"
---
# <a name="advanced-hunting-schema---naming-changes"></a><span data-ttu-id="9a206-104">Geavanceerd schema voor de jacht - Naamgevingswijzigingen</span><span class="sxs-lookup"><span data-stu-id="9a206-104">Advanced hunting schema - Naming changes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="9a206-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="9a206-105">**Applies to:**</span></span>
- <span data-ttu-id="9a206-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9a206-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="9a206-107">Het [geavanceerde schema wordt](advanced-hunting-schema-tables.md) regelmatig bijgewerkt om nieuwe tabellen en kolommen toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="9a206-107">The [advanced hunting schema](advanced-hunting-schema-tables.md) is updated regularly to add new tables and columns.</span></span> <span data-ttu-id="9a206-108">In sommige gevallen worden bestaande kolommennamen hernoemd of vervangen om de gebruikerservaring te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="9a206-108">In some cases, existing columns names are renamed or replaced to improve the user experience.</span></span> <span data-ttu-id="9a206-109">Raadpleeg dit artikel om naamgevingswijzigingen te bekijken die van invloed kunnen zijn op uw query's.</span><span class="sxs-lookup"><span data-stu-id="9a206-109">Refer to this article to review naming changes that could impact your queries.</span></span>

<span data-ttu-id="9a206-110">Naamgevingswijzigingen worden automatisch toegepast op query's die zijn opgeslagen in het beveiligingscentrum, inclusief query's die worden gebruikt door aangepaste detectieregels.</span><span class="sxs-lookup"><span data-stu-id="9a206-110">Naming changes are automatically applied to queries that are saved in the security center, including queries used by custom detection rules.</span></span> <span data-ttu-id="9a206-111">U hoeft deze query's niet handmatig bij te werken.</span><span class="sxs-lookup"><span data-stu-id="9a206-111">You don't need to update these queries manually.</span></span> <span data-ttu-id="9a206-112">U moet echter de volgende query's bijwerken:</span><span class="sxs-lookup"><span data-stu-id="9a206-112">However, you will need to update the following queries:</span></span>
- <span data-ttu-id="9a206-113">Query's die worden uitgevoerd met de API</span><span class="sxs-lookup"><span data-stu-id="9a206-113">Queries that are run using the API</span></span>
- <span data-ttu-id="9a206-114">Query's die ergens anders buiten het beveiligingscentrum worden opgeslagen</span><span class="sxs-lookup"><span data-stu-id="9a206-114">Queries that are saved elsewhere outside the security center</span></span>

## <a name="december-2020"></a><span data-ttu-id="9a206-115">December 2020</span><span class="sxs-lookup"><span data-stu-id="9a206-115">December 2020</span></span>

| <span data-ttu-id="9a206-116">Tabelnaam</span><span class="sxs-lookup"><span data-stu-id="9a206-116">Table name</span></span> | <span data-ttu-id="9a206-117">Oorspronkelijke kolomnaam</span><span class="sxs-lookup"><span data-stu-id="9a206-117">Original column name</span></span> | <span data-ttu-id="9a206-118">Nieuwe kolomnaam</span><span class="sxs-lookup"><span data-stu-id="9a206-118">New column name</span></span> | <span data-ttu-id="9a206-119">Reden voor wijziging</span><span class="sxs-lookup"><span data-stu-id="9a206-119">Reason for change</span></span>
|--|--|--|--|
| [<span data-ttu-id="9a206-120">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="9a206-120">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailAction` | `EmailAction` | <span data-ttu-id="9a206-121">Feedback van klanten</span><span class="sxs-lookup"><span data-stu-id="9a206-121">Customer feedback</span></span> |
| [<span data-ttu-id="9a206-122">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="9a206-122">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicy` | `EmailActionPolicy` | <span data-ttu-id="9a206-123">Feedback van klanten</span><span class="sxs-lookup"><span data-stu-id="9a206-123">Customer feedback</span></span> |
| [<span data-ttu-id="9a206-124">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="9a206-124">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicyGuid` | `EmailActionPolicyGuid` | <span data-ttu-id="9a206-125">Feedback van klanten</span><span class="sxs-lookup"><span data-stu-id="9a206-125">Customer feedback</span></span> |

## <a name="january-2021"></a><span data-ttu-id="9a206-126">Januari 2021</span><span class="sxs-lookup"><span data-stu-id="9a206-126">January 2021</span></span>

| <span data-ttu-id="9a206-127">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="9a206-127">Column name</span></span> | <span data-ttu-id="9a206-128">Oorspronkelijke waardenaam</span><span class="sxs-lookup"><span data-stu-id="9a206-128">Original value name</span></span> | <span data-ttu-id="9a206-129">Nieuwe waardenaam</span><span class="sxs-lookup"><span data-stu-id="9a206-129">New value name</span></span> | <span data-ttu-id="9a206-130">Reden voor wijziging</span><span class="sxs-lookup"><span data-stu-id="9a206-130">Reason for change</span></span>
|--|--|--|--|
| `DetectionSource` | <span data-ttu-id="9a206-131">MCAS</span><span class="sxs-lookup"><span data-stu-id="9a206-131">MCAS</span></span> |    <span data-ttu-id="9a206-132">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="9a206-132">Microsoft Cloud App Security</span></span> | <span data-ttu-id="9a206-133">Rebranding</span><span class="sxs-lookup"><span data-stu-id="9a206-133">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="9a206-134">WindowsDefenderAtp</span><span class="sxs-lookup"><span data-stu-id="9a206-134">WindowsDefenderAtp</span></span>|   <span data-ttu-id="9a206-135">EDR</span><span class="sxs-lookup"><span data-stu-id="9a206-135">EDR</span></span>| <span data-ttu-id="9a206-136">Rebranding</span><span class="sxs-lookup"><span data-stu-id="9a206-136">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="9a206-137">WindowsDefenderAv</span><span class="sxs-lookup"><span data-stu-id="9a206-137">WindowsDefenderAv</span></span> | <span data-ttu-id="9a206-138">Antivirus</span><span class="sxs-lookup"><span data-stu-id="9a206-138">Antivirus</span></span> | <span data-ttu-id="9a206-139">Rebranding</span><span class="sxs-lookup"><span data-stu-id="9a206-139">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="9a206-140">WindowsDefenderSmartScreen</span><span class="sxs-lookup"><span data-stu-id="9a206-140">WindowsDefenderSmartScreen</span></span> |  <span data-ttu-id="9a206-141">SmartScreen</span><span class="sxs-lookup"><span data-stu-id="9a206-141">SmartScreen</span></span> | <span data-ttu-id="9a206-142">Rebranding</span><span class="sxs-lookup"><span data-stu-id="9a206-142">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="9a206-143">CustomerTI</span><span class="sxs-lookup"><span data-stu-id="9a206-143">CustomerTI</span></span> |  <span data-ttu-id="9a206-144">Aangepaste TI</span><span class="sxs-lookup"><span data-stu-id="9a206-144">Custom TI</span></span> | <span data-ttu-id="9a206-145">Rebranding</span><span class="sxs-lookup"><span data-stu-id="9a206-145">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="9a206-146">OfficeATP</span><span class="sxs-lookup"><span data-stu-id="9a206-146">OfficeATP</span></span> | <span data-ttu-id="9a206-147">Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="9a206-147">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="9a206-148">Rebranding</span><span class="sxs-lookup"><span data-stu-id="9a206-148">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="9a206-149">MTP</span><span class="sxs-lookup"><span data-stu-id="9a206-149">MTP</span></span>   | <span data-ttu-id="9a206-150">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9a206-150">Microsoft 365 Defender</span></span> | <span data-ttu-id="9a206-151">Rebranding</span><span class="sxs-lookup"><span data-stu-id="9a206-151">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="9a206-152">AzureATP</span><span class="sxs-lookup"><span data-stu-id="9a206-152">AzureATP</span></span> |    <span data-ttu-id="9a206-153">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="9a206-153">Microsoft Defender for Identity</span></span> | <span data-ttu-id="9a206-154">Rebranding</span><span class="sxs-lookup"><span data-stu-id="9a206-154">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="9a206-155">CustomDetection</span><span class="sxs-lookup"><span data-stu-id="9a206-155">CustomDetection</span></span>   | <span data-ttu-id="9a206-156">Aangepaste detectie</span><span class="sxs-lookup"><span data-stu-id="9a206-156">Custom detection</span></span> | <span data-ttu-id="9a206-157">Rebranding</span><span class="sxs-lookup"><span data-stu-id="9a206-157">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="9a206-158">AutomatedInvestigation</span><span class="sxs-lookup"><span data-stu-id="9a206-158">AutomatedInvestigation</span></span> |<span data-ttu-id="9a206-159">Geautomatiseerd onderzoek</span><span class="sxs-lookup"><span data-stu-id="9a206-159">Automated investigation</span></span> | <span data-ttu-id="9a206-160">Rebranding</span><span class="sxs-lookup"><span data-stu-id="9a206-160">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="9a206-161">ThreatExperts</span><span class="sxs-lookup"><span data-stu-id="9a206-161">ThreatExperts</span></span> | <span data-ttu-id="9a206-162">Microsoft Threat Experts</span><span class="sxs-lookup"><span data-stu-id="9a206-162">Microsoft Threat Experts</span></span> | <span data-ttu-id="9a206-163">Rebranding</span><span class="sxs-lookup"><span data-stu-id="9a206-163">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="9a206-164">TI van derden</span><span class="sxs-lookup"><span data-stu-id="9a206-164">3rd party TI</span></span> | <span data-ttu-id="9a206-165">Sensoren van derden</span><span class="sxs-lookup"><span data-stu-id="9a206-165">3rd Party sensors</span></span> | <span data-ttu-id="9a206-166">Rebranding</span><span class="sxs-lookup"><span data-stu-id="9a206-166">Rebranding</span></span> |
| `ServiceSource` | <span data-ttu-id="9a206-167">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="9a206-167">Microsoft Defender ATP</span></span>| <span data-ttu-id="9a206-168">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="9a206-168">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="9a206-169">Rebranding</span><span class="sxs-lookup"><span data-stu-id="9a206-169">Rebranding</span></span> |
|`ServiceSource` |<span data-ttu-id="9a206-170">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="9a206-170">Microsoft Threat Protection</span></span>   | <span data-ttu-id="9a206-171">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9a206-171">Microsoft 365 Defender</span></span> | <span data-ttu-id="9a206-172">Rebranding</span><span class="sxs-lookup"><span data-stu-id="9a206-172">Rebranding</span></span> |
| `ServiceSource` | <span data-ttu-id="9a206-173">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="9a206-173">Office 365 ATP</span></span>  |<span data-ttu-id="9a206-174">Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="9a206-174">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="9a206-175">Rebranding</span><span class="sxs-lookup"><span data-stu-id="9a206-175">Rebranding</span></span> |
| `ServiceSource` |<span data-ttu-id="9a206-176">Azure ATP</span><span class="sxs-lookup"><span data-stu-id="9a206-176">Azure ATP</span></span>    |<span data-ttu-id="9a206-177">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="9a206-177">Microsoft Defender for Identity</span></span> | <span data-ttu-id="9a206-178">Rebranding</span><span class="sxs-lookup"><span data-stu-id="9a206-178">Rebranding</span></span> |

<span data-ttu-id="9a206-179">`DetectionSource`is beschikbaar in de [tabel AlertInfo.](advanced-hunting-alertinfo-table.md)</span><span class="sxs-lookup"><span data-stu-id="9a206-179">`DetectionSource` is available in the [AlertInfo](advanced-hunting-alertinfo-table.md) table.</span></span> <span data-ttu-id="9a206-180">`ServiceSource`is beschikbaar in de [tabellen AlertEvidence](advanced-hunting-alertevidence-table.md) en [AlertInfo.](advanced-hunting-alertinfo-table.md)</span><span class="sxs-lookup"><span data-stu-id="9a206-180">`ServiceSource` is available in the [AlertEvidence](advanced-hunting-alertevidence-table.md) and [AlertInfo](advanced-hunting-alertinfo-table.md) tables.</span></span> 

## <a name="february-2021"></a><span data-ttu-id="9a206-181">Februari 2021</span><span class="sxs-lookup"><span data-stu-id="9a206-181">February 2021</span></span>

1. <span data-ttu-id="9a206-182">In de [tabellen EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) en [EmailEvents](advanced-hunting-emailevents-table.md) zijn de kolommen vervangen `MalwareFilterVerdict` door de `PhishFilterVerdict` `ThreatTypes` kolom.</span><span class="sxs-lookup"><span data-stu-id="9a206-182">In the [EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) and [EmailEvents](advanced-hunting-emailevents-table.md) tables, the `MalwareFilterVerdict`and `PhishFilterVerdict` columns have been replaced by the `ThreatTypes` column.</span></span> <span data-ttu-id="9a206-183">De `MalwareDetectionMethod` kolommen en kolommen zijn ook vervangen door de `PhishDetectionMethod` `DetectionMethods` kolom.</span><span class="sxs-lookup"><span data-stu-id="9a206-183">The `MalwareDetectionMethod` and `PhishDetectionMethod` columns were also replaced by the `DetectionMethods` column.</span></span> <span data-ttu-id="9a206-184">Met deze stroomlijning kunnen we meer informatie geven onder de nieuwe kolommen.</span><span class="sxs-lookup"><span data-stu-id="9a206-184">This streamlining allows us to provide more information under the new columns.</span></span> <span data-ttu-id="9a206-185">De toewijzing vindt u hieronder.</span><span class="sxs-lookup"><span data-stu-id="9a206-185">The mapping is provided below.</span></span>

| <span data-ttu-id="9a206-186">Tabelnaam</span><span class="sxs-lookup"><span data-stu-id="9a206-186">Table name</span></span> | <span data-ttu-id="9a206-187">Oorspronkelijke kolomnaam</span><span class="sxs-lookup"><span data-stu-id="9a206-187">Original column name</span></span> | <span data-ttu-id="9a206-188">Nieuwe kolomnaam</span><span class="sxs-lookup"><span data-stu-id="9a206-188">New column name</span></span> | <span data-ttu-id="9a206-189">Reden voor wijziging</span><span class="sxs-lookup"><span data-stu-id="9a206-189">Reason for change</span></span>
|--|--|--|--|
| `EmailAttachmentInfo` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | <span data-ttu-id="9a206-190">Meer detectiemethoden opnemen</span><span class="sxs-lookup"><span data-stu-id="9a206-190">Include more detection methods</span></span> |
| `EmailAttachmentInfo`  | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | <span data-ttu-id="9a206-191">Meer bedreigingstypen opnemen</span><span class="sxs-lookup"><span data-stu-id="9a206-191">Include more threat types</span></span> |
| `EmailEvents` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | <span data-ttu-id="9a206-192">Meer detectiemethoden opnemen</span><span class="sxs-lookup"><span data-stu-id="9a206-192">Include more detection methods</span></span> |
| `EmailEvents` | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | <span data-ttu-id="9a206-193">Meer bedreigingstypen opnemen</span><span class="sxs-lookup"><span data-stu-id="9a206-193">Include more threat types</span></span> |


2. <span data-ttu-id="9a206-194">In de tabellen en tabellen is de kolom toegevoegd om meer informatie over de e-maildreiging `EmailAttachmentInfo` `EmailEvents` te `ThreatNames` geven.</span><span class="sxs-lookup"><span data-stu-id="9a206-194">In the `EmailAttachmentInfo` and `EmailEvents` tables, the `ThreatNames` column was added to give more information about the email threat.</span></span> <span data-ttu-id="9a206-195">Deze kolom bevat waarden zoals Spam of Phish.</span><span class="sxs-lookup"><span data-stu-id="9a206-195">This column contains values like Spam or Phish.</span></span>

3. <span data-ttu-id="9a206-196">In de [tabel DeviceInfo](advanced-hunting-deviceinfo-table.md) is de `DeviceObjectId` kolom vervangen door de kolom op basis van feedback van `AadDeviceId` klanten.</span><span class="sxs-lookup"><span data-stu-id="9a206-196">In the [DeviceInfo](advanced-hunting-deviceinfo-table.md) table, the `DeviceObjectId` column was replaced by the `AadDeviceId` column based on customer feedback.</span></span>

4. <span data-ttu-id="9a206-197">In de [tabel DeviceEvents](advanced-hunting-deviceevents-table.md) zijn verschillende ActionType-namen gewijzigd om de beschrijving van de actie beter weer te geven.</span><span class="sxs-lookup"><span data-stu-id="9a206-197">In the [DeviceEvents](advanced-hunting-deviceevents-table.md) table, several ActionType names were modified to better reflect the description of the action.</span></span> <span data-ttu-id="9a206-198">Details van de wijzigingen vindt u hieronder.</span><span class="sxs-lookup"><span data-stu-id="9a206-198">Details of the changes can be found below.</span></span>

| <span data-ttu-id="9a206-199">Tabelnaam</span><span class="sxs-lookup"><span data-stu-id="9a206-199">Table name</span></span> | <span data-ttu-id="9a206-200">Oorspronkelijke naam ActionType</span><span class="sxs-lookup"><span data-stu-id="9a206-200">Original ActionType name</span></span> | <span data-ttu-id="9a206-201">Nieuwe naam ActionType</span><span class="sxs-lookup"><span data-stu-id="9a206-201">New ActionType name</span></span> | <span data-ttu-id="9a206-202">Reden voor wijziging</span><span class="sxs-lookup"><span data-stu-id="9a206-202">Reason for change</span></span>
|--|--|--|--|
| `DeviceEvents` | `DlpPocPrintJob` | `FilePrinted` | <span data-ttu-id="9a206-203">Feedback van klanten</span><span class="sxs-lookup"><span data-stu-id="9a206-203">Customer feedback</span></span> |
| `DeviceEvents` | `UsbDriveMount` | `UsbDriveMounted` | <span data-ttu-id="9a206-204">Feedback van klanten</span><span class="sxs-lookup"><span data-stu-id="9a206-204">Customer feedback</span></span> |
| `DeviceEvents` | `UsbDriveUnmount` | `UsbDriveUnmounted` | <span data-ttu-id="9a206-205">Feedback van klanten</span><span class="sxs-lookup"><span data-stu-id="9a206-205">Customer feedback</span></span> |
| `DeviceEvents` | `WriteProcessMemoryApiCall` | `WriteToLsassProcessMemory` | <span data-ttu-id="9a206-206">Feedback van klanten</span><span class="sxs-lookup"><span data-stu-id="9a206-206">Customer feedback</span></span> |






## <a name="related-topics"></a><span data-ttu-id="9a206-207">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="9a206-207">Related topics</span></span>
- [<span data-ttu-id="9a206-208">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="9a206-208">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="9a206-209">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="9a206-209">Understand the schema</span></span>](advanced-hunting-schema-tables.md)