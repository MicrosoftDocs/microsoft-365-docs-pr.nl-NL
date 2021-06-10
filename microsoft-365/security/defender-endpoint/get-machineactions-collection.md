---
title: List machineActions API
description: Meer informatie over het gebruik van de LIST MachineActions API om een verzameling machineacties op te halen in Microsoft Defender voor Eindpunt.
keywords: api's, graph api, ondersteunde api's, machineaction collection
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
ms.openlocfilehash: 2ee9a4e29dded3e299ffbb2c2997fd02f32d1abf
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771115"
---
# <a name="list-machineactions-api"></a><span data-ttu-id="895e1-104">List MachineActions API</span><span class="sxs-lookup"><span data-stu-id="895e1-104">List MachineActions API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="895e1-105">**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="895e1-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="895e1-106">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="895e1-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="895e1-107">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="895e1-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="895e1-108">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="895e1-108">API description</span></span>
<span data-ttu-id="895e1-109">Hiermee wordt een verzameling [machineacties opgehaald.](machineaction.md)</span><span class="sxs-lookup"><span data-stu-id="895e1-109">Retrieves a collection of [Machine Actions](machineaction.md).</span></span>
<br><span data-ttu-id="895e1-110">Ondersteunt [OData V4-query's.](https://www.odata.org/documentation/)</span><span class="sxs-lookup"><span data-stu-id="895e1-110">Supports [OData V4 queries](https://www.odata.org/documentation/).</span></span>
<br><span data-ttu-id="895e1-111">De query van OData ```$filter``` wordt ondersteund op: ```status``` , , en ```machineId``` ```type``` ```requestor``` ```creationDateTimeUtc``` eigenschappen.</span><span class="sxs-lookup"><span data-stu-id="895e1-111">The OData's ```$filter``` query is supported on: ```status```, ```machineId```, ```type```, ```requestor``` and ```creationDateTimeUtc``` properties.</span></span>
<br><span data-ttu-id="895e1-112">Zie voorbeelden bij [OData-query's met Microsoft Defender voor Eindpunt](exposed-apis-odata-samples.md)</span><span class="sxs-lookup"><span data-stu-id="895e1-112">See examples at [OData queries with Microsoft Defender for Endpoint](exposed-apis-odata-samples.md)</span></span>


## <a name="limitations"></a><span data-ttu-id="895e1-113">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="895e1-113">Limitations</span></span>
1. <span data-ttu-id="895e1-114">De maximale paginagrootte is 10.000.</span><span class="sxs-lookup"><span data-stu-id="895e1-114">Maximum page size is 10,000.</span></span>
2. <span data-ttu-id="895e1-115">Tariefbeperkingen voor deze API zijn 100 oproepen per minuut en 1500 oproepen per uur.</span><span class="sxs-lookup"><span data-stu-id="895e1-115">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span> 


## <a name="permissions"></a><span data-ttu-id="895e1-116">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="895e1-116">Permissions</span></span>
<span data-ttu-id="895e1-117">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="895e1-117">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="895e1-118">Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="895e1-118">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="895e1-119">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="895e1-119">Permission type</span></span> |   <span data-ttu-id="895e1-120">Machtiging</span><span class="sxs-lookup"><span data-stu-id="895e1-120">Permission</span></span>  |   <span data-ttu-id="895e1-121">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="895e1-121">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="895e1-122">Toepassing</span><span class="sxs-lookup"><span data-stu-id="895e1-122">Application</span></span> |   <span data-ttu-id="895e1-123">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="895e1-123">Machine.Read.All</span></span> |  <span data-ttu-id="895e1-124">'Alle machineprofielen lezen'</span><span class="sxs-lookup"><span data-stu-id="895e1-124">'Read all machine profiles'</span></span>
<span data-ttu-id="895e1-125">Toepassing</span><span class="sxs-lookup"><span data-stu-id="895e1-125">Application</span></span> |   <span data-ttu-id="895e1-126">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="895e1-126">Machine.ReadWrite.All</span></span> | <span data-ttu-id="895e1-127">'Alle computergegevens lezen en schrijven'</span><span class="sxs-lookup"><span data-stu-id="895e1-127">'Read and write all machine information'</span></span>
<span data-ttu-id="895e1-128">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="895e1-128">Delegated (work or school account)</span></span> | <span data-ttu-id="895e1-129">Machine.Lezen</span><span class="sxs-lookup"><span data-stu-id="895e1-129">Machine.Read</span></span> | <span data-ttu-id="895e1-130">'Machinegegevens lezen'</span><span class="sxs-lookup"><span data-stu-id="895e1-130">'Read machine information'</span></span>
<span data-ttu-id="895e1-131">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="895e1-131">Delegated (work or school account)</span></span> | <span data-ttu-id="895e1-132">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="895e1-132">Machine.ReadWrite</span></span> | <span data-ttu-id="895e1-133">'Machinegegevens lezen en schrijven'</span><span class="sxs-lookup"><span data-stu-id="895e1-133">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="895e1-134">Bij het verkrijgen van een token met gebruikersreferenties:</span><span class="sxs-lookup"><span data-stu-id="895e1-134">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="895e1-135">De gebruiker moet ten minste de volgende rolmachtiging hebben: 'Gegevens weergeven' [(Zie](user-roles.md) Rollen maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="895e1-135">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="895e1-136">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="895e1-136">HTTP request</span></span>
```
GET https://api.securitycenter.microsoft.com/api/machineactions
```

## <a name="request-headers"></a><span data-ttu-id="895e1-137">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="895e1-137">Request headers</span></span>

<span data-ttu-id="895e1-138">Naam</span><span class="sxs-lookup"><span data-stu-id="895e1-138">Name</span></span> | <span data-ttu-id="895e1-139">Type</span><span class="sxs-lookup"><span data-stu-id="895e1-139">Type</span></span> | <span data-ttu-id="895e1-140">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="895e1-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="895e1-141">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="895e1-141">Authorization</span></span> | <span data-ttu-id="895e1-142">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="895e1-142">String</span></span> | <span data-ttu-id="895e1-143">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="895e1-143">Bearer {token}.</span></span> <span data-ttu-id="895e1-144">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="895e1-144">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="895e1-145">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="895e1-145">Request body</span></span>
<span data-ttu-id="895e1-146">Leeg</span><span class="sxs-lookup"><span data-stu-id="895e1-146">Empty</span></span>

## <a name="response"></a><span data-ttu-id="895e1-147">Antwoord</span><span class="sxs-lookup"><span data-stu-id="895e1-147">Response</span></span>
<span data-ttu-id="895e1-148">Als dit is gelukt, retourneert deze methode 200, Ok-antwoordcode met een verzameling [machineAction-entiteiten.](machineaction.md)</span><span class="sxs-lookup"><span data-stu-id="895e1-148">If successful, this method returns 200, Ok response code with a collection of [machineAction](machineaction.md) entities.</span></span>


## <a name="example-1"></a><span data-ttu-id="895e1-149">Voorbeeld 1</span><span class="sxs-lookup"><span data-stu-id="895e1-149">Example 1</span></span>

<span data-ttu-id="895e1-150">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="895e1-150">**Request**</span></span>

<span data-ttu-id="895e1-151">Hier is een voorbeeld van de aanvraag voor een organisatie met drie MachineActions.</span><span class="sxs-lookup"><span data-stu-id="895e1-151">Here is an example of the request on an organization that has three MachineActions.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/machineactions
```

<span data-ttu-id="895e1-152">**Antwoord**</span><span class="sxs-lookup"><span data-stu-id="895e1-152">**Response**</span></span>

<span data-ttu-id="895e1-153">Hier is een voorbeeld van het antwoord.</span><span class="sxs-lookup"><span data-stu-id="895e1-153">Here is an example of the response.</span></span>


```
HTTP/1.1 200 Ok
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineActions",
    "value": [
        {
            "id": "69dc3630-1ccc-4342-acf3-35286eec741d",
            "type": "CollectInvestigationPackage",
            "scope": null,
            "requestor": "Analyst@contoso.com",
            "requestorComment": "test",
            "status": "Succeeded",
            "machineId": "f46b9bb259ed4a7fb9981b73510e3cc7aa81ec1f",
            "computerDnsName": "desktop-39g9tgl",
            "creationDateTimeUtc": "2018-12-04T12:43:57.2011911Z",
            "lastUpdateTimeUtc": "2018-12-04T12:45:25.4049122Z",
            "relatedFileInfo": null
        },
        {
            "id": "2e9da30d-27f6-4208-81f2-9cd3d67893ba",
            "type": "RunAntiVirusScan",
            "scope": "Full",
            "requestor": "Analyst@contoso.com",
            "requestorComment": "Check machine for viruses due to alert 3212",
            "status": "Succeeded",
            "machineId": "f46b9bb259ed4a7fb9981b73510e3cc7aa81ec1f",
            "computerDnsName": "desktop-39g9tgl",
            "creationDateTimeUtc": "2018-12-04T12:18:27.1293487Z",
            "lastUpdateTimeUtc": "2018-12-04T12:18:57.5511934Z",
            "relatedFileInfo": null
        },
        {
            "id": "44cffc15-0e3d-4cbf-96aa-bf76f9b27f5e",
            "type": "StopAndQuarantineFile",
            "scope": null,
            "requestor": "Analyst@contoso.com",
            "requestorComment": "test",
            "status": "Succeeded",
            "machineId": "f46b9bb259ed4a7fb9981b73510e3cc7aa81ec1f",
            "computerDnsName": "desktop-39g9tgl",
            "creationDateTimeUtc": "2018-12-04T12:15:40.6052029Z",
            "lastUpdateTimeUtc": "2018-12-04T12:16:14.2899973Z",
            "relatedFileInfo": {
                "fileIdentifier": "a0c659857ccbe457fdaf5fe21d54efdcbf6f6508",
                "fileIdentifierType": "Sha1"
            }
        }
    ]
}
```

## <a name="example-2"></a><span data-ttu-id="895e1-154">Voorbeeld 2</span><span class="sxs-lookup"><span data-stu-id="895e1-154">Example 2</span></span>

<span data-ttu-id="895e1-155">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="895e1-155">**Request**</span></span>

<span data-ttu-id="895e1-156">Hier ziet u een voorbeeld van een aanvraag die de MachineActions filtert op machine-id en de meest recente twee MachineActions wekt.</span><span class="sxs-lookup"><span data-stu-id="895e1-156">Here is an example of a request that filters the MachineActions by machine ID and shows the latest two MachineActions.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/machineactions?$filter=machineId eq 'f46b9bb259ed4a7fb9981b73510e3cc7aa81ec1f'&$top=2
```

<span data-ttu-id="895e1-157">**Antwoord**</span><span class="sxs-lookup"><span data-stu-id="895e1-157">**Response**</span></span>

<span data-ttu-id="895e1-158">Hier is een voorbeeld van het antwoord.</span><span class="sxs-lookup"><span data-stu-id="895e1-158">Here is an example of the response.</span></span>

```
HTTP/1.1 200 Ok
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineActions",
    "value": [
        {
            "id": "69dc3630-1ccc-4342-acf3-35286eec741d",
            "type": "CollectInvestigationPackage",
            "scope": null,
            "requestor": "Analyst@contoso.com",
            "requestorComment": "test",
            "status": "Succeeded",
            "machineId": "f46b9bb259ed4a7fb9981b73510e3cc7aa81ec1f",
            "computerDnsName": "desktop-39g9tgl",
            "creationDateTimeUtc": "2018-12-04T12:43:57.2011911Z",
            "lastUpdateTimeUtc": "2018-12-04T12:45:25.4049122Z",
            "relatedFileInfo": null
        },
        {
            "id": "2e9da30d-27f6-4208-81f2-9cd3d67893ba",
            "type": "RunAntiVirusScan",
            "scope": "Full",
            "requestor": "Analyst@contoso.com",
            "requestorComment": "Check machine for viruses due to alert 3212",
            "status": "Succeeded",
            "machineId": "f46b9bb259ed4a7fb9981b73510e3cc7aa81ec1f",
            "computerDnsName": "desktop-39g9tgl",
            "creationDateTimeUtc": "2018-12-04T12:18:27.1293487Z",
            "lastUpdateTimeUtc": "2018-12-04T12:18:57.5511934Z",
            "relatedFileInfo": null
        }
    ]
}
```

## <a name="related-topics"></a><span data-ttu-id="895e1-159">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="895e1-159">Related topics</span></span>
- [<span data-ttu-id="895e1-160">OData-query's met Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="895e1-160">OData queries with Microsoft Defender for Endpoint</span></span>](exposed-apis-odata-samples.md)
