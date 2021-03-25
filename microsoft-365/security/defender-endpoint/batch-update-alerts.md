---
title: Batch Update alert entities API
description: Meer informatie over het bijwerken van waarschuwingen van Microsoft Defender voor eindpunten in een batch met deze API. U kunt de eigenschappen status, bepaling, classificatie en toegewezen Aan bijwerken.
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
ms.technology: mde
ms.openlocfilehash: db745c1b12c64baff5bf2c0a212446ce0f773709
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166682"
---
# <a name="batch-update-alerts"></a><span data-ttu-id="f6496-105">Batchupdatewaarschuwingen</span><span class="sxs-lookup"><span data-stu-id="f6496-105">Batch update alerts</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="f6496-106">**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="f6496-106">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span></span>

- <span data-ttu-id="f6496-107">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="f6496-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f6496-108">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="f6496-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="f6496-109">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="f6496-109">API description</span></span>
<span data-ttu-id="f6496-110">De eigenschappen van een batch bestaande waarschuwingen [worden bijgewerkt.](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="f6496-110">Updates properties of a batch of existing [Alerts](alerts.md).</span></span>
<br><span data-ttu-id="f6496-111">Het indienen **van opmerkingen** is beschikbaar met of zonder bij te werken eigenschappen.</span><span class="sxs-lookup"><span data-stu-id="f6496-111">Submission of **comment** is available with or without updating properties.</span></span>
<br><span data-ttu-id="f6496-112">Datumbare eigenschappen zijn: `status` `determination` , en `classification` `assignedTo` .</span><span class="sxs-lookup"><span data-stu-id="f6496-112">Updatable properties are: `status`, `determination`, `classification` and `assignedTo`.</span></span>


## <a name="limitations"></a><span data-ttu-id="f6496-113">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="f6496-113">Limitations</span></span>
1. <span data-ttu-id="f6496-114">U kunt waarschuwingen bijwerken die beschikbaar zijn in de API.</span><span class="sxs-lookup"><span data-stu-id="f6496-114">You can update alerts that are available in the API.</span></span> <span data-ttu-id="f6496-115">Zie [Lijstwaarschuwingen](get-alerts.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="f6496-115">See [List Alerts](get-alerts.md) for more information.</span></span>
2. <span data-ttu-id="f6496-116">Tariefbeperkingen voor deze API zijn 10 oproepen per minuut en 500 oproepen per uur.</span><span class="sxs-lookup"><span data-stu-id="f6496-116">Rate limitations for this API are 10 calls per minute and 500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="f6496-117">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="f6496-117">Permissions</span></span>
<span data-ttu-id="f6496-118">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="f6496-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="f6496-119">Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="f6496-119">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="f6496-120">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="f6496-120">Permission type</span></span> |   <span data-ttu-id="f6496-121">Machtiging</span><span class="sxs-lookup"><span data-stu-id="f6496-121">Permission</span></span>  |   <span data-ttu-id="f6496-122">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="f6496-122">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="f6496-123">Toepassing</span><span class="sxs-lookup"><span data-stu-id="f6496-123">Application</span></span> |   <span data-ttu-id="f6496-124">Alerts.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="f6496-124">Alerts.ReadWrite.All</span></span> |  <span data-ttu-id="f6496-125">'Alle waarschuwingen lezen en schrijven'</span><span class="sxs-lookup"><span data-stu-id="f6496-125">'Read and write all alerts'</span></span>
<span data-ttu-id="f6496-126">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="f6496-126">Delegated (work or school account)</span></span> | <span data-ttu-id="f6496-127">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="f6496-127">Alert.ReadWrite</span></span> | <span data-ttu-id="f6496-128">'Waarschuwingen lezen en schrijven'</span><span class="sxs-lookup"><span data-stu-id="f6496-128">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="f6496-129">Bij het verkrijgen van een token met gebruikersreferenties:</span><span class="sxs-lookup"><span data-stu-id="f6496-129">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="f6496-130">De gebruiker moet ten minste de volgende rolmachtiging hebben: 'Alerts investigation' (Zie Rollen maken [en](user-roles.md) beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="f6496-130">The user needs to have at least the following role permission: 'Alerts investigation' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="f6496-131">De gebruiker moet toegang hebben tot het apparaat dat aan de waarschuwing is gekoppeld, op basis van apparaatgroepinstellingen (Zie [Apparaatgroepen](machine-groups.md) maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="f6496-131">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="f6496-132">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="f6496-132">HTTP request</span></span>
```http
POST /api/alerts/batchUpdate
```

## <a name="request-headers"></a><span data-ttu-id="f6496-133">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="f6496-133">Request headers</span></span>

<span data-ttu-id="f6496-134">Naam</span><span class="sxs-lookup"><span data-stu-id="f6496-134">Name</span></span> | <span data-ttu-id="f6496-135">Type</span><span class="sxs-lookup"><span data-stu-id="f6496-135">Type</span></span> | <span data-ttu-id="f6496-136">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="f6496-136">Description</span></span>
:---|:---|:---
<span data-ttu-id="f6496-137">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="f6496-137">Authorization</span></span> | <span data-ttu-id="f6496-138">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f6496-138">String</span></span> | <span data-ttu-id="f6496-139">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="f6496-139">Bearer {token}.</span></span> <span data-ttu-id="f6496-140">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="f6496-140">**Required**.</span></span>
<span data-ttu-id="f6496-141">Inhoudstype</span><span class="sxs-lookup"><span data-stu-id="f6496-141">Content-Type</span></span> | <span data-ttu-id="f6496-142">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f6496-142">String</span></span> | <span data-ttu-id="f6496-143">toepassing/json.</span><span class="sxs-lookup"><span data-stu-id="f6496-143">application/json.</span></span> <span data-ttu-id="f6496-144">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="f6496-144">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="f6496-145">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="f6496-145">Request body</span></span>
<span data-ttu-id="f6496-146">In de aanvraag-body geeft u de 1D's op van de waarschuwingen die moeten worden bijgewerkt en de waarden van de relevante velden die u wilt bijwerken voor deze waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="f6496-146">In the request body, supply the IDs of the alerts to be updated and the values of the relevant fields that you wish to update for these alerts.</span></span>
<br><span data-ttu-id="f6496-147">Bestaande eigenschappen die niet in de aanvraag worden opgenomen, behouden hun vorige waarden of worden herberekend op basis van wijzigingen in andere eigenschapswaarden.</span><span class="sxs-lookup"><span data-stu-id="f6496-147">Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values.</span></span> 
<br><span data-ttu-id="f6496-148">Voor de beste prestaties moet u geen bestaande waarden opnemen die niet zijn gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="f6496-148">For best performance you shouldn't include existing values that haven't changed.</span></span>

<span data-ttu-id="f6496-149">Eigenschap</span><span class="sxs-lookup"><span data-stu-id="f6496-149">Property</span></span> | <span data-ttu-id="f6496-150">Type</span><span class="sxs-lookup"><span data-stu-id="f6496-150">Type</span></span> | <span data-ttu-id="f6496-151">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="f6496-151">Description</span></span>
:---|:---|:---
<span data-ttu-id="f6496-152">alertIds</span><span class="sxs-lookup"><span data-stu-id="f6496-152">alertIds</span></span> | <span data-ttu-id="f6496-153">&lt;Lijstreeks&gt;</span><span class="sxs-lookup"><span data-stu-id="f6496-153">List&lt;String&gt;</span></span>| <span data-ttu-id="f6496-154">Een lijst met de ID's van de waarschuwingen die moeten worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="f6496-154">A list of the IDs of the alerts to be updated.</span></span> <span data-ttu-id="f6496-155">**Vereist**</span><span class="sxs-lookup"><span data-stu-id="f6496-155">**Required**</span></span>
<span data-ttu-id="f6496-156">status</span><span class="sxs-lookup"><span data-stu-id="f6496-156">status</span></span> | <span data-ttu-id="f6496-157">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f6496-157">String</span></span> | <span data-ttu-id="f6496-158">Hiermee geeft u de bijgewerkte status van de opgegeven waarschuwingen op.</span><span class="sxs-lookup"><span data-stu-id="f6496-158">Specifies the updated status of the specified alerts.</span></span> <span data-ttu-id="f6496-159">De eigenschapswaarden zijn: 'Nieuw', 'InProgress' en 'Opgelost'.</span><span class="sxs-lookup"><span data-stu-id="f6496-159">The property values are: 'New', 'InProgress' and 'Resolved'.</span></span>
<span data-ttu-id="f6496-160">toegewezenTo</span><span class="sxs-lookup"><span data-stu-id="f6496-160">assignedTo</span></span> | <span data-ttu-id="f6496-161">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f6496-161">String</span></span> | <span data-ttu-id="f6496-162">Eigenaar van de opgegeven waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="f6496-162">Owner of the specified alerts</span></span>
<span data-ttu-id="f6496-163">classificatie</span><span class="sxs-lookup"><span data-stu-id="f6496-163">classification</span></span> | <span data-ttu-id="f6496-164">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f6496-164">String</span></span> | <span data-ttu-id="f6496-165">Hiermee geeft u de specificatie van de opgegeven waarschuwingen op.</span><span class="sxs-lookup"><span data-stu-id="f6496-165">Specifies the specification of the specified alerts.</span></span> <span data-ttu-id="f6496-166">De eigenschapswaarden zijn: 'Onbekend', 'FalsePositive', 'TruePositive'.</span><span class="sxs-lookup"><span data-stu-id="f6496-166">The property values are: 'Unknown', 'FalsePositive', 'TruePositive'.</span></span> 
<span data-ttu-id="f6496-167">bepaling</span><span class="sxs-lookup"><span data-stu-id="f6496-167">determination</span></span> | <span data-ttu-id="f6496-168">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f6496-168">String</span></span> | <span data-ttu-id="f6496-169">Hiermee geeft u de bepaling van de opgegeven waarschuwingen op.</span><span class="sxs-lookup"><span data-stu-id="f6496-169">Specifies the determination of the specified alerts.</span></span> <span data-ttu-id="f6496-170">De eigenschapswaarden zijn: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'</span><span class="sxs-lookup"><span data-stu-id="f6496-170">The property values are: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'</span></span>
<span data-ttu-id="f6496-171">opmerking</span><span class="sxs-lookup"><span data-stu-id="f6496-171">comment</span></span> | <span data-ttu-id="f6496-172">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f6496-172">String</span></span> | <span data-ttu-id="f6496-173">Opmerking die moet worden toegevoegd aan de opgegeven waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="f6496-173">Comment to be added to the specified alerts.</span></span>

## <a name="response"></a><span data-ttu-id="f6496-174">Antwoord</span><span class="sxs-lookup"><span data-stu-id="f6496-174">Response</span></span>
<span data-ttu-id="f6496-175">Als dit is gelukt, retourneert deze methode 200 OK, met een lege antwoord body.</span><span class="sxs-lookup"><span data-stu-id="f6496-175">If successful, this method returns 200 OK, with an empty response body.</span></span>


## <a name="example"></a><span data-ttu-id="f6496-176">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="f6496-176">Example</span></span>

<span data-ttu-id="f6496-177">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="f6496-177">**Request**</span></span>

<span data-ttu-id="f6496-178">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="f6496-178">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/alerts/batchUpdate
```

```json
{
    "alertIds": ["da637399794050273582_760707377", "da637399989469816469_51697947354"],
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "FalsePositive",
    "determination": "Malware",
    "comment": "Resolve my alert and assign to secop2"
}
```
