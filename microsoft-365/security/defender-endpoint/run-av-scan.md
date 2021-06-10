---
title: Antivirusscan-API uitvoeren
description: Gebruik deze API om oproepen te maken die betrekking hebben op het uitvoeren van een antivirusscan op een apparaat.
keywords: api's, graph api, ondersteunde api's, apparaat verwijderen uit isolatie
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
ms.openlocfilehash: 3df703fd84c87a2bd34bb2a81f8c83063e468b17
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771445"
---
# <a name="run-antivirus-scan-api"></a><span data-ttu-id="ca04f-104">Antivirusscan-API uitvoeren</span><span class="sxs-lookup"><span data-stu-id="ca04f-104">Run antivirus scan API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ca04f-105">**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="ca04f-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="ca04f-106">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="ca04f-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ca04f-107">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="ca04f-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="ca04f-108">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="ca04f-108">API description</span></span>
<span data-ttu-id="ca04f-109">Start Microsoft Defender Antivirus scan op een apparaat.</span><span class="sxs-lookup"><span data-stu-id="ca04f-109">Initiate Microsoft Defender Antivirus scan on a device.</span></span>


## <a name="limitations"></a><span data-ttu-id="ca04f-110">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="ca04f-110">Limitations</span></span>
1. <span data-ttu-id="ca04f-111">Tariefbeperkingen voor deze API zijn 100 oproepen per minuut en 1500 oproepen per uur.</span><span class="sxs-lookup"><span data-stu-id="ca04f-111">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="ca04f-112">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="ca04f-112">Permissions</span></span>
<span data-ttu-id="ca04f-113">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="ca04f-113">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="ca04f-114">Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="ca04f-114">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="ca04f-115">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="ca04f-115">Permission type</span></span> |   <span data-ttu-id="ca04f-116">Machtiging</span><span class="sxs-lookup"><span data-stu-id="ca04f-116">Permission</span></span>  |   <span data-ttu-id="ca04f-117">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="ca04f-117">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="ca04f-118">Toepassing</span><span class="sxs-lookup"><span data-stu-id="ca04f-118">Application</span></span> |   <span data-ttu-id="ca04f-119">Machine.Scannen</span><span class="sxs-lookup"><span data-stu-id="ca04f-119">Machine.Scan</span></span> |  <span data-ttu-id="ca04f-120">'Scan machine'</span><span class="sxs-lookup"><span data-stu-id="ca04f-120">'Scan machine'</span></span>
<span data-ttu-id="ca04f-121">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="ca04f-121">Delegated (work or school account)</span></span> |    <span data-ttu-id="ca04f-122">Machine.Scannen</span><span class="sxs-lookup"><span data-stu-id="ca04f-122">Machine.Scan</span></span> |  <span data-ttu-id="ca04f-123">'Scan machine'</span><span class="sxs-lookup"><span data-stu-id="ca04f-123">'Scan machine'</span></span>

>[!Note]
> <span data-ttu-id="ca04f-124">Bij het verkrijgen van een token met gebruikersreferenties:</span><span class="sxs-lookup"><span data-stu-id="ca04f-124">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="ca04f-125">De gebruiker moet ten minste de volgende rolmachtiging hebben: 'Active remediation actions' (Zie [Rollen](user-roles.md) maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="ca04f-125">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="ca04f-126">De gebruiker moet toegang hebben tot het apparaat op basis van apparaatgroepinstellingen (Zie [Apparaatgroepen](machine-groups.md) maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="ca04f-126">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="ca04f-127">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="ca04f-127">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/runAntiVirusScan
```

## <a name="request-headers"></a><span data-ttu-id="ca04f-128">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="ca04f-128">Request headers</span></span>

<span data-ttu-id="ca04f-129">Naam</span><span class="sxs-lookup"><span data-stu-id="ca04f-129">Name</span></span> | <span data-ttu-id="ca04f-130">Type</span><span class="sxs-lookup"><span data-stu-id="ca04f-130">Type</span></span> | <span data-ttu-id="ca04f-131">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="ca04f-131">Description</span></span>
:---|:---|:---
<span data-ttu-id="ca04f-132">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="ca04f-132">Authorization</span></span> | <span data-ttu-id="ca04f-133">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="ca04f-133">String</span></span> | <span data-ttu-id="ca04f-134">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="ca04f-134">Bearer {token}.</span></span> <span data-ttu-id="ca04f-135">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="ca04f-135">**Required**.</span></span>
<span data-ttu-id="ca04f-136">Inhoudstype</span><span class="sxs-lookup"><span data-stu-id="ca04f-136">Content-Type</span></span> | <span data-ttu-id="ca04f-137">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="ca04f-137">string</span></span> | <span data-ttu-id="ca04f-138">toepassing/json</span><span class="sxs-lookup"><span data-stu-id="ca04f-138">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="ca04f-139">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="ca04f-139">Request body</span></span>
<span data-ttu-id="ca04f-140">In de objectaanvraag moet u een JSON-object de volgende parameters geven:</span><span class="sxs-lookup"><span data-stu-id="ca04f-140">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="ca04f-141">Parameter</span><span class="sxs-lookup"><span data-stu-id="ca04f-141">Parameter</span></span> | <span data-ttu-id="ca04f-142">Type</span><span class="sxs-lookup"><span data-stu-id="ca04f-142">Type</span></span>    | <span data-ttu-id="ca04f-143">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="ca04f-143">Description</span></span>
:---|:---|:---
<span data-ttu-id="ca04f-144">Opmerking</span><span class="sxs-lookup"><span data-stu-id="ca04f-144">Comment</span></span> |   <span data-ttu-id="ca04f-145">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="ca04f-145">String</span></span> | <span data-ttu-id="ca04f-146">Opmerking om te koppelen aan de actie.</span><span class="sxs-lookup"><span data-stu-id="ca04f-146">Comment to associate with the action.</span></span> <span data-ttu-id="ca04f-147">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="ca04f-147">**Required**.</span></span>
<span data-ttu-id="ca04f-148">ScanType</span><span class="sxs-lookup"><span data-stu-id="ca04f-148">ScanType</span></span>|   <span data-ttu-id="ca04f-149">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="ca04f-149">String</span></span>  | <span data-ttu-id="ca04f-150">Hiermee wordt het type scan definieert.</span><span class="sxs-lookup"><span data-stu-id="ca04f-150">Defines the type of the Scan.</span></span> <span data-ttu-id="ca04f-151">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="ca04f-151">**Required**.</span></span>

<span data-ttu-id="ca04f-152">**ScanType** bepaalt het type scan dat moet worden uitgevoerd en kan een van de volgende opties zijn:</span><span class="sxs-lookup"><span data-stu-id="ca04f-152">**ScanType** controls the type of scan to perform and can be one of the following:</span></span>

- <span data-ttu-id="ca04f-153">**Snel:** snel scannen op het apparaat</span><span class="sxs-lookup"><span data-stu-id="ca04f-153">**Quick** – Perform quick scan on the device</span></span>
- <span data-ttu-id="ca04f-154">**Volledig:** volledige scan uitvoeren op het apparaat</span><span class="sxs-lookup"><span data-stu-id="ca04f-154">**Full** – Perform full scan on the device</span></span>



## <a name="response"></a><span data-ttu-id="ca04f-155">Antwoord</span><span class="sxs-lookup"><span data-stu-id="ca04f-155">Response</span></span>
<span data-ttu-id="ca04f-156">Als dit is gelukt, retourneert deze methode 201, Gemaakt antwoordcode en _MachineAction-object_ in de antwoord body.</span><span class="sxs-lookup"><span data-stu-id="ca04f-156">If successful, this method returns 201, Created response code and _MachineAction_ object in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="ca04f-157">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="ca04f-157">Example</span></span>

<span data-ttu-id="ca04f-158">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="ca04f-158">**Request**</span></span>

<span data-ttu-id="ca04f-159">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="ca04f-159">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/runAntiVirusScan 
```

```json
{
  "Comment": "Check machine for viruses due to alert 3212",
  "ScanType": "Full"
}
```

