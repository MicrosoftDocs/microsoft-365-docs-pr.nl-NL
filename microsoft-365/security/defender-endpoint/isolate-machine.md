---
title: Machine-API isoleren
description: Meer informatie over het gebruik van de API van isolate machine om een apparaat te isoleren van toegang tot een extern netwerk in Microsoft Defender voor Eindpunt.
keywords: api's, graph api, ondersteunde api's, isoleert apparaat
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
ms.openlocfilehash: 9f3313a08b072f4fb2f699148ab801207e56fc09
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772111"
---
# <a name="isolate-machine-api"></a><span data-ttu-id="5a78d-104">Machine-API isoleren</span><span class="sxs-lookup"><span data-stu-id="5a78d-104">Isolate machine API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="5a78d-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="5a78d-105">**Applies to:**</span></span>
- [<span data-ttu-id="5a78d-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="5a78d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5a78d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5a78d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="5a78d-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="5a78d-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="5a78d-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="5a78d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="5a78d-110">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="5a78d-110">API description</span></span>
<span data-ttu-id="5a78d-111">Isoleert een apparaat voor toegang tot een extern netwerk.</span><span class="sxs-lookup"><span data-stu-id="5a78d-111">Isolates a device from accessing external network.</span></span>


## <a name="limitations"></a><span data-ttu-id="5a78d-112">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="5a78d-112">Limitations</span></span>
1. <span data-ttu-id="5a78d-113">Tariefbeperkingen voor deze API zijn 100 oproepen per minuut en 1500 oproepen per uur.</span><span class="sxs-lookup"><span data-stu-id="5a78d-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="5a78d-114">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="5a78d-114">Permissions</span></span>
<span data-ttu-id="5a78d-115">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="5a78d-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="5a78d-116">Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="5a78d-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="5a78d-117">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="5a78d-117">Permission type</span></span> |   <span data-ttu-id="5a78d-118">Machtiging</span><span class="sxs-lookup"><span data-stu-id="5a78d-118">Permission</span></span>  |   <span data-ttu-id="5a78d-119">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="5a78d-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="5a78d-120">Toepassing</span><span class="sxs-lookup"><span data-stu-id="5a78d-120">Application</span></span> |   <span data-ttu-id="5a78d-121">Machine.Isolate</span><span class="sxs-lookup"><span data-stu-id="5a78d-121">Machine.Isolate</span></span> |   <span data-ttu-id="5a78d-122">'Isolate machine'</span><span class="sxs-lookup"><span data-stu-id="5a78d-122">'Isolate machine'</span></span>
<span data-ttu-id="5a78d-123">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="5a78d-123">Delegated (work or school account)</span></span> | <span data-ttu-id="5a78d-124">Machine.Isolate</span><span class="sxs-lookup"><span data-stu-id="5a78d-124">Machine.Isolate</span></span> |  <span data-ttu-id="5a78d-125">'Isolate machine'</span><span class="sxs-lookup"><span data-stu-id="5a78d-125">'Isolate machine'</span></span>

>[!Note]
> <span data-ttu-id="5a78d-126">Bij het verkrijgen van een token met gebruikersreferenties:</span><span class="sxs-lookup"><span data-stu-id="5a78d-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="5a78d-127">De gebruiker moet ten minste de volgende rolmachtiging hebben: 'Active remediation actions' (Zie [Rollen](user-roles.md) maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="5a78d-127">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="5a78d-128">De gebruiker moet toegang hebben tot het apparaat op basis van apparaatgroepinstellingen (Zie [Apparaatgroepen](machine-groups.md) maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="5a78d-128">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>


## <a name="http-request"></a><span data-ttu-id="5a78d-129">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="5a78d-129">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/isolate
```

## <a name="request-headers"></a><span data-ttu-id="5a78d-130">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="5a78d-130">Request headers</span></span>

<span data-ttu-id="5a78d-131">Naam</span><span class="sxs-lookup"><span data-stu-id="5a78d-131">Name</span></span> | <span data-ttu-id="5a78d-132">Type</span><span class="sxs-lookup"><span data-stu-id="5a78d-132">Type</span></span> | <span data-ttu-id="5a78d-133">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="5a78d-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="5a78d-134">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="5a78d-134">Authorization</span></span> | <span data-ttu-id="5a78d-135">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="5a78d-135">String</span></span> | <span data-ttu-id="5a78d-136">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="5a78d-136">Bearer {token}.</span></span> <span data-ttu-id="5a78d-137">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="5a78d-137">**Required**.</span></span>
<span data-ttu-id="5a78d-138">Inhoudstype</span><span class="sxs-lookup"><span data-stu-id="5a78d-138">Content-Type</span></span> | <span data-ttu-id="5a78d-139">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="5a78d-139">string</span></span> | <span data-ttu-id="5a78d-140">toepassing/json.</span><span class="sxs-lookup"><span data-stu-id="5a78d-140">application/json.</span></span> <span data-ttu-id="5a78d-141">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="5a78d-141">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="5a78d-142">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="5a78d-142">Request body</span></span>
<span data-ttu-id="5a78d-143">In de objectaanvraag moet u een JSON-object de volgende parameters geven:</span><span class="sxs-lookup"><span data-stu-id="5a78d-143">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="5a78d-144">Parameter</span><span class="sxs-lookup"><span data-stu-id="5a78d-144">Parameter</span></span> | <span data-ttu-id="5a78d-145">Type</span><span class="sxs-lookup"><span data-stu-id="5a78d-145">Type</span></span>    | <span data-ttu-id="5a78d-146">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="5a78d-146">Description</span></span>
:---|:---|:---
<span data-ttu-id="5a78d-147">Opmerking</span><span class="sxs-lookup"><span data-stu-id="5a78d-147">Comment</span></span> |   <span data-ttu-id="5a78d-148">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="5a78d-148">String</span></span> |    <span data-ttu-id="5a78d-149">Opmerking om te koppelen aan de actie.</span><span class="sxs-lookup"><span data-stu-id="5a78d-149">Comment to associate with the action.</span></span> <span data-ttu-id="5a78d-150">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="5a78d-150">**Required**.</span></span>
<span data-ttu-id="5a78d-151">IsolationType</span><span class="sxs-lookup"><span data-stu-id="5a78d-151">IsolationType</span></span>   | <span data-ttu-id="5a78d-152">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="5a78d-152">String</span></span> |  <span data-ttu-id="5a78d-153">Type isolatie.</span><span class="sxs-lookup"><span data-stu-id="5a78d-153">Type of the isolation.</span></span> <span data-ttu-id="5a78d-154">Toegestane waarden zijn: 'Volledig' of 'Selectief'.</span><span class="sxs-lookup"><span data-stu-id="5a78d-154">Allowed values are: 'Full' or 'Selective'.</span></span>

<span data-ttu-id="5a78d-155">**IsolationType** bepaalt het type isolatie dat moet worden gebruikt en kan een van de volgende opties zijn:</span><span class="sxs-lookup"><span data-stu-id="5a78d-155">**IsolationType** controls the type of isolation to perform and can be one of the following:</span></span>
- <span data-ttu-id="5a78d-156">Volledig – Volledige isolatie</span><span class="sxs-lookup"><span data-stu-id="5a78d-156">Full – Full isolation</span></span>
- <span data-ttu-id="5a78d-157">Selectief: beperk slechts een beperkt aantal toepassingen om toegang te krijgen tot het netwerk (zie [Apparaten isoleren van](respond-machine-alerts.md#isolate-devices-from-the-network) het netwerk voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="5a78d-157">Selective – Restrict only limited set of applications from accessing the network (see [Isolate devices from the network](respond-machine-alerts.md#isolate-devices-from-the-network) for more details)</span></span>


## <a name="response"></a><span data-ttu-id="5a78d-158">Antwoord</span><span class="sxs-lookup"><span data-stu-id="5a78d-158">Response</span></span>
<span data-ttu-id="5a78d-159">Als dit is gelukt, retourneert deze methode 201: de reactiecode en [de machineactie](machineaction.md) in de antwoordgroep.</span><span class="sxs-lookup"><span data-stu-id="5a78d-159">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="5a78d-160">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="5a78d-160">Example</span></span>

<span data-ttu-id="5a78d-161">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="5a78d-161">**Request**</span></span>

<span data-ttu-id="5a78d-162">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="5a78d-162">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/isolate
```

```json
{
  "Comment": "Isolate machine due to alert 1234",
  "IsolationType": "Full" 
}
```

- <span data-ttu-id="5a78d-163">Zie Apparaat los van isolatie als u een apparaat wilt los laten van [isolatie.](unisolate-machine.md)</span><span class="sxs-lookup"><span data-stu-id="5a78d-163">To release a device from isolation, see [Release device from isolation](unisolate-machine.md).</span></span>
