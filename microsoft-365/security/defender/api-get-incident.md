---
title: Incident-API krijgen
description: Meer informatie over het gebruik van de API Voor incidenten krijgen om één incident in Microsoft 365 Defender.
keywords: api's, graph api, ondersteunde api's, downloaden, bestand, hash
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
ms.openlocfilehash: 2e051803a4cd228e3b455ec08b30e5c2197ca9a3
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289605"
---
# <a name="get-incident-information-api"></a>Api voor incidentgegevens verkrijgen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefversie.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API-beschrijving

Haalt een specifiek incident op met de id

## <a name="limitations"></a>Beperkingen

1. Tariefbeperkingen voor deze API zijn 100 oproepen per minuut en 1500 oproepen per uur.


## <a name="permissions"></a>Machtigingen

Een van de volgende machtigingen is vereist om deze API te bellen. 

Machtigingstype | Machtiging | Weergavenaam machtiging
:---|:---|:---
Toepassing | Incident.Read.All | 'Alle incidenten lezen'
Toepassing | Incident.ReadWrite.All | 'Alle incidenten lezen en schrijven'
Gedelegeerd (werk- of schoolaccount) | Incident.Read | 'Incidenten lezen'
Gedelegeerd (werk- of schoolaccount) | Incident.ReadWrite | 'Incidenten lezen en schrijven'

> [!NOTE]
>
> Bij het verkrijgen van een token met gebruikersreferenties:
>
> - De gebruiker moet ten minste de volgende rolmachtiging hebben: 'Gegevens weergeven'
> - Het antwoord bevat alleen incidenten waar de gebruiker aan wordt blootgesteld

## <a name="http-request"></a>HTTP-aanvraag

```console
GET .../api/incidents/{id} 
```

## <a name="request-headers"></a>Aanvraagheaders

Naam | Type | Omschrijving
:---|:---|:---
Autorisatie | Tekenreeks | Bearer {token}. **Vereist**.

## <a name="request-body"></a>Aanvraagtekst

Leeg

## <a name="response"></a>Antwoord

Als dit is gelukt, retourneert deze methode 200 OK en de incident-entiteit in de antwoordlichaam. Als een incident met de opgegeven id niet is gevonden - 404 Niet gevonden.

## <a name="example"></a>Voorbeeld

**Aanvraag**

Hier is een voorbeeld van de aanvraag.

```http
GET https://api.security.microsoft.com/api/incidents/{id}
```
