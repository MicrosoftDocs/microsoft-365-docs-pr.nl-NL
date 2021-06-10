---
title: API voor indicatoren importeren
description: Meer informatie over het gebruik van de batch Indicator API importeren in Microsoft Defender voor Eindpunt.
keywords: api's, ondersteunde api's, submit, ti, indicator, update
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
ms.openlocfilehash: b1777adf7b97083fae2daf4213a4bda742ba097d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198243"
---
# <a name="import-indicators-api"></a><span data-ttu-id="a8fc7-104">API voor indicatoren importeren</span><span class="sxs-lookup"><span data-stu-id="a8fc7-104">Import Indicators API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a8fc7-105">**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="a8fc7-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="a8fc7-106">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="a8fc7-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a8fc7-107">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="a8fc7-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="a8fc7-108">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="a8fc7-108">API description</span></span>
<span data-ttu-id="a8fc7-109">Verzend of updates [](ti-indicator.md) batch van indicatorentiteiten.</span><span class="sxs-lookup"><span data-stu-id="a8fc7-109">Submits or Updates batch of [Indicator](ti-indicator.md) entities.</span></span>
<br><span data-ttu-id="a8fc7-110">CIDR-notatie voor IPs wordt niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="a8fc7-110">CIDR notation for IPs is not supported.</span></span>

## <a name="limitations"></a><span data-ttu-id="a8fc7-111">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="a8fc7-111">Limitations</span></span>
1. <span data-ttu-id="a8fc7-112">Tariefbeperkingen voor deze API zijn 30 oproepen per minuut.</span><span class="sxs-lookup"><span data-stu-id="a8fc7-112">Rate limitations for this API are 30 calls per minute.</span></span>
2. <span data-ttu-id="a8fc7-113">Er is een limiet van 15.000 actieve [indicatoren](ti-indicator.md) per tenant.</span><span class="sxs-lookup"><span data-stu-id="a8fc7-113">There is a limit of 15,000 active [Indicators](ti-indicator.md) per tenant.</span></span> 
3. <span data-ttu-id="a8fc7-114">De maximale batchgrootte voor één API-oproep is 500.</span><span class="sxs-lookup"><span data-stu-id="a8fc7-114">Maximum batch size for one API call is 500.</span></span>

## <a name="permissions"></a><span data-ttu-id="a8fc7-115">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="a8fc7-115">Permissions</span></span>
<span data-ttu-id="a8fc7-116">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="a8fc7-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="a8fc7-117">Zie Aan de slag voor meer informatie, inclusief het kiezen van [machtigingen.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="a8fc7-117">To learn more, including how to choose permissions, see [Get started](apis-intro.md)</span></span>

<span data-ttu-id="a8fc7-118">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="a8fc7-118">Permission type</span></span> |   <span data-ttu-id="a8fc7-119">Machtiging</span><span class="sxs-lookup"><span data-stu-id="a8fc7-119">Permission</span></span>  |   <span data-ttu-id="a8fc7-120">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="a8fc7-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="a8fc7-121">Toepassing</span><span class="sxs-lookup"><span data-stu-id="a8fc7-121">Application</span></span> |   <span data-ttu-id="a8fc7-122">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="a8fc7-122">Ti.ReadWrite</span></span> |  <span data-ttu-id="a8fc7-123">'Indicatoren lezen en schrijven'</span><span class="sxs-lookup"><span data-stu-id="a8fc7-123">'Read and write Indicators'</span></span>
<span data-ttu-id="a8fc7-124">Toepassing</span><span class="sxs-lookup"><span data-stu-id="a8fc7-124">Application</span></span> |   <span data-ttu-id="a8fc7-125">Ti.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="a8fc7-125">Ti.ReadWrite.All</span></span> |  <span data-ttu-id="a8fc7-126">'Alle indicatoren lezen en schrijven'</span><span class="sxs-lookup"><span data-stu-id="a8fc7-126">'Read and write All Indicators'</span></span>
<span data-ttu-id="a8fc7-127">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="a8fc7-127">Delegated (work or school account)</span></span> |    <span data-ttu-id="a8fc7-128">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="a8fc7-128">Ti.ReadWrite</span></span> |  <span data-ttu-id="a8fc7-129">'Indicatoren lezen en schrijven'</span><span class="sxs-lookup"><span data-stu-id="a8fc7-129">'Read and write Indicators'</span></span>


## <a name="http-request"></a><span data-ttu-id="a8fc7-130">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="a8fc7-130">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/indicators/import
```

## <a name="request-headers"></a><span data-ttu-id="a8fc7-131">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="a8fc7-131">Request headers</span></span>

<span data-ttu-id="a8fc7-132">Naam</span><span class="sxs-lookup"><span data-stu-id="a8fc7-132">Name</span></span> | <span data-ttu-id="a8fc7-133">Type</span><span class="sxs-lookup"><span data-stu-id="a8fc7-133">Type</span></span> | <span data-ttu-id="a8fc7-134">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="a8fc7-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="a8fc7-135">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="a8fc7-135">Authorization</span></span> | <span data-ttu-id="a8fc7-136">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="a8fc7-136">String</span></span> | <span data-ttu-id="a8fc7-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="a8fc7-137">Bearer {token}.</span></span> <span data-ttu-id="a8fc7-138">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="a8fc7-138">**Required**.</span></span>
<span data-ttu-id="a8fc7-139">Inhoudstype</span><span class="sxs-lookup"><span data-stu-id="a8fc7-139">Content-Type</span></span> | <span data-ttu-id="a8fc7-140">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="a8fc7-140">string</span></span> | <span data-ttu-id="a8fc7-141">toepassing/json.</span><span class="sxs-lookup"><span data-stu-id="a8fc7-141">application/json.</span></span> <span data-ttu-id="a8fc7-142">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="a8fc7-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="a8fc7-143">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="a8fc7-143">Request body</span></span>
<span data-ttu-id="a8fc7-144">In de objectaanvraag moet u een JSON-object de volgende parameters geven:</span><span class="sxs-lookup"><span data-stu-id="a8fc7-144">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="a8fc7-145">Parameter</span><span class="sxs-lookup"><span data-stu-id="a8fc7-145">Parameter</span></span> | <span data-ttu-id="a8fc7-146">Type</span><span class="sxs-lookup"><span data-stu-id="a8fc7-146">Type</span></span>    | <span data-ttu-id="a8fc7-147">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="a8fc7-147">Description</span></span>
:---|:---|:---
<span data-ttu-id="a8fc7-148">Indicatoren</span><span class="sxs-lookup"><span data-stu-id="a8fc7-148">Indicators</span></span> | <span data-ttu-id="a8fc7-149">Lijst<[indicator](ti-indicator.md)></span><span class="sxs-lookup"><span data-stu-id="a8fc7-149">List<[Indicator](ti-indicator.md)></span></span> | <span data-ttu-id="a8fc7-150">Lijst met [indicatoren](ti-indicator.md).</span><span class="sxs-lookup"><span data-stu-id="a8fc7-150">List of [Indicators](ti-indicator.md).</span></span> <span data-ttu-id="a8fc7-151">**Vereist**</span><span class="sxs-lookup"><span data-stu-id="a8fc7-151">**Required**</span></span>


## <a name="response"></a><span data-ttu-id="a8fc7-152">Antwoord</span><span class="sxs-lookup"><span data-stu-id="a8fc7-152">Response</span></span>
- <span data-ttu-id="a8fc7-153">Als dit is gelukt, retourneert deze methode 200 - OK-antwoordcode met een lijst met importresultaten per indicator, zie voorbeeld hieronder.</span><span class="sxs-lookup"><span data-stu-id="a8fc7-153">If successful, this method returns 200 - OK response code with a list of import results per indicator, see example below.</span></span>
- <span data-ttu-id="a8fc7-154">Als dit niet is gelukt: met deze methode wordt 400 - Slecht verzoek als return gebruikt.</span><span class="sxs-lookup"><span data-stu-id="a8fc7-154">If not successful: this method return 400 - Bad Request.</span></span> <span data-ttu-id="a8fc7-155">Een slechte aanvraag geeft meestal een onjuiste body aan.</span><span class="sxs-lookup"><span data-stu-id="a8fc7-155">Bad request usually indicates incorrect body.</span></span>

## <a name="example"></a><span data-ttu-id="a8fc7-156">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="a8fc7-156">Example</span></span>

<span data-ttu-id="a8fc7-157">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="a8fc7-157">**Request**</span></span>

<span data-ttu-id="a8fc7-158">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="a8fc7-158">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/indicators/import
```

```json
{
    "Indicators":
    [
        {
            "indicatorValue": "220e7d15b011d7fac48f2bd61114db1022197f7f",
            "indicatorType": "FileSha1",
            "title": "demo",
            "application": "demo-test",
            "expirationTime": "2021-12-12T00:00:00Z",
            "action": "Alert",
            "severity": "Informational",
            "description": "demo2",
            "recommendedActions": "nothing",
            "rbacGroupNames": ["group1", "group2"]
        },
        {
            "indicatorValue": "2233223322332233223322332233223322332233223322332233223322332222",
            "indicatorType": "FileSha256",
            "title": "demo2",
            "application": "demo-test2",
            "expirationTime": "2021-12-12T00:00:00Z",
            "action": "Alert",
            "severity": "Medium",
            "description": "demo2",
            "recommendedActions": "nothing",
            "rbacGroupNames": []
        }
    ]
}
```

<span data-ttu-id="a8fc7-159">**Antwoord**</span><span class="sxs-lookup"><span data-stu-id="a8fc7-159">**Response**</span></span>

<span data-ttu-id="a8fc7-160">Hier is een voorbeeld van het antwoord.</span><span class="sxs-lookup"><span data-stu-id="a8fc7-160">Here is an example of the response.</span></span>

```json
{
    "value": [
        {
            "id": "2841",
            "indicator": "220e7d15b011d7fac48f2bd61114db1022197f7f",
            "isFailed": false,
            "failureReason": null
        },
        {
            "id": "2842",
            "indicator": "2233223322332233223322332233223322332233223322332233223322332222",
            "isFailed": false,
            "failureReason": null
        }
    ]
}
```

## <a name="related-topic"></a><span data-ttu-id="a8fc7-161">Verwant onderwerp</span><span class="sxs-lookup"><span data-stu-id="a8fc7-161">Related topic</span></span>
- [<span data-ttu-id="a8fc7-162">Indicatoren beheren</span><span class="sxs-lookup"><span data-stu-id="a8fc7-162">Manage indicators</span></span>](manage-indicators.md)
