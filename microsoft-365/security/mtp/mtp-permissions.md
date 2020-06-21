---
title: Toegang tot Microsoft Threat Protection-gegevens beheren in het Microsoft 365-beveiligingscentrum
description: Meer informatie over het beheren van machtigingen voor gegevens in Microsoft Threat Protection
keywords: toegang, machtigingen, MTP, Microsoft Threat Protection, M365, beveiliging, MCAS, MDATP, Cloud App Security, Microsoft Defender Advanced Threat Protection, scope, scoping, RBAC
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: f747737fc94241ca5f65ad9881715f517d5fbe3c
ms.sourcegitcommit: 51e47ca4b355436a2ad3deb154060eb1927428e6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/17/2020
ms.locfileid: "44773837"
---
# <a name="manage-access-to-microsoft-threat-protection"></a>Toegang tot Microsoft-bedreigingsbeveiliging beheren

**Van toepassing op:**
- Microsoft Threat Protection

Accounts die de volgende Azure Active Directory(AD)-rollen hebben toegewezen, hebben toegang tot de functionaliteit en gegevens van Microsoft Threat Protection:
- Globale beheerder
- Beveiligingsbeheerder
- Beveiligingsoperator
- Global Reader
- Beveiligingslezer

Als u accounts met deze rollen wilt controleren, [bekijkt u Machtigingen in het Microsoft 365-beveiligingscentrum](https://security.microsoft.com/permissions).

## <a name="access-to-functionality"></a>Toegang tot functionaliteit
Toegang tot specifieke functionaliteit wordt bepaald door uw [Azure AD-rol.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) Neem contact op met een globale beheerder als u toegang nodig hebt tot specifieke functionaliteit waarvoor u of uw gebruikersgroep een nieuwe rol moet krijgen toegewezen.

### <a name="approve-pending-automated-tasks"></a>In behandeling zijnde geautomatiseerde taken goedkeuren
[Geautomatiseerd onderzoek en herstel](mtp-autoir-actions.md) kan actie ondernemen op e-mails, doorsturen regels, bestanden, persistentie mechanismen, en andere artefacten gevonden tijdens onderzoeken. Als u lopende acties wilt goedkeuren of afwijzen waarvoor expliciete goedkeuring vereist is, moet u bepaalde rollen hebben toegewezen in Microsoft 365. Zie [Machtigingen van het Onderhoudscentrum voor](mtp-action-center.md#required-permissions-for-action-center-tasks)meer informatie .

## <a name="access-to-data"></a>Toegang tot gegevens
Toegang tot Microsoft Threat Protection-gegevens kan worden beheerd met behulp van het bereik dat is toegewezen aan gebruikersgroepen in het RBAC (Microsoft Defender ATP role-based access control). Als uw toegang niet is beperkt tot een specifieke set apparaten in de Microsoft Defender ATP, hebt u volledige toegang tot gegevens in Microsoft Threat Protection. Zodra uw account echter is gescoped, ziet u alleen gegevens over de apparaten in uw bereik.

Als u bijvoorbeeld tot slechts één gebruikersgroep behoort met een Microsoft Defender ATP-rol en die gebruikersgroep alleen toegang heeft gekregen tot verkoopapparaten, ziet u alleen gegevens over verkoopapparaten in Microsoft Threat Protection. [Meer informatie over RBAC-instellingen in Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a>Toegangsbesturingselementen voor microsoft cloud-app-beveiliging
Tijdens de preview dwingt Microsoft Threat Protection geen toegangscontroles af op basis van beveiligingsinstellingen voor cloud-apps. De toegang tot microsoft-gegevens over bedreigingsbescherming wordt niet beïnvloed door deze instellingen.

## <a name="related-topics"></a>Verwante onderwerpen

- [Azure AD-rollen](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [Microsoft Defender ATP RBAC](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [Beveiligingsrollen voor cloud-apps](https://docs.microsoft.com/cloud-app-security/manage-admins)
