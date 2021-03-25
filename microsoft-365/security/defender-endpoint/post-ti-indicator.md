---
title: Api voor indicator verzenden of bijwerken
description: Lees hoe u de API Voor verzenden of bijwerken kunt gebruiken om een nieuwe indicatorentiteit in Microsoft Defender voor eindpunt in te dienen of bij te werken.
keywords: api's, graph api, ondersteunde api's, submit, ti, indicator, update
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: mde
ms.openlocfilehash: 42bab0a9d20d5e1ef78b98b3538cef209240d890
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187130"
---
# <a name="submit-or-update-indicator-api"></a>Api voor indicator verzenden of bijwerken

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API-beschrijving
Verstuurt of werkt de nieuwe [indicatorentiteit](ti-indicator.md) bij.
<br>CIDR-notatie voor IPs wordt niet ondersteund.

## <a name="limitations"></a>Beperkingen
1. Tariefbeperkingen voor deze API zijn 100 oproepen per minuut en 1500 oproepen per uur.
2. Er is een limiet van 15.000 actieve indicatoren per tenant. 


## <a name="permissions"></a>Machtigingen
Een van de volgende machtigingen is vereist om deze API te bellen. Zie Aan de slag voor meer informatie, inclusief het kiezen van [machtigingen.](apis-intro.md)

Machtigingstype |   Machtiging  |   Weergavenaam machtiging
:---|:---|:---
Toepassing |   Ti.ReadWrite |  'Indicatoren lezen en schrijven'
Toepassing |   Ti.ReadWrite.All |  'Alle indicatoren lezen en schrijven'
Gedelegeerd (werk- of schoolaccount) |    Ti.ReadWrite |  'Indicatoren lezen en schrijven'


## <a name="http-request"></a>HTTP-aanvraag
```
POST https://api.securitycenter.microsoft.com/api/indicators
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
indicatorValue | Tekenreeks | Identiteit van de [entiteit Indicator.](ti-indicator.md) **Vereist**
indicatorType | Enum | Type indicator. Mogelijke waarden zijn: "FileSha1", "FileSha256", "IpAddress", "DomainName" en "Url". **Vereist**
actie | Enum | De actie die wordt ondernomen als de indicator wordt gevonden in de organisatie. Mogelijke waarden zijn: 'Waarschuwing', 'AlertAndBlock' en 'Toegestaan'. **Vereist**
toepassing | Tekenreeks | De toepassing die aan de indicator is gekoppeld. **Optioneel**
titel | Tekenreeks | Indicatorwaarschuwingstitel. **Vereist**
beschrijving | Tekenreeks | Beschrijving van de indicator. **Vereist**
verlooptijd | DateTimeOffset | De verlooptijd van de indicator. **Optioneel**
ernst | Enum | De ernst van de indicator. mogelijke waarden zijn: 'Informatief', 'Laag', 'Gemiddeld' en 'Hoog'. **Optioneel**
aanbevolenActie | Tekenreeks | Aanbevolen acties voor ti-indicatorwaarschuwingen. **Optioneel**
rbacGroupNames | Tekenreeks | Door komma's gescheiden lijst met RBAC-groepsnamen waar de indicator op zou worden toegepast. **Optioneel**


## <a name="response"></a>Antwoord
- Als dit is gelukt, retourneert deze methode 200 - OK-antwoordcode en de aangemaakte / bijgewerkte [indicator-entiteit](ti-indicator.md) in de antwoordinstelling.
- Als dit niet is gelukt: met deze methode wordt 400 - Slecht verzoek als return gebruikt. Een slechte aanvraag geeft meestal een onjuiste body aan.

## <a name="example"></a>Voorbeeld

**Aanvraag**

Hier is een voorbeeld van de aanvraag.

```http
POST https://api.securitycenter.microsoft.com/api/indicators
```

```json
{
    "indicatorValue": "220e7d15b011d7fac48f2bd61114db1022197f7f",
    "indicatorType": "FileSha1",
    "title": "test",
    "application": "demo-test",
    "expirationTime": "2020-12-12T00:00:00Z",
    "action": "AlertAndBlock",
    "severity": "Informational",
    "description": "test",
    "recommendedActions": "nothing",
    "rbacGroupNames": ["group1", "group2"]
}
```

## <a name="related-topic"></a>Verwant onderwerp
- [Indicatoren beheren](manage-indicators.md)
