---
title: Bekende foutcodes Microsoft Threat Protection REST API
description: Meer informatie over de veelvoorkomende foutcodes voor Microsoft Threat Protection REST API
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
ms.openlocfilehash: 36a1cedacc5f16c422e2b0d458b0d1767cf08b64
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650251"
---
# <a name="common-microsoft-threat-protection-rest-api-error-codes"></a><span data-ttu-id="2ff0d-104">Bekende foutcodes Microsoft Threat Protection REST API</span><span class="sxs-lookup"><span data-stu-id="2ff0d-104">Common Microsoft Threat Protection REST API error codes</span></span>

<span data-ttu-id="2ff0d-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="2ff0d-105">**Applies to:**</span></span>
- <span data-ttu-id="2ff0d-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="2ff0d-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="2ff0d-107">Sommige informatie verhoudt zich tot een voorvrijgegeven product dat bij de commerciële versie van de commerciële versie mogelijk ingrijpend werd gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="2ff0d-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="2ff0d-108">Microsoft biedt geen garanties, expliciete of impliciete informatie met betrekking tot de informatie die u hier opgeeft.</span><span class="sxs-lookup"><span data-stu-id="2ff0d-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="2ff0d-109">De foutcodes in de volgende tabel kunnen als resultaat worden gegeven door een bewerking bij een van de Microsoft Threat Protection-Api's.</span><span class="sxs-lookup"><span data-stu-id="2ff0d-109">The error codes listed in the following table may be returned by an operation on any of Microsoft Threat Protection APIs.</span></span>

<span data-ttu-id="2ff0d-110">Elk foutbericht bevat een foutbericht dat kan worden opgelost om het probleem te verhelpen.</span><span class="sxs-lookup"><span data-stu-id="2ff0d-110">Every error response contains an error message, which can help resolving the problem.</span></span>

<span data-ttu-id="2ff0d-111">Het bericht is een vrije tekst die kan worden gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="2ff0d-111">The message is a free text that can be changed.</span></span>

<span data-ttu-id="2ff0d-112">Onder aan de pagina vindt u antwoord voorbeelden.</span><span class="sxs-lookup"><span data-stu-id="2ff0d-112">At the bottom of the page, you can find response examples.</span></span>

<span data-ttu-id="2ff0d-113">Foutcode</span><span class="sxs-lookup"><span data-stu-id="2ff0d-113">Error code</span></span> |<span data-ttu-id="2ff0d-114">HTTP-statuscode</span><span class="sxs-lookup"><span data-stu-id="2ff0d-114">HTTP status code</span></span> |<span data-ttu-id="2ff0d-115">Bericht</span><span class="sxs-lookup"><span data-stu-id="2ff0d-115">Message</span></span> 
:---|:---|:---
<span data-ttu-id="2ff0d-116">BadRequest</span><span class="sxs-lookup"><span data-stu-id="2ff0d-116">BadRequest</span></span> | <span data-ttu-id="2ff0d-117">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="2ff0d-117">BadRequest (400)</span></span> | <span data-ttu-id="2ff0d-118">Foutbericht over algemene onjuiste aanvraag.</span><span class="sxs-lookup"><span data-stu-id="2ff0d-118">General Bad Request error message.</span></span>
<span data-ttu-id="2ff0d-119">ODataError</span><span class="sxs-lookup"><span data-stu-id="2ff0d-119">ODataError</span></span> | <span data-ttu-id="2ff0d-120">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="2ff0d-120">BadRequest (400)</span></span> | <span data-ttu-id="2ff0d-121">Ongeldige OData URI-query (de specifieke fout is opgegeven).</span><span class="sxs-lookup"><span data-stu-id="2ff0d-121">Invalid OData URI query (the specific error is specified).</span></span>
<span data-ttu-id="2ff0d-122">InvalidInput</span><span class="sxs-lookup"><span data-stu-id="2ff0d-122">InvalidInput</span></span> | <span data-ttu-id="2ff0d-123">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="2ff0d-123">BadRequest (400)</span></span> | <span data-ttu-id="2ff0d-124">Ongeldige invoer {de ongeldige invoer}.</span><span class="sxs-lookup"><span data-stu-id="2ff0d-124">Invalid input {the invalid input}.</span></span>
<span data-ttu-id="2ff0d-125">InvalidRequestBody</span><span class="sxs-lookup"><span data-stu-id="2ff0d-125">InvalidRequestBody</span></span> | <span data-ttu-id="2ff0d-126">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="2ff0d-126">BadRequest (400)</span></span> | <span data-ttu-id="2ff0d-127">Ongeldige hoofdtekst van aanvraag.</span><span class="sxs-lookup"><span data-stu-id="2ff0d-127">Invalid request body.</span></span>
<span data-ttu-id="2ff0d-128">InvalidHashValue</span><span class="sxs-lookup"><span data-stu-id="2ff0d-128">InvalidHashValue</span></span> | <span data-ttu-id="2ff0d-129">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="2ff0d-129">BadRequest (400)</span></span> | <span data-ttu-id="2ff0d-130">Hashwaarde {de ongeldige hash} is ongeldig.</span><span class="sxs-lookup"><span data-stu-id="2ff0d-130">Hash value {the invalid hash} is invalid.</span></span>
<span data-ttu-id="2ff0d-131">InvalidDomainName</span><span class="sxs-lookup"><span data-stu-id="2ff0d-131">InvalidDomainName</span></span> | <span data-ttu-id="2ff0d-132">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="2ff0d-132">BadRequest (400)</span></span> | <span data-ttu-id="2ff0d-133">Domeinnaam {ongeldig domein} is ongeldig.</span><span class="sxs-lookup"><span data-stu-id="2ff0d-133">Domain name {the invalid domain} is invalid.</span></span>
<span data-ttu-id="2ff0d-134">InvalidIpAddress</span><span class="sxs-lookup"><span data-stu-id="2ff0d-134">InvalidIpAddress</span></span> | <span data-ttu-id="2ff0d-135">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="2ff0d-135">BadRequest (400)</span></span> | <span data-ttu-id="2ff0d-136">IP-adres {ongeldig IP-adres}.</span><span class="sxs-lookup"><span data-stu-id="2ff0d-136">IP address {the invalid IP} is invalid.</span></span>
<span data-ttu-id="2ff0d-137">InvalidUrl</span><span class="sxs-lookup"><span data-stu-id="2ff0d-137">InvalidUrl</span></span> | <span data-ttu-id="2ff0d-138">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="2ff0d-138">BadRequest (400)</span></span> | <span data-ttu-id="2ff0d-139">URL {de ongeldige URL} is ongeldig.</span><span class="sxs-lookup"><span data-stu-id="2ff0d-139">URL {the invalid URL} is invalid.</span></span>
<span data-ttu-id="2ff0d-140">MaximumBatchSizeExceeded</span><span class="sxs-lookup"><span data-stu-id="2ff0d-140">MaximumBatchSizeExceeded</span></span> | <span data-ttu-id="2ff0d-141">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="2ff0d-141">BadRequest (400)</span></span> | <span data-ttu-id="2ff0d-142">Maximale grootte van de batch overschreden.</span><span class="sxs-lookup"><span data-stu-id="2ff0d-142">Maximum batch size exceeded.</span></span> <span data-ttu-id="2ff0d-143">Ontvangen: {batchgrootte ontvangen}, toegestaan: {batchgrootte toegestaan}.</span><span class="sxs-lookup"><span data-stu-id="2ff0d-143">Received: {batch size received}, allowed: {batch size allowed}.</span></span>
<span data-ttu-id="2ff0d-144">MissingRequiredParameter</span><span class="sxs-lookup"><span data-stu-id="2ff0d-144">MissingRequiredParameter</span></span> | <span data-ttu-id="2ff0d-145">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="2ff0d-145">BadRequest (400)</span></span> | <span data-ttu-id="2ff0d-146">Parameter {de ontbrekende parameter} ontbreekt.</span><span class="sxs-lookup"><span data-stu-id="2ff0d-146">Parameter {the missing parameter} is missing.</span></span>
<span data-ttu-id="2ff0d-147">OsPlatformNotSupported</span><span class="sxs-lookup"><span data-stu-id="2ff0d-147">OsPlatformNotSupported</span></span> | <span data-ttu-id="2ff0d-148">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="2ff0d-148">BadRequest (400)</span></span> | <span data-ttu-id="2ff0d-149">OS platform {het clientbesturingssysteem platform} wordt niet ondersteund voor deze actie.</span><span class="sxs-lookup"><span data-stu-id="2ff0d-149">OS Platform {the client OS Platform} is not supported for this action.</span></span>
<span data-ttu-id="2ff0d-150">ClientVersionNotSupported</span><span class="sxs-lookup"><span data-stu-id="2ff0d-150">ClientVersionNotSupported</span></span> | <span data-ttu-id="2ff0d-151">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="2ff0d-151">BadRequest (400)</span></span> | <span data-ttu-id="2ff0d-152">{De gevraagde actie} wordt ondersteund op de clientversie {ondersteunde clientversie} en hoger.</span><span class="sxs-lookup"><span data-stu-id="2ff0d-152">{The requested action} is supported on client version {supported client version} and above.</span></span>
<span data-ttu-id="2ff0d-153">Onbevoegde</span><span class="sxs-lookup"><span data-stu-id="2ff0d-153">Unauthorized</span></span> | <span data-ttu-id="2ff0d-154">Onbevoegd (401)</span><span class="sxs-lookup"><span data-stu-id="2ff0d-154">Unauthorized (401)</span></span> | <span data-ttu-id="2ff0d-155">Niet toegestaan (meestal ongeldig of vervallen autorisatie-header).</span><span class="sxs-lookup"><span data-stu-id="2ff0d-155">Unauthorized (usually invalid or expired authorization header).</span></span>
<span data-ttu-id="2ff0d-156">Slag</span><span class="sxs-lookup"><span data-stu-id="2ff0d-156">Forbidden</span></span> | <span data-ttu-id="2ff0d-157">Niet toegestaan (403)</span><span class="sxs-lookup"><span data-stu-id="2ff0d-157">Forbidden (403)</span></span> | <span data-ttu-id="2ff0d-158">Niet toegestaan (geldig token maar onvoldoende machtigingen voor de actie).</span><span class="sxs-lookup"><span data-stu-id="2ff0d-158">Forbidden (valid token but insufficient permission for the action).</span></span>
<span data-ttu-id="2ff0d-159">DisabledFeature</span><span class="sxs-lookup"><span data-stu-id="2ff0d-159">DisabledFeature</span></span> | <span data-ttu-id="2ff0d-160">Niet toegestaan (403)</span><span class="sxs-lookup"><span data-stu-id="2ff0d-160">Forbidden (403)</span></span> | <span data-ttu-id="2ff0d-161">De Tenant functie is niet ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="2ff0d-161">Tenant feature is not enabled.</span></span>
<span data-ttu-id="2ff0d-162">DisallowedOperation</span><span class="sxs-lookup"><span data-stu-id="2ff0d-162">DisallowedOperation</span></span> | <span data-ttu-id="2ff0d-163">Niet toegestaan (403)</span><span class="sxs-lookup"><span data-stu-id="2ff0d-163">Forbidden (403)</span></span> | <span data-ttu-id="2ff0d-164">{de niet-toegestane bewerking en de reden}.</span><span class="sxs-lookup"><span data-stu-id="2ff0d-164">{the disallowed operation and the reason}.</span></span>
<span data-ttu-id="2ff0d-165">NotFound</span><span class="sxs-lookup"><span data-stu-id="2ff0d-165">NotFound</span></span> | <span data-ttu-id="2ff0d-166">Niet gevonden (404)</span><span class="sxs-lookup"><span data-stu-id="2ff0d-166">Not Found (404)</span></span> | <span data-ttu-id="2ff0d-167">Foutbericht algemeen niet gevonden.</span><span class="sxs-lookup"><span data-stu-id="2ff0d-167">General Not Found error message.</span></span>
<span data-ttu-id="2ff0d-168">ResourceNotFound</span><span class="sxs-lookup"><span data-stu-id="2ff0d-168">ResourceNotFound</span></span> | <span data-ttu-id="2ff0d-169">Niet gevonden (404)</span><span class="sxs-lookup"><span data-stu-id="2ff0d-169">Not Found (404)</span></span> | <span data-ttu-id="2ff0d-170">Resource {de gevraagde resource} is niet gevonden.</span><span class="sxs-lookup"><span data-stu-id="2ff0d-170">Resource {the requested resource} was not found.</span></span>
<span data-ttu-id="2ff0d-171">InternalServerError</span><span class="sxs-lookup"><span data-stu-id="2ff0d-171">InternalServerError</span></span> | <span data-ttu-id="2ff0d-172">Interne server fout (500)</span><span class="sxs-lookup"><span data-stu-id="2ff0d-172">Internal Server Error (500)</span></span> | <span data-ttu-id="2ff0d-173">(Geen foutbericht, probeer het opnieuw of neem contact met ons op als dit niet wordt opgelost)</span><span class="sxs-lookup"><span data-stu-id="2ff0d-173">(No error message,  retry the operation or contact us if it does not get resolved)</span></span>

## <a name="body-parameters-are-case-sensitive"></a><span data-ttu-id="2ff0d-174">Hoofd parameters zijn hoofdletters en kleine letters</span><span class="sxs-lookup"><span data-stu-id="2ff0d-174">Body parameters are case-sensitive</span></span>

<span data-ttu-id="2ff0d-175">De ingediende parameters voor de hoofdtekst zijn momenteel hoofdlettergevoelig.</span><span class="sxs-lookup"><span data-stu-id="2ff0d-175">The submitted body parameters are currently case-sensitive.</span></span>
<br><span data-ttu-id="2ff0d-176">Als u een **InvalidRequestBody** -of **MissingRequiredParameter** -fout ondervindt, wordt dit mogelijk veroorzaakt door een onjuist parameter kapitaal of een kleine letter.</span><span class="sxs-lookup"><span data-stu-id="2ff0d-176">If you experience an **InvalidRequestBody** or **MissingRequiredParameter** errors, it might be caused from a wrong parameter capital or lower-case letter.</span></span>
<br><span data-ttu-id="2ff0d-177">We raden u aan de API-documentatie pagina te bekijken en te controleren of de verzonden parameters overeenkomen met het relevante voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="2ff0d-177">We recommend that you review the API documentation page and check that the submitted parameters match the relevant example.</span></span>

## <a name="correlation-request-id"></a><span data-ttu-id="2ff0d-178">ID van correlatie aanvraag</span><span class="sxs-lookup"><span data-stu-id="2ff0d-178">Correlation request ID</span></span>

<span data-ttu-id="2ff0d-179">Elke foutmelding bevat een unieke ID-parameter voor bijhouden.</span><span class="sxs-lookup"><span data-stu-id="2ff0d-179">Each error response contains a unique ID parameter for tracking.</span></span>
<br><span data-ttu-id="2ff0d-180">De naam van de eigenschap van deze parameter is ' doel '.</span><span class="sxs-lookup"><span data-stu-id="2ff0d-180">The property name of this parameter is "target".</span></span>
<br><span data-ttu-id="2ff0d-181">Als u over een fout contact met ons opneemt, kunt u met deze ID de hoofdoorzaak van het probleem achterhalen.</span><span class="sxs-lookup"><span data-stu-id="2ff0d-181">When contacting us about an error, attaching this ID will help find the root cause of the problem.</span></span>

## <a name="examples"></a><span data-ttu-id="2ff0d-182">Voorbeelden</span><span class="sxs-lookup"><span data-stu-id="2ff0d-182">Examples</span></span>

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

