---
title: Gebruikersgegevens met betrekking tot waarschuwingen ophalen
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: e895885a638c60a845ed4857c682cd472e42615c
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772315"
---
# <a name="get-alert-related-user-information-api"></a><span data-ttu-id="31811-104">Api voor waarschuwingsgerelateerde gebruikersgegevens</span><span class="sxs-lookup"><span data-stu-id="31811-104">Get alert related user information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="31811-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="31811-105">**Applies to:**</span></span>
- [<span data-ttu-id="31811-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="31811-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="31811-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="31811-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="31811-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="31811-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="31811-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="31811-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="31811-110">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="31811-110">API description</span></span>
<span data-ttu-id="31811-111">Hiermee wordt de gebruiker opgehaald die is gerelateerd aan een specifieke waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="31811-111">Retrieves the User related to a specific alert.</span></span>


## <a name="limitations"></a><span data-ttu-id="31811-112">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="31811-112">Limitations</span></span>
1. <span data-ttu-id="31811-113">U kunt query's uitvoeren op waarschuwingen die het laatst zijn bijgewerkt op basis van de geconfigureerde bewaarperiode.</span><span class="sxs-lookup"><span data-stu-id="31811-113">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="31811-114">Tariefbeperkingen voor deze API zijn 100 oproepen per minuut en 1500 oproepen per uur.</span><span class="sxs-lookup"><span data-stu-id="31811-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="31811-115">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="31811-115">Permissions</span></span>
<span data-ttu-id="31811-116">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="31811-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="31811-117">Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="31811-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="31811-118">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="31811-118">Permission type</span></span> |   <span data-ttu-id="31811-119">Machtiging</span><span class="sxs-lookup"><span data-stu-id="31811-119">Permission</span></span>  |   <span data-ttu-id="31811-120">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="31811-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="31811-121">Toepassing</span><span class="sxs-lookup"><span data-stu-id="31811-121">Application</span></span> |   <span data-ttu-id="31811-122">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="31811-122">User.Read.All</span></span> | <span data-ttu-id="31811-123">'Gebruikersprofielen lezen'</span><span class="sxs-lookup"><span data-stu-id="31811-123">'Read user profiles'</span></span>
<span data-ttu-id="31811-124">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="31811-124">Delegated (work or school account)</span></span> | <span data-ttu-id="31811-125">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="31811-125">User.Read.All</span></span> | <span data-ttu-id="31811-126">'Gebruikersprofielen lezen'</span><span class="sxs-lookup"><span data-stu-id="31811-126">'Read user profiles'</span></span>

>[!Note]
> <span data-ttu-id="31811-127">Bij het verkrijgen van een token met gebruikersreferenties:</span><span class="sxs-lookup"><span data-stu-id="31811-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="31811-128">De gebruiker moet ten minste de volgende rolmachtiging hebben: 'Gegevens weergeven' [(Zie](user-roles.md) Rollen maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="31811-128">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="31811-129">De gebruiker moet toegang hebben tot het apparaat dat aan de waarschuwing is gekoppeld, op basis van apparaatgroepinstellingen (Zie [Apparaatgroepen](machine-groups.md) maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="31811-129">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="31811-130">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="31811-130">HTTP request</span></span>
```
GET /api/alerts/{id}/user
```

## <a name="request-headers"></a><span data-ttu-id="31811-131">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="31811-131">Request headers</span></span>

<span data-ttu-id="31811-132">Naam</span><span class="sxs-lookup"><span data-stu-id="31811-132">Name</span></span> | <span data-ttu-id="31811-133">Type</span><span class="sxs-lookup"><span data-stu-id="31811-133">Type</span></span> | <span data-ttu-id="31811-134">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="31811-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="31811-135">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="31811-135">Authorization</span></span> | <span data-ttu-id="31811-136">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="31811-136">String</span></span> | <span data-ttu-id="31811-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="31811-137">Bearer {token}.</span></span> <span data-ttu-id="31811-138">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="31811-138">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="31811-139">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="31811-139">Request body</span></span>
<span data-ttu-id="31811-140">Leeg</span><span class="sxs-lookup"><span data-stu-id="31811-140">Empty</span></span>

## <a name="response"></a><span data-ttu-id="31811-141">Antwoord</span><span class="sxs-lookup"><span data-stu-id="31811-141">Response</span></span>
<span data-ttu-id="31811-142">Als dit is gelukt en een waarschuwing en een gebruiker bestaat- 200 OK met de gebruiker in de body.</span><span class="sxs-lookup"><span data-stu-id="31811-142">If successful and alert and a user exists - 200 OK with user in the body.</span></span> <span data-ttu-id="31811-143">Als waarschuwing of gebruiker niet is gevonden - 404 Niet gevonden.</span><span class="sxs-lookup"><span data-stu-id="31811-143">If alert or user not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="31811-144">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="31811-144">Example</span></span>

<span data-ttu-id="31811-145">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="31811-145">**Request**</span></span>

<span data-ttu-id="31811-146">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="31811-146">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/alerts/636688558380765161_2136280442/user
```

<span data-ttu-id="31811-147">**Antwoord**</span><span class="sxs-lookup"><span data-stu-id="31811-147">**Response**</span></span>

<span data-ttu-id="31811-148">Hier is een voorbeeld van het antwoord.</span><span class="sxs-lookup"><span data-stu-id="31811-148">Here is an example of the response.</span></span>


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
