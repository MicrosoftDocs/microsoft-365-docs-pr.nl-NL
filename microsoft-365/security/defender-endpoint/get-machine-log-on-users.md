---
title: API voor gebruikers van computerlogen krijgen
description: Meer informatie over het gebruik van de API Voor gebruikers van computermelding ophalen om een verzameling aangemelde gebruikers op te halen op een apparaat in Microsoft Defender voor Eindpunt.
keywords: api's, graph api, ondersteunde api's, krijgen, apparaat, aanmelden, gebruikers
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
ms.openlocfilehash: 1c81d2978677b751a8085f88b5c4732fd4a5a247
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770047"
---
# <a name="get-machine-logon-users-api"></a>API voor gebruikers van computerlogen krijgen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API-beschrijving
Hiermee wordt een verzameling aangemelde gebruikers op een bepaald apparaat opgehaald.


## <a name="limitations"></a>Beperkingen
1. U kunt query's uitvoeren op waarschuwingen die het laatst zijn bijgewerkt op basis van de geconfigureerde bewaarperiode.
2. Tariefbeperkingen voor deze API zijn 100 oproepen per minuut en 1500 oproepen per uur.


## <a name="permissions"></a>Machtigingen
Een van de volgende machtigingen is vereist om deze API te bellen. Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.

Machtigingstype |   Machtiging  |   Weergavenaam machtiging
:---|:---|:---
Toepassing |   User.Read.All | 'Gebruikersprofielen lezen'
Gedelegeerd (werk- of schoolaccount) | User.Read.All | 'Gebruikersprofielen lezen'

>[!Note]
> Bij het verkrijgen van een token met gebruikersreferenties:
>- De gebruiker moet ten minste de volgende rolmachtiging hebben: 'Gegevens weergeven'. Zie Rollen maken [en beheren voor meer informatie](user-roles.md) .
>- Het antwoord bevat alleen gebruikers als het apparaat zichtbaar is voor de gebruiker, op basis van de instellingen van de apparaatgroep. Zie Apparaatgroepen maken en beheren voor meer [informatie.](machine-groups.md)

## <a name="http-request"></a>HTTP-aanvraag
```http
GET /api/machines/{id}/logonusers
```

## <a name="request-headers"></a>Kopteksten aanvragen

Naam | Type | Beschrijving
:---|:---|:---
Autorisatie | Tekenreeks | Bearer {token}. **Vereist**.


## <a name="request-body"></a>Body aanvragen
Leeg

## <a name="response"></a>Antwoord
Als dit is gelukt en het apparaat [](user.md) bestaat- 200 OK met een lijst met gebruikersentiteiten in de body. Als het apparaat niet is gevonden- 404 Niet gevonden.


## <a name="example"></a>Voorbeeld

**Aanvraag**

Hier is een voorbeeld van de aanvraag.

```http
GET https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/logonusers
```

**Antwoord**

Hier is een voorbeeld van het antwoord.


```http
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Users",
    "value": [
        {
            "id": "contoso\\user1",
            "accountName": "user1",
            "accountDomain": "contoso",
            "accountSid": "S-1-5-21-72051607-1745760036-109187956-93922",
            "firstSeen": "2019-12-18T08:02:54Z",
            "lastSeen": "2020-01-06T08:01:48Z",
            "logonTypes": "Interactive",
            "logOnMachinesCount": 8,
            "isDomainAdmin": true,
            "isOnlyNetworkUser": false
        },
        ...
    ]
}
```
