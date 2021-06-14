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
ms.openlocfilehash: 8c7aeb449da161fe49050631643c63c93268a13f
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904178"
---
# <a name="batchdelete"></a><span data-ttu-id="bb843-103">BatchDelete</span><span class="sxs-lookup"><span data-stu-id="bb843-103">BatchDelete</span></span>

<span data-ttu-id="bb843-104">Verwijdert een toegepast model met documentbegrip uit een of meer bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="bb843-104">Removes an applied document understanding model from one or more libraries.</span></span> <span data-ttu-id="bb843-105">Houd er rekening mee dat een model moet worden verwijderd uit alle bibliotheken voordat het kan worden verwijderd (zie [voorbeeld](rest-batchdelete-method.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="bb843-105">Note that a model must be removed from all libraries before it can be deleted (see [example](rest-batchdelete-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="bb843-106">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="bb843-106">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/publications/batchdelete HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="bb843-107">URI-parameters</span><span class="sxs-lookup"><span data-stu-id="bb843-107">URI parameters</span></span>

<span data-ttu-id="bb843-108">Geen</span><span class="sxs-lookup"><span data-stu-id="bb843-108">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="bb843-109">Aanvraagheaders</span><span class="sxs-lookup"><span data-stu-id="bb843-109">Request headers</span></span>

| <span data-ttu-id="bb843-110">Koptekst</span><span class="sxs-lookup"><span data-stu-id="bb843-110">Header</span></span> | <span data-ttu-id="bb843-111">Waarde</span><span class="sxs-lookup"><span data-stu-id="bb843-111">Value</span></span> |
|--------|-------|
|<span data-ttu-id="bb843-112">Accepteren</span><span class="sxs-lookup"><span data-stu-id="bb843-112">Accept</span></span>|<span data-ttu-id="bb843-113">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="bb843-113">application/json;odata=verbose</span></span>|
|<span data-ttu-id="bb843-114">Inhoudstype</span><span class="sxs-lookup"><span data-stu-id="bb843-114">Content-Type</span></span>|<span data-ttu-id="bb843-115">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="bb843-115">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="bb843-116">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="bb843-116">x-requestdigest</span></span>|<span data-ttu-id="bb843-117">De juiste samenvatting voor deze site.</span><span class="sxs-lookup"><span data-stu-id="bb843-117">The appropriate digest for current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="bb843-118">Aanvraagtekst</span><span class="sxs-lookup"><span data-stu-id="bb843-118">Request body</span></span>

| <span data-ttu-id="bb843-119">Naam</span><span class="sxs-lookup"><span data-stu-id="bb843-119">Name</span></span> | <span data-ttu-id="bb843-120">Vereist</span><span class="sxs-lookup"><span data-stu-id="bb843-120">Required</span></span> | <span data-ttu-id="bb843-121">Type</span><span class="sxs-lookup"><span data-stu-id="bb843-121">Type</span></span> | <span data-ttu-id="bb843-122">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="bb843-122">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="bb843-123">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="bb843-123">ModelUniqueId</span></span>|<span data-ttu-id="bb843-124">ja</span><span class="sxs-lookup"><span data-stu-id="bb843-124">yes</span></span>|<span data-ttu-id="bb843-125">reeks</span><span class="sxs-lookup"><span data-stu-id="bb843-125">string</span></span>|<span data-ttu-id="bb843-126">De unieke id van het modelbestand.</span><span class="sxs-lookup"><span data-stu-id="bb843-126">The unique ID of the model file.</span></span>|
<span data-ttu-id="bb843-127">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="bb843-127">TargetSiteUrl</span></span>|<span data-ttu-id="bb843-128">ja</span><span class="sxs-lookup"><span data-stu-id="bb843-128">yes</span></span>|<span data-ttu-id="bb843-129">reeks</span><span class="sxs-lookup"><span data-stu-id="bb843-129">string</span></span>|<span data-ttu-id="bb843-130">De volledige URL van de doelbibliotheeksite.</span><span class="sxs-lookup"><span data-stu-id="bb843-130">The full URL of the target library site.</span></span>|
<span data-ttu-id="bb843-131">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="bb843-131">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="bb843-132">ja</span><span class="sxs-lookup"><span data-stu-id="bb843-132">yes</span></span>|<span data-ttu-id="bb843-133">reeks</span><span class="sxs-lookup"><span data-stu-id="bb843-133">string</span></span>|<span data-ttu-id="bb843-134">De relatieve server-URL van het web voor de doelbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="bb843-134">The server relative URL of the web for the target library.</span></span>|
<span data-ttu-id="bb843-135">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="bb843-135">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="bb843-136">ja</span><span class="sxs-lookup"><span data-stu-id="bb843-136">yes</span></span>|<span data-ttu-id="bb843-137">reeks</span><span class="sxs-lookup"><span data-stu-id="bb843-137">string</span></span>|<span data-ttu-id="bb843-138">De relatieve server-URL van de doelbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="bb843-138">The server relative URL of the target library.</span></span>|
<span data-ttu-id="bb843-139">ViewOption</span><span class="sxs-lookup"><span data-stu-id="bb843-139">ViewOption</span></span>|<span data-ttu-id="bb843-140">nee</span><span class="sxs-lookup"><span data-stu-id="bb843-140">no</span></span>|<span data-ttu-id="bb843-141">reeks</span><span class="sxs-lookup"><span data-stu-id="bb843-141">string</span></span>|<span data-ttu-id="bb843-142">Hiermee geeft u op of een nieuwe modelweergave als standaardbibliotheek moet worden ingesteld.</span><span class="sxs-lookup"><span data-stu-id="bb843-142">Specifies whether to set new model view as the library default.</span></span>|

## <a name="response"></a><span data-ttu-id="bb843-143">Antwoord</span><span class="sxs-lookup"><span data-stu-id="bb843-143">Response</span></span>

| <span data-ttu-id="bb843-144">Naam</span><span class="sxs-lookup"><span data-stu-id="bb843-144">Name</span></span>   | <span data-ttu-id="bb843-145">Type</span><span class="sxs-lookup"><span data-stu-id="bb843-145">Type</span></span>  | <span data-ttu-id="bb843-146">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="bb843-146">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="bb843-147">200 OK</span><span class="sxs-lookup"><span data-stu-id="bb843-147">200 OK</span></span>| |<span data-ttu-id="bb843-148">Succes</span><span class="sxs-lookup"><span data-stu-id="bb843-148">Success</span></span>|


## <a name="examples"></a><span data-ttu-id="bb843-149">Voorbeelden</span><span class="sxs-lookup"><span data-stu-id="bb843-149">Examples</span></span>

### <a name="remove-a-model-from-the-contracts-document-library-in-the-repository-site"></a><span data-ttu-id="bb843-150">Een model verwijderen uit de contractdocumentbibliotheek op de repositorysite</span><span class="sxs-lookup"><span data-stu-id="bb843-150">Remove a model from the contracts document library in the repository site</span></span>

<span data-ttu-id="bb843-151">In dit voorbeeld is de id van het model voor documentbegrip van het Contoso Contract `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span><span class="sxs-lookup"><span data-stu-id="bb843-151">In this sample, the ID of the Contoso Contract document understanding model is `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="bb843-152">Voorbeeldaanvraag</span><span class="sxs-lookup"><span data-stu-id="bb843-152">Sample request</span></span>

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


#### <a name="sample-response"></a><span data-ttu-id="bb843-153">Voorbeeldantwoord</span><span class="sxs-lookup"><span data-stu-id="bb843-153">Sample response</span></span>

<span data-ttu-id="bb843-154">In de reactie verwijzen TotalFailures en TotalSuccesses naar het aantal mislukte en geslaagde pogingen van het model dat van toepassing is op de opgegeven bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="bb843-154">In the response, TotalFailures and TotalSuccesses refer to the number of failures and successes of the model being applies to the specified libraries.</span></span>

<span data-ttu-id="bb843-155">**Statuscode:** 200</span><span class="sxs-lookup"><span data-stu-id="bb843-155">**Status code:** 200</span></span>

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

## <a name="see-also"></a><span data-ttu-id="bb843-156">Zie ook</span><span class="sxs-lookup"><span data-stu-id="bb843-156">See also</span></span>

[<span data-ttu-id="bb843-157">REST API van Syntex-model voor documentbegrip</span><span class="sxs-lookup"><span data-stu-id="bb843-157">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
