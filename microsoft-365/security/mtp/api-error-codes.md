---
title: Veelgebruikte foutcodes voor Microsoft 365 Defender REST API
description: Meer informatie over de veelvoorkomende foutcodes voor Microsoft 365 Defender REST API
keywords: API, fout, code, veelvoorkomende fouten, MTP, API-foutcodes
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
ms.openlocfilehash: 0df741efb7555d587a6033acc23716e93f542d5e
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719212"
---
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a><span data-ttu-id="a9fc2-104">Veelgebruikte foutcodes voor Microsoft 365 Defender REST API</span><span class="sxs-lookup"><span data-stu-id="a9fc2-104">Common Microsoft 365 Defender REST API error codes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="a9fc2-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="a9fc2-105">**Applies to:**</span></span>

- <span data-ttu-id="a9fc2-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="a9fc2-106">Microsoft Threat Protection</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a9fc2-107">Sommige informatie verhoudt zich tot een voorvrijgegeven product dat bij de commerciële versie van de commerciële versie mogelijk ingrijpend werd gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="a9fc2-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="a9fc2-108">Microsoft biedt geen garanties, expliciete of impliciete informatie met betrekking tot de informatie die u hier opgeeft.</span><span class="sxs-lookup"><span data-stu-id="a9fc2-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="a9fc2-109">Foutcodes kunnen als resultaat worden gegeven door een bewerking op een van de Microsoft 365 Defender-Api's.</span><span class="sxs-lookup"><span data-stu-id="a9fc2-109">Error codes may be returned by an operation on any of the Microsoft 365 Defender APIs.</span></span> <span data-ttu-id="a9fc2-110">Telkens wanneer een foutbericht wordt weergegeven, wordt een foutbericht weergegeven dat u kunt helpen dit probleem op te lossen.</span><span class="sxs-lookup"><span data-stu-id="a9fc2-110">Every error response will contain an error message, which can help resolve the problem.</span></span> <span data-ttu-id="a9fc2-111">De kolom foutbericht in de tabel sectie bevat enkele voorbeeldberichten.</span><span class="sxs-lookup"><span data-stu-id="a9fc2-111">The error message column in the table section provides some sample messages.</span></span> <span data-ttu-id="a9fc2-112">De inhoud van werkelijke berichten kan variëren, afhankelijk van de factoren die het antwoord hebben veroorzaakt.</span><span class="sxs-lookup"><span data-stu-id="a9fc2-112">The content of actual messages will vary based on the factors that triggered the response.</span></span> <span data-ttu-id="a9fc2-113">Variabele-inhoud wordt in de tabel aangegeven met punthaken.</span><span class="sxs-lookup"><span data-stu-id="a9fc2-113">Variable content is indicated in the table by angle brackets.</span></span>

## <a name="error-codes"></a><span data-ttu-id="a9fc2-114">Foutcodes</span><span class="sxs-lookup"><span data-stu-id="a9fc2-114">Error codes</span></span>

<span data-ttu-id="a9fc2-115">Foutcode</span><span class="sxs-lookup"><span data-stu-id="a9fc2-115">Error code</span></span> | <span data-ttu-id="a9fc2-116">HTTP-statuscode</span><span class="sxs-lookup"><span data-stu-id="a9fc2-116">HTTP status code</span></span> | <span data-ttu-id="a9fc2-117">Bericht</span><span class="sxs-lookup"><span data-stu-id="a9fc2-117">Message</span></span>
-|-|-
<span data-ttu-id="a9fc2-118">BadRequest</span><span class="sxs-lookup"><span data-stu-id="a9fc2-118">BadRequest</span></span> | <span data-ttu-id="a9fc2-119">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="a9fc2-119">BadRequest (400)</span></span> | <span data-ttu-id="a9fc2-120">Foutbericht over algemene onjuiste aanvraag.</span><span class="sxs-lookup"><span data-stu-id="a9fc2-120">General Bad Request error message.</span></span>
<span data-ttu-id="a9fc2-121">ODataError</span><span class="sxs-lookup"><span data-stu-id="a9fc2-121">ODataError</span></span> | <span data-ttu-id="a9fc2-122">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="a9fc2-122">BadRequest (400)</span></span> | <span data-ttu-id="a9fc2-123">Ongeldige OData URI-query \<the specific error is specified\> .</span><span class="sxs-lookup"><span data-stu-id="a9fc2-123">Invalid OData URI query \<the specific error is specified\>.</span></span>
<span data-ttu-id="a9fc2-124">InvalidInput</span><span class="sxs-lookup"><span data-stu-id="a9fc2-124">InvalidInput</span></span> | <span data-ttu-id="a9fc2-125">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="a9fc2-125">BadRequest (400)</span></span> | <span data-ttu-id="a9fc2-126">Ongeldige invoer \<the invalid input\> .</span><span class="sxs-lookup"><span data-stu-id="a9fc2-126">Invalid input \<the invalid input\>.</span></span>
<span data-ttu-id="a9fc2-127">InvalidRequestBody</span><span class="sxs-lookup"><span data-stu-id="a9fc2-127">InvalidRequestBody</span></span> | <span data-ttu-id="a9fc2-128">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="a9fc2-128">BadRequest (400)</span></span> | <span data-ttu-id="a9fc2-129">Ongeldige hoofdtekst van aanvraag.</span><span class="sxs-lookup"><span data-stu-id="a9fc2-129">Invalid request body.</span></span>
<span data-ttu-id="a9fc2-130">InvalidHashValue</span><span class="sxs-lookup"><span data-stu-id="a9fc2-130">InvalidHashValue</span></span> | <span data-ttu-id="a9fc2-131">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="a9fc2-131">BadRequest (400)</span></span> | <span data-ttu-id="a9fc2-132">Ongeldige hash-waarde \<the invalid hash\> .</span><span class="sxs-lookup"><span data-stu-id="a9fc2-132">Hash value \<the invalid hash\> is invalid.</span></span>
<span data-ttu-id="a9fc2-133">InvalidDomainName</span><span class="sxs-lookup"><span data-stu-id="a9fc2-133">InvalidDomainName</span></span> | <span data-ttu-id="a9fc2-134">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="a9fc2-134">BadRequest (400)</span></span> | <span data-ttu-id="a9fc2-135">Domeinnaam \<the invalid domain\> is ongeldig.</span><span class="sxs-lookup"><span data-stu-id="a9fc2-135">Domain name \<the invalid domain\> is invalid.</span></span>
<span data-ttu-id="a9fc2-136">InvalidIpAddress</span><span class="sxs-lookup"><span data-stu-id="a9fc2-136">InvalidIpAddress</span></span> | <span data-ttu-id="a9fc2-137">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="a9fc2-137">BadRequest (400)</span></span> | <span data-ttu-id="a9fc2-138">Het IP-adres \<the invalid IP\> is ongeldig.</span><span class="sxs-lookup"><span data-stu-id="a9fc2-138">IP address \<the invalid IP\> is invalid.</span></span>
<span data-ttu-id="a9fc2-139">InvalidUrl</span><span class="sxs-lookup"><span data-stu-id="a9fc2-139">InvalidUrl</span></span> | <span data-ttu-id="a9fc2-140">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="a9fc2-140">BadRequest (400)</span></span> | <span data-ttu-id="a9fc2-141">URL \<the invalid URL\> ongeldig is.</span><span class="sxs-lookup"><span data-stu-id="a9fc2-141">URL \<the invalid URL\> is invalid.</span></span>
<span data-ttu-id="a9fc2-142">MaximumBatchSizeExceeded</span><span class="sxs-lookup"><span data-stu-id="a9fc2-142">MaximumBatchSizeExceeded</span></span> | <span data-ttu-id="a9fc2-143">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="a9fc2-143">BadRequest (400)</span></span> | <span data-ttu-id="a9fc2-144">Maximale grootte van de batch overschreden.</span><span class="sxs-lookup"><span data-stu-id="a9fc2-144">Maximum batch size exceeded.</span></span> <span data-ttu-id="a9fc2-145">Ontvangen: \<batch size received\> , toegestaan: {batchgrootte toegestaan}.</span><span class="sxs-lookup"><span data-stu-id="a9fc2-145">Received: \<batch size received\>, allowed: {batch size allowed}.</span></span>
<span data-ttu-id="a9fc2-146">MissingRequiredParameter</span><span class="sxs-lookup"><span data-stu-id="a9fc2-146">MissingRequiredParameter</span></span> | <span data-ttu-id="a9fc2-147">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="a9fc2-147">BadRequest (400)</span></span> | <span data-ttu-id="a9fc2-148">Parameter \<the missing parameter\> ontbreekt.</span><span class="sxs-lookup"><span data-stu-id="a9fc2-148">Parameter \<the missing parameter\> is missing.</span></span>
<span data-ttu-id="a9fc2-149">OsPlatformNotSupported</span><span class="sxs-lookup"><span data-stu-id="a9fc2-149">OsPlatformNotSupported</span></span> | <span data-ttu-id="a9fc2-150">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="a9fc2-150">BadRequest (400)</span></span> | <span data-ttu-id="a9fc2-151">Het besturingssysteem platform \<the client OS Platform\> wordt niet ondersteund voor deze actie.</span><span class="sxs-lookup"><span data-stu-id="a9fc2-151">OS Platform \<the client OS Platform\> is not supported for this action.</span></span>
<span data-ttu-id="a9fc2-152">ClientVersionNotSupported</span><span class="sxs-lookup"><span data-stu-id="a9fc2-152">ClientVersionNotSupported</span></span> | <span data-ttu-id="a9fc2-153">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="a9fc2-153">BadRequest (400)</span></span> | <span data-ttu-id="a9fc2-154">\<The requested action\> wordt ondersteund op clientversie \<supported client version\> en hoger.</span><span class="sxs-lookup"><span data-stu-id="a9fc2-154">\<The requested action\> is supported on client version \<supported client version\> and above.</span></span>
<span data-ttu-id="a9fc2-155">Onbevoegde</span><span class="sxs-lookup"><span data-stu-id="a9fc2-155">Unauthorized</span></span> | <span data-ttu-id="a9fc2-156">Onbevoegd (401)</span><span class="sxs-lookup"><span data-stu-id="a9fc2-156">Unauthorized (401)</span></span> | <span data-ttu-id="a9fc2-157">Onbevoegde</span><span class="sxs-lookup"><span data-stu-id="a9fc2-157">Unauthorized</span></span> <br /><br /><span data-ttu-id="a9fc2-158">*Opmerking: doorgaans veroorzaakt een ongeldige of verlopen autorisatie header.*</span><span class="sxs-lookup"><span data-stu-id="a9fc2-158">*Note: Usually caused by an invalid or expired authorization header.*</span></span>
<span data-ttu-id="a9fc2-159">Slag</span><span class="sxs-lookup"><span data-stu-id="a9fc2-159">Forbidden</span></span> | <span data-ttu-id="a9fc2-160">Niet toegestaan (403)</span><span class="sxs-lookup"><span data-stu-id="a9fc2-160">Forbidden (403)</span></span> | <span data-ttu-id="a9fc2-161">Slag</span><span class="sxs-lookup"><span data-stu-id="a9fc2-161">Forbidden</span></span> <br /><br /><span data-ttu-id="a9fc2-162">*Opmerking: geldig token maar onvoldoende machtigingen voor de actie*.</span><span class="sxs-lookup"><span data-stu-id="a9fc2-162">*Note: Valid token but insufficient permission for the action*.</span></span>
<span data-ttu-id="a9fc2-163">DisabledFeature</span><span class="sxs-lookup"><span data-stu-id="a9fc2-163">DisabledFeature</span></span> | <span data-ttu-id="a9fc2-164">Niet toegestaan (403)</span><span class="sxs-lookup"><span data-stu-id="a9fc2-164">Forbidden (403)</span></span> | <span data-ttu-id="a9fc2-165">De Tenant functie is niet ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="a9fc2-165">Tenant feature is not enabled.</span></span>
<span data-ttu-id="a9fc2-166">DisallowedOperation</span><span class="sxs-lookup"><span data-stu-id="a9fc2-166">DisallowedOperation</span></span> | <span data-ttu-id="a9fc2-167">Niet toegestaan (403)</span><span class="sxs-lookup"><span data-stu-id="a9fc2-167">Forbidden (403)</span></span> | <span data-ttu-id="a9fc2-168">\<the disallowed operation and the reason\>.</span><span class="sxs-lookup"><span data-stu-id="a9fc2-168">\<the disallowed operation and the reason\>.</span></span>
<span data-ttu-id="a9fc2-169">NotFound</span><span class="sxs-lookup"><span data-stu-id="a9fc2-169">NotFound</span></span> | <span data-ttu-id="a9fc2-170">Niet gevonden (404)</span><span class="sxs-lookup"><span data-stu-id="a9fc2-170">Not Found (404)</span></span> | <span data-ttu-id="a9fc2-171">Foutbericht algemeen niet gevonden.</span><span class="sxs-lookup"><span data-stu-id="a9fc2-171">General Not Found error message.</span></span>
<span data-ttu-id="a9fc2-172">ResourceNotFound</span><span class="sxs-lookup"><span data-stu-id="a9fc2-172">ResourceNotFound</span></span> | <span data-ttu-id="a9fc2-173">Niet gevonden (404)</span><span class="sxs-lookup"><span data-stu-id="a9fc2-173">Not Found (404)</span></span> | <span data-ttu-id="a9fc2-174">De resource \<the requested resource\> is niet gevonden.</span><span class="sxs-lookup"><span data-stu-id="a9fc2-174">Resource \<the requested resource\> was not found.</span></span>
<span data-ttu-id="a9fc2-175">InternalServerError</span><span class="sxs-lookup"><span data-stu-id="a9fc2-175">InternalServerError</span></span> | <span data-ttu-id="a9fc2-176">Interne server fout (500)</span><span class="sxs-lookup"><span data-stu-id="a9fc2-176">Internal Server Error (500)</span></span> | <span data-ttu-id="a9fc2-177">*Opmerking: geen foutbericht, probeer de bewerking of neem contact op met Microsoft als deze niet wordt weergegeven.*</span><span class="sxs-lookup"><span data-stu-id="a9fc2-177">*Note: No error message,  retry the operation or contact Microsoft if it does not get resolved*</span></span>

## <a name="examples"></a><span data-ttu-id="a9fc2-178">Voorbeelden</span><span class="sxs-lookup"><span data-stu-id="a9fc2-178">Examples</span></span>

```json
{
    "error": {
        "code": "ResourceNotFound",
        "message": "Machine 123123123 was not found",
        "target": "43f4cb08-8fac-4b65-9db1-745c2ae65f3a"
    }
}
```

```json
{
    "error": {
        "code": "InvalidRequestBody",
        "message": "Request body is incorrect",
        "target": "1fa66c0f-18bd-4133-b378-36d76f3a2ba0"
    }
}
```

## <a name="body-parameters"></a><span data-ttu-id="a9fc2-179">Hoofd parameters</span><span class="sxs-lookup"><span data-stu-id="a9fc2-179">Body parameters</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a9fc2-180">Hoofd parameters zijn hoofdlettergevoelig.</span><span class="sxs-lookup"><span data-stu-id="a9fc2-180">Body parameters are case-sensitive.</span></span>

<span data-ttu-id="a9fc2-181">Als u een *InvalidRequestBody* -of *MissingRequiredParameter* -fout ondervindt, wordt dit mogelijk veroorzaakt door een type fout.</span><span class="sxs-lookup"><span data-stu-id="a9fc2-181">If you experience an *InvalidRequestBody* or *MissingRequiredParameter* error, it might be caused by a typo.</span></span> <span data-ttu-id="a9fc2-182">Bekijk de API-documentatie en controleer of de verzonden parameters overeenkomen met het relevante voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="a9fc2-182">Review the API documentation and check that the submitted parameters match the relevant example.</span></span>

## <a name="tracking-id"></a><span data-ttu-id="a9fc2-183">Tracking-ID</span><span class="sxs-lookup"><span data-stu-id="a9fc2-183">Tracking ID</span></span>

<span data-ttu-id="a9fc2-184">Elke foutmelding bevat een unieke ID-parameter voor bijhouden.</span><span class="sxs-lookup"><span data-stu-id="a9fc2-184">Each error response contains a unique ID parameter for tracking.</span></span> <span data-ttu-id="a9fc2-185">De naam van de eigenschap van deze parameter is *doel*.</span><span class="sxs-lookup"><span data-stu-id="a9fc2-185">The property name of this parameter is *target*.</span></span> <span data-ttu-id="a9fc2-186">Als u bij ons contact met ons opneemt, kunt u met deze ID de hoofdoorzaak van het probleem achterhalen.</span><span class="sxs-lookup"><span data-stu-id="a9fc2-186">When contacting us about an error, attaching this ID will help us find the root cause of the problem.</span></span>

## <a name="related-articles"></a><span data-ttu-id="a9fc2-187">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="a9fc2-187">Related articles</span></span>

- [<span data-ttu-id="a9fc2-188">Overzicht van Microsoft 365 Defender-Api's</span><span class="sxs-lookup"><span data-stu-id="a9fc2-188">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="a9fc2-189">Ondersteunde Microsoft 365 Defender-API's</span><span class="sxs-lookup"><span data-stu-id="a9fc2-189">Supported Microsoft 365 Defender APIs</span></span>](api-supported.md)
- [<span data-ttu-id="a9fc2-190">Toegang tot de Microsoft 365 Defender-Api's</span><span class="sxs-lookup"><span data-stu-id="a9fc2-190">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="a9fc2-191">Meer informatie over API-limieten en licenties</span><span class="sxs-lookup"><span data-stu-id="a9fc2-191">Learn about API limits and licensing</span></span>](api-terms.md)
