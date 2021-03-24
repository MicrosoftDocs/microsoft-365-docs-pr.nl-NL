---
title: Api's voor Microsoft 365 Defender-incidenten en het type incidentresource
description: Meer informatie over de methoden en eigenschappen van het type incidentresource in Microsoft 365 Defender
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
ms.openlocfilehash: 0a9022c0448ae0ddc16dc996ca93075abf6b2857
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056673"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incident-resource-type"></a>Microsoft 365 Defender-incidenten API en het type incidentresource

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Van toepassing op:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Sommige informatie is gerelateerd aan voorlopige productversies die mogelijk aanzienlijk gewijzigd worden voordat ze commercieel gepubliceerd worden. Microsoft geeft geen garantie, uitdrukkelijk of impliciet, met betrekking tot de informatie die hier wordt beschreven.

Een [incident](incidents-overview.md) is een verzameling gerelateerde waarschuwingen die helpen bij het beschrijven van een aanval. Gebeurtenissen uit verschillende entiteiten in uw organisatie worden automatisch samengevoegd door Microsoft 365 Defender. U kunt de API voor incidenten gebruiken om programmaatically toegang te krijgen tot de incidenten en gerelateerde waarschuwingen van uw organisatie.

## <a name="quotas-and-resource-allocation"></a>Quota en resourcetoewijzing

U kunt maximaal 50 oproepen per minuut of 1500 oproepen per uur aanvragen. Elke methode heeft ook een eigen quotum. Zie het betreffende artikel voor de methode die u wilt gebruiken voor meer informatie over methodespecifieke quota.

Een HTTP-antwoordcode geeft aan dat u een quotum hebt bereikt, hetzij op het aantal verzonden aanvragen, hetzij door de toegewezen `429` gebruikstijd. De reactie body bevat de tijd totdat het quotum dat u hebt bereikt, opnieuw wordt ingesteld.

## <a name="permissions"></a>Machtigingen

Voor de API voor incidenten zijn verschillende soorten machtigingen voor elk van de methoden vereist. Zie het artikel van de betreffende methode voor meer informatie over vereiste machtigingen.

## <a name="methods"></a>Methoden

Methode | Retourtype | Beschrijving
-|-|-
[Lijst met incidenten](api-list-incidents.md) | [Lijst met incidenten](api-incident.md) | Een lijst met incidenten.
[Incident bijwerken](api-update-incidents.md) | [Incident](api-incident.md) | Een specifiek incident bijwerken.

## <a name="request-body-response-and-examples"></a>Body, antwoord en voorbeelden aanvragen

Raadpleeg de betreffende methodeartikelen voor meer informatie over het maken van een aanvraag of het parseren van een antwoord en voor praktische voorbeelden.

## <a name="common-properties"></a>Veelgebruikte eigenschappen

Eigenschap | Type | Beschrijving
-|-|-
incidentId | lang | Unieke id voor incidenten.
redirectIncidentId | nullable long | De incident-id waarbij het huidige incident is samengevoegd.
incidentName | tekenreeks | De naam van het incident.
createdTime | DateTimeOffset | De datum en tijd (in UTC) het incident is gemaakt.
lastUpdateTime | DateTimeOffset | De datum en tijd (in UTC) het incident is voor het laatst bijgewerkt.
toegewezenTo | tekenreeks | Eigenaar van het incident.
ernst | Enum | Ernst van het incident. Mogelijke waarden zijn: ```UnSpecified``` , , , en ```Informational``` ```Low``` ```Medium``` ```High``` .
status | Enum | Hiermee geeft u de huidige status van het incident op. Mogelijke waarden zijn: ```Active``` ```Resolved``` , en ```Redirected``` .
classificatie | Enum | Specificatie van het incident. Mogelijke waarden zijn: ```Unknown``` ```FalsePositive``` , , ```TruePositive``` .
bepaling | Enum | Hiermee geeft u de bepaling van het incident op. Mogelijke waarden zijn: ```NotAvailable``` , , , , , , ```Apt``` ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` ```UnwantedSoftware``` . ```Other```
tags | lijst met tekenreeksen | Lijst met incidentlabels.
waarschuwingen | Lijst met waarschuwingen | Lijst met gerelateerde waarschuwingen. Zie voorbeelden van [API-documentatie lijstincidenten.](api-list-incidents.md)

## <a name="related-articles"></a>Verwante artikelen

- [Overzicht van Microsoft 365 Defender-API's](api-overview.md)
- [Overzicht van incidenten](incidents-overview.md)
- [Lijstincidenten API](api-list-incidents.md)
- [Api voor incidenten bijwerken](api-update-incidents.md)
