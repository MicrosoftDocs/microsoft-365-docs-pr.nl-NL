---
title: Update-incidenten API
description: Informatie over het bijwerken van incidenten met Microsoft 365 Defender API
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 18be4565c2611457d0f5fdc135f99a301bb39e2a
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929068"
---
# <a name="update-incidents-api"></a><span data-ttu-id="cecd4-104">Update-incidenten API</span><span class="sxs-lookup"><span data-stu-id="cecd4-104">Update incidents API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="cecd4-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="cecd4-105">**Applies to:**</span></span>

- <span data-ttu-id="cecd4-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cecd4-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cecd4-107">Sommige informatie heeft betrekking op vooraf uitgebracht product dat aanzienlijk kan worden gewijzigd voordat het in de handel wordt gebracht.</span><span class="sxs-lookup"><span data-stu-id="cecd4-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="cecd4-108">Microsoft biedt geen garanties, uitdrukkelijk of impliciet, met betrekking tot de informatie die hier wordt be gegeven.</span><span class="sxs-lookup"><span data-stu-id="cecd4-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="api-description"></a><span data-ttu-id="cecd4-109">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="cecd4-109">API description</span></span>

<span data-ttu-id="cecd4-110">De eigenschappen van een bestaand incident worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="cecd4-110">Updates properties of existing incident.</span></span> <span data-ttu-id="cecd4-111">De eigenschappen die kunnen worden updatable zijn: ```status``` ```determination``` , , en ```classification``` ```assignedTo``` ```tags``` .</span><span class="sxs-lookup"><span data-stu-id="cecd4-111">Updatable properties are: ```status```, ```determination```, ```classification```, ```assignedTo```, and ```tags```.</span></span>

### <a name="quotas-resource-allocation-and-other-constraints"></a><span data-ttu-id="cecd4-112">Quota's, toewijzing van resources en andere beperkingen</span><span class="sxs-lookup"><span data-stu-id="cecd4-112">Quotas, resource allocation, and other constraints</span></span>

1. <span data-ttu-id="cecd4-113">U kunt maximaal 50 oproepen per minuut of 1500 oproepen per uur doen voordat u de beperkingsdrempel overschrijdt.</span><span class="sxs-lookup"><span data-stu-id="cecd4-113">You can make up to 50 calls per minute or 1500 calls per hour before you hit the throttling threshold.</span></span>
2. <span data-ttu-id="cecd4-114">U kunt de eigenschap `determination` alleen instellen als dit is ingesteld op `classification` TruePositive.</span><span class="sxs-lookup"><span data-stu-id="cecd4-114">You can set the `determination` property only if `classification` is set to TruePositive.</span></span>

<span data-ttu-id="cecd4-115">Als uw aanvraag wordt beperkt, wordt een `429` antwoordcode als retourneerd.</span><span class="sxs-lookup"><span data-stu-id="cecd4-115">If your request is throttled, it will return a `429` response code.</span></span> <span data-ttu-id="cecd4-116">In de antwoord body wordt het tijdstip aangegeven waarop u nieuwe gesprekken kunt starten.</span><span class="sxs-lookup"><span data-stu-id="cecd4-116">The response body will indicate the time when you can begin making new calls.</span></span>

## <a name="permissions"></a><span data-ttu-id="cecd4-117">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="cecd4-117">Permissions</span></span>

<span data-ttu-id="cecd4-118">Een van de volgende machtigingen is vereist om deze API aan te roepen.</span><span class="sxs-lookup"><span data-stu-id="cecd4-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="cecd4-119">Zie Access de [Microsoft 365 Defender-API's](api-access.md)voor meer informatie, waaronder het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="cecd4-119">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender APIs](api-access.md).</span></span>

<span data-ttu-id="cecd4-120">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="cecd4-120">Permission type</span></span> | <span data-ttu-id="cecd4-121">Machtiging</span><span class="sxs-lookup"><span data-stu-id="cecd4-121">Permission</span></span> | <span data-ttu-id="cecd4-122">Weergavenaam van machtiging</span><span class="sxs-lookup"><span data-stu-id="cecd4-122">Permission display name</span></span>
-|-|-
<span data-ttu-id="cecd4-123">Toepassing</span><span class="sxs-lookup"><span data-stu-id="cecd4-123">Application</span></span> | <span data-ttu-id="cecd4-124">Incident.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="cecd4-124">Incident.ReadWrite.All</span></span> | <span data-ttu-id="cecd4-125">Alle incidenten lezen en schrijven</span><span class="sxs-lookup"><span data-stu-id="cecd4-125">Read and write all incidents</span></span>
<span data-ttu-id="cecd4-126">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="cecd4-126">Delegated (work or school account)</span></span> | <span data-ttu-id="cecd4-127">Incident.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="cecd4-127">Incident.ReadWrite</span></span> | <span data-ttu-id="cecd4-128">Incidenten lezen en schrijven</span><span class="sxs-lookup"><span data-stu-id="cecd4-128">Read and write incidents</span></span>

> [!NOTE]
> <span data-ttu-id="cecd4-129">Wanneer u een token verkrijgt met behulp van gebruikersreferenties, moet de gebruiker zijn toestemming hebben om het incident bij te werken in de portal.</span><span class="sxs-lookup"><span data-stu-id="cecd4-129">When obtaining a token using user credentials, the user needs to have permission to update the incident in the portal.</span></span>

## <a name="http-request"></a><span data-ttu-id="cecd4-130">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="cecd4-130">HTTP request</span></span>

```HTTP
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a><span data-ttu-id="cecd4-131">Berichtkoppen aanvragen</span><span class="sxs-lookup"><span data-stu-id="cecd4-131">Request headers</span></span>

<span data-ttu-id="cecd4-132">Naam</span><span class="sxs-lookup"><span data-stu-id="cecd4-132">Name</span></span> | <span data-ttu-id="cecd4-133">Type</span><span class="sxs-lookup"><span data-stu-id="cecd4-133">Type</span></span> | <span data-ttu-id="cecd4-134">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="cecd4-134">Description</span></span>
-|-|-
<span data-ttu-id="cecd4-135">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="cecd4-135">Authorization</span></span> | <span data-ttu-id="cecd4-136">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="cecd4-136">String</span></span> | <span data-ttu-id="cecd4-137">Beller {token}.</span><span class="sxs-lookup"><span data-stu-id="cecd4-137">Bearer {token}.</span></span> <span data-ttu-id="cecd4-138">**Vereist.**</span><span class="sxs-lookup"><span data-stu-id="cecd4-138">**Required**.</span></span>
<span data-ttu-id="cecd4-139">Inhoudstype</span><span class="sxs-lookup"><span data-stu-id="cecd4-139">Content-Type</span></span> | <span data-ttu-id="cecd4-140">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="cecd4-140">String</span></span> | <span data-ttu-id="cecd4-141">toepassing/json.</span><span class="sxs-lookup"><span data-stu-id="cecd4-141">application/json.</span></span> <span data-ttu-id="cecd4-142">**Vereist.**</span><span class="sxs-lookup"><span data-stu-id="cecd4-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="cecd4-143">Aanvraag in de eerste instantie</span><span class="sxs-lookup"><span data-stu-id="cecd4-143">Request body</span></span>

<span data-ttu-id="cecd4-144">In de aanvraag zelf de waarden voor de velden die moeten worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="cecd4-144">In the request body, supply the values for the fields that should be updated.</span></span> <span data-ttu-id="cecd4-145">Bestaande eigenschappen die niet in de aanvraag zelf zijn opgenomen, behouden de waarden, tenzij deze moeten worden herberekend vanwege wijzigingen in gerelateerde waarden.</span><span class="sxs-lookup"><span data-stu-id="cecd4-145">Existing properties that aren't included in the request body will maintain their values, unless they have to be recalculated due to changes to related values.</span></span> <span data-ttu-id="cecd4-146">Voor de beste prestaties moet u bestaande waarden weglaten die niet zijn gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="cecd4-146">For best performance, you should omit existing values that haven't changed.</span></span>

<span data-ttu-id="cecd4-147">Eigenschap</span><span class="sxs-lookup"><span data-stu-id="cecd4-147">Property</span></span> | <span data-ttu-id="cecd4-148">Type</span><span class="sxs-lookup"><span data-stu-id="cecd4-148">Type</span></span> | <span data-ttu-id="cecd4-149">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="cecd4-149">Description</span></span>
-|-|-
<span data-ttu-id="cecd4-150">status</span><span class="sxs-lookup"><span data-stu-id="cecd4-150">status</span></span> | <span data-ttu-id="cecd4-151">Enum</span><span class="sxs-lookup"><span data-stu-id="cecd4-151">Enum</span></span> | <span data-ttu-id="cecd4-152">Hiermee geeft u de huidige status van de waarschuwing op.</span><span class="sxs-lookup"><span data-stu-id="cecd4-152">Specifies the current status of the alert.</span></span> <span data-ttu-id="cecd4-153">Mogelijke waarden zijn: ```Active``` ```Resolved``` en ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="cecd4-153">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="cecd4-154">toegewezen Aan</span><span class="sxs-lookup"><span data-stu-id="cecd4-154">assignedTo</span></span> | <span data-ttu-id="cecd4-155">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="cecd4-155">string</span></span> | <span data-ttu-id="cecd4-156">De eigenaar van het incident.</span><span class="sxs-lookup"><span data-stu-id="cecd4-156">Owner of the incident.</span></span>
<span data-ttu-id="cecd4-157">classificatie</span><span class="sxs-lookup"><span data-stu-id="cecd4-157">classification</span></span> | <span data-ttu-id="cecd4-158">Enum</span><span class="sxs-lookup"><span data-stu-id="cecd4-158">Enum</span></span> | <span data-ttu-id="cecd4-159">Specificatie van de waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="cecd4-159">Specification of the alert.</span></span> <span data-ttu-id="cecd4-160">Mogelijke waarden zijn: ```Unknown``` ```FalsePositive``` , ```TruePositive``` .</span><span class="sxs-lookup"><span data-stu-id="cecd4-160">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="cecd4-161">besluit</span><span class="sxs-lookup"><span data-stu-id="cecd4-161">determination</span></span> | <span data-ttu-id="cecd4-162">Enum</span><span class="sxs-lookup"><span data-stu-id="cecd4-162">Enum</span></span> | <span data-ttu-id="cecd4-163">Bepaalt de bepalingen van de waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="cecd4-163">Specifies the determination of the alert.</span></span> <span data-ttu-id="cecd4-164">Mogelijke waarden zijn: ```NotAvailable``` ```Apt``` , , , ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` ```UnwantedSoftware``` . ```Other```</span><span class="sxs-lookup"><span data-stu-id="cecd4-164">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="cecd4-165">tags</span><span class="sxs-lookup"><span data-stu-id="cecd4-165">tags</span></span> | <span data-ttu-id="cecd4-166">lijst met tekenreeksen</span><span class="sxs-lookup"><span data-stu-id="cecd4-166">string List</span></span> | <span data-ttu-id="cecd4-167">Lijst met incidentlabels.</span><span class="sxs-lookup"><span data-stu-id="cecd4-167">List of Incident tags.</span></span>

## <a name="response"></a><span data-ttu-id="cecd4-168">Antwoord</span><span class="sxs-lookup"><span data-stu-id="cecd4-168">Response</span></span>

<span data-ttu-id="cecd4-169">Als dit lukt, retourneert deze `200 OK` methode.</span><span class="sxs-lookup"><span data-stu-id="cecd4-169">If successful, this method returns `200 OK`.</span></span> <span data-ttu-id="cecd4-170">De antwoordinstantie bevat de incidententiteit met bijgewerkte eigenschappen.</span><span class="sxs-lookup"><span data-stu-id="cecd4-170">The response body will contain the incident entity with updated properties.</span></span> <span data-ttu-id="cecd4-171">Als een incident met de opgegeven id niet is gevonden, wordt het retourneert de `404 Not Found` methode.</span><span class="sxs-lookup"><span data-stu-id="cecd4-171">If an incident with the specified ID wasn't found, the method returns `404 Not Found`.</span></span>

## <a name="example"></a><span data-ttu-id="cecd4-172">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="cecd4-172">Example</span></span>

<span data-ttu-id="cecd4-173">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="cecd4-173">**Request**</span></span>

<span data-ttu-id="cecd4-174">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="cecd4-174">Here's an example of the request.</span></span>

```HTTP
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

<span data-ttu-id="cecd4-175">**Antwoord**</span><span class="sxs-lookup"><span data-stu-id="cecd4-175">**Response**</span></span>

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "TruePositive",
    "determination": "Malware",
    "tags": ["Yossi's playground", "Don't mess with the Zohan"]
}
```

## <a name="related-articles"></a><span data-ttu-id="cecd4-176">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="cecd4-176">Related articles</span></span>

- [<span data-ttu-id="cecd4-177">Toegang tot de Microsoft 365 Defender-API's</span><span class="sxs-lookup"><span data-stu-id="cecd4-177">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="cecd4-178">Meer informatie over API-limieten en licenties</span><span class="sxs-lookup"><span data-stu-id="cecd4-178">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="cecd4-179">Meer te weten komen over foutcodes</span><span class="sxs-lookup"><span data-stu-id="cecd4-179">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="cecd4-180">API's voor incidenten</span><span class="sxs-lookup"><span data-stu-id="cecd4-180">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="cecd4-181">Lijst met incidenten</span><span class="sxs-lookup"><span data-stu-id="cecd4-181">List incidents</span></span>](api-list-incidents.md)
- [<span data-ttu-id="cecd4-182">Overzicht van incidenten</span><span class="sxs-lookup"><span data-stu-id="cecd4-182">Incidents overview</span></span>](incidents-overview.md)
