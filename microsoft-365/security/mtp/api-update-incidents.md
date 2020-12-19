---
title: API voor update van incidenten
description: Meer informatie over het bijwerken van incidenten met de Microsoft 365 Defender API
keywords: Update, API, incident
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 6fc1ff730994f03aa500ad9a4559b66970e32d87
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719402"
---
# <a name="update-incidents-api"></a>API voor update van incidenten

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Van toepassing op:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Sommige informatie verhoudt zich tot een voorvrijgegeven product dat bij de commerciële versie van de commerciële versie mogelijk ingrijpend werd gewijzigd. Microsoft biedt geen garanties, expliciete of impliciete informatie met betrekking tot de informatie die u hier opgeeft.

## <a name="api-description"></a>API-beschrijving

Hiermee worden de eigenschappen van een bestaand incident bijgewerkt. Bijwerkbare eigenschappen zijn: ```status``` , ```determination``` , ```classification``` , ```assignedTo``` en ```tags``` .

### <a name="quotas-resource-allocation-and-other-constraints"></a>Quota's, resourcetoewijzing en andere beperkingen

1. U kunt maximaal 50 oproepen per minuut of 1500 bellen per uur maken voordat u op de drempelwaarde klikt.
2. U kunt de `determination` eigenschap alleen instellen als dit `classification` is ingesteld op TruePositive.

Als uw aanvraag wordt vertraagd, wordt een `429` antwoordcode geretourneerd. De antwoordtekst geeft de tijd aan waarop u kunt beginnen met het maken van nieuwe oproepen.

## <a name="permissions"></a>Machtigingen

U moet een van de volgende machtigingen hebben om deze API te kunnen bellen. Voor meer informatie, waaronder de manier waarop u machtigingen kiest, raadpleegt u [de Microsoft 365-api's voor Access](api-access.md).

Type machtiging | Machtigingsset | Weergavenaam van de machtiging
-|-|-
Toepassing | Incident. ReadWrite. all | Alle incidenten lezen en schrijven
Gedelegeerd (werk-of schoolaccount) | Incident. ReadWrite | Lees-en schrijf incidenten

> [!NOTE]
> Bij het verkrijgen van een token met behulp van gebruikersreferenties moet de gebruiker zijn gemachtigd om het incident bij te werken in de portal.

## <a name="http-request"></a>HTTP-aanvraag

```HTTP
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a>Kopteksten aanvragen

Naam | Type | Beschrijving
-|-|-
Bevoegdheid | Tekenreeks | Bearer {token}. **Vereist**.
Inhouds type | Tekenreeks | Application/JSON. **Vereist**.

## <a name="request-body"></a>Aanvraagtekst

Geef in de hoofdtekst van de aanvraag de waarden op voor de velden die moeten worden bijgewerkt. Bestaande eigenschappen die niet zijn opgenomen in de hoofdtekst van de aanvraag, behouden hun waarden, tenzij ze moeten worden herberekend als gevolg van wijzigingen in gerelateerde waarden. Voor de beste prestaties moet u bestaande waarden weglaten die niet zijn gewijzigd.

Eigenschap | Type | Beschrijving
-|-|-
status | Opsommings | Geeft de huidige status van de waarschuwing op. Mogelijke waarden zijn: ```Active``` , ```Resolved``` , en ```Redirected``` .
ToegewezenAan | tekenreeks | Eigenaar van het incident.
Contactpersoonclassificatie | Opsommings | Specificatie van de waarschuwing. Mogelijke waarden zijn: ```Unknown``` , ```FalsePositive``` , ```TruePositive``` .
relevant | Opsommings | Hiermee geeft u het bepalen van de waarschuwing op. Mogelijke waarden zijn: ```NotAvailable``` , ```Apt``` ,,, ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` , ```UnwantedSoftware``` , ```Other``` .
Tags | Lijst met tekenreeksen | Lijst met incident Tags.

## <a name="response"></a>Na

Als dit slaagt, retourneert deze methode `200 OK` . De antwoordtekst bevat de entiteit van de schade met bijgewerkte eigenschappen. Als een incident met de opgegeven ID niet kan worden gevonden, wordt de methode geretourneerd `404 Not Found` .

## <a name="example"></a>Voorbeeld

**Webonderdeelverzoek**

Hier ziet u een voorbeeld van de aanvraag.

```HTTP
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

**Na**

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

- [Toegang tot de Microsoft 365 Defender-Api's](api-access.md)
- [Meer informatie over API-limieten en licenties](api-terms.md)
- [Meer informatie over foutcodes](api-error-codes.md)
- [API's voor incidenten](api-incident.md)
- [Lijst met incidenten](api-list-incidents.md)
- [Overzicht van incidenten](incidents-overview.md)
