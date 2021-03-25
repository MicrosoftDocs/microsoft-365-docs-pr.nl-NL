---
title: Alle aanbevelingen op een lijst zetten
description: Hiermee wordt een lijst opgehaald met alle beveiligingsaanbevelingen die van invloed zijn op de organisatie.
keywords: api's, graph api, ondersteunde api's, get, beveiligingsaanbevelingen, mdatp tvm-api, bedreigings- en kwetsbaarheidsbeheer, api voor bedreigings- en kwetsbaarheidsbeheer
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: mde
ms.openlocfilehash: 5fb68572ee1b154be1db5eb5a092013a1c1a257e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166595"
---
# <a name="list-all-recommendations"></a><span data-ttu-id="cb9a7-104">Alle aanbevelingen op een lijst zetten</span><span class="sxs-lookup"><span data-stu-id="cb9a7-104">List all recommendations</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="cb9a7-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="cb9a7-105">**Applies to:**</span></span>
- [<span data-ttu-id="cb9a7-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="cb9a7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="cb9a7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cb9a7-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="cb9a7-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="cb9a7-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="cb9a7-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="cb9a7-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="cb9a7-110">Hiermee wordt een lijst opgehaald met alle beveiligingsaanbevelingen die van invloed zijn op de organisatie.</span><span class="sxs-lookup"><span data-stu-id="cb9a7-110">Retrieves a list of all security recommendations affecting the organization.</span></span>

## <a name="permissions"></a><span data-ttu-id="cb9a7-111">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="cb9a7-111">Permissions</span></span>
<span data-ttu-id="cb9a7-112">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="cb9a7-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="cb9a7-113">Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="cb9a7-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="cb9a7-114">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="cb9a7-114">Permission type</span></span> |   <span data-ttu-id="cb9a7-115">Machtiging</span><span class="sxs-lookup"><span data-stu-id="cb9a7-115">Permission</span></span>  |   <span data-ttu-id="cb9a7-116">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="cb9a7-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="cb9a7-117">Toepassing</span><span class="sxs-lookup"><span data-stu-id="cb9a7-117">Application</span></span> |   <span data-ttu-id="cb9a7-118">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="cb9a7-118">SecurityRecommendation.Read.All</span></span> |   <span data-ttu-id="cb9a7-119">'Informatie over beveiligingsaanbeveling bedreigings- en kwetsbaarheidsbeheer lezen'</span><span class="sxs-lookup"><span data-stu-id="cb9a7-119">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="cb9a7-120">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="cb9a7-120">Delegated (work or school account)</span></span> | <span data-ttu-id="cb9a7-121">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="cb9a7-121">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="cb9a7-122">'Informatie over beveiligingsaanbeveling bedreigings- en kwetsbaarheidsbeheer lezen'</span><span class="sxs-lookup"><span data-stu-id="cb9a7-122">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="cb9a7-123">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="cb9a7-123">HTTP request</span></span>
```
GET /api/recommendations
```

## <a name="request-headers"></a><span data-ttu-id="cb9a7-124">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="cb9a7-124">Request headers</span></span>

<span data-ttu-id="cb9a7-125">Naam</span><span class="sxs-lookup"><span data-stu-id="cb9a7-125">Name</span></span> | <span data-ttu-id="cb9a7-126">Type</span><span class="sxs-lookup"><span data-stu-id="cb9a7-126">Type</span></span> | <span data-ttu-id="cb9a7-127">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="cb9a7-127">Description</span></span>
:---|:---|:---
<span data-ttu-id="cb9a7-128">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="cb9a7-128">Authorization</span></span> | <span data-ttu-id="cb9a7-129">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="cb9a7-129">String</span></span> | <span data-ttu-id="cb9a7-130">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="cb9a7-130">Bearer {token}.</span></span> <span data-ttu-id="cb9a7-131">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="cb9a7-131">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="cb9a7-132">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="cb9a7-132">Request body</span></span>
<span data-ttu-id="cb9a7-133">Leeg</span><span class="sxs-lookup"><span data-stu-id="cb9a7-133">Empty</span></span>

## <a name="response"></a><span data-ttu-id="cb9a7-134">Antwoord</span><span class="sxs-lookup"><span data-stu-id="cb9a7-134">Response</span></span>
<span data-ttu-id="cb9a7-135">Als dit is gelukt, retourneert deze methode 200 OK met de lijst met beveiligingsaanbevelingen in de body.</span><span class="sxs-lookup"><span data-stu-id="cb9a7-135">If successful, this method returns 200 OK with the list of security recommendations in the body.</span></span>


## <a name="example"></a><span data-ttu-id="cb9a7-136">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="cb9a7-136">Example</span></span>

<span data-ttu-id="cb9a7-137">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="cb9a7-137">**Request**</span></span>

<span data-ttu-id="cb9a7-138">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="cb9a7-138">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/recommendations
```

<span data-ttu-id="cb9a7-139">**Antwoord**</span><span class="sxs-lookup"><span data-stu-id="cb9a7-139">**Response**</span></span>

<span data-ttu-id="cb9a7-140">Hier is een voorbeeld van het antwoord.</span><span class="sxs-lookup"><span data-stu-id="cb9a7-140">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Recommendations",
    "value": [
        {
            "id": "va-_-microsoft-_-windows_10",
            "productName": "windows_10",
            "recommendationName": "Update Windows 10",
            "weaknesses": 397,
            "vendor": "microsoft",
            "recommendedVersion": "",
            "recommendationCategory": "Application",
            "subCategory": "",
            "severityScore": 0,
            "publicExploit": true,
            "activeAlert": false,
            "associatedThreats": [
                "3098b8ef-23b1-46b3-aed4-499e1928f9ed",
                "40c189d5-0330-4654-a816-e48c2b7f9c4b",
                "4b0c9702-9b6c-4ca2-9d02-1556869f56f8",
                "e8fc2121-3cf3-4dd2-9ea0-87d7e1d2b29d",
                "94b6e94b-0c1d-4817-ac06-c3b8639be3ab"
            ],
            "remediationType": "Update",
            "status": "Active",
            "configScoreImpact": 0,
            "exposureImpact": 7.674418604651163,
            "totalMachineCount": 37,
            "exposedMachinesCount": 7,
            "nonProductivityImpactedAssets": 0,
            "relatedComponent": "Windows 10"
        }
        ...
     ]
}
```
## <a name="see-also"></a><span data-ttu-id="cb9a7-141">Zie ook</span><span class="sxs-lookup"><span data-stu-id="cb9a7-141">See also</span></span>
- [<span data-ttu-id="cb9a7-142">Risicogebaseerd bedreigingsbeheer & kwetsbaarheidsbeheer</span><span class="sxs-lookup"><span data-stu-id="cb9a7-142">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="cb9a7-143">Aanbeveling & beveiligingsaanbeveling voor bedreigingen</span><span class="sxs-lookup"><span data-stu-id="cb9a7-143">Threat & Vulnerability security recommendation</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)

