---
title: Beveiligingsaanbevelingen ophalen
description: Hiermee wordt een verzameling beveiligingsaanbevelingen opgehaald die betrekking hebben op een bepaalde apparaat-id.
keywords: api's, graph api, ondersteunde api's, get, list, file, information, security recommendation per device, threat & vulnerability management api, Microsoft Defender for Endpoint tvm api
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
ms.openlocfilehash: 44f64334d08d8d0d6a5ed1e8e06baa2880859ad2
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771127"
---
# <a name="get-security-recommendations"></a><span data-ttu-id="4dc02-104">Beveiligingsaanbevelingen ophalen</span><span class="sxs-lookup"><span data-stu-id="4dc02-104">Get security recommendations</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4dc02-105">**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="4dc02-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="4dc02-106">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="4dc02-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="4dc02-107">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="4dc02-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="4dc02-108">Hiermee wordt een verzameling beveiligingsaanbevelingen opgehaald die betrekking hebben op een bepaalde apparaat-id.</span><span class="sxs-lookup"><span data-stu-id="4dc02-108">Retrieves a collection of security recommendations related to a given device ID.</span></span>

## <a name="permissions"></a><span data-ttu-id="4dc02-109">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="4dc02-109">Permissions</span></span>
<span data-ttu-id="4dc02-110">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="4dc02-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="4dc02-111">Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="4dc02-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="4dc02-112">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="4dc02-112">Permission type</span></span> |   <span data-ttu-id="4dc02-113">Machtiging</span><span class="sxs-lookup"><span data-stu-id="4dc02-113">Permission</span></span>  |   <span data-ttu-id="4dc02-114">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="4dc02-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="4dc02-115">Toepassing</span><span class="sxs-lookup"><span data-stu-id="4dc02-115">Application</span></span> | <span data-ttu-id="4dc02-116">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="4dc02-116">SecurityRecommendation.Read.All</span></span> | <span data-ttu-id="4dc02-117">'Informatie over beveiligingsaanbeveling bedreigings- en kwetsbaarheidsbeheer lezen'</span><span class="sxs-lookup"><span data-stu-id="4dc02-117">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="4dc02-118">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="4dc02-118">Delegated (work or school account)</span></span> | <span data-ttu-id="4dc02-119">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="4dc02-119">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="4dc02-120">'Informatie over beveiligingsaanbeveling bedreigings- en kwetsbaarheidsbeheer lezen'</span><span class="sxs-lookup"><span data-stu-id="4dc02-120">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="4dc02-121">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="4dc02-121">HTTP request</span></span>
```
GET /api/machines/{machineId}/recommendations
```

## <a name="request-headers"></a><span data-ttu-id="4dc02-122">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="4dc02-122">Request headers</span></span>

<span data-ttu-id="4dc02-123">Naam</span><span class="sxs-lookup"><span data-stu-id="4dc02-123">Name</span></span> | <span data-ttu-id="4dc02-124">Type</span><span class="sxs-lookup"><span data-stu-id="4dc02-124">Type</span></span> | <span data-ttu-id="4dc02-125">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="4dc02-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="4dc02-126">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="4dc02-126">Authorization</span></span> | <span data-ttu-id="4dc02-127">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4dc02-127">String</span></span> | <span data-ttu-id="4dc02-128">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="4dc02-128">Bearer {token}.</span></span> <span data-ttu-id="4dc02-129">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="4dc02-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="4dc02-130">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="4dc02-130">Request body</span></span>
<span data-ttu-id="4dc02-131">Leeg</span><span class="sxs-lookup"><span data-stu-id="4dc02-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="4dc02-132">Antwoord</span><span class="sxs-lookup"><span data-stu-id="4dc02-132">Response</span></span>
<span data-ttu-id="4dc02-133">Als dit is gelukt, retourneert deze methode 200 OK met de beveiligingsaanbevelingen in de body.</span><span class="sxs-lookup"><span data-stu-id="4dc02-133">If successful, this method returns 200 OK with the security recommendations in the body.</span></span>


## <a name="example"></a><span data-ttu-id="4dc02-134">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="4dc02-134">Example</span></span>

<span data-ttu-id="4dc02-135">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="4dc02-135">**Request**</span></span>

<span data-ttu-id="4dc02-136">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="4dc02-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/machines/ac233fa6208e1579620bf44207c4006ed7cc4501/recommendations
```

<span data-ttu-id="4dc02-137">**Antwoord**</span><span class="sxs-lookup"><span data-stu-id="4dc02-137">**Response**</span></span>

<span data-ttu-id="4dc02-138">Hier is een voorbeeld van het antwoord.</span><span class="sxs-lookup"><span data-stu-id="4dc02-138">Here is an example of the response.</span></span>


```
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Recommendations",
    "value": [
        {
            "id": "va-_-git-scm-_-git",
            "productName": "git",
            "recommendationName": "Update Git to version 2.24.1.2",
            "weaknesses": 3,
            "vendor": "git-scm",
            "recommendedVersion": "2.24.1.2",
            "recommendationCategory": "Application",
            "subCategory": "",
            "severityScore": 0,
            "publicExploit": false,
            "activeAlert": false,
            "associatedThreats": [],
            "remediationType": "Update",
            "status": "Active",
            "configScoreImpact": 0,
            "exposureImpact": 0,
            "totalMachineCount": 0,
            "exposedMachinesCount": 1,
            "nonProductivityImpactedAssets": 0,
            "relatedComponent": "Git"
        },
…
}
```

## <a name="related-topics"></a><span data-ttu-id="4dc02-139">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="4dc02-139">Related topics</span></span>
- [<span data-ttu-id="4dc02-140">Risicogebaseerd bedreigingsbeheer & kwetsbaarheidsbeheer</span><span class="sxs-lookup"><span data-stu-id="4dc02-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="4dc02-141">Aanbeveling & beveiligingsaanbeveling voor bedreigingen</span><span class="sxs-lookup"><span data-stu-id="4dc02-141">Threat & Vulnerability security recommendation</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)
