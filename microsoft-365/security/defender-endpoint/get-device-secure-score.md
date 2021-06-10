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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: dd9def688619b6079d947cb76069aa0f77d768de
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772303"
---
# <a name="get-device-secure-score"></a><span data-ttu-id="7c454-104">Secure Score voor apparaten ophalen</span><span class="sxs-lookup"><span data-stu-id="7c454-104">Get device secure score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7c454-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="7c454-105">**Applies to:**</span></span>
- [<span data-ttu-id="7c454-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="7c454-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="7c454-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7c454-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="7c454-108">**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="7c454-108">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="7c454-109">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="7c454-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="7c454-110">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="7c454-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="7c454-111">Haalt uw [Microsoft Secure Score voor apparaten op.](tvm-microsoft-secure-score-devices.md)</span><span class="sxs-lookup"><span data-stu-id="7c454-111">Retrieves your [Microsoft Secure Score for Devices](tvm-microsoft-secure-score-devices.md).</span></span> <span data-ttu-id="7c454-112">Een hogere Microsoft Secure Score voor apparaten betekent dat uw eindpunten beter bestand zijn tegen cyberbeveiligingsaanvallen.</span><span class="sxs-lookup"><span data-stu-id="7c454-112">A higher Microsoft Secure Score for Devices means your endpoints are more resilient from cybersecurity threat attacks.</span></span> 

## <a name="permissions"></a><span data-ttu-id="7c454-113">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="7c454-113">Permissions</span></span>

<span data-ttu-id="7c454-114">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="7c454-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="7c454-115">Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="7c454-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="7c454-116">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="7c454-116">Permission type</span></span> |   <span data-ttu-id="7c454-117">Machtiging</span><span class="sxs-lookup"><span data-stu-id="7c454-117">Permission</span></span>  |   <span data-ttu-id="7c454-118">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="7c454-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="7c454-119">Toepassing</span><span class="sxs-lookup"><span data-stu-id="7c454-119">Application</span></span> |   <span data-ttu-id="7c454-120">Score.Read.Alll</span><span class="sxs-lookup"><span data-stu-id="7c454-120">Score.Read.Alll</span></span> |   <span data-ttu-id="7c454-121">'Score bedreigings- en kwetsbaarheidsbeheer lezen'</span><span class="sxs-lookup"><span data-stu-id="7c454-121">'Read Threat and Vulnerability Management score'</span></span>
<span data-ttu-id="7c454-122">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="7c454-122">Delegated (work or school account)</span></span> | <span data-ttu-id="7c454-123">Score.Read</span><span class="sxs-lookup"><span data-stu-id="7c454-123">Score.Read</span></span> | <span data-ttu-id="7c454-124">'Score bedreigings- en kwetsbaarheidsbeheer lezen'</span><span class="sxs-lookup"><span data-stu-id="7c454-124">'Read Threat and Vulnerability Management score'</span></span>

## <a name="http-request"></a><span data-ttu-id="7c454-125">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="7c454-125">HTTP request</span></span>

```
GET /api/configurationScore
```

## <a name="request-headers"></a><span data-ttu-id="7c454-126">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="7c454-126">Request headers</span></span>

<span data-ttu-id="7c454-127">Naam</span><span class="sxs-lookup"><span data-stu-id="7c454-127">Name</span></span> | <span data-ttu-id="7c454-128">Type</span><span class="sxs-lookup"><span data-stu-id="7c454-128">Type</span></span> | <span data-ttu-id="7c454-129">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="7c454-129">Description</span></span>
:---|:---|:---
<span data-ttu-id="7c454-130">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="7c454-130">Authorization</span></span> | <span data-ttu-id="7c454-131">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7c454-131">String</span></span> | <span data-ttu-id="7c454-132">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="7c454-132">Bearer {token}.</span></span> <span data-ttu-id="7c454-133">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="7c454-133">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="7c454-134">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="7c454-134">Request body</span></span>

<span data-ttu-id="7c454-135">Leeg</span><span class="sxs-lookup"><span data-stu-id="7c454-135">Empty</span></span>

## <a name="response"></a><span data-ttu-id="7c454-136">Antwoord</span><span class="sxs-lookup"><span data-stu-id="7c454-136">Response</span></span>

<span data-ttu-id="7c454-137">Als dit is gelukt, retourneert deze methode 200 OK, waarbij de veilige scoregegevens van het apparaat in de antwoord-body worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="7c454-137">If successful, this method returns 200 OK, with the device secure score data in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="7c454-138">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="7c454-138">Example</span></span>

### <a name="request"></a><span data-ttu-id="7c454-139">Aanvraag</span><span class="sxs-lookup"><span data-stu-id="7c454-139">Request</span></span>

<span data-ttu-id="7c454-140">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="7c454-140">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/configurationScore
```

### <a name="response"></a><span data-ttu-id="7c454-141">Antwoord</span><span class="sxs-lookup"><span data-stu-id="7c454-141">Response</span></span>

<span data-ttu-id="7c454-142">Hier is een voorbeeld van het antwoord.</span><span class="sxs-lookup"><span data-stu-id="7c454-142">Here is an example of the response.</span></span>

>[!NOTE]
><span data-ttu-id="7c454-143">De hier weergegeven antwoordlijst kan worden afgekapt voor beknoptheid.</span><span class="sxs-lookup"><span data-stu-id="7c454-143">The response list shown here may be truncated for brevity.</span></span> 

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ConfigurationScore/$entity",
    "time": "2019-12-03T09:15:58.1665846Z",
    "score": 340
}
```

## <a name="see-also"></a><span data-ttu-id="7c454-144">Zie ook</span><span class="sxs-lookup"><span data-stu-id="7c454-144">See also</span></span>

- [<span data-ttu-id="7c454-145">OData-query's met Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="7c454-145">OData queries with Microsoft Defender for Endpoint</span></span>](exposed-apis-odata-samples.md)
