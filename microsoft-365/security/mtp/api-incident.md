---
title: Microsoft 365 Defender-incidenten API's en het type incidentresource
description: Meer informatie over de methoden en eigenschappen van het resourcetype Incident in Microsoft 365 Defender
keywords: incident, incidenten, api
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
ms.openlocfilehash: 37413c3c7458527e90d4657ddfb3afb058e1dfaa
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928352"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incident-resource-type"></a>Api voor Microsoft 365 Defender-incidenten en het type incidentresource

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Van toepassing op:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Sommige informatie heeft betrekking op vooraf uitgebracht product dat aanzienlijk kan worden gewijzigd voordat het in de handel wordt gebracht. Microsoft biedt geen garanties, uitdrukkelijk of impliciet, met betrekking tot de informatie die hier wordt be gegeven.

Een [incident](incidents-overview.md) is een verzameling gerelateerde waarschuwingen die een aanval helpen beschrijven. Gebeurtenissen van verschillende entiteiten in uw organisatie worden automatisch samengevoegd door Microsoft 365 Defender. U kunt de INCIDENTEN-API gebruiken om programmatisch toegang te krijgen tot de incidenten en gerelateerde waarschuwingen van uw organisatie.

## <a name="quotas-and-resource-allocation"></a>Quota en resourcetoewijzing

U kunt maximaal 50 oproepen per minuut of 1500 oproepen per uur aanvragen. Elke methode heeft ook een eigen quota. Zie het desbetreffende artikel over de methode die u wilt gebruiken voor meer informatie over methodespecifieke quota's.

Een HTTP-antwoordcode geeft aan dat u een quotum hebt bereikt, hetzij door het aantal verzonden aanvragen of door de toegewezen `429` lopende tijd. De reactie zelf bevat de tijd tot het quotum dat u hebt bereikt, wordt opnieuw ingesteld.

## <a name="permissions"></a>Machtigingen

De API voor incidenten vereist verschillende soorten machtigingen voor elk van de methoden. Zie het artikel van de desbetreffende methode voor meer informatie over vereiste machtigingen.

## <a name="methods"></a>Methoden

Methode | Type retournering | Beschrijving
-|-|-
[Lijst met incidenten](api-list-incidents.md) | [Lijst met incidenten](api-incident.md) | Hier wordt een lijst met incidenten weergegeven.
[Incident bijwerken](api-update-incidents.md) | [Incident](api-incident.md) | Een specifiek incident bijwerken.

## <a name="request-body-response-and-examples"></a>De body, het antwoord en voorbeelden aanvragen

Raadpleeg de artikelen met de desbetreffende methode voor meer informatie over het maken van een aanvraag of het parseren van een antwoord en voor praktische voorbeelden.

## <a name="common-properties"></a>Algemene eigenschappen

Eigenschap | Type | Beschrijving
-|-|-
incidentId | lang | Unieke id voor incident.
redirectIncidentId | nullable long | De incident-id die het huidige incident is samengevoegd.
incidentName | tekenreeks | De naam van het incident.
createdTime | DateTimeOffset | De datum en tijd (in UTC) het incident is gemaakt.
lastUpdateTime | DateTimeOffset | De datum en tijd (in UTC) het incident is voor het laatst bijgewerkt.
toegewezen Aan | tekenreeks | Eigenaar van het incident.
ernst | Enum | Ernst van het incident. Mogelijke waarden zijn: ```UnSpecified``` ```Informational``` , , en ```Low``` ```Medium``` ```High``` .
status | Enum | Hiermee geeft u de huidige status van het incident op. Mogelijke waarden zijn: ```Active``` ```Resolved``` en ```Redirected``` .
classificatie | Enum | Specificatie van het incident. Mogelijke waarden zijn: ```Unknown``` ```FalsePositive``` , ```TruePositive``` .
besluit | Enum | Bepaalt de vaststelling van het incident. Mogelijke waarden zijn: ```NotAvailable``` ```Apt``` , , , ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` ```UnwantedSoftware``` . ```Other```
tags | lijst met tekenreeksen | Lijst met incidentlabels.
waarschuwingen | Lijst met waarschuwingen | Lijst met gerelateerde waarschuwingen. Bekijk voorbeelden van [API-documentatie voor lijstincidenten.](api-list-incidents.md)

## <a name="related-articles"></a>Verwante artikelen

- [Overzicht van Microsoft 365 Defender API's](api-overview.md)
- [Overzicht van incidenten](incidents-overview.md)
- [Api voor lijstincidenten](api-list-incidents.md)
- [Update-incident-API](api-update-incidents.md)
