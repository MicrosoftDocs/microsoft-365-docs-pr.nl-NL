---
title: Offboard-machine-API
description: Meer informatie over het gebruik van een API om een apparaat van Windows Defender Advanced Threat Protection (WDATP) te verwijderen.
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
ms.technology: mde
ms.openlocfilehash: 0b3fa5a5daba1aa09eef0f733c7439848ce66a2c
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187122"
---
# <a name="offboard-machine-api"></a><span data-ttu-id="415f5-104">Offboard-machine-API</span><span class="sxs-lookup"><span data-stu-id="415f5-104">Offboard machine API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="415f5-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="415f5-105">**Applies to:**</span></span>
- [<span data-ttu-id="415f5-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="415f5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="415f5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="415f5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="415f5-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="415f5-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="415f5-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="415f5-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 



[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="415f5-110">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="415f5-110">API description</span></span>
<span data-ttu-id="415f5-111">Offboard-apparaat van Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="415f5-111">Offboard device from Defender for Endpoint.</span></span>


## <a name="limitations"></a><span data-ttu-id="415f5-112">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="415f5-112">Limitations</span></span>
 - <span data-ttu-id="415f5-113">Tariefbeperkingen voor deze API zijn 100 oproepen per minuut en 1500 oproepen per uur.</span><span class="sxs-lookup"><span data-stu-id="415f5-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Machine actions note](../../includes/machineactionsnote.md)]

>[!Note]
> <span data-ttu-id="415f5-114">Deze API wordt ondersteund in Windows 10, versie 1703 en hoger of Windows Server 2019 en hoger.</span><span class="sxs-lookup"><span data-stu-id="415f5-114">This API is supported on Windows 10, version 1703 and later, or Windows Server 2019 and later.</span></span> <span data-ttu-id="415f5-115">Deze API wordt niet ondersteund op MacOS- of Linux-apparaten.</span><span class="sxs-lookup"><span data-stu-id="415f5-115">This API is not supported on MacOS or Linux devices.</span></span>

## <a name="permissions"></a><span data-ttu-id="415f5-116">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="415f5-116">Permissions</span></span>
<span data-ttu-id="415f5-117">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="415f5-117">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="415f5-118">Zie Defender voor [eindpunt-API's gebruiken](apis-intro.md) voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="415f5-118">To learn more, including how to choose permissions, see [Use Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="415f5-119">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="415f5-119">Permission type</span></span> |   <span data-ttu-id="415f5-120">Machtiging</span><span class="sxs-lookup"><span data-stu-id="415f5-120">Permission</span></span>  |   <span data-ttu-id="415f5-121">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="415f5-121">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="415f5-122">Toepassing</span><span class="sxs-lookup"><span data-stu-id="415f5-122">Application</span></span> |   <span data-ttu-id="415f5-123">Machine.Offboard</span><span class="sxs-lookup"><span data-stu-id="415f5-123">Machine.Offboard</span></span> |  <span data-ttu-id="415f5-124">'Offboard machine'</span><span class="sxs-lookup"><span data-stu-id="415f5-124">'Offboard machine'</span></span>
<span data-ttu-id="415f5-125">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="415f5-125">Delegated (work or school account)</span></span> |    <span data-ttu-id="415f5-126">Machine.Offboard</span><span class="sxs-lookup"><span data-stu-id="415f5-126">Machine.Offboard</span></span> |  <span data-ttu-id="415f5-127">'Offboard machine'</span><span class="sxs-lookup"><span data-stu-id="415f5-127">'Offboard machine'</span></span>

>[!Note]
> <span data-ttu-id="415f5-128">Bij het verkrijgen van een token met gebruikersreferenties:</span><span class="sxs-lookup"><span data-stu-id="415f5-128">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="415f5-129">De gebruiker moet ad-rol 'Globale beheerder'</span><span class="sxs-lookup"><span data-stu-id="415f5-129">The user needs to 'Global Admin' AD role</span></span>
>- <span data-ttu-id="415f5-130">De gebruiker moet toegang hebben tot het apparaat op basis van apparaatgroepinstellingen (Zie [Apparaatgroepen](machine-groups.md) maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="415f5-130">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="415f5-131">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="415f5-131">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/offboard
```

## <a name="request-headers"></a><span data-ttu-id="415f5-132">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="415f5-132">Request headers</span></span>

<span data-ttu-id="415f5-133">Naam</span><span class="sxs-lookup"><span data-stu-id="415f5-133">Name</span></span> | <span data-ttu-id="415f5-134">Type</span><span class="sxs-lookup"><span data-stu-id="415f5-134">Type</span></span> | <span data-ttu-id="415f5-135">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="415f5-135">Description</span></span>
:---|:---|:---
<span data-ttu-id="415f5-136">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="415f5-136">Authorization</span></span> | <span data-ttu-id="415f5-137">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="415f5-137">String</span></span> | <span data-ttu-id="415f5-138">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="415f5-138">Bearer {token}.</span></span> <span data-ttu-id="415f5-139">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="415f5-139">**Required**.</span></span>
<span data-ttu-id="415f5-140">Inhoudstype</span><span class="sxs-lookup"><span data-stu-id="415f5-140">Content-Type</span></span> | <span data-ttu-id="415f5-141">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="415f5-141">string</span></span> | <span data-ttu-id="415f5-142">toepassing/json.</span><span class="sxs-lookup"><span data-stu-id="415f5-142">application/json.</span></span> <span data-ttu-id="415f5-143">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="415f5-143">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="415f5-144">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="415f5-144">Request body</span></span>
<span data-ttu-id="415f5-145">In de objectaanvraag moet u een JSON-object de volgende parameters geven:</span><span class="sxs-lookup"><span data-stu-id="415f5-145">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="415f5-146">Parameter</span><span class="sxs-lookup"><span data-stu-id="415f5-146">Parameter</span></span> | <span data-ttu-id="415f5-147">Type</span><span class="sxs-lookup"><span data-stu-id="415f5-147">Type</span></span>    | <span data-ttu-id="415f5-148">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="415f5-148">Description</span></span>
:---|:---|:---
<span data-ttu-id="415f5-149">Opmerking</span><span class="sxs-lookup"><span data-stu-id="415f5-149">Comment</span></span> |   <span data-ttu-id="415f5-150">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="415f5-150">String</span></span> |    <span data-ttu-id="415f5-151">Opmerking om te koppelen aan de actie.</span><span class="sxs-lookup"><span data-stu-id="415f5-151">Comment to associate with the action.</span></span> <span data-ttu-id="415f5-152">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="415f5-152">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="415f5-153">Antwoord</span><span class="sxs-lookup"><span data-stu-id="415f5-153">Response</span></span>
<span data-ttu-id="415f5-154">Als dit is gelukt, retourneert deze methode 201: de reactiecode en [de machineactie](machineaction.md) in de antwoordgroep.</span><span class="sxs-lookup"><span data-stu-id="415f5-154">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="415f5-155">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="415f5-155">Example</span></span>

<span data-ttu-id="415f5-156">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="415f5-156">**Request**</span></span>

<span data-ttu-id="415f5-157">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="415f5-157">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/offboard
```

```json
{
  "Comment": "Offboard machine by automation"
}
```
