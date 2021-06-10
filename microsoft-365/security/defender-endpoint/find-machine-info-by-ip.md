---
title: Apparaatgegevens zoeken via interne IP-API
description: Gebruik deze API om oproepen te maken die betrekking hebben op het vinden van een apparaatinvoer rond een specifieke tijdstempel via interne IP.
keywords: ip, api's, graph api, ondersteunde api's, apparaat zoeken, apparaatgegevens
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: fa1973d1c53048b04c9135a72e55ec4759412b18
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166709"
---
# <a name="find-device-information-by-internal-ip-api"></a><span data-ttu-id="63aa9-104">Apparaatgegevens zoeken via interne IP-API</span><span class="sxs-lookup"><span data-stu-id="63aa9-104">Find device information by internal IP API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="63aa9-105">**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="63aa9-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span></span>

- <span data-ttu-id="63aa9-106">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="63aa9-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="63aa9-107">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="63aa9-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="63aa9-108">Een apparaat zoeken op intern IP-adres.</span><span class="sxs-lookup"><span data-stu-id="63aa9-108">Find a device by internal IP.</span></span>

>[!NOTE]
><span data-ttu-id="63aa9-109">De tijdstempel moet binnen de laatste 30 dagen zijn.</span><span class="sxs-lookup"><span data-stu-id="63aa9-109">The timestamp must be within the last 30 days.</span></span>

## <a name="permissions"></a><span data-ttu-id="63aa9-110">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="63aa9-110">Permissions</span></span>
<span data-ttu-id="63aa9-111">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="63aa9-111">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="63aa9-112">Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="63aa9-112">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="63aa9-113">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="63aa9-113">Permission type</span></span> | <span data-ttu-id="63aa9-114">Machtiging</span><span class="sxs-lookup"><span data-stu-id="63aa9-114">Permission</span></span> | <span data-ttu-id="63aa9-115">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="63aa9-115">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="63aa9-116">Toepassing</span><span class="sxs-lookup"><span data-stu-id="63aa9-116">Application</span></span> | <span data-ttu-id="63aa9-117">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="63aa9-117">Machine.Read.All</span></span> | <span data-ttu-id="63aa9-118">'Alle machineprofielen lezen'</span><span class="sxs-lookup"><span data-stu-id="63aa9-118">'Read all machine profiles'</span></span>
<span data-ttu-id="63aa9-119">Toepassing</span><span class="sxs-lookup"><span data-stu-id="63aa9-119">Application</span></span> | <span data-ttu-id="63aa9-120">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="63aa9-120">Machine.ReadWrite.All</span></span> | <span data-ttu-id="63aa9-121">'Alle computergegevens lezen en schrijven'</span><span class="sxs-lookup"><span data-stu-id="63aa9-121">'Read and write all machine information'</span></span>

## <a name="http-request"></a><span data-ttu-id="63aa9-122">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="63aa9-122">HTTP request</span></span>
```
GET /api/machines/find(timestamp={time},key={IP})
```

## <a name="request-headers"></a><span data-ttu-id="63aa9-123">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="63aa9-123">Request headers</span></span>

<span data-ttu-id="63aa9-124">Naam</span><span class="sxs-lookup"><span data-stu-id="63aa9-124">Name</span></span> | <span data-ttu-id="63aa9-125">Type</span><span class="sxs-lookup"><span data-stu-id="63aa9-125">Type</span></span> | <span data-ttu-id="63aa9-126">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="63aa9-126">Description</span></span>
:---|:---|:---
<span data-ttu-id="63aa9-127">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="63aa9-127">Authorization</span></span> | <span data-ttu-id="63aa9-128">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="63aa9-128">String</span></span> | <span data-ttu-id="63aa9-129">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="63aa9-129">Bearer {token}.</span></span> <span data-ttu-id="63aa9-130">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="63aa9-130">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="63aa9-131">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="63aa9-131">Request body</span></span>
<span data-ttu-id="63aa9-132">Leeg</span><span class="sxs-lookup"><span data-stu-id="63aa9-132">Empty</span></span>

## <a name="response"></a><span data-ttu-id="63aa9-133">Antwoord</span><span class="sxs-lookup"><span data-stu-id="63aa9-133">Response</span></span>
<span data-ttu-id="63aa9-134">Als dit is gelukt en de computer bestaat- 200 OK.</span><span class="sxs-lookup"><span data-stu-id="63aa9-134">If successful and machine exists - 200 OK.</span></span>
<span data-ttu-id="63aa9-135">Als er geen computer is gevonden- 404 Niet gevonden.</span><span class="sxs-lookup"><span data-stu-id="63aa9-135">If no machine found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="63aa9-136">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="63aa9-136">Example</span></span>

<span data-ttu-id="63aa9-137">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="63aa9-137">**Request**</span></span>

<span data-ttu-id="63aa9-138">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="63aa9-138">Here is an example of the request.</span></span>

```
GET https://graph.microsoft.com/testwdatppreview/machines/find(timestamp=2018-06-19T10:00:00Z,key='10.166.93.61')
Content-type: application/json
```

<span data-ttu-id="63aa9-139">**Antwoord**</span><span class="sxs-lookup"><span data-stu-id="63aa9-139">**Response**</span></span>

<span data-ttu-id="63aa9-140">Hier is een voorbeeld van het antwoord.</span><span class="sxs-lookup"><span data-stu-id="63aa9-140">Here is an example of the response.</span></span>

<span data-ttu-id="63aa9-141">Het antwoord retourneerde een lijst met alle apparaten die dit IP-adres binnen zestien minuten vóór en na de tijdstempel hebben gerapporteerd.</span><span class="sxs-lookup"><span data-stu-id="63aa9-141">The response will return a list of all devices that reported this IP address within sixteen minutes prior and after the timestamp.</span></span> 

```
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://graph.microsoft.com/testwdatppreview/$metadata#Machines",
    "value": [
        {
            "id": "04c99d46599f078f1c3da3783cf5b95f01ac61bb",
            "computerDnsName": "",
            "firstSeen": "2017-07-06T01:25:04.9480498Z",
            "osPlatform": "Windows10",
…
}
```
