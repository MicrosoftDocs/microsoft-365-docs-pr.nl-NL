---
title: Microsoft 365 Api's voor Defender-incidenten en het resourcetype incidenten
description: Meer informatie over de methoden en eigenschappen van het resourcetype Incidenten in Microsoft 365 Defender
keywords: incident, incidenten, api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 0c0c2e280f63076687a0854e25c47577b050a8f7
ms.sourcegitcommit: 03aa8ed22d9ef685a851e28c7d0cfb725732fe4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/10/2021
ms.locfileid: "52888431"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incidents-resource-type"></a><span data-ttu-id="e447b-104">Microsoft 365 Defender-incidenten-API en het resourcetype incidenten</span><span class="sxs-lookup"><span data-stu-id="e447b-104">Microsoft 365 Defender incidents API and the incidents resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="e447b-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="e447b-105">**Applies to:**</span></span>

- [<span data-ttu-id="e447b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e447b-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> <span data-ttu-id="e447b-107">Sommige informatie is gerelateerd aan voorlopige productversies die mogelijk aanzienlijk gewijzigd worden voordat ze commercieel gepubliceerd worden.</span><span class="sxs-lookup"><span data-stu-id="e447b-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="e447b-108">Microsoft geeft geen garantie, uitdrukkelijk of impliciet, met betrekking tot de informatie die hier wordt beschreven.</span><span class="sxs-lookup"><span data-stu-id="e447b-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="e447b-109">Een [incident](incidents-overview.md) is een verzameling gerelateerde waarschuwingen die helpen bij het beschrijven van een aanval.</span><span class="sxs-lookup"><span data-stu-id="e447b-109">An [incident](incidents-overview.md) is a collection of related alerts that help describe an attack.</span></span> <span data-ttu-id="e447b-110">Gebeurtenissen uit verschillende entiteiten in uw organisatie worden automatisch samengevoegd door Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="e447b-110">Events from different entities in your organization are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="e447b-111">U kunt de API voor incidenten gebruiken om programmaatically toegang te krijgen tot de incidenten en gerelateerde waarschuwingen van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="e447b-111">You can use the incidents API to programatically access your organization's incidents and related alerts.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="e447b-112">Quota en resourcetoewijzing</span><span class="sxs-lookup"><span data-stu-id="e447b-112">Quotas and resource allocation</span></span>

<span data-ttu-id="e447b-113">U kunt maximaal 50 oproepen per minuut of 1500 oproepen per uur aanvragen.</span><span class="sxs-lookup"><span data-stu-id="e447b-113">You can request up to 50 calls per minute or 1500 calls per hour.</span></span> <span data-ttu-id="e447b-114">Elke methode heeft ook een eigen quotum.</span><span class="sxs-lookup"><span data-stu-id="e447b-114">Each method also has its own quotas.</span></span> <span data-ttu-id="e447b-115">Zie het betreffende artikel voor de methode die u wilt gebruiken voor meer informatie over methodespecifieke quota.</span><span class="sxs-lookup"><span data-stu-id="e447b-115">For more information on method-specific quotas, see the respective article for the method you want to use.</span></span>

<span data-ttu-id="e447b-116">Een HTTP-antwoordcode geeft aan dat u een quotum hebt bereikt, hetzij op het aantal verzonden aanvragen, hetzij door de toegewezen `429` gebruikstijd.</span><span class="sxs-lookup"><span data-stu-id="e447b-116">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="e447b-117">De reactie body bevat de tijd totdat het quotum dat u hebt bereikt, opnieuw wordt ingesteld.</span><span class="sxs-lookup"><span data-stu-id="e447b-117">The response body will include the time until the quota you reached will be reset.</span></span>

## <a name="permissions"></a><span data-ttu-id="e447b-118">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="e447b-118">Permissions</span></span>

<span data-ttu-id="e447b-119">Voor de API voor incidenten zijn verschillende soorten machtigingen voor elk van de methoden vereist.</span><span class="sxs-lookup"><span data-stu-id="e447b-119">The incidents API requires different kinds of permissions for each of its methods.</span></span> <span data-ttu-id="e447b-120">Zie het artikel van de betreffende methode voor meer informatie over vereiste machtigingen.</span><span class="sxs-lookup"><span data-stu-id="e447b-120">For more information about required permissions, see the respective method's article.</span></span>

## <a name="methods"></a><span data-ttu-id="e447b-121">Methoden</span><span class="sxs-lookup"><span data-stu-id="e447b-121">Methods</span></span>

<span data-ttu-id="e447b-122">Methode</span><span class="sxs-lookup"><span data-stu-id="e447b-122">Method</span></span> | <span data-ttu-id="e447b-123">Retourtype</span><span class="sxs-lookup"><span data-stu-id="e447b-123">Return Type</span></span> | <span data-ttu-id="e447b-124">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="e447b-124">Description</span></span>
-|-|-
[<span data-ttu-id="e447b-125">Lijst met incidenten</span><span class="sxs-lookup"><span data-stu-id="e447b-125">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="e447b-126">[Lijst met incidenten](api-incident.md)</span><span class="sxs-lookup"><span data-stu-id="e447b-126">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="e447b-127">Een lijst met incidenten.</span><span class="sxs-lookup"><span data-stu-id="e447b-127">Get a list of incidents.</span></span>
[<span data-ttu-id="e447b-128">Incident bijwerken</span><span class="sxs-lookup"><span data-stu-id="e447b-128">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="e447b-129">Incident</span><span class="sxs-lookup"><span data-stu-id="e447b-129">Incident</span></span>](api-incident.md) | <span data-ttu-id="e447b-130">Een specifiek incident bijwerken.</span><span class="sxs-lookup"><span data-stu-id="e447b-130">Update a specific incident.</span></span>
[<span data-ttu-id="e447b-131">Incident opsn</span><span class="sxs-lookup"><span data-stu-id="e447b-131">Get incident</span></span>](api-get-incident.md) | [<span data-ttu-id="e447b-132">Incident</span><span class="sxs-lookup"><span data-stu-id="e447b-132">Incident</span></span>](api-incident.md) | <span data-ttu-id="e447b-133">Eén incident.</span><span class="sxs-lookup"><span data-stu-id="e447b-133">Get a single incident.</span></span>

## <a name="request-body-response-and-examples"></a><span data-ttu-id="e447b-134">Body, antwoord en voorbeelden aanvragen</span><span class="sxs-lookup"><span data-stu-id="e447b-134">Request body, response, and examples</span></span>

<span data-ttu-id="e447b-135">Raadpleeg de betreffende methodeartikelen voor meer informatie over het maken van een aanvraag of het parseren van een antwoord en voor praktische voorbeelden.</span><span class="sxs-lookup"><span data-stu-id="e447b-135">Refer to the respective method articles for more details on how to construct a request or parse a response, and for practical examples.</span></span>

## <a name="common-properties"></a><span data-ttu-id="e447b-136">Veelgebruikte eigenschappen</span><span class="sxs-lookup"><span data-stu-id="e447b-136">Common properties</span></span>

<span data-ttu-id="e447b-137">Eigenschap</span><span class="sxs-lookup"><span data-stu-id="e447b-137">Property</span></span> | <span data-ttu-id="e447b-138">Type</span><span class="sxs-lookup"><span data-stu-id="e447b-138">Type</span></span> | <span data-ttu-id="e447b-139">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="e447b-139">Description</span></span>
-|-|-
<span data-ttu-id="e447b-140">incidentId</span><span class="sxs-lookup"><span data-stu-id="e447b-140">incidentId</span></span> | <span data-ttu-id="e447b-141">lang</span><span class="sxs-lookup"><span data-stu-id="e447b-141">long</span></span> | <span data-ttu-id="e447b-142">Unieke id voor incidenten.</span><span class="sxs-lookup"><span data-stu-id="e447b-142">Incident unique ID.</span></span>
<span data-ttu-id="e447b-143">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="e447b-143">redirectIncidentId</span></span> | <span data-ttu-id="e447b-144">nullable long</span><span class="sxs-lookup"><span data-stu-id="e447b-144">nullable long</span></span> | <span data-ttu-id="e447b-145">De incident-id waarbij het huidige incident is samengevoegd.</span><span class="sxs-lookup"><span data-stu-id="e447b-145">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="e447b-146">incidentName</span><span class="sxs-lookup"><span data-stu-id="e447b-146">incidentName</span></span> | <span data-ttu-id="e447b-147">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="e447b-147">string</span></span> | <span data-ttu-id="e447b-148">De naam van het incident.</span><span class="sxs-lookup"><span data-stu-id="e447b-148">The name of the Incident.</span></span>
<span data-ttu-id="e447b-149">createdTime</span><span class="sxs-lookup"><span data-stu-id="e447b-149">createdTime</span></span> | <span data-ttu-id="e447b-150">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="e447b-150">DateTimeOffset</span></span> | <span data-ttu-id="e447b-151">De datum en tijd (in UTC) het incident is gemaakt.</span><span class="sxs-lookup"><span data-stu-id="e447b-151">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="e447b-152">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="e447b-152">lastUpdateTime</span></span> | <span data-ttu-id="e447b-153">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="e447b-153">DateTimeOffset</span></span> | <span data-ttu-id="e447b-154">De datum en tijd (in UTC) het incident is voor het laatst bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="e447b-154">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="e447b-155">toegewezenTo</span><span class="sxs-lookup"><span data-stu-id="e447b-155">assignedTo</span></span> | <span data-ttu-id="e447b-156">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="e447b-156">string</span></span> | <span data-ttu-id="e447b-157">Eigenaar van het incident.</span><span class="sxs-lookup"><span data-stu-id="e447b-157">Owner of the Incident.</span></span>
<span data-ttu-id="e447b-158">ernst</span><span class="sxs-lookup"><span data-stu-id="e447b-158">severity</span></span> | <span data-ttu-id="e447b-159">Enum</span><span class="sxs-lookup"><span data-stu-id="e447b-159">Enum</span></span> | <span data-ttu-id="e447b-160">Ernst van het incident.</span><span class="sxs-lookup"><span data-stu-id="e447b-160">Severity of the Incident.</span></span> <span data-ttu-id="e447b-161">Mogelijke waarden zijn: ```UnSpecified``` , , , en ```Informational``` ```Low``` ```Medium``` ```High``` .</span><span class="sxs-lookup"><span data-stu-id="e447b-161">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium```, and ```High```.</span></span>
<span data-ttu-id="e447b-162">status</span><span class="sxs-lookup"><span data-stu-id="e447b-162">status</span></span> | <span data-ttu-id="e447b-163">Enum</span><span class="sxs-lookup"><span data-stu-id="e447b-163">Enum</span></span> | <span data-ttu-id="e447b-164">Hiermee geeft u de huidige status van het incident op.</span><span class="sxs-lookup"><span data-stu-id="e447b-164">Specifies the current status of the incident.</span></span> <span data-ttu-id="e447b-165">Mogelijke waarden zijn: ```Active``` ```Resolved``` , en ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="e447b-165">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="e447b-166">classificatie</span><span class="sxs-lookup"><span data-stu-id="e447b-166">classification</span></span> | <span data-ttu-id="e447b-167">Enum</span><span class="sxs-lookup"><span data-stu-id="e447b-167">Enum</span></span> | <span data-ttu-id="e447b-168">Specificatie van het incident.</span><span class="sxs-lookup"><span data-stu-id="e447b-168">Specification of the incident.</span></span> <span data-ttu-id="e447b-169">Mogelijke waarden zijn: ```Unknown``` ```FalsePositive``` , , ```TruePositive``` .</span><span class="sxs-lookup"><span data-stu-id="e447b-169">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="e447b-170">bepaling</span><span class="sxs-lookup"><span data-stu-id="e447b-170">determination</span></span> | <span data-ttu-id="e447b-171">Enum</span><span class="sxs-lookup"><span data-stu-id="e447b-171">Enum</span></span> | <span data-ttu-id="e447b-172">Hiermee geeft u de bepaling van het incident op.</span><span class="sxs-lookup"><span data-stu-id="e447b-172">Specifies the determination of the incident.</span></span> <span data-ttu-id="e447b-173">Mogelijke waarden zijn: ```NotAvailable``` , , , , , , ```Apt``` ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` ```UnwantedSoftware``` . ```Other```</span><span class="sxs-lookup"><span data-stu-id="e447b-173">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="e447b-174">tags</span><span class="sxs-lookup"><span data-stu-id="e447b-174">tags</span></span> | <span data-ttu-id="e447b-175">lijst met tekenreeksen</span><span class="sxs-lookup"><span data-stu-id="e447b-175">string List</span></span> | <span data-ttu-id="e447b-176">Lijst met incidentlabels.</span><span class="sxs-lookup"><span data-stu-id="e447b-176">List of Incident tags.</span></span>
<span data-ttu-id="e447b-177">opmerkingen</span><span class="sxs-lookup"><span data-stu-id="e447b-177">comments</span></span> | <span data-ttu-id="e447b-178">Lijst met opmerkingen over incidenten</span><span class="sxs-lookup"><span data-stu-id="e447b-178">List of incident comments</span></span> | <span data-ttu-id="e447b-179">Incident Comment object contains: comment string, createdBy string, and createTime date time.</span><span class="sxs-lookup"><span data-stu-id="e447b-179">Incident Comment object contains: comment string, createdBy string, and createTime date time.</span></span>
<span data-ttu-id="e447b-180">waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="e447b-180">alerts</span></span> | <span data-ttu-id="e447b-181">Lijst met waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="e447b-181">Alert List</span></span> | <span data-ttu-id="e447b-182">Lijst met gerelateerde waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="e447b-182">List of related alerts.</span></span> <span data-ttu-id="e447b-183">Zie voorbeelden van [API-documentatie lijstincidenten.](api-list-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="e447b-183">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>

## <a name="related-articles"></a><span data-ttu-id="e447b-184">Aanverwante artikelen</span><span class="sxs-lookup"><span data-stu-id="e447b-184">Related articles</span></span>

- [<span data-ttu-id="e447b-185">Microsoft 365 Overzicht van DEFENDER-API's</span><span class="sxs-lookup"><span data-stu-id="e447b-185">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="e447b-186">Overzicht van incidenten</span><span class="sxs-lookup"><span data-stu-id="e447b-186">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="e447b-187">Lijstincidenten API</span><span class="sxs-lookup"><span data-stu-id="e447b-187">List incidents API</span></span>](api-list-incidents.md)
- [<span data-ttu-id="e447b-188">Api voor incidenten bijwerken</span><span class="sxs-lookup"><span data-stu-id="e447b-188">Update incident API</span></span>](api-update-incidents.md)
