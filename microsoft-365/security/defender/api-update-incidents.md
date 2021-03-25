---
title: Api voor incidenten bijwerken
description: Informatie over het bijwerken van incidenten met de Microsoft 365 Defender API
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
ms.openlocfilehash: 549f9bf2b9dc2ea5d1c734a809ad10a168c8123e
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056663"
---
# <a name="update-incidents-api"></a>Api voor incidenten bijwerken

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Van toepassing op:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Sommige informatie is gerelateerd aan voorlopige productversies die mogelijk aanzienlijk gewijzigd worden voordat ze commercieel gepubliceerd worden. Microsoft geeft geen garantie, uitdrukkelijk of impliciet, met betrekking tot de informatie die hier wordt beschreven.

## <a name="api-description"></a>API-beschrijving

De eigenschappen van bestaande incidenten worden bijgewerkt. Updatable properties are: ```status``` , , , , , and ```determination``` ```classification``` ```assignedTo``` ```tags``` .

### <a name="quotas-resource-allocation-and-other-constraints"></a>Quota, resourcetoewijzing en andere beperkingen

1. U kunt maximaal 50 oproepen per minuut of 1500 oproepen per uur voeren voordat u de beperkingsdrempel bereikt.
2. U kunt de `determination` eigenschap alleen instellen als deze is ingesteld op `classification` TruePositive.

Als uw aanvraag wordt beperkt, wordt er een `429` antwoordcode retourneerd. De antwoord body geeft het tijdstip aan waarop u kunt beginnen met het starten van nieuwe oproepen.

## <a name="permissions"></a>Machtigingen

Een van de volgende machtigingen is vereist om deze API te bellen. Zie Access the Microsoft 365 Defender APIs (Toegang tot de [Microsoft 365 Defender-API's)](api-access.md)voor meer informatie, inclusief het kiezen van machtigingen.

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
status | Enum | Hiermee geeft u de huidige status van de waarschuwing op. Mogelijke waarden zijn: ```Active``` ```Resolved``` , en ```Redirected``` .
toegewezenTo | tekenreeks | Eigenaar van het incident.
classificatie | Enum | Specificatie van de waarschuwing. Mogelijke waarden zijn: ```Unknown``` ```FalsePositive``` , , ```TruePositive``` .
bepaling | Enum | Hiermee geeft u de bepaling van de waarschuwing op. Mogelijke waarden zijn: ```NotAvailable``` , , , , , , ```Apt``` ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` ```UnwantedSoftware``` . ```Other```
tags | lijst met tekenreeksen | Lijst met incidentlabels.

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
    "tags": ["Yossi's playground", "Don't mess with the Zohan"]
}
```

## <a name="related-articles"></a>Verwante artikelen

- [De Microsoft 365 Defender-API's openen](api-access.md)
- [Meer informatie over API-limieten en -licenties](api-terms.md)
- [Foutcodes begrijpen](api-error-codes.md)
- [API's voor incidenten](api-incident.md)
- [Lijst met incidenten](api-list-incidents.md)
- [Overzicht van incidenten](incidents-overview.md)