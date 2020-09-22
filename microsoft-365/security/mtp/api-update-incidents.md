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
ms.openlocfilehash: 8ad47453c7163bfac99c17f42986b818cdca603f
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203625"
---
# <a name="update-incidents-api"></a><span data-ttu-id="71746-104">API voor update van incidenten</span><span class="sxs-lookup"><span data-stu-id="71746-104">Update incidents API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="71746-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="71746-105">**Applies to:**</span></span>
- <span data-ttu-id="71746-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="71746-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="71746-107">Sommige informatie verhoudt zich tot een voorvrijgegeven product dat bij de commerciële versie van de commerciële versie mogelijk ingrijpend werd gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="71746-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="71746-108">Microsoft biedt geen garanties, expliciete of impliciete informatie met betrekking tot de informatie die u hier opgeeft.</span><span class="sxs-lookup"><span data-stu-id="71746-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


## <a name="api-description"></a><span data-ttu-id="71746-109">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="71746-109">API description</span></span>
<span data-ttu-id="71746-110">Hiermee worden de eigenschappen van een bestaand incident bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="71746-110">Updates properties of existing incident.</span></span>
<br><span data-ttu-id="71746-111">Bijwerkbare eigenschappen zijn: ```status``` , ```determination``` , ```classification``` ```assignedTo``` en ```tags``` .</span><span class="sxs-lookup"><span data-stu-id="71746-111">Updatable properties are: ```status```, ```determination```, ```classification```, ```assignedTo``` and ```tags```.</span></span>


## <a name="limitations"></a><span data-ttu-id="71746-112">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="71746-112">Limitations</span></span>
1. <span data-ttu-id="71746-113">Tarief beperkingen voor deze API zijn 50 oproepen per minuut en 1500-oproepen per uur.</span><span class="sxs-lookup"><span data-stu-id="71746-113">Rate limitations for this API are 50 calls per minute and 1500 calls per hour.</span></span>
2. <span data-ttu-id="71746-114">U kunt instellen ```determination``` dat alleen als de classificatie is ingesteld op TruePositive.</span><span class="sxs-lookup"><span data-stu-id="71746-114">You can set the ```determination``` only if the classification is set to TruePositive.</span></span>


## <a name="permissions"></a><span data-ttu-id="71746-115">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="71746-115">Permissions</span></span>
<span data-ttu-id="71746-116">U moet een van de volgende machtigingen hebben om deze API te kunnen bellen.</span><span class="sxs-lookup"><span data-stu-id="71746-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="71746-117">Voor meer informatie, waaronder de manier waarop u machtigingen kiest, raadpleegt u [de Api's Microsoft Threat Protection openen](api-access.md).</span><span class="sxs-lookup"><span data-stu-id="71746-117">To learn more, including how to choose permissions, see [Access the Microsoft Threat Protection APIs](api-access.md).</span></span>

<span data-ttu-id="71746-118">Type machtiging</span><span class="sxs-lookup"><span data-stu-id="71746-118">Permission type</span></span> |   <span data-ttu-id="71746-119">Machtigingsset</span><span class="sxs-lookup"><span data-stu-id="71746-119">Permission</span></span>  |   <span data-ttu-id="71746-120">Weergavenaam van de machtiging</span><span class="sxs-lookup"><span data-stu-id="71746-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="71746-121">Toepassing</span><span class="sxs-lookup"><span data-stu-id="71746-121">Application</span></span> |   <span data-ttu-id="71746-122">Incident. ReadWrite. all</span><span class="sxs-lookup"><span data-stu-id="71746-122">Incident.ReadWrite.All</span></span> |    <span data-ttu-id="71746-123">' Alle incidenten lezen en schrijven '</span><span class="sxs-lookup"><span data-stu-id="71746-123">'Read and write all incidents'</span></span>
<span data-ttu-id="71746-124">Gedelegeerd (werk-of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="71746-124">Delegated (work or school account)</span></span> | <span data-ttu-id="71746-125">Incident. ReadWrite</span><span class="sxs-lookup"><span data-stu-id="71746-125">Incident.ReadWrite</span></span> | <span data-ttu-id="71746-126">' Lees-en schrijf incident '</span><span class="sxs-lookup"><span data-stu-id="71746-126">'Read and write incidents'</span></span>

>[!NOTE]
> <span data-ttu-id="71746-127">Bij het verkrijgen van een token met behulp van gebruikersreferenties:</span><span class="sxs-lookup"><span data-stu-id="71746-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="71746-128">De gebruiker moet zijn gemachtigd om het incident in de portal bij te werken.</span><span class="sxs-lookup"><span data-stu-id="71746-128">The user needs to have permission to update the incident in the portal.</span></span>


## <a name="http-request"></a><span data-ttu-id="71746-129">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="71746-129">HTTP request</span></span>

```
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a><span data-ttu-id="71746-130">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="71746-130">Request headers</span></span>

<span data-ttu-id="71746-131">Naam</span><span class="sxs-lookup"><span data-stu-id="71746-131">Name</span></span> | <span data-ttu-id="71746-132">Type</span><span class="sxs-lookup"><span data-stu-id="71746-132">Type</span></span> | <span data-ttu-id="71746-133">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="71746-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="71746-134">Bevoegdheid</span><span class="sxs-lookup"><span data-stu-id="71746-134">Authorization</span></span> | <span data-ttu-id="71746-135">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="71746-135">String</span></span> | <span data-ttu-id="71746-136">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="71746-136">Bearer {token}.</span></span> <span data-ttu-id="71746-137">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="71746-137">**Required**.</span></span>
<span data-ttu-id="71746-138">Inhouds type</span><span class="sxs-lookup"><span data-stu-id="71746-138">Content-Type</span></span> | <span data-ttu-id="71746-139">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="71746-139">String</span></span> | <span data-ttu-id="71746-140">Application/JSON.</span><span class="sxs-lookup"><span data-stu-id="71746-140">application/json.</span></span> <span data-ttu-id="71746-141">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="71746-141">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="71746-142">Aanvraagtekst</span><span class="sxs-lookup"><span data-stu-id="71746-142">Request body</span></span>
<span data-ttu-id="71746-143">Geef in de hoofdtekst van de aanvraag de waarden op voor de relevante velden die moeten worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="71746-143">In the request body, supply the values for the relevant fields that should be updated.</span></span>
<br><span data-ttu-id="71746-144">Bestaande eigenschappen die niet zijn opgenomen in de aanvraagtekst, behouden hun vorige waarden of worden herberekend op basis van wijzigingen in andere eigenschapswaarden.</span><span class="sxs-lookup"><span data-stu-id="71746-144">Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values.</span></span> 
<br><span data-ttu-id="71746-145">Voor de beste prestaties mag u geen bestaande waarden opnemen die niet zijn gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="71746-145">For best performance you shouldn't include existing values that haven't change.</span></span>

<span data-ttu-id="71746-146">Eigenschap</span><span class="sxs-lookup"><span data-stu-id="71746-146">Property</span></span> | <span data-ttu-id="71746-147">Type</span><span class="sxs-lookup"><span data-stu-id="71746-147">Type</span></span> | <span data-ttu-id="71746-148">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="71746-148">Description</span></span>
:---|:---|:---
<span data-ttu-id="71746-149">status</span><span class="sxs-lookup"><span data-stu-id="71746-149">status</span></span> | <span data-ttu-id="71746-150">Opsommings</span><span class="sxs-lookup"><span data-stu-id="71746-150">Enum</span></span> | <span data-ttu-id="71746-151">Geeft de huidige status van de waarschuwing op.</span><span class="sxs-lookup"><span data-stu-id="71746-151">Specifies the current status of the alert.</span></span> <span data-ttu-id="71746-152">Mogelijke waarden zijn: ```Active``` , ```Resolved``` en ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="71746-152">Possible values are: ```Active```, ```Resolved``` and ```Redirected```.</span></span>
<span data-ttu-id="71746-153">ToegewezenAan</span><span class="sxs-lookup"><span data-stu-id="71746-153">assignedTo</span></span> | <span data-ttu-id="71746-154">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="71746-154">string</span></span> | <span data-ttu-id="71746-155">Eigenaar van het incident.</span><span class="sxs-lookup"><span data-stu-id="71746-155">Owner of the incident.</span></span>
<span data-ttu-id="71746-156">Contactpersoonclassificatie</span><span class="sxs-lookup"><span data-stu-id="71746-156">classification</span></span> | <span data-ttu-id="71746-157">Opsommings</span><span class="sxs-lookup"><span data-stu-id="71746-157">Enum</span></span> | <span data-ttu-id="71746-158">Specificatie van de waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="71746-158">Specification of the alert.</span></span> <span data-ttu-id="71746-159">Mogelijke waarden zijn: ```Unknown``` , ```FalsePositive``` , ```TruePositive``` .</span><span class="sxs-lookup"><span data-stu-id="71746-159">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="71746-160">relevant</span><span class="sxs-lookup"><span data-stu-id="71746-160">determination</span></span> | <span data-ttu-id="71746-161">Opsommings</span><span class="sxs-lookup"><span data-stu-id="71746-161">Enum</span></span> | <span data-ttu-id="71746-162">Hiermee geeft u het bepalen van de waarschuwing op.</span><span class="sxs-lookup"><span data-stu-id="71746-162">Specifies the determination of the alert.</span></span> <span data-ttu-id="71746-163">Mogelijke waarden zijn: ```NotAvailable``` , ```Apt``` ,,, ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` , ```UnwantedSoftware``` , ```Other``` .</span><span class="sxs-lookup"><span data-stu-id="71746-163">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="71746-164">Tags</span><span class="sxs-lookup"><span data-stu-id="71746-164">tags</span></span> | <span data-ttu-id="71746-165">Lijst met tekenreeksen</span><span class="sxs-lookup"><span data-stu-id="71746-165">string List</span></span> | <span data-ttu-id="71746-166">Lijst met incident Tags.</span><span class="sxs-lookup"><span data-stu-id="71746-166">List of Incident tags.</span></span>



## <a name="response"></a><span data-ttu-id="71746-167">Na</span><span class="sxs-lookup"><span data-stu-id="71746-167">Response</span></span>
<span data-ttu-id="71746-168">Als dit is gelukt, retourneert deze methode 200 OK en de entiteit van het incident in de tekst van het antwoord met de bijgewerkte eigenschappen.</span><span class="sxs-lookup"><span data-stu-id="71746-168">If successful, this method returns 200 OK, and the incident entity in the response body with the updated properties.</span></span> <span data-ttu-id="71746-169">If incident met de opgegeven id niet gevonden-404 is niet gevonden.</span><span class="sxs-lookup"><span data-stu-id="71746-169">If incident with the specified id was not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="71746-170">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="71746-170">Example</span></span>

<span data-ttu-id="71746-171">**Webonderdeelverzoek**</span><span class="sxs-lookup"><span data-stu-id="71746-171">**Request**</span></span>

<span data-ttu-id="71746-172">Hier ziet u een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="71746-172">Here is an example of the request.</span></span>

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


## <a name="related-topic"></a><span data-ttu-id="71746-173">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="71746-173">Related topic</span></span>
- [<span data-ttu-id="71746-174">API's voor incidenten</span><span class="sxs-lookup"><span data-stu-id="71746-174">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="71746-175">Lijst met incidenten</span><span class="sxs-lookup"><span data-stu-id="71746-175">List incidents</span></span>](api-list-incidents.md)
