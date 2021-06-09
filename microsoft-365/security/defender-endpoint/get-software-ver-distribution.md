---
title: Lijst van distributie van softwareversies
description: Hiermee wordt een lijst met de distributie van de softwareversie van uw organisatie opgehaald
keywords: api's, graph api, ondersteunde api's, get, softwareversiedistributie, Microsoft Defender voor Endpoint tvm api
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
ms.openlocfilehash: 7d0e38789cfc576c0c3f1a8be352796e674ac13a
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845004"
---
# <a name="list-software-version-distribution"></a><span data-ttu-id="cc19a-104">Lijst van distributie van softwareversies</span><span class="sxs-lookup"><span data-stu-id="cc19a-104">List software version distribution</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="cc19a-105">**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="cc19a-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="cc19a-106">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="cc19a-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="cc19a-107">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="cc19a-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="cc19a-108">Hiermee wordt een lijst met de distributie van de softwareversie van uw organisatie opgehaald.</span><span class="sxs-lookup"><span data-stu-id="cc19a-108">Retrieves a list of your organization's software version distribution.</span></span> 

## <a name="permissions"></a><span data-ttu-id="cc19a-109">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="cc19a-109">Permissions</span></span>
<span data-ttu-id="cc19a-110">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="cc19a-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="cc19a-111">Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="cc19a-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="cc19a-112">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="cc19a-112">Permission type</span></span> |   <span data-ttu-id="cc19a-113">Machtiging</span><span class="sxs-lookup"><span data-stu-id="cc19a-113">Permission</span></span>  |   <span data-ttu-id="cc19a-114">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="cc19a-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="cc19a-115">Toepassing</span><span class="sxs-lookup"><span data-stu-id="cc19a-115">Application</span></span> | <span data-ttu-id="cc19a-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="cc19a-116">Software.Read.All</span></span> | <span data-ttu-id="cc19a-117">'Informatie over bedreigings- en kwetsbaarheidsbeheersoftware lezen'</span><span class="sxs-lookup"><span data-stu-id="cc19a-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="cc19a-118">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="cc19a-118">Delegated (work or school account)</span></span> | <span data-ttu-id="cc19a-119">Software.Lezen</span><span class="sxs-lookup"><span data-stu-id="cc19a-119">Software.Read</span></span> | <span data-ttu-id="cc19a-120">'Informatie over bedreigings- en kwetsbaarheidsbeheersoftware lezen'</span><span class="sxs-lookup"><span data-stu-id="cc19a-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="cc19a-121">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="cc19a-121">HTTP request</span></span>
```
GET /api/Software/{Id}/distributions
```

## <a name="request-headers"></a><span data-ttu-id="cc19a-122">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="cc19a-122">Request headers</span></span>

| <span data-ttu-id="cc19a-123">Naam</span><span class="sxs-lookup"><span data-stu-id="cc19a-123">Name</span></span>        | <span data-ttu-id="cc19a-124">Type</span><span class="sxs-lookup"><span data-stu-id="cc19a-124">Type</span></span> | <span data-ttu-id="cc19a-125">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="cc19a-125">Description</span></span>
|:--------------|:-------|:--------------|
| <span data-ttu-id="cc19a-126">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="cc19a-126">Authorization</span></span> | <span data-ttu-id="cc19a-127">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="cc19a-127">String</span></span> | <span data-ttu-id="cc19a-128">Bearer {token}. **Vereist**.</span><span class="sxs-lookup"><span data-stu-id="cc19a-128">Bearer {token}.**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="cc19a-129">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="cc19a-129">Request body</span></span>
<span data-ttu-id="cc19a-130">Leeg</span><span class="sxs-lookup"><span data-stu-id="cc19a-130">Empty</span></span>

## <a name="response"></a><span data-ttu-id="cc19a-131">Antwoord</span><span class="sxs-lookup"><span data-stu-id="cc19a-131">Response</span></span>
<span data-ttu-id="cc19a-132">Als dit lukt, retourneert deze methode 200 OK met een lijst met gegevens over softwaredistributies in de body.</span><span class="sxs-lookup"><span data-stu-id="cc19a-132">If successful, this method returns 200 OK with a list of software distributions data in the body.</span></span> 


## <a name="example"></a><span data-ttu-id="cc19a-133">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="cc19a-133">Example</span></span>

<span data-ttu-id="cc19a-134">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="cc19a-134">**Request**</span></span>

<span data-ttu-id="cc19a-135">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="cc19a-135">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/distributions
```

<span data-ttu-id="cc19a-136">**Antwoord**</span><span class="sxs-lookup"><span data-stu-id="cc19a-136">**Response**</span></span>

<span data-ttu-id="cc19a-137">Hier is een voorbeeld van het antwoord.</span><span class="sxs-lookup"><span data-stu-id="cc19a-137">Here is an example of the response.</span></span>

```json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Distributions",
    "value": [
        {
            "version": "11.0.17134.1039",
            "installations": 1,
            "vulnerabilities": 11
        },
        {
            "version": "11.0.18363.535",
            "installations": 750,
            "vulnerabilities": 0
        }
        ...
    ]
}
```

## <a name="related-topics"></a><span data-ttu-id="cc19a-138">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="cc19a-138">Related topics</span></span>
- [<span data-ttu-id="cc19a-139">Risicogebaseerd bedreigingsbeheer & kwetsbaarheidsbeheer</span><span class="sxs-lookup"><span data-stu-id="cc19a-139">Risk-based Threat & Vulnerability Management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="cc19a-140">Inventaris van & beveiligingsprobleemsoftware</span><span class="sxs-lookup"><span data-stu-id="cc19a-140">Threat & Vulnerability software inventory</span></span>](/microsoft-365/security/defender-endpoint/tvm-software-inventory)
