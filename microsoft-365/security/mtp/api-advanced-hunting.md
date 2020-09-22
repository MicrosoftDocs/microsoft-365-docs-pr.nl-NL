---
title: Geavanceerde jacht-Api's
description: Meer informatie over het uitvoeren van geavanceerde query's met een Microsoft Threat Protection-API
keywords: Geavanceerde jacht, Api's, API, MTP
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: dd7b02200e370588bbb9470a3d7e897b30234ead
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197807"
---
# <a name="advanced-hunting-apis"></a><span data-ttu-id="c0beb-104">Geavanceerde jacht-Api's</span><span class="sxs-lookup"><span data-stu-id="c0beb-104">Advanced hunting APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c0beb-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="c0beb-105">**Applies to:**</span></span>
- <span data-ttu-id="c0beb-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c0beb-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="c0beb-107">Sommige informatie verhoudt zich tot een voorvrijgegeven product dat bij de commerciële versie van de commerciële versie mogelijk ingrijpend werd gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="c0beb-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="c0beb-108">Microsoft biedt geen garanties, expliciete of impliciete informatie met betrekking tot de informatie die u hier opgeeft.</span><span class="sxs-lookup"><span data-stu-id="c0beb-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="limitations"></a><span data-ttu-id="c0beb-109">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="c0beb-109">Limitations</span></span>
1. <span data-ttu-id="c0beb-110">U kunt alleen een query uitvoeren op gegevens van de afgelopen 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="c0beb-110">You can only run a query on data from the last 30 days.</span></span>
2. <span data-ttu-id="c0beb-111">De resultaten hebben een maximum van 100.000 rijen.</span><span class="sxs-lookup"><span data-stu-id="c0beb-111">The results will include a maximum of 100,000 rows.</span></span>
3. <span data-ttu-id="c0beb-112">Het aantal uitvoeringen is beperkt per Tenant: tot 10 oproepen per minuut, 10 minuten per uur, met een tijdsduur van telkens een dag en 4 uur.</span><span class="sxs-lookup"><span data-stu-id="c0beb-112">The number of executions is limited per tenant: up to 10 calls per minute, 10 minutes of running time every hour and 4 hours of running time a day.</span></span>
4. <span data-ttu-id="c0beb-113">De maximale uitvoeringstijd van één aanvraag duurt 10 minuten.</span><span class="sxs-lookup"><span data-stu-id="c0beb-113">The maximal execution time of a single request is 10 minutes.</span></span>
5. <span data-ttu-id="c0beb-114">429-antwoord geeft een limiet aan voor het bereiken van de quotumlimiet per aantal aanvragen of door processor.</span><span class="sxs-lookup"><span data-stu-id="c0beb-114">429 response will represent reaching quota limit either by number of requests or by CPU.</span></span> <span data-ttu-id="c0beb-115">De antwoordtekst van 429 geeft ook de tijd aan waarop de quota worden verlengd.</span><span class="sxs-lookup"><span data-stu-id="c0beb-115">The 429 response body will also indicate the time until the quota is renewed.</span></span> 


## <a name="permissions"></a><span data-ttu-id="c0beb-116">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="c0beb-116">Permissions</span></span>
<span data-ttu-id="c0beb-117">U moet een van de volgende machtigingen hebben om deze API te kunnen bellen.</span><span class="sxs-lookup"><span data-stu-id="c0beb-117">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="c0beb-118">Zie [de Api's Microsoft Threat Protection openen](api-access.md) voor meer informatie, waaronder de manier waarop u machtigingen kiest.</span><span class="sxs-lookup"><span data-stu-id="c0beb-118">To learn more, including how to choose permissions, see [Access the Microsoft Threat Protection APIs](api-access.md)</span></span>

<span data-ttu-id="c0beb-119">Type machtiging</span><span class="sxs-lookup"><span data-stu-id="c0beb-119">Permission type</span></span> |   <span data-ttu-id="c0beb-120">Machtigingsset</span><span class="sxs-lookup"><span data-stu-id="c0beb-120">Permission</span></span>  |   <span data-ttu-id="c0beb-121">Weergavenaam van de machtiging</span><span class="sxs-lookup"><span data-stu-id="c0beb-121">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="c0beb-122">Toepassing</span><span class="sxs-lookup"><span data-stu-id="c0beb-122">Application</span></span> |   <span data-ttu-id="c0beb-123">AdvancedHunting. Read. all</span><span class="sxs-lookup"><span data-stu-id="c0beb-123">AdvancedHunting.Read.All</span></span> |  <span data-ttu-id="c0beb-124">' Geavanceerde query's uitvoeren '</span><span class="sxs-lookup"><span data-stu-id="c0beb-124">'Run advanced queries'</span></span>
<span data-ttu-id="c0beb-125">Gedelegeerd (werk-of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="c0beb-125">Delegated (work or school account)</span></span> | <span data-ttu-id="c0beb-126">AdvancedHunting. Read</span><span class="sxs-lookup"><span data-stu-id="c0beb-126">AdvancedHunting.Read</span></span> | <span data-ttu-id="c0beb-127">' Geavanceerde query's uitvoeren '</span><span class="sxs-lookup"><span data-stu-id="c0beb-127">'Run advanced queries'</span></span>

>[!Note]
> <span data-ttu-id="c0beb-128">Bij het verkrijgen van een token met behulp van gebruikersreferenties:</span><span class="sxs-lookup"><span data-stu-id="c0beb-128">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="c0beb-129">De gebruiker moet de rol gegevens weergeven hebben</span><span class="sxs-lookup"><span data-stu-id="c0beb-129">The user needs to have 'View Data' AD role</span></span>
>- <span data-ttu-id="c0beb-130">De gebruiker moet toegang hebben tot het apparaat, op basis van de instellingen van de apparaatgroepen.</span><span class="sxs-lookup"><span data-stu-id="c0beb-130">The user needs to have access to the device, based on device group settings.</span></span>

## <a name="http-request"></a><span data-ttu-id="c0beb-131">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="c0beb-131">HTTP request</span></span>
```
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a><span data-ttu-id="c0beb-132">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="c0beb-132">Request headers</span></span>

<span data-ttu-id="c0beb-133">Factuurkop</span><span class="sxs-lookup"><span data-stu-id="c0beb-133">Header</span></span> | <span data-ttu-id="c0beb-134">Value</span><span class="sxs-lookup"><span data-stu-id="c0beb-134">Value</span></span> 
:---|:---
<span data-ttu-id="c0beb-135">Bevoegdheid</span><span class="sxs-lookup"><span data-stu-id="c0beb-135">Authorization</span></span> | <span data-ttu-id="c0beb-136">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="c0beb-136">Bearer {token}.</span></span> <span data-ttu-id="c0beb-137">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="c0beb-137">**Required**.</span></span>
<span data-ttu-id="c0beb-138">Inhouds type</span><span class="sxs-lookup"><span data-stu-id="c0beb-138">Content-Type</span></span>    | <span data-ttu-id="c0beb-139">toepassing/JSON</span><span class="sxs-lookup"><span data-stu-id="c0beb-139">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="c0beb-140">Aanvraagtekst</span><span class="sxs-lookup"><span data-stu-id="c0beb-140">Request body</span></span>
<span data-ttu-id="c0beb-141">Geef in de hoofdtekst van de aanvraag een JSON-object op met de volgende parameters:</span><span class="sxs-lookup"><span data-stu-id="c0beb-141">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="c0beb-142">Tabelwaardeparameter</span><span class="sxs-lookup"><span data-stu-id="c0beb-142">Parameter</span></span> | <span data-ttu-id="c0beb-143">Type</span><span class="sxs-lookup"><span data-stu-id="c0beb-143">Type</span></span>    | <span data-ttu-id="c0beb-144">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="c0beb-144">Description</span></span>
:---|:---|:---
<span data-ttu-id="c0beb-145">Query</span><span class="sxs-lookup"><span data-stu-id="c0beb-145">Query</span></span> | <span data-ttu-id="c0beb-146">Tekst</span><span class="sxs-lookup"><span data-stu-id="c0beb-146">Text</span></span> |  <span data-ttu-id="c0beb-147">De query wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="c0beb-147">The query to run.</span></span> <span data-ttu-id="c0beb-148">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="c0beb-148">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="c0beb-149">Na</span><span class="sxs-lookup"><span data-stu-id="c0beb-149">Response</span></span>
<span data-ttu-id="c0beb-150">Als dit is gelukt, retourneert deze methode 200 OK en _QueryResponse_ object in de tekst van het antwoord.</span><span class="sxs-lookup"><span data-stu-id="c0beb-150">If successful, this method returns 200 OK, and _QueryResponse_ object in the response body.</span></span> <br><br>

<span data-ttu-id="c0beb-151">Het antwoordobject is onderverdeeld in drie delen (eigenschappen):</span><span class="sxs-lookup"><span data-stu-id="c0beb-151">The response object is divided to 3 parts (properties):</span></span><br>
1) <span data-ttu-id="c0beb-152">```Stats``` -Prestatiestatistieken voor query's.</span><span class="sxs-lookup"><span data-stu-id="c0beb-152">```Stats``` - Query performance statistics.</span></span><br>
2) <span data-ttu-id="c0beb-153">```Schema``` -Het schema van het antwoord, een lijst met namen van de typen paren voor elke kolom.</span><span class="sxs-lookup"><span data-stu-id="c0beb-153">```Schema``` - The schema of the response, a list of Name-Type pairs for each column.</span></span> <br>
3) <span data-ttu-id="c0beb-154">```Results``` -Een lijst met geavanceerde bejacht gebeurtenissen.</span><span class="sxs-lookup"><span data-stu-id="c0beb-154">```Results``` - A list of Advanced Hunting events.</span></span>

## <a name="example"></a><span data-ttu-id="c0beb-155">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="c0beb-155">Example</span></span>

<span data-ttu-id="c0beb-156">Webonderdeelverzoek</span><span class="sxs-lookup"><span data-stu-id="c0beb-156">Request</span></span>

<span data-ttu-id="c0beb-157">Hier ziet u een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="c0beb-157">Here is an example of the request.</span></span>


```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

<span data-ttu-id="c0beb-158">Na</span><span class="sxs-lookup"><span data-stu-id="c0beb-158">Response</span></span>

<span data-ttu-id="c0beb-159">Hier ziet u een voorbeeld van het antwoord.</span><span class="sxs-lookup"><span data-stu-id="c0beb-159">Here is an example of the response.</span></span>


```json
{
    "Stats": {
        "ExecutionTime": 4.621215,
        "resource_usage": {
            "cache": {
                "memory": {
                    "hits": 773461,
                    "misses": 4481,
                    "total": 777942
                },
                "disk": {
                    "hits": 994,
                    "misses": 197,
                    "total": 1191
                }
            },
            "cpu": {
                "user": "00:00:19.0468750",
                "kernel": "00:00:00.0156250",
                "total cpu": "00:00:19.0625000"
            },
            "memory": {
                "peak_per_node": 236822432
            }
        },
        "dataset_statistics": [
            {
                "table_row_count": 2,
                "table_size": 102
            }
        ]
    },
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
        }
    ],
    "Results": [
        {
            "Timestamp": "2020-08-30T06:38:35.7664356Z",
            "FileName": "conhost.exe",
            "InitiatingProcessFileName": "powershell.exe"
        },
        {
            "Timestamp": "2020-08-30T06:38:30.5163363Z",
            "FileName": "conhost.exe",
            "InitiatingProcessFileName": "powershell.exe"
        }
    ]
}

```

## <a name="related-topic"></a><span data-ttu-id="c0beb-160">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="c0beb-160">Related topic</span></span>
- [<span data-ttu-id="c0beb-161">Toegang tot de Microsoft Threat Protection-Api's</span><span class="sxs-lookup"><span data-stu-id="c0beb-161">Access the Microsoft Threat Protection APIs</span></span>](api-access.md)
