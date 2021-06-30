---
title: Model Batch toepassen
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
description: Gebruik REST API om een model met documentbegrip toe te passen op een of meer bibliotheken.
ms.openlocfilehash: 24ea9a480bc3ce5a7745857de17a6fab6ed97685
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177259"
---
# <a name="batch-apply-model"></a><span data-ttu-id="abbb8-103">Model Batch toepassen</span><span class="sxs-lookup"><span data-stu-id="abbb8-103">Batch Apply model</span></span>

<span data-ttu-id="abbb8-104">Past (of synchroniseert) een getraind model voor documentbegrip toe op een of meer bibliotheken (zie [voorbeeld](rest-applymodel-method.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="abbb8-104">Applies (or syncs) a trained document understanding model to one or more libraries (see [example](rest-applymodel-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="abbb8-105">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="abbb8-105">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/publications HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="abbb8-106">URI-parameters</span><span class="sxs-lookup"><span data-stu-id="abbb8-106">URI parameters</span></span>

<span data-ttu-id="abbb8-107">Geen</span><span class="sxs-lookup"><span data-stu-id="abbb8-107">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="abbb8-108">Aanvraagheaders</span><span class="sxs-lookup"><span data-stu-id="abbb8-108">Request headers</span></span>

| <span data-ttu-id="abbb8-109">Header</span><span class="sxs-lookup"><span data-stu-id="abbb8-109">Header</span></span> | <span data-ttu-id="abbb8-110">Waarde</span><span class="sxs-lookup"><span data-stu-id="abbb8-110">Value</span></span> |
|--------|-------|
|<span data-ttu-id="abbb8-111">Accepteren</span><span class="sxs-lookup"><span data-stu-id="abbb8-111">Accept</span></span>|<span data-ttu-id="abbb8-112">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="abbb8-112">application/json;odata=verbose</span></span>|
|<span data-ttu-id="abbb8-113">Content-Type</span><span class="sxs-lookup"><span data-stu-id="abbb8-113">Content-Type</span></span>|<span data-ttu-id="abbb8-114">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="abbb8-114">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="abbb8-115">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="abbb8-115">x-requestdigest</span></span>|<span data-ttu-id="abbb8-116">De juiste samenvatting voor deze site.</span><span class="sxs-lookup"><span data-stu-id="abbb8-116">The appropriate digest for current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="abbb8-117">Aanvraagtekst</span><span class="sxs-lookup"><span data-stu-id="abbb8-117">Request body</span></span>

| <span data-ttu-id="abbb8-118">Naam</span><span class="sxs-lookup"><span data-stu-id="abbb8-118">Name</span></span> | <span data-ttu-id="abbb8-119">Vereist</span><span class="sxs-lookup"><span data-stu-id="abbb8-119">Required</span></span> | <span data-ttu-id="abbb8-120">Type</span><span class="sxs-lookup"><span data-stu-id="abbb8-120">Type</span></span> | <span data-ttu-id="abbb8-121">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="abbb8-121">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="abbb8-122">__metadata</span><span class="sxs-lookup"><span data-stu-id="abbb8-122">__metadata</span></span>|<span data-ttu-id="abbb8-123">ja</span><span class="sxs-lookup"><span data-stu-id="abbb8-123">yes</span></span>|<span data-ttu-id="abbb8-124">reeks</span><span class="sxs-lookup"><span data-stu-id="abbb8-124">string</span></span>|<span data-ttu-id="abbb8-125">Stel de objectmeta in op de SPO.</span><span class="sxs-lookup"><span data-stu-id="abbb8-125">Set the object meta on the SPO.</span></span> <span data-ttu-id="abbb8-126">Gebruik altijd de waarde: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningPublicationsEntityData"}.</span><span class="sxs-lookup"><span data-stu-id="abbb8-126">Always use the value: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningPublicationsEntityData"}.</span></span>|
|<span data-ttu-id="abbb8-127">Publicaties</span><span class="sxs-lookup"><span data-stu-id="abbb8-127">Publications</span></span>|<span data-ttu-id="abbb8-128">ja</span><span class="sxs-lookup"><span data-stu-id="abbb8-128">yes</span></span>|<span data-ttu-id="abbb8-129">MachineLearningPublicationEntityData[]</span><span class="sxs-lookup"><span data-stu-id="abbb8-129">MachineLearningPublicationEntityData[]</span></span>|<span data-ttu-id="abbb8-130">De verzameling MachineLearningPublicationEntityData die elk het model en de doeldocumentbibliotheek specificeert.</span><span class="sxs-lookup"><span data-stu-id="abbb8-130">The collection of MachineLearningPublicationEntityData each of which specifies the model and target document library.</span></span>|

### <a name="machinelearningpublicationentitydata"></a><span data-ttu-id="abbb8-131">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="abbb8-131">MachineLearningPublicationEntityData</span></span>
| <span data-ttu-id="abbb8-132">Naam</span><span class="sxs-lookup"><span data-stu-id="abbb8-132">Name</span></span> | <span data-ttu-id="abbb8-133">Vereist</span><span class="sxs-lookup"><span data-stu-id="abbb8-133">Required</span></span> | <span data-ttu-id="abbb8-134">Type</span><span class="sxs-lookup"><span data-stu-id="abbb8-134">Type</span></span> | <span data-ttu-id="abbb8-135">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="abbb8-135">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="abbb8-136">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="abbb8-136">ModelUniqueId</span></span>|<span data-ttu-id="abbb8-137">ja</span><span class="sxs-lookup"><span data-stu-id="abbb8-137">yes</span></span>|<span data-ttu-id="abbb8-138">reeks</span><span class="sxs-lookup"><span data-stu-id="abbb8-138">string</span></span>|<span data-ttu-id="abbb8-139">De unieke id van het modelbestand.</span><span class="sxs-lookup"><span data-stu-id="abbb8-139">The unique ID of the model file.</span></span>|
|<span data-ttu-id="abbb8-140">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="abbb8-140">TargetSiteUrl</span></span>|<span data-ttu-id="abbb8-141">ja</span><span class="sxs-lookup"><span data-stu-id="abbb8-141">yes</span></span>|<span data-ttu-id="abbb8-142">reeks</span><span class="sxs-lookup"><span data-stu-id="abbb8-142">string</span></span>|<span data-ttu-id="abbb8-143">De volledige URL van de doelbibliotheeksite.</span><span class="sxs-lookup"><span data-stu-id="abbb8-143">The full URL of the target library site.</span></span>|
|<span data-ttu-id="abbb8-144">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="abbb8-144">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="abbb8-145">ja</span><span class="sxs-lookup"><span data-stu-id="abbb8-145">yes</span></span>|<span data-ttu-id="abbb8-146">reeks</span><span class="sxs-lookup"><span data-stu-id="abbb8-146">string</span></span>|<span data-ttu-id="abbb8-147">De relatieve server-URL van het web voor de doelbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="abbb8-147">The server relative URL of the web for the target library.</span></span>|
|<span data-ttu-id="abbb8-148">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="abbb8-148">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="abbb8-149">ja</span><span class="sxs-lookup"><span data-stu-id="abbb8-149">yes</span></span>|<span data-ttu-id="abbb8-150">reeks</span><span class="sxs-lookup"><span data-stu-id="abbb8-150">string</span></span>|<span data-ttu-id="abbb8-151">De relatieve server-URL van de doelbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="abbb8-151">The server relative URL of the target library.</span></span>|
|<span data-ttu-id="abbb8-152">ViewOption</span><span class="sxs-lookup"><span data-stu-id="abbb8-152">ViewOption</span></span>|<span data-ttu-id="abbb8-153">nee</span><span class="sxs-lookup"><span data-stu-id="abbb8-153">no</span></span>|<span data-ttu-id="abbb8-154">reeks</span><span class="sxs-lookup"><span data-stu-id="abbb8-154">string</span></span>|<span data-ttu-id="abbb8-155">Hiermee geeft u op of een nieuwe modelweergave als standaardbibliotheek moet worden ingesteld.</span><span class="sxs-lookup"><span data-stu-id="abbb8-155">Specifies whether to set new model view as the library default.</span></span>|

## <a name="response"></a><span data-ttu-id="abbb8-156">Antwoord</span><span class="sxs-lookup"><span data-stu-id="abbb8-156">Response</span></span>

| <span data-ttu-id="abbb8-157">Naam</span><span class="sxs-lookup"><span data-stu-id="abbb8-157">Name</span></span>   | <span data-ttu-id="abbb8-158">Type</span><span class="sxs-lookup"><span data-stu-id="abbb8-158">Type</span></span>  | <span data-ttu-id="abbb8-159">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="abbb8-159">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="abbb8-160">201 gemaakt</span><span class="sxs-lookup"><span data-stu-id="abbb8-160">201 Created</span></span>||<span data-ttu-id="abbb8-161">Dit is een aangepaste API ter ondersteuning van het toepassen van een model op bibliotheken met meerdere documenten.</span><span class="sxs-lookup"><span data-stu-id="abbb8-161">This is a customized API to support applying a model to multi document libraries.</span></span> <span data-ttu-id="abbb8-162">In het geval van gedeeltelijk succes kan 201 gemaakt nog steeds worden geretourneerd en moet de aanroeper de antwoordtekst inspecteren om te begrijpen of het model is toegepast op een documentbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="abbb8-162">In the case of partial success, 201 created could still be returned and the caller needs to inspect the response body to understand if the model has been successfully applied to a document library.</span></span>|

## <a name="response-body"></a><span data-ttu-id="abbb8-163">Antwoordtekst</span><span class="sxs-lookup"><span data-stu-id="abbb8-163">Response Body</span></span>
| <span data-ttu-id="abbb8-164">Naam</span><span class="sxs-lookup"><span data-stu-id="abbb8-164">Name</span></span>   | <span data-ttu-id="abbb8-165">Type</span><span class="sxs-lookup"><span data-stu-id="abbb8-165">Type</span></span>  | <span data-ttu-id="abbb8-166">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="abbb8-166">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="abbb8-167">TotalSuccesses</span><span class="sxs-lookup"><span data-stu-id="abbb8-167">TotalSuccesses</span></span>|<span data-ttu-id="abbb8-168">int</span><span class="sxs-lookup"><span data-stu-id="abbb8-168">int</span></span>|<span data-ttu-id="abbb8-169">Het totale aantal modellen dat wordt toegepast op een documentbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="abbb8-169">The total number of a model being successfully applied to a document library.</span></span>|
|<span data-ttu-id="abbb8-170">TotalFailures</span><span class="sxs-lookup"><span data-stu-id="abbb8-170">TotalFailures</span></span>|<span data-ttu-id="abbb8-171">int</span><span class="sxs-lookup"><span data-stu-id="abbb8-171">int</span></span>|<span data-ttu-id="abbb8-172">Het totale aantal modellen dat niet kan worden toegepast op een documentbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="abbb8-172">The total number of a model failing to be applied to a document library.</span></span>|
|<span data-ttu-id="abbb8-173">Details</span><span class="sxs-lookup"><span data-stu-id="abbb8-173">Details</span></span>|<span data-ttu-id="abbb8-174">MachineLearningPublicationResult[]</span><span class="sxs-lookup"><span data-stu-id="abbb8-174">MachineLearningPublicationResult[]</span></span>|<span data-ttu-id="abbb8-175">De verzameling MachineLearningPublicationResult die elk het gedetailleerde resultaat specificeert van het toepassen van het model op de documentbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="abbb8-175">The collection of MachineLearningPublicationResult each of which specifies the detailed result of applying the model to the document library.</span></span>|

### <a name="machinelearningpublicationresult"></a><span data-ttu-id="abbb8-176">MachineLearningPublicationResult</span><span class="sxs-lookup"><span data-stu-id="abbb8-176">MachineLearningPublicationResult</span></span>
| <span data-ttu-id="abbb8-177">Naam</span><span class="sxs-lookup"><span data-stu-id="abbb8-177">Name</span></span>   | <span data-ttu-id="abbb8-178">Type</span><span class="sxs-lookup"><span data-stu-id="abbb8-178">Type</span></span>  | <span data-ttu-id="abbb8-179">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="abbb8-179">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="abbb8-180">Statuscode</span><span class="sxs-lookup"><span data-stu-id="abbb8-180">StatusCode</span></span>|<span data-ttu-id="abbb8-181">int</span><span class="sxs-lookup"><span data-stu-id="abbb8-181">int</span></span>|<span data-ttu-id="abbb8-182">De HTTP-statuscode.</span><span class="sxs-lookup"><span data-stu-id="abbb8-182">The HTTP status code.</span></span>|
|<span data-ttu-id="abbb8-183">ErrorMessage</span><span class="sxs-lookup"><span data-stu-id="abbb8-183">ErrorMessage</span></span>|<span data-ttu-id="abbb8-184">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="abbb8-184">string</span></span>|<span data-ttu-id="abbb8-185">Het foutbericht dat aangeeft wat het probleem is bij het toepassen van het model op de documentbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="abbb8-185">The error message which tells what's wrong when apply the model to the document library.</span></span>|
|<span data-ttu-id="abbb8-186">Publicatie</span><span class="sxs-lookup"><span data-stu-id="abbb8-186">Publication</span></span>|<span data-ttu-id="abbb8-187">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="abbb8-187">MachineLearningPublicationEntityData</span></span>|<span data-ttu-id="abbb8-188">Hiermee geeft u de modelgegevens en de doeldocumentbibliotheek op.</span><span class="sxs-lookup"><span data-stu-id="abbb8-188">It specifies the model info and the target document library.</span></span>| 

### <a name="machinelearningpublicationentitydata"></a><span data-ttu-id="abbb8-189">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="abbb8-189">MachineLearningPublicationEntityData</span></span>
| <span data-ttu-id="abbb8-190">Naam</span><span class="sxs-lookup"><span data-stu-id="abbb8-190">Name</span></span> | <span data-ttu-id="abbb8-191">Type</span><span class="sxs-lookup"><span data-stu-id="abbb8-191">Type</span></span> | <span data-ttu-id="abbb8-192">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="abbb8-192">Description</span></span> |
|--------|--------|------------|
|<span data-ttu-id="abbb8-193">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="abbb8-193">ModelUniqueId</span></span>|<span data-ttu-id="abbb8-194">reeks</span><span class="sxs-lookup"><span data-stu-id="abbb8-194">string</span></span>|<span data-ttu-id="abbb8-195">De unieke id van het modelbestand.</span><span class="sxs-lookup"><span data-stu-id="abbb8-195">The unique ID of the model file.</span></span>|
|<span data-ttu-id="abbb8-196">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="abbb8-196">TargetSiteUrl</span></span>|<span data-ttu-id="abbb8-197">reeks</span><span class="sxs-lookup"><span data-stu-id="abbb8-197">string</span></span>|<span data-ttu-id="abbb8-198">De volledige URL van de doelbibliotheeksite.</span><span class="sxs-lookup"><span data-stu-id="abbb8-198">The full URL of the target library site.</span></span>|
|<span data-ttu-id="abbb8-199">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="abbb8-199">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="abbb8-200">reeks</span><span class="sxs-lookup"><span data-stu-id="abbb8-200">string</span></span>|<span data-ttu-id="abbb8-201">De relatieve server-URL van het web voor de doelbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="abbb8-201">The server relative URL of the web for the target library.</span></span>|
|<span data-ttu-id="abbb8-202">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="abbb8-202">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="abbb8-203">reeks</span><span class="sxs-lookup"><span data-stu-id="abbb8-203">string</span></span>|<span data-ttu-id="abbb8-204">De relatieve server-URL van de doelbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="abbb8-204">The server relative URL of the target library.</span></span>|

## <a name="examples"></a><span data-ttu-id="abbb8-205">Voorbeelden</span><span class="sxs-lookup"><span data-stu-id="abbb8-205">Examples</span></span>

### <a name="apply-a-model-to-the-contracts-document-library-in-the-repository-site"></a><span data-ttu-id="abbb8-206">Een model toepassen op de contractdocumentbibliotheek op de repositorysite</span><span class="sxs-lookup"><span data-stu-id="abbb8-206">Apply a model to the contracts document library in the repository site</span></span>

<span data-ttu-id="abbb8-207">In dit voorbeeld is de id van het model voor documentbegrip van het Contoso Contract `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span><span class="sxs-lookup"><span data-stu-id="abbb8-207">In this sample, the ID of the Contoso Contract document understanding model is `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="abbb8-208">Voorbeeldaanvraag</span><span class="sxs-lookup"><span data-stu-id="abbb8-208">Sample request</span></span>

```HTTP
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningPublicationsEntityData"
    },
    "Publications": {
        "results": [
            {
                "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
                "TargetSiteUrl": "https://contoso.sharepoint.com/sites/repository/",
                "TargetWebServerRelativeUrl": "/sites/repository",
                "TargetLibraryServerRelativeUrl": "/sites/repository/contracts",
                "ViewOption": "NewViewAsDefault"
            }
        ]
    }
}
```


#### <a name="sample-response"></a><span data-ttu-id="abbb8-209">Voorbeeldantwoord</span><span class="sxs-lookup"><span data-stu-id="abbb8-209">Sample response</span></span>

<span data-ttu-id="abbb8-210">In de reactie verwijzen TotalFailures en TotalSuccesses naar het aantal mislukte en geslaagde pogingen van het model dat van toepassing is op de opgegeven bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="abbb8-210">In the response, TotalFailures and TotalSuccesses refers to the number of failures and successes of the model being applies to the specified libraries.</span></span>

<span data-ttu-id="abbb8-211">**Statuscode:** 201</span><span class="sxs-lookup"><span data-stu-id="abbb8-211">**Status code:** 201</span></span>

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
            "StatusCode": 201
        }
    ],
    "TotalFailures": 0,
    "TotalSuccesses": 1
}
```

## <a name="see-also"></a><span data-ttu-id="abbb8-212">Zie ook</span><span class="sxs-lookup"><span data-stu-id="abbb8-212">See also</span></span>

[<span data-ttu-id="abbb8-213">REST API van Syntex-model voor documentbegrip</span><span class="sxs-lookup"><span data-stu-id="abbb8-213">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
