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
# <a name="manage-access-to-microsoft-365-defender"></a><span data-ttu-id="c7432-104">Toegang tot Microsoft 365 Defender beheren</span><span class="sxs-lookup"><span data-stu-id="c7432-104">Manage access to Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c7432-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="c7432-105">**Applies to:**</span></span>
- <span data-ttu-id="c7432-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c7432-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="c7432-107">Accounts die zijn toegewezen aan de volgende Azure Active Directory (AD)-rollen, hebben toegang tot functionaliteit en gegevens van Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="c7432-107">Accounts assigned the following Azure Active Directory (AD) roles can access Microsoft 365 Defender functionality and data:</span></span>
- <span data-ttu-id="c7432-108">Globale beheerder</span><span class="sxs-lookup"><span data-stu-id="c7432-108">Global administrator</span></span>
- <span data-ttu-id="c7432-109">Beveiligingsbeheerder</span><span class="sxs-lookup"><span data-stu-id="c7432-109">Security administrator</span></span>
- <span data-ttu-id="c7432-110">Beveiligingsoperator</span><span class="sxs-lookup"><span data-stu-id="c7432-110">Security Operator</span></span>
- <span data-ttu-id="c7432-111">Algemene lezer</span><span class="sxs-lookup"><span data-stu-id="c7432-111">Global Reader</span></span>
- <span data-ttu-id="c7432-112">Beveiligingslezer</span><span class="sxs-lookup"><span data-stu-id="c7432-112">Security Reader</span></span>

<span data-ttu-id="c7432-113">Als u accounts met deze rollen wilt controleren, bekijkt u [machtigingen in het Microsoft 365-beveiligingscentrum.](https://security.microsoft.com/permissions)</span><span class="sxs-lookup"><span data-stu-id="c7432-113">To review accounts with these roles, [view Permissions in the Microsoft 365 security center](https://security.microsoft.com/permissions).</span></span>

## <a name="access-to-functionality"></a><span data-ttu-id="c7432-114">Toegang tot functionaliteit</span><span class="sxs-lookup"><span data-stu-id="c7432-114">Access to functionality</span></span>
<span data-ttu-id="c7432-115">Toegang tot specifieke functionaliteit wordt bepaald door uw [Azure AD-rol.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="c7432-115">Access to specific functionality is determined by your [Azure AD role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> <span data-ttu-id="c7432-116">Neem contact op met een globale beheerder als u toegang nodig hebt tot specifieke functionaliteit die vereist dat aan u of uw gebruikersgroep een nieuwe rol wordt toegewezen.</span><span class="sxs-lookup"><span data-stu-id="c7432-116">Contact a global administrator if you need access to specific functionality that requires you or your user group be assigned a new role.</span></span>

### <a name="approve-pending-automated-tasks"></a><span data-ttu-id="c7432-117">Geautomatiseerde taken in behandeling goedkeuren</span><span class="sxs-lookup"><span data-stu-id="c7432-117">Approve pending automated tasks</span></span>
<span data-ttu-id="c7432-118">[Automatisch onderzoek en herstel kunnen acties](mtp-autoir-actions.md) ondernemen op e-mailberichten, doorsturenregels, bestanden, persistentiemechanismen en andere artefacten die tijdens onderzoeken zijn gevonden.</span><span class="sxs-lookup"><span data-stu-id="c7432-118">[Automated investigation and remediation](mtp-autoir-actions.md) can take action on emails, forwarding rules, files, persistence mechanisms, and other artifacts found during investigations.</span></span> <span data-ttu-id="c7432-119">Als u acties in behandeling die expliciet moeten worden goedgekeurd, wilt goedkeuren of weigeren, moet u bepaalde rollen hebben toegewezen in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c7432-119">To approve or reject pending actions that require explicit approval, you must have certain roles assigned in Microsoft 365.</span></span> <span data-ttu-id="c7432-120">Zie machtigingen van [het Actiecentrum voor meer informatie.](mtp-action-center.md#required-permissions-for-action-center-tasks)</span><span class="sxs-lookup"><span data-stu-id="c7432-120">To learn more, see [Action center permissions](mtp-action-center.md#required-permissions-for-action-center-tasks).</span></span>

## <a name="access-to-data"></a><span data-ttu-id="c7432-121">Toegang tot gegevens</span><span class="sxs-lookup"><span data-stu-id="c7432-121">Access to data</span></span>
<span data-ttu-id="c7432-122">Toegang tot Gegevens van Microsoft 365 Defender kan worden beheerd met behulp van het bereik dat is toegewezen aan gebruikersgroepen in toegangsbeheer op basis van een Eindpunt-rol in Microsoft Defender for Endpoint (RBAC).</span><span class="sxs-lookup"><span data-stu-id="c7432-122">Access to Microsoft 365 Defender data can be controlled using the scope assigned to user groups in Microsoft Defender for Endpoint role-based access control (RBAC).</span></span> <span data-ttu-id="c7432-123">Als uw toegang niet beperkt is tot een specifieke set apparaten in Defender for Endpoint, hebt u volledige toegang tot gegevens in Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="c7432-123">If your access has not been scoped to a specific set of devices in the Defender for Endpoint, you will have full access to data in Microsoft 365 Defender.</span></span> <span data-ttu-id="c7432-124">Zodra uw account echter beperkt is, ziet u alleen gegevens over de apparaten binnen uw bereik.</span><span class="sxs-lookup"><span data-stu-id="c7432-124">However, once your account is scoped, you will only see data about the devices in your scope.</span></span>

<span data-ttu-id="c7432-125">Als u bijvoorbeeld tot slechts één gebruikersgroep behoort met de rol Microsoft Defender voor eindpunt en die gebruikersgroep alleen toegang heeft gekregen tot verkoopapparaten, ziet u alleen gegevens over verkoopapparaten in Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="c7432-125">For example, if you belong to only one user group with a Microsoft Defender for Endpoint role and that user group has been given access to sales devices only, you will see only data about sales devices in Microsoft 365 Defender.</span></span> [<span data-ttu-id="c7432-126">Meer informatie over RBAC-instellingen in Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="c7432-126">Learn more about RBAC settings in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a><span data-ttu-id="c7432-127">Toegangsbesturingselementen voor Microsoft Cloud App-beveiliging</span><span class="sxs-lookup"><span data-stu-id="c7432-127">Microsoft Cloud App Security access controls</span></span>
<span data-ttu-id="c7432-128">Tijdens de preview-versie dwingt Microsoft 365 Defender geen toegangsbesturingselementen af op basis van beveiligingsinstellingen voor cloud-apps.</span><span class="sxs-lookup"><span data-stu-id="c7432-128">During the preview, Microsoft 365 Defender does not enforce access controls based on  Cloud App Security settings.</span></span> <span data-ttu-id="c7432-129">Toegang tot Microsoft 365 Defender-gegevens wordt niet beïnvloed door deze instellingen.</span><span class="sxs-lookup"><span data-stu-id="c7432-129">Access to Microsoft 365 Defender data is not affected by these settings.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c7432-130">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="c7432-130">Related topics</span></span>

- [<span data-ttu-id="c7432-131">Azure AD-rollen</span><span class="sxs-lookup"><span data-stu-id="c7432-131">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [<span data-ttu-id="c7432-132">Microsoft Defender for Endpoint RBAC</span><span class="sxs-lookup"><span data-stu-id="c7432-132">Microsoft Defender for Endpoint RBAC</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [<span data-ttu-id="c7432-133">Rollen voor beveiliging in cloud-apps</span><span class="sxs-lookup"><span data-stu-id="c7432-133">Cloud App Security roles</span></span>](https://docs.microsoft.com/cloud-app-security/manage-admins)
