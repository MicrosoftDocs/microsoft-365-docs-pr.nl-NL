---
title: Model toepassen
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
description: Gebruik REST API om een toegepast model met documentbegrip toe te passen op een of meer bibliotheken.
ms.openlocfilehash: d4cadad3c45dd7af0cdaeb4e1b367426289db870
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904268"
---
# <a name="apply-model"></a>Model toepassen

Past (of synchroniseert) een getraind model voor documentbegrip toe op een of meer bibliotheken (zie [voorbeeld](rest-applymodel-method.md#examples)).

## <a name="http-request"></a>HTTP-aanvraag

```HTTP
POST /_api/machinelearning/publications HTTP/1.1
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

## <a name="response"></a>Reactie

| Naam   | Type  | Omschrijving|
|--------|-------|------------|
|200 OK| |Succes|
|201 gemaakt| |Houd er rekening mee dat, omdat deze API het toepassen van een model op meerdere bibliotheken ondersteunt, een 201 kan worden geretourneerd, zelfs als er een fout is opgetreden bij het toepassen van het model op een van de bibliotheken. <br>Controleer de antwoordtekst om te zien of het model is toegepast op alle opgegeven bibliotheken. Zie [aanvraagtekst](rest-applymodel-method.md#request-body) voor meer informatie.|

## <a name="examples"></a>Voorbeelden

### <a name="apply-a-model-to-the-contracts-document-library-in-the-repository-site"></a>Een model toepassen op de contractdocumentbibliotheek op de repositorysite

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
