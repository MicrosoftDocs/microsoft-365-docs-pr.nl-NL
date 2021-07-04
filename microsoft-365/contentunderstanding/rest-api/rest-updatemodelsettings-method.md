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
# <a name="updatemodelsettings"></a>UpdateModelSettings

Hiermee worden de beschikbare modelinstellingen (gekoppeld retentielabel en modelbeschrijving) bijgewerkt voor een SharePoint Syntex-model voor documentbegrip (zie [voorbeeld](rest-updatemodelsettings-method.md#examples)).

## <a name="http-request"></a>HTTP-aanvraag

```HTTP
POST /_api/machinelearning/models/getbytitle('{modelFileName}')/updatemodelsettings HTTP/1.1
```

## <a name="uri-parameters"></a>URI-parameters

|Naam |In |Vereist|Type|Omschrijving|
|-----|---|--------|----|-----------|
|modelFileName|query|Waar|reeks|Naam van het Syntex-modelbestand.|

## <a name="request-headers"></a>Aanvraagheaders

| Header | Waarde |
|--------|-------|
|Accepteren|application/json;odata=verbose|
|Content-Type|application/json;odata=verbose;charset=utf-8|
|x-requestdigest|De juiste samenvatting voor de huidige site.|

## <a name="request-body"></a>Aanvraagtekst

|Naam    |Type   |Beschrijving |
|--------|-------|-------|
|ModelSettings|tekenreeks|JSON van modelinstellingen.|
|Beschrijving|tekenreeks|De beschrijving van het model.|
|RetentionLabel| |Info voor het bijbehorende label (label-id en naam).|

## <a name="responses"></a>Antwoorden

| Naam   | Type  | Omschrijving|
|--------|-------|------------|
|200 OK| |Succes|

## <a name="examples"></a>Voorbeelden

### <a name="update-model-settings-for-contoso-contract"></a>Modelinstellingen bijwerken voor Contoso-contract

In dit voorbeeld worden de modelbeschrijving en het retentielabel Standaard bewaring bijgewerkt. De id van het retentielabel is `27c5fcba-abfd-4c34-823d-0b4a48f7ffe6`.

#### <a name="sample-request"></a>Voorbeeldaanvraag

```HTTP
{
    "ModelSettings": "{\"Description\":\"This model is used to set files classified as Contoso Contracts with a standard hold retention.\", \"RetentionLabel\":{\"Id\":\"27c5fcba-abfd-4c34-823d-0b4a48f7ffe6\",\"Name\":\"Standard Hold\"}}"
}

```

#### <a name="sample-response"></a>Voorbeeldantwoord

**Statuscode:** 200

## <a name="see-also"></a>Zie ook

[REST API van Syntex-model voor documentbegrip](syntex-model-rest-api.md)
