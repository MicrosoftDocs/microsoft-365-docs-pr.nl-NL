---
title: CVE-KB-map-API krijgen
description: Meer informatie over het gebruik van de MAP-API VOOR CVE-KB ophalen om een kaart van CVE's op te halen naar KB-gegevens en CVE-gegevens in Microsoft Defender voor Eindpunt.
keywords: api's, graph api, ondersteunde api's, get, cve, kb
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: leonidzh
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ROBOTS: NOINDEX
ms.technology: mde
ms.openlocfilehash: 85c4d82f07354193fb1e997abb98dbdaa02dc8ef
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166583"
---
# <a name="get-cve-kb-map-api"></a>CVE-KB-map-API krijgen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Hiermee wordt een kaart met CVE's naar KB-gegevens en CVE-gegevens opgehaald.

## <a name="permissions"></a>Machtigingen
Gebruiker heeft leesmachtigingen nodig.

## <a name="http-request"></a>HTTP-aanvraag
```
GET /testwdatppreview/cvekbmap
```

## <a name="request-headers"></a>Kopteksten aanvragen

Koptekst | Waarde 
:---|:---
Autorisatie | Bearer {token}. **Vereist**.
Inhoudstype | toepassing/json

## <a name="request-body"></a>Body aanvragen
Leeg

## <a name="response"></a>Antwoord
Als dit is gelukt en de kaart bestaat- 200 OK.

## <a name="example"></a>Voorbeeld

**Aanvraag**

Hier is een voorbeeld van de aanvraag.

```http
GET https://graph.microsoft.com/testwdatppreview/CveKbMap
```

**Antwoord**

Hier is een voorbeeld van het antwoord.

```json
{
    "@odata.context":"https://graph.microsoft.com/testwdatppreview/$metadata#CveKbMap",
    "@odata.count": 4168,
    "value": [
        {
            "cveKbId": "CVE-2015-2482-3097617",
            "cveId": "CVE-2015-2482",
            "kbId":"3097617",
            "title": "Cumulative Security Update for Internet Explorer",
            "severity": "Critical"
        },
    …
}

```
