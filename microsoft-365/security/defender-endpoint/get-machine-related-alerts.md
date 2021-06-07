---
title: Api voor machinegerelateerde waarschuwingen krijgen
description: Lees hoe u de API Voor machinegerelateerde waarschuwingen ophalen gebruikt om alle waarschuwingen op te halen die betrekking hebben op een specifiek apparaat in Microsoft Defender voor Eindpunt.
keywords: api's, graph api, ondersteunde api's, get, apparaten, gerelateerde, waarschuwingen
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: bf445332fed7b8661c510bf60f36088b79e2d8df
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770023"
---
# <a name="get-machine-related-alerts--api"></a><span data-ttu-id="7d817-104">Api voor machinegerelateerde waarschuwingen krijgen</span><span class="sxs-lookup"><span data-stu-id="7d817-104">Get machine related alerts  API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7d817-105">**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="7d817-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="7d817-106">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="7d817-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="7d817-107">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="7d817-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="7d817-108">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="7d817-108">API description</span></span>
<span data-ttu-id="7d817-109">Hiermee worden alle [waarschuwingen opgehaald die](alerts.md) betrekking hebben op een specifiek apparaat.</span><span class="sxs-lookup"><span data-stu-id="7d817-109">Retrieves all [Alerts](alerts.md) related to a specific device.</span></span>


## <a name="limitations"></a><span data-ttu-id="7d817-110">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="7d817-110">Limitations</span></span>
1. <span data-ttu-id="7d817-111">U kunt query's uitvoeren op apparaten die het laatst zijn bijgewerkt op basis van de geconfigureerde bewaarperiode.</span><span class="sxs-lookup"><span data-stu-id="7d817-111">You can query on devices last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="7d817-112">Tariefbeperkingen voor deze API zijn 100 oproepen per minuut en 1500 oproepen per uur.</span><span class="sxs-lookup"><span data-stu-id="7d817-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


<span data-ttu-id="7d817-113">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="7d817-113">Permission type</span></span> |   <span data-ttu-id="7d817-114">Machtiging</span><span class="sxs-lookup"><span data-stu-id="7d817-114">Permission</span></span>  |   <span data-ttu-id="7d817-115">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="7d817-115">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="7d817-116">Toepassing</span><span class="sxs-lookup"><span data-stu-id="7d817-116">Application</span></span> |   <span data-ttu-id="7d817-117">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="7d817-117">Alert.Read.All</span></span> |    <span data-ttu-id="7d817-118">'Alle waarschuwingen lezen'</span><span class="sxs-lookup"><span data-stu-id="7d817-118">'Read all alerts'</span></span>
<span data-ttu-id="7d817-119">Toepassing</span><span class="sxs-lookup"><span data-stu-id="7d817-119">Application</span></span> |   <span data-ttu-id="7d817-120">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="7d817-120">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="7d817-121">'Alle waarschuwingen lezen en schrijven'</span><span class="sxs-lookup"><span data-stu-id="7d817-121">'Read and write all alerts'</span></span>
<span data-ttu-id="7d817-122">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="7d817-122">Delegated (work or school account)</span></span> | <span data-ttu-id="7d817-123">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="7d817-123">Alert.Read</span></span> | <span data-ttu-id="7d817-124">'Leeswaarschuwingen'</span><span class="sxs-lookup"><span data-stu-id="7d817-124">'Read alerts'</span></span>
<span data-ttu-id="7d817-125">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="7d817-125">Delegated (work or school account)</span></span> | <span data-ttu-id="7d817-126">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="7d817-126">Alert.ReadWrite</span></span> | <span data-ttu-id="7d817-127">'Waarschuwingen lezen en schrijven'</span><span class="sxs-lookup"><span data-stu-id="7d817-127">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="7d817-128">Bij het verkrijgen van een token met gebruikersreferenties:</span><span class="sxs-lookup"><span data-stu-id="7d817-128">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="7d817-129">De gebruiker moet ten minste de volgende rolmachtiging hebben: 'Gegevens weergeven' [(Zie](user-roles.md) Rollen maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="7d817-129">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="7d817-130">Gebruiker moet toegang hebben tot het apparaat, op basis van instellingen voor apparaatgroep (Zie [Apparaatgroepen](machine-groups.md) maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="7d817-130">User needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="7d817-131">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="7d817-131">HTTP request</span></span>
```http
GET /api/machines/{id}/alerts
```

## <a name="request-headers"></a><span data-ttu-id="7d817-132">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="7d817-132">Request headers</span></span>

<span data-ttu-id="7d817-133">Naam</span><span class="sxs-lookup"><span data-stu-id="7d817-133">Name</span></span> | <span data-ttu-id="7d817-134">Type</span><span class="sxs-lookup"><span data-stu-id="7d817-134">Type</span></span> | <span data-ttu-id="7d817-135">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="7d817-135">Description</span></span>
:---|:---|:---
<span data-ttu-id="7d817-136">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="7d817-136">Authorization</span></span> | <span data-ttu-id="7d817-137">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7d817-137">String</span></span> | <span data-ttu-id="7d817-138">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="7d817-138">Bearer {token}.</span></span> <span data-ttu-id="7d817-139">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="7d817-139">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="7d817-140">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="7d817-140">Request body</span></span>
<span data-ttu-id="7d817-141">Leeg</span><span class="sxs-lookup"><span data-stu-id="7d817-141">Empty</span></span>

## <a name="response"></a><span data-ttu-id="7d817-142">Antwoord</span><span class="sxs-lookup"><span data-stu-id="7d817-142">Response</span></span>
<span data-ttu-id="7d817-143">Als dit is gelukt en het apparaat [](alerts.md) bestaat- 200 OK met een lijst met waarschuwingsentiteiten in de body.</span><span class="sxs-lookup"><span data-stu-id="7d817-143">If successful and device exists - 200 OK with list of [alert](alerts.md) entities in the body.</span></span> <span data-ttu-id="7d817-144">Als het apparaat niet is gevonden- 404 Niet gevonden.</span><span class="sxs-lookup"><span data-stu-id="7d817-144">If device was not found - 404 Not Found.</span></span>
