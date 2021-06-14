---
title: Model toepassen
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
description: Gebruik REST API om een toegepast model met documentbegrip toe te passen op een of meer bibliotheken.
ms.openlocfilehash: d4cadad3c45dd7af0cdaeb4e1b367426289db870
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904268"
---
# <a name="apply-model"></a><span data-ttu-id="24e6b-103">Model toepassen</span><span class="sxs-lookup"><span data-stu-id="24e6b-103">Apply model</span></span>

<span data-ttu-id="24e6b-104">Past (of synchroniseert) een getraind model voor documentbegrip toe op een of meer bibliotheken (zie [voorbeeld](rest-applymodel-method.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="24e6b-104">Applies (or syncs) a trained document understanding model to one or more libraries (see [example](rest-applymodel-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="24e6b-105">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="24e6b-105">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/publications HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="24e6b-106">URI-parameters</span><span class="sxs-lookup"><span data-stu-id="24e6b-106">URI parameters</span></span>

<span data-ttu-id="24e6b-107">Geen</span><span class="sxs-lookup"><span data-stu-id="24e6b-107">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="24e6b-108">Aanvraagheaders</span><span class="sxs-lookup"><span data-stu-id="24e6b-108">Request headers</span></span>

| <span data-ttu-id="24e6b-109">Koptekst</span><span class="sxs-lookup"><span data-stu-id="24e6b-109">Header</span></span> | <span data-ttu-id="24e6b-110">Waarde</span><span class="sxs-lookup"><span data-stu-id="24e6b-110">Value</span></span> |
|--------|-------|
|<span data-ttu-id="24e6b-111">Accepteren</span><span class="sxs-lookup"><span data-stu-id="24e6b-111">Accept</span></span>|<span data-ttu-id="24e6b-112">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="24e6b-112">application/json;odata=verbose</span></span>|
|<span data-ttu-id="24e6b-113">Inhoudstype</span><span class="sxs-lookup"><span data-stu-id="24e6b-113">Content-Type</span></span>|<span data-ttu-id="24e6b-114">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="24e6b-114">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="24e6b-115">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="24e6b-115">x-requestdigest</span></span>|<span data-ttu-id="24e6b-116">De juiste samenvatting voor deze site.</span><span class="sxs-lookup"><span data-stu-id="24e6b-116">The appropriate digest for current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="24e6b-117">Aanvraagtekst</span><span class="sxs-lookup"><span data-stu-id="24e6b-117">Request body</span></span>

| <span data-ttu-id="24e6b-118">Naam</span><span class="sxs-lookup"><span data-stu-id="24e6b-118">Name</span></span> | <span data-ttu-id="24e6b-119">Vereist</span><span class="sxs-lookup"><span data-stu-id="24e6b-119">Required</span></span> | <span data-ttu-id="24e6b-120">Type</span><span class="sxs-lookup"><span data-stu-id="24e6b-120">Type</span></span> | <span data-ttu-id="24e6b-121">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="24e6b-121">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="24e6b-122">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="24e6b-122">ModelUniqueId</span></span>|<span data-ttu-id="24e6b-123">ja</span><span class="sxs-lookup"><span data-stu-id="24e6b-123">yes</span></span>|<span data-ttu-id="24e6b-124">reeks</span><span class="sxs-lookup"><span data-stu-id="24e6b-124">string</span></span>|<span data-ttu-id="24e6b-125">De unieke id van het modelbestand.</span><span class="sxs-lookup"><span data-stu-id="24e6b-125">The unique ID of the model file.</span></span>|
<span data-ttu-id="24e6b-126">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="24e6b-126">TargetSiteUrl</span></span>|<span data-ttu-id="24e6b-127">ja</span><span class="sxs-lookup"><span data-stu-id="24e6b-127">yes</span></span>|<span data-ttu-id="24e6b-128">reeks</span><span class="sxs-lookup"><span data-stu-id="24e6b-128">string</span></span>|<span data-ttu-id="24e6b-129">De volledige URL van de doelbibliotheeksite.</span><span class="sxs-lookup"><span data-stu-id="24e6b-129">The full URL of the target library site.</span></span>|
<span data-ttu-id="24e6b-130">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="24e6b-130">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="24e6b-131">ja</span><span class="sxs-lookup"><span data-stu-id="24e6b-131">yes</span></span>|<span data-ttu-id="24e6b-132">reeks</span><span class="sxs-lookup"><span data-stu-id="24e6b-132">string</span></span>|<span data-ttu-id="24e6b-133">De relatieve server-URL van het web voor de doelbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="24e6b-133">The server relative URL of the web for the target library.</span></span>|
<span data-ttu-id="24e6b-134">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="24e6b-134">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="24e6b-135">ja</span><span class="sxs-lookup"><span data-stu-id="24e6b-135">yes</span></span>|<span data-ttu-id="24e6b-136">reeks</span><span class="sxs-lookup"><span data-stu-id="24e6b-136">string</span></span>|<span data-ttu-id="24e6b-137">De relatieve server-URL van de doelbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="24e6b-137">The server relative URL of the target library.</span></span>|
<span data-ttu-id="24e6b-138">ViewOption</span><span class="sxs-lookup"><span data-stu-id="24e6b-138">ViewOption</span></span>|<span data-ttu-id="24e6b-139">nee</span><span class="sxs-lookup"><span data-stu-id="24e6b-139">no</span></span>|<span data-ttu-id="24e6b-140">reeks</span><span class="sxs-lookup"><span data-stu-id="24e6b-140">string</span></span>|<span data-ttu-id="24e6b-141">Hiermee geeft u op of een nieuwe modelweergave als standaardbibliotheek moet worden ingesteld.</span><span class="sxs-lookup"><span data-stu-id="24e6b-141">Specifies whether to set new model view as the library default.</span></span>|

## <a name="response"></a><span data-ttu-id="24e6b-142">Reactie</span><span class="sxs-lookup"><span data-stu-id="24e6b-142">Response</span></span>

| <span data-ttu-id="24e6b-143">Naam</span><span class="sxs-lookup"><span data-stu-id="24e6b-143">Name</span></span>   | <span data-ttu-id="24e6b-144">Type</span><span class="sxs-lookup"><span data-stu-id="24e6b-144">Type</span></span>  | <span data-ttu-id="24e6b-145">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="24e6b-145">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="24e6b-146">200 OK</span><span class="sxs-lookup"><span data-stu-id="24e6b-146">200 OK</span></span>| |<span data-ttu-id="24e6b-147">Succes</span><span class="sxs-lookup"><span data-stu-id="24e6b-147">Success</span></span>|
|<span data-ttu-id="24e6b-148">201 gemaakt</span><span class="sxs-lookup"><span data-stu-id="24e6b-148">201 Created</span></span>| |<span data-ttu-id="24e6b-149">Houd er rekening mee dat, omdat deze API het toepassen van een model op meerdere bibliotheken ondersteunt, een 201 kan worden geretourneerd, zelfs als er een fout is opgetreden bij het toepassen van het model op een van de bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="24e6b-149">Note that because this API supports applying model to multiple libraries, a 201 could be returned even if there's a failure applying the model to one of the libraries.</span></span> <br><span data-ttu-id="24e6b-150">Controleer de antwoordtekst om te zien of het model is toegepast op alle opgegeven bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="24e6b-150">Check the response body to understand if the model has been successfully applied to all the specified libraries.</span></span> <span data-ttu-id="24e6b-151">Zie [aanvraagtekst](rest-applymodel-method.md#request-body) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="24e6b-151">See [Request body](rest-applymodel-method.md#request-body) for details.</span></span>|

## <a name="examples"></a><span data-ttu-id="24e6b-152">Voorbeelden</span><span class="sxs-lookup"><span data-stu-id="24e6b-152">Examples</span></span>

### <a name="apply-a-model-to-the-contracts-document-library-in-the-repository-site"></a><span data-ttu-id="24e6b-153">Een model toepassen op de contractdocumentbibliotheek op de repositorysite</span><span class="sxs-lookup"><span data-stu-id="24e6b-153">Apply a model to the contracts document library in the repository site</span></span>

<span data-ttu-id="24e6b-154">In dit voorbeeld is de id van het model voor documentbegrip van het Contoso Contract `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span><span class="sxs-lookup"><span data-stu-id="24e6b-154">In this sample, the ID of the Contoso Contract document understanding model is `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="24e6b-155">Voorbeeldaanvraag</span><span class="sxs-lookup"><span data-stu-id="24e6b-155">Sample request</span></span>

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


#### <a name="sample-response"></a><span data-ttu-id="24e6b-156">Voorbeeldantwoord</span><span class="sxs-lookup"><span data-stu-id="24e6b-156">Sample response</span></span>

<span data-ttu-id="24e6b-157">In de reactie verwijzen TotalFailures en TotalSuccesses naar het aantal mislukte en geslaagde pogingen van het model dat van toepassing is op de opgegeven bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="24e6b-157">In the response, TotalFailures and TotalSuccesses refers to the number of failures and successes of the model being applies to the specified libraries.</span></span>

<span data-ttu-id="24e6b-158">**Statuscode:** 200</span><span class="sxs-lookup"><span data-stu-id="24e6b-158">**Status code:** 200</span></span>

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

## <a name="see-also"></a><span data-ttu-id="24e6b-159">Zie ook</span><span class="sxs-lookup"><span data-stu-id="24e6b-159">See also</span></span>

[<span data-ttu-id="24e6b-160">REST API van Syntex-model voor documentbegrip</span><span class="sxs-lookup"><span data-stu-id="24e6b-160">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
