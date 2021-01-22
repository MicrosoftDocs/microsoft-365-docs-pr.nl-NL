---
title: Veelvoorkomende foutcodes voor Microsoft 365 Defender REST API
description: Meer informatie over de veelgebruikte foutcodes voor Microsoft 365 Defender REST API
keywords: api, fout, codes, veelvoorkomende fouten, mtp, api-foutcodes
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
ms.openlocfilehash: 15eabc8ff28e7cc0313e2a1cb701403de0eab120
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928388"
---
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a><span data-ttu-id="a3e19-104">Veelvoorkomende foutcodes voor Microsoft 365 Defender REST API</span><span class="sxs-lookup"><span data-stu-id="a3e19-104">Common Microsoft 365 Defender REST API error codes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="a3e19-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="a3e19-105">**Applies to:**</span></span>

- <span data-ttu-id="a3e19-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="a3e19-106">Microsoft Threat Protection</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a3e19-107">Sommige informatie heeft betrekking op vooraf uitgebracht product dat aanzienlijk kan worden gewijzigd voordat het in de handel wordt gebracht.</span><span class="sxs-lookup"><span data-stu-id="a3e19-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="a3e19-108">Microsoft biedt geen garanties, uitdrukkelijk of impliciet, met betrekking tot de informatie die hier wordt be gegeven.</span><span class="sxs-lookup"><span data-stu-id="a3e19-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="a3e19-109">Foutcodes kunnen worden geretourneerd door een bewerking op een van de Microsoft 365 Defender-API's.</span><span class="sxs-lookup"><span data-stu-id="a3e19-109">Error codes may be returned by an operation on any of the Microsoft 365 Defender APIs.</span></span> <span data-ttu-id="a3e19-110">Elk foutbericht bevat een foutbericht waarmee het probleem kan worden opgelost.</span><span class="sxs-lookup"><span data-stu-id="a3e19-110">Every error response will contain an error message, which can help resolve the problem.</span></span> <span data-ttu-id="a3e19-111">De kolom foutbericht in de tabelsectie bevat enkele voorbeeldberichten.</span><span class="sxs-lookup"><span data-stu-id="a3e19-111">The error message column in the table section provides some sample messages.</span></span> <span data-ttu-id="a3e19-112">De inhoud van feitelijke berichten is afhankelijk van de factoren die de reactie hebben veroorzaakt.</span><span class="sxs-lookup"><span data-stu-id="a3e19-112">The content of actual messages will vary based on the factors that triggered the response.</span></span> <span data-ttu-id="a3e19-113">Variabele inhoud wordt in de tabel aangegeven met haakjes.</span><span class="sxs-lookup"><span data-stu-id="a3e19-113">Variable content is indicated in the table by angle brackets.</span></span>

## <a name="error-codes"></a><span data-ttu-id="a3e19-114">Foutcodes</span><span class="sxs-lookup"><span data-stu-id="a3e19-114">Error codes</span></span>

<span data-ttu-id="a3e19-115">Foutcode</span><span class="sxs-lookup"><span data-stu-id="a3e19-115">Error code</span></span> | <span data-ttu-id="a3e19-116">HTTP-statuscode</span><span class="sxs-lookup"><span data-stu-id="a3e19-116">HTTP status code</span></span> | <span data-ttu-id="a3e19-117">Bericht</span><span class="sxs-lookup"><span data-stu-id="a3e19-117">Message</span></span>
-|-|-
<span data-ttu-id="a3e19-118">BadRequest</span><span class="sxs-lookup"><span data-stu-id="a3e19-118">BadRequest</span></span> | <span data-ttu-id="a3e19-119">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="a3e19-119">BadRequest (400)</span></span> | <span data-ttu-id="a3e19-120">Foutbericht over algemene bad request.</span><span class="sxs-lookup"><span data-stu-id="a3e19-120">General Bad Request error message.</span></span>
<span data-ttu-id="a3e19-121">ODataError</span><span class="sxs-lookup"><span data-stu-id="a3e19-121">ODataError</span></span> | <span data-ttu-id="a3e19-122">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="a3e19-122">BadRequest (400)</span></span> | <span data-ttu-id="a3e19-123">Ongeldige OData \<the specific error is specified\> URI-query.</span><span class="sxs-lookup"><span data-stu-id="a3e19-123">Invalid OData URI query \<the specific error is specified\>.</span></span>
<span data-ttu-id="a3e19-124">InvalidInput</span><span class="sxs-lookup"><span data-stu-id="a3e19-124">InvalidInput</span></span> | <span data-ttu-id="a3e19-125">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="a3e19-125">BadRequest (400)</span></span> | <span data-ttu-id="a3e19-126">Ongeldige \<the invalid input\> invoer.</span><span class="sxs-lookup"><span data-stu-id="a3e19-126">Invalid input \<the invalid input\>.</span></span>
<span data-ttu-id="a3e19-127">InvalidRequest Heely</span><span class="sxs-lookup"><span data-stu-id="a3e19-127">InvalidRequestBody</span></span> | <span data-ttu-id="a3e19-128">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="a3e19-128">BadRequest (400)</span></span> | <span data-ttu-id="a3e19-129">Ongeldige aanvraag body.</span><span class="sxs-lookup"><span data-stu-id="a3e19-129">Invalid request body.</span></span>
<span data-ttu-id="a3e19-130">InvalidHashValue</span><span class="sxs-lookup"><span data-stu-id="a3e19-130">InvalidHashValue</span></span> | <span data-ttu-id="a3e19-131">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="a3e19-131">BadRequest (400)</span></span> | <span data-ttu-id="a3e19-132">De hashwaarde \<the invalid hash\> is ongeldig.</span><span class="sxs-lookup"><span data-stu-id="a3e19-132">Hash value \<the invalid hash\> is invalid.</span></span>
<span data-ttu-id="a3e19-133">InvalidDomainName</span><span class="sxs-lookup"><span data-stu-id="a3e19-133">InvalidDomainName</span></span> | <span data-ttu-id="a3e19-134">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="a3e19-134">BadRequest (400)</span></span> | <span data-ttu-id="a3e19-135">Domeinnaam \<the invalid domain\> is ongeldig.</span><span class="sxs-lookup"><span data-stu-id="a3e19-135">Domain name \<the invalid domain\> is invalid.</span></span>
<span data-ttu-id="a3e19-136">InvalidIpAddress</span><span class="sxs-lookup"><span data-stu-id="a3e19-136">InvalidIpAddress</span></span> | <span data-ttu-id="a3e19-137">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="a3e19-137">BadRequest (400)</span></span> | <span data-ttu-id="a3e19-138">HET \<the invalid IP\> IP-adres is ongeldig.</span><span class="sxs-lookup"><span data-stu-id="a3e19-138">IP address \<the invalid IP\> is invalid.</span></span>
<span data-ttu-id="a3e19-139">InvalidUrl</span><span class="sxs-lookup"><span data-stu-id="a3e19-139">InvalidUrl</span></span> | <span data-ttu-id="a3e19-140">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="a3e19-140">BadRequest (400)</span></span> | <span data-ttu-id="a3e19-141">URL \<the invalid URL\> is ongeldig.</span><span class="sxs-lookup"><span data-stu-id="a3e19-141">URL \<the invalid URL\> is invalid.</span></span>
<span data-ttu-id="a3e19-142">MaximumBatchSizeExceeded</span><span class="sxs-lookup"><span data-stu-id="a3e19-142">MaximumBatchSizeExceeded</span></span> | <span data-ttu-id="a3e19-143">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="a3e19-143">BadRequest (400)</span></span> | <span data-ttu-id="a3e19-144">De maximale batchgrootte is overschreden.</span><span class="sxs-lookup"><span data-stu-id="a3e19-144">Maximum batch size exceeded.</span></span> <span data-ttu-id="a3e19-145">Ontvangen: \<batch size received\> , toegestaan: {batch size allowed}.</span><span class="sxs-lookup"><span data-stu-id="a3e19-145">Received: \<batch size received\>, allowed: {batch size allowed}.</span></span>
<span data-ttu-id="a3e19-146">MissingRequiredParameter</span><span class="sxs-lookup"><span data-stu-id="a3e19-146">MissingRequiredParameter</span></span> | <span data-ttu-id="a3e19-147">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="a3e19-147">BadRequest (400)</span></span> | <span data-ttu-id="a3e19-148">De parameter \<the missing parameter\> ontbreekt.</span><span class="sxs-lookup"><span data-stu-id="a3e19-148">Parameter \<the missing parameter\> is missing.</span></span>
<span data-ttu-id="a3e19-149">OsPlatformNotSupported</span><span class="sxs-lookup"><span data-stu-id="a3e19-149">OsPlatformNotSupported</span></span> | <span data-ttu-id="a3e19-150">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="a3e19-150">BadRequest (400)</span></span> | <span data-ttu-id="a3e19-151">Het \<the client OS Platform\> besturingssysteemplatform wordt niet ondersteund voor deze actie.</span><span class="sxs-lookup"><span data-stu-id="a3e19-151">OS Platform \<the client OS Platform\> is not supported for this action.</span></span>
<span data-ttu-id="a3e19-152">ClientVersionNotSupported</span><span class="sxs-lookup"><span data-stu-id="a3e19-152">ClientVersionNotSupported</span></span> | <span data-ttu-id="a3e19-153">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="a3e19-153">BadRequest (400)</span></span> | <span data-ttu-id="a3e19-154">\<The requested action\> wordt ondersteund in de clientversie \<supported client version\> en hoger.</span><span class="sxs-lookup"><span data-stu-id="a3e19-154">\<The requested action\> is supported on client version \<supported client version\> and above.</span></span>
<span data-ttu-id="a3e19-155">Niet geautoriseerd</span><span class="sxs-lookup"><span data-stu-id="a3e19-155">Unauthorized</span></span> | <span data-ttu-id="a3e19-156">Niet geautoriseerd (401)</span><span class="sxs-lookup"><span data-stu-id="a3e19-156">Unauthorized (401)</span></span> | <span data-ttu-id="a3e19-157">Niet geautoriseerd</span><span class="sxs-lookup"><span data-stu-id="a3e19-157">Unauthorized</span></span> <br /><br /><span data-ttu-id="a3e19-158">*Opmerking: Meestal veroorzaakt door een ongeldige of verlopen autorisatiekop.*</span><span class="sxs-lookup"><span data-stu-id="a3e19-158">*Note: Usually caused by an invalid or expired authorization header.*</span></span>
<span data-ttu-id="a3e19-159">Verboden</span><span class="sxs-lookup"><span data-stu-id="a3e19-159">Forbidden</span></span> | <span data-ttu-id="a3e19-160">Verboden (403)</span><span class="sxs-lookup"><span data-stu-id="a3e19-160">Forbidden (403)</span></span> | <span data-ttu-id="a3e19-161">Verboden</span><span class="sxs-lookup"><span data-stu-id="a3e19-161">Forbidden</span></span> <br /><br /><span data-ttu-id="a3e19-162">*Opmerking: Geldig token, maar onvoldoende machtigingen voor de actie.*</span><span class="sxs-lookup"><span data-stu-id="a3e19-162">*Note: Valid token but insufficient permission for the action*.</span></span>
<span data-ttu-id="a3e19-163">DisabledFeature</span><span class="sxs-lookup"><span data-stu-id="a3e19-163">DisabledFeature</span></span> | <span data-ttu-id="a3e19-164">Verboden (403)</span><span class="sxs-lookup"><span data-stu-id="a3e19-164">Forbidden (403)</span></span> | <span data-ttu-id="a3e19-165">Tenantfunctie is niet ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="a3e19-165">Tenant feature is not enabled.</span></span>
<span data-ttu-id="a3e19-166">DisallowedOperation</span><span class="sxs-lookup"><span data-stu-id="a3e19-166">DisallowedOperation</span></span> | <span data-ttu-id="a3e19-167">Verboden (403)</span><span class="sxs-lookup"><span data-stu-id="a3e19-167">Forbidden (403)</span></span> | <span data-ttu-id="a3e19-168">\<the disallowed operation and the reason\>.</span><span class="sxs-lookup"><span data-stu-id="a3e19-168">\<the disallowed operation and the reason\>.</span></span>
<span data-ttu-id="a3e19-169">NotFound</span><span class="sxs-lookup"><span data-stu-id="a3e19-169">NotFound</span></span> | <span data-ttu-id="a3e19-170">Niet gevonden (404)</span><span class="sxs-lookup"><span data-stu-id="a3e19-170">Not Found (404)</span></span> | <span data-ttu-id="a3e19-171">Foutbericht Algemeen niet gevonden.</span><span class="sxs-lookup"><span data-stu-id="a3e19-171">General Not Found error message.</span></span>
<span data-ttu-id="a3e19-172">ResourceNotFound</span><span class="sxs-lookup"><span data-stu-id="a3e19-172">ResourceNotFound</span></span> | <span data-ttu-id="a3e19-173">Niet gevonden (404)</span><span class="sxs-lookup"><span data-stu-id="a3e19-173">Not Found (404)</span></span> | <span data-ttu-id="a3e19-174">Resource \<the requested resource\> is niet gevonden.</span><span class="sxs-lookup"><span data-stu-id="a3e19-174">Resource \<the requested resource\> was not found.</span></span>
<span data-ttu-id="a3e19-175">InternalServerError</span><span class="sxs-lookup"><span data-stu-id="a3e19-175">InternalServerError</span></span> | <span data-ttu-id="a3e19-176">Interne serverfout (500)</span><span class="sxs-lookup"><span data-stu-id="a3e19-176">Internal Server Error (500)</span></span> | <span data-ttu-id="a3e19-177">*Opmerking: Geen foutbericht, de bewerking opnieuw uitvoeren of contact opnemen met Microsoft als dit niet wordt opgelost*</span><span class="sxs-lookup"><span data-stu-id="a3e19-177">*Note: No error message,  retry the operation or contact Microsoft if it does not get resolved*</span></span>

## <a name="examples"></a><span data-ttu-id="a3e19-178">Voorbeelden</span><span class="sxs-lookup"><span data-stu-id="a3e19-178">Examples</span></span>

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

## <a name="body-parameters"></a><span data-ttu-id="a3e19-179">Parameters voor de body</span><span class="sxs-lookup"><span data-stu-id="a3e19-179">Body parameters</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a3e19-180">Bodyparameters zijn case-sensitive.</span><span class="sxs-lookup"><span data-stu-id="a3e19-180">Body parameters are case-sensitive.</span></span>

<span data-ttu-id="a3e19-181">Als er een invalidRequest Wordt weergegeven in de fout *InvalidRequestAntwoordy* of *MissingRequiredParameter,* wordt deze mogelijk veroorzaakt door een typfout.</span><span class="sxs-lookup"><span data-stu-id="a3e19-181">If you experience an *InvalidRequestBody* or *MissingRequiredParameter* error, it might be caused by a typo.</span></span> <span data-ttu-id="a3e19-182">Raadpleeg de DOCUMENTATIE van de API en controleer of de ingediende parameters overeenkomen met het desbetreffende voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="a3e19-182">Review the API documentation and check that the submitted parameters match the relevant example.</span></span>

## <a name="tracking-id"></a><span data-ttu-id="a3e19-183">Tracerings-id</span><span class="sxs-lookup"><span data-stu-id="a3e19-183">Tracking ID</span></span>

<span data-ttu-id="a3e19-184">Elke foutreactie bevat een unieke id-parameter om bij te houden.</span><span class="sxs-lookup"><span data-stu-id="a3e19-184">Each error response contains a unique ID parameter for tracking.</span></span> <span data-ttu-id="a3e19-185">De eigenschapsnaam van deze parameter is *doel.*</span><span class="sxs-lookup"><span data-stu-id="a3e19-185">The property name of this parameter is *target*.</span></span> <span data-ttu-id="a3e19-186">Wanneer u contact met ons op neemt over een fout, helpt het koppelen van deze id ons om de oorzaak van het probleem te vinden.</span><span class="sxs-lookup"><span data-stu-id="a3e19-186">When contacting us about an error, attaching this ID will help us find the root cause of the problem.</span></span>

## <a name="related-articles"></a><span data-ttu-id="a3e19-187">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="a3e19-187">Related articles</span></span>

- [<span data-ttu-id="a3e19-188">Overzicht van Microsoft 365 Defender API's</span><span class="sxs-lookup"><span data-stu-id="a3e19-188">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="a3e19-189">Ondersteunde Microsoft 365 Defender-API's</span><span class="sxs-lookup"><span data-stu-id="a3e19-189">Supported Microsoft 365 Defender APIs</span></span>](api-supported.md)
- [<span data-ttu-id="a3e19-190">Toegang tot de Microsoft 365 Defender-API's</span><span class="sxs-lookup"><span data-stu-id="a3e19-190">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="a3e19-191">Meer informatie over API-limieten en licenties</span><span class="sxs-lookup"><span data-stu-id="a3e19-191">Learn about API limits and licensing</span></span>](api-terms.md)
