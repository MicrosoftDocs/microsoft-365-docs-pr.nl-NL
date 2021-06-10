---
title: Informatie over waarschuwingsgerelateerde bestanden downloaden
description: Alle bestanden ophalen die betrekking hebben op een specifieke waarschuwing met Microsoft Defender voor Eindpunt.
keywords: api's, graph api, ondersteunde api's, waarschuwingsinformatie, waarschuwingsgegevens, gerelateerde bestanden
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
ms.openlocfilehash: 369dd35c65094d5a5985b471bec506cb5d266e59
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772347"
---
# <a name="get-alert-related-files-information-api"></a><span data-ttu-id="d741e-104">Api voor waarschuwingsgerelateerde bestanden</span><span class="sxs-lookup"><span data-stu-id="d741e-104">Get alert related files information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d741e-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="d741e-105">**Applies to:**</span></span>
- [<span data-ttu-id="d741e-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="d741e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d741e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d741e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
 
> <span data-ttu-id="d741e-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="d741e-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d741e-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="d741e-109">Sign up for free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="d741e-110">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="d741e-110">API description</span></span>
<span data-ttu-id="d741e-111">Hiermee worden alle bestanden opgehaald die betrekking hebben op een specifieke waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="d741e-111">Retrieves all files related to a specific alert.</span></span>


## <a name="limitations"></a><span data-ttu-id="d741e-112">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="d741e-112">Limitations</span></span>
1. <span data-ttu-id="d741e-113">U kunt query's uitvoeren op waarschuwingen die het laatst zijn bijgewerkt op basis van de geconfigureerde bewaarperiode.</span><span class="sxs-lookup"><span data-stu-id="d741e-113">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="d741e-114">Tariefbeperkingen voor deze API zijn 100 oproepen per minuut en 1500 oproepen per uur.</span><span class="sxs-lookup"><span data-stu-id="d741e-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="d741e-115">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="d741e-115">Permissions</span></span>
<span data-ttu-id="d741e-116">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="d741e-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="d741e-117">Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="d741e-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="d741e-118">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="d741e-118">Permission type</span></span> | <span data-ttu-id="d741e-119">Machtiging</span><span class="sxs-lookup"><span data-stu-id="d741e-119">Permission</span></span> | <span data-ttu-id="d741e-120">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="d741e-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="d741e-121">Toepassing</span><span class="sxs-lookup"><span data-stu-id="d741e-121">Application</span></span> | <span data-ttu-id="d741e-122">File.Read.All</span><span class="sxs-lookup"><span data-stu-id="d741e-122">File.Read.All</span></span> | <span data-ttu-id="d741e-123">'Bestandsprofielen lezen'</span><span class="sxs-lookup"><span data-stu-id="d741e-123">'Read file profiles'</span></span>
<span data-ttu-id="d741e-124">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="d741e-124">Delegated (work or school account)</span></span> | <span data-ttu-id="d741e-125">File.Read.All</span><span class="sxs-lookup"><span data-stu-id="d741e-125">File.Read.All</span></span> | <span data-ttu-id="d741e-126">'Bestandsprofielen lezen'</span><span class="sxs-lookup"><span data-stu-id="d741e-126">'Read file profiles'</span></span>

>[!Note]
> <span data-ttu-id="d741e-127">Bij het verkrijgen van een token met gebruikersreferenties:</span><span class="sxs-lookup"><span data-stu-id="d741e-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="d741e-128">De gebruiker moet ten minste de volgende rolmachtiging hebben: 'Gegevens weergeven' [(Zie](user-roles.md) Rollen maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="d741e-128">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="d741e-129">De gebruiker moet toegang hebben tot het apparaat dat aan de waarschuwing is gekoppeld, op basis van apparaatgroepinstellingen (Zie [Apparaatgroepen](machine-groups.md) maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="d741e-129">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="d741e-130">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="d741e-130">HTTP request</span></span>
```
GET /api/alerts/{id}/files
```

## <a name="request-headers"></a><span data-ttu-id="d741e-131">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="d741e-131">Request headers</span></span>

<span data-ttu-id="d741e-132">Naam</span><span class="sxs-lookup"><span data-stu-id="d741e-132">Name</span></span> | <span data-ttu-id="d741e-133">Type</span><span class="sxs-lookup"><span data-stu-id="d741e-133">Type</span></span> | <span data-ttu-id="d741e-134">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="d741e-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="d741e-135">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="d741e-135">Authorization</span></span> | <span data-ttu-id="d741e-136">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="d741e-136">String</span></span> | <span data-ttu-id="d741e-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="d741e-137">Bearer {token}.</span></span> <span data-ttu-id="d741e-138">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="d741e-138">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="d741e-139">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="d741e-139">Request body</span></span>
<span data-ttu-id="d741e-140">Leeg</span><span class="sxs-lookup"><span data-stu-id="d741e-140">Empty</span></span>

## <a name="response"></a><span data-ttu-id="d741e-141">Antwoord</span><span class="sxs-lookup"><span data-stu-id="d741e-141">Response</span></span>
<span data-ttu-id="d741e-142">Als dit is gelukt en er waarschuwings- en bestanden bestaan- 200 OK.</span><span class="sxs-lookup"><span data-stu-id="d741e-142">If successful and alert and files exist - 200 OK.</span></span> <span data-ttu-id="d741e-143">Als waarschuwing niet is gevonden - 404 Niet gevonden.</span><span class="sxs-lookup"><span data-stu-id="d741e-143">If alert not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="d741e-144">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="d741e-144">Example</span></span>

<span data-ttu-id="d741e-145">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="d741e-145">**Request**</span></span>

<span data-ttu-id="d741e-146">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="d741e-146">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/alerts/636688558380765161_2136280442/files
```

<span data-ttu-id="d741e-147">**Antwoord**</span><span class="sxs-lookup"><span data-stu-id="d741e-147">**Response**</span></span>

<span data-ttu-id="d741e-148">Hier is een voorbeeld van het antwoord.</span><span class="sxs-lookup"><span data-stu-id="d741e-148">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Files",
    "value": [
        {
            "sha1": "f2a00fd2f2de1be0214b8529f1e9f67096c1aa70",
            "sha256": "dcd71ef5fff4362a9f64cf3f96f14f2b11d6f428f3badbedcb9ff3361e7079aa",
            "md5": "8d5b7cc9a832e21d22503057e1fec8e9",
            "globalPrevalence": 29,
            "globalFirstObserved": "2019-03-23T23:54:06.0135204Z",
            "globalLastObserved": "2019-04-23T00:43:20.0489831Z",
            "size": 113984,
            "fileType": null,
            "isPeFile": true,
            "filePublisher": "Microsoft Corporation",
            "fileProductName": "Microsoft� Windows� Operating System",
            "signer": "Microsoft Corporation",
            "issuer": "Microsoft Code Signing PCA",
            "signerHash": "9dc17888b5cfad98b3cb35c1994e96227f061675",
            "isValidCertificate": true,
            "determinationType": "Unknown",
            "determinationValue": null
        }
        ...
    ]
}
```
