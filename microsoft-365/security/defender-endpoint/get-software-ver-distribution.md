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
ms.openlocfilehash: 7ac7fdf4c38846e2e8be614567ddb87a98e3a96c
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772121"
---
# <a name="list-software-version-distribution"></a><span data-ttu-id="65dfc-104">Lijst van distributie van softwareversies</span><span class="sxs-lookup"><span data-stu-id="65dfc-104">List software version distribution</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="65dfc-105">**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="65dfc-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="65dfc-106">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="65dfc-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="65dfc-107">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="65dfc-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="65dfc-108">Hiermee wordt een lijst met de distributie van de softwareversie van uw organisatie opgehaald.</span><span class="sxs-lookup"><span data-stu-id="65dfc-108">Retrieves a list of your organization's software version distribution.</span></span> 

## <a name="permissions"></a><span data-ttu-id="65dfc-109">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="65dfc-109">Permissions</span></span>
<span data-ttu-id="65dfc-110">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="65dfc-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="65dfc-111">Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="65dfc-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="65dfc-112">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="65dfc-112">Permission type</span></span> |   <span data-ttu-id="65dfc-113">Machtiging</span><span class="sxs-lookup"><span data-stu-id="65dfc-113">Permission</span></span>  |   <span data-ttu-id="65dfc-114">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="65dfc-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="65dfc-115">Toepassing</span><span class="sxs-lookup"><span data-stu-id="65dfc-115">Application</span></span> | <span data-ttu-id="65dfc-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="65dfc-116">Software.Read.All</span></span> | <span data-ttu-id="65dfc-117">'Informatie over bedreigings- en kwetsbaarheidsbeheersoftware lezen'</span><span class="sxs-lookup"><span data-stu-id="65dfc-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="65dfc-118">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="65dfc-118">Delegated (work or school account)</span></span> | <span data-ttu-id="65dfc-119">Software.Lezen</span><span class="sxs-lookup"><span data-stu-id="65dfc-119">Software.Read</span></span> | <span data-ttu-id="65dfc-120">'Informatie over bedreigings- en kwetsbaarheidsbeheersoftware lezen'</span><span class="sxs-lookup"><span data-stu-id="65dfc-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="65dfc-121">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="65dfc-121">HTTP request</span></span>
```
GET /api/Software/{Id}/distributions
```

## <a name="request-headers"></a><span data-ttu-id="65dfc-122">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="65dfc-122">Request headers</span></span>

| <span data-ttu-id="65dfc-123">Naam</span><span class="sxs-lookup"><span data-stu-id="65dfc-123">Name</span></span>        | <span data-ttu-id="65dfc-124">Type</span><span class="sxs-lookup"><span data-stu-id="65dfc-124">Type</span></span> | <span data-ttu-id="65dfc-125">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="65dfc-125">Description</span></span>
|:--------------|:-------|:--------------|
| <span data-ttu-id="65dfc-126">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="65dfc-126">Authorization</span></span> | <span data-ttu-id="65dfc-127">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="65dfc-127">String</span></span> | <span data-ttu-id="65dfc-128">Bearer {token}. **Vereist**.</span><span class="sxs-lookup"><span data-stu-id="65dfc-128">Bearer {token}.**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="65dfc-129">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="65dfc-129">Request body</span></span>
<span data-ttu-id="65dfc-130">Leeg</span><span class="sxs-lookup"><span data-stu-id="65dfc-130">Empty</span></span>

## <a name="response"></a><span data-ttu-id="65dfc-131">Antwoord</span><span class="sxs-lookup"><span data-stu-id="65dfc-131">Response</span></span>
<span data-ttu-id="65dfc-132">Als dit lukt, retourneert deze methode 200 OK met een lijst met gegevens over softwaredistributies in de body.</span><span class="sxs-lookup"><span data-stu-id="65dfc-132">If successful, this method returns 200 OK with a list of software distributions data in the body.</span></span> 


## <a name="example"></a><span data-ttu-id="65dfc-133">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="65dfc-133">Example</span></span>

<span data-ttu-id="65dfc-134">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="65dfc-134">**Request**</span></span>

<span data-ttu-id="65dfc-135">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="65dfc-135">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/distributions
```

<span data-ttu-id="65dfc-136">**Antwoord**</span><span class="sxs-lookup"><span data-stu-id="65dfc-136">**Response**</span></span>

<span data-ttu-id="65dfc-137">Hier is een voorbeeld van het antwoord.</span><span class="sxs-lookup"><span data-stu-id="65dfc-137">Here is an example of the response.</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="65dfc-138">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="65dfc-138">Related topics</span></span>
- [<span data-ttu-id="65dfc-139">Risicogebaseerd bedreigingsbeheer & kwetsbaarheidsbeheer</span><span class="sxs-lookup"><span data-stu-id="65dfc-139">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="65dfc-140">Inventaris van & beveiligingsprobleemsoftware</span><span class="sxs-lookup"><span data-stu-id="65dfc-140">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
