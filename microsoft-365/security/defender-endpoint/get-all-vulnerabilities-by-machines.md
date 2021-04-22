---
title: Alle beveiligingslekken per computer en software krijgen
description: Hiermee wordt een lijst opgehaald met alle beveiligingslekken die van invloed zijn op de organisatie door Machine en Software
keywords: api's, graph api, ondersteunde api's, get, vulnerability information, Microsoft Defender for Endpoint tvm api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: mde
ms.openlocfilehash: 229c1f9e77a0cb85744155e82934b48dd63052b2
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933407"
---
# <a name="list-vulnerabilities-by-machine-and-software"></a>Lijst van beveiligingsproblemen per computer en software

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


Hiermee wordt een lijst opgehaald met alle beveiligingslekken die van invloed zijn op de organisatie per [computer](machine.md) en [software.](software.md)
- Als het beveiligingsprobleem een kb-fix heeft, wordt deze weergegeven in het antwoord.
- Ondersteunt [OData V4-query's.](https://www.odata.org/documentation/)
- De OData ```$filter``` wordt ondersteund voor alle eigenschappen.

>[!Tip]
>Dit is een geweldige API voor [Power BI-integratie.](api-power-bi.md)

## <a name="permissions"></a>Machtigingen
Een van de volgende machtigingen is vereist om deze API te bellen. Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.

Machtigingstype |   Machtiging  |   Weergavenaam machtiging
:---|:---|:---
Toepassing |   Kwetsbaarheid.Read.All |    'Informatie over kwetsbaarheidsinformatie over bedreigings- en kwetsbaarheidsbeheer lezen'
Gedelegeerd (werk- of schoolaccount) | Kwetsbaarheid.Lezen |   'Informatie over kwetsbaarheidsinformatie over bedreigings- en kwetsbaarheidsbeheer lezen'

## <a name="http-request"></a>HTTP-aanvraag
```
GET /api/vulnerabilities/machinesVulnerabilities
```

## <a name="request-headers"></a>Kopteksten aanvragen

Naam | Type | Beschrijving
:---|:---|:---
Autorisatie | Tekenreeks | Bearer {token}. **Vereist**.


## <a name="request-body"></a>Body aanvragen
Leeg

## <a name="response"></a>Antwoord
Als dit is gelukt, retourneert deze methode 200 OK met de lijst met beveiligingslekken in de body.


## <a name="example"></a>Voorbeeld

**Aanvraag**

Hier is een voorbeeld van de aanvraag.

```http
GET https://api.securitycenter.microsoft.com/api/vulnerabilities/machinesVulnerabilities
```

**Antwoord**

Hier is een voorbeeld van het antwoord.


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.PublicAssetVulnerabilityDto)",
    "value": [
        {
            "id": "5afa3afc92a7c63d4b70129e0a6f33f63a427e21-_-CVE-2020-6494-_-microsoft-_-edge_chromium-based-_-81.0.416.77-_-",
            "cveId": "CVE-2020-6494",
            "machineId": "5afa3afc92a7c63d4b70129e0a6f33f63a427e21",
            "fixingKbId": null,
            "productName": "edge_chromium-based",
            "productVendor": "microsoft",
            "productVersion": "81.0.416.77",
            "severity": "Low"
        },
        {
            "id": "7a704e17d1c2977c0e7b665fb18ae6e1fe7f3283-_-CVE-2016-3348-_-microsoft-_-windows_server_2012_r2-_-6.3.9600.19728-_-3185911",
            "cveId": "CVE-2016-3348",
            "machineId": "7a704e17d1c2977c0e7b665fb18ae6e1fe7f3283",
            "fixingKbId": "3185911",
            "productName": "windows_server_2012_r2",
            "productVendor": "microsoft",
            "productVersion": "6.3.9600.19728",
            "severity": "Low"
        },
        ...
    ]

}
```

## <a name="see-also"></a>Zie ook

- [Risicogebaseerd bedreigings- en kwetsbaarheidsbeheer](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Beveiligingslekken in uw organisatie](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-weaknesses)
