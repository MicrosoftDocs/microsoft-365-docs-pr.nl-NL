---
title: Api voor verzamelingen van RBAC-machinegroepen ophalen
description: Lees hoe u de API van de KB-verzameling ophalen kunt gebruiken om een verzameling RBAC-apparaatgroepen op te halen in Microsoft Defender voor Eindpunt.
keywords: api's, graph api, ondersteunde api's, get, RBAC, groep
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
ms.date: 10/07/2018
ms.openlocfilehash: 18566025d79f02281c1d2c1509dd98f1e57879c2
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932773"
---
# <a name="get-kb-collection-api"></a><span data-ttu-id="c9e0b-104">KB-verzameling-API ophalen</span><span class="sxs-lookup"><span data-stu-id="c9e0b-104">Get KB collection API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="c9e0b-105">**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="c9e0b-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span></span>

- <span data-ttu-id="c9e0b-106">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="c9e0b-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c9e0b-107">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="c9e0b-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="c9e0b-108">Hiermee wordt een verzameling RBAC-apparaatgroepen opgehaald.</span><span class="sxs-lookup"><span data-stu-id="c9e0b-108">Retrieves a collection of RBAC device groups.</span></span>

## <a name="permissions"></a><span data-ttu-id="c9e0b-109">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="c9e0b-109">Permissions</span></span>
<span data-ttu-id="c9e0b-110">Gebruiker heeft leesmachtigingen nodig.</span><span class="sxs-lookup"><span data-stu-id="c9e0b-110">User needs read permissions.</span></span>

## <a name="http-request"></a><span data-ttu-id="c9e0b-111">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="c9e0b-111">HTTP request</span></span>
```
GET /testwdatppreview/machinegroups
```

## <a name="request-headers"></a><span data-ttu-id="c9e0b-112">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="c9e0b-112">Request headers</span></span>

<span data-ttu-id="c9e0b-113">Koptekst</span><span class="sxs-lookup"><span data-stu-id="c9e0b-113">Header</span></span> | <span data-ttu-id="c9e0b-114">Waarde</span><span class="sxs-lookup"><span data-stu-id="c9e0b-114">Value</span></span> 
:---|:---
<span data-ttu-id="c9e0b-115">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="c9e0b-115">Authorization</span></span> | <span data-ttu-id="c9e0b-116">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="c9e0b-116">Bearer {token}.</span></span> <span data-ttu-id="c9e0b-117">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="c9e0b-117">**Required**.</span></span>
<span data-ttu-id="c9e0b-118">Inhoudstype</span><span class="sxs-lookup"><span data-stu-id="c9e0b-118">Content type</span></span> | <span data-ttu-id="c9e0b-119">toepassing/json</span><span class="sxs-lookup"><span data-stu-id="c9e0b-119">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="c9e0b-120">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="c9e0b-120">Request body</span></span>
<span data-ttu-id="c9e0b-121">Leeg</span><span class="sxs-lookup"><span data-stu-id="c9e0b-121">Empty</span></span>

## <a name="response"></a><span data-ttu-id="c9e0b-122">Antwoord</span><span class="sxs-lookup"><span data-stu-id="c9e0b-122">Response</span></span>
<span data-ttu-id="c9e0b-123">Als dit is gelukt- 200 OK.</span><span class="sxs-lookup"><span data-stu-id="c9e0b-123">If successful - 200 OK.</span></span>

## <a name="example"></a><span data-ttu-id="c9e0b-124">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="c9e0b-124">Example</span></span>

<span data-ttu-id="c9e0b-125">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="c9e0b-125">**Request**</span></span>

<span data-ttu-id="c9e0b-126">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="c9e0b-126">Here is an example of the request.</span></span>

```
GET https://graph.microsoft.com/testwdatppreview/machinegroups
Content-type: application/json
```

<span data-ttu-id="c9e0b-127">**Antwoord**</span><span class="sxs-lookup"><span data-stu-id="c9e0b-127">**Response**</span></span>

<span data-ttu-id="c9e0b-128">Hier is een voorbeeld van het antwoord.</span><span class="sxs-lookup"><span data-stu-id="c9e0b-128">Here is an example of the response.</span></span>
<span data-ttu-id="c9e0b-129">Veld-id bevat **apparaatgroep-id** en gelijk aan veld **rbacGroupId** in apparatengegevens.</span><span class="sxs-lookup"><span data-stu-id="c9e0b-129">Field id contains device group **id** and equal to field **rbacGroupId** in devices info.</span></span> <span data-ttu-id="c9e0b-130">Veld **dat niet is gegroepeerd,** geldt slechts voor één groep voor alle apparaten die niet aan een groep zijn toegewezen.</span><span class="sxs-lookup"><span data-stu-id="c9e0b-130">Field **ungrouped** is true only for one group for all devices that have not been assigned to any group.</span></span> <span data-ttu-id="c9e0b-131">Deze groep heeft zoals gewoonlijk de naam 'UnassignedGroup'.</span><span class="sxs-lookup"><span data-stu-id="c9e0b-131">This group as usual has name "UnassignedGroup".</span></span>

```
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context":"https://graph.microsoft.com/testwdatppreview/$metadata#MachineGroups",
    "@odata.count":7,
    "value":[
        {
            "id":86,
            "name":"UnassignedGroup",
            "description":"",
            "ungrouped":true},
        …
}
```
