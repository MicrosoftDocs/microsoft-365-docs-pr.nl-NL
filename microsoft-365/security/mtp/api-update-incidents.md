---
title: Update-incidenten API
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 18be4565c2611457d0f5fdc135f99a301bb39e2a
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929068"
---
# <a name="update-incidents-api"></a>Update-incidenten API

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Van toepassing op:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Sommige informatie heeft betrekking op vooraf uitgebracht product dat aanzienlijk kan worden gewijzigd voordat het in de handel wordt gebracht. Microsoft biedt geen garanties, uitdrukkelijk of impliciet, met betrekking tot de informatie die hier wordt be gegeven.

## <a name="api-description"></a>API-beschrijving

De eigenschappen van een bestaand incident worden bijgewerkt. De eigenschappen die kunnen worden updatable zijn: ```status``` ```determination``` , , en ```classification``` ```assignedTo``` ```tags``` .

### <a name="quotas-resource-allocation-and-other-constraints"></a>Quota's, toewijzing van resources en andere beperkingen

1. U kunt maximaal 50 oproepen per minuut of 1500 oproepen per uur doen voordat u de beperkingsdrempel overschrijdt.
2. U kunt de eigenschap `determination` alleen instellen als dit is ingesteld op `classification` TruePositive.

Als uw aanvraag wordt beperkt, wordt een `429` antwoordcode als retourneerd. In de antwoord body wordt het tijdstip aangegeven waarop u nieuwe gesprekken kunt starten.

## <a name="permissions"></a>Machtigingen

Een van de volgende machtigingen is vereist om deze API aan te roepen. Zie Access de [Microsoft 365 Defender-API's](api-access.md)voor meer informatie, waaronder het kiezen van machtigingen.

Machtigingstype | Machtiging | Weergavenaam van machtiging
-|-|-
Toepassing | Incident.ReadWrite.All | Alle incidenten lezen en schrijven
Gedelegeerd (werk- of schoolaccount) | Incident.ReadWrite | Incidenten lezen en schrijven

> [!NOTE]
> Wanneer u een token verkrijgt met behulp van gebruikersreferenties, moet de gebruiker zijn toestemming hebben om het incident bij te werken in de portal.

## <a name="http-request"></a>HTTP-aanvraag

```HTTP
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a>Berichtkoppen aanvragen

Naam | Type | Beschrijving
-|-|-
Autorisatie | Tekenreeks | Beller {token}. **Vereist.**
Inhoudstype | Tekenreeks | toepassing/json. **Vereist.**

## <a name="request-body"></a>Aanvraag in de eerste instantie

In de aanvraag zelf de waarden voor de velden die moeten worden bijgewerkt. Bestaande eigenschappen die niet in de aanvraag zelf zijn opgenomen, behouden de waarden, tenzij deze moeten worden herberekend vanwege wijzigingen in gerelateerde waarden. Voor de beste prestaties moet u bestaande waarden weglaten die niet zijn gewijzigd.

Eigenschap | Type | Beschrijving
-|-|-
status | Enum | Hiermee geeft u de huidige status van de waarschuwing op. Mogelijke waarden zijn: ```Active``` ```Resolved``` en ```Redirected``` .
toegewezen Aan | tekenreeks | De eigenaar van het incident.
classificatie | Enum | Specificatie van de waarschuwing. Mogelijke waarden zijn: ```Unknown``` ```FalsePositive``` , ```TruePositive``` .
besluit | Enum | Bepaalt de bepalingen van de waarschuwing. Mogelijke waarden zijn: ```NotAvailable``` ```Apt``` , , , ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` ```UnwantedSoftware``` . ```Other```
tags | lijst met tekenreeksen | Lijst met incidentlabels.

## <a name="response"></a>Antwoord

Als dit lukt, retourneert deze `200 OK` methode. De antwoordinstantie bevat de incidententiteit met bijgewerkte eigenschappen. Als een incident met de opgegeven id niet is gevonden, wordt het retourneert de `404 Not Found` methode.

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

- [Toegang tot de Microsoft 365 Defender-API's](api-access.md)
- [Meer informatie over API-limieten en licenties](api-terms.md)
- [Meer te weten komen over foutcodes](api-error-codes.md)
- [API's voor incidenten](api-incident.md)
- [Lijst met incidenten](api-list-incidents.md)
- [Overzicht van incidenten](incidents-overview.md)
