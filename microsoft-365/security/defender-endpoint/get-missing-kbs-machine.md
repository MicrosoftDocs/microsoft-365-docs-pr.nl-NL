---
title: Ontbrekende KBs op apparaat-id krijgen
description: Haalt ontbrekende beveiligingsupdates op via apparaat-id
keywords: api's, graph api, ondersteunde api's, get, list, file, information, device id, threat & vulnerability management api, mdatp tvm api
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 908ddf531a5a20b9811084ba534a152ad6158170
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198847"
---
# <a name="get-missing-kbs-by-device-id"></a><span data-ttu-id="d0c68-104">Ontbrekende KBs op apparaat-id krijgen</span><span class="sxs-lookup"><span data-stu-id="d0c68-104">Get missing KBs by device ID</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d0c68-105">**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="d0c68-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="d0c68-106">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="d0c68-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d0c68-107">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="d0c68-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="d0c68-108">Hiermee worden ontbrekende KBs (beveiligingsupdates) opgehaald op apparaat-id</span><span class="sxs-lookup"><span data-stu-id="d0c68-108">Retrieves missing KBs (security updates) by device ID</span></span>

## <a name="http-request"></a><span data-ttu-id="d0c68-109">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="d0c68-109">HTTP request</span></span>

```
GET /api/machines/{machineId}/getmissingkbs
```

## <a name="request-header"></a><span data-ttu-id="d0c68-110">Koptekst aanvragen</span><span class="sxs-lookup"><span data-stu-id="d0c68-110">Request header</span></span>

<span data-ttu-id="d0c68-111">Naam</span><span class="sxs-lookup"><span data-stu-id="d0c68-111">Name</span></span> | <span data-ttu-id="d0c68-112">Type</span><span class="sxs-lookup"><span data-stu-id="d0c68-112">Type</span></span> | <span data-ttu-id="d0c68-113">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="d0c68-113">Description</span></span>
:---|:---|:---
<span data-ttu-id="d0c68-114">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="d0c68-114">Authorization</span></span> | <span data-ttu-id="d0c68-115">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="d0c68-115">String</span></span> | <span data-ttu-id="d0c68-116">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="d0c68-116">Bearer {token}.</span></span> <span data-ttu-id="d0c68-117">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="d0c68-117">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="d0c68-118">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="d0c68-118">Request body</span></span>

<span data-ttu-id="d0c68-119">Leeg</span><span class="sxs-lookup"><span data-stu-id="d0c68-119">Empty</span></span>

## <a name="response"></a><span data-ttu-id="d0c68-120">Antwoord</span><span class="sxs-lookup"><span data-stu-id="d0c68-120">Response</span></span>

<span data-ttu-id="d0c68-121">Als dit is gelukt, retourneert deze methode 200 OK, waarbij op het opgegeven apparaat kbgegevens ontbreken in de body.</span><span class="sxs-lookup"><span data-stu-id="d0c68-121">If successful, this method returns 200 OK, with the specified device missing kb data in the body.</span></span>

## <a name="example"></a><span data-ttu-id="d0c68-122">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="d0c68-122">Example</span></span>

### <a name="request"></a><span data-ttu-id="d0c68-123">Aanvraag</span><span class="sxs-lookup"><span data-stu-id="d0c68-123">Request</span></span>

<span data-ttu-id="d0c68-124">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="d0c68-124">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/machines/2339ad14a01bd0299afb93dfa2550136057bff96/getmissingkbs 
```

### <a name="response"></a><span data-ttu-id="d0c68-125">Antwoord</span><span class="sxs-lookup"><span data-stu-id="d0c68-125">Response</span></span>

<span data-ttu-id="d0c68-126">Hier is een voorbeeld van het antwoord.</span><span class="sxs-lookup"><span data-stu-id="d0c68-126">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.PublicProductFixDto)",
    "value": [
        {
            "id": "4540673",
            "name": "March 2020 Security Updates",
            "productsNames": [
                "windows_10",
                "edge",
                "internet_explorer"
            ],
            "url": "https://catalog.update.microsoft.com/v7/site/Search.aspx?q=KB4540673",
            "machineMissedOn": 1,
            "cveAddressed": 97
        },
         ...
        ]
}
```

## <a name="related-topics"></a><span data-ttu-id="d0c68-127">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="d0c68-127">Related topics</span></span>

- [<span data-ttu-id="d0c68-128">Risicogebaseerd bedreigingsbeheer & kwetsbaarheidsbeheer</span><span class="sxs-lookup"><span data-stu-id="d0c68-128">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="d0c68-129">Inventaris van & beveiligingsprobleemsoftware</span><span class="sxs-lookup"><span data-stu-id="d0c68-129">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
