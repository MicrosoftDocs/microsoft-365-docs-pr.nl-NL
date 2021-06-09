---
title: Aanbeveling per id krijgen
description: Hiermee wordt een beveiligingsaanbeveling opgehaald op de id.
keywords: api's, graph api, ondersteunde api's, get, beveiligingsaanbeveling, beveiligingsaanbeveling per id, Threat and Vulnerability Management, Threat and Vulnerability Management api
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 66eb9c838e351a75ff68f40e9179cfeeb9bf9d4e
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845184"
---
# <a name="get-recommendation-by-id"></a><span data-ttu-id="30249-104">Aanbevelingen per id ophalen</span><span class="sxs-lookup"><span data-stu-id="30249-104">Get recommendation by ID</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="30249-105">**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="30249-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="30249-106">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="30249-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="30249-107">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="30249-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="30249-108">Hiermee wordt een beveiligingsaanbeveling opgehaald op de id.</span><span class="sxs-lookup"><span data-stu-id="30249-108">Retrieves a security recommendation by its ID.</span></span>

## <a name="permissions"></a><span data-ttu-id="30249-109">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="30249-109">Permissions</span></span>
<span data-ttu-id="30249-110">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="30249-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="30249-111">Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="30249-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="30249-112">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="30249-112">Permission type</span></span> |   <span data-ttu-id="30249-113">Machtiging</span><span class="sxs-lookup"><span data-stu-id="30249-113">Permission</span></span>  |   <span data-ttu-id="30249-114">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="30249-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="30249-115">Toepassing</span><span class="sxs-lookup"><span data-stu-id="30249-115">Application</span></span> |   <span data-ttu-id="30249-116">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="30249-116">SecurityRecommendation.Read.All</span></span> |   <span data-ttu-id="30249-117">'Informatie over beveiligingsaanbeveling bedreigings- en kwetsbaarheidsbeheer lezen'</span><span class="sxs-lookup"><span data-stu-id="30249-117">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="30249-118">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="30249-118">Delegated (work or school account)</span></span> | <span data-ttu-id="30249-119">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="30249-119">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="30249-120">'Informatie over beveiligingsaanbeveling bedreigings- en kwetsbaarheidsbeheer lezen'</span><span class="sxs-lookup"><span data-stu-id="30249-120">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="30249-121">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="30249-121">HTTP request</span></span>
```
GET /api/recommendations/{id}
```

## <a name="request-headers"></a><span data-ttu-id="30249-122">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="30249-122">Request headers</span></span>

<span data-ttu-id="30249-123">Naam</span><span class="sxs-lookup"><span data-stu-id="30249-123">Name</span></span> | <span data-ttu-id="30249-124">Type</span><span class="sxs-lookup"><span data-stu-id="30249-124">Type</span></span> | <span data-ttu-id="30249-125">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="30249-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="30249-126">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="30249-126">Authorization</span></span> | <span data-ttu-id="30249-127">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="30249-127">String</span></span> | <span data-ttu-id="30249-128">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="30249-128">Bearer {token}.</span></span> <span data-ttu-id="30249-129">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="30249-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="30249-130">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="30249-130">Request body</span></span>
<span data-ttu-id="30249-131">Leeg</span><span class="sxs-lookup"><span data-stu-id="30249-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="30249-132">Antwoord</span><span class="sxs-lookup"><span data-stu-id="30249-132">Response</span></span>
<span data-ttu-id="30249-133">Als dit is gelukt, retourneert deze methode 200 OK met de beveiligingsaanbevelingen in de body.</span><span class="sxs-lookup"><span data-stu-id="30249-133">If successful, this method returns 200 OK with the security recommendations in the body.</span></span>


## <a name="example"></a><span data-ttu-id="30249-134">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="30249-134">Example</span></span>

<span data-ttu-id="30249-135">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="30249-135">**Request**</span></span>

<span data-ttu-id="30249-136">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="30249-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/recommendations/va-_-google-_-chrome
```

<span data-ttu-id="30249-137">**Antwoord**</span><span class="sxs-lookup"><span data-stu-id="30249-137">**Response**</span></span>

<span data-ttu-id="30249-138">Hier is een voorbeeld van het antwoord.</span><span class="sxs-lookup"><span data-stu-id="30249-138">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Recommendations/$entity",
    "id": "va-_-google-_-chrome",
    "productName": "chrome",
    "recommendationName": "Update Chrome",
    "weaknesses": 38,
    "vendor": "google",
    "recommendedVersion": "",
    "recommendationCategory": "Application",
    "subCategory": "",
    "severityScore": 0,
    "publicExploit": false,
    "activeAlert": false,
    "associatedThreats": [],
    "remediationType": "Update",
    "status": "Active",
    "configScoreImpact": 0,
    "exposureImpact": 3.9441860465116285,
    "totalMachineCount": 6,
    "exposedMachinesCount": 5,
    "nonProductivityImpactedAssets": 0,
    "relatedComponent": "Chrome"
}
```

## <a name="related-topics"></a><span data-ttu-id="30249-139">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="30249-139">Related topics</span></span>
- [<span data-ttu-id="30249-140">Risicogebaseerd bedreigingsbeheer & kwetsbaarheidsbeheer</span><span class="sxs-lookup"><span data-stu-id="30249-140">Risk-based Threat & Vulnerability Management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="30249-141">Aanbeveling & beveiligingsaanbeveling voor bedreigingen</span><span class="sxs-lookup"><span data-stu-id="30249-141">Threat & Vulnerability security recommendation</span></span>](/microsoft-365/security/defender-endpoint/tvm-security-recommendation)
