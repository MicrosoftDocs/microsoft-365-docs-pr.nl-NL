---
title: Lijst van software
description: Hiermee wordt een lijst met softwarevoorraad opgehaald
keywords: api's, graph api, ondersteunde api's, get, list, file, information, software inventory, threat & vulnerability management api, Microsoft Defender for Endpoint tvm api
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: f7e71c58396fd4b3ed40ba88aab5c2757ae41a41
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771079"
---
# <a name="list-software-inventory-api"></a>List software inventory API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)

- Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Hiermee wordt de inventaris van de organisatiesoftware opgehaald.

## <a name="permissions"></a>Machtigingen
Een van de volgende machtigingen is vereist om deze API te bellen. Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.

Machtigingstype |   Machtiging  |   Weergavenaam machtiging
:---|:---|:---
Toepassing |Software.Read.All |    'Informatie over bedreigings- en kwetsbaarheidsbeheersoftware lezen'
Gedelegeerd (werk- of schoolaccount) | Software.Lezen |    'Informatie over bedreigings- en kwetsbaarheidsbeheersoftware lezen'

## <a name="http-request"></a>HTTP-aanvraag
```
GET /api/Software
```

## <a name="request-headers"></a>Kopteksten aanvragen

Naam | Type | Omschrijving
:---|:---|:---
Autorisatie | Tekenreeks | Bearer {token}. **Vereist**.


## <a name="request-body"></a>Body aanvragen
Leeg

## <a name="response"></a>Antwoord
Als dit is gelukt, retourneert deze methode 200 OK met de softwarevoorraad in de body.


## <a name="example"></a>Voorbeeld

**Aanvraag**

Hier is een voorbeeld van de aanvraag.

```
GET https://api.securitycenter.microsoft.com/api/Software
```

**Antwoord**

Hier is een voorbeeld van het antwoord.


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Software",
    "value": [
            {
                "id": "microsoft-_-edge",
                "name": "edge",
                "vendor": "microsoft",
                "weaknesses": 467,
                "publicExploit": true,
                "activeAlert": false,
                "exposedMachines": 172,
                "impactScore": 2.39947438
            }
            ...
        ]
}
```

## <a name="related-topics"></a>Verwante onderwerpen
- [Risicogebaseerd bedreigingsbeheer & kwetsbaarheidsbeheer](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Inventaris van & beveiligingsprobleemsoftware](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
