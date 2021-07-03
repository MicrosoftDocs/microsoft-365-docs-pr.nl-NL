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
# <a name="create-classification-request"></a>Classificatieaanvraag maken

Hiermee wordt een aanvraag gemaakt om een of meer bestanden te classificeren met behulp van het toegepaste model voor documentbegrip (zie [voorbeeld](rest-createclassificationrequest.md#examples)).

De SharePoint Online (en SharePoint 2016 en hoger on-premises) REST-service ondersteunt het combineren van meerdere aanvragen. Aanvragen worden gecombineerd in één oproep naar de service met behulp van de queryoptie OData-$batch. Deze methode kan worden gebruikt om classificatiewerkitems voor honderden documenten tegelijk in de wachtrij te plaatsen.

## <a name="http-request"></a>HTTP-aanvraag

```http
POST /_api/machinelearning/workItems HTTP/1.1
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
|_metagegevens|reeks |Stel de objectmeta in op de SPO. Gebruik altijd de waarde: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningWorkItemEntityData"}. |
|TargetSiteId|guid|De site-id waar het te classificeren bestand zich bevindt.|
|TargetWebId|guid|De web-id waar het te classificeren bestand zich bevindt.|
|TargetUniqueId|guid|De id van het bestand dat moet worden geclassificeerd.|

## <a name="responses"></a>Antwoorden

| Naam   | Type  | Omschrijving|
|--------|-------|------------|
|201 gemaakt| |Geslaagd|

## <a name="examples"></a>Voorbeelden

### <a name="enqueue-a-request-to-classify-a-file-of-id-e6cff8b7-c90c-4564-b5b8-033449090932"></a>Een verzoek in de wachtrij plaatsen om een bestand met id 'e6cff8b7-c90c-4564-b5b8-033449090932' te classificeren

#### <a name="sample-request"></a>Voorbeeldaanvraag

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

#### <a name="sample-response"></a>Voorbeeldreactie

**Statuscode:** 201

## <a name="see-also"></a>Zie ook

[REST API van Syntex-model voor documentbegrip](syntex-model-rest-api.md)
