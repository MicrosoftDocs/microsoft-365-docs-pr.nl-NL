---
title: API voor update van incidenten
description: Meer informatie over het bijwerken van incidenten met de Microsoft 365 Defender API
keywords: Update, API, incident
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
ms.openlocfilehash: 6fc1ff730994f03aa500ad9a4559b66970e32d87
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719402"
---
# <a name="update-incidents-api"></a><span data-ttu-id="48a2c-104">API voor update van incidenten</span><span class="sxs-lookup"><span data-stu-id="48a2c-104">Update incidents API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="48a2c-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="48a2c-105">**Applies to:**</span></span>

- <span data-ttu-id="48a2c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="48a2c-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="48a2c-107">Sommige informatie verhoudt zich tot een voorvrijgegeven product dat bij de commerciële versie van de commerciële versie mogelijk ingrijpend werd gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="48a2c-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="48a2c-108">Microsoft biedt geen garanties, expliciete of impliciete informatie met betrekking tot de informatie die u hier opgeeft.</span><span class="sxs-lookup"><span data-stu-id="48a2c-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="api-description"></a><span data-ttu-id="48a2c-109">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="48a2c-109">API description</span></span>

<span data-ttu-id="48a2c-110">Hiermee worden de eigenschappen van een bestaand incident bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="48a2c-110">Updates properties of existing incident.</span></span> <span data-ttu-id="48a2c-111">Bijwerkbare eigenschappen zijn: ```status``` , ```determination``` , ```classification``` , ```assignedTo``` en ```tags``` .</span><span class="sxs-lookup"><span data-stu-id="48a2c-111">Updatable properties are: ```status```, ```determination```, ```classification```, ```assignedTo```, and ```tags```.</span></span>

### <a name="quotas-resource-allocation-and-other-constraints"></a><span data-ttu-id="48a2c-112">Quota's, resourcetoewijzing en andere beperkingen</span><span class="sxs-lookup"><span data-stu-id="48a2c-112">Quotas, resource allocation, and other constraints</span></span>

1. <span data-ttu-id="48a2c-113">U kunt maximaal 50 oproepen per minuut of 1500 bellen per uur maken voordat u op de drempelwaarde klikt.</span><span class="sxs-lookup"><span data-stu-id="48a2c-113">You can make up to 50 calls per minute or 1500 calls per hour before you hit the throttling threshold.</span></span>
2. <span data-ttu-id="48a2c-114">U kunt de `determination` eigenschap alleen instellen als dit `classification` is ingesteld op TruePositive.</span><span class="sxs-lookup"><span data-stu-id="48a2c-114">You can set the `determination` property only if `classification` is set to TruePositive.</span></span>

<span data-ttu-id="48a2c-115">Als uw aanvraag wordt vertraagd, wordt een `429` antwoordcode geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="48a2c-115">If your request is throttled, it will return a `429` response code.</span></span> <span data-ttu-id="48a2c-116">De antwoordtekst geeft de tijd aan waarop u kunt beginnen met het maken van nieuwe oproepen.</span><span class="sxs-lookup"><span data-stu-id="48a2c-116">The response body will indicate the time when you can begin making new calls.</span></span>

## <a name="permissions"></a><span data-ttu-id="48a2c-117">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="48a2c-117">Permissions</span></span>

<span data-ttu-id="48a2c-118">U moet een van de volgende machtigingen hebben om deze API te kunnen bellen.</span><span class="sxs-lookup"><span data-stu-id="48a2c-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="48a2c-119">Voor meer informatie, waaronder de manier waarop u machtigingen kiest, raadpleegt u [de Microsoft 365-api's voor Access](api-access.md).</span><span class="sxs-lookup"><span data-stu-id="48a2c-119">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender APIs](api-access.md).</span></span>

<span data-ttu-id="48a2c-120">Type machtiging</span><span class="sxs-lookup"><span data-stu-id="48a2c-120">Permission type</span></span> | <span data-ttu-id="48a2c-121">Machtigingsset</span><span class="sxs-lookup"><span data-stu-id="48a2c-121">Permission</span></span> | <span data-ttu-id="48a2c-122">Weergavenaam van de machtiging</span><span class="sxs-lookup"><span data-stu-id="48a2c-122">Permission display name</span></span>
-|-|-
<span data-ttu-id="48a2c-123">Toepassing</span><span class="sxs-lookup"><span data-stu-id="48a2c-123">Application</span></span> | <span data-ttu-id="48a2c-124">Incident. ReadWrite. all</span><span class="sxs-lookup"><span data-stu-id="48a2c-124">Incident.ReadWrite.All</span></span> | <span data-ttu-id="48a2c-125">Alle incidenten lezen en schrijven</span><span class="sxs-lookup"><span data-stu-id="48a2c-125">Read and write all incidents</span></span>
<span data-ttu-id="48a2c-126">Gedelegeerd (werk-of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="48a2c-126">Delegated (work or school account)</span></span> | <span data-ttu-id="48a2c-127">Incident. ReadWrite</span><span class="sxs-lookup"><span data-stu-id="48a2c-127">Incident.ReadWrite</span></span> | <span data-ttu-id="48a2c-128">Lees-en schrijf incidenten</span><span class="sxs-lookup"><span data-stu-id="48a2c-128">Read and write incidents</span></span>

> [!NOTE]
> <span data-ttu-id="48a2c-129">Bij het verkrijgen van een token met behulp van gebruikersreferenties moet de gebruiker zijn gemachtigd om het incident bij te werken in de portal.</span><span class="sxs-lookup"><span data-stu-id="48a2c-129">When obtaining a token using user credentials, the user needs to have permission to update the incident in the portal.</span></span>

## <a name="http-request"></a><span data-ttu-id="48a2c-130">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="48a2c-130">HTTP request</span></span>

```HTTP
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a><span data-ttu-id="48a2c-131">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="48a2c-131">Request headers</span></span>

<span data-ttu-id="48a2c-132">Naam</span><span class="sxs-lookup"><span data-stu-id="48a2c-132">Name</span></span> | <span data-ttu-id="48a2c-133">Type</span><span class="sxs-lookup"><span data-stu-id="48a2c-133">Type</span></span> | <span data-ttu-id="48a2c-134">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="48a2c-134">Description</span></span>
-|-|-
<span data-ttu-id="48a2c-135">Bevoegdheid</span><span class="sxs-lookup"><span data-stu-id="48a2c-135">Authorization</span></span> | <span data-ttu-id="48a2c-136">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="48a2c-136">String</span></span> | <span data-ttu-id="48a2c-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="48a2c-137">Bearer {token}.</span></span> <span data-ttu-id="48a2c-138">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="48a2c-138">**Required**.</span></span>
<span data-ttu-id="48a2c-139">Inhouds type</span><span class="sxs-lookup"><span data-stu-id="48a2c-139">Content-Type</span></span> | <span data-ttu-id="48a2c-140">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="48a2c-140">String</span></span> | <span data-ttu-id="48a2c-141">Application/JSON.</span><span class="sxs-lookup"><span data-stu-id="48a2c-141">application/json.</span></span> <span data-ttu-id="48a2c-142">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="48a2c-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="48a2c-143">Aanvraagtekst</span><span class="sxs-lookup"><span data-stu-id="48a2c-143">Request body</span></span>

<span data-ttu-id="48a2c-144">Geef in de hoofdtekst van de aanvraag de waarden op voor de velden die moeten worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="48a2c-144">In the request body, supply the values for the fields that should be updated.</span></span> <span data-ttu-id="48a2c-145">Bestaande eigenschappen die niet zijn opgenomen in de hoofdtekst van de aanvraag, behouden hun waarden, tenzij ze moeten worden herberekend als gevolg van wijzigingen in gerelateerde waarden.</span><span class="sxs-lookup"><span data-stu-id="48a2c-145">Existing properties that aren't included in the request body will maintain their values, unless they have to be recalculated due to changes to related values.</span></span> <span data-ttu-id="48a2c-146">Voor de beste prestaties moet u bestaande waarden weglaten die niet zijn gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="48a2c-146">For best performance, you should omit existing values that haven't changed.</span></span>

<span data-ttu-id="48a2c-147">Eigenschap</span><span class="sxs-lookup"><span data-stu-id="48a2c-147">Property</span></span> | <span data-ttu-id="48a2c-148">Type</span><span class="sxs-lookup"><span data-stu-id="48a2c-148">Type</span></span> | <span data-ttu-id="48a2c-149">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="48a2c-149">Description</span></span>
-|-|-
<span data-ttu-id="48a2c-150">status</span><span class="sxs-lookup"><span data-stu-id="48a2c-150">status</span></span> | <span data-ttu-id="48a2c-151">Opsommings</span><span class="sxs-lookup"><span data-stu-id="48a2c-151">Enum</span></span> | <span data-ttu-id="48a2c-152">Geeft de huidige status van de waarschuwing op.</span><span class="sxs-lookup"><span data-stu-id="48a2c-152">Specifies the current status of the alert.</span></span> <span data-ttu-id="48a2c-153">Mogelijke waarden zijn: ```Active``` , ```Resolved``` , en ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="48a2c-153">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="48a2c-154">ToegewezenAan</span><span class="sxs-lookup"><span data-stu-id="48a2c-154">assignedTo</span></span> | <span data-ttu-id="48a2c-155">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="48a2c-155">string</span></span> | <span data-ttu-id="48a2c-156">Eigenaar van het incident.</span><span class="sxs-lookup"><span data-stu-id="48a2c-156">Owner of the incident.</span></span>
<span data-ttu-id="48a2c-157">Contactpersoonclassificatie</span><span class="sxs-lookup"><span data-stu-id="48a2c-157">classification</span></span> | <span data-ttu-id="48a2c-158">Opsommings</span><span class="sxs-lookup"><span data-stu-id="48a2c-158">Enum</span></span> | <span data-ttu-id="48a2c-159">Specificatie van de waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="48a2c-159">Specification of the alert.</span></span> <span data-ttu-id="48a2c-160">Mogelijke waarden zijn: ```Unknown``` , ```FalsePositive``` , ```TruePositive``` .</span><span class="sxs-lookup"><span data-stu-id="48a2c-160">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="48a2c-161">relevant</span><span class="sxs-lookup"><span data-stu-id="48a2c-161">determination</span></span> | <span data-ttu-id="48a2c-162">Opsommings</span><span class="sxs-lookup"><span data-stu-id="48a2c-162">Enum</span></span> | <span data-ttu-id="48a2c-163">Hiermee geeft u het bepalen van de waarschuwing op.</span><span class="sxs-lookup"><span data-stu-id="48a2c-163">Specifies the determination of the alert.</span></span> <span data-ttu-id="48a2c-164">Mogelijke waarden zijn: ```NotAvailable``` , ```Apt``` ,,, ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` , ```UnwantedSoftware``` , ```Other``` .</span><span class="sxs-lookup"><span data-stu-id="48a2c-164">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="48a2c-165">Tags</span><span class="sxs-lookup"><span data-stu-id="48a2c-165">tags</span></span> | <span data-ttu-id="48a2c-166">Lijst met tekenreeksen</span><span class="sxs-lookup"><span data-stu-id="48a2c-166">string List</span></span> | <span data-ttu-id="48a2c-167">Lijst met incident Tags.</span><span class="sxs-lookup"><span data-stu-id="48a2c-167">List of Incident tags.</span></span>

## <a name="response"></a><span data-ttu-id="48a2c-168">Na</span><span class="sxs-lookup"><span data-stu-id="48a2c-168">Response</span></span>

<span data-ttu-id="48a2c-169">Als dit slaagt, retourneert deze methode `200 OK` .</span><span class="sxs-lookup"><span data-stu-id="48a2c-169">If successful, this method returns `200 OK`.</span></span> <span data-ttu-id="48a2c-170">De antwoordtekst bevat de entiteit van de schade met bijgewerkte eigenschappen.</span><span class="sxs-lookup"><span data-stu-id="48a2c-170">The response body will contain the incident entity with updated properties.</span></span> <span data-ttu-id="48a2c-171">Als een incident met de opgegeven ID niet kan worden gevonden, wordt de methode geretourneerd `404 Not Found` .</span><span class="sxs-lookup"><span data-stu-id="48a2c-171">If an incident with the specified ID wasn't found, the method returns `404 Not Found`.</span></span>

## <a name="example"></a><span data-ttu-id="48a2c-172">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="48a2c-172">Example</span></span>

<span data-ttu-id="48a2c-173">**Webonderdeelverzoek**</span><span class="sxs-lookup"><span data-stu-id="48a2c-173">**Request**</span></span>

<span data-ttu-id="48a2c-174">Hier ziet u een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="48a2c-174">Here's an example of the request.</span></span>

```HTTP
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

<span data-ttu-id="48a2c-175">**Na**</span><span class="sxs-lookup"><span data-stu-id="48a2c-175">**Response**</span></span>

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "TruePositive",
    "determination": "Malware",
    "tags": ["Yossi's playground", "Don't mess with the Zohan"]
}
```

## <a name="related-articles"></a><span data-ttu-id="48a2c-176">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="48a2c-176">Related articles</span></span>

- [<span data-ttu-id="48a2c-177">Toegang tot de Microsoft 365 Defender-Api's</span><span class="sxs-lookup"><span data-stu-id="48a2c-177">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="48a2c-178">Meer informatie over API-limieten en licenties</span><span class="sxs-lookup"><span data-stu-id="48a2c-178">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="48a2c-179">Meer informatie over foutcodes</span><span class="sxs-lookup"><span data-stu-id="48a2c-179">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="48a2c-180">API's voor incidenten</span><span class="sxs-lookup"><span data-stu-id="48a2c-180">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="48a2c-181">Lijst met incidenten</span><span class="sxs-lookup"><span data-stu-id="48a2c-181">List incidents</span></span>](api-list-incidents.md)
- [<span data-ttu-id="48a2c-182">Overzicht van incidenten</span><span class="sxs-lookup"><span data-stu-id="48a2c-182">Incidents overview</span></span>](incidents-overview.md)
