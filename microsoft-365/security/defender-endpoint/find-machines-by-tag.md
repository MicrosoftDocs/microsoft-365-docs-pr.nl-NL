---
title: Apparaten zoeken op tag-API
description: Alle apparaten zoeken die specifc-tag bevatten
keywords: api's, ondersteunde api's, get, device, find, find device, by tag, tag
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
ms.openlocfilehash: 88ad63d8b7cc71f7d3f809c7cb0371fc41bb9f5d
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771163"
---
# <a name="find-devices-by-tag-api"></a><span data-ttu-id="bda4d-104">Apparaten zoeken op tag-API</span><span class="sxs-lookup"><span data-stu-id="bda4d-104">Find devices by tag API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="bda4d-105">**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="bda4d-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="bda4d-106">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="bda4d-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="bda4d-107">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="bda4d-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="bda4d-108">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="bda4d-108">API description</span></span>
<span data-ttu-id="bda4d-109">Machines [zoeken](machine.md) op [tag](machine-tags.md).</span><span class="sxs-lookup"><span data-stu-id="bda4d-109">Find [Machines](machine.md) by [Tag](machine-tags.md).</span></span>
<br><span data-ttu-id="bda4d-110">```startswith``` query wordt ondersteund.</span><span class="sxs-lookup"><span data-stu-id="bda4d-110">```startswith``` query is supported.</span></span> 

## <a name="limitations"></a><span data-ttu-id="bda4d-111">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="bda4d-111">Limitations</span></span>
1. <span data-ttu-id="bda4d-112">Tariefbeperkingen voor deze API zijn 100 oproepen per minuut en 1500 oproepen per uur.</span><span class="sxs-lookup"><span data-stu-id="bda4d-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="bda4d-113">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="bda4d-113">Permissions</span></span>
<span data-ttu-id="bda4d-114">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="bda4d-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="bda4d-115">Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="bda4d-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="bda4d-116">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="bda4d-116">Permission type</span></span> |   <span data-ttu-id="bda4d-117">Machtiging</span><span class="sxs-lookup"><span data-stu-id="bda4d-117">Permission</span></span>  |   <span data-ttu-id="bda4d-118">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="bda4d-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="bda4d-119">Toepassing</span><span class="sxs-lookup"><span data-stu-id="bda4d-119">Application</span></span> |   <span data-ttu-id="bda4d-120">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="bda4d-120">Machine.Read.All</span></span> |  <span data-ttu-id="bda4d-121">'Alle machineprofielen lezen'</span><span class="sxs-lookup"><span data-stu-id="bda4d-121">'Read all machine profiles'</span></span>
<span data-ttu-id="bda4d-122">Toepassing</span><span class="sxs-lookup"><span data-stu-id="bda4d-122">Application</span></span> |   <span data-ttu-id="bda4d-123">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="bda4d-123">Machine.ReadWrite.All</span></span> | <span data-ttu-id="bda4d-124">'Alle computergegevens lezen en schrijven'</span><span class="sxs-lookup"><span data-stu-id="bda4d-124">'Read and write all machine information'</span></span>
<span data-ttu-id="bda4d-125">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="bda4d-125">Delegated (work or school account)</span></span> | <span data-ttu-id="bda4d-126">Machine.Lezen</span><span class="sxs-lookup"><span data-stu-id="bda4d-126">Machine.Read</span></span> | <span data-ttu-id="bda4d-127">'Machinegegevens lezen'</span><span class="sxs-lookup"><span data-stu-id="bda4d-127">'Read machine information'</span></span>
<span data-ttu-id="bda4d-128">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="bda4d-128">Delegated (work or school account)</span></span> | <span data-ttu-id="bda4d-129">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="bda4d-129">Machine.ReadWrite</span></span> | <span data-ttu-id="bda4d-130">'Machinegegevens lezen en schrijven'</span><span class="sxs-lookup"><span data-stu-id="bda4d-130">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="bda4d-131">Bij het verkrijgen van een token met gebruikersreferenties:</span><span class="sxs-lookup"><span data-stu-id="bda4d-131">When obtaining a token using user credentials:</span></span>
> - <span data-ttu-id="bda4d-132">Antwoord bevat alleen apparaten tot wie de gebruiker toegang heeft op basis van instellingen voor apparaatgroepen (Zie [Apparaatgroepen](machine-groups.md) maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="bda4d-132">Response will include only devices that the user have access to based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>
> - <span data-ttu-id="bda4d-133">De gebruiker moet ten minste de volgende rolmachtiging hebben: 'Gegevens weergeven' [(Zie](user-roles.md) Rollen maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="bda4d-133">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
> - <span data-ttu-id="bda4d-134">Antwoord bevat alleen apparaten tot wie de gebruiker toegang heeft op basis van instellingen voor apparaatgroepen (Zie [Apparaatgroepen](machine-groups.md) maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="bda4d-134">Response will include only devices that the user have access to based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="bda4d-135">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="bda4d-135">HTTP request</span></span>
```
GET /api/machines/findbytag?tag={tag}&useStartsWithFilter={true/false}
```

## <a name="request-headers"></a><span data-ttu-id="bda4d-136">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="bda4d-136">Request headers</span></span>

<span data-ttu-id="bda4d-137">Naam</span><span class="sxs-lookup"><span data-stu-id="bda4d-137">Name</span></span> | <span data-ttu-id="bda4d-138">Type</span><span class="sxs-lookup"><span data-stu-id="bda4d-138">Type</span></span> | <span data-ttu-id="bda4d-139">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="bda4d-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="bda4d-140">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="bda4d-140">Authorization</span></span> | <span data-ttu-id="bda4d-141">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bda4d-141">String</span></span> | <span data-ttu-id="bda4d-142">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="bda4d-142">Bearer {token}.</span></span> <span data-ttu-id="bda4d-143">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="bda4d-143">**Required**.</span></span>

## <a name="request-uri-parameters"></a><span data-ttu-id="bda4d-144">URI-parameters aanvragen</span><span class="sxs-lookup"><span data-stu-id="bda4d-144">Request URI parameters</span></span>

<span data-ttu-id="bda4d-145">Naam</span><span class="sxs-lookup"><span data-stu-id="bda4d-145">Name</span></span> | <span data-ttu-id="bda4d-146">Type</span><span class="sxs-lookup"><span data-stu-id="bda4d-146">Type</span></span> | <span data-ttu-id="bda4d-147">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="bda4d-147">Description</span></span>
:---|:---|:---
<span data-ttu-id="bda4d-148">tag</span><span class="sxs-lookup"><span data-stu-id="bda4d-148">tag</span></span> | <span data-ttu-id="bda4d-149">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bda4d-149">String</span></span> | <span data-ttu-id="bda4d-150">De naam van de tag.</span><span class="sxs-lookup"><span data-stu-id="bda4d-150">The tag name.</span></span> <span data-ttu-id="bda4d-151">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="bda4d-151">**Required**.</span></span>
<span data-ttu-id="bda4d-152">useStartsWithFilter</span><span class="sxs-lookup"><span data-stu-id="bda4d-152">useStartsWithFilter</span></span> | <span data-ttu-id="bda4d-153">Booleaanse waarde</span><span class="sxs-lookup"><span data-stu-id="bda4d-153">Boolean</span></span> | <span data-ttu-id="bda4d-154">Wanneer de zoekopdracht is ingesteld op waar, worden alle apparaten met de naam van de tag gevonden die beginnen met de opgegeven tag in de query.</span><span class="sxs-lookup"><span data-stu-id="bda4d-154">When set to true, the search will find all devices with tag name that starts with the given tag in the query.</span></span> <span data-ttu-id="bda4d-155">Standaardwaarden voor onwaar.</span><span class="sxs-lookup"><span data-stu-id="bda4d-155">Defaults to false.</span></span> <span data-ttu-id="bda4d-156">**Optioneel**.</span><span class="sxs-lookup"><span data-stu-id="bda4d-156">**Optional**.</span></span>

## <a name="request-body"></a><span data-ttu-id="bda4d-157">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="bda4d-157">Request body</span></span>
<span data-ttu-id="bda4d-158">Leeg</span><span class="sxs-lookup"><span data-stu-id="bda4d-158">Empty</span></span>

## <a name="response"></a><span data-ttu-id="bda4d-159">Antwoord</span><span class="sxs-lookup"><span data-stu-id="bda4d-159">Response</span></span>
<span data-ttu-id="bda4d-160">Als dit is gelukt- 200 OK met de lijst met de machines in de antwoord body.</span><span class="sxs-lookup"><span data-stu-id="bda4d-160">If successful - 200 OK with list of the machines in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="bda4d-161">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="bda4d-161">Example</span></span>

<span data-ttu-id="bda4d-162">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="bda4d-162">**Request**</span></span>

<span data-ttu-id="bda4d-163">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="bda4d-163">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/findbytag?tag=testTag&useStartsWithFilter=true
```