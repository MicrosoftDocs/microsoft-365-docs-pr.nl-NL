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
ms.openlocfilehash: 4cf60ea73ea907be9c10b2dd9562a0ea60127f2d
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289893"
---
# <a name="collect-investigation-package-api"></a><span data-ttu-id="c00b9-104">Api voor onderzoekspakket verzamelen</span><span class="sxs-lookup"><span data-stu-id="c00b9-104">Collect investigation package API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c00b9-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="c00b9-105">**Applies to:**</span></span>
- [<span data-ttu-id="c00b9-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="c00b9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c00b9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c00b9-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


- <span data-ttu-id="c00b9-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="c00b9-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c00b9-109">Meld u aan voor een gratis proefversie.</span><span class="sxs-lookup"><span data-stu-id="c00b9-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="c00b9-110">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="c00b9-110">API description</span></span>

<span data-ttu-id="c00b9-111">Verzamel een onderzoekspakket vanaf een apparaat.</span><span class="sxs-lookup"><span data-stu-id="c00b9-111">Collect investigation package from a device.</span></span>

## <a name="limitations"></a><span data-ttu-id="c00b9-112">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="c00b9-112">Limitations</span></span>

1. <span data-ttu-id="c00b9-113">Tariefbeperkingen voor deze API zijn 100 oproepen per minuut en 1500 oproepen per uur.</span><span class="sxs-lookup"><span data-stu-id="c00b9-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="c00b9-114">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="c00b9-114">Permissions</span></span>

<span data-ttu-id="c00b9-115">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="c00b9-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="c00b9-116">Zie Defender voor [eindpunt-API's gebruiken](apis-intro.md) voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="c00b9-116">To learn more, including how to choose permissions, see [Use Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="c00b9-117">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="c00b9-117">Permission type</span></span> | <span data-ttu-id="c00b9-118">Machtiging</span><span class="sxs-lookup"><span data-stu-id="c00b9-118">Permission</span></span> | <span data-ttu-id="c00b9-119">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="c00b9-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="c00b9-120">Toepassing</span><span class="sxs-lookup"><span data-stu-id="c00b9-120">Application</span></span> | <span data-ttu-id="c00b9-121">Machine.CollectForensics</span><span class="sxs-lookup"><span data-stu-id="c00b9-121">Machine.CollectForensics</span></span> | <span data-ttu-id="c00b9-122">'Forensics verzamelen'</span><span class="sxs-lookup"><span data-stu-id="c00b9-122">'Collect forensics'</span></span>
<span data-ttu-id="c00b9-123">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="c00b9-123">Delegated (work or school account)</span></span> | <span data-ttu-id="c00b9-124">Machine.CollectForensics</span><span class="sxs-lookup"><span data-stu-id="c00b9-124">Machine.CollectForensics</span></span> | <span data-ttu-id="c00b9-125">'Forensics verzamelen'</span><span class="sxs-lookup"><span data-stu-id="c00b9-125">'Collect forensics'</span></span>

> [!NOTE]
> <span data-ttu-id="c00b9-126">Bij het verkrijgen van een token met gebruikersreferenties:</span><span class="sxs-lookup"><span data-stu-id="c00b9-126">When obtaining a token using user credentials:</span></span>
>
> - <span data-ttu-id="c00b9-127">De gebruiker moet ten minste de volgende rolmachtiging hebben: 'Alerts Investigation' (Zie Rollen maken [en](user-roles.md) beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="c00b9-127">The user needs to have at least the following role permission: 'Alerts Investigation' (See [Create and manage roles](user-roles.md) for more information)</span></span>
> - <span data-ttu-id="c00b9-128">De gebruiker moet toegang hebben tot het apparaat op basis van apparaatgroepinstellingen (Zie [Apparaatgroepen](machine-groups.md) maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="c00b9-128">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="c00b9-129">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="c00b9-129">HTTP request</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/{id}/collectInvestigationPackage
```

## <a name="request-headers"></a><span data-ttu-id="c00b9-130">Aanvraagheaders</span><span class="sxs-lookup"><span data-stu-id="c00b9-130">Request headers</span></span>

<span data-ttu-id="c00b9-131">Naam</span><span class="sxs-lookup"><span data-stu-id="c00b9-131">Name</span></span> | <span data-ttu-id="c00b9-132">Type</span><span class="sxs-lookup"><span data-stu-id="c00b9-132">Type</span></span> | <span data-ttu-id="c00b9-133">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="c00b9-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="c00b9-134">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="c00b9-134">Authorization</span></span> | <span data-ttu-id="c00b9-135">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="c00b9-135">String</span></span> | <span data-ttu-id="c00b9-136">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="c00b9-136">Bearer {token}.</span></span> <span data-ttu-id="c00b9-137">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="c00b9-137">**Required**.</span></span>
<span data-ttu-id="c00b9-138">Content-Type</span><span class="sxs-lookup"><span data-stu-id="c00b9-138">Content-Type</span></span> | <span data-ttu-id="c00b9-139">reeks</span><span class="sxs-lookup"><span data-stu-id="c00b9-139">string</span></span> | <span data-ttu-id="c00b9-140">toepassing/json.</span><span class="sxs-lookup"><span data-stu-id="c00b9-140">application/json.</span></span> <span data-ttu-id="c00b9-141">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="c00b9-141">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="c00b9-142">Aanvraagtekst</span><span class="sxs-lookup"><span data-stu-id="c00b9-142">Request body</span></span>

<span data-ttu-id="c00b9-143">In de objectaanvraag moet u een JSON-object de volgende parameters geven:</span><span class="sxs-lookup"><span data-stu-id="c00b9-143">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="c00b9-144">Parameter</span><span class="sxs-lookup"><span data-stu-id="c00b9-144">Parameter</span></span> | <span data-ttu-id="c00b9-145">Type</span><span class="sxs-lookup"><span data-stu-id="c00b9-145">Type</span></span> | <span data-ttu-id="c00b9-146">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="c00b9-146">Description</span></span>
:---|:---|:---
<span data-ttu-id="c00b9-147">Opmerking</span><span class="sxs-lookup"><span data-stu-id="c00b9-147">Comment</span></span> | <span data-ttu-id="c00b9-148">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="c00b9-148">String</span></span> | <span data-ttu-id="c00b9-149">Opmerking om te koppelen aan de actie.</span><span class="sxs-lookup"><span data-stu-id="c00b9-149">Comment to associate with the action.</span></span> <span data-ttu-id="c00b9-150">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="c00b9-150">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="c00b9-151">Antwoord</span><span class="sxs-lookup"><span data-stu-id="c00b9-151">Response</span></span>

<span data-ttu-id="c00b9-152">Als dit is gelukt, retourneert deze methode 201: de reactiecode en [de machineactie](machineaction.md) in de antwoordgroep.</span><span class="sxs-lookup"><span data-stu-id="c00b9-152">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="c00b9-153">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="c00b9-153">Example</span></span>

### <a name="request"></a><span data-ttu-id="c00b9-154">Aanvraag</span><span class="sxs-lookup"><span data-stu-id="c00b9-154">Request</span></span>

<span data-ttu-id="c00b9-155">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="c00b9-155">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/fb9ab6be3965095a09c057be7c90f0a2/collectInvestigationPackage
```

```json
{
  "Comment": "Collect forensics due to alert 1234"
}
```
