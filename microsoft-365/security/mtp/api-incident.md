---
title: De Api's van Microsoft 365 Defender en het brontype incident
description: Meer informatie over de methoden en eigenschappen van het type incident bron in Microsoft 365 Defender
keywords: incident, incidenten, API
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
ms.openlocfilehash: 372c939f5eed29832725e6b048735040ca7391d6
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719332"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incident-resource-type"></a>De API van Microsoft 365 Defender-incidenten en het brontype incident

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Van toepassing op:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Sommige informatie verhoudt zich tot een voorvrijgegeven product dat bij de commerciële versie van de commerciële versie mogelijk ingrijpend werd gewijzigd. Microsoft biedt geen garanties, expliciete of impliciete informatie met betrekking tot de informatie die u hier opgeeft.

Een [incident](incidents-overview.md) is een verzameling verwante waarschuwingen die een aanval kunnen beschrijven. Gebeurtenissen van verschillende entiteiten in uw organisatie worden automatisch samengevoegd met Microsoft 365 Defender. U kunt de API incidenties gebruiken voor de programmatische toegang tot incidenten en verwante meldingen van uw organisatie.

## <a name="quotas-and-resource-allocation"></a>Quota's en resources toewijzen

U kunt maximaal 50 oproepen per minuut en 1500 bellen per uur aanvragen. Elke methode heeft ook eigen quota's. Zie voor meer informatie over bepaalde quota's de artikelen voor de methode die u wilt gebruiken.

Met een `429` HTTP-antwoordcode wordt aangegeven dat u een quotum hebt bereikt, hetzij op basis van het aantal ingediende aanvragen of over de beschikde periode. De antwoordtekst omvat de tijd totdat het door u bereikte quotum opnieuw wordt ingesteld.

## <a name="permissions"></a>Machtigingen

Voor de incidenten-API is verschillende soorten machtigingen vereist voor de verschillende methoden. Zie het artikel van de desbetreffende methode voor meer informatie over de vereiste machtigingen.

## <a name="methods"></a>Methode

Methode | Type resultaat | Beschrijving
-|-|-
[Lijst met incidenten](api-list-incidents.md) | Lijst met [incidenten](api-incident.md) | Een lijst met incidenten weergeven.
[Incident bijwerken](api-update-incidents.md) | [Voorval](api-incident.md) | Een specifiek incident bijwerken.

## <a name="request-body-response-and-examples"></a>Hoofdtekst, antwoord en voorbeelden aanvragen

Raadpleeg de desbetreffende procedure artikelen voor meer informatie over het maken van een aanvraag of het parseren van een aanvraag, en voor praktische voorbeelden.

## <a name="common-properties"></a>Gemeenschappelijke eigenschappen

Eigenschap | Type | Beschrijving
-|-|-
incidentId | lang | Unieke ID van incident.
redirectIncidentId | met nullen lang | De incident-ID waarmee het huidige incident is samengevoegd.
voorval | tekenreeks | De naam van het incident.
createdTime | Offset | De datum en tijd (in UTC) waarop het incident is gemaakt.
lastUpdateTime | Offset | De datum en tijd (in UTC) waarop het incident voor het laatst is bijgewerkt.
ToegewezenAan | tekenreeks | Eigenaar van het incident.
Ernst | Opsommings | Ernst van het incident. Mogelijke waarden zijn: ```UnSpecified``` , ```Informational``` , ```Low``` , ```Medium``` en ```High``` .
status | Opsommings | Geeft de huidige status van het incident aan. Mogelijke waarden zijn: ```Active``` , ```Resolved``` , en ```Redirected``` .
Contactpersoonclassificatie | Opsommings | Specificatie van het incident. Mogelijke waarden zijn: ```Unknown``` , ```FalsePositive``` , ```TruePositive``` .
relevant | Opsommings | Hiermee wordt het bepalen van het incident aangegeven. Mogelijke waarden zijn: ```NotAvailable``` , ```Apt``` ,,, ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` , ```UnwantedSoftware``` , ```Other``` .
Tags | Lijst met tekenreeksen | Lijst met incident Tags.
kennisgeving | Lijst met waarschuwingen | Lijst met verwante meldingen. Zie voorbeelden in API-documentatie voor [lijst incidenten](api-list-incidents.md) .

## <a name="related-articles"></a>Verwante artikelen

- [Overzicht van Microsoft 365 Defender-Api's](api-overview.md)
- [Overzicht van incidenten](incidents-overview.md)
- [API voor lijst incidenten](api-list-incidents.md)
- [Update incident-API](api-update-incidents.md)
