---
title: Indicator-API verwijderen.
description: Meer informatie over het gebruik van de INDICATOR-API verwijderen om een indicatorentiteit te verwijderen op id in Microsoft Defender voor Eindpunt.
keywords: api's, openbare api, ondersteunde api's, delete, ti indicator, entiteit, id
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
ms.openlocfilehash: 1305be897dff6932713cf294eb4e5cd53692681c
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166691"
---
# <a name="delete-indicator-api"></a><span data-ttu-id="4329d-104">Indicator-API verwijderen</span><span class="sxs-lookup"><span data-stu-id="4329d-104">Delete Indicator API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4329d-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="4329d-105">**Applies to:**</span></span>
- [<span data-ttu-id="4329d-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="4329d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4329d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4329d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="4329d-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="4329d-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="4329d-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="4329d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)  

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="4329d-110">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="4329d-110">API description</span></span>
<span data-ttu-id="4329d-111">Hiermee verwijdert [](ti-indicator.md) u een indicatorentiteit op id.</span><span class="sxs-lookup"><span data-stu-id="4329d-111">Deletes an [Indicator](ti-indicator.md) entity by ID.</span></span>


## <a name="limitations"></a><span data-ttu-id="4329d-112">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="4329d-112">Limitations</span></span>
1. <span data-ttu-id="4329d-113">Tariefbeperkingen voor deze API zijn 100 oproepen per minuut en 1500 oproepen per uur.</span><span class="sxs-lookup"><span data-stu-id="4329d-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="4329d-114">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="4329d-114">Permissions</span></span>
<span data-ttu-id="4329d-115">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="4329d-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="4329d-116">Zie Aan de slag voor meer informatie, inclusief het kiezen van [machtigingen.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="4329d-116">To learn more, including how to choose permissions, see [Get started](apis-intro.md)</span></span>

<span data-ttu-id="4329d-117">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="4329d-117">Permission type</span></span> |   <span data-ttu-id="4329d-118">Machtiging</span><span class="sxs-lookup"><span data-stu-id="4329d-118">Permission</span></span>  |   <span data-ttu-id="4329d-119">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="4329d-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="4329d-120">Toepassing</span><span class="sxs-lookup"><span data-stu-id="4329d-120">Application</span></span> |   <span data-ttu-id="4329d-121">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="4329d-121">Ti.ReadWrite</span></span> |  <span data-ttu-id="4329d-122">'Ti-indicatoren lezen en schrijven'</span><span class="sxs-lookup"><span data-stu-id="4329d-122">'Read and write TI Indicators'</span></span>
<span data-ttu-id="4329d-123">Toepassing</span><span class="sxs-lookup"><span data-stu-id="4329d-123">Application</span></span> |   <span data-ttu-id="4329d-124">Ti.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="4329d-124">Ti.ReadWrite.All</span></span> |  <span data-ttu-id="4329d-125">'Indicatoren lezen en schrijven'</span><span class="sxs-lookup"><span data-stu-id="4329d-125">'Read and write Indicators'</span></span>


## <a name="http-request"></a><span data-ttu-id="4329d-126">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="4329d-126">HTTP request</span></span>
```
Delete https://api.securitycenter.microsoft.com/api/indicators/{id}
```

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="request-headers"></a><span data-ttu-id="4329d-127">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="4329d-127">Request headers</span></span>

<span data-ttu-id="4329d-128">Naam</span><span class="sxs-lookup"><span data-stu-id="4329d-128">Name</span></span> | <span data-ttu-id="4329d-129">Type</span><span class="sxs-lookup"><span data-stu-id="4329d-129">Type</span></span> | <span data-ttu-id="4329d-130">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="4329d-130">Description</span></span>
:---|:---|:---
<span data-ttu-id="4329d-131">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="4329d-131">Authorization</span></span> | <span data-ttu-id="4329d-132">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4329d-132">String</span></span> | <span data-ttu-id="4329d-133">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="4329d-133">Bearer {token}.</span></span> <span data-ttu-id="4329d-134">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="4329d-134">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="4329d-135">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="4329d-135">Request body</span></span>
<span data-ttu-id="4329d-136">Leeg</span><span class="sxs-lookup"><span data-stu-id="4329d-136">Empty</span></span>

## <a name="response"></a><span data-ttu-id="4329d-137">Antwoord</span><span class="sxs-lookup"><span data-stu-id="4329d-137">Response</span></span>
<span data-ttu-id="4329d-138">Als indicator bestaat en is verwijderd- 204 OK zonder inhoud.</span><span class="sxs-lookup"><span data-stu-id="4329d-138">If Indicator exist and deleted successfully - 204 OK without content.</span></span>
<span data-ttu-id="4329d-139">Als Indicator met de opgegeven id niet is gevonden- 404 Niet gevonden.</span><span class="sxs-lookup"><span data-stu-id="4329d-139">If Indicator with the specified id was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="4329d-140">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="4329d-140">Example</span></span>

<span data-ttu-id="4329d-141">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="4329d-141">**Request**</span></span>

<span data-ttu-id="4329d-142">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="4329d-142">Here is an example of the request.</span></span>

```http
DELETE https://api.securitycenter.microsoft.com/api/indicators/995
```
