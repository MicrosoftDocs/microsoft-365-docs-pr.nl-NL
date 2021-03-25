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
ms.technology: mde
ms.openlocfilehash: 670282f0f87092437bb1f3c6bf7be908e4649042
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199727"
---
# <a name="stop-and-quarantine-file-api"></a><span data-ttu-id="8c653-105">API voor bestand stoppen en in quarantaine plaatsen</span><span class="sxs-lookup"><span data-stu-id="8c653-105">Stop and quarantine file API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8c653-106">**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="8c653-106">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="8c653-107">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="8c653-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="8c653-108">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="8c653-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="8c653-109">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="8c653-109">API description</span></span>
<span data-ttu-id="8c653-110">De uitvoering van een bestand op een apparaat stoppen en verwijderen.</span><span class="sxs-lookup"><span data-stu-id="8c653-110">Stop execution of a file on a device and delete it.</span></span>


## <a name="limitations"></a><span data-ttu-id="8c653-111">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="8c653-111">Limitations</span></span>
1. <span data-ttu-id="8c653-112">Tariefbeperkingen voor deze API zijn 100 oproepen per minuut en 1500 oproepen per uur.</span><span class="sxs-lookup"><span data-stu-id="8c653-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="8c653-113">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="8c653-113">Permissions</span></span>
<span data-ttu-id="8c653-114">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="8c653-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="8c653-115">Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="8c653-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="8c653-116">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="8c653-116">Permission type</span></span> |   <span data-ttu-id="8c653-117">Machtiging</span><span class="sxs-lookup"><span data-stu-id="8c653-117">Permission</span></span>  |   <span data-ttu-id="8c653-118">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="8c653-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="8c653-119">Toepassing</span><span class="sxs-lookup"><span data-stu-id="8c653-119">Application</span></span> |   <span data-ttu-id="8c653-120">Machine.StopAndQuarantine</span><span class="sxs-lookup"><span data-stu-id="8c653-120">Machine.StopAndQuarantine</span></span> | <span data-ttu-id="8c653-121">'Stop and Quarantine'</span><span class="sxs-lookup"><span data-stu-id="8c653-121">'Stop And Quarantine'</span></span>
<span data-ttu-id="8c653-122">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="8c653-122">Delegated (work or school account)</span></span> | <span data-ttu-id="8c653-123">Machine.StopAndQuarantine</span><span class="sxs-lookup"><span data-stu-id="8c653-123">Machine.StopAndQuarantine</span></span> | <span data-ttu-id="8c653-124">'Stop and Quarantine'</span><span class="sxs-lookup"><span data-stu-id="8c653-124">'Stop And Quarantine'</span></span>

>[!Note]
> <span data-ttu-id="8c653-125">Bij het verkrijgen van een token met gebruikersreferenties:</span><span class="sxs-lookup"><span data-stu-id="8c653-125">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="8c653-126">De gebruiker moet ten minste de volgende rolmachtiging hebben: 'Active remediation actions' (Zie [Rollen](user-roles.md) maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="8c653-126">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="8c653-127">De gebruiker moet toegang hebben tot het apparaat op basis van apparaatgroepinstellingen (Zie [Apparaatgroepen](machine-groups.md) maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="8c653-127">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="8c653-128">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="8c653-128">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/StopAndQuarantineFile
```

## <a name="request-headers"></a><span data-ttu-id="8c653-129">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="8c653-129">Request headers</span></span>

<span data-ttu-id="8c653-130">Naam</span><span class="sxs-lookup"><span data-stu-id="8c653-130">Name</span></span> | <span data-ttu-id="8c653-131">Type</span><span class="sxs-lookup"><span data-stu-id="8c653-131">Type</span></span> | <span data-ttu-id="8c653-132">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="8c653-132">Description</span></span>
:---|:---|:---
<span data-ttu-id="8c653-133">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="8c653-133">Authorization</span></span> | <span data-ttu-id="8c653-134">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="8c653-134">String</span></span> | <span data-ttu-id="8c653-135">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="8c653-135">Bearer {token}.</span></span> <span data-ttu-id="8c653-136">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="8c653-136">**Required**.</span></span>
<span data-ttu-id="8c653-137">Inhoudstype</span><span class="sxs-lookup"><span data-stu-id="8c653-137">Content-Type</span></span> | <span data-ttu-id="8c653-138">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="8c653-138">string</span></span> | <span data-ttu-id="8c653-139">toepassing/json.</span><span class="sxs-lookup"><span data-stu-id="8c653-139">application/json.</span></span> <span data-ttu-id="8c653-140">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="8c653-140">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="8c653-141">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="8c653-141">Request body</span></span>
<span data-ttu-id="8c653-142">In de objectaanvraag moet u een JSON-object de volgende parameters geven:</span><span class="sxs-lookup"><span data-stu-id="8c653-142">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="8c653-143">Parameter</span><span class="sxs-lookup"><span data-stu-id="8c653-143">Parameter</span></span> | <span data-ttu-id="8c653-144">Type</span><span class="sxs-lookup"><span data-stu-id="8c653-144">Type</span></span>    | <span data-ttu-id="8c653-145">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="8c653-145">Description</span></span>
:---|:---|:---
<span data-ttu-id="8c653-146">Opmerking</span><span class="sxs-lookup"><span data-stu-id="8c653-146">Comment</span></span> |   <span data-ttu-id="8c653-147">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="8c653-147">String</span></span> |    <span data-ttu-id="8c653-148">Opmerking om te koppelen aan de actie.</span><span class="sxs-lookup"><span data-stu-id="8c653-148">Comment to associate with the action.</span></span> <span data-ttu-id="8c653-149">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="8c653-149">**Required**.</span></span>
<span data-ttu-id="8c653-150">Sha1</span><span class="sxs-lookup"><span data-stu-id="8c653-150">Sha1</span></span> |  <span data-ttu-id="8c653-151">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="8c653-151">String</span></span>   | <span data-ttu-id="8c653-152">Sha1 van het bestand om het apparaat te stoppen en in quarantaine te plaatsen.</span><span class="sxs-lookup"><span data-stu-id="8c653-152">Sha1 of the file to stop and quarantine on the device.</span></span> <span data-ttu-id="8c653-153">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="8c653-153">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="8c653-154">Antwoord</span><span class="sxs-lookup"><span data-stu-id="8c653-154">Response</span></span>
<span data-ttu-id="8c653-155">Als dit is gelukt, retourneert deze methode 201: de reactiecode en [de machineactie](machineaction.md) in de antwoordgroep.</span><span class="sxs-lookup"><span data-stu-id="8c653-155">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="8c653-156">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="8c653-156">Example</span></span>

<span data-ttu-id="8c653-157">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="8c653-157">**Request**</span></span>

<span data-ttu-id="8c653-158">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="8c653-158">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/StopAndQuarantineFile 
```

```json
{
  "Comment": "Stop and quarantine file on machine due to alert 441688558380765161_2136280442",
  "Sha1": "87662bc3d60e4200ceaf7aae249d1c343f4b83c9"
}

```
