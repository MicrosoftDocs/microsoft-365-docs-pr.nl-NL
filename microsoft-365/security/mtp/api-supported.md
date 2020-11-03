---
title: Ondersteunde Microsoft 365 Defender-Api's
description: Ondersteunde Microsoft 365 Defender-Api's
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
ms.openlocfilehash: b7c0accf2d649d4ad6177260294922ee17783f2c
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844958"
---
# <a name="supported-microsoft-365-defender-apis"></a>Ondersteunde Microsoft 365 Defender-Api's 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Van toepassing op:**
- Microsoft 365 Defender

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
[Geavanceerde API voor opsporing](api-advanced-hunting.md) | Voer geavanceerde jacht-query's uit via API.
[API's voor incidenten](api-incident.md) | Incidentele API-oproepen uitvoeren, zoals: incidenten vermelden, incident bijwerken en meer.
