---
title: API voor bestand stoppen en in quarantaine plaatsen
description: Meer informatie over het stoppen met het uitvoeren van een bestand op een apparaat en het bestand verwijderen in Microsoft Defender voor Eindpunt. Zie een voorbeeld.
keywords: api's, graph api, ondersteunde api's, stop- en quarantainebestand
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
ms.openlocfilehash: ac14f1ecda2b6256dc19223869b8878e6e725b96
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771398"
---
# <a name="stop-and-quarantine-file-api"></a><span data-ttu-id="7a0bb-105">API voor bestand stoppen en in quarantaine plaatsen</span><span class="sxs-lookup"><span data-stu-id="7a0bb-105">Stop and quarantine file API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7a0bb-106">**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="7a0bb-106">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="7a0bb-107">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="7a0bb-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="7a0bb-108">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="7a0bb-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="7a0bb-109">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="7a0bb-109">API description</span></span>
<span data-ttu-id="7a0bb-110">De uitvoering van een bestand op een apparaat stoppen en verwijderen.</span><span class="sxs-lookup"><span data-stu-id="7a0bb-110">Stop execution of a file on a device and delete it.</span></span>


## <a name="limitations"></a><span data-ttu-id="7a0bb-111">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="7a0bb-111">Limitations</span></span>
1. <span data-ttu-id="7a0bb-112">Tariefbeperkingen voor deze API zijn 100 oproepen per minuut en 1500 oproepen per uur.</span><span class="sxs-lookup"><span data-stu-id="7a0bb-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="7a0bb-113">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="7a0bb-113">Permissions</span></span>
<span data-ttu-id="7a0bb-114">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="7a0bb-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="7a0bb-115">Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="7a0bb-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="7a0bb-116">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="7a0bb-116">Permission type</span></span> |   <span data-ttu-id="7a0bb-117">Machtiging</span><span class="sxs-lookup"><span data-stu-id="7a0bb-117">Permission</span></span>  |   <span data-ttu-id="7a0bb-118">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="7a0bb-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="7a0bb-119">Toepassing</span><span class="sxs-lookup"><span data-stu-id="7a0bb-119">Application</span></span> |   <span data-ttu-id="7a0bb-120">Machine.StopAndQuarantine</span><span class="sxs-lookup"><span data-stu-id="7a0bb-120">Machine.StopAndQuarantine</span></span> | <span data-ttu-id="7a0bb-121">'Stop and Quarantine'</span><span class="sxs-lookup"><span data-stu-id="7a0bb-121">'Stop And Quarantine'</span></span>
<span data-ttu-id="7a0bb-122">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="7a0bb-122">Delegated (work or school account)</span></span> | <span data-ttu-id="7a0bb-123">Machine.StopAndQuarantine</span><span class="sxs-lookup"><span data-stu-id="7a0bb-123">Machine.StopAndQuarantine</span></span> | <span data-ttu-id="7a0bb-124">'Stop and Quarantine'</span><span class="sxs-lookup"><span data-stu-id="7a0bb-124">'Stop And Quarantine'</span></span>

>[!Note]
> <span data-ttu-id="7a0bb-125">Bij het verkrijgen van een token met gebruikersreferenties:</span><span class="sxs-lookup"><span data-stu-id="7a0bb-125">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="7a0bb-126">De gebruiker moet ten minste de volgende rolmachtiging hebben: 'Active remediation actions' (Zie [Rollen](user-roles.md) maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="7a0bb-126">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="7a0bb-127">De gebruiker moet toegang hebben tot het apparaat op basis van apparaatgroepinstellingen (Zie [Apparaatgroepen](machine-groups.md) maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="7a0bb-127">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="7a0bb-128">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="7a0bb-128">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/StopAndQuarantineFile
```

## <a name="request-headers"></a><span data-ttu-id="7a0bb-129">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="7a0bb-129">Request headers</span></span>

<span data-ttu-id="7a0bb-130">Naam</span><span class="sxs-lookup"><span data-stu-id="7a0bb-130">Name</span></span> | <span data-ttu-id="7a0bb-131">Type</span><span class="sxs-lookup"><span data-stu-id="7a0bb-131">Type</span></span> | <span data-ttu-id="7a0bb-132">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="7a0bb-132">Description</span></span>
:---|:---|:---
<span data-ttu-id="7a0bb-133">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="7a0bb-133">Authorization</span></span> | <span data-ttu-id="7a0bb-134">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7a0bb-134">String</span></span> | <span data-ttu-id="7a0bb-135">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="7a0bb-135">Bearer {token}.</span></span> <span data-ttu-id="7a0bb-136">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="7a0bb-136">**Required**.</span></span>
<span data-ttu-id="7a0bb-137">Inhoudstype</span><span class="sxs-lookup"><span data-stu-id="7a0bb-137">Content-Type</span></span> | <span data-ttu-id="7a0bb-138">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7a0bb-138">string</span></span> | <span data-ttu-id="7a0bb-139">toepassing/json.</span><span class="sxs-lookup"><span data-stu-id="7a0bb-139">application/json.</span></span> <span data-ttu-id="7a0bb-140">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="7a0bb-140">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="7a0bb-141">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="7a0bb-141">Request body</span></span>
<span data-ttu-id="7a0bb-142">In de objectaanvraag moet u een JSON-object de volgende parameters geven:</span><span class="sxs-lookup"><span data-stu-id="7a0bb-142">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="7a0bb-143">Parameter</span><span class="sxs-lookup"><span data-stu-id="7a0bb-143">Parameter</span></span> | <span data-ttu-id="7a0bb-144">Type</span><span class="sxs-lookup"><span data-stu-id="7a0bb-144">Type</span></span>    | <span data-ttu-id="7a0bb-145">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="7a0bb-145">Description</span></span>
:---|:---|:---
<span data-ttu-id="7a0bb-146">Opmerking</span><span class="sxs-lookup"><span data-stu-id="7a0bb-146">Comment</span></span> |   <span data-ttu-id="7a0bb-147">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7a0bb-147">String</span></span> |    <span data-ttu-id="7a0bb-148">Opmerking om te koppelen aan de actie.</span><span class="sxs-lookup"><span data-stu-id="7a0bb-148">Comment to associate with the action.</span></span> <span data-ttu-id="7a0bb-149">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="7a0bb-149">**Required**.</span></span>
<span data-ttu-id="7a0bb-150">Sha1</span><span class="sxs-lookup"><span data-stu-id="7a0bb-150">Sha1</span></span> |  <span data-ttu-id="7a0bb-151">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7a0bb-151">String</span></span>   | <span data-ttu-id="7a0bb-152">Sha1 van het bestand om het apparaat te stoppen en in quarantaine te plaatsen.</span><span class="sxs-lookup"><span data-stu-id="7a0bb-152">Sha1 of the file to stop and quarantine on the device.</span></span> <span data-ttu-id="7a0bb-153">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="7a0bb-153">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="7a0bb-154">Antwoord</span><span class="sxs-lookup"><span data-stu-id="7a0bb-154">Response</span></span>
<span data-ttu-id="7a0bb-155">Als dit is gelukt, retourneert deze methode 201: de reactiecode en [de machineactie](machineaction.md) in de antwoordgroep.</span><span class="sxs-lookup"><span data-stu-id="7a0bb-155">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="7a0bb-156">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="7a0bb-156">Example</span></span>

<span data-ttu-id="7a0bb-157">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="7a0bb-157">**Request**</span></span>

<span data-ttu-id="7a0bb-158">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="7a0bb-158">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/StopAndQuarantineFile 
```

```json
{
  "Comment": "Stop and quarantine file on machine due to alert 441688558380765161_2136280442",
  "Sha1": "87662bc3d60e4200ceaf7aae249d1c343f4b83c9"
}

```
