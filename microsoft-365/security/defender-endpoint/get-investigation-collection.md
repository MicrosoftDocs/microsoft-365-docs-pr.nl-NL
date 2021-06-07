---
title: List Investigations API
description: Gebruik deze API om oproepen te maken die betrekking hebben op het ophalen van onderzoeken
keywords: api's, graph api, ondersteunde api's, Investigations collection
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
ms.openlocfilehash: 38485a5028626153c26cd1e11537ef7a2daf5296
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770143"
---
# <a name="list-investigations-api"></a><span data-ttu-id="2ed8f-104">List Investigations API</span><span class="sxs-lookup"><span data-stu-id="2ed8f-104">List Investigations API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2ed8f-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="2ed8f-105">**Applies to:**</span></span>
- [<span data-ttu-id="2ed8f-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="2ed8f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2ed8f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2ed8f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="2ed8f-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="2ed8f-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2ed8f-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="2ed8f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="2ed8f-110">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="2ed8f-110">API description</span></span>
<span data-ttu-id="2ed8f-111">Hiermee wordt een verzameling [onderzoeken opgehaald.](investigation.md)</span><span class="sxs-lookup"><span data-stu-id="2ed8f-111">Retrieves a collection of [Investigations](investigation.md).</span></span>
<br><span data-ttu-id="2ed8f-112">Ondersteunt [OData V4-query's.](https://www.odata.org/documentation/)</span><span class="sxs-lookup"><span data-stu-id="2ed8f-112">Supports [OData V4 queries](https://www.odata.org/documentation/).</span></span>
<br><span data-ttu-id="2ed8f-113">De query van OData ```$filter``` wordt ondersteund op: ```startTime``` en ```state``` ```machineId``` ```triggeringAlertId``` eigenschappen.</span><span class="sxs-lookup"><span data-stu-id="2ed8f-113">The OData's ```$filter``` query is supported on: ```startTime```, ```state```, ```machineId``` and ```triggeringAlertId``` properties.</span></span>
<br><span data-ttu-id="2ed8f-114">Zie voorbeelden bij [OData-query's met Microsoft Defender voor Eindpunt](exposed-apis-odata-samples.md)</span><span class="sxs-lookup"><span data-stu-id="2ed8f-114">See examples at [OData queries with Microsoft Defender for Endpoint](exposed-apis-odata-samples.md)</span></span>


## <a name="limitations"></a><span data-ttu-id="2ed8f-115">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="2ed8f-115">Limitations</span></span>
1. <span data-ttu-id="2ed8f-116">De maximale paginagrootte is 10.000.</span><span class="sxs-lookup"><span data-stu-id="2ed8f-116">Maximum page size is 10,000.</span></span>
2. <span data-ttu-id="2ed8f-117">Tariefbeperkingen voor deze API zijn 100 oproepen per minuut en 1500 oproepen per uur.</span><span class="sxs-lookup"><span data-stu-id="2ed8f-117">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span> 


## <a name="permissions"></a><span data-ttu-id="2ed8f-118">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="2ed8f-118">Permissions</span></span>
<span data-ttu-id="2ed8f-119">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="2ed8f-119">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="2ed8f-120">Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="2ed8f-120">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="2ed8f-121">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="2ed8f-121">Permission type</span></span> |   <span data-ttu-id="2ed8f-122">Machtiging</span><span class="sxs-lookup"><span data-stu-id="2ed8f-122">Permission</span></span>  |   <span data-ttu-id="2ed8f-123">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="2ed8f-123">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="2ed8f-124">Toepassing</span><span class="sxs-lookup"><span data-stu-id="2ed8f-124">Application</span></span> |   <span data-ttu-id="2ed8f-125">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="2ed8f-125">Alert.Read.All</span></span> |    <span data-ttu-id="2ed8f-126">'Alle waarschuwingen lezen'</span><span class="sxs-lookup"><span data-stu-id="2ed8f-126">'Read all alerts'</span></span>
<span data-ttu-id="2ed8f-127">Toepassing</span><span class="sxs-lookup"><span data-stu-id="2ed8f-127">Application</span></span> |   <span data-ttu-id="2ed8f-128">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="2ed8f-128">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="2ed8f-129">'Alle waarschuwingen lezen en schrijven'</span><span class="sxs-lookup"><span data-stu-id="2ed8f-129">'Read and write all alerts'</span></span>
<span data-ttu-id="2ed8f-130">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="2ed8f-130">Delegated (work or school account)</span></span> | <span data-ttu-id="2ed8f-131">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="2ed8f-131">Alert.Read</span></span> | <span data-ttu-id="2ed8f-132">'Leeswaarschuwingen'</span><span class="sxs-lookup"><span data-stu-id="2ed8f-132">'Read alerts'</span></span>
<span data-ttu-id="2ed8f-133">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="2ed8f-133">Delegated (work or school account)</span></span> | <span data-ttu-id="2ed8f-134">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="2ed8f-134">Alert.ReadWrite</span></span> | <span data-ttu-id="2ed8f-135">'Waarschuwingen lezen en schrijven'</span><span class="sxs-lookup"><span data-stu-id="2ed8f-135">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="2ed8f-136">Bij het verkrijgen van een token met gebruikersreferenties:</span><span class="sxs-lookup"><span data-stu-id="2ed8f-136">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="2ed8f-137">De gebruiker moet ten minste de volgende rolmachtiging hebben: 'Gegevens weergeven' [(Zie](user-roles.md) Rollen maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="2ed8f-137">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="2ed8f-138">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="2ed8f-138">HTTP request</span></span>
```
GET https://api.securitycenter.microsoft.com/api/investigations
```

## <a name="request-headers"></a><span data-ttu-id="2ed8f-139">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="2ed8f-139">Request headers</span></span>

<span data-ttu-id="2ed8f-140">Naam</span><span class="sxs-lookup"><span data-stu-id="2ed8f-140">Name</span></span> | <span data-ttu-id="2ed8f-141">Type</span><span class="sxs-lookup"><span data-stu-id="2ed8f-141">Type</span></span> | <span data-ttu-id="2ed8f-142">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="2ed8f-142">Description</span></span>
:---|:---|:---
<span data-ttu-id="2ed8f-143">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="2ed8f-143">Authorization</span></span> | <span data-ttu-id="2ed8f-144">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2ed8f-144">String</span></span> | <span data-ttu-id="2ed8f-145">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="2ed8f-145">Bearer {token}.</span></span> <span data-ttu-id="2ed8f-146">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="2ed8f-146">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="2ed8f-147">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="2ed8f-147">Request body</span></span>
<span data-ttu-id="2ed8f-148">Leeg</span><span class="sxs-lookup"><span data-stu-id="2ed8f-148">Empty</span></span>

## <a name="response"></a><span data-ttu-id="2ed8f-149">Antwoord</span><span class="sxs-lookup"><span data-stu-id="2ed8f-149">Response</span></span>
<span data-ttu-id="2ed8f-150">Als dit is gelukt, retourneert deze methode 200, Ok-antwoordcode met een verzameling onderzoeksentiteiten. [](investigation.md)</span><span class="sxs-lookup"><span data-stu-id="2ed8f-150">If successful, this method returns 200, Ok response code with a collection of [Investigations](investigation.md) entities.</span></span>


## <a name="example"></a><span data-ttu-id="2ed8f-151">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="2ed8f-151">Example</span></span>

<span data-ttu-id="2ed8f-152">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="2ed8f-152">**Request**</span></span>

<span data-ttu-id="2ed8f-153">Hier is een voorbeeld van een verzoek om alle onderzoeken op te vragen:</span><span class="sxs-lookup"><span data-stu-id="2ed8f-153">Here is an example of a request to get all investigations:</span></span> 

```
GET https://api.securitycenter.microsoft.com/api/investigations
```

<span data-ttu-id="2ed8f-154">**Antwoord**</span><span class="sxs-lookup"><span data-stu-id="2ed8f-154">**Response**</span></span>

<span data-ttu-id="2ed8f-155">Hier is een voorbeeld van het antwoord:</span><span class="sxs-lookup"><span data-stu-id="2ed8f-155">Here is an example of the response:</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Investigations",
    "value": [
        {
            "id": "63017",
            "startTime": "2020-01-06T14:11:34Z",
            "endTime": null,
            "state": "Running",
            "cancelledBy": null,
            "statusDetails": null,
            "machineId": "a69a22debe5f274d8765ea3c368d00762e057b30",
            "computerDnsName": "desktop-gtrcon0",
            "triggeringAlertId": "da637139166940871892_-598649278"
        }
        ...
    ]
}
```
