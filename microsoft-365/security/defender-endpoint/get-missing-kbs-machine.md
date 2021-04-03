---
title: Ontbrekende KBs op apparaat-id krijgen
description: Haalt ontbrekende beveiligingsupdates op via apparaat-id
keywords: api's, graph api, ondersteunde api's, get, list, file, information, device id, threat & vulnerability management api, mdatp tvm api
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
ms.openlocfilehash: 4364e6a38d4597a95d4d9a1f05dcce6fce5797ef
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500694"
---
# <a name="get-missing-kbs-by-device-id"></a><span data-ttu-id="395c6-104">Ontbrekende KBs op apparaat-id krijgen</span><span class="sxs-lookup"><span data-stu-id="395c6-104">Get missing KBs by device ID</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="395c6-105">**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="395c6-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="395c6-106">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="395c6-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="395c6-107">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="395c6-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="395c6-108">Hiermee worden ontbrekende KBs (beveiligingsupdates) opgehaald op apparaat-id</span><span class="sxs-lookup"><span data-stu-id="395c6-108">Retrieves missing KBs (security updates) by device ID</span></span>

## <a name="http-request"></a><span data-ttu-id="395c6-109">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="395c6-109">HTTP request</span></span>

```
GET /api/machines/{machineId}/getmissingkbs
```

## <a name="request-header"></a><span data-ttu-id="395c6-110">Koptekst aanvragen</span><span class="sxs-lookup"><span data-stu-id="395c6-110">Request header</span></span>

<span data-ttu-id="395c6-111">Naam</span><span class="sxs-lookup"><span data-stu-id="395c6-111">Name</span></span> | <span data-ttu-id="395c6-112">Type</span><span class="sxs-lookup"><span data-stu-id="395c6-112">Type</span></span> | <span data-ttu-id="395c6-113">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="395c6-113">Description</span></span>
:---|:---|:---
<span data-ttu-id="395c6-114">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="395c6-114">Authorization</span></span> | <span data-ttu-id="395c6-115">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="395c6-115">String</span></span> | <span data-ttu-id="395c6-116">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="395c6-116">Bearer {token}.</span></span> <span data-ttu-id="395c6-117">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="395c6-117">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="395c6-118">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="395c6-118">Request body</span></span>

<span data-ttu-id="395c6-119">Leeg</span><span class="sxs-lookup"><span data-stu-id="395c6-119">Empty</span></span>

## <a name="response"></a><span data-ttu-id="395c6-120">Antwoord</span><span class="sxs-lookup"><span data-stu-id="395c6-120">Response</span></span>

<span data-ttu-id="395c6-121">Als dit is gelukt, retourneert deze methode 200 OK, waarbij op het opgegeven apparaat kbgegevens ontbreken in de body.</span><span class="sxs-lookup"><span data-stu-id="395c6-121">If successful, this method returns 200 OK, with the specified device missing kb data in the body.</span></span>

## <a name="example"></a><span data-ttu-id="395c6-122">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="395c6-122">Example</span></span>

### <a name="request"></a><span data-ttu-id="395c6-123">Aanvraag</span><span class="sxs-lookup"><span data-stu-id="395c6-123">Request</span></span>

<span data-ttu-id="395c6-124">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="395c6-124">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/machines/2339ad14a01bd0299afb93dfa2550136057bff96/getmissingkbs 
```

### <a name="response"></a><span data-ttu-id="395c6-125">Antwoord</span><span class="sxs-lookup"><span data-stu-id="395c6-125">Response</span></span>

<span data-ttu-id="395c6-126">Hier is een voorbeeld van het antwoord.</span><span class="sxs-lookup"><span data-stu-id="395c6-126">Here is an example of the response.</span></span>


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

## <a name="related-topics"></a><span data-ttu-id="395c6-127">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="395c6-127">Related topics</span></span>

- [<span data-ttu-id="395c6-128">Risicogebaseerd bedreigingsbeheer & kwetsbaarheidsbeheer</span><span class="sxs-lookup"><span data-stu-id="395c6-128">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="395c6-129">Inventaris van & beveiligingsprobleemsoftware</span><span class="sxs-lookup"><span data-stu-id="395c6-129">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
