---
title: Apparaatgegevens zoeken via interne IP-API
description: Gebruik deze API om oproepen te maken die betrekking hebben op het vinden van een apparaatinvoer rond een specifieke tijdstempel via interne IP.
keywords: ip, api's, graph api, ondersteunde api's, apparaat zoeken, apparaatgegevens
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
ms.openlocfilehash: fa1973d1c53048b04c9135a72e55ec4759412b18
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166709"
---
# <a name="find-device-information-by-internal-ip-api"></a>Apparaatgegevens zoeken via interne IP-API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)

- Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Een apparaat zoeken op intern IP-adres.

>[!NOTE]
>De tijdstempel moet binnen de laatste 30 dagen zijn.

## <a name="permissions"></a>Machtigingen
Een van de volgende machtigingen is vereist om deze API te bellen. Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.

Machtigingstype | Machtiging | Weergavenaam machtiging
:---|:---|:---
Toepassing | Machine.Read.All | 'Alle machineprofielen lezen'
Toepassing | Machine.ReadWrite.All | 'Alle computergegevens lezen en schrijven'

## <a name="http-request"></a>HTTP-aanvraag
```
GET /api/machines/find(timestamp={time},key={IP})
```

## <a name="request-headers"></a>Kopteksten aanvragen

Naam | Type | Beschrijving
:---|:---|:---
Autorisatie | Tekenreeks | Bearer {token}. **Vereist**.


## <a name="request-body"></a>Body aanvragen
Leeg

## <a name="response"></a>Antwoord
Als dit is gelukt en de computer bestaat- 200 OK.
Als er geen computer is gevonden- 404 Niet gevonden.


## <a name="example"></a>Voorbeeld

**Aanvraag**

Hier is een voorbeeld van de aanvraag.

```
GET https://graph.microsoft.com/testwdatppreview/machines/find(timestamp=2018-06-19T10:00:00Z,key='10.166.93.61')
Content-type: application/json
```

**Antwoord**

Hier is een voorbeeld van het antwoord.

Het antwoord retourneerde een lijst met alle apparaten die dit IP-adres binnen zestien minuten vóór en na de tijdstempel hebben gerapporteerd. 

```
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://graph.microsoft.com/testwdatppreview/$metadata#Machines",
    "value": [
        {
            "id": "04c99d46599f078f1c3da3783cf5b95f01ac61bb",
            "computerDnsName": "",
            "firstSeen": "2017-07-06T01:25:04.9480498Z",
            "osPlatform": "Windows10",
…
}
```
