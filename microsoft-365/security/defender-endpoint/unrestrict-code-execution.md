---
title: App-beperkings-API verwijderen
description: Gebruik deze API om oproepen te maken die betrekking hebben op het verwijderen van een beperking uit toepassingen die niet worden uitgevoerd.
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
ms.openlocfilehash: 989e44647a5f0661bfdefa184c6c26f4cdf2b456
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770875"
---
# <a name="remove-app-restriction-api"></a><span data-ttu-id="5daff-104">App-beperkings-API verwijderen</span><span class="sxs-lookup"><span data-stu-id="5daff-104">Remove app restriction API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5daff-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="5daff-105">**Applies to:**</span></span>
- [<span data-ttu-id="5daff-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="5daff-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="5daff-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5daff-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="5daff-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="5daff-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5daff-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="5daff-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="5daff-110">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="5daff-110">API description</span></span>
<span data-ttu-id="5daff-111">De uitvoering van een toepassing op het apparaat inschakelen.</span><span class="sxs-lookup"><span data-stu-id="5daff-111">Enable execution of any application on the device.</span></span>


## <a name="limitations"></a><span data-ttu-id="5daff-112">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="5daff-112">Limitations</span></span>
1. <span data-ttu-id="5daff-113">Tariefbeperkingen voor deze API zijn 100 oproepen per minuut en 1500 oproepen per uur.</span><span class="sxs-lookup"><span data-stu-id="5daff-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="5daff-114">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="5daff-114">Permissions</span></span>
<span data-ttu-id="5daff-115">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="5daff-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="5daff-116">Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="5daff-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="5daff-117">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="5daff-117">Permission type</span></span> |   <span data-ttu-id="5daff-118">Machtiging</span><span class="sxs-lookup"><span data-stu-id="5daff-118">Permission</span></span>  |   <span data-ttu-id="5daff-119">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="5daff-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="5daff-120">Toepassing</span><span class="sxs-lookup"><span data-stu-id="5daff-120">Application</span></span> |   <span data-ttu-id="5daff-121">Machine.RestrictExecution</span><span class="sxs-lookup"><span data-stu-id="5daff-121">Machine.RestrictExecution</span></span> | <span data-ttu-id="5daff-122">'Codeuitvoering beperken'</span><span class="sxs-lookup"><span data-stu-id="5daff-122">'Restrict code execution'</span></span>
<span data-ttu-id="5daff-123">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="5daff-123">Delegated (work or school account)</span></span> | <span data-ttu-id="5daff-124">Machine.RestrictExecution</span><span class="sxs-lookup"><span data-stu-id="5daff-124">Machine.RestrictExecution</span></span> | <span data-ttu-id="5daff-125">'Codeuitvoering beperken'</span><span class="sxs-lookup"><span data-stu-id="5daff-125">'Restrict code execution'</span></span>

>[!Note]
> <span data-ttu-id="5daff-126">Bij het verkrijgen van een token met gebruikersreferenties:</span><span class="sxs-lookup"><span data-stu-id="5daff-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="5daff-127">De gebruiker moet ten minste de volgende rolmachtiging hebben: 'Active remediation actions' (Zie [Rollen](user-roles.md) maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="5daff-127">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="5daff-128">De gebruiker moet toegang hebben tot het apparaat op basis van apparaatgroepinstellingen (Zie [Apparaatgroepen](machine-groups.md) maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="5daff-128">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="5daff-129">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="5daff-129">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/unrestrictCodeExecution
```

## <a name="request-headers"></a><span data-ttu-id="5daff-130">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="5daff-130">Request headers</span></span>
<span data-ttu-id="5daff-131">Naam</span><span class="sxs-lookup"><span data-stu-id="5daff-131">Name</span></span> | <span data-ttu-id="5daff-132">Type</span><span class="sxs-lookup"><span data-stu-id="5daff-132">Type</span></span> | <span data-ttu-id="5daff-133">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="5daff-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="5daff-134">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="5daff-134">Authorization</span></span> | <span data-ttu-id="5daff-135">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="5daff-135">String</span></span> | <span data-ttu-id="5daff-136">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="5daff-136">Bearer {token}.</span></span> <span data-ttu-id="5daff-137">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="5daff-137">**Required**.</span></span>
<span data-ttu-id="5daff-138">Inhoudstype</span><span class="sxs-lookup"><span data-stu-id="5daff-138">Content-Type</span></span> | <span data-ttu-id="5daff-139">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="5daff-139">string</span></span> | <span data-ttu-id="5daff-140">toepassing/json.</span><span class="sxs-lookup"><span data-stu-id="5daff-140">application/json.</span></span> <span data-ttu-id="5daff-141">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="5daff-141">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="5daff-142">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="5daff-142">Request body</span></span>
<span data-ttu-id="5daff-143">In de objectaanvraag moet u een JSON-object de volgende parameters geven:</span><span class="sxs-lookup"><span data-stu-id="5daff-143">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="5daff-144">Parameter</span><span class="sxs-lookup"><span data-stu-id="5daff-144">Parameter</span></span> | <span data-ttu-id="5daff-145">Type</span><span class="sxs-lookup"><span data-stu-id="5daff-145">Type</span></span>    | <span data-ttu-id="5daff-146">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="5daff-146">Description</span></span>
:---|:---|:---
<span data-ttu-id="5daff-147">Opmerking</span><span class="sxs-lookup"><span data-stu-id="5daff-147">Comment</span></span> |   <span data-ttu-id="5daff-148">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="5daff-148">String</span></span> | <span data-ttu-id="5daff-149">Opmerking om te koppelen aan de actie.</span><span class="sxs-lookup"><span data-stu-id="5daff-149">Comment to associate with the action.</span></span> <span data-ttu-id="5daff-150">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="5daff-150">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="5daff-151">Antwoord</span><span class="sxs-lookup"><span data-stu-id="5daff-151">Response</span></span>
<span data-ttu-id="5daff-152">Als dit is gelukt, retourneert deze methode 201: de reactiecode en [de machineactie](machineaction.md) in de antwoordgroep.</span><span class="sxs-lookup"><span data-stu-id="5daff-152">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="5daff-153">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="5daff-153">Example</span></span>

<span data-ttu-id="5daff-154">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="5daff-154">**Request**</span></span>

<span data-ttu-id="5daff-155">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="5daff-155">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/unrestrictCodeExecution 
```

```json
{
  "Comment": "Unrestrict code execution since machine was cleaned and validated"
}

```


<span data-ttu-id="5daff-156">Zie De uitvoering van apps beperken als u de uitvoering van code op een apparaat [wilt beperken.](restrict-code-execution.md)</span><span class="sxs-lookup"><span data-stu-id="5daff-156">To restrict code execution on a device, see [Restrict app execution](restrict-code-execution.md).</span></span>
