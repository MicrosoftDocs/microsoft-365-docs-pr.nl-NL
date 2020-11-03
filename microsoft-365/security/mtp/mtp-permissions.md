---
title: Toegang tot Microsoft 365 Defender-gegevens beheren in het Microsoft 365 Beveiligingscentrum
description: Meer informatie over het beheren van machtigingen voor gegevens in Microsoft 365 Defender
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
ms.openlocfilehash: 55b7b8c5755b773a4d53c95017a0a17a85495dee
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847246"
---
# <a name="manage-access-to-microsoft-365-defender"></a>Toegang tot Microsoft 365 Defender beheren

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

Accounts die zijn toegewezen aan de volgende Azure Active Directory (AD) rollen, hebben toegang tot de functies en gegevens van Microsoft 365 Defender:
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
Toegang tot gegevens van Microsoft 365 Defender kan worden beheerd met behulp van het bereik dat is toegewezen aan gebruikersgroepen in Microsoft Defender voor op rollen gebaseerd toegangsbeheer op basis van rollen (RBAC). Als uw toegang niet is beperkt tot een specifieke set apparaten in het eindpunt voor eindpunten, hebt u volledige toegang tot gegevens in Microsoft 365 Defender. Wanneer uw account is beperkt tot uw account, worden er alleen gegevens weergegeven over de apparaten in uw bereik.

Als u bijvoorbeeld lid bent van slechts één gebruikersgroep met een functie van Microsoft Defender voor eindpunt en die gebruikersgroep toegang heeft verleend tot verkoop apparaten, ziet u alleen gegevens over verkoop apparaten in Microsoft 365. [Meer informatie over de instellingen voor de RBAC in Microsoft Defender voor eindpunt](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a>Toegangsbeheer voor Microsoft Cloud-app
In de preview-versie van Microsoft 365 Defender worden geen toegangsbeheer afgedwongen op basis van beveiligingsinstellingen voor Cloud apps. Deze instellingen zijn niet van invloed op de toegang tot Microsoft 365 Defender-gegevens.

## <a name="related-topics"></a>Verwante onderwerpen

- [Azure AD-rollen](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [Microsoft Defender voor eindpunten RBAC](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [Beveiligingsrollen voor Cloud apps](https://docs.microsoft.com/cloud-app-security/manage-admins)
