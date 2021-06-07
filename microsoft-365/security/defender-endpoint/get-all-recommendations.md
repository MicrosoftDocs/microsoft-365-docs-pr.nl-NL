---
title: Lijst van alle aanbevelingen
description: Hiermee wordt een lijst opgehaald met alle beveiligingsaanbevelingen die van invloed zijn op de organisatie.
keywords: api's, graph api, ondersteunde api's, get, beveiligingsaanbevelingen, Microsoft Defender voor Endpoint tvm api, Threat and Vulnerability Management, Threat and Vulnerability Management api
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 0a58287a9bd48a4d19144a40674e1d3ad3bd256a
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52768924"
---
# <a name="list-all-recommendations"></a><span data-ttu-id="e6fd6-104">Lijst van alle aanbevelingen</span><span class="sxs-lookup"><span data-stu-id="e6fd6-104">List all recommendations</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e6fd6-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="e6fd6-105">**Applies to:**</span></span>
- [<span data-ttu-id="e6fd6-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="e6fd6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e6fd6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e6fd6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="e6fd6-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="e6fd6-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e6fd6-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="e6fd6-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="e6fd6-110">Hiermee wordt een lijst opgehaald met alle beveiligingsaanbevelingen die van invloed zijn op de organisatie.</span><span class="sxs-lookup"><span data-stu-id="e6fd6-110">Retrieves a list of all security recommendations affecting the organization.</span></span>

## <a name="permissions"></a><span data-ttu-id="e6fd6-111">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="e6fd6-111">Permissions</span></span>
<span data-ttu-id="e6fd6-112">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="e6fd6-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="e6fd6-113">Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="e6fd6-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="e6fd6-114">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="e6fd6-114">Permission type</span></span> |   <span data-ttu-id="e6fd6-115">Machtiging</span><span class="sxs-lookup"><span data-stu-id="e6fd6-115">Permission</span></span>  |   <span data-ttu-id="e6fd6-116">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="e6fd6-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="e6fd6-117">Toepassing</span><span class="sxs-lookup"><span data-stu-id="e6fd6-117">Application</span></span> |   <span data-ttu-id="e6fd6-118">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="e6fd6-118">SecurityRecommendation.Read.All</span></span> |   <span data-ttu-id="e6fd6-119">'Informatie over beveiligingsaanbeveling bedreigings- en kwetsbaarheidsbeheer lezen'</span><span class="sxs-lookup"><span data-stu-id="e6fd6-119">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="e6fd6-120">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="e6fd6-120">Delegated (work or school account)</span></span> | <span data-ttu-id="e6fd6-121">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="e6fd6-121">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="e6fd6-122">'Informatie over beveiligingsaanbeveling bedreigings- en kwetsbaarheidsbeheer lezen'</span><span class="sxs-lookup"><span data-stu-id="e6fd6-122">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="e6fd6-123">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="e6fd6-123">HTTP request</span></span>
```
GET /api/recommendations
```

## <a name="request-headers"></a><span data-ttu-id="e6fd6-124">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="e6fd6-124">Request headers</span></span>

<span data-ttu-id="e6fd6-125">Naam</span><span class="sxs-lookup"><span data-stu-id="e6fd6-125">Name</span></span> | <span data-ttu-id="e6fd6-126">Type</span><span class="sxs-lookup"><span data-stu-id="e6fd6-126">Type</span></span> | <span data-ttu-id="e6fd6-127">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="e6fd6-127">Description</span></span>
:---|:---|:---
<span data-ttu-id="e6fd6-128">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="e6fd6-128">Authorization</span></span> | <span data-ttu-id="e6fd6-129">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="e6fd6-129">String</span></span> | <span data-ttu-id="e6fd6-130">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="e6fd6-130">Bearer {token}.</span></span> <span data-ttu-id="e6fd6-131">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="e6fd6-131">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="e6fd6-132">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="e6fd6-132">Request body</span></span>
<span data-ttu-id="e6fd6-133">Leeg</span><span class="sxs-lookup"><span data-stu-id="e6fd6-133">Empty</span></span>

## <a name="response"></a><span data-ttu-id="e6fd6-134">Antwoord</span><span class="sxs-lookup"><span data-stu-id="e6fd6-134">Response</span></span>
<span data-ttu-id="e6fd6-135">Als dit is gelukt, retourneert deze methode 200 OK met de lijst met beveiligingsaanbevelingen in de body.</span><span class="sxs-lookup"><span data-stu-id="e6fd6-135">If successful, this method returns 200 OK with the list of security recommendations in the body.</span></span>


## <a name="example"></a><span data-ttu-id="e6fd6-136">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="e6fd6-136">Example</span></span>

<span data-ttu-id="e6fd6-137">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="e6fd6-137">**Request**</span></span>

<span data-ttu-id="e6fd6-138">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="e6fd6-138">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/recommendations
```

<span data-ttu-id="e6fd6-139">**Antwoord**</span><span class="sxs-lookup"><span data-stu-id="e6fd6-139">**Response**</span></span>

<span data-ttu-id="e6fd6-140">Hier is een voorbeeld van het antwoord.</span><span class="sxs-lookup"><span data-stu-id="e6fd6-140">Here is an example of the response.</span></span>


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
## <a name="see-also"></a><span data-ttu-id="e6fd6-141">Zie ook</span><span class="sxs-lookup"><span data-stu-id="e6fd6-141">See also</span></span>
- [<span data-ttu-id="e6fd6-142">Risicogebaseerd bedreigingsbeheer & kwetsbaarheidsbeheer</span><span class="sxs-lookup"><span data-stu-id="e6fd6-142">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="e6fd6-143">Aanbeveling & beveiligingsaanbeveling voor bedreigingen</span><span class="sxs-lookup"><span data-stu-id="e6fd6-143">Threat & Vulnerability security recommendation</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)

