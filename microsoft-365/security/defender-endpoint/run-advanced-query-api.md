---
title: Geavanceerde API voor opsporing
ms.reviewer: ''
description: Meer informatie over het gebruik van de geavanceerde api voor jagen om geavanceerde query's uit te voeren op Microsoft Defender voor Eindpunt. Lees meer over beperkingen en zie een voorbeeld.
keywords: api's, ondersteunde api's, geavanceerd zoeken, query
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
ms.openlocfilehash: 40487143ff18cedb76c9f3f33c52cab24687c282
ms.sourcegitcommit: dc1ac43a57fac6f57438859dd668f927d94fdf34
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/07/2021
ms.locfileid: "51604367"
---
# <a name="advanced-hunting-api"></a><span data-ttu-id="d79e4-105">Geavanceerde api voor jagen</span><span class="sxs-lookup"><span data-stu-id="d79e4-105">Advanced hunting API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d79e4-106">**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="d79e4-106">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="d79e4-107">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="d79e4-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d79e4-108">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="d79e4-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="limitations"></a><span data-ttu-id="d79e4-109">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="d79e4-109">Limitations</span></span>

1. <span data-ttu-id="d79e4-110">U kunt alleen een query uitvoeren op gegevens van de afgelopen 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="d79e4-110">You can only run a query on data from the last 30 days.</span></span>

2. <span data-ttu-id="d79e4-111">De resultaten bevatten maximaal 100.000 rijen.</span><span class="sxs-lookup"><span data-stu-id="d79e4-111">The results will include a maximum of 100,000 rows.</span></span>

3. <span data-ttu-id="d79e4-112">Het aantal uitvoeringen is beperkt per tenant:</span><span class="sxs-lookup"><span data-stu-id="d79e4-112">The number of executions is limited per tenant:</span></span>
   - <span data-ttu-id="d79e4-113">API-oproepen: maximaal 45 oproepen per minuut, maximaal 1500 oproepen per uur.</span><span class="sxs-lookup"><span data-stu-id="d79e4-113">API calls: Up to 45 calls per minute, up to 1500 calls per hour.</span></span>
   - <span data-ttu-id="d79e4-114">Uitvoeringstijd: 10 minuten speeltijd per uur en 3 uur werktijd per dag.</span><span class="sxs-lookup"><span data-stu-id="d79e4-114">Execution time: 10 minutes of running time every hour and 3 hours of running time a day.</span></span>

4. <span data-ttu-id="d79e4-115">De maximale uitvoeringstijd van één aanvraag is 10 minuten.</span><span class="sxs-lookup"><span data-stu-id="d79e4-115">The maximal execution time of a single request is 10 minutes.</span></span>

5. <span data-ttu-id="d79e4-116">429-antwoord vertegenwoordigt het bereiken van de quotumlimiet, hetzij per aantal aanvragen of per CPU.</span><span class="sxs-lookup"><span data-stu-id="d79e4-116">429 response will represent reaching quota limit either by number of requests or by CPU.</span></span> <span data-ttu-id="d79e4-117">Lees de antwoord body om te begrijpen welke limiet is bereikt.</span><span class="sxs-lookup"><span data-stu-id="d79e4-117">Read response body to understand what limit has been reached.</span></span> 

## <a name="permissions"></a><span data-ttu-id="d79e4-118">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="d79e4-118">Permissions</span></span>

<span data-ttu-id="d79e4-119">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="d79e4-119">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="d79e4-120">Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="d79e4-120">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="d79e4-121">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="d79e4-121">Permission type</span></span> |   <span data-ttu-id="d79e4-122">Machtiging</span><span class="sxs-lookup"><span data-stu-id="d79e4-122">Permission</span></span>  |   <span data-ttu-id="d79e4-123">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="d79e4-123">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="d79e4-124">Toepassing</span><span class="sxs-lookup"><span data-stu-id="d79e4-124">Application</span></span> |   <span data-ttu-id="d79e4-125">AdvancedQuery.Read.All</span><span class="sxs-lookup"><span data-stu-id="d79e4-125">AdvancedQuery.Read.All</span></span> |    <span data-ttu-id="d79e4-126">'Geavanceerde query's uitvoeren'</span><span class="sxs-lookup"><span data-stu-id="d79e4-126">'Run advanced queries'</span></span>
<span data-ttu-id="d79e4-127">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="d79e4-127">Delegated (work or school account)</span></span> | <span data-ttu-id="d79e4-128">AdvancedQuery.Read</span><span class="sxs-lookup"><span data-stu-id="d79e4-128">AdvancedQuery.Read</span></span> | <span data-ttu-id="d79e4-129">'Geavanceerde query's uitvoeren'</span><span class="sxs-lookup"><span data-stu-id="d79e4-129">'Run advanced queries'</span></span>

>[!Note]
> <span data-ttu-id="d79e4-130">Bij het verkrijgen van een token met gebruikersreferenties:</span><span class="sxs-lookup"><span data-stu-id="d79e4-130">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="d79e4-131">De gebruiker moet ad-rol 'Gegevens weergeven' hebben</span><span class="sxs-lookup"><span data-stu-id="d79e4-131">The user needs to have 'View Data' AD role</span></span>
>- <span data-ttu-id="d79e4-132">De gebruiker moet toegang hebben tot het apparaat op basis van apparaatgroepinstellingen (Zie [Apparaatgroepen](machine-groups.md) maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="d79e4-132">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="d79e4-133">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="d79e4-133">HTTP request</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/advancedqueries/run
```

## <a name="request-headers"></a><span data-ttu-id="d79e4-134">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="d79e4-134">Request headers</span></span>

<span data-ttu-id="d79e4-135">Koptekst</span><span class="sxs-lookup"><span data-stu-id="d79e4-135">Header</span></span> | <span data-ttu-id="d79e4-136">Waarde</span><span class="sxs-lookup"><span data-stu-id="d79e4-136">Value</span></span> 
:---|:---
<span data-ttu-id="d79e4-137">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="d79e4-137">Authorization</span></span> | <span data-ttu-id="d79e4-138">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="d79e4-138">Bearer {token}.</span></span> <span data-ttu-id="d79e4-139">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="d79e4-139">**Required**.</span></span>
<span data-ttu-id="d79e4-140">Inhoudstype</span><span class="sxs-lookup"><span data-stu-id="d79e4-140">Content-Type</span></span>    | <span data-ttu-id="d79e4-141">toepassing/json</span><span class="sxs-lookup"><span data-stu-id="d79e4-141">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="d79e4-142">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="d79e4-142">Request body</span></span>

<span data-ttu-id="d79e4-143">In de objectaanvraag moet u een JSON-object de volgende parameters geven:</span><span class="sxs-lookup"><span data-stu-id="d79e4-143">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="d79e4-144">Parameter</span><span class="sxs-lookup"><span data-stu-id="d79e4-144">Parameter</span></span> | <span data-ttu-id="d79e4-145">Type</span><span class="sxs-lookup"><span data-stu-id="d79e4-145">Type</span></span>    | <span data-ttu-id="d79e4-146">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="d79e4-146">Description</span></span>
:---|:---|:---
<span data-ttu-id="d79e4-147">Query</span><span class="sxs-lookup"><span data-stu-id="d79e4-147">Query</span></span> | <span data-ttu-id="d79e4-148">Tekst</span><span class="sxs-lookup"><span data-stu-id="d79e4-148">Text</span></span> |  <span data-ttu-id="d79e4-149">De query die u wilt uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="d79e4-149">The query to run.</span></span> <span data-ttu-id="d79e4-150">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="d79e4-150">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="d79e4-151">Antwoord</span><span class="sxs-lookup"><span data-stu-id="d79e4-151">Response</span></span>

<span data-ttu-id="d79e4-152">Als dit is gelukt, retourneert deze methode 200 OK en _QueryResponse-object_ in de antwoord body.</span><span class="sxs-lookup"><span data-stu-id="d79e4-152">If successful, this method returns 200 OK, and _QueryResponse_ object in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="d79e4-153">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="d79e4-153">Example</span></span>

##### <a name="request"></a><span data-ttu-id="d79e4-154">Aanvraag</span><span class="sxs-lookup"><span data-stu-id="d79e4-154">Request</span></span>

<span data-ttu-id="d79e4-155">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="d79e4-155">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/advancedqueries/run
```

```json
{
    "Query":"DeviceProcessEvents  
    | where InitiatingProcessFileName =~ 'powershell.exe'
    | where ProcessCommandLine contains 'appdata'
    | project Timestamp, FileName, InitiatingProcessFileName, DeviceId
    | limit 2"
}
```

##### <a name="response"></a><span data-ttu-id="d79e4-156">Antwoord</span><span class="sxs-lookup"><span data-stu-id="d79e4-156">Response</span></span>

<span data-ttu-id="d79e4-157">Hier is een voorbeeld van het antwoord.</span><span class="sxs-lookup"><span data-stu-id="d79e4-157">Here is an example of the response.</span></span>

>[!NOTE]
><span data-ttu-id="d79e4-158">Het antwoordobject dat hier wordt weergegeven, kan worden afgekapt voor beknoptheid.</span><span class="sxs-lookup"><span data-stu-id="d79e4-158">The response object shown here may be truncated for brevity.</span></span> <span data-ttu-id="d79e4-159">Alle eigenschappen worden geretourneerd uit een echt gesprek.</span><span class="sxs-lookup"><span data-stu-id="d79e4-159">All of the properties will be returned from an actual call.</span></span>

```json
{
    "Schema": [
        {
            "Name": "Timestamp",
            "Type": "DateTime"
        },
        {
            "Name": "FileName",
            "Type": "String"
        },
        {
            "Name": "InitiatingProcessFileName",
            "Type": "String"
        },
        {
            "Name": "DeviceId",
            "Type": "String"
        }
    ],
    "Results": [
        {
            "Timestamp": "2020-02-05T01:10:26.2648757Z",
            "FileName": "csc.exe",
            "InitiatingProcessFileName": "powershell.exe",
            "DeviceId": "10cbf9182d4e95660362f65cfa67c7731f62fdb3"
        },
        {
            "Timestamp": "2020-02-05T01:10:26.5614772Z",
            "FileName": "csc.exe",
            "InitiatingProcessFileName": "powershell.exe",
            "DeviceId": "10cbf9182d4e95660362f65cfa67c7731f62fdb3"
        }
    ]
}
```

## <a name="related-topics"></a><span data-ttu-id="d79e4-160">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="d79e4-160">Related topics</span></span>

- [<span data-ttu-id="d79e4-161">Microsoft Defender for Endpoint API's introduction</span><span class="sxs-lookup"><span data-stu-id="d79e4-161">Microsoft Defender for Endpoint APIs introduction</span></span>](apis-intro.md)
- [<span data-ttu-id="d79e4-162">Advanced Hunting from Portal</span><span class="sxs-lookup"><span data-stu-id="d79e4-162">Advanced Hunting from Portal</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="d79e4-163">Geavanceerde opsporing met behulp van PowerShell</span><span class="sxs-lookup"><span data-stu-id="d79e4-163">Advanced Hunting using PowerShell</span></span>](run-advanced-query-sample-powershell.md)
