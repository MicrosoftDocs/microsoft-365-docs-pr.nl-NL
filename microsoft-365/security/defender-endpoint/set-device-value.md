---
title: Apparaatwaarde-API instellen
description: Meer informatie over het opgeven van de waarde van een apparaat met een Microsoft Defender voor Eindpunt-API.
keywords: api's, graph api, ondersteunde api's, tags, machinetags
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 33692ddf62153c0a6aa8f84568d69803af113bc6
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185561"
---
# <a name="set-device-value-api"></a><span data-ttu-id="857b9-104">Apparaatwaarde-API instellen</span><span class="sxs-lookup"><span data-stu-id="857b9-104">Set device value API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="857b9-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="857b9-105">**Applies to:**</span></span>
- [<span data-ttu-id="857b9-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="857b9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="857b9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="857b9-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="857b9-108">**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="857b9-108">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="857b9-109">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="857b9-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="857b9-110">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="857b9-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="857b9-111">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="857b9-111">API description</span></span>

<span data-ttu-id="857b9-112">Stel de apparaatwaarde van een specifieke [computer in.](machine.md)</span><span class="sxs-lookup"><span data-stu-id="857b9-112">Set the device value of a specific [Machine](machine.md).</span></span><br>
<span data-ttu-id="857b9-113">Zie [Apparaatwaarden toewijzen](tvm-assign-device-value.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="857b9-113">See [assign device values](tvm-assign-device-value.md) for more information.</span></span>

## <a name="limitations"></a><span data-ttu-id="857b9-114">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="857b9-114">Limitations</span></span>

1. <span data-ttu-id="857b9-115">U kunt posten op apparaten die het laatst zijn gezien op basis van de geconfigureerde bewaarperiode.</span><span class="sxs-lookup"><span data-stu-id="857b9-115">You can post on devices last seen according to your configured retention period.</span></span>

2. <span data-ttu-id="857b9-116">Tariefbeperkingen voor deze API zijn 100 oproepen per minuut en 1500 oproepen per uur.</span><span class="sxs-lookup"><span data-stu-id="857b9-116">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="857b9-117">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="857b9-117">Permissions</span></span>

<span data-ttu-id="857b9-118">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="857b9-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="857b9-119">Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="857b9-119">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="857b9-120">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="857b9-120">Permission type</span></span> |    <span data-ttu-id="857b9-121">Machtiging</span><span class="sxs-lookup"><span data-stu-id="857b9-121">Permission</span></span>    |    <span data-ttu-id="857b9-122">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="857b9-122">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="857b9-123">Toepassing</span><span class="sxs-lookup"><span data-stu-id="857b9-123">Application</span></span> |    <span data-ttu-id="857b9-124">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="857b9-124">Machine.ReadWrite.All</span></span> |    <span data-ttu-id="857b9-125">'Alle computergegevens lezen en schrijven'</span><span class="sxs-lookup"><span data-stu-id="857b9-125">'Read and write all machine information'</span></span>
<span data-ttu-id="857b9-126">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="857b9-126">Delegated (work or school account)</span></span> | <span data-ttu-id="857b9-127">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="857b9-127">Machine.ReadWrite</span></span> | <span data-ttu-id="857b9-128">'Machinegegevens lezen en schrijven'</span><span class="sxs-lookup"><span data-stu-id="857b9-128">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="857b9-129">Bij het verkrijgen van een token met gebruikersreferenties:</span><span class="sxs-lookup"><span data-stu-id="857b9-129">When obtaining a token using user credentials:</span></span>
>
>- <span data-ttu-id="857b9-130">De gebruiker moet ten minste de volgende rolmachtiging hebben: 'Beveiligingsinstelling beheren'.</span><span class="sxs-lookup"><span data-stu-id="857b9-130">The user needs to have at least the following role permission: 'Manage security setting'.</span></span> <span data-ttu-id="857b9-131">Voor meer informatie (Zie [Rollen maken en beheren](user-roles.md) voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="857b9-131">For more  (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="857b9-132">Gebruiker moet toegang hebben tot de computer, op basis van instellingen voor de machinegroep (Zie [Machinegroepen](machine-groups.md) maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="857b9-132">User needs to have access to the machine, based on machine group settings (See [Create and manage machine groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="857b9-133">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="857b9-133">HTTP request</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/{machineId}/setDeviceValue
```

## <a name="request-headers"></a><span data-ttu-id="857b9-134">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="857b9-134">Request headers</span></span>

<span data-ttu-id="857b9-135">Naam</span><span class="sxs-lookup"><span data-stu-id="857b9-135">Name</span></span> | <span data-ttu-id="857b9-136">Type</span><span class="sxs-lookup"><span data-stu-id="857b9-136">Type</span></span> | <span data-ttu-id="857b9-137">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="857b9-137">Description</span></span>
:---|:---|:---
<span data-ttu-id="857b9-138">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="857b9-138">Authorization</span></span> | <span data-ttu-id="857b9-139">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="857b9-139">String</span></span> | <span data-ttu-id="857b9-140">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="857b9-140">Bearer {token}.</span></span> <span data-ttu-id="857b9-141">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="857b9-141">**Required**.</span></span>
<span data-ttu-id="857b9-142">Inhoudstype</span><span class="sxs-lookup"><span data-stu-id="857b9-142">Content-Type</span></span> | <span data-ttu-id="857b9-143">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="857b9-143">string</span></span> | <span data-ttu-id="857b9-144">toepassing/json.</span><span class="sxs-lookup"><span data-stu-id="857b9-144">application/json.</span></span> <span data-ttu-id="857b9-145">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="857b9-145">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="857b9-146">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="857b9-146">Request body</span></span>

<span data-ttu-id="857b9-147">In de objectaanvraag moet u een JSON-object de volgende parameters geven:</span><span class="sxs-lookup"><span data-stu-id="857b9-147">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="857b9-148">Parameter</span><span class="sxs-lookup"><span data-stu-id="857b9-148">Parameter</span></span> |    <span data-ttu-id="857b9-149">Type</span><span class="sxs-lookup"><span data-stu-id="857b9-149">Type</span></span>    | <span data-ttu-id="857b9-150">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="857b9-150">Description</span></span>
:---|:---|:---
<span data-ttu-id="857b9-151">Apparaatwaarde</span><span class="sxs-lookup"><span data-stu-id="857b9-151">DeviceValue</span></span> |    <span data-ttu-id="857b9-152">Enum</span><span class="sxs-lookup"><span data-stu-id="857b9-152">Enum</span></span> |    <span data-ttu-id="857b9-153">Apparaatwaarde.</span><span class="sxs-lookup"><span data-stu-id="857b9-153">Device value.</span></span> <span data-ttu-id="857b9-154">Toegestane waarden zijn: 'Normaal', 'Laag' en 'Hoog'.</span><span class="sxs-lookup"><span data-stu-id="857b9-154">Allowed values are: 'Normal', 'Low' and 'High'.</span></span> <span data-ttu-id="857b9-155">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="857b9-155">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="857b9-156">Antwoord</span><span class="sxs-lookup"><span data-stu-id="857b9-156">Response</span></span>

<span data-ttu-id="857b9-157">Als dit is gelukt, retourneert deze methode 200 - Ok-antwoordcode en de bijgewerkte machine in de antwoord body.</span><span class="sxs-lookup"><span data-stu-id="857b9-157">If successful, this method returns 200 - Ok response code and the updated Machine in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="857b9-158">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="857b9-158">Example</span></span>

<span data-ttu-id="857b9-159">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="857b9-159">**Request**</span></span>

<span data-ttu-id="857b9-160">Hier is een voorbeeld van een aanvraag die een machinelabel toevoegt.</span><span class="sxs-lookup"><span data-stu-id="857b9-160">Here is an example of a request that adds machine tag.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/setDeviceValue
```

```json
{
  "DeviceValue" : "High"
}
```
