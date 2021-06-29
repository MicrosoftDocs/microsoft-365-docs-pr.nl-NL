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
ms.openlocfilehash: 0a1b6ef9b7e38f2c4f52082103530da432e3e855
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177151"
---
# <a name="create-model"></a>Model maken

Een model en het gekoppelde inhoudstype maken. Hiermee wordt het model alleen gemaakt. Het moet nog wel worden getraind in het inhoudscentrum (zie [voorbeeld](rest-createmodel-method.md#examples)).

## <a name="http-request"></a>HTTP-aanvraag

```
POST /_api/machinelearning/models HTTP/1.1
```
## <a name="uri-parameters"></a>URI-parameters

Geen

## <a name="request-headers"></a>Aanvraagheaders

| Header | Waarde |
|--------|-------|
|Accepteren|application/json;odata=verbose|
|Content-Type|application/json;odata=verbose;charset=utf-8|
|x-requestdigest|De juiste samenvatting voor deze site|

## <a name="request-body"></a>Aanvraagtekst

|Naam    |Type   |Omschrijving |
|--------|-------|------------|
|_metadata|  |Stel de objectmeta in op de SPO. Gebruik altijd de waarde: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"}. |
|ContentTypeGroup|string|De groep van het gekoppelde inhoudstype die aan het model is gekoppeld. Is standaard ingesteld op 'Typen intelligente documentinhoud'.|
|ContentTypeName|string|De naam van het gekoppelde inhoudstype. Het gemaakte modelbestand krijgt dezelfde naam.|

## <a name="responses"></a>Reacties

| Naam   | Type  | Omschrijving|
|--------|-------|------------|
|201 gemaakt| |Geslaagd|

## <a name="examples"></a>Voorbeelden

### <a name="create-a-new-document-understanding-model-called-contoso-contract"></a>Een nieuw documentbegripmodel maken met de naam 'Contoso-contract'

#### <a name="sample-request"></a>Voorbeeldaanvraag

```
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"
    },
    "ContentTypeGroup": "Intelligent Document Content Types",
    "ContentTypeName": "Contoso Contract"
}
```

#### <a name="sample-response"></a>Voorbeeldreactie

**Statuscode:** 201

## <a name="see-also"></a>Zie ook

[REST API van Syntex-model voor documentbegrip](syntex-model-rest-api.md)
