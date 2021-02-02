---
title: Naamgevingswijzigingen in het geavanceerde schema van Microsoft 365 Defender voor zoeken
description: Wijzigingen in tabellen en kolommen in het geavanceerde schema voor zoeken bijhouden en bekijken
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 3f03543b03dca5fe426700ffff4f5c6edb8fa3c7
ms.sourcegitcommit: c550c1b5b9e67398fd95bfb0256c4f5c7930b2be
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/01/2021
ms.locfileid: "50066867"
---
# <a name="advanced-hunting-schema---naming-changes"></a><span data-ttu-id="008e2-104">Geavanceerd schema voor zoeken - naamwijzigingen</span><span class="sxs-lookup"><span data-stu-id="008e2-104">Advanced hunting schema - Naming changes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="008e2-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="008e2-105">**Applies to:**</span></span>
- <span data-ttu-id="008e2-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="008e2-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="008e2-107">Het [geavanceerde schema voor zoeken](advanced-hunting-schema-tables.md) wordt regelmatig bijgewerkt om nieuwe tabellen en kolommen toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="008e2-107">The [advanced hunting schema](advanced-hunting-schema-tables.md) is updated regularly to add new tables and columns.</span></span> <span data-ttu-id="008e2-108">In sommige gevallen worden bestaande kolomnamen gewijzigd of vervangen om de gebruikerservaring te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="008e2-108">In some cases, existing columns names are renamed or replaced to improve the user experience.</span></span> <span data-ttu-id="008e2-109">Raadpleeg dit artikel voor meer informatie over naamgevingswijzigingen die van invloed kunnen zijn op uw query's.</span><span class="sxs-lookup"><span data-stu-id="008e2-109">Refer to this article to review naming changes that could impact your queries.</span></span>

<span data-ttu-id="008e2-110">Naamwijzigingen worden automatisch toegepast op query's die worden opgeslagen in het beveiligingscentrum, inclusief query's die door aangepaste detectieregels worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="008e2-110">Naming changes are automatically applied to queries that are saved in the security center, including queries used by custom detection rules.</span></span> <span data-ttu-id="008e2-111">U hoeft deze query's niet handmatig bij te werken.</span><span class="sxs-lookup"><span data-stu-id="008e2-111">You don't need to update these queries manually.</span></span> <span data-ttu-id="008e2-112">U moet echter de volgende query's bijwerken:</span><span class="sxs-lookup"><span data-stu-id="008e2-112">However, you will need to update the following queries:</span></span>
- <span data-ttu-id="008e2-113">Query's die worden uitgevoerd met de API</span><span class="sxs-lookup"><span data-stu-id="008e2-113">Queries that are run using the API</span></span>
- <span data-ttu-id="008e2-114">Query's die ergens anders buiten het beveiligingscentrum worden opgeslagen</span><span class="sxs-lookup"><span data-stu-id="008e2-114">Queries that are saved elsewhere outside the security center</span></span>

## <a name="december-2020"></a><span data-ttu-id="008e2-115">December 2020</span><span class="sxs-lookup"><span data-stu-id="008e2-115">December 2020</span></span>

| <span data-ttu-id="008e2-116">Tabelnaam</span><span class="sxs-lookup"><span data-stu-id="008e2-116">Table name</span></span> | <span data-ttu-id="008e2-117">Oorspronkelijke kolomnaam</span><span class="sxs-lookup"><span data-stu-id="008e2-117">Original column name</span></span> | <span data-ttu-id="008e2-118">Nieuwe kolomnaam</span><span class="sxs-lookup"><span data-stu-id="008e2-118">New column name</span></span> | <span data-ttu-id="008e2-119">Reden voor wijziging</span><span class="sxs-lookup"><span data-stu-id="008e2-119">Reason for change</span></span>
|--|--|--|--|
| [<span data-ttu-id="008e2-120">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="008e2-120">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailAction` | `EmailAction` | <span data-ttu-id="008e2-121">Feedback van klanten</span><span class="sxs-lookup"><span data-stu-id="008e2-121">Customer feedback</span></span> |
| [<span data-ttu-id="008e2-122">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="008e2-122">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicy` | `EmailActionPolicy` | <span data-ttu-id="008e2-123">Feedback van klanten</span><span class="sxs-lookup"><span data-stu-id="008e2-123">Customer feedback</span></span> |
| [<span data-ttu-id="008e2-124">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="008e2-124">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicyGuid` | `EmailActionPolicyGuid` | <span data-ttu-id="008e2-125">Feedback van klanten</span><span class="sxs-lookup"><span data-stu-id="008e2-125">Customer feedback</span></span> |

## <a name="january-2021"></a><span data-ttu-id="008e2-126">Januari 2021</span><span class="sxs-lookup"><span data-stu-id="008e2-126">January 2021</span></span>

| <span data-ttu-id="008e2-127">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="008e2-127">Column name</span></span> | <span data-ttu-id="008e2-128">Oorspronkelijke waardenaam</span><span class="sxs-lookup"><span data-stu-id="008e2-128">Original value name</span></span> | <span data-ttu-id="008e2-129">Nieuwe waardenaam</span><span class="sxs-lookup"><span data-stu-id="008e2-129">New value name</span></span> | <span data-ttu-id="008e2-130">Reden voor wijziging</span><span class="sxs-lookup"><span data-stu-id="008e2-130">Reason for change</span></span>
|--|--|--|--|
| `DetectionSource` | <span data-ttu-id="008e2-131">MCAS</span><span class="sxs-lookup"><span data-stu-id="008e2-131">MCAS</span></span> |    <span data-ttu-id="008e2-132">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="008e2-132">Microsoft Cloud App Security</span></span> | <span data-ttu-id="008e2-133">Naamswijziging</span><span class="sxs-lookup"><span data-stu-id="008e2-133">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="008e2-134">WindowsDefenderAtp</span><span class="sxs-lookup"><span data-stu-id="008e2-134">WindowsDefenderAtp</span></span>|   <span data-ttu-id="008e2-135">EDR</span><span class="sxs-lookup"><span data-stu-id="008e2-135">EDR</span></span>| <span data-ttu-id="008e2-136">Naamswijziging</span><span class="sxs-lookup"><span data-stu-id="008e2-136">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="008e2-137">WindowsDefenderAv</span><span class="sxs-lookup"><span data-stu-id="008e2-137">WindowsDefenderAv</span></span> | <span data-ttu-id="008e2-138">Antivirussoftware</span><span class="sxs-lookup"><span data-stu-id="008e2-138">Antivirus</span></span> | <span data-ttu-id="008e2-139">Naamswijziging</span><span class="sxs-lookup"><span data-stu-id="008e2-139">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="008e2-140">WindowsDefenderSmartScreen</span><span class="sxs-lookup"><span data-stu-id="008e2-140">WindowsDefenderSmartScreen</span></span> |  <span data-ttu-id="008e2-141">SmartScreen</span><span class="sxs-lookup"><span data-stu-id="008e2-141">SmartScreen</span></span> | <span data-ttu-id="008e2-142">Naamswijziging</span><span class="sxs-lookup"><span data-stu-id="008e2-142">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="008e2-143">CustomerTI</span><span class="sxs-lookup"><span data-stu-id="008e2-143">CustomerTI</span></span> |  <span data-ttu-id="008e2-144">Aangepaste TI</span><span class="sxs-lookup"><span data-stu-id="008e2-144">Custom TI</span></span> | <span data-ttu-id="008e2-145">Naamswijziging</span><span class="sxs-lookup"><span data-stu-id="008e2-145">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="008e2-146">OfficeATP</span><span class="sxs-lookup"><span data-stu-id="008e2-146">OfficeATP</span></span> | <span data-ttu-id="008e2-147">Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="008e2-147">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="008e2-148">Naamswijziging</span><span class="sxs-lookup"><span data-stu-id="008e2-148">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="008e2-149">MTP</span><span class="sxs-lookup"><span data-stu-id="008e2-149">MTP</span></span>   | <span data-ttu-id="008e2-150">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="008e2-150">Microsoft 365 Defender</span></span> | <span data-ttu-id="008e2-151">Naamswijziging</span><span class="sxs-lookup"><span data-stu-id="008e2-151">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="008e2-152">AzureATP</span><span class="sxs-lookup"><span data-stu-id="008e2-152">AzureATP</span></span> |    <span data-ttu-id="008e2-153">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="008e2-153">Microsoft Defender for Identity</span></span> | <span data-ttu-id="008e2-154">Naamswijziging</span><span class="sxs-lookup"><span data-stu-id="008e2-154">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="008e2-155">CustomDetection</span><span class="sxs-lookup"><span data-stu-id="008e2-155">CustomDetection</span></span>   | <span data-ttu-id="008e2-156">Aangepaste detectie</span><span class="sxs-lookup"><span data-stu-id="008e2-156">Custom detection</span></span> | <span data-ttu-id="008e2-157">Naamswijziging</span><span class="sxs-lookup"><span data-stu-id="008e2-157">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="008e2-158">AutomatedInvestigation</span><span class="sxs-lookup"><span data-stu-id="008e2-158">AutomatedInvestigation</span></span> |<span data-ttu-id="008e2-159">Geautomatiseerd onderzoek</span><span class="sxs-lookup"><span data-stu-id="008e2-159">Automated investigation</span></span> | <span data-ttu-id="008e2-160">Naamswijziging</span><span class="sxs-lookup"><span data-stu-id="008e2-160">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="008e2-161">ThreatExperts</span><span class="sxs-lookup"><span data-stu-id="008e2-161">ThreatExperts</span></span> | <span data-ttu-id="008e2-162">Microsoft Threat Experts</span><span class="sxs-lookup"><span data-stu-id="008e2-162">Microsoft Threat Experts</span></span> | <span data-ttu-id="008e2-163">Naamswijziging</span><span class="sxs-lookup"><span data-stu-id="008e2-163">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="008e2-164">TI van derden</span><span class="sxs-lookup"><span data-stu-id="008e2-164">3rd party TI</span></span> | <span data-ttu-id="008e2-165">Sensoren van derden</span><span class="sxs-lookup"><span data-stu-id="008e2-165">3rd Party sensors</span></span> | <span data-ttu-id="008e2-166">Naamswijziging</span><span class="sxs-lookup"><span data-stu-id="008e2-166">Rebranding</span></span> |
| `ServiceSource` | <span data-ttu-id="008e2-167">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="008e2-167">Microsoft Defender ATP</span></span>| <span data-ttu-id="008e2-168">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="008e2-168">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="008e2-169">Naamswijziging</span><span class="sxs-lookup"><span data-stu-id="008e2-169">Rebranding</span></span> |
|`ServiceSource` |<span data-ttu-id="008e2-170">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="008e2-170">Microsoft Threat Protection</span></span>   | <span data-ttu-id="008e2-171">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="008e2-171">Microsoft 365 Defender</span></span> | <span data-ttu-id="008e2-172">Naamswijziging</span><span class="sxs-lookup"><span data-stu-id="008e2-172">Rebranding</span></span> |
| `ServiceSource` | <span data-ttu-id="008e2-173">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="008e2-173">Office 365 ATP</span></span>  |<span data-ttu-id="008e2-174">Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="008e2-174">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="008e2-175">Naamswijziging</span><span class="sxs-lookup"><span data-stu-id="008e2-175">Rebranding</span></span> |
| `ServiceSource` |<span data-ttu-id="008e2-176">Azure ATP</span><span class="sxs-lookup"><span data-stu-id="008e2-176">Azure ATP</span></span>    |<span data-ttu-id="008e2-177">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="008e2-177">Microsoft Defender for Identity</span></span> | <span data-ttu-id="008e2-178">Naamswijziging</span><span class="sxs-lookup"><span data-stu-id="008e2-178">Rebranding</span></span> |

<span data-ttu-id="008e2-179">`DetectionSource`is beschikbaar in de [tabel AlertInfo.](advanced-hunting-alertinfo-table.md)</span><span class="sxs-lookup"><span data-stu-id="008e2-179">`DetectionSource` is available in the [AlertInfo](advanced-hunting-alertinfo-table.md) table.</span></span> <span data-ttu-id="008e2-180">`ServiceSource`is beschikbaar in de [tabellen AlertEvidence en](advanced-hunting-alertevidence-table.md) [AlertInfo.](advanced-hunting-alertinfo-table.md)</span><span class="sxs-lookup"><span data-stu-id="008e2-180">`ServiceSource` is available in the [AlertEvidence](advanced-hunting-alertevidence-table.md) and [AlertInfo](advanced-hunting-alertinfo-table.md) tables.</span></span> 
## <a name="related-topics"></a><span data-ttu-id="008e2-181">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="008e2-181">Related topics</span></span>
- [<span data-ttu-id="008e2-182">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="008e2-182">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="008e2-183">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="008e2-183">Understand the schema</span></span>](advanced-hunting-schema-tables.md)