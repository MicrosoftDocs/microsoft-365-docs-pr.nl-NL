---
title: Blootstellingsscore ophalen
description: Hiermee wordt de score voor de blootstelling van de organisatie opgehaald.
keywords: api's, graph api, ondersteunde api's, get, exposure score, organizational exposure score
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 071b0e7597d334fe06d5045e06a5c4d82dd65609
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845388"
---
# <a name="get-exposure-score"></a><span data-ttu-id="2c04b-104">Blootstellingsscore ophalen</span><span class="sxs-lookup"><span data-stu-id="2c04b-104">Get exposure score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2c04b-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="2c04b-105">**Applies to:**</span></span>
- [<span data-ttu-id="2c04b-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="2c04b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2c04b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2c04b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="2c04b-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="2c04b-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2c04b-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="2c04b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="2c04b-110">Hiermee wordt de score voor de blootstelling van de organisatie opgehaald.</span><span class="sxs-lookup"><span data-stu-id="2c04b-110">Retrieves the organizational exposure score.</span></span>

## <a name="permissions"></a><span data-ttu-id="2c04b-111">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="2c04b-111">Permissions</span></span>

<span data-ttu-id="2c04b-112">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="2c04b-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="2c04b-113">Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="2c04b-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="2c04b-114">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="2c04b-114">Permission type</span></span> | <span data-ttu-id="2c04b-115">Machtiging</span><span class="sxs-lookup"><span data-stu-id="2c04b-115">Permission</span></span> | <span data-ttu-id="2c04b-116">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="2c04b-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="2c04b-117">Toepassing</span><span class="sxs-lookup"><span data-stu-id="2c04b-117">Application</span></span> | <span data-ttu-id="2c04b-118">Score.Read.All</span><span class="sxs-lookup"><span data-stu-id="2c04b-118">Score.Read.All</span></span> | <span data-ttu-id="2c04b-119">'Score bedreigings- en kwetsbaarheidsbeheer lezen'</span><span class="sxs-lookup"><span data-stu-id="2c04b-119">'Read Threat and Vulnerability Management score'</span></span>
<span data-ttu-id="2c04b-120">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="2c04b-120">Delegated (work or school account)</span></span> | <span data-ttu-id="2c04b-121">Score.Read</span><span class="sxs-lookup"><span data-stu-id="2c04b-121">Score.Read</span></span> | <span data-ttu-id="2c04b-122">'Score bedreigings- en kwetsbaarheidsbeheer lezen'</span><span class="sxs-lookup"><span data-stu-id="2c04b-122">'Read Threat and Vulnerability Management score'</span></span>

## <a name="http-request"></a><span data-ttu-id="2c04b-123">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="2c04b-123">HTTP request</span></span>

```
GET /api/exposureScore
```

## <a name="request-headers"></a><span data-ttu-id="2c04b-124">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="2c04b-124">Request headers</span></span>

<span data-ttu-id="2c04b-125">Naam</span><span class="sxs-lookup"><span data-stu-id="2c04b-125">Name</span></span> | <span data-ttu-id="2c04b-126">Type</span><span class="sxs-lookup"><span data-stu-id="2c04b-126">Type</span></span> | <span data-ttu-id="2c04b-127">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="2c04b-127">Description</span></span>
:---|:---|:---
<span data-ttu-id="2c04b-128">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="2c04b-128">Authorization</span></span> | <span data-ttu-id="2c04b-129">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2c04b-129">String</span></span> | <span data-ttu-id="2c04b-130">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="2c04b-130">Bearer {token}.</span></span> <span data-ttu-id="2c04b-131">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="2c04b-131">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="2c04b-132">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="2c04b-132">Request body</span></span>

<span data-ttu-id="2c04b-133">Leeg</span><span class="sxs-lookup"><span data-stu-id="2c04b-133">Empty</span></span>

## <a name="response"></a><span data-ttu-id="2c04b-134">Antwoord</span><span class="sxs-lookup"><span data-stu-id="2c04b-134">Response</span></span>

<span data-ttu-id="2c04b-135">Als dit is gelukt, retourneert deze methode 200 OK, met de blootstellingsgegevens in de antwoord body.</span><span class="sxs-lookup"><span data-stu-id="2c04b-135">If successful, this method returns 200 OK, with the exposure data in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="2c04b-136">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="2c04b-136">Example</span></span>

### <a name="request"></a><span data-ttu-id="2c04b-137">Aanvraag</span><span class="sxs-lookup"><span data-stu-id="2c04b-137">Request</span></span>

<span data-ttu-id="2c04b-138">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="2c04b-138">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/exposureScore
```

### <a name="response"></a><span data-ttu-id="2c04b-139">Antwoord</span><span class="sxs-lookup"><span data-stu-id="2c04b-139">Response</span></span>

<span data-ttu-id="2c04b-140">Hier is een voorbeeld van het antwoord.</span><span class="sxs-lookup"><span data-stu-id="2c04b-140">Here is an example of the response.</span></span>

>[!NOTE]
><span data-ttu-id="2c04b-141">De hier weergegeven antwoordlijst kan worden afgekapt voor beknoptheid.</span><span class="sxs-lookup"><span data-stu-id="2c04b-141">The response list shown here may be truncated for brevity.</span></span> 

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ExposureScore/$entity",
    "time": "2019-12-03T07:23:53.280499Z",
    "score": 33.491554051195706
}

```

## <a name="see-also"></a><span data-ttu-id="2c04b-142">Zie ook</span><span class="sxs-lookup"><span data-stu-id="2c04b-142">See also</span></span>

- [<span data-ttu-id="2c04b-143">Risicogebaseerd bedreigingsbeheer & kwetsbaarheidsbeheer</span><span class="sxs-lookup"><span data-stu-id="2c04b-143">Risk-based Threat & Vulnerability Management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="2c04b-144">Threat & Vulnerability Exposure Score</span><span class="sxs-lookup"><span data-stu-id="2c04b-144">Threat & Vulnerability exposure score</span></span>](/microsoft-365/security/defender-endpoint/tvm-exposure-score)
