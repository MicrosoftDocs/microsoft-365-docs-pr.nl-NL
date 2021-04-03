---
title: Secure Score voor apparaten ophalen
description: Hiermee wordt de beveiligde score van het organisatieapparaat opgehaald.
keywords: api's, graph api, ondersteunde api's, get, waarschuwingen, recent
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: dansimp
ms.author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: db4682d0d2fccd7504eb46d9099a9783408cfb73
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570934"
---
# <a name="get-device-secure-score"></a>Secure Score voor apparaten ophalen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)

- Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


Haalt uw [Microsoft Secure Score voor apparaten op.](tvm-microsoft-secure-score-devices.md) Een hogere Microsoft Secure Score voor apparaten betekent dat uw eindpunten beter bestand zijn tegen cyberbeveiligingsaanvallen. 

## <a name="permissions"></a>Machtigingen

Een van de volgende machtigingen is vereist om deze API te bellen. Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.

Machtigingstype |   Machtiging  |   Weergavenaam machtiging
:---|:---|:---
Toepassing |   Score.Read.Alll |   'Score bedreigings- en kwetsbaarheidsbeheer lezen'
Gedelegeerd (werk- of schoolaccount) | Score.Read | 'Score bedreigings- en kwetsbaarheidsbeheer lezen'

## <a name="http-request"></a>HTTP-aanvraag

```
GET /api/configurationScore
```

## <a name="request-headers"></a>Kopteksten aanvragen

Naam | Type | Omschrijving
:---|:---|:---
Autorisatie | Tekenreeks | Bearer {token}. **Vereist**.

## <a name="request-body"></a>Body aanvragen

Leeg

## <a name="response"></a>Antwoord

Als dit is gelukt, retourneert deze methode 200 OK, waarbij de veilige scoregegevens van het apparaat in de antwoord-body worden gebruikt.

## <a name="example"></a>Voorbeeld

### <a name="request"></a>Aanvraag

Hier is een voorbeeld van de aanvraag.

```http
GET https://api.securitycenter.microsoft.com/api/configurationScore
```

### <a name="response"></a>Antwoord

Hier is een voorbeeld van het antwoord.

>[!NOTE]
>De hier weergegeven antwoordlijst kan worden afgekapt voor beknoptheid. 

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ConfigurationScore/$entity",
    "time": "2019-12-03T09:15:58.1665846Z",
    "score": 340
}
```

## <a name="see-also"></a>Zie ook

- [OData-query's met Microsoft Defender voor Eindpunt](exposed-apis-odata-samples.md)
