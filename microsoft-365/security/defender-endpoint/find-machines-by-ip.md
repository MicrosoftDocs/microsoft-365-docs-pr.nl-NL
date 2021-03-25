---
title: Apparaten zoeken via interne IP-API
description: Apparaten zoeken die worden gezien met het aangevraagde interne IP-adres in het tijdbereik van 15 minuten vóór en na een bepaalde tijdstempel
keywords: api's, graph api, ondersteunde api's, get, device, IP, find, find device, by ip, ip
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
ms.openlocfilehash: fa523a7f9b997f3a8d36dff42d10c1229e7a467f
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200435"
---
# <a name="find-devices-by-internal-ip-api"></a>Apparaten zoeken via interne IP-API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API-beschrijving
Zoek [machines](machine.md) die worden gezien met het aangevraagde interne IP-adres in het tijdbereik van 15 minuten vóór en na een bepaalde tijdstempel.


## <a name="limitations"></a>Beperkingen
1. De opgegeven tijdstempel moet de afgelopen 30 dagen zijn.
2. Tariefbeperkingen voor deze API zijn 100 oproepen per minuut en 1500 oproepen per uur.


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
GET /api/machines/findbyip(ip='{IP}',timestamp={TimeStamp})
```

## <a name="request-headers"></a>Kopteksten aanvragen

Naam | Type | Beschrijving
:---|:---|:---
Autorisatie | Tekenreeks | Bearer {token}. **Vereist**.

## <a name="request-body"></a>Body aanvragen
Leeg

## <a name="response"></a>Antwoord
Als dit is gelukt- 200 OK met de lijst met de machines in de antwoord body.
Als de tijdstempel niet in de afgelopen 30 dagen - 400 Bad Request is.

## <a name="example"></a>Voorbeeld

**Aanvraag**

Hier is een voorbeeld van de aanvraag.

```http
GET https://api.securitycenter.microsoft.com/api/machines/findbyip(ip='10.248.240.38',timestamp=2019-09-22T08:44:05Z)
```
