---
title: List machines API
description: Meer informatie over het gebruik van de LIST-machines-API om een verzameling machines op te halen die zijn gecommuniceerd met Microsoft Defender voor endpoint-cloud.
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: f06973bc45ecac05c15d48afe5f0e2e9e7788f78
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770743"
---
# <a name="list-machines-api"></a><span data-ttu-id="08e57-104">List machines API</span><span class="sxs-lookup"><span data-stu-id="08e57-104">List machines API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="08e57-105">**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="08e57-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="08e57-106">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="08e57-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="08e57-107">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="08e57-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="08e57-108">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="08e57-108">API description</span></span>
<span data-ttu-id="08e57-109">Hiermee wordt een verzameling [machines opgehaald die](machine.md) zijn gecommuniceerd met Microsoft Defender voor endpoint-cloud.</span><span class="sxs-lookup"><span data-stu-id="08e57-109">Retrieves a collection of [Machines](machine.md) that have communicated with  Microsoft Defender for Endpoint cloud.</span></span>
<br><span data-ttu-id="08e57-110">Ondersteunt [OData V4-query's.](https://www.odata.org/documentation/)</span><span class="sxs-lookup"><span data-stu-id="08e57-110">Supports [OData V4 queries](https://www.odata.org/documentation/).</span></span>
<br><span data-ttu-id="08e57-111">De query van OData `$filter` wordt ondersteund op: `computerDnsName` , , , en `lastSeen` `healthStatus` `osPlatform` `riskScore` `rbacGroupId` .</span><span class="sxs-lookup"><span data-stu-id="08e57-111">The OData's `$filter` query is supported on: `computerDnsName`, `lastSeen`, `healthStatus`, `osPlatform`, `riskScore` and `rbacGroupId`.</span></span>
<br><span data-ttu-id="08e57-112">Zie voorbeelden bij [OData-query's met Defender voor Eindpunt](exposed-apis-odata-samples.md)</span><span class="sxs-lookup"><span data-stu-id="08e57-112">See examples at [OData queries with Defender for Endpoint](exposed-apis-odata-samples.md)</span></span>


## <a name="limitations"></a><span data-ttu-id="08e57-113">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="08e57-113">Limitations</span></span>
1. <span data-ttu-id="08e57-114">U kunt apparaten voor het laatst zien op basis van de geconfigureerde bewaarperiode.</span><span class="sxs-lookup"><span data-stu-id="08e57-114">You can get devices last seen according to your configured retention period.</span></span>
2. <span data-ttu-id="08e57-115">De maximale paginagrootte is 10.000.</span><span class="sxs-lookup"><span data-stu-id="08e57-115">Maximum page size is 10,000.</span></span>
3. <span data-ttu-id="08e57-116">Tariefbeperkingen voor deze API zijn 100 oproepen per minuut en 1500 oproepen per uur.</span><span class="sxs-lookup"><span data-stu-id="08e57-116">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span> 


## <a name="permissions"></a><span data-ttu-id="08e57-117">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="08e57-117">Permissions</span></span>

<span data-ttu-id="08e57-118">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="08e57-118">Permission type</span></span> |   <span data-ttu-id="08e57-119">Machtiging</span><span class="sxs-lookup"><span data-stu-id="08e57-119">Permission</span></span>  |   <span data-ttu-id="08e57-120">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="08e57-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="08e57-121">Toepassing</span><span class="sxs-lookup"><span data-stu-id="08e57-121">Application</span></span> |   <span data-ttu-id="08e57-122">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="08e57-122">Machine.Read.All</span></span> |  <span data-ttu-id="08e57-123">'Alle machineprofielen lezen'</span><span class="sxs-lookup"><span data-stu-id="08e57-123">'Read all machine profiles'</span></span>
<span data-ttu-id="08e57-124">Toepassing</span><span class="sxs-lookup"><span data-stu-id="08e57-124">Application</span></span> |   <span data-ttu-id="08e57-125">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="08e57-125">Machine.ReadWrite.All</span></span> | <span data-ttu-id="08e57-126">'Alle computergegevens lezen en schrijven'</span><span class="sxs-lookup"><span data-stu-id="08e57-126">'Read and write all machine information'</span></span>
<span data-ttu-id="08e57-127">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="08e57-127">Delegated (work or school account)</span></span> | <span data-ttu-id="08e57-128">Machine.Lezen</span><span class="sxs-lookup"><span data-stu-id="08e57-128">Machine.Read</span></span> | <span data-ttu-id="08e57-129">'Machinegegevens lezen'</span><span class="sxs-lookup"><span data-stu-id="08e57-129">'Read machine information'</span></span>
<span data-ttu-id="08e57-130">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="08e57-130">Delegated (work or school account)</span></span> | <span data-ttu-id="08e57-131">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="08e57-131">Machine.ReadWrite</span></span> | <span data-ttu-id="08e57-132">'Machinegegevens lezen en schrijven'</span><span class="sxs-lookup"><span data-stu-id="08e57-132">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="08e57-133">Bij het verkrijgen van een token met gebruikersreferenties:</span><span class="sxs-lookup"><span data-stu-id="08e57-133">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="08e57-134">De gebruiker moet ten minste de volgende rolmachtiging hebben: 'Gegevens weergeven' [(Zie](user-roles.md) Rollen maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="08e57-134">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="08e57-135">Antwoord bevat alleen apparaten, waar de gebruiker toegang toe heeft, op basis van apparaatgroepsinstellingen (Zie [Apparaatgroepen](machine-groups.md) maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="08e57-135">Response will include only devices, that the user have access to, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="08e57-136">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="08e57-136">HTTP request</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines
```

## <a name="request-headers"></a><span data-ttu-id="08e57-137">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="08e57-137">Request headers</span></span>

<span data-ttu-id="08e57-138">Naam</span><span class="sxs-lookup"><span data-stu-id="08e57-138">Name</span></span> | <span data-ttu-id="08e57-139">Type</span><span class="sxs-lookup"><span data-stu-id="08e57-139">Type</span></span> | <span data-ttu-id="08e57-140">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="08e57-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="08e57-141">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="08e57-141">Authorization</span></span> | <span data-ttu-id="08e57-142">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="08e57-142">String</span></span> | <span data-ttu-id="08e57-143">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="08e57-143">Bearer {token}.</span></span> <span data-ttu-id="08e57-144">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="08e57-144">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="08e57-145">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="08e57-145">Request body</span></span>
<span data-ttu-id="08e57-146">Leeg</span><span class="sxs-lookup"><span data-stu-id="08e57-146">Empty</span></span>

## <a name="response"></a><span data-ttu-id="08e57-147">Antwoord</span><span class="sxs-lookup"><span data-stu-id="08e57-147">Response</span></span>
<span data-ttu-id="08e57-148">Als dit is gelukt en er machines bestaan- 200 OK met een lijst met [machine-entiteiten](machine.md) in de body.</span><span class="sxs-lookup"><span data-stu-id="08e57-148">If successful and machines exists - 200 OK with list of [machine](machine.md) entities in the body.</span></span> <span data-ttu-id="08e57-149">Als er geen recente machines - 404 Niet gevonden.</span><span class="sxs-lookup"><span data-stu-id="08e57-149">If no recent machines - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="08e57-150">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="08e57-150">Example</span></span>

<span data-ttu-id="08e57-151">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="08e57-151">**Request**</span></span>

<span data-ttu-id="08e57-152">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="08e57-152">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines
```

<span data-ttu-id="08e57-153">**Antwoord**</span><span class="sxs-lookup"><span data-stu-id="08e57-153">**Response**</span></span>

<span data-ttu-id="08e57-154">Hier is een voorbeeld van het antwoord.</span><span class="sxs-lookup"><span data-stu-id="08e57-154">Here is an example of the response.</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="08e57-155">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="08e57-155">Related topics</span></span>
- [<span data-ttu-id="08e57-156">OData-query's met Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="08e57-156">OData queries with Microsoft Defender for Endpoint</span></span>](exposed-apis-odata-samples.md)
