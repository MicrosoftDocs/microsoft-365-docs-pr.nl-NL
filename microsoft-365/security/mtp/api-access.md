---
title: Toegang tot de Microsoft 365 Defender-Api's
description: Meer informatie over het openen van de Microsoft 365 Defender-Api's
keywords: Access, api's, toepassingscontext, gebruikerscontext, Aad-toepassing, toegangstoken
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
ms.openlocfilehash: 5e01aaf2ee9255fd909b26278346fd4ccf54729a
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719236"
---
# <a name="access-the-microsoft-365-defender-apis"></a>Toegang tot de Microsoft 365 Defender-Api's

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Van toepassing op:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Sommige informatie verhoudt zich tot een voorvrijgegeven product dat bij de commerciële versie van de commerciële versie mogelijk ingrijpend werd gewijzigd. Microsoft biedt geen garanties, expliciete of impliciete informatie met betrekking tot de informatie die u hier opgeeft.

Microsoft 365 Defender geeft veel van zijn gegevens en acties getoond via een set programmeer Api's. Met deze Api's kunt u werkstromen automatiseren en volledig gebruik maken van de mogelijkheden van Microsoft 365.

In het algemeen dient u de volgende stappen uit te voeren om de Api's te gebruiken:

- Een Azure Active Directory-toepassing maken
- Een toegangstoken verkrijgen met deze toepassing
- Het token gebruiken voor toegang tot de Microsoft 365 Defender API

> [!NOTE]
> Voor API-toegang is OAuth 2.0-authenticatie vereist. Voor meer informatie raadpleegt u [OAuth 2,0 Authorization code flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

Wanneer u deze stappen hebt uitgevoerd, bent u klaar om toegang te krijgen tot de Microsoft 365 Defender-API met een bepaalde context.

## <a name="application-context-recommended"></a>Toepassingscontext (aanbevolen)

Gebruik deze context voor apps die zonder een aangemelde gebruiker worden uitgevoerd, zoals Achtergrondservices of demonies.

1. Maak een Azure Active Directory-webtoepassing.
2. Wijs de gewenste machtigingen voor de toepassing toe.
3. Een sleutel voor de toepassing maken.
4. U ontvangt een beveiligingstoken met behulp van de toepassing en de bijbehorende sleutel.
5. Gebruik het token om toegang te krijgen tot de Microsoft 365 Defender API.

Zie **[een app maken voor toegang tot Microsoft 365 Defender zonder een gebruiker](api-create-app-web.md)** voor meer informatie.

## <a name="user-context"></a>Gebruikerscontext

Gebruik deze context om acties uit te voeren namens één gebruiker.

1. Maak een native Azure Active Directory-toepassing.
2. Wijs de gewenste machtiging voor de toepassing toe.
3. U ontvangt een beveiligingstoken met de gebruikersreferenties voor de toepassing.
4. Gebruik het token om toegang te krijgen tot de Microsoft 365 Defender API.

Zie voor meer informatie **[een app maken om toegang te krijgen tot Microsoft 365-api's voor een gebruiker](api-create-app-user-context.md)**.

## <a name="partner-context"></a>Partner context

Gebruik deze context wanneer u een app moet verlenen aan veel gebruikers in [meerdere tenants](https://docs.microsoft.com/azure/active-directory/develop/single-and-multi-tenant-apps).

1. Maak een Azure Active Directory-multi-tenant toepassing.
2. Wijs de gewenste machtiging voor de toepassing toe.
3. Neem de [beheerder toestemming](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) voor de app van elke Tenant.
4. U ontvangt een beveiligingstoken met behulp van gebruikersreferenties op basis van de Tenant-ID van een klant.
5. Gebruik het token om toegang te krijgen tot de Microsoft 365 Defender API.

Zie voor meer informatie **[een app met partner toegang maken voor Microsoft 365 Defender-api's](api-partner-access.md)**.

## <a name="related-articles"></a>Verwante artikelen

- [Overzicht van Microsoft 365 Defender-Api's](api-overview.md)
- [OAuth 2,0-autorisatie voor gebruikersaanmelding en API-toegang](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
- [Geheimen in uw server-apps beheren met Azure-sleutel kluis](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)
- [Een ' Hallo wereld '-toepassing maken waarmee de Microsoft 365-Api's worden geopend](api-hello-world.md)
