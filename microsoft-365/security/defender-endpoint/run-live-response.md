---
title: Opdrachten voor livereacties uitvoeren op een apparaat
description: Meer informatie over het uitvoeren van een reeks opdrachten voor livereacties op een apparaat.
keywords: api's, graph api, ondersteunde api's, uploaden naar bibliotheek
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 2a7daf18b1a1d791e7b92ded0a6b839bba1fd4c2
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879668"
---
#  <a name="run-live-response-commands-on-a-device"></a><span data-ttu-id="4a68f-104">Opdrachten voor livereacties uitvoeren op een apparaat</span><span class="sxs-lookup"><span data-stu-id="4a68f-104">Run live response commands on a device</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4a68f-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="4a68f-105">**Applies to:**</span></span>
- [<span data-ttu-id="4a68f-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="4a68f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)


[!include[Prerelease information](../../includes/prerelease.md)]

><span data-ttu-id="4a68f-107">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="4a68f-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="4a68f-108">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="4a68f-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="4a68f-109">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="4a68f-109">API description</span></span>

<span data-ttu-id="4a68f-110">Voert een reeks opdrachten voor livereacties uit op een apparaat</span><span class="sxs-lookup"><span data-stu-id="4a68f-110">Runs a sequence of live response commands on a device</span></span>

## <a name="limitations"></a><span data-ttu-id="4a68f-111">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="4a68f-111">Limitations</span></span>

1.  <span data-ttu-id="4a68f-112">Tariefbeperkingen voor deze API zijn 10 oproepen per minuut (extra aanvragen worden beantwoord met HTTP 429).</span><span class="sxs-lookup"><span data-stu-id="4a68f-112">Rate limitations for this API are 10 calls per minute (additional requests are responded with HTTP 429).</span></span>

2.  <span data-ttu-id="4a68f-113">25 gelijktijdige sessies (aanvragen die de beperkingslimiet overschrijden, ontvangen een antwoord op '429 - Te veel aanvragen').</span><span class="sxs-lookup"><span data-stu-id="4a68f-113">25 concurrently running sessions (requests exceeding the throttling limit will receive a "429 - Too many requests" response).</span></span>

3.  <span data-ttu-id="4a68f-114">Als de computer niet beschikbaar is, wordt de sessie maximaal 3 dagen in de wachtrij geplaatst.</span><span class="sxs-lookup"><span data-stu-id="4a68f-114">If the machine is not available, the session will be queued for up to 3 days.</span></span>

4.  <span data-ttu-id="4a68f-115">RunScript-opdracht time-outs na 10 minuten.</span><span class="sxs-lookup"><span data-stu-id="4a68f-115">RunScript command timeouts after 10 minutes.</span></span>

5.  <span data-ttu-id="4a68f-116">Wanneer een livereactieopdracht mislukt, worden alle gevolgde acties niet uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="4a68f-116">When a live response command fails all followed actions will not be executed.</span></span>

## <a name="permissions"></a><span data-ttu-id="4a68f-117">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="4a68f-117">Permissions</span></span>

<span data-ttu-id="4a68f-118">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="4a68f-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="4a68f-119">Zie Aan de slag voor meer informatie, waaronder hoe u machtigingen [kiest.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="4a68f-119">To learn more, including how to choose permissions, see [Get started](apis-intro.md).</span></span>

| <span data-ttu-id="4a68f-120">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="4a68f-120">Permission type</span></span>                    | <span data-ttu-id="4a68f-121">Machtiging</span><span class="sxs-lookup"><span data-stu-id="4a68f-121">Permission</span></span>           | <span data-ttu-id="4a68f-122">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="4a68f-122">Permission display name</span></span>                   |
|------------------------------------|----------------------|-------------------------------------------|
| <span data-ttu-id="4a68f-123">Toepassing</span><span class="sxs-lookup"><span data-stu-id="4a68f-123">Application</span></span>                        | <span data-ttu-id="4a68f-124">Machine.LiveResponse</span><span class="sxs-lookup"><span data-stu-id="4a68f-124">Machine.LiveResponse</span></span> | <span data-ttu-id="4a68f-125">Livereactie uitvoeren op een specifieke computer</span><span class="sxs-lookup"><span data-stu-id="4a68f-125">Run live response on a specific machine</span></span> |
| <span data-ttu-id="4a68f-126">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="4a68f-126">Delegated (work or school account)</span></span> | <span data-ttu-id="4a68f-127">Machine.LiveResponse</span><span class="sxs-lookup"><span data-stu-id="4a68f-127">Machine.LiveResponse</span></span> | <span data-ttu-id="4a68f-128">Livereactie uitvoeren op een specifieke computer</span><span class="sxs-lookup"><span data-stu-id="4a68f-128">Run live response on a specific machine</span></span> |

## <a name="http-request"></a><span data-ttu-id="4a68f-129">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="4a68f-129">HTTP request</span></span>

```HTTP
POST
https://api.securitycenter.microsoft.com/API/machines/{machine_id}/runliveresponse
```

## <a name="request-headers"></a><span data-ttu-id="4a68f-130">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="4a68f-130">Request headers</span></span>

| <span data-ttu-id="4a68f-131">Naam</span><span class="sxs-lookup"><span data-stu-id="4a68f-131">Name</span></span>      | <span data-ttu-id="4a68f-132">Type</span><span class="sxs-lookup"><span data-stu-id="4a68f-132">Type</span></span> | <span data-ttu-id="4a68f-133">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="4a68f-133">Description</span></span>                 |
|---------------|----------|---------------------------------|
| <span data-ttu-id="4a68f-134">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="4a68f-134">Authorization</span></span> | <span data-ttu-id="4a68f-135">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4a68f-135">String</span></span>   | <span data-ttu-id="4a68f-136">Bearer\<token>\.</span><span class="sxs-lookup"><span data-stu-id="4a68f-136">Bearer\<token>\.</span></span> <span data-ttu-id="4a68f-137">Vereist.</span><span class="sxs-lookup"><span data-stu-id="4a68f-137">Required.</span></span>   |
| <span data-ttu-id="4a68f-138">Inhoudstype</span><span class="sxs-lookup"><span data-stu-id="4a68f-138">Content-Type</span></span>  | <span data-ttu-id="4a68f-139">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4a68f-139">string</span></span>   | <span data-ttu-id="4a68f-140">toepassing/json.</span><span class="sxs-lookup"><span data-stu-id="4a68f-140">application/json.</span></span> <span data-ttu-id="4a68f-141">Vereist.</span><span class="sxs-lookup"><span data-stu-id="4a68f-141">Required.</span></span> |

## <a name="request-body"></a><span data-ttu-id="4a68f-142">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="4a68f-142">Request body</span></span>

| <span data-ttu-id="4a68f-143">Parameter</span><span class="sxs-lookup"><span data-stu-id="4a68f-143">Parameter</span></span> | <span data-ttu-id="4a68f-144">Type</span><span class="sxs-lookup"><span data-stu-id="4a68f-144">Type</span></span> | <span data-ttu-id="4a68f-145">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="4a68f-145">Description</span></span>                                                        |
|---------------|----------|------------------------------------------------------------------------|
| <span data-ttu-id="4a68f-146">Opmerking</span><span class="sxs-lookup"><span data-stu-id="4a68f-146">Comment</span></span>       | <span data-ttu-id="4a68f-147">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4a68f-147">String</span></span>   | <span data-ttu-id="4a68f-148">Opmerking om te koppelen aan de actie.</span><span class="sxs-lookup"><span data-stu-id="4a68f-148">Comment to associate with the action.</span></span>                                 |
| <span data-ttu-id="4a68f-149">Opdrachten</span><span class="sxs-lookup"><span data-stu-id="4a68f-149">Commands</span></span>      | <span data-ttu-id="4a68f-150">Matrix</span><span class="sxs-lookup"><span data-stu-id="4a68f-150">Array</span></span>    | <span data-ttu-id="4a68f-151">Opdrachten die u wilt uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="4a68f-151">Commands to run.</span></span> <span data-ttu-id="4a68f-152">Toegestane waarden zijn PutFile, RunScript, GetFile.</span><span class="sxs-lookup"><span data-stu-id="4a68f-152">Allowed values are PutFile, RunScript, GetFile.</span></span> |

<span data-ttu-id="4a68f-153">Opdrachten:</span><span class="sxs-lookup"><span data-stu-id="4a68f-153">Commands:</span></span>

| <span data-ttu-id="4a68f-154">Opdrachttype</span><span class="sxs-lookup"><span data-stu-id="4a68f-154">Command Type</span></span> | <span data-ttu-id="4a68f-155">Parameters</span><span class="sxs-lookup"><span data-stu-id="4a68f-155">Parameters</span></span>                                                                          | <span data-ttu-id="4a68f-156">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="4a68f-156">Description</span></span>                                                                                                                      |
|------------------|-----------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="4a68f-157">PutFile</span><span class="sxs-lookup"><span data-stu-id="4a68f-157">PutFile</span></span>      | <span data-ttu-id="4a68f-158">Sleutel: Bestandsnaam</span><span class="sxs-lookup"><span data-stu-id="4a68f-158">Key: FileName</span></span>  <br><br>  <span data-ttu-id="4a68f-159">Waarde: \<file name\></span><span class="sxs-lookup"><span data-stu-id="4a68f-159">Value: \<file name\></span></span>                                                                          | <span data-ttu-id="4a68f-160">Zet een bestand uit de bibliotheek op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="4a68f-160">Puts a file from the library to the device.</span></span> <span data-ttu-id="4a68f-161">Bestanden worden opgeslagen in een werkmap en worden verwijderd wanneer het apparaat standaard opnieuw wordt gestart.</span><span class="sxs-lookup"><span data-stu-id="4a68f-161">Files are saved in a working folder and are deleted when the device restarts by default.</span></span>
| <span data-ttu-id="4a68f-162">RunScript</span><span class="sxs-lookup"><span data-stu-id="4a68f-162">RunScript</span></span>    | <span data-ttu-id="4a68f-163">Sleutel: Scriptnaam</span><span class="sxs-lookup"><span data-stu-id="4a68f-163">Key: ScriptName</span></span><br><span data-ttu-id="4a68f-164">Waarde: \<Script from library\></span><span class="sxs-lookup"><span data-stu-id="4a68f-164">Value: \<Script from library\></span></span> <br><br> <span data-ttu-id="4a68f-165">Sleutel: Args</span><span class="sxs-lookup"><span data-stu-id="4a68f-165">Key: Args</span></span>  <br> <span data-ttu-id="4a68f-166">Waarde: \<Script arguments\></span><span class="sxs-lookup"><span data-stu-id="4a68f-166">Value: \<Script arguments\></span></span>                          | <span data-ttu-id="4a68f-167">Voert een script uit vanuit de bibliotheek op een apparaat.</span><span class="sxs-lookup"><span data-stu-id="4a68f-167">Runs a script from the library on a device.</span></span>    <br><br>  <span data-ttu-id="4a68f-168">De parameter Args wordt doorgegeven aan het script.</span><span class="sxs-lookup"><span data-stu-id="4a68f-168">The Args parameter is passed to your script.</span></span> <br><br> <span data-ttu-id="4a68f-169">Time-outs na 10 minuten.</span><span class="sxs-lookup"><span data-stu-id="4a68f-169">Timeouts after 10 minutes.</span></span>     
| <span data-ttu-id="4a68f-170">GetFile</span><span class="sxs-lookup"><span data-stu-id="4a68f-170">GetFile</span></span>      | <span data-ttu-id="4a68f-171">Sleutel: Pad</span><span class="sxs-lookup"><span data-stu-id="4a68f-171">Key: Path</span></span> <br> <span data-ttu-id="4a68f-172">Waarde: \<File path\></span><span class="sxs-lookup"><span data-stu-id="4a68f-172">Value: \<File path\></span></span>                                                        | <span data-ttu-id="4a68f-173">Bestanden verzamelen vanaf een apparaat.</span><span class="sxs-lookup"><span data-stu-id="4a68f-173">Collect file from a device.</span></span> <span data-ttu-id="4a68f-174">OPMERKING: Backslashes in pad moeten worden ontsnapt.</span><span class="sxs-lookup"><span data-stu-id="4a68f-174">NOTE: Backslashes in path must be escaped.</span></span>                                                                      |

## <a name="response"></a><span data-ttu-id="4a68f-175">Antwoord</span><span class="sxs-lookup"><span data-stu-id="4a68f-175">Response</span></span>

-   <span data-ttu-id="4a68f-176">Als dit is gelukt, retourneert deze methode 200, ok.</span><span class="sxs-lookup"><span data-stu-id="4a68f-176">If successful, this method returns 200, Ok.</span></span>
    <span data-ttu-id="4a68f-177">Actie-entiteit.</span><span class="sxs-lookup"><span data-stu-id="4a68f-177">Action entity.</span></span> <span data-ttu-id="4a68f-178">Als de computer met de opgegeven id niet is gevonden- 404 Niet gevonden.</span><span class="sxs-lookup"><span data-stu-id="4a68f-178">If machine with the specified ID was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="4a68f-179">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="4a68f-179">Example</span></span>

<span data-ttu-id="4a68f-180">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="4a68f-180">**Request**</span></span>

<span data-ttu-id="4a68f-181">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="4a68f-181">Here is an example of the request.</span></span>

```HTTP

POST
https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/runliveresponse

```
<span data-ttu-id="4a68f-182">**JSON**</span><span class="sxs-lookup"><span data-stu-id="4a68f-182">**JSON**</span></span>

```JSON
{
   "Commands":[
      {
         "type":"RunScript",
         "params":[
            {
               "key":"ScriptName",
               "value":"minidump.ps1"
            },
            {
               "key":"Args",
               "value":"OfficeClickToRun"
            }

         ]
      },
      {
         "type":"GetFile",
         "params":[
            {
               "key":"Path",
               "value":"C:\\windows\\TEMP\\OfficeClickToRun.dmp.zip"
            }
         ]
      }
   ],
   "Comment":"Testing Live Response API"
}
```

<span data-ttu-id="4a68f-183">**Antwoord**</span><span class="sxs-lookup"><span data-stu-id="4a68f-183">**Response**</span></span>

<span data-ttu-id="4a68f-184">Hier is een voorbeeld van het antwoord.</span><span class="sxs-lookup"><span data-stu-id="4a68f-184">Here is an example of the response.</span></span>

```HTTP
HTTP/1.1 200 Ok
```

<span data-ttu-id="4a68f-185">Inhoudstype: toepassing/json</span><span class="sxs-lookup"><span data-stu-id="4a68f-185">Content-type: application/json</span></span>

```JSON
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineActions/$entity",
    "id": "{machine_action_id}",
    "type": "LiveResponse",
    "requestor": "analyst@microsoft.com",
    "requestorComment": "Testing Live Response API",
    "status": "Pending",
    "machineId": "{machine_id}",
    "computerDnsName": "hostname",
    "creationDateTimeUtc": "2021-02-04T15:36:52.7788848Z",
    "lastUpdateDateTimeUtc": "2021-02-04T15:36:52.7788848Z",
    "errorHResult": 0,
    "commands": [
        {
            "index": 0,
            "startTime": null,
            "endTime": null,
            "commandStatus": "Created",
            "errors": [],
            "command": {
                "type": "RunScript",
                "params": [
                    {
                        "key": "ScriptName",
                        "value": "minidump.ps1"
                    },{
                        "key": "Args",
                        "value": "OfficeClickToRun"
                    }
                ]
            }
        }, {
            "index": 1,
            "startTime": null,
            "endTime": null,
            "commandStatus": "Created",
            "errors": [],
            "command": {
                "type": "GetFile",
                "params": [{
                        "key": "Path", "value": "C:\\windows\\TEMP\\OfficeClickToRun.dmp.zip"
                    }
                ]
            }
        }
    ]
}


```

## <a name="related-topics"></a><span data-ttu-id="4a68f-186">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="4a68f-186">Related topics</span></span>
- [<span data-ttu-id="4a68f-187">Api voor machineactie krijgen</span><span class="sxs-lookup"><span data-stu-id="4a68f-187">Get machine action API</span></span>](get-machineaction-object.md)
- [<span data-ttu-id="4a68f-188">Live-antwoordresultaat ontvangen</span><span class="sxs-lookup"><span data-stu-id="4a68f-188">Get live response result</span></span>](get-live-response-result.md)
- [<span data-ttu-id="4a68f-189">Computeractie annuleren</span><span class="sxs-lookup"><span data-stu-id="4a68f-189">Cancel machine action</span></span>](cancel-machine-action.md)
