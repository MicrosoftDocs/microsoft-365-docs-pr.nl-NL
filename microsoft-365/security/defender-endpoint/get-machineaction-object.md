---
title: MachineAction-object-API krijgen
description: Meer informatie over het gebruik van de Get MachineAction API om een specifieke machineactie op te halen met de id in Microsoft Defender voor Eindpunt.
keywords: api's, graph api, ondersteunde api's, machineaction object
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
ms.openlocfilehash: dcb00d0d2afc7f873ea9c4afa3174ac46babf879
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770779"
---
# <a name="get-machineaction-api"></a><span data-ttu-id="404a1-104">MachineAction-API krijgen</span><span class="sxs-lookup"><span data-stu-id="404a1-104">Get machineAction API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="404a1-105">**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="404a1-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="404a1-106">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="404a1-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="404a1-107">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="404a1-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="404a1-108">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="404a1-108">API description</span></span>
<span data-ttu-id="404a1-109">Hiermee wordt specifieke [machineactie opgehaald](machineaction.md) met de id.</span><span class="sxs-lookup"><span data-stu-id="404a1-109">Retrieves specific [Machine Action](machineaction.md) by its ID.</span></span>


## <a name="limitations"></a><span data-ttu-id="404a1-110">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="404a1-110">Limitations</span></span>
1. <span data-ttu-id="404a1-111">Tariefbeperkingen voor deze API zijn 100 oproepen per minuut en 1500 oproepen per uur.</span><span class="sxs-lookup"><span data-stu-id="404a1-111">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="404a1-112">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="404a1-112">Permissions</span></span>
<span data-ttu-id="404a1-113">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="404a1-113">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="404a1-114">Zie Defender voor [eindpunt-API's gebruiken](apis-intro.md) voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="404a1-114">To learn more, including how to choose permissions, see [Use Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="404a1-115">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="404a1-115">Permission type</span></span> |   <span data-ttu-id="404a1-116">Machtiging</span><span class="sxs-lookup"><span data-stu-id="404a1-116">Permission</span></span>  |   <span data-ttu-id="404a1-117">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="404a1-117">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="404a1-118">Toepassing</span><span class="sxs-lookup"><span data-stu-id="404a1-118">Application</span></span> |   <span data-ttu-id="404a1-119">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="404a1-119">Machine.Read.All</span></span> |  <span data-ttu-id="404a1-120">'Alle machineprofielen lezen'</span><span class="sxs-lookup"><span data-stu-id="404a1-120">'Read all machine profiles'</span></span>
<span data-ttu-id="404a1-121">Toepassing</span><span class="sxs-lookup"><span data-stu-id="404a1-121">Application</span></span> |   <span data-ttu-id="404a1-122">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="404a1-122">Machine.ReadWrite.All</span></span> | <span data-ttu-id="404a1-123">'Alle computergegevens lezen en schrijven'</span><span class="sxs-lookup"><span data-stu-id="404a1-123">'Read and write all machine information'</span></span>
<span data-ttu-id="404a1-124">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="404a1-124">Delegated (work or school account)</span></span> | <span data-ttu-id="404a1-125">Machine.Lezen</span><span class="sxs-lookup"><span data-stu-id="404a1-125">Machine.Read</span></span> | <span data-ttu-id="404a1-126">'Machinegegevens lezen'</span><span class="sxs-lookup"><span data-stu-id="404a1-126">'Read machine information'</span></span>
<span data-ttu-id="404a1-127">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="404a1-127">Delegated (work or school account)</span></span> | <span data-ttu-id="404a1-128">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="404a1-128">Machine.ReadWrite</span></span> | <span data-ttu-id="404a1-129">'Machinegegevens lezen en schrijven'</span><span class="sxs-lookup"><span data-stu-id="404a1-129">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="404a1-130">Bij het verkrijgen van een token met gebruikersreferenties:</span><span class="sxs-lookup"><span data-stu-id="404a1-130">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="404a1-131">De gebruiker moet ten minste de volgende rolmachtiging hebben: 'Gegevens weergeven' [(Zie](user-roles.md) Rollen maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="404a1-131">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="404a1-132">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="404a1-132">HTTP request</span></span>
```
GET https://api.securitycenter.microsoft.com/api/machineactions/{id}
```

## <a name="request-headers"></a><span data-ttu-id="404a1-133">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="404a1-133">Request headers</span></span>

<span data-ttu-id="404a1-134">Naam</span><span class="sxs-lookup"><span data-stu-id="404a1-134">Name</span></span> | <span data-ttu-id="404a1-135">Type</span><span class="sxs-lookup"><span data-stu-id="404a1-135">Type</span></span> | <span data-ttu-id="404a1-136">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="404a1-136">Description</span></span>
:---|:---|:---
<span data-ttu-id="404a1-137">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="404a1-137">Authorization</span></span> | <span data-ttu-id="404a1-138">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="404a1-138">String</span></span> | <span data-ttu-id="404a1-139">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="404a1-139">Bearer {token}.</span></span> <span data-ttu-id="404a1-140">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="404a1-140">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="404a1-141">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="404a1-141">Request body</span></span>
<span data-ttu-id="404a1-142">Leeg</span><span class="sxs-lookup"><span data-stu-id="404a1-142">Empty</span></span>

## <a name="response"></a><span data-ttu-id="404a1-143">Antwoord</span><span class="sxs-lookup"><span data-stu-id="404a1-143">Response</span></span>
<span data-ttu-id="404a1-144">Als dit is gelukt, retourneert deze methode 200, Ok-antwoordcode met een [entiteit Machineactie.](machineaction.md)</span><span class="sxs-lookup"><span data-stu-id="404a1-144">If successful, this method returns 200, Ok response code with a [Machine Action](machineaction.md) entity.</span></span> <span data-ttu-id="404a1-145">Als de entiteit machineactie met de opgegeven id niet is gevonden- 404 Niet gevonden.</span><span class="sxs-lookup"><span data-stu-id="404a1-145">If machine action entity with the specified id was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="404a1-146">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="404a1-146">Example</span></span>

<span data-ttu-id="404a1-147">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="404a1-147">**Request**</span></span>

<span data-ttu-id="404a1-148">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="404a1-148">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/machineactions/2e9da30d-27f6-4208-81f2-9cd3d67893ba
```

<span data-ttu-id="404a1-149">**Antwoord**</span><span class="sxs-lookup"><span data-stu-id="404a1-149">**Response**</span></span>

<span data-ttu-id="404a1-150">Hier is een voorbeeld van het antwoord.</span><span class="sxs-lookup"><span data-stu-id="404a1-150">Here is an example of the response.</span></span>


```
HTTP/1.1 200 Ok
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineActions/$entity",
    "id": "5382f7ea-7557-4ab7-9782-d50480024a4e",
    "type": "Isolate",
    "scope": "Selective",
    "requestor": "Analyst@TestPrd.onmicrosoft.com",
    "requestorComment": "test for docs",
    "status": "Succeeded",
    "machineId": "7b1f4967d9728e5aa3c06a9e617a22a4a5a17378",
    "computerDnsName": "desktop-test",
    "creationDateTimeUtc": "2019-01-02T14:39:38.2262283Z",
    "lastUpdateDateTimeUtc": "2019-01-02T14:40:44.6596267Z",
    "relatedFileInfo": null
}


```
