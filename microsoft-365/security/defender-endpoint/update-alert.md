---
title: Api voor waarschuwingsentiteit bijwerken
description: Meer informatie over het bijwerken van een Waarschuwing van Microsoft Defender voor eindpunten met behulp van deze API. U kunt de eigenschappen status, bepaling, classificatie en toegewezen Aan bijwerken.
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
ms.openlocfilehash: 043d423e1016d77cad4a175aa41718329f464252
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52768921"
---
# <a name="update-alert"></a>Waarschuwing bijwerken

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API-beschrijving
Updates van de eigenschappen van bestaande [waarschuwing](alerts.md).
<br>Het indienen **van opmerkingen** is beschikbaar met of zonder bij te werken eigenschappen.
<br>Datumbare eigenschappen zijn: ```status``` ```determination``` , en ```classification``` ```assignedTo``` .


## <a name="limitations"></a>Beperkingen
1. U kunt waarschuwingen bijwerken die beschikbaar zijn in de API. Zie [Lijstwaarschuwingen](get-alerts.md) voor meer informatie.
2. Tariefbeperkingen voor deze API zijn 100 oproepen per minuut en 1500 oproepen per uur.


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
```
PATCH /api/alerts/{id}
```

## <a name="request-headers"></a>Kopteksten aanvragen

Naam | Type | Beschrijving
:---|:---|:---
Autorisatie | Tekenreeks | Bearer {token}. **Vereist**.
Inhoudstype | Tekenreeks | toepassing/json. **Vereist**.


## <a name="request-body"></a>Body aanvragen
In de aanvraagt u de waarden voor de relevante velden die moeten worden bijgewerkt.
<br>Bestaande eigenschappen die niet in de aanvraag worden opgenomen, behouden hun vorige waarden of worden herberekend op basis van wijzigingen in andere eigenschapswaarden. 
<br>Voor de beste prestaties moet u geen bestaande waarden opnemen die niet zijn gewijzigd.

Eigenschap | Type | Beschrijving
:---|:---|:---
status | Tekenreeks | Hiermee geeft u de huidige status van de waarschuwing op. De eigenschapswaarden zijn: 'Nieuw', 'InProgress' en 'Opgelost'.
toegewezenTo | Tekenreeks | Eigenaar van de waarschuwing
classificatie | Tekenreeks | Hiermee geeft u de specificatie van de waarschuwing op. De eigenschapswaarden zijn: 'Onbekend', 'FalsePositive', 'TruePositive'. 
bepaling | Tekenreeks | Hiermee geeft u de bepaling van de waarschuwing op. De eigenschapswaarden zijn: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'
opmerking | Tekenreeks | Opmerking die moet worden toegevoegd aan de waarschuwing.

## <a name="response"></a>Antwoord
Als dit is gelukt, retourneert deze [](alerts.md) methode 200 OK en de waarschuwingsentiteit in de antwoordinstelling met de bijgewerkte eigenschappen. Als een waarschuwing met de opgegeven id niet is gevonden- 404 Niet gevonden.


## <a name="example"></a>Voorbeeld

**Aanvraag**

Hier is een voorbeeld van de aanvraag.

```http
PATCH https://api.securitycenter.microsoft.com/api/alerts/121688558380765161_2136280442
```

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "FalsePositive",
    "determination": "Malware",
    "comment": "Resolve my alert and assign to secop2"
}
```
