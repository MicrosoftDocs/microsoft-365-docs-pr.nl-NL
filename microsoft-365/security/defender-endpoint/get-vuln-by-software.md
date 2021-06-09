---
title: Lijst van beveiligingsproblemen per software
description: Een lijst met beveiligingslekken in de geïnstalleerde software ophalen.
keywords: api's, graph api, ondersteunde api's, get, lijst met beveiligingslekken, Microsoft Defender voor Endpoint tvm-api
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
ms.openlocfilehash: 18a2cf87cd0e6b898a9f2aa4d6ecd47a86a8c7f6
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769915"
---
# <a name="list-vulnerabilities-by-software"></a><span data-ttu-id="33862-104">Lijst van beveiligingsproblemen per software</span><span class="sxs-lookup"><span data-stu-id="33862-104">List vulnerabilities by software</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="33862-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="33862-105">**Applies to:**</span></span>
- [<span data-ttu-id="33862-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="33862-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="33862-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="33862-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="33862-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="33862-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="33862-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="33862-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="33862-110">Een lijst met beveiligingslekken in de geïnstalleerde software ophalen.</span><span class="sxs-lookup"><span data-stu-id="33862-110">Retrieve a list of vulnerabilities in the installed software.</span></span> 

## <a name="permissions"></a><span data-ttu-id="33862-111">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="33862-111">Permissions</span></span>
<span data-ttu-id="33862-112">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="33862-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="33862-113">Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="33862-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="33862-114">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="33862-114">Permission type</span></span> |   <span data-ttu-id="33862-115">Machtiging</span><span class="sxs-lookup"><span data-stu-id="33862-115">Permission</span></span>  |   <span data-ttu-id="33862-116">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="33862-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="33862-117">Toepassing</span><span class="sxs-lookup"><span data-stu-id="33862-117">Application</span></span> | <span data-ttu-id="33862-118">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="33862-118">Software.Read.All</span></span> | <span data-ttu-id="33862-119">'Informatie over bedreigings- en kwetsbaarheidsbeheersoftware lezen'</span><span class="sxs-lookup"><span data-stu-id="33862-119">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="33862-120">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="33862-120">Delegated (work or school account)</span></span> | <span data-ttu-id="33862-121">Software.Lezen</span><span class="sxs-lookup"><span data-stu-id="33862-121">Software.Read</span></span> | <span data-ttu-id="33862-122">'Informatie over bedreigings- en kwetsbaarheidsbeheersoftware lezen'</span><span class="sxs-lookup"><span data-stu-id="33862-122">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="33862-123">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="33862-123">HTTP request</span></span>
```
GET /api/Software/{Id}/vulnerabilities
```

## <a name="request-headers"></a><span data-ttu-id="33862-124">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="33862-124">Request headers</span></span>

| <span data-ttu-id="33862-125">Naam</span><span class="sxs-lookup"><span data-stu-id="33862-125">Name</span></span>        | <span data-ttu-id="33862-126">Type</span><span class="sxs-lookup"><span data-stu-id="33862-126">Type</span></span> | <span data-ttu-id="33862-127">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="33862-127">Description</span></span>
|:--------------|:-------|:--------------|
| <span data-ttu-id="33862-128">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="33862-128">Authorization</span></span> | <span data-ttu-id="33862-129">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="33862-129">String</span></span> | <span data-ttu-id="33862-130">Bearer {token}. **Vereist**.</span><span class="sxs-lookup"><span data-stu-id="33862-130">Bearer {token}.**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="33862-131">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="33862-131">Request body</span></span>
<span data-ttu-id="33862-132">Leeg</span><span class="sxs-lookup"><span data-stu-id="33862-132">Empty</span></span>

## <a name="response"></a><span data-ttu-id="33862-133">Antwoord</span><span class="sxs-lookup"><span data-stu-id="33862-133">Response</span></span>
<span data-ttu-id="33862-134">Als dit is gelukt, retourneert deze methode 200 OK met een lijst met beveiligingslekken die door de opgegeven software worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="33862-134">If successful, this method returns 200 OK with a list of vulnerabilities exposed by the specified software.</span></span> 


## <a name="example"></a><span data-ttu-id="33862-135">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="33862-135">Example</span></span>

<span data-ttu-id="33862-136">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="33862-136">**Request**</span></span>

<span data-ttu-id="33862-137">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="33862-137">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/vulnerabilities 
```

<span data-ttu-id="33862-138">**Antwoord**</span><span class="sxs-lookup"><span data-stu-id="33862-138">**Response**</span></span>

<span data-ttu-id="33862-139">Hier is een voorbeeld van het antwoord.</span><span class="sxs-lookup"><span data-stu-id="33862-139">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(Analytics.Contracts.PublicAPI.PublicVulnerabilityDto)",
    "value": [
            {
                "id": "CVE-2017-0140",
                "name": "CVE-2017-0140",
                "description": "A security feature bypass vulnerability exists when Microsoft Edge improperly handles requests of different origins. The vulnerability allows Microsoft Edge to bypass Same-Origin Policy (SOP) restrictions, and to allow requests that should otherwise be ignored. An attacker who successfully exploited the vulnerability could force the browser to send data that would otherwise be restricted.In a web-based attack scenario, an attacker could host a specially crafted website that is designed to exploit the vulnerability through Microsoft Edge and then convince a user to view the website. The attacker could also take advantage of compromised websites, and websites that accept or host user-provided content or advertisements. These websites could contain specially crafted content that could exploit the vulnerability.The security update addresses the vulnerability by modifying how affected Microsoft Edge handles different-origin requests.",
                "severity": "Medium",
                "cvssV3": 4.2,
                "exposedMachines": 1,
                "publishedOn": "2017-03-14T00:00:00Z",
                "updatedOn": "2019-10-03T00:03:00Z",
                "publicExploit": false,
                "exploitVerified": false,
                "exploitInKit": false,
                "exploitTypes": [],
                "exploitUris": []
            }
            ...
        ]
}
```

