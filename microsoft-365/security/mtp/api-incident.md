---
title: Microsoft 365 Defender-incidenten API's en het type incidentresource
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 37413c3c7458527e90d4657ddfb3afb058e1dfaa
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928352"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incident-resource-type"></a><span data-ttu-id="3daaf-104">Api voor Microsoft 365 Defender-incidenten en het type incidentresource</span><span class="sxs-lookup"><span data-stu-id="3daaf-104">Microsoft 365 Defender incidents API and the incident resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="3daaf-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="3daaf-105">**Applies to:**</span></span>

- <span data-ttu-id="3daaf-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3daaf-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3daaf-107">Sommige informatie heeft betrekking op vooraf uitgebracht product dat aanzienlijk kan worden gewijzigd voordat het in de handel wordt gebracht.</span><span class="sxs-lookup"><span data-stu-id="3daaf-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="3daaf-108">Microsoft biedt geen garanties, uitdrukkelijk of impliciet, met betrekking tot de informatie die hier wordt be gegeven.</span><span class="sxs-lookup"><span data-stu-id="3daaf-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="3daaf-109">Een [incident](incidents-overview.md) is een verzameling gerelateerde waarschuwingen die een aanval helpen beschrijven.</span><span class="sxs-lookup"><span data-stu-id="3daaf-109">An [incident](incidents-overview.md) is a collection of related alerts that help describe an attack.</span></span> <span data-ttu-id="3daaf-110">Gebeurtenissen van verschillende entiteiten in uw organisatie worden automatisch samengevoegd door Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="3daaf-110">Events from different entities in your organization are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="3daaf-111">U kunt de INCIDENTEN-API gebruiken om programmatisch toegang te krijgen tot de incidenten en gerelateerde waarschuwingen van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="3daaf-111">You can use the incidents API to programatically access your organization's incidents and related alerts.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="3daaf-112">Quota en resourcetoewijzing</span><span class="sxs-lookup"><span data-stu-id="3daaf-112">Quotas and resource allocation</span></span>

<span data-ttu-id="3daaf-113">U kunt maximaal 50 oproepen per minuut of 1500 oproepen per uur aanvragen.</span><span class="sxs-lookup"><span data-stu-id="3daaf-113">You can request up to 50 calls per minute or 1500 calls per hour.</span></span> <span data-ttu-id="3daaf-114">Elke methode heeft ook een eigen quota.</span><span class="sxs-lookup"><span data-stu-id="3daaf-114">Each method also has its own quotas.</span></span> <span data-ttu-id="3daaf-115">Zie het desbetreffende artikel over de methode die u wilt gebruiken voor meer informatie over methodespecifieke quota's.</span><span class="sxs-lookup"><span data-stu-id="3daaf-115">For more information on method-specific quotas, see the respective article for the method you want to use.</span></span>

<span data-ttu-id="3daaf-116">Een HTTP-antwoordcode geeft aan dat u een quotum hebt bereikt, hetzij door het aantal verzonden aanvragen of door de toegewezen `429` lopende tijd.</span><span class="sxs-lookup"><span data-stu-id="3daaf-116">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="3daaf-117">De reactie zelf bevat de tijd tot het quotum dat u hebt bereikt, wordt opnieuw ingesteld.</span><span class="sxs-lookup"><span data-stu-id="3daaf-117">The response body will include the time until the quota you reached will be reset.</span></span>

## <a name="permissions"></a><span data-ttu-id="3daaf-118">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="3daaf-118">Permissions</span></span>

<span data-ttu-id="3daaf-119">De API voor incidenten vereist verschillende soorten machtigingen voor elk van de methoden.</span><span class="sxs-lookup"><span data-stu-id="3daaf-119">The incidents API requires different kinds of permissions for each of its methods.</span></span> <span data-ttu-id="3daaf-120">Zie het artikel van de desbetreffende methode voor meer informatie over vereiste machtigingen.</span><span class="sxs-lookup"><span data-stu-id="3daaf-120">For more information about required permissions, see the respective method's article.</span></span>

## <a name="methods"></a><span data-ttu-id="3daaf-121">Methoden</span><span class="sxs-lookup"><span data-stu-id="3daaf-121">Methods</span></span>

<span data-ttu-id="3daaf-122">Methode</span><span class="sxs-lookup"><span data-stu-id="3daaf-122">Method</span></span> | <span data-ttu-id="3daaf-123">Type retournering</span><span class="sxs-lookup"><span data-stu-id="3daaf-123">Return Type</span></span> | <span data-ttu-id="3daaf-124">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="3daaf-124">Description</span></span>
-|-|-
[<span data-ttu-id="3daaf-125">Lijst met incidenten</span><span class="sxs-lookup"><span data-stu-id="3daaf-125">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="3daaf-126">[Lijst met incidenten](api-incident.md)</span><span class="sxs-lookup"><span data-stu-id="3daaf-126">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="3daaf-127">Hier wordt een lijst met incidenten weergegeven.</span><span class="sxs-lookup"><span data-stu-id="3daaf-127">Get a list of incidents.</span></span>
[<span data-ttu-id="3daaf-128">Incident bijwerken</span><span class="sxs-lookup"><span data-stu-id="3daaf-128">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="3daaf-129">Incident</span><span class="sxs-lookup"><span data-stu-id="3daaf-129">Incident</span></span>](api-incident.md) | <span data-ttu-id="3daaf-130">Een specifiek incident bijwerken.</span><span class="sxs-lookup"><span data-stu-id="3daaf-130">Update a specific incident.</span></span>

## <a name="request-body-response-and-examples"></a><span data-ttu-id="3daaf-131">De body, het antwoord en voorbeelden aanvragen</span><span class="sxs-lookup"><span data-stu-id="3daaf-131">Request body, response, and examples</span></span>

<span data-ttu-id="3daaf-132">Raadpleeg de artikelen met de desbetreffende methode voor meer informatie over het maken van een aanvraag of het parseren van een antwoord en voor praktische voorbeelden.</span><span class="sxs-lookup"><span data-stu-id="3daaf-132">Refer to the respective method articles for more details on how to construct a request or parse a response, and for practical examples.</span></span>

## <a name="common-properties"></a><span data-ttu-id="3daaf-133">Algemene eigenschappen</span><span class="sxs-lookup"><span data-stu-id="3daaf-133">Common properties</span></span>

<span data-ttu-id="3daaf-134">Eigenschap</span><span class="sxs-lookup"><span data-stu-id="3daaf-134">Property</span></span> | <span data-ttu-id="3daaf-135">Type</span><span class="sxs-lookup"><span data-stu-id="3daaf-135">Type</span></span> | <span data-ttu-id="3daaf-136">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="3daaf-136">Description</span></span>
-|-|-
<span data-ttu-id="3daaf-137">incidentId</span><span class="sxs-lookup"><span data-stu-id="3daaf-137">incidentId</span></span> | <span data-ttu-id="3daaf-138">lang</span><span class="sxs-lookup"><span data-stu-id="3daaf-138">long</span></span> | <span data-ttu-id="3daaf-139">Unieke id voor incident.</span><span class="sxs-lookup"><span data-stu-id="3daaf-139">Incident unique ID.</span></span>
<span data-ttu-id="3daaf-140">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="3daaf-140">redirectIncidentId</span></span> | <span data-ttu-id="3daaf-141">nullable long</span><span class="sxs-lookup"><span data-stu-id="3daaf-141">nullable long</span></span> | <span data-ttu-id="3daaf-142">De incident-id die het huidige incident is samengevoegd.</span><span class="sxs-lookup"><span data-stu-id="3daaf-142">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="3daaf-143">incidentName</span><span class="sxs-lookup"><span data-stu-id="3daaf-143">incidentName</span></span> | <span data-ttu-id="3daaf-144">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="3daaf-144">string</span></span> | <span data-ttu-id="3daaf-145">De naam van het incident.</span><span class="sxs-lookup"><span data-stu-id="3daaf-145">The name of the Incident.</span></span>
<span data-ttu-id="3daaf-146">createdTime</span><span class="sxs-lookup"><span data-stu-id="3daaf-146">createdTime</span></span> | <span data-ttu-id="3daaf-147">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="3daaf-147">DateTimeOffset</span></span> | <span data-ttu-id="3daaf-148">De datum en tijd (in UTC) het incident is gemaakt.</span><span class="sxs-lookup"><span data-stu-id="3daaf-148">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="3daaf-149">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="3daaf-149">lastUpdateTime</span></span> | <span data-ttu-id="3daaf-150">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="3daaf-150">DateTimeOffset</span></span> | <span data-ttu-id="3daaf-151">De datum en tijd (in UTC) het incident is voor het laatst bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="3daaf-151">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="3daaf-152">toegewezen Aan</span><span class="sxs-lookup"><span data-stu-id="3daaf-152">assignedTo</span></span> | <span data-ttu-id="3daaf-153">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="3daaf-153">string</span></span> | <span data-ttu-id="3daaf-154">Eigenaar van het incident.</span><span class="sxs-lookup"><span data-stu-id="3daaf-154">Owner of the Incident.</span></span>
<span data-ttu-id="3daaf-155">ernst</span><span class="sxs-lookup"><span data-stu-id="3daaf-155">severity</span></span> | <span data-ttu-id="3daaf-156">Enum</span><span class="sxs-lookup"><span data-stu-id="3daaf-156">Enum</span></span> | <span data-ttu-id="3daaf-157">Ernst van het incident.</span><span class="sxs-lookup"><span data-stu-id="3daaf-157">Severity of the Incident.</span></span> <span data-ttu-id="3daaf-158">Mogelijke waarden zijn: ```UnSpecified``` ```Informational``` , , en ```Low``` ```Medium``` ```High``` .</span><span class="sxs-lookup"><span data-stu-id="3daaf-158">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium```, and ```High```.</span></span>
<span data-ttu-id="3daaf-159">status</span><span class="sxs-lookup"><span data-stu-id="3daaf-159">status</span></span> | <span data-ttu-id="3daaf-160">Enum</span><span class="sxs-lookup"><span data-stu-id="3daaf-160">Enum</span></span> | <span data-ttu-id="3daaf-161">Hiermee geeft u de huidige status van het incident op.</span><span class="sxs-lookup"><span data-stu-id="3daaf-161">Specifies the current status of the incident.</span></span> <span data-ttu-id="3daaf-162">Mogelijke waarden zijn: ```Active``` ```Resolved``` en ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="3daaf-162">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="3daaf-163">classificatie</span><span class="sxs-lookup"><span data-stu-id="3daaf-163">classification</span></span> | <span data-ttu-id="3daaf-164">Enum</span><span class="sxs-lookup"><span data-stu-id="3daaf-164">Enum</span></span> | <span data-ttu-id="3daaf-165">Specificatie van het incident.</span><span class="sxs-lookup"><span data-stu-id="3daaf-165">Specification of the incident.</span></span> <span data-ttu-id="3daaf-166">Mogelijke waarden zijn: ```Unknown``` ```FalsePositive``` , ```TruePositive``` .</span><span class="sxs-lookup"><span data-stu-id="3daaf-166">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="3daaf-167">besluit</span><span class="sxs-lookup"><span data-stu-id="3daaf-167">determination</span></span> | <span data-ttu-id="3daaf-168">Enum</span><span class="sxs-lookup"><span data-stu-id="3daaf-168">Enum</span></span> | <span data-ttu-id="3daaf-169">Bepaalt de vaststelling van het incident.</span><span class="sxs-lookup"><span data-stu-id="3daaf-169">Specifies the determination of the incident.</span></span> <span data-ttu-id="3daaf-170">Mogelijke waarden zijn: ```NotAvailable``` ```Apt``` , , , ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` ```UnwantedSoftware``` . ```Other```</span><span class="sxs-lookup"><span data-stu-id="3daaf-170">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="3daaf-171">tags</span><span class="sxs-lookup"><span data-stu-id="3daaf-171">tags</span></span> | <span data-ttu-id="3daaf-172">lijst met tekenreeksen</span><span class="sxs-lookup"><span data-stu-id="3daaf-172">string List</span></span> | <span data-ttu-id="3daaf-173">Lijst met incidentlabels.</span><span class="sxs-lookup"><span data-stu-id="3daaf-173">List of Incident tags.</span></span>
<span data-ttu-id="3daaf-174">waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="3daaf-174">alerts</span></span> | <span data-ttu-id="3daaf-175">Lijst met waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="3daaf-175">Alert List</span></span> | <span data-ttu-id="3daaf-176">Lijst met gerelateerde waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="3daaf-176">List of related alerts.</span></span> <span data-ttu-id="3daaf-177">Bekijk voorbeelden van [API-documentatie voor lijstincidenten.](api-list-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="3daaf-177">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>

## <a name="related-articles"></a><span data-ttu-id="3daaf-178">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="3daaf-178">Related articles</span></span>

- [<span data-ttu-id="3daaf-179">Overzicht van Microsoft 365 Defender API's</span><span class="sxs-lookup"><span data-stu-id="3daaf-179">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="3daaf-180">Overzicht van incidenten</span><span class="sxs-lookup"><span data-stu-id="3daaf-180">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="3daaf-181">Api voor lijstincidenten</span><span class="sxs-lookup"><span data-stu-id="3daaf-181">List incidents API</span></span>](api-list-incidents.md)
- [<span data-ttu-id="3daaf-182">Update-incident-API</span><span class="sxs-lookup"><span data-stu-id="3daaf-182">Update incident API</span></span>](api-update-incidents.md)
