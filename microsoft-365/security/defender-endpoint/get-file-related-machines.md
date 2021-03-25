---
title: API voor bestandsgerelateerde machines downloaden
description: Meer informatie over het gebruik van de API Voor bestandsgerelateerde machines downloaden voor een verzameling machines die betrekking hebben op een bestandshash in Microsoft Defender voor Eindpunt.
keywords: api's, graph api, ondersteunde api's, get, apparaten, hash
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
ms.openlocfilehash: 051bdad362e142446d248e90fad608fe5c0f016f
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166540"
---
# <a name="get-file-related-machines-api"></a><span data-ttu-id="e79df-104">API voor bestandsgerelateerde machines downloaden</span><span class="sxs-lookup"><span data-stu-id="e79df-104">Get file-related machines API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e79df-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="e79df-105">**Applies to:**</span></span>
- [<span data-ttu-id="e79df-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="e79df-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e79df-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e79df-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="e79df-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="e79df-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e79df-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="e79df-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="e79df-110">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="e79df-110">API description</span></span>
<span data-ttu-id="e79df-111">Hiermee wordt een verzameling [machines opgehaald die betrekking](machine.md) hebben op een bepaalde bestandshash.</span><span class="sxs-lookup"><span data-stu-id="e79df-111">Retrieves a collection of [Machines](machine.md) related to a given file hash.</span></span>


## <a name="limitations"></a><span data-ttu-id="e79df-112">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="e79df-112">Limitations</span></span>
1. <span data-ttu-id="e79df-113">Tariefbeperkingen voor deze API zijn 100 oproepen per minuut en 1500 oproepen per uur.</span><span class="sxs-lookup"><span data-stu-id="e79df-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="e79df-114">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="e79df-114">Permissions</span></span>
<span data-ttu-id="e79df-115">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="e79df-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="e79df-116">Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="e79df-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="e79df-117">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="e79df-117">Permission type</span></span> |   <span data-ttu-id="e79df-118">Machtiging</span><span class="sxs-lookup"><span data-stu-id="e79df-118">Permission</span></span>  |   <span data-ttu-id="e79df-119">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="e79df-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="e79df-120">Toepassing</span><span class="sxs-lookup"><span data-stu-id="e79df-120">Application</span></span> |   <span data-ttu-id="e79df-121">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="e79df-121">Machine.Read.All</span></span> |  <span data-ttu-id="e79df-122">'Alle machineprofielen lezen'</span><span class="sxs-lookup"><span data-stu-id="e79df-122">'Read all machine profiles'</span></span>
<span data-ttu-id="e79df-123">Toepassing</span><span class="sxs-lookup"><span data-stu-id="e79df-123">Application</span></span> |   <span data-ttu-id="e79df-124">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="e79df-124">Machine.ReadWrite.All</span></span> | <span data-ttu-id="e79df-125">'Alle computergegevens lezen en schrijven'</span><span class="sxs-lookup"><span data-stu-id="e79df-125">'Read and write all machine information'</span></span>
<span data-ttu-id="e79df-126">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="e79df-126">Delegated (work or school account)</span></span> | <span data-ttu-id="e79df-127">Machine.Lezen</span><span class="sxs-lookup"><span data-stu-id="e79df-127">Machine.Read</span></span> | <span data-ttu-id="e79df-128">'Machinegegevens lezen'</span><span class="sxs-lookup"><span data-stu-id="e79df-128">'Read machine information'</span></span>
<span data-ttu-id="e79df-129">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="e79df-129">Delegated (work or school account)</span></span> | <span data-ttu-id="e79df-130">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="e79df-130">Machine.ReadWrite</span></span> | <span data-ttu-id="e79df-131">'Machinegegevens lezen en schrijven'</span><span class="sxs-lookup"><span data-stu-id="e79df-131">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="e79df-132">Bij het verkrijgen van een token met gebruikersreferenties:</span><span class="sxs-lookup"><span data-stu-id="e79df-132">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="e79df-133">De gebruiker moet ten minste de volgende rolmachtiging hebben: 'Gegevens weergeven' [(Zie](user-roles.md) Rollen maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="e79df-133">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="e79df-134">Antwoord bevat alleen apparaten, waar de gebruiker toegang toe heeft, op basis van apparaatgroepsinstellingen (Zie [Apparaatgroepen](machine-groups.md) maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="e79df-134">Response will include only devices, that the user have access to, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="e79df-135">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="e79df-135">HTTP request</span></span>
```
GET /api/files/{id}/machines
```

## <a name="request-headers"></a><span data-ttu-id="e79df-136">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="e79df-136">Request headers</span></span>

<span data-ttu-id="e79df-137">Naam</span><span class="sxs-lookup"><span data-stu-id="e79df-137">Name</span></span> | <span data-ttu-id="e79df-138">Type</span><span class="sxs-lookup"><span data-stu-id="e79df-138">Type</span></span> | <span data-ttu-id="e79df-139">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="e79df-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="e79df-140">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="e79df-140">Authorization</span></span> | <span data-ttu-id="e79df-141">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="e79df-141">String</span></span> | <span data-ttu-id="e79df-142">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="e79df-142">Bearer {token}.</span></span> <span data-ttu-id="e79df-143">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="e79df-143">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="e79df-144">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="e79df-144">Request body</span></span>
<span data-ttu-id="e79df-145">Leeg</span><span class="sxs-lookup"><span data-stu-id="e79df-145">Empty</span></span>

## <a name="response"></a><span data-ttu-id="e79df-146">Antwoord</span><span class="sxs-lookup"><span data-stu-id="e79df-146">Response</span></span>
<span data-ttu-id="e79df-147">Als dit is gelukt en het bestand bestaat- 200 OK met een lijst met [machine-entiteiten](machine.md) in de body.</span><span class="sxs-lookup"><span data-stu-id="e79df-147">If successful and file exists - 200 OK with list of [machine](machine.md) entities in the body.</span></span> <span data-ttu-id="e79df-148">Als bestand niet bestaat- 404 Niet gevonden.</span><span class="sxs-lookup"><span data-stu-id="e79df-148">If file does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="e79df-149">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="e79df-149">Example</span></span>

<span data-ttu-id="e79df-150">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="e79df-150">**Request**</span></span>

<span data-ttu-id="e79df-151">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="e79df-151">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/files/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/machines
```
