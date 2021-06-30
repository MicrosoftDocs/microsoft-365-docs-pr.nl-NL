---
title: BatchDelete
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: reference
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: m365initiative-syntex
localization_priority: Priority
description: Gebruik REST API om een toegepast model met documentbegrip te verwijderen uit een of meer bibliotheken.
ms.openlocfilehash: e95c0583b1b0e2f5de08228afbf161c339544047
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177235"
---
# <a name="batchdelete"></a><span data-ttu-id="eeaa9-103">BatchDelete</span><span class="sxs-lookup"><span data-stu-id="eeaa9-103">BatchDelete</span></span>

<span data-ttu-id="eeaa9-104">Verwijdert een toegepast model met documentbegrip uit een of meer bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="eeaa9-104">Removes an applied document understanding model from one or more libraries.</span></span> <span data-ttu-id="eeaa9-105">Houd er rekening mee dat een model moet worden verwijderd uit alle bibliotheken voordat het kan worden verwijderd (zie [voorbeeld](rest-batchdelete-method.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="eeaa9-105">Note that a model must be removed from all libraries before it can be deleted (see [example](rest-batchdelete-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="eeaa9-106">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="eeaa9-106">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/publications/batchdelete HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="eeaa9-107">URI-parameters</span><span class="sxs-lookup"><span data-stu-id="eeaa9-107">URI parameters</span></span>

<span data-ttu-id="eeaa9-108">Geen</span><span class="sxs-lookup"><span data-stu-id="eeaa9-108">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="eeaa9-109">Aanvraagheaders</span><span class="sxs-lookup"><span data-stu-id="eeaa9-109">Request headers</span></span>

| <span data-ttu-id="eeaa9-110">Header</span><span class="sxs-lookup"><span data-stu-id="eeaa9-110">Header</span></span> | <span data-ttu-id="eeaa9-111">Waarde</span><span class="sxs-lookup"><span data-stu-id="eeaa9-111">Value</span></span> |
|--------|-------|
|<span data-ttu-id="eeaa9-112">Accepteren</span><span class="sxs-lookup"><span data-stu-id="eeaa9-112">Accept</span></span>|<span data-ttu-id="eeaa9-113">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="eeaa9-113">application/json;odata=verbose</span></span>|
|<span data-ttu-id="eeaa9-114">Content-Type</span><span class="sxs-lookup"><span data-stu-id="eeaa9-114">Content-Type</span></span>|<span data-ttu-id="eeaa9-115">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="eeaa9-115">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="eeaa9-116">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="eeaa9-116">x-requestdigest</span></span>|<span data-ttu-id="eeaa9-117">De juiste samenvatting voor deze site.</span><span class="sxs-lookup"><span data-stu-id="eeaa9-117">The appropriate digest for current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="eeaa9-118">Aanvraagtekst</span><span class="sxs-lookup"><span data-stu-id="eeaa9-118">Request body</span></span>

| <span data-ttu-id="eeaa9-119">Naam</span><span class="sxs-lookup"><span data-stu-id="eeaa9-119">Name</span></span> | <span data-ttu-id="eeaa9-120">Vereist</span><span class="sxs-lookup"><span data-stu-id="eeaa9-120">Required</span></span> | <span data-ttu-id="eeaa9-121">Type</span><span class="sxs-lookup"><span data-stu-id="eeaa9-121">Type</span></span> | <span data-ttu-id="eeaa9-122">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="eeaa9-122">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="eeaa9-123">Publicaties</span><span class="sxs-lookup"><span data-stu-id="eeaa9-123">Publications</span></span>|<span data-ttu-id="eeaa9-124">ja</span><span class="sxs-lookup"><span data-stu-id="eeaa9-124">yes</span></span>|<span data-ttu-id="eeaa9-125">MachineLearningPublicationEntityData[]</span><span class="sxs-lookup"><span data-stu-id="eeaa9-125">MachineLearningPublicationEntityData[]</span></span>|<span data-ttu-id="eeaa9-126">De verzameling MachineLearningPublicationEntityData die elk het model en de doeldocumentbibliotheek specificeert.</span><span class="sxs-lookup"><span data-stu-id="eeaa9-126">The collection of MachineLearningPublicationEntityData each of which specifies the model and target document library.</span></span>|

### <a name="machinelearningpublicationentitydata"></a><span data-ttu-id="eeaa9-127">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="eeaa9-127">MachineLearningPublicationEntityData</span></span>
| <span data-ttu-id="eeaa9-128">Naam</span><span class="sxs-lookup"><span data-stu-id="eeaa9-128">Name</span></span> | <span data-ttu-id="eeaa9-129">Vereist</span><span class="sxs-lookup"><span data-stu-id="eeaa9-129">Required</span></span> | <span data-ttu-id="eeaa9-130">Type</span><span class="sxs-lookup"><span data-stu-id="eeaa9-130">Type</span></span> | <span data-ttu-id="eeaa9-131">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="eeaa9-131">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="eeaa9-132">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="eeaa9-132">ModelUniqueId</span></span>|<span data-ttu-id="eeaa9-133">ja</span><span class="sxs-lookup"><span data-stu-id="eeaa9-133">yes</span></span>|<span data-ttu-id="eeaa9-134">reeks</span><span class="sxs-lookup"><span data-stu-id="eeaa9-134">string</span></span>|<span data-ttu-id="eeaa9-135">De unieke id van het modelbestand.</span><span class="sxs-lookup"><span data-stu-id="eeaa9-135">The unique ID of the model file.</span></span>|
|<span data-ttu-id="eeaa9-136">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="eeaa9-136">TargetSiteUrl</span></span>|<span data-ttu-id="eeaa9-137">ja</span><span class="sxs-lookup"><span data-stu-id="eeaa9-137">yes</span></span>|<span data-ttu-id="eeaa9-138">reeks</span><span class="sxs-lookup"><span data-stu-id="eeaa9-138">string</span></span>|<span data-ttu-id="eeaa9-139">De volledige URL van de doelbibliotheeksite.</span><span class="sxs-lookup"><span data-stu-id="eeaa9-139">The full URL of the target library site.</span></span>|
|<span data-ttu-id="eeaa9-140">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="eeaa9-140">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="eeaa9-141">ja</span><span class="sxs-lookup"><span data-stu-id="eeaa9-141">yes</span></span>|<span data-ttu-id="eeaa9-142">reeks</span><span class="sxs-lookup"><span data-stu-id="eeaa9-142">string</span></span>|<span data-ttu-id="eeaa9-143">De relatieve server-URL van het web voor de doelbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="eeaa9-143">The server relative URL of the web for the target library.</span></span>|
|<span data-ttu-id="eeaa9-144">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="eeaa9-144">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="eeaa9-145">ja</span><span class="sxs-lookup"><span data-stu-id="eeaa9-145">yes</span></span>|<span data-ttu-id="eeaa9-146">reeks</span><span class="sxs-lookup"><span data-stu-id="eeaa9-146">string</span></span>|<span data-ttu-id="eeaa9-147">De relatieve server-URL van de doelbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="eeaa9-147">The server relative URL of the target library.</span></span>|

## <a name="response"></a><span data-ttu-id="eeaa9-148">Antwoord</span><span class="sxs-lookup"><span data-stu-id="eeaa9-148">Response</span></span>

| <span data-ttu-id="eeaa9-149">Naam</span><span class="sxs-lookup"><span data-stu-id="eeaa9-149">Name</span></span>   | <span data-ttu-id="eeaa9-150">Type</span><span class="sxs-lookup"><span data-stu-id="eeaa9-150">Type</span></span>  | <span data-ttu-id="eeaa9-151">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="eeaa9-151">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="eeaa9-152">200 OK</span><span class="sxs-lookup"><span data-stu-id="eeaa9-152">200 OK</span></span>||<span data-ttu-id="eeaa9-153">Dit is een aangepaste API ter ondersteuning van het verwijderen van een model uit bibliotheken met meerdere documenten.</span><span class="sxs-lookup"><span data-stu-id="eeaa9-153">This is a customized API to support removing a model from multi document libraries.</span></span> <span data-ttu-id="eeaa9-154">In het geval van gedeeltelijk succes kan 200 OK nog steeds worden geretourneerd en moet de aanroeper de antwoordtekst inspecteren om te begrijpen of het model is verwijderd uit een documentbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="eeaa9-154">In the case of partial success, 200 OK could still be returned and the caller needs to inspect the response body to understand if the model has been successfully removed from a document library.</span></span>|

## <a name="response-body"></a><span data-ttu-id="eeaa9-155">Antwoordtekst</span><span class="sxs-lookup"><span data-stu-id="eeaa9-155">Response Body</span></span>
| <span data-ttu-id="eeaa9-156">Naam</span><span class="sxs-lookup"><span data-stu-id="eeaa9-156">Name</span></span>   | <span data-ttu-id="eeaa9-157">Type</span><span class="sxs-lookup"><span data-stu-id="eeaa9-157">Type</span></span>  | <span data-ttu-id="eeaa9-158">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="eeaa9-158">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="eeaa9-159">TotalSuccesses</span><span class="sxs-lookup"><span data-stu-id="eeaa9-159">TotalSuccesses</span></span>|<span data-ttu-id="eeaa9-160">int</span><span class="sxs-lookup"><span data-stu-id="eeaa9-160">int</span></span>|<span data-ttu-id="eeaa9-161">Het totale aantal modellen dat uit een documentbibliotheek wordt verwijderd.</span><span class="sxs-lookup"><span data-stu-id="eeaa9-161">The total number of a model being successfully removed from a document library.</span></span>|
|<span data-ttu-id="eeaa9-162">TotalFailures</span><span class="sxs-lookup"><span data-stu-id="eeaa9-162">TotalFailures</span></span>|<span data-ttu-id="eeaa9-163">int</span><span class="sxs-lookup"><span data-stu-id="eeaa9-163">int</span></span>|<span data-ttu-id="eeaa9-164">Het totale aantal modellen dat niet kan worden verwijderd uit een documentbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="eeaa9-164">The total number of a model failing to be removed from a document library.</span></span>|
|<span data-ttu-id="eeaa9-165">Details</span><span class="sxs-lookup"><span data-stu-id="eeaa9-165">Details</span></span>|<span data-ttu-id="eeaa9-166">MachineLearningPublicationResult[]</span><span class="sxs-lookup"><span data-stu-id="eeaa9-166">MachineLearningPublicationResult[]</span></span>|<span data-ttu-id="eeaa9-167">De verzameling MachineLearningPublicationResult die elk het gedetailleerde resultaat specificeert van het verwijderen van het model uit een documentbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="eeaa9-167">The collection of MachineLearningPublicationResult each of which specifies the detailed result of removing the model from a document library.</span></span>|

### <a name="machinelearningpublicationresult"></a><span data-ttu-id="eeaa9-168">MachineLearningPublicationResult</span><span class="sxs-lookup"><span data-stu-id="eeaa9-168">MachineLearningPublicationResult</span></span>
| <span data-ttu-id="eeaa9-169">Naam</span><span class="sxs-lookup"><span data-stu-id="eeaa9-169">Name</span></span>   | <span data-ttu-id="eeaa9-170">Type</span><span class="sxs-lookup"><span data-stu-id="eeaa9-170">Type</span></span>  | <span data-ttu-id="eeaa9-171">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="eeaa9-171">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="eeaa9-172">Statuscode</span><span class="sxs-lookup"><span data-stu-id="eeaa9-172">StatusCode</span></span>|<span data-ttu-id="eeaa9-173">int</span><span class="sxs-lookup"><span data-stu-id="eeaa9-173">int</span></span>|<span data-ttu-id="eeaa9-174">De HTTP-statuscode.</span><span class="sxs-lookup"><span data-stu-id="eeaa9-174">The HTTP status code.</span></span>|
|<span data-ttu-id="eeaa9-175">ErrorMessage</span><span class="sxs-lookup"><span data-stu-id="eeaa9-175">ErrorMessage</span></span>|<span data-ttu-id="eeaa9-176">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="eeaa9-176">string</span></span>|<span data-ttu-id="eeaa9-177">Het foutbericht dat aangeeft wat het probleem is bij het toepassen van het model op de documentbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="eeaa9-177">The error message which tells what's wrong when apply the model to the document library.</span></span>|
|<span data-ttu-id="eeaa9-178">Publicatie</span><span class="sxs-lookup"><span data-stu-id="eeaa9-178">Publication</span></span>|<span data-ttu-id="eeaa9-179">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="eeaa9-179">MachineLearningPublicationEntityData</span></span>|<span data-ttu-id="eeaa9-180">Hiermee geeft u de modelgegevens en de doeldocumentbibliotheek op.</span><span class="sxs-lookup"><span data-stu-id="eeaa9-180">It specifies the model info and the target document library.</span></span>| 

### <a name="machinelearningpublicationentitydata"></a><span data-ttu-id="eeaa9-181">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="eeaa9-181">MachineLearningPublicationEntityData</span></span>
| <span data-ttu-id="eeaa9-182">Naam</span><span class="sxs-lookup"><span data-stu-id="eeaa9-182">Name</span></span> | <span data-ttu-id="eeaa9-183">Type</span><span class="sxs-lookup"><span data-stu-id="eeaa9-183">Type</span></span> | <span data-ttu-id="eeaa9-184">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="eeaa9-184">Description</span></span> |
|--------|--------|------------|
|<span data-ttu-id="eeaa9-185">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="eeaa9-185">ModelUniqueId</span></span>|<span data-ttu-id="eeaa9-186">reeks</span><span class="sxs-lookup"><span data-stu-id="eeaa9-186">string</span></span>|<span data-ttu-id="eeaa9-187">De unieke id van het modelbestand.</span><span class="sxs-lookup"><span data-stu-id="eeaa9-187">The unique ID of the model file.</span></span>|
|<span data-ttu-id="eeaa9-188">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="eeaa9-188">TargetSiteUrl</span></span>|<span data-ttu-id="eeaa9-189">reeks</span><span class="sxs-lookup"><span data-stu-id="eeaa9-189">string</span></span>|<span data-ttu-id="eeaa9-190">De volledige URL van de doelbibliotheeksite.</span><span class="sxs-lookup"><span data-stu-id="eeaa9-190">The full URL of the target library site.</span></span>|
|<span data-ttu-id="eeaa9-191">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="eeaa9-191">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="eeaa9-192">reeks</span><span class="sxs-lookup"><span data-stu-id="eeaa9-192">string</span></span>|<span data-ttu-id="eeaa9-193">De relatieve server-URL van het web voor de doelbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="eeaa9-193">The server relative URL of the web for the target library.</span></span>|
|<span data-ttu-id="eeaa9-194">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="eeaa9-194">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="eeaa9-195">reeks</span><span class="sxs-lookup"><span data-stu-id="eeaa9-195">string</span></span>|<span data-ttu-id="eeaa9-196">De relatieve server-URL van de doelbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="eeaa9-196">The server relative URL of the target library.</span></span>|

## <a name="examples"></a><span data-ttu-id="eeaa9-197">Voorbeelden</span><span class="sxs-lookup"><span data-stu-id="eeaa9-197">Examples</span></span>

### <a name="remove-a-model-from-the-contracts-document-library-in-the-repository-site"></a><span data-ttu-id="eeaa9-198">Een model verwijderen uit de contractdocumentbibliotheek op de repositorysite</span><span class="sxs-lookup"><span data-stu-id="eeaa9-198">Remove a model from the contracts document library in the repository site</span></span>

<span data-ttu-id="eeaa9-199">In dit voorbeeld is de id van het model voor documentbegrip van het Contoso Contract `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span><span class="sxs-lookup"><span data-stu-id="eeaa9-199">In this sample, the ID of the Contoso Contract document understanding model is `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="eeaa9-200">Voorbeeldaanvraag</span><span class="sxs-lookup"><span data-stu-id="eeaa9-200">Sample request</span></span>

```HTTP
{ 
    "publications": [ 
        { 
            "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc", 
            "TargetSiteUrl": "https://constco.sharepoint-df.com/sites/docsite", 
            "TargetWebServerRelativeUrl": "/sites/docsite ", 
            "TargetLibraryServerRelativeUrl": "/sites/dcocsite/joedcos" 
        } 
    ] 
} 
```


#### <a name="sample-response"></a><span data-ttu-id="eeaa9-201">Voorbeeldreactie</span><span class="sxs-lookup"><span data-stu-id="eeaa9-201">Sample response</span></span>

<span data-ttu-id="eeaa9-202">In de reactie verwijzen TotalFailures en TotalSuccesses naar het aantal mislukte en geslaagde pogingen van het model dat wordt verwijderd uit de opgegeven bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="eeaa9-202">In the response, TotalFailures and TotalSuccesses refer to the number of failures and successes of the model being removed from the specified libraries.</span></span>

<span data-ttu-id="eeaa9-203">**Statuscode:** 200</span><span class="sxs-lookup"><span data-stu-id="eeaa9-203">**Status code:** 200</span></span>

```JSON
{
    "Details": [
        {
            "ErrorMessage": null,
            "Publication": {
                "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
                "TargetSiteUrl": "https://contoso.sharepoint.com/sites/repository/",
                "TargetWebServerRelativeUrl": "/sites/repository",
                "TargetLibraryServerRelativeUrl": "/sites/repository/contracts",
                "ViewOption": "NewViewAsDefault"
            },
            "StatusCode": 200
        }
    ],
    "TotalFailures": 0,
    "TotalSuccesses": 1
}
```

## <a name="see-also"></a><span data-ttu-id="eeaa9-204">Zie ook</span><span class="sxs-lookup"><span data-stu-id="eeaa9-204">See also</span></span>

[<span data-ttu-id="eeaa9-205">REST API van Syntex-model voor documentbegrip</span><span class="sxs-lookup"><span data-stu-id="eeaa9-205">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
