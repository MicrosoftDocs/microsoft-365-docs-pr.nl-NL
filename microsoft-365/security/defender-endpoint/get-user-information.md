---
title: Api voor gebruikersgegevens verkrijgen
description: Meer informatie over het gebruik van de API Gebruikersgegevens ophalen om een gebruikersentiteit op basis van de sleutel of gebruikersnaam op te halen in Microsoft Defender voor Eindpunt.
keywords: api's, graph api, ondersteunde api's, get, gebruiker, gebruikersgegevens
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
ms.openlocfilehash: 1c5b8fa6e0f1fd887c857bd4e6451a5e59b708af
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198539"
---
# <a name="get-user-information-api"></a><span data-ttu-id="669a9-104">Api voor gebruikersgegevens verkrijgen</span><span class="sxs-lookup"><span data-stu-id="669a9-104">Get user information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="669a9-105">**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="669a9-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="669a9-106">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="669a9-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="669a9-107">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="669a9-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

> <span data-ttu-id="669a9-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="669a9-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="669a9-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="669a9-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)
<span data-ttu-id="669a9-110">Een gebruikersentiteit ophalen met de sleutel (gebruikersnaam).</span><span class="sxs-lookup"><span data-stu-id="669a9-110">Retrieve a User entity by key (user name).</span></span>

## <a name="permissions"></a><span data-ttu-id="669a9-111">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="669a9-111">Permissions</span></span>
<span data-ttu-id="669a9-112">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="669a9-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="669a9-113">Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="669a9-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="669a9-114">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="669a9-114">Permission type</span></span> |   <span data-ttu-id="669a9-115">Machtiging</span><span class="sxs-lookup"><span data-stu-id="669a9-115">Permission</span></span>  |   <span data-ttu-id="669a9-116">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="669a9-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="669a9-117">Toepassing</span><span class="sxs-lookup"><span data-stu-id="669a9-117">Application</span></span> |   <span data-ttu-id="669a9-118">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="669a9-118">User.Read.All</span></span> | <span data-ttu-id="669a9-119">'Alle gebruikersprofielen lezen'</span><span class="sxs-lookup"><span data-stu-id="669a9-119">'Read all user profiles'</span></span>

## <a name="http-request"></a><span data-ttu-id="669a9-120">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="669a9-120">HTTP request</span></span>
```
GET /api/users/{id}/
```

## <a name="request-headers"></a><span data-ttu-id="669a9-121">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="669a9-121">Request headers</span></span>

<span data-ttu-id="669a9-122">Naam</span><span class="sxs-lookup"><span data-stu-id="669a9-122">Name</span></span> | <span data-ttu-id="669a9-123">Type</span><span class="sxs-lookup"><span data-stu-id="669a9-123">Type</span></span> | <span data-ttu-id="669a9-124">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="669a9-124">Description</span></span>
:---|:---|:---
<span data-ttu-id="669a9-125">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="669a9-125">Authorization</span></span> | <span data-ttu-id="669a9-126">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="669a9-126">String</span></span> | <span data-ttu-id="669a9-127">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="669a9-127">Bearer {token}.</span></span> <span data-ttu-id="669a9-128">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="669a9-128">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="669a9-129">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="669a9-129">Request body</span></span>
<span data-ttu-id="669a9-130">Leeg</span><span class="sxs-lookup"><span data-stu-id="669a9-130">Empty</span></span>

## <a name="response"></a><span data-ttu-id="669a9-131">Antwoord</span><span class="sxs-lookup"><span data-stu-id="669a9-131">Response</span></span>
<span data-ttu-id="669a9-132">Als dit is gelukt en de gebruiker bestaat- 200 OK met [gebruikersentiteit](user.md) in de body.</span><span class="sxs-lookup"><span data-stu-id="669a9-132">If successful and user exists - 200 OK with [user](user.md) entity in the body.</span></span> <span data-ttu-id="669a9-133">Als gebruiker niet bestaat- 404 Niet gevonden.</span><span class="sxs-lookup"><span data-stu-id="669a9-133">If user does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="669a9-134">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="669a9-134">Example</span></span>

<span data-ttu-id="669a9-135">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="669a9-135">**Request**</span></span>

<span data-ttu-id="669a9-136">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="669a9-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/users/user1
Content-type: application/json
```

<span data-ttu-id="669a9-137">**Antwoord**</span><span class="sxs-lookup"><span data-stu-id="669a9-137">**Response**</span></span>

<span data-ttu-id="669a9-138">Hier is een voorbeeld van het antwoord.</span><span class="sxs-lookup"><span data-stu-id="669a9-138">Here is an example of the response.</span></span>


```
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Users/$entity",
    "id": "user1",
    "firstSeen": "2018-08-02T00:00:00Z",
    "lastSeen": "2018-08-04T00:00:00Z",
    "mostPrevalentMachineId": null,
    "leastPrevalentMachineId": null,
    "logonTypes": "Network",
    "logOnMachinesCount": 3,
    "isDomainAdmin": false,
    "isOnlyNetworkUser": null
}
```
