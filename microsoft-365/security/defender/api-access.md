---
title: Toegang tot de Microsoft 365 Defender API's
description: Informatie over het openen van de Microsoft 365 Defender API's
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 03fd82cd5dc24653b6d67fa47cc225d355bfac45
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028797"
---
# <a name="access-the-microsoft-365-defender-apis"></a>Toegang tot de Microsoft 365 Defender API's

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Van toepassing op:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Sommige informatie is gerelateerd aan voorlopige productversies die mogelijk aanzienlijk gewijzigd worden voordat ze commercieel gepubliceerd worden. Microsoft geeft geen garantie, uitdrukkelijk of impliciet, met betrekking tot de informatie die hier wordt beschreven.

Microsoft 365 Defender worden veel van de gegevens en acties ervan via een set programmatische API's openbaar. Met deze API's kunt u werkstromen automatiseren en volledig gebruikmaken van Microsoft 365 Defender de mogelijkheden van de Microsoft 365 Defender.

Over het algemeen moet u de volgende stappen nemen om de API's te gebruiken:

- Een Azure Active Directory maken
- Een toegangs token krijgen met deze toepassing
- Het token gebruiken om toegang te krijgen tot de Microsoft 365 Defender API

> [!NOTE]
> Api-toegang vereist OAuth2.0-verificatie. Zie [OAuth 2.0 Autorisatiecode](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)voor Flow.

Nadat u deze stappen hebt voltooid, bent u klaar om toegang te krijgen tot de Microsoft 365 Defender API met een bepaalde context.

## <a name="application-context-recommended"></a>Toepassingscontext (aanbevolen)

Gebruik deze context voor apps die worden uitgevoerd zonder dat een aangemelde gebruiker aanwezig is, zoals achtergrondservices of daemons.

1. Maak een Azure Active Directory webtoepassing.
2. Wijs de gewenste machtigingen toe aan de toepassing.
3. Maak een sleutel voor de toepassing.
4. Krijg een beveiligings-token met behulp van de toepassing en de sleutel.
5. Gebruik het token om toegang te krijgen tot Microsoft 365 Defender API.

Zie Een app maken voor toegang tot Microsoft 365 Defender **[zonder gebruiker voor meer informatie.](api-create-app-web.md)**

## <a name="user-context"></a>Context van gebruiker

Gebruik deze context om acties uit te voeren namens één gebruiker.

1. Maak een Azure Active Directory eigen toepassing.
2. Wijs de gewenste machtiging toe aan de toepassing.
3. Krijg een beveiligings-token met de gebruikersreferenties voor de toepassing.
4. Gebruik het token om toegang te krijgen tot Microsoft 365 Defender API.

Zie Een app maken voor toegang tot Microsoft 365 Defender **[API's namens een gebruiker voor meer informatie.](api-create-app-user-context.md)**

## <a name="partner-context"></a>Partnercontext

Gebruik deze context wanneer u een app moet bieden aan veel gebruikers in [meerdere tenants.](/azure/active-directory/develop/single-and-multi-tenant-apps)

1. Maak een Azure Active Directory multi-tenanttoepassing.
2. Wijs de gewenste machtiging toe aan de toepassing.
3. Ontvang [toestemming van de](/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) beheerder voor de app van elke tenant.
4. Krijg een beveiligings-token met gebruikersreferenties op basis van de tenant-id van een klant.
5. Gebruik het token om toegang te krijgen tot Microsoft 365 Defender API.

Zie Een app maken met partnertoegang tot Microsoft 365 Defender **[API's voor meer informatie.](api-partner-access.md)**

## <a name="related-articles"></a>Verwante artikelen

- [Microsoft 365 Defender OVERZICHT VAN API's](api-overview.md)
- [OAuth 2.0-autorisatie voor gebruikers aanmelden en API-toegang](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
- [Geheimen beheren in uw server-apps met Azure Key Vault](/learn/modules/manage-secrets-with-azure-key-vault/)
- [Een 'Hello world'-toepassing maken die toegang heeft tot de Microsoft 365 API's](api-hello-world.md)