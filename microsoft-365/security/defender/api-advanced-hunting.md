---
title: Microsoft 365 Defender advanced hunting API
description: Meer informatie over het uitvoeren van geavanceerde zoekquery's met behulp van de geavanceerde api van Microsoft 365 Defender
keywords: Advanced Hunting, API's, api, M365 Defender, Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: c988a609a329c8f7f8988314e56aae942beebac5
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932891"
---
# <a name="microsoft-365-defender-advanced-hunting-api"></a><span data-ttu-id="bbcef-104">Microsoft 365 Defender Advanced hunting API</span><span class="sxs-lookup"><span data-stu-id="bbcef-104">Microsoft 365 Defender Advanced hunting API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="bbcef-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="bbcef-105">**Applies to:**</span></span>

- <span data-ttu-id="bbcef-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bbcef-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bbcef-107">Sommige informatie is gerelateerd aan voorlopige productversies die mogelijk aanzienlijk gewijzigd worden voordat ze commercieel gepubliceerd worden.</span><span class="sxs-lookup"><span data-stu-id="bbcef-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="bbcef-108">Microsoft geeft geen garantie, uitdrukkelijk of impliciet, met betrekking tot de informatie die hier wordt beschreven.</span><span class="sxs-lookup"><span data-stu-id="bbcef-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="bbcef-109">[Geavanceerd zoeken](advanced-hunting-overview.md) is een hulpprogramma [](advanced-hunting-query-language.md) voor het zoeken naar bedreigingen dat speciaal samengestelde query's gebruikt om de afgelopen 30 dagen met gebeurtenisgegevens in Microsoft 365 Defender te bekijken.</span><span class="sxs-lookup"><span data-stu-id="bbcef-109">[Advanced hunting](advanced-hunting-overview.md) is a threat-hunting tool that uses [specially constructed queries](advanced-hunting-query-language.md) to examine the past 30 days of event data in Microsoft 365 Defender.</span></span> <span data-ttu-id="bbcef-110">U kunt geavanceerde zoekquery's gebruiken om ongebruikelijke activiteiten te controleren, mogelijke bedreigingen te detecteren en zelfs te reageren op aanvallen.</span><span class="sxs-lookup"><span data-stu-id="bbcef-110">You can use advanced hunting queries to inspect unusual activity, detect possible threats, and even respond to attacks.</span></span> <span data-ttu-id="bbcef-111">Met de geavanceerde api voor jagen kunt u gebeurtenisgegevens programmeren.</span><span class="sxs-lookup"><span data-stu-id="bbcef-111">The advanced hunting API allows you to programatically query event data.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="bbcef-112">Quota en resourcetoewijzing</span><span class="sxs-lookup"><span data-stu-id="bbcef-112">Quotas and resource allocation</span></span>

<span data-ttu-id="bbcef-113">De volgende voorwaarden hebben betrekking op alle query's.</span><span class="sxs-lookup"><span data-stu-id="bbcef-113">The following conditions relate to all queries.</span></span>

1. <span data-ttu-id="bbcef-114">Query's verkennen en retourneren gegevens uit de afgelopen 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="bbcef-114">Queries explore and return data from the past 30 days.</span></span>
2. <span data-ttu-id="bbcef-115">Resultaten kunnen maximaal 100.000 rijen opleveren.</span><span class="sxs-lookup"><span data-stu-id="bbcef-115">Results can return up to 100,000 rows.</span></span>
3. <span data-ttu-id="bbcef-116">U kunt maximaal 15 oproepen per minuut per tenant voeren.</span><span class="sxs-lookup"><span data-stu-id="bbcef-116">You can make up to 15 calls per minute per tenant.</span></span>
4. <span data-ttu-id="bbcef-117">U hebt 10 minuten speeltijd per uur per tenant.</span><span class="sxs-lookup"><span data-stu-id="bbcef-117">You have 10 minutes of running time per hour per tenant.</span></span>
5. <span data-ttu-id="bbcef-118">U hebt in totaal vier uur aan gebruikstijden per dag per tenant.</span><span class="sxs-lookup"><span data-stu-id="bbcef-118">You have four total hours of running time per day per tenant.</span></span>
6. <span data-ttu-id="bbcef-119">Als één aanvraag langer dan 10 minuten wordt uitgevoerd, wordt er een time-out uitgevoerd en wordt er een foutbericht weergegeven.</span><span class="sxs-lookup"><span data-stu-id="bbcef-119">If a single request runs for more than 10 minutes, it will time out and return an error.</span></span>
7. <span data-ttu-id="bbcef-120">Een HTTP-antwoordcode geeft aan dat u een quotum hebt bereikt, hetzij op het aantal verzonden aanvragen, hetzij door de toegewezen `429` gebruikstijd.</span><span class="sxs-lookup"><span data-stu-id="bbcef-120">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="bbcef-121">Lees de antwoord body voor meer informatie over de limiet die u hebt bereikt.</span><span class="sxs-lookup"><span data-stu-id="bbcef-121">Read the response body to understand the limit you have reached.</span></span> 

> [!NOTE]
> <span data-ttu-id="bbcef-122">Alle quota die hierboven worden vermeld (bijvoorbeeld 15 oproepen per min) zijn per tenantgrootte.</span><span class="sxs-lookup"><span data-stu-id="bbcef-122">All quotas listed above (for example 15 calls per min) are per tenant size.</span></span> <span data-ttu-id="bbcef-123">Deze quota's zijn het minimum.</span><span class="sxs-lookup"><span data-stu-id="bbcef-123">These quotas are the minimum.</span></span>

## <a name="permissions"></a><span data-ttu-id="bbcef-124">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="bbcef-124">Permissions</span></span>

<span data-ttu-id="bbcef-125">Een van de volgende machtigingen is vereist om de geavanceerde api voor jagen te bellen.</span><span class="sxs-lookup"><span data-stu-id="bbcef-125">One of the following permissions is required to call the advanced hunting API.</span></span> <span data-ttu-id="bbcef-126">Zie [Access the Microsoft 365 Defender Protection API's (Access the Microsoft 365 Defender Protection](api-access.md) API's) voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="bbcef-126">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender Protection APIs](api-access.md)</span></span>

<span data-ttu-id="bbcef-127">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="bbcef-127">Permission type</span></span> | <span data-ttu-id="bbcef-128">Machtiging</span><span class="sxs-lookup"><span data-stu-id="bbcef-128">Permission</span></span> | <span data-ttu-id="bbcef-129">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="bbcef-129">Permission display name</span></span>
-|-|-
<span data-ttu-id="bbcef-130">Toepassing</span><span class="sxs-lookup"><span data-stu-id="bbcef-130">Application</span></span> | <span data-ttu-id="bbcef-131">AdvancedHunting.Read.All</span><span class="sxs-lookup"><span data-stu-id="bbcef-131">AdvancedHunting.Read.All</span></span> | <span data-ttu-id="bbcef-132">Geavanceerde query's uitvoeren</span><span class="sxs-lookup"><span data-stu-id="bbcef-132">Run advanced queries</span></span>
<span data-ttu-id="bbcef-133">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="bbcef-133">Delegated (work or school account)</span></span> | <span data-ttu-id="bbcef-134">AdvancedHunting.Read</span><span class="sxs-lookup"><span data-stu-id="bbcef-134">AdvancedHunting.Read</span></span> | <span data-ttu-id="bbcef-135">Geavanceerde query's uitvoeren</span><span class="sxs-lookup"><span data-stu-id="bbcef-135">Run advanced queries</span></span>

>[!Note]
> <span data-ttu-id="bbcef-136">Bij het verkrijgen van een token met gebruikersreferenties:</span><span class="sxs-lookup"><span data-stu-id="bbcef-136">When obtaining a token using user credentials:</span></span>
>
>- <span data-ttu-id="bbcef-137">De gebruiker moet de AD-rol 'Gegevens weergeven' hebben</span><span class="sxs-lookup"><span data-stu-id="bbcef-137">The user needs to have the 'View Data' AD role</span></span>
>- <span data-ttu-id="bbcef-138">De gebruiker moet toegang hebben tot het apparaat op basis van de instellingen van de apparaatgroep.</span><span class="sxs-lookup"><span data-stu-id="bbcef-138">The user needs to have access to the device, based on device group settings.</span></span>

## <a name="http-request"></a><span data-ttu-id="bbcef-139">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="bbcef-139">HTTP request</span></span>

```HTTP
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a><span data-ttu-id="bbcef-140">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="bbcef-140">Request headers</span></span>

<span data-ttu-id="bbcef-141">Koptekst</span><span class="sxs-lookup"><span data-stu-id="bbcef-141">Header</span></span> | <span data-ttu-id="bbcef-142">Waarde</span><span class="sxs-lookup"><span data-stu-id="bbcef-142">Value</span></span>
-|-
<span data-ttu-id="bbcef-143">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="bbcef-143">Authorization</span></span> | <span data-ttu-id="bbcef-144">Bearer {token} **Opmerking: vereist**</span><span class="sxs-lookup"><span data-stu-id="bbcef-144">Bearer {token} **Note: required**</span></span>
<span data-ttu-id="bbcef-145">Inhoudstype</span><span class="sxs-lookup"><span data-stu-id="bbcef-145">Content-Type</span></span> | <span data-ttu-id="bbcef-146">toepassing/json</span><span class="sxs-lookup"><span data-stu-id="bbcef-146">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="bbcef-147">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="bbcef-147">Request body</span></span>

<span data-ttu-id="bbcef-148">In de objectaanvraag moet u een JSON-object de volgende parameters geven:</span><span class="sxs-lookup"><span data-stu-id="bbcef-148">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="bbcef-149">Parameter</span><span class="sxs-lookup"><span data-stu-id="bbcef-149">Parameter</span></span> | <span data-ttu-id="bbcef-150">Type</span><span class="sxs-lookup"><span data-stu-id="bbcef-150">Type</span></span> | <span data-ttu-id="bbcef-151">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="bbcef-151">Description</span></span>
-|-|-
<span data-ttu-id="bbcef-152">Query</span><span class="sxs-lookup"><span data-stu-id="bbcef-152">Query</span></span> | <span data-ttu-id="bbcef-153">Tekst</span><span class="sxs-lookup"><span data-stu-id="bbcef-153">Text</span></span> | <span data-ttu-id="bbcef-154">De query die u wilt uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="bbcef-154">The query to run.</span></span> <span data-ttu-id="bbcef-155">**Opmerking: vereist**</span><span class="sxs-lookup"><span data-stu-id="bbcef-155">**Note: required**</span></span>

## <a name="response"></a><span data-ttu-id="bbcef-156">Antwoord</span><span class="sxs-lookup"><span data-stu-id="bbcef-156">Response</span></span>

<span data-ttu-id="bbcef-157">Als dit is gelukt, worden deze methode `200 OK` en een _object QueryResponse_ in de reactie-body als return gegeven.</span><span class="sxs-lookup"><span data-stu-id="bbcef-157">If successful, this method will return `200 OK`, and a _QueryResponse_ object in the response body.</span></span>

<span data-ttu-id="bbcef-158">Het antwoordobject bevat drie eigenschappen op het hoogste niveau:</span><span class="sxs-lookup"><span data-stu-id="bbcef-158">The response object contains three top-level properties:</span></span>

1. <span data-ttu-id="bbcef-159">Statistieken: een woordenlijst met prestatiestatistieken voor query's.</span><span class="sxs-lookup"><span data-stu-id="bbcef-159">Stats - A dictionary of query performance statistics.</span></span>
2. <span data-ttu-id="bbcef-160">Schema- Het schema van het antwoord, een lijst met Name-Type paren voor elke kolom.</span><span class="sxs-lookup"><span data-stu-id="bbcef-160">Schema - The schema of the response, a list of Name-Type pairs for each column.</span></span>
3. <span data-ttu-id="bbcef-161">Resultaten: een lijst met geavanceerde gebeurtenissen in de jacht.</span><span class="sxs-lookup"><span data-stu-id="bbcef-161">Results - A list of advanced hunting events.</span></span>

## <a name="example"></a><span data-ttu-id="bbcef-162">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="bbcef-162">Example</span></span>

<span data-ttu-id="bbcef-163">In het volgende voorbeeld verzendt een gebruiker de query hieronder en ontvangt een API-antwoordobject met `Stats` `Schema` , en `Results` .</span><span class="sxs-lookup"><span data-stu-id="bbcef-163">In the following example, a user sends the query below and receives an API response object containing `Stats`, `Schema`, and `Results`.</span></span>

### <a name="query"></a><span data-ttu-id="bbcef-164">Query</span><span class="sxs-lookup"><span data-stu-id="bbcef-164">Query</span></span>

```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

### <a name="response-object"></a><span data-ttu-id="bbcef-165">Antwoordobject</span><span class="sxs-lookup"><span data-stu-id="bbcef-165">Response object</span></span>

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

## <a name="related-articles"></a><span data-ttu-id="bbcef-166">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="bbcef-166">Related articles</span></span>

- [<span data-ttu-id="bbcef-167">De Microsoft 365 Defender-API's openen</span><span class="sxs-lookup"><span data-stu-id="bbcef-167">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="bbcef-168">Meer informatie over API-limieten en -licenties</span><span class="sxs-lookup"><span data-stu-id="bbcef-168">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="bbcef-169">Foutcodes begrijpen</span><span class="sxs-lookup"><span data-stu-id="bbcef-169">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="bbcef-170">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="bbcef-170">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
