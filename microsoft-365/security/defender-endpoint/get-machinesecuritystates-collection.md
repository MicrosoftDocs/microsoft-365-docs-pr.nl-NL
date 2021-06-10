---
title: Api voor verzamelingen van beveiligingsstaten voor machines ophalen
description: Een verzameling apparaatbeveiligingsstaten ophalen met Microsoft Defender voor Eindpunt.
keywords: api's, graph api, ondersteunde api's, get, apparaat, beveiliging, status
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
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
ms.openlocfilehash: 9dab4bdccc1fead5bc2cc5b9bdff8f2a45b6c8db
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200363"
---
# <a name="get-machines-security-states-collection-api"></a><span data-ttu-id="89385-104">Api voor verzamelingen van beveiligingsstaten van Machines ophalen</span><span class="sxs-lookup"><span data-stu-id="89385-104">Get Machines security states collection API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="89385-105">**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="89385-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="89385-106">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="89385-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="89385-107">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="89385-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="89385-108">Hiermee wordt een verzameling beveiligingsupdates van apparaten opgehaald.</span><span class="sxs-lookup"><span data-stu-id="89385-108">Retrieves a collection of devices security states.</span></span>

## <a name="permissions"></a><span data-ttu-id="89385-109">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="89385-109">Permissions</span></span>
<span data-ttu-id="89385-110">Gebruiker heeft leesmachtigingen nodig.</span><span class="sxs-lookup"><span data-stu-id="89385-110">User needs read permissions.</span></span>

## <a name="http-request"></a><span data-ttu-id="89385-111">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="89385-111">HTTP request</span></span>
```
GET /testwdatppreview/machinesecuritystates
```

## <a name="request-headers"></a><span data-ttu-id="89385-112">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="89385-112">Request headers</span></span>

<span data-ttu-id="89385-113">Koptekst</span><span class="sxs-lookup"><span data-stu-id="89385-113">Header</span></span> | <span data-ttu-id="89385-114">Waarde</span><span class="sxs-lookup"><span data-stu-id="89385-114">Value</span></span> 
:---|:---
<span data-ttu-id="89385-115">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="89385-115">Authorization</span></span> | <span data-ttu-id="89385-116">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="89385-116">Bearer {token}.</span></span> <span data-ttu-id="89385-117">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="89385-117">**Required**.</span></span>
<span data-ttu-id="89385-118">Inhoudstype</span><span class="sxs-lookup"><span data-stu-id="89385-118">Content type</span></span> | <span data-ttu-id="89385-119">toepassing/json</span><span class="sxs-lookup"><span data-stu-id="89385-119">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="89385-120">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="89385-120">Request body</span></span>
<span data-ttu-id="89385-121">Leeg</span><span class="sxs-lookup"><span data-stu-id="89385-121">Empty</span></span>

## <a name="response"></a><span data-ttu-id="89385-122">Antwoord</span><span class="sxs-lookup"><span data-stu-id="89385-122">Response</span></span>
<span data-ttu-id="89385-123">Als dit is gelukt- 200 OK.</span><span class="sxs-lookup"><span data-stu-id="89385-123">If successful - 200 OK.</span></span>

## <a name="example"></a><span data-ttu-id="89385-124">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="89385-124">Example</span></span>

<span data-ttu-id="89385-125">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="89385-125">**Request**</span></span>

<span data-ttu-id="89385-126">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="89385-126">Here is an example of the request.</span></span>

```
GET https://graph.microsoft.com/testwdatppreview/machinesecuritystates
Content-type: application/json
```

<span data-ttu-id="89385-127">**Antwoord**</span><span class="sxs-lookup"><span data-stu-id="89385-127">**Response**</span></span>

<span data-ttu-id="89385-128">Hier is een voorbeeld van het antwoord.</span><span class="sxs-lookup"><span data-stu-id="89385-128">Here is an example of the response.</span></span>
<span data-ttu-id="89385-129">*Veld-id* bevat apparaat-id en gelijk aan de *veld-id*\* in apparaatgegevens.</span><span class="sxs-lookup"><span data-stu-id="89385-129">Field *id* contains device id and equal to the field *id*\* in devices info.</span></span> 

```
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context":"https://graph.microsoft.com/testwdatppreview/$metadata#MachineSecurityStates",
    "@odata.count":444,
    "@odata.nextLink":"https://graph.microsoft.com/testwdatppreview/machinesecuritystates?$skiptoken=[continuation token]",
    "value":[
        {
            "id":"000050e1b4afeee3742489ede9ad7a3e16bbd9c4",
            "build":14393,
            "revision":2485,
            "architecture":"Amd64",
            "osVersion":"10.0.14393.2485.amd64fre.rs1_release.180827-1809",
            "propertiesRequireAttention":[
                "AntivirusNotReporting",
                "EdrImpairedCommunications"
            ]
        },
        …
    ]
}
```
