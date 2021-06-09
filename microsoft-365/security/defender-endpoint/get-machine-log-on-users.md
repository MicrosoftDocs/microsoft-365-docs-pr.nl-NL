---
title: API voor gebruikers van computerlogen krijgen
description: Meer informatie over het gebruik van de API Voor gebruikers van computermelding ophalen om een verzameling aangemelde gebruikers op te halen op een apparaat in Microsoft Defender voor Eindpunt.
keywords: api's, graph api, ondersteunde api's, krijgen, apparaat, aanmelden, gebruikers
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
ms.openlocfilehash: 1c81d2978677b751a8085f88b5c4732fd4a5a247
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770047"
---
# <a name="get-machine-logon-users-api"></a><span data-ttu-id="6cb3e-104">API voor gebruikers van computerlogen krijgen</span><span class="sxs-lookup"><span data-stu-id="6cb3e-104">Get machine logon users API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="6cb3e-105">**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="6cb3e-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="6cb3e-106">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="6cb3e-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6cb3e-107">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="6cb3e-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="6cb3e-108">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="6cb3e-108">API description</span></span>
<span data-ttu-id="6cb3e-109">Hiermee wordt een verzameling aangemelde gebruikers op een bepaald apparaat opgehaald.</span><span class="sxs-lookup"><span data-stu-id="6cb3e-109">Retrieves a collection of logged on users on a specific device.</span></span>


## <a name="limitations"></a><span data-ttu-id="6cb3e-110">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="6cb3e-110">Limitations</span></span>
1. <span data-ttu-id="6cb3e-111">U kunt query's uitvoeren op waarschuwingen die het laatst zijn bijgewerkt op basis van de geconfigureerde bewaarperiode.</span><span class="sxs-lookup"><span data-stu-id="6cb3e-111">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="6cb3e-112">Tariefbeperkingen voor deze API zijn 100 oproepen per minuut en 1500 oproepen per uur.</span><span class="sxs-lookup"><span data-stu-id="6cb3e-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="6cb3e-113">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="6cb3e-113">Permissions</span></span>
<span data-ttu-id="6cb3e-114">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="6cb3e-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="6cb3e-115">Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="6cb3e-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="6cb3e-116">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="6cb3e-116">Permission type</span></span> |   <span data-ttu-id="6cb3e-117">Machtiging</span><span class="sxs-lookup"><span data-stu-id="6cb3e-117">Permission</span></span>  |   <span data-ttu-id="6cb3e-118">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="6cb3e-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="6cb3e-119">Toepassing</span><span class="sxs-lookup"><span data-stu-id="6cb3e-119">Application</span></span> |   <span data-ttu-id="6cb3e-120">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="6cb3e-120">User.Read.All</span></span> | <span data-ttu-id="6cb3e-121">'Gebruikersprofielen lezen'</span><span class="sxs-lookup"><span data-stu-id="6cb3e-121">'Read user profiles'</span></span>
<span data-ttu-id="6cb3e-122">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="6cb3e-122">Delegated (work or school account)</span></span> | <span data-ttu-id="6cb3e-123">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="6cb3e-123">User.Read.All</span></span> | <span data-ttu-id="6cb3e-124">'Gebruikersprofielen lezen'</span><span class="sxs-lookup"><span data-stu-id="6cb3e-124">'Read user profiles'</span></span>

>[!Note]
> <span data-ttu-id="6cb3e-125">Bij het verkrijgen van een token met gebruikersreferenties:</span><span class="sxs-lookup"><span data-stu-id="6cb3e-125">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="6cb3e-126">De gebruiker moet ten minste de volgende rolmachtiging hebben: 'Gegevens weergeven'.</span><span class="sxs-lookup"><span data-stu-id="6cb3e-126">The user needs to have at least the following role permission: 'View Data'.</span></span> <span data-ttu-id="6cb3e-127">Zie Rollen maken [en beheren voor meer informatie](user-roles.md) .</span><span class="sxs-lookup"><span data-stu-id="6cb3e-127">For more information, see [Create and manage roles](user-roles.md) )</span></span>
>- <span data-ttu-id="6cb3e-128">Het antwoord bevat alleen gebruikers als het apparaat zichtbaar is voor de gebruiker, op basis van de instellingen van de apparaatgroep.</span><span class="sxs-lookup"><span data-stu-id="6cb3e-128">Response will include users only if the device is visible to the user, based on device group settings.</span></span> <span data-ttu-id="6cb3e-129">Zie Apparaatgroepen maken en beheren voor meer [informatie.](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="6cb3e-129">For more information, see [Create and manage device groups](machine-groups.md).</span></span>

## <a name="http-request"></a><span data-ttu-id="6cb3e-130">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="6cb3e-130">HTTP request</span></span>
```http
GET /api/machines/{id}/logonusers
```

## <a name="request-headers"></a><span data-ttu-id="6cb3e-131">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="6cb3e-131">Request headers</span></span>

<span data-ttu-id="6cb3e-132">Naam</span><span class="sxs-lookup"><span data-stu-id="6cb3e-132">Name</span></span> | <span data-ttu-id="6cb3e-133">Type</span><span class="sxs-lookup"><span data-stu-id="6cb3e-133">Type</span></span> | <span data-ttu-id="6cb3e-134">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="6cb3e-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="6cb3e-135">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="6cb3e-135">Authorization</span></span> | <span data-ttu-id="6cb3e-136">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="6cb3e-136">String</span></span> | <span data-ttu-id="6cb3e-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="6cb3e-137">Bearer {token}.</span></span> <span data-ttu-id="6cb3e-138">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="6cb3e-138">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="6cb3e-139">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="6cb3e-139">Request body</span></span>
<span data-ttu-id="6cb3e-140">Leeg</span><span class="sxs-lookup"><span data-stu-id="6cb3e-140">Empty</span></span>

## <a name="response"></a><span data-ttu-id="6cb3e-141">Antwoord</span><span class="sxs-lookup"><span data-stu-id="6cb3e-141">Response</span></span>
<span data-ttu-id="6cb3e-142">Als dit is gelukt en het apparaat [](user.md) bestaat- 200 OK met een lijst met gebruikersentiteiten in de body.</span><span class="sxs-lookup"><span data-stu-id="6cb3e-142">If successful and device exists - 200 OK with list of [user](user.md) entities in the body.</span></span> <span data-ttu-id="6cb3e-143">Als het apparaat niet is gevonden- 404 Niet gevonden.</span><span class="sxs-lookup"><span data-stu-id="6cb3e-143">If device was not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="6cb3e-144">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="6cb3e-144">Example</span></span>

<span data-ttu-id="6cb3e-145">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="6cb3e-145">**Request**</span></span>

<span data-ttu-id="6cb3e-146">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="6cb3e-146">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/logonusers
```

<span data-ttu-id="6cb3e-147">**Antwoord**</span><span class="sxs-lookup"><span data-stu-id="6cb3e-147">**Response**</span></span>

<span data-ttu-id="6cb3e-148">Hier is een voorbeeld van het antwoord.</span><span class="sxs-lookup"><span data-stu-id="6cb3e-148">Here is an example of the response.</span></span>


```http
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Users",
    "value": [
        {
            "id": "contoso\\user1",
            "accountName": "user1",
            "accountDomain": "contoso",
            "accountSid": "S-1-5-21-72051607-1745760036-109187956-93922",
            "firstSeen": "2019-12-18T08:02:54Z",
            "lastSeen": "2020-01-06T08:01:48Z",
            "logonTypes": "Interactive",
            "logOnMachinesCount": 8,
            "isDomainAdmin": true,
            "isOnlyNetworkUser": false
        },
        ...
    ]
}
```
