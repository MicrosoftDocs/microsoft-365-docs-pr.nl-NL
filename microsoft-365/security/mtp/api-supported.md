---
title: Ondersteunde Microsoft 365 Defender-API's
description: Ondersteunde Microsoft 365 Defender-API's
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
ms.openlocfilehash: dbb7613dae3755b0fb794a3d68b5b424d765cc62
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719320"
---
# <a name="supported-microsoft-365-defender-apis"></a>Ondersteunde Microsoft 365 Defender-API's 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Van toepassing op:**
- Microsoft 365 Defender

> [!IMPORTANT]
> Sommige informatie verhoudt zich tot een voorvrijgegeven product dat bij de commerciële versie van de commerciële versie mogelijk ingrijpend werd gewijzigd. Microsoft biedt geen garanties, expliciete of impliciete informatie met betrekking tot de informatie die u hier opgeeft.

## <a name="list-of-available-apis"></a>Lijst met beschikbare Api's

Artikel | Beschrijving
-|-
[Geavanceerde API voor opsporing](api-advanced-hunting.md) | Voer geavanceerde zoekopdrachten uit.
[API's voor incidenten](api-incident.md) | U kunt lijsten met behulp van een lijst en update.

### <a name="endpoint-uris"></a>Url's van eindpunten

De basis-URI voor beide belangrijkste Api's is: https://api.security.microsoft.com . Voor betere prestaties gebruikt u een server dichter bij uw geolocatie:

- De Verenigde Staten: api-us.security.microsoft.com
- Europa: api-eu.security.microsoft.com
- Het Verenigd Koninkrijk: api-uk.security.microsoft.com

Tokens kunnen worden verkregen door toegang te krijgen https://api.security.microsoft.com .

Alle Api's langs het `/api` pad gebruiken het [OData](https://docs.microsoft.com/odata/overview) -protocol, bijvoorbeeld https://api.security.microsoft.com/api/incidents .

## <a name="related-articles"></a>Verwante artikelen

- [Overzicht van Microsoft 365 Defender-Api's](api-overview.md)
- [Toegang tot de Microsoft Threat Protection-Api's](api-access.md)
- [Meer informatie over API-limieten en licenties](api-terms.md)
- [Meer informatie over foutcodes](api-error-codes.md)
