---
title: Overzicht van Microsoft 365 Defender-API's
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 0fbe8751a9f82a8e264f1a38207744d091b57474
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922184"
---
# <a name="overview-of--microsoft-365-defender-apis"></a>Overzicht van Microsoft 365 Defender-API's

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Van toepassing op:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Sommige informatie heeft betrekking op vooraf uitgebracht product dat mogelijk aanzienlijk wordt gewijzigd voordat het commercieel wordt uitgebracht. Microsoft biedt geen garanties, uitdrukkelijk of impliciet, met betrekking tot de informatie die hier wordt verstrekt.

Microsoft 365 Defender is gebouwd op een platform dat klaar is voor integratie.

Gebruik de Microsoft 365 Defender-API's om werkstromen te automatiseren op basis van het gedeelde incident en geavanceerde zoektabellen.

- **[Wachtrij gecombineerde](api-incident.md)** incidenten: focus op wat kritiek is door het volledige aanvalsbereik en alle beïnvloede activa te groeperen onder de incident-API.

- **[Op zoek](api-advanced-hunting.md)** naar bedreigingen tussen producten: gebruik de organisatiekennis van uw beveiligingsteam om te zoeken naar tekenen van compromissen door uw eigen aangepaste query's te maken om onbewerkte gegevens te oversprokken die zijn verzameld in meerdere beveiligingsproducten.

Naast deze Microsoft 365 Defender-specifieke API's worden in elk van onze andere beveiligingsproducten extra [API's](api-articles.md) aan de man brengen om te profiteren van hun unieke mogelijkheden.

## <a name="learn-more"></a>Meer informatie

| **Meer informatie over het openen van de API's** |
|-|
| [Meer informatie over API-quota en -licenties](api-terms.md) |
| [De Microsoft 365 Defender-API's openen](api-access.md) |
| **Apps maken** |
| [Een 'Hello world' app maken](api-hello-world.md) |
| [Een app maken voor toegang tot Microsoft 365 Defender-API's namens een gebruiker](api-create-app-user-context.md) |
| [Een app maken voor toegang tot Microsoft 365 Defender zonder een gebruiker](api-create-app-web.md) |
| [Een app maken met partnertoegang voor meerdere tenants tot Microsoft 365 Defender-API's](api-partner-access.md) |
| **Problemen met uw apps oplossen en onderhouden** |
| [Api-foutcodes begrijpen](api-error-codes.md) |
| [Geheimen beheren in uw apps met Azure Key Vault](/learn/modules/manage-secrets-with-azure-key-vault/) |
| [OAuth 2.0-autorisatie implementeren voor het aanmelden van gebruikers](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code) |