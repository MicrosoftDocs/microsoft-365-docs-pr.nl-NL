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
ms.openlocfilehash: 8c7aeb449da161fe49050631643c63c93268a13f
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904178"
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

| Koptekst | Waarde |
|--------|-------|
|Accepteren|application/json;odata=verbose|
|Inhoudstype|application/json;odata=verbose;charset=utf-8|
|x-requestdigest|De juiste samenvatting voor deze site.|

## <a name="request-body"></a>Aanvraagtekst

| Naam | Vereist | Type | Omschrijving |
|--------|-------|--------|------------|
|ModelUniqueId|ja|reeks|De unieke id van het modelbestand.|
TargetSiteUrl|ja|reeks|De volledige URL van de doelbibliotheeksite.|
TargetWebServerRelativeUrl|ja|reeks|De relatieve server-URL van het web voor de doelbibliotheek.|
TargetLibraryServerRelativeUrl|ja|reeks|De relatieve server-URL van de doelbibliotheek.|
ViewOption|nee|reeks|Hiermee geeft u op of een nieuwe modelweergave als standaardbibliotheek moet worden ingesteld.|

## <a name="response"></a>Antwoord

| Naam   | Type  | Omschrijving|
|--------|-------|------------|
|200 OK| |Succes|


## <a name="examples"></a>Voorbeelden

### <a name="remove-a-model-from-the-contracts-document-library-in-the-repository-site"></a>Een model verwijderen uit de contractdocumentbibliotheek op de repositorysite

In dit voorbeeld is de id van het model voor documentbegrip van het Contoso Contract `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.

#### <a name="sample-request"></a>Voorbeeldaanvraag

```HTTP
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningPublicationsEntityData"
    },
    "Publications": {
        "results": [
            {
                "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
                "TargetSiteUrl": "https://contoso.sharepoint.com/sites/repository/",
                "TargetWebServerRelativeUrl": "/sites/repository",
                "TargetLibraryServerRelativeUrl": "/sites/repository/contracts",
                "ViewOption": "NewViewAsDefault"
            }
        ]
    }
}
```


#### <a name="sample-response"></a>Voorbeeldantwoord

In de reactie verwijzen TotalFailures en TotalSuccesses naar het aantal mislukte en geslaagde pogingen van het model dat van toepassing is op de opgegeven bibliotheken.

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
