---
title: API voor IP-statistieken krijgen
description: Krijg de meest recente statistieken voor uw IP-adres met Microsoft Defender voor Eindpunt.
keywords: api's, graph api, ondersteunde api's, get, ip, statistics, prevalentie
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 4919f082c115d8a57960ec49532b6cda6a63833f
ms.sourcegitcommit: 787fb30fdae6d49347a87f4baae3cd140067e573
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/17/2021
ms.locfileid: "52998726"
---
# <a name="get-ip-statistics-api"></a>API voor IP-statistieken krijgen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API-beschrijving
Hiermee worden de statistieken voor het opgegeven IP-adres opgehaald.

## <a name="limitations"></a>Beperkingen
1. Tariefbeperkingen voor deze API zijn 100 oproepen per minuut en 1500 oproepen per uur.

## <a name="permissions"></a>Machtigingen
Een van de volgende machtigingen is vereist om deze API te bellen. Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.

Machtigingstype |   Machtiging  |   Weergavenaam machtiging
:---|:---|:---
Toepassing |   Ip.Read.All |   'Ip-adresprofielen lezen'
Gedelegeerd (werk- of schoolaccount) | Ip.Read.All |  'Ip-adresprofielen lezen'

>[!NOTE]
> Bij het verkrijgen van een token met gebruikersreferenties:
>- De gebruiker moet ten minste de volgende rolmachtiging hebben: 'Gegevens weergeven' [(Zie](user-roles.md) Rollen maken en beheren voor meer informatie)

## <a name="http-request"></a>HTTP-aanvraag

```http
GET /api/ips/{ip}/stats
```

## <a name="request-headers"></a>Aanvraagheaders

Naam | Type | Beschrijving
:---|:---|:---
Autorisatie | Tekenreeks | Bearer {token}. **Vereist**.

## <a name="request-uri-parameters"></a>URI-parameters aanvragen

Naam | Type | Beschrijving
:---|:---|:---
lookBackHours | Int32 | Definieert de uren die we terug zoeken om de statistieken te krijgen. Standaard is dit 30 dagen. **Optioneel**.

## <a name="request-body"></a>Aanvraagtekst
Leeg

## <a name="response"></a>Antwoord
Als dit is gelukt en ip bestaat- 200 OK met statistische gegevens in de body. IP bestaat niet - 404 Niet gevonden.


## <a name="example"></a>Voorbeeld

**Aanvraag**

Hier is een voorbeeld van de aanvraag.

```http
GET https://api.securitycenter.microsoft.com/api/ips/10.209.67.177/stats?lookBackHours=48
```

**Antwoord**

Hier is een voorbeeld van het antwoord.


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.InOrgIPStats",
    "ipAddress": "10.209.67.177",
    "organizationPrevalence": 63515,
    "orgFirstSeen": "2017-07-30T13:36:06Z",
    "orgLastSeen": "2017-08-29T13:32:59Z"
}
```


| Naam | Beschrijving |
| :--- | :---------- |
| Organisatieprepresenties | het duidelijke aantal apparaten dat de netwerkverbinding met dit IP-adres heeft geopend. |
| Organisatie die voor het eerst is gezien | de eerste verbinding voor dit IP-adres in de organisatie. |
| Org laatst gezien  | de laatste verbinding voor dit IP-adres in de organisatie. |

> [!NOTE]
> Deze statistische gegevens zijn gebaseerd op gegevens uit de afgelopen 30 dagen. 
