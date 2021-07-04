---
title: Waarschuwings-API krijgen
description: Meer informatie over de methoden en eigenschappen van het brontype Waarschuwing in Microsoft Defender voor Eindpunt.
keywords: api's, graph api, ondersteunde api's, get, waarschuwingen, recent
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: df1a032ffab0490c41edc7d282f0f2cc60608870
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289677"
---
# <a name="alert-resource-type"></a><span data-ttu-id="1a9e6-104">Type waarschuwingsresource</span><span class="sxs-lookup"><span data-stu-id="1a9e6-104">Alert resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1a9e6-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="1a9e6-105">**Applies to:**</span></span>
- [<span data-ttu-id="1a9e6-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="1a9e6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

- <span data-ttu-id="1a9e6-107">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="1a9e6-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1a9e6-108">Meld u aan voor een gratis proefversie.</span><span class="sxs-lookup"><span data-stu-id="1a9e6-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="methods"></a><span data-ttu-id="1a9e6-109">Methoden</span><span class="sxs-lookup"><span data-stu-id="1a9e6-109">Methods</span></span>

<span data-ttu-id="1a9e6-110">Methode</span><span class="sxs-lookup"><span data-stu-id="1a9e6-110">Method</span></span> |<span data-ttu-id="1a9e6-111">Retourtype</span><span class="sxs-lookup"><span data-stu-id="1a9e6-111">Return Type</span></span> |<span data-ttu-id="1a9e6-112">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="1a9e6-112">Description</span></span>
:---|:---|:---
[<span data-ttu-id="1a9e6-113">Waarschuwing ontvangen</span><span class="sxs-lookup"><span data-stu-id="1a9e6-113">Get alert</span></span>](get-alert-info-by-id.md) | [<span data-ttu-id="1a9e6-114">Waarschuwingsweergave</span><span class="sxs-lookup"><span data-stu-id="1a9e6-114">Alert</span></span>](alerts.md) | <span data-ttu-id="1a9e6-115">Eén [waarschuwingsobject](alerts.md) krijgen.</span><span class="sxs-lookup"><span data-stu-id="1a9e6-115">Get a single [alert](alerts.md) object.</span></span>
[<span data-ttu-id="1a9e6-116">Lijstwaarschuwingen</span><span class="sxs-lookup"><span data-stu-id="1a9e6-116">List alerts</span></span>](get-alerts.md) | <span data-ttu-id="1a9e6-117">[Waarschuwingsverzameling](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="1a9e6-117">[Alert](alerts.md) collection</span></span> | <span data-ttu-id="1a9e6-118">[Lijstwaarschuwingsverzameling.](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="1a9e6-118">List [alert](alerts.md) collection.</span></span>
[<span data-ttu-id="1a9e6-119">Waarschuwing bijwerken</span><span class="sxs-lookup"><span data-stu-id="1a9e6-119">Update alert</span></span>](update-alert.md) | [<span data-ttu-id="1a9e6-120">Waarschuwingsweergave</span><span class="sxs-lookup"><span data-stu-id="1a9e6-120">Alert</span></span>](alerts.md) | <span data-ttu-id="1a9e6-121">Specifieke waarschuwing [bijwerken](alerts.md).</span><span class="sxs-lookup"><span data-stu-id="1a9e6-121">Update specific [alert](alerts.md).</span></span>
[<span data-ttu-id="1a9e6-122">Batchupdatewaarschuwingen</span><span class="sxs-lookup"><span data-stu-id="1a9e6-122">Batch update alerts</span></span>](batch-update-alerts.md) | | <span data-ttu-id="1a9e6-123">Een reeks waarschuwingen [bijwerken.](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="1a9e6-123">Update a batch of [alerts](alerts.md).</span></span>
[<span data-ttu-id="1a9e6-124">Waarschuwing maken</span><span class="sxs-lookup"><span data-stu-id="1a9e6-124">Create alert</span></span>](create-alert-by-reference.md)|[<span data-ttu-id="1a9e6-125">Waarschuwingsweergave</span><span class="sxs-lookup"><span data-stu-id="1a9e6-125">Alert</span></span>](alerts.md)|<span data-ttu-id="1a9e6-126">Maak een waarschuwing op basis van gebeurtenisgegevens die zijn verkregen uit [Advanced Hunting.](run-advanced-query-api.md)</span><span class="sxs-lookup"><span data-stu-id="1a9e6-126">Create an alert based on event data obtained from [Advanced Hunting](run-advanced-query-api.md).</span></span>
[<span data-ttu-id="1a9e6-127">Gerelateerde domeinen lijst</span><span class="sxs-lookup"><span data-stu-id="1a9e6-127">List related domains</span></span>](get-alert-related-domain-info.md)|<span data-ttu-id="1a9e6-128">Domeinverzameling</span><span class="sxs-lookup"><span data-stu-id="1a9e6-128">Domain collection</span></span>| <span data-ttu-id="1a9e6-129">Lijst-URL's die aan de waarschuwing zijn gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="1a9e6-129">List URLs associated with the alert.</span></span>
[<span data-ttu-id="1a9e6-130">Gerelateerde bestanden lijst</span><span class="sxs-lookup"><span data-stu-id="1a9e6-130">List related files</span></span>](get-alert-related-files-info.md) | <span data-ttu-id="1a9e6-131">[Bestandsverzameling](files.md)</span><span class="sxs-lookup"><span data-stu-id="1a9e6-131">[File](files.md) collection</span></span> |  <span data-ttu-id="1a9e6-132">Vermeld [](files.md) de bestandsentiteiten die aan de [waarschuwing zijn gekoppeld.](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="1a9e6-132">List the [file](files.md) entities that are associated with the [alert](alerts.md).</span></span>
[<span data-ttu-id="1a9e6-133">Lijstgerelateerde IPs</span><span class="sxs-lookup"><span data-stu-id="1a9e6-133">List related IPs</span></span>](get-alert-related-ip-info.md) | <span data-ttu-id="1a9e6-134">IP-verzameling</span><span class="sxs-lookup"><span data-stu-id="1a9e6-134">IP collection</span></span> | <span data-ttu-id="1a9e6-135">Lijst-IPs die zijn gekoppeld aan de waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="1a9e6-135">List IPs that are associated with the alert.</span></span>
[<span data-ttu-id="1a9e6-136">Gerelateerde machines krijgen</span><span class="sxs-lookup"><span data-stu-id="1a9e6-136">Get related machines</span></span>](get-alert-related-machine-info.md) | [<span data-ttu-id="1a9e6-137">Computer</span><span class="sxs-lookup"><span data-stu-id="1a9e6-137">Machine</span></span>](machine.md) | <span data-ttu-id="1a9e6-138">De [computer](machine.md) die is gekoppeld aan de [waarschuwing](alerts.md).</span><span class="sxs-lookup"><span data-stu-id="1a9e6-138">The [machine](machine.md) that is associated with the [alert](alerts.md).</span></span>
[<span data-ttu-id="1a9e6-139">Verwante gebruikers krijgen</span><span class="sxs-lookup"><span data-stu-id="1a9e6-139">Get related users</span></span>](get-alert-related-user-info.md) | [<span data-ttu-id="1a9e6-140">Gebruiker</span><span class="sxs-lookup"><span data-stu-id="1a9e6-140">User</span></span>](user.md) | <span data-ttu-id="1a9e6-141">De [gebruiker](user.md) die is gekoppeld aan de [waarschuwing](alerts.md).</span><span class="sxs-lookup"><span data-stu-id="1a9e6-141">The [user](user.md) that is associated with the [alert](alerts.md).</span></span>

## <a name="properties"></a><span data-ttu-id="1a9e6-142">Eigenschappen</span><span class="sxs-lookup"><span data-stu-id="1a9e6-142">Properties</span></span>

<span data-ttu-id="1a9e6-143">Eigenschap</span><span class="sxs-lookup"><span data-stu-id="1a9e6-143">Property</span></span> |    <span data-ttu-id="1a9e6-144">Type</span><span class="sxs-lookup"><span data-stu-id="1a9e6-144">Type</span></span>    |    <span data-ttu-id="1a9e6-145">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="1a9e6-145">Description</span></span>
:---|:---|:---
<span data-ttu-id="1a9e6-146">id</span><span class="sxs-lookup"><span data-stu-id="1a9e6-146">id</span></span> | <span data-ttu-id="1a9e6-147">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="1a9e6-147">String</span></span> | <span data-ttu-id="1a9e6-148">Waarschuwings-id.</span><span class="sxs-lookup"><span data-stu-id="1a9e6-148">Alert ID.</span></span>
<span data-ttu-id="1a9e6-149">titel</span><span class="sxs-lookup"><span data-stu-id="1a9e6-149">title</span></span> | <span data-ttu-id="1a9e6-150">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="1a9e6-150">String</span></span> | <span data-ttu-id="1a9e6-151">Waarschuwingstitel.</span><span class="sxs-lookup"><span data-stu-id="1a9e6-151">Alert title.</span></span>
<span data-ttu-id="1a9e6-152">beschrijving</span><span class="sxs-lookup"><span data-stu-id="1a9e6-152">description</span></span> | <span data-ttu-id="1a9e6-153">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="1a9e6-153">String</span></span> | <span data-ttu-id="1a9e6-154">Beschrijving van waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="1a9e6-154">Alert description.</span></span>
<span data-ttu-id="1a9e6-155">alertCreationTime</span><span class="sxs-lookup"><span data-stu-id="1a9e6-155">alertCreationTime</span></span> | <span data-ttu-id="1a9e6-156">Nullable DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="1a9e6-156">Nullable DateTimeOffset</span></span> | <span data-ttu-id="1a9e6-157">De datum en tijd (in UTC) de waarschuwing is gemaakt.</span><span class="sxs-lookup"><span data-stu-id="1a9e6-157">The date and time (in UTC) the alert was created.</span></span>
<span data-ttu-id="1a9e6-158">lastEventTime</span><span class="sxs-lookup"><span data-stu-id="1a9e6-158">lastEventTime</span></span> | <span data-ttu-id="1a9e6-159">Nullable DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="1a9e6-159">Nullable DateTimeOffset</span></span> | <span data-ttu-id="1a9e6-160">De laatste gebeurtenis die de waarschuwing op hetzelfde apparaat heeft geactiveerd.</span><span class="sxs-lookup"><span data-stu-id="1a9e6-160">The last occurrence of the event that triggered the alert on the same device.</span></span>
<span data-ttu-id="1a9e6-161">firstEventTime</span><span class="sxs-lookup"><span data-stu-id="1a9e6-161">firstEventTime</span></span> | <span data-ttu-id="1a9e6-162">Nullable DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="1a9e6-162">Nullable DateTimeOffset</span></span> | <span data-ttu-id="1a9e6-163">De eerste gebeurtenis die de waarschuwing op dat apparaat heeft geactiveerd.</span><span class="sxs-lookup"><span data-stu-id="1a9e6-163">The first occurrence of the event that triggered the alert on that device.</span></span>
<span data-ttu-id="1a9e6-164">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="1a9e6-164">lastUpdateTime</span></span> | <span data-ttu-id="1a9e6-165">Nullable DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="1a9e6-165">Nullable DateTimeOffset</span></span> | <span data-ttu-id="1a9e6-166">De datum en tijd (in UTC) de waarschuwing is voor het laatst bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="1a9e6-166">The date and time (in UTC) the alert was last updated.</span></span>
<span data-ttu-id="1a9e6-167">resolvedTime</span><span class="sxs-lookup"><span data-stu-id="1a9e6-167">resolvedTime</span></span> | <span data-ttu-id="1a9e6-168">Nullable DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="1a9e6-168">Nullable DateTimeOffset</span></span> | <span data-ttu-id="1a9e6-169">De datum en tijd waarin de status van de waarschuwing is gewijzigd in 'Opgelost'.</span><span class="sxs-lookup"><span data-stu-id="1a9e6-169">The date and time in which the status of the alert was changed to 'Resolved'.</span></span>
<span data-ttu-id="1a9e6-170">incidentId</span><span class="sxs-lookup"><span data-stu-id="1a9e6-170">incidentId</span></span> | <span data-ttu-id="1a9e6-171">Nullable Long</span><span class="sxs-lookup"><span data-stu-id="1a9e6-171">Nullable Long</span></span> | <span data-ttu-id="1a9e6-172">De [incident-id](view-incidents-queue.md) van de waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="1a9e6-172">The [Incident](view-incidents-queue.md) ID of the Alert.</span></span>
<span data-ttu-id="1a9e6-173">investigationId</span><span class="sxs-lookup"><span data-stu-id="1a9e6-173">investigationId</span></span> | <span data-ttu-id="1a9e6-174">Nullable Long</span><span class="sxs-lookup"><span data-stu-id="1a9e6-174">Nullable Long</span></span> | <span data-ttu-id="1a9e6-175">De [onderzoeks-id](automated-investigations.md) die is gerelateerd aan de waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="1a9e6-175">The [Investigation](automated-investigations.md) ID related to the Alert.</span></span>
<span data-ttu-id="1a9e6-176">investigationState</span><span class="sxs-lookup"><span data-stu-id="1a9e6-176">investigationState</span></span> | <span data-ttu-id="1a9e6-177">Nullable Enum</span><span class="sxs-lookup"><span data-stu-id="1a9e6-177">Nullable Enum</span></span> | <span data-ttu-id="1a9e6-178">De huidige stand van het [onderzoek](automated-investigations.md).</span><span class="sxs-lookup"><span data-stu-id="1a9e6-178">The current state of the [Investigation](automated-investigations.md).</span></span> <span data-ttu-id="1a9e6-179">Mogelijke waarden zijn: 'Onbekend', 'Beëindigd', 'SuccessfullyRemediated', 'Benign', 'Failed', 'PartiallyRemediated', 'Running', 'PendingApproval', 'PendingResource', 'PartiallyInvestigated', 'TerminatedByUser', 'TerminatedBySystem', 'Queued', 'InnerFailure', 'PreexistingAlert', 'UnsupportedOs', 'UnsupportedAlertType', 'SuppressedAlert'.</span><span class="sxs-lookup"><span data-stu-id="1a9e6-179">Possible values are: 'Unknown', 'Terminated', 'SuccessfullyRemediated', 'Benign', 'Failed', 'PartiallyRemediated', 'Running', 'PendingApproval', 'PendingResource', 'PartiallyInvestigated', 'TerminatedByUser', 'TerminatedBySystem', 'Queued', 'InnerFailure', 'PreexistingAlert', 'UnsupportedOs', 'UnsupportedAlertType', 'SuppressedAlert'.</span></span>
<span data-ttu-id="1a9e6-180">toegewezenTo</span><span class="sxs-lookup"><span data-stu-id="1a9e6-180">assignedTo</span></span> | <span data-ttu-id="1a9e6-181">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="1a9e6-181">String</span></span> | <span data-ttu-id="1a9e6-182">Eigenaar van de waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="1a9e6-182">Owner of the alert.</span></span>
<span data-ttu-id="1a9e6-183">ernst</span><span class="sxs-lookup"><span data-stu-id="1a9e6-183">severity</span></span> | <span data-ttu-id="1a9e6-184">Enum</span><span class="sxs-lookup"><span data-stu-id="1a9e6-184">Enum</span></span> | <span data-ttu-id="1a9e6-185">Ernst van de waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="1a9e6-185">Severity of the alert.</span></span> <span data-ttu-id="1a9e6-186">Mogelijke waarden zijn: 'Niet gespecificeerd', 'Informatief', 'Laag', 'Gemiddeld' en 'Hoog'.</span><span class="sxs-lookup"><span data-stu-id="1a9e6-186">Possible values are: 'UnSpecified', 'Informational', 'Low', 'Medium' and 'High'.</span></span>
<span data-ttu-id="1a9e6-187">status</span><span class="sxs-lookup"><span data-stu-id="1a9e6-187">status</span></span> | <span data-ttu-id="1a9e6-188">Enum</span><span class="sxs-lookup"><span data-stu-id="1a9e6-188">Enum</span></span> | <span data-ttu-id="1a9e6-189">Hiermee geeft u de huidige status van de waarschuwing op.</span><span class="sxs-lookup"><span data-stu-id="1a9e6-189">Specifies the current status of the alert.</span></span> <span data-ttu-id="1a9e6-190">Mogelijke waarden zijn: 'Onbekend', 'Nieuw', 'InProgress' en 'Opgelost'.</span><span class="sxs-lookup"><span data-stu-id="1a9e6-190">Possible values are: 'Unknown', 'New', 'InProgress' and 'Resolved'.</span></span>
<span data-ttu-id="1a9e6-191">classificatie</span><span class="sxs-lookup"><span data-stu-id="1a9e6-191">classification</span></span> | <span data-ttu-id="1a9e6-192">Nullable Enum</span><span class="sxs-lookup"><span data-stu-id="1a9e6-192">Nullable Enum</span></span> | <span data-ttu-id="1a9e6-193">Specificatie van de waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="1a9e6-193">Specification of the alert.</span></span> <span data-ttu-id="1a9e6-194">Mogelijke waarden zijn: 'Onbekend', 'FalsePositive', 'TruePositive'.</span><span class="sxs-lookup"><span data-stu-id="1a9e6-194">Possible values are: 'Unknown', 'FalsePositive', 'TruePositive'.</span></span>
<span data-ttu-id="1a9e6-195">bepaling</span><span class="sxs-lookup"><span data-stu-id="1a9e6-195">determination</span></span> | <span data-ttu-id="1a9e6-196">Nullable Enum</span><span class="sxs-lookup"><span data-stu-id="1a9e6-196">Nullable Enum</span></span> | <span data-ttu-id="1a9e6-197">Hiermee geeft u de bepaling van de waarschuwing op.</span><span class="sxs-lookup"><span data-stu-id="1a9e6-197">Specifies the determination of the alert.</span></span> <span data-ttu-id="1a9e6-198">Mogelijke waarden zijn: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'.</span><span class="sxs-lookup"><span data-stu-id="1a9e6-198">Possible values are: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'.</span></span>
<span data-ttu-id="1a9e6-199">categorie</span><span class="sxs-lookup"><span data-stu-id="1a9e6-199">category</span></span>| <span data-ttu-id="1a9e6-200">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="1a9e6-200">String</span></span> | <span data-ttu-id="1a9e6-201">Categorie van de waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="1a9e6-201">Category of the alert.</span></span>
<span data-ttu-id="1a9e6-202">detectionSource</span><span class="sxs-lookup"><span data-stu-id="1a9e6-202">detectionSource</span></span> | <span data-ttu-id="1a9e6-203">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="1a9e6-203">String</span></span> | <span data-ttu-id="1a9e6-204">Detectiebron.</span><span class="sxs-lookup"><span data-stu-id="1a9e6-204">Detection source.</span></span>
<span data-ttu-id="1a9e6-205">threatFamilyName</span><span class="sxs-lookup"><span data-stu-id="1a9e6-205">threatFamilyName</span></span> | <span data-ttu-id="1a9e6-206">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="1a9e6-206">String</span></span> | <span data-ttu-id="1a9e6-207">Familie van bedreigingen.</span><span class="sxs-lookup"><span data-stu-id="1a9e6-207">Threat family.</span></span>
<span data-ttu-id="1a9e6-208">threatName</span><span class="sxs-lookup"><span data-stu-id="1a9e6-208">threatName</span></span> | <span data-ttu-id="1a9e6-209">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="1a9e6-209">String</span></span> | <span data-ttu-id="1a9e6-210">Bedreigingsnaam.</span><span class="sxs-lookup"><span data-stu-id="1a9e6-210">Threat name.</span></span>
<span data-ttu-id="1a9e6-211">machineId</span><span class="sxs-lookup"><span data-stu-id="1a9e6-211">machineId</span></span> | <span data-ttu-id="1a9e6-212">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="1a9e6-212">String</span></span> | <span data-ttu-id="1a9e6-213">Id van een [machine-entiteit](machine.md) die is gekoppeld aan de waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="1a9e6-213">ID of a [machine](machine.md) entity that is associated with the alert.</span></span>
<span data-ttu-id="1a9e6-214">computerDnsName</span><span class="sxs-lookup"><span data-stu-id="1a9e6-214">computerDnsName</span></span> | <span data-ttu-id="1a9e6-215">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="1a9e6-215">String</span></span> | <span data-ttu-id="1a9e6-216">[computer](machine.md) volledig gekwalificeerde naam.</span><span class="sxs-lookup"><span data-stu-id="1a9e6-216">[machine](machine.md) fully qualified name.</span></span>
<span data-ttu-id="1a9e6-217">aadTenantId</span><span class="sxs-lookup"><span data-stu-id="1a9e6-217">aadTenantId</span></span> | <span data-ttu-id="1a9e6-218">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="1a9e6-218">String</span></span> | <span data-ttu-id="1a9e6-219">De Azure Active Directory id.</span><span class="sxs-lookup"><span data-stu-id="1a9e6-219">The Azure Active Directory ID.</span></span>
<span data-ttu-id="1a9e6-220">melderId</span><span class="sxs-lookup"><span data-stu-id="1a9e6-220">detectorId</span></span> | <span data-ttu-id="1a9e6-221">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="1a9e6-221">String</span></span> | <span data-ttu-id="1a9e6-222">De id van de melder die de waarschuwing heeft geactiveerd.</span><span class="sxs-lookup"><span data-stu-id="1a9e6-222">The ID of the detector that triggered the alert.</span></span>
<span data-ttu-id="1a9e6-223">opmerkingen</span><span class="sxs-lookup"><span data-stu-id="1a9e6-223">comments</span></span> | <span data-ttu-id="1a9e6-224">Lijst met opmerkingen over waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="1a9e6-224">List of Alert comments</span></span> | <span data-ttu-id="1a9e6-225">Object Waarschuwingscommentant bevat: tekenreeks, gemaaktEen tekenreeks en createTime date time.</span><span class="sxs-lookup"><span data-stu-id="1a9e6-225">Alert Comment object contains: comment string, createdBy string and createTime date time.</span></span>
<span data-ttu-id="1a9e6-226">Bewijs</span><span class="sxs-lookup"><span data-stu-id="1a9e6-226">Evidence</span></span> | <span data-ttu-id="1a9e6-227">Lijst met aanwijzingen voor waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="1a9e6-227">List of Alert evidence</span></span> | <span data-ttu-id="1a9e6-228">Bewijs met betrekking tot de waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="1a9e6-228">Evidence related to the alert.</span></span> <span data-ttu-id="1a9e6-229">Zie het onderstaande voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="1a9e6-229">See example below.</span></span>

### <a name="response-example-for-getting-single-alert"></a><span data-ttu-id="1a9e6-230">Voorbeeld van antwoord voor het ontvangen van een enkele waarschuwing:</span><span class="sxs-lookup"><span data-stu-id="1a9e6-230">Response example for getting single alert:</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/alerts/da637472900382838869_1364969609
```

```json
{
    "id": "da637472900382838869_1364969609",
    "incidentId": 1126093,
    "investigationId": null,
    "assignedTo": null,
    "severity": "Low",
    "status": "New",
    "classification": null,
    "determination": null,
    "investigationState": "Queued",
    "detectionSource": "WindowsDefenderAtp",
    "detectorId": "17e10bbc-3a68-474a-8aad-faef14d43952",
    "category": "Execution",
    "threatFamilyName": null,
    "title": "Low-reputation arbitrary code executed by signed executable",
    "description": "Binaries signed by Microsoft can be used to run low-reputation arbitrary code. This technique hides the execution of malicious code within a trusted process. As a result, the trusted process might exhibit suspicious behaviors, such as opening a listening port or connecting to a command-and-control (C&C) server.",
    "alertCreationTime": "2021-01-26T20:33:57.7220239Z",
    "firstEventTime": "2021-01-26T20:31:32.9562661Z",
    "lastEventTime": "2021-01-26T20:31:33.0577322Z",
    "lastUpdateTime": "2021-01-26T20:33:59.2Z",
    "resolvedTime": null,
    "machineId": "111e6dd8c833c8a052ea231ec1b19adaf497b625",
    "computerDnsName": "temp123.middleeast.corp.microsoft.com",
    "rbacGroupName": "A",
    "aadTenantId": "a839b112-1253-6432-9bf6-94542403f21c",
    "threatName": null,
    "mitreTechniques": [
        "T1064",
        "T1085",
        "T1220"
    ],
    "relatedUser": {
        "userName": "temp123",
        "domainName": "MIDDLEEAST"
    },
    "comments": [
        {
            "comment": "test comment for docs",
            "createdBy": "secop123@contoso.com",
            "createdTime": "2021-01-26T01:00:37.8404534Z"
        }
    ],
    "evidence": [
        {
            "entityType": "User",
            "evidenceCreationTime": "2021-01-26T20:33:58.42Z",
            "sha1": null,
            "sha256": null,
            "fileName": null,
            "filePath": null,
            "processId": null,
            "processCommandLine": null,
            "processCreationTime": null,
            "parentProcessId": null,
            "parentProcessCreationTime": null,
            "parentProcessFileName": null,
            "parentProcessFilePath": null,
            "ipAddress": null,
            "url": null,
            "registryKey": null,
            "registryHive": null,
            "registryValueType": null,
            "registryValue": null,
            "accountName": "eranb",
            "domainName": "MIDDLEEAST",
            "userSid": "S-1-5-21-11111607-1111760036-109187956-75141",
            "aadUserId": "11118379-2a59-1111-ac3c-a51eb4a3c627",
            "userPrincipalName": "temp123@microsoft.com",
            "detectionStatus": null
        },
        {
            "entityType": "Process",
            "evidenceCreationTime": "2021-01-26T20:33:58.6133333Z",
            "sha1": "ff836cfb1af40252bd2a2ea843032e99a5b262ed",
            "sha256": "a4752c71d81afd3d5865d24ddb11a6b0c615062fcc448d24050c2172d2cbccd6",
            "fileName": "rundll32.exe",
            "filePath": "C:\\Windows\\SysWOW64",
            "processId": 3276,
            "processCommandLine": "rundll32.exe  c:\\temp\\suspicious.dll,RepeatAfterMe",
            "processCreationTime": "2021-01-26T20:31:32.9581596Z",
            "parentProcessId": 8420,
            "parentProcessCreationTime": "2021-01-26T20:31:32.9004163Z",
            "parentProcessFileName": "rundll32.exe",
            "parentProcessFilePath": "C:\\Windows\\System32",
            "ipAddress": null,
            "url": null,
            "registryKey": null,
            "registryHive": null,
            "registryValueType": null,
            "registryValue": null,
            "accountName": null,
            "domainName": null,
            "userSid": null,
            "aadUserId": null,
            "userPrincipalName": null,
            "detectionStatus": "Detected"
        },
        {
            "entityType": "File",
            "evidenceCreationTime": "2021-01-26T20:33:58.42Z",
            "sha1": "8563f95b2f8a284fc99da44500cd51a77c1ff36c",
            "sha256": "dc0ade0c95d6db98882bc8fa6707e64353cd6f7767ff48d6a81a6c2aef21c608",
            "fileName": "suspicious.dll",
            "filePath": "c:\\temp",
            "processId": null,
            "processCommandLine": null,
            "processCreationTime": null,
            "parentProcessId": null,
            "parentProcessCreationTime": null,
            "parentProcessFileName": null,
            "parentProcessFilePath": null,
            "ipAddress": null,
            "url": null,
            "registryKey": null,
            "registryHive": null,
            "registryValueType": null,
            "registryValue": null,
            "accountName": null,
            "domainName": null,
            "userSid": null,
            "aadUserId": null,
            "userPrincipalName": null,
            "detectionStatus": "Detected"
        }
    ]
}
```
