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
ms.openlocfilehash: cd3b1343711a5bed9ad606a6b8dc754f223ed279
ms.sourcegitcommit: 997a21b83795789cda0a6b4a77f9985a3233d0c0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/14/2021
ms.locfileid: "53430778"
---
# <a name="get-discovered-vulnerabilities"></a><span data-ttu-id="296fa-104">Gevonden beveiligingsproblemen ophalen</span><span class="sxs-lookup"><span data-stu-id="296fa-104">Get discovered vulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="296fa-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="296fa-105">**Applies to:**</span></span>
- [<span data-ttu-id="296fa-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="296fa-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="296fa-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="296fa-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="296fa-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="296fa-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="296fa-109">Meld u aan voor een gratis proefversie.</span><span class="sxs-lookup"><span data-stu-id="296fa-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="296fa-110">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="296fa-110">API description</span></span>
<span data-ttu-id="296fa-111">Hiermee wordt een verzameling gevonden beveiligingslekken met betrekking tot een bepaalde apparaat-id opgehaald.</span><span class="sxs-lookup"><span data-stu-id="296fa-111">Retrieves a collection of discovered vulnerabilities related to a given device ID.</span></span>

## <a name="limitations"></a><span data-ttu-id="296fa-112">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="296fa-112">Limitations</span></span>
1. <span data-ttu-id="296fa-113">Tariefbeperkingen voor deze API zijn 50 oproepen per minuut en 1500 oproepen per uur.</span><span class="sxs-lookup"><span data-stu-id="296fa-113">Rate limitations for this API are 50 calls per minute and 1500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="296fa-114">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="296fa-114">Permissions</span></span>

<span data-ttu-id="296fa-115">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="296fa-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="296fa-116">Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="296fa-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="296fa-117">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="296fa-117">Permission type</span></span> | <span data-ttu-id="296fa-118">Machtiging</span><span class="sxs-lookup"><span data-stu-id="296fa-118">Permission</span></span> | <span data-ttu-id="296fa-119">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="296fa-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="296fa-120">Toepassing</span><span class="sxs-lookup"><span data-stu-id="296fa-120">Application</span></span> |<span data-ttu-id="296fa-121">Kwetsbaarheid.Read.All</span><span class="sxs-lookup"><span data-stu-id="296fa-121">Vulnerability.Read.All</span></span> | <span data-ttu-id="296fa-122">'Informatie over kwetsbaarheidsinformatie over bedreigings- en kwetsbaarheidsbeheer lezen'</span><span class="sxs-lookup"><span data-stu-id="296fa-122">'Read Threat and Vulnerability Management vulnerability information'</span></span>
<span data-ttu-id="296fa-123">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="296fa-123">Delegated (work or school account)</span></span> | <span data-ttu-id="296fa-124">Kwetsbaarheid.Lezen</span><span class="sxs-lookup"><span data-stu-id="296fa-124">Vulnerability.Read</span></span> | <span data-ttu-id="296fa-125">'Informatie over kwetsbaarheidsinformatie over bedreigings- en kwetsbaarheidsbeheer lezen'</span><span class="sxs-lookup"><span data-stu-id="296fa-125">'Read Threat and Vulnerability Management vulnerability information'</span></span>

## <a name="http-request"></a><span data-ttu-id="296fa-126">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="296fa-126">HTTP request</span></span>

```
GET /api/machines/{machineId}/vulnerabilities
```

## <a name="request-headers"></a><span data-ttu-id="296fa-127">Aanvraagheaders</span><span class="sxs-lookup"><span data-stu-id="296fa-127">Request headers</span></span>

<span data-ttu-id="296fa-128">Naam</span><span class="sxs-lookup"><span data-stu-id="296fa-128">Name</span></span> | <span data-ttu-id="296fa-129">Type</span><span class="sxs-lookup"><span data-stu-id="296fa-129">Type</span></span> | <span data-ttu-id="296fa-130">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="296fa-130">Description</span></span>
:---|:---|:---
<span data-ttu-id="296fa-131">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="296fa-131">Authorization</span></span> | <span data-ttu-id="296fa-132">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="296fa-132">String</span></span> | <span data-ttu-id="296fa-133">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="296fa-133">Bearer {token}.</span></span> <span data-ttu-id="296fa-134">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="296fa-134">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="296fa-135">Aanvraagtekst</span><span class="sxs-lookup"><span data-stu-id="296fa-135">Request body</span></span>

<span data-ttu-id="296fa-136">Leeg</span><span class="sxs-lookup"><span data-stu-id="296fa-136">Empty</span></span>

## <a name="response"></a><span data-ttu-id="296fa-137">Antwoord</span><span class="sxs-lookup"><span data-stu-id="296fa-137">Response</span></span>

<span data-ttu-id="296fa-138">Als dit is gelukt, retourneert deze methode 200 OK met de gevonden kwetsbaarheidsgegevens in de body.</span><span class="sxs-lookup"><span data-stu-id="296fa-138">If successful, this method returns 200 OK with the discovered vulnerability information in the body.</span></span>

## <a name="example"></a><span data-ttu-id="296fa-139">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="296fa-139">Example</span></span>

### <a name="request"></a><span data-ttu-id="296fa-140">Aanvraag</span><span class="sxs-lookup"><span data-stu-id="296fa-140">Request</span></span>

<span data-ttu-id="296fa-141">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="296fa-141">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/ac233fa6208e1579620bf44207c4006ed7cc4501/vulnerabilities
```

### <a name="response"></a><span data-ttu-id="296fa-142">Antwoord</span><span class="sxs-lookup"><span data-stu-id="296fa-142">Response</span></span>

<span data-ttu-id="296fa-143">Hier is een voorbeeld van het antwoord.</span><span class="sxs-lookup"><span data-stu-id="296fa-143">Here is an example of the response.</span></span>

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
    ]
}
```

## <a name="see-also"></a><span data-ttu-id="296fa-144">Zie ook</span><span class="sxs-lookup"><span data-stu-id="296fa-144">See also</span></span>

- [<span data-ttu-id="296fa-145">Risicogebaseerd bedreigingsbeheer & kwetsbaarheidsbeheer</span><span class="sxs-lookup"><span data-stu-id="296fa-145">Risk-based Threat & Vulnerability Management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="296fa-146">Beveiligingslekken in uw organisatie</span><span class="sxs-lookup"><span data-stu-id="296fa-146">Vulnerabilities in your organization</span></span>](/microsoft-365/security/defender-endpoint/tvm-weaknesses)
