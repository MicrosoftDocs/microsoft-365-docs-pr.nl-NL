---
title: API voor domeinstatistieken krijgen
description: Meer informatie over het gebruik van de API Voor domeinstatistieken ophalen om de statistieken over het opgegeven domein op te halen in Microsoft Defender voor Eindpunt.
keywords: api's, graph api, ondersteunde api's, get, domein, domeingerelateerde apparaten
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
ms.openlocfilehash: 50b05b98ba507e120bbd6a3dc09f4633dac3a005
ms.sourcegitcommit: 787fb30fdae6d49347a87f4baae3cd140067e573
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/17/2021
ms.locfileid: "52998774"
---
# <a name="get-domain-statistics-api"></a><span data-ttu-id="f7cc3-104">API voor domeinstatistieken krijgen</span><span class="sxs-lookup"><span data-stu-id="f7cc3-104">Get domain statistics API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f7cc3-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="f7cc3-105">**Applies to:**</span></span>
- [<span data-ttu-id="f7cc3-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="f7cc3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f7cc3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f7cc3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f7cc3-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="f7cc3-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f7cc3-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="f7cc3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="f7cc3-110">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="f7cc3-110">API description</span></span>
<span data-ttu-id="f7cc3-111">Hiermee worden de statistieken van het opgegeven domein opgehaald.</span><span class="sxs-lookup"><span data-stu-id="f7cc3-111">Retrieves the statistics on the given domain.</span></span>


## <a name="limitations"></a><span data-ttu-id="f7cc3-112">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="f7cc3-112">Limitations</span></span>
1. <span data-ttu-id="f7cc3-113">Tariefbeperkingen voor deze API zijn 100 oproepen per minuut en 1500 oproepen per uur.</span><span class="sxs-lookup"><span data-stu-id="f7cc3-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="f7cc3-114">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="f7cc3-114">Permissions</span></span>
<span data-ttu-id="f7cc3-115">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="f7cc3-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="f7cc3-116">Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="f7cc3-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="f7cc3-117">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="f7cc3-117">Permission type</span></span> |   <span data-ttu-id="f7cc3-118">Machtiging</span><span class="sxs-lookup"><span data-stu-id="f7cc3-118">Permission</span></span>  |   <span data-ttu-id="f7cc3-119">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="f7cc3-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="f7cc3-120">Toepassing</span><span class="sxs-lookup"><span data-stu-id="f7cc3-120">Application</span></span> |   <span data-ttu-id="f7cc3-121">URL. Read.All</span><span class="sxs-lookup"><span data-stu-id="f7cc3-121">URL.Read.All</span></span> |  <span data-ttu-id="f7cc3-122">'URL's lezen'</span><span class="sxs-lookup"><span data-stu-id="f7cc3-122">'Read URLs'</span></span>
<span data-ttu-id="f7cc3-123">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="f7cc3-123">Delegated (work or school account)</span></span> | <span data-ttu-id="f7cc3-124">URL. Read.All</span><span class="sxs-lookup"><span data-stu-id="f7cc3-124">URL.Read.All</span></span> | <span data-ttu-id="f7cc3-125">'URL's lezen'</span><span class="sxs-lookup"><span data-stu-id="f7cc3-125">'Read URLs'</span></span>

>[!Note]
> <span data-ttu-id="f7cc3-126">Bij het verkrijgen van een token met gebruikersreferenties:</span><span class="sxs-lookup"><span data-stu-id="f7cc3-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="f7cc3-127">De gebruiker moet ten minste de volgende rolmachtiging hebben: 'Gegevens weergeven' [(Zie](user-roles.md) Rollen maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="f7cc3-127">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="f7cc3-128">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="f7cc3-128">HTTP request</span></span>
```
GET /api/domains/{domain}/stats
```

## <a name="request-headers"></a><span data-ttu-id="f7cc3-129">Aanvraagheaders</span><span class="sxs-lookup"><span data-stu-id="f7cc3-129">Request headers</span></span>

<span data-ttu-id="f7cc3-130">Header</span><span class="sxs-lookup"><span data-stu-id="f7cc3-130">Header</span></span> | <span data-ttu-id="f7cc3-131">Waarde</span><span class="sxs-lookup"><span data-stu-id="f7cc3-131">Value</span></span> 
:---|:---
<span data-ttu-id="f7cc3-132">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="f7cc3-132">Authorization</span></span> | <span data-ttu-id="f7cc3-133">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="f7cc3-133">Bearer {token}.</span></span> <span data-ttu-id="f7cc3-134">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="f7cc3-134">**Required**.</span></span>

## <a name="request-uri-parameters"></a><span data-ttu-id="f7cc3-135">URI-parameters aanvragen</span><span class="sxs-lookup"><span data-stu-id="f7cc3-135">Request URI parameters</span></span>

<span data-ttu-id="f7cc3-136">Naam</span><span class="sxs-lookup"><span data-stu-id="f7cc3-136">Name</span></span> | <span data-ttu-id="f7cc3-137">Type</span><span class="sxs-lookup"><span data-stu-id="f7cc3-137">Type</span></span> | <span data-ttu-id="f7cc3-138">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="f7cc3-138">Description</span></span>
:---|:---|:---
<span data-ttu-id="f7cc3-139">lookBackHours</span><span class="sxs-lookup"><span data-stu-id="f7cc3-139">lookBackHours</span></span> | <span data-ttu-id="f7cc3-140">Int32</span><span class="sxs-lookup"><span data-stu-id="f7cc3-140">Int32</span></span> | <span data-ttu-id="f7cc3-141">Definieert de uren die we terug zoeken om de statistieken te krijgen.</span><span class="sxs-lookup"><span data-stu-id="f7cc3-141">Defines the hours we search back to get the statistics.</span></span> <span data-ttu-id="f7cc3-142">Standaard is dit 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="f7cc3-142">Defaults to 30 days.</span></span> <span data-ttu-id="f7cc3-143">**Optioneel**.</span><span class="sxs-lookup"><span data-stu-id="f7cc3-143">**Optional**.</span></span>

## <a name="request-body"></a><span data-ttu-id="f7cc3-144">Aanvraagtekst</span><span class="sxs-lookup"><span data-stu-id="f7cc3-144">Request body</span></span>
<span data-ttu-id="f7cc3-145">Leeg</span><span class="sxs-lookup"><span data-stu-id="f7cc3-145">Empty</span></span>

## <a name="response"></a><span data-ttu-id="f7cc3-146">Antwoord</span><span class="sxs-lookup"><span data-stu-id="f7cc3-146">Response</span></span>
<span data-ttu-id="f7cc3-147">Als dit is gelukt en domein bestaat- 200 OK, met een statistisch object in de antwoord body.</span><span class="sxs-lookup"><span data-stu-id="f7cc3-147">If successful and domain exists - 200 OK, with statistics object in the response body.</span></span> <span data-ttu-id="f7cc3-148">Als domein niet bestaat- 404 Niet gevonden.</span><span class="sxs-lookup"><span data-stu-id="f7cc3-148">If domain does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="f7cc3-149">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="f7cc3-149">Example</span></span>

<span data-ttu-id="f7cc3-150">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="f7cc3-150">**Request**</span></span>

<span data-ttu-id="f7cc3-151">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="f7cc3-151">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/domains/example.com/stats?lookBackHours=48
```

<span data-ttu-id="f7cc3-152">**Antwoord**</span><span class="sxs-lookup"><span data-stu-id="f7cc3-152">**Response**</span></span>

<span data-ttu-id="f7cc3-153">Hier is een voorbeeld van het antwoord.</span><span class="sxs-lookup"><span data-stu-id="f7cc3-153">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.InOrgDomainStats",
    "host": "example.com",
    "organizationPrevalence": 4070,
    "orgFirstSeen": "2017-07-30T13:23:48Z",
    "orgLastSeen": "2017-08-29T13:09:05Z"
}
```
