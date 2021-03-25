---
title: List machines API
description: Meer informatie over het gebruik van de LIST-machines-API om een verzameling machines op te halen die zijn gecommuniceerd met microsoft Defender ATP-cloud.
keywords: api's, graph api, ondersteunde api's, get, apparaten
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
ms.openlocfilehash: 23997cf4997ccfea8ee89a9b9ec5cc991dfa1ed0
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200375"
---
# <a name="list-machines-api"></a><span data-ttu-id="f3c6b-104">List machines API</span><span class="sxs-lookup"><span data-stu-id="f3c6b-104">List machines API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f3c6b-105">**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="f3c6b-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="f3c6b-106">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="f3c6b-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f3c6b-107">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="f3c6b-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="f3c6b-108">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="f3c6b-108">API description</span></span>
<span data-ttu-id="f3c6b-109">Hiermee wordt een verzameling [machines opgehaald die](machine.md) zijn gecommuniceerd met Microsoft Defender voor endpoint-cloud.</span><span class="sxs-lookup"><span data-stu-id="f3c6b-109">Retrieves a collection of [Machines](machine.md) that have communicated with  Microsoft Defender for Endpoint cloud.</span></span>
<br><span data-ttu-id="f3c6b-110">Ondersteunt [OData V4-query's.](https://www.odata.org/documentation/)</span><span class="sxs-lookup"><span data-stu-id="f3c6b-110">Supports [OData V4 queries](https://www.odata.org/documentation/).</span></span>
<br><span data-ttu-id="f3c6b-111">De query van OData `$filter` wordt ondersteund op: `computerDnsName` , , , en `lastSeen` `healthStatus` `osPlatform` `riskScore` `rbacGroupId` .</span><span class="sxs-lookup"><span data-stu-id="f3c6b-111">The OData's `$filter` query is supported on: `computerDnsName`, `lastSeen`, `healthStatus`, `osPlatform`, `riskScore` and `rbacGroupId`.</span></span>
<br><span data-ttu-id="f3c6b-112">Zie voorbeelden bij [OData-query's met Defender voor Eindpunt](exposed-apis-odata-samples.md)</span><span class="sxs-lookup"><span data-stu-id="f3c6b-112">See examples at [OData queries with Defender for Endpoint](exposed-apis-odata-samples.md)</span></span>


## <a name="limitations"></a><span data-ttu-id="f3c6b-113">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="f3c6b-113">Limitations</span></span>
1. <span data-ttu-id="f3c6b-114">U kunt apparaten voor het laatst zien op basis van de geconfigureerde bewaarperiode.</span><span class="sxs-lookup"><span data-stu-id="f3c6b-114">You can get devices last seen according to your configured retention period.</span></span>
2. <span data-ttu-id="f3c6b-115">De maximale paginagrootte is 10.000.</span><span class="sxs-lookup"><span data-stu-id="f3c6b-115">Maximum page size is 10,000.</span></span>
3. <span data-ttu-id="f3c6b-116">Tariefbeperkingen voor deze API zijn 100 oproepen per minuut en 1500 oproepen per uur.</span><span class="sxs-lookup"><span data-stu-id="f3c6b-116">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span> 


## <a name="permissions"></a><span data-ttu-id="f3c6b-117">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="f3c6b-117">Permissions</span></span>

<span data-ttu-id="f3c6b-118">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="f3c6b-118">Permission type</span></span> |   <span data-ttu-id="f3c6b-119">Machtiging</span><span class="sxs-lookup"><span data-stu-id="f3c6b-119">Permission</span></span>  |   <span data-ttu-id="f3c6b-120">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="f3c6b-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="f3c6b-121">Toepassing</span><span class="sxs-lookup"><span data-stu-id="f3c6b-121">Application</span></span> |   <span data-ttu-id="f3c6b-122">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="f3c6b-122">Machine.Read.All</span></span> |  <span data-ttu-id="f3c6b-123">'Alle machineprofielen lezen'</span><span class="sxs-lookup"><span data-stu-id="f3c6b-123">'Read all machine profiles'</span></span>
<span data-ttu-id="f3c6b-124">Toepassing</span><span class="sxs-lookup"><span data-stu-id="f3c6b-124">Application</span></span> |   <span data-ttu-id="f3c6b-125">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="f3c6b-125">Machine.ReadWrite.All</span></span> | <span data-ttu-id="f3c6b-126">'Alle computergegevens lezen en schrijven'</span><span class="sxs-lookup"><span data-stu-id="f3c6b-126">'Read and write all machine information'</span></span>
<span data-ttu-id="f3c6b-127">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="f3c6b-127">Delegated (work or school account)</span></span> | <span data-ttu-id="f3c6b-128">Machine.Lezen</span><span class="sxs-lookup"><span data-stu-id="f3c6b-128">Machine.Read</span></span> | <span data-ttu-id="f3c6b-129">'Machinegegevens lezen'</span><span class="sxs-lookup"><span data-stu-id="f3c6b-129">'Read machine information'</span></span>
<span data-ttu-id="f3c6b-130">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="f3c6b-130">Delegated (work or school account)</span></span> | <span data-ttu-id="f3c6b-131">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="f3c6b-131">Machine.ReadWrite</span></span> | <span data-ttu-id="f3c6b-132">'Machinegegevens lezen en schrijven'</span><span class="sxs-lookup"><span data-stu-id="f3c6b-132">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="f3c6b-133">Bij het verkrijgen van een token met gebruikersreferenties:</span><span class="sxs-lookup"><span data-stu-id="f3c6b-133">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="f3c6b-134">De gebruiker moet ten minste de volgende rolmachtiging hebben: 'Gegevens weergeven' [(Zie](user-roles.md) Rollen maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="f3c6b-134">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="f3c6b-135">Antwoord bevat alleen apparaten, waar de gebruiker toegang toe heeft, op basis van apparaatgroepsinstellingen (Zie [Apparaatgroepen](machine-groups.md) maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="f3c6b-135">Response will include only devices, that the user have access to, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="f3c6b-136">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="f3c6b-136">HTTP request</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines
```

## <a name="request-headers"></a><span data-ttu-id="f3c6b-137">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="f3c6b-137">Request headers</span></span>

<span data-ttu-id="f3c6b-138">Naam</span><span class="sxs-lookup"><span data-stu-id="f3c6b-138">Name</span></span> | <span data-ttu-id="f3c6b-139">Type</span><span class="sxs-lookup"><span data-stu-id="f3c6b-139">Type</span></span> | <span data-ttu-id="f3c6b-140">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="f3c6b-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="f3c6b-141">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="f3c6b-141">Authorization</span></span> | <span data-ttu-id="f3c6b-142">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f3c6b-142">String</span></span> | <span data-ttu-id="f3c6b-143">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="f3c6b-143">Bearer {token}.</span></span> <span data-ttu-id="f3c6b-144">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="f3c6b-144">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="f3c6b-145">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="f3c6b-145">Request body</span></span>
<span data-ttu-id="f3c6b-146">Leeg</span><span class="sxs-lookup"><span data-stu-id="f3c6b-146">Empty</span></span>

## <a name="response"></a><span data-ttu-id="f3c6b-147">Antwoord</span><span class="sxs-lookup"><span data-stu-id="f3c6b-147">Response</span></span>
<span data-ttu-id="f3c6b-148">Als dit is gelukt en er machines bestaan- 200 OK met een lijst met [machine-entiteiten](machine.md) in de body.</span><span class="sxs-lookup"><span data-stu-id="f3c6b-148">If successful and machines exists - 200 OK with list of [machine](machine.md) entities in the body.</span></span> <span data-ttu-id="f3c6b-149">Als er geen recente machines - 404 Niet gevonden.</span><span class="sxs-lookup"><span data-stu-id="f3c6b-149">If no recent machines - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="f3c6b-150">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="f3c6b-150">Example</span></span>

<span data-ttu-id="f3c6b-151">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="f3c6b-151">**Request**</span></span>

<span data-ttu-id="f3c6b-152">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="f3c6b-152">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines
```

<span data-ttu-id="f3c6b-153">**Antwoord**</span><span class="sxs-lookup"><span data-stu-id="f3c6b-153">**Response**</span></span>

<span data-ttu-id="f3c6b-154">Hier is een voorbeeld van het antwoord.</span><span class="sxs-lookup"><span data-stu-id="f3c6b-154">Here is an example of the response.</span></span>

```http
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Machines",
    "value": [
        {
            "id": "1e5bc9d7e413ddd7902c2932e418702b84d0cc07",
            "computerDnsName": "mymachine1.contoso.com",
            "firstSeen": "2018-08-02T14:55:03.7791856Z",
            "lastSeen": "2018-08-02T14:55:03.7791856Z",
            "osPlatform": "Windows10",
            "version": "1709",
            "osProcessor": "x64",
            "lastIpAddress": "172.17.230.209",
            "lastExternalIpAddress": "167.220.196.71",
            "osBuild": 18209,
            "healthStatus": "Active",
            "rbacGroupId": 140,
            "rbacGroupName": "The-A-Team",
            "riskScore": "Low",
            "exposureLevel": "Medium",
            "isAadJoined": true,
            "aadDeviceId": "80fe8ff8-2624-418e-9591-41f0491218f9",
            "machineTags": [ "test tag 1", "test tag 2" ]
        }
        ...
    ]
}
```

## <a name="related-topics"></a><span data-ttu-id="f3c6b-155">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="f3c6b-155">Related topics</span></span>
- [<span data-ttu-id="f3c6b-156">OData-query's met Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="f3c6b-156">OData queries with Microsoft Defender for Endpoint</span></span>](exposed-apis-odata-samples.md)
