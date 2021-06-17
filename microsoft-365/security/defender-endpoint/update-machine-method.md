---
title: Api voor machine-entiteit bijwerken
description: Meer informatie over het bijwerken van machinetags met behulp van deze API. U kunt de tags en apparaatwaardeeigenschappen bijwerken.
keywords: api's, graph api, ondersteunde api's, get, alert, information, id
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
ms.openlocfilehash: 8f08b1fdafd653561ac2aae10a73f37b21874b59
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985630"
---
# <a name="update-machine"></a>Computer bijwerken 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API-beschrijving
De eigenschappen van bestaande [machine worden bijgewerkt.](machine.md)
<br>Updatable properties are: ```machineTags``` and ```deviceValue``` .


## <a name="limitations"></a>Beperkingen
1. U kunt machines bijwerken die beschikbaar zijn in de API. 
2. Update machine voegt alleen tags toe aan de tagverzameling. Als er tags bestaan, moeten ze worden opgenomen in de tagsverzameling in de body.
3. Tariefbeperkingen voor deze API zijn 100 oproepen per minuut en 1500 oproepen per uur.


## <a name="permissions"></a>Machtigingen
Een van de volgende machtigingen is vereist om deze API te bellen. Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.

Machtigingstype |   Machtiging  |   Weergavenaam machtiging
:---|:---|:---
Toepassing |   Machine.ReadWrite.All | 'Machinegegevens lezen en schrijven voor alle machines'
Gedelegeerd (werk- of schoolaccount) | Machine.ReadWrite | 'Machinegegevens lezen en schrijven'

>[!Note]
> Bij het verkrijgen van een token met gebruikersreferenties:
>- De gebruiker moet ten minste de volgende rolmachtiging hebben: 'Alerts investigation'. Zie Rollen maken [en beheren voor meer informatie.](user-roles.md)
>- De gebruiker moet toegang hebben tot het apparaat dat aan de waarschuwing is gekoppeld, op basis van de instellingen van de apparaatgroep. Zie Apparaatgroepen maken en beheren voor meer [informatie.](machine-groups.md)

## <a name="http-request"></a>HTTP-aanvraag
```
PATCH /api/machines/{machineId}
```

## <a name="request-headers"></a>Aanvraagheaders

Naam | Type | Beschrijving
:---|:---|:---
Autorisatie | Tekenreeks | Bearer {token}. **Vereist**.
Content-Type | Tekenreeks | toepassing/json. **Vereist**.


## <a name="request-body"></a>Aanvraagtekst
In de aanvraagt u de waarden voor de relevante velden die moeten worden bijgewerkt.
<br>Bestaande eigenschappen die niet in de aanvraag worden opgenomen, behouden hun vorige waarden of worden herberekend op basis van wijzigingen in andere eigenschapswaarden. 
<br>Voor de beste prestaties moet u geen bestaande waarden opnemen die niet zijn gewijzigd.

Eigenschap | Type | Beschrijving
:---|:---|:---
machineTags | Tekenreeksverzameling | Set [met machinelabels.](machine.md)
deviceValue | Nullable Enum | De [waarde van het apparaat](tvm-assign-device-value.md). Mogelijke waarden zijn: 'Normaal', 'Laag' en 'Hoog'.

## <a name="response"></a>Antwoord
Als dit is gelukt, retourneert deze methode 200 OK en de [machine-entiteit](machine.md) in de antwoordinstelling met de bijgewerkte eigenschappen. Als de verzameling van machinelabels in de body geen bestaande machinelabels bevat: 400 ongeldige invoer en een bericht met informatie over de ontbrekende tag/s.
Als de computer met de opgegeven id niet is gevonden- 404 Niet gevonden.


## <a name="example"></a>Voorbeeld

**Aanvraag**

Hier is een voorbeeld van de aanvraag.

```http
PATCH https://api.securitycenter.microsoft.com/api/machines/{machineId}
```

```json
{
    "deviceValue": "Normal",
    "machineTags": [
                     "Demo Device",
                     "Generic User Machine - Attack Source",
                     "Windows 10",
                     "Windows Insider - Fast"
    ]
}
```
