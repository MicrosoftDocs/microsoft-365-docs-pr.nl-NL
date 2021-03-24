---
title: Api's voor Microsoft 365 Defender-incidenten en het type incidentresource
description: Meer informatie over de methoden en eigenschappen van het type incidentresource in Microsoft 365 Defender
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
ms.openlocfilehash: 0a9022c0448ae0ddc16dc996ca93075abf6b2857
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056673"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incident-resource-type"></a><span data-ttu-id="545e9-104">Microsoft 365 Defender-incidenten API en het type incidentresource</span><span class="sxs-lookup"><span data-stu-id="545e9-104">Microsoft 365 Defender incidents API and the incident resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="545e9-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="545e9-105">**Applies to:**</span></span>

- <span data-ttu-id="545e9-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="545e9-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="545e9-107">Sommige informatie is gerelateerd aan voorlopige productversies die mogelijk aanzienlijk gewijzigd worden voordat ze commercieel gepubliceerd worden.</span><span class="sxs-lookup"><span data-stu-id="545e9-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="545e9-108">Microsoft geeft geen garantie, uitdrukkelijk of impliciet, met betrekking tot de informatie die hier wordt beschreven.</span><span class="sxs-lookup"><span data-stu-id="545e9-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="545e9-109">Een [incident](incidents-overview.md) is een verzameling gerelateerde waarschuwingen die helpen bij het beschrijven van een aanval.</span><span class="sxs-lookup"><span data-stu-id="545e9-109">An [incident](incidents-overview.md) is a collection of related alerts that help describe an attack.</span></span> <span data-ttu-id="545e9-110">Gebeurtenissen uit verschillende entiteiten in uw organisatie worden automatisch samengevoegd door Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="545e9-110">Events from different entities in your organization are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="545e9-111">U kunt de API voor incidenten gebruiken om programmaatically toegang te krijgen tot de incidenten en gerelateerde waarschuwingen van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="545e9-111">You can use the incidents API to programatically access your organization's incidents and related alerts.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="545e9-112">Quota en resourcetoewijzing</span><span class="sxs-lookup"><span data-stu-id="545e9-112">Quotas and resource allocation</span></span>

<span data-ttu-id="545e9-113">U kunt maximaal 50 oproepen per minuut of 1500 oproepen per uur aanvragen.</span><span class="sxs-lookup"><span data-stu-id="545e9-113">You can request up to 50 calls per minute or 1500 calls per hour.</span></span> <span data-ttu-id="545e9-114">Elke methode heeft ook een eigen quotum.</span><span class="sxs-lookup"><span data-stu-id="545e9-114">Each method also has its own quotas.</span></span> <span data-ttu-id="545e9-115">Zie het betreffende artikel voor de methode die u wilt gebruiken voor meer informatie over methodespecifieke quota.</span><span class="sxs-lookup"><span data-stu-id="545e9-115">For more information on method-specific quotas, see the respective article for the method you want to use.</span></span>

<span data-ttu-id="545e9-116">Een HTTP-antwoordcode geeft aan dat u een quotum hebt bereikt, hetzij op het aantal verzonden aanvragen, hetzij door de toegewezen `429` gebruikstijd.</span><span class="sxs-lookup"><span data-stu-id="545e9-116">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="545e9-117">De reactie body bevat de tijd totdat het quotum dat u hebt bereikt, opnieuw wordt ingesteld.</span><span class="sxs-lookup"><span data-stu-id="545e9-117">The response body will include the time until the quota you reached will be reset.</span></span>

## <a name="permissions"></a><span data-ttu-id="545e9-118">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="545e9-118">Permissions</span></span>

<span data-ttu-id="545e9-119">Voor de API voor incidenten zijn verschillende soorten machtigingen voor elk van de methoden vereist.</span><span class="sxs-lookup"><span data-stu-id="545e9-119">The incidents API requires different kinds of permissions for each of its methods.</span></span> <span data-ttu-id="545e9-120">Zie het artikel van de betreffende methode voor meer informatie over vereiste machtigingen.</span><span class="sxs-lookup"><span data-stu-id="545e9-120">For more information about required permissions, see the respective method's article.</span></span>

## <a name="methods"></a><span data-ttu-id="545e9-121">Methoden</span><span class="sxs-lookup"><span data-stu-id="545e9-121">Methods</span></span>

<span data-ttu-id="545e9-122">Methode</span><span class="sxs-lookup"><span data-stu-id="545e9-122">Method</span></span> | <span data-ttu-id="545e9-123">Retourtype</span><span class="sxs-lookup"><span data-stu-id="545e9-123">Return Type</span></span> | <span data-ttu-id="545e9-124">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="545e9-124">Description</span></span>
-|-|-
[<span data-ttu-id="545e9-125">Lijst met incidenten</span><span class="sxs-lookup"><span data-stu-id="545e9-125">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="545e9-126">[Lijst met incidenten](api-incident.md)</span><span class="sxs-lookup"><span data-stu-id="545e9-126">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="545e9-127">Een lijst met incidenten.</span><span class="sxs-lookup"><span data-stu-id="545e9-127">Get a list of incidents.</span></span>
[<span data-ttu-id="545e9-128">Incident bijwerken</span><span class="sxs-lookup"><span data-stu-id="545e9-128">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="545e9-129">Incident</span><span class="sxs-lookup"><span data-stu-id="545e9-129">Incident</span></span>](api-incident.md) | <span data-ttu-id="545e9-130">Een specifiek incident bijwerken.</span><span class="sxs-lookup"><span data-stu-id="545e9-130">Update a specific incident.</span></span>

## <a name="request-body-response-and-examples"></a><span data-ttu-id="545e9-131">Body, antwoord en voorbeelden aanvragen</span><span class="sxs-lookup"><span data-stu-id="545e9-131">Request body, response, and examples</span></span>

<span data-ttu-id="545e9-132">Raadpleeg de betreffende methodeartikelen voor meer informatie over het maken van een aanvraag of het parseren van een antwoord en voor praktische voorbeelden.</span><span class="sxs-lookup"><span data-stu-id="545e9-132">Refer to the respective method articles for more details on how to construct a request or parse a response, and for practical examples.</span></span>

## <a name="common-properties"></a><span data-ttu-id="545e9-133">Veelgebruikte eigenschappen</span><span class="sxs-lookup"><span data-stu-id="545e9-133">Common properties</span></span>

<span data-ttu-id="545e9-134">Eigenschap</span><span class="sxs-lookup"><span data-stu-id="545e9-134">Property</span></span> | <span data-ttu-id="545e9-135">Type</span><span class="sxs-lookup"><span data-stu-id="545e9-135">Type</span></span> | <span data-ttu-id="545e9-136">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="545e9-136">Description</span></span>
-|-|-
<span data-ttu-id="545e9-137">incidentId</span><span class="sxs-lookup"><span data-stu-id="545e9-137">incidentId</span></span> | <span data-ttu-id="545e9-138">lang</span><span class="sxs-lookup"><span data-stu-id="545e9-138">long</span></span> | <span data-ttu-id="545e9-139">Unieke id voor incidenten.</span><span class="sxs-lookup"><span data-stu-id="545e9-139">Incident unique ID.</span></span>
<span data-ttu-id="545e9-140">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="545e9-140">redirectIncidentId</span></span> | <span data-ttu-id="545e9-141">nullable long</span><span class="sxs-lookup"><span data-stu-id="545e9-141">nullable long</span></span> | <span data-ttu-id="545e9-142">De incident-id waarbij het huidige incident is samengevoegd.</span><span class="sxs-lookup"><span data-stu-id="545e9-142">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="545e9-143">incidentName</span><span class="sxs-lookup"><span data-stu-id="545e9-143">incidentName</span></span> | <span data-ttu-id="545e9-144">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="545e9-144">string</span></span> | <span data-ttu-id="545e9-145">De naam van het incident.</span><span class="sxs-lookup"><span data-stu-id="545e9-145">The name of the Incident.</span></span>
<span data-ttu-id="545e9-146">createdTime</span><span class="sxs-lookup"><span data-stu-id="545e9-146">createdTime</span></span> | <span data-ttu-id="545e9-147">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="545e9-147">DateTimeOffset</span></span> | <span data-ttu-id="545e9-148">De datum en tijd (in UTC) het incident is gemaakt.</span><span class="sxs-lookup"><span data-stu-id="545e9-148">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="545e9-149">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="545e9-149">lastUpdateTime</span></span> | <span data-ttu-id="545e9-150">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="545e9-150">DateTimeOffset</span></span> | <span data-ttu-id="545e9-151">De datum en tijd (in UTC) het incident is voor het laatst bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="545e9-151">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="545e9-152">toegewezenTo</span><span class="sxs-lookup"><span data-stu-id="545e9-152">assignedTo</span></span> | <span data-ttu-id="545e9-153">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="545e9-153">string</span></span> | <span data-ttu-id="545e9-154">Eigenaar van het incident.</span><span class="sxs-lookup"><span data-stu-id="545e9-154">Owner of the Incident.</span></span>
<span data-ttu-id="545e9-155">ernst</span><span class="sxs-lookup"><span data-stu-id="545e9-155">severity</span></span> | <span data-ttu-id="545e9-156">Enum</span><span class="sxs-lookup"><span data-stu-id="545e9-156">Enum</span></span> | <span data-ttu-id="545e9-157">Ernst van het incident.</span><span class="sxs-lookup"><span data-stu-id="545e9-157">Severity of the Incident.</span></span> <span data-ttu-id="545e9-158">Mogelijke waarden zijn: ```UnSpecified``` , , , en ```Informational``` ```Low``` ```Medium``` ```High``` .</span><span class="sxs-lookup"><span data-stu-id="545e9-158">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium```, and ```High```.</span></span>
<span data-ttu-id="545e9-159">status</span><span class="sxs-lookup"><span data-stu-id="545e9-159">status</span></span> | <span data-ttu-id="545e9-160">Enum</span><span class="sxs-lookup"><span data-stu-id="545e9-160">Enum</span></span> | <span data-ttu-id="545e9-161">Hiermee geeft u de huidige status van het incident op.</span><span class="sxs-lookup"><span data-stu-id="545e9-161">Specifies the current status of the incident.</span></span> <span data-ttu-id="545e9-162">Mogelijke waarden zijn: ```Active``` ```Resolved``` , en ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="545e9-162">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="545e9-163">classificatie</span><span class="sxs-lookup"><span data-stu-id="545e9-163">classification</span></span> | <span data-ttu-id="545e9-164">Enum</span><span class="sxs-lookup"><span data-stu-id="545e9-164">Enum</span></span> | <span data-ttu-id="545e9-165">Specificatie van het incident.</span><span class="sxs-lookup"><span data-stu-id="545e9-165">Specification of the incident.</span></span> <span data-ttu-id="545e9-166">Mogelijke waarden zijn: ```Unknown``` ```FalsePositive``` , , ```TruePositive``` .</span><span class="sxs-lookup"><span data-stu-id="545e9-166">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="545e9-167">bepaling</span><span class="sxs-lookup"><span data-stu-id="545e9-167">determination</span></span> | <span data-ttu-id="545e9-168">Enum</span><span class="sxs-lookup"><span data-stu-id="545e9-168">Enum</span></span> | <span data-ttu-id="545e9-169">Hiermee geeft u de bepaling van het incident op.</span><span class="sxs-lookup"><span data-stu-id="545e9-169">Specifies the determination of the incident.</span></span> <span data-ttu-id="545e9-170">Mogelijke waarden zijn: ```NotAvailable``` , , , , , , ```Apt``` ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` ```UnwantedSoftware``` . ```Other```</span><span class="sxs-lookup"><span data-stu-id="545e9-170">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="545e9-171">tags</span><span class="sxs-lookup"><span data-stu-id="545e9-171">tags</span></span> | <span data-ttu-id="545e9-172">lijst met tekenreeksen</span><span class="sxs-lookup"><span data-stu-id="545e9-172">string List</span></span> | <span data-ttu-id="545e9-173">Lijst met incidentlabels.</span><span class="sxs-lookup"><span data-stu-id="545e9-173">List of Incident tags.</span></span>
<span data-ttu-id="545e9-174">waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="545e9-174">alerts</span></span> | <span data-ttu-id="545e9-175">Lijst met waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="545e9-175">Alert List</span></span> | <span data-ttu-id="545e9-176">Lijst met gerelateerde waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="545e9-176">List of related alerts.</span></span> <span data-ttu-id="545e9-177">Zie voorbeelden van [API-documentatie lijstincidenten.](api-list-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="545e9-177">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>

## <a name="related-articles"></a><span data-ttu-id="545e9-178">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="545e9-178">Related articles</span></span>

- [<span data-ttu-id="545e9-179">Overzicht van Microsoft 365 Defender-API's</span><span class="sxs-lookup"><span data-stu-id="545e9-179">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="545e9-180">Overzicht van incidenten</span><span class="sxs-lookup"><span data-stu-id="545e9-180">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="545e9-181">Lijstincidenten API</span><span class="sxs-lookup"><span data-stu-id="545e9-181">List incidents API</span></span>](api-list-incidents.md)
- [<span data-ttu-id="545e9-182">Api voor incidenten bijwerken</span><span class="sxs-lookup"><span data-stu-id="545e9-182">Update incident API</span></span>](api-update-incidents.md)
