---
title: GetByTitle
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: m365initiative-syntex
localization_priority: Priority
description: Gebruik REST API om informatie over een SharePoint Syntex-documentbegripsmodel op te halen of bij te werken met behulp van de modeltitel.
ms.openlocfilehash: a6fbe9ba9d3f5240c7b775613f97b83bfa2caa50
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904245"
---
# <a name="getbytitle"></a><span data-ttu-id="8c127-103">GetByTitle</span><span class="sxs-lookup"><span data-stu-id="8c127-103">GetByTitle</span></span>

<span data-ttu-id="8c127-104">Ontvangt of werkt informatie bij over een SharePoint Syntex-model voor documentbegrip met behulp van de modeltitel (zie [voorbeeld](rest-getbytitle-method.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="8c127-104">Gets or updates information about a SharePoint Syntex document understanding model using the model title (see [example](rest-getbytitle-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="8c127-105">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="8c127-105">HTTP request</span></span>

```HTTP
GET /_api/machinelearning/models/getbytitle('{modelFileName') HTTP/1.1
```

<span data-ttu-id="8c127-106">Deze methode kan ook worden gebruikt voor het verwijderen van een model.</span><span class="sxs-lookup"><span data-stu-id="8c127-106">This same method can be used for deleting a model, too.</span></span>

```HTTP
DELETE /_api/machinelearning/models/getbytitle('{modelFileName') HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="8c127-107">URI-parameters</span><span class="sxs-lookup"><span data-stu-id="8c127-107">URI parameters</span></span>

|<span data-ttu-id="8c127-108">Naam</span><span class="sxs-lookup"><span data-stu-id="8c127-108">Name</span></span> |<span data-ttu-id="8c127-109">In</span><span class="sxs-lookup"><span data-stu-id="8c127-109">In</span></span> |<span data-ttu-id="8c127-110">Vereist</span><span class="sxs-lookup"><span data-stu-id="8c127-110">Required</span></span>|<span data-ttu-id="8c127-111">Type</span><span class="sxs-lookup"><span data-stu-id="8c127-111">Type</span></span>|<span data-ttu-id="8c127-112">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="8c127-112">Description</span></span>|
|-----|---|--------|----|-----------|
|<span data-ttu-id="8c127-113">modelFileName</span><span class="sxs-lookup"><span data-stu-id="8c127-113">modelFileName</span></span>|<span data-ttu-id="8c127-114">query</span><span class="sxs-lookup"><span data-stu-id="8c127-114">query</span></span>|<span data-ttu-id="8c127-115">Waar</span><span class="sxs-lookup"><span data-stu-id="8c127-115">True</span></span>|<span data-ttu-id="8c127-116">reeks</span><span class="sxs-lookup"><span data-stu-id="8c127-116">string</span></span>|<span data-ttu-id="8c127-117">Naam van het Syntex-modelbestand.</span><span class="sxs-lookup"><span data-stu-id="8c127-117">Name of the Syntex model file.</span></span>|

## <a name="request-headers"></a><span data-ttu-id="8c127-118">Aanvraagheaders</span><span class="sxs-lookup"><span data-stu-id="8c127-118">Request headers</span></span>

| <span data-ttu-id="8c127-119">Koptekst</span><span class="sxs-lookup"><span data-stu-id="8c127-119">Header</span></span> | <span data-ttu-id="8c127-120">Waarde</span><span class="sxs-lookup"><span data-stu-id="8c127-120">Value</span></span> |
|--------|-------|
|<span data-ttu-id="8c127-121">Accepteren</span><span class="sxs-lookup"><span data-stu-id="8c127-121">Accept</span></span>|<span data-ttu-id="8c127-122">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="8c127-122">application/json;odata=verbose</span></span>|

## <a name="request-body"></a><span data-ttu-id="8c127-123">Aanvraagtekst</span><span class="sxs-lookup"><span data-stu-id="8c127-123">Request body</span></span>

<span data-ttu-id="8c127-124">Voor GET hebt u geen aanvraagtekst nodig.</span><span class="sxs-lookup"><span data-stu-id="8c127-124">For GET, no request body is needed.</span></span>

## <a name="responses"></a><span data-ttu-id="8c127-125">Antwoorden</span><span class="sxs-lookup"><span data-stu-id="8c127-125">Responses</span></span>

| <span data-ttu-id="8c127-126">Naam</span><span class="sxs-lookup"><span data-stu-id="8c127-126">Name</span></span>   | <span data-ttu-id="8c127-127">Type</span><span class="sxs-lookup"><span data-stu-id="8c127-127">Type</span></span>  | <span data-ttu-id="8c127-128">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="8c127-128">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="8c127-129">200 OK</span><span class="sxs-lookup"><span data-stu-id="8c127-129">200 OK</span></span>| |<span data-ttu-id="8c127-130">Succes</span><span class="sxs-lookup"><span data-stu-id="8c127-130">Success</span></span>|

## <a name="examples"></a><span data-ttu-id="8c127-131">Voorbeelden</span><span class="sxs-lookup"><span data-stu-id="8c127-131">Examples</span></span>

### <a name="get-information-about-the-contoso-contract-model"></a><span data-ttu-id="8c127-132">Informatie over het Contoso-contractmodel verkrijgen</span><span class="sxs-lookup"><span data-stu-id="8c127-132">Get information about the Contoso Contract model</span></span>

<span data-ttu-id="8c127-133">In dit voorbeeld is de naam van het Syntex-model voor documentbegrip `Contoso Contract`.</span><span class="sxs-lookup"><span data-stu-id="8c127-133">In this sample, the name of the Syntex document understanding model is `Contoso Contract`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="8c127-134">Voorbeeldaanvraag</span><span class="sxs-lookup"><span data-stu-id="8c127-134">Sample request</span></span>

```HTTP
GET /_api/machinelearning/models/getbytitle('{Contoso Contract') HTTP/1.1
```

#### <a name="sample-response"></a><span data-ttu-id="8c127-135">Voorbeeldantwoord</span><span class="sxs-lookup"><span data-stu-id="8c127-135">Sample response</span></span>

<span data-ttu-id="8c127-136">**Statuscode:** 204</span><span class="sxs-lookup"><span data-stu-id="8c127-136">**Status code:** 204</span></span>

```HTTP
{
    "@odata.context": "https://contoso.sharepoint.com/sites/filerepository/_api/$metadata#models/$entity",
    "@odata.type": "#Microsoft.Office.Server.ContentCenter.SPMachineLearningModel",
    "@odata.id": "https://contoso.sharepoint.com/sites/filerepository/_api/machinelearning/models/getbyuniqueId('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc')",
    "@odata.etag": "\"7645e69d-21fb-4a24-a17a-9bdfa7cb63dc,111\"",
    "@odata.editLink": " https://contoso.sharepoint.com/sites/filerepository /_api/machinelearning/models/getbyuniqueId('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc')",
    "ConfidenceScore": "{\"trainingStatus\":{\"kind\":\"original\",\"ClassifierStatus\":{\"TrainingStatus\":\"success\",\"TimeStamp\":1611716640535},\"ExtractorsStatus\":[{\"TimeStamp\":1585175746775,\"ExtractorName\":\"Contract Name\",\"TrainingStatus\":\"success\"},{\"TimeStamp\":1586905975794,\"ExtractorName\":\"Client \",\"TrainingStatus\":\"success\"},{\"TimeStamp\":1586906061099,\"ExtractorName\":\"Contract Date\",\"TrainingStatus\":\"success\"},{\"TimeStamp\":1586907912388,\"ExtractorName\":\"Fee\",\"TrainingStatus\":\"success\"},{\"TimeStamp\":1611716640115,\"ExtractorName\":\"ServiceType\",\"TrainingStatus\":\"success\"}]},\"modelAccuracy\":{\"Classifier\":1,\"Extractors\":{\"Contract Name\":1,\"Client \":1,\"Contract Date\":1,\"Fee\":1,\"ServiceType\":1}},\"perSampleAccuracy\":{\"133\":{\"Classifier\":1,\"Extractors\":{\"ServiceType\":1}},\"249\":{\"Classifier\":1,\"Extractors\":{\"ServiceType\":1}},\"252\":{\"Classifier\":1,\"Extractors\":{\"ServiceType\":1}},\"253\":{\"Classifier\":1,\"Extractors\":{\"ServiceType\":1}},\"254\":{\"Classifier\":1,\"Extractors\":{\"ServiceType\":1}},\"255\":{\"Classifier\":1,\"Extractors\":{\"ServiceType\":1}},\"256\":{\"Extractors\":{\"ServiceType\":1}},\"257\":{\"Extractors\":{\"ServiceType\":1}}},\"perSamplePrediction\":{\"133\":{\"Extractors\":{\"ServiceType\":[]}},\"249\":{\"Extractors\":{\"ServiceType\":[\"Writing\"]}},\"252\":{\"Extractors\":{\"ServiceType\":[\"Catering\"]}},\"253\":{\"Extractors\":{\"ServiceType\":[\"Design\"]}},\"254\":{\"Extractors\":{\"ServiceType\":[\"Marketing\"]}},\"255\":{\"Extractors\":{\"ServiceType\":[\"Financial Planning\"]}},\"256\":{\"Extractors\":{\"ServiceType\":[\"Writing\"]}},\"257\":{\"Extractors\":{\"ServiceType\":[\"Writing\"]}}},\"trainingFailures\":{}}",
    "ContentTypeGroup": "Intelligent Document Content Types",
    "ContentTypeId": "0x01010083DF84D4F59BBD4CB06F075AA81F58AA",
    "ContentTypeName": "Contoso Contract",
    "Created": "2020-03-25T22:04:04Z",
    "CreatedBy": "i:0#.f|membership|meganb@contoso.com",
    "DriveId": "b!O-aG9qer5UiXx2jEwd8pL0221maIb9lNs9tH5vAMU-h2NuHxlYUiTJyiwKQHZobK",
    "Explanations": "{\"Classifier\":[{\"id\":\"8122ac1d-8fcb-4705-8872-2825cbf05bfe\",\"kind\":\"dictionaryFeature\",\"name\":\"agreement\",\"active\":true,\"nGrams\":[\"CONSULTING AGREEMENT\",\"SERVICES AGREEMENT\"],\"caseSensitive\":false,\"ignoreDigitIdentity\":false,\"ignoreLetterIdentity\":false},{\"id\":\"af83bea8-bc53-4e93-a3da-f1e697eb6bef\",\"kind\":\"modelFeature\",\"name\":\"Contract Name\",\"active\":true,\"modelReference\":\"Contract Name\",\"conceptId\":\"841d0dcf-7f1d-4a39-931c-53923d10c346\"},{\"id\":\"e3734994-9e34-40e3-82c7-bb6c7bc5a0c3\",\"kind\":\"modelFeature\",\"name\":\"Client \",\"active\":true,\"modelReference\":\"Client \",\"conceptId\":\"8b8490d0-9a09-4c16-bcff-59ce62e05c28\"},{\"id\":\"7c93e7fe-cbfb-47ee-8cca-46ecdf5f628f\",\"kind\":\"modelFeature\",\"name\":\"Contract Date\",\"active\":true,\"modelReference\":\"Contract Date\",\"conceptId\":\"6ba58918-e2f0-4685-9080-98ec4c3adc7c\"},{\"id\":\"5cc85b62-148a-4b07-9155-d9fb7cebb6d0\",\"kind\":\"modelFeature\",\"name\":\"Fee\",\"active\":true,\"modelReference\":\"Fee\",\"conceptId\":\"9c7f764d-afd2-49cd-aaa2-e9407156bfb3\"},{\"id\":\"0f8a23a6-c744-4cae-82bd-d836332ceb56\",\"kind\":\"modelFeature\",\"name\":\"ServiceType\",\"active\":true,\"modelReference\":\"ServiceType\",\"conceptId\":\"4aa9f2fe-cfab-49f8-86b1-11646c79cdbf\"}],\"Extractors\":{\"Contract Name\":[{\"id\":\"8804fbeb-bcf8-44c0-8ade-3fc65496037f\",\"kind\":\"dictionaryFeature\",\"name\":\"before\",\"active\":true,\"nGrams\":[\"- AND -\"],\"caseSensitive\":false,\"ignoreDigitIdentity\":false,\"ignoreLetterIdentity\":false}],\"Client \":[{\"id\":\"606c56de-9e71-42ef-8ec6-f0bbf351d673\",\"kind\":\"dictionaryFeature\",\"name\":\"start\",\"active\":true,\"nGrams\":[\"BETWEEN:\"],\"caseSensitive\":false,\"ignoreDigitIdentity\":false,\"ignoreLetterIdentity\":false},{\"id\":\"334e6df5-e076-40db-a47b-f11ceec7af9a\",\"kind\":\"dictionaryFeature\",\"name\":\"after\",\"active\":true,\"nGrams\":[\"of\"],\"caseSensitive\":false,\"ignoreDigitIdentity\":false,\"ignoreLetterIdentity\":false},{\"id\":\"bccefd2e-88a4-406c-aa9d-81d508bbafb3\",\"kind\":\"proximityFeature\",\"name\":\"prox\",\"active\":true,\"patterns\":[[{\"id\":\"606c56de-9e71-42ef-8ec6-f0bbf351d673\",\"kind\":\"proximityFeatureReference\"},{\"kind\":\"proximityTokenRange\",\"minCount\":1,\"maxCount\":6},{\"id\":\"334e6df5-e076-40db-a47b-f11ceec7af9a\",\"kind\":\"proximityFeatureReference\"}]]}],\"Contract Date\":[{\"id\":\"fabe1ed3-07af-4dc6-852d-fe9521c64801\",\"kind\":\"dictionaryFeature\",\"name\":\"dated\",\"active\":true,\"nGrams\":[\"dated\"],\"caseSensitive\":false,\"ignoreDigitIdentity\":false,\"ignoreLetterIdentity\":false},{\"id\":\"983da7b8-51d7-4a85-9644-007b488fce0b\",\"kind\":\"dictionaryFeature\",\"name\":\"betw\",\"active\":true,\"nGrams\":[\"between\"],\"caseSensitive\":false,\"ignoreDigitIdentity\":false,\"ignoreLetterIdentity\":false}],\"Fee\":[{\"id\":\"f4cf89dc-64d1-49a1-9be4-41debda251b6\",\"kind\":\"dictionaryFeature\",\"name\":\"flat fee of \",\"active\":true,\"nGrams\":[\"flat fee of $\",\"flat fee of $$\"],\"caseSensitive\":false,\"ignoreDigitIdentity\":false,\"ignoreLetterIdentity\":false}],\"ServiceType\":[{\"id\":\"c04408f5-ce14-4eb0-81d0-f72ea9fa7e83\",\"kind\":\"dictionaryFeature\",\"name\":\"Before label\",\"active\":true,\"nGrams\":[\"will provide \"],\"caseSensitive\":false,\"ignoreDigitIdentity\":false,\"ignoreLetterIdentity\":false},{\"id\":\"ea94fa7f-e41b-4e09-a484-355912bfbdff\",\"kind\":\"dictionaryFeature\",\"name\":\"After label\",\"active\":true,\"nGrams\":[\"services for \"],\"caseSensitive\":false,\"ignoreDigitIdentity\":false,\"ignoreLetterIdentity\":false}]}}",
    "ID": 16,
    "LastTrained": "2021-01-27T03:04:00Z",
    "ListID": "f1e13676-8595-4c22-9ca2-c0a4076686ca",
    "ModelSettings": null,
    "ModelType": 2,
    "Modified": "2021-01-27T03:05:04Z",
    "ModifiedBy": "i:0#.f|membership|kevinche@contoso.com",
    "ObjectId": "01ZBWEM5E54ZCXN6ZBERFKC6U336T4WY64",
    "PublicationType": 0,
    "Schemas": "{\"Extractors\":{\"Contract Name\":{\"concepts\":{\"841d0dcf-7f1d-4a39-931c-53923d10c346\":{\"name\":\"Contract Name\"}},\"relationships\":[]},\"Client \":{\"concepts\":{\"8b8490d0-9a09-4c16-bcff-59ce62e05c28\":{\"name\":\"Client \"}},\"relationships\":[]},\"Contract Date\":{\"concepts\":{\"6ba58918-e2f0-4685-9080-98ec4c3adc7c\":{\"name\":\"Contract Date\"}},\"relationships\":[]},\"Fee\":{\"concepts\":{\"9c7f764d-afd2-49cd-aaa2-e9407156bfb3\":{\"name\":\"Fee\"}},\"relationships\":[]},\"ServiceType\":{\"concepts\":{\"4aa9f2fe-cfab-49f8-86b1-11646c79cdbf\":{\"name\":\"ServiceType\",\"termSetId\":\"76c12efb-5173-4982-ae9b-5f9e37187171\"}},\"relationships\":[]}}}",
    "SourceUrl": null,
    "UniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc"
}
```

### <a name="get-and-delete-the-contoso-contract-model-by-name"></a><span data-ttu-id="8c127-137">Het Contoso-contractmodel op naam ophalen en verwijderen</span><span class="sxs-lookup"><span data-stu-id="8c127-137">Get and delete the Contoso Contract model by name</span></span>

<span data-ttu-id="8c127-138">In dit voorbeeld is de naam van het model voor documentbegrip van het Contoso Contract `Contoso Contract`.</span><span class="sxs-lookup"><span data-stu-id="8c127-138">In this sample, the name of the Contoso Contract document understanding model is `Contoso Contract`.</span></span>

##### <a name="sample-request"></a><span data-ttu-id="8c127-139">Voorbeeldaanvraag</span><span class="sxs-lookup"><span data-stu-id="8c127-139">Sample request</span></span>

```HTTP
DELETE /_api/machinelearning/models/getbytitle('{Contoso Contract') HTTP/1.1
```

## <a name="see-also"></a><span data-ttu-id="8c127-140">Zie ook</span><span class="sxs-lookup"><span data-stu-id="8c127-140">See also</span></span>

[<span data-ttu-id="8c127-141">REST API van Syntex-model voor documentbegrip</span><span class="sxs-lookup"><span data-stu-id="8c127-141">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)