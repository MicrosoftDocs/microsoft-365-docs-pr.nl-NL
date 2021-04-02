---
title: Ontbrekende KBs op software-id
description: Haalt ontbrekende beveiligingsupdates op met software-id
keywords: api's, graph api, ondersteunde api's, get, list, file, information, software-id, threat & vulnerability management api, mdatp tvm api
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: e5d84a3eadab85713779dd70848bc11d27484dcc
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499396"
---
# <a name="get-missing-kbs-by-software-id"></a><span data-ttu-id="20cf6-104">Ontbrekende KBs op software-id</span><span class="sxs-lookup"><span data-stu-id="20cf6-104">Get missing KBs by software ID</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="20cf6-105">**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="20cf6-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="20cf6-106">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="20cf6-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="20cf6-107">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="20cf6-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="20cf6-108">Haalt ontbrekende KBs (beveiligingsupdates) op via software-id</span><span class="sxs-lookup"><span data-stu-id="20cf6-108">Retrieves missing KBs (security updates) by software ID</span></span>

## <a name="permissions"></a><span data-ttu-id="20cf6-109">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="20cf6-109">Permissions</span></span>

<span data-ttu-id="20cf6-110">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="20cf6-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="20cf6-111">Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="20cf6-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="20cf6-112">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="20cf6-112">Permission type</span></span> |   <span data-ttu-id="20cf6-113">Machtiging</span><span class="sxs-lookup"><span data-stu-id="20cf6-113">Permission</span></span>   |   <span data-ttu-id="20cf6-114">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="20cf6-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="20cf6-115">Toepassing</span><span class="sxs-lookup"><span data-stu-id="20cf6-115">Application</span></span> |<span data-ttu-id="20cf6-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="20cf6-116">Software.Read.All</span></span> |   <span data-ttu-id="20cf6-117">'Informatie over bedreigings- en kwetsbaarheidsbeheersoftware lezen'</span><span class="sxs-lookup"><span data-stu-id="20cf6-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="20cf6-118">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="20cf6-118">Delegated (work or school account)</span></span> | <span data-ttu-id="20cf6-119">Software.Lezen</span><span class="sxs-lookup"><span data-stu-id="20cf6-119">Software.Read</span></span> |   <span data-ttu-id="20cf6-120">'Informatie over bedreigings- en kwetsbaarheidsbeheersoftware lezen'</span><span class="sxs-lookup"><span data-stu-id="20cf6-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="20cf6-121">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="20cf6-121">HTTP request</span></span>

```
GET /api/Software/{Id}/getmissingkbs
```

## <a name="request-header"></a><span data-ttu-id="20cf6-122">Koptekst aanvragen</span><span class="sxs-lookup"><span data-stu-id="20cf6-122">Request header</span></span>

<span data-ttu-id="20cf6-123">Naam</span><span class="sxs-lookup"><span data-stu-id="20cf6-123">Name</span></span> | <span data-ttu-id="20cf6-124">Type</span><span class="sxs-lookup"><span data-stu-id="20cf6-124">Type</span></span> | <span data-ttu-id="20cf6-125">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="20cf6-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="20cf6-126">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="20cf6-126">Authorization</span></span> | <span data-ttu-id="20cf6-127">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="20cf6-127">String</span></span> | <span data-ttu-id="20cf6-128">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="20cf6-128">Bearer {token}.</span></span> <span data-ttu-id="20cf6-129">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="20cf6-129">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="20cf6-130">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="20cf6-130">Request body</span></span>

<span data-ttu-id="20cf6-131">Leeg</span><span class="sxs-lookup"><span data-stu-id="20cf6-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="20cf6-132">Antwoord</span><span class="sxs-lookup"><span data-stu-id="20cf6-132">Response</span></span>

<span data-ttu-id="20cf6-133">Als dit is gelukt, retourneert deze methode 200 OK, waarbij de opgegeven software kbgegevens in de body mist.</span><span class="sxs-lookup"><span data-stu-id="20cf6-133">If successful, this method returns 200 OK, with the specified software missing kb data in the body.</span></span>

## <a name="example"></a><span data-ttu-id="20cf6-134">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="20cf6-134">Example</span></span>

### <a name="request"></a><span data-ttu-id="20cf6-135">Aanvraag</span><span class="sxs-lookup"><span data-stu-id="20cf6-135">Request</span></span>

<span data-ttu-id="20cf6-136">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="20cf6-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/getmissingkbs
```

### <a name="response"></a><span data-ttu-id="20cf6-137">Antwoord</span><span class="sxs-lookup"><span data-stu-id="20cf6-137">Response</span></span>

<span data-ttu-id="20cf6-138">Hier is een voorbeeld van het antwoord.</span><span class="sxs-lookup"><span data-stu-id="20cf6-138">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.PublicProductFixDto)",
    "value": [
         {
            "id": "4540673",
            "name": "March 2020 Security Updates",
            "productsNames": [
                "edge"
            ],
            "url": "https://catalog.update.microsoft.com/v7/site/Search.aspx?q=KB4540673",
            "machineMissedOn": 240,
            "cveAddressed": 14
         },
         ...
        ]
}
```

## <a name="related-topics"></a><span data-ttu-id="20cf6-139">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="20cf6-139">Related topics</span></span>

- [<span data-ttu-id="20cf6-140">Risicogebaseerd bedreigingsbeheer & kwetsbaarheidsbeheer</span><span class="sxs-lookup"><span data-stu-id="20cf6-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="20cf6-141">Inventaris van & beveiligingsprobleemsoftware</span><span class="sxs-lookup"><span data-stu-id="20cf6-141">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
