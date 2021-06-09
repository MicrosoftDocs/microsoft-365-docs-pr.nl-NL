---
title: Beveiligingsaanbevelingen ophalen
description: Hiermee wordt een verzameling beveiligingsaanbevelingen opgehaald die betrekking hebben op een bepaalde apparaat-id.
keywords: api's, graph api, ondersteunde api's, get, list, file, information, security recommendation per device, threat & vulnerability management api, Microsoft Defender for Endpoint tvm api
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
ms.openlocfilehash: 4498761fd21331821cf4676bfe65630be5436ce5
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845127"
---
# <a name="get-security-recommendations"></a>Beveiligingsaanbevelingen ophalen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)

> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

Hiermee wordt een verzameling beveiligingsaanbevelingen opgehaald die betrekking hebben op een bepaalde apparaat-id.

## <a name="permissions"></a>Machtigingen
Een van de volgende machtigingen is vereist om deze API te bellen. Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.

Machtigingstype |   Machtiging  |   Weergavenaam machtiging
:---|:---|:---
Toepassing | SecurityRecommendation.Read.All | 'Informatie over beveiligingsaanbeveling bedreigings- en kwetsbaarheidsbeheer lezen'
Gedelegeerd (werk- of schoolaccount) | SecurityRecommendation.Read |  'Informatie over beveiligingsaanbeveling bedreigings- en kwetsbaarheidsbeheer lezen'

## <a name="http-request"></a>HTTP-aanvraag
```
GET /api/machines/{machineId}/recommendations
```

## <a name="request-headers"></a>Kopteksten aanvragen

Naam | Type | Beschrijving
:---|:---|:---
Autorisatie | Tekenreeks | Bearer {token}. **Vereist**.


## <a name="request-body"></a>Body aanvragen
Leeg

## <a name="response"></a>Antwoord
Als dit is gelukt, retourneert deze methode 200 OK met de beveiligingsaanbevelingen in de body.


## <a name="example"></a>Voorbeeld

**Aanvraag**

Hier is een voorbeeld van de aanvraag.

```
GET https://api.securitycenter.microsoft.com/api/machines/ac233fa6208e1579620bf44207c4006ed7cc4501/recommendations
```

**Antwoord**

Hier is een voorbeeld van het antwoord.


```
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Recommendations",
    "value": [
        {
            "id": "va-_-git-scm-_-git",
            "productName": "git",
            "recommendationName": "Update Git to version 2.24.1.2",
            "weaknesses": 3,
            "vendor": "git-scm",
            "recommendedVersion": "2.24.1.2",
            "recommendationCategory": "Application",
            "subCategory": "",
            "severityScore": 0,
            "publicExploit": false,
            "activeAlert": false,
            "associatedThreats": [],
            "remediationType": "Update",
            "status": "Active",
            "configScoreImpact": 0,
            "exposureImpact": 0,
            "totalMachineCount": 0,
            "exposedMachinesCount": 1,
            "nonProductivityImpactedAssets": 0,
            "relatedComponent": "Git"
        },
…
}
```

## <a name="related-topics"></a>Verwante onderwerpen
- [Risicogebaseerd bedreigingsbeheer & kwetsbaarheidsbeheer](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Aanbeveling & beveiligingsaanbeveling voor bedreigingen](/microsoft-365/security/defender-endpoint/tvm-security-recommendation)
