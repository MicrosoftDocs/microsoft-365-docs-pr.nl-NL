---
title: Distributie van softwareversies van lijst
description: Hiermee wordt een lijst met de distributie van de softwareversie van uw organisatie opgehaald
keywords: api's, graph api, ondersteunde api's, get, distributie van softwareversies, mdatp tvm-api
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
ms.openlocfilehash: 88f446ddd87768817099c1a206bab17aa8be5b7b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198575"
---
# <a name="list-software-version-distribution"></a>Distributie van softwareversies van lijst 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)

- Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

Hiermee wordt een lijst met de distributie van de softwareversie van uw organisatie opgehaald. 

## <a name="permissions"></a>Machtigingen
Een van de volgende machtigingen is vereist om deze API te bellen. Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.

Machtigingstype |   Machtiging  |   Weergavenaam machtiging
:---|:---|:---
Toepassing | Software.Read.All | 'Informatie over bedreigings- en kwetsbaarheidsbeheersoftware lezen'
Gedelegeerd (werk- of schoolaccount) | Software.Lezen | 'Informatie over bedreigings- en kwetsbaarheidsbeheersoftware lezen'

## <a name="http-request"></a>HTTP-aanvraag
```
GET /api/Software/{Id}/distributions
```

## <a name="request-headers"></a>Kopteksten aanvragen

| Naam        | Type | Beschrijving
|:--------------|:-------|:--------------|
| Autorisatie | Tekenreeks | Bearer {token}. **Vereist**.

## <a name="request-body"></a>Body aanvragen
Leeg

## <a name="response"></a>Antwoord
Als dit lukt, retourneert deze methode 200 OK met een lijst met gegevens over softwaredistributies in de body. 


## <a name="example"></a>Voorbeeld

**Aanvraag**

Hier is een voorbeeld van de aanvraag.

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/distributions
```

**Antwoord**

Hier is een voorbeeld van het antwoord.

```json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Distributions",
    "value": [
        {
            "version": "11.0.17134.1039",
            "installations": 1,
            "vulnerabilities": 11
        },
        {
            "version": "11.0.18363.535",
            "installations": 750,
            "vulnerabilities": 0
        }
        ...
    ]
}
```

## <a name="related-topics"></a>Verwante onderwerpen
- [Risicogebaseerd bedreigingsbeheer & kwetsbaarheidsbeheer](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Inventaris van & beveiligingsprobleemsoftware](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
