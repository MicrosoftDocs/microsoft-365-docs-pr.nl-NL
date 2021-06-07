---
title: API voor domeingerelateerde machines krijgen
description: Meer informatie over het gebruik van de API Voor domeingerelateerde machines krijgen om machines te krijgen die communiceren met of van een domein in Microsoft Defender voor Eindpunt.
keywords: api's, graph api, ondersteunde api's, get, domein, gerelateerde, apparaten
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
ms.openlocfilehash: 362e3db0ed89924c58fa9662f7acbbe0c16c37c6
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772219"
---
# <a name="get-domain-related-machines-api"></a><span data-ttu-id="5b4b0-104">API voor domeingerelateerde machines krijgen</span><span class="sxs-lookup"><span data-stu-id="5b4b0-104">Get domain related machines API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5b4b0-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="5b4b0-105">**Applies to:**</span></span>
- [<span data-ttu-id="5b4b0-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="5b4b0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5b4b0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5b4b0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="5b4b0-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="5b4b0-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5b4b0-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="5b4b0-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="5b4b0-110">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="5b4b0-110">API description</span></span>
<span data-ttu-id="5b4b0-111">Hiermee wordt een verzameling [machines opgehaald die](machine.md) zijn gecommuniceerd naar of van een bepaald domeinadres.</span><span class="sxs-lookup"><span data-stu-id="5b4b0-111">Retrieves a collection of [Machines](machine.md) that have communicated to or from a given domain address.</span></span>


## <a name="limitations"></a><span data-ttu-id="5b4b0-112">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="5b4b0-112">Limitations</span></span>
1. <span data-ttu-id="5b4b0-113">U kunt query's uitvoeren op apparaten die het laatst zijn bijgewerkt op basis van de geconfigureerde bewaarperiode.</span><span class="sxs-lookup"><span data-stu-id="5b4b0-113">You can query on devices last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="5b4b0-114">Tariefbeperkingen voor deze API zijn 100 oproepen per minuut en 1500 oproepen per uur.</span><span class="sxs-lookup"><span data-stu-id="5b4b0-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="5b4b0-115">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="5b4b0-115">Permissions</span></span>
<span data-ttu-id="5b4b0-116">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="5b4b0-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="5b4b0-117">Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="5b4b0-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="5b4b0-118">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="5b4b0-118">Permission type</span></span> |   <span data-ttu-id="5b4b0-119">Machtiging</span><span class="sxs-lookup"><span data-stu-id="5b4b0-119">Permission</span></span>  |   <span data-ttu-id="5b4b0-120">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="5b4b0-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="5b4b0-121">Toepassing</span><span class="sxs-lookup"><span data-stu-id="5b4b0-121">Application</span></span> |   <span data-ttu-id="5b4b0-122">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="5b4b0-122">Machine.Read.All</span></span> |  <span data-ttu-id="5b4b0-123">'Alle machineprofielen lezen'</span><span class="sxs-lookup"><span data-stu-id="5b4b0-123">'Read all machine profiles'</span></span>
<span data-ttu-id="5b4b0-124">Toepassing</span><span class="sxs-lookup"><span data-stu-id="5b4b0-124">Application</span></span> |   <span data-ttu-id="5b4b0-125">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="5b4b0-125">Machine.ReadWrite.All</span></span> | <span data-ttu-id="5b4b0-126">'Alle computergegevens lezen en schrijven'</span><span class="sxs-lookup"><span data-stu-id="5b4b0-126">'Read and write all machine information'</span></span>
<span data-ttu-id="5b4b0-127">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="5b4b0-127">Delegated (work or school account)</span></span> | <span data-ttu-id="5b4b0-128">Machine.Lezen</span><span class="sxs-lookup"><span data-stu-id="5b4b0-128">Machine.Read</span></span> | <span data-ttu-id="5b4b0-129">'Machinegegevens lezen'</span><span class="sxs-lookup"><span data-stu-id="5b4b0-129">'Read machine information'</span></span>
<span data-ttu-id="5b4b0-130">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="5b4b0-130">Delegated (work or school account)</span></span> | <span data-ttu-id="5b4b0-131">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="5b4b0-131">Machine.ReadWrite</span></span> | <span data-ttu-id="5b4b0-132">'Machinegegevens lezen en schrijven'</span><span class="sxs-lookup"><span data-stu-id="5b4b0-132">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="5b4b0-133">Bij het verkrijgen van een token met gebruikersreferenties:</span><span class="sxs-lookup"><span data-stu-id="5b4b0-133">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="5b4b0-134">De gebruiker moet ten minste de volgende rolmachtiging hebben: 'Gegevens weergeven' [(Zie](user-roles.md) Rollen maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="5b4b0-134">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="5b4b0-135">Antwoord bevat alleen apparaten die de gebruiker kan openen op basis van apparaatgroepinstellingen (Zie [Apparaatgroepen](machine-groups.md) maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="5b4b0-135">Response will include only devices that the user can access, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="5b4b0-136">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="5b4b0-136">HTTP request</span></span>
```http
GET /api/domains/{domain}/machines
```

## <a name="request-headers"></a><span data-ttu-id="5b4b0-137">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="5b4b0-137">Request headers</span></span>

<span data-ttu-id="5b4b0-138">Naam</span><span class="sxs-lookup"><span data-stu-id="5b4b0-138">Name</span></span> | <span data-ttu-id="5b4b0-139">Type</span><span class="sxs-lookup"><span data-stu-id="5b4b0-139">Type</span></span> | <span data-ttu-id="5b4b0-140">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="5b4b0-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="5b4b0-141">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="5b4b0-141">Authorization</span></span> | <span data-ttu-id="5b4b0-142">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="5b4b0-142">String</span></span> | <span data-ttu-id="5b4b0-143">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="5b4b0-143">Bearer {token}.</span></span> <span data-ttu-id="5b4b0-144">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="5b4b0-144">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="5b4b0-145">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="5b4b0-145">Request body</span></span>
<span data-ttu-id="5b4b0-146">Leeg</span><span class="sxs-lookup"><span data-stu-id="5b4b0-146">Empty</span></span>

## <a name="response"></a><span data-ttu-id="5b4b0-147">Antwoord</span><span class="sxs-lookup"><span data-stu-id="5b4b0-147">Response</span></span>
<span data-ttu-id="5b4b0-148">Als dit is gelukt en domein bestaat- [](machine.md) 200 OK met lijst met machine-entiteiten.</span><span class="sxs-lookup"><span data-stu-id="5b4b0-148">If successful and domain exists - 200 OK with list of [machine](machine.md) entities.</span></span> <span data-ttu-id="5b4b0-149">Als domein niet bestaat- 404 Niet gevonden.</span><span class="sxs-lookup"><span data-stu-id="5b4b0-149">If domain do not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="5b4b0-150">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="5b4b0-150">Example</span></span>

<span data-ttu-id="5b4b0-151">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="5b4b0-151">**Request**</span></span>

<span data-ttu-id="5b4b0-152">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="5b4b0-152">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/domains/api.securitycenter.microsoft.com/machines
```
