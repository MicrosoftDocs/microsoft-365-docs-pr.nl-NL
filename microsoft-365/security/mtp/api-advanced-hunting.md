---
title: Microsoft 365 Defender advanced hunting API
description: Meer informatie over het uitvoeren van geavanceerde zoekquery's met de geavanceerde api van Microsoft 365 Defender voor zoeken
keywords: Advanced Hunting, API's, api, MTP, M365 Defender, Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 4213773c3305c28f0913013d8f7634c083811f52
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932080"
---
# <a name="microsoft-365-defender-advanced-hunting-api"></a><span data-ttu-id="313ad-104">Microsoft 365 Defender Advanced hunting API</span><span class="sxs-lookup"><span data-stu-id="313ad-104">Microsoft 365 Defender Advanced hunting API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="313ad-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="313ad-105">**Applies to:**</span></span>

- <span data-ttu-id="313ad-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="313ad-106">Microsoft Threat Protection</span></span>

> [!IMPORTANT]
> <span data-ttu-id="313ad-107">Sommige informatie heeft betrekking op vooraf uitgebracht product dat aanzienlijk kan worden gewijzigd voordat het in de handel wordt gebracht.</span><span class="sxs-lookup"><span data-stu-id="313ad-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="313ad-108">Microsoft biedt geen garanties, uitdrukkelijk of impliciet, met betrekking tot de informatie die hier wordt be gegeven.</span><span class="sxs-lookup"><span data-stu-id="313ad-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="313ad-109">[Geavanceerd zoeken](advanced-hunting-overview.md) is een hulpprogramma [](advanced-hunting-query-language.md) voor het op zoek naar risico' en maakt gebruik van speciaal gebouwde query's om de gebeurtenisgegevens van de afgelopen 30 dagen in Microsoft 365 Defender te analyseren.</span><span class="sxs-lookup"><span data-stu-id="313ad-109">[Advanced hunting](advanced-hunting-overview.md) is a threat-hunting tool that uses [specially constructed queries](advanced-hunting-query-language.md) to examine the past 30 days of event data in Microsoft 365 Defender.</span></span> <span data-ttu-id="313ad-110">U kunt geavanceerde zoekquery's gebruiken om ongebruikelijke activiteiten te controleren, mogelijke bedreigingen te detecteren en zelfs om te reageren op aanvallen.</span><span class="sxs-lookup"><span data-stu-id="313ad-110">You can use advanced hunting queries to inspect unusual activity, detect possible threats, and even respond to attacks.</span></span> <span data-ttu-id="313ad-111">Met de geavanceerde api voor zoeken kunt u gebeurtenisgegevens programmatisch opvragen.</span><span class="sxs-lookup"><span data-stu-id="313ad-111">The advanced hunting API allows you to programatically query event data.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="313ad-112">Quota en resourcetoewijzing</span><span class="sxs-lookup"><span data-stu-id="313ad-112">Quotas and resource allocation</span></span>

<span data-ttu-id="313ad-113">De volgende voorwaarden hebben betrekking op alle query's.</span><span class="sxs-lookup"><span data-stu-id="313ad-113">The following conditions relate to all queries.</span></span>

1. <span data-ttu-id="313ad-114">Query's verkennen en retourneren gegevens van de afgelopen 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="313ad-114">Queries explore and return data from the past 30 days.</span></span>
2. <span data-ttu-id="313ad-115">Resultaten kunnen maximaal 100.000 rijen retourneren.</span><span class="sxs-lookup"><span data-stu-id="313ad-115">Results can return up to 100,000 rows.</span></span>
3. <span data-ttu-id="313ad-116">U kunt maximaal 10 oproepen per minuut per tenant voeren.</span><span class="sxs-lookup"><span data-stu-id="313ad-116">You can make up to 10 calls per minute per tenant.</span></span>
4. <span data-ttu-id="313ad-117">U hebt 10 minuten aan gebruikstijd per uur per tenant.</span><span class="sxs-lookup"><span data-stu-id="313ad-117">You have 10 minutes of running time per hour per tenant.</span></span>
5. <span data-ttu-id="313ad-118">U hebt in totaal vier werkdagen per tenant.</span><span class="sxs-lookup"><span data-stu-id="313ad-118">You have four total hours of running time day per tenant.</span></span>
6. <span data-ttu-id="313ad-119">Als één aanvraag langer dan tien minuten wordt uitgevoerd, wordt er een time-out gemaakt en wordt een foutmelding weergegeven.</span><span class="sxs-lookup"><span data-stu-id="313ad-119">If a single request runs for more than 10 minutes, it will time out and return an error.</span></span>
7. <span data-ttu-id="313ad-120">Een HTTP-antwoordcode geeft aan dat u een quotum hebt bereikt, hetzij door het aantal verzonden aanvragen of door de toegewezen `429` lopende tijd.</span><span class="sxs-lookup"><span data-stu-id="313ad-120">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="313ad-121">De reactie zelf bevat de tijd tot het quotum dat u hebt bereikt, wordt opnieuw ingesteld.</span><span class="sxs-lookup"><span data-stu-id="313ad-121">The response body will include the time until the quota you reached will be reset.</span></span>

## <a name="permissions"></a><span data-ttu-id="313ad-122">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="313ad-122">Permissions</span></span>

<span data-ttu-id="313ad-123">Een van de volgende machtigingen is vereist om de geavanceerde api voor zoeken aan te roepen.</span><span class="sxs-lookup"><span data-stu-id="313ad-123">One of the following permissions is required to call the advanced hunting API.</span></span> <span data-ttu-id="313ad-124">Zie Access voor meer informatie, waaronder het kiezen van machtigingen, [de Microsoft 365 Defender Protection-API's](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="313ad-124">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender Protection APIs](api-access.md)</span></span>

<span data-ttu-id="313ad-125">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="313ad-125">Permission type</span></span> | <span data-ttu-id="313ad-126">Machtiging</span><span class="sxs-lookup"><span data-stu-id="313ad-126">Permission</span></span> | <span data-ttu-id="313ad-127">Weergavenaam van machtiging</span><span class="sxs-lookup"><span data-stu-id="313ad-127">Permission display name</span></span>
-|-|-
<span data-ttu-id="313ad-128">Toepassing</span><span class="sxs-lookup"><span data-stu-id="313ad-128">Application</span></span> | <span data-ttu-id="313ad-129">AdvancedHunting.Read.All</span><span class="sxs-lookup"><span data-stu-id="313ad-129">AdvancedHunting.Read.All</span></span> | <span data-ttu-id="313ad-130">Geavanceerde query's uitvoeren</span><span class="sxs-lookup"><span data-stu-id="313ad-130">Run advanced queries</span></span>
<span data-ttu-id="313ad-131">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="313ad-131">Delegated (work or school account)</span></span> | <span data-ttu-id="313ad-132">AdvancedHunting.Read</span><span class="sxs-lookup"><span data-stu-id="313ad-132">AdvancedHunting.Read</span></span> | <span data-ttu-id="313ad-133">Geavanceerde query's uitvoeren</span><span class="sxs-lookup"><span data-stu-id="313ad-133">Run advanced queries</span></span>

>[!Note]
> <span data-ttu-id="313ad-134">Wanneer u een token verkrijgt met behulp van gebruikersreferenties:</span><span class="sxs-lookup"><span data-stu-id="313ad-134">When obtaining a token using user credentials:</span></span>
>
>- <span data-ttu-id="313ad-135">De gebruiker moet de AD-rol Gegevens weergeven hebben</span><span class="sxs-lookup"><span data-stu-id="313ad-135">The user needs to have the 'View Data' AD role</span></span>
>- <span data-ttu-id="313ad-136">De gebruiker moet toegang hebben tot het apparaat op basis van de instellingen van de apparaatgroep.</span><span class="sxs-lookup"><span data-stu-id="313ad-136">The user needs to have access to the device, based on device group settings.</span></span>

## <a name="http-request"></a><span data-ttu-id="313ad-137">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="313ad-137">HTTP request</span></span>

```HTTP
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a><span data-ttu-id="313ad-138">Berichtkoppen aanvragen</span><span class="sxs-lookup"><span data-stu-id="313ad-138">Request headers</span></span>

<span data-ttu-id="313ad-139">Koptekst</span><span class="sxs-lookup"><span data-stu-id="313ad-139">Header</span></span> | <span data-ttu-id="313ad-140">Value</span><span class="sxs-lookup"><span data-stu-id="313ad-140">Value</span></span>
-|-
<span data-ttu-id="313ad-141">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="313ad-141">Authorization</span></span> | <span data-ttu-id="313ad-142">Opmerking voor gewenste {token}: **vereist**</span><span class="sxs-lookup"><span data-stu-id="313ad-142">Bearer {token} **Note: required**</span></span>
<span data-ttu-id="313ad-143">Inhoudstype</span><span class="sxs-lookup"><span data-stu-id="313ad-143">Content-Type</span></span> | <span data-ttu-id="313ad-144">toepassing/json</span><span class="sxs-lookup"><span data-stu-id="313ad-144">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="313ad-145">Aanvraag in de eerste instantie</span><span class="sxs-lookup"><span data-stu-id="313ad-145">Request body</span></span>

<span data-ttu-id="313ad-146">In de aanvraag zelf een JSON-object opgeven met de volgende parameters:</span><span class="sxs-lookup"><span data-stu-id="313ad-146">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="313ad-147">Parameter</span><span class="sxs-lookup"><span data-stu-id="313ad-147">Parameter</span></span> | <span data-ttu-id="313ad-148">Type</span><span class="sxs-lookup"><span data-stu-id="313ad-148">Type</span></span> | <span data-ttu-id="313ad-149">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="313ad-149">Description</span></span>
-|-|-
<span data-ttu-id="313ad-150">Query</span><span class="sxs-lookup"><span data-stu-id="313ad-150">Query</span></span> | <span data-ttu-id="313ad-151">Tekst</span><span class="sxs-lookup"><span data-stu-id="313ad-151">Text</span></span> | <span data-ttu-id="313ad-152">De query die moet worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="313ad-152">The query to run.</span></span> <span data-ttu-id="313ad-153">**Opmerking: vereist**</span><span class="sxs-lookup"><span data-stu-id="313ad-153">**Note: required**</span></span>

## <a name="response"></a><span data-ttu-id="313ad-154">Antwoord</span><span class="sxs-lookup"><span data-stu-id="313ad-154">Response</span></span>

<span data-ttu-id="313ad-155">Als dit lukt, wordt met deze methode `200 OK` een _object QueryResponse_ in de antwoord zelf gegeven.</span><span class="sxs-lookup"><span data-stu-id="313ad-155">If successful, this method will return `200 OK`, and a _QueryResponse_ object in the response body.</span></span>

<span data-ttu-id="313ad-156">Het antwoordobject bevat drie eigenschappen op het hoogste niveau:</span><span class="sxs-lookup"><span data-stu-id="313ad-156">The response object contains three top-level properties:</span></span>

1. <span data-ttu-id="313ad-157">Stats: een woordenlijst met prestatiestatistieken voor query's.</span><span class="sxs-lookup"><span data-stu-id="313ad-157">Stats - A dictionary of query performance statistics.</span></span>
2. <span data-ttu-id="313ad-158">Schema: het schema van het antwoord, een lijst Name-Type paren voor elke kolom.</span><span class="sxs-lookup"><span data-stu-id="313ad-158">Schema - The schema of the response, a list of Name-Type pairs for each column.</span></span>
3. <span data-ttu-id="313ad-159">Results: een lijst met geavanceerde zoekgebeurtenissen.</span><span class="sxs-lookup"><span data-stu-id="313ad-159">Results - A list of advanced hunting events.</span></span>

## <a name="example"></a><span data-ttu-id="313ad-160">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="313ad-160">Example</span></span>

<span data-ttu-id="313ad-161">In het volgende voorbeeld verzendt een gebruiker de onderstaande query en ontvangt deze een API-antwoordobject met `Stats` `Schema` de volgende . `Results`</span><span class="sxs-lookup"><span data-stu-id="313ad-161">In the following example, a user sends the query below and receives an API response object containing `Stats`, `Schema`, and `Results`.</span></span>

### <a name="query"></a><span data-ttu-id="313ad-162">Query</span><span class="sxs-lookup"><span data-stu-id="313ad-162">Query</span></span>

```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

### <a name="response-object"></a><span data-ttu-id="313ad-163">Antwoordobject</span><span class="sxs-lookup"><span data-stu-id="313ad-163">Response object</span></span>

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

## <a name="related-articles"></a><span data-ttu-id="313ad-164">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="313ad-164">Related articles</span></span>

- [<span data-ttu-id="313ad-165">Toegang tot de Microsoft 365 Defender-API's</span><span class="sxs-lookup"><span data-stu-id="313ad-165">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="313ad-166">Meer informatie over API-limieten en licenties</span><span class="sxs-lookup"><span data-stu-id="313ad-166">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="313ad-167">Meer te weten komen over foutcodes</span><span class="sxs-lookup"><span data-stu-id="313ad-167">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="313ad-168">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="313ad-168">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
