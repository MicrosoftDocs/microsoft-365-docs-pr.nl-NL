---
title: Microsoft 365 Api's voor Defender-incidenten en het type incidentbron
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 5cc149668e49e21b38b5fb95ae3f40db6c296e1d
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572583"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incident-resource-type"></a>Microsoft 365 Api voor Defender-incidenten en het type incidentbron

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Van toepassing op:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Sommige informatie is gerelateerd aan voorlopige productversies die mogelijk aanzienlijk gewijzigd worden voordat ze commercieel gepubliceerd worden. Microsoft geeft geen garantie, uitdrukkelijk of impliciet, met betrekking tot de informatie die hier wordt beschreven.

Een [incident](incidents-overview.md) is een verzameling gerelateerde waarschuwingen die een aanval helpen beschrijven. Gebeurtenissen van verschillende entiteiten in uw organisatie worden automatisch geaggregeerd door Microsoft 365 Defender. U kunt de incidenten-API gebruiken om programmatisch toegang te krijgen tot de incidenten en gerelateerde waarschuwingen van uw organisatie.

## <a name="quotas-and-resource-allocation"></a>Quota en toewijzing van middelen

U kunt maximaal 50 gesprekken per minuut of 1500 oproepen per uur aanvragen. Elke methode heeft ook zijn eigen quota. Zie het betreffende artikel voor de methode die u wilt gebruiken voor meer informatie over methodespecifieke quota.

Een `429` HTTP-antwoordcode geeft aan dat u een quotum hebt bereikt, hetzij op aantal verzonden aanvragen, hetzij op toegewezen looptijd. De hoofdtekst van de reactie bevat de tijd totdat het quotum dat u hebt bereikt, opnieuw wordt ingesteld.

## <a name="permissions"></a>Machtigingen

De incidenten-API vereist verschillende soorten machtigingen voor elk van de methoden. Zie het artikel van de betreffende methode voor meer informatie over vereiste machtigingen.

## <a name="methods"></a>Methoden

Methode | Retourtype | Omschrijving
-|-|-
[Lijst met incidenten](api-list-incidents.md) | [Lijst met incidenten](api-incident.md) | Krijg een lijst met incidenten.
[Incident bijwerken](api-update-incidents.md) | [incident](api-incident.md) | Een specifiek incident bijwerken.

## <a name="request-body-response-and-examples"></a>Hoofdtekst, antwoord en voorbeelden aanvragen

Raadpleeg de betreffende methodeartikelen voor meer informatie over het maken van een aanvraag of het parseren van een antwoord, en voor praktische voorbeelden.

## <a name="common-properties"></a>Gemeenschappelijke eigenschappen

Eigenschap | Type | Omschrijving
-|-|-
incidentId | lang | Unieke ID voor incidenten.
omleidingIncidentId | nullable lang | De incident-ID waaraan het huidige incident is samengevoegd.
incidentNaam | snaar | De naam van het incident.
gemaaktTijd | DatumTimeOffset | De datum en tijd (in UTC) waarop het incident is gemaakt.
laatsteUpdateTime | DatumTimeOffset | De datum en tijd (in UTC) van het incident zijn voor het laatst bijgewerkt.
toegewezenTo | snaar | Eigenaar van het incident.
strengheid | Enum | Ernst van het incident. Mogelijke waarden zijn: ```UnSpecified``` , , , , en ```Informational``` ```Low``` ```Medium``` ```High``` .
status | Enum | Hiermee geeft u de huidige status van het incident op. Mogelijke waarden zijn: ```Active``` ```Resolved``` , , en ```Redirected``` .
classificatie | Enum | Specificatie van het incident. Mogelijke waarden zijn: ```Unknown``` ```FalsePositive``` , , ```TruePositive``` .
vastberadenheid | Enum | Hiermee geeft u de bepaling van het incident op. Mogelijke waarden zijn: ```NotAvailable``` , , , , , ```Apt``` ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` ```UnwantedSoftware``` ```Other``` .
Tags | tekenreekslijst | Lijst met incidenttags.
Opmerkingen | Lijst met incidentopmerkingen | Incident Opmerkingsobject bevat: commentaartekenreeks, createdBy-tekenreeks en createTime-datumtijd.
Waarschuwingen | Waarschuwingslijst | Lijst met gerelateerde waarschuwingen. Zie voorbeelden bij [API-documentatie voor lijstincidenten.](api-list-incidents.md)

## <a name="related-articles"></a>Verwante artikelen

- [Microsoft 365 Defender API's overzicht](api-overview.md)
- [Overzicht incidenten](incidents-overview.md)
- [Api voor lijstincidenten](api-list-incidents.md)
- [Api voor incident bijwerken](api-update-incidents.md)
