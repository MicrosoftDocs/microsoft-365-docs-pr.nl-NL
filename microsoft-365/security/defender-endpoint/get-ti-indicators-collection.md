---
title: Lijstindicatoren API
description: Meer informatie over het gebruik van de LIJSTINDICATOREN-API om een verzameling van alle actieve indicatoren in Microsoft Defender voor eindpunt op te halen.
keywords: api's, openbare api, ondersteunde api's, indicatorenverzameling
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: d9ec8610957af0bc7741848e7c7bd4fe850f5e32
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770420"
---
# <a name="list-indicators-api"></a><span data-ttu-id="21d8f-104">Lijstindicatoren API</span><span class="sxs-lookup"><span data-stu-id="21d8f-104">List Indicators API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="21d8f-105">**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="21d8f-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="21d8f-106">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="21d8f-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="21d8f-107">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="21d8f-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="21d8f-108">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="21d8f-108">API description</span></span>
<span data-ttu-id="21d8f-109">Hiermee wordt een verzameling met alle actieve indicatoren [opgehaald.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="21d8f-109">Retrieves a collection of all active [Indicators](ti-indicator.md).</span></span>
<br><span data-ttu-id="21d8f-110">Ondersteunt [OData V4-query's.](https://www.odata.org/documentation/)</span><span class="sxs-lookup"><span data-stu-id="21d8f-110">Supports [OData V4 queries](https://www.odata.org/documentation/).</span></span>
<br><span data-ttu-id="21d8f-111">De query van OData ```$filter``` wordt ondersteund op: ```indicatorValue``` , , , en ```indicatorType``` ```creationTimeDateTimeUtc``` ```createdBy``` ```action``` ```severity``` eigenschappen.</span><span class="sxs-lookup"><span data-stu-id="21d8f-111">The OData's ```$filter``` query is supported on: ```indicatorValue```, ```indicatorType```, ```creationTimeDateTimeUtc```, ```createdBy```, ```action``` and ```severity``` properties.</span></span>
<br><span data-ttu-id="21d8f-112">Zie voorbeelden bij [OData-query's met Microsoft Defender voor Eindpunt](exposed-apis-odata-samples.md)</span><span class="sxs-lookup"><span data-stu-id="21d8f-112">See examples at [OData queries with Microsoft Defender for Endpoint](exposed-apis-odata-samples.md)</span></span>


## <a name="limitations"></a><span data-ttu-id="21d8f-113">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="21d8f-113">Limitations</span></span>
1. <span data-ttu-id="21d8f-114">Tariefbeperkingen voor deze API zijn 100 oproepen per minuut en 1500 oproepen per uur.</span><span class="sxs-lookup"><span data-stu-id="21d8f-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span> 


## <a name="permissions"></a><span data-ttu-id="21d8f-115">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="21d8f-115">Permissions</span></span>
<span data-ttu-id="21d8f-116">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="21d8f-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="21d8f-117">Zie Aan de slag voor meer informatie, inclusief het kiezen van [machtigingen.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="21d8f-117">To learn more, including how to choose permissions, see [Get started](apis-intro.md)</span></span>

<span data-ttu-id="21d8f-118">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="21d8f-118">Permission type</span></span> |   <span data-ttu-id="21d8f-119">Machtiging</span><span class="sxs-lookup"><span data-stu-id="21d8f-119">Permission</span></span>  |   <span data-ttu-id="21d8f-120">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="21d8f-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="21d8f-121">Toepassing</span><span class="sxs-lookup"><span data-stu-id="21d8f-121">Application</span></span> |   <span data-ttu-id="21d8f-122">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="21d8f-122">Ti.ReadWrite</span></span> |  <span data-ttu-id="21d8f-123">'Indicatoren lezen en schrijven'</span><span class="sxs-lookup"><span data-stu-id="21d8f-123">'Read and write Indicators'</span></span>
<span data-ttu-id="21d8f-124">Toepassing</span><span class="sxs-lookup"><span data-stu-id="21d8f-124">Application</span></span> |   <span data-ttu-id="21d8f-125">Ti.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="21d8f-125">Ti.ReadWrite.All</span></span> |  <span data-ttu-id="21d8f-126">'Alle indicatoren lezen en schrijven'</span><span class="sxs-lookup"><span data-stu-id="21d8f-126">'Read and write All Indicators'</span></span>
<span data-ttu-id="21d8f-127">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="21d8f-127">Delegated (work or school account)</span></span> |    <span data-ttu-id="21d8f-128">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="21d8f-128">Ti.ReadWrite</span></span> |  <span data-ttu-id="21d8f-129">'Indicatoren lezen en schrijven'</span><span class="sxs-lookup"><span data-stu-id="21d8f-129">'Read and write Indicators'</span></span>

## <a name="http-request"></a><span data-ttu-id="21d8f-130">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="21d8f-130">HTTP request</span></span>
```
GET https://api.securitycenter.microsoft.com/api/indicators
```

## <a name="request-headers"></a><span data-ttu-id="21d8f-131">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="21d8f-131">Request headers</span></span>

<span data-ttu-id="21d8f-132">Naam</span><span class="sxs-lookup"><span data-stu-id="21d8f-132">Name</span></span> | <span data-ttu-id="21d8f-133">Type</span><span class="sxs-lookup"><span data-stu-id="21d8f-133">Type</span></span> | <span data-ttu-id="21d8f-134">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="21d8f-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="21d8f-135">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="21d8f-135">Authorization</span></span> | <span data-ttu-id="21d8f-136">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="21d8f-136">String</span></span> | <span data-ttu-id="21d8f-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="21d8f-137">Bearer {token}.</span></span> <span data-ttu-id="21d8f-138">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="21d8f-138">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="21d8f-139">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="21d8f-139">Request body</span></span>
<span data-ttu-id="21d8f-140">Leeg</span><span class="sxs-lookup"><span data-stu-id="21d8f-140">Empty</span></span>

## <a name="response"></a><span data-ttu-id="21d8f-141">Antwoord</span><span class="sxs-lookup"><span data-stu-id="21d8f-141">Response</span></span>
<span data-ttu-id="21d8f-142">Als dit is gelukt, retourneert deze methode 200, Ok-antwoordcode met een verzameling indicatorentiteiten. [](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="21d8f-142">If successful, this method returns 200, Ok response code with a collection of [Indicator](ti-indicator.md) entities.</span></span>

>[!Note]
> <span data-ttu-id="21d8f-143">Als de toepassing de machtiging 'Ti.ReadWrite.All' heeft, wordt deze aan alle indicatoren getoond.</span><span class="sxs-lookup"><span data-stu-id="21d8f-143">If the Application has 'Ti.ReadWrite.All' permission, it will be exposed to all Indicators.</span></span> <span data-ttu-id="21d8f-144">Anders wordt deze alleen blootgesteld aan de indicatoren die het heeft gemaakt.</span><span class="sxs-lookup"><span data-stu-id="21d8f-144">Otherwise, it will be exposed only to the Indicators it created.</span></span>

## <a name="example-1"></a><span data-ttu-id="21d8f-145">Voorbeeld 1: </span><span class="sxs-lookup"><span data-stu-id="21d8f-145">Example 1:</span></span>

<span data-ttu-id="21d8f-146">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="21d8f-146">**Request**</span></span>

<span data-ttu-id="21d8f-147">Hier is een voorbeeld van een aanvraag die alle indicatoren krijgt</span><span class="sxs-lookup"><span data-stu-id="21d8f-147">Here is an example of a request that gets all Indicators</span></span>

```
GET https://api.securitycenter.microsoft.com/api/indicators
```

<span data-ttu-id="21d8f-148">**Antwoord**</span><span class="sxs-lookup"><span data-stu-id="21d8f-148">**Response**</span></span>

<span data-ttu-id="21d8f-149">Hier is een voorbeeld van het antwoord.</span><span class="sxs-lookup"><span data-stu-id="21d8f-149">Here is an example of the response.</span></span>

```
HTTP/1.1 200 Ok
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Indicators",
    "value": [
        {
            "id": "995",
            "indicatorValue": "12.13.14.15",
            "indicatorType": "IpAddress",
            "action": "Alert",
            "application": "demo-test",
            "source": "TestPrdApp",
            "sourceType": "AadApp",
            "title": "test",
            "creationTimeDateTimeUtc": "2018-10-24T11:15:35.3688259Z",
            "createdBy": "45097602-1234-5678-1234-9f453233e62c",
            "expirationTime": "2020-12-12T00:00:00Z",
            "lastUpdateTime": "2019-10-24T10:54:23.2009016Z",
            "lastUpdatedBy": TestPrdApp,
            "severity": "Informational",
            "description": "test",
            "recommendedActions": "test",
            "rbacGroupNames": []
        },
        {
            "id": "996",
            "indicatorValue": "220e7d15b0b3d7fac48f2bd61114db1022197f7f",
            "indicatorType": "FileSha1",
            "action": "AlertAndBlock",
            "application": null,
            "source": "TestPrdApp",
            "sourceType": "AadApp",
            "title": "test",
            "creationTimeDateTimeUtc": "2018-10-24T10:54:23.2009016Z",
            "createdBy": "45097602-1234-5678-1234-9f453233e62c",
            "expirationTime": "2020-12-12T00:00:00Z",
            "lastUpdateTime": "2019-10-24T10:54:23.2009016Z",
            "lastUpdatedBy": TestPrdApp,
            "severity": "Informational",
            "description": "test",
            "recommendedActions": "TEST",
            "rbacGroupNames": [ "Group1", "Group2" ]
        }
        ...
    ]
}
```

## <a name="example-2"></a><span data-ttu-id="21d8f-150">Voorbeeld 2: </span><span class="sxs-lookup"><span data-stu-id="21d8f-150">Example 2:</span></span>

<span data-ttu-id="21d8f-151">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="21d8f-151">**Request**</span></span>

<span data-ttu-id="21d8f-152">Hier is een voorbeeld van een aanvraag die alle indicatoren krijgt met de actie 'AlertAndBlock'.</span><span class="sxs-lookup"><span data-stu-id="21d8f-152">Here is an example of a request that gets all Indicators with 'AlertAndBlock' action</span></span> 

```
GET https://api.securitycenter.microsoft.com/api/indicators?$filter=action+eq+'AlertAndBlock'
```

<span data-ttu-id="21d8f-153">**Antwoord**</span><span class="sxs-lookup"><span data-stu-id="21d8f-153">**Response**</span></span>

<span data-ttu-id="21d8f-154">Hier is een voorbeeld van het antwoord.</span><span class="sxs-lookup"><span data-stu-id="21d8f-154">Here is an example of the response.</span></span>

```
HTTP/1.1 200 Ok
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Indicators",
    "value": [
        {
            "id": "997",
            "indicatorValue": "111e7d15b0b3d7fac48f2bd61114db1022197f7f",
            "indicatorType": "FileSha1",
            "action": "AlertAndBlock",
            "application": null,
            "source": "TestPrdApp",
            "sourceType": "AadApp",
            "title": "test",
            "creationTimeDateTimeUtc": "2018-10-24T10:54:23.2009016Z",
            "createdBy": "45097602-1234-5678-1234-9f453233e62c",
            "expirationTime": "2020-12-12T00:00:00Z",
            "lastUpdateTime": "2019-10-24T10:54:23.2009016Z",
            "lastUpdatedBy": TestPrdApp,
            "severity": "Informational",
            "description": "test",
            "recommendedActions": "TEST",
            "rbacGroupNames": [ "Group1", "Group2" ]
        }
        ...
    ]
}
```
