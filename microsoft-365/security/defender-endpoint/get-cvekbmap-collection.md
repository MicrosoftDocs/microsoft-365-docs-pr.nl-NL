---
title: CVE-KB-map-API krijgen
description: Meer informatie over het gebruik van de MAP-API VOOR CVE-KB ophalen om een kaart van CVE's op te halen naar KB-gegevens en CVE-gegevens in Microsoft Defender voor Eindpunt.
keywords: api's, graph api, ondersteunde api's, get, cve, kb
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
ms.openlocfilehash: 85c4d82f07354193fb1e997abb98dbdaa02dc8ef
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166583"
---
# <a name="get-cve-kb-map-api"></a><span data-ttu-id="d771e-104">CVE-KB-map-API krijgen</span><span class="sxs-lookup"><span data-stu-id="d771e-104">Get CVE-KB map API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d771e-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="d771e-105">**Applies to:**</span></span>
- [<span data-ttu-id="d771e-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="d771e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d771e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d771e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="d771e-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="d771e-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d771e-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="d771e-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="d771e-110">Hiermee wordt een kaart met CVE's naar KB-gegevens en CVE-gegevens opgehaald.</span><span class="sxs-lookup"><span data-stu-id="d771e-110">Retrieves a map of CVE's to KB's and CVE details.</span></span>

## <a name="permissions"></a><span data-ttu-id="d771e-111">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="d771e-111">Permissions</span></span>
<span data-ttu-id="d771e-112">Gebruiker heeft leesmachtigingen nodig.</span><span class="sxs-lookup"><span data-stu-id="d771e-112">User needs read permissions.</span></span>

## <a name="http-request"></a><span data-ttu-id="d771e-113">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="d771e-113">HTTP request</span></span>
```
GET /testwdatppreview/cvekbmap
```

## <a name="request-headers"></a><span data-ttu-id="d771e-114">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="d771e-114">Request headers</span></span>

<span data-ttu-id="d771e-115">Koptekst</span><span class="sxs-lookup"><span data-stu-id="d771e-115">Header</span></span> | <span data-ttu-id="d771e-116">Waarde</span><span class="sxs-lookup"><span data-stu-id="d771e-116">Value</span></span> 
:---|:---
<span data-ttu-id="d771e-117">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="d771e-117">Authorization</span></span> | <span data-ttu-id="d771e-118">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="d771e-118">Bearer {token}.</span></span> <span data-ttu-id="d771e-119">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="d771e-119">**Required**.</span></span>
<span data-ttu-id="d771e-120">Inhoudstype</span><span class="sxs-lookup"><span data-stu-id="d771e-120">Content type</span></span> | <span data-ttu-id="d771e-121">toepassing/json</span><span class="sxs-lookup"><span data-stu-id="d771e-121">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="d771e-122">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="d771e-122">Request body</span></span>
<span data-ttu-id="d771e-123">Leeg</span><span class="sxs-lookup"><span data-stu-id="d771e-123">Empty</span></span>

## <a name="response"></a><span data-ttu-id="d771e-124">Antwoord</span><span class="sxs-lookup"><span data-stu-id="d771e-124">Response</span></span>
<span data-ttu-id="d771e-125">Als dit is gelukt en de kaart bestaat- 200 OK.</span><span class="sxs-lookup"><span data-stu-id="d771e-125">If successful and map exists - 200 OK.</span></span>

## <a name="example"></a><span data-ttu-id="d771e-126">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="d771e-126">Example</span></span>

<span data-ttu-id="d771e-127">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="d771e-127">**Request**</span></span>

<span data-ttu-id="d771e-128">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="d771e-128">Here is an example of the request.</span></span>

```http
GET https://graph.microsoft.com/testwdatppreview/CveKbMap
```

<span data-ttu-id="d771e-129">**Antwoord**</span><span class="sxs-lookup"><span data-stu-id="d771e-129">**Response**</span></span>

<span data-ttu-id="d771e-130">Hier is een voorbeeld van het antwoord.</span><span class="sxs-lookup"><span data-stu-id="d771e-130">Here is an example of the response.</span></span>

```json
{
    "@odata.context":"https://graph.microsoft.com/testwdatppreview/$metadata#CveKbMap",
    "@odata.count": 4168,
    "value": [
        {
            "cveKbId": "CVE-2015-2482-3097617",
            "cveId": "CVE-2015-2482",
            "kbId":"3097617",
            "title": "Cumulative Security Update for Internet Explorer",
            "severity": "Critical"
        },
    …
}

```
