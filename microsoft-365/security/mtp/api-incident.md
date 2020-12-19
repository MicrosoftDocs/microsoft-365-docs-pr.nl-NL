---
title: De Api's van Microsoft 365 Defender en het brontype incident
description: Meer informatie over de methoden en eigenschappen van het type incident bron in Microsoft 365 Defender
keywords: incident, incidenten, API
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 372c939f5eed29832725e6b048735040ca7391d6
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719332"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incident-resource-type"></a><span data-ttu-id="097a7-104">De API van Microsoft 365 Defender-incidenten en het brontype incident</span><span class="sxs-lookup"><span data-stu-id="097a7-104">Microsoft 365 Defender incidents API and the incident resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="097a7-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="097a7-105">**Applies to:**</span></span>

- <span data-ttu-id="097a7-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="097a7-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="097a7-107">Sommige informatie verhoudt zich tot een voorvrijgegeven product dat bij de commerciële versie van de commerciële versie mogelijk ingrijpend werd gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="097a7-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="097a7-108">Microsoft biedt geen garanties, expliciete of impliciete informatie met betrekking tot de informatie die u hier opgeeft.</span><span class="sxs-lookup"><span data-stu-id="097a7-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="097a7-109">Een [incident](incidents-overview.md) is een verzameling verwante waarschuwingen die een aanval kunnen beschrijven.</span><span class="sxs-lookup"><span data-stu-id="097a7-109">An [incident](incidents-overview.md) is a collection of related alerts that help describe an attack.</span></span> <span data-ttu-id="097a7-110">Gebeurtenissen van verschillende entiteiten in uw organisatie worden automatisch samengevoegd met Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="097a7-110">Events from different entities in your organization are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="097a7-111">U kunt de API incidenties gebruiken voor de programmatische toegang tot incidenten en verwante meldingen van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="097a7-111">You can use the incidents API to programatically access your organization's incidents and related alerts.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="097a7-112">Quota's en resources toewijzen</span><span class="sxs-lookup"><span data-stu-id="097a7-112">Quotas and resource allocation</span></span>

<span data-ttu-id="097a7-113">U kunt maximaal 50 oproepen per minuut en 1500 bellen per uur aanvragen.</span><span class="sxs-lookup"><span data-stu-id="097a7-113">You can request up to 50 calls per minute or 1500 calls per hour.</span></span> <span data-ttu-id="097a7-114">Elke methode heeft ook eigen quota's.</span><span class="sxs-lookup"><span data-stu-id="097a7-114">Each method also has its own quotas.</span></span> <span data-ttu-id="097a7-115">Zie voor meer informatie over bepaalde quota's de artikelen voor de methode die u wilt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="097a7-115">For more information on method-specific quotas, see the respective article for the method you want to use.</span></span>

<span data-ttu-id="097a7-116">Met een `429` HTTP-antwoordcode wordt aangegeven dat u een quotum hebt bereikt, hetzij op basis van het aantal ingediende aanvragen of over de beschikde periode.</span><span class="sxs-lookup"><span data-stu-id="097a7-116">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="097a7-117">De antwoordtekst omvat de tijd totdat het door u bereikte quotum opnieuw wordt ingesteld.</span><span class="sxs-lookup"><span data-stu-id="097a7-117">The response body will include the time until the quota you reached will be reset.</span></span>

## <a name="permissions"></a><span data-ttu-id="097a7-118">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="097a7-118">Permissions</span></span>

<span data-ttu-id="097a7-119">Voor de incidenten-API is verschillende soorten machtigingen vereist voor de verschillende methoden.</span><span class="sxs-lookup"><span data-stu-id="097a7-119">The incidents API requires different kinds of permissions for each of its methods.</span></span> <span data-ttu-id="097a7-120">Zie het artikel van de desbetreffende methode voor meer informatie over de vereiste machtigingen.</span><span class="sxs-lookup"><span data-stu-id="097a7-120">For more information about required permissions, see the respective method's article.</span></span>

## <a name="methods"></a><span data-ttu-id="097a7-121">Methode</span><span class="sxs-lookup"><span data-stu-id="097a7-121">Methods</span></span>

<span data-ttu-id="097a7-122">Methode</span><span class="sxs-lookup"><span data-stu-id="097a7-122">Method</span></span> | <span data-ttu-id="097a7-123">Type resultaat</span><span class="sxs-lookup"><span data-stu-id="097a7-123">Return Type</span></span> | <span data-ttu-id="097a7-124">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="097a7-124">Description</span></span>
-|-|-
[<span data-ttu-id="097a7-125">Lijst met incidenten</span><span class="sxs-lookup"><span data-stu-id="097a7-125">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="097a7-126">Lijst met [incidenten](api-incident.md)</span><span class="sxs-lookup"><span data-stu-id="097a7-126">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="097a7-127">Een lijst met incidenten weergeven.</span><span class="sxs-lookup"><span data-stu-id="097a7-127">Get a list of incidents.</span></span>
[<span data-ttu-id="097a7-128">Incident bijwerken</span><span class="sxs-lookup"><span data-stu-id="097a7-128">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="097a7-129">Voorval</span><span class="sxs-lookup"><span data-stu-id="097a7-129">Incident</span></span>](api-incident.md) | <span data-ttu-id="097a7-130">Een specifiek incident bijwerken.</span><span class="sxs-lookup"><span data-stu-id="097a7-130">Update a specific incident.</span></span>

## <a name="request-body-response-and-examples"></a><span data-ttu-id="097a7-131">Hoofdtekst, antwoord en voorbeelden aanvragen</span><span class="sxs-lookup"><span data-stu-id="097a7-131">Request body, response, and examples</span></span>

<span data-ttu-id="097a7-132">Raadpleeg de desbetreffende procedure artikelen voor meer informatie over het maken van een aanvraag of het parseren van een aanvraag, en voor praktische voorbeelden.</span><span class="sxs-lookup"><span data-stu-id="097a7-132">Refer to the respective method articles for more details on how to construct a request or parse a response, and for practical examples.</span></span>

## <a name="common-properties"></a><span data-ttu-id="097a7-133">Gemeenschappelijke eigenschappen</span><span class="sxs-lookup"><span data-stu-id="097a7-133">Common properties</span></span>

<span data-ttu-id="097a7-134">Eigenschap</span><span class="sxs-lookup"><span data-stu-id="097a7-134">Property</span></span> | <span data-ttu-id="097a7-135">Type</span><span class="sxs-lookup"><span data-stu-id="097a7-135">Type</span></span> | <span data-ttu-id="097a7-136">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="097a7-136">Description</span></span>
-|-|-
<span data-ttu-id="097a7-137">incidentId</span><span class="sxs-lookup"><span data-stu-id="097a7-137">incidentId</span></span> | <span data-ttu-id="097a7-138">lang</span><span class="sxs-lookup"><span data-stu-id="097a7-138">long</span></span> | <span data-ttu-id="097a7-139">Unieke ID van incident.</span><span class="sxs-lookup"><span data-stu-id="097a7-139">Incident unique ID.</span></span>
<span data-ttu-id="097a7-140">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="097a7-140">redirectIncidentId</span></span> | <span data-ttu-id="097a7-141">met nullen lang</span><span class="sxs-lookup"><span data-stu-id="097a7-141">nullable long</span></span> | <span data-ttu-id="097a7-142">De incident-ID waarmee het huidige incident is samengevoegd.</span><span class="sxs-lookup"><span data-stu-id="097a7-142">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="097a7-143">voorval</span><span class="sxs-lookup"><span data-stu-id="097a7-143">incidentName</span></span> | <span data-ttu-id="097a7-144">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="097a7-144">string</span></span> | <span data-ttu-id="097a7-145">De naam van het incident.</span><span class="sxs-lookup"><span data-stu-id="097a7-145">The name of the Incident.</span></span>
<span data-ttu-id="097a7-146">createdTime</span><span class="sxs-lookup"><span data-stu-id="097a7-146">createdTime</span></span> | <span data-ttu-id="097a7-147">Offset</span><span class="sxs-lookup"><span data-stu-id="097a7-147">DateTimeOffset</span></span> | <span data-ttu-id="097a7-148">De datum en tijd (in UTC) waarop het incident is gemaakt.</span><span class="sxs-lookup"><span data-stu-id="097a7-148">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="097a7-149">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="097a7-149">lastUpdateTime</span></span> | <span data-ttu-id="097a7-150">Offset</span><span class="sxs-lookup"><span data-stu-id="097a7-150">DateTimeOffset</span></span> | <span data-ttu-id="097a7-151">De datum en tijd (in UTC) waarop het incident voor het laatst is bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="097a7-151">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="097a7-152">ToegewezenAan</span><span class="sxs-lookup"><span data-stu-id="097a7-152">assignedTo</span></span> | <span data-ttu-id="097a7-153">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="097a7-153">string</span></span> | <span data-ttu-id="097a7-154">Eigenaar van het incident.</span><span class="sxs-lookup"><span data-stu-id="097a7-154">Owner of the Incident.</span></span>
<span data-ttu-id="097a7-155">Ernst</span><span class="sxs-lookup"><span data-stu-id="097a7-155">severity</span></span> | <span data-ttu-id="097a7-156">Opsommings</span><span class="sxs-lookup"><span data-stu-id="097a7-156">Enum</span></span> | <span data-ttu-id="097a7-157">Ernst van het incident.</span><span class="sxs-lookup"><span data-stu-id="097a7-157">Severity of the Incident.</span></span> <span data-ttu-id="097a7-158">Mogelijke waarden zijn: ```UnSpecified``` , ```Informational``` , ```Low``` , ```Medium``` en ```High``` .</span><span class="sxs-lookup"><span data-stu-id="097a7-158">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium```, and ```High```.</span></span>
<span data-ttu-id="097a7-159">status</span><span class="sxs-lookup"><span data-stu-id="097a7-159">status</span></span> | <span data-ttu-id="097a7-160">Opsommings</span><span class="sxs-lookup"><span data-stu-id="097a7-160">Enum</span></span> | <span data-ttu-id="097a7-161">Geeft de huidige status van het incident aan.</span><span class="sxs-lookup"><span data-stu-id="097a7-161">Specifies the current status of the incident.</span></span> <span data-ttu-id="097a7-162">Mogelijke waarden zijn: ```Active``` , ```Resolved``` , en ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="097a7-162">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="097a7-163">Contactpersoonclassificatie</span><span class="sxs-lookup"><span data-stu-id="097a7-163">classification</span></span> | <span data-ttu-id="097a7-164">Opsommings</span><span class="sxs-lookup"><span data-stu-id="097a7-164">Enum</span></span> | <span data-ttu-id="097a7-165">Specificatie van het incident.</span><span class="sxs-lookup"><span data-stu-id="097a7-165">Specification of the incident.</span></span> <span data-ttu-id="097a7-166">Mogelijke waarden zijn: ```Unknown``` , ```FalsePositive``` , ```TruePositive``` .</span><span class="sxs-lookup"><span data-stu-id="097a7-166">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="097a7-167">relevant</span><span class="sxs-lookup"><span data-stu-id="097a7-167">determination</span></span> | <span data-ttu-id="097a7-168">Opsommings</span><span class="sxs-lookup"><span data-stu-id="097a7-168">Enum</span></span> | <span data-ttu-id="097a7-169">Hiermee wordt het bepalen van het incident aangegeven.</span><span class="sxs-lookup"><span data-stu-id="097a7-169">Specifies the determination of the incident.</span></span> <span data-ttu-id="097a7-170">Mogelijke waarden zijn: ```NotAvailable``` , ```Apt``` ,,, ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` , ```UnwantedSoftware``` , ```Other``` .</span><span class="sxs-lookup"><span data-stu-id="097a7-170">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="097a7-171">Tags</span><span class="sxs-lookup"><span data-stu-id="097a7-171">tags</span></span> | <span data-ttu-id="097a7-172">Lijst met tekenreeksen</span><span class="sxs-lookup"><span data-stu-id="097a7-172">string List</span></span> | <span data-ttu-id="097a7-173">Lijst met incident Tags.</span><span class="sxs-lookup"><span data-stu-id="097a7-173">List of Incident tags.</span></span>
<span data-ttu-id="097a7-174">kennisgeving</span><span class="sxs-lookup"><span data-stu-id="097a7-174">alerts</span></span> | <span data-ttu-id="097a7-175">Lijst met waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="097a7-175">Alert List</span></span> | <span data-ttu-id="097a7-176">Lijst met verwante meldingen.</span><span class="sxs-lookup"><span data-stu-id="097a7-176">List of related alerts.</span></span> <span data-ttu-id="097a7-177">Zie voorbeelden in API-documentatie voor [lijst incidenten](api-list-incidents.md) .</span><span class="sxs-lookup"><span data-stu-id="097a7-177">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>

## <a name="related-articles"></a><span data-ttu-id="097a7-178">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="097a7-178">Related articles</span></span>

- [<span data-ttu-id="097a7-179">Overzicht van Microsoft 365 Defender-Api's</span><span class="sxs-lookup"><span data-stu-id="097a7-179">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="097a7-180">Overzicht van incidenten</span><span class="sxs-lookup"><span data-stu-id="097a7-180">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="097a7-181">API voor lijst incidenten</span><span class="sxs-lookup"><span data-stu-id="097a7-181">List incidents API</span></span>](api-list-incidents.md)
- [<span data-ttu-id="097a7-182">Update incident-API</span><span class="sxs-lookup"><span data-stu-id="097a7-182">Update incident API</span></span>](api-update-incidents.md)
