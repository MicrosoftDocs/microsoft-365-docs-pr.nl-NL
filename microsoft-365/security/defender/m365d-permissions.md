---
title: Toegang tot gegevens Microsoft 365 Defender beheren in het Microsoft 365 beveiligingscentrum
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
ms.openlocfilehash: 52e4e9fc8c73d1adca0c24c5bebb50f9dcf7ac6f
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935627"
---
# <a name="manage-access-to-microsoft-365-defender-with-azure-active-directory-global-roles"></a><span data-ttu-id="fcaa4-104">Toegang tot Microsoft 365 Defender beheren met Azure Active Directory globale rollen</span><span class="sxs-lookup"><span data-stu-id="fcaa4-104">Manage access to Microsoft 365 Defender with Azure Active Directory global roles</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="fcaa4-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="fcaa4-105">**Applies to:**</span></span>
- <span data-ttu-id="fcaa4-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fcaa4-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="fcaa4-107">Er zijn twee manieren om toegang tot een Defender Microsoft 365 beheren</span><span class="sxs-lookup"><span data-stu-id="fcaa4-107">There are two ways to manage access to Microsoft 365 Defender</span></span>
- <span data-ttu-id="fcaa4-108">**Hoofdrollen Azure Active Directory (AD)**</span><span class="sxs-lookup"><span data-stu-id="fcaa4-108">**Global Azure Active Directory (AD) roles**</span></span>
- <span data-ttu-id="fcaa4-109">**Aangepaste roltoegang**</span><span class="sxs-lookup"><span data-stu-id="fcaa4-109">**Custom role access**</span></span>

<span data-ttu-id="fcaa4-110">Accounts die aan de volgende **globale Azure Active Directory (AD)** zijn toegewezen, hebben toegang tot Microsoft 365 defender-functionaliteit en -gegevens:</span><span class="sxs-lookup"><span data-stu-id="fcaa4-110">Accounts assigned the following **Global Azure Active Directory (AD) roles** can access Microsoft 365 Defender functionality and data:</span></span>
- <span data-ttu-id="fcaa4-111">Globale beheerder</span><span class="sxs-lookup"><span data-stu-id="fcaa4-111">Global administrator</span></span>
- <span data-ttu-id="fcaa4-112">Beveiligingsbeheerder</span><span class="sxs-lookup"><span data-stu-id="fcaa4-112">Security administrator</span></span>
- <span data-ttu-id="fcaa4-113">Beveiligingsoperator</span><span class="sxs-lookup"><span data-stu-id="fcaa4-113">Security Operator</span></span>
- <span data-ttu-id="fcaa4-114">Algemene lezer</span><span class="sxs-lookup"><span data-stu-id="fcaa4-114">Global Reader</span></span>
- <span data-ttu-id="fcaa4-115">Beveiligingslezer</span><span class="sxs-lookup"><span data-stu-id="fcaa4-115">Security Reader</span></span>

<span data-ttu-id="fcaa4-116">Als u accounts met deze rollen wilt controleren, [bekijkt u Machtigingen in het Microsoft 365 beveiligingscentrum.](https://security.microsoft.com/permissions)</span><span class="sxs-lookup"><span data-stu-id="fcaa4-116">To review accounts with these roles, [view Permissions in the Microsoft 365 security center](https://security.microsoft.com/permissions).</span></span>

<span data-ttu-id="fcaa4-117">**Aangepaste roltoegang** is een nieuwe mogelijkheid in Microsoft 365 Defender en stelt u in staat om de toegang tot specifieke gegevens, taken en mogelijkheden in Microsoft Defender 365 te beheren.</span><span class="sxs-lookup"><span data-stu-id="fcaa4-117">**Custom role** access is a new capability in Microsoft 365 Defender and allows you to manage access to specific data, tasks, and capabilities in Microsoft Defender 365.</span></span> <span data-ttu-id="fcaa4-118">Aangepaste rollen bieden meer controle dan globale Azure AD-rollen, zodat gebruikers alleen de benodigde toegang hebben met de minst permissieve rollen die nodig zijn.</span><span class="sxs-lookup"><span data-stu-id="fcaa4-118">Custom roles offer more control than global Azure AD roles, providing users only the access they need with the least-permissive roles necessary.</span></span>  <span data-ttu-id="fcaa4-119">Aangepaste rollen kunnen worden gemaakt naast globale Azure AD-rollen.</span><span class="sxs-lookup"><span data-stu-id="fcaa4-119">Custom roles can be created in addition to global Azure AD roles.</span></span> <span data-ttu-id="fcaa4-120">[Meer informatie over aangepaste rollen.](custom-roles.md)</span><span class="sxs-lookup"><span data-stu-id="fcaa4-120">[Learn more about custom roles](custom-roles.md).</span></span>

> <span data-ttu-id="fcaa4-121">! [OPMERKING] Dit artikel is alleen van toepassing op het beheren van globale Azure Active Directory rollen.</span><span class="sxs-lookup"><span data-stu-id="fcaa4-121">![NOTE] This article applies only to managing global Azure Active Directory roles.</span></span> <span data-ttu-id="fcaa4-122">Zie Aangepaste rollen voor toegangsbeheer op basis van rollen voor meer informatie over het gebruik van aangepaste toegangsbeheer op basis [van rollen](custom-roles.md)</span><span class="sxs-lookup"><span data-stu-id="fcaa4-122">For more information about using custom role-based access control, see [Custom roles for role-based access control](custom-roles.md)</span></span>

## <a name="access-to-functionality"></a><span data-ttu-id="fcaa4-123">Toegang tot functionaliteit</span><span class="sxs-lookup"><span data-stu-id="fcaa4-123">Access to functionality</span></span>
<span data-ttu-id="fcaa4-124">Toegang tot specifieke functionaliteit wordt bepaald door uw [Azure AD-rol.](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="fcaa4-124">Access to specific functionality is determined by your [Azure AD role](/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> <span data-ttu-id="fcaa4-125">Neem contact op met een globale beheerder als u toegang nodig hebt tot specifieke functionaliteit die vereist dat u of uw gebruikersgroep een nieuwe rol krijgt toegewezen.</span><span class="sxs-lookup"><span data-stu-id="fcaa4-125">Contact a global administrator if you need access to specific functionality that requires you or your user group be assigned a new role.</span></span>

### <a name="approve-pending-automated-tasks"></a><span data-ttu-id="fcaa4-126">In behandeling zijnde geautomatiseerde taken goedkeuren</span><span class="sxs-lookup"><span data-stu-id="fcaa4-126">Approve pending automated tasks</span></span>
<span data-ttu-id="fcaa4-127">[Geautomatiseerde onderzoeken en herstel](m365d-autoir-actions.md) kunnen actie ondernemen op basis van e-mailberichten, regels voor doorsturen, bestanden, persistentiemechanismen en andere artefacten die tijdens onderzoeken zijn gevonden.</span><span class="sxs-lookup"><span data-stu-id="fcaa4-127">[Automated investigation and remediation](m365d-autoir-actions.md) can take action on emails, forwarding rules, files, persistence mechanisms, and other artifacts found during investigations.</span></span> <span data-ttu-id="fcaa4-128">Als u in behandeling zijnde acties wilt goedkeuren of afwijzen waarvoor expliciete goedkeuring is vereist, moet u bepaalde rollen hebben toegewezen in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fcaa4-128">To approve or reject pending actions that require explicit approval, you must have certain roles assigned in Microsoft 365.</span></span> <span data-ttu-id="fcaa4-129">Zie Machtigingen voor [actiecentrum voor meer informatie.](m365d-action-center.md#required-permissions-for-action-center-tasks)</span><span class="sxs-lookup"><span data-stu-id="fcaa4-129">To learn more, see [Action center permissions](m365d-action-center.md#required-permissions-for-action-center-tasks).</span></span>

## <a name="access-to-data"></a><span data-ttu-id="fcaa4-130">Toegang tot gegevens</span><span class="sxs-lookup"><span data-stu-id="fcaa4-130">Access to data</span></span>
<span data-ttu-id="fcaa4-131">Toegang tot Microsoft 365 Defender-gegevens kan worden bepaald met behulp van het bereik dat is toegewezen aan gebruikersgroepen in Microsoft Defender for Endpoint role-based access control (RBAC).</span><span class="sxs-lookup"><span data-stu-id="fcaa4-131">Access to Microsoft 365 Defender data can be controlled using the scope assigned to user groups in Microsoft Defender for Endpoint role-based access control (RBAC).</span></span> <span data-ttu-id="fcaa4-132">Als uw toegang niet is beperkt tot een bepaalde set apparaten in het Defender voor Eindpunt, hebt u volledige toegang tot gegevens in Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="fcaa4-132">If your access has not been scoped to a specific set of devices in the Defender for Endpoint, you will have full access to data in Microsoft 365 Defender.</span></span> <span data-ttu-id="fcaa4-133">Wanneer uw account echter een bereik heeft, ziet u alleen gegevens over de apparaten in uw bereik.</span><span class="sxs-lookup"><span data-stu-id="fcaa4-133">However, once your account is scoped, you will only see data about the devices in your scope.</span></span>

<span data-ttu-id="fcaa4-134">Als u bijvoorbeeld tot slechts één gebruikersgroep behoort met een Microsoft Defender voor eindpuntrol en die gebruikersgroep alleen toegang heeft gekregen tot verkoopapparaten, ziet u alleen gegevens over verkoopapparaten in Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="fcaa4-134">For example, if you belong to only one user group with a Microsoft Defender for Endpoint role and that user group has been given access to sales devices only, you will see only data about sales devices in Microsoft 365 Defender.</span></span> [<span data-ttu-id="fcaa4-135">Meer informatie over RBAC-instellingen in Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="fcaa4-135">Learn more about RBAC settings in Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a><span data-ttu-id="fcaa4-136">Microsoft Cloud App Security toegangsbesturingselementen</span><span class="sxs-lookup"><span data-stu-id="fcaa4-136">Microsoft Cloud App Security access controls</span></span>
<span data-ttu-id="fcaa4-137">Tijdens het preview-Microsoft 365 Defender geen toegangsbesturingselementen afdwingen op basis van Cloud App Security instellingen.</span><span class="sxs-lookup"><span data-stu-id="fcaa4-137">During the preview, Microsoft 365 Defender does not enforce access controls based on  Cloud App Security settings.</span></span> <span data-ttu-id="fcaa4-138">Toegang tot Microsoft 365 Defender-gegevens wordt niet beïnvloed door deze instellingen.</span><span class="sxs-lookup"><span data-stu-id="fcaa4-138">Access to Microsoft 365 Defender data is not affected by these settings.</span></span>

## <a name="related-topics"></a><span data-ttu-id="fcaa4-139">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="fcaa4-139">Related topics</span></span>
- [<span data-ttu-id="fcaa4-140">Aangepaste rollen in op rollen gebaseerd toegangsbeheer voor Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fcaa4-140">Custom roles in role-based access control for Microsoft 365 Defender</span></span>](custom-roles.md)
- [<span data-ttu-id="fcaa4-141">Azure AD-rollen</span><span class="sxs-lookup"><span data-stu-id="fcaa4-141">Azure AD roles</span></span>](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [<span data-ttu-id="fcaa4-142">Microsoft Defender voor Endpoint RBAC</span><span class="sxs-lookup"><span data-stu-id="fcaa4-142">Microsoft Defender for Endpoint RBAC</span></span>](/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [<span data-ttu-id="fcaa4-143">Cloud App Security rollen</span><span class="sxs-lookup"><span data-stu-id="fcaa4-143">Cloud App Security roles</span></span>](/cloud-app-security/manage-admins)