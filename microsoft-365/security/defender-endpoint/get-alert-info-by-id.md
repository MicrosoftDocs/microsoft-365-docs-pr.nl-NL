---
title: Waarschuwingsgegevens ontvangen via id-API
description: Lees hoe u de meldingsgegevens ophalen per ID-API kunt gebruiken om een specifieke waarschuwing op te halen met de id in Microsoft Defender voor Eindpunt.
keywords: api's, graph api, ondersteunde api's, get, alert, information, id
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
ms.openlocfilehash: b9de7645abc59849b3ca28f64904b0ba49d4eef5
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771895"
---
# <a name="get-alert-information-by-id-api"></a><span data-ttu-id="197df-104">Waarschuwingsgegevens ontvangen via id-API</span><span class="sxs-lookup"><span data-stu-id="197df-104">Get alert information by ID API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="197df-105">**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="197df-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="197df-106">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="197df-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="197df-107">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="197df-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="197df-108">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="197df-108">API description</span></span>
<span data-ttu-id="197df-109">Hiermee wordt een specifieke [waarschuwing opgehaald](alerts.md) op de id.</span><span class="sxs-lookup"><span data-stu-id="197df-109">Retrieves specific [Alert](alerts.md) by its ID.</span></span>


## <a name="limitations"></a><span data-ttu-id="197df-110">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="197df-110">Limitations</span></span>
1. <span data-ttu-id="197df-111">U kunt waarschuwingen ontvangen die het laatst zijn bijgewerkt op basis van de geconfigureerde bewaarperiode.</span><span class="sxs-lookup"><span data-stu-id="197df-111">You can get alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="197df-112">Tariefbeperkingen voor deze API zijn 100 oproepen per minuut en 1500 oproepen per uur.</span><span class="sxs-lookup"><span data-stu-id="197df-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="197df-113">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="197df-113">Permissions</span></span>
<span data-ttu-id="197df-114">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="197df-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="197df-115">Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="197df-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="197df-116">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="197df-116">Permission type</span></span> |   <span data-ttu-id="197df-117">Machtiging</span><span class="sxs-lookup"><span data-stu-id="197df-117">Permission</span></span>  |   <span data-ttu-id="197df-118">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="197df-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="197df-119">Toepassing</span><span class="sxs-lookup"><span data-stu-id="197df-119">Application</span></span> |   <span data-ttu-id="197df-120">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="197df-120">Alert.Read.All</span></span> |    <span data-ttu-id="197df-121">'Alle waarschuwingen lezen'</span><span class="sxs-lookup"><span data-stu-id="197df-121">'Read all alerts'</span></span>
<span data-ttu-id="197df-122">Toepassing</span><span class="sxs-lookup"><span data-stu-id="197df-122">Application</span></span> |   <span data-ttu-id="197df-123">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="197df-123">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="197df-124">'Alle waarschuwingen lezen en schrijven'</span><span class="sxs-lookup"><span data-stu-id="197df-124">'Read and write all alerts'</span></span>
<span data-ttu-id="197df-125">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="197df-125">Delegated (work or school account)</span></span> | <span data-ttu-id="197df-126">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="197df-126">Alert.Read</span></span> | <span data-ttu-id="197df-127">'Leeswaarschuwingen'</span><span class="sxs-lookup"><span data-stu-id="197df-127">'Read alerts'</span></span>
<span data-ttu-id="197df-128">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="197df-128">Delegated (work or school account)</span></span> | <span data-ttu-id="197df-129">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="197df-129">Alert.ReadWrite</span></span> | <span data-ttu-id="197df-130">'Waarschuwingen lezen en schrijven'</span><span class="sxs-lookup"><span data-stu-id="197df-130">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="197df-131">Bij het verkrijgen van een token met gebruikersreferenties:</span><span class="sxs-lookup"><span data-stu-id="197df-131">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="197df-132">De gebruiker moet ten minste de volgende rolmachtiging hebben: 'Gegevens weergeven' [(Zie](user-roles.md) Rollen maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="197df-132">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="197df-133">De gebruiker moet toegang hebben tot het apparaat dat aan de waarschuwing is gekoppeld, op basis van apparaatgroepinstellingen (Zie [Apparaatgroepen](machine-groups.md) maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="197df-133">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="197df-134">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="197df-134">HTTP request</span></span>
```
GET /api/alerts/{id}
```

## <a name="request-headers"></a><span data-ttu-id="197df-135">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="197df-135">Request headers</span></span>

<span data-ttu-id="197df-136">Naam</span><span class="sxs-lookup"><span data-stu-id="197df-136">Name</span></span> | <span data-ttu-id="197df-137">Type</span><span class="sxs-lookup"><span data-stu-id="197df-137">Type</span></span> | <span data-ttu-id="197df-138">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="197df-138">Description</span></span>
:---|:---|:---
<span data-ttu-id="197df-139">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="197df-139">Authorization</span></span> | <span data-ttu-id="197df-140">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="197df-140">String</span></span> | <span data-ttu-id="197df-141">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="197df-141">Bearer {token}.</span></span> <span data-ttu-id="197df-142">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="197df-142">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="197df-143">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="197df-143">Request body</span></span>
<span data-ttu-id="197df-144">Leeg</span><span class="sxs-lookup"><span data-stu-id="197df-144">Empty</span></span>

## <a name="response"></a><span data-ttu-id="197df-145">Antwoord</span><span class="sxs-lookup"><span data-stu-id="197df-145">Response</span></span>
<span data-ttu-id="197df-146">Als dit is gelukt, retourneert deze [](alerts.md) methode 200 OK en de waarschuwingsentiteit in de antwoordinstelling.</span><span class="sxs-lookup"><span data-stu-id="197df-146">If successful, this method returns 200 OK, and the [alert](alerts.md) entity in the response body.</span></span> <span data-ttu-id="197df-147">Als een waarschuwing met de opgegeven id niet is gevonden- 404 Niet gevonden.</span><span class="sxs-lookup"><span data-stu-id="197df-147">If alert with the specified id was not found - 404 Not Found.</span></span>
