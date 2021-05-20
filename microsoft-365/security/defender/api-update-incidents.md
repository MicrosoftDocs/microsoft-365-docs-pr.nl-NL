---
title: Api voor incident bijwerken
description: Meer informatie over het bijwerken van incidenten met Microsoft 365 Defender API
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
ms.openlocfilehash: e3f3919d067078ef1fd1e116dc52e8a73c0726d9
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571779"
---
# <a name="update-incident-api"></a>Api voor incident bijwerken

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Van toepassing op:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Sommige informatie is gerelateerd aan voorlopige productversies die mogelijk aanzienlijk gewijzigd worden voordat ze commercieel gepubliceerd worden. Microsoft geeft geen garantie, uitdrukkelijk of impliciet, met betrekking tot de informatie die hier wordt beschreven.

## <a name="api-description"></a>API-beschrijving

Hiermee worden de eigenschappen van het bestaande incident bijgewerkt. Updatable eigenschappen zijn: ```status``` , , , , , en ```determination``` ```classification``` ```assignedTo``` ```tags``` ```comments``` .

### <a name="quotas-resource-allocation-and-other-constraints"></a>Quota, toewijzing van middelen en andere beperkingen

1. U kunt maximaal 50 gesprekken per minuut of 1500 gesprekken per uur voeren voordat u de beperkingsdrempel bereikt.
2. U kunt de eigenschap alleen instellen `determination` als deze is ingesteld op `classification` TruePositive.

Als uw aanvraag wordt beperkt, wordt er een `429` antwoordcode geretourneerd. De instantie van de reactie geeft het tijdstip aan waarop u kunt beginnen met het voeren van nieuwe oproepen.

## <a name="permissions"></a>Machtigingen

Een van de volgende machtigingen is vereist om deze API aan te roepen. Zie Toegang tot [de API's van Microsoft 365 Defender](api-access.md)voor meer informatie, waaronder het kiezen van machtigingen.

Machtigingstype | Machtiging | Naam van machtigingsweergave
-|-|-
Toepassing | Incident.ReadWrite.All | Lees en schrijf alle incidenten
Gedelegeerd (werk- of schoolaccount) | Incident.ReadWrite | Lees en schrijf incidenten

> [!NOTE]
> Wanneer u een token verkrijgt met behulp van gebruikers referenties, moet de gebruiker toestemming hebben om het incident in de portal bij te werken.

## <a name="http-request"></a>HTTP-aanvraag

```HTTP
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a>Headers aanvragen

Naam | Type | Omschrijving
-|-|-
machtiging | Tekenreeks | Aan toonder {token}. **Vereist**.
Inhoudstype | Tekenreeks | toepassing/json. **Vereist**.

## <a name="request-body"></a>Instantie aanvragen

Geef in de hoofdtekst van de aanvraag de waarden op voor de velden die moeten worden bijgewerkt. Bestaande eigenschappen die niet zijn opgenomen in de hoofdtekst van de aanvraag, behouden hun waarden, tenzij ze opnieuw moeten worden berekend vanwege wijzigingen in gerelateerde waarden. Voor de beste prestaties moet u bestaande waarden weglaten die niet zijn gewijzigd.

Eigenschap | Type | Omschrijving
-|-|-
status | Enum | Hiermee geeft u de huidige status van het incident op. Mogelijke waarden zijn: ```Active``` ```Resolved``` , , en ```Redirected``` .
toegewezenTo | snaar | Eigenaar van het incident.
classificatie | Enum | Specificatie van het incident. Mogelijke waarden zijn: ```Unknown``` ```FalsePositive``` , , ```TruePositive``` .
vastberadenheid | Enum | Hiermee geeft u de bepaling van het incident op. Mogelijke waarden zijn: ```NotAvailable``` , , , , , ```Apt``` ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` ```UnwantedSoftware``` ```Other``` .
Tags | tekenreekslijst | Lijst met incidenttags.
commentaar | snaar | Commentaar dat aan het incident moet worden toegevoegd.

## <a name="response"></a>antwoord

Als dit is gelukt, retourneert deze methode `200 OK` . De antwoordtekst bevat de incidententiteit met bijgewerkte eigenschappen. Als er geen incident met de opgegeven ID is gevonden, retourneert de methode `404 Not Found` .

## <a name="example"></a>Voorbeeld

**verzoek**

Hier is een voorbeeld van het verzoek.

```HTTP
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

**antwoord**

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

## <a name="related-articles"></a>Verwante artikelen

- [Toegang tot de API's van Microsoft 365 Defender](api-access.md)
- [Meer informatie over API-limieten en licenties](api-terms.md)
- [Foutcodes begrijpen](api-error-codes.md)
- [API's voor incidenten](api-incident.md)
- [Lijst met incidenten](api-list-incidents.md)
- [Overzicht incidenten](incidents-overview.md)
