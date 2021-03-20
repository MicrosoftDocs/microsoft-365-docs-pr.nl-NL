---
title: De Microsoft 365 Defender-API's openen
description: Meer informatie over het openen van de Microsoft 365 Defender-API's
keywords: access, api's, application context, user context, aad application, access token
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
ms.openlocfilehash: 17fa47fd9998f4097ff323e670b9e442d7126a94
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50903974"
---
# <a name="access-the-microsoft-365-defender-apis"></a>De Microsoft 365 Defender-API's openen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Van toepassing op:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Sommige informatie heeft betrekking op vooraf uitgebracht product dat mogelijk aanzienlijk wordt gewijzigd voordat het commercieel wordt uitgebracht. Microsoft biedt geen garanties, uitdrukkelijk of impliciet, met betrekking tot de informatie die hier wordt verstrekt.

Microsoft 365 Defender toont een groot deel van de gegevens en acties via een set programmatische API's. Met deze API's kunt u werkstromen automatiseren en volledig gebruikmaken van de mogelijkheden van Microsoft 365 Defender.

Over het algemeen moet u de volgende stappen nemen om de API's te gebruiken:

- Een Azure Active Directory-toepassing maken
- Een toegangs token krijgen met deze toepassing
- Het token gebruiken om toegang te krijgen tot de Microsoft 365 Defender-API

> [!NOTE]
> Api-toegang vereist OAuth2.0-verificatie. Zie [OAuth 2.0 Autorisatiecodestroom](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)voor meer informatie.

Nadat u deze stappen hebt voltooid, kunt u de Microsoft 365 Defender-API openen met een bepaalde context.

## <a name="application-context-recommended"></a>Toepassingscontext (aanbevolen)

Gebruik deze context voor apps die worden uitgevoerd zonder dat een aangemelde gebruiker aanwezig is, zoals achtergrondservices of daemons.

1. Een Azure Active Directory-webtoepassing maken.
2. Wijs de gewenste machtigingen toe aan de toepassing.
3. Maak een sleutel voor de toepassing.
4. Krijg een beveiligings-token met behulp van de toepassing en de sleutel.
5. Gebruik het token om toegang te krijgen tot de Microsoft 365 Defender-API.

Zie Een app maken voor toegang tot **[Microsoft 365 Defender zonder gebruiker voor meer informatie.](api-create-app-web.md)**

## <a name="user-context"></a>Context van gebruiker

Gebruik deze context om acties uit te voeren namens één gebruiker.

1. Maak een azure Active Directory-native toepassing.
2. Wijs de gewenste machtiging toe aan de toepassing.
3. Krijg een beveiligings-token met de gebruikersreferenties voor de toepassing.
4. Gebruik het token om toegang te krijgen tot de Microsoft 365 Defender-API.

Zie Een app maken voor toegang tot **[Microsoft 365 Defender-API's namens een gebruiker voor meer informatie.](api-create-app-user-context.md)**

## <a name="partner-context"></a>Partnercontext

Gebruik deze context wanneer u een app moet bieden aan veel gebruikers in [meerdere tenants.](/azure/active-directory/develop/single-and-multi-tenant-apps)

1. Maak een Azure Active Directory-toepassing met meerdere tenants.
2. Wijs de gewenste machtiging toe aan de toepassing.
3. Ontvang [toestemming van de](/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) beheerder voor de app van elke tenant.
4. Krijg een beveiligings-token met gebruikersreferenties op basis van de tenant-id van een klant.
5. Gebruik het token om toegang te krijgen tot de Microsoft 365 Defender-API.

Zie Een app maken met partnertoegang tot **[Microsoft 365 Defender-API's](api-partner-access.md)** voor meer informatie.

## <a name="related-articles"></a>Verwante artikelen

- [Overzicht van Microsoft 365 Defender-API's](api-overview.md)
- [OAuth 2.0-autorisatie voor gebruikers aanmelden en API-toegang](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
- [Geheimen beheren in uw server-apps met Azure Key Vault](/learn/modules/manage-secrets-with-azure-key-vault/)
- [Een 'Hello world'-toepassing maken die toegang heeft tot de Microsoft 365-API's](api-hello-world.md)