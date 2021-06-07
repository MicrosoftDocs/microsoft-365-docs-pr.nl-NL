---
title: Informatie over waarschuwingsgerelateerde machines
description: Haal alle apparaten op die betrekking hebben op een specifieke waarschuwing met Microsoft Defender voor Eindpunt.
keywords: api's, graph api, ondersteunde api's, waarschuwingsinformatie, waarschuwingsinformatie, gerelateerd apparaat
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: ef10d2bd7193fc7b4a1604658f496ef38ef33555
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772339"
---
# <a name="get-alert-related-machine-information-api"></a><span data-ttu-id="876dd-104">Api voor waarschuwingsgerelateerde computergegevens</span><span class="sxs-lookup"><span data-stu-id="876dd-104">Get alert related machine information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="876dd-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="876dd-105">**Applies to:**</span></span>
- [<span data-ttu-id="876dd-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="876dd-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="876dd-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="876dd-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="876dd-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="876dd-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="876dd-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="876dd-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="876dd-110">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="876dd-110">API description</span></span>
<span data-ttu-id="876dd-111">Hiermee wordt [apparaat opgehaald](machine.md) dat is gerelateerd aan een specifieke waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="876dd-111">Retrieves [Device](machine.md) related to a specific alert.</span></span>


## <a name="limitations"></a><span data-ttu-id="876dd-112">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="876dd-112">Limitations</span></span>
1. <span data-ttu-id="876dd-113">U kunt query's uitvoeren op waarschuwingen die het laatst zijn bijgewerkt op basis van de geconfigureerde bewaarperiode.</span><span class="sxs-lookup"><span data-stu-id="876dd-113">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="876dd-114">Tariefbeperkingen voor deze API zijn 100 oproepen per minuut en 1500 oproepen per uur.</span><span class="sxs-lookup"><span data-stu-id="876dd-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="876dd-115">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="876dd-115">Permissions</span></span>
<span data-ttu-id="876dd-116">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="876dd-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="876dd-117">Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="876dd-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="876dd-118">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="876dd-118">Permission type</span></span> |   <span data-ttu-id="876dd-119">Machtiging</span><span class="sxs-lookup"><span data-stu-id="876dd-119">Permission</span></span>  |   <span data-ttu-id="876dd-120">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="876dd-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="876dd-121">Toepassing</span><span class="sxs-lookup"><span data-stu-id="876dd-121">Application</span></span> |   <span data-ttu-id="876dd-122">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="876dd-122">Machine.Read.All</span></span> |  <span data-ttu-id="876dd-123">'Alle computergegevens lezen'</span><span class="sxs-lookup"><span data-stu-id="876dd-123">'Read all machine information'</span></span>
<span data-ttu-id="876dd-124">Toepassing</span><span class="sxs-lookup"><span data-stu-id="876dd-124">Application</span></span> |   <span data-ttu-id="876dd-125">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="876dd-125">Machine.ReadWrite.All</span></span> | <span data-ttu-id="876dd-126">'Alle computergegevens lezen en schrijven'</span><span class="sxs-lookup"><span data-stu-id="876dd-126">'Read and write all machine information'</span></span>
<span data-ttu-id="876dd-127">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="876dd-127">Delegated (work or school account)</span></span> | <span data-ttu-id="876dd-128">Machine.Lezen</span><span class="sxs-lookup"><span data-stu-id="876dd-128">Machine.Read</span></span> | <span data-ttu-id="876dd-129">'Machinegegevens lezen'</span><span class="sxs-lookup"><span data-stu-id="876dd-129">'Read machine information'</span></span>
<span data-ttu-id="876dd-130">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="876dd-130">Delegated (work or school account)</span></span> | <span data-ttu-id="876dd-131">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="876dd-131">Machine.ReadWrite</span></span> | <span data-ttu-id="876dd-132">'Machinegegevens lezen en schrijven'</span><span class="sxs-lookup"><span data-stu-id="876dd-132">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="876dd-133">Bij het verkrijgen van een token met gebruikersreferenties:</span><span class="sxs-lookup"><span data-stu-id="876dd-133">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="876dd-134">De gebruiker moet ten minste de volgende rolmachtiging hebben: 'Gegevens weergeven' [(Zie](user-roles.md) Rollen maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="876dd-134">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="876dd-135">De gebruiker moet toegang hebben tot het apparaat dat aan de waarschuwing is gekoppeld, op basis van apparaatgroepinstellingen (Zie [Apparaatgroepen](machine-groups.md) maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="876dd-135">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="876dd-136">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="876dd-136">HTTP request</span></span>

```http
GET /api/alerts/{id}/machine
```

## <a name="request-headers"></a><span data-ttu-id="876dd-137">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="876dd-137">Request headers</span></span>

<span data-ttu-id="876dd-138">Naam</span><span class="sxs-lookup"><span data-stu-id="876dd-138">Name</span></span> | <span data-ttu-id="876dd-139">Type</span><span class="sxs-lookup"><span data-stu-id="876dd-139">Type</span></span> | <span data-ttu-id="876dd-140">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="876dd-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="876dd-141">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="876dd-141">Authorization</span></span> | <span data-ttu-id="876dd-142">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="876dd-142">String</span></span> | <span data-ttu-id="876dd-143">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="876dd-143">Bearer {token}.</span></span> <span data-ttu-id="876dd-144">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="876dd-144">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="876dd-145">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="876dd-145">Request body</span></span>
<span data-ttu-id="876dd-146">Leeg</span><span class="sxs-lookup"><span data-stu-id="876dd-146">Empty</span></span>

## <a name="response"></a><span data-ttu-id="876dd-147">Antwoord</span><span class="sxs-lookup"><span data-stu-id="876dd-147">Response</span></span>
<span data-ttu-id="876dd-148">Als dit is gelukt en een waarschuwing en een apparaat aanwezig zijn, is dit 200 OK.</span><span class="sxs-lookup"><span data-stu-id="876dd-148">If successful and alert and device exist - 200 OK.</span></span> <span data-ttu-id="876dd-149">Als een waarschuwing niet is gevonden of het apparaat niet is gevonden- 404 Niet gevonden.</span><span class="sxs-lookup"><span data-stu-id="876dd-149">If alert not found or device not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="876dd-150">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="876dd-150">Example</span></span>

<span data-ttu-id="876dd-151">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="876dd-151">**Request**</span></span>

<span data-ttu-id="876dd-152">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="876dd-152">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/alerts/636688558380765161_2136280442/machine
```

<span data-ttu-id="876dd-153">**Antwoord**</span><span class="sxs-lookup"><span data-stu-id="876dd-153">**Response**</span></span>

<span data-ttu-id="876dd-154">Hier is een voorbeeld van het antwoord.</span><span class="sxs-lookup"><span data-stu-id="876dd-154">Here is an example of the response.</span></span>


```json
{
    "id": "1e5bc9d7e413ddd7902c2932e418702b84d0cc07",
    "computerDnsName": "mymachine1.contoso.com",
    "firstSeen": "2018-08-02T14:55:03.7791856Z",
    "lastSeen": "2021-01-25T07:27:36.052313Z",
    "osPlatform": "Windows10",
    "osProcessor": "x64",
    "version": "1901",
    "lastIpAddress": "10.166.113.46",
    "lastExternalIpAddress": "167.220.203.175",
    "osBuild": 19042,
    "healthStatus": "Active",
    "deviceValue": "Normal",
    "rbacGroupName": "The-A-Team",
    "riskScore": "Low",
    "exposureLevel": "Low",
    "aadDeviceId": "fd2e4d29-7072-4195-aaa5-1af139b78028",
    "machineTags": [
        "Tag1",
        "Tag2"
    ],
    "ipAddresses": [
        {
            "ipAddress": "10.166.113.47",
            "macAddress": "8CEC4B897E73",
            "operationalStatus": "Up"
        },
        {
            "ipAddress": "2a01:110:68:4:59e4:3916:3b3e:4f96",
            "macAddress": "8CEC4B897E73",
            "operationalStatus": "Up"
        }
    ]
}
```
