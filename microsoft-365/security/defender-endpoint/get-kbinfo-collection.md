---
title: KB-verzameling-API ophalen
description: Haal een verzameling kennisbases (KB's) en KB-gegevens op met Microsoft Defender voor Eindpunt.
keywords: api's, graph api, ondersteunde api's, get, kb
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: leonidzh
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ROBOTS: NOINDEX
ms.technology: mde
ms.openlocfilehash: 7becfc4a7246dc32aa244dc96ea423f5d31877f9
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166727"
---
# <a name="get-kb-collection-api"></a><span data-ttu-id="1d0cb-104">KB-verzameling-API ophalen</span><span class="sxs-lookup"><span data-stu-id="1d0cb-104">Get KB collection API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1d0cb-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="1d0cb-105">**Applies to:**</span></span>
- [<span data-ttu-id="1d0cb-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="1d0cb-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1d0cb-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1d0cb-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="1d0cb-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="1d0cb-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1d0cb-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="1d0cb-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="1d0cb-110">Hiermee wordt een verzameling KB-gegevens en KB-gegevens opgehaald.</span><span class="sxs-lookup"><span data-stu-id="1d0cb-110">Retrieves a collection of KB's and KB details.</span></span>

## <a name="permissions"></a><span data-ttu-id="1d0cb-111">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="1d0cb-111">Permissions</span></span>
<span data-ttu-id="1d0cb-112">Gebruiker heeft leesmachtigingen nodig.</span><span class="sxs-lookup"><span data-stu-id="1d0cb-112">User needs read permissions.</span></span>

## <a name="http-request"></a><span data-ttu-id="1d0cb-113">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="1d0cb-113">HTTP request</span></span>
```
GET /testwdatppreview/kbinfo
```

## <a name="request-headers"></a><span data-ttu-id="1d0cb-114">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="1d0cb-114">Request headers</span></span>

<span data-ttu-id="1d0cb-115">Koptekst</span><span class="sxs-lookup"><span data-stu-id="1d0cb-115">Header</span></span> | <span data-ttu-id="1d0cb-116">Waarde</span><span class="sxs-lookup"><span data-stu-id="1d0cb-116">Value</span></span> 
:---|:---
<span data-ttu-id="1d0cb-117">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="1d0cb-117">Authorization</span></span> | <span data-ttu-id="1d0cb-118">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="1d0cb-118">Bearer {token}.</span></span> <span data-ttu-id="1d0cb-119">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="1d0cb-119">**Required**.</span></span>
<span data-ttu-id="1d0cb-120">Inhoudstype</span><span class="sxs-lookup"><span data-stu-id="1d0cb-120">Content type</span></span> | <span data-ttu-id="1d0cb-121">toepassing/json</span><span class="sxs-lookup"><span data-stu-id="1d0cb-121">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="1d0cb-122">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="1d0cb-122">Request body</span></span>
<span data-ttu-id="1d0cb-123">Leeg</span><span class="sxs-lookup"><span data-stu-id="1d0cb-123">Empty</span></span>

## <a name="response"></a><span data-ttu-id="1d0cb-124">Antwoord</span><span class="sxs-lookup"><span data-stu-id="1d0cb-124">Response</span></span>
<span data-ttu-id="1d0cb-125">Als dit is gelukt- 200 OK.</span><span class="sxs-lookup"><span data-stu-id="1d0cb-125">If successful - 200 OK.</span></span>

## <a name="example"></a><span data-ttu-id="1d0cb-126">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="1d0cb-126">Example</span></span>

<span data-ttu-id="1d0cb-127">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="1d0cb-127">**Request**</span></span>

<span data-ttu-id="1d0cb-128">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="1d0cb-128">Here is an example of the request.</span></span>

```http
GET https://graph.microsoft.com/testwdatppreview/KbInfo
```

<span data-ttu-id="1d0cb-129">**Antwoord**</span><span class="sxs-lookup"><span data-stu-id="1d0cb-129">**Response**</span></span>

<span data-ttu-id="1d0cb-130">Hier is een voorbeeld van het antwoord.</span><span class="sxs-lookup"><span data-stu-id="1d0cb-130">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://graph.microsoft.com/testwdatppreview/$metadata#KbInfo",
    "@odata.count": 271,
    "value":[
        {
            "id": "KB3097617 (10240.16549) Amd64",
            "release": "KB3097617 (10240.16549)",
            "publishingDate": "2015-10-16T21:00:00Z",
            "version": "10.0.10240.16549",
            "architecture": "Amd64"
        },
        …
}
```
