---
title: Veelvoorkomende fouten in microsoft Defender voor endpoint-API
description: Lijst met veelvoorkomende Microsoft Defender voor Endpoint API-fouten met beschrijvingen.
keywords: api's, mdatp-api, fouten, probleemoplossing
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
ms.openlocfilehash: 4fc2aeb6ee5a95f7eb121abdcf4431dc6d34cd49
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893459"
---
# <a name="common-rest-api-error-codes"></a><span data-ttu-id="dc3fa-104">Algemene REST API-foutcodes</span><span class="sxs-lookup"><span data-stu-id="dc3fa-104">Common REST API error codes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


* <span data-ttu-id="dc3fa-105">De foutcodes die in de volgende tabel worden vermeld, kunnen worden geretourneerd door een bewerking op een van de API's van Microsoft Defender voor eindpunten.</span><span class="sxs-lookup"><span data-stu-id="dc3fa-105">The error codes listed in the following table may be returned by an operation on any of Microsoft Defender for Endpoint APIs.</span></span>
* <span data-ttu-id="dc3fa-106">Naast de foutcode bevat elk foutbericht een foutbericht, waarmee het probleem kan worden opgelost.</span><span class="sxs-lookup"><span data-stu-id="dc3fa-106">In addition to the error code, every error response contains an error message, which can help resolve the problem.</span></span>
* <span data-ttu-id="dc3fa-107">Het bericht is een gratis tekst die kan worden gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="dc3fa-107">The message is a free text that can be changed.</span></span>
* <span data-ttu-id="dc3fa-108">Onder aan de pagina vindt u antwoordvoorbeelden.</span><span class="sxs-lookup"><span data-stu-id="dc3fa-108">At the bottom of the page, you can find response examples.</span></span>

><span data-ttu-id="dc3fa-109">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="dc3fa-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="dc3fa-110">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="dc3fa-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="dc3fa-111">Foutcode</span><span class="sxs-lookup"><span data-stu-id="dc3fa-111">Error code</span></span> |<span data-ttu-id="dc3fa-112">HTTP-statuscode</span><span class="sxs-lookup"><span data-stu-id="dc3fa-112">HTTP status code</span></span> |<span data-ttu-id="dc3fa-113">Bericht</span><span class="sxs-lookup"><span data-stu-id="dc3fa-113">Message</span></span> 
:---|:---|:---
<span data-ttu-id="dc3fa-114">BadRequest</span><span class="sxs-lookup"><span data-stu-id="dc3fa-114">BadRequest</span></span> | <span data-ttu-id="dc3fa-115">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="dc3fa-115">BadRequest (400)</span></span> | <span data-ttu-id="dc3fa-116">Foutbericht algemeen slecht verzoek.</span><span class="sxs-lookup"><span data-stu-id="dc3fa-116">General Bad Request error message.</span></span>
<span data-ttu-id="dc3fa-117">ODataError</span><span class="sxs-lookup"><span data-stu-id="dc3fa-117">ODataError</span></span> | <span data-ttu-id="dc3fa-118">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="dc3fa-118">BadRequest (400)</span></span> | <span data-ttu-id="dc3fa-119">Ongeldige OData URI-query (de specifieke fout is opgegeven).</span><span class="sxs-lookup"><span data-stu-id="dc3fa-119">Invalid OData URI query (the specific error is specified).</span></span>
<span data-ttu-id="dc3fa-120">InvalidInput</span><span class="sxs-lookup"><span data-stu-id="dc3fa-120">InvalidInput</span></span> | <span data-ttu-id="dc3fa-121">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="dc3fa-121">BadRequest (400)</span></span> | <span data-ttu-id="dc3fa-122">Ongeldige invoer {de ongeldige invoer}.</span><span class="sxs-lookup"><span data-stu-id="dc3fa-122">Invalid input {the invalid input}.</span></span>
<span data-ttu-id="dc3fa-123">InvalidRequestBody</span><span class="sxs-lookup"><span data-stu-id="dc3fa-123">InvalidRequestBody</span></span> | <span data-ttu-id="dc3fa-124">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="dc3fa-124">BadRequest (400)</span></span> | <span data-ttu-id="dc3fa-125">Ongeldige aanvraag body.</span><span class="sxs-lookup"><span data-stu-id="dc3fa-125">Invalid request body.</span></span>
<span data-ttu-id="dc3fa-126">OngeldigeHashValue</span><span class="sxs-lookup"><span data-stu-id="dc3fa-126">InvalidHashValue</span></span> | <span data-ttu-id="dc3fa-127">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="dc3fa-127">BadRequest (400)</span></span> | <span data-ttu-id="dc3fa-128">Hashwaarde {de ongeldige hash} is ongeldig.</span><span class="sxs-lookup"><span data-stu-id="dc3fa-128">Hash value {the invalid hash} is invalid.</span></span>
<span data-ttu-id="dc3fa-129">InvalidDomainName</span><span class="sxs-lookup"><span data-stu-id="dc3fa-129">InvalidDomainName</span></span> | <span data-ttu-id="dc3fa-130">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="dc3fa-130">BadRequest (400)</span></span> | <span data-ttu-id="dc3fa-131">Domeinnaam {het ongeldige domein} is ongeldig.</span><span class="sxs-lookup"><span data-stu-id="dc3fa-131">Domain name {the invalid domain} is invalid.</span></span>
<span data-ttu-id="dc3fa-132">InvalidIpAddress</span><span class="sxs-lookup"><span data-stu-id="dc3fa-132">InvalidIpAddress</span></span> | <span data-ttu-id="dc3fa-133">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="dc3fa-133">BadRequest (400)</span></span> | <span data-ttu-id="dc3fa-134">IP-adres {het ongeldige IP} is ongeldig.</span><span class="sxs-lookup"><span data-stu-id="dc3fa-134">IP address {the invalid IP} is invalid.</span></span>
<span data-ttu-id="dc3fa-135">InvalidUrl</span><span class="sxs-lookup"><span data-stu-id="dc3fa-135">InvalidUrl</span></span> | <span data-ttu-id="dc3fa-136">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="dc3fa-136">BadRequest (400)</span></span> | <span data-ttu-id="dc3fa-137">URL {de ongeldige URL} is ongeldig.</span><span class="sxs-lookup"><span data-stu-id="dc3fa-137">URL {the invalid URL} is invalid.</span></span>
<span data-ttu-id="dc3fa-138">MaximumBatchSizeExceeded</span><span class="sxs-lookup"><span data-stu-id="dc3fa-138">MaximumBatchSizeExceeded</span></span> | <span data-ttu-id="dc3fa-139">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="dc3fa-139">BadRequest (400)</span></span> | <span data-ttu-id="dc3fa-140">De maximale batchgrootte is overschreden.</span><span class="sxs-lookup"><span data-stu-id="dc3fa-140">Maximum batch size exceeded.</span></span> <span data-ttu-id="dc3fa-141">Ontvangen: {batch size received}, allowed: {batch size allowed}.</span><span class="sxs-lookup"><span data-stu-id="dc3fa-141">Received: {batch size received}, allowed: {batch size allowed}.</span></span>
<span data-ttu-id="dc3fa-142">MissingRequiredParameter</span><span class="sxs-lookup"><span data-stu-id="dc3fa-142">MissingRequiredParameter</span></span> | <span data-ttu-id="dc3fa-143">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="dc3fa-143">BadRequest (400)</span></span> | <span data-ttu-id="dc3fa-144">Parameter {de ontbrekende parameter} ontbreekt.</span><span class="sxs-lookup"><span data-stu-id="dc3fa-144">Parameter {the missing parameter} is missing.</span></span>
<span data-ttu-id="dc3fa-145">OsPlatformNotSupported</span><span class="sxs-lookup"><span data-stu-id="dc3fa-145">OsPlatformNotSupported</span></span> | <span data-ttu-id="dc3fa-146">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="dc3fa-146">BadRequest (400)</span></span> | <span data-ttu-id="dc3fa-147">Os Platform {the client OS Platform} wordt niet ondersteund voor deze actie.</span><span class="sxs-lookup"><span data-stu-id="dc3fa-147">OS Platform {the client OS Platform} is not supported for this action.</span></span>
<span data-ttu-id="dc3fa-148">ClientVersionNotSupported</span><span class="sxs-lookup"><span data-stu-id="dc3fa-148">ClientVersionNotSupported</span></span> | <span data-ttu-id="dc3fa-149">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="dc3fa-149">BadRequest (400)</span></span> | <span data-ttu-id="dc3fa-150">{De aangevraagde actie} wordt ondersteund in clientversie {ondersteunde clientversie} en hoger.</span><span class="sxs-lookup"><span data-stu-id="dc3fa-150">{The requested action} is supported on client version {supported client version} and above.</span></span>
<span data-ttu-id="dc3fa-151">Onbevoegden</span><span class="sxs-lookup"><span data-stu-id="dc3fa-151">Unauthorized</span></span> | <span data-ttu-id="dc3fa-152">Onbevoegden (401)</span><span class="sxs-lookup"><span data-stu-id="dc3fa-152">Unauthorized (401)</span></span> | <span data-ttu-id="dc3fa-153">Onbevoegden (ongeldige of verlopen autorisatiekoptekst).</span><span class="sxs-lookup"><span data-stu-id="dc3fa-153">Unauthorized (invalid or expired authorization header).</span></span>
<span data-ttu-id="dc3fa-154">Verboden</span><span class="sxs-lookup"><span data-stu-id="dc3fa-154">Forbidden</span></span> | <span data-ttu-id="dc3fa-155">Verboden (403)</span><span class="sxs-lookup"><span data-stu-id="dc3fa-155">Forbidden (403)</span></span> | <span data-ttu-id="dc3fa-156">Verboden (geldig token, maar onvoldoende toestemming voor de actie).</span><span class="sxs-lookup"><span data-stu-id="dc3fa-156">Forbidden (valid token but insufficient permission for the action).</span></span>
<span data-ttu-id="dc3fa-157">DisabledFeature</span><span class="sxs-lookup"><span data-stu-id="dc3fa-157">DisabledFeature</span></span> | <span data-ttu-id="dc3fa-158">Verboden (403)</span><span class="sxs-lookup"><span data-stu-id="dc3fa-158">Forbidden (403)</span></span> | <span data-ttu-id="dc3fa-159">Tenantfunctie is niet ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="dc3fa-159">Tenant feature is not enabled.</span></span>
<span data-ttu-id="dc3fa-160">DisallowedOperation</span><span class="sxs-lookup"><span data-stu-id="dc3fa-160">DisallowedOperation</span></span> | <span data-ttu-id="dc3fa-161">Verboden (403)</span><span class="sxs-lookup"><span data-stu-id="dc3fa-161">Forbidden (403)</span></span> | <span data-ttu-id="dc3fa-162">{de niet-goedgekeurde bewerking en de reden}.</span><span class="sxs-lookup"><span data-stu-id="dc3fa-162">{the disallowed operation and the reason}.</span></span>
<span data-ttu-id="dc3fa-163">NotFound</span><span class="sxs-lookup"><span data-stu-id="dc3fa-163">NotFound</span></span> | <span data-ttu-id="dc3fa-164">Niet gevonden (404)</span><span class="sxs-lookup"><span data-stu-id="dc3fa-164">Not Found (404)</span></span> | <span data-ttu-id="dc3fa-165">Foutbericht Algemeen niet gevonden.</span><span class="sxs-lookup"><span data-stu-id="dc3fa-165">General Not Found error message.</span></span>
<span data-ttu-id="dc3fa-166">ResourceNotFound</span><span class="sxs-lookup"><span data-stu-id="dc3fa-166">ResourceNotFound</span></span> | <span data-ttu-id="dc3fa-167">Niet gevonden (404)</span><span class="sxs-lookup"><span data-stu-id="dc3fa-167">Not Found (404)</span></span> | <span data-ttu-id="dc3fa-168">Resource {de aangevraagde resource} is niet gevonden.</span><span class="sxs-lookup"><span data-stu-id="dc3fa-168">Resource {the requested resource} was not found.</span></span>
<span data-ttu-id="dc3fa-169">InternalServerError</span><span class="sxs-lookup"><span data-stu-id="dc3fa-169">InternalServerError</span></span> | <span data-ttu-id="dc3fa-170">Interne serverfout (500)</span><span class="sxs-lookup"><span data-stu-id="dc3fa-170">Internal Server Error (500)</span></span> | <span data-ttu-id="dc3fa-171">(Geen foutbericht, de bewerking opnieuw proberen)</span><span class="sxs-lookup"><span data-stu-id="dc3fa-171">(No error message, retry the operation)</span></span>
<span data-ttu-id="dc3fa-172">TooManyRequests</span><span class="sxs-lookup"><span data-stu-id="dc3fa-172">TooManyRequests</span></span> | <span data-ttu-id="dc3fa-173">Te veel aanvragen (429)</span><span class="sxs-lookup"><span data-stu-id="dc3fa-173">Too Many Requests (429)</span></span> | <span data-ttu-id="dc3fa-174">Antwoord vertegenwoordigt het bereiken van quotumlimiet per aantal aanvragen of per CPU.</span><span class="sxs-lookup"><span data-stu-id="dc3fa-174">Response will represent reaching quota limit either by number of requests or by CPU.</span></span>

## <a name="body-parameters-are-case-sensitive"></a><span data-ttu-id="dc3fa-175">Bodyparameters zijn case-sensitive</span><span class="sxs-lookup"><span data-stu-id="dc3fa-175">Body parameters are case-sensitive</span></span>

<span data-ttu-id="dc3fa-176">De ingediende bodyparameters zijn momenteel case-sensitive.</span><span class="sxs-lookup"><span data-stu-id="dc3fa-176">The submitted body parameters are currently case-sensitive.</span></span>
<br><span data-ttu-id="dc3fa-177">Als er fouten optreden bij **InvalidRequestBody** of **MissingRequiredParameter,** kan dit worden veroorzaakt door een verkeerde parameterhoofdletter of kleine letter.</span><span class="sxs-lookup"><span data-stu-id="dc3fa-177">If you experience an **InvalidRequestBody** or **MissingRequiredParameter** errors, it might be caused from a wrong parameter capital or lower-case letter.</span></span>
<br><span data-ttu-id="dc3fa-178">Controleer de api-documentatiepagina en controleer of de ingediende parameters overeenkomen met het relevante voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="dc3fa-178">Review the API documentation page and check that the submitted parameters match the relevant example.</span></span>

## <a name="correlation-request-id"></a><span data-ttu-id="dc3fa-179">Correlatieaanvraag-id</span><span class="sxs-lookup"><span data-stu-id="dc3fa-179">Correlation request ID</span></span>

<span data-ttu-id="dc3fa-180">Elke foutreactie bevat een unieke id-parameter voor het bijhouden.</span><span class="sxs-lookup"><span data-stu-id="dc3fa-180">Each error response contains a unique ID parameter for tracking.</span></span>
<br><span data-ttu-id="dc3fa-181">De eigenschapsnaam van deze parameter is 'doel'.</span><span class="sxs-lookup"><span data-stu-id="dc3fa-181">The property name of this parameter is "target".</span></span>
<br><span data-ttu-id="dc3fa-182">Wanneer u contact met ons op neemt over een fout, helpt u bij het koppelen van deze id de oorzaak van het probleem te vinden.</span><span class="sxs-lookup"><span data-stu-id="dc3fa-182">When contacting us about an error, attaching this ID will help find the root cause of the problem.</span></span>

## <a name="examples"></a><span data-ttu-id="dc3fa-183">Voorbeelden</span><span class="sxs-lookup"><span data-stu-id="dc3fa-183">Examples</span></span>

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
