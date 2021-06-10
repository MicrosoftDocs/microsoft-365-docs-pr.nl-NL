---
title: Geïnstalleerde software ophalen
description: Hiermee wordt een verzameling geïnstalleerde software opgehaald die betrekking heeft op een bepaalde apparaat-id.
keywords: api's, graph api, ondersteunde api's, get, list, file, information, software inventory, installed software per device, threat & vulnerability management api, Microsoft Defender for Endpoint tvm api
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
ms.openlocfilehash: e13e2072ad1c18f3c6bf1abbbe95c95bb519dc3e
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841103"
---
# <a name="get-installed-software"></a><span data-ttu-id="ceef0-104">Geïnstalleerde software ophalen</span><span class="sxs-lookup"><span data-stu-id="ceef0-104">Get installed software</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ceef0-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="ceef0-105">**Applies to:**</span></span>
- [<span data-ttu-id="ceef0-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="ceef0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ceef0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ceef0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="ceef0-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="ceef0-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ceef0-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="ceef0-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="ceef0-110">Hiermee wordt een verzameling geïnstalleerde software opgehaald die betrekking heeft op een bepaalde apparaat-id.</span><span class="sxs-lookup"><span data-stu-id="ceef0-110">Retrieves a collection of installed software related to a given device ID.</span></span>

## <a name="permissions"></a><span data-ttu-id="ceef0-111">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="ceef0-111">Permissions</span></span>
<span data-ttu-id="ceef0-112">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="ceef0-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="ceef0-113">Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="ceef0-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="ceef0-114">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="ceef0-114">Permission type</span></span> |   <span data-ttu-id="ceef0-115">Machtiging</span><span class="sxs-lookup"><span data-stu-id="ceef0-115">Permission</span></span>  |   <span data-ttu-id="ceef0-116">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="ceef0-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="ceef0-117">Toepassing</span><span class="sxs-lookup"><span data-stu-id="ceef0-117">Application</span></span> |<span data-ttu-id="ceef0-118">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="ceef0-118">Software.Read.All</span></span> |    <span data-ttu-id="ceef0-119">'Informatie over bedreigings- en kwetsbaarheidsbeheersoftware lezen'</span><span class="sxs-lookup"><span data-stu-id="ceef0-119">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="ceef0-120">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="ceef0-120">Delegated (work or school account)</span></span> | <span data-ttu-id="ceef0-121">Software.Lezen</span><span class="sxs-lookup"><span data-stu-id="ceef0-121">Software.Read</span></span> |    <span data-ttu-id="ceef0-122">'Informatie over bedreigings- en kwetsbaarheidsbeheersoftware lezen'</span><span class="sxs-lookup"><span data-stu-id="ceef0-122">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="ceef0-123">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="ceef0-123">HTTP request</span></span>
```
GET /api/machines/{machineId}/software
```

## <a name="request-headers"></a><span data-ttu-id="ceef0-124">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="ceef0-124">Request headers</span></span>

<span data-ttu-id="ceef0-125">Naam</span><span class="sxs-lookup"><span data-stu-id="ceef0-125">Name</span></span> | <span data-ttu-id="ceef0-126">Type</span><span class="sxs-lookup"><span data-stu-id="ceef0-126">Type</span></span> | <span data-ttu-id="ceef0-127">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="ceef0-127">Description</span></span>
:---|:---|:---
<span data-ttu-id="ceef0-128">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="ceef0-128">Authorization</span></span> | <span data-ttu-id="ceef0-129">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="ceef0-129">String</span></span> | <span data-ttu-id="ceef0-130">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="ceef0-130">Bearer {token}.</span></span> <span data-ttu-id="ceef0-131">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="ceef0-131">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="ceef0-132">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="ceef0-132">Request body</span></span>
<span data-ttu-id="ceef0-133">Leeg</span><span class="sxs-lookup"><span data-stu-id="ceef0-133">Empty</span></span>

## <a name="response"></a><span data-ttu-id="ceef0-134">Antwoord</span><span class="sxs-lookup"><span data-stu-id="ceef0-134">Response</span></span>
<span data-ttu-id="ceef0-135">Als dit is gelukt, retourneert deze methode 200 OK met de geïnstalleerde softwaregegevens in de body.</span><span class="sxs-lookup"><span data-stu-id="ceef0-135">If successful, this method returns 200 OK with the installed software information in the body.</span></span>


## <a name="example"></a><span data-ttu-id="ceef0-136">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="ceef0-136">Example</span></span>

<span data-ttu-id="ceef0-137">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="ceef0-137">**Request**</span></span>

<span data-ttu-id="ceef0-138">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="ceef0-138">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/ac233fa6208e1579620bf44207c4006ed7cc4501/software
```

<span data-ttu-id="ceef0-139">**Antwoord**</span><span class="sxs-lookup"><span data-stu-id="ceef0-139">**Response**</span></span>

<span data-ttu-id="ceef0-140">Hier is een voorbeeld van het antwoord.</span><span class="sxs-lookup"><span data-stu-id="ceef0-140">Here is an example of the response.</span></span>


```
{
"@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Software",
"value": [
        {
"id": "microsoft-_-internet_explorer",
"name": "internet_explorer",
"vendor": "microsoft",
"weaknesses": 67,
"publicExploit": true,
"activeAlert": false,
"exposedMachines": 42115,
"impactScore": 46.2037163
        }
    ]
}
```

## <a name="see-also"></a><span data-ttu-id="ceef0-141">Zie ook</span><span class="sxs-lookup"><span data-stu-id="ceef0-141">See also</span></span>

- [<span data-ttu-id="ceef0-142">Risicogebaseerd bedreigingsbeheer & kwetsbaarheidsbeheer</span><span class="sxs-lookup"><span data-stu-id="ceef0-142">Risk-based Threat & Vulnerability Management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="ceef0-143">Inventaris van & beveiligingsprobleemsoftware</span><span class="sxs-lookup"><span data-stu-id="ceef0-143">Threat & Vulnerability software inventory</span></span>](/microsoft-365/security/defender-endpoint/tvm-software-inventory)
