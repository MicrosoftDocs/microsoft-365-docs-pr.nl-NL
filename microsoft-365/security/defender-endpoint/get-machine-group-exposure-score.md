---
title: Lijstblootstellingsscore per apparaatgroep
description: Hiermee wordt een lijst met blootstellingsscores per apparaatgroep opgehaald.
keywords: api's, graph api, ondersteunde api's, get, exposure score, device group, device group exposure score
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: dansimp
ms.author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 54b3e0cd63189e67de0aa101634508ff8833dc6a
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500245"
---
# <a name="list-exposure-score-by-device-group"></a><span data-ttu-id="69cbb-104">Lijstblootstellingsscore per apparaatgroep</span><span class="sxs-lookup"><span data-stu-id="69cbb-104">List exposure score by device group</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="69cbb-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="69cbb-105">**Applies to:**</span></span>
- [<span data-ttu-id="69cbb-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="69cbb-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="69cbb-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="69cbb-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="69cbb-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="69cbb-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="69cbb-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="69cbb-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="69cbb-110">Hiermee wordt een verzameling waarschuwingen opgehaald die betrekking hebben op een bepaald domeinadres.</span><span class="sxs-lookup"><span data-stu-id="69cbb-110">Retrieves a collection of alerts related to a given domain address.</span></span>

## <a name="permissions"></a><span data-ttu-id="69cbb-111">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="69cbb-111">Permissions</span></span>

<span data-ttu-id="69cbb-112">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="69cbb-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="69cbb-113">Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="69cbb-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="69cbb-114">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="69cbb-114">Permission type</span></span> |   <span data-ttu-id="69cbb-115">Machtiging</span><span class="sxs-lookup"><span data-stu-id="69cbb-115">Permission</span></span>  |   <span data-ttu-id="69cbb-116">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="69cbb-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="69cbb-117">Toepassing</span><span class="sxs-lookup"><span data-stu-id="69cbb-117">Application</span></span> | <span data-ttu-id="69cbb-118">Score.Read.All</span><span class="sxs-lookup"><span data-stu-id="69cbb-118">Score.Read.All</span></span> | <span data-ttu-id="69cbb-119">'Score bedreigings- en kwetsbaarheidsbeheer lezen'</span><span class="sxs-lookup"><span data-stu-id="69cbb-119">'Read Threat and Vulnerability Management score'</span></span>
<span data-ttu-id="69cbb-120">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="69cbb-120">Delegated (work or school account)</span></span> | <span data-ttu-id="69cbb-121">Score.Read</span><span class="sxs-lookup"><span data-stu-id="69cbb-121">Score.Read</span></span> | <span data-ttu-id="69cbb-122">'Score bedreigings- en kwetsbaarheidsbeheer lezen'</span><span class="sxs-lookup"><span data-stu-id="69cbb-122">'Read Threat and Vulnerability Management score'</span></span>

## <a name="http-request"></a><span data-ttu-id="69cbb-123">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="69cbb-123">HTTP request</span></span>

```
GET /api/exposureScore/ByMachineGroups
```

## <a name="request-headers"></a><span data-ttu-id="69cbb-124">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="69cbb-124">Request headers</span></span>

| <span data-ttu-id="69cbb-125">Naam</span><span class="sxs-lookup"><span data-stu-id="69cbb-125">Name</span></span>        | <span data-ttu-id="69cbb-126">Type</span><span class="sxs-lookup"><span data-stu-id="69cbb-126">Type</span></span> | <span data-ttu-id="69cbb-127">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="69cbb-127">Description</span></span>
|:--------------|:-------|:--------------|
| <span data-ttu-id="69cbb-128">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="69cbb-128">Authorization</span></span> | <span data-ttu-id="69cbb-129">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="69cbb-129">String</span></span> | <span data-ttu-id="69cbb-130">Bearer {token}. **Vereist**.</span><span class="sxs-lookup"><span data-stu-id="69cbb-130">Bearer {token}.**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="69cbb-131">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="69cbb-131">Request body</span></span>

<span data-ttu-id="69cbb-132">Leeg</span><span class="sxs-lookup"><span data-stu-id="69cbb-132">Empty</span></span>

## <a name="response"></a><span data-ttu-id="69cbb-133">Antwoord</span><span class="sxs-lookup"><span data-stu-id="69cbb-133">Response</span></span>

<span data-ttu-id="69cbb-134">Als dit is gelukt, retourneert deze methode 200 OK, met een lijst met blootstellingsscores per apparaatgroepgegevens in de hoofdgroep reactie.</span><span class="sxs-lookup"><span data-stu-id="69cbb-134">If successful, this method returns 200 OK, with a list of exposure score per device group data in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="69cbb-135">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="69cbb-135">Example</span></span>

### <a name="request"></a><span data-ttu-id="69cbb-136">Aanvraag</span><span class="sxs-lookup"><span data-stu-id="69cbb-136">Request</span></span>

<span data-ttu-id="69cbb-137">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="69cbb-137">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/exposureScore/ByMachineGroups
```

### <a name="response"></a><span data-ttu-id="69cbb-138">Antwoord</span><span class="sxs-lookup"><span data-stu-id="69cbb-138">Response</span></span>

<span data-ttu-id="69cbb-139">Hier is een voorbeeld van het antwoord.</span><span class="sxs-lookup"><span data-stu-id="69cbb-139">Here is an example of the response.</span></span>

```json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ExposureScore",
    "value": [
        {
            "time": "2019-12-03T09:51:28.214338Z",
            "score": 41.38041766305988,
            "rbacGroupName": "GroupOne"
        },
        {
            "time": "2019-12-03T09:51:28.2143399Z",
            "score": 37.403726933165366,
            "rbacGroupName": "GroupTwo"
        }
        ...
    ]
}
```

## <a name="related-topics"></a><span data-ttu-id="69cbb-140">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="69cbb-140">Related topics</span></span>

- [<span data-ttu-id="69cbb-141">Risicogebaseerd bedreigingsbeheer & kwetsbaarheidsbeheer</span><span class="sxs-lookup"><span data-stu-id="69cbb-141">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="69cbb-142">Threat & Vulnerability Exposure Score</span><span class="sxs-lookup"><span data-stu-id="69cbb-142">Threat & Vulnerability exposure score</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-exposure-score)
