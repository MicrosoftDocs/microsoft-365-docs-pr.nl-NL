---
title: BatchDelete
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
description: Gebruik REST API om een toegepast model met documentbegrip te verwijderen uit een of meer bibliotheken.
ms.openlocfilehash: e95c0583b1b0e2f5de08228afbf161c339544047
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177235"
---
# <a name="batchdelete"></a>BatchDelete

Verwijdert een toegepast model met documentbegrip uit een of meer bibliotheken. Houd er rekening mee dat een model moet worden verwijderd uit alle bibliotheken voordat het kan worden verwijderd (zie [voorbeeld](rest-batchdelete-method.md#examples)).

## <a name="http-request"></a>HTTP-aanvraag

```HTTP
POST /_api/machinelearning/publications/batchdelete HTTP/1.1
```

## <a name="uri-parameters"></a>URI-parameters

Geen

## <a name="request-headers"></a>Aanvraagheaders

| Header | Waarde |
|--------|-------|
|Accepteren|application/json;odata=verbose|
|Content-Type|application/json;odata=verbose;charset=utf-8|
|x-requestdigest|De juiste samenvatting voor deze site.|

## <a name="request-body"></a>Aanvraagtekst

| Naam | Vereist | Type | Omschrijving |
|--------|-------|--------|------------|
|Publicaties|ja|MachineLearningPublicationEntityData[]|De verzameling MachineLearningPublicationEntityData die elk het model en de doeldocumentbibliotheek specificeert.|

### <a name="machinelearningpublicationentitydata"></a>MachineLearningPublicationEntityData
| Naam | Vereist | Type | Omschrijving |
|--------|-------|--------|------------|
|ModelUniqueId|ja|reeks|De unieke id van het modelbestand.|
|TargetSiteUrl|ja|reeks|De volledige URL van de doelbibliotheeksite.|
|TargetWebServerRelativeUrl|ja|reeks|De relatieve server-URL van het web voor de doelbibliotheek.|
|TargetLibraryServerRelativeUrl|ja|reeks|De relatieve server-URL van de doelbibliotheek.|

## <a name="response"></a>Antwoord

| Naam   | Type  | Omschrijving|
|--------|-------|------------|
|200 OK||Dit is een aangepaste API ter ondersteuning van het verwijderen van een model uit bibliotheken met meerdere documenten. In het geval van gedeeltelijk succes kan 200 OK nog steeds worden geretourneerd en moet de aanroeper de antwoordtekst inspecteren om te begrijpen of het model is verwijderd uit een documentbibliotheek.|

## <a name="response-body"></a>Antwoordtekst
| Naam   | Type  | Omschrijving|
|--------|-------|------------|
|TotalSuccesses|int|Het totale aantal modellen dat uit een documentbibliotheek wordt verwijderd.|
|TotalFailures|int|Het totale aantal modellen dat niet kan worden verwijderd uit een documentbibliotheek.|
|Details|MachineLearningPublicationResult[]|De verzameling MachineLearningPublicationResult die elk het gedetailleerde resultaat specificeert van het verwijderen van het model uit een documentbibliotheek.|

### <a name="machinelearningpublicationresult"></a>MachineLearningPublicationResult
| Naam   | Type  | Omschrijving|
|--------|-------|------------|
|Statuscode|int|De HTTP-statuscode.|
|ErrorMessage|tekenreeks|Het foutbericht dat aangeeft wat het probleem is bij het toepassen van het model op de documentbibliotheek.|
|Publicatie|MachineLearningPublicationEntityData|Hiermee geeft u de modelgegevens en de doeldocumentbibliotheek op.| 

### <a name="machinelearningpublicationentitydata"></a>MachineLearningPublicationEntityData
| Naam | Type | Omschrijving |
|--------|--------|------------|
|ModelUniqueId|reeks|De unieke id van het modelbestand.|
|TargetSiteUrl|reeks|De volledige URL van de doelbibliotheeksite.|
|TargetWebServerRelativeUrl|reeks|De relatieve server-URL van het web voor de doelbibliotheek.|
|TargetLibraryServerRelativeUrl|reeks|De relatieve server-URL van de doelbibliotheek.|

## <a name="examples"></a>Voorbeelden

### <a name="remove-a-model-from-the-contracts-document-library-in-the-repository-site"></a>Een model verwijderen uit de contractdocumentbibliotheek op de repositorysite

In dit voorbeeld is de id van het model voor documentbegrip van het Contoso Contract `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.

#### <a name="sample-request"></a>Voorbeeldaanvraag

```HTTP
{ 
    "publications": [ 
        { 
            "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc", 
            "TargetSiteUrl": "https://constco.sharepoint-df.com/sites/docsite", 
            "TargetWebServerRelativeUrl": "/sites/docsite ", 
            "TargetLibraryServerRelativeUrl": "/sites/dcocsite/joedcos" 
        } 
    ] 
} 
```


#### <a name="sample-response"></a>Voorbeeldreactie

In de reactie verwijzen TotalFailures en TotalSuccesses naar het aantal mislukte en geslaagde pogingen van het model dat wordt verwijderd uit de opgegeven bibliotheken.

**Statuscode:** 200

```JSON
{
    "Details": [
        {
            "ErrorMessage": null,
            "Publication": {
                "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
                "TargetSiteUrl": "https://contoso.sharepoint.com/sites/repository/",
                "TargetWebServerRelativeUrl": "/sites/repository",
                "TargetLibraryServerRelativeUrl": "/sites/repository/contracts",
                "ViewOption": "NewViewAsDefault"
            },
            "StatusCode": 200
        }
    ],
    "TotalFailures": 0,
    "TotalSuccesses": 1
}
```

## <a name="see-also"></a>Zie ook

[REST API van Syntex-model voor documentbegrip](syntex-model-rest-api.md)
