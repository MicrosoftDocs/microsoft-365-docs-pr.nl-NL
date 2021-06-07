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
ms.openlocfilehash: 4ec4758453f43cb211143918ed5fe8fe83e91c3f
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771799"
---
# <a name="get-recommendation-by-id"></a><span data-ttu-id="9588e-104">Aanbevelingen per id ophalen</span><span class="sxs-lookup"><span data-stu-id="9588e-104">Get recommendation by ID</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9588e-105">**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="9588e-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="9588e-106">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="9588e-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="9588e-107">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="9588e-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="9588e-108">Hiermee wordt een beveiligingsaanbeveling opgehaald op de id.</span><span class="sxs-lookup"><span data-stu-id="9588e-108">Retrieves a security recommendation by its ID.</span></span>

## <a name="permissions"></a><span data-ttu-id="9588e-109">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="9588e-109">Permissions</span></span>
<span data-ttu-id="9588e-110">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="9588e-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="9588e-111">Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="9588e-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="9588e-112">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="9588e-112">Permission type</span></span> |   <span data-ttu-id="9588e-113">Machtiging</span><span class="sxs-lookup"><span data-stu-id="9588e-113">Permission</span></span>  |   <span data-ttu-id="9588e-114">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="9588e-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="9588e-115">Toepassing</span><span class="sxs-lookup"><span data-stu-id="9588e-115">Application</span></span> |   <span data-ttu-id="9588e-116">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="9588e-116">SecurityRecommendation.Read.All</span></span> |   <span data-ttu-id="9588e-117">'Informatie over beveiligingsaanbeveling bedreigings- en kwetsbaarheidsbeheer lezen'</span><span class="sxs-lookup"><span data-stu-id="9588e-117">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="9588e-118">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="9588e-118">Delegated (work or school account)</span></span> | <span data-ttu-id="9588e-119">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="9588e-119">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="9588e-120">'Informatie over beveiligingsaanbeveling bedreigings- en kwetsbaarheidsbeheer lezen'</span><span class="sxs-lookup"><span data-stu-id="9588e-120">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="9588e-121">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="9588e-121">HTTP request</span></span>
```
GET /api/recommendations/{id}
```

## <a name="request-headers"></a><span data-ttu-id="9588e-122">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="9588e-122">Request headers</span></span>

<span data-ttu-id="9588e-123">Naam</span><span class="sxs-lookup"><span data-stu-id="9588e-123">Name</span></span> | <span data-ttu-id="9588e-124">Type</span><span class="sxs-lookup"><span data-stu-id="9588e-124">Type</span></span> | <span data-ttu-id="9588e-125">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="9588e-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="9588e-126">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="9588e-126">Authorization</span></span> | <span data-ttu-id="9588e-127">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="9588e-127">String</span></span> | <span data-ttu-id="9588e-128">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="9588e-128">Bearer {token}.</span></span> <span data-ttu-id="9588e-129">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="9588e-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="9588e-130">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="9588e-130">Request body</span></span>
<span data-ttu-id="9588e-131">Leeg</span><span class="sxs-lookup"><span data-stu-id="9588e-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="9588e-132">Antwoord</span><span class="sxs-lookup"><span data-stu-id="9588e-132">Response</span></span>
<span data-ttu-id="9588e-133">Als dit is gelukt, retourneert deze methode 200 OK met de beveiligingsaanbevelingen in de body.</span><span class="sxs-lookup"><span data-stu-id="9588e-133">If successful, this method returns 200 OK with the security recommendations in the body.</span></span>


## <a name="example"></a><span data-ttu-id="9588e-134">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="9588e-134">Example</span></span>

<span data-ttu-id="9588e-135">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="9588e-135">**Request**</span></span>

<span data-ttu-id="9588e-136">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="9588e-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/recommendations/va-_-google-_-chrome
```

<span data-ttu-id="9588e-137">**Antwoord**</span><span class="sxs-lookup"><span data-stu-id="9588e-137">**Response**</span></span>

<span data-ttu-id="9588e-138">Hier is een voorbeeld van het antwoord.</span><span class="sxs-lookup"><span data-stu-id="9588e-138">Here is an example of the response.</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="9588e-139">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="9588e-139">Related topics</span></span>
- [<span data-ttu-id="9588e-140">Risicogebaseerd bedreigingsbeheer & kwetsbaarheidsbeheer</span><span class="sxs-lookup"><span data-stu-id="9588e-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="9588e-141">Aanbeveling & beveiligingsaanbeveling voor bedreigingen</span><span class="sxs-lookup"><span data-stu-id="9588e-141">Threat & Vulnerability security recommendation</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)
