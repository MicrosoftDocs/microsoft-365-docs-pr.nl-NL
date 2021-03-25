---
title: Score voor blootstelling krijgen
description: Hiermee wordt de score voor de blootstelling van de organisatie opgehaald.
keywords: api's, graph api, ondersteunde api's, get, exposure score, organizational exposure score
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: levinec
ms.author: ellevin
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e7037e49a7f750597af15cfb16e1552aeb98859a
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166568"
---
# <a name="get-exposure-score"></a><span data-ttu-id="cc042-104">Score voor blootstelling krijgen</span><span class="sxs-lookup"><span data-stu-id="cc042-104">Get exposure score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="cc042-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="cc042-105">**Applies to:**</span></span>
- [<span data-ttu-id="cc042-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="cc042-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="cc042-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cc042-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="cc042-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="cc042-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="cc042-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="cc042-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="cc042-110">Hiermee wordt de score voor de blootstelling van de organisatie opgehaald.</span><span class="sxs-lookup"><span data-stu-id="cc042-110">Retrieves the organizational exposure score.</span></span>

## <a name="permissions"></a><span data-ttu-id="cc042-111">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="cc042-111">Permissions</span></span>

<span data-ttu-id="cc042-112">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="cc042-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="cc042-113">Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="cc042-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="cc042-114">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="cc042-114">Permission type</span></span> | <span data-ttu-id="cc042-115">Machtiging</span><span class="sxs-lookup"><span data-stu-id="cc042-115">Permission</span></span> | <span data-ttu-id="cc042-116">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="cc042-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="cc042-117">Toepassing</span><span class="sxs-lookup"><span data-stu-id="cc042-117">Application</span></span> | <span data-ttu-id="cc042-118">Score.Read.All</span><span class="sxs-lookup"><span data-stu-id="cc042-118">Score.Read.All</span></span> | <span data-ttu-id="cc042-119">'Score bedreigings- en kwetsbaarheidsbeheer lezen'</span><span class="sxs-lookup"><span data-stu-id="cc042-119">'Read Threat and Vulnerability Management score'</span></span>
<span data-ttu-id="cc042-120">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="cc042-120">Delegated (work or school account)</span></span> | <span data-ttu-id="cc042-121">Score.Read</span><span class="sxs-lookup"><span data-stu-id="cc042-121">Score.Read</span></span> | <span data-ttu-id="cc042-122">'Score bedreigings- en kwetsbaarheidsbeheer lezen'</span><span class="sxs-lookup"><span data-stu-id="cc042-122">'Read Threat and Vulnerability Management score'</span></span>

## <a name="http-request"></a><span data-ttu-id="cc042-123">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="cc042-123">HTTP request</span></span>

```
GET /api/exposureScore
```

## <a name="request-headers"></a><span data-ttu-id="cc042-124">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="cc042-124">Request headers</span></span>

<span data-ttu-id="cc042-125">Naam</span><span class="sxs-lookup"><span data-stu-id="cc042-125">Name</span></span> | <span data-ttu-id="cc042-126">Type</span><span class="sxs-lookup"><span data-stu-id="cc042-126">Type</span></span> | <span data-ttu-id="cc042-127">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="cc042-127">Description</span></span>
:---|:---|:---
<span data-ttu-id="cc042-128">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="cc042-128">Authorization</span></span> | <span data-ttu-id="cc042-129">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="cc042-129">String</span></span> | <span data-ttu-id="cc042-130">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="cc042-130">Bearer {token}.</span></span> <span data-ttu-id="cc042-131">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="cc042-131">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="cc042-132">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="cc042-132">Request body</span></span>

<span data-ttu-id="cc042-133">Leeg</span><span class="sxs-lookup"><span data-stu-id="cc042-133">Empty</span></span>

## <a name="response"></a><span data-ttu-id="cc042-134">Antwoord</span><span class="sxs-lookup"><span data-stu-id="cc042-134">Response</span></span>

<span data-ttu-id="cc042-135">Als dit is gelukt, retourneert deze methode 200 OK, met de blootstellingsgegevens in de antwoord body.</span><span class="sxs-lookup"><span data-stu-id="cc042-135">If successful, this method returns 200 OK, with the exposure data in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="cc042-136">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="cc042-136">Example</span></span>

### <a name="request"></a><span data-ttu-id="cc042-137">Aanvraag</span><span class="sxs-lookup"><span data-stu-id="cc042-137">Request</span></span>

<span data-ttu-id="cc042-138">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="cc042-138">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/exposureScore
```

### <a name="response"></a><span data-ttu-id="cc042-139">Antwoord</span><span class="sxs-lookup"><span data-stu-id="cc042-139">Response</span></span>

<span data-ttu-id="cc042-140">Hier is een voorbeeld van het antwoord.</span><span class="sxs-lookup"><span data-stu-id="cc042-140">Here is an example of the response.</span></span>

>[!NOTE]
><span data-ttu-id="cc042-141">De hier weergegeven antwoordlijst kan worden afgekapt voor beknoptheid.</span><span class="sxs-lookup"><span data-stu-id="cc042-141">The response list shown here may be truncated for brevity.</span></span> 

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ExposureScore/$entity",
    "time": "2019-12-03T07:23:53.280499Z",
    "score": 33.491554051195706
}

```

## <a name="see-also"></a><span data-ttu-id="cc042-142">Zie ook</span><span class="sxs-lookup"><span data-stu-id="cc042-142">See also</span></span>

- [<span data-ttu-id="cc042-143">Risicogebaseerd bedreigingsbeheer & kwetsbaarheidsbeheer</span><span class="sxs-lookup"><span data-stu-id="cc042-143">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="cc042-144">Threat & Vulnerability Exposure Score</span><span class="sxs-lookup"><span data-stu-id="cc042-144">Threat & Vulnerability exposure score</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-exposure-score)
