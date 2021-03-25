---
title: API voor indicatoren importeren
description: Meer informatie over het gebruik van de batch Indicator API importeren in Microsoft Defender voor Eindpunt.
keywords: api's, ondersteunde api's, submit, ti, indicator, update
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
ms.openlocfilehash: b1777adf7b97083fae2daf4213a4bda742ba097d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198243"
---
# <a name="import-indicators-api"></a>API voor indicatoren importeren

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)

- Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API-beschrijving
Verzend of updates [](ti-indicator.md) batch van indicatorentiteiten.
<br>CIDR-notatie voor IPs wordt niet ondersteund.

## <a name="limitations"></a>Beperkingen
1. Tariefbeperkingen voor deze API zijn 30 oproepen per minuut.
2. Er is een limiet van 15.000 actieve [indicatoren](ti-indicator.md) per tenant. 
3. De maximale batchgrootte voor één API-oproep is 500.

## <a name="permissions"></a>Machtigingen
Een van de volgende machtigingen is vereist om deze API te bellen. Zie Aan de slag voor meer informatie, inclusief het kiezen van [machtigingen.](apis-intro.md)

Machtigingstype |   Machtiging  |   Weergavenaam machtiging
:---|:---|:---
Toepassing |   Ti.ReadWrite |  'Indicatoren lezen en schrijven'
Toepassing |   Ti.ReadWrite.All |  'Alle indicatoren lezen en schrijven'
Gedelegeerd (werk- of schoolaccount) |    Ti.ReadWrite |  'Indicatoren lezen en schrijven'


## <a name="http-request"></a>HTTP-aanvraag
```
POST https://api.securitycenter.microsoft.com/api/indicators/import
```

## <a name="request-headers"></a>Kopteksten aanvragen

Naam | Type | Beschrijving
:---|:---|:---
Autorisatie | Tekenreeks | Bearer {token}. **Vereist**.
Inhoudstype | tekenreeks | toepassing/json. **Vereist**.

## <a name="request-body"></a>Body aanvragen
In de objectaanvraag moet u een JSON-object de volgende parameters geven:

Parameter | Type    | Beschrijving
:---|:---|:---
Indicatoren | Lijst<[indicator](ti-indicator.md)> | Lijst met [indicatoren](ti-indicator.md). **Vereist**


## <a name="response"></a>Antwoord
- Als dit is gelukt, retourneert deze methode 200 - OK-antwoordcode met een lijst met importresultaten per indicator, zie voorbeeld hieronder.
- Als dit niet is gelukt: met deze methode wordt 400 - Slecht verzoek als return gebruikt. Een slechte aanvraag geeft meestal een onjuiste body aan.

## <a name="example"></a>Voorbeeld

**Aanvraag**

Hier is een voorbeeld van de aanvraag.

```http
POST https://api.securitycenter.microsoft.com/api/indicators/import
```

```json
{
    "Indicators":
    [
        {
            "indicatorValue": "220e7d15b011d7fac48f2bd61114db1022197f7f",
            "indicatorType": "FileSha1",
            "title": "demo",
            "application": "demo-test",
            "expirationTime": "2021-12-12T00:00:00Z",
            "action": "Alert",
            "severity": "Informational",
            "description": "demo2",
            "recommendedActions": "nothing",
            "rbacGroupNames": ["group1", "group2"]
        },
        {
            "indicatorValue": "2233223322332233223322332233223322332233223322332233223322332222",
            "indicatorType": "FileSha256",
            "title": "demo2",
            "application": "demo-test2",
            "expirationTime": "2021-12-12T00:00:00Z",
            "action": "Alert",
            "severity": "Medium",
            "description": "demo2",
            "recommendedActions": "nothing",
            "rbacGroupNames": []
        }
    ]
}
```

**Antwoord**

Hier is een voorbeeld van het antwoord.

```json
{
    "value": [
        {
            "id": "2841",
            "indicator": "220e7d15b011d7fac48f2bd61114db1022197f7f",
            "isFailed": false,
            "failureReason": null
        },
        {
            "id": "2842",
            "indicator": "2233223322332233223322332233223322332233223322332233223322332222",
            "isFailed": false,
            "failureReason": null
        }
    ]
}
```

## <a name="related-topic"></a>Verwant onderwerp
- [Indicatoren beheren](manage-indicators.md)
