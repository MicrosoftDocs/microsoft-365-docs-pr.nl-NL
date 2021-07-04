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
ms.openlocfilehash: c75f669913f16233c6015230a60643cf86f33f5a
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288645"
---
# <a name="updatemodelsettings"></a><span data-ttu-id="3cb7b-103">UpdateModelSettings</span><span class="sxs-lookup"><span data-stu-id="3cb7b-103">UpdateModelSettings</span></span>

<span data-ttu-id="3cb7b-104">Hiermee worden de beschikbare modelinstellingen (gekoppeld retentielabel en modelbeschrijving) bijgewerkt voor een SharePoint Syntex-model voor documentbegrip (zie [voorbeeld](rest-updatemodelsettings-method.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="3cb7b-104">Updates available models settings (associated retention label and model description) for a SharePoint Syntex document understanding model (see [example](rest-updatemodelsettings-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="3cb7b-105">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="3cb7b-105">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/models/getbytitle('{modelFileName}')/updatemodelsettings HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="3cb7b-106">URI-parameters</span><span class="sxs-lookup"><span data-stu-id="3cb7b-106">URI parameters</span></span>

|<span data-ttu-id="3cb7b-107">Naam</span><span class="sxs-lookup"><span data-stu-id="3cb7b-107">Name</span></span> |<span data-ttu-id="3cb7b-108">In</span><span class="sxs-lookup"><span data-stu-id="3cb7b-108">In</span></span> |<span data-ttu-id="3cb7b-109">Vereist</span><span class="sxs-lookup"><span data-stu-id="3cb7b-109">Required</span></span>|<span data-ttu-id="3cb7b-110">Type</span><span class="sxs-lookup"><span data-stu-id="3cb7b-110">Type</span></span>|<span data-ttu-id="3cb7b-111">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="3cb7b-111">Description</span></span>|
|-----|---|--------|----|-----------|
|<span data-ttu-id="3cb7b-112">modelFileName</span><span class="sxs-lookup"><span data-stu-id="3cb7b-112">modelFileName</span></span>|<span data-ttu-id="3cb7b-113">query</span><span class="sxs-lookup"><span data-stu-id="3cb7b-113">query</span></span>|<span data-ttu-id="3cb7b-114">Waar</span><span class="sxs-lookup"><span data-stu-id="3cb7b-114">True</span></span>|<span data-ttu-id="3cb7b-115">reeks</span><span class="sxs-lookup"><span data-stu-id="3cb7b-115">string</span></span>|<span data-ttu-id="3cb7b-116">Naam van het Syntex-modelbestand.</span><span class="sxs-lookup"><span data-stu-id="3cb7b-116">Name of the Syntex model file.</span></span>|

## <a name="request-headers"></a><span data-ttu-id="3cb7b-117">Aanvraagheaders</span><span class="sxs-lookup"><span data-stu-id="3cb7b-117">Request headers</span></span>

| <span data-ttu-id="3cb7b-118">Header</span><span class="sxs-lookup"><span data-stu-id="3cb7b-118">Header</span></span> | <span data-ttu-id="3cb7b-119">Waarde</span><span class="sxs-lookup"><span data-stu-id="3cb7b-119">Value</span></span> |
|--------|-------|
|<span data-ttu-id="3cb7b-120">Accepteren</span><span class="sxs-lookup"><span data-stu-id="3cb7b-120">Accept</span></span>|<span data-ttu-id="3cb7b-121">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="3cb7b-121">application/json;odata=verbose</span></span>|
|<span data-ttu-id="3cb7b-122">Content-Type</span><span class="sxs-lookup"><span data-stu-id="3cb7b-122">Content-Type</span></span>|<span data-ttu-id="3cb7b-123">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="3cb7b-123">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="3cb7b-124">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="3cb7b-124">x-requestdigest</span></span>|<span data-ttu-id="3cb7b-125">De juiste samenvatting voor de huidige site.</span><span class="sxs-lookup"><span data-stu-id="3cb7b-125">The appropriate digest for the current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="3cb7b-126">Aanvraagtekst</span><span class="sxs-lookup"><span data-stu-id="3cb7b-126">Request body</span></span>

|<span data-ttu-id="3cb7b-127">Naam</span><span class="sxs-lookup"><span data-stu-id="3cb7b-127">Name</span></span>    |<span data-ttu-id="3cb7b-128">Type</span><span class="sxs-lookup"><span data-stu-id="3cb7b-128">Type</span></span>   |<span data-ttu-id="3cb7b-129">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="3cb7b-129">Description</span></span> |
|--------|-------|-------|
|<span data-ttu-id="3cb7b-130">ModelSettings</span><span class="sxs-lookup"><span data-stu-id="3cb7b-130">ModelSettings</span></span>|<span data-ttu-id="3cb7b-131">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="3cb7b-131">string</span></span>|<span data-ttu-id="3cb7b-132">JSON van modelinstellingen.</span><span class="sxs-lookup"><span data-stu-id="3cb7b-132">JSON of model settings.</span></span>|
|<span data-ttu-id="3cb7b-133">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="3cb7b-133">Description</span></span>|<span data-ttu-id="3cb7b-134">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="3cb7b-134">string</span></span>|<span data-ttu-id="3cb7b-135">De beschrijving van het model.</span><span class="sxs-lookup"><span data-stu-id="3cb7b-135">The model description.</span></span>|
|<span data-ttu-id="3cb7b-136">RetentionLabel</span><span class="sxs-lookup"><span data-stu-id="3cb7b-136">RetentionLabel</span></span>| |<span data-ttu-id="3cb7b-137">Info voor het bijbehorende label (label-id en naam).</span><span class="sxs-lookup"><span data-stu-id="3cb7b-137">Info for the associated label (label ID and name).</span></span>|

## <a name="responses"></a><span data-ttu-id="3cb7b-138">Antwoorden</span><span class="sxs-lookup"><span data-stu-id="3cb7b-138">Responses</span></span>

| <span data-ttu-id="3cb7b-139">Naam</span><span class="sxs-lookup"><span data-stu-id="3cb7b-139">Name</span></span>   | <span data-ttu-id="3cb7b-140">Type</span><span class="sxs-lookup"><span data-stu-id="3cb7b-140">Type</span></span>  | <span data-ttu-id="3cb7b-141">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="3cb7b-141">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="3cb7b-142">200 OK</span><span class="sxs-lookup"><span data-stu-id="3cb7b-142">200 OK</span></span>| |<span data-ttu-id="3cb7b-143">Succes</span><span class="sxs-lookup"><span data-stu-id="3cb7b-143">Success</span></span>|

## <a name="examples"></a><span data-ttu-id="3cb7b-144">Voorbeelden</span><span class="sxs-lookup"><span data-stu-id="3cb7b-144">Examples</span></span>

### <a name="update-model-settings-for-contoso-contract"></a><span data-ttu-id="3cb7b-145">Modelinstellingen bijwerken voor Contoso-contract</span><span class="sxs-lookup"><span data-stu-id="3cb7b-145">Update model settings for Contoso Contract</span></span>

<span data-ttu-id="3cb7b-146">In dit voorbeeld worden de modelbeschrijving en het retentielabel Standaard bewaring bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="3cb7b-146">In this example, the model description and "Standard Hold" retention label are updated.</span></span> <span data-ttu-id="3cb7b-147">De id van het retentielabel is `27c5fcba-abfd-4c34-823d-0b4a48f7ffe6`.</span><span class="sxs-lookup"><span data-stu-id="3cb7b-147">The ID of the retention label is `27c5fcba-abfd-4c34-823d-0b4a48f7ffe6`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="3cb7b-148">Voorbeeldaanvraag</span><span class="sxs-lookup"><span data-stu-id="3cb7b-148">Sample request</span></span>

```HTTP
{
    "ModelSettings": "{\"Description\":\"This model is used to set files classified as Contoso Contracts with a standard hold retention.\", \"RetentionLabel\":{\"Id\":\"27c5fcba-abfd-4c34-823d-0b4a48f7ffe6\",\"Name\":\"Standard Hold\"}}"
}

```

#### <a name="sample-response"></a><span data-ttu-id="3cb7b-149">Voorbeeldantwoord</span><span class="sxs-lookup"><span data-stu-id="3cb7b-149">Sample response</span></span>

<span data-ttu-id="3cb7b-150">**Statuscode:** 200</span><span class="sxs-lookup"><span data-stu-id="3cb7b-150">**Status code:** 200</span></span>

## <a name="see-also"></a><span data-ttu-id="3cb7b-151">Zie ook</span><span class="sxs-lookup"><span data-stu-id="3cb7b-151">See also</span></span>

[<span data-ttu-id="3cb7b-152">REST API van Syntex-model voor documentbegrip</span><span class="sxs-lookup"><span data-stu-id="3cb7b-152">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
