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
ms.openlocfilehash: f24fc8428adbf22ded2ca6d7a49cabc84b385770
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904190"
---
# <a name="updatemodelsettings"></a><span data-ttu-id="64f71-103">UpdateModelSettings</span><span class="sxs-lookup"><span data-stu-id="64f71-103">UpdateModelSettings</span></span>

<span data-ttu-id="64f71-104">Hiermee worden de beschikbare modelinstellingen (gekoppeld retentielabel en modelbeschrijving) bijgewerkt voor een SharePoint Syntex-model voor documentbegrip (zie [voorbeeld](rest-updatemodelsettings-method.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="64f71-104">Updates available models settings (associated retention label and model description) for a SharePoint Syntex document understanding model (see [example](rest-updatemodelsettings-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="64f71-105">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="64f71-105">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/models/updatemodelsettings HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="64f71-106">URI-parameters</span><span class="sxs-lookup"><span data-stu-id="64f71-106">URI parameters</span></span>

<span data-ttu-id="64f71-107">Geen</span><span class="sxs-lookup"><span data-stu-id="64f71-107">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="64f71-108">Aanvraagheaders</span><span class="sxs-lookup"><span data-stu-id="64f71-108">Request headers</span></span>

| <span data-ttu-id="64f71-109">Koptekst</span><span class="sxs-lookup"><span data-stu-id="64f71-109">Header</span></span> | <span data-ttu-id="64f71-110">Waarde</span><span class="sxs-lookup"><span data-stu-id="64f71-110">Value</span></span> |
|--------|-------|
|<span data-ttu-id="64f71-111">Accepteren</span><span class="sxs-lookup"><span data-stu-id="64f71-111">Accept</span></span>|<span data-ttu-id="64f71-112">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="64f71-112">application/json;odata=verbose</span></span>|
|<span data-ttu-id="64f71-113">Inhoudstype</span><span class="sxs-lookup"><span data-stu-id="64f71-113">Content-Type</span></span>|<span data-ttu-id="64f71-114">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="64f71-114">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="64f71-115">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="64f71-115">x-requestdigest</span></span>|<span data-ttu-id="64f71-116">De juiste samenvatting voor de huidige site.</span><span class="sxs-lookup"><span data-stu-id="64f71-116">The appropriate digest for the current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="64f71-117">Aanvraagtekst</span><span class="sxs-lookup"><span data-stu-id="64f71-117">Request body</span></span>

|<span data-ttu-id="64f71-118">Naam</span><span class="sxs-lookup"><span data-stu-id="64f71-118">Name</span></span>    |<span data-ttu-id="64f71-119">Type</span><span class="sxs-lookup"><span data-stu-id="64f71-119">Type</span></span>   |<span data-ttu-id="64f71-120">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="64f71-120">Description</span></span> |
|--------|-------|-------|
|<span data-ttu-id="64f71-121">ModelSettings</span><span class="sxs-lookup"><span data-stu-id="64f71-121">ModelSettings</span></span>|<span data-ttu-id="64f71-122">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="64f71-122">string</span></span>|<span data-ttu-id="64f71-123">JSON van modelinstellingen.</span><span class="sxs-lookup"><span data-stu-id="64f71-123">JSON of model settings.</span></span>|
|<span data-ttu-id="64f71-124">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="64f71-124">Description</span></span>|<span data-ttu-id="64f71-125">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="64f71-125">string</span></span>|<span data-ttu-id="64f71-126">De beschrijving van het model.</span><span class="sxs-lookup"><span data-stu-id="64f71-126">The model description.</span></span>|
|<span data-ttu-id="64f71-127">RetentionLabel</span><span class="sxs-lookup"><span data-stu-id="64f71-127">RetentionLabel</span></span>| |<span data-ttu-id="64f71-128">Info voor het bijbehorende label (label-id en naam).</span><span class="sxs-lookup"><span data-stu-id="64f71-128">Info for the associated label (label ID and name).</span></span>|

## <a name="responses"></a><span data-ttu-id="64f71-129">Antwoorden</span><span class="sxs-lookup"><span data-stu-id="64f71-129">Responses</span></span>

| <span data-ttu-id="64f71-130">Naam</span><span class="sxs-lookup"><span data-stu-id="64f71-130">Name</span></span>   | <span data-ttu-id="64f71-131">Type</span><span class="sxs-lookup"><span data-stu-id="64f71-131">Type</span></span>  | <span data-ttu-id="64f71-132">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="64f71-132">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="64f71-133">200 OK</span><span class="sxs-lookup"><span data-stu-id="64f71-133">200 OK</span></span>| |<span data-ttu-id="64f71-134">Succes</span><span class="sxs-lookup"><span data-stu-id="64f71-134">Success</span></span>|

## <a name="examples"></a><span data-ttu-id="64f71-135">Voorbeelden</span><span class="sxs-lookup"><span data-stu-id="64f71-135">Examples</span></span>

### <a name="update-model-settings-for-contoso-contract"></a><span data-ttu-id="64f71-136">Modelinstellingen bijwerken voor Contoso-contract</span><span class="sxs-lookup"><span data-stu-id="64f71-136">Update model settings for Contoso Contract</span></span>

<span data-ttu-id="64f71-137">In dit voorbeeld worden de modelbeschrijving en het retentielabel Standaard bewaring bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="64f71-137">In this example, the model description and "Standard Hold" retention label are updated.</span></span> <span data-ttu-id="64f71-138">De id van het retentielabel is `27c5fcba-abfd-4c34-823d-0b4a48f7ffe6`.</span><span class="sxs-lookup"><span data-stu-id="64f71-138">The ID of the retention label is `27c5fcba-abfd-4c34-823d-0b4a48f7ffe6`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="64f71-139">Voorbeeldaanvraag</span><span class="sxs-lookup"><span data-stu-id="64f71-139">Sample request</span></span>

```HTTP
{
    "ModelSettings": "{\"Description\":\"This model is used to set files classified as Contoso Contracts with a standard hold retention.\", \"RetentionLabel\":{\"Id\":\"27c5fcba-abfd-4c34-823d-0b4a48f7ffe6\",\"Name\":\"Standard Hold\"}}"
}

```

#### <a name="sample-response"></a><span data-ttu-id="64f71-140">Voorbeeldantwoord</span><span class="sxs-lookup"><span data-stu-id="64f71-140">Sample response</span></span>

<span data-ttu-id="64f71-141">**Statuscode:** 200</span><span class="sxs-lookup"><span data-stu-id="64f71-141">**Status code:** 200</span></span>

## <a name="see-also"></a><span data-ttu-id="64f71-142">Zie ook</span><span class="sxs-lookup"><span data-stu-id="64f71-142">See also</span></span>

[<span data-ttu-id="64f71-143">REST API van Syntex-model voor documentbegrip</span><span class="sxs-lookup"><span data-stu-id="64f71-143">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
