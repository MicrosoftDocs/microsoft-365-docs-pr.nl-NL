---
title: Microsoft 365 Api's voor Defender-incidenten en het type incidentbron
description: Meer informatie over de methoden en eigenschappen van het resourcetype Incident in Microsoft 365 Defender
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
ms.openlocfilehash: 5cc149668e49e21b38b5fb95ae3f40db6c296e1d
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572583"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incident-resource-type"></a><span data-ttu-id="fba4a-104">Microsoft 365 Api voor Defender-incidenten en het type incidentbron</span><span class="sxs-lookup"><span data-stu-id="fba4a-104">Microsoft 365 Defender incidents API and the incident resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="fba4a-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="fba4a-105">**Applies to:**</span></span>

- <span data-ttu-id="fba4a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fba4a-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fba4a-107">Sommige informatie is gerelateerd aan voorlopige productversies die mogelijk aanzienlijk gewijzigd worden voordat ze commercieel gepubliceerd worden.</span><span class="sxs-lookup"><span data-stu-id="fba4a-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="fba4a-108">Microsoft geeft geen garantie, uitdrukkelijk of impliciet, met betrekking tot de informatie die hier wordt beschreven.</span><span class="sxs-lookup"><span data-stu-id="fba4a-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="fba4a-109">Een [incident](incidents-overview.md) is een verzameling gerelateerde waarschuwingen die een aanval helpen beschrijven.</span><span class="sxs-lookup"><span data-stu-id="fba4a-109">An [incident](incidents-overview.md) is a collection of related alerts that help describe an attack.</span></span> <span data-ttu-id="fba4a-110">Gebeurtenissen van verschillende entiteiten in uw organisatie worden automatisch geaggregeerd door Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="fba4a-110">Events from different entities in your organization are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="fba4a-111">U kunt de incidenten-API gebruiken om programmatisch toegang te krijgen tot de incidenten en gerelateerde waarschuwingen van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="fba4a-111">You can use the incidents API to programatically access your organization's incidents and related alerts.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="fba4a-112">Quota en toewijzing van middelen</span><span class="sxs-lookup"><span data-stu-id="fba4a-112">Quotas and resource allocation</span></span>

<span data-ttu-id="fba4a-113">U kunt maximaal 50 gesprekken per minuut of 1500 oproepen per uur aanvragen.</span><span class="sxs-lookup"><span data-stu-id="fba4a-113">You can request up to 50 calls per minute or 1500 calls per hour.</span></span> <span data-ttu-id="fba4a-114">Elke methode heeft ook zijn eigen quota.</span><span class="sxs-lookup"><span data-stu-id="fba4a-114">Each method also has its own quotas.</span></span> <span data-ttu-id="fba4a-115">Zie het betreffende artikel voor de methode die u wilt gebruiken voor meer informatie over methodespecifieke quota.</span><span class="sxs-lookup"><span data-stu-id="fba4a-115">For more information on method-specific quotas, see the respective article for the method you want to use.</span></span>

<span data-ttu-id="fba4a-116">Een `429` HTTP-antwoordcode geeft aan dat u een quotum hebt bereikt, hetzij op aantal verzonden aanvragen, hetzij op toegewezen looptijd.</span><span class="sxs-lookup"><span data-stu-id="fba4a-116">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="fba4a-117">De hoofdtekst van de reactie bevat de tijd totdat het quotum dat u hebt bereikt, opnieuw wordt ingesteld.</span><span class="sxs-lookup"><span data-stu-id="fba4a-117">The response body will include the time until the quota you reached will be reset.</span></span>

## <a name="permissions"></a><span data-ttu-id="fba4a-118">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="fba4a-118">Permissions</span></span>

<span data-ttu-id="fba4a-119">De incidenten-API vereist verschillende soorten machtigingen voor elk van de methoden.</span><span class="sxs-lookup"><span data-stu-id="fba4a-119">The incidents API requires different kinds of permissions for each of its methods.</span></span> <span data-ttu-id="fba4a-120">Zie het artikel van de betreffende methode voor meer informatie over vereiste machtigingen.</span><span class="sxs-lookup"><span data-stu-id="fba4a-120">For more information about required permissions, see the respective method's article.</span></span>

## <a name="methods"></a><span data-ttu-id="fba4a-121">Methoden</span><span class="sxs-lookup"><span data-stu-id="fba4a-121">Methods</span></span>

<span data-ttu-id="fba4a-122">Methode</span><span class="sxs-lookup"><span data-stu-id="fba4a-122">Method</span></span> | <span data-ttu-id="fba4a-123">Retourtype</span><span class="sxs-lookup"><span data-stu-id="fba4a-123">Return Type</span></span> | <span data-ttu-id="fba4a-124">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="fba4a-124">Description</span></span>
-|-|-
[<span data-ttu-id="fba4a-125">Lijst met incidenten</span><span class="sxs-lookup"><span data-stu-id="fba4a-125">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="fba4a-126">[Lijst met incidenten](api-incident.md)</span><span class="sxs-lookup"><span data-stu-id="fba4a-126">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="fba4a-127">Krijg een lijst met incidenten.</span><span class="sxs-lookup"><span data-stu-id="fba4a-127">Get a list of incidents.</span></span>
[<span data-ttu-id="fba4a-128">Incident bijwerken</span><span class="sxs-lookup"><span data-stu-id="fba4a-128">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="fba4a-129">incident</span><span class="sxs-lookup"><span data-stu-id="fba4a-129">Incident</span></span>](api-incident.md) | <span data-ttu-id="fba4a-130">Een specifiek incident bijwerken.</span><span class="sxs-lookup"><span data-stu-id="fba4a-130">Update a specific incident.</span></span>

## <a name="request-body-response-and-examples"></a><span data-ttu-id="fba4a-131">Hoofdtekst, antwoord en voorbeelden aanvragen</span><span class="sxs-lookup"><span data-stu-id="fba4a-131">Request body, response, and examples</span></span>

<span data-ttu-id="fba4a-132">Raadpleeg de betreffende methodeartikelen voor meer informatie over het maken van een aanvraag of het parseren van een antwoord, en voor praktische voorbeelden.</span><span class="sxs-lookup"><span data-stu-id="fba4a-132">Refer to the respective method articles for more details on how to construct a request or parse a response, and for practical examples.</span></span>

## <a name="common-properties"></a><span data-ttu-id="fba4a-133">Gemeenschappelijke eigenschappen</span><span class="sxs-lookup"><span data-stu-id="fba4a-133">Common properties</span></span>

<span data-ttu-id="fba4a-134">Eigenschap</span><span class="sxs-lookup"><span data-stu-id="fba4a-134">Property</span></span> | <span data-ttu-id="fba4a-135">Type</span><span class="sxs-lookup"><span data-stu-id="fba4a-135">Type</span></span> | <span data-ttu-id="fba4a-136">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="fba4a-136">Description</span></span>
-|-|-
<span data-ttu-id="fba4a-137">incidentId</span><span class="sxs-lookup"><span data-stu-id="fba4a-137">incidentId</span></span> | <span data-ttu-id="fba4a-138">lang</span><span class="sxs-lookup"><span data-stu-id="fba4a-138">long</span></span> | <span data-ttu-id="fba4a-139">Unieke ID voor incidenten.</span><span class="sxs-lookup"><span data-stu-id="fba4a-139">Incident unique ID.</span></span>
<span data-ttu-id="fba4a-140">omleidingIncidentId</span><span class="sxs-lookup"><span data-stu-id="fba4a-140">redirectIncidentId</span></span> | <span data-ttu-id="fba4a-141">nullable lang</span><span class="sxs-lookup"><span data-stu-id="fba4a-141">nullable long</span></span> | <span data-ttu-id="fba4a-142">De incident-ID waaraan het huidige incident is samengevoegd.</span><span class="sxs-lookup"><span data-stu-id="fba4a-142">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="fba4a-143">incidentNaam</span><span class="sxs-lookup"><span data-stu-id="fba4a-143">incidentName</span></span> | <span data-ttu-id="fba4a-144">snaar</span><span class="sxs-lookup"><span data-stu-id="fba4a-144">string</span></span> | <span data-ttu-id="fba4a-145">De naam van het incident.</span><span class="sxs-lookup"><span data-stu-id="fba4a-145">The name of the Incident.</span></span>
<span data-ttu-id="fba4a-146">gemaaktTijd</span><span class="sxs-lookup"><span data-stu-id="fba4a-146">createdTime</span></span> | <span data-ttu-id="fba4a-147">DatumTimeOffset</span><span class="sxs-lookup"><span data-stu-id="fba4a-147">DateTimeOffset</span></span> | <span data-ttu-id="fba4a-148">De datum en tijd (in UTC) waarop het incident is gemaakt.</span><span class="sxs-lookup"><span data-stu-id="fba4a-148">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="fba4a-149">laatsteUpdateTime</span><span class="sxs-lookup"><span data-stu-id="fba4a-149">lastUpdateTime</span></span> | <span data-ttu-id="fba4a-150">DatumTimeOffset</span><span class="sxs-lookup"><span data-stu-id="fba4a-150">DateTimeOffset</span></span> | <span data-ttu-id="fba4a-151">De datum en tijd (in UTC) van het incident zijn voor het laatst bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="fba4a-151">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="fba4a-152">toegewezenTo</span><span class="sxs-lookup"><span data-stu-id="fba4a-152">assignedTo</span></span> | <span data-ttu-id="fba4a-153">snaar</span><span class="sxs-lookup"><span data-stu-id="fba4a-153">string</span></span> | <span data-ttu-id="fba4a-154">Eigenaar van het incident.</span><span class="sxs-lookup"><span data-stu-id="fba4a-154">Owner of the Incident.</span></span>
<span data-ttu-id="fba4a-155">strengheid</span><span class="sxs-lookup"><span data-stu-id="fba4a-155">severity</span></span> | <span data-ttu-id="fba4a-156">Enum</span><span class="sxs-lookup"><span data-stu-id="fba4a-156">Enum</span></span> | <span data-ttu-id="fba4a-157">Ernst van het incident.</span><span class="sxs-lookup"><span data-stu-id="fba4a-157">Severity of the Incident.</span></span> <span data-ttu-id="fba4a-158">Mogelijke waarden zijn: ```UnSpecified``` , , , , en ```Informational``` ```Low``` ```Medium``` ```High``` .</span><span class="sxs-lookup"><span data-stu-id="fba4a-158">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium```, and ```High```.</span></span>
<span data-ttu-id="fba4a-159">status</span><span class="sxs-lookup"><span data-stu-id="fba4a-159">status</span></span> | <span data-ttu-id="fba4a-160">Enum</span><span class="sxs-lookup"><span data-stu-id="fba4a-160">Enum</span></span> | <span data-ttu-id="fba4a-161">Hiermee geeft u de huidige status van het incident op.</span><span class="sxs-lookup"><span data-stu-id="fba4a-161">Specifies the current status of the incident.</span></span> <span data-ttu-id="fba4a-162">Mogelijke waarden zijn: ```Active``` ```Resolved``` , , en ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="fba4a-162">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="fba4a-163">classificatie</span><span class="sxs-lookup"><span data-stu-id="fba4a-163">classification</span></span> | <span data-ttu-id="fba4a-164">Enum</span><span class="sxs-lookup"><span data-stu-id="fba4a-164">Enum</span></span> | <span data-ttu-id="fba4a-165">Specificatie van het incident.</span><span class="sxs-lookup"><span data-stu-id="fba4a-165">Specification of the incident.</span></span> <span data-ttu-id="fba4a-166">Mogelijke waarden zijn: ```Unknown``` ```FalsePositive``` , , ```TruePositive``` .</span><span class="sxs-lookup"><span data-stu-id="fba4a-166">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="fba4a-167">vastberadenheid</span><span class="sxs-lookup"><span data-stu-id="fba4a-167">determination</span></span> | <span data-ttu-id="fba4a-168">Enum</span><span class="sxs-lookup"><span data-stu-id="fba4a-168">Enum</span></span> | <span data-ttu-id="fba4a-169">Hiermee geeft u de bepaling van het incident op.</span><span class="sxs-lookup"><span data-stu-id="fba4a-169">Specifies the determination of the incident.</span></span> <span data-ttu-id="fba4a-170">Mogelijke waarden zijn: ```NotAvailable``` , , , , , ```Apt``` ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` ```UnwantedSoftware``` ```Other``` .</span><span class="sxs-lookup"><span data-stu-id="fba4a-170">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="fba4a-171">Tags</span><span class="sxs-lookup"><span data-stu-id="fba4a-171">tags</span></span> | <span data-ttu-id="fba4a-172">tekenreekslijst</span><span class="sxs-lookup"><span data-stu-id="fba4a-172">string List</span></span> | <span data-ttu-id="fba4a-173">Lijst met incidenttags.</span><span class="sxs-lookup"><span data-stu-id="fba4a-173">List of Incident tags.</span></span>
<span data-ttu-id="fba4a-174">Opmerkingen</span><span class="sxs-lookup"><span data-stu-id="fba4a-174">comments</span></span> | <span data-ttu-id="fba4a-175">Lijst met incidentopmerkingen</span><span class="sxs-lookup"><span data-stu-id="fba4a-175">List of incident comments</span></span> | <span data-ttu-id="fba4a-176">Incident Opmerkingsobject bevat: commentaartekenreeks, createdBy-tekenreeks en createTime-datumtijd.</span><span class="sxs-lookup"><span data-stu-id="fba4a-176">Incident Comment object contains: comment string, createdBy string, and createTime date time.</span></span>
<span data-ttu-id="fba4a-177">Waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="fba4a-177">alerts</span></span> | <span data-ttu-id="fba4a-178">Waarschuwingslijst</span><span class="sxs-lookup"><span data-stu-id="fba4a-178">Alert List</span></span> | <span data-ttu-id="fba4a-179">Lijst met gerelateerde waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="fba4a-179">List of related alerts.</span></span> <span data-ttu-id="fba4a-180">Zie voorbeelden bij [API-documentatie voor lijstincidenten.](api-list-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="fba4a-180">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>

## <a name="related-articles"></a><span data-ttu-id="fba4a-181">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="fba4a-181">Related articles</span></span>

- [<span data-ttu-id="fba4a-182">Microsoft 365 Defender API's overzicht</span><span class="sxs-lookup"><span data-stu-id="fba4a-182">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="fba4a-183">Overzicht incidenten</span><span class="sxs-lookup"><span data-stu-id="fba4a-183">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="fba4a-184">Api voor lijstincidenten</span><span class="sxs-lookup"><span data-stu-id="fba4a-184">List incidents API</span></span>](api-list-incidents.md)
- [<span data-ttu-id="fba4a-185">Api voor incident bijwerken</span><span class="sxs-lookup"><span data-stu-id="fba4a-185">Update incident API</span></span>](api-update-incidents.md)
