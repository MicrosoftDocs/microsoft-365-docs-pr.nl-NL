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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: b2239b960106d756cbd29504af05af77a553067d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056664"
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
- [Toegang tot de API's voor Microsoft Threat Protection](api-access.md)
- [Meer informatie over API-limieten en -licenties](api-terms.md)
- [Foutcodes begrijpen](api-error-codes.md)