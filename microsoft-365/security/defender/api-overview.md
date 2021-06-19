---
title: Overzicht van Microsoft 365 Defender API's
description: Meer informatie over de beschikbare API's in Microsoft 365 Defender
keywords: api's, overzicht, incident, incidenten, bedreigingsjacht, microsoft 365 defender
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
ms.openlocfilehash: 2ca601c3c68df9f9f1cc4fb90bcfbe907850ce91
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029727"
---
# <a name="overview-of-microsoft-365-defender-apis"></a>Overzicht van Microsoft 365 Defender API's

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Van toepassing op:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Sommige informatie is gerelateerd aan voorlopige productversies die mogelijk aanzienlijk gewijzigd worden voordat ze commercieel gepubliceerd worden. Microsoft geeft geen garantie, uitdrukkelijk of impliciet, met betrekking tot de informatie die hier wordt beschreven.

Microsoft 365 Defender is gebouwd op een platform dat klaar is voor integratie.

Gebruik de Microsoft 365 Defender API's om werkstromen te automatiseren op basis van het gedeelde incident en geavanceerde zoektabellen.

- **[Wachtrij gecombineerde](api-incident.md)** incidenten: focus op wat kritiek is door het volledige aanvalsbereik en alle beïnvloede activa te groeperen onder de incident-API.

- **[Op zoek](api-advanced-hunting.md)** naar bedreigingen tussen producten: gebruik de organisatiekennis van uw beveiligingsteam om te zoeken naar tekenen van compromissen door uw eigen aangepaste query's te maken om onbewerkte gegevens te oversprokken die zijn verzameld in meerdere beveiligingsproducten.

Gebruik de [Streaming API om](../defender-endpoint/raw-data-export.md) realtimegebeurtenissen en waarschuwingen van exemplaren te verzenden terwijl deze binnen één gegevensstroom plaatsvinden.

Naast deze Microsoft 365 Defender-specifieke API's, worden in elk [](api-articles.md) van onze andere beveiligingsproducten extra API's aan de man Microsoft 365 Defender om te profiteren van hun unieke mogelijkheden.

> [!NOTE]
> De overgang naar de geïntegreerde portal mag geen invloed hebben op de PowerBi-dashboards op basis van MICROSOFT Defender voor eindpunt-API's. U kunt blijven werken met de bestaande API's, ongeacht de interactieve portalovergang.

## <a name="learn-more"></a>Meer informatie

| **Meer informatie over het openen van de API's** |
|-|
| [Meer informatie over API-quota en -licenties](api-terms.md) |
| [Toegang tot de Microsoft 365 Defender API's](api-access.md) |
| **Apps maken** |
| [Een 'Hello world' app maken](api-hello-world.md) |
| [Een app maken voor toegang Microsoft 365 Defender API's namens een gebruiker](api-create-app-user-context.md) |
| [Een app maken voor toegang tot Microsoft 365 Defender zonder een gebruiker](api-create-app-web.md) |
| [Een app maken met partnertoegang voor meerdere tenants Microsoft 365 Defender API's](api-partner-access.md) |
| **Problemen met uw apps oplossen en onderhouden** |
| [Api-foutcodes begrijpen](api-error-codes.md) |
| [Geheimen beheren in uw apps met Azure Key Vault](/learn/modules/manage-secrets-with-azure-key-vault/) |
| [OAuth 2.0-autorisatie implementeren voor het aanmelden van gebruikers](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code) |