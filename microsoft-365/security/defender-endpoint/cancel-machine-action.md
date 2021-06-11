---
title: Api voor computeractie annuleren
description: Meer informatie over het annuleren van een al gestarte machineactie
keywords: api's, graph api,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 490ee91d5f2d2c02174be94c52fc83fd0ec0fc5e
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879696"
---
#   <a name="cancel-machine-action-api"></a><span data-ttu-id="77c9b-104">Api voor computeractie annuleren</span><span class="sxs-lookup"><span data-stu-id="77c9b-104">Cancel machine action API</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="77c9b-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="77c9b-105">**Applies to:**</span></span>
- [<span data-ttu-id="77c9b-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="77c9b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)

[!include[Prerelease information](../../includes/prerelease.md)]

><span data-ttu-id="77c9b-107">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="77c9b-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="77c9b-108">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="77c9b-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="77c9b-109">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="77c9b-109">API description</span></span>

<span data-ttu-id="77c9b-110">Een al gestarte machineactie annuleren die nog niet definitief is (voltooid, geannuleerd, mislukt).</span><span class="sxs-lookup"><span data-stu-id="77c9b-110">Cancel an already launched machine action that are not yet in final state (completed, cancelled, failed).</span></span>

## <a name="limitations"></a><span data-ttu-id="77c9b-111">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="77c9b-111">Limitations</span></span>

1.  <span data-ttu-id="77c9b-112">Tariefbeperkingen voor deze API zijn 100 oproepen per minuut en 1500 oproepen per uur.</span><span class="sxs-lookup"><span data-stu-id="77c9b-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="77c9b-113">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="77c9b-113">Permissions</span></span>

<span data-ttu-id="77c9b-114">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="77c9b-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="77c9b-115">Zie Aan de slag voor meer informatie, waaronder hoe u machtigingen [kiest.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="77c9b-115">To learn more, including how to choose permissions, see [Get started](apis-intro.md).</span></span>

|     <span data-ttu-id="77c9b-116">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="77c9b-116">Permission    type</span></span>     |     <span data-ttu-id="77c9b-117">Machtiging</span><span class="sxs-lookup"><span data-stu-id="77c9b-117">Permission</span></span>     |    <span data-ttu-id="77c9b-118">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="77c9b-118">Permission    display name</span></span>     |
|-|-|-|
|    <br><span data-ttu-id="77c9b-119">Toepassing</span><span class="sxs-lookup"><span data-stu-id="77c9b-119">Application</span></span>    |    <br><span data-ttu-id="77c9b-120">Machine.CollectForensic</span><span class="sxs-lookup"><span data-stu-id="77c9b-120">Machine.CollectForensic</span></span><br>   <span data-ttu-id="77c9b-121">Machine.Isolate</span><span class="sxs-lookup"><span data-stu-id="77c9b-121">Machine.Isolate</span></span>   <br><span data-ttu-id="77c9b-122">Machine.RestrictExecution</span><span class="sxs-lookup"><span data-stu-id="77c9b-122">Machine.RestrictExecution</span></span><br>   <span data-ttu-id="77c9b-123">Machine.Scannen</span><span class="sxs-lookup"><span data-stu-id="77c9b-123">Machine.Scan</span></span><br>   <span data-ttu-id="77c9b-124">Machine.Offboard</span><span class="sxs-lookup"><span data-stu-id="77c9b-124">Machine.Offboard</span></span><br>   <span data-ttu-id="77c9b-125">Machine.StopAndQuarantine</span><span class="sxs-lookup"><span data-stu-id="77c9b-125">Machine.StopAndQuarantine</span></span><br>   <span data-ttu-id="77c9b-126">Machine.LiveResponse</span><span class="sxs-lookup"><span data-stu-id="77c9b-126">Machine.LiveResponse</span></span>    |    <span data-ttu-id="77c9b-127">Gerechtelijke gegevens verzamelen</span><span class="sxs-lookup"><span data-stu-id="77c9b-127">Collect   forensics</span></span>   <br><span data-ttu-id="77c9b-128">Machine isoleren</span><span class="sxs-lookup"><span data-stu-id="77c9b-128">Isolate   machine</span></span><br><span data-ttu-id="77c9b-129">De uitvoering van code beperken</span><span class="sxs-lookup"><span data-stu-id="77c9b-129">Restrict   code execution</span></span><br>  <span data-ttu-id="77c9b-130">Scanapparaat</span><span class="sxs-lookup"><span data-stu-id="77c9b-130">Scan   machine</span></span><br>  <span data-ttu-id="77c9b-131">Offboard-machine</span><span class="sxs-lookup"><span data-stu-id="77c9b-131">Offboard   machine</span></span><br>   <span data-ttu-id="77c9b-132">Stoppen en quarantaine</span><span class="sxs-lookup"><span data-stu-id="77c9b-132">Stop And   Quarantine</span></span><br>   <span data-ttu-id="77c9b-133">Livereactie uitvoeren op een specifieke computer</span><span class="sxs-lookup"><span data-stu-id="77c9b-133">Run live   response on a specific machine</span></span>    |
|    <br><span data-ttu-id="77c9b-134">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="77c9b-134">Delegated   (work or school account)</span></span>    |    <span data-ttu-id="77c9b-135">Machine.CollectForensic</span><span class="sxs-lookup"><span data-stu-id="77c9b-135">Machine.CollectForensic</span></span><br>   <span data-ttu-id="77c9b-136">Machine.Isolate</span><span class="sxs-lookup"><span data-stu-id="77c9b-136">Machine.Isolate</span></span>    <br><span data-ttu-id="77c9b-137">Machine.RestrictExecution</span><span class="sxs-lookup"><span data-stu-id="77c9b-137">Machine.RestrictExecution</span></span><br>   <span data-ttu-id="77c9b-138">Machine.Scannen</span><span class="sxs-lookup"><span data-stu-id="77c9b-138">Machine.Scan</span></span><br>   <span data-ttu-id="77c9b-139">Machine.Offboard</span><span class="sxs-lookup"><span data-stu-id="77c9b-139">Machine.Offboard</span></span><br>   <span data-ttu-id="77c9b-140">Machine.StopAndQuarantineMachine.LiveResponse</span><span class="sxs-lookup"><span data-stu-id="77c9b-140">Machine.StopAndQuarantineMachine.LiveResponse</span></span>    |    <span data-ttu-id="77c9b-141">Gerechtelijke gegevens verzamelen</span><span class="sxs-lookup"><span data-stu-id="77c9b-141">Collect   forensics</span></span><br>   <span data-ttu-id="77c9b-142">Machine isoleren</span><span class="sxs-lookup"><span data-stu-id="77c9b-142">Isolate   machine</span></span><br>  <span data-ttu-id="77c9b-143">De uitvoering van code beperken</span><span class="sxs-lookup"><span data-stu-id="77c9b-143">Restrict   code execution</span></span><br> <span data-ttu-id="77c9b-144">Scanapparaat</span><span class="sxs-lookup"><span data-stu-id="77c9b-144">Scan   machine</span></span><br><span data-ttu-id="77c9b-145">Offboard-machine</span><span class="sxs-lookup"><span data-stu-id="77c9b-145">Offboard   machine</span></span><br> <span data-ttu-id="77c9b-146">Stoppen en quarantaine</span><span class="sxs-lookup"><span data-stu-id="77c9b-146">Stop And   Quarantine</span></span><br> <span data-ttu-id="77c9b-147">Livereactie uitvoeren op een specifieke computer</span><span class="sxs-lookup"><span data-stu-id="77c9b-147">Run live   response on a specific machine</span></span>    |


## <a name="http-request"></a><span data-ttu-id="77c9b-148">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="77c9b-148">HTTP request</span></span>

```
POST https://api.securitycenter.microsoft.com/api/machineactions/<machineactionid>/cancel  
```


## <a name="request-headers"></a><span data-ttu-id="77c9b-149">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="77c9b-149">Request headers</span></span>

| <span data-ttu-id="77c9b-150">Naam</span><span class="sxs-lookup"><span data-stu-id="77c9b-150">Name</span></span>      | <span data-ttu-id="77c9b-151">Type</span><span class="sxs-lookup"><span data-stu-id="77c9b-151">Type</span></span> | <span data-ttu-id="77c9b-152">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="77c9b-152">Description</span></span>                 |
|---------------|----------|---------------------------------|
| <span data-ttu-id="77c9b-153">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="77c9b-153">Authorization</span></span> | <span data-ttu-id="77c9b-154">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="77c9b-154">String</span></span>   | <span data-ttu-id="77c9b-155">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="77c9b-155">Bearer {token}.</span></span> <span data-ttu-id="77c9b-156">Vereist.</span><span class="sxs-lookup"><span data-stu-id="77c9b-156">Required.</span></span>   |
| <span data-ttu-id="77c9b-157">Inhoudstype</span><span class="sxs-lookup"><span data-stu-id="77c9b-157">Content-Type</span></span>  | <span data-ttu-id="77c9b-158">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="77c9b-158">string</span></span>   | <span data-ttu-id="77c9b-159">toepassing/json.</span><span class="sxs-lookup"><span data-stu-id="77c9b-159">application/json.</span></span> <span data-ttu-id="77c9b-160">Vereist.</span><span class="sxs-lookup"><span data-stu-id="77c9b-160">Required.</span></span> |

## <a name="request-body"></a><span data-ttu-id="77c9b-161">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="77c9b-161">Request body</span></span>

| <span data-ttu-id="77c9b-162">Parameter</span><span class="sxs-lookup"><span data-stu-id="77c9b-162">Parameter</span></span> | <span data-ttu-id="77c9b-163">Type</span><span class="sxs-lookup"><span data-stu-id="77c9b-163">Type</span></span> | <span data-ttu-id="77c9b-164">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="77c9b-164">Description</span></span>                        |
|---------------|----------|----------------------------------------|
| <span data-ttu-id="77c9b-165">Opmerking</span><span class="sxs-lookup"><span data-stu-id="77c9b-165">Comment</span></span>       | <span data-ttu-id="77c9b-166">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="77c9b-166">String</span></span>   | <span data-ttu-id="77c9b-167">Opmerking om te koppelen aan de annuleringsactie.</span><span class="sxs-lookup"><span data-stu-id="77c9b-167">Comment to associate with the cancellation action.</span></span>  |

## <a name="response"></a><span data-ttu-id="77c9b-168">Antwoord</span><span class="sxs-lookup"><span data-stu-id="77c9b-168">Response</span></span>

<span data-ttu-id="77c9b-169">Als dit is gelukt, retourneert deze methode 200, Ok-antwoordcode met een entiteit Machineactie.</span><span class="sxs-lookup"><span data-stu-id="77c9b-169">If successful, this method returns 200, Ok response code with a Machine Action entity.</span></span> <span data-ttu-id="77c9b-170">Als de entiteit machineactie met de opgegeven id niet is gevonden- 404 Niet gevonden.</span><span class="sxs-lookup"><span data-stu-id="77c9b-170">If machine action entity with the specified id was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="77c9b-171">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="77c9b-171">Example</span></span>

<span data-ttu-id="77c9b-172">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="77c9b-172">**Request**</span></span>

<span data-ttu-id="77c9b-173">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="77c9b-173">Here is an example of the request.</span></span>

```HTTP
POST
https://api.securitycenter.microsoft.com/api/machineactions/988cc94e-7a8f-4b28-ab65-54970c5d5018/cancel
```


```JSON
{
    "Comment": "Machine action was canceled by automation"
}
```

## <a name="related-topic"></a><span data-ttu-id="77c9b-174">Verwant onderwerp</span><span class="sxs-lookup"><span data-stu-id="77c9b-174">Related topic</span></span>

- [<span data-ttu-id="77c9b-175">Api voor machineactie krijgen</span><span class="sxs-lookup"><span data-stu-id="77c9b-175">Get machine action API</span></span>](get-machineaction-object.md)