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
ms.openlocfilehash: acd8ec28fb1d78e3724cb0ca0ebee48133e7310f
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985082"
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
[API voor geavanceerde opsporing](api-advanced-hunting.md) | Geavanceerde zoekquery's uitvoeren.
[API's voor incidenten](api-incident.md) | Lijst en werk incidenten bij, samen met andere praktische taken.
[Streaming API](streaming-api.md) (preview) | Verzend realtime gebeurtenissen en waarschuwingen als ze in één gegevensstroom voorkomen.

### <a name="endpoint-uris"></a>Eindpunt-URL's

De basis-URI voor beide hoofd-API's is: https://api.security.microsoft.com . Voor betere prestaties gebruikt u een server die dichter bij uw geolocatie staat:

- De Verenigde Staten: api-us.security.microsoft.com
- Europa: api-eu.security.microsoft.com
- Het Verenigd Koninkrijk: api-uk.security.microsoft.com

Tokens kunnen worden verkregen door toegang te krijgen https://api.security.microsoft.com tot .

Alle API's langs `/api` het pad gebruiken het [OData-protocol,](/odata/overview) bijvoorbeeld https://api.security.microsoft.com/api/incidents .

## <a name="related-articles"></a>Verwante artikelen

- [Microsoft 365 Defender OVERZICHT VAN API's](api-overview.md)
- [Toegang tot de Microsoft 365 Defender API's](api-access.md)
- [Streaming-API](../defender-endpoint/raw-data-export.md)
- [Meer informatie over API-limieten en -licenties](api-terms.md)
- [Foutcodes begrijpen](api-error-codes.md)
