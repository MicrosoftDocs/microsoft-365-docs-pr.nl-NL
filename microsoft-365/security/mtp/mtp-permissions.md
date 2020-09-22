---
title: Toegang tot Microsoft Threat Protection-gegevens beheren in het Microsoft 365-Beveiligingscentrum
description: Meer informatie over het beheren van machtigingen voor gegevens in Microsoft Threat Protection
keywords: Access, machtigingen, MTP, Microsoft Threat Protection, M365, beveiliging, MCAS, MDATP, Cloud app Security, Microsoft Defender Advanced Threat Protection, Scope, Scope, RBAC
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
ms.openlocfilehash: 96a8694f5cbc7c27d27acbd5ec0aabe8712c6f06
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201073"
---
# <a name="manage-access-to-microsoft-threat-protection"></a>Toegang tot Microsoft Threat Protection beheren

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft Threat Protection

Accounts die zijn toegewezen aan de volgende Azure Active Directory (AD) rollen hebben toegang tot de functies en gegevens van Microsoft Threat Protection.
- Globale beheerder
- Beveiligingsbeheerder
- Beveiligings operator
- Algemene lezer
- Beveiligings lezer

Als u accounts met deze rollen wilt bekijken, [raadpleegt u machtigingen in het Microsoft 365-Beveiligingscentrum](https://security.microsoft.com/permissions).

## <a name="access-to-functionality"></a>Toegang tot functionaliteit
Toegang tot specifieke functionaliteit wordt bepaald door uw [functie van Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles). Neem contact op met een globale beheerder als u toegang hebt tot specifieke functionaliteit waarvoor u of uw gebruikersgroep een nieuwe rol moet krijgen.

### <a name="approve-pending-automated-tasks"></a>Openstaande geautomatiseerde taken goedkeuren
[Automatisch onderzoek en herstel](mtp-autoir-actions.md) kunnen actie ondernemen voor e-mailberichten, doorstuurregels, bestanden, permanente mechanismen en andere artefacten die zich tijdens het onderzoek bevinden. Als u acties wilt goedkeuren of weigeren die expliciet moeten worden goedgekeurd, moet u bepaalde rollen hebben toegewezen in Microsoft 365. Zie machtigingen voor het [Actiecentrum](mtp-action-center.md#required-permissions-for-action-center-tasks)voor meer informatie.

## <a name="access-to-data"></a>Toegang tot gegevens
De toegang tot Microsoft Threat Protection-gegevens kan worden beheerd met behulp van het bereik dat is toegewezen aan gebruikersgroepen in Microsoft Defender ATP op rollen gebaseerd toegangsbeheer. Als uw toegang niet is beperkt tot een bepaalde set apparaten in Microsoft Defender ATP, krijgt u volledige toegang tot gegevens in Microsoft Threat Protection. Wanneer uw account is beperkt tot uw account, worden er alleen gegevens weergegeven over de apparaten in uw bereik.

Als u bijvoorbeeld lid bent van slechts één gebruikersgroep met een Microsoft Defender ATP-rol en die gebruikersgroep toegang heeft verleend tot verkoop apparaten, ziet u alleen gegevens over verkoop apparaten in Microsoft Threat Protection. [Meer informatie over de instellingen voor de RBAC in Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a>Toegangsbeheer voor Microsoft Cloud-app
In het voorbeeld worden in Microsoft Threat Protection geen toegangsbeheer afgedwongen op basis van beveiligingsinstellingen voor Cloud apps. De toegang tot Microsoft Threat Protection-gegevens wordt niet beïnvloed door deze instellingen.

## <a name="related-topics"></a>Verwante onderwerpen

- [Azure AD-rollen](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [Microsoft Defender ATP RBAC](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [Beveiligingsrollen voor Cloud apps](https://docs.microsoft.com/cloud-app-security/manage-admins)
