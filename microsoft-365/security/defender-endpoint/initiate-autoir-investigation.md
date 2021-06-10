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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: b7a6a3e7f6f705f322ee3eb1c1b561bc01c55d29
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770887"
---
# <a name="start-investigation-api"></a><span data-ttu-id="fd042-104">Api voor onderzoek starten</span><span class="sxs-lookup"><span data-stu-id="fd042-104">Start Investigation API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="fd042-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="fd042-105">**Applies to:**</span></span>
- [<span data-ttu-id="fd042-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="fd042-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="fd042-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fd042-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="fd042-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="fd042-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="fd042-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="fd042-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="fd042-110">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="fd042-110">API description</span></span>
<span data-ttu-id="fd042-111">Start automatisch onderzoek op een apparaat.</span><span class="sxs-lookup"><span data-stu-id="fd042-111">Start automated investigation on a device.</span></span>
<br><span data-ttu-id="fd042-112">Zie [Overzicht van geautomatiseerde onderzoeken voor](automated-investigations.md) meer informatie.</span><span class="sxs-lookup"><span data-stu-id="fd042-112">See [Overview of automated investigations](automated-investigations.md) for more information.</span></span>


## <a name="limitations"></a><span data-ttu-id="fd042-113">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="fd042-113">Limitations</span></span>
1. <span data-ttu-id="fd042-114">Tariefbeperkingen voor deze API zijn 50 oproepen per uur.</span><span class="sxs-lookup"><span data-stu-id="fd042-114">Rate limitations for this API are 50 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="fd042-115">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="fd042-115">Permissions</span></span>
<span data-ttu-id="fd042-116">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="fd042-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="fd042-117">Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="fd042-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="fd042-118">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="fd042-118">Permission type</span></span> |   <span data-ttu-id="fd042-119">Machtiging</span><span class="sxs-lookup"><span data-stu-id="fd042-119">Permission</span></span>  |   <span data-ttu-id="fd042-120">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="fd042-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="fd042-121">Toepassing</span><span class="sxs-lookup"><span data-stu-id="fd042-121">Application</span></span> |   <span data-ttu-id="fd042-122">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="fd042-122">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="fd042-123">'Alle waarschuwingen lezen en schrijven'</span><span class="sxs-lookup"><span data-stu-id="fd042-123">'Read and write all alerts'</span></span>
<span data-ttu-id="fd042-124">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="fd042-124">Delegated (work or school account)</span></span> | <span data-ttu-id="fd042-125">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="fd042-125">Alert.ReadWrite</span></span> | <span data-ttu-id="fd042-126">'Waarschuwingen lezen en schrijven'</span><span class="sxs-lookup"><span data-stu-id="fd042-126">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="fd042-127">Bij het verkrijgen van een token met gebruikersreferenties:</span><span class="sxs-lookup"><span data-stu-id="fd042-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="fd042-128">De gebruiker moet ten minste de volgende rolmachtiging hebben: 'Active remediation actions' (Zie [Rollen](user-roles.md) maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="fd042-128">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="fd042-129">De gebruiker moet toegang hebben tot het apparaat op basis van apparaatgroepinstellingen (Zie [Apparaatgroepen](machine-groups.md) maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="fd042-129">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>


## <a name="http-request"></a><span data-ttu-id="fd042-130">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="fd042-130">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/startInvestigation
```

## <a name="request-headers"></a><span data-ttu-id="fd042-131">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="fd042-131">Request headers</span></span>

<span data-ttu-id="fd042-132">Naam</span><span class="sxs-lookup"><span data-stu-id="fd042-132">Name</span></span> | <span data-ttu-id="fd042-133">Type</span><span class="sxs-lookup"><span data-stu-id="fd042-133">Type</span></span> | <span data-ttu-id="fd042-134">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="fd042-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="fd042-135">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="fd042-135">Authorization</span></span> | <span data-ttu-id="fd042-136">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="fd042-136">String</span></span> | <span data-ttu-id="fd042-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="fd042-137">Bearer {token}.</span></span> <span data-ttu-id="fd042-138">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="fd042-138">**Required**.</span></span>
<span data-ttu-id="fd042-139">Inhoudstype</span><span class="sxs-lookup"><span data-stu-id="fd042-139">Content-Type</span></span> | <span data-ttu-id="fd042-140">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="fd042-140">string</span></span> | <span data-ttu-id="fd042-141">toepassing/json.</span><span class="sxs-lookup"><span data-stu-id="fd042-141">application/json.</span></span> <span data-ttu-id="fd042-142">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="fd042-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="fd042-143">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="fd042-143">Request body</span></span>
<span data-ttu-id="fd042-144">In de objectaanvraag moet u een JSON-object de volgende parameters geven:</span><span class="sxs-lookup"><span data-stu-id="fd042-144">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="fd042-145">Parameter</span><span class="sxs-lookup"><span data-stu-id="fd042-145">Parameter</span></span> | <span data-ttu-id="fd042-146">Type</span><span class="sxs-lookup"><span data-stu-id="fd042-146">Type</span></span>    | <span data-ttu-id="fd042-147">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="fd042-147">Description</span></span>
:---|:---|:---
<span data-ttu-id="fd042-148">Opmerking</span><span class="sxs-lookup"><span data-stu-id="fd042-148">Comment</span></span> |   <span data-ttu-id="fd042-149">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="fd042-149">String</span></span> |    <span data-ttu-id="fd042-150">Opmerking om te koppelen aan de actie.</span><span class="sxs-lookup"><span data-stu-id="fd042-150">Comment to associate with the action.</span></span> <span data-ttu-id="fd042-151">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="fd042-151">**Required**.</span></span>


## <a name="response"></a><span data-ttu-id="fd042-152">Antwoord</span><span class="sxs-lookup"><span data-stu-id="fd042-152">Response</span></span>
<span data-ttu-id="fd042-153">Als dit is gelukt, retourneert deze methode 201: Reactiecode gemaakt en [Onderzoek](investigation.md) in de antwoord-body.</span><span class="sxs-lookup"><span data-stu-id="fd042-153">If successful, this method returns 201 - Created response code and [Investigation](investigation.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="fd042-154">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="fd042-154">Example</span></span>

<span data-ttu-id="fd042-155">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="fd042-155">**Request**</span></span>

<span data-ttu-id="fd042-156">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="fd042-156">Here is an example of the request.</span></span>

```https
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/startInvestigation
```

```json
{
  "Comment": "Test investigation"
}
```
