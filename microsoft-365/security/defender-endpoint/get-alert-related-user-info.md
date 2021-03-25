---
title: Waarschuwingsgerelateerde gebruikersgegevens ontvangen
description: Lees hoe u de API Voor waarschuwingen gerelateerde gebruikersgegevens ophalen kunt gebruiken om de gebruiker op te halen die is gerelateerd aan een specifieke waarschuwing in Microsoft Defender voor Eindpunt.
keywords: api's, graph api, ondersteunde api's, get, alert, information, related, user
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
ms.technology: mde
ms.openlocfilehash: aee3c6fb381341c6823fbcb6766c0b761cb3413d
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166628"
---
# <a name="get-alert-related-user-information-api"></a><span data-ttu-id="ad7e4-104">Api voor waarschuwingsgerelateerde gebruikersgegevens</span><span class="sxs-lookup"><span data-stu-id="ad7e4-104">Get alert related user information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ad7e4-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="ad7e4-105">**Applies to:**</span></span>
- [<span data-ttu-id="ad7e4-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="ad7e4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ad7e4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ad7e4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="ad7e4-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="ad7e4-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ad7e4-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="ad7e4-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="ad7e4-110">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="ad7e4-110">API description</span></span>
<span data-ttu-id="ad7e4-111">Hiermee wordt de gebruiker opgehaald die is gerelateerd aan een specifieke waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="ad7e4-111">Retrieves the User related to a specific alert.</span></span>


## <a name="limitations"></a><span data-ttu-id="ad7e4-112">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="ad7e4-112">Limitations</span></span>
1. <span data-ttu-id="ad7e4-113">U kunt query's uitvoeren op waarschuwingen die het laatst zijn bijgewerkt op basis van de geconfigureerde bewaarperiode.</span><span class="sxs-lookup"><span data-stu-id="ad7e4-113">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="ad7e4-114">Tariefbeperkingen voor deze API zijn 100 oproepen per minuut en 1500 oproepen per uur.</span><span class="sxs-lookup"><span data-stu-id="ad7e4-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="ad7e4-115">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="ad7e4-115">Permissions</span></span>
<span data-ttu-id="ad7e4-116">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="ad7e4-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="ad7e4-117">Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="ad7e4-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="ad7e4-118">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="ad7e4-118">Permission type</span></span> |   <span data-ttu-id="ad7e4-119">Machtiging</span><span class="sxs-lookup"><span data-stu-id="ad7e4-119">Permission</span></span>  |   <span data-ttu-id="ad7e4-120">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="ad7e4-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="ad7e4-121">Toepassing</span><span class="sxs-lookup"><span data-stu-id="ad7e4-121">Application</span></span> |   <span data-ttu-id="ad7e4-122">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="ad7e4-122">User.Read.All</span></span> | <span data-ttu-id="ad7e4-123">'Gebruikersprofielen lezen'</span><span class="sxs-lookup"><span data-stu-id="ad7e4-123">'Read user profiles'</span></span>
<span data-ttu-id="ad7e4-124">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="ad7e4-124">Delegated (work or school account)</span></span> | <span data-ttu-id="ad7e4-125">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="ad7e4-125">User.Read.All</span></span> | <span data-ttu-id="ad7e4-126">'Gebruikersprofielen lezen'</span><span class="sxs-lookup"><span data-stu-id="ad7e4-126">'Read user profiles'</span></span>

>[!Note]
> <span data-ttu-id="ad7e4-127">Bij het verkrijgen van een token met gebruikersreferenties:</span><span class="sxs-lookup"><span data-stu-id="ad7e4-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="ad7e4-128">De gebruiker moet ten minste de volgende rolmachtiging hebben: 'Gegevens weergeven' [(Zie](user-roles.md) Rollen maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="ad7e4-128">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="ad7e4-129">De gebruiker moet toegang hebben tot het apparaat dat aan de waarschuwing is gekoppeld, op basis van apparaatgroepinstellingen (Zie [Apparaatgroepen](machine-groups.md) maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="ad7e4-129">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="ad7e4-130">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="ad7e4-130">HTTP request</span></span>
```
GET /api/alerts/{id}/user
```

## <a name="request-headers"></a><span data-ttu-id="ad7e4-131">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="ad7e4-131">Request headers</span></span>

<span data-ttu-id="ad7e4-132">Naam</span><span class="sxs-lookup"><span data-stu-id="ad7e4-132">Name</span></span> | <span data-ttu-id="ad7e4-133">Type</span><span class="sxs-lookup"><span data-stu-id="ad7e4-133">Type</span></span> | <span data-ttu-id="ad7e4-134">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="ad7e4-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="ad7e4-135">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="ad7e4-135">Authorization</span></span> | <span data-ttu-id="ad7e4-136">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="ad7e4-136">String</span></span> | <span data-ttu-id="ad7e4-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="ad7e4-137">Bearer {token}.</span></span> <span data-ttu-id="ad7e4-138">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="ad7e4-138">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="ad7e4-139">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="ad7e4-139">Request body</span></span>
<span data-ttu-id="ad7e4-140">Leeg</span><span class="sxs-lookup"><span data-stu-id="ad7e4-140">Empty</span></span>

## <a name="response"></a><span data-ttu-id="ad7e4-141">Antwoord</span><span class="sxs-lookup"><span data-stu-id="ad7e4-141">Response</span></span>
<span data-ttu-id="ad7e4-142">Als dit is gelukt en een waarschuwing en een gebruiker bestaat- 200 OK met de gebruiker in de body.</span><span class="sxs-lookup"><span data-stu-id="ad7e4-142">If successful and alert and a user exists - 200 OK with user in the body.</span></span> <span data-ttu-id="ad7e4-143">Als waarschuwing of gebruiker niet is gevonden - 404 Niet gevonden.</span><span class="sxs-lookup"><span data-stu-id="ad7e4-143">If alert or user not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="ad7e4-144">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="ad7e4-144">Example</span></span>

<span data-ttu-id="ad7e4-145">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="ad7e4-145">**Request**</span></span>

<span data-ttu-id="ad7e4-146">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="ad7e4-146">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/alerts/636688558380765161_2136280442/user
```

<span data-ttu-id="ad7e4-147">**Antwoord**</span><span class="sxs-lookup"><span data-stu-id="ad7e4-147">**Response**</span></span>

<span data-ttu-id="ad7e4-148">Hier is een voorbeeld van het antwoord.</span><span class="sxs-lookup"><span data-stu-id="ad7e4-148">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Users/$entity",
    "id": "contoso\\user1",
    "accountName": "user1",
    "accountDomain": "contoso",
    "accountSid": "S-1-5-21-72051607-1745760036-109187956-93922",
    "firstSeen": "2019-12-08T06:33:39Z",
    "lastSeen": "2020-01-05T06:58:34Z",
    "mostPrevalentMachineId": "0111b647235c26159bec3e5eb6c8c3a0cc3ab766",
    "leastPrevalentMachineId": "0111b647235c26159bec3e5eb6c8c3a0cc3ab766",
    "logonTypes": "Network",
    "logOnMachinesCount": 1,
    "isDomainAdmin": false,
    "isOnlyNetworkUser": false
}
```
