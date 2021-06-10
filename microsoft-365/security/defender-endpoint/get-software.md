---
title: Lijst van software
description: Hiermee wordt een lijst met softwarevoorraad opgehaald
keywords: api's, graph api, ondersteunde api's, get, list, file, information, software inventory, threat & vulnerability management api, Microsoft Defender for Endpoint tvm api
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
ms.openlocfilehash: 2b7375f04094cdb56b0801adf2c1c0b7a8ab3098
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844272"
---
# <a name="list-software-inventory-api"></a><span data-ttu-id="2d446-104">List software inventory API</span><span class="sxs-lookup"><span data-stu-id="2d446-104">List software inventory API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2d446-105">**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="2d446-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="2d446-106">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="2d446-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2d446-107">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="2d446-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="2d446-108">Hiermee wordt de inventaris van de organisatiesoftware opgehaald.</span><span class="sxs-lookup"><span data-stu-id="2d446-108">Retrieves the organization software inventory.</span></span>

## <a name="permissions"></a><span data-ttu-id="2d446-109">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="2d446-109">Permissions</span></span>
<span data-ttu-id="2d446-110">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="2d446-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="2d446-111">Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="2d446-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="2d446-112">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="2d446-112">Permission type</span></span> |   <span data-ttu-id="2d446-113">Machtiging</span><span class="sxs-lookup"><span data-stu-id="2d446-113">Permission</span></span>  |   <span data-ttu-id="2d446-114">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="2d446-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="2d446-115">Toepassing</span><span class="sxs-lookup"><span data-stu-id="2d446-115">Application</span></span> |<span data-ttu-id="2d446-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="2d446-116">Software.Read.All</span></span> |    <span data-ttu-id="2d446-117">'Informatie over bedreigings- en kwetsbaarheidsbeheersoftware lezen'</span><span class="sxs-lookup"><span data-stu-id="2d446-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="2d446-118">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="2d446-118">Delegated (work or school account)</span></span> | <span data-ttu-id="2d446-119">Software.Lezen</span><span class="sxs-lookup"><span data-stu-id="2d446-119">Software.Read</span></span> |    <span data-ttu-id="2d446-120">'Informatie over bedreigings- en kwetsbaarheidsbeheersoftware lezen'</span><span class="sxs-lookup"><span data-stu-id="2d446-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="2d446-121">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="2d446-121">HTTP request</span></span>
```
GET /api/Software
```

## <a name="request-headers"></a><span data-ttu-id="2d446-122">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="2d446-122">Request headers</span></span>

<span data-ttu-id="2d446-123">Naam</span><span class="sxs-lookup"><span data-stu-id="2d446-123">Name</span></span> | <span data-ttu-id="2d446-124">Type</span><span class="sxs-lookup"><span data-stu-id="2d446-124">Type</span></span> | <span data-ttu-id="2d446-125">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="2d446-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="2d446-126">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="2d446-126">Authorization</span></span> | <span data-ttu-id="2d446-127">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2d446-127">String</span></span> | <span data-ttu-id="2d446-128">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="2d446-128">Bearer {token}.</span></span> <span data-ttu-id="2d446-129">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="2d446-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="2d446-130">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="2d446-130">Request body</span></span>
<span data-ttu-id="2d446-131">Leeg</span><span class="sxs-lookup"><span data-stu-id="2d446-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="2d446-132">Antwoord</span><span class="sxs-lookup"><span data-stu-id="2d446-132">Response</span></span>
<span data-ttu-id="2d446-133">Als dit is gelukt, retourneert deze methode 200 OK met de softwarevoorraad in de body.</span><span class="sxs-lookup"><span data-stu-id="2d446-133">If successful, this method returns 200 OK with the software inventory in the body.</span></span>


## <a name="example"></a><span data-ttu-id="2d446-134">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="2d446-134">Example</span></span>

<span data-ttu-id="2d446-135">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="2d446-135">**Request**</span></span>

<span data-ttu-id="2d446-136">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="2d446-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software
```

<span data-ttu-id="2d446-137">**Antwoord**</span><span class="sxs-lookup"><span data-stu-id="2d446-137">**Response**</span></span>

<span data-ttu-id="2d446-138">Hier is een voorbeeld van het antwoord.</span><span class="sxs-lookup"><span data-stu-id="2d446-138">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Software",
    "value": [
            {
                "id": "microsoft-_-edge",
                "name": "edge",
                "vendor": "microsoft",
                "weaknesses": 467,
                "publicExploit": true,
                "activeAlert": false,
                "exposedMachines": 172,
                "impactScore": 2.39947438
            }
            ...
        ]
}
```

## <a name="related-topics"></a><span data-ttu-id="2d446-139">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="2d446-139">Related topics</span></span>
- [<span data-ttu-id="2d446-140">Risicogebaseerd bedreigingsbeheer & kwetsbaarheidsbeheer</span><span class="sxs-lookup"><span data-stu-id="2d446-140">Risk-based Threat & Vulnerability Management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="2d446-141">Inventaris van & beveiligingsprobleemsoftware</span><span class="sxs-lookup"><span data-stu-id="2d446-141">Threat & Vulnerability software inventory</span></span>](/microsoft-365/security/defender-endpoint/tvm-software-inventory)
