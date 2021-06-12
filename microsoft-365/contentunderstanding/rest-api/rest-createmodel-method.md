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
# <a name="create-model"></a>Model maken

Maakt een model en het gekoppelde inhoudstype. Merk op dat hierdoor alleen het model wordt gemaakt. Deze moet nog worden getraind in het inhoudscentrum (zie [voorbeeld](rest-createmodel-method.md#examples)).

## <a name="http-request"></a>HTTP-aanvraag

```
POST /_api/machinelearning/models HTTP/1.1
```
## <a name="uri-parameters"></a>URI-parameters

Geen

## <a name="request-headers"></a>Aanvraagheaders

| Koptekst | Waarde |
|--------|-------|
|Accepteren|toepassing/json;odata=verbose|
|Inhoudstype|toepassing/json;odata=verbose;charset=utf-8|
|x-requestdigest|De juiste samenvatting voor deze site|

## <a name="request-body"></a>Aanvraagtekst

|Naam    |Type   |Omschrijving |
|--------|-------|------------|
|_metagegevens|  |Stel de objectmeta in op de SPO. Gebruik altijd de waarde: {"type": "Microsoft.Office.Server.ContentCenter.SP MachineLearningModelEntityData"}. |
|ContentTypeGroup|tekenreeks|De groep van het gekoppelde inhoudstype die aan het model is gekoppeld. Is standaard ingesteld op 'Intelligente documentinhoudtypen'.|
|ContentTypeName|tekenreeks|De naam van het gekoppelde inhoudstype. Het gemaakte modelbestand krijgt dezelfde naam.|

## <a name="responses"></a>Antwoorden

| Naam   | Type  | Omschrijving|
|--------|-------|------------|
|201 gemaakt| |Geslaagd|

## <a name="examples"></a>Voorbeelden

### <a name="create-a-new-document-understanding-model-called-contoso-contract"></a>Een nieuw documentbegripsmodel maken met de naam 'Contoso-contract'

#### <a name="sample-request"></a>Voorbeeldaanvraag

```
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"
    },
    "ContentTypeGroup": "Intelligent Document Content Types",
    "ContentTypeName": "Contoso Contract",
}
```

#### <a name="sample-response"></a>Voorbeeldreactie

**Statuscode:** 201

## <a name="see-also"></a>Zie ook

[RESET API Syntec-documentbegripmodel](syntex-model-rest-api.md)
