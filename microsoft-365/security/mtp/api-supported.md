---
title: Ondersteunde Microsoft Threat Protection-Api's
description: Ondersteunde Microsoft Threat Protection-Api's
keywords: MTP, API, API
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
ms.openlocfilehash: 49fa182a6142748ca7769411fe74389f365ba75f
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650228"
---
# <a name="supported-microsoft-threat-protection-apis"></a>Ondersteunde Microsoft Threat Protection-Api's 
**Van toepassing op:**
- Microsoft Threat Protection

>[!IMPORTANT] 
>Sommige informatie verhoudt zich tot een voorvrijgegeven product dat bij de commerciële versie van de commerciële versie mogelijk ingrijpend werd gewijzigd. Microsoft biedt geen garanties, expliciete of impliciete informatie met betrekking tot de informatie die u hier opgeeft.


### <a name="end-point-uris"></a>Uri's van eindpunt:

- De basis-URI van de service is: https://api.security.microsoft.com <br>

>[!NOTE]
>Voor betere prestaties kunt u Server dichter gebruiken voor uw geografische locatie:
> - api-us.security.microsoft.com
> - api-eu.security.microsoft.com
> - api-uk.security.microsoft.com

 - De resource voor het verwerving van tokens moet zijn: https://api.security.microsoft.com

 - Alle Api's onder ```/api``` Path zijn OData-api's. namelijk. ```https://api.security.microsoft.com/api/incidents```

## <a name="list-of-available-apis"></a>Lijst met beschikbare Api's:

Rond | Beschrijving
:---|:---
[Geavanceerde jacht-API](api-advanced-hunting.md) | Voer geavanceerde jacht-query's uit via API.
[Api's voor incidenten](api-incident.md) | Incidentele API-oproepen uitvoeren, zoals: incidenten vermelden, incident bijwerken en meer.
