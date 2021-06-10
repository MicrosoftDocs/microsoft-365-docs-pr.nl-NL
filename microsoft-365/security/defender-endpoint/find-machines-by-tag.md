---
title: Apparaten zoeken op tag-API
description: Alle apparaten zoeken die specifc-tag bevatten
keywords: api's, ondersteunde api's, get, device, find, find device, by tag, tag
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
ms.openlocfilehash: 88ad63d8b7cc71f7d3f809c7cb0371fc41bb9f5d
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771163"
---
# <a name="find-devices-by-tag-api"></a>Apparaten zoeken op tag-API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)

- Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API-beschrijving
Machines [zoeken](machine.md) op [tag](machine-tags.md).
<br>```startswith``` query wordt ondersteund. 

## <a name="limitations"></a>Beperkingen
1. Tariefbeperkingen voor deze API zijn 100 oproepen per minuut en 1500 oproepen per uur.


## <a name="permissions"></a>Machtigingen
Een van de volgende machtigingen is vereist om deze API te bellen. Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.

Machtigingstype |   Machtiging  |   Weergavenaam machtiging
:---|:---|:---
Toepassing |   Machine.Read.All |  'Alle machineprofielen lezen'
Toepassing |   Machine.ReadWrite.All | 'Alle computergegevens lezen en schrijven'
Gedelegeerd (werk- of schoolaccount) | Machine.Lezen | 'Machinegegevens lezen'
Gedelegeerd (werk- of schoolaccount) | Machine.ReadWrite | 'Machinegegevens lezen en schrijven'

>[!Note]
> Bij het verkrijgen van een token met gebruikersreferenties:
> - Antwoord bevat alleen apparaten tot wie de gebruiker toegang heeft op basis van instellingen voor apparaatgroepen (Zie [Apparaatgroepen](machine-groups.md) maken en beheren voor meer informatie)
> - De gebruiker moet ten minste de volgende rolmachtiging hebben: 'Gegevens weergeven' [(Zie](user-roles.md) Rollen maken en beheren voor meer informatie)
> - Antwoord bevat alleen apparaten tot wie de gebruiker toegang heeft op basis van instellingen voor apparaatgroepen (Zie [Apparaatgroepen](machine-groups.md) maken en beheren voor meer informatie)

## <a name="http-request"></a>HTTP-aanvraag
```
GET /api/machines/findbytag?tag={tag}&useStartsWithFilter={true/false}
```

## <a name="request-headers"></a>Kopteksten aanvragen

Naam | Type | Beschrijving
:---|:---|:---
Autorisatie | Tekenreeks | Bearer {token}. **Vereist**.

## <a name="request-uri-parameters"></a>URI-parameters aanvragen

Naam | Type | Beschrijving
:---|:---|:---
tag | Tekenreeks | De naam van de tag. **Vereist**.
useStartsWithFilter | Booleaanse waarde | Wanneer de zoekopdracht is ingesteld op waar, worden alle apparaten met de naam van de tag gevonden die beginnen met de opgegeven tag in de query. Standaardwaarden voor onwaar. **Optioneel**.

## <a name="request-body"></a>Body aanvragen
Leeg

## <a name="response"></a>Antwoord
Als dit is gelukt- 200 OK met de lijst met de machines in de antwoord body.

## <a name="example"></a>Voorbeeld

**Aanvraag**

Hier is een voorbeeld van de aanvraag.

```http
GET https://api.securitycenter.microsoft.com/api/machines/findbytag?tag=testTag&useStartsWithFilter=true
```