---
title: Api voor domeinwaarschuwingen ontvangen
description: Lees hoe u de API Voor domeingerelateerde waarschuwingen ophalen gebruikt om waarschuwingen op te halen die betrekking hebben op een bepaald domeinadres in Microsoft Defender voor Eindpunt.
keywords: api's, graph api, ondersteunde api's, get, domein, gerelateerde, waarschuwingen
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
ms.openlocfilehash: f8de54072c0b0ebef69b8e5586fee058b971c51f
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166571"
---
# <a name="get-domain-related-alerts-api"></a>Api voor domeinwaarschuwingen ontvangen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API-beschrijving
Hiermee wordt een verzameling waarschuwingen [opgehaald die](alerts.md) betrekking hebben op een bepaald domeinadres.


## <a name="limitations"></a>Beperkingen
1. U kunt query's uitvoeren op waarschuwingen die het laatst zijn bijgewerkt op basis van de geconfigureerde bewaarperiode.
2. Tariefbeperkingen voor deze API zijn 100 oproepen per minuut en 1500 oproepen per uur.


## <a name="permissions"></a>Machtigingen
Een van de volgende machtigingen is vereist om deze API te bellen. Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.

Machtigingstype |   Machtiging  |   Weergavenaam machtiging
:---|:---|:---
Toepassing |   Alert.Read.All |    'Alle waarschuwingen lezen'
Toepassing |   Alert.ReadWrite.All |   'Alle waarschuwingen lezen en schrijven'
Gedelegeerd (werk- of schoolaccount) | Alert.Read | 'Leeswaarschuwingen'
Gedelegeerd (werk- of schoolaccount) | Alert.ReadWrite | 'Waarschuwingen lezen en schrijven'

>[!Note]
> Bij het verkrijgen van een token met gebruikersreferenties:
>- De gebruiker moet ten minste de volgende rolmachtiging hebben: 'Gegevens weergeven' [(Zie](user-roles.md) Rollen maken en beheren voor meer informatie)
>- Antwoord bevat alleen waarschuwingen, gekoppeld aan apparaten, die de gebruiker toegang [](machine-groups.md) heeft, op basis van instellingen voor apparaatgroep (Zie Apparaatgroepen maken en beheren voor meer informatie)

## <a name="http-request"></a>HTTP-aanvraag
```http
GET /api/domains/{domain}/alerts
```

## <a name="request-headers"></a>Kopteksten aanvragen

| Koptekst        | Value  |
|:--------------|:-------|
| Autorisatie | Tekenreeks |

## <a name="request-body"></a>Body aanvragen
Leeg

## <a name="response"></a>Antwoord
Als dit is gelukt en domein bestaat- [](alerts.md) 200 OK met lijst met waarschuwingsentiteiten. Als domein niet bestaat- 404 Niet gevonden.


## <a name="example"></a>Voorbeeld

**Aanvraag**

Hier is een voorbeeld van de aanvraag.

```http
GET https://api.securitycenter.microsoft.com/api/domains/client.wns.windows.com/alerts
```
