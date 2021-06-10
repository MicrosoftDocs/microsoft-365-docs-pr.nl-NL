---
title: Gevonden beveiligingsproblemen ophalen
description: Hiermee wordt een verzameling gevonden beveiligingslekken met betrekking tot een bepaalde apparaat-id opgehaald.
keywords: api's, graph api, ondersteunde api's, get, list, file, information, discovered vulnerabilities, threat & vulnerability management api, Microsoft Defender for Endpoint tvm api
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
ms.openlocfilehash: 73d9803736df546f2381b7a84c9089d2460c4c44
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843080"
---
# <a name="get-discovered-vulnerabilities"></a><span data-ttu-id="b3fb6-104">Gevonden beveiligingsproblemen ophalen</span><span class="sxs-lookup"><span data-stu-id="b3fb6-104">Get discovered vulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b3fb6-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="b3fb6-105">**Applies to:**</span></span>
- [<span data-ttu-id="b3fb6-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="b3fb6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b3fb6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b3fb6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="b3fb6-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="b3fb6-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b3fb6-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="b3fb6-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="b3fb6-110">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="b3fb6-110">API description</span></span>
<span data-ttu-id="b3fb6-111">Hiermee wordt een verzameling gevonden beveiligingslekken met betrekking tot een bepaalde apparaat-id opgehaald.</span><span class="sxs-lookup"><span data-stu-id="b3fb6-111">Retrieves a collection of discovered vulnerabilities related to a given device ID.</span></span>

## <a name="limitations"></a><span data-ttu-id="b3fb6-112">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="b3fb6-112">Limitations</span></span>
1. <span data-ttu-id="b3fb6-113">Tariefbeperkingen voor deze API zijn 50 oproepen per minuut en 1500 oproepen per uur.</span><span class="sxs-lookup"><span data-stu-id="b3fb6-113">Rate limitations for this API are 50 calls per minute and 1500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="b3fb6-114">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="b3fb6-114">Permissions</span></span>

<span data-ttu-id="b3fb6-115">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="b3fb6-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="b3fb6-116">Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="b3fb6-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="b3fb6-117">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="b3fb6-117">Permission type</span></span> | <span data-ttu-id="b3fb6-118">Machtiging</span><span class="sxs-lookup"><span data-stu-id="b3fb6-118">Permission</span></span> | <span data-ttu-id="b3fb6-119">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="b3fb6-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="b3fb6-120">Toepassing</span><span class="sxs-lookup"><span data-stu-id="b3fb6-120">Application</span></span> |<span data-ttu-id="b3fb6-121">Kwetsbaarheid.Read.All</span><span class="sxs-lookup"><span data-stu-id="b3fb6-121">Vulnerability.Read.All</span></span> | <span data-ttu-id="b3fb6-122">'Informatie over kwetsbaarheidsinformatie over bedreigings- en kwetsbaarheidsbeheer lezen'</span><span class="sxs-lookup"><span data-stu-id="b3fb6-122">'Read Threat and Vulnerability Management vulnerability information'</span></span>
<span data-ttu-id="b3fb6-123">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="b3fb6-123">Delegated (work or school account)</span></span> | <span data-ttu-id="b3fb6-124">Kwetsbaarheid.Lezen</span><span class="sxs-lookup"><span data-stu-id="b3fb6-124">Vulnerability.Read</span></span> | <span data-ttu-id="b3fb6-125">'Informatie over kwetsbaarheidsinformatie over bedreigings- en kwetsbaarheidsbeheer lezen'</span><span class="sxs-lookup"><span data-stu-id="b3fb6-125">'Read Threat and Vulnerability Management vulnerability information'</span></span>

## <a name="http-request"></a><span data-ttu-id="b3fb6-126">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="b3fb6-126">HTTP request</span></span>

```
GET /api/machines/{machineId}/vulnerabilities
```

## <a name="request-headers"></a><span data-ttu-id="b3fb6-127">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="b3fb6-127">Request headers</span></span>

<span data-ttu-id="b3fb6-128">Naam</span><span class="sxs-lookup"><span data-stu-id="b3fb6-128">Name</span></span> | <span data-ttu-id="b3fb6-129">Type</span><span class="sxs-lookup"><span data-stu-id="b3fb6-129">Type</span></span> | <span data-ttu-id="b3fb6-130">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="b3fb6-130">Description</span></span>
:---|:---|:---
<span data-ttu-id="b3fb6-131">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="b3fb6-131">Authorization</span></span> | <span data-ttu-id="b3fb6-132">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b3fb6-132">String</span></span> | <span data-ttu-id="b3fb6-133">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="b3fb6-133">Bearer {token}.</span></span> <span data-ttu-id="b3fb6-134">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="b3fb6-134">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="b3fb6-135">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="b3fb6-135">Request body</span></span>

<span data-ttu-id="b3fb6-136">Leeg</span><span class="sxs-lookup"><span data-stu-id="b3fb6-136">Empty</span></span>

## <a name="response"></a><span data-ttu-id="b3fb6-137">Antwoord</span><span class="sxs-lookup"><span data-stu-id="b3fb6-137">Response</span></span>

<span data-ttu-id="b3fb6-138">Als dit is gelukt, retourneert deze methode 200 OK met de gevonden kwetsbaarheidsgegevens in de body.</span><span class="sxs-lookup"><span data-stu-id="b3fb6-138">If successful, this method returns 200 OK with the discovered vulnerability information in the body.</span></span>

## <a name="example"></a><span data-ttu-id="b3fb6-139">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="b3fb6-139">Example</span></span>

### <a name="request"></a><span data-ttu-id="b3fb6-140">Aanvraag</span><span class="sxs-lookup"><span data-stu-id="b3fb6-140">Request</span></span>

<span data-ttu-id="b3fb6-141">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="b3fb6-141">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/ac233fa6208e1579620bf44207c4006ed7cc4501/vulnerabilities
```

### <a name="response"></a><span data-ttu-id="b3fb6-142">Antwoord</span><span class="sxs-lookup"><span data-stu-id="b3fb6-142">Response</span></span>

<span data-ttu-id="b3fb6-143">Hier is een voorbeeld van het antwoord.</span><span class="sxs-lookup"><span data-stu-id="b3fb6-143">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(Analytics.Contracts.PublicAPI.PublicVulnerabilityDto)",
    "value": [
        {
            "id": "CVE-2019-1348",
            "name": "CVE-2019-1348",
            "description": "Git could allow a remote attacker to bypass security restrictions, caused by a flaw in the --export-marks option of git fast-import. By persuading a victim to import specially-crafted content, an attacker could exploit this vulnerability to overwrite arbitrary paths.",
            "severity": "Medium",
            "cvssV3": 4.3,
            "exposedMachines": 1,
            "publishedOn": "2019-12-13T00:00:00Z",
            "updatedOn": "2019-12-13T00:00:00Z",
            "publicExploit": false,
            "exploitVerified": false,
            "exploitInKit": false,
            "exploitTypes": [],
            "exploitUris": []
        }
}
```

## <a name="see-also"></a><span data-ttu-id="b3fb6-144">Zie ook</span><span class="sxs-lookup"><span data-stu-id="b3fb6-144">See also</span></span>

- [<span data-ttu-id="b3fb6-145">Risicogebaseerd bedreigingsbeheer & kwetsbaarheidsbeheer</span><span class="sxs-lookup"><span data-stu-id="b3fb6-145">Risk-based Threat & Vulnerability Management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="b3fb6-146">Beveiligingslekken in uw organisatie</span><span class="sxs-lookup"><span data-stu-id="b3fb6-146">Vulnerabilities in your organization</span></span>](/microsoft-365/security/defender-endpoint/tvm-weaknesses)
