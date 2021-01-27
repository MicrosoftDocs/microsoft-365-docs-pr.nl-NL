---
title: Microsoft 365 Defender Advanced jacht API
description: Meer informatie over het uitvoeren van geavanceerde jacht-query's met behulp van de geavanceerde Microsoft 365-API
keywords: Geavanceerde jacht, Api's, API, MTP, M365 Defender, Microsoft 365 Defender
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
ms.openlocfilehash: 99f39a10de6231a72220c5c2a90ec915b1a4e44a
ms.sourcegitcommit: cbe8724bd71d1c002395d98f1451c5f578c824f9
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/26/2021
ms.locfileid: "49988114"
---
# <a name="microsoft-365-defender-advanced-hunting-api"></a><span data-ttu-id="5bbc1-104">Microsoft 365 Defender Advanced jacht API</span><span class="sxs-lookup"><span data-stu-id="5bbc1-104">Microsoft 365 Defender Advanced hunting API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="5bbc1-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="5bbc1-105">**Applies to:**</span></span>

- <span data-ttu-id="5bbc1-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="5bbc1-106">Microsoft Threat Protection</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5bbc1-107">Sommige informatie verhoudt zich tot een voorvrijgegeven product dat bij de commerciële versie van de commerciële versie mogelijk ingrijpend werd gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="5bbc1-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="5bbc1-108">Microsoft biedt geen garanties, expliciete of impliciete informatie met betrekking tot de informatie die u hier opgeeft.</span><span class="sxs-lookup"><span data-stu-id="5bbc1-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="5bbc1-109">[Geavanceerde jacht](advanced-hunting-overview.md) is een hulpprogramma voor een Threat-jacht waarbij [speciaal samengestelde query's](advanced-hunting-query-language.md) worden gebruikt om de afgelopen 30 dagen van gebeurtenisgegevens te bekijken in Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="5bbc1-109">[Advanced hunting](advanced-hunting-overview.md) is a threat-hunting tool that uses [specially constructed queries](advanced-hunting-query-language.md) to examine the past 30 days of event data in Microsoft 365 Defender.</span></span> <span data-ttu-id="5bbc1-110">U kunt geavanceerde jacht-query's gebruiken om ongebruikelijke activiteiten te controleren, mogelijke bedreigingen te detecteren en zelfs tegen aanvallen te reageren.</span><span class="sxs-lookup"><span data-stu-id="5bbc1-110">You can use advanced hunting queries to inspect unusual activity, detect possible threats, and even respond to attacks.</span></span> <span data-ttu-id="5bbc1-111">Met de Advanced jacht-API kunt u programmatische gegevens van querygebeurtenissen uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="5bbc1-111">The advanced hunting API allows you to programatically query event data.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="5bbc1-112">Quota's en resources toewijzen</span><span class="sxs-lookup"><span data-stu-id="5bbc1-112">Quotas and resource allocation</span></span>

<span data-ttu-id="5bbc1-113">De volgende voorwaarden hebben betrekking op alle query's.</span><span class="sxs-lookup"><span data-stu-id="5bbc1-113">The following conditions relate to all queries.</span></span>

1. <span data-ttu-id="5bbc1-114">Met query's worden gegevens uit de afgelopen 30 dagen verkend en geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="5bbc1-114">Queries explore and return data from the past 30 days.</span></span>
2. <span data-ttu-id="5bbc1-115">Resultaten kunnen resulteren in 100.000 rijen.</span><span class="sxs-lookup"><span data-stu-id="5bbc1-115">Results can return up to 100,000 rows.</span></span>
3. <span data-ttu-id="5bbc1-116">U kunt maximaal 15 oproepen per Tenant maken.</span><span class="sxs-lookup"><span data-stu-id="5bbc1-116">You can make up to 15 calls per minute per tenant.</span></span>
4. <span data-ttu-id="5bbc1-117">U hebt 10 minuten per uur tijdsperiode per Tenant.</span><span class="sxs-lookup"><span data-stu-id="5bbc1-117">You have 10 minutes of running time per hour per tenant.</span></span>
5. <span data-ttu-id="5bbc1-118">U hebt vier totale uren per dag per Tenant.</span><span class="sxs-lookup"><span data-stu-id="5bbc1-118">You have four total hours of running time per day per tenant.</span></span>
6. <span data-ttu-id="5bbc1-119">Als één verzoek langer dan 10 minuten wordt uitgevoerd, wordt de time-out weergegeven en wordt een fout geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="5bbc1-119">If a single request runs for more than 10 minutes, it will time out and return an error.</span></span>
7. <span data-ttu-id="5bbc1-120">Met een `429` HTTP-antwoordcode wordt aangegeven dat u een quotum hebt bereikt, hetzij op basis van het aantal ingediende aanvragen of over de beschikde periode.</span><span class="sxs-lookup"><span data-stu-id="5bbc1-120">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="5bbc1-121">Lees de antwoordtekst als u wilt weten wat de limiet is bereikt.</span><span class="sxs-lookup"><span data-stu-id="5bbc1-121">Read the response body to understand the limit you have reached.</span></span> 

> [!NOTE]
> <span data-ttu-id="5bbc1-122">Alle hierboven genoemde quota's (bijvoorbeeld 15 oproepen per min) zijn per Tenant grootte.</span><span class="sxs-lookup"><span data-stu-id="5bbc1-122">All quotas listed above (for example 15 calls per min) are per tenant size.</span></span> <span data-ttu-id="5bbc1-123">Dit zijn de quota's.</span><span class="sxs-lookup"><span data-stu-id="5bbc1-123">These quotas are the minimum.</span></span>

## <a name="permissions"></a><span data-ttu-id="5bbc1-124">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="5bbc1-124">Permissions</span></span>

<span data-ttu-id="5bbc1-125">U hebt een van de volgende machtigingen nodig om de API Advanced jacht te bellen.</span><span class="sxs-lookup"><span data-stu-id="5bbc1-125">One of the following permissions is required to call the advanced hunting API.</span></span> <span data-ttu-id="5bbc1-126">Voor meer informatie, waaronder de manier waarop u machtigingen kiest, raadpleegt u [de Microsoft 365 Defender-beveiligings-Api's openen](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="5bbc1-126">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender Protection APIs](api-access.md)</span></span>

<span data-ttu-id="5bbc1-127">Type machtiging</span><span class="sxs-lookup"><span data-stu-id="5bbc1-127">Permission type</span></span> | <span data-ttu-id="5bbc1-128">Machtigingsset</span><span class="sxs-lookup"><span data-stu-id="5bbc1-128">Permission</span></span> | <span data-ttu-id="5bbc1-129">Weergavenaam van de machtiging</span><span class="sxs-lookup"><span data-stu-id="5bbc1-129">Permission display name</span></span>
-|-|-
<span data-ttu-id="5bbc1-130">Toepassing</span><span class="sxs-lookup"><span data-stu-id="5bbc1-130">Application</span></span> | <span data-ttu-id="5bbc1-131">AdvancedHunting. Read. all</span><span class="sxs-lookup"><span data-stu-id="5bbc1-131">AdvancedHunting.Read.All</span></span> | <span data-ttu-id="5bbc1-132">Geavanceerde query's uitvoeren</span><span class="sxs-lookup"><span data-stu-id="5bbc1-132">Run advanced queries</span></span>
<span data-ttu-id="5bbc1-133">Gedelegeerd (werk-of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="5bbc1-133">Delegated (work or school account)</span></span> | <span data-ttu-id="5bbc1-134">AdvancedHunting. Read</span><span class="sxs-lookup"><span data-stu-id="5bbc1-134">AdvancedHunting.Read</span></span> | <span data-ttu-id="5bbc1-135">Geavanceerde query's uitvoeren</span><span class="sxs-lookup"><span data-stu-id="5bbc1-135">Run advanced queries</span></span>

>[!Note]
> <span data-ttu-id="5bbc1-136">Bij het verkrijgen van een token met behulp van gebruikersreferenties:</span><span class="sxs-lookup"><span data-stu-id="5bbc1-136">When obtaining a token using user credentials:</span></span>
>
>- <span data-ttu-id="5bbc1-137">De gebruiker moet de rol gegevens weergeven hebben</span><span class="sxs-lookup"><span data-stu-id="5bbc1-137">The user needs to have the 'View Data' AD role</span></span>
>- <span data-ttu-id="5bbc1-138">De gebruiker moet toegang hebben tot het apparaat, op basis van de instellingen van de apparaatgroepen.</span><span class="sxs-lookup"><span data-stu-id="5bbc1-138">The user needs to have access to the device, based on device group settings.</span></span>

## <a name="http-request"></a><span data-ttu-id="5bbc1-139">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="5bbc1-139">HTTP request</span></span>

```HTTP
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a><span data-ttu-id="5bbc1-140">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="5bbc1-140">Request headers</span></span>

<span data-ttu-id="5bbc1-141">Factuurkop</span><span class="sxs-lookup"><span data-stu-id="5bbc1-141">Header</span></span> | <span data-ttu-id="5bbc1-142">Value</span><span class="sxs-lookup"><span data-stu-id="5bbc1-142">Value</span></span>
-|-
<span data-ttu-id="5bbc1-143">Bevoegdheid</span><span class="sxs-lookup"><span data-stu-id="5bbc1-143">Authorization</span></span> | <span data-ttu-id="5bbc1-144">Bearer {token} **Opmerking: vereist**</span><span class="sxs-lookup"><span data-stu-id="5bbc1-144">Bearer {token} **Note: required**</span></span>
<span data-ttu-id="5bbc1-145">Inhouds type</span><span class="sxs-lookup"><span data-stu-id="5bbc1-145">Content-Type</span></span> | <span data-ttu-id="5bbc1-146">toepassing/JSON</span><span class="sxs-lookup"><span data-stu-id="5bbc1-146">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="5bbc1-147">Aanvraagtekst</span><span class="sxs-lookup"><span data-stu-id="5bbc1-147">Request body</span></span>

<span data-ttu-id="5bbc1-148">Geef in de hoofdtekst van de aanvraag een JSON-object op met de volgende parameters:</span><span class="sxs-lookup"><span data-stu-id="5bbc1-148">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="5bbc1-149">Tabelwaardeparameter</span><span class="sxs-lookup"><span data-stu-id="5bbc1-149">Parameter</span></span> | <span data-ttu-id="5bbc1-150">Type</span><span class="sxs-lookup"><span data-stu-id="5bbc1-150">Type</span></span> | <span data-ttu-id="5bbc1-151">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="5bbc1-151">Description</span></span>
-|-|-
<span data-ttu-id="5bbc1-152">Query</span><span class="sxs-lookup"><span data-stu-id="5bbc1-152">Query</span></span> | <span data-ttu-id="5bbc1-153">Tekst</span><span class="sxs-lookup"><span data-stu-id="5bbc1-153">Text</span></span> | <span data-ttu-id="5bbc1-154">De query wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="5bbc1-154">The query to run.</span></span> <span data-ttu-id="5bbc1-155">**Opmerking: vereist**</span><span class="sxs-lookup"><span data-stu-id="5bbc1-155">**Note: required**</span></span>

## <a name="response"></a><span data-ttu-id="5bbc1-156">Na</span><span class="sxs-lookup"><span data-stu-id="5bbc1-156">Response</span></span>

<span data-ttu-id="5bbc1-157">Als dit is gelukt, wordt deze methode geretourneerd `200 OK` en wordt een _QueryResponse_ -object in de tekst van het antwoord weergegeven.</span><span class="sxs-lookup"><span data-stu-id="5bbc1-157">If successful, this method will return `200 OK`, and a _QueryResponse_ object in the response body.</span></span>

<span data-ttu-id="5bbc1-158">Het antwoordobject bevat drie eigenschappen op het hoogste niveau:</span><span class="sxs-lookup"><span data-stu-id="5bbc1-158">The response object contains three top-level properties:</span></span>

1. <span data-ttu-id="5bbc1-159">Stats: een dictionary met statistieken voor queryprestaties.</span><span class="sxs-lookup"><span data-stu-id="5bbc1-159">Stats - A dictionary of query performance statistics.</span></span>
2. <span data-ttu-id="5bbc1-160">Schema: het schema van het antwoord, een lijst met Name-Type paren voor elke kolom.</span><span class="sxs-lookup"><span data-stu-id="5bbc1-160">Schema - The schema of the response, a list of Name-Type pairs for each column.</span></span>
3. <span data-ttu-id="5bbc1-161">Resultaten: een lijst met geavanceerde jacht gebeurtenissen.</span><span class="sxs-lookup"><span data-stu-id="5bbc1-161">Results - A list of advanced hunting events.</span></span>

## <a name="example"></a><span data-ttu-id="5bbc1-162">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="5bbc1-162">Example</span></span>

<span data-ttu-id="5bbc1-163">In het volgende voorbeeld worden de onderstaande query verzonden en ontvangt hij of zij een API-antwoordobject met de naam `Stats` , `Schema` en `Results` .</span><span class="sxs-lookup"><span data-stu-id="5bbc1-163">In the following example, a user sends the query below and receives an API response object containing `Stats`, `Schema`, and `Results`.</span></span>

### <a name="query"></a><span data-ttu-id="5bbc1-164">Query</span><span class="sxs-lookup"><span data-stu-id="5bbc1-164">Query</span></span>

```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

### <a name="response-object"></a><span data-ttu-id="5bbc1-165">Antwoordobject</span><span class="sxs-lookup"><span data-stu-id="5bbc1-165">Response object</span></span>

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

## <a name="related-articles"></a><span data-ttu-id="5bbc1-166">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="5bbc1-166">Related articles</span></span>

- [<span data-ttu-id="5bbc1-167">Toegang tot de Microsoft 365 Defender-Api's</span><span class="sxs-lookup"><span data-stu-id="5bbc1-167">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="5bbc1-168">Meer informatie over API-limieten en licenties</span><span class="sxs-lookup"><span data-stu-id="5bbc1-168">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="5bbc1-169">Meer informatie over foutcodes</span><span class="sxs-lookup"><span data-stu-id="5bbc1-169">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="5bbc1-170">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="5bbc1-170">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
