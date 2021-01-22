---
title: Toegang tot de Microsoft 365 Defender-API's
description: Informatie over toegang tot de Microsoft 365 Defender-API's
keywords: access, apis, toepassingscontext, gebruikerscontext, aad-toepassing, toegang token
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
ms.openlocfilehash: ea787adfba0afb425da5f6ea0f6609f96e06b378
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932152"
---
# <a name="access-the-microsoft-365-defender-apis"></a>Toegang tot de Microsoft 365 Defender-API's

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Van toepassing op:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Sommige informatie heeft betrekking op vooraf uitgebracht product dat aanzienlijk kan worden gewijzigd voordat het in de handel wordt gebracht. Microsoft biedt geen garanties, uitdrukkelijk of impliciet, met betrekking tot de informatie die hier wordt be gegeven.

Microsoft 365 Defender laat veel van zijn gegevens en acties zien via een set programmatische API's. Deze API's helpen u werkstromen te automatiseren en volledig gebruik te maken van de mogelijkheden van Microsoft 365 Defender.

Over het algemeen moet u de volgende stappen nemen om de API's te gebruiken:

- Een Azure Active Directory-toepassing maken
- Een toegangs token krijgen met deze toepassing
- Het token gebruiken om toegang te krijgen tot de Microsoft 365 Defender-API

> [!NOTE]
> Voor API-toegang is OAuth2.0-verificatie vereist. Zie [OAuth 2.0 Authorization Code Flow voor](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)meer informatie.

Als u deze stappen hebt voltooid, kunt u de Microsoft 365 Defender-API openen in een bepaalde context.

## <a name="application-context-recommended"></a>Toepassingscontext (aanbevolen)

Gebruik deze context voor apps die worden uitgevoerd zonder dat een aangemelde gebruiker aanwezig is, zoals achtergrondservices of daemons.

1. Maak een Azure Active Directory-webtoepassing.
2. Wijs de gewenste machtigingen toe aan de toepassing.
3. Maak een sleutel voor de toepassing.
4. Haal een beveiligings token op met behulp van de toepassing en de sleutel.
5. Gebruik het token om toegang te krijgen tot de Microsoft 365 Defender-API.

Zie Een app maken voor toegang **[tot Microsoft 365 Defender zonder gebruiker voor meer informatie.](api-create-app-web.md)**

## <a name="user-context"></a>Gebruikerscontext

Gebruik deze context om acties uit te voeren namens één gebruiker.

1. Maak een in azure Active Directory native toepassing.
2. Wijs de gewenste machtiging aan de toepassing toe.
3. Haal een beveiligings token op met behulp van de gebruikersreferenties voor de toepassing.
4. Gebruik het token om toegang te krijgen tot de Microsoft 365 Defender-API.

Zie Een app maken voor toegang **[tot Microsoft 365 Defender-API's namens een gebruiker voor meer informatie.](api-create-app-user-context.md)**

## <a name="partner-context"></a>Partnercontext

Gebruik deze context wanneer u een app moet bieden aan veel gebruikers in [meerdere tenants.](https://docs.microsoft.com/azure/active-directory/develop/single-and-multi-tenant-apps)

1. Maak een Azure Active Directory-toepassing met meerdere tenants.
2. Wijs de gewenste machtiging aan de toepassing toe.
3. Krijg [toestemming van de](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) beheerder voor de app in elke tenant.
4. Haal een beveiligings token op met behulp van gebruikersreferenties op basis van de tenant-id van een klant.
5. Gebruik het token om toegang te krijgen tot de Microsoft 365 Defender-API.

Zie Een app maken met partnertoegang tot **[Microsoft 365 Defender API's voor](api-partner-access.md)** meer informatie.

## <a name="related-articles"></a>Verwante artikelen

- [Overzicht van Microsoft 365 Defender API's](api-overview.md)
- [OAuth 2.0 authorization for user sign in and API access](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
- [Geheimen in uw server-apps beheren met Azure Key Vault](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)
- [Een 'Hallo wereld'-toepassing maken voor toegang tot de Microsoft 365-API's](api-hello-world.md)
