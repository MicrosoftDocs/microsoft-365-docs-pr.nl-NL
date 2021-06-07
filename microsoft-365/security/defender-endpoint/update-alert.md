---
title: Api voor waarschuwingsentiteit bijwerken
description: Meer informatie over het bijwerken van een Waarschuwing van Microsoft Defender voor eindpunten met behulp van deze API. U kunt de eigenschappen status, bepaling, classificatie en toegewezen Aan bijwerken.
keywords: api's, graph api, ondersteunde api's, get, alert, information, id
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 043d423e1016d77cad4a175aa41718329f464252
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52768921"
---
# <a name="update-alert"></a><span data-ttu-id="ef78d-105">Waarschuwing bijwerken</span><span class="sxs-lookup"><span data-stu-id="ef78d-105">Update alert</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ef78d-106">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="ef78d-106">**Applies to:**</span></span>
- [<span data-ttu-id="ef78d-107">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="ef78d-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="ef78d-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ef78d-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="ef78d-109">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="ef78d-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ef78d-110">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="ef78d-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="ef78d-111">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="ef78d-111">API description</span></span>
<span data-ttu-id="ef78d-112">Updates van de eigenschappen van bestaande [waarschuwing](alerts.md).</span><span class="sxs-lookup"><span data-stu-id="ef78d-112">Updates properties of existing [Alert](alerts.md).</span></span>
<br><span data-ttu-id="ef78d-113">Het indienen **van opmerkingen** is beschikbaar met of zonder bij te werken eigenschappen.</span><span class="sxs-lookup"><span data-stu-id="ef78d-113">Submission of **comment** is available with or without updating properties.</span></span>
<br><span data-ttu-id="ef78d-114">Datumbare eigenschappen zijn: ```status``` ```determination``` , en ```classification``` ```assignedTo``` .</span><span class="sxs-lookup"><span data-stu-id="ef78d-114">Updatable properties are: ```status```, ```determination```, ```classification``` and ```assignedTo```.</span></span>


## <a name="limitations"></a><span data-ttu-id="ef78d-115">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="ef78d-115">Limitations</span></span>
1. <span data-ttu-id="ef78d-116">U kunt waarschuwingen bijwerken die beschikbaar zijn in de API.</span><span class="sxs-lookup"><span data-stu-id="ef78d-116">You can update alerts that available in the API.</span></span> <span data-ttu-id="ef78d-117">Zie [Lijstwaarschuwingen](get-alerts.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="ef78d-117">See [List Alerts](get-alerts.md) for more information.</span></span>
2. <span data-ttu-id="ef78d-118">Tariefbeperkingen voor deze API zijn 100 oproepen per minuut en 1500 oproepen per uur.</span><span class="sxs-lookup"><span data-stu-id="ef78d-118">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="ef78d-119">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="ef78d-119">Permissions</span></span>
<span data-ttu-id="ef78d-120">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="ef78d-120">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="ef78d-121">Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="ef78d-121">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="ef78d-122">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="ef78d-122">Permission type</span></span> |   <span data-ttu-id="ef78d-123">Machtiging</span><span class="sxs-lookup"><span data-stu-id="ef78d-123">Permission</span></span>  |   <span data-ttu-id="ef78d-124">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="ef78d-124">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="ef78d-125">Toepassing</span><span class="sxs-lookup"><span data-stu-id="ef78d-125">Application</span></span> |   <span data-ttu-id="ef78d-126">Alerts.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="ef78d-126">Alerts.ReadWrite.All</span></span> |  <span data-ttu-id="ef78d-127">'Alle waarschuwingen lezen en schrijven'</span><span class="sxs-lookup"><span data-stu-id="ef78d-127">'Read and write all alerts'</span></span>
<span data-ttu-id="ef78d-128">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="ef78d-128">Delegated (work or school account)</span></span> | <span data-ttu-id="ef78d-129">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="ef78d-129">Alert.ReadWrite</span></span> | <span data-ttu-id="ef78d-130">'Waarschuwingen lezen en schrijven'</span><span class="sxs-lookup"><span data-stu-id="ef78d-130">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="ef78d-131">Bij het verkrijgen van een token met gebruikersreferenties:</span><span class="sxs-lookup"><span data-stu-id="ef78d-131">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="ef78d-132">De gebruiker moet ten minste de volgende rolmachtiging hebben: 'Alerts investigation' (Zie Rollen maken [en](user-roles.md) beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="ef78d-132">The user needs to have at least the following role permission: 'Alerts investigation' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="ef78d-133">De gebruiker moet toegang hebben tot het apparaat dat aan de waarschuwing is gekoppeld, op basis van apparaatgroepinstellingen (Zie [Apparaatgroepen](machine-groups.md) maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="ef78d-133">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="ef78d-134">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="ef78d-134">HTTP request</span></span>
```
PATCH /api/alerts/{id}
```

## <a name="request-headers"></a><span data-ttu-id="ef78d-135">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="ef78d-135">Request headers</span></span>

<span data-ttu-id="ef78d-136">Naam</span><span class="sxs-lookup"><span data-stu-id="ef78d-136">Name</span></span> | <span data-ttu-id="ef78d-137">Type</span><span class="sxs-lookup"><span data-stu-id="ef78d-137">Type</span></span> | <span data-ttu-id="ef78d-138">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="ef78d-138">Description</span></span>
:---|:---|:---
<span data-ttu-id="ef78d-139">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="ef78d-139">Authorization</span></span> | <span data-ttu-id="ef78d-140">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="ef78d-140">String</span></span> | <span data-ttu-id="ef78d-141">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="ef78d-141">Bearer {token}.</span></span> <span data-ttu-id="ef78d-142">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="ef78d-142">**Required**.</span></span>
<span data-ttu-id="ef78d-143">Inhoudstype</span><span class="sxs-lookup"><span data-stu-id="ef78d-143">Content-Type</span></span> | <span data-ttu-id="ef78d-144">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="ef78d-144">String</span></span> | <span data-ttu-id="ef78d-145">toepassing/json.</span><span class="sxs-lookup"><span data-stu-id="ef78d-145">application/json.</span></span> <span data-ttu-id="ef78d-146">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="ef78d-146">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="ef78d-147">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="ef78d-147">Request body</span></span>
<span data-ttu-id="ef78d-148">In de aanvraagt u de waarden voor de relevante velden die moeten worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="ef78d-148">In the request body, supply the values for the relevant fields that should be updated.</span></span>
<br><span data-ttu-id="ef78d-149">Bestaande eigenschappen die niet in de aanvraag worden opgenomen, behouden hun vorige waarden of worden herberekend op basis van wijzigingen in andere eigenschapswaarden.</span><span class="sxs-lookup"><span data-stu-id="ef78d-149">Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values.</span></span> 
<br><span data-ttu-id="ef78d-150">Voor de beste prestaties moet u geen bestaande waarden opnemen die niet zijn gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="ef78d-150">For best performance you shouldn't include existing values that haven't change.</span></span>

<span data-ttu-id="ef78d-151">Eigenschap</span><span class="sxs-lookup"><span data-stu-id="ef78d-151">Property</span></span> | <span data-ttu-id="ef78d-152">Type</span><span class="sxs-lookup"><span data-stu-id="ef78d-152">Type</span></span> | <span data-ttu-id="ef78d-153">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="ef78d-153">Description</span></span>
:---|:---|:---
<span data-ttu-id="ef78d-154">status</span><span class="sxs-lookup"><span data-stu-id="ef78d-154">status</span></span> | <span data-ttu-id="ef78d-155">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="ef78d-155">String</span></span> | <span data-ttu-id="ef78d-156">Hiermee geeft u de huidige status van de waarschuwing op.</span><span class="sxs-lookup"><span data-stu-id="ef78d-156">Specifies the current status of the alert.</span></span> <span data-ttu-id="ef78d-157">De eigenschapswaarden zijn: 'Nieuw', 'InProgress' en 'Opgelost'.</span><span class="sxs-lookup"><span data-stu-id="ef78d-157">The property values are: 'New', 'InProgress' and 'Resolved'.</span></span>
<span data-ttu-id="ef78d-158">toegewezenTo</span><span class="sxs-lookup"><span data-stu-id="ef78d-158">assignedTo</span></span> | <span data-ttu-id="ef78d-159">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="ef78d-159">String</span></span> | <span data-ttu-id="ef78d-160">Eigenaar van de waarschuwing</span><span class="sxs-lookup"><span data-stu-id="ef78d-160">Owner of the alert</span></span>
<span data-ttu-id="ef78d-161">classificatie</span><span class="sxs-lookup"><span data-stu-id="ef78d-161">classification</span></span> | <span data-ttu-id="ef78d-162">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="ef78d-162">String</span></span> | <span data-ttu-id="ef78d-163">Hiermee geeft u de specificatie van de waarschuwing op.</span><span class="sxs-lookup"><span data-stu-id="ef78d-163">Specifies the specification of the alert.</span></span> <span data-ttu-id="ef78d-164">De eigenschapswaarden zijn: 'Onbekend', 'FalsePositive', 'TruePositive'.</span><span class="sxs-lookup"><span data-stu-id="ef78d-164">The property values are: 'Unknown', 'FalsePositive', 'TruePositive'.</span></span> 
<span data-ttu-id="ef78d-165">bepaling</span><span class="sxs-lookup"><span data-stu-id="ef78d-165">determination</span></span> | <span data-ttu-id="ef78d-166">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="ef78d-166">String</span></span> | <span data-ttu-id="ef78d-167">Hiermee geeft u de bepaling van de waarschuwing op.</span><span class="sxs-lookup"><span data-stu-id="ef78d-167">Specifies the determination of the alert.</span></span> <span data-ttu-id="ef78d-168">De eigenschapswaarden zijn: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'</span><span class="sxs-lookup"><span data-stu-id="ef78d-168">The property values are: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'</span></span>
<span data-ttu-id="ef78d-169">opmerking</span><span class="sxs-lookup"><span data-stu-id="ef78d-169">comment</span></span> | <span data-ttu-id="ef78d-170">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="ef78d-170">String</span></span> | <span data-ttu-id="ef78d-171">Opmerking die moet worden toegevoegd aan de waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="ef78d-171">Comment to be added to the alert.</span></span>

## <a name="response"></a><span data-ttu-id="ef78d-172">Antwoord</span><span class="sxs-lookup"><span data-stu-id="ef78d-172">Response</span></span>
<span data-ttu-id="ef78d-173">Als dit is gelukt, retourneert deze [](alerts.md) methode 200 OK en de waarschuwingsentiteit in de antwoordinstelling met de bijgewerkte eigenschappen.</span><span class="sxs-lookup"><span data-stu-id="ef78d-173">If successful, this method returns 200 OK, and the [alert](alerts.md) entity in the response body with the updated properties.</span></span> <span data-ttu-id="ef78d-174">Als een waarschuwing met de opgegeven id niet is gevonden- 404 Niet gevonden.</span><span class="sxs-lookup"><span data-stu-id="ef78d-174">If alert with the specified id was not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="ef78d-175">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="ef78d-175">Example</span></span>

<span data-ttu-id="ef78d-176">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="ef78d-176">**Request**</span></span>

<span data-ttu-id="ef78d-177">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="ef78d-177">Here is an example of the request.</span></span>

```http
PATCH https://api.securitycenter.microsoft.com/api/alerts/121688558380765161_2136280442
```

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "FalsePositive",
    "determination": "Malware",
    "comment": "Resolve my alert and assign to secop2"
}
```
