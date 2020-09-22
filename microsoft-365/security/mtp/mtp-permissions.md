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
# <a name="manage-access-to-microsoft-threat-protection"></a><span data-ttu-id="76f9d-104">Toegang tot Microsoft Threat Protection beheren</span><span class="sxs-lookup"><span data-stu-id="76f9d-104">Manage access to Microsoft Threat Protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="76f9d-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="76f9d-105">**Applies to:**</span></span>
- <span data-ttu-id="76f9d-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="76f9d-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="76f9d-107">Accounts die zijn toegewezen aan de volgende Azure Active Directory (AD) rollen hebben toegang tot de functies en gegevens van Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="76f9d-107">Accounts assigned the following Azure Active Directory (AD) roles can access Microsoft Threat Protection functionality and data:</span></span>
- <span data-ttu-id="76f9d-108">Globale beheerder</span><span class="sxs-lookup"><span data-stu-id="76f9d-108">Global administrator</span></span>
- <span data-ttu-id="76f9d-109">Beveiligingsbeheerder</span><span class="sxs-lookup"><span data-stu-id="76f9d-109">Security administrator</span></span>
- <span data-ttu-id="76f9d-110">Beveiligings operator</span><span class="sxs-lookup"><span data-stu-id="76f9d-110">Security Operator</span></span>
- <span data-ttu-id="76f9d-111">Algemene lezer</span><span class="sxs-lookup"><span data-stu-id="76f9d-111">Global Reader</span></span>
- <span data-ttu-id="76f9d-112">Beveiligings lezer</span><span class="sxs-lookup"><span data-stu-id="76f9d-112">Security Reader</span></span>

<span data-ttu-id="76f9d-113">Als u accounts met deze rollen wilt bekijken, [raadpleegt u machtigingen in het Microsoft 365-Beveiligingscentrum](https://security.microsoft.com/permissions).</span><span class="sxs-lookup"><span data-stu-id="76f9d-113">To review accounts with these roles, [view Permissions in the Microsoft 365 security center](https://security.microsoft.com/permissions).</span></span>

## <a name="access-to-functionality"></a><span data-ttu-id="76f9d-114">Toegang tot functionaliteit</span><span class="sxs-lookup"><span data-stu-id="76f9d-114">Access to functionality</span></span>
<span data-ttu-id="76f9d-115">Toegang tot specifieke functionaliteit wordt bepaald door uw [functie van Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="76f9d-115">Access to specific functionality is determined by your [Azure AD role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> <span data-ttu-id="76f9d-116">Neem contact op met een globale beheerder als u toegang hebt tot specifieke functionaliteit waarvoor u of uw gebruikersgroep een nieuwe rol moet krijgen.</span><span class="sxs-lookup"><span data-stu-id="76f9d-116">Contact a global administrator if you need access to specific functionality that requires you or your user group be assigned a new role.</span></span>

### <a name="approve-pending-automated-tasks"></a><span data-ttu-id="76f9d-117">Openstaande geautomatiseerde taken goedkeuren</span><span class="sxs-lookup"><span data-stu-id="76f9d-117">Approve pending automated tasks</span></span>
<span data-ttu-id="76f9d-118">[Automatisch onderzoek en herstel](mtp-autoir-actions.md) kunnen actie ondernemen voor e-mailberichten, doorstuurregels, bestanden, permanente mechanismen en andere artefacten die zich tijdens het onderzoek bevinden.</span><span class="sxs-lookup"><span data-stu-id="76f9d-118">[Automated investigation and remediation](mtp-autoir-actions.md) can take action on emails, forwarding rules, files, persistence mechanisms, and other artifacts found during investigations.</span></span> <span data-ttu-id="76f9d-119">Als u acties wilt goedkeuren of weigeren die expliciet moeten worden goedgekeurd, moet u bepaalde rollen hebben toegewezen in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="76f9d-119">To approve or reject pending actions that require explicit approval, you must have certain roles assigned in Microsoft 365.</span></span> <span data-ttu-id="76f9d-120">Zie machtigingen voor het [Actiecentrum](mtp-action-center.md#required-permissions-for-action-center-tasks)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="76f9d-120">To learn more, see [Action center permissions](mtp-action-center.md#required-permissions-for-action-center-tasks).</span></span>

## <a name="access-to-data"></a><span data-ttu-id="76f9d-121">Toegang tot gegevens</span><span class="sxs-lookup"><span data-stu-id="76f9d-121">Access to data</span></span>
<span data-ttu-id="76f9d-122">De toegang tot Microsoft Threat Protection-gegevens kan worden beheerd met behulp van het bereik dat is toegewezen aan gebruikersgroepen in Microsoft Defender ATP op rollen gebaseerd toegangsbeheer.</span><span class="sxs-lookup"><span data-stu-id="76f9d-122">Access to Microsoft Threat Protection data can be controlled using the scope assigned to user groups in Microsoft Defender ATP role-based access control (RBAC).</span></span> <span data-ttu-id="76f9d-123">Als uw toegang niet is beperkt tot een bepaalde set apparaten in Microsoft Defender ATP, krijgt u volledige toegang tot gegevens in Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="76f9d-123">If your access has not been scoped to a specific set of devices in the Microsoft Defender ATP, you will have full access to data in Microsoft Threat Protection.</span></span> <span data-ttu-id="76f9d-124">Wanneer uw account is beperkt tot uw account, worden er alleen gegevens weergegeven over de apparaten in uw bereik.</span><span class="sxs-lookup"><span data-stu-id="76f9d-124">However, once your account is scoped, you will only see data about the devices in your scope.</span></span>

<span data-ttu-id="76f9d-125">Als u bijvoorbeeld lid bent van slechts één gebruikersgroep met een Microsoft Defender ATP-rol en die gebruikersgroep toegang heeft verleend tot verkoop apparaten, ziet u alleen gegevens over verkoop apparaten in Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="76f9d-125">For example, if you belong to only one user group with a Microsoft Defender ATP role and that user group has been given access to sales devices only, you will see only data about sales devices in Microsoft Threat Protection.</span></span> [<span data-ttu-id="76f9d-126">Meer informatie over de instellingen voor de RBAC in Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="76f9d-126">Learn more about RBAC settings in Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a><span data-ttu-id="76f9d-127">Toegangsbeheer voor Microsoft Cloud-app</span><span class="sxs-lookup"><span data-stu-id="76f9d-127">Microsoft Cloud App Security access controls</span></span>
<span data-ttu-id="76f9d-128">In het voorbeeld worden in Microsoft Threat Protection geen toegangsbeheer afgedwongen op basis van beveiligingsinstellingen voor Cloud apps.</span><span class="sxs-lookup"><span data-stu-id="76f9d-128">During the preview, Microsoft Threat Protection does not enforce access controls based on  Cloud App Security settings.</span></span> <span data-ttu-id="76f9d-129">De toegang tot Microsoft Threat Protection-gegevens wordt niet beïnvloed door deze instellingen.</span><span class="sxs-lookup"><span data-stu-id="76f9d-129">Access to Microsoft Threat Protection data is not affected by these settings.</span></span>

## <a name="related-topics"></a><span data-ttu-id="76f9d-130">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="76f9d-130">Related topics</span></span>

- [<span data-ttu-id="76f9d-131">Azure AD-rollen</span><span class="sxs-lookup"><span data-stu-id="76f9d-131">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [<span data-ttu-id="76f9d-132">Microsoft Defender ATP RBAC</span><span class="sxs-lookup"><span data-stu-id="76f9d-132">Microsoft Defender ATP RBAC</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [<span data-ttu-id="76f9d-133">Beveiligingsrollen voor Cloud apps</span><span class="sxs-lookup"><span data-stu-id="76f9d-133">Cloud App Security roles</span></span>](https://docs.microsoft.com/cloud-app-security/manage-admins)
