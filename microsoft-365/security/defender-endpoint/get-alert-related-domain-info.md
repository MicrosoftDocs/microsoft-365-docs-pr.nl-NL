---
title: Informatie over waarschuwingsgerelateerde domeinen
description: Alle domeinen ophalen die betrekking hebben op een specifieke waarschuwing met Microsoft Defender voor Eindpunt.
keywords: api's, graph api, ondersteunde api's, waarschuwingsinformatie, waarschuwingsgegevens, gerelateerd domein
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
ms.openlocfilehash: 0cb09b23df8243d970069d087976ddc79394b67d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200411"
---
# <a name="get-alert-related-domain-information-api"></a><span data-ttu-id="c3704-104">Api voor waarschuwingsgerelateerde domeingegevens krijgen</span><span class="sxs-lookup"><span data-stu-id="c3704-104">Get alert related domain information API</span></span>

<span data-ttu-id="c3704-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="c3704-105">**Applies to:**</span></span> 
- [<span data-ttu-id="c3704-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="c3704-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

- <span data-ttu-id="c3704-107">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="c3704-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c3704-108">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="c3704-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="c3704-109">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="c3704-109">API description</span></span>
<span data-ttu-id="c3704-110">Hiermee worden alle domeinen opgehaald die betrekking hebben op een specifieke waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="c3704-110">Retrieves all domains related to a specific alert.</span></span>


## <a name="limitations"></a><span data-ttu-id="c3704-111">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="c3704-111">Limitations</span></span>
1. <span data-ttu-id="c3704-112">U kunt query's uitvoeren op waarschuwingen die het laatst zijn bijgewerkt op basis van de geconfigureerde bewaarperiode.</span><span class="sxs-lookup"><span data-stu-id="c3704-112">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="c3704-113">Tariefbeperkingen voor deze API zijn 100 oproepen per minuut en 1500 oproepen per uur.</span><span class="sxs-lookup"><span data-stu-id="c3704-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="c3704-114">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="c3704-114">Permissions</span></span>
<span data-ttu-id="c3704-115">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="c3704-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="c3704-116">Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="c3704-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="c3704-117">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="c3704-117">Permission type</span></span> | <span data-ttu-id="c3704-118">Machtiging</span><span class="sxs-lookup"><span data-stu-id="c3704-118">Permission</span></span> | <span data-ttu-id="c3704-119">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="c3704-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="c3704-120">Toepassing</span><span class="sxs-lookup"><span data-stu-id="c3704-120">Application</span></span> | <span data-ttu-id="c3704-121">URL. Read.All</span><span class="sxs-lookup"><span data-stu-id="c3704-121">URL.Read.All</span></span> | <span data-ttu-id="c3704-122">'URL's lezen'</span><span class="sxs-lookup"><span data-stu-id="c3704-122">'Read URLs'</span></span>
<span data-ttu-id="c3704-123">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="c3704-123">Delegated (work or school account)</span></span> | <span data-ttu-id="c3704-124">URL. Read.All</span><span class="sxs-lookup"><span data-stu-id="c3704-124">URL.Read.All</span></span> | <span data-ttu-id="c3704-125">'URL's lezen'</span><span class="sxs-lookup"><span data-stu-id="c3704-125">'Read URLs'</span></span>

>[!Note]
> <span data-ttu-id="c3704-126">Bij het verkrijgen van een token met gebruikersreferenties:</span><span class="sxs-lookup"><span data-stu-id="c3704-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="c3704-127">De gebruiker moet ten minste de volgende rolmachtiging hebben: 'Gegevens weergeven' [(Zie](user-roles.md) Rollen maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="c3704-127">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="c3704-128">De gebruiker moet toegang hebben tot het apparaat dat aan de waarschuwing is gekoppeld, op basis van apparaatgroepinstellingen (Zie [Apparaatgroepen](machine-groups.md) maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="c3704-128">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="c3704-129">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="c3704-129">HTTP request</span></span>
```
GET /api/alerts/{id}/domains
```

## <a name="request-headers"></a><span data-ttu-id="c3704-130">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="c3704-130">Request headers</span></span>

<span data-ttu-id="c3704-131">Naam</span><span class="sxs-lookup"><span data-stu-id="c3704-131">Name</span></span> | <span data-ttu-id="c3704-132">Type</span><span class="sxs-lookup"><span data-stu-id="c3704-132">Type</span></span> | <span data-ttu-id="c3704-133">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="c3704-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="c3704-134">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="c3704-134">Authorization</span></span> | <span data-ttu-id="c3704-135">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="c3704-135">String</span></span> | <span data-ttu-id="c3704-136">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="c3704-136">Bearer {token}.</span></span> <span data-ttu-id="c3704-137">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="c3704-137">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="c3704-138">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="c3704-138">Request body</span></span>
<span data-ttu-id="c3704-139">Leeg</span><span class="sxs-lookup"><span data-stu-id="c3704-139">Empty</span></span>

## <a name="response"></a><span data-ttu-id="c3704-140">Antwoord</span><span class="sxs-lookup"><span data-stu-id="c3704-140">Response</span></span>
<span data-ttu-id="c3704-141">Als er een succesvol en waarschuwings- en domein bestaat- 200 OK.</span><span class="sxs-lookup"><span data-stu-id="c3704-141">If successful and alert and domain exist - 200 OK.</span></span> <span data-ttu-id="c3704-142">Als waarschuwing niet is gevonden - 404 Niet gevonden.</span><span class="sxs-lookup"><span data-stu-id="c3704-142">If alert not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="c3704-143">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="c3704-143">Example</span></span>

<span data-ttu-id="c3704-144">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="c3704-144">**Request**</span></span>

<span data-ttu-id="c3704-145">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="c3704-145">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/alerts/636688558380765161_2136280442/domains
```

<span data-ttu-id="c3704-146">**Antwoord**</span><span class="sxs-lookup"><span data-stu-id="c3704-146">**Response**</span></span>

<span data-ttu-id="c3704-147">Hier is een voorbeeld van het antwoord.</span><span class="sxs-lookup"><span data-stu-id="c3704-147">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/$metadata#Domains",
    "value": [
        {
            "host": "www.example.com"
        },
        {
            "host": "www.example2.com"
        }
        ...
    ]
}

```
