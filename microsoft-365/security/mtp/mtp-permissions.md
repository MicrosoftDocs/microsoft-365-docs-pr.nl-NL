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
# <a name="manage-access-to-microsoft-threat-protection"></a><span data-ttu-id="cfa22-104">Toegang tot Microsoft Threat Protection beheren</span><span class="sxs-lookup"><span data-stu-id="cfa22-104">Manage access to Microsoft Threat Protection</span></span>

<span data-ttu-id="cfa22-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="cfa22-105">**Applies to:**</span></span>
- <span data-ttu-id="cfa22-106">Microsoft-bedreigingsbeveiliging</span><span class="sxs-lookup"><span data-stu-id="cfa22-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="cfa22-107">Accounts die de volgende AD-rollen (Azure Directory) hebben toegewezen, hebben toegang tot de functionaliteit en gegevens van Microsoft Threat Protection:</span><span class="sxs-lookup"><span data-stu-id="cfa22-107">Accounts assigned the following Azure Active Directory (AD) roles can access Microsoft Threat Protection functionality and data:</span></span>
- <span data-ttu-id="cfa22-108">Globale beheerder</span><span class="sxs-lookup"><span data-stu-id="cfa22-108">Global administrator</span></span>
- <span data-ttu-id="cfa22-109">Beveiligingsbeheerder</span><span class="sxs-lookup"><span data-stu-id="cfa22-109">Security administrator</span></span>
- <span data-ttu-id="cfa22-110">Beveiligingsoperator</span><span class="sxs-lookup"><span data-stu-id="cfa22-110">Security Operator</span></span>
- <span data-ttu-id="cfa22-111">Globale lezer</span><span class="sxs-lookup"><span data-stu-id="cfa22-111">Global Reader</span></span>
- <span data-ttu-id="cfa22-112">Beveiligingslezer</span><span class="sxs-lookup"><span data-stu-id="cfa22-112">Security Reader</span></span>

<span data-ttu-id="cfa22-113">Als u accounts met deze rollen wilt bekijken, [bekijkt u Machtigingen in het Microsoft 365-beveiligingscentrum](https://security.microsoft.com/permissions).</span><span class="sxs-lookup"><span data-stu-id="cfa22-113">To review accounts with these roles, [view Permissions in the Microsoft 365 security center](https://security.microsoft.com/permissions).</span></span>

## <a name="access-to-functionality"></a><span data-ttu-id="cfa22-114">Toegang tot functionaliteit</span><span class="sxs-lookup"><span data-stu-id="cfa22-114">Access to functionality</span></span>
<span data-ttu-id="cfa22-115">De toegang tot specifieke functionaliteit wordt bepaald door uw [Azure AD-rol](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="cfa22-115">Access to specific functionality is determined by your [Azure AD role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> <span data-ttu-id="cfa22-116">Neem contact op met een globale beheerder als u toegang nodig hebt tot specifieke functionaliteit waarvoor u of uw gebruikersgroep een nieuwe rol moet krijgen toegewezen.</span><span class="sxs-lookup"><span data-stu-id="cfa22-116">Contact a global administrator if you need access to specific functionality that requires you or your user group be assigned a new role.</span></span>

### <a name="approve-pending-automated-tasks"></a><span data-ttu-id="cfa22-117">In behandeling zijnde geautomatiseerde taken goedkeuren</span><span class="sxs-lookup"><span data-stu-id="cfa22-117">Approve pending automated tasks</span></span>
<span data-ttu-id="cfa22-118">[Geautomatiseerd onderzoek en herstel](mtp-autoir-actions.md) kan actie ondernemen op e-mails, doorsturen regels, bestanden, persistentie mechanismen, en andere artefacten gevonden tijdens onderzoeken.</span><span class="sxs-lookup"><span data-stu-id="cfa22-118">[Automated investigation and remediation](mtp-autoir-actions.md) can take action on emails, forwarding rules, files, persistence mechanisms, and other artifacts found during investigations.</span></span> <span data-ttu-id="cfa22-119">Als u lopende acties wilt goedkeuren of weigeren waarvoor expliciete goedkeuring vereist is, moet bepaalde rollen zijn toegewezen in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cfa22-119">To approve or reject pending actions that require explicit approval, you must have certain roles assigned in Microsoft 365.</span></span> <span data-ttu-id="cfa22-120">Zie Machtigingen voor [het onderhoudscentrum](mtp-action-center.md#required-permissions-for-action-center-tasks)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="cfa22-120">To learn more, see [Action center permissions](mtp-action-center.md#required-permissions-for-action-center-tasks).</span></span>

## <a name="access-to-data"></a><span data-ttu-id="cfa22-121">Toegang tot gegevens</span><span class="sxs-lookup"><span data-stu-id="cfa22-121">Access to data</span></span>
<span data-ttu-id="cfa22-122">Toegang tot Microsoft Threat Protection-gegevens kan worden beheerd met behulp van het bereik dat is toegewezen aan gebruikersgroepen in Microsoft Defender ATP-toegangsbeheer (RBAC).</span><span class="sxs-lookup"><span data-stu-id="cfa22-122">Access to Microsoft Threat Protection data can be controlled using the scope assigned to user groups in Microsoft Defender ATP role-based access control (RBAC).</span></span> <span data-ttu-id="cfa22-123">Als uw toegang niet is beperkt tot een specifieke set apparaten in de Microsoft Defender ATP, hebt u volledige toegang tot gegevens in Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="cfa22-123">If your access has not been scoped to a specific set of devices in the Microsoft Defender ATP, you will have full access to data in Microsoft Threat Protection.</span></span> <span data-ttu-id="cfa22-124">Zodra uw account echter is gescoped, ziet u alleen gegevens over de apparaten in uw bereik.</span><span class="sxs-lookup"><span data-stu-id="cfa22-124">However, once your account is scoped, you will only see data about the devices in your scope.</span></span>

<span data-ttu-id="cfa22-125">Als u bijvoorbeeld tot slechts één gebruikersgroep behoort met een Microsoft Defender ATP-rol en die gebruikersgroep alleen toegang heeft gekregen tot verkoopapparaten, ziet u alleen gegevens over verkoopapparaten in Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="cfa22-125">For example, if you belong to only one user group with a Microsoft Defender ATP role and that user group has been given access to sales devices only, you will see only data about sales devices in Microsoft Threat Protection.</span></span> [<span data-ttu-id="cfa22-126">Meer informatie over RBAC-instellingen in Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="cfa22-126">Learn more about RBAC settings in Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a><span data-ttu-id="cfa22-127">Besturingselementen voor beveiligingsbeheer van Microsoft Cloud App</span><span class="sxs-lookup"><span data-stu-id="cfa22-127">Microsoft Cloud App Security access controls</span></span>
<span data-ttu-id="cfa22-128">Tijdens de preview dwingt Microsoft Threat Protection geen toegangscontroles af op basis van beveiligingsinstellingen voor cloudapps.</span><span class="sxs-lookup"><span data-stu-id="cfa22-128">During the preview, Microsoft Threat Protection does not enforce access controls based on  Cloud App Security settings.</span></span> <span data-ttu-id="cfa22-129">De toegang tot gegevens over bedreigingsbeveiliging van Microsoft wordt niet beïnvloed door deze instellingen.</span><span class="sxs-lookup"><span data-stu-id="cfa22-129">Access to Microsoft Threat Protection data is not affected by these settings.</span></span>

## <a name="related-topics"></a><span data-ttu-id="cfa22-130">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="cfa22-130">Related topics</span></span>

- [<span data-ttu-id="cfa22-131">Azure AD-rollen</span><span class="sxs-lookup"><span data-stu-id="cfa22-131">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [<span data-ttu-id="cfa22-132">Microsoft Defender ATP RBAC</span><span class="sxs-lookup"><span data-stu-id="cfa22-132">Microsoft Defender ATP RBAC</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [<span data-ttu-id="cfa22-133">Beveiligingsrollen voor cloudapps</span><span class="sxs-lookup"><span data-stu-id="cfa22-133">Cloud App Security roles</span></span>](https://docs.microsoft.com/cloud-app-security/manage-admins)
