---
title: API voor IP-statistieken krijgen
description: Krijg de meest recente statistieken voor uw IP-adres met Microsoft Defender voor Eindpunt.
keywords: api's, graph api, ondersteunde api's, get, ip, statistics, prevalentie
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
ms.openlocfilehash: 4919f082c115d8a57960ec49532b6cda6a63833f
ms.sourcegitcommit: 787fb30fdae6d49347a87f4baae3cd140067e573
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/17/2021
ms.locfileid: "52998726"
---
# <a name="get-ip-statistics-api"></a><span data-ttu-id="3b9e1-104">API voor IP-statistieken krijgen</span><span class="sxs-lookup"><span data-stu-id="3b9e1-104">Get IP statistics API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3b9e1-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="3b9e1-105">**Applies to:**</span></span>
- [<span data-ttu-id="3b9e1-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="3b9e1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3b9e1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3b9e1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="3b9e1-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="3b9e1-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="3b9e1-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="3b9e1-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="3b9e1-110">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="3b9e1-110">API description</span></span>
<span data-ttu-id="3b9e1-111">Hiermee worden de statistieken voor het opgegeven IP-adres opgehaald.</span><span class="sxs-lookup"><span data-stu-id="3b9e1-111">Retrieves the statistics for the given IP.</span></span>

## <a name="limitations"></a><span data-ttu-id="3b9e1-112">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="3b9e1-112">Limitations</span></span>
1. <span data-ttu-id="3b9e1-113">Tariefbeperkingen voor deze API zijn 100 oproepen per minuut en 1500 oproepen per uur.</span><span class="sxs-lookup"><span data-stu-id="3b9e1-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="3b9e1-114">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="3b9e1-114">Permissions</span></span>
<span data-ttu-id="3b9e1-115">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="3b9e1-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="3b9e1-116">Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="3b9e1-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="3b9e1-117">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="3b9e1-117">Permission type</span></span> |   <span data-ttu-id="3b9e1-118">Machtiging</span><span class="sxs-lookup"><span data-stu-id="3b9e1-118">Permission</span></span>  |   <span data-ttu-id="3b9e1-119">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="3b9e1-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="3b9e1-120">Toepassing</span><span class="sxs-lookup"><span data-stu-id="3b9e1-120">Application</span></span> |   <span data-ttu-id="3b9e1-121">Ip.Read.All</span><span class="sxs-lookup"><span data-stu-id="3b9e1-121">Ip.Read.All</span></span> |   <span data-ttu-id="3b9e1-122">'Ip-adresprofielen lezen'</span><span class="sxs-lookup"><span data-stu-id="3b9e1-122">'Read IP address profiles'</span></span>
<span data-ttu-id="3b9e1-123">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="3b9e1-123">Delegated (work or school account)</span></span> | <span data-ttu-id="3b9e1-124">Ip.Read.All</span><span class="sxs-lookup"><span data-stu-id="3b9e1-124">Ip.Read.All</span></span> |  <span data-ttu-id="3b9e1-125">'Ip-adresprofielen lezen'</span><span class="sxs-lookup"><span data-stu-id="3b9e1-125">'Read IP address profiles'</span></span>

>[!NOTE]
> <span data-ttu-id="3b9e1-126">Bij het verkrijgen van een token met gebruikersreferenties:</span><span class="sxs-lookup"><span data-stu-id="3b9e1-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="3b9e1-127">De gebruiker moet ten minste de volgende rolmachtiging hebben: 'Gegevens weergeven' [(Zie](user-roles.md) Rollen maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="3b9e1-127">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="3b9e1-128">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="3b9e1-128">HTTP request</span></span>

```http
GET /api/ips/{ip}/stats
```

## <a name="request-headers"></a><span data-ttu-id="3b9e1-129">Aanvraagheaders</span><span class="sxs-lookup"><span data-stu-id="3b9e1-129">Request headers</span></span>

<span data-ttu-id="3b9e1-130">Naam</span><span class="sxs-lookup"><span data-stu-id="3b9e1-130">Name</span></span> | <span data-ttu-id="3b9e1-131">Type</span><span class="sxs-lookup"><span data-stu-id="3b9e1-131">Type</span></span> | <span data-ttu-id="3b9e1-132">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="3b9e1-132">Description</span></span>
:---|:---|:---
<span data-ttu-id="3b9e1-133">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="3b9e1-133">Authorization</span></span> | <span data-ttu-id="3b9e1-134">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="3b9e1-134">String</span></span> | <span data-ttu-id="3b9e1-135">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="3b9e1-135">Bearer {token}.</span></span> <span data-ttu-id="3b9e1-136">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="3b9e1-136">**Required**.</span></span>

## <a name="request-uri-parameters"></a><span data-ttu-id="3b9e1-137">URI-parameters aanvragen</span><span class="sxs-lookup"><span data-stu-id="3b9e1-137">Request URI parameters</span></span>

<span data-ttu-id="3b9e1-138">Naam</span><span class="sxs-lookup"><span data-stu-id="3b9e1-138">Name</span></span> | <span data-ttu-id="3b9e1-139">Type</span><span class="sxs-lookup"><span data-stu-id="3b9e1-139">Type</span></span> | <span data-ttu-id="3b9e1-140">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="3b9e1-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="3b9e1-141">lookBackHours</span><span class="sxs-lookup"><span data-stu-id="3b9e1-141">lookBackHours</span></span> | <span data-ttu-id="3b9e1-142">Int32</span><span class="sxs-lookup"><span data-stu-id="3b9e1-142">Int32</span></span> | <span data-ttu-id="3b9e1-143">Definieert de uren die we terug zoeken om de statistieken te krijgen.</span><span class="sxs-lookup"><span data-stu-id="3b9e1-143">Defines the hours we search back to get the statistics.</span></span> <span data-ttu-id="3b9e1-144">Standaard is dit 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="3b9e1-144">Defaults to 30 days.</span></span> <span data-ttu-id="3b9e1-145">**Optioneel**.</span><span class="sxs-lookup"><span data-stu-id="3b9e1-145">**Optional**.</span></span>

## <a name="request-body"></a><span data-ttu-id="3b9e1-146">Aanvraagtekst</span><span class="sxs-lookup"><span data-stu-id="3b9e1-146">Request body</span></span>
<span data-ttu-id="3b9e1-147">Leeg</span><span class="sxs-lookup"><span data-stu-id="3b9e1-147">Empty</span></span>

## <a name="response"></a><span data-ttu-id="3b9e1-148">Antwoord</span><span class="sxs-lookup"><span data-stu-id="3b9e1-148">Response</span></span>
<span data-ttu-id="3b9e1-149">Als dit is gelukt en ip bestaat- 200 OK met statistische gegevens in de body.</span><span class="sxs-lookup"><span data-stu-id="3b9e1-149">If successful and ip exists - 200 OK with statistical data in the body.</span></span> <span data-ttu-id="3b9e1-150">IP bestaat niet - 404 Niet gevonden.</span><span class="sxs-lookup"><span data-stu-id="3b9e1-150">IP do not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="3b9e1-151">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="3b9e1-151">Example</span></span>

<span data-ttu-id="3b9e1-152">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="3b9e1-152">**Request**</span></span>

<span data-ttu-id="3b9e1-153">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="3b9e1-153">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/ips/10.209.67.177/stats?lookBackHours=48
```

<span data-ttu-id="3b9e1-154">**Antwoord**</span><span class="sxs-lookup"><span data-stu-id="3b9e1-154">**Response**</span></span>

<span data-ttu-id="3b9e1-155">Hier is een voorbeeld van het antwoord.</span><span class="sxs-lookup"><span data-stu-id="3b9e1-155">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.InOrgIPStats",
    "ipAddress": "10.209.67.177",
    "organizationPrevalence": 63515,
    "orgFirstSeen": "2017-07-30T13:36:06Z",
    "orgLastSeen": "2017-08-29T13:32:59Z"
}
```


| <span data-ttu-id="3b9e1-156">Naam</span><span class="sxs-lookup"><span data-stu-id="3b9e1-156">Name</span></span> | <span data-ttu-id="3b9e1-157">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="3b9e1-157">Description</span></span> |
| :--- | :---------- |
| <span data-ttu-id="3b9e1-158">Organisatieprepresenties</span><span class="sxs-lookup"><span data-stu-id="3b9e1-158">Organization prevalence</span></span> | <span data-ttu-id="3b9e1-159">het duidelijke aantal apparaten dat de netwerkverbinding met dit IP-adres heeft geopend.</span><span class="sxs-lookup"><span data-stu-id="3b9e1-159">the distinct count of devices that opened network connection to this IP.</span></span> |
| <span data-ttu-id="3b9e1-160">Organisatie die voor het eerst is gezien</span><span class="sxs-lookup"><span data-stu-id="3b9e1-160">Org first seen</span></span> | <span data-ttu-id="3b9e1-161">de eerste verbinding voor dit IP-adres in de organisatie.</span><span class="sxs-lookup"><span data-stu-id="3b9e1-161">the first connection for this IP in the organization.</span></span> |
| <span data-ttu-id="3b9e1-162">Org laatst gezien</span><span class="sxs-lookup"><span data-stu-id="3b9e1-162">Org last seen</span></span>  | <span data-ttu-id="3b9e1-163">de laatste verbinding voor dit IP-adres in de organisatie.</span><span class="sxs-lookup"><span data-stu-id="3b9e1-163">the last connection for this IP in the organization.</span></span> |

> [!NOTE]
> <span data-ttu-id="3b9e1-164">Deze statistische gegevens zijn gebaseerd op gegevens uit de afgelopen 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="3b9e1-164">This statistic information is based on data from the past 30 days.</span></span> 
