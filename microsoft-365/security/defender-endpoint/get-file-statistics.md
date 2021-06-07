---
title: API voor bestandsstatistieken downloaden
description: Lees hoe u de API Bestandsstatistieken ophalen kunt gebruiken om de statistieken voor het opgegeven bestand op te halen in Microsoft Defender voor Eindpunt.
keywords: api's, graph api, ondersteunde api's, get, bestand, statistieken
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
ms.openlocfilehash: 6063d29562be40aed3060e241b52b1a2936aa36d
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770203"
---
# <a name="get-file-statistics-api"></a><span data-ttu-id="c4a73-104">API voor bestandsstatistieken downloaden</span><span class="sxs-lookup"><span data-stu-id="c4a73-104">Get file statistics API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c4a73-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="c4a73-105">**Applies to:**</span></span>
- [<span data-ttu-id="c4a73-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="c4a73-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c4a73-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c4a73-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c4a73-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="c4a73-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c4a73-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="c4a73-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="c4a73-110">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="c4a73-110">API description</span></span>
<span data-ttu-id="c4a73-111">Hiermee worden de statistieken voor het opgegeven bestand opgehaald.</span><span class="sxs-lookup"><span data-stu-id="c4a73-111">Retrieves the statistics for the given file.</span></span>


## <a name="limitations"></a><span data-ttu-id="c4a73-112">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="c4a73-112">Limitations</span></span>
1. <span data-ttu-id="c4a73-113">Tariefbeperkingen voor deze API zijn 100 oproepen per minuut en 1500 oproepen per uur.</span><span class="sxs-lookup"><span data-stu-id="c4a73-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="c4a73-114">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="c4a73-114">Permissions</span></span>
<span data-ttu-id="c4a73-115">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="c4a73-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="c4a73-116">Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="c4a73-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="c4a73-117">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="c4a73-117">Permission type</span></span> |   <span data-ttu-id="c4a73-118">Machtiging</span><span class="sxs-lookup"><span data-stu-id="c4a73-118">Permission</span></span>  |   <span data-ttu-id="c4a73-119">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="c4a73-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="c4a73-120">Toepassing</span><span class="sxs-lookup"><span data-stu-id="c4a73-120">Application</span></span> |   <span data-ttu-id="c4a73-121">File.Read.All</span><span class="sxs-lookup"><span data-stu-id="c4a73-121">File.Read.All</span></span> | <span data-ttu-id="c4a73-122">'Bestandsprofielen lezen'</span><span class="sxs-lookup"><span data-stu-id="c4a73-122">'Read file profiles'</span></span>
<span data-ttu-id="c4a73-123">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="c4a73-123">Delegated (work or school account)</span></span> | <span data-ttu-id="c4a73-124">File.Read.All</span><span class="sxs-lookup"><span data-stu-id="c4a73-124">File.Read.All</span></span> | <span data-ttu-id="c4a73-125">'Bestandsprofielen lezen'</span><span class="sxs-lookup"><span data-stu-id="c4a73-125">'Read file profiles'</span></span>

>[!Note]
> <span data-ttu-id="c4a73-126">Bij het verkrijgen van een token met gebruikersreferenties:</span><span class="sxs-lookup"><span data-stu-id="c4a73-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="c4a73-127">De gebruiker moet ten minste de volgende rolmachtiging hebben: 'Gegevens weergeven' [(Zie](user-roles.md) Rollen maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="c4a73-127">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="c4a73-128">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="c4a73-128">HTTP request</span></span>
```
GET /api/files/{id}/stats
```

## <a name="request-headers"></a><span data-ttu-id="c4a73-129">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="c4a73-129">Request headers</span></span>

<span data-ttu-id="c4a73-130">Naam</span><span class="sxs-lookup"><span data-stu-id="c4a73-130">Name</span></span> | <span data-ttu-id="c4a73-131">Type</span><span class="sxs-lookup"><span data-stu-id="c4a73-131">Type</span></span> | <span data-ttu-id="c4a73-132">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="c4a73-132">Description</span></span>
:---|:---|:---
<span data-ttu-id="c4a73-133">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="c4a73-133">Authorization</span></span> | <span data-ttu-id="c4a73-134">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="c4a73-134">String</span></span> | <span data-ttu-id="c4a73-135">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="c4a73-135">Bearer {token}.</span></span> <span data-ttu-id="c4a73-136">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="c4a73-136">**Required**.</span></span>

## <a name="request-uri-parameters"></a><span data-ttu-id="c4a73-137">URI-parameters aanvragen</span><span class="sxs-lookup"><span data-stu-id="c4a73-137">Request URI parameters</span></span>

<span data-ttu-id="c4a73-138">Naam</span><span class="sxs-lookup"><span data-stu-id="c4a73-138">Name</span></span> | <span data-ttu-id="c4a73-139">Type</span><span class="sxs-lookup"><span data-stu-id="c4a73-139">Type</span></span> | <span data-ttu-id="c4a73-140">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="c4a73-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="c4a73-141">lookBackHours</span><span class="sxs-lookup"><span data-stu-id="c4a73-141">lookBackHours</span></span> | <span data-ttu-id="c4a73-142">Int32</span><span class="sxs-lookup"><span data-stu-id="c4a73-142">Int32</span></span> | <span data-ttu-id="c4a73-143">Definieert de uren die we terug zoeken om de statistieken te krijgen.</span><span class="sxs-lookup"><span data-stu-id="c4a73-143">Defines the hours we search back to get the statistics.</span></span> <span data-ttu-id="c4a73-144">Standaard is dit 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="c4a73-144">Defaults to 30 days.</span></span> <span data-ttu-id="c4a73-145">**Optioneel**.</span><span class="sxs-lookup"><span data-stu-id="c4a73-145">**Optional**.</span></span>

## <a name="request-body"></a><span data-ttu-id="c4a73-146">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="c4a73-146">Request body</span></span>
<span data-ttu-id="c4a73-147">Leeg</span><span class="sxs-lookup"><span data-stu-id="c4a73-147">Empty</span></span>

## <a name="response"></a><span data-ttu-id="c4a73-148">Antwoord</span><span class="sxs-lookup"><span data-stu-id="c4a73-148">Response</span></span>
<span data-ttu-id="c4a73-149">Als dit is gelukt en het bestand bestaat- 200 OK met statistische gegevens in de body.</span><span class="sxs-lookup"><span data-stu-id="c4a73-149">If successful and file exists - 200 OK with statistical data in the body.</span></span> <span data-ttu-id="c4a73-150">Als bestand niet bestaat - 404 Niet gevonden.</span><span class="sxs-lookup"><span data-stu-id="c4a73-150">If file do not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="c4a73-151">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="c4a73-151">Example</span></span>

<span data-ttu-id="c4a73-152">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="c4a73-152">**Request**</span></span>

<span data-ttu-id="c4a73-153">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="c4a73-153">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/files/0991a395da64e1c5fbe8732ed11e6be064081d9f/stats?lookBackHours=48
```

<span data-ttu-id="c4a73-154">**Antwoord**</span><span class="sxs-lookup"><span data-stu-id="c4a73-154">**Response**</span></span>

<span data-ttu-id="c4a73-155">Hier is een voorbeeld van het antwoord.</span><span class="sxs-lookup"><span data-stu-id="c4a73-155">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.InOrgFileStats",
    "sha1": "0991a395da64e1c5fbe8732ed11e6be064081d9f",
    "orgPrevalence": "14850",
    "orgFirstSeen": "2019-12-07T13:44:16Z",
    "orgLastSeen": "2020-01-06T13:39:36Z",
    "globalPrevalence": "705012",
    "globalFirstObserved": "2015-03-19T12:20:07.3432441Z",
    "globalLastObserved": "2020-01-06T13:39:36Z",
    "topFileNames": [
        "MREC.exe"
    ]
}

```
