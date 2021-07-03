---
title: Classificatieaanvraag maken
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
description: Gebruik REST API om een aanvraag te maken om een of meer bestanden te classificeren met behulp van een getraind model voor documentbegrip.
ms.openlocfilehash: b1022787d6e11ebe36c88ecd29936a777289dd74
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287231"
---
# <a name="create-classification-request"></a><span data-ttu-id="46835-103">Classificatieaanvraag maken</span><span class="sxs-lookup"><span data-stu-id="46835-103">Create classification request</span></span>

<span data-ttu-id="46835-104">Hiermee wordt een aanvraag gemaakt om een of meer bestanden te classificeren met behulp van het toegepaste model voor documentbegrip (zie [voorbeeld](rest-createclassificationrequest.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="46835-104">Creates a request to classify one or more files using the applied document understanding model (see [example](rest-createclassificationrequest.md#examples)).</span></span>

<span data-ttu-id="46835-105">De SharePoint Online (en SharePoint 2016 en hoger on-premises) REST-service ondersteunt het combineren van meerdere aanvragen.</span><span class="sxs-lookup"><span data-stu-id="46835-105">The SharePoint Online (and SharePoint 2016 and later on-premises) REST service supports combining multiple requests.</span></span> <span data-ttu-id="46835-106">Aanvragen worden gecombineerd in één oproep naar de service met behulp van de queryoptie OData-$batch.</span><span class="sxs-lookup"><span data-stu-id="46835-106">Requests are combined into a single call to the service by using the OData $batch query option.</span></span> <span data-ttu-id="46835-107">Deze methode kan worden gebruikt om classificatiewerkitems voor honderden documenten tegelijk in de wachtrij te plaatsen.</span><span class="sxs-lookup"><span data-stu-id="46835-107">This method can be used to enqueue classification work items for hundreds of documents at one time.</span></span>

## <a name="http-request"></a><span data-ttu-id="46835-108">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="46835-108">HTTP request</span></span>

```http
POST /_api/machinelearning/workItems HTTP/1.1
```
## <a name="uri-parameters"></a><span data-ttu-id="46835-109">URI-parameters</span><span class="sxs-lookup"><span data-stu-id="46835-109">URI Parameters</span></span>

<span data-ttu-id="46835-110">Geen</span><span class="sxs-lookup"><span data-stu-id="46835-110">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="46835-111">Aanvraagheaders</span><span class="sxs-lookup"><span data-stu-id="46835-111">Request headers</span></span>

| <span data-ttu-id="46835-112">Header</span><span class="sxs-lookup"><span data-stu-id="46835-112">Header</span></span> | <span data-ttu-id="46835-113">Waarde</span><span class="sxs-lookup"><span data-stu-id="46835-113">Value</span></span> |
|--------|-------|
|<span data-ttu-id="46835-114">Accepteren</span><span class="sxs-lookup"><span data-stu-id="46835-114">Accept</span></span>|<span data-ttu-id="46835-115">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="46835-115">application/json;odata=verbose</span></span>|
|<span data-ttu-id="46835-116">Content-Type</span><span class="sxs-lookup"><span data-stu-id="46835-116">Content-Type</span></span>|<span data-ttu-id="46835-117">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="46835-117">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="46835-118">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="46835-118">x-requestdigest</span></span>|<span data-ttu-id="46835-119">De juiste samenvatting voor deze site</span><span class="sxs-lookup"><span data-stu-id="46835-119">The appropriate digest for current site</span></span>|

## <a name="request-body"></a><span data-ttu-id="46835-120">Aanvraagtekst</span><span class="sxs-lookup"><span data-stu-id="46835-120">Request body</span></span>

|<span data-ttu-id="46835-121">Naam</span><span class="sxs-lookup"><span data-stu-id="46835-121">Name</span></span>    |<span data-ttu-id="46835-122">Type</span><span class="sxs-lookup"><span data-stu-id="46835-122">Type</span></span>   |<span data-ttu-id="46835-123">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="46835-123">Description</span></span> |
|--------|-------|------------|
|<span data-ttu-id="46835-124">_metagegevens</span><span class="sxs-lookup"><span data-stu-id="46835-124">_metadata</span></span>|<span data-ttu-id="46835-125">reeks</span><span class="sxs-lookup"><span data-stu-id="46835-125">string</span></span> |<span data-ttu-id="46835-126">Stel de objectmeta in op de SPO.</span><span class="sxs-lookup"><span data-stu-id="46835-126">Set the object meta on the SPO.</span></span> <span data-ttu-id="46835-127">Gebruik altijd de waarde: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningWorkItemEntityData"}.</span><span class="sxs-lookup"><span data-stu-id="46835-127">Always use the value: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningWorkItemEntityData"}.</span></span> |
|<span data-ttu-id="46835-128">TargetSiteId</span><span class="sxs-lookup"><span data-stu-id="46835-128">TargetSiteId</span></span>|<span data-ttu-id="46835-129">guid</span><span class="sxs-lookup"><span data-stu-id="46835-129">guid</span></span>|<span data-ttu-id="46835-130">De site-id waar het te classificeren bestand zich bevindt.</span><span class="sxs-lookup"><span data-stu-id="46835-130">The id of the site where the file to classify is located.</span></span>|
|<span data-ttu-id="46835-131">TargetWebId</span><span class="sxs-lookup"><span data-stu-id="46835-131">TargetWebId</span></span>|<span data-ttu-id="46835-132">guid</span><span class="sxs-lookup"><span data-stu-id="46835-132">guid</span></span>|<span data-ttu-id="46835-133">De web-id waar het te classificeren bestand zich bevindt.</span><span class="sxs-lookup"><span data-stu-id="46835-133">The id of the web where the file to classify is located.</span></span>|
|<span data-ttu-id="46835-134">TargetUniqueId</span><span class="sxs-lookup"><span data-stu-id="46835-134">TargetUniqueId</span></span>|<span data-ttu-id="46835-135">guid</span><span class="sxs-lookup"><span data-stu-id="46835-135">guid</span></span>|<span data-ttu-id="46835-136">De id van het bestand dat moet worden geclassificeerd.</span><span class="sxs-lookup"><span data-stu-id="46835-136">The id of the file to classify.</span></span>|

## <a name="responses"></a><span data-ttu-id="46835-137">Antwoorden</span><span class="sxs-lookup"><span data-stu-id="46835-137">Responses</span></span>

| <span data-ttu-id="46835-138">Naam</span><span class="sxs-lookup"><span data-stu-id="46835-138">Name</span></span>   | <span data-ttu-id="46835-139">Type</span><span class="sxs-lookup"><span data-stu-id="46835-139">Type</span></span>  | <span data-ttu-id="46835-140">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="46835-140">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="46835-141">201 gemaakt</span><span class="sxs-lookup"><span data-stu-id="46835-141">201 Created</span></span>| |<span data-ttu-id="46835-142">Geslaagd</span><span class="sxs-lookup"><span data-stu-id="46835-142">Success</span></span>|

## <a name="examples"></a><span data-ttu-id="46835-143">Voorbeelden</span><span class="sxs-lookup"><span data-stu-id="46835-143">Examples</span></span>

### <a name="enqueue-a-request-to-classify-a-file-of-id-e6cff8b7-c90c-4564-b5b8-033449090932"></a><span data-ttu-id="46835-144">Een verzoek in de wachtrij plaatsen om een bestand met id 'e6cff8b7-c90c-4564-b5b8-033449090932' te classificeren</span><span class="sxs-lookup"><span data-stu-id="46835-144">Enqueue a request to classify a file of id "e6cff8b7-c90c-4564-b5b8-033449090932"</span></span>

#### <a name="sample-request"></a><span data-ttu-id="46835-145">Voorbeeldaanvraag</span><span class="sxs-lookup"><span data-stu-id="46835-145">Sample request</span></span>

```JSON
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningWorkItemEntityData"
    },
    "TargetSiteId": "f686e63b-aba7-48e5-97c7-68c4c1df292f",
    "TargetWebId": "66d6b64d-6f88-4dd9-b3db-47e6f00c53e8",
    "TargetUniqueId": "e6cff8b7-c90c-4564-b5b8-033449090932"
}
```

#### <a name="sample-response"></a><span data-ttu-id="46835-146">Voorbeeldreactie</span><span class="sxs-lookup"><span data-stu-id="46835-146">Sample response</span></span>

<span data-ttu-id="46835-147">**Statuscode:** 201</span><span class="sxs-lookup"><span data-stu-id="46835-147">**Status code:** 201</span></span>

## <a name="see-also"></a><span data-ttu-id="46835-148">Zie ook</span><span class="sxs-lookup"><span data-stu-id="46835-148">See also</span></span>

[<span data-ttu-id="46835-149">REST API van Syntex-model voor documentbegrip</span><span class="sxs-lookup"><span data-stu-id="46835-149">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
