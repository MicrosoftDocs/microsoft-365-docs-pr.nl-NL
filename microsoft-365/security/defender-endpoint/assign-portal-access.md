---
title: Gebruikerstoegang toewijzen aan microsoft Defender-beveiligingscentrum
description: Wijs alleen lees- en schrijf- of leestoegang toe aan de Microsoft Defender for Endpoint-portal.
keywords: gebruikersrollen toewijzen, lees- en schrijftoegang toewijzen, alleen-lezentoegang toewijzen, gebruiker, gebruikersrollen, rollen
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 11/28/2018
ms.technology: mde
ms.openlocfilehash: 71215c4988351644cfa4d79503c097c932caf9d6
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164753"
---
# <a name="assign-user-access-to-microsoft-defender-security-center"></a><span data-ttu-id="78341-104">Gebruikerstoegang toewijzen aan microsoft Defender-beveiligingscentrum</span><span class="sxs-lookup"><span data-stu-id="78341-104">Assign user access to Microsoft Defender Security Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="78341-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="78341-105">**Applies to:**</span></span>
- <span data-ttu-id="78341-106">Microsoft Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="78341-106">Azure Active Directory</span></span>
- <span data-ttu-id="78341-107">Office 365</span><span class="sxs-lookup"><span data-stu-id="78341-107">Office 365</span></span>
- [<span data-ttu-id="78341-108">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="78341-108">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="78341-109">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="78341-109">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="78341-110">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="78341-110">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="78341-111">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="78341-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="78341-112">Defender voor Eindpunt ondersteunt twee manieren om machtigingen te beheren:</span><span class="sxs-lookup"><span data-stu-id="78341-112">Defender for Endpoint supports two ways to manage permissions:</span></span>

- <span data-ttu-id="78341-113">**Beheer van basismachtigingen:** Machtigingen instellen voor volledige toegang of alleen-lezen.</span><span class="sxs-lookup"><span data-stu-id="78341-113">**Basic permissions management**: Set permissions to either full access or read-only.</span></span>
- <span data-ttu-id="78341-114">**RBAC (Role-based Access Control)**: Stel granulaire machtigingen in door rollen te definiëren, Gebruikersgroepen van Azure AD toe te wijzen aan de rollen en gebruikersgroepen toegang te verlenen tot apparaatgroepen.</span><span class="sxs-lookup"><span data-stu-id="78341-114">**Role-based access control (RBAC)**: Set granular permissions by defining roles, assigning Azure AD user groups to the roles, and granting the user groups access to device groups.</span></span> <span data-ttu-id="78341-115">Zie Portaltoegang beheren met behulp van op rollen [gebaseerd toegangsbeheer](rbac.md)voor meer informatie over RBAC.</span><span class="sxs-lookup"><span data-stu-id="78341-115">For more information on RBAC, see [Manage portal access using role-based access control](rbac.md).</span></span>

> [!NOTE]
> <span data-ttu-id="78341-116">Als u al basismachtigingen hebt toegewezen, kunt u op elk gewenst moment overschakelen naar RBAC.</span><span class="sxs-lookup"><span data-stu-id="78341-116">If you have already assigned basic permissions, you may switch to RBAC anytime.</span></span> <span data-ttu-id="78341-117">Houd rekening met het volgende voordat u overschakelt:</span><span class="sxs-lookup"><span data-stu-id="78341-117">Consider the following before making the switch:</span></span>
> 
> - <span data-ttu-id="78341-118">Gebruikers met volledige toegang (gebruikers die de directoryrol globale beheerder of beveiligingsbeheerder in Azure AD hebben toegewezen), krijgen automatisch de standaardrol van de Defender voor eindpuntbeheerder toegewezen, die ook volledige toegang heeft.</span><span class="sxs-lookup"><span data-stu-id="78341-118">Users with full access (users that are assigned the Global Administrator or Security Administrator directory role in Azure AD), are automatically assigned the default Defender for Endpoint administrator role, which also has full access.</span></span> <span data-ttu-id="78341-119">Extra Azure AD-gebruikersgroepen kunnen worden toegewezen aan de beheerdersrol van Defender voor Eindpunt nadat u bent overstappen op RBAC.</span><span class="sxs-lookup"><span data-stu-id="78341-119">Additional Azure AD user groups can be assigned to the Defender for Endpoint administrator role after switching to RBAC.</span></span>  <span data-ttu-id="78341-120">Alleen gebruikers die zijn toegewezen aan de beheerdersrol van Defender voor Eindpunt, kunnen machtigingen beheren met RBAC.</span><span class="sxs-lookup"><span data-stu-id="78341-120">Only users assigned to the Defender for Endpoint administrator role can manage permissions using RBAC.</span></span> 
> - <span data-ttu-id="78341-121">Gebruikers met alleen-lezentoegang (beveiligingslezers) hebben geen toegang meer tot de portal totdat ze een rol krijgen toegewezen.</span><span class="sxs-lookup"><span data-stu-id="78341-121">Users that have read-only access (Security Readers) will lose access to the portal until they are assigned a role.</span></span> <span data-ttu-id="78341-122">Houd er rekening mee dat alleen Azure AD-gebruikersgroepen een rol kunnen worden toegewezen onder RBAC.</span><span class="sxs-lookup"><span data-stu-id="78341-122">Note that only Azure AD user groups can be assigned a role under RBAC.</span></span>
> - <span data-ttu-id="78341-123">Nadat u bent overschakelt naar RBAC, kunt u niet meer teruggaan naar basismachtigingenbeheer.</span><span class="sxs-lookup"><span data-stu-id="78341-123">After switching to RBAC, you will not be able to switch back to using basic permissions management.</span></span>

## <a name="related-topics"></a><span data-ttu-id="78341-124">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="78341-124">Related topics</span></span>

- [<span data-ttu-id="78341-125">Basismachtigingen gebruiken om toegang te krijgen tot de portal</span><span class="sxs-lookup"><span data-stu-id="78341-125">Use basic permissions to access the portal</span></span>](basic-permissions.md)
- [<span data-ttu-id="78341-126">Portaltoegang beheren met RBAC</span><span class="sxs-lookup"><span data-stu-id="78341-126">Manage portal access using RBAC</span></span>](rbac.md)
