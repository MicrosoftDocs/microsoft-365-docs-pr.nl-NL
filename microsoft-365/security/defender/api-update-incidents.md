---
title: Api voor incidenten bijwerken
description: Informatie over het bijwerken van incidenten met de Microsoft 365 Defender API
keywords: update, api, incident
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
ms.openlocfilehash: 549f9bf2b9dc2ea5d1c734a809ad10a168c8123e
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056663"
---
# <a name="update-incidents-api"></a><span data-ttu-id="e4ce1-104">Api voor incidenten bijwerken</span><span class="sxs-lookup"><span data-stu-id="e4ce1-104">Update incidents API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="e4ce1-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="e4ce1-105">**Applies to:**</span></span>

- <span data-ttu-id="e4ce1-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e4ce1-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e4ce1-107">Sommige informatie is gerelateerd aan voorlopige productversies die mogelijk aanzienlijk gewijzigd worden voordat ze commercieel gepubliceerd worden.</span><span class="sxs-lookup"><span data-stu-id="e4ce1-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="e4ce1-108">Microsoft geeft geen garantie, uitdrukkelijk of impliciet, met betrekking tot de informatie die hier wordt beschreven.</span><span class="sxs-lookup"><span data-stu-id="e4ce1-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="api-description"></a><span data-ttu-id="e4ce1-109">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="e4ce1-109">API description</span></span>

<span data-ttu-id="e4ce1-110">De eigenschappen van bestaande incidenten worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="e4ce1-110">Updates properties of existing incident.</span></span> <span data-ttu-id="e4ce1-111">Updatable properties are: ```status``` , , , , , and ```determination``` ```classification``` ```assignedTo``` ```tags``` .</span><span class="sxs-lookup"><span data-stu-id="e4ce1-111">Updatable properties are: ```status```, ```determination```, ```classification```, ```assignedTo```, and ```tags```.</span></span>

### <a name="quotas-resource-allocation-and-other-constraints"></a><span data-ttu-id="e4ce1-112">Quota, resourcetoewijzing en andere beperkingen</span><span class="sxs-lookup"><span data-stu-id="e4ce1-112">Quotas, resource allocation, and other constraints</span></span>

1. <span data-ttu-id="e4ce1-113">U kunt maximaal 50 oproepen per minuut of 1500 oproepen per uur voeren voordat u de beperkingsdrempel bereikt.</span><span class="sxs-lookup"><span data-stu-id="e4ce1-113">You can make up to 50 calls per minute or 1500 calls per hour before you hit the throttling threshold.</span></span>
2. <span data-ttu-id="e4ce1-114">U kunt de `determination` eigenschap alleen instellen als deze is ingesteld op `classification` TruePositive.</span><span class="sxs-lookup"><span data-stu-id="e4ce1-114">You can set the `determination` property only if `classification` is set to TruePositive.</span></span>

<span data-ttu-id="e4ce1-115">Als uw aanvraag wordt beperkt, wordt er een `429` antwoordcode retourneerd.</span><span class="sxs-lookup"><span data-stu-id="e4ce1-115">If your request is throttled, it will return a `429` response code.</span></span> <span data-ttu-id="e4ce1-116">De antwoord body geeft het tijdstip aan waarop u kunt beginnen met het starten van nieuwe oproepen.</span><span class="sxs-lookup"><span data-stu-id="e4ce1-116">The response body will indicate the time when you can begin making new calls.</span></span>

## <a name="permissions"></a><span data-ttu-id="e4ce1-117">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="e4ce1-117">Permissions</span></span>

<span data-ttu-id="e4ce1-118">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="e4ce1-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="e4ce1-119">Zie Access the Microsoft 365 Defender APIs (Toegang tot de [Microsoft 365 Defender-API's)](api-access.md)voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="e4ce1-119">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender APIs](api-access.md).</span></span>

<span data-ttu-id="e4ce1-120">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="e4ce1-120">Permission type</span></span> | <span data-ttu-id="e4ce1-121">Machtiging</span><span class="sxs-lookup"><span data-stu-id="e4ce1-121">Permission</span></span> | <span data-ttu-id="e4ce1-122">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="e4ce1-122">Permission display name</span></span>
-|-|-
<span data-ttu-id="e4ce1-123">Toepassing</span><span class="sxs-lookup"><span data-stu-id="e4ce1-123">Application</span></span> | <span data-ttu-id="e4ce1-124">Incident.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="e4ce1-124">Incident.ReadWrite.All</span></span> | <span data-ttu-id="e4ce1-125">Alle incidenten lezen en schrijven</span><span class="sxs-lookup"><span data-stu-id="e4ce1-125">Read and write all incidents</span></span>
<span data-ttu-id="e4ce1-126">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="e4ce1-126">Delegated (work or school account)</span></span> | <span data-ttu-id="e4ce1-127">Incident.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="e4ce1-127">Incident.ReadWrite</span></span> | <span data-ttu-id="e4ce1-128">Incidenten lezen en schrijven</span><span class="sxs-lookup"><span data-stu-id="e4ce1-128">Read and write incidents</span></span>

> [!NOTE]
> <span data-ttu-id="e4ce1-129">Bij het verkrijgen van een token met gebruikersreferenties moet de gebruiker toestemming hebben om het incident in de portal bij te werken.</span><span class="sxs-lookup"><span data-stu-id="e4ce1-129">When obtaining a token using user credentials, the user needs to have permission to update the incident in the portal.</span></span>

## <a name="http-request"></a><span data-ttu-id="e4ce1-130">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="e4ce1-130">HTTP request</span></span>

```HTTP
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a><span data-ttu-id="e4ce1-131">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="e4ce1-131">Request headers</span></span>

<span data-ttu-id="e4ce1-132">Naam</span><span class="sxs-lookup"><span data-stu-id="e4ce1-132">Name</span></span> | <span data-ttu-id="e4ce1-133">Type</span><span class="sxs-lookup"><span data-stu-id="e4ce1-133">Type</span></span> | <span data-ttu-id="e4ce1-134">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="e4ce1-134">Description</span></span>
-|-|-
<span data-ttu-id="e4ce1-135">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="e4ce1-135">Authorization</span></span> | <span data-ttu-id="e4ce1-136">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="e4ce1-136">String</span></span> | <span data-ttu-id="e4ce1-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="e4ce1-137">Bearer {token}.</span></span> <span data-ttu-id="e4ce1-138">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="e4ce1-138">**Required**.</span></span>
<span data-ttu-id="e4ce1-139">Inhoudstype</span><span class="sxs-lookup"><span data-stu-id="e4ce1-139">Content-Type</span></span> | <span data-ttu-id="e4ce1-140">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="e4ce1-140">String</span></span> | <span data-ttu-id="e4ce1-141">toepassing/json.</span><span class="sxs-lookup"><span data-stu-id="e4ce1-141">application/json.</span></span> <span data-ttu-id="e4ce1-142">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="e4ce1-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="e4ce1-143">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="e4ce1-143">Request body</span></span>

<span data-ttu-id="e4ce1-144">In de aanvraagt u de waarden voor de velden die moeten worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="e4ce1-144">In the request body, supply the values for the fields that should be updated.</span></span> <span data-ttu-id="e4ce1-145">Bestaande eigenschappen die niet in de aanvraag worden opgenomen, behouden hun waarden, tenzij ze opnieuw moeten worden berekend vanwege wijzigingen in gerelateerde waarden.</span><span class="sxs-lookup"><span data-stu-id="e4ce1-145">Existing properties that aren't included in the request body will maintain their values, unless they have to be recalculated due to changes to related values.</span></span> <span data-ttu-id="e4ce1-146">Voor de beste prestaties moet u bestaande waarden weglaten die niet zijn gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="e4ce1-146">For best performance, you should omit existing values that haven't changed.</span></span>

<span data-ttu-id="e4ce1-147">Eigenschap</span><span class="sxs-lookup"><span data-stu-id="e4ce1-147">Property</span></span> | <span data-ttu-id="e4ce1-148">Type</span><span class="sxs-lookup"><span data-stu-id="e4ce1-148">Type</span></span> | <span data-ttu-id="e4ce1-149">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="e4ce1-149">Description</span></span>
-|-|-
<span data-ttu-id="e4ce1-150">status</span><span class="sxs-lookup"><span data-stu-id="e4ce1-150">status</span></span> | <span data-ttu-id="e4ce1-151">Enum</span><span class="sxs-lookup"><span data-stu-id="e4ce1-151">Enum</span></span> | <span data-ttu-id="e4ce1-152">Hiermee geeft u de huidige status van de waarschuwing op.</span><span class="sxs-lookup"><span data-stu-id="e4ce1-152">Specifies the current status of the alert.</span></span> <span data-ttu-id="e4ce1-153">Mogelijke waarden zijn: ```Active``` ```Resolved``` , en ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="e4ce1-153">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="e4ce1-154">toegewezenTo</span><span class="sxs-lookup"><span data-stu-id="e4ce1-154">assignedTo</span></span> | <span data-ttu-id="e4ce1-155">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="e4ce1-155">string</span></span> | <span data-ttu-id="e4ce1-156">Eigenaar van het incident.</span><span class="sxs-lookup"><span data-stu-id="e4ce1-156">Owner of the incident.</span></span>
<span data-ttu-id="e4ce1-157">classificatie</span><span class="sxs-lookup"><span data-stu-id="e4ce1-157">classification</span></span> | <span data-ttu-id="e4ce1-158">Enum</span><span class="sxs-lookup"><span data-stu-id="e4ce1-158">Enum</span></span> | <span data-ttu-id="e4ce1-159">Specificatie van de waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="e4ce1-159">Specification of the alert.</span></span> <span data-ttu-id="e4ce1-160">Mogelijke waarden zijn: ```Unknown``` ```FalsePositive``` , , ```TruePositive``` .</span><span class="sxs-lookup"><span data-stu-id="e4ce1-160">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="e4ce1-161">bepaling</span><span class="sxs-lookup"><span data-stu-id="e4ce1-161">determination</span></span> | <span data-ttu-id="e4ce1-162">Enum</span><span class="sxs-lookup"><span data-stu-id="e4ce1-162">Enum</span></span> | <span data-ttu-id="e4ce1-163">Hiermee geeft u de bepaling van de waarschuwing op.</span><span class="sxs-lookup"><span data-stu-id="e4ce1-163">Specifies the determination of the alert.</span></span> <span data-ttu-id="e4ce1-164">Mogelijke waarden zijn: ```NotAvailable``` , , , , , , ```Apt``` ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` ```UnwantedSoftware``` . ```Other```</span><span class="sxs-lookup"><span data-stu-id="e4ce1-164">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="e4ce1-165">tags</span><span class="sxs-lookup"><span data-stu-id="e4ce1-165">tags</span></span> | <span data-ttu-id="e4ce1-166">lijst met tekenreeksen</span><span class="sxs-lookup"><span data-stu-id="e4ce1-166">string List</span></span> | <span data-ttu-id="e4ce1-167">Lijst met incidentlabels.</span><span class="sxs-lookup"><span data-stu-id="e4ce1-167">List of Incident tags.</span></span>

## <a name="response"></a><span data-ttu-id="e4ce1-168">Antwoord</span><span class="sxs-lookup"><span data-stu-id="e4ce1-168">Response</span></span>

<span data-ttu-id="e4ce1-169">Als dit is gelukt, retourneert deze methode `200 OK` .</span><span class="sxs-lookup"><span data-stu-id="e4ce1-169">If successful, this method returns `200 OK`.</span></span> <span data-ttu-id="e4ce1-170">De antwoordinstantie bevat de entiteit incident met bijgewerkte eigenschappen.</span><span class="sxs-lookup"><span data-stu-id="e4ce1-170">The response body will contain the incident entity with updated properties.</span></span> <span data-ttu-id="e4ce1-171">Als er geen incident met de opgegeven id is gevonden, retourneert de methode `404 Not Found` .</span><span class="sxs-lookup"><span data-stu-id="e4ce1-171">If an incident with the specified ID wasn't found, the method returns `404 Not Found`.</span></span>

## <a name="example"></a><span data-ttu-id="e4ce1-172">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="e4ce1-172">Example</span></span>

<span data-ttu-id="e4ce1-173">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="e4ce1-173">**Request**</span></span>

<span data-ttu-id="e4ce1-174">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="e4ce1-174">Here's an example of the request.</span></span>

```HTTP
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

<span data-ttu-id="e4ce1-175">**Antwoord**</span><span class="sxs-lookup"><span data-stu-id="e4ce1-175">**Response**</span></span>

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "TruePositive",
    "determination": "Malware",
    "tags": ["Yossi's playground", "Don't mess with the Zohan"]
}
```

## <a name="related-articles"></a><span data-ttu-id="e4ce1-176">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="e4ce1-176">Related articles</span></span>

- [<span data-ttu-id="e4ce1-177">De Microsoft 365 Defender-API's openen</span><span class="sxs-lookup"><span data-stu-id="e4ce1-177">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="e4ce1-178">Meer informatie over API-limieten en -licenties</span><span class="sxs-lookup"><span data-stu-id="e4ce1-178">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="e4ce1-179">Foutcodes begrijpen</span><span class="sxs-lookup"><span data-stu-id="e4ce1-179">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="e4ce1-180">API's voor incidenten</span><span class="sxs-lookup"><span data-stu-id="e4ce1-180">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="e4ce1-181">Lijst met incidenten</span><span class="sxs-lookup"><span data-stu-id="e4ce1-181">List incidents</span></span>](api-list-incidents.md)
- [<span data-ttu-id="e4ce1-182">Overzicht van incidenten</span><span class="sxs-lookup"><span data-stu-id="e4ce1-182">Incidents overview</span></span>](incidents-overview.md)
