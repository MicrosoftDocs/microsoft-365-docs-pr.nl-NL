---
title: Lijst van beveiligingsproblemen per aanbeveling
description: Hiermee wordt een lijst met beveiligingsproblemen opgehaald die zijn gekoppeld aan de beveiligingsaanbeveling.
keywords: api's, graph api, ondersteunde api's, get, lijst met beveiligingsproblemen, beveiligingsaanbeveling, beveiligingsaanbeveling voor beveiligingsproblemen, Threat and Vulnerability Management, Threat and Vulnerability Management api
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
ms.openlocfilehash: d5a59c3cd57aa369b1edb46eebddffb84a2b8c78
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845148"
---
# <a name="list-vulnerabilities-by-recommendation"></a><span data-ttu-id="40b74-104">Lijst van beveiligingsproblemen per aanbeveling</span><span class="sxs-lookup"><span data-stu-id="40b74-104">List vulnerabilities by recommendation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="40b74-105">**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="40b74-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="40b74-106">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="40b74-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="40b74-107">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="40b74-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="40b74-108">Hiermee wordt een lijst met beveiligingsproblemen opgehaald die zijn gekoppeld aan de beveiligingsaanbeveling.</span><span class="sxs-lookup"><span data-stu-id="40b74-108">Retrieves a list of vulnerabilities associated with the security recommendation.</span></span>

## <a name="permissions"></a><span data-ttu-id="40b74-109">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="40b74-109">Permissions</span></span>
<span data-ttu-id="40b74-110">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="40b74-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="40b74-111">Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="40b74-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="40b74-112">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="40b74-112">Permission type</span></span> |   <span data-ttu-id="40b74-113">Machtiging</span><span class="sxs-lookup"><span data-stu-id="40b74-113">Permission</span></span>  |   <span data-ttu-id="40b74-114">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="40b74-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="40b74-115">Toepassing</span><span class="sxs-lookup"><span data-stu-id="40b74-115">Application</span></span> |   <span data-ttu-id="40b74-116">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="40b74-116">SecurityRecommendation.Read.All</span></span> |   <span data-ttu-id="40b74-117">'Informatie over beveiligingsaanbeveling bedreigings- en kwetsbaarheidsbeheer lezen'</span><span class="sxs-lookup"><span data-stu-id="40b74-117">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="40b74-118">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="40b74-118">Delegated (work or school account)</span></span> | <span data-ttu-id="40b74-119">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="40b74-119">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="40b74-120">'Informatie over beveiligingsaanbeveling bedreigings- en kwetsbaarheidsbeheer lezen'</span><span class="sxs-lookup"><span data-stu-id="40b74-120">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="40b74-121">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="40b74-121">HTTP request</span></span>
```
GET /api/recommendations/{id}/vulnerabilities
```

## <a name="request-headers"></a><span data-ttu-id="40b74-122">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="40b74-122">Request headers</span></span>

<span data-ttu-id="40b74-123">Naam</span><span class="sxs-lookup"><span data-stu-id="40b74-123">Name</span></span> | <span data-ttu-id="40b74-124">Type</span><span class="sxs-lookup"><span data-stu-id="40b74-124">Type</span></span> | <span data-ttu-id="40b74-125">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="40b74-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="40b74-126">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="40b74-126">Authorization</span></span> | <span data-ttu-id="40b74-127">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="40b74-127">String</span></span> | <span data-ttu-id="40b74-128">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="40b74-128">Bearer {token}.</span></span> <span data-ttu-id="40b74-129">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="40b74-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="40b74-130">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="40b74-130">Request body</span></span>
<span data-ttu-id="40b74-131">Leeg</span><span class="sxs-lookup"><span data-stu-id="40b74-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="40b74-132">Antwoord</span><span class="sxs-lookup"><span data-stu-id="40b74-132">Response</span></span>
<span data-ttu-id="40b74-133">Als dit is gelukt, retourneert deze methode 200 OK, met de lijst met beveiligingsproblemen die zijn gekoppeld aan de beveiligingsaanbeveling.</span><span class="sxs-lookup"><span data-stu-id="40b74-133">If successful, this method returns 200 OK, with the list of vulnerabilities associated with the security recommendation.</span></span>


## <a name="example"></a><span data-ttu-id="40b74-134">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="40b74-134">Example</span></span>

<span data-ttu-id="40b74-135">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="40b74-135">**Request**</span></span>

<span data-ttu-id="40b74-136">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="40b74-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/recommendations/va-_-google-_-chrome/vulnerabilities
```

<span data-ttu-id="40b74-137">**Antwoord**</span><span class="sxs-lookup"><span data-stu-id="40b74-137">**Response**</span></span>

<span data-ttu-id="40b74-138">Hier is een voorbeeld van het antwoord.</span><span class="sxs-lookup"><span data-stu-id="40b74-138">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(Analytics.Contracts.PublicAPI.PublicVulnerabilityDto)",
    "value": [
        {
            "id": "CVE-2019-13748",
            "name": "CVE-2019-13748",
            "description": "Insufficient policy enforcement in developer tools in Google Chrome prior to 79.0.3945.79 allowed a local attacker to obtain potentially sensitive information from process memory via a crafted HTML page.",
            "severity": "Medium",
            "cvssV3": 6.5,
            "exposedMachines": 0,
            "publishedOn": "2019-12-10T00:00:00Z",
            "updatedOn": "2019-12-16T12:15:00Z",
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

## <a name="related-topics"></a><span data-ttu-id="40b74-139">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="40b74-139">Related topics</span></span>
- [<span data-ttu-id="40b74-140">Risicogebaseerd bedreigingsbeheer & kwetsbaarheidsbeheer</span><span class="sxs-lookup"><span data-stu-id="40b74-140">Risk-based Threat & Vulnerability Management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="40b74-141">Aanbeveling & beveiligingsaanbeveling voor bedreigingen</span><span class="sxs-lookup"><span data-stu-id="40b74-141">Threat & Vulnerability security recommendation</span></span>](/microsoft-365/security/defender-endpoint/tvm-security-recommendation)
