---
title: KB-verzameling-API ophalen
description: Haal een verzameling kennisbases (KB's) en KB-gegevens op met Microsoft Defender voor Eindpunt.
keywords: api's, graph api, ondersteunde api's, get, kb
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
ms.openlocfilehash: 7becfc4a7246dc32aa244dc96ea423f5d31877f9
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166727"
---
# <a name="get-kb-collection-api"></a>KB-verzameling-API ophalen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Hiermee wordt een verzameling KB-gegevens en KB-gegevens opgehaald.

## <a name="permissions"></a>Machtigingen
Gebruiker heeft leesmachtigingen nodig.

## <a name="http-request"></a>HTTP-aanvraag
```
GET /testwdatppreview/kbinfo
```

## <a name="request-headers"></a>Kopteksten aanvragen

Koptekst | Waarde 
:---|:---
Autorisatie | Bearer {token}. **Vereist**.
Inhoudstype | toepassing/json

## <a name="request-body"></a>Body aanvragen
Leeg

## <a name="response"></a>Antwoord
Als dit is gelukt- 200 OK.

## <a name="example"></a>Voorbeeld

**Aanvraag**

Hier is een voorbeeld van de aanvraag.

```http
GET https://graph.microsoft.com/testwdatppreview/KbInfo
```

**Antwoord**

Hier is een voorbeeld van het antwoord.

```json
{
    "@odata.context": "https://graph.microsoft.com/testwdatppreview/$metadata#KbInfo",
    "@odata.count": 271,
    "value":[
        {
            "id": "KB3097617 (10240.16549) Amd64",
            "release": "KB3097617 (10240.16549)",
            "publishingDate": "2015-10-16T21:00:00Z",
            "version": "10.0.10240.16549",
            "architecture": "Amd64"
        },
        …
}
```
