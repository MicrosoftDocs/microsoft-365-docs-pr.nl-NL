---
title: Api voor onderzoek starten
description: Gebruik deze API om een onderzoek op een apparaat te starten.
keywords: api's, graph api, ondersteunde api's, onderzoek
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
ms.openlocfilehash: 4bdbfbb20f3abb9829b2c8be83b9eaa6ec92cde7
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187114"
---
# <a name="start-investigation-api"></a><span data-ttu-id="49509-104">Api voor onderzoek starten</span><span class="sxs-lookup"><span data-stu-id="49509-104">Start Investigation API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="49509-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="49509-105">**Applies to:**</span></span>
- [<span data-ttu-id="49509-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="49509-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="49509-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="49509-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="49509-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="49509-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="49509-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="49509-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="49509-110">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="49509-110">API description</span></span>
<span data-ttu-id="49509-111">Start automatisch onderzoek op een apparaat.</span><span class="sxs-lookup"><span data-stu-id="49509-111">Start automated investigation on a device.</span></span>
<br><span data-ttu-id="49509-112">Zie [Overzicht van geautomatiseerde onderzoeken voor](automated-investigations.md) meer informatie.</span><span class="sxs-lookup"><span data-stu-id="49509-112">See [Overview of automated investigations](automated-investigations.md) for more information.</span></span>


## <a name="limitations"></a><span data-ttu-id="49509-113">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="49509-113">Limitations</span></span>
1. <span data-ttu-id="49509-114">Tariefbeperkingen voor deze API zijn 50 oproepen per uur.</span><span class="sxs-lookup"><span data-stu-id="49509-114">Rate limitations for this API are 50 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="49509-115">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="49509-115">Permissions</span></span>
<span data-ttu-id="49509-116">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="49509-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="49509-117">Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="49509-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="49509-118">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="49509-118">Permission type</span></span> |   <span data-ttu-id="49509-119">Machtiging</span><span class="sxs-lookup"><span data-stu-id="49509-119">Permission</span></span>  |   <span data-ttu-id="49509-120">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="49509-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="49509-121">Toepassing</span><span class="sxs-lookup"><span data-stu-id="49509-121">Application</span></span> |   <span data-ttu-id="49509-122">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="49509-122">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="49509-123">'Alle waarschuwingen lezen en schrijven'</span><span class="sxs-lookup"><span data-stu-id="49509-123">'Read and write all alerts'</span></span>
<span data-ttu-id="49509-124">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="49509-124">Delegated (work or school account)</span></span> | <span data-ttu-id="49509-125">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="49509-125">Alert.ReadWrite</span></span> | <span data-ttu-id="49509-126">'Waarschuwingen lezen en schrijven'</span><span class="sxs-lookup"><span data-stu-id="49509-126">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="49509-127">Bij het verkrijgen van een token met gebruikersreferenties:</span><span class="sxs-lookup"><span data-stu-id="49509-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="49509-128">De gebruiker moet ten minste de volgende rolmachtiging hebben: 'Active remediation actions' (Zie [Rollen](user-roles.md) maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="49509-128">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="49509-129">De gebruiker moet toegang hebben tot het apparaat op basis van apparaatgroepinstellingen (Zie [Apparaatgroepen](machine-groups.md) maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="49509-129">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>


## <a name="http-request"></a><span data-ttu-id="49509-130">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="49509-130">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/startInvestigation
```

## <a name="request-headers"></a><span data-ttu-id="49509-131">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="49509-131">Request headers</span></span>

<span data-ttu-id="49509-132">Naam</span><span class="sxs-lookup"><span data-stu-id="49509-132">Name</span></span> | <span data-ttu-id="49509-133">Type</span><span class="sxs-lookup"><span data-stu-id="49509-133">Type</span></span> | <span data-ttu-id="49509-134">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="49509-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="49509-135">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="49509-135">Authorization</span></span> | <span data-ttu-id="49509-136">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="49509-136">String</span></span> | <span data-ttu-id="49509-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="49509-137">Bearer {token}.</span></span> <span data-ttu-id="49509-138">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="49509-138">**Required**.</span></span>
<span data-ttu-id="49509-139">Inhoudstype</span><span class="sxs-lookup"><span data-stu-id="49509-139">Content-Type</span></span> | <span data-ttu-id="49509-140">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="49509-140">string</span></span> | <span data-ttu-id="49509-141">toepassing/json.</span><span class="sxs-lookup"><span data-stu-id="49509-141">application/json.</span></span> <span data-ttu-id="49509-142">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="49509-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="49509-143">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="49509-143">Request body</span></span>
<span data-ttu-id="49509-144">In de objectaanvraag moet u een JSON-object de volgende parameters geven:</span><span class="sxs-lookup"><span data-stu-id="49509-144">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="49509-145">Parameter</span><span class="sxs-lookup"><span data-stu-id="49509-145">Parameter</span></span> | <span data-ttu-id="49509-146">Type</span><span class="sxs-lookup"><span data-stu-id="49509-146">Type</span></span>    | <span data-ttu-id="49509-147">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="49509-147">Description</span></span>
:---|:---|:---
<span data-ttu-id="49509-148">Opmerking</span><span class="sxs-lookup"><span data-stu-id="49509-148">Comment</span></span> |   <span data-ttu-id="49509-149">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="49509-149">String</span></span> |    <span data-ttu-id="49509-150">Opmerking om te koppelen aan de actie.</span><span class="sxs-lookup"><span data-stu-id="49509-150">Comment to associate with the action.</span></span> <span data-ttu-id="49509-151">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="49509-151">**Required**.</span></span>


## <a name="response"></a><span data-ttu-id="49509-152">Antwoord</span><span class="sxs-lookup"><span data-stu-id="49509-152">Response</span></span>
<span data-ttu-id="49509-153">Als dit is gelukt, retourneert deze methode 201: Reactiecode gemaakt en [Onderzoek](investigation.md) in de antwoord-body.</span><span class="sxs-lookup"><span data-stu-id="49509-153">If successful, this method returns 201 - Created response code and [Investigation](investigation.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="49509-154">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="49509-154">Example</span></span>

<span data-ttu-id="49509-155">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="49509-155">**Request**</span></span>

<span data-ttu-id="49509-156">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="49509-156">Here is an example of the request.</span></span>

```https
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/startInvestigation
```

```json
{
  "Comment": "Test investigation"
}
```
