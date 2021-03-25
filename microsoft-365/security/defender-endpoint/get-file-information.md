---
title: Api voor bestandsgegevens downloaden
description: Lees hoe u de API Voor bestandsgegevens downloaden kunt gebruiken om een bestand op te halen via Sha1, Sha256 of MD5-id in Microsoft Defender voor Eindpunt.
keywords: api's, graph api, ondersteunde api's, downloaden, bestand, informatie, sha1, sha256, md5
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
ms.technology: mde
ms.openlocfilehash: 181d808b465bfbf26eeff48a564e231b00a9a77f
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166565"
---
# <a name="get-file-information-api"></a><span data-ttu-id="045a7-104">Api voor bestandsgegevens downloaden</span><span class="sxs-lookup"><span data-stu-id="045a7-104">Get file information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="045a7-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="045a7-105">**Applies to:**</span></span>
- [<span data-ttu-id="045a7-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="045a7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="045a7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="045a7-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="045a7-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="045a7-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="045a7-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="045a7-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="045a7-110">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="045a7-110">API description</span></span>
<span data-ttu-id="045a7-111">Haalt een bestand [op id](files.md) Sha1 of Sha256 op</span><span class="sxs-lookup"><span data-stu-id="045a7-111">Retrieves a [File](files.md) by identifier Sha1, or Sha256</span></span>


## <a name="limitations"></a><span data-ttu-id="045a7-112">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="045a7-112">Limitations</span></span>
1. <span data-ttu-id="045a7-113">Tariefbeperkingen voor deze API zijn 100 oproepen per minuut en 1500 oproepen per uur.</span><span class="sxs-lookup"><span data-stu-id="045a7-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="045a7-114">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="045a7-114">Permissions</span></span>
<span data-ttu-id="045a7-115">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="045a7-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="045a7-116">Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="045a7-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="045a7-117">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="045a7-117">Permission type</span></span> |   <span data-ttu-id="045a7-118">Machtiging</span><span class="sxs-lookup"><span data-stu-id="045a7-118">Permission</span></span>  |   <span data-ttu-id="045a7-119">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="045a7-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="045a7-120">Toepassing</span><span class="sxs-lookup"><span data-stu-id="045a7-120">Application</span></span> |   <span data-ttu-id="045a7-121">File.Read.All</span><span class="sxs-lookup"><span data-stu-id="045a7-121">File.Read.All</span></span> | <span data-ttu-id="045a7-122">'Alle bestandsprofielen lezen'</span><span class="sxs-lookup"><span data-stu-id="045a7-122">'Read all file profiles'</span></span>
<span data-ttu-id="045a7-123">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="045a7-123">Delegated (work or school account)</span></span> | <span data-ttu-id="045a7-124">File.Read.All</span><span class="sxs-lookup"><span data-stu-id="045a7-124">File.Read.All</span></span> |    <span data-ttu-id="045a7-125">'Alle bestandsprofielen lezen'</span><span class="sxs-lookup"><span data-stu-id="045a7-125">'Read all file profiles'</span></span>

>[!Note]
> <span data-ttu-id="045a7-126">Bij het verkrijgen van een token met gebruikersreferenties:</span><span class="sxs-lookup"><span data-stu-id="045a7-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="045a7-127">De gebruiker moet ten minste de volgende rolmachtiging hebben: 'Gegevens weergeven' [(Zie](user-roles.md) Rollen maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="045a7-127">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="045a7-128">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="045a7-128">HTTP request</span></span>
```
GET /api/files/{id}
```

## <a name="request-headers"></a><span data-ttu-id="045a7-129">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="045a7-129">Request headers</span></span>

<span data-ttu-id="045a7-130">Naam</span><span class="sxs-lookup"><span data-stu-id="045a7-130">Name</span></span> | <span data-ttu-id="045a7-131">Type</span><span class="sxs-lookup"><span data-stu-id="045a7-131">Type</span></span> | <span data-ttu-id="045a7-132">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="045a7-132">Description</span></span>
:---|:---|:---
<span data-ttu-id="045a7-133">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="045a7-133">Authorization</span></span> | <span data-ttu-id="045a7-134">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="045a7-134">String</span></span> | <span data-ttu-id="045a7-135">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="045a7-135">Bearer {token}.</span></span> <span data-ttu-id="045a7-136">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="045a7-136">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="045a7-137">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="045a7-137">Request body</span></span>
<span data-ttu-id="045a7-138">Leeg</span><span class="sxs-lookup"><span data-stu-id="045a7-138">Empty</span></span>

## <a name="response"></a><span data-ttu-id="045a7-139">Antwoord</span><span class="sxs-lookup"><span data-stu-id="045a7-139">Response</span></span>
<span data-ttu-id="045a7-140">Als dit is gelukt en het bestand bestaat: 200 OK met [de bestandsentiteit](files.md) in de body.</span><span class="sxs-lookup"><span data-stu-id="045a7-140">If successful and file exists - 200 OK with the [file](files.md) entity in the body.</span></span> <span data-ttu-id="045a7-141">Als bestand niet bestaat- 404 Niet gevonden.</span><span class="sxs-lookup"><span data-stu-id="045a7-141">If file does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="045a7-142">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="045a7-142">Example</span></span>

<span data-ttu-id="045a7-143">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="045a7-143">**Request**</span></span>

<span data-ttu-id="045a7-144">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="045a7-144">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/files/4388963aaa83afe2042a46a3c017ad50bdcdafb3
```

<span data-ttu-id="045a7-145">**Antwoord**</span><span class="sxs-lookup"><span data-stu-id="045a7-145">**Response**</span></span>

<span data-ttu-id="045a7-146">Hier is een voorbeeld van het antwoord.</span><span class="sxs-lookup"><span data-stu-id="045a7-146">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Files/$entity",
    "sha1": "4388963aaa83afe2042a46a3c017ad50bdcdafb3",
    "sha256": "413c58c8267d2c8648d8f6384bacc2ae9c929b2b96578b6860b5087cd1bd6462",
    "globalPrevalence": 180022,
    "globalFirstObserved": "2017-09-19T03:51:27.6785431Z",
    "globalLastObserved": "2020-01-06T03:59:21.3229314Z",
    "size": 22139496,
    "fileType": "APP",
    "isPeFile": true,
    "filePublisher": "CHENGDU YIWO Tech Development Co., Ltd.",
    "fileProductName": "EaseUS MobiSaver for Android",
    "signer": "CHENGDU YIWO Tech Development Co., Ltd.",
    "issuer": "VeriSign Class 3 Code Signing 2010 CA",
    "signerHash": "6c3245d4a9bc0244d99dff27af259cbbae2e2d16",
    "isValidCertificate": false,
    "determinationType": "Pua",
    "determinationValue": "PUA:Win32/FusionCore"
}
```
