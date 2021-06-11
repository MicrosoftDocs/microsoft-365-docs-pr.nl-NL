---
title: Api voor computeractie annuleren
description: Meer informatie over het annuleren van een al gestarte machineactie
keywords: api's, graph api,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 490ee91d5f2d2c02174be94c52fc83fd0ec0fc5e
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879696"
---
#   <a name="cancel-machine-action-api"></a>Api voor computeractie annuleren 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2146631)

[!include[Prerelease information](../../includes/prerelease.md)]

>Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API-beschrijving

Een al gestarte machineactie annuleren die nog niet definitief is (voltooid, geannuleerd, mislukt).

## <a name="limitations"></a>Beperkingen

1.  Tariefbeperkingen voor deze API zijn 100 oproepen per minuut en 1500 oproepen per uur.

## <a name="permissions"></a>Machtigingen

Een van de volgende machtigingen is vereist om deze API te bellen. Zie Aan de slag voor meer informatie, waaronder hoe u machtigingen [kiest.](apis-intro.md)

|     Machtigingstype     |     Machtiging     |    Weergavenaam machtiging     |
|-|-|-|
|    <br>Toepassing    |    <br>Machine.CollectForensic<br>   Machine.Isolate   <br>Machine.RestrictExecution<br>   Machine.Scannen<br>   Machine.Offboard<br>   Machine.StopAndQuarantine<br>   Machine.LiveResponse    |    Gerechtelijke gegevens verzamelen   <br>Machine isoleren<br>De uitvoering van code beperken<br>  Scanapparaat<br>  Offboard-machine<br>   Stoppen en quarantaine<br>   Livereactie uitvoeren op een specifieke computer    |
|    <br>Gedelegeerd (werk- of schoolaccount)    |    Machine.CollectForensic<br>   Machine.Isolate    <br>Machine.RestrictExecution<br>   Machine.Scannen<br>   Machine.Offboard<br>   Machine.StopAndQuarantineMachine.LiveResponse    |    Gerechtelijke gegevens verzamelen<br>   Machine isoleren<br>  De uitvoering van code beperken<br> Scanapparaat<br>Offboard-machine<br> Stoppen en quarantaine<br> Livereactie uitvoeren op een specifieke computer    |


## <a name="http-request"></a>HTTP-aanvraag

```
POST https://api.securitycenter.microsoft.com/api/machineactions/<machineactionid>/cancel  
```


## <a name="request-headers"></a>Kopteksten aanvragen

| Naam      | Type | Omschrijving                 |
|---------------|----------|---------------------------------|
| Autorisatie | Tekenreeks   | Bearer {token}. Vereist.   |
| Inhoudstype  | tekenreeks   | toepassing/json. Vereist. |

## <a name="request-body"></a>Body aanvragen

| Parameter | Type | Omschrijving                        |
|---------------|----------|----------------------------------------|
| Opmerking       | Tekenreeks   | Opmerking om te koppelen aan de annuleringsactie.  |

## <a name="response"></a>Antwoord

Als dit is gelukt, retourneert deze methode 200, Ok-antwoordcode met een entiteit Machineactie. Als de entiteit machineactie met de opgegeven id niet is gevonden- 404 Niet gevonden.

## <a name="example"></a>Voorbeeld

**Aanvraag**

Hier is een voorbeeld van de aanvraag.

```HTTP
POST
https://api.securitycenter.microsoft.com/api/machineactions/988cc94e-7a8f-4b28-ab65-54970c5d5018/cancel
```


```JSON
{
    "Comment": "Machine action was canceled by automation"
}
```

## <a name="related-topic"></a>Verwant onderwerp

- [Api voor machineactie krijgen](get-machineaction-object.md)