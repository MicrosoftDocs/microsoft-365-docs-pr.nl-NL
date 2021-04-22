---
title: Ondersteunde Microsoft 365 Defender-API's
description: Ondersteunde Microsoft 365 Defender-API's
keywords: Microsoft 365 Defender, API's, api
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
ms.openlocfilehash: f2c66dca326589807f5712c5548c177a0d08ade0
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935723"
---
# <a name="supported-microsoft-365-defender-apis"></a>Ondersteunde Microsoft 365 Defender-API's 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Van toepassing op:**
- Microsoft 365 Defender

> [!IMPORTANT]
> Sommige informatie is gerelateerd aan voorlopige productversies die mogelijk aanzienlijk gewijzigd worden voordat ze commercieel gepubliceerd worden. Microsoft geeft geen garantie, uitdrukkelijk of impliciet, met betrekking tot de informatie die hier wordt beschreven.

## <a name="list-of-available-apis"></a>Lijst met beschikbare API's

Artikel | Beschrijving
-|-
[Geavanceerde API voor opsporing](api-advanced-hunting.md) | Geavanceerde zoekquery's uitvoeren.
[API's voor incidenten](api-incident.md) | Lijst en werk incidenten bij, samen met andere praktische taken.

### <a name="endpoint-uris"></a>Eindpunt-URL's

De basis-URI voor beide hoofd-API's is: https://api.security.microsoft.com . Voor betere prestaties gebruikt u een server die dichter bij uw geolocatie staat:

- De Verenigde Staten: api-us.security.microsoft.com
- Europa: api-eu.security.microsoft.com
- Het Verenigd Koninkrijk: api-uk.security.microsoft.com

Tokens kunnen worden verkregen door toegang te krijgen https://api.security.microsoft.com tot .

Alle API's langs `/api` het pad gebruiken het [OData-protocol,](/odata/overview) bijvoorbeeld https://api.security.microsoft.com/api/incidents .

## <a name="related-articles"></a>Verwante artikelen

- [Overzicht van Microsoft 365 Defender-API's](api-overview.md)
- [De Microsoft 365 Defender-API's openen](api-access.md)
- [Meer informatie over API-limieten en -licenties](api-terms.md)
- [Foutcodes begrijpen](api-error-codes.md)