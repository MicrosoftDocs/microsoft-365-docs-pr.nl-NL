---
title: Apparaten per softwarelijst maken
description: Een lijst met apparaten ophalen waar deze software is geïnstalleerd.
keywords: api's, graph api, ondersteunde api's, get, list devices, devices list, list devices by software, Microsoft Defender for Endpoint tvm api
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
ms.openlocfilehash: 8312818fe06b5a25ae32bf1f9585a51fe8848de6
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845376"
---
# <a name="list-devices-by-software"></a>Apparaten per softwarelijst maken

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)

- Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

Een lijst met apparaatverwijzingen ophalen waar deze software is geïnstalleerd.

## <a name="permissions"></a>Machtigingen
Een van de volgende machtigingen is vereist om deze API te bellen. Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.

Machtigingstype |   Machtiging  |   Weergavenaam machtiging
:---|:---|:---
Toepassing | Software.Read.All | 'Informatie over bedreigings- en kwetsbaarheidsbeheersoftware lezen'
Gedelegeerd (werk- of schoolaccount) | Software.Lezen | 'Informatie over bedreigings- en kwetsbaarheidsbeheersoftware lezen'

## <a name="http-request"></a>HTTP-aanvraag
```
GET /api/Software/{Id}/machineReferences 
```

## <a name="request-headers"></a>Kopteksten aanvragen

| Naam        | Type | Beschrijving
|:--------------|:-------|:--------------|
| Autorisatie | Tekenreeks | Bearer {token}. **Vereist**.

## <a name="request-body"></a>Body aanvragen
Leeg

## <a name="response"></a>Antwoord
Als dit is gelukt, retourneert deze methode 200 OK en een lijst met apparaten waarop de software in de body is geïnstalleerd. 


## <a name="example"></a>Voorbeeld

**Aanvraag**

Hier is een voorbeeld van de aanvraag.

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/machineReferences
```

**Antwoord**

Hier is een voorbeeld van het antwoord.

```json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineReferences",
    "value": [
        {
            "id": "7c7e1896fa39efb0a32a2cf421d837af1b9bf762",
            "computerDnsName": "dave_desktop",
            "osPlatform": "Windows10",
            "rbacGroupName": "GroupTwo"
        },
        {
            "id": "7d5cc2e7c305e4a0a290392abf6707f9888fda0d",
            "computerDnsName": "jane_PC",
            "osPlatform": "Windows10",
            "rbacGroupName": "GroupTwo"
        }
        ...
    ]
}
```

## <a name="related-topics"></a>Verwante onderwerpen
- [Risicogebaseerd bedreigingsbeheer & kwetsbaarheidsbeheer](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Inventaris van & beveiligingsprobleemsoftware](/microsoft-365/security/defender-endpoint/tvm-software-inventory)
