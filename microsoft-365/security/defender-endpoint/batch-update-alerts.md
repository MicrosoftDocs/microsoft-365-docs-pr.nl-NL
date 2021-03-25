---
title: Batch Update alert entities API
description: Meer informatie over het bijwerken van waarschuwingen van Microsoft Defender voor eindpunten in een batch met deze API. U kunt de eigenschappen status, bepaling, classificatie en toegewezen Aan bijwerken.
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
ms.technology: mde
ms.openlocfilehash: db745c1b12c64baff5bf2c0a212446ce0f773709
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166682"
---
# <a name="batch-update-alerts"></a>Batchupdatewaarschuwingen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)

- Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API-beschrijving
De eigenschappen van een batch bestaande waarschuwingen [worden bijgewerkt.](alerts.md)
<br>Het indienen **van opmerkingen** is beschikbaar met of zonder bij te werken eigenschappen.
<br>Datumbare eigenschappen zijn: `status` `determination` , en `classification` `assignedTo` .


## <a name="limitations"></a>Beperkingen
1. U kunt waarschuwingen bijwerken die beschikbaar zijn in de API. Zie [Lijstwaarschuwingen](get-alerts.md) voor meer informatie.
2. Tariefbeperkingen voor deze API zijn 10 oproepen per minuut en 500 oproepen per uur.


## <a name="permissions"></a>Machtigingen
Een van de volgende machtigingen is vereist om deze API te bellen. Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.

Machtigingstype |   Machtiging  |   Weergavenaam machtiging
:---|:---|:---
Toepassing |   Alerts.ReadWrite.All |  'Alle waarschuwingen lezen en schrijven'
Gedelegeerd (werk- of schoolaccount) | Alert.ReadWrite | 'Waarschuwingen lezen en schrijven'

>[!Note]
> Bij het verkrijgen van een token met gebruikersreferenties:
>- De gebruiker moet ten minste de volgende rolmachtiging hebben: 'Alerts investigation' (Zie Rollen maken [en](user-roles.md) beheren voor meer informatie)
>- De gebruiker moet toegang hebben tot het apparaat dat aan de waarschuwing is gekoppeld, op basis van apparaatgroepinstellingen (Zie [Apparaatgroepen](machine-groups.md) maken en beheren voor meer informatie)

## <a name="http-request"></a>HTTP-aanvraag
```http
POST /api/alerts/batchUpdate
```

## <a name="request-headers"></a>Kopteksten aanvragen

Naam | Type | Beschrijving
:---|:---|:---
Autorisatie | Tekenreeks | Bearer {token}. **Vereist**.
Inhoudstype | Tekenreeks | toepassing/json. **Vereist**.


## <a name="request-body"></a>Body aanvragen
In de aanvraag-body geeft u de 1D's op van de waarschuwingen die moeten worden bijgewerkt en de waarden van de relevante velden die u wilt bijwerken voor deze waarschuwingen.
<br>Bestaande eigenschappen die niet in de aanvraag worden opgenomen, behouden hun vorige waarden of worden herberekend op basis van wijzigingen in andere eigenschapswaarden. 
<br>Voor de beste prestaties moet u geen bestaande waarden opnemen die niet zijn gewijzigd.

Eigenschap | Type | Beschrijving
:---|:---|:---
alertIds | &lt;Lijstreeks&gt;| Een lijst met de ID's van de waarschuwingen die moeten worden bijgewerkt. **Vereist**
status | Tekenreeks | Hiermee geeft u de bijgewerkte status van de opgegeven waarschuwingen op. De eigenschapswaarden zijn: 'Nieuw', 'InProgress' en 'Opgelost'.
toegewezenTo | Tekenreeks | Eigenaar van de opgegeven waarschuwingen
classificatie | Tekenreeks | Hiermee geeft u de specificatie van de opgegeven waarschuwingen op. De eigenschapswaarden zijn: 'Onbekend', 'FalsePositive', 'TruePositive'. 
bepaling | Tekenreeks | Hiermee geeft u de bepaling van de opgegeven waarschuwingen op. De eigenschapswaarden zijn: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'
opmerking | Tekenreeks | Opmerking die moet worden toegevoegd aan de opgegeven waarschuwingen.

## <a name="response"></a>Antwoord
Als dit is gelukt, retourneert deze methode 200 OK, met een lege antwoord body.


## <a name="example"></a>Voorbeeld

**Aanvraag**

Hier is een voorbeeld van de aanvraag.

```http
POST https://api.securitycenter.microsoft.com/api/alerts/batchUpdate
```

```json
{
    "alertIds": ["da637399794050273582_760707377", "da637399989469816469_51697947354"],
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "FalsePositive",
    "determination": "Malware",
    "comment": "Resolve my alert and assign to secop2"
}
```
