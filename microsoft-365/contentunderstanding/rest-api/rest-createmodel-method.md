---
title: Model maken
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
description: Gebruik REST API om een model en het gekoppelde inhoudstype te maken.
ms.openlocfilehash: 4af980d0733fce63767c6570003342eadb079f26
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904186"
---
# <a name="create-model"></a><span data-ttu-id="14322-103">Model maken</span><span class="sxs-lookup"><span data-stu-id="14322-103">Create model</span></span>

<span data-ttu-id="14322-104">Maakt een model en het gekoppelde inhoudstype.</span><span class="sxs-lookup"><span data-stu-id="14322-104">Creates a model and its associated content type.</span></span> <span data-ttu-id="14322-105">Merk op dat hierdoor alleen het model wordt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="14322-105">Note that this only creates the model.</span></span> <span data-ttu-id="14322-106">Deze moet nog worden getraind in het inhoudscentrum (zie [voorbeeld](rest-createmodel-method.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="14322-106">It will still need to be trained in the content center (see [example](rest-createmodel-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="14322-107">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="14322-107">HTTP request</span></span>

```
POST /_api/machinelearning/models HTTP/1.1
```
## <a name="uri-parameters"></a><span data-ttu-id="14322-108">URI-parameters</span><span class="sxs-lookup"><span data-stu-id="14322-108">URI Parameters</span></span>

<span data-ttu-id="14322-109">Geen</span><span class="sxs-lookup"><span data-stu-id="14322-109">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="14322-110">Aanvraagheaders</span><span class="sxs-lookup"><span data-stu-id="14322-110">Request headers</span></span>

| <span data-ttu-id="14322-111">Koptekst</span><span class="sxs-lookup"><span data-stu-id="14322-111">Header</span></span> | <span data-ttu-id="14322-112">Waarde</span><span class="sxs-lookup"><span data-stu-id="14322-112">Value</span></span> |
|--------|-------|
|<span data-ttu-id="14322-113">Accepteren</span><span class="sxs-lookup"><span data-stu-id="14322-113">Accept</span></span>|<span data-ttu-id="14322-114">toepassing/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="14322-114">application/json;odata=verbose</span></span>|
|<span data-ttu-id="14322-115">Inhoudstype</span><span class="sxs-lookup"><span data-stu-id="14322-115">Content-Type</span></span>|<span data-ttu-id="14322-116">toepassing/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="14322-116">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="14322-117">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="14322-117">x-requestdigest</span></span>|<span data-ttu-id="14322-118">De juiste samenvatting voor deze site</span><span class="sxs-lookup"><span data-stu-id="14322-118">The appropriate digest for current site</span></span>|

## <a name="request-body"></a><span data-ttu-id="14322-119">Aanvraagtekst</span><span class="sxs-lookup"><span data-stu-id="14322-119">Request body</span></span>

|<span data-ttu-id="14322-120">Naam</span><span class="sxs-lookup"><span data-stu-id="14322-120">Name</span></span>    |<span data-ttu-id="14322-121">Type</span><span class="sxs-lookup"><span data-stu-id="14322-121">Type</span></span>   |<span data-ttu-id="14322-122">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="14322-122">Description</span></span> |
|--------|-------|------------|
|<span data-ttu-id="14322-123">_metagegevens</span><span class="sxs-lookup"><span data-stu-id="14322-123">_metadata</span></span>|  |<span data-ttu-id="14322-124">Stel de objectmeta in op de SPO.</span><span class="sxs-lookup"><span data-stu-id="14322-124">Set the object meta on the SPO.</span></span> <span data-ttu-id="14322-125">Gebruik altijd de waarde: {"type": "Microsoft.Office.Server.ContentCenter.SP MachineLearningModelEntityData"}.</span><span class="sxs-lookup"><span data-stu-id="14322-125">Always use the value: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"}.</span></span> |
|<span data-ttu-id="14322-126">ContentTypeGroup</span><span class="sxs-lookup"><span data-stu-id="14322-126">ContentTypeGroup</span></span>|<span data-ttu-id="14322-127">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="14322-127">string</span></span>|<span data-ttu-id="14322-128">De groep van het gekoppelde inhoudstype die aan het model is gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="14322-128">The associated content type group associated with the model.</span></span> <span data-ttu-id="14322-129">Is standaard ingesteld op 'Intelligente documentinhoudtypen'.</span><span class="sxs-lookup"><span data-stu-id="14322-129">Defaulted to "Intelligent Document Content Types".</span></span>|
|<span data-ttu-id="14322-130">ContentTypeName</span><span class="sxs-lookup"><span data-stu-id="14322-130">ContentTypeName</span></span>|<span data-ttu-id="14322-131">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="14322-131">string</span></span>|<span data-ttu-id="14322-132">De naam van het gekoppelde inhoudstype.</span><span class="sxs-lookup"><span data-stu-id="14322-132">The associated content type name.</span></span> <span data-ttu-id="14322-133">Het gemaakte modelbestand krijgt dezelfde naam.</span><span class="sxs-lookup"><span data-stu-id="14322-133">The created model file will have the same name.</span></span>|

## <a name="responses"></a><span data-ttu-id="14322-134">Antwoorden</span><span class="sxs-lookup"><span data-stu-id="14322-134">Responses</span></span>

| <span data-ttu-id="14322-135">Naam</span><span class="sxs-lookup"><span data-stu-id="14322-135">Name</span></span>   | <span data-ttu-id="14322-136">Type</span><span class="sxs-lookup"><span data-stu-id="14322-136">Type</span></span>  | <span data-ttu-id="14322-137">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="14322-137">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="14322-138">201 gemaakt</span><span class="sxs-lookup"><span data-stu-id="14322-138">201 Created</span></span>| |<span data-ttu-id="14322-139">Geslaagd</span><span class="sxs-lookup"><span data-stu-id="14322-139">Success</span></span>|

## <a name="examples"></a><span data-ttu-id="14322-140">Voorbeelden</span><span class="sxs-lookup"><span data-stu-id="14322-140">Examples</span></span>

### <a name="create-a-new-document-understanding-model-called-contoso-contract"></a><span data-ttu-id="14322-141">Een nieuw documentbegripsmodel maken met de naam 'Contoso-contract'</span><span class="sxs-lookup"><span data-stu-id="14322-141">Create a new document understanding model called "Contoso Contract"</span></span>

#### <a name="sample-request"></a><span data-ttu-id="14322-142">Voorbeeldaanvraag</span><span class="sxs-lookup"><span data-stu-id="14322-142">Sample request</span></span>

```
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"
    },
    "ContentTypeGroup": "Intelligent Document Content Types",
    "ContentTypeName": "Contoso Contract",
}
```

#### <a name="sample-response"></a><span data-ttu-id="14322-143">Voorbeeldreactie</span><span class="sxs-lookup"><span data-stu-id="14322-143">Sample response</span></span>

<span data-ttu-id="14322-144">**Statuscode:** 201</span><span class="sxs-lookup"><span data-stu-id="14322-144">**Status code:** 201</span></span>

## <a name="see-also"></a><span data-ttu-id="14322-145">Zie ook</span><span class="sxs-lookup"><span data-stu-id="14322-145">See also</span></span>

[<span data-ttu-id="14322-146">RESET API Syntec-documentbegripmodel</span><span class="sxs-lookup"><span data-stu-id="14322-146">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
