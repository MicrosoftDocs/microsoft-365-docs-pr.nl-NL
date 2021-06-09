---
title: Lijstindicatoren API
description: Meer informatie over het gebruik van de LIJSTINDICATOREN-API om een verzameling van alle actieve indicatoren in Microsoft Defender voor eindpunt op te halen.
keywords: api's, openbare api, ondersteunde api's, indicatorenverzameling
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: d9ec8610957af0bc7741848e7c7bd4fe850f5e32
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770420"
---
# <a name="list-indicators-api"></a>Lijstindicatoren API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)

- Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API-beschrijving
Hiermee wordt een verzameling met alle actieve indicatoren [opgehaald.](ti-indicator.md)
<br>Ondersteunt [OData V4-query's.](https://www.odata.org/documentation/)
<br>De query van OData ```$filter``` wordt ondersteund op: ```indicatorValue``` , , , en ```indicatorType``` ```creationTimeDateTimeUtc``` ```createdBy``` ```action``` ```severity``` eigenschappen.
<br>Zie voorbeelden bij [OData-query's met Microsoft Defender voor Eindpunt](exposed-apis-odata-samples.md)


## <a name="limitations"></a>Beperkingen
1. Tariefbeperkingen voor deze API zijn 100 oproepen per minuut en 1500 oproepen per uur. 


## <a name="permissions"></a>Machtigingen
Een van de volgende machtigingen is vereist om deze API te bellen. Zie Aan de slag voor meer informatie, inclusief het kiezen van [machtigingen.](apis-intro.md)

Machtigingstype |   Machtiging  |   Weergavenaam machtiging
:---|:---|:---
Toepassing |   Ti.ReadWrite |  'Indicatoren lezen en schrijven'
Toepassing |   Ti.ReadWrite.All |  'Alle indicatoren lezen en schrijven'
Gedelegeerd (werk- of schoolaccount) |    Ti.ReadWrite |  'Indicatoren lezen en schrijven'

## <a name="http-request"></a>HTTP-aanvraag
```
GET https://api.securitycenter.microsoft.com/api/indicators
```

## <a name="request-headers"></a>Kopteksten aanvragen

Naam | Type | Beschrijving
:---|:---|:---
Autorisatie | Tekenreeks | Bearer {token}. **Vereist**.


## <a name="request-body"></a>Body aanvragen
Leeg

## <a name="response"></a>Antwoord
Als dit is gelukt, retourneert deze methode 200, Ok-antwoordcode met een verzameling indicatorentiteiten. [](ti-indicator.md)

>[!Note]
> Als de toepassing de machtiging 'Ti.ReadWrite.All' heeft, wordt deze aan alle indicatoren getoond. Anders wordt deze alleen blootgesteld aan de indicatoren die het heeft gemaakt.

## <a name="example-1"></a>Voorbeeld 1: 

**Aanvraag**

Hier is een voorbeeld van een aanvraag die alle indicatoren krijgt

```
GET https://api.securitycenter.microsoft.com/api/indicators
```

**Antwoord**

Hier is een voorbeeld van het antwoord.

```
HTTP/1.1 200 Ok
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Indicators",
    "value": [
        {
            "id": "995",
            "indicatorValue": "12.13.14.15",
            "indicatorType": "IpAddress",
            "action": "Alert",
            "application": "demo-test",
            "source": "TestPrdApp",
            "sourceType": "AadApp",
            "title": "test",
            "creationTimeDateTimeUtc": "2018-10-24T11:15:35.3688259Z",
            "createdBy": "45097602-1234-5678-1234-9f453233e62c",
            "expirationTime": "2020-12-12T00:00:00Z",
            "lastUpdateTime": "2019-10-24T10:54:23.2009016Z",
            "lastUpdatedBy": TestPrdApp,
            "severity": "Informational",
            "description": "test",
            "recommendedActions": "test",
            "rbacGroupNames": []
        },
        {
            "id": "996",
            "indicatorValue": "220e7d15b0b3d7fac48f2bd61114db1022197f7f",
            "indicatorType": "FileSha1",
            "action": "AlertAndBlock",
            "application": null,
            "source": "TestPrdApp",
            "sourceType": "AadApp",
            "title": "test",
            "creationTimeDateTimeUtc": "2018-10-24T10:54:23.2009016Z",
            "createdBy": "45097602-1234-5678-1234-9f453233e62c",
            "expirationTime": "2020-12-12T00:00:00Z",
            "lastUpdateTime": "2019-10-24T10:54:23.2009016Z",
            "lastUpdatedBy": TestPrdApp,
            "severity": "Informational",
            "description": "test",
            "recommendedActions": "TEST",
            "rbacGroupNames": [ "Group1", "Group2" ]
        }
        ...
    ]
}
```

## <a name="example-2"></a>Voorbeeld 2: 

**Aanvraag**

Hier is een voorbeeld van een aanvraag die alle indicatoren krijgt met de actie 'AlertAndBlock'. 

```
GET https://api.securitycenter.microsoft.com/api/indicators?$filter=action+eq+'AlertAndBlock'
```

**Antwoord**

Hier is een voorbeeld van het antwoord.

```
HTTP/1.1 200 Ok
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Indicators",
    "value": [
        {
            "id": "997",
            "indicatorValue": "111e7d15b0b3d7fac48f2bd61114db1022197f7f",
            "indicatorType": "FileSha1",
            "action": "AlertAndBlock",
            "application": null,
            "source": "TestPrdApp",
            "sourceType": "AadApp",
            "title": "test",
            "creationTimeDateTimeUtc": "2018-10-24T10:54:23.2009016Z",
            "createdBy": "45097602-1234-5678-1234-9f453233e62c",
            "expirationTime": "2020-12-12T00:00:00Z",
            "lastUpdateTime": "2019-10-24T10:54:23.2009016Z",
            "lastUpdatedBy": TestPrdApp,
            "severity": "Informational",
            "description": "test",
            "recommendedActions": "TEST",
            "rbacGroupNames": [ "Group1", "Group2" ]
        }
        ...
    ]
}
```
