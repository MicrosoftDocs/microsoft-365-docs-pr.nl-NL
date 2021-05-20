---
title: Api voor incident bijwerken
description: Meer informatie over het bijwerken van incidenten met Microsoft 365 Defender API
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
ms.openlocfilehash: e3f3919d067078ef1fd1e116dc52e8a73c0726d9
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571779"
---
# <a name="update-incident-api"></a><span data-ttu-id="7af8a-104">Api voor incident bijwerken</span><span class="sxs-lookup"><span data-stu-id="7af8a-104">Update incident API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="7af8a-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="7af8a-105">**Applies to:**</span></span>

- <span data-ttu-id="7af8a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7af8a-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7af8a-107">Sommige informatie is gerelateerd aan voorlopige productversies die mogelijk aanzienlijk gewijzigd worden voordat ze commercieel gepubliceerd worden.</span><span class="sxs-lookup"><span data-stu-id="7af8a-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="7af8a-108">Microsoft geeft geen garantie, uitdrukkelijk of impliciet, met betrekking tot de informatie die hier wordt beschreven.</span><span class="sxs-lookup"><span data-stu-id="7af8a-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="api-description"></a><span data-ttu-id="7af8a-109">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="7af8a-109">API description</span></span>

<span data-ttu-id="7af8a-110">Hiermee worden de eigenschappen van het bestaande incident bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="7af8a-110">Updates properties of existing incident.</span></span> <span data-ttu-id="7af8a-111">Updatable eigenschappen zijn: ```status``` , , , , , en ```determination``` ```classification``` ```assignedTo``` ```tags``` ```comments``` .</span><span class="sxs-lookup"><span data-stu-id="7af8a-111">Updatable properties are: ```status```, ```determination```, ```classification```, ```assignedTo```, ```tags```, and ```comments```.</span></span>

### <a name="quotas-resource-allocation-and-other-constraints"></a><span data-ttu-id="7af8a-112">Quota, toewijzing van middelen en andere beperkingen</span><span class="sxs-lookup"><span data-stu-id="7af8a-112">Quotas, resource allocation, and other constraints</span></span>

1. <span data-ttu-id="7af8a-113">U kunt maximaal 50 gesprekken per minuut of 1500 gesprekken per uur voeren voordat u de beperkingsdrempel bereikt.</span><span class="sxs-lookup"><span data-stu-id="7af8a-113">You can make up to 50 calls per minute or 1500 calls per hour before you hit the throttling threshold.</span></span>
2. <span data-ttu-id="7af8a-114">U kunt de eigenschap alleen instellen `determination` als deze is ingesteld op `classification` TruePositive.</span><span class="sxs-lookup"><span data-stu-id="7af8a-114">You can set the `determination` property only if `classification` is set to TruePositive.</span></span>

<span data-ttu-id="7af8a-115">Als uw aanvraag wordt beperkt, wordt er een `429` antwoordcode geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="7af8a-115">If your request is throttled, it will return a `429` response code.</span></span> <span data-ttu-id="7af8a-116">De instantie van de reactie geeft het tijdstip aan waarop u kunt beginnen met het voeren van nieuwe oproepen.</span><span class="sxs-lookup"><span data-stu-id="7af8a-116">The response body will indicate the time when you can begin making new calls.</span></span>

## <a name="permissions"></a><span data-ttu-id="7af8a-117">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="7af8a-117">Permissions</span></span>

<span data-ttu-id="7af8a-118">Een van de volgende machtigingen is vereist om deze API aan te roepen.</span><span class="sxs-lookup"><span data-stu-id="7af8a-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="7af8a-119">Zie Toegang tot [de API's van Microsoft 365 Defender](api-access.md)voor meer informatie, waaronder het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="7af8a-119">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender APIs](api-access.md).</span></span>

<span data-ttu-id="7af8a-120">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="7af8a-120">Permission type</span></span> | <span data-ttu-id="7af8a-121">Machtiging</span><span class="sxs-lookup"><span data-stu-id="7af8a-121">Permission</span></span> | <span data-ttu-id="7af8a-122">Naam van machtigingsweergave</span><span class="sxs-lookup"><span data-stu-id="7af8a-122">Permission display name</span></span>
-|-|-
<span data-ttu-id="7af8a-123">Toepassing</span><span class="sxs-lookup"><span data-stu-id="7af8a-123">Application</span></span> | <span data-ttu-id="7af8a-124">Incident.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="7af8a-124">Incident.ReadWrite.All</span></span> | <span data-ttu-id="7af8a-125">Lees en schrijf alle incidenten</span><span class="sxs-lookup"><span data-stu-id="7af8a-125">Read and write all incidents</span></span>
<span data-ttu-id="7af8a-126">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="7af8a-126">Delegated (work or school account)</span></span> | <span data-ttu-id="7af8a-127">Incident.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="7af8a-127">Incident.ReadWrite</span></span> | <span data-ttu-id="7af8a-128">Lees en schrijf incidenten</span><span class="sxs-lookup"><span data-stu-id="7af8a-128">Read and write incidents</span></span>

> [!NOTE]
> <span data-ttu-id="7af8a-129">Wanneer u een token verkrijgt met behulp van gebruikers referenties, moet de gebruiker toestemming hebben om het incident in de portal bij te werken.</span><span class="sxs-lookup"><span data-stu-id="7af8a-129">When obtaining a token using user credentials, the user needs to have permission to update the incident in the portal.</span></span>

## <a name="http-request"></a><span data-ttu-id="7af8a-130">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="7af8a-130">HTTP request</span></span>

```HTTP
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a><span data-ttu-id="7af8a-131">Headers aanvragen</span><span class="sxs-lookup"><span data-stu-id="7af8a-131">Request headers</span></span>

<span data-ttu-id="7af8a-132">Naam</span><span class="sxs-lookup"><span data-stu-id="7af8a-132">Name</span></span> | <span data-ttu-id="7af8a-133">Type</span><span class="sxs-lookup"><span data-stu-id="7af8a-133">Type</span></span> | <span data-ttu-id="7af8a-134">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="7af8a-134">Description</span></span>
-|-|-
<span data-ttu-id="7af8a-135">machtiging</span><span class="sxs-lookup"><span data-stu-id="7af8a-135">Authorization</span></span> | <span data-ttu-id="7af8a-136">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7af8a-136">String</span></span> | <span data-ttu-id="7af8a-137">Aan toonder {token}.</span><span class="sxs-lookup"><span data-stu-id="7af8a-137">Bearer {token}.</span></span> <span data-ttu-id="7af8a-138">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="7af8a-138">**Required**.</span></span>
<span data-ttu-id="7af8a-139">Inhoudstype</span><span class="sxs-lookup"><span data-stu-id="7af8a-139">Content-Type</span></span> | <span data-ttu-id="7af8a-140">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7af8a-140">String</span></span> | <span data-ttu-id="7af8a-141">toepassing/json.</span><span class="sxs-lookup"><span data-stu-id="7af8a-141">application/json.</span></span> <span data-ttu-id="7af8a-142">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="7af8a-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="7af8a-143">Instantie aanvragen</span><span class="sxs-lookup"><span data-stu-id="7af8a-143">Request body</span></span>

<span data-ttu-id="7af8a-144">Geef in de hoofdtekst van de aanvraag de waarden op voor de velden die moeten worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="7af8a-144">In the request body, supply the values for the fields that should be updated.</span></span> <span data-ttu-id="7af8a-145">Bestaande eigenschappen die niet zijn opgenomen in de hoofdtekst van de aanvraag, behouden hun waarden, tenzij ze opnieuw moeten worden berekend vanwege wijzigingen in gerelateerde waarden.</span><span class="sxs-lookup"><span data-stu-id="7af8a-145">Existing properties that aren't included in the request body will maintain their values, unless they have to be recalculated due to changes to related values.</span></span> <span data-ttu-id="7af8a-146">Voor de beste prestaties moet u bestaande waarden weglaten die niet zijn gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="7af8a-146">For best performance, you should omit existing values that haven't changed.</span></span>

<span data-ttu-id="7af8a-147">Eigenschap</span><span class="sxs-lookup"><span data-stu-id="7af8a-147">Property</span></span> | <span data-ttu-id="7af8a-148">Type</span><span class="sxs-lookup"><span data-stu-id="7af8a-148">Type</span></span> | <span data-ttu-id="7af8a-149">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="7af8a-149">Description</span></span>
-|-|-
<span data-ttu-id="7af8a-150">status</span><span class="sxs-lookup"><span data-stu-id="7af8a-150">status</span></span> | <span data-ttu-id="7af8a-151">Enum</span><span class="sxs-lookup"><span data-stu-id="7af8a-151">Enum</span></span> | <span data-ttu-id="7af8a-152">Hiermee geeft u de huidige status van het incident op.</span><span class="sxs-lookup"><span data-stu-id="7af8a-152">Specifies the current status of the incident.</span></span> <span data-ttu-id="7af8a-153">Mogelijke waarden zijn: ```Active``` ```Resolved``` , , en ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="7af8a-153">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="7af8a-154">toegewezenTo</span><span class="sxs-lookup"><span data-stu-id="7af8a-154">assignedTo</span></span> | <span data-ttu-id="7af8a-155">snaar</span><span class="sxs-lookup"><span data-stu-id="7af8a-155">string</span></span> | <span data-ttu-id="7af8a-156">Eigenaar van het incident.</span><span class="sxs-lookup"><span data-stu-id="7af8a-156">Owner of the incident.</span></span>
<span data-ttu-id="7af8a-157">classificatie</span><span class="sxs-lookup"><span data-stu-id="7af8a-157">classification</span></span> | <span data-ttu-id="7af8a-158">Enum</span><span class="sxs-lookup"><span data-stu-id="7af8a-158">Enum</span></span> | <span data-ttu-id="7af8a-159">Specificatie van het incident.</span><span class="sxs-lookup"><span data-stu-id="7af8a-159">Specification of the incident.</span></span> <span data-ttu-id="7af8a-160">Mogelijke waarden zijn: ```Unknown``` ```FalsePositive``` , , ```TruePositive``` .</span><span class="sxs-lookup"><span data-stu-id="7af8a-160">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="7af8a-161">vastberadenheid</span><span class="sxs-lookup"><span data-stu-id="7af8a-161">determination</span></span> | <span data-ttu-id="7af8a-162">Enum</span><span class="sxs-lookup"><span data-stu-id="7af8a-162">Enum</span></span> | <span data-ttu-id="7af8a-163">Hiermee geeft u de bepaling van het incident op.</span><span class="sxs-lookup"><span data-stu-id="7af8a-163">Specifies the determination of the incident.</span></span> <span data-ttu-id="7af8a-164">Mogelijke waarden zijn: ```NotAvailable``` , , , , , ```Apt``` ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` ```UnwantedSoftware``` ```Other``` .</span><span class="sxs-lookup"><span data-stu-id="7af8a-164">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="7af8a-165">Tags</span><span class="sxs-lookup"><span data-stu-id="7af8a-165">tags</span></span> | <span data-ttu-id="7af8a-166">tekenreekslijst</span><span class="sxs-lookup"><span data-stu-id="7af8a-166">string List</span></span> | <span data-ttu-id="7af8a-167">Lijst met incidenttags.</span><span class="sxs-lookup"><span data-stu-id="7af8a-167">List of Incident tags.</span></span>
<span data-ttu-id="7af8a-168">commentaar</span><span class="sxs-lookup"><span data-stu-id="7af8a-168">comment</span></span> | <span data-ttu-id="7af8a-169">snaar</span><span class="sxs-lookup"><span data-stu-id="7af8a-169">string</span></span> | <span data-ttu-id="7af8a-170">Commentaar dat aan het incident moet worden toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="7af8a-170">Comment to be added to the incident.</span></span>

## <a name="response"></a><span data-ttu-id="7af8a-171">antwoord</span><span class="sxs-lookup"><span data-stu-id="7af8a-171">Response</span></span>

<span data-ttu-id="7af8a-172">Als dit is gelukt, retourneert deze methode `200 OK` .</span><span class="sxs-lookup"><span data-stu-id="7af8a-172">If successful, this method returns `200 OK`.</span></span> <span data-ttu-id="7af8a-173">De antwoordtekst bevat de incidententiteit met bijgewerkte eigenschappen.</span><span class="sxs-lookup"><span data-stu-id="7af8a-173">The response body will contain the incident entity with updated properties.</span></span> <span data-ttu-id="7af8a-174">Als er geen incident met de opgegeven ID is gevonden, retourneert de methode `404 Not Found` .</span><span class="sxs-lookup"><span data-stu-id="7af8a-174">If an incident with the specified ID wasn't found, the method returns `404 Not Found`.</span></span>

## <a name="example"></a><span data-ttu-id="7af8a-175">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="7af8a-175">Example</span></span>

<span data-ttu-id="7af8a-176">**verzoek**</span><span class="sxs-lookup"><span data-stu-id="7af8a-176">**Request**</span></span>

<span data-ttu-id="7af8a-177">Hier is een voorbeeld van het verzoek.</span><span class="sxs-lookup"><span data-stu-id="7af8a-177">Here's an example of the request.</span></span>

```HTTP
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

<span data-ttu-id="7af8a-178">**antwoord**</span><span class="sxs-lookup"><span data-stu-id="7af8a-178">**Response**</span></span>

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "TruePositive",
    "determination": "Malware",
    "tags": ["Yossi's playground", "Don't mess with the Zohan"],
    "comments": [
          {
              "comment": "pen testing",
              "createdBy": "secop2@contoso.com",
              "createdTime": "2021-05-02T09:34:21.5519738Z"
          },
          {
              "comment": "valid incident",
              "createdBy": "secop2@contoso.comt",
              "createdTime": "2021-05-02T09:36:27.6652581Z"
          }
      ]
}
```

## <a name="related-articles"></a><span data-ttu-id="7af8a-179">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="7af8a-179">Related articles</span></span>

- [<span data-ttu-id="7af8a-180">Toegang tot de API's van Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7af8a-180">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="7af8a-181">Meer informatie over API-limieten en licenties</span><span class="sxs-lookup"><span data-stu-id="7af8a-181">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="7af8a-182">Foutcodes begrijpen</span><span class="sxs-lookup"><span data-stu-id="7af8a-182">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="7af8a-183">API's voor incidenten</span><span class="sxs-lookup"><span data-stu-id="7af8a-183">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="7af8a-184">Lijst met incidenten</span><span class="sxs-lookup"><span data-stu-id="7af8a-184">List incidents</span></span>](api-list-incidents.md)
- [<span data-ttu-id="7af8a-185">Overzicht incidenten</span><span class="sxs-lookup"><span data-stu-id="7af8a-185">Incidents overview</span></span>](incidents-overview.md)
