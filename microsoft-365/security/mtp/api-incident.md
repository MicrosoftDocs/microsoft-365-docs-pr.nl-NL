---
title: Type incident bron in Microsoft 365 Defender API
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
ms.openlocfilehash: 68bee647cdd5687dbaad08ce3cd01b427dabf030
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844018"
---
# <a name="incident-resource-type"></a>Brontype incident

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

>[!IMPORTANT] 
>Sommige informatie verhoudt zich tot een voorvrijgegeven product dat bij de commerciële versie van de commerciële versie mogelijk ingrijpend werd gewijzigd. Microsoft biedt geen garanties, expliciete of impliciete informatie met betrekking tot de informatie die u hier opgeeft.

## <a name="methods"></a>Methode

Methode |Type resultaat |Beschrijving
:---|:---|:---
[Lijst met incidenten](api-list-incidents.md) | Lijst met [incidenten](api-incident.md) | Een lijst met incidenten weergeven.
[Incident bijwerken](api-update-incidents.md) | [Voorval](api-incident.md) | Update specifiek incident.


## <a name="properties"></a>Eigenschappen

Eigenschap |    Type    |    Beschrijving
:---|:---|:---
incidentId | lang | Unieke ID van incident.
redirectIncidentId | met nullen lang | De incident-ID waarmee het huidige incident is samengevoegd.
voorval | tekenreeks | De naam van het incident.
createdTime | Offset | De datum en tijd (in UTC) waarop het incident is gemaakt.
lastUpdateTime | Offset | De datum en tijd (in UTC) waarop het incident voor het laatst is bijgewerkt.
ToegewezenAan | tekenreeks | Eigenaar van het incident.
Ernst | Opsommings | Ernst van het incident. Mogelijke waarden zijn: ```UnSpecified``` , ```Informational``` , ```Low``` ```Medium``` en ```High``` .
status | Opsommings | Geeft de huidige status van het incident aan. Mogelijke waarden zijn: ```Active``` , ```Resolved``` en ```Redirected``` .
Contactpersoonclassificatie | Opsommings | Specificatie van het incident. Mogelijke waarden zijn: ```Unknown``` , ```FalsePositive``` , ```TruePositive``` .
relevant | Opsommings | Hiermee wordt het bepalen van het incident aangegeven. Mogelijke waarden zijn: ```NotAvailable``` , ```Apt``` ,,, ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` , ```UnwantedSoftware``` , ```Other``` .
Tags | Lijst met tekenreeksen | Lijst met incident Tags.
kennisgeving | Lijst met waarschuwingen | Lijst met verwante meldingen. Zie voorbeelden in API-documentatie voor [lijst incidenten](api-list-incidents.md) .
