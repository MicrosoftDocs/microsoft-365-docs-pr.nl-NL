---
title: Resultaten van livereacties ontvangen
description: Meer informatie over het ophalen van een specifiek resultaat van een livereactieopdracht door de index.
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
ms.openlocfilehash: d58fc87d16bb58199c95933d85752008a08a0e81
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879687"
---
#  <a name="get-live-response-results"></a><span data-ttu-id="7db22-104">Resultaten van livereacties ontvangen</span><span class="sxs-lookup"><span data-stu-id="7db22-104">Get live response results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7db22-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="7db22-105">**Applies to:**</span></span>
- [<span data-ttu-id="7db22-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="7db22-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)

[!include[Prerelease information](../../includes/prerelease.md)]

><span data-ttu-id="7db22-107">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="7db22-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="7db22-108">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="7db22-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="7db22-109">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="7db22-109">API description</span></span>

<span data-ttu-id="7db22-110">Hiermee wordt een specifiek resultaat van de livereactieopdracht opgehaald op de index.</span><span class="sxs-lookup"><span data-stu-id="7db22-110">Retrieves a specific live response command result by its index.</span></span>

## <a name="limitations"></a><span data-ttu-id="7db22-111">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="7db22-111">Limitations</span></span>

1.  <span data-ttu-id="7db22-112">Tariefbeperkingen voor deze API zijn 100 oproepen per minuut en 1500 oproepen per uur.</span><span class="sxs-lookup"><span data-stu-id="7db22-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="7db22-113">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="7db22-113">Permissions</span></span>

<span data-ttu-id="7db22-114">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="7db22-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="7db22-115">Zie Aan de slag voor meer informatie, waaronder hoe u machtigingen [kiest.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="7db22-115">To learn more, including how to choose permissions, see [Get started](apis-intro.md).</span></span>

| <span data-ttu-id="7db22-116">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="7db22-116">Permission type</span></span>                    | <span data-ttu-id="7db22-117">Machtiging</span><span class="sxs-lookup"><span data-stu-id="7db22-117">Permission</span></span>           | <span data-ttu-id="7db22-118">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="7db22-118">Permission display name</span></span>                   |
|------------------------------------|----------------------|-------------------------------------------|
| <span data-ttu-id="7db22-119">Toepassing</span><span class="sxs-lookup"><span data-stu-id="7db22-119">Application</span></span>                        | <span data-ttu-id="7db22-120">Machine.LiveResponse</span><span class="sxs-lookup"><span data-stu-id="7db22-120">Machine.LiveResponse</span></span> | <span data-ttu-id="7db22-121">Livereactie uitvoeren op een specifieke computer</span><span class="sxs-lookup"><span data-stu-id="7db22-121">Run live response on a specific machine</span></span> |
| <span data-ttu-id="7db22-122">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="7db22-122">Delegated (work or school account)</span></span> | <span data-ttu-id="7db22-123">Machine.LiveResponse</span><span class="sxs-lookup"><span data-stu-id="7db22-123">Machine.LiveResponse</span></span> | <span data-ttu-id="7db22-124">Livereactie uitvoeren op een specifieke computer</span><span class="sxs-lookup"><span data-stu-id="7db22-124">Run live response on a specific machine</span></span> |

## <a name="http-request"></a><span data-ttu-id="7db22-125">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="7db22-125">HTTP request</span></span>

```HTTP
GET https://api.securitycenter.microsoft.com/api/machineactions/{machine action
id}/GetLiveResponseResultDownloadLink(index={command-index})
```

## <a name="request-headers"></a><span data-ttu-id="7db22-126">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="7db22-126">Request headers</span></span>

| <span data-ttu-id="7db22-127">Naam</span><span class="sxs-lookup"><span data-stu-id="7db22-127">Name</span></span>      | <span data-ttu-id="7db22-128">Type</span><span class="sxs-lookup"><span data-stu-id="7db22-128">Type</span></span> | <span data-ttu-id="7db22-129">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="7db22-129">Description</span></span>               |
|---------------|----------|-------------------------------|
| <span data-ttu-id="7db22-130">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="7db22-130">Authorization</span></span> | <span data-ttu-id="7db22-131">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7db22-131">String</span></span>   | <span data-ttu-id="7db22-132">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="7db22-132">Bearer {token}.</span></span> <span data-ttu-id="7db22-133">Vereist.</span><span class="sxs-lookup"><span data-stu-id="7db22-133">Required.</span></span> |

## <a name="request-body"></a><span data-ttu-id="7db22-134">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="7db22-134">Request body</span></span>

<span data-ttu-id="7db22-135">Leeg</span><span class="sxs-lookup"><span data-stu-id="7db22-135">Empty</span></span>

## <a name="response"></a><span data-ttu-id="7db22-136">Antwoord</span><span class="sxs-lookup"><span data-stu-id="7db22-136">Response</span></span>

<span data-ttu-id="7db22-137">Als dit is gelukt, retourneert deze methode 200, Ok-antwoordcode met object met de koppeling naar het opdrachtresultaat in de *eigenschap waarde.*</span><span class="sxs-lookup"><span data-stu-id="7db22-137">If successful, this method returns 200, Ok response code with object that holds the link to the command result in the *value* property.</span></span> <span data-ttu-id="7db22-138">Deze koppeling is 30 minuten geldig en moet onmiddellijk worden gebruikt voor het downloaden van het pakket naar een lokale opslag.</span><span class="sxs-lookup"><span data-stu-id="7db22-138">This link is valid for 30 minutes and should be used immediately for downloading the package to a local storage.</span></span> <span data-ttu-id="7db22-139">Een verlopen koppeling kan opnieuw worden gemaakt door een ander gesprek en het is niet nodig om de livereactie opnieuw uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="7db22-139">An expired link can be re-created by another call, and there is no need to run live response again.</span></span>

<span data-ttu-id="7db22-140">*Eigenschappen van runscripttranscript:*</span><span class="sxs-lookup"><span data-stu-id="7db22-140">*Runscript transcript properties:*</span></span>

| <span data-ttu-id="7db22-141">Eigenschap</span><span class="sxs-lookup"><span data-stu-id="7db22-141">Property</span></span>  | <span data-ttu-id="7db22-142">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="7db22-142">Description</span></span>                       |
|---------------|---------------------------------------|
| <span data-ttu-id="7db22-143">naam</span><span class="sxs-lookup"><span data-stu-id="7db22-143">name</span></span>          | <span data-ttu-id="7db22-144">Naam van uitgevoerd script</span><span class="sxs-lookup"><span data-stu-id="7db22-144">Executed script name</span></span>                  |
| <span data-ttu-id="7db22-145">exit_code</span><span class="sxs-lookup"><span data-stu-id="7db22-145">exit_code</span></span>     | <span data-ttu-id="7db22-146">Scriptuitgangscode uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="7db22-146">Executed script exit code</span></span>             |
| <span data-ttu-id="7db22-147">script_output</span><span class="sxs-lookup"><span data-stu-id="7db22-147">script_output</span></span> | <span data-ttu-id="7db22-148">Standaarduitvoer voor uitgevoerd script</span><span class="sxs-lookup"><span data-stu-id="7db22-148">Executed script standard output</span></span>       |
| <span data-ttu-id="7db22-149">script_error</span><span class="sxs-lookup"><span data-stu-id="7db22-149">script_error</span></span>  | <span data-ttu-id="7db22-150">Standaarduitvoer van uitgevoerd script</span><span class="sxs-lookup"><span data-stu-id="7db22-150">Executed script standard error output</span></span> |

## <a name="example"></a><span data-ttu-id="7db22-151">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="7db22-151">Example</span></span>

<span data-ttu-id="7db22-152">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="7db22-152">**Request**</span></span>

<span data-ttu-id="7db22-153">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="7db22-153">Here is an example of the request.</span></span>

```HTTP
GET
https://api.securitycenter.microsoft.com/api/machineactions/988cc94e-7a8f-4b28-ab65-54970c5d5018/GetLiveResponseResultDownloadLink(index=0)
```

<span data-ttu-id="7db22-154">**Antwoord**</span><span class="sxs-lookup"><span data-stu-id="7db22-154">**Response**</span></span>

<span data-ttu-id="7db22-155">Hier is een voorbeeld van het antwoord.</span><span class="sxs-lookup"><span data-stu-id="7db22-155">Here is an example of the response.</span></span>

<span data-ttu-id="7db22-156">HTTP/1.1 200 Ok</span><span class="sxs-lookup"><span data-stu-id="7db22-156">HTTP/1.1 200 Ok</span></span>

<span data-ttu-id="7db22-157">Inhoudstype: toepassing/json</span><span class="sxs-lookup"><span data-stu-id="7db22-157">Content-type: application/json</span></span>

```JSON
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Edm.String",
    "value": "https://core.windows.net/investigation-actions-data/ID/CustomPlaybookCommandOutput/4ed5e7807ad1fe59b00b664fe06a0f07?se=2021-02-04T16%3A13%3A50Z&sp=r&sv=2019-07-07&sr=b&sig=1dYGe9rPvUlXBPvYSmr6/OLXPY98m8qWqfIQCBbyZTY%3D"
}
```

<span data-ttu-id="7db22-158">*Bestandsinhoud:*</span><span class="sxs-lookup"><span data-stu-id="7db22-158">*File content:*</span></span> 

```JSON
{
    "script_name": "minidump.ps1",
    "exit_code": 0,
    "script_output": "Transcript started, output file is C:\\ProgramData\\Microsoft\\Windows Defender Advanced Threat Protection\\Temp\\PSScriptOutputs\\PSScript_Transcript_{TRANSCRIPT_ID}.txt
C:\\windows\\TEMP\\OfficeClickToRun.dmp.zip\n51 MB\n\u0000\u0000\u0000",
    "script_error":""
}
```

## <a name="related-topics"></a><span data-ttu-id="7db22-159">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="7db22-159">Related topics</span></span>

- [<span data-ttu-id="7db22-160">Api voor machineactie krijgen</span><span class="sxs-lookup"><span data-stu-id="7db22-160">Get machine action API</span></span>](get-machineaction-object.md)
- [<span data-ttu-id="7db22-161">Computeractie annuleren</span><span class="sxs-lookup"><span data-stu-id="7db22-161">Cancel machine action</span></span>](cancel-machine-action.md)
- [<span data-ttu-id="7db22-162">Livereactie uitvoeren</span><span class="sxs-lookup"><span data-stu-id="7db22-162">Run live response</span></span>](run-live-response.md) 
