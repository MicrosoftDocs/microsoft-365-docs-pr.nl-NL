---
title: Model Batch toepassen
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
description: Gebruik REST API om een model met documentbegrip toe te passen op een of meer bibliotheken.
ms.openlocfilehash: 04f1dfdb0c16110c9ba7de12f5f0735d498d50cf
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286535"
---
# <a name="batch-apply-model"></a>Model Batch toepassen

Past (of synchroniseert) een getraind model voor documentbegrip toe op een of meer bibliotheken (zie [voorbeeld](rest-applymodel-method.md#examples)).

## <a name="http-request"></a>HTTP-aanvraag

```HTTP
POST /_api/machinelearning/publications HTTP/1.1
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
|__metadata|ja|reeks|Stel de objectmeta in op de SPO. Gebruik altijd de waarde: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningPublicationsEntityData"}.|
|Publicaties|ja|MachineLearningPublicationEntityData[]|De verzameling MachineLearningPublicationEntityData die elk het model en de doeldocumentbibliotheek specificeert.|

### <a name="machinelearningpublicationentitydata"></a>MachineLearningPublicationEntityData

| Naam | Vereist | Type | Omschrijving |
|--------|-------|--------|------------|
|ModelUniqueId|ja|reeks|De unieke id van het modelbestand.|
|TargetSiteUrl|ja|reeks|De volledige URL van de doelbibliotheeksite.|
|TargetWebServerRelativeUrl|ja|reeks|De relatieve server-URL van het web voor de doelbibliotheek.|
|TargetLibraryServerRelativeUrl|ja|reeks|De relatieve server-URL van de doelbibliotheek.|
|ViewOption|nee|reeks|Hiermee geeft u op of een nieuwe modelweergave als standaardbibliotheek moet worden ingesteld.|

## <a name="response"></a>Antwoord

| Naam   | Type  | Omschrijving|
|--------|-------|------------|
|201 gemaakt||Dit is een aangepaste API ter ondersteuning van het toepassen van een model op bibliotheken met meerdere documenten. In het geval van gedeeltelijk succes kan 201 gemaakt nog steeds worden geretourneerd en moet de aanroeper de antwoordtekst inspecteren om te begrijpen of het model is toegepast op een documentbibliotheek.|

## <a name="response-body"></a>Antwoordtekst

| Naam   | Type  | Omschrijving|
|--------|-------|------------|
|TotalSuccesses|int|Het totale aantal modellen dat wordt toegepast op een documentbibliotheek.|
|TotalFailures|int|Het totale aantal modellen dat niet kan worden toegepast op een documentbibliotheek.|
|Details|MachineLearningPublicationResult[]|De verzameling MachineLearningPublicationResult die elk het gedetailleerde resultaat specificeert van het toepassen van het model op de documentbibliotheek.|

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

**Statuscode:** 201

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
            "StatusCode": 201
        }
    ],
    "TotalFailures": 0,
    "TotalSuccesses": 1
}
```

## <a name="see-also"></a>Zie ook

[REST API van Syntex-model voor documentbegrip](syntex-model-rest-api.md)
