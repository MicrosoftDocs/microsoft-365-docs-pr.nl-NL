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
ms.openlocfilehash: 110bbe6fe48932217c9bdc009d175161fe9226cd
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/24/2020
ms.locfileid: "42812442"
---
# <a name="manage-access-to-microsoft-threat-protection"></a>Toegang tot Microsoft Threat Protection beheren

**Van toepassing op:**
- Microsoft-bedreigingsbeveiliging



Accounts die de volgende AD-rollen (Azure Directory) hebben toegewezen, hebben toegang tot de functionaliteit en gegevens van Microsoft Threat Protection:
- Globale beheerder
- Beveiligingsbeheerder
- Beveiligingsoperator
- Globale lezer
- Beveiligingslezer

Als u accounts met deze rollen wilt bekijken, [bekijkt u Machtigingen in het Microsoft 365-beveiligingscentrum](https://security.microsoft.com/permissions).

## <a name="access-to-functionality"></a>Toegang tot functionaliteit
De toegang tot specifieke functionaliteit wordt bepaald door uw [Azure AD-rol](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles). Neem contact op met een globale beheerder als u toegang nodig hebt tot specifieke functionaliteit waarvoor u of uw gebruikersgroep een nieuwe rol moet krijgen toegewezen.

### <a name="approve-pending-automated-tasks"></a>In behandeling zijnde geautomatiseerde taken goedkeuren
[Geautomatiseerd onderzoek en herstel](mtp-autoir-actions.md) kan actie ondernemen op e-mails, doorsturen regels, bestanden, persistentie mechanismen, en andere artefacten gevonden tijdens onderzoeken. Als u lopende acties wilt goedkeuren of weigeren waarvoor expliciete goedkeuring vereist is, moet bepaalde rollen zijn toegewezen in Microsoft 365. Zie Machtigingen voor [het onderhoudscentrum](mtp-action-center.md#required-permissions-for-action-center-tasks)voor meer informatie.

## <a name="access-to-data"></a>Toegang tot gegevens
Toegang tot Microsoft Threat Protection-gegevens kan worden beheerd met behulp van het bereik dat is toegewezen aan gebruikersgroepen in Microsoft Defender ATP-toegangsbeheer (RBAC). Als uw toegang niet is beperkt tot een specifieke set apparaten in de Microsoft Defender ATP, hebt u volledige toegang tot gegevens in Microsoft Threat Protection. Zodra uw account echter is gescoped, ziet u alleen gegevens over de apparaten in uw bereik.

Als u bijvoorbeeld tot slechts één gebruikersgroep behoort met een Microsoft Defender ATP-rol en die gebruikersgroep alleen toegang heeft gekregen tot verkoopapparaten, ziet u alleen gegevens over verkoopapparaten in Microsoft Threat Protection. [Meer informatie over RBAC-instellingen in Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a>Besturingselementen voor beveiligingsbeheer van Microsoft Cloud App
Tijdens de preview dwingt Microsoft Threat Protection geen toegangscontroles af op basis van beveiligingsinstellingen voor cloudapps. De toegang tot gegevens over bedreigingsbeveiliging van Microsoft wordt niet beïnvloed door deze instellingen.

## <a name="related-topics"></a>Verwante onderwerpen

- [Azure AD-rollen](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [Microsoft Defender ATP RBAC](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [Beveiligingsrollen voor cloudapps](https://docs.microsoft.com/cloud-app-security/manage-admins)
