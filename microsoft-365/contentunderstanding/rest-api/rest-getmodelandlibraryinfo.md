---
title: Model- en bibliotheekgegevens ophalen
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
description: Gebruik REST API om informatie te krijgen over een model en de bibliotheek waarop het is toegepast.
ms.openlocfilehash: 6cd61364ed3b360ef235aaba21a2735002fe481e
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904187"
---
# <a name="get-model-and-library-information"></a><span data-ttu-id="b6067-103">Model- en bibliotheekgegevens ophalen</span><span class="sxs-lookup"><span data-stu-id="b6067-103">Get model and library information</span></span>

<span data-ttu-id="b6067-104">Haalt informatie op over een model en de bibliotheek waarop het is toegepast (zie [voorbeeld](rest-getmodelandlibraryinfo.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="b6067-104">Gets information about a model and the library where it has been applied (see [example](rest-getmodelandlibraryinfo.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="b6067-105">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="b6067-105">HTTP request</span></span>

```HTTP
GET /_api/machinelearning/publications/getbyuniqueid(‘{modelUniqueId}’) HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="b6067-106">URI-parameters</span><span class="sxs-lookup"><span data-stu-id="b6067-106">URI parameters</span></span>

| <span data-ttu-id="b6067-107">Naam</span><span class="sxs-lookup"><span data-stu-id="b6067-107">Name</span></span> | <span data-ttu-id="b6067-108">In</span><span class="sxs-lookup"><span data-stu-id="b6067-108">In</span></span> | <span data-ttu-id="b6067-109">Vereist</span><span class="sxs-lookup"><span data-stu-id="b6067-109">Required</span></span> | <span data-ttu-id="b6067-110">Type</span><span class="sxs-lookup"><span data-stu-id="b6067-110">Type</span></span> | <span data-ttu-id="b6067-111">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="b6067-111">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="b6067-112">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="b6067-112">ModelUniqueId</span></span>|<span data-ttu-id="b6067-113">query</span><span class="sxs-lookup"><span data-stu-id="b6067-113">query</span></span>|<span data-ttu-id="b6067-114">Waar</span><span class="sxs-lookup"><span data-stu-id="b6067-114">True</span></span>|<span data-ttu-id="b6067-115">GUID</span><span class="sxs-lookup"><span data-stu-id="b6067-115">GUID</span></span>|<span data-ttu-id="b6067-116">De unieke id van het modelbestand.</span><span class="sxs-lookup"><span data-stu-id="b6067-116">The unique id of the model file.</span></span>|

## <a name="request-headers"></a><span data-ttu-id="b6067-117">Aanvraagheaders</span><span class="sxs-lookup"><span data-stu-id="b6067-117">Request headers</span></span>

| <span data-ttu-id="b6067-118">Koptekst</span><span class="sxs-lookup"><span data-stu-id="b6067-118">Header</span></span> | <span data-ttu-id="b6067-119">Waarde</span><span class="sxs-lookup"><span data-stu-id="b6067-119">Value</span></span> |
|--------|-------|
|<span data-ttu-id="b6067-120">Accepteren</span><span class="sxs-lookup"><span data-stu-id="b6067-120">Accept</span></span>|<span data-ttu-id="b6067-121">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="b6067-121">application/json;odata=verbose</span></span>|


## <a name="request-body"></a><span data-ttu-id="b6067-122">Aanvraagtekst</span><span class="sxs-lookup"><span data-stu-id="b6067-122">Request body</span></span>

| <span data-ttu-id="b6067-123">Naam</span><span class="sxs-lookup"><span data-stu-id="b6067-123">Name</span></span> | <span data-ttu-id="b6067-124">Vereist</span><span class="sxs-lookup"><span data-stu-id="b6067-124">Required</span></span> | <span data-ttu-id="b6067-125">Type</span><span class="sxs-lookup"><span data-stu-id="b6067-125">Type</span></span> | <span data-ttu-id="b6067-126">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="b6067-126">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="b6067-127">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="b6067-127">ModelUniqueId</span></span>|<span data-ttu-id="b6067-128">ja</span><span class="sxs-lookup"><span data-stu-id="b6067-128">yes</span></span>|<span data-ttu-id="b6067-129">reeks</span><span class="sxs-lookup"><span data-stu-id="b6067-129">string</span></span>|<span data-ttu-id="b6067-130">De unieke id van het modelbestand.</span><span class="sxs-lookup"><span data-stu-id="b6067-130">The unique ID of the model file.</span></span>|
|<span data-ttu-id="b6067-131">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="b6067-131">TargetSiteUrl</span></span>|<span data-ttu-id="b6067-132">ja</span><span class="sxs-lookup"><span data-stu-id="b6067-132">yes</span></span>|<span data-ttu-id="b6067-133">reeks</span><span class="sxs-lookup"><span data-stu-id="b6067-133">string</span></span>|<span data-ttu-id="b6067-134">De volledige URL van de doelbibliotheeksite.</span><span class="sxs-lookup"><span data-stu-id="b6067-134">The full URL of the target library site.</span></span>|
|<span data-ttu-id="b6067-135">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="b6067-135">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="b6067-136">ja</span><span class="sxs-lookup"><span data-stu-id="b6067-136">yes</span></span>|<span data-ttu-id="b6067-137">reeks</span><span class="sxs-lookup"><span data-stu-id="b6067-137">string</span></span>|<span data-ttu-id="b6067-138">De relatieve server-URL van het web voor de doelbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="b6067-138">The server relative URL of the web for the target library.</span></span>|
|<span data-ttu-id="b6067-139">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="b6067-139">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="b6067-140">ja</span><span class="sxs-lookup"><span data-stu-id="b6067-140">yes</span></span>|<span data-ttu-id="b6067-141">reeks</span><span class="sxs-lookup"><span data-stu-id="b6067-141">string</span></span>|<span data-ttu-id="b6067-142">De relatieve server-URL van de doelbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="b6067-142">The server relative URL of the target library.</span></span>|
|<span data-ttu-id="b6067-143">TargetLibraryRemoved</span><span class="sxs-lookup"><span data-stu-id="b6067-143">TargetLibraryRemoved</span></span>|<span data-ttu-id="b6067-144">ja</span><span class="sxs-lookup"><span data-stu-id="b6067-144">yes</span></span>|<span data-ttu-id="b6067-145">int</span><span class="sxs-lookup"><span data-stu-id="b6067-145">int</span></span>|<span data-ttu-id="b6067-146">De vlag die aangeeft of de doelbibliotheek al dan niet is verwijderd.</span><span class="sxs-lookup"><span data-stu-id="b6067-146">The flag that indicates if the target library has been removed or not.</span></span>|

## <a name="response"></a><span data-ttu-id="b6067-147">Antwoord</span><span class="sxs-lookup"><span data-stu-id="b6067-147">Response</span></span>

| <span data-ttu-id="b6067-148">Naam</span><span class="sxs-lookup"><span data-stu-id="b6067-148">Name</span></span>   | <span data-ttu-id="b6067-149">Type</span><span class="sxs-lookup"><span data-stu-id="b6067-149">Type</span></span>  | <span data-ttu-id="b6067-150">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="b6067-150">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="b6067-151">200 OK</span><span class="sxs-lookup"><span data-stu-id="b6067-151">200 OK</span></span>| |<span data-ttu-id="b6067-152">Succes</span><span class="sxs-lookup"><span data-stu-id="b6067-152">Success</span></span>|
|<span data-ttu-id="b6067-153">201 gemaakt</span><span class="sxs-lookup"><span data-stu-id="b6067-153">201 Created</span></span>| |<span data-ttu-id="b6067-154">Houd er rekening mee dat, omdat deze API het toepassen van een model op meerdere bibliotheken ondersteunt, een 201 kan worden geretourneerd, zelfs als er een fout is opgetreden bij het toepassen van het model op een van de bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="b6067-154">Note that because this API supports applying model to multiple libraries, a 201 could be returned even if there's a failure applying the model to one of the libraries.</span></span> <br><span data-ttu-id="b6067-155">Controleer de antwoordtekst om te zien of het model is toegepast op alle opgegeven bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="b6067-155">Check the response body to understand if the model has been successfully applied to all the specified libraries.</span></span> <span data-ttu-id="b6067-156">Zie [aanvraagtekst](rest-getmodelandlibraryinfo.md#request-body) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="b6067-156">See [Request body](rest-getmodelandlibraryinfo.md#request-body) for details.</span></span>|

## <a name="examples"></a><span data-ttu-id="b6067-157">Voorbeelden</span><span class="sxs-lookup"><span data-stu-id="b6067-157">Examples</span></span>

### <a name="get-information-about-the-contracts-model-and-primed-document-library-in-the-repository-site"></a><span data-ttu-id="b6067-158">Krijg informatie over het contractmodel en de geprimede documentbibliotheek op de repositorysite</span><span class="sxs-lookup"><span data-stu-id="b6067-158">Get information about the contracts model and primed document library in the repository site</span></span>

<span data-ttu-id="b6067-159">In dit voorbeeld is de id van het model voor documentbegrip van het Contoso Contract `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span><span class="sxs-lookup"><span data-stu-id="b6067-159">In this sample, the ID of the Contoso Contract document understanding model is `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="b6067-160">Voorbeeldaanvraag</span><span class="sxs-lookup"><span data-stu-id="b6067-160">Sample request</span></span>

```HTTP
GET /sites/TestCC/_api/machinelearning/publications/getbymodeluniqueid(‘{7645e69d-21fb-4a24-a17a-9bdfa7cb63dc}’) HTTP/1.1
```
#### <a name="sample-response"></a><span data-ttu-id="b6067-161">Voorbeeldantwoord</span><span class="sxs-lookup"><span data-stu-id="b6067-161">Sample response</span></span>

<span data-ttu-id="b6067-162">**Statuscode:** 200</span><span class="sxs-lookup"><span data-stu-id="b6067-162">**Status code:** 200</span></span>

```JSON
{
    "@odata.context": "https://contoso.sharepoint.com/sites/TestCC/_api/$metadata#publications",
    "value": [
        {
            "@odata.type": "#Microsoft.Office.Server.ContentCenter.SPMachineLearningPublication",
            "@odata.id": "https://contoso.sharepoint.com/sites/repository /_api/machinelearning/publications/getbyuniqueId('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc')",
            "@odata.etag": "\"7645e69d-21fb-4a24-a17a-9bdfa7cb63dc,94\"",
            "@odata.editLink": " https://contoso.sharepoint.com/sites/TestCC /_api/machinelearning/publications/getbyuniqueId('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc')",
            "Created": "2021-04-27T03:05:25Z",
            "CreatedBy": "i:0#.f|membership|meganb@contoso.com",
            "DriveId": "b!O-aG9qer5UiXx2jEwd8pL0221maIb9lNs9tH5vAMU-gPy9BrxT7GTrtXtdtv1Uzb",
            "ID": 26,
            "ModelId": 16,
            "ModelName": "contosocontract.classifier",
            "ModelType": 0,
            "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
            "ModelVersion": "8.0",
            "Modified": "2021-03-17T17:56:42Z",
            "ModifiedBy": "i:0#.f|membership|joedoe@contoso.com",
            "ObjectId": "01ZBWEM5FZRILGLXTEB5CZ2NNNSCTWBJMQ",
            "PublicationType": 1,
            "TargetLibraryRemoved": false,
            "TargetLibraryServerRelativeUrl": "/sites/repository/contracts",
            "TargetLibraryUrl": " https://contoso.sharepoint.com/sites/repository/contracts",
            "TargetSiteUrl": "https://contoso.sharepoint.com/sites/repository",
            "TargetWebServerRelativeUrl": "/sites/repository",
            "UniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
            "ViewOption": "NewViewAsDefault"
        },
        {
            "@odata.type": "#Microsoft.Office.Server.ContentCenter.SPMachineLearningPublication",
            "@odata.id": "https://contoso.sharepoint.com /sites/legal/_api/machinelearning/publications/getbyuniqueId('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc')",
            "@odata.etag": "\"7645e69d-21fb-4a24-a17a-9bdfa7cb63dc,101\"",
            "@odata.editLink": "https://contoso.sharepoint.com /sites/legal/_api/machinelearning/publications/getbyuniqueId('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc')",
            "Created": "2021-01-27T03:17:44Z",
            "CreatedBy": "i:0#.f|membership|esherman@contoso.com ",
            "DriveId": "b!O-aG9qer5UiXx2jEwd8pL0221maIb9lNs9tH5vAMU-gPy9BrxT7GTrtXtdtv1Uzb",
            "ID": 27,
            "ModelId": 16,
            "ModelName": "dispositions.classifier",
            "ModelType": 0,
            "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
            "ModelVersion": "8.0",
            "Modified": "2021-03-17T23:17:46Z",
            "ModifiedBy": "i:0#.f|membership|esherman@contoso.com ",
            "ObjectId": "01ZBWEM5B3ERSZK4PAARGLFZ7JP6GMXG2R",
            "PublicationType": 1,
            "TargetLibraryRemoved": false,
            "TargetLibraryServerRelativeUrl": "/sites/legal/dispositions",
            "TargetLibraryUrl": "https://contoso.sharepoint.com/sites/legal/dispositions",
            "TargetSiteUrl": " https://contoso.sharepoint.com/sites/legal",
            "TargetWebServerRelativeUrl": "/sites/legal",
            "UniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
            "ViewOption": "NewViewAsDefault"
        }
    ]
}```
```

## <a name="see-also"></a><span data-ttu-id="b6067-163">Zie ook</span><span class="sxs-lookup"><span data-stu-id="b6067-163">See also</span></span>

[<span data-ttu-id="b6067-164">REST API van Syntex-model voor documentbegrip</span><span class="sxs-lookup"><span data-stu-id="b6067-164">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
