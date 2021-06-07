---
title: Machine op id-API krijgen
description: Meer informatie over het gebruik van de API Computer ophalen op id om een computer op te halen op de apparaat-id of computernaam in Microsoft Defender voor Eindpunt.
keywords: api's, graph api, ondersteunde api's, get, apparaten, entiteit, id
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
ms.openlocfilehash: e4ed5a68b0f4c5e9472702d3cc2798a810e4f84e
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769471"
---
# <a name="get-machine-by-id-api"></a><span data-ttu-id="baf66-104">Machine op id-API krijgen</span><span class="sxs-lookup"><span data-stu-id="baf66-104">Get machine by ID API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="baf66-105">**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="baf66-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>


> <span data-ttu-id="baf66-106">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="baf66-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="baf66-107">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="baf66-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="baf66-108">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="baf66-108">API description</span></span>
<span data-ttu-id="baf66-109">Hiermee wordt specifieke [machine opgehaald](machine.md) op de apparaat-id of computernaam.</span><span class="sxs-lookup"><span data-stu-id="baf66-109">Retrieves specific [Machine](machine.md) by its device ID or computer name.</span></span>


## <a name="limitations"></a><span data-ttu-id="baf66-110">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="baf66-110">Limitations</span></span>
1. <span data-ttu-id="baf66-111">U kunt apparaten voor het laatst zien volgens uw geconfigureerd bewaarbeleid.</span><span class="sxs-lookup"><span data-stu-id="baf66-111">You can get devices last seen according to your configured retention policy.</span></span>
2. <span data-ttu-id="baf66-112">Tariefbeperkingen voor deze API zijn 100 oproepen per minuut en 1500 oproepen per uur.</span><span class="sxs-lookup"><span data-stu-id="baf66-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="baf66-113">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="baf66-113">Permissions</span></span>
<span data-ttu-id="baf66-114">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="baf66-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="baf66-115">Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="baf66-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="baf66-116">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="baf66-116">Permission type</span></span> |   <span data-ttu-id="baf66-117">Machtiging</span><span class="sxs-lookup"><span data-stu-id="baf66-117">Permission</span></span>  |   <span data-ttu-id="baf66-118">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="baf66-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="baf66-119">Toepassing</span><span class="sxs-lookup"><span data-stu-id="baf66-119">Application</span></span> |   <span data-ttu-id="baf66-120">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="baf66-120">Machine.Read.All</span></span> |  <span data-ttu-id="baf66-121">'Alle machineprofielen lezen'</span><span class="sxs-lookup"><span data-stu-id="baf66-121">'Read all machine profiles'</span></span>
<span data-ttu-id="baf66-122">Toepassing</span><span class="sxs-lookup"><span data-stu-id="baf66-122">Application</span></span> |   <span data-ttu-id="baf66-123">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="baf66-123">Machine.ReadWrite.All</span></span> | <span data-ttu-id="baf66-124">'Alle computergegevens lezen en schrijven'</span><span class="sxs-lookup"><span data-stu-id="baf66-124">'Read and write all machine information'</span></span>
<span data-ttu-id="baf66-125">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="baf66-125">Delegated (work or school account)</span></span> | <span data-ttu-id="baf66-126">Machine.Lezen</span><span class="sxs-lookup"><span data-stu-id="baf66-126">Machine.Read</span></span> | <span data-ttu-id="baf66-127">'Machinegegevens lezen'</span><span class="sxs-lookup"><span data-stu-id="baf66-127">'Read machine information'</span></span>
<span data-ttu-id="baf66-128">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="baf66-128">Delegated (work or school account)</span></span> | <span data-ttu-id="baf66-129">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="baf66-129">Machine.ReadWrite</span></span> | <span data-ttu-id="baf66-130">'Machinegegevens lezen en schrijven'</span><span class="sxs-lookup"><span data-stu-id="baf66-130">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="baf66-131">Bij het verkrijgen van een token met gebruikersreferenties:</span><span class="sxs-lookup"><span data-stu-id="baf66-131">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="baf66-132">De gebruiker moet ten minste de volgende rolmachtiging hebben: 'Gegevens weergeven' [(Zie](user-roles.md) Rollen maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="baf66-132">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="baf66-133">Gebruiker moet toegang hebben tot het apparaat, op basis van instellingen voor apparaatgroep (Zie [Apparaatgroepen](machine-groups.md) maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="baf66-133">User needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>


## <a name="http-request"></a><span data-ttu-id="baf66-134">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="baf66-134">HTTP request</span></span>
```http
GET /api/machines/{id}
```

## <a name="request-headers"></a><span data-ttu-id="baf66-135">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="baf66-135">Request headers</span></span>

<span data-ttu-id="baf66-136">Naam</span><span class="sxs-lookup"><span data-stu-id="baf66-136">Name</span></span> | <span data-ttu-id="baf66-137">Type</span><span class="sxs-lookup"><span data-stu-id="baf66-137">Type</span></span> | <span data-ttu-id="baf66-138">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="baf66-138">Description</span></span>
:---|:---|:---
<span data-ttu-id="baf66-139">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="baf66-139">Authorization</span></span> | <span data-ttu-id="baf66-140">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="baf66-140">String</span></span> | <span data-ttu-id="baf66-141">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="baf66-141">Bearer {token}.</span></span> <span data-ttu-id="baf66-142">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="baf66-142">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="baf66-143">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="baf66-143">Request body</span></span>
<span data-ttu-id="baf66-144">Leeg</span><span class="sxs-lookup"><span data-stu-id="baf66-144">Empty</span></span>

## <a name="response"></a><span data-ttu-id="baf66-145">Antwoord</span><span class="sxs-lookup"><span data-stu-id="baf66-145">Response</span></span>
<span data-ttu-id="baf66-146">Als dit is gelukt en het apparaat bestaat- 200 OK met de [machine-entiteit](machine.md) in de body.</span><span class="sxs-lookup"><span data-stu-id="baf66-146">If successful and device exists - 200 OK with the [machine](machine.md) entity in the body.</span></span>
<span data-ttu-id="baf66-147">Als de computer met de opgegeven id niet is gevonden- 404 Niet gevonden.</span><span class="sxs-lookup"><span data-stu-id="baf66-147">If machine with the specified ID was not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="baf66-148">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="baf66-148">Example</span></span>

<span data-ttu-id="baf66-149">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="baf66-149">**Request**</span></span>

<span data-ttu-id="baf66-150">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="baf66-150">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07
```

<span data-ttu-id="baf66-151">**Antwoord**</span><span class="sxs-lookup"><span data-stu-id="baf66-151">**Response**</span></span>

<span data-ttu-id="baf66-152">Hier is een voorbeeld van het antwoord.</span><span class="sxs-lookup"><span data-stu-id="baf66-152">Here is an example of the response.</span></span>


```http
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Machine",
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

```
