---
title: Machine-API isoleren
description: Meer informatie over het gebruik van de API van isolate machine om een apparaat te isoleren van toegang tot een extern netwerk in Microsoft Defender voor Eindpunt.
keywords: api's, graph api, ondersteunde api's, isoleert apparaat
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
ms.technology: mde
ms.openlocfilehash: b9c8d4da528ba065dc1b4a68ddaa816a1ad78c4a
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187830"
---
# <a name="isolate-machine-api"></a>Machine-API isoleren

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API-beschrijving
Isoleert een apparaat voor toegang tot een extern netwerk.


## <a name="limitations"></a>Beperkingen
1. Tariefbeperkingen voor deze API zijn 100 oproepen per minuut en 1500 oproepen per uur.


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a>Machtigingen
Een van de volgende machtigingen is vereist om deze API te bellen. Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.

Machtigingstype |   Machtiging  |   Weergavenaam machtiging
:---|:---|:---
Toepassing |   Machine.Isolate |   'Isolate machine'
Gedelegeerd (werk- of schoolaccount) | Machine.Isolate |  'Isolate machine'

>[!Note]
> Bij het verkrijgen van een token met gebruikersreferenties:
>- De gebruiker moet ten minste de volgende rolmachtiging hebben: 'Active remediation actions' (Zie [Rollen](user-roles.md) maken en beheren voor meer informatie)
>- De gebruiker moet toegang hebben tot het apparaat op basis van apparaatgroepinstellingen (Zie [Apparaatgroepen](machine-groups.md) maken en beheren voor meer informatie)


## <a name="http-request"></a>HTTP-aanvraag
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/isolate
```

## <a name="request-headers"></a>Kopteksten aanvragen

Naam | Type | Beschrijving
:---|:---|:---
Autorisatie | Tekenreeks | Bearer {token}. **Vereist**.
Inhoudstype | tekenreeks | toepassing/json. **Vereist**.

## <a name="request-body"></a>Body aanvragen
In de objectaanvraag moet u een JSON-object de volgende parameters geven:

Parameter | Type    | Beschrijving
:---|:---|:---
Opmerking |   Tekenreeks |    Opmerking om te koppelen aan de actie. **Vereist**.
IsolationType   | Tekenreeks |  Type isolatie. Toegestane waarden zijn: 'Volledig' of 'Selectief'.

**IsolationType** bepaalt het type isolatie dat moet worden gebruikt en kan een van de volgende opties zijn:
- Volledig – Volledige isolatie
- Selectief: beperk slechts een beperkt aantal toepassingen om toegang te krijgen tot het netwerk (zie [Apparaten isoleren van](respond-machine-alerts.md#isolate-devices-from-the-network) het netwerk voor meer informatie)


## <a name="response"></a>Antwoord
Als dit is gelukt, retourneert deze methode 201: de reactiecode en [de machineactie](machineaction.md) in de antwoordgroep.


## <a name="example"></a>Voorbeeld

**Aanvraag**

Hier is een voorbeeld van de aanvraag.

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/isolate
```

```json
{
  "Comment": "Isolate machine due to alert 1234",
  "IsolationType": "Full" 
}
```

- Zie Apparaat los van isolatie als u een apparaat wilt los laten van [isolatie.](unisolate-machine.md)
