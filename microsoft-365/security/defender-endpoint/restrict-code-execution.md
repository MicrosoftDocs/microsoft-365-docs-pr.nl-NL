---
title: Api voor app-uitvoering beperken
description: Gebruik deze API om oproepen te maken die betrekking hebben op het beperken van het uitvoeren van een toepassing.
keywords: api's, graph api, ondersteunde api's, onderzoekspakket verzamelen
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
ms.openlocfilehash: 7195e91a3a9b7aef6977c925f2c8689d3e461815
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771571"
---
# <a name="restrict-app-execution-api"></a><span data-ttu-id="82aed-104">Api voor app-uitvoering beperken</span><span class="sxs-lookup"><span data-stu-id="82aed-104">Restrict app execution API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="82aed-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="82aed-105">**Applies to:**</span></span>
- [<span data-ttu-id="82aed-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="82aed-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="82aed-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="82aed-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="82aed-108">**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="82aed-108">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="82aed-109">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="82aed-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="82aed-110">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="82aed-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="82aed-111">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="82aed-111">API description</span></span>
<span data-ttu-id="82aed-112">De uitvoering van alle toepassingen op het apparaat beperken, behalve een vooraf gedefinieerde set.</span><span class="sxs-lookup"><span data-stu-id="82aed-112">Restrict execution of all applications on the device except a predefined set.</span></span>


## <a name="limitations"></a><span data-ttu-id="82aed-113">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="82aed-113">Limitations</span></span>
1. <span data-ttu-id="82aed-114">Tariefbeperkingen voor deze API zijn 100 oproepen per minuut en 1500 oproepen per uur.</span><span class="sxs-lookup"><span data-stu-id="82aed-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="82aed-115">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="82aed-115">Permissions</span></span>
<span data-ttu-id="82aed-116">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="82aed-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="82aed-117">Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="82aed-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="82aed-118">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="82aed-118">Permission type</span></span> |   <span data-ttu-id="82aed-119">Machtiging</span><span class="sxs-lookup"><span data-stu-id="82aed-119">Permission</span></span>  |   <span data-ttu-id="82aed-120">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="82aed-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="82aed-121">Toepassing</span><span class="sxs-lookup"><span data-stu-id="82aed-121">Application</span></span> |   <span data-ttu-id="82aed-122">Machine.RestrictExecution</span><span class="sxs-lookup"><span data-stu-id="82aed-122">Machine.RestrictExecution</span></span> | <span data-ttu-id="82aed-123">'Codeuitvoering beperken'</span><span class="sxs-lookup"><span data-stu-id="82aed-123">'Restrict code execution'</span></span>
<span data-ttu-id="82aed-124">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="82aed-124">Delegated (work or school account)</span></span> | <span data-ttu-id="82aed-125">Machine.RestrictExecution</span><span class="sxs-lookup"><span data-stu-id="82aed-125">Machine.RestrictExecution</span></span> | <span data-ttu-id="82aed-126">'Codeuitvoering beperken'</span><span class="sxs-lookup"><span data-stu-id="82aed-126">'Restrict code execution'</span></span>

>[!Note]
> <span data-ttu-id="82aed-127">Bij het verkrijgen van een token met gebruikersreferenties:</span><span class="sxs-lookup"><span data-stu-id="82aed-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="82aed-128">De gebruiker moet ten minste de volgende rolmachtiging hebben: 'Active remediation actions' (Zie [Rollen](user-roles.md) maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="82aed-128">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="82aed-129">De gebruiker moet toegang hebben tot het apparaat op basis van apparaatgroepinstellingen (Zie [Apparaatgroepen](machine-groups.md) maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="82aed-129">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="82aed-130">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="82aed-130">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/restrictCodeExecution
```

## <a name="request-headers"></a><span data-ttu-id="82aed-131">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="82aed-131">Request headers</span></span>

<span data-ttu-id="82aed-132">Naam</span><span class="sxs-lookup"><span data-stu-id="82aed-132">Name</span></span> | <span data-ttu-id="82aed-133">Type</span><span class="sxs-lookup"><span data-stu-id="82aed-133">Type</span></span> | <span data-ttu-id="82aed-134">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="82aed-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="82aed-135">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="82aed-135">Authorization</span></span> | <span data-ttu-id="82aed-136">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="82aed-136">String</span></span> | <span data-ttu-id="82aed-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="82aed-137">Bearer {token}.</span></span> <span data-ttu-id="82aed-138">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="82aed-138">**Required**.</span></span>
<span data-ttu-id="82aed-139">Inhoudstype</span><span class="sxs-lookup"><span data-stu-id="82aed-139">Content-Type</span></span> | <span data-ttu-id="82aed-140">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="82aed-140">string</span></span> | <span data-ttu-id="82aed-141">toepassing/json.</span><span class="sxs-lookup"><span data-stu-id="82aed-141">application/json.</span></span> <span data-ttu-id="82aed-142">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="82aed-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="82aed-143">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="82aed-143">Request body</span></span>
<span data-ttu-id="82aed-144">In de objectaanvraag moet u een JSON-object de volgende parameters geven:</span><span class="sxs-lookup"><span data-stu-id="82aed-144">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="82aed-145">Parameter</span><span class="sxs-lookup"><span data-stu-id="82aed-145">Parameter</span></span> | <span data-ttu-id="82aed-146">Type</span><span class="sxs-lookup"><span data-stu-id="82aed-146">Type</span></span>    | <span data-ttu-id="82aed-147">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="82aed-147">Description</span></span>
:---|:---|:---
<span data-ttu-id="82aed-148">Opmerking</span><span class="sxs-lookup"><span data-stu-id="82aed-148">Comment</span></span> |   <span data-ttu-id="82aed-149">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="82aed-149">String</span></span> |    <span data-ttu-id="82aed-150">Opmerking om te koppelen aan de actie.</span><span class="sxs-lookup"><span data-stu-id="82aed-150">Comment to associate with the action.</span></span> <span data-ttu-id="82aed-151">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="82aed-151">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="82aed-152">Antwoord</span><span class="sxs-lookup"><span data-stu-id="82aed-152">Response</span></span>
<span data-ttu-id="82aed-153">Als dit is gelukt, retourneert deze methode 201: de reactiecode en [de machineactie](machineaction.md) in de antwoordgroep.</span><span class="sxs-lookup"><span data-stu-id="82aed-153">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="82aed-154">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="82aed-154">Example</span></span>

<span data-ttu-id="82aed-155">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="82aed-155">**Request**</span></span>

<span data-ttu-id="82aed-156">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="82aed-156">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/restrictCodeExecution 
```

```json
{
  "Comment": "Restrict code execution due to alert 1234"
}

```

- <span data-ttu-id="82aed-157">Zie App-beperking verwijderen als u beperkingen voor het uitvoeren van code van een [apparaat wilt verwijderen.](unrestrict-code-execution.md)</span><span class="sxs-lookup"><span data-stu-id="82aed-157">To remove code execution restriction from a device, see [Remove app restriction](unrestrict-code-execution.md).</span></span>
