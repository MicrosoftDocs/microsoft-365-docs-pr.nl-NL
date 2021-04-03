---
title: Secure Score voor apparaten ophalen
description: Hiermee wordt de beveiligde score van het organisatieapparaat opgehaald.
keywords: api's, graph api, ondersteunde api's, get, waarschuwingen, recent
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
ms.technology: mde
ms.openlocfilehash: db4682d0d2fccd7504eb46d9099a9783408cfb73
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570934"
---
# <a name="get-device-secure-score"></a><span data-ttu-id="5f6e1-104">Secure Score voor apparaten ophalen</span><span class="sxs-lookup"><span data-stu-id="5f6e1-104">Get device secure score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5f6e1-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="5f6e1-105">**Applies to:**</span></span>
- [<span data-ttu-id="5f6e1-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="5f6e1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5f6e1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5f6e1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="5f6e1-108">**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="5f6e1-108">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="5f6e1-109">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="5f6e1-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5f6e1-110">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="5f6e1-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="5f6e1-111">Haalt uw [Microsoft Secure Score voor apparaten op.](tvm-microsoft-secure-score-devices.md)</span><span class="sxs-lookup"><span data-stu-id="5f6e1-111">Retrieves your [Microsoft Secure Score for Devices](tvm-microsoft-secure-score-devices.md).</span></span> <span data-ttu-id="5f6e1-112">Een hogere Microsoft Secure Score voor apparaten betekent dat uw eindpunten beter bestand zijn tegen cyberbeveiligingsaanvallen.</span><span class="sxs-lookup"><span data-stu-id="5f6e1-112">A higher Microsoft Secure Score for Devices means your endpoints are more resilient from cybersecurity threat attacks.</span></span> 

## <a name="permissions"></a><span data-ttu-id="5f6e1-113">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="5f6e1-113">Permissions</span></span>

<span data-ttu-id="5f6e1-114">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="5f6e1-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="5f6e1-115">Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="5f6e1-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="5f6e1-116">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="5f6e1-116">Permission type</span></span> |   <span data-ttu-id="5f6e1-117">Machtiging</span><span class="sxs-lookup"><span data-stu-id="5f6e1-117">Permission</span></span>  |   <span data-ttu-id="5f6e1-118">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="5f6e1-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="5f6e1-119">Toepassing</span><span class="sxs-lookup"><span data-stu-id="5f6e1-119">Application</span></span> |   <span data-ttu-id="5f6e1-120">Score.Read.Alll</span><span class="sxs-lookup"><span data-stu-id="5f6e1-120">Score.Read.Alll</span></span> |   <span data-ttu-id="5f6e1-121">'Score bedreigings- en kwetsbaarheidsbeheer lezen'</span><span class="sxs-lookup"><span data-stu-id="5f6e1-121">'Read Threat and Vulnerability Management score'</span></span>
<span data-ttu-id="5f6e1-122">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="5f6e1-122">Delegated (work or school account)</span></span> | <span data-ttu-id="5f6e1-123">Score.Read</span><span class="sxs-lookup"><span data-stu-id="5f6e1-123">Score.Read</span></span> | <span data-ttu-id="5f6e1-124">'Score bedreigings- en kwetsbaarheidsbeheer lezen'</span><span class="sxs-lookup"><span data-stu-id="5f6e1-124">'Read Threat and Vulnerability Management score'</span></span>

## <a name="http-request"></a><span data-ttu-id="5f6e1-125">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="5f6e1-125">HTTP request</span></span>

```
GET /api/configurationScore
```

## <a name="request-headers"></a><span data-ttu-id="5f6e1-126">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="5f6e1-126">Request headers</span></span>

<span data-ttu-id="5f6e1-127">Naam</span><span class="sxs-lookup"><span data-stu-id="5f6e1-127">Name</span></span> | <span data-ttu-id="5f6e1-128">Type</span><span class="sxs-lookup"><span data-stu-id="5f6e1-128">Type</span></span> | <span data-ttu-id="5f6e1-129">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="5f6e1-129">Description</span></span>
:---|:---|:---
<span data-ttu-id="5f6e1-130">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="5f6e1-130">Authorization</span></span> | <span data-ttu-id="5f6e1-131">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="5f6e1-131">String</span></span> | <span data-ttu-id="5f6e1-132">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="5f6e1-132">Bearer {token}.</span></span> <span data-ttu-id="5f6e1-133">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="5f6e1-133">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="5f6e1-134">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="5f6e1-134">Request body</span></span>

<span data-ttu-id="5f6e1-135">Leeg</span><span class="sxs-lookup"><span data-stu-id="5f6e1-135">Empty</span></span>

## <a name="response"></a><span data-ttu-id="5f6e1-136">Antwoord</span><span class="sxs-lookup"><span data-stu-id="5f6e1-136">Response</span></span>

<span data-ttu-id="5f6e1-137">Als dit is gelukt, retourneert deze methode 200 OK, waarbij de veilige scoregegevens van het apparaat in de antwoord-body worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="5f6e1-137">If successful, this method returns 200 OK, with the device secure score data in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="5f6e1-138">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="5f6e1-138">Example</span></span>

### <a name="request"></a><span data-ttu-id="5f6e1-139">Aanvraag</span><span class="sxs-lookup"><span data-stu-id="5f6e1-139">Request</span></span>

<span data-ttu-id="5f6e1-140">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="5f6e1-140">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/configurationScore
```

### <a name="response"></a><span data-ttu-id="5f6e1-141">Antwoord</span><span class="sxs-lookup"><span data-stu-id="5f6e1-141">Response</span></span>

<span data-ttu-id="5f6e1-142">Hier is een voorbeeld van het antwoord.</span><span class="sxs-lookup"><span data-stu-id="5f6e1-142">Here is an example of the response.</span></span>

>[!NOTE]
><span data-ttu-id="5f6e1-143">De hier weergegeven antwoordlijst kan worden afgekapt voor beknoptheid.</span><span class="sxs-lookup"><span data-stu-id="5f6e1-143">The response list shown here may be truncated for brevity.</span></span> 

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ConfigurationScore/$entity",
    "time": "2019-12-03T09:15:58.1665846Z",
    "score": 340
}
```

## <a name="see-also"></a><span data-ttu-id="5f6e1-144">Zie ook</span><span class="sxs-lookup"><span data-stu-id="5f6e1-144">See also</span></span>

- [<span data-ttu-id="5f6e1-145">OData-query's met Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="5f6e1-145">OData queries with Microsoft Defender for Endpoint</span></span>](exposed-apis-odata-samples.md)
