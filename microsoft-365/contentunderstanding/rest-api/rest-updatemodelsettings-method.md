---
title: UpdateModelSettings
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
description: Gebruik REST API om de beschikbare modelinstellingen bij te werken voor een SharePoint Syntex-model voor documentbegrip.
ms.openlocfilehash: cd288812044f3b02839c3c11c321947bd02cccaa
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177163"
---
# <a name="updatemodelsettings"></a><span data-ttu-id="c23e7-103">UpdateModelSettings</span><span class="sxs-lookup"><span data-stu-id="c23e7-103">UpdateModelSettings</span></span>

<span data-ttu-id="c23e7-104">Hiermee worden de beschikbare modelinstellingen (gekoppeld retentielabel en modelbeschrijving) bijgewerkt voor een SharePoint Syntex-model voor documentbegrip (zie [voorbeeld](rest-updatemodelsettings-method.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="c23e7-104">Updates available models settings (associated retention label and model description) for a SharePoint Syntex document understanding model (see [example](rest-updatemodelsettings-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="c23e7-105">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="c23e7-105">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/models/getbytitle('{modelFileName}')/updatemodelsettings HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="c23e7-106">URI-parameters</span><span class="sxs-lookup"><span data-stu-id="c23e7-106">URI parameters</span></span>

|<span data-ttu-id="c23e7-107">Naam</span><span class="sxs-lookup"><span data-stu-id="c23e7-107">Name</span></span> |<span data-ttu-id="c23e7-108">In</span><span class="sxs-lookup"><span data-stu-id="c23e7-108">In</span></span> |<span data-ttu-id="c23e7-109">Vereist</span><span class="sxs-lookup"><span data-stu-id="c23e7-109">Required</span></span>|<span data-ttu-id="c23e7-110">Type</span><span class="sxs-lookup"><span data-stu-id="c23e7-110">Type</span></span>|<span data-ttu-id="c23e7-111">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="c23e7-111">Description</span></span>|
|-----|---|--------|----|-----------|
|<span data-ttu-id="c23e7-112">modelFileName</span><span class="sxs-lookup"><span data-stu-id="c23e7-112">modelFileName</span></span>|<span data-ttu-id="c23e7-113">query</span><span class="sxs-lookup"><span data-stu-id="c23e7-113">query</span></span>|<span data-ttu-id="c23e7-114">Waar</span><span class="sxs-lookup"><span data-stu-id="c23e7-114">True</span></span>|<span data-ttu-id="c23e7-115">reeks</span><span class="sxs-lookup"><span data-stu-id="c23e7-115">string</span></span>|<span data-ttu-id="c23e7-116">Naam van het Syntex-modelbestand.</span><span class="sxs-lookup"><span data-stu-id="c23e7-116">Name of the Syntex model file.</span></span>|

## <a name="request-headers"></a><span data-ttu-id="c23e7-117">Aanvraagheaders</span><span class="sxs-lookup"><span data-stu-id="c23e7-117">Request headers</span></span>

| <span data-ttu-id="c23e7-118">Header</span><span class="sxs-lookup"><span data-stu-id="c23e7-118">Header</span></span> | <span data-ttu-id="c23e7-119">Waarde</span><span class="sxs-lookup"><span data-stu-id="c23e7-119">Value</span></span> |
|--------|-------|
|<span data-ttu-id="c23e7-120">Accepteren</span><span class="sxs-lookup"><span data-stu-id="c23e7-120">Accept</span></span>|<span data-ttu-id="c23e7-121">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="c23e7-121">application/json;odata=verbose</span></span>|
|<span data-ttu-id="c23e7-122">Content-Type</span><span class="sxs-lookup"><span data-stu-id="c23e7-122">Content-Type</span></span>|<span data-ttu-id="c23e7-123">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="c23e7-123">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="c23e7-124">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="c23e7-124">x-requestdigest</span></span>|<span data-ttu-id="c23e7-125">De juiste samenvatting voor de huidige site.</span><span class="sxs-lookup"><span data-stu-id="c23e7-125">The appropriate digest for the current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="c23e7-126">Aanvraagtekst</span><span class="sxs-lookup"><span data-stu-id="c23e7-126">Request body</span></span>

|<span data-ttu-id="c23e7-127">Naam</span><span class="sxs-lookup"><span data-stu-id="c23e7-127">Name</span></span>    |<span data-ttu-id="c23e7-128">Type</span><span class="sxs-lookup"><span data-stu-id="c23e7-128">Type</span></span>   |<span data-ttu-id="c23e7-129">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="c23e7-129">Description</span></span> |
|--------|-------|-------|
|<span data-ttu-id="c23e7-130">ModelSettings</span><span class="sxs-lookup"><span data-stu-id="c23e7-130">ModelSettings</span></span>|<span data-ttu-id="c23e7-131">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="c23e7-131">string</span></span>|<span data-ttu-id="c23e7-132">JSON van modelinstellingen.</span><span class="sxs-lookup"><span data-stu-id="c23e7-132">JSON of model settings.</span></span>|
|<span data-ttu-id="c23e7-133">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="c23e7-133">Description</span></span>|<span data-ttu-id="c23e7-134">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="c23e7-134">string</span></span>|<span data-ttu-id="c23e7-135">De beschrijving van het model.</span><span class="sxs-lookup"><span data-stu-id="c23e7-135">The model description.</span></span>|
|<span data-ttu-id="c23e7-136">RetentionLabel</span><span class="sxs-lookup"><span data-stu-id="c23e7-136">RetentionLabel</span></span>| |<span data-ttu-id="c23e7-137">Info voor het bijbehorende label (label-id en naam).</span><span class="sxs-lookup"><span data-stu-id="c23e7-137">Info for the associated label (label ID and name).</span></span>|

## <a name="responses"></a><span data-ttu-id="c23e7-138">Antwoorden</span><span class="sxs-lookup"><span data-stu-id="c23e7-138">Responses</span></span>

| <span data-ttu-id="c23e7-139">Naam</span><span class="sxs-lookup"><span data-stu-id="c23e7-139">Name</span></span>   | <span data-ttu-id="c23e7-140">Type</span><span class="sxs-lookup"><span data-stu-id="c23e7-140">Type</span></span>  | <span data-ttu-id="c23e7-141">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="c23e7-141">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="c23e7-142">200 OK</span><span class="sxs-lookup"><span data-stu-id="c23e7-142">200 OK</span></span>| |<span data-ttu-id="c23e7-143">Succes</span><span class="sxs-lookup"><span data-stu-id="c23e7-143">Success</span></span>|

## <a name="examples"></a><span data-ttu-id="c23e7-144">Voorbeelden</span><span class="sxs-lookup"><span data-stu-id="c23e7-144">Examples</span></span>

### <a name="update-model-settings-for-contoso-contract"></a><span data-ttu-id="c23e7-145">Modelinstellingen bijwerken voor Contoso-contract</span><span class="sxs-lookup"><span data-stu-id="c23e7-145">Update model settings for Contoso Contract</span></span>

<span data-ttu-id="c23e7-146">In dit voorbeeld worden de modelbeschrijving en het retentielabel Standaard bewaring bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="c23e7-146">In this example, the model description and "Standard Hold" retention label are updated.</span></span> <span data-ttu-id="c23e7-147">De id van het retentielabel is `27c5fcba-abfd-4c34-823d-0b4a48f7ffe6`.</span><span class="sxs-lookup"><span data-stu-id="c23e7-147">The ID of the retention label is `27c5fcba-abfd-4c34-823d-0b4a48f7ffe6`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="c23e7-148">Voorbeeldaanvraag</span><span class="sxs-lookup"><span data-stu-id="c23e7-148">Sample request</span></span>

```HTTP
{
    "ModelSettings": "{\"Description\":\"This model is used to set files classified as Contoso Contracts with a standard hold retention.\", \"RetentionLabel\":{\"Id\":\"27c5fcba-abfd-4c34-823d-0b4a48f7ffe6\",\"Name\":\"Standard Hold\"}}"
}

```

#### <a name="sample-response"></a><span data-ttu-id="c23e7-149">Voorbeeldantwoord</span><span class="sxs-lookup"><span data-stu-id="c23e7-149">Sample response</span></span>

<span data-ttu-id="c23e7-150">**Statuscode:** 200</span><span class="sxs-lookup"><span data-stu-id="c23e7-150">**Status code:** 200</span></span>

## <a name="see-also"></a><span data-ttu-id="c23e7-151">Zie ook</span><span class="sxs-lookup"><span data-stu-id="c23e7-151">See also</span></span>

[<span data-ttu-id="c23e7-152">REST API van Syntex-model voor documentbegrip</span><span class="sxs-lookup"><span data-stu-id="c23e7-152">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
