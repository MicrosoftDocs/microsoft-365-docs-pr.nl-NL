---
title: Toegang tot Microsoft 365 Defender-gegevens beheren in het Microsoft 365-beveiligingscentrum
description: Informatie over het beheren van machtigingen voor gegevens in Microsoft 365 Defender
keywords: toegang, machtigingen, MTP, Microsoft Threat Protection, M365, beveiliging, MCAS, MDATP, Cloud App Security, Microsoft Defender Advanced Threat Protection, bereik, scoping, RBAC
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 6f042b0c6314e8e5f80d40d76159712bc817a01c
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930136"
---
# <a name="manage-access-to-microsoft-365-defender"></a>Toegang tot Microsoft 365 Defender beheren

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

Accounts die zijn toegewezen aan de volgende Azure Active Directory (AD)-rollen, hebben toegang tot functionaliteit en gegevens van Microsoft 365 Defender:
- Globale beheerder
- Beveiligingsbeheerder
- Beveiligingsoperator
- Algemene lezer
- Beveiligingslezer

Als u accounts met deze rollen wilt controleren, bekijkt u [machtigingen in het Microsoft 365-beveiligingscentrum.](https://security.microsoft.com/permissions)

## <a name="access-to-functionality"></a>Toegang tot functionaliteit
Toegang tot specifieke functionaliteit wordt bepaald door uw [Azure AD-rol.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) Neem contact op met een globale beheerder als u toegang nodig hebt tot specifieke functionaliteit die vereist dat aan u of uw gebruikersgroep een nieuwe rol wordt toegewezen.

### <a name="approve-pending-automated-tasks"></a>Geautomatiseerde taken in behandeling goedkeuren
[Automatisch onderzoek en herstel kunnen acties](mtp-autoir-actions.md) ondernemen op e-mailberichten, doorsturenregels, bestanden, persistentiemechanismen en andere artefacten die tijdens onderzoeken zijn gevonden. Als u acties in behandeling die expliciet moeten worden goedgekeurd, wilt goedkeuren of weigeren, moet u bepaalde rollen hebben toegewezen in Microsoft 365. Zie machtigingen van [het Actiecentrum voor meer informatie.](mtp-action-center.md#required-permissions-for-action-center-tasks)

## <a name="access-to-data"></a>Toegang tot gegevens
Toegang tot Gegevens van Microsoft 365 Defender kan worden beheerd met behulp van het bereik dat is toegewezen aan gebruikersgroepen in toegangsbeheer op basis van een Eindpunt-rol in Microsoft Defender for Endpoint (RBAC). Als uw toegang niet beperkt is tot een specifieke set apparaten in Defender for Endpoint, hebt u volledige toegang tot gegevens in Microsoft 365 Defender. Zodra uw account echter beperkt is, ziet u alleen gegevens over de apparaten binnen uw bereik.

Als u bijvoorbeeld tot slechts één gebruikersgroep behoort met de rol Microsoft Defender voor eindpunt en die gebruikersgroep alleen toegang heeft gekregen tot verkoopapparaten, ziet u alleen gegevens over verkoopapparaten in Microsoft 365 Defender. [Meer informatie over RBAC-instellingen in Microsoft Defender voor Eindpunt](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a>Toegangsbesturingselementen voor Microsoft Cloud App-beveiliging
Tijdens de preview-versie dwingt Microsoft 365 Defender geen toegangsbesturingselementen af op basis van beveiligingsinstellingen voor cloud-apps. Toegang tot Microsoft 365 Defender-gegevens wordt niet beïnvloed door deze instellingen.

## <a name="related-topics"></a>Verwante onderwerpen

- [Azure AD-rollen](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [Microsoft Defender for Endpoint RBAC](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [Rollen voor beveiliging in cloud-apps](https://docs.microsoft.com/cloud-app-security/manage-admins)
