---
title: Api voor indicator verzenden of bijwerken
description: Lees hoe u de API Voor verzenden of bijwerken kunt gebruiken om een nieuwe indicatorentiteit in Microsoft Defender voor eindpunt in te dienen of bij te werken.
keywords: api's, graph api, ondersteunde api's, submit, ti, indicator, update
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
ms.openlocfilehash: ce0dc0ce255e9717082687bd1f8bf5941739261d
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771703"
---
# <a name="submit-or-update-indicator-api"></a><span data-ttu-id="3b148-104">Api voor indicator verzenden of bijwerken</span><span class="sxs-lookup"><span data-stu-id="3b148-104">Submit or Update Indicator API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3b148-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="3b148-105">**Applies to:**</span></span>
- [<span data-ttu-id="3b148-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="3b148-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3b148-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3b148-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="3b148-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="3b148-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="3b148-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="3b148-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="3b148-110">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="3b148-110">API description</span></span>
<span data-ttu-id="3b148-111">Verstuurt of werkt de nieuwe [indicatorentiteit](ti-indicator.md) bij.</span><span class="sxs-lookup"><span data-stu-id="3b148-111">Submits or Updates new [Indicator](ti-indicator.md) entity.</span></span>
<br><span data-ttu-id="3b148-112">CIDR-notatie voor IPs wordt niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="3b148-112">CIDR notation for IPs is not supported.</span></span>

## <a name="limitations"></a><span data-ttu-id="3b148-113">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="3b148-113">Limitations</span></span>
1. <span data-ttu-id="3b148-114">Tariefbeperkingen voor deze API zijn 100 oproepen per minuut en 1500 oproepen per uur.</span><span class="sxs-lookup"><span data-stu-id="3b148-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>
2. <span data-ttu-id="3b148-115">Er is een limiet van 15.000 actieve indicatoren per tenant.</span><span class="sxs-lookup"><span data-stu-id="3b148-115">There is a limit of 15,000 active indicators per tenant.</span></span> 


## <a name="permissions"></a><span data-ttu-id="3b148-116">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="3b148-116">Permissions</span></span>
<span data-ttu-id="3b148-117">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="3b148-117">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="3b148-118">Zie Aan de slag voor meer informatie, inclusief het kiezen van [machtigingen.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="3b148-118">To learn more, including how to choose permissions, see [Get started](apis-intro.md)</span></span>

<span data-ttu-id="3b148-119">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="3b148-119">Permission type</span></span> |   <span data-ttu-id="3b148-120">Machtiging</span><span class="sxs-lookup"><span data-stu-id="3b148-120">Permission</span></span>  |   <span data-ttu-id="3b148-121">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="3b148-121">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="3b148-122">Toepassing</span><span class="sxs-lookup"><span data-stu-id="3b148-122">Application</span></span> |   <span data-ttu-id="3b148-123">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="3b148-123">Ti.ReadWrite</span></span> |  <span data-ttu-id="3b148-124">'Indicatoren lezen en schrijven'</span><span class="sxs-lookup"><span data-stu-id="3b148-124">'Read and write Indicators'</span></span>
<span data-ttu-id="3b148-125">Toepassing</span><span class="sxs-lookup"><span data-stu-id="3b148-125">Application</span></span> |   <span data-ttu-id="3b148-126">Ti.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="3b148-126">Ti.ReadWrite.All</span></span> |  <span data-ttu-id="3b148-127">'Alle indicatoren lezen en schrijven'</span><span class="sxs-lookup"><span data-stu-id="3b148-127">'Read and write All Indicators'</span></span>
<span data-ttu-id="3b148-128">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="3b148-128">Delegated (work or school account)</span></span> |    <span data-ttu-id="3b148-129">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="3b148-129">Ti.ReadWrite</span></span> |  <span data-ttu-id="3b148-130">'Indicatoren lezen en schrijven'</span><span class="sxs-lookup"><span data-stu-id="3b148-130">'Read and write Indicators'</span></span>


## <a name="http-request"></a><span data-ttu-id="3b148-131">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="3b148-131">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/indicators
```

## <a name="request-headers"></a><span data-ttu-id="3b148-132">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="3b148-132">Request headers</span></span>

<span data-ttu-id="3b148-133">Naam</span><span class="sxs-lookup"><span data-stu-id="3b148-133">Name</span></span> | <span data-ttu-id="3b148-134">Type</span><span class="sxs-lookup"><span data-stu-id="3b148-134">Type</span></span> | <span data-ttu-id="3b148-135">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="3b148-135">Description</span></span>
:---|:---|:---
<span data-ttu-id="3b148-136">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="3b148-136">Authorization</span></span> | <span data-ttu-id="3b148-137">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="3b148-137">String</span></span> | <span data-ttu-id="3b148-138">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="3b148-138">Bearer {token}.</span></span> <span data-ttu-id="3b148-139">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="3b148-139">**Required**.</span></span>
<span data-ttu-id="3b148-140">Inhoudstype</span><span class="sxs-lookup"><span data-stu-id="3b148-140">Content-Type</span></span> | <span data-ttu-id="3b148-141">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="3b148-141">string</span></span> | <span data-ttu-id="3b148-142">toepassing/json.</span><span class="sxs-lookup"><span data-stu-id="3b148-142">application/json.</span></span> <span data-ttu-id="3b148-143">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="3b148-143">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="3b148-144">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="3b148-144">Request body</span></span>
<span data-ttu-id="3b148-145">In de objectaanvraag moet u een JSON-object de volgende parameters geven:</span><span class="sxs-lookup"><span data-stu-id="3b148-145">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="3b148-146">Parameter</span><span class="sxs-lookup"><span data-stu-id="3b148-146">Parameter</span></span> | <span data-ttu-id="3b148-147">Type</span><span class="sxs-lookup"><span data-stu-id="3b148-147">Type</span></span>    | <span data-ttu-id="3b148-148">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="3b148-148">Description</span></span>
:---|:---|:---
<span data-ttu-id="3b148-149">indicatorValue</span><span class="sxs-lookup"><span data-stu-id="3b148-149">indicatorValue</span></span> | <span data-ttu-id="3b148-150">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="3b148-150">String</span></span> | <span data-ttu-id="3b148-151">Identiteit van de [entiteit Indicator.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="3b148-151">Identity of the [Indicator](ti-indicator.md) entity.</span></span> <span data-ttu-id="3b148-152">**Vereist**</span><span class="sxs-lookup"><span data-stu-id="3b148-152">**Required**</span></span>
<span data-ttu-id="3b148-153">indicatorType</span><span class="sxs-lookup"><span data-stu-id="3b148-153">indicatorType</span></span> | <span data-ttu-id="3b148-154">Enum</span><span class="sxs-lookup"><span data-stu-id="3b148-154">Enum</span></span> | <span data-ttu-id="3b148-155">Type indicator.</span><span class="sxs-lookup"><span data-stu-id="3b148-155">Type of the indicator.</span></span> <span data-ttu-id="3b148-156">Mogelijke waarden zijn: "FileSha1", "FileSha256", "IpAddress", "DomainName" en "Url".</span><span class="sxs-lookup"><span data-stu-id="3b148-156">Possible values are: "FileSha1", "FileSha256", "IpAddress", "DomainName" and "Url".</span></span> <span data-ttu-id="3b148-157">**Vereist**</span><span class="sxs-lookup"><span data-stu-id="3b148-157">**Required**</span></span>
<span data-ttu-id="3b148-158">actie</span><span class="sxs-lookup"><span data-stu-id="3b148-158">action</span></span> | <span data-ttu-id="3b148-159">Enum</span><span class="sxs-lookup"><span data-stu-id="3b148-159">Enum</span></span> | <span data-ttu-id="3b148-160">De actie die wordt ondernomen als de indicator wordt gevonden in de organisatie.</span><span class="sxs-lookup"><span data-stu-id="3b148-160">The action that will be taken if the indicator will be discovered in the organization.</span></span> <span data-ttu-id="3b148-161">Mogelijke waarden zijn: 'Waarschuwing', 'AlertAndBlock' en 'Toegestaan'.</span><span class="sxs-lookup"><span data-stu-id="3b148-161">Possible values are: "Alert", "AlertAndBlock", and "Allowed".</span></span> <span data-ttu-id="3b148-162">**Vereist**</span><span class="sxs-lookup"><span data-stu-id="3b148-162">**Required**</span></span>
<span data-ttu-id="3b148-163">toepassing</span><span class="sxs-lookup"><span data-stu-id="3b148-163">application</span></span> | <span data-ttu-id="3b148-164">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="3b148-164">String</span></span> | <span data-ttu-id="3b148-165">De toepassing die aan de indicator is gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="3b148-165">The application associated with the indicator.</span></span> <span data-ttu-id="3b148-166">**Optioneel**</span><span class="sxs-lookup"><span data-stu-id="3b148-166">**Optional**</span></span>
<span data-ttu-id="3b148-167">titel</span><span class="sxs-lookup"><span data-stu-id="3b148-167">title</span></span> | <span data-ttu-id="3b148-168">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="3b148-168">String</span></span> | <span data-ttu-id="3b148-169">Indicatorwaarschuwingstitel.</span><span class="sxs-lookup"><span data-stu-id="3b148-169">Indicator alert title.</span></span> <span data-ttu-id="3b148-170">**Vereist**</span><span class="sxs-lookup"><span data-stu-id="3b148-170">**Required**</span></span>
<span data-ttu-id="3b148-171">beschrijving</span><span class="sxs-lookup"><span data-stu-id="3b148-171">description</span></span> | <span data-ttu-id="3b148-172">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="3b148-172">String</span></span> | <span data-ttu-id="3b148-173">Beschrijving van de indicator.</span><span class="sxs-lookup"><span data-stu-id="3b148-173">Description of the indicator.</span></span> <span data-ttu-id="3b148-174">**Vereist**</span><span class="sxs-lookup"><span data-stu-id="3b148-174">**Required**</span></span>
<span data-ttu-id="3b148-175">verlooptijd</span><span class="sxs-lookup"><span data-stu-id="3b148-175">expirationTime</span></span> | <span data-ttu-id="3b148-176">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="3b148-176">DateTimeOffset</span></span> | <span data-ttu-id="3b148-177">De verlooptijd van de indicator.</span><span class="sxs-lookup"><span data-stu-id="3b148-177">The expiration time of the indicator.</span></span> <span data-ttu-id="3b148-178">**Optioneel**</span><span class="sxs-lookup"><span data-stu-id="3b148-178">**Optional**</span></span>
<span data-ttu-id="3b148-179">ernst</span><span class="sxs-lookup"><span data-stu-id="3b148-179">severity</span></span> | <span data-ttu-id="3b148-180">Enum</span><span class="sxs-lookup"><span data-stu-id="3b148-180">Enum</span></span> | <span data-ttu-id="3b148-181">De ernst van de indicator.</span><span class="sxs-lookup"><span data-stu-id="3b148-181">The severity of the indicator.</span></span> <span data-ttu-id="3b148-182">mogelijke waarden zijn: 'Informatief', 'Laag', 'Gemiddeld' en 'Hoog'.</span><span class="sxs-lookup"><span data-stu-id="3b148-182">possible values are: "Informational", "Low", "Medium" and "High".</span></span> <span data-ttu-id="3b148-183">**Optioneel**</span><span class="sxs-lookup"><span data-stu-id="3b148-183">**Optional**</span></span>
<span data-ttu-id="3b148-184">aanbevolenActie</span><span class="sxs-lookup"><span data-stu-id="3b148-184">recommendedActions</span></span> | <span data-ttu-id="3b148-185">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="3b148-185">String</span></span> | <span data-ttu-id="3b148-186">Aanbevolen acties voor ti-indicatorwaarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="3b148-186">TI indicator alert recommended actions.</span></span> <span data-ttu-id="3b148-187">**Optioneel**</span><span class="sxs-lookup"><span data-stu-id="3b148-187">**Optional**</span></span>
<span data-ttu-id="3b148-188">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="3b148-188">rbacGroupNames</span></span> | <span data-ttu-id="3b148-189">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="3b148-189">String</span></span> | <span data-ttu-id="3b148-190">Door komma's gescheiden lijst met RBAC-groepsnamen waar de indicator op zou worden toegepast.</span><span class="sxs-lookup"><span data-stu-id="3b148-190">Comma-separated list of RBAC group names the indicator would be applied to.</span></span> <span data-ttu-id="3b148-191">**Optioneel**</span><span class="sxs-lookup"><span data-stu-id="3b148-191">**Optional**</span></span>


## <a name="response"></a><span data-ttu-id="3b148-192">Antwoord</span><span class="sxs-lookup"><span data-stu-id="3b148-192">Response</span></span>
- <span data-ttu-id="3b148-193">Als dit is gelukt, retourneert deze methode 200 - OK-antwoordcode en de aangemaakte / bijgewerkte [indicator-entiteit](ti-indicator.md) in de antwoordinstelling.</span><span class="sxs-lookup"><span data-stu-id="3b148-193">If successful, this method returns 200 - OK response code and the created / updated [Indicator](ti-indicator.md) entity in the response body.</span></span>
- <span data-ttu-id="3b148-194">Als dit niet is gelukt: met deze methode wordt 400 - Slecht verzoek als return gebruikt.</span><span class="sxs-lookup"><span data-stu-id="3b148-194">If not successful: this method return 400 - Bad Request.</span></span> <span data-ttu-id="3b148-195">Een slechte aanvraag geeft meestal een onjuiste body aan.</span><span class="sxs-lookup"><span data-stu-id="3b148-195">Bad request usually indicates incorrect body.</span></span>

## <a name="example"></a><span data-ttu-id="3b148-196">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="3b148-196">Example</span></span>

<span data-ttu-id="3b148-197">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="3b148-197">**Request**</span></span>

<span data-ttu-id="3b148-198">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="3b148-198">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/indicators
```

```json
{
    "indicatorValue": "220e7d15b011d7fac48f2bd61114db1022197f7f",
    "indicatorType": "FileSha1",
    "title": "test",
    "application": "demo-test",
    "expirationTime": "2020-12-12T00:00:00Z",
    "action": "AlertAndBlock",
    "severity": "Informational",
    "description": "test",
    "recommendedActions": "nothing",
    "rbacGroupNames": ["group1", "group2"]
}
```

## <a name="related-topic"></a><span data-ttu-id="3b148-199">Verwant onderwerp</span><span class="sxs-lookup"><span data-stu-id="3b148-199">Related topic</span></span>
- [<span data-ttu-id="3b148-200">Indicatoren beheren</span><span class="sxs-lookup"><span data-stu-id="3b148-200">Manage indicators</span></span>](manage-indicators.md)
