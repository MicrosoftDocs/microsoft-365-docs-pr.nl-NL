---
title: Toegang tot Microsoft 365 Defender gegevens beheren in het Microsoft 365 beveiligingscentrum
description: Meer informatie over het beheren van machtigingen voor gegevens in Microsoft 365 Defender
keywords: access, permissions, Microsoft 365 Defender, M365, security, MCAS, Cloud App Security, Microsoft Defender for Endpoint, scope, scoping, RBAC
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 738315c446fd57d4cd027de92eb77b0029f84323
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177526"
---
# <a name="manage-access-to-microsoft-365-defender-with-azure-active-directory-global-roles"></a>Toegang tot Microsoft 365 Defender beheren met Azure Active Directory globale rollen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

Er zijn twee manieren om toegang tot Microsoft 365 Defender
- **Hoofdrollen Azure Active Directory (AD)**
- **Aangepaste roltoegang**

Accounts die zijn toegewezen aan de volgende **Azure Active Directory (AD)** hebben toegang tot Microsoft 365 Defender functionaliteit en gegevens:
- Globale beheerder
- Beveiligingsbeheerder
- Beveiligingsoperator
- Algemene lezer
- Beveiligingslezer

Als u accounts met deze rollen wilt controleren, [bekijkt u Machtigingen in het Microsoft 365 beveiligingscentrum.](https://security.microsoft.com/permissions)

**Aangepaste roltoegang** is een nieuwe mogelijkheid in Microsoft 365 Defender en stelt u in staat om de toegang tot specifieke gegevens, taken en mogelijkheden in Microsoft Defender 365 te beheren. Aangepaste rollen bieden meer controle dan globale Azure AD-rollen, zodat gebruikers alleen de benodigde toegang hebben met de minst permissieve rollen die nodig zijn.  Aangepaste rollen kunnen worden gemaakt naast globale Azure AD-rollen. [Meer informatie over aangepaste rollen.](custom-roles.md)

> [!NOTE]
> Dit artikel is alleen van toepassing op het beheren van globale Azure Active Directory rollen. Zie Aangepaste rollen voor toegangsbeheer op basis van rollen voor meer informatie over het gebruik van aangepaste toegangsbeheer op basis [van rollen](custom-roles.md)

## <a name="access-to-functionality"></a>Toegang tot functionaliteit
Toegang tot specifieke functionaliteit wordt bepaald door uw [Azure AD-rol.](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) Neem contact op met een globale beheerder als u toegang nodig hebt tot specifieke functionaliteit die vereist dat u of uw gebruikersgroep een nieuwe rol krijgt toegewezen.

### <a name="approve-pending-automated-tasks"></a>In behandeling zijnde geautomatiseerde taken goedkeuren
[Geautomatiseerde onderzoeken en herstel](m365d-autoir-actions.md) kunnen actie ondernemen op basis van e-mailberichten, regels voor doorsturen, bestanden, persistentiemechanismen en andere artefacten die tijdens onderzoeken zijn gevonden. Als u in behandeling zijnde acties wilt goedkeuren of afwijzen waarvoor expliciete goedkeuring is vereist, moet u bepaalde rollen hebben toegewezen in Microsoft 365. Zie Machtigingen voor [actiecentrum voor meer informatie.](m365d-action-center.md#required-permissions-for-action-center-tasks)

## <a name="access-to-data"></a>Toegang tot gegevens
Toegang tot Microsoft 365 Defender gegevens kan worden bepaald met behulp van het bereik dat is toegewezen aan gebruikersgroepen in Microsoft Defender for Endpoint role-based access control (RBAC). Als uw toegang niet is beperkt tot een specifieke set apparaten in het Defender voor Eindpunt, hebt u volledige toegang tot gegevens in Microsoft 365 Defender. Wanneer uw account echter een bereik heeft, ziet u alleen gegevens over de apparaten in uw bereik.

Als u bijvoorbeeld tot slechts één gebruikersgroep behoort met een Microsoft Defender voor eindpuntrol en die gebruikersgroep alleen toegang heeft gekregen tot verkoopapparaten, ziet u alleen gegevens over verkoopapparaten in Microsoft 365 Defender. [Meer informatie over RBAC-instellingen in Microsoft Defender voor Eindpunt](/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a>Microsoft Cloud App Security toegangsbesturingselementen
Tijdens het voorbeeld worden Microsoft 365 Defender toegangsbesturingselementen niet afgedwongen op basis van Cloud App Security instellingen. Toegang tot Microsoft 365 Defender gegevens wordt niet beïnvloed door deze instellingen.

## <a name="related-topics"></a>Gerelateerde onderwerpen
- [Aangepaste rollen in op rollen gebaseerd toegangsbeheer voor Microsoft 365 Defender](custom-roles.md)
- [Azure AD-rollen](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [Microsoft Defender voor Endpoint RBAC](/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [Cloud App Security rollen](/cloud-app-security/manage-admins)
