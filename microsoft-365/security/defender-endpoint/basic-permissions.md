---
title: Basismachtigingen gebruiken om toegang te krijgen tot Microsoft Defender-beveiligingscentrum
description: Meer informatie over het gebruik van basismachtigingen voor toegang tot de Microsoft Defender for Endpoint-portal.
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
ms.technology: mde
ms.openlocfilehash: 2d022e903111c498d6f3b7411857748fcb637b64
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844656"
---
# <a name="use-basic-permissions-to-access-the-portal"></a><span data-ttu-id="83b27-104">Basismachtigingen gebruiken voor toegang tot de portal</span><span class="sxs-lookup"><span data-stu-id="83b27-104">Use basic permissions to access the portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="83b27-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="83b27-105">**Applies to:**</span></span>
- <span data-ttu-id="83b27-106">Microsoft Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="83b27-106">Azure Active Directory</span></span>
- [<span data-ttu-id="83b27-107">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="83b27-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="83b27-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="83b27-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="83b27-109">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="83b27-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="83b27-110">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="83b27-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-basicaccess-abovefoldlink)

<span data-ttu-id="83b27-111">Raadpleeg de onderstaande instructies voor het gebruik van basismachtigingenbeheer.</span><span class="sxs-lookup"><span data-stu-id="83b27-111">Refer to the instructions below to use basic permissions management.</span></span>

<span data-ttu-id="83b27-112">U kunt een van de volgende oplossingen gebruiken:</span><span class="sxs-lookup"><span data-stu-id="83b27-112">You can use either of the following solutions:</span></span>
- <span data-ttu-id="83b27-113">Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="83b27-113">Azure PowerShell</span></span>
- <span data-ttu-id="83b27-114">Azure-portal</span><span class="sxs-lookup"><span data-stu-id="83b27-114">Azure portal</span></span>

<span data-ttu-id="83b27-115">Voor gedetailleerde controle over machtigingen schakelt u over naar toegangsbesturingselement [op basis van rollen.](rbac.md)</span><span class="sxs-lookup"><span data-stu-id="83b27-115">For granular control over permissions, [switch to role-based access control](rbac.md).</span></span>

## <a name="assign-user-access-using-azure-powershell"></a><span data-ttu-id="83b27-116">Gebruikerstoegang toewijzen met Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="83b27-116">Assign user access using Azure PowerShell</span></span>
<span data-ttu-id="83b27-117">U kunt gebruikers toewijzen met een van de volgende machtigingsniveaus:</span><span class="sxs-lookup"><span data-stu-id="83b27-117">You can assign users with one of the following levels of permissions:</span></span>
- <span data-ttu-id="83b27-118">Volledige toegang (lezen en schrijven)</span><span class="sxs-lookup"><span data-stu-id="83b27-118">Full access (Read and Write)</span></span>
- <span data-ttu-id="83b27-119">Alleen-lezen toegang</span><span class="sxs-lookup"><span data-stu-id="83b27-119">Read-only access</span></span>

### <a name="before-you-begin"></a><span data-ttu-id="83b27-120">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="83b27-120">Before you begin</span></span>

- <span data-ttu-id="83b27-121">Installeer Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="83b27-121">Install Azure PowerShell.</span></span> <span data-ttu-id="83b27-122">Zie Het installeren en configureren van Azure PowerShell voor [meer informatie.](https://azure.microsoft.com/documentation/articles/powershell-install-configure/)</span><span class="sxs-lookup"><span data-stu-id="83b27-122">For more information, see, [How to install and configure Azure PowerShell](https://azure.microsoft.com/documentation/articles/powershell-install-configure/).</span></span><br>

    > [!NOTE]
    > <span data-ttu-id="83b27-123">U moet de PowerShell-cmdlets uitvoeren op een verhoogde opdrachtregel.</span><span class="sxs-lookup"><span data-stu-id="83b27-123">You need to run the PowerShell cmdlets in an elevated command-line.</span></span>

- <span data-ttu-id="83b27-124">Verbinding maken naar uw Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="83b27-124">Connect to your Azure Active Directory.</span></span> <span data-ttu-id="83b27-125">Zie [Verbinding maken-MsolService](/powershell/module/msonline/connect-msolservice?view=azureadps-1.0&preserve-view=true)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="83b27-125">For more information, see [Connect-MsolService](/powershell/module/msonline/connect-msolservice?view=azureadps-1.0&preserve-view=true).</span></span>

<span data-ttu-id="83b27-126">**Volledige toegang**</span><span class="sxs-lookup"><span data-stu-id="83b27-126">**Full access**</span></span> <br>
<span data-ttu-id="83b27-127">Gebruikers met volledige toegang kunnen zich aanmelden, alle systeemgegevens bekijken en waarschuwingen oplossen, bestanden indienen voor uitgebreide analyse en het onboarding-pakket downloaden.</span><span class="sxs-lookup"><span data-stu-id="83b27-127">Users with full access can log in, view all system information and resolve alerts, submit files for deep analysis, and download the onboarding package.</span></span>
<span data-ttu-id="83b27-128">Als u volledige toegangsrechten toewijst, moeten de gebruikers worden toegevoegd aan de ingebouwde rollen 'Beveiligingsbeheerder' of 'Globale beheerder'.</span><span class="sxs-lookup"><span data-stu-id="83b27-128">Assigning full access rights requires adding the users to the "Security Administrator" or "Global Administrator" AAD built-in roles.</span></span>

<span data-ttu-id="83b27-129">**Alleen-lezen toegang**</span><span class="sxs-lookup"><span data-stu-id="83b27-129">**Read-only access**</span></span> <br>
<span data-ttu-id="83b27-130">Gebruikers met alleen-lezen toegang kunnen zich aanmelden, alle waarschuwingen en gerelateerde informatie bekijken.</span><span class="sxs-lookup"><span data-stu-id="83b27-130">Users with read-only access can log in, view all alerts, and related information.</span></span>
<span data-ttu-id="83b27-131">Ze kunnen geen waarschuwingstoestanden wijzigen, bestanden indienen voor uitgebreide analyse of statuswijzigingsbewerkingen uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="83b27-131">They will not be able to change alert states, submit files for deep analysis or perform any state changing operations.</span></span>
<span data-ttu-id="83b27-132">Als u alleen-lezentoegangsrechten toewijst, moeten de gebruikers worden toegevoegd aan de ingebouwde azure AD-rol 'Beveiligingslezer'.</span><span class="sxs-lookup"><span data-stu-id="83b27-132">Assigning read-only access rights requires adding the users to the "Security Reader" Azure AD built-in role.</span></span>

<span data-ttu-id="83b27-133">Gebruik de volgende stappen om beveiligingsrollen toe te wijzen:</span><span class="sxs-lookup"><span data-stu-id="83b27-133">Use the following steps to assign security roles:</span></span>

- <span data-ttu-id="83b27-134">Voor **lees- en schrijftoegang** wijst u gebruikers toe aan de rol van beveiligingsbeheerder met de volgende opdracht:</span><span class="sxs-lookup"><span data-stu-id="83b27-134">For **read and write** access, assign users to the security administrator role by using the following command:</span></span>

  ```PowerShell
  Add-MsolRoleMember -RoleName "Security Administrator" -RoleMemberEmailAddress "secadmin@Contoso.onmicrosoft.com"
  ```
  
- <span data-ttu-id="83b27-135">Voor **alleen-lezentoegang** wijst u gebruikers toe aan de rol van de beveiligingslezer met de volgende opdracht:</span><span class="sxs-lookup"><span data-stu-id="83b27-135">For **read-only** access, assign users to the security reader role by using the following command:</span></span>

  ```PowerShell
  Add-MsolRoleMember -RoleName "Security Reader" -RoleMemberEmailAddress "reader@Contoso.onmicrosoft.com"
  ```

<span data-ttu-id="83b27-136">Zie Groepsleden [toevoegen of](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)verwijderen met behulp van Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="83b27-136">For more information, see [Add or remove group members using Azure Active Directory](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal).</span></span>

## <a name="assign-user-access-using-the-azure-portal"></a><span data-ttu-id="83b27-137">Gebruikerstoegang toewijzen met de Azure-portal</span><span class="sxs-lookup"><span data-stu-id="83b27-137">Assign user access using the Azure portal</span></span>

<span data-ttu-id="83b27-138">Zie Beheerders- en [niet-beheerdersrollen](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)toewijzen aan gebruikers met Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="83b27-138">For more information, see [Assign administrator and non-administrator roles to users with Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).</span></span>

## <a name="related-topic"></a><span data-ttu-id="83b27-139">Verwant onderwerp</span><span class="sxs-lookup"><span data-stu-id="83b27-139">Related topic</span></span>

- [<span data-ttu-id="83b27-140">Portaltoegang beheren met RBAC</span><span class="sxs-lookup"><span data-stu-id="83b27-140">Manage portal access using RBAC</span></span>](rbac.md)
