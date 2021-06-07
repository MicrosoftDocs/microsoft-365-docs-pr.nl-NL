---
title: Indicator-API verwijderen.
description: Meer informatie over het gebruik van de INDICATOR-API verwijderen om een indicatorentiteit te verwijderen op id in Microsoft Defender voor Eindpunt.
keywords: api's, openbare api, ondersteunde api's, delete, ti indicator, entiteit, id
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
ms.openlocfilehash: eaef6b25e2db72149a1a1128899d8a79a38a4c60
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771019"
---
# <a name="delete-indicator-api"></a>Indicator-API verwijderen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)  

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API-beschrijving
Hiermee verwijdert [](ti-indicator.md) u een indicatorentiteit op id.


## <a name="limitations"></a>Beperkingen
1. Tariefbeperkingen voor deze API zijn 100 oproepen per minuut en 1500 oproepen per uur.


## <a name="permissions"></a>Machtigingen
Een van de volgende machtigingen is vereist om deze API te bellen. Zie Aan de slag voor meer informatie, inclusief het kiezen van [machtigingen.](apis-intro.md)

Machtigingstype |   Machtiging  |   Weergavenaam machtiging
:---|:---|:---
Toepassing |   Ti.ReadWrite |  'Ti-indicatoren lezen en schrijven'
Toepassing |   Ti.ReadWrite.All |  'Indicatoren lezen en schrijven'


## <a name="http-request"></a>HTTP-aanvraag
```
Delete https://api.securitycenter.microsoft.com/api/indicators/{id}
```

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="request-headers"></a>Kopteksten aanvragen

Naam | Type | Omschrijving
:---|:---|:---
Autorisatie | Tekenreeks | Bearer {token}. **Vereist**.


## <a name="request-body"></a>Body aanvragen
Leeg

## <a name="response"></a>Antwoord
Als indicator bestaat en is verwijderd- 204 OK zonder inhoud.
Als Indicator met de opgegeven id niet is gevonden- 404 Niet gevonden.

## <a name="example"></a>Voorbeeld

**Aanvraag**

Hier is een voorbeeld van de aanvraag.

```http
DELETE https://api.securitycenter.microsoft.com/api/indicators/995
```
