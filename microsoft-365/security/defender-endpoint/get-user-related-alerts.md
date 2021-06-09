---
title: Api voor gebruikerswaarschuwingen ontvangen
description: Een verzameling waarschuwingen ophalen die betrekking hebben op een bepaalde gebruikers-id met Microsoft Defender voor Eindpunt.
keywords: api's, graph api, ondersteunde api's, get, user, related, alerts
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
ms.openlocfilehash: ab0d0e97365b5ce38b29f2b0d65e3aea48d6c28c
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769927"
---
# <a name="get-user-related-alerts-api"></a>Api voor gebruikerswaarschuwingen ontvangen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API-beschrijving
Hiermee wordt een verzameling waarschuwingen opgehaald die betrekking hebben op een bepaalde gebruikers-id.


## <a name="limitations"></a>Beperkingen
1. Tariefbeperkingen voor deze API zijn 100 oproepen per minuut en 1500 oproepen per uur.


## <a name="permissions"></a>Machtigingen
Een van de volgende machtigingen is vereist om deze API te bellen. Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.

Machtigingstype |   Machtiging  |   Weergavenaam machtiging
:---|:---|:---
Toepassing |   Alert.Read.All |    'Alle waarschuwingen lezen'
Toepassing |   Alert.ReadWrite.All |   'Alle waarschuwingen lezen en schrijven'
Gedelegeerd (werk- of schoolaccount) | Alert.Read | 'Leeswaarschuwingen'
Gedelegeerd (werk- of schoolaccount) | Alert.ReadWrite | 'Waarschuwingen lezen en schrijven'

>[!Note]
> Bij het verkrijgen van een token met gebruikersreferenties:
>- De gebruiker moet ten minste de volgende rolmachtiging hebben: 'Gegevens weergeven'. Zie Rollen maken [en beheren voor meer informatie.](user-roles.md)
>- Antwoord bevat alleen waarschuwingen, gekoppeld aan apparaten, die de gebruiker toegang [](machine-groups.md) heeft, op basis van instellingen voor apparaatgroep (Zie Apparaatgroepen maken en beheren voor meer informatie)

## <a name="http-request"></a>HTTP-aanvraag
```
GET /api/users/{id}/alerts
```

**De id is niet de volledige UPN, maar alleen de gebruikersnaam. (bijvoorbeeld om waarschuwingen op te halen voor user1@contoso.com /api/users/user1/alerts)**

## <a name="request-headers"></a>Kopteksten aanvragen

Naam | Type | Beschrijving
:---|:---|:---
Autorisatie | Tekenreeks | Bearer {token}. **Vereist**.


## <a name="request-body"></a>Body aanvragen
Leeg

## <a name="response"></a>Antwoord
Als dit is gelukt en de gebruiker bestaat- 200 OK. Als de gebruiker niet bestaat- 404 Niet gevonden. 


## <a name="example"></a>Voorbeeld

**Aanvraag**

Hier is een voorbeeld van de aanvraag.

```http
GET https://api.securitycenter.microsoft.com/api/users/user1/alerts
```
