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
description: REST API gebruiken om een model en het gekoppelde inhoudstype te maken.
ms.openlocfilehash: 4af980d0733fce63767c6570003342eadb079f26
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904186"
---
# <a name="create-model"></a><span data-ttu-id="75191-103">Model maken</span><span class="sxs-lookup"><span data-stu-id="75191-103">Create model</span></span>

<span data-ttu-id="75191-104">Een model en het gekoppelde inhoudstype maken.</span><span class="sxs-lookup"><span data-stu-id="75191-104">Creates a model and its associated content type.</span></span> <span data-ttu-id="75191-105">Hiermee wordt het model alleen gemaakt.</span><span class="sxs-lookup"><span data-stu-id="75191-105">Note that this only creates the model.</span></span> <span data-ttu-id="75191-106">Het moet nog wel worden getraind in het inhoudscentrum (zie [voorbeeld](rest-createmodel-method.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="75191-106">It will still need to be trained in the content center (see [example](rest-createmodel-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="75191-107">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="75191-107">HTTP request</span></span>

```
POST /_api/machinelearning/models HTTP/1.1
```
## <a name="uri-parameters"></a><span data-ttu-id="75191-108">URI-parameters</span><span class="sxs-lookup"><span data-stu-id="75191-108">URI Parameters</span></span>

<span data-ttu-id="75191-109">Geen</span><span class="sxs-lookup"><span data-stu-id="75191-109">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="75191-110">Aanvraagheaders</span><span class="sxs-lookup"><span data-stu-id="75191-110">Request headers</span></span>

| <span data-ttu-id="75191-111">Header</span><span class="sxs-lookup"><span data-stu-id="75191-111">Header</span></span> | <span data-ttu-id="75191-112">Waarde</span><span class="sxs-lookup"><span data-stu-id="75191-112">Value</span></span> |
|--------|-------|
|<span data-ttu-id="75191-113">Accepteren</span><span class="sxs-lookup"><span data-stu-id="75191-113">Accept</span></span>|<span data-ttu-id="75191-114">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="75191-114">application/json;odata=verbose</span></span>|
|<span data-ttu-id="75191-115">Content-Type</span><span class="sxs-lookup"><span data-stu-id="75191-115">Content-Type</span></span>|<span data-ttu-id="75191-116">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="75191-116">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="75191-117">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="75191-117">x-requestdigest</span></span>|<span data-ttu-id="75191-118">De juiste samenvatting voor deze site</span><span class="sxs-lookup"><span data-stu-id="75191-118">The appropriate digest for current site</span></span>|

## <a name="request-body"></a><span data-ttu-id="75191-119">Aanvraagtekst</span><span class="sxs-lookup"><span data-stu-id="75191-119">Request body</span></span>

|<span data-ttu-id="75191-120">Naam</span><span class="sxs-lookup"><span data-stu-id="75191-120">Name</span></span>    |<span data-ttu-id="75191-121">Type</span><span class="sxs-lookup"><span data-stu-id="75191-121">Type</span></span>   |<span data-ttu-id="75191-122">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="75191-122">Description</span></span> |
|--------|-------|------------|
|<span data-ttu-id="75191-123">_metadata</span><span class="sxs-lookup"><span data-stu-id="75191-123">_metadata</span></span>|  |<span data-ttu-id="75191-124">Stel de objectmeta in op de SPO.</span><span class="sxs-lookup"><span data-stu-id="75191-124">Set the object meta on the SPO.</span></span> <span data-ttu-id="75191-125">Gebruik altijd de waarde: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"}.</span><span class="sxs-lookup"><span data-stu-id="75191-125">Always use the value: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"}.</span></span> |
|<span data-ttu-id="75191-126">ContentTypeGroup</span><span class="sxs-lookup"><span data-stu-id="75191-126">ContentTypeGroup</span></span>|<span data-ttu-id="75191-127">string</span><span class="sxs-lookup"><span data-stu-id="75191-127">string</span></span>|<span data-ttu-id="75191-128">De groep van het gekoppelde inhoudstype die aan het model is gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="75191-128">The associated content type group associated with the model.</span></span> <span data-ttu-id="75191-129">Is standaard ingesteld op 'Typen intelligente documentinhoud'.</span><span class="sxs-lookup"><span data-stu-id="75191-129">Defaulted to "Intelligent Document Content Types".</span></span>|
|<span data-ttu-id="75191-130">ContentTypeName</span><span class="sxs-lookup"><span data-stu-id="75191-130">ContentTypeName</span></span>|<span data-ttu-id="75191-131">string</span><span class="sxs-lookup"><span data-stu-id="75191-131">string</span></span>|<span data-ttu-id="75191-132">De naam van het gekoppelde inhoudstype.</span><span class="sxs-lookup"><span data-stu-id="75191-132">The associated content type name.</span></span> <span data-ttu-id="75191-133">Het gemaakte modelbestand krijgt dezelfde naam.</span><span class="sxs-lookup"><span data-stu-id="75191-133">The created model file will have the same name.</span></span>|

## <a name="responses"></a><span data-ttu-id="75191-134">Reacties</span><span class="sxs-lookup"><span data-stu-id="75191-134">Responses</span></span>

| <span data-ttu-id="75191-135">Naam</span><span class="sxs-lookup"><span data-stu-id="75191-135">Name</span></span>   | <span data-ttu-id="75191-136">Type</span><span class="sxs-lookup"><span data-stu-id="75191-136">Type</span></span>  | <span data-ttu-id="75191-137">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="75191-137">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="75191-138">201 gemaakt</span><span class="sxs-lookup"><span data-stu-id="75191-138">201 Created</span></span>| |<span data-ttu-id="75191-139">Geslaagd</span><span class="sxs-lookup"><span data-stu-id="75191-139">Success</span></span>|

## <a name="examples"></a><span data-ttu-id="75191-140">Voorbeelden</span><span class="sxs-lookup"><span data-stu-id="75191-140">Examples</span></span>

### <a name="create-a-new-document-understanding-model-called-contoso-contract"></a><span data-ttu-id="75191-141">Een nieuw documentbegripmodel maken met de naam 'Contoso-contract'</span><span class="sxs-lookup"><span data-stu-id="75191-141">Create a new document understanding model called "Contoso Contract"</span></span>

#### <a name="sample-request"></a><span data-ttu-id="75191-142">Voorbeeldaanvraag</span><span class="sxs-lookup"><span data-stu-id="75191-142">Sample request</span></span>

```
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"
    },
    "ContentTypeGroup": "Intelligent Document Content Types",
    "ContentTypeName": "Contoso Contract",
}
```

#### <a name="sample-response"></a><span data-ttu-id="75191-143">Voorbeeldreactie</span><span class="sxs-lookup"><span data-stu-id="75191-143">Sample response</span></span>

<span data-ttu-id="75191-144">**Statuscode:** 201</span><span class="sxs-lookup"><span data-stu-id="75191-144">**Status code:** 201</span></span>

## <a name="see-also"></a><span data-ttu-id="75191-145">Zie ook</span><span class="sxs-lookup"><span data-stu-id="75191-145">See also</span></span>

[<span data-ttu-id="75191-146">REST API van Syntex-model voor documentbegrip</span><span class="sxs-lookup"><span data-stu-id="75191-146">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
