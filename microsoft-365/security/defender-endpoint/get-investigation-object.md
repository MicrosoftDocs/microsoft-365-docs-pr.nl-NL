---
title: Object-API voor onderzoek krijgen
description: Gebruik deze API om oproepen te maken die betrekking hebben op het object Onderzoek
keywords: api's, graph api, ondersteunde api's, Onderzoeksobject
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
ms.openlocfilehash: 001b8dcf4b0bfd2550f41454fc840602a6e4361f
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770128"
---
# <a name="get-investigation-api"></a><span data-ttu-id="eec6a-104">Onderzoeks-API krijgen</span><span class="sxs-lookup"><span data-stu-id="eec6a-104">Get Investigation API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="eec6a-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="eec6a-105">**Applies to:**</span></span>
- [<span data-ttu-id="eec6a-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="eec6a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="eec6a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="eec6a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="eec6a-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="eec6a-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="eec6a-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="eec6a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="eec6a-110">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="eec6a-110">API description</span></span>
<span data-ttu-id="eec6a-111">Hiermee wordt specifiek [onderzoek opgehaald](investigation.md) op de id.</span><span class="sxs-lookup"><span data-stu-id="eec6a-111">Retrieves specific [Investigation](investigation.md) by its ID.</span></span>
<br> <span data-ttu-id="eec6a-112">Id kan de onderzoeks-id zijn of het onderzoek dat waarschuwings-id activeert.</span><span class="sxs-lookup"><span data-stu-id="eec6a-112">ID can be the investigation ID or the investigation triggering alert ID.</span></span>


## <a name="limitations"></a><span data-ttu-id="eec6a-113">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="eec6a-113">Limitations</span></span>
1. <span data-ttu-id="eec6a-114">Tariefbeperkingen voor deze API zijn 100 oproepen per minuut en 1500 oproepen per uur.</span><span class="sxs-lookup"><span data-stu-id="eec6a-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="eec6a-115">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="eec6a-115">Permissions</span></span>
<span data-ttu-id="eec6a-116">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="eec6a-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="eec6a-117">Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="eec6a-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="eec6a-118">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="eec6a-118">Permission type</span></span> |   <span data-ttu-id="eec6a-119">Machtiging</span><span class="sxs-lookup"><span data-stu-id="eec6a-119">Permission</span></span>  |   <span data-ttu-id="eec6a-120">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="eec6a-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="eec6a-121">Toepassing</span><span class="sxs-lookup"><span data-stu-id="eec6a-121">Application</span></span> |   <span data-ttu-id="eec6a-122">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="eec6a-122">Alert.Read.All</span></span> |    <span data-ttu-id="eec6a-123">'Alle waarschuwingen lezen'</span><span class="sxs-lookup"><span data-stu-id="eec6a-123">'Read all alerts'</span></span>
<span data-ttu-id="eec6a-124">Toepassing</span><span class="sxs-lookup"><span data-stu-id="eec6a-124">Application</span></span> |   <span data-ttu-id="eec6a-125">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="eec6a-125">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="eec6a-126">'Alle waarschuwingen lezen en schrijven'</span><span class="sxs-lookup"><span data-stu-id="eec6a-126">'Read and write all alerts'</span></span>
<span data-ttu-id="eec6a-127">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="eec6a-127">Delegated (work or school account)</span></span> | <span data-ttu-id="eec6a-128">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="eec6a-128">Alert.Read</span></span> | <span data-ttu-id="eec6a-129">'Leeswaarschuwingen'</span><span class="sxs-lookup"><span data-stu-id="eec6a-129">'Read alerts'</span></span>
<span data-ttu-id="eec6a-130">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="eec6a-130">Delegated (work or school account)</span></span> | <span data-ttu-id="eec6a-131">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="eec6a-131">Alert.ReadWrite</span></span> | <span data-ttu-id="eec6a-132">'Waarschuwingen lezen en schrijven'</span><span class="sxs-lookup"><span data-stu-id="eec6a-132">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="eec6a-133">Bij het verkrijgen van een token met gebruikersreferenties:</span><span class="sxs-lookup"><span data-stu-id="eec6a-133">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="eec6a-134">De gebruiker moet ten minste de volgende rolmachtiging hebben: 'Gegevens weergeven' [(Zie](user-roles.md) Rollen maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="eec6a-134">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="eec6a-135">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="eec6a-135">HTTP request</span></span>
```
GET https://api.securitycenter.microsoft.com/api/investigations/{id}
```

## <a name="request-headers"></a><span data-ttu-id="eec6a-136">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="eec6a-136">Request headers</span></span>

<span data-ttu-id="eec6a-137">Naam</span><span class="sxs-lookup"><span data-stu-id="eec6a-137">Name</span></span> | <span data-ttu-id="eec6a-138">Type</span><span class="sxs-lookup"><span data-stu-id="eec6a-138">Type</span></span> | <span data-ttu-id="eec6a-139">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="eec6a-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="eec6a-140">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="eec6a-140">Authorization</span></span> | <span data-ttu-id="eec6a-141">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="eec6a-141">String</span></span> | <span data-ttu-id="eec6a-142">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="eec6a-142">Bearer {token}.</span></span> <span data-ttu-id="eec6a-143">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="eec6a-143">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="eec6a-144">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="eec6a-144">Request body</span></span>
<span data-ttu-id="eec6a-145">Leeg</span><span class="sxs-lookup"><span data-stu-id="eec6a-145">Empty</span></span>

## <a name="response"></a><span data-ttu-id="eec6a-146">Antwoord</span><span class="sxs-lookup"><span data-stu-id="eec6a-146">Response</span></span>
<span data-ttu-id="eec6a-147">Als dit is gelukt, retourneert deze methode 200, Ok-antwoordcode met een [entiteit Onderzoeken.](investigation.md)</span><span class="sxs-lookup"><span data-stu-id="eec6a-147">If successful, this method returns 200, Ok response code with a [Investigations](investigation.md) entity.</span></span>

