---
title: Model- en bibliotheekgegevens ophalen
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
description: Gebruik REST API om informatie te krijgen over een model en de bibliotheek waarop het is toegepast.
ms.openlocfilehash: 6cd61364ed3b360ef235aaba21a2735002fe481e
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904187"
---
# <a name="get-model-and-library-information"></a>Model- en bibliotheekgegevens ophalen

Haalt informatie op over een model en de bibliotheek waarop het is toegepast (zie [voorbeeld](rest-getmodelandlibraryinfo.md#examples)).

## <a name="http-request"></a>HTTP-aanvraag

```HTTP
GET /_api/machinelearning/publications/getbyuniqueid(‘{modelUniqueId}’) HTTP/1.1
```

## <a name="uri-parameters"></a>URI-parameters

| Naam | In | Vereist | Type | Omschrijving |
|--------|-------|--------|------------|
|ModelUniqueId|query|Waar|GUID|De unieke id van het modelbestand.|

## <a name="request-headers"></a>Aanvraagheaders

| Koptekst | Waarde |
|--------|-------|
|Accepteren|application/json;odata=verbose|


## <a name="request-body"></a>Aanvraagtekst

| Naam | Vereist | Type | Omschrijving |
|--------|-------|--------|------------|
|ModelUniqueId|ja|reeks|De unieke id van het modelbestand.|
|TargetSiteUrl|ja|reeks|De volledige URL van de doelbibliotheeksite.|
|TargetWebServerRelativeUrl|ja|reeks|De relatieve server-URL van het web voor de doelbibliotheek.|
|TargetLibraryServerRelativeUrl|ja|reeks|De relatieve server-URL van de doelbibliotheek.|
|TargetLibraryRemoved|ja|int|De vlag die aangeeft of de doelbibliotheek al dan niet is verwijderd.|

## <a name="response"></a>Antwoord

| Naam   | Type  | Omschrijving|
|--------|-------|------------|
|200 OK| |Succes|
|201 gemaakt| |Houd er rekening mee dat, omdat deze API het toepassen van een model op meerdere bibliotheken ondersteunt, een 201 kan worden geretourneerd, zelfs als er een fout is opgetreden bij het toepassen van het model op een van de bibliotheken. <br>Controleer de antwoordtekst om te zien of het model is toegepast op alle opgegeven bibliotheken. Zie [aanvraagtekst](rest-getmodelandlibraryinfo.md#request-body) voor meer informatie.|

## <a name="examples"></a>Voorbeelden

### <a name="get-information-about-the-contracts-model-and-primed-document-library-in-the-repository-site"></a>Krijg informatie over het contractmodel en de geprimede documentbibliotheek op de repositorysite

In dit voorbeeld is de id van het model voor documentbegrip van het Contoso Contract `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.

#### <a name="sample-request"></a>Voorbeeldaanvraag

```HTTP
GET /sites/TestCC/_api/machinelearning/publications/getbymodeluniqueid(‘{7645e69d-21fb-4a24-a17a-9bdfa7cb63dc}’) HTTP/1.1
```
#### <a name="sample-response"></a>Voorbeeldantwoord

**Statuscode:** 200

```JSON
{
    "@odata.context": "https://contoso.sharepoint.com/sites/TestCC/_api/$metadata#publications",
    "value": [
        {
            "@odata.type": "#Microsoft.Office.Server.ContentCenter.SPMachineLearningPublication",
            "@odata.id": "https://contoso.sharepoint.com/sites/repository /_api/machinelearning/publications/getbyuniqueId('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc')",
            "@odata.etag": "\"7645e69d-21fb-4a24-a17a-9bdfa7cb63dc,94\"",
            "@odata.editLink": " https://contoso.sharepoint.com/sites/TestCC /_api/machinelearning/publications/getbyuniqueId('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc')",
            "Created": "2021-04-27T03:05:25Z",
            "CreatedBy": "i:0#.f|membership|meganb@contoso.com",
            "DriveId": "b!O-aG9qer5UiXx2jEwd8pL0221maIb9lNs9tH5vAMU-gPy9BrxT7GTrtXtdtv1Uzb",
            "ID": 26,
            "ModelId": 16,
            "ModelName": "contosocontract.classifier",
            "ModelType": 0,
            "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
            "ModelVersion": "8.0",
            "Modified": "2021-03-17T17:56:42Z",
            "ModifiedBy": "i:0#.f|membership|joedoe@contoso.com",
            "ObjectId": "01ZBWEM5FZRILGLXTEB5CZ2NNNSCTWBJMQ",
            "PublicationType": 1,
            "TargetLibraryRemoved": false,
            "TargetLibraryServerRelativeUrl": "/sites/repository/contracts",
            "TargetLibraryUrl": " https://contoso.sharepoint.com/sites/repository/contracts",
            "TargetSiteUrl": "https://contoso.sharepoint.com/sites/repository",
            "TargetWebServerRelativeUrl": "/sites/repository",
            "UniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
            "ViewOption": "NewViewAsDefault"
        },
        {
            "@odata.type": "#Microsoft.Office.Server.ContentCenter.SPMachineLearningPublication",
            "@odata.id": "https://contoso.sharepoint.com /sites/legal/_api/machinelearning/publications/getbyuniqueId('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc')",
            "@odata.etag": "\"7645e69d-21fb-4a24-a17a-9bdfa7cb63dc,101\"",
            "@odata.editLink": "https://contoso.sharepoint.com /sites/legal/_api/machinelearning/publications/getbyuniqueId('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc')",
            "Created": "2021-01-27T03:17:44Z",
            "CreatedBy": "i:0#.f|membership|esherman@contoso.com ",
            "DriveId": "b!O-aG9qer5UiXx2jEwd8pL0221maIb9lNs9tH5vAMU-gPy9BrxT7GTrtXtdtv1Uzb",
            "ID": 27,
            "ModelId": 16,
            "ModelName": "dispositions.classifier",
            "ModelType": 0,
            "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
            "ModelVersion": "8.0",
            "Modified": "2021-03-17T23:17:46Z",
            "ModifiedBy": "i:0#.f|membership|esherman@contoso.com ",
            "ObjectId": "01ZBWEM5B3ERSZK4PAARGLFZ7JP6GMXG2R",
            "PublicationType": 1,
            "TargetLibraryRemoved": false,
            "TargetLibraryServerRelativeUrl": "/sites/legal/dispositions",
            "TargetLibraryUrl": "https://contoso.sharepoint.com/sites/legal/dispositions",
            "TargetSiteUrl": " https://contoso.sharepoint.com/sites/legal",
            "TargetWebServerRelativeUrl": "/sites/legal",
            "UniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
            "ViewOption": "NewViewAsDefault"
        }
    ]
}```
```

## <a name="see-also"></a>Zie ook

[REST API van Syntex-model voor documentbegrip](syntex-model-rest-api.md)
