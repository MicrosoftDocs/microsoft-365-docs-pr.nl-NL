---
title: API voor update van incidenten
description: Informatie over het bijwerken van incidenten met Microsoft Threat Protection API
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
ms.openlocfilehash: e790f4f415575323cfdd5fc15db41baa8b59c7f6
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650226"
---
# <a name="update-incidents-api"></a><span data-ttu-id="d0de2-104">API voor update van incidenten</span><span class="sxs-lookup"><span data-stu-id="d0de2-104">Update incidents API</span></span>

<span data-ttu-id="d0de2-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="d0de2-105">**Applies to:**</span></span>
- <span data-ttu-id="d0de2-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="d0de2-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="d0de2-107">Sommige informatie verhoudt zich tot een voorvrijgegeven product dat bij de commerciële versie van de commerciële versie mogelijk ingrijpend werd gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="d0de2-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="d0de2-108">Microsoft biedt geen garanties, expliciete of impliciete informatie met betrekking tot de informatie die u hier opgeeft.</span><span class="sxs-lookup"><span data-stu-id="d0de2-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


## <a name="api-description"></a><span data-ttu-id="d0de2-109">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="d0de2-109">API description</span></span>
<span data-ttu-id="d0de2-110">Hiermee worden de eigenschappen van een bestaand incident bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="d0de2-110">Updates properties of existing incident.</span></span>
<br><span data-ttu-id="d0de2-111">Bijwerkbare eigenschappen zijn: ```status``` , ```determination``` , ```classification``` ```assignedTo``` en ```tags``` .</span><span class="sxs-lookup"><span data-stu-id="d0de2-111">Updatable properties are: ```status```, ```determination```, ```classification```, ```assignedTo``` and ```tags```.</span></span>


## <a name="limitations"></a><span data-ttu-id="d0de2-112">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="d0de2-112">Limitations</span></span>
1. <span data-ttu-id="d0de2-113">Tarief beperkingen voor deze API zijn 50 oproepen per minuut en 1500-oproepen per uur.</span><span class="sxs-lookup"><span data-stu-id="d0de2-113">Rate limitations for this API are 50 calls per minute and 1500 calls per hour.</span></span>
2. <span data-ttu-id="d0de2-114">U kunt instellen ```determination``` dat alleen als de classificatie is ingesteld op TruePositive.</span><span class="sxs-lookup"><span data-stu-id="d0de2-114">You can set the ```determination``` only if the classification is set to TruePositive.</span></span>


## <a name="permissions"></a><span data-ttu-id="d0de2-115">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="d0de2-115">Permissions</span></span>
<span data-ttu-id="d0de2-116">U moet een van de volgende machtigingen hebben om deze API te kunnen bellen.</span><span class="sxs-lookup"><span data-stu-id="d0de2-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="d0de2-117">Voor meer informatie, waaronder de manier waarop u machtigingen kiest, raadpleegt u [de Api's Microsoft Threat Protection openen](api-access.md).</span><span class="sxs-lookup"><span data-stu-id="d0de2-117">To learn more, including how to choose permissions, see [Access the Microsoft Threat Protection APIs](api-access.md).</span></span>

<span data-ttu-id="d0de2-118">Type machtiging</span><span class="sxs-lookup"><span data-stu-id="d0de2-118">Permission type</span></span> |   <span data-ttu-id="d0de2-119">Machtigingsset</span><span class="sxs-lookup"><span data-stu-id="d0de2-119">Permission</span></span>  |   <span data-ttu-id="d0de2-120">Weergavenaam van de machtiging</span><span class="sxs-lookup"><span data-stu-id="d0de2-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="d0de2-121">Toepassing</span><span class="sxs-lookup"><span data-stu-id="d0de2-121">Application</span></span> |   <span data-ttu-id="d0de2-122">Incident. ReadWrite. all</span><span class="sxs-lookup"><span data-stu-id="d0de2-122">Incident.ReadWrite.All</span></span> |    <span data-ttu-id="d0de2-123">' Alle incidenten lezen en schrijven '</span><span class="sxs-lookup"><span data-stu-id="d0de2-123">'Read and write all incidents'</span></span>
<span data-ttu-id="d0de2-124">Gedelegeerd (werk-of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="d0de2-124">Delegated (work or school account)</span></span> | <span data-ttu-id="d0de2-125">Incident. ReadWrite</span><span class="sxs-lookup"><span data-stu-id="d0de2-125">Incident.ReadWrite</span></span> | <span data-ttu-id="d0de2-126">' Lees-en schrijf incident '</span><span class="sxs-lookup"><span data-stu-id="d0de2-126">'Read and write incidents'</span></span>

>[!NOTE]
> <span data-ttu-id="d0de2-127">Bij het verkrijgen van een token met behulp van gebruikersreferenties:</span><span class="sxs-lookup"><span data-stu-id="d0de2-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="d0de2-128">De gebruiker moet zijn gemachtigd om het incident in de portal bij te werken.</span><span class="sxs-lookup"><span data-stu-id="d0de2-128">The user needs to have permission to update the incident in the portal.</span></span>


## <a name="http-request"></a><span data-ttu-id="d0de2-129">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="d0de2-129">HTTP request</span></span>

```
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a><span data-ttu-id="d0de2-130">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="d0de2-130">Request headers</span></span>

<span data-ttu-id="d0de2-131">Naam</span><span class="sxs-lookup"><span data-stu-id="d0de2-131">Name</span></span> | <span data-ttu-id="d0de2-132">Type</span><span class="sxs-lookup"><span data-stu-id="d0de2-132">Type</span></span> | <span data-ttu-id="d0de2-133">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="d0de2-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="d0de2-134">Bevoegdheid</span><span class="sxs-lookup"><span data-stu-id="d0de2-134">Authorization</span></span> | <span data-ttu-id="d0de2-135">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="d0de2-135">String</span></span> | <span data-ttu-id="d0de2-136">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="d0de2-136">Bearer {token}.</span></span> <span data-ttu-id="d0de2-137">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="d0de2-137">**Required**.</span></span>
<span data-ttu-id="d0de2-138">Inhouds type</span><span class="sxs-lookup"><span data-stu-id="d0de2-138">Content-Type</span></span> | <span data-ttu-id="d0de2-139">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="d0de2-139">String</span></span> | <span data-ttu-id="d0de2-140">Application/JSON.</span><span class="sxs-lookup"><span data-stu-id="d0de2-140">application/json.</span></span> <span data-ttu-id="d0de2-141">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="d0de2-141">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="d0de2-142">Aanvraagtekst</span><span class="sxs-lookup"><span data-stu-id="d0de2-142">Request body</span></span>
<span data-ttu-id="d0de2-143">Geef in de hoofdtekst van de aanvraag de waarden op voor de relevante velden die moeten worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="d0de2-143">In the request body, supply the values for the relevant fields that should be updated.</span></span>
<br><span data-ttu-id="d0de2-144">Bestaande eigenschappen die niet zijn opgenomen in de aanvraagtekst, behouden hun vorige waarden of worden herberekend op basis van wijzigingen in andere eigenschapswaarden.</span><span class="sxs-lookup"><span data-stu-id="d0de2-144">Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values.</span></span> 
<br><span data-ttu-id="d0de2-145">Voor de beste prestaties mag u geen bestaande waarden opnemen die niet zijn gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="d0de2-145">For best performance you shouldn't include existing values that haven't change.</span></span>

<span data-ttu-id="d0de2-146">Eigenschap</span><span class="sxs-lookup"><span data-stu-id="d0de2-146">Property</span></span> | <span data-ttu-id="d0de2-147">Type</span><span class="sxs-lookup"><span data-stu-id="d0de2-147">Type</span></span> | <span data-ttu-id="d0de2-148">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="d0de2-148">Description</span></span>
:---|:---|:---
<span data-ttu-id="d0de2-149">status</span><span class="sxs-lookup"><span data-stu-id="d0de2-149">status</span></span> | <span data-ttu-id="d0de2-150">Opsommings</span><span class="sxs-lookup"><span data-stu-id="d0de2-150">Enum</span></span> | <span data-ttu-id="d0de2-151">Geeft de huidige status van de waarschuwing op.</span><span class="sxs-lookup"><span data-stu-id="d0de2-151">Specifies the current status of the alert.</span></span> <span data-ttu-id="d0de2-152">Mogelijke waarden zijn: ```Active``` , ```Resolved``` en ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="d0de2-152">Possible values are: ```Active```, ```Resolved``` and ```Redirected```.</span></span>
<span data-ttu-id="d0de2-153">ToegewezenAan</span><span class="sxs-lookup"><span data-stu-id="d0de2-153">assignedTo</span></span> | <span data-ttu-id="d0de2-154">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="d0de2-154">string</span></span> | <span data-ttu-id="d0de2-155">Eigenaar van het incident.</span><span class="sxs-lookup"><span data-stu-id="d0de2-155">Owner of the incident.</span></span>
<span data-ttu-id="d0de2-156">Contactpersoonclassificatie</span><span class="sxs-lookup"><span data-stu-id="d0de2-156">classification</span></span> | <span data-ttu-id="d0de2-157">Opsommings</span><span class="sxs-lookup"><span data-stu-id="d0de2-157">Enum</span></span> | <span data-ttu-id="d0de2-158">Specificatie van de waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="d0de2-158">Specification of the alert.</span></span> <span data-ttu-id="d0de2-159">Mogelijke waarden zijn: ```Unknown``` , ```FalsePositive``` , ```TruePositive``` .</span><span class="sxs-lookup"><span data-stu-id="d0de2-159">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="d0de2-160">relevant</span><span class="sxs-lookup"><span data-stu-id="d0de2-160">determination</span></span> | <span data-ttu-id="d0de2-161">Opsommings</span><span class="sxs-lookup"><span data-stu-id="d0de2-161">Enum</span></span> | <span data-ttu-id="d0de2-162">Hiermee geeft u het bepalen van de waarschuwing op.</span><span class="sxs-lookup"><span data-stu-id="d0de2-162">Specifies the determination of the alert.</span></span> <span data-ttu-id="d0de2-163">Mogelijke waarden zijn: ```NotAvailable``` , ```Apt``` ,,, ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` , ```UnwantedSoftware``` , ```Other``` .</span><span class="sxs-lookup"><span data-stu-id="d0de2-163">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="d0de2-164">Tags</span><span class="sxs-lookup"><span data-stu-id="d0de2-164">tags</span></span> | <span data-ttu-id="d0de2-165">Lijst met tekenreeksen</span><span class="sxs-lookup"><span data-stu-id="d0de2-165">string List</span></span> | <span data-ttu-id="d0de2-166">Lijst met incident Tags.</span><span class="sxs-lookup"><span data-stu-id="d0de2-166">List of Incident tags.</span></span>



## <a name="response"></a><span data-ttu-id="d0de2-167">Na</span><span class="sxs-lookup"><span data-stu-id="d0de2-167">Response</span></span>
<span data-ttu-id="d0de2-168">Als dit is gelukt, retourneert deze methode 200 OK en de entiteit van het incident in de tekst van het antwoord met de bijgewerkte eigenschappen.</span><span class="sxs-lookup"><span data-stu-id="d0de2-168">If successful, this method returns 200 OK, and the incident entity in the response body with the updated properties.</span></span> <span data-ttu-id="d0de2-169">If incident met de opgegeven id niet gevonden-404 is niet gevonden.</span><span class="sxs-lookup"><span data-stu-id="d0de2-169">If incident with the specified id was not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="d0de2-170">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="d0de2-170">Example</span></span>

<span data-ttu-id="d0de2-171">**Webonderdeelverzoek**</span><span class="sxs-lookup"><span data-stu-id="d0de2-171">**Request**</span></span>

<span data-ttu-id="d0de2-172">Hier ziet u een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="d0de2-172">Here is an example of the request.</span></span>

```
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "TruePositive",
    "determination": "Malware",
    "tags": ["Yossi's playground", "Don't mess with the Zohan"]
}
```


## <a name="related-topic"></a><span data-ttu-id="d0de2-173">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="d0de2-173">Related topic</span></span>
- [<span data-ttu-id="d0de2-174">Api's voor incidenten</span><span class="sxs-lookup"><span data-stu-id="d0de2-174">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="d0de2-175">Lijst incidenten</span><span class="sxs-lookup"><span data-stu-id="d0de2-175">List incidents</span></span>](api-list-incidents.md)