---
title: Alle beveiligingslekken krijgen
description: Hiermee wordt een lijst opgehaald met alle beveiligingslekken die van invloed zijn op de organisatie
keywords: api's, graph api, ondersteunde api's, get, vulnerability information, mdatp tvm api
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
ms.technology: mde
ms.openlocfilehash: c97b70b682351e5ad9d92435068b97622032f769
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166586"
---
# <a name="list-vulnerabilities"></a><span data-ttu-id="12b34-104">Lijstproblemen</span><span class="sxs-lookup"><span data-stu-id="12b34-104">List vulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="12b34-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="12b34-105">**Applies to:**</span></span>
- [<span data-ttu-id="12b34-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="12b34-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="12b34-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="12b34-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="12b34-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="12b34-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="12b34-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="12b34-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="12b34-110">Hiermee wordt een lijst opgehaald met alle beveiligingslekken die van invloed zijn op de organisatie.</span><span class="sxs-lookup"><span data-stu-id="12b34-110">Retrieves a list of all the vulnerabilities affecting the organization.</span></span>

## <a name="permissions"></a><span data-ttu-id="12b34-111">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="12b34-111">Permissions</span></span>
<span data-ttu-id="12b34-112">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="12b34-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="12b34-113">Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="12b34-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="12b34-114">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="12b34-114">Permission type</span></span> |   <span data-ttu-id="12b34-115">Machtiging</span><span class="sxs-lookup"><span data-stu-id="12b34-115">Permission</span></span>  |   <span data-ttu-id="12b34-116">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="12b34-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="12b34-117">Toepassing</span><span class="sxs-lookup"><span data-stu-id="12b34-117">Application</span></span> |   <span data-ttu-id="12b34-118">Kwetsbaarheid.Read.All</span><span class="sxs-lookup"><span data-stu-id="12b34-118">Vulnerability.Read.All</span></span> |    <span data-ttu-id="12b34-119">'Informatie over kwetsbaarheidsinformatie over bedreigings- en kwetsbaarheidsbeheer lezen'</span><span class="sxs-lookup"><span data-stu-id="12b34-119">'Read Threat and Vulnerability Management vulnerability information'</span></span>
<span data-ttu-id="12b34-120">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="12b34-120">Delegated (work or school account)</span></span> | <span data-ttu-id="12b34-121">Kwetsbaarheid.Lezen</span><span class="sxs-lookup"><span data-stu-id="12b34-121">Vulnerability.Read</span></span> |   <span data-ttu-id="12b34-122">'Informatie over kwetsbaarheidsinformatie over bedreigings- en kwetsbaarheidsbeheer lezen'</span><span class="sxs-lookup"><span data-stu-id="12b34-122">'Read Threat and Vulnerability Management vulnerability information'</span></span>

## <a name="http-request"></a><span data-ttu-id="12b34-123">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="12b34-123">HTTP request</span></span>
```
GET /api/vulnerabilities
```

## <a name="request-headers"></a><span data-ttu-id="12b34-124">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="12b34-124">Request headers</span></span>

<span data-ttu-id="12b34-125">Naam</span><span class="sxs-lookup"><span data-stu-id="12b34-125">Name</span></span> | <span data-ttu-id="12b34-126">Type</span><span class="sxs-lookup"><span data-stu-id="12b34-126">Type</span></span> | <span data-ttu-id="12b34-127">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="12b34-127">Description</span></span>
:---|:---|:---
<span data-ttu-id="12b34-128">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="12b34-128">Authorization</span></span> | <span data-ttu-id="12b34-129">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="12b34-129">String</span></span> | <span data-ttu-id="12b34-130">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="12b34-130">Bearer {token}.</span></span> <span data-ttu-id="12b34-131">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="12b34-131">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="12b34-132">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="12b34-132">Request body</span></span>
<span data-ttu-id="12b34-133">Leeg</span><span class="sxs-lookup"><span data-stu-id="12b34-133">Empty</span></span>

## <a name="response"></a><span data-ttu-id="12b34-134">Antwoord</span><span class="sxs-lookup"><span data-stu-id="12b34-134">Response</span></span>
<span data-ttu-id="12b34-135">Als dit is gelukt, retourneert deze methode 200 OK met de lijst met beveiligingslekken in de body.</span><span class="sxs-lookup"><span data-stu-id="12b34-135">If successful, this method returns 200 OK with the list of vulnerabilities in the body.</span></span>


## <a name="example"></a><span data-ttu-id="12b34-136">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="12b34-136">Example</span></span>

<span data-ttu-id="12b34-137">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="12b34-137">**Request**</span></span>

<span data-ttu-id="12b34-138">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="12b34-138">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/Vulnerabilities
```

<span data-ttu-id="12b34-139">**Antwoord**</span><span class="sxs-lookup"><span data-stu-id="12b34-139">**Response**</span></span>

<span data-ttu-id="12b34-140">Hier is een voorbeeld van het antwoord.</span><span class="sxs-lookup"><span data-stu-id="12b34-140">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Vulnerabilities",
    "value": [
        {
            "id": "CVE-2019-0608",
            "name": "CVE-2019-0608",
            "description": "A spoofing vulnerability exists when Microsoft Browsers does not properly parse HTTP content. An attacker who successfully exploited this vulnerability could impersonate a user request by crafting HTTP queries. The specially crafted website could either spoof content or serve as a pivot to chain an attack with other vulnerabilities in web services.To exploit the vulnerability, the user must click a specially crafted URL. In an email attack scenario, an attacker could send an email message containing the specially crafted URL to the user in an attempt to convince the user to click it.In a web-based attack scenario, an attacker could host a specially crafted website designed to appear as a legitimate website to the user. However, the attacker would have no way to force the user to visit the specially crafted website. The attacker would have to convince the user to visit the specially crafted website, typically by way of enticement in an email or instant message, and then convince the user to interact with content on the website.The update addresses the vulnerability by correcting how Microsoft Browsers parses HTTP responses.",
            "severity": "Medium",
            "cvssV3": 4.3,
            "exposedMachines": 4,
            "publishedOn": "2019-10-08T00:00:00Z",
            "updatedOn": "2019-12-16T16:20:00Z",
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

## <a name="see-also"></a><span data-ttu-id="12b34-141">Zie ook</span><span class="sxs-lookup"><span data-stu-id="12b34-141">See also</span></span>
- [<span data-ttu-id="12b34-142">Risicogebaseerd bedreigingsbeheer & kwetsbaarheidsbeheer</span><span class="sxs-lookup"><span data-stu-id="12b34-142">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="12b34-143">Beveiligingslekken in uw organisatie</span><span class="sxs-lookup"><span data-stu-id="12b34-143">Vulnerabilities in your organization</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-weaknesses)
