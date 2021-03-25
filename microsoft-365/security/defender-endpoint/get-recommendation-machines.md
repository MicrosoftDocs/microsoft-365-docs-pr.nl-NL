---
title: Lijstapparaten op aanbeveling
description: Hiermee wordt een lijst opgehaald met apparaten die zijn gekoppeld aan de beveiligingsaanbeveling.
keywords: api's, graph api, ondersteunde api's, get, beveiligingsaanbeveling voor kwetsbare apparaten, bedreigings- en kwetsbaarheidsbeheer, bedreigings- en kwetsbaarheidsbeheer-api
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
ms.openlocfilehash: 515542f6eca208e92228a8d0b344b6013b11a148
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198267"
---
# <a name="list-devices-by-recommendation"></a>Lijstapparaten op aanbeveling

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)

> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

Hiermee wordt een lijst opgehaald met apparaten die zijn gekoppeld aan de beveiligingsaanbeveling.

## <a name="permissions"></a>Machtigingen
Een van de volgende machtigingen is vereist om deze API te bellen. Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.

Machtigingstype |   Machtiging  |   Weergavenaam machtiging
:---|:---|:---
Toepassing |   SecurityRecommendation.Read.All |   'Informatie over beveiligingsaanbeveling bedreigings- en kwetsbaarheidsbeheer lezen'
Gedelegeerd (werk- of schoolaccount) | SecurityRecommendation.Read |  'Informatie over beveiligingsaanbeveling bedreigings- en kwetsbaarheidsbeheer lezen'

## <a name="http-request"></a>HTTP-aanvraag
```
GET /api/recommendations/{id}/machineReferences
```

## <a name="request-headers"></a>Kopteksten aanvragen

Naam | Type | Beschrijving
:---|:---|:---
Autorisatie | Tekenreeks | Bearer {token}. **Vereist**.


## <a name="request-body"></a>Body aanvragen
Leeg

## <a name="response"></a>Antwoord
Als dit is gelukt, retourneert deze methode 200 OK met de lijst met apparaten die zijn gekoppeld aan de beveiligingsaanbeveling.


## <a name="example"></a>Voorbeeld

**Aanvraag**

Hier is een voorbeeld van de aanvraag.

```
GET https://api.securitycenter.microsoft.com/api/recommendations/va-_-google-_-chrome/machineReferences
```

**Antwoord**

Hier is een voorbeeld van het antwoord.

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineReferences",
    "value": [
        {
            "id": "e058770379bc199a9c179ce52a23e16fd44fd2ee",
            "computerDnsName": "niw_pc",
            "osPlatform": "Windows10",
            "rbacGroupName": "GroupTwo"
        }
        ...
    ]
}
```

## <a name="related-topics"></a>Verwante onderwerpen
- [Risicogebaseerd bedreigingsbeheer & kwetsbaarheidsbeheer](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Aanbeveling & beveiligingsaanbeveling voor bedreigingen](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)
