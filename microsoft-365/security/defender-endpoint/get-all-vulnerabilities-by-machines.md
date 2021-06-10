---
title: Alle beveiligingslekken per computer en software krijgen
description: Hiermee wordt een lijst opgehaald met alle beveiligingslekken die van invloed zijn op de organisatie door Machine en Software
keywords: api's, graph api, ondersteunde api's, get, vulnerability information, Microsoft Defender for Endpoint tvm api
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
ms.openlocfilehash: 01e14be20cee2b8644ebe5d1d1212f921a2fb9b5
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841520"
---
# <a name="list-vulnerabilities-by-machine-and-software"></a><span data-ttu-id="57d37-104">Lijst van beveiligingsproblemen per computer en software</span><span class="sxs-lookup"><span data-stu-id="57d37-104">List vulnerabilities by machine and software</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="57d37-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="57d37-105">**Applies to:**</span></span>
- [<span data-ttu-id="57d37-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="57d37-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="57d37-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="57d37-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="57d37-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="57d37-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="57d37-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="57d37-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="57d37-110">Hiermee wordt een lijst opgehaald met alle beveiligingslekken die van invloed zijn op de organisatie per [computer](machine.md) en [software.](software.md)</span><span class="sxs-lookup"><span data-stu-id="57d37-110">Retrieves a list of all the vulnerabilities affecting the organization per [machine](machine.md) and [software](software.md).</span></span>
- <span data-ttu-id="57d37-111">Als het beveiligingsprobleem een kb-fix heeft, wordt deze weergegeven in het antwoord.</span><span class="sxs-lookup"><span data-stu-id="57d37-111">If the vulnerability has a fixing KB, it will appear in the response.</span></span>
- <span data-ttu-id="57d37-112">Ondersteunt [OData V4-query's.](https://www.odata.org/documentation/)</span><span class="sxs-lookup"><span data-stu-id="57d37-112">Supports [OData V4 queries](https://www.odata.org/documentation/).</span></span>
- <span data-ttu-id="57d37-113">De OData ```$filter``` wordt ondersteund voor alle eigenschappen.</span><span class="sxs-lookup"><span data-stu-id="57d37-113">The OData ```$filter``` is supported on all properties.</span></span>

>[!Tip]
><span data-ttu-id="57d37-114">Dit is een geweldige API [voor Power BI integratie.](api-power-bi.md)</span><span class="sxs-lookup"><span data-stu-id="57d37-114">This is great API for [Power BI integration](api-power-bi.md).</span></span>

## <a name="permissions"></a><span data-ttu-id="57d37-115">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="57d37-115">Permissions</span></span>
<span data-ttu-id="57d37-116">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="57d37-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="57d37-117">Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="57d37-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="57d37-118">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="57d37-118">Permission type</span></span> |   <span data-ttu-id="57d37-119">Machtiging</span><span class="sxs-lookup"><span data-stu-id="57d37-119">Permission</span></span>  |   <span data-ttu-id="57d37-120">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="57d37-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="57d37-121">Toepassing</span><span class="sxs-lookup"><span data-stu-id="57d37-121">Application</span></span> |   <span data-ttu-id="57d37-122">Kwetsbaarheid.Read.All</span><span class="sxs-lookup"><span data-stu-id="57d37-122">Vulnerability.Read.All</span></span> |    <span data-ttu-id="57d37-123">'Informatie over kwetsbaarheidsinformatie over bedreigings- en kwetsbaarheidsbeheer lezen'</span><span class="sxs-lookup"><span data-stu-id="57d37-123">'Read Threat and Vulnerability Management vulnerability information'</span></span>
<span data-ttu-id="57d37-124">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="57d37-124">Delegated (work or school account)</span></span> | <span data-ttu-id="57d37-125">Kwetsbaarheid.Lezen</span><span class="sxs-lookup"><span data-stu-id="57d37-125">Vulnerability.Read</span></span> |   <span data-ttu-id="57d37-126">'Informatie over kwetsbaarheidsinformatie over bedreigings- en kwetsbaarheidsbeheer lezen'</span><span class="sxs-lookup"><span data-stu-id="57d37-126">'Read Threat and Vulnerability Management vulnerability information'</span></span>

## <a name="http-request"></a><span data-ttu-id="57d37-127">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="57d37-127">HTTP request</span></span>
```
GET /api/vulnerabilities/machinesVulnerabilities
```

## <a name="request-headers"></a><span data-ttu-id="57d37-128">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="57d37-128">Request headers</span></span>

<span data-ttu-id="57d37-129">Naam</span><span class="sxs-lookup"><span data-stu-id="57d37-129">Name</span></span> | <span data-ttu-id="57d37-130">Type</span><span class="sxs-lookup"><span data-stu-id="57d37-130">Type</span></span> | <span data-ttu-id="57d37-131">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="57d37-131">Description</span></span>
:---|:---|:---
<span data-ttu-id="57d37-132">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="57d37-132">Authorization</span></span> | <span data-ttu-id="57d37-133">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="57d37-133">String</span></span> | <span data-ttu-id="57d37-134">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="57d37-134">Bearer {token}.</span></span> <span data-ttu-id="57d37-135">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="57d37-135">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="57d37-136">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="57d37-136">Request body</span></span>
<span data-ttu-id="57d37-137">Leeg</span><span class="sxs-lookup"><span data-stu-id="57d37-137">Empty</span></span>

## <a name="response"></a><span data-ttu-id="57d37-138">Antwoord</span><span class="sxs-lookup"><span data-stu-id="57d37-138">Response</span></span>
<span data-ttu-id="57d37-139">Als dit is gelukt, retourneert deze methode 200 OK met de lijst met beveiligingslekken in de body.</span><span class="sxs-lookup"><span data-stu-id="57d37-139">If successful, this method returns 200 OK with the list of vulnerabilities in the body.</span></span>


## <a name="example"></a><span data-ttu-id="57d37-140">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="57d37-140">Example</span></span>

<span data-ttu-id="57d37-141">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="57d37-141">**Request**</span></span>

<span data-ttu-id="57d37-142">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="57d37-142">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/vulnerabilities/machinesVulnerabilities
```

<span data-ttu-id="57d37-143">**Antwoord**</span><span class="sxs-lookup"><span data-stu-id="57d37-143">**Response**</span></span>

<span data-ttu-id="57d37-144">Hier is een voorbeeld van het antwoord.</span><span class="sxs-lookup"><span data-stu-id="57d37-144">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.PublicAssetVulnerabilityDto)",
    "value": [
        {
            "id": "5afa3afc92a7c63d4b70129e0a6f33f63a427e21-_-CVE-2020-6494-_-microsoft-_-edge_chromium-based-_-81.0.416.77-_-",
            "cveId": "CVE-2020-6494",
            "machineId": "5afa3afc92a7c63d4b70129e0a6f33f63a427e21",
            "fixingKbId": null,
            "productName": "edge_chromium-based",
            "productVendor": "microsoft",
            "productVersion": "81.0.416.77",
            "severity": "Low"
        },
        {
            "id": "7a704e17d1c2977c0e7b665fb18ae6e1fe7f3283-_-CVE-2016-3348-_-microsoft-_-windows_server_2012_r2-_-6.3.9600.19728-_-3185911",
            "cveId": "CVE-2016-3348",
            "machineId": "7a704e17d1c2977c0e7b665fb18ae6e1fe7f3283",
            "fixingKbId": "3185911",
            "productName": "windows_server_2012_r2",
            "productVendor": "microsoft",
            "productVersion": "6.3.9600.19728",
            "severity": "Low"
        },
        ...
    ]

}
```

## <a name="see-also"></a><span data-ttu-id="57d37-145">Zie ook</span><span class="sxs-lookup"><span data-stu-id="57d37-145">See also</span></span>

- [<span data-ttu-id="57d37-146">Risicogebaseerde Threat and Vulnerability Management</span><span class="sxs-lookup"><span data-stu-id="57d37-146">Risk-based threat and vulnerability management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="57d37-147">Beveiligingslekken in uw organisatie</span><span class="sxs-lookup"><span data-stu-id="57d37-147">Vulnerabilities in your organization</span></span>](/microsoft-365/security/defender-endpoint/tvm-weaknesses)
