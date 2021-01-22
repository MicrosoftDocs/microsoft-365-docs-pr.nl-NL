---
title: Ondersteunde Microsoft 365 Defender-API's
description: Ondersteunde Microsoft 365 Defender-API's
keywords: MTP, API's, api
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
ms.openlocfilehash: ee03e5a255a88c084403842e7bf0319c06c0517b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926196"
---
# <a name="supported-microsoft-365-defender-apis"></a>Ondersteunde Microsoft 365 Defender-API's 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Van toepassing op:**
- Microsoft 365 Defender

> [!IMPORTANT]
> Sommige informatie heeft betrekking op vooraf uitgebracht product dat aanzienlijk kan worden gewijzigd voordat het in de handel wordt gebracht. Microsoft biedt geen garanties, uitdrukkelijk of impliciet, met betrekking tot de informatie die hier wordt be gegeven.

## <a name="list-of-available-apis"></a>Lijst met beschikbare API's

Artikel | Beschrijving
-|-
[Geavanceerde API voor opsporing](api-advanced-hunting.md) | Voer geavanceerde zoekquery's uit.
[API's voor incidenten](api-incident.md) | Vermeld en werk incidenten bij, samen met andere praktische taken.

### <a name="endpoint-uris"></a>URI's voor eindpunten

De basis-URI voor beide hoofd-API's is: https://api.security.microsoft.com . Gebruik voor betere prestaties een server dichter bij uw geolocatie:

- Verenigde Staten: api-us.security.microsoft.com
- Europa: api-eu.security.microsoft.com
- Verenigd Koninkrijk: api-uk.security.microsoft.com

Tokens kunnen worden verkregen door toegang te krijgen tot https://api.security.microsoft.com .

Alle API's op `/api` het pad maken gebruik van het [OData-protocol,](https://docs.microsoft.com/odata/overview) https://api.security.microsoft.com/api/incidents bijvoorbeeld.

## <a name="related-articles"></a>Verwante artikelen

- [Overzicht van Microsoft 365 Defender API's](api-overview.md)
- [Toegang tot de Microsoft Threat Protection-API's](api-access.md)
- [Meer informatie over API-limieten en licenties](api-terms.md)
- [Meer te weten komen over foutcodes](api-error-codes.md)
