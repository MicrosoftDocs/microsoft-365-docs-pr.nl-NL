---
title: Api voor incidenten bijwerken
description: Informatie over het bijwerken van incidenten met Microsoft 365 Defender API
keywords: update, api, incident
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: e3b445b2f9612f0113f353450ca7bf0b8a1a2bb2
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730856"
---
# <a name="update-incidents-api"></a>Api voor incidenten bijwerken

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Van toepassing op:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> Sommige informatie is gerelateerd aan voorlopige productversies die mogelijk aanzienlijk gewijzigd worden voordat ze commercieel gepubliceerd worden. Microsoft geeft geen garantie, uitdrukkelijk of impliciet, met betrekking tot de informatie die hier wordt beschreven.

## <a name="api-description"></a>API-beschrijving

De eigenschappen van bestaande incidenten worden bijgewerkt. Updatable properties are: ```status``` , , , , , , and ```determination``` ```classification``` ```assignedTo``` ```tags``` ```comments``` .

### <a name="quotas-resource-allocation-and-other-constraints"></a>Quota, resourcetoewijzing en andere beperkingen

1. U kunt maximaal 50 oproepen per minuut of 1500 oproepen per uur voeren voordat u de beperkingsdrempel bereikt.
2. U kunt de `determination` eigenschap alleen instellen als deze is ingesteld op `classification` TruePositive.

Als uw aanvraag wordt beperkt, wordt er een `429` antwoordcode retourneerd. De antwoord body geeft het tijdstip aan waarop u kunt beginnen met het starten van nieuwe oproepen.

## <a name="permissions"></a>Machtigingen

Een van de volgende machtigingen is vereist om deze API te bellen. Zie [Access the Microsoft 365 Defender API's (Access the Microsoft 365 Defender API's ) voor meer informatie,](api-access.md)inclusief het kiezen van machtigingen.

Machtigingstype | Machtiging | Weergavenaam machtiging
-|-|-
Toepassing | Incident.ReadWrite.All | Alle incidenten lezen en schrijven
Gedelegeerd (werk- of schoolaccount) | Incident.ReadWrite | Incidenten lezen en schrijven

> [!NOTE]
> Bij het verkrijgen van een token met gebruikersreferenties moet de gebruiker toestemming hebben om het incident in de portal bij te werken.

## <a name="http-request"></a>HTTP-aanvraag

```HTTP
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a>Kopteksten aanvragen

Naam | Type | Beschrijving
-|-|-
Autorisatie | Tekenreeks | Bearer {token}. **Vereist**.
Inhoudstype | Tekenreeks | toepassing/json. **Vereist**.

## <a name="request-body"></a>Body aanvragen

In de aanvraagt u de waarden voor de velden die moeten worden bijgewerkt. Bestaande eigenschappen die niet in de aanvraag worden opgenomen, behouden hun waarden, tenzij ze opnieuw moeten worden berekend vanwege wijzigingen in gerelateerde waarden. Voor de beste prestaties moet u bestaande waarden weglaten die niet zijn gewijzigd.

Eigenschap | Type | Beschrijving
-|-|-
status | Enum | Hiermee geeft u de huidige status van het incident op. Mogelijke waarden zijn: ```Active``` ```Resolved``` , en ```Redirected``` .
toegewezenTo | tekenreeks | Eigenaar van het incident.
classificatie | Enum | Specificatie van het incident. Mogelijke waarden zijn: ```Unknown``` ```FalsePositive``` , , ```TruePositive``` .
bepaling | Enum | Hiermee geeft u de bepaling van het incident op. Mogelijke waarden zijn: ```NotAvailable``` , , , , , , ```Apt``` ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` ```UnwantedSoftware``` . ```Other```
tags | lijst met tekenreeksen | Lijst met incidentlabels.
opmerking | tekenreeks | Opmerking die moet worden toegevoegd aan het incident.

## <a name="response"></a>Antwoord

Als dit is gelukt, retourneert deze methode `200 OK` . De antwoordinstantie bevat de entiteit incident met bijgewerkte eigenschappen. Als er geen incident met de opgegeven id is gevonden, retourneert de methode `404 Not Found` .

## <a name="example"></a>Voorbeeld

**Aanvraag**

Hier is een voorbeeld van de aanvraag.

```HTTP
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

**Antwoord**

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "TruePositive",
    "determination": "Malware",
    "tags": ["Yossi's playground", "Don't mess with the Zohan"],
    "comments": [
          {
              "comment": "pen testing",
              "createdBy": "secop2@contoso.com",
              "createdTime": "2021-05-02T09:34:21.5519738Z"
          },
          {
              "comment": "valid incident",
              "createdBy": "secop2@contoso.comt",
              "createdTime": "2021-05-02T09:36:27.6652581Z"
          }
      ]
}
```

## <a name="related-articles"></a>Aanverwante artikelen

- [Toegang tot Microsoft 365 Defender-API's](api-access.md)
- [Meer informatie over API-limieten en -licenties](api-terms.md)
- [Foutcodes begrijpen](api-error-codes.md)
- [API's voor incidenten](api-incident.md)
- [Lijst met incidenten](api-list-incidents.md)
- [Overzicht van incidenten](incidents-overview.md)
