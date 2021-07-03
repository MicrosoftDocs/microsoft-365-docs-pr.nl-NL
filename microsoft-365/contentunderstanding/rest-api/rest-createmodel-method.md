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
ms.openlocfilehash: 1c5bd84c777774edc1aa0c2419181f7b84aa4707
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287243"
---
# <a name="create-model"></a><span data-ttu-id="304c4-103">Model maken</span><span class="sxs-lookup"><span data-stu-id="304c4-103">Create model</span></span>

<span data-ttu-id="304c4-104">Een model en het gekoppelde inhoudstype maken.</span><span class="sxs-lookup"><span data-stu-id="304c4-104">Creates a model and its associated content type.</span></span> <span data-ttu-id="304c4-105">Hiermee wordt het model alleen gemaakt.</span><span class="sxs-lookup"><span data-stu-id="304c4-105">Note that this only creates the model.</span></span> <span data-ttu-id="304c4-106">Het moet nog wel worden getraind in het inhoudscentrum (zie [voorbeeld](rest-createmodel-method.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="304c4-106">It will still need to be trained in the content center (see [example](rest-createmodel-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="304c4-107">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="304c4-107">HTTP request</span></span>

```http
POST /_api/machinelearning/models HTTP/1.1
```
## <a name="uri-parameters"></a><span data-ttu-id="304c4-108">URI-parameters</span><span class="sxs-lookup"><span data-stu-id="304c4-108">URI Parameters</span></span>

<span data-ttu-id="304c4-109">Geen</span><span class="sxs-lookup"><span data-stu-id="304c4-109">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="304c4-110">Aanvraagheaders</span><span class="sxs-lookup"><span data-stu-id="304c4-110">Request headers</span></span>

| <span data-ttu-id="304c4-111">Header</span><span class="sxs-lookup"><span data-stu-id="304c4-111">Header</span></span> | <span data-ttu-id="304c4-112">Waarde</span><span class="sxs-lookup"><span data-stu-id="304c4-112">Value</span></span> |
|--------|-------|
|<span data-ttu-id="304c4-113">Accepteren</span><span class="sxs-lookup"><span data-stu-id="304c4-113">Accept</span></span>|<span data-ttu-id="304c4-114">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="304c4-114">application/json;odata=verbose</span></span>|
|<span data-ttu-id="304c4-115">Content-Type</span><span class="sxs-lookup"><span data-stu-id="304c4-115">Content-Type</span></span>|<span data-ttu-id="304c4-116">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="304c4-116">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="304c4-117">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="304c4-117">x-requestdigest</span></span>|<span data-ttu-id="304c4-118">De juiste samenvatting voor deze site</span><span class="sxs-lookup"><span data-stu-id="304c4-118">The appropriate digest for current site</span></span>|

## <a name="request-body"></a><span data-ttu-id="304c4-119">Aanvraagtekst</span><span class="sxs-lookup"><span data-stu-id="304c4-119">Request body</span></span>

|<span data-ttu-id="304c4-120">Naam</span><span class="sxs-lookup"><span data-stu-id="304c4-120">Name</span></span>    |<span data-ttu-id="304c4-121">Type</span><span class="sxs-lookup"><span data-stu-id="304c4-121">Type</span></span>   |<span data-ttu-id="304c4-122">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="304c4-122">Description</span></span> |
|--------|-------|------------|
|<span data-ttu-id="304c4-123">_metagegevens</span><span class="sxs-lookup"><span data-stu-id="304c4-123">_metadata</span></span>|  |<span data-ttu-id="304c4-124">Stel de objectmeta in op de SPO.</span><span class="sxs-lookup"><span data-stu-id="304c4-124">Set the object meta on the SPO.</span></span> <span data-ttu-id="304c4-125">Gebruik altijd de waarde: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"}.</span><span class="sxs-lookup"><span data-stu-id="304c4-125">Always use the value: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"}.</span></span> |
|<span data-ttu-id="304c4-126">ContentTypeGroup</span><span class="sxs-lookup"><span data-stu-id="304c4-126">ContentTypeGroup</span></span>|<span data-ttu-id="304c4-127">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="304c4-127">string</span></span>|<span data-ttu-id="304c4-128">De groep van het gekoppelde inhoudstype die aan het model is gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="304c4-128">The associated content type group associated with the model.</span></span> <span data-ttu-id="304c4-129">Is standaard ingesteld op 'Typen intelligente documentinhoud'.</span><span class="sxs-lookup"><span data-stu-id="304c4-129">Defaulted to "Intelligent Document Content Types".</span></span>|
|<span data-ttu-id="304c4-130">ContentTypeName</span><span class="sxs-lookup"><span data-stu-id="304c4-130">ContentTypeName</span></span>|<span data-ttu-id="304c4-131">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="304c4-131">string</span></span>|<span data-ttu-id="304c4-132">De naam van het gekoppelde inhoudstype.</span><span class="sxs-lookup"><span data-stu-id="304c4-132">The associated content type name.</span></span> <span data-ttu-id="304c4-133">Het gemaakte modelbestand krijgt dezelfde naam.</span><span class="sxs-lookup"><span data-stu-id="304c4-133">The created model file will have the same name.</span></span>|

## <a name="responses"></a><span data-ttu-id="304c4-134">Antwoorden</span><span class="sxs-lookup"><span data-stu-id="304c4-134">Responses</span></span>

| <span data-ttu-id="304c4-135">Naam</span><span class="sxs-lookup"><span data-stu-id="304c4-135">Name</span></span>   | <span data-ttu-id="304c4-136">Type</span><span class="sxs-lookup"><span data-stu-id="304c4-136">Type</span></span>  | <span data-ttu-id="304c4-137">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="304c4-137">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="304c4-138">201 gemaakt</span><span class="sxs-lookup"><span data-stu-id="304c4-138">201 Created</span></span>| |<span data-ttu-id="304c4-139">Geslaagd</span><span class="sxs-lookup"><span data-stu-id="304c4-139">Success</span></span>|

## <a name="examples"></a><span data-ttu-id="304c4-140">Voorbeelden</span><span class="sxs-lookup"><span data-stu-id="304c4-140">Examples</span></span>

### <a name="create-a-new-document-understanding-model-called-contoso-contract"></a><span data-ttu-id="304c4-141">Een nieuw documentbegripmodel maken met de naam 'Contoso-contract'</span><span class="sxs-lookup"><span data-stu-id="304c4-141">Create a new document understanding model called "Contoso Contract"</span></span>

#### <a name="sample-request"></a><span data-ttu-id="304c4-142">Voorbeeldaanvraag</span><span class="sxs-lookup"><span data-stu-id="304c4-142">Sample request</span></span>

```json
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"
    },
    "ContentTypeGroup": "Intelligent Document Content Types",
    "ContentTypeName": "Contoso Contract"
}
```

#### <a name="sample-response"></a><span data-ttu-id="304c4-143">Voorbeeldreactie</span><span class="sxs-lookup"><span data-stu-id="304c4-143">Sample response</span></span>

<span data-ttu-id="304c4-144">**Statuscode:** 201</span><span class="sxs-lookup"><span data-stu-id="304c4-144">**Status code:** 201</span></span>

## <a name="see-also"></a><span data-ttu-id="304c4-145">Zie ook</span><span class="sxs-lookup"><span data-stu-id="304c4-145">See also</span></span>

[<span data-ttu-id="304c4-146">REST API van Syntex-model voor documentbegrip</span><span class="sxs-lookup"><span data-stu-id="304c4-146">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
