---
title: Gevonden beveiligingsproblemen ophalen
description: Hiermee wordt een verzameling gevonden beveiligingslekken met betrekking tot een bepaalde apparaat-id opgehaald.
keywords: api's, graph api, ondersteunde api's, get, list, file, information, discovered vulnerabilities, threat & vulnerability management api, Microsoft Defender for Endpoint tvm api
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 73d9803736df546f2381b7a84c9089d2460c4c44
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843080"
---
# <a name="get-discovered-vulnerabilities"></a>Gevonden beveiligingsproblemen ophalen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API-beschrijving
Hiermee wordt een verzameling gevonden beveiligingslekken met betrekking tot een bepaalde apparaat-id opgehaald.

## <a name="limitations"></a>Beperkingen
1. Tariefbeperkingen voor deze API zijn 50 oproepen per minuut en 1500 oproepen per uur.

## <a name="permissions"></a>Machtigingen

Een van de volgende machtigingen is vereist om deze API te bellen. Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.

Machtigingstype | Machtiging | Weergavenaam machtiging
:---|:---|:---
Toepassing |Kwetsbaarheid.Read.All | 'Informatie over kwetsbaarheidsinformatie over bedreigings- en kwetsbaarheidsbeheer lezen'
Gedelegeerd (werk- of schoolaccount) | Kwetsbaarheid.Lezen | 'Informatie over kwetsbaarheidsinformatie over bedreigings- en kwetsbaarheidsbeheer lezen'

## <a name="http-request"></a>HTTP-aanvraag

```
GET /api/machines/{machineId}/vulnerabilities
```

## <a name="request-headers"></a>Kopteksten aanvragen

Naam | Type | Beschrijving
:---|:---|:---
Autorisatie | Tekenreeks | Bearer {token}. **Vereist**.

## <a name="request-body"></a>Body aanvragen

Leeg

## <a name="response"></a>Antwoord

Als dit is gelukt, retourneert deze methode 200 OK met de gevonden kwetsbaarheidsgegevens in de body.

## <a name="example"></a>Voorbeeld

### <a name="request"></a>Aanvraag

Hier is een voorbeeld van de aanvraag.

```http
GET https://api.securitycenter.microsoft.com/api/machines/ac233fa6208e1579620bf44207c4006ed7cc4501/vulnerabilities
```

### <a name="response"></a>Antwoord

Hier is een voorbeeld van het antwoord.

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(Analytics.Contracts.PublicAPI.PublicVulnerabilityDto)",
    "value": [
        {
            "id": "CVE-2019-1348",
            "name": "CVE-2019-1348",
            "description": "Git could allow a remote attacker to bypass security restrictions, caused by a flaw in the --export-marks option of git fast-import. By persuading a victim to import specially-crafted content, an attacker could exploit this vulnerability to overwrite arbitrary paths.",
            "severity": "Medium",
            "cvssV3": 4.3,
            "exposedMachines": 1,
            "publishedOn": "2019-12-13T00:00:00Z",
            "updatedOn": "2019-12-13T00:00:00Z",
            "publicExploit": false,
            "exploitVerified": false,
            "exploitInKit": false,
            "exploitTypes": [],
            "exploitUris": []
        }
}
```

## <a name="see-also"></a>Zie ook

- [Risicogebaseerd bedreigingsbeheer & kwetsbaarheidsbeheer](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Beveiligingslekken in uw organisatie](/microsoft-365/security/defender-endpoint/tvm-weaknesses)
