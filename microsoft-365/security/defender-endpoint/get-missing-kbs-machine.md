---
title: Ontbrekende KBs op apparaat-id krijgen
description: Haalt ontbrekende beveiligingsupdates op via apparaat-id
keywords: api's, graph api, ondersteunde api's, get, list, file, information, device id, threat & vulnerability management api, Microsoft Defender for Endpoint tvm api
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: aa22b90b95788d9f5a65d54c7a335a2e0f4c3091
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933575"
---
# <a name="get-missing-kbs-by-device-id"></a>Ontbrekende KBs op apparaat-id krijgen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)

- Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Hiermee worden ontbrekende KBs (beveiligingsupdates) opgehaald op apparaat-id

## <a name="http-request"></a>HTTP-aanvraag

```
GET /api/machines/{machineId}/getmissingkbs
```

## <a name="request-header"></a>Koptekst aanvragen

Naam | Type | Beschrijving
:---|:---|:---
Autorisatie | Tekenreeks | Bearer {token}. **Vereist**.

## <a name="request-body"></a>Body aanvragen

Leeg

## <a name="response"></a>Antwoord

Als dit is gelukt, retourneert deze methode 200 OK, waarbij op het opgegeven apparaat kbgegevens ontbreken in de body.

## <a name="example"></a>Voorbeeld

### <a name="request"></a>Aanvraag

Hier is een voorbeeld van de aanvraag.

```
GET https://api.securitycenter.microsoft.com/api/machines/2339ad14a01bd0299afb93dfa2550136057bff96/getmissingkbs 
```

### <a name="response"></a>Antwoord

Hier is een voorbeeld van het antwoord.


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.PublicProductFixDto)",
    "value": [
        {
            "id": "4540673",
            "name": "March 2020 Security Updates",
            "productsNames": [
                "windows_10",
                "edge",
                "internet_explorer"
            ],
            "url": "https://catalog.update.microsoft.com/v7/site/Search.aspx?q=KB4540673",
            "machineMissedOn": 1,
            "cveAddressed": 97
        },
         ...
        ]
}
```

## <a name="related-topics"></a>Verwante onderwerpen

- [Risicogebaseerd bedreigingsbeheer & kwetsbaarheidsbeheer](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Inventaris van & beveiligingsprobleemsoftware](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
