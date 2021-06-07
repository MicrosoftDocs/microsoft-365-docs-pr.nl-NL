---
title: Api voor onderzoekspakket verzamelen
description: Gebruik deze API om oproepen te maken die betrekking hebben op het verzamelen van een onderzoekspakket vanaf een apparaat.
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
ms.openlocfilehash: 0083d806f3e52307e6dce30f74e255073a09c16a
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770491"
---
# <a name="collect-investigation-package-api"></a><span data-ttu-id="22963-104">Api voor onderzoekspakket verzamelen</span><span class="sxs-lookup"><span data-stu-id="22963-104">Collect investigation package API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="22963-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="22963-105">**Applies to:**</span></span>
- [<span data-ttu-id="22963-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="22963-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="22963-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="22963-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


- <span data-ttu-id="22963-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="22963-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="22963-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="22963-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="22963-110">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="22963-110">API description</span></span>
<span data-ttu-id="22963-111">Verzamel een onderzoekspakket vanaf een apparaat.</span><span class="sxs-lookup"><span data-stu-id="22963-111">Collect investigation package from a device.</span></span>


## <a name="limitations"></a><span data-ttu-id="22963-112">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="22963-112">Limitations</span></span>
1. <span data-ttu-id="22963-113">Tariefbeperkingen voor deze API zijn 100 oproepen per minuut en 1500 oproepen per uur.</span><span class="sxs-lookup"><span data-stu-id="22963-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="22963-114">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="22963-114">Permissions</span></span>
<span data-ttu-id="22963-115">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="22963-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="22963-116">Zie Defender voor [eindpunt-API's gebruiken](apis-intro.md) voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="22963-116">To learn more, including how to choose permissions, see [Use Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="22963-117">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="22963-117">Permission type</span></span> |   <span data-ttu-id="22963-118">Machtiging</span><span class="sxs-lookup"><span data-stu-id="22963-118">Permission</span></span>  |   <span data-ttu-id="22963-119">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="22963-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="22963-120">Toepassing</span><span class="sxs-lookup"><span data-stu-id="22963-120">Application</span></span> |   <span data-ttu-id="22963-121">Machine.CollectForensics</span><span class="sxs-lookup"><span data-stu-id="22963-121">Machine.CollectForensics</span></span> |  <span data-ttu-id="22963-122">'Forensics verzamelen'</span><span class="sxs-lookup"><span data-stu-id="22963-122">'Collect forensics'</span></span>
<span data-ttu-id="22963-123">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="22963-123">Delegated (work or school account)</span></span> |    <span data-ttu-id="22963-124">Machine.CollectForensics</span><span class="sxs-lookup"><span data-stu-id="22963-124">Machine.CollectForensics</span></span> |  <span data-ttu-id="22963-125">'Forensics verzamelen'</span><span class="sxs-lookup"><span data-stu-id="22963-125">'Collect forensics'</span></span>

>[!Note]
> <span data-ttu-id="22963-126">Bij het verkrijgen van een token met gebruikersreferenties:</span><span class="sxs-lookup"><span data-stu-id="22963-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="22963-127">De gebruiker moet ten minste de volgende rolmachtiging hebben: 'Alerts Investigation' (Zie Rollen maken [en](user-roles.md) beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="22963-127">The user needs to have at least the following role permission: 'Alerts Investigation' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="22963-128">De gebruiker moet toegang hebben tot het apparaat op basis van apparaatgroepinstellingen (Zie [Apparaatgroepen](machine-groups.md) maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="22963-128">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="22963-129">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="22963-129">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/collectInvestigationPackage
```

## <a name="request-headers"></a><span data-ttu-id="22963-130">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="22963-130">Request headers</span></span>

<span data-ttu-id="22963-131">Naam</span><span class="sxs-lookup"><span data-stu-id="22963-131">Name</span></span> | <span data-ttu-id="22963-132">Type</span><span class="sxs-lookup"><span data-stu-id="22963-132">Type</span></span> | <span data-ttu-id="22963-133">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="22963-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="22963-134">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="22963-134">Authorization</span></span> | <span data-ttu-id="22963-135">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="22963-135">String</span></span> | <span data-ttu-id="22963-136">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="22963-136">Bearer {token}.</span></span> <span data-ttu-id="22963-137">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="22963-137">**Required**.</span></span>
<span data-ttu-id="22963-138">Inhoudstype</span><span class="sxs-lookup"><span data-stu-id="22963-138">Content-Type</span></span> | <span data-ttu-id="22963-139">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="22963-139">string</span></span> | <span data-ttu-id="22963-140">toepassing/json.</span><span class="sxs-lookup"><span data-stu-id="22963-140">application/json.</span></span> <span data-ttu-id="22963-141">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="22963-141">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="22963-142">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="22963-142">Request body</span></span>
<span data-ttu-id="22963-143">In de objectaanvraag moet u een JSON-object de volgende parameters geven:</span><span class="sxs-lookup"><span data-stu-id="22963-143">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="22963-144">Parameter</span><span class="sxs-lookup"><span data-stu-id="22963-144">Parameter</span></span> | <span data-ttu-id="22963-145">Type</span><span class="sxs-lookup"><span data-stu-id="22963-145">Type</span></span>    | <span data-ttu-id="22963-146">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="22963-146">Description</span></span>
:---|:---|:---
<span data-ttu-id="22963-147">Opmerking</span><span class="sxs-lookup"><span data-stu-id="22963-147">Comment</span></span> |   <span data-ttu-id="22963-148">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="22963-148">String</span></span> |    <span data-ttu-id="22963-149">Opmerking om te koppelen aan de actie.</span><span class="sxs-lookup"><span data-stu-id="22963-149">Comment to associate with the action.</span></span> <span data-ttu-id="22963-150">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="22963-150">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="22963-151">Antwoord</span><span class="sxs-lookup"><span data-stu-id="22963-151">Response</span></span>
<span data-ttu-id="22963-152">Als dit is gelukt, retourneert deze methode 201: de reactiecode en [de machineactie](machineaction.md) in de antwoordgroep.</span><span class="sxs-lookup"><span data-stu-id="22963-152">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="22963-153">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="22963-153">Example</span></span>

<span data-ttu-id="22963-154">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="22963-154">**Request**</span></span>

<span data-ttu-id="22963-155">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="22963-155">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/fb9ab6be3965095a09c057be7c90f0a2/collectInvestigationPackage
```

```json
{
  "Comment": "Collect forensics due to alert 1234"
}
```
