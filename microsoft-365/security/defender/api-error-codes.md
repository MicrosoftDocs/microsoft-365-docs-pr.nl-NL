---
title: Veelgebruikte Microsoft 365 Defender REST API-foutcodes
description: Meer informatie over de algemene Microsoft 365 Defender REST API-foutcodes
keywords: api, fout, codes, veelvoorkomende fouten, Microsoft 365 Defender, api-foutcodes
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
ms.openlocfilehash: e621b79d37a2c3a22394bd51e0493334eff461c7
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932879"
---
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a><span data-ttu-id="d7355-104">Veelgebruikte Microsoft 365 Defender REST API-foutcodes</span><span class="sxs-lookup"><span data-stu-id="d7355-104">Common Microsoft 365 Defender REST API error codes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="d7355-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="d7355-105">**Applies to:**</span></span>

- <span data-ttu-id="d7355-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d7355-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d7355-107">Sommige informatie is gerelateerd aan voorlopige productversies die mogelijk aanzienlijk gewijzigd worden voordat ze commercieel gepubliceerd worden.</span><span class="sxs-lookup"><span data-stu-id="d7355-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="d7355-108">Microsoft geeft geen garantie, uitdrukkelijk of impliciet, met betrekking tot de informatie die hier wordt beschreven.</span><span class="sxs-lookup"><span data-stu-id="d7355-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="d7355-109">Foutcodes kunnen worden geretourneerd door een bewerking op een van de Microsoft 365 Defender-API's.</span><span class="sxs-lookup"><span data-stu-id="d7355-109">Error codes may be returned by an operation on any of the Microsoft 365 Defender APIs.</span></span> <span data-ttu-id="d7355-110">Elke foutreactie bevat een foutbericht, waarmee het probleem kan worden opgelost.</span><span class="sxs-lookup"><span data-stu-id="d7355-110">Every error response will contain an error message, which can help resolve the problem.</span></span> <span data-ttu-id="d7355-111">De kolom met foutberichten in de tabelsectie bevat enkele voorbeeldberichten.</span><span class="sxs-lookup"><span data-stu-id="d7355-111">The error message column in the table section provides some sample messages.</span></span> <span data-ttu-id="d7355-112">De inhoud van de werkelijke berichten verschilt op basis van de factoren die de reactie hebben veroorzaakt.</span><span class="sxs-lookup"><span data-stu-id="d7355-112">The content of actual messages will vary based on the factors that triggered the response.</span></span> <span data-ttu-id="d7355-113">Variabele inhoud wordt in de tabel aangegeven met hoekhaken.</span><span class="sxs-lookup"><span data-stu-id="d7355-113">Variable content is indicated in the table by angle brackets.</span></span>

## <a name="error-codes"></a><span data-ttu-id="d7355-114">Foutcodes</span><span class="sxs-lookup"><span data-stu-id="d7355-114">Error codes</span></span>

<span data-ttu-id="d7355-115">Foutcode</span><span class="sxs-lookup"><span data-stu-id="d7355-115">Error code</span></span> | <span data-ttu-id="d7355-116">HTTP-statuscode</span><span class="sxs-lookup"><span data-stu-id="d7355-116">HTTP status code</span></span> | <span data-ttu-id="d7355-117">Bericht</span><span class="sxs-lookup"><span data-stu-id="d7355-117">Message</span></span>
-|-|-
<span data-ttu-id="d7355-118">BadRequest</span><span class="sxs-lookup"><span data-stu-id="d7355-118">BadRequest</span></span> | <span data-ttu-id="d7355-119">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="d7355-119">BadRequest (400)</span></span> | <span data-ttu-id="d7355-120">Foutbericht algemeen slecht verzoek.</span><span class="sxs-lookup"><span data-stu-id="d7355-120">General Bad Request error message.</span></span>
<span data-ttu-id="d7355-121">ODataError</span><span class="sxs-lookup"><span data-stu-id="d7355-121">ODataError</span></span> | <span data-ttu-id="d7355-122">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="d7355-122">BadRequest (400)</span></span> | <span data-ttu-id="d7355-123">Ongeldige OData URI-query \<the specific error is specified\> .</span><span class="sxs-lookup"><span data-stu-id="d7355-123">Invalid OData URI query \<the specific error is specified\>.</span></span>
<span data-ttu-id="d7355-124">InvalidInput</span><span class="sxs-lookup"><span data-stu-id="d7355-124">InvalidInput</span></span> | <span data-ttu-id="d7355-125">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="d7355-125">BadRequest (400)</span></span> | <span data-ttu-id="d7355-126">Ongeldige invoer \<the invalid input\> .</span><span class="sxs-lookup"><span data-stu-id="d7355-126">Invalid input \<the invalid input\>.</span></span>
<span data-ttu-id="d7355-127">InvalidRequestBody</span><span class="sxs-lookup"><span data-stu-id="d7355-127">InvalidRequestBody</span></span> | <span data-ttu-id="d7355-128">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="d7355-128">BadRequest (400)</span></span> | <span data-ttu-id="d7355-129">Ongeldige aanvraag body.</span><span class="sxs-lookup"><span data-stu-id="d7355-129">Invalid request body.</span></span>
<span data-ttu-id="d7355-130">OngeldigeHashValue</span><span class="sxs-lookup"><span data-stu-id="d7355-130">InvalidHashValue</span></span> | <span data-ttu-id="d7355-131">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="d7355-131">BadRequest (400)</span></span> | <span data-ttu-id="d7355-132">De \<the invalid hash\> hashwaarde is ongeldig.</span><span class="sxs-lookup"><span data-stu-id="d7355-132">Hash value \<the invalid hash\> is invalid.</span></span>
<span data-ttu-id="d7355-133">InvalidDomainName</span><span class="sxs-lookup"><span data-stu-id="d7355-133">InvalidDomainName</span></span> | <span data-ttu-id="d7355-134">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="d7355-134">BadRequest (400)</span></span> | <span data-ttu-id="d7355-135">Domeinnaam \<the invalid domain\> is ongeldig.</span><span class="sxs-lookup"><span data-stu-id="d7355-135">Domain name \<the invalid domain\> is invalid.</span></span>
<span data-ttu-id="d7355-136">InvalidIpAddress</span><span class="sxs-lookup"><span data-stu-id="d7355-136">InvalidIpAddress</span></span> | <span data-ttu-id="d7355-137">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="d7355-137">BadRequest (400)</span></span> | <span data-ttu-id="d7355-138">IP-adres \<the invalid IP\> is ongeldig.</span><span class="sxs-lookup"><span data-stu-id="d7355-138">IP address \<the invalid IP\> is invalid.</span></span>
<span data-ttu-id="d7355-139">InvalidUrl</span><span class="sxs-lookup"><span data-stu-id="d7355-139">InvalidUrl</span></span> | <span data-ttu-id="d7355-140">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="d7355-140">BadRequest (400)</span></span> | <span data-ttu-id="d7355-141">URL \<the invalid URL\> is ongeldig.</span><span class="sxs-lookup"><span data-stu-id="d7355-141">URL \<the invalid URL\> is invalid.</span></span>
<span data-ttu-id="d7355-142">MaximumBatchSizeExceeded</span><span class="sxs-lookup"><span data-stu-id="d7355-142">MaximumBatchSizeExceeded</span></span> | <span data-ttu-id="d7355-143">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="d7355-143">BadRequest (400)</span></span> | <span data-ttu-id="d7355-144">De maximale batchgrootte is overschreden.</span><span class="sxs-lookup"><span data-stu-id="d7355-144">Maximum batch size exceeded.</span></span> <span data-ttu-id="d7355-145">Ontvangen: \<batch size received\> , toegestaan: {batch size allowed}.</span><span class="sxs-lookup"><span data-stu-id="d7355-145">Received: \<batch size received\>, allowed: {batch size allowed}.</span></span>
<span data-ttu-id="d7355-146">MissingRequiredParameter</span><span class="sxs-lookup"><span data-stu-id="d7355-146">MissingRequiredParameter</span></span> | <span data-ttu-id="d7355-147">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="d7355-147">BadRequest (400)</span></span> | <span data-ttu-id="d7355-148">Parameter \<the missing parameter\> ontbreekt.</span><span class="sxs-lookup"><span data-stu-id="d7355-148">Parameter \<the missing parameter\> is missing.</span></span>
<span data-ttu-id="d7355-149">OsPlatformNotSupported</span><span class="sxs-lookup"><span data-stu-id="d7355-149">OsPlatformNotSupported</span></span> | <span data-ttu-id="d7355-150">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="d7355-150">BadRequest (400)</span></span> | <span data-ttu-id="d7355-151">Os Platform \<the client OS Platform\> wordt niet ondersteund voor deze actie.</span><span class="sxs-lookup"><span data-stu-id="d7355-151">OS Platform \<the client OS Platform\> is not supported for this action.</span></span>
<span data-ttu-id="d7355-152">ClientVersionNotSupported</span><span class="sxs-lookup"><span data-stu-id="d7355-152">ClientVersionNotSupported</span></span> | <span data-ttu-id="d7355-153">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="d7355-153">BadRequest (400)</span></span> | <span data-ttu-id="d7355-154">\<The requested action\> wordt ondersteund in clientversie \<supported client version\> en hoger.</span><span class="sxs-lookup"><span data-stu-id="d7355-154">\<The requested action\> is supported on client version \<supported client version\> and above.</span></span>
<span data-ttu-id="d7355-155">Onbevoegden</span><span class="sxs-lookup"><span data-stu-id="d7355-155">Unauthorized</span></span> | <span data-ttu-id="d7355-156">Onbevoegden (401)</span><span class="sxs-lookup"><span data-stu-id="d7355-156">Unauthorized (401)</span></span> | <span data-ttu-id="d7355-157">Onbevoegden</span><span class="sxs-lookup"><span data-stu-id="d7355-157">Unauthorized</span></span> <br /><br /><span data-ttu-id="d7355-158">*Opmerking: Meestal veroorzaakt door een ongeldige of verlopen autorisatiekoptekst.*</span><span class="sxs-lookup"><span data-stu-id="d7355-158">*Note: Usually caused by an invalid or expired authorization header.*</span></span>
<span data-ttu-id="d7355-159">Verboden</span><span class="sxs-lookup"><span data-stu-id="d7355-159">Forbidden</span></span> | <span data-ttu-id="d7355-160">Verboden (403)</span><span class="sxs-lookup"><span data-stu-id="d7355-160">Forbidden (403)</span></span> | <span data-ttu-id="d7355-161">Verboden</span><span class="sxs-lookup"><span data-stu-id="d7355-161">Forbidden</span></span> <br /><br /><span data-ttu-id="d7355-162">*Opmerking: Geldig token, maar onvoldoende machtiging voor de actie.*</span><span class="sxs-lookup"><span data-stu-id="d7355-162">*Note: Valid token but insufficient permission for the action*.</span></span>
<span data-ttu-id="d7355-163">DisabledFeature</span><span class="sxs-lookup"><span data-stu-id="d7355-163">DisabledFeature</span></span> | <span data-ttu-id="d7355-164">Verboden (403)</span><span class="sxs-lookup"><span data-stu-id="d7355-164">Forbidden (403)</span></span> | <span data-ttu-id="d7355-165">Tenantfunctie is niet ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="d7355-165">Tenant feature is not enabled.</span></span>
<span data-ttu-id="d7355-166">DisallowedOperation</span><span class="sxs-lookup"><span data-stu-id="d7355-166">DisallowedOperation</span></span> | <span data-ttu-id="d7355-167">Verboden (403)</span><span class="sxs-lookup"><span data-stu-id="d7355-167">Forbidden (403)</span></span> | <span data-ttu-id="d7355-168">\<the disallowed operation and the reason\>.</span><span class="sxs-lookup"><span data-stu-id="d7355-168">\<the disallowed operation and the reason\>.</span></span>
<span data-ttu-id="d7355-169">NotFound</span><span class="sxs-lookup"><span data-stu-id="d7355-169">NotFound</span></span> | <span data-ttu-id="d7355-170">Niet gevonden (404)</span><span class="sxs-lookup"><span data-stu-id="d7355-170">Not Found (404)</span></span> | <span data-ttu-id="d7355-171">Foutbericht Algemeen niet gevonden.</span><span class="sxs-lookup"><span data-stu-id="d7355-171">General Not Found error message.</span></span>
<span data-ttu-id="d7355-172">ResourceNotFound</span><span class="sxs-lookup"><span data-stu-id="d7355-172">ResourceNotFound</span></span> | <span data-ttu-id="d7355-173">Niet gevonden (404)</span><span class="sxs-lookup"><span data-stu-id="d7355-173">Not Found (404)</span></span> | <span data-ttu-id="d7355-174">Resource \<the requested resource\> is niet gevonden.</span><span class="sxs-lookup"><span data-stu-id="d7355-174">Resource \<the requested resource\> was not found.</span></span>
<span data-ttu-id="d7355-175">InternalServerError</span><span class="sxs-lookup"><span data-stu-id="d7355-175">InternalServerError</span></span> | <span data-ttu-id="d7355-176">Interne serverfout (500)</span><span class="sxs-lookup"><span data-stu-id="d7355-176">Internal Server Error (500)</span></span> | <span data-ttu-id="d7355-177">*Opmerking: Geen foutbericht, de bewerking opnieuw uitvoeren of contact opnemen met Microsoft als dit niet wordt opgelost*</span><span class="sxs-lookup"><span data-stu-id="d7355-177">*Note: No error message,  retry the operation or contact Microsoft if it does not get resolved*</span></span>

## <a name="examples"></a><span data-ttu-id="d7355-178">Voorbeelden</span><span class="sxs-lookup"><span data-stu-id="d7355-178">Examples</span></span>

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

## <a name="body-parameters"></a><span data-ttu-id="d7355-179">Parameters van de body</span><span class="sxs-lookup"><span data-stu-id="d7355-179">Body parameters</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d7355-180">Bodyparameters zijn case-sensitive.</span><span class="sxs-lookup"><span data-stu-id="d7355-180">Body parameters are case-sensitive.</span></span>

<span data-ttu-id="d7355-181">Als er een fout is opgetreden bij *InvalidRequestBody* of *MissingRequiredParameter,* kan dit worden veroorzaakt door een typefout.</span><span class="sxs-lookup"><span data-stu-id="d7355-181">If you experience an *InvalidRequestBody* or *MissingRequiredParameter* error, it might be caused by a typo.</span></span> <span data-ttu-id="d7355-182">Controleer de API-documentatie en controleer of de ingediende parameters overeenkomen met het relevante voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="d7355-182">Review the API documentation and check that the submitted parameters match the relevant example.</span></span>

## <a name="tracking-id"></a><span data-ttu-id="d7355-183">Tracking-id</span><span class="sxs-lookup"><span data-stu-id="d7355-183">Tracking ID</span></span>

<span data-ttu-id="d7355-184">Elke foutreactie bevat een unieke id-parameter voor het bijhouden.</span><span class="sxs-lookup"><span data-stu-id="d7355-184">Each error response contains a unique ID parameter for tracking.</span></span> <span data-ttu-id="d7355-185">De eigenschapsnaam van deze parameter is *doel*.</span><span class="sxs-lookup"><span data-stu-id="d7355-185">The property name of this parameter is *target*.</span></span> <span data-ttu-id="d7355-186">Wanneer u contact met ons op neemt over een fout, kunnen we met deze id de hoofdoorzaak van het probleem vinden.</span><span class="sxs-lookup"><span data-stu-id="d7355-186">When contacting us about an error, attaching this ID will help us find the root cause of the problem.</span></span>

## <a name="related-articles"></a><span data-ttu-id="d7355-187">Aanverwante artikelen</span><span class="sxs-lookup"><span data-stu-id="d7355-187">Related articles</span></span>

- [<span data-ttu-id="d7355-188">Microsoft 365 Overzicht van DEFENDER-API's</span><span class="sxs-lookup"><span data-stu-id="d7355-188">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="d7355-189">Ondersteunde Microsoft 365 Defender-API's</span><span class="sxs-lookup"><span data-stu-id="d7355-189">Supported Microsoft 365 Defender APIs</span></span>](api-supported.md)
- [<span data-ttu-id="d7355-190">Toegang tot Microsoft 365 Defender-API's</span><span class="sxs-lookup"><span data-stu-id="d7355-190">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="d7355-191">Meer informatie over API-limieten en -licenties</span><span class="sxs-lookup"><span data-stu-id="d7355-191">Learn about API limits and licensing</span></span>](api-terms.md)
